# Phí vận chuyển

[1. Tạo đơn phí ship hàng](#add-shipping_costs)

[2. Sửa một đơn phí ship hàng ](#put-shipping_costs_id)

[3. Lấy ra một đơn phí ship hàng](#get-shipping_costs_id)

[4. Xóa một đơn phí ship hàng](#delete-shipping_costs_id)


**Các tham số**

<a name= "add-shipping_costs"></a>
## 1. Tạo đơn phí ship hàng
**Request**

```
POST /admin/shipping_costs HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

{
  "shipping_cost": {
    "id": 3,
    "name": "trăm tỉ mới chuyển 3",
    "base_on": "weight",
    "lower_limit": 1,
    "upper_limit": null,
    "cost": 100
  }
}
```
**Kết quả trả về**
```
{
    "shipping_cost": {
        "id": 1438,
        "tenant_id": 21406,
        "name": "trăm tỉ mới chuyển 3",
        "base_on": "weight",
        "lower_limit": 1,
        "upper_limit": null,
        "cost": 100,
        "created_on": "2018-07-30T09:50:06Z",
        "modified_on": "2018-07-30T09:50:06Z",
        "status": "active"
    }
}
```
<a name= "put-shipping_costs_id"></a>
## 2. Sửa đơn phí ship hàng
**Request**

```
PUT /admin/shipping_costs/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "shipping_cost": {
    "id": 3,
    "name": "trăm tỉ mới chuyển 3",
    "base_on": "weight",
    "lower_limit": 1,
    "upper_limit": null,
    "cost": 100
  }
}
```
**Kết quả trả về**
```
{
    "shipping_cost": {
        "id": 1438,
        "tenant_id": 21406,
        "name": "trăm tỉ mới chuyển 3",
        "base_on": "weight",
        "lower_limit": 1,
        "upper_limit": null,
        "cost": 100,
        "created_on": "2018-07-30T09:50:06Z",
        "modified_on": "2018-07-30T09:59:58Z",
        "status": "active"
    }
}
```
<a name= "get-shipping_costs_id"></a>
## 3. Lấy đơn phí ship hàng
**Request**

```
GET /admin/shipping_costs/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "shipping_cost": {
        "id": 1438,
        "tenant_id": 21406,
        "name": "trăm tỉ mới chuyển 3",
        "base_on": "weight",
        "lower_limit": 1,
        "upper_limit": null,
        "cost": 100,
        "created_on": "2018-07-30T09:50:06Z",
        "modified_on": "2018-07-30T09:59:58Z",
        "status": "active"
    }
}
```
<a name= "delete-shipping_costs_id"></a>
## 4. Xóa đơn phí ship hàng
**Request**

```
DELETE /admin/shipping_costs/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
Status 200 OK
```

