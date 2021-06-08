# Postpaid Payment
Postpaid service to pay your customer's postpaid transaction. Unlike postpaid inquiry services, there are no difference between postpaid products on how to do payment transaction.

## Available fields
| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| trId | Transaction ID you get form inquiry success response | Yes | - |

## Code request example
```js
const { IAKPostpaid } = require('@iak-id/iak-api-server-js');

new IAKPostpaid().payment({ 
  trId: 9922721
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
    tr_id: 9922721,
    code: 'BPJS',
    datetime: '20210604123833',
    hp: '8801234560001',
    tr_name: 'VERGIE',
    period: '02',
    nominal: 50000,
    admin: 2500,
    response_code: '00',
    message: 'PAYMENT SUCCESS',
    price: 52500,
    selling_price: 51350,
    balance: 98799110,
    noref: '148732328035714773',
    ref_id: 'TPhgBfgIU4',
    desc: {
      kode_cabang: '0901',
      nama_cabang: 'JAKARTA PUSAT',
      sisa_pembayaran: '0',
      jumlah_peserta: '2'
    }
  }
}
```