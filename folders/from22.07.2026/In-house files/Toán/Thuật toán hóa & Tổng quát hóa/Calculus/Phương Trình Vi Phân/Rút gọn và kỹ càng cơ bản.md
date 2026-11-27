*Các vấn đề về lỗi hiển thị xuất hiện đầy rẫy, muốn khắc phục, hãy lấy file .md này rồi phân tích ngược hoặc dùng cách hiển thị khác ko phải github để tương thích

# GIÁO TRÌNH PTVP TỪ A → Z (BẢN CHUẨN HÓA THEO QUY ƯỚC CỦA BẠN)

> **Quy ước bắt buộc xuyên suốt giáo trình:**
> - Biến độc lập duy nhất: $t$ (thời gian).
> - Mọi đại lượng phụ thuộc $t$ đều viết dưới dạng hàm: $y(t)$, $x(t)$, $v(t)$, $q(t)$… **Không dùng tham số trừu tượng**.
> - Đạo hàm **chỉ dùng ký hiệu Leibniz**, có ghi rõ biến: $\dfrac{dy(t)}{dt}$, $\dfrac{d^2y(t)}{dt^2}$ — **không viết tắt** $y'$, $y''$.
> - Vi phân viết đầy đủ: $dy(t) = f(t)\,dt$.
> - Hằng số vật lý ($m$, $k$, $g$, $R$, $L$, $C$…) được phép dùng vì chúng là **hằng số của bài toán**, không phải tham số trừu tượng.
> - Thuật ngữ chuyên môn viết bằng tiếng Anh, giải thích bằng tiếng Việt.

---

# PHẦN 0 — BẢN CHẤT CỦA PTVP (HIỂU, KHÔNG HỌC VẸT)

## 0.1. Vì sao Vũ trụ buộc phải "cục bộ"?

Trước khi nói PTVP là gì, phải hiểu **vì sao Vật lý cần đến nó**.

Trong Vũ trụ này có một giới hạn tốc độ tuyệt đối: **tốc độ ánh sáng $c$**. Không một tín hiệu, một lực, hay một thông tin nào có thể truyền nhanh hơn $c$. Hệ quả triết học cực kỳ sâu sắc:

> **Một vật tại vị trí $A$ không thể "biết ngay lập tức" vật tại vị trí $B$ đang làm gì.** Nó chỉ có thể biết sau khi tín hiệu từ $B$ truyền đến $A$ — mất một khoảng thời gian hữu hạn.

Điều này có nghĩa: **mọi quy luật tự nhiên đều phải viết dưới dạng LOCAL** — tức là "trạng thái tại đây, lúc này thay đổi thế nào phụ thuộc vào trạng thái lân cận ngay sát đây, lúc này". Không có "hành động từ xa tức thời" (action at a distance).

Toán học của sự thay đổi cục bộ chính là **đạo hàm**. Vì vậy, ngôn ngữ tự nhiên của Vật lý là **phương trình vi phân**.

## 0.2. Vì sao không thể "cứ tích phân là xong"?

Giả sử ta biết vận tốc của một vật phụ thuộc **chỉ vào thời gian**:

$$
\frac{dy(t)}{dt} = f(t)
$$

Lúc này ta **có thể** tích phân trực tiếp: $y(t) = \displaystyle\int f(t)\,dt + C$ — vì vế phải không chứa $y(t)$, nên tích phân hoàn toàn tính được.

**Nhưng thực tế Vật lý không cho ta điều đó.** Vật lý cho ta:

$$
\frac{dy(t)}{dt} = g\big(t,\, y(t)\big)
$$

Vế phải chứa $y(t)$ — chính là **hàm ta đang đi tìm**. Nếu bạn thử tích phân hai vế:

$$
y(t) = \int g\big(t,\, y(t)\big)\,dt + C
$$

Bạn **không thể tính tích phân này** vì bên trong dấu tích phân có $y(t)$ — ẩn số chưa biết. Đây chính là **rào cản bản chất** khiến PTVP khó hơn phép tính tích phân thông thường.

**Ví dụ cụ thể:** vật rơi có lực cản tỉ lệ vận tốc:

$$
m\,\frac{dv(t)}{dt} = mg - \gamma\, v(t)
$$

Bạn không thể viết $v(t) = \displaystyle\int \big(g - \tfrac{\gamma}{m}v(t)\big)\,dt$ rồi tính — vì $v(t)$ nằm trong dấu tích phân. Phải dùng **kỹ thuật** để gỡ $v(t)$ ra khỏi tích phân (đó chính là D.3 — integrating factor).

## 0.3. Định nghĩa PTVP

> **Phương trình vi phân** (differential equation) là một phương trình trong đó **ẩn số là một hàm**, và phương trình có chứa **đạo hàm của hàm ẩn đó**.

Khi hàm ẩn chỉ phụ thuộc **một biến độc lập** ($t$), ta gọi là **phương trình vi phân thường** (Ordinary Differential Equation — **ODE**, tiếng Việt: **PTVP**).

Dạng tổng quát của PTVP bậc $n$:

$$
F\!\left(t,\; y(t),\; \frac{dy(t)}{dt},\; \frac{d^2y(t)}{dt^2},\; \dots,\; \frac{d^ny(t)}{dt^n}\right) = 0
$$

Trong đó:
- $t$ — biến độc lập,
- $y(t)$ — hàm ẩn cần tìm,
- $F$ — biểu thức liên hệ giữa $t$, $y(t)$ và các đạo hàm của $y(t)$.

## 0.4. Nghiệm của PTVP là gì?

**Nghiệm** của PTVP là một hàm $y(t)$ mà khi thay vào phương trình (cùng các đạo hàm của nó) thì phương trình trở thành **đẳng thức đúng với mọi $t$** trong miền xác định.

**Ví dụ:** Xét $\dfrac{dy(t)}{dt} = 2t$.
- $y(t) = t^2$ → $\dfrac{dy(t)}{dt} = 2t$ ✓
- $y(t) = t^2 + 7$ → $\dfrac{dy(t)}{dt} = 2t$ ✓
- $y(t) = t^2 - 100$ → $\dfrac{dy(t)}{dt} = 2t$ ✓

Vậy PTVP có **vô số nghiệm**, sai khác nhau một hằng số. Đó là **nghiệm tổng quát** (general solution):

$$
y(t) = t^2 + C
$$

Với PTVP bậc $n$, nghiệm tổng quát chứa **đúng $n$ hằng số tùy ý** $C_1, \dots, C_n$. Đây là lý do **PTVP bậc $n$ cần $n$ điều kiện đầu** để chọn ra một nghiệm riêng (particular solution) duy nhất.

## 0.5. Các thuật ngữ bắt buộc

| Khái niệm | Ý nghĩa | Ví dụ |
|---|---|---|
| **Bậc** (order) | Cấp cao nhất của đạo hàm xuất hiện | $\dfrac{d^2y(t)}{dt^2} + y(t) = 0$ — bậc 2 |
| **Tuyến tính** (linear) | $y(t)$ và các đạo hàm chỉ xuất hiện **bậc 1**, không nhân nhau, không nằm trong hàm phi tuyến | $\dfrac{dy(t)}{dt} + 3y(t) = t^2$ — tuyến tính |
| **Phi tuyến** (nonlinear) | Ngược lại | $\dfrac{dy(t)}{dt} + [y(t)]^2 = 0$ — phi tuyến |
| **Thuần nhất** (homogeneous, tuyến tính) | Vế phải (phần không chứa $y$) $= 0$ | $\dfrac{d^2y(t)}{dt^2} + y(t) = 0$ |
| **Không thuần nhất** (non-homogeneous) | Vế phải $\neq 0$ | $\dfrac{d^2y(t)}{dt^2} + y(t) = \cos t$ |
| **Hệ số hằng** (constant coefficients) | Hệ số trước $y(t)$ và các đạo hàm là hằng | $3\dfrac{d^2y(t)}{dt^2} + 2\dfrac{dy(t)}{dt} + 5y(t) = 0$ |
| **Tự trị** (autonomous) | Biến $t$ **không xuất hiện tường minh** | $\dfrac{dy(t)}{dt} = f(y(t))$ |
| **Điều kiện đầu** (initial conditions) | Giá trị của $y$ và các đạo hàm tại $t=0$ | $y(0)=0$, $\dfrac{dy(t)}{dt}\Big|_{t=0} = 5$ |

> ⚠️ **Cảnh báo ngôn ngữ:** chữ "homogeneous" có **hai nghĩa** khác nhau:
> - (a) *tuyến tính thuần nhất*: vế phải $= 0$ — dùng cho PTVP tuyến tính.
> - (b) *đẳng cấp (homogeneous of degree 0)*: vế phải phụ thuộc $y(t)/t$ — một loại PTVP phi tuyến.
>
> Trong giáo trình này: **"thuần nhất"** = nghĩa (a); **"đẳng cấp"** = nghĩa (b).

## 0.6. Ý nghĩa hình học — trường hướng (slope field)

Với PTVP bậc 1 $\dfrac{dy(t)}{dt} = f\big(t, y(t)\big)$, tại mỗi điểm $(t, y)$ trong mặt phẳng, hãy vẽ một mũi tên có hệ số góc $f(t, y)$. Tập hợp mọi mũi tên là **trường hướng** (slope field). Nghiệm $y(t)$ chính là **đường cong luôn tiếp xúc** với các mũi tên đó (integral curve).

Hệ quả mạnh mẽ:
- Qua mỗi điểm (với điều kiện tồn tại–duy nhất) có **đúng một** đường nghiệm → các đường nghiệm **không cắt nhau**.
- **Đường đẳng nghiêng** (isocline) $f(t,y)=k$ giúp phác thảo nghiệm không cần giải.
- Điểm có $f=0$ → **nghiệm hằng** (điểm cân bằng).

---

# PHẦN D.1 — TÍCH PHÂN TRỰC TIẾP (Direct Integration)

## D.1.1. Nhận diện

$$
\frac{dy(t)}{dt} = f(t)
$$

Vế phải **chỉ phụ thuộc $t$**, không chứa $y(t)$.

## D.1.2. Thuật toán

**Bước 1.** Viết vi phân hai vế (Leibniz):

$$
dy(t) = f(t)\,dt
$$

**Bước 2.** Tích phân hai vế:

$$
\int dy(t) = \int f(t)\,dt
$$

**Bước 3.** Kết quả:

$$
\boxed{\,y(t) = \int f(t)\,dt + C\,}
$$

Nếu có điều kiện đầu $y(t_0) = y_0$, dùng dạng xác định:

$$
y(t) = y_0 + \int_{t_0}^{t} f(s)\,ds
$$

## D.1.3. Ví dụ vật lý

Một vật chuyển động thẳng với gia tốc $a(t) = 6t$ (SI). Biết $v(0) = 2$ m/s, $x(0) = 0$ m. Tìm $x(t)$.

**Bước 1:** $\dfrac{dv(t)}{dt} = 6t$. Tích phân trực tiếp:

$$
v(t) = \int 6t\,dt = 3t^2 + C_1
$$

Điều kiện $v(0) = 2$ → $C_1 = 2$ → $v(t) = 3t^2 + 2$.

**Bước 2:** $v(t) = \dfrac{dx(t)}{dt} = 3t^2 + 2$. Tích phân trực tiếp lần nữa:

$$
x(t) = \int (3t^2 + 2)\,dt = t^3 + 2t + C_2
$$

Điều kiện $x(0) = 0$ → $C_2 = 0$ → $x(t) = t^3 + 2t$.

**Nhận xét:** PTVP bậc $n$ dạng $\dfrac{d^ny(t)}{dt^n} = f(t)$ cần tích phân $n$ lần, sinh ra $n$ hằng số.

## D.1.4. Lưu ý

Nếu $\displaystyle\int f(t)\,dt$ không có dạng đóng (ví dụ $\int e^{-t^2}\,dt$), **vẫn để dạng tích phân** — đó là nghiệm hợp lệ. Trong Vật lý, thường dùng dạng tích phân xác định.

---

# PHẦN D.2 — TÁCH BIẾN (Separation of Variables)

## D.2.1. Nhận diện

$$
\frac{dy(t)}{dt} = f(t)\cdot g\big(y(t)\big)
$$

Vế phải **phân tích thành tích** của một hàm chỉ chứa $t$ và một hàm chỉ chứa $y(t)$.

Trường hợp đặc biệt cực quan trọng: **autonomous** — $\dfrac{dy(t)}{dt} = g(y(t))$ (vắng $t$ tường minh).

## D.2.2. Thuật toán

**Bước 1 (bắt buộc):** Tìm nghiệm hằng — giải $g(y^*) = 0$. Mỗi nghiệm $y^*$ cho $y(t) \equiv y^*$ là một nghiệm. **Bước chia cho $g(y)$ tiếp theo sẽ làm mất các nghiệm này**, phải ghi riêng.

**Bước 2:** Với $g(y(t)) \neq 0$, tách biến:

$$
\frac{dy(t)}{g\big(y(t)\big)} = f(t)\,dt
$$

**Bước 3:** Tích phân hai vế:

$$
\int \frac{dy}{g(y)} = \int f(t)\,dt + C
$$

**Bước 4:** Giải ngược ra $y(t)$ nếu được; nếu không, để dạng ẩn $\Phi(t, y) = C$.

**Bước 5:** Áp dụng điều kiện đầu; **kiểm tra nghiệm hằng** có thỏa điều kiện đầu không.

## D.2.3. Ví dụ 1 — Phân rã phóng xạ

$$
\frac{dy(t)}{dt} = -k\, y(t), \quad k > 0
$$

**Nghiệm hằng:** $y^*=0$ → $y(t) \equiv 0$.

**Tách biến:** $\dfrac{dy(t)}{y(t)} = -k\,dt$.

**Tích phân:**

$$
\ln\big|y(t)\big| = -kt + C
$$

$$
\big|y(t)\big| = e^{-kt+C} = e^C\, e^{-kt}
$$

Đặt $A = \pm e^C$ (hằng số tùy ý, có thể âm, dương, hoặc bằng 0):

$$
\boxed{\,y(t) = A\, e^{-kt}\,}
$$

Với $y(0) = y_0$ → $A = y_0$ → $y(t) = y_0\, e^{-kt}$.

## D.2.4. Ví dụ 2 — Định luật làm nguội Newton

$$
\frac{dy(t)}{dt} = -k\,\big(y(t) - T_0\big)
$$

trong đó $T_0$ là nhiệt độ môi trường. Tách biến:

$$
\frac{dy(t)}{y(t) - T_0} = -k\,dt
$$

Tích phân:

$$
\ln\big|y(t) - T_0\big| = -kt + C
$$

$$
y(t) = T_0 + A\, e^{-kt}
$$

Với $y(0) = y_0$ → $A = y_0 - T_0$ → $y(t) = T_0 + (y_0 - T_0)\, e^{-kt}$.

## D.2.5. Ví dụ 3 — Lực cản bậc hai (rơi tự do có lực cản)

$$
\frac{dv(t)}{dt} = g\left(1 - \frac{[v(t)]^2}{v_t^2}\right), \quad v_t = \sqrt{\frac{mg}{k}}
$$

**Nghiệm hằng:** $v^* = \pm v_t$.

**Tách biến:**

$$
\frac{dv(t)}{1 - [v(t)]^2/v_t^2} = g\,dt
$$

$$
v_t\,\mathrm{artanh}\!\left(\frac{v(t)}{v_t}\right) = gt + C
$$

Với $v(0)=0$ → $C=0$:

$$
\boxed{\,v(t) = v_t\,\tanh\!\left(\frac{gt}{v_t}\right)\,}
$$

**Kiểm chứng:** $t \to \infty$ → $v \to v_t$ (khớp nghiệm hằng); $t \to 0$ → $v \approx gt$ (rơi tự do).

## D.2.6. Các bẫy kinh điển

| Bẫy | Cách tránh |
|---|---|
| Quên nghiệm hằng $g(y^*)=0$ | Giải $g(y^*)=0$ **trước** khi chia |
| Viết $\int dy/y = \ln y$ (thiếu trị tuyệt đối) | Viết $\ln|y|$, hấp thụ dấu $\pm$ vào hằng $A$ |
| Nghiệm chỉ hợp lệ trên khoảng không chứa điểm $g=0$ | Ghi rõ miền xác định |

---

# PHẦN D.3 — TUYẾN TÍNH BẬC 1 (Linear First Order)

## D.3.1. Dạng chuẩn

$$
\frac{dy(t)}{dt} + p(t)\, y(t) = q(t)
$$

trong đó $p(t)$, $q(t)$ là các hàm đã biết của $t$.

- Nếu $q(t) \equiv 0$: **thuần nhất** (linear homogeneous).
- Nếu $q(t) \not\equiv 0$: **không thuần nhất** (linear non-homogeneous).

## D.3.2. Trường hợp thuần nhất — tách biến được

$$
\frac{dy(t)}{dt} + p(t)\, y(t) = 0
$$

$$
\frac{dy(t)}{y(t)} = -p(t)\,dt \;\Longrightarrow\; \ln\big|y(t)\big| = -\int p(t)\,dt + C
$$

$$
\boxed{\,y(t) = A\, \exp\!\left(-\int p(t)\,dt\right)\,}
$$

## D.3.3. Trường hợp không thuần nhất — Integrating Factor

**Ý tưởng cốt lõi:** Ta muốn nhân hai vế với một hàm $\mu(t) > 0$ (gọi là **thừa số tích phân** — integrating factor) sao cho vế trái trở thành **đạo hàm của một tích** $\dfrac{d}{dt}\big[\mu(t)\, y(t)\big]$. Khi đó tích phân hai vế là xong.

**Bước 1.** Xác định $\mu(t)$: Ta cần $\mu(t)\dfrac{dy(t)}{dt} + \mu(t)\, p(t)\, y(t) = \dfrac{d}{dt}\big[\mu(t)\, y(t)\big]$. Khai triển vế phải bằng quy tắc tích:

$$
\frac{d}{dt}\big[\mu(t)\, y(t)\big] = \mu(t)\frac{dy(t)}{dt} + \frac{d\mu(t)}{dt}\, y(t)
$$

Đồng nhất hệ số → $\dfrac{d\mu(t)}{dt} = \mu(t)\, p(t)$ → $\mu(t) = \exp\!\left(\displaystyle\int p(t)\,dt\right)$.

$$
\boxed{\,\mu(t) = \exp\!\left(\int p(t)\,dt\right)\,}
$$

**Bước 2.** Nhân hai vế phương trình ban đầu với $\mu(t)$:

$$
\mu(t)\frac{dy(t)}{dt} + \mu(t)\, p(t)\, y(t) = \mu(t)\, q(t)
$$

Vế trái chính là $\dfrac{d}{dt}\big[\mu(t)\, y(t)\big]$:

$$
\frac{d}{dt}\big[\mu(t)\, y(t)\big] = \mu(t)\, q(t)
$$

**Bước 3.** Tích phân hai vế:

$$
\mu(t)\, y(t) = \int \mu(t)\, q(t)\, dt + C
$$

**Bước 4.** Chia hai vế cho $\mu(t)$:

$$
\boxed{\,y(t) = \frac{1}{\mu(t)}\left[\int \mu(t)\, q(t)\, dt + C\right]\,}
$$

## D.3.4. Cấu trúc nghiệm — cực kỳ quan trọng

$$
y(t) = \underbrace{C\, e^{-P(t)}}_{\text{nghiệm thuần nhất (quá độ)}} + \underbrace{e^{-P(t)}\int \mu(t) q(t)\, dt}_{\text{nghiệm riêng (xác lập)}}
$$

trong đó $P(t) = \displaystyle\int p(t)\,dt$.

**Ý nghĩa Vật lý:**
- Phần $C\, e^{-P(t)}$ — **quá độ** (transient). Nếu $p(t)>0$, phần này tắt dần.
- Phần còn lại — **xác lập** (steady-state). Sau thời gian $t \gg \tau$ (hằng số thời gian), hệ quên điều kiện đầu.

**Đây là bộ khung của mọi mạch RC, RL, bài làm nguội, bồn hòa tan.**

## D.3.5. Ví dụ — Mạch RL

Mạch gồm $R$, $L$ nối tiếp, nguồn $E(t)$. Dòng điện $i(t)$ thỏa:

$$
L\,\frac{di(t)}{dt} + R\, i(t) = E(t)
$$

Chia cho $L$:

$$
\frac{di(t)}{dt} + \frac{R}{L}\, i(t) = \frac{E(t)}{L}
$$

Vậy $p(t) = \dfrac{R}{L}$ (hằng), $q(t) = \dfrac{E(t)}{L}$.

**Integrating factor:**

$$
\mu(t) = \exp\!\left(\int \frac{R}{L}\, dt\right) = e^{(R/L)t}
$$

**Nhân hai vế:**

$$
e^{(R/L)t}\frac{di(t)}{dt} + \frac{R}{L}e^{(R/L)t}\, i(t) = \frac{E(t)}{L}e^{(R/L)t}
$$

$$
\frac{d}{dt}\!\left[e^{(R/L)t}\, i(t)\right] = \frac{E(t)}{L}e^{(R/L)t}
$$

**Tích phân:**

$$
e^{(R/L)t}\, i(t) = \int \frac{E(t)}{L}e^{(R/L)t}\, dt + C
$$

$$
i(t) = e^{-(R/L)t}\left[\int \frac{E(t)}{L}e^{(R/L)t}\, dt + C\right]
$$

**Trường hợp $E(t) = E_0$ hằng:**

$$
i(t) = \frac{E_0}{R} + C\, e^{-(R/L)t}
$$

Với $i(0) = 0$ → $C = -\dfrac{E_0}{R}$:

$$
i(t) = \frac{E_0}{R}\left(1 - e^{-(R/L)t}\right)
$$

Đây là dòng tăng dần từ $0$ đến giá trị xác lập $E_0/R$ với hằng số thời gian $\tau = L/R$.

## D.3.6. Ví dụ — Hệ số biến thiên

$$
\frac{dy(t)}{dt} - \frac{y(t)}{t} = t
$$

$p(t) = -\dfrac{1}{t}$, $\mu(t) = \exp\!\left(-\displaystyle\int \tfrac{dt}{t}\right) = \dfrac{1}{t}$.

$$
\frac{d}{dt}\!\left[\frac{y(t)}{t}\right] = 1 \;\Longrightarrow\; \frac{y(t)}{t} = t + C \;\Longrightarrow\; y(t) = t^2 + Ct
$$

## D.3.7. Bẫy

| Bẫy | Cách tránh |
|---|---|
| Quên chia cho hệ số của $\dfrac{dy(t)}{dt}$ trước khi xác định $p(t)$ | Luôn đưa về dạng chuẩn |
| Nhầm dấu trong $\mu(t) = e^{\int p\,dt}$ | $e^{+P}$ trong tích phân, $e^{-P}$ bên ngoài |
| Dùng điều kiện đầu khi $y(t)$ còn chứa $C$ ở vị trí phức tạp | Chỉ thay điều kiện đầu vào nghiệm **tổng** (sau khi đã có $C$ độc lập) |

---

# PHẦN D.6 — PHƯƠNG TRÌNH BERNOULLI

## D.6.1. Dạng

$$
\frac{dy(t)}{dt} + p(t)\, y(t) = q(t)\, [y(t)]^n, \quad n \neq 0,\; n \neq 1
$$

## D.6.2. Ý tưởng

Đây là phương trình **tuyến tính bị nhiễu bởi lũy thừa của $y$**. Phép thế $z(t) = [y(t)]^{1-n}$ sẽ **khử nhiễu**, biến nó thành tuyến tính.

## D.6.3. Thuật toán

**Bước 1.** Chia hai vế cho $[y(t)]^n$:

$$
[y(t)]^{-n}\frac{dy(t)}{dt} + p(t)\, [y(t)]^{1-n} = q(t)
$$

**Bước 2.** Đặt $z(t) = [y(t)]^{1-n}$. Đạo hàm:

$$
\frac{dz(t)}{dt} = (1-n)\, [y(t)]^{-n}\, \frac{dy(t)}{dt}
$$

$$
\Longrightarrow\; [y(t)]^{-n}\frac{dy(t)}{dt} = \frac{1}{1-n}\, \frac{dz(t)}{dt}
$$

**Bước 3.** Thay vào:

$$
\frac{1}{1-n}\, \frac{dz(t)}{dt} + p(t)\, z(t) = q(t)
$$

Nhân hai vế với $(1-n)$:

$$
\boxed{\,\frac{dz(t)}{dt} + (1-n)\, p(t)\, z(t) = (1-n)\, q(t)\,}
$$

Đây là **PTVP tuyến tính bậc 1** theo $z(t)$ — giải bằng D.3.

**Bước 4.** Tìm $z(t)$, quay lại:

$$
y(t) = [z(t)]^{1/(1-n)}
$$

**Bước 5.** Kiểm tra nghiệm $y(t) \equiv 0$ (nếu $n > 0$).

## D.6.4. Ví dụ — Bài toán logistic (tăng trưởng có giới hạn)

$$
\frac{dN(t)}{dt} = r\, N(t)\left(1 - \frac{N(t)}{K}\right)
$$

Viết lại:

$$
\frac{dN(t)}{dt} - r\, N(t) = -\frac{r}{K}\,[N(t)]^2
$$

Đây là Bernoulli với $n=2$, $p(t) = -r$, $q(t) = -\dfrac{r}{K}$.

Đặt $z(t) = [N(t)]^{-1}$:

$$
\frac{dz(t)}{dt} + r\, z(t) = \frac{r}{K}
$$

Tuyến tính → integrating factor $\mu(t) = e^{rt}$:

$$
\frac{d}{dt}\!\left[e^{rt}\, z(t)\right] = \frac{r}{K} e^{rt}
$$

$$
z(t) = \frac{1}{K} + C\, e^{-rt}
$$

$$
N(t) = \frac{1}{z(t)} = \frac{K}{1 + CK\, e^{-rt}}
$$

Với $N(0) = N_0$ → $CK = \dfrac{K}{N_0} - 1$:

$$
\boxed{\,N(t) = \frac{K}{1 + \left(\dfrac{K}{N_0} - 1\right)e^{-rt}}\,}
$$

**Kiểm chứng:** $t \to \infty$ → $N \to K$ (khớp nghiệm hằng ổn định $N^*=K$); $t \to 0$ → $N \to N_0$ ✓.

---

# PHẦN E.2 — TUYẾN TÍNH HỆ SỐ HẰNG, THUẦN NHẤT

## E.2.1. Dạng

$$
a\,\frac{d^2y(t)}{dt^2} + b\,\frac{dy(t)}{dt} + c\, y(t) = 0
$$

với $a \neq 0$, $a$, $b$, $c$ là **hằng số**.

## E.2.2. Phương trình đặc trưng (characteristic equation)

Giả sử nghiệm có dạng $y(t) = e^{\lambda t}$ với $\lambda$ là một số (thực hoặc phức). Thay vào:

$$
a\,\lambda^2 e^{\lambda t} + b\,\lambda e^{\lambda t} + c\, e^{\lambda t} = 0
$$

Vì $e^{\lambda t} \neq 0$:

$$
\boxed{\,a\,\lambda^2 + b\,\lambda + c = 0\,}
$$

Đây là phương trình bậc 2 theo $\lambda$. Biệt thức:

$$
\Delta = b^2 - 4ac
$$

## E.2.3. Ba trường hợp

| Trường hợp | Nghiệm đặc trưng | Nghiệm tổng quát |
|---|---|---|
| $\Delta > 0$ | $\lambda_1 \neq \lambda_2$ thực | $y(t) = C_1\, e^{\lambda_1 t} + C_2\, e^{\lambda_2 t}$ |
| $\Delta = 0$ | $\lambda_1 = \lambda_2 = \lambda$ | $y(t) = (C_1 + C_2\, t)\, e^{\lambda t}$ |
| $\Delta < 0$ | $\lambda = \alpha \pm i\beta$ | $y(t) = e^{\alpha t}\big[C_1\cos(\beta t) + C_2\sin(\beta t)\big]$ |

## E.2.4. Vì sao có trường hợp $\Delta = 0$?

Khi $\lambda_1 = \lambda_2 = \lambda$, ta chỉ có **một** nghiệm độc lập $e^{\lambda t}$. Phải tìm nghiệm thứ hai. Có thể chứng minh bằng **hạ bậc** (reduction of order) rằng nghiệm thứ hai là $t\, e^{\lambda t}$. (Kỹ thuật: đặt $y(t) = e^{\lambda t}\, u(t)$, thay vào, giải ra $u(t) = C_1 + C_2 t$.)

## E.2.5. Ví dụ — Dao động điều hòa

$$
\frac{d^2y(t)}{dt^2} + \omega^2\, y(t) = 0
$$

Phương trình đặc trưng: $\lambda^2 + \omega^2 = 0$ → $\lambda = \pm i\omega$ (thuần ảo, $\alpha = 0$, $\beta = \omega$).

$$
y(t) = C_1\cos(\omega t) + C_2\sin(\omega t)
$$

Dạng biên độ–pha: $y(t) = A\cos(\omega t - \varphi)$ với $A = \sqrt{C_1^2 + C_2^2}$.

**Đây là phương trình dao động điều hòa — nền tảng của mọi bài dao động trong Vật lý.**

## E.2.6. Ví dụ — Dao động tắt dần (damped oscillation)

$$
m\,\frac{d^2x(t)}{dt^2} + \gamma\,\frac{dx(t)}{dt} + k\, x(t) = 0
$$

Đặt $\omega_0 = \sqrt{k/m}$ (tần số riêng), $\delta = \gamma/(2m)$ (hệ số tắt dần). Phương trình đặc trưng:

$$
\lambda^2 + 2\delta\lambda + \omega_0^2 = 0
$$

$$
\lambda = -\delta \pm \sqrt{\delta^2 - \omega_0^2}
$$

| Chế độ | Điều kiện | Nghiệm |
|---|---|---|
| **Tắt dần yếu** (underdamped) | $\delta < \omega_0$ | $x(t) = e^{-\delta t}\big[C_1\cos(\omega_d t) + C_2\sin(\omega_d t)\big]$, $\omega_d = \sqrt{\omega_0^2 - \delta^2}$ |
| **Tắt dần tới hạn** (critical) | $\delta = \omega_0$ | $x(t) = (C_1 + C_2 t)\, e^{-\delta t}$ |
| **Tắt dần mạnh** (overdamped) | $\delta > \omega_0$ | $x(t) = C_1 e^{\lambda_1 t} + C_2 e^{\lambda_2 t}$ với $\lambda_{1,2} < 0$ |

**Kiểm chứng:** Cả ba trường hợp đều có $x(t) \to 0$ khi $t \to \infty$ (vì $\delta > 0$). Chỉ underdamped mới **dao động** (vượt qua VTCB nhiều lần).

---

# PHẦN E.3 — TUYẾN TÍNH HỆ SỐ HẰNG, KHÔNG THUẦN NHẤT

## E.3.1. Dạng

$$
a\,\frac{d^2y(t)}{dt^2} + b\,\frac{dy(t)}{dt} + c\, y(t) = f(t)
$$

với $f(t) \not\equiv 0$.

## E.3.2. Định lý cấu trúc nghiệm (nền tảng)

$$
\boxed{\,y(t) = y_h(t) + y_p(t)\,}
$$

trong đó:
- $y_h(t)$ — nghiệm tổng quát của phương trình **thuần nhất** (E.2), chứa $C_1, C_2$.
- $y_p(t)$ — **một** nghiệm riêng **bất kỳ** của phương trình không thuần nhất.

**Nguyên lý chồng chất** (superposition): nếu $f(t) = f_1(t) + f_2(t)$ thì $y_p(t) = y_{p1}(t) + y_{p2}(t)$ với $y_{p1}$, $y_{p2}$ lần lượt là nghiệm riêng ứng với $f_1$, $f_2$.

## E.3.3. Phương pháp hệ số bất định (Undetermined Coefficients)

**Điều kiện áp dụng:** $f(t)$ thuộc **lớp đóng kín dưới đạo hàm** — tức đa thức, $e^{\alpha t}$, $\cos(\beta t)$, $\sin(\beta t)$, và tích của chúng.

**Bảng dạng thử nghiệm riêng:**

| $f(t)$ | Dạng thử $y_p(t)$ (trước khi nhân $t^s$) |
|---|---|
| $P_n(t)$ (đa thức bậc $n$) | $A_n t^n + \cdots + A_1 t + A_0$ |
| $P_n(t)\, e^{\alpha t}$ | $(A_n t^n + \cdots + A_0)\, e^{\alpha t}$ |
| $P_n(t)\cos(\beta t)$ hoặc $P_n(t)\sin(\beta t)$ | $(A_n t^n + \cdots + A_0)\cos(\beta t) + (B_n t^n + \cdots + B_0)\sin(\beta t)$ |
| $e^{\alpha t}\big[P_n(t)\cos(\beta t) + R_m(t)\sin(\beta t)\big]$ | $e^{\alpha t}\big[Q_k(t)\cos(\beta t) + S_k(t)\sin(\beta t)\big]$, $k=\max(n,m)$ |

**Quy tắc cộng hưởng (resonance):** Nếu dạng thử **trùng với nghiệm của phương trình thuần nhất**, phải nhân thêm $t^s$, trong đó $s$ là **bội** của nghiệm đặc trưng tương ứng:
- $s = 0$: không trùng,
- $s = 1$: trùng nghiệm đơn,
- $s = 2$: trùng nghiệm kép.

## E.3.4. Thuật toán

**Bước 1.** Giải phương trình thuần nhất → $y_h(t)$ chứa $C_1, C_2$.

**Bước 2.** Phân $f(t)$ thành các số hạng. Mỗi số hạng, chọn dạng $y_p$ theo bảng, **nhân thêm $t^s$** nếu cộng hưởng.

**Bước 3.** Thay $y_p$ vào phương trình, **đồng nhất hệ số** với $f(t)$ → giải ra các hệ số chưa biết.

**Bước 4.** Nghiệm tổng: $y(t) = y_h(t) + y_p(t)$.

**Bước 5.** Dùng điều kiện đầu **lên nghiệm tổng** $y(t)$ — **không** lên $y_h$ riêng.

## E.3.5. Ví dụ — Có cộng hưởng

$$
\frac{d^2y(t)}{dt^2} - 3\frac{dy(t)}{dt} + 2y(t) = e^t
$$

**Bước 1:** Đặc trưng $\lambda^2 - 3\lambda + 2 = 0$ → $\lambda = 1,\, 2$.

$$
y_h(t) = C_1 e^t + C_2 e^{2t}
$$

**Bước 2:** $f(t) = e^t$. Nhưng $e^t$ **trùng nghiệm đơn** $\lambda_1 = 1$ → $s = 1$. Dạng thử:

$$
y_p(t) = A\, t\, e^t
$$

**Bước 3:** Tính đạo hàm:

$$
\frac{dy_p(t)}{dt} = A e^t + A t e^t = A(1 + t) e^t
$$

$$
\frac{d^2y_p(t)}{dt^2} = A e^t + A(1+t) e^t = A(2 + t) e^t
$$

Thay vào:

$$
A(2+t) e^t - 3A(1+t) e^t + 2At e^t = e^t
$$

$$
A\big[(2+t) - 3(1+t) + 2t\big] = 1
$$

$$
A\big[2 + t - 3 - 3t + 2t\big] = 1 \;\Longrightarrow\; A(-1) = 1 \;\Longrightarrow\; A = -1
$$

**Bước 4:**

$$
\boxed{\,y(t) = C_1 e^t + C_2 e^{2t} - t\, e^t\,}
$$

## E.3.6. Phương pháp phức hóa (Complexification) — mẹo mạnh

Với $f(t) = F_0\cos(\omega t)$, giải phương trình với $f(t) = F_0 e^{i\omega t}$ (dùng số phức), được nghiệm phức $y_c(t)$; nghiệm riêng thật là $\mathrm{Re}\,y_c(t)$.

**Ví dụ:** $\dfrac{d^2y(t)}{dt^2} + \omega_0^2 y(t) = F_0\cos(\omega t)$.

Thử $y_c(t) = Y e^{i\omega t}$ → $\dfrac{dy_c(t)}{dt} = i\omega Y e^{i\omega t}$, $\dfrac{d^2y_c(t)}{dt^2} = -\omega^2 Y e^{i\omega t}$:

$$
(-\omega^2 + \omega_0^2) Y e^{i\omega t} = F_0 e^{i\omega t} \;\Longrightarrow\; Y = \frac{F_0}{\omega_0^2 - \omega^2}
$$

$$
y_p(t) = \mathrm{Re}\!\left[\frac{F_0}{\omega_0^2 - \omega^2} e^{i\omega t}\right] = \frac{F_0}{\omega_0^2 - \omega^2}\cos(\omega t)
$$

## E.3.7. Ứng dụng — Dao động cưỡng bức và cộng hưởng

$$
m\,\frac{d^2x(t)}{dt^2} + \gamma\,\frac{dx(t)}{dt} + k\, x(t) = F_0\cos(\omega t)
$$

Chia $m$, đặt $2\delta = \gamma/m$, $\omega_0^2 = k/m$:

$$
\frac{d^2x(t)}{dt^2} + 2\delta\,\frac{dx(t)}{dt} + \omega_0^2 x(t) = \frac{F_0}{m}\cos(\omega t)
$$

**Nghiệm xác lập** (dùng phức hóa): $x_p(t) = A(\omega)\cos(\omega t - \varphi)$ với

$$
A(\omega) = \frac{F_0/m}{\sqrt{(\omega_0^2 - \omega^2)^2 + 4\delta^2\omega^2}}, \quad \tan\varphi = \frac{2\delta\omega}{\omega_0^2 - \omega^2}
$$

**Cộng hưởng biên độ:** $A$ cực đại tại $\omega_r = \sqrt{\omega_0^2 - 2\delta^2}$ (nếu $\delta < \omega_0/\sqrt{2}$).

**Cộng hưởng thuần túy** ($\delta = 0$, $\omega = \omega_0$): $e^{i\omega t}$ **trùng nghiệm đặc trưng** → $s=1$:

$$
x_p(t) = \frac{F_0}{2m\omega_0}\, t\sin(\omega_0 t)
$$

Biên độ **tăng tuyến tính theo $t$** — đây là hiện tượng cộng hưởng.

---

# PHẦN E.1.b / E.1.c — PHI TUYẾN, VẮNG BIẾN ĐỘC LẬP $t$

> **Lưu ý ký hiệu:** Trong file gốc, hai dạng này được gọi là "vắng $x$" (khi biến độc lập là $x$). Với quy ước của chúng ta — biến độc lập là $t$ — hai dạng này trở thành **vắng $t$** (autonomous, tự trị).

## E.1.b — Dạng tổng quát: vắng $t$

$$
F\!\left(y(t),\; \frac{dy(t)}{dt},\; \frac{d^2y(t)}{dt^2}\right) = 0
$$

Phương trình **không chứa $t$ tường minh** — chỉ chứa $y(t)$ và các đạo hàm.

## E.1.b.1. Thuật toán

**Bước 1.** Đặt $p(t) = \dfrac{dy(t)}{dt}$, nhưng coi $p$ là **hàm của $y$** — tức $p = p(y(t))$.

**Bước 2.** Dùng quy tắc chuỗi:

$$
\frac{d^2y(t)}{dt^2} = \frac{dp(t)}{dt} = \frac{dp}{dy}\cdot\frac{dy(t)}{dt} = p\,\frac{dp}{dy}
$$

**Bước 3.** Phương trình gốc trở thành PTVP bậc 1 cho $p(y)$:

$$
F\!\left(y,\; p,\; p\,\frac{dp}{dy}\right) = 0
$$

**Bước 4.** Giải $p(y)$ (thường bằng tách biến D.2). Sau đó:

$$
\frac{dy(t)}{dt} = p\big(y(t)\big) \;\Longrightarrow\; \int \frac{dy}{p(y)} = t + C
$$

## E.1.c — Trường hợp đặc biệt: $\dfrac{d^2y(t)}{dt^2} = f\big(y(t)\big)$

Đây là dạng quan trọng nhất trong Cơ học — xuất hiện khi lực **chỉ phụ thuộc vị trí** (không phụ thuộc vận tốc, không phụ thuộc thời gian).

## E.1.c.1. Tích phân năng lượng (Energy Integral)

**Phép màu:** Nhân hai vế với $2\,\dfrac{dy(t)}{dt}$:

$$
2\,\frac{dy(t)}{dt}\,\frac{d^2y(t)}{dt^2} = 2\, f\big(y(t)\big)\, \frac{dy(t)}{dt}
$$

Vế trái là đạo hàm của $\left(\dfrac{dy(t)}{dt}\right)^2$:

$$
\frac{d}{dt}\!\left[\left(\frac{dy(t)}{dt}\right)^2\right] = 2\, f\big(y(t)\big)\, \frac{dy(t)}{dt}
$$

Tích phân hai vế theo $t$:

$$
\left(\frac{dy(t)}{dt}\right)^2 = 2\int f(y)\,dy + C
$$

$$
\boxed{\,\frac{1}{2}\left(\frac{dy(t)}{dt}\right)^2 - \int f(y)\,dy = E\,}
$$

Trong đó $E$ là **hằng số tích phân** — chính là **năng lượng toàn phần** (hoặc tích phân đầu tiên — first integral).

## E.1.c.2. Ý nghĩa Vật lý — Cơ học một chiều

Với $m\,\dfrac{d^2x(t)}{dt^2} = F(x(t))$, đặt $F(x) = -\dfrac{dV(x)}{dx}$:

$$
m\,\frac{d^2x(t)}{dt^2} = -\frac{dV(x)}{dx}\Big|_{x=x(t)}
$$

Tích phân năng lượng:

$$
\frac{1}{2}m\left(\frac{dx(t)}{dt}\right)^2 + V\big(x(t)\big) = E
$$

Đây chính là **định luật bảo toàn cơ năng**. Từ đó:

$$
\frac{dx(t)}{dt} = \pm\sqrt{\frac{2}{m}\big(E - V(x(t))\big)}
$$

$$
t = \pm\int \frac{dx}{\sqrt{\frac{2}{m}\big(E - V(x)\big)}} + t_0
$$

**Chu kỳ dao động** (khi $E$ nằm giữa hai điểm quay $x_1, x_2$):

$$
T = 2\int_{x_1}^{x_2} \frac{dx}{\sqrt{\frac{2}{m}\big(E - V(x)\big)}}
$$

## E.1.c.3. Ví dụ — Con lắc đơn (không xấp xỉ góc nhỏ)

$$
\frac{d^2\theta(t)}{dt^2} = -\omega_0^2 \sin\theta(t), \quad \omega_0 = \sqrt{g/L}
$$

Đây là dạng E.1.c với $f(\theta) = -\omega_0^2\sin\theta$. Tích phân năng lượng:

$$
\frac{1}{2}\left(\frac{d\theta(t)}{dt}\right)^2 - \omega_0^2\cos\theta(t) = E
$$

Với $\theta(0) = \theta_0$, $\dfrac{d\theta(t)}{dt}\Big|_{t=0} = 0$:

$$
-\omega_0^2\cos\theta_0 = E
$$

$$
\frac{1}{2}\left(\frac{d\theta(t)}{dt}\right)^2 = \omega_0^2\big(\cos\theta - \cos\theta_0\big)
$$

Chu kỳ dao động (biên độ $\theta_0$):

$$
T = 4\int_0^{\theta_0} \frac{d\theta}{\omega_0\sqrt{2(\cos\theta - \cos\theta_0)}} = \frac{4}{\omega_0}K\!\left(\sin\frac{\theta_0}{2}\right)
$$

trong đó $K$ là **tích phân elliptic đầy đủ loại 1**.

**Xấp xỉ góc nhỏ:** $K(\sin(\theta_0/2)) \approx \dfrac{\pi}{2}\left(1 + \dfrac{\theta_0^2}{16}\right)$:

$$
T \approx T_0\left(1 + \frac{\theta_0^2}{16}\right), \quad T_0 = \frac{2\pi}{\omega_0}
$$

Chu kỳ **tăng** khi biên độ tăng (đây là hiệu ứng phi tuyến — G.2 sẽ giải thích vì sao xấp xỉ góc nhỏ chỉ đúng khi $\theta_0$ nhỏ).

## E.1.b.4. Ví dụ minh họa E.1.b — phương trình không phải dạng $y''=f(y)$

$$
\frac{d^2y(t)}{dt^2} + \left(\frac{dy(t)}{dt}\right)^2 = 0
$$

Đặt $p(y) = \dfrac{dy(t)}{dt}$, $\dfrac{d^2y(t)}{dt^2} = p\,\dfrac{dp}{dy}$:

$$
p\,\frac{dp}{dy} + p^2 = 0
$$

Với $p \neq 0$: $\dfrac{dp}{dy} = -p$ → $\dfrac{dp}{p} = -dy$ → $\ln|p| = -y + C$ → $p = Ae^{-y}$.

$$
\frac{dy(t)}{dt} = A e^{-y(t)} \;\Longrightarrow\; e^{y(t)}\, dy = A\, dt \;\Longrightarrow\; e^{y(t)} = At + B
$$

$$
y(t) = \ln|At + B|
$$

(Và $p \equiv 0$ → $y(t) \equiv$ hằng.)

---

# PHẦN G.1 — PHÂN TÍCH ĐỊNH TÍNH BẬC 1: ĐƯỜNG PHA (Phase Line)

> Nhiều bài không yêu cầu nghiệm tường minh — chỉ hỏi **hành vi** của nghiệm. Phân tích định tính trả lời câu hỏi đó mà không cần giải.

## G.1.1. Dạng autonomous bậc 1

$$
\frac{dy(t)}{dt} = f\big(y(t)\big)
$$

Không phụ thuộc $t$ tường minh.

## G.1.2. Thuật toán phân tích đường pha

**Bước 1.** Tìm **điểm cân bằng** (equilibrium points): giải $f(y^*) = 0$. Mỗi $y^*$ cho nghiệm hằng $y(t) \equiv y^*$.

**Bước 2.** Xét dấu $f(y)$ giữa các điểm cân bằng:
- $f(y) > 0$ → $y(t)$ **tăng**,
- $f(y) < 0$ → $y(t)$ **giảm**.

**Bước 3.** Phân loại ổn định:
- $f'(y^*) < 0$ → **ổn định tiệm cận** (asymptotically stable): nghiệm gần $y^*$ sẽ **tiến về** $y^*$.
- $f'(y^*) > 0$ → **không ổn định** (unstable): nghiệm gần $y^*$ sẽ **rời xa**.
- $f'(y^*) = 0$ → cần xét thêm (dùng đạo hàm bậc cao hơn, hoặc xét dấu hai bên).

**Bước 4.** Nghiệm **đơn điệu** trên từng khoảng giữa các điểm cân bằng (do tính duy nhất nghiệm — các đường nghiệm không cắt nhau). Do đó nghiệm **không thể vượt qua** một điểm cân bằng.

## G.1.3. Ví dụ — Logistic

$$
\frac{dN(t)}{dt} = r\, N(t)\left(1 - \frac{N(t)}{K}\right), \quad r, K > 0
$$

Điểm cân bằng: $N^* = 0$ và $N^* = K$.

Đạo hàm:

$$
f'(N) = r - \frac{2rN}{K}
$$

- $f'(0) = r > 0$ → **không ổn định**.
- $f'(K) = -r < 0$ → **ổn định tiệm cận**.

**Kết luận:**
- Nếu $0 < N(0) < K$: $N(t)$ **tăng đơn điệu** → $K$.
- Nếu $N(0) > K$: $N(t)$ **giảm đơn điệu** → $K$.
- Nếu $N(0) = 0$: $N(t) \equiv 0$ (nghiệm hằng, không bao giờ lớn lên).
- Nếu $N(0) < 0$: không có ý nghĩa sinh học.

Đây chính là mô hình tăng trưởng dân số có giới hạn — **cùng một kết luận định tính** như nghiệm tường minh ở D.6.4, nhưng **không cần giải**.

## G.1.4. Ví dụ — Phân rã phóng xạ

$$
\frac{dN(t)}{dt} = -\lambda\, N(t), \quad \lambda > 0
$$

Điểm cân bằng duy nhất $N^* = 0$, $f'(0) = -\lambda < 0$ → **ổn định tiệm cận**.

Kết luận: mọi nghiệm dương đều giảm đơn điệu về $0$ khi $t \to \infty$ (khớp nghiệm $N_0 e^{-\lambda t}$ ở D.2.3).

---

# PHẦN G.2 — TUYẾN TÍNH HÓA / DAO ĐỘNG BÉ

> Đây là kỹ thuật **quan trọng bậc nhất** cho HSGQG Vật lý: mọi bài dao động nhỏ quanh cân bằng đều dùng nó.

## G.2.1. Bài toán đặt ra

Cho hệ cơ học một chiều:

$$
m\,\frac{d^2x(t)}{dt^2} = F\big(x(t)\big) = -\frac{dV(x)}{dx}\Big|_{x=x(t)}
$$

Phương trình này **thường không giải được** bằng hàm sơ cấp (ví dụ con lắc đơn với $\sin\theta$). Nhưng nếu ta chỉ quan tâm **dao động bé quanh vị trí cân bằng**, có thể **tuyến tính hóa**.

## G.2.2. Thuật toán

**Bước 1.** Tìm **điểm cân bằng** $x^*$: giải $F(x^*) = 0$, tức $V'(x^*) = 0$.

**Bước 2.** Khai triển Taylor $V(x)$ quanh $x^*$:

$$
V(x) = V(x^*) + V'(x^*)(x - x^*) + \frac{1}{2}V''(x^*)(x - x^*)^2 + \frac{1}{6}V'''(x^*)(x - x^*)^3 + \cdots
$$

Vì $V'(x^*) = 0$:

$$
V(x) \approx V(x^*) + \frac{1}{2}V''(x^*)(x - x^*)^2
$$

**Bước 3.** Đặt $\xi(t) = x(t) - x^*$ (độ lệch khỏi cân bằng, hàm của $t$). Khi đó:

$$
m\,\frac{d^2\xi(t)}{dt^2} = -\frac{dV}{dx}\Big|_{x = x^* + \xi} \approx -V''(x^*)\, \xi(t)
$$

$$
\boxed{\,m\,\frac{d^2\xi(t)}{dt^2} + V''(x^*)\, \xi(t) = 0\,}
$$

**Bước 4.** Đây là phương trình dao động điều hòa với:

$$
\boxed{\,\omega^2 = \frac{V''(x^*)}{m}\,}
$$

**Bước 5.** Phân loại:
- $V''(x^*) > 0$ → $x^*$ là **cực tiểu** $V$ → **cân bằng ổn định**, dao động điều hòa tần số $\omega$.
- $V''(x^*) < 0$ → $x^*$ là **cực đại** $V$ → **cân bằng không ổn định**, nghiệm $\xi(t) \sim e^{\pm\sqrt{|V''|/m}\, t}$ (tăng/giảm theo hàm mũ).
- $V''(x^*) = 0$ → cần giữ số hạng bậc cao hơn (dao động **không điều hòa**, chu kỳ **phụ thuộc biên độ**).

## G.2.3. Điều kiện hợp lệ (Pre)

Tuyến tính hóa chỉ đúng khi **biên độ đủ nhỏ** để bỏ số hạng $O(\xi^3)$. Cụ thể:

$$
\frac{|V'''(x^*)|\, |\xi|}{|V''(x^*)|} \ll 1
$$

Khi điều kiện này **không thỏa**, phải dùng phương pháp phi tuyến (E.1.c hoặc perturbation).

## G.2.4. Ví dụ 1 — Con lắc đơn

$$
\frac{d^2\theta(t)}{dt^2} = -\frac{g}{L}\sin\theta(t)
$$

Viết dưới dạng $m\dfrac{d^2\theta(t)}{dt^2} = F(\theta)$ với $F(\theta) = -mg\sin\theta/L$: coi "$m$" ở đây là $1$, lực là $-g\sin\theta/L$.

"Thế năng" (tích phân âm của lực):

$$
V(\theta) = -\frac{g}{L}\cos\theta
$$

Cân bằng: $\sin\theta^* = 0$ → $\theta^* = 0, \pm\pi, \pm 2\pi, \dots$

Đạo hàm bậc 2:

$$
V''(\theta) = \frac{g}{L}\cos\theta
$$

- $V''(0) = g/L > 0$ → **ổn định**, $\omega = \sqrt{g/L}$ (dao động nhỏ quanh VTCB).
- $V''(\pm\pi) = -g/L < 0$ → **không ổn định** (con lắc dựng ngược).

Kết quả $\omega = \sqrt{g/L}$ chính là công thức chu kỳ con lắc đơn quen thuộc.

## G.2.5. Ví dụ 2 — Hạt trong thế $V(x) = V_0\left[(x/a)^4 - 2(x/a)^2\right]$

Tính:

$$
V'(x) = V_0\left(\frac{4x^3}{a^4} - \frac{4x}{a^2}\right) = \frac{4V_0}{a^2}\left(\frac{x^3}{a^2} - x\right) = \frac{4V_0 x}{a^2}\left(\frac{x^2}{a^2} - 1\right)
$$

Cân bằng: $x^* = 0$, $x^* = \pm a$.

$$
V''(x) = V_0\left(\frac{12x^2}{a^4} - \frac{4}{a^2}\right) = \frac{4V_0}{a^2}\left(\frac{3x^2}{a^2} - 1\right)
$$

- $V''(0) = -4V_0/a^2 < 0$ → **không ổn định** (cực đại).
- $V''(\pm a) = \dfrac{4V_0}{a^2}(3 - 1) = 8V_0/a^2 > 0$ → **ổn định** (cực tiểu), $\omega = \sqrt{\dfrac{8V_0}{ma^2}}$.

Đây là mô hình **lưỡng thế** (double-well potential) — xuất hiện trong nhiều bài Vật lý.

## G.2.6. Ví dụ 3 — Hai lò xo, một khối lượng (không cần thiết, nhưng hữu ích)

Một vật khối lượng $m$ gắn vào hai lò xo có độ cứng $k_1$, $k_2$ nối tiếp với hai tường. Cân bằng tại $x^*=0$ (giữa hai tường). Với độ dời $\xi$, lực hồi phục là $-(k_1 + k_2)\xi$ → $\omega = \sqrt{(k_1+k_2)/m}$.

Đây là trường hợp đơn giản nhất của **dao động nhỏ** — ta sẽ tổng quát hóa cho hệ nhiều bậc tự do ở Phần Hệ PTVP.

---

# PHẦN G.3 — MẶT PHẲNG PHA (Phase Plane)

> Mở rộng của đường pha (G.1) cho hệ 2 chiều — cần thiết khi PTVP bậc 2 autonomous: $\dfrac{d^2x(t)}{dt^2} = f\big(x(t), \dfrac{dx(t)}{dt}\big)$.

## G.3.1. Chuyển hệ bậc 2 về hệ 2 PTVP bậc 1

Đặt:

$$
u(t) = x(t), \quad w(t) = \frac{dx(t)}{dt}
$$

Khi đó:

$$
\begin{cases} \dfrac{du(t)}{dt} = w(t) \\[8pt] \dfrac{dw(t)}{dt} = f\big(u(t), w(t)\big) \end{cases}
$$

Đây là hệ autonomous bậc 1 với hai ẩn $u(t)$, $w(t)$. Mặt phẳng $(u, w)$ gọi là **mặt phẳng pha** (phase plane), đường cong $(u(t), w(t))$ gọi là **quỹ đạo pha** (phase trajectory).

## G.3.2. Trường hợp cơ học bảo toàn

Với $m\dfrac{d^2x(t)}{dt^2} = F(x(t)) = -V'(x(t))$, năng lượng $E = \dfrac{1}{2}m\left(\dfrac{dx(t)}{dt}\right)^2 + V(x)$ **bảo toàn**. Do đó quỹ đạo pha là **đường mức năng lượng**:

$$
\frac{1}{2}m\, [w(t)]^2 + V\big(u(t)\big) = E
$$

Mỗi giá trị $E$ cho một quỹ đạo khép kín hoặc không khép kín.

## G.3.3. Phân loại điểm cân bằng

Tại điểm cân bằng $(u^*, w^*) = (x^*, 0)$ với $V'(x^*) = 0$. Tuyến tính hóa (như G.2) cho hệ:

$$
\frac{d}{dt}\begin{pmatrix} \xi \\ \eta \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ -V''(x^*)/m & 0 \end{pmatrix}\begin{pmatrix} \xi \\ \eta \end{pmatrix}
$$

Trị riêng: $\lambda^2 = -V''(x^*)/m$.

| $V''(x^*)$ | Trị riêng | Loại điểm cân bằng |
|---|---|---|
| $> 0$ (cực tiểu) | $\lambda = \pm i\sqrt{V''/m}$ (thuần ảo) | **Tâm** (center) — quỹ đạo là ellipse khép kín |
| $< 0$ (cực đại) | $\lambda = \pm\sqrt{\|V''\|/m}$ (thực, trái dấu) | **Điểm yên** (saddle) — không ổn định |

## G.3.4. Phân loại điểm cân bằng tổng quát (có ma sát hoặc hệ không bảo toàn)

Cho hệ tuyến tính hóa tại điểm cân bằng:

$$
\frac{d}{dt}\begin{pmatrix} \xi \\ \eta \end{pmatrix} = J\begin{pmatrix} \xi \\ \eta \end{pmatrix}, \quad J = \begin{pmatrix} J_{11} & J_{12} \\ J_{21} & J_{22} \end{pmatrix}
$$

Gọi $\lambda_1, \lambda_2$ là trị riêng của $J$:

| Trị riêng | Loại |
|---|---|
| $\lambda_1, \lambda_2$ thực, cùng dấu âm | **Nút ổn định** (stable node) |
| $\lambda_1, \lambda_2$ thực, cùng dấu dương | **Nút không ổn định** (unstable node) |
| $\lambda_1, \lambda_2$ thực, trái dấu | **Điểm yên** (saddle) — không ổn định |
| $\lambda = \alpha \pm i\beta$, $\alpha < 0$ | **Tiêu điểm ổn định** (stable spiral/focus) |
| $\lambda = \alpha \pm i\beta$, $\alpha > 0$ | **Tiêu điểm không ổn định** |
| $\lambda = \pm i\beta$ thuần ảo | **Tâm** (center) |

## G.3.5. Ví dụ — Dao động tắt dần

$$
\frac{d^2x(t)}{dt^2} + 2\delta\,\frac{dx(t)}{dt} + \omega_0^2 x(t) = 0
$$

Hệ 2 chiều: $u(t) = x(t)$, $w(t) = \dfrac{dx(t)}{dt}$:

$$
\frac{du(t)}{dt} = w(t), \quad \frac{dw(t)}{dt} = -\omega_0^2 u(t) - 2\delta w(t)
$$

Ma trận:

$$
J = \begin{pmatrix} 0 & 1 \\ -\omega_0^2 & -2\delta \end{pmatrix}
$$

Trị riêng: $\lambda^2 + 2\delta\lambda + \omega_0^2 = 0$.

- $\delta < \omega_0$ (underdamped): $\lambda = -\delta \pm i\omega_d$ → $\alpha = -\delta < 0$ → **tiêu điểm ổn định** (xoắn vào gốc).
- $\delta = \omega_0$ (critical): $\lambda = -\delta$ (kép) → **nút ổn định** (degenerate).
- $\delta > \omega_0$ (overdamped): $\lambda_{1,2}$ thực âm → **nút ổn định**.
- $\delta = 0$ (không ma sát): $\lambda = \pm i\omega_0$ → **tâm**.

Điều này khớp với E.2.6: ba chế độ tắt dần tương ứng với ba loại điểm cân bằng.

## G.3.6. Separatrix (đường phân cách)

Với hệ bảo toàn có cả cực tiểu và cực đại thế năng, tồn tại **đường phân cách** — quỹ đạo nối hai điểm yên qua điểm cực đại thế. Nó **chia mặt phẳng pha thành hai vùng**:
- Vùng bên trong: quỹ đạo khép kín (dao động).
- Vùng bên ngoài: quỹ đạo không khép kín (chuyển động không tuần hoàn).

**Ví dụ con lắc:** separatrix tương ứng $E = 2mgL$ (đủ năng lượng để con lắc quay hết vòng). Phía dưới: dao động tuần hoàn; phía trên: quay liên tục.

---

# PHẦN HỆ PTVP VÀ NORMAL MODES

> **Đây là phần quan trọng nhất cho HSGQG Vật lý** — vì hầu hết hệ nhiều bậc tự do (nhiều vật nối lò xo, mạch điện nhiều vòng, dao động phân tử, mạng tinh thể) đều là **hệ PTVP**, và nghiệm của chúng được phân tích thành **normal modes**.

## H.1. Hệ PTVP là gì?

**Hệ PTVP** (system of ODEs) là tập hợp nhiều PTVP liên kết với nhau, trong đó có nhiều hàm ẩn **cùng xuất hiện**.

Ví dụ — hai vật nối lò xo:

$$
\begin{cases} m_1\dfrac{d^2 x_1(t)}{dt^2} = -k_1 x_1(t) + k_2\big(x_2(t) - x_1(t)\big) \\[8pt] m_2\dfrac{d^2 x_2(t)}{dt^2} = -k_2\big(x_2(t) - x_1(t)\big) \end{cases}
$$

Hai hàm ẩn $x_1(t)$, $x_2(t)$ liên kết với nhau.

## H.2. Dạng ma trận — hệ bậc 1

Mọi hệ PTVP tuyến tính bậc 1 với $n$ ẩn có thể viết:

$$
\frac{d\mathbf{x}(t)}{dt} = A\,\mathbf{x}(t) + \mathbf{b}(t)
$$

trong đó:
- $\mathbf{x}(t) = \begin{pmatrix} x_1(t) \\ x_2(t) \\ \vdots \\ x_n(t) \end{pmatrix}$ — vector hàm,
- $A$ — ma trận hằng $n \times n$,
- $\mathbf{b}(t)$ — vector hàm cho trước.

Nếu $\mathbf{b}(t) \equiv \mathbf{0}$: **hệ thuần nhất** (homogeneous system).

## H.3. Hệ thuần nhất — Trị riêng và vector riêng

Xét:

$$
\frac{d\mathbf{x}(t)}{dt} = A\,\mathbf{x}(t)
$$

**Ý tưởng:** thử nghiệm $\mathbf{x}(t) = \mathbf{v}\, e^{\lambda t}$ với $\mathbf{v}$ là vector hằng (không phụ thuộc $t$), $\lambda$ là số. Thay vào:

$$
\lambda\, \mathbf{v}\, e^{\lambda t} = A\, \mathbf{v}\, e^{\lambda t} \;\Longrightarrow\; A\, \mathbf{v} = \lambda\, \mathbf{v}
$$

Đây chính là **bài toán trị riêng** (eigenvalue problem). $\lambda$ — **trị riêng**, $\mathbf{v}$ — **vector riêng**.

**Nghiệm tổng quát** khi $A$ có $n$ trị riêng **phân biệt** $\lambda_1, \dots, \lambda_n$:

$$
\boxed{\,\mathbf{x}(t) = C_1\, e^{\lambda_1 t}\, \mathbf{v}_1 + C_2\, e^{\lambda_2 t}\, \mathbf{v}_2 + \cdots + C_n\, e^{\lambda_n t}\, \mathbf{v}_n\,}
$$

trong đó $C_1, \dots, C_n$ là hằng số xác định từ điều kiện đầu.

## H.4. Trị riêng phức

Nếu $\lambda = \alpha \pm i\beta$ (phức liên hợp), vector riêng $\mathbf{v} = \mathbf{a} \pm i\mathbf{b}$, nghiệm thực:

$$
\mathbf{x}(t) = e^{\alpha t}\Big[C_1\big(\mathbf{a}\cos(\beta t) - \mathbf{b}\sin(\beta t)\big) + C_2\big(\mathbf{a}\sin(\beta t) + \mathbf{b}\cos(\beta t)\big)\Big]
$$

Đây là **dao động tắt dần** (nếu $\alpha < 0$) hoặc **tăng dần** (nếu $\alpha > 0$), hoặc **điều hòa** (nếu $\alpha = 0$).

## H.5. Trị riêng bội

Nếu $\lambda$ bội $m$:
- Nếu $A$ có $m$ vector riêng độc lập: dùng $m$ nghiệm $e^{\lambda t}\mathbf{v}_i$.
- Nếu ít hơn (defective): phải dùng thêm nghiệm dạng $t\, e^{\lambda t}\mathbf{v}$, $t^2 e^{\lambda t}\mathbf{v}$, … (generalized eigenvectors).

## H.6. Dao động tử ghép — Normal Modes

> Đây là **ứng dụng quan trọng nhất** cho Vật lý.

## H.6.1. Bài toán

Hệ $n$ khối lượng ghép với nhau bằng lò xo. Phương trình:

$$
M\,\frac{d^2\mathbf{x}(t)}{dt^2} = -K\,\mathbf{x}(t)
$$

trong đó:
- $\mathbf{x}(t)$ — vector vị trí (hàm của $t$),
- $M$ — ma trận khối lượng (thường là đường chéo),
- $K$ — ma trận độ cứng (symmetric, positive definite).

## H.6.2. Tìm normal modes

**Bước 1.** Thử $\mathbf{x}(t) = \mathbf{v}\, e^{i\omega t}$ (dao động điều hòa với tần số $\omega$):

$$
-M\,\omega^2\, \mathbf{v}\, e^{i\omega t} = -K\, \mathbf{v}\, e^{i\omega t}
$$

$$
\boxed{\,\big(K - \omega^2 M\big)\,\mathbf{v} = 0\,}
$$

**Bước 2.** Đây là **bài toán trị riêng tổng quát** (generalized eigenvalue problem). Nghiệm không tầm thường tồn tại khi:

$$
\det\big(K - \omega^2 M\big) = 0
$$

Đây là **phương trình đặc trưng**, cho $n$ giá trị $\omega_1^2, \dots, \omega_n^2$ — gọi là các **tần số riêng** (eigenfrequencies, normal frequencies).

**Bước 3.** Với mỗi $\omega_i^2$, giải $(K - \omega_i^2 M)\mathbf{v}_i = 0$ để tìm **vector riêng** (mode shape) $\mathbf{v}_i$.

**Bước 4.** Mỗi cặp $(\omega_i^2, \mathbf{v}_i)$ xác định một **normal mode** — một kiểu dao động đặc biệt mà **tất cả các khối lượng dao động cùng tần số $\omega_i$, cùng pha hoặc ngược pha**.

**Bước 5.** Nghiệm tổng quát:

$$
\mathbf{x}(t) = \sum_{i=1}^{n} \mathbf{v}_i\big[A_i\cos(\omega_i t) + B_i\sin(\omega_i t)\big]
$$

trong đó $A_i$, $B_i$ xác định từ điều kiện đầu.

## H.6.3. Ý nghĩa Vật lý của normal modes

- **Normal mode** = "kiểu rung tự nhiên" của hệ.
- **Tần số riêng** $\omega_i$ = tần số rung của mode $i$.
- **Mode shape** $\mathbf{v}_i$ = hình dạng biến dạng của mode $i$.

Bất kỳ chuyển động nào của hệ đều có thể phân tích thành tổng các normal modes (nguyên lý chồng chất). Đây là nền tảng của:
- Dao động phân tử (spectroscopy),
- Mạng tinh thể (phonon),
- Cầu dao động (kỹ thuật xây dựng),
- Mạch điện nhiều vòng.

## H.6.4. Ví dụ cụ thể — Hai khối lượng, ba lò xo

Hai vật khối lượng $m$ bằng nhau, ba lò xo cùng độ cứng $k$: lò xo 1 nối tường trái – vật 1, lò xo 2 nối vật 1 – vật 2, lò xo 3 nối vật 2 – tường phải.

**Phương trình:**

$$
\begin{cases} m\dfrac{d^2 x_1(t)}{dt^2} = -k x_1(t) + k\big(x_2(t) - x_1(t)\big) = -2k x_1(t) + k x_2(t) \\[8pt] m\dfrac{d^2 x_2(t)}{dt^2} = -k\big(x_2(t) - x_1(t)\big) - k x_2(t) = k x_1(t) - 2k x_2(t) \end{cases}
$$

**Dạng ma trận:**

$$
M\,\frac{d^2\mathbf{x}(t)}{dt^2} = -K\,\mathbf{x}(t), \quad M = m\, I, \quad K = \begin{pmatrix} 2k & -k \\ -k & 2k \end{pmatrix}
$$

**Phương trình đặc trưng:**

$$
\det(K - m\omega^2 I) = \begin{vmatrix} 2k - m\omega^2 & -k \\ -k & 2k - m\omega^2 \end{vmatrix} = (2k - m\omega^2)^2 - k^2 = 0
$$

$$
2k - m\omega^2 = \pm k \;\Longrightarrow\; \omega^2 = \frac{2k \mp k}{m}
$$

$$
\omega_1^2 = \frac{k}{m}, \quad \omega_2^2 = \frac{3k}{m}
$$

**Vector riêng:**

Với $\omega_1^2 = k/m$:

$$
(K - m\omega_1^2 I)\mathbf{v}_1 = \begin{pmatrix} k & -k \\ -k & k \end{pmatrix}\mathbf{v}_1 = 0 \;\Longrightarrow\; \mathbf{v}_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}
$$

Với $\omega_2^2 = 3k/m$:

$$
(K - m\omega_2^2 I)\mathbf{v}_2 = \begin{pmatrix} -k & -k \\ -k & -k \end{pmatrix}\mathbf{v}_2 = 0 \;\Longrightarrow\; \mathbf{v}_2 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}
$$

**Hai normal modes:**

| Mode | $\omega$ | Mode shape | Ý nghĩa |
|---|---|---|---|
| Mode 1 | $\sqrt{k/m}$ | $(1, 1)$ | Hai vật dao động **cùng pha**, cùng biên độ. Lò xo giữa **không biến dạng** (khoảng cách hai vật không đổi). Tần số bằng tần số của một vật đơn gắn một lò xo. |
| Mode 2 | $\sqrt{3k/m}$ | $(1, -1)$ | Hai vật dao động **ngược pha**, cùng biên độ. Lò xo giữa **bị nén/giãn mạnh**. Tần số cao hơn. |

**Nghiệm tổng quát:**

$$
\begin{pmatrix} x_1(t) \\ x_2(t) \end{pmatrix} = C_1\begin{pmatrix} 1 \\ 1 \end{pmatrix}\cos\!\left(\sqrt{\tfrac{k}{m}}\, t + \varphi_1\right) + C_2\begin{pmatrix} 1 \\ -1 \end{pmatrix}\cos\!\left(\sqrt{\tfrac{3k}{m}}\, t + \varphi_2\right)
$$

Hằng số $C_1$, $C_2$, $\varphi_1$, $\varphi_2$ xác định từ điều kiện đầu $x_1(0)$, $x_2(0)$, $\dfrac{dx_1(t)}{dt}\Big|_{t=0}$, $\dfrac{dx_2(t)}{dt}\Big|_{t=0}$.

## H.6.5. Nhận xét vật lý quan trọng

- **Số normal modes = số bậc tự do.** Hệ hai vật → hai modes.
- **Mode có tần số thấp hơn** thường là mode "đồng bộ" (các vật chuyển động cùng nhau).
- **Mode có tần số cao hơn** thường là mode "đối kháng" (các vật chuyển động ngược chiều).
- **Chuyển động bất kỳ** = chồng chất các modes với biên độ khác nhau. Đây là **nguyên lý Fourier** của dao động.

## H.6.6. Phương pháp khử (Elimination) — cách khác tìm cùng kết quả

Thay vì ma trận, có thể dùng **phương pháp khử** để đưa hệ về một PTVP bậc cao.

**Ví dụ trên:** Từ phương trình 2:

$$
x_1(t) = \frac{m}{k}\,\frac{d^2 x_2(t)}{dt^2} + 2x_2(t)
$$

Đạo hàm 2 lần theo $t$:

$$
\frac{d^2 x_1(t)}{dt^2} = \frac{m}{k}\,\frac{d^4 x_2(t)}{dt^4} + 2\,\frac{d^2 x_2(t)}{dt^2}
$$

Thay vào phương trình 1:

$$
m\left(\frac{m}{k}\,\frac{d^4 x_2(t)}{dt^4} + 2\,\frac{d^2 x_2(t)}{dt^2}\right) = -2k\left(\frac{m}{k}\,\frac{d^2 x_2(t)}{dt^2} + 2x_2(t)\right) + k\, x_2(t)
$$

$$
\frac{m^2}{k}\,\frac{d^4 x_2(t)}{dt^4} + 2m\,\frac{d^2 x_2(t)}{dt^2} = -2m\,\frac{d^2 x_2(t)}{dt^2} - 4k\, x_2(t) + k\, x_2(t)
$$

$$
\frac{m^2}{k}\,\frac{d^4 x_2(t)}{dt^4} + 4m\,\frac{d^2 x_2(t)}{dt^2} + 3k\, x_2(t) = 0
$$

Nhân với $k/m^2$:

$$
\frac{d^4 x_2(t)}{dt^4} + \frac{4k}{m}\,\frac{d^2 x_2(t)}{dt^2} + \frac{3k^2}{m^2}\, x_2(t) = 0
$$

Đặc trưng: $\lambda^4 + \dfrac{4k}{m}\lambda^2 + \dfrac{3k^2}{m^2} = 0$. Đặt $y = \lambda^2$:

$$
y^2 + \frac{4k}{m}y + \frac{3k^2}{m^2} = 0 \;\Longrightarrow\; y = \frac{-4k/m \pm \sqrt{16k^2/m^2 - 12k^2/m^2}}{2} = \frac{-4k/m \pm 2k/m}{2}
$$

$$
y_1 = -\frac{k}{m}, \quad y_2 = -\frac{3k}{m}
$$

$$
\lambda = \pm i\sqrt{\frac{k}{m}}, \quad \pm i\sqrt{\frac{3k}{m}}
$$

Hai tần số: $\omega_1 = \sqrt{k/m}$, $\omega_2 = \sqrt{3k/m}$ — **khớp với phương pháp ma trận**.

**Kết luận:** Phương pháp ma trận **hiệu quả hơn** (tự nhiên cho ra tất cả các modes cùng lúc), nhưng phương pháp khử hữu ích khi hệ chỉ có 2 ẩn và ta muốn tránh đại số tuyến tính phức tạp.

## H.6.7. Hệ PTVP bậc 1 không thuần nhất

$$
\frac{d\mathbf{x}(t)}{dt} = A\,\mathbf{x}(t) + \mathbf{b}(t)
$$

Cấu trúc nghiệm tương tự E.3:

$$
\mathbf{x}(t) = \mathbf{x}_h(t) + \mathbf{x}_p(t)
$$

- $\mathbf{x}_h(t)$ — nghiệm tổng quát của hệ thuần nhất (như H.3).
- $\mathbf{x}_p(t)$ — một nghiệm riêng. Có thể tìm bằng **biến thiên hằng số**:

$$
\mathbf{x}_p(t) = \Phi(t)\int \Phi^{-1}(s)\,\mathbf{b}(s)\,ds
$$

trong đó $\Phi(t)$ là **ma trận cơ bản** (fundamental matrix) — ma trận mà các cột là $n$ nghiệm độc lập tuyến tính của hệ thuần nhất.

---

# TỔNG KẾT — SƠ ĐỒ QUYẾT ĐỊNH

```
Bậc 1
├── Vế phải chỉ chứa t: y'(t) = f(t)          → D.1  Tích phân trực tiếp
├── Tách được: y'(t) = f(t)·g(y(t))            → D.2  Tách biến
├── Tuyến tính: y'(t) + p(t)·y(t) = q(t)       → D.3  Integrating factor
└── Bernoulli: y'(t) + p(t)·y(t) = q(t)·[y(t)]^n → D.6  Thế z = y^(1-n)

Bậc 2
├── Tuyến tính, hệ số hằng
│   ├── Thuần nhất: a·y''(t) + b·y'(t) + c·y(t) = 0  → E.2  Đặc trưng
│   └── Không thuần nhất: ... = f(t)                   → E.3  y = y_h + y_p
└── Phi tuyến
    ├── Vắng t: F(y(t), y'(t), y''(t)) = 0     → E.1.b  p = y'(t), y'' = p·dp/dy
    └── y''(t) = f(y(t))                       → E.1.c  Tích phân năng lượng

Không giải được / chỉ hỏi hành vi
├── Bậc 1 autonomous: y'(t) = f(y(t))          → G.1  Đường pha
├── Bậc 2 quanh cân bằng                       → G.2  Tuyến tính hóa, ω² = V''(x*)/m
└── Hệ 2 chiều                                 → G.3  Mặt phẳng pha

Hệ PTVP / nhiều bậc tự do
└── Ma trận: dX(t)/dt = A·X(t)                 → H.  Trị riêng, vector riêng
    Dao động tử ghép: M·X''(t) = -K·X(t)         → H.6  Normal modes
```

## Bảng tra nhanh

| Dạng | Nhận diện | Phương pháp | Nghiệm |
|---|---|---|---|
| D.1 | $y'(t) = f(t)$ | Tích phân trực tiếp | $y(t) = \int f\,dt + C$ |
| D.2 | $y'(t) = f(t)g(y(t))$ | Tách biến | $\int dy/g = \int f\,dt + C$ |
| D.3 | $y'(t) + p(t)y(t) = q(t)$ | $\mu(t) = e^{\int p\,dt}$ | $y = \mu^{-1}[\int \mu q\,dt + C]$ |
| D.6 | $y'(t) + p(t)y(t) = q(t)y(t)^n$ | $z = y^{1-n}$ | Chuyển về D.3 |
| E.2 | $a y''(t) + b y'(t) + c y(t) = 0$ | Đặc trưng $a\lambda^2+b\lambda+c=0$ | Theo $\Delta$ |
| E.3 | $a y''(t) + b y'(t) + c y(t) = f(t)$ | Hệ số bất định | $y = y_h + y_p$ |
| E.1.b | $F(y(t), y'(t), y''(t)) = 0$ | $p = y'(t)$, $y'' = p\,dp/dy$ | Hạ về bậc 1 |
| E.1.c | $y''(t) = f(y(t))$ | Tích phân năng lượng | $\frac{1}{2}y'^2 = \int f\,dy + E$ |
| G.1 | $y'(t) = f(y(t))$ | Đường pha | Điểm cân bằng, dấu $f$ |
| G.2 | $my''(t) = -V'(y)$ quanh cân bằng | Tuyến tính hóa | $\omega^2 = V''(y^*)/m$ |
| G.3 | Hệ 2 chiều autonomous | Mặt phẳng pha | Trị riêng Jacobi |
| H. | $d\mathbf{X}(t)/dt = A\mathbf{X}(t)$ | Trị riêng, vector riêng | $\sum C_i e^{\lambda_i t}\mathbf{v}_i$ |
| H.6 | $M\mathbf{X}''(t) = -K\mathbf{X}(t)$ | Generalized eigenvalue | Normal modes $(\omega_i, \mathbf{v}_i)$ |

---

## LỜI KẾT

PTVP không phải "30 dạng cần học thuộc". Nó là **ngôn ngữ của sự biến thiên cục bộ** — ngôn ngữ mà Vũ trụ buộc phải dùng vì tốc độ ánh sáng hữu hạn. Giải PTVP là:

1. **Dựng** đúng luật cục bộ từ Vật lý (khó nhất, quyết định đáp án).
2. **Nhận diện** đối xứng/bất biến của phương trình (mỗi phương pháp D.1–D.6, E.2–E.3, E.1.b–E.1.c là một **đối xứng** được khai thác).
3. **Khai thác** đối xứng để hạ bậc hoặc tuyến tính hóa (G.2 là ví dụ đẹp nhất: đối xứng quanh cân bằng → dao động điều hòa).
4. **Kiểm chứng** bằng thế ngược, thứ nguyên, giới hạn.

Với **hệ PTVP và normal modes**: đây là bước nhảy từ "một vật" sang "nhiều vật". Mọi hệ nhiều bậc tự do tuyến tính đều có thể **phân rã** thành các normal modes độc lập — mỗi mode là một bài toán một bậc tự do. Đó là phép màu của **đại số tuyến tính** áp vào Vật lý.

Hãy tự tay giải lại mọi ví dụ trên giấy trắng. **Hiểu ≠ Làm được.**
