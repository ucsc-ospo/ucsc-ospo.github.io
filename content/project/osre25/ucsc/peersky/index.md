---
title: "Peersky Browser"
authors: [akhileshthite]
author_notes: ["MS Sudent, UC Santa Cruz"]
tags: ["osre25", "dweb", "p2p", "local-first", "browser"]
date: 2025-02-18T12:00:00-08:00
lastmod: 2025-02-18T12:00:00-08:00
---

[Peersky Browser](https://peersky.p2plabs.xyz/) is an experimental personal gatekeeper to a new way of accessing web content. In a world where a handful of big companies control most of the internet, Peersky leverages distributed web technologies—[IPFS](https://ipfs.tech/), [Hypercore](https://holepunch.to/), and Web3—to return control to the users. With integrated local P2P applications, Peersky offers a fresh, community-driven approach to browsing.

### Implement Web Extensions Integration

- **Topics:** `Browser Extensions`, `UI/UX`, `Electron`
- **Skills:** JavaScript, Electron.js, HTML/CSS
- **Difficulty:** Moderate
- **Size:** Medium (175 hours)
- **Mentors:** [Akhilesh Thite](mailto:athite@ucsc.edu)

Implement web extension support in Electron by leveraging its web extension node modules, pre-installing extensions, and providing a user interface for adding, updating, and securely managing them.

**Tasks:**

- **Loading Extensions via Electron Modules:**
  - Utilize Electron’s web extension node modules to load extensions, as Electron.js doesn't support marketplace integration.
- **Default Pre-installed Extensions:**
  - Configure a set of pre-installed extensions like uBlock to offer immediate value for privacy and security.
- **User-Installed Extensions UI:**
  - Create an interface where users can add extension `.zip` files in `peersky://settings`.
  - Add an option for users to manually update all installed extensions.
- **Validate and Sandbox Extensions:**
  - Check the integrity and manifest structure of the uploaded extensions to ensure they meet Chrome Manifest V3 requirements.
  - Apply sandboxing techniques and enforce strict content security policies to mitigate potential risks.
- **Extension Management UI:**
  - Design a dedicated UI at the top right of the navigation bar to manage extensions, including stack order and pinning functionality for quick access and organization.

### Implement Chat History Synchronization for Hyper Chat Rooms

- **Topics:** `P2P Communication`, `Hypercore Protocol`, `Real-time Synchronization`
- **Skills:** JavaScript, Distributed Systems, P2P
- **Difficulty:** Moderate
- **Size:** Medium (175 hours)
- **Mentors:** [Akhilesh Thite](mailto:athite@ucsc.edu)

Implement chat history synchronization for Hyper chat rooms, ensuring that new devices retrieve all past messages—including those sent while offline—for a seamless user experience. Additionally, research and experiment with mDNS to enable true offline, peer-to-peer messaging on local networks.

**Tasks:**

- **History Retrieval Mechanism:**
  - Implement chat history synchronization so that when a new device joins a Hyper chat room, it retrieves the entire chat history from the Hypercore feed.
- **Offline Message Inclusion:**
  - Ensure that devices that were offline during prior messages can still access the full chat history upon joining the room, even after messages were sent in their absence.
- **UI Integration:**
  - Create a seamless experience for users across devices by ensuring that no messages are lost and that users can access the full chat history regardless of their online status.
- **Research mDNS (Multicast DNS):**
  - mDNS is a protocol that allows devices on the same local network to communicate with each other without the need for a central DNS server. This enables peer-to-peer communication, especially in offline environments, making it ideal for offline messaging.
  - Experiment with the `mDNS()` function to enable peer-to-peer communication for offline chat rooms.
- **Create Hyper Chat Web App Version:**
  - Currently, Hyper chat is accessed via `peersky://p2p/chat`. Develop a web app version of Hyper chat that can be hosted on the `hyper://` protocol (`hyper://chat.p2plabs.xyz`). This way, other P2P browsers (like [Agregore](https://agregore.mauve.moe/)) can use it to communicate.
