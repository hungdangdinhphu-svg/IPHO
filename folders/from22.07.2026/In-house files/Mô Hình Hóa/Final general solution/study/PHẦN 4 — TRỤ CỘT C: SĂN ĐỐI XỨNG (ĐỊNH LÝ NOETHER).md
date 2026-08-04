# TRỤ CỘT C: SĂN ĐỐI XỨNG — ĐỊNH LÝ NOETHER
### Tài liệu giảng giải chi tiết (dành cho học sinh đã biết đạo hàm và đạo hàm riêng)

---

## Lời mở đầu: vì sao đây là "vũ khí" mạnh nhất?

Khi giải một bài cơ học, cách "thô bạo" nhất là viết định luật 2 Newton cho từng vật, được một đống phương trình vi phân, rồi vật lộn giải chúng. Cách đó luôn *đúng*, nhưng thường *rất khó*.

Định lý Noether cho ta một con đường tắt: **thay vì giải phương trình vi phân, ta chỉ cần "nhìn" xem hệ có "vẻ ngoài" nào không đổi khi ta xê dịch nó đi một chút** (đẩy nó, xoay nó, đổi mốc thời gian, lật gương nó...). Mỗi lần tìm được một "vẻ ngoài không đổi" như vậy, ta được thưởng **miễn phí** một đại lượng không đổi theo thời gian (một *hằng số của chuyển động*). Đây chính là bảo toàn động lượng, bảo toàn mô-men động lượng, bảo toàn năng lượng — những thứ em đã quen dùng — nhưng bây giờ em sẽ thấy **chúng đến từ đâu**, chứ không phải là những "luật trời cho".

Mục tiêu của tài liệu này: sau khi đọc xong, em phải tự tay **chứng minh lại** được vì sao bảo toàn động lượng/mô-men động lượng/năng lượng là đúng, chỉ bằng cách nhìn vào tính đối xứng của bài toán — không cần học thuộc.

---

## 0. Hộp kiến thức nền: Lagrangian và phương trình Euler–Lagrange

Phần 4 dùng những công cụ này mà không định nghĩa lại (chúng thuộc phần khác của tài liệu gốc), nên ta ôn nhanh ở đây.

> **Toạ độ suy rộng $q^i$:** thay vì luôn dùng $x, y, z$, ta cho phép dùng *bất kỳ* tập số nào đủ để mô tả vị trí của hệ — góc, khoảng cách, v.v. Ví dụ con lắc đơn chỉ cần một số duy nhất: góc lệch $\theta$. Ta viết $q = (q^1, \dots, q^n)$ cho gọn, và $\dot q^i = dq^i/dt$ là vận tốc suy rộng tương ứng.

> **Hàm Lagrangian:** $L(q, \dot q, t) = T - V$, tức là **động năng trừ thế năng**, viết như một hàm của vị trí, vận tốc, và (đôi khi) thời gian.

> **Phương trình Euler–Lagrange:**
> $$\frac{d}{dt}\frac{\partial L}{\partial \dot q^i} = \frac{\partial L}{\partial q^i}$$
> Đây chỉ là **định luật 2 Newton ($F=ma$) viết lại** dưới dạng tổng quát, đúng cho mọi hệ toạ độ. Em không cần biết cách suy ra nó ở đây — chỉ cần chấp nhận: *đây là phương trình chuyển động đúng của hệ, giống vai trò của $F=ma$.*

> **Động lượng suy rộng:** đại lượng $p_i := \dfrac{\partial L}{\partial \dot q^i}$. Khi $q^i$ là toạ độ Descartes thường ($x$ chẳng hạn) và $T = \frac12 m\dot x^2$, ta có $p_x = \partial T/\partial \dot x = m\dot x$ — đúng là động lượng quen thuộc.

Với hai công cụ này (Lagrangian + Euler–Lagrange), toàn bộ Phần 4 sẽ được xây dựng.

---

## 1. "Đối xứng" nghĩa là gì, chính xác?

Trực giác: một bông tuyết có đối xứng quay $60°$ vì xoay nó $60°$ quanh tâm, ta *không phân biệt được* trước và sau. Một hình vuông đối xứng qua đường chéo.

Trong cơ học, ta áp dụng ý tưởng y hệt, nhưng đối tượng "trông có đổi hay không" bây giờ không phải là hình dạng, mà là **hàm Lagrangian $L$** — tức là *quy luật vật lý chi phối hệ*.

> **Định nghĩa (trực giác):** Một phép biến đổi (đẩy, xoay, đổi mốc thời gian...) là **đối xứng** của hệ nếu sau khi áp dụng nó, hàm $L$ mô tả hệ **không đổi**.

Ví dụ dễ nhất: hai hòn bi hút nhau bằng lực hấp dẫn, không có gì khác trong vũ trụ. Nếu ta bê *cả hệ* (cả hai hòn bi, giữ nguyên khoảng cách và vận tốc tương đối) dịch sang trái 5 mét — thì chuyển động tiếp theo sẽ diễn ra **giống hệt**, chỉ là toạ độ tuyệt đối khác đi. Đó là đối xứng tịnh tiến.

Ngược lại: một hòn bi nảy trên sàn nhà. Nếu ta bê cả hệ dịch xuống dưới 5 mét (xuyên qua sàn), tình huống vật lý **không còn giống** nữa (giờ bi nằm trong lòng đất!). Vậy đối xứng tịnh tiến *theo phương thẳng đứng* bị phá vỡ bởi sự có mặt của sàn nhà (một mốc tuyệt đối trong không gian).

**Điểm mấu chốt:** đối xứng không phải là tính chất tự nhiên "có sẵn" của không gian, mà là tính chất của **bài toán cụ thể** (phụ thuộc: có tường, có sàn, có trường ngoài hay không).

---

## 2. Phát biểu định lý Noether bằng lời, và vì sao nó "cho không"

> **Định lý Noether (bản dễ hiểu):** Nếu tồn tại một phép biến đổi liên tục (nghĩa là: có thể làm "rất nhỏ", làm dần dần từ 0 lên, chứ không phải bật/tắt như phép lật gương) sao cho $L$ không đổi, thì tồn tại một đại lượng **không đổi theo thời gian** trong suốt chuyển động.

Vì sao "cho không"? Vì trong Toán/Lý, giải một phương trình vi phân bậc 2 (như $F=ma$) khó hơn nhiều so với việc chỉ cần đạo hàm và cộng trừ để **kiểm tra** một tính chất bất biến. Định lý Noether biến việc "đoán/tìm định luật bảo toàn" thành một **thủ tục thuật toán**: đề xuất một phép biến đổi, thử xem $L$ có đổi không, nếu không đổi → có ngay một đại lượng bảo toàn, không cần giải gì thêm.

**Lưu ý quan trọng:** không phải MỌI phép biến đổi đều là đối xứng của MỌI bài toán. Ta phải *chủ động đi tìm* (đi "săn") xem bài toán cụ thể có đối xứng nào trong một danh sách hữu hạn các ứng viên. Đó là nội dung Mục 3 dưới đây.

---

## 3. Sáu phép thử "săn" đối xứng (tương ứng Mục 4.1)

Với mỗi bài toán, ta thử lần lượt 6 câu hỏi sau. Mỗi câu trả lời "có, vẫn giống hệt" cho ta một đại lượng bảo toàn.

### Phép thử 1 — Tịnh tiến theo một trục

**Câu hỏi:** Nếu bê cả hệ dịch một đoạn nhỏ dọc theo trục này, còn lực nào "từ bên ngoài" tác dụng dọc trục đó không?

**Ví dụ có đối xứng:** hai vật nối bằng lò xo, đặt trên mặt phẳng ngang không ma sát, không có gì khác. Đẩy cả hệ dọc trục ngang $x$ → không đổi gì (lực lò xo chỉ phụ thuộc khoảng cách tương đối, không phụ thuộc vị trí tuyệt đối). ⟹ tồn tại một đại lượng bảo toàn liên quan đến trục $x$ (ta sẽ thấy đó là tổng động lượng theo $x$).

**Ví dụ không có đối xứng:** một vật nằm cạnh một bức tường cố định. Đẩy cả hệ (vật + tường) thì được, nhưng nếu chỉ đẩy *vật* mà giữ tường đứng yên, khoảng cách vật–tường đổi → lực khác đi. Ở đây trục vuông góc với tường **không phải** đối xứng của riêng "vật" (tường là mốc tuyệt đối).

### Phép thử 2 — Quay quanh một trục

**Câu hỏi:** Nếu xoay cả hệ một góc nhỏ quanh trục này, còn ngoại mô-men lực (ngoại lực gây xoay) không?

**Ví dụ có đối xứng:** Mặt Trời và một hành tinh, lực hấp dẫn chỉ phụ thuộc khoảng cách giữa chúng. Xoay cả hệ (cả hai vật) quanh trục bất kỳ đi qua khối tâm → cấu hình mới có cùng khoảng cách, cùng lực → giống hệt.

### Phép thử 3 — Dịch mốc thời gian

**Câu hỏi:** Nếu bắt đầu thí nghiệm muộn hơn 1 giây (nhưng giữ nguyên mọi vị trí, vận tốc ban đầu), thì diễn biến tiếp theo có giống hệt kịch bản gốc (chỉ trễ đi 1 giây) không?

**Có đối xứng khi:** các lực không phụ thuộc "tường minh" vào $t$ tuyệt đối. Ví dụ con lắc đơn treo cố định, không ai tác động thêm — làm thí nghiệm hôm nay hay ngày mai, kết quả (xét theo thời gian trôi qua kể từ lúc thả) là như nhau.

**Không có đối xứng khi:** ví dụ mặt phẳng nghiêng đang được một động cơ *kéo di chuyển theo một quy luật đã định trước* $v(t)$ — ở đây "kịch bản" phụ thuộc vào thời điểm tuyệt đối vì vận tốc kéo tại giây thứ 3 khác giây thứ 5.

### Phép thử 4 — Phản xạ gương / hoán vị nhãn

**Câu hỏi:** Nếu lật hệ qua một gương (hoặc đổi tên hai vật giống hệt nhau cho nhau), bài toán có "trông giống" như cũ không?

**Ví dụ:** hai vật khối lượng bằng nhau nối với nhau bằng lò xo, đối xứng qua điểm giữa. Đổi nhãn "vật 1" ↔ "vật 2" và lật qua điểm giữa → cấu hình giống hệt. Hệ quả: khối tâm đứng yên (nếu ban đầu đứng yên) và hai vật luôn chuyển động đối xứng qua khối tâm.

### Phép thử 5 — Co giãn tỉ lệ (đổi thang đo)

**Câu hỏi:** Nếu phóng to/thu nhỏ toàn bộ hình học của bài theo một hệ số, cấu trúc bài có "lặp lại chính nó" không?

**Ví dụ:** một mạng điện trở vô hạn (mỗi ô giống hệt ô tiếp theo). Nhìn từ ô thứ 2 trở đi, mạng "trông giống hệt" mạng nhìn từ ô thứ nhất. Đây không phải phép tịnh tiến không gian vật lý, mà là tự-đồng-dạng cấu trúc — cho phép ta viết phương trình đệ quy thay vì cộng vô hạn số hạng.

### Phép thử 6 — Đảo dấu một biến

**Câu hỏi:** Nếu đảo chiều vận tốc ban đầu (hoặc đảo dấu điện tích nguồn), phương trình chuyển động có dạng giống hệt (chỉ khác dấu ở đâu đó) không?

**Ví dụ:** ném một vật thẳng đứng lên với vận tốc $v_0$; nếu thay $v_0 \to -v_0$ (ném xuống) thì quỹ đạo chuyển động chỉ là "quay ngược thời gian" của quỹ đạo ban đầu. Tính đối xứng này giúp suy ra ngay, ví dụ, thời gian đi lên bằng thời gian đi xuống — mà không cần giải lại phương trình.

---

## ⚠️ 4. Cạm bẫy hay gặp (đọc kỹ trước khi làm bài!)

Hai cảnh báo quan trọng:

1. **Một định luật bảo toàn chỉ đúng trong phạm vi mà đối xứng còn đúng.** Nếu giữa chừng bài toán có va chạm, xuất hiện ma sát, hay ngoại lực đổi bản chất (ví dụ dây bị chùng rồi lại căng) — đối xứng có thể *mất đi* tại thời điểm đó, và đại lượng "bảo toàn" trước đó có thể **đổi giá trị** sau thời điểm đó. Luôn kiểm tra lại điều kiện áp dụng ở *từng đoạn* của chuyển động.

2. **Không thể có cả bảo toàn động lượng và bảo toàn động năng "miễn phí" cùng lúc**, trừ khi được cho biết đó là va chạm đàn hồi (chứng minh riêng). Nếu đề bài ngầm yêu cầu dùng cả hai mà không nói rõ, gần như chắc chắn ít nhất một trong hai *không* thật sự bảo toàn — đây là bẫy rất hay gặp trong đề thi.

---

## 5. Định lý C1 — trái tim của Trụ cột C

Đây là phần "kỹ thuật" nhất, nhưng thực chất chỉ dùng đạo hàm và quy tắc tích/chuỗi mà em đã biết. Ta đi từng bước.

### 5.1 Ký hiệu $X^i$ nghĩa là gì?

$X = (X^1, \dots, X^n)$ là một "hướng nhích nhẹ" mà ta *đề xuất* cho mỗi toạ độ — nó có thể phụ thuộc vào vị trí hiện tại $q$ và thời gian $t$ (không nhất thiết là hằng số!). Phép biến đổi cụ thể là:
$$q^i \mapsto q^i + \varepsilon X^i(q, t)$$
với $\varepsilon$ là một số **rất nhỏ** (nghĩ như "nhích thêm một chút xíu"). 

**Ví dụ cụ thể:**
- Tịnh tiến đều theo trục $x$: $X = (1, 0, 0)$ — một *hằng số*, không phụ thuộc $q, t$.
- Quay quanh trục $\hat n$: $X_i(r) = \hat n \times r_i$ — phụ thuộc vào vị trí $r_i$ (càng xa trục, "nhích" càng nhiều — đúng như quay thật).

### 5.2 Điều kiện $(*)$ nghĩa là gì?

$$\sum_i\left[\frac{\partial L}{\partial q^i}X^i+\frac{\partial L}{\partial \dot q^i}\frac{dX^i}{dt}\right]=0$$

Đây chính xác là: **"tốc độ thay đổi của $L$ khi ta nhích hệ theo hướng $X$"**, tính bằng quy tắc chuỗi (giống hệt cách em tính $dL/d\varepsilon$ tại $\varepsilon = 0$ khi $L$ phụ thuộc $q$ và $\dot q$ mà cả hai đều phụ thuộc $\varepsilon$ qua công thức $q \to q + \varepsilon X$).

Chỗ hay dễ nhầm: $\dfrac{dX^i}{dt}$ không phải là đạo hàm riêng của $X^i$ theo $t$ đơn thuần, mà là đạo hàm **toàn phần** dọc theo chuyển động thật:
$$\frac{dX^i}{dt} = \frac{\partial X^i}{\partial t} + \sum_j \frac{\partial X^i}{\partial q^j}\dot q^j$$
(quy tắc chuỗi bình thường: $X^i$ phụ thuộc $t$ trực tiếp, và gián tiếp qua $q^j(t)$).

**Điều quan trọng nhất về $(*)$:** nó phải đúng **với MỌI** $(q, \dot q, t)$ — tức là đúng như một *đẳng thức hàm số*, không chỉ đúng dọc theo nghiệm thật của bài toán. Đây là lý do việc kiểm tra $(*)$ chỉ là đạo hàm-và-cộng thuần túy, làm được bằng máy tính, không cần "linh cảm vật lý" — ta chỉ cần linh cảm để **đề xuất** $X$ nào đáng thử (đó là việc của 6 phép thử ở Mục 3).

### 5.3 Phát biểu định lý

> Nếu $(*)$ đúng, thì đại lượng
> $$I(q,\dot q,t) = \sum_i \frac{\partial L}{\partial \dot q^i}X^i(q,t) = \sum_i p_i X^i$$
> **không đổi theo thời gian** dọc theo mọi nghiệm thật của bài toán: $\dfrac{dI}{dt} = 0$.

Đọc bằng lời: $I$ là **"động lượng suy rộng, chiếu lên hướng nhích $X$"**. Nếu nhích theo hướng $X$ mà vật lý không đổi, thì "lượng động lượng đi theo hướng đó" được giữ nguyên mãi mãi.

### 5.4 Chứng minh, giải thích từng dòng

$$\frac{dI}{dt}=\sum_i\left[\underbrace{\frac{d}{dt}\Big(\frac{\partial L}{\partial \dot q^i}\Big)}_{\text{đạo hàm của } p_i}X^i+\frac{\partial L}{\partial \dot q^i}\frac{dX^i}{dt}\right]$$

Đây chỉ là **quy tắc đạo hàm một tích** áp dụng cho $I = \sum_i p_i(t) \cdot X^i(t)$: đạo hàm của (số hạng thứ nhất) $\times$ (số hạng thứ hai), cộng với (số hạng thứ nhất) $\times$ đạo hàm của (số hạng thứ hai).

Bước tiếp theo: **vì $q(t)$ là nghiệm thật của bài toán**, phương trình Euler–Lagrange cho phép ta thay
$$\frac{d}{dt}\Big(\frac{\partial L}{\partial \dot q^i}\Big) \longrightarrow \frac{\partial L}{\partial q^i}$$
(đây là chỗ *duy nhất* trong chứng minh dùng đến "vật lý thật" — tức là dùng $F=ma$).

Thay vào, ta được:
$$\frac{dI}{dt}=\sum_i\left[\frac{\partial L}{\partial q^i}X^i+\frac{\partial L}{\partial \dot q^i}\frac{dX^i}{dt}\right]$$

— và đây **chính xác là vế trái của $(*)$**, mà theo giả thiết bằng 0. Vậy $dI/dt = 0$. $\blacksquare$

**Tóm gọn cấu trúc chứng minh bằng một câu:** *"Đạo hàm của $I$ = (Euler–Lagrange biến nó thành) vế trái của điều kiện đối xứng $(*)$ = 0."* Không có bước nào khác. Đây là lý do định lý này "ngắn gọn một cách đáng kinh ngạc" — toàn bộ sức mạnh nằm ở việc *chọn đúng* $X$, chứ không nằm ở độ khó của chứng minh.

---

## 6. Bốn hệ quả quen thuộc (tương ứng Mục 4.3)

Bây giờ ta áp dụng Định lý C1 cho các phép thử cụ thể, và sẽ thấy các định luật bảo toàn "cổ điển" hiện ra như trường hợp riêng.

Khái niệm "không xuất hiện tường minh" (explicitly absent) trong cơ học Lagrange, bản chất của nó là kiểu như "Nhìn mắt thường vào công thức không thấy chữ đó xuất hiện." :3 

### (a) Toạ độ vắng mặt (cyclic) ⟹ động lượng suy rộng bảo toàn

**Tình huống:** giả sử trong biểu thức của $L$, biến $q^1$ không xuất hiện tường minh (chỉ $\dot q^1$ xuất hiện) — nghĩa là $\partial L/\partial q^1 \equiv 0$.

**Ví dụ cụ thể:** một hạt trượt tự do trên mặt phẳng ngang, không ma sát, không lực nào khác. $L = \frac12 m\dot x^2$ — biến $x$ hoàn toàn không xuất hiện (chỉ $\dot x$ có mặt) $\Rightarrow$ $x$ là toạ độ cyclic.

**Áp dụng:** chọn $X = (1, 0, \dots, 0)$ — một hằng số, nên $dX/dt = 0$. Kiểm tra $(*)$:
$$\frac{\partial L}{\partial q^1}\cdot 1 + \frac{\partial L}{\partial \dot q^1}\cdot 0 = \frac{\partial L}{\partial q^1} = 0 \quad \checkmark \text{ (đúng theo giả thiết)}$$

Vậy $I = \partial L/\partial \dot q^1 = p_1$ bảo toàn.

**Trong ví dụ trên:** $p_x = m\dot x = $ const, tức là $\dot x$ không đổi — **đây chính là Định luật 1 Newton (quán tính), suy ra từ Noether!** Một minh chứng đẹp: cái mà ta tưởng là "tiên đề" hoá ra chỉ là hệ quả của việc không gian trống không có gì phân biệt điểm này với điểm khác dọc trục $x$.

### (b) Đối xứng tịnh tiến toàn hệ ⟹ tổng động lượng bảo toàn

**Tình huống:** hệ $n$ chất điểm, $L = \sum_i \frac12 m_i|\dot r_i|^2 - V(r_1,\dots,r_n)$, trong đó $V$ **chỉ phụ thuộc hiệu vị trí** giữa các hạt (ví dụ lực hấp dẫn/lò xo giữa các hạt với nhau, không có ngoại lực).

**Ví dụ cụ thể:** hai vật nối bằng lò xo, bay tự do trong không gian (không trọng lực, không ma sát). $V = \frac12 k(|r_1 - r_2| - \ell_0)^2$ — chỉ phụ thuộc $r_1 - r_2$, nếu dịch cả $r_1$ và $r_2$ cùng một vector $\hat n$ thì $r_1 - r_2$ không đổi $\Rightarrow$ $V$ không đổi.

**Áp dụng:** chọn $X_i = \hat n$ (cùng một vector hằng số cho MỌI hạt — tức là đẩy cả hệ cùng lúc, cùng hướng, cùng độ lớn), $dX/dt = 0$. Vì $V$ bất biến dưới tịnh tiến toàn cục, đạo hàm của $V$ theo $\varepsilon$ tại $\varepsilon=0$ (chính là vế trái $(*)$, phần thế năng) phải bằng 0:
$$\sum_i \nabla_i V \cdot \hat n = 0 \quad \text{với mọi } \hat n$$
Đây đúng là điều kiện $(*)$ được thoả mãn (phần động năng của $(*)$ tự động bằng 0 vì $X$ là hằng số).

Vậy $I = \sum_i m_i \dot r_i \cdot \hat n = P \cdot \hat n$ bảo toàn — đúng với **mọi** hướng $\hat n$ ta chọn (trên, dưới, trái, phải...) $\Rightarrow$ cả vector $P = \sum_i m_i \dot r_i$ (tổng động lượng) phải là hằng số.

**Đây chính là định luật bảo toàn động lượng em đã học** — bây giờ em thấy nó không phải "tiên đề", mà là hệ quả của việc lực giữa hai vật chỉ phụ thuộc khoảng cách tương đối, không phụ thuộc "chúng đang ở đâu trong vũ trụ".

### (c) Đối xứng quay toàn hệ ⟹ tổng mô-men động lượng bảo toàn

> **Hộp nhắc lại — tích có hướng (cross product) $a \times b$:** một vector mới, độ lớn $= |a||b|\sin\theta$ ($\theta$ là góc giữa $a, b$), hướng vuông góc với cả $a$ và $b$ (theo quy tắc bàn tay phải). Tính chất cần dùng: $v \times v = 0$ (một vector nhân có hướng với chính nó luôn bằng 0), và **hoán vị vòng** của tích ba vô hướng: $a\cdot(b\times c) = b\cdot(c\times a) = c\cdot(a\times b)$ (đây là một đẳng thức đại số thuần tuý, có thể kiểm chứng bằng toạ độ).

**Tình huống:** cùng hệ như trên nhưng bây giờ $V$ bất biến dưới **quay** toàn hệ (ví dụ $V$ chỉ phụ thuộc khoảng cách $|r_1 - r_2|$, mà khoảng cách không đổi khi ta quay cả hai điểm cùng một góc quanh cùng một trục).

**Áp dụng:** chọn $X_i(r) = \hat n \times r_i$ — đây chính là công thức toán học của "quay vi phân": khi quay một vector $r$ một góc rất nhỏ $\varepsilon$ quanh trục $\hat n$, độ dịch chuyển xấp xỉ là $\varepsilon (\hat n \times r)$ (em có thể hình dung: điểm càng xa trục quay thì "vun vút" càng nhanh, đúng như $|\hat n \times r|$ tăng theo khoảng cách vuông góc tới trục).

Vì $X$ bây giờ phụ thuộc vị trí (không phải hằng số), $\dfrac{dX_i}{dt} = \hat n \times \dot r_i$.

Phần thế năng của $(*)$: lý luận y hệt phần (b) nhưng với phép quay, cho $\sum_i \nabla_i V \cdot (\hat n \times r_i) = 0$.

Phần động năng của $(*)$: $\sum_i m_i \dot r_i \cdot (\hat n \times \dot r_i) = 0$ — vì đây có dạng $\dot r_i \cdot (\hat n \times \dot r_i)$, dùng hoán vị vòng $\to \hat n \cdot (\dot r_i \times \dot r_i) = \hat n \cdot 0 = 0$ (một vector nhân có hướng với chính nó bằng 0).

Vậy $(*)$ được thoả mãn, và:
$$I=\sum_i m_i\dot r_i\cdot(\hat n\times r_i)\stackrel{\text{hoán vị vòng}}{=}\hat n\cdot\Big(\sum_i r_i \times m_i\dot r_i\Big) = \hat n \cdot L_{\text{tổng}}$$
bảo toàn với **mọi** $\hat n$ $\Rightarrow$ $L_{\text{tổng}} = \sum_i r_i \times m_i \dot r_i$ (tổng mô-men động lượng) là hằng số.

### (d) Đối xứng dịch mốc thời gian ⟹ năng lượng bảo toàn

**Định nghĩa:** $H := \sum_i \dot q^i \dfrac{\partial L}{\partial \dot q^i} - L$ (gọi là "Hamiltonian").

**Tính $dH/dt$ trực tiếp** (không cần điều kiện $(*)$ ở dạng tổng quát của C1, vì phép "dịch thời gian" là một trường hợp đặc biệt cần xử lý riêng — nhưng ý tưởng giống hệt):

$$\frac{dH}{dt} = -\frac{\partial L}{\partial t}$$

(Kết quả này có được bằng cách khai triển đạo hàm của $H$ theo quy tắc tích, rồi dùng Euler–Lagrange để rút gọn — hoàn toàn tương tự thao tác ở Mục 5.4.)

**Đọc bằng lời:** $H$ thay đổi theo thời gian *đúng bằng* mức độ mà $L$ "tự nó" phụ thuộc tường minh vào $t$. Nếu $L$ không có $t$ nằm trơ trọi trong công thức (mọi sự phụ thuộc $t$ đều gián tiếp qua $q(t), \dot q(t)$) — tức là có đối xứng dịch mốc thời gian — thì $\partial L/\partial t = 0$ nên $H = $ const.

**$H$ có phải là năng lượng $T + V$ không?** Không phải lúc nào cũng đúng ngay — cần thêm một điều kiện: $T$ phải là **hàm thuần nhất bậc 2** theo $\dot q$ (nghĩa là nếu nhân mọi $\dot q^i$ với hệ số $k$, thì $T$ nhân với $k^2$) — điều này đúng khi ràng buộc của hệ **không phụ thuộc thời gian** (gọi là *scleronomic*, ví dụ: vật trượt trên đường ray *cố định*, không phải đường ray đang di chuyển).

**Kiểm tra với ví dụ đơn giản:** $T = \frac12 m\dot x^2$. Nhân $\dot x \to k\dot x$: $T \to \frac12 m k^2 \dot x^2 = k^2 T$ ✓ (thuần nhất bậc 2).

**Định lý Euler cho hàm thuần nhất bậc 2** nói: nếu $T$ thuần nhất bậc 2 theo $\dot q$, thì $\sum_i \dot q^i \dfrac{\partial T}{\partial \dot q^i} = 2T$.

*Kiểm chứng nhanh bằng ví dụ trên:* $\dot x \cdot \dfrac{\partial T}{\partial \dot x} = \dot x \cdot (m\dot x) = m\dot x^2 = 2T$ ✓.

Vì $V$ thường không phụ thuộc $\dot q$ (chỉ phụ thuộc $q$), nên $\sum_i \dot q^i \partial L/\partial \dot q^i = \sum_i \dot q^i \partial T/\partial \dot q^i = 2T$. Thay vào định nghĩa $H$:
$$H = 2T - L = 2T - (T - V) = T + V = E$$

Vậy trong điều kiện thông thường (ràng buộc không đổi theo thời gian), $H$ chính là năng lượng cơ học quen thuộc $E = T+V$, và nó bảo toàn khi hệ có đối xứng dịch mốc thời gian.

---

## 7. Bảng tổng kết Trụ cột C (Bảng C) — giải thích từng dòng

| # | Phép thử $X$ | Điều kiện áp dụng | Đại lượng bảo toàn |
|---|---|---|---|
| 1 | Tịnh tiến dọc $\hat e_j$ | $q^j$ vắng mặt trong $L$ | $p_j$ |
| 2 | Quay quanh $\hat n$ | thế năng chỉ phụ thuộc khoảng cách/góc, bất biến quay quanh $\hat n$ | $L_{\hat n}$ |
| 3 | Dịch mốc thời gian | $\partial L/\partial t = 0$ | $H$ (= $T+V$ nếu ràng buộc cố định) |
| 4 | Đối xứng hình học nguồn trường | mật độ điện tích/dòng bất biến dưới nhóm quay/tịnh tiến tương ứng | dạng hàm của $\vec E, \vec B$ đơn giản hoá |
| 5 | Đối xứng gương/hoán vị mạch | mạch bất biến dưới phản chiếu/hoán vị nút | các thế nút liên hợp bằng nhau |

**Vì sao bảng này liệt kê đủ, không sót gì (Mục 4.4)?** Lý luận như sau: trong toàn bộ chương trình thi Vật lý cơ học kiểu IPhO, thế năng $V$ chỉ có hai dạng:

- **Loại (i):** phụ thuộc khoảng cách từng cặp hạt (lực hấp dẫn, lực Coulomb, lực lò xo giữa hai vật...). Loại này chỉ bất biến dưới đúng nhóm phép biến đổi "tịnh tiến + quay" (gọi là $SE(3)$ trong toán học) — không có phép biến đổi liên tục nào khác giữ nguyên khoảng cách giữa hai điểm ngoài tịnh tiến và quay.
- **Loại (ii):** phụ thuộc vị trí tuyệt đối qua một **trường ngoài đều** (trọng lực đều gần mặt đất, điện trường đều). Loại này chỉ bất biến dưới tịnh tiến **trong mặt phẳng vuông góc với trường** (dịch lên xuống theo phương trường thì thế năng đổi, dịch ngang thì không).

Vì hai loại lực trên là *toàn bộ* "thư viện lực" xuất hiện trong đề thi cơ học IPhO, nên **không có đối xứng "ẩn" nào khác** có thể xuất hiện ngoài Phép thử 1–3. Đây là lý do Trụ cột C được gọi là "$G_k$" — một danh sách hữu hạn, có thể duyệt hết — chứ không phải một danh sách vô hạn cần trực giác thiên tài mới nghĩ ra.

---

## 8. Mở rộng sang trường liên tục: Định lý C2

Bây giờ ta áp dụng đúng *tinh thần* của Noether ("đối xứng của nguyên nhân ⟹ đối xứng của kết quả") sang một bối cảnh khác: điện trường sinh ra bởi một đám mây điện tích.

### 8.1 Phát biểu bằng lời

> Nếu một đám mây điện tích có **mật độ đối xứng cầu** (nghĩa là: xoay đám mây quanh tâm theo bất kỳ cách nào, đám mây "trông giống hệt" — mật độ điện tích tại điểm cách tâm $r$, theo hướng nào cũng như nhau), thì điện trường mà nó sinh ra **buộc phải** có hai tính chất:
> 1. Tại mỗi điểm, vector điện trường **chỉ có thể hướng ra ngoài (hoặc vào trong) theo phương bán kính** — không thể nghiêng đi đâu khác.
> 2. Độ lớn điện trường **chỉ phụ thuộc khoảng cách $r$ tới tâm**, không phụ thuộc hướng.

Đây không phải là một quan sát thực nghiệm — nó là **hệ quả logic bắt buộc** của tính đối xứng của nguồn.

### 8.2 Vì sao lại "buộc phải" như vậy — chứng minh từng bước

**Bước 1 — Tính "song hành" (đẳng biến):** nếu ta xoay toàn bộ đám mây điện tích bằng một phép quay $R$ nào đó, thì trường sinh ra tại điểm $Rx$ (điểm đã bị xoay) chính là trường cũ tại $x$, nhưng bản thân vector đó cũng bị xoay đi:
$$\vec E(Rx) = R\,\vec E(x)$$
Điều này đúng cho *bất kỳ* phân bố điện tích nào (không cần đối xứng) — nó chỉ phản ánh việc công thức tính điện trường (tích phân Coulomb) "tôn trọng" phép quay, vì khoảng cách và hướng tương đối không đổi khi ta quay cả nguồn lẫn điểm quan sát cùng lúc.

**Nhưng** vì mật độ điện tích $\rho$ của ta có đối xứng cầu ($\rho(Rx) = \rho(x)$ với **mọi** $R$), quay nguồn không làm gì thay đổi cả — nguồn "trước và sau khi quay" là *cùng một đám mây*. Vậy trường sinh ra bởi "nguồn đã quay" chính là trường $\vec E(x)$ ban đầu (không đổi khi ta quay nguồn), kết hợp với tính đẳng biến ở trên, ta được:
$$\vec E(Rx) = R\,\vec E(x) \quad \text{với } \rho \text{ đối xứng cầu}$$

**Bước 2 — Suy ra hướng:** cố định một điểm $x \neq 0$ bất kỳ. Xét riêng các phép quay $R$ **quanh chính trục nối tâm với $x$** (tức là các phép quay giữ nguyên điểm $x$: $Rx = x$). Với các $R$ này, công thức trên cho:
$$\vec E(x) = \vec E(Rx) = R\,\vec E(x)$$
Nghĩa là $\vec E(x)$ là một vector **không đổi khi bị quay quanh trục qua $x$**. Nhưng một vector chỉ có thể "sống sót" không đổi khi quay quanh một trục nếu nó **nằm dọc theo chính trục đó** (mọi vector nghiêng đi sẽ "quét" thành một hình nón khi quay, tức là đổi hướng). Vậy $\vec E(x)$ phải song song với $x$ — tức là **hướng theo phương bán kính**.

**Bước 3 — Suy ra độ lớn chỉ phụ thuộc $r$:** lấy hai điểm $x, x'$ có cùng khoảng cách tới tâm ($|x|=|x'|$). Luôn tồn tại một phép quay $R$ đưa $x$ thành $x'$ ($Rx = x'$). Áp dụng Bước 1: $\vec E(x') = R\,\vec E(x)$ — hai vector này có cùng độ lớn (quay không đổi độ dài) $\Rightarrow$ $E(x') = E(x)$. Vậy độ lớn $E$ chỉ phụ thuộc $r = |x|$, không phụ thuộc hướng. $\blacksquare$

### 8.3 Vì sao điều này khiến định lý Gauss "gần như hiển nhiên"

Một khi đã biết (nhờ đối xứng, không cần tính toán gì thêm!) rằng $\vec E$ luôn hướng ra ngoài theo bán kính và có độ lớn $E(r)$ như nhau trên mọi điểm của một mặt cầu bán kính $r$ quanh tâm, thì thông lượng qua mặt cầu đó là phép nhân đơn giản:
$$\oint_{S_r}\vec E\cdot d\vec S = E(r)\times(\text{diện tích mặt cầu}) = E(r)\cdot 4\pi r^2$$
(vì $\vec E$ luôn song song với vector pháp tuyến $d\vec S$ tại mọi điểm trên mặt cầu, và có cùng độ lớn — nên tích vô hướng chỉ đơn giản là tích độ lớn). Kết hợp với định luật Gauss ($\oint \vec E \cdot d\vec S = Q_{\text{trong}}/\varepsilon_0$), ta giải ra $E(r)$ bằng đại số, **không cần làm tích phân khó** trên toàn bộ đám mây điện tích.

**Ví dụ số kiểm chứng:** quả cầu điện tích đều, mật độ $\rho$, bán kính $R$. Với $r < R$, điện tích nằm trong bán kính $r$ là $Q_{\text{trong}}(r) = \rho \cdot \frac43\pi r^3$. Định luật Gauss:
$$E(r)\cdot 4\pi r^2 = \frac{\rho \cdot \frac43\pi r^3}{\varepsilon_0} \Longrightarrow E(r) = \frac{\rho r}{3\varepsilon_0}$$
— khớp với kết quả đã biết.

**Cùng một cơ chế logic** (chỉ thay nhóm đối xứng: đối xứng trụ cho dây/ống dài vô hạn, đối xứng phẳng cho mặt phẳng vô hạn) áp dụng cho định lý Ampère (từ trường) và trường điện phẳng — em không cần học lại từ đầu, chỉ cần thay "hình học của nguồn" tương ứng.

---

## 9. Một ví dụ hoàn chỉnh: "săn đối xứng" từ đầu đến cuối

**Đề bài:** Hai vật khối lượng $m_1, m_2$ nối bằng một lò xo lý tưởng, nằm trên mặt phẳng ngang **không ma sát**, không có ngoại lực nào khác. Tìm các đại lượng bảo toàn, không cần giải phương trình chuyển động.

**Bước 1 — Viết Lagrangian.** Gọi $x_1, x_2$ là vị trí hai vật trên trục ngang:
$$L = \frac12 m_1\dot x_1^2 + \frac12 m_2\dot x_2^2 - \frac12 k(x_1 - x_2 - \ell_0)^2$$

**Bước 2 — Thử Phép thử 1 (tịnh tiến toàn hệ dọc $x$).** Đẩy cả hai vật cùng một đoạn $\varepsilon$: $x_1 \to x_1+\varepsilon$, $x_2 \to x_2+\varepsilon$. Vì $L$ chỉ phụ thuộc *hiệu* $x_1 - x_2$ (không đổi khi cộng cùng $\varepsilon$ vào cả hai), $L$ không đổi $\Rightarrow$ đây là đối xứng, với $X = (1,1)$.

**Bước 3 — Tính đại lượng bảo toàn.** Theo Định lý C1 (hoặc trực tiếp theo hệ quả (b)):
$$I = \frac{\partial L}{\partial \dot x_1}\cdot 1 + \frac{\partial L}{\partial \dot x_2}\cdot 1 = m_1\dot x_1 + m_2\dot x_2 = P$$
— tổng động lượng bảo toàn, dù lò xo có thể đang dao động rất phức tạp!

**Bước 4 — Thử Phép thử 3 (dịch mốc thời gian).** $L$ ở trên không chứa $t$ tường minh ở đâu cả (không có động cơ, không có ngoại lực đổi theo thời gian tuyệt đối) $\Rightarrow$ có đối xứng dịch thời gian $\Rightarrow$ năng lượng $E = \frac12 m_1\dot x_1^2 + \frac12 m_2\dot x_2^2 + \frac12 k(x_1-x_2-\ell_0)^2$ bảo toàn.

**Kết quả:** chỉ bằng cách "nhìn" đối xứng — không giải một phương trình vi phân nào — ta có ngay **hai** đại lượng bảo toàn ($P$ và $E$), đủ để giải bài toán hai vật một chiều bằng đại số thuần túy (đưa về bài toán một vật trong hệ quy chiếu khối tâm).

---

## 10. Tóm tắt quy trình làm bài ("thuật toán săn đối xứng")

1. Viết $L = T - V$ cho hệ.
2. Với mỗi phép thử trong Bảng C (tịnh tiến theo từng trục, quay quanh từng trục khả dĩ, dịch mốc thời gian, và với bài điện/từ trường: đối xứng hình học nguồn) — **tự hỏi:** hệ có "trông giống hệt" sau phép biến đổi này không?
3. Nếu có, xác định $X$ tương ứng, và viết ra đại lượng bảo toàn $I = \sum_i p_i X^i$ (hoặc dùng trực tiếp các công thức đã chứng minh sẵn ở Mục 6: $p_j$, $P$, $L_{\hat n}$, $H$).
4. **Kiểm tra bẫy:** đối xứng có bị phá vỡ ở đoạn nào của chuyển động không (va chạm, ma sát xuất hiện...)? Nếu có, đại lượng chỉ bảo toàn trong từng đoạn, phải nối các đoạn lại cẩn thận.
5. Dùng các đại lượng bảo toàn tìm được như những phương trình đại số, thay cho việc giải phương trình vi phân.

**Bài tập tự luyện đề xuất:**
- Con lắc kép (double pendulum): thử tìm xem có đối xứng tịnh tiến/quay/thời gian nào không — vì sao động lượng thẳng *không* bảo toàn ở đây?
- Hai điện tích cùng dấu, tự do trong không gian: chứng minh cả động lượng và mô-men động lượng tổng đều bảo toàn, viết rõ $X$ dùng trong mỗi trường hợp.
- Một khối trụ tích điện đều, dài vô hạn: dùng lý luận giống Định lý C2 (thay nhóm quay cầu bằng nhóm quay quanh trục trụ + tịnh tiến dọc trục) để chứng minh $\vec E$ hướng theo phương bán kính trụ và chỉ phụ thuộc khoảng cách tới trục.
