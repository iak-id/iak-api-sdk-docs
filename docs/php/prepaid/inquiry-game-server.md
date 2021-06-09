# Inquiry Game Server
API for generating game server list

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| gameCode | Game Code. See [here](https://api.iak.id/docs/reference/docs/prepaid/game-format.md) for game code list | Yes | - |

Code Example
```php
$iakPrepaid = new IAKPrepaid();
echo $iakPrepaid->inquiryGameServer([
    'gameCode' => '142'
]);
```
Response Example
```php
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'servers' => [
            [
                'name' => 'Test 1',
                'value' => '90001'
            ],
            [
                'name' => 'Test 2',
                'value' => '90002'
            ]
        ],
        'status' => 1,
        'message' => 'SUCCESS',
        'rc' => '00'
    ]
]
```