# Đối tượng Voucher
Đối tượng chứng từ sẽ quản lý tổng quan về sổ quỹ tiền mặt của cửa hàng của các chi nhánh (nếu có), các loại phiếu thu, phiếu chi, sổ quỹ và hạch toán kinh doanh cho cửa hàng.

[1. Tạo mới đối tượng quản lý Vouchers](#add-voucher_actors)

[2. Lấy 1 đối tượng vouchers theo id](#get-voucher_actors_id)

[3. Lấy toàn bộ danh sách đối tượng vouchers](#get-voucher_actors)

[4. Lấy ra nhóm phiếu chi](#get-payment_voucher_groups)

[5. Lấy ra nhóm phiếu thu](#get-receipt_voucher_groups)

<a name="add-voucher_actors"></a>
## 1. Tạo mới đối tượng quản lý Vouchers
**Request**
```
POST /admin/vouchers_actors HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
"{
""voucher_actor"":{
""name"":""Thưởng""
}
}"
```
**Kết quả trả về**
```
"{
  ""voucher_actor"": {
    ""id"": 2,
    ""tenant_id"": 9287,
    ""name"": ""Thưởng"",
    ""created_on"": ""2017-03-10T11:24:08Z"",
    ""modified_on"": ""2017-03-10T11:24:08Z""
  }
}"
```
**Trường hợp xảy ra lỗi**
```
{
    "data_error": {
        "status": 422,
        "errors": {
            "name": "Tên đối tượng đã tồn tại"
        }
    }
}
```
<a name="get-voucher_actors_id"></a>
## 2. Lấy 1 đối tượng vouchers theo id
**Request**
```
GET /admin/vouchers_actors/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "voucher_actor": {
        "id": 9362,
        "tenant_id": 56322,
        "name": "Sơn",
        "created_on": "2018-06-29T06:46:12Z",
        "modified_on": "2018-06-29T06:46:12Z",
        "status": "active"
    }
}
```
**Trường hợp xảy ra lỗi**
```
{
    "error": {
        "message": "Không tìm thấy đối tượng"
    }
}
```
<a name="get-voucher_actors"></a>
## 3. Lấy toàn bộ danh sách đối tượng vouchers
**Request**
```
GET /admin/vouchers_actors?query= HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "metadata": null,
    "voucher_actors": [
        {
            "id": 9354,
            "tenant_id": 56322,
            "name": "Hà",
            "created_on": "2018-06-29T03:45:32Z",
            "modified_on": "2018-06-29T03:45:32Z",
            "status": "active"
        }
    ]
}
```
**Trường hợp xảy ra lỗi**
```
{
    "metadata": null,
    "voucher_actors": []
}
```
<a name="get-payment_voucher_groups"></a>
## 4. Lấy ra nhóm phiếu chi
**Request**
```
GET /admin/payment_voucher_groups HTTP/1.1
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
    "payment_voucher_groups": [
        {
            "id": 983501,
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
            "id": 983500,
            "tenant_id": 56322,
            "name": "Trả nợ đối tác vận chuyển",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "TRANO",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983491,
            "tenant_id": 56322,
            "name": "Chi phí sinh hoạt",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "PVG12",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983490,
            "tenant_id": 56322,
            "name": "Chi phí sản xuất",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "PVG14",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983489,
            "tenant_id": 56322,
            "name": "Chi phí quản lý cửa hàng",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "PVG9",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983488,
            "tenant_id": 56322,
            "name": "Chi phí nhân công",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "PVG11",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983487,
            "tenant_id": 56322,
            "name": "Chi phí nguyên - vật liệu",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "PVG13",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983486,
            "tenant_id": 56322,
            "name": "Chi phí khác",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "PVG15",
            "status": "active",
            "auto_init": true
        },
        {
            "id": 983485,
            "tenant_id": 56322,
            "name": "Chi phí bán hàng",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "note": null,
            "code": "PVG10",
            "status": "active",
            "auto_init": true
        }
    ]
}
```
<a name="get-receipt_voucher_groups"></a>
## 5. Lấy ra nhóm phiếu thu
**Request**
```
GET /admin/receipt_voucher_groups HTTP/1.1
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
