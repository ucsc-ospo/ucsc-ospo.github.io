---
title: "Midterm blog: Data Portability, Backup Systems, and Onboarding in PeerSky Browser"
subtitle: "Building the core backup engine, P2P content-addressed sharing, browser onboarding, and identity transfer"
summary: "A midterm update on implementing full data portability, P2P IPFS/Hypercore backup sharing, browser onboarding flows, and profanity filtering for PeerSky Browser."
authors:
  - ayush-vish
tags: ["osre26", "gsoc", "peersky", "p2p", "ipfs", "hypercore", "backup", "electron"]
categories: ["GSoC 2026", "PeerSky", "Open Source"]
date: 2026-07-24
lastmod: 2026-07-24
featured: true
draft: false
image:
  caption: "PeerSky Browser"
  focal_point: "Center"
  preview_only: false
---

Hi everyone! I am Ayush Vishwakarma, and this is my midterm update for [PeerSky Browser](/project/osre26/ucsc/peersky) under Google Summer of Code 2026 and UC OSPO. I am working under the mentorship of Akhilesh Thite to build data portability infrastructure, decentralized backup engines, browser onboarding flows, and offline messaging capabilities for PeerSky.

If you haven't read it yet, my [introductory blog post](https://ucsc-ospo.github.io/report/osre26/ucsc/peersky/2026-05-23-ayush-vish/) details my background and initial project goals. You can also track our progress across the repositories on [GitHub](https://github.com/p2plabsxyz/peersky-browser).

## Project Recap

PeerSky is a browser built for the peer-to-peer and decentralized web. Unlike traditional browsers where application state resides on centralized servers, PeerSky stores decentralized drives (Hypercore), IPFS content, P2P identity keys, chat histories, and ENS caches directly on the user's device.

While local-first storage ensures privacy and sovereignty, it creates a major challenge: **data portability and resilience**. Reinstalling the browser or moving to a new device could result in lost keys, feeds, and browser states.

My GSoC project addresses this challenge by building:

1. A robust **Core Backup & Restore Engine** to create integrity-verified, atomic profile snapshots.
2. A **P2P Sharing Layer** allowing users to publish and download backups via IPFS CIDs and Hyperdrive addresses.
3. An **Onboarding & Extension Ecosystem** to seamlessly import tab states and browser profiles from Chrome and Firefox.
4. **Identity Transfer Protocols** for secure device-to-device migration.
5. **Offline PeerChat** and mobile backup integration for local mesh communication.

---

## Progress So Far

### 1. Core Backup & Restore Engine ([PR #204](https://github.com/p2plabsxyz/peersky-browser/pull/204))

I implemented a transactional backup and restore engine for PeerSky Browser located under `src/backup/`.

- **Atomic Zip Snapshots with Checksum Verification (`backup-core.js`):** Backups are packaged into portable `.zip` archives containing a SHA-256 integrity manifest. Restore operations extract data transactionally into a temporary directory, verify checksums, enforce zip-slip security guards against path traversal, and exclude runtime lock files (`LOCK`, `SingletonLock`).
- **Worker Thread Processing (`backup-worker.js`):** Heavy archive compression and checksum hashing are offloaded to dedicated worker threads, ensuring the main Electron UI thread remains fast and responsive.
- **Quiesce-then-Zip Strategy (`backup-manager.js`):** To prevent database corruption or file lock conflicts during backups, the backup manager safely suspends active IPFS (Helia) and Hypercore runtime protocols prior to snapshotting and automatically resumes them once the archive is written.
- **Transactional Restore & Cleanup:** On boot, PeerSky inspects and cleans up any orphaned temporary extraction directories left behind by abnormal shutdowns.

### 2. P2P Backup Sharing via IPFS & Hypercore ([PR #204](https://github.com/p2plabsxyz/peersky-browser/pull/204))

Beyond local file export, users can share and retrieve backups across decentralized networks:

- **IPFS & Hyperdrive Publishing (`p2p-backup.js`, `ipfs-backup.js`, `hyper-backup.js`):** Users can publish their backup archives directly to IPFS (`ipfs://<CID>`) or host them over Hyperdrive (`hyper://<address>`).
- **Cache Management:** Local and P2P backup transactions are recorded in `ipfsCache.json` and `hyperCache.json` for history tracking.

### 3. Onboarding Extension & Tab Import Flow ([Extension PR #1](https://github.com/p2plabsxyz/peersky-onboarding-extension/pull/1))

To make transitioning to PeerSky effortless, I developed the **PeerSky Onboarding Extension** for Chromium (Chrome, Brave, Edge) and Firefox:

- **Browser Data Exporter:** The extension exports open tabs, window states, and installed extension lists into a standardized `peersky-export-[timestamp].json` format.
- **Integrated Onboarding UI:** Built an animated, multi-step onboarding wizard in PeerSky Browser (`peersky://backup` and onboarding views) that enables users to import JSON exports or restore P2P ZIP backups directly upon first launch.

### 4. Identity Backup & Multi-Desktop Identity Transfer

In decentralized networks, user identity is tied to cryptographic key pairs. I implemented a device-linked identity migration workflow:

- **Key-Secured Export:** Allows users to separate standard browser backups from sensitive cryptographic identities.
- **QR Code & IPC Pairings:** Generates temporary encryption keys and QR codes to pair desktop and mobile devices securely for identity sync.

### 5. PeerChat Moderation & Filtering Engine ([PeerChat PR #13](https://github.com/p2plabsxyz/peerchat/pull/13))

In the `peerchat` submodule, I upgraded the chat moderation system:

- **External Curated Dataset:** Replaced hardcoded regular expressions with a dynamic, file-based bad words loader backed by curated word lists.
- **High-Performance Filtering:** Utilizes an optimized `Set` structure for instant lookup during chat filtering, with dual fallback support for Node.js file systems and browser `fetch` APIs.

### 6. Testing & CI Pipeline

To ensure safety and reliability, the backup and onboarding stack is backed by 29 unit and integration tests across three test suites (`backup-core`, `backup-manager`, `p2p-backup`). The test suite validates checksum mismatches, lock file exclusions, path traversal rejections, worker error propagation, and P2P address parsing across Linux, macOS, and Windows CI environments.

---

## Challenges and Learnings

- **Quiescing Active P2P Protocols:** One of the trickiest bugs was snapshotting LevelDB databases and SQLite instances while IPFS or Hypercore nodes were actively writing blocks. Suspending runtimes cleanly without dropping peer connections or corrupting open sockets required establishing clear IPC state guards.
- **Cross-Platform File System Differences:** Windows file handling introduced unique challenges regarding locked files and path separators during ZIP extraction. Implementing atomic temporary directory writes and worker thread retries solved cross-platform inconsistencies.

---

## What's Next

For the second half of Google Summer of Code 2026, my focus will shift to:

1. **PeerSky Mobile Backup & Restore Integration:** Porting the core backup engine, CID/Hyper extraction logic, and identity pairing to PeerSky Mobile (React Native / Bare worklet).
2. **Offline PeerChat & Local Mesh Communication:** Implementing offline LAN peer discovery and messaging in PeerChat using Hyperswarm local topic broadcasting, allowing users to chat over local Wi-Fi without internet connectivity.
3. **Refining Cross-Device Identity Sync:** Polishing the mobile QR scanner identity transfer flow and adding seamless restore prompts.
4. **Documentation & Performance Polish:** Expanding developer guides in `docs/Backup.md` and optimizing P2P backup compression speeds.

---

## Closing Thoughts

At the midpoint, PeerSky Browser has acquired a comprehensive data portability infrastructure—from local ZIP backups and P2P IPFS/Hyper sharing to Chrome/Firefox onboarding extensions and device identity transfers.

I want to express my gratitude to my mentor, Akhilesh Thite, for his invaluable feedback, detailed code reviews, and architectural guidance throughout the first half of the program. I am excited to bring these features to PeerSky Mobile and build offline PeerChat capabilities in the coming weeks!
