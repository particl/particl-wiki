---
title: Coingecko
subtitle: 100% free crypto API by CoinGecko
slug:
weight: 3
tags:
  - API
aliases:
  - /dev/coingecko-api
---

Access CoinGecko data such as live pricing, trading volume, tickers, exchanges, historical data, coin info & images, developer & community stats, events, global markets, and CoinGecko Beam coins & exchanges status updates directly.

{{< button href="https://www.coingecko.com/api/documentations/v3" >}}API v3 Docs{{< /button >}}
{{< button href="https://www.coingecko.com/en/api" >}}Homepage{{< /button >}}

{{< toc >}}

## Example API calls

This is a non-exhaustive list of API example usage. Visit [official API docs](https://www.coingecko.com/api/documentations/v3) for complete and up-to-date list.

### Get current price

Simple price info for USD & EUR (comma-separated):

https://api.coingecko.com/api/v3/simple/price?ids=particl&vs_currencies=usd,eur

```json
{
  "particl": {
    "usd": 2.58,
    "eur": 2.3
  }
}
```

### Coin's current data

Get current data (name, price, market, … including exchange tickers) for a coin:

https://api.coingecko.com/api/v3/coins/particl?localization=false

(Click the link for preview, it contains a "wall of text" amount of content :)

### Historic data

Get historical data (name, price, market, stats) at a given date for a coin:

https://api.coingecko.com/api/v3/coins/particl/history?date=05-08-2019

```json
{
  "id": "particl",
  "symbol": "part",
  (...)
  "market_data": {
    "current_price": {
      (...)
      "btc": 0.00018252005023326441,
      "eur": 1.7995897007224058,
      "usd": 1.9988778193073453,
      (...)
    },
    "market_cap": {
      "btc": 1693.3579520529054,
      "eur": 16695006.341716846,
      "usd": 18543825.771095067,
      (...)
    },
    "total_volume": {
      "btc": 9.97276602445598,
      "usd": 109217.2655987682,
      (...)
    }
  },
  "community_data": {
    "facebook_likes": null,
    "twitter_followers": 19491,
    "reddit_average_posts_48h": 0.083,
    "reddit_average_comments_48h": 0.167,
    "reddit_subscribers": 2604,
    "reddit_accounts_active_48h": "1550.6"
  },
  "developer_data": {
    "forks": 41,
    "stars": 84,
    "subscribers": 28,
    "total_issues": 0,
    "closed_issues": 0,
    "pull_requests_merged": 30,
    "pull_request_contributors": 15,
    "code_additions_deletions_4_weeks": {
      "additions": 2240,
      "deletions": -2017
    },
    "commit_count_4_weeks": 269
  },
  "public_interest_stats": {
    "alexa_rank": 701745,
    "bing_matches": 34
  }
}
```

### Status updates

Get status updates for a given coin:

https://api.coingecko.com/api/v3/coins/particl/status_updates?per_page=3

```json
{
  "status_updates": [
    {
      "description": "New Particl Open Marketplace Testnet Builds Available\r\n---\r\n\r\nParticl has initiated today its last testing round before its Open Marketplace Dapp moves up onto mainnet on the 12th of August by publishing new testnet builds. This version of the marketplace includes private-by-default TXs powered by RingCT and all the bug fixes made since Particl's last testing round.\r\n\r\nClick the link below to test it out!\r\n\r\n👉 https://particl.news/new-open-marketplace-testnet-build-now-available-e35173736a4",
      "category": "software_release",
      "created_at": "2019-08-01T18:19:34.764Z",
      "user": "Cryptoguard",
      "user_title": "Lead Community Manager",
      "pin": true,
      "project": {
        "type": "Coin",
        "id": "particl",
        "name": "Particl",
        "symbol": "part",
        "image": {
          "thumb": "https://assets.coingecko.com/coins/images/839/thumb/Particl.png?1558053958",
          "small": "https://assets.coingecko.com/coins/images/839/small/Particl.png?1558053958",
          "large": "https://assets.coingecko.com/coins/images/839/large/Particl.png?1558053958"
        }
      }
    },
(...)
```

### Global cryptocurrency data

Get cryptocurrency global data:

https://api.coingecko.com/api/v3/global

```json
{
  "data": {
    "active_cryptocurrencies": 5353,
    "upcoming_icos": 30,
    "ongoing_icos": 181,
    "ended_icos": 3207,
    "markets": 414,
    "total_market_cap": {
      "btc": 26449414.03170717,
      "eth": 1338415532.0638607,
      "usd": 310335507323.30597,
      (...)
    },
    "total_volume": {
      "btc": 5631110.951722441,
      "eth": 284950220.5048951,
      "eur": 58985358273.98497,
      "usd": 66070789768.78997,
      (...)
    },
    "market_cap_percentage": {
      "btc": 67.52300151209654,
      "eth": 8.009767450191033,
      (...)
    },
    "market_cap_change_percentage_24h_usd": 5.952690470013277,
    "updated_at": 1565022135
  }
}
```

## More info

Visit https://www.coingecko.com/api/documentations/v3 for complete and up-to-date list.
