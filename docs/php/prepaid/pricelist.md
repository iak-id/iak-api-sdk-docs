# Price List
API for generating prepaid products' price list

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| type | Product type. See [here](https://api.iak.id/docs/reference/docs/prepaid/product-type.md) for product type list | No | - |
| operator | Operator type. See [here](https://api.iak.id/docs/reference/docs/prepaid/product-type.md) for operator type list | No | - |
| status | Product Status. "all", "active", "non active" | No | all |

### Code Example

Code Example without parameter
```php
$iakPrepaid = new IAKPrepaid();
echo $iakPrepaid->pricelist();
```

Code Example with type parameter
```php
$iakPrepaid = new IAKPrepaid();
echo $iakPrepaid->pricelist([
    'type' => 'data'
]);
```

Code Example with type and operator parameter
```php
$iakPrepaid = new IAKPrepaid();
echo $iakPrepaid->pricelist([
    'type' => 'data',
    'operator' => 'telkomsel_paket_internet'
]);
```

Response Example
```php
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        [
            'product_code' => 'alfamart100',
            'product_description' => 'Alfamart Voucher',
            'product_nominal' => 'Voucher Alfamart Rp 100.000',
            'product_details' => '-',
            'product_price' => 100000,
            'product_type' => 'voucher',
            'active_period' => '0',
            'status' => 'active',
            'icon_url' => 'http=>//cdn.mobileproduct.net/img/product/operator_list/140119034649-Alfa-01.png'
        ],
        [
            'product_code' => 'altel10',
            'product_description' => 'Malaysia Topup',
            'product_nominal' => '10',
            'product_details' => '-',
            'product_price' => 39750,
            'product_type' => 'malaysia',
            'active_period' => '0',
            'status' => 'active',
            'icon_url' => '-'
        ]
    ]
]
```