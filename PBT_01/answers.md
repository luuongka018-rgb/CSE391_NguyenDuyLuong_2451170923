# A1

# Khi truy cập https://shopee.vn xảy ra những gì?

Dựa theo sơ đồ Client - Server:

1. Browser (Client) gửi HTTP Request tới server Shopee.
2. Server nhận request và tìm file cần trả về (ví dụ: index.html).
3. Server gửi HTTP Response lại cho trình duyệt.
4. Trình duyệt nhận nội dung HTML.
5. Browser phân tích HTML (Parse HTML).
6. Browser tiếp tục tải các file CSS và JavaScript.
7. Trình duyệt render (kết xuất) giao diện hoàn chỉnh để hiển thị cho người dùng.

---

# Tab Network trong Chrome DevTools hiển thị thông tin gì?

Tab Network dùng để theo dõi:

- Các HTTP Request/Response
- Status Code (200, 404, 500,…)
- File HTML, CSS, JS, ảnh
- Thời gian tải tài nguyên
- Tổng thời gian tải trang
- Dung lượng dữ liệu tải về

---

# Những phần cần đánh dấu trong ảnh chụp Network
![alt text]({F6399919-A399-47F0-BC3D-0ADF49459C3B}.png)

# A2

## Tại sao trang web bị Google đánh giá SEO thấp?

Dựa theo code thấy:
    dùng quá nhiều thẻ <div> quá nhiều thay vì dùng thẻ ngữ nghĩa nên Google khó hiểu cấu trúc nội dung của trang

# Các lỗi semantic

## 1. Không dùng thẻ `<header>`

Sai:
...html
<div class="header">
...

Sửa:
...html
<header>
...

## 2. Không dùng thẻ `<nav>`

Sai:
...html
<div class="menu">
...

Sửa:
...html
<nav>
...

## 3. Không dùng thẻ `<main>`

Sai:
...html
<div class="main">
...

Sửa:
...html
<main>
...

## 4. Không dùng thẻ `<article>` cho sản phẩm

Sai:
...html
<div class="product">
...

Sửa:
...html
<article class="product">
...

# A3
-----------------------
        Hộp 1
-----------------------
    Text A | Text B
-----------------------
        Hộp 2
-----------------------
    Text C | Text D
-----------------------
        Hộp 3          
-----------------------

<div> hiển thị như một khối riêng xuống dòng.
<span> và <strong> hiển thị cùng hàng nên Text A Text B .. nằm chung dòng.

# A4
## Giải thích sự khác nhau giữa <thead>, <tbody>, <tfoot>.

- <thead> Dùng để viết tiêu đề các cột.
- <tbody> Dữ liệu chính.
- <tfoot> Tổng kết.

# Tại sao KHÔNG NÊN dùng table để tạo layout trang web?

1. <table> chỉ cho tabular data — dữ liệu có hàng và cột có ý nghĩa. KHÔNG layout trang
2. <table> sinh ra để hiển thị dữ liệu bảng.
3. <table> không đúng ngữ nghĩa, Google khó đánh giá và phân tích được.
4. <table> code khó bảo trì

# B3 Sửa lỗi

Lỗi 1: Dòng 1 — <!DOCTYPE> thiếu html — Sửa <!DOCTYPE html>

Lỗi 2: Dòng 4 — Thẻ <title> chưa đóng — Thêm </title>

Lỗi 3: Dòng 5 — utf8 sai chuẩn — Sửa  UTF-8

Lỗi 4: Dòng 8 — Thẻ <h1> đóng sai — Sửa <h1> cuối  </h1>

Lỗi 5: Dòng 12 — Thẻ <a> đầu tiên chưa đóng đúng — Sửa <a> cuối  </a>

Lỗi 6: Dòng 12 — href="home" không phải liên kết nội bộ chuẩn — Sửa href="#home"

Lỗi 7: Dòng 13 — href="products" không phải liên kết nội bộ chuẩn — Sửa href="#products"

Lỗi 8: Dòng 22 — Thuộc tính src=iphone.jpg thiếu dấu ngoặc kép — Sửa  src="iphone.jpg"

Lỗi 9: Dòng 22 — Thẻ <img> thiếu thuộc tính alt — Thêm alt="iPhone 16 Pro"

Lỗi 10: Dòng 22 — Thẻ <b> đóng sai vị trí — Đưa </b> vào trước </p>

Lỗi 11: Dòng 22 — Dùng <b> chưa đúng semantic — Sửa  <strong>

Lỗi 12: Dòng 29-30 — Hàng tiêu đề bảng dùng <td> thay vì <th> — Sửa  <th>

Lỗi 13: Dòng 38 — Một trang chỉ nên có một thẻ <main> — Đổi <main> thứ hai thành <aside>

Lỗi 14: Dòng 45 — Thẻ <p> trong footer chưa đóng — Thêm </p>

Lỗi 15: Thiếu thuộc tính lang trong thẻ <html> — Thêm lang="vi" 

# B4 Phân tích trang web thật

## 1. Chụp màn hình tab Elements và chỉ ra:
1. CHỉ ra 3 thẻ ngữ nghĩa:

![alt text]({4235DA80-156D-4E30-9D4C-AC0B834B4367}.png)

- Thẻ <header>: Nằm bên trong thẻ <div class="home-page">

- Thẻ <main>: Nằm ngay sau thẻ <div> chứa banner

- Thẻ <footer>: 

2. 2 thẻ trăng không dùng đúng ngữ nghĩa:

- Sử dụng quá nhiều thẻ <div> lồng nhau như: sc-f862d3ca-1, sc-4a670bf7-0 đều dùng thẻ <div>.

- Thẻ <div> cho các nút hoặc liên kết.

## 2. Tìm 1 <table> trên trang:

## 3. Tìm 1 <form> trên trang


# Phần C:

# C2
Theo em, nói rằng chỉ cần dùng <div> cho mọi thứ là chưa hợp lý. Đúng là dùng <div> sẽ nhanh và dễ viết hơn lúc đầu, nhưng HTML ngữ nghĩa vẫn rất quan trọng.

Thứ nhất là về SEO. Khi dùng các thẻ như <header>, <nav>, <article> hay <footer>, công cụ tìm kiếm như Google sẽ hiểu cấu trúc trang web tốt hơn. Ví dụ, nếu một bài viết được đặt trong thẻ <article> thì Google có thể nhận biết đó là nội dung chính của trang. Điều này giúp website dễ được tìm thấy hơn trên công cụ tìm kiếm. Nếu chỉ dùng toàn <div> thì máy tìm kiếm khó hiểu phần nào quan trọng.

Thứ hai là Accessibility (khả năng hỗ trợ người khuyết tật). Những người dùng trình đọc màn hình sẽ dễ sử dụng web hơn khi trang có HTML ngữ nghĩa. Ví dụ, thẻ <nav> giúp họ biết ngay đâu là menu điều hướng để di chuyển nhanh hơn trong trang. Nếu chỉ dùng <div> thì trình đọc màn hình sẽ khó phân biệt chức năng của từng phần.

Một ví dụ thực tế là trên các trang bán hàng như Shopee hay Tiki. Phần menu thường dùng <nav>, phần sản phẩm dùng <section> hoặc <article>. Điều này giúp code dễ đọc và dễ bảo trì hơn khi làm nhóm.

Tuy nhiên, <div> vẫn phù hợp trong một số trường hợp, ví dụ khi chỉ cần chia layout hoặc nhóm các phần tử để CSS dễ chỉnh hơn mà không có ý nghĩa nội dung đặc biệt.