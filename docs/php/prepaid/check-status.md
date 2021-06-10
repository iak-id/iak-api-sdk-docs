# Check Status
API for checking your prepaid transaction status

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| refId | Your order number / reference ID | Yes | - |

Code Example
```php
$iakPrepaid = new IAKPrepaid();
echo $iakPrepaid->checkStatus([
    'refId' => '123'
]);
```
Response Example
```php
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'ref_id' => '123',
        'status' => 1,
        'product_code' => 'htelkomsel10000',
        'customer_id' => '081357922222',
        'price' => 10850,
        'message' => 'SUCCESS',
        'balance' => '99989150',
        'tr_id' => 1,
        'rc' => '00',
        'sn' => '123456789'
    ]
]
```