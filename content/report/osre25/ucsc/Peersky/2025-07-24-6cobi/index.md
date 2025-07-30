---
title: "[MidTerm] Building PeerSky’s Settings System"
subtitle: "Modular preferences, secure IPC, and dynamic theming in a decentralized browser"
summary: "A midterm update on my GSoC 2025 progress building the settings architecture for the PeerSky browser with UC OSPO."
authors:
  - 6cobi
tags: ["osre25", "Electron", "Peersky", "Dweb"]
categories: ["web-development"]
date: 2025-07-24
lastmod: 2025-07-24
featured: true
draft: false

image:
  caption: "Hanzhong Liu, GSoC 2025"
  focal_point: "Center"
  preview_only: false
---
Hi everyone, I’m Hanzhong Liu. My project focuses on building a secure and extensible `peersky://settings` system for the [PeerSky browser](https://github.com/p2plabsxyz/peersky-browser), a decentralized and privacy-first browser built on Electron.

This post is a midterm check-in covering what’s been implemented so far — from IPC architecture to real-time theme and wallpaper updates — and a preview of what’s coming next.

## Project Overview

Peersky’s new settings system is designed to unify browser preferences (themes, search engine, appearance, extensions, etc.) into a single modular interface. It’s accessible via a protocol route (`peersky://settings`) and built using web-standard HTML/CSS, scoped APIs, and Electron’s context isolation model.

### Key Design Goals:
- Secure preload-based API exposure via `contextBridge`
- Fast access to user preferences with zero-flicker wallpaper updates
- Extensibility for bookmarks, future plugins, and privacy tools

## Midterm Progress Highlights

### Electron Integration

Rather than using `webFrame.executeJavaScript()`, I implemented preload-scoped APIs using `contextBridge` and `ipcRenderer` to prevent injection vulnerabilities and ensure synchronous availability during early page load. Each internal protocol (settings, home, bookmarks) is granted its own API access level.

> Code: [`src/pages/unified-preload.js`](https://github.com/p2plabsxyz/peersky-browser/blob/main/src/pages/unified-preload.js)

### Modular Settings Page

The UI lives in a single HTML file with sidebar-based navigation (Appearance, Search, Bookmarks, Extensions). Each section updates independently using event-driven IPC and live sync.

### Wallpaper & Theme Switching

- Supports both built-in wallpapers and custom uploads
- Background applies instantly using `sendSync()` during preload
- Themes (light, dark, system) are controlled using root-level CSS variables and real-time IPC events

![Wallpaper](https://hackmd.io/_uploads/S11q7M1Dee.png)

### Cache & Search Engine

- Added IPC handler to clear both Electron session and P2P cache directories (`ipfs/`, `hyper/`)
- Settings API allows switching between DuckDuckGo, Ecosia, and Startpage via dropdown

### Example: Adding a New Setting (`autoSave`)

I also documented how developers can add new settings like `autoSave` using:
- `settings-manager.js` for default values and validation
- Preload event listeners (`onAutoSaveChanged`)
- UI toggles and save logic in `settings.js`

Documentation link: [Settings Guide](https://github.com/p2plabsxyz/peersky-browser/blob/main/docs/settings.md)


## Reflection

I’m really thankful for the mentorship I’ve received from Akhilesh Thite. His guidance has been the perfect balance of autonomy and support. He challenged me to reason clearly about technical choices, especially when I thought some of them are minor and not worthing paying attention to. His feedback helped me write cleaner, better-scoped code. This project has helped me grow as a software engineer in ways I didn’t fully anticipate, but I've enjoyed it so so much.


You can explore the project here:  
https://github.com/p2plabsxyz/peersky-browser
