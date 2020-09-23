---
title: Data Storage Network (DSN)
subtitle: Data Storage Networks are used on Particl to store any data (i.e. marketplace-related data such as images) off-chain 
slug: 
weight: 7
tags:
  - market
  - scalability
  - SMSG
---

Contrary to on-chain storage, **storing data on DSN allows the platform to scale well regardless of the amount of data it uses**. This form of storage works without relying on servers and without centralizing powers into masternodes.


## About DSN

DSN is a generic term that describes a specific set of software with the purpose of storing and retrieving data on the internet. The usage of the term DSN is simply a layer of abstraction.

It is not required to know how a specific DSN works internally as long as it can store blobs of data and later retrieve them using a comparable cryptographic identifier. **Popular DSNs include BitMessage, IPFS, SMSG, HTTPs, TOR** etc.


## Implementation

The default (and for the moment, the only) DSN used on Particl is SMSG. It is a P2P BitMessage-like message mixnet that runs parallel to Particl's blockchain. It is hosted on the same nodes that run the Particl blockchain.

{{< image src="particl-smsg-dsn.png" alt="How SMSG works" >}}

A small hash of the hosted content is created and stored on the Particl blockchain when it is used to store data on a DSN. To verify the integrity of data when the client retrieves it back from the DSN, its hash is recomputed and compared with the one stored on the Particl blockchain. The data is considered trusted if the hashes match, and rejected by the platform if they don’t.

{{< hint info >}}
Read more about **[Data Storage Network on OMP](https://kewde.gitbooks.io/protocol/content/data-storage-network/overview.html)**
{{< /hint >}}