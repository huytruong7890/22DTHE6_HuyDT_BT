---
title: "Tổng quan về lập trình mạng"
date: 2025-12-26
categories: ["Lập trình mạng"]
tags: ["Mạng", "Network", "Socket"]
draft: false
---

## Lập trình mạng là gì?

Lập trình mạng là việc xây dựng các ứng dụng có khả năng giao tiếp với nhau qua mạng máy tính (LAN, WAN, Internet). Đây là nền tảng của hầu hết các ứng dụng hiện đại.

## Tại sao cần học lập trình mạng?

- **Ứng dụng thực tế**: Hầu hết app ngày nay đều cần kết nối mạng
- **Hiểu cách hoạt động**: Biết cách website, app chat, game online hoạt động
- **Cơ hội việc làm**: Kỹ năng được nhiều công ty tìm kiếm
- **Nền tảng cho IoT**: Thiết bị thông minh đều dùng lập trình mạng

## Các khái niệm cơ bản

### 1. IP Address (Địa chỉ IP)
Địa chỉ định danh duy nhất của máy tính trên mạng.
```
Ví dụ: 192.168.1.100, 8.8.8.8
```

### 2. Port (Cổng)
Số định danh ứng dụng trên máy tính.
```
Port 80: HTTP (Website)
Port 443: HTTPS (Website bảo mật)
Port 3306: MySQL Database
```

### 3. Protocol (Giao thức)
Quy tắc giao tiếp giữa các máy:
- **TCP**: Đảm bảo dữ liệu đến đúng, đầy đủ
- **UDP**: Nhanh nhưng không đảm bảo
- **HTTP/HTTPS**: Giao thức web

## Ứng dụng của lập trình mạng

### 1. Website
- Browser (client) gửi request đến server
- Server xử lý và trả về HTML, CSS, JS

### 2. Ứng dụng Chat
- WhatsApp, Messenger, Zalo
- Client gửi tin nhắn qua server
- Server chuyển đến người nhận

### 3. Game Online
- Nhiều người chơi kết nối đến game server
- Server đồng bộ trạng thái game

### 4. Hệ thống Banking
- ATM, Internet Banking kết nối đến server ngân hàng
- Xử lý giao dịch an toàn

### 5. IoT (Internet of Things)
- Smart home, cảm biến
- Thiết bị gửi dữ liệu lên cloud

## Ví dụ đơn giản với Java

### Server đơn giản
```java
import java.net.*;
import java.io.*;

public class SimpleServer {
    public static void main(String[] args) {
        try {
            ServerSocket server = new ServerSocket(8080);
            System.out.println("Server đang chờ kết nối...");
            
            Socket client = server.accept();
            System.out.println("Client đã kết nối!");
            
            server.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Client đơn giản
```java
import java.net.*;
import java.io.*;

public class SimpleClient {
    public static void main(String[] args) {
        try {
            Socket socket = new Socket("localhost", 8080);
            System.out.println("Đã kết nối đến server!");
            
            socket.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## Các công nghệ cần học

1. **Socket Programming**: Nền tảng cơ bản
2. **HTTP/REST API**: Giao tiếp web
3. **WebSocket**: Chat realtime
4. **Database**: MySQL, MongoDB
5. **Framework**: Spring Boot (Java), Express (Node.js)

## Kết luận

Lập trình mạng là kỹ năng quan trọng trong CNTT hiện đại. Từ website đến app mobile, game online đều cần kiến thức lập trình mạng. Hãy bắt đầu học và thực hành ngay hôm nay!
