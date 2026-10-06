https://chat.deepseek.com/share/56odi3wvppfmi15bah

```txt

Hãy dạy tôi lại từ đầu (A->Z) đầy đủ 100% về, nhưng làm ơn hạn chế việc dùng tham số (trừ biến thời gian t), hãy biểu diễn mọi thứ theo hàm, chi tiết nhất có thể nhé, dùng ký hiệu của Leibniz, đừng viết tắt! Đảm bảo dạy tôi cực kỳ chi tiết để tôi từ 1 học sinh ngu giải tích (đúng hơn là chưa học, do tôi vượt cấp mà) lên được pro PTVP cho HSGQG Vật Lý nhé! : Phương trình vi phân rốt cuộc là gì? Định nghĩa của ptvp? 

Tách biến (D.2), Tuyến tính bậc 1 (D.3), Bernoulli (D.6), Tích phân trực tiếp (D.1); PTVP đẳng cấp (Homogeneous Equations); PTVP toàn phần (Exact Equations) & Thừa số tích phân;

Tuyến tính hệ số hằng - Thuần nhất (E.2), Tuyến tính hệ số hằng - Không thuần nhất (E.3), Phi tuyến - Vắng x (E.1.b / E.1.c);

Tiếp tục là, Hệ PTVP (Systems of ODEs) và Phương pháp khử, Ma Trận.

Điều kiện đầu và Điều kiện biên (Initial & Boundary Conditions): Một PTVP vô nghiệm hoặc vô số nghiệm nếu không có điều kiện. Trong Vật lý, điều kiện đầu (tại t = 0) và điều kiện biên (tại vị trí giới hạn) là bắt buộc để tìm hằng số tích phân.

Phân tích định tính (Qualitative Analysis): Kỹ thuật này liên quan đến việc xét giới hạn của tích phân hoặc dùng trường vectơ (vector field).

```

Nếu thấy cuộc sống như cuộc đời, thấy bản thân không còn muốn tồn tại nữa, hãy xem video này : https://youtu.be/p_di4Zn4wz4 ; https://www.youtube.com/watch?v=p_di4Zn4wz4&list=PLZHQObOWTQDNPOjrT6KVlfJuKtYTftqH6

Tại sao Vũ trụ lại chọn cách vận hành "cục bộ"? Bởi vì có một giới hạn tốc độ tuyệt đối trong vũ trụ này: Tốc độ ánh sáng (c). [1] Không có một thông tin hay lực nào có thể truyền đi nhanh hơn tốc độ ánh sáng. Vì vậy, một vật ở điểm A không thể nào biết được vật ở điểm B (cách đó 1 năm ánh sáng) đang làm gì để mà thay đổi theo. Cách duy nhất để điểm A bị ảnh hưởng là điểm B phải gửi một "tín hiệu" (như ánh sáng, sóng hấp dẫn) đi xuyên qua các điểm không gian trung gian để đến được chỗ A.

Và đó là lý do vì sao chúng ta cần Phương trình vi phân (PTVP), Bởi vì PTVP sinh ra là để viết lại các quy luật cục bộ này dưới dạng toán học.

Trong tự nhiên, vận tốc (hoặc tốc độ thay đổi) thường không phụ thuộc vào thời gian \(t\), mà nó phụ thuộc vào trạng thái hiện tại của vật thể. Vì thế nên ta không thể cứ đơn giản là tích phân bừa bãi được. Ví dụ: 

• Phương trình: Đạo hàm của vận tốc (gia tốc \(v^{\prime }\)) bằng:
\(v^{\prime }=g-k\cdot v\)


• Rắc rối xuất hiện: Để tìm được vận tốc \(v\), bạn nghĩ đến việc lấy tích phân hai vế: \(v = \int (g - k \cdot v) dt\). Nhưng bạn không thể tính được tích phân này, vì bên trong dấu tích phân có chứa chữ \(v\) — chính là thứ mà bạn chưa biết và đang đi tìm! Bạn không thể lấy tích phân của một hàm số theo biến \(t\) khi chính hàm số đó đang biến đổi.

@3blue1brown:

```txt

Some notes on the intended use of this series.  I was deliberate in using the phrase "tour of differential equations", as opposed to "introduction to" or "essence of".  I think of the relationship between watching this series and taking a course as being analogous to the relationship between touring a city vs. living in it.  You'll certainly see a lot less with the tour since you're spending less time overall, but the goal will be to walk around some of the most noteworthy monuments and town centers with helpful context given to you by a guide.  And just as someone who lives in a city may very well have never gone to visit some of the historical sites of their town, despite living there for years, many differential equations students may not always get the chance to zoom out and appreciate the central cornerstones of the subject amidst all the computations they are learning.


I hope you enjoy the tour, but at the same time know that it is, by design, very different from taking courses on the subject.

```

@Alexander_Sannikov:

```txt

I basically solve all kinds of differential equations for living: modelling soft body dynamics, rigid body dynamics, optics, whatever. I just wanted to give an advice to anyone aspiring to learn all this stuff. What they often teach you at school/uni is how to solve these equations analytically : sure, this is sometimes useful. However, in most real applications, it's more productive to be able to write a program to solve them rather than to do that "manually". Even the simplest explicit solver that's literally 2 lines of code, instantly covers 95% of all differential equations, even though its performance and accuracy are not the best. It's kind of a brute force solution.


One might even start thinking that "hey, if my computer can just solve all these equations, why even bother studying them?". And the reason is very simple: by applying knowledge of certain types of DE's and by using more advanced solvers, one can increase performance and accuracy of these solvers by orders of magnitude. Which might make a huge difference: physics simulation in your game becomes more stable, your rendering algorithm can run your effects 60fps instead of 5fps, you can render your image in higher resolution on the same hardware, etc. My idea is, don't think of your computer as a replacement for your knowledge. Think of it as of an incredibly powerful tool, that still fully depends on your skill.


```


# Phương trình vi phân (PTVP) bậc 1 và bậc 2: từ bản chất đến thuật toán

> **Dành cho:** học sinh đã có nền Toán (đạo hàm, tích phân, số phức cơ bản) và đang học Vật Lý ở mức HSGQG, VPHO, IPHO.
> **Mục tiêu:** (1) hiểu PTVP *là gì* và *vì sao Vật Lý chứa đầy nó*; (2) có một **quy trình nhận diện** để nhìn một PTVP là biết nó thuộc loại nào; (3) có **thuật toán giải** cho từng loại, kèm **điều kiện áp dụng** (Pre), **bất biến nhận diện** và **cách kiểm chứng**.
>
> **Lưu ý về độ tin cậy:** các ví dụ trong tài liệu đã được thế ngược để kiểm tra, nhưng đúng với tinh thần của bạn: *đừng tin, hãy tự thế lại.* Nếu thấy sai sót, hãy ghi lại và sửa.

---

## Mục lục

- **Phần A.** Hiểu PTVP (bản chất, thuật ngữ, hình học, tồn tại và duy nhất)
- **Phần B.** Từ bài Vật Lý sang PTVP (Vấn đề 2 của bạn)
- **Phần C.** Bản đồ nhận diện (cây quyết định)
- **Phần D.** PTVP bậc 1: từng thuật toán
- **Phần E.** PTVP bậc 2: từng thuật toán
- **Phần F.** "Bất biến" và đối xứng: vì sao các thuật toán trên hoạt động
- **Phần G.** Phân tích định tính và tuyến tính hóa (khi không giải được hoặc không cần giải)
- **Phần H.** Quy trình tổng hợp, kiểm chứng, các bẫy
- **Phần I.** Bài tập có hướng dẫn
- **Phần J.** Bảng tra nhanh, tài liệu

---

# PHẦN A. HIỂU PTVP

## A.1. PTVP là gì? (bằng ngôn ngữ Vật Lý)

Một phương trình đại số như $x^2 - 3x + 2 = 0$ có ẩn là một **con số**. Một PTVP có ẩn là một **hàm số** $y(x)$ (hoặc $x(t)$), và phương trình chứa **đạo hàm** của hàm đó.

Vật Lý hầu như luôn cho ta **quy luật cục bộ về sự biến thiên**, không cho trực tiếp hàm:

- "Tốc độ phân rã tỉ lệ với số hạt hiện có": $\dfrac{dN}{dt} = -\lambda N$.
- "Gia tốc bằng lực chia khối lượng": $m\ddot{x} = F(x, \dot{x}, t)$.
- "Điện tích tụ giảm theo dòng qua điện trở": $R\dfrac{dq}{dt} = -\dfrac{q}{C}$.

Ta biết **"từ trạng thái hiện tại, bước tiếp theo đi thế nào"**. PTVP là bài toán ngược: *biết luật đi từng bước nhỏ, tìm ra toàn bộ quỹ đạo.*

**Hình dung:** PTVP là *luật giao thông*, nghiệm là *một hành trình cụ thể*. Luật chỉ nói "ở vị trí này, lái theo hướng kia". Muốn biết hành trình, bạn phải biết **điểm xuất phát** (điều kiện đầu).

### Ví dụ mở đầu: vật rơi có lực cản tỉ lệ vận tốc

$$m\frac{dv}{dt} = mg - \gamma v.$$

Chưa cần giải, chỉ đọc ý nghĩa: khi $v$ nhỏ, $\dot v \approx g$ (rơi tự do). Khi $v$ tăng, lực cản tăng, gia tốc giảm. Khi $\dot v = 0$ thì $v = v_\infty = mg/\gamma$ (vận tốc giới hạn). **Ta đoán được hành vi của nghiệm trước khi giải**; đó là trực giác định tính (Phần G).

Nghiệm: $v(t) = \dfrac{mg}{\gamma}\left(1 - e^{-\gamma t/m}\right)$ với $v(0)=0$. Hằng số thời gian $\tau = m/\gamma$.

## A.2. Thuật ngữ bắt buộc phải nắm

| Khái niệm | Ý nghĩa | Ví dụ |
|---|---|---|
| **Bậc** | Cấp đạo hàm cao nhất xuất hiện | $y'' + y = 0$ là bậc 2 |
| **Nghiệm tổng quát** | Họ nghiệm chứa các hằng số tùy ý (số hằng = bậc) | $y = Ce^{-x}$ |
| **Nghiệm riêng** | Một nghiệm cụ thể (đã chọn hằng số) | $y = 3e^{-x}$ |
| **Nghiệm kỳ dị** | Nghiệm không nằm trong họ tổng quát | $y\equiv 0$ của $y'=\sqrt{|y|}$... (xem A.5) |
| **Bài toán Cauchy / điều kiện đầu** | PTVP + giá trị đầu, đủ để chọn đúng 1 nghiệm | $y(0)=1$ |
| **Tuyến tính** | $y, y', y'', \dots$ chỉ xuất hiện bậc 1 và không nhân với nhau | $y'' + p(x)y' + q(x)y = f(x)$ |
| **Thuần nhất (tuyến tính)** | Vế phải (số hạng không chứa $y$) bằng 0 | $y''+y=0$ |
| **Ô-tô-nôm (autonomous)** | Biến độc lập không xuất hiện tường minh | $y' = f(y)$, $\ddot x = F(x,\dot x)$ |
| **Hệ số hằng** | Các hệ số của $y, y', y''$ là hằng | $y''+3y'+2y=0$ |

> **Cảnh báo ngôn ngữ:** "thuần nhất" có **hai nghĩa khác nhau**:
> (a) *tuyến tính thuần nhất*: vế phải $=0$ (dùng cho PTVP tuyến tính);
> (b) *đẳng cấp (homogeneous of degree 0)*: $y' = F(y/x)$.
> Tài liệu này dùng **"thuần nhất"** cho (a) và **"đẳng cấp"** cho (b).

Một hệ phương trình vi phân cấp bất kỳ (hoặc một phương trình vi phân cấp cao) có biến độc lập là \(t\) và các hàm ẩn cần tìm là \(y_1(t), y_2(t), \dots, y_n(t)\) được gọi là tự trị (autonomous) nếu nó có thể biểu diễn dưới dạng:

\(F\big(y_{1},y_{2},\dots ,y_{n},\;y_{1}^{\prime },y_{2}^{\prime },\dots ,y_{n}^{\prime },\;\dots ,\;y_{1}^{(k)},y_{2}^{(k)},\dots ,y_{n}^{(k)}\big)=0\)

Hàm toán học \(F\) này nhận đầu vào là các hàm ẩn \(y_{i}\) và tất cả các cấp đạo hàm của chúng (\(y', y'', \dots, y^{(k)}\)). Trong danh sách các đối số đầu vào của hàm \(F\), tuyệt đối không có sự xuất hiện của biến độc lập \(t\) đứng một mình.


## A.3. Vì sao Cơ học luôn là bậc 2, và số hằng số = bậc

Định luật II Newton $m\ddot x = F$ chứa $\ddot x$, nên bậc 2. Để dự đoán chuyển động, bạn cần **hai** dữ kiện đầu: $x(0)$ và $\dot x(0)$. Đây không phải trùng hợp.

**Quy tắc:** PTVP bậc $n$ cần $n$ điều kiện đầu và nghiệm tổng quát có $n$ hằng số tùy ý.

Khi bài cho PTVP bậc 2 mà chỉ có **một** điều kiện, nghiệm sẽ còn một tham số tự do (hoặc đó là **bài toán biên**, xem A.5).

## A.4. Ý nghĩa hình học (bậc 1): trường hướng

Với $y' = f(x,y)$, tại mỗi điểm $(x,y)$ ta vẽ một đoạn nhỏ có hệ số góc $f(x,y)$. Tập mọi đoạn đó là **trường hướng**. Nghiệm là **đường cong luôn tiếp xúc** với các đoạn đó ("đi theo dòng chảy").

Tức hàm f(x,y) tại mỗi điểm (x,y), hàm sẽ trả về giá trị đạo hàm của hàm y tại điểm (x,y) tương ứng.

"Mỗi đường cong tích phân (integral curve) liên tục trên trường hướng (slope field) của phương trình vi phân y' = f(x,y) chính là đồ thị biểu diễn cho 1 nghiệm riêng y = g(x) của phương trình đó."

Hàm f(x,y) = y' mang thông tin về độ dốc f(x,y) hay y' và mang thông tin về tọa độ x,y;

Hệ quả quan trọng:
- Qua mỗi điểm (thông thường) có **đúng một** đường nghiệm → các đường nghiệm **không cắt nhau**.
- **Đường đẳng độ nghiêng** (isocline) $f(x,y)=k$ giúp phác thảo nghiệm không cần giải.
- Điểm có $f = 0$ trên cả đường $y = y^*$ cho **nghiệm hằng** (điểm cân bằng).

## A.5. Tồn tại và duy nhất: điều kiện Pre của *mọi* phương pháp

**Định lý (Picard–Lindelöf, phát biểu nhẹ).** Nếu $f(x,y)$ liên tục và $\partial f/\partial y$ liên tục (hoặc chỉ cần "Lipschitz theo $y$") quanh $(x_0,y_0)$, thì bài toán $y'=f(x,y),\ y(x_0)=y_0$ có **nghiệm duy nhất** trong một lân cận của $x_0$.

Hai phản ví dụ phải thuộc lòng:

1. **Mất duy nhất:** $y' = \sqrt{|y|},\ y(0)=0$. Cả $y\equiv 0$ lẫn $y = x|x|/4$ đều là nghiệm. (Vì $\partial f/\partial y$ không bị chặn tại $y=0$.)
2. **Nghiệm "nổ" hữu hạn:** $y' = y^2,\ y(0)=1 \Rightarrow y = \dfrac{1}{1-x}$, chỉ tồn tại với $x<1$. **Nghiệm không cần tồn tại trên toàn trục.**

**Với PTVP tuyến tính** $y'' + p y' + q y = f$ với $p,q,f$ liên tục trên khoảng $I$: nghiệm tồn tại, duy nhất và kéo dài trên **toàn bộ** $I$. Đây là lý do PTVP tuyến tính "ngoan".

**Bài toán biên** (ví dụ dây căng, sóng dừng): cho điều kiện tại hai điểm $y(0)=0,\ y(L)=0$. **Không đảm bảo** tồn tại duy nhất. Ví dụ $y''+k^2y=0,\ y(0)=y(L)=0$ chỉ có nghiệm không tầm thường khi $kL = n\pi$ → đây chính là gốc của **lượng tử hóa / tần số riêng**.

## A.6. Tinh thần giải PTVP: không có "công thức chung", chỉ có "kho công cụ + nhận diện"

Khác với phương trình bậc 2 đại số, **không có thuật toán vạn năng** giải mọi PTVP bằng biểu thức đóng. Điều ta có là:

1. Một **kho hữu hạn** các dạng giải được (tách biến, tuyến tính, Bernoulli, hệ số hằng…).
2. Một **quy trình nhận diện** (Phần C) cho biết đề bài rơi vào dạng nào, với **bất biến kiểm tra được** bằng tay.
3. Khi hết cách: phân tích định tính, tuyến tính hóa, xấp xỉ, số.

Theo ngôn ngữ của bạn: mỗi phương pháp $\ell$ có $\mathrm{Pre}(\ell)$ (điều kiện nhận diện), $\mathrm{Post}(\ell)$ (nghiệm). Tài liệu này là **thư viện precondition** cho PTVP bậc 1, 2.

## Bổ sung.

Tôi ghét các cách giáo dục ngày nay viết ký hiệu, thách thức và làm người mới hiểu sai, thậm chí lâu năm.

1. Việc viết y' rồi giải thích như kiểu cái đạo hàm y này chỉ phụ thuộc vào chính nó, hay y; Cực kỳ vô lý với cách giải thích này cho người mới, ai hiểu được? Bởi vì đạo hàm là phải "phụ thuộc" vào 2 thứ, làm gì có vụ dy/dy? Chỉ có dy/d?, kiểu như dy/dx; Phải đấy, lẽ ra nên ghi thẳng là dy/dx;

---

# PHẦN B. TỪ BÀI VẬT LÝ SANG PTVP (VẤN ĐỀ 2)

Đây thường là bước khó hơn việc giải. Quy trình **không cần trực giác đặc biệt**:

## B.1. Quy trình 7 bước

1. **Chọn ẩn và biến độc lập.** Hàm nào theo biến nào (thường $x(t)$, $q(t)$, $T(t)$, hoặc theo vị trí $y(x)$).
2. **Chọn quy ước dấu và gốc.** Chọn chiều dương một lần, ghi lên hình. Mọi lực, vận tốc, dòng điện được gán dấu theo quy ước đó.
3. **Vẽ "trạng thái tổng quát" tại thời điểm $t$ bất kỳ.** **Không vẽ trạng thái đặc biệt** (VTCB, điểm cao nhất…). Đây là bẫy lớn nhất: ở trạng thái đặc biệt, có hạng tử triệt tiêu và bạn sẽ mất nó.
4. **Chọn định luật gốc phù hợp** (first principles):
   - Chuyển động: $\sum\vec F = \dfrac{d\vec p}{dt}$ (chú ý: nếu khối lượng thay đổi thì **không** dùng $m\vec a$), hoặc mômen: $\dfrac{dL}{dt}=\tau$, hoặc Lagrange.
   - Năng lượng: $\dfrac{dE}{dt} = P_{\text{ngoài}} - P_{\text{tiêu tán}}$.
   - Cân bằng lượng (khối lượng, điện tích, nhiệt): **tốc độ biến thiên = vào − ra**.
   - Mạch điện: Kirchhoff tại thời điểm $t$ bất kỳ.
5. **Viết phương trình, khử về một ẩn.** Nếu có nhiều ẩn phụ, dùng ràng buộc hình học/đại số để loại.
6. **Ghi điều kiện đầu** (số điều kiện = bậc).
7. **Kiểm tra thứ nguyên** từng số hạng và kiểm tra giới hạn (ví dụ $\gamma\to0$, $t\to0$, $t\to\infty$).

## B.2. Bốn mẫu "cân bằng" cực phổ biến

**(i) Phân rã / tăng trưởng:** $\dot N = \pm kN$ → mũ.

**(ii) Bồn hòa tan (mixing tank):** thể tích $V$, lưu lượng vào = ra $=r$, nồng độ vào $c_{in}$:
$$V\frac{dc}{dt} = r\,(c_{in} - c) \Rightarrow c' + \frac{r}{V}c = \frac{r}{V}c_{in}.$$
Tuyến tính bậc 1. Nếu lưu lượng vào $\neq$ ra thì $V=V(t)$ → hệ số biến thiên, **viết lại $V(t)$ trước**.

**(iii) Làm nguội (Newton), mạch RC, RL:** cùng cấu trúc $\ \tau \dot u + u = u_{\infty}$.

**(iv) Dao động ($m\ddot x + \gamma \dot x + kx = F(t)$, $L\ddot q + R\dot q + q/C = \mathcal E(t)$):** cùng một PTVP bậc 2 tuyến tính hệ số hằng. **Tương tự cơ–điện** là công cụ cực mạnh: $m\leftrightarrow L,\ \gamma\leftrightarrow R,\ k\leftrightarrow 1/C,\ x\leftrightarrow q$.

## B.3. Ví dụ dựng PTVP

**Bài:** Vật khối lượng $m$ rơi, lực cản $kv^2$ ($k>0$). Chọn trục $y$ hướng xuống.

Trạng thái bất kỳ: lực xuống $mg$, lực cản ngược chiều chuyển động (lên) $kv^2$.
$$m\dot v = mg - kv^2 \quad\Longrightarrow\quad \dot v = g\Big(1-\frac{v^2}{v_t^2}\Big),\quad v_t = \sqrt{\frac{mg}{k}}.$$
**Dạng:** ô-tô-nôm → **tách biến** (D.2). Nghiệm với $v(0)=0$: $v = v_t\tanh(gt/v_t)$.

> **Cảnh báo dấu:** nếu vật *ném lên*, lực cản hướng xuống và đổi dấu theo chiều chuyển động; phải viết $-k v|v|$, không phải $-kv^2$ cả hai giai đoạn. Chia bài thành hai giai đoạn.

---

# PHẦN C. BẢN ĐỒ NHẬN DIỆN (CÂY QUYẾT ĐỊNH)

> Dùng khi nhìn một PTVP mà chưa biết làm gì. Mỗi nút kiểm tra một **bất biến** có thể tính bằng tay.

## C.1. Bước 0: Phân loại thô (luôn làm trước)

Hỏi lần lượt:
1. **Bậc** là mấy?
2. **Tuyến tính** theo $y$ và các đạo hàm không? (Có tích như $yy'$, hàm phi tuyến như $\sin y$, $y^2$, $\sqrt{y'}$ không?)
3. **Hệ số** là hằng hay phụ thuộc $x$?
4. **Ô-tô-nôm** không (vắng $x$ tường minh)? Có vắng $y$ không?
5. Có **đối xứng/bảo toàn** nào không (Phần F)?

## C.2. Cây quyết định cho bậc 1: $y' = f(x,y)$ hoặc $M\,dx + N\,dy = 0$

```
Bậc 1
│
├─ Vế phải chỉ chứa x:        y' = f(x)               → D.1  Tích phân trực tiếp
├─ Tách được f(x)·g(y):       y' = f(x)g(y)            → D.2  Tách biến (gồm cả y' = f(y))
├─ Tuyến tính:  y' + p(x)y = q(x)                      → D.3  Thừa số tích phân
├─ Đẳng cấp:   y' = F(y/x)  (M,N cùng bậc đồng nhất)   → D.4  Thế u = y/x
├─ y' = F(ax+by+c)                                     → D.5  Thế u = ax+by+c
├─ y' = F( (a₁x+b₁y+c₁)/(a₂x+b₂y+c₂) )                → D.5  Tịnh tiến về đẳng cấp
├─ Bernoulli: y' + p y = q yⁿ                          → D.6  Thế z = y^(1-n)
├─ Toàn phần: ∂M/∂y = ∂N/∂x                            → D.7  Tìm hàm thế F
├─ Gần toàn phần: (M_y − N_x)/N chỉ phụ thuộc x, ...   → D.7  Thừa số tích phân μ
├─ Riccati: y' = q₀ + q₁y + q₂y²  (biết 1 nghiệm riêng)→ D.8  Thế y = y₁ + 1/v
├─ Clairaut: y = xy' + f(y')                           → D.9
└─ Không dạng nào:                                     → G (định tính), xấp xỉ, số
```

**Thứ tự thử khuyến nghị** (từ rẻ đến đắt): trực tiếp → tách biến → tuyến tính → đẳng cấp → Bernoulli → toàn phần → thừa số tích phân → thế khác. Nhiều PTVP **thuộc nhiều dạng** cùng lúc (ví dụ $y'=y(1-y)$ vừa tách biến vừa Bernoulli); chọn dạng dễ tính nhất.

Theo tôi, HSGQG Lý nên chủ yếu mấy thứ này: Tách biến (D.2), Tuyến tính bậc 1 (D.3), Bernoulli (D.6), Tích phân trực tiếp (D.1); PTVP đẳng cấp (Homogeneous Equations); PTVP toàn phần (Exact Equations) & Thừa số tích phân;



## C.3. Cây quyết định cho bậc 2: $F(x,y,y',y'')=0$

```
Bậc 2
│
├─ Tuyến tính?
│   ├─ Hệ số hằng:  a y'' + b y' + c y = f(x)
│   │     ├─ Thuần nhất (f=0)           → E.2  Phương trình đặc trưng (Δ = b²−4ac)
│   │     └─ Không thuần nhất           → E.3  Hệ số bất định (f dạng đẹp)  hoặc  E.4 Biến thiên hằng số
│   ├─ Euler–Cauchy: x²y'' + a x y' + b y = f   → E.5  Thế y = x^r  (hoặc t = ln x)
│   └─ Hệ số biến thiên khác                     → E.6  Biết 1 nghiệm → hạ bậc;  chuỗi lũy thừa;  nhận diện Bessel/Legendre
│
└─ Phi tuyến
    ├─ Vắng y:       F(x, y', y'') = 0           → E.1.a  p = y'  (hạ về bậc 1)
    ├─ Vắng x:       F(y, y', y'') = 0           → E.1.b  p = y', y'' = p dp/dy
    ├─ y'' = f(y)    (trường hợp riêng của vắng x) → E.1.c  Tích phân năng lượng
    ├─ Thuần nhất theo (y,y',y''):                → E.1.d  z = y'/y
    ├─ Vế trái là đạo hàm đúng d/dx[Φ(x,y,y')]    → E.1.e  Tích phân một lần
    └─ Còn lại:                                    → G (mặt phẳng pha, tuyến tính hóa, số)
```

Theo tôi, HSGQG Lý nên chủ yếu mấy thứ này: Tuyến tính hệ số hằng - Thuần nhất (E.2), Tuyến tính hệ số hằng - Không thuần nhất (E.3), Phi tuyến - Vắng x (E.1.b / E.1.c)

Tiếp tục là, Hệ PTVP (Systems of ODEs) và Phương pháp khử, Ma Trận.

Bổ sung, Perturbation & Series: Khi PTVP không thể giải chính xác, HSGQG thường yêu cầu giải gần đúng. Bạn cần biết khai triển Taylor, chuỗi Fourier, hoặc phương pháp nhiễu (perturbation).


Điều kiện đầu và Điều kiện biên (Initial & Boundary Conditions): Một PTVP vô nghiệm hoặc vô số nghiệm nếu không có điều kiện. Trong Vật lý, điều kiện đầu (tại t = 0) và điều kiện biên (tại vị trí giới hạn) là bắt buộc để tìm hằng số tích phân.

Phân tích định tính (Qualitative Analysis): Kỹ thuật này liên quan đến việc xét giới hạn của tích phân hoặc dùng trường vectơ (vector field).



---

# PHẦN D. PTVP BẬC 1: TỪNG THUẬT TOÁN

> Cấu trúc mỗi mục: **Nhận diện (bất biến)** → **Thuật toán** → **Điều kiện/bẫy** → **Ví dụ** → **Kiểm chứng**.

---

## D.1. Tích phân trực tiếp

**Nhận diện:** $y' = f(x)$.
**Thuật toán:** $y = \int f(x)\,dx + C$. Với điều kiện đầu: $y(x) = y_0 + \int_{x_0}^x f(s)\,ds$.
**Bẫy:** nếu $\int f$ không có dạng đóng, cứ để ở **dạng tích phân xác định**; vẫn là nghiệm hợp lệ.

---

## D.2. Tách biến (separable)

**Nhận diện (bất biến):** vế phải **phân tích thành tích** $f(x)\cdot g(y)$. Tương đương: $\dfrac{\partial^2 \ln|y'|}{\partial x\,\partial y}=0$ (bạn thường chỉ cần *nhìn*).
Trường hợp riêng quan trọng: **ô-tô-nôm** $y' = g(y)$ (vắng $x$).

**Thuật toán:**
1. **Tìm nghiệm hằng trước:** giải $g(y^*) = 0$ → các nghiệm $y\equiv y^*$. (Bước chia cho $g(y)$ sẽ **làm mất** chúng.)
2. Với $g(y)\neq 0$: viết $\dfrac{dy}{g(y)} = f(x)\,dx$.
3. Tích phân hai vế: $\displaystyle\int \frac{dy}{g(y)} = \int f(x)\,dx + C$.
4. Giải ngược $y(x)$ nếu được (nghiệm ẩn vẫn chấp nhận).
5. Kết hợp điều kiện đầu **và** xét xem nghiệm hằng có thỏa điều kiện đầu không.

**Bẫy:**
- Quên nghiệm hằng.
- Tích phân $\int dy/y = \ln|y|$ (có **giá trị tuyệt đối**), rồi hấp thụ $\pm$ vào hằng số.
- Nghiệm chỉ hợp lệ trên khoảng không chứa điểm $g=0$.

**Ví dụ vật lý (lực cản bậc hai):** $\dot v = g(1 - v^2/v_t^2)$.
- Nghiệm hằng: $v=\pm v_t$.
- Tách: $\dfrac{dv}{1 - v^2/v_t^2} = g\,dt \Rightarrow v_t\,\mathrm{artanh}(v/v_t) = gt + C$.
- Với $v(0)=0$: $C=0$ → $v = v_t\tanh\!\big(gt/v_t\big)$.

**Kiểm chứng:** $v' = (g/\cosh^2)=g(1-\tanh^2) = g(1 - v^2/v_t^2)$ ✓; $t\to\infty$: $v\to v_t$ ✓ (khớp nghiệm hằng); $t\to0$: $v\approx gt$ ✓ (rơi tự do).

---

## D.3. Tuyến tính bậc 1 (thừa số tích phân)

**Nhận diện (bất biến):** có thể đưa về $y' + p(x)\,y = q(x)$ — tức $y$ và $y'$ xuất hiện **bậc 1, không nhân nhau**.

**Thuật toán:**
1. Chia để hệ số của $y'$ bằng 1. Đọc $p(x)$, $q(x)$.
2. Tính $P(x) = \int p(x)\,dx$ (không cần hằng), đặt $\mu = e^{P(x)}$.
3. Nhân hai vế với $\mu$: vế trái trở thành $(\mu y)'$ (vì $\mu' = p\mu$).
4. $\mu y = \int \mu q\,dx + C \Rightarrow$
$$\boxed{\,y = e^{-P(x)}\left[\int q(x)e^{P(x)}\,dx + C\right]\,}$$

**Cấu trúc nghiệm (rất quan trọng):** $y = \underbrace{Ce^{-P}}_{\text{nghiệm thuần nhất (dập tắt)}} + \underbrace{y_p}_{\text{nghiệm riêng (đáp ứng ép buộc)}}$.

**Ý nghĩa vật lý:** phần $Ce^{-P}$ là **quá độ**, tắt dần theo $\tau$. Phần $y_p$ là **xác lập**. Đây là bộ khung của mọi mạch RC, RL, bài làm nguội, bồn hòa tan.

**Ví dụ (mạch RC nạp, $E$ không đổi):** $R\dot q + q/C = E \Rightarrow \dot q + \dfrac{q}{RC} = \dfrac{E}{R}$.
$\mu = e^{t/RC}$, $\ (q e^{t/RC})' = \dfrac{E}{R}e^{t/RC} \Rightarrow q = EC + Ae^{-t/RC}$. Với $q(0)=0$: $q = EC(1 - e^{-t/RC})$.

**Ví dụ (hệ số biến thiên):** $y' - \dfrac{y}{x} = x$ → $p = -1/x$, $\mu = 1/x$, $(y/x)' = 1$, $y = x^2 + Cx$.

**Bẫy:** quên chia hệ số của $y'$; sai dấu của $p$ ($e^{-P}$ ở ngoài, $e^{+P}$ trong tích phân).

---

## D.4. Đẳng cấp (homogeneous of degree 0)

**Nhận diện (bất biến):** $y' = F(y/x)$, hay $M(x,y)dx + N(x,y)dy = 0$ với $M, N$ **cùng bậc đồng nhất** $n$:
$M(tx,ty) = t^n M(x,y)$, $N(tx,ty) = t^nN(x,y)$.
Nói theo đối xứng (Phần F): PTVP bất biến dưới phép **co giãn** $(x,y)\to(\lambda x,\lambda y)$.

**Thuật toán:**
1. Thế $y = ux$ ($u=u(x)$), $y' = u + xu'$.
2. Phương trình thành $x u' = F(u) - u$: **tách biến** được: $\dfrac{du}{F(u)-u} = \dfrac{dx}{x}$.
3. Tích phân, quay lại $u = y/x$.
4. Xét nghiệm hằng $u^*$ (tức $F(u^*)=u^*$) ↔ đường thẳng $y = u^*x$.

**Ví dụ:** $(x^2+y^2)dx - 2xy\,dy=0$ (bậc 2 cả hai). Thế $y = ux$:
$(1-u^2)\,dx = 2ux\,du \Rightarrow \dfrac{dx}{x} = \dfrac{2u\,du}{1-u^2} \Rightarrow x(1-u^2) = C \Rightarrow x^2 - y^2 = Cx.$

---

## D.5. Các dạng đưa về đã học bằng phép thế tuyến tính

**(a)** $y' = F(ax + by + c)$ — **nhận diện:** biến chỉ xuất hiện qua một tổ hợp tuyến tính.
Thế $u = ax+by+c$: $u' = a + bF(u)$ → **tách biến**.

**(b)** $y' = F\!\left(\dfrac{a_1x+b_1y+c_1}{a_2x+b_2y+c_2}\right)$:
- Nếu $\Delta = a_1b_2 - a_2b_1 \neq 0$: giải $a_1h+b_1k+c_1=0,\ a_2h+b_2k+c_2=0$ để tìm giao điểm $(h,k)$; thế $X = x-h,\ Y = y-k$ → **đẳng cấp** (D.4).
- Nếu $\Delta = 0$: hai đường song song → thế $u = a_1x + b_1y$ → **tách biến**.

**Nguyên tắc chung:** *tịnh tiến đưa gốc về điểm đặc biệt (đối xứng)* — chính là việc "thêm/bớt yếu tố để đạt đối xứng" trong tài liệu của bạn.

---

## D.6. Bernoulli

**Nhận diện (bất biến):** $y' + p(x)\,y = q(x)\,y^n,\ n\neq 0,1$. (Tuyến tính "bị nhiễu" bởi một lũy thừa của $y$.)

**Thuật toán:**
1. Chia hai vế cho $y^n$: $y^{-n}y' + p\,y^{1-n} = q$.
2. Đặt $z = y^{1-n}$, $z' = (1-n)y^{-n}y'$.
3. Được **tuyến tính**: $z' + (1-n)p\,z = (1-n)q$ → dùng D.3.
4. Quay lại $y = z^{1/(1-n)}$. Kiểm tra nghiệm $y\equiv0$ (với $n>0$).

**Ví dụ:** $y' + \dfrac{y}{x} = y^2$ ($n=2$). $z = 1/y$: $z' - \dfrac{z}{x} = -1 \Rightarrow (z/x)' = -1/x \Rightarrow z = x(C - \ln x)$. Vậy $y = \dfrac{1}{x(C - \ln x)}$ và $y\equiv0$.

**Ví dụ vật lý – logistic:** $\dot N = rN(1 - N/K)$ → $N(t)=\dfrac{K}{1 + \left(\frac{K}{N_0}-1\right)e^{-rt}}$.

---

## D.7. Vi phân toàn phần và thừa số tích phân

**Nhận diện (bất biến):** viết $M(x,y)\,dx + N(x,y)\,dy = 0$.
- **Toàn phần** (exact) nếu $\dfrac{\partial M}{\partial y} = \dfrac{\partial N}{\partial x}$ (trên miền đơn liên).

**Thuật toán (toàn phần):**
1. Kiểm $M_y = N_x$.
2. Tìm $F$ với $F_x = M$: $F = \int M\,dx + g(y)$.
3. Dùng $F_y = N$: $g'(y) = N - \dfrac{\partial}{\partial y}\int M\,dx$ (vế phải **phải** không chứa $x$ — đây cũng là phép tự kiểm).
4. Nghiệm ẩn: $F(x,y) = C$.

**Nếu không toàn phần**, thử tìm $\mu$ để $\mu M\,dx + \mu N\,dy$ toàn phần:

| Bất biến kiểm tra | Thừa số tích phân |
|---|---|
| $\dfrac{M_y - N_x}{N} = h(x)$ chỉ phụ thuộc $x$ | $\mu(x) = \exp\!\Big(\int h(x)\,dx\Big)$ |
| $\dfrac{N_x - M_y}{M} = k(y)$ chỉ phụ thuộc $y$ | $\mu(y) = \exp\!\Big(\int k(y)\,dy\Big)$ |

(Suy ra từ $(\mu M)_y = (\mu N)_x$.)

**Ví dụ 1 (toàn phần):** $(2xy+3)dx + (x^2-1)dy=0$; $M_y = 2x = N_x$. $F = x^2y + 3x - y = C$.

**Ví dụ 2 (cần $\mu$):** $(x+y^2)dx - 2xy\,dy = 0$. $M_y=2y$, $N_x=-2y$, $\dfrac{M_y-N_x}{N} = \dfrac{4y}{-2xy} = -\dfrac2x \Rightarrow \mu = x^{-2}$. Nhân vào: $F = \ln|x| - \dfrac{y^2}{x} = C$.

**Ý nghĩa vật lý:** $F$ là **đại lượng bảo toàn** dọc nghiệm (giống thế năng/năng lượng). Toàn phần ↔ trường "bảo toàn" ($\vec\nabla\times$ = 0). Đây là cầu nối sang Phần F.

---

## D.8. Riccati

**Nhận diện:** $y' = q_0(x) + q_1(x)y + q_2(x)y^2$.
**Điều kiện Pre:** phải **biết một nghiệm riêng** $y_1$ (thường đoán: hằng, $x^k$, $e^{kx}$).
**Thuật toán:** thế $y = y_1 + \dfrac1v$ ⇒ $v' = -(q_1 + 2q_2y_1)\,v - q_2$ — **tuyến tính** (D.3).
**Ghi chú:** Riccati liên hệ trực tiếp với PTVP bậc 2 tuyến tính qua $y = -\dfrac{u'}{q_2u}$ (khi $q_2$ hằng/đơn giản). Nhiều bài bậc 2 "khó" thực ra là Riccati.

---

## D.9. Clairaut (hiếm, biết để nhận diện)

**Nhận diện:** $y = xy' + f(y')$.
**Nghiệm:** (i) **họ đường thẳng** $y = Cx + f(C)$; (ii) **nghiệm kỳ dị** là **đường bao** của họ đó: $x = -f'(p),\ y = xp + f(p)$.
Đây là ví dụ kinh điển của **nghiệm kỳ dị** (không nằm trong họ tổng quát).

---

## D.10. Khi cả D.1–D.9 đều không khớp

- **Thế** để đưa về dạng đã biết (ưu tiên: đổi biến độc lập/phụ thuộc, $u = y/x$, $u = xy$, $u = y^k$).
- Xem **đối xứng** của phương trình (Phần F): có co giãn? tịnh tiến?
- Làm **định tính** (Phần G) hoặc **số** (Euler, Runge–Kutta) nếu đề chỉ yêu cầu hành vi.

---

# PHẦN E. PTVP BẬC 2: TỪNG THUẬT TOÁN

## E.1. Hạ bậc cho PTVP bậc 2 phi tuyến (và tuyến tính đặc biệt)

> Ý chung: tìm một cách **biến bậc 2 thành bậc 1** (rồi dùng Phần D).

### E.1.a. Vắng $y$: $F(x, y', y'')=0$
**Bất biến:** $y$ không xuất hiện (chỉ $y', y''$). Phương trình bất biến dưới **tịnh tiến** $y\to y+c$.
**Thuật toán:** $p = y'$, $p' = y''$ → được PTVP bậc 1 theo $p(x)$; giải xong, $y=\int p\,dx$.
**Ví dụ:** $y'' + (y')^2 = 0$ → $p' = -p^2 \Rightarrow p = \dfrac{1}{x+C_1} \Rightarrow y = \ln|x+C_1| + C_2$ (và $p\equiv 0$: $y=C_2$).

### E.1.b. Vắng $x$ (ô-tô-nôm): $F(y, y', y'')=0$
**Bất biến:** $x$ (thời gian) không xuất hiện tường minh. Phương trình bất biến dưới **tịnh tiến thời gian**.
**Thuật toán:**
1. Coi $p$ là hàm của $y$: $p(y) = y'$. Khi đó $y'' = \dfrac{dp}{dx} = \dfrac{dp}{dy}\dfrac{dy}{dx} = p\dfrac{dp}{dy}$.
2. Được PTVP **bậc 1** cho $p(y)$.
3. Giải $p(y)$, rồi $\displaystyle\int\frac{dy}{p(y)} = x + C$.

**Vật lý:** đây là "vẽ quỹ đạo trên mặt phẳng pha $(y,\dot y)$" trước khi biết thời gian.

### E.1.c. Trường hợp riêng quan trọng nhất: $y'' = f(y)$ (cơ học một chiều với lực chỉ phụ thuộc vị trí)

**Tích phân năng lượng:** nhân hai vế với $y'$: $y'y'' = f(y)y'$ ⇒ $\dfrac{d}{dx}\!\left(\tfrac12 y'^2\right) = \dfrac{d}{dx}\!\int f(y)\,dy$:
$$\tfrac12 y'^2 - \int f(y)\,dy = E \quad (\text{hằng}).$$
Với cơ học: $m\ddot x = -V'(x) \Rightarrow \tfrac12m\dot x^2 + V(x) = E$.
Rồi $\displaystyle t = \pm\int\frac{dx}{\sqrt{\tfrac{2}{m}(E - V(x))}} + t_0$ — chu kỳ dao động, thời gian rơi… đều là tích phân này.

**Ví dụ (con lắc đơn):** $\ddot\theta = -\omega_0^2\sin\theta$ → $\tfrac12\dot\theta^2 - \omega_0^2\cos\theta = E$ → $T = \dfrac{4}{\omega_0}K\!\big(\sin\tfrac{\theta_0}{2}\big)\approx T_0\Big(1 + \dfrac{\theta_0^2}{16}\Big)$ ($K$ là tích phân elliptic đầy đủ loại 1).

### E.1.d. Thuần nhất theo $(y, y', y'')$ (bất biến dưới $y\to\lambda y$)
**Nhận diện:** thay $y\to\lambda y$ phương trình không đổi (các số hạng cùng bậc theo $y$).
**Thuật toán:** $z = y'/y$, $y' = zy$, $y'' = (z' + z^2)y$ → $y$ **triệt tiêu**, còn PTVP bậc 1 cho $z(x)$.
Sau đó $y = C\exp\!\int z\,dx$.

### E.1.e. Vế trái là đạo hàm đúng
**Nhận diện:** thử xem $F(x,y,y',y'')=\dfrac{d}{dx}\Phi(x,y,y')$. Ví dụ $yy''+y'^2 = (yy')'$.
**Thuật toán:** $\Phi = C_1$ (tích phân đầu một lần, hạ về bậc 1).

---

## E.2. Tuyến tính hệ số hằng, thuần nhất

$$a\,y'' + b\,y' + c\,y = 0,\quad a\neq0.$$

**Nhận diện (bất biến):** hệ số hằng, vế phải $0$. Đối xứng: tịnh tiến $x$ và co giãn $y$ (nhân $y$ bởi hằng số vẫn là nghiệm).

**Thuật toán:**
1. Thử $y = e^{\lambda x}$ → **phương trình đặc trưng** $a\lambda^2 + b\lambda + c = 0$, $\Delta = b^2 - 4ac$.
2. Xét 3 trường hợp:

| $\Delta$ | Nghiệm đặc trưng | Nghiệm tổng quát |
|---|---|---|
| $>0$ | $\lambda_1\neq\lambda_2$ thực | $y = C_1e^{\lambda_1x} + C_2e^{\lambda_2x}$ |
| $=0$ | $\lambda_1=\lambda_2=\lambda$ | $y = (C_1 + C_2x)e^{\lambda x}$ |
| $<0$ | $\lambda = \alpha\pm i\beta$ | $y = e^{\alpha x}\big(C_1\cos\beta x + C_2\sin\beta x\big)$ |

3. Dùng 2 điều kiện đầu giải $C_1, C_2$.

**Vì sao $(C_1+C_2x)e^{\lambda x}$?** Khi hai nghiệm đặc trưng trùng nhau, $e^{\lambda x}$ chỉ cho **một** nghiệm độc lập; nghiệm thứ hai $xe^{\lambda x}$ sinh ra từ đạo hàm theo $\lambda$ của họ nghiệm (hoặc từ hạ bậc E.4).

**Dạng biên độ–pha ($\Delta<0$):** $y = Ae^{\alpha x}\cos(\beta x - \varphi)$, với $A = \sqrt{C_1^2 + C_2^2}$.

### Ứng dụng: dao động tắt dần

$m\ddot x + \gamma\dot x + kx = 0$. Đặt $\omega_0 = \sqrt{k/m}$, $\delta = \gamma/2m$ (hệ số tắt dần), $\zeta = \dfrac{\gamma}{2\sqrt{mk}} = \dfrac{\delta}{\omega_0}$.

$$\lambda = -\delta \pm \sqrt{\delta^2 - \omega_0^2}.$$

| Chế độ | Điều kiện | Hành vi |
|---|---|---|
| **Tắt dần yếu** (underdamped) | $\delta<\omega_0$ ($\zeta<1$) | $x = Ae^{-\delta t}\cos(\omega_dt-\varphi)$, $\ \omega_d = \sqrt{\omega_0^2-\delta^2}$ |
| **Tới hạn** (critical) | $\delta=\omega_0$ ($\zeta=1$) | $x = (C_1 + C_2t)e^{-\delta t}$, về 0 nhanh nhất không dao động |
| **Tắt dần mạnh** (overdamped) | $\delta>\omega_0$ ($\zeta>1$) | hai hàm mũ giảm, không dao động |

**Chống nhầm:** "không dao động" không có nghĩa là không vượt qua VTCB 1 lần (tùy điều kiện đầu).

---

## E.3. Tuyến tính hệ số hằng, không thuần nhất: **hệ số bất định**

$$a\,y'' + b\,y' + c\,y = f(x).$$

**Cấu trúc nghiệm (định lý nền tảng):**
$$\boxed{\,y = y_h + y_p\,}$$
$y_h$ = nghiệm tổng quát của phương trình thuần nhất (E.2, chứa $C_1,C_2$); $y_p$ = **một** nghiệm riêng bất kỳ.
**Nguyên lý chồng chất:** nếu $f = f_1 + f_2$ thì $y_p = y_{p1} + y_{p2}$.

**Nhận diện (Pre của phương pháp):** $f(x)$ thuộc lớp "đóng kín dưới đạo hàm": đa thức, $e^{rx}$, $\cos\beta x$, $\sin\beta x$ và **tích** của chúng.

**Thuật toán:**
1. Giải $y_h$ trước (cần biết các nghiệm đặc trưng $\lambda_{1,2}$).
2. Phân $f$ thành các số hạng. Với mỗi số hạng, đoán $y_p$ theo bảng, nhân thêm $x^s$:

| $f(x)$ | Dạng thử $y_p$ (trước khi nhân $x^s$) |
|---|---|
| $P_m(x)$ (đa thức bậc $m$) | $Q_m(x)$ (đa thức đủ bậc $m$, **mọi hệ số**) |
| $P_m(x)e^{rx}$ | $Q_m(x)e^{rx}$ |
| $e^{\alpha x}[P(x)\cos\beta x + R(x)\sin\beta x]$ | $e^{\alpha x}[Q_1(x)\cos\beta x + Q_2(x)\sin\beta x]$, bậc $=\max(\deg P,\deg R)$ |

   **Quy tắc cộng hưởng:** $s$ là **bội** của số $r$ (hoặc $\alpha+i\beta$) như nghiệm của phương trình đặc trưng ($s=0$ nếu không phải nghiệm; $s=1$ nghiệm đơn; $s=2$ nghiệm kép).
3. Thế $y_p$ vào phương trình, **đồng nhất hệ số** → giải ra hệ số.
4. $y = y_h + y_p$; dùng điều kiện đầu **sau cùng** (lên $y$ tổng, không lên $y_h$ riêng).

**Ví dụ:** $y'' - 3y' + 2y = e^x$. $\lambda = 1, 2$; $r=1$ **trùng** nghiệm đơn → $s=1$. $y_p = Axe^x$: $A[(2+x) - 3(1+x) + 2x]e^x = -Ae^x = e^x \Rightarrow A=-1$.
$y = C_1e^x + C_2e^{2x} - xe^x$.

### Mẹo mạnh: **phương pháp phức hóa**
Với $f = F_0\cos\omega x$: giải với $f = F_0e^{i\omega x}$, được $y_c$, rồi $y_p = \mathrm{Re}\,y_c$. Với $y_p = Ye^{i\omega x}$, đạo hàm biến thành nhân $i\omega$:
$$(-a\omega^2 + ib\omega + c)\,Y = F_0 \Rightarrow Y = \frac{F_0}{c - a\omega^2 + ib\omega}.$$

### Ứng dụng: dao động cưỡng bức và cộng hưởng

$m\ddot x + \gamma\dot x + kx = F_0\cos\omega t$, hay $\ddot x + 2\delta\dot x + \omega_0^2x = \dfrac{F_0}{m}\cos\omega t$.

- **Xác lập:** $x_p = A(\omega)\cos(\omega t - \varphi)$,
$$A(\omega) = \frac{F_0/m}{\sqrt{(\omega_0^2-\omega^2)^2 + 4\delta^2\omega^2}},\qquad \tan\varphi = \frac{2\delta\omega}{\omega_0^2-\omega^2}\ (\varphi\in(0,\pi)).$$
- **Quá độ** $x_h\propto e^{-\delta t}$ tắt dần; sau $\gg1/\delta$ chỉ còn $x_p$.
- **Cộng hưởng biên độ:** cực đại tại $\omega_r = \sqrt{\omega_0^2-2\delta^2}$ (nếu $\delta^2<\omega_0^2/2$); khi $\delta\ll\omega_0$: $\omega_r\approx\omega_0$, $A_{\max}\approx\dfrac{F_0}{2m\delta\omega_0}$, phẩm chất $Q\approx\dfrac{\omega_0}{2\delta}$.
- **Không ma sát, $\omega=\omega_0$ (cộng hưởng thuần túy):** $r = i\omega_0$ trùng nghiệm đặc trưng nên $s=1$: $x_p = \dfrac{F_0}{2m\omega_0}\,t\sin\omega_0t$ — biên độ **tăng tuyến tính** theo $t$.
- **Phách ($\omega\approx\omega_0$, không ma sát):** tổng hai dao động gần tần số → đường bao $\propto\sin\!\big(\tfrac{\omega-\omega_0}{2}t\big)$.

---

## E.4. **Biến thiên hằng số** (khi $f$ bất kỳ hoặc hệ số biến thiên)

**Pre:** biết **hai nghiệm độc lập** $y_1,y_2$ của phương trình thuần nhất $y'' + p(x)y' + q(x)y = 0$, và phương trình đã chuẩn hóa (hệ số của $y''$ bằng 1): $y'' + p\,y' + q\,y = f(x)$.

**Thuật toán:**
1. Tính **Wronskian** $W = y_1y_2' - y_1'y_2$. (Phải $\neq0$ — đó là điều kiện độc lập tuyến tính.)
2. $$y_p = -y_1\int\frac{y_2f}{W}\,dx + y_2\int\frac{y_1f}{W}\,dx.$$
3. $y = C_1y_1 + C_2y_2 + y_p$.

**Ví dụ:** $y''+y=\tan x$: $y_1=\cos x,\ y_2=\sin x,\ W=1$.
$y_p = -\cos x\int\frac{\sin^2x}{\cos x}dx + \sin x\int\sin x\,dx = -\cos x\,\ln|\sec x+\tan x|$.

**Nguồn gốc:** tìm $y_p = u_1y_1 + u_2y_2$ với ràng buộc $u_1'y_1 + u_2'y_2 = 0$ để chỉ còn một PTVP bậc 1 cho mỗi $u_i'$.

**Bẫy:** nếu **chưa chuẩn hóa** (hệ số của $y''$ khác 1), $f$ phải chia cho hệ số đó.

---

## E.5. Wronskian, Abel, hạ bậc khi biết một nghiệm

**Wronskian** $W(y_1,y_2) = \begin{vmatrix}y_1&y_2\\y_1'&y_2'\end{vmatrix}$.
- Với hai nghiệm của PTVP tuyến tính thuần nhất bậc 2: $W\equiv0$ trên khoảng **hoặc** $W\neq0$ mọi nơi (không có "đôi khi bằng 0").
- **Công thức Abel:** $W(x) = W(x_0)\exp\!\Big(-\!\int_{x_0}^{x}p(s)\,ds\Big)$. *Hệ quả:* nếu $p=0$ (không có số hạng $y'$) thì $W$ **hằng**.
- $W\neq0 \Leftrightarrow$ hai nghiệm độc lập tuyến tính ⇒ $y_h = C_1y_1+C_2y_2$ là nghiệm tổng quát.

**Hạ bậc (reduction of order):** biết một nghiệm $y_1\neq0$ của $y''+py'+qy=0$. Thế $y = y_1v$ ⇒ $v''y_1 + v'(2y_1' + py_1)=0$ → là PTVP bậc 1 cho $v'$. Kết quả:
$$y_2 = y_1\int\frac{e^{-\int p\,dx}}{y_1^2}\,dx.$$
**Dùng khi:** đoán được một nghiệm (hằng, $x^k$, $e^{kx}$). Nhớ: **kiểm tra "tổng hệ số" hoặc thử $y=x^k$** trước.

---

## E.6. Euler–Cauchy (tuyến tính, hệ số "co giãn")

**Nhận diện (bất biến):** $x^2y'' + a\,x\,y' + b\,y = f(x)$ — mỗi số hạng có dạng $x^k\,y^{(k)}$ (bất biến dưới co giãn $x\to\lambda x$).

**Thuật toán thuần nhất:**
1. Thế $y = x^r$ ($x>0$) → $r(r-1) + a\,r + b = 0$.
2. Ba trường hợp tương ứng E.2:
   - $r_1\neq r_2$ thực: $y = C_1x^{r_1} + C_2x^{r_2}$.
   - $r_1=r_2=r$: $y = (C_1 + C_2\ln x)\,x^r$.
   - $r=\alpha\pm i\beta$: $y = x^\alpha\big[C_1\cos(\beta\ln x) + C_2\sin(\beta\ln x)\big]$.

**Thuật toán thay thế (và cho vế phải $f\neq0$):** thế $t=\ln x$ → phương trình **hệ số hằng** theo $t$ (đưa về E.2/E.3).

**Ví dụ:** $x^2y'' - xy' - 3y=0$ → $r^2-2r-3 = 0 \Rightarrow r=3,-1 \Rightarrow y = C_1x^3 + C_2x^{-1}$.

**Gặp ở Vật Lý:** phương trình Laplace trong tọa độ cực/cầu (phần bán kính), các bài có tính tự đồng dạng.

---

## E.7. Hệ số biến thiên khác (khi E.2–E.6 không đủ)

1. **Bỏ số hạng $y'$ (dạng chuẩn / Liouville):** $y = u\,\exp\!\big(-\tfrac12\!\int p\,dx\big)$ ⇒
$$u'' + \Big(q - \tfrac{p^2}{4} - \tfrac{p'}{2}\Big)u = 0.$$
   Nhìn vào hàm $Q(x)=q-\frac{p^2}{4}-\frac{p'}{2}$: $Q>0$ → dao động; $Q<0$ → mũ. Khi $Q$ biến thiên chậm → **xấp xỉ WKB**: $u\approx Q^{-1/4}\cos\!\big(\!\int\!\sqrt Q\,dx+\varphi\big)$.
2. **Đoán nghiệm** + **hạ bậc** (E.5).
3. **Chuỗi lũy thừa** $y = \sum a_nx^n$ (tại điểm thường), **Frobenius** $y = x^s\sum a_nx^n$ (tại điểm kỳ dị chính quy): cho hệ thức truy hồi cho $a_n$.
4. **Nhận diện các phương trình kinh điển** (tra giáo trình, không tự giải lại):

| Phương trình | Tên | Gặp ở |
|---|---|---|
| $x^2y''+xy'+(x^2-\nu^2)y=0$ | Bessel | sóng trụ, trống, điện từ trụ |
| $(1-x^2)y''-2xy'+\ell(\ell+1)y=0$ | Legendre | thế đối xứng cầu |
| $y''-xy=0$ | Airy | hạt trong trường đều, quang hình học tới hạn |
| $y''-2xy'+2ny=0$ | Hermite | dao động tử điều hòa lượng tử |

---

## E.8. Công cụ nâng cao (nhận biết, không bắt buộc)

- **Biến đổi Laplace:** biến PTVP hệ số hằng thành phương trình **đại số**, tự đưa điều kiện đầu vào: $\mathcal L\{y'\}=sY-y(0)$, $\mathcal L\{y''\}=s^2Y-sy(0)-y'(0)$. Rất mạnh cho lực cưỡng bức xung/đoạn.
- **Hàm Green** $G(t,t')$: đáp ứng với xung $\delta(t-t')$. Nghiệm $y_p = \int G(t,t')f(t')\,dt'$ (nguyên lý chồng chất của "nhiều xung nhỏ"). Với dao động tắt dần yếu: $G(t) = \dfrac{1}{m\omega_d}e^{-\delta t}\sin\omega_dt\ (t>0)$.

---

# PHẦN F. "BẤT BIẾN" VÀ ĐỐI XỨNG: VÌ SAO CÁC THUẬT TOÁN HOẠT ĐỘNG

Đây là **lớp nhận diện sâu** (theo đúng tinh thần "tìm CHỖ" của bạn). Hầu hết kỹ thuật giải PTVP là **khai thác một đối xứng** của phương trình.

## F.1. Bảng "đối xứng ↔ kỹ thuật"

| Đối xứng/bất biến của PTVP | Nhận diện bằng tay | Kỹ thuật khai thác | Mục |
|---|---|---|---|
| **Tịnh tiến theo $x$** (vắng $x$) | Không có $x$ tường minh | $y'$ thành hàm của $y$ ($p(y)$): hạ bậc | D.2, E.1.b |
| **Tịnh tiến theo $y$** (vắng $y$) | Chỉ có $y', y''$ | $p = y'$ | E.1.a |
| **Co giãn đồng thời** $(x,y)\to(\lambda x,\lambda y)$ | Vế phải $F(y/x)$ | $u = y/x$ | D.4 |
| **Co giãn riêng** $x\to\lambda x$ (với $x^ky^{(k)}$) | Mỗi hạng $x^ky^{(k)}$ | $t = \ln x$ hoặc $y = x^r$ | E.6 |
| **Co giãn riêng $y\to\lambda y$** (thuần nhất theo $y$ và đạo hàm) | PTVP bất biến khi $y\to\lambda y$ | $z = y'/y$ | E.1.d |
| **Tuyến tính** (cộng được nghiệm) | $y,y',y''$ bậc 1 | $y = y_h+y_p$, chồng chất | D.3, E.2–E.4 |
| **Có đại lượng bảo toàn** | Tồn tại $F$ với $dF=0$ dọc nghiệm | Tích phân đầu (hạ bậc) | D.7, E.1.c |

> **Triết lý:** *"Một đối xứng ⇒ hạ được một bậc."* Đây chính là lý do cơ học dùng bảo toàn năng lượng (đối xứng tịnh tiến thời gian), bảo toàn động lượng (tịnh tiến không gian), bảo toàn mômen động lượng (quay): **mỗi bảo toàn là một lần hạ bậc cho PTVP chuyển động** (định lý Noether).

## F.2. Bất biến nhận diện (checklist số)

Các **đại lượng tính được** quyết định phương pháp:

| Đại lượng | Công thức | Ý nghĩa |
|---|---|---|
| Bậc đồng nhất | $M(tx,ty)=t^nM$ | $M,N$ cùng $n$ → đẳng cấp |
| Tính "toàn phần" | $M_y-N_x$ | $=0$ → toàn phần |
| Tỉ số thừa số tích phân | $(M_y-N_x)/N$, $(N_x-M_y)/M$ | chỉ theo 1 biến → $\mu(x)$ hoặc $\mu(y)$ |
| Biệt thức đặc trưng | $\Delta=b^2-4ac$ | 3 trường hợp E.2 |
| Wronskian | $W=y_1y_2'-y_1'y_2$ | độc lập tuyến tính; $W\ne0$ |
| Bội nghiệm đặc trưng $s$ | Số lần $r$ là nghiệm | cộng hưởng: nhân $x^s$ |
| $f'(y^*)$ (bậc 1), $V''(x^*)$ (bậc 2) | Đạo hàm tại cân bằng | ổn định / tần số riêng (Phần G) |

## F.3. Co giãn thứ nguyên (phân tích thứ nguyên + biến không thứ nguyên)

**Thuật toán "vô thứ nguyên hóa":**
1. Liệt kê tham số và thứ nguyên của chúng.
2. Chọn thang đo đặc trưng (thời gian $\tau$, độ dài $\ell$…) từ chính tham số.
3. Thế $x = \ell\,\xi,\ t = \tau\,s$; chọn $\tau,\ell$ để **hệ số trở thành 1** càng nhiều càng tốt.
4. Còn lại các **nhóm không thứ nguyên** $\Pi$.

**Ví dụ:** $\dot v = g(1 - v^2/v_t^2)$: đặt $\tilde v = v/v_t,\ s = gt/v_t$ ⇒ $\dfrac{d\tilde v}{ds} = 1 - \tilde v^2$, **không còn tham số nào**: mọi bài toán lực cản bậc hai là *một* bài. Đáp án $\tilde v = \tanh s$.

Lợi ích: biết ngay các thang $\tau=v_t/g$, bớt sai lầm, kiểm chứng giới hạn dễ.

---

# PHẦN G. PHÂN TÍCH ĐỊNH TÍNH VÀ TUYẾN TÍNH HÓA

Nhiều đề thi **không đòi** nghiệm tường minh; chỉ hỏi chu kỳ, điều kiện ổn định, hành vi dài hạn.

## G.1. Bậc 1 ô-tô-nôm $y' = f(y)$: **đường pha**

1. Giải $f(y^*) = 0$ → các **điểm cân bằng**.
2. Xét dấu $f$ giữa các điểm cân bằng: $f>0$ ⇒ $y$ tăng; $f<0$ ⇒ $y$ giảm.
3. **Ổn định:** $f'(y^*)<0$ → ổn định; $f'(y^*)>0$ → không ổn định; $f'(y^*)=0$ → xét thêm.
4. Nghiệm đơn điệu, **không** thể vượt qua một cân bằng (do duy nhất nghiệm).

**Ví dụ logistic:** $f = rN(1-N/K)$: cân bằng $0$ (không ổn định) và $K$ (ổn định).

## G.2. Bậc 2: tuyến tính hóa quanh cân bằng (**dao động bé**)

Với $m\ddot x = -V'(x)$ (hoặc tổng quát $\ddot q = F(q)$):
1. **Cân bằng** $x^*$: $V'(x^*)=0$.
2. Khai triển Taylor: $V(x)\approx V(x^*) + \tfrac12V''(x^*)(x-x^*)^2$.
3. Đặt $\xi = x-x^*$: $m\ddot\xi = -V''(x^*)\,\xi$ ⇒ dao động điều hòa với
$$\boxed{\omega^2 = \frac{V''(x^*)}{m}}\quad (V''(x^*)>0\ \text{ổn định}).$$
4. Nếu $V''(x^*)<0$: $\xi\sim e^{\pm\sqrt{|V''|/m}\,t}$ → mất ổn định.

**Điều kiện Pre (cảnh báo):** biên độ **đủ nhỏ** để bỏ số hạng bậc cao $O(\xi^3)$; nếu $V''(x^*)=0$ thì phải giữ số hạng bậc cao (dao động không điều hòa, chu kỳ phụ thuộc biên độ).

## G.3. Mặt phẳng pha $(x,\dot x)$

- Quỹ đạo là đường mức của năng lượng $E=\tfrac12m\dot x^2+V(x)$ (hệ bảo toàn).
- **Tâm** (đường đóng): cân bằng ổn định (cực tiểu $V$).
- **Điểm yên** (đường phân kỳ): cực đại $V$.
- **Có ma sát:** quỹ đạo xoắn vào cân bằng ổn định (**tiêu điểm** hoặc **nút**).
- **Separatrix** (đường phân cách) là quỹ đạo qua điểm yên: ngăn cách dao động và quay (ví dụ con lắc có $E=2mg\ell$).

## G.4. Khi cần số

**Phương pháp Euler** (chỉ để hiểu): $y_{n+1} = y_n + h\,f(x_n,y_n)$. **Bậc 2 → hệ bậc 1:** đặt $v=y'$: $\ y'=v,\ v'=f(x,y,v)$. Trên thực tế dùng Runge–Kutta (RK4).

---

# PHẦN H. QUY TRÌNH TỔNG HỢP, KIỂM CHỨNG, CÁC BẪY

## H.1. Thuật toán tổng hợp (từ đề Vật Lý đến đáp số)

```
1. Dựng PTVP từ Vật Lý (B.1): ẩn, dấu, trạng thái tổng quát, định luật gốc, ĐK đầu.
2. Vô thứ nguyên hóa (F.3) nếu có nhiều tham số.
3. Phân loại thô (C.1): bậc, tuyến tính?, hệ số hằng?, ô-tô-nôm?
4. Chạy cây quyết định (C.2 hoặc C.3); tính các bất biến (F.2).
5. Áp dụng thuật toán tương ứng (Phần D/E); NHỚ nghiệm hằng, nghiệm đặc biệt.
6. Dùng điều kiện đầu để cố định hằng số (lên nghiệm TỔNG).
7. Kiểm chứng (H.2).
8. Diễn giải Vật Lý: các thang thời gian, giới hạn, hành vi dài hạn.
```

## H.2. Kiểm chứng (cực kỳ quan trọng, vì *PTVP rất dễ sai dấu*)

1. **Thế ngược:** nghiệm vào PTVP và vào **từng** điều kiện đầu.
2. **Thứ nguyên:** từng số hạng của PTVP cùng thứ nguyên; đối số của $e,\sin,\ln$ phải **không thứ nguyên**.
3. **Giới hạn:** $t\to0$ (khớp ĐK đầu), $t\to\infty$ (khớp cân bằng/xác lập), $\gamma\to0$, $\omega\to\omega_0$.
4. **Định tính:** nghiệm có hành vi (đơn điệu, dao động, tắt dần) đúng như trực giác Vật Lý của PTVP không?
5. **Bảo toàn:** nếu hệ bảo toàn, năng lượng/động lượng có giữ không?

## H.3. Các bẫy kinh điển

| Bẫy | Biểu hiện | Cách tránh |
|---|---|---|
| **Mất nghiệm hằng** | Chia cho $g(y)$ trong tách biến | Giải $g(y)=0$ trước |
| **Sai dấu lực cản** | $-kv^2$ cả hai chiều chuyển động | Dùng $-kv|v|$; chia giai đoạn |
| **Vẽ trạng thái đặc biệt** | Mất hạng tử khi dựng PTVP | Vẽ trạng thái tổng quát (B.1.3) |
| **Cộng hưởng bỏ sót** | $y_p$ thử trùng $y_h$ | So $r$ với nghiệm đặc trưng, nhân $x^s$ |
| **ĐK đầu lên $y_h$ thay vì $y$** | Hằng số sai | Chỉ dùng ĐK đầu **sau** khi có $y=y_h+y_p$ |
| **Tuyến tính hóa quá tay** | Dùng $\sin\theta\approx\theta$ với góc lớn | Ghi rõ **sai số** (Err), kiểm biên độ |
| **Khối lượng biến thiên** | $m\vec a$ thay vì $d\vec p/dt$ | Luôn viết $F=dp/dt$ |
| **Bỏ $|\cdot|$ khi tích phân** | $\int dy/y=\ln y$ | $\ln|y|$ và hấp thụ $\pm$ |
| **Không chuẩn hóa $y''$** (biến thiên hằng số) | $f$ thiếu hệ số chia | Chia cho $a$ trước |
| **Nghiệm không tồn tại toàn cục** | $y=1/(1-x)$ | Ghi khoảng nghiệm hợp lệ |
| **Nhầm hai nghĩa "thuần nhất"** | Dùng sai công cụ | A.2 |

## H.4. "Pre / Post" của vài phương pháp (theo ngôn ngữ mô hình hình thức của bạn)

| Phương pháp $\ell$ | $\mathrm{Pre}(\ell)$ (nhận diện, kiểm được) | $\mathrm{Post}(\ell)$ | Lưu ý/Err |
|---|---|---|---|
| Tách biến | $y'=f(x)g(y)$ | $\int dy/g=\int f\,dx+C$ | mất nghiệm $g=0$ |
| Thừa số tích phân (tuyến tính) | $y'+py=q$, $p,q$ liên tục | $y=e^{-P}(\int qe^P+C)$ | nghiệm toàn cục trên khoảng liên tục |
| Đẳng cấp | $M,N$ cùng bậc đồng nhất | $u=y/x$, tách biến | tìm cả $y=u^*x$ |
| Bernoulli | $y'+py=qy^n$ | $z=y^{1-n}$ tuyến tính | kiểm $y\equiv0$ |
| Toàn phần | $M_y=N_x$ | $F(x,y)=C$ | miền đơn liên |
| Đặc trưng | hệ số hằng, thuần nhất | $e^{\lambda x}$ theo $\Delta$ | ba trường hợp |
| Hệ số bất định | $f$ lớp đa thức·mũ·lượng giác | $y_p$ với $x^s$ | cộng hưởng |
| Biến thiên hằng số | biết $y_1,y_2$, $W\ne0$ | công thức tích phân | chuẩn hóa $y''$ |
| Tích phân năng lượng | $y''=f(y)$ | $\tfrac12y'^2-\int f=E$ | cần dấu căn, điểm quay |
| Tuyến tính hóa | cân bằng, biên độ bé | $\omega^2=V''/m$ | $V''(x^*)\ne0$; sai số $O(A^2)$ |

---

# PHẦN I. BÀI TẬP CÓ HƯỚNG DẪN

> **Cách dùng:** tự giải **trên giấy trắng** trước khi đọc đáp án (phản ánh nguyên tắc "đừng ảo tưởng hiểu"). Với mỗi bài, **ghi rõ** bạn đã chạy qua cây quyết định ở nút nào.

**Bài 1.** $y' - \dfrac{y}{x} = x$. *(Gợi ý: D.3.)*
**Đáp:** $y = x^2 + Cx$.

**Bài 2.** $(x^2+y^2)\,dx - 2xy\,dy = 0$. *(D.4.)*
**Đáp:** $x^2 - y^2 = Cx$ (và $x=0$ xét riêng).

**Bài 3.** $y' + \dfrac{y}{x} = y^2$. *(D.6.)*
**Đáp:** $y=\dfrac{1}{x(C-\ln x)}$, $y\equiv0$.

**Bài 4.** $(2xy+3)dx + (x^2-1)dy=0$. *(D.7.)*
**Đáp:** $x^2y + 3x - y = C$.

**Bài 5.** $(x+y^2)dx - 2xy\,dy=0$. *(D.7, thừa số $x^{-2}$.)*
**Đáp:** $\ln|x| - y^2/x = C$.

**Bài 6.** $y''-3y'+2y=e^x$. *(E.3, cộng hưởng.)*
**Đáp:** $y=C_1e^x + C_2e^{2x} - xe^x$.

**Bài 7.** $y''+y=\tan x$. *(E.4.)*
**Đáp:** $y = C_1\cos x + C_2\sin x - \cos x\ln|\sec x+\tan x|$.

**Bài 8.** $x^2y''-xy'-3y=0$. *(E.6.)*
**Đáp:** $y=C_1x^3 + C_2x^{-1}$.

**Bài 9.** $y''+(y')^2=0$. *(E.1.a.)*
**Đáp:** $y=\ln|x+C_1|+C_2$ (và $y=C$).

**Bài 10 (Vật Lý – xích trượt khỏi bàn).** Một sợi xích đồng chất dài $L$, đặt trên mặt bàn **nhẵn**, ban đầu để thòng một đoạn $x_0$ ở mép bàn rồi thả (đầu thả vận tốc 0). Tìm $x(t)$ (đoạn thòng xuống).

*Hướng dẫn:* trạng thái bất kỳ: lực kéo cả xích = trọng lượng đoạn thòng $=\lambda xg$; khối lượng cả xích $\lambda L$ ⇒ $\lambda L\ddot x = \lambda gx \Rightarrow \ddot x = \dfrac{g}{L}x$. **Hệ số hằng, thuần nhất** (E.2) với $\lambda^2=g/L>0$ ⇒ nghiệm **hyperbol** (không dao động).
**Đáp:** $x(t) = x_0\cosh\!\sqrt{g/L}\,t$.
*Pre/Bẫy:* giả sử xích luôn nằm trên bàn và đoạn thòng thẳng đứng, bỏ qua độ cong ở mép; $x$ chỉ hợp lệ đến khi $x=L$.

**Bài 11 (Vật Lý – lực cản bậc nhất, quãng đường).** Ném một vật theo phương ngang với vận tốc $v_0$, lực cản $-\gamma\vec v$, bỏ qua trọng lực. Tìm quãng đường tối đa.
*Hướng dẫn:* $m\dot v = -\gamma v$ (D.2/D.3) → $v=v_0e^{-\gamma t/m}$ → $x(t)=\dfrac{mv_0}{\gamma}(1-e^{-\gamma t/m})$. $x_{\max}=\dfrac{mv_0}{\gamma}$.
*Cách khác (E.1.b):* $m\,v\,\dfrac{dv}{dx} = -\gamma v \Rightarrow v = v_0-\dfrac{\gamma}{m}x$, $v=0$ khi $x=\dfrac{mv_0}{\gamma}$. **Đối chiếu hai cách** là kiểm chứng.

**Bài 12 (Vật Lý – dao động cưỡng bức).** $\ddot x + 2\delta\dot x + \omega_0^2x = a\cos\omega t$.
(a) Tìm $x_p$ bằng phức hóa. (b) Xác định $\omega$ làm $A$ cực đại. (c) Khi $\delta=0,\ \omega=\omega_0$, dạng nghiệm?
**Đáp:** xem E.3. (a) $x_p=\mathrm{Re}\!\Big[\dfrac{a\,e^{i\omega t}}{\omega_0^2-\omega^2+2i\delta\omega}\Big]$. (b) $\omega_r=\sqrt{\omega_0^2-2\delta^2}$. (c) $x_p=\dfrac{a}{2\omega_0}t\sin\omega_0t$.

**Bài 13 (Vật Lý – tuyến tính hóa).** Hạt khối lượng $m$ trong thế $V(x)=V_0\big[(x/a)^4 - 2(x/a)^2\big]$. Tìm các cân bằng và tần số dao động bé quanh cân bằng ổn định.
*Hướng dẫn:* $V' = 4V_0(x^3/a^4 - x/a^2)=0 \Rightarrow x=0,\pm a$. $V''(x)=4V_0(3x^2/a^4-1/a^2)$: $V''(0)=-4V_0/a^2<0$ (**không ổn định**), $V''(\pm a)=8V_0/a^2>0$ (**ổn định**) ⇒ $\omega=\sqrt{\dfrac{8V_0}{ma^2}}$.

**Bài 14 (tự nghĩ).** Chọn một bài Vật Lý bạn từng làm sai, **dựng lại PTVP bằng quy trình B.1**, rồi chạy cây quyết định C. Ghi lại: nút nào bạn đã *đoán* thay vì *kiểm bất biến*?

---

# PHẦN J. BẢNG TRA NHANH VÀ TÀI LIỆU

## J.1. Bảng tra nhanh (bậc 1)

| Dạng | Nhận diện | Phép thế / công thức |
|---|---|---|
| Tách biến | $y'=f(x)g(y)$ | $\int dy/g=\int f\,dx$ |
| Tuyến tính | $y'+py=q$ | $y=e^{-P}(\int qe^P\,dx+C)$ |
| Đẳng cấp | $y'=F(y/x)$ | $u=y/x$ |
| $F(ax+by+c)$ | tổ hợp tuyến tính | $u=ax+by+c$ |
| Bernoulli | $y'+py=qy^n$ | $z=y^{1-n}$ |
| Toàn phần | $M_y=N_x$ | $F=\int M\,dx+g(y)$ |
| Thừa số TP | $(M_y-N_x)/N=h(x)$ | $\mu=e^{\int h}$ |
| Riccati | biết $y_1$ | $y=y_1+1/v$ |

## J.2. Bảng tra nhanh (bậc 2)

| Dạng | Nhận diện | Cách giải |
|---|---|---|
| Vắng $y$ | $F(x,y',y'')$ | $p=y'$ |
| Vắng $x$ | $F(y,y',y'')$ | $y''=p\,dp/dy$ |
| $y''=f(y)$ | | $\frac12y'^2-\int f=E$ |
| Hệ số hằng | $ay''+by'+cy=0$ | đặc trưng, 3 trường hợp |
| Hệ số bất định | $f=P e^{rx}$, $\cos$, $\sin$ | $y_p=x^s(\dots)$ |
| Biến thiên hằng số | biết $y_1,y_2$ | $y_p=-y_1\!\int\!\frac{y_2f}{W}+y_2\!\int\!\frac{y_1f}{W}$ |
| Euler–Cauchy | $x^2y''+axy'+by=0$ | $y=x^r$ hoặc $t=\ln x$ |
| Biết 1 nghiệm | $y_1$ | $y_2=y_1\!\int\!e^{-\int p}/y_1^2$ |
| Dạng chuẩn | $y''+py'+qy=0$ | $y=u\,e^{-\frac12\int p}$ |

## J.3. Dao động (công thức hay dùng)

$$\omega_0=\sqrt{k/m},\quad \delta=\frac{\gamma}{2m},\quad \omega_d=\sqrt{\omega_0^2-\delta^2},\quad Q\approx\frac{\omega_0}{2\delta}.$$
Tương tự cơ–điện: $m\to L,\ \gamma\to R,\ k\to1/C,\ x\to q$ (mạch RLC nối tiếp: $\omega_0=1/\sqrt{LC}$, $\delta=R/2L$).

## J.4. Tài liệu

- **Toán:** Mary L. Boas, *Mathematical Methods in the Physical Sciences* (chương PTVP); Boyce & DiPrima, *Elementary Differential Equations*; V. I. Arnold, *Ordinary Differential Equations* (hình học/định tính, rất sâu); Tenenbaum & Pollard (nhiều ví dụ).
- **Vật Lý:** Morin, *Introduction to Classical Mechanics* (dao động, các bài PTVP); Kleppner & Kolenkow; Landau & Lifshitz, *Mechanics* (§ dao động bé, tích phân đầu); Taylor, *Classical Mechanics* (dao động tắt dần/cưỡng bức, mặt phẳng pha).
- **Trực giác:** 3Blue1Brown (series Differential Equations), mô phỏng PhET (mass–spring), phần mềm vẽ trường hướng (ví dụ Desmos/GeoGebra).

---

## LỜI KẾT

PTVP không phải là "một chương đáng sợ cần học thuộc 30 dạng". Nó là **ngôn ngữ của sự biến thiên**, và việc giải nó là:

1. **Dựng** đúng luật cục bộ (Vấn đề 2 — khó nhất, và cũng quyết định đáp án).
2. **Nhận diện** bất biến/đối xứng của phương trình (một cây quyết định hữu hạn, nhỏ).
3. **Khai thác** đối xứng để hạ bậc hoặc tuyến tính hóa (mỗi thuật toán là một "CHỖ" hợp lệ).
4. **Kiểm chứng** bằng thế ngược, thứ nguyên, giới hạn.

Hãy tự tay giải mọi ví dụ trên giấy trắng. *Hiểu ≠ Làm được.*
