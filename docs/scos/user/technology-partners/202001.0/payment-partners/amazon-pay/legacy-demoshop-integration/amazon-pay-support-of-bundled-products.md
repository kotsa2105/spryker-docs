---
title: Amazon Pay - Support of Bundled Products
description: Amazon Pay supports the bundled products and can be configured in the Spryker shop.
originalLink: https://documentation.spryker.com/v4/docs/amazon-pay-support-bundled-products-demoshop
originalArticleId: d18ac575-5364-4db6-afb2-0d0b3558430d
redirect_from:
  - /v4/docs/amazon-pay-support-bundled-products-demoshop
  - /v4/docs/en/amazon-pay-support-bundled-products-demoshop
---

Bundled products are optional in the shop, thus support of those should be configured.

First, you have to extend `AmazonPayFactory`:

```php
<?php

namespace Pyz\Yves\AmazonPay;

use Spryker\Yves\ProductBundle\Grouper\ProductBundleGrouper;
use SprykerEco\Yves\AmazonPay\AmazonPayFactory as EcoAmazonPayFactory;

class AmazonPayFactory extends EcoAmazonPayFactory
{
 /**
 * @return \Spryker\Yves\ProductBundle\Grouper\ProductBundleGrouperInterface
 */
 public function createProductBundleGrouper()
 {
 return new ProductBundleGrouper();
 }
}
```

Second, you have to extend `AmazonPay\PaymentController`:

```php
<?php

namespace Pyz\Yves\AmazonPay\Controller;

use Generated\Shared\Transfer\QuoteTransfer;
use SprykerEco\Yves\AmazonPay\Controller\PaymentController as EcoPaymentController;

/**
 * @method \Pyz\Yves\AmazonPay\AmazonPayFactory getFactory()
 */
class PaymentController extends EcoPaymentController
{
 /**
 * @param \Generated\Shared\Transfer\QuoteTransfer $quoteTransfer
 *
 * @return \ArrayObject|\Generated\Shared\Transfer\ItemTransfer[]
 */
 protected function getCartItems(QuoteTransfer $quoteTransfer)
 {
 return $this->getFactory()->createProductBundleGrouper()->getGroupedBundleItems(
 $quoteTransfer->getItems(),
 $quoteTransfer->getBundleItems()
 );
 }
}
```