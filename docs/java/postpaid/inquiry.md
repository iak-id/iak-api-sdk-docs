# Inquiry
API for inquiry postpaid product

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| code | Product code. See [here](https://iak.id/webapp/pricelist) or Pricelist API for product code list | Yes | - |
| hp | Customer number | Yes | - |
| refId | Your order number / reference ID (Must Unique) | Yes | - |
| month | Number of month you're willing to pay (Required for BPJS type) | No | - |

Code Example
```java
IAK iak = new IAK();
iak.setApikey("your_key");
iak.setNohp("your_username");
iak.setStage("sandbox");

// If you want to inquiry BPJS product please see this code
System.out.println(iak.postpaid().inquiry_postpaid("postpaid_order01", "8801234560001", "BPJS", "2"));

// If you not to inquiry BPJS product please see this code
System.out.println(iak.postpaid().inquiry_postpaid("postpaid_order02", "0110014601", "PGAS", null));
System.out.println(iak.postpaid().inquiry_postpaid("postpaid_order03", "6391601201", "FNMEGA", null));

// If you want to inquiry E Samsat product, you must use code like this
// where '0212502110170100' is nomor_identitas (Registered identity number / KTP)
System.out.println(iak.postpaid().inquiry_postpaid_esamsat("postpaid_order_esamsat", "9658548523568701", "ESAMSAT.JABAR", "0212502110170100"));

// Then if you want to inquiry PBB product, you can use previous code (not E samsat inquiry code)
// where '329801092375999901' is tax object number
System.out.println(iak.postpaid().inquiry_postpaid("postpaid_order_pbb", "329801092375999901""PBBKOT.CIMAHI", null));

```
Response Example
```java
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'tr_id' => 1,
        'code' => 'BPJS',
        'hp' => '8801234560001',
        'tr_name' => 'Test',
        'period' => '02',
        'nominal' => 50000,
        'admin' => 2500,
        'ref_id' => '123',
        'response_code' => '00',
        'message' => 'INQUIRY SUCCESS',
        'price' => 52500,
        'selling_price' => 52300,
        'desc' => [
            'kode_cabang' => '0901',
            'nama_cabang' => 'JAKARTA PUSAT',
            'sisa_pembayaran' => '0',
            'jumlah_peserta' => '2'
        ]
    ]
]
```