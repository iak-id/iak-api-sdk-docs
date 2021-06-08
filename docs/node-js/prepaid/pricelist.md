# Price List
Prepaid service to see your prepaid products' price list. You see the list of the product type and operator on this [link](https://api.iak.id/docs/reference/docs/prepaid/product-type.md).

## Available fields
| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| type | Product type. See [here](https://api.iak.id/docs/reference/docs/prepaid/product-type.md) for product type list | No | - |
| operator | Operator type. See [here](https://api.iak.id/docs/reference/docs/prepaid/product-type.md) for operator type list | No | - |
| status | Product status. 'all', 'active', 'non active' | No | all |

## Code request example

### All products

```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().pricelist().then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

### Only game type products
```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().pricelist({ 
  type: 'game' 
}).then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

### Only mobile legends game products
```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().pricelist({ 
  type: 'game', 
  operator: 'mobile_legend'
}).then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

### Only active game products
```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().pricelist({ 
  type: 'game', 
  status: 'active'
}).then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

## Success response example
```js
/*Active mobile legend game products*/
{
  status: 'success',
  code: 200,
  data: {
    pricelist: [
      {
        product_code: 'hmobilelegend110',
        product_description: 'Mobile Legend',
        product_nominal: '110 Diamonds',
        product_details: '-',
        product_price: 30000,
        product_type: 'game',
        active_period: '0',
        status: 'active',
        icon_url: 'https://cdn.mobilepulsa.net/img/product/operator_list/140119035948-Moba-01.png',
      },
      {
        product_code: 'hmobilelegend1159',
        product_description: 'Mobile Legend',
        product_nominal: '1159 Diamonds',
        product_details: '-',
        product_price: 300000,
        product_type: 'game',
        active_period: '0',
        status: 'active',
        icon_url: 'https://cdn.mobilepulsa.net/img/product/operator_list/140119035948-Moba-01.png',
      },
      {
        product_code: 'hmobilelegend12',
        product_description: 'Mobile Legend',
        product_nominal: '12 Diamonds',
        product_details: '-',
        product_price: 3500,
        product_type: 'game',
        active_period: '0',
        status: 'active',
        icon_url: 'https://cdn.mobilepulsa.net/img/product/operator_list/140119035948-Moba-01.png',
      },
    ],
    rc: '00',
    message: 'SUCCESS',
  },
}
```