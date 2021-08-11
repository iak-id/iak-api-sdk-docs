# Check Status
API for checking your postpaid transaction status

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| refId | Your order number / reference ID (Must Unique) | Yes | - |

Code Example
```java
IAK iak = new IAK();
iak.setApikey("your_key");
iak.setNohp("your_username");
iak.setStage("sandbox");

System.out.println(iak.postpaid().check_status_postpaid_payment("postpaid_order_pbb"));
//System.out.println(iak.postpaid().check_status_postpaid_payment("your_ref_id"));
```
Response Example
```java
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'tr_id' => 1,
        'code' => 'PDAM',
        'datetime' => '20180803171608',
        'hp' => '08123123123',
        'tr_name' => 'Test',
        'period' => '202105,202106',
        'nominal' => 120000,
        'admin' => 7500,
        'ref_id' => '123',
        'status' => 0,
        'response_code' => '00',
        'message' => 'PAYMENT SUCCESS',
        'price' => 127500,
        'selling_price' => 126000,
        'balance' => 981230000,
        'desc' => []
    ]
]
```