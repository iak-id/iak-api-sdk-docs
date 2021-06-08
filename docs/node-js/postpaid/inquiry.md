# Postpaid Inquiry
Postpaid service to inquire your postpaid transaction. To see the complete details of inquiring your postpaid transaction, see our [API Documentation](https://api.iak.id/docs/reference/docs/postpaid/flow.md) on the Core API section on the Postpaid Section.

## Available fields
| Field Name | Description | Mandatory | Default Value |
|---|---|---|---|
| code | Product code. See [here](https://iak.id/webapp/pricelist) or Pricelist API for product code list | Yes | - |
| hp | Customer number | Yes | - |
| refId | Your order number / reference ID **(Must Unique)** | Yes | - |
| month | Number of month you're willing to pay **(Required for BPJS type)** | No | - |

## Code request example
```js
const { IAKPostpaid } = require('@iak-id/iak-api-server-js');

/*PDAM Jakarta products*/
const inquiryRequest = {
  code: 'AETRA',
  hp: '10202001',
  refId: 'TPhgBfgIU4',
};

/*BPJS*/
const inquiryRequest = {
  code: 'BPJS',
  hp: '8801234560001',
  refId: 'TPhgBfgIU4',
  month: '2',
};

/*E-Samsat Jawa Barat products*/
const inquiryRequest = {
  code: 'ESAMSAT.JABAR',
  hp: '9658548523568701',
  refId: 'TPhgBfgIU4',
  nomorIdentitas: '0212502110170100',
};

new IAKPostpaid().inquiry(inquiryRequest).then((response) => {
  console.log(response);
}).catch((error) => {
  console.log(error);
});
```

## Success response example of BPJS product
```js
{
  status: 'success',
  code: 200,
  data: {
    tr_id: 9922721,
    code: 'BPJS',
    hp: '8801234560001',
    tr_name: 'VERGIE',
    period: '02',
    nominal: 50000,
    admin: 2500,
    ref_id: 'TPhgBfgIU4',
    response_code: '00',
    message: 'INQUIRY SUCCESS',
    price: 52500,
    selling_price: 51350,
    desc: {
      kode_cabang: '0901',
      nama_cabang: 'JAKARTA PUSAT',
      sisa_pembayaran: '0',
      jumlah_peserta: '2'
    }
  }
}

```