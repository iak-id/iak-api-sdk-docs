# Postpaid Download Receipt
Postpaid service to get your customer's postpaid transaction receipt.

## Available fields
| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| trId | Transaction ID | Yes | - |

## Code request example
```js
const { IAKPostpaid } = require('@iak-id/iak-api-server-js');

new IAKPostpaid().downloadReceipt({ 
  trId: '9922721' 
}).then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

## Success response of BPJS product (from previous BPJS inquiry)
```js
{
  status: 'success',
  code: 200,
  data: {
    'HEADER': 'STRUK PEMBAYARAN BPJS Kesehatan',
    'NO REFERENSI': '148732328035714773',
    'TANGGAL': '2021-06-04 12:38:33',
    'NO. RESI': '148732328035714773',
    'NAMA PRODUK': 'BPJS Kesehatan',
    'JUMLAH PESERTA': '2 ORANG',
    'SISA SBLMNYA': 'Rp 0',
    'PERIODE': '2 BULAN',
    'ID PELANGGAN': '8801234560001',
    'NAMA': 'VERGIE',
    'JUMLAH TAGIHAN': 'Rp 50.000',
    'ADMIN': 'Rp 2.500'
  }
}
```