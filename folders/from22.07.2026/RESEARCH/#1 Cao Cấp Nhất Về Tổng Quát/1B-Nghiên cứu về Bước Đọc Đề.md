
---

## 0. LỜI NÓI ĐẦU — TRIẾT LÝ "GIẢI MÃ"

Một đề bài Vật lý, xét về bản chất thông tin, **không phải** là một đoạn văn bản/hình vẽ tự do — nó là một **bản mã hoá đầy đủ** của:

- các đối tượng vật lý đang tồn tại (vật rắn, chất điểm, điện tích, dòng điện, trường...),
- các **bậc tự do** (degrees of freedom) của hệ,
- các **ràng buộc hình học và điều kiện biên** áp lên các bậc tự do đó,
- và (ẩn) các **đối xứng** của hệ dẫn tới đại lượng bảo toàn (Noether).

Nếu giải mã được đầy đủ 4 lớp thông tin trên, bài toán **tất yếu** trở thành một hệ phương trình toán học thuần tuý — luôn giải được bằng "Kiến thức đã có" (KTĐC) về Toán và các công cụ chuẩn (Newton, năng lượng, Kirchhoff, Gauss, Maxwell...).

**Hệ quả sư phạm quan trọng nhất:** cách huấn luyện đúng không phải là học thuộc lời giải của hàng nghìn bài (case-by-case — sẽ vỡ trận ngay khi đề đổi cấu trúc bề mặt), mà là huấn luyện **một quy trình giải mã tổng quát**, cố định, áp dụng được cho *mọi* bài trong phổ độ khó đã nêu.

> **Meta-nguyên lý (đối phó "Anti-Algorithmic Design"):**
> Người ra đề IPhO/VPHO có thể đổi *cách hỏi* — xáo trộn thứ tự dữ kiện, giấu ẩn số trong lời văn, vẽ hình theo góc lạ, đặt tên biến gây nhiễu, lồng ghép nhiều hiện tượng — nhưng **không thể đổi luật của vũ trụ** (Newton, Maxwell, nhiệt động lực, v.v.) và **không thể xoá bậc tự do thật của hệ**. Vì đề vẫn phải "khả thi" (solvable), nó buộc phải chứa đủ thông tin để tái dựng đúng 4 lớp trên. Do đó: "Anti-Anti-Algorithmic Design" chính là — **đừng học pattern bề mặt, hãy học quy trình trích xuất bất biến bên dưới bề mặt.** Mọi lớp "Anti^n" tiếp theo của người ra đề chỉ làm phong phú thêm *cách nguỵ trang*, không bao giờ vô hiệu hoá được quy trình giải mã đúng đắn ở lớp dưới.

---

## 1. KHUNG TỔNG QUÁT: TỪ HIỆN TƯỢNG ĐẾN ĐÁP SỐ

```
Hiện tượng Vật lý  --[Mô hình hoá/Xấp xỉ]-->  Hệ PT & Điều kiện biên  --[Công cụ Toán]-->  Đáp số
```

### 1.1. Bậc tự do (Degrees of Freedom — DOF)

- Trước khi viết bất kỳ phương trình nào, hãy **đếm DOF** của hệ: một chất điểm tự do trong mặt phẳng có 2 DOF; một vật rắn phẳng có 3 (2 tịnh tiến + 1 quay); một hệ N chất điểm không ràng buộc có 3N (không gian) hoặc 2N (phẳng).
- Mỗi ràng buộc **hình học** (dây không giãn, mặt tiếp xúc không xuyên qua nhau, vành khớp...) giảm DOF đi 1.
- **Fact 18 (Kalda):** số phương trình cân bằng lực/mô-men độc lập tối đa **bằng đúng số DOF** của vật. Nếu bạn viết nhiều hơn số DOF phương trình "độc lập", chắc chắn có ít nhất một phương trình dư thừa (hệ quả của các phương trình khác) — đây là cách tự kiểm tra khi bí.
- Với mạch điện: DOF tương ứng là số **dòng nhánh độc lập** hoặc số **thế nút độc lập** (N nút ⇒ N−1 phương trình Kirchhoff I độc lập).

### 1.2. Ràng buộc hình học & điều kiện biên

Đây là phần hay bị "giấu" nhất trong đề. Một số dạng ràng buộc kinh điển và cách "đọc" chúng:

| Từ khoá trong đề | Ý nghĩa vật lý ẩn | Phương trình sinh ra |
|---|---|---|
| "dây không giãn", "thanh cứng nối hai vật" | khoảng cách giữa 2 điểm cố định | quan hệ tuyến tính giữa dịch chuyển/vận tốc/gia tốc hai đầu (Kalda idea 32) |
| "ròng rọc lý tưởng", "không khối lượng" | lực căng như nhau hai bên; không tích trữ động năng/động lượng | T như nhau hai bên dây (idea 33) |
| "vừa khít", "không trượt", "lăn không trượt" | vận tốc điểm tiếp xúc = 0 | ràng buộc vận tốc góc–vận tốc dài (idea K-34, idea 65) |
| "chạm nhẹ", "tựa lên", "áp vào" | chỉ có phản lực pháp tuyến ≥ 0 (không kéo được) | điều kiện một phía N ≥ 0, mất tiếp xúc khi N=0 (idea 40, 41) |
| "nối đất" (mạch điện) | thế = 0 tại điểm đó, điện tích có thể trao đổi tự do với đất | biên Dirichlet cho thế |
| "cách điện", "cô lập" | tổng điện tích bảo toàn trên vật đó | biên Neumann kiểu bảo toàn |
| "lý tưởng" (ampe kế/vôn kế/nguồn) | điện trở trong = 0 hoặc ∞ tương ứng | rút gọn mạch |
| "đối xứng" (hình học/điện) | một số thế/dòng/áp lực phải bằng nhau | giảm số ẩn (Kiisk §1.4 "Sümmeetria") |

**Nguyên tắc đọc đề (Kalda idea 1–2, mở rộng cho mọi lĩnh vực):** chọn trục toạ độ / điểm quy chiếu mô-men / nút quy chiếu thế sao cho **triệt tiêu tối đa số ẩn không cần biết** (phản lực, lực căng dây, dòng nhánh không hỏi tới...).

### 1.3. Định lý Noether & các đại lượng bảo toàn — "từ điển đối xứng ⇒ bảo toàn"

| Đối xứng của hệ | Đại lượng bảo toàn | Điều kiện áp dụng |
|---|---|---|
| Bất biến tịnh tiến không gian (theo 1 trục) | động lượng theo trục đó | tổng ngoại lực theo trục = 0 (idea 43) |
| Bất biến quay quanh 1 trục | mô-men động lượng quanh trục đó | tổng mô-men ngoại lực quanh trục = 0 (fact 7) |
| Bất biến tịnh tiến thời gian (lực thế, không ma sát) | cơ năng | không có lực tiêu tán / lực ngoài biến thiên theo thời gian (fact 8) |
| Đối xứng gauge điện tích | điện tích toàn phần | luôn đúng (bảo toàn điện tích, Kirchhoff I) |
| Bất biến quay quanh trục đối xứng của vật dẫn/nam châm | dòng điện cảm ứng đối xứng | Kiisk §4.3 Sümmeetria |
| Hệ không có ma sát trong khi biến đổi chậm (2 khoảng thời gian đặc trưng lệch xa nhau) | bất biến đoạn nhiệt I (diện tích quỹ đạo pha) | idea 74 |

**Mẹo:** mỗi đại lượng bảo toàn tìm được sẽ **giảm 1 DOF hiệu dụng** của bài toán (idea 34, idea 35) — đây là lý do các bài "khó" luôn ẩn ít nhất một đối xứng không hiển nhiên.

### 1.4. THUẬT TOÁN GIẢI MÃ — 8 BƯỚC (áp dụng cho MỌI bài, không phân biệt Cơ/Điện)

1. **Đọc chậm, quét toàn bộ hình vẽ** trái→phải, trên→dưới; gạch chân *mọi* tính từ ("nhẹ", "lý tưởng", "trơn", "đủ dài", "chuẩn tĩnh", "đối xứng"...) — mỗi tính từ là một ràng buộc/xấp xỉ, không phải văn phong.
2. **Liệt kê đối tượng & bản chất**: vật rắn hay chất điểm? nguồn trường hay hạt thử? phần tử mạch tuyến tính hay phi tuyến?
3. **Đếm DOF** và liệt kê các ràng buộc hình học tương ứng (bảng 1.2).
4. **Quét đối xứng** ⇒ liệt kê đại lượng bảo toàn khả dụng (bảng 1.3).
5. **Chọn hệ quy chiếu / gốc thế / trục mô-men** tối ưu hoá số ẩn cần triệt tiêu (idea 1, 2, 7, 8).
6. **Chọn phương pháp phù hợp cấu trúc** — không phải "phương pháp quen tay": xem mục 2 & 3 để tra bảng dấu hiệu → phương pháp.
7. **Viết hệ phương trình**: số phương trình độc lập phải bằng đúng số ẩn (fact 18 tổng quát hoá).
8. **Kiểm tra ngược (sanity check):** giới hạn đặc biệt (m→0, R→∞, µ→0...), thứ nguyên, dấu, đối xứng của đáp số có khớp đối xứng của đề không.

---
