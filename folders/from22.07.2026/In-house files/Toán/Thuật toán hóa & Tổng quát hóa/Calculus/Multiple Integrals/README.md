https://chat.deepseek.com/share/u2s34wosozw0f0x2pb

# TÍCH PHÂN BỘI (MULTIPLE INTEGRALS) TRONG VẬT LÝ HSGQG

> Tài liệu này được viết theo đúng tinh thần triết lý trong "Thảo luận lớn về Cách giải Đề thi HSGQG Vật Lý": không dạy "dạng bài", mà dạy **First Principles + Điều kiện Cần/Đủ + Thuật toán xử lý CHỖ**. Tích phân bội ở đây được xem như một **CÔNG CỤ (ℓ)** trong thư viện công cụ của bạn, với `Dom(ℓ)`, `Pre(ℓ)`, `Post(ℓ)` được định nghĩa rõ ràng.

---

## PHẦN 0: TẠI SAO CẦN TÍCH PHÂN BỘI — TRỰC GIÁC TRƯỚC

### 0.1. Vấn đề gốc

Rất nhiều công thức Vật Lý phổ thông — ví dụ $m = \rho V$, $I = \frac{1}{2}mr^2$ (đĩa tròn), $E = \frac{kQ}{r^2}$ — chỉ đúng khi vật là **đều, đối xứng cao, hoặc là điểm**. Nhưng vật thật thì:

- Khối lượng riêng có thể thay đổi theo vị trí: $\rho(x,y,z)$.
- Điện tích phân bố trên một mặt, một khối, không phải một điểm.
- Hình dạng vật rắn không đơn giản (đĩa, cầu, trụ, nêm, vành không đều...).

**Insight cốt lõi:** Khi một đại lượng vật lý (khối lượng, điện tích, mô-men quán tính, điện trường, lực hấp dẫn, công, thông lượng...) được **sinh ra bởi một mật độ (density) trải trên một miền nhiều chiều**, ta không thể cộng "thô" được nữa — ta phải **chia nhỏ miền thành vô số phần tử vi phân, tính đóng góp của từng phần tử, rồi lấy tổng (lấy giới hạn tổng Riemann)**. Đó chính là bản chất của tích phân bội.

> Tích phân bội **không phải là một chủ đề toán học tách biệt** — nó là **phép tổng quát hóa phép cộng** khi đại lượng cần cộng trải trên 2 hoặc 3 chiều không gian.

### 0.2. Tư duy diễn dịch (First Principles)

Mọi công thức "mẹo" bạn học (như $I_{đĩa} = \frac{1}{2}mr^2$) đều là **hệ quả** của một tích phân bội tổng quát hơn:

$$I = \iiint_V r_\perp^2 \, \rho(\vec{r}) \, dV$$

Khi $\rho$ = hằng số và hình dạng đối xứng cao, tích phân này "sụp" xuống thành công thức đóng (closed-form) quen thuộc. Khi vật không đều hoặc hình dạng lạ, bạn **bắt buộc phải quay về tích phân gốc** — đây chính là lý do đề thi HSGQG/VPHO/IPHO rất thích ra các bài "phá vỡ" công thức mẹo.

---

## PHẦN 1: NỀN TẢNG TOÁN HỌC (Pre-requisite)

### 1.1. Định nghĩa (First Principles)

**Tích phân hai lớp (double integral)** trên miền phẳng $D \subset \mathbb{R}^2$:

$$\iint_D f(x,y)\, dA = \lim_{n\to\infty} \sum_{i=1}^{n} f(x_i^*, y_i^*)\, \Delta A_i$$

Tức là: chia $D$ thành $n$ ô diện tích $\Delta A_i$ rất nhỏ, nhân giá trị hàm tại mỗi ô với diện tích ô đó, cộng lại, rồi cho $n \to \infty$.

**Tích phân ba lớp (triple integral)** trên miền khối $V \subset \mathbb{R}^3$:

$$\iiint_V f(x,y,z)\, dV = \lim_{n\to\infty} \sum_{i=1}^{n} f(x_i^*, y_i^*, z_i^*)\, \Delta V_i$$

**Điều kiện cần để tích phân tồn tại (well-posedness)**: $f$ liên tục (hoặc liên tục từng khúc) trên miền $D$ (hoặc $V$) đóng và bị chặn.

### 1.2. Định lý Fubini — "CÔNG CỤ" biến tích phân bội thành tích phân lặp

**Phát biểu**: Nếu $f$ liên tục trên hình chữ nhật/hộp $R$, thì:

$$\iint_R f(x,y)\, dA = \int_a^b \left( \int_c^d f(x,y)\, dy \right) dx = \int_c^d \left( \int_a^b f(x,y)\, dx \right) dy$$

**Ý nghĩa thực chiến**: Đây là cách DUY NHẤT để tính tích phân bội bằng tay — biến nó thành **chuỗi các tích phân một biến lồng nhau**, tính từ trong ra ngoài.

**Pre(Fubini)**: Miền tích phân phải được mô tả được bằng cận trên-dưới rõ ràng cho từng biến (xem Phần 3). Nếu miền $D$ không phải hình chữ nhật, ta phải viết cận của biến trong dưới dạng **hàm của biến ngoài**.

### 1.3. Các hệ tọa độ và Jacobian — CÔNG CỤ đổi biến

Đây là phần **quan trọng nhất** về mặt kỹ thuật. Chọn sai hệ tọa độ = tự làm khó mình.

#### a) Tọa độ cực (2D): $(x,y) \to (r,\theta)$

$$x = r\cos\theta,\quad y = r\sin\theta, \qquad dA = r\, dr\, d\theta$$

**Pre**: Dùng khi miền có **đối xứng trụ/tròn quanh gốc tọa độ** (đĩa, vành, hình quạt).

#### b) Tọa độ trụ (3D): $(x,y,z) \to (r,\theta,z)$

$$x = r\cos\theta,\ y = r\sin\theta,\ z = z, \qquad dV = r\, dr\, d\theta\, dz$$

**Pre**: Dùng khi vật có **trục đối xứng** (hình trụ, dây dẫn thẳng dài, cuộn dây solenoid).

#### c) Tọa độ cầu (3D): $(x,y,z) \to (\rho,\theta,\phi)$

$$x = \rho\sin\phi\cos\theta,\ y = \rho\sin\phi\sin\theta,\ z = \rho\cos\phi, \qquad dV = \rho^2 \sin\phi\, d\rho\, d\phi\, d\theta$$

(quy ước: $\phi$ là góc tính từ trục $z$, $\theta$ là góc phương vị — **LƯU Ý: một số sách Vật Lý đảo ký hiệu $\theta \leftrightarrow \phi$ so với sách Toán, luôn kiểm tra lại định nghĩa trước khi dùng!**)

**Pre**: Dùng khi vật có **đối xứng tâm** (quả cầu, vỏ cầu).

#### d) Jacobian tổng quát — khi đổi biến bất kỳ $(x,y) \to (u,v)$

$$dA = \left| \frac{\partial(x,y)}{\partial(u,v)} \right| du\, dv, \qquad \frac{\partial(x,y)}{\partial(u,v)} = \det\begin{pmatrix} \partial x/\partial u & \partial x/\partial v \\ \partial y/\partial u & \partial y/\partial v \end{pmatrix}$$

**Nguyên tắc chuyển tầng**: Trước khi học các hệ tọa độ "có sẵn" (cực, trụ, cầu), hãy hiểu rằng chúng chỉ là **trường hợp riêng của phép đổi biến tổng quát qua Jacobian**. Nắm Jacobian → bạn có thể tự chế hệ tọa độ phù hợp cho bài lạ (ví dụ tọa độ elip, tọa độ parabol).

---

## PHẦN 2: ĐIỀU KIỆN CẦN & ĐỦ — KHI NÀO PHẢI DÙNG TÍCH PHÂN BỘI

Đây là phần giải quyết **Vấn đề tìm kiếm (Search Problem)** theo đúng tinh thần tài liệu gốc: tìm **CHỖ** mà công cụ "Tích phân bội" cần được áp dụng.

### 2.1. Điều kiện CẦN (Necessary — thiếu thì chắc chắn không cần tích phân bội)

Bài toán phải có **ít nhất một đại lượng trải liên tục trên miền ≥ 2 chiều** mà bạn cần "cộng dồn" đóng góp. Các tín hiệu nhận diện trong đề bài:

- Đề cho **mật độ** (khối lượng riêng $\rho(\vec r)$, mật độ điện tích mặt $\sigma$, mật độ điện tích khối $\rho_q$, mật độ dòng $\vec J$) **là hàm của vị trí**, không phải hằng số.
- Đề hỏi về đại lượng tổng: khối lượng, điện tích, mô-men quán tính, mô-men lưỡng cực, trọng tâm, điện trường/từ trường tại một điểm do một vật **có kích thước** (không phải điện tích điểm) gây ra, công của lực biến thiên, thông lượng qua một mặt không phẳng, lực hút hấp dẫn giữa hai vật có kích thước.
- Hình dạng vật **không đối xứng đủ cao** để dùng định luật Gauss/Ampere "tắt" (xem 2.3).

### 2.2. Điều kiện ĐỦ (Sufficient — có precondition này thì chắc chắn thiết lập được)

Bạn **chắc chắn thiết lập được** tích phân bội khi và chỉ khi bạn xác định được **đầy đủ 4 thành phần**:

1. **Phần tử vi phân** $dm$, $dq$, $dI$, $dE$,... — biểu thức cho đóng góp của MỘT phần tử nhỏ của vật.
2. **Hệ tọa độ** mô tả vị trí của phần tử đó, phù hợp với đối xứng của vật (Phần 1.3).
3. **Miền lấy tích phân** $D$ hoặc $V$ — biên của vật trong hệ tọa độ đã chọn, viết được thành cận trên/dưới tường minh.
4. **Hàm cần lấy tổng** $f$ tại vị trí phần tử đó (ví dụ $r_\perp^2$ cho mô-men quán tính).

**Nếu thiếu bất kỳ thành phần nào trong 4 cái trên → bạn CHƯA thể viết tích phân, phải quay lại mô hình hóa.**

### 2.3. Khi nào KHÔNG NÊN "brute-force" bằng tích phân bội

Đây là "điểm neo" bẫy thường gặp: đề cho vật có đối xứng rất cao (cầu, trụ, phẳng vô hạn) để **gài bạn đi tích phân trực tiếp trong khi có công cụ mạnh hơn**:

- Đối xứng cầu/trụ/phẳng cho điện trường, trọng trường → ưu tiên xét **Định luật Gauss** trước (biến tích phân mặt thành phép nhân đại số).
- Vật đối xứng cho mô-men quán tính đã có sẵn qua **Định lý trục song song (Parallel Axis)** hoặc **Định lý cộng trục vuông góc (Perpendicular Axis, chỉ cho vật phẳng)** → tránh tích phân lại từ đầu nếu có thể lắp ghép từ các mảnh đã biết.

**Nguyên tắc chọn công cụ**: Luôn luôn kiểm tra đối xứng trước — nếu đối xứng đủ cao và công cụ "tắt" áp dụng được, dùng nó. Tích phân bội là công cụ **tổng quát nhất nhưng tốn thời gian nhất** — chỉ dùng khi các công cụ "tắt" (Gauss, định lý trục,...) không thỏa Pre của chúng.

---

## PHẦN 3: "THUẬT TOÁN" THIẾT LẬP TÍCH PHÂN BỘI TRONG VẬT LÝ

Đây là quy trình **máy móc**, giảm tối thiểu phụ thuộc trực giác, áp dụng được cho hầu hết bài HSGQG.

### Bước 1 — Xác định đại lượng vi phân gốc (Isolate the differential element)

Viết biểu thức cho phần tử vi phân **cơ bản nhất** liên quan đến mật độ đề cho. Ví dụ:

- $dm = \rho\, dV$ (khối), $dm = \sigma\, dA$ (mặt), $dm = \lambda\, dl$ (dây/thanh).
- $dq = \sigma\, dA$, $dq = \rho_q\, dV$, $dq = \lambda\, dl$.

### Bước 2 — Chọn hệ tọa độ theo đối xứng của VẬT (không phải theo thói quen)

Quy tắc chọn (Pre của từng hệ tọa độ, xem 1.3):

| Hình dạng vật | Hệ tọa độ nên chọn |
|---|---|
| Thanh thẳng, dây thẳng | Descartes 1D dọc theo thanh |
| Vành tròn, đĩa tròn, hình quạt | Cực (2D) |
| Trụ, ống trụ, dây dài | Trụ (3D) |
| Cầu, vỏ cầu | Cầu (3D) |
| Hình dạng bất kỳ không đối xứng | Descartes, hoặc tự xây hệ tọa độ phù hợp qua Jacobian |

### Bước 3 — Viết biên của vật trong hệ tọa độ đã chọn (xác định miền $D$/$V$)

Đây là bước hay gây lỗi nhất. Nguyên tắc:

- **Cận của biến NGOÀI CÙNG** (được lấy tích phân sau cùng) phải là **hằng số**.
- **Cận của các biến TRONG** có thể là hàm của các biến ngoài nó.
- Vẽ hình, xác định "quét" biến nào trước — thường quét biến có khoảng giá trị **phụ thuộc vào biến còn lại** trước (tích phân trong), biến độc lập sau (tích phân ngoài).

**Kỹ thuật kiểm tra nhanh**: Thử với 1-2 giá trị biên cụ thể, xem có khớp hình học không (dimensional/sanity check).

### Bước 4 — Viết hàm cần lấy tổng tại vị trí phần tử (đưa về CÙNG hệ tọa độ với bước 2)

Ví dụ: với mô-men quán tính quanh trục $z$, hàm cần lấy tổng là $r_\perp^2$ — khoảng cách vuông góc từ phần tử đến trục quay, **viết theo hệ tọa độ đã chọn**, KHÔNG được lẫn hệ tọa độ khác.

**Bẫy thường gặp**: Trộn lẫn biến tích phân của các hệ tọa độ khác nhau trong cùng một tích phân (ví dụ dùng $r$ của tọa độ cầu cho field point, nhưng $r'$ của tọa độ trụ cho source point, mà không phân biệt rõ) — đây là lỗi kinh điển khi tính điện trường/trọng trường gây bởi vật có kích thước.

### Bước 5 — Ráp tích phân và áp dụng Fubini

$$\text{Đại lượng cần tìm} = \iint_D \text{hoặc} \iiint_V (\text{hàm Bước 4}) \times (\text{phần tử Bước 1, viết lại theo hệ tọa độ}) $$

Chuyển thành tích phân lặp theo đúng thứ tự biên đã xác định ở Bước 3.

### Bước 6 — Kiểm tra tính hợp lệ của kết quả (Derivation Validity — Phần 7 Model Specification)

- **Phân tích thứ nguyên**: Kết quả có đúng đơn vị không?
- **Giới hạn đặc biệt**: Cho tham số về 0 hoặc vô cùng, kết quả có khớp với trường hợp đã biết không? (ví dụ: cho bán kính trong của vành $\to 0$, công thức có trở về công thức đĩa đặc không?)
- **Đối xứng**: Kết quả có tôn trọng đối xứng của bài toán không? (ví dụ điện trường do vật đối xứng trụ phải vuông góc với trục, không có thành phần dọc trục nếu vô hạn dài)

---

## PHẦN 4: CÁC BẤT BIẾN (INVARIANTS) CẦN KHẮC CỐT GHI TÂM

Đây là những điều **không đổi dù bài toán biến tấu thế nào** — chúng chính là "cốt lõi" theo First Principles:

1. **Nguyên lý chồng chất (Superposition)**: Mọi tích phân bội trong Vật Lý THỰC CHẤT là áp dụng nguyên lý chồng chất ở dạng liên tục — tổng vô hạn các đóng góp vi phân độc lập. Đây là lý do tích phân bội áp dụng được cho khối lượng, điện tích, lực hấp dẫn, điện trường (tuyến tính) nhưng **KHÔNG áp dụng trực tiếp được cho các đại lượng phi tuyến** (ví dụ không thể tích phân "thế năng hấp dẫn của hệ" bằng cách cộng thế năng từng cặp phần tử một cách ngây thơ — phải cẩn thận đếm đôi/không đếm đôi).

2. **Tính cộng được (Additivity) theo miền**: $\iint_{D_1 \cup D_2} f\, dA = \iint_{D_1} f\, dA + \iint_{D_2} f\, dA$ nếu $D_1, D_2$ không giao nhau. → Đây là cơ sở cho kỹ thuật **"chia để trị"**: vật hình dạng phức tạp = tổng/hiệu của các vật hình dạng đơn giản (ví dụ: vành = đĩa lớn − đĩa nhỏ; tích phân cũng cộng/trừ theo).

3. **Jacobian luôn dương (giá trị tuyệt đối)**: $dA, dV$ luôn dương bất kể hướng đổi biến — quên dấu trị tuyệt đối là lỗi rất phổ biến khi đổi biến.

4. **Thứ tự lấy tích phân có thể đổi (Fubini) NHƯNG cận phải đổi theo tương ứng** — đổi thứ tự tích phân mà giữ nguyên cận là lỗi nghiêm trọng.

5. **Đối xứng của bài toán quyết định đối xứng của kết quả** — nếu nguồn đối xứng cầu thì field cũng phải đối xứng cầu (chỉ phụ thuộc $\rho$, hướng theo $\hat\rho$). Đây là bất biến dùng để **kiểm tra ngược (sanity check)** kết quả tích phân.

---

## PHẦN 5: ỨNG DỤNG VẬT LÝ CHI TIẾT (Modular Library — Thư viện precondition)

### 5.1. Khối lượng và khối tâm

$$m = \iiint_V \rho\, dV, \qquad \vec{r}_{cm} = \frac{1}{m}\iiint_V \vec{r}\, \rho\, dV$$

**Pre**: Biết $\rho(\vec r)$ (có thể hằng số hoặc hàm vị trí).

**Mẹo giảm bậc**: Nếu vật đối xứng qua một mặt phẳng/trục/tâm, khối tâm tự động nằm trên đó theo đối xứng — **không cần tích phân cho các thành phần đó**, chỉ tích phân cho thành phần không đối xứng.

### 5.2. Mô-men quán tính

$$I = \iiint_V r_\perp^2\, \rho\, dV$$

**Thư viện kết quả chuẩn (để kiểm tra/kiểm tra giới hạn, KHÔNG học thuộc để thay tích phân khi vật không đều)**:

- Thanh đồng chất dài $L$, quanh trục qua giữa, vuông góc thanh: $I = \frac{1}{12}mL^2$
- Đĩa đặc đồng chất bán kính $R$, quanh trục đối xứng: $I = \frac{1}{2}mR^2$
- Vành mỏng bán kính $R$: $I = mR^2$
- Cầu đặc đồng chất: $I = \frac{2}{5}mR^2$
- Vỏ cầu mỏng: $I = \frac{2}{3}mR^2$

**Định lý trục song song (Steiner)**: $I = I_{cm} + md^2$ — dùng để **tránh tích phân lại** khi trục quay không qua khối tâm, với điều kiện đủ là bạn đã biết $I_{cm}$.

### 5.3. Điện trường do vật tích điện có kích thước (bài kinh điển HSGQG)

$$\vec{E}(\vec{r}) = \frac{1}{4\pi\varepsilon_0} \iiint_{V'} \frac{(\vec{r} - \vec{r}')}{|\vec{r} - \vec{r}'|^3}\, \rho_q(\vec{r}')\, dV'$$

**Lưu ý CỰC KỲ QUAN TRỌNG**: $\vec r$ (điểm khảo sát/field point) và $\vec r'$ (điểm nguồn/source point, biến tích phân) là **hai điểm khác nhau** — đây là nguồn lỗi số 1 khi học sinh mới làm quen. Luôn vẽ hình, đặt tên rõ ràng, không bao giờ nhầm lẫn.

**Quy trình giảm bậc cho bài thi** (ví dụ: đĩa tích điện đều, tính $E$ trên trục):

1. Chia đĩa thành các **vành tròn** bán kính $r'$, bề dày $dr'$ → mỗi vành có $dq = \sigma \cdot 2\pi r' dr'$ (đã "tích phân sẵn" theo góc nhờ đối xứng — đây là mẹo giảm từ tích phân 2 lớp xuống 1 lớp).
2. Điện trường do một vành trên trục đã là công thức đã biết (hoặc tự suy từ First Principles bằng đối xứng: thành phần vuông góc trục triệt tiêu).
3. Tích phân theo $r'$ từ $0$ đến $R$.

**Đây chính là minh họa cho "Tư duy Lắp ghép" (Modular Thinking)**: không nhất thiết phải viết tích phân 2 lớp đầy đủ nếu một chiều đã "cho không" nhờ đối xứng — hãy tận dụng đối xứng để **hạ bậc tích phân trước khi brute-force**.

### 5.4. Thông lượng và Định luật Gauss (khi nào tích phân mặt "sụp" thành đại số)

$$\Phi_E = \oiint_S \vec{E}\cdot d\vec{A} = \frac{Q_{in}}{\varepsilon_0}$$

**Pre để "tắt" tích phân mặt thành phép nhân**: Phải chọn được **mặt Gauss** sao cho trên đó $|\vec E|$ không đổi và $\vec E \parallel d\vec A$ (hoặc vuông góc, khi đó không đóng góp). Điều này CHỈ xảy ra khi vật nguồn có đối xứng cầu/trụ/phẳng **và** bạn chọn mặt Gauss cùng dạng đối xứng đó.

**Nếu Pre này không thỏa** (vật không đối xứng đủ cao) → phải quay về tích phân bội trực tiếp như 5.3.

### 5.5. Công của lực biến thiên trên đường cong / qua miền 2D-3D

$$W = \int_C \vec{F}\cdot d\vec{l} \quad (\text{tích phân đường, không phải tích phân bội — phân biệt rõ!})$$

Lưu ý: tích phân đường (line integral) **khác** tích phân bội — nhiều học sinh nhầm lẫn khi bài có cả hai loại trong cùng đề (ví dụ: công của điện trường do vật tích điện có kích thước → cần tích phân bội để tìm $\vec E$ trước, sau đó tích phân đường để tìm $W$).

---

## PHẦN 6: CÁC BẪY THƯỜNG GẶP TRONG ĐỀ THI

1. **Nhầm field point và source point** khi tính trường gây bởi vật có kích thước (5.3).
2. **Không hạ bậc tích phân** dù đối xứng cho phép — brute-force tích phân 2-3 lớp trong khi chỉ cần 1 lớp (tốn thời gian phòng thi).
3. **Cận tích phân sai thứ tự** khi đổi Fubini — đặc biệt khi miền không phải hình chữ nhật/hộp.
4. **Quên Jacobian** hoặc quên trị tuyệt đối khi đổi biến.
5. **Dùng công thức "mẹo" đóng (closed-form)** (như $I = \frac{1}{2}mR^2$) cho vật **không đều** $\rho \neq$ hằng số — đây là bẫy kinh điển, đề sẽ cho $\rho(r)$ biến thiên để buộc bạn quay về tích phân gốc.
6. **Bỏ sót miền tích phân** khi vật có lỗ/khoét — quên dùng tính cộng được theo miền (Phần 4.2) để trừ phần khoét.
7. **Nhầm $\theta$ và $\phi$** giữa quy ước Toán học và quy ước Vật Lý trong tọa độ cầu (Phần 1.3c).
8. **Không kiểm tra giới hạn/thứ nguyên** sau khi ra kết quả → bỏ lỡ cơ hội tự phát hiện sai sót ngay trong phòng thi.

---

## PHẦN 7: QUY TRÌNH KIỂM TRA TỔNG HỢP (Checklist trước khi viết tích phân)

```
┌─────────────────────────────────────────────┐
│ 1. Đại lượng cần tìm là TỔNG của cái gì?     │
│    → Viết phần tử vi phân (dm, dq, dI,...)    │
├─────────────────────────────────────────────┤
│ 2. Vật có đối xứng gì? (cầu/trụ/phẳng/không) │
│    → Có dùng được Gauss/định lý trục không?   │
│    Có → dùng công cụ "tắt". Không → bước 3.   │
├─────────────────────────────────────────────┤
│ 3. Chọn hệ tọa độ khớp đối xứng vật           │
├─────────────────────────────────────────────┤
│ 4. Viết biên miền D/V theo hệ tọa độ đó,      │
│    xác định thứ tự quét biến                  │
├─────────────────────────────────────────────┤
│ 5. Viết hàm cần lấy tổng f, CÙNG hệ tọa độ    │
│    với phần tử vi phân (không trộn hệ)        │
├─────────────────────────────────────────────┤
│ 6. Tận dụng đối xứng để HẠ BẬC nếu có thể     │
│    (ví dụ: tích phân góc "cho không")         │
├─────────────────────────────────────────────┤
│ 7. Ráp Fubini, tính từ trong ra ngoài          │
├─────────────────────────────────────────────┤
│ 8. Kiểm tra: thứ nguyên? giới hạn đặc biệt?    │
│    đối xứng kết quả có hợp lý không?           │
└─────────────────────────────────────────────┘
```

---

## PHẦN 8: BÀI TẬP LUYỆN TẬP ĐỀ XUẤT (tự giải, không tra lời giải trước)

1. Tìm mô-men quán tính của một thanh có khối lượng riêng theo chiều dài biến thiên $\lambda(x) = \lambda_0 (1 + x/L)$, dài $L$, quanh trục vuông góc qua một đầu thanh.
2. Tìm điện trường trên trục đối xứng của một **vành** (không phải đĩa đặc) bán kính $R$, tích điện đều $Q$, tại điểm cách tâm vành khoảng $z$ trên trục. So sánh giới hạn $z \gg R$ với công thức điện tích điểm.
3. Một đĩa tích điện với mật độ mặt không đều $\sigma(r) = \sigma_0 (r/R)$ (tăng dần ra biên). Tìm điện tích tổng và điện trường tại tâm đối xứng... (gợi ý: tại tâm, dùng đối xứng để lý luận trước khi tích phân).
4. Tìm khối tâm của một tấm phẳng hình một phần tư đĩa tròn bán kính $R$, khối lượng riêng mặt đều $\sigma$.
5. (Nâng cao - mức VPHO) Tìm lực hấp dẫn giữa một thanh mảnh dài $L$ khối lượng $M$ và một chất điểm khối lượng $m$ đặt trên đường kéo dài của thanh, cách đầu gần nhất một khoảng $d$. So sánh với công thức lực hấp dẫn điểm khi $d \gg L$.

---

## LỜI KẾT PHẦN NÀY

Tích phân bội không phải là "một chương Toán phải học riêng" — nó là **ngôn ngữ hình thức của Nguyên lý chồng chất liên tục**. Một khi bạn thấm được Bước 1–6 ở Phần 3 như phản xạ, bạn sẽ thấy: "đĩa tích điện", "thanh không đều", "khối cầu đặc biệt", "nêm có mật độ biến thiên" — tất cả **chỉ là lá khác màu mọc từ cùng một gốc cây**, đúng như triết lý tổng của tài liệu gốc.

**Nhắc lại bất biến quan trọng nhất**: *Nếu bạn không thể viết đủ 4 thành phần (phần tử vi phân, hệ tọa độ, miền, hàm cần tổng), bạn chưa thực sự hiểu bài — hãy quay lại mô hình hóa, đừng cố "đoán" công thức.*
