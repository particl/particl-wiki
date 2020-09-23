---
title: Secure Messaging (SMSG)
subtitle: The DSN used to store data off-chain is also used as the messaging protocol for the marketplace
slug: smsg
weight: 8
tags:
  - market
  - scalability
  - SMSG
---

## About SMSG

SMSG is a decentralized P2P message mixnet where all nodes store a copy of everyone's **end-to-end encrypted messages and data** for a duration of 48 hours (which can be increased for a fee).

> It is the default and most private DSN available for use on the platform.

The reference implementation is developed in C++ and incorporated into the Particl daemon. It operates parallel to Particl's network and is hosted on the same nodes running the blockchain.

{{< image src="particl-smsg-topology.png" alt="SMSG network topology" >}}

All nodes continuously attempt to decrypt every incoming message, but can only succeed if the node is able to recalculate the HMAC hash accompanying the message. If the hash check fails, then it can not be decrypted by the node, which means the message was either fraudulent, tampered with or meant for another node.


## Privacy benefits

**SMSG messages are stripped from of any metadata**, therefore it is impossible for anyone to extract information such as IP addresses, sender or receiver. The only metadata not stripped from SMSG messages are the hash, the encryption payload, and a temporary public key.

{{< hint info >}}
**Read more** about [SMSG on OMP](https://kewde.gitbooks.io/protocol/content/data-storage-network/smsg.html)
{{< /hint >}}