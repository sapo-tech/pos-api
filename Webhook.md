# Webhooks
Một Webhook là một công cụ để truy vấn và lưu trữ dữ liệu của một Event xác định. Bạn có thể đăng ký đường dẫn http:// hoặc https:// - nơi mà dữ liệu của Event được lưu trữ dưới dạng XML hoặc JSON. Webhook có thể được đăng ký cho các Event sau

| Chức năng| Method |
| ------------- |:-------------|
| App	| installed |
| Product |	create/update/delete |
| Order |	create/update/cancelled/delete/active/finalized/invoiced/partial_invoiced/fulfilled/partial_fulfilled/paid/partial_paid |
| Order | Transaction	create |
| Customer | create/delete/update |
| Order Return | create/update/cancelled/returned/partial_refund/refund |
| Inventory |	update |
## Bạn có thể làm gì với Webhooks?
Sapo API cho phép bạn thực hiện các thao tác sau với tài nguyên Product. Các phiên bản chi tiết hơn của những thao tác này có thể có

***[GET /admin/webhooks.json]***

Lấy danh sách tất cả các Webhook

**Kết quả trả về**
```
GET /admin/webhooks.json
HTTP/1.1 200 OK

{
    "webhooks": [
        {
            "id": 290218,
            "address": "https://chungps1.mysapo.vn/integration/listeners/bizweb-channel/bizweb-customers",
            "format": "json",
            "topic": "customers/delete",
            "created_on": "2018-04-04T04:20:50Z",
            "modified_on": null
        },
        {
            "id": 290217,
            "address": "https://chungps1.mysapo.vn/integration/listeners/bizweb-channel/bizweb-customers",
            "format": "json",
            "topic": "customers/update",
            "created_on": "2018-04-04T04:20:50Z",
            "modified_on": null
        },
        {
            "id": 290216,
            "address": "https://chungps1.mysapo.vn/integration/listeners/bizweb-channel/bizweb-customers",
            "format": "json",
            "topic": "customers/create",
            "created_on": "2018-04-04T04:20:50Z",
            "modified_on": null
        },
        {
            "id": 290215,
            "address": "https://chungps1.mysapo.vn/integration/listeners/bizweb-channel/bizweb-products",
            "format": "json",
            "topic": "products/delete",
            "created_on": "2018-04-04T04:20:50Z",
            "modified_on": null
        },
        {
            "id": 290213,
            "address": "https://chungps1.mysapo.vn/integration/listeners/bizweb-channel/bizweb-products",
            "format": "json",
            "topic": "products/create",
            "created_on": "2018-04-04T04:20:49Z",
            "modified_on": null
        },
        {
            "id": 289173,
            "address": "http://requestbin.fullcontact.com/1iw51kj1",
            "format": "json",
            "topic": "orders/create",
            "created_on": "2018-04-02T06:36:32Z",
            "modified_on": null
        }
    ]
}

``` 

***[GET /admin/webhooks/{id}.json]***

Lấy một Webhook

**Kết quả trả về**
```
GET /admin/webhooks/{id}.json
HTTP/1.1 200 OK
{
  "webhook": {
    "id": 4759306,
    "address": "http:\/\/apple.com",
    "topic": "orders\/create",
    "created_on": "2016-01-20T13:00:56Z",
    "modified_on": "2016-01-20T13:00:56Z",
    "format": "json"
    
  }
}

```
***[POST /admin/webhooks.json]***

Tạo mới một Webhook

```
POST /admin/webhooks.json
HTTP/1.1 200 OK
"{
  ""webhook"": {
    ""topic"": ""orders/create"",
    ""address"": ""http://whatever.hostname.com/"",
    ""format"": ""json""
  }
}"
```

**Kết quả trả về**

```
"{
            ""id"": 290218,
            ""address"": ""https://chungps1.mysapo.vn/integration/listeners/bizweb-channel/bizweb-customers"",
            ""format"": ""json"",
            ""topic"": ""orders/create"",
            ""created_on"": ""2018-04-04T04:20:50Z"",
            ""modified_on"": null
        }"
```
***[PUT /admin/webhooks/{id}.json]***

Cập nhật một Webhook
```
PUT /admin/webhooks/{id}.json
HTTP/1.1 200 OK

"{
  ""webhook"": {
    ""id"": 4759306,
    ""address"": ""http://somewhere-else.com/""
  }
}"
```

**Kết quả trả về**

```
"{
            ""id"": 4759306,
            ""address"": ""https://chungps1.mysapo.vn/integration/listeners/bizweb-channel/bizweb-customers"",
            ""format"": ""json"",
            ""topic"": ""orders/create"",
            ""created_on"": ""2018-04-04T04:20:50Z"",
            ""modified_on"": null
        }"
```
***[GET /admin/webhooks/{id}.json]***


Lấy chi tiết danh sách Webhook

**Kết quả trả về**
```
"{
            ""id"": 4759306,
            ""address"": ""https://chungps1.mysapo.vn/integration/listeners/bizweb-channel/bizweb-customers"",
            ""format"": ""json"",
            ""topic"": ""orders/create"",
            ""created_on"": ""2018-04-04T04:20:50Z"",
            ""modified_on"": null
        }"
```

## Các thuộc tính của Webhooks
|  |  |
| ------------- |:-------------|
| address | { "address" : "http://whatever.hostname.com/" } . Địa chỉ URI mà Webhook sẽ gửi một POST Request đến khi có Event xảy ra. |
| created_on | { "created_on" : "2012-09-28T11:50:07-04:00" } Thời gian Webhook được tạo. API trả về kết quả theo định dạng chuẩn ISO 8601. |
| format | { "format" : "json" } . Định dạng kiểu dữ liệu mà Webhook trả về. Các giá trị hợp lệ là json và xml. |
| id | { "id" : 4759306 } . Số duy nhất định danh Webhook. |
| topic | { "topic" : "orders/create" } . Event mà khi xảy ra sẽ thực hiện lời gọi Webhook. Các giá trị hợp lệ là: products/create, products/delete, products/update, orders/create, orders/update, orders/cancelled, orders/delete, orders/active, orders/finalized, orders/invoiced, orders/partial_invoiced, orders/fulfilled, orders/partial_fulfilled, orders/paid, orders/partial_paid, customers/create, customers/update, customers/delete, suppliers/create, suppliers/update, suppliers/delete, order_returns/create, order_returns/update, order_returns/cancelled, order_returns/returned, order_returns/partial_refund, order_returns/refund, inventories/update |
| modified_on | { "modified_on" : "2012-09-28T11:50:07-04:00" } . Thời gian Webhook được cập nhật. API trả về kết quả theo định dạng chuẩn ISO 8601. |

