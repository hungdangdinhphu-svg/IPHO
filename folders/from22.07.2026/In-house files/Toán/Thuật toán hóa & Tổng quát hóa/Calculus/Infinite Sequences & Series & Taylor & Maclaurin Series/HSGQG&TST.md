# Taylor & Maclaurin Series cho HSGQG, TST Vật Lý
### Bài giảng: Từ trực giác đến thuật toán giải bài tập

> Tài liệu này được viết theo đúng tinh thần "Thảo luận lớn" mà bạn đang xây dựng: không dừng ở "dùng được", mà phải biết **điều kiện cần/đủ (Pre/Suf)**, **bất biến phải giữ**, và có một **quy trình gần như máy móc** để áp dụng khi làm bài. Taylor/Maclaurin chính là một trong những CÔNG CỤ (ℓ) xuất hiện nhiều nhất trong lời giải HSGQG, TST, VPHO, IPhO — gần như mọi bài có "gần đúng", "dao động nhỏ", "nhiễu loạn", "góc nhỏ" đều là một bài toán Taylor trá hình.

---

## PHẦN 0: TẠI SAO PHẢI HỌC KỸ CÁI NÀY?

Trong ngôn ngữ của tài liệu gốc: Taylor/Maclaurin là một **CÔNG CỤ ℓ**, và công việc của bạn là phải biết chính xác:

- **Dom(ℓ)**: miền hàm số mà công cụ này áp dụng được (hàm phải khả vi đến bậc nào đó).
- **Pre(ℓ)**: điều kiện cần để áp dụng (có một "biến nhỏ" thực sự, có điểm khai triển hợp lý).
- **Suf(ℓ)**: điều kiện đủ để kết quả đáng tin (sai số control được, bậc giữ lại đủ để không "triệt tiêu" thông tin vật lý cần tìm).
- **Post(ℓ)**: cái bạn thu được (một đa thức xấp xỉ hàm ban đầu quanh một điểm).
- **Err(ℓ)**: sai số — phần dư Lagrange/Peano.

Nếu bạn chỉ nhớ "công thức khai triển sin x ≈ x" mà không hiểu 5 thứ trên, bạn đang **pattern-matching bề mặt** — đúng thứ mà tài liệu gốc cảnh báo là con đường dẫn đến sụp đổ khi đề thi "lệch đi".

---

## PHẦN 1: XÂY DỰNG TRỰC GIÁC (trước khi vào công thức)

### 1.1. Câu hỏi gốc rễ

Giả sử bạn biết giá trị của một hàm $f$ và tất cả đạo hàm của nó **tại một điểm duy nhất** $x = a$. Câu hỏi: bạn có thể dự đoán được giá trị của $f$ tại một điểm **lân cận** $x$ gần $a$ hay không, mà không cần biết công thức tường minh của $f$ ở xa?

Trực giác: Có. Vì đạo hàm cấp 1 cho biết hàm đang "nghiêng" bao nhiêu, đạo hàm cấp 2 cho biết độ "cong", đạo hàm cấp 3 cho biết độ cong đang thay đổi nhanh ra sao,... Càng biết nhiều đạo hàm, bạn càng "tái dựng" được hình dạng hàm số chính xác hơn trong một vùng lân cận $a$.

### 1.2. Hình ảnh hóa

Hãy tưởng tượng bạn đang lái một chiếc xe và chỉ biết:

- Vị trí hiện tại $f(a)$ — xấp xỉ bậc 0 (hằng số, "đứng yên tại chỗ").
- Vận tốc hiện tại $f'(a)$ — xấp xỉ bậc 1 (đường thẳng tiếp tuyến).
- Gia tốc hiện tại $f''(a)$ — xấp xỉ bậc 2 (parabol ôm sát đường cong hơn).
- Độ biến thiên gia tốc $f'''(a)$ — xấp xỉ bậc 3,...

Mỗi bậc đạo hàm thêm vào là một lớp thông tin tinh chỉnh giúp "đường cong xấp xỉ" bám sát đường cong thật hơn **trong một lân cận đủ nhỏ** của $a$. Đây chính là bản chất vật lý–hình học của chuỗi Taylor: **xấp xỉ đa thức địa phương (local polynomial approximation)**.

### 1.3. Vì sao Vật Lý cần nó đến thế?

Phần lớn các định luật Vật Lý là **phi tuyến** (sin, cos, $1/r^2$, $\sqrt{1-v^2/c^2}$,...). Nhưng phương trình vi phân phi tuyến thường **không giải được bằng hàm sơ cấp**. Trong khi đó, phương trình vi phân **tuyến tính** (đặc biệt là dao động điều hòa $\ddot{x} = -\omega^2 x$) thì luôn giải được.

$\Rightarrow$ Taylor là cây cầu: nó biến một hàm phi tuyến phức tạp thành **một đa thức** (mà số hạng bậc thấp nhất thường là tuyến tính) — từ đó bài toán phi tuyến "khó nhằn" trở thành bài toán tuyến tính "máy móc" mà bạn đã có đầy đủ công cụ để giải (dao động điều hòa, phương trình đặc trưng,...).

**Đây chính là một trong những "CHỖ" phổ biến nhất mà bài toán gài bẫy:** cho một hệ trông có vẻ phi tuyến/phức tạp (lực hấp dẫn, con lắc, điện thế,...), nhưng "gợi ý ngầm" (dao động "nhỏ", biến dạng "bé", $v \ll c$,...) chính là lệnh ngầm: "Hãy Taylor hóa quanh điểm cân bằng/giá trị gốc, rồi dùng công cụ tuyến tính."

---

## PHẦN 2: PHÁT BIỂU TOÁN HỌC CHẶT CHẼ

### 2.1. Chuỗi Taylor tổng quát

Cho hàm $f$ khả vi vô hạn lần ($f \in C^\infty$) trong một lân cận của điểm $a$. Chuỗi Taylor của $f$ tại $a$ là:

$$f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!}(x-a)^n = f(a) + f'(a)(x-a) + \frac{f''(a)}{2!}(x-a)^2 + \frac{f'''(a)}{3!}(x-a)^3 + \cdots$$

### 2.2. Chuỗi Maclaurin — trường hợp đặc biệt $a = 0$

$$f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(0)}{n!}x^n = f(0) + f'(0)x + \frac{f''(0)}{2!}x^2 + \cdots$$

**Lưu ý quan trọng (hay bị hiểu nhầm):** Maclaurin **không phải là một công cụ khác** — nó chỉ là Taylor với $a=0$. Trong Vật Lý, "điểm 0" thường không phải là số 0 theo nghĩa toán thuần túy, mà là **điểm cân bằng, trạng thái chuẩn, hoặc giá trị gốc của hệ** (ví dụ góc lệch $\theta = 0$ ở VTCB, biến dạng $x=0$ khi lò xo tự nhiên, vận tốc $v = 0$,...). Việc chọn đúng điểm khai triển $a$ **chính là một phần của bước Mô Hình Hóa**, không phải bước thuần túy toán học.

### 2.3. Đa thức Taylor bậc $n$ và phần dư

$$f(x) = \underbrace{\sum_{k=0}^{n} \frac{f^{(k)}(a)}{k!}(x-a)^k}_{T_n(x) \text{ — đa thức Taylor bậc } n} + \underbrace{R_n(x)}_{\text{phần dư (sai số)}}$$

Hai dạng phần dư hay dùng:

**Dạng Lagrange** (quan trọng nhất cho Vật Lý vì cho đánh giá sai số *định lượng*):

$$R_n(x) = \frac{f^{(n+1)}(\xi)}{(n+1)!}(x-a)^{n+1}, \quad \xi \in (a, x)$$

**Dạng Peano (bậc nhỏ — big-O)** — dùng khi chỉ cần biết *bậc* của sai số, không cần giá trị cụ thể:

$$R_n(x) = o\big((x-a)^n\big) \quad \text{khi } x \to a$$

**Đây chính là Err(ℓ) trong ngôn ngữ mô hình hóa của bạn.** Một lời giải Vật Lý dùng Taylor mà không nêu được sai số đang bỏ qua là lời giải **chưa well-posed** theo đúng 7 điều kiện bạn đã đặt ra (điều kiện (2) Soundness và (5) Well-posedness).

---

## PHẦN 3: ĐIỀU KIỆN CẦN & ĐỦ (Pre/Suf) — PHẦN QUAN TRỌNG NHẤT

Đây là phần thường bị bỏ qua trong sách giáo khoa phổ thông nhưng **chính là nơi đề thi HSGQG/TST gài bẫy**.

### 3.1. Điều kiện để chuỗi Taylor **tồn tại được** (Dom)

| Điều kiện | Ý nghĩa | Ví dụ phản chứng |
|---|---|---|
| $f$ khả vi vô hạn lần tại $a$ | Mọi $f^{(n)}(a)$ phải tồn tại | $f(x) = \lvert x \rvert$ không khả vi tại $0$ |
| Chuỗi phải **hội tụ** trong một khoảng quanh $a$ | Bán kính hội tụ $R > 0$ | $f(x) = e^{-1/x^2}$ (với $f(0)=0$): mọi đạo hàm tại $0$ đều bằng $0$ nhưng hàm không trùng với chuỗi Taylor của nó — "khả vi vô hạn" KHÔNG đảm bảo hàm bằng chuỗi Taylor của chính nó! |

**Cảnh báo cực kỳ quan trọng:** $f$ khả vi vô hạn lần tại $a$ là điều kiện **cần**, nhưng **không đủ** để $f(x)$ bằng chuỗi Taylor của nó. Điều kiện **đủ** chuẩn và hay dùng nhất trong thi cử: $R_n(x) \to 0$ khi $n \to \infty$ (tức là phần dư Lagrange tiến về 0). Trong hầu hết các hàm Vật Lý quen thuộc (sin, cos, $e^x$, $\ln(1+x)$, $(1+x)^\alpha$), điều này đúng trong miền hội tụ của chúng — nhưng bạn phải **biết miền đó là gì**, đừng mặc định "cứ Taylor là được".

### 3.2. Điều kiện để **dùng Taylor có ý nghĩa Vật Lý** (đây là phần "Pre" theo tinh thần tài liệu gốc của bạn)

Đây mới là phần quyết định bạn có tìm đúng "**CHỖ**" để dùng công cụ hay không:

**(a) Phải tồn tại một "biến nhỏ không thứ nguyên" (dimensionless small parameter) $\varepsilon$.**

Đây là điều kiện **cần** gần như tuyệt đối. Taylor khai triển hàm theo $(x-a)$, nhưng trong Vật Lý, cái thực sự "nhỏ" phải là một **tỉ số không thứ nguyên**, ví dụ:

- Góc lệch con lắc: $\varepsilon = \theta$ (radian — vốn không thứ nguyên).
- Dao động quanh VTCB: $\varepsilon = x/L$ (tỉ số biến dạng trên độ dài đặc trưng).
- Hiệu ứng tương đối tính: $\varepsilon = v/c$.
- Nhiễu loạn thế năng: $\varepsilon = $ (độ lớn nhiễu loạn)/(độ lớn thế năng chính).
- Gần đúng lưỡng cực xa: $\varepsilon = d/r$ (khoảng cách hai điện tích chia khoảng cách quan sát).

**Nếu bạn không chỉ ra được $\varepsilon \ll 1$ là gì, bạn chưa đủ điều kiện để Taylor hóa — đây là lỗi phổ biến nhất của học sinh: "thấy có $\sin\theta$ thì cứ xấp xỉ $\theta$" mà không hỏi "vậy bài có nói gì về độ lớn của $\theta$ không?"**

**(b) Phải xác định đúng điểm khai triển $a$ — đây là bước Mô Hình Hóa, không máy móc.**

$a$ thường là: vị trí cân bằng, trạng thái không nhiễu loạn, giới hạn phi tương đối tính ($v=0$),... Chọn sai $a$ ($a$ không phải là điểm mà hệ dao động/biến thiên quanh nó) sẽ cho một khai triển vô nghĩa về mặt Vật Lý dù vẫn đúng về mặt toán học thuần túy.

**(c) Phải xác định đúng bậc cần giữ lại — đây là điều kiện ĐỦ (Suf) quan trọng nhất.**

Đây là nơi phần lớn sai lầm nghiêm trọng xảy ra. Quy tắc:

> **Giữ bậc thấp nhất mà tại đó số hạng đó khác 0 VÀ đóng góp vào đại lượng Vật Lý mà đề bài hỏi.**

Ví dụ kinh điển — vì sao con lắc đơn dùng $\sin\theta \approx \theta$ (bậc 1) chứ không phải bậc 0:

- Bậc 0: $\sin\theta \approx 0$ → phương trình chuyển động trở thành $0 = 0$, **vô nghĩa, mất hết Vật Lý**. Đây là ví dụ "triệt tiêu thông tin vật lý cần tìm" mà tài liệu gốc của bạn cảnh báo.
- Bậc 1: $\sin\theta \approx \theta$ → $\ddot\theta = -\frac{g}{l}\theta$: phương trình dao động điều hòa, đúng là Vật Lý cần tìm (tần số dao động nhỏ).
- Nếu đề hỏi **hiệu chỉnh phi tuyến của chu kỳ** (anharmonic correction), bậc 1 lại **không đủ** — phải lấy đến bậc 3: $\sin\theta \approx \theta - \theta^3/6$, vì bản thân hiệu ứng cần tìm (độ lệch chu kỳ so với $2\pi\sqrt{l/g}$) chỉ "sống" ở bậc 3 trở lên.

**Quy tắc vàng:** *Bậc cần giữ không phải là một số cố định "luôn lấy đến bậc 2" — mà phụ thuộc vào việc đại lượng Vật Lý bạn cần tìm xuất hiện lần đầu ở bậc nào trong khai triển.* Đây chính là mối liên hệ trực tiếp với **Vấn đề 2 — Vấn đề tìm kiếm CHỖ** mà bạn đã nêu: "CHỖ" ở đây là "bậc khai triển nào chứa thông tin cần tìm".

**(d) Phải kiểm tra tính tự hợp (self-consistency).**

Sau khi giải xong với xấp xỉ bậc $n$, hãy kiểm tra: nghiệm thu được có **thỏa mãn ngược lại** điều kiện $\varepsilon \ll 1$ ban đầu không? Nếu nghiệm cho ra $\varepsilon \sim 1$ thì xấp xỉ **tự mâu thuẫn** — đây là một dạng kiểm tra "Consistency" (điều kiện (4) trong 7 điều kiện của bạn).

### 3.3. Tóm tắt Pre(ℓ) và Suf(ℓ) của Taylor trong Vật Lý

| | Điều kiện | Nếu vi phạm |
|---|---|---|
| **Pre (cần)** | Tồn tại $\varepsilon \ll 1$ không thứ nguyên, hàm khả vi đủ bậc quanh điểm khai triển $a$ hợp lý về mặt Vật Lý | Khai triển vô nghĩa hoặc không hội tụ |
| **Suf (đủ)** | Bậc giữ lại chứa đúng thông tin Vật Lý cần tìm; $R_n \to 0$ trong miền $\varepsilon$ đang xét; nghiệm cuối tự hợp với giả thiết $\varepsilon \ll 1$ | Kết quả "đúng công thức, sai Vật Lý" — mất hiện tượng hoặc dự đoán sai hệ số |

---

## PHẦN 4: BẤT BIẾN PHẢI GIỮ KHI XẤP XỈ (INVARIANTS)

Dù xấp xỉ, một số "bất biến" buộc phải được tôn trọng, nếu không lời giải sẽ **mất tính Soundness**:

1. **Tính đối xứng của hệ phải được bảo toàn trong khai triển.** Ví dụ: nếu thế năng $U(x)$ là hàm chẵn quanh VTCB ($U(x) = U(-x)$), thì khai triển Taylor của nó quanh VTCB **không có số hạng bậc lẻ** (bậc 1, 3,...) — nếu bạn tính ra có số hạng bậc lẻ, gần như chắc chắn bạn đã tính sai hoặc chọn sai điểm khai triển.

2. **Bậc 1 tại điểm cân bằng phải triệt tiêu.** Nếu $a$ thực sự là điểm cân bằng (cực trị của thế năng), thì theo định nghĩa $U'(a) = 0$ — đây là một ràng buộc **kiểm tra chéo**: nếu sau khi khai triển bạn thấy số hạng bậc 1 khác 0, thì hoặc $a$ không phải điểm cân bằng, hoặc bạn tính sai đạo hàm.

3. **Thứ nguyên (dimensional consistency) của từng số hạng trong chuỗi phải giống nhau** (đều là thứ nguyên của $f$). Đây là công cụ kiểm tra lỗi cực nhanh: nếu bạn viết $f(x) \approx f(a) + f'(a)x$ (quên nhân $(x-a)$, hoặc quên chia giai thừa), thứ nguyên sẽ lệch ngay và bạn phát hiện được lỗi.

4. **Bảo toàn năng lượng/động lượng (nếu có) phải đúng đến cùng bậc xấp xỉ.** Một lỗi tinh vi hay gặp: giữ động năng đến bậc 2 nhưng thế năng chỉ đến bậc 1 (hoặc ngược lại) — phá vỡ tính nhất quán bậc (order-consistency), dẫn đến phương trình chuyển động sai dạng. **Quy tắc: luôn khai triển MỌI đại lượng trong bài toán đến CÙNG MỘT bậc của $\varepsilon$ trước khi ráp vào phương trình.**

---

## PHẦN 5: THƯ VIỆN CÁC KHAI TRIỂN MACLAURIN CHUẨN (thuộc lòng, có sai số)

Đặt $x$ là biến nhỏ không thứ nguyên ($|x| \ll 1$ trừ khi ghi chú khác).

| Hàm | Khai triển (đến vài bậc đầu) | Miền hội tụ | Bậc đầu tiên khác 0 |
|---|---|---|---|
| $e^x$ | $1 + x + \dfrac{x^2}{2!} + \dfrac{x^3}{3!} + \cdots$ | mọi $x$ | — |
| $\sin x$ | $x - \dfrac{x^3}{3!} + \dfrac{x^5}{5!} - \cdots$ | mọi $x$ | bậc 1 |
| $\cos x$ | $1 - \dfrac{x^2}{2!} + \dfrac{x^4}{4!} - \cdots$ | mọi $x$ | bậc 0 (hằng), bậc khác-0 đầu tiên là bậc 2 |
| $\tan x$ | $x + \dfrac{x^3}{3} + \dfrac{2x^5}{15} + \cdots$ | $\lvert x\rvert < \pi/2$ | bậc 1 |
| $\ln(1+x)$ | $x - \dfrac{x^2}{2} + \dfrac{x^3}{3} - \cdots$ | $-1 < x \le 1$ | bậc 1 |
| $(1+x)^{\alpha}$ (nhị thức tổng quát) | $1 + \alpha x + \dfrac{\alpha(\alpha-1)}{2!}x^2 + \cdots$ | $\lvert x\rvert < 1$ | tùy $\alpha$ |
| $\dfrac{1}{1+x}$ | $1 - x + x^2 - x^3 + \cdots$ | $\lvert x \rvert < 1$ | bậc 0 |
| $\dfrac{1}{1-x}$ | $1 + x + x^2 + x^3 + \cdots$ | $\lvert x \rvert < 1$ | bậc 0 |
| $\sqrt{1+x}$ | $1 + \dfrac{x}{2} - \dfrac{x^2}{8} + \dfrac{x^3}{16} - \cdots$ | $\lvert x \rvert < 1$ | bậc 0 |
| $\dfrac{1}{\sqrt{1-x}}$ | $1 + \dfrac{x}{2} + \dfrac{3x^2}{8} + \cdots$ | $\lvert x\rvert < 1$ | bậc 0 |

**Các khai triển "đặc sản Vật Lý" dẫn xuất trực tiếp từ bảng trên (học thuộc gốc, tự suy ra các cái này, đừng học vẹt):**

- **Hệ số Lorentz** (Thuyết tương đối hẹp): với $\beta = v/c \ll 1$,
$$\gamma = \frac{1}{\sqrt{1-\beta^2}} \approx 1 + \frac{1}{2}\beta^2 + \frac{3}{8}\beta^4 + \cdots \quad \Rightarrow \quad E_k = (\gamma - 1)mc^2 \approx \frac{1}{2}mv^2 + \frac{3}{8}\frac{mv^4}{c^2} + \cdots$$
(số hạng đầu tái hiện đúng động năng cổ điển Newton — một "bất biến" cần kiểm tra khi học tương đối tính).

- **Thế hấp dẫn/tĩnh điện ở gần mặt đất** (với $h \ll R$):
$$\frac{1}{(R+h)^2} = \frac{1}{R^2}\left(1+\frac{h}{R}\right)^{-2} \approx \frac{1}{R^2}\left(1 - \frac{2h}{R} + \cdots\right)$$

- **Gần đúng lưỡng cực điện** (với $d \ll r$): dẫn ra trực tiếp từ $(1+x)^{-1/2}$ hoặc $(1+x)^{-3/2}$ khi khai triển $\frac{1}{\sqrt{r^2 \mp rd\cos\theta + d^2/4}}$.

---

## PHẦN 6: "THUẬT TOÁN" — QUY TRÌNH GẦN NHƯ MÁY MÓC ĐỂ GIẢI BÀI BẰNG TAYLOR

Đây là phiên bản cụ thể hóa cho Taylor của "Bài Toán Tìm Kiếm" (ℓ, CHỖ) mà bạn đã đặt ra ở Phần 0 tài liệu gốc.

```
┌──────────────────────────────────────────────────────────┐
│  BƯỚC 0 — NHẬN DIỆN TÍN HIỆU                              │
│  Đề có từ khóa: "nhỏ", "bé", "gần đúng", "xấp xỉ bậc nhất",│
│  "nhiễu loạn nhỏ", hoặc ẩn ý vật lý: v≪c, d≪r, biên độ nhỏ,│
│  góc nhỏ, khối lượng nhỏ so với...                         │
│  → Đây là "gợi ý ngầm": chuẩn bị dùng Taylor.              │
└───────────────────────────┬────────────────────────────────┘
                            │
┌───────────────────────────▼────────────────────────────────┐
│  BƯỚC 1 — XÁC ĐỊNH BIẾN NHỎ ε KHÔNG THỨ NGUYÊN              │
│  Viết tường minh: ε = ? (vd: ε = θ, ε = v/c, ε = x/L)      │
│  Nếu không lập được ε không thứ nguyên → DỪNG, chưa đủ     │
│  điều kiện Pre(ℓ), tìm công cụ/mô hình khác.               │
└───────────────────────────┬────────────────────────────────┘
                            │
┌───────────────────────────▼────────────────────────────────┐
│  BƯỚC 2 — XÁC ĐỊNH ĐIỂM KHAI TRIỂN a (Mô hình hóa)          │
│  a = trạng thái cân bằng / giới hạn chuẩn / giá trị gốc.   │
│  Kiểm tra bất biến: nếu a là cực trị thế năng → f'(a)=0.   │
└───────────────────────────┬────────────────────────────────┘
                            │
┌───────────────────────────▼────────────────────────────────┐
│  BƯỚC 3 — XÁC ĐỊNH BẬC CẦN GIỮ n                            │
│  Hỏi: đại lượng Vật Lý cần tìm xuất hiện sớm nhất ở bậc    │
│  nào? Nếu bậc thấp nhất triệt tiêu (=0) hoặc không chứa    │
│  thông tin cần tìm → tăng n lên.                           │
└───────────────────────────┬────────────────────────────────┘
                            │
┌───────────────────────────▼────────────────────────────────┐
│  BƯỚC 4 — KHAI TRIỂN TẤT CẢ ĐẠI LƯỢNG LIÊN QUAN ĐẾN CÙNG    │
│  MỘT BẬC ε (động năng, thế năng, lực, ràng buộc hình học,  │
│  mọi hàm lượng giác/căn xuất hiện trong bài — đồng bộ bậc) │
└───────────────────────────┬────────────────────────────────┘
                            │
┌───────────────────────────▼────────────────────────────────┐
│  BƯỚC 5 — RÁP VÀO CÔNG CỤ CHÍNH (Newton II, Lagrangian,    │
│  bảo toàn năng lượng,...) → thu phương trình đã TUYẾN TÍNH │
│  HÓA (hoặc đơn giản hóa đáng kể so với bài gốc)            │
└───────────────────────────┬────────────────────────────────┘
                            │
┌───────────────────────────▼────────────────────────────────┐
│  BƯỚC 6 — GIẢI PHƯƠNG TRÌNH ĐÃ ĐƠN GIẢN HÓA (Vấn đề 3)     │
└───────────────────────────┬────────────────────────────────┘
                            │
┌───────────────────────────▼────────────────────────────────┐
│  BƯỚC 7 — KIỂM TRA TÍNH TỰ HỢP & GIỚI HẠN                  │
│  • Nghiệm có thỏa ε ≪ 1 ngược lại không?                   │
│  • Khi ε → 0, kết quả có về đúng trường hợp lý tưởng/cổ    │
│    điển đã biết không? (vd: γ→1 khi v→0)                   │
│  • Thứ nguyên có khớp không?                               │
│  • Đối xứng có được tôn trọng không (bậc lẻ/chẵn)?         │
└──────────────────────────────────────────────────────────┘
```

### 6.1. Ví dụ áp dụng thuật toán — Con lắc đơn góc nhỏ

- **Bước 0:** Đề cho "dao động nhỏ" hoặc biên độ góc $\theta_0$ nhỏ.
- **Bước 1:** $\varepsilon = \theta$ (radian, không thứ nguyên). ✓.
- **Bước 2:** $a = 0$ (VTCB thẳng đứng).
- **Bước 3:** Cần tìm phương trình dao động → cần số hạng tuyến tính tồn tại → bậc 1 đủ (vì $\sin\theta$ có bậc khác-0 đầu tiên là bậc 1, không triệt tiêu).
- **Bước 4:** $\sin\theta \approx \theta$.
- **Bước 5:** $ml\ddot\theta = -mg\sin\theta \approx -mg\theta \Rightarrow \ddot\theta = -\dfrac{g}{l}\theta$.
- **Bước 6:** Đây là phương trình dao động điều hòa chuẩn $\Rightarrow \omega = \sqrt{g/l}$, $T = 2\pi\sqrt{l/g}$.
- **Bước 7:** Khi $l \to \infty$ hoặc $g \to 0$, $T \to \infty$ — hợp lý vật lý. Thứ nguyên: $\sqrt{[l]/[g]} = \sqrt{\text{m}/(\text{m/s}^2)} = \text{s}$ ✓.

### 6.2. Ví dụ bậc cao hơn — Hiệu chỉnh phi tuyến của chu kỳ con lắc

- **Bước 3 (khác với trên):** Lần này đề hỏi **độ lệch chu kỳ thực so với $2\pi\sqrt{l/g}$** — đại lượng này **không tồn tại** ở xấp xỉ bậc 1 (vì bậc 1 chính là định nghĩa ra $2\pi\sqrt{l/g}$, không có "độ lệch" nào cả). Phải giữ đến bậc 3: $\sin\theta \approx \theta - \theta^3/6$.
- **Bước 5:** $\ddot\theta = -\dfrac{g}{l}\left(\theta - \dfrac{\theta^3}{6}\right)$ — phương trình Duffing, xử lý bằng phương pháp nhiễu loạn (perturbation theory — biến thiên tham số/phương pháp Poincaré–Lindstedt), cho ra kết quả kinh điển:
$$T \approx 2\pi\sqrt{\frac{l}{g}}\left(1 + \frac{\theta_0^2}{16} + \cdots\right)$$
- **Đây chính là minh chứng sống động cho nguyên tắc ở Bước 3:** chọn sai bậc (dừng ở bậc 1) sẽ khiến bạn **không thể trả lời được câu hỏi của đề bài**, dù "có vẻ" đã áp dụng đúng công cụ Taylor.

---

## PHẦN 7: CÁC BẪY THƯỜNG GẶP (Pitfalls) — đọc kỹ trước khi đi thi

1. **Dừng Taylor ở bậc làm triệt tiêu đúng hiện tượng cần tìm.** Đây là lỗi nghiêm trọng nhất (xem ví dụ 6.2). Luôn tự hỏi: "Số hạng tôi vừa bỏ đi có phải chính là cái đề đang hỏi không?"

2. **Nhầm "biến nhỏ về giá trị tuyệt đối" với "biến nhỏ không thứ nguyên".** $x$ có thể "nhỏ" tính bằng mét nhưng không hề nhỏ nếu so với độ dài đặc trưng $L$ của bài toán. Luôn chuẩn hóa: tìm tỉ số không thứ nguyên trước khi khai triển.

3. **Khai triển không đồng bộ bậc giữa các đại lượng trong cùng một phương trình.** (Đã nói ở Phần 4.4.)

4. **Chọn sai điểm khai triển $a$** — ví dụ khai triển quanh $\theta=0$ cho một con lắc đang dao động quanh một vị trí lệch $\theta = \theta^*$ do có thêm lực ngoài không đổi — phải khai triển quanh VTCB **mới** $\theta^*$ (nghiệm của $U'(\theta^*)=0$), không phải quanh 0.

5. **Dùng miền hội tụ sai.** Ví dụ áp dụng $\ln(1+x) \approx x$ khi $x \to 1$ (biên của miền hội tụ, sai số lớn) thay vì $x \ll 1$ thực sự.

6. **Quên kiểm tra tính tự hợp ở Bước 7.** Rất nhiều bài thi có "bẫy ngầm": giải ra nghiệm nhưng nghiệm đó vi phạm chính giả thiết $\varepsilon \ll 1$ ban đầu — khi đó phải quay lại và nhận định rằng xấp xỉ tuyến tính **không áp dụng được** trong chế độ đó (cần công cụ khác, hoặc bài yêu cầu bạn *chỉ ra* sự vi phạm này như một phần của đáp án).

7. **Nhầm lẫn giữa chuỗi Taylor và chuỗi Fourier/các loại khai triển khác.** Taylor là xấp xỉ **địa phương** (local, quanh một điểm); nếu bài yêu cầu biểu diễn một hàm tuần hoàn trên toàn miền (không phải lân cận một điểm), đó là bài toán Fourier, không phải Taylor — **chọn sai công cụ chính là chọn sai "ℓ" trong (ℓ, CHỖ)**.

---

## PHẦN 8: CHECKLIST NHANH TRƯỚC KHI NỘP BÀI

- [ ] Tôi đã nêu rõ biến nhỏ không thứ nguyên $\varepsilon$ là gì.
- [ ] Tôi đã chỉ ra/biện minh điểm khai triển $a$.
- [ ] Tôi đã kiểm tra: ở $a$, nếu là cân bằng, thì $f'(a) = 0$.
- [ ] Tôi giữ đủ bậc để đại lượng cần tìm **không bị triệt tiêu**.
- [ ] Mọi đại lượng trong phương trình được khai triển **cùng bậc**.
- [ ] Tôi đã kiểm tra thứ nguyên của từng số hạng.
- [ ] Tôi đã kiểm tra đối xứng (bậc lẻ/chẵn có hợp lý không).
- [ ] Nghiệm cuối cùng tự hợp với giả thiết $\varepsilon \ll 1$.
- [ ] Khi $\varepsilon \to 0$, kết quả trở về đúng giới hạn cổ điển/lý tưởng đã biết.
- [ ] (Nếu đề yêu cầu) tôi đã nêu được bậc sai số $R_n = O(\varepsilon^{n+1})$.

---

## PHẦN 9: BÀI TẬP LUYỆN TẬP (tự làm, kiểm tra bằng checklist trên)

1. Một quả cầu tích điện $q$ dao động nhỏ quanh tâm một vòng dây tròn bán kính $R$ tích điện đều $Q$, dọc theo trục vòng dây. Tìm $\varepsilon$, điểm khai triển $a$, và tần số dao động nhỏ $\omega$. *(Gợi ý: thế năng trên trục vòng dây là hàm chẵn theo khoảng cách $z$ từ tâm — hãy kiểm tra xem số hạng bậc nhất có tự động triệt tiêu không, và vì sao.)*

2. Một hạt chuyển động với $v \ll c$ chịu một lực không đổi $F$. So sánh động năng cổ điển $\frac{1}{2}mv^2$ với động năng tương đối tính chính xác đến bậc $v^4/c^2$. Tại tốc độ nào thì hiệu chỉnh tương đối tính chiếm 1% động năng cổ điển?

3. Con lắc lò xo có thế năng $U(x) = \frac{1}{2}kx^2 + \lambda x^4$ ($\lambda$ nhỏ). Dùng Taylor/nhiễu loạn để tìm hiệu chỉnh bậc nhất của tần số dao động theo biên độ $A$. So sánh cấu trúc bài toán này với bài tập 6.2 (con lắc đơn) — chúng có cùng "cấu trúc toán học ẩn" không? (Liên hệ với mục "Cấu trúc chặt chẽ giữa Vật Lý và Toán Học" trong tài liệu gốc của bạn.)

4. Hai điện tích $+q$ và $-q$ đặt cách nhau $d$ (lưỡng cực). Dùng khai triển nhị thức tổng quát để suy ra điện thế gần đúng tại điểm cách tâm lưỡng cực $r \gg d$, góc $\theta$ so với trục lưỡng cực. Chỉ rõ bậc nào của $d/r$ cho ra số hạng lưỡng cực, bậc nào tiếp theo cho ra số hạng tứ cực (quadrupole) — và vì sao các bậc "chẵn/lẻ" ở đây có liên hệ với tính đối xứng/phản đối xứng của cấu hình điện tích.

---

## LỜI KẾT (nối lại với tư duy tổng quát)

Taylor/Maclaurin không phải là "một chiêu tính gần đúng" để nhớ máy móc — nó là hiện thân cụ thể của chính triết lý mà bạn đang xây dựng trong tài liệu gốc: **mọi công cụ (ℓ) đều có Pre/Suf/Post/Err rõ ràng, và việc tìm đúng "CHỖ" áp dụng (ở đây là: đúng biến nhỏ, đúng điểm khai triển, đúng bậc) quan trọng hơn việc "biết công thức"**. Một học sinh thuộc bảng khai triển Maclaurin nhưng không biết tại sao phải giữ đến bậc 3 trong bài 6.2 sẽ thất bại trước một học sinh chỉ nhớ công thức $\sin x \approx x$ nhưng hiểu sâu **vì sao, khi nào, và đến bậc nào**.

**Hãy tự tay làm lại toàn bộ Phần 6 và 4 bài tập Phần 9 trên giấy trắng, không nhìn tài liệu, trước khi coi là đã hiểu — đúng tinh thần Phần 1.1 trong tài liệu gốc của bạn.**
