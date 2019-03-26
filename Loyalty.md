# Loyalty

Tích điểm là 

[1. Thẻ tích điểm](#loyalty_cards)

  [1.1 Tạo thẻ tích điểm](#add-loyalty_cards)

  [1.2 Lấy tất cả thẻ tích điểm ](#get-loyalty_cards)

  [1.3 Sửa một thẻ tích điểm](#put-loyalty_cards_id)

  [1.4 Xóa một thẻ tích điểm](#delete-loyalty_cards_id)
  
[2. Thiết lập](#loyalty_settings)

  [2.1 Lấy tất cả thiết lập thẻ tích điểm](#get-loyalty_settings)

  [2.2 Sửa thiết lập thẻ tích điểm ](#put-shipping_costs_id)

3. Khách hàng

  [3.1 Lấy khách hàng có thẻ tích điểm](#get-loyalty_customers/customers/{id})
  
  [3.2 Lấy khách hàng có thẻ tích điểm](#get-admin/loyalty_customers?query,limit,page)

  [3.3 Lấy lịch sử khách hàng dùng thẻ tích điểm](#get-loyalty_customers/customers/{id}/loyalty_histories)

4. Tích điểm đổi quà

5. Chiết khấu tích điểm

**Các tham số**
<a name= "loyalty_cards"></a>
## Thẻ tích điểm

<a name= "add-loyalty_cards"></a>
### 1.1 Tạo thẻ tích điểm
**Request**

```
POST admin/loyalty_cards HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "loyalty_card": {
    "name": "chung1",
    "discount_type": "percent",
    "discount_value": 10,
    "amount": 2000000,
    "amount_condition": 200000,
    "date_time_type": "day",
    "date_time_value": 10,
    "status": "active"
  }
}
```
**Kết quả trả về**
```
{
    "loyalty_card": {
        "id": 2316,
        "tenant_id": 56322,
        "name": "chung1",
        "discount_type": "percent",
        "discount_value": 10,
        "amount": 2000000,
        "amount_condition": 200000,
        "date_time_type": "day",
        "date_time_value": 10,
        "status": "active",
        "created_on": "2018-07-31T09:20:14Z",
        "modified_on": "2018-07-31T09:20:14Z",
        "note": null
    }
}
```
<a name= "put-shipping_costs_id"></a>
### 1.2 Lấy tất cả thẻ tích điểm
**Request**

```
GET admin/loyalty_cards HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 1,
        "page": 1,
        "limit": 20
    },
    "loyalty_cards": [
        {
            "id": 2315,
            "tenant_id": 56322,
            "name": "chung",
            "discount_type": "percent",
            "discount_value": 10,
            "amount": 1000000,
            "amount_condition": 100000,
            "date_time_type": "day",
            "date_time_value": 10,
            "status": "active",
            "created_on": "2018-07-31T07:01:27Z",
            "modified_on": "2018-07-31T07:01:27Z",
            "note": null
        }
    ]
}
```
<a name= "put-loyalty_cards_id"></a>
### 1.3 Sửa một thẻ tích điểm
**Request**

```
PUT admin/loyalty_cards/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "loyalty_card": {
    "name": "chung1",
    "discount_type": "money",
    "discount_value": 10,
    "amount": 2000000,
    "amount_condition": 200000,
    "date_time_type": "month",
    "date_time_value": 10,
    "status": "active"
  }
}
```
**Kết quả trả về**
```
{
    "loyalty_card": {
        "id": 2316,
        "tenant_id": 56322,
        "name": "chung1",
        "discount_type": "money",
        "discount_value": 10,
        "amount": 2000000,
        "amount_condition": 200000,
        "date_time_type": "day",
        "date_time_value": 10,
        "status": "active",
        "created_on": "2018-07-31T09:20:14Z",
        "modified_on": "2018-07-31T09:24:00Z",
        "note": null
    }
}
```
**Trường hợp có lỗi*
```
{
    "error": {
        "message": "Không được cập nhật hạng thẻ cùng mức doanh thu điều kiện"
    }
}
```
<a name= "delete-loyalty_cards_id"></a>
### 1.4 Xóa một thẻ tích điểm
**Request**

```
DELETE admin/loyalty_cards/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
Status 200 OK
```
<a name= "loyalty_settings"></a>
## 2. Thiết lập

<a name= "get-loyalty_settings"></a>
### 2.1 Lấy tất cả thiết lập thẻ tích điểm
**Request**

```
GET admin/loyalty_settings HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
Status 200 OK
```

<a name= "put-shipping_costs_id"></a>
### 2.2 Sửa thiết lập thẻ tích điểm 
**Request**

```
PUT admin/loyalty_settings HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```

```

## 3. Khách hàng

### 3.1 Lấy khách hàng có thẻ tích điểm
**Request**

```
GET admin/loyalty_customers/customers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```

```

### 3.2 Lấy khách hàng có thẻ tích điể theo bộ lọc
**Request**

```
GET admin/loyalty_customers/customers/{id}/loyalty_histories HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```

```
### 3.3 Lấy lịch sử khách hàng dùng thẻ tích điểm
**Request**

```
GET admin/loyalty_customers/customers/{id}/loyalty_histories HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
Status 200 OK
```
