# Nhóm khách hàng

Một tài nguyên Customer đại diện cho một tài khoản khách hàng của Shop. Tài khoản Customer lưu trữ thông tin liên hệ của khách hàng giúp cho người dùng đã đăng nhập không phải khai báo thông tin mỗi khi thực hiện đặt hàng. 
Vì lí do bảo mật, tài nguyên Customer trên Sapo.vn không lưu thông tin thẻ của khách hàng. Khách hàng sẽ vẫn phải cung cấp thông tin thẻ mỗi khi thực hiện thanh toán.

Người dùng có thể quản lý khách hàng theo nhóm để tiện áp dụng cho các chương trình ưu đãi cũng như khuyến mại của cửa hàng. 
Chú ý: Mỗi khách hàng chỉ có thể nằm trong một nhóm khách hàng.

[1. Tạo nhóm khách hàng](#add-customer_groups)

[2. Cập nhật nhóm khách hàng](#put-customer_groups)

[3. Xóa nhóm khách hàng](#delete-customer_groups)

[4. Lấy 1 nhóm khách hàng theo id](#get-customer_groups_id)

[5. Lấy toàn bộ nhóm khách hàng](#get-customer_groups)

[6. Lấy nhóm khách hàng theo bộ lọc](#get-customer_groups?)

<a name= "add-customer_groups"></a>
## 1. Tạo nhóm khách hàng
Bắt đầu với việc tạo nhóm khách hàng, bạn sẽ đưa ra những tùy chọn nhóm để thêm khách hàng vào danh sách.

**Các tham số**

| Tham số | Bắt buộc | Mô tả |
| ------------- |:-------------:|:-------------|
| name | yes | Tên nhóm khách hàng, tên nhóm không được trùng với nhóm đã có trước đó  |
| is_default |	yes | |
| default_payment_term_id | yes |  |
| default_payment_method_id | yes | Id định danh phương thức thanh toán |
| default_tax_type_id"":  | yes | Id định danh mã số thuế |
| default_discount_rate | yes | Tỷ lệ phần trăm giảm giá được quy định nhóm khách hàng |
| default_price_list_id |	yes | Id định danh danh sách hàng  |
| code | yes | Mã tham chiếu đến nhóm khách hàng trong hệ thống |
| note|	no | Ghi chú cho nhóm khách hàng (nếu có) . Trường này có thể NULL |
| id |	yes | Id định danh cho nhóm khách hàng trong hệ thống. Trường không bắt buộc người dùng điền, tự sinh dưới hệ thống khi để trống. |
| tenant_id |	yes | id định danh cho nhân viên thực hiện tạo nhóm khách hàng  |
| created_on |	yes | Thời gian nhóm khách hàng được tạo. API trả về kết quả theo định dạng chuẩn ISO 8601. |
| modified_on |	yes | Thời gian nhóm khách hàng được chỉnh sửa. API trả về kết quả theo định dạng chuẩn ISO 8601. |
| name | yes | Tên nhóm khách hàng, tên nhóm không được trùng với nhóm đã có trước đó |
| name_translate | no | Tên nhóm khách hàng |
| status |	yes | Trạng thái nhóm khách hàng |
| is_default | yes |  |
| default_payment_term_id | yes | id định danh cho kỳ hạn thanh toán |
| default_payment_method_id | yes | Id định danh phương thức thanh toán |
| default_tax_type_id | yes | Id định danh mã số thuế |
| default_discount_rate | yes | Tỷ lệ phần trăm giảm giá được quy định nhóm khách hàng |
| default_price_list_id |	yes | Id định danh danh sách hàng  |
| code | yes | Mã tham chiếu đến nhóm khách hàng |
| note|	no | Ghi chú cho nhóm khách hàng (nếu có) . Trường này có thể NULL |
| count_customer | yes | Mã tham chiếu đến nhóm khách hàng trong hệ thống |

**Request**

```
POST admin/customer_groups HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

{
    "customer_group": {
        "name": "New Sun group1",
        "is_default": false,
        "default_payment_term_id": 0,
        "default_payment_method_id": 0,
        "default_tax_type_id": 0,
        "default_discount_rate": 0,
        "default_price_list_id": 0,
        "note": null,
        "code": "CT200617541"
    }
}
```

**Kết quả trả về**
```
{
    "customer_group": {
        "id": 268479,
        "tenant_id": 56322,
        "created_on": "2018-07-20T07:55:43Z",
        "modified_on": "2018-07-20T07:55:43Z",
        "name": "New Sun group1",
        "name_translate": "New Sun group1",
        "status": "active",
        "is_default": false,
        "default_payment_term_id": 0,
        "default_payment_method_id": 0,
        "default_tax_type_id": 0,
        "default_discount_rate": 0,
        "default_price_list_id": 0,
        "note": null,
        "code": "CT200617541",
        "count_customer": null
    }
}
```
<a name= "put-customer_groups"></a>
## 2. Cập nhật nhóm khách hàng

Bạn có thể sửa đổi và cập nhật các thuộc tính trong nhóm khách hàng đã được tạo trước đó.

**Request**
```
PUT/admin/customer_groups/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
"{
    ""customer_group"": {
        ""id"": 268479,
        ""tenant_id"": 9287,
        ""created_on"": ""2017-06-20T02:54:06Z"",
        ""modified_on"": ""2017-06-20T02:55:06Z"",
        ""name"": ""New Sun group1"",
        ""name_translate"": ""New Sun group1"",
        ""status"": ""active"",
        ""is_default"": false,
        ""default_payment_term_id"": 0,
        ""default_payment_method_id"": 0,
        ""default_tax_type_id"": 0,
        ""default_discount_rate"": 0,
        ""default_price_list_id"": 0,
        ""note"": null,
        ""code"": ""CT200617541"",
        ""count_customer"": null
    }
}"

```
**Kết quả trả về**
```
{
    "customer_group": {
        "id": 268479,
        "tenant_id": 56322,
        "created_on": "2018-07-20T07:55:43Z",
        "modified_on": "2018-07-20T08:01:50Z",
        "name": "New Sun group1",
        "name_translate": "New Sun group1",
        "status": "active",
        "is_default": false,
        "default_payment_term_id": 0,
        "default_payment_method_id": 0,
        "default_tax_type_id": 0,
        "default_discount_rate": 0,
        "default_price_list_id": 0,
        "note": null,
        "code": "CT200617541",
        "count_customer": null
    }
}
```
**Trường hợp có lỗi**
```
{
    "data_error": {
        "status": 422,
        "errors": {
            "code": "Mã nhóm khách hàng đã tồn tại"
        }
    }
}
```
<a name= "delete-customer_groups"></a>
## 3. Xóa nhóm khách hàng
Khi nhóm khách hàng đã tồn tại trong hệ thống, bạn hoàn toàn có thể thực hiện xóa nhóm khách hàng.
**Request**
```
DELETE/admin/customer_groups/id HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**kết quả trả về**
```
200 OK
```
<a name= "get-customer_groups_id"></a>
## 4. Lấy 1 nhóm khách hàng theo id
**Request**
```
GET/admin/customer_groups/id HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "customer_group": {
        "id": 268512,
        "tenant_id": 56322,
        "created_on": "2018-07-20T08:13:31Z",
        "modified_on": "2018-07-20T08:13:31Z",
        "name": "New Sun group",
        "name_translate": "New Sun group",
        "status": "deleted",
        "is_default": false,
        "default_payment_term_id": 0,
        "default_payment_method_id": 0,
        "default_tax_type_id": 0,
        "default_discount_rate": 0,
        "default_price_list_id": 0,
        "note": null,
        "code": "CT200617542",
        "count_customer": null
    }
}
```
<a name= "get-customer_groups"></a>
## 5. Lấy toàn bộ nhóm khách hàng
**Request**
```
GET/admin/customer_groups HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 3,
        "page": 1,
        "limit": 250
    },
    "customer_groups": [
        {
            "id": 226529,
            "tenant_id": 56322,
            "created_on": "2018-05-08T02:07:59Z",
            "modified_on": "2018-06-22T04:23:27Z",
            "name": "VIP",
            "name_translate": "Vip",
            "status": "active",
            "is_default": true,
            "default_payment_term_id": 0,
            "default_payment_method_id": 0,
            "default_tax_type_id": 0,
            "default_discount_rate": 0,
            "default_price_list_id": 0,
            "note": null,
            "code": "VIP",
            "count_customer": 0
        },
        {
            "id": 226528,
            "tenant_id": 56322,
            "created_on": "2018-05-08T02:07:59Z",
            "modified_on": "2018-06-22T03:31:30Z",
            "name": "WHOLESALE",
            "name_translate": "Bán buôn",
            "status": "active",
            "is_default": true,
            "default_payment_term_id": 0,
            "default_payment_method_id": 0,
            "default_tax_type_id": 0,
            "default_discount_rate": 0,
            "default_price_list_id": 0,
            "note": null,
            "code": "BANBUON",
            "count_customer": 0
        },
        {
            "id": 226527,
            "tenant_id": 56322,
            "created_on": "2018-05-08T02:07:59Z",
            "modified_on": "2018-05-08T02:07:59Z",
            "name": "RETAIL",
            "name_translate": "Bán lẻ",
            "status": "active",
            "is_default": true,
            "default_payment_term_id": null,
            "default_payment_method_id": null,
            "default_tax_type_id": null,
            "default_discount_rate": null,
            "default_price_list_id": null,
            "note": null,
            "code": "BANLE",
            "count_customer": 10
        }
    ]
}
```
<a name= "get-customer_groups?"></a>
## 1.6 Lấy nhóm khách hàng theo bộ lọc
**Request**
```
GET /admin/customer_groups? HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
param: status = (active)
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 3,
        "page": 1,
        "limit": 250
    },
    "customer_groups": [
        {
            "id": 226529,
            "tenant_id": 56322,
            "created_on": "2018-05-08T02:07:59Z",
            "modified_on": "2018-06-22T04:23:27Z",
            "name": "VIP",
            "name_translate": "Vip",
            "status": "active",
            "is_default": true,
            "default_payment_term_id": 0,
            "default_payment_method_id": 0,
            "default_tax_type_id": 0,
            "default_discount_rate": 0,
            "default_price_list_id": 0,
            "note": null,
            "code": "VIP",
            "count_customer": 0
        },
        {
            "id": 226528,
            "tenant_id": 56322,
            "created_on": "2018-05-08T02:07:59Z",
            "modified_on": "2018-06-22T03:31:30Z",
            "name": "WHOLESALE",
            "name_translate": "Bán buôn",
            "status": "active",
            "is_default": true,
            "default_payment_term_id": 0,
            "default_payment_method_id": 0,
            "default_tax_type_id": 0,
            "default_discount_rate": 0,
            "default_price_list_id": 0,
            "note": null,
            "code": "BANBUON",
            "count_customer": 0
        },
        {
            "id": 226527,
            "tenant_id": 56322,
            "created_on": "2018-05-08T02:07:59Z",
            "modified_on": "2018-05-08T02:07:59Z",
            "name": "RETAIL",
            "name_translate": "Bán lẻ",
            "status": "active",
            "is_default": true,
            "default_payment_term_id": null,
            "default_payment_method_id": null,
            "default_tax_type_id": null,
            "default_discount_rate": null,
            "default_price_list_id": null,
            "note": null,
            "code": "BANLE",
            "count_customer": 10
        }
    ]
}
```
