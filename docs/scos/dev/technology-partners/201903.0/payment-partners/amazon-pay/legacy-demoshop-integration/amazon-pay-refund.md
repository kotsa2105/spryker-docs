---
title: Amazon Pay - Refund
description: This article contain information on the refund process for the Amazon Pay module in Spryker.
originalLink: https://documentation.spryker.com/v2/docs/amazon-pay-refund-demoshop
originalArticleId: d8999a0c-8b90-4cbe-b844-d037a6d66c86
redirect_from:
  - /v2/docs/amazon-pay-refund-demoshop
  - /v2/docs/en/amazon-pay-refund-demoshop
---

After the successful authorization and capture processes, the order should be closed. This blocks any modifications to an order. From this state only Refund operation is possible. The refund can be partial if more than one item is set to refund or full.

Amazon only requires the amount of money which has to be refunded, and the calculation has to be implemented on the shop's side. Spryker OS provides a module for calculating the amount to refund. Regardless of the chosen setting, the refund is always asynchronous. Once requested, an order goes to "refund pending" status and then IPN notification will notify the shop if the refund was accepted or declined.