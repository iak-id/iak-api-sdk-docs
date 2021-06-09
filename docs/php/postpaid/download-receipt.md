# Download Receipt
API for retrieving paid transaction's receipt details

Available fields

| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| trId | Transaction ID | Yes | - |

Code Example
```php
$iakPostpaid = new IAKPostpaid();
echo $iakPostpaid->downloadBill([
    'trId' => 1
]);
```
Response Example
```php
[
    'status' => 'success',
    'code' => 200,
    'data' => [
        'HEADER' => 'STRUK PEMBAYARAN BPJS Kesehatan',
        'NO REFERENSI' => '148732328035714773',
        'TANGGAL' => '2021-05-27 18:56:01',
        'NO. RESI' => '148732328035714773',
        'NAMA PRODUK' => 'BPJS Kesehatan',
        'JUMLAH PESERTA' => '2 ORANG',
        'SISA SBLMNYA' => 'Rp 0',
        'PERIODE' => '2 BULAN',
        'ID PELANGGAN' => '8801234560001',
        'NAMA' => 'Test',
        'JUMLAH TAGIHAN' => 'Rp 50.000',
        'ADMIN' => 'Rp 2.500'
    ]
]
```