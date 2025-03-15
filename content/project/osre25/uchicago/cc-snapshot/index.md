---
title: "Assessing and Enhancing CC-Snapshot for Reproducible Experiment Environments"
authors: [mpowers, msherman]
author_notes: ["University of Chicago", "University of Chicago"]
tags: ["osre25", "reproducibility", "operating systems"]
date: 2025-02-18
lastmod: 2025-02-18
---

## Overview

A critical challenge in computer systems research reproducibility is establishing and sharing experimental environments. While open testbeds like Chameleon provide access to hardware resources, researchers still face significant barriers when attempting to recreate the precise software configurations, dependencies, and system states needed for reproducible experiments. Environment snapshotting tools offer a solution, but face technical challenges in consistently capturing running systems without introducing distortions or requiring disruptive system modifications. This project addresses these fundamental reproducibility barriers by enhancing CC-Snapshot, an tool capturing the experimental environment configured by the user on bare metal images, to create more reliable and consistent system captures that can be shared and redeployed without loss of fidelity.

[CC-Snapshot](https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility) is a tool on the [Chameleon](chameleoncloud.org) testbed that enables users to package their customized environments as complex images or appliances. By allowing researchers to share these environments easily, CC-Snapshot offers a powerful mechanism for reproducibility, ensuring that experiments can be replicated and extended by others.

In this project, you will review existing CC-Snapshot workflows, research the latest snapshotting technologies, and develop enhancements that improve the tool’s usability and reliability. This includes ensuring snapshots are created consistently (even when the OS is actively running), preserving the integrity of user systems, and exploring advanced features such as out-of-band snapshotting and API-based triggers.

## Key Outcomes

- Improved Snapshot Consistency: New methods to capture the full state of a disk without risking corruption or data inconsistency.
- Enhanced Reproducibility: A refined workflow that allows researchers to reliably share custom environments, facilitating collaborative and repeatable experiments.
- User-Friendly Tooling: Streamlined processes that reduce disruption to running systems—so installing dependencies or rebooting into special environments is less burdensome.
- Exploratory Features (Stretch Goals): Advanced mechanisms to stream disk data in real time during snapshotting and to initiate snapshots via an API call (for parity with VM snapshots).

**Topics**: Cloud Computing, Systems & Infrastructure, Reproducibility, Operating System Internals

**Skills**: Linux / OS Concepts, Cloud Tools, Systems Programming / Scripting, DevOps / CI

**Difficulty**: Moderate

**Size**: Medium

**Mentors**: {{% mention msherman %}}, {{% mention mpowers %}}

**Tasks**: 
  - Ensure Snapshot Consistency
    - Reboot into a ramdisk and copy the offline disk.
    - Use kexec to switch to/from a ramdisk environment without a full reboot.
    - Change images to use a snapshot-capable filesystem (e.g., LVM) for safer live snapshots.
    - Investigate additional methods (e.g., blog.benjojo.co.uk) for safely imaging live disks.
  - Prevent System Modifications During Snapshot
    - Currently, CC-Snapshot installs dependencies (e.g., qemu-img) on the running system, affecting its state.
    - In-Band Fix: Download and run tools in a temp directory with static linking, avoiding system-level changes.
    - Out-of-Band Approach: Snapshots done via ramdisk or kexec do not require altering the running system.
  - API-Triggered Snapshots
    - Extend or integrate with the Nova “snapshot instance” API to support the same workflow for bare metal.
    - Leverage Ironic’s new “service steps” feature for an automated snapshot pipeline.
  - (Stretch Goal) Streaming Snapshots
    - Modify the workflow to stream data directly to storage, rather than making a full local copy first.
    - Explore incremental or differential snapshot techniques to reduce bandwidth usage and storage overhead.
