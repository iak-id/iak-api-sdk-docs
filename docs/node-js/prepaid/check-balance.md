# Check Balance
Function you can use to check or see your IAK balance.

## Code request example

```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().checkBalance().then((response) => {
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
    balance: 100000000, 
    message: 'SUCCESS', 
    rc: '00' 
  }
}
```