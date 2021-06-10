# Error Handling
These are guides about how we handle errors in this SDK.

## Failed response code

All response that is not in this following list will be seen as error or exception, to be exact as ApiError. You can see our [Prepaid Response Code](https://api.iak.id/docs/reference/docs/prepaid/response-code.md) and [Postpaid Response Code](https://api.iak.id/docs/reference/docs/postpaid/response-code.md) to see the complete list of our response codes.

Here is the list of our success response code.
1. SUCCESS / INQUIRY SUCCESS / PAYMENT SUCCESS (rc: 00)
2. PROCESS (rc: 39)
3. PAYMENT_REQUEST_NOT_RECEIVED_YET (rc: 42)

Here is the dummy snippet of one of the failed response.
```js
ApiError: DUPLICATE REF ID
{
  status: 'failed',
  code: 400,
  data: { rc: '11', message: 'DUPLICATE REF ID', details: '' }
}
```

---

## Timeout
Timeout happens when your application can not connect to our API or our API process your request too long.

Here is the dummy snippet when timeout occurred.
```js
TimeoutError: Connection timeout. Please check your internet connection or wait for a seconds.
{
  status: 'failed',
  code: 408
}
```

---

## Missing arguments
Missing arguments happens when you failed to fulfill the request property requirement.
Please check again your parameter given to the SDK functions.

Here is the dummy snippet on price list request when we put the operator property without type property.
```js
MissingArgumentError: Field type is missing from your argument. This field is required.
  {
    status: 'failed',
    code: 400
  }
}
```

---

## Invalid parameter content type
This error happens when you failed to fulfill the request type requirement.
All the parameters on this SDK functions only accept **OBJECT** type.
So if you put parameter with type other than that, this error will be thrown.
Please check again your parameter given to the SDK functions.

Here is the dummy snippet on this error.
```js
ContentTypeError: Content or fields must be an object.
  {
    status: 'failed',
    code: 400
  }

```