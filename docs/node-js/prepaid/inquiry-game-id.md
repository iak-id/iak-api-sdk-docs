# Inquiry Game ID
Prepaid service to check whether your customer game id is existed or not. You can see the list of the game code and customer game id format in this [link](https://api.iak.id/docs/reference/docs/prepaid/game-format.md#inquiry-game-id).

## Available fields
| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| customerId | Customer ID. See [here](https://api.iak.id/docs/reference/docs/prepaid/game-format.md) for customer ID format | Yes | - |
| gameCode | Game Code. See [here](https://api.iak.id/docs/reference/docs/prepaid/game-format.md) for game code list | Yes | - |

## Code request example
```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().inquiryGameId({
  customerId: '156378300|8483',
  gameCode: '103',  
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
    username: 'budi', 
    status: 1, 
    message: 'SUCCESS', 
    rc: '00' 
  }
}
```