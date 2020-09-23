---
title: Open Market Protocol (OMP)
subtitle: Particl's Open Marketplace is based on the Open Market Protocol developed by Particl developer Kewde
slug: open-market-protocol
weight: 10
tags:
  - market
  - OMP
---

{{< toc >}}

It is a standardized and open format containing most of the economic interactions of an online marketplace. The [OMP is available as an open-source protocol](https://github.com/particl/omp-lib) on Particl's Github page and is licensed under the terms of the [MIT license](https://opensource.org/licenses/MIT).

{{< hint info >}}
Read **[Open Market Protocol documentation](https://kewde.gitbooks.io/protocol/content/)** for in-depth info.
{{< /hint >}}


## Design

The Open Market Protocol is divided into two distinct formats.

  * **Public listing format** – contains all the necessary data related to a certain item or service listed for sale. This includes the title, description, images, payment destination, and other similar information.
  * **Private message format** – contains all the data that must remain private. It includes the transaction information, the conversations between the seller and the buyer, and the buyer's address.

> The protocol has few virtues in mind: extensibility and privacy.


## Extensibility

Technology moves at an exponential rate. **The very few protocols that survive the test of time are all designed with extensibility in mind.** A protocol looking to be relevant on a long enough timeline should be both robust and flexible enough to allow any developer to expand it. The development of both decentralized storage networks (DHTs, BitTorrent, IPFS) and blockchain solutions is still young. Since there aren't any clear “winners” that meet all criteria, nor may there ever be, the protocol must accommodate for it.

## Privacy

**Privacy is also an important cornerstone of the OMP.** The protocol specifies a format for private messages that buyers and sellers must use to communicate. We strongly recommend that these messages be exchanged over end-to-end encrypted communication channels. Recent revelations and academic papers have proven beyond a doubt that there are many active threats to our digital privacy and security.

Additionally, blockchains are open public books that are full of sensitive information for passive attackers to abuse. This was of great concern when designing this protocol as it puts users at risk.

## Portability

The online e-commerce industry is a fragmented space. A few big companies such as Amazon and eBay have established a dominant position in the market. A tremendous amount of small online stores are also not to be neglected. There are a plethora of software applications to set up online shops, but almost none of them are designed for interoperability.

**One of the frustrations online merchants suffer is the lack of portability of their inventory data between different online marketplaces.** The more markets products are available on, the greater their exposure and thus, the greater their potential revenue streams. Yet, importing the inventory data into another application or website remains a cumbersome process. This is often done on purpose to prevent vendors from using competing platforms. Up until now, vendors are limited to either importing CSV files (which have many limitations) or using third-party software that manages many marketplaces.

The lack of inventory portability by large enterprises is deliberate. It is a strategy to prevent vendors from offering their goods on competing platforms. Moving large amounts of inventory data to a competitor is a painstaking process that restricts vendor's economic potential.

**The OMP allows for full inventory data portability**, but it doesn't stop there. It also lets vendors easily assign images as well as payment and shipping details to specific listings. Transferring data to other marketplaces that follow the OMP specification becomes very straightforward.

The current rise of blockchain technology has given programmers a toolset to interact with money in a way that wasn't possible before. The OMP payment formats operate with the Bitcoin blockchain and any derivatives. It also allows merchants to accept a multitude of virtual currencies on a per item basis.

A unified protocol is a step in the right direction. It fosters a more open and free e-commerce experience where portability, not fragmentation, is glorified.