# Biến đổi Laplace cho HSGQG Vật Lý: Bài giảng, Hồ sơ công cụ và Thuật toán

> Tài liệu này là **một CÔNG CỤ** trong khung "Thảo luận lớn về Cách giải Đề thi HSGQG Vật Lý". Nó được viết theo đúng tinh thần của khung đó: có **Dom / Pre / Suf / Post / Err**, có quy trình *tra theo trình tự cố định*, có **bất biến** để tự kiểm, và có cảnh báo về chỗ nào **cấm dùng**.
>
> **Trạng thái kiểm duyệt:** Các ví dụ trong file đã được thử lại bằng cách thế ngược vào phương trình và điều kiện đầu. Tuy vậy, hãy tự tay làm lại từng ví dụ. Đừng tin vào việc "đọc thấy hợp lý".

---

## Mục lục

0. Định vị công cụ: Laplace nằm ở đâu trong "3 vấn đề lớn"
1. **Bài giảng nhập môn**: Laplace là gì, vì sao nó hoạt động
2. **Hồ sơ công cụ** (Dom, Pre, Suf, Post, Err), bảng tra, tính chất
3. **Thuật toán L** (bản nháp) và các **bất biến tự kiểm**
4. **Quy tắc chép sạch**: trình bày như thể không dùng Laplace
5. PTVP bậc 1 tuyến tính hệ số hằng
6. PTVP bậc 2 tuyến tính hệ số hằng, không thuần nhất
7. Hệ PTVP và phương pháp khử
8. Lực/nguồn gián đoạn (công tắc, xung)
9. **Bẫy** và **các trường hợp cấm dùng**
10. Bài tập và đáp số
11. Tóm tắt một trang

---

## PHẦN 0: ĐỊNH VỊ CÔNG CỤ

### 0.1. Laplace giải quyết Vấn đề nào?

Theo khung của bạn:

- **Vấn đề 1:** nhận diện CÔNG CỤ.
- **Vấn đề 2:** chuyển bài Vật Lý sang bài Toán, tức là **lập ra PTVP**.
- **Vấn đề 3:** giải bài Toán.

**Laplace chỉ thuộc Vấn đề 3**, cụ thể là giải PTVP/hệ PTVP *sau khi đã lập xong*. Nó **không** giúp bạn lập phương trình (việc đó vẫn là Newton, Kirchhoff, Faraday, bảo toàn... và vẫn cần mô hình hóa đúng).

Nó có một "lợi ích phụ" lên Vấn đề 1: khi nhìn PTVP, bạn **biết ngay hình dạng nghiệm** (mũ, sin/cos, có nhân thêm $t$ hay không) mà không phải đoán. Đây là chỗ nó giảm sự phụ thuộc vào trực giác.

### 0.2. Phạm vi tài liệu

| Có trong tài liệu | Không có (không cần cho HSGQG) |
|---|---|
| Định nghĩa, tính chất cốt lõi, bảng tra | Tích phân ngược Bromwich |
| PTVP bậc 1, bậc 2 hệ số hằng | Giải tích phức, thặng dư |
| Hệ PTVP hệ số hằng | PDE, hàm truyền đạt, ổn định điều khiển |
| Hàm lực dạng bậc thang, xung, nhảy | Hệ số biến thiên |

Học sinh **không cần biết số phức**. Mọi nghiệm phức đều được xử lý bằng *hoàn thành bình phương* và bảng tra.

### 0.3. Quy tắc vàng của tài liệu này

> **Laplace là bản NHÁP. Bài thi nộp bản CHÉP SẠCH theo phương pháp cổ điển.**

- **Bản nháp (trên giấy nháp):** dùng Laplace để ra đáp án, cấu trúc nghiệm và các hằng số, với tốc độ máy móc.
- **Bản chép sạch (bài làm):** viết lại bằng *thừa số tích phân*, *phương trình đặc trưng + nghiệm riêng*, hoặc *phương pháp khử*. Mỗi con số trong bản sạch phải **tự suy ra được** bằng đồng nhất hệ số hoặc điều kiện đầu. Không "chép từ nháp". Bản sạch không có $Y(s)$, không có "tra bảng".

Phần 4 trình bày chi tiết cách làm. Mỗi ví dụ ở các phần sau đều có đủ **cả hai bản**.

---

## PHẦN 1: BÀI GIẢNG NHẬP MÔN

### 1.1. Vấn đề cần giải quyết

Phương trình vi phân khó vì nó trộn **hàm** với **đạo hàm của hàm**. Đại số thì dễ vì chỉ có phép nhân và cộng.

Ta quen với một mẹo cùng loại: **logarit** biến phép nhân (khó) thành phép cộng (dễ). Tính xong thì quay về bằng $10^x$.

Laplace làm đúng như vậy: biến *đạo hàm* (khó) thành *phép nhân với $s$* (dễ). Giải đại số xong thì quay về.

```
   PTVP theo t   ──── Laplace ────►   Phương trình ĐẠI SỐ theo s
        │                                      │
   (khó, trực tiếp)                     (giải bằng tay, máy móc)
        │                                      │
   Nghiệm y(t)   ◄─── tra bảng ngược ───   Nghiệm Y(s)
```

### 1.2. Ý tưởng cốt lõi: $e^{st}$ là hàm "ngoan" nhất đối với đạo hàm

Hãy tính:

$$\frac{d}{dt}\,e^{st} = s\,e^{st}.$$

Lấy đạo hàm hàm $e^{st}$ chỉ là **nhân nó với con số $s$**. Hàm không đổi hình dạng, chỉ đổi biên độ. Mọi PTVP tuyến tính hệ số hằng, khi thế $y = e^{st}$ vào, đều biến thành một đa thức theo $s$. Đây chính là *phương trình đặc trưng* mà bạn đã biết.

Ý tưởng của Laplace là: **mọi hàm $f(t)$ có thể "phân tích" thành một tổng (tích phân) của các $e^{-st}$ với trọng số**. Khi đó đạo hàm hàm gốc tương ứng với phép nhân với $s$ lên các trọng số.

### 1.3. Định nghĩa

$$\boxed{F(s)=\mathcal{L}\{f(t)\}=\int_0^{\infty} f(t)\,e^{-st}\,dt}$$

Hiểu một cách vật lý: ta lấy $f(t)$ nhân với một "bộ lọc tắt dần" $e^{-st}$ (tắt càng nhanh khi $s$ lớn), rồi cộng tất cả các thời điểm lại từ $t=0$. Kết quả $F(s)$ là một hàm của $s$.

Quy ước ký hiệu: chữ thường là hàm theo $t$ ($y(t)$), chữ hoa là ảnh theo $s$ ($Y(s)$).

Ở mức HSGQG, bạn coi $s$ là **số thực dương đủ lớn** để tích phân hội tụ.

### 1.4. Tự tính vài ảnh từ định nghĩa

**(a) Hàm hằng $f=1$:**
$$\int_0^\infty e^{-st}dt=\left[-\frac{e^{-st}}{s}\right]_0^\infty=\frac1s\qquad(s>0).$$

**(b) Hàm mũ $f=e^{-at}$:**
$$\int_0^\infty e^{-(s+a)t}dt=\frac{1}{s+a}\qquad(s>-a).$$

**(c) Hàm $f=t$:** tích phân từng phần,
$$\int_0^\infty t e^{-st}dt=\left[-\frac{t e^{-st}}{s}\right]_0^\infty+\frac1s\int_0^\infty e^{-st}dt=\frac{1}{s^2}.$$

Tổng quát: $\mathcal{L}\{t^n\}=\dfrac{n!}{s^{n+1}}$.

**(d) $\sin\omega t$ và $\cos\omega t$:** dùng $\mathcal L\{e^{i\omega t}\}=\frac{1}{s-i\omega}$ rồi tách phần thực/ảo, hoặc tích phân từng phần hai lần. Kết quả:
$$\mathcal{L}\{\sin\omega t\}=\frac{\omega}{s^2+\omega^2},\qquad \mathcal{L}\{\cos\omega t\}=\frac{s}{s^2+\omega^2}.$$

### 1.5. Viên gạch trung tâm: quy tắc đạo hàm

Tích phân từng phần với $u=e^{-st}$, $dv=f'(t)dt$:

$$\mathcal{L}\{f'\}=\int_0^\infty f'(t)e^{-st}dt=\Big[f(t)e^{-st}\Big]_0^\infty+s\int_0^\infty f(t)e^{-st}dt = -f(0)+sF(s).$$

$$\boxed{\mathcal{L}\{y'\}=sY-y(0)},\qquad \boxed{\mathcal{L}\{y''\}=s^2Y-s\,y(0)-y'(0)}$$

(Dòng thứ hai là áp dụng dòng thứ nhất hai lần.)

Có hai điều cần để ý ngay:

1. **Điều kiện đầu được "đóng gói" tự động** vào phương trình. Đây là lý do Laplace rất hợp với bài vật lý ("tại $t=0$ đóng công tắc, ...").
2. Phép toán "đạo hàm" đã biến mất, chỉ còn nhân với $s$ rồi trừ đi vài hằng số.

### 1.6. Ví dụ nhỏ nhất (làm để thấm)

Giải $y'+2y=0$, $y(0)=3$.

- Laplace hai vế: $\big(sY-3\big)+2Y=0$.
- Đại số: $Y(s+2)=3 \Rightarrow Y=\dfrac{3}{s+2}$.
- Tra bảng ngược: $y=3e^{-2t}$.

Đối chiếu với cách cổ điển (phương trình đặc trưng $r+2=0$, $y=Ce^{-2t}$, $y(0)=3$): giống hệt. Chú ý rằng **mẫu số $s+2$ chính là đa thức đặc trưng**. Đây là một **bất biến** quan trọng, sẽ dùng nhiều lần.

### 1.7. Đọc mẫu số của $Y(s)$ như đọc "đồng hồ"

Mỗi nhân tử ở mẫu số của $Y(s)$ cho biết một hành vi của nghiệm:

| Mẫu số xuất hiện trong $Y(s)$ | Hành vi trong $y(t)$ |
|---|---|
| $\dfrac{1}{s}$ | hằng số (trạng thái xác lập) |
| $\dfrac{1}{s+a}$ | $e^{-at}$ (tắt dần nếu $a>0$, tăng nếu $a<0$) |
| $\dfrac{1}{(s+a)^2}$ | $t\,e^{-at}$ (**nhân thêm $t$**: dấu hiệu cộng hưởng/nghiệm kép) |
| $\dfrac{1}{(s+a)^3}$ | $t^2 e^{-at}$ |
| $\dfrac{\cdot}{s^2+\omega^2}$ | dao động $\sin\omega t$, $\cos\omega t$ (không tắt) |
| $\dfrac{\cdot}{(s+a)^2+\omega^2}$ | $e^{-at}\sin\omega t$, $e^{-at}\cos\omega t$ (dao động tắt dần) |
| $\dfrac{\cdot}{(s^2+\omega^2)^2}$ | $t\sin\omega t$, $t\cos\omega t$ (cộng hưởng dao động) |

Đây là câu trả lời cho câu hỏi "nghiệm riêng dạng gì?": **dạng nghiệm = các cực của $Y(s)$, với bội số tính cả hai nguồn** (đa thức đặc trưng và lực ngoài). Nếu hai nguồn **trùng cực** thì bội tăng, và nghiệm xuất hiện thêm một nhân tử $t$. Đó chính là hiện tượng cộng hưởng.

### 1.8. Vì sao quay ngược bằng bảng tra là hợp lệ?

Với các hàm liên tục theo từng khúc và bị chặn bởi hàm mũ, phép biến đổi Laplace là **1–1**: hai hàm khác nhau cho hai ảnh khác nhau. Vì vậy, nếu bạn tìm được $Y(s)$ có dạng trùng với một mục trong bảng, thì $y(t)$ **chính là** hàm tương ứng, không có nghiệm nào khác.

### 1.9. Thứ nguyên của $s$: một công cụ kiểm tra miễn phí

Trong $e^{-st}$, tích $st$ không thứ nguyên, nên $[s]=1/T$ (nghịch đảo thời gian), cùng loại với tốc độ tắt $a$ hoặc tần số $\omega$.

Do đó trong mọi biểu thức như $s+a$, $s^2+\omega^2$, các số hạng phải **cùng thứ nguyên**. Nếu bạn viết ra $s+\omega^2$ thì đã sai. Còn $F(s)$ có thứ nguyên $[f]\cdot T$ (thêm một thừa số thời gian do $\int dt$).

---

## PHẦN 2: HỒ SƠ CÔNG CỤ

Theo mô hình $M=(O,V,L,C,Q,I)$ của bạn, công cụ $\ell=$ *Laplace-cho-PTVP* có hồ sơ như sau:

| Mục | Nội dung |
|---|---|
| **Dom($\ell$)** | Hàm $f(t)$ xác định với $t\ge0$, liên tục từng khúc, tăng không nhanh hơn mũ ($\lvert f\rvert\le Me^{ct}$). Ảnh $F(s)$ xác định với $s>c$. |
| **Pre($\ell$)** (điều kiện **cần** để dùng làm công cụ giải PTVP) | **(P1)** PT/hệ **tuyến tính** theo ẩn và đạo hàm của ẩn. **(P2)** **Hệ số hằng**. **(P3)** Có **điều kiện đầu tại $t=0$** (đủ $n$ điều kiện cho PT bậc $n$). **(P4)** Lực/nguồn ngoài $f(t)$ thuộc lớp "tra được" (xem bảng: đa thức, mũ, sin, cos, tích của chúng, bậc thang, xung). |
| **Suf($\ell$)** (điều kiện **đủ**) | P1+P2+P3+P4 $\Rightarrow$ PTVP biến thành phương trình đại số tuyến tính trong $s$, nghiệm tồn tại và **duy nhất**. |
| **Post($\ell$)** | $Y(s)=\dfrac{N(s)}{P(s)}$ với $P(s)$ là **đa thức đặc trưng**, $N(s)$ chứa điều kiện đầu và lực ngoài. |
| **Err($\ell$)** | Bản thân phép biến đổi là **chính xác**, không có sai số xấp xỉ. Mọi sai số (tuyến tính hóa góc nhỏ, bỏ ma sát nhỏ,...) nằm ở bước **mô hình hóa** ở thượng nguồn. Phải ghi rõ ở bước đó. |

**Về "CHỖ":** các công cụ khác (Gauss, Kirchhoff,...) cần tìm *chỗ* áp dụng. Laplace thì **không tìm chỗ**: nó áp dụng lên **toàn bộ phương trình/hệ** cùng lúc. Gánh nặng "tìm kiếm" chuyển sang việc **kiểm tra Pre** (4 câu hỏi có/không, xem 3.1).

### 2.1. Bảng tra (học thuộc, vì nhỏ)

| $f(t)$ ($t\ge0$) | $F(s)$ | Ghi chú |
|---|---|---|
| $1$ | $\dfrac1s$ | |
| $t^n$ | $\dfrac{n!}{s^{n+1}}$ | |
| $e^{-at}$ | $\dfrac1{s+a}$ | $a$ có thể âm |
| $t\,e^{-at}$ | $\dfrac1{(s+a)^2}$ | |
| $t^n e^{-at}$ | $\dfrac{n!}{(s+a)^{n+1}}$ | |
| $\sin\omega t$ | $\dfrac{\omega}{s^2+\omega^2}$ | |
| $\cos\omega t$ | $\dfrac{s}{s^2+\omega^2}$ | |
| $e^{-at}\sin\omega t$ | $\dfrac{\omega}{(s+a)^2+\omega^2}$ | dịch $s\to s+a$ |
| $e^{-at}\cos\omega t$ | $\dfrac{s+a}{(s+a)^2+\omega^2}$ | dịch $s\to s+a$ |
| $\sinh\omega t$ | $\dfrac{\omega}{s^2-\omega^2}$ | |
| $\cosh\omega t$ | $\dfrac{s}{s^2-\omega^2}$ | |
| $t\sin\omega t$ | $\dfrac{2\omega s}{(s^2+\omega^2)^2}$ | cộng hưởng |
| $t\cos\omega t$ | $\dfrac{s^2-\omega^2}{(s^2+\omega^2)^2}$ | |
| $u(t-T)$ (bậc thang bật tại $T$) | $\dfrac{e^{-sT}}{s}$ | công tắc |
| $\delta(t)$ (xung đơn vị) | $1$ | xung lực/xung dòng |

### 2.2. Tính chất cần dùng

| Tính chất | Công thức |
|---|---|
| Tuyến tính | $\mathcal L\{\alpha f+\beta g\}=\alpha F+\beta G$ |
| Đạo hàm | $\mathcal L\{y'\}=sY-y(0)$; $\mathcal L\{y''\}=s^2Y-sy(0)-y'(0)$ |
| Tích phân | $\mathcal L\!\left\{\int_0^t f\right\}=\dfrac{F}{s}$ |
| Dịch theo $s$ | $\mathcal L\{e^{-at}f\}=F(s+a)$ |
| Dịch theo $t$ (trễ) | $\mathcal L\{f(t-T)\,u(t-T)\}=e^{-sT}F(s)$ |
| Nhân với $t$ | $\mathcal L\{t f\}=-F'(s)$ |
| Tích chập | $\mathcal L\{f*g\}=F\cdot G$, với $(f*g)(t)=\int_0^t f(\tau)g(t-\tau)d\tau$ |
| Giá trị đầu | $f(0^+)=\lim_{s\to\infty}sF(s)$ |
| Giá trị cuối | $f(\infty)=\lim_{s\to0}sF(s)$ (**chỉ khi** $f(t)$ thật sự có giới hạn khi $t\to\infty$, tức là mọi cực của $sF(s)$ nằm bên trái) |

(Hai dòng cuối là **bất biến tự kiểm**, dùng ở 3.4.)
