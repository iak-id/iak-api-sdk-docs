# Check Status
Prepaid service to check your transaction status. You must use the same refId you used to top up to see the transaction status.

## Available fields
| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| refId | Your order number / reference ID **(Must Unique)** | Yes | - |

## Code request example
```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().checkStatus({
  refId: '1IEUV4FCGi',
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