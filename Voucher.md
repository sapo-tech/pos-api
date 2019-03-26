# Voucher
[1. Phiếu chi](#payment_vouchers)

  [1.1 Đăng phiếu chi](#add-payment_vouchers)
   
  [1.2 Lấy phiếu chi theo id](#get-payment_vouchers_id)

  [1.3 Lấy mã code phiếu chi](#get-payment_vouchers_codes)

  [1.4 Cập nhật phiếu chi](#put-payment_vouchers_id)

  [1.5 Hủy phiếu chi](#payment_vouchers_id-cancel)

  [1.6 Lấy phiếu chi theo bộ lọc](#get-payment_vouchers?)
  
[2. Phiếu thu](#receipt_vouchers)

  [2.1 Đăng phiếu thu](#add-receipt_vouchers)
   
  [2.2 Lấy phiếu thu theo id](#get-receipt_vouchers_id)

  [2.3 Lấy mã code phiếu thu](#get-receipt_vouchers_codes)

  [2.4 Cập nhật phiếu thu](#put-receipt_vouchers_id)

  [2.5 Hủy phiếu thu](#receipt_vouchers_id-cancel)

  [2.6 Lấy loại phiếu thu](#get-payment_voucher_groups)
  
  [2.7 Lấy loại phiếu thu theo id](#get-receipt_voucher_groups_id)
  
  [2.8 Lấy mã code loại phiếu thu](#get-receipt_voucher_groups_codes)
  
  
<a name="payment_vouchers"></a>
## 1. Phiếu chi
Chủ shop quản lý phiếu thu và phiếu chi của cửa hàng.
Phiếu chi là chứng từ kế toán bắt buộc dùng để xác định số tiền mặt thực tế nhập quỹ, làm bằng chứng cho việc đã thanh toán hay chưa.

<a name="add-payment_vouchers"></a>
### 1.1 Đăng phiếu chi

**Request**
```
POST /admin/payment_vouchers HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

{
  "payment_voucher": {
    "id": 4,
    "tenant_id": 77,
    "location_id": 81,
    "account_id": 0,
    "code": "PV1307164",
    "object_type": "customer",
    "object_id": "1381",
    "issued_on": "2016-07-13T01:59:35Z",
    "reference": "refrrrrrrrrrrrrrrrrrrr",
    "note": "Piếu này đã sửa",
    "payment_method_id": 2008,
    "currency_id": 7030,
    "exchange_rate": 0,
    "amount": 9000,
    "source_type": null,
    "source_id": null,
    "type": "payment",
    "auto": false,
    "counted": true,
    "status": "cancelled",
    "created_on": "2016-07-13T02:00:02Z",
    "modified_on": "2016-07-13T02:12:31Z",
    "tags": [
      "hoinx",
      "haha091",
      "hichic"
    ]
  }
}
```
**Kết quả trả về khi đăng chứng từ thanh toán thành công**
```
{
  "payment_voucher": {
    "id": 4,
    "tenant_id": 77,
    "location_id": 81,
    "account_id": 0,
    "code": "PV1307164",
    "object_type": "customer",
    "object_id": "1381",
    "issued_on": "2016-07-13T01:59:35Z",
    "reference": "refrrrrrrrrrrrrrrrrrrr",
    "note": "Piếu này đã sửa",
    "payment_method_id": 2008,
    "currency_id": 7030,
    "exchange_rate": 0,
    "amount": 9000,
    "source_type": null,
    "source_id": null,
    "type": "payment",
    "auto": false,
    "counted": true,
    "status": "cancelled",
    "created_on": "2016-07-13T02:00:02Z",
    "modified_on": "2016-07-13T02:12:31Z",
    "tags": [
      "hoinx",
      "haha091",
      "hichic"
    ]
  }
}
```
<a name="get-payment_vouchers_id"></a>
### 1.2 Lấy phiếu chi theo id

**Request**
```
GET /admin/payment_vouchers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json 
```
**Kết quả trả về**

```
{
    "payment_voucher": {
        "id": 7414112,
        "tenant_id": 56322,
        "location_id": 58369,
        "account_id": 72098,
        "code": "PV20071811",
        "object_type": "customer",
        "object_id": 3280093,
        "issued_on": "2016-06-30T11:06:29Z",
        "reference": null,
        "note": "Phiếu chi tự động tạo khi hoàn tiền cho khách trả hàng",
        "payment_method_id": 220256,
        "currency_id": 0,
        "exchange_rate": 1,
        "amount": 10000,
        "source_type": "refund",
        "source_id": 159706,
        "group_id": 983501,
        "group_name": "Tự động",
        "auto": true,
        "counted": false,
        "status": "active",
        "created_on": "2018-07-20T09:08:09Z",
        "modified_on": "2018-07-20T09:08:09Z",
        "tags": [],
        "cancelled_on": null,
        "document_root_id": 212603,
        "document_root_code": "SR2007185",
        "account_name": null,
        "payment_method_name": null
    }
}
```
**Trường hợp có lỗi**

```
{
    "error": {
        "message": "Phiếu chi không tồn tại"
    }
}
```
<a name="get-payment_vouchers_codes"></a>
### 1.3 Lấy mã code phiếu chi

**Request**
```
GET /admin/payment_vouchers/codes HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json 
```
**Kết quả trả về**

```
{
    "payment_voucher": {
        "id": 7414112,
        "tenant_id": 56322,
        "location_id": 58369,
        "account_id": 72098,
        "code": "PV20071811",
        "object_type": "customer",
        "object_id": 3280093,
        "issued_on": "2016-06-30T11:06:29Z",
        "reference": null,
        "note": "Phiếu chi tự động tạo khi hoàn tiền cho khách trả hàng",
        "payment_method_id": 220256,
        "currency_id": 0,
        "exchange_rate": 1,
        "amount": 10000,
        "source_type": "refund",
        "source_id": 159706,
        "group_id": 983501,
        "group_name": "Tự động",
        "auto": true,
        "counted": false,
        "status": "active",
        "created_on": "2018-07-20T09:08:09Z",
        "modified_on": "2018-07-20T09:08:09Z",
        "tags": [],
        "cancelled_on": null,
        "document_root_id": 212603,
        "document_root_code": "SR2007185",
        "account_name": null,
        "payment_method_name": null
    }
}
```
**Trường hợp có lỗi**

```
{
    "error": {
        "message": "Phiếu chi không tồn tại"
    }
}
```
<a name="put-payment_vouchers_id"></a>
### 1.4 Cập nhật phiếu chi
**Request**

```
PUT /admin/payment_vouchers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json 

{"note": "abc"}
```
**Kết quả trả về**

```
{
    "payment_voucher": {
        "id": 7414112,
        "tenant_id": 56322,
        "location_id": 58369,
        "account_id": 72098,
        "code": "PV20071811",
        "object_type": "customer",
        "object_id": 3280093,
        "issued_on": "2016-06-30T11:06:29Z",
        "reference": null,
        "note": "abc",
        "payment_method_id": 220256,
        "currency_id": 0,
        "exchange_rate": 1,
        "amount": 10000,
        "source_type": "refund",
        "source_id": 159706,
        "group_id": 983501,
        "group_name": null,
        "auto": true,
        "counted": false,
        "status": "active",
        "created_on": "2018-07-20T09:08:09Z",
        "modified_on": "2018-07-23T03:35:51Z",
        "tags": [],
        "cancelled_on": null,
        "document_root_id": 212603,
        "document_root_code": "SR2007185",
        "account_name": null,
        "payment_method_name": null
    }
}
```
**Trường hợp có lỗi**

```
{
    "error": {
        "message": "Không tìm thấy đối tượng"
    }
}
```
<a name="payment_vouchers_id-cancel"></a>
### 1.5 Hủy phiếu chi
**Request**
```
POST /admin/payment_vouchers/{id}/cancel HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json 
```
**Kết quả trả về**
```
Status: 200 OK
```
**Trường hợp có lỗi**
```
{
    "error": {
        "message": "Không có quyền hoặc bị chặn thao tác"
    }
}
```
<a name="get-payment_vouchers?"></a>
### 1.6 Lấy phiếu chi theo bộ lọc

**Request**
```
GET /admin/payment_vouchers HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json 

param: "limit"=1000
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 9,
        "page": 1,
        "limit": 1000
    },
    "payment_vouchers": [
        {
            "id": 7414112,
            "tenant_id": 56322,
            "location_id": 58369,
            "account_id": 72098,
            "code": "PV20071811",
            "object_type": "customer",
            "object_id": 3280093,
            "issued_on": "2016-06-30T11:06:29Z",
            "reference": null,
            "note": "abc",
            "payment_method_id": 220256,
            "currency_id": 0,
            "exchange_rate": 1,
            "amount": 10000,
            "source_type": "refund",
            "source_id": 159706,
            "group_id": 983501,
            "group_name": "Tự động",
            "auto": true,
            "counted": false,
            "status": "active",
            "created_on": "2018-07-20T09:08:09Z",
            "modified_on": "2018-07-23T03:35:51Z",
            "tags": null,
            "cancelled_on": null,
            "document_root_id": 212603,
            "document_root_code": "SR2007185",
            "payment_method_name": null,
            "account_name": null
        },
        {
            "id": 7414077,
            "tenant_id": 56322,
            "location_id": 58369,
            "account_id": 72098,
            "code": "PV20071810",
            "object_type": "customer",
            "object_id": 3281243,
            "issued_on": "2018-07-20T09:07:12Z",
            "reference": null,
            "note": "Phiếu chi tự động tạo khi hoàn tiền cho khách trả hàng",
            "payment_method_id": 220256,
            "currency_id": 0,
            "exchange_rate": 1,
            "amount": 1000000,
            "source_type": "refund",
            "source_id": 159703,
            "group_id": 983501,
            "group_name": "Tự động",
            "auto": true,
            "counted": false,
            "status": "active",
            "created_on": "2018-07-20T09:07:09Z",
            "modified_on": "2018-07-20T09:07:09Z",
            "tags": null,
            "cancelled_on": null,
            "document_root_id": 212602,
            "document_root_code": "SR2007184",
            "payment_method_name": null,
            "account_name": null
        },
        {
            "id": 7414044,
            "tenant_id": 56322,
            "location_id": 58369,
            "account_id": 72098,
            "code": "PV2007189",
            "object_type": "customer",
            "object_id": 3281243,
            "issued_on": "2018-07-20T09:06:08Z",
            "reference": null,
            "note": "Phiếu chi tự động tạo khi hoàn tiền cho khách trả hàng",
            "payment_method_id": 220256,
            "currency_id": 0,
            "exchange_rate": 1,
            "amount": 350000,
            "source_type": "refund",
            "source_id": 159702,
            "group_id": 983501,
            "group_name": "Tự động",
            "auto": true,
            "counted": false,
            "status": "active",
            "created_on": "2018-07-20T09:06:18Z",
            "modified_on": "2018-07-20T09:06:18Z",
            "tags": null,
            "cancelled_on": null,
            "document_root_id": 212602,
            "document_root_code": "SR2007184",
            "payment_method_name": null,
            "account_name": null
        },
        {
            "id": 7413991,
            "tenant_id": 56322,
            "location_id": 58369,
            "account_id": 72098,
            "code": "PV2007188",
            "object_type": "customer",
            "object_id": 3338352,
            "issued_on": "2018-07-20T09:04:25Z",
            "reference": null,
            "note": "Phiếu chi tự động tạo khi hoàn tiền cho khách trả hàng",
            "payment_method_id": 220256,
            "currency_id": 0,
            "exchange_rate": 1,
            "amount": 100000,
            "source_type": "refund",
            "source_id": 159700,
            "group_id": 983501,
            "group_name": "Tự động",
            "auto": true,
            "counted": false,
            "status": "active",
            "created_on": "2018-07-20T09:04:56Z",
            "modified_on": "2018-07-20T09:04:56Z",
            "tags": null,
            "cancelled_on": null,
            "document_root_id": 212599,
            "document_root_code": "SR2007183",
            "payment_method_name": null,
            "account_name": null
        },
        {
            "id": 7413900,
            "tenant_id": 56322,
            "location_id": 58369,
            "account_id": 72098,
            "code": "PV2007187",
            "object_type": "customer",
            "object_id": 4128452,
            "issued_on": "2018-07-20T09:02:07Z",
            "reference": null,
            "note": "Phiếu chi tự động tạo khi hoàn tiền cho khách trả hàng",
            "payment_method_id": 220256,
            "currency_id": 0,
            "exchange_rate": 1,
            "amount": 790000,
            "source_type": "refund",
            "source_id": 159698,
            "group_id": 983501,
            "group_name": "Tự động",
            "auto": true,
            "counted": false,
            "status": "active",
            "created_on": "2018-07-20T09:02:05Z",
            "modified_on": "2018-07-20T09:02:05Z",
            "tags": null,
            "cancelled_on": null,
            "document_root_id": 212580,
            "document_root_code": "SR2007182",
            "payment_method_name": null,
            "account_name": null
        },
        {
            "id": 7413801,
            "tenant_id": 56322,
            "location_id": 58369,
            "account_id": 72098,
            "code": "PV2007186",
            "object_type": "customer",
            "object_id": 4128452,
            "issued_on": "2016-06-30T11:06:29Z",
            "reference": null,
            "note": "Phiếu chi tự động tạo khi hoàn tiền cho khách trả hàng",
            "payment_method_id": 220256,
            "currency_id": 0,
            "exchange_rate": 1,
            "amount": 10000,
            "source_type": "refund",
            "source_id": 159694,
            "group_id": 983501,
            "group_name": "Tự động",
            "auto": true,
            "counted": false,
            "status": "active",
            "created_on": "2018-07-20T08:59:15Z",
            "modified_on": "2018-07-20T08:59:15Z",
            "tags": null,
            "cancelled_on": null,
            "document_root_id": 212580,
            "document_root_code": "SR2007182",
            "payment_method_name": null,
            "account_name": null
        },
        {
            "id": 7413730,
            "tenant_id": 56322,
            "location_id": 58369,
            "account_id": 72098,
            "code": "PV2007185",
            "object_type": "customer",
            "object_id": 3335156,
            "issued_on": "2018-07-20T08:56:54Z",
            "reference": null,
            "note": "Phiếu chi tự động tạo khi hoàn tiền cho khách trả hàng",
            "payment_method_id": 220256,
            "currency_id": 0,
            "exchange_rate": 1,
            "amount": 1999980,
            "source_type": "refund",
            "source_id": 159689,
            "group_id": 983501,
            "group_name": "Tự động",
            "auto": true,
            "counted": false,
            "status": "active",
            "created_on": "2018-07-20T08:56:50Z",
            "modified_on": "2018-07-20T08:56:50Z",
            "tags": null,
            "cancelled_on": null,
            "document_root_id": 198300,
            "document_root_code": "SR2906181",
            "payment_method_name": null,
            "account_name": null
        },
        {
            "id": 7017948,
            "tenant_id": 56322,
            "location_id": 58369,
            "account_id": 72098,
            "code": "PV0207182",
            "object_type": "customer",
            "object_id": 3689589,
            "issued_on": "2018-07-02T04:34:54Z",
            "reference": null,
            "note": "Phiếu chi tự động tạo khi hoàn tiền cho khách trả hàng",
            "payment_method_id": 220256,
            "currency_id": 0,
            "exchange_rate": 1,
            "amount": 800000,
            "source_type": "refund",
            "source_id": 150241,
            "group_id": 983501,
            "group_name": "Tự động",
            "auto": true,
            "counted": false,
            "status": "active",
            "created_on": "2018-07-02T04:34:54Z",
            "modified_on": "2018-07-02T04:34:54Z",
            "tags": null,
            "cancelled_on": null,
            "document_root_id": 200294,
            "document_root_code": "SR0207183",
            "payment_method_name": null,
            "account_name": null
        },
        {
            "id": 7017348,
            "tenant_id": 56322,
            "location_id": 58369,
            "account_id": 72098,
            "code": "PV0207181",
            "object_type": "customer",
            "object_id": 3280093,
            "issued_on": "2018-07-02T04:08:17Z",
            "reference": null,
            "note": "Phiếu chi tự động tạo khi hoàn tiền cho khách trả hàng",
            "payment_method_id": 220256,
            "currency_id": 0,
            "exchange_rate": 1,
            "amount": 1500000,
            "source_type": "refund",
            "source_id": 150219,
            "group_id": 983501,
            "group_name": "Tự động",
            "auto": true,
            "counted": false,
            "status": "active",
            "created_on": "2018-07-02T04:08:16Z",
            "modified_on": "2018-07-02T04:08:16Z",
            "tags": null,
            "cancelled_on": null,
            "document_root_id": 200275,
            "document_root_code": "SR0207182",
            "payment_method_name": null,
            "account_name": null
        }
    ]
}
```

<a name="receipt_vouchers"></a>
## 2. Phiếu thu
Chủ shop quản lý phiếu thu và phiếu chi của cửa hàng.
Phiếu thu là chứng từ kế toán bắt buộc dùng để xác định số tiền mặt thực tế nhập quỹ, làm bằng chứng cho việc đã thanh toán hay chưa.

<a name="add-receipt_vouchers"></a>
### 2.1 Đăng phiếu thu

**Request**
```
POST /admin/receipt_vouchers HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

{
  "receipt_voucher": {
    "id": 7517872,
    "tenant_id": 56322,
    "location_id": 58369,
    "account_id": 72098,
    "code": "RV25071814",
    "object_type": "customer",
    "object_id": 3689589,
    "issued_on": "2018-07-25T04:26:25Z",
    "reference": null,
    "note": null,
    "payment_method_id": 220258,
    "currency_id": 56321,
    "exchange_rate": 1,
    "amount": 7000000,
    "source_type": null,
    "source_id": null,
    "group_id": 983492,
    "group_name": "Cho thuê tài sản",
    "auto": false,
    "counted": true,
    "status": "active",
    "created_on": "2018-07-25T04:26:51Z",
    "modified_on": "2018-07-25T04:26:51Z",
    "tags": [],
    "cancelled_on": null,
    "document_root_id": null,
    "document_root_code": null,
    "account_name": null,
    "payment_method_name": null
  }
}
```
**Kết quả trả về khi đăng chứng từ thanh toán thành công**
```
{
    "receipt_voucher": {
        "id": 7517897,
        "tenant_id": 56322,
        "location_id": 58369,
        "account_id": 72098,
        "code": "RV25071815",
        "object_type": "customer",
        "object_id": 3689589,
        "issued_on": "2018-07-25T04:26:25Z",
        "reference": null,
        "note": null,
        "payment_method_id": 220258,
        "currency_id": 56321,
        "exchange_rate": 1,
        "amount": 7000000,
        "source_type": null,
        "source_id": null,
        "group_id": 983492,
        "group_name": null,
        "auto": false,
        "counted": true,
        "status": "active",
        "created_on": "2018-07-25T04:27:14Z",
        "modified_on": "2018-07-25T04:27:14Z",
        "tags": [],
        "cancelled_on": null,
        "document_root_id": null,
        "document_root_code": null,
        "account_name": null,
        "payment_method_name": null
    }
}
```
<a name="get-receipt_vouchers_id"></a>
### 2.2 Lấy phiếu thu theo id

**Request**
```
GET /admin/receipt_vouchers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json 
```
**Kết quả trả về**

```
{
    "receipt_voucher": {
        "id": 7517897,
        "tenant_id": 56322,
        "location_id": 58369,
        "account_id": 72098,
        "code": "RV25071815",
        "object_type": "customer",
        "object_id": 3689589,
        "issued_on": "2018-07-25T04:26:25Z",
        "reference": null,
        "note": null,
        "payment_method_id": 220258,
        "currency_id": 56321,
        "exchange_rate": 1,
        "amount": 7000000,
        "source_type": null,
        "source_id": null,
        "group_id": 983492,
        "group_name": "Cho thuê tài sản",
        "auto": false,
        "counted": true,
        "status": "active",
        "created_on": "2018-07-25T04:27:14Z",
        "modified_on": "2018-07-25T04:27:14Z",
        "tags": [],
        "cancelled_on": null,
        "document_root_id": null,
        "document_root_code": null,
        "account_name": null,
        "payment_method_name": null
    }
}
```
**Trường hợp có lỗi**

```
{
    "error": {
        "message": "Phiếu thu không tồn tại"
    }
}
```
<a name="get-receipt_vouchers_codes"></a>
### 2.3 Lấy mã code phiếu thu

**Request**
```
GET /admin/payment_vouchers/codes HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json 
```
**Kết quả trả về**

```
{
    "voucher_code": {
        "tenant_id": 56322,
        "code": "RV25071816"
    }
}
```

<a name="put-receipt_vouchers_id"></a>
### 2.4 Cập nhật phiếu thu
**Request**
```
PUT /admin/receipt_vouchers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json 

{"note": "Phiếu thu đã được cập nhật"}
```
**Kết quả trả về**

```
{
    "receipt_voucher": {
        "id": 7517897,
        "tenant_id": 56322,
        "location_id": 58369,
        "account_id": 72098,
        "code": "RV25071815",
        "object_type": "customer",
        "object_id": 3689589,
        "issued_on": "2018-07-25T04:26:25Z",
        "reference": null,
        "note": "Phiếu thu đã được cập nhật",
        "payment_method_id": 220258,
        "currency_id": 56321,
        "exchange_rate": 1,
        "amount": 7000000,
        "source_type": null,
        "source_id": null,
        "group_id": 983492,
        "group_name": null,
        "auto": false,
        "counted": true,
        "status": "active",
        "created_on": "2018-07-25T04:27:14Z",
        "modified_on": "2018-07-25T04:31:50Z",
        "tags": [],
        "cancelled_on": null,
        "document_root_id": null,
        "document_root_code": null,
        "payment_method_name": null,
        "account_name": null
    }
}
```
**Trường hợp có lỗi**

```
{
    "error": {
        "message": "Không tìm thấy đối tượng"
    }
}
```
<a name="receipt_vouchers_id-cancel"></a>

### 2.5 Hủy phiếu thu
**Request**
```
POST /admin/receipt_vouchers/{id}/cancel HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json 

```
**Kết quả trả về**
```
Status: 200 OK
```
**Trường hợp có lỗi**
```
{
    "error": {
        "message": "Không có quyền hoặc bị chặn thao tác"
    }
}
```

<a name="get-payment_voucher_groups"></a>
### 2.6 Lấy loại phiếu thu
**Request**
```
GET /admin/receipt_vouchers HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 9,
        "page": 1,
        "limit": 250
    },
    "receipt_voucher_groups": [
        {
            "id": 983502,
            "tenant_id": 56322,
            "name": "Tự động",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "TUDONG",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983499,
            "tenant_id": 56322,
            "name": "Tiền thưởng",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "RVG6",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983498,
            "tenant_id": 56322,
            "name": "Tiền bồi thường",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "RVG5",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983497,
            "tenant_id": 56322,
            "name": "Thu nợ khách hàng",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "RVG2",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983496,
            "tenant_id": 56322,
            "name": "Thu nợ đối tác vận chuyển",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "THUNO",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983495,
            "tenant_id": 56322,
            "name": "Thu nhập khác",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "RVG7",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983494,
            "tenant_id": 56322,
            "name": "Nhượng bán, thanh lý tài sản",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "RVG3",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983493,
            "tenant_id": 56322,
            "name": "Đối tác vận chuyển đặt cọc",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "DATCOC",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983492,
            "tenant_id": 56322,
            "name": "Cho thuê tài sản",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "RVG4",
            "status": "active",
            "auto_init": true
        }
    ]
}
```
<a name="get-receipt_voucher_groups_id"></a>
### 2.7 Lấy loại phiếu thu theo id
**Request**
```
GET /admin/receipt_vouchers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "receipt_voucher_group": {
        "id": 983502,
        "tenant_id": 56322,
        "name": "Tự động",
        "created_on": "2018-05-08T02:07:57Z",
        "modified_on": "2018-05-08T02:07:57Z",
        "note": null,
        "code": "TUDONG",
        "status": "active",
        "auto_init": true
    }
}
```
**Trường hợp có lỗi**
```
{
    "error": {
        "message": "Không tìm thấy nhóm chi phí"
    }
}
```
<a name="get-receipt_voucher_groups_codes"></a>
### 2.8 Lấy mã code loại phiếu thu
**Request**
```
GET /admin/receipt_vouchers/codes HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "voucher_group_code": {
        "tenant_id": 56322,
        "code": "RVG25071810"
    }
}
```
```
