---
title: How to Buy/Sell on Open Marketplace
subtitle: Quick walkthrough of Buy-Sell flow on Particl Open Marketplace
slug: 
weight: 2
tags:
  - market
  - Particl Desktop
---

If you've already installed the Particl Open Marketplace and have it enabled on your [Particl Desktop](/tutorial/wallets/particl-desktop) client, then you're all set and ready to start buying and selling stuff for crypto without giving away your data.

{{< toc >}}

## Complete Buy flow

{{< hint info >}}
**If you haven't installed or enabled the Particl Open Marketplace** yet, then follow our [Getting started with Particl Open Marketplace](/tutorial/marketplace/intro) guide!
{{< /hint >}}

The following steps will show you how to use the Open Marketplace by going, in detail, through a complete purchase using the Open Marketplace.

At each step of the process, an [encrypted P2P network called SMSG](/learn/marketplace/smsg) makes the secure transmission of data and messages between the buyer and the seller. It is on this network that any marketplace content (i.e. listing pictures, orders, etc) is stored.

SMSG messages are shared in a peer-to-peer way between all the nodes running the marketplace. **Only the party you're transacting with will be able to decrypt your messages, orders, and any other kind of information**, and therefore be notified about orders and their updates.


### Listing stage

<lead>The {{< label info >}}Seller{{< /label >}} lists an item for sale</lead>

1. To list an item, first go to the **Sell** page of Particl Desktop
1. On the **Sell** page, you will see a list of all previously listed items. To add a new one, click on `+ Add new listing`
1. Fill the Listing's details and add pictures. Note that the first picture you add is going to be used as the thumbnail for your Listing
1. Click on `Save & Publish` and then type your encryption password to temporarily unlock your wallet. An unlocked wallet is required to publish Listings
1. Choose the duration of the Listing and click on `Confirm & Publish` – e.g. if you choose 1 week, then your Listing is going to stay up on the Open Marketplace for 7 days
1. Wait for at least one confirmation and your Listing will appear in the **Listings** page of the Particl Open Marketplace

{{< hint info >}}
**[Listing fees](/learn/marketplace/fees) are calculated based on the duration and size of your Listing**.\
In other words, the longer it stays up, and the more images/text your Listing has, the more expensive listing the item will be.
{{< /hint >}}


### Bidding stage

<lead>The {{< label primary >}}Buyer{{< /label >}} places a bid on item</lead>

During this step, the Buyer is going to place a bid (an order) and ["soft lock" twice the amount](/learn/marketplace/mad-escrow) of the item being purchased (including shipping costs). Placing a bid will most probably use more than twice the value of the purchased item, but the extra funds will be refunded after ~30 minutes. To know why, checkout [FAQ: Why is a big portion of my Anon balance getting locked after bidding on an item?](/support/faq/market#why-is-a-big-portion-of-my-anon-balance-getting-locked-after-bidding-on-an-item)

1. Go to the **Listings** page
1. Browse the Marketplace, and click on the item you want to purchase
1. On the Listing's pop-up page, verify the total amount required to [fund the escrow](/learn/marketplace/mad-escrow) and then add the item to your cart by clicking on `Add to cart`
1. To checkout, click on the cart icon at the top right section of the Particl Desktop client _or_ by going to the **Buy** page
1. Verify the content of your cart, and click on `Continue to shipping`
1. Fill your shipping information and, optionally, save your shipping profile for future purchases (this profile stays only on your computer)
1. Verify all the information is correct on the next page, and then click on `Place order` to place your bid
1. Confirm you want to place the order by clicking on `Yes, place order` on the pop-up confirmation page that appears
1. You can now see the status of your order by clicking on the `Orders` tab of the **Buy** page


### Order stage

<lead>The {{< label info >}}Seller{{< /label >}} accepts/rejects Buyer's bid</lead>

- If the seller **rejects the bid**, the soft locked funds will release back to you and the Order will be cancelled
- If the seller **accepts the bid**, the funds required for the escrow will soft lock on his side as well and the Buy flow continues

To accept/reject incoming bids from Buyers:

1. Go to the **Sell** page and click on the `Orders` tab
1. Either accept the order by clicking on `Yes, accept bid` or reject it by clicking on `Reject bid & cancel order`


### Escrow stage

<lead>The {{< label primary >}}Buyer{{< /label >}} makes payment into Escrow smart-contract</lead>

1. Go to the **Buy** page and click on the `Orders` tab to see your order
1. Click on the `Make payment` button to fund the escrow smart-contract
1. A pop-up window will appear, allowing you to send the seller contact information which may be useful for international shipping – giving out that information is entirely optional
1. Confirm your payment by clicking on `Confirm & Buy`


### Escrow stage, pt. II

<lead>The {{< label info >}}Seller{{< /label >}} makes payment into Escrow smart-contract</lead>

1. Go to the **Sell** page and click on the `Orders` tab to see your Order
1. Click on the `Complete escrow` button to fund the escrow smart-contract and complete the payment process
1. On the pop-up window that appears, confirm your payment by clicking on the `Yes, lock escrow` button


### Packaging & shipping stage

<lead>The {{< label info >}}Seller{{< /label >}} packages and ships the item to Buyer</lead>

1. Package and ship your item
1. Go to the **Sell** page and click on the `Orders` tab to see your Order
1. Click on the `Mark as shipped` button to let your customer know that you've shipped the order
1. In the pop-up window that appears, you can include the tracking number so that the customer can track the shipment online
1. To confirm shipment, click on the `Order shipped` button


### Delivered/complete stage

<lead>The {{< label primary >}}Buyer{{< /label >}} receives the item</lead>

1. Wait to receive your order – you can go to the **Buy** page and click on the `Orders` tab to see the tracking number of the Order
1. Once received, inspect the package as well as the product to make sure it is all good
1. If satisfied, go to the **Buy** page and click on the `Orders` tab
1. Mark the order as complete by clicking on the `Mark as delivered` button
1. On the pop-up window that appears, confirm the transaction as been completed satisfactorily by clicking on the `Yes, I received the order` button – **this will unlock the escrow to both parties and complete the transaction**

And that's it! You just finished buying/selling via trustless 2-party escrow on the Open Marketplace!