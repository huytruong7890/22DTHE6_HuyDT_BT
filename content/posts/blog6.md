---
title: "Xử lý sự kiện trong JavaScript"
date: 2025-12-26
categories: ["JavaScript"]
tags: ["JavaScript", "Event", "Web"]
draft: false
---

## Sự kiện (Event) là gì?

Sự kiện là những hành động xảy ra trên trang web như:
- Click chuột
- Di chuyển chuột
- Nhập dữ liệu vào form
- Submit form
- Scroll trang
- Load trang

JavaScript cho phép chúng ta "lắng nghe" và xử lý các sự kiện này.

## Các loại sự kiện phổ biến

### 1. Sự kiện chuột (Mouse Events)
- `click`: Click chuột
- `dblclick`: Click đúp
- `mouseover`: Chuột di chuyển vào
- `mouseout`: Chuột rời khỏi
- `mousemove`: Chuột di chuyển

### 2. Sự kiện bàn phím (Keyboard Events)
- `keydown`: Nhấn phím xuống
- `keyup`: Nhả phím
- `keypress`: Nhấn và nhả phím

### 3. Sự kiện form (Form Events)
- `submit`: Submit form
- `change`: Thay đổi giá trị
- `focus`: Focus vào input
- `blur`: Rời khỏi input

## Cách xử lý sự kiện

### Cách 1: Inline HTML
```html
<button onclick="alert('Xin chào!')">Click me</button>
```

### Cách 2: DOM property
```javascript
let btn = document.getElementById('myBtn');
btn.onclick = function() {
    alert('Button clicked!');
};
```

### Cách 3: addEventListener (Khuyên dùng)
```javascript
let btn = document.getElementById('myBtn');

btn.addEventListener('click', function() {
    console.log('Button được click!');
});

// Có thể thêm nhiều listener cho cùng 1 sự kiện
btn.addEventListener('click', function() {
    console.log('Handler thứ 2');
});
```

## Ví dụ thực tế

### Thay đổi màu nền khi click
```html
<!DOCTYPE html>
<html>
<body>
    <button id="colorBtn">Đổi màu</button>
    
    <script>
        let btn = document.getElementById('colorBtn');
        let colors = ['#FF6B6B', '#4ECDC4', '#45B7D1', '#FFA07A'];
        let index = 0;
        
        btn.addEventListener('click', function() {
            document.body.style.backgroundColor = colors[index];
            index = (index + 1) % colors.length;
        });
    </script>
</body>
</html>
```

### Đếm số lần click
```html
<button id="countBtn">Click: 0</button>

<script>
let count = 0;
let btn = document.getElementById('countBtn');

btn.addEventListener('click', function() {
    count++;
    btn.textContent = 'Click: ' + count;
});
</script>
```

### Validation form
```html
<form id="myForm">
    <input type="text" id="username" placeholder="Tên đăng nhập">
    <button type="submit">Đăng nhập</button>
</form>

<script>
let form = document.getElementById('myForm');
let username = document.getElementById('username');

form.addEventListener('submit', function(event) {
    event.preventDefault(); // Ngăn form submit
    
    if (username.value === '') {
        alert('Vui lòng nhập tên đăng nhập!');
    } else {
        alert('Chào mừng: ' + username.value);
    }
});
</script>
```

## Event Object

Mỗi sự kiện đều có một đối tượng event chứa thông tin:

```javascript
let btn = document.getElementById('myBtn');

btn.addEventListener('click', function(event) {
    console.log('Type:', event.type);           // "click"
    console.log('Target:', event.target);       // Element được click
    console.log('Position:', event.clientX, event.clientY); // Tọa độ chuột
});
```

## Kết luận

Xử lý sự kiện là kỹ năng quan trọng giúp website trở nên tương tác. Hãy thực hành nhiều để thành thạo!
