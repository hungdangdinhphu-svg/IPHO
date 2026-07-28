# CÁCH GIẢI TỔNG QUÁT : Cơ & Điện-Từ học (Tổng hợp và soạn lại)

Lưu ý quan trọng : Tôi giả định rằng ta đã học và đã làm nhiều bài tập và đọc nhiều lý thuyết để ta có dày dặn kinh nghiệm, pattern, case-by-case từ trước. Những gì tôi ghi ở bên dưới đều chỉ liên quan đến những gì thực sự tổng quát hoặc cực kỳ phổ biến.

---

## PHẦN I — SƠ ĐỒ TỔNG QUÁT: QUY TRÌNH 10 BƯỚC (B0 → B10)

```
B0  Quét văn bản & hình ảnh — trích xuất dữ kiện
B1  Định nghĩa Hệ & lựa chọn hệ quy chiếu
B2  Đếm Bậc Tự Do thô (f_raw)                         [Trụ cột A]
B3  Liệt kê Ràng buộc                                 [Trụ cột B]
B4  Săn Đối xứng / Định luật bảo toàn (Noether)       [Trụ cột C]
B5  Chọn Tọa độ suy rộng tối thiểu (f_eff)
B6  Xấp xỉ hóa & Phân tích thang đo                   [Trụ cột D]
B7  Chọn "ngôn ngữ chi phối" đúng 
B8  Điều kiện biên & điều kiện đầu (nguồn tin ẩn thứ 2)
B9  Giải hệ (đại số / vi phân / đồ thị / số)
B10 Kiểm tra ngược — Verification Protocol
```


---

## B0 — QUÉT (Full Scan Protocol)

**Nguyên tắc:** Đề bài là dữ liệu nén — mỗi tính từ, mỗi con số, mỗi đường nét trong hình/văn bản đều mang thông tin.

**Thủ tục bắt buộc:**

1. Đọc chậm **toàn bộ** đề một lượt, không giải, chỉ **gạch chân**:
   - Mọi đại lượng đã cho (kèm đơn vị, và **dấu** nếu có: đại số hóa mọi đại lượng ngay từ đầu — dòng điện, điện tích, công,.. đều là đại lượng có dấu);
   - Mọi tính từ mô tả (nhẹ, lý tưởng, không ma sát, rất dài, mảnh, đồng chất, chuẩn tĩnh, đủ lâu, ban đầu, tức thời…);
   - Động từ chỉ hành động/biến cố (thả ra, đóng khóa K, đảo cực, cắt dây, va chạm…);
   - Câu hỏi thật sự (đại lượng cần tìm — đây là "biến mục tiêu", định hướng bạn chọn phương pháp ở B7).
2. Nếu có hình: quét **trái→phải, trên→dưới**, liệt kê **từng** phần tử (điện trở, tụ, cuộn, ròng rọc, bản lề, mặt tiếp xúc…) và **từng** ký hiệu góc/khoảng cách/chiều mũi tên dòng điện — dấu mũi tên = quy ước dấu, không phải chiều thật.
3. Lập **Bảng biến số**: | Đã cho | Ký hiệu | Ẩn cần tìm | — việc lập bảng buộc não bộ tường minh hóa từng dữ kiện thay vì "cảm giác đã hiểu".
4. **Tự vẽ lại hình** (kể cả khi đề đã có hình) — thao tác vẽ lại chính là bước đầu tiên của B1/B2, và nó lộ ra ràng buộc mà mắt "lướt qua" khi chỉ nhìn hình có sẵn.
5. Đặc biệt với hình: **không giả định gì không được vẽ hoặc không được nói** (ví dụ không tự thêm ma sát nếu đề không nói có; nhưng cũng không tự loại bỏ ma sát nếu đề không nói "không ma sát" — xem Từ điển B3).

---



## B1 — ĐỊNH NGHĨA HỆ & HỆ QUY CHIẾU

- **Hệ là gì?** Liệt kê từng vật thể/mỗi phần tử là một "hệ con". Áp dụng **idea 4** (Kalda): đôi khi coi *toàn bộ* nhiều vật là **một hệ** (loại bỏ nội lực chưa biết) lợi hơn xét từng vật; đôi khi phải **tách** ra (idea 47: vật "nhẹ" ⇒ hợp lực & hợp mô-men trên nó luôn bằng 0, dùng để tách ẩn).

- **Chọn hệ quy chiếu thông minh** & idea 7, idea K-7, idea 73


---


## PHẦN 2 — TRỤ CỘT A: BẬC TỰ DO (Degrees of Freedom)


### 2.2 Định lý A (Đếm bậc tự do — Định lý Giá trị Chính quy)

> **Định lý A.** Cho $N$ toạ độ thô $x=(x^1,\dots,x^N)\in\mathbb R^N$ và $k$ hàm ràng buộc toàn chỉnh $g_1,\dots,g_k: \mathbb R^N\times\mathbb R\to\mathbb R$, $g_j(x,t)=0$. Giả sử tại điểm đang xét, ma trận Jacobi $\partial(g_1,\dots,g_k)/\partial x$ có **hạng đầy đủ** $k$ (đây là định nghĩa chính xác, kiểm tra được, của "$k$ ràng buộc độc lập"). Khi đó tập nghiệm $Q_t = \{x: g_j(x,t)=0\ \forall j\}$ là một đa tạp trơn với
> $$\dim Q_t = N-k = f.$$

**Chứng minh.** Đây là hệ quả trực tiếp của Định lý Hàm ẩn. Vì hạng Jacobi $=k$, sau khi (nếu cần) sắp lại thứ tự toạ độ, ma trận con $k\times k$ gồm các đạo hàm riêng theo $k$ biến cuối $x^{N-k+1},\dots,x^N$ khả nghịch tại điểm $x_0$. Định lý Hàm ẩn cho phép giải $k$ biến này như hàm trơn của $N-k$ biến còn lại trong một lân cận của $x_0$: $x^{N-k+i} = \varphi_i(x^1,\dots,x^{N-k})$. Ánh xạ $x\mapsto (x^1,\dots,x^{N-k})$ hạn chế trên $Q_t$ do đó là một vi phôi địa phương lên một tập mở của $\mathbb R^{N-k}$. Vậy $Q_t$ trơn, chiều $N-k$ tại lân cận mọi điểm thoả điều kiện hạng. $\blacksquare$

Định lý A **hoàn toàn tổng quát và thuật toán** — cho $N,k$ và các $g_j$, việc tính hạng Jacobi là đại số tuyến tính thuần tuý (khử Gauss), không cần trực giác.


- Bậc tự do là số chiều của đa tạp không gian cấu hình Q; Và f = N - k khi điều kiện k phương trình đều độc lập tuyến tính với nhau.

- Đếm số xem hệ vật lý được mô tả gồm bao nhiêu "vật rắn/chất điểm" độc lập

- Và check xem loại khớp nối/ràng buộc nào áp dụng

- Từ đó tính ra số bậc tự do mà ta cần

**Quy tắc kiểm tra (Fact 18 tổng quát hóa):**
$$f_{\text{eff}} = f_{\text{raw}} - (\text{số ràng buộc độc lập tìm được ở B3}) - (\text{số bảo toàn/đối xứng tìm được ở B4})$$

**Vấn đề phát sinh 1 : "loại khớp nối nào áp dụng", làm sao để đảm bảo rằng xấp xỉ 100% học sinh sở hữu trực giác trung bình sẽ không gặp vấn đề gì tại IPHO/VPHO do cái phát sinh này?**


---


## PHẦN 3 — TRỤ CỘT B: RÀNG BUỘC & BIÊN

> Mỗi ràng buộc hình học/vật lý = **1 phương trình liên hệ giữa các DOF**, làm $f_{eff}$ giảm đi đúng **1**.

**Phép kiểm tra gốc (khi từ khóa không rõ / bị "giấu"):** dùng **phép dịch chuyển ảo (virtual displacement)** — tưởng tượng hệ nhích một lượng vi phân $\delta$, hỏi "đại lượng nào **buộc phải không đổi**?" (chiều dài dây, thông lượng qua vòng siêu dẫn, điện tích trên vật cô lập…). Đây là cách tái tạo ràng buộc **từ nguyên lý đầu tiên**, không phụ thuộc từ khóa có xuất hiện hay không — đây là "lưới an toàn" chống lại việc đề bài dùng cách diễn đạt lạ để né từ khóa quen thuộc.


### 3.1 Chính xác hoá ranh giới toàn chỉnh / không toàn chỉnh

`[MD]` định nghĩa holonomic là $F(q,t)=0$, non-holonomic là bất phương trình hoặc vi phân không tích phân được $\sum A_i\,dq_i+A_t\,dt=0$. Câu hỏi tự nhiên: *"làm sao biết một ràng buộc vi phân cho trước có 'thực sự' không tích phân được hay không, một cách tổng quát, không case-by-case?"* — Câu trả lời là **có**, và đó là nội dung Định lý B dưới đây (đây là phần bị bỏ ngỏ hoàn toàn trong `[MD]`).

> **Định lý B (Tiêu chuẩn Frobenius).** Cho ràng buộc Pfaff $\omega = \sum_i A_i(q,t)\,dq^i + A_t(q,t)\,dt = 0$ (một dạng vi phân bậc 1). Ràng buộc này là **toàn chỉnh** (tồn tại thừa số tích phân $\mu$ và hàm $F$ sao cho $\omega=\mu\,dF$, tức mặt $F=$const chứa trọn quỹ đạo) **khi và chỉ khi**
> $$\omega\wedge d\omega = 0.$$
> Đây là một phép kiểm tra **thuật toán, tổng quát tuyệt đối** trên lớp ràng buộc Pfaff đơn: chỉ cần lấy vi phân ngoài và nhân ngoài, không cần đoán.

*(Đây là định lý Frobenius/Pfaff cổ điển trong hình học vi phân; whitepaper không chứng minh lại từ tiên đề hình học vi phân — vượt phạm vi IPhO — mà **kiểm chứng tính đúng đắn bằng hai ví dụ tính tay độc lập, đầy đủ**, đủ để một học sinh IPhO tự tay áp dụng.)*

**Ví dụ kiểm chứng B.1 (toàn chỉnh).** Đĩa bán kính $R$ lăn không trượt trên một đường thẳng: $\dot x = R\dot\theta \Rightarrow \omega = dx - R\,d\theta$. Vì $R$ hằng, $d\omega = 0$, nên $\omega\wedge d\omega = \omega\wedge 0=0$ tự động. **Toàn chỉnh** — tích phân trực tiếp: $x-R\theta=$const. (Đây chính là cơ sở toán học của các ràng buộc lăn dùng xuyên suốt `[MEH, pr. 44, 47, 65]`, nơi ràng buộc lăn được dùng như một phương trình đại số bình thường.)

**Ví dụ kiểm chứng B.2 (không toàn chỉnh — "xe đạp một bánh"/đĩa lăn tự do đổi hướng).** Cấu hình $(x,y,\theta)$, ràng buộc "không trượt ngang": $-\sin\theta\,dx+\cos\theta\,dy=0$, tức $\omega=-\sin\theta\,dx+\cos\theta\,dy$.
$$d\omega = -\cos\theta\,d\theta\wedge dx-\sin\theta\,d\theta\wedge dy.$$
Tính trực tiếp (khai triển đầy đủ, dùng phản đối xứng $dq^i\wedge dq^j=-dq^j\wedge dq^i$, $dq^i\wedge dq^i=0$):
$$\omega\wedge d\omega = -\,dx\wedge dy\wedge d\theta \;\neq\; 0.$$
**Không toàn chỉnh.** Đây là lý do toán học nghiêm ngặt vì sao một chiếc xe/đĩa có thể đi từ *bất kỳ* cấu hình $(x,y,\theta)$ nào đến *bất kỳ* cấu hình nào khác (đỗ xe song song!) dù tại mỗi thời điểm chỉ có 1 bậc tự do vận tốc khả dĩ: không gian cấu hình *không* bị thu hẹp, dù không gian *vận tốc tức thời* bị thu hẹp — **đúng chính xác** như câu chữ của `[MD]`: *"Non-holonomic... giới hạn quỹ đạo tiến triển của hệ"* chứ không làm giảm DOF của $\mathcal Q$. Whitepaper này đã **chứng minh** thay vì chỉ khẳng định lại điều `[MD]` phát biểu.


**Quan sát quan trọng :**

Có một lớp tình huống mà Định lý A thất bại theo nghĩa kỹ thuật: khi số ràng buộc **hình học lý tưởng hoá** (dây/thanh cứng tuyệt đối) vượt quá số bậc tự do thực — hệ *siêu tĩnh*. `[MEH, idea 30]` chỉ ra chính xác đây là lúc mô hình "vật rắn tuyệt đối" phải được **nới lỏng** thành mô hình đàn hồi (`[MEH, fact 13]`, định luật Hooke $k=AY/L$) để đóng hệ phương trình.

---

## B4 — SĂN ĐỐI XỨNG: ĐỊNH LÝ NOETHER NHƯ MÁY GIẢM BẬC TỰ DO — [Trụ cột C]

> **Định lý Noether (diễn giải thực dụng):** *Nếu tồn tại một phép biến đổi liên tục làm cho toàn cảnh vật lý "trông y hệt như trước", thì tồn tại một đại lượng bảo toàn tương ứng.*

Đây là công cụ **mạnh nhất** để giảm bậc tự do *hiệu dụng* mà không cần giải phương trình vi phân — mỗi đối xứng tìm được cho ta **một tích phân đầu** (first integral), tức hạ bậc của hệ phương trình vi phân đi 1.


### 4.2. Thủ tục "săn" đối xứng

Với mỗi bài, **chủ động thử** từng phép biến đổi sau, hỏi "hiện tượng có trông y hệt không?":

1. **Tịnh tiến** hệ theo mỗi trục — còn ngoại lực dọc trục đó không?
2. **Quay** hệ quanh mỗi trục khả dĩ — còn ngoại mô-men không?
3. **Dịch thời gian** — các lực có phụ thuộc t một cách "ngoại lai" không (ví dụ mặt phẳng nghiêng đang được kéo di chuyển)? Nếu **không** ⇒ năng lượng bảo toàn.
4. **Phản xạ gương / hoán vị nhãn** hai bộ phận — bài có "trông giống" sau khi lật không?
5. **Co giãn tỉ lệ** (đổi thang đo) — cấu trúc bài có lặp lại chính nó không (mạng vô hạn, phân dạng)?
6. **Đảo dấu một biến** (đảo cực nguồn, đảo chiều vận tốc ban đầu) — hệ có đối xứng gì?

> **Cảnh báo (idea 42, idea 58):** Một định luật bảo toàn *chỉ đúng trong một khoảng thời gian/không gian nhất định* — kiểm tra lại điều kiện áp dụng mỗi khi có va chạm, ma sát xuất hiện, hoặc ngoại lực thay đổi bản chất. **Không thể** đồng thời có cả bảo toàn động lượng *và* bảo toàn động năng một cách "miễn phí" trừ khi được chứng minh (va chạm đàn hồi) — nếu bài yêu cầu dùng cả hai mà không nói rõ, ít nhất một trong hai **không** thật sự bảo toàn (idea 58) — đây là bẫy hay gặp.


Đây là trụ cột có nội dung toán học sâu nhất, và là nơi câu hỏi `[MD]` (*"phép biến đổi nào... cho tích phân đầu"*) cần một câu trả lời **tổng quát và chứng minh được** — không chỉ trường hợp đặc biệt "toạ độ cyclic" mà `[MD]` nêu.

### 4.1 Định lý C1 (Noether, dạng hữu hạn chiều, biến đổi không gian)

> **Định lý C1.** Cho $L(q,\dot q,t)$ với $q=(q^1,\dots,q^n)$ thoả phương trình Euler–Lagrange $\frac{d}{dt}\frac{\partial L}{\partial \dot q^i}=\frac{\partial L}{\partial q^i}$. Cho một trường véc-tơ $X=(X^1,\dots,X^n)$ trên không gian cấu hình (có thể phụ thuộc $t$), sinh ra họ biến đổi $q^i\mapsto q^i+\varepsilon X^i(q,t)$. Giả sử **với mọi** $(q,\dot q,t)$ (không chỉ dọc nghiệm):
> $$\sum_i\left[\frac{\partial L}{\partial q^i}X^i+\frac{\partial L}{\partial \dot q^i}\frac{dX^i}{dt}\right]=0,\qquad \frac{dX^i}{dt}:=\frac{\partial X^i}{\partial t}+\sum_j\frac{\partial X^i}{\partial q^j}\dot q^j. \tag{$*$}$$
> Khi đó đại lượng $I(q,\dot q,t)=\sum_i \dfrac{\partial L}{\partial \dot q^i}X^i(q,t)$ **bảo toàn** dọc mọi nghiệm: $\dfrac{dI}{dt}=0$.

**Chứng minh.** Dọc một nghiệm $q(t)$:
$$
\frac{dI}{dt}=\sum_i\left[\frac{d}{dt}\Big(\frac{\partial L}{\partial \dot q^i}\Big)X^i+\frac{\partial L}{\partial \dot q^i}\frac{dX^i}{dt}\right]
\stackrel{\text{E-L}}{=}\sum_i\left[\frac{\partial L}{\partial q^i}X^i+\frac{\partial L}{\partial \dot q^i}\frac{dX^i}{dt}\right]\stackrel{(*)}{=}0.\qquad\blacksquare
$$

**Điều kiện $(*)$ là tổng quát và thuật toán:** với **bất kỳ** $X$ *cho trước*, kiểm tra $(*)$ chỉ là đạo hàm riêng và cộng — có thể lập trình bằng phần mềm đại số máy tính, không cần trực giác. Phần "case-by-case" duy nhất trong toàn bộ trụ cột C là: **liệt kê $X$ nào đáng thử**, và Mục 4.3 sẽ chỉ ra đây là lớp $G_k$ (tổng-quát-hữu-hạn), không phải $C$ vô hạn.

### 4.2 Ba hệ quả tường minh — kiểm chứng từng bước, khớp `[MEH]`

**(a) Toạ độ cyclic $\Rightarrow$ động lượng suy rộng bảo toàn (đúng như `[MD]` nêu, nay được chứng minh chứ không chỉ khẳng định).**
Nếu $\partial L/\partial q^1\equiv 0$, chọn $X=(1,0,\dots,0)$ (hằng, $dX/dt=0$). $(*)$: $\frac{\partial L}{\partial q^1}\cdot 1+0=0$ — đúng theo giả thiết. $\Rightarrow I=\partial L/\partial \dot q^1=p_1=$const. Đây đúng là công thức `[MD]` cho, và cũng là ghi chú của `[MEH]` ở phần chú thích Phụ lục 6: *"in the case of translational symmetry we don't even need to use the Noether's theorem: $\partial L/\partial q_i=0$, hence $d/dt\,p_i=0$"*.

**(b) Đối xứng tịnh tiến toàn hệ $\Rightarrow$ bảo toàn động lượng tổng (`[MEH, fact 6]`).**
Xét $n$ chất điểm, $L=\sum_i \frac12 m_i|\dot r_i|^2-V(r_1,\dots,r_n)$, với $V$ chỉ phụ thuộc **hiệu** vị trí (bất biến tịnh tiến toàn cục). Lấy $X_i=\hat n$ (cùng một hằng véc-tơ cho mọi hạt), $dX/dt=0$. Điều kiện bất biến của chính $V$ dưới tịnh tiến toàn cục, lấy đạo hàm theo $\varepsilon$ tại $\varepsilon=0$, cho trực tiếp $\sum_i \nabla_i V\cdot \hat n=0$ với mọi $\hat n$ — đây chính là $(*)$ (vì $\partial L/\partial \dot r_i\cdot \hat n$ không đóng góp gì vào phần đầu, và số hạng động năng không phụ thuộc $q$). Vậy $I=\sum_i m_i\dot r_i\cdot\hat n = P\cdot\hat n$ bảo toàn với mọi $\hat n$ $\Rightarrow$ $P=$const. $\blacksquare$ — khớp `[MEH, fact 6]` và cơ chế đúng như `[MEH, appendix 1]` (đạo hàm trực tiếp từ định luật III Newton).

**(c) Đối xứng quay toàn hệ $\Rightarrow$ bảo toàn mô-men động lượng (`[MEH, fact 7]`).**
Lấy $X_i(r)=\hat n\times r_i$ (phép quay vi phân quanh trục $\hat n$), tuyến tính theo $q$ nên $dX_i/dt=\hat n\times \dot r_i$. Với $V$ bất biến quay (phụ thuộc khoảng cách từng cặp $|r_i-r_j|$), cùng lý luận đạo hàm-tại-$\varepsilon=0$ cho $\sum_i\nabla_iV\cdot(\hat n\times r_i)=0$. Số hạng động năng: $\sum_i m_i\dot r_i\cdot(\hat n\times \dot r_i)=\sum_i m_i\hat n\cdot(\dot r_i\times\dot r_i)=0$ (dùng đẳng thức hoán vị vòng tích hỗn hợp $a\cdot(b\times c)=b\cdot(c\times a)$, và $\dot r_i\times \dot r_i=0$). Vậy $(*)$ thoả tự động, và
$$I=\sum_i m_i\dot r_i\cdot(\hat n\times r_i)\stackrel{\text{hoán vị vòng}}{=}\sum_i m_i\,\hat n\cdot(r_i\times\dot r_i)=\hat n\cdot L_{\text{tổng}}$$
bảo toàn với mọi $\hat n$ $\Rightarrow$ $L_{\text{tổng}}=$const. $\blacksquare$ — khớp `[MEH, fact 7]`.

**(d) Đối xứng tịnh tiến thời gian $\Rightarrow$ bảo toàn năng lượng (`[MEH, fact 8]`) — phát biểu tách biệt vì cần biến đổi $t$.**
Định nghĩa Hamilton hoá $H:=\sum_i \dot q^i \dfrac{\partial L}{\partial \dot q^i}-L$. Tính trực tiếp dọc nghiệm, dùng E-L:
$$
\frac{dH}{dt}=\sum_i\Big[\ddot q^i p_i+\dot q^i\dot p_i\Big]-\Big[\sum_i(\dot p_i\dot q^i+p_i\ddot q^i)+\frac{\partial L}{\partial t}\Big]=-\frac{\partial L}{\partial t}.
$$
Vậy **nếu $L$ không phụ thuộc tường minh vào $t$** (đối xứng tịnh tiến thời gian), $H=$const. Nếu thêm điều kiện động năng $T$ là hàm thuần nhất bậc 2 theo $\dot q$ (trường hợp cơ học chuẩn, ràng buộc không phụ thuộc $t$ — scleronomic), định lý Euler cho hàm thuần nhất ($\sum \dot q^i \partial T/\partial \dot q^i = 2T$, chứng minh: lấy đạo hàm $T(q,\lambda\dot q)=\lambda^2T(q,\dot q)$ theo $\lambda$ tại $\lambda=1$) cho $H=2T-(T-V)=T+V=E$. $\blacksquare$ — khớp `[MEH, fact 8]` và `[MEH, appendix 3]`.

### 4.3 Vì sao trụ cột C là $G_k$ (Tổng-quát-hữu-hạn) trên $\mathcal P_{\text{IPhO}}$

Mục 4.1–4.2 chứng tỏ: **cho trước** $X$, việc kiểm tra $(*)$ là thuật toán tuyệt đối (G). Câu hỏi còn lại: danh sách $X$ nào cần thử? Với hệ xây từ thư viện lực chuẩn IPhO (hấp dẫn/Coulomb — tâm; Hooke — cặp; trường ngoài đều), toàn bộ đối xứng khả dĩ nằm trong danh sách **hữu hạn**:

**Bảng C — danh mục $X$ hữu hạn cần thử (đúng nghĩa $G_k$, Định nghĩa 0.3):**

| # | Phép thử $X$ | Điều kiện áp dụng (thuật toán kiểm tra) | Đại lượng bảo toàn | Nguồn đối chiếu |
|---|---|---|---|---|
| 1 | Tịnh tiến dọc trục $\hat e_j$ | $q^j$ vắng mặt trong $L$ (cyclic) — kiểm tra bằng mắt/đạo hàm | $p_j$ | `[MEH, idea 34, idea 35, idea 43]` |
| 2 | Quay quanh trục $\hat n$ | thế năng chỉ phụ thuộc khoảng cách/góc bất biến quay quanh $\hat n$ | $L_{\hat n}$ | `[MEH, fact 7]` |
| 3 | Tịnh tiến thời gian | $\partial L/\partial t=0$ (không có ngoại lực biến thiên theo $t$, không ràng buộc biến thiên theo $t$) | $H$ (và $=T+V$ nếu scleronomic) | `[MEH, fact 8, method 6]` |
| 4 | Đối xứng hình học nguồn trường (cầu/trụ/phẳng) | mật độ điện tích/dòng bất biến dưới nhóm con $SO(3)$/$SO(2)$/tịnh tiến | dạng hàm của $\vec E,\vec B$ suy giảm bậc tự do (xem 4.4) | `[ELK, §3.2 Gaussi teoreem, §4.2 tsirkulatsiooniteoreem]` |
| 5 | Đối xứng gương/hoán vị mạch điện | mạch bất biến dưới một phép phản chiếu/hoán vị nút | các thế nút liên hợp bằng nhau | `[ELK, §1.4 Sümmeetria]` |

**Vì sao bảng này đầy đủ trên $\mathcal P_{\text{IPhO}}$ (không phải một khẳng định tuỳ tiện):** mọi $V$ trong chương trình IPhO chỉ phụ thuộc (i) khoảng cách từng cặp hạt, (ii) vị trí tuyệt đối qua một trường ngoài *đều* (hấp dẫn đều, điện trường đều). Loại (i) chỉ có đúng nhóm đối xứng $SE(3)$ (tịnh tiến + quay) là để lại bất biến — không có đối xứng liên tục nào khác khả dĩ với thế năng phụ thuộc khoảng cách (chứng minh: $|r_i-r_j|$ bất biến dưới chính xác nhóm các phép đẳng cự của $\mathbb R^3$, không hơn). Loại (ii) chỉ bất biến dưới tịnh tiến *trong mặt phẳng vuông góc với trường*. Vậy: **không có đối xứng "ẩn" nào khác có thể tồn tại** ngoài mục 1–3 của Bảng C đối với thư viện lực này — đây là một khẳng định có thể chứng minh, không phải phỏng đoán, và chính là điều biến trụ cột C từ "case-by-case vô hạn" ở Mệnh đề 0 thành "$G_k$ hữu hạn" trên $\mathcal P_{\text{IPhO}}$.

### 4.4 Mở rộng sang trường liên tục (Gauss/Ampère) — cùng một cơ chế đối xứng, chứng minh đầy đủ

`[MD]` chỉ định nghĩa trụ cột C cho hệ Lagrangian hữu hạn chiều, nhưng cùng triết lý áp dụng nguyên vẹn cho bài toán trường (E&M) — đây là phần whitepaper **bổ sung** để trụ cột C thực sự tổng quát trên toàn bộ chương trình IPhO (Cơ + Điện), không chỉ Cơ học.

> **Định lý C2 (Đối xứng nguồn $\Rightarrow$ đối xứng trường).** Cho mật độ điện tích $\rho$ đối xứng cầu: $\rho(Rx)=\rho(x)$ với mọi $R\in SO(3)$. Khi đó trường $\vec E(x)=\int \frac{x-x'}{4\pi\varepsilon_0|x-x'|^3}\rho(x')\,d^3x'$ thoả $\vec E(x)=E(|x|)\hat x$ với $E$ là một hàm vô hướng của $|x|$ duy nhất.

**Chứng minh.** *Bước 1 (đẳng biến).* Với $R\in SO(3)$ bất kỳ, đổi biến $x'=Ry$ trong tích phân ($|\det R|=1$, $R$ đẳng cự $\Rightarrow |Rx-Ry|=|x-y|$):
$$
\vec E(Rx)=\int \frac{Rx-x'}{4\pi\varepsilon_0|Rx-x'|^3}\rho(x')\,d^3x' = \int\frac{Rx-Ry}{4\pi\varepsilon_0|Rx-Ry|^3}\rho(Ry)\,d^3y = R\int\frac{x-y}{4\pi\varepsilon_0|x-y|^3}\rho(y)\,d^3y = R\,\vec E(x),
$$
dùng $R(x-y)=Rx-Ry$, $|R(x-y)|=|x-y|$, và $\rho(Ry)=\rho(y)$ (đối xứng cầu). Vậy $\vec E(Rx)=R\vec E(x)$ với mọi $R\in SO(3)$, mọi $x$.

*Bước 2 (hướng).* Cố định $x\ne 0$. Lấy $R$ bất kỳ trong nhóm con $SO(2)_x$ các phép quay quanh trục $Ox$ (thoả $Rx=x$). Bước 1 cho $\vec E(x)=\vec E(Rx)=R\vec E(x)$: $\vec E(x)$ là véc-tơ **bất động** dưới mọi phần tử của $SO(2)_x$. Véc-tơ duy nhất bất động dưới toàn bộ nhóm quay quanh một trục là véc-tơ song song trục đó (thành phần vuông góc trục, nếu khác 0, sẽ bị quay sang hướng khác — mâu thuẫn). Vậy $\vec E(x)\parallel \hat x$.

*Bước 3 (độ lớn chỉ phụ thuộc $r$).* Với $x,x'$ cùng bán kính ($|x|=|x'|$), luôn tồn tại $R\in SO(3)$: $Rx=x'$. Bước 1: $\vec E(x')=\vec E(Rx)=R\vec E(x)=R(E(x)\hat x)=E(x)\hat x'$ (vì $R\hat x=\hat x'$ theo cách chọn $R$). So với $\vec E(x')=E(x')\hat x'$: $E(x')=E(x)$. Vậy $E$ chỉ phụ thuộc $r=|x|$. $\blacksquare$

**Hệ quả tức thời — thuật toán Gauss chỉ là hệ quả của Định lý C2 + định lý Gauss-Ostrogradsky.** Vì $E_n=E(r)$ hằng trên mặt cầu $S_r$: $\oint_{S_r}\vec E\cdot d\vec S = E(r)\cdot 4\pi r^2 = Q_{\text{trong}}(r)/\varepsilon_0$. Kiểm chứng bằng số với `[ELK, ul. 72]` ($\rho$ đều, bán kính $R$): $Q_{\text{trong}}(r)=\rho\cdot\frac43\pi r^3$ ($r<R$) $\Rightarrow E(r)=\dfrac{\rho r}{3\varepsilon_0}$ — **khớp chính xác** đáp số đã cho: *"$E(r) = \rho r/(3\varepsilon_0)$ kui $r<R$"*. Cùng cơ chế áp dụng cho đối xứng trụ (`[ELK, §4.2]`, định lý Ampère) và đối xứng phẳng, chỉ thay $SO(3)$ bằng $SO(2)\times\mathbb R$ hoặc nhóm tịnh tiến 2 chiều tương ứng — thủ tục chứng minh giống hệt, chỉ đổi nhóm.

**Kết luận Phần 4.** Trụ cột C có một lõi **hoàn toàn tổng quát và chứng minh được** (Định lý C1, C2: kiểm tra bất biến là thuật toán), bọc quanh một danh sách phép thử **hữu hạn, liệt kê đầy đủ** trên thư viện lực IPhO (Bảng C). Đây là câu trả lời chặt chẽ, không case-by-case theo nghĩa mạnh, cho câu hỏi "phép biến đổi nào cho tích phân đầu" của `[MD]`.

---


## PHẦN 5 — TRỤ CỘT D: XẤP XỈ & THANG ĐO

### 5.1 Vì sao trụ cột D là trụ cột "dễ thuật toán hoá nhất"

Quan sát mấu chốt (được kiểm chứng bằng bằng chứng văn bản trực tiếp, không suy diễn): trái với trụ cột C (nơi phải *tìm* đối xứng), tham số bé $\varepsilon$ ở trụ cột D **hầu như luôn được đề bài cho tường minh** bằng ký hiệu $\ll$ hoặc $\gg$. Bằng chứng liệt kê trực tiếp từ hai tài liệu nguồn:

| Bài | Câu chữ tường minh trong đề | Nguồn |
|---|---|---|
| Tụ phẳng | "$d \ll R$" | `[ELK, ul. 52]` |
| Thấu kính electron | "$eU_0 \gg eE_1z_1, eE_2z_2$ và $a \ll z_1,z_2$" | `[ELK, ul. 74]` |
| Vật va chạm liên tục | "Assume that $g\tau \ll v$" | `[MEH, pr. 17]`, dùng bởi `[MEH, method 2]` |
| Mạch RC | so sánh $T$ với $RC$ | `[ELK, ul. 58]`, `[ELK, §2.4]` |
| Nêm nhẹ vs khối nặng | "very light and slippery material" | `[MEH, pr. 25]` |

Vì vậy **bước "nhận diện $\varepsilon$" phần lớn không phải bài toán vật lý — nó là bài toán đọc-hiểu đề bài** (một kỹ năng thuần tuý mà học sinh kỷ luật, cẩn thận hoàn toàn làm chủ được, không cần "trực giác vật lý"). Khi $\varepsilon$ không cho tường minh, ta có công cụ tổng quát sau để **suy ra nó bằng thuật toán thuần tuý**.

Rất nhiều bài IPhO **không có nghiệm dạng đóng chính xác** — thí sinh **buộc phải** nhận diện một tham số nhỏ ε và tuyến tính hóa. Đây là kỹ năng bị đánh giá thấp nhất nhưng lại là **điểm phân loại** giữa thí sinh đạt HCV và thí sinh chỉ đạt trung bình.

### 6.2. Kỹ thuật phân tích thứ nguyên nhanh (order-of-magnitude check)
Trước khi tin một kết quả trung gian, luôn tự hỏi: "Nếu tham số X → 0 hoặc X → ∞, kết quả có tiến về giới hạn vật lý hiển nhiên không?" — đây vừa là công cụ xấp xỉ (B6) vừa là công cụ kiểm tra ngược (B10).

### 5.2 Định lý D1 (Buckingham $\Pi$ — xác định số tham số không thứ nguyên một cách thuật toán)

> **Định lý D1 (Buckingham, 1914).** Nếu một hệ thức vật lý liên hệ $n$ đại lượng, và các đại lượng này được dựng từ $k$ thứ nguyên cơ bản độc lập (thường $k\le 3$: khối lượng $M$, chiều dài $L$, thời gian $T$), thì hệ thức đó **tương đương** với một hệ thức giữa $p=n-k$ nhóm không thứ nguyên độc lập $\Pi_1,\dots,\Pi_p$ dựng từ tích luỹ thừa của $n$ đại lượng ban đầu.

Đây là công cụ **thuần thuật toán**: lập ma trận số mũ thứ nguyên của $n$ đại lượng theo $k$ cơ sở, hạng của ma trận này cho $k$ thực, và không gian hạt nhân (kernel) của ma trận — tính bằng đại số tuyến tính — sinh ra chính xác các $\Pi_i$. Khi bài không cho $\varepsilon$ tường minh, $\varepsilon$ **bắt buộc** phải là một trong các $\Pi_i$ này (không thể là đại lượng có thứ nguyên, vì so sánh "bé/lớn" chỉ có nghĩa với số không thứ nguyên) — đây là một ràng buộc tổng quát mạnh, thu hẹp triệt để không gian tìm kiếm.

### 5.3 Định lý D2 (Khai triển tiệm cận theo bậc — thuật toán, cho trước $\varepsilon$)

> **Định lý D2.** Cho phương trình $F(x,\varepsilon)=0$ (đại số hoặc vi phân) với nghiệm $x_0$ khi $\varepsilon=0$ và $F$ khả vi đủ bậc theo $\varepsilon$ tại lân cận $x_0$. Đặt $x=x_0+\varepsilon x_1+\varepsilon^2x_2+\cdots$. Khai triển Taylor $F$ theo $\varepsilon$ và **gom theo từng bậc $\varepsilon^0,\varepsilon^1,\varepsilon^2,\dots$**, mỗi bậc cho một phương trình tuyến tính cho $x_k$ theo $x_0,\dots,x_{k-1}$ đã biết — giải tuần tự.

Đây chính xác là `[MEH, idea 20]` (chuỗi Taylor: $\sin\varphi\approx\varphi$, $\cos\varphi\approx1-\varphi^2/2,\dots$) và `[MEH, method 2]` (phương pháp nhiễu loạn: giải bậc 0 trước, dùng nó tính lực hiệu chỉnh bậc 1). Thủ tục **thuật toán tuyệt đối**, có thể tự động hoá bằng đại số máy tính (giải thích rõ vì sao không cần trực giác một khi $\varepsilon$ đã xác định).

### 5.4 Định lý D3 (So sánh thang thời gian tuyến tính hoá $\Leftrightarrow$ trị riêng)

Bài toán "so sánh $T$ với $\tau=RC$ (hay $L/R$)" (`[ELK, §2.4, §5.2]`) tổng quát hoá thành:

> **Mệnh đề.** Với hệ phương trình vi phân tuyến tính bậc nhất $\dot y = Ay$ ($A$ hằng), các "hằng số thời gian đặc trưng" chính xác là $\tau_i = -1/\operatorname{Re}(\lambda_i)$, với $\lambda_i$ là trị riêng của $A$. Việc *bài toán biến thiên "nhanh" hay "chậm" so với hệ* quy về so sánh chu kỳ ngoại lực $T$ với $\max_i \tau_i$.

Với mạch $RC$ đơn giản ($\dot U=-U/RC$), $A=(-1/RC)$, $\tau=RC$ — khớp `[ELK, §2.4]`. Đây là đại số tuyến tính thuần tuý (tìm trị riêng), thuật toán tổng quát tuyệt đối một khi hệ đã tuyến tính hoá — và việc tuyến tính hoá quanh trạng thái cân bằng chính là Định lý D2 ở bậc $\varepsilon^1$.

**Kết luận Phần 5.** Trụ cột D gần như hoàn toàn thuật toán hoá được: (i) $\varepsilon$ thường **cho sẵn** trong đề (khảo sát thực nghiệm văn bản ở Mục 5.1); (ii) khi không cho sẵn, Định lý D1 (Buckingham) thu hẹp không gian tìm kiếm về hữu hạn ứng viên; (iii) một khi có $\varepsilon$, khai triển (Định lý D2) và so sánh thang thời gian (Định lý D3) là thuật toán tuyệt đối.




---

## B8 — ĐIỀU KIỆN BIÊN & ĐIỀU KIỆN ĐẦU (nguồn thông tin "ẩn" thứ hai)

Ngoài từ khóa tường minh, đề bài **luôn** mang theo các điều kiện biên **ngầm định**, theo quy ước vật lý chuẩn. Đây là bảng tra cứu bắt buộc thuộc lòng:

| Tình huống | Điều kiện biên/đầu ngầm định |
|---|---|
| Thế tại vô cực (không có gì đặc biệt ở đó) | φ(∞) = 0 |
| Vật/khối bắt đầu **được thả ra**, "ban đầu đứng yên" | v(0) = 0; gia tốc ban đầu ∥ hợp lực ban đầu (idea 31) |
| "vừa mới…", "ngay sau khi", "tức thời" | Đại lượng có quán tính (vị trí, Q trên tụ, I qua cuộn, động lượng góc ngoài xung lực) **liên tục**; đại lượng không có quán tính (vận tốc khi có xung tức thời, dòng qua điện trở/tụ, U trên cuộn) có thể **nhảy bậc** |
| "sau một thời gian dài", "ổn định", "trạng thái dừng" | Đạo hàm theo t của mọi đại lượng chậm → 0 (dI/dt=0 trên cuộn, dU/dt=0 trên tụ, dv/dt=0 khi đạt vận tốc giới hạn) |
| Vật **tách khỏi** bề mặt / dây **chùng** | N = 0 hoặc T = 0 tại đó (bất đẳng thức chuyển thành đẳng thức biên — idea 40) |
| "…bắt đầu trượt", "trên bờ vực…" | \|F_masat\| = μN (dấu bằng, biên giữa tĩnh và động) |
| Ampe kế/Vôn kế lý tưởng | R→0 / R→∞ tương ứng (xem B3.4) |
| Vật dẫn nối đất | φ = 0 |
| Vật dẫn cô lập | Q = const (giá trị ban đầu hoặc 0 nếu "chưa tích điện") |
| Bề mặt chất lỏng tự do gần tường/áp suất khí quyển | p = p_khí quyển tại đó (Fact 30 — Bernoulli) |
| Cực đại/cực tiểu của 1 đại lượng theo thời gian | Đạo hàm theo t của đại lượng đó = 0 tại thời điểm đó (idea 44; với mạch: dI/dt=0 ⇒ U_cuộn=0 lúc I cực đại — jaotis 5.4) |





---

## B9 — GIẢI TOÁN



---

## B10 — KIỂM TRA NGƯỢC (Verification Protocol)

Không bao giờ nộp bài mà bỏ qua bước này — đây là bước tách biệt điểm 10 và điểm 7-8.

1. **Kiểm tra thứ nguyên** — mọi số hạng cộng với nhau phải cùng đơn vị.
2. **Kiểm tra giới hạn đặc biệt** (idea 37): cho tham số → 0 hoặc → ∞ hoặc → giá trị đối xứng đặc biệt, so với trực giác/công thức đã biết (ví dụ μ→0 phải cho lại kết quả "không ma sát"; ε→1 (chân không) phải cho lại kết quả tĩnh điện chân không — chính jaotis 3.10 của Elekter.pdf nhắc thẳng điều này).
3. **Kiểm tra dấu** — lực/mô-men/dòng điện có đúng chiều vật lý hợp lý không?
4. **Kiểm tra qua định luật bảo toàn độc lập** — nếu bạn dùng Newton để giải, thử thay số vào biểu thức năng lượng xem có bảo toàn không (hoặc ngược lại).
5. **Kiểm tra bậc tự do** — số phương trình đã dùng có đúng bằng f_eff không (Fact 18)? Nếu dư 1 phương trình mà vẫn ra nghiệm hợp lý — có khả năng bạn đã vô tình lặp một ràng buộc; nếu thiếu 1 phương trình mà "đoán" ra đáp số — có khả năng bài có nghiệm nhưng lời giải chưa chặt chẽ, thiếu lập luận cho điểm.

---








































