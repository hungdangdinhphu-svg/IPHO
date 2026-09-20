# THƯ VIỆN CÔNG CỤ & THUẬT TOÁN "TÌM CHỖ" — TĨNH ĐIỆN, TỪ HỌC
*(Hoàn thành Vấn đề 1 = nhận diện công cụ + tiền xử lý; Vấn đề 2 = chuyển Vật Lý → Toán. Không đụng Vấn đề 3.)*

---

## PHẦN A — TUYÊN BỐ TRUNG THỰC (đọc trước)

**Đã kiểm chứng bằng tính số (chạy code):** điện trở tương đương khối lập phương (7R/12, 3R/4, 5R/6); biến đổi Δ–Y; tích phân trường solenoid hữu hạn tại tâm; năng lượng trường của vỏ cầu / cầu đặc (kQ²/2R, 3kQ²/5R); nhiệt tỏa khi nối hai tụ = ½·C₁C₂/(C₁+C₂)·(U₁−U₂)².

**Viết từ kiến thức chuẩn, chưa chạy code:** mọi công thức còn lại. Các công thức mang dấu **[⚠ kiểm lại]** là những chỗ dấu/hệ số dễ sai — hãy tự dẫn xuất lại một lần rồi mới tin.

**Phần "quy trình quét CHỖ" và "họ precondition" là cách hệ thống hoá của tôi trên khung của bạn**, không phải định lý. Tôi không chứng minh nó bao phủ mọi bài IPHO. Tôi chỉ khẳng định: nó bao phủ những cấu trúc lặp đi lặp lại nhiều nhất trong Điện–Từ, và mỗi công cụ đều có (i) điều kiện áp dụng, (ii) trình tự quét cố định, (iii) dạng phương trình đầu ra.

**Nhận xét về README của bạn (để dùng đúng):**
1. Bạn tách `Dom(ℓ)` và `Pre(ℓ)` — đúng và quan trọng. Trong Điện–Từ, ví dụ rõ nhất: định luật Gauss có `Dom` = mọi trường tĩnh (luôn đúng), nhưng để *tính E từ Gauss* thì `Pre` rất hẹp (cần đối xứng). Tôi giữ đúng cách tách này ở dưới.
2. Bạn dùng "điều kiện đủ Suf(ℓ)" làm chìa khoá tìm CHỖ. Tôi đồng ý, nhưng thêm một điểm: trong thực hành, **`Pre` kiểm tra nhanh hơn `Suf`** nên tôi dùng `Pre` để *lọc nhanh*, `Suf` để *khẳng định có ích*. Thẻ công cụ dưới đây có cả hai.
3. "Duyệt từng pixel/từng chữ" là brute-force hợp lý, nhưng có thể **có cấu trúc**: tôi chia thành 7 loại quét (mục C) để việc duyệt không bị mù.
4. Ràng buộc bạn nêu (không máy tính, thời gian thi hữu hạn) → tôi chỉ giữ thuật toán làm được bằng tay (điện thế nút, đối xứng, bảo toàn điện tích...).

---

## PHẦN B — KHUNG CHUNG

### B.1. Thẻ công cụ (mỗi công cụ ℓ phải điền đủ)

```
ℓ        : tên
Dom(ℓ)   : miền mà định luật đúng
Pre(ℓ)   : điều kiện CẦN để dùng được (kiểm nhanh)
Suf(ℓ)   : điều kiện ĐỦ để nó chắc chắn có ích tại CHỖ
Post(ℓ)  : phương trình/ràng buộc sinh ra (đầu ra Toán)
QUÉT     : trình tự cố định tìm CHỖ (không cần trực giác)
Err(ℓ)   : sai số / khi nào vỡ
BẪY      : lỗi thường gặp
```

### B.2. Quy trình tổng (áp dụng cho MỌI bài Điện–Từ)

1. **Phiên dịch (I):** vẽ lại hình; đánh nhãn mọi thực thể (O), mọi đại lượng đã biết/chưa biết (V); ghi Q (cần tìm gì, dạng gì, đơn vị).
2. **Tiền xử lý (T1–T12, mục B.4):** đưa bài về dạng để các công cụ áp dụng được.
3. **Chọn nhóm công cụ (Bảng chẩn đoán, phần F).**
4. **Quét CHỖ** cho từng công cụ theo thẻ (mục C).
5. **Sổ cái ẩn–phương trình (mục B.3):** mỗi (ℓ, CHỖ) ghi một dòng.
6. **Kiểm tra đóng kín:** #phương trình độc lập ≥ #ẩn? Nếu thiếu → quay lại bước 4 với công cụ khác (đặc biệt: bảo toàn, đối xứng, điều kiện biên).
7. **Chuyển sang Vấn đề 3.**
8. **Kiểm tra sau:** thứ nguyên, giới hạn (điều kiện đặc biệt), đối xứng, dấu, năng lượng.

### B.3. Sổ cái ẩn–phương trình (chống "ảo tưởng đã đủ")

| # | Công cụ ℓ | CHỖ | Pre thoả? | Phương trình sinh ra | Ẩn mới | Ghi chú/xấp xỉ |
|---|---|---|---|---|---|---|

Quy tắc: **không được sang Vấn đề 3 khi chưa đếm ẩn vs phương trình**. Đây là điều kiện (3) Completeness và (5) Well-posedness trong README của bạn.

### B.4. Kho phép biến đổi tiền xử lý (T)

| Mã | Biến đổi | Khi nào | Lưu ý |
|---|---|---|---|
| T1 | **Gộp nút:** mọi điểm nối bằng dây lý tưởng = 1 nút; vẽ lại mạch theo nút | luôn làm với mạch điện | Dây lý tưởng ⇒ cùng điện thế |
| T2 | **Đối xứng ⇒ đẳng thế / không dòng:** tìm nút đẳng thế (nối lại/tách ra được), nhánh không dòng (cầu cân bằng) | mạch có đối xứng | Phải chứng minh đối xứng cả nguồn lẫn tải |
| T3 | **Thevenin ↔ Norton** | nguồn có nội trở | Chỉ cho phần tuyến tính |
| T4 | **Gộp nối tiếp/song song, Δ↔Y** | rút gọn | Δ↔Y là biến đổi *tương đương tại 3 đầu ngoài* |
| T5 | **Lý tưởng hoá / mô hình hoá thực:** ampe kế R=0, vôn kế R=∞ *hoặc* coi chúng là điện trở hữu hạn nếu đề nói | dụng cụ đo | Đề cho "vôn kế thực" ⇒ phải đưa R_V vào mạch |
| T6 | **Trạng thái đặc biệt:** t=0⁺ (C→nguồn áp U(0⁻), L→nguồn dòng I(0⁻)), t→∞ (C hở, L nối tắt) | chuyển mạch | Dựa vào tính liên tục u_C, i_L |
| T7 | **Tách chồng chất:** phân bố phức tạp = tổng phân bố đơn giản (kể cả điện tích/dòng ÂM để "khoét lỗ") | có lỗ hổng, hình lệch tâm | Chỉ tuyến tính |
| T8 | **Chọn hệ toạ độ theo đối xứng** (cầu/trụ/phẳng) | tích phân, Gauss/Ampère | Chọn để trường chỉ còn 1 thành phần |
| T9 | **Đổi hệ quy chiếu:** E′ = E + v×B (v << c) | vật chuyển động đều trong từ trường | Cẩn thận: không phải mọi bài đều đơn giản hơn |
| T10 | **Vô thứ nguyên hoá & thang đo:** tìm τ, l, U đặc trưng | phương trình vi phân, giới hạn | Cho ra nhanh dạng nghiệm |
| T11 | **Tương tự (analogy):** tĩnh điện ↔ dòng điện dừng ↔ hấp dẫn ↔ dẫn nhiệt | bài lạ về hình học | Xem mục D.13 (RC = ρε₀ε) |
| T12 | **Xác định các "đảo" (island):** nhóm bản tụ/ vật dẫn không nối nguồn ⇒ tổng điện tích của đảo bảo toàn | mạch tụ | CHỖ quan trọng nhất của mạch tụ |

---

## PHẦN C — 7 LOẠI QUÉT (thuật toán tìm CHỖ có cấu trúc)

Đây là hệ thống hoá của tinh thần "duyệt từng pixel" của bạn. Với bài Điện–Từ, mọi CHỖ rơi vào một trong 7 loại thực thể; quét đủ 7 loại là quét đủ.

| Loại | Liệt kê cái gì | Công cụ liên quan | Cách quét (cố định) |
|---|---|---|---|
| **Q1. Nút** | mọi nút mạch; mọi "đảo" điện tích | KCL; điện thế nút; bảo toàn điện tích | Với mỗi nút: viết Σ(dòng vào) = 0 (hoặc Σ q = const nếu đảo) |
| **Q2. Vòng/Đường** | mọi vòng kín trong mạch; mọi đường đi giữa 2 điểm | KVL; Faraday; Ampère; hiệu điện thế | Với mỗi vòng độc lập: Σ ΔV = 0 (hoặc = −dΦ/dt) |
| **Q3. Mặt kín** | các mặt kín tưởng tượng hợp đối xứng | Gauss; dòng qua mặt | Liệt kê mặt trên đó |E| hằng & ⟂/∥ |
| **Q4. Phần tử** | mỗi điện tích/ hạt/ thanh/ khung/ phần tử dòng | Coulomb, Lorentz, Newton, Biot–Savart | Với mỗi phần tử: liệt kê mọi lực/trường tác dụng |
| **Q5. Đối xứng** | phản xạ, quay, tịnh tiến, đảo ngược, bất biến thang | rút gọn E, B, dòng | Hỏi: phép biến đổi nào giữ nguyên bài? Trường phải giữ nguyên (hoặc đảo dấu đúng quy tắc: E là vectơ cực, B là giả vectơ) |
| **Q6. Đại lượng bảo toàn** | Q, năng lượng, xung lượng, mômen động lượng, thông lượng (siêu dẫn), động lượng chính tắc | mọi bài "trước–sau" | Với mỗi đại lượng: hệ có cô lập không? Có ma sát/ Joule không? |
| **Q7. Biên/Giới hạn** | bề mặt vật dẫn, mặt phân cách điện môi, vô cực, điểm kỳ dị, giới hạn (d→0, R→∞...) | điều kiện biên; kiểm chứng | Ghi điều kiện E_t, D_n, B_n, H_t; kiểm giới hạn cuối bài |

**Quy tắc phản xạ gương (Q5) — dùng để biết hướng E, B trên mặt phẳng đối xứng Π:**

| Phân bố nguồn qua gương Π | Điện tích | E tại điểm trên Π | Dòng điện | B tại điểm trên Π |
|---|---|---|---|---|
| Ảnh gương **giống hệt** (cùng dấu; dòng là ảnh gương của dòng) | ρ(r′)=ρ(r) | **nằm trong Π** (E⊥Π = 0) | J(r′)=phản xạ của J(r) | **vuông góc Π** (B nằm trong Π = 0) |
| Ảnh gương **đảo dấu** | ρ(r′)=−ρ(r) | **vuông góc Π** | J(r′)=−phản xạ của J(r) | **nằm trong Π** |

Cách nhớ: E là vectơ cực, B là giả vectơ nên hai quy tắc "ngược nhau". Kiểm nhanh bằng ví dụ: dây thẳng dài có dòng, Π chứa dây ⇒ B ⟂ Π ✔; hai dây song song cùng chiều dòng, Π ở giữa ⇒ trên Π: B ⟂ Π ✔ (thành phần trong Π triệt tiêu).

**Cách quét Gauss/Ampère (Q3, Q2) không dùng trực giác:**
1. Liệt kê nhóm đối xứng của phân bố (cầu: O(3); trụ dài: tịnh tiến dọc trục + quay quanh trục; mặt phẳng vô hạn: tịnh tiến 2 chiều + quay quanh pháp tuyến).
2. Nhóm đó quyết định *hướng* trường (cầu → hướng kính; trụ → hướng kính; phẳng → pháp tuyến) và *biến phụ thuộc* (r; r; z).
3. Mặt Gauss = mặt "cùng biến phụ thuộc". Nếu không có nhóm đối xứng đủ lớn ⇒ **Gauss không cho E**, phải chuyển sang chồng chất (T7) hoặc tích phân trực tiếp.

---

## PHẦN D — THƯ VIỆN CÔNG CỤ TĨNH ĐIỆN
*(khớp mục 1 trong bảng của bạn: lực–điện trường; điện thế; tụ & năng lượng; mạch–Ohm toàn mạch–mạch phức hợp; công–công suất–nguồn; mạch tụ–trở)*

### D.1. Coulomb + nguyên lý chồng chất (điện tích điểm)
- **Dom:** điện tích đứng yên (hoặc chuyển động chậm, gia tốc nhỏ), môi trường đồng nhất; F₁₂ = k q₁q₂ r̂₁₂ / r², k = 1/(4πε₀) = 8,99·10⁹ N·m²/C².
- **Pre:** (a) mọi điện tích **đã biết vị trí, độ lớn** — nếu có vật dẫn/điện môi gần đó thì điện tích cảm ứng/liên kết là **ẩn**, khi đó Pre *không thoả*; (b) kích thước << khoảng cách, hoặc đã cắt nhỏ thành phần tử điểm.
- **Suf (có ích):** cần lực/gia tốc/cân bằng của một điện tích thử cụ thể.
- **Post:** F_thử = Σ_i k q q_i (r_thử − r_i)/|r_thử − r_i|³ (vectơ).
- **QUÉT (Q4):** (1) chọn hệ toạ độ theo đối xứng; (2) liệt kê MỌI điện tích khác (kể cả điện tích cảm ứng nếu đã tìm được bằng D.5/D.6); (3) viết từng vectơ lực, chiếu; (4) nếu cân bằng: ΣF = 0 ⇒ với nhiều điện tích tự do, viết **cho mỗi điện tích tự do** một phương trình (đếm: n điện tích ⇒ 2–3n phương trình).
- **Err:** vỡ khi tốc độ ~ c (thêm lực từ, trễ). Điện tích điểm tự nó không thể ổn định bằng tĩnh điện (định lý Earnshaw).
- **BẪY:** quên điện tích cảm ứng; nhầm dấu chiều lực; quên hằng số 4π khi dùng ε₀.

### D.2. Điện trường qua tích phân chồng chất
- **Post:** dE = k dq (r − r′)/|r − r′|³, với dq = λ dl, σ dS, hoặc ρ dV.
- **Pre:** phân bố đã biết trước (không phải điện tích cảm ứng chưa biết).
- **Suf:** phân bố có tham số hoá đơn giản (vòng, đĩa, đoạn thẳng, mặt cầu...).
- **QUÉT (Q4+Q5):** (1) chọn điểm quan sát P; (2) tham số hoá phần tử dq bằng **một biến** (góc hoặc toạ độ dọc); (3) viết r − r′ dạng vectơ; (4) **dùng đối xứng (Q5) bỏ thành phần triệt tiêu** *trước* khi tích phân; (5) đổi mọi biến về một biến; (6) đưa về Vấn đề 3 (tích phân một biến).
- **Kết quả chuẩn (dùng làm "viên gạch"):**
  - Vòng tròn bán kính R, tổng Q, trên trục cách tâm z: E = kQz/(R²+z²)^{3/2}, φ = kQ/√(R²+z²).
  - Dây thẳng dài vô hạn: E = 2kλ/r = λ/(2πε₀ r).
  - Mặt phẳng vô hạn σ: E = σ/(2ε₀).
  - Đĩa tròn R, σ, trên trục: E = (σ/2ε₀)(1 − z/√(z²+R²)).
- **BẪY:** cộng độ lớn thay vì cộng vectơ.

### D.3. Định lý Gauss
- **Dom:** ∮E·dS = Q_trong/ε₀ đúng cho **mọi** trường tĩnh (trong điện môi: ∮D·dS = Q_tự do trong).
- **Pre (dùng để TÍNH E):** tồn tại mặt kín trên đó |E| không đổi và E ∥ hoặc ⟂ dS từng phần.
- **Suf:** phân bố có nhóm đối xứng đủ lớn: cầu (O(3)), trụ dài vô hạn, mặt phẳng vô hạn — hoặc tổ hợp qua chồng chất T7.
- **Post:** cầu: E = kQ_trong/r²; trụ: E = λ_trong/(2πε₀ r); phẳng: E = σ/(2ε₀) mỗi bên.
- **QUÉT (Q3+Q5):** theo 3 bước ở mục C: nhóm đối xứng → hướng E & biến → mặt Gauss. Nếu không tìm được ⇒ không dùng Gauss để tính E.
- **Ứng dụng KHÔNG cần đối xứng:** (i) trong vật dẫn E=0 ⇒ ∮E·dS=0 ⇒ điện tích trong bề mặt trong = −(điện tích trong hốc); (ii) tính điện thông; (iii) "khoét lỗ" bằng chồng chất T7: cầu đặc điện tích ρ có hốc cầu lệch tâm ⇒ E trong hốc **đều**: E = ρ a/(3ε₀) (a = vectơ từ tâm cầu lớn đến tâm hốc).
- **BẪY:** áp Gauss cho vật hữu hạn (đĩa, thanh ngắn) như thể vô hạn.

### D.4. Điện thế & hiệu điện thế; bảo toàn năng lượng
- **Dom:** trường tĩnh (rot E = 0). **Không dùng** cho E cảm ứng (xem M.4).
- **Post:** φ_A − φ_B = ∫_A^B E·dl (không phụ thuộc đường); E = −∇φ; công lực điện A_{A→B} = q(φ_A − φ_B); bảo toàn: ½mv² + qφ = hằng.
- **φ của điện tích điểm:** kq/r (mốc ở ∞); **chồng chất vô hướng** ⇒ luôn thử tính φ trước E (đỡ vectơ).
- **Pre (dùng bảo toàn năng lượng):** chỉ có lực điện (+ lực thế khác), không ma sát, không bức xạ.
- **QUÉT (Q1/Q2/Q6):** với mỗi hạt: hai trạng thái đầu–cuối ⇒ viết ½mv²+qφ; với mỗi cặp điểm cần liên hệ: đường đi bất kỳ (chọn đường dễ nhất, ví dụ dọc trục đối xứng).
- **Điểm đối xứng:** E=0 chưa chắc φ=0; φ cực trị dọc trục ⇒ E=0 tại đó (chú ý: chỉ đúng nếu φ là cực trị theo *mọi* hướng).
- **BẪY:** quên mốc thế; nhầm dấu q âm.

### D.5. Vật dẫn ở cân bằng tĩnh điện (công cụ chủ lực của bài tụ/cầu)
- **Dom/Pre:** vật dẫn lý tưởng, tĩnh (không dòng). Suy ra: E_trong = 0; φ = hằng trên cả vật; điện tích tự do chỉ ở mặt ngoài; E ngoài ⟂ mặt, E = σ/ε₀ sát mặt; áp lực tĩnh điện p = σ²/(2ε₀) = ½ε₀E² hướng ra ngoài. Hốc rỗng không có điện tích: E = 0 trong hốc (lồng Faraday).
- **Suf (có ích):** có vật dẫn nối nhau, nối đất, hoặc cô lập.
- **Thuật toán "mỗi vật dẫn = 1 cặp (Q_i, φ_i)":**
  1. Mỗi vật dẫn i có hai đại lượng Q_i, φ_i. **Đề luôn cho một trong hai** (Q_i cố định nếu cô lập; φ_i = 0 nếu nối đất; φ_i = U nếu nối nguồn; φ_i = φ_j nếu nối dây).
  2. Nối dây giữa i và j ⇒ φ_i = φ_j **và** Q_i + Q_j bảo toàn (nếu hệ i,j cô lập).
  3. Quan hệ tuyến tính: Q_i = Σ_j C_ij φ_j (hệ số điện dung, C_ii>0, C_ij<0). Với hệ cầu đồng tâm tính C_ij bằng Gauss.
  4. Đủ phương trình khi mỗi vật dẫn cho đúng 1 điều kiện (Q hoặc φ).
- **Cầu đồng tâm (thường gặp):** với vỏ trong bán kính a điện tích q_a, vỏ ngoài bán kính b: φ_a − φ_b = k q_a(1/a − 1/b). Điện tích cảm ứng mặt trong vỏ ngoài = −q_a; mặt ngoài vỏ ngoài = Q_b + q_a (Q_b = tổng điện tích vỏ ngoài).
- **Hai cầu nối dây, cách xa:** φ bằng nhau ⇒ q₁/R₁ = q₂/R₂; σ ∝ 1/R (mật độ điện tích lớn ở chỗ nhọn).
- **BẪY:** quên rằng điện tích **mặt trong** và **mặt ngoài** là hai ẩn khác nhau; quên bảo toàn tổng điện tích khi vật dẫn cô lập.

### D.6. Phương pháp ảnh điện (image method)
- **Dom:** nghiệm Poisson–Laplace trong miền có biên là vật dẫn (φ = hằng), **nghiệm duy nhất** (định lý duy nhất).
- **Pre (bắt buộc):** biên là vật dẫn có hình dạng đặc biệt: **mặt phẳng** hoặc **mặt cầu** (cũng gồm mặt trụ cho dây thẳng); nguồn là điện tích điểm/đường.
- **Post:**
  - Mặt phẳng nối đất, điện tích q cách mặt d ⇒ ảnh −q đối xứng qua mặt; lực hút F = kq²/(2d)².
  - Cầu nối đất bán kính R, q cách tâm d>R ⇒ ảnh q′ = −qR/d tại khoảng R²/d từ tâm (cùng phía). Cầu **cô lập**, tổng điện tích Q: thêm ảnh q″ = Q − q′ = Q + qR/d **ở tâm** (với Q=0: q″ = +qR/d).
  - Mật độ điện tích cảm ứng trên mặt phẳng: σ = −qd/(2π(d²+ρ²)^{3/2}); tổng = −q.
- **QUÉT (Q7):** (1) đánh dấu mọi mặt vật dẫn; (2) nếu là mặt phẳng/cầu, đặt ảnh sao cho φ = hằng (0 nếu nối đất) trên mặt; (3) tính trường trong **miền thực** chỉ bằng nguồn thật + ảnh; (4) lực = lực từ ảnh (chỉ ở miền thực).
- **BẪY LỚN (năng lượng):** công đưa q từ ∞ đến d = −kq²/(4d) (**một nửa** năng lượng tương tác thật–ảnh vì ảnh không phải điện tích thật); tính lực rồi tích phân ∫F dd để có đúng.
- **Err:** vỡ với biên hình dạng tuỳ ý.

### D.7. Lưỡng cực & trường xa
- p = q d (hướng từ − sang +). Trường: φ = k p cosθ/r²; E_r = 2kp cosθ/r³, E_θ = kp sinθ/r³. Mômen lực τ = p × E; thế năng U = −p·E; lực F = (p·∇)E.
- **Vật dẫn cầu R trong điện trường đều E₀:** φ = −E₀(r − R³/r²)cosθ (r>R); tương đương lưỡng cực p = 4πε₀R³E₀; σ = 3ε₀E₀cosθ.
- **Pre:** quan sát ở xa so với kích thước phân bố (khai triển đa cực); phân bố trung hoà.
- **Dùng khi:** phân tử phân cực; hạt trong trường ngoài; dao động nhỏ quanh cân bằng của lưỡng cực.

### D.8. Điện môi tuyến tính (khi đề có chất cách điện trong tụ)
- **Dom/Pre:** đồng nhất, đẳng hướng, tuyến tính (D = εε₀E).
- **Điều kiện biên tại mặt phân cách (không có điện tích tự do bề mặt):** thành phần **tiếp tuyến** của E liên tục; thành phần **pháp tuyến** của D liên tục.
- **Hệ quả tụ phẳng:** lớp điện môi **song song** bản (nối tiếp về mặt tụ, D liên tục): C⁻¹ = Σ d_i/(ε_i ε₀ S). Lớp điện môi **vuông góc** bản (song song về mặt tụ, E liên tục): C = ε₀ Σ ε_i S_i/d.
- **Lực kéo tấm điện môi vào tụ (nối nguồn U, chiều rộng w, khoảng cách d):** F = ε₀(ε−1)wU²/(2d) (bỏ hiệu ứng mép).
- **BẪY:** nhầm "giữ nguyên U" với "giữ nguyên Q" khi tính lực/năng lượng (xem D.9).

### D.9. Tụ điện — định nghĩa, ghép, năng lượng, lực (CỐT LÕI của mục "Tụ điện, năng lượng của tụ điện")
- **Định nghĩa C = Q/U:** **Pre:** hai vật dẫn mang điện ±Q (mọi đường sức từ vật này kết thúc ở vật kia) ⇒ nếu có vật dẫn thứ ba/điện tích ngoài thì phải dùng ma trận C_ij (D.5).
- **Công thức chuẩn:** phẳng εε₀S/d; cầu (hai vỏ a<b) 4πε₀ εab/(b−a); trụ 2πε₀ε L/ln(b/a); cầu cô lập bán kính R: 4πε₀R.
- **Ghép:** song song ΣC_i (cùng U); nối tiếp 1/C = Σ1/C_i (cùng Q). **Pre của "nối tiếp":** các bản nối giữa hai tụ là *đảo cô lập* (không có nhánh khác đi vào) ⇒ Q bằng nhau. Nếu còn nhánh thứ ba ⇒ **không phải nối tiếp**, phải dùng thuật toán nút.
- **Năng lượng:** W = Q²/(2C) = CU²/2 = QU/2; mật độ ½ε₀E² (½εε₀E² trong điện môi). Nhiều vật dẫn: W = ½ΣQ_iφ_i.
- **THUẬT TOÁN MẠCH TỤ (thuộc T12, Q1) — điện thế nút cho tụ:**
  1. Đặt tên mỗi nút (nút = nhóm bản nối bằng dây). Nút nối nguồn áp lý tưởng: φ đã biết (biết luôn cả nút đất φ=0).
  2. Với mỗi nút **tự do (đảo)** i: viết Σ_j C_ij(φ_i − φ_j) = Q_i⁰ (tổng điện tích ban đầu của các bản thuộc nút đó — thường bằng 0 nếu ban đầu chưa tích điện).
  3. Giải hệ (số phương trình = số nút tự do).
  - **Tương tự với điện trở:** C_ij ↔ độ dẫn G_ij = 1/R_ij, điện tích đảo ↔ dòng bơm vào nút. Toàn bộ phương pháp điện thế nút của điện trở dùng được, chỉ đổi ký hiệu.
  - Nguồn có emf ξ nối tiếp tụ: đưa ξ vào hiệu thế của nhánh: q = C(φ_i − φ_j + ξ_{ij}) (dấu theo quy ước D.15).
- **Chuyển mạch/ nối hai tụ:** đảo tụ cô lập: Q tổng bảo toàn; nếu nối ± cùng dấu: U_cuối = (C₁U₁+C₂U₂)/(C₁+C₂); nhiệt Joule = ½[C₁C₂/(C₁+C₂)](U₁−U₂)² **(đã kiểm)** — **không phụ thuộc điện trở nối** (miễn không bức xạ).
- **Nạp tụ qua nguồn ξ từ q=0:** A_nguồn = Qξ = Cξ²; W_tụ = ½Cξ²; nhiệt = ½Cξ² (độc lập R).
- **Lực giữa hai bản/ dịch chuyển:** F = −(∂W/∂x)_Q = +(∂W/∂x)_U (**dấu + vì nguồn thực hiện công**); tụ phẳng: F = Q²/(2ε₀S) = ε₀SU²/(2d²).
  - *Cô lập Q*: W = Q²/2C, tách bản ra ⇒ W tăng, công ngoài = ΔW.
  - *Nối nguồn U*: A_nguồn = UΔQ = ΔW + A_cơ + nhiệt; ΔW ≠ A_cơ **(bẫy lớn nhất của mục này)**.
- **QUÉT:** (Q1) mọi đảo và mọi nút; (Q6) đại lượng nào giữ nguyên: Q hay U?; (Q7) điều kiện biên tại bản.
- **Err:** bỏ hiệu ứng mép; tụ lý tưởng bỏ qua điện trở/độ tự cảm dây.

### D.10. Năng lượng hệ điện tích & phương pháp công ảo
- **Post:** W = ½Σ_i q_iφ_i (φ_i do các điện tích *khác*) = Σ_{i<j} kq_iq_j/r_ij; liên tục: ½∫ρφ dV = ∫½ε₀E²dV.
- **Tự năng lượng (đã kiểm):** vỏ cầu tích điện: kQ²/(2R); quả cầu đặc đều: 3kQ²/(5R).
- **Công ảo:** F_x = −∂W/∂x (giữ các điện tích cố định) — đặc biệt tiện với hệ đối xứng nơi tính lực trực tiếp khó. Cách tính "áp suất lên mặt vật dẫn": p = ½ε₀E² (E ngay ngoài mặt).
- **Ổn định:** cân bằng tĩnh điện thuần (điện tích điểm) không ổn định (Earnshaw); vật dẫn/ có ràng buộc thì có thể ổn định.

### D.11. Chuyển động hạt tích điện trong điện trường
- **Đều:** parabol (như ném xiên); bảo toàn năng lượng: ½mv² = qU.
- **Lực xuyên tâm (điện tích điểm):** tương tự hấp dẫn: thay GMm → −kq₁q₂ (thế tương tác **đẩy** cho cùng dấu ⇒ quỹ đạo hyperbol; Rutherford). Bảo toàn L = mr²φ̇ và E cơ.
- **QUÉT (Q6):** năng lượng ✔; mômen động lượng nếu lực xuyên tâm ✔; xung lượng nếu tịnh tiến bất biến ✔.

### D.12. Dòng điện dừng, định luật Ohm (vi mô & vĩ mô)
- **Post:** I = ∫J·dS = nqvS; J = σE; R = ρl/S (đồng nhất); tổng quát R = ∫ρ dl/S(l) (dây có tiết diện thay đổi từ từ).
- **Điện trở theo hình học:** vỏ cầu đồng tâm a<b: R = (ρ/4π)(1/a − 1/b); tiếp đất bán cầu: R = ρ/(2πa); trụ đồng trục: R = ρ ln(b/a)/(2πL).
- **Điều kiện dòng dừng (Pre của KCL):** ∇·J = 0, không tích luỹ điện tích tại nút.
- **Bản chất:** mạch điện dừng là bài toán Laplace ∇²φ = 0 trong môi trường dẫn ⇒ dùng lại được mọi công cụ D.2–D.7 (đối xứng, ảnh...).

### D.13. TƯƠNG TỰ mạnh: dòng ↔ tĩnh điện (T11) — "RC = ρε₀ε"
- Hai điện cực cùng hình dạng trong **cùng một môi trường đồng nhất**: điện dung C (điện môi ε) và điện trở R (điện trở suất ρ) thoả **R·C = ρ ε ε₀**.
- Dùng khi: tính điện trở giữa hai vật dẫn hình học phức tạp mà điện dung đã biết (hoặc ngược lại); dòng rò qua tụ có điện môi không hoàn hảo; hằng số thời gian tự phóng điện: τ = ρεε₀.
- **Pre:** mọi dòng đi qua từ điện cực này sang điện cực kia, môi trường đồng nhất, điện cực đẳng thế.

### D.14. Nguồn điện, Ohm toàn mạch, công–công suất
- **Nguồn:** ξ (suất điện động), nội trở r: U = ξ − Ir khi phát; máy thu (ξ′, r′): U = ξ′ + Ir′.
- **Toàn mạch:** I = Σξ/ΣR (một vòng, cùng chiều dòng: ξ nào ngược chiều dòng thì lấy dấu −).
- **Ohm cho nhánh chứa nguồn:** đi từ A đến B theo chiều dòng I: φ_B = φ_A − IR_tổng + Σε (ε>0 nếu đi từ cực − sang cực + của nguồn). Đây là quy tắc *duy nhất* nên dùng để chống nhầm dấu.
- **Công suất:** P = UI = I²R = U²/R (điện trở); nguồn phát: P_ng = ξI; hiệu suất H = U/ξ = R/(R+r). **Cực đại công suất trên R tải khi R = r: P_max = ξ²/(4r)** (H = 50%). Với tải là biến trở nối tiếp R₀: cực đại khi R = r + R₀ cho công suất trên R.
- **Bảo toàn:** ξI = I²(R+r) (nguồn thuần trở); nhánh có tụ đang nạp: ξI = I²R + d(W_C)/dt.
- **Pre:** dòng dừng (hoặc chậm đủ để bỏ qua trường cảm ứng).
- **BẪY:** cực đại công suất trên nguồn ≠ cực đại công suất trên tải; công suất cực đại theo R khác cực đại theo biến khác.

### D.15. THUẬT TOÁN GIẢI MẠCH ĐIỆN (trả lời trực tiếp ví dụ mạch điện của bạn)
**Bước 0 — Tiền xử lý:** T1 (gộp nút), T2 (đối xứng), T3, T4, T5.

**Bước 1 — Đếm & chọn phương pháp:** cho mạch có b nhánh, n nút:
- Kirchhoff thuần: ẩn = b dòng ⇒ n−1 phương trình KCL + (b−n+1) KVL. Tay chậm.
- **Điện thế nút:** ẩn = n−1 điện thế (hoặc ít hơn nếu có nguồn áp lý tưởng, cộng thêm kỹ thuật "siêu nút"). Ưu tiên khi n−1 < b−n+1.
- **Dòng mắt lưới (mesh):** ẩn = b−n+1 dòng vòng. Ưu tiên khi mạch phẳng ít vòng.
- Chọn cái có **ít ẩn hơn**.

**Bước 2 — Điện thế nút, "lập ma trận bằng quy tắc" (chính là cái "pattern" bạn nói):**
- Quy ước dòng nhánh i→j qua điện trở R_ij nối tiếp nguồn ε_ij: I_ij = G_ij(φ_i − φ_j + ε_ij), ε_ij > 0 nếu đi i→j vượt nguồn từ − sang +.
- KCL nút i: **Σ_j G_ij(φ_i − φ_j) = J_i − Σ_j G_ij ε_ij**, với J_i = dòng ngoài bơm vào nút i.
- Ma trận: đường chéo = tổng độ dẫn nối vào nút; ngoài chéo = −G_ij; vế phải = J_i − Σ G_ijε_ij. Ma trận **đối xứng** (kiểm chứng bằng cách so sánh).
- Nút tham chiếu φ = 0 (chọn nút nối nhiều nguồn nhất); nếu có nguồn áp lý tưởng giữa 2 nút ⇒ φ_i − φ_j = ε (một ràng buộc thay cho một phương trình KCL, dùng KCL tổng cho cả siêu nút).
- Với tụ: G_ij → jωC_ij (xoay chiều) hoặc dùng Q_i (D.9).

**Bước 3 — Công cụ hỗ trợ khi có cấu trúc:**
- **Đối xứng (T2, Q5):** hai nhánh đối xứng qua trục; nút nằm trên trục đối xứng gương của bài (nguồn cũng đối xứng) ⇒ đẳng thế ⇒ nối/tách. Khối lập phương (mỗi cạnh R): R_(kề) = 7R/12, R_(chéo mặt) = 3R/4, R_(chéo khối) = 5R/6 **(đã kiểm)**.
- **Cầu Wheatstone:** cân bằng khi R₁/R₂ = R₃/R₄ ⇒ nhánh giữa không dòng (bỏ đi hoặc nối tắt tuỳ tiện).
- **Δ ↔ Y (đã kiểm):** Δ→Y: R₁ = R_aR_b/(R_a+R_b+R_c), với R_a, R_b là hai điện trở Δ kề nút 1. Y→Δ: R_ij = (R₁R₂+R₂R₃+R₃R₁)/R_k (R_k là điện trở Y ở nút đối diện).
- **Chồng chất (chỉ tuyến tính):** triệt nguồn áp ⇒ nối tắt; triệt nguồn dòng ⇒ hở. Dùng khi có nhiều nguồn ở xa nhau hoặc cần tách "phần đối xứng + phản đối xứng".
- **Thevenin/Norton:** thay phần mạch tuyến tính bên ngoài một đôi cực bằng (U_hở, R_th). Nên dùng khi chỉ quan tâm một nhánh tải.
- **Mạch vô hạn tuần hoàn/tự đồng dạng:** nếu bớt một mắt mà mạch không đổi ⇒ R_x = f(R_x) (phương trình đại số). Lưới vuông vô hạn: điện trở giữa hai nút kề = R/2; chéo = 2R/π.
- **Cắt mạch theo trục đối xứng:** nếu dòng đi vào/ra đối xứng qua một trục thì mỗi nhánh nằm *trên* trục có thể chẻ đôi: hai điện trở R song song cùng chỗ ⇔ một điện trở R/2, hoặc một điện trở nằm trên trục ⇔ hai điện trở 2R song song (tuỳ chiều chẻ). Mục đích: giảm số nút rồi dùng T4.
- **Phần tử phi tuyến (đèn, diode):** vẽ đặc tuyến I(U) và **đường tải** (U = ξ − Ir hoặc tương đương Thevenin); giao điểm = điểm làm việc. Diode lý tưởng: chia trường hợp (mở/khoá) ⇒ **Case Completeness**: thử từng tổ hợp, chọn tổ hợp tự nhất quán.
- **Dụng cụ đo thực:** ampe kế = điện trở nhỏ nối tiếp; vôn kế = điện trở lớn song song (T5).

**Bước 4 — Kiểm tra:** ΣP_nguồn = ΣP_tiêu thụ; dòng tại nút cân bằng; giới hạn R→0/∞.

### D.16. Mạch chứa tụ & điện trở — trạng thái dừng
- **Dòng một chiều ổn định:** tụ = hở (không dòng nhưng **có** hiệu điện thế). Trình tự: (1) bỏ nhánh tụ, giải mạch điện trở ⇒ mọi dòng và mọi φ nút; (2) hiệu điện thế trên tụ = φ hai bản (đi theo bất kỳ đường nào qua các phần tử đã biết dòng, dùng quy tắc D.14; đường đi qua tụ khác cho cùng kết quả — kiểm chứng chéo).
- **Đảo điện tích:** dùng D.9 (thuật toán nút cho tụ). Mạch hỗn hợp: tính φ mọi nút từ phần điện trở trước (dòng dừng), rồi dùng φ đó làm điều kiện biên cho phần tụ.

### D.17. Mạch RC (quá độ) — thuật toán cố định
- **Dom:** thông số dồn (kích thước mạch << bước sóng), tuyến tính, thời gian đặc trưng >> L/c.
- **Nguyên lý:** u_C và q **liên tục** khi dòng hữu hạn (không nhảy).
- **QUÉT (Q1+Q6+T6):**
  1. **Trước chuyển mạch:** tính trạng thái dừng (tụ hở) ⇒ u_C(0⁻), các Q_đảo.
  2. **Ngay sau chuyển mạch (0⁺):** u_C(0⁺)=u_C(0⁻); *ngoại lệ*: nếu chuyển mạch tạo nối 2 tụ trực tiếp (không R) hoặc nối nguồn áp lý tưởng vào tụ ⇒ có xung dòng ⇒ dùng **bảo toàn tổng Q của đảo** tại đúng thời điểm đó (bảo toàn Q, không bảo toàn năng lượng).
  3. **t → ∞:** tụ hở ⇒ giá trị dừng x_∞.
  4. **τ = R_th·C_th:** R_th nhìn từ hai đầu tụ (triệt nguồn: nguồn áp ⇒ nối tắt).
  5. **Bậc nhất (chỉ 1 tụ độc lập sau khi gộp):** x(t) = x_∞ + (x₀ − x_∞)e^{−t/τ}.
  6. **Nhiều tụ độc lập:** với mỗi đảo i: Σ_j C_ij d(φ_i−φ_j)/dt = −Σ_j G_ij(φ_i−φ_j+ε_ij) + J_i ⇒ hệ ODE bậc nhất tuyến tính (số ẩn = số đảo) ⇒ giá trị riêng (Vấn đề 3) hoặc biến đổi Laplace.
- **Năng lượng:** ∫I²R dt = nhiệt; nạp tụ từ 0 qua nguồn ξ: nhiệt = ½Cξ² (đặc trưng độc lập R). Xả tụ qua R: nhiệt = W ban đầu = ½CU².
- **BẪY:** áp e^{−t/RC} cho mạch có nhiều tụ hoặc nhiều R mà chưa tính R_th, C_th đúng; nhầm u_C(0⁺) khi mạch có nguồn nối lại.

---

## PHẦN E — THƯ VIỆN CÔNG CỤ TỪ HỌC
*(khớp mục 2: từ trường–Biot–Savart; lực từ; cảm ứng điện từ; tự cảm; dòng xoay chiều)*

### M.1. Từ trường & định luật Biot–Savart
- **Dom:** dòng dừng (hoặc biến đổi chậm, quasi-tĩnh); dB = (μ₀/4π) I dl × r̂/r²; điện tích chuyển động chậm (v<<c): B = (μ₀/4π) q v × r̂/r².
- **Pre:** dòng điện là **đường/khối kín** (∇·J = 0); phần tử dòng đơn độc không có ý nghĩa vật lý riêng.
- **Suf:** hình dạng dây tham số hoá được (thẳng, cung tròn, vòng).
- **QUÉT (Q4+Q5):** (1) tham số hoá dây bằng một biến; (2) viết dl và r − r′ dạng vectơ; (3) **tích vectơ dl × (r−r′)**: xác định hướng bằng quy tắc bàn tay phải; (4) dùng đối xứng (Q5, bảng gương) bỏ thành phần triệt tiêu; (5) đưa về 1 tích phân.
- **Kết quả chuẩn:**
  - Dây thẳng dài vô hạn: B = μ₀I/(2πr).
  - Đoạn thẳng hữu hạn, cách dây d: B = (μ₀I/4πd)(sinα₂ − sinα₁) (α đo từ pháp tuyến).
  - Tâm cung tròn góc θ: B = μ₀Iθ/(4πR); vòng tròn: μ₀I/(2R).
  - Trên trục vòng: B = μ₀IR²/[2(R²+z²)^{3/2}]. Helmholtz (hai vòng cách nhau R): từ trường gần đều ở giữa.
  - Solenoid vô hạn: B = μ₀nI trong, 0 ngoài. **Hữu hạn (đã kiểm ở tâm):** B_trục = (μ₀nI/2)(cosα₁ + cosα₂), α là góc giữa trục và đường từ điểm khảo sát đến mép vòng ở hai đầu (điểm nằm giữa hai đầu).
- **BẪY:** sai dấu ở tích vectơ; dùng công thức "dây vô hạn" cho dây ngắn.

### M.2. Định luật Ampère (+ dòng điện dịch Maxwell)
- **Dom:** ∮B·dl = μ₀(I_qua + ε₀dΦ_E/dt).
- **Pre (để TÍNH B):** tồn tại đường kín trên đó |B| hằng và B ∥ dl (hoặc ⟂ dl) từng phần — đúng khi có đối xứng đủ lớn.
- **Suf:** dòng thẳng dài / hình trụ; solenoid dài / xuyến; tấm phẳng vô hạn. QUÉT theo mục C (nhóm đối xứng → hướng B & biến → đường Ampère).
- **Post:** dây trụ đặc bán kính a, dòng đều: r<a: B = μ₀Ir/(2πa²); r>a: μ₀I/(2πr). Xuyến N vòng: B = μ₀NI/(2πr). Tấm phẳng dòng mặt K: B = μ₀K/2 mỗi bên.
- **Khoét lỗ (T7):** trụ có hốc trụ lệch tâm, mật độ dòng J đều ⇒ B **đều** trong hốc: B = (μ₀/2) J × a (a = vectơ từ trục trụ lớn đến trục hốc) (dẫn xuất: B_trụ lớn − B_trụ nhỏ = (μ₀/2)J ẑ×r − (μ₀/2)J ẑ×(r−a); với J = Jẑ.)
- **Dòng dịch (tụ nạp):** trong tụ tròn bán kính R, r<R: B = μ₀rI/(2πR²) (E biến thiên đều theo thời gian).
- **BẪY:** áp Ampère khi không có đối xứng; quên dòng dịch khi đường đi luồn qua khe tụ.

### M.3. Lực từ & chuyển động hạt/dây trong từ trường
- **Post:** F = q(E + v×B); dF = I dl × B; hai dây thẳng song song: F/l = μ₀I₁I₂/(2πd), **hút** nếu cùng chiều.
- **Khung dây:** mômen từ m = I S n̂; mômen lực τ = m × B; thế năng U = −m·B; lực trong từ trường không đều (m cố định): F = ∇(m·B).
- **Hạt trong B đều:** lực từ không sinh công ⇒ |v| hằng; r = mv_⊥/(qB), T = 2πm/(qB) (không phụ thuộc v); quỹ đạo xoắn ốc (bước = v_∥T).
- **E ⟂ B đều:** hạt trôi với v_d = E×B/B² (nếu E << cB); chọn vận tốc: v = E/B.
- **Hiệu ứng Hall (đã cân bằng):** U_H = IB/(n q t) (t = bề dày *dọc theo* B); dấu U_H cho biết dấu hạt tải.
- **QUÉT & kỹ thuật giải nhanh:**
  1. **Xung lượng cho B đều:** mΔv = qΔr × B (vì ∫v×B dt = Δr×B) — đôi khi không cần giải phương trình chuyển động.
  2. **Xung dòng ngắn qua thanh dài l:** mv = B l ∫I dt = B l q.
  3. **Đối xứng trục (từ trường tĩnh, không E_φ):** mômen động lượng chính tắc bảo toàn: m r²φ̇ + qΦ(r)/(2π) = hằng (Φ(r) = từ thông qua đĩa bán kính r) — nắm được cái này là giải xong nhiều bài từ trường không đều.
  4. Hạt đi vào mép từ trường vuông góc: đối xứng ⇒ góc ra bằng góc vào (khi biên phẳng).
- **Err:** v ~ c ⇒ dùng động lượng tương đối tính p = γmv trong r = p/(qB).
- **BẪY:** cho rằng lực từ sinh công; nhầm "công của lực từ" trên dây chuyển động với lực Lorentz lên electron (công cơ của lực Ampère được bù bằng công của nguồn/ε cảm ứng, xem M.4).

### M.4. Cảm ứng điện từ (Faraday–Lenz) — mục trung tâm
- **Dom:** ∮_C E·dl = −dΦ/dt (Φ = ∫_S B·dS qua mặt tựa lên C); ε = ∮(E + v×B)·dl cho vòng dây chuyển động.
- **Pre (dùng "ε = −dΦ/dt" trực tiếp):** (a) vòng dây **là một vật liệu xác định** (các hạt tải của vòng không đổi) *hoặc* biên vòng được định nghĩa rõ ràng theo thời gian; (b) Φ(t) tính được. **Cẩn trọng khi có tiếp điểm trượt** (đĩa Faraday, con chạy): ưu tiên tính ε = ∫(v×B)·dl trên phần dây thực sự chuyển động (Cách B).
- **Hai cách tính ε (luôn dùng cả hai để kiểm chứng chéo):**
  - **Cách A (thông lượng):** viết Φ(t) = B·S(t); ε = −dΦ/dt.
  - **Cách B (lực Lorentz lên phần tử):** ε = ∫(v×B)·dl trên từng đoạn chuyển động.
- **QUÉT (Q2, Q6):**
  1. Chọn chiều dương của vòng ⇒ chiều pháp tuyến ⇒ dấu Φ (**quy tắc: chọn chiều dòng dương trước, rồi Φ theo bàn tay phải**).
  2. Viết Φ(t) theo các biến (vị trí x, góc θ, B(t)).
  3. ε = −dΦ/dt (dấu − đã chứa Lenz; kiểm chiều bằng Lenz: cảm ứng chống lại biến thiên).
  4. **Mạch tương đương điện:** ε nối tiếp R, L (điện áp L dI/dt), C (q/C); viết KVL: ε = IR + L dI/dt + q/C.
  5. **Phương trình cơ:** m dv/dt = F_ngoài − B l I (lực Ampère chống chuyển động).
  6. Nối hai phương trình bằng I và v ⇒ hệ đóng.
- **Kết quả chuẩn (thanh khối lượng m, dài l, trượt trên ray, B ⟂ mặt phẳng):**
  - ε = Blv.
  - Có R, không F: v(t) = v₀e^{−t/τ}, τ = mR/(B²l²); quãng đường dừng = mv₀R/(B²l²); điện lượng q = ΔΦ/R = Blx/R.
  - Có F không đổi: v_giới hạn = FR/(B²l²).
  - Nối **tụ** C (R≈0): gia tốc a = F/(m + CB²l²) — *khối lượng hiệu dụng tăng thêm CB²l²*.
  - Nối **cuộn** L (R≈0), không F: v'' = −(B²l²/(mL))v ⇒ dao động điều hoà ω = Bl/√(mL).
- **Điện lượng qua mạch:** q = ΔΦ/R_tổng (I = ε/R, không cần biết quy luật theo thời gian nếu bỏ qua tự cảm khi tính tổng điện lượng, hoặc nếu dòng đầu=cuối=0). **[Đây là kỹ thuật "bỏ qua động lực học" rất mạnh cho bài va chạm ngắn.]**
- **Điện trường xoáy (B biến thiên trong vùng trụ bán kính a):** trong r<a: E_φ = −(r/2)dB/dt; ngoài r>a: E_φ = −(a²/2r)dB/dt (**không** thế: hiệu điện thế giữa hai điểm phụ thuộc đường đi).
- **Thanh quay quanh đầu, tốc độ góc ω:** ε = ½Bωl²; đĩa Faraday bán kính R: ε = ½BωR² (từ tâm đến rìa).
- **Năng lượng:** công suất cơ = công suất điện (thuần trở): Fv = I²R = (Blv)²/R; nếu có L: Fv = I²R + d(½LI²)/dt.
- **Dòng xoáy (eddy):** khi khối dẫn chuyển động/ B biến thiên ⇒ dòng cảm ứng ⇒ lực hãm; ước lượng cỡ bằng cách lấy mạch "tương đương" đơn giản (một vòng có R ~ ρ·chu vi/tiết diện).
- **BẪY:** dấu (chiều dòng, chiều lực); dùng ε = −dΦ/dt khi Φ đổi vì đổi mạch chứ không phải vì chuyển động vật liệu; khi tính hiệu điện thế hai đầu thanh, nhớ **U ≠ ε** khi có điện trở trong.

### M.5. Tự cảm, hỗ cảm, năng lượng từ
- **Dom/Pre:** mạch tuyến tính (không lõi sắt bão hoà); thông số dồn.
- **Post:** Φ = LI; ε_tc = −L dI/dt; W = ½LI²; mật độ năng lượng từ B²/(2μ₀).
- **Giá trị thông dụng:** solenoid dài: L = μ₀N²S/l = μ₀n²V; xuyến (tiết diện nhỏ): μ₀N²S/(2πR); dây đồng trục (độ tự cảm ngoài) trên đơn vị dài: (μ₀/2π)ln(b/a).
- **Hỗ cảm:** ε₁ = −L₁dI₁/dt − M dI₂/dt; M = k√(L₁L₂), 0≤k≤1; nối tiếp L = L₁+L₂ ± 2M; năng lượng W = ½L₁I₁² + ½L₂I₂² + MI₁I₂ **(dấu MI₁I₂ theo quy ước chiều dòng)**; biến áp lý tưởng (k=1, L→∞): U₁/U₂ = N₁/N₂, I₁/I₂ = N₂/N₁.
- **Điều kiện liên tục:** i_L **liên tục** khi điện áp hữu hạn; nếu ngắt mạch đột ngột với nhánh song song R: dòng qua L chuyển sang R, năng lượng ½LI² toả nhiệt (không phụ thuộc R).
- **Mạch siêu dẫn (R=0):** từ thông qua mỗi vòng **bảo toàn**: L₁I₁ + MI₂ = hằng (mỗi vòng). Dùng cho bài "đưa vòng siêu dẫn vào từ trường".
- **QUÉT (Q6, T6):** t=0⁺: cuộn dây coi như nguồn dòng I(0⁻); t=∞: cuộn dây ngắn mạch (dừng); τ = L/R_th (R_th nhìn từ hai đầu cuộn, nguồn triệt tiêu).
- **Mạch RL:** I(t) = (ξ/R)(1−e^{−Rt/L}); tắt: I₀e^{−Rt/L}.
- **Mạch LC:** ω₀ = 1/√(LC); q(t)=q₀cos(ω₀t) khi bắt đầu từ tụ tích điện; năng lượng ½Li² + q²/2C = hằng.
- **RLC nối tiếp (tắt dần):** ω′ = √(1/LC − R²/4L²); tới hạn khi R = 2√(L/C).
- **BẪY:** quên L "phản ứng chống lại thay đổi dòng", nên ngay sau chuyển mạch dòng qua L KHÔNG nhảy; hỗ cảm dấu M phụ thuộc chiều quấn.

### M.6. Dòng điện xoay chiều — dùng công cụ mạch một chiều qua số phức
- **Dom/Pre:** mạch tuyến tính, tần số đơn, trạng thái **xác lập** (bỏ quá độ), thông số dồn. (Tần số đa thành phần: chồng chất theo từng tần số; công suất trung bình cộng theo từng thành phần, do trực giao.)
- **Post (phasor):** u = U₀cos(ωt+φ) ↔ Ũ = U₀e^{jφ}; Z_R = R, Z_L = jωL, Z_C = 1/(jωC). **Mọi công cụ D.15 (Kirchhoff, điện thế nút, Thevenin, chia áp...) dùng nguyên vẹn với Z thay R.**
- **QUÉT:** (1) chuyển từng phần tử sang Z; (2) áp dụng thuật toán điện thế nút (D.15) với G_ij = 1/Z_ij ⇒ hệ phức; (3) lấy phần thực/độ lớn/pha ở cuối.
- **Công thức chuẩn:** |Z| = √(R² + (ωL − 1/ωC)²); tanφ = (ωL − 1/ωC)/R; giá trị hiệu dụng U = U₀/√2 (sin thuần); P_TB = UI cosφ = I²R; hệ số công suất cosφ.
- **Cộng hưởng nối tiếp:** ω₀ = 1/√(LC); Z = R (cực tiểu), I cực đại; U_L = U_C = Q·U với Q = ω₀L/R; độ rộng băng Δω ≈ R/L.
- **Cộng hưởng song song (LC lý tưởng):** Z → ∞; dòng tổng → 0 trong khi dòng vòng trong L–C lớn.
- **Bù công suất (nâng cosφ):** tụ song song tải: C = P(tanφ₁ − tanφ₂)/(ωU²).
- **Biến áp:** trở kháng phản ánh Z′ = (N₁/N₂)²Z; công suất P₁=P₂ (lý tưởng).
- **Giản đồ Fresnel (hình học):** trực quan hoá U² = U_R² + (U_L − U_C)², giải nhanh khi bài cho vôn kế đo các đoạn (dùng định lý cosin cho tam giác điện áp).
- **Dòng không sin (chỉnh lưu, diode, xung):** quay lại miền thời gian: giá trị hiệu dụng I_rms² = ⟨i²⟩_T; nhiệt trung bình = I_rms²R. Dòng = một chiều + xoay chiều: I_rms² = I_dc² + I_ac,rms².
- **BẪY:** trộn giá trị hiệu dụng với biên độ; dùng phasor khi mạch có diode/phi tuyến; công suất trung bình ≠ tích công suất hiệu dụng khi có lệch pha.

### M.7. Hệ cơ–điện ghép cặp (thuật toán chuẩn hoá cho bài thanh/ khung/ cuộn dây)
1. Liệt kê **biến cơ** (x, v hoặc θ, ω) và **biến điện** (q hoặc I).
2. **Phương trình cơ:** ΣF (hoặc ΣM) = ma (hoặc Iα) với **lực từ = B l I (thuộc biến điện)**.
3. **Phương trình điện:** KVL với ε = B l v (thuộc biến cơ) + các phần tử R, L, C.
4. Kiểm tra năng lượng: công cơ + công nguồn = nhiệt + ΔW_L + ΔW_C + ΔW_động + ΔW_thế.
5. Nhận diện tương tự khối lượng–lò xo–ma sát ↔ L–C–R (khối lượng hiệu dụng, cản nhớt hiệu dụng, độ cứng hiệu dụng).

---

## PHẦN F — BẢNG CHẨN ĐOÁN "DẤU HIỆU TRONG ĐỀ → CÔNG CỤ" (Vấn đề 1 + tiền xử lý)

| Dấu hiệu trong đề / hình | Nhóm công cụ | Hành động tiền xử lý |
|---|---|---|
| Nhiều điện tích điểm, tìm lực/cân bằng | D.1 | Liệt kê từng điện tích tự do; đếm phương trình |
| Đối xứng cầu/trụ/phẳng + phân bố điện tích | D.3 Gauss | Xác định nhóm đối xứng → mặt Gauss |
| Hình phức tạp nhưng gần đối xứng (lỗ, lệch tâm) | D.3+T7 | Chồng chất với phân bố âm |
| Vật dẫn cô lập/nối đất/nối dây | D.5 | Mỗi vật dẫn cho (Q_i hoặc φ_i); bảo toàn tổng Q |
| Điện tích gần mặt phẳng/cầu dẫn | D.6 ảnh | Kiểm nối đất hay cô lập |
| Hạt bay trong điện trường | D.4, D.11 | Bảo toàn năng lượng, đối xứng bảo toàn |
| Hai bản tụ, dịch chuyển, chèn điện môi | D.8, D.9 | Xác định giữ Q hay giữ U; F = −∂W/∂x |
| Mạng tụ có "nút tự do" | D.9 nút tụ | T12: đảo & bảo toàn Q_đảo |
| Nối hai tụ / chuyển mạch tụ | D.9, D.17 | Bảo toàn Q_đảo, nhiệt = ½C_sΔU² |
| Mạch điện trở nhiều nhánh | D.15 | T1, T2; đếm b, n; chọn nút/mesh |
| Mạch có tính đối xứng đẹp | D.15 T2 | Tìm nút đẳng thế, cắt |
| Vôn/ ampe kế thực, đèn, diode | D.15 T5 | Mô hình điện trở/đặc tuyến; chia trường hợp |
| Cực đại công suất, hiệu suất | D.14 | Xác định biến số cần tối ưu; điều kiện ký hiệu |
| Chuyển mạch, "sau thời gian dài" | D.17, M.5 | T6: trạng thái 0⁻, 0⁺, ∞ |
| Dòng điện tạo từ trường, hình dạng dây | M.1 | Tham số hoá; đối xứng; dùng bảng gương |
| Đối xứng trụ/xuyến/tấm, tìm B | M.2 Ampère | Chọn đường Ampère |
| Trụ/ khối có hốc | M.2+T7 | Dòng âm |
| Hạt trong B, quỹ đạo | M.3 | B đều: bán kính; không đều: bảo toàn chính tắc |
| Thanh/khung chuyển động, B biến thiên | M.4, M.7 | ε bằng cách A và B; hệ cơ–điện |
| Cuộn dây, chuyển mạch RL/LC | M.5 | i_L liên tục; τ = L/R_th |
| Hai cuộn dây, biến áp | M.5 hỗ cảm | M, k; biến áp lý tưởng |
| Mạch xoay chiều xác lập | M.6 | Phasor; điện thế nút phức |
| Đề "cho từ thông" hoặc "cho đường cong" | M.4 | Dùng Φ(t) trực tiếp |
| Siêu dẫn / R=0 / thông lượng giữ nguyên | M.5 siêu dẫn | Bảo toàn từ thông |

**Nếu bế tắc (rule-of-thumb):**
1. Quay lại 7 loại quét (mục C) và hỏi: loại nào chưa quét?
2. **Đếm ẩn–phương trình** (B.3): còn thiếu ở đâu? Thiếu thường là *bảo toàn* (Q6) hoặc *biên* (Q7).
3. Thử **giới hạn đặc biệt** trước khi giải đầy đủ để dự đoán dạng nghiệm.
4. Thử **công cụ đối ngẫu:** Gauss ↔ thế; lực ↔ năng lượng; KVL ↔ KCL; nút ↔ mesh.

---

## PHẦN G — VÍ DỤ MINH HOẠ CÁCH "QUÉT CHỖ" (sổ cái ẩn–phương trình)

### G.1. Mạng tụ cầu (mạch tụ với đảo điện tích)
Nút A: φ_A = U (nguồn), nút đất 0. C₁: A–X; C₂: X–0; C₃: A–Y; C₄: Y–0; C₅: X–Y. X, Y là **đảo** ban đầu không tích điện.

| # | ℓ | CHỖ | Pre | Phương trình | Ẩn |
|---|---|---|---|---|---|
| 1 | Bảo toàn Q đảo | X | X không nối nguồn ✔ | C₁(φ_X−U) + C₂φ_X + C₅(φ_X−φ_Y) = 0 | φ_X |
| 2 | Bảo toàn Q đảo | Y | ✔ | C₃(φ_Y−U) + C₄φ_Y + C₅(φ_Y−φ_X) = 0 | φ_Y |

2 ẩn, 2 phương trình ⇒ đóng kín. **Nhận xét (đối xứng/cân bằng):** nếu C₁/C₂ = C₃/C₄ thì φ_X = φ_Y nghiệm ⇒ C₅ bị loại (không tích điện) — đây là "cầu tụ cân bằng", tương tự cầu Wheatstone. Nếu đề hỏi chỉ điện tích Q₅ ⇒ chỉ cần biết φ_X − φ_Y.

### G.2. Thanh trượt nối tụ
**Đề:** thanh (m, l) trượt không ma sát trên ray nằm ngang, B thẳng đứng đều, nối tụ C, lực F không đổi. Tìm a.

| # | ℓ | CHỖ | Pre | Phương trình | Ẩn |
|---|---|---|---|---|---|
| 1 | Faraday (cách B) | thanh | (v×B)·dl trên đoạn chuyển động ✔ | ε = Blv | ε |
| 2 | KVL | vòng | R≈0, L≈0 ⇒ ε = q/C | q = CBlv | q |
| 3 | I = dq/dt | nhánh tụ | | I = CBl·a | I |
| 4 | Newton | thanh | | ma = F − BlI | a |

Thế: ma = F − CB²l²a ⇒ **a = F/(m + CB²l²)**. Nhận xét: khối lượng hiệu dụng; giới hạn C→0 trả về F/m ✔; l→0 ✔.

### G.3. Solenoid hữu hạn từ Biot–Savart
Chọn "viên gạch": vòng tròn có B trên trục (M.1). CHỖ = mỗi vòng dây là phần tử dz; **đối xứng trục** ⇒ chỉ còn B_z; chồng chất: B = ∫(μ₀nI/2)R²/(R²+z²)^{3/2}dz = (μ₀nI/2)[z/√(R²+z²)]. Đưa về Vấn đề 3: một tích phân cơ bản. Giới hạn L→∞ ⇒ μ₀nI ✔.

### G.4. Lỗ hổng trong quả cầu điện tích
CHỖ: T7 — cầu đặc đều ρ (tâm O₁, bán kính R) trừ cầu đều −ρ (tâm O₂ = tâm hốc). Trong hốc: E = ρ(r−r₁)/3ε₀ − ρ(r−r₂)/3ε₀ = ρ(r₂−r₁)/3ε₀ = ρa/3ε₀ — **đều**, không phụ thuộc điểm. Bốn dòng, không tích phân.

---

## PHẦN H — NGOÀI BẢNG NHƯNG THƯỜNG GẶP Ở HSGQG/IPHO (thư viện chưa xây đủ thẻ)

Mỗi mục dưới đây **đáng làm thành thẻ công cụ tiếp theo** (theo thứ tự ưu tiên tôi đề xuất) nhưng tôi **chưa** viết chi tiết trong bản này để tránh viết ẩu:

1. Phương trình Poisson–Laplace: tách biến, khai triển đa cực, định lý giá trị trung bình, định lý duy nhất.
2. Từ môi trường, vật liệu từ, siêu dẫn (Meissner: B=0 bên trong, dòng mặt; lượng tử hoá từ thông); từ hoá M, H.
3. Đường truyền/ mạch bậc thang vô hạn RC, LC (Z₀ = √(L/C)); mạch tương tự.
4. Lực từ với chuyển động tương đối tính; đối xứng Lorentz E,B; hệ quy chiếu chuyển động.
5. Poynting vector, dòng năng lượng, sức căng Maxwell (áp lực tĩnh điện/từ tổng quát).
6. Bức xạ điện từ của điện tích gia tốc (công thức Larmor P = q²a²/(6πε₀c³)); sóng điện từ; hiệu ứng bề mặt (skin).
7. Plasma, hạt trong trường biến thiên chậm (bất biến đoạn nhiệt: từ thông qua quỹ đạo hạt là bất biến).
8. Dụng cụ đo và nhiễu (bài thực hành/ IPHO thí nghiệm).

---

## PHẦN I — KIỂM TRA MÔ HÌNH (áp 7 điều kiện của README vào Điện–Từ)

| Điều kiện | Câu hỏi kiểm tra (Điện–Từ) |
|---|---|
| (1) Diễn giải đúng | Chiều dương của dòng, pháp tuyến, cực nguồn đã đặt rõ? Điện tích cảm ứng, dòng cảm ứng đã liệt kê? |
| (2) Hợp lệ (Sound) | Mỗi công cụ có Pre thoả? Gauss/Ampère có đối xứng? KCL có nút thật? Faraday/ Pre "vòng vật liệu"? Dùng φ trong trường xoáy? |
| (3) Đủ/đóng kín | #ẩn = #phương trình độc lập? Có thiếu bảo toàn Q hoặc điều kiện biên? |
| (4) Nhất quán | Có hai điều kiện mâu thuẫn (vd. vừa cô lập Q vừa nối đất)? Dấu ε, chiều dòng nhất quán? |
| (5) Xác định | Nghiệm tồn tại, duy nhất? Ví dụ mạch có nút cô lập vô nghiệm dòng; bài Poisson thiếu biên. |
| (6) Đủ trường hợp | Diode mở/khoá; vật dẫn nối/không nối; hạt ra/ không ra khỏi vùng từ trường; R nhỏ/lớn; bản tụ có/không chạm |
| (7) Biến đổi hợp lệ | Nhân chia cho đại lượng có thể =0? Bình phương hai vế có thêm nghiệm ngoại lai? Dấu √? |

**10 lỗi hay gặp nhất (Điện–Từ):**
1. Nhầm "giữ Q" với "giữ U" khi dịch chuyển bản tụ (D.9).
2. Xem năng lượng tụ = công cơ khi tụ nối nguồn.
3. Quên điện tích cảm ứng (D.1).
4. Áp Gauss/Ampère khi thiếu đối xứng.
5. Nhầm dấu ε trong Kirchhoff và Faraday (dùng B.2 & M.4 để cố định).
6. Coi "nối tiếp" khi còn nhánh thứ ba ở giữa hai tụ.
7. Bỏ qua i_L, u_C liên tục ở t=0⁺.
8. Dùng hiệu điện thế/thế φ cho điện trường xoáy.
9. Nhầm biên độ & hiệu dụng ở AC.
10. Quên các trường hợp diode/đèn (phi tuyến).

---

## PHẦN J — HẠN CHẾ CÒN LẠI & BƯỚC TIẾP

- **Chưa có tính phủ kín:** không có bảo đảm rằng 7 loại quét + thư viện này bao trọn mọi đề IPHO Điện–Từ. Nên xem đây là **"bản thư viện phiên bản 1"** và cập nhật khi giải bài thật (mỗi bài lạ ⇒ tự hỏi: công cụ nào tôi thiếu thẻ?).
- **Việc nên làm tiếp:** (1) Chạy thử toàn bộ quy trình trên 10–20 đề HSGQG cũ, ghi lại ở sổ cái loại quét nào hay bỏ sót. (2) Xây các thẻ ở phần H. (3) Với mỗi công thức có **[⚠]**, tự dẫn xuất lại.
- **Các chỗ cần cảnh giác nhất:** quy ước dấu của hỗ cảm M và số hạng MI₁I₂; quy tắc phản xạ gương cho E/B trong bài có hình học lạ (nên tự dựng cặp phần tử đối xứng rồi cộng vectơ để chắc). Tôi có thể tách từng cái ra và kiểm bằng tính số nếu bạn muốn.
