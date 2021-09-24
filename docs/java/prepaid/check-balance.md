# Check Balance
API for checking your deposit balance

Check balance function doesn't require any parameter to pass

Code Example
```java
IAK iak = new IAK();
iak.setApikey("your_key");
iak.setNohp("your_username");
iak.setStage("sandbox");

System.out.println(iak.prepaid().checkBalance());
```
Response Example
```java
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'balance' => 100000000,
        'message' => 'SUCCESS',
        'rc' => '00'
    ]
]
```