---
title: Connections & peers
subtitle: When you don't have connections to the network
slug:
weight: 2
tags:
  - support
---

## Clear banned peers

{{< image src="particl-desktop-open-console.png" class="side-thumb" alt="Opening Console in Particl Desktop" >}}

Open Console:

- **Particl Desktop**: click on the terminal/console icon in bottom left corner
- **Particl Core**: _Help → Debug window → Console tab_

Enter `clearbanned`, press <kbd>Enter</kbd> and restart wallet.

## Find peers from scratch

Delete your `peers.dat` file in [Particl directory](/tutorial/security/backup-restore-wallet/#where-is-walletdat). This will force the app to find new connections to peers.

## Time offset error

If you see a time offset error icon, it means that your machine is either ahead of behind a few seconds compared to your peers. To fix this:

- **Enable automatic time on your OS** (this will sync and setup your time settings with a time server)