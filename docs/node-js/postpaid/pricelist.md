# Price List
Postpaid service to see your postpaid products' price list. You can see the list of the product type on this [link](https://api.iak.id/docs/reference/docs/postpaid/core/price-list.md).

## Available fields
| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| type | Product type. See [here](https://api.iak.id/docs/reference/docs/postpaid/core/price-list.md) for product type list | No | - |
| province | 34 Provinces in Indonesia (Only for PDAM type) | No | - |
| status | Product Status. 'all', 'active', 'non active' | No | all |

## Code request example

### All products
```js
const { IAKPostpaid } = require('@iak-id/iak-api-server-js');

new IAKPostpaid().pricelist().then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

### BPJS products
```js
const { IAKPostpaid } = require('@iak-id/iak-api-server-js');

new IAKPostpaid().pricelist({ 
  type: 'bpjs' 
}).then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

### PDAM jakarta products
```js
const { IAKPostpaid } = require('@iak-id/iak-api-server-js');

new IAKPostpaid().pricelist({ 
  type: 'pdam', 
  province: 'jakarta'
}).then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

### Only active PDAM products
```js
const { IAKPostpaid } = require('@iak-id/iak-api-server-js');

new IAKPostpaid().pricelist({ 
  type: 'pdam', 
  status: 'active'
}).then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

## Success response example
```js
/*PDAM jakarta products*/
{
  status: 'success',
  code: 200,
  data: { 
    pasca: [
      {
        code: 'AETRA',
        name: 'AETRA',
        status: 1,
        fee: 2500,
        komisi: 700,
        type: 'pdam',
        province: 'Jakarta'
      },
      {
        code: 'PALYJA',
        name: 'PALYJA JAKARTA',
        status: 1,
        fee: 2500,
        komisi: 700,
        type: 'pdam',
        province: 'Jakarta'
      },
    ], 
    message: 'SUCCESS', 
    rc: '00' 
  }
}
```