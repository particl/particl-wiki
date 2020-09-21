---
title: Partyman staking utility
slug: partyman
subtitle: Partyman is a CLI utility for managing your self-hosted staking nodes, like DSD or servers
weight: 3
tags:
  - staking
  - dsd
---

{{< toc >}}

## About Partyman

{{< image src="partyman-status.png" alt="Partyman displaying staking status" >}}

Partyman automates all kinds of heavy lifting related to running your own (staking) node. It's very lightweight and runs on many platforms, including ARM (for [DSD](/learn/staking/dedicated-devices/) like Raspberry Pi, Rock64 and others).

As CLI, it doesn't offer any graphical interface, but it's still very usable and user-friendly.

{{< button ref="https://github.com/dasource/partyman" class="primary" >}}
Partyman GitHub repo/download
{{< /button >}}

## Use cases

**Partyman is ideal for running your own staking node 24/7 on a [DSD](/learn/staking/dedicated-devices/).** These devices have a very low power consumption and still offer enough computing power and storage to run a Particl full node.

{{< hint info >}}
See out comprehensive and unified **[Guide for setting up Cold staking](tutorial:staking:cold-staking)** and detailed **[Guide for setting up your own node with Partyman](tutorial:staking:on-dedicated-device)**!
{{< /hint >}}

### Advantages

Once you have your DSD with Partyman set up, you can use it for [cold staking](/learn/staking#cold-staking/) with your main wallet (running on your PC or mobile). Your main wallet therefore doesn't need to be online 24/7, yet you still get your staking rewards.

**It's a step for increased convenience and, at the same time, also security.** With cold staking activated, your main wallet (PC/mobile) has only rights to spend the coins, whereas your staking node (DSD with Partyman) has only right for staking. Even in the case that your DSD would somehow got hacked, the attacker couldn't steal the coins on it.

## Features

- Automatic updates
- Download, verify and install latest `partild` (daemon)
- Update `partild` to latest version
- Create new wallets
- Configure new staking node
- Create/list multiple public keys for staking
- Show node status (connections, staking status etc.)
- Display staking stats for current month & year
- Enable/disable and auto-configure [UWF](https://wiki.ubuntu.com/UncomplicatedFirewall) firewall