---
title: Heidelpay - Workflow for Errors
description: This article describes the procedure for handling errors in Heidelpay.
originalLink: https://documentation.spryker.com/v4/docs/heidelpay-error-workflow
originalArticleId: aaede83b-de7a-4f49-a759-07aac5c46f94
redirect_from:
  - /v4/docs/heidelpay-error-workflow
  - /v4/docs/en/heidelpay-error-workflow
---

From the user's perspective, there is almost no difference between successful and unsuccessful order flow.

The only exception is a redirect to the URL after the `placeOrderAction` (`/checkout/place-order`) is complete. Both URLs can be configured as follows:
```php
 $config[HeidelpayConstants::CONFIG_YVES_URL] = 'http://' . $config[ApplicationConstants::HOST_YVES];

 //url which is used in case if order was successfuly handled by Heidelpay
 $config[HeidelpayConstants::CONFIG_YVES_CHECKOUT_SUCCESS_URL] = 'http://' . $config[ApplicationConstants::HOST_YVES] . '/checkout/success';

 //url which is used in case if order was unsuccessfully handled by Heidelpay
 $config[HeidelpayConstants::CONFIG_YVES_CHECKOUT_PAYMENT_FAILED_URL] = 'http://' . $config[ApplicationConstants::HOST_YVES] . '/heidelpay/payment-failed?error_code=%s';
 ```
Data flow containing information about the Heidelpay transaction error is marked red.
![Click Me](https://cdn.document360.io/9fafa0d5-d76f-40c5-8b02-ab9515d3e879/Images/Documentation/heidelpay-error-handling-workflow.png) 