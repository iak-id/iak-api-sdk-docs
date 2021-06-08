# Prepaid Inquiry Game Server
Prepaid service to check whether the requested game server is existed or not. You can see the list of the game code in this [link](https://api.iak.id/docs/reference/docs/prepaid/game-format.md#inquiry-game-id).

## Available fields
| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| gameCode | Game Code. See [here](https://api.iak.id/docs/reference/docs/prepaid/game-format.md) for game code list | Yes | - |

## Code request example
```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().inquiryGameServer({
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
    servers: [
      { name: 'Test 1', value: '90001' },
      { name: 'Test 2', value: '90002' }
    ],
    status: 1,
    message: 'SUCCESS',
    rc: '00'
  }
}
```