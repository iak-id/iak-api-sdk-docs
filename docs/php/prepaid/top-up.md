# Top Up
API for top up prepaid transaction e.g. pulsa, e-money, voucher, game voucher

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| customerId | Customer ID / phone number | Yes | - |
| refId | Your order number / reference ID (Must Unique) | Yes | - |
| productCode | Product Code. See full list [here](https://iak.id/webapp/pricelist) or in Pricelist API | Yes | - |

Code Example
```php
$iakPrepaid = new IAKPrepaid();
echo $iakPrepaid->topUp([
    'customerId' => '081357922222',
    'refId' => '123',
    'productCode' => 'htelkomsel10000'
]);
```
Response Example
```php
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'ref_id' => '123',
        'status' => 0,
        'product_code' => 'htelkomsel10000',
        'customer_id' => '081357922222',
        'price' => 10850,
        'message' => 'PROCESS',
        'balance' => '99989150',
        'tr_id' => 1,
        'rc' => '39'
    ]
]
```