# CÁCH GIẢI TỔNG QUÁT : Cơ & Điện-Từ học

Lưu ý quan trọng : Tôi giả định rằng ta đã học và đã làm nhiều bài tập và đọc nhiều lý thuyết để ta có dày dặn kinh nghiệm, pattern, case-by-case từ trước. Những gì tôi ghi ở bên dưới đều chỉ liên quan đến những gì thực sự tổng quát hoặc cực kỳ phổ biến.

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


### 2.2 Định lý A (Đếm bậc tự do — Định lý Giá trị Chính quy)

> **Định lý A.** Cho $N$ toạ độ thô $x=(x^1,\dots,x^N)\in\mathbb R^N$ và $k$ hàm ràng buộc toàn chỉnh $g_1,\dots,g_k: \mathbb R^N\times\mathbb R\to\mathbb R$, $g_j(x,t)=0$. Giả sử tại điểm đang xét, ma trận Jacobi $\partial(g_1,\dots,g_k)/\partial x$ có **hạng đầy đủ** $k$ (đây là định nghĩa chính xác, kiểm tra được, của "$k$ ràng buộc độc lập"). Khi đó tập nghiệm $Q_t = \{x: g_j(x,t)=0\ \forall j\}$ là một đa tạp trơn với
> $$\dim Q_t = N-k = f.$$

**Chứng minh.** Đây là hệ quả trực tiếp của Định lý Hàm ẩn. Vì hạng Jacobi $=k$, sau khi (nếu cần) sắp lại thứ tự toạ độ, ma trận con $k\times k$ gồm các đạo hàm riêng theo $k$ biến cuối $x^{N-k+1},\dots,x^N$ khả nghịch tại điểm $x_0$. Định lý Hàm ẩn cho phép giải $k$ biến này như hàm trơn của $N-k$ biến còn lại trong một lân cận của $x_0$: $x^{N-k+i} = \varphi_i(x^1,\dots,x^{N-k})$. Ánh xạ $x\mapsto (x^1,\dots,x^{N-k})$ hạn chế trên $Q_t$ do đó là một vi phôi địa phương lên một tập mở của $\mathbb R^{N-k}$. Vậy $Q_t$ trơn, chiều $N-k$ tại lân cận mọi điểm thoả điều kiện hạng. $\blacksquare$

Định lý A **hoàn toàn tổng quát và thuật toán** — cho $N,k$ và các $g_j$, việc tính hạng Jacobi là đại số tuyến tính thuần tuý (khử Gauss), không cần trực giác.


- Bậc tự do là số chiều của đa tạp không gian cấu hình Q; Và f = N - k khi điều kiện k phương trình đều độc lập tuyến tính với nhau.

- Đếm số xem hệ vật lý được mô tả gồm bao nhiêu "vật rắn/chất điểm" độc lập

- Và check xem loại khớp nối/ràng buộc nào áp dụng

- Từ đó tính ra số bậc tự do mà ta cần

**Quy tắc kiểm tra (Fact 18 tổng quát hóa):**
$$f_{\text{eff}} = f_{\text{raw}} - (\text{số ràng buộc độc lập tìm được ở B3}) - (\text{số bảo toàn/đối xứng tìm được ở B4})$$


---


## PHẦN 3 — TRỤ CỘT B: RÀNG BUỘC & BIÊN

> Mỗi ràng buộc hình học/vật lý = **1 phương trình liên hệ giữa các DOF**, làm $f_{eff}$ giảm đi đúng **1**.

**Phép kiểm tra gốc (khi từ khóa không rõ / bị "giấu"):** dùng **phép dịch chuyển ảo (virtual displacement)** — tưởng tượng hệ nhích một lượng vi phân $\delta$, hỏi "đại lượng nào **buộc phải không đổi**?" (chiều dài dây, thông lượng qua vòng siêu dẫn, điện tích trên vật cô lập…). Đây là cách tái tạo ràng buộc **từ nguyên lý đầu tiên**, không phụ thuộc từ khóa có xuất hiện hay không — đây là "lưới an toàn" chống lại việc đề bài dùng cách diễn đạt lạ để né từ khóa quen thuộc.


### 3.1 Chính xác hoá ranh giới toàn chỉnh / không toàn chỉnh

`[MD]` định nghĩa holonomic là $F(q,t)=0$, non-holonomic là bất phương trình hoặc vi phân không tích phân được $\sum A_i\,dq_i+A_t\,dt=0$. Câu hỏi tự nhiên: *"làm sao biết một ràng buộc vi phân cho trước có 'thực sự' không tích phân được hay không, một cách tổng quát, không case-by-case?"* — Câu trả lời là **có**, và đó là nội dung Định lý B dưới đây (đây là phần bị bỏ ngỏ hoàn toàn trong `[MD]`).

> **Định lý B (Tiêu chuẩn Frobenius).** Cho ràng buộc Pfaff $\omega = \sum_i A_i(q,t)\,dq^i + A_t(q,t)\,dt = 0$ (một dạng vi phân bậc 1). Ràng buộc này là **toàn chỉnh** (tồn tại thừa số tích phân $\mu$ và hàm $F$ sao cho $\omega=\mu\,dF$, tức mặt $F=$const chứa trọn quỹ đạo) **khi và chỉ khi**
> $$\omega\wedge d\omega = 0.$$
> Đây là một phép kiểm tra **thuật toán, tổng quát tuyệt đối** trên lớp ràng buộc Pfaff đơn: chỉ cần lấy vi phân ngoài và nhân ngoài, không cần đoán.

*(Đây là định lý Frobenius/Pfaff cổ điển trong hình học vi phân; whitepaper không chứng minh lại từ tiên đề hình học vi phân — vượt phạm vi IPhO — mà **kiểm chứng tính đúng đắn bằng hai ví dụ tính tay độc lập, đầy đủ**, đủ để một học sinh IPhO tự tay áp dụng.)*

**Ví dụ kiểm chứng B.1 (toàn chỉnh).** Đĩa bán kính $R$ lăn không trượt trên một đường thẳng: $\dot x = R\dot\theta \Rightarrow \omega = dx - R\,d\theta$. Vì $R$ hằng, $d\omega = 0$, nên $\omega\wedge d\omega = \omega\wedge 0=0$ tự động. **Toàn chỉnh** — tích phân trực tiếp: $x-R\theta=$const. (Đây chính là cơ sở toán học của các ràng buộc lăn dùng xuyên suốt `[MEH, pr. 44, 47, 65]`, nơi ràng buộc lăn được dùng như một phương trình đại số bình thường.)

**Ví dụ kiểm chứng B.2 (không toàn chỉnh — "xe đạp một bánh"/đĩa lăn tự do đổi hướng).** Cấu hình $(x,y,\theta)$, ràng buộc "không trượt ngang": $-\sin\theta\,dx+\cos\theta\,dy=0$, tức $\omega=-\sin\theta\,dx+\cos\theta\,dy$.
$$d\omega = -\cos\theta\,d\theta\wedge dx-\sin\theta\,d\theta\wedge dy.$$
Tính trực tiếp (khai triển đầy đủ, dùng phản đối xứng $dq^i\wedge dq^j=-dq^j\wedge dq^i$, $dq^i\wedge dq^i=0$):
$$\omega\wedge d\omega = -\,dx\wedge dy\wedge d\theta \;\neq\; 0.$$
**Không toàn chỉnh.** Đây là lý do toán học nghiêm ngặt vì sao một chiếc xe/đĩa có thể đi từ *bất kỳ* cấu hình $(x,y,\theta)$ nào đến *bất kỳ* cấu hình nào khác (đỗ xe song song!) dù tại mỗi thời điểm chỉ có 1 bậc tự do vận tốc khả dĩ: không gian cấu hình *không* bị thu hẹp, dù không gian *vận tốc tức thời* bị thu hẹp — **đúng chính xác** như câu chữ của `[MD]`: *"Non-holonomic... giới hạn quỹ đạo tiến triển của hệ"* chứ không làm giảm DOF của $\mathcal Q$. Whitepaper này đã **chứng minh** thay vì chỉ khẳng định lại điều `[MD]` phát biểu.


**Quan sát quan trọng :**

Có một lớp tình huống mà Định lý A thất bại theo nghĩa kỹ thuật: khi số ràng buộc **hình học lý tưởng hoá** (dây/thanh cứng tuyệt đối) vượt quá số bậc tự do thực — hệ *siêu tĩnh*. `[MEH, idea 30]` chỉ ra chính xác đây là lúc mô hình "vật rắn tuyệt đối" phải được **nới lỏng** thành mô hình đàn hồi (`[MEH, fact 13]`, định luật Hooke $k=AY/L$) để đóng hệ phương trình.

---

## B4 — SĂN ĐỐI XỨNG: ĐỊNH LÝ NOETHER NHƯ MÁY GIẢM BẬC TỰ DO — [Trụ cột C]

> **Định lý Noether (diễn giải thực dụng):** *Nếu tồn tại một phép biến đổi liên tục làm cho toàn cảnh vật lý "trông y hệt như trước", thì tồn tại một đại lượng bảo toàn tương ứng.*

Đây là công cụ **mạnh nhất** để giảm bậc tự do *hiệu dụng* mà không cần giải phương trình vi phân — mỗi đối xứng tìm được cho ta **một tích phân đầu** (first integral), tức hạ bậc của hệ phương trình vi phân đi 1.
























