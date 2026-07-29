# TÀI LIỆU GIẢNG DẠY VẬT LÝ OLYMPIC (IPhO)
## PHẦN I: CÔNG CỤ TOÁN HỌC NỀN TẢNG
*Soạn cho học sinh lớp 9, xây dựng từ những gì đã biết, đi lên từng bước, không học vẹt*

---

## LỜI DẶN CHO GIÁO VIÊN (đọc trước khi dạy)

Tài liệu gốc (formula sheet của J. Kalda dùng cho đội tuyển IPhO) giả định người đọc đã thành thạo đạo hàm, tích phân, số phức, phương trình vi phân và vector — những thứ học sinh lớp 9 Việt Nam chưa học. Toàn bộ Phần I dưới đây được viết lại theo một **trình tự phụ thuộc logic**: mỗi công cụ mới chỉ dùng những gì vừa được chứng minh ở mục trước, không có công cụ nào "từ trên trời rơi xuống".

**Học sinh lớp 9 đã có sẵn** (dùng làm điểm xuất phát): các phép biến đổi đại số, phương trình bậc hai (denta), hệ thức lượng trong tam giác vuông (sin, cos, tan, cot của góc nhọn), định lý Pythagoras, tam giác đồng dạng, góc nội tiếp — góc ở tâm, tứ giác nội tiếp, trọng tâm tam giác.

**Sẽ được xây mới trong Phần I**: vector và các phép nhân vector, các công thức lượng giác cộng góc, khái niệm giới hạn — đạo hàm — tích phân, khai triển Taylor, số phức, phương trình vi phân tuyến tính, hai phương pháp số cơ bản.

Mỗi mục có 4 phần cố định: **Vì sao cần** (động cơ) → **Xây dựng / chứng minh** (bản chất) → **Ví dụ** → **Bài tập tự luyện** (thuần túy toán, không có ngữ cảnh vật lý, đúng theo yêu cầu của thầy/cô). Đáp số bài tập ở cuối tài liệu.

Đây là lượng kiến thức của khoảng 1 học kỳ dạy nghiêm túc (2 buổi/tuần) cho học sinh khá–giỏi. Không nên dạy dồn — mỗi mục cần thời gian để "ngấm" trước khi dùng làm nền cho mục sau.

**Bản đồ liên kết tới các Phần sau** (để thầy/cô hình dung vì sao mỗi mục ở đây là cần thiết):

| Công cụ ở Phần I | Sẽ dùng ở |
|---|---|
| Vector, tích vô hướng/có hướng | Động học, Cơ học, Điện từ |
| Định lý sin/cos, công thức cộng góc | Dao động, Quang học |
| Đạo hàm, tích phân | Động học (vận tốc, gia tốc), Cơ học, Nhiệt động lực học |
| Khai triển Taylor | Gần đúng trong hầu hết mọi phần |
| Số phức | Dao động điều hòa, Mạch điện xoay chiều |
| Phương trình vi phân | Dao động, Mạch RLC |
| Phương pháp số | Các bài toán không giải được bằng công thức đóng |

---

## MỤC A. VECTOR — ĐẠI LƯỢNG CÓ HƯỚNG

### A.1 Vì sao cần

Học sinh đã quen với đại lượng "chỉ có độ lớn" (số đo góc, diện tích, khối lượng...). Nhưng có những đại lượng cần **cả độ lớn lẫn hướng** mới mô tả đủ — ví dụ độ dịch chuyển từ nhà đến trường không chỉ là "300 mét" mà còn "về hướng nào". Vector là công cụ chính xác hóa ý tưởng "đại lượng có hướng" này, và hóa ra hai phép "nhân" vector với nhau sẽ tự động sinh ra hầu hết các công thức lượng giác và hình học phẳng mà ta biết — đây là điều bất ngờ và rất mạnh.

### A.2 Định nghĩa và phép cộng

Vector **a** là một đoạn có hướng, đặc trưng bởi độ dài |**a**| và hướng. Phép cộng hai vector: đặt đuôi **b** vào đầu **a**, vector tổng là đoạn nối từ đuôi **a** đến đầu **b** (quy tắc "nối đuôi"), tương đương quy tắc hình bình hành. Phép cộng vector có tính giao hoán và kết hợp — kiểm chứng được bằng hình vẽ.

Trong hệ tọa độ, **a** = (ax, ay), và **a** + **b** = (ax+bx, ay+by).

### A.3 Tích vô hướng (dot product)

**Định nghĩa:** **a**·**b** = |**a**||**b**|cos φ, với φ là góc giữa hai vector.

**Vì sao định nghĩa như vậy có ích:** |**b**|cos φ chính là hình chiếu của **b** lên phương của **a**. Vậy **a**·**b** = |**a**| × (hình chiếu của **b** lên **a**) — một đại lượng đo "hai vector cùng hướng đến đâu": bằng 0 khi vuông góc, dương khi cùng phía, âm khi ngược phía.

**Chứng minh công thức theo tọa độ** **a**·**b** = axbx + ayby: Đây là hệ quả của **tính phân phối** **a**·(**b**+**c**) = **a**·**b** + **a**·**c**. Tính phân phối đúng vì hình chiếu của tổng hai vector lên một phương bằng tổng hình chiếu của từng vector (tự vẽ hình chiếu vuông góc của **b**, **c** và **b**+**c** lên đường thẳng chứa **a** sẽ thấy ngay điều này — hình chiếu là phép biến đổi tuyến tính). Từ đó, viết **a** = ax**ex** + ay**ey** (**ex**, **ey** là vector đơn vị trên hai trục), khai triển bằng phân phối:

**a**·**b** = (ax**ex**+ay**ey**)·(bx**ex**+by**ey**) = axbx(**ex**·**ex**) + axby(**ex**·**ey**) + aybx(**ey**·**ex**) + ayby(**ey**·**ey**)

Vì **ex**·**ex** = **ey**·**ey** = 1 (góc 0°, cos0=1) và **ex**·**ey** = 0 (vuông góc), ta còn lại **a**·**b** = axbx + ayby. ∎

**Ứng dụng ngay: định lý cos như một hệ quả tự nhiên.** Xét tam giác với hai cạnh là vector **a**, **b** xuất phát từ một đỉnh, cạnh còn lại là **a** − **b**. Ta có:

|**a**−**b**|² = (**a**−**b**)·(**a**−**b**) = **a**·**a** − 2**a**·**b** + **b**·**b** = |**a**|² + |**b**|² − 2|**a**||**b**|cos φ

Đây chính xác là định lý cos: c² = a² + b² − 2ab cos φ. Khi φ = 90°, số hạng cos φ triệt tiêu, ta thu lại định lý Pythagoras — nghĩa là **định lý cos là bản mở rộng của Pythagoras cho tam giác bất kỳ**, và ta vừa nhìn thấy rõ tại sao.

### A.4 Tích có hướng (cross product)

**Định nghĩa (trong mặt phẳng, xét độ lớn):** |**a**×**b**| = |**a**||**b**|sin φ. Đây đúng bằng **diện tích hình bình hành** dựng trên hai cạnh **a**, **b** (vì diện tích hình bình hành = cạnh × chiều cao = |**a**| × |**b**|sin φ). Về hướng (trong không gian 3 chiều): **a**×**b** vuông góc với cả **a** và **b**, chiều xác định theo quy tắc bàn tay phải. Tính phản giao hoán **a**×**b** = −**b**×**a** phản ánh đúng việc đổi thứ tự thì đổi chiều quay từ **a** sang **b**.

**Công thức tọa độ** (suy ra tương tự A.3, dùng phân phối và **ex**×**ey**=**ez**, **ex**×**ex**=0...):

**a**×**b** = (aybz − byaz)**ex** + (azbx − bzax)**ey** + (axby − bxay)**ez**

**Ứng dụng: định lý sin.** Diện tích tam giác cạnh a, b, c (đối diện góc A, B, C) tính bằng nửa tích có hướng của hai cạnh kề bất kỳ, cho ba cách tính bằng nhau:

S = ½ ab sin C = ½ bc sin A = ½ ca sin B

Chia cả ba vế cho ½abc:

sin C / c = sin A / a = sin B / b ⟺ a/sin A = b/sin B = c/sin C

Đó chính là định lý sin — sinh ra trực tiếp từ việc "diện tích tam giác không phụ thuộc vào việc ta chọn cặp cạnh nào để tính". (Phần "= 2R" trong công thức gốc sẽ chứng minh ở Mục C bằng góc nội tiếp.)

**Tích hỗn hợp** (a, b, c) ≡ **a**·(**b**×**c**): về bản chất, **b**×**c** là vector có độ dài bằng diện tích đáy hình hộp dựng trên **b**, **c**, hướng vuông góc đáy; nhân vô hướng với **a** tức là lấy diện tích đáy nhân với chiều cao (hình chiếu của **a** lên phương vuông góc đáy) — chính là **thể tích hình hộp** dựng trên ba vector. Vì thể tích không đổi dù ta "xoay vòng" chọn cạnh nào làm đáy, ta có (**a**,**b**,**c**) = (**b**,**c**,**a**) = (**c**,**a**,**b**).

### A.5 Ví dụ

Cho **a** = (3,4), **b** = (4,−3). Tính **a**·**b** và góc giữa chúng.
**a**·**b** = 3×4 + 4×(−3) = 12−12 = 0 ⟹ hai vector vuông góc (φ=90°) — kiểm tra nhanh mà không cần đo góc bằng thước.

### A.6 Bài tập tự luyện (Mục A)

1. Cho tam giác ABC với AB=5, AC=7, góc A=60°. Dùng tích vô hướng tính BC.
2. Chứng minh bằng vector: trong tam giác ABC, trọng tâm G thỏa **AG** = ⅓(**AB**+**AC**). Từ đó suy ra G chia trung tuyến theo tỉ lệ 2:1 kể từ đỉnh. *(Gợi ý: trung điểm M của BC có **AM** = ½(**AB**+**AC**); G nằm trên AM sao cho **AG**=k·**AM**, dùng thêm một trung tuyến nữa để tìm k.)*
3. Cho **a**=(1,2,3), **b**=(4,5,6). Tính **a**×**b** và kiểm tra kết quả vuông góc với cả **a** lẫn **b** (bằng tích vô hướng bằng 0).
4. Ba điểm A(0,0), B(4,0), C(1,3). Tính diện tích tam giác ABC bằng tích có hướng của **AB** và **AC**, rồi kiểm tra lại bằng công thức ½|đáy×cao| thông thường.

---

## MỤC B. CÔNG THỨC LƯỢNG GIÁC CỘNG GÓC

### B.1 Vì sao cần

Học sinh đã biết sin, cos của **một** góc nhọn trong tam giác vuông. Nhưng rất nhiều bài toán cần biết sin/cos của **tổng hai góc** (ví dụ hai dao động cộng lại, hai tia sáng giao thoa). Điều tuyệt vời là công cụ vừa xây ở Mục A cho phép suy ra các công thức này **không cần học thuộc**.

### B.2 Xây dựng từ tích vô hướng và tích có hướng

Xét hai vector đơn vị **u** = (cos α, sin α) và **v** = (cos β, sin β) (mỗi vector là điểm trên đường tròn đơn vị ứng với góc α, β so với trục Ox). Góc giữa **u** và **v** là (α−β).

Theo A.3: **u**·**v** = |**u**||**v**|cos(α−β) = cos(α−β) (vì |**u**|=|**v**|=1). Nhưng cũng theo công thức tọa độ:

**u**·**v** = cos α cos β + sin α sin β

Vậy: **cos(α−β) = cos α cos β + sin α sin β**. Thay β bằng −β (dùng cos(−β)=cosβ, sin(−β)=−sinβ) được **cos(α+β) = cos α cos β − sin α sin β**.

Tương tự, theo A.4, thành phần z của **u**×**v** = uxvy − uyvx = cos α sin β − sin α cos β, và độ lớn có dấu này bằng sin(β−α). Vậy sin(β−α) = cosα sinβ − sinα cosβ, tức **sin(α−β) = sin α cos β − cos α sin β**, và thay β→−β: **sin(α+β) = sin α cos β + cos α sin β**.

**tan(α±β)** suy ra bằng cách chia trực tiếp hai công thức trên cho nhau, rồi chia cả tử và mẫu cho cosα cosβ:

tan(α±β) = sin(α±β)/cos(α±β) = (tanα ± tanβ)/(1 ∓ tanα tanβ)

**Công thức nhân đôi**: thay β=α vào công thức cộng: cos2α = cos²α − sin²α = 2cos²α−1 = 1−2sin²α. Từ đây giải ngược ra công thức hạ bậc: cos²α = (1+cos2α)/2, sin²α = (1−cos2α)/2 — chỉ là biến đổi đại số của chính công thức nhân đôi, không phải công thức độc lập cần nhớ riêng.

**Công thức tích thành tổng**: cộng hai công thức cos(α+β) và cos(α−β) vế theo vế, số hạng sinαsinβ triệt tiêu:

cos(α+β) + cos(α−β) = 2cosα cosβ ⟹ cosα cosβ = [cos(α+β)+cos(α−β)]/2

Các công thức còn lại trong nhóm này (sinα sinβ, sinα cosβ...) suy ra tương tự bằng cộng/trừ các công thức cộng góc.

**Công thức tổng thành tích**: đặt α+β=x, α−β=y (⟹ α=(x+y)/2, β=(x−y)/2) rồi thế ngược vào công thức tích-thành-tổng ở trên.

### B.3 Điểm mấu chốt cần học sinh nắm

Chỉ cần **nhớ chắc hai công thức gốc** cos(α−β) và sin(α+β) (hoặc nhớ cách suy ra chúng từ **u**·**v** và **u**×**v**) — toàn bộ phần còn lại (nhân đôi, hạ bậc, tích-tổng, tổng-tích, tan) chỉ là **biến đổi đại số** từ hai công thức gốc. Đây chính là "hiểu bản chất thay vì học vẹt": thay vì nhớ 8-10 công thức rời rạc, học sinh chỉ cần nhớ *một cách xây dựng*.

### B.4 Bài tập tự luyện (Mục B)

1. Từ cos(α+β) và cos(α−β), tự suy ra công thức sin α sin β = ... và sin α cos β = ... (đừng tra bảng — dùng đúng cách cộng/trừ như ví dụ đã làm với cosα cosβ).
2. Biết sin α = 3/5 (α nhọn), cos β = 5/13 (β nhọn). Tính cos(α+β), sin(α−β).
3. Chứng minh cos3α = 4cos³α − 3cosα bằng cách viết cos3α = cos(2α+α) rồi dùng công thức cộng và nhân đôi.
4. Rút gọn biểu thức (cos75° + cos15°) mà không dùng máy tính, bằng công thức tổng thành tích.

---

## MỤC C. HÌNH HỌC: ĐƯỜNG TRÒN, DIỆN TÍCH TAM GIÁC, TRỌNG TÂM

*(Phần lớn mục này ôn và mở rộng kiến thức lớp 9 đã học ở chương "Góc với đường tròn" — chỉ nêu ngắn gọn các hệ quả hay dùng trong Vật lý.)*

**Góc nội tiếp bằng nửa góc ở tâm chắn cùng một cung** (đã học). Hệ quả quan trọng hay quên: **cạnh huyền của tam giác vuông là đường kính đường tròn ngoại tiếp** (vì góc vuông nội tiếp chắn nửa đường tròn, tức chắn cung 180°); và **tứ giác có hai góc đối bù nhau (tổng 180°) thì nội tiếp được đường tròn** (chiều đảo của định lý góc nội tiếp).

**Diện tích tam giác — bốn công thức, một bản chất:**
- S = ½ a·ha (đáy nhân chiều cao chia 2 — định nghĩa gốc)
- S = ½ ab sin C (đã suy ra ở Mục A.4 từ tích có hướng — chỉ là viết ha = b sinC)
- S = pr, với p là nửa chu vi, r bán kính đường tròn nội tiếp: chia tam giác thành 3 tam giác nhỏ đỉnh chung là tâm nội tiếp I, mỗi tam giác nhỏ có chiều cao đúng bằng r, đáy là một cạnh của tam giác lớn — cộng ba diện tích: S = ½ar+½br+½cr = pr.
- S = abc/4R: từ định lý sin a=2R sinA, suy sinA = a/2R, thay vào S=½bc sinA được S = abc/4R.
- S = √[p(p−a)(p−b)(p−c)] (Heron): suy ra bằng đại số từ S=½ab sinC và định lý cos (dùng sin²C=1−cos²C rồi phân tích thành nhân tử) — có thể để học sinh tự làm như bài tập nâng cao.

**Trọng tâm chia trung tuyến theo tỉ lệ 2:1** — đã chứng minh bằng vector ở bài tập A.6.2. Đây là ví dụ cho học sinh thấy: một kết quả hình học "thuần túy" (không có vẻ liên quan đến vector) lại được chứng minh gọn nhất bằng vector — bài học quan trọng: **chọn đúng công cụ giúp bài toán ngắn đi rất nhiều**.

### C.1 Bài tập tự luyện (Mục C)

1. Chứng minh công thức Heron từ S=½ab sinC và định lý cos (gợi ý: viết sin²C = (1−cosC)(1+cosC), thay cosC theo a,b,c từ định lý cos, rồi phân tích thành nhân tử dạng (a+b+c)(−a+b+c)(a−b+c)(a+b−c)).
2. Một tứ giác ABCD có góc A=110°. Góc C bằng bao nhiêu để tứ giác nội tiếp được đường tròn?

---

## MỤC D. GIỚI HẠN VÀ ĐẠO HÀM

### D.1 Vì sao cần: bài toán vận tốc tức thời

Xét một hàm số thuần túy s(t) = t² (không cần gắn ý nghĩa vật lý vội). Ta hỏi: "hàm số này thay đổi nhanh cỡ nào tại đúng thời điểm t₀ = 3?"

**Tốc độ thay đổi trung bình** trên đoạn [3, 3+Δt] là:

[s(3+Δt) − s(3)] / Δt = [(3+Δt)² − 9] / Δt = [9 + 6Δt + Δt² − 9]/Δt = 6 + Δt

Với Δt=1 được 7; Δt=0.1 được 6.1; Δt=0.01 được 6.01... Con số này **tiến gần đến 6** khi Δt càng nhỏ, dù không bao giờ đúng bằng 6 nếu Δt≠0 (và ta không được chia cho 0). "6" chính là **tốc độ thay đổi tức thời** tại t=3 — đây là ý tưởng cốt lõi của giới hạn và đạo hàm.

### D.2 Định nghĩa

**Giới hạn** lim(x→x₀) f(x) = L nghĩa là: f(x) tiến gần L bất kỳ mức nào ta muốn, miễn x đủ gần x₀ (nhưng không cần x=x₀).

**Đạo hàm** tại x₀:

f'(x₀) = lim(x→x₀) [f(x) − f(x₀)] / (x − x₀)

**Ý nghĩa hình học**: đây là **hệ số góc của tiếp tuyến** với đồ thị y=f(x) tại điểm x₀ — vì [f(x)−f(x₀)]/(x−x₀) là hệ số góc của đường thẳng nối hai điểm trên đồ thị (cát tuyến), và khi x→x₀, cát tuyến "xoay" dần thành tiếp tuyến.

### D.3 Đạo hàm của hàm lũy thừa xⁿ

Với f(x) = x², dùng đúng cách tính D.1: f'(x) = lim [(x+h)²−x²]/h = lim(2x+h) = 2x.

Với f(x) = x³: (x+h)³ = x³+3x²h+3xh²+h³, nên [f(x+h)−f(x)]/h = 3x²+3xh+h² → 3x² khi h→0.

**Quy luật chung** (xⁿ)' = nxⁿ⁻¹: khai triển (x+h)ⁿ bằng nhị thức Newton, số hạng đầu là xⁿ (triệt tiêu với −xⁿ), số hạng thứ hai là n·xⁿ⁻¹·h — sau khi chia cho h và cho h→0, chỉ số hạng này còn lại (mọi số hạng khác đều còn thừa số h). Đây là lý do vì sao số mũ "tụt xuống một bậc và ra làm hệ số" — không phải phép màu, mà là hệ quả trực tiếp của nhị thức Newton.

### D.4 Các quy tắc tính đạo hàm

- **Tổng**: (f+g)' = f'+g' — hiển nhiên từ định nghĩa (giới hạn của tổng bằng tổng giới hạn).
- **Tích**: (fg)' = f'g + fg'. Chứng minh: [f(x+h)g(x+h) − f(x)g(x)]/h. Cộng và trừ f(x+h)g(x) ở tử:
 = f(x+h)[g(x+h)−g(x)]/h + g(x)[f(x+h)−f(x)]/h → f(x)g'(x) + g(x)f'(x) khi h→0.
- **Hợp hàm (chain rule)**: f[g(x)]' = f'[g(x)]·g'(x). Ý nghĩa: nếu y thay đổi theo tốc độ f' so với u=g(x), và u thay đổi theo tốc độ g' so với x, thì "tốc độ nhân tốc độ" cho tốc độ thay đổi của y so với x — giống như xe A chạy nhanh gấp đôi B, B chạy nhanh gấp ba C thì A nhanh gấp sáu C.

### D.5 Đạo hàm của sin x, cos x — dùng lại Mục B!

f'(x) = lim [sin(x+h) − sin x]/h. Dùng công thức cộng góc (Mục B): sin(x+h) = sinx cosh + cosx sinh. Vậy:

[sin(x+h)−sinx]/h = sinx·(cosh−1)/h + cosx·(sinh/h)

Cần hai giới hạn cơ bản khi h→0: **sinh/h → 1** và **(cosh−1)/h → 0**. Chứng minh trực giác bằng hình học: trên đường tròn đơn vị, với góc h rất nhỏ, độ dài dây cung ≈ độ dài cung tròn ≈ h, và sinh chính là gần đúng chiều cao của dây cung đó, nên sinh/h→1 (kẹp giữa diện tích tam giác và hình quạt); còn cosh−1 là bậc hai theo h (từ cosh≈1−h²/2, sẽ chứng minh chặt hơn ở Mục F) nên chia cho h vẫn →0.

Thay hai giới hạn vào: (sinx)' = sinx·0 + cosx·1 = **cos x**. Chứng minh tương tự cho (cosx)' = **−sin x**.

### D.6 Đạo hàm của hàm mũ, log, và hàm ngược

**eˣ** là số được **định nghĩa** sao cho (eˣ)' = eˣ (e ≈ 2.71828 là hằng số duy nhất có tính chất "đạo hàm bằng chính nó" — sẽ thấy rõ hơn qua khai triển Taylor ở Mục F).

**ln x** là hàm ngược của eˣ. Nếu y = ln x thì x = e^y. Lấy đạo hàm hai vế theo x (vế phải dùng chain rule, coi y là hàm của x): 1 = e^y · y' = x · y', suy ra **y' = 1/x**.

**arctan x**: nếu y=arctanx thì x=tany. Đạo hàm hai vế: 1 = (tany)'·y'. Cần (tanx)' = (sinx/cosx)' — dùng quy tắc thương (suy từ quy tắc tích, coi 1/g = g⁻¹): (tanx)' = (cos²x+sin²x)/cos²x = 1+tan²x. Vậy 1 = (1+tan²y)y' = (1+x²)y', suy ra **y' = 1/(1+x²)**. Đây là ví dụ đẹp cho thấy đạo hàm hàm ngược luôn suy được từ đạo hàm hàm thuận bằng đúng một kỹ thuật: đạo hàm ẩn hai vế.

### D.7 Ví dụ

Tìm hệ số góc tiếp tuyến của y = x³ − 2x tại x=1. y' = 3x²−2, tại x=1: y'=1.

### D.8 Bài tập tự luyện (Mục D)

1. Tính đạo hàm của f(x) = x⁴ trực tiếp từ định nghĩa (khai triển (x+h)⁴).
2. Dùng quy tắc tích, tính đạo hàm của y = x²·sinx.
3. Dùng chain rule, tính đạo hàm của y = sin(3x+1) và y = (2x−5)³.
4. Chứng minh (arcsin x)' = 1/√(1−x²) bằng kỹ thuật đạo hàm ẩn như đã làm với arctan (đặt y=arcsinx ⟹ x=siny, đạo hàm hai vế, dùng cos²y=1−sin²y=1−x²).
5. Tìm các điểm trên đồ thị y=x³−3x có tiếp tuyến nằm ngang (y'=0).

---

## MỤC E. NGUYÊN HÀM VÀ TÍCH PHÂN

### E.1 Vì sao cần: bài toán ngược của Mục D

Ở Mục D, biết s(t), ta tìm được tốc độ thay đổi s'(t). Bài toán ngược: **biết tốc độ thay đổi, tìm lại hàm gốc** — đây là bài toán rất tự nhiên (ví dụ: biết vận tốc mọi lúc, tìm quãng đường).

**Nguyên hàm** F(x) của f(x) là hàm sao cho F'(x) = f(x). Vì đạo hàm của hằng số bằng 0, nguyên hàm không duy nhất — luôn có thể cộng thêm hằng số C bất kỳ. Ký hiệu ∫f(x)dx = F(x) + C.

**Bảng nguyên hàm** — chính là "đọc ngược" bảng đạo hàm ở Mục D: vì (xⁿ⁺¹/(n+1))' = xⁿ, nên ∫xⁿdx = xⁿ⁺¹/(n+1) + C.

### E.2 Tích phân xác định như diện tích

Bài toán khác, có vẻ không liên quan: tính **diện tích** dưới đồ thị y=f(x), giữa x=a và x=b. Chia đoạn [a,b] thành n dải hẹp bề rộng Δx=(b−a)/n, mỗi dải xấp xỉ bằng một hình chữ nhật cao f(xᵢ), diện tích gần đúng:

S ≈ Σ f(xᵢ)Δx (i=1...n)

Khi n→∞ (dải càng hẹp), tổng này tiến đến giá trị chính xác, gọi là **tích phân xác định**, ký hiệu ∫[a,b] f(x)dx.

### E.3 Định lý cơ bản của giải tích — cầu nối giữa E.1 và E.2

Đây là kết quả quan trọng nhất của toàn bộ giải tích: **diện tích (E.2) tính được bằng nguyên hàm (E.1)**: ∫[a,b] f(x)dx = F(b) − F(a).

**Vì sao đúng (giải thích bản chất, không chỉ công nhận)**: Gọi A(x) là diện tích dưới đồ thị từ a đến x (x thay đổi được — "hàm diện tích tích lũy"). Khi x tăng thêm Δx rất nhỏ, diện tích tăng thêm một dải mỏng, xấp xỉ hình chữ nhật cao f(x) rộng Δx: A(x+Δx) − A(x) ≈ f(x)·Δx. Chia hai vế cho Δx và cho Δx→0, vế trái chính là định nghĩa đạo hàm: **A'(x) = f(x)**. Vậy A(x) là MỘT nguyên hàm của f — tức A(x) = F(x) + C với hằng số C nào đó. Vì A(a)=0 (diện tích từ a đến a), suy C = −F(a), nên A(x) = F(x)−F(a). Tại x=b: A(b) = F(b)−F(a) — đúng là công thức cần chứng minh. ∎

Đây là lý do vì sao "đạo hàm" (tốc độ thay đổi tức thời) và "tích phân" (diện tích, tức tổng cộng dồn) tuy xuất phát từ hai bài toán hoàn toàn khác nhau lại là **hai phép toán ngược nhau** — một sự thật không hiển nhiên chút nào nếu không đi qua lập luận A(x) ở trên.

### E.4 Phép đổi biến

∫f(ax+b)dx = F(ax+b)/a + C — suy trực tiếp từ chain rule ngược: nếu G(x)=F(ax+b), thì G'(x) = F'(ax+b)·a = f(ax+b)·a (theo D.4), nên ∫f(ax+b)·a dx = F(ax+b), chia hai vế cho a được công thức trên.

### E.5 Ví dụ

∫[0,2] x²dx = [x³/3] từ 0 đến 2 = 8/3 − 0 = 8/3.

### E.6 Bài tập tự luyện (Mục E)

1. Tính ∫(3x²−4x+1)dx.
2. Tính ∫[1,3] (2x+1)dx bằng nguyên hàm, sau đó kiểm tra lại bằng công thức diện tích hình thang (vì y=2x+1 là đường thẳng).
3. Tính ∫cos(5x)dx và ∫e^(−2x)dx bằng phép đổi biến (E.4).
4. Nếu F'(x)=f(x) và biết ∫[0,4]f(x)dx=10, F(0)=3, tìm F(4).

---

## MỤC F. KHAI TRIỂN TAYLOR

### F.1 Vì sao cần

Nhiều hàm số (sin, cos, eˣ...) khó tính tay và khó thao tác đại số. Ta muốn **thay gần đúng** chúng bằng đa thức — dễ tính, dễ cộng trừ nhân chia — miễn sai số đủ nhỏ khi x gần một điểm x₀ (thường x₀=0).

### F.2 Xây dựng từng bậc

**Bậc 0**: gần đúng thô nhất, F(x) ≈ F(x₀) — chỉ đúng tại đúng x₀.

**Bậc 1 (đã có sẵn từ Mục D!)**: phương trình tiếp tuyến tại x₀ chính là xấp xỉ tốt hơn:

F(x) ≈ F(x₀) + F'(x₀)(x−x₀)

vì tiếp tuyến "ôm sát" đồ thị gần x₀ hơn hẳn đường ngang.

**Bậc 2**: muốn xấp xỉ tốt hơn nữa, ta cộng thêm một số hạng bậc hai sao cho không chỉ giá trị và độ dốc khớp tại x₀, mà cả **độ cong** (đạo hàm bậc 2) cũng khớp:

F(x) ≈ F(x₀) + F'(x₀)(x−x₀) + a₂(x−x₀)²

Lấy đạo hàm bậc 2 hai vế tại x=x₀: vế trái cho F''(x₀); vế phải, đạo hàm của a₂(x−x₀)² hai lần là 2a₂. Cần 2a₂ = F''(x₀) ⟹ **a₂ = F''(x₀)/2**.

**Tổng quát**: để số hạng bậc n khớp đúng đạo hàm bậc n tại x₀, hệ số phải là F⁽ⁿ⁾(x₀)/n! (n giai thừa xuất hiện vì lấy đạo hàm n lần liên tiếp của (x−x₀)ⁿ cho ra n·(n−1)·...·1 = n!). Đây chính là công thức:

F(x) = F(x₀) + Σ F⁽ⁿ⁾(x₀)(x−x₀)ⁿ / n!

**Bản chất cần nhớ**: khai triển Taylor không phải công thức để học thuộc, mà là **"mỗi số hạng thêm vào là để khớp thêm một đạo hàm bậc cao hơn tại x₀"** — hoàn toàn tự nhiên nếu đã hiểu Mục D.

### F.3 Áp dụng cho các hàm quen thuộc (quanh x₀=0)

Tính các đạo hàm tại 0 rồi thay vào công thức:
- f(x)=sinx: f(0)=0, f'(0)=cos0=1, f''(0)=−sin0=0, f'''(0)=−cos0=−1... ⟹ sinx ≈ x − x³/6 + ... nên với |x|≪1: **sinx ≈ x**.
- f(x)=cosx: f(0)=1, f'(0)=0, f''(0)=−1 ⟹ **cosx ≈ 1 − x²/2**.
- f(x)=eˣ: mọi đạo hàm của eˣ đều là eˣ, tại 0 đều bằng 1 ⟹ eˣ = 1+x+x²/2+... nên **eˣ ≈ 1+x**.
- f(x)=ln(1+x): f(0)=0, f'(x)=1/(1+x) nên f'(0)=1 ⟹ **ln(1+x) ≈ x**.
- f(x)=(1+x)ⁿ: f'(x)=n(1+x)ⁿ⁻¹, f'(0)=n ⟹ **(1+x)ⁿ ≈ 1+nx**.

### F.4 Ví dụ dùng để ước lượng

Tính gần đúng √1.02 không dùng máy tính: viết √1.02 = (1+0.02)^(1/2) ≈ 1 + (1/2)(0.02) = 1.01 (theo công thức (1+x)ⁿ≈1+nx với n=1/2, x=0.02). Giá trị thật: 1.00995... — sai số cực nhỏ.

### F.5 Bài tập tự luyện (Mục F)

1. Viết khai triển Taylor bậc 2 (đến số hạng x²) của cosx quanh x=0, rồi dùng nó ước lượng cos(0.1) (so sánh với giá trị máy tính 0.995).
2. Ước lượng (1.03)⁵ bằng công thức (1+x)ⁿ≈1+nx, không dùng máy tính, rồi so sánh với giá trị chính xác 1.159...
3. Chứng minh eˣ·e⁻ˣ ≈ 1 khi |x|≪1 bằng cách nhân hai khai triển bậc nhất eˣ≈1+x và e⁻ˣ≈1−x.
4. (Nâng cao — chuẩn bị cho Mục G) Viết khai triển Taylor đầy đủ (không dừng ở bậc 1-2, viết dạng tổng Σ) của eˣ, sinx, cosx. Giữ lại kết quả này — sẽ dùng ngay ở mục tiếp theo.

---

## MỤC G. SỐ PHỨC

### G.1 Vì sao cần

Phương trình x²+1=0 vô nghiệm trong tập số thực (vì x² ≥ 0 luôn). Nhưng nếu ta *chấp nhận* tồn tại một "số" i sao cho i²=−1, đại số vẫn hoạt động nhất quán và mở ra công cụ cực mạnh: nó sẽ giúp giải phương trình vi phân (Mục H) và thống nhất lượng giác với hàm mũ.

### G.2 Định nghĩa và các phép toán

z = a + bi (a: phần thực, b: phần ảo). Cộng, trừ như vector 2 chiều (a,b). Nhân: (a+bi)(c+di) = ac + adi + bci + bdi² = (ac−bd) + (ad+bc)i (dùng i²=−1).

**Biểu diễn hình học**: z=a+bi ứng với điểm (a,b) trên mặt phẳng — giống hệt vector! **Môđun** |z|=√(a²+b²) (độ dài vector), **acgumen** φ=arg z (góc so với trục thực). **Dạng lượng giác**: z = |z|(cosφ + i sinφ). **Số phức liên hợp** z̄ = a−bi (đối xứng qua trục thực); |z|² = z·z̄ = a²+b².

### G.3 Nhân hai số phức dạng lượng giác — dùng lại Mục B!

Cho z₁=r₁(cosα+isinα), z₂=r₂(cosβ+isinβ). Nhân trực tiếp:

z₁z₂ = r₁r₂[(cosα cosβ − sinα sinβ) + i(sinα cosβ + cosα sinβ)]

Hai ngoặc đúng bằng cos(α+β) và sin(α+β) theo công thức cộng góc (Mục B)! Vậy:

**z₁z₂ = r₁r₂[cos(α+β) + i sin(α+β)]**

Kết luận đẹp: **nhân số phức = nhân môđun, cộng acgumen**. Phép nhân với số phức chính là phép "vừa co giãn vừa xoay" trong mặt phẳng.

### G.4 Công thức Euler — dùng lại Mục F!

Ở bài tập F.5.4, học sinh đã viết khai triển Taylor đầy đủ:

eˣ = 1 + x + x²/2! + x³/3! + x⁴/4! + ...
cosφ = 1 − φ²/2! + φ⁴/4! − ...
sinφ = φ − φ³/3! + φ⁵/5! − ...

Bây giờ, **thay hình thức** x = iφ vào khai triển của eˣ (chấp nhận công thức vẫn dùng được cho số phức):

e^(iφ) = 1 + iφ + (iφ)²/2! + (iφ)³/3! + (iφ)⁴/4! + ...

Dùng i²=−1, i³=−i, i⁴=1, i⁵=i... (chu kỳ 4), tách các số hạng thực và ảo:

e^(iφ) = [1 − φ²/2! + φ⁴/4! − ...] + i[φ − φ³/3! + φ⁵/5! − ...]

Hai ngoặc vuông chính xác là khai triển của cosφ và sinφ ở trên! Vậy:

**e^(iφ) = cos φ + i sin φ** (công thức Euler)

Đây là một trong những đẳng thức đẹp nhất của toán học — nó không phải định nghĩa tùy tiện, mà là hệ quả tất yếu khi ta yêu cầu khai triển Taylor của eˣ vẫn đúng khi x là số ảo. Nó thống nhất Mục F (Taylor) và Mục B (lượng giác) làm một.

**Hệ quả trực tiếp**: mọi số phức viết được z = |z|e^(iφ) — và quy tắc nhân ở G.3 (nhân môđun cộng góc) giờ chỉ là quy tắc quen thuộc eᵃ·eᵇ=eᵃ⁺ᵇ áp dụng cho số mũ ảo — không cần nhớ riêng nữa.

Từ công thức Euler còn suy ra được: cosφ = (e^(iφ)+e^(−iφ))/2, sinφ = (e^(iφ)−e^(−iφ))/2i (cộng/trừ công thức Euler cho φ và −φ, giải ra cos, sin).

### G.5 Ví dụ

Tính (1+i)⁴. Viết 1+i dưới dạng lượng giác: |1+i|=√2, góc 45°=π/4. Vậy (1+i)⁴ = (√2)⁴·[cos(4·π/4)+isin(4·π/4)] = 4·[cosπ+isinπ] = 4·(−1+0i) = −4. (Thử nhân trực tiếp (1+i)² = 2i, rồi (2i)²=−4 — khớp, và cách dùng dạng lượng giác nhanh hơn nhiều với số mũ lớn.)

### G.6 Bài tập tự luyện (Mục G)

1. Viết z = √3 + i dưới dạng lượng giác và dạng e^(iφ).
2. Tính (1−i)⁶ bằng dạng lượng giác.
3. Dùng công thức Euler, chứng minh lại công thức cos(α+β) bằng cách so sánh phần thực của e^(i(α+β)) với phần thực của e^(iα)·e^(iβ) = e^(iα+iβ). (Đây là con đường ngược lại của Mục B — cho thấy B và G thực ra là hai mặt của cùng một sự thật.)
4. Giải phương trình z² = i (viết i dưới dạng lượng giác trước: môđun 1, góc π/2, rồi "lấy căn bậc hai" bằng cách chia đôi góc — chú ý có 2 nghiệm).

---

## MỤC H. PHƯƠNG TRÌNH VI PHÂN TUYẾN TÍNH HỆ SỐ HẰNG

### H.1 Vì sao cần

Rất nhiều hiện tượng (không chỉ vật lý) được mô tả bởi phương trình liên hệ một hàm y(x) với chính đạo hàm của nó, ví dụ: ay'' + by' + cy = 0. Đây gọi là **phương trình vi phân** — ẩn số không phải một con số mà là **cả một hàm số**.

### H.2 Ý tưởng giải: đưa về đại số

Ta *đoán* nghiệm có dạng y = e^(λx) (hợp lý vì đạo hàm của hàm mũ tỉ lệ với chính nó — Mục D.6 — nên khi thế vào phương trình, mọi số hạng đều còn thừa số chung e^(λx)). Tính y'=λe^(λx), y''=λ²e^(λx), thế vào ay''+by'+cy=0:

(aλ² + bλ + c)e^(λx) = 0

Vì e^(λx) không bao giờ bằng 0, ta cần **aλ² + bλ + c = 0** — đây là phương trình bậc hai bình thường (**phương trình đặc trưng**), giải bằng denta như đã học! Vậy: **giải phương trình vi phân bậc 2 quy về giải một phương trình bậc hai đại số** — đây là toàn bộ "phép màu" của phương pháp.

### H.3 Trường hợp hai nghiệm thực phân biệt λ₁≠λ₂

Nghiệm tổng quát: y = Ae^(λ₁x) + Be^(λ₂x) (A, B là hằng số tùy ý, xác định từ điều kiện đầu bài — vì tổng hai nghiệm của phương trình tuyến tính vẫn là nghiệm, kiểm tra trực tiếp bằng cách thế vào).

### H.4 Trường hợp nghiệm phức — dùng lại Mục G!

Nếu denta<0, phương trình đặc trưng có nghiệm phức λ = γ ± iω (γ, ω thực). Nghiệm hình thức vẫn là y = Ae^((γ+iω)x) + Be^((γ−iω)x), nhưng ta muốn **y thực** (vì y mô tả đại lượng thực). Viết lại dùng công thức Euler (G.4):

e^((γ+iω)x) = e^(γx)·e^(iωx) = e^(γx)[cos(ωx) + i sin(ωx)]

Tổ hợp Ae^((γ+iω)x) + Be^((γ−iω)x), sau khi khai triển bằng Euler và **chọn A, B là số phức liên hợp nhau** để phần ảo triệt tiêu (chi tiết đại số dành cho học sinh giỏi tự kiểm chứng), thu được nghiệm thực:

**y = Ce^(γx) sin(ωx + φ₀)**

với C, φ₀ là hai hằng số thực xác định từ điều kiện đầu (thay cho hai hằng số phức A, B ban đầu — đúng vẫn là 2 bậc tự do). Đây chính là dao động (sin) có biên độ tăng/giảm theo hàm mũ (e^(γx)) — kết quả sẽ dùng trực tiếp ở Phần Dao động.

**Điểm mấu chốt sư phạm**: số phức ở đây không phải "trò chơi trừu tượng" — nó là công cụ trung gian giúp giải một phương trình có nghiệm cuối cùng hoàn toàn thực và có ý nghĩa vật lý rõ ràng (dao động tắt dần/tăng dần).

### H.5 Bài tập tự luyện (Mục H)

1. Giải phương trình y'' − 5y' + 6y = 0 (tìm phương trình đặc trưng, giải denta, viết nghiệm tổng quát).
2. Giải phương trình y'' + 4y = 0 (chú ý: nghiệm đặc trưng thuần ảo λ=±2i, tức γ=0 — viết nghiệm dạng sin thuần túy không tắt dần).
3. Giải phương trình y'' + 2y' + 5y = 0 (nghiệm phức có cả phần thực và ảo — dạng dao động tắt dần).

---

## MỤC I. PHƯƠNG PHÁP NHIỄU LOẠN (giới thiệu ngắn)

Khi một bài toán gần giống một bài toán đã biết cách giải, nhưng có thêm một số hạng "nhiễu loạn" nhỏ, ta có thể: (1) giải bài toán gốc (bỏ qua nhiễu loạn) làm **gần đúng bậc 0**; (2) dùng nghiệm bậc 0 đó thay vào phần nhiễu loạn để tính **hiệu chỉnh bậc 1**; (3) lặp lại nếu cần độ chính xác cao hơn. Đây thực chất là áp dụng liên tiếp ý tưởng khai triển Taylor (Mục F) — mỗi bước hiệu chỉnh giống như thêm một số hạng bậc cao hơn vào xấp xỉ.

---

## MỤC J. HAI PHƯƠNG PHÁP SỐ CƠ BẢN

### J.1 Phương pháp Newton tìm nghiệm — dùng lại Mục D và F!

Muốn giải f(x)=0 khi không có công thức đóng. Ý tưởng: bắt đầu từ một điểm đoán xₙ, dùng xấp xỉ tuyến tính Taylor bậc 1 (Mục F.2) quanh xₙ:

f(x) ≈ f(xₙ) + f'(xₙ)(x−xₙ)

Tìm nghiệm của đường thẳng xấp xỉ này (dễ hơn nhiều so với f(x) gốc): đặt vế phải = 0, giải ra x:

**xₙ₊₁ = xₙ − f(xₙ)/f'(xₙ)**

Về hình học: xₙ₊₁ là giao điểm của tiếp tuyến tại xₙ với trục hoành. Lặp lại nhiều lần, xₙ hội tụ rất nhanh về nghiệm thật (nếu điểm xuất phát đủ gần).

### J.2 Quy tắc hình thang tính tích phân gần đúng — dùng lại Mục E!

Thay vì xấp xỉ mỗi dải nhỏ bằng hình chữ nhật (Mục E.2), xấp xỉ bằng **hình thang** (nối hai điểm f(xᵢ), f(xᵢ₊₁) bằng đoạn thẳng thay vì đường ngang) — chính xác hơn hẳn với cùng số dải. Diện tích hình thang thứ i: (f(xᵢ)+f(xᵢ₊₁))/2 · Δx. Cộng tất cả các dải, mỗi điểm trong (không phải đầu mút) xuất hiện trong 2 hình thang liền kề nên có hệ số 2:

∫[a,b] f(x)dx ≈ (b−a)/2n · [f(x₀) + 2f(x₁) + 2f(x₂) + ... + 2f(xₙ₋₁) + f(xₙ)]

### J.3 Bài tập tự luyện (Mục J)

1. Dùng phương pháp Newton, tìm gần đúng √5 bằng cách giải f(x)=x²−5=0, bắt đầu từ x₀=2, thực hiện 2 bước lặp.
2. Dùng quy tắc hình thang với n=4 dải, ước lượng ∫[0,2] x²dx, so sánh với giá trị chính xác 8/3 (đã tính ở bài E.6 ví dụ).

---

## MỤC K. ĐẠO HÀM VÀ TÍCH PHÂN CỦA VECTOR (ghi chú ngắn)

Nếu **r**(t) = (x(t), y(t)) là vector phụ thuộc thời gian, đạo hàm/tích phân của nó chỉ đơn giản là **làm riêng cho từng thành phần**: **r**'(t) = (x'(t), y'(t)). Điều này hợp lý vì hệ tọa độ (ex, ey) không đổi theo t, nên phép lấy giới hạn ở Mục D áp dụng độc lập cho từng trục. Đây là cầu nối trực tiếp giữa Mục A (vector) và Mục D–E (đạo hàm–tích phân), sẽ dùng ngay khi định nghĩa vận tốc, gia tốc dưới dạng vector ở Phần II.

---

## TỔNG KẾT PHẦN I

Sơ đồ phụ thuộc giữa các mục (mũi tên: "cần đến"):

A (Vector) → B (Lượng giác cộng góc) → G.3 (nhân số phức)
A → C (Hình học tam giác/đường tròn)
D (Đạo hàm) → E (Tích phân) → J.2 (hình thang)
D → F (Taylor) → G.4 (Euler) 
B + F → G (Số phức hoàn chỉnh)
D + G → H (Phương trình vi phân)
D + F → J.1 (Newton)
A + D + E → K (vector theo thời gian)

Học sinh **hiểu bản chất** khi có thể, không nhìn tài liệu, tự suy lại được: vì sao định lý cos là Pythagoras mở rộng; vì sao (xⁿ)'=nxⁿ⁻¹; vì sao đạo hàm và tích phân là hai phép ngược nhau; vì sao e^(iφ)=cosφ+isinφ; vì sao giải phương trình vi phân quy về giải phương trình đại số. Nếu các em làm được điều này, các em không "nhớ công thức" — các em **sở hữu** công thức, và có thể tái tạo lại bất cứ lúc nào, kể cả khi quên.

---

## ĐÁP SỐ BÀI TẬP (tóm tắt)

**Mục A**: 1. BC²=25+49−2·5·7·cos60°=74−35=39, BC=√39. 3. **a**×**b**=(2·6−3·5, 3·4−1·6, 1·5−2·4)=(−3,6,−3). 4. S=½|4·3−0·1|=6.

**Mục B**: 2. cos(α+β)=(4/5)(5/13)−(3/5)(12/13)=20/65−36/65=−16/65 (chú ý cosα=4/5, sinβ=12/13 tính từ Pythagoras).

**Mục D**: 1. 4x³. 2. 2x·sinx+x²cosx. 3. 3cos(3x+1); 6(2x−5)². 5. x=±1.

**Mục E**: 1. x³−2x²+x+C. 3. sin(5x)/5+C; −e^(−2x)/2+C. 4. F(4)=13.

**Mục F**: 1. cos(0.1)≈1−0.005=0.995. 2. (1.03)⁵≈1+5(0.03)=1.15.

**Mục G**: 1. z=2(cos30°+isin30°)=2e^(iπ/6). 2. (1−i)⁶: |1−i|=√2, góc−45°; (√2)⁶[cos(−270°)+isin(−270°)]=8[0+i·1]=8i. 4. z=cos45°+isin45° hoặc z=cos225°+isin225° (hai nghiệm đối nhau).

**Mục H**: 1. λ=2,3 ⟹ y=Ae^(2x)+Be^(3x). 2. λ=±2i ⟹ y=Csin(2x+φ₀). 3. λ=−1±2i ⟹ y=Ce^(−x)sin(2x+φ₀).

**Mục J**: 1. x₁=2.25, x₂≈2.2361 (rất gần √5=2.2360679...).

---

*Phần II (Động học) và các phần tiếp theo sẽ chỉ cần trích dẫn lại các mục A, D, E, F ở trên — không cần dạy lại toán từ đầu. Đề nghị dành ít nhất 3-4 tuần để học sinh làm chủ Phần I trước khi sang Phần II.*
