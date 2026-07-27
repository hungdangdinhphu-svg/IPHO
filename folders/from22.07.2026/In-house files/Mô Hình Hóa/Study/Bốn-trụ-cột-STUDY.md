# TÀI LIỆU BỔ TRỢ
## Bộ công cụ toán học cần thiết để đọc hiểu whitepaper *"Bốn Trụ Cột: Khung Hình Thức Hoá Chặt Chẽ..."*

---

## Lời nói đầu (dành cho giáo viên)

Whitepaper gốc **không phải** một tài liệu vật lý — nó là một tài liệu **toán học viết bằng ký hiệu đại học/sau đại học** (tập hợp, đạo hàm riêng, ma trận, dạng vi phân, lý thuyết nhóm, cơ học Lagrange, giải tích thứ nguyên, trị riêng) áp dụng vào vật lý Olympiad. Học sinh lớp 9 hoàn toàn có thể hiểu **bản chất** của mọi công cụ này — chỉ là các em chưa từng gặp *ký hiệu* đó. Vấn đề không phải là "quá khó để hiểu", mà là "chưa được phiên dịch".

Tài liệu này làm đúng một việc: xây, **từ dưới lên**, từng viên gạch toán học mà bài viết gốc giả định người đọc đã có sẵn — bắt đầu từ những gì lớp 9 chắc chắn đã biết (hệ trục Oxy, giải hệ phương trình, hàm số, lượng giác trong tam giác vuông), rồi mở rộng dần sang các khái niệm mới, mỗi bước chỉ dùng lại bước trước.

Tài liệu **không** giảng lại nội dung 4 trụ cột (DOF, Ràng buộc, Đối xứng, Xấp xỉ) — vì bài gốc đã tự làm việc đó rất kỹ, có định nghĩa, có chứng minh, có ví dụ số kiểm chứng. Tài liệu này chỉ giảng **ngôn ngữ** mà bài gốc dùng để nói.

**Cách dùng:** Học theo đúng thứ tự Module 1 → 11. Mỗi module có mục "Dùng ở đâu trong tài liệu gốc" — chỉ thẳng ra công thức/định nghĩa nào trong bài whitepaper sẽ trở nên đọc được sau khi học xong module đó. Cuối mỗi module có một "Kiểm tra nhanh" — học sinh tự làm được thì mới sang module tiếp theo. Cuối tài liệu là **Bản đồ ký hiệu** — tra cứu nhanh mọi ký hiệu lạ xuất hiện trong bài gốc.

---

## Bản đồ tổng thể

| Phần trong tài liệu gốc | Cần công cụ nào mà lớp 9 chưa học | Học ở Module |
|---|---|---|
| Phần 0 (định nghĩa "Tổng quát", "Case-by-case") | Ngôn ngữ tập hợp, mệnh đề "với mọi/tồn tại", "khi và chỉ khi" | 1 |
| Phần 0–2 ($\mathbb R^N$, toạ độ thô) | Không gian nhiều chiều | 2 |
| Mọi nơi có $\partial L/\partial x$ | Hàm nhiều biến, đạo hàm riêng | 3 |
| Định lý A (hạng Jacobi) | Vectơ, ma trận, hạng ma trận, Định lý Hàm ẩn | 4 |
| Mục 2.3 ($SO(2), SO(3)$) | Ma trận quay, khái niệm nhóm | 5 |
| Định lý B (Frobenius, $\omega\wedge d\omega$) | Vi phân, dạng vi phân, tích ngoài | 6 |
| Định lý C1 (Noether), Euler–Lagrange | Cơ học Lagrange | 7 |
| Chứng minh (c) Phần 4.2 | Tích có hướng, hoán vị vòng | 8 |
| Định lý D1 (Buckingham) | Phân tích thứ nguyên | 9 |
| Định lý D2, D3 | Khai triển tiệm cận, trị riêng ma trận | 10 |

---

## MODULE 1 — Ngôn ngữ hình thức: tập hợp, "với mọi/tồn tại", "khi và chỉ khi"

### 1.1 Tập hợp và ký hiệu $\in$

Một **tập hợp** chỉ là một "cái túi" chứa các đối tượng. Lớp 9 đã quen với tập hợp số ($\mathbb N,\mathbb Z,\mathbb Q$...). Whitepaper mở rộng ý tưởng này: $\mathcal P$ không phải một túi chứa *số*, mà là một túi chứa **bài toán**. Viết $p \in \mathcal P$ nghĩa là "bài toán $p$ nằm trong túi $\mathcal P$" — hệt như $3 \in \mathbb N$ nghĩa là "3 nằm trong tập số tự nhiên". Không có gì bí ẩn: chỉ là đối tượng trong túi đổi từ "số" thành "bài toán".

### 1.2 "Với mọi" ($\forall$) và "tồn tại" ($\exists$)

Đây là hai từ các em đã dùng bằng lời mà không biết mặt ký hiệu:

- "**Mọi** số chẵn đều chia hết cho 2" — ký hiệu: $\forall n$ chẵn, $n \,\vdots\, 2$.
- "**Có tồn tại** một số nguyên tố chẵn" (đó là số 2) — ký hiệu: $\exists n$ nguyên tố, $n$ chẵn.

Điểm mấu chốt cần nắm chắc (vì cả whitepaper xoay quanh phân biệt này): một khẳng định dạng "$\forall p, \mathcal M$ đúng" là một lời hứa **rất mạnh** — chỉ cần **một** phản ví dụ là sụp đổ toàn bộ. Đây chính xác là cấu trúc của Mệnh đề 0: để bác bỏ "tồn tại một phương pháp đúng cho *mọi* bài toán", ta chỉ cần chỉ ra rằng không thể có một mô tả cố định hoạt động cho *mọi* trường hợp — không cần duyệt hết vô hạn bài toán.

### 1.3 Điều kiện cần, điều kiện đủ, "khi và chỉ khi"

Ba khái niệm này lớp 9 đã dùng ngầm khi học "định lý đảo":

- "Nếu $A$ thì $B$" ($A\Rightarrow B$): $A$ là **điều kiện đủ** cho $B$, $B$ là **điều kiện cần** cho $A$.
- Ví dụ quen thuộc: "Nếu một tứ giác là hình vuông thì nó là hình thoi" — đúng một chiều, chưa chắc đúng chiều ngược ($A\Rightarrow B$ nhưng $B\not\Rightarrow A$).
- "**Khi và chỉ khi**" ($A \Leftrightarrow B$) là khi *cả hai chiều* đều đúng: "Một tam giác là đều **khi và chỉ khi** cả ba góc bằng nhau."

Định lý B trong bài gốc có dạng chính xác này: "ràng buộc là toàn chỉnh **khi và chỉ khi** $\omega\wedge d\omega=0$" — nghĩa là phép kiểm tra đó vừa đủ, vừa cần: hễ đúng công thức thì chắc chắn toàn chỉnh, và hễ toàn chỉnh thì chắc chắn công thức đúng. Không có "trường hợp ngoại lệ" nào cần lo — đó là lý do bài gốc gọi phép kiểm tra này là "thuật toán tuyệt đối".

### 1.4 "Thuật toán" (algorithm) đối lập với "case-by-case"

Đây là khái niệm cốt lõi nhất — mọi bảng phân loại [G]/[G$_k$]/[C] trong bài gốc chỉ là ứng dụng ý này lặp đi lặp lại:

- Một **thuật toán** là một quy trình cố định, viết ra một lần, áp dụng máy móc cho mọi đầu vào — giống công thức nghiệm phương trình bậc hai $x=\dfrac{-b\pm\sqrt{b^2-4ac}}{2a}$: không cần "cảm nhận" gì, cứ thay số vào là ra đáp số, đúng cho *mọi* phương trình bậc hai.
- **Case-by-case** là khi không có công thức cố định — phải trước tiên "nhận diện xem bài này giống dạng nào đã gặp", rồi mới biết dùng cách nào — giống việc giải phương trình vô tỉ: không có một công thức chung, phải nhận ra "kiểu" của nó (đặt ẩn phụ, nhân liên hợp, hay dùng bất đẳng thức) rồi mới chọn đường.
- **Ký hiệu $\blacksquare$** cuối một đoạn chỉ đơn giản là "kết thúc chứng minh" — quy ước quốc tế, không mang nghĩa toán học gì thêm.

**Kiểm tra nhanh:** Phát biểu "Với mọi hình chữ nhật, hai đường chéo bằng nhau" — đây là khẳng định $\forall$ hay $\exists$? Nó là điều kiện cần hay đủ để một tứ giác là hình chữ nhật? *(Đáp: $\forall$; đây chỉ là điều kiện cần — hình thang cân cũng có 2 đường chéo bằng nhau, nên không đủ để suy ngược ra hình chữ nhật.)*

---

## MODULE 2 — Từ Oxy, Oxyz đến không gian $N$ chiều

### 2.1 Ôn: một điểm cần bao nhiêu số để xác định?

- Trên **một đường thẳng**: 1 số (toạ độ $x$).
- Trên **mặt phẳng Oxy**: 2 số $(x,y)$.
- Trong **không gian Oxyz**: 3 số $(x,y,z)$.

Nhận ra quy luật: số lượng con số cần dùng = **số bậc tự do định vị** của điểm đó trong không gian đang xét. Đây chính là con số $N$ trong bài gốc.

### 2.2 Mở rộng: không cần "nhìn thấy" để làm việc

Câu hỏi tự nhiên: "không gian 5 chiều trông như thế nào?" — câu trả lời trung thực: **không cần hình dung ra hình ảnh**, chỉ cần coi một "điểm trong không gian $N$ chiều" là một **danh sách có thứ tự gồm $N$ số**: $x = (x^1, x^2, \dots, x^N)$. Đại số hoàn toàn làm việc bình thường dù không vẽ được — giống hệt cách các em đã quen giải hệ 4 ẩn, 5 ẩn mà không cần "hình dung" ra một hình học 4 chiều.

Ví dụ cụ thể: muốn mô tả đầy đủ trạng thái của **hai** chất điểm trong mặt phẳng, cần $2+2=4$ số $(x_1,y_1,x_2,y_2)$ — đây là một điểm trong $\mathbb R^4$. Không có gì huyền bí, chỉ là *đếm* — và whitepaper gọi $N$ này là "toạ độ thô".

### 2.3 Vì sao gọi là "thô" (raw)?

Vì đây là *tất cả* các số cần để định vị vật, **trước khi** trừ đi các ràng buộc (dây nối, khớp bản lề...). Bước "trừ ràng buộc" là nội dung của Module 4.

**Dùng ở đâu trong tài liệu gốc:** Định nghĩa 0.1 ($I(p)$ chứa $N$), toàn bộ Phần 2 (Trụ cột A).

**Kiểm tra nhanh:** Ba chất điểm chuyển động tự do trong không gian 3D (không ràng buộc gì) — $N$ tổng cộng là bao nhiêu? *(Đáp: $3\times 3=9$.)*

---

## MODULE 3 — Hàm nhiều biến và đạo hàm riêng

### 3.1 Ôn hàm một biến

Lớp 9 đã quen $y=f(x)$: cho một số $x$, hàm trả về một số $y$. Ví dụ $S(x) = x^2$ (diện tích hình vuông cạnh $x$).

### 3.2 Hàm nhiều biến — không có gì mới ngoài việc "vào" nhiều hơn

$f(x,y) = xy$ (diện tích hình chữ nhật cạnh $x,y$) là một hàm **hai biến**: đưa vào hai số, nhận lại một số. Whitepaper viết $L(q,\dot q, t)$ nghĩa hệt vậy — chỉ là hàm này nhận vào **nhiều đầu vào** (toạ độ, vận tốc, thời gian) và trả ra một số.

### 3.3 Đạo hàm — ôn lại từ "tốc độ thay đổi"

Trước khi có đạo hàm riêng, cần chắc trực giác đạo hàm một biến (ngay cả khi lớp 9 chưa học chính thức, đây là ý tưởng vật lý các em đã quen: **vận tốc** chính là tốc độ thay đổi *tức thời* của vị trí theo thời gian). Nếu $x(t)$ là vị trí tại thời điểm $t$, độ dốc trung bình trên một khoảng rất ngắn $\Delta t$ là $\dfrac{\Delta x}{\Delta t}$; khi $\Delta t$ nhỏ dần đến mức "tức thời", ta gọi tỉ số đó là **đạo hàm**, ký hiệu $\dot x$ hoặc $\dfrac{dx}{dt}$. Bài gốc dùng đúng ký hiệu chấm ở trên ($\dot q$, $\dot x$, $\dot\theta$...) để chỉ "tốc độ thay đổi theo thời gian" — không có gì khác vận tốc mà các em đã biết, chỉ tổng quát hoá cho *bất kỳ* đại lượng nào, không riêng vị trí.

Một vài công thức đạo hàm cơ bản cần nhớ như bảng tra (không cần chứng minh, chỉ cần dùng đúng):

| Hàm | Đạo hàm |
|---|---|
| $x^n$ | $n x^{n-1}$ |
| hằng số $c$ | $0$ |
| $\sin\theta$ | $\cos\theta$ |
| $\cos\theta$ | $-\sin\theta$ |

### 3.4 Đạo hàm riêng — "giữ các biến khác đứng yên"

Với hàm nhiều biến $f(x,y)=xy$, câu hỏi "tốc độ thay đổi" trở nên mơ hồ: thay đổi theo $x$ hay theo $y$? **Đạo hàm riêng** giải quyết chính xác việc này: $\dfrac{\partial f}{\partial x}$ nghĩa là "đạo hàm theo $x$, coi $y$ như một *hằng số* tạm thời". Ký hiệu $\partial$ (đọc là "del", khác chữ $d$ thường) chỉ để **nhắc** rằng đây là đạo hàm trong bối cảnh nhiều biến, còn cách tính giống hệt đạo hàm một biến đã ôn ở 3.3.

**Ví dụ tính tay:** $f(x,y) = x^2y + 3y$.
$$\frac{\partial f}{\partial x} = 2xy \quad (\text{coi } y \text{ là hằng số, đạo hàm } x^2 \text{ ra } 2x)$$
$$\frac{\partial f}{\partial y} = x^2 + 3 \quad (\text{coi } x \text{ là hằng số, đạo hàm } y \text{ ra } 1)$$

Mọi biểu thức $\partial L/\partial q^i$, $\partial g_j/\partial x$ trong bài gốc được tính đúng theo quy tắc này — không hơn.

**Dùng ở đâu trong tài liệu gốc:** khắp Định lý A, C1, C2 (bất cứ đâu có $\partial$).

**Kiểm tra nhanh:** Cho $f(x,y)=3x^2+2xy-y^3$. Tính $\partial f/\partial x$ và $\partial f/\partial y$ tại $(x,y)=(1,2)$. *(Đáp: $\partial f/\partial x = 6x+2y = 10$; $\partial f/\partial y = 2x-3y^2 = 2-12=-10$.)*

---

## MODULE 4 — Vectơ, ma trận, hạng ma trận, và Định lý Hàm ẩn

### 4.1 Vectơ — chỉ là một danh sách số có thứ tự

Một vectơ trong $\mathbb R^2$ như $(3,4)$ có thể hình dung là mũi tên từ gốc toạ độ đến điểm $(3,4)$ — độ dài $\sqrt{3^2+4^2}=5$ (Pythagoras quen thuộc). Trong không gian nhiều chiều hơn, vectơ vẫn chỉ là danh sách số $(x^1,\dots,x^N)$ — độ dài tổng quát hoá tự nhiên: $\sqrt{(x^1)^2+\dots+(x^N)^2}$.

### 4.2 Từ giải hệ phương trình đến khái niệm "ma trận"

Lớp 9 đã giải quen hệ 2 phương trình 2 ẩn, ví dụ:
$$x+y=2,\qquad x-y=0.$$
Bảng các hệ số đứng trước ẩn số:
$$
\begin{pmatrix}1 & 1\\ 1 & -1\end{pmatrix}
$$
chính là một **ma trận** — chỉ là cách viết gọn các hệ số thành bảng. Không có phép toán mới nào cần học ở đây ngoài việc *nhìn* hệ phương trình quen thuộc dưới dạng bảng.

### 4.3 "Hạng" ma trận — đếm số phương trình *thực sự* độc lập

Xét hai hệ sau:

**Hệ 1** (2 ẩn, 2 phương trình, nhưng phương trình 2 chỉ là phương trình 1 nhân đôi):
$$x+y=2,\qquad 2x+2y=4.$$
Đây thực chất chỉ là **một** thông tin duy nhất — vô số nghiệm nằm trên một đường thẳng.

**Hệ 2:**
$$x+y=2,\qquad x-y=0.$$
Hai phương trình *thực sự khác nhau* — cho đúng một điểm nghiệm duy nhất.

Ta nói Hệ 1 có **hạng 1** (dù viết ra 2 phương trình, chỉ có 1 cái "có tác dụng" thật), còn Hệ 2 có **hạng 2** (đầy đủ, không dư thừa). Đây chính xác là ý nghĩa của "hạng ma trận Jacobi $=k$" trong Định lý A: nếu học sinh viết ra $k$ phương trình ràng buộc nhưng chúng không thực sự độc lập (một cái suy ra được từ những cái còn lại), số bậc tự do bị đếm sai.

Cách kiểm tra hạng bằng tay ở mức lớp 9 hoàn toàn khả thi: thử xem có phương trình nào là **tổ hợp** (cộng/trừ/nhân hệ số) của các phương trình còn lại hay không.

### 4.4 Ma trận Jacobi — chỉ là "bảng đạo hàm riêng"

Nếu có $k$ hàm ràng buộc $g_1,\dots,g_k$ theo $N$ biến, **ma trận Jacobi** chỉ là bảng gồm mọi đạo hàm riêng có thể:
$$
\frac{\partial(g_1,\dots,g_k)}{\partial x} =
\begin{pmatrix}
\partial g_1/\partial x^1 & \cdots & \partial g_1/\partial x^N\\
\vdots & & \vdots\\
\partial g_k/\partial x^1 & \cdots & \partial g_k/\partial x^N
\end{pmatrix}.
$$
"Hạng đầy đủ $=k$" (điều kiện trong Định lý A) nghĩa đúng như Mục 4.3: $k$ ràng buộc đó thực sự độc lập tại điểm đang xét, không cái nào dư thừa.

### 4.5 Định lý Hàm ẩn — trực giác qua đường tròn

Xét ràng buộc quen thuộc: $g(x,y) = x^2+y^2-r^2=0$ (phương trình đường tròn). Đây là **1 phương trình** trong **2 ẩn** — Định lý A tiên đoán còn lại $2-1=1$ chiều tự do: đúng vậy, đường tròn là một đường cong 1 chiều (đi dọc nó chỉ cần 1 con số, ví dụ góc $\theta$).

Tính đạo hàm riêng: $\partial g/\partial x = 2x$, $\partial g/\partial y=2y$. Tại điểm bất kỳ trên đường tròn **trừ** hai điểm $(0,\pm r)$ (nơi $\partial g/\partial y=0$), ta có $\partial g/\partial y \ne 0$ — nghĩa là *gần điểm đó*, có thể giải ngược ra $y$ theo $x$: $y=\pm\sqrt{r^2-x^2}$. Đây chính là nội dung Định lý Hàm ẩn: **hễ đạo hàm riêng theo một biến khác 0 tại một điểm, thì gần điểm đó, có thể "giải" biến ấy như một hàm trơn của các biến còn lại**. Whitepaper dùng đúng lập luận này (mở rộng cho $k$ phương trình, $N$ biến) để chứng minh Định lý A ở Mục 2.2.

**Dùng ở đâu trong tài liệu gốc:** Định lý A và toàn bộ chứng minh của nó (Mục 2.2), Mục 2.3 (tính DOF vật rắn qua $SO(2),SO(3)$).

**Kiểm tra nhanh:** Với ràng buộc $g(x,y)=x^2-y=0$ (parabol), tính $\partial g/\partial x$ và $\partial g/\partial y$. Tại điểm nào thì *không* giải được $y$ theo $x$ bằng Định lý Hàm ẩn theo biến $y$? *(Đáp: $\partial g/\partial x=2x,\ \partial g/\partial y=-1$ — luôn khác 0, nên luôn giải được $y=x^2$ ở mọi điểm, không có điểm suy biến.)*

---

## MODULE 5 — Ma trận quay, và khái niệm "nhóm"

### 5.1 Quay một điểm quanh gốc toạ độ

Lớp 9 đã biết $\sin,\cos$ trong tam giác vuông. Mở rộng tự nhiên: nếu quay điểm $(x,y)$ quanh gốc toạ độ một góc $\theta$, điểm mới $(x',y')$ tính theo công thức:
$$x' = x\cos\theta - y\sin\theta,\qquad y'=x\sin\theta+y\cos\theta.$$
Viết dưới dạng ma trận (chỉ là gọn hoá hai công thức trên thành một bảng):
$$
\begin{pmatrix}x'\\y'\end{pmatrix} = R(\theta)\begin{pmatrix}x\\y\end{pmatrix},\qquad R(\theta)=\begin{pmatrix}\cos\theta & -\sin\theta\\ \sin\theta&\cos\theta\end{pmatrix}.
$$
Đây là **ma trận quay 2D**, và tập hợp mọi ma trận như vậy (ứng với mọi góc $\theta$) được gọi là $SO(2)$.

### 5.2 Vì sao $R^\top R = I$?

Phép quay không làm thay đổi độ dài của bất kỳ vectơ nào (quay một mũi tên không kéo dài hay rút ngắn nó — trực giác hình học thuần tuý). Điều kiện đại số diễn đạt đúng sự thật hình học "bảo toàn độ dài mọi vectơ" chính là $R^\top R = I$ ($R^\top$ là ma trận chuyển vị — đổi hàng thành cột; $I$ là ma trận đơn vị, tương đương số 1 trong phép nhân). Có thể kiểm chứng trực tiếp bằng tay với $R(\theta)$ ở trên, dùng đúng công thức $\sin^2\theta+\cos^2\theta=1$ đã học.

### 5.3 "Nhóm" là gì?

Một **nhóm** là một tập hợp các phép biến đổi thoả ba điều rất tự nhiên: (i) làm liên tiếp hai phép biến đổi trong tập vẫn cho ra một phép biến đổi trong tập ("đóng kín" — quay $\theta_1$ rồi quay $\theta_2$ = quay $\theta_1+\theta_2$, vẫn là một phép quay), (ii) có phép "không làm gì" (quay góc $0$), (iii) mọi phép đều "undo được" (quay ngược lại góc $-\theta$). Tập mọi phép quay 2D thoả cả ba — đó là lý do gọi $SO(2)$ là một nhóm. $SO(3)$ (phép quay 3D) cũng vậy, chỉ thay ma trận $2\times2$ bằng $3\times3$.

**Dùng ở đâu trong tài liệu gốc:** Mục 2.3 (đếm DOF vật rắn qua $SO(2), SO(3)$ — hướng của vật rắn *chính là* một điểm trong nhóm quay, và ràng buộc $R^\top R=I$ chính là ràng buộc "hướng" phải thoả).

**Kiểm tra nhanh:** Vì sao $R(0)$ (quay góc $0$) bằng ma trận đơn vị $I$? *(Đáp: thay $\theta=0$: $\cos 0=1,\sin 0=0$, cho đúng $\begin{pmatrix}1&0\\0&1\end{pmatrix}=I$ — "quay 0 độ" nghĩa là giữ nguyên, đúng logic.)*

---

## MODULE 6 — Vi phân, dạng vi phân, tích ngoài, và trực giác Định lý Frobenius

Đây là module khó nhất trong toàn bộ tài liệu bổ trợ này, vì nó dùng công cụ thuộc về **hình học vi phân** — bình thường chỉ dạy ở đại học. Ta xây thật chậm, từng bước một, bằng hình ảnh cụ thể.

### 6.1 $dx$ là gì?

Các em đã quen $\Delta x$ = "một khoảng thay đổi của $x$" (ví dụ trong công thức tính độ dốc trung bình). Ký hiệu $dx$ chỉ là **phiên bản cực nhỏ, tức thời** của $\Delta x$ — một "bước đi rất bé" theo trục $x$. Không cần hiểu "bé đến mức nào" một cách chặt chẽ (đó là việc của giải tích đại học) — chỉ cần hiểu $dx$ như một **bước dịch chuyển rất nhỏ, có thể dương hoặc âm**, y hệt cách các em tưởng tượng "nhích một chút theo trục $x$".

### 6.2 Dạng vi phân bậc 1 — một "luật kiểm tra hướng đi"

Xét biểu thức $\omega = A\,dx + B\,dy$ (với $A,B$ có thể là số hoặc hàm của $x,y$). Đây gọi là **dạng vi phân bậc 1**. Cách đọc đúng nhất cho học sinh: $\omega$ là một **cái máy kiểm tra** — đưa vào một bước đi rất nhỏ $(dx,dy)$ theo bất kỳ hướng nào, máy trả lại một con số $A\,dx+B\,dy$.

Ví dụ vật lý ngay trong bài gốc: đĩa lăn không trượt có $\dot x = R\dot\theta$, viết lại dưới dạng vi phân: $dx - R\,d\theta = 0$. Đây là "luật": *bước đi rất nhỏ $(dx,d\theta)$ chỉ được phép nếu $dx=R\,d\theta$* — đúng nghĩa vật lý "lăn không trượt": xoay một chút thì phải lăn đúng một chút tương ứng, không hơn không kém.

### 6.3 Tích ngoài $\wedge$ — đo "diện tích có hướng"

Đây là bước mới nhất. Lớp 9 đã biết công thức diện tích tam giác qua toạ độ (hoặc ít nhất, biết định thức $2\times 2$ liên quan đến diện tích hình bình hành dựng bởi hai vectơ $(a,b)$ và $(c,d)$: diện tích $=ad-bc$, có thể âm nếu tính "có hướng"). Định nghĩa:
$$dx\wedge dy := \text{"máy đo diện tích có hướng của hình bình hành dựng bởi hai bước đi nhỏ"}.$$
Vì diện tích có hướng đổi dấu khi đổi chỗ hai cạnh ($ad-bc = -(cb-da)$... tổng quát, đổi thứ tự hai vectơ đảo dấu diện tích có hướng), ta có tính chất nền tảng:
$$dx\wedge dy = -\,dy\wedge dx, \qquad dx\wedge dx = 0$$
(diện tích của một "hình bình hành" dựng từ một vectơ với chính nó thì bằng 0 — hai cạnh trùng nhau). Hai quy tắc này là **toàn bộ những gì cần nhớ để tính tay** — không cần biết gì thêm về hình học vi phân. Mở rộng lên 3 biến: $dx\wedge dy\wedge d\theta$ đo "thể tích có hướng" của 3 bước đi nhỏ, với cùng quy tắc đổi dấu khi hoán đổi hai ký hiệu bất kỳ.

**Ví dụ tính tay** (đúng phép tính whitepaper dùng ở Ví dụ kiểm chứng B.2): cho $\omega = -\sin\theta\,dx+\cos\theta\,dy$ và
$$d\omega = -\cos\theta\,d\theta\wedge dx - \sin\theta\,d\theta\wedge dy.$$
Nhân $\omega\wedge d\omega$, dùng quy tắc phân phối (như nhân đa thức bình thường) rồi áp hai quy tắc ở trên để rút gọn — mọi số hạng có $dx\wedge dx$ hay $dy\wedge dy$ triệt tiêu, chỉ còn lại số hạng chứa đủ ba ký hiệu khác nhau $dx,dy,d\theta$, sắp theo đúng thứ tự thành $dx\wedge dy\wedge d\theta$ (đổi dấu mỗi lần hoán đổi hai ký hiệu liền kề). Đây thuần túy là "nhân đa thức có quy tắc dấu đặc biệt" — kỹ năng đại số các em đã có, chỉ thêm hai luật ở trên.

### 6.4 $d\omega$ là gì? — "độ xoáy" của luật hướng đi

Nếu $\omega = A(x,y)\,dx+B(x,y)\,dy$ với $A,B$ *thay đổi* theo vị trí, định nghĩa:
$$d\omega := \left(\frac{\partial B}{\partial x}-\frac{\partial A}{\partial y}\right)dx\wedge dy.$$
Công thức này đo mức độ luật "hướng cho phép" **xoay/xoắn** khi đi từ điểm này sang điểm khác (đúng khái niệm vật lý gọi là "độ xoáy"/curl mà nhiều em sẽ gặp lại ở đại học). Nếu $A,B$ là hằng số (không đổi theo vị trí, như Ví dụ B.1: $\omega=dx-R\,d\theta$, $R$ là hằng số bán kính) thì mọi đạo hàm riêng $=0$, nên $d\omega=0$ ngay lập tức — "không xoáy gì cả".

### 6.5 Trực giác Định lý Frobenius — đỗ xe song song

Đây là câu hỏi vật lý whitepaper đặt ra: nếu tại **mỗi thời điểm**, hướng đi bị giới hạn chỉ còn một số hướng (ràng buộc $\omega=0$), thì xét về lâu dài, xe có bị "giam" trong một mặt cong cố định (không bao giờ tới được những cấu hình nhất định), hay có thể **len lỏi** tới bất kỳ cấu hình nào?

Trực giác: nếu luật hướng đi *không xoáy* theo đúng nghĩa Mục 6.4 (test $\omega\wedge d\omega=0$), các hướng cho phép tại từng điểm "xếp chồng gọn gàng" thành từng lớp mặt cong lồng vào nhau — giống lớp vỏ củ hành hay đường đồng mức trên bản đồ địa hình: đi mãi trong một hướng cho phép, bạn **luôn ở trên cùng một lớp**, không bao giờ nhảy sang lớp khác. Đó là trường hợp **toàn chỉnh** (Ví dụ B.1: bánh xe lăn thẳng — vị trí và góc quay luôn khoá chặt với nhau qua $x-R\theta=$const, không thể phá vỡ).

Ngược lại, nếu luật hướng đi *có xoáy* ($\omega\wedge d\omega\ne0$), các hướng cho phép tại các điểm lân cận "vặn xoắn" đủ mạnh để, bằng cách nối tiếp nhiều bước đi hợp lệ (dù *mỗi bước* chỉ đi theo hướng bị giới hạn), bạn len lỏi tới **bất kỳ** cấu hình nào — đây chính xác là hiện tượng đỗ xe song song mà whitepaper nêu ở Ví dụ B.2: dù tại mỗi khắc chỉ có 1 hướng lăn cho phép (không trượt ngang), bằng cách đánh lái qua lại (đổi $\theta$ liên tục), xe *vẫn* dịch chuyển ngang được — cấu hình $(x,y,\theta)$ *không* bị giam.

**Dùng ở đâu trong tài liệu gốc:** toàn bộ Định lý B (Phần 3.1), Ví dụ kiểm chứng B.1 và B.2.

**Kiểm tra nhanh:** Với $\omega = dx - R\,d\theta$ ($R$ là hằng số), hãy tự giải thích bằng lời (không cần tính) vì sao $d\omega$ chắc chắn bằng $0$. *(Đáp: hệ số trước $dx$ là $1$ và trước $d\theta$ là $-R$ đều là hằng số, không đổi theo vị trí — mọi đạo hàm riêng trong công thức $d\omega$ đều bằng 0, nên "không có gì để xoáy".)*

---

## MODULE 7 — Cơ học Lagrange: toạ độ suy rộng, hàm $L$, phương trình Euler–Lagrange

### 7.1 Vì sao cần một cách viết mới cho định luật Newton?

Định luật Newton $F=ma$ hoạt động tốt khi biết rõ mọi lực. Nhưng với hệ có ràng buộc phức tạp (nêm trượt trên mặt trơn, con lắc), tính lực ràng buộc (phản lực, lực căng dây...) tốn công không cần thiết. **Cơ học Lagrange** là một cách viết lại đúng cùng một vật lý, nhưng "tự động bỏ qua" các lực ràng buộc, chỉ làm việc trực tiếp trên các bậc tự do thật sự — đúng ý tưởng "toạ độ suy rộng $q$" (đại lượng $f=N-k$ đã đếm ở Module 4).

### 7.2 Hàm Lagrangian $L$

Định nghĩa (chỉ cần nhớ công thức, không cần chứng minh nguồn gốc — bài gốc cũng dùng nó như một công cụ có sẵn):
$$L(q,\dot q,t) := T - V$$
với $T$ là động năng (các em đã biết $T=\tfrac12 mv^2$), $V$ là thế năng (đã biết $V=mgh$ cho trọng trường, hoặc $V=\tfrac12 kx^2$ cho lò xo). Điểm mới duy nhất: bây giờ $T,V$ được viết theo **toạ độ suy rộng** $q$ (một con số đại diện, không nhất thiết là một khoảng cách theo trục Oxy — có thể là một góc, một độ dài dọc theo mặt nêm, v.v.) thay vì toạ độ Oxy thô.

### 7.3 Phương trình Euler–Lagrange

$$\frac{d}{dt}\left(\frac{\partial L}{\partial \dot q}\right) = \frac{\partial L}{\partial q}.$$

Đây là "phương trình chuyển động" — dùng thay cho $F=ma$. Ta kiểm chứng nó cho đúng bằng ví dụ đơn giản nhất có thể: một vật khối lượng $m$ rơi tự do theo trục $x$ (chọn chiều dương xuống dưới), $T=\tfrac12m\dot x^2$, $V=-mgx$ (thế năng giảm khi rơi xuống), nên $L=\tfrac12m\dot x^2+mgx$.

- $\dfrac{\partial L}{\partial \dot x} = m\dot x$ (coi $x$ là hằng, đạo hàm theo $\dot x$).
- $\dfrac{d}{dt}(m\dot x) = m\ddot x$.
- $\dfrac{\partial L}{\partial x} = mg$ (coi $\dot x$ là hằng, đạo hàm theo $x$).

Phương trình Euler–Lagrange cho: $m\ddot x = mg \Rightarrow \ddot x = g$ — **chính xác** định luật rơi tự do đã biết! Đây là bằng chứng bằng tay rằng công thức trừu tượng ở trên tương đương $F=ma$ trong trường hợp đơn giản — đúng những gì bài gốc làm (phức tạp hơn) ở Ví dụ 1, Phần 7.

### 7.4 "Cyclic coordinate" — vì sao thiếu vắng $q$ trong $L$ lại quan trọng

Nếu $L$ **không chứa** $q^1$ một cách tường minh (chỉ chứa $\dot q^1$), thì $\partial L/\partial q^1=0$. Theo phương trình Euler–Lagrange, $\dfrac{d}{dt}\Big(\dfrac{\partial L}{\partial \dot q^1}\Big)=0$ — nghĩa là đại lượng $\partial L/\partial \dot q^1$ **không đổi theo thời gian** (bảo toàn!). Đây chính xác là cơ chế whitepaper dùng ở Mục 4.2(a) — không cần công cụ gì thêm ngoài chính phương trình vừa kiểm chứng ở 7.3.

**Dùng ở đâu trong tài liệu gốc:** Định lý C1 và toàn bộ Phần 4 (chứng minh dựa thẳng trên phương trình Euler–Lagrange này), Bước 6 của Giao thức MAP (Phần 6).

**Kiểm tra nhanh:** Con lắc lò xo nằm ngang, toạ độ $x$ là độ giãn lò xo, $T=\tfrac12m\dot x^2$, $V=\tfrac12kx^2$. Viết $L$, tính $\partial L/\partial \dot x$, $\partial L/\partial x$, và suy ra phương trình chuyển động. *(Đáp: $L=\tfrac12m\dot x^2-\tfrac12kx^2$; $\partial L/\partial\dot x=m\dot x$; $\partial L/\partial x=-kx$; Euler–Lagrange: $m\ddot x=-kx$ — đúng định luật Hooke $F=-kx=ma$.)*

---

## MODULE 8 — Tích vô hướng, tích có hướng, và hoán vị vòng

Cần cho một bước duy nhất trong chứng minh (c) ở Mục 4.2 (bảo toàn mô-men động lượng).

### 8.1 Tích vô hướng (dot product)

Với hai vectơ $\vec a=(a_1,a_2,a_3)$, $\vec b=(b_1,b_2,b_3)$: $\vec a\cdot\vec b = a_1b_1+a_2b_2+a_3b_3$ — một **số**. Tính chất cần dùng: $\vec a\cdot\vec a = |\vec a|^2 \ge 0$, và nếu hai vectơ *bằng nhau*, $\vec a\times\vec a = \vec 0$ (xem 8.2) — vectơ không có "diện tích quét" với chính nó, giống hệt $dx\wedge dx=0$ ở Module 6 (cùng một trực giác: không có gì để tạo diện tích/thể tích từ một hướng lặp lại).

### 8.2 Tích có hướng (cross product)

Với hai vectơ trong không gian 3D, $\vec a\times\vec b$ là một **vectơ mới**, vuông góc với cả $\vec a$ và $\vec b$, độ lớn bằng diện tích hình bình hành do chúng dựng nên. Tính chất cốt lõi cần nhớ (phản đối xứng — cùng bản chất với $\wedge$ ở Module 6!):
$$\vec a\times\vec b = -\vec b\times\vec a, \qquad \vec a\times\vec a=\vec 0.$$

### 8.3 Hoán vị vòng của tích hỗn hợp

Với ba vectơ, biểu thức $\vec a\cdot(\vec b\times\vec c)$ có tính chất "xoay vòng không đổi giá trị":
$$\vec a\cdot(\vec b\times\vec c) = \vec b\cdot(\vec c\times\vec a) = \vec c\cdot(\vec a\times \vec b).$$
(Có thể kiểm chứng bằng cách khai triển toạ độ, nhưng ở mức lớp 9 chỉ cần **ghi nhớ và biết dùng** — bài gốc chỉ dùng tính chất này như một công cụ tính toán, không chứng minh lại.)

**Dùng ở đâu trong tài liệu gốc:** chứng minh (c), Mục 4.2 — dùng đúng ba bước: $\vec r_i\times\vec r_i=0$ (Mục 8.2) và hoán vị vòng (Mục 8.3) để rút gọn biểu thức bảo toàn mô-men động lượng.

**Kiểm tra nhanh:** Vì sao $\vec v\cdot(\vec n\times\vec v)=0$ với $\vec n$ bất kỳ? *(Đáp: theo hoán vị vòng, $\vec v\cdot(\vec n\times\vec v)=\vec n\cdot(\vec v\times\vec v)=\vec n\cdot\vec 0=0$.)*

---

## MODULE 9 — Phân tích thứ nguyên và Định lý Buckingham $\Pi$

### 9.1 Thứ nguyên — ôn lại điều đã biết ngầm

Các em đã luôn kiểm tra "đơn vị có khớp không" khi làm bài tập vật lý (không thể cộng mét với giây). Đó chính là **phân tích thứ nguyên**. Ba thứ nguyên cơ bản hay dùng: khối lượng $M$, chiều dài $L$, thời gian $T$. Ví dụ: vận tốc có thứ nguyên $L/T$, lực có thứ nguyên $M\cdot L/T^2$.

### 9.2 Ví dụ kinh điển: chu kỳ con lắc đơn

Giả sử ta *không biết* công thức chu kỳ con lắc, chỉ biết nó phụ thuộc chiều dài $\ell$ (thứ nguyên $L$), gia tốc trọng trường $g$ (thứ nguyên $L/T^2$), và khối lượng $m$ (thứ nguyên $M$). Ta tìm tổ hợp $\ell^a g^b m^c$ có thứ nguyên đúng bằng thời gian $T$:
$$L^a\cdot(L/T^2)^b\cdot M^c = T^1.$$
So khớp số mũ từng thứ nguyên: $M$: $c=0$; $L$: $a+b=0$; $T$: $-2b=1\Rightarrow b=-\tfrac12, a=\tfrac12$. Vậy chu kỳ phải có dạng $T\propto\sqrt{\ell/g}$ — **không cần giải phương trình vi phân con lắc**, chỉ bằng cách so khớp đơn vị mà suy gần đúng ra dạng công thức đúng (công thức thật $T=2\pi\sqrt{\ell/g}$, sai khác chỉ ở hằng số $2\pi$ không thứ nguyên — đúng như dự đoán, vì hằng số thuần túy luôn "vô hình" với phép phân tích thứ nguyên).

### 9.3 Định lý Buckingham $\Pi$ — tổng quát hoá ví dụ trên

Định lý chỉ nói: nếu có $n$ đại lượng liên quan, dựng từ $k$ thứ nguyên cơ bản, thì bài toán tương đương với việc tìm $p=n-k$ **nhóm không thứ nguyên** (tỉ số/tổ hợp không có đơn vị, giống cách ta chọn $a,b,c$ ở trên để triệt tiêu mọi đơn vị). Đây **cùng một cấu trúc đếm** như Định lý A ở Module 4 ($f=N-k$) — chỉ khác đối tượng đang đếm: ở đây là "bậc tự do trong việc chọn đơn vị", không phải "bậc tự do hình học".

**Dùng ở đâu trong tài liệu gốc:** Định lý D1, Phần 5.2 — lý do "$\varepsilon$ (tham số bé) bắt buộc phải là một nhóm không thứ nguyên $\Pi_i$" chính là vì so sánh "bé/lớn" chỉ có nghĩa với số *không đơn vị* (đúng trực giác các em đã có: không thể nói "5 mét là bé" mà không so nó với một chiều dài khác).

**Kiểm tra nhanh:** Vận tốc rơi cuối cùng của giọt mưa phụ thuộc bán kính $r$ ($L$), khối lượng riêng không khí... giả sử đơn giản hoá chỉ phụ thuộc $g$ ($L/T^2$) và $r$ ($L$) — tổ hợp nào có thứ nguyên vận tốc $L/T$? *(Đáp: thử $v\propto\sqrt{gr}$: thứ nguyên $\sqrt{(L/T^2)\cdot L}=\sqrt{L^2/T^2}=L/T$ — khớp.)*

---

## MODULE 10 — Khai triển tiệm cận và trị riêng ma trận

### 10.1 Khai triển Taylor — ôn qua xấp xỉ đã quen

Các em đã dùng xấp xỉ $\sin\theta\approx\theta$ khi $\theta$ rất nhỏ (tính bằng radian) trong vật lý con lắc. Đó chính là **trường hợp riêng** của khai triển Taylor: mọi hàm trơn có thể viết gần đúng thành chuỗi luỹ thừa của một tham số bé $\varepsilon$:
$$x(\varepsilon) \approx x_0 + \varepsilon x_1 + \varepsilon^2 x_2 + \cdots$$
càng lấy nhiều số hạng càng chính xác; khi $\varepsilon$ rất nhỏ, chỉ cần 1–2 số hạng đầu đã đủ tốt. Định lý D2 trong bài gốc chỉ tổng quát hoá đúng ý tưởng quen thuộc này: thay số vào từng "bậc" $\varepsilon^0,\varepsilon^1,\varepsilon^2,\dots$ rồi giải tuần tự — không có gì mới về bản chất so với $\sin\theta\approx\theta$, chỉ là làm việc này một cách có hệ thống cho *cả một phương trình*, không riêng một hàm số.

### 10.2 Hàm mũ và suy giảm theo thời gian — chuẩn bị cho trị riêng

Phương trình $\dot y = -y/\tau$ (ví dụ: điện áp tụ điện xả qua điện trở) có nghiệm $y(t)=y_0 e^{-t/\tau}$ — đại lượng $y$ giảm dần theo thời gian, và $\tau$ (gọi là "hằng số thời gian") cho biết *tốc độ* giảm: sau thời gian $\tau$, $y$ còn lại khoảng $37\%$ giá trị ban đầu. Đây là kiến thức có thể đã gặp qua ví dụ phóng xạ hoặc mạch RC ở lớp trên — nếu chưa, chỉ cần chấp nhận công thức nghiệm này như một sự thật đã kiểm chứng.

### 10.3 Trị riêng (eigenvalue) — khi có *nhiều* đại lượng cùng biến đổi

Nếu có một **hệ** nhiều đại lượng cùng thay đổi và ảnh hưởng lẫn nhau (ví dụ mạch điện phức tạp với nhiều tụ, nhiều điện trở), phương trình tổng quát có dạng $\dot y = Ay$ với $A$ là một ma trận (bảng hệ số — đã quen ở Module 4) thay vì một số đơn. Sự thật toán học (không cần chứng minh ở mức lớp 9, chỉ cần biết để đọc): luôn tồn tại một số **hướng đặc biệt** trong không gian nhiều chiều đó, sao cho *dọc theo mỗi hướng này*, hệ phức tạp hành xử **y hệt** trường hợp đơn giản 1 đại lượng ở Mục 10.2 — mỗi hướng có "tốc độ suy giảm/tăng trưởng riêng" gọi là **trị riêng** $\lambda_i$, và hằng số thời gian tương ứng là $\tau_i = -1/\lambda_i$ (đây chính xác là công thức whitepaper dùng ở Định lý D3).

Không cần biết cách *tính* trị riêng ở mức này (đó là đại số tuyến tính đại học) — chỉ cần hiểu: **trị riêng là các "phiên bản $\tau$" của một hệ nhiều chiều**, đóng đúng vai trò $RC$ hay $L/R$ mà các em đã quen trong mạch điện đơn giản, mở rộng cho hệ phức tạp hơn.

**Dùng ở đâu trong tài liệu gốc:** Định lý D2 (Phần 5.3), Định lý D3 (Phần 5.4).

**Kiểm tra nhanh:** Với $\dot U=-U/(RC)$, sau bao lâu thì $U$ còn lại khoảng $37\%$ giá trị ban đầu? *(Đáp: sau đúng $t=RC$ — theo định nghĩa hằng số thời gian ở Mục 10.2.)*

---

## MODULE 11 — Tổng kết: đọc tài liệu gốc theo đúng thứ tự

Sau khi hoàn thành 10 module trên, đề nghị đọc tài liệu gốc theo đúng thứ tự viết (Phần 0 → Phần 9), vì bản thân whitepaper cũng được xây "từ dưới lên" — mỗi phần chỉ dùng lại công cụ đã giới thiệu trước đó. Bảng dưới nhắc lại module nào "mở khoá" phần nào, dùng để tra cứu khi bị vướng:

| Đọc đến... | Nếu vướng, quay lại Module |
|---|---|
| Phần 0 (Định nghĩa 0.1–0.3) | 1, 2 |
| Mệnh đề 0 | 1 |
| Phần 2 (Trụ cột A) | 2, 3, 4, 5 |
| Phần 3 (Trụ cột B) | 6 |
| Phần 4 (Trụ cột C) | 3, 7, 8 |
| Phần 5 (Trụ cột D) | 9, 10 |
| Phần 6–9, Phụ lục | không cần công cụ mới — thuần tổng hợp |

---

## BẢN ĐỒ KÝ HIỆU — tra cứu nhanh mọi ký hiệu lạ trong tài liệu gốc

| Ký hiệu | Đọc là | Ý nghĩa ngắn gọn | Module |
|---|---|---|---|
| $\mathcal P$, $p\in\mathcal P$ | "P script", "p thuộc P" | Một tập hợp bài toán; $p$ là một bài toán trong đó | 1 |
| $\forall$, $\exists$ | "với mọi", "tồn tại" | Lượng từ logic | 1 |
| $\Leftrightarrow$ | "khi và chỉ khi" | Đúng cả hai chiều suy luận | 1 |
| $\blacksquare$ | (không đọc) | Kết thúc chứng minh | 1 |
| $\mathbb R^N$ | "R mũ N" | Không gian gồm các danh sách $N$ số thực | 2 |
| $N$, $k$, $f=N-k$ | | Số toạ độ thô, số ràng buộc, số bậc tự do còn lại | 2, 4 |
| $\partial f/\partial x$ | "đen ta f trên đen ta x" (hoặc "del") | Đạo hàm riêng — đạo hàm theo $x$, các biến khác giữ cố định | 3 |
| $\dot q$, $\dot x$ | "q chấm" | Đạo hàm theo thời gian (vận tốc suy rộng) | 3 |
| ma trận Jacobi | | Bảng mọi đạo hàm riêng của các hàm ràng buộc | 4 |
| hạng (rank) | | Số phương trình/hướng thực sự độc lập, không dư thừa | 4 |
| $SO(2)$, $SO(3)$ | | Tập mọi phép quay 2D / 3D (một nhóm) | 5 |
| $R^\top R=I$ | | Điều kiện ma trận là phép quay (bảo toàn độ dài) | 5 |
| $dx$, $\omega$ | | Bước đi rất nhỏ; dạng vi phân bậc 1 (luật kiểm tra hướng) | 6 |
| $\wedge$ | "tích ngoài" | Phép nhân phản đối xứng, đo diện tích/thể tích có hướng | 6 |
| $d\omega$ | | "Độ xoáy" của luật hướng đi | 6 |
| $\omega\wedge d\omega=0$ | | Điều kiện Frobenius: ràng buộc toàn chỉnh | 6 |
| $L(q,\dot q,t)$ | "Lagrangian" | Hàm $L=T-V$, công cụ thay $F=ma$ | 7 |
| $\dfrac{d}{dt}\dfrac{\partial L}{\partial \dot q}=\dfrac{\partial L}{\partial q}$ | Euler–Lagrange | Phương trình chuyển động dạng Lagrange | 7 |
| $X$ | | Một phép biến đổi thử (ứng viên đối xứng) trong Định lý Noether | 7 |
| $\vec a\times\vec b$ | "tích có hướng" | Vectơ vuông góc, đo diện tích có hướng trong 3D | 8 |
| $M, L, T$ (thứ nguyên) | | Khối lượng, chiều dài, thời gian — đơn vị cơ bản | 9 |
| $\Pi_i$ | | Nhóm không thứ nguyên (Buckingham) | 9 |
| $\varepsilon$ | "epsilon" | Tham số bé (hoặc lớn) dùng để xấp xỉ | 9, 10 |
| $\lambda_i$ | "trị riêng" | "Tốc độ mũ" đặc trưng của một hướng trong hệ nhiều chiều | 10 |
| $\tau_i=-1/\lambda_i$ | | Hằng số thời gian tương ứng trị riêng | 10 |
| [G], [G$_k$], [C] | | Thuật toán tuyệt đối / thuật toán theo danh mục hữu hạn / cần đọc-hiểu đề | 1 |
