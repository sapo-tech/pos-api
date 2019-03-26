# Kênh bán hàng
Nếu bán hàng tại cửa hàng dùng màn hình pos mặc định là kênh POS
Còn khi chủ shop bán hàng online thì bắt buộc phải có kênh bán hàng.
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

[ 1. Lấy một đối tượng kênh bán hàng ](#get-order_source_id)

[ 2. Thêm một kênh bán hàng](#add-order_source)

[ 3. Sửa một kênh bán hàng](#put-order_source_id)

[ 4. Xoá kênh bán hàng](#delete-order_source_id)

[ 5. Lấy kênh bán hàng theo bộ lọc](#sget-order_source?)

<a name="get-order_source_id"></a>
## 1. Lấy một đối tượng kênh bán hàng
**Request**
```
GET /admin/order_sources/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

param request: ?include_deleted
```
**Kết quả trả về**
```
{
    "order_source": {
        "id": 387299,
        "tenant_id": 56322,
        "name": "Web",
        "status": "default",
        "init": true,
        "created_on": "2018-05-08T02:07:57Z",
        "modified_on": "2018-05-08T02:07:57Z"
    }
}
```
<a name="add-order_source"></a>
## 2. Thêm một kênh bán hàng
**Request**
```
POST /admin/order_sources HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "order_source": {
    "name": "Cửa hàng X",
    "status": "active"
  }
}
```
**Kết quả trả về**
```
{
    "order_source": {
        "id": 465899,
        "tenant_id": 56322,
        "name": "Cửa hàng X",
        "status": "active",
        "init": false,
        "created_on": "2018-07-26T03:25:45Z",
        "modified_on": "2018-07-26T03:25:45Z"
    }
}
```
**Trường hợp có lỗi**
```
{
    "error": {
        "message": "Đã tồn tại kênh bán hàng có tên: Other"
    }
}
```
<a name="put-order_source_id"></a>
## 3. Sửa một kênh bán hàng
**Request**
```
PUT /admin/order_sources/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "order_source": {
    "name": "Web",
    "status": "default"
  }
}
```
**Kết quả trả về**
```
{
    "order_source": {
        "id": 387299,
        "tenant_id": 56322,
        "name": "Web",
        "status": "default",
        "init": true,
        "created_on": "2018-05-08T02:07:57Z",
        "modified_on": "2018-05-08T02:07:57Z"
    }
}
```
**Trường hợp có lỗi**
```
{
    "error": {
        "message": "Không thể cập nhật tên của kênh bán hàng khởi tạo bởi hệ thống"
    }
}
```
<a name="delete-order_source_id"></a>
## 4. Xoá kênh bán hàng
**Request**
```
DELETE /admin/order_sources/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
Status 200 OK
```
**Trường hợp có lỗi**
```
{
    "error": {
        "message": "Không thể xóa kênh bán hàng mặc định"
    }
}
```
<a name="get-order_source?"></a>
## 5. Lấy kênh bán hàng theo bộ lọc
**Request**
```
GET /admin/order_sources HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

param request: name = web
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 1,
        "page": 1,
        "limit": 250
    },
    "order_sources": [
        {
            "id": 387299,
            "tenant_id": 56322,
            "name": "Web",
            "status": "default",
            "init": true,
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z"
        }
    ]
}
```

