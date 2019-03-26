# Nhóm nhà cung cấp

Một tài nguyên Supplier đại diện cho một đơn vị cung cấp sản phẩm cho Shop. Tài khoản Supplier lưu trữ thông tin liên hệ của nhà cung cấp giúp cho chủ shop không phải khai báo thông tin nhà cung cấp mỗi khi tạo đơn hàng. 
 
Chủ shop có thể quản lý nhà cung cấp theo nhóm để tiện áp dụng các phương thức thanh toán, kế hoạch nhập hàng. 
Chú ý: Mỗi nhà cung cấp chỉ có thể nằm trong một nhóm nhà cung cấp.

[1. Tạo nhóm nhà cung cấp](#add-supplier_groups)

[2. Cập nhật nhóm nhà cung cấp](#put-supplier_groups)

[3. Xóa nhóm nhà cung cấp](#delete-supplier_groups)

[4. Lấy 1 nhóm nhà cung cấp theo id](#get-supplier_groups_id)

[5. Lấy toàn bộ nhóm nhà cung cấp](#get-supplier_groups)

[6. Lấy nhóm nhà cung cấp theo bộ lọc](#get-supplier_groups?)

[7. Lấy mã code nhà cung cấp](#get-supplier_groups_codes)

<a name="#add-supplier_groups"></a>
## 1. Tạo mới nhóm nhà cung cấp
Bắt đầu với việc tạo nhóm nhà cung cấp, bạn sẽ đưa ra những tùy chọn nhóm để thêm nhà cung cấp vào danh sách.

**Các tham số**

| Tham số | Bắt buộc | Mô tả |
| ------------- |:-------------:|:-------------|
| Supplier_group.name | yes | Tên nhóm nhà cung cấp, tên nhóm không được trùng với nhóm đã có trước đó  |
| Supplier_group.is_default |	yes | |
| Supplier_group.code | yes | Mã tham chiếu đến nhóm nhà cung cấp trong hệ thống |
| Supplier_group.note| no | Ghi chú, mô tả cho nhóm nhà cung cấp (nếu có) . Trường này có thể NULL |
| id |	yes | Id định danh cho nhóm nhà cung cấp trong hệ thống. Trường không bắt buộc người dùng điền, tự sinh dưới hệ thống khi để trống. |
| tenant_id |	yes | id định danh cho nhân viên thực hiện tạo nhóm nhà cung cấp  |
| created_on |	yes | Thời gian nhóm nhà cung cấp được tạo. API trả về kết quả theo định dạng chuẩn ISO 8601. |
| modified_on |	yes | Thời gian nhóm nhà cung cấp được chỉnh sửa. API trả về kết quả theo định dạng chuẩn ISO 8601. |
| name | yes | Tên nhóm nhà cung cấp, tên nhóm không được trùng với nhóm đã có trước đó |
| name_translate | no | Tên nhóm nhà cung cấp |
| status |	yes | Trạng thái nhóm nhà cung cấp |
| is_default | yes |  |
| code | yes | Mã tham chiếu đến nhóm nhà cung cấp  |
| note| no | Ghi chú cho nhóm nhà cung cấp (nếu có) . Trường này có thể NULL |
| count_supplier | yes | Mã tham chiếu đến nhóm nhà cung cấp trong hệ thống |

**Request**

```
POST/admin/supplier_groups HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
    "supplier_group": {
        "name": "New Sun group1",
        "is_default": false,
        "note": null,
        "code": "ST200617541"
    }
}

```

**Kết quả trả về**
```
{
    "supplier_group": {
        "id": 270323,
        "tenant_id": 56322,
        "type": "supplier",
        "created_on": "2018-07-23T02:39:39Z",
        "modified_on": "2018-07-23T02:39:39Z",
        "name": "New Sun group1",
        "name_translate": "New Sun group1",
        "status": "active",
        "is_default": false,
        "count_supplier": 0,
        "note": null,
        "code": "ST200617541"
    }
}
```
<a name="#put-supplier_groups"></a>
## 2. Cập nhật nhóm nhà cung cấp

Bạn có thể sửa đổi và cập nhật các thuộc tính trong nhóm nhà cung cấp đã được tạo trước đó.

**Request**
```
PUT/admin/supplier_groups/id HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
    "supplier_group": {
        "id": 14379,
        "tenant_id": 9287,
        "created_on": "2017-06-20T02:54:06Z",
        "modified_on": "2017-06-20T02:55:06Z",
        "name": "New Sun group1",
        "name_translate": "New Sun group1",
        "status": "active",
        "is_default": false,
        "note": null,
        "code": "CT200617541",
        "count_supplier": null
    }
}

```
**Kết quả trả về**
```
{
    "supplier_group": {
        "id": 270323,
        "tenant_id": 56322,
        "type": "supplier",
        "created_on": "2018-07-23T02:39:39Z",
        "modified_on": "2018-07-23T02:53:28Z",
        "name": "New Sun group1",
        "name_translate": "New Sun group1",
        "status": "active",
        "is_default": false,
        "count_supplier": 0,
        "note": null,
        "code": "CT200617541"
    }
}
```
<a name="#delete-supplier_groups"></a>
## 3. Xóa nhóm nhà cung cấp
Khi nhóm nhà cung cấp đã tồn tại trong hệ thống, bạn hoàn toàn có thể thực hiện xóa nhóm nhà cung cấp.

**Request**
```
DELETE/admin/supplier_groups/id
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
Status: 200 OK
```
<a name="#get-supplier_groups_id"></a>
## 4. Lấy 1 nhóm nhà cung cấp theo id
**Request**
```
GET/admin/supplier_groups/id
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "supplier_group": {
        "id": 270323,
        "tenant_id": 56322,
        "type": "supplier",
        "created_on": "2018-07-23T02:39:39Z",
        "modified_on": "2018-07-23T02:53:28Z",
        "name": "New Sun group1",
        "name_translate": "New Sun group1",
        "status": "deleted",
        "is_default": false,
        "count_supplier": 0,
        "note": null,
        "code": "CT200617541"
    }
}
```
<a name="#get-supplier_groups"></a>
## 5. Lấy toàn bộ nhóm nhà cung cấp
**Request**
```
GET/admin/supplier_groups
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
    "supplier_groups": [
        {
            "id": 266817,
            "tenant_id": 56322,
            "type": "supplier",
            "created_on": "2018-07-18T08:17:45Z",
            "modified_on": "2018-07-18T08:17:45Z",
            "name": "VIP1",
            "name_translate": "VIP1",
            "status": "active",
            "is_default": false,
            "count_supplier": 1,
            "note": null,
            "code": "ST1807184"
        },
        {
            "id": 252430,
            "tenant_id": 56322,
            "type": "supplier",
            "created_on": "2018-06-22T07:42:16Z",
            "modified_on": "2018-06-25T07:07:49Z",
            "name": "VIP",
            "name_translate": "VIP",
            "status": "active",
            "is_default": false,
            "count_supplier": 0,
            "note": null,
            "code": "ST2206182"
        },
        {
            "id": 226526,
            "tenant_id": 56322,
            "type": "supplier",
            "created_on": "2018-05-08T02:07:57Z",
            "modified_on": "2018-05-08T02:07:57Z",
            "name": "DEFAULT",
            "name_translate": "Khác",
            "status": "active",
            "is_default": true,
            "count_supplier": 0,
            "note": null,
            "code": "MACDINH"
        }
    ]
}
```
<a name="#get-supplier_groups?"></a>
## 6. Lấy nhóm nhà cung cấp theo bộ lọc
**Request**
```
GET/admin/supplier_groups?
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

statuses=(active,deleted)
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 0,
        "page": 1,
        "limit": 250
    },
    "supplier_groups": []
}
```
<a name="#get-supplier_groups_codes"></a>
## 7. Lấy mã code nhà cung cấp
**Request**
```
GET/admin/supplier_groups/codes
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "partner_group_code": {
        "tenant_id": 56322,
        "code": "ST2307186"
    }
}
```
