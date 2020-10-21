---
title: Particl CLI
subtitle: Command-line client for advanced users
slug:
weight: 6
tags:
  - Particl CLI
aliases:
  - /tutorial/particl-cli/start
---

{{< toc >}}

{{< image class="side-thumb" src="particl-cli.png" alt="Preview of Particl CLI" >}}

## About Particl CLI

Particl-cli offers all the essential features, but doesn't include all the advanced bells and whistles of Particl graphical clients.

Controlled via command line interface, **Particl-cli is usually used on remote machines and computers without monitors**, e.g. servers and less powerful devices like Raspberry Pi (which make great [dedicated staking devices](/learn/staking/dedicated-devices/)!).


{{< button href="https://particl.io/downloads" class="primary" >}}Download Particl-cli{{< /button >}}
{{< button href="https://github.com/particl/particl-core/issues" >}}Report bugs{{< /button >}}

{{< hint info >}}
Also check out **[Partyman staking utility](/learn/staking/partyman/) which is a great tool to manage your staking node with ease** – it's beginner-friendly and automates many of the tedious tasks related to maintenance of your node!
{{< /hint >}}


## Features

[Browse & compare Particl-cli's features](learn:wallets:#comparison) with other available wallets.


## Getting started

### Installation

  1. **Download** [latest release](https://particl.io/downloads) latest release
  2. {{< label primary >}}Recommended{{< /label >}} Verify the downloaded archive (to make sure you haven't downloaded bad client, e.g. infected with malware)
  3. Launch the client – see [Usage](#usage) below
  4. **Backup your wallet** – see [Backup & Restore wallet](/tutorial/security/backup-restore-wallet/) guide


### Backup & Restore

Read our dedicated guide on [how to properly and securely back-up (and restore)](/tutorial/security/backup-restore-wallet/) your Particl wallet.


## Usage

Everything is executed in particl-cli directory `particl/bin/` by default.

**Before you can enter any commands, you need Particld (daemon) to run:**

    $ ./particld -daemon

### Basic commands

Next, you can enter commands you need.

{{< hint warning >}}
Beware as every command starts with `./particl-cli <command>` (and NOT `./particld <command>`)
{{< /hint >}}

- `stop` – stop the daemon
- `help` – lists all available commands

{{< hint info >}}
If you see `Error: couldn't connect to server: unknown (code -1)`, you probably haven't started `./particld`.\
You cannot run `./particld` in parallel with [Particl Core](tutorial:particl-core:) wallet.
{{< /hint >}}

### Informative

- `getinfo` –  general info about your wallet (version, balance, staking balance, network data etc.)
- `getwalletinfo` –  view balances (total, staking, immature), wallet (un)locked status etc.
- `getbalance` –  shows your total balance only
- `listtransactions` –  lists latest transactions
- `getnetworkinfo` –  about your connection to the network
- `getpeerinfo` –  info about peer connections
- `getstakinginfo` –  staking status & stats

### Actions

- `getnewaddress` –  returns your new address
- `listaddressgroupings` –  lists all used addresses (with balances)
- `listreceivedbyaddress 0 true` –  returns addresses with zero balance
- `liststealthaddresses` –  lists stealth (private) addresses
- `sendtoaddress <receiver> <amount> <comment> <comment-to> <narration>` – sending (public) PART coins

#### Confidential Transactions (Blind)

- `sendparttoblind <stealth address> <amount>` – convert public PART to blinded PART coins
- `sendblindtoblind <stealth address> <amount>` – sending blinded PART coins (transactions with hidden TX amount)
- `sendblindtopart <stealth address> <amount>` – converting blind PART coins back to public PART coins

### Wallet unlocking

#### With enhanced privacy

The RPC command-line client gained a new argument, `-stdin` to read extra arguments from standard input, one per line until EOF (`Ctrl-D`). For example:

```
$ ./particl-cli -stdin   # then press [Enter]
walletpassphrase         # then press [Enter]
"<passphrase>"           # then press [Enter]
<timeout>                # then press [Enter]
true                     # then press [Ctrl-D] here to end input
```

#### Standard unlocking

Unlock wallet (optionally for staking only) for `timeout` seconds:

    $ ./particl-cli walletpassphrase <passphrase> <timeout> [stakingonly]

e.g. `walletpassphrase “<my long pass>” 0 true` – unlocks the wallet forever (until locked manually or restarted) for staking only

- long password containing spaces should be “in quotes”
- `0` = unlocked forever; 10 = for 10 seconds and so on
- `true` in the end toggles “for staking only”; if you want your wallet completely unlocked (for sending transactions etc.) you can leave it out