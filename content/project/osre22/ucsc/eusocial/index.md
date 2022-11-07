---
title: "Eusocial Storage Devices"
authors: ["Jianshen Liu",admin]
author_notes: ["Ph.D. Student, UC Santa Cruz"]
categories: ["osre22"]
tags: ["uc"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

As storage devices get faster, data management tasks rob the host of CPU cycles and main memory bandwidth. The [Eusocial project](https://cross.ucsc.edu/projects/eusocialpage.html) aims to create a new interface to storage devices that can leverage existing and new CPU and main memory resources to take over data management tasks like availability, recovery, and migrations. The project refers to these storage devices as “eusocial” because we are inspired by eusocial insects like ants, termites, and bees, which as individuals are primitive but collectively accomplish amazing things.

### Dynamic function injection for RocksDB

 - **Skills:** C/C++, Java
 - **Difficulty:** Challenging
 - **Size** 175 or 350 hours 
 - **Mentor:** [Jianshen Liu](mailto:jliu120@ucsc.edu)

Recent research reveals that the compaction process in RocksDB can be altered to optimize future data access by changing the data layout in compaction levels. The benefit of this approach can be extended to different data layout optimization based on application access patterns and requirements. In this project, we want to create an interface that would allow users to dynamically inject layout optimization functions to RockDB, using containerization technologies such as Webassembly.
 - Reference: Saxena, Hemant, et al. "Real-Time LSM-Trees for HTAP Workloads." arXiv preprint arXiv:2101.06801 (2021).

### Demonstrating a composable storage system accelerated by memory semantic technologies

 - **Skills:** C/C++, Bash, Python, System architecture, Network fabrics
 - **Difficulty:** Challenging
 - **Size** 350 hours 
 - **Mentor:** [Jianshen Liu](mailto:jliu120@ucsc.edu)

Since the last decade, the slowing down in the performance improvement of general-purpose processors is driving the system architecture to be increasingly heterogeneous. We have seen the kinds of domain-specific accelerator hardware (e.g., FPAG, SmartNIC, TPU, GPU) are growing to take over many different jobs from the general-purpose processors. On the other hand, the network and storage device performance have been tremendously improved with a trajectory much outweighed than that of processors. With this trend, a natural thought to continuously scale the storage system performance economically is to efficiently utilize and share different sources from different nodes over the network. There already exist different resource sharing protocols like CCIX, CXL, and GEN-Z. Among these GEN-Z is the most interesting because, unlike RDMA, it enables remote memory accessing without exposing details to applications (i.e., not application changes). Therefore, it would be interesting to see how/whether these technologies can help improve the performance of storage systems, and to what extent. This project would require building a demo system that uses some of these technologies (especially GEN-Z) and run selected applications/workloads to better understand the benefits.
 - References: Gen-Z: An Open Memory Fabric for Future Data Processing Needs: https://www.youtube.com/watch?v=JLb9nojNS8E, Pekon Gupta, SMART Modular; Gen-Z subsystem for Linux, https://github.com/linux-genz

### When will Rotational Media Users abandon SATA and converge to NVMe?

- **Skills:** Entrepreneurial mind, interest in researching high technology markets
- **Difficulty:** Medium
- **Size:** 350 hours 
- **Mentor:** [Carlos Maltzahn](mailto:carlosm@ucsc.edu)

**Goal:** Determine the benefits in particular market verticals such as genomics and health care to converge the storage stack in data center computer systems to the NVMe device interface, even when devices include rotational media (aka disk drives). The key question: “When do people abandon SATA and SAS and converge to NVMe?”

**Background:** NVMe is a widely used device interface for fast storage devices such as flash that behave much more like random access memory than the traditional rotational media. Rotational media is accessed mostly via SATA and SAS which has served the industry well for close to two decades. SATA in particular is much cheaper than NVMe. Now that NVMe is widely available and quickly advancing in functionality, an interesting question is whether there is a market for rotational media devices with NVMe interfaces, converging the storage stack to only one logical device interface, thereby enabling a common ecosystem and more efficient connectivity from multiple processes to storage devices.

The NVMe 2.0 specification, which came out last year, has been restructured to support the increasingly diverse NVMe device environment (including rotational media). The extensibility of 2.0 encourages enhancements of independent command sets such as Zoned Namespaces (ZNS) and Key Value (NVMe-KV) while supporting transport protocols for NVMe over Fabrics (NVMe-oF). A lot of creative energy is now focused on advancing NVMe while SATA has not changed in 16 years. Having all storage devices connect the same way not only frees up space on motherboards but also enables new ways to manage drives, for example via NVMe-oF that allows drives to be networked without additional abstraction layers.

**Suggested Project Structure:** This is really just a suggestion for a starting point. As research progresses, a better structure might emerge.

1. Convergence of software stack: seamless integration between rotational media and hot storage  
  - Direct tiering: one unified interface to place data among fast and slow devices on the same NVMe fabric depending on whether the data is hot or cold.
2. Computational storage:  
  - What are the architectures of computational NVMe devices? For example, offloading compute to an FPGA vs an onboard processor in a disk drive?  
  - Do market verticals such as genomics and health care for one over the other? When do people abandon SATA and converge to NVMe? 

**Project tasks:**
- Review current literature
- Survey what the industry is doing
- Join weekly meetings to discuss findings with Ph.D. students, experienced industry veterans, and faculty (Thursday’s 2-3pm, can be adjusted if necessary)
- Product is a slide deck with lots of pictures


**Interesting links:**  
https://www.opencompute.org/wiki/Storage/NVMeHDD  
https://2021ocpglobal.fnvirtual.app/a/event/1714 (video and slides, requires $0 registration)  
https://www.storagereview.com/news/nvme-hdd-edges-closer-to-reality  
https://www.tomshardware.com/news/seagate-demonstrates-hdd-with-pcie-nvme-interface  
https://nvmexpress.org/everything-you-need-to-know-about-the-nvme-2-0-specifications-and-new-technical-proposals/  
https://www.tomshardware.com/news/nvme-2-0-supports-hard-disk-drives  

