---
title: "Xử lý ngoại lệ trong Java"
date: 2025-12-26
categories: ["Java"]
tags: ["Java", "Exception"]
draft: false
---

# 🟢 BÀI 3 – XỬ LÝ NGOẠI LỆ TRONG JAVA

## Ngoại lệ là gì?
Ngoại lệ là lỗi xảy ra trong quá trình chạy chương trình.

## Cách xử lý ngoại lệ
Java sử dụng khối try – catch – finally để xử lý lỗi.

## Ví dụ
```java
try {
    int a = 10 / 0;
} catch (Exception e) {
    System.out.println("Loi chia cho 0");
}
```
