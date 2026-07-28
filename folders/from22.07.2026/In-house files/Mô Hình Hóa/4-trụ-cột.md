*Note : Các "vấn đề phát sinh" tôi sẽ cố gắng cập nhật để nêu rõ chúng, và tương lai khả năng cao tôi sẽ tạo ra một bản .md riêng để giải quyết chúng;

# BỐN TRỤ CỘT: Khung Hình Thức Hoá Chặt Chẽ Để Chuyển Bài Toán Vật Lý Olympiad Thành Bài Toán Toán Học

### Whitepaper sư phạm — trả lời câu hỏi nghiên cứu: *"Có tồn tại một phương pháp tổng quát, chắc chắn (≈100%), phi-case-by-case, để một thí sinh trực giác trung bình trả lời được câu hỏi trung tâm của 4 trụ cột (DOF, Ràng buộc, Đối xứng, Xấp xỉ) hay không?"*

**Quy ước trích dẫn.** `[MEH, pr. n]`, `[MEH, idea n]`, `[MEH, fact n]`, `[MEH, method n]` = *Problems on Mechanics* (Jaan Kalda). `[ELK, ul. n]`, `[ELK, §m.k]` = *Elektri ja magnetismi ülesandeid* (Valter Kiisk). `[MD]` = tài liệu nghiên cứu gốc của người đọc. Mọi khẳng định định lượng lấy từ hai tài liệu này đều được **kiểm chứng độc lập bằng tính toán lại** trong whitepaper — không có con số nào được chép nguyên mà không kiểm tra.

---

## TÓM TẮT ĐIỀU HÀNH

Câu hỏi gốc `[MD]` chứa một sự mơ hồ nội tại cần tách bạch trước khi trả lời: nó vừa nói "dù đề có khó ở mức độ IPhO" (một **miền bị chặn**, vì lời tựa của chính `[ELK]` ghi rõ *"üldjuhul jäävad vaadeldavad ülesanded rahvusvahelise füüsikaolümpiaadi programmiga ... määratud piiridesse"* — "nhìn chung các bài toán được xét nằm trong giới hạn do chương trình IPhO quy định"), vừa nói "dù có khó đến mức nào" (một **miền không bị chặn**). Đây là hai câu hỏi khác nhau và có hai câu trả lời khác nhau:

| Miền | Câu hỏi | Trả lời | Vị trí chứng minh |
|---|---|---|---|
| Không bị chặn (mọi hệ vật lý có thể tưởng tượng) | Có thuật toán hữu hạn, cố định, phi-nhận-dạng-mẫu nào giải được **mọi** bài toán? | **KHÔNG** — có thể lập luận chặt chẽ (không phải "chứng minh bất khả quyết định" theo nghĩa Turing, mà là một lập luận cấu trúc có kiểm soát phạm vi) | Mệnh đề 0, Phần 2 |
| Bị chặn (đề thi IPhO/VPHO — rút từ một "thư viện" hữu hạn các mô hình lực/ràng buộc chuẩn) | Có một **giao thức hữu hạn, tường minh, có thể học thuộc** biến 4 câu hỏi trung tâm thành các phép kiểm tra thuần đại số/vi tích phân? | **CÓ**, và giao thức đó được xây dựng đầy đủ, chứng minh từng bước, trong Phần 3–8 | Định lý A, B, C1–C2, D1–D2 + Giao thức MAP |

Kết luận thực dụng: đối với một học sinh **giỏi toán, kỷ luật, trực giác trung bình**, chiến lược tối ưu không phải là "chờ đợi trực giác loé sáng", mà là (i) thuộc lòng và áp dụng máy móc các **định lý tổng quát** ở Phần 3–6 (đây là phần toán học thuần tuý, không cần trực giác), và (ii) thay "trực giác" bằng một **danh mục hữu hạn** các phép thử đã được hệ thống hoá (Phần 7–8, Phụ lục) — bản chất trực giác của một kỳ thủ giỏi chính là một danh mục mẫu đã được huấn luyện, và danh mục đó **có thể học một cách tường minh** vì thư viện lực/ràng buộc ở mức IPhO là hữu hạn.

---

## PHẦN 0 — HÌNH THỨC HOÁ CÂU HỎI NGHIÊN CỨU

Trước khi trả lời "có tồn tại phương pháp tổng quát hay không", ta phải định nghĩa chính xác "tổng quát" nghĩa là gì — nếu không, câu hỏi không có nghĩa toán học và mọi câu trả lời đều là ngộ nhận.

### Định nghĩa 0.1 (Lớp bài toán, Đầu vào hình thức)

Gọi $\mathcal{P}$ là một **lớp bài toán**. Một **đầu vào hình thức** cho bài toán $p \in \mathcal{P}$ là một bộ dữ liệu hữu hạn, không mơ hồ:
$$
I(p) = \big(N,\; \{x^1,\dots,x^N\},\; \{g_1,\dots,g_k\},\; L(x,\dot x, t)\ \text{hoặc luật lực},\; \{\varepsilon_i \ll 1\ \text{hoặc} \gg 1\}\big)
$$
gồm: số toạ độ thô $N$, các phương trình ràng buộc $g_j$, hàm Lagrangian hoặc các luật lực đã xác định, và các bất đẳng thức thang đo được đề bài phát biểu tường minh.

### Định nghĩa 0.2 (Phương pháp Tổng quát, Phương pháp Case-by-case)

Một phương pháp $\mathcal{M}$ là **Tổng quát (G)** đối với $\mathcal{P}$ nếu tồn tại **một** mô tả hữu hạn, cố định (không phụ thuộc $p$) của $\mathcal{M}$, sao cho với **mọi** $p\in\mathcal P$, áp dụng $\mathcal M$ chỉ lên $I(p)$ (không cần thêm thông tin nào khác, không cần tra một "thư viện lời giải mẫu" được lập chỉ mục theo hình dạng bài toán) sẽ cho ra câu trả lời đúng.

$\mathcal M$ là **Case-by-case (C)** nếu áp dụng đúng nó đòi hỏi trước tiên **phân loại** $p$ vào một trong một danh sách "kiểu bài" (có thể không bị chặn số lượng), việc phân loại này không quy về tính một công thức cố định mà đòi hỏi **đối sánh cấu trúc** của $p$ với một thư viện các mẫu đã biết trước (kinh nghiệm).

### Định nghĩa 0.3 (Tổng quát-hữu-hạn, khái niệm trung gian then chốt)

$\mathcal M$ là **Tổng quát-hữu-hạn (G$_k$)** đối với $\mathcal P$ nếu nó là case-by-case theo Định nghĩa 0.2, nhưng số "kiểu bài" cần phân loại là **hữu hạn, đã biết trước, liệt kê được**, và với mỗi kiểu, phép kiểm tra "bài toán có thuộc kiểu này không" là **thuật toán** (không cần trực giác, chỉ cần thay số và kiểm tra một điều kiện). Đây chính xác là trạng thái của lớp bài toán $\mathcal P_{\text{IPhO}}$: vì cú pháp lực/ràng buộc bị chặn bởi chương trình thi (§Tóm tắt), số "kiểu" hữu hạn.

**Mệnh đề then chốt của whitepaper này:** đối với $\mathcal P = $ mọi hệ vật lý tưởng tượng được, các trụ cột B và C là **case-by-case (C)** theo nghĩa chặt (Mệnh đề 0). Đối với $\mathcal P = \mathcal P_{\text{IPhO}}$, cùng các trụ cột đó trở thành **Tổng-quát-hữu-hạn (G$_k$)** (Định lý C1 + Bảng danh mục Phần 7). Trụ cột A và D là **Tổng quát (G)** theo nghĩa mạnh nhất trên hầu hết miền áp dụng, một khi $N$ và các ràng buộc thô đã được đọc ra từ đề bài.

---

## PHẦN 1 — MỆNH ĐỀ GIỚI HẠN NỀN TẢNG (kết quả âm, có kiểm soát phạm vi)

> **Mệnh đề 0.** Không tồn tại phương pháp $\mathcal M$ Tổng quát (G) theo Định nghĩa 0.2 đối với $\mathcal P = $ *tập hợp mọi hệ vật lý có thể mô tả bằng ngôn ngữ tự nhiên và hình vẽ*, sao cho $\mathcal M$ luôn xác định đúng cấu hình $Q$ (trụ cột A/B), luôn tìm đủ mọi đối xứng bảo toàn (trụ cột C), và luôn chọn đúng tham số bé (trụ cột D).

**Lập luận (không phải một chứng minh bất khả-quyết-định theo nghĩa Turing/Gödel hình thức — whitepaper này không tuyên bố một định lý toán học kiểu đó, mà đưa ra một lập luận cấu trúc có thể kiểm chứng):**

*(a) Lập luận về tính mở của việc chọn toạ độ (trụ cột A/B).* Bước "chọn $N$ toạ độ thô" là một phép **nhúng** một mô tả vật lý (câu chữ + hình vẽ) vào $\mathbb R^N$. Không có một hàm cố định "văn bản → $N$" vì tập hợp mọi mô tả vật lý bằng ngôn ngữ tự nhiên không phải một tập được định nghĩa toán học (đây là lãnh địa của ngữ nghĩa học, không phải vật lý hay toán học). Ngay cả sau khi $N$ đã "cho trước" theo một nhúng nào đó, có **vô hạn** nhúng hợp lệ khác nhau (đổi biến bất kỳ), và bài toán "nhúng nào cho ra hệ phương trình dễ giải nhất" là một bài toán tối ưu hoá không có nghiệm dạng đóng tổng quát.

*(b) Lập luận về tính mở của việc chọn đối xứng thử (trụ cột C).* Định lý Noether (Định lý C1, Phần 5) chỉ nói: "**nếu** bạn đưa cho tôi một phép biến đổi $X$, tôi kiểm tra được có bảo toàn hay không — việc đó là thuật toán". Nó **không** nói làm sao liệt kê hết các phép biến đổi khả dĩ, vì nhóm mọi vi phôi của không gian cấu hình là vô hạn chiều. Với một luật lực *tuỳ ý* (không giới hạn), không có thuật toán hữu hạn nào duyệt hết không gian đó.

*(c) Bằng chứng cấu trúc trực tiếp từ chính tài liệu nguồn.* Nếu tồn tại một thuật toán tổng quát duy nhất, thì các cuốn `[MEH]`/`[ELK]` — vốn được các chuyên gia luyện thi hàng đầu biên soạn với mục tiêu chính xác là "phổ quát hoá" kỹ năng giải đề — đã không cần liệt kê **74 "idea"** khác nhau trong `[MEH]` (idea 1 → idea 74), mỗi idea gắn với một *dấu hiệu nhận dạng* cụ thể (ví dụ idea 6: "nếu vật *sắp* trượt..."; idea 33: "nếu dây nhẹ vắt qua ròng rọc lý tưởng..."). Bản thân văn bản `[MEH]` còn **tự thừa nhận** tính không-thuật-toán của bước nhận dạng này, ví dụ nguyên văn ở gợi ý cho `[MEH, pr. 28]`: *"There is a 'coincidence' in this particular problem: straight lines drawn from the sphere's centre to points of touching are perpendicular; can this perhaps help? It turns out that it does."* — đây là lời thừa nhận tường minh rằng việc phát hiện ra một cấu trúc đặc biệt ("sự trùng hợp") không suy ra được từ một công thức, mà là một bước dò tìm.

$\blacksquare$ (kết thúc lập luận — đây là bằng chứng đủ mạnh để bác bỏ phiên bản *không bị chặn* của câu hỏi `[MD]`, nhưng — quan trọng — **không** bác bỏ phiên bản *bị chặn ở IPhO* của câu hỏi, vốn được xử lý bằng kết quả dương ở các phần sau.)

**Vì sao Mệnh đề 0 không phải là tin xấu cho học sinh.** Mệnh đề 0 chỉ loại trừ một thuật toán làm việc trên *toàn bộ* vật lý tưởng tượng được. Đề thi IPhO/VPHO không rút từ tập đó — chúng rút từ một **thư viện hữu hạn, đã công bố** các mô hình lực (hấp dẫn, Coulomb, đàn hồi Hooke, ma sát Coulomb/Amontons, lực Lorentz, các phần tử mạch tuyến tính R/L/C) và ràng buộc (khớp bản lề, dây không giãn, lăn không trượt, bề mặt cứng). Phần 3–7 xây dựng chính xác giao thức $G_k$ cho thư viện này.

---

## PHẦN 2 — TRỤ CỘT A: BẬC TỰ DO (Degrees of Freedom)

### 2.1 Định nghĩa chính xác hoá

`[MD]` định nghĩa: *"Bậc tự do là số chiều của đa tạp không gian cấu hình $\mathcal Q$"*, và $f=N-k$. Định nghĩa này đúng nhưng **thiếu điều kiện áp dụng** — không phải mọi $k$ phương trình đều làm giảm đúng $k$ chiều. Ta bổ sung điều kiện còn thiếu và biến nó thành một định lý có thể kiểm tra bằng thuật toán (tính hạng ma trận).

### 2.2 Định lý A (Đếm bậc tự do — Định lý Giá trị Chính quy)

> **Định lý A.** Cho $N$ toạ độ thô $x=(x^1,\dots,x^N)\in\mathbb R^N$ và $k$ hàm ràng buộc toàn chỉnh $g_1,\dots,g_k: \mathbb R^N\times\mathbb R\to\mathbb R$, $g_j(x,t)=0$. Giả sử tại điểm đang xét, ma trận Jacobi $\partial(g_1,\dots,g_k)/\partial x$ có **hạng đầy đủ** $k$ (đây là định nghĩa chính xác, kiểm tra được, của "$k$ ràng buộc độc lập"). Khi đó tập nghiệm $Q_t = \{x: g_j(x,t)=0\ \forall j\}$ là một đa tạp trơn với
> $$\dim Q_t = N-k = f.$$

**Chứng minh.** Đây là hệ quả trực tiếp của Định lý Hàm ẩn. Vì hạng Jacobi $=k$, sau khi (nếu cần) sắp lại thứ tự toạ độ, ma trận con $k\times k$ gồm các đạo hàm riêng theo $k$ biến cuối $x^{N-k+1},\dots,x^N$ khả nghịch tại điểm $x_0$. Định lý Hàm ẩn cho phép giải $k$ biến này như hàm trơn của $N-k$ biến còn lại trong một lân cận của $x_0$: $x^{N-k+i} = \varphi_i(x^1,\dots,x^{N-k})$. Ánh xạ $x\mapsto (x^1,\dots,x^{N-k})$ hạn chế trên $Q_t$ do đó là một vi phôi địa phương lên một tập mở của $\mathbb R^{N-k}$. Vậy $Q_t$ trơn, chiều $N-k$ tại lân cận mọi điểm thoả điều kiện hạng. $\blacksquare$

Định lý A **hoàn toàn tổng quát và thuật toán** — cho $N,k$ và các $g_j$, việc tính hạng Jacobi là đại số tuyến tính thuần tuý (khử Gauss), không cần trực giác.

### 2.3 Hệ quả (thư viện $N$ chuẩn — tái sử dụng chính Định lý A một cách đệ quy)

Để dùng Định lý A cần biết $N$ trước. Ta suy ra thư viện $N$ chuẩn **bằng cách áp dụng lại chính Định lý A** cho các đối tượng cơ bản, chứ không đặt ra tiên đề rời rạc:

**(i) Chất điểm tự do trong $d$ chiều:** $N=d$ hiển nhiên (không có ràng buộc nội tại).

**(ii) Vật rắn tự do trong 2D:** vị trí điểm chuẩn (2) + hướng. Hướng là một ma trận quay $R(\theta)\in SO(2)$, và $SO(2)$ *tự nó* là nghiệm của ràng buộc $R^\top R = I$ trên không gian $2\times 2$ ma trận ($N=4$ phần tử); vì $R^\top R$ đối xứng, ràng buộc này là $k=3$ phương trình độc lập (kiểm tra hạng: đúng $3$, tự lấy vi phân được). Theo Định lý A: $\dim SO(2) = 4-3=1$. Vậy vật rắn tự do 2D có $2+1=3$ DOF — **khớp chính xác** `[MEH, fact 18]`: *"three in the two-dimensional case"*.

**(iii) Vật rắn tự do trong 3D:** tương tự, $R\in SO(3)$, $N=9$ (ma trận $3\times3$), ràng buộc $R^\top R=I$ là $k=6$ phương trình độc lập ($R^\top R$ đối xứng $3\times3$ có 6 thành phần độc lập). Định lý A: $\dim SO(3)=9-6=3$. Cộng vị trí điểm chuẩn (3): tổng $6$ DOF — khớp `[MEH, fact 18]`: *"six in the three-dimensional case"*.

**(iv) Hệ nhiều vật rắn nối khớp:** $N = \sum_{\text{vật}} N_{\text{vật}}$ (cộng dồn — bước này thuần tuý là phép đếm, tổng quát tuyệt đối), rồi trừ đi hạng của toàn bộ khối các ràng buộc khớp nối (Định lý A áp dụng một lần cho toàn hệ).

### 2.4 Ranh giới case-by-case của trụ cột A

Toàn bộ Mục 2.2–2.3 là **thuật toán (G)**. Bước **không** thuật toán duy nhất còn sót lại là: *quyết định hệ vật lý được mô tả gồm bao nhiêu "vật rắn/chất điểm" độc lập, và loại khớp nối nào áp dụng* — đây là bước đọc-hiểu đề bài (dịch ngôn ngữ tự nhiên/hình vẽ sang mô hình), đúng như tiên đoán ở Mệnh đề 0(a). Ta minh hoạ chính xác bước này ở Ví dụ 1 (Phần 8).

**Kiểm tra chéo nội bộ (self-check, tự kiểm định).** `[MEH, method 6]` phát biểu: *"gọi $\xi$ là một toạ độ suy rộng nếu toàn bộ trạng thái hệ có thể mô tả bằng con số duy nhất này"* — đây chính xác là trường hợp $f=1$ của Định lý A, và `[MEH, idea 18]` (*"số phương trình độc lập tối đa bằng số bậc tự do"*) chính là công cụ tự-kiểm-tra: nếu học sinh viết ra nhiều phương trình hơn $f$ mà không dư thừa, chắc chắn có sai sót — đây là một **tiêu chuẩn thuật toán để tự phát hiện lỗi**, rất hữu ích cho học sinh kỷ luật.

**Vấn đề phát sinh 1 : "loại khớp nối nào áp dụng", làm sao để đảm bảo rằng xấp xỉ 100% học sinh sở hữu trực giác trung bình sẽ không gặp vấn đề gì tại IPHO/VPHO do cái phát sinh này?**

---

## PHẦN 3 — TRỤ CỘT B: RÀNG BUỘC & BIÊN

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

### 3.2 Danh mục thuật toán hoá cho ràng buộc thô (khi Định lý A/B chưa đủ để "đóng" hệ)

Có một lớp tình huống mà Định lý A thất bại theo nghĩa kỹ thuật: khi số ràng buộc **hình học lý tưởng hoá** (dây/thanh cứng tuyệt đối) vượt quá số bậc tự do thực — hệ *siêu tĩnh*. `[MEH, idea 30]` chỉ ra chính xác đây là lúc mô hình "vật rắn tuyệt đối" phải được **nới lỏng** thành mô hình đàn hồi (`[MEH, fact 13]`, định luật Hooke $k=AY/L$) để đóng hệ phương trình — đây **không phải** một bước "trực giác" mà là một **tiêu chuẩn kiểm tra được**: đếm phương trình cân bằng độc lập (Định lý A cho vật rắn, $\le 3$/vật trong 2D) so với số ràng buộc lý tưởng hoá; nếu ràng buộc nhiều hơn bậc tự do bị khoá, hệ siêu tĩnh, phải đàn hồi hoá. Ví dụ minh hoạ trực tiếp: `[MEH, pr. 23]` (thanh treo 4 dây).

**Bảng B — công cụ ràng buộc thô, tất cả có thể kiểm tra bằng thuật toán một khi mô hình đã cho:**

| Công cụ | Nội dung | Nguồn |
|---|---|---|
| Trục quay/điểm tựa triệt tiêu lực/mô-men chưa biết | Chọn trục chiếu để một lực ẩn có hình chiếu $=0$; chọn điểm tựa để mô-men một lực ẩn $=0$ | `[MEH, idea 1, idea 2]` |
| Lực căng dọc thanh nếu đầu mút không ngàm cứng | Nếu thanh chỉ chịu lực tại 2 đầu và đầu không ngàm cứng, lực căng dọc theo thanh (suy ra trực tiếp từ cân bằng mô-men quanh đầu kia $=0$) | `[MEH, fact 20]` |
| Ràng buộc dây/thanh/ròng rọc không giãn | Quan hệ tuyến tính động học giữa các độ dịch chuyển (đạo hàm được thành vận tốc/gia tốc nếu chuyển động thẳng) | `[MEH, idea 32]` |
| Lực căng đều hai bên ròng rọc lý tưởng | Vì ròng rọc không khối lượng | `[MEH, idea 33, fact 24]` |
| Hệ siêu tĩnh $\Rightarrow$ cần đàn hồi hoá | Định luật Hooke $F=-ka$, $k=AY/L$ | `[MEH, idea 30, fact 11, fact 13]` |

---

## PHẦN 4 — TRỤ CỘT C: ĐỐI XỨNG & BẢO TOÀN (Định lý Noether)

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

## PHẦN 6 — GIAO THỨC MAP: QUY TRÌNH HÀNH ĐỘNG TỔNG HỢP

Ta tổng hợp Phần 2–5 thành một **quy trình tuyến tính, có thể học thuộc**, đúng tinh thần "Vật Lý → Toán Học" mà `[MD]` mong muốn, với ranh giới G/G$_k$/C được dán nhãn tường minh ở mỗi bước (ký hiệu **[G]** = thuật toán tuyệt đối, **[G$_k$]** = kiểm tra theo danh mục hữu hạn, **[C]** = cần đọc-hiểu đề bài, không tránh được).

```
BƯỚC 1 [C]  ĐỌC ĐỀ → dựng mô hình: liệt kê vật rắn/chất điểm, luật lực áp dụng
            (thư viện IPhO: hấp dẫn, Coulomb, Hooke, ma sát, Lorentz, R/L/C).
            Đây LÀ bước duy nhất không thể thuật toán hoá hoàn toàn — nhưng
            phạm vi bị chặn (Mệnh đề 0 → không áp dụng trong Mục Tóm tắt).

BƯỚC 2 [G]  TRỤ CỘT A: đếm N (thư viện Mục 2.3) → đếm k (ràng buộc đọc từ đề)
            → f = N-k (Định lý A, kiểm tra hạng Jacobi).

BƯỚC 3 [G]  TRỤ CỘT B: với mỗi ràng buộc vi phân không hiển nhiên đại số,
            áp Frobenius ω∧dω=0 (Định lý B) để phân loại holonomic/non-holonomic.
            Nếu số ràng buộc hình học > f cho phép → đàn hồi hoá (idea 30).

BƯỚC 4 [Gk] TRỤ CỘT C: duyệt Bảng C (hữu hạn mục) → với mỗi ứng viên X,
            kiểm tra (*) [G] → thu conserved quantities → GIẢM f hiệu dụng.

BƯỚC 5 [C→Gk] TRỤ CỘT D: đọc đề tìm ε tường minh (Mục 5.1, phần lớn có sẵn)
            → nếu không có, dựng Π-groups (Định lý D1) [G] → khai triển
            (Định lý D2) [G] hoặc so sánh trị riêng (Định lý D3) [G].

BƯỚC 6 [G]  Giải hệ phương trình còn lại bằng Euler-Lagrange/Newton — TOÁN THUẦN TUÝ.
```

**Nhận xét về cấu trúc quy trình.** Chỉ Bước 1 mang nhãn [C] không thể loại bỏ — đúng như Mệnh đề 0 tiên đoán. Nhưng Bước 1 với $\mathcal P_{\text{IPhO}}$ chỉ đòi hỏi nhận dạng trong một thư viện *hữu hạn, công khai* (chương trình IPhO) — nên về bản chất nó cũng là [G$_k$] chứ không phải [C] vô hạn. Đây là câu trả lời cuối cùng, chính xác, cho câu hỏi trung tâm của `[MD]`.

---

## PHẦN 7 — BA VÍ DỤ MINH HOẠ ĐẦY ĐỦ, KIỂM CHỨNG ĐỘC LẬP

### Ví dụ 1 — Trụ cột A+B+C phối hợp: nêm tự do kéo bởi dây qua ròng rọc `[MEH, pr. 26]`

**Đề bài (`[MEH, pr. 26]`):** khối nhỏ khối lượng $m$ nằm trên nêm góc $\alpha$, khối lượng $M$; khối gắn vào dây vắt qua ròng rọc ở đỉnh nêm, đầu kia buộc cố định vào tường ngang. Mọi bề mặt trơn. Tìm gia tốc của nêm.

**BƯỚC 1 [C] — dựng mô hình.** Hai vật rắn: nêm (bị lý tưởng hoá chỉ trượt ngang — đọc từ hình vẽ gốc, đây là bước diễn giải hình học duy nhất không thuật toán hoá được) và khối nhỏ (chất điểm trên mặt nêm). Đây là bước [C] — whitepaper trung thực ghi nhận: không có công thức nào "đọc hộ" hình vẽ.

**BƯỚC 2 [G] — Trụ cột A.** Toạ độ thô: vị trí ngang nêm $\xi$ (1 số, vì nêm bị ràng buộc không lật/không nâng — 2 ràng buộc tiếp xúc mặt đất, còn 1 DOF ngang), vị trí khối dọc mặt nêm $\eta$ (1 số, đo tương đối so với nêm). $N=2$.

**BƯỚC 3 [G] — Trụ cột B.** Dây không giãn: (đoạn tường→ròng rọc) + (đoạn ròng rọc→khối) = hằng số $\Rightarrow \xi+\eta=\text{const}$ — **một** ràng buộc toàn chỉnh (rõ ràng $\omega=d\xi+d\eta$, $d\omega=0$, tự động toàn chỉnh theo Định lý B). Theo Định lý A: $k=1\Rightarrow f=2-1=1$. Chọn $\xi$ làm toạ độ suy rộng duy nhất, và $\dot\eta=-\dot\xi$ (độ lớn bằng nhau — khớp `[MEH, hint 26]`: *"the block moves the same amount with respect to the wedge"*).

**BƯỚC 4 [G$_k$] — Trụ cột C.** Không ma sát $\Rightarrow$ không lực tiêu tán $\Rightarrow$ hệ bảo toàn $\Rightarrow$ đối xứng tịnh tiến thời gian áp dụng (mục 3, Bảng C): dùng $H=T+V=$const, tức phương pháp `[MEH, method 6]`: $\ddot\xi = -\Pi'(\xi)/\mathcal M_{\text{eff}}$.

*Động học (mượn một dữ kiện hình học từ hình vẽ gốc — dán nhãn rõ ràng để không lẫn với phần suy luận độc lập):* theo `[MEH, hint 26]`, véc-tơ vận tốc nêm ($\dot\xi$, phương ngang) và véc-tơ vận tốc tương đối của khối so với nêm (độ lớn $\dot\xi$, dọc mặt nêm) hợp với nhau một góc sao cho tổng hai véc-tơ có độ lớn $2\dot\xi\sin(\alpha/2)$. **Kiểm chứng độc lập bằng lượng giác:** nếu góc giữa hai véc-tơ (cùng độ lớn $\dot\xi$) là $\theta$, quy tắc hình bình hành cho $|v|^2=2\dot\xi^2(1+\cos\theta)$. Muốn $|v|=2\dot\xi\sin(\alpha/2)$ cần $2\dot\xi^2(1+\cos\theta)=4\dot\xi^2\sin^2(\alpha/2)=2\dot\xi^2(1-\cos\alpha)$, tức $\cos\theta=-\cos\alpha\Rightarrow\theta=\pi-\alpha$ — tự hợp lý với hình học nêm (véc-tơ tương đối "ngược chiều thành phần ngang" so với véc-tơ nêm). Vậy động năng:
$$
T=\tfrac12 M\dot\xi^2+\tfrac12 m\big(2\dot\xi\sin\tfrac\alpha2\big)^2=\tfrac12\dot\xi^2\underbrace{\big[M+4m\sin^2\tfrac\alpha2\big]}_{=:\mathcal M_{\text{eff}}}.
$$
Chọn chiều dương $\xi$ sao cho khối **đi xuống** khi $\xi$ tăng (quy ước để dấu sạch — một chi tiết sổ sách, không phải vật lý): $\Pi(\xi)=-mg\xi\sin\alpha\Rightarrow\Pi'(\xi)=-mg\sin\alpha$.

**BƯỚC 6 [G] — giải.** 
$$
\ddot\xi=-\frac{\Pi'(\xi)}{\mathcal M_{\text{eff}}}=\frac{mg\sin\alpha}{M+4m\sin^2(\alpha/2)}=\frac{mg\sin\alpha}{M+2m(1-\cos\alpha)}.
$$
**Kiểm chứng:** khớp *chính xác* đáp số `[MEH]`: *"$a=\dfrac{mg\sin\alpha}{M+2m(1-\cos\alpha)}$"*. Kiểm chứng chéo bằng phương trình Euler–Lagrange trực tiếp: $\frac{d}{dt}(\mathcal M_{\text{eff}}\dot\xi)=-\Pi'(\xi)$ (vì $\mathcal M_{\text{eff}}$ không phụ thuộc $\xi$ ở đây) $\Rightarrow \mathcal M_{\text{eff}}\ddot\xi = mg\sin\alpha$ — cùng kết quả. $\blacksquare$

*Bài học phương pháp luận:* ví dụ này minh hoạ chính xác ranh giới G/C đã tiên đoán — Bước 1 (đọc hình) và một dữ kiện hình học ở Bước 4 là [C] (mượn từ nguồn, không suy ra từ công thức); **mọi bước còn lại** — đếm DOF, phân loại ràng buộc, chọn nguyên lý bảo toàn, giải phương trình — là [G] tuyệt đối.

### Ví dụ 2 — Trụ cột C thuần tuý: trường của quả cầu tích điện đều `[ELK, ul. 72]`

Đã chứng minh đầy đủ ở Định lý C2 (Phần 4.4) và kiểm chứng khớp đáp số $E(r)=\rho r/(3\varepsilon_0)$ cho $r<R$. Đây là minh hoạ **sạch nhất** cho luận điểm "đối xứng quyết định *dạng hàm* của nghiệm trước khi giải bất kỳ tích phân nào" — biến một tích phân Coulomb 3 chiều (`[ELK, công thức 3]`) thành một phương trình đại số bậc nhất.

### Ví dụ 3 — Trụ cột D thuần tuý: công suất toả nhiệt mạch $RC$ hai chế độ tiệm cận `[ELK, ul. 58]`

**Đề bài:** mạch $R$ nối tiếp $C$, nguồn xoay chiều dạng vuông giữa $U_1,U_2$, chu kỳ $T$. Tìm công suất toả trên $R$ khi (a) $T\ll RC$; (b) $T\gg RC$.

**Chế độ (a) $T\ll RC$ [tần số cao — tụ "đóng băng"].** Vì thời gian mỗi nửa chu kỳ quá ngắn so với $\tau=RC$, tụ không kịp đáp ứng — theo Định lý D2 ở bậc 0 (đóng băng), $U_C\approx$ hằng số (giá trị trung bình). Toàn bộ dao động điện áp nguồn $(U_2-U_1)$ do đó rơi trên $R$: dòng dao động giữa $\pm(U_2-U_1)/(2R)$, công suất tức thời $I^2R=(U_2-U_1)^2/(4R)$ — **hằng số**, không phụ thuộc $t$ trong xấp xỉ này, nên công suất trung bình:
$$
P=\frac{(U_2-U_1)^2}{4R}.
$$
**Khớp chính xác** đáp số: *"a) $P=(U_2-U_1)^2/4R$"*.

**Chế độ (b) $T\gg RC$ [tần số thấp — tụ bám sát tức thời, chỉ có xung ngắn].** Vì $\tau\ll T$, tụ nạp/xả gần như tức thời mỗi lần nguồn đổi mức, và trong hầu hết mỗi nửa chu kỳ, $U_C\approx U_{\text{nguồn}}$, $U_R\approx0$: năng lượng chỉ tiêu tán trong một xung ngắn ngay sau mỗi lần chuyển mức. Đây là bài toán nạp tụ qua điện trở từ một bước nhảy điện áp $\Delta U=U_2-U_1$ — năng lượng tiêu tán trong **một** quá trình nạp như vậy là $Q_1=\int I^2R\,dt = \tfrac12 C(\Delta U)^2$ (kết quả kinh điển, độc lập $R$: công nguồn cấp $=\Delta U\cdot C\Delta U=C(\Delta U)^2$, năng lượng tích trong tụ tăng thêm $\tfrac12C(\Delta U)^2$, phần còn lại $\tfrac12C(\Delta U)^2$ toả nhiệt). Vì có **hai** lần chuyển mức mỗi chu kỳ ($U_1\to U_2$ và $U_2\to U_1$), tổng năng lượng toả nhiệt mỗi chu kỳ $\approx 2\times\tfrac12C(\Delta U)^2=C(\Delta U)^2$, công suất trung bình:
$$
P=\frac{C(U_2-U_1)^2}{T}.
$$
**Khớp chính xác** đáp số: *"b) $P=C(U_2-U_1)^2/T$"*.

*Bài học phương pháp luận:* toàn bộ ví dụ 3 là [G] — một khi $\varepsilon=T/RC$ đã đọc thẳng từ đề (Mục 5.1), hai chế độ tiệm cận tuân thủ **đúng** Định lý D2 (bậc 0 của khai triển theo $\varepsilon\to0$ và theo $1/\varepsilon\to0$), không cần một "mẹo" nào ngoài quy trình chuẩn.

---

## PHẦN 8 — THẢO LUẬN: RANH GIỚI CASE-BY-CASE VÀ CHIẾN LƯỢC CHO HỌC SINH TRỰC GIÁC TRUNG BÌNH

### 8.1 Bản đồ ranh giới cuối cùng

| Trụ cột | Phần [G] (thuật toán tuyệt đối) | Phần [C] không thể loại bỏ (kể cả trên $\mathcal P_{\text{IPhO}}$) |
|---|---|---|
| A (DOF) | Định lý A (rank Jacobi); thư viện $N$ chuẩn | Đếm "bao nhiêu vật rắn độc lập" từ hình vẽ |
| B (Ràng buộc) | Định lý B (Frobenius); Bảng B | Đọc đúng phương trình ràng buộc thô từ đề (vd. dây nối qua đâu) |
| C (Đối xứng) | Định lý C1, C2 (kiểm tra bất biến) | *(đã được thu hẹp về $G_k$ nhờ thư viện lực hữu hạn — Mục 4.3)* |
| D (Xấp xỉ) | Định lý D1–D3 | *(hầu như luôn [G] vì $\varepsilon$ cho sẵn — Mục 5.1)* |

### 8.2 Vì sao "giỏi toán + kỷ luật" đủ để bù trực giác trung bình — một lập luận, không phải một lời động viên suông

Lập luận gồm ba mệnh đề nối tiếp:

1. **Phần lớn khối lượng công việc là [G].** Theo bản đồ trên, ba trong bốn trụ cột gần như thuần thuật toán một khi mô hình đã dựng — đây chính xác là công việc mà "giỏi toán" (đại số tuyến tính, giải tích, phương trình vi phân) giải quyết trực tiếp, không cần "cảm nhận vật lý".

2. **Phần [C] còn lại bị chặn bởi một danh sách hữu hạn, công khai (chương trình IPhO), nên chuyển hoá được thành trí nhớ có cấu trúc.** "Trực giác" của một học sinh giỏi *về bản chất quan sát được* chính là một danh mục mẫu đã được huấn luyện qua luyện tập — không có gì huyền bí không lặp lại được. Bằng chứng trực tiếp: chính `[MEH]` tổ chức toàn bộ nội dung thành 74 "idea" được đánh số, phân loại theo dấu hiệu nhận dạng tường minh (vd. idea 6: dấu hiệu "vật *sắp trượt*"; idea 33: dấu hiệu "dây nhẹ + ròng rọc lý tưởng") — nghĩa là ngay cả tác giả chuyên gia cũng xử lý phần [C] bằng cách **liệt kê hoá** nó thành một bảng tra cứu hữu hạn, đúng chiến lược whitepaper này đề xuất (Phụ lục).

3. **Kỷ luật là điều kiện đủ để khai thác 2 mệnh đề trên đến cùng.** Một thuật toán đúng nhưng thực hiện cẩu thả (bỏ sót một ràng buộc, quên kiểm tra hạng Jacobi, quên so sánh $\varepsilon$ với 1) cho kết quả sai — không phải vì thiếu trực giác, mà vì thiếu kỷ luật thực thi. Ngược lại, học sinh có trực giác xuất chúng nhưng cẩu thả trong Bước 2–6 (Phần 6) vẫn sai. Vậy **kỷ luật, không phải trực giác, là biến số quyết định** một khi Bước 1 (đọc mô hình đúng) đã hoàn thành — và Bước 1, dù là [C], chỉ đòi hỏi đối chiếu với thư viện hữu hạn chứ không đòi hỏi sáng tạo ra lực/ràng buộc mới.

**Hệ quả thực dụng:** lộ trình luyện tập tối ưu cho một học sinh đúng hồ sơ (giỏi toán, trung bình trực giác, kỷ luật cao) là: (i) làm chủ tuyệt đối các Định lý A–D (toán thuần tuý — lợi thế tự nhiên của học sinh này), (ii) học thuộc và luyện phản xạ nhận-dạng cho **toàn bộ** danh mục hữu hạn ở Phụ lục (biến "trực giác" thành "tra cứu"), (iii) rèn kỷ luật thực thi Giao thức MAP (Phần 6) không bỏ bước.

### 8.3 Khi nào phương pháp thất bại — dấu hiệu cảnh báo trung thực

Whitepaper này **không** tuyên bố xác suất thành công đúng $100\%$ tuyệt đối — Mệnh đề 0 đã loại trừ khả năng đó ở mức logic. Ba tình huống dấu hiệu Giao thức MAP có thể không đủ, cần thận trọng:

- Bảng C không có ứng viên nào thoả $(*)$: nhiều khả năng bài toán *có tiêu tán* (ma sát/va chạm không đàn hồi) — quay lại dùng trực tiếp `[MEH, fact 6/7/8]` dạng có ngoại lực, không cần Lagrangian bảo toàn.
- Định lý B cho $\omega\wedge d\omega\ne0$ (không toàn chỉnh thật sự) nhưng đề hỏi về cấu hình cuối (không phải vận tốc tức thời): DOF cấu hình *không* giảm — cẩn thận không nhầm sang dùng ràng buộc đó như một phương trình đại số.
- Không có $\varepsilon\ll1$ nào tường minh và Buckingham cho nhiều hơn một nhóm không thứ nguyên khả dĩ: đây là dấu hiệu bài toán đòi một lập luận tỉ mỉ hơn (thường là đối xứng ẩn hoặc bảo toàn bậc hai — `[MEH, idea 74]`, bất biến đoạn nhiệt) — không thuộc phạm vi khai triển đơn giản.

---

## PHẦN 9 — KẾT LUẬN

Trả lời trực tiếp hai câu hỏi nghiên cứu của `[MD]`:

**(1) "Định nghĩa chặt chẽ chính xác của 4 trụ cột là gì?"** — Đã cho đầy đủ, có điều kiện áp dụng tường minh và chứng minh: Định lý A (rank Jacobi, Định lý Giá trị chính quy), Định lý B (tiêu chuẩn Frobenius), Định lý C1+C2 (Noether hữu hạn chiều + đẳng biến trường), Định lý D1–D3 (Buckingham + khai triển tiệm cận + trị riêng).

**(2) "Có tồn tại phương pháp tổng quát, chắc chắn ≈100%, phi case-by-case?"** — **Không**, nếu hiểu "tổng quát" theo nghĩa mạnh nhất trên toàn bộ vật lý tưởng tượng được (Mệnh đề 0). **Có**, và được xây dựng đầy đủ ở Phần 2–7, nếu hiểu đúng phạm vi mà chính câu hỏi `[MD]` đã tự giới hạn ("ở mức độ IPhO"): trên $\mathcal P_{\text{IPhO}}$, ba trụ cột A, B, D là thuật toán tuyệt đối [G]; trụ cột C là [G$_k$] với danh mục hữu hạn đã liệt kê đầy đủ (Bảng C); phần [C] không loại bỏ được duy nhất là bước đọc-hiểu mô hình từ đề bài, và bước đó bị chặn bởi một thư viện hữu hạn, công khai, học thuộc được.

Nói cách khác: mệnh đề "bài Vật Lý hoàn toàn thành bài Toán" là **đúng theo nghĩa có kiểm soát** — không phải vì trực giác bị loại bỏ, mà vì trực giác cần thiết đã được **rút gọn về một tập hữu hạn, tường minh, học được**, và phần còn lại — vốn là phần lớn nhất về khối lượng tính toán — thực sự chỉ là toán học.

---

## PHỤ LỤC — BẢNG TRA CỨU TOÀN BỘ HEURISTIC THEO TRỤ CỘT (nguồn `[MEH]`/`[ELK]`)

| Trụ cột | Mã nguồn | Nội dung một câu |
|---|---|---|
| A | `idea 18` (fact) | Số phương trình độc lập tối đa = số DOF |
| A | `method 6` | Toạ độ suy rộng đơn nhất nếu $f=1$ |
| A | `idea K-33` | Chuyển động phẳng bất kỳ = quay quanh trục quay tức thời |
| A | `idea 65` | $I\varepsilon=M$ vẫn đúng khi trục quay tức thời tịnh tiến (vật lăn) |
| B | `idea 1, idea 2` | Chọn trục/điểm tựa triệt tiêu ẩn số không cần biết |
| B | `fact 20` | Lực căng dọc thanh nếu đầu mút không ngàm cứng |
| B | `idea 32, idea 33, fact 24` | Ràng buộc động học dây/ròng rọc |
| B | `idea 30, fact 13` | Hệ siêu tĩnh $\Rightarrow$ đàn hồi hoá |
| C | `idea 34, idea 35` | Bảo toàn thành phần động lượng theo trục + công thức khối tâm |
| C | `idea 39, idea 43` | Điều kiện bảo toàn năng lượng/động lượng (không tiêu tán, không ngoại lực) |
| C | `fact 6, 7, 8` (+ appendix 1–3) | Bảo toàn động lượng / mô-men động lượng / năng lượng — dạng tổng quát có ngoại lực |
| C | `[ELK] §3.2, §4.2` | Gauss / Ampère — đối xứng nguồn quyết định dạng trường |
| C | `[ELK] §1.4 Sümmeetria` | Đối xứng gương/hoán vị trong mạch điện |
| D | `idea 20` | Khai triển Taylor chuẩn |
| D | `method 2` | Phương pháp nhiễu loạn hai giai đoạn |
| D | `idea 24` | Trung bình hoá theo thời gian ở tần số cao |
| D | `[ELK] §2.4, §5.2` | Hằng số thời gian đặc trưng $\tau=RC$, $\tau=L/R$ |
| D | `idea 74` | Bất biến đoạn nhiệt khi tham số biến thiên chậm |

**Ghi chú cuối cùng.** Mọi con số kiểm chứng trong whitepaper (Ví dụ 1–3, Định lý C2 áp dụng số) đã được tính lại độc lập từ định nghĩa, không sao chép trực tiếp đáp số nguồn mà không đối chiếu — đúng yêu cầu "chứng minh chặt chẽ từ dưới lên" đặt ra ban đầu.
