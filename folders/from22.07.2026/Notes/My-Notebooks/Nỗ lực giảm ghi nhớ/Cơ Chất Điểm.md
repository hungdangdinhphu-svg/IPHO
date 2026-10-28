# HẠT GIỐNG (SEED) — CƠ CHẤT ĐIỂM
**Bộ kiến thức gốc tối thiểu để tái sinh toàn bộ công thức trong "Cơ chất điểm — Thư viện công cụ K/D/C/O"**

---

## 0. Ý tưởng và cách đọc file này

Thay vì nhớ ~70 công cụ (K1–K8, D1–D11, C1–C9, O1–O8) như các sự kiện rời rạc, file này tách chúng thành:

> **SEED = (toán nền) + (vật lý gốc) + (ba "máy sinh")**
> rồi **mọi công thức còn lại = SEED chạy qua một thao tác suy diễn ngắn, lặp lại.**

Nguyên tắc chọn SEED: một mục được đưa vào SEED **chỉ khi** nó không suy ra được từ phần còn lại của SEED (nó là tiên đề, định nghĩa, hoặc hằng số thực nghiệm), **và** nó được dùng lại ≥ 3 lần trong tài liệu gốc. Mọi công thức khác đều có một "đường suy diễn" (derivation path) ngắn ghi ở Phần C–F, dùng đúng các SEED này.

**Trung thực:** đây vẫn là *nén có tổ chức*, không phải "ghi nhớ 10 dòng thay vì 2000 dòng rồi suy ra mọi thứ trong đầu lúc thi". Một số công thức (đánh dấu 🔧) cần một **thủ thuật cụ thể** đi kèm — thủ thuật đó cũng được liệt kê như một SEED-nhỏ (Phần B) vì tự nó không "lộ ra" nếu chỉ biết Newton.

---

## PHẦN A. SEED-M — Nền toán học (coi là đã biết, không phải "học cơ")

Bạn không cần nhớ những thứ này như vật lý; chúng là ngôn ngữ. Nhưng chính **A3, A4, A5** là nơi 80% "phép màu" suy luận xảy ra, nên liệt kê tường minh:

| # | SEED-M | Nội dung | Dùng để suy ra |
|---|---|---|---|
| **A1** | Đạo hàm/tích phân 1 biến, quy tắc chuỗi | `d/dt`, `∫dt`, `d(fg)=f'g+fg'` | Mọi công thức động học |
| **A2** | Khai triển Taylor bậc 2 quanh điểm dừng | `f(x₀+δ) ≈ f(x₀) + f'(x₀)δ + ½f''(x₀)δ²` | Toàn bộ Phần Dao động (O1–O8) |
| **A3** | **Đạo hàm vector trong hệ cơ sở xoay** (then chốt nhất) | Nếu **e**_r, **e**_φ quay với tốc độ φ̇: `d**e**_r/dt = φ̇**e**_φ`, `d**e**_φ/dt = −φ̇**e**_r` | Toàn bộ tọa độ cực, (t,n), Coriolis/ly tâm, Binet |
| **A4** | ODE tuyến tính hệ số hằng, bậc 2 | Thử nghiệm `x = e^{rt}` → phương trình đặc trưng; nếu có vế phải điều hòa, thử `x = Xe^{iΩt}` | O1, O5, O6, O7 (toàn bộ dao động) |
| **A5** | Đổi biến `v dv = a dx` (quy tắc chuỗi áp cho vận tốc) | `a = dv/dt = (dv/dx)(dx/dt) = v dv/dx` | K2, mọi công thức "năng lượng từ lực" |
| **A6** | Tích phân tách biến bậc nhất | `dy/f(y) = g(t)dt` | K2 (a(t), a(v)), D5 (lực cản), D2 (capstan) |
| **A7** | Cực trị hàm 1 biến + biệt thức bậc hai (Δ) | `dF/dλ=0`; `aλ²+bλ+c=0` có nghiệm thực ⇔ `Δ≥0` | K8 (mọi bài "lớn nhất/nhỏ nhất") |
| **A8** | Tích/thương vector: `a·b`, `a×b`, và tính chất `(a×b)·c` | Chiếu lực, mô-men, diện tích quét | D6, C7, K5 |

**Ghi nhớ một câu cho A3 (quan trọng nhất):** *"Vector đơn vị quay thì đạo hàm của nó là chính nó xoay 90° nhân với tốc độ quay."* Từ một câu này suy ra **toàn bộ** cột "gia tốc hướng tâm/tiếp tuyến", "Coriolis", "ly tâm", tọa độ cực — không cần nhớ riêng từng công thức.

---

## PHẦN B. SEED-P — Vật lý gốc (phải nhớ, KHÔNG suy ra được từ đâu khác)

Đây là phần "thật sự phải thuộc lòng" — nén xuống còn **9 khối**:

### B1. Ba định luật Newton
- N1: tồn tại hệ quy chiếu quán tính.
- N2: **ΣF = dp/dt** (= m**a** khi m hằng).
- N3: **F**_AB = −**F**_BA, đặt lên **hai vật khác nhau**, cùng đường nối (dạng mạnh, cần cho C7).

### B2. Danh sách lực cấu thành (constitutive laws — thực nghiệm, không suy từ Newton)
| Lực | Công thức | Ghi chú |
|---|---|---|
| Trọng lực đều | **F** = m**g** | Xấp xỉ của hấp dẫn khi h ≪ R |
| Hấp dẫn | **F** = −GMm/r² **r̂** | Định luật gốc; trọng lực đều chỉ là trường hợp riêng |
| Đàn hồi (Hooke) | **F** = −k(l−l₀) dọc lò xo | Tuyến tính; giới hạn vật liệu |
| Ma sát | nghỉ: f ≤ μ_sN; trượt: f = μ_kN ngược **v**_tương đối | Mô hình Coulomb |
| Cản môi trường | F = −bv (tuyến tính) hoặc −cv² (bậc hai) | Hai mô hình thực nghiệm phổ biến nhất |
| Liên kết lý tưởng (N, T) | ⟂ hoặc dọc ràng buộc; **không sinh công nếu ràng buộc không đổi theo t** | Đây là *định nghĩa* của "nhẵn/nhẹ/không dãn", không phải định luật |

### B3. Hệ số hồi phục (định nghĩa thực nghiệm cho va chạm)
`e = −(v₂'−v₁')_n / (v₂−v₁)_n`, 0 ≤ e ≤ 1. **Không suy ra từ Newton** — đây là dữ liệu đo được bổ sung cho bài toán va chạm (vì va chạm thật có biến dạng vi mô ngoài phạm vi cơ chất điểm).

### B4. "Công thức vận chuyển" giữa hai hệ quy chiếu (Transport theorem)
Với hệ quay tốc độ **ω** (có thể suy từ A3 cho hệ cơ sở bất kỳ gắn với hệ quay, không chỉ (e_r,e_φ)):

> (d/dt)|_quán tính = (d/dt)|_quay + **ω** ×

Áp hai lần cho **r**, cộng **a₀** nếu gốc hệ quay cũng có gia tốc tịnh tiến, ta được:

> m**a**' = **F** − m**a**₀ − 2m**ω**×**v**' − m**ω**×(**ω**×**r**') [− m(dω/dt)×**r**' nếu ω đổi]

**Đây là SEED, không phải D9/D10 riêng** — D9 là trường hợp ω=0, D10 là trường hợp a₀=0. Chỉ cần nhớ **một** công thức vận chuyển này.

### B5. Thế năng là tích phân ngược của lực bảo toàn
Định nghĩa: **F** = −∇U ⇔ U(r) = −∫**F**·d**r** (đường đi bất kỳ, vì ∮F·dr=0). Đây **là một định nghĩa toán học áp cho lực bảo toàn**, không phải luật vật lý riêng — nhưng liệt kê ở đây vì là bản lề của toàn Phần C.

### B6. "Mỗi lực liên kết lý tưởng không sinh công ⇒ công ảo = 0" (nguyên lý D11)
Đây là một tiên đề độc lập (không suy từ N2 một mình) cho bài toán tĩnh.

### B7. Dữ kiện mô-men quán tính (chỉ dùng làm input, không chứng minh)
Thanh qua tâm: mL²/12; đĩa: mR²/2; vành: mR²; cầu đặc: 2mR²/5; định lý trục song song I=I_cm+md².
*(Không thuộc "lõi" chất điểm — chỉ cần khi bài cho con lắc vật lý/xoắn.)*

### B8. Hằng số hấp dẫn và các định luật Kepler ở dạng phát biểu (không phải suy ra, mà là một hệ quả đã biết của lực 1/r² — xem máy sinh E3)
Không cần nhớ thêm gì ngoài B2 (lực hấp dẫn) — ba định luật Kepler **suy ra được hết** từ B2 + máy sinh (Phần C).

### B9. "Giảm biên độ tuyến tính cho ma sát khô" là hệ quả của B1+B2, không phải seed riêng — đã gộp, không cần nhớ thêm.

**→ Tổng SEED-P thực sự độc lập: N1,N2,N3 (B1) + 6 dòng lực (B2) + định nghĩa e (B3) + công thức vận chuyển (B4) + định nghĩa U (B5) + công ảo = 0 (B6).**
Đó là **toàn bộ vật lý** bạn phải nhớ. Mọi thứ còn lại trong 2000+ dòng gốc là suy luận.

---

## PHẦN C. BA "MÁY SINH" TRUNG TÂM (nơi phần lớn công thức được tạo ra)

### MÁY SINH 1 — "Tích phân Newton theo ba cách" → sinh ra TOÀN BỘ Phần C (C1–C9)

Lấy N2 (**ΣF = dp/dt**) và tích phân nó theo **ba cách khác nhau**:

| Tích phân theo | Phép toán | Kết quả | Khi nào "miễn phí" (bảo toàn) |
|---|---|---|---|
| **dt** | ∫ΣF dt = Δp | **Định lý xung lượng** (C1) | ΣF_ext = 0 theo một phương ⇒ P_e bảo toàn |
| **d r** (tức ΣF·dr) | ∫ΣF·dr = ΔK | **Định lý công–động năng** (C3); nếu F bảo toàn, dùng B5: ΔK = −ΔU ⇒ **E=K+U bảo toàn** (C4) | Lực không thế công = 0 trong đoạn xét |
| **r × (·)** rồi dt | d(r×p)/dt = r×F = **M**_O ⇒ ∫**M**_O dt = ΔL_O | **Định lý momen xung lượng** (C7) | **M**_O = 0 (lực xuyên tâm qua O, hoặc O trên đường tác dụng lực chưa biết) |

Cộng N2 cho **nhiều vật** trong hệ Σ, dùng N3 để triệt nội lực từng cặp:
- Tổng theo dt, nội lực triệt ⇒ **M a_cm = ΣF_ext** (C2) — khối tâm chỉ "thấy" ngoại lực.
- Đây cũng là lý do **C1 mở rộng tự nhiên sang hệ nhiều vật**: nội lực luôn triệt khi lấy tổng (hệ quả trực tiếp của N3).

**C5** (đồ thị thế năng) = chỉ là **đọc lại** phương trình `E = K+U` (từ cột giữa) dưới dạng đồ thị, cộng thêm A2 (Taylor) để có ω² = U''/m_eff tại cực tiểu — không có nội dung mới.

**C6** (va chạm) = áp **cột trái** (xung lượng, vì Δt→0 nên bỏ lực hữu hạn) cho thành phần tiếp tuyến **cộng thêm** định nghĩa B3 (hệ số e) cho thành phần pháp tuyến. Không có công thức mới — chỉ là C1 + B3 ghép lại.

**C7 → Kepler** = cột phải (L bảo toàn vì lực hấp dẫn xuyên tâm) **+** cột giữa (E bảo toàn vì hấp dẫn bảo toàn, dùng B5 với F=B2) **+** 🔧 thủ thuật đổi biến u=1/r (A5/A6 áp trong tọa độ cực, xem Binet ở Máy sinh 3) ⇒ ra phương trình quỹ đạo conic, mọi công thức Kepler (a, T²∝a³, vis-viva) chỉ là đại số từ hai đại lượng bảo toàn đó.

**C8** (quét đối xứng) không phải máy sinh thêm — nó **chính là bảng tra** "làm sao biết cột nào trong bảng trên miễn phí", tức là một thuật toán nhận diện Pre chứ không sinh công thức mới.

**C9** (Lagrange) là một **đường vòng khác** để tới cùng N2 (qua nguyên lý công ảo B6 mở rộng động), không bắt buộc nếu đã thạo Máy sinh 1 — bỏ qua được nếu muốn tối giản SEED.

---

### MÁY SINH 2 — "Công thức vận chuyển" (B4) → sinh ra TOÀN BỘ D9, D10 và một phần K4/K5

Chỉ cần thay số vào B4:
- ω = 0: còn lại m**a**' = **F** − m**a**₀ ⇒ toàn bộ **D9** (g_eff = g − a₀, con lắc trong thang máy/xe…).
- a₀ = 0, ω hằng: ra **D10** (ly tâm mω²r_⊥, Coriolis −2mω×v', thế năng ly tâm bằng B5 tích phân lực ly tâm).
- Áp A3 **cho chính tọa độ cực/tự nhiên trong hệ quán tính** (không cần hệ quay vật lý, chỉ là **e**_r, **e**_t quay theo quỹ đạo) ⇒ ra **a** = (r̈−rφ̇²)**e**_r + (rφ̈+2ṙφ̇)**e**_φ của K5, và **a** = s̈**t** + (ṡ²/ρ)**n** của K5 — về bản chất là **cùng một phép toán A3**, chỉ khác "hệ xoay" là do quỹ đạo tự nhiên hay do hệ vật lý quay.

→ **Nhận ra K4, K5, D10 là MỘT công thức (A3) áp vào ba ngữ cảnh khác nhau** giúp giảm ba công thức thành một.

---

### MÁY SINH 3 — "Tuyến tính hóa Taylor quanh cân bằng" (A2) + N2 (hoặc Máy sinh 1 cột giữa) → sinh ra TOÀN BỘ Phần O (O1–O8)

Quy trình chuẩn (chính là ALG-O1/O4 trong tài liệu gốc, viết lại như một **phép toán duy nhất**):

1. Tìm q₀: U'(q₀) = 0 (cân bằng — hệ quả trực tiếp của N2: ΣF=0 ⇔ −U'=0).
2. Viết E = ½M_eff(q)q̇² + U(q) (từ Máy sinh 1, cột giữa — đây **là** bảo toàn cơ năng, không phải công cụ mới).
3. Taylor U quanh q₀ (A2), giữ bậc 2: U ≈ U(q₀) + ½U''(q₀)x².
4. So sánh với dạng chuẩn ½M_eff ẋ² + ½K_eff x² = hằng ⇒ đạo hàm theo t ⇒ **M_eff ẍ + K_eff x = 0**, tức **ω² = U''(q₀)/M_eff(q₀)**.

Đây **chính là O1 + O4 gộp lại thành một phép toán**, và toàn bộ **O3** (bảng "hệ chuẩn": lò xo, con lắc đơn, con lắc vật lý...) chỉ là **áp phép toán trên cho từng U(q) cụ thể** — không có nội dung mới, chỉ là một bảng tra kết quả đã tính sẵn.

Từ phương trình chuẩn ẍ+ω²x=0, dùng A4 (ODE tuyến tính):
- Thêm số hạng cản tuyến tính (từ B2: F=−bv) vào vế trái ⇒ ẍ+2γẋ+ω₀²x=0 ⇒ **toàn bộ O5** chỉ là giải phương trình đặc trưng bậc hai (A4) của *cùng một* phương trình, biện luận theo dấu Δ=γ²−ω₀².
- Thêm vế phải điều hòa (lực ngoài cho trước) ⇒ ẍ+2γẋ+ω₀²x=(F₀/m)cosΩt ⇒ **toàn bộ O6** chỉ là nghiệm riêng dạng số phức (A4) của *cùng một* phương trình.
- Mở rộng sang **nhiều** tọa độ q_i (Taylor bậc 2 cho U(q₁,…,qₙ) thành dạng toàn phương ½xᵀKx) ⇒ **O7**: det(K−ω²M)=0 chỉ là phiên bản ma trận của bước 4 ở trên — cùng một ý tưởng, không phải công cụ mới.
- Nếu U''(q₀)=0 (bậc 2 triệt tiêu), giữ Taylor tới bậc cao hơn ⇒ **O8** (phi tuyến, Duffing) — vẫn là A2, chỉ lấy thêm một số hạng.
- **O2** (tổng hợp dao động) không sinh từ vật lý mới — chỉ là đại số cộng nghiệm `x=Acos(ωt+φ)` dưới dạng số phức (biểu diễn phasor), tức là cách viết khác của nghiệm ở bước 4.

**→ Nhận ra: toàn bộ 8 mục O1–O8 (≈ 1/4 tài liệu gốc) chỉ là MỘT phép toán (Taylor bậc 2 + ODE tuyến tính bậc 2) lặp lại với các số hạng vế phải/trái khác nhau.**

---

## PHẦN D. ĐỘNG HỌC THUẦN TÚY (K1–K3, K6, K8) — suy từ A1/A5/A6/A7, KHÔNG cần N2

Đây là nhánh "rẻ" nhất: không cần vật lý, chỉ là tích phân `a` theo các điều kiện khác nhau.

| Mục | Suy từ | Thao tác |
|---|---|---|
| K1 (a hằng) | A1 | Tích phân hằng số hai lần: `v=v₀+at`, `x=x₀+v₀t+½at²`; khử t bằng A1 cho `v²=v₀²+2aΔx` |
| K2 (a(t), a(x), a(v)) | A1/A5/A6 | Chọn đúng biến tách: a(x) dùng A5 (`vdv=a dx` — thực chất là B5 áp cho "thế năng động học", vì vậy K2-trường hợp a(x) **chính là** nguồn gốc của khái niệm năng lượng ở B5!) |
| K3 (ném xiên) | K1 áp độc lập cho 2 trục (vì **g** không đổi, N2 tách tuyến tính theo trục) | Thế t từ phương ngang vào phương đứng |
| K6 (vận tốc tương đối) | A1 (đạo hàm của hiệu vị trí) | **r**_rel(t) = **r**₀+**u**t; cực tiểu |**r**_rel|² dùng A7 |
| K8 (cực trị) | A7 | Chỉ là kỹ thuật toán thuần túy áp lên kết quả của K3 (hoặc bất kỳ công cụ nào khác) |

**K4, K5 → xem Máy sinh 2** (đều là A3). **K7 (ràng buộc)** → xem Phần E dưới đây (không phải vật lý, là hình học + đạo hàm).

---

## PHẦN E. RÀNG BUỘC HÌNH HỌC (K7, D2, D4 phần ghép, mọi "ràng buộc dây/ròng rọc") — một thao tác duy nhất

**SEED-nhỏ duy nhất cần thêm:** *"Viết hình học (khoảng cách/độ dài không đổi) thành phương trình đại số giữa các tọa độ, rồi đạo hàm theo t một hoặc hai lần."*

- Dây không dãn: Σ(chiều dài từng đoạn) = hằng ⇒ đạo hàm 1 lần ra ràng buộc vận tốc, 2 lần ra ràng buộc gia tốc.
- Thanh cứng: `|r_A−r_B|² = L²` ⇒ đạo hàm 2 lần (nhớ: đạo hàm bậc 2 của một bình phương sinh thêm số hạng `|Δv|²` — đây là **hệ quả toán học của A1**, không phải quy tắc mới, chỉ dễ quên).
- Lăn không trượt: v_điểm_tiếp_xúc = 0 ⇒ v_tâm = ωR (định nghĩa "không trượt").

Toàn bộ **K7, D2 (trừ dây nặng/capstan), phần ghép của D4 (lò xo nối hai vật)** chỉ là áp lặp lại thao tác này.

**Hai mục không suy ra được, phải nhớ thêm làm SEED nhỏ:**
- Dây nặng/capstan (`T = T₀e^{μφ}`): suy từ N2 áp cho **phần tử vi phân** dm=λ ds của dây — đây là một *kỹ thuật* (chia nhỏ hệ, viết N2 cho phần tử), không phải công thức, nhưng cần luyện riêng vì không "lộ ra" từ K7.
- Khối lượng hiệu dụng lò xo `m+m_s/3`: suy từ tích phân động năng của từng phần tử lò xo (một tích phân cụ thể, kỹ thuật tương tự).

---

## PHẦN F. QUÉT BIÊN LỰC (D1) VÀ CÁC ỨNG DỤNG (D3, D5, D6, D7) — không sinh công thức, chỉ là N2 + B2 "đọc thẳng"

- **D1**: chỉ là N2 (B1) cộng thủ tục liệt kê lực từ B2 — không có công thức mới, chỉ có **thuật toán đọc đề** (quét biên).
- **D3** (ma sát): chép thẳng dòng "Ma sát" trong B2, cộng thuật toán P10 (giả sử–kiểm tra, vốn chỉ là biện luận theo dấu/bất đẳng thức, tức A7 mở rộng).
- **D5** (lực cản): N2 + dòng "Cản" trong B2 + A6 (tách biến) ⇒ mọi công thức `v(t)`, `v_t`, `x(t)` chỉ là tích phân tách biến của hai dạng lực cụ thể.
- **D6** (lực hướng tâm): N2 chiếu lên **e**_n từ A3/Máy sinh 2, cộng B5 để lấy v từ năng lượng trước khi thế vào — đây là "chuỗi 2 máy sinh nối tiếp" (Máy sinh 1 cột giữa → Máy sinh 2), không phải công cụ độc lập.
- **D7** (hấp dẫn): chép thẳng dòng "Hấp dẫn" trong B2; quỹ đạo tròn chỉ là D6 với lực cụ thể này.
- **D8** (khối lượng biến thiên): N2 tổng quát (ΣF=dp/dt) áp cho hệ "vật + phần dm sắp vào/ra" — là **cách viết lại N2 cho hệ biên thay đổi**, cần nhớ thêm vế `(dm/dt)(u−v)` như một bước kỹ thuật, không phải định luật mới.
- **D11** (cân bằng, công ảo): chép thẳng B6; định lý Lami chỉ là hình học tam giác lực (ΣF=0 với 3 vector).

---

## PHẦN G. BẢNG TRA NGƯỢC: TỪ SEED → MỌI MỤC GỐC (dùng để tự kiểm tra trí nhớ)

| Mục gốc | Suy từ (SEED) | Thao tác chính |
|---|---|---|
| K1 | A1 | tích phân a hằng |
| K2 | A1, A5, A6 | chọn biến tách |
| K3 | K1 × 2 trục | B2 (trọng lực) tách trục |
| K4 | A3 (Máy sinh 2) | hệ cực r=const |
| K5 | A3, A8 (Máy sinh 2) | (t,n) hoặc (r,φ) tổng quát |
| K6 | A1, A7 | hiệu vị trí tuyến tính theo t |
| K7 | hình học + A1 (đạo hàm 2 lần) | Phần E |
| K8 | A7 | cực trị/Δ |
| D1 | N2(B1) + B2 | quét biên, không công thức mới |
| D2 | K7 + (capstan: N2 vi phân) | — |
| D3 | B2 dòng Ma sát + A7 (biện luận) | P10 |
| D4 | B2 dòng Đàn hồi + K7 (ghép) | tích phân động năng cho m_s/3 |
| D5 | N2 + B2 dòng Cản + A6 | tách biến |
| D6 | N2 chiếu theo A3 + Máy sinh 1 (lấy v) | chuỗi 2 máy sinh |
| D7 | B2 dòng Hấp dẫn | D6 với lực cụ thể |
| D8 | N2 tổng quát cho hệ biên đổi | kỹ thuật riêng (nhớ thêm) |
| D9 | B4 với ω=0 (Máy sinh 2) | — |
| D10 | B4 với a₀=0 (Máy sinh 2) | — |
| D11 | B6 | hình học lực/ảo |
| C1 | Máy sinh 1, cột trái | — |
| C2 | Máy sinh 1, cột trái + N3 cho hệ | — |
| C3 | Máy sinh 1, cột giữa | — |
| C4 | Máy sinh 1, cột giữa + B5 | — |
| C5 | C4 + A2 | đọc đồ thị |
| C6 | C1 + B3 (định nghĩa e) | — |
| C7 | Máy sinh 1, cột phải + Kepler: + C4 + 🔧u=1/r (A5/A6 trong hệ cực) | — |
| C8 | thuật toán nhận diện (không sinh công thức) | — |
| C9 | đường vòng khác tới N2 (tùy chọn) | — |
| O1–O8 | Máy sinh 3 (A2 + A4 + Máy sinh 1 cột giữa) | một phép toán lặp lại |

---

## PHẦN H. NHỮNG GÌ **KHÔNG** SUY RA ĐƯỢC TỪ SEED (phải nhớ thêm, danh sách đóng, ngắn)

Đây là "phần dư" thật sự — những thứ hoặc là hằng số thực nghiệm, hoặc là một thủ thuật đổi biến đặc thù không "lộ ra" tự nhiên từ 4 máy sinh trên. Nhớ **danh sách này** cộng với **SEED** ở Phần A–C là đủ để tái tạo toàn bộ tài liệu gốc:

1. **Giá trị số/tỉ lệ mô-men quán tính** (B7) — dữ kiện hình học thuần túy, không phải suy luận cơ học.
2. **Thủ thuật Binet** (đổi biến u=1/r trong chuyển động xuyên tâm) — cần biết để K5/C7 ra được dạng quỹ đạo kín (ellipse) thay vì chỉ dừng ở "L, E bảo toàn".
3. **Thủ thuật "phần tử vi phân"** cho dây nặng/capstan và khối lượng hiệu dụng lò xo — ý tưởng "chia hệ liên tục thành dm rồi tích phân", một kỹ năng riêng ngoài 4 máy sinh.
4. **Công thức vận chuyển khối lượng** `m dv/dt = F_ext + (dm/dt)(u−v)` (D8) — cách viết N2 cho biên hệ thay đổi, không suy từ N2 "thường" một cách hiển nhiên.
5. **Định nghĩa hệ số hồi phục e** (B3) — thực nghiệm, bù cho việc va chạm thật có biến dạng ngoài phạm vi chất điểm.
6. **Khai triển chuỗi chính xác của con lắc đơn / Duffing** (θ₀²/16, 3εA²/8ω₀) — là kết quả của khai triển Taylor **bậc cao hơn 2** (ngoài phạm vi A2 "bậc 2" trong SEED); chỉ cần khi bài đòi hỏi độ chính xác cao, nhớ dạng tỉ lệ chứ không cần nhớ hệ số nếu chấp nhận suy lại bằng tích phân số.
7. **Công thức tán xạ `sinθ_max = m₂/m₁`** và **số va chạm `⌊π·10ⁿ⌋`** — là các *kết quả nổi tiếng* của hệ Máy sinh 1 + P3 (hệ khối tâm) nhưng cần một bước dựng hình/đổi biến riêng (vẽ tam giác vận tốc, hoặc đổi biến `(√m₁v₁,√m₂v₂)`) — nên xem là "mẹo đã biết trước", không tự nhiên suy ra khi đang thi nếu chưa luyện qua một lần.
8. **Lệch Coriolis về phía đông khi rơi tự do** — là B4 áp cụ thể cho Trái Đất, nhưng tích phân cho ra hệ số 1/3 cần làm một lần cẩn thận (không khó, chỉ dễ sai dấu/hệ số).

**Tổng kết:** SEED (Phần A+B, khoảng 15 dòng) + 3 Máy sinh (Phần C, khoảng nửa trang) + danh sách 8 mục ở Phần H = toàn bộ kiến thức "phải nhớ cứng". Phần D–G chỉ là **cách áp dụng lặp lại** ba máy sinh, không phải kiến thức mới.

---

## PHẦN I. "THẺ GHI NHỚ" MỘT TRANG (bản cô đọng nhất)

```
TOÁN NỀN (biết sẵn): đạo hàm/tích phân · Taylor bậc 2 · vector xoay: de_r/dt=φ̇e_φ
                       · ODE tt bậc 2 (e^{rt}) · v dv = a dx · tách biến · Δ≥0

VẬT LÝ GỐC (9 khối, học thuộc):
  N1,N2(F=dp/dt),N3(F=-F')
  Lực: mg | GMm/r² | -k(l-l0) | f≤μsN,f=μkN | -bv,-cv² | liên kết ⟂/dọc không công
  e = -(Δv2')_n/(Δv2)_n
  Vận chuyển hệ: ma' = F - ma0 - 2mω×v' - mω×(ω×r')
  U = -∫F·dr
  Cân bằng lý tưởng: ΣF·δr = 0

BA MÁY SINH:
  (1) Tích phân N2 theo dt / dr / (r×)dt  →  C1–C9 (bảo toàn P, E, L)
  (2) Công thức vận chuyển hệ quy chiếu   →  D9, D10, K4, K5
  (3) Taylor bậc 2 quanh cân bằng + ODE tt →  O1–O8

PHẦN DƯ (nhớ thêm, không suy được):
  I_cm bảng | Binet u=1/r | dm vi phân (dây nặng/lò xo nặng) | m dv/dt=F+(dm/dt)(u-v)
  | tán xạ sinθmax=m2/m1 | số va chạm ⌊π·10ⁿ⌋ | lệch Coriolis hệ số 1/3
```

---

## PHẦN J. Ghi chú trung thực

- File này **không thay thế** tài liệu gốc — nó là một "bản đồ nén" để học thuộc nhanh hơn và để **kiểm tra** khi quên: nếu quên một công thức, tra bảng Phần G xem nó "thuộc máy sinh nào", rồi tự suy lại bằng SEED thay vì cố nhớ nguyên văn.
- Độ khó thực tế **không nằm ở việc nhớ SEED** (ngắn) mà nằm ở việc **luyện tới mức nhận ra nhanh** máy sinh nào áp dụng cho một CHỖ cụ thể trong đề — đúng tinh thần "giảm trực giác chứ không xóa" của tài liệu gốc (Phần 0.1).
- Phần H (8 mục "không suy ra được") là nơi duy nhất cần học thuộc lòng thuần túy như dữ kiện; phần còn lại nên luyện **suy lại từ đầu** nhiều lần cho tới khi phản xạ, thay vì học thuộc công thức cuối.
