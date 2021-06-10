# Inquiry PLN / Electricity
API for checking whether PLN Prepaid Subscriber is valid or invalid

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| customerId | Customer ID | Yes | - |

Code Example
```php
$iakPrepaid = new IAKPrepaid();
echo $iakPrepaid->inquiryPLN([
    'customerId' => '12345678901'
]);
```
Response Example
```php
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