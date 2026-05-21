### CƠ BẢN VỀ CSS — Bộ chọn, Mô hình hộp, Kế thừa & Hiệu ứng xếp tầng

# PHẦN A — KIỂM TRA ĐỌC HIỂU

# A1 Cách nhúng CSS

3 cách nhúng CSS:
1. CSS nội tuyến — thuộc tính trong style:
vd:
<p style="color: red; font-size: 20px;">
    Hello World
</p>

- Ưu điểm:
+ Nhanh, đơn giản
+ Áp dụng ngay cho 1 phần tử

- Nhược điểm:
+ Khó quản lý khi code lớn
+ Lặp code nhiều
+ Không tái sử dụng được

- Nền dùng khi:
+ Test nhanh
+ Chỉnh riêng 1 phần tử đặc biệt

2. CSS nội bộ — trong thẻ <style>:
vd:
<head>
    <style>
        p {
            color: blue;
            font-size: 18px;
        }
    </style>
</head>

<body>
    <p>Hello HTML</p>
</body>

- Ưu điểm:
+ Quản lý dễ hơn inline
+ Dùng cho nhiều phần tử trong cùng trang

- Nhược điểm:
+ Chỉ áp dụng cho 1 file HTML
+ Không tái sử dụng cho nhiều trang

- Nên dùng khi:
+ Website nhỏ
+ Trang đơn giản chỉ có 1 file

3. CSS bên ngoài — dành riêng cho tệp:
vd:
# html
<head>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <p>Hello CSS</p>
</body>

# css
p {
    color: green;
    font-size: 22px;
}

- Ưu điểm:
+ Dễ quản lý
+ Tái sử dụng cho nhiều trang
+ Code gọn gàng, chuyên nghiệp'

- Nhược điểm:
+ Phải tạo thêm file CSS
+ Nếu file CSS lỗi thì giao diện có thể mất style

- Nên dùng khi:
+ Website lớn
+ Dự án thực tế

- Câu hỏi thêm: Nếu cùng 1 phần tử có cả 3 cách CSS đồng thời áp dụng thì "thắng" bằng cách nào? Giải thích tại sao?

code sẽ đi từ trên xuống dưới, cái nào ở dưới cùng sẽ là thắng.

## A2 Bộ chọn CSS — Kết quả mong đợi

1. h1                           
→ Chọn: ShopTLU
2. .price                       
→ Chọn: 25.990.000đ 45.990.000đ
3. #app header                  
→ Chọn: <header class="top-bar dark">, nội dung bên trong thẻ.
4. nav a:first-child             
→ Chọn: Home
5. .product.featured h2         
→ Chọn: MacBook Pro
6. article > p                  
→ Chọn: 25.990.000đ
Mô tả sản phẩm...
45.990.000đ
Mô tả sản phẩm...
7. a[href="/"]                  
→ Chọn: Home
8. .top-bar.dark h1              
→ Chọn: ShopTLU

kết quả: ![alt text]({01CE6306-5F12-4AF7-BDE1-A6F897E5AAA6}.png)

# A3 Box Model — Tính toán kích thước

/* Trường hợp 1: content-box (mặc định) */
.box-1 {
    width: 400px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
→ Chiều rộng hiển thị = 450px
→ Không gian chiếm trên trang = 470px 

/* Trường hợp 2: border-box */
.box-2 {
    box-sizing: border-box;
    width: 400px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
→ Chiều rộng hiển thị = 400px
→ Kích thước content thực tế = 350px
→ Không gian chiếm trên trang = 420px

/* Trường hợp 3: Margin collapse */
.box-a { margin-bottom: 25px; }
.box-b { margin-top: 40px; }
→ Khoảng cách giữa box-a và box-b = 40px
→ Giải thích tại sao KHÔNG PHẢI 65px
vì: xảy ra hiện tượng Margin Collapse, hai margin dọc chạm nhau sẽ: không cộng lại, browser chỉ lấy margin lớn hơn.

#  A4 Tính đặc hiệu (Độ ưu tiên)

1. Element sẽ có màu: red

vì c (1,0,0) là ID mạnh nhất → Rule C thắng 

2. nếu thêm <p class="price" id="main-price" style="color: orange;">
Màu cuối cùng = orange

3. Nếu thêm !important
Màu cuối cùng = black vì !important có độ ưu tiên cao nhất 

# Phần B:
## B1:

# Các loại bộ chọn đã sử dụng

1. Element selector
- body
- table
- footer

2. Class selector
- .container
- .active

3. ID selector
- #main-header

4. Descendant selector
- nav a

5. Pseudo-class selector
- nav a:hover
- tr:nth-child(even)
- tr:hover

## B2:

## B3:
1. Liệt kê 10 quy tắc + điểm đặc hiệu
| Rule | Selector | Specificity |
| 1 | p | (0,0,1) |
| 2 | .text | (0,1,0) |
| 3 | .highlight | (0,1,0) |
| 4 | p.text | (0,1,1) |
| 5 | p.highlight | (0,1,1) |
| 6 | .text.highlight | (0,2,0) |
| 7 | #demo | (1,0,0) |
| 8 | p#demo | (1,0,1) |
| 9 | #demo.text | (1,1,0) |
| 10 | p#demo.text.highlight | (1,2,1) |

2. Phần tử cuối cùng hiển thị màu gì? Tại sao?

- Màu cuối cùng: gold
- Rule số 10 có specificity cao nhất: (1,2,1)

Bao gồm:
- 1 ID
- 2 class
- 1 element

Nó mạnh hơn tất cả các rule còn lại nên browser áp dụng màu gold.

3. ảnh chụp màn hình kết quả
![alt text]({C4ABB67A-10C8-4879-94FB-D7A16B8BA2F8}.png)

4. Thay đổi quy tắc thứ tự trong tệp CSS. Kết quả có thay đổi không? Giải thích thích.

/* trường hợp 1 */
Nếu specificity khác nhau:
- thứ tự KHÔNG quan trọng
- rule mạnh hơn vẫn thắng

/* trường hợp 2 */
Nếu specificity bằng nhau:
- rule viết SAU sẽ thắng'


# PHẦN C — DEBUG & SUY LUẬN
##  C1: Gỡ lỗi bố cục CSS
1. Tính chiều rộng thực tế của sidebar và nội dung (content-box!)
.sidebar {
    width: 300px;
    padding: 20px;
    border: 1px solid #ccc;
}

Sidebar thực tế = 342px

.content {
    width: 660px;
    padding: 30px;
    border: 1px solid #ccc;
}

Content thực tế = 722px

2. Giải thích tại sao bố cục bị hỏng
Do đang dùng: box-sizing: content-box;

Nên:
- width chỉ tính content
padding + border bị cộng thêm ra ngoài

- Tổng chiều rộng vượt quá container 960px nên .content bị rớt xuống dòng mới.

# C3 Câu đố xếp tầng

1. “Sản phẩm A” (h2) có font-size= 20px và color= green

- giải thích: 
- các rule liên quan:
.card {
    color: blue;
}

#featured .title {
    color: red;
}

.highlight {
    color: green !important;
}

vì important có ưu tiên cao nhất → color = green

2. "Mô tả sản phẩm" (p trong thẻ đặc trưng) có color= blue
- giải thích: 
- các rule: 

.card {
    color: blue;
}

.card p {
    color: inherit;
}


3. “Sản phẩm B” (h2) có font-size= 20px và color= blue
- giải thích: 
- các rule:

.card {
    color: blue;
}


4. "Mô tả sản phẩm B" (p.highlight) có color= green

.highlight {
    color: green !important;
} 

vì important có ưu tiên cao nhất → color = green.




