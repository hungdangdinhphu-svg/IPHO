# ĐỘNG HỌC — VẤN ĐỀ 1 & VẤN ĐỀ 2
### (Nhận diện CÔNG CỤ + tiền xử lý → Chuyển bài Vật Lý sang bài Toán) — hướng tới HSGQG / VPhO / IPhO

*Phiên bản 1.0 — 19/09/2026. Tài liệu làm việc, không phải bản cuối. Mọi phần đều có thể sai; các mục "Mức tin cậy" ở 0.2 nói rõ cái gì đã được kiểm chứng và cái gì chưa.*

---

## MỤC LỤC

0. Đọc trước: phạm vi, mức tin cậy, kiến trúc, ký hiệu
1. Mô hình hình thức M = (O, V, L, C, Q, I) cụ thể hoá cho Động học
2. Thư viện CÔNG CỤ của Động học (K0 → K15) — mỗi công cụ là một "dạng"
3. Thư viện TOÁN TỬ TIỀN XỬ LÝ (T1 → T15)
4. VẤN ĐỀ 1 — Giao thức nhận diện công cụ và quét CHỖ
5. VẤN ĐỀ 2 — Quy trình chuyển sang Toán ("Tọa độ hoá mở rộng", bản tái dựng)
6. Mười ví dụ thực hành (dừng ở bàn giao cho Vấn đề 3)
7. Mở rộng cho IPhO
8. Danh mục lỗi kinh điển
9. Kế hoạch luyện tập & cách kiểm thử thư viện
10. Giới hạn & việc còn dang dở
- Phụ lục A: Bảng tra nhanh Suf / Pre / Post
- Phụ lục B: Công thức chuẩn

---

## 0. ĐỌC TRƯỚC

### 0.1. Phạm vi

**Làm:** Vấn đề 1 (nhận diện công cụ + tiền xử lý đưa đề về dạng dùng được công cụ) và Vấn đề 2 (chuyển chính thức sang bài Toán) cho phần **Động học**: chất điểm, vật rắn, dây/thanh/ròng rọc, lăn/tiếp xúc, chuyển động tương đối, ném xiên, quỹ đạo & bán kính cong, đuổi bắt, giao điểm phi vật chất, cực trị động học, cùng vài cầu nối sang IPhO (vật rắn 3D, hệ quy chiếu quay, tương đối hẹp, chuyển động của ảnh).

**Không làm:** Vấn đề 3 (giải Toán). Mọi ví dụ dừng ở "hệ Toán đã đóng kín, sẵn sàng bàn giao". Những chỗ tôi ghi kết quả cuối (ví dụ ρ = 4R ở đỉnh cycloid) chỉ là **mẫu đối chiếu** để bạn thử xem quy trình của mình có ra đúng không — không phải phần giải.

**Ranh giới với Động lực học:** Động học chỉ chứa *hình học + thời gian*. Những điều kiện như "dây luôn căng", "vật còn tiếp xúc", "không trượt vì ma sát đủ lớn" — ở đây được **ghi nhận thành Pre cần kiểm tra sau** (xem mức [K] ở 1.7). Việc kiểm tra bằng lực thuộc phần khác.

### 0.2. Mức tin cậy — nói thẳng cái gì đã kiểm, cái gì chưa

Tôi phân nội dung thành ba mức. Đây là phần trung thực bắt buộc: bạn dùng tài liệu này để thi, nên bạn phải biết chỗ nào có thể dựa vào.

**Mức A — đã kiểm bằng máy trong chính phiên làm tài liệu này (sympy/numpy/scipy):**

| # | Mệnh đề | Cách kiểm |
|---|---|---|
| A1 | Đuổi bắt trong n-giác đều, mỗi con hướng về con kế: T = a/(2v·sin²(π/n)) | mô phỏng số ODE, n = 3,4,5,6 (sai lệch < 0,1% do ngưỡng dừng) |
| A2 | Bán kính cong của cycloid: ρ = 4R·sin(θ/2); ở đỉnh ρ = 4R | symbolic |
| A3 | Tay quay–thanh truyền: v_B = ω·r·PB/PA với P là tâm quay tức thời của thanh | số, 4 vị trí ngẫu nhiên |
| A4 | Parabol an toàn Y = v₀²/(2g) − gX²/(2v₀²); tầm xa trên mặt nghiêng lên/xuống = v₀²/(g(1 ± sinα)); góc ném tối ưu trên mặt nghiêng | symbolic + số |
| A5 | Vận tốc giao điểm hai đường: u·nᵢ = wᵢ (nᵢ pháp tuyến, wᵢ tốc độ pháp tuyến của đường i) | symbolic (đường thẳng, góc bất kỳ) |
| A6 | Thang trượt: trung điểm luôn cách góc O đoạn L/2 | symbolic |
| A7 | Gia tốc trong toạ độ cầu (3 thành phần) | symbolic |
| A8 | Đường thân khai (involute): tốc độ = ℓφ̇, ρ = ℓ; gia tốc a = R(φ̇²+φφ̈)n̂ − ℓφ̇²ê_s | symbolic |
| A9 | Khoảng cách nhỏ nhất của hai chất điểm chuyển động đều: d_min = \|r₀×v\|/\|v\|, t* = −r₀·v/v² | số |
| A10 | Cực tiểu thời gian ⇒ sinθ₁/v₁ = sinθ₂/v₂ (Snell) | số |
| A11 | Gia tốc trong hệ quay 2D: a = a_O' + α×r' + ω×(ω×r') + 2ω×v_rel + a_rel | symbolic |
| A12 | Grübler cho các cơ cấu mẫu (tay quay 1, 4 khâu 1, đĩa lăn 1, đĩa trượt 2, thang 1) | số học |
| A13 | ∂L/∂C = û_in − û_out cho dây quấn quanh ròng rọc tròn có tâm C dịch chuyển | số (đạo hàm sai phân) |
| A14 | Đuổi bắt mục tiêu chuyển động thẳng đều: v_A·r + v_B·ξ = (v_B²−v_A²)t + const; T = (v_A r₀ + v_B ξ₀)/(v_A²−v_B²) | mô phỏng số |
| A15 | Ném từ độ cao h: tanα_opt = v₀/√(v₀²+2gh), R_max = (v₀/g)√(v₀²+2gh) | số |
| A16 | Ca nô qua sông, độ trôi nhỏ nhất d√(v²−u²)/u khi sinθ = u/v (u<v) | số |
| A17 | Nón lăn không trượt (đỉnh cố định): \|ω\| = Ω·cotβ | đại số vector |
| A18 | Tâm gia tốc: \|a_B\| = \|JB\|√(α²+ω⁴) | số |
| A19 | Chuyển động ảnh qua thấu kính mỏng: v_ảnh = −m²·v_vật (thành phần dọc trục) | symbolic |
| A20 | Vòng tròn giãn nở của đạn ném: bao của các đường tròn tâm (0, −gt²/2), bán kính v₀t chính là parabol an toàn | symbolic (bao) |

**Mức B — công thức chuẩn của giáo trình, tôi tin đúng nhưng chưa chạy máy trong phiên này:** SUVAT, thành phần Frenet (a_t, a_n), công thức toạ độ cực/trụ, định lý Kennedy, định lý chiếu vận tốc, công thức Lorentz/Doppler/quang sai, Kutzbach 3D, công thức ρ = (1+y′²)^{3/2}/|y″|. Hãy đối chiếu với giáo trình khi dùng lần đầu.

**Mức C — phần THIẾT KẾ của tôi, chưa được thử trên một kho đề thật:** cấu trúc Dom/Pre/Suf/Post/Err cho từng công cụ; "Suf = vị ngữ kiểm được bằng mắt"; sổ quét; đếm vòng kín bằng số chu trình; "bổ đề vận tốc pháp" dùng làm công cụ K8; các bảng định tuyến Q→công cụ; toàn bộ mục 4, 5, 9. **Đây là giả thuyết làm việc**, và mục 9 đưa ra phép thử để bạn tự bác bỏ hoặc xác nhận nó.

**Hai lưu ý thêm:**
1. Tôi **không truy cập được** thư mục GitHub bạn dẫn (trang chặn truy cập tự động). Vì vậy tôi không biết định nghĩa chính xác của "Phương pháp/Thuật toán Tọa độ Hoá Mở rộng" và "Giải pháp cho vấn đề 2" trong repo của bạn. Mục 5 là **bản tái dựng của tôi** từ mô tả trong README và từ thực hành động học cơ cấu. Nếu khác định nghĩa của bạn, ưu tiên định nghĩa của bạn.
2. **Tính đầy đủ của thư viện K0–K15 KHÔNG được chứng minh.** Tôi không thể khẳng định nó phủ mọi đề HSGQG/IPhO. Điều tôi khẳng định được chỉ là: mỗi công cụ có thẻ kiểm tra rõ ràng, và có quy trình để phát hiện khi thư viện thiếu (mục 4.6).

### 0.3. Kiến trúc tổng thể

```
ĐỀ BÀI ──► [Lớp M] Xây mô hình M=(O,V,L,C,Q,I)          (mục 1)
              │
              ▼
          [Lớp S] Giao thức quét CHỖ = VẤN ĐỀ 1            (mục 4)
              │   dùng: Thư viện L = {K0..K15}, mỗi thẻ có Dom/Pre/Suf/Post/Err   (mục 2)
              │   dùng: Toán tử tiền xử lý T1..T15                                 (mục 3)
              ▼
          [Lớp P] Pipeline P0..P8 = VẤN ĐỀ 2               (mục 5)
              │   đầu ra: hệ Toán ĐÓNG KÍN + miền + điều kiện đầu
              ▼
          BÀN GIAO VẤN ĐỀ 3 (giải Toán — không thuộc tài liệu này)
```

Nguyên tắc xuyên suốt, bám đúng tinh thần README của bạn: **"dạng" = công cụ**, không phải chuyên đề SGK. Ròng rọc, cung, thang, bánh xe… đều chỉ là *cách gặp* của cùng vài công cụ (K1: bảo toàn độ dài; K2: tiếp xúc–lăn; K3: vật rắn; K8: điểm phi vật chất…). Bạn học công cụ, không học "loại bài".

### 0.4. Ký hiệu

- Vector viết r, v, a, ω, α; độ lớn viết |v|. "×" là tích có hướng, "·" là tích vô hướng. Trong mặt phẳng: ẑ × (x, y) = (−y, x).
- ω × r (2D) = ω·(−r_y, r_x) khi ω = ω·ẑ (dương = ngược chiều kim đồng hồ).
- ℓ (chữ ℓ) chỉ **định luật/công cụ**; độ dài dùng L, d, s.
- Pre(ℓ), Suf(ℓ), Post(ℓ), Dom(ℓ), Err(ℓ) như trong README của bạn.
- **CHỖ** (in hoa) = vị trí trong bài để áp dụng một công cụ. **Kiểu CHỖ** = loại đối tượng của bài mà công cụ áp lên (điểm, cặp điểm, vật rắn, tiếp điểm, sợi dây, vòng kín, thời điểm, khoảng thời gian, hệ quy chiếu, giao điểm, …).
- q = biến cấu hình độc lập (toạ độ suy rộng); f(q,t) = 0 = ràng buộc holonomic.
- "Trực giác còn lại" = phần của công cụ mà tôi **không** chuyển được thành thủ tục máy móc; tôi ghi ra cho bạn biết chính xác nó là gì (đúng tinh thần "đến đây là tốt rồi" — nhưng không giấu nó đi).

---

## 1. MÔ HÌNH HÌNH THỨC M = (O, V, L, C, Q, I) CHO ĐỘNG HỌC

README của bạn nói: bài khó thường do **mô hình chưa đúng/đủ/nhất quán/đóng kín**, không phải do không biết công cụ. Mục này đổ khuôn mô hình vào riêng Động học để bước "đọc đề" có thể làm bằng danh mục kiểm tra chứ không bằng cảm giác.

### 1.1. O — Ontology: các loại thực thể của một bài Động học

| Loại thực thể | Ví dụ | Điều cần khai báo | Cạm bẫy |
|---|---|---|---|
| **Điểm vật chất** | chất điểm; một điểm cố định trên vật rắn | quỹ đạo, hệ quy chiếu | "Điểm trên vật" ≠ "điểm hình học đang trùng với nó" |
| **Điểm phi vật chất (hình học)** | tiếp điểm, giao điểm hai thanh, bóng/vệt sáng, tâm quay tức thời, điểm bẻ của dây | được định nghĩa bằng hình học (giao/tiếp xúc/chiếu) | Vận tốc của nó **không** tuân thuộc tính "cùng vật rắn"; có thể lớn tuỳ ý (kể cả > c). Xem K8 |
| **Vật rắn** | đĩa, thanh, khối, nêm | số bậc tự do (2D: 3; 3D: 6); khớp/tiếp xúc với các vật khác | Điểm A, B thuộc **cùng** vật rắn mới dùng được v_B = v_A + ω×AB |
| **Liên kết độ dài** | dây không giãn, thanh cứng nhẹ, cọc | chiều dài cố định; hai đầu; các điểm bẻ | Dây là ràng buộc **một chiều** (chùng được) — thanh thì hai chiều |
| **Bề mặt/đường dẫn** | mặt phẳng nghiêng, rãnh, cung tròn, tường | dạng hình học; đứng yên hay chuyển động | Bề mặt chuyển động ⇒ ràng buộc phụ thuộc t (rheonomic) |
| **Hệ quy chiếu** | đất, nêm, đĩa quay, vật rơi tự do | quán tính? quay? | Mọi v, a phải nói rõ "đối với hệ nào" |
| **Topology** | đồ thị: nút = vật, cạnh = khớp/tiếp xúc/dây | các chu trình kín | Dùng để đếm bậc tự do và số phương trình vòng (1.6) |

### 1.2. V — Biến

Mỗi đại lượng phải được gán **một** trong các nhãn: hằng (đề cho), tham số hình học, biến cấu hình độc lập q, biến phụ (phụ thuộc q qua ràng buộc), ẩn cần tìm, hoặc thời gian t. **Quy tắc:** viết ra bảng biến ngay đầu bài. Lỗi thường gặp: một đại lượng vừa đóng vai "cho trước" vừa bị ràng buộc làm "biến phụ" (khiến hệ thừa/mâu thuẫn ngầm).

### 1.3. C — Ràng buộc: phân loại để biết nó sinh ra bao nhiêu phương trình và dạng gì

| Loại | Dạng | Ví dụ Động học | Ghi chú |
|---|---|---|---|
| Holonomic, hai chiều | f(q, t) = 0 | thanh cứng, khoảng cách cố định, điểm trượt trên rãnh, **lăn không trượt trên đường** (khả tích) | Đạo hàm theo t → ràng buộc vận tốc **tuyến tính** theo q̇ |
| Holonomic, một chiều | f(q, t) ≤ 0 | dây (có thể chùng), tiếp xúc (có thể tách) | **Phải kiểm tra sau**: trạng thái nào thì chuyển thành đẳng thức |
| Phi holonomic | g(q, q̇) = 0 không khả tích | bánh xe/xe không trượt ngang (v ∥ trục xe); cầu/đĩa lăn không trượt trên mặt phẳng 2D | Không thể khử q̇ về ràng buộc vị trí; cần giữ ở dạng vận tốc |
| Ràng buộc vi phân "hướng" | v_A ∥ (r_B − r_A) | đuổi bắt | Là ràng buộc vận tốc cho trước, thường phi holonomic |
| Phụ thuộc thời gian (rheonomic) | f(q, t) = 0 với t hiện | tường/nêm chuyển động cho trước | Đạo hàm có thêm số hạng ∂f/∂t |
| Điều kiện đầu/biên | q(0), q̇(0), điều kiện tại biên | thả không vận tốc đầu; xuất phát từ mặt đất | Cần số điều kiện đầu = bậc của phương trình vi phân |
| Đối xứng | bất biến dưới phép biến đổi | n-giác đều đuổi bắt | Suy ra từ tính duy nhất nghiệm (xem K9); cần ghi rõ Pre |

### 1.4. Q — Câu hỏi: 10 loại và dạng Toán tương ứng

| Q | Câu hỏi thường gặp | Dạng Toán đích |
|---|---|---|
| Q1 | v, a, toạ độ **tại một thời điểm/cấu hình cho trước** | hệ tuyến tính theo v (hoặc a) với ma trận Jacobi tại cấu hình đó |
| Q2 | Tỉ số vận tốc/gia tốc giữa hai điểm | như Q1, khử ẩn phụ |
| Q3 | Phương trình quỹ đạo | khử tham số t (hoặc q) khỏi r(t) |
| Q4 | Thời điểm/vị trí **gặp nhau, va chạm** | hệ đại số r_A(t) = r_B(t) (2–3 phương trình, 1 ẩn t + ẩn phụ) |
| Q5 | Cực trị (nhỏ nhất/lớn nhất) | tối ưu 1 biến; hoặc điều kiện discriminant; hoặc đường bao |
| Q6 | Quãng đường, vận tốc trung bình | tích phân ∫\|v\|dt (chia đoạn tại điểm đổi chiều) |
| Q7 | Bán kính cong, gia tốc pháp/tiếp tuyến | ρ = v²/a_n = \|v×a\|⁻¹·v³ |
| Q8 | Biện luận: số nghiệm, điều kiện tồn tại, miền | discriminant/miền giá trị/tính đơn điệu |
| Q9 | Tìm bất biến, quỹ tích | phương trình bất biến; đường bao F=0, ∂F/∂λ=0 |
| Q10 | Điều kiện để mô hình còn đúng (dây căng, còn tiếp xúc, không chạm đất trước) | bất đẳng thức cần kiểm ở **sau** khi có nghiệm |

### 1.5. I — Ánh xạ diễn giải: những quyết định hay sai nhất

Đọc từng cụm từ của đề và ghi lại **nghĩa mình chọn**:

| Cụm từ | Nghĩa cần chốt |
|---|---|
| "vận tốc của A" | đối với hệ nào? vector hay độ lớn? tức thời hay trung bình? |
| "đi được quãng đường" vs "độ dời" | quãng đường = ∫\|v\|dt; độ dời = Δr |
| "gặp nhau" vs "quỹ đạo cắt nhau" | gặp nhau: cùng vị trí **cùng lúc**; quỹ đạo cắt: không cần cùng lúc |
| "không trượt" | tại **điểm vật chất nào** của mỗi vật? (thường: điểm vật chất trùng tại tiếp điểm) |
| "dây không giãn", "dây nhẹ" | Động học chỉ cần "không giãn"; "nhẹ" là chuyện lực. Dây có căng suốt quá trình không? → Pre [K] |
| "tầm xa" | theo phương ngang hay dọc theo mặt nghiêng? |
| "gia tốc" | toàn phần, tiếp tuyến, hay pháp tuyến? trong hệ nào? |
| "thả rơi", "ném từ mặt đất" | có vận tốc đầu? độ cao đầu? |
| "vô cùng xa", "rất nhỏ", "gần đúng" | ngầm chứa Err; ghi ra tham số nhỏ |

### 1.6. Đếm bậc tự do và kiểm tra "đóng kín"

Đây là công cụ **kiểm tra đủ/thừa** rẻ nhất — bạn nên làm trước khi viết bất kỳ phương trình nào.

**(a) Đếm bậc tự do.**
- **Chất điểm** trong mặt phẳng: 2N − (số ràng buộc độc lập). Mỗi dây không giãn nối vào hệ cho 1 ràng buộc.
- **Cơ cấu phẳng (Grübler–Kutzbach):**
  F = 3(n − 1) − 2·j₁ − j₂
  với n = số khâu **kể cả giá cố định**; j₁ = số khớp làm mất 2 bậc (bản lề, con trượt–rãnh, **lăn không trượt**); j₂ = số khớp làm mất 1 bậc (tiếp xúc có thể trượt, chốt trượt trong rãnh).
- **Trong không gian:** F = 6(n − 1) − Σ(6 − fᵢ) với fᵢ = số bậc tự do của khớp thứ i.

*Đã kiểm (A12):* tay quay–thanh truyền–con trượt: n = 4, j₁ = 4 ⇒ F = 1. Cơ cấu 4 khâu bản lề: F = 1. Đĩa lăn không trượt trên đường: n = 2, j₁ = 1 ⇒ F = 1. Đĩa có thể trượt: j₂ = 1 ⇒ F = 2. Thang hai đầu tựa sàn và tường (hai tiếp xúc có thể trượt): n = 2, j₂ = 2 ⇒ F = 1.

*Cảnh báo:* Grübler có thể sai với cơ cấu **quá ràng buộc (overconstrained)** — nơi hình học đặc biệt làm hai ràng buộc trùng nhau. Khi số F tính ra lệch với trực quan, kiểm tra xem hình học có đặc biệt không.

**(b) Đếm chu trình (vòng kín) độc lập.** Dựng đồ thị G: nút = vật (kể cả giá), cạnh = khớp/tiếp xúc/dây. Nếu G liên thông với V nút, E cạnh thì số chu trình độc lập là

  ℓ_loop = E − V + 1.

Mỗi chu trình cho 1 phương trình vector kín (2D: 2 phương trình vô hướng; 3D: 3). Hệ thức nhất quán với Grübler: F = Σfᵢ − 3·ℓ_loop (2D). (Kiểm với tay quay: Σfᵢ = 4, ℓ_loop = 1 ⇒ F = 1 ✓.)

**(c) Quy tắc đóng kín.** Ở mỗi "bậc vi phân":

| Bậc | Ẩn | Phương trình | Tính chất |
|---|---|---|---|
| Vị trí | q (mọi biến cấu hình cần cho Q) | f(q,t) = 0 | thường **phi tuyến** |
| Vận tốc | q̇ | J(q)·q̇ = −∂f/∂t | **tuyến tính** theo q̇, ma trận J = ∂f/∂q |
| Gia tốc | q̈ | J(q)·q̈ = −(J̇)q̇ − (đạo hàm riêng khác) | **tuyến tính** theo q̈, **cùng J** |

Hệ quả rất có lợi cho thi cử: **đã có cấu hình (vị trí) thì vận tốc và gia tốc chỉ còn là đại số tuyến tính với cùng một ma trận.** Chỗ duy nhất khó là bậc vị trí.

*Điều kiện Pre của bậc vận tốc/gia tốc:* J không suy biến. Khi det J = 0 (cấu hình kỳ dị: tay quay ở điểm chết, dây thẳng hàng), hệ vô nghiệm hoặc vô số nghiệm — phải xử lý riêng (thường bằng giới hạn hoặc đạo hàm cấp cao hơn). **Đừng để bước này lọt.**

**(d) Kiểm tra ẩn–phương trình.** Lập bảng: #ẩn (biến Q cần + biến phụ chưa khử) và #phương trình **độc lập**. Thừa ⇒ nhất quán? phụ thuộc? Thiếu ⇒ quay lại quét công cụ (mục 4.6).

### 1.7. Dom, Pre, Suf — phân biệt bằng ví dụ; và ba **mức trạng thái** của Pre

README của bạn nhấn mạnh Dom ≠ Pre. Ba ví dụ minh hoạ:

| Công cụ ℓ | Dom(ℓ) — miền nó *có nghĩa* | Pre(ℓ) — điều kiện nó *đúng* | Suf(ℓ) — dấu hiệu **đọc được bằng mắt** đủ bảo đảm Pre |
|---|---|---|---|
| Định lý cộng vận tốc v_B = v_A + ω×AB | mọi cặp điểm bất kỳ (có nghĩa hình thức) | A, B thuộc **cùng một vật rắn** tại thời điểm xét; ω là vận tốc góc của vật đó | đề nói "thanh", "đĩa", "khối" mà cả A và B nằm trên nó; hoặc |AB| cố định theo mọi cấu hình |
| SUVAT (s = v₀t + at²/2, …) | chuyển động dọc **một** trục | a **không đổi** trên khoảng thời gian dùng | đề cho "nhanh dần đều", hoặc gia tốc = g và chỉ chịu trọng lực; hoặc chia đoạn sao cho a hằng trong mỗi đoạn |
| ρ = v²/a_n | mọi quỹ đạo trơn có v ≠ 0 | v ≠ 0; a_n là thành phần **vuông góc** với v **trong cùng hệ** | có sẵn v, a của điểm đó tại thời điểm xét |

**Nguyên tắc thiết kế Suf trong tài liệu này:** Suf phải **kiểm được bằng cách đọc đề/nhìn hình mà không cần giải bài**. Đó là điều kiện để bước quét ở mục 4 là bước "máy móc". Còn Pre có thể cần kiểm thêm sau.

**Ba mức trạng thái của mỗi Pre khi bạn dùng nó (ghi bên cạnh mỗi phương trình):**
- **[Đ]** — đề cho hẳn ("dây không giãn", "lăn không trượt").
- **[S]** — suy ra ngay từ hình học/đối xứng.
- **[K]** — *giả định cần kiểm sau khi có nghiệm* (dây có căng suốt không? vật có chạm đất trước lúc gặp không? có tách khỏi mặt không?). Đây là nơi mô hình hay "vỡ" âm thầm. Nếu bạn ghi [K] mà không bao giờ quay lại kiểm thì bài của bạn có Q10 chưa trả lời.

---

## 2. THƯ VIỆN CÔNG CỤ CỦA ĐỘNG HỌC (L = K0 … K15)

**Mỗi công cụ = một "dạng".** Mỗi thẻ có cùng khuôn để bạn tra như tra bảng:

- **Phát biểu** — nội dung công cụ.
- **Kiểu CHỖ** — công cụ áp lên loại đối tượng nào của bài.
- **Dom / Pre / Suf / Post / Err** — như README của bạn (Suf = dấu hiệu quét được bằng mắt).
- **Trình tự cố định** — nếu không dùng trực giác, cứ chạy các bước này (câu hỏi bạn đặt ra trong README).
- **Trực giác còn lại** — phần *không* máy móc hoá được. Tôi ghi ra cho bạn thấy chính xác nó là gì.
- **Bẫy.**

Nguyên lý gốc chi phối cả thư viện — gọi là **Nguyên lý P\***: *mọi ràng buộc hình học holonomic f(q,t) = 0 đều được đạo hàm theo t để cho ràng buộc vận tốc/gia tốc.* K1, K2, K3, K8, K15 đều là các trường hợp của P\*.

---

### K0. Nền: hệ quy chiếu, vector vị trí, đạo hàm của vector quay

**Phát biểu.** v = dr/dt, a = dv/dt (trong một hệ đã chọn). Với vector đơn vị e **gắn với vật/khung đang quay** tốc độ góc ω: de/dt = ω × e. Ví dụ toạ độ cực: dr̂/dt = θ̇·θ̂, dθ̂/dt = −θ̇·r̂.

**Kiểu CHỖ.** Mọi điểm quan tâm; mọi vector đơn vị bị quay.

**Pre.** Hệ quy chiếu đã chỉ định; các vector dùng cùng một cơ sở khi cộng/trừ.

**Trình tự cố định.** (1) chọn hệ + gốc + chiều dương; (2) viết r của mọi điểm cần thiết dưới dạng hàm của biến cấu hình; (3) đạo hàm theo t đúng **quy tắc tích** khi có cơ sở quay (đừng quên dr̂/dt).

**Trực giác còn lại.** Chọn hệ nào cho gọn (xem 5.2 — tiêu chí chọn bằng bảng).

**Bẫy.** Quên đạo hàm của vector đơn vị quay. Nhầm "vận tốc trong hệ động" với "vận tốc trong hệ cố định".

---

### K1. Bảo toàn độ dài: dây, thanh cứng, khoảng cách cố định

**Phát biểu — hai dạng.**

*(1a) Hai điểm cách nhau cố định (thanh cứng, hai điểm cùng vật rắn):*

- Vận tốc: (r_A − r_B)·(v_A − v_B) = 0 ⇔ v_A·û = v_B·û (û = vector đơn vị AB). Đây là **định lý chiếu vận tốc**.
- Gia tốc (đạo hàm tiếp): (a_A − a_B)·û = −|v_A − v_B|²/|AB|. **Lưu ý:** hai hạng tử — *không* phải a_A·û = a_B·û.

*(1b) Dây không giãn, căng, nhiều đoạn thẳng + cung:*

L_dây = Σ (đoạn thẳng) + Σ Rⱼφⱼ (cung ôm) = hằng.

**Quy tắc đạo hàm chiều dài dây (Bổ đề biến phân đầu mút)** — công cụ cốt lõi, đã kiểm (A13). Với dây căng ôm quanh các ròng rọc tròn bán kính không đổi:

  dL/dt = Σ_{đầu mút cuối Q} û_đến·v_Q − Σ_{đầu mút đầu P} û_đi·v_P + Σ_{ròng rọc C} (û_vào − û_ra)·V_C = 0

trong đó û là vector đơn vị **theo chiều đi dọc dây**: û_đến = hướng dây đi vào đầu mút cuối; û_đi = hướng dây rời đầu mút đầu; û_vào/û_ra = hướng dây đi vào/ra khỏi ròng rọc (dây trượt hay không trượt trên ròng rọc **không** ảnh hưởng tới tổng chiều dài); V_C = vận tốc **tâm** ròng rọc. Ròng rọc/vật cản cố định ⇒ số hạng của nó bằng 0 — kể cả vật cản có hình dạng bất kỳ (miễn dây căng và là đường ngắn nhất).

*Vì sao đúng:* dây căng là đường trắc địa ⇒ biến phân bậc nhất của độ dài chỉ còn các số hạng ở đầu mút và ở các điểm tựa di động. Số hạng tại một ròng rọc di động: ∂L/∂C = û_vào − û_ra. Kiểm bằng ví dụ ròng rọc động cổ điển: hai nhánh dây thẳng đứng đi xuống rồi đi lên quanh ròng rọc, ròng rọc đi xuống δ ⇒ độ dài tăng 2δ; công thức cho (û_vào − û_ra)·V_C = (−ŷ − ŷ)·(−δŷ) = 2δ ✓.

**Kiểu CHỖ.** (1a) cặp điểm; (1b) sợi dây (chuỗi đoạn thẳng–cung), cùng các điểm tựa di động.

**Dom.** Mọi hệ có liên kết chiều dài.

**Pre.**
- (1a): khoảng cách thật sự cố định **suốt quá trình** (thanh cứng). *Dây thì không*: khoảng cách chỉ ≤ L. [Đ]
- (1b): dây không giãn [Đ]; **dây căng** trong khoảng thời gian xét [K]; ròng rọc tròn, bán kính không đổi [Đ]; dây không bị quấn thêm/tháo ra ở đầu mút — nếu có, tính cả phần quấn vào L.

**Suf (quét được bằng mắt).**
- Có "thanh" nối hai điểm; hoặc hai điểm trên cùng vật rắn.
- Có "sợi dây" nối ≥ 2 điểm; có ròng rọc; có dây vắt qua góc/cung/trụ.
- Có cụm "không giãn", "nối", "buộc vào".

**Post.** (1a) 1 phương trình vận tốc (+1 phương trình gia tốc). (1b) 1 phương trình cho mỗi sợi dây.

**Err.** Dây giãn (Hooke) hoặc thanh mềm: chỉ là xấp xỉ khi hệ số giãn nhỏ; phải nêu tham số nhỏ.

**Trình tự cố định (dây):**
1. Vẽ mỗi sợi dây thành chuỗi: điểm đầu → (đoạn thẳng, cung, tiếp điểm…) → điểm cuối.
2. Đánh dấu chiều đi dọc dây; viết û cho mỗi đoạn.
3. Liệt kê **tất cả** điểm mà dây ôm/vắt: điểm cố định (bỏ), ròng rọc di động (giữ V_C), đầu mút.
4. Viết dL/dt = 0 theo công thức trên → 1 phương trình.
5. Đưa v của từng điểm về biến cấu hình q̇ (bước sang P3, mục 5).
6. Ghi [K]: dây căng? (chỉ kiểm được khi có lực; ở Động học chỉ ghi lại).

**Trực giác còn lại.** Xác định đúng các điểm tựa và đâu là ròng rọc *di động*; đọc hình cho đúng dây đi từ đâu tới đâu.

**Bẫy.**
- Ràng buộc dây **một chiều**: chùng ⇒ ràng buộc biến mất.
- Với thanh: a_A·û = a_B·û là **sai**; phải có −v_rel²/|AB|.
- Dây quấn/tháo khỏi trụ: L = ℓ_tự do + Rφ_đã quấn (xem Ví dụ 1).
- Ròng rọc động *quay*: chỉ V_C (tâm) vào công thức tổng chiều dài, không phải ω của ròng rọc.

---

### K2. Tiếp xúc, không xuyên, không trượt, lăn

**Phát biểu.**
- **Không xuyên (bilateral khi còn tiếp xúc):** thành phần **pháp tuyến** của vận tốc của hai *điểm vật chất trùng nhau tại tiếp điểm* bằng nhau: v_A·n = v_B·n.
- **Không trượt:** hai điểm vật chất trùng nhau có **cùng vector vận tốc**: v_A = v_B.
- **Lăn không trượt trên nền cố định:** vận tốc điểm vật chất của vật ở tiếp điểm = 0 ⇒ tiếp điểm là tâm quay tức thời (K3).
- **Đĩa bán kính r lăn không trượt trên đường thẳng:** v_O = ωr, a_O = αr (dạng khả tích: x_O = rθ). **Gia tốc của điểm vật chất tại tiếp điểm khác 0**: a_P = ω²r hướng về tâm (không phụ thuộc a_O).
- **Lăn trên đường tròn cố định bán kính R:** lăn ngoài (đĩa bán kính r ở ngoài): v_O = (R + r)Ω (Ω = vận tốc góc của tâm O quanh tâm cố định), |ω_đĩa| = (R + r)Ω/r **cùng chiều** Ω; lăn trong (đĩa nằm trong vòng R): |ω_đĩa| = (R − r)Ω/r **ngược chiều** Ω.

**Kiểu CHỖ.** Tiếp điểm của cặp vật; mọi chỗ "chạm", "tựa", "lăn", "đặt lên".

**Pre.**
- Không xuyên: các vật còn tiếp xúc [K] (tách ra ⇒ mất ràng buộc).
- Không trượt: [Đ] (đề nói) — hoặc [K] nếu ma sát đủ lớn (thuộc Động lực học).

**Suf.**
- Cụm từ "lăn không trượt", "không trượt", "dính", "tựa vào", "chạm".
- Hai vật có bề mặt chung.

**Post.** Không xuyên: 1 phương trình (pháp tuyến). Không trượt: 2 phương trình vô hướng (2D) — nhưng **bậc tự do trừ 2**, khớp thuộc loại j₁ trong Grübler.

**Err.** Nền biến dạng; lăn có trượt nhỏ.

**Trình tự cố định.**
1. Nhận diện mọi tiếp điểm (mỗi cặp vật kề nhau trên đồ thị topology).
2. Tại mỗi tiếp điểm, xác định **hai điểm vật chất** trùng nhau tại thời điểm xét (một của mỗi vật).
3. Viết v_A và v_B bằng công thức vật rắn (K3) cho từng vật.
4. Viết v_A·n = v_B·n (luôn); và v_A = v_B nếu "không trượt".
5. Đếm: mỗi không trượt cho thêm 2 phương trình (2D).

**Trực giác còn lại.** Chọn *hai điểm vật chất nào* (không có gì khó, nhưng người ta hay quên rằng điểm tiếp xúc di chuyển trên vật).

**Bẫy.**
- **Tiếp điểm hình học ≠ điểm vật chất.** Điểm vật chất của bánh ở tiếp điểm có v = 0 nhưng a ≠ 0; còn *tiếp điểm hình học* chạy trên nền với vận tốc = v_O.
- "Lăn không trượt" của **cầu/đĩa trên mặt phẳng 2D** là phi holonomic: không thể viết thành "vị trí = hàm của góc" toàn cục (xem K12).
- Với đĩa lăn trên đường **cong**: hệ thức v_O = ωr sai; dùng công thức (R ± r)Ω ở trên.

---

### K3. Vật rắn phẳng: phân bố vận tốc/gia tốc, tâm quay tức thời, Kennedy

**Phát biểu.** Với A, B **cùng vật rắn**, ω = ω·ẑ, α = dω/dt:

- v_B = v_A + ω × AB, độ lớn |v_B − v_A| = |ω|·|AB|, vuông góc AB.
- a_B = a_A + α × AB − ω²·AB.
- **Tâm quay tức thời (ICR) P:** điểm (trên mặt phẳng của vật, có thể ngoài vật) với v_P = 0 khi ω ≠ 0: P = A + (ẑ × v_A)/ω. Hình học: P nằm trên **đường vuông góc với v_A đi qua A**, cách A đoạn |v_A|/|ω|. Nếu biết hướng v của hai điểm ⇒ P là giao của hai đường vuông góc đó.
- Tốc độ điểm M bất kỳ: |v_M| = |ω|·|PM|, hướng vuông góc PM.
- **Tâm gia tốc tức thời J** (khi (α, ω) ≠ 0): a_J = 0 và |a_B| = |JB|·√(α² + ω⁴) (đã kiểm A18). **ICR ≠ tâm gia tốc**: gia tốc điểm P (ICR) nói chung ≠ 0.
- **Định lý Kennedy–Aronhold:** ba vật bất kỳ chuyển động phẳng tương đối thì ba tâm quay tương đối I₁₂, I₂₃, I₁₃ **thẳng hàng**. n vật (kể cả giá) có n(n−1)/2 tâm quay tương đối.
- **Centrode (quỹ tích tâm quay):** chuyển động phẳng bất kỳ của vật = **centrode động** (quỹ tích P trong vật) **lăn không trượt** trên **centrode tĩnh** (quỹ tích P trên nền). Ví dụ thang trượt hai đầu trên trục: centrode tĩnh là đường tròn tâm O bán kính L; centrode động là đường tròn đường kính L (đường kính = thang) lăn trong.

**Kiểu CHỖ.** Cặp điểm cùng vật rắn; điểm có hướng vận tốc biết trước (con trượt trên rãnh, đầu thanh tựa tường); tiếp điểm lăn; ba vật kề nhau.

**Dom.** Vật rắn phẳng; mọi thời điểm.

**Pre.**
- A, B thuộc **cùng** vật rắn **cùng lúc** [S].
- ICR: chỉ hợp lệ cho **vận tốc tức thời**. **Không** dùng ICR để tính gia tốc bằng a = ω²·PM [Đ/S].
- ω ≠ 0. Nếu ω = 0 thì vật đang **tịnh tiến tức thời**: mọi điểm cùng vận tốc.

**Suf.**
- Có "thanh", "đĩa", "khối", "bánh xe" chuyển động phẳng.
- Có hai điểm mà hướng vận tốc biết (con trượt trên rãnh thẳng/cong, đầu thanh trên sàn/tường, đầu dây vòng qua ròng rọc, điểm lăn không trượt).
- Có ba vật liên tiếp (dùng Kennedy).

**Post.** Mỗi điểm với **hướng v biết** cho 1 phương trình (v ∥ rãnh: v × ê_rãnh = 0). Mỗi cặp điểm cùng vật cho quan hệ vector (2 phương trình vô hướng, thêm 1 ẩn ω).

**Err.** Vật gần rắn (biến dạng nhỏ).

**Trình tự cố định — vận tốc:**
1. Chọn A có v_A biết (độ lớn hoặc chỉ hướng).
2. Với mỗi điểm M cần quan tâm: viết v_M = v_A + ω × AM.
3. Với mỗi điểm có hướng biết: viết v_M × ê = 0 (1 phương trình).
4. Tại mỗi tiếp điểm/khớp: thêm quan hệ từ K1/K2.
5. Đếm ẩn (ω và các độ lớn chưa biết) = phương trình → hệ tuyến tính. *(Cách khác: dựng ICR bằng hai đường vuông góc.)*

**Trình tự cố định — gia tốc:** như trên nhưng dùng a_B = a_A + α × AB − ω²AB; ω đã có từ bước vận tốc; ẩn: α và các gia tốc chưa biết; điều kiện hướng gia tốc biết (con trượt: a ∥ rãnh) cho phương trình; **với rãnh cong: gia tốc của điểm trượt có thêm thành phần pháp tuyến v²/ρ_rãnh** (K7).

**Trực giác còn lại.** Chọn điểm tham chiếu A gọn nhất; thấy được ICR bằng hình.

**Bẫy.** Dùng ICR cho gia tốc. Dùng công thức vật rắn cho hai điểm thuộc **hai vật khác nhau**. Quên rằng hướng v của điểm trượt trên rãnh cong thay đổi ⇒ gia tốc pháp tuyến. Nhầm dấu ω × AB (kiểm bằng giới hạn: A cố định ⇒ v_B ⟂ AB).

---

### K4. Chuyển động tương đối và đổi hệ quy chiếu (kể cả hệ quay, hệ rơi tự do, không gian vận tốc)

**Phát biểu.**

- **Galileo (hệ tịnh tiến, không quay):** v = v' + V, a = a' + A.
- **Hệ quay + gia tốc (đã kiểm A11 cho 2D):**
  - v = v_O' + ω × r' + v_rel
  - a = a_O' + α × r' + ω × (ω × r') + 2ω × v_rel + a_rel
  (r' = vị trí trong hệ động, v_rel, a_rel đo **trong hệ động**).
- **Hệ rơi tự do:** nếu mọi vật quan tâm chỉ chịu gia tốc g (đều nhau) thì trong hệ chuyển động với gia tốc g, mọi vật ấy **chuyển động thẳng đều**. Hệ quả: hai đạn ném cùng lúc **va chạm** ⇔ vector vị trí tương đối r₀ **cùng phương ngược chiều** với vận tốc tương đối v_rel (2D: r₀ × v_rel = 0 và r₀·v_rel < 0), thời điểm t = |r₀|/|v_rel|. **Pre [K]: cả hai chưa chạm đất trước t.**
- **Khoảng cách nhỏ nhất** giữa hai chất điểm chuyển động đều: đặt A đứng yên, B chuyển động thẳng đều với v_rel: d_min = |r₀ × v_rel|/|v_rel|, tại t* = −r₀·v_rel/|v_rel|² (nếu t* < 0 thì cực tiểu trên t ≥ 0 nằm ở t = 0) — đã kiểm A9.
- **Không gian vận tốc:** khi một vật có tốc độ **tương đối** cố định u nhưng hướng tự do, tập các vận tốc khả dĩ đối với hệ khác là **đường tròn tâm V, bán kính u** (V = vận tốc hệ). Các bài "ca nô qua sông", "đuổi kịp/đón đầu", "bay ngược gió" thành bài hình học của đường tròn và tiếp tuyến. Ví dụ ca nô: nếu u < v (nước chảy nhanh hơn) độ trôi nhỏ nhất d√(v²−u²)/u đạt khi vận tốc đối đất tiếp xúc đường tròn (đã kiểm A16).

**Kiểu CHỖ.** Cặp (đối tượng quan tâm, hệ quy chiếu). **Quét mọi cặp**: mỗi vật đều có thể là hệ.

**Pre.**
- Cộng vận tốc/gia tốc kiểu Galileo: v ≪ c [Đ]; hệ không quay (nếu quay: thêm số hạng ω).
- Hệ rơi tự do: **cùng một g** đối với tất cả vật xét (Err: g phụ thuộc độ cao) và chỉ chịu trọng lực.
- Phép cộng vận tốc/gia tốc **về hình học/động học** không đòi hệ quán tính — chỉ định luật Newton mới đòi.

**Suf.**
- Có một vật đứng yên/đơn giản trong một hệ nào đó ("người ngồi trên xe", "bọ trên đĩa").
- Có hai vật chịu cùng một gia tốc (g).
- Có "gió", "dòng nước", "băng chuyền" (hệ nền chuyển động).
- Câu hỏi hỏi quan hệ **giữa hai vật**.

**Post.** Bài toán trong hệ mới thường **ít ràng buộc hơn / đơn giản hơn**.

**Err.** Tương đối tính khi v ~ 0,1c trở lên.

**Trình tự cố định.**
1. Liệt kê các hệ ứng viên: đất; mỗi vật; hệ rơi tự do; hệ quay theo đường nối/đĩa.
2. Với mỗi hệ, đếm: (số ràng buộc còn lại) + (độ đơn giản của Q). Chọn hệ có tổng nhỏ nhất (tiêu chí ở 5.2).
3. Viết công thức chuyển hệ cho v (và a) đầy đủ số hạng.
4. Giải trong hệ mới; đổi ngược nếu cần.

**Trực giác còn lại.** Sự "nhìn ra" hệ tốt nhất; tôi chỉ cho tiêu chí đếm ở 5.2 chứ không thay được trực giác hoàn toàn.

**Bẫy.** Quên hạng tử Coriolis 2ω × v_rel; dùng a = a' + A trong hệ quay; dùng hệ rơi tự do khi có lực khác (lực đẩy, lực nâng); dùng d_min ở t* < 0 mà chưa kiểm t ≥ 0.

---

### K5. Gia tốc không đổi, tích phân 1D và đồ thị

**Phát biểu.**
- Gia tốc vector hằng (Pre): mỗi **thành phần theo mỗi trục độc lập**:
  v = v₀ + at, s = v₀t + at²/2, v² − v₀² = 2as, v_tb = (v₀ + v)/2 (**chỉ khi a hằng**).
- Tổng quát 1D: a = dv/dt = v·dv/dx ⇒ nếu a = a(x): ∫v dv = ∫a dx; nếu a = a(t): tích phân theo t.
- **Đồ thị:** Δs = diện tích dưới v–t (có dấu); a = độ dốc v–t; đường thẳng cắt nhau trên s–t ⇒ gặp nhau.
- **Quãng đường vs độ dời:** quãng đường = ∫|v|dt: **chia tại v = 0** (điểm đổi chiều).
- **Vận tốc trung bình** = Δs/Δt (không phải trung bình cộng vận tốc, trừ khi a hằng); nửa quãng đầu đi v₁, nửa sau v₂ ⇒ v_tb = 2v₁v₂/(v₁ + v₂) (trung bình điều hoà).

**Kiểu CHỖ.** Khoảng thời gian; mỗi trục toạ độ; mỗi giai đoạn.

**Pre.** a không đổi **trong khoảng dùng** [Đ/S]; chuyển động dọc một trục (hoặc tách được theo trục) [S].

**Suf.**
- Cụm "đều", "nhanh dần đều", "chậm dần đều", "rơi tự do", "ném".
- Gia tốc cho trước là hằng hoặc hằng từng đoạn.
- Cho đồ thị v–t/a–t.

**Post.** Quan hệ s, v, t (2–3 phương trình độc lập cho mỗi đoạn).

**Err.** g thay đổi theo độ cao; lực cản không đáng kể.

**Trình tự cố định.**
1. Chọn trục và chiều dương (chốt dấu ngay).
2. **Chia đoạn** tại mọi sự kiện đổi gia tốc/va chạm/chạm đất/đổi chiều.
3. Mỗi đoạn: viết s(t), v(t) với **điều kiện nối** (s, v liên tục; a nói chung không).
4. Ghép với Q (điều kiện gặp, thời gian, quãng đường…).
5. Gặp nhau 1D: s_A(t) = s_B(t) là bậc hai ⇒ số nghiệm = số lần gặp (discriminant); kiểm t ≥ 0 và cùng thuộc miền đoạn tương ứng.

**Trực giác còn lại.** Chọn cách chia đoạn (thường hiển nhiên).

**Bẫy.** Áp SUVAT qua điểm đổi gia tốc. v_tb = (v₁+v₂)/2 khi a không hằng. Quãng đường tính bằng độ dời khi vật quay đầu.

---

### K6. Ném xiên, đường bao, tối ưu theo tham số

**Phát biểu.** Với g hằng, vận tốc đầu v₀, góc α (u = tanα):
- x = v₀cosα·t, y = v₀sinα·t − gt²/2
- y = u·x − g x²(1+u²)/(2v₀²)   (quỹ đạo)

*Điểm (X, Y) có với tới được không?* Đưa về bậc hai theo u:

  (gX²/2v₀²)·u² − X·u + (Y + gX²/2v₀²) = 0.

Với tới được ⇔ discriminant ≥ 0 ⇔ Y ≤ v₀²/(2g) − gX²/(2v₀²). Biên = **parabol an toàn** (A4).

*Cách hình học (vòng tròn giãn nở, A20):* trong hệ rơi tự do, tại thời điểm t mọi đạn ném cùng tốc độ v₀ từ cùng một điểm nằm trên đường tròn bán kính v₀t tâm (0, −gt²/2). Bao của họ đường tròn này (khi t thay đổi) là parabol an toàn.

*Tầm xa trên mặt nghiêng góc α so với ngang* (đã kiểm A4):
- lên dốc: R_max = v₀²/(g(1 + sinα)); xuống dốc: R_max = v₀²/(g(1 − sinα)).
- Góc ném tối ưu (đối với ngang) = 45° ± α/2 (phân giác góc giữa mặt nghiêng và phương thẳng đứng).
- Công thức có thông số β (góc ném so với mặt nghiêng, lên dốc): R = v₀²[sin(2β + α) − sinα]/(g cos²α).

*Ném từ độ cao h:* tanα_opt = v₀/√(v₀² + 2gh), R_max = (v₀/g)√(v₀² + 2gh) (A15).

**Kiểu CHỖ.** Đạn/vật chỉ chịu g; điểm đích trên mặt/đường bất kỳ y = f(x).

**Pre.** g hằng (độ cao ≪ R_Trái Đất) [Đ]; chỉ chịu trọng lực (bỏ cản) [Đ]; cùng g cho mọi đạn.

**Suf.** "Ném", "bắn", "đạn", "vòi nước", "hạt bắn ra theo mọi hướng với cùng tốc độ" (⇒ đường bao); "vật rời tiếp xúc rồi bay tự do".

**Post.** Phương trình quỹ đạo; điều kiện tới đích (giao với đường y = f(x)); đường bao F = 0, ∂F/∂u = 0.

**Err.** Lực cản; g phụ thuộc độ cao; quay Trái Đất.

**Trình tự cố định — "vật chạm bề mặt y = f(x)":**
1. Chọn hệ (ngang–đứng, hoặc dọc–vuông mặt nghiêng: a = (−g sinα, −g cosα)).
2. Viết r(t) với điều kiện đầu.
3. Thế r(t) vào phương trình bề mặt ⇒ phương trình theo t (thường bậc hai) ⇒ t_chạm (nghiệm dương lớn nhất/đúng).
4. Cực trị theo góc: (a) đạo hàm; (b) discriminant theo u; (c) đường bao.

**Trực giác còn lại.** Chọn biến (t? u = tanα? góc?) để phương trình gọn; tôi khuyến nghị: nếu mục tiêu là *tập các điểm với tới được* ⇒ đường bao/discriminant; nếu là *thời gian* ⇒ t.

**Bẫy.** Chỉ lấy một nghiệm của bậc hai (bỏ mất quỹ đạo cao/thấp). Ném nhiều đạn "cùng lúc" quên rằng chúng va nhau chỉ khi Pre [K] (chưa chạm đất). Nhầm "tầm xa ngang" với "tầm xa trên mặt nghiêng".

---

### K7. Toạ độ cong và động học quỹ đạo: cực, trụ, cầu, tự nhiên; bán kính cong

**Phát biểu.**
- **Cực:** v = ṙ r̂ + rθ̇ θ̂; a = (r̈ − rθ̇²) r̂ + (rθ̈ + 2ṙθ̇) θ̂.
- **Trụ:** thêm z: v_z = ż, a_z = z̈; (ρ, φ) như cực.
- **Cầu:** v = ṙ r̂ + rθ̇ θ̂ + r sinθ φ̇ φ̂; a_r = r̈ − rθ̇² − r sin²θ φ̇²; a_θ = rθ̈ + 2ṙθ̇ − r sinθ cosθ φ̇²; a_φ = r sinθ φ̈ + 2ṙ sinθ φ̇ + 2r cosθ θ̇φ̇ (đã kiểm A7).
- **Tự nhiên:** v = v·τ̂; a = v̇ τ̂ + (v²/ρ)·n̂; a_t = a·v/|v|; a_n = |v × a|/|v|; ρ = v³/|v × a| = (1 + y′²)^{3/2}/|y″| (quỹ đạo dạng y(x)).
- **Ứng dụng:**
  - ném xiên: tại đỉnh a_n = g, v = v₀cosα ⇒ ρ_đỉnh = v₀²cos²α/g; tại điểm ném a_n = g cosα ⇒ ρ = v₀²/(g cosα).
  - Cycloid: ρ = 4R sin(θ/2) (A2); ở đỉnh ρ = 4R.
  - Đường thân khai (dây tháo khỏi trụ): ρ = ℓ (ℓ = đoạn dây thẳng), v = ℓφ̇ (A8).

**Kiểu CHỖ.** Điểm trên quỹ đạo; điểm chuyển động quanh một "tâm"; câu hỏi về ρ/a_n.

**Pre.** v ≠ 0 để có ρ và τ̂ (tại v = 0 dùng giới hạn); a_n và ρ **phụ thuộc hệ quy chiếu** — dùng đúng v, a **trong cùng một hệ**; vận tốc/gia tốc thu được từ công cụ khác.

**Suf.**
- Quỹ đạo tròn/xoắn ốc, "quay quanh", "hướng về điểm O", "vuông góc với bán kính".
- Đề hỏi bán kính cong/gia tốc pháp tuyến/gia tốc hướng tâm.
- Ràng buộc dạng hướng tương đối với đường nối.

**Post.** Thành phần vận tốc/gia tốc theo từng hướng; ρ.

**Err.** Không có (định nghĩa hình học), trừ khi dùng gần đúng cho bán kính cong lớn.

**Trình tự cố định (tính ρ tại một điểm).**
1. Tính v (vector) tại điểm: bằng công cụ khác (K3/K4/K6…).
2. Tính a (vector) tại điểm — trong **cùng hệ**.
3. a_n = |v × a|/|v|; ρ = v²/a_n.
4. Cách thay thế: nếu biết y(x) thì ρ = (1 + y′²)^{3/2}/|y″|.

**Trực giác còn lại.** Chọn hệ toạ độ cong nào (thường: cực nếu có điểm "tâm").

**Bẫy.** ρ trong hệ này khác hệ khác; quên rằng hệ của bánh xe cho ρ=... khác đất. Dùng a_n = v²/R_vòng cho quỹ đạo **không** tròn: phải dùng ρ.

---

### K8. Điểm phi vật chất và giao điểm: vận tốc "hình học"

**Phát biểu — Bổ đề vận tốc pháp** (đã kiểm A5 cho đường thẳng). Cho các đường (hoặc mặt) C_i(t) chuyển động/biến dạng, và điểm P(t) **luôn nằm trên tất cả** các đường đó. Khi đó **thành phần vận tốc của P theo pháp tuyến nᵢ của Cᵢ bằng tốc độ pháp tuyến wᵢ của Cᵢ tại P**:

  u · nᵢ = wᵢ   với i = 1, 2, …

trong đó u = vận tốc của P; wᵢ = nᵢ · (vận tốc của **điểm vật chất** của vật mang đường i đang trùng P) — nếu đường Cᵢ là đường **gắn với vật rắn**. Hai đường **không song song tại P** ⇒ u = N⁻¹·w, N = ma trận có hàng là nᵢᵀ.

Trường hợp đường thẳng quay quanh điểm O nằm trên nó với tốc độ góc ω: tốc độ pháp tuyến tại điểm cách O đoạn ρ là w = ωρ.

*Ví dụ kiểm nhanh:* vệt sáng laser quay đều ω quét lên tường thẳng đứng cách O đoạn d, tia lệch góc θ so với pháp tuyến tường: u_y = ωd/cos²θ (đối chiếu với đạo hàm x = d·tanθ) — và **có thể lớn hơn c** vì đó không phải chuyển động của vật chất.

**Kiểu CHỖ.** Giao điểm của hai thanh/đường/tia; bóng và vệt sáng; tiếp điểm hình học; điểm bẻ của dây; tâm quay tức thời.

**Pre.** P nằm trên cả hai đường trong suốt quá trình [S]; các đường trơn tại P; hai pháp tuyến không song song (nếu song song/tiếp xúc: hệ suy biến); *bổ đề chỉ xác định thành phần pháp tuyến* — thành phần **tiếp tuyến** của P dọc mỗi đường **không** được xác định bởi riêng đường đó.

**Suf.**
- Đề nói "giao điểm", "chỗ hai thanh cắt nhau", "bóng", "vệt sáng", "điểm chạm chạy trên…".
- Điểm mà đề hỏi vận tốc **không phải** một vật thật.

**Post.** Hệ tuyến tính 2×2 cho u.

**Err.** Không (chính xác) — nhưng nhớ: u có thể vượt c; tương đối tính chỉ hạn chế vận tốc tín hiệu/vật chất.

**Trình tự cố định.**
1. Liệt kê các đường đi qua P.
2. Tại P, viết nᵢ (pháp tuyến đơn vị của đường i).
3. Xác định wᵢ: đường tịnh tiến ⇒ w = n·V; đường quay quanh O ⇒ w = ωρ (chú ý dấu theo n); đường gắn vật rắn ⇒ w = n·v(điểm vật chất trùng P).
4. Giải n₁·u = w₁, n₂·u = w₂.
5. Nếu có thêm thông tin về hướng u (P bị buộc trượt trên đường thứ ba cố định) thì đưa vào.

**Cách thay thế (song song để kiểm):** tham số hoá P = P(q) bằng biến cấu hình, đạo hàm.

**Trực giác còn lại.** Nhận ra rằng điểm cần tìm là *phi vật chất* (đây chính là "CHỖ" mà nhiều thí sinh không thấy: họ cố tìm một vật chất để áp v_B = v_A + ω×AB).

**Bẫy.** Dùng công thức vật rắn cho giao điểm; cộng vận tốc kiểu Galileo cho điểm hình học; quên rằng đường trượt dọc chính nó (tiếp tuyến) không ảnh hưởng đến phương trình (chỉ pháp tuyến).

---

### K9. Đuổi bắt và đối xứng

**Phát biểu.**
- **Ràng buộc đuổi bắt:** v_A luôn hướng tới B: v_A = v_A·(r_B − r_A)/|r_B − r_A|. Đặt r = r_B − r_A, û = r/|r|:
  d|r|/dt = û·(v_B − v_A) — chỉ cần chiếu vận tốc lên đường nối.
- **Mục tiêu chuyển động thẳng đều (v_B hằng), A có tốc độ v_A hằng, luôn hướng B** (A14): gọi ξ = thành phần của r dọc phương v_B, β = góc giữa r và v_B:
  ṙ = −v_A + v_B cosβ, ξ̇ = v_B − v_A cosβ ⇒ v_A·ṙ + v_B·ξ̇ = v_B² − v_A² (hằng).
  Suy ra v_A r + v_B ξ = (v_B² − v_A²)t + const; nếu v_A > v_B, thời gian bắt kịp T = (v_A r₀ + v_B ξ₀)/(v_A² − v_B²).
- **n vật ở đỉnh n-giác đều cạnh a, mỗi vật hướng về vật kế, cùng tốc độ v** (A1):
  - Đối xứng C_n được bảo toàn (xem Pre).
  - Theo phương hướng tâm: ṙ = −v·sin(π/n); theo phương tiếp tuyến: rθ̇ = v·cos(π/n).
  - Bán kính ban đầu r₀ = a/(2 sin(π/n)) ⇒ **T = a/(2v sin²(π/n))** (n = 3: 2a/3v; n = 4: a/v).
  - Quỹ đạo là **xoắn ốc logarit** r = r₀e^{−(θ−θ₀)tan(π/n)}; quãng đường mỗi vật = vT.
- **Tổng quát hoá:** nếu ràng buộc là "vận tốc luôn hợp với đường nối một góc không đổi" thì ṙ/(rθ̇) = hằng ⇒ xoắn ốc logarit.

**Kiểu CHỖ.** Cặp (đuổi, bị đuổi); đa giác chu trình; ràng buộc "luôn hướng".

**Pre.** Đuổi bắt: hướng v_A cập nhật tức thời [Đ]. Bất biến hai vế (v_A, v_B hằng) [Đ]. Đối xứng n-giác: **cấu hình đầu có nhóm đối xứng C_n** *và* **các vật giống hệt nhau về luật chuyển động** [S] — khi đó, do nghiệm ODE duy nhất, cấu hình mọi lúc còn giữ đối xứng C_n.

**Suf.**
- Cụm "luôn hướng về", "đuổi theo", "mỗi con chạy về con kế", "luôn nhằm vào".
- Cấu hình ban đầu là đa giác đều, các tốc độ đều nhau.

**Post.** Hệ ODE giản lược; quan hệ bảo toàn.

**Err.** Trễ phản ứng, độ cong quỹ đạo (không có trong mô hình lý tưởng).

**Trình tự cố định.**
1. Xác định cặp đuổi–bị đuổi.
2. Viết ràng buộc vận tốc "hướng". Chọn hệ toạ độ hoặc quay theo đường nối (hệ quay: đường nối = trục).
3. Chiếu vận tốc lên đường nối và vuông góc: ra ṙ và rθ̇.
4. Nếu có đối xứng (Pre): thay hệ nhiều vật bằng **một** phương trình.
5. Tìm đại lượng bảo toàn (tổ hợp tuyến tính ṙ, ξ̇ dùng v_A, v_B như trên).

**Trực giác còn lại.** Nhận ra tổ hợp bảo toàn; hoặc nhận ra đối xứng. (Tổ hợp bảo toàn cho mục tiêu thẳng đều có thể *tìm được có hệ thống* bằng cách giải v_A·ṙ + λ ξ̇ = hằng tìm λ.)

**Bẫy.** Đối xứng "hiển nhiên" nhưng thiếu Pre (các tốc độ khác nhau ⇒ mất đối xứng). Cho rằng "gặp nhau" ⇔ cả đa giác co về **tâm** (đúng chỉ với tốc độ bằng nhau). Nhầm quãng đường với độ dời.

---

### K10. Cực trị động học và tối ưu

**Phát biểu.**
- **Khoảng cách nhỏ nhất:** như K4.
- **Thời gian nhỏ nhất qua hai môi trường** (tốc độ v₁ ở môi trường 1, v₂ ở môi trường 2, ranh giới thẳng): sinθ₁/v₁ = sinθ₂/v₂ (Snell), θ là góc so với pháp tuyến ranh giới (A10). Tổng quát: **không phải trực giác — đạo hàm hàm thời gian theo vị trí điểm qua biên bằng 0**.
- **Cực trị theo tham số kèm điều kiện tồn tại:** dạng "có nghiệm ⇔ discriminant ≥ 0" (K6).
- **Cực trị bằng bất đẳng thức:** AM–GM, Cauchy–Schwarz (khi hàm mục tiêu có dạng tổng nghịch đảo/tích).
- **Cực trị với ràng buộc** (nhiều biến): khử biến bằng ràng buộc (P\*), hoặc nhân tử Lagrange.

**Kiểu CHỖ.** Biến tự do (điểm qua biên, góc ném, thời điểm); hàm mục tiêu (thời gian, khoảng cách, độ cao, tầm xa).

**Pre (rất quan trọng, hay lọt).**
- Cực trị **nội tại** phải nằm **trong miền cho phép** [K] — nếu cực trị rơi ra ngoài đoạn, đáp án ở **biên**. Với Snell: khi v₂ > v₁ có **góc tới hạn**, đường đi tối ưu có thể "bám dọc ranh giới".
- Hàm mục tiêu khả vi trên miền xét.
- Nghiệm f′ = 0 phải được xác nhận là cực **tiểu** (hay cực đại) đúng loại [K].

**Suf.**
- "Ngắn nhất", "nhanh nhất", "lớn nhất", "nhỏ nhất", "tối ưu", "tránh xa nhất".
- "Điều kiện để vật với tới được", "khoảng cách gần nhất".

**Post.** Phương trình f′ = 0 (hoặc D = 0) kèm điều kiện miền.

**Trình tự cố định.**
1. Chọn **một** biến tự do (nếu nhiều: khử bằng ràng buộc).
2. Viết hàm mục tiêu f(x) (đơn vị đúng).
3. Xác định miền [a, b] của x (thực tế).
4. Tìm f′ = 0 **và** kiểm hai biên.
5. Xác nhận loại cực trị.
6. Kiểm giới hạn: khi tham số → biên, đáp án có tiến về kết quả đã biết?

**Trực giác còn lại.** Chọn biến tự do khiến f đơn giản; đoán miền.

**Bẫy.** Quên biên; đạo hàm không tính hạng tử cách đều; cực trị theo góc nhưng không kiểm góc trong (0, π/2); dùng Snell khi môi trường không cho tốc độ hằng.

---

### K11. Phasor: chuyển động tròn đều ⇄ dao động điều hoà (giao diện với phần Dao động)

**Phát biểu.** x = A cos(ωt + φ) là hình chiếu của chuyển động tròn đều bán kính A; v = −Aω sin(ωt + φ) = ±ω√(A² − x²); a = −ω²x. Thời gian giữa hai vị trí = (góc quét giữa hai điểm trên đường tròn)/ω.

**Kiểu CHỖ.** Dao động điều hoà; mọi x(t) sinh ra bởi hình chiếu; tổng hợp hai dao động cùng tần số (vector quay cộng vector); Lissajous.

**Pre.** Dao động điều hoà (thoả a = −ω²x) [Đ/S].

**Suf.** x(t) dạng sin/cos; đề cho ω, hoặc phương trình a = −ω²x.

**Post.** Mọi câu hỏi về thời gian giữa hai trạng thái ⇒ bài hình học về góc.

**Trình tự cố định.** (1) đặt trạng thái đầu và cuối trên vòng tròn pha; (2) đọc góc quét; (3) t = Δ(góc)/ω; nhớ phân biệt hai nghiệm (đi lên/xuống).

**Trực giác còn lại.** Nhận diện chuyển động là hình chiếu của chuyển động tròn.

**Bẫy.** Mất nghiệm thứ hai; nhầm đơn vị góc; áp cho dao động không điều hoà.

---

### K12. Vật rắn 3D và tổng hợp chuyển động quay (bậc IPhO)

**Phát biểu.**
- v_B = v_A + ω × AB (vector 3D); a_B = a_A + α × AB + ω × (ω × AB).
- **Cộng vận tốc góc:** ω_{a/c} = ω_{a/b} + ω_{b/c} (vật a đối với c qua trung gian b).
- **Trục quay tức thời:** chuyển động rắn tổng quát = quay quanh một trục + tịnh tiến dọc trục (Chasles/Mozzi). Khi có điểm cố định (đỉnh nón, con quay), trục quay tức thời đi qua điểm cố định.
- **Lăn không trượt trong 3D:** v(điểm vật chất tại tiếp điểm) = vận tốc nền tại đó.
  - Nón (đỉnh cố định) lăn trên mặt phẳng: trục quay tức thời = đường sinh tiếp xúc. Với nửa góc β (trục nón hợp mặt phẳng góc β) và tiến động Ω (quay của trục nón quanh phương thẳng đứng): ω = ω_spin·ê_trục + Ω·ẑ, ω nằm ngang ⇒ ω_spin = −Ω/sinβ, |ω| = Ω cotβ (A17).
  - Cầu/đĩa lăn không trượt trên mặt phẳng: v_O = R·(ω × ẑ) (ẑ = pháp tuyến), **thành phần ω_z tuỳ ý** ⇒ **phi holonomic**.
- Đạo hàm vector gắn vật: de/dt = ω × e.

**Kiểu CHỖ.** Vật rắn có điểm cố định; vật rắn lăn trên mặt; hệ nhiều khâu có nhiều trục quay; con quay.

**Pre.** Các phép quay được **cộng dưới dạng vector vận tốc góc** (đúng) — nhưng **KHÔNG** cộng các góc quay hữu hạn theo cách vector (phi giao hoán). Điểm A, B cùng vật rắn.

**Suf.**
- Có ≥ 2 trục quay chồng lên nhau (quay quanh trục + trục đó quay quanh trục khác).
- Có nón, cầu, con quay, bánh xe nghiêng.

**Post.** Vector ω; phương trình v = 0 tại tiếp điểm.

**Trình tự cố định.**
1. Phân rã chuyển động thành **chuỗi quay** qua các khung trung gian (mỗi khâu 1 trục).
2. Viết ω_khâu, cộng vector (ω_{a/c} = Σω).
3. Viết điều kiện lăn: v(tiếp điểm) = vận tốc nền.
4. Giải hệ vector (tuyến tính theo ω, v_O).
5. Kiểm: ω có nằm trên trục quay tức thời như dự đoán.

**Trực giác còn lại.** Hình dung 3D; chọn khung trung gian.

**Bẫy.** Cộng góc quay hữu hạn như vector; bỏ qua ω_z tự do của cầu (ẩn dư); tính a bằng a = ω²r cho chuyển động quay không đều mà quên α × r và các hạng tử Coriolis giữa các trục.

---

### K13. Tương đối hẹp — động học (bậc IPhO)

**Phát biểu (giáo trình chuẩn, Mức B).** Hệ S′ chuyển động với vận tốc V dọc +x đối với S, β = V/c, γ = 1/√(1−β²):
- x′ = γ(x − Vt), t′ = γ(t − Vx/c²); khoảng bất biến s² = c²t² − x².
- Cộng vận tốc: u′ = (u − V)/(1 − uV/c²) (dọc); u′_⊥ = u_⊥/(γ(1 − uV/c²)).
- Quang sai: cosθ′ = (cosθ − β)/(1 − β cosθ).
- Doppler dọc: f_thu = f_phát·√((1+β)/(1−β)) khi lại gần.

**Kiểu CHỖ.** **Sự kiện** (không phải "vật"); thời điểm/vị trí đo bằng hai hệ.

**Pre.** Hệ quán tính; vận tốc ≳ 0,1c; tín hiệu ánh sáng.

**Suf.** "Gần vận tốc ánh sáng", "tia sáng", "đồng hồ chuyển động", "chiều dài trong hệ khác".

**Err.** Khi β ≪ 1: sai số của Galileo cỡ β²; ghi tham số nhỏ.

**Trình tự cố định.** (1) đặt **các sự kiện** cần thiết; (2) toạ độ (x, t) của chúng trong hệ thuận tiện; (3) biến đổi Lorentz; (4) đọc hiệu ứng (co chiều dài, giãn thời gian, không đồng thời) từ hiệu toạ độ sự kiện.

**Trực giác còn lại.** Chọn sự kiện đúng.

**Bẫy.** Điểm phi vật chất (K8) có thể vượt c mà không vi phạm; nhầm "chiều dài đo đồng thời" với "chiều dài đo tại cùng vị trí"; áp Galileo ở β lớn.

---

### K14. Gần đúng, sai số, thứ nguyên, trường hợp giới hạn (công cụ **kiểm tra**, không phải công cụ giải)

**Phát biểu.** Khai triển hữu ích (góc nhỏ ε): sinε ≈ ε (sai số ε³/6), cosε ≈ 1 − ε²/2, (1 + ε)^n ≈ 1 + nε, √(1 + ε) ≈ 1 + ε/2, 1/(1 − ε) ≈ 1 + ε.

**Pre.** Tham số nhỏ đã được nêu rõ [Đ/S]. **Mỗi lần gần đúng: ghi lại sai số bậc nhất bị bỏ (Err).**

**Quy trình kiểm tra 5 bước (nên dùng cho mọi bài):**
1. **Thứ nguyên:** hai vế cùng thứ nguyên.
2. **Giới hạn đã biết:** cho tham số → 0/→ ∞/→ giá trị đặc biệt; kết quả có về đáp án đã biết không (thang chạm sàn α → 0 ...).
3. **Đối xứng/đảo:** đổi vai trò các vật, kết quả đối xứng?
4. **Hai đường giải:** cùng Q giải bằng hai công cụ độc lập (ví dụ toạ độ và ICR); hai kết quả phải trùng (ví dụ 8 và 9 ở mục 6).
5. **Dấu và miền:** đáp án nằm trong miền hợp lý? (t ≥ 0, không chạm đất trước, dây căng…).

---

### K15. Hệ thức hàm số ⇒ đạo hàm: chuyển động của ảnh, tia phản xạ, bóng (cầu nối quang–động học)

**Phát biểu.** Tinh thần P\*: **mọi hệ thức hình học giữa các đại lượng biến thiên đều đạo hàm được**.
- **Thấu kính mỏng:** 1/d + 1/d′ = 1/f ⇒ ḋ′ = −(d′/d)²·ḋ = −m²·ḋ (m = d′/d) (A19). Vật lại gần thấu kính (ḋ < 0) ⇒ ảnh (thật) đi ra xa (ḋ′ > 0). Thành phần **ngang**: y′ = m·y ⇒ ẏ′ = m·ẏ + ṁ·y (ṁ ≠ 0 nếu d đổi).
- **Gương phẳng:** ảnh đối xứng với vật qua gương; **gương quay góc θ ⇒ tia phản xạ quay 2θ** (vận tốc góc tia phản xạ = 2× vận tốc góc gương).
- **Vệt sáng/bóng:** dùng K8.

**Kiểu CHỖ.** Vật–ảnh; tia phản xạ; nguồn–bóng.

**Pre.** Quang hình gần trục cho thấu kính mỏng; ảnh tồn tại (không ở vô cực) [K].

**Suf.** "Ảnh của vật chuyển động", "gương quay", "vệt sáng trên màn".

**Trình tự cố định.** (1) viết hệ thức hình học/quang (f(q) = 0); (2) đạo hàm theo t (P\*); (3) khử ẩn phụ.

**Trực giác còn lại.** Không nhiều; đây là thủ tục cơ học.

**Bẫy.** Quên dấu; dùng m thay cho m² với vận tốc **dọc**.

---

## 3. THƯ VIỆN TOÁN TỬ TIỀN XỬ LÝ (T1 → T15)

Đây là phần "tiện thể (pre-processing) chuyển bài Vật Lý về dạng áp dụng được CÔNG CỤ" trong Vấn đề 1. Mỗi toán tử biến đổi bài toán B → B′ (cùng đáp án, dễ hơn). Theo đúng tinh thần README: **mỗi toán tử có Pre riêng**. Dùng khi Pre thoả; không thoả mà dùng ⇒ ra bài toán khác.

| # | Toán tử | Pre (phải thoả) | Post (kết quả) | Dấu hiệu để dùng | Bẫy |
|---|---|---|---|---|---|
| T1 | **Đổi hệ quy chiếu** (K4) | công thức chuyển hệ đầy đủ số hạng | ít ràng buộc hơn/Q đơn giản hơn | có vật đứng yên trong hệ nào đó; hai vật cùng g; đường nối quay | quên số hạng hệ quay |
| T2 | **Chia giai đoạn** tại sự kiện | có sự kiện xác định (va chạm, chạm đất, đổi gia tốc, v = 0) | mỗi đoạn dùng công cụ riêng + điều kiện nối (r, v liên tục) | nhiều kiểu chuyển động nối tiếp | nối sai (a không nhất thiết liên tục) |
| T3 | **Tách thành phần** độc lập | gia tốc/ràng buộc tách được theo trục trực giao | bài 2D → hai bài 1D | ném xiên; chuyển động trên mặt nghiêng | ràng buộc "chéo" làm hai thành phần liên hệ |
| T4 | **Quá trình → ảnh chụp tức thời** | Q chỉ hỏi ở **một cấu hình/thời điểm** | bậc vận tốc/gia tốc là **hệ tuyến tính** (1.6c) | "khi thanh hợp góc 60°, tìm v, a" | J kỳ dị ở cấu hình xét |
| T5 | **Chọn biến cấu hình độc lập** | F = số bậc tự do biết trước | mọi đại lượng = hàm của q | hệ có ràng buộc; nhiều đại lượng phụ thuộc | chọn q khiến hàm phức tạp: thử q khác |
| T6 | **Điểm vật chất ↔ điểm hình học** | biết loại điểm | dùng đúng công cụ (K3 hay K8) | đề hỏi vận tốc "giao điểm", "bóng", "vệt" | áp v_B = v_A + ω×AB cho điểm phi vật chất |
| T7 | **Trải phẳng bằng gương (phương pháp ảnh)** | tường phẳng bất động, phản xạ đàn hồi lý tưởng (v_t giữ, v_n đảo), tốc độ không đổi | đường thẳng trong không gian gương; số va chạm = số giao với các gương | tia/bi nảy giữa tường; ánh sáng phản xạ | tường chuyển động ⇒ không dùng |
| T8 | **Vô thứ nguyên hoá** | có ≥ 2 thang đặc trưng (độ dài, tốc độ, thời gian) | giảm số tham số; nhận diện giới hạn | nhiều tham số; cần kiểm giới hạn | chọn thang sai làm mất tính đơn giản |
| T9 | **Đạo hàm hoá ràng buộc** (P\*) | ràng buộc holonomic khả vi | ràng buộc vận tốc/gia tốc | có bất kỳ f(q, t) = 0 | quên ∂f/∂t khi ràng buộc phụ thuộc t |
| T10 | **Hình học hoá / đồ thị hoá** | quan hệ biểu diễn được trên đồ thị (s–t, v–t, không gian vận tốc, vòng pha, Minkowski) | bài Toán thành bài hình học | v–t/đồ thị; tốc độ tương đối cố định; dao động | đọc sai tỉ lệ/dấu |
| T11 | **Tuyến tính hoá cục bộ** | tham số nhỏ ε xác định | hệ tuyến tính ± sai số bậc 2 | dao động nhỏ, góc nhỏ | quên ghi Err |
| T12 | **Đảo thời gian** | quá trình chỉ hình học (không ma sát, ràng buộc khả nghịch) | bài "từ đích trở lại" có dạng quen | ném đến đỉnh; va chạm đàn hồi | quá trình có tiêu hao |
| T13 | **Đổi biến độc lập** | biến mới đơn điệu theo t | t = t(góc/độ dài): phương trình gọn | vật chuyển động quanh tâm; góc thay đổi đều | biến mới không đơn điệu |
| T14 | **Quy về mô hình đã biết** | mô hình kia đúng **cấu trúc** (cùng topology + loại ràng buộc) | dùng nghiệm đã có | bài "quen mặt" ở dạng khác | chỉ giống bề mặt (rơi vào pattern-matching) |
| T15 | **Kiểm toán dấu & chiều dương** | — | mọi vector đúng dấu | mọi bài | lỗi dấu là nguồn sai số số 1 |

**Trình tự dùng:** T15 (chốt dấu) → T1 (chọn hệ) → T5 (chọn q) → T2 (chia đoạn nếu có sự kiện) → T3/T4 (tách/chụp) → T9 (đạo hàm) → T10/T13 (dạng đồ thị/biến mới nếu cần) → T11 nếu có tham số nhỏ.

---

## 4. VẤN ĐỀ 1 — GIAO THỨC NHẬN DIỆN CÔNG CỤ VÀ QUÉT CHỖ

### 4.1. Bài toán tìm kiếm (nhắc lại theo README, cụ thể hoá cho Động học)

Cho mô hình M của bài B. Tìm dãy hữu hạn (ℓ₁, CHỖ₁), …, (ℓₙ, CHỖₙ) sao cho:
1. Pre(ℓᵢ) thoả tại CHỖᵢ (mức [Đ]/[S], hoặc [K] đã đưa vào sổ kiểm sau);
2. Post(ℓᵢ) sinh ra ràng buộc mới có ý nghĩa cho C;
3. Sau bước n: C ∪ L ⊢ Q (đủ để tính Q — kiểm đóng kín ở 1.6d).

**Tuyên bố cương lĩnh (để bạn kiểm chứng, không phải sự thật đã chứng minh):** với Động học ở mức HSGQG, 15 công cụ K0–K15, cùng 15 toán tử T1–T15, **có thể** phủ đa số bước hợp lý; phần còn lại là "trực giác còn lại" ghi ở từng thẻ. Mục 9 cho phép thử.

### 4.2. Nhận diện theo **cấu trúc**, không theo chủ đề — năm trục

Đây là câu trả lời cho câu hỏi của README: *"dạng" phải định nghĩa theo trục nào để hữu hạn, bao trùm biến thể lạ, không rơi vào khớp mẫu bề mặt?* → Theo **cấu trúc toán học của bài**, gồm năm trục:

| Trục | Câu hỏi | Giá trị có thể | Công cụ liên quan |
|---|---|---|---|
| **Q** | Câu hỏi cuối là gì? | Q1–Q10 (1.4) | quyết định K nào là "đích" |
| **E** (thực thể) | Có những loại đối tượng nào? | điểm vật chất / phi vật chất / vật rắn / dây–thanh / bề mặt / hệ quy chiếu | K1, K2, K3, K8 |
| **C** (ràng buộc) | Có ràng buộc loại nào? | độ dài, tiếp xúc/lăn, hướng v biết, "luôn hướng", đối xứng | K1, K2, K3, K9 |
| **A** (gia tốc) | Gia tốc thế nào? | hằng / hằng từng đoạn / phụ thuộc vị trí / quay / không biết | K5, K6, K7, K4 |
| **T** (topology) | Đồ thị nối vật có chu trình không? Bao nhiêu? | ℓ_loop = E − V + 1 | 1.6, 5.3 |

Một bài là **tổ hợp giá trị** của năm trục ấy. Số tổ hợp hữu hạn; **biến thể lạ** (ví dụ "cung" thay cho "ròng rọc") chỉ đổi *dạng hình học* mà giữ giá trị các trục — nên công cụ vẫn nhận ra.

### 4.3. Bảng định tuyến nhanh (Q, E, C, A → công cụ)

| Nếu đọc thấy… | Bật công cụ | Tra thẻ |
|---|---|---|
| thanh/dây/khoảng cách cố định | K1 (+ K3 nếu vật rắn) | 2 |
| tiếp xúc/lăn/tựa/không trượt | K2, K3 | 2 |
| vật rắn, điểm có hướng v biết | K3 (ICR) | 2 |
| ≥ 2 vật chuyển động, hỏi quan hệ giữa chúng | K4 | 2 |
| hai vật cùng g / "ném" nhiều vật | K4 (hệ rơi tự do), K6 | 2 |
| a hằng; đồ thị v–t; quãng đường | K5 | 2 |
| "ném", bề mặt cắt quỹ đạo, tầm xa, đường bao | K6 | 2 |
| "quanh", "tâm", bán kính cong, thành phần a | K7 | 2 |
| "giao điểm", "bóng", "vệt sáng", "điểm chạm chạy" | K8 | 2 |
| "luôn hướng về", "đuổi", đa giác đều | K9 | 2 |
| "ngắn nhất/lớn nhất/tối ưu/gần nhất" | K10 (+K4) | 2 |
| dao động, hình chiếu chuyển động tròn | K11 | 2 |
| 3D, con quay, nón, ≥ 2 trục quay | K12 | 2 |
| tia sáng, v ~ c | K13 | 2 |
| ảnh, gương quay, thấu kính | K15 | 2 |
| *mọi bài, cuối cùng* | K14 (kiểm) | 2 |

**Cảnh báo:** bảng này dùng **để gợi ý danh sách quét**, không phải để chọn duy nhất. Cụm từ chỉ là *dấu hiệu bề mặt*; công cụ chỉ được coi là "đủ" khi Suf **và** Pre thoả ở một CHỖ cụ thể (4.4).

### 4.4. Giao thức quét CHỖ (brute-force có kỷ luật, đúng tinh thần README)

**S0 — Phân rã đề.** Cắt đề thành **câu nguyên tử** (mỗi câu một ý). Gán nhãn O/V/C/Q/I. Mỗi dữ kiện số vào bảng biến. Đánh dấu dữ kiện *chưa* dùng — đó là tín hiệu (nhưng không đủ): dữ kiện chưa dùng có thể là nhiễu, hoặc là dấu vết của công cụ chưa bật.

**S1 — Lập kho CHỖ theo kiểu.** Liệt kê **đầy đủ** (không dựa vào trực giác chọn lọc) mọi CHỖ:

| Kiểu CHỖ | Cách liệt kê máy móc | Ví dụ |
|---|---|---|
| Điểm | mọi đầu mút, tâm, tiếp điểm, điểm nối, điểm bẻ dây, giao điểm, đỉnh quỹ đạo | A, B, O, P… |
| Cặp điểm cùng vật | với mỗi vật rắn: mọi cặp điểm quan trọng (C(k,2)) | (A,B) trên thanh |
| Vật rắn | mỗi vật cứng | thanh, đĩa, nêm |
| Tiếp điểm | mỗi cạnh của đồ thị topology | bánh–nền |
| Sợi dây/chuỗi | mỗi sợi | dây qua ròng rọc |
| Vòng kín | cơ sở chu trình (số = E − V + 1) | thanh–tay quay–con trượt |
| Thời điểm đặc biệt | t = 0; va chạm; chạm đất; v = 0; dừng; đổi gia tốc | đỉnh quỹ đạo |
| Khoảng thời gian | giữa các thời điểm đặc biệt | pha nhanh dần |
| Cặp (đối tượng, hệ) | mỗi vật ×{đất, mỗi vật khác, hệ rơi tự do, hệ quay} | (B, hệ A) |
| Giao điểm/phi vật chất | mọi "bóng", "vệt", "điểm cắt" | vệt sáng |
| Điểm trên quỹ đạo | các điểm hỏi ρ/a_n | đỉnh |
| Cặp quỹ đạo | mọi cặp vật có Q gặp nhau/khoảng cách | (đạn A, đạn B) |

**S2 — Quét theo công cụ.** Lần lượt K0 → K15 (mỗi K quét **toàn bộ** kho CHỖ cùng kiểu). Với mỗi (K, CHỖ): kiểm **Suf** (bằng mắt, đọc đề/hình). Nếu Suf đúng ⇒ ghi vào **sổ quét**.

**Mẫu sổ quét:**

| # | Công cụ | CHỖ | Suf ✓? | Pre (mức) | Post (phương trình sinh ra) | Có ý nghĩa? | Chọn? |
|---|---|---|---|---|---|---|---|
| 1 | K1 | thanh AB | ✓ ("thanh") | [Đ] | (r_A−r_B)·(v_A−v_B)=0 | ✓ liên hệ hai ẩn v | ✓ |
| 2 | K2 | tiếp điểm B–tường | ✓ | [K] còn tiếp xúc | v_B·n=0 | ✓ | ✓ |
| … | | | | | | | |

**S3 — Kiểm "có ý nghĩa".** Post của một bước được coi là **có ý nghĩa** khi thoả cả ba:
- (i) Liên hệ ≥ 2 đại lượng, trong đó ≥ 1 đại lượng là ẩn hoặc cần cho Q;
- (ii) **Độc lập** với các phương trình đã có (không suy ra từ chúng);
- (iii) Không chỉ là đổi tên biến.

**S4 — Chọn tập tối thiểu & kiểm đóng kín.** Lập bảng #ẩn – #phương trình độc lập (1.6d). Nếu **thiếu** → 4.6. Nếu **thừa** → kiểm nhất quán/độc lập tuyến tính; phương trình thừa dùng làm **kiểm tra chéo**.

**S5 — Ghi Sổ Pre.** Mỗi bước dùng một Pre mức [K] phải được ghi vào **Sổ Pre** cùng "cách kiểm sau".

**Mẫu Sổ Pre:**

| Pre | Nằm ở công cụ | Mức | Cách kiểm sau khi có nghiệm |
|---|---|---|---|
| dây căng | K1 | [K] | lực căng ≥ 0 hoặc điều kiện hình học |
| chưa chạm đất trước t* | K4 | [K] | y_A(t*), y_B(t*) ≥ 0 |
| cực trị nội tại trong miền | K10 | [K] | so với biên |

### 4.5. Chống khớp mẫu bề mặt: **kiểm thử biến thể lạ**

Khi bạn đã có bộ công cụ và bộ Suf, kiểm xem **nó còn nhận đúng khi bề mặt thay đổi** bằng ba phép biến đổi *bảo toàn cấu trúc*:

1. **Đổi hình học, giữ topology và loại ràng buộc:** thay ròng rọc bằng cung tròn ôm; thay thang bằng thanh cong; thay đĩa bằng elip? (Cảnh báo: elip lăn không trượt ≠ đĩa: tâm không còn ở độ cao hằng.) → công cụ vẫn nhận ra thì Suf đủ tổng quát.
2. **Đổi vai trò vật:** hoán vị vật đuổi và bị đuổi; vật A làm hệ.
3. **Đổi thực thể vật chất ↔ phi vật chất:** thay vật thật bằng bóng/vệt sáng — K3 phải nhường K8.

Nếu một biến thể bị bỏ lọt ⇒ Suf hẹp quá ⇒ sửa Suf (và ghi vào nhật ký thư viện, mục 9).

### 4.6. Chẩn đoán bế tắc (khi #phương trình < #ẩn hoặc không thấy CHỖ)

```
Thiếu phương trình?
 ├─ Đã quét đủ K0..K15 trên MỌI kiểu CHỖ chưa?  → chưa: quét nốt (kho CHỖ S1)
 ├─ Có CHỖ đúng Suf nhưng bị bỏ vì Pre [K] "không chắc"?  → giả sử thoả, ghi Sổ Pre, đi tiếp
 ├─ Đã thử ĐỔI HỆ QUY CHIẾU (T1) chưa? → mỗi vật làm hệ một lần
 ├─ Đã thử ĐỔI BIẾN (T13) hoặc CHIA GIAI ĐOẠN (T2) chưa?
 ├─ Có điểm phi vật chất (T6/K8) bị coi là vật chất?
 ├─ Đã đạo hàm hoá MỌI ràng buộc holonomic (T9) chưa? (đặc biệt: ràng buộc phụ thuộc t)
 ├─ Có bậc vi phân nào bị bỏ (cần gia tốc mà mới có vận tốc)?
 └─ Vẫn thiếu ⇒ nghi thư viện thiếu công cụ → 4.7
Thừa phương trình?
 ├─ Phụ thuộc tuyến tính? (bỏ bớt)
 ├─ Mâu thuẫn? ⇒ Pre bị vi phạm hoặc I (diễn giải) sai
 └─ Dùng để kiểm chéo (K14 bước 4)
```

### 4.7. Khi thư viện thiếu: quy trình **thêm công cụ mới** (K16, K17…)

Nếu bế tắc thật sự và mọi bước trên đều đã làm, xem xét bạn vừa phát hiện một công cụ mới. Muốn nhập vào thư viện phải điền **đủ** thẻ:

1. Tên & phát biểu (công thức).
2. Dom, Pre, **Suf (kiểm được bằng mắt!)**, Post, Err.
3. Kiểu CHỖ.
4. Trình tự cố định (không trực giác) + "trực giác còn lại".
5. Ít nhất **2 bài đã giải** bằng nó và **1 bài mà nó KHÔNG áp dụng được** (phản ví dụ — để hiểu Pre).
6. Kiểm thử biến thể lạ (4.5).

---

## 5. VẤN ĐỀ 2 — CHUYỂN SANG TOÁN ("Tọa độ hoá mở rộng", bản tái dựng)

*(Nhắc lại: tôi không xem được repo của bạn — đây là bản tái dựng của tôi. So sánh và sửa theo định nghĩa của bạn.)*

### 5.1. Pipeline P0 → P8

| Bước | Việc | Đầu ra | Công cụ hỗ trợ |
|---|---|---|---|
| **P0** | Chốt mô hình M, Q, Sổ giả định | M = (O, V, L, C, Q, I) đầy đủ | mục 1 |
| **P1** | Chọn hệ quy chiếu và hệ toạ độ | hệ đã chốt, dấu dương | 5.2, T1, T15 |
| **P2** | Chọn biến cấu hình q (đúng F) và biến phụ | bảng biến | Grübler (1.6a), T5 |
| **P3** | **Toạ độ hoá** mọi điểm quan tâm: r_i = r_i(q, t) (và các vector đơn vị bị quay) | bảng vector | K0, K7 |
| **P4** | **Ràng buộc → phương trình vị trí** (holonomic; nhóm phi holonomic giữ ở dạng vận tốc) | f_k(q, t) = 0 | K1, K2, K3 (hình học), 5.3 |
| **P5** | **Đạo hàm:** v_i, a_i; đạo hàm ràng buộc (P\*) | hệ **tuyến tính** theo q̇, q̈ | T9, T4 |
| **P6** | **Dịch Q sang dạng Toán** | mục tiêu Toán | bảng 5.4 |
| **P7** | **Đóng kín & nhất quán**: đếm; kiểm Pre [K]; kiểm miền/case; kiểm điểm kỳ dị | "hệ đóng, miền rõ" | 1.6d, Sổ Pre |
| **P8** | **Bàn giao V3**: chuẩn hoá thành một trong các dạng ở 5.5 | phiếu bàn giao | 5.5 |

### 5.2. Chọn hệ quy chiếu và toạ độ — tiêu chí bằng bảng (thay trực giác bằng đếm)

Với mỗi hệ ứng viên H, chấm ba số (nhỏ hơn = tốt hơn):

- **c_C** = số ràng buộc còn *phụ thuộc thời gian* trong H (ràng buộc tĩnh dễ xử lý).
- **c_r** = tổng số số hạng của các r_i(q, t) quan trọng.
- **c_Q** = "độ xa" của Q khỏi dạng chuẩn (Q trở thành hình học đơn giản nhất trong hệ này?).

Chọn H có tổng nhỏ nhất. Hướng dẫn nhanh (từ kinh nghiệm cơ học cơ cấu):

| Tình huống | Hệ nên thử | Vì sao |
|---|---|---|
| Có một vật lớn nhiều ràng buộc (nêm, xe) | hệ gắn vật đó | ràng buộc thành tĩnh |
| ≥ 2 vật chỉ chịu g | hệ rơi tự do | chuyển động thẳng đều |
| Có "tâm" để quay quanh | cực/cầu quanh tâm | ρ, θ đơn giản |
| Vật đuổi theo một điểm | hệ quay theo đường nối | phép chiếu lên đường nối |
| Bề mặt nghiêng | trục dọc–vuông mặt | g phân tích một lần |
| Vòng kín có nhiều thanh | **toạ độ phức** dọc vòng | 5.3 |
| Đối xứng rõ (đa giác đều) | cực quanh tâm đối xứng | thu về 1 phương trình |
| Tương đối tính | hệ tiện: hệ tĩnh của "vật" mang đồng hồ | dễ đọc sự kiện |

### 5.3. Phương pháp vòng kín (loop closure) — quy trình máy móc cho cơ cấu và hệ nhiều khâu

Với **mỗi chu trình độc lập** (số = E − V + 1):

1. Chọn một chiều đi vòng; đặt vector cho mỗi khâu (độ dài l_k, góc θ_k).
2. Viết **đóng kín**: Σ l_k·e^{iθ_k} = 0 (số phức; hai phương trình thực: Re, Im).
3. Đạo hàm theo t (P\*): Σ i·l̇... — với l_k hằng: Σ i·l_k·θ̇_k·e^{iθ_k} = 0 (vận tốc); đạo hàm lần nữa: Σ [i·l_k·θ̈_k − l_k·θ̇_k²]·e^{iθ_k} = 0 (gia tốc).
4. Khử các góc/độ dài phụ bằng các phương trình vị trí (bước hình học), rồi giải hệ **tuyến tính** cho θ̇_k, θ̈_k.
5. Đếm: 2ℓ_loop phương trình thực so với số biến — phải cho đúng F (1.6b).

*Ví dụ (tay quay–thanh truyền–con trượt):* r·e^{iθ} + l·e^{iφ} = x (thực). Hai phương trình: r cosθ + l cosφ = x; r sinθ + l sinφ = 0. Biến: θ, φ, x ⇒ 3 biến, 2 phương trình ⇒ F = 1 ✓ (khớp Grübler).

### 5.4. Bảng dịch câu hỏi Q sang dạng Toán (chi tiết hơn 1.4)

| Q đề hỏi | Dạng Toán | Việc cần làm ở P6 | Hay sai |
|---|---|---|---|
| v, a tại cấu hình cho trước | J(q₀)·q̇ = b; J(q₀)·q̈ = b′ | thay q = q₀ **trước**, rồi giải tuyến tính (T4) | quên số hạng v² trong gia tốc |
| tỉ số vận tốc | khử ẩn trong hệ tuyến tính | tỉ số hai nghiệm | dấu |
| quỹ đạo | khử tham số t | tìm hệ thức chỉ chứa x, y | mất miền của tham số |
| gặp nhau/va chạm | r_A(t) = r_B(t) (vector ⇒ 2 hoặc 3 phương trình, 1 ẩn t + ẩn phụ) | đặt hệ; số ẩn = số phương trình | cùng vị trí khác thời điểm |
| khoảng cách nhỏ nhất | min_t |r₀ + v_rel·t| (bậc hai) hoặc min theo tham số | đưa về **một** biến; d² thay d | t* < 0 |
| cực trị theo tham số | f′ = 0 hoặc D = 0; kiểm biên | ghi miền | quên biên |
| quãng đường | ∫|v|dt | chia tại v = 0 | dùng độ dời |
| bán kính cong | ρ = v²/a_n | lấy v, a cùng hệ | hệ sai |
| tồn tại/số nghiệm | discriminant; miền giá trị | biến đổi về bậc hai/đơn điệu | bỏ nghiệm ngoại lai |
| quỹ tích/đường bao | F(x, y; λ) = 0, ∂F/∂λ = 0 | khử λ | không kiểm nhánh |
| điều kiện mô hình còn đúng | bất đẳng thức sau nghiệm | [K] trong Sổ Pre | không bao giờ quay lại kiểm |

### 5.5. Phiếu bàn giao cho Vấn đề 3 (dạng chuẩn của bài Toán)

Kết thúc V2, bạn phải có **một phiếu** gồm (làm sạch, không còn Vật Lý):

1. **Loại bài Toán:** (a) hệ phương trình đại số phi tuyến; (b) hệ tuyến tính với tham số; (c) ODE + điều kiện đầu; (d) tối ưu 1 biến; (e) tích phân; (f) bất đẳng thức/biện luận.
2. **Ẩn** (tên + ý nghĩa) và **tham số cho trước**.
3. **Phương trình đã đóng kín** (đánh số) + **số ẩn = số phương trình**.
4. **Miền** của mỗi ẩn (ví dụ t ≥ 0, 0 < θ < π/2, y ≥ 0).
5. **Điều kiện đầu/biên**.
6. **Đại lượng Q cần tính** biểu diễn qua ẩn.
7. **Sổ Pre [K]:** các bất đẳng thức cần kiểm **sau** khi có nghiệm.
8. **Kiểm tra chéo** đã chuẩn bị: giới hạn, thứ nguyên, đường giải thứ hai (K14).

### 5.6. Khi hệ phương trình vị trí phi tuyến khó

- Đổi tham số: tham số bằng **góc** (cho vòng kín), bằng **độ dài** hoặc bằng **tỉ số** (cho hệ dây).
- Đảo vai biến độc lập/phụ (T13).
- Vận tốc/gia tốc **không cần** giải hệ vị trí **nếu Q chỉ hỏi tại một cấu hình cho trước**: chỉ cần *hình học của cấu hình đó* (T4).
- Với hệ phi holonomic: **không cố tích phân**; giữ ở dạng ODE bậc nhất cho q̇ = h(q, u).

---
