# CẤU TRÚC TOÁN HỌC — THƯ VIỆN CHO "VẤN ĐỀ 2" CƠ HỌC CHẤT ĐIỂM
**Dùng chung với:** README (0.1 — 2 vấn đề lớn) và "CƠ CHẤT ĐIỂM — THƯ VIỆN CÔNG CỤ CHO VẤN ĐỀ 1 & VẤN ĐỀ 2"
**Mục tiêu tài liệu này:** Liệt kê **hữu hạn** các Cấu Trúc Toán Học mà *mọi* công cụ K/D/C/O/P trong thư viện Cơ Chất Điểm (và do đó, mọi biến tấu đề VPHO/HSGQG/IPhO phần cơ học chất điểm) đều quy về. Với mỗi cấu trúc: định nghĩa, thuật toán giải cố định, Pre/Post, bẫy, và bảng đối chiếu ngược về từng công cụ Vật Lý đã liệt kê trong file gốc.

**Nhãn độ tin cậy** giữ nguyên quy ước của file gốc: **[C]** kiến thức chuẩn, **[H]** heuristic/tổ chức của tôi, **[EXT]** vượt khung nhưng cần cho VPHO/IPhO, **[?]** cần bạn đối chiếu.

---

## PHẦN 0. NGUYÊN TẮC TỔ CHỨC

Theo README: *"Thành thạo cấu trúc Toán A ⇒ giỏi mọi bài Vật lý thuộc cấu trúc A."* Và theo file Cơ Chất Điểm (mục 7.2 — "Bài toán đích"), sau khi mô hình hóa (Vấn đề 1), mọi bài cơ chất điểm **luôn** đổ vào một trong **8 cấu trúc toán học** dưới đây — không hơn. Đây là khẳng định thực chiến **[H]**, kiểm chứng bằng cách: mọi dòng "Chuyển sang Toán (V2)" trong file gốc đều map được vào đúng một (hoặc tổ hợp) các mục A–H.

| # | Cấu trúc | Vai trò |
|---|---|---|
| A | Đại số sơ cấp: hệ phương trình & bất phương trình (tuyến tính + bậc hai) | "Xương sống" — xuất hiện trong > 80% bài |
| B | Vector, hệ tọa độ & hình học giải tích (kể cả conic) | Dựng mô hình không gian, chiếu lực |
| C | Giải tích vi phân một biến: đạo hàm, cực trị, khai triển Taylor | Tìm "CHỖ" cực trị, tuyến tính hóa quanh cân bằng |
| D | Giải tích tích phân một biến & ODE tách biến bậc nhất | Công, năng lượng, a(x)/a(v)/a(t) |
| E | ODE tuyến tính hệ số hằng bậc hai (+ số phức/phasor) | Mọi bài dao động O1, O5, O6 |
| F | Đại số tuyến tính ma trận: hệ phương trình nhiều ẩn, định thức, trị riêng–vector riêng | D1+K7 (nhiều vật nối), O7 (mode chuẩn) |
| G | Nguyên lý biến phân & đối xứng (Euler–Lagrange, Noether) | Công cụ "hạng nặng hợp pháp": C9, kiểm tra bảo toàn C8 |
| H | Giải tích tiệm cận / nhiễu loạn & chuỗi lũy thừa | Hiệu chỉnh phi tuyến: O3 (con lắc góc lớn), O8, P12 |

**Hệ quả thực dụng [H]:** Khi gặp bài lạ, thay vì hỏi "bài này thuộc dạng gì", hãy hỏi: **sau khi mô hình hóa, hệ phương trình/phương trình thu được có hình dạng nào trong 8 dạng trên?** Hình dạng quyết định toàn bộ phần còn lại của lời giải — phần Vật Lý chỉ quyết định *các hệ số* của hệ đó.

---

## PHẦN A. ĐẠI SỐ SƠ CẤP: HỆ PHƯƠNG TRÌNH & BẤT PHƯƠNG TRÌNH

### A.1. Phạm vi và vì sao nó là cấu trúc nền tảng nhất **[C]**

Mọi bước "Post" từ Newton tại một thời điểm (D1), mọi định luật bảo toàn áp dụng giữa hai trạng thái (C1, C3, C4, C7), mọi ràng buộc động học (K7) đều sinh ra **một hoặc vài phương trình đại số** (tuyến tính hoặc bậc hai) giữa các ẩn (vận tốc, lực, thời gian, góc). Đây chính là tầng thấp nhất mà README gọi là "Bước chuyển Vật lý → Toán là bước quyết định": một khi đã có hệ phương trình, phần còn lại là **thuần túy kỹ thuật đại số**, không còn trực giác vật lý.

### A.2. Thư viện kỹ thuật con

**(a) Hệ phương trình tuyến tính n ẩn n phương trình [C]**
- **Phương pháp thế / khử Gauss:** khử dần từng ẩn. Dùng khi n ≤ 3–4 và hệ "thưa" (nhiều hệ số 0) — đa số bài D1+K7.
- **Quy tắc Cramer:** x_i = det(A_i)/det(A). Dùng khi cần **công thức tường minh** theo tham số (m, M, k, α…) thay vì chỉ một con số — đúng tinh thần README về "Nodal Analysis": *"cái pattern của hệ phương trình đó rất dễ nắm bắt (chuẩn bị trước)"*. Với hệ 2×2, 3×3 nhỏ, thuộc lòng công thức Cramer là "thuật toán hợp pháp trong phòng thi".
- **Pre:** hệ **tuyến tính** theo đúng nghĩa (các ẩn không nhân với nhau, không có sin/cos của ẩn). Nếu không tuyến tính → xem (b) hoặc sang cấu trúc B/C.
- **Post:** nghiệm duy nhất nếu det(A) ≠ 0; nếu det(A) = 0 → hệ suy biến (thiếu phương trình độc lập, quay lại 1.7 của file gốc — kiểm kê ẩn–phương trình).
- **Bẫy:** dấu của hệ số (chiều dương đã quy ước ở P1 file gốc); nhầm ẩn phụ (lực liên kết) với ẩn chính khi đếm bậc.

**(b) Phương trình/hệ phương trình bậc hai [C]**
- Dạng chuẩn ax² + bx + c = 0; Δ = b² − 4ac.
- **Vai trò đặc biệt trong cơ chất điểm:** K1 (giây thứ n, gặp nhau), K3 (ném trúng điểm — bậc hai theo tan θ hoặc theo t), K8 (bao hình: Δ = 0 chính là điều kiện biên), C6 (va chạm đàn hồi 1D đôi khi quy về bậc hai nếu đặt ẩn sai hệ).
- **Post quan trọng nhất — "định lý tồn tại":** Δ ≥ 0 ⇔ tồn tại trạng thái vật lý thỏa mãn. Đây là cầu nối trực tiếp giữa cấu trúc đại số và điều kiện (5) "Xác định — Well-posedness" trong README.
- **Thuật toán cố định ALG-A2b:**
  1. Nhận diện ẩn thật sự cần giải (thường **không** phải đại lượng đề hỏi trực tiếp — ví dụ ẩn là tan θ chứ không phải θ).
  2. Đưa phương trình về đúng dạng chuẩn bậc hai theo ẩn đó.
  3. Tính Δ; nếu bài hỏi "tồn tại/không tồn tại/tối thiểu" → dừng ở Δ ≥ 0 (không cần giải nghiệm).
  4. Nếu cần nghiệm cụ thể: x = (−b ± √Δ)/(2a); **luôn kiểm cả hai nghiệm có hợp lệ vật lý không** (bẫy #19 file gốc).
- **Bẫy:** bỏ nghiệm thứ hai; quên miền xác định của ẩn gốc khi đổi biến (vd. θ ∈ [0, π] nhưng tan θ thì tuần hoàn π).

**(c) Hệ phương trình phi tuyến nhỏ (2–3 ẩn, có tích/thương giữa ẩn) [C]**
- Kỹ thuật: thế một ẩn, đưa về bậc hai của một ẩn còn lại; hoặc dùng **đối xứng** của hệ (đổi vai trò hai vật) để giảm số ẩn độc lập — xem phần B và G (đối xứng).
- Thường gặp: C6 va chạm xiên có ràng buộc hình học; P10 (ma sát: hệ phương trình với ẩn rời rạc chế độ).

**(d) Bất đẳng thức tuyến tính / bất đẳng thức điều kiện tồn tại chế độ [C]**
- Cốt lõi của **P10 "assume–verify"**: |f| ≤ μN, T ≥ 0, N ≥ 0. Đây **không phải** bài toán tối ưu — chỉ là kiểm tra một bất đẳng thức tuyến tính (hoặc gần tuyến tính) sau khi đã có nghiệm bằng (a).
- **Thuật toán:** giải hệ giả sử một chế độ (dùng (a)); thay nghiệm vào bất đẳng thức ràng buộc chế độ đó; nếu sai → đổi chế độ, là một **bài toán tổ hợp hữu hạn** (tối đa 2^k tổ hợp với k mặt ma sát/dây/tiếp xúc).
- **Liên hệ:** đây chính là nơi "thuật toán duyệt" của README trở thành brute-force **có kiểm soát và hữu hạn** — không phải duyệt vô hạn.

### A.3. Bảng đối chiếu ngược (A → công cụ K/D/C/O)

| Công cụ gốc | Dùng cấu trúc A nào | Ghi chú |
|---|---|---|
| K1 | A.2(a), A.2(b) | 5 biến, 2 phương trình độc lập mỗi lần |
| K3 | A.2(b) | Bậc hai theo tan θ hoặc theo t |
| K4 (gặp nhau trên vòng) | A.2(a) + họ nghiệm (xem phần B.4 — số nguyên) |
| K6 | A.2(b) (cực tiểu hóa |r₀+ut|² — thực chất là C.2) |
| K7 | A.2(a) (hệ tuyến tính cho gia tốc/vận tốc ẩn) |
| K8 | A.2(b) — Δ = 0 là điều kiện bao hình |
| D1 + mọi D | A.2(a), kết hợp A.2(d) khi có ma sát/dây |
| C1–C4, C6, C7 | A.2(a)/(c) — Post của mỗi định luật là một phương trình đại số |
| P10 | A.2(d) |

---

## PHẦN B. VECTOR, HỆ TỌA ĐỘ & HÌNH HỌC GIẢI TÍCH

### B.1. Phạm vi

Toàn bộ README/file gốc nhấn mạnh "Mô Hình Hóa" (Vấn đề 1) — mà bước đầu tiên của mô hình hóa trong cơ học luôn là: **chọn hệ tọa độ, biểu diễn vị trí/vận tốc/lực bằng vector**. Đây là cấu trúc "phiên dịch" giữa thế giới vật lý 3D và các phương trình đại số ở Phần A.

### B.2. Thư viện kỹ thuật con

**(a) Đại số vector cơ bản [C]**
- Tích vô hướng **a**·**b** = ab cosθ (dùng để "chiếu" lực/vận tốc lên một trục — nền tảng của D1, D6, C3).
- Tích có hướng **a**×**b** (độ lớn = ab sinθ) — dùng tính momen lực (C7), diện tích quét (Kepler), và công thức ρ = v³/|**v**×**a**| (K5).
- **Phân tích vector thành hai thành phần vuông góc** — đây là "phép thuật" duy nhất đứng sau toàn bộ Phần D (động lực học): phân tích lực trên mặt nghiêng, phân tích gia tốc (t, n).
- **Pre:** hệ quy chiếu đã chọn là quán tính hoặc đã cộng đủ lực quán tính (P1, P4, D9, D10 của file gốc — đây là bước Vật Lý, không phải Toán, nhưng **quyết định vector nào được phép cộng trực tiếp**).

**(b) Các hệ tọa độ chuẩn và quy tắc chọn [C]** — đã liệt kê ở P5 file gốc, nhắc lại dưới góc độ toán thuần túy:

| Hệ | Vector vận tốc | Vector gia tốc | Khi nào là lựa chọn tối ưu (tiêu chí toán học) |
|---|---|---|---|
| Descartes (x,y) | (ẋ, ẏ) | (ẍ, ÿ) | Lực không đổi hướng theo hệ trục cố định |
| Cực (r, φ) | ṙ**e**_r + rφ̇**e**_φ | (r̈−rφ̇²)**e**_r + (rφ̈+2ṙφ̇)**e**_φ | Lực có tâm (chỉ phụ thuộc r), **e**_r, **e**_φ không hằng ⇒ cần quy tắc đạo hàm vector đơn vị: ė_r = φ̇**e**_φ, ė_φ = −φ̇**e**_r |
| Tự nhiên (t, n) | v**t** | v̇**t** + (v²/ρ)**n** | Quỹ đạo đã biết hình dạng hình học, cần tách "đổi tốc độ" khỏi "đổi hướng" |

- **Quy tắc chọn [H] (phiên bản toán học của "nguyên lý khử ẩn" 1.6):** chọn hệ tọa độ sao cho **số hạng cần khử (ẩn chưa biết) trở thành hệ số 0** trong một phương trình — đây là một bài toán đại số tuyến tính trá hình: tìm phép chiếu (hướng e) sao cho **a**_ẩn · **e** = 0.

**(c) Hình học giải tích phẳng: đường thẳng, parabol, elip (conic) [C]**
- **Parabol** y = x tanθ − gx²(1+tan²θ)/(2v₀²): quỹ đạo ném xiên — một bài toán hình học giải tích thuần túy một khi đã có phương trình.
- **Đường bao hình (envelope)** của họ parabol: khử tham số θ từ {F(x,y,θ)=0, ∂F/∂θ=0} — chính là kỹ thuật K8(d), cho ra "parabol an toàn".
- **Elip** (quỹ đạo Kepler, r = p/(1+e cosφ)): phương trình cực của conic — cần thuộc **5 đại lượng** (a, e, p, r_min, r_max) và quan hệ giữa chúng.
- **Thuật toán ALG-B2c (bao hình):**
  1. Viết họ đường cong F(x, y; λ) = 0 với λ là tham số biến thiên (góc ném, pha…).
  2. Lấy ∂F/∂λ = 0.
  3. Khử λ giữa hai phương trình ⇒ phương trình bao hình không còn λ.
  4. Đối chiếu với Δ = 0 của phần A.2(b) — **hai cách tính cho cùng một kết quả** (kiểm tra chéo điều kiện (4) Nhất quán của README).

**(d) Phép đổi hệ quy chiếu (phép biến đổi Galileo) [C]**
- **r**' = **r** − **u**t, **v**' = **v** − **u**: đây là một **phép biến đổi affine** của không gian vector. Về mặt toán, nó biến bài toán phức tạp (va chạm với vật chuyển động) thành bài toán đơn giản (va chạm với vật đứng yên) bằng cách **dịch gốc tọa độ vận tốc**.
- **Bất biến dưới phép biến đổi này:** gia tốc, lực, khối lượng, **độ lớn vận tốc tương đối**. **Không bất biến:** động năng, công (từng đại lượng riêng lẻ).

### B.3. Bảng đối chiếu ngược

| Công cụ gốc | Dùng cấu trúc B nào |
|---|---|
| K3, K8 | B.2(c) — conic, bao hình |
| K4, K5, D6, D7, C7 (Kepler) | B.2(b) tọa độ cực + B.2(c) conic |
| K6, D9, D10, P2, P3 | B.2(d) đổi hệ quy chiếu |
| D1 (quét biên, chiếu lực) | B.2(a), B.2(b) |
| P5, P13 | B.2(b) |

### B.4. Bổ sung: số học modulo / họ nghiệm rời rạc **[H]**

Một mục nhỏ nhưng hay bị bỏ sót (bẫy #20 file gốc): bài "gặp nhau trên vòng tròn" cho ra **θ_A(t) = θ_B(t) + 2πk, k ∈ ℤ** — đây là cấu trúc **đồng dư/số học modulo** chứ không còn là đại số liên tục thuần túy. Quy tắc: luôn giữ **k** như một ẩn nguyên, chỉ chọn giá trị k cụ thể ở **bước cuối cùng** sau khi đã có điều kiện t > 0 nhỏ nhất.

---

## PHẦN C. GIẢI TÍCH VI PHÂN MỘT BIẾN: ĐẠO HÀM, CỰC TRỊ, TAYLOR

### C.1. Phạm vi

Đây là cấu trúc đứng sau **mọi** từ khóa "lớn nhất/nhỏ nhất/điều kiện để/tối ưu" (K8), và đứng sau **toàn bộ** quá trình "tìm vị trí cân bằng rồi tuyến tính hóa" (O1, O4, C5, D11, P12) — tức là **nửa đầu** của mọi bài toán dao động.

### C.2. Thư viện kỹ thuật con

**(a) Tìm cực trị bằng đạo hàm [C]**
- dF/dλ = 0 cho điểm dừng; dấu của d²F/dλ² (hoặc xét biên) phân loại cực đại/cực tiểu.
- **Thuật toán ALG-C2a:** (1) viết F theo đúng một biến độc lập λ (nếu có nhiều biến ràng buộc nhau, dùng B hoặc thế biến trước — xem K7); (2) F' = 0; (3) kiểm F'' hoặc so sánh giá trị biên; (4) **luôn kiểm miền xác định vật lý của λ** (góc trong [0, π/2], t > 0…) — đây chính là bẫy #19.
- **Vai trò kép:** cùng một bài có thể giải bằng đạo hàm **hoặc** bằng Δ ≥ 0 của Phần A — hai cấu trúc này **phải cho cùng kết quả** khi bài toán là bậc hai (đạo hàm của ax²+bx+c triệt tiêu đúng tại đỉnh, và đỉnh chạm trục hoành khi Δ=0). Dùng làm kiểm tra chéo bắt buộc.

**(b) Tìm vị trí cân bằng & phân loại ổn định [C]** — đây là trái tim toán học của O1, O4, C5, D11:
- Cân bằng: U'(q₀) = 0 (lực suy rộng = 0).
- **Ổn định ⇔ U''(q₀) > 0**; không ổn định ⇔ U''(q₀) < 0; **suy biến** (cần Phần H) nếu U''(q₀) = 0.
- **Thuật toán ALG-C2b (đây chính là O4/Rayleigh viết lại thuần túy toán học):**
  1. Viết U(q) — hàm một biến, sau khi đã dùng ràng buộc (K7) để quy hệ về **một** bậc tự do.
  2. Giải U'(q) = 0 ⇒ (các) điểm cân bằng q₀.
  3. Tính U''(q₀) tại từng điểm; phân loại.
  4. Nếu cần tần số dao động nhỏ: cần thêm M_eff (xem (c) — khai triển Taylor của động năng).

**(c) Khai triển Taylor & tuyến tính hóa [C]** — công cụ **duy nhất** biến một hệ phi tuyến (vật lý thực) thành một hệ tuyến tính (giải được bằng Phần E):
- f(q₀ + x) ≈ f(q₀) + f'(q₀)x + ½f''(q₀)x² + …
- **Quy tắc bắt buộc với thế năng:** phải khai triển **đến bậc 2** (không phải bậc 1!) vì số hạng bậc 1 triệt tiêu tại cân bằng (U'(q₀)=0) — số hạng đầu tiên "sống sót" quyết định động lực học là bậc 2.
- **Thuật toán ALG-C2c:**
  1. Xác định điểm khai triển q₀ (từ (b)).
  2. Đặt x = q − q₀.
  3. Khai triển U(q) đến bậc 2: U ≈ U(q₀) + ½U''(q₀)x².
  4. Khai triển động năng (nếu M_eff(q) phụ thuộc q): chỉ cần M_eff **tại q₀** (bậc 0 là đủ, vì động năng đã là bậc 2 theo q̇).
  5. Kết quả luôn có dạng chuẩn ½M_effẋ² + ½K_effx² = hằng ⇒ ODE bậc 2 tuyến tính (chuyển sang Phần E).
- **Bẫy (đã nêu ở O4 file gốc):** bỏ sót "hiệu ứng hình học" khi hàm ràng buộc hình học l(q) có l''(q₀) ≠ 0 và lực tại cân bằng khác 0 (lò xo đã biến dạng) — số hạng chéo F(q₀)·l''(q₀) không được bỏ qua.

**(d) Các khai triển xấp xỉ chuẩn (thuộc lòng) [C]**
sin θ ≈ θ − θ³/6; cos θ ≈ 1 − θ²/2; (1+ε)ⁿ ≈ 1+nε; √(1+ε) ≈ 1+ε/2; ln(1+ε) ≈ ε − ε²/2; e^ε ≈ 1+ε. Đây là "bộ từ điển" cần thuộc để thực hiện bước (c) nhanh, không phải tính lại đạo hàm mỗi lần.

### C.3. Bảng đối chiếu ngược

| Công cụ gốc | Dùng cấu trúc C nào |
|---|---|
| K8 | C.2(a) (song song với A.2(b)) |
| C5, D11, O1, O4 | C.2(b) + C.2(c) |
| P12 | C.2(c), C.2(d) |
| O3 (mọi công thức ω²) | Kết quả **đóng gói sẵn** của C.2(b)+(c) cho các hệ chuẩn |

---

## PHẦN D. GIẢI TÍCH TÍCH PHÂN MỘT BIẾN & ODE TÁCH BIẾN BẬC NHẤT

### D.1. Phạm vi

Đây là cấu trúc của **mọi** bài liên quan đến công (C3), năng lượng khi lực biến thiên theo vị trí (C4, C5), và chuyển động một chiều với gia tốc không hằng (K2, D5).

### D.2. Thư viện kỹ thuật con

**(a) Tích phân xác định cơ bản [C]** — ∫F·dr tính công; ∫a dt, ∫v dt tính Δv, Δx trực tiếp khi a hoặc v là hàm tường minh của t.

**(b) Đổi biến tích phân — kỹ thuật "v dv = a dx" [C]**, chính là P13 của file gốc nhưng nhìn dưới góc độ thuần túy Toán:
- Xuất phát: a = dv/dt = (dv/dx)(dx/dt) = v dv/dx.
- Đây là một **phép đổi biến độc lập** chuẩn trong giải tích (chain rule ngược), không phải "mẹo Vật Lý" — nó áp dụng được **bất cứ khi nào** hàm a chỉ phụ thuộc đúng một trong ba biến (t, x, v).
- **Thuật toán ALG-D2b (ba nhánh, khớp K2 file gốc):**

| a = a(t) | a = a(x) | a = a(v) |
|---|---|---|
| dv = a(t)dt | v dv = a(x)dx | dv/a(v) = dt |
| tích phân trực tiếp | ⇒ ½v² − ½v₀² = ∫a dx (= định lý công–động năng, Phần A nối với đây) | v dv/a(v) = dx |

- Về bản chất, **C4 (bảo toàn cơ năng) chính là trường hợp riêng** của nhánh giữa khi a(x) = −U'(x)/m: tích phân ∫a dx = −ΔU/m. Đây là minh chứng toán học cho việc README gọi các định luật bảo toàn là "công cụ" chứ không phải tiên đề độc lập — chúng **suy ra được** từ Phần D + Newton.

**(c) ODE tách biến bậc nhất tổng quát [C]** — dy/dx = f(x)g(y) ⇒ ∫dy/g(y) = ∫f(x)dx + C.
- **Pre:** vế phải tách được thành tích của hàm một biến x và hàm một biến y. Nếu không tách được (vd a phụ thuộc đồng thời cả x và v) → bài toán **không** thuộc cấu trúc D nữa, cần phương pháp số hoặc là dấu hiệu mô hình hóa sai (quay lại Vấn đề 1).
- **Mẫu chuẩn (đã kiểm trong file gốc):** cản tuyến tính (tách theo v), cản bậc hai (tách theo v, dùng ∫dv/(1−v²) dạng tanh/artanh), capstan dT/T = μdφ.
- **Hàm ngược hay gặp cần thuộc:** ∫dv/(a²−v²) → (1/a)artanh(v/a) hoặc dạng log; ∫dv/(a²+v²) → (1/a)arctan(v/a); các hàm này tương ứng với **tanh, tan** xuất hiện trong lời giải cản bậc hai và dao động.

### D.3. Bảng đối chiếu ngược

| Công cụ gốc | Dùng cấu trúc D nào |
|---|---|
| K2 | D.2(b) toàn bộ |
| D5 | D.2(c) |
| C3, C4, C5 (tích phân chu kỳ T = √(2m)∫dq/√(E−U)) | D.2(a), D.2(b) |
| D8 (tên lửa) | D.2(c) dạng m dv = u_rel |dm|, tách biến theo m |
| D2 (dây nặng, capstan) | D.2(c) |

---

## PHẦN E. ODE TUYẾN TÍNH HỆ SỐ HẰNG BẬC HAI (+ SỐ PHỨC/PHASOR)

### E.1. Phạm vi

Đây là cấu trúc toán học **duy nhất** đứng sau toàn bộ chương Dao Động một bậc tự do (O1, O5, O6) — đúng như README tiên đoán: "Cùng một cấu trúc Toán có thể sinh ra nhiều dạng bài Vật lý khác nhau." Mọi biến tấu đề thi về lò xo, con lắc, mạch LC-tương tự cơ học, dao động tắt dần, dao động cưỡng bức **đều là cùng MỘT** phương trình toán học, chỉ khác tên biến và hệ số.

### E.2. Dạng chuẩn tổng quát

> **ẍ + 2γẋ + ω₀²x = f(t)**

với γ = 0, f = 0 cho O1 (DĐĐH thuần túy); γ > 0, f = 0 cho O5 (tắt dần); γ ≥ 0, f = (F₀/m)cos Ωt cho O6 (cưỡng bức).

### E.3. Thư viện kỹ thuật con

**(a) Phương trình đặc trưng [C]** — thử nghiệm x = e^{rt} ⇒ r² + 2γr + ω₀² = 0 ⇒ r = −γ ± √(γ²−ω₀²).
- **Đây là lý do duy nhất tại sao Phần A (đại số bậc hai) "tái xuất hiện" bên trong Phần E** — nghiệm của ODE tuyến tính hệ số hằng luôn quy về nghiệm của **một phương trình đại số bậc hai** (phương trình đặc trưng). Ba trường hợp Δ (ở đây là γ² − ω₀²) dương/0/âm cho ba chế độ nghiệm (quá tắt / tới hạn / dưới tới hạn) — khớp chính xác với bảng O5 file gốc.
- **Thuật toán ALG-E3a:**
  1. Đưa phương trình chuyển động (từ D1 hoặc C.2(c)) về đúng dạng chuẩn ẍ + 2γẋ + ω₀²x = f(t).
  2. Giải phương trình đặc trưng cho nghiệm thuần nhất x_h.
  3. Tìm một nghiệm riêng x_p ứng với f(t) (xem (b)).
  4. Nghiệm tổng quát x = x_h + x_p; dùng điều kiện đầu (x(0), ẋ(0)) để xác định 2 hằng số tích phân.

**(b) Số phức & phương pháp phasor cho nghiệm riêng [C]** — công cụ **bắt buộc** cho O6:
- Với f(t) = F₀cos Ωt, viết f̂(t) = F₀e^{iΩt} (lấy phần thực ở cuối). Thử x̂ = X̂e^{iΩt}.
- Thay vào ODE: (−Ω² + 2iγΩ + ω₀²)X̂ = F₀/m ⇒ **X̂ = (F₀/m)/(ω₀² − Ω² + 2iγΩ)**.
- Biên độ thực X = |X̂|, độ trễ pha δ = −arg(X̂).
- **Vì sao số phức là cấu trúc đúng (không phải "mẹo")**: một số phức z = Xe^{−iδ} mã hóa **đồng thời** biên độ và pha của một dao động điều hòa; phép nhân với e^{iΩt} tương đương một phép **quay-và-co-giãn**, biến đạo hàm bậc hai (toán tử vi phân) thành **phép nhân đại số** (i Ω)² — đây là lý do bài toán ODE bậc hai "sụp" thành bài toán **đại số Phần A** một khi đã chuyển qua miền phức.
- **Thuật toán ALG-E3b:**
  1. Viết lực cưỡng bức dưới dạng phần thực của F₀e^{iΩt}.
  2. Thay x = Re(X̂e^{iΩt}), được phương trình đại số (phức) cho X̂.
  3. Giải X̂ bằng Phần A (nay hệ số là số phức).
  4. X = |X̂|, tan δ = −Im(X̂)/Re(X̂) (hoặc dùng công thức đóng gói sẵn trong O6).

**(c) Hệ số bất định (undetermined coefficients) khi không dùng số phức [C]** — thay thế (b): thử x_p = X cos(Ωt − δ) trực tiếp, khai triển cos(Ωt−δ) = cosΩt cosδ + sinΩt sinδ, cân bằng hệ số của cos Ωt và sin Ωt riêng biệt ⇒ **lại là một hệ phương trình tuyến tính 2×2 (Phần A)** cho (X cosδ, X sinδ). Hai đường (b) và (c) phải cho cùng kết quả — dùng làm kiểm tra chéo.

**(d) Điều kiện cộng hưởng — lại là bài toán cực trị (nối với Phần C) [C]** — X(Ω) đạt max khi dX²/dΩ² = 0 (vì X² là hàm hữu tỉ đơn giản của Ω²) ⇒ Ω_r² = ω₀² − 2γ². Đây là minh chứng khác cho việc Phần C (cực trị) và Phần E không tách rời — chúng lồng vào nhau.

### E.4. Bảng đối chiếu ngược

| Công cụ gốc | Dùng cấu trúc E nào |
|---|---|
| O1 | E.3(a) với γ=0: nghiệm r = ±iω₀ ⇒ x = A cos(ω₀t+φ) (dùng Euler e^{iθ}=cosθ+isinθ để "giải thích" vì sao nghiệm phức liên hợp cho ra hàm thực dao động) |
| O5 | E.3(a) đầy đủ ba chế độ |
| O6 | E.3(a)+(b)/(c)+(d) |
| O2 (tổng hợp dao động, phách) | E.3(b) — cộng hai phasor cùng ω hoặc khác ω (biểu diễn hình học trên mặt phẳng phức) |

---

## PHẦN F. ĐẠI SỐ TUYẾN TÍNH MA TRẬN: HỆ NHIỀU ẨN, ĐỊNH THỨC, TRỊ RIÊNG–VECTOR RIÊNG

### F.1. Phạm vi

Đây chính là cấu trúc mà README nhắc tới qua ví dụ **Nodal Analysis** (mạch điện) — "bưng từ Đại học xuống". Trong cơ chất điểm, nó xuất hiện ở hai tầng: (i) **tầng đại số tuyến tính cơ bản** (đã nói ở Phần A, n ẩn n phương trình, dùng khử Gauss/Cramer); (ii) **tầng cao hơn** — bài toán trị riêng, khi số **phương trình vi phân** ghép với nhau (không chỉ phương trình đại số).

### F.2. Thư viện kỹ thuật con

**(a) Hệ đại số tuyến tính tổng quát (nhắc lại có hệ thống hóa) [C]**
- Viết dưới dạng ma trận **A**x = b. Số ẩn = số phương trình độc lập ⇔ det(A) ≠ 0 (khớp điều kiện (3)+(5) của README: Completeness + Well-posedness).
- **Với hệ nhiều vật nối (D1+K7), "pattern chuẩn bị trước" (README):** ma trận A thường có cấu trúc **gần đường chéo** (mỗi vật chỉ liên kết trực tiếp với 1–2 vật khác qua dây/lò xo) — tương tự ma trận tổng dẫn trong Nodal Analysis. Nhận ra cấu trúc này giúp khử ẩn theo thứ tự tối ưu thay vì Gauss "mù".

**(b) Bài toán trị riêng – vector riêng (eigenvalue problem) [C]** — cấu trúc riêng của O7 (hệ dao động ghép):
- Từ **M**ẍ + **K**x = 0, thử x = **a**e^{iωt} ⇒ (**K** − ω²**M**)**a** = 0.
- Có nghiệm **a** ≠ 0 ⇔ **det(K − ω²M) = 0** — đây lại là một **phương trình đại số** (thường bậc n theo ω²) theo đúng Phần A, nhưng hệ số của nó đến từ một **định thức ma trận**.
- Mỗi nghiệm ω_j² là một **trị riêng suy rộng**; vector riêng tương ứng **a**_j là **mode chuẩn** — mô tả *tỉ lệ biên độ tương đối cố định* giữa các vật khi chỉ dao động ở tần số đó.
- **Tính trực giao (đã nêu ở O7 file gốc):** **a**_i^T**M****a**_j = 0 với i≠j — đây là hệ quả toán học thuần túy của việc **M**, **K** đối xứng (định lý phổ cho ma trận đối xứng/cặp ma trận đối xứng xác định dương) — **không cần chứng minh lại mỗi lần**, chỉ cần dùng.
- **Thuật toán ALG-F2b:**
  1. Chọn tọa độ lệch khỏi cân bằng cho mỗi vật (nối Phần C.2(c)).
  2. Lập **M** từ động năng (K = ½ẋ^T**M**ẋ), **K** từ thế năng (U = ½x^T**K**x, tức K_ij = ∂²U/∂q_i∂q_j tại cân bằng — lại là Phần C!).
  3. **Khai thác đối xứng của bài toán trước khi giải định thức thô** (xem Phần G.2(c)): đổi sang tọa độ tổng/hiệu có thể làm **M**, **K** trở thành ma trận chéo ngay lập tức, biến bài toán n×n thành n bài toán 1×1 (mỗi cái là một O1 độc lập).
  4. Nếu không có đối xứng rõ: giải det(**K**−ω²**M**)=0 trực tiếp (Phần A cho đa thức bậc n theo ω²).
  5. Với mỗi ω_j², giải (**K**−ω_j²**M**)**a**_j = 0 (lại là Phần A, hệ suy biến bậc (n−1)).
  6. Nghiệm tổng quát x = Σc_j**a**_jcos(ω_jt+φ_j); dùng điều kiện đầu + tính trực giao để tách c_j, φ_j (phép chiếu — Phần B.2(a)).
- **Kiểm tra chéo bắt buộc (nối 7.5 file gốc):** nếu hệ không bị "neo" (không có lò xo nối đất) phải tồn tại **mode ω=0** (tịnh tiến toàn hệ) — đây là kiểm tra bằng cách thử det(**K**) = 0 khi ω=0, một kiểm tra toán học thuần túy cho một tính chất vật lý (bảo toàn động lượng tổng khi không ngoại lực).

**(c) Khối lượng rút gọn — một phép đổi biến tuyến tính đặc biệt [C]**
- (**r**, **R**) = phép đổi biến tuyến tính từ (**r**₁, **r**₂): **R** = (m₁**r**₁+m₂**r**₂)/M, **r** = **r**₁−**r**₂.
- Về mặt toán, đây là một phép **chéo hóa đồng thời** động năng: K = ½m₁ṙ₁²+½m₂ṙ₂² = ½MṘ² + ½μṙ² (không còn số hạng chéo ṙ₁·ṙ₂) — cùng bản chất với bước đổi biến tổng/hiệu ở (b).

### F.3. Bảng đối chiếu ngược

| Công cụ gốc | Dùng cấu trúc F nào |
|---|---|
| D1 + K7 (hệ nhiều vật nối) | F.2(a) |
| O7 | F.2(b) |
| P7, C7 (hai vật → khối tâm) | F.2(c) |
| C6 (va chạm 2D, 4 ẩn 4 pt) | F.2(a) |

---

## PHẦN G. NGUYÊN LÝ BIẾN PHÂN & ĐỐI XỨNG (EULER–LAGRANGE, NOETHER) **[EXT, bonus hợp pháp]**

### G.1. Phạm vi và vị trí trong hệ thống

README: *"Cấu trúc của bài Toán quyết định phương pháp giải... hãy biết dùng 'thuật toán' để giảm tải."* Lagrange + Noether là **thuật toán tổng quát nhất** trong toàn bộ danh sách — nó **sinh ra** D1 (Newton), C1 (động lượng), C7 (momen động lượng), C4 (năng lượng) như các **trường hợp riêng**. Syllabus IPhO không bắt buộc, nhưng theo chính đánh giá trong file gốc: *"công cụ 'hạng nặng' là bonus hợp pháp"* — nắm nó giúp **kiểm tra chéo cực nhanh** bất kỳ bài D/C/O nào.

### G.2. Thư viện kỹ thuật con

**(a) Phiếm hàm tác dụng & phương trình Euler–Lagrange [C]**
- L(q, q̇, t) = T − U (hàm Lagrange). Nguyên lý: quỹ đạo thật làm cực trị tác dụng S = ∫L dt.
- **Phương trình Euler–Lagrange:** d/dt(∂L/∂q̇) − ∂L/∂q = Q_nt (lực suy rộng không thế).
- Đây là **cấu trúc toán học của phép tính biến phân (calculus of variations)** — khác về bản chất so với Phần C (cực trị của một hàm số) vì ở đây ta tìm cực trị của một **phiếm hàm** (hàm nhận cả một quỹ đạo làm đối số). Tuy nhiên **kỹ thuật tính toán cuối cùng quy về đạo hàm riêng và đạo hàm toàn phần theo t** — vẫn dùng công cụ của Phần C và D.
- **Thuật toán ALG-G2a (khớp ALG-C9 file gốc, nay tách rõ phần "Toán"):**
  1. Dùng Phần F (số bậc tự do = 2N − số ràng buộc) chọn bộ q độc lập.
  2. Viết T(q, q̇), U(q) bằng Phần B (động năng = tổng ½mv² sau khi biểu diễn mọi vận tốc qua q̇ — một phép **đạo hàm của ràng buộc hình học**, chính là K7!).
  3. L = T − U.
  4. Với mỗi q_i: tính ∂L/∂q̇_i, lấy d/dt, trừ ∂L/∂q_i.
  5. Thu được **hệ ODE** (một phương trình mỗi bậc tự do) — nối thẳng vào Phần E (nếu tuyến tính hóa được) hoặc Phần F (nếu là hệ tuyến tính nhiều bậc tự do).

**(b) Tích phân đầu & tọa độ cyclic [C]**
- Nếu ∂L/∂q_i = 0 (q_i "cyclic"/không xuất hiện tường minh trong L) ⇒ **p_i = ∂L/∂q̇_i = hằng số** — đây là **định lý Noether phiên bản đại số**, và là cách **chứng minh** (không chỉ "nhận ra") các định luật bảo toàn C1, C7:
  - L không đổi khi dịch chuyển theo x (tọa độ x không hiện diện tường minh trong U) ⇒ động lượng P_x bảo toàn.
  - L không đổi khi quay quanh trục e (chỉ phụ thuộc r, không phụ thuộc φ) ⇒ momen động lượng L_e bảo toàn.
  - L không phụ thuộc t tường minh ⇒ "năng lượng Jacobi" h = Σq̇_i ∂L/∂q̇_i − L bảo toàn (= E thường khi ràng buộc không phụ thuộc t).
- **Đây chính là lời giải thích toán học đầy đủ cho C8 (Quét đối xứng) trong file gốc** — bảng "phép biến đổi → đại lượng bảo toàn" không phải kinh nghiệm, mà là hệ quả trực tiếp của (b).

**(c) Đối xứng để giảm bậc tự do trước khi giải (liên kết Phần F) [H]**
- Khi L bất biến dưới một phép hoán vị (ví dụ đổi hai vật giống nhau trong hệ ba vật m–M–m), **tọa độ đối xứng/phản đối xứng** (tổng/hiệu) tự động **chéo hóa** ma trận **K**, **M** của Phần F mà không cần giải định thức bậc cao. Đây là kỹ thuật tiết kiệm thời gian quan trọng nhất khi gặp hệ ghép có đối xứng rõ ràng.

### G.3. Bảng đối chiếu ngược

| Công cụ gốc | Dùng cấu trúc G nào |
|---|---|
| C9 | G.2(a) toàn bộ |
| C8 | G.2(b) — nền tảng lý thuyết |
| C1, C2, C7 (khi dùng như kiểm tra chéo) | G.2(b) |
| O7 (khi hệ có đối xứng) | G.2(c) + F.2(b) |

---

## PHẦN H. GIẢI TÍCH TIỆM CẬN / NHIỄU LOẠN & CHUỖI LŨY THỪA

### H.1. Phạm vi

Khi Phần C.2(c) (Taylor bậc 2) **không đủ** — hoặc vì U''(q₀) = 0 (suy biến, cần bậc cao hơn), hoặc vì biên độ/góc **không nhỏ** và ta cần **hiệu chỉnh** cho kết quả bậc thấp. Đây là cấu trúc của O3 (chu kỳ con lắc góc lớn), O8 (dao động phi tuyến, Duffing), và P12 khi cần biết **sai số Err**, không chỉ giá trị gần đúng.

### H.2. Thư viện kỹ thuật con

**(a) Khai triển nhiễu loạn chính quy (regular perturbation) [C]**
- Đưa phương trình về dạng không thứ nguyên với một tham số nhỏ ε (biên độ/chiều dài, hoặc hệ số phi tuyến).
- Giả sử nghiệm x = x₀ + εx₁ + ε²x₂ + …, thay vào phương trình, **cân bằng từng bậc của ε** — một kỹ thuật thuần túy đại số (Phần A) lặp lại nhiều lần theo bậc.
- **Mẫu chuẩn (đã kiểm số trong file gốc):** con lắc đơn T ≈ T₀(1+θ₀²/16+11θ₀⁴/3072) — bậc 0 cho T₀ = 2π√(l/g) (chính là kết quả Phần E với γ=0); bậc 2 và 4 là hiệu chỉnh nhiễu loạn.
- **Duffing** ẍ+ω₀²x+εx³=0: phương pháp **Poincaré–Lindstedt** (nhiễu loạn có hiệu chỉnh tần số ω = ω₀+εω₁+…) để tránh "số hạng thế kỷ" (secular term, số hạng tăng không giới hạn theo t mà nghiệm nhiễu loạn ngây thơ sẽ sinh ra).

**(b) Hàm tỉ lệ (scaling law) khi thế năng là đơn thức [C]**
- Nếu U(x) ∝ |x|ⁿ (không khai triển Taylor nữa mà dùng **dạng chính xác**): từ phân tích thứ nguyên (P11 file gốc) + công thức chu kỳ tích phân T = √(2m)∫dq/√(E−U), suy ra **T ∝ A^{1−n/2}** bằng phép đổi biến x = Au (không thứ nguyên hóa biên độ) — biến tích phân phụ thuộc A thành tích phân **không phụ thuộc A** nhân với thừa số A^{1−n/2} đứng ngoài.
- Đây là kỹ thuật "rẻ nhất": **không cần giải ODE**, chỉ cần phép đổi biến tỉ lệ.

**(c) Khi nào H thay thế được Phần C, khi nào không [H]**
- Nếu chỉ cần **tần số góc nhỏ** (bậc thấp nhất) → dùng Phần C (Taylor bậc 2) là đủ, nhanh hơn.
- Nếu cần **sai số tương đối** của một công thức gần đúng, hoặc bậc thấp nhất của U triệt tiêu → bắt buộc dùng Phần H.

### H.3. Bảng đối chiếu ngược

| Công cụ gốc | Dùng cấu trúc H nào |
|---|---|
| O3 (chu kỳ con lắc chính xác hơn) | H.2(a) |
| O8 | H.2(a), H.2(b) |
| P12 (phần "Err") | H.2(a) |
| P11 | H.2(b) (nền tảng không thứ nguyên hóa) |

---

## PHẦN I. BẢNG TRA CHÉO TỔNG HỢP (DÙNG TRONG PHÒNG THI)

### I.1. Từ "Post" (kết quả sau mô hình hóa) → Cấu trúc Toán

| Dạng phương trình thu được sau Vấn đề 1 | Cấu trúc | Mục |
|---|---|---|
| n phương trình đại số tuyến tính, n ẩn số (lực, gia tốc) | F (hoặc A nếu n nhỏ) | A.2(a), F.2(a) |
| Một phương trình bậc hai theo ẩn hình học (góc, thời gian) | A | A.2(b) |
| "Lớn nhất/nhỏ nhất/điều kiện để" | C (song song A nếu bậc hai) | C.2(a) |
| Tích phân công/năng lượng, a(x)/a(v)/a(t) | D | D.2 |
| ẍ + 2γẋ + ω₀²x = f(t) | E | E.2 |
| Hệ ODE tuyến tính ghép (≥2 bậc tự do dao động) | F | F.2(b) |
| Cần chứng minh/kiểm tra một đại lượng bảo toàn | G | G.2(b) |
| U''(q₀) = 0 hoặc cần sai số bậc cao | H | H.2 |
| Quỹ đạo hình học (parabol, elip, bao hình) | B | B.2(c) |

### I.2. Quy trình tổng — tích hợp vào Bước 5 của Giao thức 1.8 (file gốc)

```
Sau BƯỚC 4 (đã lọc các cặp (ℓ, CHỖ) có ý nghĩa), với MỖI Post thu được:
  (i)   Xác định hình dạng phương trình (đại số? ODE? ma trận? phiếm hàm?)
        → tra bảng I.1 để chọn đúng một trong 8 cấu trúc A–H.
  (ii)  Áp dụng ĐÚNG thuật toán cố định (ALG-X) của cấu trúc đó — không "mò".
  (iii) Nếu cấu trúc cho ra một cấu trúc "con" bên trong (vd: E sinh ra một
        phương trình đặc trưng = A; F sinh ra một định thức = A; G sinh ra
        một ODE = E hoặc D) → đệ quy xuống cấu trúc con bằng ALG tương ứng.
  (iv)  Kiểm tra chéo: nếu có ≥ 2 con đường toán học tới cùng một đại lượng
        (ví dụ Δ=0 của A và F'=0 của C), bắt buộc đối chiếu — đây là cách
        rẻ nhất để phát hiện lỗi mô hình hóa (điều kiện (4) README).
```

### I.3. Vì sao 8 cấu trúc là "đủ" cho VPHO/HSGQG/IPhO phần cơ chất điểm **[H, cần đối chiếu tiếp qua 9.4 file gốc]**

- Toàn bộ 16 mục đề cương gốc (K1–K8, D1–D11, C1–C9, O1–O8) đã được map 1-1 hoặc nhiều-1 vào A–H ở các bảng "Bảng đối chiếu ngược" của từng phần — không có công cụ nào bị bỏ sót, không có cấu trúc nào không dùng đến.
- Theo đúng tinh thần README ("Cùng một cấu trúc Toán có thể sinh ra nhiều dạng bài Vật lý khác nhau"): 8 cấu trúc này **không đổi** dù đề thi biến tấu số lượng vật, loại lực, hình dạng ràng buộc — **biến tấu chỉ thay hệ số và kích thước của hệ phương trình**, không thay loại cấu trúc.
- **Giới hạn trung thực:** danh sách này được suy ra bằng cách quét lại chính file "Cơ Chất Điểm" đã cho, nên nó **đảm bảo đủ cho phạm vi của file đó** (động học/động lực học/bảo toàn/dao động chất điểm). Nếu đề thi mở rộng sang vật rắn, chất lưu, hoặc dùng công cụ ngoài phạm vi, cần bổ sung (ví dụ: đại số tensor quán tính cho vật rắn) — đúng tinh thần mục 9.3/9.4 file gốc.

---

## PHẦN J. MƯỜI LĂM BẪY TOÁN HỌC XUYÊN SUỐT (bổ sung cho 7.4 file gốc, tầng Toán thuần túy)

1. Quên kiểm miền xác định của ẩn sau khi đổi biến (vd. đặt u = tanθ nhưng θ có miền hẹp hơn miền của u).
2. Bỏ nghiệm thứ hai của phương trình bậc hai mà không kiểm tra tính hợp lệ vật lý (Phần A).
3. Nhầm "Δ ≥ 0" (tồn tại nghiệm thực) với "nghiệm hợp lý vật lý" (còn cần t>0, góc trong khoảng…).
4. Quên nhân tích vô hướng đúng cách khi chiếu lực lên trục không vuông góc, không trực giao (Phần B).
5. Đạo hàm vector đơn vị **e**_r, **e**_φ như thể chúng là hằng số (Phần B.2(b)).
6. Khai triển Taylor thế năng chỉ đến bậc 1 (triệt tiêu, vô dụng) thay vì bậc 2 (Phần C.2(c)).
7. Bỏ số hạng hình học khi lực tại cân bằng khác 0 (Phần C.2(c), bẫy O4).
8. Nhầm phương trình đặc trưng bậc hai (Phần E) với phương trình vật lý gốc — quên "r" là một đại lượng toán học thuần túy, không phải tốc độ.
9. Dùng công thức hệ số bất định (E.3(c)) nhưng quên cân bằng **riêng biệt** hệ số cos và sin.
10. Quên kiểm mode ω = 0 khi hệ không bị neo cố định (Phần F.2(b)).
11. Lập ma trận **M**, **K** không đối xứng do sai sót khi viết động năng/thế năng (Phần F.2(b)).
12. Dùng δr không tương thích ràng buộc khi ràng buộc phụ thuộc thời gian (Phần G.2(a), nguyên lý công ảo).
13. Nhầm "tọa độ cyclic" khi thế năng **có vẻ** không chứa q nhưng ràng buộc động năng lại chứa q ẩn trong M_eff(q) (Phần G.2(b)).
14. Dùng khai triển nhiễu loạn "ngây thơ" (không Poincaré–Lindstedt) cho bài có số hạng thế kỷ (Phần H.2(a)).
15. Nhầm giữa "không thứ nguyên hóa để tìm tỉ lệ" (Phần H.2(b)) với "tuyến tính hóa để tìm tần số" (Phần C.2(c)) — hai mục tiêu khác nhau, không thể dùng lẫn.

---

## PHẦN K. GHI CHÚ TRUNG THỰC VÀ GIỚI HẠN

1. Tài liệu này **suy luận ngược** từ nội dung đã có trong file "Cơ Chất Điểm" — nó không phải một nguồn độc lập đã được kiểm chứng bằng đề thi thật, giống hệt giới hạn đã nêu ở mục 9.1–9.3 của file gốc.
2. Các "thuật toán ALG-X" trong tài liệu này là **tổ chức lại** của tôi **[H]** dựa trên kỹ thuật toán chuẩn mực **[C]**; bản thân từng kỹ thuật con (Cramer, khử Gauss, phương trình đặc trưng, trị riêng, Euler–Lagrange, nhiễu loạn Poincaré–Lindstedt) là kiến thức toán chuẩn, có thể đối chiếu với Boas *Mathematical Methods in the Physical Sciences* (đại số tuyến tính, ODE, số phức, chuỗi) và Stewart *Calculus* (đạo hàm, tích phân, Taylor) — đúng hai tài liệu Toán mà bạn đã nêu trong file gốc.
3. Phần G và Phần H là **[EXT]** — vượt khung đề cương ảnh gốc nhưng được giữ lại vì (a) Lagrange là công cụ kiểm tra chéo cực mạnh và (b) nhiễu loạn là bắt buộc cho các câu hỏi "chính xác hơn" thường gặp ở IPhO/VPHO vòng sâu.
4. Nếu bạn gửi đề cụ thể, có thể chạy thử Phần I.2 (quy trình tích hợp) trên đề đó để kiểm tra 8 cấu trúc có thực sự phủ hết hay cần bổ sung cấu trúc thứ 9 (ví dụ: phương trình sai phân/truy hồi tường minh cho bài đếm va chạm kiểu π — hiện đang được xếp tạm vào Phần A.2(a) dạng lặp, nhưng có thể xứng đáng một mục riêng nếu gặp nhiều bài tương tự).
