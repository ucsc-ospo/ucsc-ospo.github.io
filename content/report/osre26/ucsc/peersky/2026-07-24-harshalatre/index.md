---
title: "Midterm blog : PeerSky Mobile"
subtitle: "Building the protocol foundation, collaborative apps, and browser experience"
summary: "A midterm update on bringing PeerSky to mobile with Bare, Hypercore, Holesail, P2PMD, and a React Native browser shell."
authors:
  - harshalatre
tags: ["osre26", "gsoc", "peersky", "p2p", "hypercore", "holesail", "react-native"]
categories: ["GSoC 2026", "PeerSky", "Open Source"]
date: 2026-07-24
lastmod: 2026-07-24
featured: true
draft: false

image:
  caption: "PeerSky Mobile"
  focal_point: "Center"
  preview_only: false
---

Hi again! I am Harshal Atre, and this is my midterm update for [PeerSky Mobile Browser](/project/osre26/ucsc/peersky) under Google Summer of Code 2026 and UC OSPO. I am working with my mentor, Akhilesh Thite, to bring PeerSky's peer-to-peer browsing and local applications to Android and iOS.

If you have not seen it yet, my [introductory blog](https://ucsc-ospo.github.io/report/osre26/ucsc/peersky/2026-05-07-harshalatre/) covers my background and the original project goals. You can also find the PeerSky Mobile source code on [GitHub](https://github.com/p2plabsxyz/peersky-mobile).

## Project Recap

PeerSky is a browser for the decentralized web. The mobile project combines React Native and Expo for the application layer, a [Bare](https://github.com/holepunchto/bare) worklet for the peer-to-peer runtime, and React Native WebView for browser rendering.

The first half of the project focused on building the protocol foundation incrementally. The order was intentional: make `hyper://` work first, integrate Holesail tunneling next, build the collaborative P2PMD application on top of both, and then turn those capabilities into a usable mobile browser.

## Progress So Far

I began by stabilizing the Expo and Bare setup so development and runtime dependencies were in the correct places ([PR #2](https://github.com/p2plabsxyz/peersky-mobile/pull/2)). This gave the project a reliable base for bundling the Bare backend across Android and iOS targets.

The first major protocol milestone was native `hyper://` support ([PR #3](https://github.com/p2plabsxyz/peersky-mobile/pull/3)). I built the communication flow between React Native and the Bare worklet using RPC, added Hyperdrive creation and fetching, and hardened URL handling against malformed input and path traversal. This made it possible to create a Hyperdrive on a phone, publish content, and open it from PeerSky Desktop.

Next, I integrated [Holesail](https://holesail.io/) for encrypted peer-to-peer TCP tunneling ([PR #4](https://github.com/p2plabsxyz/peersky-mobile/pull/4)). The mobile app can host or join a Holesail connection, report its status, and cleanly stop the session. I also added transition guards to prevent concurrent session races and restricted tunnel hosts to loopback addresses so the phone cannot accidentally become a relay into a private local network.

With Hyper and Holesail working, I moved to P2PMD, PeerSky's collaborative Markdown application. The foundation PR added room creation and joining, a local Bare HTTP service, Markdown storage, and real-time synchronization over Holesail ([PR #5](https://github.com/p2plabsxyz/peersky-mobile/pull/5)). The next iteration brought the experience much closer to PeerSky Desktop by adding a mobile Markdown editor, preview mode, Yjs-based real-time synchronization, participant presence, per-line gutter attribution, a formatting toolbar, automatic saving, Hyper publishing, and image uploads from the phone.

That work was completed in [PR #6](https://github.com/p2plabsxyz/peersky-mobile/pull/6). It required more than reproducing the UI. The mobile editor had to keep Yjs state, peer presence, image publishing, and line attribution compatible with desktop so a phone and laptop could edit the same document. The host and client paths also had to provide the same editing, preview, upload, and publishing behavior.

I then added protocol, platform, and integration coverage along with runtime documentation and CI ([PR #7](https://github.com/p2plabsxyz/peersky-mobile/pull/7)). The tests exercise Hyper URL and media handling, Holesail session validation and live tunneling, P2PMD HTTP endpoints, Yjs synchronization, peer presence, Android/iOS configuration, and Bare bundle generation. The current runtime suite contains 110 tests.

The latest stage is the mobile browser shell ([PR #8](https://github.com/p2plabsxyz/peersky-mobile/pull/8)). After researching how privacy-focused browsers such as DuckDuckGo, Firefox, Tor Browser, and Brave structure their mobile stacks, we chose React Native WebView as the practical foundation for the initial shell. It now supports address and search input, back, forward, and reload controls, and navigation across `http://`, `https://`, and `hyper://`. Hyper pages are rendered through `hypercore-fetch`, including CSS, images, scripts, audio, and streamed video assets.

The shell also includes persistent tabs with a bounded number of live WebView instances, local PeerSky applications exposed through stable `peersky://` routes, and functional settings for appearance, accessibility, data clearing, and external-app permissions. Applications such as P2PMD, Holesail, and the Hyper runtime appear from the browser home screen, while regular web and Hyper pages share the same browser controls.

## Challenges and Learnings

One of the biggest challenges has been crossing runtime boundaries. React Native owns the mobile UI, the WebView renders browser content, and Bare runs the peer-to-peer protocols. Features that look simple from the interface often require a carefully designed path across all three layers.

Hyper media playback is a good example. A desktop browser can connect its protocol handler directly to the browser engine, but a mobile WebView does not understand `hyper://` media URLs. The solution was to fetch the asset through Bare and stream it through a tightly scoped loopback proxy that supports media range requests. This allows videos to seek and play without buffering the complete file in mobile memory.

Testing Holesail also showed the difference between an emulator and a real phone. The tunnel could initialize in the emulator while hole punching still failed because of the virtual network environment. Building a release APK and testing across real devices helped separate implementation bugs from emulator limitations.

P2PMD brought a different class of problems. Host and client editors initially followed slightly different paths, which exposed synchronization and publishing edge cases. I learned to validate both roles as first-class flows and to test reconnects, concurrent edits, peer cleanup, payload limits, and mobile memory constraints rather than stopping at the happy path.

Mentor reviews have been especially valuable here. They have pushed me to think about malformed URLs, path traversal, arbitrary local-network access, races between RPC calls, unbounded uploads, stale peers, stream cleanup, and clear error reporting before considering a feature finished. The project has improved not only my understanding of peer-to-peer systems, but also how I review code for production readiness.

## What's Next

For the second half of the project, I plan to finish and refine the browser shell, continue adding meaningful browser elements, and keep the architecture ready for multiple WebView instances. I will also work on native ad and tracker blocking. On Android, this means intercepting WebView requests at the native layer; on iOS, it means using `WKContentRuleList`, with community-maintained filter sources such as EasyList and EasyPrivacy.

After that, the focus will move toward the remaining local applications and PeerChat integration, including careful handling of mobile lifecycle and background-runtime limitations. Tests and documentation will continue to be added alongside each protocol- or platform-specific feature.

## Closing Thoughts

At the midpoint, PeerSky Mobile has grown from a Bare and Expo foundation into a working peer-to-peer browser prototype. A phone can load Hyper sites, create and join Holesail tunnels, collaborate with PeerSky Desktop through P2PMD, publish Markdown and images to Hyper, stream Hyper media, and browse through a persistent multi-tab shell.

The most important lesson so far is that bringing desktop peer-to-peer behavior to mobile is not a direct port. Mobile networking, lifecycle rules, memory limits, and WebView boundaries require different solutions while preserving protocol compatibility. Working through those constraints has been challenging, but it has also been the most rewarding part of the project.

Thank you to Akhilesh for the detailed reviews and guidance, and to UC OSPO, OSRE, and Google Summer of Code for the opportunity. I am excited to continue building during the second half of the summer.
