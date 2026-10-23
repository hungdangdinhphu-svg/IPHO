---

## PHẦN 3: THUẬT TOÁN L (BẢN NHÁP)

### 3.1. Bước 0: kiểm tra Pre (bốn câu hỏi có/không)

Trả lời **từng câu**, ghi ra giấy nháp:

| # | Câu hỏi | Nếu "Không" |
|---|---|---|
| P1 | PT/hệ có **tuyến tính** không? (ẩn và đạo hàm chỉ xuất hiện bậc 1, không nhân với nhau, không nằm trong $\sin y$, $y^2$, $\dot y^2$,...) | **Dừng.** Không dùng Laplace. Xem lại mô hình (có tuyến tính hóa hợp lệ được không?). |
| P2 | **Hệ số có hằng không?** (không có $t$ nhân với $y$ hoặc $y'$, khối lượng/điện trở/độ cứng không đổi theo thời gian) | **Dừng.** Với bậc 1: dùng thừa số tích phân $e^{\int p\,dt}$. Xem Phần 9. |
| P3 | Có **điều kiện đầu tại $t=0$** không? Đủ $n$ điều kiện cho PT bậc $n$ không? | Dịch gốc thời gian về sự kiện (công tắc), hoặc tìm điều kiện đầu từ vật lý (xem 3.5). |
| P4 | Lực/nguồn ngoài có thuộc bảng tra (hoặc tổ hợp tuyến tính của chúng) không? | Nếu là $1/t$, $\tan t$, $\ln t$...: không dùng Laplace; dùng biến thiên hằng số. |

**Chỉ khi cả bốn đều "Có"** mới sang bước 1.

### 3.2. Các bước

Với PT bậc 2 tổng quát $a\,y''+b\,y'+c\,y=f(t)$, $y(0)=y_0$, $y'(0)=v_0$.

| Bước | Việc làm | Kết quả |
|---|---|---|
| **L1** | Laplace hai vế, thay $y\to Y$, $y'\to sY-y_0$, $y''\to s^2Y-sy_0-v_0$, $f\to F(s)$. | Phương trình đại số theo $Y$. |
| **L2** | Gom $Y$: $\;(as^2+bs+c)\,Y=F(s)+a(s\,y_0+v_0)+b\,y_0$. | $\;Y(s)=\dfrac{F(s)+a(sy_0+v_0)+by_0}{as^2+bs+c}$ |
| **L3** | **Tách phân thức** (xem 3.3). | $Y=\sum$ các số hạng có trong bảng. |
| **L4** | **Tra bảng ngược** từng số hạng. | $y(t)$. |
| **L5** | **Tự kiểm bằng bất biến** (xem 3.4). | Tin tưởng được đáp án. |
| **L6** | **Phân loại** các số hạng của $y(t)$ thành *phần quá độ* (cực của $P(s)$) và *phần cưỡng bức* (cực của $F(s)$). | Dùng cho bản chép sạch (Phần 4). |

Với PT bậc 1 ($a\,y'+b\,y=f$) thì $P(s)=as+b$ và $Y=\dfrac{F(s)+a\,y_0}{as+b}$.

### 3.3. Tách phân thức: ba quy tắc, không cần số phức

Giả sử $Y(s)=\dfrac{N(s)}{P(s)}$, bậc tử nhỏ hơn bậc mẫu. (Nếu không nhỏ hơn, chia đa thức trước. Với PTVP vật lý thông thường, trường hợp này chỉ xảy ra khi có xung $\delta$.)

**(a) Cực thực đơn.** Mẫu có nhân tử $(s-r)$:
$$\frac{A}{s-r},\qquad A=\Big[(s-r)\,Y(s)\Big]_{s=r}\quad(\text{che nhân tử, thế }s=r).$$

**(b) Cực kép thực.** Mẫu có $(s-r)^2$:
$$\frac{B_1}{s-r}+\frac{B_2}{(s-r)^2},\qquad B_2=\Big[(s-r)^2Y\Big]_{s=r},\quad B_1=\frac{d}{ds}\Big[(s-r)^2Y\Big]_{s=r}.$$

**(c) Nhân tử bậc hai vô nghiệm thực.** Ví dụ $s^2+2\beta s+\omega_0^2$ khi $\beta<\omega_0$:

1. Hoàn thành bình phương: $(s+\beta)^2+\omega^2$ với $\omega=\sqrt{\omega_0^2-\beta^2}$.
2. Viết phần tử dưới dạng $\dfrac{\alpha\,(s+\beta)+\gamma\,\omega}{(s+\beta)^2+\omega^2}$.
3. Tra: $\alpha\,e^{-\beta t}\cos\omega t+\gamma\,e^{-\beta t}\sin\omega t$.

Khi che nhân tử khó (do có nhiều nhân tử), dùng **đồng nhất hệ số**: quy đồng, đồng nhất các lũy thừa của $s$, và dùng cover-up để kiểm tra lại.

### 3.4. Bất biến tự kiểm (những thứ phải luôn đúng)

Các bất biến này dùng để *bắt lỗi* trước khi chép sạch.

| # | Bất biến | Cách dùng |
|---|---|---|
| **I1** | **Mẫu số $Y(s)$ khi đã rút gọn là đa thức đặc trưng** (của PT hoặc của hệ). Nó **không phụ thuộc** điều kiện đầu hay lực ngoài. Chúng chỉ ảnh hưởng tử số. | Nếu mẫu số của bạn khác $as^2+bs+c$ (ngoài các nhân tử thêm từ $F(s)$): sai ở L1 hoặc L2. |
| **I2** | **Số hằng số tự do = bậc PT.** Một PT bậc $n$ thì phần nghiệm thuần nhất có đúng $n$ hằng số, được cố định bởi $n$ điều kiện đầu. | Đếm. |
| **I3** | **Giá trị đầu:** $y(0^+)=\lim_{s\to\infty}sY(s)=y_0$. Với $y'$: $y'(0)=v_0$. | Thế $t=0$ vào $y(t)$ vừa tìm: phải ra điều kiện đầu. |
| **I4** | **Giá trị cuối:** nếu hệ có xác lập, $y(\infty)=\lim_{s\to0}sY(s)$. Với lực không đổi $f_0$: $y(\infty)=f_0/c$ (trạng thái cân bằng tĩnh). | Kiểm tra vật lý: dòng điện cuối $=E/R$, độ dãn cuối $=F/k$,... |
| **I5** | **Thứ nguyên:** mọi số hạng trong $s+a$, $s^2+\omega^2$ cùng thứ nguyên; $y(t)$ có đúng thứ nguyên của ẩn. | Kiểm tra từng nhân tử. |
| **I6** | **Thế ngược vào PT:** $y(t)$ tìm được phải thỏa PT gốc và các điều kiện đầu. | Phép thử cuối cùng, chắc chắn nhất (chỉ cần thế một hai bước). |
| **I7** | **Giới hạn vật lý:** $\beta\to0$ thì dao động không tắt; $k\to\infty$ thì...; tham số $\to$ giá trị đặc biệt thì ra kết quả đã biết. | Tư duy giới hạn đặc biệt (Phần 4.4 của khung). |

### 3.5. Về điều kiện đầu có "nhảy" (cảnh báo)

Công thức $\mathcal L\{y'\}=sY-y(0)$ cần $y$ liên tục tại $t=0$. Trong vật lý, các đại lượng "có quán tính" **không nhảy** khi lực hữu hạn:

- dòng qua cuộn cảm $i_L$, hiệu điện thế trên tụ $u_C$;
- vị trí $x$ và vận tốc $v$ của vật khi lực hữu hạn.

Nếu có **xung** (va chạm cực ngắn, xung dòng) thì đại lượng đó **nhảy** ngay tại $t=0$. Khi đó phải quy về **"điều kiện đầu ngay sau xung"**, được suy từ bảo toàn xung lượng (xem 8.3). Đừng dùng giá trị trước xung cho $y(0)$.

---

## PHẦN 4: QUY TẮC CHÉP SẠCH (TRÌNH BÀY NHƯ THỂ KHÔNG DÙNG LAPLACE)

### 4.1. Ba "không" của bản sạch

1. **Không** có ký hiệu $\mathcal L$, $Y(s)$, "ảnh", "tra bảng".
2. **Không** viết kết quả mà bạn chưa chứng minh được bằng phương pháp cổ điển. Mỗi hằng số phải suy ra từ **đồng nhất hệ số** hoặc **điều kiện đầu** trên giấy.
3. **Không** bỏ bước kiểm tra cuối (thế điều kiện đầu hoặc giới hạn $t\to\infty$) nếu còn thời gian.

Về mặt toán học, bản sạch hoàn toàn chặt chẽ vì **định lý tồn tại và duy nhất** đảm bảo: với PTVP tuyến tính hệ số hằng, có đúng một nghiệm thỏa điều kiện đầu cho trước. Vậy nghiệm tìm được bằng *bất kỳ* đường nào, miễn thỏa PT và điều kiện đầu, **chính là** nghiệm.

### 4.2. Laplace nháp cho bạn gì để chép sạch?

| Việc cần làm trong bản sạch | Laplace nháp cho bạn biết... |
|---|---|
| Chọn **phương pháp** | PT bậc 1: dùng thừa số tích phân. PT bậc 2: nghiệm tổng quát = nghiệm thuần nhất + nghiệm riêng. Hệ: khử. |
| **Dạng nghiệm thuần nhất** | Các cực của $P(s)$: thực phân biệt $\to$ hai mũ; kép $\to(C_1+C_2t)e^{rt}$; phức $\to e^{-\beta t}(C_1\cos+C_2\sin)$. |
| **Dạng nghiệm riêng** (khỏi đoán!) | Các cực của $F(s)$, **bội số cộng thêm** nếu trùng với cực của $P(s)$. |
| **Giá trị các hệ số** | Bạn đã có kết quả để *đối chiếu* khi tự đồng nhất hệ số. Nếu hai bên trùng thì yên tâm. |
| **Có cần xét trường hợp** (cộng hưởng, tắt dần quá mức,...) không | Xem bội của cực. |

### 4.3. Bảng "dạng nghiệm riêng" (suy ra từ cực, khỏi nhớ mẹo)

Gọi $m$ là số lần cực của lực ngoài trùng với nghiệm của phương trình đặc trưng (kể cả bội). Nghiệm riêng $=t^m\times$ (dạng dưới đây):

| Lực ngoài $f(t)$ | Dạng nghiệm riêng ($m=0$) | Khi $m\ge1$ |
|---|---|---|
| hằng $f_0$ | $A$ | $A\,t^m$ (khi $0$ là nghiệm đặc trưng, tức $c=0$) |
| đa thức bậc $n$ | đa thức bậc $n$ đủ hệ số | nhân $t^m$ |
| $e^{-\gamma t}$ | $A e^{-\gamma t}$ | $A\,t^m e^{-\gamma t}$ ($-\gamma$ là nghiệm đặc trưng) |
| $\cos\Omega t$ hoặc $\sin\Omega t$ | $A\cos\Omega t+B\sin\Omega t$ (**cả hai**, dù lực chỉ có một) | $t\,(A\cos+B\sin)$ khi $\pm i\Omega$ là nghiệm đặc trưng |
| $e^{-\gamma t}\cos\Omega t$ | $e^{-\gamma t}(A\cos\Omega t+B\sin\Omega t)$ | nhân $t$ |
| tổng của các loại trên | tổng các nghiệm riêng tương ứng | |

### 4.4. Khuôn chép sạch chung

```
Bước C0. Phát biểu kiểu PT: "PT tuyến tính hệ số hằng bậc n  ⇒  nghiệm thỏa
         điều kiện đầu là duy nhất; nghiệm tổng quát y = y_h + y_p."
Bước C1. Thuần nhất: PT đặc trưng …  ⇒  nghiệm …  ⇒  y_h = …
Bước C2. Nghiệm riêng: dạng … (lý do: lực có dạng …, khác/trùng nghiệm
         đặc trưng). Thế vào PT, đồng nhất hệ số ⇒ …
Bước C3. y = y_h + y_p. Dùng y(0), y'(0) ⇒ các hằng số.
Bước C4. Kiểm tra: (a) thế lại điều kiện đầu; (b) t → ∞;
         (c) thứ nguyên / trường hợp đặc biệt.
```

Với PT bậc 1, thay C0–C2 bằng *thừa số tích phân* (xem 5.1).

---

## PHẦN 5: PTVP BẬC 1 TUYẾN TÍNH HỆ SỐ HẰNG

### 5.1. Công thức chung

$$y'+p\,y=q(t),\quad y(0)=y_0,\quad p=\text{hằng số}.$$

**Nháp Laplace:**
$$sY-y_0+pY=Q(s)\ \Rightarrow\ Y=\frac{y_0}{s+p}+\frac{Q(s)}{s+p}.$$
Tra ngược (phần thứ hai dùng tích chập):
$$y(t)=y_0e^{-pt}+\int_0^t e^{-p(t-\tau)}\,q(\tau)\,d\tau.$$

**Chép sạch (thừa số tích phân):** nhân hai vế với $e^{pt}$:
$$\big(y\,e^{pt}\big)'=q(t)\,e^{pt}\ \Rightarrow\ y\,e^{pt}-y_0=\int_0^t q(\tau)e^{p\tau}d\tau.$$
Công thức này **trùng hoàn toàn** với kết quả Laplace. Đây là bằng chứng rằng với bậc 1, thừa số tích phân *chính là* Laplace "mặc đồ cổ điển".

> **Thành thật về bậc 1:** bậc 1 hệ số hằng, **thừa số tích phân thường nhanh hơn Laplace**. Laplace ở đây chỉ có ba tác dụng: (i) kiểm tra đáp án; (ii) báo trước trường hợp đặc biệt (cực kép $\to$ có $t$); (iii) xử lý lực dạng công tắc (Phần 8).
> **Hệ số $p$ biến thiên** (ví dụ $y'+\frac{y}{t}=\ldots$) thì **không dùng Laplace**; dùng thừa số tích phân tổng quát $e^{\int p\,dt}$. Xem Phần 9.

### 5.2. Ví dụ 5.A: chuyển động có lực cản, lực tắt theo hàm mũ

**Đề.** Vật khối lượng $m$ chịu lực cản $-bv$ và lực kéo $F(t)=F_0e^{-\gamma t}$. $v(0)=0$. Tìm $v(t)$.

**Lập PT (Vấn đề 2, giữ nguyên bằng Newton):**
$$m\dot v=F_0e^{-\gamma t}-bv\ \Rightarrow\ \dot v+kv=f_0e^{-\gamma t},\quad k=\frac bm,\ f_0=\frac{F_0}{m}.$$

**Nháp Laplace (giấy nháp):**
$$(s+k)V=\frac{f_0}{s+\gamma}\ \Rightarrow\ V=\frac{f_0}{(s+k)(s+\gamma)}=\frac{f_0}{\gamma-k}\left[\frac1{s+k}-\frac1{s+\gamma}\right]\quad(\gamma\neq k).$$
$$v=\frac{f_0}{\gamma-k}\big(e^{-kt}-e^{-\gamma t}\big).$$
Quan sát: nếu $\gamma=k$ thì mẫu số là $(s+k)^2$, nghiệm là $v=f_0\,t\,e^{-kt}$. Ta **biết trước** phải chia hai trường hợp.

**Bản chép sạch (thừa số tích phân):**
Nhân hai vế với $e^{kt}$: $\ (v\,e^{kt})'=f_0\,e^{(k-\gamma)t}$. Tích phân từ $0$ đến $t$, với $v(0)=0$:

- Nếu $\gamma\neq k$:
$$v\,e^{kt}=f_0\frac{e^{(k-\gamma)t}-1}{k-\gamma}\ \Rightarrow\ v=\frac{f_0}{\gamma-k}\big(e^{-kt}-e^{-\gamma t}\big).$$
- Nếu $\gamma=k$: $\ (v\,e^{kt})'=f_0\ \Rightarrow\ v=f_0\,t\,e^{-kt}$.

**Kiểm tra:** $v(0)=0$; $v\to0$ khi $t\to\infty$ (cả hai lực lẫn cản đều tắt); thứ nguyên: $f_0/k$ có thứ nguyên vận tốc. Khi $\gamma\to k$, công thức đầu tiến về $f_0te^{-kt}$ (giới hạn $\frac{e^{-kt}-e^{-\gamma t}}{\gamma-k}\to te^{-kt}$). Khớp.

### 5.3. Ví dụ 5.B: mạch RL với nguồn xoay chiều

**Đề.** Mạch RL nối tiếp, nguồn $E_0\sin\omega t$, $i(0)=0$. Tìm $i(t)$.

**Lập PT (Kirchhoff, Vấn đề 2):**
$$L\,i'+R\,i=E_0\sin\omega t\ \Rightarrow\ i'+a\,i=e\sin\omega t,\quad a=\frac RL,\ e=\frac{E_0}{L}.$$

**Nháp Laplace:**
$$(s+a)I=\frac{e\omega}{s^2+\omega^2}\ \Rightarrow\ I=\frac{e\omega}{(s+a)(s^2+\omega^2)}.$$
Tách phân thức: $\ I=\dfrac{A}{s+a}+\dfrac{Bs+C}{s^2+\omega^2}$. Che nhân tử tại $s=-a$: $A=\dfrac{e\omega}{a^2+\omega^2}$. Đồng nhất hệ số: $B=-A$, $C=aA$. Vậy
$$I=A\left[\frac1{s+a}-\frac{s}{s^2+\omega^2}+\frac{a}{\omega}\cdot\frac{\omega}{s^2+\omega^2}\right]$$
$$\Rightarrow\ i(t)=\frac{e}{a^2+\omega^2}\Big[\omega e^{-at}-\omega\cos\omega t+a\sin\omega t\Big].$$

**Phân loại (L6):** số hạng $\omega e^{-at}$ đến từ cực $-a$ của $P(s)$: *quá độ*. Hai số hạng sin, cos đến từ cực $\pm i\omega$ của lực: *xác lập*. Không trùng cực, nên **không có** nhân tử $t$.

**Bản chép sạch (PT tuyến tính hệ số hằng, nghiệm riêng + nghiệm thuần nhất):**

*Thuần nhất:* $i'+ai=0\Rightarrow i_h=Ce^{-at}$.

*Nghiệm riêng:* lực ở dạng sin và $\pm i\omega$ khác nghiệm đặc trưng $-a$ (vì $a$ thực), nên đặt $i_p=\alpha\sin\omega t+\beta\cos\omega t$. Thế vào:
$$i_p'+ai_p=(a\alpha-\omega\beta)\sin\omega t+(\omega\alpha+a\beta)\cos\omega t=e\sin\omega t.$$
Đồng nhất: $a\alpha-\omega\beta=e$ và $\omega\alpha+a\beta=0$. Từ phương trình thứ hai, $\beta=-\omega\alpha/a$; thế vào phương trình đầu: $\alpha\dfrac{a^2+\omega^2}{a}=e$. Vậy
$$\alpha=\frac{ea}{a^2+\omega^2},\qquad \beta=-\frac{e\,\omega}{a^2+\omega^2}.$$

*Điều kiện đầu:* $i(0)=C+\beta=0\Rightarrow C=\dfrac{e\omega}{a^2+\omega^2}$. Kết quả:
$$i(t)=\frac{e}{a^2+\omega^2}\Big[\omega e^{-at}+a\sin\omega t-\omega\cos\omega t\Big].$$

**Kiểm tra:** $i(0)=\frac{e}{a^2+\omega^2}[\omega-\omega]=0$. Phần xác lập có thể viết gọn $i_p=\dfrac{e}{\sqrt{a^2+\omega^2}}\sin(\omega t-\varphi)$, $\tan\varphi=\omega/a$: dòng *trễ pha* so với áp (đúng vật lý của cuộn cảm). Biên độ $\frac{E_0}{\sqrt{R^2+L^2\omega^2}}$ khớp với tổng trở cuộn cảm.

---

## PHẦN 6: PTVP BẬC 2 TUYẾN TÍNH HỆ SỐ HẰNG, KHÔNG THUẦN NHẤT

### 6.1. Mô hình chuẩn: dao động tắt dần có lực cưỡng bức

$$x''+2\beta\,x'+\omega_0^2\,x=f(t),\qquad x(0)=x_0,\ x'(0)=v_0.$$

(Với lò xo: $\omega_0^2=k/m$, $2\beta=b/m$, $f=F/m$. Với mạch RLC nối tiếp theo điện tích: $\omega_0^2=1/LC$, $2\beta=R/L$, $f=E/L$.)

**Nháp Laplace:**
$$\underbrace{(s^2+2\beta s+\omega_0^2)}_{P(s)}X=F(s)+(s+2\beta)\,x_0+v_0.$$

Hoàn thành bình phương $P(s)=(s+\beta)^2+(\omega_0^2-\beta^2)$ và phân loại **bằng dấu của $\omega_0^2-\beta^2$**:

| Trường hợp | Cực của $P(s)$ | Phần quá độ trong $x(t)$ |
|---|---|---|
| $\beta<\omega_0$ (**tắt dần yếu**) | $-\beta\pm i\omega$, $\omega=\sqrt{\omega_0^2-\beta^2}$ | $e^{-\beta t}(C_1\cos\omega t+C_2\sin\omega t)$ |
| $\beta=\omega_0$ (**tắt dần tới hạn**) | $-\beta$ (kép) | $(C_1+C_2t)\,e^{-\beta t}$ |
| $\beta>\omega_0$ (**tắt dần mạnh**) | $-\beta\pm\sigma$, $\sigma=\sqrt{\beta^2-\omega_0^2}$ | $C_1e^{(-\beta+\sigma)t}+C_2e^{(-\beta-\sigma)t}$ |

Khi $\beta=0$: $P(s)=s^2+\omega_0^2$, dao động điều hòa không tắt.

### 6.2. Ví dụ 6.A: lực không đổi đột ngột tác dụng (tắt dần yếu)

**Đề.** Vật nối lò xo, có lực cản nhớt. Tại $t=0$ (đang nằm yên tại vị trí cân bằng cũ) đặt lực không đổi $F_0$. Tìm $x(t)$.

**Lập PT:** $x''+2\beta x'+\omega_0^2x=a_0$, $a_0=F_0/m$, $x(0)=0$, $x'(0)=0$, $\beta<\omega_0$.

**Nháp Laplace:**
$$X=\frac{a_0}{s\,[(s+\beta)^2+\omega^2]}.$$
Tách: $\ \dfrac{1}{s\,P(s)}=\dfrac1{\omega_0^2}\Big[\dfrac1s-\dfrac{s+2\beta}{P(s)}\Big]$ (kiểm tra bằng cách quy đồng). Rồi $\dfrac{s+2\beta}{(s+\beta)^2+\omega^2}=\dfrac{s+\beta}{(\cdot)}+\dfrac{\beta}{\omega}\cdot\dfrac{\omega}{(\cdot)}$. Tra ngược:
$$x(t)=\frac{a_0}{\omega_0^2}\Big[1-e^{-\beta t}\Big(\cos\omega t+\frac{\beta}{\omega}\sin\omega t\Big)\Big].$$

**Phân loại:** số hạng $1$ đến từ cực $s=0$ của lực: *xác lập*. Phần còn lại từ cực của $P(s)$: *quá độ*. Không trùng cực vì $\omega_0\ne0$.

**Bản chép sạch:**

*Nghiệm riêng.* Lực không đổi, và $0$ không phải nghiệm đặc trưng ($\omega_0^2\neq0$), nên đặt $x_p=A$. Thế vào: $\omega_0^2A=a_0\Rightarrow A=a_0/\omega_0^2$.

*Thuần nhất.* $r^2+2\beta r+\omega_0^2=0\Rightarrow r=-\beta\pm i\omega$ (vì $\beta<\omega_0$). Vậy $x_h=e^{-\beta t}(C_1\cos\omega t+C_2\sin\omega t)$.

*Điều kiện đầu.* $x=x_h+x_p$:

- $x(0)=C_1+\dfrac{a_0}{\omega_0^2}=0\Rightarrow C_1=-\dfrac{a_0}{\omega_0^2}$.
- $x'(0)=-\beta C_1+\omega C_2=0\Rightarrow C_2=\dfrac{\beta}{\omega}C_1=-\dfrac{a_0\beta}{\omega_0^2\omega}$.

Kết quả giống hệt bản nháp.

**Kiểm tra:**

- $x(\infty)=a_0/\omega_0^2=F_0/k$: độ dãn cân bằng tĩnh. ✔
- $\beta\to0$: $x=\frac{a_0}{\omega_0^2}(1-\cos\omega_0t)$ (dao động quanh vị trí cân bằng mới với biên độ $a_0/\omega_0^2$). ✔
- Thứ nguyên $a_0/\omega_0^2$: (m/s²)/(1/s²)=m. ✔

### 6.3. Ví dụ 6.B: cộng hưởng không tắt

**Đề.** $x''+\omega_0^2x=A\cos\omega_0t$, $x(0)=0$, $x'(0)=0$.

**Nháp Laplace:**
$$X=\frac{A\,s}{(s^2+\omega_0^2)^2}=\frac{A}{2\omega_0}\cdot\frac{2\omega_0s}{(s^2+\omega_0^2)^2}\ \Rightarrow\ x=\frac{A}{2\omega_0}\,t\sin\omega_0t.$$
Cực kép $\pm i\omega_0$ báo hiệu: nghiệm có dạng $t\sin$ và $t\cos$ (biên độ tăng tuyến tính theo $t$).

**Bản chép sạch:**

Lực có tần số trùng nghiệm đặc trưng $\pm i\omega_0$, nên đặt $x_p=t\,(\alpha\cos\omega_0t+\gamma\sin\omega_0t)$. Tính:
$$x_p''=2\omega_0\,(\gamma\cos\omega_0t-\alpha\sin\omega_0t)-\omega_0^2x_p.$$
Thế vào PT: $x_p''+\omega_0^2x_p=2\omega_0(\gamma\cos\omega_0t-\alpha\sin\omega_0t)=A\cos\omega_0t$. Suy ra $\gamma=\dfrac{A}{2\omega_0}$, $\alpha=0$. Nghiệm thuần nhất $C_1\cos\omega_0t+C_2\sin\omega_0t$ với $x(0)=0$, $x'(0)=0$ cho $C_1=C_2=0$. Vậy
$$x=\frac{A}{2\omega_0}\,t\sin\omega_0t.$$

### 6.4. Nghiệm xác lập khi tắt dần, lực điều hòa (kết quả hay dùng nên tự dẫn lại được)

$x''+2\beta x'+\omega_0^2x=a_0\cos\Omega t$. Đặt $x_p=A\cos\Omega t+B\sin\Omega t$. Thế vào, đồng nhất:
$$(\omega_0^2-\Omega^2)A+2\beta\Omega B=a_0,\qquad(\omega_0^2-\Omega^2)B-2\beta\Omega A=0.$$
$$A=\frac{a_0(\omega_0^2-\Omega^2)}{D},\quad B=\frac{2\beta\Omega\,a_0}{D},\quad D=(\omega_0^2-\Omega^2)^2+4\beta^2\Omega^2.$$
Biên độ: $\sqrt{A^2+B^2}=a_0/\sqrt D$, cực đại gần $\Omega\approx\omega_0$ khi $\beta$ nhỏ. Phần quá độ $x_h$ tắt dần theo $e^{-\beta t}$ và chỉ cần cho điều kiện đầu.

---

## PHẦN 7: HỆ PTVP VÀ PHƯƠNG PHÁP KHỬ

### 7.1. Hệ bậc 1 hệ số hằng, dạng $2\times2$

$$x'=ax+by,\qquad y'=cx+dy,\qquad x(0)=x_0,\ y(0)=y_0.$$

**Nháp Laplace:**
$$(s-a)X-bY=x_0,\qquad -cX+(s-d)Y=y_0.$$
Định thức hệ:
$$\Delta(s)=(s-a)(s-d)-bc=s^2-(a+d)s+(ad-bc).$$
Theo quy tắc Cramer, $X=\dfrac{\ldots}{\Delta(s)}$, $Y=\dfrac{\ldots}{\Delta(s)}$. **Mẫu số chung là $\Delta(s)$** (bất biến I1 cho hệ).

**Khử trong bản sạch:** từ $x'=ax+by$ đạo hàm tiếp:
$$x''=ax'+by'=ax'+b(cx+dy).$$
Thay $by=x'-ax$ để loại $y$: $x''=ax'+bcx+d(x'-ax)$, tức là
$$\boxed{x''-(a+d)\,x'+(ad-bc)\,x=0.}$$
Đây là PT bậc 2 cho riêng $x$, và **đa thức đặc trưng của nó đúng bằng $\Delta$**. Từ đó:

1. Giải PT đặc trưng $\Delta(r)=0$ $\to$ $x$ có hai hằng số $C_1,C_2$.
2. Tìm $y$ từ chính phương trình $x'=ax+by$: $y=\dfrac{x'-ax}{b}$ (nếu $b\neq0$; nếu $b=0$ thì hoán vai trò $x\leftrightarrow y$).
3. **Điều kiện đầu cho $x$:** $x(0)=x_0$ và $x'(0)=ax_0+by_0$ (lấy từ PT gốc, đừng bỏ sót!).

### 7.2. Ví dụ 7.A: hệ không đối xứng

**Đề.** $x'=x+2y$, $y'=3x+2y$, $x(0)=1$, $y(0)=0$.

**Nháp Laplace:** $(s-1)X-2Y=1$, $-3X+(s-2)Y=0\Rightarrow Y=\dfrac{3X}{s-2}$. Thế: $X\,\dfrac{(s-1)(s-2)-6}{s-2}=1\Rightarrow X=\dfrac{s-2}{s^2-3s-4}=\dfrac{s-2}{(s-4)(s+1)}$. Che nhân tử: $X=\dfrac{2/5}{s-4}+\dfrac{3/5}{s+1}$, vậy $x=\tfrac25e^{4t}+\tfrac35e^{-t}$.

**Bản chép sạch (khử):**

$a=1,b=2,c=3,d=2$. Khử $y$: $x''-3x'-4x=0$. PT đặc trưng $r^2-3r-4=(r-4)(r+1)=0$, nên $x=C_1e^{4t}+C_2e^{-t}$.

Điều kiện đầu: $x(0)=1=C_1+C_2$; $x'(0)=x(0)+2y(0)=1=4C_1-C_2$. Cộng hai phương trình: $5C_1=2$, vậy $C_1=\tfrac25$, $C_2=\tfrac35$.

Từ $y=\dfrac{x'-x}{2}$: $\ y=\tfrac35\big(e^{4t}-e^{-t}\big)$.

**Kiểm tra:** $y(0)=0$ ✔. $y'=\tfrac35(4e^{4t}+e^{-t})$ và $3x+2y=\tfrac{12}5e^{4t}+\tfrac35e^{-t}$ ✔.

### 7.3. Ví dụ 7.B: hai dao động tử ghép (mẫu mực cho các bài "dao động chuẩn")

**Đề.** Hai vật khối lượng $m$ bằng nhau, mỗi vật nối với tường bằng lò xo $k$, hai vật nối với nhau bằng lò xo $k_c$ (ghép). Đặt $\omega_0^2=k/m$, $\kappa=k_c/m$. Kéo vật 1 lệch $A$, vật 2 ở vị trí cân bằng, thả không vận tốc đầu.

**Lập hệ (Newton, Vấn đề 2):**
$$x_1''=-\omega_0^2x_1-\kappa(x_1-x_2),\qquad x_2''=-\omega_0^2x_2-\kappa(x_2-x_1).$$
$x_1(0)=A$, $x_2(0)=0$, $x_1'(0)=x_2'(0)=0$.

**Nháp Laplace:** đặt $p=s^2+\omega_0^2+\kappa$.
$$pX_1-\kappa X_2=sA,\qquad -\kappa X_1+pX_2=0.$$
Định thức: $p^2-\kappa^2=(p-\kappa)(p+\kappa)=(s^2+\omega_0^2)(s^2+\omega_0^2+2\kappa)$. Đây là **bất biến I1 cho hệ**: hai nhân tử cho biết trước **hai tần số chuẩn**. Giải ra
$$X_1+X_2=\frac{sA}{s^2+\omega_0^2},\qquad X_1-X_2=\frac{sA}{s^2+\omega_1^2},\quad\omega_1^2=\omega_0^2+2\kappa.$$
Tra ngược: $x_1+x_2=A\cos\omega_0t$, $x_1-x_2=A\cos\omega_1t$.

**Bản chép sạch (khử bằng cách cộng/trừ hai PT):**

Đặt $u=x_1+x_2$ và $w=x_1-x_2$. **Cộng** hai phương trình: $u''=-\omega_0^2u$. **Trừ** hai phương trình: $w''=-(\omega_0^2+2\kappa)w=-\omega_1^2w$. Hai PT này **tách rời** nhau, là dao động điều hòa:
$$u=C_1\cos\omega_0t+C_2\sin\omega_0t,\qquad w=D_1\cos\omega_1t+D_2\sin\omega_1t.$$
Điều kiện đầu: $u(0)=w(0)=A$, $u'(0)=w'(0)=0$ $\Rightarrow$ $C_1=D_1=A$, $C_2=D_2=0$. Từ $x_1=\frac{u+w}{2}$, $x_2=\frac{u-w}{2}$:
$$x_1=\frac A2\big(\cos\omega_0t+\cos\omega_1t\big),\qquad x_2=\frac A2\big(\cos\omega_0t-\cos\omega_1t\big).$$

**Kiểm tra / hệ quả:**
Dùng tích thành tổng: $x_1=A\cos\dfrac{\omega_1+\omega_0}{2}t\,\cos\dfrac{\omega_1-\omega_0}{2}t$, $x_2=A\sin\dfrac{\omega_1+\omega_0}{2}t\,\sin\dfrac{\omega_1-\omega_0}{2}t$. Khi $\kappa\ll\omega_0^2$ thì năng lượng chuyển dần qua lại giữa hai vật (**phách**). Khi $\kappa\to0$: $x_1\to A\cos\omega_0t$, $x_2\to0$ (hai vật độc lập). ✔

**Điều Laplace cho thêm:** định thức phân tích được thành hai nhân tử *bình phương ở dạng $s^2+\text{hằng}$* nói với bạn rằng **có hai tổ hợp tách rời được** và chúng ứng với cộng/trừ. Khi hệ không đối xứng (như 7.2), dùng công thức khử tổng quát ở 7.1.

### 7.4. Ví dụ 7.C: chuỗi phân rã (hệ tam giác)

$N_1'=-\lambda_1N_1$, $N_2'=\lambda_1N_1-\lambda_2N_2$, $N_1(0)=N_0$, $N_2(0)=0$.

**Nháp Laplace:** $N_1=\dfrac{N_0}{s+\lambda_1}$, $(s+\lambda_2)N_2=\lambda_1N_1\Rightarrow N_2=\dfrac{\lambda_1N_0}{(s+\lambda_1)(s+\lambda_2)}$, tách như 5.A:
$$N_2=\frac{\lambda_1N_0}{\lambda_2-\lambda_1}\big(e^{-\lambda_1t}-e^{-\lambda_2t}\big)\quad(\lambda_1\neq\lambda_2).$$

**Chép sạch:** giải $N_1=N_0e^{-\lambda_1t}$. Thế vào PT thứ hai, đưa về $N_2'+\lambda_2N_2=\lambda_1N_0e^{-\lambda_1t}$ rồi dùng thừa số tích phân $e^{\lambda_2t}$ (giống hệt 5.A với $k=\lambda_2$, $\gamma=\lambda_1$). Hệ này "tam giác" nên khử chỉ là *thế lần lượt*.

Thời điểm $N_2$ cực đại: $N_2'=0\Rightarrow\lambda_1e^{-\lambda_1t}=\lambda_2e^{-\lambda_2t}\Rightarrow t_{\max}=\dfrac{\ln(\lambda_2/\lambda_1)}{\lambda_2-\lambda_1}$.

---

## PHẦN 8: LỰC/NGUỒN GIÁN ĐOẠN

Công tắc đóng/mở, lực tác dụng trong một khoảng thời gian, va chạm cực ngắn. Đây là chỗ Laplace *tiết kiệm công nhất*, và cũng là chỗ **chép sạch** cần cẩn thận nhất.

### 8.1. Lực bật tại $t=0$ rồi tắt tại $t=T$

Lực $=f_0\,[u(t)-u(t-T)]$. Với PT tuyến tính, đáp ứng là hiệu hai đáp ứng bước, một cái bật tại $0$ và một cái bật tại $T$:
$$y(t)=y_s(t)-y_s(t-T)\,u(t-T),\qquad(\text{tính chất dịch theo }t).$$
với $y_s$ là nghiệm khi bật lực **vĩnh viễn** tại $t=0$.

### 8.2. Ví dụ 8.A: mạch RL, nguồn $E$ nối trong khoảng $0<t<T$ rồi bị nối tắt

**Lập PT:** $i'+ai=\dfrac{E}{L}\,[u(t)-u(t-T)]$, $i(0)=0$, $a=R/L$.

**Nháp Laplace:** nghiệm bước $i_s=\dfrac ER(1-e^{-at})$. Do đó
$$i(t)=\frac ER(1-e^{-at})-\frac ER\big(1-e^{-a(t-T)}\big)u(t-T).$$
Với $t>T$: $\ i=\dfrac ER\big(e^{-a(t-T)}-e^{-at}\big)=\dfrac ER\,(e^{aT}-1)\,e^{-at}$.

**Bản chép sạch (giải hai giai đoạn và "khâu" bằng điều kiện liên tục):**

*Giai đoạn 1 ($0\le t\le T$):* $i'+ai=E/L$. Thừa số tích phân $e^{at}$: $(ie^{at})'=\dfrac EL e^{at}\Rightarrow i=\dfrac ER\big(1-e^{-at}\big)$ với $i(0)=0$.

*Giai đoạn 2 ($t\ge T$):* nguồn bị nối tắt nên $i'+ai=0\Rightarrow i=i(T)\,e^{-a(t-T)}$. **Dòng qua cuộn cảm liên tục** (không có xung điện áp vô hạn), nên $i(T)=\dfrac ER(1-e^{-aT})$:
$$i(t)=\frac ER\big(1-e^{-aT}\big)e^{-a(t-T)}\quad(t\ge T).$$

**Kiểm tra:** $\;(1-e^{-aT})e^{aT}=e^{aT}-1$, khớp với bản nháp. ✔ Khi $T\to\infty$ thì $i\to\frac{E}{R}$ trong giai đoạn 1 (không bao giờ bị tắt). ✔

**Với PT bậc 2** (ví dụ lực tác dụng trong thời gian $T$): giai đoạn 2 giải với điều kiện đầu $x(T)$ và $x'(T)$ lấy từ giai đoạn 1 (cả $x$ lẫn $x'$ đều **liên tục** nếu lực hữu hạn).

### 8.3. Xung lực/xung điện (va chạm cực ngắn)

Lực $F(t)=J\,\delta(t)$, với $J=\int F\,dt$ là xung lượng. **Nháp Laplace:** $\mathcal L\{J\delta\}=J$, vì thế $m x''+kx=J\delta(t)\to(ms^2+k)X=J\Rightarrow x=\dfrac{J}{m\omega_0}\sin\omega_0t$ (bắt đầu từ $x(0^-)=0$, $v(0^-)=0$).

**Chép sạch:** không cần $\delta$. Tích phân PT trong khoảng ngắn $(0^-,0^+)$ cho $m\,\Delta v=J$ (định lý xung lượng), còn $x$ liên tục. Vậy ngay sau xung: $x(0^+)=0$, $v(0^+)=J/m$. Bài toán trở về dao động tự do với điều kiện đầu đó: $x=\dfrac{J}{m\omega_0}\sin\omega_0t$. Hai cách cho cùng kết quả.

---

## PHẦN 9: BẪY VÀ CÁC TRƯỜNG HỢP CẤM DÙNG

### 9.1. Cấm dùng (vi phạm Pre)

| Tình huống | Vì sao cấm | Cách làm đúng |
|---|---|---|
| **Bậc 1 hệ số biến thiên**, ví dụ $y'+\dfrac{y}{t}=g$, $y'+t\,y=g$ | $\mathcal L\{t\,y'\}=-\dfrac{d}{ds}(sY-y_0)$ sinh ra **đạo hàm theo $s$**. Bài toán không còn là đại số. | **Thừa số tích phân** $\mu=e^{\int p\,dt}$ (luôn dùng được cho bậc 1 tuyến tính). |
| **Phi tuyến**: $\ddot\theta+\sin\theta=0$ (góc lớn), $m\dot v=-bv^2$ | $\mathcal L\{y^2\}\neq(\mathcal L\{y\})^2$; phi tuyến phá tính chất cộng. | Năng lượng, tách biến, hoặc **tuyến tính hóa hợp lệ** (góc nhỏ), ghi rõ sai số theo Err. |
| **Khối lượng biến thiên** (tên lửa), **độ cứng/điện trở biến thiên theo $t$** | Hệ số phụ thuộc $t$. | Tách biến, thừa số tích phân, hoặc phương pháp riêng. |
| **Lực ngoài ngoài bảng** ($1/t$, $\tan t$, $\ln t$, xung răng cưa phức tạp) | Không tra ngược được. | Biến thiên hằng số hoặc tích phân Duhamel $\int_0^t e^{-p(t-\tau)}q(\tau)d\tau$ viết trực tiếp. |
| **PT không có điều kiện đầu tại $t=0$** (bài biên) | Laplace cần dữ kiện tại một điểm. | Giải nghiệm tổng quát bằng cổ điển, đặt hằng số từ điều kiện biên. |

### 9.2. Lỗi hay mắc khi dùng Laplace (rà soát nháp)

1. **Quên số hạng điều kiện đầu** ($-y_0$, $-sy_0-v_0$) hoặc đổi dấu.
2. **Nhầm $\mathcal L\{e^{-at}\}=\frac1{s+a}$ với $\frac1{s-a}$.** Dấu của $a$ trong $e^{-at}$ ngược với dấu trong mẫu số.
3. **Điều kiện đầu cho hệ:** quên rằng $x'(0)$ phải **tính từ PT gốc** ($x'(0)=ax_0+by_0$), vì đề chỉ cho $x(0)$, $y(0)$.
4. **Tách phân thức sai:** luôn kiểm tra bằng cách thế một giá trị $s$ cụ thể (ví dụ $s=1$) vào cả hai vế.
5. **Dùng tính chất dịch $t$ nhưng quên $u(t-T)$:** $f(t-T)$ chỉ là một nửa. Phải nhân với bậc thang. (Xem 8.1.)
6. **Điều kiện đầu "nhảy":** gặp xung thì phải chuyển về điều kiện ngay sau xung (3.5, 8.3).
7. **Định lý giá trị cuối áp dụng bừa:** nghiệm dao động không tắt ($\sin\omega t$) *không có giới hạn* khi $t\to\infty$; công thức sẽ cho kết quả vô nghĩa.
8. **Chép sạch kiểu "đã biết đáp số":** viết đáp số rồi lùi lại bịa các bước. Mỗi hằng số phải **thực sự** suy ra được.

### 9.3. Khi nào Laplace *không đáng* dùng?

- Bậc 1 với lực là hằng/mũ/sin đơn giản: thừa số tích phân nhanh hơn.
- Bậc 2 thuần nhất ($f=0$): phương trình đặc trưng đã đủ.
- Hệ có đối xứng rõ ràng (cộng/trừ tách ngay): khử trực tiếp.

Laplace đáng giá nhất khi: **điều kiện đầu phức tạp, lực là tổ hợp (sin + mũ + hằng), có cộng hưởng, có công tắc, hoặc là hệ 3 ẩn trở lên.**

---

## PHẦN 10: BÀI TẬP VÀ ĐÁP SỐ

**Cách dùng:** với mỗi bài, làm **hai bản**: nháp Laplace và chép sạch cổ điển. So khớp. Chỉ xem đáp số sau khi đã có bản của mình.

| # | Đề | Gợi ý nhận diện |
|---|---|---|
| **1** | $v'+3v=6$, $v(0)=0$ | Bậc 1, lực hằng |
| **2** | $i'+2i=4e^{-2t}$, $i(0)=1$ | Bậc 1, lực trùng cực $\to$ cộng hưởng |
| **3** | $x''+3x'+2x=2$, $x(0)=0$, $x'(0)=0$ | Bậc 2, tắt dần mạnh, lực hằng |
| **4** | $x''+2x'+x=e^{-t}$, $x(0)=0$, $x'(0)=1$ | Bậc 2, nghiệm đặc trưng kép trùng lực |
| **5** | $x'=2x+y$, $y'=x+2y$, $x(0)=1$, $y(0)=0$ | Hệ đối xứng $\to$ cộng/trừ |
| **6** | Như 8.A nhưng bậc 2: $x''+\omega_0^2x=a_0$ trong $0<t<T$, bằng $0$ sau đó, $x(0)=x'(0)=0$. Tìm $x$ khi $t>T$. | Công tắc, khâu $x$ và $x'$ |
| **7** | Tự lập: dao động cưỡng bức tắt dần $x''+2\beta x'+\omega_0^2x=a_0\cos\Omega t$, tìm $\Omega$ làm biên độ xác lập cực đại. | Từ 6.4 |

**Đáp số:**

1. $v=2\,(1-e^{-3t})$.
2. $i=(1+4t)\,e^{-2t}$.
3. $x=1-2e^{-t}+e^{-2t}$.
4. $x=\big(t+\tfrac{t^2}{2}\big)e^{-t}$. (Gợi ý chép sạch: đặt $x=e^{-t}g$, khi đó $(D+1)^2x=e^{-t}g''$.)
5. $x=\tfrac12(e^{3t}+e^{t})$, $y=\tfrac12(e^{3t}-e^{t})$.
6. Giai đoạn 1: $x=\dfrac{a_0}{\omega_0^2}(1-\cos\omega_0t)$. Khâu tại $T$ bằng $x(T)$, $x'(T)$. Với $t>T$: $x=\dfrac{a_0}{\omega_0^2}\big[\cos\omega_0(t-T)-\cos\omega_0t\big]$.
7. $A^2+B^2=\dfrac{a_0^2}{D(\Omega)}$. Cực đại biên độ khi $D$ cực tiểu, tức $\Omega^2=\omega_0^2-2\beta^2$ (nếu $\omega_0^2>2\beta^2$).

---

## PHẦN 11: TÓM TẮT MỘT TRANG

```
        ┌─────────────────────────────────────────────────────┐
        │  ĐÃ LẬP XONG PTVP (Vấn đề 2 xong, bằng Newton/KVL…) │
        └──────────────────────────┬──────────────────────────┘
                                   │
        ┌──────────────────────────▼──────────────────────────┐
        │  P1 Tuyến tính?  P2 Hệ số hằng?  P3 ĐK đầu tại t=0? │
        │  P4 Lực thuộc bảng tra?                              │
        └───────┬──────────────────────────────────┬──────────┘
          cả 4 CÓ                                có ≥1 KHÔNG
                │                                  │
                │                         Dừng. Dùng cổ điển:
                │                         bậc 1 hệ số biến ⇒ e^{∫p dt}
                │                         phi tuyến ⇒ năng lượng/tách biến
        ┌───────▼───────────────────────────────┐
        │  NHÁP (giấy nháp)                     │
        │  L1 Laplace hai vế (nhớ số hạng ĐK đầu)│
        │  L2 Y = N(s)/P(s)  [P = đa thức đặc trưng]│
        │  L3 Tách phân thức (cover-up / hoàn thành bình phương)│
        │  L4 Tra bảng ngược → y(t)             │
        │  L5 Bất biến: ĐK đầu? giá trị cuối? thứ nguyên?│
        │  L6 Phân loại: cực của P (quá độ) vs cực của F (xác lập)│
        └───────┬───────────────────────────────┘
                │
        ┌───────▼───────────────────────────────┐
        │  CHÉP SẠCH (bài nộp, KHÔNG nhắc Laplace)│
        │  Bậc 1:  thừa số tích phân e^{pt}      │
        │  Bậc 2:  y_h (PT đặc trưng) + y_p      │
        │          (dạng y_p đọc từ cực, thế vào,│
        │           đồng nhất hệ số)              │
        │  Hệ:    khử (cộng/trừ hoặc x''−(a+d)x'+(ad−bc)x=0)│
        │  Công tắc: giải từng giai đoạn, khâu x và x' (hoặc i_L, u_C) liên tục│
        │  Kiểm tra: ĐK đầu, t→∞, thứ nguyên, giới hạn đặc biệt│
        └───────────────────────────────────────┘
```

**Các mệnh đề cần khắc ghi:**

1. **Laplace là máy nháp, không phải bài làm.** Đáp số phải đứng được mà không cần nó.
2. **Mẫu số $Y(s)$ = đa thức đặc trưng.** Đây là cầu nối giữa Laplace và phương pháp cổ điển.
3. **Cực của lực ngoài quyết định dạng nghiệm riêng.** Trùng cực thì nhân thêm $t$ (cộng hưởng).
4. **Hệ số hằng, tuyến tính, có điều kiện đầu**: thiếu một trong ba thì đừng dùng.
5. **Đừng quên Err:** Laplace chính xác, nhưng *mô hình đưa vào* có thể đã xấp xỉ (tuyến tính hóa), và sai số nằm ở đó.

---

*Góp ý cho tác giả: nếu phát hiện lỗi ở ví dụ nào, hãy thế ngược vào PT gốc và điều kiện đầu để xác định chính xác dòng sai. Tinh thần "thảo luận" của bộ tài liệu này là để các lỗi được tìm ra, không phải để che đi.*
