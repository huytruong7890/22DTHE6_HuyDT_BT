---
title: "Biến và kiểu dữ liệu trong JavaScript"
date: 2025-12-26
categories: ["JavaScript"]
tags: ["JavaScript", "Biến", "Cơ bản"]
draft: false
---

## Khai báo biến trong JavaScript

JavaScript cung cấp 3 cách khai báo biến, mỗi cách có đặc điểm riêng:

### 1. var (cách cũ)
```javascript
var name = "Huy";
var age = 20;
```
- Phạm vi: Function scope
- Có thể khai báo lại
- Không nên dùng trong code hiện đại

### 2. let (khuyên dùng)
```javascript
let name = "Huy";
let age = 20;
age = 21; // Có thể thay đổi giá trị
```
- Phạm vi: Block scope
- Không thể khai báo lại
- Giá trị có thể thay đổi

### 3. const (hằng số)
```javascript
const PI = 3.14159;
const SCHOOL = "HUTECH";
// PI = 3.14; // Lỗi! Không thể thay đổi
```
- Phạm vi: Block scope
- Giá trị không thể thay đổi
- Dùng cho các giá trị cố định

## Kiểu dữ liệu trong JavaScript

### 1. Number (Số)
```javascript
let age = 20;
let price = 99.99;
let negative = -10;
```

### 2. String (Chuỗi)
```javascript
let name = "Trương Đức Huy";
let school = 'HUTECH';
let message = `Xin chào ${name}`; // Template string
```

### 3. Boolean (Đúng/Sai)
```javascript
let isStudent = true;
let isPassed = false;
```

### 4. Array (Mảng)
```javascript
let fruits = ["Táo", "Chuối", "Cam"];
let numbers = [1, 2, 3, 4, 5];
console.log(fruits[0]); // "Táo"
```

### 5. Object (Đối tượng)
```javascript
let student = {
    name: "Trương Đức Huy",
    age: 20,
    major: "CNTT",
    showInfo: function() {
        console.log(this.name);
    }
};

console.log(student.name); // "Trương Đức Huy"
```

### 6. Null và Undefined
```javascript
let empty = null;        // Giá trị rỗng có chủ đích
let notDefined;          // undefined - chưa gán giá trị
```

## Ví dụ thực tế

```javascript
// Thông tin sinh viên
const studentName = "Trương Đức Huy";
let currentAge = 20;
let subjects = ["Java", "JavaScript", "Lập trình mạng"];

let studentInfo = {
    name: studentName,
    age: currentAge,
    school: "HUTECH",
    courses: subjects,
    isActive: true
};

console.log(studentInfo);
```

## Kiểm tra kiểu dữ liệu

```javascript
console.log(typeof "Hello");      // "string"
console.log(typeof 42);           // "number"
console.log(typeof true);         // "boolean"
console.log(typeof [1,2,3]);      // "object"
console.log(typeof {name: "A"}); // "object"
```

## Kết luận

Hiểu rõ về biến và kiểu dữ liệu là nền tảng quan trọng để học JavaScript. Hãy thực hành nhiều để nắm vững các khái niệm này!
