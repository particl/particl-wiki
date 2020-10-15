---
title: Fixing syncing issues
subtitle: Are you having trouble synchronizing latest blocks? 
slug:
weight: 1
tags:
  - support
  - TODO
---

Particl wallets are a network-based software. **Make sure that no firewall or anti-virus software is blocking Particl from running or connecting the internet**. If in doubt, disable them for testing purposes and enable them afterwards if you have identified your problem.

## Update to latest version

Make sure you're running on [latest version](https://particl.io/downloads).

If not, update your wallet.

## Reindex blockchain

Relaunch the client with `-reindex` flag:

{{< tabs "reindex" >}}

{{< tab "Windows" >}}
### Windows

- **Particl Desktop**: FIXME
- **Particl Core**: FIXME
{{< /tab >}}

{{< tab "macOS" >}}
### macOS

- **Particl Desktop**: launch via `/particl-desktop.app/Contents/MacOS/particl-desktop -reindex` on actual Particl Desktop binary
- **Particl Core**: FIXME
{{< /tab >}}

{{< tab "Linux" >}}
### Linux

- **Particl Desktop**: launch wallet via `./particl-desktop -reindex` in app directory
- **Particl Core**: launch wallet via `./particl-qt -reindex` in app directory
{{< /tab >}}

{{< /tabs >}}
