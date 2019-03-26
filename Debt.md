# Công nợ
Dễ dàng đối chiếu khách hàng, nhà cung cấp còn đang nợ chủ shop.

**Các tham số**

| Tham số | Bắt buộc | Mô tả |
| ------------- |:-------------|:-------------|
| id | no | string -  |
| code | no| string - |
| account_name | no | string -  |
| document_issued_on | no | datetime -  |
| modified_on | no| datetime -  |
| change_debt | no |  -  |
| debt_amount |	no |  - |
| location_id |	no | int -  |
| account_id | no | int -  |
| created_on | no | datetime - Thời gian Order được tạo. API trả về kết quả theo định dạng chuẩn ISO 8601 |
| document_type | no | int -  |
| document_id |	no | string - |
| object_type |	no | int -  |
| object_id | no | string -  |
| action | no | string - |
| log_id | no | int - |
| log_type | no | int - |
| root_id| no | int -  |

[ 1. Lấy ra tổng nợ của một khách hàng ](#customers_id_debts)

[ 2. Lấy ra tổng nợ của một nhà cung cấp](#suppliers_id_debts)

[ 3. Lấy ra tất cả tổng đang nợ của một nhà cung cấp](#suppliers_id_debt_change_logs)

<a name="customers_id_debts"></a>
## 1. Lấy ra tổng nợ của một khách hàng 
**Request**
```
GET /admin/customers/{id}/debts HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "debt": {
        "debt_amount": 693000
    }
}
```
<a name="suppliers_id_debts"></a>
## 2. Lấy ra tổng nợ của một nhà cung cấp
**Request**
```
GET admin/suppliers/{id}/debts HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "debt": {
        "debt_amount": 17500000
    }
}
```
<a name="suppliers_id_debt_change_logs"></a>
## 3. Lấy ra nhật ký tổng nợ của một nhà cung cấp
**Request**
```
GET admin/suppliers/{id}/debt_change_logs HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 1,
        "page": 1,
        "limit": 250
    },
    "debt_change_logs": [
        {
            "id": 17030595,
            "code": "PO1807181",
            "invoice_code": null,
            "account_name": "Ha Duong",
            "document_issued_on": "2018-07-18T08:19:39Z",
            "modified_on": "2018-07-18T08:19:39Z",
            "change_debt": 17500000,
            "debt_amount": 17500000,
            "location_id": 58369,
            "account_id": 72098,
            "created_on": "2018-07-18T08:19:39Z",
            "document_type": 102,
            "document_id": 371937,
            "object_type": 0,
            "object_id": 4202926,
            "action": "bill_added",
            "log_id": 506371,
            "log_type": 1,
            "root_id": 506371
        }
    ]
}
```
