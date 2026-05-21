# PHẦN A — KIỂM TRA ĐỌC HIỂU

# Câu A1 (10đ) — 5 Loại Định Vị

- static: có | Theo luồng bình thường | Có | Layout mặc định
- relative: Có | So với vị trí ban đầu của chính nó | Có | Dịch chuyển nhẹ phần tử, làm mốc cho absolut
- absolute: Không | Theo tổ tiên có position gần nhất | Có | Tooltip, dropdown, popup
- fixed: Không | Theo viewport (màn hình) | Không | Navbar cố định, nút back-to-top
- sticky: Có | Theo viewport khi scroll | Một phần | Menu dính khi cuộn

# Câu hỏi thêm
- Khi nào absolute tham chiếu body?
    Khi không có tổ tiên nào có, thì lúc đó absolute sẽ lấy body hoặc viewport làm mốc.

- Khi nào absolute tham chiếu parent?
    Khi phần tử cha gần nhất có

- “Tổ tiên ở vị trí gần nhất” là gì?
Là phần tử cha gần nhất có: 
    Browser sẽ tìm từ phần tử con:
        lên cha
        rồi ông
        rồi các phần tử bên ngoài

# Câu A2 (10đ) — Flexbox vs Grid

/* Trường hợp 1 */
.container { display: flex; }
.item { flex: 1; }

## Giải thích
display: flex → các item nằm ngang
flex: 1 → chia đều chiều rộng

Có 4 item:
mỗi item chiếm 1 phần bằng nhau: 1 hàng, 4 cột bằng nhau
---------------------------------
/* Trường hợp 2 */
.container { display: flex; flex-wrap: wrap; }
.item { width: 45%; margin: 2.5%; }
/* 6 items → Bố cục = ??? (mấy hàng, mấy cột?) */

# Giải thích

Mỗi item:
45% + 2.5% + 2.5% = 50%

→ mỗi hàng chứa được 2 item

Có 6 item: 6/2=3 hàng

Bố cục: 3 hàng, 2 cột
---------------------------------
/* Trường hợp 3 */
.container { display: flex; justify-content: space-between; align-items: center; }

/* 3 items → Bố cục = ??? */
# Giải thích
    justify-content: space-between
    item đầu sát trái
    item cuối sát phải
    item giữa nằm giữa
    align-items: center
    căn giữa theo chiều dọc
bố cục: 1 hàng ngang, khoảng cách đều nhau


---------------------------------
/* Trường hợp 4 */
.container { display: grid; grid-template-columns: 200px 1fr 200px; gap: 20px; }
/* 3 items → Bố cục = ??? */
# Giải thích:
    Grid có:
    cột 1 = 200px
    cột 2 = phần còn lại (1fr)
    cột 3 = 200px
    Có 3 item → mỗi item vào 1 cột

- Bố cục: 1 hàng, 3 cột
---------------------------------
/* Trường hợp 5 */
.container { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
/* 7 items → Bố cục = ??? (mấy hàng? item cuối ở đâu?) */

# Giải thích:
repeat(3, 1fr)
→ grid có 3 cột bằng nhau
Có 7 item.
Hàng 1
    item 1
    item 2
    item 3
Hàng 2
    item 4
    item 5
    item 6
Hàng 3
    item 7
Bố cục: 3 hàng, item 7 nằm ở: hàng 3, cột 1.

# PHẦN C — SUY LUẬN

# Câu C1 (10đ) — Flexbox vs Grid: Khi nào dùng gì?
Cho 5 bài toán thực tế. Với mỗi câu hỏi, trả lời: dùng Flexbox , Grid , hay kết hợp cả hai ? Giải thích rút gọn tại sao.

Thanh điều hướng ngang (logo + menu + nút)
Lưới ảnh Instagram (3 cột đều nhau, số ảnh chưa biết trước)
Bố cục blog: nội dung chính + thanh bên
Footer with 4 cột thông tin (Về chúng tôi, Liên kết, Hỗ trợ, Liên hệ)
Card sản phẩm (ảnh trên, văn bản giữa, nút dưới — nút luôn Đáy)

1. Bài toán: Thanh điều hướng ngang (logo + menu + nút)
- Dùng: Flexbox
- Giải thích: Vì đây là layout 1 chiều (ngang). Flexbox rất mạnh để căn giữa, đẩy trái/phải và tạo khoảng cách đều.

2. Bài toán: Lưới ảnh Instagram (3 cột đều nhau, số ảnh chưa biết trước)
- Dùng: Grid
- Giải thích:Vì đây là layout 2 chiều (hàng + cột). Grid dễ tạo các cột đều nhau bằng repeat(3, 1fr).

3. Bài toán: Bố cục blog: nội dung chính + thanh bên
- Dùng: Grid
- Giải thích: Có nhiều vùng layout rõ ràng (main + sidebar). Grid kiểm soát cột tốt hơn Flexbox.

4. Bài toán: Footer có 4 cột thông tin
- Dùng: Grid hoặc Flexbox
- Giải thích: Nếu chỉ cần 4 cột ngang đơn giản → Flexbox. Nếu muốn đều cột và responsive đẹp → Grid tốt hơn.

5. Bài toán: Card sản phẩm (ảnh trên, văn bản giữa, nút dưới — nút luôn đáy)
- Dùng: Flexbox
- Giải thích: Vì cần sắp xếp theo chiều dọc và đẩy nút xuống đáy bằng margin-top: auto