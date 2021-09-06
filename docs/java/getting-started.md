# Getting Started

## SDK Code Example

You can use below snippet code to use our check balance service on prepaid API and get our pricelist on postpaid API to get started on our SDK.

```java
IAK iak = new IAK();
iak.setApikey("your_key");
iak.setNohp("your_username");
iak.setStage("sandbox");

System.out.println(iak.prepaid().checkBalance());

```

```java
IAK iak = new IAK();
iak.setApikey("your_key");
iak.setNohp("your_username");
iak.setStage("sandbox");

System.out.println(iak.postpaid().pricelist_postpaid("pdam", "active", null));
System.out.println(iak.postpaid().pricelist_postpaid("pdam", "active", "Jakarta"));
```


---


## Set your credential

We will start things off with configuring IAK API credential which is required to use IAK API features. There are two ways to configure your API credential, pass your credential as parameter or set your initial credential in env file.

### Parameter Passing

Passing your IAK API configuration as parameters when creating an IAK instance in your project.

Available fields


| Field Name | Description                                   | Mandatory | Default Value |
| ------------ | ----------------------------------------------- | ----------- | --------------- |
| NoHp     | Your registered phone number in IAK           | Yes       | -             |
| apiKey     | Your development or production API key in IAK | Yes       | -             |
| Stage      | "sandbox" or "production"                     | Yes       | sandbox       |

### Code Example

```java
IAK iak = new IAK();
iak.setApikey("your_key");
iak.setNohp("your_username");
iak.setStage("sandbox");
```