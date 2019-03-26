# OrderReturn
Trả hàng cho khách hàng được thực hiện khi một đơn hàng đã được tạo và hàng hóa đã được xuất kho trên hệ thống và khách hàng có yêu cầu đổi sản phẩm hoặc hủy sản phẩm.
OrderReturn chỉ được thực hiện khi có đơn đặt hàng thành công.

[1. Thêm 1 đơn trả hàng](#add-order_returns)

[2. Tạo mới code cho đơn trả hàng](#add-order_returns_code)

[3. Lấy một đơn trả hàng theo id](#get-order_returns_id)

[4. Lấy đơn trả hàng theo bộ lọc](#get-order_returns?)

[5. Thêm đơn hàng hoàn tiền theo id](#add-order_returns/id/refunds)

[6. TLấy 1 đơn hàng hoàn tiền theo id](#aget-order_returns/id/refunds/{refundId})

<a name="add-order_returns"></a>
## 1. Thêm 1 đơn trả hàng

**Các tham số**
| Tham số | Bắt buộc | Mô tả |
| ------------- |:-------------|:-------------|
| OrderReturn.id | no | Mã tham chiếu đơn trả hàng |

| OrderReturn.tenant_id | no |  |

| OrderReturn.location_id | no |  |

| OrderReturn.code | no | Mã tham chiếu của khách hàng có đơn hàng |

| OrderReturn.account_id | no | Id định danh tài khoản nhân viên dùng để tạo đơn hàng |

| OrderReturn.order_id | yes | Id định danh đơn đặt hàng  |

| OrderReturn.order_code | no | Mã tham chiếu đến đơn đặt hàng |

| OrderReturn.customer_id | no | Id định danh khách hàng muốn trả hàng |

| OrderReturn.billing_address | no | Địa chỉ hóa đơn đơn hàng |

| OrderReturn.contact_id | no | Id định danh cho liên lạc với khách hàng |

| OrderReturn.reference| no |  |

| OrderReturn.status| no | Trạng thái đơn trả hàng |
| OrderReturn.refund_status| no | Trạng thái thanh toán trả  |
| OrderReturn.total_amount | no | Tổng lượng hàng trong đơn đặt hàng |
| OrderReturn.issued_on | no | Thời gian Order được tạo. API trả về kết quả theo định dạng chuẩn ISO 8601. Thuộc tính này được tạo tự động và không thể chỉnh sửa. Nếu bạn import Order từ một hệ thống khác vào Sapo thì hãy sử dụng thuộc tính có thể ghi processed_on để xác định thời gian Order được xử lý. |
| OrderReturn.received_on | no |  |
| OrderReturn.created_on| no |  |
| OrderReturn.refund_status| no |  |
| OrderReturn.modified_on | no |  |
| OrderReturn.line_items | yes |  |

**Request**
```
POST /admin/order_returns HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

{
  "order_return": {
    "id": 1635,
    "tenant_id": 77,
    "location_id": 81,
    "code": "SR1810161",
    "account_id": 33,
    "order_id": 7859,
    "order_code": null,
    "customer_id": 10080,
    "billing_address": null,
    "contact_id": null,
    "reference": null,
    "note": null,
    "status": "returning",
    "refund_status": "partial",
    "total_amount": 10000,
    "issued_on": "2016-10-18T08:54:16Z",
    "received_on": null,
    "created_on": "2016-10-18T08:54:16Z",
    "modified_on": "2016-10-18T08:54:43Z",
    "line_items": [
      {
        "id": 2074,
        "product_id": 27970,
        "product_name": "Hoa lay ơn trắng",
        "variant_id": 34198,
        "variant_name": "Hoa lay ơn trắng",
        "note": null,
        "quantity": 1,
        "price": 10000,
        "is_composite": false,
        "is_freeform": false,
        "line_amount": 10000,
        "created_on": "2016-10-18T08:54:16Z",
        "modified_on": "2016-10-18T08:54:16Z"
      }
    ]
  }
}
```
**Kết quả trả về**
```
{
  "order_return": {
    "id": 1635,
    "tenant_id": 77,
    "location_id": 81,
    "code": "SR1810161",
    "account_id": 33,
    "order_id": 7859,
    "order_code": null,
    "customer_id": 10080,
    "billing_address": null,
    "contact_id": null,
    "reference": null,
    "note": null,
    "status": "returning",
    "refund_status": "partial",
    "total_amount": 10000,
    "issued_on": "2016-10-18T08:54:16Z",
    "received_on": null,
    "created_on": "2016-10-18T08:54:16Z",
    "modified_on": "2016-10-18T08:54:43Z",
    "line_items": [
      {
        "id": 2074,
        "product_id": 27970,
        "product_name": "Hoa lay ơn trắng",
        "variant_id": 34198,
        "variant_name": "Hoa lay ơn trắng",
        "note": null,
        "quantity": 1,
        "price": 10000,
        "is_composite": false,
        "is_freeform": false,
        "line_amount": 10000,
        "created_on": "2016-10-18T08:54:16Z",
        "modified_on": "2016-10-18T08:54:16Z"
      }
    ]
  }
}
```
**Trường hợp có lỗi**
```
{
    "data_error": {
        "status": 422,
        "errors": {
            "line_items[0].order_line_item_id": "may not be null"
        }
    }
}
```
<a name="add-order_returns_code"></a>
## 2. Tạo mới code cho đơn trả hàng
```
POST /admin/order_returns/codes HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "order_return_code": {
        "tenant_id": 56322,
        "code": "SR2906182"
    }
}
```
<a name="get-order_returns_id"></a>
## 3. Lấy một đơn trả hàng theo id
```
GET /admin/order_returns/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "order_return": {
        "id": 198300,
        "tenant_id": 56322,
        "location_id": 58369,
        "code": "SR2906181",
        "account_id": 72098,
        "order_id": 14549649,
        "order_code": "SO1806182",
        "customer_id": 3335156,
        "billing_address": {
            "id": 17662926,
            "label": null,
            "first_name": "Thoa",
            "last_name": "Đào",
            "address1": "Trương Định",
            "address2": null,
            "email": null,
            "phone_number": "01647158965",
            "country": "Việt Nam",
            "city": "Hà Nội",
            "district": "Quận Hoàng Mai",
            "zip_code": null,
            "full_address": null
        },
        "contact_id": null,
        "reference": null,
        "note": null,
        "status": "returning",
        "refund_status": "unpaid",
        "total_amount": 1999980,
        "total_quantity": null,
        "issued_on": "2018-06-29T03:49:26Z",
        "received_on": null,
        "created_on": "2018-06-29T03:49:36Z",
        "modified_on": "2018-06-29T03:49:36Z",
        "line_items": [
            {
                "id": 371591,
                "order_line_item_id": 22887065,
                "product_id": 3262676,
                "product_name": "Áo khoác có mũ Bellfield",
                "variant_id": 4653239,
                "variant_name": "Áo khoác có mũ Bellfield",
                "note": null,
                "quantity": 2,
                "price": 999990,
                "is_composite": false,
                "is_freeform": false,
                "line_amount": 1999980,
                "created_on": "2018-06-29T03:49:36Z",
                "modified_on": "2018-06-29T03:49:36Z",
                "sku": "SP3",
                "barcode": "SP3",
                "unit": null,
                "variant_options": "Mặc định"
            }
        ],
        "refunds": [],
        "reason_id": null
    }
}
```
**Trường hợp có lỗi**
```
{
    "error": {
        "message": "Không tìm thấy đơn trả"
    }
}
```
<a name="get-order_returns?"></a>
## 4. Lấy đơn trả hàng theo bộ lọc
```
GET /admin/order_returns HTTP/1.1
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
    "order_returns": [
        {
            "id": 198300,
            "tenant_id": 56322,
            "location_id": 58369,
            "code": "SR2906181",
            "account_id": 72098,
            "order_id": 14549649,
            "order_code": "SO1806182",
            "customer_id": 3335156,
            "billing_address": {
                "id": 17662926,
                "label": null,
                "first_name": "Thoa",
                "last_name": "Đào",
                "address1": "Trương Định",
                "address2": null,
                "email": null,
                "phone_number": "01647158965",
                "country": "Việt Nam",
                "city": "Hà Nội",
                "district": "Quận Hoàng Mai",
                "zip_code": null,
                "full_address": null
            },
            "contact_id": null,
            "reference": null,
            "note": null,
            "status": "returned",
            "refund_status": "unpaid",
            "total_amount": 1999980,
            "total_quantity": null,
            "issued_on": "2018-06-29T03:49:26Z",
            "received_on": "2018-07-02T02:46:26Z",
            "created_on": "2018-06-29T03:49:36Z",
            "modified_on": "2018-07-02T02:46:26Z",
            "line_items": [
                {
                    "id": 371591,
                    "order_line_item_id": 22887065,
                    "product_id": 3262676,
                    "product_name": "Áo khoác có mũ Bellfield",
                    "variant_id": 4653239,
                    "variant_name": "Áo khoác có mũ Bellfield",
                    "note": null,
                    "quantity": 2,
                    "price": 999990,
                    "is_composite": false,
                    "is_freeform": false,
                    "line_amount": 1999980,
                    "created_on": "2018-06-29T03:49:36Z",
                    "modified_on": "2018-06-29T03:49:36Z",
                    "sku": "SP3",
                    "barcode": "SP3",
                    "unit": null,
                    "variant_options": "Mặc định"
                }
            ],
            "refunds": [],
            "reason_id": null
        }
    ]
}
```
**Trường hợp có lỗi
```
{
    "metadata": {
        "total": 0,
        "page": 1,
        "limit": 250
    },
    "order_returns": []
}
```
<a name="add-order_returns/id/refunds"></a>
## 5. Thêm đơn hàng hoàn tiền theo id

Trong trường hợp đơn hàng đã được khách hàng thanh 
```
POST /admin/order_returns/{id}/refunds HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Request**
```
{
  "refund": {
    "id": 6,
    "tenant_id": 77,
    "location_id": 81,
    "customer_id": 10080,
    "order_return_id": 39,
    "account_id": 0,
    "amount": 10000,
    "reference": null,
    "paid_on": "2016-06-30T11:06:29Z",
    "currency_id": 7016,
    "exchange_rate": 0,
    "status": "active",
    "created_on": "2016-06-30T11:06:29Z",
    "modified_on": "2016-06-30T11:06:29Z"
  }
}
```
**Kết quả trả về**
```
{
    "refund": {
        "id": 159694,
        "tenant_id": 56322,
        "location_id": 58369,
        "customer_id": 4128452,
        "order_return_id": 212580,
        "order_id": 212580,
        "payment_method_id": 220256,
        "account_id": 72098,
        "amount": 10000,
        "reference": null,
        "paid_on": "2016-06-30T11:06:29Z",
        "currency_id": null,
        "exchange_rate": null,
        "status": "active",
        "created_on": "2018-07-20T08:59:15Z",
        "modified_on": "2018-07-20T08:59:15Z"
    }
}
```
<a name="get-order_returns/id/refunds/{refundId}"></a>
## 6. Lấy 1 đơn hàng hoàn tiền theo id
```
GET /admin/order_returns/{id}/refunds/{refundId} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "refund": {
        "id": 159694,
        "tenant_id": 56322,
        "location_id": 58369,
        "customer_id": 0,
        "order_return_id": 212580,
        "order_id": 15606631,
        "payment_method_id": 220256,
        "account_id": 72098,
        "amount": 10000,
        "reference": null,
        "paid_on": "2016-06-30T11:06:29Z",
        "currency_id": null,
        "exchange_rate": null,
        "status": "active",
        "created_on": "2018-07-20T08:59:15Z",
        "modified_on": "2018-07-20T08:59:15Z"
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
