# OAuth
App của bạn không thể lấy dữ liệu từ Sapo nếu không thực hiện bước xác thực đầu tiên. Một người dùng muốn truy vấn vào bất cứ tài nguyên nào qua REST API đều phải xin quyền. Bài viết này sẽ hướng dẫn bạn toàn bộ quá trình xác thực (bạn có thể xem chi tiết hơn ở [OAuth 2.0 specification](https://tools.ietf.org/html/rfc6749).
Các bước được đề cập đến trong bài viết:
```
Bước 1: Lấy thông tin client’s credentials
Bước 2: Xin cấp quyền
Bước 3: Thực hiện cài đặt
Bước 4: Tạo các Request đã được xác thực
Scopes
Verification
```
# Thuật ngữ
Trước khi đi vào một khía cạnh quan trọng nhất của quá trình xác thực, hãy cùng tìm hiểu qua một vài thuật ngữ mà chúng ta sẽ sử dụng trong phần còn lại của hướng dẫn.

* Client
Bất cứ ứng dụng nào muốn truy cập vào dữ liệu của Shop. Một người dùng quản trị (thường là chủ Shop) phải cấp quyền trước khi Client có thể truy cập vào bất kỳ dữ liệu nào của Shop.
* API
REST API của Sapo. Đây là nơi mà Client có thể xem và chỉnh sửa dữ liệu của Shop.
* User
Một tài khoản phía quản trị của Sapo, thường là chủ Shop. Đây à người cấp quyền cho Client để truy vấn vào dữ liệu của Shop thông qua REST API.
## Bước 1: Lấy chứng chỉ (credentials) của Client
Bạn cần lấy API Key và Secret Key để định danh Client trong suốt quá trình xác thực.

**Để lấy chứng chỉ:**

1. Click để mở [trang danh sách Apps trong màn hình quản lý của Partner](https://developers.sapo.vn/services/partners/auth?returnUrl=%2Fservices%2Fpartners%2Fapi_clients)

2. Click vào tên App để xem thông tin chi tiết

3. Thông tin API Key và Secret Key được hiển thị.

## Bước 2: Xin cấp quyền
Bước đầu tiên của quá trình là lấy xác thực từ User. Việc này được thực hiện bằng cách hiển thị màn hình xin quyền được cung cấp bởi Sapo:

Để hiển thị màn hình xin quyền, Redirect User về địa chỉ URL này:
```
https://{store}.mysapo.vn/admin/oauth/authorize?client_id={api_key}&scope={scopes}&redirect_uri={redirect_uri}

```
Với các giá trị tương ứng như sau:

`{store}` - tên của Shop.
`{api_key}` - API Key.
`{scopes}` - danh sách [copes](#Scopes), cách nhau bởi dấu phẩy. Ví dụ, muốn xin quyền write orders và read customers thì sử dụng `scope=write_orders,read_customers`.
`{redirect_url}` - **(Bắt buộc)** đường dẫn URL mà bạn muốn Redirect User đến sau khi họ xác thực Client. Địa chỉ URL này **phải** giống với địa chỉ _Redirect URL của App_
## Bước 3: Khẳng định việc cài đặt
Khi User click nút ***Install*** trong màn hình xin quyền, họ sẽ được chuyển hướng tới địa chỉ đã được xác định ở trên. Một tham số được truyền trên đường dẫn là *Authorization Code* (Các tham số khác sẽ được đề cập đến ở phần sau của bài viết).
```
https://{your_domain}/some/redirect/uri?code={authorization_code}&signature=da9d83c171400a41f8db91a950508985×tamp=1409617544
Authorization code có thể được dùng để lấy một access token để sử dụng bằng cách thực hiện request sau tới Shop.
```
```
POST
https://{store}.mysapo.vn/admin/oauth/access_token
```
Trong đó `{store}` là tên của Shop và request có gửi kèm theo các tham số sau:

`client_id`
*API Key* của App. (Xem lại phần credentials trong bài viết).

`client_secret`
*Secret Key* của App. (Xem lại phần credentials trong bài viết).

`code`
Authorization code được cấp ở trên.
Server sẽ trả về Truy xuất dữ liệu của các tài nguyên cho Client.
`
{
    "access_token": "f85632530bf277ec9ac6f649fc327f17"
}
`
Đây chính là API access token *vĩnh viễn* được sử dụng để truy cập vào các dữ liệu của Shop khi Client được cài đặt. Client nên lưu trữ token này lại để gửi các request hợp lệ đến để lấy dữ liệu từ Shop.

## Bước 4: Tạo request đã được xác thực
Sau khi Client đã lấy được API access token, Client có thể tạo các Request đã được xác thực lên REST API. Những Request này có gắn kèm tham số trên header là `X-Sapo-Access-Token: {access_token}` trong đó `{access_token}` chính là token mà Client đã lấy được ở trên.

<a name="Scopes"></a>
## Scopes

Một phần trong quá trình xác thực yêu cầu xác định xem Client muốn truy xuất vào dữ liệu gì của Shop (Xem phần “Xin cấp quyền” trong hướng dẫn này). Một Client có thể xin cấp quyền trong các Scopes sau:

`read_products`, `write_products`
Truy xuất dữ liệu của các tài nguyên [Product].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Sản phẩm của Shop.

`read_purchaseorder`, `write_purchaseorder`
Truy xuất dữ liệu của các tài nguyên [PurchaseOrder].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu Nhập hàng của Shop.

`read_purchase_orders/returns`, `write_purchase_orders/returns`
Truy xuất dữ liệu của các tài nguyên [PurchaseOrdersReturns]

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu Trả hàng nhà cung cấp của Shop.

`read_stocktranfer`, `write_stocktranfer`
Truy xuất dữ liệu của các tài nguyên [StockTranfer].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu Chuyển hàng của Shop.

`read_stockadjustment`, `write_stockadjustment`
Truy xuất dữ liệu của các tài nguyên [StockAdjustment].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu Kiểm hàng của Shop.

`read_priceadjustment`, `write_priceadjustment`
Truy xuất dữ liệu của các tài nguyên [PriceAdjustment].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu Điều chỉnh giá vốn của Shop.

`read_sales`,`write_sales`
Truy xuất dữ liệu của các tài nguyên [Sales].

Bạn có thể thông qua Cilent để xem dữ liệu phần Bán hàng của Shop.

`read_reports/sales/by_end_day`
Truy xuất dữ liệu của các tài nguyên [ReportSaleByEndDay].

Bạn có thể thông qua Cilent để xem dữ liệu phần Báo cáo cuối ngày của Shop.

`read_orderreturn`,`write_orderreturn`
Truy xuất dữ liệu của các tài nguyên [OrderReturn].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Trả hàng cho khách hàng của Shop.

`read_shippers`,`write_shippers`
Truy xuất dữ liệu của các tài nguyên [Shippers].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Quản lý vận chuyển của Shop.

`read_deliverycollations`,`write_deliverycollations`
Truy xuất dữ liệu của các tài nguyên [DeliveryCollations].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Phiếu đối soát của Shop.

`read_customers`,`write_customers`
Truy xuất dữ liệu của các tài nguyên [Customers].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Khách hàng của Shop.

`read_suppliers`,`write_suppliers`
Truy xuất dữ liệu của các tài nguyên [Suppliers].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Nhà cung cấp của Shop.

`read_settings`,`write_settings`
Truy xuất dữ liệu của các tài nguyên [Settings].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Thiết lập của Shop.

`read_advanced`,`write_advanced`
Truy xuất dữ liệu của các tài nguyên [Advanced].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Nâng cao của Shop.

`read_reports/sales`
Truy xuất dữ liệu của các tài nguyên [ReportsSales].

Bạn có thể thông qua Cilent để xem phần Báo cáo bán hàng của Shop.

`read_reports/inventories`
Truy xuất dữ liệu của các tài nguyên [ReportsInventories]

Bạn có thể thông qua Cilent để xem phần Báo cáo kho của Shop.

`read_reports/finance`
Truy xuất dữ liệu của các tài nguyên [ReportsFiance].

Bạn có thể thông qua Cilent để xem dữ liệu phần Báo cáo tài chính của Shop.

`read_reports/vouchers/dash_board`
Truy xuất dữ liệu của các tài nguyên [ReportsVouchersDashBoard]

Bạn có thể thông qua Cilent để xem dữ liệu phần Tổng quan của Shop.

`read_accounts`,`write_accounts`
Truy xuất dữ liệu của các tài nguyên [Accounts].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Nhân viên của Shop.

`read_Branch`,`write_Branch`
Truy xuất dữ liệu của các tài nguyên [Branch].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Thương hiệu của Shop.

`read_receipt_vouchers`, `write_receipt_vouchers`
Truy xuất dữ liệu của các tài nguyên [ReceiptVouchers],[Vouchers]

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Phiếu thu của Shop.

`read_payment_vouchers`, `write_payment_vouchers`
Truy xuất dữ liệu của các tài nguyên [PaymentVouchers],[Vouchers].

Bạn có thể thông qua Cilent để xem và chỉnh sửa dữ liệu phần Phiếu chi của Shop.

## Verification
Mỗi Request hoặc chuyển hướng từ Sapo về Client đều chứa các tham số *signature* và **hmac**, được dùng để xác minh dữ liệu đúng là từ Sapo. **Thuộc tính signature sẽ bị loại bỏ do những lỗ hổng bảo mật trong việc tạo signature.**

Để xác minh một Request là hợp lệ, đầu tiên thực hiện phân giải tham số trong query string ra thành các cặp (key, value) tương ứng.

Ví dụ về một query string:
```
"store=some-store.mysapo.vn&code=a94a110d86d2452eb3e2af4cfb8a3828&timestamp=1337178173&signature=6e39a2ea9e497af6cb806720da1f1bf3&hmac=2cb1a277650a659f1b11e92a4a64275b128e037f2c3390e3c8fd2d8721dac9e2"
```
được phân tách ra như sau:
```
{
    "store": "some-store.mysapo.vn",
    "code": "a94a110d86d2452eb3e2af4cfb8a3828",
    "timestamp": "1337178173",
    "signature": "6e39a2ea9e497af6cb806720da1f1bf3",
    "hmac": "2cb1a277650a659f1b11e92a4a64275b128e037f2c3390e3c8fd2d8721dac9e2"
}
```
## HMAC Signature Validation
Các giá trị `signature` và `hmac` được lấy ra, để lại các tham số khác.
```
{
    "store": "some-store.mysapo.vn",
    "code": "a94a110d86d2452eb3e2af4cfb8a3828",
    "timestamp": "1337178173"
}
```
Các ký tự `&` và `%` được thay thế bởi `%26` và `%25` tương ứng trong giá trị của các cặp (key, value) đó. Thêm vào đó, ký tự `=` được thay thế bởi `%3D` trong giá trị key.

Mỗi một key được ghép với value tương ứng của nó qua ký tự = để tạo ra một danh sách các xâu. Danh sách các cặp key-value được sắp xếp theo thứ tự như trong từ điển và được ghép với nhau bởi ký tự & để tạo ra một xâu duy nhất:
```
"code=a94a110d86d2452eb3e2af4cfb8a3828&store=some-store.mysapo.vn&timestamp=1337178173"
```
Cuối cùng, xâu này được thực hiện mã hóa HMAC-SHA256 sử dụng khóa là **Secret Key**. Dữ liệu được xác thực là hợp lệ nếu như chuỗi ký tự mã hóa được sinh ra bằng với giá trị của tham số `hmac`.
```
digest = OpenSSL::Digest.new('sha256')
secret = "hush"
message = "store=some-shop.mysapo.vn&timestamp=1337178173"
digest = OpenSSL::HMAC.hexdigest(digest, secret, message)
digest == "2cb1a277650a659f1b11e92a4a64275b128e037f2c3390e3c8fd2d8721dac9e2"
```

