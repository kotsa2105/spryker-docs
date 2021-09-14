---
title: PayOne - Authorization and Preauthorization Capture Flows
description: Payone module makes it possible for a project to choose which Payone flow it wants to implement- authorize or preauthorize + capture.
originalLink: https://documentation.spryker.com/v3/docs/payone-authorization-and-preauthorization-capture-flows
originalArticleId: 9afd62e3-50d7-49c8-9942-06e15a7c51b1
redirect_from:
  - /v3/docs/payone-authorization-and-preauthorization-capture-flows
  - /v3/docs/en/payone-authorization-and-preauthorization-capture-flows
---

Payone module makes it possible for a project to choose which Payone flow it wants to implement: authorize or preauthorize + capture.

## Authorization Example State Machine:
![Click Me](https://spryker.s3.eu-central-1.amazonaws.com/docs/Technology+Partners/Payment+Partners/BS+Payone/payone-authorization-flow-example.png) 

Authorization state machine example xml can be found in `vendor/<payone_module_folder>/src/config/Zed/Oms/PayoneInvoice.xml`

### Commands and Conditions Used in Authorization Flow:
 Commands:
  - `src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Command/AuthorizeCommandPlugin.php`

Conditions:
  - `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Condition/AuthorizationIsApprovedConditionPlugin.php`
  - `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Condition/AuthorizationIsErrorConditionPlugin.php`
  - `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Condition/AuthorizationIsRedirectConditionPlugin.php`

## Preauthorization-Capture Example State Machine:
![Click Me](https://spryker.s3.eu-central-1.amazonaws.com/docs/Technology+Partners/Payment+Partners/BS+Payone/payone-preauthorization-capture-flow-example.png) 

Preauthorization-capture state machine example XML can be found in `vendor/<payone_module_folder>/config/Zed/Oms/DirectDebit.xml`

### Commands and Conditions Used in Preauthorization-Capture Flow:
Commands:
  * `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Command/PreAuthorizeCommandPlugin.php`
  * `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Command/CaptureCommandPlugin.php`
  * `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Command/PreAuthorizaWithSettlementCommandPlugin.php`

Conditions:
  * `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Condition/PreAuthorizationIsApprovedConditionPlugin.php`
  * `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Condition/PreAuthorizationIsErrorConditionPlugin.php`
  * `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Condition/PreAuthorizationIsRedirectConditionPlugin.php`
  * `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Condition/CaptureIsApprovedConditionPlugin.php`
  * `vendor/<payone_module_folder>/src/SprykerEco/Zed/Payone/Communication/Plugin/Oms/Condition/CaptureIsErrorConditionPlugin.php`