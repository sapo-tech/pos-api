# Tags
Tài nguyên Tags trên Mysapo đại diện cho các tags được gắn tại mỗi trang. Điều này giúp cho việc truy xuất các trang trở nên dễ dàng mà không cần tác động gì vào các khung giao diện có sẵn.

Khi một app được gỡ ra khỏi Shop, tất cả Tag được tạo cho app sẽ được tự động gỡ bỏ.

## Lấy các tags 
**Request**
```
GET /admin/tags HTTP/1.1
Token: X-Sapo-Access-Token 28a48cee892343b2b29780a586c5ded2
Content-Type: application/json
param request: ?document_type=product

```
**Kết quả trả về**
```
{
    "tags": []
}
```
