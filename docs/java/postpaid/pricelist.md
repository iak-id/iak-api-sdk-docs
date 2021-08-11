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
IAK iak = new IAK();
iak.setApikey("your_key");
iak.setNohp("your_username");
iak.setStage("sandbox");

// To show pdam products by province you can use code below
System.out.println(iak.postpaid().pricelist_postpaid("pdam", "active", "Jakarta"));

// If you want to show all pdam product you can see this code
System.out.println(iak.postpaid().pricelist_postpaid("pdam", "active", null));

// If you want to show other products you can change 'pdam' to other product
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