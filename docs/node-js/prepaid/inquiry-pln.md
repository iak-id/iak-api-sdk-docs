# Inquiry PLN
Prepaid service to check whether the requested PLN subscriber is existed or not. You can use both customer subscriber id or customer electric meter number in the customerId property.

## Available fields
| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| customerId | Customer ID | Yes | - |

## Code request example
```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().inquiryPln({ 
  customerId: '12345678901' 
}).then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

## Success response example
```js
{
  status: 'success',
  code: 200,
  data: {
    status: '1',
    customer_id: '12345678901',
    meter_no: '548933889287',
    subscriber_id: '12345678901',
    name: 'Test PLN',
    segment_power: 'R1M /000000900',
    message: 'SUCCESS',
    rc: '00'
  }
}
```