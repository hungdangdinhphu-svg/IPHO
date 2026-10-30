# VẬT LÝ TỪ FIRST PRINCIPLES — GIÁO TRÌNH NHẬP MÔN TỪ CON SỐ 0

> *Tài liệu này giả định bạn: biết Vật Lý phổ thông (F=ma, động năng, thế năng, dao động điều hòa) và Toán phổ thông (đạo hàm, tích phân cơ bản). Tài liệu này KHÔNG giả định bạn biết gì về giải tích biến phân, Lagrangian, Hamiltonian, hay định lý Noether. Mọi thứ sẽ được xây từ đầu, chậm, có ví dụ số cụ thể.*

> *Mục tiêu: sau khi đọc xong, bạn hiểu **vì sao** toàn bộ Cơ học Newton chỉ là một hệ quả của MỘT câu duy nhất, và vì sao việc hiểu câu đó làm giảm "Vấn đề tìm kiếm" (tìm CHỖ + CÔNG CỤ) xuống gần như bằng không đối với một lớp rất lớn các bài toán. Đây không phải là "phím tắt HSGQG" — đây là nền móng mà từ đó mọi phím tắt chỉ là hệ quả.*

---

## MỤC LỤC

- Chương 0 — Tại sao làm việc này, và nó liên hệ thế nào với "Vấn đề tìm kiếm"
- Chương 1 — Chuẩn bị toán học tối thiểu (functional, biến phân)
- Chương 2 — Nguyên lý tác dụng tối thiểu: xây dựng từ đầu
- Chương 3 — Phương trình Euler–Lagrange: suy luận chi tiết, không bỏ bước
- Chương 4 — Áp dụng: năm ví dụ dựng Lagrangian từ số 0
- Chương 5 — Vì sao toạ độ suy rộng là "vũ khí tối thượng" (ví dụ con lắc trên xe, con lắc kép)
- Chương 6 — Ràng buộc và nhân tử Lagrange
- Chương 7 — Hamilton: đổi biến Legendre, không gian pha
- Chương 8 — Định lý Noether: trái tim của toàn bộ Vật Lý (chứng minh chi tiết + 4 ví dụ)
- Chương 9 — Cách một Researcher đọc một bài toán mới (quy trình thao tác được)
- Chương 10 — Mở rộng ra toàn bộ Vật Lý (bản đồ tổng, liên hệ ngắn gọn)
- Chương 11 — Lộ trình luyện tập 10 tuần, có bài tập cụ thể
- Phụ lục — Bảng tra nhanh & checklist tự kiểm tra

---

# CHƯƠNG 0 — TẠI SAO LÀM VIỆC NÀY

Bạn đã có trong tay một tài liệu ("Vấn đề tìm kiếm") phát biểu một quan sát rất sắc: mỗi bài Vật Lý khó không phải vì bạn thiếu công cụ, mà vì bạn không biết **CHỖ** nào trong bài để áp dụng công cụ nào. Giải pháp được đề xuất ở đó là xây một **thư viện công cụ hữu hạn, mỗi công cụ gắn với một "precondition"** (Pre/Suf), rồi duyệt có hệ thống.

Thư viện đó — dù đồ sộ (bạn đã có hàng nghìn dòng cho Cơ, Nhiệt, Điện, Quang, Hạt nhân) — vẫn là tập hợp của **hệ quả**. Mỗi công cụ trong đó (bảo toàn động lượng, bảo toàn mômen động lượng, bảo toàn năng lượng, điều kiện cân bằng, phương trình dao động...) đều **suy ra được** từ đúng một câu:

> **Tự nhiên chọn con đường làm một đại lượng gọi là "tác dụng" dừng (stationary).**

Đây là insight trong file "Một Sợi Chỉ Xuyên Suốt" mà bạn đã có. Nhiệm vụ của file này là: **dạy bạn từ số 0** để câu đó không còn là một câu trích dẫn trừu tượng, mà là một công cụ bạn **tự tay suy ra được** mọi định luật bảo toàn, mọi phương trình chuyển động, trong vài phút, với bất kỳ hệ nào bạn gặp — kể cả hệ bạn chưa từng thấy.

**Vì sao điều này triệt tiêu "Vấn đề tìm kiếm"?** Vì thay vì hỏi *"bài này nên dùng công cụ nào trong 200 công cụ tôi đã học?"*, bạn chỉ hỏi đúng hai câu:

1. **T (động năng) và U (thế năng) của hệ này là gì, viết theo toạ độ nào?**
2. **Hệ này có đối xứng gì (dịch chuyển, quay, thời gian) — đối xứng nào bị giữ nguyên?**

Câu 1 cho bạn phương trình chuyển động (Euler–Lagrange). Câu 2 cho bạn **mọi** định luật bảo toàn mà không cần nhớ tên chúng. Đó là "quá ít công cụ để thắc mắc" mà bạn đã nói trong câu hỏi gốc — và nó không phải ảo tưởng, nó là sự thật toán học.

**Giới hạn thành thật:** first principles cho bạn *bản đồ*, không đi bộ hộ bạn. Bạn vẫn cần giải phương trình vi phân, vẫn cần mô hình hoá đúng (viết đúng T, U, đúng ràng buộc). Nhưng khoảng cách từ "đọc đề" đến "có phương trình đúng" co lại gần như về 0, vì bạn không còn phải *đoán* công cụ nào trong hàng trăm công cụ — bạn **luôn dùng đúng một quy trình**.

---

# CHƯƠNG 1 — CHUẨN BỊ TOÁN HỌC TỐI THIỂU

Rào cản duy nhất ngăn bạn hiểu Chương 2 là một khái niệm: **phiếm hàm (functional)**. Ta xây nó từ cái bạn đã biết.

## 1.1. Hàm số bạn đã biết

Một hàm số thông thường $f(x)$ nhận **một số** $x$, trả về **một số** $f(x)$. Ví dụ $f(x) = x^2$.

Bạn đã biết: để tìm cực trị của $f$, ta giải $f'(x) = 0$. Ý tưởng: tại điểm cực trị, một thay đổi nhỏ $x \to x+\epsilon$ không làm $f$ thay đổi ở **bậc nhất** theo $\epsilon$:
$$f(x+\epsilon) = f(x) + f'(x)\epsilon + O(\epsilon^2)$$
Nếu $f'(x) \neq 0$ thì $f(x+\epsilon) - f(x) \approx f'(x)\epsilon$, dấu của nó phụ thuộc dấu $\epsilon$ ⇒ $x$ không phải cực trị. Chỉ khi $f'(x)=0$ thì số hạng bậc nhất biến mất.

**Giữ chắc ý tưởng này** — "số hạng bậc nhất phải triệt tiêu" — vì toàn bộ Chương 2 chỉ là áp đúng ý tưởng này lên một đối tượng phức tạp hơn.

## 1.2. Phiếm hàm — hàm nhận vào MỘT ĐƯỜNG, trả ra MỘT SỐ

Bây giờ thay vì nhận vào một số, ta xét một đối tượng nhận vào **cả một hàm** $q(t)$ (tức là nhận vào *toàn bộ một đường đi*, một quỹ đạo theo thời gian) và trả ra **một số**. Đối tượng đó gọi là **phiếm hàm**, ký hiệu $S[q(t)]$.

Ví dụ cụ thể để bạn có cảm giác: giả sử
$$S[q(t)] = \int_0^1 \big(\dot q(t)\big)^2 \, dt$$
Nếu $q(t) = t$ (đường thẳng, $\dot q = 1$) thì $S[q] = \int_0^1 1\, dt = 1$.
Nếu $q(t) = t^2$ (đường cong, $\dot q = 2t$) thì $S[q] = \int_0^1 4t^2\, dt = 4/3$.

Thấy không: **hai hàm $q(t)$ khác nhau cho ra hai số $S$ khác nhau**. $S$ "ăn" cả một đường đi, nhả ra một con số duy nhất đo lường "đường đi đó như thế nào" theo nghĩa mà $S$ định nghĩa.

## 1.3. Bài toán biến phân: tìm đường đi làm $S$ dừng

Câu hỏi trung tâm của Chương 2: trong tất cả các hàm $q(t)$ nối hai điểm cố định $q(t_1)=q_1$, $q(t_2)=q_2$, hàm nào làm $S[q]$ **dừng** (không đổi ở bậc nhất khi ta nhiễu loạn $q$ một chút)?

Đây **chính xác** là ý tưởng của mục 1.1, chỉ khác: thay vì nhiễu một con số $x \to x + \epsilon$, ta nhiễu **cả một đường** $q(t) \to q(t) + \epsilon\, \eta(t)$, với $\eta(t)$ là một hàm bất kỳ (biên độ nhiễu tại từng thời điểm) miễn là $\eta(t_1) = \eta(t_2) = 0$ (hai đầu mút giữ cố định, vì ta chỉ so sánh các đường có cùng điểm đầu — điểm cuối).

Chương 2–3 sẽ làm chính xác phép tính này cho $S$ là tác dụng vật lý thật.

---

# CHƯƠNG 2 — NGUYÊN LÝ TÁC DỤNG TỐI THIỂU: XÂY DỰNG TỪ ĐẦU

## 2.1. Động cơ: $F=ma$ thiếu gì?

$F=ma$ là đúng, nhưng nó là một **phát biểu cục bộ**: nó nói, tại từng thời điểm, gia tốc tỉ lệ với lực tại thời điểm đó. Nó không nói gì về *toàn bộ lịch sử* chuyển động là gì mà chỉ cho bạn cách xây dựng nó từng bước vi phân một.

Hệ quả thực tế của sự "cục bộ" này:
- Khi đổi toạ độ (ví dụ sang toạ độ cực, hoặc toạ độ gắn với ràng buộc như góc của con lắc), bạn phải **tính lại lực theo toạ độ mới** một cách thủ công, dễ sai dấu, dễ quên lực quán tính, dễ quên lực liên kết (sức căng dây, phản lực).
- Với hệ nhiều vật ràng buộc phức tạp (con lắc kép, vật trên nêm di động), số lực liên kết chưa biết tăng nhanh, và bạn phải "đoán" đúng mọi lực trước khi viết phương trình.

## 2.2. Phát biểu nguyên lý

Định nghĩa **hàm Lagrange** (Lagrangian) của hệ:
$$L(q, \dot q, t) = T - U$$
với $T$ là động năng, $U$ là thế năng, $q$ là toạ độ (có thể là $x$, có thể là góc $\theta$, bất kỳ cái gì mô tả đủ trạng thái hệ).

Định nghĩa **tác dụng**:
$$S[q(t)] = \int_{t_1}^{t_2} L(q, \dot q, t)\, dt$$

**Nguyên lý Hamilton (tác dụng tối thiểu):** Trong tất cả các đường $q(t)$ khả dĩ nối $(t_1, q_1)$ và $(t_2, q_2)$, đường đi **thật** mà hệ tuân theo là đường làm $S$ **dừng**:
$$\delta S = 0$$

Chỉ vậy thôi. Đây là toàn bộ nội dung. Chương 3 sẽ chứng minh rằng điều kiện $\delta S = 0$ này **tương đương** với $F = ma$ (và tổng quát hơn, với mọi phương trình Newton cho mọi toạ độ).

## 2.3. Vì sao "T trừ U" chứ không phải "T cộng U"?

Đây là câu hỏi rất tự nhiên và đáng hỏi. Câu trả lời ngắn: **ta định nghĩa $L = T-U$ vì nó cho kết quả đúng** (khớp với $F=ma$ đã biết) — đây không phải một định lý suy ra từ cái gì sâu hơn ở mức phổ thông, mà là một **tiên đề** (giống như $F=ma$ cũng là tiên đề). Cái sâu hơn ($L=T-U$ đến từ đâu) thuộc về tương đối hẹp/QFT và nằm ngoài phạm vi nhập môn này — nhưng bạn có thể tự kiểm chứng ở Chương 3 rằng chọn $L=T-U$ cho ra đúng $F=ma$, còn $L=T+U$ thì không.

---

# CHƯƠNG 3 — PHƯƠNG TRÌNH EULER–LAGRANGE: SUY LUẬN CHI TIẾT

Đây là phép tính quan trọng nhất của toàn tài liệu. Đọc chậm, viết lại bằng tay nếu cần.

## 3.1. Thiết lập

Ta có $S[q] = \int_{t_1}^{t_2} L(q,\dot q, t)\,dt$. Xét đường đi lân cận:
$$q_\epsilon(t) = q(t) + \epsilon\, \eta(t), \qquad \eta(t_1)=\eta(t_2)=0$$
với $\epsilon$ nhỏ, $\eta(t)$ là một hàm **tuỳ ý** (đây là điểm mấu chốt — ta sẽ dùng tính tuỳ ý của $\eta$ sau).

Khi đó $\dot q_\epsilon(t) = \dot q(t) + \epsilon\, \dot\eta(t)$.

## 3.2. Khai triển $S[q_\epsilon]$ theo $\epsilon$

$$S[q_\epsilon] = \int_{t_1}^{t_2} L(q+\epsilon\eta,\ \dot q+\epsilon\dot\eta,\ t)\, dt$$

Khai triển Taylor $L$ theo $\epsilon$ ở bậc nhất (giống hệt khai triển $f(x+\epsilon)$ ở mục 1.1, nhưng $L$ có hai "biến" $q$ và $\dot q$ nên dùng đạo hàm riêng):
$$L(q+\epsilon\eta, \dot q+\epsilon\dot\eta, t) \approx L(q,\dot q,t) + \frac{\partial L}{\partial q}\,\epsilon\eta + \frac{\partial L}{\partial \dot q}\,\epsilon\dot\eta$$

Vậy:
$$S[q_\epsilon] - S[q] \approx \epsilon \int_{t_1}^{t_2} \left(\frac{\partial L}{\partial q}\eta + \frac{\partial L}{\partial \dot q}\dot\eta\right) dt \equiv \epsilon\, \delta S$$

**Điều kiện dừng:** $\delta S = 0$ với **mọi** $\eta(t)$ hợp lệ.

## 3.3. Khử $\dot\eta$ bằng tích phân từng phần

Vấn đề: số hạng thứ hai chứa $\dot\eta$, không phải $\eta$, nên chưa thể dùng trực tiếp "tuỳ ý $\eta$ ⇒ hệ số triệt tiêu". Ta tích phân từng phần:
$$\int_{t_1}^{t_2} \frac{\partial L}{\partial \dot q}\,\dot\eta\, dt = \left[\frac{\partial L}{\partial \dot q}\,\eta\right]_{t_1}^{t_2} - \int_{t_1}^{t_2} \frac{d}{dt}\!\left(\frac{\partial L}{\partial \dot q}\right)\eta\, dt$$

Số hạng biên $\left[\frac{\partial L}{\partial \dot q}\eta\right]_{t_1}^{t_2}$ **bằng 0** vì $\eta(t_1)=\eta(t_2)=0$ (đây là lý do ta *bắt buộc* giữ cố định hai đầu mút khi biến phân — nếu không, số hạng biên này sẽ sinh ra thêm điều kiện khác, chính là nguồn gốc của định lý Noether ở Chương 8!).

Vậy:
$$\delta S = \int_{t_1}^{t_2} \left(\frac{\partial L}{\partial q} - \frac{d}{dt}\frac{\partial L}{\partial \dot q}\right)\eta(t)\, dt$$

## 3.4. Bổ đề cơ bản của phép tính biến phân

**Bổ đề:** Nếu $\int_{t_1}^{t_2} g(t)\,\eta(t)\,dt = 0$ với **mọi** hàm $\eta(t)$ triệt tiêu ở hai đầu, thì $g(t) \equiv 0$ trên toàn khoảng.

*Trực giác (không cần chứng minh chặt chẽ để dùng):* nếu $g(t_0) \neq 0$ tại một điểm nào đó, ta luôn chọn được $\eta(t)$ "gồ" dương quanh $t_0$ và bằng 0 ở nơi khác, khi đó tích phân sẽ cùng dấu với $g(t_0)$, khác 0 — mâu thuẫn. Vậy $g$ phải bằng 0 ở mọi nơi.

Áp bổ đề này vào $\delta S = 0$ với $g(t) = \frac{\partial L}{\partial q} - \frac{d}{dt}\frac{\partial L}{\partial \dot q}$, ta được:

$$\boxed{\frac{d}{dt}\left(\frac{\partial L}{\partial \dot q}\right) - \frac{\partial L}{\partial q} = 0}$$

Đây là **phương trình Euler–Lagrange**. Đây là "công cụ vạn năng": với *bất kỳ* hệ nào, chỉ cần viết đúng $L=T-U$ theo toạ độ bạn chọn, công thức này tự động sinh ra phương trình chuyển động đúng — không cần vẽ lực, không cần đoán phản lực.

## 3.5. Kiểm chứng: lấy lại đúng $F=ma$

Hạt khối lượng $m$ chuyển động 1D dưới thế năng $U(x)$:
$$T = \tfrac12 m\dot x^2, \qquad L = \tfrac12 m\dot x^2 - U(x)$$
$$\frac{\partial L}{\partial \dot x} = m\dot x \quad\Rightarrow\quad \frac{d}{dt}\frac{\partial L}{\partial \dot x} = m\ddot x$$
$$\frac{\partial L}{\partial x} = -\frac{\partial U}{\partial x}$$
Euler–Lagrange: $m\ddot x - \left(-\frac{\partial U}{\partial x}\right) = 0 \Rightarrow m\ddot x = -\frac{\partial U}{\partial x} = F$.

**Chính xác $F=ma$.** Đây là bằng chứng (không phải chứng minh toán học đầy đủ, nhưng là kiểm chứng thuyết phục) rằng nguyên lý tác dụng tối thiểu với $L=T-U$ tương thích với Newton. Và thử lại với $L = T+U$: bạn sẽ ra $m\ddot x = +\partial U/\partial x$ — **sai dấu**, sai vật lý. Đó là lý do $L=T-U$ chứ không phải $T+U$.

---

# CHƯƠNG 4 — ÁP DỤNG: NĂM VÍ DỤ DỰNG LAGRANGIAN TỪ SỐ 0

Quy trình chuẩn, luôn giống nhau, **không cần trực giác** ở bước này:
1. Chọn toạ độ $q$ mô tả đủ hệ (ít toạ độ nhất có thể, tôn trọng ràng buộc).
2. Viết $T$ (động năng) theo $q, \dot q$.
3. Viết $U$ (thế năng) theo $q$.
4. $L = T - U$.
5. Áp Euler–Lagrange: $\dfrac{d}{dt}\dfrac{\partial L}{\partial \dot q} - \dfrac{\partial L}{\partial q} = 0$.

## Ví dụ 1 — Vật rơi tự do (kiểm tra sanity)

$q = y$ (độ cao), $T=\tfrac12 m\dot y^2$, $U = mgy$.
$$L = \tfrac12 m\dot y^2 - mgy$$
$$\frac{\partial L}{\partial \dot y} = m\dot y \Rightarrow \frac{d}{dt}(m\dot y) = m\ddot y; \qquad \frac{\partial L}{\partial y} = -mg$$
$$m\ddot y - (-mg) = 0 \Rightarrow \ddot y = -g$$
Đúng như mong đợi.

## Ví dụ 2 — Dao động điều hoà (lò xo)

$q=x$, $T=\tfrac12 m\dot x^2$, $U=\tfrac12 kx^2$.
$$L = \tfrac12 m\dot x^2 - \tfrac12 kx^2$$
$$\frac{d}{dt}(m\dot x) - (-kx) = 0 \Rightarrow m\ddot x + kx = 0 \Rightarrow \ddot x = -\frac{k}{m}x$$
Đúng phương trình dao động điều hoà quen thuộc, $\omega^2 = k/m$.

## Ví dụ 3 — Con lắc đơn (đây là chỗ Lagrangian bắt đầu "toả sáng")

Cách Newton: bạn phải vẽ trọng lực, sức căng dây $T$, chiếu lên phương tiếp tuyến, **và phải khử $T$** bằng phương trình hướng tâm — hai bước, dễ sai dấu.

Cách Lagrangian: chọn luôn $q=\theta$ (góc lệch), đây **đã là** toạ độ tôn trọng ràng buộc "dây không dãn dài $l$" — ta không cần nói gì về sức căng dây cả, nó tự động biến mất vì nó không sinh công dọc theo ràng buộc.

Vị trí vật: $x = l\sin\theta$, $y = -l\cos\theta$ (gốc tại điểm treo, chiều dương xuống).
$$\dot x = l\dot\theta\cos\theta, \qquad \dot y = l\dot\theta\sin\theta$$
$$v^2 = \dot x^2+\dot y^2 = l^2\dot\theta^2(\cos^2\theta+\sin^2\theta) = l^2\dot\theta^2$$
$$T = \tfrac12 m l^2\dot\theta^2, \qquad U = -mgl\cos\theta \ (\text{thế năng, lấy mốc tại điểm treo})$$
$$L = \tfrac12 ml^2\dot\theta^2 + mgl\cos\theta$$
Euler–Lagrange theo $\theta$:
$$\frac{\partial L}{\partial \dot\theta} = ml^2\dot\theta \Rightarrow \frac{d}{dt}(ml^2\dot\theta) = ml^2\ddot\theta$$
$$\frac{\partial L}{\partial \theta} = -mgl\sin\theta$$
$$ml^2\ddot\theta - (-mgl\sin\theta) = 0 \Rightarrow \ddot\theta = -\frac{g}{l}\sin\theta$$
Đúng phương trình con lắc đơn chuẩn — **không một lần nào ta phải nhắc đến sức căng dây T**. Đây chính xác là điều "Một Sợi Chỉ Xuyên Suốt" nói ở mục 1.2: *"bạn không cần tính lực căng dây, lực pháp tuyến gì cả"*.

Với góc nhỏ $\sin\theta \approx \theta$: $\ddot\theta = -\frac{g}{l}\theta$ ⇒ $\omega^2 = g/l$, công thức con lắc đơn quen thuộc, suy ra trong vài dòng.

## Ví dụ 4 — Hạt trên mặt phẳng nghiêng, không ma sát (kiểm tra thêm)

$q=s$ (quãng đường dọc mặt nghiêng góc $\alpha$). $T=\tfrac12 m\dot s^2$, độ cao giảm $h = s\sin\alpha$ (lấy chiều $s$ tăng là đi xuống) nên $U = -mgs\sin\alpha$.
$$L = \tfrac12 m\dot s^2 + mgs\sin\alpha$$
$$m\ddot s - mg\sin\alpha = 0 \Rightarrow \ddot s = g\sin\alpha$$
Khớp hoàn toàn kết quả phân tích lực truyền thống — nhưng lần này ta **không hề vẽ** phản lực pháp tuyến $N$, vì nó không sinh công dọc theo ràng buộc (mặt phẳng), đúng tinh thần Chương 2.

## Ví dụ 5 — Hệ hai vật nối qua ròng rọc (máy Atwood) — nơi thấy rõ sức mạnh so với Newton

Hai vật $m_1, m_2$ nối dây qua ròng rọc nhẹ, không ma sát. Dây không dãn ⇒ **chỉ một bậc tự do**: khi $m_1$ đi xuống đoạn $x$ thì $m_2$ đi lên đoạn $x$. Chọn $q=x$.

$$T = \tfrac12 m_1\dot x^2 + \tfrac12 m_2\dot x^2 = \tfrac12(m_1+m_2)\dot x^2$$
$$U = -m_1 g x + m_2 g x = -(m_1-m_2)gx$$
(vật 1 hạ độ cao $x$ ⇒ U giảm $m_1gx$; vật 2 tăng độ cao $x$ ⇒ U tăng $m_2gx$.)
$$L = \tfrac12(m_1+m_2)\dot x^2 + (m_1-m_2)gx$$
$$(m_1+m_2)\ddot x - (m_1-m_2)g = 0 \Rightarrow \ddot x = \frac{(m_1-m_2)g}{m_1+m_2}$$

Đúng công thức máy Atwood chuẩn — đạt được **không cần vẽ sức căng dây $T$ hai lần cho hai vật rồi khử nó**. Với Newton, bạn phải viết 2 phương trình (một cho mỗi vật), chứa ẩn $T$, rồi cộng/trừ để khử $T$. Với Lagrangian, bạn viết **một** $L$ và sức căng không bao giờ xuất hiện.

---

# CHƯƠNG 5 — VÌ SAO TOẠ ĐỘ SUY RỘNG LÀ "VŨ KHÍ TỐI THƯỢNG"

## 5.1. Phát biểu then chốt

Phương trình Euler–Lagrange **giữ nguyên dạng** dưới mọi phép đổi toạ độ $q \to Q(q)$ bất kỳ — bạn không cần "quy đổi lực" qua toạ độ cong như khi dùng Newton trực tiếp (nhớ lại Thẻ K5/K7 trong thư viện Cơ học của bạn: toạ độ cực có số hạng ly tâm $-r\dot\phi^2$ và Coriolis $2\dot r\dot\phi$ "thuần tuý do toán học của hệ toạ độ" — với Lagrangian, những số hạng này **tự động xuất hiện đúng** khi bạn viết $T$ bằng toạ độ cực, không cần nhớ công thức gia tốc trong toạ độ cực).

**Hệ quả thực chiến:** bạn được *tự do tuyệt đối* chọn toạ độ nào tiện nhất — miễn nó mô tả đủ hệ, mọi lực liên kết lý tưởng (sức căng dây không dãn, phản lực pháp tuyến của mặt nhẵn, phản lực trục quay không ma sát) **tự động biến mất** khỏi phương trình, vì chúng không sinh công dọc theo chuyển động được ràng buộc cho phép.

## 5.2. Ví dụ: con lắc đơn gắn trên xe đang chuyển động — Newton sẽ rất khó, Lagrangian thì không

Xe chuyển động ngang với gia tốc $a(t)$ đã cho (ép buộc, không phải ẩn). Con lắc dài $l$, khối lượng $m$, treo trên xe. Hỏi phương trình chuyển động của góc lệch $\theta$.

**Với Newton:** bạn phải chuyển sang hệ quy chiếu phi quán tính gắn với xe, thêm lực quán tính $-ma$, rồi chiếu lên phương tiếp tuyến, khử sức căng dây — nhiều bước, dễ sai dấu lực quán tính.

**Với Lagrangian — không cần nghĩ về "lực quán tính" chút nào:** Vị trí xe là $x_0(t)$ (đã biết, $\ddot x_0 = a(t)$). Vị trí vật nặng:
$$x = x_0(t) + l\sin\theta, \qquad y = -l\cos\theta$$
$$\dot x = \dot x_0 + l\dot\theta\cos\theta, \qquad \dot y = l\dot\theta\sin\theta$$
$$v^2 = \dot x_0^2 + 2l\dot x_0\dot\theta\cos\theta + l^2\dot\theta^2$$
$$T = \tfrac12 m\left(\dot x_0^2 + 2l\dot x_0\dot\theta\cos\theta + l^2\dot\theta^2\right), \qquad U = -mgl\cos\theta$$
$$L = \tfrac12 m\dot x_0^2 + ml\dot x_0\dot\theta\cos\theta + \tfrac12 ml^2\dot\theta^2 + mgl\cos\theta$$
Áp Euler–Lagrange theo $\theta$ (chú ý $\dot x_0$ là hàm đã biết của $t$, không phải ẩn):
$$\frac{\partial L}{\partial\dot\theta} = ml\dot x_0\cos\theta + ml^2\dot\theta$$
$$\frac{d}{dt}\left(\frac{\partial L}{\partial\dot\theta}\right) = ml\ddot x_0\cos\theta - ml\dot x_0\dot\theta\sin\theta + ml^2\ddot\theta$$
$$\frac{\partial L}{\partial\theta} = -ml\dot x_0\dot\theta\sin\theta - mgl\sin\theta$$
Euler–Lagrange:
$$ml\ddot x_0\cos\theta - ml\dot x_0\dot\theta\sin\theta + ml^2\ddot\theta - \left(-ml\dot x_0\dot\theta\sin\theta - mgl\sin\theta\right) = 0$$
Hai số hạng $-ml\dot x_0\dot\theta\sin\theta$ triệt tiêu lẫn nhau (một dấu cộng một dấu trừ khi chuyển vế) — **đây chính là việc toán học tự loại bỏ cho bạn thứ mà nếu làm tay bằng Newton bạn phải tự nhận ra và xử lý khéo léo.** Kết quả gọn:
$$l\ddot\theta + \ddot x_0\cos\theta + g\sin\theta = 0 \quad\Rightarrow\quad \ddot\theta = -\frac{g\sin\theta + a(t)\cos\theta}{l}$$

So sánh với kết quả "chuẩn" trong thư viện D9 của bạn ($g_{eff} = g - a_0$, với góc nhỏ $\tan\varphi = a/g$): đặt $\theta$ nhỏ, $\cos\theta\approx1,\sin\theta\approx\theta$: $\ddot\theta \approx -\frac{g\theta + a(t)}{l}$ — vị trí cân bằng mới dịch tới $\theta_0 = -a/g$ ($\tan\varphi\approx a/g$ với dấu phù hợp), khớp với bảng thư viện D9/D4 "con lắc trong xe" bạn đã có. **Ta vừa tự suy ra công cụ D9 từ số 0, không cần tra bảng.**

## 5.3. Bài học rút ra

Bất cứ khi nào bạn thấy trong thư viện của mình một dòng dạng "Thẻ XX — Pre: ràng buộc phức tạp, hệ nhiều vật" — đó chính là **lời mời dùng Lagrangian thay vì Newton**. Quy tắc kinh nghiệm (đã có trong tài liệu gốc của bạn, nay bạn hiểu *vì sao* nó đúng): nếu hệ có **≥ 2 vật tương tác qua ràng buộc**, hoặc ràng buộc **phụ thuộc thời gian** (xe, nêm di động, vòng quay), hãy luôn thử Lagrangian trước.

---

# CHƯƠNG 6 — RÀNG BUỘC VÀ NHÂN TỬ LAGRANGE

## 6.1. Khi nào bạn *cần* biết lực liên kết?

Chương 4–5 cho thấy Lagrangian **xoá** lực liên kết khỏi bài toán. Nhưng đôi khi đề hỏi chính lực đó (ví dụ: "tính sức căng dây tại thời điểm con lắc ở đáy", "dây có bị đứt không nếu lực căng tối đa là X"). Khi đó bạn cần một kỹ thuật khác: **nhân tử Lagrange**.

## 6.2. Ý tưởng

Thay vì *loại bỏ* ràng buộc bằng cách chọn toạ độ tối thiểu (như Chương 4–5), ta **giữ nguyên** toạ độ dư thừa, viết ràng buộc dưới dạng $f(q,t)=0$, rồi sửa Euler–Lagrange thành:
$$\frac{d}{dt}\frac{\partial L}{\partial \dot q_i} - \frac{\partial L}{\partial q_i} = \lambda \frac{\partial f}{\partial q_i}$$
với $\lambda(t)$ là một ẩn mới (nhân tử Lagrange) — và **$\lambda$ chính là lực liên kết** (sai khác một hệ số hình học).

## 6.3. Ví dụ: tìm sức căng dây của con lắc đơn tại góc $\theta$ bất kỳ

Giữ cả $r$ và $\theta$ làm toạ độ (không rút gọn), với ràng buộc $f(r) = r - l = 0$.

$$T = \tfrac12 m(\dot r^2 + r^2\dot\theta^2), \qquad U = -mgr\cos\theta$$
$$L = \tfrac12 m(\dot r^2+r^2\dot\theta^2) + mgr\cos\theta$$

Phương trình theo $r$ với nhân tử $\lambda$ (hệ số $\partial f/\partial r = 1$):
$$\frac{d}{dt}(m\dot r) - \left(mr\dot\theta^2 + mg\cos\theta\right) = \lambda$$
Sau khi áp ràng buộc $r=l$ (nên $\dot r=\ddot r=0$):
$$-ml\dot\theta^2 - mg\cos\theta = \lambda$$

Nhân tử $\lambda$ ở đây đóng vai trò $-T_{dây}$ (sức căng, dấu âm vì dây chỉ kéo vào tâm). Dùng $\dot\theta^2 = v^2/l^2$ và bảo toàn năng lượng ($v^2 = 2gl(\cos\theta-\cos\theta_0)$ từ Chương 8 bạn sẽ tự suy), ta ra lại đúng công thức quen thuộc $T_{dây} = mg(3\cos\theta - 2\cos\theta_0)$ đã có trong thư viện D6 của bạn — **tự suy từ số 0**, không tra bảng.

**Khi nào dùng nhân tử thay vì rút gọn toạ độ?** Duy nhất khi đề *hỏi trực tiếp* về lực liên kết. Mặc định luôn rút gọn toạ độ (Chương 4–5) vì nhanh hơn nhiều.

---

# CHƯƠNG 7 — HAMILTON: ĐỔI BIẾN LEGENDRE, KHÔNG GIAN PHA

## 7.1. Động lượng suy rộng

Định nghĩa:
$$p \equiv \frac{\partial L}{\partial \dot q}$$

Với hạt thường, $p = m\dot x$ — chính là động lượng quen thuộc. Nhưng với toạ độ góc, $p_\theta = \partial L/\partial\dot\theta$ là **mômen động lượng**, không phải động lượng thẳng! Đây là lý do "động lượng suy rộng" là khái niệm tổng quát hơn động lượng $mv$ thông thường — nó tự động cho đúng đại lượng bảo toàn tương ứng với từng toạ độ (sẽ thấy rõ ở Chương 8).

## 7.2. Phép biến đổi Legendre (giải thích bằng ví dụ số, không trừu tượng)

Cho hàm $L(\dot q)$ (giả sử không phụ thuộc $q,t$ để đơn giản). Phép biến đổi Legendre định nghĩa hàm mới $H(p)$ bằng:
$$H = p\dot q - L$$
trong đó $\dot q$ được **giải ngược** từ $p=\partial L/\partial\dot q$ theo $p$.

**Ví dụ cụ thể, bằng số:** $L = \tfrac12 m\dot q^2 - U(q)$.
$$p = m\dot q \ \Rightarrow\ \dot q = p/m$$
$$H = p\cdot\frac{p}{m} - \left(\tfrac12 m(p/m)^2 - U(q)\right) = \frac{p^2}{m} - \frac{p^2}{2m} + U(q) = \frac{p^2}{2m} + U(q)$$

**$H$ chính là năng lượng toàn phần $T+U$ viết theo $(q,p)$ thay vì $(q,\dot q)$.** Đây là lý do Hamiltonian "thường chính là năng lượng" như file gốc đã nói.

## 7.3. Phương trình Hamilton

Có thể chứng minh (bỏ qua chi tiết đại số, chỉ cần nhớ kết quả vì đây không phải trọng tâm nhập môn):
$$\dot q = \frac{\partial H}{\partial p}, \qquad \dot p = -\frac{\partial H}{\partial q}$$

**Kiểm tra nhanh với ví dụ trên:** $H = p^2/2m + U(q)$.
$$\dot q = \frac{\partial H}{\partial p} = \frac{p}{m} \ \checkmark \ (\text{đúng định nghĩa } p=m\dot q)$$
$$\dot p = -\frac{\partial H}{\partial q} = -\frac{\partial U}{\partial q} = F \ \Rightarrow\ m\ddot q = F \ \checkmark$$

Khớp $F=ma$ lần nữa, từ một con đường khác.

## 7.4. Vì sao Hamilton hữu ích (mức nhập môn)

- $H$ thường **chính là năng lượng**, nên viết được $H$ là có ngay công cụ "năng lượng hiệu dụng" (Thẻ C5, C7 trong thư viện của bạn) mà không cần đoán.
- Hệ phương trình Hamilton là hệ **bậc nhất** (so với Euler–Lagrange là bậc hai) — thuận tiện hơn cho phân tích không gian pha $(q,p)$, dao động nhỏ, và là cầu nối trực tiếp sang Cơ học Lượng tử (phép lượng tử hoá $p \to -i\hbar\,\partial_q$ — chi tiết trong file gốc "Một Sợi Chỉ Xuyên Suốt" Phần 7, không lặp lại ở đây).

---

# CHƯƠNG 8 — ĐỊNH LÝ NOETHER: TRÁI TIM CỦA TOÀN BỘ VẬT LÝ

Đây là chương quan trọng nhất về mặt "lợi thế cực lớn". Đọc kỹ.

## 8.1. Câu hỏi Noether trả lời

Vì sao động lượng bảo toàn khi không có ngoại lực theo một phương? Vì sao mômen động lượng bảo toàn với lực xuyên tâm? Vì sao năng lượng bảo toàn khi lực không phụ thuộc thời gian tường minh? Sách giáo khoa dạy ba câu trả lời này như **ba sự kiện độc lập, phải học thuộc riêng**. Noether chỉ ra: **chúng là MỘT hiện tượng**, nhìn từ ba góc khác nhau.

## 8.2. Phát biểu

> **Mỗi đối xứng liên tục của Lagrangian (một phép biến đổi toạ độ làm $L$ không đổi) sinh ra đúng một đại lượng bảo toàn theo thời gian.**

"Đối xứng liên tục" nghĩa là một họ phép biến đổi phụ thuộc một tham số liên tục $\epsilon$ (ví dụ: dịch chuyển một đoạn $\epsilon$, quay một góc $\epsilon$) sao cho $\epsilon=0$ là phép đồng nhất.

## 8.3. Chứng minh chi tiết (chậm hơn bản gốc, có giải thích từng bước)

Giả sử có phép biến đổi $q \to q + \epsilon K(q)$ (với $\epsilon$ nhỏ, $K(q)$ là "hướng" của phép biến đổi — ví dụ $K=1$ cho tịnh tiến, $K(q)=$ vuông góc bán kính cho phép quay) sao cho **$L$ không đổi** dưới phép biến đổi này, tức $\delta L = 0$.

Tính $\delta L$ bằng khai triển Taylor (giống hệt kỹ thuật Chương 3):
$$\delta L = \frac{\partial L}{\partial q}\cdot \epsilon K + \frac{\partial L}{\partial \dot q}\cdot \epsilon \dot K$$

(ở đây $\dot K = \frac{d}{dt}K(q(t)) = K'(q)\dot q$ — tốc độ thay đổi của "hướng dịch chuyển" dọc quỹ đạo thật).

Giả thiết đối xứng: $\delta L = 0$, tức:
$$\frac{\partial L}{\partial q}K + \frac{\partial L}{\partial \dot q}\dot K = 0 \tag{*}$$

Bây giờ, **vì quỹ đạo $q(t)$ là quỹ đạo THẬT** (đã thoả Euler–Lagrange từ Chương 3), ta có:
$$\frac{\partial L}{\partial q} = \frac{d}{dt}\frac{\partial L}{\partial \dot q}$$
(đây chính là phương trình Euler–Lagrange viết lại). Thay vào (*):
$$\frac{d}{dt}\left(\frac{\partial L}{\partial\dot q}\right) K + \frac{\partial L}{\partial \dot q}\dot K = 0$$

Nhìn vế trái: đây **chính xác** là đạo hàm của một tích theo quy tắc Leibniz $\frac{d}{dt}(uv) = \dot u v + u\dot v$ với $u = \frac{\partial L}{\partial \dot q}$, $v=K$:
$$\frac{d}{dt}\left(\frac{\partial L}{\partial \dot q}\cdot K\right) = 0$$

Nhớ lại $p \equiv \partial L/\partial \dot q$ (Chương 7). Vậy:
$$\boxed{\frac{d}{dt}\big(p\cdot K(q)\big) = 0 \quad\Rightarrow\quad Q \equiv p\cdot K(q) = \text{hằng số theo thời gian}}$$

**Đây là chứng minh đầy đủ.** Mọi ứng dụng dưới đây chỉ là chọn $K$ cụ thể.

## 8.4. Bốn ứng dụng, tính tay từng cái

### (a) Tịnh tiến ⇒ bảo toàn động lượng

Lấy $K=1$ (phép dịch chuyển $q\to q+\epsilon$ đơn giản). Nếu $L$ không đổi dưới dịch chuyển này (tức $\partial L/\partial q = 0$ — $L$ không phụ thuộc tường minh vào $q$, chỉ phụ thuộc $\dot q$), thì theo công thức trên:
$$Q = p\cdot 1 = p = \text{const}$$
**Động lượng bảo toàn.** Kiểm tra bằng hạt tự do: $L=\tfrac12 m\dot x^2$ không chứa $x$ ⇒ $p=m\dot x$ bảo toàn. Đúng.

### (b) Quay ⇒ bảo toàn mômen động lượng

Xét hạt trong mặt phẳng, toạ độ cực $(r,\phi)$. Phép quay là $\phi \to \phi + \epsilon$ (tức $K=1$ theo biến $\phi$). Nếu $L$ không phụ thuộc tường minh $\phi$ (đúng khi lực xuyên tâm, vì thế năng chỉ phụ thuộc $r$):
$$p_\phi \equiv \frac{\partial L}{\partial \dot\phi} = \text{const}$$
Với $T=\tfrac12 m(\dot r^2+r^2\dot\phi^2)$: $p_\phi = mr^2\dot\phi$ — **chính là mômen động lượng** $L=mr^2\dot\phi$ (ký hiệu trùng tên với Lagrangian nhưng khác nghĩa, cẩn thận). Đây **chính là** nguồn gốc của "tốc độ quét diện tích không đổi" (định luật Kepler II) trong thư viện C7/Thẻ 9 của bạn: $dA/dt = \tfrac12 r^2\dot\phi = p_\phi/(2m) = $ const — **suy ra trực tiếp từ đối xứng quay, không cần tích phân quỹ đạo**, đúng như file gốc đã nói ở mục 2.3.

### (c) Dịch thời gian ⇒ bảo toàn năng lượng

Đây là trường hợp cần xử lý hơi khác (biến đổi theo $t$ chứ không theo $q$), nhưng kết quả đáng nhớ: nếu $L$ không phụ thuộc tường minh vào $t$ (tức $\partial L/\partial t = 0$), thì $H = p\dot q - L$ (Chương 7) là **hằng số theo thời gian**. Vì $H$ thường chính là năng lượng $T+U$, đây chính là **bảo toàn cơ năng** — một định luật bạn đã quen từ phổ thông, nay thấy nó là **cùng một cơ chế** với bảo toàn động lượng và mômen động lượng.

### (d) Đối xứng gauge ⇒ bảo toàn điện tích (chỉ nêu, không đi sâu — thuộc file gốc Phần 5.2)

Đây là ví dụ cho thấy Noether không chỉ áp dụng cho không-thời gian — nó áp dụng cho **bất kỳ** phép biến đổi nào giữ $L$ bất biến, kể cả phép biến đổi "nội tại" (pha của trường điện từ). Chi tiết đã có trong file "Một Sợi Chỉ Xuyên Suốt" của bạn, không lặp lại.

## 8.5. Vì sao điều này "hiển nhiên hoá" đề thi

Bây giờ quy trình đọc một bài va chạm/hệ phức tạp **không còn là** "nhớ xem công thức nào áp dụng được" mà là:

> **Hỏi: hệ này có đối xứng gì?**
> - Không ma sát theo phương ngang ⟹ $L$ không phụ thuộc toạ độ ngang ⟹ động lượng ngang bảo toàn.
> - Lực xuyên tâm ⟹ $L$ không phụ thuộc góc ⟹ mômen động lượng quanh tâm bảo toàn.
> - Thế năng không phụ thuộc thời gian ⟹ $H$ không phụ thuộc $t$ ⟹ năng lượng bảo toàn.

Đây **chính xác** là quy trình "duyệt đối xứng" trong Thẻ C8 của thư viện Cơ học bạn đã có — giờ bạn hiểu *tại sao* nó hoạt động, không chỉ *rằng* nó hoạt động.

---

# CHƯƠNG 9 — CÁCH MỘT RESEARCHER ĐỌC MỘT BÀI TOÁN MỚI

Đây là quy trình thao tác được, nối trực tiếp "Vấn đề tìm kiếm" của bạn với những gì vừa học.

## 9.1. Quy trình năm bước

**Bước 1 — Đếm bậc tự do.** Hệ có bao nhiêu toạ độ độc lập sau khi trừ ràng buộc? (Thẻ 7, tài liệu "Cơ học Vật rắn" của bạn đã có bảng "ràng buộc → phương trình" — dùng lại y nguyên.)

**Bước 2 — Chọn toạ độ suy rộng.** Chọn sao cho mỗi ràng buộc trở thành "một toạ độ = hằng số" (tiêu chí đã có sẵn trong thư viện của bạn ở Thẻ 7 "Các hệ toạ độ" — giờ bạn biết *vì sao* tiêu chí đó đúng: nó tối thiểu hoá công sức viết $T, U$).

**Bước 3 — Viết $T$ và $U$.** Đây là bước duy nhất cần một chút cẩn thận hình học (tính vận tốc từng vật theo $\dot q$). Không cần vẽ lực.

*Thay vì viết L, thông thường HSGQG Lý nên xài biểu thức Động năng (W_đ hoặc T) và Công của ngoại lực. Do ở HSGQG, rất nhiều bài có ma sát hoặc va chạm mất mát năng lượng, lúc đó ta cần hàm tiêu tán Rayleigh, vốn không có trong chương trình phổ thông. Đừng viết chữ L:), trừ khi thật sự cần, dù có vẻ gần như không thể xảy ra.

**Bước 4 — TRƯỚC KHI viết Euler–Lagrange, hỏi về đối xứng (Chương 8).** Đối xứng nào có mặt cho bạn **ngay lập tức** một đại lượng bảo toàn — tức **một phương trình miễn phí**, bậc thấp hơn (đại số, không phải ODE bậc 2) so với phải giải Euler–Lagrange đầy đủ.

*Dùng tư duy này để chọn định luật bảo toàn. Đừng viết chữ "Noether" ra giấy.

**Bước 5 — Với phần còn lại (không có đối xứng tương ứng), mới áp Euler–Lagrange đầy đủ.**

*Ý tôi là: Phương trình Euler-Lagrange chính là định lý động năng hay định luật II Newton viết theo tọa độ suy rộng. Bạn dùng nó ở nháp để kiểm tra dấu, nhưng khi viết vào bài, bạn viết:

Độ biến thiên W_đ = A_ngoại lực (nếu cần năng lượng).

Hay F_hl = ma (nếu cần gia tốc).

Hoặc phương trình hướng tâm (nếu cần tìm lực liên kết).

...

*Đúng nghĩa học cách tư duy và giảm không gian tìm kiếm, cũng như bản chất:), chứ phòng thi có ai xài Lagrange đâu.

## 9.2. Vì sao thứ tự "đối xứng trước, phương trình chuyển động sau" lại quan trọng

Nếu bạn áp Euler–Lagrange ngay (Bước 5 trước), bạn ra một hệ ODE bậc 2 — phải giải (tích phân hai lần, hoặc giải số). Nếu bạn áp Noether trước (Bước 4), với *mỗi toạ độ cyclic* (không xuất hiện tường minh trong $L$) bạn có ngay **một tích phân đầu** (first integral) — một phương trình bậc 1, thường **đại số được**, không cần giải ODE nữa. Đây chính xác là kỹ thuật "thế năng hiệu dụng" trong Thẻ 9 (Kepler) và Thẻ C5 (Đồ thị thế năng 1D) của thư viện bạn: bảo toàn $L$ (mômen động lượng) và $E$ biến bài 2D thành bài 1D $E = \tfrac12 m\dot r^2 + U_{eff}(r)$ — **giảm bậc tự do hiệu dụng bằng cách khai thác đối xứng trước khi giải**.

## 9.3. Liên hệ với "Vấn đề tìm kiếm"

Nhắc lại khung hình thức $M=(O,V,L,C,Q,I)$ trong tài liệu gốc của bạn. Với first principles, danh sách công cụ $L$ (viết hoa, khác Lagrangian $L$ viết trong công thức — chú ý tránh nhầm lẫn ký hiệu khi đọc hai tài liệu song song) co lại còn **đúng hai mục**:

$$L = \{\text{Euler–Lagrange}, \text{Noether}\}$$

Và "CHỖ" để áp dụng chúng không còn là một danh sách hàng trăm dòng Pre/Suf cần tra — nó chỉ còn là: *mọi toạ độ* (cho Euler–Lagrange) và *mọi đối xứng của $L$* (cho Noether). Đây là "quá ít công cụ để thắc mắc bản thân cần dùng công cụ vật lý nào" — đúng như bạn mô tả trong câu hỏi gốc, và giờ nó không còn là một khẳng định niềm tin mà là một **hệ quả toán học bạn tự tay suy ra được**.

**Thành thật về giới hạn:** thư viện hàng nghìn dòng bạn đã xây (HSGQG) **vẫn cần thiết**, vì: (i) trong phòng thi, việc *nhận ra ngay* công thức Kepler/con lắc vật lý/áp suất tĩnh điện mà không phải tự suy từ Lagrangian mỗi lần sẽ nhanh hơn rất nhiều; (ii) một số bài chỉ cho dữ kiện dạng lực/phản lực cụ thể (không phải đề cho $T,U$) nên bạn vẫn cần thành thạo cách dịch "lời đề → $T,U$". First principles không thay thế việc luyện tập — nó là **lớp nền đảm bảo bạn hiểu *vì sao* mọi công thức trong thư viện đúng**, để khi gặp biến tấu chưa từng thấy, bạn tự suy ra được thay vì bí.

---

# CHƯƠNG 10 — MỞ RỘNG RA TOÀN BỘ VẬT LÝ (BẢN ĐỒ TỔNG, NGẮN GỌN)

Chương này chỉ tóm tắt rất ngắn, vì chi tiết đã có trong file "Một Sợi Chỉ Xuyên Suốt" bạn đã gửi — ở đây chỉ nối lại mạch logic để bạn thấy toàn cảnh sau khi đã hiểu Chương 1–9.

| Lĩnh vực | $L$ (hoặc nguyên lý biến phân tương ứng) | Những gì bạn vừa học áp dụng thế nào |
|---|---|---|
| Cơ học Newton | $L=T-U$ | Toàn bộ Chương 2–9 ở trên |
| Điện từ Maxwell | $L = -\tfrac14 F_{\mu\nu}F^{\mu\nu} - A_\mu J^\mu$ | Euler–Lagrange áp cho **trường** $A_\mu(x)$ thay vì hạt $q(t)$; Noether cho đối xứng gauge ⇒ bảo toàn điện tích |
| Tương đối hẹp | $L=-mc^2\sqrt{1-v^2/c^2}$ | Cùng Chương 3, chỉ đổi $L$; Legendre transform (Chương 7) cho $E=\gamma mc^2$ |
| Tương đối rộng | $L=-mc\int ds$ trên mêtric cong | Cùng nguyên lý dừng, không gian cấu hình là không-thời gian cong |
| Cơ học lượng tử | tích phân đường $e^{iS/\hbar}$, tổng trên mọi $q(t)$ | Nguyên lý tác dụng tối thiểu là giới hạn $\hbar\to0$ — chính là Chương 2 "xuất hiện lại" dưới dạng giao thoa triệt tiêu các đường không dừng |
| Nhiệt động/thống kê | cực đại $S=-k_B\sum p_i\ln p_i$ với ràng buộc | Dùng **đúng kỹ thuật nhân tử Lagrange** của Chương 6, chỉ đổi đối tượng tối ưu hoá từ $S$ (tác dụng) sang $S$ (entropy — trùng tên, khác nghĩa, đã cảnh báo trong file gốc) |

**Thông điệp:** bạn không học sáu lĩnh vực riêng biệt — bạn học **một kỹ thuật** (tìm điểm dừng của một phiếm hàm, dùng Euler–Lagrange, khai thác đối xứng bằng Noether) và áp nó sáu lần với sáu lựa chọn $L$ khác nhau.

---

# CHƯƠNG 11 — LỘ TRÌNH LUYỆN TẬP 10 TUẦN

Mục tiêu: biến hiểu biết lý thuyết ở trên thành phản xạ. Mỗi tuần nên dành ít nhất 2–3 buổi.

**Tuần 1.** Tự chứng minh lại Euler–Lagrange (Chương 3) bằng tay, không nhìn tài liệu, ít nhất 3 lần cho đến khi viết trôi chảy không vấp.

**Tuần 2.** Giải lại 10 bài cơ học bạn đã biết đáp số bằng Newton (phổ thông/HSGQG) — **chỉ bằng Lagrangian**. Gợi ý: bắt đầu từ các bài trong thư viện D-series (Động lực học) bạn đã có — máy Atwood các biến thể, con lắc trên nêm, vật trên nêm di động.

**Tuần 3.** Làm lại Ví dụ con lắc trên xe (Chương 5.2) nhưng với $a(t)$ là **hàm điều hoà** $a(t)=a_0\cos\Omega t$ — đây chính là bài "dao động cưỡng bức" Thẻ O6, giờ bạn tự suy phương trình vi phân chủ đạo thay vì tra công thức.

**Tuần 4.** Với mỗi bài đã giải ở Tuần 2–3, **trước khi giải**, viết ra "hệ này có đối xứng gì?" rồi tự suy định luật bảo toàn tương ứng bằng Noether (Chương 8), kiểm tra nó khớp với đáp số Lagrangian đầy đủ.

**Tuần 5.** Giải 5 bài dùng nhân tử Lagrange (Chương 6) để tìm lực liên kết — đối chiếu với kết quả "công thức có sẵn" trong thư viện D6, D2 của bạn.

**Tuần 6.** Viết lại Hamiltonian cho 5 hệ đã làm ở Tuần 2, vẽ không gian pha $(q,p)$ định tính cho dao động điều hoà và con lắc đơn (biên độ lớn) — quan sát quỹ đạo kín (dao động) so với quỹ đạo hở (quay vòng).

**Tuần 7.** Áp dụng Chương 9 (quy trình 5 bước) cho bài toán Kepler — tự suy $U_{eff}(r)$, tự suy $e, a, T^2\propto a^3$ từ hai bảo toàn ($L, E$) mà không tra Thẻ 9.

**Tuần 8.** Hệ dao động ghép (O7 trong thư viện bạn) — dựng $L$ cho hệ hai/ba vật nối lò xo, tự suy ma trận $M, K$, tự thấy $\det(K-\omega^2 M)=0$ xuất hiện tự nhiên từ Euler–Lagrange tuyến tính hoá.

**Tuần 9.** Đọc lại phần Điện từ trong file "Một Sợi Chỉ Xuyên Suốt" (Phần 3, 5), tự tay suy sóng điện từ từ 4 phương trình Maxwell (đã có mẫu trong file gốc) — chỉ để thấy cùng logic "Euler–Lagrange cho trường" hoạt động y hệt cơ học hạt.

**Tuần 10.** Chọn 5 đề thi thật (HSGQG/IPhO cũ) phần Cơ học — giải bằng quy trình Chương 9, đối chiếu thời gian làm bài và độ chắc chắn so với cách làm Newton thuần tuý trước đây.

---

# PHỤ LỤC — BẢNG TRA NHANH & CHECKLIST TỰ KIỂM TRA

## A. Công thức cốt lõi (toàn bộ Chương 1–8 trong một bảng)

| Khái niệm | Công thức |
|---|---|
| Lagrangian | $L = T - U$ |
| Tác dụng | $S=\int_{t_1}^{t_2} L\,dt$ |
| Euler–Lagrange | $\dfrac{d}{dt}\dfrac{\partial L}{\partial\dot q} - \dfrac{\partial L}{\partial q}=0$ |
| Động lượng suy rộng | $p=\partial L/\partial\dot q$ |
| Hamiltonian | $H=p\dot q - L$ |
| Phương trình Hamilton | $\dot q = \partial H/\partial p,\ \dot p=-\partial H/\partial q$ |
| Noether (dạng dùng được) | $L$ bất biến dưới $q\to q+\epsilon K(q)$ $\Rightarrow$ $p\cdot K(q)=$ const |
| Ràng buộc (nhân tử) | $\dfrac{d}{dt}\dfrac{\partial L}{\partial\dot q_i}-\dfrac{\partial L}{\partial q_i}=\lambda\dfrac{\partial f}{\partial q_i}$ |

## B. Checklist 5 bước khi gặp một bài cơ học mới (dùng ngay trong phòng thi)

1. [ ] Đếm bậc tự do, chọn toạ độ suy rộng tối thiểu.
2. [ ] Viết $T(q,\dot q)$, $U(q)$ — kiểm tra đã tính đúng vận tốc mọi vật theo $\dot q$ (đặc biệt khi có ràng buộc di động như xe, nêm).
3. [ ] Hỏi: toạ độ nào **không** xuất hiện tường minh trong $L$? ⇒ viết ngay động lượng suy rộng tương ứng là hằng số.
4. [ ] Hỏi: $L$ có phụ thuộc tường minh $t$ không? Nếu không ⇒ $H$ (thường là $E$) bảo toàn.
5. [ ] Với phần còn lại, áp Euler–Lagrange đầy đủ cho các toạ độ chưa cho tích phân đầu ở bước 3–4.

## C. Ba lỗi hay gặp khi mới học (tự kiểm tra)

1. **Quên ký hiệu $\partial L/\partial \dot q$ nghĩa là đạo hàm riêng theo $\dot q$, coi $q$ là hằng số khi lấy đạo hàm này** — và ngược lại cho $\partial L/\partial q$. Hai đạo hàm riêng này độc lập dù $q,\dot q$ "liên quan" qua đạo hàm thời gian.
2. **Quên nhân toạ độ Descartes của từng vật theo đúng $\dot q$ khi có ràng buộc di động** (như Ví dụ 5.2: quên số hạng chéo $\dot x_0\dot\theta$).
3. **Dùng Noether khi $L$ thực ra có phụ thuộc tường minh vào toạ độ đó** (ví dụ quên rằng với con lắc trên xe có $a(t)\neq0$, $\theta$ không cyclic, nên mômen động lượng góc quanh điểm treo **không** bảo toàn — phải kiểm tra kỹ $\partial L/\partial q = 0$ thật sự trước khi dùng Noether, đừng áp dụng theo quán tính).

---

*Hết phần nhập môn. Tài liệu này là nền móng; mọi thư viện HSGQG bạn đã có (Cơ, Nhiệt, Điện, Quang, Hạt nhân) giờ nên được đọc lại với câu hỏi: "công thức này tự suy ra từ Euler–Lagrange + Noether như thế nào?" — đó chính là cách biến một thư viện phải tra cứu thành một thư viện bạn **hiểu từ gốc**, và đó là lợi thế bạn đang tìm.*
