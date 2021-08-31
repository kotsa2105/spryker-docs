---
title: Migration Guide - StockGui
description: Use the guide to learn how to update the StockGui module to a newer version.
originalLink: https://documentation.spryker.com/v5/docs/mg-stockgui
originalArticleId: 79e2b697-975e-45aa-a38a-0f6c63cd368b
redirect_from:
  - /v5/docs/mg-stockgui
  - /v5/docs/en/mg-stockgui
---

## Upgrading from Version 1.* to Version 2.0.0

In this new version of the **StockGui** module, we have added support of the warehouse per store. You can find more details about the changes on the [StockGui module](https://github.com/spryker/stock-gui/releases) release page.

**To upgrade to the new version of the module, do the following:**

1. Follow the steps in the individual migration guide for the **Stock** module. For more information, see [Migration Guide - Stock](/docs/scos/dev/migration-and-integration/202005.0/module-migration-guides/migration-guide-stock.html#upgrading-from-version-7---to-version-8-0-0). 
2. Upgrade the **StockGui** module to the new version:

```bash
composer require spryker/stock-gui:"^2.0.0" --update-with-dependencies
```

3. Generate the transfer objects:

```bash
console transfer:generate
```

4. Register the following form plugins:

| Plugin | Specification | Prerequisites | Namespace |
| --- | --- | --- | --- |
| `StoreRelationToggleFormTypePlugin` | Represents a store relation toggle form based on stores registered in the system. | None | `Spryker\Zed\Store\Communication\Plugin\Form` |

src/Pyz/Zed/StockGui/StockGuiDependencyProvider.php

```php
<?php
 
namespace Pyz\Zed\StockGui;
 
use Spryker\Zed\Kernel\Communication\Form\FormTypeInterface;
use Spryker\Zed\StockGui\StockGuiDependencyProvider as SprykerStockGuiDependencyProvider;
use Spryker\Zed\Store\Communication\Plugin\Form\StoreRelationToggleFormTypePlugin;
 
class StockGuiDependencyProvider extends SprykerStockGuiDependencyProvider
{
    /**
     * @return \Spryker\Zed\Kernel\Communication\Form\FormTypeInterface
     */
    protected function getStoreRelationFormTypePlugin(): FormTypeInterface
    {
        return new StoreRelationToggleFormTypePlugin();
    }
}
```

*Estimated migration time: 5 min*