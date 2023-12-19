---
title: "Reproducible Analysis & Models for Predicting Genomics Workflow Execution Time (Midterm Blog Post)"
subtitle: ""
summary:
authors: ['charishulu']
tags: ["osre23", reproducibility]
categories: [SoR'23]
date: 2023-08-03
lastmod: 2023-08-03
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

## Introduction

As part of the [Reproducible Analysis & Models for Predicting Genomics Workflow Execution Time](/project/osre23/uga/genomicswfmodels/), our goal was to characterize the tools on genomic workflows in terms of system metrics and data quality to build machine learning models to predict the elapsed time of genomic workflows. While Shayantan (another contributor) did the analysis on data quality metrics, I contributed to the system metrics analysis. We are getting closer to that goal because we have managed to collect datasets and do some analysis.

## Steps

In this project, we selected DNA-Seq Pipeline as the workflow to be analyzed. This pipeline consists of four tools for processing single-end reads, namely BWA-mem, Samtool-view, Picard-SortSam, Picard-MarkDuplicates. For each tool we executed it using various configurations and stored system metrics for each execution. To do this, we have to take two steps:
* Step 1: Building the tools execution environment.
* Step 2: Developing a program to execute tools using some configurations and collect runtime parameters (eg. CPU, RSS, VSZ, and IO) automatically.


## Execution Environment

Tools are executed on Chameleon instances by submitting them using Slurm. The machine used in collecting system metrics is a Haswell instance of the Chameleon Texas server. This instance uses Intel(R) Xeon(R) CPU E5-2670 v3 @ 2.30GHz with following detailed specifications.


<table>
    <tr>
        <th>Number of CPUs</th>
        <td>48</td>
    </tr>
    <tr>
        <th>Number of threads per core</th>
        <td>2</td>
    </tr>
    <tr>
        <th>Number of cores per socket</th>
        <td>12</td>
    </tr>
    <tr>
        <th>Number of sockets</th>
        <td>2</td>
    </tr>
</table>

In this experiment, we use n+1 instances, where there are n compute nodes and 1 master node. Each execution is done by submitting a job, which is a tool with a certain configuration, from a master node and it will be processed by one of the compute nodes. In order for the tool to be executed, we need to set the master node to be a common container using NFS. This common container is used to store input files and commands for executing tools so that all nodes can access them without having to download and install them.


## Executing and Collecting System Metrics

Tools will be executed in various specific configurations by varying parameters such as input size, number of CPU allocation, memory allocation and threads. For example, for BWA-mem respectively the number of variations in values for the number of CPU allocations, memory allocations, and threads is 5, 4, and 5 using 10 different files so that there are 5 x 4 x 5 x 10 = 1000 configuration combinations. For each configuration will be executed 8 times so that there are 8000 data points. Configuration details can be seen in the following table.

<table>
    <tr>
        <th></th>
        <th>#repetions</th>
        <th>#files</th>
        <th>#allocated CPU</th>
        <th>#allocated memory</th>
        <th>#threads</th>
        <th>total</th>
    </tr>
    <tr>
        <th>BWA-mem</th>
        <td>8</td>
        <td>10</td>
        <td>2, 4, 8, 16, 32</td>
        <td>8, 16, 32, 64</td>
        <td>2, 4, 8, 16, 32</td>
        <td>8000</td>
    </tr>
    <tr>
        <th>Samtool-view</th>
        <td>10</td>
        <td>10</td>
        <td>2, 4, 8, 16, 32</td>
        <td>8, 16, 32, 64</td>
        <td>-</td>
        <td>2000</td>
    </tr>
    <tr>
        <th>Picard-Sortsam</th>
        <td>10</td>
        <td>10</td>
        <td>2, 4, 8, 16, 32</td>
        <td>8, 16, 32, 64</td>
        <td>-</td>
        <td>2000</td>
    </tr>
    <tr>
        <th>Picard-MarkDuplicates</th>
        <td>10</td>
        <td>10</td>
        <td>2, 4, 8, 16, 32</td>
        <td>8, 16, 32, 64</td>
        <td>-</td>
        <td>2000</td>
    </tr>
</table>

Meanwhile, to run the tools, we use the following commands:

* BWA-mem
```shell 
$BWA mem -t $threads $REF_DIR/hg19.fa ${INPUT_DIR}/${sra_id}*.fastq > ${OUTPUT_DIR}/${sra_id}.sam
```

* Samtool-view
```shell
$SAMTOOLS view $INPUT_DIR/${sra_id}.sam -Shb -o $OUTPUT_DIR/${sra_id}.bam
```

* Picard-SortSam
```shell
java -jar $PICARD SortSam \
CREATE_INDEX=true \
INPUT=$INPUT_DIR/${sra_id}.bam \
OUTPUT=$OUTPUT_DIR/${sra_id}.bam \
SORT_ORDER=coordinate \
VALIDATION_STRINGENCY=STRICT
```

* Picard-MarkDuplicates
```shell
java -jar $PICARD MarkDuplicates \
CREATE_INDEX=true \
INPUT=$INPUT_DIR/${sra_id}.bam \
OUTPUT=$OUTPUT_DIR/${sra_id}.bam \
METRICS_FILE=$OUTPUT_DIR/${sra_id}_rmd.txt \
VALIDATION_STRINGENCY=STRICT

```

In Slurm, each job has a job id. In addition, there is a `scontrol listpids` command to see the job id to PID mapping. Using this, we can obtain system metrics for a job by gathering information from the `/proc/$PID` system file. Information that can be obtained from it is the use of CPU, physical memory, virtual memory, read bytes, and write bytes at a particular time. So that in collecting this data, we will record these features along with the timestamp at 1 second intervals throughout the execution process.

## Results

We also have calculated the correlation for each feature with the elapsed time. For BWA-mem, the features that correlate more than absolute of 0.5 are Input size, Average CPU Usage, and Output file size , which is in SAM format. For samtools there are input size, average cpu usage and output size in BAM. 
For Sortsam, there are input size, write operation, and BAM output size. For MarkDuplicates, there are input size and BAM output size.

<table>
    <tr>
        <th>Features\Tools</th>
        <th>BWA-mem</th>
        <th>Samtool-view</th>
        <th>Picard-SortSam</th>
        <th>Picard-MarkDuplicates</th>
    </tr>
    <tr>
        <th>Allocated CPU</th>
        <td>-0.145</td>
        <td>-0.095</td>
        <td>-0.179</td>
        <td>-0.156</td>
    </tr>
    <tr>
        <th>Allocated physical memory</th>
        <td>-0.010</td>
        <td>-0.038</td>
        <td>-0.069</td>
        <td>0.132</td>
    </tr>
    <tr>
        <th>Input size</th>
        <td><b>0.583</b></td>
        <td><b>0.651</b></td>
        <td><b>0.937</b></td>
        <td><b>0.922</b></td>
    </tr>
    <tr>
        <th>Threads</th>
        <td>-0.072</td>
        <td>-</td>
        <td>-</td>
        <td>-</td>
    </tr>
    <tr>
        <th>Average CPU</th>
        <td><b>-0.607</b></td>
        <td><b>-0.567</b></td>
        <td>-0.479</td>
        <td>-0.480</td>
    </tr>
    <tr>
        <th>Peak CPU</th>
        <td>-0.175</td>
        <td>0.174</td>
        <td>-0.170</td>
        <td>0.046</td>
    </tr>
    <tr>
        <th>Average RSS</th>
        <td>0.040</td>
        <td>0.034</td>
        <td>0.131</td>
        <td>0.182</td>
    </tr>
    <tr>
        <th>Peak RSS</th>
        <td>0.068</td>
        <td>0.046</td>
        <td>0.314</td>
        <td>0.175</td>
    </tr>
    <tr>
        <th>Average VSZ</th>
        <td>0.032</td>
        <td>-0.349</td>
        <td>-0.127</td>
        <td>0.090</td>
    </tr>
    <tr>
        <th>Peak VSZ</th>
        <td>0.048</td>
        <td>0.074</td>
        <td>-0.130</td>
        <td>0.088</td>
    </tr>
    <tr>
        <th>Write bytes</th>
        <td>0.037</td>
        <td>0.190</td>
        <td><b>0.735</b></td>
        <td>0.244</td>
    </tr>
    <tr>
        <th>Read bytes</th>
        <td>-0.031</td>
        <td>0.109</td>
        <td>0.070</td>
        <td>0.110</td>
    </tr>
    <tr>
        <th>Output SAM size</th>
        <td><b>0.589</b></td>
        <td>-</td>
        <td>-</td>
        <td>-</td>
    </tr>
    <tr>
        <th>Output BAM size</th>
        <td>-</td>
        <td><b>0.763</b></td>
        <td><b>0.934</b></td>
        <td><b>0.923</b></td>
    </tr>
    <tr>
        <th>Output BAI size</th>
        <td>-</td>
        <td>-</td>
        <td>0.400</td>
        <td>0.399</td>
    </tr>
</table>

## Future Works
For further work, we will analyze the correlation between elapsed time and features whose scores are below an absolute 0.5. Because there is a possibility that these features are actually correlated with the elapsed time but do not appear to be correlated because the measurements are made by calculating the overall data. So we also need to calculate the feature correlation for each data grouped by input file. Then, we create a machine learning model to predict elapsed time.