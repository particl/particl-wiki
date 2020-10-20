---
title: Chainz
subtitle: Free crypto API by CryptoID's Chainz
slug:
weight: 4
tags:
  - API
---

{{< hint warning >}}
**Services provided by [cryptoid.info](https://chainz.cryptoid.info/) are free of charge.**\
Please do not abuse them.
{{< /hint >}}

{{< button href="https://chainz.cryptoid.info/api.dws" >}}API Docs{{< /button >}}
{{< button href="https://chainz.cryptoid.info/part/" >}}Chainz Particl Block Explorer{{< /button >}}

{{< toc >}}

## Example API calls

{{< hint alert >}}
**Query limit!**\
Please limit your calls to the Query API to 1 every 10 seconds.
{{< /hint >}}

This is a non-exhaustive list of API example usage. Visit [official API docs](https://chainz.cryptoid.info/api.dws) for complete and up-to-date list.

### Prices

#### In BTC

https://chainz.cryptoid.info/part/api.dws?q=ticker.btc

```
0.000210047495939782
```

#### In USD

https://chainz.cryptoid.info/part/api.dws?q=ticker.usd

```
2.51467502233282
```

### Last 10 TXs

https://chainz.cryptoid.info/part/api.dws?q=lasttxs

```json
[
  {
    "hash": "2c0e50f5837cd7605658a3ed6ac10722990cfb2910d398f06f22932ebf252d30",
    "confirmations": 8,
    "time": 1565025456,
    "total": 1695.19140209
  },
  {
    "hash": "20a994fa7b2663585c8702d49e22d6832f2106e519ae078f0425e98b02b1efce",
    "confirmations": 9,
    "time": 1565025152,
    "total": 77.28392811
  }
...
```

### Connected nodes

Lists connected nodes (to Chainz only!), grouped by version:

https://chainz.cryptoid.info/part/api.dws?q=nodes

```json
[
  {
    "subver": "/Satoshi:0.15.0.2.1/",
    "protocol": 90005,
    "nodes": [
      "[IP REDACTED]"
    ]
  },
  {
    "subver": "/Satoshi:0.15.1.0.1/",
    "protocol": 90006,
    "nodes": [
      "[IP REDACTED]"
    ]
  },
```

### PART in circulation

https://chainz.cryptoid.info/part/api.dws?q=circulating

```
9286195.54890558
```

### Block count

https://chainz.cryptoid.info/part/api.dws?q=getblockcount

```
502448
```

### Rich list

Get top 1000 addresses by balance:

https://chainz.cryptoid.info/part/api.dws?q=rich

```json
{
  "total": 9286199.41330688,
  "rich1000": [
    {
      "amount": 564994.93524035,
      "addr": "RNcFFGBNdbWKWG6p4FMewSzJfxjJ4DXCPr",
      "wallet": 7060
    },
    {
      "amount": 521634.39673855,
      "addr": "Pj6FLZgMitX7HqNaGHEbGQqpbQmEJvhTFh",
      "wallet": 5678
    },
...
```


## More info

Visit https://chainz.cryptoid.info/api.dws for complete and up-to-date list.
