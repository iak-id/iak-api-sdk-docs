# Check Balance
API for checking your deposit balance

Check balance function doesn't require any parameter to pass

Code Example
```php
$iakPrepaid = new IAKPrepaid();
echo $iakPrepaid->checkBalance();
```
Response Example
```php
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