---
title: "Mô hình Client – Server"
date: 2025-12-26
categories: ["Lập trình mạng"]
tags: ["Client", "Server", "Network"]
draft: false
---

## Mô hình Client – Server là gì?

Client-Server là mô hình kiến trúc mạng trong đó:
- **Client (Máy khách)**: Gửi yêu cầu (request)
- **Server (Máy chủ)**: Xử lý yêu cầu và trả kết quả (response)

Đây là mô hình phổ biến nhất trong phát triển ứng dụng mạng hiện nay.

## Cách hoạt động

```
1. Client gửi yêu cầu    →    Server nhận yêu cầu
2. Server xử lý          →    Truy vấn database
3. Server gửi phản hồi   →    Client nhận kết quả
4. Client hiển thị      →    Người dùng thấy kết quả
```

## Ví dụ thực tế

### 1. Website
- **Client**: Trình duyệt (Chrome, Firefox)
- **Server**: Web server (Apache, Nginx)
- **Luồng**:
  ```
  Browser → Gửi HTTP Request → Web Server
  Web Server → Xử lý PHP/Java → Database
  Web Server → Trả HTML/CSS/JS → Browser hiển thị
  ```

### 2. Email
- **Client**: Outlook, Gmail app
- **Server**: Mail server (Gmail, Yahoo)
- **Luồng**: Viết email → Gửi đến mail server → Server chuyển đến người nhận

### 3. Game Online
- **Client**: Game client trên máy/điện thoại
- **Server**: Game server
- **Luồng**: Hành động của bạn → Gửi server → Server đồng bộ → Gửi cho người chơi khác

### 4. Banking
- **Client**: App ngân hàng, ATM
- **Server**: Server ngân hàng
- **Luồng**: Chuyển tiền → Gửi server → Kiểm tra số dư → Thực hiện giao dịch

## Ưu điểm của mô hình Client-Server

### 1. Quản lý tập trung
- Dữ liệu lưu trên server
- Dễ backup, bảo mật
- Cập nhật dễ dàng

### 2. Khả năng mở rộng
- Thêm client mới dễ dàng
- Nâng cấp server khi cần
- Phân tải với nhiều server

### 3. Bảo mật
- Server kiểm soát truy cập
- Mã hóa dữ liệu
- Authentication & Authorization

### 4. Chia sẻ tài nguyên
- Nhiều client dùng chung database
- Chia sẻ file, máy in
- Tiết kiệm chi phí

## Nhược điểm

- **Single point of failure**: Server hỏng → toàn hệ thống ngừng
- **Chi phí cao**: Cần server mạnh
- **Phụ thuộc mạng**: Không có mạng → không dùng được
- **Tắc nghẽn**: Quá nhiều client → server quá tải

## Ví dụ code Java

### Server đơn giản
```java
import java.net.*;
import java.io.*;

public class Server {
    public static void main(String[] args) {
        try {
            // Tạo server socket ở port 8080
            ServerSocket serverSocket = new ServerSocket(8080);
            System.out.println("Server đang chạy ở port 8080...");
            
            while (true) {
                // Chờ client kết nối
                Socket clientSocket = serverSocket.accept();
                System.out.println("Client kết nối: " + clientSocket.getInetAddress());
                
                // Đọc dữ liệu từ client
                BufferedReader in = new BufferedReader(
                    new InputStreamReader(clientSocket.getInputStream()));
                String message = in.readLine();
                System.out.println("Nhận: " + message);
                
                // Gửi phản hồi cho client
                PrintWriter out = new PrintWriter(clientSocket.getOutputStream(), true);
                out.println("Server đã nhận: " + message);
                
                clientSocket.close();
            }
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

public class Client {
    public static void main(String[] args) {
        try {
            // Kết nối đến server
            Socket socket = new Socket("localhost", 8080);
            System.out.println("Đã kết nối đến server!");
            
            // Gửi dữ liệu đến server
            PrintWriter out = new PrintWriter(socket.getOutputStream(), true);
            out.println("Xin chào Server!");
            
            // Nhận phản hồi từ server
            BufferedReader in = new BufferedReader(
                new InputStreamReader(socket.getInputStream()));
            String response = in.readLine();
            System.out.println("Phản hồi: " + response);
            
            socket.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## Các biến thể của mô hình

### 1. Peer-to-Peer (P2P)
- Mỗi máy vừa là client vừa là server
- Ví dụ: BitTorrent, Blockchain

### 2. Three-tier Architecture
```
Client ↔ Application Server ↔ Database Server
```
- Tách biệt presentation, logic, data

### 3. Microservices
- Nhiều server nhỏ, mỗi server làm 1 việc
- Dễ mở rộng, bảo trì

## Kết luận

Mô hình Client-Server là nền tảng của hầu hết ứng dụng mạng hiện đại. Hiểu rõ mô hình này sẽ giúp bạn:
- Thiết kế hệ thống tốt hơn
- Debug lỗi dễ dàng
- Tối ưu hiệu suất

Hãy thực hành code ví dụ trên để hiểu sâu hơn về cách Client và Server giao tiếp!
