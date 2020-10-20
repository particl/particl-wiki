---
title: Particl Insight
subtitle: Insight API as a part of Particl Block Explorer
slug:
weight: 2
tags:
  - API
---

{{< hint info >}}
**This API also supports testnet data**,\
just replace the url with https://explorer-testnet.particl.io
{{< /hint >}}

{{< button href="https://github.com/particl/particl-insight-api/blob/master/README.md#api-http-endpoints" >}}API Docs{{< /button >}}
{{< button href="https://explorer.particl.io" >}}Block Explorer{{< /button >}}

{{< toc >}}


## Example API calls

This is a non-exhaustive list of API example usage. [See official API docs](https://github.com/particl/particl-insight-api/blob/master/README.md#api-http-endpoints) for complete list.

### Blockchain status

Get current blockchain data (block height, supply, difficulty(...)):

https://explorer.particl.io/particl-insight-api/status

```json
{
  "info": {
    "version": 18010001,
    "protocolversion": 90009,
    "blocks": 502427,
    "moneysupply": 9403349.49981462,
    "timeoffset": 0,
    "connections": 44,
    "difficulty": 957991.7980531633,
    "relayfee": 0.00001,
    "network": "main"
  }
}
```

### Latest blocks

Gets latest blocks info (height, block size, hash, time, number of transactions(...)):

https://explorer.particl.io/particl-insight-api/blocks

```json
{
  "blocks": [
    {
      "height": 502432,
      "size": 485,
      "hash": "abf0c4e5463eacc37fd92c25513d555662e8131179d047386117e9614e04d770",
      "time": 1565024048,
      "txlength": 1,
      "poolInfo": {}
    },
    {
      "height": 502431,
      "size": 396,
      "hash": "ea666585de591f0ce0df87742491a2c997109c1697089ee3b8617185031991a6",
      "time": 1565023984,
      "txlength": 1,
      "poolInfo": {}
    },
```

### Block info

Get info for `blockId` (block `abf0c4e5463eacc37fd92c25513d555662e8131179d047386117e9614e04d770` in this example):

https://explorer.particl.io/particl-insight-api/block/abf0c4e5463eacc37fd92c25513d555662e8131179d047386117e9614e04d770

```json
{
  "hash": "abf0c4e5463eacc37fd92c25513d555662e8131179d047386117e9614e04d770",
  "size": 485,
  "height": 502432,
  "version": 160,
  "merkleroot": "52fcaac3582cffb1ee5c5617a67cd6fbf11aa2b0cb600f74f0c86dc0dcd55c28",
  "witnessmerkleroot": "5551393a854ddcdd544eb60ff1960a04261323bb6ae6495bbaa0eda40626cbc5",
  "tx": [
    "52fcaac3582cffb1ee5c5617a67cd6fbf11aa2b0cb600f74f0c86dc0dcd55c28"
  ],
  "time": 1565024048,
  "nonce": 0,
  "bits": "1a1a9131",
  "difficulty": 631492.55820872,
  "chainwork": "000000000000000000000000000000000000000000000060f0bbd6bf421ba693",
  "confirmations": 10,
  "previousblockhash": "ea666585de591f0ce0df87742491a2c997109c1697089ee3b8617185031991a6",
  "nextblockhash": "6868f3c3804cbfb3aecbf3853b0df32342e00c9dac1a1495c00ea5e399fd3d34",
  "reward": 0,
  "isMainChain": true,
  "poolInfo": {}
}
```

### Transaction info

Get info for `txId` (`52fcaac3582cffb1ee5c5617a67cd6fbf11aa2b0cb600f74f0c86dc0dcd55c28` in this example):

https://explorer.particl.io/particl-insight-api/tx/52fcaac3582cffb1ee5c5617a67cd6fbf11aa2b0cb600f74f0c86dc0dcd55c28

```json
{
  "txid": "52fcaac3582cffb1ee5c5617a67cd6fbf11aa2b0cb600f74f0c86dc0dcd55c28",
  "version": 672,
  "locktime": 0,
  "isCoinStake": true,
  "vin": [
    {
      "txid": "e82a61313b38a2127dcb000e35f5e102107820eb72b9a3bec8422dbceaf6c60b",
      "vout": 1,
      (...)
    }
  ],
  "vout": [
    {
      "value": "0.00000000",
      "n": 0,
      "scriptPubKey": {
        "hex": "",
        "asm": ""
      },
      "type": "data",
      "spentTxId": null,
      "spentIndex": "",
      "spentHeight": null,
      "data": "a0aa070007c0a19c8a0209aa86030affffff1e",
      "v": [
        {
          "name": "height",
          "value": 502432
        },
        {
          "name": "foundation-fund",
          "value": 5.58305472
        },
        {
          "name": "unknown",
          "value": 9
        }
      ]
    },
    {
      "value": "1563.45846427",
      "n": 1,
      "scriptPubKey": {
        "hex": "b86376a91425a6e814154da2f5e4570100318293c91276d07788ac67a91492342ed9db0c6090d81d8aff95f014f693784b888768",
        "asm": "OP_ISCOINSTAKE OP_IF OP_DUP OP_HASH160 25a6e814154da2f5e4570100318293c91276d077 OP_EQUALVERIFY OP_CHECKSIG OP_ELSE OP_HASH160 92342ed9db0c6090d81d8aff95f014f693784b88 OP_EQUAL OP_ENDIF",
        "addresses": [
          "RNcFFGBNdbWKWG6p4FMewSzJfxjJ4DXCPr"
        ],
        "type": "scripthash"
      (...)
    }
  ],
  "blockhash": "abf0c4e5463eacc37fd92c25513d555662e8131179d047386117e9614e04d770",
  "blockheight": 502432,
  "confirmations": 10,
  "time": 1565024048,
  "blocktime": 1565024048,
  "valueOut": 3126.91692855,
  "size": 301,
  "valueIn": 3125.95083064,
  "fees": -0.96609791
}
```