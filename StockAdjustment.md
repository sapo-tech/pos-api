# Kiểm hàng

[1. Lấy đơn kiểm hàng theo bộ lọc](#get-stock_adjustments?)

[2. Lấy ra một đơn kiểm hàng](#get-stock_adjustments_id)

[3. Lấy mã code đơn kiểm hàng](#get-stock_adjustments_codes)

[4. Hủy đơn kiểm hàng](#cancel-stock_adjustments)

[5. Cập nhật một đơn kiểm hàng ](#put-stock_adjustments_id)

[6. Thêm mới một đơn kiểm hàng ](#add-stock_adjustments_id)

[7. Cập nhật trạng thái đơn kiểm hàng ](#put-stock_adjustments_id_status)

**Các tham số**

<a name= "get-stock_adjustments?"></a>
## 1. Lấy đơn kiểm hàng theo bộ lọc
**Request**

```
GET admin/stock_adjustments HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
param: limit=10000
```
**Kết quả trả về**
```
{
    "metadata": {
        "total": 12,
        "page": 1,
        "limit": 10000
    },
    "stock_adjustments": [
        {
            "id": 168857,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA1605181",
            "status": "adjusted",
            "created_on": "2018-05-16T10:22:01Z",
            "modified_on": "2018-05-16T10:22:02Z",
            "adjusted_on": "2018-05-16T10:22:02Z",
            "note": null,
            "reason": null,
            "total": 11,
            "line_items": [
                {
                    "id": 3299508,
                    "stock_adjustment_id": 168857,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2018-05-16T10:22:01Z",
                    "modified_on": "2018-05-16T10:22:01Z",
                    "variant_id": 4320829,
                    "product_id": 3118292,
                    "position": 0,
                    "after_quantity": 11,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                }
            ],
            "tags": null
        },
        {
            "id": 88633,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA1311171",
            "status": "active",
            "created_on": "2017-11-13T02:03:02Z",
            "modified_on": "2017-11-13T02:03:02Z",
            "adjusted_on": null,
            "note": null,
            "reason": null,
            "total": 1,
            "line_items": [
                {
                    "id": 2407287,
                    "stock_adjustment_id": 88633,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-11-13T02:03:02Z",
                    "modified_on": "2017-11-13T02:03:02Z",
                    "variant_id": 2466652,
                    "product_id": 1797811,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                }
            ],
            "tags": null
        },
        {
            "id": 77052,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA1710171",
            "status": "active",
            "created_on": "2017-10-17T07:33:31Z",
            "modified_on": "2017-10-17T07:33:31Z",
            "adjusted_on": null,
            "note": null,
            "reason": null,
            "total": 90,
            "line_items": [
                {
                    "id": 891412,
                    "stock_adjustment_id": 77052,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-17T07:33:31Z",
                    "modified_on": "2017-10-17T07:33:31Z",
                    "variant_id": 1376280,
                    "product_id": 1015969,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "Hao mòn",
                    "reason": "Hao mòn"
                },
                {
                    "id": 891413,
                    "stock_adjustment_id": 77052,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-17T07:33:31Z",
                    "modified_on": "2017-10-17T07:33:31Z",
                    "variant_id": 1376279,
                    "product_id": 1015968,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "Trả hàng",
                    "reason": "Trả hàng"
                },
                {
                    "id": 891414,
                    "stock_adjustment_id": 77052,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-17T07:33:31Z",
                    "modified_on": "2017-10-17T07:33:31Z",
                    "variant_id": 1376278,
                    "product_id": 1015967,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "Hư hỏng",
                    "reason": "Hư hỏng"
                },
                {
                    "id": 891415,
                    "stock_adjustment_id": 77052,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-17T07:33:31Z",
                    "modified_on": "2017-10-17T07:33:31Z",
                    "variant_id": 1376277,
                    "product_id": 1015966,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "Chuyển hàng",
                    "reason": "Chuyển hàng"
                },
                {
                    "id": 891416,
                    "stock_adjustment_id": 77052,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-17T07:33:31Z",
                    "modified_on": "2017-10-17T07:33:31Z",
                    "variant_id": 1376276,
                    "product_id": 1015965,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "Sản xuất hàng hóa",
                    "reason": "Sản xuất hàng hóa"
                },
                {
                    "id": 891417,
                    "stock_adjustment_id": 77052,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-17T07:33:31Z",
                    "modified_on": "2017-10-17T07:33:31Z",
                    "variant_id": 1376275,
                    "product_id": 1015964,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "Khác",
                    "reason": "Khác"
                },
                {
                    "id": 891418,
                    "stock_adjustment_id": 77052,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-17T07:33:31Z",
                    "modified_on": "2017-10-17T07:33:31Z",
                    "variant_id": 1376274,
                    "product_id": 1015963,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "Khác",
                    "reason": "Khác"
                },
                {
                    "id": 891419,
                    "stock_adjustment_id": 77052,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-17T07:33:31Z",
                    "modified_on": "2017-10-17T07:33:31Z",
                    "variant_id": 1375790,
                    "product_id": 1015515,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "Khác",
                    "reason": "Khác"
                },
                {
                    "id": 891420,
                    "stock_adjustment_id": 77052,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-17T07:33:31Z",
                    "modified_on": "2017-10-17T07:33:31Z",
                    "variant_id": 1353127,
                    "product_id": 998156,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "Khác",
                    "reason": "Khác"
                }
            ],
            "tags": null
        },
        {
            "id": 75400,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "KK87",
            "status": "active",
            "created_on": "2017-10-14T02:30:14Z",
            "modified_on": "2017-10-14T02:30:14Z",
            "adjusted_on": null,
            "note": null,
            "reason": null,
            "total": 90,
            "line_items": [
                {
                    "id": 883856,
                    "stock_adjustment_id": 75400,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-14T02:30:14Z",
                    "modified_on": "2017-10-14T02:30:14Z",
                    "variant_id": 1376280,
                    "product_id": 1015969,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "",
                    "reason": "Khác"
                },
                {
                    "id": 883857,
                    "stock_adjustment_id": 75400,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-14T02:30:14Z",
                    "modified_on": "2017-10-14T02:30:14Z",
                    "variant_id": 1376279,
                    "product_id": 1015968,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "",
                    "reason": "Khác"
                },
                {
                    "id": 883858,
                    "stock_adjustment_id": 75400,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-14T02:30:14Z",
                    "modified_on": "2017-10-14T02:30:14Z",
                    "variant_id": 1376278,
                    "product_id": 1015967,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "",
                    "reason": "Khác"
                },
                {
                    "id": 883859,
                    "stock_adjustment_id": 75400,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-14T02:30:14Z",
                    "modified_on": "2017-10-14T02:30:14Z",
                    "variant_id": 1376277,
                    "product_id": 1015966,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "",
                    "reason": "Khác"
                },
                {
                    "id": 883860,
                    "stock_adjustment_id": 75400,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-14T02:30:14Z",
                    "modified_on": "2017-10-14T02:30:14Z",
                    "variant_id": 1376276,
                    "product_id": 1015965,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "",
                    "reason": "Khác"
                },
                {
                    "id": 883861,
                    "stock_adjustment_id": 75400,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-14T02:30:14Z",
                    "modified_on": "2017-10-14T02:30:14Z",
                    "variant_id": 1376275,
                    "product_id": 1015964,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "",
                    "reason": "Khác"
                },
                {
                    "id": 883862,
                    "stock_adjustment_id": 75400,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-14T02:30:14Z",
                    "modified_on": "2017-10-14T02:30:14Z",
                    "variant_id": 1376274,
                    "product_id": 1015963,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "",
                    "reason": "Khác"
                },
                {
                    "id": 883863,
                    "stock_adjustment_id": 75400,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-14T02:30:14Z",
                    "modified_on": "2017-10-14T02:30:14Z",
                    "variant_id": 1375790,
                    "product_id": 1015515,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "",
                    "reason": "Khác"
                },
                {
                    "id": 883864,
                    "stock_adjustment_id": 75400,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-10-14T02:30:14Z",
                    "modified_on": "2017-10-14T02:30:14Z",
                    "variant_id": 1353127,
                    "product_id": 998156,
                    "position": 0,
                    "after_quantity": 10,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": "",
                    "reason": "Khác"
                }
            ],
            "tags": null
        },
        {
            "id": 68219,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA1809171",
            "status": "active",
            "created_on": "2017-09-18T09:42:16Z",
            "modified_on": "2017-09-18T09:55:55Z",
            "adjusted_on": null,
            "note": null,
            "reason": null,
            "total": 3,
            "line_items": [
                {
                    "id": 817875,
                    "stock_adjustment_id": 68219,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-09-18T09:55:55Z",
                    "modified_on": "2017-09-18T09:55:55Z",
                    "variant_id": 1974968,
                    "product_id": 1463485,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                },
                {
                    "id": 817876,
                    "stock_adjustment_id": 68219,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-09-18T09:55:55Z",
                    "modified_on": "2017-09-18T09:55:55Z",
                    "variant_id": 1961752,
                    "product_id": 1453952,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                },
                {
                    "id": 817877,
                    "stock_adjustment_id": 68219,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-09-18T09:55:55Z",
                    "modified_on": "2017-09-18T09:55:55Z",
                    "variant_id": 1930323,
                    "product_id": 1432513,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                }
            ],
            "tags": "ád,b,ẻyrty,n,nmghj,nv,r,sdf,u,ut,v,vb,bn,bnvm,cvb,h,hfg,hj,hjk,k,m,nm"
        },
        {
            "id": 65728,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA0809171",
            "status": "active",
            "created_on": "2017-09-08T04:01:18Z",
            "modified_on": "2017-09-08T04:02:31Z",
            "adjusted_on": null,
            "note": "ád",
            "reason": null,
            "total": 3,
            "line_items": [
                {
                    "id": 751450,
                    "stock_adjustment_id": 65728,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-09-08T04:01:18Z",
                    "modified_on": "2017-09-08T04:01:18Z",
                    "variant_id": 1974968,
                    "product_id": 1463485,
                    "position": 0,
                    "after_quantity": 2,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                },
                {
                    "id": 751451,
                    "stock_adjustment_id": 65728,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-09-08T04:01:18Z",
                    "modified_on": "2017-09-08T04:01:18Z",
                    "variant_id": 1881375,
                    "product_id": 1402259,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                }
            ],
            "tags": "á,ádas,d,das,dasdas,s,sadasdas"
        },
        {
            "id": 63680,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA3008172",
            "status": "adjusted",
            "created_on": "2017-08-30T03:30:32Z",
            "modified_on": "2017-08-30T03:30:35Z",
            "adjusted_on": "2017-08-30T03:30:35Z",
            "note": null,
            "reason": null,
            "total": 10.56,
            "line_items": [
                {
                    "id": 717864,
                    "stock_adjustment_id": 63680,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-08-30T03:30:32Z",
                    "modified_on": "2017-08-30T03:30:32Z",
                    "variant_id": 1961752,
                    "product_id": 1453952,
                    "position": 0,
                    "after_quantity": 10.56,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                }
            ],
            "tags": null
        },
        {
            "id": 63677,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA3008171",
            "status": "cancelled",
            "created_on": "2017-08-30T03:22:02Z",
            "modified_on": "2017-08-30T03:25:04Z",
            "adjusted_on": "2017-08-30T03:22:06Z",
            "note": null,
            "reason": null,
            "total": 72,
            "line_items": [
                {
                    "id": 717861,
                    "stock_adjustment_id": 63677,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-08-30T03:22:02Z",
                    "modified_on": "2017-08-30T03:22:02Z",
                    "variant_id": 1961752,
                    "product_id": 1453952,
                    "position": 0,
                    "after_quantity": 72,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                }
            ],
            "tags": null
        },
        {
            "id": 61219,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA2108171",
            "status": "adjusted",
            "created_on": "2017-08-21T04:18:10Z",
            "modified_on": "2017-08-21T04:18:12Z",
            "adjusted_on": "2017-08-21T04:18:12Z",
            "note": null,
            "reason": null,
            "total": 4,
            "line_items": [
                {
                    "id": 672411,
                    "stock_adjustment_id": 61219,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-08-21T04:18:10Z",
                    "modified_on": "2017-08-21T04:18:10Z",
                    "variant_id": 1376300,
                    "product_id": 1015970,
                    "position": 0,
                    "after_quantity": 4,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                }
            ],
            "tags": null
        },
        {
            "id": 49352,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA2407171",
            "status": "active",
            "created_on": "2017-07-24T02:03:47Z",
            "modified_on": "2017-09-08T03:58:41Z",
            "adjusted_on": null,
            "note": null,
            "reason": null,
            "total": 8,
            "line_items": [
                {
                    "id": 537189,
                    "stock_adjustment_id": 49352,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-07-24T02:03:47Z",
                    "modified_on": "2017-07-24T02:04:00Z",
                    "variant_id": 1639481,
                    "product_id": 1210891,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                },
                {
                    "id": 537190,
                    "stock_adjustment_id": 49352,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-07-24T02:03:47Z",
                    "modified_on": "2017-07-24T02:04:00Z",
                    "variant_id": 1600835,
                    "product_id": 1184649,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                },
                {
                    "id": 537191,
                    "stock_adjustment_id": 49352,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-07-24T02:03:47Z",
                    "modified_on": "2017-07-24T02:04:00Z",
                    "variant_id": 1631027,
                    "product_id": 1203624,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                },
                {
                    "id": 537192,
                    "stock_adjustment_id": 49352,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-07-24T02:03:47Z",
                    "modified_on": "2017-07-24T02:04:00Z",
                    "variant_id": 1376286,
                    "product_id": 1015975,
                    "position": 0,
                    "after_quantity": 2,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                },
                {
                    "id": 537193,
                    "stock_adjustment_id": 49352,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-07-24T02:03:47Z",
                    "modified_on": "2017-07-24T02:04:00Z",
                    "variant_id": 1376279,
                    "product_id": 1015968,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                },
                {
                    "id": 537194,
                    "stock_adjustment_id": 49352,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-07-24T02:03:47Z",
                    "modified_on": "2017-07-24T02:04:00Z",
                    "variant_id": 1461401,
                    "product_id": 1083647,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                },
                {
                    "id": 537195,
                    "stock_adjustment_id": 49352,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-07-24T02:03:47Z",
                    "modified_on": "2017-07-24T02:04:00Z",
                    "variant_id": 1376280,
                    "product_id": 1015969,
                    "position": 0,
                    "after_quantity": 1,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                }
            ],
            "tags": null
        },
        {
            "id": 32328,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA2305172",
            "status": "adjusted",
            "created_on": "2017-05-23T03:22:43Z",
            "modified_on": "2017-05-23T03:22:45Z",
            "adjusted_on": "2017-05-23T03:22:45Z",
            "note": null,
            "reason": null,
            "total": 70,
            "line_items": [
                {
                    "id": 306699,
                    "stock_adjustment_id": 32328,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-05-23T03:22:43Z",
                    "modified_on": "2017-05-23T03:22:43Z",
                    "variant_id": 1138320,
                    "product_id": 830784,
                    "position": 0,
                    "after_quantity": 70,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                }
            ],
            "tags": null
        },
        {
            "id": 32327,
            "tenant_id": 21406,
            "location_id": 22322,
            "account_id": 25153,
            "code": "IA2305171",
            "status": "adjusted",
            "created_on": "2017-05-23T03:20:57Z",
            "modified_on": "2017-05-23T03:21:33Z",
            "adjusted_on": "2017-05-23T03:21:33Z",
            "note": null,
            "reason": null,
            "total": 73,
            "line_items": [
                {
                    "id": 306698,
                    "stock_adjustment_id": 32327,
                    "tenant_id": 21406,
                    "location_id": 22322,
                    "created_on": "2017-05-23T03:20:57Z",
                    "modified_on": "2017-05-23T03:20:57Z",
                    "variant_id": 1138320,
                    "product_id": 830784,
                    "position": 0,
                    "after_quantity": 73,
                    "adjusted_quantity": null,
                    "price": 0,
                    "note": null,
                    "reason": "Khác"
                }
            ],
            "tags": null
        }
    ]
}
```
<a name= "get-stock_adjustments_id"></a>
## 2. Lấy ra một đơn kiểm hàng
**Request**
```
GET admin/stock_adjustments/{id}} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "stock_adjustment": {
        "id": 168857,
        "tenant_id": 21406,
        "location_id": 22322,
        "account_id": 25153,
        "code": "IA1605181",
        "status": "adjusted",
        "created_on": "2018-05-16T10:22:01Z",
        "modified_on": "2018-05-16T10:22:02Z",
        "adjusted_on": "2018-05-16T10:22:02Z",
        "note": null,
        "reason": null,
        "total": 11,
        "line_items": [
            {
                "id": 3299508,
                "stock_adjustment_id": 168857,
                "tenant_id": 21406,
                "location_id": 22322,
                "created_on": "2018-05-16T10:22:01Z",
                "modified_on": "2018-05-16T10:22:01Z",
                "variant_id": 4320829,
                "product_id": 3118292,
                "position": 0,
                "after_quantity": 11,
                "adjusted_quantity": 1,
                "price": 0,
                "note": null,
                "reason": "Khác"
            }
        ],
        "tags": null
    }
}
```

<a name= "get-stock_adjustments_codes"></a>
## 3. Lấy mã code đơn kiểm hàng

**Request**
```
POST admin/stock_adjustments/codes HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
{
    "stock_adjustment": {
        "tenant_id": 21406,
        "code": "IA0308181"
    }
}
```
<a name= "cancel-stock_adjustments"></a>
## 4. Hủy đơn kiểm hàng
Hệ thống sẽ hủy đơn nếu đơn ở trạng thái adjusted : adjusted -> cancelled
Xóa đơn nếu ở trạng thái active : active -> deleted
**Request**
```
POST admin/stock_adjustments/{id}/cancel HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

```
**Kết quả trả về**
```
Status 200 OK
```
<a name="put-stock_adjustments_id"></a>
## 5. Cập nhật một đơn kiểm hàng 

**Request**
```
PUT admin/stock_adjustments/{id} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json

params: statuses = draft
```
**Kết quả trả về**
```

```
<a name="add-stock_adjustments_id"></a>
## 6. Thêm mới một đơn kiểm hàng

**Request**
```
POST admin/stock_adjustments HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
status=draft

```
**Kết quả trả về**
```
Status 200 OK
```
**Trường hợp có lỗi**
```

```
<a name="put-stock_adjustments_id_status"></a>
## 7. Cập nhật trạng thái đơn kiểm hàng
**Request**
```
POST admin/stock_adjustments/{id}/{status} HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
status=draft

```
**Kết quả trả về**
```
{
    "stock_adjustment": {
        "id": 68219,
        "tenant_id": 21406,
        "location_id": 22322,
        "account_id": 25153,
        "code": "IA1809171",
        "status": "adjusted",
        "created_on": "2017-09-18T09:42:16Z",
        "modified_on": "2018-08-03T07:36:04Z",
        "adjusted_on": "2018-08-03T07:36:04Z",
        "note": null,
        "reason": null,
        "total": 3,
        "line_items": [
            {
                "id": 817875,
                "stock_adjustment_id": 0,
                "tenant_id": 0,
                "location_id": 0,
                "created_on": "2017-09-18T09:55:55Z",
                "modified_on": "2017-09-18T09:55:55Z",
                "variant_id": 1974968,
                "product_id": 1463485,
                "position": 0,
                "after_quantity": 1,
                "adjusted_quantity": null,
                "price": null,
                "note": null,
                "reason": "Khác"
            },
            {
                "id": 817876,
                "stock_adjustment_id": 0,
                "tenant_id": 0,
                "location_id": 0,
                "created_on": "2017-09-18T09:55:55Z",
                "modified_on": "2017-09-18T09:55:55Z",
                "variant_id": 1961752,
                "product_id": 1453952,
                "position": 0,
                "after_quantity": 1,
                "adjusted_quantity": null,
                "price": null,
                "note": null,
                "reason": "Khác"
            },
            {
                "id": 817877,
                "stock_adjustment_id": 0,
                "tenant_id": 0,
                "location_id": 0,
                "created_on": "2017-09-18T09:55:55Z",
                "modified_on": "2017-09-18T09:55:55Z",
                "variant_id": 1930323,
                "product_id": 1432513,
                "position": 0,
                "after_quantity": 1,
                "adjusted_quantity": null,
                "price": null,
                "note": null,
                "reason": "Khác"
            }
        ],
        "tags": "ád,b,ẻyrty,n,nmghj,nv,r,sdf,u,ut,v,vb,bn,bnvm,cvb,h,hfg,hj,hjk,k,m,nm"
    }
}
```
**Trường hợp có lỗi**
```

```

