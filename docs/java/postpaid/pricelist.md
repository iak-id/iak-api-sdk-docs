# Price List
API for generating postpaid products' price list

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| type | Product type. See [here](https://api.iak.id/docs/reference/docs/postpaid/core/price-list.md) for product type list | No | - |
| province | 34 Provinces in Indonesia (Only for PDAM type) | No | - |
| status | Product Status. "all", "active", "non active" | No | all |

### Code Example

Code Example without parameter
```java
$iakPostpaid = new IAKPostpaid();
echo $iakPostpaid->pricelist();
```

Code Example with type parameter
```java
$iakPostpaid = new IAKPostpaid();
echo $iakPostpaid->pricelist([
    'type' => 'pdam'
]);
```

Code Example with type and status parameter
```java
$iakPostpaid = new IAKPostpaid();
echo $iakPostpaid->pricelist([
    'type' => 'pdam',
    'status' => 'all'
]);
```

Response Example
```java
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'pasca' => [
            [
                'code' => 'AETRA',
                'name' => 'AETRA',
                'status' => 1,
                'fee' => 2500,
                'komisi' => 700,
                'type' => 'pdam'
            ]
        ]
    ]
]
```