*Tập trung vào : Định lí O-G, Thế năng tương tác của hệ điện tích, Lí thuyết lưỡng cực điện, Điện môi, Vật dẫn, Mạch 1 chiều, phi tuyến, Dao động điện từ, điốt.

# ĐIỆN TỪ NÂNG CAO — THƯ VIỆN CÔNG CỤ & PRECONDITION
### Giải pháp cho Vấn đề 1 (nhận diện CÔNG CỤ) và Vấn đề 2 (chuyển Vật lý → Toán)
*Phạm vi: 7 mảng trong ảnh — Định lí O–G, Thế năng tương tác, Lưỡng cực điện, Điện môi, Vật dẫn, Mạch 1 chiều & phi tuyến, Dao động điện từ & điốt. Đối tượng: HSGQG / VPhO / IPhO và nền tảng nghiên cứu.*

---

## PHẦN 0 — KHUNG VẬN HÀNH

Mỗi công cụ ℓ được đóng gói thành một **thẻ** gồm 7 ô:

| Ô | Ý nghĩa |
|---|---|
| **Dom(ℓ)** | Miền vật lý mà ℓ *phát biểu được* |
| **Pre(ℓ)** | Điều kiện **cần** để ℓ đúng |
| **Suf(ℓ)** | Điều kiện **đủ** để ℓ *giải ra được ẩn* (khác Pre! — đây là ô quan trọng nhất) |
| **Post(ℓ)** | Ràng buộc toán học mới sinh ra (chính là sản phẩm của Vấn đề 2) |
| **Err(ℓ)** | Sai số / giới hạn xấp xỉ |
| **CHỖ-detector** | Quy trình duyệt cơ học để tìm nơi áp dụng |
| **Toán hoá** | Loại đối tượng toán thu được: phương trình đại số / ODE / PDE / hệ tuyến tính / phương trình siêu việt / bài toán biên |

**Nguyên tắc vàng của mảng Điện từ:** hầu hết mọi định luật ở đây có **Pre rất rộng nhưng Suf rất hẹp**. Ví dụ, Định lí O–G *luôn đúng* với mọi mặt kín (Pre gần như trống), nhưng chỉ *giải ra được E* khi có đối xứng (Suf rất chặt). **Toàn bộ độ khó của bài điện từ nằm ở ô Suf.** Người học yếu nhầm Pre với Suf, rồi viết Gauss cho một mặt bất đối xứng và bế tắc.

**Ba trục để định vị mọi bài điện từ tĩnh** (dùng trục này để chọn nhóm công cụ, trước khi duyệt CHỖ):

1. **Trục nguồn:** điện tích *cho trước* (tự do, cố định) hay *chưa biết* (cảm ứng trên vật dẫn, liên kết trong điện môi)?
   → Cho trước ⇒ tích phân/chồng chất/Gauss. Chưa biết ⇒ bài toán biên (Laplace + uniqueness + ảnh điện).
2. **Trục đối xứng:** nhóm đối xứng của *toàn bộ* cấu hình (kể cả vật dẫn & điện môi) có truyền dẫn trên một mặt kín không?
   → Có ⇒ Gauss giải trực tiếp. Không ⇒ chồng chất các mảnh đối xứng, hoặc khai triển đa cực, hoặc Laplace.
3. **Trục tuyến tính:** quan hệ cấu thành (D–E, I–U) có tuyến tính không?
   → Có ⇒ chồng chất, ma trận điện dung, Nodal. Không ⇒ đường tải, liệt kê trạng thái, tích phân từng khúc.

---

## PHẦN A — BẢN ĐỒ CÔNG CỤ (tập L)

| # | Nhóm | Công cụ chính |
|---|---|---|
| 1 | **Định lí O–G** | Gauss tích phân (E, D), Gauss vi phân, hộp Gauss ở mặt phân cách, chồng chất mảnh đối xứng, định lí lớp cầu/vỏ |
| 2 | **Năng lượng** | W tổng cặp, W = ½∫ρV, W = (ε₀/2)∫E², W = ½∫D·E, năng lượng lắp ráp, F = −∇W\|_Q vs +∇W\|_V, áp suất σ²/2ε₀ |
| 3 | **Lưỡng cực** | p, V và E của lưỡng cực, U = −p·E, τ = p×E, F = ∇(p·E), khai triển đa cực, lưỡng cực cảm ứng p = αE |
| 4 | **Điện môi** | P, ρ_b = −∇·P, σ_b = P·n̂, D = ε₀E + P, ∮D·dA = Q_tự do, điều kiện biên E_t / D_n, Clausius–Mossotti |
| 5 | **Vật dẫn** | E_trong = 0, V = const, σ = ε₀E_n, định lí duy nhất, ảnh điện (phẳng, cầu), ma trận C_ij, **định lí tương hỗ Green** |
| 6 | **Mạch 1 chiều & phi tuyến** | Nodal analysis, Thévenin/Norton, đối xứng & thang vô hạn, Y–Δ, **đường tải**, liệt kê trạng thái điốt, điện trở vi phân r_d, ổn định điểm làm việc |
| 7 | **Dao động & điốt** | LC/RLC, bảo toàn năng lượng, **ODE tuyến tính từng khúc + điều kiện nối**, ánh xạ chu kỳ (Poincaré), chỉnh lưu & ghim áp |

---

## PHẦN B — CÁC THẺ CÔNG CỤ

---

### THẺ 1 — ĐỊNH LÍ OSTROGRADSKY–GAUSS

**Phát biểu.** ∮_S **E**·d**A** = Q_trong/ε₀ ; dạng vi phân ∇·**E** = ρ/ε₀ ; dạng vật chất ∮_S **D**·d**A** = Q_tự do,trong.

**Dom.** Mọi trường tuân luật nghịch đảo bình phương với nguồn vô hướng. Đúng cả khi trường biến thiên (là một trong 4 phương trình Maxwell). Đúng cho trọng trường với thay thế ρ/ε₀ → −4πGρ.

**Pre.** (rất yếu) S là mặt kín, khả vi từng mảnh; không có điện tích điểm *nằm đúng trên* S. Đó là tất cả — định lí **luôn** đúng.

**Suf (ô quyết định).** Gauss *giải ra* |E| khi và chỉ khi tồn tại mặt S chia được thành các mảnh S_k sao cho trên mỗi mảnh:
- (a) **E** ⊥ mảnh và |E| = const (mảnh sinh thông lượng), **hoặc**
- (b) **E** ∥ mảnh (thông lượng bằng 0).

Điều kiện hình thức: nhóm đối xứng G của **toàn bộ phân bố điện tích thực tế** (điện tích cho trước **+ điện tích cảm ứng trên vật dẫn + điện tích liên kết trong điện môi**) phải tác động truyền dẫn trên mỗi mảnh S_k. Chỉ có **ba** lớp đạt được trong chương trình thi:
- **Cầu:** đối xứng O(3) → S là mặt cầu đồng tâm → E(r)·4πr² = Q(r)/ε₀
- **Trụ vô hạn:** tịnh tiến theo z + quay quanh z + gương → S là mặt trụ → E(r)·2πrL = λL/ε₀
- **Phẳng vô hạn:** tịnh tiến trong mặt phẳng + gương → S là hộp dẹt → E·2A = σA/ε₀

> **Lỗi chết người số 1:** đặt một điện tích điểm lệch tâm bên trong quả cầu, rồi vẫn viết E·4πr² = Q/ε₀. Sai, vì Q thì đối xứng cầu nhưng điện tích điểm thì không. Gauss vẫn đúng (thông lượng vẫn là Q/ε₀) nhưng **không giải được E**.

**Post.** Một **phương trình đại số** cho một hàm vô hướng một biến |E|(r). Đây chính là điểm chuyển Vật lý → Toán: cả bài trở thành E(r) = f(r), rồi V(r) = −∫E dr.

**Err.** Trụ/phẳng "vô hạn" thực ra hữu hạn: sai số bậc O(R/L) do hiệu ứng mép. Chỉ bỏ qua khi bài nói rõ "dài vô hạn" hoặc L ≫ R.

**CHỖ-detector (duyệt cơ học).**
1. Liệt kê **mọi** phép đối xứng của cấu hình cuối cùng (sau khi đã tính vật dẫn & điện môi).
2. Với mỗi đối xứng, vẽ họ mặt bất biến tương ứng (cầu / trụ / phẳng đôi).
3. Cho bán kính (hoặc khoảng cách) chạy **qua mọi miền**: trong lòng, trong lớp vật chất, trong khe, ngoài cùng. Mỗi miền là một CHỖ → một phương trình.
4. Riêng với vật dẫn: đặt **hộp Gauss dẹt** cưỡi lên *mỗi* mặt vật dẫn → E_ngoài = σ/ε₀. Đây là CHỖ mà 90% học sinh quên duyệt.
5. Riêng với mặt phân cách bất kỳ: hộp dẹt → điều kiện nhảy E_2n − E_1n = σ/ε₀.

**Kỹ thuật nâng cao bắt buộc thuộc.**
- **Chồng chất mảnh đối xứng:** quả cầu ρ có khoang lệch tâm = (cầu đặc ρ) + (cầu nhỏ −ρ). Trong khoang: **E** = ρ**a**/(3ε₀) — **trường đều**. Tương tự cho trụ: **E** = ρ**a**/(2ε₀). Đây là một trong những mẫu ra đề yêu thích nhất của HSGQG.
- **Định lí vỏ:** vỏ cầu tích điện đều không tạo trường bên trong; ngoài thì như điện tích điểm ở tâm.
- **Gauss cho D** để bỏ qua điện tích liên kết (xem Thẻ 4).

**Toán hoá.** Bài toán trở thành: tính Q(r) = ∫₀^r ρ(r′)4πr′²dr′ (một tích phân xác định), rồi đại số hoá. Nếu ρ cho bởi ρ(E) (điện môi phi tuyến, plasma) thì ∇·E = ρ(E)/ε₀ trở thành **ODE phi tuyến** — dạng ra IPhO.

---

### THẺ 2 — THẾ NĂNG TƯƠNG TÁC CỦA HỆ ĐIỆN TÍCH

**Năm công thức và Pre riêng của từng cái** (đây là nơi sai nhiều nhất):

| Công thức | Dùng khi | Có chứa tự năng? |
|---|---|---|
| W = ½ Σ_{i≠j} kq_iq_j/r_ij | hệ điện tích **điểm** | **Không** |
| W = ½ ∫ρV dτ | phân bố **liên tục** | **Có** |
| W = ½ ∫σV dA | điện tích trên **mặt** | Có |
| W = (ε₀/2)∫E² dτ (toàn không gian) | phân bố liên tục | **Có** — phân kỳ với điện tích điểm |
| W = ½ ∫**D**·**E** dτ | có **điện môi tuyến tính** | Có; đã gộp năng lượng phân cực |

**Pre then chốt.** Không bao giờ dùng (ε₀/2)∫E² cho hệ điện tích điểm (phân kỳ). Khi bài hỏi "công cần thiết để đưa các điện tích lại gần nhau" ⇒ chỉ tương tác ⇒ dùng tổng cặp. Khi bài hỏi "năng lượng dự trữ trong quả cầu tích điện" ⇒ có tự năng ⇒ dùng ∫E².

**Suf.** ∫E² giải được khi đã có E(r) từ Thẻ 1 (nên hai thẻ này luôn đi cặp: Gauss → E(r) → W). Tổng cặp giải được khi số điện tích hữu hạn nhỏ hoặc có đối xứng để nhóm lại.

**Post.** Một **số** hoặc một **hàm W(x)** của tham số hình học x.

**Năng lượng lắp ráp (assembly).** W = ∫₀^Q V(q) dq, với V(q) là thế tại nơi đưa dq vào khi đã có q. Quả cầu đặc bán kính R: W = 3kQ²/5R. Vỏ cầu: kQ²/2R.

**Cầu nối sang lực — ô Suf tinh vi nhất của cả tài liệu:**

- Hệ **cô lập** (điện tích giữ không đổi): F_x = −(∂W/∂x)|_Q
- Hệ **nối nguồn** (hiệu điện thế giữ không đổi): F_x = **+**(∂W/∂x)|_V

Dấu ngược nhau vì nguồn bơm thêm công 2dW. Hai cách cho **cùng** một lực nếu tính đúng. Ràng buộc này là Pre — quên nó là mất trọn câu.

- **Áp suất tĩnh điện** lên mặt vật dẫn: p = σ²/(2ε₀) = ε₀E²/2, luôn hướng **ra ngoài**. Hệ số ½ vì mảnh diện tích chỉ chịu trường của *phần còn lại*: E_còn lại = σ/2ε₀. Đây là "định lí nửa trường", một CHỖ kinh điển.

**CHỖ-detector.** (i) Mọi cặp điện tích → tổng cặp. (ii) Mọi miền không gian có E ≠ 0 → ∫E². (iii) Mọi tham số hình học mà bài cho "di chuyển / kéo ra / dịch chuyển" → lập W(x) rồi đạo hàm. (iv) Mọi mặt vật dẫn → áp suất σ²/2ε₀.

**Toán hoá.** W(x) → bài toán đạo hàm/cực trị; hoặc W₁ = W₂ thành phương trình bảo toàn; hoặc mW = ½mv² thành phương trình chuyển động.

---

### THẺ 3 — LÍ THUYẾT LƯỠNG CỰC ĐIỆN

**Định nghĩa.** **p** = Σ q_i**r**_i = ∫ **r** ρ dτ. **Bất biến với gốc toạ độ khi và chỉ khi Q_tổng = 0** — đây là một Pre luôn phải kiểm tra trước khi nói "mômen lưỡng cực của hệ".

**Trường.**
- V(**r**) = k **p**·**r̂**/r²
- **E** = k[3(**p**·**r̂**)**r̂** − **p**]/r³ ; độ lớn E = (kp/r³)√(1+3cos²θ)
- Trên trục: E = 2kp/r³. Trên mặt phẳng vuông góc: E = kp/r³ (ngược chiều **p**).

**Pre.** r ≫ d (kích thước hệ). Nếu không thoả ⇒ phải dùng đa cực bậc cao hoặc tính trực tiếp.

**Tương tác với trường ngoài.**
- U = −**p**·**E** (Pre: **p** cứng, không cảm ứng)
- **τ** = **p** × **E**
- **F** = (**p**·∇)**E** = ∇(**p**·**E**) khi ∇×**E** = 0.
  ⇒ **Trong trường đều, F = 0 nhưng τ ≠ 0.** Đây là dấu hiệu nhận dạng: bài nào nói "lưỡng cực trong trường đều" thì chắc chắn là bài **quay / dao động**, không phải bài tịnh tiến.

**Dao động nhỏ.** I θ̈ = −pE sinθ ≈ −pEθ ⇒ ω = √(pE/I). Đây là CHỖ chuyển thẳng sang dao động điều hoà — một cầu nối giữa Thẻ 3 và Thẻ 7.

**Lưỡng cực cảm ứng.** **p** = α**E**. Khi đó U = −½α E² (hệ số ½ vì phải tốn công phân cực), và **F** = ½α∇(E²).
⇒ **Vật trung hoà có α > 0 luôn bị hút về vùng trường mạnh.** Giải thích mẩu giấy bị hút bởi thước nhựa; cũng là nguyên lý bẫy quang học.

**Khai triển đa cực.** V = k[Q/r + **p**·**r̂**/r² + (1/2r³)Σ_{ij} Q_ij r̂_i r̂_j + …]. Quy tắc dùng: số hạng đầu tiên **khác 0** là số hạng chi phối ở xa. Hệ trung hoà không đối xứng ⇒ lưỡng cực chi phối (1/r³). Hệ trung hoà + không lưỡng cực ⇒ tứ cực (1/r⁴).

**CHỖ-detector.** (1) Mọi cụm điện tích nhìn từ xa → tính Q rồi p; (2) mọi vật trung hoà đặt trong trường không đều → lưỡng cực cảm ứng; (3) mọi bài "phân tử phân cực trong điện trường" → U = −pE cosθ → thống kê hoặc dao động; (4) mọi khối điện môi phân cực đều → thay bằng p = PV rồi dùng trường lưỡng cực ở xa.

**Toán hoá.** Phương trình chuyển động quay (ODE bậc 2), hoặc hàm thế U(θ), U(x) → cực trị / chu kỳ / điều kiện cân bằng bền (∂²U > 0).

---

### THẺ 4 — ĐIỆN MÔI

**Bộ khái niệm.** **P** = mômen lưỡng cực trên đơn vị thể tích.
- ρ_b = −∇·**P** ; σ_b = **P**·**n̂** (n̂ hướng ra ngoài khối điện môi)
- **D** = ε₀**E** + **P** ; ∮**D**·d**A** = Q_tự do,trong ; ∇·**D** = ρ_tự do
- Tuyến tính đẳng hướng: **P** = ε₀χ_e**E**, **D** = ε**E**, ε = ε₀ε_r, ε_r = 1 + χ_e

**Pre.** Quan hệ **D** = ε**E** chỉ đúng cho môi trường tuyến tính, đẳng hướng, đồng nhất từng miền. Với tinh thể ⇒ ε là **tensor**. Với trường mạnh ⇒ phi tuyến.

**Suf (điểm tử của mảng này).** Gauss cho **D** giải ra **D** **chỉ khi** *cả phân bố điện tích tự do lẫn hình học của khối điện môi* cùng có một đối xứng truyền dẫn. Lý do: nói chung ∇×**D** = ∇×**P** ≠ 0, nên **D** **không** phải trường thế và Gauss một mình không đủ.
> Ví dụ bẫy: tụ phẳng nhét nửa tấm điện môi *song song với bản*. Ở đây D là như nhau ở hai miền (đối xứng phẳng còn nguyên) ⇒ Gauss-D dùng được. Nhưng nếu nhét nửa tấm *vuông góc với bản* thì **E** mới là đại lượng chung (vì E_t liên tục) ⇒ phải dùng điều kiện biên chứ không phải Gauss-D.

**Điều kiện biên (CHỖ vàng, luôn phải duyệt).** Tại mọi mặt phân cách:
- **E_tiếp tuyến liên tục:** E_1t = E_2t
- **D_pháp tuyến nhảy theo điện tích tự do mặt:** D_2n − D_1n = σ_tự do
- Hệ quả: định luật khúc xạ đường sức tan θ₁/tan θ₂ = ε₁/ε₂

**Hai mô hình tụ có điện môi** (chuyển ngay sang mạch):
- Điện môi xếp **song song với bản** (nhiều lớp theo chiều điện trường) ⇒ các tụ **nối tiếp**, D chung.
- Điện môi xếp **cạnh nhau theo diện tích** ⇒ các tụ **song song**, E chung.

**Kết quả kinh điển phải thuộc.**
- Cầu điện môi ε_r trong trường đều E₀: **E_trong = 3E₀/(ε_r + 2)** (đều). Suy ra từ Laplace + đa thức Legendre bậc 1, dùng E_t và D_n liên tục.
- Khoang cầu rỗng trong điện môi: E_khoang = 3ε_r E₀/(2ε_r + 1).
- Clausius–Mossotti: (ε_r − 1)/(ε_r + 2) = nα/3ε₀ — cầu nối vi mô ↔ vĩ mô, hay hỏi ở IPhO.
- Lực hút điện môi vào tụ: dùng Thẻ 2 với F = +(∂W/∂x)|_V; lực luôn kéo điện môi **vào** vùng trường mạnh.

**CHỖ-detector.** (1) Mọi mặt phân cách → viết 2 điều kiện biên. (2) Mọi khối điện môi phân cực → tính ngay ρ_b và σ_b, rồi **coi chúng như điện tích thật trong chân không** — đây là con đường an toàn nhất khi đối xứng bị phá. (3) Mọi tụ có điện môi → phân rã thành mạng tụ nối tiếp/song song.

**Toán hoá.** Hoặc (a) đại số hoá bằng Gauss-D + điều kiện biên; hoặc (b) **bài toán biên Laplace** ∇²V = 0 ở mỗi miền, khai triển theo hàm điều hoà (Legendre cho cầu, lượng giác/log cho trụ), khớp hệ số ở biên → hệ phương trình tuyến tính cho các hệ số.

---

### THẺ 5 — VẬT DẪN

**Năm tính chất (mỗi tính chất là một CHỖ sinh phương trình).**
1. **E** = 0 ở mọi điểm trong lòng vật dẫn cân bằng.
2. Toàn vật dẫn là **một mặt đẳng thế**: V = const.
3. ρ = 0 trong lòng; mọi điện tích dư nằm trên **mặt**.
4. Ngay sát mặt ngoài: **E** = (σ/ε₀)**n̂**, vuông góc mặt.
5. **Khoang rỗng:** nếu khoang không chứa điện tích ⇒ E = 0 trong khoang (chắn tĩnh điện). Nếu chứa q ⇒ mặt trong khoang mang −q, mặt ngoài mang +q (nếu cô lập).

**Định lí duy nhất (Pre của mọi mẹo).** Nghiệm của ∇²V = ρ/ε₀ trong miền Ω là **duy nhất** khi biết V trên toàn biên ∂Ω (Dirichlet), hoặc duy nhất sai khác hằng số khi biết ∂V/∂n (Neumann).
⇒ **Hệ quả vận hành:** bất kỳ hàm V nào thoả phương trình và khớp mọi điều kiện biên đều là *nghiệm đúng*, bất kể ta **đoán** ra nó bằng cách nào. Đây chính là giấy phép hợp pháp cho phương pháp ảnh điện.

**Ảnh điện (method of images).**
| Cấu hình | Ảnh | Ghi chú |
|---|---|---|
| q cách mặt phẳng nối đất d | −q tại điểm đối xứng | σ(r) = −qd/[2π(r²+d²)^{3/2}]; F = −kq²/(2d)²; W = −kq²/4d (chú ý **không** phải −kq²/2d) |
| q cách tâm cầu nối đất R một đoạn a > R | q′ = −qR/a tại b = R²/a | Cầu cô lập trung hoà: thêm +qR/a tại tâm |
| q giữa hai mặt phẳng song song | chuỗi ảnh vô hạn | thành chuỗi số |

**Pre của ảnh điện:** hình học phải cho phép một tập điện tích ảnh **đặt ngoài miền quan tâm** tái tạo đúng điều kiện biên. Nếu không, chuyển sang khai triển Laplace.

**Ma trận điện dung.** Q_i = Σ_j C_ij V_j, với C_ij = C_ji (đối xứng). Hệ n vật dẫn ⇒ hệ tuyến tính n×n — đây là "Nodal Analysis của tĩnh điện".

**Định lí tương hỗ Green (vũ khí bị bỏ quên).** Với hai cấu hình điện tích/thế trên cùng bộ vật dẫn:
> Σ_i q_i V′_i = Σ_i q′_i V_i

Ứng dụng: tính **điện tích cảm ứng** trên một vật dẫn nối đất hình dạng *bất kỳ* do q đặt ở vị trí bất kỳ, mà **không cần** giải trường. Đây là lời giải một dòng cho những bài mà cách trực tiếp tốn 3 trang. Rất đáng thuộc cho HSGQG.

**CHỖ-detector.** (1) Mỗi mặt vật dẫn → một phương trình σ = ε₀E_n. (2) Mỗi vật dẫn → một phương trình V = const. (3) Mỗi vật dẫn cô lập → bảo toàn điện tích tổng. (4) Mỗi vật dẫn nối đất → V = 0. (5) Mỗi khoang → áp Gauss với mặt nằm trọn trong kim loại (thông lượng = 0 ⇒ điện tích trong bằng 0). Đếm số ẩn = số phương trình: đây là kiểm tra **tính đóng kín** (điều kiện 3 trong khung M).

**Toán hoá.** Hệ phương trình tuyến tính theo các σ_i / Q_i / V_i; hoặc bài toán biên Laplace; hoặc — nhờ ảnh điện — một biểu thức đại số tường minh.

---

### THẺ 6 — MẠCH 1 CHIỀU, PHI TUYẾN

#### 6A. Phần tuyến tính — biến mạch thành đại số tuyến tính

**Nodal Analysis (thuật toán, gần như không cần trực giác).**
1. Chọn nút gốc (thường nút nhiều nhánh nhất hoặc cực âm nguồn), đặt V = 0.
2. Gán ẩn φ₁…φ_{n−1} cho các nút còn lại.
3. Với mỗi nút: Σ (φ_k − φ_j)/R_jk = Σ I_nguồn vào nút. (Nguồn áp lý tưởng giữa hai nút ⇒ dùng supernode.)
4. Giải hệ n−1 ẩn. Ma trận hệ số là ma trận Laplace của đồ thị mạch: **đường chéo = tổng điện dẫn tại nút, ngoài đường chéo = −điện dẫn nhánh**. Nắm "pattern" này thì viết hệ trong 30 giây.
5. Dòng nhánh: I_jk = (φ_j − φ_k)/R_jk.

**Các CHỖ tăng tốc cần duyệt trước khi bổ Nodal:**
- **Đối xứng:** hai nút cùng thế ⇒ **chập lại** (hoặc bỏ nhánh nối giữa chúng, vì I = 0). Lập phương diện: tìm phép hoán vị đồ thị giữ nguyên nguồn.
- **Tự đồng dạng (thang vô hạn):** R_∞ = f(R_∞) ⇒ phương trình bậc hai. Pre: mạch thực sự vô hạn và f là ánh xạ co.
- **Thévenin/Norton:** khi chỉ quan tâm **một** nhánh (đặc biệt khi nhánh đó **phi tuyến**) ⇒ thu gọn phần còn lại thành (E_th, R_th). Đây là cầu nối bắt buộc sang phần 6B.
- **Y–Δ:** khi mạch cầu không cân bằng và không có đối xứng.
- **Chồng chất:** chỉ khi mọi phần tử tuyến tính.

#### 6B. Phần phi tuyến — ba phương pháp, ba tình huống

**(i) Phương pháp đường tải (load line).** Tình huống: một phần tử phi tuyến đặc trưng bởi I = f(U) (cho bằng đồ thị hoặc công thức), phần còn lại tuyến tính.
- Bước 1: Thévenin hoá phần tuyến tính → E_th, R_th.
- Bước 2: KVL cho ra **đường tải** I = (E_th − U)/R_th — một đường thẳng.
- Bước 3: Điểm làm việc = **giao điểm** của đường tải với đặc tuyến I = f(U).
- **Toán hoá:** f(U) = (E_th − U)/R_th — một **phương trình siêu việt** một ẩn. Giải bằng đồ thị (nếu đề cho đồ thị), bằng đại số (nếu f là đa thức: ví dụ đèn I = kU² → phương trình bậc hai), hoặc lặp Newton.
- **Pre:** phần tử phi tuyến chỉ có **một** cổng; đặc tuyến đơn trị.

**(ii) Liệt kê trạng thái (điốt lý tưởng).** Điốt lý tưởng = phần tử hai trạng thái:
- **Dẫn (ON):** U = 0 (hoặc U = U_γ), ràng buộc I ≥ 0
- **Khoá (OFF):** I = 0, ràng buộc U ≤ 0 (hoặc ≤ U_γ)

**Thuật toán (hoàn toàn máy móc):** với n điốt, duyệt tối đa 2ⁿ tổ hợp trạng thái. Với mỗi tổ hợp: thay điốt bằng dây nối / hở mạch, giải mạch **tuyến tính**, rồi **kiểm tra ràng buộc bất đẳng thức**. Tổ hợp nào thoả toàn bộ chính là nghiệm (và nó là duy nhất với mạch điện trở dương). Thực tế chỉ cần thử 1–2 tổ hợp nếu đoán khéo, nhưng **phải kiểm tra** — đây là bước học sinh hay bỏ.

**(iii) Nhiễu nhỏ quanh điểm làm việc.** Điện trở vi phân r_d = dU/dI tại điểm làm việc. Với tín hiệu nhỏ, thay phần tử phi tuyến bằng điện trở r_d ⇒ mạch trở lại tuyến tính.
- **Điều kiện ổn định của điểm làm việc:** R_th + r_d > 0. Nếu r_d < 0 (đèn phóng điện, điốt tunnel, hồ quang) và R_th + r_d < 0 ⇒ điểm làm việc **không ổn định** ⇒ mạch nhảy trạng thái / tự dao động. Đây là mạch ra đề ở tầm IPhO.

**CHỖ-detector cho toàn Thẻ 6.**
1. Đếm nút, đếm vòng độc lập (E − N + 1) → chọn Nodal hay Mesh theo số ẩn nhỏ hơn.
2. Quét tìm đối xứng và nút đẳng thế **trước tiên**.
3. Khoanh vùng mọi phần tử phi tuyến → Thévenin hoá phần còn lại nhìn từ nó.
4. Mỗi điốt → một biến trạng thái nhị phân.
5. Mỗi câu hỏi "công suất cực đại / hiệu suất" → đạo hàm P(R) hoặc dùng bất đẳng thức AM–GM (P_max khi R = R_th; nhưng hiệu suất khi đó chỉ 50% — phân biệt hai câu hỏi này).

---

### THẺ 7 — DAO ĐỘNG ĐIỆN TỪ, ĐIỐT

**Nền tảng tuyến tính.**
- LC: L q̈ + q/C = 0 ⇒ ω₀ = 1/√(LC), T = 2π√(LC).
- Bảo toàn: q²/2C + Li²/2 = const. Biên độ: I₀ = Q₀ω₀ = Q₀/√(LC) = U₀√(C/L).
- RLC: L q̈ + R q̇ + q/C = 0. Tắt dần khi R < 2√(L/C); tới hạn R = 2√(L/C).
- **Đại lượng trở kháng đặc trưng** ρ = √(L/C) — dùng để liên hệ nhanh U và I: U = ρI ở các bài chuyển trạng thái.

**Bộ khung cho mạch có điốt — "ODE tuyến tính từng khúc":** đây là ô Suf của cả mảng.

Điốt **không** làm bài toán phi tuyến theo nghĩa khó; nó **chia trục thời gian thành các khoảng**, trên mỗi khoảng mạch là tuyến tính. Quy trình máy móc:

1. **Xác định trạng thái ban đầu** của mỗi điốt (dựa vào dấu điện áp/dòng lúc t = 0).
2. **Giải mạch tuyến tính tương ứng** trên khoảng đó (LC, RLC, hoặc thuần RC/RL).
3. **Tìm thời điểm chuyển trạng thái** bằng điều kiện: điốt đang dẫn tắt khi i giảm về **0**; điốt đang khoá mở khi u đạt **U_γ** (hoặc 0). Đây là CHỖ sinh ra phương trình xác định thời điểm.
4. **Áp điều kiện nối (matching conditions)** tại thời điểm chuyển — **bất biến vật lý bắt buộc:**
   - **i_L liên tục** (vì L di/dt không được vô hạn)
   - **u_C liên tục** (vì C du/dt không được vô hạn)
   Hai điều kiện này là "điều kiện đầu" cho khoảng kế tiếp.
5. **Lặp** và tìm **quy luật hồi quy**: biểu diễn trạng thái đầu khoảng thứ (n+1) theo trạng thái đầu khoảng thứ n. Thu được một **ánh xạ / dãy số** (thường là cấp số nhân hoặc cấp số cộng).

**Post / Toán hoá.** Bài trở thành: (a) một ODE tuyến tính bậc 2 hệ số hằng trên mỗi khoảng; (b) một phương trình lượng giác xác định thời điểm chuyển; (c) một **dãy truy hồi** U_{n+1} = f(U_n) → tính tổng, tìm giới hạn, tính số chu kỳ đến khi dừng. Câu hỏi "sau bao lâu thì dao động dừng hẳn" ⇒ giải bất phương trình trên dãy.

**Mẹo giảm tải:** khi điốt **lý tưởng** (không sụt áp, không tiêu tán), **bảo toàn năng lượng** thường thay thế được toàn bộ việc giải ODE. Ví dụ: điốt chỉ cho dòng chạy một chiều ⇒ dao động bị "cắt nửa" ⇒ dùng năng lượng để tìm biên độ ở nửa chu kỳ tiếp theo mà không cần biểu thức q(t). **Pre:** điốt lý tưởng và không có R. Nếu điốt có U_γ ⇒ mỗi lần dẫn tiêu tốn ΔW = U_γ·Δq — đây là một CHỖ sinh phương trình năng lượng rất hay được hỏi.

**Ba cấu hình phải thuộc.**
- **Chỉnh lưu nửa chu kỳ trên LC:** dao động chạy nửa chu kỳ rồi bị khoá lại, tụ giữ nguyên điện tích vô hạn định ⇒ câu hỏi "điện áp cuối cùng trên tụ".
- **Mạch ghim áp (clamping) C–điốt:** tụ nạp đến giá trị đỉnh rồi giữ; nhân đôi điện áp (Villard).
- **Chuyển năng lượng giữa hai tụ qua cuộn cảm + điốt:** điốt ngăn dòng chảy ngược ⇒ năng lượng kẹt lại ở tụ thứ hai; dùng i_L liên tục + bảo toàn năng lượng.

**Err.** Bỏ qua điện trở dây ⇒ mô hình "dao động mãi mãi"; trong thực tế Q hữu hạn. Nếu bài cho R nhỏ, dùng xấp xỉ suy giảm biên độ theo e^{−Rt/2L} và **chỉ** tính năng lượng mất bằng ∫I²R dt.

---

## PHẦN C — QUY TRÌNH DUYỆT TỔNG (Search Routine)

Khi nhận một bài Điện từ nâng cao, chạy đúng trình tự sau. Đây là phiên bản "brute-force có tổ chức" mà README yêu cầu — duyệt từng "pixel".

**Bước 0 — Dựng ontology O.** Liệt kê bằng chữ: có bao nhiêu vật thể? mỗi vật là vật dẫn / điện môi / điện tích cho trước? Có nối đất không? Có nguồn không? Biến thiên theo t không?

**Bước 1 — Phân loại theo 3 trục** (Phần 0). Kết quả: chọn được nhóm công cụ (Thẻ nào).

**Bước 2 — Đếm ẩn và đếm phương trình.** Viết ra danh sách V (ẩn). Nếu số phương trình sẽ sinh < số ẩn ⇒ mô hình **chưa đóng kín** ⇒ còn CHỖ chưa duyệt. Đây là chỉ báo định lượng cho biết khi nào được dừng tìm kiếm.

**Bước 3 — Duyệt CHỖ theo danh mục cố định:**
- Mọi **mặt kín** bất biến dưới đối xứng → Gauss
- Mọi **mặt phân cách** → điều kiện biên (E_t, D_n, hộp Gauss)
- Mọi **mặt vật dẫn** → σ = ε₀E_n, V = const
- Mọi **vật cô lập** → bảo toàn điện tích
- Mọi **cặp điện tích / miền có E** → năng lượng
- Mọi **tham số hình học biến thiên** → F = ∓∂W/∂x
- Mọi **nút mạch** → KCL; mọi **vòng** → KVL
- Mọi **phần tử phi tuyến** → Thévenin + đường tải
- Mọi **điốt** → biến trạng thái nhị phân + điều kiện chuyển
- Mọi **thời điểm chuyển trạng thái** → i_L, u_C liên tục

**Bước 4 — Kiểm tra Pre của từng công cụ đã chọn.** Đặc biệt: đối xứng có bị phá bởi điện tích cảm ứng không? r ≫ d có thoả không? môi trường có tuyến tính không?

**Bước 5 — Kiểm tra tính nhất quán & biên.** Cho tham số → 0 và → ∞, so với trường hợp đã biết. Kiểm tra thứ nguyên. Kiểm tra dấu bằng lập luận vật lý (lực hút hay đẩy?).

**Bước 6 — Giao cho Vấn đề 3.**

---

## PHẦN D — BẢNG TRA "DẤU HIỆU ĐỀ BÀI → CÔNG CỤ"

| Dấu hiệu trong đề | Công cụ gần như chắc chắn |
|---|---|
| "quả cầu / trụ dài vô hạn / mặt phẳng rộng vô hạn", ρ cho trước | Gauss (Thẻ 1) |
| "khoang lệch tâm", "lỗ hổng hình cầu/trụ" | Chồng chất hai khối đối xứng → trường đều |
| "công cần thiết để...", "năng lượng dự trữ" | Thẻ 2, chú ý tự năng |
| "kéo tấm điện môi ra", "tách hai bản tụ" | W(x) rồi F = ∓∂W/∂x; xác định Q hay V không đổi |
| "nhìn từ rất xa", "phân tử trung hoà" | Khai triển đa cực / lưỡng cực (Thẻ 3) |
| "trường không đều hút vật trung hoà" | p = αE, F = ½α∇(E²) |
| "hằng số điện môi ε_r", "chất cách điện lấp đầy" | Gauss-D nếu đối xứng, nếu không → ρ_b, σ_b |
| "nối đất", "điện tích cảm ứng", "điện tích điểm gần mặt phẳng/cầu" | Ảnh điện + định lí duy nhất (Thẻ 5) |
| "tính điện tích cảm ứng trên vật dẫn hình dạng bất kỳ" | Định lí tương hỗ Green |
| "đèn có đặc tuyến I–U cho bởi đồ thị" | Thévenin + đường tải (Thẻ 6B) |
| "điốt lý tưởng" trong mạch một chiều | Liệt kê 2ⁿ trạng thái + kiểm tra bất đẳng thức |
| "điốt" + "L, C" | ODE từng khúc + i_L, u_C liên tục + truy hồi (Thẻ 7) |
| "sau bao nhiêu chu kỳ thì dừng" | Dãy truy hồi + bất phương trình |

---

## PHẦN E — DANH SÁCH BẪY (kiểm tra trước khi nộp)

1. Dùng Gauss để **giải** E ở cấu hình bất đối xứng (Pre ≠ Suf).
2. Quên điện tích cảm ứng/liên kết khi xét đối xứng.
3. Dùng (ε₀/2)∫E² cho điện tích **điểm** (phân kỳ).
4. Nhầm W tương tác với W toàn phần (có tự năng).
5. Sai dấu F = −∂W/∂x khi mạch đang **nối nguồn**.
6. Quên hệ số ½ trong áp suất σ²/2ε₀ và trong U = −½αE².
7. Dùng **p** khi Q_tổng ≠ 0 mà không nói rõ gốc toạ độ.
8. Tính W của điện tích trước mặt phẳng nối đất bằng −kq²/2d (đúng là **−kq²/4d**), do ảnh không phải điện tích thật nên không được nhân đôi công.
9. Dùng ảnh điện để tính trường **bên trong** vùng chứa điện tích ảnh (vô hiệu).
10. Áp **D** = ε**E** xuyên qua mặt phân cách (ε khác nhau hai bên).
11. Giải mạch điốt mà **không kiểm tra** bất đẳng thức của trạng thái giả định.
12. Áp dụng công thức công suất cực đại R = R_th khi nguồn có R_trong cố định nhưng câu hỏi thực ra hỏi **hiệu suất**.
13. Quên điều kiện i_L liên tục / u_C liên tục tại thời điểm điốt đổi trạng thái — lỗi phổ biến nhất của Thẻ 7.
14. Dùng bảo toàn năng lượng ở mạch có điốt **có sụt áp U_γ** mà quên trừ U_γ·Δq.

---

## PHẦN F — NHỮNG CHỖ CHƯA ĐẦY ĐỦ (trung thực về giới hạn)

Tài liệu này là **bản khung mật độ cao**, chưa phải bản đầy đủ. Những phần còn nợ, xếp theo mức độ cần bổ sung:

- Thẻ 4 & 5: lời giải chi tiết bài toán biên Laplace (khai triển Legendre, hàm Green, phương pháp tách biến trong toạ độ trụ/cầu) — mới nêu kết quả, chưa dẫn xuất.
- Thẻ 5: lý thuyết ma trận điện dung/hệ số thế đầy đủ, và các hệ quả của định lí tương hỗ.
- Thẻ 6: phân tích mạch có phần tử phi tuyến **nhiều cổng**, và mạch có nhiều phần tử phi tuyến đồng thời (bài toán điểm bất động đa chiều).
- Thẻ 7: mạch có điốt **và** nguồn xoay chiều; phân tích Fourier của dạng sóng đã chỉnh lưu.
- Chưa bao gồm: từ trường, cảm ứng điện từ, mạch xoay chiều — theo đúng yêu cầu chỉ xử lý 7 mục trong ảnh.
