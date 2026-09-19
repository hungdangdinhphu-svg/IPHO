# CƠ HỌC VẬT RẮN — CƠ HỌC LÍ THUYẾT — CƠ HỌC CHẤT LƯU
### Thư viện CÔNG CỤ & PRECONDITION: giải pháp cho Vấn đề 1 và Vấn đề 2
*Phạm vi: đúng 3 mục trong ảnh. Đối tượng: HSGQG / VPhO / IPhO và nền tảng nghiên cứu.*

---

## PHẦN 0 — KHUNG VẬN HÀNH & TRỤC PHÂN LOẠI

Mỗi công cụ ℓ đóng gói thành thẻ: **Dom / Pre / Suf / Post / Err / CHỖ-detector / Toán hoá**. Nhắc lại phân biệt sống còn: **Pre** = điều kiện để công cụ *đúng*; **Suf** = điều kiện để công cụ *giải ra được ẩn*.

**Đặc thù của Cơ học (khác Điện từ và Quang học):** ở hai mảng kia, khó khăn nằm ở chỗ *tìm nơi áp dụng*. Ở Cơ học, khó khăn nằm ở hai chỗ khác:

1. **Chọn toạ độ và hệ quy chiếu.** Cùng một bài, chọn đúng thì ràng buộc biến thành "một toạ độ = const" và bài tan ra; chọn sai thì sa lầy vô hạn. Đây là nơi Cơ học đòi trực giác nhiều nhất — và cũng là nơi có thuật toán thay thế tốt nhất (Thẻ 7, 8).
2. **Kiểm tra Pre của các định lý mômen.** Công thức dL/dt = M có một tập Pre hẹp mà sách phổ thông hầu như không nêu; đây là nguồn sai lầm nghiêm trọng nhất của toàn mảng (Thẻ 5).

**Bốn trục định vị mọi bài cơ học:**

| Trục | Câu hỏi | Rẽ nhánh |
|---|---|---|
| **Tĩnh / Động** | Có gia tốc không? | Tĩnh ⇒ Thẻ 2 (+ công ảo). Động ⇒ Thẻ 5, 8 |
| **Bậc tự do** | Đếm n = (số toạ độ) − (số ràng buộc) | n = 1 ⇒ năng lượng là đủ. n ≥ 2 ⇒ nên Lagrange |
| **Ràng buộc** | Holonomic (viết được f(q,t)=0) hay không? | Holonomic ⇒ Lagrange chuẩn. Non-holonomic ⇒ phải dùng Newton–Euler hoặc nhân tử |
| **Hệ quy chiếu** | Ràng buộc có đơn giản hơn trong một HQC chuyển động không? | Có ⇒ chuyển HQC + thêm lực quán tính (Thẻ 6) |

**Nguyên tắc chuyển hoá trung tâm của Vấn đề 2 trong Cơ học:**
> Bài cơ học trở thành bài toán ngay khi ta viết xong **hàm Lagrange L(q, q̇, t)** hoặc **hàm năng lượng E(q, q̇)**. Mọi việc trước đó là mô hình hoá; mọi việc sau đó là giải ODE. Vì vậy con đường ít trực giác nhất luôn là: *đếm bậc tự do → chọn toạ độ suy rộng → biểu diễn mọi vận tốc theo q̇ → viết T và U*.

---

# PHẦN I — CƠ HỌC VẬT RẮN

---

## A. TĨNH HỌC VẬT RẮN

### THẺ 1 — TRỌNG TÂM / KHỐI TÂM

**Định nghĩa.** **R**_G = (1/M)Σm_i**r**_i = (1/M)∫**r** dm.
*Phân biệt:* **khối tâm** là khái niệm động lực học; **trọng tâm** là điểm đặt hợp lực trọng trường. Chúng trùng nhau **khi và chỉ khi g đồng nhất** — với vật kích thước rất lớn (vệ tinh dài, thanh trong trường hấp dẫn không đều) chúng lệch nhau, sinh ra **mômen thuỷ triều** (gravity-gradient torque). Đây là Pre hiếm khi được nêu nhưng có ra ở IPhO.

**Ba tính chất biến bài tích phân thành bài số học:**
1. **Tính cộng theo mảnh:** chia vật thành các phần có khối tâm đã biết, rồi lấy trung bình có trọng số.
2. **Khối lượng âm:** vật có lỗ = vật đặc + "lỗ mang khối lượng âm". Biến bài lỗ khuyết thành hai số hạng.
3. **Đối xứng:** khối tâm nằm trên mọi mặt phẳng / trục / tâm đối xứng. Mỗi đối xứng khử một toạ độ ⇒ luôn khai thác trước khi tích phân.

**Bảng cần thuộc:** tam giác (giao trung tuyến, cách đáy h/3) · cung tròn bán kính R nửa góc α: R·sinα/α · hình quạt: (2R/3)·sinα/α · nửa đĩa 4R/3π · bán cầu **đặc** 3R/8 · bán cầu **rỗng** R/2 · khối nón/chóp: h/4 tính từ đáy · mặt nón rỗng: h/3 từ đáy.

**Định lý Pappus–Guldinus (mẹo ngược cực hay):** V = 2π·R_G·A và S = 2π·R_G·L với vật tròn xoay. Dùng **ngược**: biết V thì suy ra R_G mà không cần tích phân.

**Toán hoá.** Tổng có trọng số hoặc tích phân một chiều (sau khi dùng đối xứng).

---

### THẺ 2 — HỆ LỰC & ĐIỀU KIỆN CÂN BẰNG

**Ontology đúng (chỗ khác biệt giữa chất điểm và vật rắn):** lực tác dụng lên vật rắn là **vector trượt** — dời được dọc theo giá của nó mà không đổi tác dụng, nhưng **không** dời song song được.

**Định lý giản lược.** Mọi hệ lực đều tương đương với một lực **F** = Σ**F**_i đặt tại điểm O tuỳ chọn, cộng một ngẫu lực **M**_O = Σ**r**_i × **F**_i. Khi đổi điểm:
> **M**_{O′} = **M**_O + **O′O** × **F**

**Hệ quả 1 (rất dùng):** nếu **F** = 0 thì **M** **không phụ thuộc điểm lấy mômen** ⇒ ngẫu lực thuần.
**Hệ quả 2 (bất biến):** tích **F**·**M**_O không đổi khi đổi điểm ⇒ tổng quát nhất, mọi hệ lực rút gọn về một **vít động lực** (lực + ngẫu lực song song) trên một trục trung tâm. Hệ lực đồng phẳng hoặc đồng quy thì bất biến này bằng 0 ⇒ rút gọn được về **một lực duy nhất**.

**Điều kiện cân bằng.** Σ**F** = 0 **và** Σ**M**_O = 0 với **một** điểm O bất kỳ.
- Bài phẳng: 3 phương trình độc lập. Bài không gian: 6.
- Biến thể tương đương: 3 phương trình mômen với 3 điểm **không thẳng hàng** (phẳng). Rất hữu ích khi muốn tránh hẳn việc chiếu lực.

**Suf — thuật toán chọn điểm lấy mômen (đây là "CHỖ" then chốt của tĩnh học):**
> Chọn điểm nằm trên **giao của nhiều giá lực chưa biết nhất**. Mỗi lực đi qua điểm đó biến mất khỏi phương trình.

Quy trình máy móc: liệt kê mọi ẩn (phản lực, lực căng) → với mỗi cặp/bộ ẩn, tìm giao điểm giá của chúng → lấy mômen tại đó → mỗi phương trình chỉ còn 1 ẩn. Đây là cách giải bài tĩnh học **không cần trực giác**, thay cho việc mò mẫm chiếu lực.

**Tĩnh định và siêu tĩnh — bước kiểm tra bắt buộc:**
> Đếm ẩn. Nếu (số ẩn) > (số phương trình cân bằng), bài **siêu tĩnh** ⇒ **không giải được bằng tĩnh học thuần**, bắt buộc phải thêm điều kiện biến dạng (định luật Hooke, điều kiện tương thích) hoặc một giả thiết bổ sung của đề.

Ví dụ kinh điển: thanh đặt trên ba chân, hoặc thang tựa tường có ma sát ở **cả hai** đầu — đều siêu tĩnh. Nhận ra điều này sớm tiết kiệm rất nhiều thời gian và là dấu hiệu của người hiểu bản chất.

**Ma sát — đặc thù bất đẳng thức.**
- f ≤ μN là **bất đẳng thức**, không phải phương trình. Chỉ khi **đang trượt** mới có f = μN với chiều xác định.
- **Nón ma sát:** phản lực toàn phần nằm trong nón nửa góc φ = arctan μ. Bài "vật có tự hãm không" = hỏi giá của lực có nằm trong nón không ⇒ điều kiện hình học thuần tuý.
- **Trượt hay lật:** tính hai ngưỡng riêng biệt (ngưỡng trượt từ f = μN, ngưỡng lật từ điều kiện điểm đặt phản lực chạm mép chân đế), rồi so sánh. Bỏ sót một trong hai là lỗi phổ biến.

**Nguyên lý công ảo (công cụ hạng nặng của tĩnh học):**
> Hệ ở cân bằng ⟺ δW = Σ**F**_i·δ**r**_i = 0 với mọi dịch chuyển ảo tương thích ràng buộc.

**Ưu điểm quyết định:** **phản lực liên kết lý tưởng tự động biến mất** (chúng vuông góc với dịch chuyển ảo). Với hệ cơ cấu nhiều khâu (đòn bẩy phức hợp, kích vít, hệ ròng rọc lồng nhau), đây là khác biệt giữa 10 phương trình và 1 phương trình. Đây là "Nodal Analysis của tĩnh học".

**Cân bằng bền / không bền.**
- 1 bậc tự do: viết U(q); cân bằng tại U′(q₀)=0; **bền ⟺ U″(q₀) > 0**.
- Nhiều bậc tự do: ma trận Hessian ∂²U/∂q_i∂q_j **xác định dương**.
- Trường hợp suy biến U″ = 0 ⇒ phải xét bậc cao hơn.
- Tần số dao động nhỏ quanh cân bằng bền: ω² = U″(q₀)/m_eff — nối thẳng sang Thẻ 5.
- **Tiêu chí hình học tương đương:** vật nổi/tựa ở cân bằng bền khi khối tâm **hạ xuống** khi bị lệch. Dùng cho vật lăn trên mặt cong: bền khi R_mặt > ... (so sánh bán kính cong với độ cao khối tâm).

**Dây xích treo (catenary) — mẫu bài hay gặp.** Cân bằng một đoạn dây vi phân:
> T cosθ = H = const (thành phần ngang không đổi) và d(T sinθ)/dx = λ g (ds/dx)

⇒ y″ = (λg/H)√(1+y′²) ⇒ **y = (H/λg)·cosh(λg x/H)**. Nếu tải phân bố đều theo **phương ngang** (cầu treo) thì đổi thành **parabol**. Phân biệt hai trường hợp này là một CHỖ ra đề.

**CHỖ-detector cho tĩnh học.** (1) Tách vật: vẽ sơ đồ vật tự do cho **từng** vật và cho **từng nhóm** vật — mỗi cách tách là một bộ phương trình, chọn bộ nào khử được nhiều ẩn nhất. (2) Mỗi liên kết → loại phản lực tương ứng (bản lề: 2 ẩn phẳng; gối: 1 ẩn; ngàm: 3 ẩn). (3) Mỗi giao điểm giá lực → một ứng viên điểm lấy mômen. (4) Mỗi đoạn dây/thanh vi phân → phương trình vi phân cân bằng.

**Toán hoá.** Hệ phương trình tuyến tính (tĩnh định); hệ + bất phương trình (có ma sát); ODE (dây, thanh biến dạng); bài cực trị (U″).

---

## B. ĐỘNG HỌC & ĐỘNG LỰC HỌC VẬT RẮN

### THẺ 3 — ĐỘNG HỌC VẬT RẮN

**Bậc tự do.** Vật rắn tự do: 6 (3 tịnh tiến + 3 quay). Chuyển động phẳng: 3 (x_G, y_G, φ).

**Công thức trung tâm của toàn bộ động học vật rắn:**
> **v**_B = **v**_A + **ω** × **r**_{AB}
> **a**_B = **a**_A + **α** × **r**_{AB} + **ω** × (**ω** × **r**_{AB})

Trong chuyển động phẳng, số hạng cuối rút gọn thành −ω²**r**_{AB} (hướng vào A).

**Hệ quả 1 — bất biến thanh cứng (dùng rất nhiều):**
> Hình chiếu vận tốc hai điểm bất kỳ lên **đường nối chúng** là bằng nhau: **v**_A·ê_{AB} = **v**_B·ê_{AB}.

Đây là một phương trình vô hướng "miễn phí" cho mọi cặp điểm trên mọi vật rắn, cho mọi thanh, và là cách nhanh nhất để liên hệ vận tốc hai đầu thanh mà không cần biết ω.

**Hệ quả 2 — Tâm quay tức thời (ICR). Đây là CHỖ vàng của động học phẳng.**
> Với chuyển động phẳng bất kỳ (trừ tịnh tiến thuần), tồn tại một điểm I có **v**_I = 0 tại thời điểm đó. Khi ấy mọi điểm quay thuần quanh I: v_P = ω·IP, và **v**_P ⊥ IP.

**Cách tìm I (máy móc):** giao của hai đường thẳng vuông góc với **v**_A tại A và vuông góc với **v**_B tại B. Nếu **v**_A ∥ **v**_B thì dùng phép chia tỉ lệ (tam giác đồng dạng).

Giá trị: biến một chuyển động "vừa tịnh tiến vừa quay" thành **quay thuần** ⇒ mọi quan hệ vận tốc thành tỉ lệ hình học đơn giản.

> **Bẫy nghiêm trọng:** ICR chỉ có **v** = 0, **không** có **a** = 0. Với bánh xe lăn không trượt, điểm tiếp xúc có v = 0 nhưng a = ω²R hướng vào tâm. Dùng ICR cho gia tốc là sai.

**Ràng buộc — thư viện hữu hạn và nhỏ (đây chính là "tập A" của động học):**

| Ràng buộc | Phương trình sinh ra |
|---|---|
| Lăn không trượt trên mặt cố định | v_tiếp xúc = 0 ⇒ v_G = ωR ; a_G = αR |
| Lăn không trượt trên mặt chuyển động | v hai điểm tiếp xúc bằng nhau |
| Dây không giãn | hình chiếu vận tốc hai đầu lên dây bằng nhau |
| Dây quấn quanh trụ | v_dây = ω·R (điểm nhả dây) |
| Hai vật tiếp xúc không xuyên qua | thành phần **pháp tuyến** của vận tốc bằng nhau |
| Hai vật tiếp xúc không trượt | thành phần **tiếp tuyến** cũng bằng nhau |
| Thanh tựa vào tường và sàn | toạ độ hai đầu thoả x² + y² = L², đạo hàm ra quan hệ vận tốc |

**Quỹ đạo:** điểm trên vành bánh lăn vẽ **cycloid**: x = R(φ − sinφ), y = R(1 − cosφ). Tốc độ điểm cao nhất = 2v_G; tại điểm tiếp xúc tốc độ = 0.

**Toán hoá.** Hệ phương trình vector; chiếu lên hệ trục thích hợp ⇒ hệ đại số tuyến tính theo (v_G, ω) hoặc (a_G, α). Hoặc: viết ràng buộc dưới dạng f(x,φ)=0 rồi **đạo hàm theo thời gian** — đây là thao tác cơ học nhất để sinh quan hệ vận tốc, thay cho việc "nhìn hình mà đoán".

---

### THẺ 4 — MÔMEN QUÁN TÍNH & TENSOR QUÁN TÍNH

**Định nghĩa.** I = Σm_i d_i² = ∫ d² dm (d = khoảng cách tới **trục**).

**Hai định lý sinh ra mọi kết quả:**
- **Trục song song (Huygens–Steiner):** I = I_G + Md². *Pre: trục phải song song với trục qua khối tâm, và I_G là mômen với trục qua **khối tâm**.*
- **Trục vuông góc:** I_z = I_x + I_y. *Pre: chỉ đúng cho **vật phẳng** (bản mỏng), với z ⊥ mặt phẳng vật.*

**Bảng bắt buộc thuộc (dạng kMR²):** thanh quanh trung điểm ML²/12 · thanh quanh đầu ML²/3 · vành/trụ rỗng MR² · đĩa/trụ đặc MR²/2 · cầu đặc 2MR²/5 · vỏ cầu 2MR²/3 · tấm chữ nhật M(a²+b²)/12 · đĩa quanh đường kính MR²/4.

**Mẹo tính nhanh bằng lập luận thứ nguyên và đồng dạng:** với vật đồng chất, I = k·MR² với k **không thứ nguyên** phụ thuộc duy nhất vào *hình dạng*. Do đó: (a) chia vật thành các phần đồng dạng để lập phương trình tự quy chiếu cho k; (b) với vật ghép, cộng I (kèm Steiner); (c) với vật khuyết lỗ, trừ I của lỗ (cũng kèm Steiner). Ba thao tác này thay thế hầu hết các tích phân trong đề thi.

**Tensor quán tính (mức IPhO).** **L** = 𝐈**ω** với 𝐈 là ma trận 3×3, I_ij = ∫(r²δ_ij − x_ix_j)dm.

> **Pre bị bỏ qua nhiều nhất trong toàn tài liệu:** công thức **L = Iω** (vô hướng) **chỉ đúng khi ω nằm dọc một trục quán tính chính**. Nói chung **L** **không cùng phương** với **ω**.

Hệ quả bắt buộc biết:
- Trục đối xứng của vật luôn là trục quán tính chính.
- Nếu ω không dọc trục chính, **L** quay quanh ω ⇒ cần một **mômen lực** để duy trì quay đều ⇒ **phản lực động lực học lên ổ trục** (rung của bánh xe mất cân bằng).
- Vật quay tự do quanh trục có I trung gian thì **không ổn định** (định lý vợt tennis / hiệu ứng Dzhanibekov).
- Phương trình Euler: I₁ω̇₁ − (I₂−I₃)ω₂ω₃ = M₁ (và hoán vị vòng).

**CHỖ-detector.** Mỗi mảnh ghép → một số hạng I (nhớ Steiner nếu trục không qua khối tâm mảnh). Mỗi lỗ → số hạng âm. Mỗi vật phẳng → dùng được trục vuông góc. Mỗi trục quay được hỏi → kiểm tra xem nó có phải trục chính không trước khi viết L = Iω.

---

### THẺ 5 — ĐỘNG LỰC HỌC VẬT RẮN & CÁC ĐỊNH LUẬT BẢO TOÀN

**Hai phương trình nền tảng (Newton–Euler):**
> (1) M**a**_G = Σ**F**_ngoài
> (2) d**L**_P/dt = Σ**M**_P (mômen ngoại lực với P)

**Pre của phương trình (2) — quan trọng nhất của toàn mảng Cơ học.** Phương trình mômen ở dạng đơn giản trên **chỉ đúng** khi điểm P thuộc một trong ba loại:
- **P cố định** trong hệ quy chiếu quán tính; **hoặc**
- **P ≡ G** (khối tâm) — đúng **ngay cả khi G đang gia tốc**, đây là đặc ân riêng của khối tâm; **hoặc**
- **P có gia tốc hướng dọc đường PG** (a_P ∥ **r**_PG), ví dụ tâm tức thời của vật lăn trên mặt cong trong vài cấu hình đặc biệt.

Với P gia tốc bất kỳ khác, phải bổ sung số hạng mômen của lực quán tính: d**L**_P/dt = Σ**M**_P − M(**r**_{PG} × **a**_P).

> **Đây là nguồn lỗi số 1.** Rất nhiều lời giải lấy mômen tại điểm tiếp xúc của vật lăn trong bài có mặt đỡ gia tốc, mà quên rằng điểm đó đang gia tốc.

**Động năng — định lý König:**
> T = ½M v_G² + ½ I_G ω²

Với chuyển động phẳng có ICR: cũng bằng ½ I_ICR ω² (chỉ dùng cho **động năng**, hợp lệ vì ICR có v = 0).

**Bảo toàn cơ năng — Pre cần kiểm tra:**
- Mọi lực sinh công đều là lực thế; **và**
- Ràng buộc là lý tưởng và **không phụ thuộc thời gian** (ràng buộc cưỡng bức chuyển động thì bơm năng lượng vào).
- **Lăn không trượt:** lực ma sát nghỉ tại điểm tiếp xúc **không sinh công** (điểm đặt có v = 0) ⇒ cơ năng bảo toàn. Đây là Pre cho phép dùng năng lượng cho mọi bài lăn — nhưng **chỉ khi thực sự không trượt**, nên phải kiểm tra f ≤ μN.

**Bảo toàn mômen động lượng — Pre:** Σ**M**_P = 0 quanh **trục** hoặc **điểm** P thoả Pre ở trên. Các CHỖ hay dùng: trục qua điểm có lực tác dụng (mômen = 0); trục qua đường tác dụng của trọng lực; trục va chạm.

**Va chạm vật rắn — thư viện công cụ:**
- Xung lượng **J** = ∫**F**dt; trong va chạm, lực thường (trọng lực...) bỏ qua được vì hữu hạn trong thời gian → 0.
- Phương trình xung: M(**v**_G′ − **v**_G) = **J** và I_G(**ω**′ − **ω**) = **r** × **J**.
- **Hệ số phục hồi** e = −(v′_{2n} − v′_{1n})/(v_{2n} − v_{1n}), lấy theo **phương pháp tuyến tại điểm va chạm** và theo **vận tốc của các điểm tiếp xúc**, không phải của khối tâm. Đây là bẫy lớn với va chạm lệch tâm.
- **Tâm va đập (center of percussion):** đánh vào điểm cách trục quay một đoạn ℓ = I_G/(M·d) + d thì **trục không chịu xung phản lực** (d = khoảng cách trục đến G). Giải thích "điểm ngọt" của vợt, gậy bóng chày — và là một câu hỏi hay của HSGQG.

**Dao động nhỏ của vật rắn — thuật toán năng lượng (nên dùng thay vì cân bằng lực):**
1. Chọn **một** toạ độ q mô tả độ lệch khỏi cân bằng.
2. Viết cơ năng E = **½A(q)q̇²** + **U(q)**, biểu diễn mọi vận tốc theo q̇.
3. Khai triển quanh q₀: A ≈ A₀, U ≈ U(q₀) + ½U″(q₀)(q−q₀)².
4. Đọc ngay: **ω = √(U″(q₀)/A₀)**.

Ưu điểm: không cần vẽ lực, không cần phản lực, không sai dấu. Trường hợp riêng: con lắc vật lý T = 2π√(I_P/(Mgd)); **chiều dài rút gọn** ℓ = I_P/(Md) và tính chất thuận nghịch (điểm treo và tâm dao động đổi chỗ cho cùng chu kỳ) — cơ sở của con lắc Kater.

---

# PHẦN II — CƠ HỌC LÍ THUYẾT

---

### THẺ 6 — HỆ QUY CHIẾU VỪA TỊNH TIẾN VỪA QUAY

**Công thức đầy đủ.** Gọi hệ S′ có gốc O′ (gia tốc **a**_{O′}) và quay với **ω** so với hệ quán tính S. Với một chất điểm có vị trí **r**′ trong S′:
> **v**_abs = **v**_{O′} + **ω** × **r**′ + **v**_rel
> **a**_abs = **a**_{O′} + **α** × **r**′ + **ω** × (**ω** × **r**′) + **2ω** × **v**_rel + **a**_rel

Viết lại theo ngôn ngữ "lực quán tính" trong S′: m**a**_rel = Σ**F**_thật + **F**_qt, với

| Lực quán tính | Biểu thức | Xuất hiện khi |
|---|---|---|
| Tịnh tiến | −m**a**_{O′} | gốc hệ gia tốc |
| **Ly tâm** | −m**ω**×(**ω**×**r**′) = +mω²**ρ** | hệ quay, ρ = khoảng cách tới trục |
| **Coriolis** | −2m**ω** × **v**_rel | hệ quay **và** vật chuyển động trong hệ |
| Euler | −m**α** × **r**′ | vận tốc góc của hệ biến thiên |

**Suf — khi nào nên đổi hệ quy chiếu (đây là CHỖ, không phải trực giác thuần):**
> Đổi sang HQC phi quán tính khi việc đó làm **ràng buộc trở thành tĩnh**. Ví dụ: hạt trượt trên rãnh của đĩa đang quay — trong HQC đĩa, rãnh đứng yên và bài thành một chiều. Vật trên nêm đang gia tốc — trong HQC nêm, mặt nêm đứng yên.

**Hai tính chất cần khai thác:**
- **Lực Coriolis không sinh công** (luôn ⊥ **v**_rel) ⇒ vẫn bảo toàn năng lượng trong HQC quay.
- **Lực ly tâm là lực thế**, với thế năng **U_ly tâm = −½mω²ρ²**. Do đó trong HQC quay đều, định nghĩa
> **U_eff = U_thật − ½mω²ρ²**
và cơ năng E = ½m v_rel² + U_eff **bảo toàn**. Đây là công cụ cực mạnh: giải được các bài điểm cân bằng trong hệ quay (điểm Lagrange L₁–L₅), hình dạng mặt chất lỏng quay, ổn định của vật trên đĩa quay — mà không cần giải phương trình chuyển động.

**Ứng dụng chuẩn phải biết:** trọng lực hiệu dụng trên Trái Đất (g_eff = g − ω²R cos²λ, và phương dây dọi lệch khỏi tâm) · độ lệch về phía Đông của vật rơi tự do · mặt phẳng dao động con lắc Foucault quay với ω sinλ · xoáy bão quay ngược chiều nhau ở hai bán cầu.

**Toán hoá.** Phương trình chuyển động trong S′ (ODE có thêm số hạng chéo do Coriolis — thường giải bằng biến phức z = x + iy, biến hệ 2 ODE thành 1); hoặc U_eff rồi khảo sát cực trị.

---

### THẺ 7 — CÁC HỆ TOẠ ĐỘ

**Nguyên tắc chọn — đây là "tập A" của việc toạ độ hoá:**
> Chọn hệ toạ độ sao cho **mỗi ràng buộc trở thành "một toạ độ = hằng số"**.

Đây là tiêu chí kiểm tra được, thay cho việc "chọn theo cảm giác":
- Hạt trên vòng tròn → cực, r = R const, còn 1 ẩn θ.
- Hạt trên mặt cầu → cầu, r = R const, còn 2 ẩn.
- Hạt trên mặt nón → cầu, θ = const.
- Hạt trên mặt trụ / rãnh xoắn → trụ, ρ = const.
- Vật trên mặt nghiêng → Descartes **nghiêng theo mặt phẳng**, y = 0.

**Công thức gia tốc trong từng hệ (phải thuộc, vì đây là bước chuyển sang toán):**

| Hệ | Vận tốc | Gia tốc |
|---|---|---|
| **Cực (r, θ)** | ṙ ê_r + rθ̇ ê_θ | (**r̈ − rθ̇²**) ê_r + (**rθ̈ + 2ṙθ̇**) ê_θ |
| **Trụ (ρ, φ, z)** | ρ̇ê_ρ + ρφ̇ê_φ + żê_z | (ρ̈ − ρφ̇²)ê_ρ + (ρφ̈ + 2ρ̇φ̇)ê_φ + z̈ê_z |
| **Tự nhiên (t, n)** | v ê_t | **v̇ ê_t + (v²/ρ) ê_n** |

Số hạng −rθ̇² là ly tâm, 2ṙθ̇ là Coriolis — chúng xuất hiện **thuần tuý do toán học của hệ toạ độ quay**, không cần đổi hệ quy chiếu. Đây là điểm nhiều người nhầm lẫn.

**Hệ toạ độ tự nhiên — CHỖ dùng:** mọi bài biết quỹ đạo nhưng không biết quy luật thời gian (vật trên đường cong, tàu lượn, xe vào cua). Cần **bán kính cong**:
> ρ = v³/|**v** × **a**| , hoặc với y = f(x): ρ = (1 + y′²)^{3/2} / |y″|

**Đếm bậc tự do.** n = (số toạ độ) − (số ràng buộc holonomic). Đây là bước bắt buộc, vì n quyết định cần bao nhiêu phương trình ⇒ là chỉ báo **đóng kín** của mô hình.

---

### THẺ 8 — PHƯƠNG PHÁP TOẠ ĐỘ HOÁ / LAGRANGE (công cụ hạng nặng)

Đây là "Nodal Analysis của Cơ học": một **thuật toán** thuần, chạy được bằng tay, gần như không cần trực giác. Với bài cơ hệ nhiều vật ràng buộc, đây là khác biệt giữa ba trang và nửa trang.

**Quy trình (chạy đúng thứ tự, không bỏ bước):**
1. Đếm bậc tự do n.
2. Chọn n **toạ độ suy rộng** q₁…q_n (Thẻ 7 cho tiêu chí chọn).
3. Viết **vị trí** của mọi vật theo (q, t).
4. Đạo hàm ra vận tốc; viết **T(q, q̇)** và **U(q)**.
5. **L = T − U**.
6. Với mỗi i: **d/dt(∂L/∂q̇_i) − ∂L/∂q_i = Q_i** (Q_i = lực suy rộng của lực **không thế**, như ma sát; bằng 0 nếu không có).

**Vì sao đây là lời giải cho Vấn đề 2:** phương pháp này **tự động triệt tiêu mọi phản lực liên kết lý tưởng** (lực căng dây, phản lực trục, phản lực pháp tuyến). Ta không bao giờ phải vẽ chúng, không bao giờ phải đoán chiều, không bao giờ sai dấu. Bước duy nhất còn đòi suy nghĩ là bước 2 — và Thẻ 7 đã cho tiêu chí cơ học cho bước đó.

**Ba hệ quả khai thác được ngay (cách tìm định luật bảo toàn một cách máy móc):**
- **Toạ độ cyclic:** nếu ∂L/∂q_k = 0 thì **p_k = ∂L/∂q̇_k bảo toàn**. Thay cho việc "nhìn ra" mômen động lượng bảo toàn, ta chỉ cần kiểm tra L có chứa q_k không.
- **Hàm năng lượng Jacobi:** h = Σq̇_i(∂L/∂q̇_i) − L **bảo toàn khi L không chứa t tường minh**.
  > *Cảnh báo tinh vi:* h = E **chỉ khi** ràng buộc không phụ thuộc t. Với hệ bị cưỡng bức (vòng quay với ω cho trước), h bảo toàn nhưng **E không bảo toàn** — nguồn ra đề của IPhO.
- **Nhân tử Lagrange:** nếu cần lấy lại một phản lực cụ thể, giữ ràng buộc đó dưới dạng f(q)=0 và thêm λ∂f/∂q_i vào vế phải; λ chính là phản lực đó.

**Dao động nhỏ nhiều bậc tự do — chuyển hẳn sang đại số tuyến tính:**
Khai triển quanh cân bằng: T = ½Σa_ij q̇_i q̇_j , U = ½Σk_ij q_i q_j. Phương trình chuyển động: **A q̈ + K q = 0**. Tần số riêng từ
> **det(K − ω²A) = 0**

Nghiệm ω_1…ω_n là các **mode chuẩn tắc**; vector riêng cho hình dạng mode. Bài "hai con lắc nối bằng lò xo", "ba khối lượng trên lò xo" trở thành bài trị riêng 2×2 hoặc 3×3 — hoàn toàn thuộc Vấn đề 3.

**Pre của Lagrange chuẩn.** Ràng buộc **holonomic** (viết được f(q,t)=0) và lý tưởng. Với ràng buộc **non-holonomic** (điển hình: quả cầu lăn không trượt trên mặt phẳng, xe có bánh không trượt ngang) phải dùng dạng nhân tử hoặc quay về Newton–Euler.

> Ghi chú thi cử: HSGQG không yêu cầu Lagrange, nhưng không cấm; nên dùng để **kiểm tra chéo** lời giải Newton. Ở IPhO thí sinh dùng tự do.

---

### THẺ 9 — KEPLER & TRƯỜNG XUYÊN TÂM

**Cấu trúc bài toán.** Lực **F** = f(r)ê_r. Hai bảo toàn tức thì, và chúng đủ để đóng kín:
- **L = m r²θ̇ = const** ⟺ định luật 2 Kepler (tốc độ quét diện tích dA/dt = L/2m không đổi). Đây cũng là lý do quỹ đạo **phẳng**.
- **E = ½m(ṙ² + r²θ̇²) + U(r) = const**

**Kỹ thuật then chốt — thế năng hiệu dụng (biến bài 2 chiều thành 1 chiều):**
> E = ½mṙ² + **U_eff(r)**, với **U_eff(r) = U(r) + L²/(2mr²)**

Sau bước này bài **hoàn toàn** là bài chuyển động một chiều: mọi câu hỏi về r_min, r_max, quỹ đạo tròn, ổn định, chu kỳ dao động bán kính đều đọc được từ đồ thị U_eff.
- Quỹ đạo tròn: U_eff′(r₀) = 0. Ổn định: U_eff″(r₀) > 0.
- Điểm dừng ṙ = 0: E = U_eff(r) ⇒ phương trình cho r_min, r_max.

**Kết quả Kepler (U = −GMm/r) — bộ công thức phải thuộc:**
> Quỹ đạo: **r = p/(1 + e·cosθ)** với p = L²/(GMm²·m) và **e = √(1 + 2EL²/(G²M²m³))**
> E < 0 ⇒ ellipse · E = 0 ⇒ parabol · E > 0 ⇒ hyperbol
> **E = −GMm/(2a)** — chỉ phụ thuộc **bán trục lớn a**
> **Vis-viva: v² = GM(2/r − 1/a)**
> Định luật 3: **T² = 4π²a³/(G(M+m))**

> **E = −GMm/2a và vis-viva là hai công cụ mạnh nhất của mảng này.** Chúng giải hầu hết bài chuyển quỹ đạo mà không cần động đến quỹ đạo conic.

**Bài toán hai vật.** Quy về một vật với **khối lượng rút gọn** μ = m₁m₂/(m₁+m₂) chuyển động quanh khối tâm đứng yên. Mọi công thức trên giữ nguyên với m → μ và M → M_tổng.

**Hai công cụ bổ sung:**
- **Định lý virial:** với U ∝ r^n, ⟨T⟩ = (n/2)⟨U⟩. Với hấp dẫn (n = −1): **⟨T⟩ = −½⟨U⟩**, do đó ⟨E⟩ = −⟨T⟩. Dùng cho bài hệ sao, khí quyển, và để ước lượng nhanh.
- **Lập luận tỉ lệ (scaling):** nếu mọi kích thước nhân k thì với lực 1/r², thời gian nhân k^{3/2}. Đây là cách chứng minh định luật 3 trong một dòng, và giải được bài "vật rơi thẳng vào tâm mất bao lâu" bằng cách coi đó là ellipse suy biến a = r₀/2 ⇒ t = T/2 = (π/2)√(r₀³/(2GM)) — một mẹo rất đẹp và hay ra.

**Toán hoá.** Hai bảo toàn ⇒ ODE bậc 1 tách biến dr/dt = √(2(E−U_eff)/m) ⇒ tích phân; hoặc dùng phép thế u = 1/r biến phương trình quỹ đạo thành **u″ + u = GMm²/L²** — một dao động điều hoà, nghiệm là conic ngay.

---

### THẺ 10 — CHUYỂN ĐỘNG PHẲNG CỦA VẬT RẮN (mức lí thuyết)

Mục này là nơi Thẻ 3, 4, 5, 8 gặp nhau. Điểm cần bổ sung ở mức lí thuyết:

**Mô hình chuẩn:** 3 toạ độ (x_G, y_G, φ) + các ràng buộc. Hệ phương trình:
> M ẍ_G = ΣF_x · M ÿ_G = ΣF_y · I_G φ̈ = ΣM_G

**Tính khả tích của ràng buộc lăn — điểm tinh tế hay ra ở IPhO:**
- Đĩa/trụ lăn không trượt trên **đường thẳng**: ẋ = Rφ̇ **tích phân được** thành x = Rφ + C ⇒ ràng buộc **holonomic** ⇒ bậc tự do giảm còn 1 ⇒ dùng Lagrange bình thường.
- Quả cầu lăn không trượt trên **mặt phẳng 2 chiều**: điều kiện lăn **không tích phân được** ⇒ **non-holonomic**. Quả cầu có 5 bậc tự do động học nhưng chỉ 3 bậc tự do tốc độ. Hệ quả vật lý: lăn theo một đường kín có thể trả cầu về đúng chỗ cũ nhưng **định hướng đã đổi**. Lagrange chuẩn **không dùng được**; phải dùng Newton–Euler hoặc nhân tử.

**Hai mẫu bài phải thuộc:**
- **Lăn trên mặt cong / trong lòng cầu:** dùng năng lượng E = ½(1+k)Mv² + Mgh (k từ I = kMR²) và **điều kiện rời mặt N = 0**. Nhớ dùng bán kính hiệu dụng (R_mặt − R_vật).
- **Lăn xuống mặt nghiêng:** a = g sinα/(1+k); điều kiện không trượt **μ ≥ k tanα/(1+k)**. Bất đẳng thức này là điều kiện phải kiểm tra, không được bỏ.

---

# PHẦN III — CƠ HỌC CHẤT LƯU

---

### THẺ 11 — CHẤT LỎNG ĐỨNG YÊN (THUỶ TĨNH)

**Phương trình gốc (nên nhớ ở dạng này, vì nó phủ mọi trường hợp):**
> **∇p = ρ·g**_eff

Trong trường trọng lực đều và HQC quán tính: p = p₀ + ρgh.

**Sức mạnh của dạng gốc — thuỷ tĩnh trong HQC phi quán tính:** thay **g**_eff = **g** − **a**. Hệ quả:
- **Mặt thoáng và mọi mặt đẳng áp luôn vuông góc với g_eff.**
- Bình gia tốc ngang a: mặt thoáng nghiêng góc **tanα = a/g**.
- Bình quay đều ω: g_eff có thành phần ly tâm ω²r ⇒ mặt thoáng là **parabol z = ω²r²/2g**. (Cũng suy ra được từ U_eff ở Thẻ 6.)

**Chất lưu nén được (khí quyển):** dp = −ρg dz với ρ = pM/RT ⇒ **p = p₀e^{−Mgz/RT}** (đẳng nhiệt). Nếu khí quyển đoạn nhiệt thì dT/dz = −g/c_p.

**Lực lên bề mặt.** F = ∫p dA. Với **mặt phẳng** ngập nước: F = p_G·A (p tại khối tâm mặt), nhưng **điểm đặt (tâm áp lực) thấp hơn khối tâm**:
> y_cp = y_G + I_G/(y_G·A)

Việc quên phân biệt "độ lớn dùng p_G" và "điểm đặt không ở G" là lỗi kinh điển khi tính mômen lật của đập, cửa cống.

**Archimedes.** F_A = ρ_lỏng·V_chìm·g, đặt tại **tâm đẩy B** = khối tâm phần chất lỏng bị chiếm chỗ (**không** phải khối tâm vật).

**Ổn định của vật nổi — metacenter (công cụ nâng cao thường thiếu):**
> Chiều cao metacentric: **GM = I_mặt nước/V_chìm − BG**. Vật nổi **ổn định ⟺ GM > 0**.

(I_mặt nước = mômen quán tính của tiết diện mặt nước quanh trục nghiêng; BG = khoảng cách tâm đẩy đến khối tâm.) Đây là lý do tàu bè rộng bản thì ổn định, và là câu trả lời đầy đủ cho "vì sao khối gỗ vuông nổi theo một hướng nhất định".

**Sức căng mặt ngoài — nhóm công cụ riêng:**
- Lực dọc đường biên dài ℓ: **F = σℓ** (nhân **2** nếu màng có hai mặt, như màng xà phòng).
- **Laplace:** Δp = σ(1/R₁ + 1/R₂). Giọt lỏng: **2σ/R**. Bong bóng xà phòng (hai mặt): **4σ/R**.
- **Mao dẫn:** h = 2σcosθ/(ρgr).
- **Năng lượng bề mặt E = σ·A** — dùng cho bài gộp/tách giọt, và cho mọi bài hỏi "năng lượng toả ra".
- CHỖ: mọi mặt phân cách cong → Laplace; mọi đường tiếp xúc ba pha → cân bằng lực σ.

**CHỖ-detector cho thuỷ tĩnh.** (1) Mỗi mặt đẳng áp nối hai nhánh → một phương trình p bằng nhau. (2) Mỗi vật ngập/nổi → Archimedes + phương trình mômen quanh trục nghiêng. (3) Mỗi mặt cứng bị ép → tích phân áp suất, tách riêng độ lớn và điểm đặt. (4) Mỗi mặt cong của chất lỏng → Laplace.

---

### THẺ 12 — CHẤT LỎNG CHUYỂN ĐỘNG

**(a) Phương trình liên tục.** Không nén được, dòng ống: **A₁v₁ = A₂v₂**. Dạng tổng quát ∂ρ/∂t + ∇·(ρ**v**) = 0.

**(b) Bernoulli.**
> p + ½ρv² + ρgh = const

**Pre — bốn điều kiện, và đây là công cụ bị dùng sai nhiều nhất trong toàn bộ Cơ học:**
1. Dòng **dừng** (không đổi theo thời gian).
2. Chất lưu **không nhớt** (không có tổn thất ma sát).
3. **Không nén được** (hoặc barotropic).
4. Áp dụng **dọc theo cùng một đường dòng**. Hằng số có thể khác nhau giữa các đường dòng — **trừ khi** dòng là **không xoáy** (irrotational), khi đó hằng số là chung cho toàn miền.

> Vi phạm phổ biến: dùng Bernoulli xuyên qua một vùng có xoáy hoặc có tổn thất (sau đột ngột mở rộng ống, qua bơm, qua vùng rối). Ở đó phải dùng **định lý động lượng** (mục d) thay vì Bernoulli.

**Bernoulli không dừng** (cho bài dao động chất lỏng trong ống chữ U, bài tháo bình nhanh):
> ∫(∂v/∂t)ds + Δ(p/ρ + v²/2 + gh) = 0

Số hạng tích phân theo đường dòng chính là chỗ sinh ra **quán tính của cột chất lỏng**, cho ra dao động điều hoà với ω = √(2g/L).

**Hệ quả trực tiếp:**
- **Torricelli:** v = √(2gh). Với lỗ thực có **hệ số co thắt** (vena contracta) ~0,6 ⇒ lưu lượng thực nhỏ hơn.
- **Venturi:** đo lưu lượng từ độ chênh áp.
- **Pitot:** p_toàn phần − p_tĩnh = ½ρv².
- **Bài tháo bình:** kết hợp liên tục + Torricelli ⇒ A_bình·(−dh/dt) = A_lỗ√(2gh) ⇒ **ODE tách biến** ⇒ t ∝ √h₀. Đây là ví dụ mẫu của việc chuyển hẳn sang Toán.

**(c) Áp suất động và lực nâng.** Chênh lệch tốc độ hai mặt ⇒ chênh áp ⇒ lực. Hiệu ứng Magnus, lực nâng cánh (định tính bằng Bernoulli, định lượng bằng lưu số Γ: L = ρvΓ trên đơn vị dài — Kutta–Joukowski).

**(d) Định lý động lượng cho thể tích kiểm tra — công cụ mà Bernoulli không thay thế được:**
> Σ**F**_ngoài = ṁ(**v**_ra − **v**_vào) (dòng dừng)

**CHỖ then chốt: chọn thể tích kiểm tra.** Quy tắc: bao trọn vùng có hiện tượng phức tạp (rối, va đập, tổn thất) sao cho **mặt vào và mặt ra đều nằm ở nơi dòng đều và đã biết**. Khi đó ta không cần biết gì về bên trong. Đây chính là tinh thần "tìm CHỖ thoả precondition".

Ứng dụng: lực của tia nước lên tấm chắn / cánh tuabin · lực lên khuỷu ống · lực đẩy tên lửa nước · lực cản của dòng lên vật · tính tổn thất năng lượng khi dòng đột ngột mở rộng (nơi Bernoulli sai nhưng động lượng đúng).

**(e) Nhớt và chế độ dòng.**
- **Số Reynolds Re = ρvL/η.** Re nhỏ ⇒ dòng tầng, lực cản ∝ v. Re lớn ⇒ rối, lực cản ∝ v². Đây là **tiêu chí chọn mô hình lực cản**, không phải đoán.
- **Stokes:** F = 6πηrv (Re ≪ 1). Vận tốc rơi giới hạn của giọt/hạt.
- **Poiseuille:** Q = πΔp R⁴/(8ηL). Chú ý phụ thuộc **R⁴** — đây là điểm ra đề (hẹp động mạch, ống mao dẫn).
- **Cản quán tính:** F = ½C_d ρ A v² (Re lớn).

**(f) Phân tích thứ nguyên & tương tự (công cụ cứu cánh).** Khi không giải được phương trình, dùng định lý Buckingham π: xây các tổ hợp không thứ nguyên (Re, Froude Fr = v/√(gL), Weber We = ρv²L/σ) và viết quan hệ giữa chúng. Cho phép trả lời "vận tốc phụ thuộc kích thước ra sao" mà không cần giải gì. Ở IPhO đây là kỹ năng được chấm điểm.

**Toán hoá.** Hệ đại số (Bernoulli + liên tục); ODE tách biến (tháo bình, rơi có cản); ODE bậc 2 (dao động cột chất lỏng); cân bằng đại số vector (định lý động lượng).

---

## PHẦN C — QUY TRÌNH DUYỆT TỔNG (Search Routine)

**Bước 0 — Ontology.** Liệt kê: có bao nhiêu vật? chất điểm hay vật rắn? liên kết gì giữa chúng? có chất lưu không? HQC nào?

**Bước 1 — Đếm bậc tự do n.** Đây là bước **bắt buộc** và là chỉ báo đóng kín: cần đúng n phương trình chuyển động độc lập.

**Bước 2 — Chọn nhánh theo trục Tĩnh/Động và theo n.**
- Tĩnh ⇒ Thẻ 2; nếu hệ nhiều khâu ⇒ **công ảo**.
- Động, n = 1 ⇒ **năng lượng** là đủ và nhanh nhất.
- Động, n ≥ 2, ràng buộc holonomic ⇒ **Lagrange** (Thẻ 8).
- Động, ràng buộc non-holonomic hoặc cần biết phản lực ⇒ **Newton–Euler** (Thẻ 5).

**Bước 3 — Quyết định hệ quy chiếu.** Có HQC nào làm ràng buộc thành tĩnh không? Nếu có, đổi sang và thêm đủ bốn lực quán tính (Thẻ 6).

**Bước 4 — Duyệt CHỖ theo danh mục cố định:**
- Mỗi vật / mỗi nhóm vật → một sơ đồ vật tự do
- Mỗi liên kết → loại và số ẩn phản lực tương ứng
- Mỗi giao điểm giá lực chưa biết → ứng viên điểm lấy mômen
- Mỗi ràng buộc hình học → **viết f(q)=0 rồi đạo hàm theo t** (ra quan hệ vận tốc), đạo hàm lần nữa (ra quan hệ gia tốc)
- Mỗi cặp điểm trên vật rắn → bất biến hình chiếu vận tốc dọc đường nối
- Mỗi chuyển động phẳng → tìm ICR
- Mỗi toạ độ suy rộng không xuất hiện trong L → một đại lượng bảo toàn
- Mỗi mặt phân cách chất lưu → cân bằng áp suất / Laplace
- Mỗi vùng dòng phức tạp → một thể tích kiểm tra

**Bước 5 — Kiểm tra Pre (danh sách ngắn, phải chạy hết):**
- Điểm lấy mômen có thoả ba điều kiện ở Thẻ 5 không?
- ω có dọc trục quán tính chính để viết L = Iω không?
- Có thực sự không trượt không (kiểm tra f ≤ μN)?
- Bernoulli có bị vi phạm bởi tổn thất/rối/không dừng không?
- Bài có siêu tĩnh không?

**Bước 6 — Kiểm tra biên & giới hạn.** Cho khối lượng → 0 hoặc → ∞; cho μ → 0; cho I → 0 (vật rắn về chất điểm); cho ω → 0. Kiểm tra thứ nguyên. Kiểm tra dấu bằng lập luận vật lý.

---

## PHẦN D — BẢNG TRA "DẤU HIỆU ĐỀ BÀI → CÔNG CỤ"

| Dấu hiệu trong đề | Công cụ gần như chắc chắn |
|---|---|
| "vật ghép", "vật khuyết lỗ", "tìm trọng tâm" | Phân rã + khối lượng âm + đối xứng (Thẻ 1) |
| "thang tựa tường", "điều kiện không trượt/không lật" | Ba phương trình cân bằng + hai ngưỡng riêng + nón ma sát (Thẻ 2) |
| "hệ đòn bẩy/ròng rọc/cơ cấu nhiều khâu", "tỉ số lực" | **Công ảo** |
| "cân bằng bền hay không bền", "tần số dao động nhỏ" | U(q), U″(q₀); ω = √(U″/A₀) |
| "dây xích treo", "cầu treo" | ODE cân bằng đoạn vi phân → cosh hoặc parabol |
| "thanh trượt, hai đầu tựa", "cơ cấu tay quay" | **ICR** + bất biến hình chiếu vận tốc (Thẻ 3) |
| "lăn không trượt" | v_G = ωR; ma sát nghỉ không sinh công ⇒ dùng năng lượng; kiểm tra μ |
| "va chạm lệch tâm", "điểm ngọt của gậy" | Xung + mômen xung; **tâm va đập** (Thẻ 5) |
| "bánh xe mất cân bằng", "rung ổ trục", "vật quay lật" | **Tensor quán tính**, L không cùng phương ω (Thẻ 4) |
| "hạt trên đĩa quay", "vật trong thang máy gia tốc" | Đổi HQC + 4 lực quán tính; U_eff (Thẻ 6) |
| "lệch Đông", "con lắc Foucault", "bão xoáy" | Coriolis |
| "hệ nhiều vật nối dây/lò xo, tìm gia tốc" | **Lagrange** — khử sạch lực căng (Thẻ 8) |
| "hai con lắc nối nhau", "mode dao động" | det(K − ω²A) = 0 |
| "vệ tinh, chuyển quỹ đạo, tốc độ tại viễn/cận điểm" | **E = −GMm/2a** và **vis-viva** (Thẻ 9) |
| "rơi thẳng vào tâm mất bao lâu" | Ellipse suy biến a = r₀/2, t = T/2 |
| "quả cầu lăn trên mặt phẳng 2D" | **Non-holonomic** — không dùng Lagrange chuẩn |
| "bình gia tốc / bình quay, mặt thoáng có dạng gì" | ∇p = ρg_eff; mặt ⊥ g_eff (Thẻ 11) |
| "khối gỗ nổi theo hướng nào", "tàu có lật không" | **Metacenter GM > 0** |
| "bong bóng, giọt, mao dẫn" | Laplace + σℓ + năng lượng σA |
| "tháo nước khỏi bình sau bao lâu" | Liên tục + Torricelli → ODE tách biến |
| "lực của tia nước lên tấm chắn / lên khuỷu ống" | **Định lý động lượng cho thể tích kiểm tra** — không phải Bernoulli |
| "hạt rơi trong chất lỏng, vận tốc giới hạn" | Stokes nếu Re nhỏ; ½C_dρAv² nếu Re lớn — kiểm tra Re trước |
| "không giải được, hỏi phụ thuộc kích thước ra sao" | Phân tích thứ nguyên, Buckingham π |

---

## PHẦN E — DANH SÁCH BẪY (kiểm tra trước khi nộp)

1. **Lấy mômen tại một điểm đang gia tốc** mà không thêm số hạng mômen lực quán tính (lỗi nghiêm trọng nhất).
2. Viết L = Iω khi ω **không** dọc trục quán tính chính.
3. Dùng ICR để tính **gia tốc** (ICR chỉ có v = 0, không có a = 0).
4. Quên định lý Steiner khi cộng/trừ mômen quán tính của mảnh hoặc lỗ.
5. Dùng định lý trục vuông góc cho vật **không** phẳng.
6. Dùng bảo toàn cơ năng khi **có trượt** (ma sát trượt sinh công âm) hoặc khi ràng buộc phụ thuộc thời gian.
7. Không kiểm tra μ ≥ k tanα/(1+k) rồi khẳng định vật lăn không trượt.
8. Quên rằng bài là **siêu tĩnh** và cố giải bằng ba phương trình cân bằng.
9. Viết f = μN ở trạng thái **tĩnh** (đúng ra là f ≤ μN).
10. Chỉ xét ngưỡng trượt mà bỏ ngưỡng lật, hoặc ngược lại.
11. Hệ số phục hồi e tính theo vận tốc **khối tâm** thay vì vận tốc **điểm tiếp xúc** trong va chạm lệch tâm.
12. Nhầm h (hàm Jacobi) với E khi ràng buộc phụ thuộc t (vòng quay cưỡng bức).
13. Dùng Lagrange chuẩn cho ràng buộc **non-holonomic**.
14. Quên khối lượng rút gọn μ trong bài hai vật có khối lượng so sánh được.
15. Dùng **Bernoulli** qua vùng có tổn thất, có rối, hoặc qua bơm.
16. Dùng Bernoulli xuyên giữa hai đường dòng khác nhau trong dòng **có xoáy**.
17. Tính lực lên đập bằng p_G·A nhưng đặt lực tại **khối tâm** thay vì tâm áp lực.
18. Tính Archimedes đặt tại khối tâm **vật** thay vì tâm đẩy (khối tâm phần chìm).
19. Bong bóng xà phòng dùng 2σ/R thay vì **4σ/R**.
20. Chọn công thức lực cản (∝v hay ∝v²) mà không kiểm tra **Re**.

---

## PHẦN F — NHỮNG CHỖ CHƯA ĐẦY ĐỦ (trung thực về giới hạn)

Đây là bản khung mật độ cao, chưa phải bản đầy đủ. Những phần còn nợ, xếp theo mức cần bổ sung:

- **Thẻ 4–5:** động lực học con quay (gyroscope) chỉ mới nêu phương trình Euler, chưa khai triển tiến động và chương động — đây là nội dung có ở VPhO/IPhO.
- **Thẻ 8:** chưa triển khai hình thức Hamilton (phương trình chính tắc, biến tác dụng–góc), vốn hữu ích cho bài biến đổi đoạn nhiệt bất biến — có xuất hiện ở IPhO.
- **Thẻ 9:** chưa nêu vector Laplace–Runge–Lenz và ứng dụng của nó (chứng minh quỹ đạo đóng, xử lý nhiễu loạn tiến động cận điểm).
- **Thẻ 2:** lý thuyết vít động lực (wrench) và trục trung tâm chỉ mới nêu, chưa có ví dụ; bài siêu tĩnh chưa nối sang cơ học vật liệu (ứng suất, biến dạng, Hooke).
- **Thẻ 12:** chưa có phương trình Navier–Stokes ở dạng đầy đủ, chưa xử lý lớp biên, chưa xử lý sóng mặt chất lỏng (tán sắc √(gλ/2π)).
- **Chưa bao gồm:** dao động và sóng cơ ở mức chuyên đề riêng, cơ học tương đối tính, và động lực học hệ biến khối (tên lửa) — vì nằm ngoài ba mục trong ảnh.
