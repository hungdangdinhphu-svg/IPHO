*from Hung Dinh Phu Dang (Đặng Đình Phú Hưng), https://github.com/nahhididwin/;

# THUẬT TOÁN GIẢI ĐỘNG HỌC CHẤT ĐIỂM (KINEMATICS)
### Dành cho: Olympic Vật Lý TP.HCM — Khối 10
### Đối tượng: Học sinh tầm trung, trực giác vật lý tầm trung, **kỷ luật và tuân thủ**

---

## PHẦN 0 — TẠI SAO ĐÂY LÀ "ALGORITHM" THẬT, KHÔNG PHẢI ẢO GIÁC

Một quy trình chỉ được gọi là algorithm nếu thỏa **cả hai** điều kiện sau (đúng như bạn đã đặt ra):

1. **Tổng quát & máy móc ở bước "biến đề thành toán"** — không đòi hỏi phát hiện ra một mẹo hiếm, không phổ biến.
2. **Bước giải toán phát sinh phải công thức hóa** — không đòi hỏi kỹ năng biến đổi đại số mang tính "trực giác/heuristic".

Lý do Kinematics (trong phạm vi lớp ≤12, gia tốc không đổi hoặc từng khúc không đổi, không tương đối tính) là một **hệ đóng** — tức là một algorithm hoàn chỉnh **chắc chắn tồn tại**:

- Toàn bộ vật lý trong phạm vi này quy về đúng **3 nhóm phương trình gốc** (xem Phần 1) — không có phương trình "ẩn" nào khác có thể xuất hiện.
- Số lượng "actor" (vật chuyển động) trong một bài luôn hữu hạn, nhỏ (thường 1–2).
- Số lượng "sự kiện" (event) mà đề có thể hỏi (gặp nhau, đạt độ cao cực đại, chạm đất...) là một **tập hữu hạn, liệt kê được** — xem Bảng B ở Phần 2.
- Cách đề bài "mã hóa" các điều kiện đầu bằng tiếng Việt cũng là một **tập hữu hạn cụm từ chuẩn** — xem Bảng A ở Phần 2.

⇒ Việc "đọc đề" thực chất là một bài toán **phân loại + tra bảng + điền khuôn (template-filling)**, không phải một bài toán sáng tạo mở. Đây chính là lý do nó khác về bản chất với "chứng minh bất đẳng thức" (nơi bảng tra cứu không đủ tổng quát) — như bạn đã chỉ ra ở phần II tài liệu gốc.

**Nguyên tắc tối cao khi dùng tài liệu này:** Khi gặp một bài mới, **không được phép "cảm" đề**. Luôn chạy đúng trình tự: (1) đọc đề theo Phần 2 → lập bảng dữ kiện → (2) tra "loại bài" → route sang thuật toán con tương ứng ở Phần 3 → (3) giải hệ phương trình phát sinh bằng công cụ ở Phần 4.

---

## BẢNG TRA CỨU NHANH (Routing Table)

| Từ khóa xuất hiện trong đề | → Thuật toán con |
|---|---|
| "tốc độ trung bình", "vận tốc trung bình", nhiều chặng | 3.1 |
| Đồ thị x–t, v–t, a–t (trục quen thuộc) | 3.2 |
| Đồ thị với 2 đại lượng "lạ" (không phải x,v,a,t trực tiếp) | 3.3 |
| "thả rơi", "rơi tự do", "ném thẳng đứng" | 3.4 |
| "đuổi kịp", "bắt kịp", "gặp nhau", 2 xe/2 vật cùng đường thẳng | 3.5a |
| "nhìn từ toa tàu/xe đang chạy", "quan sát từ mặt đất", đổi hệ quy chiếu | 3.5b |
| "ném xiên", góc so với phương ngang, tầm xa/tầm cao | 3.6 |
| "chuyển động tròn", chu kỳ T, tần số f, tốc độ góc ω, bán kính bánh xe | 3.7 |
| "mặt trời lặn", "đường chân trời", "bán kính Trái Đất" | 3.8 |
| "bơi qua sông", "dòng nước", "gió thổi", hợp hai vận tốc | 3.9 |

---

## PHẦN 1 — KHUNG TỔNG QUÁT (Master Algorithm — MAK)

Mọi bài Kinematics trong phạm vi này đều quy về việc lắp dữ kiện vào **đúng 3 phương trình gốc** cho mỗi actor:

```
v(t) = v₀ + a·(t − t₀)
x(t) = x₀ + v₀·(t − t₀) + ½·a·(t − t₀)²
v² = v₀² + 2a·(x − x₀)          [suy ra từ 2 pt trên, dùng khi không có t]
```

**6 bước bắt buộc, luôn theo đúng thứ tự:**

1. **Chọn hệ quy chiếu**: gốc tọa độ, chiều dương, gốc thời gian t=0 (nêu rõ, viết ra giấy — không giữ trong đầu).
2. **Liệt kê actor**: mỗi vật chuyển động là 1 dòng trong bảng dữ kiện (Phần 2).
3. **Viết phương trình chuyển động** cho từng actor bằng 3 công thức gốc ở trên (nếu a đổi giai đoạn → tách thành nhiều pha, mỗi pha một bộ x₀,v₀,t₀ riêng).
4. **Dịch "sự kiện" đề hỏi thành phương trình/bất phương trình** (tra Bảng B, Phần 2).
5. **Giải hệ phương trình** bằng công cụ ở Phần 4 (thuần đại số, không cần vật lý nữa).
6. **Thế ngược lại + kiểm tra thứ nguyên/độ lớn hợp lý.**

Toàn bộ Phần 3 chỉ là các **biến thể có sẵn của 6 bước này** — không có gì mới về bản chất, chỉ khác ở cách điền Bước 3–4.

---

## PHẦN 2 — THUẬT TOÁN "ĐỌC ĐỀ" (mục tiêu: dưới 60 giây)

### Quy trình
1. Gạch chân **mọi con số + đơn vị** trong đề (quét cơ học, không suy nghĩ).
2. Đếm số actor → mở 1 dòng bảng dữ kiện cho mỗi actor: `[x₀, v₀, a, t₀, ghi chú]`.
3. Với mỗi cụm từ mô tả chuyển động, tra **Bảng A** để điền vào bảng dữ kiện — không tự suy diễn.
4. Xác định câu hỏi cuối cùng thuộc loại "sự kiện" nào → tra **Bảng B** để có phương trình.
5. Đối chiếu Bảng Tra Cứu Nhanh ở trên → route sang đúng mục ở Phần 3.

### Bảng A — Cụm từ mô tả → điều kiện đầu

| Cụm từ trong đề | Ý nghĩa toán học |
|---|---|
| "thả rơi", "rơi tự do" | v₀ = 0; a = g, hướng xuống |
| "ném thẳng đứng lên" | v₀ hướng lên; a = g hướng xuống (ngược chiều v₀) |
| "ném thẳng đứng xuống" | v₀ hướng xuống; a = g cùng chiều v₀ |
| "chuyển động thẳng đều", "tốc độ không đổi", "duy trì tốc độ ổn định" | a = 0 |
| "nhanh dần đều" | a cùng chiều v (độ lớn v tăng) |
| "chậm dần đều" | a ngược chiều v (độ lớn v giảm) |
| "xuất phát cùng lúc" | t₀ giống nhau cho các actor |
| "...phút/giây sau mới xuất phát", "khởi hành trễ hơn" | t₀ lệch nhau — dùng chung 1 gốc thời gian, actor đến sau có phương trình chỉ có hiệu lực khi t ≥ t₀ của nó |
| "gần như ngay lập tức đạt tốc độ X" | Bỏ qua pha tăng tốc — coi a = 0 và v = X ngay từ t₀ |
| "quan sát/nhìn thấy từ toa tàu/xe đang chạy" | Cần dựng hệ quy chiếu gắn với phương tiện → dùng 3.5b |
| "quan sát từ mặt đất/người đứng yên" | Hệ quy chiếu gắn với đất (thường là hệ "chuẩn") |

### Bảng B — Câu hỏi "sự kiện" → phương trình cần lập

| Đề hỏi / mô tả | Phương trình |
|---|---|
| "gặp nhau", "đuổi kịp", "bắt kịp" | x₁(t) = x₂(t) |
| "cách nhau khoảng d" | \|x₁(t) − x₂(t)\| = d |
| "độ cao cực đại", "điểm cao nhất" | v_y(t) = 0 |
| "chạm đất", "rơi xuống mặt biển/mặt đất" | y(t) = 0 |
| "quay lại vị trí ban đầu", "trở về điểm ném" | y(t) = y₀ (hoặc x(t) = x₀) |
| "bay theo phương thẳng đứng" (trong 1 hệ quy chiếu cụ thể) | thành phần vận tốc **ngang** trong hệ quy chiếu đó = 0 |
| "quỹ đạo là đường parabol" (trong 1 hệ quy chiếu) | cả 2 thành phần vận tốc (ngang, dọc) ≠ 0 trong hệ đó |
| "mặt trời biến mất/lặn ở đường chân trời" | tia nhìn **tiếp tuyến** với mặt cầu Trái Đất tại điểm quan sát |
| "tốc độ trung bình" (bất kỳ dạng nào) | LUÔN = tổng quãng đường / tổng thời gian — không có công thức tắt nào khác an toàn (xem 3.1) |

---

## PHẦN 3 — CÁC THUẬT TOÁN CON

### 3.1 Vận tốc trung bình vs Tốc độ trung bình (cái bẫy kinh điển)

**Bước 1 — Phân loại bắt buộc:** Đề cho các chặng có **THỜI GIAN bằng nhau** hay **QUÃNG ĐƯỜNG bằng nhau**? Đây là bước duy nhất quyết định công thức.

- Nếu **thời gian mỗi chặng bằng nhau** (t₁=t₂=...=tₙ): tốc độ trung bình = **trung bình cộng** các tốc độ = (v₁+v₂+...+vₙ)/n
- Nếu **quãng đường mỗi chặng bằng nhau** (s₁=s₂=...=sₙ): tốc độ trung bình = **trung bình điều hòa** = n / (1/v₁ + 1/v₂ + ... + 1/vₙ)
- Nếu **cả hai đều KHÔNG bằng nhau** (trường hợp tổng quát, hay gặp nhất trong đề thật): bỏ 2 công thức tắt trên, quay về **định nghĩa gốc**:
  ```
  tốc độ trung bình = (s₁ + s₂ + ... + sₙ) / (t₁ + t₂ + ... + tₙ)
  ```
  với mỗi sᵢ = vᵢ·tᵢ (tính riêng từng chặng).

**Bước 2 — Bẫy "trung bình cộng":** Nếu ai đó lập luận tốc độ trung bình = trung bình cộng của các tốc độ thành phần, lập luận đó **chỉ đúng khi và chỉ khi các chặng có thời gian bằng nhau**. Đây là điều kiện cần kiểm tra máy móc mỗi lần gặp câu hỏi dạng "vì sao cách tính X lại sai/đúng".

**Bước 3 — Phân biệt vận tốc vs tốc độ:** Tốc độ trung bình (đại lượng vô hướng) = tổng **quãng đường** / tổng thời gian. Vận tốc trung bình (đại lượng vectơ) = **độ dời** / tổng thời gian. Nếu chuyển động không đổi chiều, hai giá trị này bằng nhau; nếu có đổi chiều, phải tính riêng.

*Ví dụ minh họa nhanh (số tự đặt):* Xe đi 2 giờ đầu với tốc độ 50 km/h, rồi đi tiếp 2 giờ với tốc độ 70 km/h (thời gian bằng nhau) → tốc độ trung bình = (50+70)/2 = 60 km/h — công thức tắt áp dụng được vì đúng điều kiện Bước 1.

---

### 3.2 Chuyển động thẳng biến đổi đều — đồ thị x–t, v–t, a–t "chuẩn"

Khi đồ thị dùng đúng 2 trong 3 đại lượng {x, v, a} và t, áp dụng trực tiếp quan hệ đạo hàm/tích phân dưới dạng hình học:

| Đồ thị | Độ dốc (slope) = | Diện tích dưới đường = |
|---|---|---|
| x – t | vận tốc v | (không dùng) |
| v – t | gia tốc a | độ dời Δx |
| a – t | (không dùng trực tiếp) | độ biến thiên vận tốc Δv |

**Quy trình:** (1) xác định 2 điểm rõ tọa độ trên đồ thị → (2) tính slope = Δ(trục dọc)/Δ(trục ngang) → (3) diện tích = hình học cơ bản (tam giác, hình thang) → (4) gán các giá trị vào đúng phương trình gốc ở Phần 1 để tìm ẩn còn lại.

---

### 3.3 Thuật toán giải mã đồ thị "lạ" (Graph Decoding)

Áp dụng khi đề cho đồ thị của **hai đại lượng phái sinh** (không phải x, v, a, t trực tiếp) — ví dụ: động lượng lúc chạm đất theo công suất trung bình của trọng lực trong quá trình rơi, hoặc v² theo s, hoặc s theo t².

**Quy trình bắt buộc (khử tham số):**
1. Xác định **biến gốc thật sự** đang thay đổi giữa các lần thử (thường là độ cao h, hoặc thời gian t).
2. Viết **từng đại lượng trên 2 trục** như một hàm của biến gốc đó, dùng đúng công thức Kinematics chuẩn (Phần 1) — không được bỏ qua bước này dù có vẻ dài dòng.
3. **Khử biến gốc** giữa 2 phương trình để tìm quan hệ trực tiếp giữa 2 trục.
4. Kiểm tra dạng quan hệ thu được là bậc nhất (đường thẳng), bậc hai, hay dạng khác → so khớp với hình dạng đồ thị đã cho.
5. Đọc slope/hoành độ gốc/tung độ gốc từ đồ thị (dùng 2 điểm cụ thể, không "áng chừng") → thế vào phương trình ở bước 3 → giải ẩn cần tìm.

*Ví dụ minh họa (dựng lại từ một dạng đề thật, số liệu tự đặt để minh họa cách làm — không phải số liệu gốc):* Thả một vật rơi tự do từ độ cao h (thay đổi giữa các lần thả), xét lúc chạm đất: động lượng P = m·v = m·√(2gh); công suất trung bình của trọng lực trong quá trình rơi S = (công của trọng lực)/(thời gian rơi) = (mgh)/√(2h/g). Khử h giữa 2 biểu thức này (bình phương P, bình phương S, rồi chia) sẽ cho ra một quan hệ **bậc nhất** giữa P và S, với hệ số góc chỉ phụ thuộc g (khối lượng m tự triệt tiêu) — từ đó đọc slope trên đồ thị là suy ra được g ngay, không cần biết m. Đây là minh chứng rõ nhất cho quy trình 5 bước trên: một đồ thị "lạ" luôn giải được bằng cách quay về biến gốc rồi khử tham số, không cần "nhìn ra" mẹo.

---

### 3.4 Rơi tự do & Ném thẳng đứng

**Bước 1:** Chọn 1 trục duy nhất (đề xuất: chiều dương = chiều ném/rơi ban đầu để đơn giản dấu).

**Bước 2:** Viết y(t) = y₀ + v₀t ± ½gt² và v(t) = v₀ ± gt (dấu theo quy ước đã chọn ở Bước 1).

**Bước 3 — tra Bảng B để lấy phương trình sự kiện**, các trường hợp chuẩn hay lặp lại:
- Đạt độ cao cực đại: v(t)=0 → t = v₀/g ; độ cao cực đại H = v₀²/(2g)
- Trở về điểm xuất phát: y(t)=y₀ → t = 2v₀/g
- Chạm đất (y=0, ném từ độ cao y₀): giải phương trình bậc hai, dùng Quy tắc chọn nghiệm ở Phần 4 (loại nghiệm t<0).
- Nếu đề cho dưới dạng đồ thị (v–t "chuẩn" → dùng 3.2; đồ thị "lạ" như P–S → dùng 3.3).

---

### 3.5a Bài toán đuổi kịp / gặp nhau (Pursuit)

**Bước 1:** Viết x₁(t), x₂(t) theo Master Algorithm, chú ý mốc thời gian nếu 2 vật xuất phát lệch nhau (tra Bảng A).

**Bước 2:** Điều kiện gặp nhau: x₁(t) = x₂(t) → giải ra t, thế ngược để có vị trí/quãng đường.

**⚠️ Bẫy cần nhớ máy móc — "tốc độ khép khoảng cách" (closing speed):** Nếu đề cho khoảng cách ban đầu d và thời gian đuổi kịp t, thì đại lượng **d/t KHÔNG PHẢI** là tốc độ của vật đuổi (hay vật bị đuổi) — nó là **tốc độ tương đối** (độ chênh giữa 2 tốc độ): d/t = |v_đuổi − v_bị_đuổi|. Đây là cụm từ đề thường "gài": một con số trông giống tốc độ tuyệt đối nhưng thực chất là hiệu 2 vận tốc. Quy tắc kiểm tra: hỏi "d/t vừa tính có phải là tốc độ CỦA MỘT VẬT CỤ THỂ hay không?" — nếu d là khoảng cách GIỮA hai vật, câu trả lời luôn là KHÔNG, đó là tốc độ tương đối.

*Ví dụ minh họa (số tự đặt):* Vật A cách vật B 12 km, A đuổi theo với tốc độ không đổi 48 km/h và đuổi kịp B sau 1 giờ. Số 12 km/1h = 12 km/h **không phải** tốc độ của B — nó là hiệu (v_A − v_B). Suy ra v_B = v_A − 12 = 36 km/h.

---

### 3.5b Đổi hệ quy chiếu (phép biến đổi Galileo)

**Công thức gốc duy nhất cần nhớ (mọi bài loại này chỉ là áp dụng lại công thức này):**
```
v(vật, đất) = v(vật, phương tiện) + v(phương tiện, đất)      [cộng vectơ, làm riêng từng thành phần x, y]
```

**Quy trình:**
1. Xác định rõ 2 hệ quy chiếu: hệ gắn với đất, hệ gắn với phương tiện đang chuyển động. Ghi vận tốc của phương tiện so với đất, V (đã biết).
2. Với vật đang xét (ví dụ quả bóng), gọi vận tốc của nó **so với phương tiện** là các ẩn cần tìm (thành phần ngang, dọc).
3. Dùng Bảng B để dịch mô tả quan sát ở MỖI hệ quy chiếu thành điều kiện về thành phần vận tốc trong hệ đó. Lưu ý: **thành phần thẳng đứng không đổi** giữa 2 hệ (vì phương tiện chỉ chuyển động ngang); chỉ **thành phần ngang** bị cộng thêm V khi đổi hệ.
4. Giải hệ phương trình (thường 1–2 phương trình, 1–2 ẩn) bằng công cụ Phần 4.
5. Từ vận tốc đã tìm được trong hệ quy chiếu mong muốn, áp dụng lại 3.4 hoặc 3.6 để trả lời phần còn lại của câu hỏi (độ cao cực đại, thời gian bay...).

*Ví dụ minh họa (dựng lại theo dạng đề thật, số tự đặt để minh họa quy trình):* Một học sinh trên toa tàu chạy thẳng đều với tốc độ V (so với đất) ném một quả bóng về phía sau toa; trong hệ quy chiếu toa tàu, bóng bay ra với góc α so với phương ngang. Người đứng dưới đất quan sát thấy bóng bay **thẳng đứng** — tra Bảng B: "bay theo phương thẳng đứng" → thành phần ngang của vận tốc bóng **trong hệ quy chiếu đất** bằng 0. Gọi tốc độ bóng trong hệ toa tàu là v: thành phần ngang trong hệ toa tàu là −v·cosα (ném về phía sau); theo công thức Galileo, thành phần ngang trong hệ đất = −v·cosα + V = 0 → v = V/cosα. Từ đó thành phần thẳng đứng (không đổi giữa 2 hệ) = v·sinα = V·tanα — đây chính là tốc độ ban đầu (thẳng đứng) mà người đứng dưới đất quan sát được, dùng tiếp cho 3.4 để tìm độ cao cực đại.

---

### 3.6 Chuyển động ném xiên (Projectile motion)

**Bước 1 — Phân tích ngay tại t=0:** v₀ₓ = v₀·cosα ; v₀ᵧ = v₀·sinα (α = góc so với phương ngang).

**Bước 2 — Viết 4 phương trình độc lập (ngang không có gia tốc, dọc có gia tốc g):**
```
x(t) = x₀ + v₀ₓ·t                    vₓ(t) = v₀ₓ  (không đổi)
y(t) = y₀ + v₀ᵧ·t − ½g·t²            vᵧ(t) = v₀ᵧ − g·t
```

**Bước 3 — Công thức phái sinh (chỉ cần áp dụng, không cần tự chứng minh lại mỗi lần):**
- Thời gian lên đỉnh: t_đỉnh = v₀ᵧ/g ; Độ cao cực đại: H = v₀ᵧ²/(2g)
- Thời gian bay (rơi lại **cùng độ cao xuất phát**): T = 2v₀ᵧ/g
- Tầm xa (chỉ khi rơi cùng độ cao xuất phát): R = v₀ₓ·T = v₀²·sin(2α)/g

**Bước 4 — Bẫy cần kiểm tra bắt buộc:** Nếu điểm rơi **khác độ cao** xuất phát (rơi từ vách núi, rơi lên dốc...), **KHÔNG được dùng công thức tầm xa R ở trên**. Quay lại Bước 2, thế y(t) = y_đích, giải phương trình bậc hai lấy t, rồi thế vào x(t).

**Bước 5 (nếu ném từ phương tiện đang chuyển động):** chạy 3.5b trước để có v₀ₓ, v₀ᵧ đúng trong hệ quy chiếu cần dùng, rồi mới áp dụng Bước 2–4.

---

### 3.7 Chuyển động tròn đều

**Bước 1 — Bảng quy đổi (chỉ cần thế số, không cần suy luận):**
```
ω = 2π/T = 2πf        v = ω·r        a_hướng_tâm = ω²·r = v²/r        s (cung) = r·θ (θ tính bằng radian)
```

**Bước 2:** Xác định đề cho **2 trong số** {T, f, ω, v, r, a} → dùng bảng quy đổi trên như một hệ phương trình đại số để suy ra các đại lượng còn lại.

**Bẫy hay gặp — sai số do bán kính thay đổi:** Nếu một thiết bị đo tốc độ dựa vào tốc độ quay của bánh xe (số vòng quay/thời gian, tức ω không đổi bản chất vật lý), nhưng bán kính bánh xe thực tế khác với bán kính lúc hiệu chỉnh thiết bị, thì: tốc độ hiển thị = ω·r_cũ (giả định), tốc độ thật = ω·r_mới. Vì ω giống nhau ở cả hai vế (cùng một bánh xe, cùng thời điểm), suy ra:
```
tốc độ thật / tốc độ hiển thị = r_mới / r_cũ
```
Đây là một biến thể thường gặp của 3.7, không phải một dạng bài mới — vẫn quy về đúng công thức v=ωr, chỉ khác ở việc nhận ra ω là đại lượng bất biến (invariant) nối hai phép tính.

---

### 3.8 Hình học Trái Đất tự quay (bài toán "đường chân trời")

Đây là dạng bài "lạ" nhất nhưng vẫn có một thuật toán hình học cố định, dùng lại cho **mọi biến thể** của bài toán này (đứng lên tăng độ cao mắt khi ngắm hoàng hôn, đo bán kính Trái Đất, v.v.):

**Bước 1 — Dựng tam giác vuông cố định:** Gọi O = tâm Trái Đất (bán kính R), E = vị trí mắt người quan sát (ở độ cao h so với mặt đất/mặt biển), T = điểm tiếp xúc giữa tia nhìn và mặt cầu (đường chân trời). Vì tia nhìn tiếp tuyến với mặt cầu tại T, ta có OT ⊥ ET → tam giác OTE vuông tại T, với OT = R, OE = R + h.

**Bước 2 — Công thức góc (luôn đúng, không cần chứng minh lại):**
```
cos θ = R / (R + h)
```
với θ = góc ở tâm O giữa phương thẳng đứng của người quan sát và phương tới điểm T (θ này cũng chính bằng "góc lệch xuống dưới đường chân ngang" nhìn từ mắt E).

**Bước 3 — Xấp xỉ góc nhỏ (luôn áp dụng được vì h ≪ R với mọi độ cao con người):**
```
θ ≈ √(2h / R)
```

**Bước 4 — Nối với thời gian qua tốc độ góc tự quay của Trái Đất:**
```
θ = ω_Trái_Đất · Δt        với ω_Trái_Đất = 2π / T_ngày   (T_ngày = 86 400 s, hằng số luôn dùng được dù đề không nhắc lại)
```

**Bước 5:** Kết hợp Bước 3 và Bước 4 thành một phương trình duy nhất: `√(2h/R) = (2π/86400)·Δt`. Ẩn nào đề cho thiếu (R, h, hay Δt) thì giải ra ẩn đó — thuật toán không đổi dù đề hỏi chiều nào.

**Ghi chú độ tổng quát:** Dù đề "kể chuyện" khác nhau (nằm trên bãi cát rồi đứng dậy, hay hai người đứng ở hai độ cao khác nhau cùng lúc), bản chất hình học luôn là **cùng một tam giác vuông** ở Bước 1 — chỉ khác cách gán h. Đây chính là ví dụ rõ nhất cho việc "một dạng bài trông có vẻ hiếm/lạ vẫn có algorithm đóng khung", miễn là ta luôn dựng đúng tam giác này trước khi làm gì khác.

---

### 3.9 Tổng hợp/phân tích chuyển động (bơi qua sông, bay có gió...)

Về bản chất đây vẫn là phép cộng vectơ Galileo (3.5b), nhưng có bộ câu hỏi chuẩn riêng đáng tách thành thuật toán con:

**Bước 1:** Gọi v₁ = vận tốc dòng nước/gió so với bờ (đã biết), v₂ = vận tốc bản thân vật so với dòng nước/gió (độ lớn thường đã biết, hướng là ẩn cần chọn), v = v₁ + v₂ = vận tốc thực so với bờ.

**Bước 2:** Dựng hệ trục: một trục dọc theo bờ (hoặc dọc dòng chảy), một trục vuông góc (bề rộng sông = d).

**Bước 3 — 3 câu hỏi chuẩn, mỗi câu có công thức cố định:**
- *"Thời gian ngắn nhất để qua sông"*: thời gian chỉ phụ thuộc thành phần vận tốc **vuông góc bờ**; để tối đa thành phần này, hướng v₂ **vuông góc hoàn toàn với bờ** → t_min = d / |v₂|.
- *"Sang đúng điểm đối diện (không bị trôi)"*: cần thành phần vận tốc **dọc bờ** của v triệt tiêu → |v₂|·sin(góc lệch so với phương vuông góc bờ) = |v₁| → giải ra góc. **Kiểm tra khả thi bắt buộc:** chỉ giải được nếu |v₂| > |v₁|; nếu không, đề vô nghiệm về mặt vật lý — phải báo rõ.
- *"Điểm chạm bờ bên kia lệch bao xa"*: t = d / (thành phần vuông góc bờ của v₂); độ lệch dọc bờ = (thành phần dọc bờ của v) × t — thế trực tiếp.

---

## PHẦN 4 — BỘ CÔNG CỤ GIẢI TOÁN (Solving Toolkit)

Sau khi Phần 2–3 đã biến đề thành phương trình, các bước sau là **thuần đại số**, không còn tính "vật lý", nên hoàn toàn công thức hóa:

1. **Phương trình bậc nhất:** giải trực tiếp.
2. **Phương trình bậc hai** at² + bt + c = 0: Δ = b² − 4ac ; t = (−b ± √Δ)/(2a).
   **Quy tắc chọn nghiệm (áp dụng máy móc, không đoán):**
   - Loại mọi nghiệm t < 0, trừ khi đề hỏi rõ về thời điểm **trước** gốc thời gian đã chọn.
   - Nếu cả hai nghiệm dương → quay lại Bảng B xem đề hỏi "1 thời điểm" hay "toàn bộ các thời điểm thỏa mãn" (ví dụ vật đi qua 1 độ cao cả lúc lên lẫn lúc xuống — cả 2 nghiệm đều là đáp án).
3. **Hệ 2 phương trình 2 ẩn** (hay gặp ở 3.5b, 3.9): ưu tiên phép thế nếu một phương trình đã cô lập sẵn 1 ẩn; dùng phép cộng/trừ nếu cả hai đối xứng.
4. **Khử tham số** (dùng ở 3.3): viết cả hai đại lượng cần khảo sát theo cùng một biến gốc, sau đó khử biến gốc bằng phép chia/thế.
5. **Kiểm tra cuối cùng (luôn luôn làm, không bỏ qua):**
   - Thứ nguyên/đơn vị của kết quả có đúng như đại lượng được hỏi không?
   - Độ lớn có hợp lý về mặt vật lý không? (ví dụ: tốc độ người > 50 m/s, bán kính Trái Đất < 1000 km... là dấu hiệu sai ở đâu đó)
   - Đơn vị đầu vào đã đồng nhất chưa (km/h vs m/s) — quy ước: luôn đổi hết về SI (m, s, kg) trước khi giải, trừ khi mọi đại lượng liên quan đều cùng một hệ đơn vị không-SI xuyên suốt bài.

---

## PHẦN 5 — QUY TRÌNH LUYỆN TẬP ĐỂ ALGORITHM TRỞ THÀNH PHẢN XẠ

Mục tiêu cuối: tổng thời gian làm 1 bài (đọc đề + giải) dưới 10–15 phút, trong đó bước "đọc đề" dưới 60 giây.

1. **Học thuộc lòng Bảng A và Bảng B** (Phần 2) đến mức phản xạ — có thể tự kiểm tra bằng cách che cột phải và tự nhớ lại.
2. **Luyện tách riêng bước đọc đề**: với mỗi đề luyện tập, chỉ bấm giờ và lập bảng dữ kiện + phương trình sự kiện, **chưa giải toán** — mục tiêu dưới 60 giây/đề dài, dưới 30 giây/đề ngắn.
3. **Luyện từng thuật toán con (3.1 → 3.9) riêng lẻ**, mỗi dạng tối thiểu 5–10 bài, cho đến khi áp dụng hoàn toàn máy móc, không còn phải "hiểu lại từ đầu vì sao công thức đúng".
4. **Luyện đề tổng hợp** (nhiều dạng trộn trong 1 đề, đúng cấu trúc đề thi thật): mục tiêu là luyện kỹ năng **routing** — nhận diện đúng thuật toán con nào cần dùng chỉ trong vài giây đầu đọc đề, đây là kỹ năng duy nhất còn mang tính "tốc độ nhận diện mẫu" chứ không phải "giải toán", nên luyện tách biệt với Bước 3.
5. Sau mỗi lần sai, **truy ngược lại xem sai ở bước nào trong 6 bước của Master Algorithm** (Phần 1) — không chấp nhận lý do mơ hồ kiểu "chưa quen dạng này".

---

*Tài liệu này chỉ bao phủ phần Kinematics (Động học chất điểm) theo đúng phạm vi đã xác định. Các dạng bài khác (điện học, công–năng lượng, ma sát...) nằm ngoài phạm vi tài liệu này và cần một bộ thuật toán riêng nếu cần.*
