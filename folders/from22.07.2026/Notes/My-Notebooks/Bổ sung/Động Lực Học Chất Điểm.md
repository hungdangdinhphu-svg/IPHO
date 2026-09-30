# Động lực học chất điểm — Cấu trúc Toán bên dưới Vật lý

*Áp dụng khung Vấn đề 1 (Vật lý → Toán) và Vấn đề 2 (cấu trúc Toán + bài toán tìm kiếm) cho: Định luật Newton · Các lực cơ học · Ứng dụng vào bài tập · HQC phi quán tính.*

## 0. Cam kết trung thực (đọc trước)

- **Chắc chắn (kiến thức chuẩn, đã kiểm lại đại số):** các công thức và ví dụ có lời giải bên dưới.
- **Phương pháp luận (heuristic, không phải định lý):** "họ precondition {Pre(ℓ)}" và quy trình tìm CHỖ là cách *tổ chức* kinh nghiệm. Tôi **không** chứng minh được rằng nó phủ mọi bài IPHO. Phần đếm ẩn–phương trình (§4) là điều kiện cần chặt; phần "bước có ý nghĩa" vẫn cần trực giác.
- Phạm vi lấy từ ảnh đề cương (4 mục). Chi tiết mức HSGQG/IPHO ở §7 là nhận định của tôi, hãy đối chiếu đề cương chính thức.

---

## 1. Mô hình M = (O, V, L, C, Q, I) cho động lực học chất điểm

**O (ontology):** chất điểm (khối lượng m), hệ quy chiếu (HQC), vật, dây, ròng rọc, mặt tiếp xúc, lò xo, trường (trọng trường...). **V:** r(t), v, a, m, các lực chưa biết (N, f, T), góc, thời gian. **C:** ràng buộc hình học (dây không giãn, tiếp xúc), điều kiện đầu, bất đẳng thức tiếp xúc. **Q:** đại lượng cần tìm. **I:** ánh xạ từ chữ trong đề sang O, V, C (bảng §2).

### L — thư viện định luật, mỗi mục có Dom / Pre / Post / Err

| ℓ | Pre (điều kiện cần) | Post | Err / ghi chú |
|---|---|---|---|
| **N1** | chất điểm cô lập | định nghĩa HQC quán tính | không kiểm chứng độc lập được; là *định nghĩa vận hành* |
| **N2** | HQC quán tính; v ≪ c; m không đổi | m**a** = Σ**F** | m biến thiên: dùng hệ *cố định tập hạt* (§6) |
| **N3** | tương tác cặp, lực nằm trên đường nối | **F**₁₂ = −**F**₂₁ | lực từ giữa điện tích chuyển động: dạng yếu có thể sai (trường mang động lượng) |
| **Hooke** | biến dạng nhỏ, lò xo lý tưởng (m≈0) | F = −kΔℓ | vượt giới hạn đàn hồi: sai |
| **Dây lý tưởng** | m≈0, không giãn | ràng buộc độ dài; T ≥ 0; T đều dọc dây nếu qua ròng rọc ideal | dây chùng ⇒ T = 0, ràng buộc thành *bất đẳng thức* |
| **Ròng rọc lý tưởng** | m≈0, không ma sát | T hai phía bằng nhau | có khối lượng: (T₁−T₂)R = Iα (ngoài chất điểm thuần) |
| **Ma sát trượt** | hai bề mặt *đang* trượt | f = μN, ngược **v**_tương đối | μ có thể phụ thuộc v |
| **Ma sát nghỉ** | *không* trượt | \|f\| ≤ μₛN (bất đẳng thức!) | f **không** mặc định bằng μₛN |
| **Cản** | — | f = −b**v** (nhớt, v nhỏ); f = −c v**v̂** (v lớn) | chọn mô hình theo số Reynolds; đề thường cho sẵn |
| **Hấp dẫn** | chất điểm/cầu đồng chất | F = GMm/r² | g = GM/R² chỉ gần mặt đất |
| **Quán tính** | chỉ trong HQC phi quán tính tương ứng | xem §3-S6 | **không** là tương tác thật, không có phản lực |

**Dom vs Pre:** N2 có Dom rộng (mọi chuyển động chất điểm phi tương đối tính) nhưng Pre hẹp (HQC quán tính). Sai Pre là nguồn lỗi số 1.

**Mở rộng:**

Để xác định chiều của lực căng dây T bất kỳ, nhớ một nguyên tắc duy nhất: Lực căng dây luôn là lực KÉO, và nó kéo vật theo hướng dọc theo sợi dây, hướng RA XA vật đang xét. 1 Sợi dây hoàn toàn có thể tồn tại 1 lúc nhiều lực căng dây cho từng vật đang xét, ví dụ trực quan cho từ nay không lú nữa đó là cầm 1 sợi dây, kéo 2 đầu, thì sợi dây sẽ căng ra và giữ lại (ko phải đàn hồi), farewell.



Để xác định chiều của lực đàn hồi F_hd bất kỳ, nhớ rằng: Lực đàn hồi là một lực "vị kỷ", nó luôn chống lại sự thay đổi để tìm cách đưa về hình dạng ban đầu.

**Làm sao để biết** vật mà ta đang xét thì ta cần "quan tâm" đến những lực nào (hay lực tác dụng lên vật đang xét)? : Vật có những lực "từ xa" nào tác dụng?; Cái gì đang "chạm" TRỰC TIẾP vào vật? Cứ 1 vật chạm vào sẽ sinh ra lực tương ứng; 




---

## 2. Vấn đề 1 — Từ đề bài sang bài Toán

**Quy trình cố định (7 bước):**
1. Chọn **HQC** và kiểm Pre của N2 (quán tính? Nếu không: thêm lực quán tính hoặc đổi HQC).
2. Chọn **hệ**: tách từng vật (cô lập), liệt kê mọi vật/dây/mặt tiếp xúc.
3. Vẽ sơ đồ lực: mỗi vật chịu (a) lực từ xa (trọng lực, điện...), (b) lực tiếp xúc: *mỗi điểm tiếp xúc cho tối đa một cặp (N, f) hoặc một T*.
4. Chọn **hệ trục** theo hình học (Descartes, cực, tự nhiên; §3-S4).
5. Dịch dữ kiện thành ràng buộc (bảng dưới).
6. Viết Newton II theo từng thành phần + ràng buộc.
7. Kiểm: đơn vị, trường hợp giới hạn, các bất đẳng thức (N ≥ 0, T ≥ 0, \|f\| ≤ μₛN).

**Từ khóa → ràng buộc** (bước 5):

| Đề nói | Nghĩa toán |
|---|---|
| nhẵn / không ma sát | f = 0, chỉ còn N ⟂ mặt |
| dây nhẹ, không giãn | m_dây=0, T đều; Σ độ dài = const ⇒ liên hệ **a** |
| ròng rọc nhẹ | T hai phía bằng nhau; ròng rọc động: ΣF = 0 ⇒ 2T = lực treo |
| bắt đầu trượt | \|f\| = μₛN (dấu = của bất đẳng thức) |
| rời khỏi mặt / bắt đầu bay | N = 0 |
| dây bắt đầu chùng | T = 0 |
| cân bằng / đứng yên | **a** = 0 |
| chuyển động đều | **a** = 0 (đường thẳng) hoặc \|**v**\| = const (đường cong, a_n ≠ 0) |
| "vừa đủ" / "tối thiểu" | dấu = của điều kiện biên (N = 0 hoặc T = 0 ở điểm nguy hiểm) |
| biết quỹ đạo tròn bán kính R | a_n = v²/R, a_t = dv/dt |

---

## 3. Vấn đề 2 — Các cấu trúc Toán của động lực học chất điểm

Sau mô hình hóa, bài thuộc một hoặc **tổ hợp** các cấu trúc sau. Việc đầu tiên là *nhận diện cấu trúc*.

### S1. Hệ phương trình tuyến tính (nhiều vật, dây, ròng rọc)
Ẩn: a_i, T_j, N_k. Phương trình: N2 từng thành phần + ràng buộc hình học đã **đạo hàm hai lần**. Dạng **A x = b** với x = (a, T, N).
- **Điều kiện đóng kín:** #ẩn = #phương trình (§4).
- Ràng buộc dây: viết độ dài dây theo tọa độ, đạo hàm hai lần. Ròng rọc động cho hệ số 2.
- Kiểm tra bằng trường hợp đặc biệt (cân bằng, m→0, m→∞).

### S2. Bất đẳng thức / chế độ (complementarity)
N ≥ 0, T ≥ 0, \|f\| ≤ μₛN tạo ra **chế độ**: dính/trượt, tiếp xúc/rời, căng/chùng.
**Thuật toán:** (i) giả thiết một chế độ; (ii) giải hệ S1 ứng với chế độ đó; (iii) kiểm bất đẳng thức; (iv) nếu vi phạm, đổi chế độ. Với k điều kiện có tối đa 2ᵏ chế độ (hữu hạn); trong thực tế chỉ vài cái khả dĩ. Điều kiện **đủ** để chấp nhận nghiệm chính là kiểm xong bước (iii).
Ngưỡng ("bắt đầu trượt", "rời mặt") ⇒ thay bất đẳng thức bằng dấu =, giải ra tham số tới hạn.

### S3. Phương trình vi phân theo t (lực phụ thuộc t, v, x)
m dv/dt = F. Phân loại theo biến nào xuất hiện trong F:
- **F(t):** tích phân trực tiếp.
- **F(v):** tách biến. Rơi có cản nhớt: v = (mg/b)(1 − e^(−bt/m)), v_lim = mg/b. Cản bậc hai: v = v_t tanh(gt/v_t), v_t = √(mg/c).
- **F(x):** dùng dv/dt = v dv/dx ⇒ ½mv² − ∫F dx = const (cầu nối sang năng lượng).
- **Tuyến tính hệ số hằng, dạng ẍ + 2γẋ + ω₀²x = f₀cos ωt:**
  - tắt dần: γ < ω₀ dao động, γ = ω₀ tới hạn, γ > ω₀ quá tắt;
  - cưỡng bức, trạng thái dừng: biên độ A = f₀ / √((ω₀² − ω²)² + 4γ²ω²).

### S4. Tọa độ cong (chọn hệ trục theo hình học)
- Tự nhiên: a_t = dv/dt, a_n = v²/ρ.
- Cực: a_r = r̈ − rθ̇², a_θ = rθ̈ + 2ṙθ̇.
- **Chỗ dùng:** quỹ đạo tròn/xoắn, vật trên mặt cong, chuyển động dưới lực xuyên tâm. Chiếu Newton lên phương pháp tuyến cho N; lên tiếp tuyến cho a_t.

### S5. Tích phân đầu (đường tắt khi đủ điều kiện)
- Thành phần ΣF_ngoài theo phương e = 0 ⇒ p_e = const (Suf: chỉ xét thành phần đó).
- Lực chỉ có công bảo toàn hoặc không sinh công (N ⟂ **v**) ⇒ bảo toàn cơ năng.
- Chúng là **hệ quả** của N2 dưới Pre thích hợp, không phải công cụ độc lập.
- Mẫu kinh điển: **năng lượng cho v(θ) + Newton pháp tuyến cho N** (ví dụ E3).

### S6. Đổi HQC = đổi biến tọa độ
Trong HQC quay với **ω** và tịnh tiến gia tốc **a**₀:

**m a′ = F − m a₀ − m ω̇×r′ − 2m ω×v′ − m ω×(ω×r′)**

- Tịnh tiến: −m**a**₀ ⇒ trọng trường hiệu dụng **g**_eff = **g** − **a**₀.
- Ly tâm: mω²r′ hướng ra trục, bảo toàn, thế −½mω²r².
- Coriolis: −2m ω×v′ ⟂ **v**′, **không sinh công**, làm lệch quỹ đạo.
- **Khi nào dùng:** khi ràng buộc/cân bằng đơn giản hơn ở HQC đó (vật đứng yên trong HQC quay, con lắc trong xe).
- **Bẫy:** không được vừa dùng lực quán tính vừa dùng gia tốc HQC theo cách tính hai lần; lực quán tính không có phản lực (N3 không áp dụng cho nó).

### S7. Thuật toán hạng nặng: Lagrange (tương tự Nodal Analysis)
L = T − U; d/dt(∂L/∂q̇) = ∂L/∂q.
- **Pre:** ràng buộc holonomic và lý tưởng (phản lực không sinh công ảo); ma sát/cản đưa vào như lực suy rộng.
- **Lợi:** chọn tọa độ suy rộng q ⇒ ràng buộc hình học thỏa tự động, **phản lực biến mất**, ra ngay phương trình chuyển động (ẩn = bậc tự do).
- **Hạn chế:** không cho N, T (phải quay lại Newton hoặc dùng nhân tử Lagrange). Chưa chắc được yêu cầu chính thức ở HSGQG/IPHO: nên dùng để *kiểm* và *tăng tốc*, đồng thời vẫn biết cách giải bằng Newton.

---

## 4. Bài toán tìm kiếm (CHỖ) áp dụng cho động lực học

Theo khung của bạn: tìm cặp (ℓ, CHỖ) sao cho Pre(ℓ) thỏa tại CHỖ và bước đó sinh ràng buộc mới có ý nghĩa.

**CHỖ trong động lực học chỉ có vài loại (hữu hạn):**
| Loại CHỖ | Công cụ ℓ | Pre cần kiểm tại CHỖ |
|---|---|---|
| Một vật, một phương | N2 | HQC quán tính; liệt kê đủ lực |
| Một dây / ròng rọc | ràng buộc, T đều | m≈0, không giãn, T ≥ 0 |
| Một mặt tiếp xúc | (N, f) | đang trượt hay nghỉ |
| Một điểm quỹ đạo cong | a_n = v²/ρ | biết bán kính cong ρ |
| Hai trạng thái cách nhau | năng lượng | công lực không bảo toàn tính được |
| Cả hệ theo một phương | động lượng | ΣF_ngoài = 0 theo phương đó |
| Một biến cố tới hạn | N=0 / T=0 / f=μₛN | đề có "vừa đủ / bắt đầu" |

**Duyệt kỷ luật ("brute-force có cấu trúc"):**
1. Với **mỗi vật** × **mỗi thành phần trục**: viết một N2. (Đây là duyệt đầy đủ; không bỏ sót.)
2. Với **mỗi dây/ròng rọc/tiếp xúc**: viết ràng buộc hình học.
3. **Đếm:** #ẩn (a, T, N, f) so với #phương trình. Hệ đóng kín ⇔ bằng nhau (điều kiện **cần** cho Completeness). Thiếu ⇒ bỏ sót một CHỖ hoặc ràng buộc; thừa ⇒ có phương trình phụ thuộc hoặc mâu thuẫn (Consistency).
4. **Lọc** theo "ý nghĩa": giữ phương trình chứa đại lượng cần tìm hoặc làm giảm ẩn; ưu tiên chiếu theo phương làm biến mất phản lực chưa biết.
5. **Kiểm bất đẳng thức** (S2) ở cuối, không ở đầu.

**Mẹo giảm tải:** tách phương *dọc* (khử N) hoặc *ngang*; chọn hệ trục theo phương gia tốc; với hệ ràng buộc, ghi ngay liên hệ a₁ = k a₂.

---

## 5. Ví dụ có lời giải (đã kiểm đại số)

### E1. Ròng rọc động (S1)
Dây vắt qua ròng rọc cố định: một đầu buộc m₁ (treo), đầu kia luồn qua ròng rọc động (nhẹ, treo m₂) rồi buộc lên trần. Lấy chiều dương hướng xuống.
- Ẩn: a₁, a₂, T (3). Phương trình: (1) m₁g − T = m₁a₁; (2) m₂g − 2T = m₂a₂; (3) ràng buộc y₁ + 2y₂ = const ⇒ a₁ = −2a₂. Đủ 3 = 3.
- Kết quả: a₂ = (m₂ − 2m₁)g/(m₂ + 4m₁), T = 3m₁m₂g/(m₂ + 4m₁).
- Kiểm: m₂ = 2m₁ ⇒ a₂ = 0, T = m₁g, và 2T = m₂g ✓.

### E2. Ma sát nghỉ (S2)
Vật A nằm trên B; B chịu lực kéo ngang F. Giả thiết *dính*: a = F/(m_A + m_B), f = m_A a. Kiểm \|f\| ≤ μₛm_Ag ⇔ a ≤ μₛg ⇔ **F ≤ μₛ(m_A + m_B)g** (nếu mặt dưới B nhẵn). Vi phạm ⇒ chuyển chế độ trượt (f = μₖm_Ag).

### E3. Vật trượt trên mặt cầu nhẵn (S2 + S4 + S5)
Đỉnh cầu bán kính R, θ từ phương thẳng đứng. Năng lượng: v² = 2gR(1 − cosθ). Pháp tuyến: mg cosθ − N = mv²/R. Rời mặt: N = 0 ⇒ cosθ = 2(1 − cosθ) ⇒ **cosθ = 2/3**.

### E4. Con lắc trong xe gia tốc a₀ (S6)
Trong HQC xe: g_eff = √(g² + a₀²). Cân bằng lệch θ₀ = arctan(a₀/g); lực căng khi cân bằng T = m√(g² + a₀²); chu kỳ dao động nhỏ **T = 2π√(l/√(g² + a₀²))**.

### E5. Hạt trên thanh quay đều, nhẵn (S3 + S4 + S6)
Cực, θ̇ = ω: phương r: r̈ − ω²r = 0 ⇒ r = Ae^(ωt) + Be^(−ωt). N ⟂ thanh cung cấp a_θ = 2ṙω. Bản chất: cùng phương trình khi xét trong HQC quay với lực ly tâm mω²r, và N cân bằng Coriolis.

### E6. Hạt trên vòng quay quanh trục thẳng đứng (S6/S7)
Vòng bán kính R, tốc độ góc ω, θ từ điểm thấp nhất. Lagrange: θ̈ = sinθ(ω²cosθ − g/R).
- ω² < g/R: chỉ cân bằng ổn định ở θ = 0.
- ω² > g/R: θ = 0 mất ổn định; xuất hiện **cosθ₀ = g/(Rω²)** ổn định, dao động nhỏ quanh đó với Ω² = ω² − g²/(R²ω²) (rẽ nhánh — pitchfork).

### E7. Hiệu ứng Trái Đất quay (S6)
- Ly tâm ở xích đạo: ω²R ≈ (7,29·10⁻⁵)² × 6,38·10⁶ ≈ 0,034 m/s² (~ g/290).
- Rơi từ độ cao h ở vĩ độ λ: lệch **về phía đông** δ = (1/3)ω cosλ √(8h³/g) (xấp xỉ bậc nhất ở ω).
- Mặt phẳng dao động con lắc Foucault quay với tốc độ góc ω sinλ.

---

## 6. Bẫy kinh điển & Điều kiện đủ để tự kiểm

1. N **không** mặc định = mg cosα; chỉ đúng khi a ⟂ mặt bằng 0.
2. Ma sát nghỉ **không** bằng μₛN; chỉ bằng ở ngưỡng.
3. Dây qua ròng rọc **có khối lượng**: T hai phía khác nhau.
4. N2 cho **khối lượng biến thiên:** F = dp/dt chỉ dùng cho hệ cố định tập hạt. Dạng thường dùng: m dv/dt = F + u_rel dm/dt (u_rel: vận tốc của khối lượng vào/ra so với vật). Tên lửa: Δv = u ln(m₀/m).
5. **Ly tâm ≠ phản lực của lực hướng tâm.** Lực hướng tâm là *tên gọi* của hợp lực hướng vào tâm, không phải một lực mới trên sơ đồ.
6. Tính hai lần: dùng lực quán tính rồi lại gán gia tốc HQC.
7. Dấu N, T âm ⇒ giả thiết chế độ sai, không phải "lực âm".
8. Chọn sai HQC quán tính (HQC gắn với vật đang gia tốc).
9. Kiểm cuối: đơn vị, trường hợp giới hạn, đối xứng, giá trị dương của N/T.

---

## 7. Mức HSGQG vs IPHO (nhận định, cần đối chiếu đề cương)

- **HSGQG:** thường gặp S1, S2, S4, S5, S6 (tịnh tiến và quay đều), một số bài ODE F(v), dao động tắt dần cơ bản. Chỗ kẹt phổ biến: **chọn HQC**, **ràng buộc dây/ròng rọc động**, **kiểm bất đẳng thức**.
- **IPHO (mở rộng):** khối lượng biến thiên, Coriolis đầy đủ, ODE tuyến tính cưỡng bức, ổn định cân bằng/dao động nhỏ (khai triển thế), bài nhiều chế độ ghép nối. Hầu hết chỗ khó là **mô hình hóa** (Vấn đề 1) hơn là giải toán.
- Cách rèn: với mỗi bài, ghi ra *cấu trúc Toán*, *Pre đã kiểm*, *bảng đếm ẩn–phương trình* trước khi giải.

---

## 8. Chưa có trong bản này (có thể mở rộng theo yêu cầu)

Khối lượng biến thiên chi tiết (băng chuyền, tên lửa, xích rơi) · Coriolis và HQC quay theo bài tập nhiều bước · dao động cưỡng bức/cộng hưởng có lời giải đầy đủ · Lagrange với nhân tử · bộ bài tập phân loại theo cấu trúc với lời giải · thư viện "họ precondition có tham số" cho từng loại bài.
