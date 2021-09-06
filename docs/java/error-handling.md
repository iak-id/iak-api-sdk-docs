# Error Handling
If an error occured or HTTP status code from API call is **not** 200, exception will be thrown with error message included.
Below are several cases where exception might be thrown.

## Invalid Content Type
This exception will be thrown if passed parameter type is not an **array**

Error Response
```java
[
    'status' => 'failed',
    'code' => 400,
    'data' => [
        'error' => 'Content type must be array'
    ]
]
```
---

## Missing Arguements
This exception will be thrown if one or more **required** field(s) are missing in the parameter **array**

Error Response
```java
[
    'status' => 'failed',
    'code' => 400,
    'data' => [
        'error' => 'Field refId is missing'
    ]
]
```
---

## Timeout
This exception will be thrown if either your application is not able to connect to our API or our API is processing your request for too long

Error Response
```java
[
    'status' => 'failed',
    'code' => 408,
    'data' => [
        'error' => 'Connection Timeout Error. Please check your internet connection and try again'
    ]
]
```
