---
title: "Peersky Browser"
authors: [akhileshthite]
author_notes: ["MS Student, UC Santa Cruz"]
tags: ["osre26", "dweb", "p2p", "local-first", "browser"]
date: 2026-01-26T12:00:00-08:00
lastmod: 2026-01-26T12:00:00-08:00
---

[Peersky Browser](https://peersky.p2plabs.xyz/) is an experimental personal gatekeeper to a new way of accessing web content. In a world where a handful of big companies control most of the internet, Peersky leverages distributed web technologies—[IPFS](https://ipfs.tech/), [Hypercore](https://holepunch.to/), and [BitTorrent](https://www.bittorrent.com/) return control to the users. With integrated local P2P applications, Peersky offers a fresh, community-driven approach to browsing.

### Implement P2P Extension Store

- **Topics:** `Browser Extensions`, `P2P`, `Electron`, `IPFS`, `Hypercore`
- **Skills:** JavaScript, Electron.js, HTML/CSS, P2P
- **Difficulty:** Moderate
- **Size:** Medium (175 hours)
- **Mentors:** {{% mention akhileshthite %}}

Build a decentralized extension distribution flow that archives WebExtensions into a predictable P2P-friendly layout and installs directly from P2P URLs.

**Tasks:**

- **Define the P2P extension layout:**
  - Standardize `/extensions/{name}/{version}/extension.zip` and `/extensions/{name}/index.json`.
- **Design install compatibility for P2P URLs:**
  - Support `peersky://extensions/...` and P2P links from IPFS or Hypercore.
- **Archive Chrome Web Store extensions to P2P:**
  - Use [chrome-extension-fetch](https://github.com/akhileshthite/chrome-extension-fetch) to fetch CRX, convert to ZIP, and store it in the layout.
  - Update `index.json` with metadata like version, `P2P_URL`, and `fetchedAt`.
  - Publish the folder to IPFS or Hypercore and feed the link into the install flow.
- **Add settings and trust model:**
  - Add a “Load from P2P” settings toggle.
  - Support curated extension hoards (`index.json`) and automated updates.
  - Clarify integrity assumptions and sandboxing expectations.

**More details in the issue:** https://github.com/p2plabsxyz/peersky-browser/issues/42

### Backup & Restore System (P2P JSON + Tabs Restore)

- **Topics:** `P2P`, `Backup`, `Session Restore`, `Electron`, `Onboarding`
- **Skills:** JavaScript, Electron.js, HTML/CSS, P2P
- **Difficulty:** Moderate
- **Size:** Medium (175 hours)
- **Mentors:** {{% mention akhileshthite %}}

Implement a backup and restore pipeline for Peersky’s P2P app data and session state, including an onboarding import flow for tabs from other browsers.

**Tasks:**

- **Generate a P2P backup bundle:**
  - Create a single `.zip` that contains `lastOpened.json`, `tabs.json`, `ensCache.json`, and the `ipfs/` and `hyper/` directories.
  - Add an option to generate a CID for the backup zip for instant sharing.
- **Restore from settings:**
  - Upload a P2P backup zip file.
  - Load a backup from an IPFS or Hyper CID.
  - Import Chrome/Firefox tab exports produced by a helper extension.
- **Define the helper extension export format:**
  - Create a small extension under [p2plabsxyz](https://github.com/p2plabsxyz/) to export windows and tabs (URLs, titles, window grouping, active tab indexes).
  - Ensure the export format is compatible with Peersky’s import pipeline.
- **Add onboarding import flow:**
  - Show `onboarding.html` on first launch and prompt “Import tabs from another browser?”.
  - Guide users to install the helper extension and import the generated file.
- **Align with existing persistence:**
  - Reuse `lastOpened.json`, `tabs.json`, and `peersky-browser-tabs` localStorage for restores.

**More details in the issue:** https://github.com/p2plabsxyz/peersky-browser/issues/60
