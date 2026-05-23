---
title: "Data Portability, Backup, and Offline PeerChat for PeerSky Browser"
subtitle: "Introducing my GSoC 2026 project with UC OSPO"
summary: "Building portable backup systems, browser onboarding flows, and offline LAN messaging support for PeerSky Browser."
authors:
  - ayush-vish
tags: ["osre26", "gsoc", "peersky", "p2p", "decentralized-web", "ipfs", "hypercore"]
categories: ["GSoC 2026", "PeerSky"]
date: 2026-05-23
lastmod: 2026-05-23
featured: true
draft: false
image:
  caption: "PeerSky Browser"
  focal_point: "Center"
  preview_only: false
---
Hello! I am Ayush Vishwakarma, a final-year Information Technology undergraduate at Atal Bihari Vajpayee Indian Institute of Information Technology and Management, Gwalior, with a strong interest in decentralized systems, peer-to-peer networking, and browser infrastructure. I enjoy building tools that improve privacy, resilience, and user ownership on the web.

This summer, I will be contributing to the [PeerSky](/project/osre26/ucsc/peersky) project through Google Summer of Code under UC OSPO. My project, "Data Portability, Backup, and Offline PeerChat for PeerSky Browser," focuses on improving portability, onboarding, and offline resilience for decentralized browsing.

The project aims to implement a complete backup and restore pipeline for PeerSky Browser, including portable ZIP-based backups for IPFS and Hypercore data, CID-based backup sharing over peer-to-peer networks, onboarding flows for importing tabs from traditional browsers like Chrome and Firefox, and offline LAN-based PeerChat communication using Hyperswarm local discovery.

One major goal of the project is preserving critical peer-to-peer application state such as Hypercore storage, IPFS repositories, encrypted room identities, and PeerChat messages, ensuring that users can recover their decentralized data even after reinstalls or device failures. Another important focus is enabling PeerChat to continue functioning locally over Wi-Fi networks even when internet connectivity is unavailable.

Before this, I contributed to the PeerSky Browser ecosystem, working on features including the native bookmarks system, P2P app management interfaces, archive management tooling, memory saver functionality, scoped logging, and PeerChat synchronization improvements. These contributions gave me deep familiarity with PeerSky’s session persistence, IPC architecture, and decentralized networking stack.

You can read my full [proposal here](https://drive.google.com/file/d/1LrDEpysZcdr-tRpa2QG8BSA1dj7KThVO/view)

My mentor for this project is Akhilesh Thite.

I am excited to continue contributing to decentralized web infrastructure and help make PeerSky Browser more portable, resilient, and accessible for users. Looking forward to an amazing summer with UC OSPO and PeerSky!
