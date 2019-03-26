
[1. Nhập hàng](#purchase_orders)

   [1.1 Thêm mới đơn nhập hàng](#add-purchase_orders)

   [1.2 Lấy đơn nhập hàng theo bộ lọc?](#get-purchase_orders?)

   [1.3 Lấy một đơn nhập hàng](#get-purchase_orders_id)

   [1.4 Sinh mã code đơn nhập hàng](#purchase_orders_codes)

   [1.5 Chuyển trạng thái từ draft sang active](#purchase_orders_id_status)

   [1.6 Hủy một đơn nhập](#cancel-purchase_orders_id_status)

   [1.7 Cập nhật một đơn nhập hàng](#put-purchase_orders_id)

   [1.8 Thêm mới một item](#put-purchase_orders_id_line_items)
   
[2. Hóa đơn nhập](#purchase_orders_bill)

   [2.1 Thêm mới 1 hoá đơn nhập hàng](#add-purchase_orders_bill)

   [2.2 Lấy ra thông tin bill](#get-purchase_orders_bill_id)

   [2.3 Cập nhật thông tin](#put-purchase_orders_bill_id)

   [2.4 Hủy 1 phiếu bill](#cancel-purchase_orders_bill_id)

   [2.5 Lấy bill theo fillter](#get-purchase_orders_bill?)
   
[3. Thanh toán cho hóa đơn nhập](#purchase_orders_bill_payment)

   [3.1 Thêm mới một phiếu thanh toán cho hóa đơn nhập](#get-purchase_orders_bill_payment)

   [3.2 Lấy một phiếu thanh toán hóa đơn nhập](#get-purchase_orders_bill_payment_id)

   [3.3 Hủy phiếu thanh toán](#cancel-purchase_orders_bill_payments)
   
[4. Nhập kho](#purchase_orders_procurements)

   [4.1 Thêm mới phiếu nhập kho](#add-purchase_orders_id_procurements)

   [4.2 Cập nhật một phiếu nhập kho](#get-purchase_orders_id_procurements)

   [4.3 Hủy 1 phiếu nhập kho](#cancel-purchase_orders_id_procurements)

   [4.4 Lấy phiếu nhập kho theo bộ lọc](#get-purchase_orders_id_procurements?)
   
 [5. Trả hàng](#purchase_order_returns) 

   [5.1 Thêm mới một đơn trả hàng](#add-purchase_order_returns)  

Chủ shop quản lý nhập hàng từ các nguồn khác nhau,

**Các tham số**

<a name= "purchase_orders"></a>
# 1. Nhập hàng 

<a name= "add-purchase_orders"></a>
## 1.1 Thêm mới đơn nhập hàng]

**Request**

```
POST /admin/purchase_orders HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "supplier_id": 42,
  "tags": [
    "hoinx100",
    "hoinx200"
  ],
  "line_items": [
    {
      "product_id": 9195,
      "variant_id": 12099,
      "quantity": 11,
      "price": 1000,
      "base_price": 1000
    }
  ]
}
```
**Kết quả trả về**
```
{
  "purchase_order": {
    "id": 68,
    "tenant_id": 77,
    "location_id": 8070,
    "account_id": 33,
    "stock_location_id": 8070,
    "created_on": "2016-06-03T04:53:48Z",
    "modified_on": "2016-06-03T04:53:48Z",
    "due_on": "2016-06-03T04:53:47Z",
    "received_on": "2016-06-03T04:53:47Z",
    "supplier_id": 42,
    "supplier_address_id": 3700,
    "email": null,
    "phone_number": null,
    "currency_id": 7016,
    "exchange_rate": 1,
    "price_list_id": 7179,
    "tax_treatment": "exclusive",
    "sub_total": 11000,
    "total_tax": 157300,
    "total_amount": 168300,
    "status": "draft",
    "billing_status": "unbilled",
    "payment_status": "unpaid",
    "procurement_status": "unreceived",
    "note": null,
    "code": "PO0306161",
    "tags": null,
    "line_items": [
      {
        "id": 56,
        "created_on": "2016-06-03T04:53:48Z",
        "modified_on": "2016-06-03T04:53:48Z",
        "product_id": 9195,
        "product_name": null,
        "variant_id": 12099,
        "variant_name": null,
        "quantity": 11,
        "base_price": 1000,
        "price": 1000,
        "tax_type_id": 1013,
        "tax_rate_override": null,
        "tax_rate": 14.3,
        "sub_amount": 11000,
        "tax_amount": 157300,
        "line_amount": 168300,
        "freeform": false,
        "note": null
      }
    ],
    "procurements": []
  }
}
```
<a name= "get-purchase_orders?"></a>
## 1.2 Lấy đơn nhập hàng theo bộ lọc

**Request**
```
GET /admin/purchase_orders HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
param = 3
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 368,
        "page": 1,
        "limit": 3
    },
    "purchase_orders": [
        {
            "id": 534296,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "stock_location_id": 22322,
            "created_on": "2018-08-04T02:34:49Z",
            "modified_on": "2018-08-04T02:37:20Z",
            "due_on": "2018-08-04T02:34:48Z",
            "received_on": "2018-08-04T02:37:10Z",
            "supplier_id": 1401953,
            "supplier_address": {
                "id": 19581903,
                "label": null,
                "first_name": null,
                "last_name": null,
                "address1": "1234567",
                "address2": null,
                "email": null,
                "phone_number": null,
                "country": "Việt Nam",
                "city": null,
                "district": null,
                "zip_code": null
            },
            "billing_address": {
                "id": 19581904,
                "label": null,
                "first_name": null,
                "last_name": null,
                "address1": "1234567",
                "address2": null,
                "email": null,
                "phone_number": null,
                "country": "Việt Nam",
                "city": null,
                "district": null,
                "zip_code": null
            },
            "contact_id": 0,
            "email": null,
            "phone_number": "01685742369",
            "currency_id": 21407,
            "exchange_rate": 1,
            "price_list_id": 60862,
            "tax_treatment": "exclusive",
            "sub_total": 1950000,
            "total_tax": 195000,
            "total_amount": 2145000,
            "status": "received",
            "billing_status": "billed",
            "payment_status": "paid",
            "procurement_status": "received",
            "note": null,
            "reference": null,
            "code": "PO0408181",
            "tags": null,
            "line_items": [
                {
                    "id": 3040771,
                    "created_on": "2018-08-04T02:34:49Z",
                    "modified_on": "2018-08-04T02:34:49Z",
                    "product_id": 3687223,
                    "variant_id": 5284103,
                    "title": "Product Q - vàng - 1 - thùng",
                    "quantity": 15,
                    "base_price": 50000,
                    "price": 50000,
                    "tax_type_id": null,
                    "tax_rate_override": 10,
                    "tax_rate": 10,
                    "sub_amount": 750000,
                    "tax_amount": 75000,
                    "line_amount": 825000,
                    "is_freeform": false,
                    "note": null
                },
                {
                    "id": 3040772,
                    "created_on": "2018-08-04T02:34:49Z",
                    "modified_on": "2018-08-04T02:34:49Z",
                    "product_id": 1015515,
                    "variant_id": 1375790,
                    "title": "Quần áo Quảng Châu -1",
                    "quantity": 15,
                    "base_price": 80000,
                    "price": 80000,
                    "tax_type_id": null,
                    "tax_rate_override": 10,
                    "tax_rate": 10,
                    "sub_amount": 1200000,
                    "tax_amount": 120000,
                    "line_amount": 1320000,
                    "is_freeform": false,
                    "note": null
                }
            ],
            "procurements": [
                {
                    "id": 530115,
                    "location_id": 22322,
                    "tenant_id": 21406,
                    "purchase_order_id": 534296,
                    "supplier_id": 0,
                    "currency_id": 0,
                    "code": "PR0408181",
                    "purchase_order_code": null,
                    "created_on": "2018-08-04T02:37:07Z",
                    "modified_on": "2018-08-04T02:37:07Z",
                    "received_on": "2018-08-04T02:37:10Z",
                    "account_id": 25153,
                    "note": null,
                    "reference": null,
                    "status": "received",
                    "line_items": []
                }
            ],
            "bills": [
                {
                    "id": 390785,
                    "location_id": 22322,
                    "tenant_id": 21406,
                    "purchase_order_id": 534296,
                    "account_id": 25153,
                    "code": null,
                    "purchase_order_code": null,
                    "bill_location_id": 22322,
                    "reference": null,
                    "note": null,
                    "payment_term_id": 60198,
                    "due_on": "2018-09-03T02:37:16Z",
                    "status": "active",
                    "created_on": "2018-08-04T02:37:14Z",
                    "modified_on": "2018-08-04T02:37:20Z",
                    "billing_on": "2018-08-04T02:37:16Z",
                    "payment_status": "paid",
                    "sub_total": 1950000,
                    "total_tax": 195000,
                    "total_amount": 2145000,
                    "supplier_id": 1401953,
                    "line_items": [
                        {
                            "id": 1687820,
                            "purchase_order_line_item_id": 3040771,
                            "position": 0,
                            "freeform": false,
                            "created_on": "2018-08-04T02:37:14Z",
                            "modified_on": "2018-08-04T02:37:14Z",
                            "price": 50000,
                            "quantity": 15,
                            "sub_amount": 750000,
                            "tax_amount": 75000,
                            "line_amount": 825000,
                            "note": null
                        },
                        {
                            "id": 1687821,
                            "purchase_order_line_item_id": 3040772,
                            "position": 1,
                            "freeform": false,
                            "created_on": "2018-08-04T02:37:14Z",
                            "modified_on": "2018-08-04T02:37:14Z",
                            "price": 80000,
                            "quantity": 15,
                            "sub_amount": 1200000,
                            "tax_amount": 120000,
                            "line_amount": 1320000,
                            "note": null
                        }
                    ],
                    "payments": [
                        {
                            "id": 306144,
                            "tenant_id": 21406,
                            "location_id": 22322,
                            "purchase_order_id": 534296,
                            "bill_id": 390785,
                            "account_id": 25153,
                            "payment_method_id": 115495,
                            "currency_id": 21407,
                            "exchange_rate": 1,
                            "amount": 2145000,
                            "reference": null,
                            "paid_on": "2018-08-04T02:37:23Z",
                            "status": "paid",
                            "created_on": "2018-08-04T02:37:20Z",
                            "modified_on": "2018-08-04T02:37:20Z"
                        }
                    ]
                }
            ],
            "payments": [
                {
                    "id": 306144,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "purchase_order_id": 534296,
                    "bill_id": 390785,
                    "account_id": 25153,
                    "payment_method_id": 115495,
                    "currency_id": 21407,
                    "exchange_rate": 1,
                    "amount": 2145000,
                    "reference": null,
                    "paid_on": "2018-08-04T02:37:23Z",
                    "status": "paid",
                    "created_on": "2018-08-04T02:37:20Z",
                    "modified_on": "2018-08-04T02:37:20Z"
                }
            ]
        },
        {
            "id": 463190,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "stock_location_id": 22322,
            "created_on": "2018-06-23T04:22:30Z",
            "modified_on": "2018-06-23T04:22:47Z",
            "due_on": "2018-06-23T04:22:29Z",
            "received_on": null,
            "supplier_id": 3654802,
            "supplier_address": null,
            "billing_address": null,
            "contact_id": 0,
            "email": null,
            "phone_number": "0123456789",
            "currency_id": 21407,
            "exchange_rate": 1,
            "price_list_id": 60862,
            "tax_treatment": "exclusive",
            "sub_total": 0,
            "total_tax": 0,
            "total_amount": 0,
            "status": "active",
            "billing_status": "unbilled",
            "payment_status": "paid",
            "procurement_status": "unreceived",
            "note": null,
            "reference": null,
            "code": "PO2306187",
            "tags": null,
            "line_items": [
                {
                    "id": 2582584,
                    "created_on": "2018-06-23T04:22:30Z",
                    "modified_on": "2018-06-23T04:22:30Z",
                    "product_id": 3596979,
                    "variant_id": 5161894,
                    "title": "check kho",
                    "quantity": 0.1,
                    "base_price": 0,
                    "price": 0,
                    "tax_type_id": null,
                    "tax_rate_override": 10,
                    "tax_rate": 10,
                    "sub_amount": 0,
                    "tax_amount": 0,
                    "line_amount": 0,
                    "is_freeform": false,
                    "note": null
                }
            ],
            "procurements": [],
            "bills": [],
            "payments": []
        },
        {
            "id": 463184,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "stock_location_id": 22322,
            "created_on": "2018-06-23T04:17:22Z",
            "modified_on": "2018-06-23T04:17:22Z",
            "due_on": "2018-06-23T04:17:22Z",
            "received_on": null,
            "supplier_id": 3654802,
            "supplier_address": null,
            "billing_address": null,
            "contact_id": 0,
            "email": null,
            "phone_number": "0123456789",
            "currency_id": 21407,
            "exchange_rate": 1,
            "price_list_id": 60862,
            "tax_treatment": "exclusive",
            "sub_total": 7200,
            "total_tax": 720,
            "total_amount": 7920,
            "status": "draft",
            "billing_status": "unbilled",
            "payment_status": "unpaid",
            "procurement_status": "unreceived",
            "note": null,
            "reference": null,
            "code": "PO2306186",
            "tags": null,
            "line_items": [
                {
                    "id": 2582573,
                    "created_on": "2018-06-23T04:17:22Z",
                    "modified_on": "2018-06-23T04:17:22Z",
                    "product_id": 3596750,
                    "variant_id": 5161526,
                    "title": "Có một con bò co trâu con chó  con mèo, con bê côn vật hay một chú xích lô",
                    "quantity": 2.4,
                    "base_price": 3000,
                    "price": 3000,
                    "tax_type_id": null,
                    "tax_rate_override": 10,
                    "tax_rate": 10,
                    "sub_amount": 7200,
                    "tax_amount": 720,
                    "line_amount": 7920,
                    "is_freeform": false,
                    "note": null
                }
            ],
            "procurements": [],
            "bills": [],
            "payments": []
        }
    ]
}
```

<a name= "get-purchase_orders_id"></a>
## 1.3 Lấy một đơn nhập hàng
**Request**
```
GET /admin/purchase_orders/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "purchase_order": {
        "id": 534296,
        "tenant_id": 21406,
        "location_id": 22322,
        "account_id": 25153,
        "stock_location_id": 22322,
        "created_on": "2018-08-04T02:34:49Z",
        "modified_on": "2018-08-04T02:37:20Z",
        "due_on": "2018-08-04T02:34:48Z",
        "received_on": "2018-08-04T02:37:10Z",
        "supplier_id": 1401953,
        "supplier_address": {
            "id": 19581903,
            "label": null,
            "first_name": null,
            "last_name": null,
            "address1": "1234567",
            "address2": null,
            "email": null,
            "phone_number": null,
            "country": "Việt Nam",
            "city": null,
            "district": null,
            "zip_code": null
        },
        "billing_address": {
            "id": 19581904,
            "label": null,
            "first_name": null,
            "last_name": null,
            "address1": "1234567",
            "address2": null,
            "email": null,
            "phone_number": null,
            "country": "Việt Nam",
            "city": null,
            "district": null,
            "zip_code": null
        },
        "contact_id": 0,
        "email": null,
        "phone_number": "01685742369",
        "currency_id": 21407,
        "exchange_rate": 1,
        "price_list_id": 60862,
        "tax_treatment": "exclusive",
        "sub_total": 1950000,
        "total_tax": 195000,
        "total_amount": 2145000,
        "status": "received",
        "billing_status": "billed",
        "payment_status": "paid",
        "procurement_status": "received",
        "note": null,
        "reference": null,
        "code": "PO0408181",
        "tags": null,
        "line_items": [
            {
                "id": 3040771,
                "created_on": "2018-08-04T02:34:49Z",
                "modified_on": "2018-08-04T02:34:49Z",
                "product_id": 3687223,
                "variant_id": 5284103,
                "title": "Product Q - vàng - 1 - thùng",
                "quantity": 15,
                "base_price": 50000,
                "price": 50000,
                "tax_type_id": null,
                "tax_rate_override": 10,
                "tax_rate": 10,
                "sub_amount": 750000,
                "tax_amount": 75000,
                "line_amount": 825000,
                "is_freeform": false,
                "note": null
            },
            {
                "id": 3040772,
                "created_on": "2018-08-04T02:34:49Z",
                "modified_on": "2018-08-04T02:34:49Z",
                "product_id": 1015515,
                "variant_id": 1375790,
                "title": "Quần áo Quảng Châu -1",
                "quantity": 15,
                "base_price": 80000,
                "price": 80000,
                "tax_type_id": null,
                "tax_rate_override": 10,
                "tax_rate": 10,
                "sub_amount": 1200000,
                "tax_amount": 120000,
                "line_amount": 1320000,
                "is_freeform": false,
                "note": null
            }
        ],
        "procurements": [
            {
                "id": 530115,
                "location_id": 22322,
                "tenant_id": 21406,
                "purchase_order_id": 534296,
                "supplier_id": 0,
                "currency_id": 0,
                "code": "PR0408181",
                "purchase_order_code": null,
                "created_on": "2018-08-04T02:37:07Z",
                "modified_on": "2018-08-04T02:37:07Z",
                "received_on": "2018-08-04T02:37:10Z",
                "account_id": 25153,
                "note": null,
                "reference": null,
                "status": "received",
                "line_items": [
                    {
                        "id": 2307018,
                        "purchase_order_line_item_id": 3040771,
                        "quantity": 15,
                        "position": 0,
                        "is_freeform": false,
                        "created_on": "2018-08-04T02:37:07Z",
                        "price": 50000,
                        "sub_amount": 750000,
                        "tax_amount": 75000,
                        "line_amount": 825000,
                        "extra_cost_value": 0,
                        "purchase_order_line_item": null
                    },
                    {
                        "id": 2307019,
                        "purchase_order_line_item_id": 3040772,
                        "quantity": 15,
                        "position": 1,
                        "is_freeform": false,
                        "created_on": "2018-08-04T02:37:07Z",
                        "price": 80000,
                        "sub_amount": 1200000,
                        "tax_amount": 120000,
                        "line_amount": 1320000,
                        "extra_cost_value": 0,
                        "purchase_order_line_item": null
                    }
                ]
            }
        ],
        "bills": [
            {
                "id": 390785,
                "location_id": 22322,
                "tenant_id": 21406,
                "purchase_order_id": 534296,
                "account_id": 25153,
                "code": null,
                "purchase_order_code": null,
                "bill_location_id": 22322,
                "reference": null,
                "note": null,
                "payment_term_id": 60198,
                "due_on": "2018-09-03T02:37:16Z",
                "status": "active",
                "created_on": "2018-08-04T02:37:14Z",
                "modified_on": "2018-08-04T02:37:20Z",
                "billing_on": "2018-08-04T02:37:16Z",
                "payment_status": "paid",
                "sub_total": 1950000,
                "total_tax": 195000,
                "total_amount": 2145000,
                "supplier_id": 1401953,
                "line_items": [
                    {
                        "id": 1687820,
                        "purchase_order_line_item_id": 3040771,
                        "position": 0,
                        "freeform": false,
                        "created_on": "2018-08-04T02:37:14Z",
                        "modified_on": "2018-08-04T02:37:14Z",
                        "price": 50000,
                        "quantity": 15,
                        "sub_amount": 750000,
                        "tax_amount": 75000,
                        "line_amount": 825000,
                        "note": null
                    },
                    {
                        "id": 1687821,
                        "purchase_order_line_item_id": 3040772,
                        "position": 1,
                        "freeform": false,
                        "created_on": "2018-08-04T02:37:14Z",
                        "modified_on": "2018-08-04T02:37:14Z",
                        "price": 80000,
                        "quantity": 15,
                        "sub_amount": 1200000,
                        "tax_amount": 120000,
                        "line_amount": 1320000,
                        "note": null
                    }
                ],
                "payments": [
                    {
                        "id": 306144,
                        "tenant_id": 21406,
                        "location_id": 22322,
                        "purchase_order_id": 534296,
                        "bill_id": 390785,
                        "account_id": 25153,
                        "payment_method_id": 115495,
                        "currency_id": 21407,
                        "exchange_rate": 1,
                        "amount": 2145000,
                        "reference": null,
                        "paid_on": "2018-08-04T02:37:23Z",
                        "status": "paid",
                        "created_on": "2018-08-04T02:37:20Z",
                        "modified_on": "2018-08-04T02:37:20Z"
                    }
                ]
            }
        ],
        "payments": [
            {
                "id": 306144,
                "tenant_id": 21406,
                "location_id": 22322,
                "purchase_order_id": 534296,
                "bill_id": 390785,
                "account_id": 25153,
                "payment_method_id": 115495,
                "currency_id": 21407,
                "exchange_rate": 1,
                "amount": 2145000,
                "reference": null,
                "paid_on": "2018-08-04T02:37:23Z",
                "status": "paid",
                "created_on": "2018-08-04T02:37:20Z",
                "modified_on": "2018-08-04T02:37:20Z"
            }
        ]
    }
}
```
<a name= "purchase_orders_codes"></a>
## 1.4 Sinh mã code đơn nhập hàng
**Request**
```
POST /admin/purchase_orders/codes HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "purchase_order_code": {
        "tenant_id": 21406,
        "code": "PO0608181"
    }
}
```
<a name="purchase_orders_id_status"></a>
## 1.5 Chuyển trạng thái từ draft sang active
**Request**
```
POST admin/purchase_orders/{id}/{status} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "purchase_order": {
        "id": 463162,
        "tenant_id": 21406,
        "location_id": 22322,
        "account_id": 25153,
        "stock_location_id": 22322,
        "created_on": "2018-06-23T04:08:51Z",
        "modified_on": "2018-08-06T06:51:21Z",
        "due_on": "2018-06-23T04:08:51Z",
        "received_on": null,
        "supplier_id": 3654802,
        "supplier_address": null,
        "billing_address": null,
        "contact_id": 0,
        "email": null,
        "phone_number": "0123456789",
        "currency_id": 21407,
        "exchange_rate": 1,
        "price_list_id": 60862,
        "tax_treatment": "exclusive",
        "sub_total": 7200,
        "total_tax": 720,
        "total_amount": 7920,
        "status": "active",
        "billing_status": "unbilled",
        "payment_status": "unpaid",
        "procurement_status": "unreceived",
        "note": null,
        "reference": null,
        "code": "PO2306185",
        "tags": null,
        "line_items": [
            {
                "id": 2582492,
                "created_on": "2018-06-23T04:08:51Z",
                "modified_on": "2018-06-23T04:08:51Z",
                "product_id": 3596750,
                "variant_id": 5161526,
                "title": "Có một con bò co trâu con chó  con mèo, con bê côn vật hay một chú xích lô",
                "quantity": 2.4,
                "base_price": 3000,
                "price": 3000,
                "tax_type_id": null,
                "tax_rate_override": 10,
                "tax_rate": 10,
                "sub_amount": 7200,
                "tax_amount": 720,
                "line_amount": 7920,
                "is_freeform": false,
                "note": null
            }
        ],
        "procurements": [],
        "bills": [],
        "payments": []
    }
}
```
<a name="cancel-purchase_orders_id"></a>
## 1.6 Hủy một đơn nhập

**Request**
```
POST admin/purchase_orders/{id}/cancel HTTP/1.1
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
        "message": "Không có quyền hoặc bị chặn thao tác"
    }
}
```

<a name="put-purchase_orders_id"></a>
## 1.7 Cập nhật một đơn nhập hàng

**Request**
```
PUT admin/purchase_orders/{id} HTTP/1.1 
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
"note: "Đây là ghi chú phiếu nhập 123",
}
```
**Kết quả trả về**
```
{
    "purchase_order": {
        "id": 441553,
        "tenant_id": 21406,
        "location_id": 22322,
        "account_id": 25153,
        "stock_location_id": 22322,
        "created_on": "2018-06-13T01:08:24Z",
        "modified_on": "2018-08-06T06:56:08Z",
        "due_on": "2018-06-13T01:08:24Z",
        "received_on": "2018-06-13T01:08:44Z",
        "supplier_id": 860645,
        "supplier_address": {
            "id": 16425448,
            "label": null,
            "first_name": null,
            "last_name": null,
            "address1": "ewr",
            "address2": null,
            "email": null,
            "phone_number": null,
            "country": "Việt Nam",
            "city": null,
            "district": null,
            "zip_code": null
        },
        "billing_address": {
            "id": 16425449,
            "label": null,
            "first_name": null,
            "last_name": null,
            "address1": "ewr",
            "address2": null,
            "email": null,
            "phone_number": null,
            "country": "Việt Nam",
            "city": null,
            "district": null,
            "zip_code": null
        },
        "contact_id": 16918,
        "email": null,
        "phone_number": null,
        "currency_id": 21407,
        "exchange_rate": 1,
        "price_list_id": 60862,
        "tax_treatment": "exclusive",
        "sub_total": 10000,
        "total_tax": 1000,
        "total_amount": 11000,
        "status": "received",
        "billing_status": "billed",
        "payment_status": "paid",
        "procurement_status": "received",
        "note": "Đây là ghi chú phiếu nhập 123",
        "reference": null,
        "code": "PO1306181",
        "tags": null,
        "line_items": [
            {
                "id": 2460411,
                "created_on": "2018-06-13T01:08:24Z",
                "modified_on": "2018-06-13T01:08:24Z",
                "product_id": 3432689,
                "variant_id": 4918287,
                "title": "váy",
                "quantity": 1,
                "base_price": 10000,
                "price": 10000,
                "tax_type_id": null,
                "tax_rate_override": 10,
                "tax_rate": 10,
                "sub_amount": 10000,
                "tax_amount": 1000,
                "line_amount": 11000,
                "is_freeform": false,
                "note": null
            }
        ],
        "procurements": [
            {
                "id": 437551,
                "location_id": 0,
                "tenant_id": 0,
                "purchase_order_id": 0,
                "supplier_id": 0,
                "currency_id": 0,
                "code": "PR1306181",
                "purchase_order_code": null,
                "created_on": "2018-06-13T01:08:43Z",
                "modified_on": "2018-06-13T01:08:43Z",
                "received_on": "2018-06-13T01:08:44Z",
                "account_id": 25153,
                "note": null,
                "reference": null,
                "status": "received",
                "line_items": [
                    {
                        "id": 1877510,
                        "purchase_order_line_item_id": 2460411,
                        "quantity": 1,
                        "position": 0,
                        "is_freeform": false,
                        "created_on": "2018-06-13T01:08:43Z",
                        "price": 10000,
                        "sub_amount": 10000,
                        "tax_amount": 1000,
                        "line_amount": 11000,
                        "extra_cost_value": 0,
                        "purchase_order_line_item": null
                    }
                ]
            }
        ],
        "bills": [
            {
                "id": 321632,
                "location_id": 0,
                "tenant_id": 0,
                "purchase_order_id": 0,
                "account_id": 25153,
                "code": null,
                "purchase_order_code": null,
                "bill_location_id": 22322,
                "reference": null,
                "note": null,
                "payment_term_id": 60198,
                "due_on": "2018-07-13T01:08:29Z",
                "status": "active",
                "created_on": "2018-06-13T01:08:26Z",
                "modified_on": "2018-06-13T01:08:37Z",
                "billing_on": "2018-06-13T01:08:29Z",
                "payment_status": "paid",
                "sub_total": 10000,
                "total_tax": 1000,
                "total_amount": 11000,
                "supplier_id": 0,
                "line_items": [
                    {
                        "id": 1370835,
                        "purchase_order_line_item_id": 2460411,
                        "position": 0,
                        "freeform": false,
                        "created_on": "2018-06-13T01:08:26Z",
                        "modified_on": "2018-06-13T01:08:26Z",
                        "price": 10000,
                        "quantity": 1,
                        "sub_amount": 10000,
                        "tax_amount": 1000,
                        "line_amount": 11000,
                        "note": null
                    }
                ],
                "payments": null
            }
        ],
        "payments": [
            {
                "id": 254184,
                "tenant_id": 0,
                "location_id": 0,
                "purchase_order_id": 0,
                "bill_id": 321632,
                "account_id": 25153,
                "payment_method_id": 79881,
                "currency_id": 21407,
                "exchange_rate": 1,
                "amount": 11000,
                "reference": null,
                "paid_on": "2018-06-13T01:08:39Z",
                "status": "paid",
                "created_on": "2018-06-13T01:08:37Z",
                "modified_on": "2018-06-13T01:08:37Z"
            }
        ]
    }
}
```

<a name="add-purchase_orders_id_line_items"></a>
## 1.8 Thêm mới một item

**Request**
```
POST /admin/purchase_orders/{id}/line_items HTTP/1.1 
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "id": 908,
  "created_on": "2016-06-11T01:49:21Z",
  "modified_on": "2016-06-11T01:49:21Z",
  "product_id": 11643,
  "variant_id": 16179,
  "title": "Cóc-Xanh",
  "quantity": 177,
  "base_price": 15066600,
  "price": 15066600,
  "tax_type_id": null,
  "tax_rate_override": 0,
  "tax_rate": 0,
  "sub_amount": 2666788200,
  "tax_amount": 0,
  "line_amount": 2666788200,
  "is_freeform": true,
  "note": null
}
```
**Kết quả trả về**
```
{
    "line_item": {
        "id": 3060153,
        "created_on": "2018-08-06T06:58:16Z",
        "modified_on": "2018-08-06T06:58:16Z",
        "product_id": 0,
        "variant_id": 0,
        "title": "Cóc-Xanh",
        "quantity": 177,
        "base_price": 15066600,
        "price": 15066600,
        "tax_type_id": null,
        "tax_rate_override": 0,
        "tax_rate": 0,
        "sub_amount": 2666788200,
        "tax_amount": 0,
        "line_amount": 2666788200,
        "is_freeform": true,
        "note": null
    }
}
```

<a name= "add-purchase_orders"></a>
# 2. Hóa đơn nhập 

<a name= "purchase_orders_bill"></a>
## 2.1 Thêm mới 1 bill nhập hàng

**Request**

```
POST /admin/purchase_orders/{purchaseOrderId}/bills HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```

```
**Trường hợp có lỗi
```
{
    "data_error": {
        "status": 422,
        "errors": {
            "line_items": "may not be null"
        }
    }
}
```
<a name= "get-purchase_orders?"></a>
## 2.2 Lấy ra thông tin bill

**Request**
```
GET /admin/bills/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "bill": {
        "id": 393091,
        "location_id": 22322,
        "tenant_id": 21406,
        "purchase_order_id": 463134,
        "account_id": 25153,
        "code": null,
        "purchase_order_code": "PO2306181",
        "bill_location_id": 22322,
        "reference": null,
        "note": null,
        "payment_term_id": 60198,
        "due_on": "2018-09-05T07:13:31Z",
        "status": "active",
        "created_on": "2018-08-06T07:13:29Z",
        "modified_on": "2018-08-06T07:13:29Z",
        "billing_on": "2018-08-06T07:13:31Z",
        "payment_status": "unpaid",
        "sub_total": 7200,
        "total_tax": 720,
        "total_amount": 7920,
        "supplier_id": 3654802,
        "line_items": [
            {
                "id": 1698065,
                "purchase_order_line_item_id": 2582309,
                "position": 0,
                "freeform": false,
                "created_on": "2018-08-06T07:13:29Z",
                "modified_on": "2018-08-06T07:13:29Z",
                "price": 3000,
                "quantity": 2.4,
                "sub_amount": 7200,
                "tax_amount": 720,
                "line_amount": 7920,
                "note": null
            }
        ],
        "payments": []
    }
}
```

```
```
<a name= "put-purchase_orders_bill_id"></a>
## 2.3 Cập nhật thông tin hóa đơn nhập hàng

**Request**
```
PUT /admin/purchase_orders/{purchaseOrderId}/bills/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "bill": {
    "code": "B1",
    "reference": "B1",
    "note": "chung",
  
    "due_on": "2016-06-08T08:57:14Z"
  }
}
```
**Kết quả trả về**
```
{
    "bill": {
        "id": 393091,
        "location_id": 22322,
        "tenant_id": 21406,
        "purchase_order_id": 463134,
        "account_id": 25153,
        "code": null,
        "purchase_order_code": null,
        "bill_location_id": 22322,
        "reference": "B1",
        "note": "chung",
        "payment_term_id": 60198,
        "due_on": "2016-06-08T08:57:14Z",
        "status": "active",
        "created_on": "2018-08-06T07:13:29Z",
        "modified_on": "2018-08-06T07:18:18Z",
        "billing_on": "2018-08-06T07:13:31Z",
        "payment_status": "unpaid",
        "sub_total": 7200,
        "total_tax": 720,
        "total_amount": 7920,
        "supplier_id": 0,
        "line_items": [
            {
                "id": 1698065,
                "purchase_order_line_item_id": 2582309,
                "position": 0,
                "freeform": false,
                "created_on": "2018-08-06T07:13:29Z",
                "modified_on": "2018-08-06T07:13:29Z",
                "price": 3000,
                "quantity": 2.4,
                "sub_amount": 7200,
                "tax_amount": 720,
                "line_amount": 7920,
                "note": null
            }
        ],
        "payments": null
    }
}
```
<a name= "cancel-purchase_orders_bill_id"></a>
## 2.4 Hủy 1 phiếu bill
**Request**
```
POST /admin/purchase_orders/{purchaseOrderId}/bills/{id}/cancel HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
Status 200 OK
```
<a name="get-purchase_orders_bill?"></a>
## 2.5 Lấy bill theo fillter
**Request**
```
POST /admin/bills HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json


```
**Kết quả trả về**
```

```
<a name= "purchase_orders_bill_payment"></a>
# 3. Thanh toán cho hóa đơn nhập

<a name="get-purchase_orders_bill_payment"></a>
## 3.1 Thêm mới một phiếu thanh toán cho hóa đơn nhập
**Request**
```
POST admin/purchase_orders/{purchaseOrderId}/bills/{billid}/bill_payments HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
"bill_payment": {
"account_id": 25153,
"payment_method_id": 115495,
"amount": 7920,
"reference": null,
"paid_on": "2016-06-08T08:57:14Z"
  }
}
```
**Kết quả trả về**
```
{
    "bill_payment": {
        "id": 307959,
        "tenant_id": 21406,
        "location_id": 22322,
        "purchase_order_id": 463149,
        "bill_id": 393312,
        "account_id": 25153,
        "payment_method_id": 115495,
        "currency_id": 21407,
        "exchange_rate": 1,
        "amount": 7920,
        "reference": null,
        "paid_on": "2016-06-08T08:57:14Z",
        "status": "paid",
        "created_on": "2018-08-06T09:13:02Z",
        "modified_on": "2018-08-06T09:13:02Z"
    }
}
```
**Trường hợp có lỗi**
```
{
    "data_error": {
        "status": 422,
        "errors": {
            "payments.amount": "can't paid more than bill unpaid amount."
        }
    }
}
```
<a name="get-purchase_orders_bill_payment_id"></a>
## 3.2 Lấy một phiếu thanh toán hóa đơn nhập
**Request**
```
GET admin/bill_payments/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "bill_payment": {
        "id": 307959,
        "tenant_id": 21406,
        "location_id": 22322,
        "purchase_order_id": 463149,
        "bill_id": 393312,
        "account_id": 25153,
        "payment_method_id": 115495,
        "currency_id": 21407,
        "exchange_rate": 1,
        "amount": 7920,
        "reference": null,
        "paid_on": "2016-06-08T08:57:14Z",
        "status": "paid",
        "created_on": "2018-08-06T09:13:02Z",
        "modified_on": "2018-08-06T09:13:02Z"
    }
}
```
<a name="cancel-purchase_orders_bill_payments"></a>
## 3.3 Hủy phiếu thanh toán
**Request**
```
POST admin/purchase_orders/{purchaseOrderId}/bills/{billId}/bill_payments/{id}/cancel HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
Status 200 OK
```
<a name= "add-purchase_orders_id_procurements"></a>
# 4. Nhập kho

<a name= "purchase_orders_bill"></a>
## 4.1 Thêm mới phiếu nhập kho

**Request**

```
POST /admin/purchase_orders/{id}/procurements  HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "procurement": {
        "id": 533804,
        "location_id": 22322,
        "tenant_id": 21406,
        "purchase_order_id": 463149,
        "supplier_id": 3654802,
        "currency_id": 21407,
        "code": "IN0906161",
        "purchase_order_code": "PO2306182",
        "created_on": "2018-08-06T09:50:22Z",
        "modified_on": "2018-08-06T09:50:22Z",
        "received_on": "2018-08-06T09:50:22Z",
        "account_id": 25153,
        "note": null,
        "reference": null,
        "status": "received",
        "line_items": [
            {
                "id": 2322707,
                "purchase_order_line_item_id": 2582393,
                "quantity": 1,
                "position": 0,
                "is_freeform": false,
                "created_on": "2018-08-06T09:50:22Z",
                "price": 3000,
                "sub_amount": 3000,
                "tax_amount": 300,
                "line_amount": 3300,
                "extra_cost_value": 0,
                "purchase_order_line_item": null
            }
        ]
    }
}
```
<a name= "get-purchase_orders_id_procurements"></a>
## 4.2 Cập nhật một phiếu nhập kho

**Request**
```
PUT /admin/purchase_orders/{orderid}/procurements/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "procurement": {
    "note": "hello",
    "reference": "hihi"
  }
}

```
**Kết quả trả về**
```
{
    "procurement": {
        "id": 533804,
        "location_id": 22322,
        "tenant_id": 21406,
        "purchase_order_id": 463149,
        "supplier_id": 3654802,
        "currency_id": 21407,
        "code": "IN0906161",
        "purchase_order_code": "PO2306182",
        "created_on": "2018-08-06T09:50:22Z",
        "modified_on": "2018-08-06T09:51:38Z",
        "received_on": "2018-08-06T09:50:22Z",
        "account_id": 25153,
        "note": "hello",
        "reference": "hihi",
        "status": "received",
        "line_items": [
            {
                "id": 2322707,
                "purchase_order_line_item_id": 2582393,
                "quantity": 1,
                "position": 0,
                "is_freeform": false,
                "created_on": "2018-08-06T09:50:22Z",
                "price": 3000,
                "sub_amount": 3000,
                "tax_amount": 300,
                "line_amount": 3300,
                "extra_cost_value": 0,
                "purchase_order_line_item": null
            }
        ]
    }
}
```

<a name= "cancel-purchase_orders_id_procurements"></a>
## 4.3 Hủy 1 phiếu nhập kho

**Request**
```
POST /admin/purchase_orders/{orderid}/procurements/{id}/cancel HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
Status 200 OK
```
<a name= "get-purchase_orders_id_procurements?"></a>
## 4.4 Lấy phiếu nhập kho theo bộ lọc
**Request**
```
GET admin/procurements HTTP/1.1
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
    "procurements": [
        {
            "id": 533804,
            "location_id": 22322,
            "tenant_id": 21406,
            "purchase_order_id": 463149,
            "supplier_id": 3654802,
            "currency_id": 21407,
            "code": "IN0906161",
            "purchase_order_code": "PO2306182",
            "created_on": "2018-08-06T09:50:22Z",
            "modified_on": "2018-08-06T09:52:47Z",
            "received_on": "2018-08-06T09:50:22Z",
            "account_id": 25153,
            "note": "hello",
            "reference": "hihi",
            "status": "cancelled",
            "line_items": [
                {
                    "id": 2322707,
                    "purchase_order_line_item_id": 2582393,
                    "quantity": 1,
                    "position": 0,
                    "is_freeform": false,
                    "created_on": "2018-08-06T09:50:22Z",
                    "price": 3000,
                    "sub_amount": 3000,
                    "tax_amount": 300,
                    "line_amount": 3300,
                    "extra_cost_value": 0,
                    "purchase_order_line_item": null
                }
            ]
        }
    ]
}
```
<a name= "purchase_order_returns"></a>
# 5. Trả hàng

<a name= "add-purchase_order_returns"></a>
## 5.1 Thêm mới một đơn trả hàng

**Request**

```
POST /admin/purchase_order_returns  HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```

```
