# Getting Started

## Getting started

You can use this snippet code to use our check balance service on prepaid API to get started use our SDK.

```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

const credential = {
  userHp: 'your-username',
  stage: 'sandbox-or-production',
  apiKey: 'your-api-key-depending-on-stage'
};

new IAKPrepaid(credential).checkBalance().then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

---

## Set your credential

Before using this SDK, you must set your credential first, so you can access the functionality of the SDK.

There are two ways to set your credential.

1. Use your environment variable (highly recommended for security issues)
```
IAK_STAGE=sandbox-or-production
IAK_USER_HP=your-username
IAK_SANDBOX_API_KEY=your-api-development-key
IAK_PRODUCTION_API_KEY=your-api-production-key
```

2. Put it manually when constructing the class directly at your source code
```js
{
  userHp: 'your-username',
  stage: 'sandbox-or-production',
  apiKey: 'your-api-key-depending-on-stage'
}
```

---

## Instantiate IAK class

After setting your credential, you can construct your class depending on service you want to use.
```js
const { IAKPrepaid, IAKPostpaid } = require('@iak-id/iak-api-server-js');

/*if you set your credential first on environment variable*/
const iakPrepaid = new IAKPrepaid();
const iakPostpaid = new IAKPostpaid();

/*if you want to put it manually*/
const credential = {
  userHp: 'your-username',
  stage: 'sandbox-or-production',
  apiKey: 'your-api-key-depending-on-stage'
};

const iakPrepaid = new IAKPrepaid(credential);
const iakPostpaid = new IAKPostpaid(credential);
```

Then, you can call the functions in the IAKPrepaid or IAKPostpaid in these ways depending on your code style.

```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

const iakPrepaid = new IAKPrepaid();
const checkBalanceResult = iakPrepaid.checkBalance();
const checkStatusResult = iakPrepaid.checkStatus(params);

/*or*/

const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

const checkBalanceResult = new IAKPrepaid().checkBalance();
const checkStatusResult = new IAKPrepaid().checkStatus(params);
```

---

## Async call

You have to use async call to use this SDK properly, these are some ways to do it.

1. Promise
```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

new IAKPrepaid().checkBalance().then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```  

2. Async/Await

```js
const { IAKPrepaid } = require('@iak-id/iak-api-server-js');

(async () => {
  try {
    const checkBalanceResult = await new IAKPrepaid().checkBalance();
    console.log(checkBalanceResult);
  } catch (error) {
    console.log(error);
  }
})();
```