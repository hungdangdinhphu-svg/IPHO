# FRAMEWORK GIẢI ĐẠO HÀM — TÍCH PHÂN CHO HỌC SINH YẾU TRỰC GIÁC

> **Triết lý cốt lõi:** Học sinh yếu trực giác không "nhìn thấy" hướng giải như học sinh giỏi. Vì vậy ta **thay trực giác bằng quy trình cơ học (mechanical checklist)**: mọi bài toán được ép vào một trong số hữu hạn các "dạng chuẩn", mỗi dạng có một thuật toán con cố định. Học sinh không cần "nghĩ ra cách giải" — chỉ cần **nhận diện đúng dạng** rồi **chạy đúng quy trình**. Kỹ năng duy nhất cần luyện là nhận diện (pattern-matching), và kỹ năng này luyện được bằng lặp lại có hệ thống.

---

## PHẦN 0 — QUY TRÌNH TỔNG (Master Algorithm)

Dạy học sinh in "5 bước thần thánh" này lên đầu mọi bài:

1. **ĐỌC – PHÂN LOẠI**: Đề hỏi đạo hàm, nguyên hàm/tích phân, hay ứng dụng (khảo sát hàm, diện tích, thể tích, cực trị...)?
2. **NHẬN DIỆN DẠNG**: Soi hàm số vào các bảng nhận diện ở Phần A/B bên dưới → chọn đúng 1 nhánh trong cây quyết định.
3. **CHẠY THUẬT TOÁN CON**: Áp dụng đúng quy trình cứng (fixed procedure) của dạng đó — không sáng tạo, không "thử".
4. **KIỂM TRA NGƯỢC (bắt buộc)**: 
   - Với nguyên hàm: đạo hàm kết quả, phải ra đúng hàm ban đầu.
   - Với tích phân xác định/trắc nghiệm: bấm máy tính (MTCT) đối chiếu số.
5. **NẾU BÍ (đặc biệt VDC)**: dùng "lối thoát hiểm" ở Phần D (máy tính cầm tay, thử đáp án, đặc biệt hóa).

---

## PHẦN A — ĐẠO HÀM

### A1. Bảng công thức gốc (phải thuộc như bảng cửu chương)

| Hàm | Đạo hàm |
|---|---|
| $x^n$ | $n x^{n-1}$ |
| $\sqrt{x}$ | $\dfrac{1}{2\sqrt{x}}$ |
| $\sin x, \cos x$ | $\cos x, -\sin x$ |
| $\tan x, \cot x$ | $\dfrac{1}{\cos^2x}, -\dfrac{1}{\sin^2x}$ |
| $e^x, a^x$ | $e^x, a^x\ln a$ |
| $\ln x, \log_a x$ | $\dfrac{1}{x}, \dfrac{1}{x\ln a}$ |

**Quy tắc đại số:** $(u\pm v)' = u'\pm v'$; $(uv)' = u'v+uv'$; $\left(\dfrac{u}{v}\right)' = \dfrac{u'v-uv'}{v^2}$.

**Một số mẹo tuyệt vời:**

**Quy tắc "căn" :**

Thực tế, ở quy tắc $\sqrt{x}$, ta biết thừa rằng nó thực sự phức tạp khi phải chuyển về $\dfrac{1}{2\sqrt{x}}$; Đặc biệt, khi tính đạo hàm bậc 2 hoặc cao hơn, ngày càng thấy được sự phiền toái của nó. Vậy nên ta có thể áp dụng quy tắc này :

$$\sqrt[m]{x^k} \longrightarrow x^{\frac{k}{m}}$$ ;

$$\sqrt{x} \longrightarrow \left(x^{\frac{1}{2}}\right)' = \frac{1}{2}x^{-\frac{1}{2}}$$

Dùng trực tiếp Quy tắc lũy thừa (Power Rule) tổng quát: $(x^n)' = n \cdot x^{n-1}$. 

Còn nếu là căn bậc lớn hơn 2 (kiểu như căn bậc 3) thì cứ 1/3, 1/4,..v.v

Chứng minh :

$$\frac{1}{2}x^{-\frac{1}{2}} = \frac{1}{2} \cdot \frac{1}{x^{\frac{1}{2}}} = \frac{1}{2\sqrt{x}}$$ (Q.E.D)



General Pattern (căn bậc 2) :

$$f^{(n)}(x) = \frac{(-1)^{n-1} \cdot (2n-3)!!}{2^n} x^{-\frac{2n-1}{2}}$$

Nếu bạn thấy hứng thú với những thứ như vậy, có thể thử tham khảo : https://github.com/nahhididwin/toan/blob/main/Derivative-Normalization.md


### A2. Thuật toán ĐẠO HÀM HÀM HỢP (chain rule) — quy trình 3 bước cứng

Cho $y = f(u(x))$:
1. **Bóc lớp ngoài**: coi $u$ là biến, tính $f'(u)$ theo bảng gốc, **giữ nguyên $u$ bên trong**.
2. **Nhân với đạo hàm lớp trong**: nhân thêm $u'(x)$.
3. **Nếu $u$ vẫn còn là hàm hợp** (nhiều lớp lồng nhau) → lặp lại bước 1–2 cho $u$.

> Mẹo dạy: viết công thức tổng quát dạng "**khuôn**" học sinh điền vào:
> $(u^n)' = n\cdot u^{n-1}\cdot u'$; $(\sin u)' = \cos u\cdot u'$; $(e^u)' = e^u\cdot u'$; $(\ln u)' = \dfrac{u'}{u}$; $(\sqrt{u})' = \dfrac{u'}{2\sqrt u}$.
> Học sinh chỉ cần xác định "ai là $u$" rồi thế vào khuôn — không cần hiểu bản chất chain rule.

### A3. Cây quyết định cho bài toán ỨNG DỤNG đạo hàm

```
Đề hỏi gì?
├─ Tính đơn điệu / khoảng đồng biến-nghịch biến
│    → B1: Tìm TXĐ. B2: Tính f'(x). B3: Giải f'(x)=0 tìm nghiệm.
│       B4: Lập bảng xét dấu f'(x) (dùng quy tắc "chẵn/lẻ nghiệm" hoặc thế số).
│       B5: Kết luận khoảng dựa trên dấu f'(x).
│
├─ Cực trị (max/min địa phương)
│    → Giống trên + tại nghiệm x0 của f'(x)=0: nếu f' đổi dấu (+)→(-) là cực đại,
│       (-)→(+) là cực tiểu. (Hoặc dùng f''(x0): f''<0→CĐ, f''>0→CT).
│
├─ GTLN–GTNN trên đoạn [a;b]
│    → B1: Tính f'(x), giải f'(x)=0, lấy các nghiệm x_i thuộc [a;b].
│       B2: Tính f(a), f(b), f(x_i) cho MỌI điểm trên.
│       B3: So sánh — max là GTLN, min là GTNN. (Không cần xét dấu, không cần biết
│       đó là cực đại hay cực tiểu — đây là "lối tắt" cực mạnh cho học sinh yếu).
│
├─ Tiếp tuyến tại điểm (x0; y0)
│    → Hệ số góc k = f'(x0). Phương trình: y = f'(x0)(x - x0) + f(x0).
│
├─ Tiếp tuyến đi qua điểm A (không thuộc đồ thị) / có hệ số góc k cho trước
│    → Gọi tiếp điểm (x0; f(x0)). Viết pt tiếp tuyến tổng quát theo x0.
│       Thế điều kiện đề bài (đi qua A, hoặc f'(x0)=k) → giải ra x0.
│
└─ Bài toán chứa tham số m (biện luận PT có nghiệm, BPT đúng với mọi x...)
     → Kỹ thuật "cô lập m" (bắt buộc dạy đầu tiên vì áp dụng được ~80% bài):
       B1: Biến đổi để đưa m về một vế, phần chứa x về vế còn lại: m = g(x).
       B2: Khảo sát hàm g(x) trên miền xác định (bảng biến thiên).
       B3: Điều kiện có nghiệm/đúng với mọi x ⟺ m nằm trong miền giá trị
           tương ứng của g(x) (đọc trực tiếp từ bảng biến thiên).
```

> **Ghi chú sư phạm:** "Cô lập m" là kỹ thuật quan trọng nhất giúp học sinh yếu trực giác giải được VDC chứa tham số — nó biến bài toán "phải nghĩ" thành bài toán "khảo sát hàm số" thuần túy, vốn đã có quy trình cứng.

---

## PHẦN B — NGUYÊN HÀM & TÍCH PHÂN (trọng tâm, khó nhất)

### B1. Bảng nguyên hàm mở rộng (thuộc lòng)

| $f(x)$ | $\int f(x)dx$ |
|---|---|
| $x^n\ (n\ne-1)$ | $\dfrac{x^{n+1}}{n+1}+C$ |
| $\dfrac1x$ | $\ln|x|+C$ |
| $e^x$ | $e^x+C$ |
| $a^x$ | $\dfrac{a^x}{\ln a}+C$ |
| $\sin x,\ \cos x$ | $-\cos x+C,\ \sin x+C$ |
| $\dfrac1{\cos^2x},\ \dfrac1{\sin^2x}$ | $\tan x+C,\ -\cot x+C$ |
| $\dfrac1{x^2+a^2}$ | $\dfrac1a\arctan\dfrac xa+C$ |
| $\dfrac1{\sqrt{a^2-x^2}}$ | $\arcsin\dfrac xa+C$ |

Và bản "mở rộng theo $u(x)$" — bản này quan trọng hơn bản gốc:
$$\int u^n u'\,dx=\frac{u^{n+1}}{n+1}+C,\quad \int \frac{u'}{u}dx=\ln|u|+C,\quad \int e^u u'\,dx=e^u+C,\quad \int \cos u\cdot u'\,dx=\sin u+C$$

### B2. CÂY QUYẾT ĐỊNH TỔNG QUÁT — "Nhìn thấy tích phân này, làm gì?"

Dạy học sinh chạy tuần tự qua các câu hỏi sau, **theo đúng thứ tự**, dừng lại ở câu đầu tiên trả lời "có":

```
Q1. Có khớp trực tiếp bảng nguyên hàm cơ bản không?
    → CÓ: dùng công thức, xong.

Q2. Biểu thức có dạng g(u(x))·u'(x) — tức là "một hàm của u, nhân đúng đạo hàm
    của u" (kể cả sai hằng số nhân)?
    → CÓ: ĐỔI BIẾN t = u(x). (xem thuật toán B3)
    Dấu hiệu nhận diện nhanh: thấy căn → đặt t = biểu thức trong căn;
    thấy mũ ở số mũ phức tạp → đặt t = số mũ; thấy mẫu là u(x) và tử "giống" u'(x)
    → đặt t = u(x); thấy (ln x) → đặt t = ln x; thấy dx đi kèm sin x·(hàm của cos x)
    → đặt t = cos x (và ngược lại).

Q3. Biểu thức là TÍCH của hai hàm KHÁC LOẠI (đa thức, lượng giác, mũ, log)
    mà không đổi biến được?
    → CÓ: TỪNG PHẦN (xem thuật toán B4).

Q4. Biểu thức là PHÂN THỨC HỮU TỈ P(x)/Q(x) (đa thức trên đa thức)?
    → CÓ: xem thuật toán B5 (chia đa thức + phân tích phân thức đơn giản).

Q5. Biểu thức chứa CĂN THỨC dạng √(a²−x²), √(a²+x²), √(x²−a²)
    (và không đổi biến thẳng được)?
    → CÓ: LƯỢNG GIÁC HÓA (xem thuật toán B6).

Q6. Biểu thức là hàm LƯỢNG GIÁC bậc cao / tích nhiều sin-cos
    (không đổi biến đơn giản được)?
    → CÓ: dùng công thức hạ bậc / biến tích thành tổng, hoặc quy tắc Bioche
    (xem thuật toán B7).

Q7. Là TÍCH PHÂN XÁC ĐỊNH với cận đặc biệt (đối xứng qua 0, hoặc dạng
    ∫₀^(π/2) f(sinx)dx, hoặc chứa hàm ẩn f) ?
    → CÓ: dùng kỹ thuật ĐỔI CẬN ĐỐI XỨNG hoặc TỪNG PHẦN NGƯỢC (xem B8 — dạng VDC).
```

### B3. Thuật toán ĐỔI BIẾN SỐ (quy trình 5 bước cứng)

1. Xác định $u = u(x)$ (phần "phức tạp nhất" nằm trong căn/mũ/mẫu/ngoặc).
2. Tính $du = u'(x)\,dx$.
3. Biến đổi **toàn bộ** biểu thức dưới dấu tích phân (kể cả $dx$) sang biến $t$ (hoặc $u$) — không được để sót $x$ nào.
4. Nếu là tích phân xác định: **đổi luôn cận** theo $u$ (không cần quay lại biến $x$ ở cuối).
5. Tính nguyên hàm theo biến mới, rồi (nếu là nguyên hàm bất định) thế ngược $u=u(x)$ để trả lời theo $x$.

### B4. Thuật toán TỪNG PHẦN — quy tắc chọn $u$: "**NHẤT LOG – NHÌ ĐA – TAM LƯỢNG – TỨ MŨ**"

Công thức: $\displaystyle\int u\,dv = uv-\int v\,du$

Thứ tự ưu tiên chọn $u$ (phần còn lại là $dv$), **theo đúng thứ tự liệt kê, ưu tiên cái đứng trước**:
1. **Log**: nếu có $\ln x$ hay $\log_a x$ → luôn chọn $u=\ln x$ (vì $\ln x$ không có nguyên hàm cơ bản đơn giản mà đạo hàm lại rất đơn giản $\to 1/x$).
2. **Đa thức**: nếu không có log, chọn $u = $ đa thức (đạo hàm làm giảm bậc).
3. **Lượng giác**: nếu chỉ còn lượng giác và mũ, có thể chọn $u=$ hàm lượng giác (lưu ý bài "quay vòng" — xem dưới).
4. **Mũ**: $dv$ chứa $e^x$ hầu như luôn nằm ở phần $dv$.

**Quy trình 4 bước:**
1. Xác định $u$ theo quy tắc trên, phần còn lại là $dv$.
2. Tính $du$ (đạo hàm $u$) và $v=\int dv$ (nguyên hàm của $dv$, không cộng $+C$ ở bước trung gian).
3. Thế vào công thức $uv-\int v\,du$.
4. Nếu $\int v\,du$ vẫn chưa tính được ngay → **lặp lại từng phần lần 2** (đôi khi cần lần 3). 
   - Trường hợp đặc biệt "**tích phân quay vòng**" (loại $\int e^x\sin x\,dx$): sau 2 lần từng phần sẽ xuất hiện lại chính tích phân ban đầu ở vế phải → chuyển vế, giải như phương trình bậc nhất ẩn là tích phân đó.

### B5. Thuật toán TÍCH PHÂN HÀM HỮU TỈ $\dfrac{P(x)}{Q(x)}$

1. **So bậc**: nếu bậc $P \ge$ bậc $Q$ → chia đa thức trước, viết $\dfrac{P}{Q} = $ (đa thức) $+ \dfrac{R(x)}{Q(x)}$ với bậc $R <$ bậc $Q$.
2. Phân tích mẫu $Q(x)$ thành tích các nhân tử bậc nhất/bậc hai vô nghiệm.
3. Phân tích $\dfrac{R(x)}{Q(x)}$ thành tổng các phân thức đơn giản dạng $\dfrac{A}{x-a}$, $\dfrac{A}{(x-a)^k}$, hoặc $\dfrac{Ax+B}{x^2+px+q}$ (đồng nhất hệ số hoặc thế nghiệm để tìm A, B...).
4. Tích phân từng phân thức đơn giản (đều thuộc dạng bảng cơ bản hoặc dạng $\arctan$).

### B6. Thuật toán LƯỢNG GIÁC HÓA (cho tích phân chứa căn)

| Dạng căn thức | Phép đặt |
|---|---|
| $\sqrt{a^2-x^2}$ | $x=a\sin t,\ t\in[-\pi/2;\pi/2]$ |
| $\sqrt{a^2+x^2}$ | $x=a\tan t$ |
| $\sqrt{x^2-a^2}$ | $x=\dfrac{a}{\cos t}$ |

Quy trình: đặt theo bảng → tính $dx$ theo $dt$ → căn thức sẽ **rút gọn hết dấu căn** (dùng $1-\sin^2=\cos^2$,...) → đưa về tích phân lượng giác thuần túy (dùng B7) → đổi cận (nếu xác định) hoặc đổi ngược lại biến $x$ qua $t=\arcsin,\arctan,...$ (nếu bất định).

### B7. Thuật toán TÍCH PHÂN LƯỢNG GIÁC (khi không đổi biến đơn giản được)

Áp dụng **quy tắc Bioche** — xét biểu thức $f(x)dx$ dưới phép đổi biến, chọn theo tính chẵn–lẻ:
- Nếu $f(-x)dx=-f(x)dx$ khi thay $x\to -x$ (lẻ theo $\sin$) → đặt $t=\cos x$.
- Nếu bất biến khi thay $x\to \pi-x$ (lẻ theo $\cos$) → đặt $t=\sin x$.
- Nếu bất biến khi thay $x\to \pi+x$ → đặt $t=\tan x$.
- Nếu không rơi vào 3 trường hợp trên → dùng **công thức hạ bậc** ($\sin^2x=\dfrac{1-\cos2x}{2}$, $\cos^2x=\dfrac{1+\cos2x}{2}$) hoặc **biến đổi tích thành tổng**, hoặc phép thế **Weierstrass** $t=\tan\dfrac x2$ (phép đặt "vạn năng" — dùng khi mọi cách khác thất bại, vì luôn đưa lượng giác về hàm hữu tỉ theo $t$, rồi quay lại thuật toán B5).

### B8. KỸ THUẬT VDC (Vận dụng cao) cho tích phân

Đây là phần quan trọng nhất để "gần như giải được mọi bài", kể cả khi hàm $f$ chỉ cho ẩn qua tính chất:

**a) Tích phân từng phần "ngược" khi biết $f'(x)$, cần tính liên quan đến $f(x)$:**
Nếu đề cho $f'(x)$ và một biểu thức liên hệ, hãy thử đặt $u=f(x)$ (hoặc $f(x)\pm g(x)$), $dv$ là phần còn lại, rồi dùng $\int u\,dv = uv-\int v\,du$ để "chuyển" tích phân của $f$ thành tích phân của $f'$ (đã biết) — kỹ thuật này giải quyết phần lớn dạng "tích phân hàm ẩn".

**b) Đối xứng cận tích phân**: Với $\displaystyle I=\int_a^b f(x)dx$, thử đặt $t=a+b-x$ (đối xứng qua trung điểm) — nếu $f(a+b-x)$ liên hệ đơn giản với $f(x)$ (bằng nhau, hoặc cộng ra hằng số), ta lập được phương trình cho $I$.
- Dạng kinh điển: $\displaystyle\int_0^{\pi/2} f(\sin x)dx=\int_0^{\pi/2} f(\cos x)dx$ (đặt $t=\pi/2-x$).

**c) Đặt $t = \dfrac{a}{x}$** cho cận từ $\dfrac1a$ đến $a$ hoặc tương tự, khi biểu thức có tính đối xứng nhân.

**d) Không tính ra được biểu tường minh?** Dùng Newton–Leibniz ngược: nếu biết $F(a)$ và cần tính $\int_a^b f$, chỉ cần tìm **một** nguyên hàm $F$ thỏa điều kiện đề cho, rồi $\int_a^b f = F(b)-F(a)$ — không cần công thức tổng quát của $f$.

### B9. Ứng dụng tích phân — quy trình cứng

**Diện tích hình phẳng giới hạn bởi $y=f(x), y=g(x), x=a, x=b$:**
1. Giải $f(x)=g(x)$ tìm nghiệm $x_i \in (a,b)$ (các điểm cắt nhau).
2. Diện tích $=\displaystyle\int_a^b |f(x)-g(x)|dx$, tách thành tổng các tích phân trên từng khoảng con giữa các nghiệm $x_i$ (trên mỗi khoảng, $f-g$ không đổi dấu nên bỏ được dấu trị tuyệt đối, chỉ cần xét dấu 1 lần bằng cách thế 1 điểm đại diện).

**Thể tích khối tròn xoay quanh $Ox$** trên $[a,b]$: $\displaystyle V=\pi\int_a^b [f(x)]^2dx$.
Quanh $Oy$: đổi vai trò $x\leftrightarrow y$, viết $x=g(y)$ rồi $V=\pi\int [g(y)]^2 dy$.

---

## PHẦN C — BẢNG NHẬN DIỆN NHANH (dán lên bàn học)

| Nhìn thấy... | Làm gì |
|---|---|
| $\ln x$ trong tích | Từng phần, $u=\ln x$ |
| Đa thức $\times \sin/\cos/e^x$ | Từng phần, $u=$ đa thức |
| $e^x\sin x$ hoặc $e^x\cos x$ | Từng phần **2 lần** → phương trình quay vòng |
| Mẫu là đa thức bậc ≥1 | Hữu tỉ: chia rồi phân tích phân thức |
| $\sqrt{a^2-x^2}$ | Đặt $x=a\sin t$ |
| $\sqrt{a^2+x^2}$ hoặc mẫu $x^2+a^2$ | Đặt $x=a\tan t$ |
| Căn của biểu thức bậc nhất/bậc hai đơn giản | Đặt $t=$ biểu thức trong căn |
| $f(u(x))\cdot u'(x)$ rõ ràng | Đổi biến $t=u(x)$ |
| Tích nhiều $\sin,\cos$ bậc cao | Hạ bậc / tích thành tổng / Bioche |
| Tích phân xác định, hàm $f$ cho ẩn qua $f'$ hoặc hệ thức | Từng phần ngược (B8a) hoặc Newton–Leibniz trực tiếp |
| Cận đối xứng ($-a\to a$, $0\to\pi/2$...) | Đổi biến $t=-x$ hoặc $t=\pi/2-x$ (B8b) |

---

## PHẦN D — "LỐI THOÁT HIỂM" KHI BÍ (đặc biệt hữu ích cho trắc nghiệm VDC)

Vì đề thi Việt Nam (THPT QG) là trắc nghiệm, đây là vũ khí quan trọng nhất cho học sinh yếu trực giác:

1. **Dùng máy tính cầm tay (MTCT — Casio/Vinacal)**:
   - Tính đạo hàm tại 1 điểm: dùng chức năng `d/dx` tại giá trị cụ thể → so khớp với đáp án đã đạo hàm sẵn bằng tay.
   - Tính tích phân xác định bằng số: dùng chức năng `∫` tính giá trị số của $\int_a^b f(x)dx$ → thế số vào từng đáp án xem đáp án nào cho cùng giá trị.
   - Với nguyên hàm (trắc nghiệm chọn $F(x)$ đúng): đạo hàm ngược từng đáp án bằng máy, đáp án nào ra đúng $f(x)$ ban đầu (thử tại 1–2 giá trị $x$) là đáp án đúng.
2. **Thế số cụ thể** thay cho biến hoặc tham số tổng quát, đặc biệt hóa bài toán để loại đáp án sai.
3. **Thử ngược từ đáp án** (đặc biệt với bài "tìm $m$ để..."): thế từng đáp án $m$ vào điều kiện đề bài, xem thỏa mãn không.
4. Không bao giờ time-out ở một cách — nếu hết 3–4 phút chưa ra hướng, chuyển ngay sang chiến thuật máy tính/thế số.

---

## PHẦN E — LỘ TRÌNH LUYỆN TẬP ĐỀ XUẤT

1. **Giai đoạn 1 (thuộc bảng)**: học thuộc lòng bảng đạo hàm, bảng nguyên hàm (Phần A1, B1) đến khi phản xạ tức thời.
2. **Giai đoạn 2 (luyện từng dạng riêng lẻ)**: làm 15–20 bài **chỉ một dạng duy nhất** cho mỗi thuật toán con (chỉ đổi biến, rồi mới chỉ từng phần, rồi mới chỉ hữu tỉ...) — **không trộn dạng** ở giai đoạn này.
3. **Giai đoạn 3 (luyện nhận diện)**: cho 30 bài trộn lẫn ngẫu nhiên các dạng, học sinh **chỉ cần nói ra "đây là dạng gì, dùng thuật toán nào"** mà chưa cần giải hết — luyện phản xạ phân loại trước khi luyện tốc độ giải.
4. **Giai đoạn 4 (VDC)**: luyện riêng B8 (kỹ thuật hàm ẩn, đối xứng) và Phần D (mẹo casio) — đây là phần tạo ra sự khác biệt ở điểm 9–10.
5. **Luôn kiểm tra ngược** (đạo hàm lại nguyên hàm vừa tìm) sau mỗi bài — thói quen này tự sửa lỗi mà không cần trực giác.
