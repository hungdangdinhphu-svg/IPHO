# Động học chất điểm — Cấu trúc Toán bên dưới Vật lý

*Khung Vấn đề 1 (Vật lý → Toán) và Vấn đề 2 (cấu trúc Toán + bài toán tìm kiếm) cho: Chuyển động thẳng đều/biến đổi đều · Rơi tự do · Chuyển động tròn đều/biến đổi đều · Khảo sát chuyển động bằng phương pháp tọa độ.*

## 0. Cam kết trung thực

- **Chắc chắn (kiến thức chuẩn, các công thức và ví dụ bên dưới đã được tôi kiểm lại đại số):** mọi công thức, đặc biệt các ví dụ E1–E6.
- **Phương pháp luận (heuristic):** "họ precondition" và quy trình tìm CHỖ là cách tổ chức kinh nghiệm, không phải định lý phủ mọi bài IPHO.
- **Không chắc:** bạn nhắc đến "Thuật toán Tọa độ Hóa Mở rộng" nhưng không định nghĩa. Ở §4 tôi trình bày *cách tôi hiểu* (biểu diễn mọi thứ bằng tọa độ/tham số rồi lấy ràng buộc). Nếu định nghĩa của bạn khác, hãy gửi để tôi chỉnh.
- Mức HSGQG/IPHO ở §7 là nhận định của tôi; hãy đối chiếu đề cương chính thức.

**Điểm khác cốt lõi so với Động lực học:** Động học chỉ *mô tả*. Nó **không cần HQC quán tính** và không có định luật vật lý nào ngoài định nghĩa v = d**r**/dt, **a** = d**v**/dt và các giả thiết về dạng a(t). Lỗi ở đây gần như luôn là lỗi *mô hình hóa và đại số*, không phải lỗi định luật.

---

## 1. Mô hình M = (O, V, L, C, Q, I)

**O:** chất điểm, HQC (gốc, trục, gốc thời gian), quỹ đạo, các vật khác, dây/thanh nối. **V:** **r**(t), **v**, **a**, t, s (quãng đường), θ, ω, α. **C:** điều kiện đầu, ràng buộc (dây, thanh, tiếp xúc), điều kiện biến cố. **Q:** đại lượng cần tìm. **I:** bảng dịch đề → C (§2).

### L — thư viện công cụ (Dom / Pre / Post / Err)

| ℓ | Pre (điều kiện cần) | Post | Ghi chú |
|---|---|---|---|
| **Định nghĩa** | khả vi | **v** = d**r**/dt, **a** = d**v**/dt | mọi chuyển động |
| **Gia tốc không đổi** (vectơ) | **a** = const *trong suốt khoảng thời gian xét* | **v** = **v**₀ + **a**t; **r** = **r**₀ + **v**₀t + ½**a**t²; v² − v₀² = 2**a**·Δ**r** (1D: 2aΔx) | hai phương trình *độc lập*, các công thức khác là hệ quả |
| **Quãng đường trung bình** | — | v_tb,vô hướng = S/t | ≠ vận tốc trung bình Δ**r**/t |
| **Rơi tự do** | bỏ cản, g = const (độ cao nhỏ) | a = g hướng xuống, v₀ tùy | ném thẳng đứng, ném ngang, ném xiên đều thuộc mục này |
| **Chuyển động tròn** | R = const | v = ωR; a_n = ω²R = v²/R; a_t = Rα; \|**a**\| = √(a_t² + a_n²) | tròn đều: α = 0, T = 2π/ω |
| **Tròn biến đổi đều** | α = const | ω = ω₀ + αt; θ = θ₀ + ω₀t + ½αt²; ω² − ω₀² = 2αΔθ | a_t = Rα là *hằng*, nhưng **a** không hằng (a_n đổi) |
| **Cộng vận tốc (Galileo)** | HQC K′ chuyển động *tịnh tiến* với vận tốc **V** so với K; v ≪ c | **v** = **v**′ + **V**; **a** = **a**′ + **A** | HQC quay: thêm số hạng (dưới bảng) |
| **Ràng buộc chiều dài** | dây không giãn *và đang căng*, hoặc thanh cứng | \|**r**_A − **r**_B\| = L ⇒ (**r**_A − **r**_B)·(**v**_A − **v**_B) = 0 | "hình chiếu vận tốc lên dây bằng nhau" |
| **Lăn không trượt** | vật rắn, không trượt tại tiếp điểm | v_tiếp điểm = 0; v_tâm = ωR | mở rộng sang vật rắn, xem K6 |

**HQC quay đều ω:** **v** = **v**′ + **V** + **ω** × **r**′; **a** = **a**′ + **A** + 2**ω** × **v**′ + **ω** × (**ω** × **r**′) (+ **ω̇** × **r**′ nếu ω đổi). Đừng dùng "cộng vận tốc đơn giản" khi HQC quay.

---

## 2. Vấn đề 1 — Từ đề bài sang bài Toán

**Quy trình cố định (7 bước):**
1. **Chọn HQC, gốc tọa độ, chiều dương, gốc thời gian** sao cho nhiều điều kiện đầu bằng 0 nhất; hoặc *đổi HQC* để bài đơn giản (K3).
2. Vẽ **hình và đồ thị (x–t, v–t)** nếu chuyển động chia pha.
3. **Chia pha** tại mọi điểm gia tốc hoặc quy luật thay đổi (chạm đất, đổi chiều, dây căng/chùng, lò xo...).
4. Với mỗi vật, mỗi pha, mỗi phương: viết **r**(t), **v**(t).
5. Dịch **biến cố** thành phương trình (bảng dưới).
6. Đếm ẩn = phương trình (§4); giải.
7. Kiểm: t ≥ 0 và nằm *trong pha*, dấu, đơn vị, trường hợp giới hạn.

**Từ khóa → điều kiện toán:**

| Đề nói | Nghĩa toán |
|---|---|
| gặp nhau | **r**₁(t) = **r**₂(t): *cùng t, cùng vị trí* (mọi thành phần) |
| đuổi kịp | cùng vị trí ở cùng thời điểm; x₁(t) = x₂(t) một phương |
| gần nhau nhất | d²(t) cực tiểu: dd²/dt = 0, hoặc dùng chuyển động tương đối |
| có thể đến điểm (x, y) | tồn tại nghiệm tham số (góc) ⇒ Δ ≥ 0 |
| đạt độ cao cực đại | v_y = 0 |
| chạm đất | y = 0 (chọn nghiệm t > 0) |
| tầm xa cực đại | tối ưu theo góc; hoặc dùng đường bao (E2) |
| chuyển động đều | **a** = 0 (đường thẳng); \|**v**\| = const (đường cong, a_n ≠ 0) |
| dừng lại | v = 0 (nếu a≠0 thì đổi chiều, không "dừng mãi") |
| dây (thanh) nối hai vật | (**r**_A − **r**_B)·(**v**_A − **v**_B) = 0 |
| lăn không trượt | v_tiếp điểm = 0 |
| bán kính cong | ρ = v²/a_n |
| rơi trong giây thứ n | s_n = s(n) − s(n−1) = ½g(2n − 1) (với t tính bằng giây, xuất phát từ nghỉ) |

---

## 3. Vấn đề 2 — Các cấu trúc Toán của động học

### K1. Đại số với gia tốc hằng ("chọn công thức thiếu ẩn")
Một phương: 5 biến (Δx, v₀, v, a, t), **2 phương trình độc lập** ⇒ cần biết 3 biến, tìm 2 còn lại.
**Thuật toán chọn công thức:** đại lượng *không* cho và *không* hỏi ⇒ chọn công thức không chứa nó:
- thiếu Δx: v = v₀ + at
- thiếu v: Δx = v₀t + ½at²
- thiếu t: v² − v₀² = 2aΔx
- thiếu a: Δx = ½(v₀ + v)t
- thiếu v₀: Δx = vt − ½at²

**Bẫy:** công thức chỉ đúng *trong một pha*; đổi chiều chuyển động làm S ≠ |Δx| (phải chia tại v = 0).

### K2. Phương trình đa thức + biện luận nghiệm (gặp nhau, tầm với, tối ưu)
Gặp nhau/đến điểm ⇒ đa thức theo t hoặc theo tham số (góc, tanα).
- **Tồn tại nghiệm:** Δ ≥ 0.
- **Nghiệm hợp lệ:** t ≥ 0, t trong pha, nghiệm đúng ở *mọi* phương (hệ nhiều phương trình cần thỏa đồng thời).
- **Điều kiện "chỉ chạm" (tiếp tuyến):** Δ = 0 (cực trị nằm ở biên).
- **Tối ưu bậc hai:** f(t) = at² + bt + c có cực trị tại t = −b/2a.
- **Định lý Viète:** hai nghiệm t₁, t₂ (lên và xuống qua cùng độ cao): t₁ + t₂ = 2v₀/g, t₁t₂ = 2h/g.

### K3. Vectơ + đổi HQC (chuyển động tương đối)
**v**₁₂ = **v**₁ − **v**₂ (Galileo, HQC tịnh tiến). Khi **a**₁ = **a**₂ (ví dụ hai vật cùng chịu g), chuyển động tương đối là **thẳng đều** với **v**_rel = **v**₁(0) − **v**₂(0).
- **Gần nhất:** d_min = \|**r**₀ × **v**_rel\| / \|**v**_rel\| tại t* = −(**r**₀·**v**_rel)/\|**v**_rel\|² (nếu t* > 0).
- **Gặp nhau:** cần **r**₀ song song **v**_rel và cùng chiều tiến lại.
- **Chỗ dùng:** hai đạn/hạt rơi tự do cùng lúc; thuyền qua sông; mưa và xe.

### K4. Tích phân/đồ thị (a(t), a(x), a(v) cho trước; đọc đồ thị)
- Δx = ∫v dt (diện tích dưới v–t); Δv = ∫a dt.
- a(x): dùng a = v dv/dx ⇒ ½v² = ∫a dx + C.
- a(v): tách biến dv/a(v) = dt.
- Chia pha khi đồ thị gãy khúc; diện tích *có dấu* cho Δx, *trị tuyệt đối* cho S.

### K5. Tọa độ cong, tham số hóa, khử tham số
- **Cực:** v_r = ṙ, v_θ = rθ̇; a_r = r̈ − rθ̇², a_θ = rθ̈ + 2ṙθ̇.
- **Tự nhiên:** a_t = dv/dt, a_n = v²/ρ.
- **Ném xiên:** x = v₀cosα·t, y = v₀sinα·t − ½gt² ⇒ y = x tanα − gx²/(2v₀²cos²α). H = v₀²sin²α/(2g), T = 2v₀sinα/g, L = v₀²sin2α/g (cùng độ cao).
- **Bán kính cong quỹ đạo ném:** ρ = v²/a_n với a_n = g cosφ (φ góc **v** với phương ngang): tại đỉnh ρ = v₀²cos²α/g; lúc ném ρ = v₀²/(g cosα).
- **Khử tham số** (t hoặc α) để lấy phương trình quỹ đạo hoặc miền chạm tới.

### K6. Ràng buộc bằng đạo hàm ("phương trình ràng buộc → liên hệ vận tốc/gia tốc")
Viết ràng buộc hình học dưới dạng phương trình tọa độ, rồi đạo hàm:
- Thanh/dây: \|**r**_A − **r**_B\|² = L² ⇒ (**r**_A − **r**_B)·(**v**_A − **v**_B) = 0 ⇒ (lần hai) \|**v**_A − **v**_B\|² + (**r**_A − **r**_B)·(**a**_A − **a**_B) = 0.
- Tổng chiều dài dây (ròng rọc động): Σ ℓᵢ = const ⇒ Σ vᵢ (có hệ số) = 0.
- **Lăn không trượt:** v_tâm = ωR, v_đỉnh = 2v_tâm, v_tiếp điểm = 0; điểm bất kỳ có v = ω × (khoảng cách tới **tâm quay tức thời**).
- **Lưu ý IPHO:** giao điểm của hai đường di động (cây kéo) có thể chuyển động nhanh hơn mọi vật thật; không vi phạm gì vì nó không phải vật chất.

### K7. Tuần hoàn / đồng dư (chuyển động tròn nhiều vật, đồng bộ)
Hai điểm quay cùng chiều gặp nhau khi (ω₁ − ω₂)t = 2πk; ngược chiều khi (ω₁ + ω₂)t = 2πk (k nguyên dương). Cấu trúc là **đồng dư modulo 2π**: tìm nghiệm nhỏ nhất dương và mọi nghiệm sau. Bài kiểu đồng hồ, bánh răng, sao đôi, đèn quét thuộc mục này.

---

## 4. Bài toán tìm kiếm (CHỖ) cho động học

Tìm cặp (ℓ, CHỖ) sao cho Pre(ℓ) thỏa tại CHỖ và bước đó cho ràng buộc mới có ý nghĩa.

| Loại CHỖ | Công cụ ℓ | Pre cần kiểm tại CHỖ |
|---|---|---|
| Một vật, một pha, một phương | K1 (gia tốc hằng) | a = const trong pha đó? |
| Một biến cố (gặp, chạm, đỉnh, đổi pha) | phương trình điều kiện (K2) | biến cố xảy ra *cùng t*? nghiệm t hợp lệ? |
| Ranh giới hai pha | liên tục x, v | hai pha nối nhau tại đúng t đó |
| Cặp điểm nối bởi dây/thanh | K6: đạo hàm ràng buộc | dây đang căng/thanh cứng? |
| Cặp vật cùng gia tốc | K3: chuyển động tương đối | a₁ = a₂ |
| Quỹ đạo tròn | K5/K7 | R = const; nếu R đổi dùng tọa độ cực |
| Điểm tiếp xúc lăn | v_tx = 0 | không trượt |

**Thuật toán tọa độ hóa (theo cách tôi hiểu):**
1. Chọn gốc/trục để *tối đa số thành phần bằng 0* (đối xứng).
2. Tham số hóa từng vật: **r**ᵢ(t) theo từng pha.
3. Mọi quan hệ hình học → **phương trình** trên tọa độ (dây: \|**r**_A − **r**_B\| = L; gặp: **r**ᵢ = **r**ⱼ; chạm đường cong: f(x, y) = 0).
4. Vận tốc, gia tốc = đạo hàm; ràng buộc vận tốc = đạo hàm ràng buộc (K6).
5. Đếm #ẩn = #phương trình; giải; **lọc nghiệm** theo miền (t ≥ 0, đúng pha, thành phần nào cũng thỏa).

**Điều kiện đóng kín:** #ẩn = #phương trình độc lập (điều kiện **cần**). Thiếu ⇒ bỏ sót một biến cố hoặc ràng buộc; thừa ⇒ phụ thuộc hoặc mâu thuẫn.

**Duyệt kỷ luật:** với mỗi *vật × phương × pha* viết x(t), v(t); với mỗi *cặp vật* xét: có thể gặp? có ràng buộc nối? cùng gia tốc? (3 câu hỏi đủ để bao hết các CHỖ thường gặp).

**Công cụ phụ để kiểm/đoán CHỖ:** đối xứng thời gian (ném lên–rơi xuống cùng độ cao có cùng tốc độ), phân tích thứ nguyên, trường hợp giới hạn (v₀ → 0, α → 0, 90°).

---

## 5. Ví dụ có lời giải (đã kiểm đại số)

### E1. Gần nhau nhất (K3)
Vị trí tương đối ban đầu **r**₀ = (−8, 6) km, vận tốc tương đối không đổi **v**_rel = (4, 0) km/h. t* = −(**r**₀·**v**_rel)/\|**v**_rel\|² = 32/16 = 2 h; d_min = \|(−8)(0) − 6·4\|/4 = **6 km** (tại t = 2: **r** = (0, 6) ✓).

### E2. Tầm với và đường bao của ném xiên (K2 + K5)
Đặt u = tanα: y = xu − (gx²/2v₀²)(1 + u²). Điểm (x, y) *với tới được* ⇔ phương trình bậc hai theo u có nghiệm thực ⇔
**y ≤ v₀²/(2g) − gx²/(2v₀²)** (parabol an toàn).
- Ném trên mặt phẳng nghiêng góc β lên phía trước (đường y = x tanβ): giao với đường bao cho tầm xa cực đại dọc mặt nghiêng **R_max = v₀²/[g(1 + sinβ)]** (xuống dốc: v₀²/[g(1 − sinβ)]); góc ném so với mặt ngang α = 45° + β/2 (lên dốc).
- β = 0 ⇒ R_max = v₀²/g ✓ (α = 45°).

### E3. Thuyền qua sông (K3 + K2)
Sông rộng d, nước chảy u, tốc độ thuyền so với nước v. Đặt φ = góc giữa vận tốc thuyền (so với nước) và hướng *ngược dòng*: vận tốc so với bờ (u − v cosφ, v sinφ); độ dạt = d(u − v cosφ)/(v sinφ).
- v > u: sang bờ đối diện thẳng khi cosφ = u/v.
- v < u: độ dạt cực tiểu khi **cosφ = v/u**, dạt = **d√(u² − v²)/v**. (Kiểm: v → u⁻ ⇒ 0 ✓.)

### E4. Đo g bằng hai độ cao (K2, Viète)
Thời gian giữa hai lần vật đi qua cùng một mức (lên rồi xuống) tại mức H là T: H = h_max − gT²/8. Với hai mức H₁ < H₂ và khoảng thời gian T₁ > T₂:
**g = 8(H₂ − H₁)/(T₁² − T₂²)** (không cần biết v₀ hay h_max).

### E5. Kim đồng hồ (K7)
Kim phút và kim giờ: ω_rel = 2π(1/60 − 1/720) rad/phút = 2π·11/720 ⇒ trùng nhau mỗi t = 720/11 phút = **12/11 giờ** (≈ 65 5/11 phút) ✓.

### E6. Thanh trượt giữa tường và sàn (K6)
Đầu A trên tường trượt xuống với tốc độ v_A; đầu B trên sàn; φ = góc giữa thanh và sàn. Hình chiếu vận tốc lên thanh bằng nhau ⇒ **v_B = v_A tanφ**. Kiểm bằng tọa độ: x_B = L cosφ, y_A = L sinφ ⇒ \|v_B\|/\|v_A\| = tanφ ✓.

---

## 6. Bẫy kinh điển & tự kiểm

1. **Quãng đường ≠ độ dời:** chia tại v = 0 khi đổi chiều.
2. **Vận tốc trung bình vector ≠ tốc độ trung bình:** đi hai nửa quãng đường với v₁, v₂ ⇒ v_tb = 2v₁v₂/(v₁ + v₂), *không* phải trung bình cộng.
3. **a = 0 tại đỉnh?** Sai. Ở đỉnh v_y = 0 nhưng a = g.
4. **Dùng công thức gia tốc hằng cho nhiều pha** hoặc cho chuyển động tròn (a không hằng).
5. **Nghiệm t âm hoặc ngoài pha** (bị "chạm đất" trước đó) chưa loại.
6. **Gặp nhau:** quên rằng phải *cùng thời điểm* (giao quỹ đạo ≠ gặp nhau).
7. **Dây chùng:** ràng buộc K6 chỉ đúng khi dây căng.
8. **Cộng vận tốc trong HQC quay** dùng như HQC tịnh tiến.
9. **Chuyển động tròn đều có a ≠ 0** (a_n = ω²R).
10. **Dấu:** thống nhất chiều dương từ đầu; g = −9,8 hay +9,8 tùy trục.
11. Kiểm cuối: thứ nguyên, giới hạn, đối xứng, t hợp lệ.

---

## 7. Mức HSGQG vs IPHO (nhận định, cần đối chiếu đề cương)

- **HSGQG:** K1, K2, K3, K5, K7 thường gặp: chuyển động tương đối, ném xiên có điều kiện (với tới, tầm xa cực đại), ràng buộc dây/thanh (K6), bài đồ thị. Chỗ kẹt thường là **chọn HQC/đổi HQC** và **biện luận nghiệm**.
- **IPHO:** thêm tọa độ cong (bán kính cong), tham số hóa/đường bao, tâm quay tức thời, bài nhiều pha với ràng buộc ghép, xấp xỉ (góc nhỏ), đại lượng cực trị bằng đạo hàm. Khó chủ yếu ở **mô hình hóa** (Vấn đề 1).
- **Rèn:** với mỗi bài, ghi (i) cấu trúc K, (ii) danh sách pha, (iii) bảng đếm ẩn–phương trình, (iv) điều kiện lọc nghiệm, *trước khi* thay số.

---

## 8. Chưa có trong bản này (có thể mở rộng theo yêu cầu)

Vật rắn và tâm quay tức thời mở rộng · chuyển động tương đối trong HQC quay (bài nhiều bước) · ném xiên có mặt phẳng nghiêng/phản xạ/va chạm đàn hồi với tường · bài rơi có cản (nối sang Động lực học) · bộ bài tập phân loại theo K1–K7 kèm lời giải · thư viện "họ precondition có tham số" cho từng cấu trúc.
