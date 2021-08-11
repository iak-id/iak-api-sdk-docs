# Inquiry Game Server
API for generating game server list

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| gameCode | Game Code. See [here](https://api.iak.id/docs/reference/docs/prepaid/game-format.md) for game code list | Yes | - |

Code Example
```java
IAK iak = new IAK();
iak.setApikey("your_key");
iak.setNohp("your_username");
iak.setStage("sandbox");

System.out.println(iak.prepaid().inquiry_gameServer("142"));
```
Response Example
```java
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