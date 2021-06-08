# Getting Started

## SDK Code Example
You can use below snippet code to use our check balance service on prepaid API to get started on our SDK.
```php
<?php

$iakPrepaid = new IAKPrepaid([
  'userHp' => 'your-username',
  'apiKey' => 'your-api-key-depending-on-stage',
  'stage' => 'sandbox-or-production'
]);

$balanceResult = $iakPrepaid->checkBalance();
echo $balanceResult;
```
---

## Set your credential
We will start things off with configuring IAK API credential which is required to use IAK API features. There are two ways to configure your API credential, pass your credential as parameter or set your initial credential in env file.

### Parameter Passing
Passing your IAK API configuration as parameters when creating an IAK instance in your project.

### Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| userHp | Your registered phone number in IAK | Yes | - |
| apiKey | Your development or production API key in IAK | Yes | - |
| Stage | "sandbox" or "production" | Yes | sandbox |

### Code Example
- Prepaid
```php
$iakPrepaid = new IAKPrepaid([
    'userHp' => '0813********',
    'apiKey' => 'e8g32*******',
    'stage' => 'sandbox'
]);
```
- Postpaid
```php
$iakPostpaid = new IAKPostpaid([
    'userHp' => '0813********',
    'apiKey' => 'e8g32*******',
    'stage' => 'sandbox'
]);
```
---

### PHP Dot Env
When creating an IAK instance, parameter passing can be ignored by configuring your IAK API credentials manually.
1. Create .env file in your root project
2. Define necessary key(s) to replace parameter field(s)
3. Available keys:
    - IAK_USERHP --> Replace userHp field
    - IAK_APIKEY_SANDBOX --> Replace apiKey field if stage is **sandbox**
    - IAK_APIKEY_PRODUCTION --> Replace apiKey field if stage is **production**
    - IAK_STAGE --> Replace stage field


### Env Example
```
IAK_USERHP=0813********
IAK_APIKEY_SANDBOX=e8g32*******
IAK_APIKEY_PRODUCTION=as342******
IAK_STAGE=sandbox
```
**Note: These keys also serve as default value if some field(s) are not available when creating an IAK instance**

### Code Example

Code example without parameter passing
```php
$iakPrepaid = new IAKPrepaid();
```

Code example with incomplete parameter
```php
$iakPostpaid = new IAKPostpaid([
    'stage' => 'production'
]);
```
In this case, **stage** value in parameter will override IAK_STAGE value in .env