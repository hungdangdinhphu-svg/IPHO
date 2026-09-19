# QUANG HỌC — THƯ VIỆN CÔNG CỤ & PRECONDITION
### Giải pháp cho Vấn đề 1 (nhận diện CÔNG CỤ) và Vấn đề 2 (chuyển Vật lý → Toán)
*Phạm vi: đúng 3 mục trong ảnh — **Quang hình**, **Sóng**, **Quang lí**. Đối tượng: HSGQG / VPhO / IPhO và nền tảng nghiên cứu.*

---

## PHẦN 0 — KHUNG VẬN HÀNH & TRỤC PHÂN LOẠI

Mỗi công cụ ℓ đóng gói thành thẻ 7 ô: **Dom / Pre / Suf / Post / Err / CHỖ-detector / Toán hoá**. Nhắc lại phân biệt sống còn: **Pre** = điều kiện để công cụ *đúng*; **Suf** = điều kiện để công cụ *giải ra được ẩn*. Độ khó nằm ở ô Suf.

**Đặc thù của Quang học (khác hẳn Điện từ):** mảng này có một cấu trúc phân tầng rất rõ, và nhận ra tầng là đã giải quyết được nửa Vấn đề 1.

```
Maxwell (đầy đủ)
   │  bỏ qua phân cực, coi vô hướng
   ▼
Quang lí (sóng vô hướng: giao thoa, nhiễu xạ)   ← λ so sánh được với kích thước
   │  λ → 0
   ▼
Quang hình (tia)                                 ← λ ≪ mọi kích thước
   │  góc → 0
   ▼
Quang cận trục (ma trận ABCD, công thức thấu kính)
```

**Ba trục để định vị mọi bài quang học:**

1. **Trục tỉ lệ λ/L.** So sánh bước sóng với kích thước đặc trưng (khe, lỗ, vật cản, sai lệch quang lộ).
   λ ≪ L ⇒ dùng tia. λ ~ L ⇒ **bắt buộc** dùng sóng. Đây là trục quyết định chọn Thẻ 1–6 hay Thẻ 11–13.
2. **Trục góc.** Góc mở lớn hay nhỏ so với trục chính? Nhỏ ⇒ cận trục ⇒ ma trận ABCD, công thức thấu kính. Lớn ⇒ phải dùng Snell/Fermat nguyên bản, và sẽ xuất hiện **quang sai / caustic**.
3. **Trục đồng nhất của môi trường.** n hằng theo từng miền ⇒ tia thẳng + khúc xạ tại mặt. n biến thiên liên tục ⇒ **bất biến Snell tổng quát / Bouguer** (Thẻ 5) — đây là mục "chiết suất thay đổi" trong ảnh.

**Nguyên tắc chuyển hoá tối quan trọng của cả tài liệu:**
> Trong Quang lí, **mọi** bài giao thoa/nhiễu xạ đều quy về việc tính một đại lượng duy nhất: **hiệu quang lộ δ** (hoặc độ lệch pha Δφ = 2πδ/λ). Sau khi có δ, bài đã hoàn toàn là bài Toán. Toàn bộ Vấn đề 2 của Quang lí = **tìm đúng δ**, kể cả các số hạng phụ (đảo pha π khi phản xạ, bản mỏng chèn vào, độ nghiêng).

---

# PHẦN I — QUANG HÌNH

---

### THẺ 1 — NGUYÊN LÍ FERMAT (công cụ gốc, đặt đầu tiên có chủ ý)

**Phát biểu.** Quang lộ L = ∫ n ds giữa hai điểm là **dừng** (stationary) đối với biến thiên nhỏ của đường đi: δ∫n ds = 0.

**Pre.** Xấp xỉ quang hình (λ → 0). Môi trường đẳng hướng (nếu bất đẳng hướng phải dùng dạng tổng quát hơn).

> **Bẫy phát biểu:** Fermat **không** nói "thời gian ngắn nhất". Nó nói **dừng**. Trong gương cầu lõm, đường đi qua tiêu điểm có thể là **cực đại**. Ở điểm tạo ảnh hoàn hảo (stigmat), mọi đường đều có L **bằng nhau** — cực trị suy biến.

**Suf — ba cách khai thác, mỗi cách là một CHỖ:**

**(a) Suy ra định luật.** Đặt hàm quang lộ theo một tham số tự do rồi cho đạo hàm bằng 0 ⇒ ra định luật phản xạ và Snell. Dùng khi đề hỏi chứng minh, hoặc khi hình học lạ mà không nhớ công thức.

**(b) Điều kiện tạo ảnh hoàn hảo (stigmatism) — cực kỳ mạnh.**
> Hai điểm A, A′ là ảnh hoàn hảo của nhau ⟺ **quang lộ dọc mọi tia nối A và A′ đều bằng nhau**.

Từ một dòng này suy ra được: dạng mặt phản xạ là ellipse/parabol/hyperbol; ovan Descartes; và đặc biệt — **công thức thấu kính mỏng** bằng cách so sánh quang lộ tia trục (qua bề dày kính) với tia rìa (qua không khí). Dùng khi bài yêu cầu thiết kế mặt hoặc khi hệ không cận trục.

**(c) Đưa về bài biến phân.** Với n = n(x,y), đặt "Lagrangian" quang học
> 𝓛(y, y′, x) = n(x,y)·√(1 + y′²)

rồi áp Euler–Lagrange. Hai hệ quả then chốt là nguồn gốc của mọi bất biến ở Thẻ 5:
- 𝓛 không phụ thuộc x (tức n = n(y)) ⇒ hằng số Beltrami ⇒ **n sinθ = const** (Snell tổng quát cho môi trường phân lớp).
- Đối xứng quay (n = n(r)) ⇒ "mômen động lượng quang học" bảo toàn ⇒ **n(r)·r·sinφ = const** (bất biến Bouguer).

**Post.** Một phương trình đại số (cách a), một đẳng thức quang lộ (cách b), hoặc một ODE / một bất biến chuyển động (cách c).

**Toán hoá.** Bài tối ưu một biến; hoặc bài biến phân → ODE bậc 2, thường hạ bậc được nhờ bất biến.

---

### THẺ 2 — TRUYỀN THẲNG & PHẢN XẠ

**Nội dung.** Trong môi trường đồng nhất, tia là đường thẳng. Phản xạ: i = i′, tia tới – pháp tuyến – tia phản xạ đồng phẳng.

**Suf / Kỹ thuật cốt lõi — "duỗi thẳng" (unfolding):**
> Thay vì theo dõi tia gãy khúc qua nhiều lần phản xạ, hãy **lấy đối xứng bản thân hệ gương** qua mỗi mặt gương. Khi đó tia trở thành **một đường thẳng duy nhất** trong không gian ảnh lặp.

Đây là công cụ biến bài "phản xạ nhiều lần trong ống / trong góc nhị diện / trong hộp gương" từ hình học rối rắm thành bài **đường thẳng cắt lưới**, tức là thành số học thuần tuý. Rất hay xuất hiện ở HSGQG.

**Các kết quả cơ học cần thuộc:**
- Ảnh qua gương phẳng = **phép đối xứng gương**; ảnh ảo, đối xứng, cùng kích thước.
- Gương quay góc α (trục nằm trong mặt gương) ⇒ tia phản xạ quay **2α**. Hệ quả: gương gắn trên dây treo xoắn → đòn bẩy quang học, dùng đo góc nhỏ.
- Hợp hai phép đối xứng qua hai gương hợp góc α = **phép quay góc 2α** ⇒ số ảnh = 360°/α − 1 (khi 360°/α nguyên).
- Gương quay quanh trục với tốc độ Ω ⇒ vết sáng trên màn cách R chạy với tốc độ 2ΩR — chuyển thẳng sang bài động học.

**CHỖ-detector.** (1) Mọi nguồn sáng + mọi mép vật cản → một tia biên → tam giác đồng dạng (bóng tối, nửa tối, camera lỗ kim, nhật thực). (2) Mọi mặt gương → một phép đối xứng → áp dụng duỗi thẳng. (3) Mọi gương chuyển động → đạo hàm theo thời gian.

**Toán hoá.** Tam giác đồng dạng (tỉ lệ thức), hoặc hình học phép biến hình, hoặc phương trình đường thẳng.

---

### THẺ 3 — KHÚC XẠ: LƯỠNG CHẤT PHẲNG, BẢN MẶT SONG SONG, LĂNG KÍNH

**Định luật.** n₁ sin i₁ = n₂ sin i₂.

**Phát biểu sâu hơn (nên dùng ở trình độ cao):** thành phần **tiếp tuyến của vector sóng k được bảo toàn** qua mặt phân cách: k₁ₜ = k₂ₜ. Cách phát biểu này mở rộng tự nhiên sang nhiều mặt, sang môi trường phân lớp, và sang cách tử.

**Pre.** Hai môi trường đồng nhất, đẳng hướng, mặt phân cách nhẵn ở quy mô λ; ánh sáng đơn sắc (nếu không → tán sắc, n = n(λ)).

**Phản xạ toàn phần.** sin i_gh = n₂/n₁ (n₁ > n₂). Là **điều kiện dạng bất đẳng thức** — luôn phải kiểm tra, vì rất nhiều bài HSGQG có bẫy "tia không ló ra được".

**(a) Lưỡng chất phẳng.** Với tia **cận trục**: độ sâu biểu kiến d′ = d·(n₂/n₁).
> **Err quan trọng:** công thức này **chỉ đúng cận trục**. Với tia xiên, các tia không cắt nhau tại một điểm ⇒ ảnh bị loạn thị, bao hình các tia tạo thành **caustic**. Bài IPhO hay khai thác đúng chỗ này.

**(b) Bản mặt song song bề dày e.** Tia ló **song song** tia tới (đây là bất biến, hệ quả trực tiếp của k_t bảo toàn). Độ dịch ngang:
> d = e·sin(i − r)/cos r , với sin i = n sin r

Với góc nhỏ: d ≈ e·i·(n−1)/n. Ảnh dịch dọc theo trục một đoạn **e(1 − 1/n)** (lại chỉ đúng cận trục). **Quang lộ tăng thêm (n−1)e** — ghi nhớ số này, nó là cầu nối sang Thẻ 11 (bản mỏng chèn vào một nhánh giao thoa).

**(c) Lăng kính góc chiết quang A.**
- Hệ bốn phương trình: sin i₁ = n sin r₁ ; r₁ + r₂ = A ; sin i₂ = n sin r₂ ; **D = i₁ + i₂ − A**.
- Góc lệch cực tiểu khi **i₁ = i₂** (đối xứng — chứng minh bằng tính thuận nghịch của đường truyền hoặc dD/di₁ = 0):
  **n = sin((A + D_min)/2) / sin(A/2)** — công thức đo chiết suất.
- Góc nhỏ (A nhỏ, tia gần vuông góc): **D ≈ (n − 1)A**. Đây là dạng dùng cho lưỡng lăng kính Fresnel ở Thẻ 11.
- Điều kiện có tia ló: A ≤ 2·i_gh.
- Tán sắc: góc lệch chênh ΔD = A·Δn — nối sang bài quang phổ.

**CHỖ-detector cho toàn Thẻ 3.** Duyệt **từng mặt phân cách** theo thứ tự tia gặp. Tại mỗi mặt viết: (i) Snell, (ii) kiểm tra bất đẳng thức phản xạ toàn phần, (iii) quan hệ hình học giữa góc khúc xạ mặt này và góc tới mặt sau (thường là r₁ + r₂ = A, hoặc r₂ = r₁ nếu hai mặt song song). Đủ ba loại này là hệ đã đóng kín.

**Toán hoá.** Hệ phương trình lượng giác; bài cực trị → đạo hàm hoặc lập luận đối xứng; bài điều kiện ló → bất phương trình lượng giác.

---

### THẺ 4 — GƯƠNG CẦU, LƯỠNG CHẤT CẦU, THẤU KÍNH — HỢP NHẤT

**Nhận định hợp nhất (giảm tải trí nhớ mạnh nhất của mảng Quang hình):**
> Gương cầu lồi, gương cầu lõm, lưỡng chất cầu, thấu kính mỏng, thấu kính dày, hệ ghép — **tất cả** là trường hợp riêng của **một** công thức khúc xạ qua mặt cầu, hoặc tương đương, của **một** phép nhân ma trận.

**Công thức mẹ — khúc xạ qua một mặt cầu bán kính R:**
> **n₂/d′ − n₁/d = (n₂ − n₁)/R**  (quy ước dấu Descartes, chiều dương theo chiều truyền)

Từ đó:
- **Gương cầu**: đặt n₂ = −n₁ ⇒ 1/d + 1/d′ = 2/R = 1/f, với **f = R/2**. Lõm: f > 0. Lồi: f < 0.
- **Thấu kính mỏng**: ghép hai mặt cầu ⇒ **1/f = (n − 1)(1/R₁ − 1/R₂)**; nếu đặt trong môi trường chiết suất n_mt thì thay (n−1) → (n/n_mt − 1). Đây là chỗ bẫy kinh điển: **thấu kính hội tụ nhúng trong chất lỏng chiết suất lớn hơn sẽ thành phân kì.**
- Công thức chính: 1/d + 1/d′ = 1/f ; k = −d′/d ; **công thức Newton x·x′ = f²** (đo từ tiêu điểm) — dạng Newton giải nhanh hơn nhiều với bài "dịch vật một đoạn, ảnh dịch bao nhiêu".

**Pre chung (cực quan trọng).** **Xấp xỉ cận trục**: sin θ ≈ tan θ ≈ θ. Nghĩa là góc mở nhỏ, tia gần trục chính, vật nhỏ.
**Err:** sai số bậc ba. Khai triển sin θ = θ − θ³/6 sinh ra **quang sai cầu**; ngoài ra có coma, loạn thị, cong trường, méo, và **sắc sai** (do n = n(λ)). Nếu đề cho "chùm rộng" hoặc "tia đi sát mép" thì Pre bị vi phạm ⇒ phải quay về Snell nguyên bản ⇒ xuất hiện **caustic**.

#### Công cụ hạng nặng: MA TRẬN TRUYỀN TIA (ABCD)

Đây là "Nodal Analysis của Quang học" — thuật toán thuần, gần như không cần trực giác, dùng được bằng tay. **Nên đẩy mạnh cho HSGQG/IPhO.**

Trạng thái tia tại một mặt phẳng: vector (y, n·u) với y = khoảng cách tới trục, u = góc nghiêng. (Dùng tích nu, gọi là "góc rút gọn", để ma trận có định thức = 1.)

| Phần tử | Ma trận |
|---|---|
| Truyền một đoạn d trong môi trường n | [[1, d/n], [0, 1]] |
| Khúc xạ qua mặt cầu R (n₁ → n₂) | [[1, 0], [−(n₂−n₁)/R, 1]] |
| Thấu kính mỏng f | [[1, 0], [−1/f, 1]] |
| Gương cầu R | [[1, 0], [−2/R, 1]] |

**Quy tắc:** ma trận hệ M = (ma trận phần tử cuối)·…·(ma trận phần tử đầu) — **nhân ngược thứ tự tia gặp**. Luôn có det M = 1.

**Đọc kết quả từ M = [[A, B], [C, D]]:**
- **B = 0** ⟺ hai mặt phẳng đang xét là **mặt vật và mặt ảnh liên hợp**. ⇒ Đây chính là "phương trình tạo ảnh" cho hệ phức tạp tuỳ ý.
- Khi B = 0: độ phóng đại dài **m = A**.
- **C = −1/f** (tiêu cự tương đương của cả hệ).
- **A = 0** ⇒ mặt phẳng tới là tiêu diện trước; **D = 0** ⇒ mặt phẳng ra là tiêu diện sau.

**Vì sao đây là lời giải cho Vấn đề 2:** bài "hệ ba thấu kính và một gương, tìm vị trí ảnh cuối" vốn đòi hỏi truy vết ảnh qua từng phần tử với vô số bẫy dấu, nay trở thành **nhân bốn ma trận 2×2 rồi giải B = 0** — một phương trình đại số. Không còn trực giác nào cần thiết.

**Bất biến Lagrange–Helmholtz (kiểm tra & tính nhanh):**
> n·y·u = n′·y′·u′ = const qua toàn hệ

Dùng để: tính ngay độ phóng đại góc từ độ phóng đại dài (γ = 1/m khi n = n′); chứng minh không thể vừa phóng to vừa tăng góc; và là dạng quang học của **bảo toàn étendue** — giới hạn vật lý của mọi hệ tập trung ánh sáng.

**CHỖ-detector.** Đi dọc trục quang, mỗi lần gặp: mặt cong → ma trận khúc xạ; khoảng trống → ma trận tịnh tiến; gương → ma trận gương và **đảo chiều trục** (hoặc duỗi thẳng như Thẻ 2). Liệt kê hết, nhân lại. Không bỏ sót phần tử nào là đã đóng kín mô hình.

---

### THẺ 5 — TIA TRONG MÔI TRƯỜNG CHIẾT SUẤT BIẾN THIÊN (GRIN)

Đây là mục "bản mặt song song và khối trụ, cầu" trong ảnh — và là mục mà học sinh thường không có công cụ, phải mò. Thực ra nó có **thuật toán sạch**.

**Nguyên lí vận hành:** không đi theo từng lần khúc xạ. Thay vào đó, **tìm bất biến ứng với đối xứng của n**, rồi tích phân. Đây đúng là tinh thần "tìm CHỖ thoả precondition": precondition ở đây là **một phép đối xứng của trường chiết suất**.

**Ba bất biến — phủ gần như toàn bộ đề thi:**

| Đối xứng của n | Bất biến | Dùng cho |
|---|---|---|
| n = n(z), phân lớp phẳng (bản mặt song song, khí quyển) | **n(z)·sin θ(z) = const**, θ đo từ pháp tuyến các lớp | ảo ảnh sa mạc, ảo ảnh biển, khúc xạ khí quyển, sợi quang bản phẳng |
| n = n(r), đối xứng **trụ** | **n(r)·r·sin φ(r) = const** (Bouguer), φ = góc giữa tia và bán kính | sợi quang GRIN, khối trụ |
| n = n(r), đối xứng **cầu** | **n(r)·r·sin φ(r) = const** (tia nằm trong mặt phẳng qua tâm) | thấu kính Luneburg, khí quyển hành tinh, "cá vàng Maxwell" |

**Cách sinh ra bất biến (không cần học thuộc):** lấy giới hạn liên tục của Snell qua các lớp mỏng, hoặc dùng Euler–Lagrange với 𝓛 = n√(1+y′²) và nhận ra biến cyclic (Thẻ 1c).

**Phép tương tự cơ học — cầu nối cho phép mượn toàn bộ công cụ Cơ:**
> Quỹ đạo tia sáng trong môi trường n(**r**) **trùng** với quỹ đạo hạt chuyển động trong thế năng U(**r**) = −n²(**r**)/2 với cơ năng toàn phần bằng 0.

Hệ quả: Bouguer ⟺ bảo toàn mômen động lượng; bài tia trong khối cầu GRIN trở thành bài chuyển động trong trường xuyên tâm, dùng được phương trình quỹ đạo và thế năng hiệu dụng.

**Công thức bán kính cong (tính nhanh, rất hay dùng):**
> 1/ρ = (1/n)·|∇⊥n|  — với ∇⊥n là thành phần gradient chiết suất **vuông góc** với tia.
>
> Hệ quả định tính: **tia luôn cong về phía chiết suất lớn hơn.** Đây là một câu để giải thích mọi ảo ảnh mà không cần tính.

**Toán hoá.** Từ bất biến, tách biến ngay:
- Phân lớp phẳng: dz/dx = cot θ, với sin θ = C/n(z) ⇒ x = ∫ dz/√((n(z)/C)² − 1).
- Đối xứng xuyên tâm: dθ/dr = C/(r√(n²r² − C²)) ⇒ tích phân quỹ đạo.
Kết quả là một **tích phân xác định** — bài toán đã hoàn toàn thuộc Vấn đề 3.
*Ví dụ chuẩn:* n²(z) = n₀²(1 + az) ⇒ quỹ đạo là **parabol**; n(z) tuyến tính với a nhỏ ⇒ **cung tròn** bán kính ρ = n/|dn/dz|.

**Err.** Xấp xỉ quang hình đòi hỏi n biến thiên chậm trên thang λ: |∇n|·λ/n ≪ 1. Nếu không, phải dùng sóng (bài toán lớp phản xạ, sóng tiến hoá).

---

### THẺ 6 — MẮT VÀ DỤNG CỤ QUANG HỌC

**Nguyên lí thống nhất:** mọi dụng cụ đều là một hệ cận trục (Thẻ 4) **cộng thêm hai ràng buộc sinh lý**:
1. Ảnh cuối cùng phải nằm trong **khoảng nhìn rõ** [C_c, C_v] của mắt (điều kiện dạng **bất đẳng thức**).
2. "Độ lợi" luôn được định nghĩa qua **góc trông**, không phải kích thước: **G = tan α / tan α₀**.

> **CHỖ sai phổ biến nhất của mảng này:** lấy tỉ số chiều cao ảnh/vật thay vì tỉ số góc trông. Với kính lúp và kính hiển vi, vật đứng yên nên hai cách khác nhau hoàn toàn.

**Mắt.** Hệ hội tụ với **khoảng cách tới màn (võng mạc) cố định** ⇒ điều tiết = **thay đổi f**, khác hẳn máy ảnh (f cố định, dịch màn). Độ tụ điều tiết: D_max − D_min = 1/OC_c − 1/OC_v.
- Cận thị: OC_v hữu hạn ⇒ kính phân kì, đeo sát mắt f = −OC_v.
- Viễn thị / lão thị: kính hội tụ đưa vật ở Đ = 25 cm về điểm cực cận.
- Kính đặt cách mắt đoạn ℓ ⇒ phải trừ ℓ trong mọi khoảng cách. Đây là bẫy dấu hay gặp.

**Các số bội giác (ngắm chừng ở vô cực):**
| Dụng cụ | G∞ |
|---|---|
| Kính lúp | Đ/f |
| Kính hiển vi | δ·Đ/(f₁f₂), δ = độ dài quang học (khoảng cách hai tiêu điểm trong) |
| Kính thiên văn khúc xạ | f_vật/f_thị |

Ngắm chừng ở cực cận: G_c = |k| (độ phóng đại ảnh, khi ảnh hiện ở C_c).

**Cầu nối bắt buộc sang Quang lí:** chất lượng dụng cụ **không** bị giới hạn bởi quang hình mà bởi **nhiễu xạ**:
> Giới hạn Rayleigh: θ_min = **1,22 λ/D**

⇒ kính thiên văn lớn không phải để "phóng to" mà để **tăng năng suất phân giải và thu quang thông**. Bất kỳ bài nào hỏi "có nhìn tách được hai ngôi sao không" đều phải dùng công thức này chứ không phải G.

**Toán hoá.** Chuỗi ma trận ABCD (hoặc chuỗi công thức thấu kính) + **hệ bất phương trình** từ khoảng nhìn rõ và từ trường nhìn ⇒ bài toán miền nghiệm.

---

# PHẦN II — SÓNG

---

### THẺ 7 — PHƯƠNG TRÌNH SÓNG & BIỂU DIỄN

**Phương trình.** ∂²u/∂t² = v²·∂²u/∂x². **Nghiệm D'Alembert**: u = f(x − vt) + g(x + vt) — mọi hình dạng đều truyền không đổi dạng (Pre: môi trường không tán sắc, tuyến tính).

**Sóng điều hoà.** u = A cos(ωt − kx + φ₀), k = 2π/λ, v = ω/k = λf.
**Biểu diễn phức** u = Re[A e^{i(ωt−kx)}] — bắt buộc dùng khi tổng hợp nhiều sóng; biến lượng giác thành đại số.

**Suy giảm biên độ theo hình học (Pre thường bị quên):**
- Sóng phẳng: A = const
- Sóng trụ (gợn nước từ nguồn điểm trên mặt): **A ∝ 1/√r**
- Sóng cầu (âm, ánh sáng trong không gian): **A ∝ 1/r**, do đó **I ∝ 1/r²**
> Bài "giao thoa sóng mặt nước" nếu hỏi **biên độ tại một điểm** thì phải dùng A ∝ 1/√r; nếu chỉ hỏi **cực đại/cực tiểu ở đâu** thì chỉ cần hiệu đường đi. Phân biệt hai loại câu hỏi này là một CHỖ quan trọng.

**Tốc độ truyền (bảng để nhận dạng loại môi trường):**
dây căng √(T/μ) · âm trong khí √(γRT/M) · âm trong rắn √(E/ρ) · sóng điện từ 1/√(εμ) · sóng nước sâu √(gλ/2π) (tán sắc!) · nước nông √(gh)

**Vận tốc pha và vận tốc nhóm.** v_p = ω/k, **v_g = dω/dk**. Pre để phân biệt: môi trường **tán sắc** (ω không tỉ lệ k). Năng lượng và tín hiệu đi với v_g. Xuất hiện trong bài sóng nước sâu và ánh sáng trong môi trường tán sắc.

**Toán hoá.** PDE → tách biến hoặc D'Alembert; sóng điều hoà → đại số phức.

---

### THẺ 8 — PHẢN XẠ SÓNG, SÓNG DỪNG

**Điều kiện biên (đây chính là "tập A" của mảng sóng — hữu hạn và rất nhỏ):**
- Đầu **cố định** (biên cứng): u = 0 ⇒ sóng phản xạ **đảo pha π**.
- Đầu **tự do**: ∂u/∂x = 0 ⇒ **không đảo pha**.

**Công cụ nâng cao — trở kháng sóng.** Z = ρv (hoặc √(μT) cho dây):
> r = (Z₁ − Z₂)/(Z₁ + Z₂) , t = 2Z₁/(Z₁ + Z₂)

Bao trùm cả hai trường hợp trên như giới hạn (Z₂ → ∞ là biên cứng, Z₂ → 0 là tự do). Cho phép xử lý bài "hai dây khác nhau nối vào nhau", và **hoàn toàn song song với công thức phản xạ ánh sáng ở mặt phân cách** — nên học chung một lần.

**Sóng dừng.** Chồng hai sóng ngược chiều: u = 2A sin(kx)·cos(ωt). Nút cách nhau λ/2; nút và bụng kề nhau cách λ/4.
- Hai đầu cố định (hoặc hai đầu tự do): **L = k·λ/2** ⇒ f_k = k·v/2L (đủ mọi hoạ âm)
- Một đầu cố định, một đầu tự do (ống sáo một đầu kín): **L = (2k+1)·λ/4** ⇒ chỉ có hoạ âm **lẻ**

**CHỖ-detector.** Mỗi đầu/mỗi mặt phân cách → một điều kiện biên → một phương trình cho **tần số riêng**. Số điều kiện biên đúng bằng số cần thiết để đóng kín.

**Toán hoá.** Bài toán trị riêng (eigenvalue): điều kiện biên → phương trình lượng giác cho k → dãy tần số rời rạc.

---

### THẺ 9 — TỔNG HỢP DAO ĐỘNG & GIAO THOA SÓNG

**Công cụ 1 — Giản đồ Fresnel / số phức.** Mỗi dao động điều hoà cùng tần số ↔ một vector (hoặc số phức A e^{iφ}). Tổng hợp = **cộng vector**.
> A² = A₁² + A₂² + 2A₁A₂cos Δφ ; tan φ = (ΣA_i sin φ_i)/(ΣA_i cos φ_i)

**Pre:** cùng tần số. Nếu khác tần số ⇒ không dùng được, phải xét **phách** (beat) f_phách = |f₁ − f₂|.

**Công cụ 2 — Điều kiện giao thoa.** Với hai nguồn kết hợp:
> Δφ = 2π·(d₂ − d₁)/λ + (φ₂ − φ₁)

- Hai nguồn **cùng pha**: cực đại khi d₂ − d₁ = kλ; cực tiểu khi = (k + ½)λ
- Hai nguồn **ngược pha**: đảo lại toàn bộ (đây là chỗ sai nhiều, phải kiểm tra pha nguồn trước khi viết)

**Bài toán sóng mặt nước — quy trình máy móc:**
1. **Hình học của vân:** tập điểm có d₂ − d₁ = const là một nhánh **hypebol** nhận hai nguồn làm tiêu điểm. Tập điểm có d₁ + d₂ = const là **elip**.
2. **Đếm số cực đại/cực tiểu** trên đoạn nối hai nguồn AB: từ −AB < kλ < AB ⇒ **−AB/λ < k < AB/λ**, đếm số nguyên k. (Với nguồn ngược pha thì thay k bằng k + ½.)
3. **Đếm trên một đường bất kỳ:** tính d₂ − d₁ tại hai đầu đường đó → lấy khoảng giá trị → đếm số nguyên trong khoảng. Đây là thuật toán tổng quát, thay cho việc vẽ hình mò.
4. **Điểm dao động cùng pha với nguồn:** cần **đồng thời** d₂ − d₁ = kλ (để cực đại) **và** d₁ + d₂ = mλ (để cùng pha với nguồn). Hai điều kiện ⇒ giao của một hypebol và một elip ⇒ hệ hai phương trình. Đây là CHỖ mà nhiều học sinh chỉ viết một điều kiện rồi sai.
5. **Điểm cực đại gần nhất/xa nhất trên một đường:** biến bài thành **tối ưu hình học** có ràng buộc số nguyên — chọn k biên rồi giải.

**Toán hoá.** Bất phương trình với ẩn nguyên k; hệ phương trình hình học giải tích (hypebol ∩ đường thẳng/đường tròn/elip).

---

### THẺ 10 — ĐIỆN TỪ TRƯỜNG (sóng điện từ)

**Từ Maxwell ra sóng.** Trong chân không: ∇²**E** = μ₀ε₀ ∂²**E**/∂t² ⇒ **c = 1/√(μ₀ε₀)**. Trong môi trường: v = c/n, **n = √(ε_r μ_r)**.

**Cấu trúc sóng phẳng (mỗi tính chất là một ràng buộc dùng được):**
- **E** ⊥ **B** ⊥ **k**, bộ ba thuận; sóng **ngang**
- **E = cB** (độ lớn), dao động **cùng pha**
- Mật độ năng lượng chia đều giữa điện và từ: u = ε₀E²

**Dòng năng lượng — vector Poynting.** **S** = (**E** × **B**)/μ₀. Cường độ:
> I = ⟨S⟩ = **½ ε₀ c E₀²** = ½ c B₀²/μ₀

**Động lượng (cầu nối sang Thẻ 13).** Sóng mang động lượng với mật độ g = S/c². Với năng lượng U truyền tới một vật: **p = U/c** nếu hấp thụ hoàn toàn, **p = 2U/c** nếu phản xạ hoàn toàn.

**Phân cực.**
- **Định luật Malus:** I = I₀cos²θ (qua kính phân cực thứ hai). Ánh sáng tự nhiên qua kính đầu tiên: I = I₀/2.
- **Góc Brewster:** tan θ_B = n₂/n₁ ⇒ tia phản xạ phân cực toàn phần; khi đó **tia phản xạ ⊥ tia khúc xạ**.

**CHỖ-detector.** Mọi bài cho "công suất / cường độ bức xạ" → dùng I = ½ε₀cE₀² để ra E₀, B₀. Mọi bài "ánh sáng đập vào vật" → dùng p = U/c hoặc 2U/c. Mọi bài có kính phân cực → Malus theo chuỗi.

---

# PHẦN III — QUANG LÍ

---

### THẺ 11 — GIAO THOA HAI CHÙM: KHE YOUNG VÀ TOÀN BỘ HỌ THIẾT BỊ

**Nhận định hợp nhất (lời giải cho Vấn đề 2 của cả mục "giao thoa nâng cao"):**
> Lưỡng lăng kính Fresnel, bán thấu kính Billet, gương Lloyd, hai gương Fresnel, lưỡng thấu kính — **không phải là năm dạng bài**. Tất cả là **một** dạng: *hai nguồn kết hợp ảo cách nhau a, cách màn D*. Toàn bộ công việc riêng của từng thiết bị chỉ là **quang hình sơ cấp để tìm (a, D) và bề rộng vùng chồng chập**. Sau đó mọi thứ dùng chung:
>
> **i = λD/a** · vân sáng x = k·i · vân tối x = (k + ½)·i · số vân trên bề rộng ℓ: N = 2⌊ℓ/2i⌋ + 1

**Bảng tra (a, D) — đây là toàn bộ nội dung cần nhớ thêm:**

| Thiết bị | a (khoảng cách hai nguồn ảo) | D | Bề rộng vùng giao thoa | Ghi chú riêng |
|---|---|---|---|---|
| **Khe Young** | a cho sẵn | D | rộng | chuẩn |
| **Lưỡng lăng kính Fresnel** (góc A nhỏ, chiết suất n, nguồn cách d) | **a = 2d(n−1)A** | D = d + L | **ℓ = 2L(n−1)A** | mỗi nửa lệch góc (n−1)A về phía đáy |
| **Hai gương Fresnel** (hợp góc α nhỏ, nguồn cách giao tuyến d) | **a = 2dα** | D = d + L | ℓ = 2Lα | hai ảnh đối xứng qua hai gương |
| **Bán thấu kính Billet** (cắt đôi, tách ra đoạn e) | a = hai ảnh S₁, S₂ của S, tính bằng công thức thấu kính; a = e(1 + \|k\|) | D = từ ảnh tới màn | hữu hạn | phải tính d′ bằng 1/d+1/d′=1/f trước |
| **Gương Lloyd** (nguồn cách gương h) | **a = 2h** | D | nửa màn | **có đảo pha π** ⇒ vân **trung tâm là vân TỐI** |

> **Gương Lloyd là bài kiểm tra xem người học có thực sự hiểu δ hay chỉ thuộc công thức.** Phản xạ trên mặt có chiết suất lớn hơn thêm nửa bước sóng vào quang lộ ⇒ đảo toàn bộ hệ vân. Cùng logic với "lớp mỏng thêm λ/2".

**Hai phép biến đổi phải thuộc (hay ra để làm khó):**
- **Chèn bản mỏng** bề dày e, chiết suất n vào một nhánh ⇒ quang lộ nhánh đó tăng **(n−1)e** ⇒ hệ vân **dịch** đi x₀ = (n−1)e·D/a về phía nhánh có bản. Đây là cách đo n và cũng là nguyên lý giao thoa kế.
- **Dịch nguồn S** một đoạn δs vuông góc trục ⇒ hệ vân dịch **ngược chiều**, với tỉ lệ theo khoảng cách nguồn–khe và khe–màn.
- **Ánh sáng trắng:** vân trung tâm trắng, hai bên là quang phổ; vị trí x trùng nhiều bức xạ ⇒ điều kiện x = kλ D/a với λ ∈ [0,38; 0,76] μm ⇒ **bài đếm số nguyên trong một khoảng**.

**Pre — tính kết hợp (coherence), ô hay bị bỏ qua nhất:**
- **Kết hợp không gian:** hai nguồn phải là ảnh của **cùng một** nguồn gốc. Hai bóng đèn không bao giờ giao thoa. Nguồn có bề rộng b làm vân mờ đi khi b vượt quá một ngưỡng ~ λ·(khoảng cách nguồn–khe)/a.
- **Kết hợp thời gian:** hiệu quang lộ δ phải nhỏ hơn **độ dài kết hợp** L_c ≈ λ²/Δλ. Đây là lý do bậc vân cao bị mờ với nguồn không đơn sắc — một câu hỏi định tính rất hay ở IPhO.

**Giao thoa bản mỏng (họ con quan trọng):**
- Hiệu quang lộ hai tia phản xạ: **δ = 2nd·cos r + λ/2** (số hạng λ/2 xuất hiện khi chỉ một trong hai lần phản xạ là từ môi trường chiết quang kém sang chiết quang hơn).
- **Vân cùng độ dày** (d thay đổi, r cố định): nêm không khí, **vân tròn Newton** r_k = √(kλR).
- **Vân cùng độ nghiêng** (d cố định, r thay đổi): vân tròn ở vô cực.
- Màng chống phản xạ: d = λ/4n.

**Toán hoá.** Tính δ ⇒ phương trình δ = kλ hoặc (k+½)λ ⇒ phương trình bậc nhất hoặc bậc hai theo x, cộng bất phương trình giới hạn miền quan sát và giới hạn bậc k.

---

### THẺ 12 — GIAO THOA NHIỀU NGUỒN & NHIỄU XẠ

**Bài toán trung tâm:** N nguồn cùng biên độ A₀, cách đều, lệch pha kế tiếp một lượng φ không đổi. Đây là **tổng cấp số nhân phức** — và đó chính là chỗ chuyển sang Toán:
> Σ_{m=0}^{N−1} A₀ e^{imφ} = A₀·(1 − e^{iNφ})/(1 − e^{iφ}) ⇒ **A = A₀·|sin(Nφ/2)/sin(φ/2)|**
>
> **I = I₀·[sin(Nφ/2)/sin(φ/2)]²**

**Đọc cấu trúc kết quả (không cần vẽ đồ thị mò):**
- **Cực đại chính** khi φ = 2kπ, giá trị I = N²I₀ (biên độ N·A₀).
- Giữa hai cực đại chính liên tiếp: **N − 1 cực tiểu** (bằng 0) và **N − 2 cực đại phụ** (rất yếu).
- Bề rộng nửa cực đại chính ∝ 1/N ⇒ **N càng lớn vân càng sắc nét** — đây là nguyên lý của cách tử.

**Cách tử nhiễu xạ.** d sin θ = kλ. Số vạch trên mm ⇒ d. Bậc cực đại lớn nhất: k ≤ d/λ.
**Năng suất phân giải:** R = λ/Δλ = **k·N**.

**Nhiễu xạ qua một khe hẹp bề rộng a** (giới hạn liên tục của N → ∞):
> I = I₀·sinc²(πa sinθ/λ) ; **cực tiểu tại a sinθ = kλ (k ≠ 0)** ; bề rộng cực đại trung tâm = 2λ/a

**Nhiễu xạ qua lỗ tròn D:** cực tiểu đầu tiên tại sinθ = **1,22 λ/D** (đĩa Airy) — nối với Thẻ 6.

**Nguyên lý chồng chập của hai hiệu ứng (rất hay bị nhầm):**
> Ảnh giao thoa thực của hệ nhiều khe = **(thừa số giao thoa nhiều nguồn) × (thừa số nhiễu xạ một khe)**.
>
> Hệ quả: một số cực đại giao thoa bị **triệt tiêu** nếu rơi đúng vào cực tiểu nhiễu xạ (khi d/a là số nguyên). Câu hỏi "vân bậc mấy bị mất" khai thác đúng điểm này.

**Công cụ tổng quát nhất (dành cho IPhO):** nguyên lí **Huygens–Fresnel** dưới dạng tích phân
> U(P) ∝ ∫_khe e^{ikr}/r dS

Mọi công thức trên là trường hợp riêng đã tích phân sẵn. Khi đề cho khẩu độ lạ (khe hình tam giác, khe có bản mỏng che nửa, hai khe không đều), hãy quay về tích phân này. Với trường xa (Fraunhofer), tích phân trở thành **biến đổi Fourier của hàm khẩu độ** — đây là cách nhìn mạnh nhất và cũng là lý do mọi kết quả đều có dạng sinc.

**CHỖ-detector.** (1) Đếm số nguồn/khe → chọn công thức N nguồn hay một khe hay tích của cả hai. (2) Mỗi khẩu độ → viết hàm khẩu độ → tích phân Huygens–Fresnel nếu không khớp công thức sẵn. (3) Mọi câu hỏi "phân giải" → R = kN hoặc 1,22λ/D.

---

### THẺ 13 — ÁP SUẤT ÁNH SÁNG

**Công thức nền (suy từ Thẻ 10).** Với chùm cường độ I chiếu **vuông góc**:
> Hấp thụ hoàn toàn: **p = I/c** · Phản xạ hoàn toàn: **p = 2I/c** · Hệ số phản xạ ρ: **p = (1 + ρ)I/c**

**Chiếu xiên góc θ — CHỖ sai kinh điển.** Phải tách động lượng theo phương. Với mặt **phản xạ gương**, chỉ thành phần pháp tuyến đổi dấu:
> áp suất pháp tuyến = **2I cos²θ/c**

Hai thừa số cos: một do diện tích hình chiếu (thông lượng giảm), một do chiếu động lượng lên pháp tuyến. Học sinh thường chỉ viết một.

**Lực toàn phần.** Với nguồn công suất P chiếu hết lên vật: **F = P/c** (hấp thụ) hoặc **2P/c** (phản xạ). Với nguồn đẳng hướng công suất P ở khoảng cách r: I = P/4πr².

**Ba tình huống ra đề:**
1. **Cánh buồm mặt trời:** F_bức xạ = 2IA/c, so sánh với hấp dẫn ⇒ điều kiện diện tích/khối lượng.
2. **Hạt bụi trong hệ Mặt Trời:** cả lực bức xạ và lực hấp dẫn đều ∝ 1/r² ⇒ **r triệt tiêu**, tỉ số chỉ phụ thuộc kích thước hạt: F_rad/F_grav ∝ R²/R³ = **1/R** ⇒ có bán kính tới hạn, hạt nhỏ hơn bị đẩy khỏi hệ. Đây là bài rất đẹp, hay ra ở IPhO.
3. **Đo áp suất bằng cân xoắn (thí nghiệm Lebedev):** cân bằng mômen lực bức xạ với mômen xoắn.

**Góc nhìn photon (dùng khi bài hỏi số hạt).** E = hf = hc/λ, **p = h/λ = E/c**. Số photon mỗi giây: Ṅ = P/(hf). Lực = Ṅ·Δp. Hai cách nhìn (sóng và hạt) cho **cùng** kết quả — nên dùng cách nào tiện hơn.

**Toán hoá.** Cân bằng lực / cân bằng mômen (phương trình đại số); hoặc định lý động lượng dF = dp/dt; hoặc phương trình chuyển động với lực ∝ 1/r² ⇒ bài cơ học quen thuộc.

---

## PHẦN C — QUY TRÌNH DUYỆT TỔNG (Search Routine cho Quang học)

**Bước 0 — Dựng ontology.** Liệt kê: nguồn (điểm/rộng, đơn sắc/trắng, kết hợp hay không); các mặt (phẳng/cầu, phản xạ/khúc xạ); các môi trường (n hằng hay biến thiên); màn quan sát; người quan sát.

**Bước 1 — Chốt tầng lý thuyết bằng trục λ/L.** Nếu đề nhắc tới bước sóng, khe, vân, màu sắc, hay khoảng cách cỡ μm ⇒ **Quang lí**. Nếu chỉ có gương/thấu kính/lăng kính kích thước cm ⇒ **Quang hình**. Nếu có cả hai ⇒ quang hình để xác định vị trí nguồn ảo, quang lí để xử lý vân (đây đúng là cấu trúc của mọi bài "giao thoa nâng cao").

**Bước 2 — Đếm ẩn, đếm phương trình.** Chưa đủ phương trình nghĩa là còn CHỖ chưa duyệt.

**Bước 3 — Duyệt CHỖ theo danh mục cố định:**
- Mỗi **mặt phân cách** → Snell + kiểm tra phản xạ toàn phần + điều kiện hình học nối với mặt kế
- Mỗi **mặt gương** → phép đối xứng / duỗi thẳng
- Mỗi **phần tử cận trục** → một ma trận ABCD
- Mỗi **miền có n biến thiên** → nhận diện đối xứng → viết bất biến (n sinθ hoặc n r sinφ)
- Mỗi **cặp đường đi** tới cùng một điểm → tính **δ** (đừng quên: λ/2 do phản xạ, (n−1)e do bản mỏng, pha ban đầu của nguồn)
- Mỗi **khẩu độ** → thừa số nhiễu xạ
- Mỗi **biên của môi trường sóng** → một điều kiện biên → một tần số riêng
- Mỗi **bề mặt bị chiếu sáng** → áp suất bức xạ nếu đề hỏi về lực

**Bước 4 — Kiểm tra Pre.** Cận trục có thoả không? Nguồn có kết hợp không? Môi trường có tán sắc không? Vùng chồng chập có thực sự tồn tại không?

**Bước 5 — Kiểm tra biên & giới hạn.** Cho λ → 0 (phải về quang hình); cho N = 2 trong công thức N nguồn (phải về công thức Young); cho n → 1; cho R → ∞ (mặt cầu → mặt phẳng). Kiểm tra thứ nguyên. Kiểm tra dấu bằng lập luận vật lý (ảnh thật hay ảo, vân dịch về phía nào).

---

## PHẦN D — BẢNG TRA "DẤU HIỆU ĐỀ BÀI → CÔNG CỤ"

| Dấu hiệu trong đề | Công cụ gần như chắc chắn |
|---|---|
| "chứng minh định luật khúc xạ", "thiết kế mặt để hội tụ hoàn hảo" | Fermat, điều kiện quang lộ bằng nhau (Thẻ 1) |
| "phản xạ nhiều lần", "hai gương hợp góc", "ống gương" | Duỗi thẳng bằng phép đối xứng (Thẻ 2) |
| "bản mặt song song", "nhìn vật dưới nước" | Snell + xấp xỉ cận trục; nhớ e(1−1/n) và (n−1)e |
| "góc lệch cực tiểu", "đo chiết suất bằng lăng kính" | i₁ = i₂, công thức D_min (Thẻ 3) |
| "hệ nhiều thấu kính/gương", "ảnh cuối cùng ở đâu" | **Ma trận ABCD**, giải B = 0 (Thẻ 4) |
| "chiết suất phụ thuộc độ cao/bán kính", "ảo ảnh", "sợi quang" | Bất biến n sinθ = const hoặc Bouguer n r sinφ = const (Thẻ 5) |
| "kính lúp/hiển vi/thiên văn", "số bội giác" | G = tanα/tanα₀ + chuỗi ảnh + bất đẳng thức khoảng nhìn rõ (Thẻ 6) |
| "tách được hai ngôi sao không" | 1,22λ/D, **không phải** số bội giác |
| "hai nguồn trên mặt nước", "đếm số điểm dao động cực đại" | Hypebol + bất phương trình số nguyên (Thẻ 9) |
| "điểm cùng pha với nguồn" | **Hai** điều kiện đồng thời: hiệu và tổng đường đi |
| "một đầu cố định/tự do", "hoạ âm" | Điều kiện biên → trị riêng (Thẻ 8) |
| "lưỡng lăng kính / gương Fresnel / bán thấu kính Billet / gương Lloyd" | Quy về (a, D) rồi dùng i = λD/a (Thẻ 11) |
| "gương Lloyd" cụ thể | Nhớ đảo pha π ⇒ tâm là **vân tối** |
| "nhúng bản mỏng vào một nhánh" | Hệ vân dịch (n−1)eD/a |
| "ánh sáng trắng", "vân trùng nhau" | Đếm số nguyên k với λ ∈ [0,38; 0,76] μm |
| "cách tử", "N khe", "năng suất phân giải" | Tổng cấp số nhân phức; R = kN (Thẻ 12) |
| "vân giao thoa bị mất/triệt tiêu" | Tích của thừa số giao thoa và thừa số nhiễu xạ |
| "khẩu độ hình dạng lạ" | Tích phân Huygens–Fresnel / biến đổi Fourier |
| "lực do ánh sáng", "cánh buồm mặt trời", "hạt bụi bị đẩy" | p = (1+ρ)I/c; chú ý cos²θ khi xiên (Thẻ 13) |

---

## PHẦN E — DANH SÁCH BẪY (kiểm tra trước khi nộp)

1. Phát biểu Fermat là "thời gian ngắn nhất" thay vì "dừng".
2. Dùng công thức thấu kính/độ sâu biểu kiến cho chùm **rộng** (vi phạm Pre cận trục) mà không nói gì về quang sai.
3. Quên kiểm tra **phản xạ toàn phần** ⇒ kết luận có tia ló trong khi thực tế không có.
4. Thấu kính nhúng trong chất lỏng: quên thay (n − 1) → (n/n_mt − 1); hội tụ có thể thành phân kì.
5. Nhân ma trận ABCD **sai thứ tự** (phải nhân ngược với thứ tự tia gặp).
6. Với môi trường n biến thiên: cố gắng khúc xạ từng lớp thay vì dùng ngay bất biến.
7. Tính số bội giác bằng tỉ số kích thước thay vì tỉ số **góc trông**.
8. Quên khoảng cách từ kính tới mắt ℓ trong bài tật mắt.
9. Trong sóng mặt nước, tính **biên độ** mà quên A ∝ 1/√r.
10. Tính "điểm cùng pha với nguồn" mà chỉ dùng điều kiện hiệu đường đi (thiếu điều kiện tổng đường đi).
11. Quên **đảo pha π** ở gương Lloyd, ở phản xạ bản mỏng, ở biên cứng của sóng dây.
12. Dùng công thức i = λD/a mà quên kiểm tra **bề rộng vùng chồng chập** (lưỡng lăng kính và Billet chỉ giao thoa trong một dải hẹp).
13. Cho rằng hai nguồn sáng độc lập có thể giao thoa (vi phạm Pre kết hợp).
14. Với cách tử: quên điều kiện k ≤ d/λ ⇒ đưa ra bậc không tồn tại.
15. Chồng chập nhiễu xạ và giao thoa bằng phép **cộng** thay vì phép **nhân**.
16. Áp suất ánh sáng chiếu xiên: viết I cosθ/c thay vì 2I cos²θ/c.
17. Nhầm vận tốc pha với vận tốc nhóm trong môi trường tán sắc.

---

## PHẦN F — NHỮNG CHỖ CHƯA ĐẦY ĐỦ (trung thực về giới hạn)

Đây là bản khung mật độ cao, chưa phải bản đầy đủ. Những phần còn nợ:

- **Thẻ 4:** lý thuyết mặt phẳng chính / điểm nút cho hệ dày; phân tích quang sai bậc ba (Seidel) một cách định lượng; ghép ma trận cho hệ có gương (quy ước duỗi thẳng) mới nêu chứ chưa khai triển ví dụ.
- **Thẻ 5:** chưa dẫn xuất chi tiết phương trình tia dạng vector d(n d**r**/ds)/ds = ∇n, vốn là dạng tổng quát nhất; chưa xử lý trường hợp n bất đẳng hướng.
- **Thẻ 11–12:** chưa xử lý định lượng lý thuyết kết hợp (hàm tương quan, định lý Van Cittert–Zernike), và chưa khai triển nhiễu xạ Fresnel (trường gần, đới Fresnel, xoắn ốc Cornu) — phần này xuất hiện ở IPhO.
- **Thẻ 10:** công thức Fresnel đầy đủ cho hệ số phản xạ/truyền qua theo phân cực s và p mới nêu Brewster, chưa nêu r_s, r_p.
- **Chưa bao gồm:** lượng tử ánh sáng ngoài phần động lượng photon phục vụ Thẻ 13 (quang điện, Compton, mẫu nguyên tử), vì nằm ngoài 3 mục trong ảnh.
