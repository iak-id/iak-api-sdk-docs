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
$iakPostpaid = new IAKPostpaid();
echo $iakPostpaid->inquiry([
    'code' => 'BPJS',
    'hp' => '8801234560001',
    'refId' => '123',
    'month' => 2
]);
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