---
title: PayOne - Security Invoice Payment
description: Integrate security invoice payment through Payone into the Spryker-based shop.
originalLink: https://documentation.spryker.com/v6/docs/payone-security-invoice
originalArticleId: 5aec437c-61eb-43b3-bd15-960bc263edea
redirect_from:
  - /v6/docs/payone-security-invoice
  - /v6/docs/en/payone-security-invoice
---

## Front-End Integration

To adjust the frontend appearance, provide the following templates in your theme directory: `src/<project_name>/Yves/Payone/Theme/<custom_theme_name>/security_invoice.twig`

## State Machine Integration

Payone module provides a demo state machine for the Security Invoice payment method which implements Authorization flow.
To enable the demo state machine, extend the configuration with following values:

```php
<?php
 $config[SalesConstants::PAYMENT_METHOD_STATEMACHINE_MAPPING] = [
 ...
 PayoneConfig::PAYMENT_METHOD_SECURITY_INVOICE => 'PayoneSecurityInvoice',
 ];
 $config[OmsConstants::ACTIVE_PROCESSES] = [
 ...
 'PayoneSecurityInvoice',
 ];
 ```
