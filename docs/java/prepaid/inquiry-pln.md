# Inquiry PLN / Electricity
API for checking whether PLN Prepaid Subscriber is valid or invalid

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| customerId | Customer ID | Yes | - |

Code Example
```java
IAK iak = new IAK();
iak.setApikey("your_key");
iak.setNohp("your_username");
iak.setStage("sandbox");

System.out.println(iak.prepaid().inquiry_pln("12345678901"));
```
Response Example
```java
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'status' => 1,
        'customer_id' => '12345678901',
        'meter_no' => '548933889287',
        'subscriber_id' => '12345678901',
        'name' => 'Test PLN',
        'segment_power' => 'R1M /000000900',
        'message' => 'SUCCESS',
        'rc' => '00'
    ]
]
```