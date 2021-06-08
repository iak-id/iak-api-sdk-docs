# Prepaid Top Up
Prepaid service to send a top up request. You can see [our price list](#prepaid-price-list) to see the list of product code you can use.

## Available fields
| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| customerId | Customer ID / phone number | Yes | - |
| refId | Your order number / reference ID **(Must Unique)** | Yes | - |
| productCode | Product Code. See full list [here](https://iak.id/webapp/pricelist) or in Pricelist API | Yes | - |

## Code request example
```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().topUp({
  customerId: '081357922222',
  refId: '1IEUV4FCGi',
  productCode: 'htelkomsel10000',
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
    ref_id: '1IEUV4FCGi',
    status: 0,
    product_code: 'htelkomsel10000',
    customer_id: '081357922222',
    price: 10900,
    message: 'PROCESS',
    balance: 98850460,
    tr_id: 66057,
    rc: '39'
  }
}
```