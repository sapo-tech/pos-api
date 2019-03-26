# Môi trường
* URL môi trường thật, production: https://www.sapo.vn/
# Xác thực tài khoản
Sau khi đối tác đăng ký và kích hoạt tài khoản trên hệ thống của Sapo, tài khoản đối tác sẽ được nhận được một chuỗi API token thông qua email.
> Tất cả các request đến API service của Sapo sẽ được xác thực theo giá trị `Token` trong header của request.
# Request Format
Sapo hỗ trợ định dạng dữ liệu mặc định `Content-Type` `application/json`. 
# Response Format 
Kết quả trả về sẽ có 3 định dạng:
* Xác thực không thành công, hay token không hợp lệ
* Request thành công và không có lỗi xảy ra, kết quả trả về ở dạng JSON
* Request thành công và có lỗi xảy ra, kết quả trả về ở dạng JSON
