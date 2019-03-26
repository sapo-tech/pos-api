# Đối tác vận chuyển
Đối tác vận chuyển là đối tác liên kết với chủ shop trong việc chuyển hàng đã được đóng gói tới khách hàng. Đối tác vận chuyển có thể là một đối tác ship, hay một nhóm đối tác là một công ty chuyên dịch vụ giao hàng.
Hiện tại ở Sapo liên kết với nhiều hệ thống vận chuyển uy tín tại Việt Nam cho chủ shop có nhiều lựa chọn.
**Các tham số**

[ 1. Thêm mới đối tác vận chuyển ](#add-delivery_service_providers)

[ 2. Cập nhật một đối tác vận chuyển](#put-delivery_service_providers_id)

[ 3. Lấy một đối tượng đối tác vận chuyển](#get-delivery_service_providers_id)

[ 4. Xoá một đối tác vận chuyển ](#delete-delivery_service_providers_id)

[ 5. Lấy danh sách toàn bộ đối tác vận chuyển](#get-delivery_service_providers)

[ 6. Lấy danh sách công nợ shipper](#get-delivery_service_providers_id_debt_change_logs)



<a name="add-delivery_service_providers"></a>
## 1. Thêm mới đối tác vận chuyển
**Request**
```
POST /admin/delivery_service_providers HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "delivery_service_provider": {
    "name": "hoinx01",
    "type": "employee",
    "reference_account_id": null,
    "phone_number": "012394343",
    "address": null,
    "email": null,
    "group_name": null
  }
}
```
**Kết quả trả về**
```
{
  "delivery_service_provider": {
    "id": 1,
    "tenant_id": 77,
    "name": "hoinx01",
    "type": "employee",
    "reference_account_id": null,
    "phone_number": "012394343",
    "address": null,
    "email": null,
    "group_name": null,
    "status": "active",
    "created_on": "2016-10-06T04:16:27Z",
    "modified_on": "2016-10-06T04:17:38Z",
    "init": false,
    "note": null
  }
}
```
<a name="put-delivery_service_providers_id"></a>
## 2. Cập nhật một đối tác vận chuyển
**Request**
```
PUT /admin/delivery_service_providers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
{
  "delivery_service_provider": {
    "name": "hoinx01",
    "type": "employee",
    "reference_account_id": null,
    "phone_number": "012394343",
    "address": null,
    "email": null,
    "group_name": null
  }
}
```
**Kết quả trả về**
```
{
  "delivery_service_provider": {
    "id": 1,
    "tenant_id": 77,
    "name": "hoinx01",
    "type": "employee",
    "reference_account_id": null,
    "phone_number": "012394343",
    "address": null,
    "email": null,
    "group_name": null,
    "status": "active",
    "created_on": "2016-10-06T04:16:27Z",
    "modified_on": "2016-10-06T04:17:38Z",
    "init": false,
    "note": null
  }
}
```
<a name="get-delivery_service_providers_id"></a>
## 3. Lấy một đối tượng đối tác vận chuyển
**Request**
```
GET /admin/delivery_service_providers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "delivery_service_provider": {
        "id": 10355,
        "tenant_id": 56322,
        "code": "DSP0907181",
        "name": "Ship ca nhân",
        "type": "external_shipper",
        "reference_account_id": null,
        "phone_number": "09876534234",
        "address": "dfsd",
        "email": null,
        "group_name": null,
        "status": "active",
        "created_on": "2018-07-09T08:10:28Z",
        "modified_on": "2018-07-09T08:10:28Z",
        "init": false,
        "note": null,
        "shipment_count": 0,
        "total_freight_amount": null,
        "debt": 400000
    }
}
```
<a name="delete-delivery_service_providers_id"></a>
## 4. Xoá một đối tác vận chuyển
**Request**
```
DELETE /admin/delivery_service_providers/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
Staus: 200 OK
```
**Trường hợp có lỗi**
```
{
    "error": {
        "message": "Không tìm thấy đối tượng"
    }
}
```

<a name="get-delivery_service_providers"></a>
## 5. Lấy danh sách toàn bộ đối tác vận chuyển
**Request**
```
GET /admin/delivery_service_providers HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 2,
        "page": 1,
        "limit": 250
    },
    "delivery_service_providers": [
        {
            "id": 11113,
            "tenant_id": 56322,
            "code": "DSP2607181",
            "name": "Giaohangnhanh",
            "type": "external_shipper",
            "reference_account_id": null,
            "phone_number": "09876543211111",
            "address": null,
            "email": null,
            "group_name": null,
            "status": "active",
            "created_on": "2018-07-26T04:12:05Z",
            "modified_on": "2018-07-26T04:12:05Z",
            "init": false,
            "note": null,
            "shipment_count": 0,
            "total_freight_amount": null,
            "debt": null
        },
        {
            "id": 8342,
            "tenant_id": 56322,
            "code": "DSP1205181",
            "name": "Shipper 1",
            "type": "employee",
            "reference_account_id": null,
            "phone_number": "0988524667",
            "address": null,
            "email": null,
            "group_name": null,
            "status": "active",
            "created_on": "2018-05-12T01:54:50Z",
            "modified_on": "2018-05-12T01:54:50Z",
            "init": false,
            "note": null,
            "shipment_count": 5,
            "total_freight_amount": 10000,
            "debt": 0
        }
    ]
}
```
<a name="get-delivery_service_providers_id_debt_change_logs"></a>
## 6. Lấy danh sách công nợ shipper
**Request**
```
GET /admin/delivery_service_providers/{id}/debt_change_logs HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
```
**Kết quả trả về**
```
{
  "metadata": {
    "total": 5,
    "page": 1,
    "limit": 250
  },
  "debt_change_logs": [
    {
      "id": 38,
      "code": null,
      "invoice_code": null,
      "account_name": "Nguyễn Hoàng Linh",
      "document_issued_on": "2017-07-11T07:08:47Z",
      "modified_on": "2017-07-11 07:09:52.943",
      "change_debt": -250000,
      "debt_amount": -315000,
      "location_id": 13245,
      "account_id": 7520,
      "created_on": "2017-07-11T07:09:52Z",
      "document_type": 303,
      "document_id": 256,
      "object_type": 3,
      "object_id": 323,
      "action": "prepayment_added",
      "log_id": 120341,
      "log_type": 3,
      "root_id": 30870
    },
    {
      "id": 34,
      "code": null,
      "invoice_code": null,
      "account_name": "Nguyễn Hoàng Linh",
      "document_issued_on": "2017-07-11T07:08:21Z",
      "modified_on": "2017-07-11 07:09:26.467",
      "change_debt": -15000,
      "debt_amount": -65000,
      "location_id": 13245,
      "account_id": 7520,
      "created_on": "2017-07-11T07:09:26Z",
      "document_type": 301,
      "document_id": 67675,
      "object_type": 3,
      "object_id": 323,
      "action": "fulfillment_fulfilled",
      "log_id": 120338,
      "log_type": 3,
      "root_id": 30870
    },
    {
      "id": 33,
      "code": null,
      "invoice_code": null,
      "account_name": "Nguyễn Hoàng Linh",
      "document_issued_on": "2017-07-11T07:04:26Z",
      "modified_on": "2017-07-11 07:05:30.537",
      "change_debt": -20000,
      "debt_amount": -50000,
      "location_id": 13245,
      "account_id": 7520,
      "created_on": "2017-07-11T07:05:30Z",
      "document_type": 301,
      "document_id": 67662,
      "object_type": 3,
      "object_id": 323,
      "action": "shipment_freight_amount_updated",
      "log_id": 120330,
      "log_type": 3,
      "root_id": 30860
    },
    {
      "id": 32,
      "code": null,
      "invoice_code": null,
      "account_name": "Nguyễn Hoàng Linh",
      "document_issued_on": "2017-07-11T07:03:40Z",
      "modified_on": "2017-07-11 07:04:45.203",
      "change_debt": -10000,
      "debt_amount": -30000,
      "location_id": 13245,
      "account_id": 7520,
      "created_on": "2017-07-11T07:04:45Z",
      "document_type": 301,
      "document_id": 67662,
      "object_type": 3,
      "object_id": 323,
      "action": "shipment_freight_amount_updated",
      "log_id": 120327,
      "log_type": 3,
      "root_id": 30860
    },
    {
      "id": 30,
      "code": null,
      "invoice_code": null,
      "account_name": "Nguyễn Hoàng Linh",
      "document_issued_on": "2017-07-11T06:54:38Z",
      "modified_on": "2017-07-11 06:58:37.693",
      "change_debt": -20000,
      "debt_amount": -20000,
      "location_id": 13245,
      "account_id": 7520,
      "created_on": "2017-07-11T06:58:37Z",
      "document_type": 301,
      "document_id": 67662,
      "object_type": 3,
      "object_id": 323,
      "action": "fulfillment_fulfilled",
      "log_id": 120313,
      "log_type": 3,
      "root_id": 30860
    }
  ]
}
```
