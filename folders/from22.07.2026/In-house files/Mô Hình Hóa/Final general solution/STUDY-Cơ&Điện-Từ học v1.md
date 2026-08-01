# GIÁO TRÌNH NỀN TẢNG
## Để tự đọc hiểu và dùng thuần thục tài liệu "Cơ & Điện-Từ học — Cách giải tổng quát"

*Soạn cho học sinh giỏi Vật lý lớp 9, đã vững Đạo hàm/Tích phân một biến.*

---

### Cách dùng tài liệu này

Tài liệu gốc của thầy con là một bản đồ chiến lược viết cho người **đã có** một bộ máy toán học nhất định trong tay (cơ học Lagrange, đại số tuyến tính, dạng vi phân, lý thuyết nhóm sơ cấp). Nó không sai ở đâu cả — nó chỉ "nhảy cóc" so với những gì con đã học, vì nó không viết cho lớp 9.

Giáo trình này làm đúng một việc: **xây từng bậc thang toán học còn thiếu, theo đúng thứ tự cần dùng**, rồi mới đặt con đứng trước từng Định lý (A, B, C1, C2, D1, D2, D3) trong tài liệu gốc để con thấy nó "hiển nhiên phải như vậy" chứ không phải "một công thức từ trên trời rơi xuống".

**Nguyên tắc đọc:** Đọc theo đúng thứ tự Chương 0 → 1 → 2 → ... Đừng nhảy. Mỗi định lý mới đều dùng lại công cụ của chương trước. Sau mỗi mục lớn có phần **"Tự kiểm tra"** — nếu con trả lời được các câu đó bằng lời của chính mình (không nhìn lại), tức là con đã hiểu bản chất, không phải học vẹt. Nếu bí một câu, quay lại đọc mục đó lần nữa trước khi đi tiếp — đừng cố nhớ, cố *hiểu lại*.

Ký hiệu $\S$X.Y trong tài liệu này tương ứng với mục X.Y; khi tôi viết "(xem tài liệu gốc, dòng B4)" nghĩa là con nên mở lại file gốc, đọc song song.

---
---

# CHƯƠNG 0 — BỘ CÔNG CỤ TOÁN HỌC BẮT BUỘC

Trước khi chạm vào một dòng Vật lý nào, ta cần 5 công cụ toán. Không có công cụ nào trong số này "khó" hơn đạo hàm mà con đã biết — chúng chỉ là đạo hàm/tích phân được **mở rộng** sang nhiều biến, và một chút hình học của vector.

## 0.1 Đạo hàm riêng và vi phân toàn phần

Con đã quen: nếu $y=f(x)$, đạo hàm $f'(x)$ đo tốc độ thay đổi của $y$ khi $x$ nhích một lượng nhỏ $dx$: $dy = f'(x)\,dx$.

Bây giờ, nếu $f$ phụ thuộc **hai** biến, $f(x,y)$ — ví dụ diện tích hình chữ nhật $f(x,y)=xy$ — thì $f$ có thể thay đổi theo hai "hướng" độc lập. Ta định nghĩa:

- **Đạo hàm riêng theo $x$**, ký hiệu $\dfrac{\partial f}{\partial x}$: đạo hàm của $f$ theo $x$, **coi $y$ là hằng số tạm thời**. Với $f=xy$: $\dfrac{\partial f}{\partial x}=y$.
- Tương tự $\dfrac{\partial f}{\partial y}=x$.

Đây không phải khái niệm mới — đó chính là đạo hàm một biến quen thuộc, chỉ là ta "đóng băng" biến còn lại. Nếu con biết tính $\dfrac{d}{dx}(3x^2)=6x$, con đã biết tính đạo hàm riêng.

**Vi phân toàn phần:** khi cả $x$ và $y$ đều nhích một lượng nhỏ $dx, dy$, $f$ thay đổi một lượng:
$$df = \frac{\partial f}{\partial x}dx + \frac{\partial f}{\partial y}dy.$$

Đây là bản mở rộng của công thức $dy=f'(x)dx$ quen thuộc — cộng dồn đóng góp từ **từng hướng** thay đổi. Với $N$ biến $x=(x^1,\dots,x^N)$:
$$df = \sum_{i=1}^N \frac{\partial f}{\partial x^i}dx^i.$$

Ký hiệu $x^i$ (số mũ trên) không phải là lũy thừa — đó là **chỉ số đánh số biến** ($x^1, x^2,\dots$), quy ước chuẩn khi số biến lớn. Con sẽ gặp ký hiệu này liên tục trong tài liệu gốc.

**Quy tắc dây chuyền theo thời gian (rất quan trọng, dùng lại suốt Chương 5):** Nếu $x^i = x^i(t)$ đều là hàm của thời gian, và $F(x,t)$ là một hàm phụ thuộc $x$ và (có thể) tường minh vào $t$, thì tốc độ thay đổi của $F$ dọc theo chuyển động là:
$$\frac{dF}{dt} = \frac{\partial F}{\partial t} + \sum_i \frac{\partial F}{\partial x^i}\dot x^i,$$
trong đó $\dot x^i := dx^i/dt$. Công thức này **chính là** vi phân toàn phần ở trên, chia cho $dt$. Số hạng $\partial F/\partial t$ là phần "$F$ tự thay đổi theo thời gian dù $x$ đứng yên"; phần còn lại là "$F$ thay đổi vì $x$ đang di chuyển". Hãy nhớ kỹ công thức này — nó xuất hiện lại y hệt khi định nghĩa $dX^i/dt$ ở Định lý C1.

**Ví dụ cụ thể:** $F(x,t) = x^2 + t$, với $x(t)=\sin t$. Cách 1 (thay trực tiếp): $F(t) = \sin^2 t + t$, $\dfrac{dF}{dt} = 2\sin t\cos t + 1$. Cách 2 (công thức trên): $\partial F/\partial t = 1$, $\partial F/\partial x = 2x$, $\dot x = \cos t$, nên $dF/dt = 1 + 2x\cos t = 1+2\sin t\cos t$. Khớp nhau — đó là vì công thức dây chuyền chỉ là cách tính "từng phần" của phép thay số trực tiếp.

## 0.2 Vector, tích vô hướng, tích có hướng

Con đã quen vector trong mặt phẳng. Ta cần 2 phép toán trên vector 3 chiều $\vec a=(a_1,a_2,a_3)$:

- **Tích vô hướng (dot product):** $\vec a\cdot\vec b = a_1b_1+a_2b_2+a_3b_3$, một **số**, đo "bao nhiêu $\vec a$ nằm dọc theo $\vec b$".
- **Tích có hướng (cross product):** $\vec a\times\vec b$ là một **vector mới**, vuông góc với cả $\vec a$ và $\vec b$, độ lớn $|\vec a||\vec b|\sin\theta$ (diện tích hình bình hành tạo bởi hai vector), chiều theo quy tắc bàn tay phải. Công thức tọa độ:
$$\vec a\times\vec b = (a_2b_3-a_3b_2,\ a_3b_1-a_1b_3,\ a_1b_2-a_2b_1).$$
- Tính chất cần nhớ: $\vec a\times\vec b = -\vec b\times\vec a$ (đổi chỗ thì đổi dấu — **phản đối xứng**), và $\vec a\times\vec a=\vec 0$.

**Tích hỗn tạp (scalar triple product):** $\vec a\cdot(\vec b\times\vec c)$ — một số, bằng đúng **thể tích có dấu** của hình hộp tạo bởi 3 vector. Vì nó là một định thức $3\times 3$ (dòng là tọa độ $\vec a,\vec b,\vec c$), và đổi chỗ **hai** dòng của định thức thì đổi dấu, còn hoán vị **vòng tròn** ba dòng ($a\to b\to c\to a$) tương đương với **hai** phép đổi chỗ liên tiếp — dấu không đổi. Vậy:
$$\vec a\cdot(\vec b\times\vec c) = \vec b\cdot(\vec c\times\vec a) = \vec c\cdot(\vec a\times\vec b).$$
Đây gọi là **tính hoán vị vòng (cyclic)** của tích hỗn tạp — ta sẽ dùng đúng đẳng thức này để chứng minh bảo toàn mô-men động lượng ở $\S5.3$(c). Con không cần nhớ máy móc; chỉ cần nhớ "đảo vòng tròn 3 vật không đổi dấu, đảo 2 vật thì đổi dấu" — đây chính là mầm mống của "tích ngoài" mà ta sẽ gặp lại ở Chương 4.

## 0.3 Ma trận và "hạng" (rank) — đo số ràng buộc thực sự độc lập

Một **ma trận** là một bảng số. Ta chỉ cần một khái niệm duy nhất: **hạng (rank)**.

Xét hệ phương trình tuyến tính, ví dụ 2 phương trình 3 ẩn:
$$x+y+z=0,\qquad 2x+2y+2z=0.$$
Nhìn qua tưởng có 2 điều kiện, nhưng phương trình thứ hai chỉ là phương trình thứ nhất nhân 2 — **nó không mang thêm thông tin nào**. Số ràng buộc **thực sự độc lập** ở đây là 1, không phải 2.

**Hạng của một ma trận** = số hàng (hoặc cột) độc lập tuyến tính thực sự — tức là sau khi khử hết các hàng "ăn theo" hàng khác (như ví dụ trên), còn lại bao nhiêu hàng. Cách tính thuật toán (con đã biết dưới tên khác): **khử Gauss** — phép biến đổi hàng con dùng để giải hệ phương trình đã học, chính là thuật toán tìm hạng.

Vì sao ta cần khái niệm này? Vì trong Vật lý, "một ràng buộc" ($g_j=0$) chỉ thực sự "đếm là 1" nếu nó **độc lập** với các ràng buộc khác — đúng như ví dụ 2 phương trình ở trên, nếu ta lỡ đếm cả 2 thì đếm sai bậc tự do. **Hạng của ma trận Jacobi** (định nghĩa ở $\S0.4$) chính là công cụ *thuật toán, không cần trực giác* để đếm số ràng buộc độc lập — đây là điều Định lý A dùng.

## 0.4 Định lý Hàm ẩn — trực giác qua đường tròn

Đây là công cụ toán quan trọng nhất của cả Chương 3 (Trụ cột A). Ta xây nó từ một ví dụ cụ thể trước khi đọc phát biểu tổng quát trong tài liệu gốc.

Xét đường tròn đơn vị: $g(x,y) := x^2+y^2-1=0$. Đây là **một** phương trình ràng buộc ($k=1$) trên **hai** biến thô $x,y$ ($N=2$). Trực giác nói: đường tròn là một đường cong 1 chiều, tức $f = N-k = 2-1=1$. Ta sẽ *chứng minh* điều "hiển nhiên" này bằng công cụ tổng quát, để thấy công cụ ấy hoạt động ra sao — vì đây đúng là cách Định lý A chứng minh trường hợp tổng quát.

Tính đạo hàm riêng của $g$: $\dfrac{\partial g}{\partial x}=2x,\quad \dfrac{\partial g}{\partial y}=2y$.

Xét điểm $(1,0)$ trên đường tròn (bên phải, ngang trục hoành). Tại đó $\partial g/\partial x = 2\neq 0$ nhưng $\partial g/\partial y = 0$. **Định lý hàm ẩn** nói: vì đạo hàm riêng theo $x$ khác 0 tại điểm này, ta có thể **giải ngược** $x$ như một hàm trơn của $y$ trong một lân cận nhỏ quanh điểm đó: $x=\varphi(y)$. Thật vậy — gần điểm $(1,0)$, với $y$ nhỏ, ta có $x=\sqrt{1-y^2}$, một hàm hoàn toàn "tử tế" (khả vi) của $y$. Vậy *gần điểm đó*, đường tròn trông giống hệt như đồ thị của một hàm số 1 biến — tức là một đường cong 1 chiều.

Bây giờ xét điểm $(0,1)$ (đỉnh trên cùng). Tại đó $\partial g/\partial x = 0$ nhưng $\partial g/\partial y = 2\neq 0$. Lần này ta phải **đổi vai trò**: giải $y$ theo $x$: $y=\sqrt{1-x^2}$. Ở điểm $(1,0)$ việc này không dùng được ($\partial g/\partial y=0$ tại đó, hàm $y(x)$ có tiếp tuyến thẳng đứng, không khả vi theo nghĩa hàm số).

**Bài học cốt lõi (sẽ dùng lại nguyên vẹn ở Định lý A):** tại **mỗi điểm**, miễn là **ít nhất một** trong các đạo hàm riêng của $g$ khác 0 — tức ma trận Jacobi (ở đây chỉ có 1 hàng $(\partial g/\partial x,\ \partial g/\partial y)$) có **hạng đầy đủ** $=k=1$ — ta luôn giải được (một cách cục bộ) một biến theo các biến còn lại, và tập nghiệm là một đường cong trơn. Việc "biến nào giải theo biến nào" có thể đổi tùy điểm, nhưng **số chiều** của tập nghiệm ($=N-k=1$) thì không đổi ở bất cứ đâu hạng Jacobi đầy đủ.

Với $N$ biến, $k$ ràng buộc, lý luận y hệt (chỉ là làm với ma trận Jacobi $k\times N$ thay vì 1 hàng): nếu ma trận này có hạng $k$ tại một điểm, ta luôn giải được $k$ biến theo $N-k$ biến còn lại **quanh điểm đó**, nên tập nghiệm là một "mặt" trơn $N-k$ chiều. Đây **chính là toàn bộ nội dung Định lý A** — con vừa tự chứng minh nó cho trường hợp $N=2,k=1$ bằng tay.

### Tự kiểm tra §0

1. Tính $\partial f/\partial x$ và $\partial f/\partial y$ với $f(x,y)=x^2y+\sin(y)$.
2. Vì sao hệ 2 phương trình $x-y=0$ và $3x-3y=6$ có hạng ma trận hệ số bằng 2 (độc lập), trong khi $x-y=0$ và $2x-2y=0$ có hạng bằng 1?
3. Trên đường tròn $x^2+y^2=1$, tại điểm $\left(\frac{\sqrt2}{2},\frac{\sqrt2}{2}\right)$, cả hai đạo hàm riêng đều khác 0. Con có thể giải cả hai cách ($x$ theo $y$ hoặc $y$ theo $x$) — hãy tự giải thích vì sao đây là điểm "tốt" hơn cả $(1,0)$ và $(0,1)$ theo nghĩa nào đó.
4. Không tính toán chi tiết, hãy đoán: với mặt cầu $x^2+y^2+z^2=1$ trong không gian ($N=3$), số ràng buộc $k=1$, thì "bề mặt" nghiệm có bao nhiêu chiều? Vì sao trực giác này khớp với việc mặt cầu là một mặt 2 chiều (dù nó "sống" trong không gian 3 chiều)?

*(Đáp án gợi ý ở cuối tài liệu, mục Phụ lục.)*

---

# CHƯƠNG 1 — CƠ HỌC LAGRANGE: NGÔN NGỮ NỀN CỦA TOÀN BỘ TÀI LIỆU

Toàn bộ tài liệu gốc (B2, B3, B4, và một nửa B5–B7) được viết bằng ngôn ngữ Lagrange, không phải ngôn ngữ Newton ($\vec F=m\vec a$) mà con quen. Đây là chương quan trọng nhất — không hiểu chương này thì không đọc được phần còn lại của tài liệu gốc.

## 1.1 Vì sao cần một ngôn ngữ khác Newton?

Newton: với mỗi vật, viết $\vec F=m\vec a$ theo từng trục tọa độ. Cách này rất tốt cho vật tự do, nhưng khi có ràng buộc (dây, thanh cứng, mặt phẳng nghiêng, con lắc kép...), lực **liên kết** (lực căng dây, phản lực) là **ẩn số chưa biết**, và ta phải viết thêm phương trình cho từng lực liên kết đó — rất cồng kềnh, dễ sai, và với hệ phức tạp thì gần như bất khả thi bằng tay.

**Ý tưởng của Lagrange:** thay vì mô tả vị trí bằng tọa độ Đề-các $(x,y,z)$ của từng vật (nhiều, và có ràng buộc giữa chúng), ta mô tả cấu hình của hệ bằng **số tọa độ tối thiểu vừa đủ** để xác định hệ — gọi là **tọa độ suy rộng**, ký hiệu $q^1,\dots,q^n$ — và các ràng buộc **biến mất khỏi phương trình một cách tự động**, vì ta đã "dùng hết" chúng ngay khi chọn $q$.

**Ví dụ:** con lắc đơn dài $l$ trong mặt phẳng. Thay vì dùng $(x,y)$ của quả nặng (2 tọa độ, cộng thêm 1 ràng buộc $x^2+y^2=l^2$), ta dùng **một** tọa độ duy nhất: góc lệch $\theta$. Ràng buộc "dây không dãn" đã được **gài sẵn** vào việc chọn $\theta$ làm biến — ta không bao giờ phải viết lực căng dây ra tường minh nữa (trừ khi câu hỏi cần chính lực căng đó).

## 1.2 Động năng, thế năng, hàm Lagrange

Với hệ có tọa độ suy rộng $q=(q^1,\dots,q^n)$:

- **Động năng** $T(q,\dot q)$: tổng $\frac12 mv^2$ của mọi vật, viết lại theo $q,\dot q$.
- **Thế năng** $V(q)$: năng lượng thế của hệ (trọng trường, đàn hồi lò xo, tĩnh điện...), viết theo $q$.
- **Hàm Lagrange**: $$L(q,\dot q, t) := T-V.$$

Đây **không phải** năng lượng ($T+V$) — dấu trừ là chủ ý, và ý nghĩa sâu xa của nó nằm ngoài phạm vi lớp 9 (liên quan nguyên lý tác dụng dừng, biến phân). Con **không cần** chứng minh tại sao $L=T-V$ "đúng" — con chỉ cần biết: **nếu** ta lập được $L$ đúng, thì phương trình chuyển động của hệ chính là:

## 1.3 Phương trình Euler–Lagrange

$$\boxed{\ \frac{d}{dt}\left(\frac{\partial L}{\partial \dot q^i}\right) = \frac{\partial L}{\partial q^i}\ } \qquad \text{với mỗi } i=1,\dots,n.$$

Đây là **quy tắc thay thế** cho $\vec F=m\vec a$: mỗi tọa độ suy rộng $q^i$ cho đúng một phương trình như trên. Ta sẽ không chứng minh công thức này (nó đến từ nguyên lý tác dụng dừng $\delta\!\int L\,dt=0$ — phần Giải tích biến phân, học ở đại học) — nhưng ta sẽ **kiểm chứng** nó bằng cách áp nó vào bài toán con đã biết chắc chắn đáp số, để thấy nó "nhả ra" đúng công thức quen thuộc.

**Kiểm chứng 1 — hạt tự do 1 chiều trong trường lực bảo toàn.** Tọa độ suy rộng: $q=x$. $T=\frac12 m\dot x^2$, $V=V(x)$, nên $L=\frac12 m\dot x^2-V(x)$.

$$\frac{\partial L}{\partial \dot x}=m\dot x \quad\Rightarrow\quad \frac{d}{dt}\left(\frac{\partial L}{\partial\dot x}\right)=m\ddot x.$$
$$\frac{\partial L}{\partial x}=-\frac{dV}{dx}=F(x)\quad(\text{định nghĩa lực từ thế năng}).$$

Euler–Lagrange cho: $m\ddot x = F(x)$ — **chính xác** định luật II Newton. Vậy Euler–Lagrange không phải "một lý thuyết khác" — nó **chứa** Newton như trường hợp riêng khi tọa độ suy rộng trùng tọa độ Đề-các.

**Kiểm chứng 2 — con lắc đơn** (bây giờ mới thấy sức mạnh thực sự: một tọa độ $\theta$, ràng buộc dây đã "biến mất"). Vận tốc quả nặng: $v=l\dot\theta$ (chuyển động tròn bán kính $l$). Chọn mốc thế năng ở điểm thấp nhất:
$$T=\frac12 m l^2\dot\theta^2,\qquad V = mgl(1-\cos\theta),\qquad L=\frac12ml^2\dot\theta^2-mgl(1-\cos\theta).$$
$$\frac{\partial L}{\partial\dot\theta}=ml^2\dot\theta\ \Rightarrow\ \frac{d}{dt}(\cdot)=ml^2\ddot\theta,\qquad \frac{\partial L}{\partial\theta}=-mgl\sin\theta.$$
Euler–Lagrange: $ml^2\ddot\theta=-mgl\sin\theta \ \Rightarrow\ \ddot\theta=-\dfrac gl\sin\theta$ — đúng phương trình con lắc đơn đã học (hoặc sẽ học), **thu được mà không cần vẽ một lực căng dây nào**. Đây chính xác là lý do tài liệu gốc dùng ngôn ngữ này: lực liên kết tự động biến mất.

## 1.4 Động lượng suy rộng $p_i$

Định nghĩa: $$p_i := \frac{\partial L}{\partial \dot q^i}.$$
Với hạt tự do Đề-các, $p=\partial L/\partial \dot x = m\dot x$ — đúng động lượng thường. Với con lắc, $p_\theta = ml^2\dot\theta$ — đây là **mô-men động lượng**, không phải động lượng thẳng — vì $q=\theta$ là một góc, không phải một độ dài. **Bài học:** "động lượng suy rộng" ứng với $q^i$ nào thì mang bản chất vật lý của chính $q^i$ đó (độ dài → động lượng thẳng; góc → mô-men động lượng).

Euler–Lagrange viết lại: $\dot p_i = \partial L/\partial q^i$. **Hệ quả tức thời (dùng suốt B4/Trụ cột C):** nếu $L$ **không chứa** $q^i$ một cách tường minh ($\partial L/\partial q^i\equiv 0$ — gọi là "**tọa độ cyclic**"), thì $\dot p_i=0$, tức $p_i$ **bảo toàn**. Đây là mầm mống đơn giản nhất của Định lý Noether — ta sẽ tổng quát hóa nó ở Chương 5.

### Bóc tách bằng Toán học (Cực kỳ hiển nhiên)

Định nghĩa động lượng suy rộng: $p_i = \frac{\partial L}{\partial \dot{q}^i}$

Phương trình Euler-Lagrange: $\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{q}^i}\right) = \frac{\partial L}{\partial q^i}$

Bây giờ, hãy thế phương trình (1) vào vế trái của phương trình (2). Ta có một phương trình mới, cực kỳ ngắn gọn: $$\frac{d}{dt}(p_i) = \frac{\partial L}{\partial q^i}$$

(Đạo hàm của động lượng theo thời gian = Đạo hàm của hàm L theo tọa độ)

Tài liệu nói: "Nếu hàm chi phí $L$ không chứa tọa độ $q^i$ một cách tường minh".


Trong ngôn ngữ giải tích, câu này có nghĩa là biến $q^i$ không xuất hiện trong biểu thức của $L$. Mà nếu $L$ không phụ thuộc vào $q^i$, thì đạo hàm riêng của $L$ theo $q^i$ bằng 0. Tức là: $$\frac{\partial L}{\partial q^i} = 0$$

Lắp số 0 này vào phương trình trên, ta được: $$\frac{d}{dt}(p_i) = 0$$

Hiển nhiên,  $p_i = \text{const}$.

### "Không chứa $q^i$ tường minh" nghĩa là gì?

Hàm Lagrange là $L = T - V$ (Động năng trừ Thế năng).

Thông thường, Động năng $T$ chỉ phụ thuộc vào vận tốc $\dot{q}$, nên việc hàm $L$ có chứa $q$ hay không hoàn toàn do thằng Thế năng $V$ quyết định.

**Ví dụ: Không gian tịnh tiến (Đi thẳng)**

Tưởng tượng ông đang thả trôi một vật trên một mặt bàn băng cực kỳ nhẵn, phẳng lỳ và rộng vô tận. Biến số $q$ ở đây là tọa độ $x$.

Dù vật ở vị trí $x = 0$ hay $x = 1000$, thế năng của nó ($V = mgh$) không hề thay đổi vì mặt bàn phẳng lỳ. Tức là $V$ không chứa biến $x$. Suy ra $L$ không chứa biến $x$.
Hệ quả: $\frac{\partial L}{\partial x} = 0 \Rightarrow$ Động lượng thẳng $p_x = mv$ được bảo toàn. Vật cứ thế trôi đi mãi mãi với vận tốc không đổi.

**Vật lý gọi đây là: Tính đồng nhất của không gian (Không gian ở đâu cũng như nhau, dời đi chỗ khác hệ vẫn không đổi).**


**Ví dụ: Không gian quay (Xoay tròn)**

Tưởng tượng ông đang quay một con quay trong môi trường chân không, không có trọng lực. Biến số $q$ ở đây là góc xoay $\theta$.
Ông có xoay toàn bộ thí nghiệm đi $30^\circ$ hay $90^\circ$, hệ thống vẫn hoạt động y hệt, năng lượng không bị thay đổi. Tức là $L$ không phụ thuộc vào góc $\theta$ ( $\theta$ là tọa độ cyclic).

Hệ quả: $\frac{\partial L}{\partial \theta} = 0 \Rightarrow$ Động lượng suy rộng tương ứng với biến góc (chính là mô-men động lượng) được bảo toàn. Con quay cứ thế quay mãi không dừng.

**Vật lý gọi đây là: Tính đẳng hướng của không gian (Không gian xoay hướng nào cũng như nhau).**

### **Định lý Noether: Trùm cuối của Vật lý Lý thuyết**

Chính từ cái mầm mống $\frac{\partial L}{\partial q^i} = 0$ vô thưởng vô phạt này, năm 1915, nữ toán học thiên tài Emmy Noether đã phát biểu một định lý làm rung chuyển cả nền vật lý, khiến cả Albert Einstein cũng phải thán phục.

Định lý Noether nói rằng: Cứ mỗi một "sự đối xứng" (Symmetry) của tự nhiên, sẽ luôn đi kèm với một "Đại lượng bảo toàn" (Conservation Law).

Không gian có đối xứng tịnh tiến (dịch chuyển không làm đổi hàm $L$) $\Rightarrow$ Bảo toàn Động lượng.

Không gian có đối xứng quay (xoay hướng không làm đổi hàm $L$) $\Rightarrow$ Bảo toàn Mô-men Động lượng.

Thời gian có đối xứng tịnh tiến (làm thí nghiệm hôm nay hay ngày mai thì quy luật vật lý vẫn thế, $L$ không phụ thuộc vào $t$) $\Rightarrow$ Bảo toàn Năng lượng.





### Tự kiểm tra §1

1. Vì sao ta nói "ràng buộc đã biến mất" khi dùng $\theta$ làm tọa độ suy rộng của con lắc đơn, thay vì $(x,y)$?
2. Viết $L$ cho một hạt khối lượng $m$ trượt không ma sát trên mặt phẳng nghiêng góc $\alpha$ cố định, tọa độ suy rộng là quãng đường $s$ dọc mặt phẳng nghiêng. Áp Euler–Lagrange, kiểm tra ra $\ddot s = g\sin\alpha$.
3. Nếu $L$ của một hệ không phụ thuộc tường minh vào $q^3$ (tọa độ suy rộng thứ 3), đại lượng nào bảo toàn? Vì sao?
4. Động lượng suy rộng ứng với một tọa độ góc có thứ nguyên gì? Có giống thứ nguyên của $mv$ không?

---

# CHƯƠNG 2 — B0 & B1: ĐỌC ĐỀ VÀ CHỌN HỆ (phần thực hành, ít lý thuyết mới)

Phần **B0** và phần đầu **B1** trong tài liệu gốc gần như không cần toán mới — đó là kỷ luật đọc đề, và con có thể đọc trực tiếp tài liệu gốc, làm theo đúng 5 bước của B0 (gạch chân dữ kiện, quét hình có hệ thống, lập bảng biến số, tự vẽ lại hình, không tự thêm/bớt giả thiết). Đây thuần túy là **thói quen làm việc cẩn thận**, không phải kiến thức Vật lý — hãy tập luyện nó trên **mọi** bài, kể cả bài dễ, cho đến khi nó tự động.

Điều duy nhất cần giải thích thêm ở B1 là câu: *"đôi khi coi toàn bộ nhiều vật là một hệ... đôi khi phải tách ra"*. Đây chính là lựa chọn **tọa độ suy rộng** mà ta vừa học ở Chương 1: coi "toàn hệ" là một hệ nghĩa là dùng ít tọa độ suy rộng nhất có thể (nội lực chưa biết giữa các vật tự động biến mất khỏi phương trình, giống lực căng dây trong con lắc); "tách ra" nghĩa là ta cố tình giữ lại một số tọa độ dư để **lộ ra** một lực nội tại mà chính đề bài đang hỏi (ví dụ: đề hỏi lực căng dây thì không được "gộp" hệ theo cách làm biến mất lực căng đó).

**Vấn đề phát sinh 0** mà tài liệu gốc đặt ra ("liệu chọn hệ quy chiếu như vậy đã đủ chưa?") sẽ tự động được trả lời khi con thành thạo Chương 3 — vì việc chọn hệ quy chiếu đúng đắn chính là điều kiện để đếm bậc tự do (B2) cho ra kết quả đúng. Ta quay lại câu hỏi này ở cuối Chương 3.

---

# CHƯƠNG 3 — TRỤ CỘT A: BẬC TỰ DO & ĐỊNH LÝ A

## 3.1 Bậc tự do là gì — xây từ ví dụ, không từ định nghĩa

**Bậc tự do (DOF)** của một hệ = số con số **độc lập** cần cho để xác định hoàn toàn cấu hình (vị trí mọi bộ phận) tại một thời điểm.

- 1 chất điểm tự do trong không gian: cần $(x,y,z)$ → $f=3$.
- 1 chất điểm bị buộc di chuyển trên một mặt phẳng cố định: cần 2 số (tọa độ trong mặt phẳng đó) → $f=2$. Ta vừa **mất** 1 bậc tự do vì có 1 ràng buộc ("$z=0$", một phương trình).
- 1 chất điểm bị buộc di chuyển trên một đường tròn bán kính $R$ cố định trong mặt phẳng: cần đúng 1 số (góc $\theta$) → $f=1$. Ràng buộc $x^2+y^2=R^2$ — đúng là ví dụ đường tròn ở $\S0.4$! Ta đã *chứng minh bằng tay* rằng tập nghiệm này là 1 chiều.
- 2 chất điểm tự do, nối bằng 1 thanh cứng dài $L$ (mô hình "quả tạ"): thô có $N=6$ tọa độ ($\vec r_1,\vec r_2$ trong 3D), ràng buộc $|\vec r_1-\vec r_2|=L$ là **1** phương trình → $f=6-1=5$ (3 tọa độ khối tâm + 2 góc định hướng thanh trong không gian; không có góc quay quanh trục thanh vì 2 chất điểm không "cảm" được góc đó).

**Quan sát chốt:** mỗi phương trình ràng buộc **độc lập** làm $f$ giảm đúng 1 — miễn là ta kiểm tra được tính độc lập đó bằng **hạng ma trận Jacobi** ($\S0.3$–$0.4$), không phải bằng cảm giác.

## 3.2 Định lý A — phát biểu lại, giờ đã có đủ công cụ

Bây giờ đọc lại **Định lý A** trong tài liệu gốc (Phần 2, $\S2.2$). Mọi ký hiệu trong đó con đã biết:

- "$N$ tọa độ thô $x\in\mathbb R^N$" = các tọa độ Đề-các thô của mọi vật trong hệ, chưa rút gọn gì cả (ví dụ với quả tạ 2 chất điểm: $N=6$).
- "$k$ hàm ràng buộc toàn chỉnh $g_j(x,t)=0$" = các phương trình ràng buộc, đúng như $g(x,y)=x^2+y^2-1$ ở $\S0.4$, chỉ tổng quát hóa lên nhiều biến, nhiều phương trình, và có thể phụ thuộc $t$ (ràng buộc thay đổi theo thời gian, ví dụ dây đang được kéo ngắn dần).
- "**hạng đầy đủ $k$**" = đúng khái niệm hạng ở $\S0.3$: $k$ phương trình đó **thực sự độc lập** (không có phương trình nào "ăn theo" phương trình khác, như ví dụ $2x+2y+2z=0$ ăn theo $x+y+z=0$).
- Kết luận $\dim Q_t = N-k=f$ — và **chứng minh** trong tài liệu gốc chính là **đúng lý luận đường tròn** ở $\S0.4$, chỉ viết cho $N,k$ tổng quát thay vì $N=2,k=1$: sắp lại thứ tự để $k$ biến cuối có ma trận con $k\times k$ khả nghịch (đó là điều kiện hạng đầy đủ), rồi Định lý Hàm ẩn giải $k$ biến đó theo $N-k$ biến còn lại.

Con hãy tự đọc lại phần chứng minh trong tài liệu gốc **một lần nữa ngay bây giờ** — nó sẽ đọc như một bài toán quen thuộc, không còn là ký hiệu xa lạ.

**Vì sao Định lý A "hoàn toàn tổng quát và thuật toán":** vì tính hạng của một ma trận là đại số tuyến tính máy móc (khử Gauss) — không cần "nhìn ra" bậc tự do bằng trực giác hình học nữa, chỉ cần liệt kê đúng các $g_j$ rồi tính hạng.

## 3.3 Quy tắc thực hành — Fact 18 tổng quát hóa

$$f_{\text{eff}} = f_{\text{raw}} - (\text{số ràng buộc độc lập ở B3}) - (\text{số bảo toàn/đối xứng ở B4}).$$

Vế đầu ($f_{\text{raw}}-\text{ràng buộc}$) chính là Định lý A. Vế "trừ thêm số bảo toàn" là điều **mới**, chưa giải thích — vì sao một định luật bảo toàn (không phải một ràng buộc hình học!) cũng làm giảm số bậc tự do *hiệu dụng* cần giải? Đây là câu hỏi Chương 5 (Trụ cột C) trả lời: một định luật bảo toàn cho ta **một phương trình đại số** (chứ không phải vi phân) liên hệ giữa các biến — về mặt "số phương trình cần giải thêm", nó có tác dụng y hệt một ràng buộc, dù bản chất vật lý hoàn toàn khác (ràng buộc là hình học có sẵn từ đầu bài; bảo toàn là hệ quả ta *suy ra* từ đối xứng). Ghi nhớ điều này, ta sẽ quay lại chính xác câu này ở cuối Chương 5.

## 3.4 Trả lời "Vấn đề phát sinh 0 và 1" của tài liệu gốc

- **Vấn đề phát sinh 0** (chọn hệ quy chiếu đã đủ tốt chưa?): với Định lý A trong tay, câu trả lời thực hành là — hệ quy chiếu "đủ tốt" khi các tọa độ thô $x$ mà con chọn khiến **mọi** ràng buộc vật lý viết được thành $g_j(x,t)=0$ **tường minh** (không ẩn trong lời văn). Nếu con thấy mình phải "đoán" một ràng buộc mà không viết ra được phương trình, đó là dấu hiệu hệ quy chiếu/tọa độ thô chưa đủ tốt — quay lại B0, quét lại đề.
- **Vấn đề phát sinh 1** ("loại khớp nối nào áp dụng"): đây chính là bảng Từ điển B3 trong tài liệu gốc (không nằm trong đoạn con thấy, nhưng được nhắc tới) — với mỗi loại khớp nối vật lý (bản lề, con lăn, dây qua ròng rọc, tiếp xúc không trượt...), luôn viết được thành **đúng một** phương trình $g=0$ (hoặc bất phương trình, xem Chương 4). Kỹ năng "không bị bất ngờ tại IPhO/VPhO" không đến từ việc thuộc lòng mọi loại khớp nối có thể có trên đời — mà đến từ **phép kiểm tra gốc** mà tài liệu gốc nêu ở đầu Phần 3: dùng **dịch chuyển ảo** — tưởng tượng hệ nhích một lượng vi phân, hỏi "đại lượng nào buộc phải không đổi" — và viết chính đại lượng đó $=$ hằng số làm phương trình $g=0$. Đây là một thuật toán, áp dụng được cho *bất kỳ* khớp nối nào, quen hay lạ.

### Tự kiểm tra §3

1. Một con lắc kép phẳng (2 thanh cứng nối tiếp, khớp bản lề tại 2 điểm) — thô có bao nhiêu tọa độ nếu mô tả bằng vị trí 2 đầu thanh dưới dạng $(x_1,y_1,x_2,y_2)$? Có bao nhiêu ràng buộc độc lập (độ dài từng thanh không đổi)? $f_{\text{eff}}$ bằng bao nhiêu? Đối chiếu với việc chọn trực tiếp 2 góc $\theta_1,\theta_2$ làm tọa độ suy rộng — có khớp không?
2. Giải thích bằng lời của con: tại sao "số ràng buộc độc lập" phải dùng khái niệm hạng ma trận Jacobi, thay vì chỉ đếm số câu ràng buộc trong đề bài?
3. Dùng phép dịch chuyển ảo, tự suy ra phương trình ràng buộc cho "hai bánh răng ăn khớp, bán kính $R_1,R_2$, quay với góc $\theta_1,\theta_2$" mà không cần biết trước công thức.

---

# CHƯƠNG 4 — TRỤ CỘT B: RÀNG BUỘC HOLONOMIC/NON-HOLONOMIC & ĐỊNH LÝ B (FROBENIUS)

Đây là phần toán "lạ" nhất trong toàn bộ tài liệu gốc — **dạng vi phân** và **tích ngoài** ($\wedge$). Nó thuộc Hình học vi phân (đại học), nhưng ta chỉ cần một mảnh rất nhỏ, và ta sẽ xây nó hoàn toàn từ vi phân $df$ mà con đã biết ở $\S0.1$.

## 4.1 Từ $df$ đến "dạng vi phân bậc 1"

Nhắc lại $\S0.1$: $df = \dfrac{\partial f}{\partial x}dx+\dfrac{\partial f}{\partial y}dy$. Đại lượng $df$ là một biểu thức **tuyến tính** theo $dx,dy$ — với mỗi hướng dịch chuyển nhỏ $(dx,dy)$, nó cho ra một số (lượng $f$ thay đổi).

Bây giờ, ta **tổng quát hóa**: một biểu thức bất kỳ có dạng
$$\omega = A(x,y)\,dx + B(x,y)\,dy$$
(với $A,B$ là hai hàm tùy ý, **không nhất thiết** là $\partial f/\partial x,\partial f/\partial y$ của một hàm $f$ nào đó) được gọi là một **dạng vi phân bậc 1** (hay dạng Pfaff). Nó **trông giống** $df$, nhưng có thể **không phải** vi phân toàn phần của bất kỳ hàm $f$ nào — đây chính là mấu chốt của cả chương.

**Vì sao ta quan tâm?** Vì một ràng buộc vận tốc tổng quát luôn viết được dưới dạng $\omega=0$: ví dụ ràng buộc lăn không trượt $\dot x = R\dot\theta$ viết lại (nhân 2 vế với $dt$) thành $dx - R\,d\theta=0$, tức $\omega=dx-R\,d\theta$ với $A=1,B=-R$.

**Câu hỏi trung tâm của Trụ cột B:** khi nào một ràng buộc dạng $\omega=0$ như vậy có thể **tích phân được** thành một phương trình đại số $F(x,y)=\text{const}$ (holonomic — ràng buộc *vị trí*, làm giảm bậc tự do thật sự), và khi nào thì **không** (non-holonomic — chỉ ràng buộc *vận tốc tức thời*, không làm giảm số chiều không gian cấu hình)?

Nếu $\omega = df$ đúng là vi phân toàn phần của một hàm $f$ nào đó, thì $\omega=0 \Leftrightarrow df=0 \Leftrightarrow f=\text{const}$ — tích phân được ngay, đó là trường hợp dễ. Vấn đề là: cho $A,B$ bất kỳ, **làm sao biết** (không cần đoán, không cần "nhìn ra" $f$) liệu có tồn tại một hàm $f$ (có thể sau khi nhân $\omega$ với một "thừa số tích phân" $\mu(x,y)$) sao cho $\mu\omega=df$?

## 4.2 Tích ngoài $\wedge$ — xây từ diện tích có hướng

Ta cần một phép "nhân" hai vi phân cơ bản $dx,dy$ lại với nhau, gọi là **tích ngoài**, ký hiệu $\wedge$, có đúng 2 quy tắc:

$$dx\wedge dy = -\,dy\wedge dx \qquad\text{(phản đối xứng)}, \qquad dx\wedge dx = 0.$$

Con đã thấy **đúng hai quy tắc này** ở $\S0.2$ với tích có hướng $\vec a\times\vec b=-\vec b\times\vec a$ và $\vec a\times\vec a=0$! Đây không phải trùng hợp: $dx\wedge dy$ đo "diện tích có hướng" quét bởi hai vi-dịch-chuyển $dx$ và $dy$ — hệt như $\vec a\times\vec b$ đo diện tích có hướng của hình bình hành — chỉ khác là $\wedge$ hoạt động trên các **vi phân** (đối tượng "đo lường hướng nhích") thay vì trên vector không gian. Vì phản đối xứng, tích ngoài của 3 vi phân hoán vị vòng tròn cũng không đổi dấu — **đúng tính chất tích hỗn tạp** ở $\S0.2$ mà con đã kiểm tra. Toàn bộ Chương 4 và một phần Chương 5(c) đều dùng chung một "mầm" đại số này.

Với dạng bậc 1 $\omega = A\,dx+B\,dy$ (2 biến), tích ngoài của $\omega$ với chính vi phân của $A,B$ sẽ tự động chỉ còn số hạng $dx\wedge dy$ (vì $dx\wedge dx=dy\wedge dy=0$).

## 4.3 Đạo hàm ngoài $d$ của một dạng bậc 1

Định nghĩa (đây thuần túy là **áp lại quy tắc vi phân $\S0.1$ cho từng hệ số**, rồi nhân ngoài):
$$d\omega := dA\wedge dx + dB\wedge dy = \left(\frac{\partial A}{\partial x}dx+\frac{\partial A}{\partial y}dy\right)\wedge dx + \left(\frac{\partial B}{\partial x}dx+\frac{\partial B}{\partial y}dy\right)\wedge dy.$$
Dùng $dx\wedge dx=dy\wedge dy=0$ và $dy\wedge dx=-dx\wedge dy$:
$$d\omega = \frac{\partial A}{\partial y}(dy\wedge dx) + \frac{\partial B}{\partial x}(dx\wedge dy) = \left(\frac{\partial B}{\partial x}-\frac{\partial A}{\partial y}\right)dx\wedge dy.$$

**Sự kiện chốt (con nên tự kiểm chứng bằng cách thay $A=\partial f/\partial x, B=\partial f/\partial y$):** nếu $\omega=df$ với $f$ nào đó, thì $d\omega=0$ **luôn luôn** — vì $\partial B/\partial x = \partial^2f/\partial x\partial y = \partial^2 f/\partial y\partial x=\partial A/\partial y$ (đạo hàm riêng hỗn hợp không phụ thuộc thứ tự lấy đạo hàm — sự kiện con có thể kiểm tra bằng vài ví dụ cụ thể như $f=x^2y$). Đây là lý do "$d\omega=0$" là **điều kiện cần** để $\omega$ tích phân được — và với 2 biến, nó cũng **đủ** (đại học gọi là bổ đề Poincaré cục bộ). Nhưng khi có **từ 3 biến trở lên**, $d\omega=0$ không còn là câu hỏi đúng nữa — cần điều kiện Định lý B: $\omega\wedge d\omega=0$.

## 4.4 Định lý B (tiêu chuẩn Frobenius) — bây giờ đọc tài liệu gốc

Bây giờ con đã có đủ công cụ để đọc **nguyên văn** Định lý B trong tài liệu gốc: *"$\omega=\sum_i A_i\,dq^i+A_t\,dt=0$ là toàn chỉnh khi và chỉ khi $\omega\wedge d\omega=0$."* Đây chỉ là việc lặp lại chính xác $\S4.2$–$4.3$ nhưng với $n\geq 3$ biến thay vì 2 — với nhiều biến hơn, $d\omega$ có thể chứa các số hạng $dq^i\wedge dq^j$ ($i\neq j$) mà **không** tự động triệt tiêu khi nhân ngoài thêm một lần $\omega$ nữa — và chính "phần dư" đó đo mức độ "không tích phân được".

**Bây giờ ta làm lại từng bước hai ví dụ của tài liệu gốc, viết đầy đủ mọi số hạng (tài liệu gốc chỉ ghi tắt "tính trực tiếp"):**

**Ví dụ B.1 — đĩa lăn không trượt trên đường thẳng (holonomic).** $\omega = dx - R\,d\theta$ ($R$ là hằng số, bán kính đĩa). Vì hệ số của $dx$ là hằng số $1$ và hệ số của $d\theta$ là hằng số $-R$ — cả hai đều **không phụ thuộc** $x,\theta$ — nên mọi đạo hàm riêng của các hệ số này bằng 0, suy ra $d\omega=0$ (áp $\S4.3$: $d\omega = d(1)\wedge dx - d(R)\wedge d\theta = 0-0=0$, vì vi phân của một hằng số luôn bằng 0). Vậy $\omega\wedge d\omega=\omega\wedge 0=0$ — **tự động thỏa mãn Định lý B**. Ràng buộc toàn chỉnh, tích phân trực tiếp ra $x-R\theta=\text{const}$ — một phương trình **đại số** bình thường, dùng được ngay như một ràng buộc vị trí thông thường.

**Ví dụ B.2 — "xe một bánh"/đĩa lăn tự do đổi hướng (non-holonomic).** Cấu hình $(x,y,\theta)$ ($\theta$ là góc hướng của xe). Ràng buộc "không trượt ngang" (vận tốc luôn dọc theo hướng xe đang chỉ): $-\sin\theta\,dx+\cos\theta\,dy=0$, tức $\omega=-\sin\theta\,dx+\cos\theta\,dy$ (không có số hạng $d\theta$, hệ số của nó bằng 0).

*Bước 1 — tính $d\omega$:* áp $\S4.3$ mở rộng cho 3 biến $(x,y,\theta)$: hệ số của $dx$ là $A=-\sin\theta$ (phụ thuộc $\theta$!), hệ số của $dy$ là $B=\cos\theta$ (cũng phụ thuộc $\theta$), hệ số của $d\theta$ là $C=0$.
$$d\omega = dA\wedge dx + dB\wedge dy = (-\cos\theta\,d\theta)\wedge dx + (-\sin\theta\,d\theta)\wedge dy = -\cos\theta\,(d\theta\wedge dx)-\sin\theta\,(d\theta\wedge dy).$$
(Khớp đúng công thức tài liệu gốc ghi.)

*Bước 2 — tính $\omega\wedge d\omega$, khai triển đủ 4 số hạng (đây là phần tài liệu gốc lược bỏ, ta làm chi tiết):*
$$\omega\wedge d\omega = (-\sin\theta\,dx+\cos\theta\,dy)\wedge\big(-\cos\theta\,d\theta\wedge dx-\sin\theta\,d\theta\wedge dy\big).$$
Nhân phân phối ra 4 số hạng:

- $(-\sin\theta\,dx)\wedge(-\cos\theta\,d\theta\wedge dx) = \sin\theta\cos\theta\,(dx\wedge d\theta\wedge dx) = 0$ (chứa $dx$ hai lần).
- $(-\sin\theta\,dx)\wedge(-\sin\theta\,d\theta\wedge dy) = \sin^2\theta\,(dx\wedge d\theta\wedge dy)$. Sắp lại thứ tự chuẩn $dx\wedge dy\wedge d\theta$: đổi chỗ $d\theta$ và $dy$ (1 phép hoán đổi, đổi dấu 1 lần) cho $dx\wedge d\theta\wedge dy = -\,dx\wedge dy\wedge d\theta$. Vậy số hạng này $=-\sin^2\theta\,(dx\wedge dy\wedge d\theta)$.
- $(\cos\theta\,dy)\wedge(-\cos\theta\,d\theta\wedge dx) = -\cos^2\theta\,(dy\wedge d\theta\wedge dx)$. Đây là hoán vị **vòng tròn** của $(dx,dy,d\theta)$ — như $\S0.2$/$\S4.2$ đã chỉ ra, hoán vị vòng không đổi dấu: $dy\wedge d\theta\wedge dx = dx\wedge dy\wedge d\theta$. Vậy số hạng này $=-\cos^2\theta\,(dx\wedge dy\wedge d\theta)$.
- $(\cos\theta\,dy)\wedge(-\sin\theta\,d\theta\wedge dy)=-\sin\theta\cos\theta\,(dy\wedge d\theta\wedge dy)=0$ (chứa $dy$ hai lần).

Cộng lại: $\omega\wedge d\omega = \big[-\sin^2\theta-\cos^2\theta\big]\,dx\wedge dy\wedge d\theta = -\,dx\wedge dy\wedge d\theta \neq 0$.

**Kết luận:** $\omega\wedge d\omega\neq 0$ — **không toàn chỉnh** theo đúng tiêu chuẩn Định lý B. Về mặt vật lý: dù *tại mỗi thời điểm* xe chỉ có thể lăn dọc theo hướng nó đang chỉ (1 bậc tự do vận tốc khả dĩ trong không gian vận tốc 3 chiều $(\dot x,\dot y,\dot\theta)$), nhưng **quỹ đạo tích lũy** qua thời gian vẫn có thể đưa xe đến **bất kỳ** cấu hình $(x,y,\theta)$ nào khác — đây chính là lý do vật lý tại sao "đỗ xe song song" (dịch ngang được dù bánh xe không trượt ngang tức thời) khả thi: không gian *cấu hình* $\mathcal Q$ không bị ràng buộc thu hẹp (vẫn 3 chiều), dù không gian *vận tốc tức thời* tại mỗi điểm bị thu hẹp còn 1 chiều.

## 4.5 Khi ràng buộc hình học "quá nhiều" — hệ siêu tĩnh

Đọc thêm đoạn "Quan sát quan trọng" cuối Phần 3 tài liệu gốc: nếu số ràng buộc lý tưởng hóa (dây/thanh tuyệt đối cứng) vượt quá số bậc tự do thực, hạng ma trận Jacobi không thể đạt "đầy đủ $k$" theo đúng cách hiểu ở Định lý A — hệ **siêu tĩnh** (statically indeterminate). Lối ra: nới lỏng giả thiết "cứng tuyệt đối" thành mô hình đàn hồi (định luật Hooke, độ cứng $k=AY/L$ với $Y$ là suất đàn hồi Young) — biến một ràng buộc "cứng" ($=0$ tuyệt đối) thành một **phương trình vật lý thêm** (lực tỉ lệ biến dạng), đóng kín hệ phương trình. Đây là ứng dụng thực tế, không cần thêm lý thuyết mới — chỉ cần nhận ra *khi nào* mô hình "vật rắn tuyệt đối" đã hết dùng được.

### Tự kiểm tra §4

1. Giải thích bằng lời (không dùng công thức) sự khác biệt giữa "ràng buộc trên vị trí" (holonomic) và "ràng buộc trên vận tốc mà không tích phân được" (non-holonomic), dùng chính ví dụ xe/đĩa lăn.
2. Vì sao $dx\wedge dx=0$ lại tương ứng với "một hình bình hành có hai cạnh trùng nhau thì diện tích bằng 0"?
3. Tự làm lại phép tính $\omega\wedge d\omega$ ở Ví dụ B.2, nhưng lần này không nhìn tài liệu, chỉ nhìn $\omega=-\sin\theta\,dx+\cos\theta\,dy$ — mục tiêu là tự tay ra được $-dx\wedge dy\wedge d\theta$.
4. Một quả cầu lăn không trượt trên một mặt phẳng (không chỉ đĩa 2D mà là quả cầu 3D, có thể đổi hướng lăn) — đây có phải là ràng buộc holonomic không? Dự đoán trước (không cần chứng minh đầy đủ) dựa trên trực giác vừa học.

---

# CHƯƠNG 5 — TRỤ CỘT C: ĐỐI XỨNG & ĐỊNH LÝ NOETHER

## 5.1 Trực giác trước — đối xứng sinh ra bảo toàn như thế nào

Ở $\S1.4$ con đã thấy mầm mống: nếu $L$ không chứa $q^i$ tường minh (tọa độ cyclic) thì $p_i$ bảo toàn. "Không chứa $q^i$" nghĩa là gì về mặt hình học? Nghĩa là: nếu ta **dịch** $q^i \to q^i+\varepsilon$ (một hằng số nhỏ $\varepsilon$ bất kỳ) mà giữ mọi tọa độ khác nguyên, thì $L$ **không đổi** — hệ "trông y hệt như trước" dưới phép dịch chuyển đó. Đây chính xác là câu tài liệu gốc mở đầu Phần 4: *"nếu tồn tại một phép biến đổi liên tục làm cho toàn cảnh vật lý trông y hệt như trước, thì tồn tại một đại lượng bảo toàn tương ứng."*

Định lý Noether (Định lý C1) chỉ **tổng quát hóa** phép dịch chuyển đơn giản "$q^i\to q^i+\varepsilon$" thành phép biến đổi **bất kỳ** dạng $q^i \to q^i + \varepsilon X^i(q,t)$, với $X^i$ là một hàm bất kỳ (không nhất thiết hằng số) mô tả "hệ dịch chuyển theo hướng nào, nhiều ít ra sao tùy vị trí". Việc "trông y hệt như trước" được đo bằng: $L$ không đổi (đến bậc nhất theo $\varepsilon$) dưới phép biến đổi này.

## 5.2 Định lý C1 — đọc từng ký hiệu

Trước khi đọc chứng minh, hãy chắc con hiểu **từng mảnh ký hiệu** trong phát biểu Định lý C1 (tài liệu gốc $\S4.1$):

- $X=(X^1,\dots,X^n)$: một "trường hướng dịch chuyển" — ứng với mỗi điểm cấu hình $q$ (và có thể mỗi thời điểm $t$), $X$ cho biết "nếu biến đổi thì $q^i$ nhích theo hướng/tỉ lệ nào". Phép biến đổi cụ thể: $q^i\mapsto q^i+\varepsilon X^i(q,t)$, với $\varepsilon$ nhỏ.
- $\dfrac{dX^i}{dt} := \dfrac{\partial X^i}{\partial t}+\displaystyle\sum_j\dfrac{\partial X^i}{\partial q^j}\dot q^j$ — đây **chính xác** là công thức quy tắc dây chuyền ở $\S0.1$ (tốc độ thay đổi của $X^i$ dọc theo chuyển động thật của hệ, vì $q^j=q^j(t)$).
- Điều kiện $(*)$: $\displaystyle\sum_i\left[\frac{\partial L}{\partial q^i}X^i + \frac{\partial L}{\partial\dot q^i}\frac{dX^i}{dt}\right]=0$ **với mọi** $(q,\dot q,t)$ — không chỉ dọc theo nghiệm thật. Đây chính là "$L$ không đổi đến bậc nhất $\varepsilon$" — nếu con thay $q\to q+\varepsilon X$, $\dot q \to \dot q+\varepsilon\,dX/dt$ vào $L$ và khai triển Taylor bậc nhất theo $\varepsilon$ (giống hệt vi phân toàn phần $\S0.1$, nhưng "biến" bây giờ là $q,\dot q$ thay vì $x,y$), số hạng bậc $\varepsilon^1$ chính xác là biểu thức trong $(*)$.
- $I = \displaystyle\sum_i \frac{\partial L}{\partial \dot q^i}X^i = \sum_i p_i X^i$ — **đại lượng bảo toàn**, là tổng "động lượng suy rộng nhân với hướng dịch chuyển tương ứng".

**Chứng minh (dùng lại đúng Euler–Lagrange $\S1.3$ và quy tắc dây chuyền $\S0.1$, không có gì mới):**
$$\frac{dI}{dt} = \sum_i\left[\frac{d}{dt}\left(\frac{\partial L}{\partial\dot q^i}\right)X^i + \frac{\partial L}{\partial\dot q^i}\frac{dX^i}{dt}\right].$$
Thay $\dfrac{d}{dt}\Big(\dfrac{\partial L}{\partial\dot q^i}\Big) = \dfrac{\partial L}{\partial q^i}$ (đúng Euler–Lagrange $\S1.3$):
$$\frac{dI}{dt} = \sum_i\left[\frac{\partial L}{\partial q^i}X^i + \frac{\partial L}{\partial\dot q^i}\frac{dX^i}{dt}\right] \stackrel{(*)}{=} 0.$$
Vậy $I=$ const dọc mọi nghiệm thật của hệ. Toàn bộ chứng minh chỉ là: **thay Euler–Lagrange vào, rồi nhận ra biểu thức thu được đúng bằng vế trái của $(*)$, vốn bằng 0 theo giả thiết.**

## 5.3 Bốn hệ quả — mỗi cái là một trường hợp riêng của C1

**(a) Tọa độ cyclic $\Rightarrow p_1$ bảo toàn** (đúng $\S1.4$, giờ là trường hợp riêng): chọn $X=(1,0,\dots,0)$ (hằng số, không phụ thuộc $q,t$), nên $dX^i/dt=0$. Điều kiện $(*)$ trở thành $\partial L/\partial q^1 = 0$ — đúng giả thiết "cyclic". $I=\partial L/\partial\dot q^1=p_1$.

**(b) Đối xứng tịnh tiến toàn hệ $\Rightarrow$ tổng động lượng bảo toàn.** Xét $n$ chất điểm, $L=\sum_i\frac12 m_i|\dot{\vec r}_i|^2 - V(\vec r_1,\dots,\vec r_n)$, với $V$ chỉ phụ thuộc **hiệu** vị trí từng cặp (ví dụ lực hấp dẫn/Hooke giữa các hạt — không phụ thuộc "hạt đang ở đâu trong không gian tuyệt đối", chỉ phụ thuộc khoảng cách tương đối). Cho **mọi** hạt cùng dịch theo một hướng cố định $\hat n$: $X_i=\hat n$ (cùng vector hằng cho mọi $i$). Vì $V$ chỉ phụ thuộc hiệu vị trí, dịch tất cả các hạt cùng một lượng theo $\hat n$ không đổi $V$ — đạo hàm theo $\varepsilon$ tại $\varepsilon=0$ của điều đó chính là $\sum_i\nabla_i V\cdot\hat n=0$, và số hạng động năng không đóng góp gì thêm (vì $X$ hằng số, $dX/dt=0$) — đây đúng là điều kiện $(*)$. Vậy $I=\sum_i m_i\dot{\vec r}_i\cdot\hat n$ bảo toàn với **mọi** $\hat n$, suy ra $\vec P=\sum_i m_i\dot{\vec r}_i=$ const.

**(c) Đối xứng quay toàn hệ $\Rightarrow$ mô-men động lượng bảo toàn.** Lấy $X_i(\vec r)=\hat n\times\vec r_i$ — đây là công thức chuẩn cho "vận tốc của một điểm khi toàn hệ quay vi phân quanh trục $\hat n$" (con có thể kiểm tra: quay một vector $\vec r$ một góc nhỏ $d\phi$ quanh trục $\hat n$ làm nó dịch một lượng $d\phi\,(\hat n\times\vec r)$ — đây là công thức vận tốc dài trong chuyển động quay mà con đã biết, $\vec v=\vec\omega\times\vec r$, chỉ viết cho độ dịch chuyển vi phân thay vì vận tốc). Vì $X_i$ phụ thuộc tuyến tính vào $\vec r_i(t)$, $dX_i/dt = \hat n\times\dot{\vec r}_i$.

Với $V$ chỉ phụ thuộc khoảng cách $|\vec r_i-\vec r_j|$ (bất biến khi quay cả hệ), lý luận y hệt (b) cho $\sum_i\nabla_i V\cdot(\hat n\times\vec r_i)=0$. Với số hạng động năng, đây là chỗ dùng **đúng** tính chất tích hỗn tạp ở $\S0.2$:
$$\sum_i m_i\dot{\vec r}_i\cdot(\hat n\times\dot{\vec r}_i) = \sum_i m_i\,\hat n\cdot(\dot{\vec r}_i\times\dot{\vec r}_i) = 0,$$
(dùng hoán vị vòng $\vec a\cdot(\vec b\times\vec c)=\vec b\cdot(\vec c\times\vec a)$ với $\vec a=\dot{\vec r}_i,\vec b=\hat n,\vec c=\dot{\vec r}_i$, rồi $\vec r\times\vec r=\vec 0$). Vậy $(*)$ thỏa mãn tự động, và
$$I = \sum_i m_i\dot{\vec r}_i\cdot(\hat n\times\vec r_i) \overset{\text{hoán vị vòng}}{=} \sum_i m_i\,\hat n\cdot(\vec r_i\times\dot{\vec r}_i) = \hat n\cdot\vec L_{\text{tổng}}$$
bảo toàn với mọi $\hat n$ $\Rightarrow \vec L_{\text{tổng}}=$ const.

**(d) Đối xứng tịnh tiến thời gian $\Rightarrow$ năng lượng bảo toàn.** Trường hợp này khác 3 trường hợp trên — ta biến đổi chính $t$, không phải $q$. Định nghĩa $H:=\sum_i\dot q^i\dfrac{\partial L}{\partial\dot q^i}-L = \sum_i \dot q^i p_i - L$ (gọi là **hàm Hamilton**). Tính đạo hàm theo thời gian dọc nghiệm thật, dùng Euler–Lagrange và quy tắc dây chuyền cho $L(q,\dot q,t)$:
$$\frac{dH}{dt}=\sum_i\Big[\ddot q^i p_i + \dot q^i \dot p_i\Big] - \frac{dL}{dt}.$$
M� $\dfrac{dL}{dt}=\sum_i\Big[\dfrac{\partial L}{\partial q^i}\dot q^i+\dfrac{\partial L}{\partial \dot q^i}\ddot q^i\Big]+\dfrac{\partial L}{\partial t} = \sum_i[\dot p_i \dot q^i + p_i\ddot q^i]+\dfrac{\partial L}{\partial t}$ (dùng $\partial L/\partial q^i=\dot p_i$). Thay vào, hai tổng triệt tiêu nhau hoàn toàn, còn lại:
$$\frac{dH}{dt} = -\frac{\partial L}{\partial t}.$$
Vậy **nếu $L$ không phụ thuộc tường minh $t$** (đối xứng tịnh tiến thời gian — không có ngoại lực nào "tự thay đổi theo đồng hồ"), $H=$ const.

Khi thế năng $V$ không phụ thuộc $\dot q$ và động năng $T$ có dạng toàn phương thuần túy theo $\dot q$ (trường hợp chuẩn, ràng buộc không phụ thuộc $t$ — gọi là *scleronomic*), ta dùng **định lý Euler cho hàm thuần nhất**: nếu $T(q,\lambda\dot q)=\lambda^2 T(q,\dot q)$ với mọi $\lambda$ (đúng vì $T$ toàn phương theo $\dot q$), lấy đạo hàm hai vế theo $\lambda$ rồi cho $\lambda=1$:
$$\sum_i \dot q^i\frac{\partial T}{\partial \dot q^i} = 2T.$$
(Con có thể tự kiểm tra với $T=\frac12 m\dot x^2$: vế trái $=\dot x\cdot m\dot x = m\dot x^2=2T$ — đúng.) Vì $V$ không chứa $\dot q$, $\partial L/\partial\dot q^i=\partial T/\partial\dot q^i$, nên $H=\sum\dot q^i p_i - L = 2T-(T-V)=T+V=E$ — đúng năng lượng cơ học quen thuộc.

## 5.4 Bảng C và vì sao danh sách đối xứng là hữu hạn

Đọc lại Bảng C trong tài liệu gốc — mỗi dòng giờ đã là một trường hợp cụ thể của (a)–(d) con vừa tự tay chứng minh. Lý do Bảng C **đầy đủ** (không sót đối xứng "ẩn" nào) với thư viện lực chuẩn IPhO: mọi thế năng trong chương trình chỉ phụ thuộc (i) khoảng cách từng cặp hạt — loại này chỉ bất biến dưới đúng nhóm phép quay + tịnh tiến (không có phép biến đổi liên tục nào khác giữ nguyên $|\vec r_i-\vec r_j|$, vì khoảng cách là bất biến duy nhất của phép đẳng cự không gian), hoặc (ii) vị trí qua một trường ngoài **đều** — chỉ bất biến dưới tịnh tiến trong mặt phẳng vuông góc trường. Đây là lý do việc "săn đối xứng" ở B4 chỉ cần thử một danh sách hữu hạn phép biến đổi (Bảng C), không phải "đoán mò" trong vô số khả năng.

**Cảnh báo quan trọng (idea 42/58):** một định luật bảo toàn chỉ đúng khi điều kiện đối xứng còn đúng — mất đi ngay khi có ma sát (phá đối xứng dịch thời gian nếu ma sát phụ thuộc vận tốc theo cách không bảo toàn năng lượng), va chạm không đàn hồi (phá bảo toàn động năng dù động lượng vẫn bảo toàn nếu không có ngoại lực), hay ngoại lực thay đổi bản chất giữa các giai đoạn. Không thể có "cả bảo toàn động lượng và bảo toàn động năng" đồng thời một cách miễn phí trong va chạm — trừ khi va chạm được **cho biết** là đàn hồi.

## 5.5 Mở rộng sang trường liên tục — Định lý C2

Phần này áp dụng ý tưởng "đối xứng $\Rightarrow$ kết luận mạnh mà không cần giải phương trình" sang bài toán Điện từ, nơi đại lượng cần tìm là một **trường** $\vec E(\vec x)$ (một vector gán cho mỗi điểm không gian), không phải một số $q(t)$.

**Cần thêm 2 khái niệm ngắn:**

- **Phép quay $R$** (ma trận $3\times 3$ với $R^TR=I$): biến đổi giữ nguyên độ dài mọi vector và góc giữa chúng — "xoay cứng" không gian. Nếu $\rho$ (mật độ điện tích) thỏa $\rho(R\vec x)=\rho(\vec x)$ với **mọi** $R$, ta nói $\rho$ **đối xứng cầu** (giống nhau theo mọi hướng nhìn từ gốc tọa độ — ví dụ quả cầu tích điện đều).
- **Đổi biến trong tích phân nhiều chiều:** con đã biết đổi biến 1 chiều ($\int f(x)dx$, đặt $x=g(u)$, nhân thêm $|g'(u)|du$). Với tích phân thể tích 3 chiều và phép quay $\vec x'=R\vec y$, vì phép quay **bảo toàn thể tích** ($|\det R|=1$ — xoay một hình không làm nó phồng to hay bẹp lại), yếu tố thể tích không đổi: $d^3x' = d^3y$. Đây là toàn bộ "phép đổi biến" cần dùng — không cần Jacobian phức tạp vì $|\det R|=1$ luôn đúng cho phép quay.

**Định lý C2 (đối xứng nguồn ⇒ đối xứng trường).** Cho $\rho$ đối xứng cầu. Trường tĩnh điện $\vec E(\vec x)=\displaystyle\int \frac{\vec x-\vec x'}{4\pi\varepsilon_0|\vec x-\vec x'|^3}\rho(\vec x')\,d^3x'$ (công thức Coulomb tổng quát cho phân bố điện tích) thỏa $\vec E(\vec x)=E(|\vec x|)\hat x$ — tức **luôn hướng ra ngoài theo bán kính, và độ lớn chỉ phụ thuộc khoảng cách $r=|\vec x|$**, không phụ thuộc hướng.

**Chứng minh, đi từng bước đúng như tài liệu gốc:**

*Bước 1 (đẳng biến — $\vec E(R\vec x)=R\vec E(\vec x)$):* thay biến $\vec x'=R\vec y$ trong tích phân định nghĩa $\vec E(R\vec x)$:
$$\vec E(R\vec x)=\int\frac{R\vec x - \vec x'}{4\pi\varepsilon_0|R\vec x-\vec x'|^3}\rho(\vec x')\,d^3x' = \int \frac{R\vec x - R\vec y}{4\pi\varepsilon_0|R\vec x - R\vec y|^3}\rho(R\vec y)\,d^3y$$
(đổi biến, dùng $d^3x'=d^3y$ vì phép quay bảo toàn thể tích). Vì $R$ là phép quay: $R\vec x-R\vec y = R(\vec x-\vec y)$ và $|R(\vec x-\vec y)|=|\vec x-\vec y|$ (quay không đổi độ dài); và $\rho(R\vec y)=\rho(\vec y)$ (giả thiết đối xứng cầu). Vậy:
$$\vec E(R\vec x) = \int \frac{R(\vec x-\vec y)}{4\pi\varepsilon_0|\vec x-\vec y|^3}\rho(\vec y)\,d^3y = R\int\frac{\vec x-\vec y}{4\pi\varepsilon_0|\vec x-\vec y|^3}\rho(\vec y)\,d^3y = R\,\vec E(\vec x)$$
(kéo $R$ ra ngoài dấu tích phân được vì $R$ là phép biến đổi tuyến tính, áp dụng cho từng thành phần).

*Bước 2 (hướng của $\vec E$):* cố định $\vec x\neq \vec 0$. Xét **các phép quay quanh chính trục $O\vec x$** — gọi tập này là $SO(2)_x$ — mọi $R$ trong tập này thỏa $R\vec x=\vec x$ (trục quay không đổi chỗ). Bước 1 cho $\vec E(\vec x)=\vec E(R\vec x)=R\,\vec E(\vec x)$: vector $\vec E(\vec x)$ **đứng yên** dưới tác động của mọi phép quay quanh trục $\vec x$. Nhưng một vector chỉ có thể đứng yên dưới **mọi** phép quay quanh một trục nếu nó **song song với chính trục đó** — bất kỳ thành phần nào vuông góc với trục sẽ bị quay sang hướng khác khi $R$ thay đổi (nếu không, mọi hướng vuông góc phải bằng nhau với mọi góc quay — chỉ có vector $\vec 0$ vuông góc thỏa điều đó). Vậy $\vec E(\vec x)\parallel \hat x$.

*Bước 3 (độ lớn chỉ phụ thuộc $r=|\vec x|$):* lấy hai điểm $\vec x,\vec x'$ cùng khoảng cách gốc tọa độ ($|\vec x|=|\vec x'|$). Vì hai điểm cách gốc bằng nhau luôn có một phép quay $R$ đưa điểm này sang điểm kia ($R\vec x=\vec x'$ — trực giác: xoay quả cầu bán kính $|\vec x|$ luôn đưa được một điểm trên mặt cầu đến bất kỳ điểm nào khác trên cùng mặt cầu đó). Bước 1: $\vec E(\vec x')=\vec E(R\vec x)=R\vec E(\vec x)$. Theo Bước 2, $\vec E(\vec x)=E(x)\hat x$ với $E(x)$ là một số vô hướng, nên $R\vec E(\vec x) = E(x)\,R\hat x = E(x)\hat x'$ (vì $R\hat x=\hat x'$ theo cách chọn $R$). So với $\vec E(\vec x')=E(x')\hat x'$ (theo Bước 2 áp cho $\vec x'$): suy ra $E(x')=E(x)$. Vậy $E$ chỉ phụ thuộc $r$, không phụ thuộc hướng. $\blacksquare$

**Hệ quả tức thời — đây là lý do "định luật Gauss" hoạt động:** vì $E$ hằng số trên toàn bộ mặt cầu bán kính $r$ (Bước 3) và luôn vuông góc mặt cầu đó (Bước 2), thông lượng qua mặt cầu tính rất đơn giản: $\oint_{S_r}\vec E\cdot d\vec S = E(r)\cdot 4\pi r^2$. Kết hợp với định lý Gauss–Ostrogradsky (thông lượng $=Q_{\text{trong}}/\varepsilon_0$, một định lý con sẽ gặp khi học phần Điện), ta có ngay $E(r)=\dfrac{Q_{\text{trong}}(r)}{4\pi\varepsilon_0 r^2}$ mà **không cần** tính tích phân Coulomb gốc trực tiếp — đây chính là "thuật toán Gauss" quen thuộc, giờ con đã thấy nó là hệ quả *tất yếu* của đối xứng, không phải một mẹo rời rạc.

**Ví dụ kiểm chứng bằng số** (đúng như tài liệu gốc dẫn): quả cầu tích điện đều $\rho=$ const, bán kính $R$. Với $r<R$: $Q_{\text{trong}}(r)=\rho\cdot\frac43\pi r^3$, nên $E(r)=\dfrac{\rho\cdot\frac43\pi r^3}{4\pi\varepsilon_0 r^2}=\dfrac{\rho r}{3\varepsilon_0}$ — khớp chính xác kết quả chuẩn cho quả cầu tích điện đều.

Cùng cơ chế áp dụng cho đối xứng trụ (định lý Ampère cho dòng điện) và đối xứng phẳng — chỉ thay nhóm phép quay $SO(3)$ bằng nhóm phép quay quanh 1 trục ($SO(2)$, cho đối xứng trụ) hoặc nhóm tịnh tiến 2 chiều (cho đối xứng phẳng); các bước chứng minh giữ nguyên cấu trúc.

### Tự kiểm tra §5

1. Không nhìn tài liệu, hãy tự phát biểu lại (bằng lời của con) vì sao điều kiện $(*)$ trong Định lý C1 chính là "$L$ không đổi đến bậc nhất theo $\varepsilon$".
2. Tự làm lại chứng minh phần (c) (bảo toàn mô-men động lượng) từ đầu, không nhìn tài liệu, đặc biệt bước dùng $\vec a\cdot(\vec b\times\vec c)=\vec b\cdot(\vec c\times\vec a)$.
3. Trong chứng minh (d), vì sao ta cần điều kiện "$T$ là hàm thuần nhất bậc 2 theo $\dot q$" để đi từ $H$ sang $T+V$? Thử nghĩ một ví dụ mà $T$ **không** toàn phương thuần túy theo $\dot q$ (gợi ý: hệ có ràng buộc phụ thuộc thời gian, ví dụ một vòng đang được kéo giãn) để thấy vì sao lúc đó $H\neq T+V$ nói chung.
4. Trong Định lý C2, bước nào **thực sự dùng** giả thiết "$\rho$ đối xứng cầu", và bước nào chỉ dùng tính chất hình học thuần túy của phép quay (đúng với mọi $\rho$)?
5. Nếu $\rho$ chỉ đối xứng trụ (không đối xứng cầu) — ví dụ dây dẫn dài tích điện đều — hãy đoán trước: $\vec E$ sẽ phụ thuộc vào những biến nào, và hướng theo đâu? (Đối chiếu với `[ELK, §3.2]` được nhắc trong tài liệu gốc.)

---

# CHƯƠNG 6 — TRỤ CỘT D: XẤP XỈ & THANG ĐO

## 6.1 Tham số bé $\varepsilon$ — vì sao ta cần xấp xỉ

Rất nhiều bài toán không có nghiệm "đóng" (công thức chính xác gọn gàng). Nhưng nếu đề cho biết một đại lượng "rất bé" hay "rất lớn" so với đại lượng khác (dấu $\ll,\gg$), ta có thể **tuyến tính hóa** — thay hàm phức tạp bằng xấp xỉ bậc thấp, miễn tham số bé đó thực sự bé. Đọc lại bảng ví dụ trong tài liệu gốc ($\S6.1$/$5.1$) — mỗi dòng là một đề bài IPhO thật, đều cho $\varepsilon$ tường minh bằng chữ. **Kỹ năng đọc ra $\varepsilon$ từ lời văn** ("rất dài", "rất nhẹ", "gần bằng") quan trọng ngang với kỹ năng giải toán.

## 6.2 Ôn lại chuỗi Taylor — con đã biết, chỉ cần đặt tên

Con đã học đạo hàm, nên chắc đã thấy xấp xỉ quen thuộc: với $\varphi$ nhỏ, $\sin\varphi\approx\varphi$, $\cos\varphi\approx 1-\varphi^2/2$. Đây là 2 số hạng đầu của **khai triển Taylor**:
$$f(\varepsilon) = f(0) + f'(0)\,\varepsilon + \frac{f''(0)}{2}\varepsilon^2 + \cdots$$
— xấp xỉ hàm $f$ gần điểm $0$ bằng một đa thức, dùng chính đạo hàm tại điểm đó. Càng giữ nhiều số hạng, xấp xỉ càng chính xác khi $\varepsilon$ đủ nhỏ; với $\varepsilon\ll 1$, giữ 1–2 số hạng đầu thường đã đủ cho bài toán Vật lý.

## 6.3 Định lý D2 — khai triển tiệm cận theo bậc

Đây thực chất là Taylor áp dụng cho **nghiệm của một phương trình** thay vì cho một hàm cho sẵn. Cho phương trình $F(x,\varepsilon)=0$, biết nghiệm $x_0$ khi $\varepsilon=0$ (bài toán "không nhiễu", dễ giải). Đặt $x=x_0+\varepsilon x_1+\varepsilon^2 x_2+\cdots$ — ta **giả sử** nghiệm thật gần nghiệm dễ $x_0$, sai khác một lượng nhỏ tỉ lệ $\varepsilon$. Thay vào $F$, khai triển Taylor theo $\varepsilon$, rồi **gom các số hạng cùng bậc $\varepsilon^0,\varepsilon^1,\dots$ lại với nhau** — vì $F(x,\varepsilon)=0$ với **mọi** $\varepsilon$ nhỏ, nên hệ số của **từng bậc** $\varepsilon^k$ riêng lẻ phải bằng 0 (nếu không, chọn $\varepsilon$ đủ nhỏ theo hướng khác sẽ phá đẳng thức). Mỗi bậc cho một phương trình **tuyến tính** cho $x_k$ theo các $x_0,\dots,x_{k-1}$ đã biết trước đó — giải tuần tự, bậc 0 trước, dùng nó tính bậc 1, v.v. Đây đúng là "phương pháp nhiễu loạn" (`[MEH, method 2]`): giải bài toán lý tưởng trước, rồi dùng nó để tính **lực hiệu chỉnh** bậc tiếp theo.

**Ví dụ nhỏ để cụ thể hóa:** phương trình $x^2 - 1 = \varepsilon x$ (với $\varepsilon$ nhỏ). Bậc 0 ($\varepsilon=0$): $x_0^2=1\Rightarrow x_0=1$ (chọn nghiệm dương). Đặt $x=1+\varepsilon x_1$, thay vào: $(1+\varepsilon x_1)^2-1=\varepsilon(1+\varepsilon x_1)$. Khai triển: $1+2\varepsilon x_1+\varepsilon^2x_1^2-1 = \varepsilon+\varepsilon^2x_1$, tức $2\varepsilon x_1+\varepsilon^2x_1^2=\varepsilon+\varepsilon^2x_1$. Gom bậc $\varepsilon^1$: $2x_1=1\Rightarrow x_1=\frac12$. Vậy $x\approx 1+\varepsilon/2$ — con có thể kiểm tra bằng công thức nghiệm chính xác $x=\frac{\varepsilon+\sqrt{\varepsilon^2+4}}2$ và khai triển Taylor của căn thức để thấy khớp.

## 6.4 Định lý D1 (Buckingham $\Pi$) — xây từ ví dụ con lắc

Câu hỏi: chu kỳ con lắc đơn $\tau$ phụ thuộc vào những gì? Trực giác vật lý gợi ý: khối lượng $m$, chiều dài $l$, gia tốc trọng trường $g$. Ta **không cần giải phương trình vi phân** để biết dạng công thức — chỉ cần phân tích **thứ nguyên**.

Lập bảng số mũ thứ nguyên của 4 đại lượng ($\tau, m, g, l$) theo 3 thứ nguyên cơ bản (Khối lượng $M$, Chiều dài $L$, Thời gian $T$):

| | $\tau$ | $m$ | $g$ | $l$ |
|---|---|---|---|---|
| $M$ | 0 | 1 | 0 | 0 |
| $L$ | 0 | 0 | 1 | 1 |
| $T$ | 1 | 0 | $-2$ | 0 |

Đây là một ma trận $3\times 4$. Tính hạng của nó ($\S0.3$): cột $m$ là cột duy nhất có mặt ở hàng $M$ — không cột nào khác "ăn theo" nó được để triệt tiêu hàng $M$, nên hạng $=3$ (đầy đủ theo số hàng). Định lý D1 nói: số nhóm không thứ nguyên độc lập là $p=n-k=4-3=1$. Chỉ có **một** tổ hợp không thứ nguyên có thể lập từ $\tau,m,g,l$ — và ta tìm nó bằng cách thử: $\tau^2 g/l$ có thứ nguyên $T^2\cdot LT^{-2}/L = 1$ — không thứ nguyên! (và đây là tổ hợp *duy nhất*, vì $p=1$).

**Hệ quả cực mạnh:** vì mối liên hệ vật lý phải viết được thành một phương trình giữa các $\Pi_i$ (ở đây chỉ có 1 cái), và một hệ thức "$f(\Pi_1)=0$" với 1 biến số chỉ có thể là $\Pi_1=\text{hằng số}$ (không có phương trình nào khác cho 1 biến duy nhất mà không phải hằng số), suy ra ngay:
$$\tau^2\frac{g}{l} = C \ (\text{hằng số}) \quad\Rightarrow\quad \tau = C'\sqrt{\frac lg},$$
và **đặc biệt, $m$ hoàn toàn biến mất khỏi công thức** — vì $m$ không tham gia được vào bất kỳ tổ hợp không thứ nguyên nào cùng $\tau,g,l$ (nó là "cô đơn" ở hàng $M$). Đây chính là lý do toán học nghiêm ngặt (không phải suy luận định tính) cho sự kiện quen thuộc "chu kỳ con lắc đơn không phụ thuộc khối lượng" — và ta biết điều này **trước khi** giải bất kỳ phương trình vi phân nào.

**Vì sao đây là công cụ dùng khi đề không cho $\varepsilon$ tường minh:** một tham số so sánh "bé/lớn" bắt buộc phải không thứ nguyên (so sánh 2 kg với 3 mét vô nghĩa) — nên nếu đề không nói thẳng $\varepsilon$ là gì, nó **chắc chắn** là một trong các $\Pi_i$ mà Định lý D1 liệt kê được — thu hẹp triệt để việc "đoán".

## 6.5 Định lý D3 — trị riêng và thang thời gian đặc trưng

Với mạch RC đơn giản (tụ phóng qua điện trở), phương trình là $\dot U = -\dfrac{U}{RC}$ — một phương trình vi phân tuyến tính bậc nhất dạng $\dot y = Ay$ với "ma trận" $A$ ở đây chỉ là một số: $A=-1/(RC)$.

Nghiệm: $U(t)=U_0 e^{At}=U_0e^{-t/RC}$ — con đã biết dạng nghiệm này (hàm mũ giảm) từ việc học đạo hàm của $e^{kt}$. Đại lượng $\tau:=-1/A=RC$ là "**thời gian đặc trưng**" — thời gian để $U$ giảm còn $1/e$ giá trị ban đầu.

**Ý tưởng "trị riêng" (chỉ cần ở mức tối thiểu này):** với hệ nhiều biến $\dot{\vec y}=A\vec y$ ($A$ là ma trận thật sự, không chỉ 1 số), ta thử nghiệm dạng $\vec y = \vec v\, e^{\lambda t}$ (đoán rằng nghiệm vẫn là hàm mũ, chỉ theo một "hướng" cố định $\vec v$ trong không gian nhiều biến). Thay vào: $\lambda \vec v e^{\lambda t} = A\vec v e^{\lambda t}$, tức $A\vec v=\lambda\vec v$ — $\lambda$ gọi là **trị riêng** của $A$, $\vec v$ là **vector riêng**. Mỗi trị riêng $\lambda_i$ cho một "hằng số thời gian" riêng $\tau_i=-1/\operatorname{Re}(\lambda_i)$. Việc so sánh "chu kỳ ngoại lực $T$ nhanh hay chậm so với hệ" quy về so sánh $T$ với $\max_i\tau_i$ — đúng bài toán "so sánh $T$ với $\tau=RC$" quen thuộc trong `[ELK]`, chỉ tổng quát hóa cho hệ nhiều biến hơn (ví dụ mạch có cả cuộn cảm lẫn tụ điện).

Với mạch RC ở trên, "ma trận" chỉ có 1 phần tử nên trị riêng chính là $A=-1/RC$ — khớp với công thức đã biết. Với hệ phức tạp hơn (không yêu cầu con tự tính trị riêng ma trận lớn ở lớp 9 — chỉ cần **hiểu khái niệm**: "mỗi cách dao động/suy giảm độc lập của hệ có tốc độ riêng của nó, đo bằng trị riêng").

**Kết luận Chương 6:** Trụ cột D gần như hoàn toàn thuật toán một khi con nắm 3 công cụ: (i) đọc $\varepsilon$ từ lời văn, hoặc suy ra bằng Buckingham $\Pi$ nếu đề giấu nó; (ii) khai triển Taylor theo bậc (D2) một khi có $\varepsilon$; (iii) so thời gian đặc trưng qua trị riêng (D3) khi bài có phương trình vi phân tuyến tính.

### Tự kiểm tra §6

1. Một vật rơi trong không khí có lực cản $\propto v^2$ nhỏ so với trọng lực. Xác định tham số $\varepsilon$ hợp lý (không thứ nguyên!) mô tả "lực cản nhỏ" trong bài toán này, dùng ý tưởng Buckingham.
2. Áp dụng Định lý D2 để tìm xấp xỉ bậc nhất của nghiệm dương phương trình $x^2=4+\varepsilon x^2$ (so sánh với nghiệm chính xác để tự kiểm tra).
3. Vì sao "một tham số so sánh bé/lớn phải không thứ nguyên" lại là một ràng buộc *hữu ích* khi đề bài không nói rõ $\varepsilon$ là gì?
4. Giải thích bằng lời (không cần tính toán ma trận): tại sao "trị riêng" của một hệ dao động-tắt dần lại đóng đúng vai trò của "$1/RC$" trong mạch điện.

---

# CHƯƠNG 7 — B8: ĐIỀU KIỆN BIÊN & ĐIỀU KIỆN ĐẦU

Phần này (bảng tra cứu trong tài liệu gốc) không cần lý thuyết mới — nó chỉ là **áp dụng lại** những gì con vừa học vào việc "dịch" từ ngữ đề bài sang phương trình toán:

- "Đại lượng có quán tính... liên tục" (vị trí, điện tích trên tụ, dòng qua cuộn cảm, mô-men động lượng ngoài xung lực): đây là hệ quả của việc các đại lượng này xuất hiện trong Lagrangian qua **đạo hàm bậc nhất theo thời gian** của chúng (như $\dot q$ trong $T=\frac12 m\dot q^2$) — một bước nhảy tức thời của chính $q$ sẽ đòi hỏi vận tốc vô hạn, tức năng lượng vô hạn, vật lý không cho phép trừ khi có xung lực tức thời tác động đúng vào đại lượng đó.
- "Sau một thời gian dài, ổn định": chính là điều kiện **trạng thái dừng** — mọi đạo hàm theo $t$ của các đại lượng "chậm" tiến về 0. Đây liên hệ trực tiếp tới $\S6.5$: hệ đã "tắt dần" qua thời gian đặc trưng $\tau$, các số hạng $e^{-t/\tau}\to 0$.
- "Cực đại/cực tiểu theo thời gian": đạo hàm theo $t$ của đại lượng đó bằng 0 tại thời điểm đó — đúng định nghĩa cực trị mà con đã học trong Đạo hàm (tìm cực trị hàm 1 biến, chỉ bây giờ biến là $t$).

Không có gì để "hiểu bản chất" thêm ở đây ngoài việc luyện thuộc bảng và liên hệ mỗi dòng với đúng khái niệm Vật lý/Toán tương ứng đã học ở các chương trước — hãy tự làm việc đó bằng cách với **mỗi dòng** trong bảng B8 gốc, tự hỏi: "khái niệm Toán nào ở Chương 0–6 đứng sau dòng này?"

---

# CHƯƠNG 8 — B9 (GIẢI HỆ) & B10 (KIỂM TRA NGƯỢC)

**B9** không có một "công thức" — nó là bước dùng toàn bộ phương trình đã lập ở B2–B8 (đại số, vi phân, hoặc đồ thị/số) để tìm ẩn. Kỹ năng ở đây chính là các kỹ năng Toán con đã có (giải hệ phương trình, giải phương trình vi phân tuyến tính bậc nhất/hai đơn giản như $\dot U=-U/RC$ ở $\S6.5$ hay $\ddot\theta=-\frac gl\theta$ dạng tuyến tính hóa của con lắc).

**B10 — kiểm tra ngược** — đọc kỹ 5 bước trong tài liệu gốc, đây là nơi mọi công cụ con vừa học "trả nợ" lẫn nhau:

1. **Kiểm tra thứ nguyên**: dùng chính bảng thứ nguyên $\S6.4$.
2. **Kiểm tra giới hạn đặc biệt**: cho $\varepsilon\to 0$ hoặc $\to\infty$ — đây chính xác là kiểm tra nghiệm $x_0$ (bậc 0) của Định lý D2 khớp trực giác vật lý đã biết trước.
3. **Kiểm tra dấu**: dùng quy ước đại số hóa đại lượng có dấu từ B0.
4. **Kiểm tra qua định luật bảo toàn độc lập**: nếu con giải bằng Euler–Lagrange (Newton suy rộng), hãy thử tính lại bằng đại lượng bảo toàn tìm được ở Chương 5 (Trụ cột C) xem có khớp không — đây là lý do Trụ cột C không chỉ dùng để *giải* mà còn để *kiểm tra*.
5. **Kiểm tra bậc tự do**: đếm số phương trình đã dùng, so với $f_{\text{eff}}$ tính từ Chương 3 ($\S3.3$, công thức Fact 18 tổng quát hóa) — nếu lệch, con đã hoặc lặp một ràng buộc, hoặc thiếu lập luận.

Đây chính là lý do 10 bước B0–B10 không phải một danh sách rời rạc — chúng là **một vòng khép kín**: B2–B4 (Trụ cột A, B, C) xác định số phương trình con *cần*, B9 dùng chúng để giải, B10 dùng lại chính B2–B4 để *xác nhận* con đã giải đúng đủ, không thừa không thiếu.

---

# CHƯƠNG 9 — BẢN ĐỒ TỔNG THỂ & LUYỆN TẬP ĐỂ DÙNG THUẦN THỤC

## 9.1 Bản đồ liên kết — mỗi bước B dựa vào công cụ nào

```
B0  Đọc đề (kỷ luật, không cần Toán mới)................ Chương 2
B1  Chọn hệ / tọa độ suy rộng........................... Chương 1 (Lagrange) + Chương 2
B2  Đếm f_raw (Định lý A)............................... Chương 0 (Hàm ẩn, hạng ma trận) + Chương 3
B3  Liệt kê ràng buộc (holonomic/non-holonomic).......... Chương 4 (dạng vi phân, Frobenius)
B4  Săn đối xứng (Noether)............................... Chương 0 (tích có hướng) + Chương 1 (Euler-Lagrange) + Chương 5
B5  Chọn q tối thiểu (f_eff)............................. Chương 3 §3.3 (kết hợp A + B4)
B6  Xấp xỉ & thang đo (ε, Taylor, Buckingham, trị riêng).. Chương 6
B7  Chọn "ngôn ngữ chi phối" (Lagrange/Newton/mạch...).... Toàn bộ Chương 1–6, tùy bài
B8  Điều kiện biên/đầu................................... Chương 7 (áp dụng lại 0–6)
B9  Giải hệ.............................................. Kỹ năng Toán nền (đã có từ trước)
B10 Kiểm tra ngược........................................ Chương 8 (áp dụng lại toàn bộ)
```

## 9.2 Vì sao đây không phải "học vẹt"

Nếu con chỉ nhớ "Định lý A nói $f=N-k$" mà không tự làm lại được ví dụ đường tròn $\S0.4$ bằng tay — đó là học vẹt. Bài kiểm tra thật sự của **hiểu bản chất**, cho từng Trụ cột:

- **Trụ cột A**: con có thể, với một hệ **mới, chưa từng gặp**, tự viết ra các hàm $g_j(x,t)$ và tính (hoặc lý luận) hạng Jacobi của chúng — không chỉ "nhớ công thức $f=N-k$".
- **Trụ cột B**: con có thể, với một ràng buộc vận tốc **mới**, tự tính $\omega\wedge d\omega$ từ đầu (như con đã luyện ở Tự kiểm tra §4, câu 3) — không chỉ nhớ "đĩa lăn thì holonomic".
- **Trụ cột C**: con có thể, với một hệ **mới**, tự đề xuất một $X$ hợp lý và tự kiểm tra điều kiện $(*)$ bằng đạo hàm riêng trực tiếp — không chỉ nhớ "có đối xứng tịnh tiến thì bảo toàn động lượng".
- **Trụ cột D**: con có thể, với một bài toán **mới** không cho $\varepsilon$ tường minh, tự lập bảng thứ nguyên và tìm $\Pi_i$ bằng tay — không chỉ nhớ "chu kỳ con lắc không phụ thuộc khối lượng".

## 9.3 Lộ trình luyện tập đề nghị (để "dùng thuần thục")

1. **Vòng 1 — tái tạo, không nhìn tài liệu:** với mỗi Định lý (A, B, C1, C2, D1, D2, D3), gấp sách lại, tự viết ra phát biểu + tự làm lại **một** ví dụ minh họa (không nhất thiết giống ví dụ trong bài) từ đầu đến cuối.
2. **Vòng 2 — bài tập lạ:** lấy 3–5 bài tập Cơ/Điện Olympic (VPhO vòng tỉnh trở lên, hoặc IPhO những năm dễ) mà con **chưa giải bao giờ**. Với mỗi bài, chạy đúng quy trình B0→B10 bằng lời (viết ra giấy từng bước, kể cả B0), đặc biệt không bỏ qua B2 (đếm DOF tường minh) và B10 (5 bước kiểm tra) dù bài "trông dễ".
3. **Vòng 3 — dạy lại:** giải thích cho một bạn khác (hoặc tự giải thích thành tiếng) vì sao Định lý B cần $\omega\wedge d\omega$ chứ không chỉ $d\omega$, và vì sao Định lý C2 cần đúng 3 bước (đẳng biến → hướng → độ lớn) chứ không thể gộp lại. Nếu con giải thích trơn tru không vấp — con đã hiểu bản chất, không phải học vẹt.
4. **Vòng 4 — tự đọc lại tài liệu gốc một mình, từ đầu đến cuối, không dừng.** Đây là bài kiểm tra cuối cùng: nếu con đọc trôi chảy, hiểu mọi ký hiệu, không còn chỗ nào phải hỏi "cái này là gì" — giáo trình này đã hoàn thành nhiệm vụ.

---

# PHỤ LỤC — GỢI Ý ĐÁP ÁN CÁC CÂU TỰ KIỂM TRA (chỉ gợi ý, không phải lời giải đầy đủ — tự làm trước khi xem)

**§0:** (1) $\partial f/\partial x=2xy$, $\partial f/\partial y=x^2+\cos y$. (2) hàng 2 không phải bội số của hàng 1 trong trường hợp đầu (hệ số khác tỉ lệ: $1/3\ne -1/-3$... thực ra kiểm tra kỹ định thức $\begin{vmatrix}1&-1\\3&-3\end{vmatrix}=-3+3=0$ — gợi ý: đề bài ở đây cố ý minh họa, con hãy tự lập lại 2 ma trận và tính định thức $2\times2$ để thấy trường hợp nào bằng 0 (phụ thuộc), trường hợp nào khác 0 (độc lập), rồi đối chiếu lại với vế phải của mỗi phương trình để xem hệ có nghiệm hay vô nghiệm/vô số nghiệm. (3) tại điểm đó cả hai đạo hàm riêng khác 0 nên **cả hai cách giải** đều dùng được cục bộ — đây là điểm "đối xứng" của đường tròn theo góc 45°. (4) $f=3-1=2$ — mặt cầu là mặt 2 chiều, khớp trực giác "cần 2 góc (kinh độ, vĩ độ) để định vị một điểm trên mặt cầu".

**§1:** (2) $L=\frac12m\dot s^2 - mg(l_0-s)\sin\alpha$ (thế năng giảm dần khi trượt xuống) hoặc chọn mốc phù hợp — Euler–Lagrange cho $m\ddot s = mg\sin\alpha$. (3) $p_3=\partial L/\partial\dot q^3$ bảo toàn. (4) thứ nguyên mô-men động lượng $\mathrm{kg\,m^2/s}$, khác thứ nguyên động lượng thẳng $\mathrm{kg\,m/s}$.

**§3:** (1) thô $N=4$ ($x_1,y_1,x_2,y_2$ cho con lắc đơn thanh 1; nếu tính cả thanh 2 thì thêm 2 nữa — tự làm rõ mô hình trước khi đếm!); dùng trực tiếp $(\theta_1,\theta_2)$ cho ra $f=2$ ngay — đối chiếu hai cách đếm phải khớp nhau.

**§4:** (4) gợi ý: quả cầu lăn tự do có nhiều bậc tự do quay hơn đĩa 2D (3 thành phần vận tốc góc thay vì 1) — dự đoán nó **cũng không toàn chỉnh**, và thực tế đây là một trong những ví dụ nổi tiếng nhất của ràng buộc non-holonomic (quả bóng lăn trên bàn).

**§5:** (4) bước dùng "$\rho$ đối xứng cầu" **chỉ** ở đẳng thức $\rho(R\vec y)=\rho(\vec y)$ trong Bước 1 — mọi lý luận sau đó (Bước 2, 3) chỉ dùng tính chất hình học của phép quay, đúng với **mọi** trường vector thỏa Bước 1, không riêng gì tĩnh điện.

**§6:** (2) bậc 0: $x_0^2=4\Rightarrow x_0=2$; đặt $x=2+\varepsilon x_1$, thay vào $x^2=4+\varepsilon x^2$, gom bậc $\varepsilon^1$ ra $4x_1 = 4 \Rightarrow x_1=1$, vậy $x\approx 2+\varepsilon$.

*(Các câu còn lại là câu hỏi mở/tự luận — không có "đáp án" cố định, mục đích là buộc con diễn đạt lại bằng lời của chính mình; hãy nhờ thầy/cô kiểm tra trực tiếp các câu đó.)*
