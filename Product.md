
[1. Product](#product)

   [ 1.1 Tạo sản phẩm mới](#add-products)

   [ 1.2 Tạo sản phẩm có packsize](#add-products_packsize)

   [ 1.3 Lấy sản phẩm theo id](#get-product_id)

   [ 1.4 Cập nhật sản phẩm](#put-product_id)

   [ 1.5 Xóa 1 sản phẩm](#delete-product_id)
   
   [ 1.6 Lấy 1 sản phẩm theo bộ lọc](#get-product?)
   
[2. Product Variant](#product_variant)

   [ 2.1 Tạo mới 1 variant](#add-product_idproduct_variant_idvariant)
   
   [ 2.2 Xóa 1 variant](#delete-product_idproduct_variant_idvariant)
   
   [ 2.3 Update 1 phiên bản](#add-prepayments)
   
   [ 2.4 Xóa nhiều variant trong 1 sản phẩm](#add-prepayments)
   
   [ 2.5  Lấy về những variants của 1 sản phẩm](#add-prepayments)
   
   [ 2.6 Bộ lọc](#add-prepayments)
  

# 1. Sản phẩm

Product là nơi quản lý danh sách sản phẩm, loại sản phẩm..và tất cả những gì liên quan đến các mặt hàng được bán của chủ shop. Product có thể là thực thể, phần mềm số (ví dụ như phim, nhạc, ebook) hoặc dịch vụ (như thuê dụng cụ, công việc cho thuê). 

Cách hiểu đơn giản nhaas là: nếu một thứ gì đó được bán trong Shop. Hệ thống Sapo POS quản lý sản phẩm tập trung, dễ dàng quản lý lượng nhập mới, lượng tồn kho.. giúp chủ shop đưa ra những quyết định chính xác trong chiến lược kinh doanh của mình.

    
<a name="add-products"></a>
## 1.1 Tạo sản phẩm
**Request**
```
POST /admin/products HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

{
  "product": {
    "category": "B1",
    "category_id": 0,
    "brand": "chung",
    "name": "chung 1",
    "brand_id": 0,
    "supplier_id": null,
    "description": "chung",
    "init_stock": 10,
    "initial_cost_price": 10000,
    "tags": "a,d,b",
    "sku": "a1",
    "barcode": "a1",
    "import_price": 10000,
    "whole_sale_price": 11000,
    "retail_price": 12000,
    "variants": null,
    "options": null
  }
}
```
**Kết quả trả về**
```
{
    "product": {
        "id": 3939079,
        "tenant_id": 56322,
        "created_on": "2018-07-25T06:50:01Z",
        "modified_on": "2018-07-25T06:50:01Z",
        "status": "active",
        "brand_id": 130703,
        "brand": "chung",
        "description": "chung",
        "image_path": null,
        "image_name": null,
        "name": "chung 1",
        "opt1": "Kích thước",
        "opt2": null,
        "opt3": null,
        "category_id": 197231,
        "category": "B1",
        "category_code": "PDG2507184",
        "quantity": 1,
        "tags": "a,b,d",
        "available": null,
        "supplier_ids": [],
        "supplier": null,
        "supplier_id": 0,
        "variant_ids": [
            5702358
        ],
        "variants": [
            {
                "id": 5702358,
                "tenant_id": 56322,
                "location_id": 58369,
                "created_on": "2018-07-25T06:50:01Z",
                "modified_on": "2018-07-25T06:50:01Z",
                "category_id": 197231,
                "brand_id": 130703,
                "product_id": 3939079,
                "committed_stock": null,
                "incoming_stock": null,
                "composite": false,
                "description": null,
                "keep_selling": true,
                "last_cost_price": 10000,
                "retail_price": 12000,
                "init_price": 10000,
                "init_stock": 10,
                "max_online": null,
                "variant_retail_price": 12000,
                "variant_whole_price": 11000,
                "variant_import_price": 10000,
                "image_path": null,
                "image_name": null,
                "image_full_path": null,
                "image_id": null,
                "moving_average_cost": null,
                "name": "chung 1",
                "online_ordering": true,
                "opt1": "Mặc định",
                "opt2": null,
                "opt3": null,
                "product_name": "chung 1",
                "product_status": null,
                "status": "active",
                "sellable": true,
                "sku": "a1",
                "barcode": "a1",
                "stock_on_hand": null,
                "available": null,
                "supplier_code": null,
                "taxable": true,
                "weight_value": null,
                "weight_unit": null,
                "unit": null,
                "packsize": false,
                "packsize_quantity": null,
                "packsize_root_id": null,
                "image_ids": [],
                "variant_channels": null,
                "variant_prices": [
                    {
                        "id": 34123476,
                        "value": 11000,
                        "name": "Giá bán buôn",
                        "price_list_id": 167324,
                        "price_list": {
                            "id": 167324,
                            "tenant_id": 56322,
                            "created_on": "2018-05-08T02:07:57Z",
                            "modified_on": "2018-05-08T02:07:57Z",
                            "code": "BANBUON",
                            "name": "Giá bán buôn",
                            "is_cost": false,
                            "currency_id": 56321,
                            "status": "active",
                            "init": true
                        }
                    },
                    {
                        "id": 34123477,
                        "value": 12000,
                        "name": "Giá bán lẻ",
                        "price_list_id": 167326,
                        "price_list": {
                            "id": 167326,
                            "tenant_id": 56322,
                            "created_on": "2018-05-08T02:07:57Z",
                            "modified_on": "2018-05-08T02:07:57Z",
                            "code": "BANLE",
                            "name": "Giá bán lẻ",
                            "is_cost": false,
                            "currency_id": 56321,
                            "status": "default",
                            "init": true
                        }
                    },
                    {
                        "id": 34123478,
                        "value": 10000,
                        "name": "Giá nhập",
                        "price_list_id": 167325,
                        "price_list": {
                            "id": 167325,
                            "tenant_id": 56322,
                            "created_on": "2018-05-08T02:07:57Z",
                            "modified_on": "2018-05-08T02:07:57Z",
                            "code": "GIANHAP",
                            "name": "Giá nhập",
                            "is_cost": true,
                            "currency_id": 56321,
                            "status": "default",
                            "init": true
                        }
                    }
                ],
                "inventories": [
                    {
                        "location_id": 58369,
                        "variant_id": 5702358,
                        "mac": 10000,
                        "amount": 0,
                        "on_hand": 10,
                        "available": 10,
                        "committed": 0,
                        "incoming": 0,
                        "onway": 0,
                        "reorder_point": 0,
                        "name": null,
                        "min_value": 0,
                        "max_value": 0,
                        "bin_location": null
                    }
                ],
                "images": [],
                "online": false
            }
        ],
        "options": [
            {
                "id": 4276727,
                "name": "Kích thước",
                "position": 1
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
            "phiên bản sản phẩm": "Mã a1 đã trùng "
        }
    }
}
```
<a name="add-products_packsize"></a>
## 1.2 Tạo sản phẩm có packsize
**Request**
```
POST /admin/products HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "product": {
    "status": "active",
    "name": "sp test unit 01",
    "opt1": "Kích thước",
    "opt2": null,
    "opt3": null,
    "variants": [
      {
        "composite": false,
        "keep_selling": true,
        "init_price": 20000,
        "init_stock": 15,
        "name": "sp test unit 01",
        "online_ordering": true,
        "opt1": "M",
        "opt2": null,
        "opt3": null,
        "status": "active",
        "sellable": true,
        "taxable": true,
        "unit": "gói",
        "online": false,
        "packsizes": [
          {
            "composite": false,
            "keep_selling": true,
            "init_price": 20000,
            "init_stock": 15,
            "name": "sp test unit 01",
            "online_ordering": true,
            "opt1": "M",
            "opt2": null,
            "opt3": null,
            "status": "active",
            "sellable": true,
            "taxable": true,
            "online": false,
            "unit": "thùng bé",
            "packsize_quantity": 6
          },
          {
            "composite": false,
            "keep_selling": true,
            "init_price": 20000,
            "init_stock": 15,
            "name": "sp test unit 01",
            "online_ordering": true,
            "opt1": "M",
            "opt2": null,
            "opt3": null,
            "status": "active",
            "sellable": true,
            "taxable": true,
            "online": false,
            "unit": "thùng to",
            "packsize_quantity": "24"
          }
        ]
      }
    ],
    "options": [
      {
        "id": 63460,
        "name": "Kích thước",
        "position": 1
      }
    ]
  }
}
```
**Kết quả trả về**
```
{
    "product": {
        "id": 3939085,
        "tenant_id": 56322,
        "created_on": "2018-07-25T06:52:17Z",
        "modified_on": "2018-07-25T06:52:17Z",
        "status": "active",
        "brand": null,
        "description": null,
        "image_path": null,
        "image_name": null,
        "name": "sp test unit 01",
        "opt1": "Kích thước",
        "opt2": null,
        "opt3": null,
        "category": null,
        "category_code": null,
        "quantity": 3,
        "tags": null,
        "available": null,
        "supplier_ids": [],
        "supplier": null,
        "supplier_id": 0,
        "variant_ids": [
            5702363,
            5702364,
            5702365
        ],
        "variants": [
            {
                "id": 5702363,
                "tenant_id": 56322,
                "location_id": 58369,
                "created_on": "2018-07-25T06:52:17Z",
                "modified_on": "2018-07-25T06:52:17Z",
                "category_id": null,
                "brand_id": null,
                "product_id": 3939085,
                "committed_stock": null,
                "incoming_stock": null,
                "composite": false,
                "description": null,
                "keep_selling": true,
                "last_cost_price": null,
                "retail_price": null,
                "init_price": 20000,
                "init_stock": 15,
                "max_online": null,
                "variant_retail_price": null,
                "variant_whole_price": null,
                "variant_import_price": null,
                "image_path": null,
                "image_name": null,
                "image_full_path": null,
                "image_id": null,
                "moving_average_cost": null,
                "name": "sp test unit 01",
                "online_ordering": true,
                "opt1": "M",
                "opt2": null,
                "opt3": null,
                "product_name": "sp test unit 01",
                "product_status": null,
                "status": "active",
                "sellable": true,
                "sku": "SP12",
                "barcode": "SP12",
                "stock_on_hand": null,
                "available": null,
                "supplier_code": null,
                "taxable": true,
                "weight_value": null,
                "weight_unit": null,
                "unit": "gói",
                "packsize": false,
                "packsize_quantity": null,
                "packsize_root_id": null,
                "image_ids": [],
                "variant_channels": null,
                "variant_prices": [],
                "inventories": [
                    {
                        "location_id": 58369,
                        "variant_id": 5702363,
                        "mac": 20000,
                        "amount": 0,
                        "on_hand": 15,
                        "available": 15,
                        "committed": 0,
                        "incoming": 0,
                        "onway": 0,
                        "reorder_point": 0,
                        "name": null,
                        "min_value": 0,
                        "max_value": 0,
                        "bin_location": null
                    }
                ],
                "images": [],
                "online": false
            },
            {
                "id": 5702364,
                "tenant_id": 56322,
                "location_id": 58369,
                "created_on": "2018-07-25T06:52:17Z",
                "modified_on": "2018-07-25T06:52:17Z",
                "category_id": null,
                "brand_id": null,
                "product_id": 3939085,
                "committed_stock": null,
                "incoming_stock": null,
                "composite": false,
                "description": null,
                "keep_selling": true,
                "last_cost_price": null,
                "retail_price": null,
                "init_price": 20000,
                "init_stock": 15,
                "max_online": null,
                "variant_retail_price": null,
                "variant_whole_price": null,
                "variant_import_price": null,
                "image_path": null,
                "image_name": null,
                "image_full_path": null,
                "image_id": null,
                "moving_average_cost": null,
                "name": "sp test unit 01",
                "online_ordering": true,
                "opt1": "M",
                "opt2": null,
                "opt3": null,
                "product_name": "sp test unit 01",
                "product_status": null,
                "status": "active",
                "sellable": true,
                "sku": "SP13",
                "barcode": "SP13",
                "stock_on_hand": null,
                "available": null,
                "supplier_code": null,
                "taxable": true,
                "weight_value": null,
                "weight_unit": null,
                "unit": "thùng bé",
                "packsize": true,
                "packsize_quantity": 6,
                "packsize_root_id": 5702363,
                "image_ids": [],
                "variant_channels": null,
                "variant_prices": [],
                "inventories": [
                    {
                        "location_id": 58369,
                        "variant_id": 5702364,
                        "mac": 20000,
                        "amount": 0,
                        "on_hand": 2.5,
                        "available": 2.5,
                        "committed": 0,
                        "incoming": 0,
                        "onway": 0,
                        "reorder_point": 0,
                        "name": null,
                        "min_value": 0,
                        "max_value": 0,
                        "bin_location": null
                    }
                ],
                "images": [],
                "online": false
            },
            {
                "id": 5702365,
                "tenant_id": 56322,
                "location_id": 58369,
                "created_on": "2018-07-25T06:52:17Z",
                "modified_on": "2018-07-25T06:52:17Z",
                "category_id": null,
                "brand_id": null,
                "product_id": 3939085,
                "committed_stock": null,
                "incoming_stock": null,
                "composite": false,
                "description": null,
                "keep_selling": true,
                "last_cost_price": null,
                "retail_price": null,
                "init_price": 20000,
                "init_stock": 15,
                "max_online": null,
                "variant_retail_price": null,
                "variant_whole_price": null,
                "variant_import_price": null,
                "image_path": null,
                "image_name": null,
                "image_full_path": null,
                "image_id": null,
                "moving_average_cost": null,
                "name": "sp test unit 01",
                "online_ordering": true,
                "opt1": "M",
                "opt2": null,
                "opt3": null,
                "product_name": "sp test unit 01",
                "product_status": null,
                "status": "active",
                "sellable": true,
                "sku": "SP14",
                "barcode": "SP14",
                "stock_on_hand": null,
                "available": null,
                "supplier_code": null,
                "taxable": true,
                "weight_value": null,
                "weight_unit": null,
                "unit": "thùng to",
                "packsize": true,
                "packsize_quantity": 24,
                "packsize_root_id": 5702363,
                "image_ids": [],
                "variant_channels": null,
                "variant_prices": [],
                "inventories": [
                    {
                        "location_id": 58369,
                        "variant_id": 5702365,
                        "mac": 20000,
                        "amount": 0,
                        "on_hand": 0.625,
                        "available": 0.625,
                        "committed": 0,
                        "incoming": 0,
                        "onway": 0,
                        "reorder_point": 0,
                        "name": null,
                        "min_value": 0,
                        "max_value": 0,
                        "bin_location": null
                    }
                ],
                "images": [],
                "online": false
            }
        ],
        "options": [
            {
                "id": 4276732,
                "name": "Kích thước",
                "position": 1
            }
        ]
    }
}
```
<a name="get-product_id"></a>
## 1.3 Lấy một đối tượng sản phẩm 
**Request**
```
GET /admin/products/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "product": {
        "id": 3939085,
        "tenant_id": 56322,
        "created_on": "2018-07-25T06:52:17Z",
        "modified_on": "2018-07-25T06:52:17Z",
        "status": "active",
        "brand": null,
        "description": null,
        "image_path": null,
        "image_name": null,
        "name": "sp test unit 01",
        "opt1": "Kích thước",
        "opt2": null,
        "opt3": null,
        "category": null,
        "category_code": null,
        "quantity": 3,
        "tags": null,
        "available": null,
        "supplier_ids": [],
        "supplier": null,
        "supplier_id": 0,
        "variant_ids": [
            5702363,
            5702364,
            5702365
        ],
        "variants": [
            {
                "id": 5702363,
                "tenant_id": 56322,
                "location_id": 58369,
                "created_on": "2018-07-25T06:52:17Z",
                "modified_on": "2018-07-25T06:52:17Z",
                "category_id": null,
                "brand_id": null,
                "product_id": 3939085,
                "committed_stock": null,
                "incoming_stock": null,
                "composite": false,
                "description": null,
                "keep_selling": true,
                "last_cost_price": null,
                "retail_price": null,
                "init_price": 20000,
                "init_stock": 15,
                "max_online": null,
                "variant_retail_price": null,
                "variant_whole_price": null,
                "variant_import_price": null,
                "image_path": null,
                "image_name": null,
                "image_full_path": null,
                "image_id": null,
                "moving_average_cost": null,
                "name": "sp test unit 01",
                "online_ordering": true,
                "opt1": "M",
                "opt2": null,
                "opt3": null,
                "product_name": "sp test unit 01",
                "product_status": null,
                "status": "active",
                "sellable": true,
                "sku": "SP12",
                "barcode": "SP12",
                "stock_on_hand": null,
                "available": null,
                "supplier_code": null,
                "taxable": true,
                "weight_value": null,
                "weight_unit": null,
                "unit": "gói",
                "packsize": false,
                "packsize_quantity": null,
                "packsize_root_id": null,
                "image_ids": [],
                "variant_channels": null,
                "variant_prices": [],
                "inventories": [
                    {
                        "location_id": 58369,
                        "variant_id": 5702363,
                        "mac": 20000,
                        "amount": 0,
                        "on_hand": 15,
                        "available": 15,
                        "committed": 0,
                        "incoming": 0,
                        "onway": 0,
                        "reorder_point": 0,
                        "name": null,
                        "min_value": 0,
                        "max_value": 0,
                        "bin_location": null
                    }
                ],
                "images": [],
                "online": false
            },
            {
                "id": 5702364,
                "tenant_id": 56322,
                "location_id": 58369,
                "created_on": "2018-07-25T06:52:17Z",
                "modified_on": "2018-07-25T06:52:17Z",
                "category_id": null,
                "brand_id": null,
                "product_id": 3939085,
                "committed_stock": null,
                "incoming_stock": null,
                "composite": false,
                "description": null,
                "keep_selling": true,
                "last_cost_price": null,
                "retail_price": null,
                "init_price": 20000,
                "init_stock": 15,
                "max_online": null,
                "variant_retail_price": null,
                "variant_whole_price": null,
                "variant_import_price": null,
                "image_path": null,
                "image_name": null,
                "image_full_path": null,
                "image_id": null,
                "moving_average_cost": null,
                "name": "sp test unit 01",
                "online_ordering": true,
                "opt1": "M",
                "opt2": null,
                "opt3": null,
                "product_name": "sp test unit 01",
                "product_status": null,
                "status": "active",
                "sellable": true,
                "sku": "SP13",
                "barcode": "SP13",
                "stock_on_hand": null,
                "available": null,
                "supplier_code": null,
                "taxable": true,
                "weight_value": null,
                "weight_unit": null,
                "unit": "thùng bé",
                "packsize": true,
                "packsize_quantity": 6,
                "packsize_root_id": 5702363,
                "image_ids": [],
                "variant_channels": null,
                "variant_prices": [],
                "inventories": [
                    {
                        "location_id": 58369,
                        "variant_id": 5702364,
                        "mac": 20000,
                        "amount": 0,
                        "on_hand": 2.5,
                        "available": 2.5,
                        "committed": 0,
                        "incoming": 0,
                        "onway": 0,
                        "reorder_point": 0,
                        "name": null,
                        "min_value": 0,
                        "max_value": 0,
                        "bin_location": null
                    }
                ],
                "images": [],
                "online": false
            },
            {
                "id": 5702365,
                "tenant_id": 56322,
                "location_id": 58369,
                "created_on": "2018-07-25T06:52:17Z",
                "modified_on": "2018-07-25T06:52:17Z",
                "category_id": null,
                "brand_id": null,
                "product_id": 3939085,
                "committed_stock": null,
                "incoming_stock": null,
                "composite": false,
                "description": null,
                "keep_selling": true,
                "last_cost_price": null,
                "retail_price": null,
                "init_price": 20000,
                "init_stock": 15,
                "max_online": null,
                "variant_retail_price": null,
                "variant_whole_price": null,
                "variant_import_price": null,
                "image_path": null,
                "image_name": null,
                "image_full_path": null,
                "image_id": null,
                "moving_average_cost": null,
                "name": "sp test unit 01",
                "online_ordering": true,
                "opt1": "M",
                "opt2": null,
                "opt3": null,
                "product_name": "sp test unit 01",
                "product_status": null,
                "status": "active",
                "sellable": true,
                "sku": "SP14",
                "barcode": "SP14",
                "stock_on_hand": null,
                "available": null,
                "supplier_code": null,
                "taxable": true,
                "weight_value": null,
                "weight_unit": null,
                "unit": "thùng to",
                "packsize": true,
                "packsize_quantity": 24,
                "packsize_root_id": 5702363,
                "image_ids": [],
                "variant_channels": null,
                "variant_prices": [],
                "inventories": [
                    {
                        "location_id": 58369,
                        "variant_id": 5702365,
                        "mac": 20000,
                        "amount": 0,
                        "on_hand": 0.625,
                        "available": 0.625,
                        "committed": 0,
                        "incoming": 0,
                        "onway": 0,
                        "reorder_point": 0,
                        "name": null,
                        "min_value": 0,
                        "max_value": 0,
                        "bin_location": null
                    }
                ],
                "images": [],
                "online": false
            }
        ],
        "options": [
            {
                "id": 4276732,
                "name": "Kích thước",
                "position": 1
            }
        ]
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
<a name="put-product_id"></a>
## 1.4 Cập nhật sản phẩm
**Request**
```
PUT admin/products/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "product": {
    "category": null,
    "category_id": null,
    "brand": "Thám tử lừng danh Conan ",
    "name": "Thám tử lừng danh Conan",
    "brand_id": null,
    "supplier_id": null,
    "description": "Truyện trinh thám",
    "init_stock": null,
    "initial_cost_price": null,
    "tags": "tags1",
    "sku": "Chung1",
    "status": "active",
    "barcode": "Co1",
    "import_price": 10000,
    "whole_sale_price": 11000,
    "retail_price": 12000,
    "options": [
      {
        "id": 235,
        "name": "Màu sắc",
        "position": 1
      },
      {
        "name": "Màu sắc sắc"
      }
    ]
  }
}
```
**Kết quả trả về**
```
{
    "product": {
        "id": 3939085,
        "tenant_id": 56322,
        "created_on": "2018-07-25T06:52:17Z",
        "modified_on": "2018-07-25T06:55:32Z",
        "status": "active",
        "brand_id": 130704,
        "brand": "Thám tử lừng danh Conan",
        "description": "Truyện trinh thám",
        "image_path": null,
        "image_name": null,
        "name": "Thám tử lừng danh Conan",
        "opt1": "Màu sắc",
        "opt2": "Màu sắc sắc",
        "opt3": null,
        "category": null,
        "category_code": null,
        "quantity": 3,
        "tags": "tags1",
        "available": null,
        "supplier_ids": [],
        "supplier": null,
        "supplier_id": 0,
        "variant_ids": [
            5702363,
            5702364,
            5702365
        ],
        "variants": [
            {
                "id": 5702363,
                "tenant_id": 56322,
                "location_id": 58369,
                "created_on": "2018-07-25T06:52:17Z",
                "modified_on": "2018-07-25T06:55:32Z",
                "category_id": null,
                "brand_id": 130704,
                "product_id": 3939085,
                "committed_stock": null,
                "incoming_stock": null,
                "composite": false,
                "description": null,
                "keep_selling": true,
                "last_cost_price": null,
                "retail_price": null,
                "init_price": 20000,
                "init_stock": 15,
                "max_online": null,
                "variant_retail_price": null,
                "variant_whole_price": null,
                "variant_import_price": null,
                "image_path": null,
                "image_name": null,
                "image_full_path": null,
                "image_id": null,
                "moving_average_cost": null,
                "name": "sp test unit 01",
                "online_ordering": true,
                "opt1": "M",
                "opt2": null,
                "opt3": null,
                "product_name": "Thám tử lừng danh Conan",
                "product_status": null,
                "status": "active",
                "sellable": true,
                "sku": "SP12",
                "barcode": "SP12",
                "stock_on_hand": null,
                "available": null,
                "supplier_code": null,
                "taxable": true,
                "weight_value": null,
                "weight_unit": null,
                "unit": "gói",
                "packsize": false,
                "packsize_quantity": null,
                "packsize_root_id": null,
                "image_ids": [],
                "variant_channels": null,
                "variant_prices": [],
                "inventories": [
                    {
                        "location_id": 58369,
                        "variant_id": 5702363,
                        "mac": 20000,
                        "amount": 0,
                        "on_hand": 15,
                        "available": 15,
                        "committed": 0,
                        "incoming": 0,
                        "onway": 0,
                        "reorder_point": 0,
                        "name": null,
                        "min_value": 0,
                        "max_value": 0,
                        "bin_location": null
                    }
                ],
                "images": [],
                "online": false
            },
            {
                "id": 5702364,
                "tenant_id": 56322,
                "location_id": 58369,
                "created_on": "2018-07-25T06:52:17Z",
                "modified_on": "2018-07-25T06:55:32Z",
                "category_id": null,
                "brand_id": 130704,
                "product_id": 3939085,
                "committed_stock": null,
                "incoming_stock": null,
                "composite": false,
                "description": null,
                "keep_selling": true,
                "last_cost_price": null,
                "retail_price": null,
                "init_price": 20000,
                "init_stock": 15,
                "max_online": null,
                "variant_retail_price": null,
                "variant_whole_price": null,
                "variant_import_price": null,
                "image_path": null,
                "image_name": null,
                "image_full_path": null,
                "image_id": null,
                "moving_average_cost": null,
                "name": "sp test unit 01",
                "online_ordering": true,
                "opt1": "M",
                "opt2": null,
                "opt3": null,
                "product_name": "Thám tử lừng danh Conan",
                "product_status": null,
                "status": "active",
                "sellable": true,
                "sku": "SP13",
                "barcode": "SP13",
                "stock_on_hand": null,
                "available": null,
                "supplier_code": null,
                "taxable": true,
                "weight_value": null,
                "weight_unit": null,
                "unit": "thùng bé",
                "packsize": true,
                "packsize_quantity": 6,
                "packsize_root_id": 5702363,
                "image_ids": [],
                "variant_channels": null,
                "variant_prices": [],
                "inventories": [
                    {
                        "location_id": 58369,
                        "variant_id": 5702364,
                        "mac": 20000,
                        "amount": 0,
                        "on_hand": 2.5,
                        "available": 2.5,
                        "committed": 0,
                        "incoming": 0,
                        "onway": 0,
                        "reorder_point": 0,
                        "name": null,
                        "min_value": 0,
                        "max_value": 0,
                        "bin_location": null
                    }
                ],
                "images": [],
                "online": false
            },
            {
                "id": 5702365,
                "tenant_id": 56322,
                "location_id": 58369,
                "created_on": "2018-07-25T06:52:17Z",
                "modified_on": "2018-07-25T06:55:32Z",
                "category_id": null,
                "brand_id": 130704,
                "product_id": 3939085,
                "committed_stock": null,
                "incoming_stock": null,
                "composite": false,
                "description": null,
                "keep_selling": true,
                "last_cost_price": null,
                "retail_price": null,
                "init_price": 20000,
                "init_stock": 15,
                "max_online": null,
                "variant_retail_price": null,
                "variant_whole_price": null,
                "variant_import_price": null,
                "image_path": null,
                "image_name": null,
                "image_full_path": null,
                "image_id": null,
                "moving_average_cost": null,
                "name": "sp test unit 01",
                "online_ordering": true,
                "opt1": "M",
                "opt2": null,
                "opt3": null,
                "product_name": "Thám tử lừng danh Conan",
                "product_status": null,
                "status": "active",
                "sellable": true,
                "sku": "SP14",
                "barcode": "SP14",
                "stock_on_hand": null,
                "available": null,
                "supplier_code": null,
                "taxable": true,
                "weight_value": null,
                "weight_unit": null,
                "unit": "thùng to",
                "packsize": true,
                "packsize_quantity": 24,
                "packsize_root_id": 5702363,
                "image_ids": [],
                "variant_channels": null,
                "variant_prices": [],
                "inventories": [
                    {
                        "location_id": 58369,
                        "variant_id": 5702365,
                        "mac": 20000,
                        "amount": 0,
                        "on_hand": 0.625,
                        "available": 0.625,
                        "committed": 0,
                        "incoming": 0,
                        "onway": 0,
                        "reorder_point": 0,
                        "name": null,
                        "min_value": 0,
                        "max_value": 0,
                        "bin_location": null
                    }
                ],
                "images": [],
                "online": false
            }
        ],
        "options": [
            {
                "id": 4276732,
                "name": "Màu sắc",
                "position": 1
            },
            {
                "id": 4276748,
                "name": "Màu sắc sắc",
                "position": 2
            }
        ]
    }
}
```
<a name="delete-product_id"></a>
## 1.5 Xóa 1 sản phẩm (xóa cả variant và option)
**Request**
```
DELETE /admin/products/425 HTTP/1.1
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
    "data_error": {
        "status": 422,
        "errors": {
            "product": "not exists Product: 393985"
        }
    }
}
```
<a name="get-products?"></a>
## 1.6 Lấy sản phẩm theo bộ lọc
**Request**
```
Get admin/products? HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
params: status=active

```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 7,
        "page": 1,
        "limit": 20
    },
    "products": [
        {
            "id": 3939079,
            "tenant_id": 56322,
            "created_on": "2018-07-25T06:50:01Z",
            "modified_on": "2018-07-25T06:50:01Z",
            "status": "active",
            "brand_id": 130703,
            "brand": "chung",
            "description": "chung",
            "image_path": null,
            "image_name": null,
            "name": "chung 1",
            "opt1": "Kích thước",
            "opt2": null,
            "opt3": null,
            "category_id": 197231,
            "category": "B1",
            "category_code": "PDG2507184",
            "quantity": 1,
            "tags": "a,b,d",
            "available": null,
            "supplier_ids": [],
            "supplier": null,
            "supplier_id": 0,
            "variant_ids": [
                5702358
            ],
            "variants": [
                {
                    "id": 5702358,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-07-25T06:50:01Z",
                    "modified_on": "2018-07-25T06:50:01Z",
                    "category_id": 197231,
                    "brand_id": 130703,
                    "product_id": 3939079,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": true,
                    "last_cost_price": 10000,
                    "retail_price": 12000,
                    "init_price": 10000,
                    "init_stock": 10,
                    "max_online": null,
                    "variant_retail_price": 12000,
                    "variant_whole_price": 11000,
                    "variant_import_price": 10000,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "chung 1",
                    "online_ordering": true,
                    "opt1": "Mặc định",
                    "opt2": null,
                    "opt3": null,
                    "product_name": "chung 1",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "a1",
                    "barcode": "a1",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": true,
                    "weight_value": null,
                    "weight_unit": null,
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 34123476,
                            "value": 11000,
                            "name": "Giá bán buôn",
                            "price_list_id": 167324,
                            "price_list": {
                                "id": 167324,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANBUON",
                                "name": "Giá bán buôn",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "active",
                                "init": true
                            }
                        },
                        {
                            "id": 34123477,
                            "value": 12000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        },
                        {
                            "id": 34123478,
                            "value": 10000,
                            "name": "Giá nhập",
                            "price_list_id": 167325,
                            "price_list": {
                                "id": 167325,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "GIANHAP",
                                "name": "Giá nhập",
                                "is_cost": true,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 5702358,
                            "mac": 10000,
                            "amount": 0,
                            "on_hand": 10,
                            "available": 10,
                            "committed": 0,
                            "incoming": 0,
                            "onway": 0,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                }
            ],
            "options": [
                {
                    "id": 4276727,
                    "name": "Kích thước",
                    "position": 1
                }
            ]
        },
        {
            "id": 3262679,
            "tenant_id": 56322,
            "created_on": "2018-05-12T01:43:13Z",
            "modified_on": "2018-05-12T01:43:13Z",
            "status": "active",
            "brand": null,
            "description": null,
            "image_path": null,
            "image_name": null,
            "name": "Mũ lưỡi trai New Era",
            "opt1": "Kích thước",
            "opt2": null,
            "opt3": null,
            "category_id": 162428,
            "category": "Phụ kiện",
            "category_code": "PDG1205183",
            "quantity": 1,
            "tags": "",
            "available": null,
            "supplier_ids": [],
            "supplier": null,
            "supplier_id": 0,
            "variant_ids": [
                4653242
            ],
            "variants": [
                {
                    "id": 4653242,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-05-12T01:43:13Z",
                    "modified_on": "2018-05-12T01:43:13Z",
                    "category_id": 162428,
                    "brand_id": null,
                    "product_id": 3262679,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": true,
                    "last_cost_price": null,
                    "retail_price": 200000,
                    "init_price": 200000,
                    "init_stock": 30,
                    "max_online": null,
                    "variant_retail_price": 200000,
                    "variant_whole_price": 0,
                    "variant_import_price": 0,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "Mũ lưỡi trai New Era",
                    "online_ordering": true,
                    "opt1": "Mặc định",
                    "opt2": null,
                    "opt3": null,
                    "product_name": "Mũ lưỡi trai New Era",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "SP6",
                    "barcode": "SP6",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": false,
                    "weight_value": 0,
                    "weight_unit": "kg",
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 26556588,
                            "value": 200000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        },
                        {
                            "id": 26556589,
                            "value": 0,
                            "name": "Giá bán buôn",
                            "price_list_id": 167324,
                            "price_list": {
                                "id": 167324,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANBUON",
                                "name": "Giá bán buôn",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "active",
                                "init": true
                            }
                        },
                        {
                            "id": 26556590,
                            "value": 0,
                            "name": "Giá nhập",
                            "price_list_id": 167325,
                            "price_list": {
                                "id": 167325,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "GIANHAP",
                                "name": "Giá nhập",
                                "is_cost": true,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 4653242,
                            "mac": 300000,
                            "amount": 0,
                            "on_hand": 45,
                            "available": 45,
                            "committed": 0,
                            "incoming": 0,
                            "onway": 0,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                }
            ],
            "options": [
                {
                    "id": 3475806,
                    "name": "Kích thước",
                    "position": 1
                }
            ]
        },
        {
            "id": 3262678,
            "tenant_id": 56322,
            "created_on": "2018-05-12T01:43:09Z",
            "modified_on": "2018-05-16T02:36:46Z",
            "status": "active",
            "brand": null,
            "description": null,
            "image_path": null,
            "image_name": null,
            "name": "Khăn ống Tommy Hilfiger",
            "opt1": "Kích thước",
            "opt2": null,
            "opt3": null,
            "category_id": 162428,
            "category": "Phụ kiện",
            "category_code": "PDG1205183",
            "quantity": 2,
            "tags": "",
            "available": null,
            "supplier_ids": [],
            "supplier": null,
            "supplier_id": 0,
            "variant_ids": [
                4653241,
                4697232
            ],
            "variants": [
                {
                    "id": 4653241,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-05-12T01:43:09Z",
                    "modified_on": "2018-05-15T08:08:09Z",
                    "category_id": 162428,
                    "brand_id": null,
                    "product_id": 3262678,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": false,
                    "last_cost_price": null,
                    "retail_price": 700000,
                    "init_price": 700000,
                    "init_stock": 30,
                    "max_online": null,
                    "variant_retail_price": 700000,
                    "variant_whole_price": 0,
                    "variant_import_price": 0,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "Khăn ống Tommy Hilfiger",
                    "online_ordering": false,
                    "opt1": "Mặc định",
                    "opt2": null,
                    "opt3": null,
                    "product_name": "Khăn ống Tommy Hilfiger",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "SP5",
                    "barcode": "SP5",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": false,
                    "weight_value": 0,
                    "weight_unit": "kg",
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 26556585,
                            "value": 700000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        },
                        {
                            "id": 26556586,
                            "value": 0,
                            "name": "Giá bán buôn",
                            "price_list_id": 167324,
                            "price_list": {
                                "id": 167324,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANBUON",
                                "name": "Giá bán buôn",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "active",
                                "init": true
                            }
                        },
                        {
                            "id": 26556587,
                            "value": 0,
                            "name": "Giá nhập",
                            "price_list_id": 167325,
                            "price_list": {
                                "id": 167325,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "GIANHAP",
                                "name": "Giá nhập",
                                "is_cost": true,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 4653241,
                            "mac": 700000,
                            "amount": 0,
                            "on_hand": 29,
                            "available": 28,
                            "committed": 1,
                            "incoming": 0,
                            "onway": 0,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                },
                {
                    "id": 4697232,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-05-15T08:08:09Z",
                    "modified_on": "2018-05-16T02:36:46Z",
                    "category_id": 162428,
                    "brand_id": null,
                    "product_id": 3262678,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": false,
                    "last_cost_price": null,
                    "retail_price": 630000,
                    "init_price": 630000,
                    "init_stock": 30,
                    "max_online": null,
                    "variant_retail_price": 630000,
                    "variant_whole_price": 0,
                    "variant_import_price": 0,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "Khăn ống Tommy Hilfiger",
                    "online_ordering": false,
                    "opt1": "(combo)",
                    "opt2": null,
                    "opt3": null,
                    "product_name": "Khăn ống Tommy Hilfiger",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "SP7",
                    "barcode": "SP7",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": false,
                    "weight_value": 0,
                    "weight_unit": "kg",
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 26817697,
                            "value": 630000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        },
                        {
                            "id": 26817698,
                            "value": 0,
                            "name": "Giá bán buôn",
                            "price_list_id": 167324,
                            "price_list": {
                                "id": 167324,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANBUON",
                                "name": "Giá bán buôn",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "active",
                                "init": true
                            }
                        },
                        {
                            "id": 26817699,
                            "value": 0,
                            "name": "Giá nhập",
                            "price_list_id": 167325,
                            "price_list": {
                                "id": 167325,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "GIANHAP",
                                "name": "Giá nhập",
                                "is_cost": true,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 4697232,
                            "mac": 630000,
                            "amount": 0,
                            "on_hand": 27.9,
                            "available": 26,
                            "committed": 1.9,
                            "incoming": 0,
                            "onway": 1,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                }
            ],
            "options": [
                {
                    "id": 3475805,
                    "name": "Kích thước",
                    "position": 1
                }
            ]
        },
        {
            "id": 3262677,
            "tenant_id": 56322,
            "created_on": "2018-05-12T01:43:03Z",
            "modified_on": "2018-05-15T08:08:10Z",
            "status": "active",
            "brand": null,
            "description": null,
            "image_path": null,
            "image_name": null,
            "name": "Kính mát gọng vuông Ray-Ban",
            "opt1": "Kích thước",
            "opt2": null,
            "opt3": null,
            "category_id": 162428,
            "category": "Phụ kiện",
            "category_code": "PDG1205183",
            "quantity": 2,
            "tags": "",
            "available": null,
            "supplier_ids": [],
            "supplier": null,
            "supplier_id": 0,
            "variant_ids": [
                4653240,
                4697233
            ],
            "variants": [
                {
                    "id": 4653240,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-05-12T01:43:03Z",
                    "modified_on": "2018-05-15T08:08:10Z",
                    "category_id": 162428,
                    "brand_id": null,
                    "product_id": 3262677,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": false,
                    "last_cost_price": null,
                    "retail_price": 1500000,
                    "init_price": 1500000,
                    "init_stock": 30,
                    "max_online": null,
                    "variant_retail_price": 1500000,
                    "variant_whole_price": 0,
                    "variant_import_price": 0,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "Kính mát gọng vuông Ray-Ban",
                    "online_ordering": false,
                    "opt1": "Mặc định",
                    "opt2": null,
                    "opt3": null,
                    "product_name": "Kính mát gọng vuông Ray-Ban",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "SP4",
                    "barcode": "SP4",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": false,
                    "weight_value": 0,
                    "weight_unit": "kg",
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 26556582,
                            "value": 1500000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        },
                        {
                            "id": 26556583,
                            "value": 0,
                            "name": "Giá bán buôn",
                            "price_list_id": 167324,
                            "price_list": {
                                "id": 167324,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANBUON",
                                "name": "Giá bán buôn",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "active",
                                "init": true
                            }
                        },
                        {
                            "id": 26556584,
                            "value": 0,
                            "name": "Giá nhập",
                            "price_list_id": 167325,
                            "price_list": {
                                "id": 167325,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "GIANHAP",
                                "name": "Giá nhập",
                                "is_cost": true,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 4653240,
                            "mac": 1500000,
                            "amount": 0,
                            "on_hand": 30,
                            "available": 30,
                            "committed": 0,
                            "incoming": 0,
                            "onway": 0,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                },
                {
                    "id": 4697233,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-05-15T08:08:10Z",
                    "modified_on": "2018-05-15T08:08:10Z",
                    "category_id": 162428,
                    "brand_id": null,
                    "product_id": 3262677,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": true,
                    "last_cost_price": null,
                    "retail_price": 1350000,
                    "init_price": 1350000,
                    "init_stock": 29,
                    "max_online": null,
                    "variant_retail_price": 1350000,
                    "variant_whole_price": 0,
                    "variant_import_price": 0,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "Kính mát gọng vuông Ray-Ban",
                    "online_ordering": true,
                    "opt1": "(combo)",
                    "opt2": null,
                    "opt3": null,
                    "product_name": "Kính mát gọng vuông Ray-Ban",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "SP8",
                    "barcode": "SP8",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": false,
                    "weight_value": 0,
                    "weight_unit": "kg",
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 26817700,
                            "value": 1350000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        },
                        {
                            "id": 26817701,
                            "value": 0,
                            "name": "Giá bán buôn",
                            "price_list_id": 167324,
                            "price_list": {
                                "id": 167324,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANBUON",
                                "name": "Giá bán buôn",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "active",
                                "init": true
                            }
                        },
                        {
                            "id": 26817702,
                            "value": 0,
                            "name": "Giá nhập",
                            "price_list_id": 167325,
                            "price_list": {
                                "id": 167325,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "GIANHAP",
                                "name": "Giá nhập",
                                "is_cost": true,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 4697233,
                            "mac": 1350000,
                            "amount": 0,
                            "on_hand": 28,
                            "available": 28,
                            "committed": 0,
                            "incoming": 1,
                            "onway": 0,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                }
            ],
            "options": [
                {
                    "id": 3475804,
                    "name": "Kích thước",
                    "position": 1
                }
            ]
        },
        {
            "id": 3262676,
            "tenant_id": 56322,
            "created_on": "2018-05-12T01:42:57Z",
            "modified_on": "2018-05-16T02:15:32Z",
            "status": "active",
            "brand": null,
            "description": null,
            "image_path": null,
            "image_name": null,
            "name": "Áo khoác có mũ Bellfield",
            "opt1": "Kích thước",
            "opt2": null,
            "opt3": null,
            "category_id": 162427,
            "category": "Áo khoác",
            "category_code": "PDG1205182",
            "quantity": 2,
            "tags": "",
            "available": null,
            "supplier_ids": [],
            "supplier": null,
            "supplier_id": 0,
            "variant_ids": [
                4653239,
                4697237
            ],
            "variants": [
                {
                    "id": 4653239,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-05-12T01:42:57Z",
                    "modified_on": "2018-05-15T08:08:24Z",
                    "category_id": 162427,
                    "brand_id": null,
                    "product_id": 3262676,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": false,
                    "last_cost_price": null,
                    "retail_price": 1000000,
                    "init_price": 1000000,
                    "init_stock": 30,
                    "max_online": null,
                    "variant_retail_price": 1000000,
                    "variant_whole_price": 0,
                    "variant_import_price": 0,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "Áo khoác có mũ Bellfield",
                    "online_ordering": false,
                    "opt1": "Mặc định",
                    "opt2": null,
                    "opt3": null,
                    "product_name": "Áo khoác có mũ Bellfield",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "SP3",
                    "barcode": "SP3",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": false,
                    "weight_value": 0,
                    "weight_unit": "kg",
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 26556579,
                            "value": 1000000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        },
                        {
                            "id": 26556580,
                            "value": 0,
                            "name": "Giá bán buôn",
                            "price_list_id": 167324,
                            "price_list": {
                                "id": 167324,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANBUON",
                                "name": "Giá bán buôn",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "active",
                                "init": true
                            }
                        },
                        {
                            "id": 26556581,
                            "value": 0,
                            "name": "Giá nhập",
                            "price_list_id": 167325,
                            "price_list": {
                                "id": 167325,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "GIANHAP",
                                "name": "Giá nhập",
                                "is_cost": true,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 4653239,
                            "mac": 1000000,
                            "amount": 0,
                            "on_hand": 30,
                            "available": 30,
                            "committed": 0,
                            "incoming": 0,
                            "onway": 0,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                },
                {
                    "id": 4697237,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-05-15T08:08:24Z",
                    "modified_on": "2018-05-16T02:15:32Z",
                    "category_id": 162427,
                    "brand_id": null,
                    "product_id": 3262676,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": false,
                    "last_cost_price": null,
                    "retail_price": 800000,
                    "init_price": 800000,
                    "init_stock": 30,
                    "max_online": null,
                    "variant_retail_price": 800000,
                    "variant_whole_price": 0,
                    "variant_import_price": 0,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "Áo khoác có mũ Bellfield",
                    "online_ordering": false,
                    "opt1": "(combo)",
                    "opt2": null,
                    "opt3": null,
                    "product_name": "Áo khoác có mũ Bellfield",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "SP10",
                    "barcode": "SP10",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": false,
                    "weight_value": 0,
                    "weight_unit": "kg",
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 26817715,
                            "value": 800000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        },
                        {
                            "id": 26817716,
                            "value": 0,
                            "name": "Giá bán buôn",
                            "price_list_id": 167324,
                            "price_list": {
                                "id": 167324,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANBUON",
                                "name": "Giá bán buôn",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "active",
                                "init": true
                            }
                        },
                        {
                            "id": 26817717,
                            "value": 0,
                            "name": "Giá nhập",
                            "price_list_id": 167325,
                            "price_list": {
                                "id": 167325,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "GIANHAP",
                                "name": "Giá nhập",
                                "is_cost": true,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 4697237,
                            "mac": 800000,
                            "amount": 0,
                            "on_hand": 29.8,
                            "available": 23,
                            "committed": 6.8,
                            "incoming": 0.1,
                            "onway": 0.1,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                }
            ],
            "options": [
                {
                    "id": 3475803,
                    "name": "Kích thước",
                    "position": 1
                }
            ]
        },
        {
            "id": 3262674,
            "tenant_id": 56322,
            "created_on": "2018-05-12T01:42:49Z",
            "modified_on": "2018-05-12T01:42:49Z",
            "status": "active",
            "brand": null,
            "description": null,
            "image_path": null,
            "image_name": null,
            "name": "Quần vải ống suông Farah",
            "opt1": "Kích thước",
            "opt2": null,
            "opt3": null,
            "category_id": 162426,
            "category": "Quần",
            "category_code": "PDG1205181",
            "quantity": 1,
            "tags": "",
            "available": null,
            "supplier_ids": [],
            "supplier": null,
            "supplier_id": 0,
            "variant_ids": [
                4653234
            ],
            "variants": [
                {
                    "id": 4653234,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-05-12T01:42:49Z",
                    "modified_on": "2018-05-12T01:42:49Z",
                    "category_id": 162426,
                    "brand_id": null,
                    "product_id": 3262674,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": true,
                    "last_cost_price": null,
                    "retail_price": 1400000,
                    "init_price": 1400000,
                    "init_stock": 26,
                    "max_online": null,
                    "variant_retail_price": 1400000,
                    "variant_whole_price": 0,
                    "variant_import_price": 0,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "Quần vải ống suông Farah",
                    "online_ordering": true,
                    "opt1": "Mặc định",
                    "opt2": null,
                    "opt3": null,
                    "product_name": "Quần vải ống suông Farah",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "SP2",
                    "barcode": "SP2",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": false,
                    "weight_value": 0,
                    "weight_unit": "kg",
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 26556564,
                            "value": 1400000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        },
                        {
                            "id": 26556565,
                            "value": 0,
                            "name": "Giá bán buôn",
                            "price_list_id": 167324,
                            "price_list": {
                                "id": 167324,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANBUON",
                                "name": "Giá bán buôn",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "active",
                                "init": true
                            }
                        },
                        {
                            "id": 26556566,
                            "value": 0,
                            "name": "Giá nhập",
                            "price_list_id": 167325,
                            "price_list": {
                                "id": 167325,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "GIANHAP",
                                "name": "Giá nhập",
                                "is_cost": true,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 4653234,
                            "mac": 1400000,
                            "amount": 0,
                            "on_hand": 26,
                            "available": 26,
                            "committed": 0,
                            "incoming": 0,
                            "onway": 0,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                }
            ],
            "options": [
                {
                    "id": 3475800,
                    "name": "Kích thước",
                    "position": 1
                }
            ]
        },
        {
            "id": 3217942,
            "tenant_id": 56322,
            "created_on": "2018-05-08T03:45:04Z",
            "modified_on": "2018-05-15T08:08:24Z",
            "status": "active",
            "brand": null,
            "description": null,
            "image_path": null,
            "image_name": null,
            "name": "Váy len nữ",
            "opt1": "Màu sắc",
            "opt2": "Chất liệu",
            "opt3": "Thương hiệu",
            "category": null,
            "category_code": null,
            "quantity": 2,
            "tags": "",
            "available": null,
            "supplier_ids": [],
            "supplier": null,
            "supplier_id": 0,
            "variant_ids": [
                4594856,
                4697236
            ],
            "variants": [
                {
                    "id": 4594856,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-05-08T03:45:04Z",
                    "modified_on": "2018-05-08T03:45:04Z",
                    "category_id": null,
                    "brand_id": null,
                    "product_id": 3217942,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": true,
                    "last_cost_price": null,
                    "retail_price": 500000,
                    "init_price": 500000,
                    "init_stock": 10,
                    "max_online": null,
                    "variant_retail_price": 500000,
                    "variant_whole_price": null,
                    "variant_import_price": null,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "Váy len nữ",
                    "online_ordering": true,
                    "opt1": "Trắng",
                    "opt2": "Len co dãn",
                    "opt3": "Zara",
                    "product_name": "Váy len nữ",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "V0001",
                    "barcode": "V0001",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": true,
                    "weight_value": 0,
                    "weight_unit": "kg",
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 26007687,
                            "value": 500000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 4594856,
                            "mac": 250000,
                            "amount": 0,
                            "on_hand": 59.5,
                            "available": 55,
                            "committed": 4.5,
                            "incoming": 0.5,
                            "onway": 0,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                },
                {
                    "id": 4697236,
                    "tenant_id": 56322,
                    "location_id": 58369,
                    "created_on": "2018-05-15T08:08:24Z",
                    "modified_on": "2018-05-15T08:08:24Z",
                    "category_id": null,
                    "brand_id": null,
                    "product_id": 3217942,
                    "committed_stock": null,
                    "incoming_stock": null,
                    "composite": false,
                    "description": null,
                    "keep_selling": true,
                    "last_cost_price": null,
                    "retail_price": 400000,
                    "init_price": 400000,
                    "init_stock": 9,
                    "max_online": null,
                    "variant_retail_price": 400000,
                    "variant_whole_price": 0,
                    "variant_import_price": 0,
                    "image_path": null,
                    "image_name": null,
                    "image_full_path": null,
                    "image_id": null,
                    "moving_average_cost": null,
                    "name": "Váy len nữ",
                    "online_ordering": true,
                    "opt1": "Trắng (combo)",
                    "opt2": "Len co dãn (combo)",
                    "opt3": "Zara (combo)",
                    "product_name": "Váy len nữ",
                    "product_status": null,
                    "status": "active",
                    "sellable": true,
                    "sku": "SP9",
                    "barcode": "SP9",
                    "stock_on_hand": null,
                    "available": null,
                    "supplier_code": null,
                    "taxable": true,
                    "weight_value": 0,
                    "weight_unit": "kg",
                    "unit": null,
                    "packsize": false,
                    "packsize_quantity": null,
                    "packsize_root_id": null,
                    "image_ids": [],
                    "variant_channels": null,
                    "variant_prices": [
                        {
                            "id": 26817712,
                            "value": 400000,
                            "name": "Giá bán lẻ",
                            "price_list_id": 167326,
                            "price_list": {
                                "id": 167326,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANLE",
                                "name": "Giá bán lẻ",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        },
                        {
                            "id": 26817713,
                            "value": 0,
                            "name": "Giá bán buôn",
                            "price_list_id": 167324,
                            "price_list": {
                                "id": 167324,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "BANBUON",
                                "name": "Giá bán buôn",
                                "is_cost": false,
                                "currency_id": 56321,
                                "status": "active",
                                "init": true
                            }
                        },
                        {
                            "id": 26817714,
                            "value": 0,
                            "name": "Giá nhập",
                            "price_list_id": 167325,
                            "price_list": {
                                "id": 167325,
                                "tenant_id": 56322,
                                "created_on": "2018-05-08T02:07:57Z",
                                "modified_on": "2018-05-08T02:07:57Z",
                                "code": "GIANHAP",
                                "name": "Giá nhập",
                                "is_cost": true,
                                "currency_id": 56321,
                                "status": "default",
                                "init": true
                            }
                        }
                    ],
                    "inventories": [
                        {
                            "location_id": 58369,
                            "variant_id": 4697236,
                            "mac": 400000,
                            "amount": 0,
                            "on_hand": 9,
                            "available": 3,
                            "committed": 6,
                            "incoming": 0,
                            "onway": 0,
                            "reorder_point": 0,
                            "name": null,
                            "min_value": 0,
                            "max_value": 0,
                            "bin_location": null
                        }
                    ],
                    "images": [],
                    "online": false
                }
            ],
            "options": [
                {
                    "id": 3426340,
                    "name": "Màu sắc",
                    "position": 1
                },
                {
                    "id": 3426341,
                    "name": "Chất liệu",
                    "position": 2
                },
                {
                    "id": 3426342,
                    "name": "Thương hiệu",
                    "position": 3
                }
            ]
        }
    ]
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
# 2. Product Variant
Một Product Variant là một phiên bản khác của Product, ví dụ như kích cỡ hay màu sắc khác.
Nếu không có Product Variant, bạn sẽ phải coi áo sơ mi với 3 kích cỡ nhỏ, vừa, lớn như 3 sản phẩm riêng biệt. Product Variant cho phép bạn coi các áo sơ mi cỡ nhỏ, vừa, lớn như 3 biến thể của cùng một sản phẩm là áo sơ mi.
Mỗi một sản phẩm có tối đa 100 biến thể.

<a name="add-product_productId_variant_variantId"></a>

## 2.1 Tạo mới 1 variant
**Request**
```
POST /admin/products/{productId}/variants HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "variant": {
    "composite": false,
    "description": "chung",
    "keep_selling": true,
    "last_cost_price": null,
    "manage_stock": false,
    "max_online": null,
    "name": "chung 1",
    "online_ordering": true,
    "opt1": "abc",
    "opt2": null,
    "opt3": null,
    "sellable": "true",
    "sku": "b2",
    "barcode": "a1",
    "supplier_code": null,
    "taxable": true,
    "weight_value": null,
    "weight_unit": null,
    "unit": null,
    "variant_channels": [
      {
        "name": "bizweb"
      }
    ],
    "variant_prices": [
      {
        "name": "whole_price",
        "value": 1000,
        "price_list_id": 167326
      }
    ],
    "online": false
  }
}
```
**Kết quả trả về**
```
{
    "variant": {
        "id": 5703407,
        "tenant_id": 56322,
        "location_id": 58369,
        "created_on": "2018-07-25T08:08:26Z",
        "modified_on": "2018-07-25T08:08:26Z",
        "category_id": 197231,
        "brand_id": 130703,
        "product_id": 3939079,
        "committed_stock": null,
        "incoming_stock": null,
        "composite": false,
        "description": "chung",
        "keep_selling": true,
        "last_cost_price": null,
        "retail_price": 1000,
        "init_price": 0,
        "init_stock": 0,
        "max_online": null,
        "variant_retail_price": 1000,
        "variant_whole_price": null,
        "variant_import_price": null,
        "image_path": null,
        "image_name": null,
        "image_full_path": null,
        "image_id": null,
        "moving_average_cost": null,
        "name": "chung 1",
        "online_ordering": true,
        "opt1": "abc",
        "opt2": null,
        "opt3": null,
        "product_name": "chung 1",
        "product_status": null,
        "status": "active",
        "sellable": true,
        "sku": "b2",
        "barcode": "a1",
        "stock_on_hand": null,
        "available": null,
        "supplier_code": null,
        "taxable": true,
        "weight_value": null,
        "weight_unit": null,
        "unit": null,
        "packsize": false,
        "packsize_quantity": null,
        "packsize_root_id": null,
        "image_ids": [],
        "variant_channels": [],
        "variant_prices": [
            {
                "id": 34132945,
                "value": 1000,
                "name": "Giá bán lẻ",
                "price_list_id": 167326,
                "price_list": {
                    "id": 167326,
                    "tenant_id": 56322,
                    "created_on": "2018-05-08T02:07:57Z",
                    "modified_on": "2018-05-08T02:07:57Z",
                    "code": "BANLE",
                    "name": "Giá bán lẻ",
                    "is_cost": false,
                    "currency_id": 56321,
                    "status": "default",
                    "init": true
                }
            }
        ],
        "inventories": [
            {
                "location_id": 58369,
                "variant_id": 0,
                "mac": 0,
                "amount": 0,
                "on_hand": 0,
                "available": 0,
                "committed": 0,
                "incoming": 0,
                "onway": 0,
                "reorder_point": 0,
                "name": null,
                "min_value": 0,
                "max_value": 0,
                "bin_location": null
            }
        ],
        "images": [],
        "online": false
    }
}
```
## 2.2 Xóa 1 variant
**Request**
```
DELETE /admin/products/{productId}/variants HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
Status 200 OK
```
## 2.3 Update 1 phiên bản
**Request**
```
PUT /admin/products/{productId}/variants/{variantId} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "variant": {
    "category": null,
    "product_id": 635642,
    "import_price": null,
    "committed_stock": null,
    "incoming_stock": null,
    "composite": false,
    "description": "chung",
    "keep_selling": true,
    "last_cost_price": null,
    "init_price": 10000,
    "init_stock": 200,
    "max_online": null,
    "image_path": null,
    "image_name": null,
    "moving_average_cost": null,
    "name": "Áo cổ đức",
    "online_ordering": true,
    "opt1": "xanh",
    "opt2": null,
    "opt3": null,
    "product_name": null,
    "product_status": null,
    "status": "active",
    "sellable": "true",
    "sku": null,
    "barcode": null,
    "stock_on_hand": null,
    "available": null,
    "supplier_code": null,
    "taxable": true,
    "weight_value": null,
    "weight_unit": null,
    "unit": null,
    "image_ids": [],
    "variant_channels": [],
    "variant_prices": [
      {
        "value": 10000,
        "name": "Giá nhập",
        "price_list_id": 16
      },
      {
        "value": 12000,
        "name": "Giá bán buôn",
        "price_list_id": 16
      },
      {
        "value": 15000,
        "name": "Giá bán lẻ",
        "price_list_id": 16
      }
    ],
    "online": false
  }
}
```
**Kết quả trả về**
```
```
**Trường hợp có lỗi**
```
{
    "error": {
        "message": "Không tìm thấy đối tượng"
    }
}
```
## 2.4 Xóa nhiều variant trong 1 sản phẩm
**Request**
```
DELETE /admin/products/{productId}/variants HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```

```
**Trường hợp có lỗi**
```
```
## 2.5 Lấy về những variants của 1 sản phẩm
**Request**
```
GET /products/{productId}/variants HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 3,
        "page": 1,
        "limit": 20
    },
    "variants": [
        {
            "id": 5710247,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-07-26T01:20:47Z",
            "modified_on": "2018-07-26T01:20:47Z",
            "category_id": null,
            "brand_id": 130704,
            "product_id": 3262676,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": "chung",
            "keep_selling": true,
            "last_cost_price": null,
            "retail_price": 1000,
            "init_price": 0,
            "init_stock": 0,
            "max_online": null,
            "variant_retail_price": 1000,
            "variant_whole_price": null,
            "variant_import_price": null,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "chung 1",
            "online_ordering": true,
            "opt1": "abc",
            "opt2": "acb",
            "opt3": null,
            "product_name": "Thám tử lừng danh Conan",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "c1",
            "barcode": "a1",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": true,
            "weight_value": null,
            "weight_unit": null,
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": [],
            "variant_prices": [
                {
                    "id": 34168716,
                    "value": 1000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 0,
                    "mac": 0,
                    "amount": 0,
                    "on_hand": 0,
                    "available": 0,
                    "committed": 0,
                    "incoming": 0,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4697237,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-15T08:08:24Z",
            "modified_on": "2018-07-26T01:17:07Z",
            "category_id": null,
            "brand_id": 130704,
            "product_id": 3262676,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": false,
            "last_cost_price": null,
            "retail_price": 800000,
            "init_price": 800000,
            "init_stock": 30,
            "max_online": null,
            "variant_retail_price": 800000,
            "variant_whole_price": 0,
            "variant_import_price": 0,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Áo khoác có mũ Bellfield",
            "online_ordering": false,
            "opt1": "(combo)",
            "opt2": null,
            "opt3": null,
            "product_name": "Thám tử lừng danh Conan",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP10",
            "barcode": "SP10",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": false,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": [],
            "variant_prices": [
                {
                    "id": 26817715,
                    "value": 800000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 26817716,
                    "value": 0,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 26817717,
                    "value": 0,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 0,
                    "mac": 800000,
                    "amount": 0,
                    "on_hand": 29.8,
                    "available": 23,
                    "committed": 6.8,
                    "incoming": 0.1,
                    "onway": 0.1,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4653239,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-12T01:42:57Z",
            "modified_on": "2018-07-26T01:17:07Z",
            "category_id": null,
            "brand_id": 130704,
            "product_id": 3262676,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": false,
            "last_cost_price": null,
            "retail_price": 1000000,
            "init_price": 1000000,
            "init_stock": 30,
            "max_online": null,
            "variant_retail_price": 1000000,
            "variant_whole_price": 0,
            "variant_import_price": 0,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Áo khoác có mũ Bellfield",
            "online_ordering": false,
            "opt1": "Mặc định",
            "opt2": null,
            "opt3": null,
            "product_name": "Thám tử lừng danh Conan",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP3",
            "barcode": "SP3",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": false,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": [],
            "variant_prices": [
                {
                    "id": 26556579,
                    "value": 1000000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 26556580,
                    "value": 0,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 26556581,
                    "value": 0,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 0,
                    "mac": 1000000,
                    "amount": 0,
                    "on_hand": 30,
                    "available": 30,
                    "committed": 0,
                    "incoming": 0,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        }
    ]
}
```
## 2.6 Bộ lọc
**Request**
```
GET /variants? HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 12,
        "page": 1,
        "limit": 20
    },
    "variants": [
        {
            "id": 5710247,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-07-26T01:20:47Z",
            "modified_on": "2018-07-26T01:20:47Z",
            "category_id": null,
            "brand_id": 130704,
            "product_id": 3262676,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": "chung",
            "keep_selling": true,
            "last_cost_price": null,
            "retail_price": 1000,
            "init_price": 0,
            "init_stock": 0,
            "max_online": null,
            "variant_retail_price": 1000,
            "variant_whole_price": null,
            "variant_import_price": null,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "chung 1",
            "online_ordering": true,
            "opt1": "abc",
            "opt2": "acb",
            "opt3": null,
            "product_name": "Thám tử lừng danh Conan",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "c1",
            "barcode": "a1",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": true,
            "weight_value": null,
            "weight_unit": null,
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 34168716,
                    "value": 1000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 5710247,
                    "mac": 0,
                    "amount": 0,
                    "on_hand": 0,
                    "available": 0,
                    "committed": 0,
                    "incoming": 0,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 5702358,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-07-25T06:50:01Z",
            "modified_on": "2018-07-25T06:50:01Z",
            "category_id": 197231,
            "brand_id": 130703,
            "product_id": 3939079,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": true,
            "last_cost_price": 10000,
            "retail_price": 12000,
            "init_price": 10000,
            "init_stock": 10,
            "max_online": null,
            "variant_retail_price": 12000,
            "variant_whole_price": 11000,
            "variant_import_price": 10000,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "chung 1",
            "online_ordering": true,
            "opt1": "Mặc định",
            "opt2": null,
            "opt3": null,
            "product_name": "chung 1",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "a1",
            "barcode": "a1",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": true,
            "weight_value": null,
            "weight_unit": null,
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 34123476,
                    "value": 11000,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 34123477,
                    "value": 12000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 34123478,
                    "value": 10000,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 5702358,
                    "mac": 10000,
                    "amount": 0,
                    "on_hand": 10,
                    "available": 10,
                    "committed": 0,
                    "incoming": 0,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4697237,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-15T08:08:24Z",
            "modified_on": "2018-07-26T01:17:07Z",
            "category_id": null,
            "brand_id": 130704,
            "product_id": 3262676,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": false,
            "last_cost_price": null,
            "retail_price": 800000,
            "init_price": 800000,
            "init_stock": 30,
            "max_online": null,
            "variant_retail_price": 800000,
            "variant_whole_price": 0,
            "variant_import_price": 0,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Áo khoác có mũ Bellfield",
            "online_ordering": false,
            "opt1": "(combo)",
            "opt2": null,
            "opt3": null,
            "product_name": "Thám tử lừng danh Conan",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP10",
            "barcode": "SP10",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": false,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 26817715,
                    "value": 800000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 26817716,
                    "value": 0,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 26817717,
                    "value": 0,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 4697237,
                    "mac": 800000,
                    "amount": 0,
                    "on_hand": 29.8,
                    "available": 23,
                    "committed": 6.8,
                    "incoming": 0.1,
                    "onway": 0.1,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4697236,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-15T08:08:24Z",
            "modified_on": "2018-05-15T08:08:24Z",
            "category_id": null,
            "brand_id": null,
            "product_id": 3217942,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": true,
            "last_cost_price": null,
            "retail_price": 400000,
            "init_price": 400000,
            "init_stock": 9,
            "max_online": null,
            "variant_retail_price": 400000,
            "variant_whole_price": 0,
            "variant_import_price": 0,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Váy len nữ",
            "online_ordering": true,
            "opt1": "Trắng (combo)",
            "opt2": "Len co dãn (combo)",
            "opt3": "Zara (combo)",
            "product_name": "Váy len nữ",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP9",
            "barcode": "SP9",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": true,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 26817712,
                    "value": 400000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 26817713,
                    "value": 0,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 26817714,
                    "value": 0,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 4697236,
                    "mac": 400000,
                    "amount": 0,
                    "on_hand": 9,
                    "available": 3,
                    "committed": 6,
                    "incoming": 0,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4697233,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-15T08:08:10Z",
            "modified_on": "2018-05-15T08:08:10Z",
            "category_id": 162428,
            "brand_id": null,
            "product_id": 3262677,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": true,
            "last_cost_price": null,
            "retail_price": 1350000,
            "init_price": 1350000,
            "init_stock": 29,
            "max_online": null,
            "variant_retail_price": 1350000,
            "variant_whole_price": 0,
            "variant_import_price": 0,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Kính mát gọng vuông Ray-Ban",
            "online_ordering": true,
            "opt1": "(combo)",
            "opt2": null,
            "opt3": null,
            "product_name": "Kính mát gọng vuông Ray-Ban",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP8",
            "barcode": "SP8",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": false,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 26817700,
                    "value": 1350000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 26817701,
                    "value": 0,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 26817702,
                    "value": 0,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 4697233,
                    "mac": 1350000,
                    "amount": 0,
                    "on_hand": 28,
                    "available": 28,
                    "committed": 0,
                    "incoming": 1,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4697232,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-15T08:08:09Z",
            "modified_on": "2018-05-16T02:36:46Z",
            "category_id": 162428,
            "brand_id": null,
            "product_id": 3262678,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": false,
            "last_cost_price": null,
            "retail_price": 630000,
            "init_price": 630000,
            "init_stock": 30,
            "max_online": null,
            "variant_retail_price": 630000,
            "variant_whole_price": 0,
            "variant_import_price": 0,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Khăn ống Tommy Hilfiger",
            "online_ordering": false,
            "opt1": "(combo)",
            "opt2": null,
            "opt3": null,
            "product_name": "Khăn ống Tommy Hilfiger",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP7",
            "barcode": "SP7",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": false,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 26817697,
                    "value": 630000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 26817698,
                    "value": 0,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 26817699,
                    "value": 0,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 4697232,
                    "mac": 630000,
                    "amount": 0,
                    "on_hand": 27.9,
                    "available": 26,
                    "committed": 1.9,
                    "incoming": 0,
                    "onway": 1,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4653242,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-12T01:43:13Z",
            "modified_on": "2018-07-25T08:17:30Z",
            "category_id": 162428,
            "brand_id": null,
            "product_id": 3262679,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": "chung",
            "keep_selling": true,
            "last_cost_price": null,
            "retail_price": null,
            "init_price": 200000,
            "init_stock": 30,
            "max_online": null,
            "variant_retail_price": null,
            "variant_whole_price": null,
            "variant_import_price": null,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Áo cổ đức",
            "online_ordering": true,
            "opt1": "xanh",
            "opt2": null,
            "opt3": null,
            "product_name": "Mũ lưỡi trai New Era",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP6",
            "barcode": null,
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": true,
            "weight_value": null,
            "weight_unit": null,
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 4653242,
                    "mac": 300000,
                    "amount": 0,
                    "on_hand": 45,
                    "available": 45,
                    "committed": 0,
                    "incoming": 0,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4653241,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-12T01:43:09Z",
            "modified_on": "2018-05-15T08:08:09Z",
            "category_id": 162428,
            "brand_id": null,
            "product_id": 3262678,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": false,
            "last_cost_price": null,
            "retail_price": 700000,
            "init_price": 700000,
            "init_stock": 30,
            "max_online": null,
            "variant_retail_price": 700000,
            "variant_whole_price": 0,
            "variant_import_price": 0,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Khăn ống Tommy Hilfiger",
            "online_ordering": false,
            "opt1": "Mặc định",
            "opt2": null,
            "opt3": null,
            "product_name": "Khăn ống Tommy Hilfiger",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP5",
            "barcode": "SP5",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": false,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 26556585,
                    "value": 700000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 26556586,
                    "value": 0,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 26556587,
                    "value": 0,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 4653241,
                    "mac": 700000,
                    "amount": 0,
                    "on_hand": 29,
                    "available": 28,
                    "committed": 1,
                    "incoming": 0,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4653240,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-12T01:43:03Z",
            "modified_on": "2018-05-15T08:08:10Z",
            "category_id": 162428,
            "brand_id": null,
            "product_id": 3262677,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": false,
            "last_cost_price": null,
            "retail_price": 1500000,
            "init_price": 1500000,
            "init_stock": 30,
            "max_online": null,
            "variant_retail_price": 1500000,
            "variant_whole_price": 0,
            "variant_import_price": 0,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Kính mát gọng vuông Ray-Ban",
            "online_ordering": false,
            "opt1": "Mặc định",
            "opt2": null,
            "opt3": null,
            "product_name": "Kính mát gọng vuông Ray-Ban",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP4",
            "barcode": "SP4",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": false,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 26556582,
                    "value": 1500000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 26556583,
                    "value": 0,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 26556584,
                    "value": 0,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 4653240,
                    "mac": 1500000,
                    "amount": 0,
                    "on_hand": 30,
                    "available": 30,
                    "committed": 0,
                    "incoming": 0,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4653239,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-12T01:42:57Z",
            "modified_on": "2018-07-26T01:17:07Z",
            "category_id": null,
            "brand_id": 130704,
            "product_id": 3262676,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": false,
            "last_cost_price": null,
            "retail_price": 1000000,
            "init_price": 1000000,
            "init_stock": 30,
            "max_online": null,
            "variant_retail_price": 1000000,
            "variant_whole_price": 0,
            "variant_import_price": 0,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Áo khoác có mũ Bellfield",
            "online_ordering": false,
            "opt1": "Mặc định",
            "opt2": null,
            "opt3": null,
            "product_name": "Thám tử lừng danh Conan",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP3",
            "barcode": "SP3",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": false,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 26556579,
                    "value": 1000000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 26556580,
                    "value": 0,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 26556581,
                    "value": 0,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 4653239,
                    "mac": 1000000,
                    "amount": 0,
                    "on_hand": 30,
                    "available": 30,
                    "committed": 0,
                    "incoming": 0,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        },
        {
            "id": 4653234,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-12T01:42:49Z",
            "modified_on": "2018-07-25T09:55:30Z",
            "category_id": 162426,
            "brand_id": null,
            "product_id": 3262674,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": true,
            "last_cost_price": null,
            "retail_price": 1400000,
            "init_price": 1400000,
            "init_stock": 26,
            "max_online": null,
            "variant_retail_price": 1400000,
            "variant_whole_price": 0,
            "variant_import_price": 0,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Quần vải ống suông Farah",
            "online_ordering": true,
            "opt1": "Mặc định",
            "opt2": null,
            "opt3": null,
            "product_name": "Quần vải ống suông Farah",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "SP2",
            "barcode": "SP2",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": false,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [
                1297567,
                1297568
            ],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 26556564,
                    "value": 1400000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                },
                {
                    "id": 26556565,
                    "value": 0,
                    "name": "Giá bán buôn",
                    "price_list_id": 167324,
                    "price_list": {
                        "id": 167324,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANBUON",
                        "name": "Giá bán buôn",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "active",
                        "init": true
                    }
                },
                {
                    "id": 26556566,
                    "value": 0,
                    "name": "Giá nhập",
                    "price_list_id": 167325,
                    "price_list": {
                        "id": 167325,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "GIANHAP",
                        "name": "Giá nhập",
                        "is_cost": true,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 4653234,
                    "mac": 1400000,
                    "amount": 0,
                    "on_hand": 26,
                    "available": 26,
                    "committed": 0,
                    "incoming": 0,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [
                {
                    "id": 1297567,
                    "size": 12973,
                    "tenant_id": 56322,
                    "variant_id": 4653234,
                    "created_on": "2018-07-25T09:49:59Z",
                    "modified_on": "2018-07-25T09:49:59Z",
                    "path": "100/056/322/variants/566d066a-aa4c-4621-beef-2054d66f2670.jpg",
                    "full_path": "https://sapo.dktcdn.net/100/056/322/variants/566d066a-aa4c-4621-beef-2054d66f2670.jpg",
                    "file_name": "566d066a-aa4c-4621-beef-2054d66f2670.jpg",
                    "is_default": false
                },
                {
                    "id": 1297568,
                    "size": 38964,
                    "tenant_id": 56322,
                    "variant_id": 4653234,
                    "created_on": "2018-07-25T09:50:02Z",
                    "modified_on": "2018-07-25T09:50:02Z",
                    "path": "100/056/322/variants/4cfa7d59-b779-488c-9651-61fbfce2a7cd.jpg",
                    "full_path": "https://sapo.dktcdn.net/100/056/322/variants/4cfa7d59-b779-488c-9651-61fbfce2a7cd.jpg",
                    "file_name": "4cfa7d59-b779-488c-9651-61fbfce2a7cd.jpg",
                    "is_default": false
                }
            ],
            "online": false
        },
        {
            "id": 4594856,
            "tenant_id": 56322,
            "location_id": 58369,
            "created_on": "2018-05-08T03:45:04Z",
            "modified_on": "2018-05-08T03:45:04Z",
            "category_id": null,
            "brand_id": null,
            "product_id": 3217942,
            "committed_stock": null,
            "incoming_stock": null,
            "composite": false,
            "description": null,
            "keep_selling": true,
            "last_cost_price": null,
            "retail_price": 500000,
            "init_price": 500000,
            "init_stock": 10,
            "max_online": null,
            "variant_retail_price": 500000,
            "variant_whole_price": null,
            "variant_import_price": null,
            "image_path": null,
            "image_name": null,
            "image_full_path": null,
            "image_id": null,
            "moving_average_cost": null,
            "name": "Váy len nữ",
            "online_ordering": true,
            "opt1": "Trắng",
            "opt2": "Len co dãn",
            "opt3": "Zara",
            "product_name": "Váy len nữ",
            "product_status": null,
            "status": "active",
            "sellable": true,
            "sku": "V0001",
            "barcode": "V0001",
            "stock_on_hand": null,
            "available": null,
            "supplier_code": null,
            "taxable": true,
            "weight_value": 0,
            "weight_unit": "kg",
            "unit": null,
            "packsize": false,
            "packsize_quantity": null,
            "packsize_root_id": null,
            "image_ids": [],
            "variant_channels": null,
            "variant_prices": [
                {
                    "id": 26007687,
                    "value": 500000,
                    "name": "Giá bán lẻ",
                    "price_list_id": 167326,
                    "price_list": {
                        "id": 167326,
                        "tenant_id": 56322,
                        "created_on": "2018-05-08T02:07:57Z",
                        "modified_on": "2018-05-08T02:07:57Z",
                        "code": "BANLE",
                        "name": "Giá bán lẻ",
                        "is_cost": false,
                        "currency_id": 56321,
                        "status": "default",
                        "init": true
                    }
                }
            ],
            "inventories": [
                {
                    "location_id": 58369,
                    "variant_id": 4594856,
                    "mac": 250000,
                    "amount": 0,
                    "on_hand": 59.5,
                    "available": 55,
                    "committed": 4.5,
                    "incoming": 0.5,
                    "onway": 0,
                    "reorder_point": 0,
                    "name": null,
                    "min_value": 0,
                    "max_value": 0,
                    "bin_location": null
                }
            ],
            "images": [],
            "online": false
        }
    ]
}
```

# 3. Product Composite
## 3.1 Cập nhật một sản phẩm đặc thù
**Request**
```
PUT admin/products/{productId}/variants/{variantId}/composites HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "composites": {
    "product_composites": [
      {
        "sub_variant_id": 4653241,
        "quantity": 4,
        "price": 10000
      },
      {
        "sub_variant_id": 4697236,
        "quantity": 2,
        "price": 2000
      }
    ]
  }
}
```
**Kết quả trả về**
```

```
**Trường hợp có lỗi**
```
{
    "data_error": {
        "status": 422,
        "errors": {
            "variant": "phiên bản này đã được tạo composite"
        }
    }
}
```
## 3.2 Lấy ra một sản phẩm đặc thù
**Request**
```
GET /variants? HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "composites": [
        {
            "id": 19904,
            "tenant_id": 56322,
            "variant_id": 5710589,
            "sub_variant_id": 4653241,
            "price": 700000,
            "quantity": 1
        },
        {
            "id": 19905,
            "tenant_id": 56322,
            "variant_id": 5710589,
            "sub_variant_id": 4697236,
            "price": 400000,
            "quantity": 1
        }
    ]
}
```
**Trường hợp có lỗi**
```
{
    "data_error": {
        "status": 422,
        "errors": {
            "variant": "not exists Variant 571089"
        }
    }
}
```
# 4. VariantInventory - Thiết lập định mức tồn	
## 4.1 Cập nhật mức định tồn
**Request**
```
PUT /admin/products/1297/variants/3321/locations HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "variant_inventories": [{
    "location_id":81,
    "min_value":19,
     "max_value":12
  },
  {
   "location_id":5072,
    min_value":19,
     "max_value":12
  }  ] }
```
**Kết quả trả về**
```

```
**Trường hợp có lỗi**
```
```
## 4.2 Lấy ra định mức tồn của phiên bản
**Request**
```
GET /admin/products/{productId}/variants/{VariantId}/locations HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "variant_inventories": [
        {
            "location_id": 58369,
            "min_value": 0,
            "max_value": 0,
            "bin_location": null
        }
    ]
}
```
**Trường hợp có lỗi**
```
```
# 5. Product Image
Sản phẩm sẽ được bán dễ dàng hơn nếu khách hàng có thể xem ảnh của sản phẩm. Thông tin ảnh được lưu trữ trong tài nguyên Product Image. Bất kì sản phẩm nào cũng có thể có tới 250 ảnh định dạng .png, .gif hoặc .jpg

## 5.1 lấy danh sách image
**Request**
```
GET /admin/products/{productId}/variants/{variantId}/images/ HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "images": [
        {
            "id": 1297568,
            "size": 38964,
            "tenant_id": 56322,
            "variant_id": 4653234,
            "created_on": "2018-07-25T09:50:02Z",
            "modified_on": "2018-07-25T09:50:02Z",
            "path": "100/056/322/variants/4cfa7d59-b779-488c-9651-61fbfce2a7cd.jpg",
            "full_path": "https://sapo.dktcdn.net/100/056/322/variants/4cfa7d59-b779-488c-9651-61fbfce2a7cd.jpg",
            "file_name": "4cfa7d59-b779-488c-9651-61fbfce2a7cd.jpg",
            "is_default": false
        },
        {
            "id": 1297567,
            "size": 12973,
            "tenant_id": 56322,
            "variant_id": 4653234,
            "created_on": "2018-07-25T09:49:59Z",
            "modified_on": "2018-07-25T09:49:59Z",
            "path": "100/056/322/variants/566d066a-aa4c-4621-beef-2054d66f2670.jpg",
            "full_path": "https://sapo.dktcdn.net/100/056/322/variants/566d066a-aa4c-4621-beef-2054d66f2670.jpg",
            "file_name": "566d066a-aa4c-4621-beef-2054d66f2670.jpg",
            "is_default": false
        },
        {
            "id": 1297564,
            "size": 98851,
            "tenant_id": 56322,
            "variant_id": 4653234,
            "created_on": "2018-07-25T09:48:46Z",
            "modified_on": "2018-07-25T09:48:46Z",
            "path": "100/056/322/variants/c1611d89-c07e-47be-a781-6fe7331ef3ff.jpg",
            "full_path": "https://sapo.dktcdn.net/100/056/322/variants/c1611d89-c07e-47be-a781-6fe7331ef3ff.jpg",
            "file_name": "c1611d89-c07e-47be-a781-6fe7331ef3ff.jpg",
            "is_default": true
        }
    ]
}
```
**Trường hợp có lỗi**
```
{
    "data_error": {
        "status": 422,
        "errors": {
            "variant": "not exists Variant 463234"
        }
    }
}
```
## 5.2 lấy 1 đối tượng image
**Request**
```
GET /admin/products/{productId}/variants/{variantId}/images/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "image": {
        "id": 1297564,
        "size": 98851,
        "tenant_id": 56322,
        "variant_id": 4653234,
        "created_on": "2018-07-25T09:48:46Z",
        "modified_on": "2018-07-25T09:48:46Z",
        "path": "100/056/322/variants/c1611d89-c07e-47be-a781-6fe7331ef3ff.jpg",
        "full_path": "https://sapo.dktcdn.net/100/056/322/variants/c1611d89-c07e-47be-a781-6fe7331ef3ff.jpg",
        "file_name": "c1611d89-c07e-47be-a781-6fe7331ef3ff.jpg",
        "is_default": true
    }
}
```

## 5.3 Tạo 1 đối tượng image
**Request**
```
POST /admin/products/1297/variants/3321/locations HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
```
**Trường hợp có lỗi**
```
```
## 5.4 Chuyển đổi giá trị mặc định của 1 đối tượng image
**Request**
```
PUT /admin/products/{productId}/variants/{variantId}/images/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
```
**Trường hợp có lỗi**
```
```
## 5.5 Xóa 1 đối tượng image
**Request**
```
DELETE /admin/products/{productId}/variants/{variantId}/images/{id} HTTP/1.1
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
    "data_error": {
        "status": 422,
        "errors": {
            "image": "item id 1297564 not exists"
        }
    }
}
```
# 6. Product category
## 6.1 Lấy danh sách category
**Request**
```
GET /admin/categories/ HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 4,
        "page": 1,
        "limit": 20
    },
    "categories": [
        {
            "id": 197231,
            "tenant_id": 56322,
            "description": null,
            "name": "B1",
            "created_on": "2018-07-25T06:50:01Z",
            "modified_on": "2018-07-25T06:50:01Z",
            "code": "PDG2507184",
            "status": "active",
            "default": false
        },
        {
            "id": 162428,
            "tenant_id": 56322,
            "description": null,
            "name": "Phụ kiện",
            "created_on": "2018-05-12T01:43:03Z",
            "modified_on": "2018-05-12T01:43:03Z",
            "code": "PDG1205183",
            "status": "active",
            "default": false
        },
        {
            "id": 162427,
            "tenant_id": 56322,
            "description": null,
            "name": "Áo khoác",
            "created_on": "2018-05-12T01:42:57Z",
            "modified_on": "2018-05-12T01:42:57Z",
            "code": "PDG1205182",
            "status": "active",
            "default": false
        },
        {
            "id": 162426,
            "tenant_id": 56322,
            "description": null,
            "name": "Quần",
            "created_on": "2018-05-12T01:42:49Z",
            "modified_on": "2018-05-12T01:42:49Z",
            "code": "PDG1205181",
            "status": "active",
            "default": false
        }
    ]
}
```

## 6.2 Lấy 1 đối tượng category
**Request**
```
GET /admin/categories/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "category": {
        "id": 162428,
        "tenant_id": 56322,
        "description": null,
        "name": "Phụ kiện",
        "created_on": "2018-05-12T01:43:03Z",
        "modified_on": "2018-05-12T01:43:03Z",
        "code": "PDG1205183",
        "status": "active",
        "default": false
    }
}
```

## 6.3 Tạo 1 đối tượng category
**Request**
```
POST /admin/categories/ HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "category": {
    "description": null,
    "name": "Default1",
    "created_on": null,
    "modified_on": null,
    "default": true
  }
}
```
**Kết quả trả về**
```
{
    "category": {
        "id": 197358,
        "tenant_id": 56322,
        "description": null,
        "name": "Default1",
        "created_on": "2018-07-25T09:06:24Z",
        "modified_on": "2018-07-25T09:06:24Z",
        "code": "PDG2507185",
        "status": "active",
        "default": false
    }
}
```
**Trường hợp có lỗi**
```
{
    "data_error": {
        "status": 422,
        "errors": {
            "name": "may not be empty"
        }
    }
}
```
## 6.4 Sửa 1 đối tượng category
**Request**
```
PUT /admin/categories/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
```
**Trường hợp có lỗi**
```
```
## 6.5 Xóa 1 đối tượng category
**Request**
```
DELETE /admin/categories/{id} HTTP/1.1
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
        "message": "Không tìm thấy đối tượng"
    }
}
```
