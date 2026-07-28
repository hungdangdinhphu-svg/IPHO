# CÁCH GIẢI TỔNG QUÁT : Cơ & Điện-Từ học

---

## PHẦN I — SƠ ĐỒ TỔNG QUÁT: QUY TRÌNH 10 BƯỚC (B0 → B10)

```
B0  Quét văn bản & hình ảnh — trích xuất dữ kiện
B1  Định nghĩa Hệ & lựa chọn hệ quy chiếu
B2  Đếm Bậc Tự Do thô (f_raw)                         [Trụ cột A]
B3  Liệt kê Ràng buộc                                 [Trụ cột B]
B4  Săn Đối xứng / Định luật bảo toàn (Noether)       [Trụ cột C]
B5  Chọn Tọa độ suy rộng tối thiểu (f_eff)
B6  Xấp xỉ hóa & Phân tích thang đo                   [Trụ cột D]
B7  Chọn "ngôn ngữ chi phối" đúng 
B8  Điều kiện biên & điều kiện đầu (nguồn tin ẩn thứ 2)
B9  Giải hệ (đại số / vi phân / đồ thị / số)
B10 Kiểm tra ngược — Verification Protocol
```


---

## B0 — QUÉT (Full Scan Protocol)

**Nguyên tắc:** Đề bài là dữ liệu nén — mỗi tính từ, mỗi con số, mỗi đường nét trong hình/văn bản đều mang thông tin.

**Thủ tục bắt buộc:**

1. Đọc chậm **toàn bộ** đề một lượt, không giải, chỉ **gạch chân**:
   - Mọi đại lượng đã cho (kèm đơn vị, và **dấu** nếu có: đại số hóa mọi đại lượng ngay từ đầu — dòng điện, điện tích, công,.. đều là đại lượng có dấu);
   - Mọi tính từ mô tả (nhẹ, lý tưởng, không ma sát, rất dài, mảnh, đồng chất, chuẩn tĩnh, đủ lâu, ban đầu, tức thời…);
   - Động từ chỉ hành động/biến cố (thả ra, đóng khóa K, đảo cực, cắt dây, va chạm…);
   - Câu hỏi thật sự (đại lượng cần tìm — đây là "biến mục tiêu", định hướng bạn chọn phương pháp ở B7).
2. Nếu có hình: quét **trái→phải, trên→dưới**, liệt kê **từng** phần tử (điện trở, tụ, cuộn, ròng rọc, bản lề, mặt tiếp xúc…) và **từng** ký hiệu góc/khoảng cách/chiều mũi tên dòng điện — dấu mũi tên = quy ước dấu, không phải chiều thật.
3. Lập **Bảng biến số**: | Đã cho | Ký hiệu | Ẩn cần tìm | — việc lập bảng buộc não bộ tường minh hóa từng dữ kiện thay vì "cảm giác đã hiểu".
4. **Tự vẽ lại hình** (kể cả khi đề đã có hình) — thao tác vẽ lại chính là bước đầu tiên của B1/B2, và nó lộ ra ràng buộc mà mắt "lướt qua" khi chỉ nhìn hình có sẵn.
5. Đặc biệt với hình: **không giả định gì không được vẽ hoặc không được nói** (ví dụ không tự thêm ma sát nếu đề không nói có; nhưng cũng không tự loại bỏ ma sát nếu đề không nói "không ma sát" — xem Từ điển B3).

---



## B1 — ĐỊNH NGHĨA HỆ & HỆ QUY CHIẾU

- **Hệ là gì?** Liệt kê từng vật thể/mỗi phần tử là một "hệ con". Áp dụng **idea 4** (Kalda): đôi khi coi *toàn bộ* nhiều vật là **một hệ** (loại bỏ nội lực chưa biết) lợi hơn xét từng vật; đôi khi phải **tách** ra (idea 47: vật "nhẹ" ⇒ hợp lực & hợp mô-men trên nó luôn bằng 0, dùng để tách ẩn).

- **Chọn hệ quy chiếu thông minh** & idea 7, idea K-7, idea 73


---


## PHẦN 2 — TRỤ CỘT A: BẬC TỰ DO (Degrees of Freedom)

- Bậc tự do là số chiều của đa tạp không gian cấu hình Q; Và f = N - k khi điều kiện k phương trình đều độc lập tuyến tính với nhau.

- Đếm số xem hệ vật lý được mô tả gồm bao nhiêu "vật rắn/chất điểm" độc lập

- Và check xem loại khớp nối nào áp dụng

- Từ đó tính ra số bậc tự do mà ta cần

**Quy tắc kiểm tra (Fact 18 tổng quát hóa):**
$$f_{\text{eff}} = f_{\text{raw}} - (\text{số ràng buộc độc lập tìm được ở B3}) - (\text{số bảo toàn/đối xứng tìm được ở B4})$$


---


## PHẦN 3 — TRỤ CỘT B: RÀNG BUỘC & BIÊN

