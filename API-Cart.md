# BURSAUKM Marketplace API
---
# _Cart API_

## Cart List Order
METHOD **POST** | [ENDPOINT](https://api.bursaukm.com/v1/order-cart) : `/v1/order-cart`
> Daftar Cart 

### Sample Data
```
{
    "userToken" : "8bde4b491892d7dac832a9807e39bfd30861c5885128bfa5fdf7f499690251c7"
}
```

### Resoponse
```
{
    "ResponseCode": "200000",
    "ResponseStatus": "Success",
    "ResponseMessage": "Data ditemukan",
    "ResponseData": {
        "draw": 1,
        "recordsTotal": 1,
        "recordsFiltered": 1,
        "sub_total": 1000000,
        "data": [
            {
                "check": "",
                "image": "20_823a3661_7637_IMG_MAIN.png",
                "title": "Mesin Pengkodean Continuous Inkjet Printer SQUID I",
                "quantity": "1",
                "price": 1000000,
                "total": 1000000,
                "id": "CRD202201190000000001",
                "company_id": "3",
                "company_name": "Pouchen",
                "stock": 95,
                "product_id": "823a3661-7637-11ec-80cb-2cea7f647529"
            }
        ]
    }
}
```
## Table Response Data
| Response Code | Status |
| ----------- | ----------- |
|200000| Data Ditemukan |
|400000| Request Method tidak sesuai |
|400001| Parameter tidak valid|
|400003| Token tidak valid|
|400999| Data tidak ditemukan|

---
## Checkout Order
METHOD **POST** | [ENDPOINT](https://api.bursaukm.com/v1/checkout) : `/v1/checkout`
> Data untuk membuat pesanan

### Sample Data
```
{
    "order": [
        {
            "pesanan" : 1,
            "items": 1,
            "subTotal": 3000000,
            "addressId":2,
            "cartId": ["CRD202201110000000003"]
        },
        {
            "pesanan" : 2,
            "items": 1,
            "subTotal": 3000000,
            "addressId":2,
            "cartId": ["CRD202201110000000002"]
        }
    ],
    "userToken" : "7451c393f7bfbee70db876dfe04f11f9eaae8bfdd4e6dee3b5d3a39dd3ca903d",
    "payment": 1
}
```

### Resoponse
```
{
    "ResponseCode": "200000",
    "ResponseStatus": "Success",
    "ResponseMessage": "Data berhasil disimpan",
    "ResponseData": ""
}
```
## Table Response Data
| Response Code | Status |
| ----------- | ----------- |
|200000| Data berhasil disimpan |
|400000| Request Method tidak sesuai |
|400001| Parameter tidak valid|
|400003| Token tidak valid|
|400005| Insert gagal|
|400006| Stok tidak cukup|
|400999| Data tidak ditemukan|

---

## Dafatr Histori Pembelian
METHOD **POST** | [ENDPOINT](https://api.bursaukm.com/v1/purchase-order) : `/v1/purchase-order`
> Data Histori Pembelian 

### Sample Data
```
{
    "userToken" : "82102c36c18bef6d24f558764d3bd4a22de7dc8ad3ff53c4c2b776fd3fc69ea0",
    "keyword": "",
    "status" : "'1','2'"
}
```
> Params Keyword : Untuk Pencarian berdasarkan Order ID. 

> Params status : untuk Pencarian berdasarkan status "'1','2'" | "'3','4'" | "'5'"
### Resoponse
```
{
    "ResponseCode": "200000",
    "ResponseStatus": "Success",
    "ResponseMessage": "Data ditemukan",
    "ResponseData": [
        {
            "check": "",
            "order_id": "ODR202201160000000003",
            "invoice_id": "INV202201160000000003",
            "company_id": "7",
            "company_name": "Indah Setara",
            "quantity": 2,
            "product_price": 3500000,
            "order_date": "2022-01-16 01:29:04",
            "order_status_id": 1,
            "order_status_name": "Belum Bayar",
            "action": "ODR202201160000000003"
        }
    ]
}
```
## Table Response Data
| Response Code | Status |
| ----------- | ----------- |
|200000| Data ditemukan |
|204001| Data tidak ditemukan|
|400000| Request Method tidak sesuai |
|400001| Parameter tidak valid|
|400003| Token tidak valid|

---

## Detail Histori Pembelian
METHOD **POST** | [ENDPOINT](https://api.bursaukm.com/v1/purchase-detail) : `/v1/purchase-detail`
> Data Detail Histori Pembelian 

### Sample Data
```
{
    "ordreId": "ODR202201160000000003",
    "userToken" : "8bde4b491892d7dac832a9807e39bfd30861c5885128bfa5fdf7f499690251c7"
}
```


### Resoponse
```
{
    "ResponseCode": "200000",
    "ResponseStatus": "Success",
    "ResponseMessage": "Data ditemukan",
    "ResponseData": {
        "order_id": "ODR202201160000000003",
        "invoice_id": "INV202201160000000003",
        "order_date": "16 January 2022",
        "company_id": "7",
        "company_name": "Indah Setara",
        "product_price": 3500000,
        "payment_id": 1,
        "payment_name": "BRI",
        "order_status_id": 1,
        "order_status_name": "Belum Bayar",
        "shipping_id": 3,
        "shipping_costs": 0,
        "shipping_address": "Jl. Pabean Link. kaligandu Bujang Boros",
        "items": 1,
        "order_detail": [
            {
                "product_name": "Tool Set Tekiro 120 pcs Kunci Sok Set Tekiro Ring",
                "image": "20_4e06a85f_7605_IMG_MAIN.png",
                "price": 1750000,
                "quantity": 2,
                "product_price_total": 3500000
            }
        ]
    }
}
```
## Table Response Data
| Response Code | Status |
| ----------- | ----------- |
|200000| Data ditemukan |
|400000| Request Method tidak sesuai |
|400001| Parameter tidak valid|
|400003| Token tidak valid|
|400999| Data tidak ditemukan|

---

## Address 
METHOD **POST** | [ENDPOINT](https://api.bursaukm.com/v1/address) : 
```
https://api.bursaukm.com/v1/address
```
> Data Alamat default untuk pengiriaman  

### Sample Data
```
{
    "userToken" : "8bde4b491892d7dac832a9807e39bfd30861c5885128bfa5fdf7f499690251c7"
}
```


### Resoponse
```
{
    "ResponseCode": "200000",
    "ResponseStatus": "Success",
    "ResponseMessage": "Data ditemukan",
    "ResponseData": [
        {
            "user_address_id": "3",
            "user_address_label": "Kantor",
            "user_address_name": "Syarif Hidayatulloh",
            "user_address_phone": "089668132627",
            "province_id": "36",
            "regencies_id": "361",
            "districts_id": "3601001",
            "users_address": "Jl. Pabean Link. kaligandu Bujang Boros",
            "postal_code": "32437",
            "users_id": "15"
        }
    ]
}
```
## Table Response Data
| Response Code | Status |
| ----------- | ----------- |
|200000| Data ditemukan |
|400000| Request Method tidak sesuai |
|400001| Parameter tidak valid|
|400003| Token tidak valid|
|400999| Data tidak ditemukan|

---

## Konfirmasi Pembayaran 
METHOD **POST** | [ENDPOINT](https://api.bursaukm.com/v1/confirm-payment) : 
```
https://api.bursaukm.com/v1/confirm-payment
```
> Konfirmasi pembayaran, dengan upload gambar

### Sample Data
```
{
    "userToken" : "41c3c969c34578c45b5643a68292d49130c1241eb146d9823a7e87d379c98dd6",
    "bank_id": 1,
    "bank_number": "123456",
    "total_paid": 1234,
    "date": "2022-01-12",
    "code_ref": "DG12",
    "receipt": "",
    "order_id": "ODR202201090000000001"
}
```
-  bank_id : (Integer),
-  bank_number : (Integer),
-  total_paid : (Integer),
-  date : (date),
-  code_ref (String, 64 chars)
-  receipt : (String, converted from BLOB to Base64)
-  userToken (String, 64 chars)
### Resoponse
```
{
    "ResponseCode": "200000",
    "ResponseStatus": "Success",
    "ResponseMessage": "Data berhasil disimpan",
    "ResponseData": ""
}
```
## Table Response Data
| Response Code | Status |
| ----------- | ----------- |
|200000| Data berhasil disimpan |
|400000| Request Method tidak sesuai |
|400001| Parameter tidak valid|
|400003| Token tidak valid|
|400005| Insert gagal|
|400999| Data tidak ditemukan|

---

## Daftar Alamat User 
METHOD **POST** | [ENDPOINT](https://api.bursaukm.com/v1/user/address) : 
```
https://api.bursaukm.com/v1/user/address
```
> Daftar Semua Alamat user

### Sample Data
```
{
    "userToken" : "41c3c969c34578c45b5643a68292d49130c1241eb146d9823a7e87d379c98dd6"
}
```


### Resoponse
```
{
    "ResponseCode": "200000",
    "ResponseStatus": "Success",
    "ResponseMessage": "Data ditemukan",
    "ResponseData": [
        {
            "id": "3",
            "user_address_label": "Kantor",
            "user_address_name": "Syarif Hidayatulloh",
            "user_address_phone": "089668132627",
            "province_id": "36",
            "regencies_id": "361",
            "districts_id": "3601001",
            "users_address": "Jl. Pabean Link. kaligandu Bujang Boros",
            "postal_code": "32437",
            "users_id": "15",
            "info": "UTAMA"
        },
        {
            "id": "2",
            "user_address_label": "Rumah Teman",
            "user_address_name": "Syarif H",
            "user_address_phone": "081966813262",
            "province_id": "36",
            "regencies_id": "3673",
            "districts_id": "3673060",
            "users_address": "Jl. Pabean Link. Kaligandu B.B RT. 14 RW.06 Kec. Purwakarta Kel. Purwakarta Cilegon",
            "postal_code": "42437",
            "users_id": "15",
            "info": null
        }
    ]
}
```
## Table Response Data
| Response Code | Status |
| ----------- | ----------- |
|200000| Data ditemukan |
|200001| Data tidak ditemukan|
|400000| Request Method tidak sesuai |
|400001| Parameter tidak valid|
|400003| Token tidak valid|

---

## Tambah Alamat User 
METHOD **POST** | [ENDPOINT](https://api.bursaukm.com/v1/user/address/new) : 
```
https://api.bursaukm.com/v1/user/address/new
```
> Tambah Alamat user

### Sample Data
```
{
    "userToken" : "ba08d8869900c8fd43f4fb96bcba942570a299a998591dc66868952fe6947c2a",
    "label": "Rumah", 
    "address_name" : "PT TRI KARYA NUSANTARA", 
    "address_phone": "81123456789", 
    "province_id": "31", 
    "regencies_id": "3175", 
    "districts_id": "3175050", 
    "users_address": "JL. BUNCIT RAYA NO 22, Kel. Pejaten Barat, Kec. Pasar Minggu, Kota Adm. Jakarta Selatan, Prop. DKI Jakarta", 
    "postal_code": "42213"
}
```


### Resoponse
```
{
    "ResponseCode": "200000",
    "ResponseStatus": "Success",
    "ResponseMessage": "Data berhasil disimpan",
    "ResponseData": ""
}
```
## Table Response Data
| Response Code | Status |
| ----------- | ----------- |
|200000| Data berhasil disimpan |
|200001| Data tidak ditemukan|
|400000| Request Method tidak sesuai |
|400001| Parameter tidak valid|
|400003| Token tidak valid|

---

## Set Default Alamat User 
METHOD **POST** | [ENDPOINT](https://api.bursaukm.com/v1/user/address/new) : 
```
https://api.bursaukm.com/v1/user/address/new
```
> Set/Merubah default Alamat user

### Sample Data
```
{
    "userToken" : "ba08d8869900c8fd43f4fb96bcba942570a299a998591dc66868952fe6947c2a",
    "address_id": 3
}
```


### Resoponse
```
{
    "ResponseCode": "200000",
    "ResponseStatus": "Success",
    "ResponseMessage": "Data berhasil disimpan",
    "ResponseData": ""
}
```
## Table Response Data
| Response Code | Status |
| ----------- | ----------- |
|200000| Data berhasil disimpan |
|400000| Request Method tidak sesuai |
|400001| Parameter tidak valid|
|400003| Token tidak valid|
|400999| Data Gagal simpan|

---