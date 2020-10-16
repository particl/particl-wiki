---
title: Particl Desktop
subtitle: Tips and notes for getting you up and running for Particl Desktop development in minutes 
slug:
weight: 1
tags:
  - dev
  - Particl Desktop
---

[Particl Desktop](/tutorial/wallets/particl-desktop) is Particl's flagship client/wallet for interacting with PART network, including [Particl Open Marketplace](/learn/marketplace/overview).

{{< hint info >}}
**For latest development set up info**\
check [official repo of Particl Desktop](https://github.com/particl/particl-desktop) (on `dev` branch)
{{< /hint >}}

## Contribute

[![Snyk](https://snyk.io/test/github/particl/particl-desktop/badge.svg)](https://snyk.io/test/github/particl/particl-desktop)
[![Build Status](https://travis-ci.org/particl/particl-desktop.svg?branch=master)](https://travis-ci.org/particl/particl-desktop)
[![Coverage Status](https://coveralls.io/repos/github/particl/particl-desktop/badge.svg?branch=master)](https://coveralls.io/github/particl/particl-desktop?branch=master)
[![Code Climate](https://codeclimate.com/github/particl/particl-desktop/badges/gpa.svg)](https://codeclimate.com/github/particl/particl-desktop)
[![Greenkeeper badge](https://badges.greenkeeper.io/particl/particl-desktop.svg)](https://greenkeeper.io/)

Join us in [#particl-dev:matrix.org](https://app.element.io/#/room/#particl-dev:matrix.org) on [Element](https://element.io) (formerly Riot) for more info and/or assistance.

Keep in mind that the development currently happens on a private fork of this repo. 

## Requirements

* [Node.js®](https://nodejs.org/) v10
* [git](https://git-scm.com/)
* [yarn](https://yarnpkg.com/en/)

## Installation

Clone the repo & fetch dependencies:

```bash
git clone https://github.com/particl/particl-desktop
cd particl-desktop
yarn install
```

## Development

> Note: most recent development happens on `dev` branch

In project's folder:

1. Run `ng serve` to start the dev server and keep it running
1. In another terminal window, run `yarn run start:electron:dev -testnet --devtools` to start Particl Desktop on testnet (daemon will be updated and launched automatically)
   * `-testnet` – for running on testnet (omit for running the client on mainnet)
   * `-reindex` – reindexes the blockchain (in case you're stuck)
   * `--devtools` – automatically opens Developer Tools on client launch

### Interact with particl-core daemon

You can directly interact with the daemon ran by the Electron version:

```
./particl-cli -testnet getblockchaininfo
```

## Packaging

### Windows-only requirements

Building for Windows requires the 32-bit libraries to be available:

```
sudo apt-get install gcc-multilib
sudo apt-get install g++-multilib
```

### Packaging commands

* `yarn run package:win` – Windows
* `yarn run package:mac` – macOS
* `yarn run package:linux` – Linux


## Troubleshooting

### Development issues

#### Blockchain syncing stuck

Restart the app with `-reindex` flag:

```
yarn run start:electron:dev -testnet --devtools -reindex
```

#### Marketplace fails to load

Delete marketplace `database` folder and restart app:

| OS      | path                                                       |
|---------|------------------------------------------------------------|
| Linux   | `~/.particl-market/testnet/03/`                            |
| Windows | `%APPDATA%/Particl Market/testnet/03/`                     |
| macOS   | `~/Library/Application Support/particl-market/testnet/03/` |

### Other issues

See our [Particl Wiki](/support) for most common problems or join [#particlhelp:matrix.org](https://app.element.io/#/room/#particlhelp:matrix.org) on [Element](https://element.io) for community help.
