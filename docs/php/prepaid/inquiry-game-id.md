# Inquiry Game ID
API for checking availability of an ID in a game

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| customerId | Customer ID. See [here](https://api.iak.id/docs/reference/docs/prepaid/game-format.md) for customer ID | Yes | - |
| gameCode | Game Code. See [here](https://api.iak.id/docs/reference/docs/prepaid/game-format.md) for game code list | Yes | - |

Code Example
```php
$iakPrepaid = new IAKPrepaid();
echo $iakPrepaid->inquiryGameID([
    'customerId' => '156378300|8483',
    'gameCode' => '103'
]);
```
Response Example
```php
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'username' => 'budi',
        'status' => 1,
        'message' => 'SUCCESS',
        'rc' => '00'
    ]
]
```