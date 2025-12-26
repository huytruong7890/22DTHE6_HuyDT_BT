---
title: "Giao thức HTTP và hoạt động của Website"
date: 2025-12-26
categories: ["Lập trình mạng"]
tags: ["HTTP", "Web", "Protocol"]
draft: false
---

## HTTP là gì?

HTTP (HyperText Transfer Protocol) là giao thức truyền dữ liệu trên web, định nghĩa cách trình duyệt và web server giao tiếp với nhau. Đây là nền tảng của World Wide Web.

## Cách Website hoạt động

```
1. Gõ địa chỉ web    →  Browser gửi HTTP Request
2. DNS phân giải     →  Tìm IP của website
3. Kết nối Server    →  Thông qua TCP/IP
4. Server xử lý      →  Tìm file HTML/PHP/Java
5. Server phản hồi   →  Gửi HTTP Response
6. Browser render    →  Hiển thị website
```

## Cấu trúc HTTP Request

### 1. Request Line
```
GET /index.html HTTP/1.1
```
- **GET**: HTTP Method (phương thức)
- **/index.html**: URL path
- **HTTP/1.1**: Phiên bản HTTP

### 2. Headers
```
Host: www.example.com
User-Agent: Mozilla/5.0
Accept: text/html
Cookie: session=abc123
```

### 3. Body (với POST)
```
username=huy&password=123456
```

## HTTP Methods (Phương thức)

### GET - Lấy dữ liệu
```
GET /users/123 HTTP/1.1
Host: api.example.com
```
- Lấy thông tin user có ID 123
- Không có body
- Có thể cache

### POST - Tạo mới
```
POST /users HTTP/1.1
Host: api.example.com
Content-Type: application/json

{
  "name": "Huy",
  "email": "huy@example.com"
}
```
- Tạo user mới
- Có body chứa dữ liệu
- Không cache

### PUT - Cập nhật toàn bộ
```
PUT /users/123 HTTP/1.1

{
  "name": "Huy Updated",
  "email": "newemail@example.com"
}
```

### DELETE - Xóa
```
DELETE /users/123 HTTP/1.1
```

### PATCH - Cập nhật một phần
```
PATCH /users/123 HTTP/1.1

{
  "email": "newemail@example.com"
}
```

## HTTP Status Codes

### 2xx - Thành công
- **200 OK**: Thành công
- **201 Created**: Tạo mới thành công
- **204 No Content**: Thành công nhưng không có dữ liệu

### 3xx - Chuyển hướng
- **301 Moved Permanently**: Chuyển hướng vĩnh viễn
- **302 Found**: Chuyển hướng tạm thời
- **304 Not Modified**: Dùng cache

### 4xx - Lỗi Client
- **400 Bad Request**: Request sai
- **401 Unauthorized**: Chưa đăng nhập
- **403 Forbidden**: Không có quyền
- **404 Not Found**: Không tìm thấy trang

### 5xx - Lỗi Server
- **500 Internal Server Error**: Lỗi server
- **502 Bad Gateway**: Lỗi gateway
- **503 Service Unavailable**: Server quá tải

## Cấu trúc HTTP Response

```
HTTP/1.1 200 OK
Content-Type: text/html; charset=UTF-8
Content-Length: 1234
Set-Cookie: session=xyz789

<!DOCTYPE html>
<html>
<head>
    <title>My Website</title>
</head>
<body>
    <h1>Hello World!</h1>
</body>
</html>
```

## HTTPS - HTTP Secure

### Khác biệt HTTP vs HTTPS

| HTTP | HTTPS |
|------|-------|
| Không mã hóa | Mã hóa SSL/TLS |
| Port 80 | Port 443 |
| Không an toàn | An toàn |
| http:// | https:// |

### Tại sao cần HTTPS?
- Bảo vệ mật khẩu, thông tin thẻ
- SEO tốt hơn (Google ưu tiên)
- Tăng độ tin cậy
- Bắt buộc với các tính năng hiện đại

## Cookies và Sessions

### Cookies
```javascript
// Server gửi
Set-Cookie: user=huy; Max-Age=3600

// Browser tự động gửi lại
Cookie: user=huy
```

### Session
1. User đăng nhập → Server tạo session
2. Server gửi session ID qua cookie
3. Browser gửi session ID mỗi request
4. Server kiểm tra session để biết user

## Ví dụ thực tế với JavaScript

### Fetch API
```javascript
// GET request
fetch('https://api.example.com/users')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error(error));

// POST request
fetch('https://api.example.com/users', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
    },
    body: JSON.stringify({
        name: 'Huy',
        email: 'huy@example.com'
    })
})
.then(response => response.json())
.then(data => console.log('Success:', data));
```

## RESTful API

Thiết kế API theo chuẩn REST:

```
GET    /users          → Lấy danh sách users
GET    /users/123      → Lấy user có ID 123
POST   /users          → Tạo user mới
PUT    /users/123      → Update toàn bộ user 123
PATCH  /users/123      → Update một phần user 123
DELETE /users/123      → Xóa user 123
```

## Tools để test HTTP

1. **Postman**: Test API
2. **cURL**: Command line
3. **Browser DevTools**: F12 → Network tab
4. **Insomnia**: Tương tự Postman

## Kết luận

HTTP là giao thức cốt lõi của web. Hiểu rõ HTTP sẽ giúp bạn:
- Phát triển web/mobile app tốt hơn
- Debug lỗi API dễ dàng
- Thiết kế RESTful API chuẩn
- Tối ưu performance

Hãy mở Browser DevTools (F12) và xem tab Network để thấy HTTP requests/responses thực tế!
