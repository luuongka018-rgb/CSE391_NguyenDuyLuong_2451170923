# Phần A
# A1 Các loại đầu vào
1. type="email" → Ô nhập text, tự kiểm tra có @ → dùng cho form đăng ký
2. type="text" → Ô nhập thông thường, kiểm tra độ dài tối thiểu, tối đa,mẫu → dùng cho nhập thông tin
3. type="password" → Ô nhập ký tự *, không tự xác thực nội dung → dùng nhập mật khẩu đăng nhập
4. type="number" → Ô nhập số có nút tăng/giảm, tự kiểm tra chỉ nhập số → dùng nhập số lượng sản phẩm cần mua
5. type="tel" → Ô nhập số điện thoại, mở bàn phím số trên điện thoại,  Không kiểm tra chặt định dạng → Dùng nhập số điện thoại
6. type="date" → Hiển thị lịch chọn ngày, tự kiểm tra định dạng ngày → dùng chọn ngày hoặc ngày sinh
7. type="file" → Nút “Choose File” để tải tệp, kiểm tra loại file nếu có thuộc tính accept → dùng tải ảnh đánh giá sản phẩm
8. type="checkbox" → Ô vuông tích chọn nhiều mục, không tự xác thực → dùng đồng ý điều khoản hoặc chọn nhiều sở thích
9. type="radio" → Nút tròn chỉ chọn một lựa chọn, không tự xác thực → dùng chọn phương thức lựa chọn
10. type="search" → Ô tìm kiếm có biểu tượng, không tự xác thực → Dùng tìm kiếm sản phẩm

# A2 Thuộc tính xác thực
`trường hợp 1`
<input type="text" required value="">
- Form sẽ không được gửi, vì thuộc tính required bắt buộc người dùng phải nhập dữ liệu, những ô đang để trống nên trình duyệt báo lôi.

`trường hợp 2`
<input type="email" value="abc">
- Form sẽ không được gửi, vì type="email" yêu cầu dữ liệu đúng định dạng email có ký tự @, giá trị "abc" không hợp lệ nên trình duyệt báo lỗi.

`trường hợp 3`
<input type="number" min="1" max="10" value="15">
- Form sẽ không được gửi, vì giá trị nhập vào là 15 vượt quá max="10", trình duyệt kiểm tra sẽ báo lỗi giá trị.

`trường hợp 4`
<input type="text" pattern="[0-9]{10}" value="abc123">
- Form sẽ không được gửi, vì pattern="[0-9]{10}" yêu cầu đúng 10 chữ số từ 0 - 9, value ="abc123" đang chứa chữ cái và không đủ 10.

`trường hợp 5`
<input type="password" minlength="8" value="123">
- Form sẽ không được gửi, vì minlength="8" yêu cầu mật khẩu ít nhất 8 ký tự, value="123" chỉ có 3 ký tự nên trình duyệt báo lỗi.

Kết quả: 
![alt text]({4328D483-431D-466B-B698-4ED5AF8E4D6B}.png)

# A3 Khả năng tiếp cận
1. <label for="email"> quan trọng với người dùng vì nó hiển thị nội dung với ô nhập liệu có id="email"
- giúp trình đọc màn hình sẽ đọc tên trường nhập khi người dùng di chuyển tới ô đầu vào.

2. <fieldset> + <legend> dùng khi cần nhóm các input liên quan đến nhau.
- giúp trình đọc màn hình hiểu các trường thuộc tính cùng một nhóm thông tin.

vd: 
<fieldset>
    <legend>Phương thức thanh toán</legend>

    <input type="radio" name="pay" id="cod">
    <label for="cod">COD</label>

    <input type="radio" name="pay" id="bank">
    <label for="bank">Chuyển khoản</label>
</fieldset>

3. aria-label dùng khi phần tử không có label hiển thị nhưng vẫn cần mô tả cho trình đọc màn hình.


# A4 Media

1. loading="lazy" trên thẻ <img> dùng để trì hoãn tải ảnh cho đến khi ảnh gần xuất hiện trên màn hình người dùng.

- nó cải thiển: 
+ Tăng tốc độ tải trang
+ Giảm dung lượng tải ban đầu
+ Tiết kiệm băng thông
+ Cải thiện hiệu năng website

- Không nên dùng:
+ Ảnh logo
+ Ảnh banner đầu trang
+ Ảnh quan trọng hiển thị ngay khi mở web

2. Nên cung cấp nhiều thẻ <source> trong <video> vì mỗi trình duyệt hỗ trợ code và định dạng video khác nhau  → Nếu một định dạng không chạy được, trình duyệt sẽ thử định dạng khác.

vd 
<video controls>
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    <source src="video.ogv" type="video/ogg">
</video>

3. định dạng video phổ biến:
+ MP4
+ WebM
+ OGG / OGV

# A5 So sánh <figure>với<img>

<!--Cách 1-->
<img src="product.jpg" alt="iPhone">

- dùng khi: 
+ Ảnh chỉ mang tính hiển thị đơn giản
+ Không cần chú thích riêng
+ Nội dung đã được giải thích ở xung quanh

- vd:  
    <img src="logo.png" alt="Logo cửa hàng">
        <!--Logo website ở header-->
------------------
<!-- Cách 2 -->
<figure>
    <img src="product.jpg" alt="iPhone 16 Pro Max 256GB Titan">
    <figcaption>iPhone 16 Pro Max — 25.990.000đ</figcaption>
</figure>

- dùng khi:
+ Ảnh cần chú thích
+ Muốn nhóm ảnh và mô tả thành một nội dung hoàn chỉnh
+ Thường dùng trong bài viết, sản phẩm, biểu đồ

- vd:
<figure>
    <img src="shoe.jpg" alt="Giày thể thao Nike màu trắng">
    <figcaption>áo — 500.000đ</figcaption>
</figure>

<!--Sản phẩm trong một website thương mại điện tử-->

# Phần C: PHÂN TÍCH & SUY LUẬN

# C1 Dạng gỡ lỗi

Lỗi 1: Dòng 2 — Input "Tên" không có <label for="...">, vi phạm accessibility
Sửa: <label for="name">Tên:</label> <input type="text" id="name" name="name" required>

Lỗi 2: Dòng 2 — Input “Tên” thiếu thuộc tính name.
Sửa: <input type="text" id="name" name="name">

Lỗi 3: Dòng 4 — Input email chỉ dùng placeholder, không có label.
Sửa: <label for="email">Email:</label>
<input type="email" id="email" name="email" placeholder="Email" required>

Lỗi 4: Dòng 6 — Password không có label và thiếu validation tối thiểu.
Sửa: <label for="password">Mật khẩu:</label>
<input type="password" id="password" name="password" minlength="8" required>

Lỗi 5: Dòng 7 — Ô nhập lại mật khẩu không có label.
Sửa: <label for="confirm-password">Nhập lại mật khẩu:</label>
<input type="password" id="confirm-password" name="confirm-password" required>

Lỗi 6: Dòng 9 — Số điện thoại dùng type="text" thay vì type="tel".
Sửa: <label for="phone">Phone:</label>
<input type="tel" id="phone" name="phone" pattern="[0-9]{10}" value="0901234567">

Lỗi 7: Dòng 11 — <select> không có label accessibility.
Sửa:<label for="city">Thành phố:</label>
<select id="city" name="city">
    <option>Hà Nội</option>
    <option>TP.HCM</option>
</select>

Lỗi 8: Dòng 16 — Checkbox điều khoản thiếu <input type="checkbox"> và không liên kết label.
Sửa:<input type="checkbox" id="agree" name="agree" required>
<label for="agree">
    Tôi đồng ý điều khoản
</label>

# C2: Xác thực thiết kế chiến lược.





















