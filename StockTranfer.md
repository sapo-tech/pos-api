# Chuyển hàng

[1. Tạo đơn chuyển hàng](#add-stock_transfers)

[2. Sửa một đơn chuyển hàng ](#put-stock_transfers_id)

[3. Lấy ra một đơn chuyển hàng](#get-stock_transfers_id)

[4. Lấy mã code đơn chuyển hàng](#get-stock_transfers_codes)

[5. Lấy đơn chuyển hàng theo bộ lọc](#get-stock_transfers?)

[6. Thay đổi trạng thái](#stock_transfers_id_status)

**Các tham số**

<a name= "add-stock_transfers"></a>
## 1. Tạo đơn chuyển hàng
**Request**

```
POST /admin/stock_transfers HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "stock_transfer": {
    "tenant_id": 77,
    "source_location_id": 81,
    "destination_location_id": 5072,
    "account_id": 33,
    "code": "ST280616_009",
    "note": null,
    "reference": "hehevvv",
    "status": "active",
    "created_on": "2016-06-28T03:26:44Z",
    "modified_on": "2016-06-28T03:29:21Z",
    "shipped_on": "2016-06-28T03:29:21Z",
    "received_on": null,
    "total_quantity": 0,
    "total_amount": 0,
    "line_items": [
      {
        "stock_transfer_id": 431,
        "variant_id": 18003,
        "product_id": 12787,
        "quantity": 1,
        "price": 400000,
        "position": 0,
        "created_on": "2016-06-28T03:26:44Z",
        "modified_on": "2016-06-28T03:26:44Z"
      }
    ]
  }
}

```
**Kết quả trả về**
```
{
  "stock_transfer": {
    "id": 24,
    "tenant_id": 77,
    "source_location_id": 81,
    "destination_location_id": 8070,
    "account_id": 0,
    "code": "ST06061614",
    "note": null,
    "reference": "hehevvv",
    "status": "active",
    "created_on": "2016-06-06T15:16:35Z",
    "modified_on": "2016-06-06T15:16:35Z",
    "shipped_on": null,
    "received_on": null,
    "total_quantity": 0,
    "total_amount": 0,
    "line_items": [
      {
        "id": 24,
        "stock_transfer_id": 24,
        "variant_id": 12099,
        "product_id": 9195,
        "quantity": 1,
        "price": 0,
        "position": 0,
        "created_on": "2016-06-06T15:16:35Z",
        "modified_on": "2016-06-06T15:16:35Z"
      }
    ]
  }
}
```
<a name= "put-stock_transfers_id"></a>
## 2. Sửa một đơn chuyển hàng 

**Request**
```
PUT /admin/stock_transfers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "stock_transfer": {
    "id": 24,
    "tenant_id": 77,
    "source_location_id": 81,
    "destination_location_id": 8070,
    "account_id": 0,
    "code": "ST06061614",
    "note": null,
    "reference": "hehevvv",
    "status": "active",
    "created_on": "2016-06-06T15:16:35Z",
    "modified_on": "2016-06-06T15:16:35Z",
    "shipped_on": null,
    "received_on": null,
    "total_quantity": 0,
    "total_amount": 0,
    "line_items": [
      {
        "id": 24,
        "stock_transfer_id": 24,
        "variant_id": 12099,
        "product_id": 9195,
        "quantity": 1,
        "price": 0,
        "position": 0,
        "created_on": "2016-06-06T15:16:35Z",
        "modified_on": "2016-06-06T15:16:35Z"
      }
    ]
  }
}
```
**Kết quả trả về**
```
{
  "stock_transfer": {
    "id": 24,
    "tenant_id": 77,
    "source_location_id": 81,
    "destination_location_id": 8070,
    "account_id": 0,
    "code": "ST06061614",
    "note": null,
    "reference": "hehevvv",
    "status": "active",
    "created_on": "2016-06-06T15:16:35Z",
    "modified_on": "2016-06-06T15:16:35Z",
    "shipped_on": null,
    "received_on": null,
    "total_quantity": 0,
    "total_amount": 0,
    "line_items": [
      {
        "id": 24,
        "stock_transfer_id": 24,
        "variant_id": 12099,
        "product_id": 9195,
        "quantity": 1,
        "price": 0,
        "position": 0,
        "created_on": "2016-06-06T15:16:35Z",
        "modified_on": "2016-06-06T15:16:35Z"
      }
    ]
  }
}
```

<a name= "get-stock_transfers_id"></a>
## 3. Lấy ra một đơn chuyển hàng

**Request**
```
GET /admin/stock_transfers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "stock_transfer": {
        "id": 219666,
        "tenant_id": 21406,
        "source_location_id": 22322,
        "destination_location_id": 30072,
        "account_id": 25153,
        "code": "ST2807181",
        "note": null,
        "reference": null,
        "status": "active",
        "created_on": "2018-07-28T04:47:05Z",
        "modified_on": "2018-07-28T04:47:05Z",
        "shipped_on": null,
        "received_on": null,
        "total_quantity": 1,
        "total_amount": 0,
        "line_items": [
            {
                "id": 1597625,
                "stock_transfer_id": 219666,
                "variant_id": 1376284,
                "product_id": 1015973,
                "quantity": 1,
                "price": 0,
                "position": 0,
                "created_on": "2018-07-28T04:47:05Z",
                "modified_on": "2018-07-28T04:47:05Z"
            }
        ]
    }
}
```
<a name= "add-customer_groups"></a>
## 4. Tạo mã code đơn chuyển hàng
**Request**
```
POST /admin/stock_transfers/codes HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "stock_transfer": {
        "code": "ST3007181",
        "tenant_id": 21406
    }
}
```
<a name="get-stock_transfers?"></a>
## 5. Lấy đơn chuyển hàng theo bộ lọc

**Request**
```
POST /admin/stock_transfers HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

params: statuses = draft
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 1,
        "page": 1,
        "limit": 250
    },
    "stock_transfers": [
        {
            "id": 85778,
            "tenant_id": 21406,
            "source_location_id": 22322,
            "destination_location_id": 30072,
            "account_id": 25153,
            "code": "ST001",
            "note": null,
            "reference": null,
            "status": "draft",
            "created_on": "2017-10-14T02:32:10Z",
            "modified_on": "2017-10-14T02:32:10Z",
            "shipped_on": null,
            "received_on": null,
            "total_quantity": 90,
            "total_amount": 0,
            "line_items": [
                {
                    "id": 547876,
                    "stock_transfer_id": 85778,
                    "variant_id": 1376280,
                    "product_id": 1015969,
                    "quantity": 10,
                    "price": 0,
                    "position": 0,
                    "created_on": "2017-10-14T02:32:10Z",
                    "modified_on": "2017-10-14T02:32:10Z"
                },
                {
                    "id": 547877,
                    "stock_transfer_id": 85778,
                    "variant_id": 1376279,
                    "product_id": 1015968,
                    "quantity": 10,
                    "price": 0,
                    "position": 1,
                    "created_on": "2017-10-14T02:32:10Z",
                    "modified_on": "2017-10-14T02:32:10Z"
                },
                {
                    "id": 547878,
                    "stock_transfer_id": 85778,
                    "variant_id": 1376278,
                    "product_id": 1015967,
                    "quantity": 10,
                    "price": 0,
                    "position": 2,
                    "created_on": "2017-10-14T02:32:10Z",
                    "modified_on": "2017-10-14T02:32:10Z"
                },
                {
                    "id": 547879,
                    "stock_transfer_id": 85778,
                    "variant_id": 1376277,
                    "product_id": 1015966,
                    "quantity": 10,
                    "price": 0,
                    "position": 3,
                    "created_on": "2017-10-14T02:32:10Z",
                    "modified_on": "2017-10-14T02:32:10Z"
                },
                {
                    "id": 547880,
                    "stock_transfer_id": 85778,
                    "variant_id": 1376276,
                    "product_id": 1015965,
                    "quantity": 10,
                    "price": 0,
                    "position": 4,
                    "created_on": "2017-10-14T02:32:10Z",
                    "modified_on": "2017-10-14T02:32:10Z"
                },
                {
                    "id": 547881,
                    "stock_transfer_id": 85778,
                    "variant_id": 1376275,
                    "product_id": 1015964,
                    "quantity": 10,
                    "price": 0,
                    "position": 5,
                    "created_on": "2017-10-14T02:32:10Z",
                    "modified_on": "2017-10-14T02:32:10Z"
                },
                {
                    "id": 547882,
                    "stock_transfer_id": 85778,
                    "variant_id": 1376274,
                    "product_id": 1015963,
                    "quantity": 10,
                    "price": 0,
                    "position": 6,
                    "created_on": "2017-10-14T02:32:10Z",
                    "modified_on": "2017-10-14T02:32:10Z"
                },
                {
                    "id": 547883,
                    "stock_transfer_id": 85778,
                    "variant_id": 1375790,
                    "product_id": 1015515,
                    "quantity": 10,
                    "price": 0,
                    "position": 7,
                    "created_on": "2017-10-14T02:32:10Z",
                    "modified_on": "2017-10-14T02:32:10Z"
                },
                {
                    "id": 547884,
                    "stock_transfer_id": 85778,
                    "variant_id": 1353127,
                    "product_id": 998156,
                    "quantity": 10,
                    "price": 0,
                    "position": 8,
                    "created_on": "2017-10-14T02:32:10Z",
                    "modified_on": "2017-10-14T02:32:10Z"
                }
            ]
        }
    ]
}
```
<a name="stock_transfers_id_status"></a>
## 6. Thay đổi trạng thái 

**Request**
```
POST /admin/stock_transfers/{id}/{status} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
status=draft
{
  "stock_transfer":{
    "shipped_on":"2018-01-01",
    "received_on":"2018-02-02"
  }
}
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
            "status": "Chỉ xác nhận được đơn ở trạng thái nháp"
        }
    }
}
```
