# Payment
API for paying postpaid product

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| trId | Transaction ID | Yes | - |

Code Example
```java
IAK iak = new IAK();
iak.setApikey("your_key");
iak.setNohp("your_username");
iak.setStage("sandbox");

// To pay inquiry pospaid product you can see code below
// where '9934079' is from inquiry response
System.out.println(iak.postpaid().pay_postpaid_inquiry("9934079"));
```
Response Example
```java
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'tr_id' => 1,
        'code' => 'BPJS',
        'datetime' => '20180803170750',
        'hp' => '8801234560001',
        'tr_name' => 'Test',
        'period' => '202105',
        'nominal' => 50000,
        'admin' => 2500,
        'response_code' => '00',
        'message' => 'PAYMENT SUCCESS',
        'price' => 52500,
        'selling_price' => 52300,
        'balance' => 999490800,
        'noref' => '148732328035714773',
        'ref_id' => '123',
        'desc' => [
            'kode_cabang' => '0901',
            'nama_cabang' => 'JAKARTA PUSAT',
            'sisa_pembayaran' => '0',
            'jumlah_peserta' => '2'
        ]
    ]
]
```