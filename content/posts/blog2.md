---
title: "Lập trình hướng đối tượng trong Java"
date: 2025-12-26
categories: ["Java"]
tags: ["Java", "OOP", "Học lập trình"]
draft: false
---

## Lập trình hướng đối tượng là gì?

Lập trình hướng đối tượng (OOP - Object-Oriented Programming) là phương pháp lập trình dựa trên khái niệm "đối tượng", giúp tổ chức code rõ ràng, dễ bảo trì và tái sử dụng.

## Các khái niệm cơ bản

### 1. Class (Lớp)
Class là khuôn mẫu, bản thiết kế để tạo ra các đối tượng. Nó định nghĩa thuộc tính và phương thức mà đối tượng sẽ có.

### 2. Object (Đối tượng)
Object là thể hiện cụ thể của class, được tạo ra từ class.

### 3. Encapsulation (Đóng gói)
Che giấu thông tin bên trong class, chỉ cho phép truy cập thông qua các phương thức công khai.

### 4. Inheritance (Kế thừa)
Class con có thể kế thừa thuộc tính và phương thức từ class cha, giúp tái sử dụng code.

### 5. Polymorphism (Đa hình)
Cho phép sử dụng cùng một interface cho các kiểu dữ liệu khác nhau.

## Ví dụ thực tế

```java
// Định nghĩa class SinhVien
class SinhVien {
    // Thuộc tính
    private String ten;
    private int tuoi;
    private String mssv;
    
    // Constructor
    public SinhVien(String ten, int tuoi, String mssv) {
        this.ten = ten;
        this.tuoi = tuoi;
        this.mssv = mssv;
    }
    
    // Phương thức
    public void hienThi() {
        System.out.println("MSSV: " + mssv);
        System.out.println("Tên: " + ten);
        System.out.println("Tuổi: " + tuoi);
    }
    
    // Getter và Setter
    public String getTen() {
        return ten;
    }
    
    public void setTen(String ten) {
        this.ten = ten;
    }
}

// Sử dụng
public class Main {
    public static void main(String[] args) {
        SinhVien sv1 = new SinhVien("Trương Đức Huy", 20, "22DT001");
        sv1.hienThi();
    }
}
```

## Lợi ích của OOP

- **Tái sử dụng code**: Kế thừa giúp sử dụng lại code đã viết
- **Dễ bảo trì**: Code được tổ chức rõ ràng theo đối tượng
- **Mở rộng dễ dàng**: Thêm tính năng mới không ảnh hưởng code cũ
- **Bảo mật**: Đóng gói giúp bảo vệ dữ liệu

## Kết luận

OOP là nền tảng quan trọng trong Java. Hiểu rõ OOP sẽ giúp bạn viết code chuyên nghiệp và dễ bảo trì hơn.
