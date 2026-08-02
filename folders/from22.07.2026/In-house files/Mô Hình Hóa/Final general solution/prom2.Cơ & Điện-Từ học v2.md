Lưu ý quan trọng : Tôi giả định rằng ta đã học và đã làm nhiều bài tập và đọc nhiều lý thuyết (Toán lẫn Vật Lý) để ta có dày dặn kinh nghiệm, pattern, case-by-case từ trước. Những gì tôi ghi ở bên dưới thường chỉ liên quan đến những gì thực sự tổng quát hoặc cực kỳ phổ biến.

# CÁCH GIẢI TỔNG QUÁT: CƠ HỌC & ĐIỆN–TỪ HỌC
### (Bản hoàn chỉnh — v3.0 — dùng cho ôn luyện IPhO / VPhO / Đội tuyển HSG Vật Lý THPT TP.HCM 2027–2028)

> **Ghi chú phạm vi:** Tài liệu này áp dụng cho hai mảng **Cơ học** và **Điện–Từ học** (bao gồm cả **mạch điện**, phần mà tài liệu gốc *Elekter.pdf* — viết tắt `[ELK]` — không trình bày đầy đủ, nay được bổ sung trọn vẹn ở **Phần 6**). Tài liệu tham chiếu:
> - `[MEH]` = *Problems on Mechanics* (Jaan Kalda, phần *meh_ENG2.pdf*)
> - `[ELK]` = *Elektri ja magnetismi ülesandeid* (Valter Kiisk, *Elekter.pdf*)
> - `[MD]` = bản nháp *framework.md* gốc mà tài liệu này hoàn thiện

**Giả định nền:** người đọc đã có một lượng kiến thức và bài tập nhất định (đã "dày dặn" ở mức làm quen). Tài liệu **không** nhắc lại lý thuyết vật lý cơ bản, mà tập trung **duy nhất** vào phần có tính **tổng quát** — tức là phần **không đổi** dù người ra đề có đổi cách hỏi thế nào.

---

## PHẦN 0 — TRIẾT LÝ NỀN: VÌ SAO MỘT "THUẬT TOÁN TỔNG QUÁT" LÀ KHẢ THI

### 0.1 Quan sát gốc, phát biểu lại chặt chẽ

> *"Người ra đề có thể đổi cách hỏi, nhưng không thể đổi luật của Vũ trụ."*

Phát biểu lại dưới dạng có thể dùng làm nền tảng suy luận:

- **Luật của Vũ trụ** = một tập **hữu hạn** các tiên đề (Newton I–III, bảo toàn năng lượng/động lượng/mô-men động lượng, phương trình Maxwell ở mức tĩnh/chuẩn tĩnh: Coulomb, Biot–Savart, Faraday, các định luật vật liệu Ohm/Hooke). `[MEH]` liệt kê chính xác các "fact" này (fact 1–17); `[ELK]` liệt kê tương ứng cho điện từ.
- **Cách hỏi** = việc chọn: (i) đại lượng nào cho biết, đại lượng nào ẩn; (ii) hình học/cấu hình cụ thể; (iii) ngôn từ diễn đạt (có thể "giấu" từ khóa quen thuộc bằng cách diễn đạt khác).
- Vì (i)+(ii)+(iii) là **hữu hạn về loại** (dù vô hạn về biến thể cụ thể) trên phạm vi chương trình thi $\mathcal P_{\text{IPhO}}$ (Cơ + Điện từ ở trình độ đề cương IPhO, xem *IPHO Syllabus*), nên **con đường từ đề bài đến hệ phương trình toán học thuần túy cũng phải hữu hạn về loại** — đây chính là nội dung có thể **thuật toán hoá**.

### 0.2 Định nghĩa "Tổng quát" dùng xuyên suốt tài liệu

Để tránh mơ hồ, ta phân biệt 3 mức:

| Ký hiệu | Nghĩa | Ví dụ trong tài liệu |
|---|---|---|
| **G** (General) | Đúng cho **mọi** trường hợp, chứng minh được bằng suy diễn toán học thuần túy, không cần liệt kê | Định lý A (đếm DOF), Định lý B (Frobenius), Định lý C1/C2 (Noether), Định lý D1–D3 |
| **$G_k$** (Tổng-quát-hữu-hạn) | Không đúng cho *mọi* hệ vật lý trừu tượng, nhưng đúng cho **mọi** hệ nằm trong thư viện lực/ràng buộc **hữu hạn** của $\mathcal P_{\text{IPhO}}$ — và thư viện này **liệt kê được trọn vẹn** | Bảng C (đối xứng khả dĩ), thư viện khớp nối B2, Từ điển B3, cây quyết định B7 |
| Case-by-case (bị cấm dùng làm nền tảng) | Chỉ đúng cho 1 bài cụ thể, không tổng quát hoá được | — (tài liệu **không** chứa loại này ở tầng phương pháp, chỉ ở tầng **ví dụ minh hoạ**) |

**Mục tiêu của toàn bộ tài liệu:** biến **mọi** bước mô hình hoá (từ đề bài → hệ phương trình) thành **G** hoặc **$G_k$**. Không có bước nào trong quy trình B0–B10 được phép chỉ là "kinh nghiệm cảm tính" — mỗi bước phải có (a) một **thủ tục kiểm tra được bằng tay**, và (b) một **danh sách hữu hạn các khả năng cần thử** nếu không thể suy ra trực tiếp.

### 0.3 Sơ đồ tổng thể của lời giải hoàn chỉnh

$$
\underbrace{\text{Đề bài (ngôn ngữ tự nhiên + hình)}}_{\text{B0}} \;\xrightarrow{\ \text{B1–B5}\ }\; \underbrace{\big(Q,\ q_1,\dots,q_f,\ L\ \text{hoặc}\ F\big)}_{\text{Mô hình toán học}} \;\xrightarrow{\ \text{B6–B7}\ }\; \underbrace{\text{Phương pháp chi phối}}_{\text{ngôn ngữ giải}} \;\xrightarrow{\ \text{B8–B9}\ }\; \underbrace{\text{Nghiệm số/công thức}}_{} \;\xrightarrow{\ \text{B10}\ }\; \text{Đáp số đã kiểm chứng}
$$

Đây chính là "Mô Hình Hóa": biến một tình huống vật lý thành **bộ ba** $(Q, q_i, L\text{ hoặc }F)$ — không gian cấu hình, tọa độ suy rộng, và hàm chi phối (Lagrangian/thế năng/hệ phương trình mạch) — sau đó bài toán còn lại **thuần túy là Toán** (đại số, ODE, hình học).

### 0.4 Cách dùng tài liệu để luyện tập

1. Với **mỗi** bài tập cũ đã giải, **viết lại tường minh** 11 bước B0–B10 ra giấy — kể cả khi đã biết đáp số. Đây là "ép buộc" bộ não chuyển từ *nhận diện mẫu* sang *thực thi thuật toán*.
2. Sau ~30–50 bài được viết tường minh như vậy, tốc độ thực thi B0–B10 sẽ nhanh dần **không phải vì đã "nhớ dạng bài"**, mà vì các bước đã thành phản xạ thủ tục (giống học sinh giỏi Toán làm được integral khó không phải vì "nhớ đề bài" mà vì thành thạo kỹ thuật đổi biến/từng phần).
3. Trong phòng thi: **luôn bắt đầu bằng B0–B5 trên giấy nháp**, kể cả khi tưởng đã "nhìn ra" cách giải — vì (a) B0–B5 tốn rất ít thời gian (2–5 phút) so với việc giải sai hướng và phải làm lại (10–20 phút); (b) đây chính là "lưới an toàn" chống lại việc đề bài diễn đạt lạ khiến trực giác đánh lừa.

---

## PHẦN I — QUY TRÌNH TỔNG QUÁT: 11 BƯỚC (B0 → B10)

```
B0  Quét văn bản & hình ảnh — trích xuất dữ kiện, dịch ngôn ngữ tự nhiên → toán học
B1  Định nghĩa Hệ & lựa chọn hệ quy chiếu                      [thủ tục hữu hạn, §B1]
B2  Đếm Bậc Tự Do thô (f_raw)                                  [Trụ cột A — Định lý A]
B3  Liệt kê Ràng buộc (dùng Từ điển B3 + phép dịch chuyển ảo)  [Trụ cột B — Định lý B]
B4  Săn Đối xứng / Định luật bảo toàn (Noether)                [Trụ cột C — Định lý C1,C2]
B5  Chọn Tọa độ suy rộng tối thiểu (f_eff)                     [thủ tục hữu hạn, §B5]
B6  Xấp xỉ hóa & Phân tích thang đo                             [Trụ cột D — Định lý D1–D3]
B7  Chọn "ngôn ngữ chi phối" đúng (method selection)           [cây quyết định, §B7 — TRỌNG TÂM]
B8  Điều kiện biên & điều kiện đầu (nguồn tin ẩn thứ 2)        [bảng tra cứu, §B8]
B9  Giải hệ (đại số / vi phân / đồ thị / số)                   [hộp công cụ, §B9]
B10 Kiểm tra ngược — Verification Protocol                     [checklist 5 bước, §B10]
```

Mỗi bước dưới đây được trình bày theo cùng khuôn: **(a)** nguyên tắc tổng quát; **(b)** thủ tục thực thi từng bước cụ thể; **(c)** bảng tra cứu/định lý hỗ trợ nếu có; **(d)** bẫy thường gặp.

---

## B0 — QUÉT (Full Scan Protocol)

**Nguyên tắc:** Đề bài là dữ liệu nén — mỗi tính từ, mỗi con số, mỗi đường nét trong hình/văn bản đều mang thông tin.

**Thủ tục bắt buộc:**

1. Đọc chậm **toàn bộ** đề một lượt, không giải, chỉ **gạch chân**:
   - Mọi đại lượng đã cho (kèm đơn vị, và **dấu** nếu có: đại số hóa mọi đại lượng ngay từ đầu — dòng điện, điện tích, công,... đều là đại lượng có dấu);
   - Mọi tính từ mô tả (nhẹ, lý tưởng, không ma sát, rất dài, mảnh, đồng chất, chuẩn tĩnh, đủ lâu, ban đầu, tức thời…) — **tra ngay vào Từ điển B3** (§3.2) để dịch sang phương trình;
   - Động từ chỉ hành động/biến cố (thả ra, đóng khóa K, đảo cực, cắt dây, va chạm…) — mỗi động từ này thường đánh dấu một **điều kiện biên/đầu** (→ B8);
   - Câu hỏi thật sự (đại lượng cần tìm — đây là "biến mục tiêu", định hướng bạn chọn phương pháp ở B7: xem quy tắc "Biến mục tiêu quyết định phương pháp" trong §B7.0).
2. Nếu có hình: quét **trái→phải, trên→dưới**, liệt kê **từng** phần tử (điện trở, tụ, cuộn, ròng rọc, bản lề, mặt tiếp xúc…) và **từng** ký hiệu góc/khoảng cách/chiều mũi tên dòng điện — dấu mũi tên = quy ước dấu, không phải chiều thật.
3. Lập **Bảng biến số**: | Đã cho | Ký hiệu | Ẩn cần tìm | — việc lập bảng buộc não bộ tường minh hóa từng dữ kiện thay vì "cảm giác đã hiểu".
4. **Tự vẽ lại hình** (kể cả khi đề đã có hình) — thao tác vẽ lại chính là bước đầu tiên của B1/B2, và nó lộ ra ràng buộc mà mắt "lướt qua" khi chỉ nhìn hình có sẵn.
5. Đặc biệt với hình: **không giả định gì không được vẽ hoặc không được nói** (ví dụ không tự thêm ma sát nếu đề không nói có; nhưng cũng không tự loại bỏ ma sát nếu đề không nói "không ma sát" — xem Từ điển B3, §3.2).

**Bẫy thường gặp:** bỏ sót một tính từ nhỏ ("ban đầu", "lý tưởng", "đủ lâu") — mỗi từ này **luôn** tương ứng đúng 1 dòng trong Từ điển B3 hoặc bảng B8; luyện thói quen quét-đối-chiếu hai bảng này cho **mọi** tính từ gạch chân.

---

## B1 — ĐỊNH NGHĨA HỆ & HỆ QUY CHIẾU

### 1.1 Định nghĩa Hệ

Liệt kê từng vật thể/mỗi phần tử là một "hệ con". Áp dụng:
- **`[MEH]` idea 4**: đôi khi coi *toàn bộ* nhiều vật là **một hệ** (loại bỏ nội lực chưa biết) lợi hơn xét từng vật — dùng khi câu hỏi **không** cần biết nội lực (lực giữa các thành phần).
- **`[MEH]` idea 47**: vật "nhẹ" (khối lượng/quán tính không đáng kể) ⇒ hợp lực & hợp mô-men trên nó luôn bằng 0 tại **mọi thời điểm** (kể cả khi đang có gia tốc!) — dùng để tách ẩn (lực căng dây nhẹ, lực trong lò xo nhẹ, dòng qua ampe kế lý tưởng...).

### 1.2 Thủ tục lựa chọn hệ quy chiếu — trả lời "Vấn đề phát sinh 0"

**Câu hỏi đặt ra trong bản nháp:** làm sao đảm bảo học sinh trực giác trung bình luôn chọn được hệ quy chiếu tốt, một cách **không phụ thuộc linh cảm**?

**Trả lời — biến việc "chọn hệ quy chiếu thông minh" thành phép **thử một danh sách hữu hạn** (đúng tinh thần $G_k$), theo thứ tự ưu tiên sau. Không cần "nhìn ra" ngay hệ tốt nhất — chỉ cần **thử lần lượt** và dùng tiêu chí loại trừ ở cột 3:**

| Thứ tự thử | Hệ quy chiếu ứng viên | Khi nào giữ lại (tiêu chí kiểm tra được) | Nguồn |
|---|---|---|---|
| 1 | Hệ phòng thí nghiệm (mặc định) | Luôn hợp lệ (quán tính) — dùng làm nền so sánh | — |
| 2 | Hệ gắn với vật "định nghĩa nền" của bài (mặt nghiêng, giá đỡ, toa xe...) đang **đứng yên hoặc chuyển động thẳng đều** | Nếu vật đó đứng yên/đều trong đề → hệ này **cũng là quán tính**, không phát sinh lực quán tính, nhưng đơn giản hoá điều kiện "vật kia nằm yên trên nó" | `[MEH]` idea 7 |
| 3 | Hệ **phi quán tính** tịnh tiến theo vật "nền" (nếu vật nền có gia tốc $\vec a$ đã biết hoặc là ẩn) | Nếu điều kiện bài toán ("vật đứng yên so với nêm", "giữ nguyên vị trí tương đối") được phát biểu **tự nhiên nhất** trong hệ này | `[MEH]` idea 7, idea 8 (gia tốc quán tính $-m\vec a$ hoạt động y hệt trọng lực hiệu dụng) |
| 4 | Hệ khối tâm (CM-frame) | Khi bài **không** có ngoại lực (hoặc ngoại lực đối xứng), và câu hỏi liên quan đến chuyển động **tương đối** giữa các phần (va chạm, dao động nội bộ, nổ) | `[MEH]` idea 53 ("collisions... easier in CM system vì động lượng tổng = 0"), Fact 6 |
| 5 | Hệ quay đều cùng bộ phận quay (rotating frame) | Khi có bộ phận quay đều với $\omega$ đã biết, và câu hỏi hỏi về vật **đứng yên hoặc chuyển động đơn giản so với bộ phận quay đó** | `[MEH]` idea 9, idea 26; xuất hiện lực li tâm $m\omega^2\vec R$ + Coriolis $-2m\vec\Omega\times\vec u$ |
| 6 | Hệ gắn với "môi trường gây ma sát" (mặt trượt) khi ma sát là lực chi phối | Khi câu hỏi cốt lõi là hướng trượt tương đối | `[MEH]` idea K-7 |

**Quy tắc dừng (khi nào KHÔNG cần đổi hệ quy chiếu):** nếu bài chỉ có **một** vật rắn không đổi trạng thái nền tảng (không có "vật nền chuyển động"), hệ phòng thí nghiệm luôn đủ — không lãng phí thời gian thử các mục 2–6.

**Tiêu chí khách quan để "chốt" hệ quy chiếu** (không dựa cảm tính): chọn hệ quy chiếu sao cho **số điều kiện ràng buộc (B3) viết ra đơn giản nhất** (ít thành phần vuông góc/song song phải chiếu nhất). Đây là tiêu chí **định lượng được** — đếm số phép chiếu cần làm trong mỗi lựa chọn, chọn hệ có số ít nhất. Nếu hai lựa chọn ngang nhau, chọn hệ mà **Trụ cột C (đối xứng)** lộ ra rõ nhất (ví dụ hệ khối tâm luôn làm lộ bảo toàn động lượng tầm thường $P=0$).

**Kết luận cho Vấn đề phát sinh 0:** việc "chọn hệ quy chiếu thông minh" được thuật toán hoá thành: (i) danh sách hữu hạn 6 loại hệ quy chiếu ứng viên (bảng trên); (ii) tiêu chí định lượng để chọn giữa các ứng viên (đếm số phép chiếu). Không còn phụ thuộc "linh cảm" — một học sinh kỷ luật chỉ cần **thử tuần tự** theo bảng.

---

## PHẦN 2 — TRỤ CỘT A: BẬC TỰ DO (Degrees of Freedom)

### 2.1 Định lý A (Đếm bậc tự do — Định lý Giá trị Chính quy)

> **Định lý A.** Cho $N$ toạ độ thô $x=(x^1,\dots,x^N)\in\mathbb R^N$ và $k$ hàm ràng buộc toàn chỉnh $g_1,\dots,g_k: \mathbb R^N\times\mathbb R\to\mathbb R$, $g_j(x,t)=0$. Giả sử tại điểm đang xét, ma trận Jacobi $\partial(g_1,\dots,g_k)/\partial x$ có **hạng đầy đủ** $k$ (đây là định nghĩa chính xác, kiểm tra được, của "$k$ ràng buộc độc lập"). Khi đó tập nghiệm $Q_t = \{x: g_j(x,t)=0\ \forall j\}$ là một đa tạp trơn với
> $$\dim Q_t = N-k = f.$$

**Chứng minh.** Đây là hệ quả trực tiếp của Định lý Hàm ẩn. Vì hạng Jacobi $=k$, sau khi (nếu cần) sắp lại thứ tự toạ độ, ma trận con $k\times k$ gồm các đạo hàm riêng theo $k$ biến cuối $x^{N-k+1},\dots,x^N$ khả nghịch tại điểm $x_0$. Định lý Hàm ẩn cho phép giải $k$ biến này như hàm trơn của $N-k$ biến còn lại trong một lân cận của $x_0$: $x^{N-k+i} = \varphi_i(x^1,\dots,x^{N-k})$. Ánh xạ $x\mapsto (x^1,\dots,x^{N-k})$ hạn chế trên $Q_t$ do đó là một vi phôi địa phương lên một tập mở của $\mathbb R^{N-k}$. Vậy $Q_t$ trơn, chiều $N-k$ tại lân cận mọi điểm thoả điều kiện hạng. $\blacksquare$

Định lý A **hoàn toàn tổng quát và thuật toán** — cho $N,k$ và các $g_j$, việc tính hạng Jacobi là đại số tuyến tính thuần tuý (khử Gauss), không cần trực giác.

**Quy tắc kiểm tra (tổng quát hóa Fact 18 của `[MEH]`):**
$$f_{\text{eff}} = f_{\text{raw}} - (\text{số ràng buộc độc lập tìm được ở B3}) - (\text{số bảo toàn/đối xứng tìm được ở B4, dùng đúng theo cảnh báo §B5.3})$$

### 2.2 Thư viện DOF thô + bảng khớp nối — trả lời "Vấn đề phát sinh 1"

**Câu hỏi đặt ra trong bản nháp:** "check xem loại khớp nối/ràng buộc nào áp dụng" — làm sao học sinh trực giác trung bình nhận diện đúng, không case-by-case?

**Trả lời — đây chính xác là một $G_k$: danh sách khớp nối/ràng buộc cơ học xuất hiện trong $\mathcal P_{\text{IPhO}}$ là HỮU HẠN và liệt kê trọn vẹn được (giống kỹ thuật "cặp động học — kinematic pair" trong cơ học máy, thu gọn về mức cần cho Olympic Vật lý).**

**Bảng 2.A — DOF thô của các đối tượng cơ bản (trước khi áp bất kỳ ràng buộc nào):**

| Đối tượng | DOF thô (chuyển động phẳng, 2D) | DOF thô (không gian, 3D) |
|---|---|---|
| Chất điểm | 2 ($x,y$) | 3 ($x,y,z$) |
| Vật rắn | 3 ($x_C,y_C,\theta$) | 6 (3 tịnh tiến CM + 3 góc quay) |
| Hệ $N$ chất điểm độc lập | $2N$ | $3N$ |
| Hệ $N$ vật rắn độc lập | $3N$ | $6N$ |
| Dòng điện trong mạch có $b$ nhánh, $n$ nút | $b$ dòng nhánh thô | (dùng B3.4 riêng cho mạch, xem dưới) |

**Bảng 2.B — Số DOF bị khử bởi mỗi loại ràng buộc/khớp nối (áp dụng lên tổng DOF thô để ra $f_{\text{eff}}$ tạm thời, TRƯỚC khi trừ tiếp phần bảo toàn ở B4):**

| Loại ràng buộc / khớp nối | Mô tả toán học | Số DOF khử (2D) | Số DOF khử (3D) | Toàn chỉnh? |
|---|---|---|---|---|
| Bản lề nối 2 vật rắn tại 1 điểm (pin/hinge) | vị trí 2 điểm trùng nhau, góc tương đối tự do | 2 | 3 | Có |
| Ngàm cứng / hàn cứng (rigid weld) | vị trí VÀ góc trùng nhau | 3 | 6 | Có |
| Con trượt trong rãnh thẳng cố định (prismatic joint) | chỉ còn 1 tịnh tiến dọc rãnh | 2 | 5 | Có |
| Chất điểm ràng buộc trên đường cong/rãnh cho trước | vị trí tham số hoá bởi 1 biến cung $s$ | 1 (còn 1 DOF) | 2 (còn 1 DOF) | Có |
| Dây/thanh cứng không giãn nối 2 điểm bất kỳ (chỉ ràng buộc khoảng cách) | $\lvert \vec r_1-\vec r_2\rvert=$const | 1 | 1 | Có |
| Ròng rọc lý tưởng (đổi hướng dây, không đổi độ dài) | không thêm DOF mới, chỉ truyền ràng buộc độ dài qua khúc gấp | 0 (không khử thêm — đã tính trong dòng trên) | 0 | — |
| Lăn không trượt trên đường **thẳng cố định** (2D) | $\dot x = R\dot\theta$, tích phân được vì $R=$const | 1 | — | **Có** (Định lý B, VD B.1) |
| Lăn không trượt trên mặt cong cố định (2D) | $ds = R\,d\theta$ | 1 | — | Có (tích phân theo cung) |
| Lăn không trượt tự do trong mặt phẳng (đĩa/quả cầu di chuyển hướng tuỳ ý, 3D) | ràng buộc vận tốc điểm tiếp xúc = 0, không tích phân được toàn cục | **0 trên $Q$** (chỉ giảm không gian **vận tốc** khả dĩ, không giảm chiều $Q$) | — | **Không** (Định lý B, VD B.2) — *bẫy kinh điển!* |
| Tiếp xúc trượt tự do, không ma sát, giữa 2 mặt cứng | khoảng cách pháp tuyến = 0 khi còn tiếp xúc (bất đẳng thức $\to$ đẳng thức biên khi chưa tách) | 1 | 1 | Có, nhưng **có điều kiện** (chỉ khi còn tiếp xúc — xem B8: N≥0) |
| Vật cô lập về điện (isolated conductor) | $Q=$const (ràng buộc "điện tích", không phải hình học) | — | — | Có (bảo toàn điện tích) |
| Nút mạch điện (Kirchhoff I) | $\sum I_{\text{vào}} = \sum I_{\text{ra}}$ tại mỗi nút | $N-1$ ràng buộc độc lập cho $N$ nút | — | Có |
| Vòng mạch kín (Kirchhoff II) | $\sum U = 0$ quanh vòng — **đây không phải "khử DOF" mà là phương trình bổ sung độc lập tuyến tính, số vòng độc lập = $b-n+1$ (định lý đồ thị Euler)** | — | — | Có |

**Thủ tục thực thi B2 (thuật toán 5 dòng, dùng được cho MỌI bài cơ hệ):**

1. Đếm số vật rắn/chất điểm **độc lập** $\Rightarrow$ $f_{\text{raw}}$ theo Bảng 2.A.
2. Với **mỗi cặp** vật có tương tác hình học (chạm nhau, nối bởi dây/thanh/bản lề/rãnh), tra Bảng 2.B, cộng dồn số DOF bị khử $\Rightarrow k_{\text{hình học}}$.
3. Với mỗi ràng buộc lăn: **bắt buộc kiểm tra bằng Định lý B** (tính $\omega\wedge d\omega$, xem §3.1) trước khi trừ — chỉ trừ nếu toàn chỉnh (thường đúng khi chuyển động bị hạn chế trong 1 mặt phẳng cố định, xem `[MEH]` idea 65 khi trục quay tức thời tịnh tiến mà không đổi khoảng cách tới khối tâm).
4. $f_{\text{eff, hình học}} = f_{\text{raw}} - k_{\text{hình học}}$.
5. Áp tiếp B4 (đối xứng/bảo toàn) theo đúng **cảnh báo về thứ tự** ở §B5.3 để ra $f_{\text{eff}}$ cuối cùng dùng cho B5/B7.

**Kết luận cho Vấn đề phát sinh 1:** "loại khớp nối nào áp dụng" được trả lời bằng cách **tra Bảng 2.B** — bảng này liệt kê **trọn vẹn** các loại khớp nối/ràng buộc xuất hiện trong $\mathcal P_{\text{IPhO}}$ (kiểm chứng: mọi bài trong `[MEH]` §3–§5 và mọi ràng buộc trong `[ELK]` đều rơi vào một trong các dòng của bảng). Nếu gặp một ràng buộc "lạ" không khớp dòng nào, **quy trình dự phòng** là quay lại định nghĩa gốc: viết phương trình hình học nối các toạ độ thô rồi áp trực tiếp Định lý A (không cần thuộc bảng — bảng chỉ là "tra cứu nhanh", Định lý A mới là nền tảng **G** thực sự).

**Vấn đề phát sinh 2:** Vậy đâu là "General Algorithm" (Đảm bảo tính tổng quát, chứ không phải lạm dụng case-by-case, cũng như tính máy móc, cơ học của nó, dù độ khó là cỡ đề thi VPHO/IPHO/APHO/...) để thí sinh trực giác trung bình vẫn có thể viết phương trình hình học nối các toạ độ thô rồi áp trực tiếp Định lý A, gần như không cần dùng não?

---

## PHẦN 3 — TRỤ CỘT B: RÀNG BUỘC & BIÊN

> Mỗi ràng buộc hình học/vật lý = **1 phương trình liên hệ giữa các DOF**, làm $f_{\text{eff}}$ giảm đi đúng **1**.

**Phép kiểm tra gốc (khi từ khóa không rõ / bị "giấu"):** dùng **phép dịch chuyển ảo (virtual displacement)** — tưởng tượng hệ nhích một lượng vi phân $\delta$, hỏi "đại lượng nào **buộc phải không đổi**?" (chiều dài dây, thông lượng qua vòng siêu dẫn, điện tích trên vật cô lập…). Đây là cách tái tạo ràng buộc **từ nguyên lý đầu tiên**, không phụ thuộc từ khóa có xuất hiện hay không — đây là "lưới an toàn" chống lại việc đề bài dùng cách diễn đạt lạ để né từ khóa quen thuộc.

**Virtual displacement :** https://en.wikipedia.org/wiki/Virtual_displacement



**Thủ tục phép dịch chuyển ảo (thuật toán 4 bước, `[MEH]` method 1):**
1. Chọn 1 đại lượng $x$ mà ta *nghĩ* là bị ràng buộc (độ dài dây, khoảng cách...).
2. Tưởng tượng $x \to x+\delta x$, giữ mọi thứ khác cố định trừ những gì hình học **buộc** phải thay đổi theo.
3. Viết biểu thức các đại lượng khác thay đổi theo $\delta x$ như thế nào (đây chính là các hệ số trong ràng buộc Pfaff, §3.1).
4. Nếu tổng công ảo/năng lượng ảo phải bằng 0 vì lý do vật lý (dây không giãn không tiêu tán năng lượng, vật cứng không biến dạng) $\Rightarrow$ ràng buộc được xác nhận và định lượng hoá.

### 3.1 Chính xác hoá ranh giới toàn chỉnh / không toàn chỉnh

> **Định lý B (Tiêu chuẩn Frobenius).** Cho ràng buộc Pfaff $\omega = \sum_i A_i(q,t)\,dq^i + A_t(q,t)\,dt = 0$ (một dạng vi phân bậc 1). Ràng buộc này là **toàn chỉnh** (tồn tại thừa số tích phân $\mu$ và hàm $F$ sao cho $\omega=\mu\,dF$, tức mặt $F=$const chứa trọn quỹ đạo) **khi và chỉ khi**
> $$\omega\wedge d\omega = 0.$$
> Đây là một phép kiểm tra **thuật toán, tổng quát tuyệt đối** trên lớp ràng buộc Pfaff đơn: chỉ cần lấy vi phân ngoài và nhân ngoài, không cần đoán.

**Ví dụ kiểm chứng B.1 (toàn chỉnh).** Đĩa bán kính $R$ lăn không trượt trên một đường thẳng: $\dot x = R\dot\theta \Rightarrow \omega = dx - R\,d\theta$. Vì $R$ hằng, $d\omega = 0$, nên $\omega\wedge d\omega = \omega\wedge 0=0$ tự động. **Toàn chỉnh** — tích phân trực tiếp: $x-R\theta=$const. (Đây chính là cơ sở toán học của các ràng buộc lăn dùng xuyên suốt `[MEH, pr. 44, 47, 65]`, nơi ràng buộc lăn được dùng như một phương trình đại số bình thường.)

**Ví dụ kiểm chứng B.2 (không toàn chỉnh — "xe đạp một bánh"/đĩa lăn tự do đổi hướng).** Cấu hình $(x,y,\theta)$, ràng buộc "không trượt ngang": $-\sin\theta\,dx+\cos\theta\,dy=0$, tức $\omega=-\sin\theta\,dx+\cos\theta\,dy$.
$$d\omega = -\cos\theta\,d\theta\wedge dx-\sin\theta\,d\theta\wedge dy.$$
Tính trực tiếp (khai triển đầy đủ, dùng phản đối xứng $dq^i\wedge dq^j=-dq^j\wedge dq^i$, $dq^i\wedge dq^i=0$):
$$\omega\wedge d\omega = -\,dx\wedge dy\wedge d\theta \;\neq\; 0.$$
**Không toàn chỉnh.** Đây là lý do toán học nghiêm ngặt vì sao một chiếc xe/đĩa có thể đi từ *bất kỳ* cấu hình $(x,y,\theta)$ nào đến *bất kỳ* cấu hình nào khác (đỗ xe song song!) dù tại mỗi thời điểm chỉ có 1 bậc tự do vận tốc khả dĩ: không gian cấu hình *không* bị thu hẹp, dù không gian *vận tốc tức thời* bị thu hẹp.

**Quan sát quan trọng:** Có một lớp tình huống mà Định lý A thất bại theo nghĩa kỹ thuật: khi số ràng buộc **hình học lý tưởng hoá** (dây/thanh cứng tuyệt đối) vượt quá số bậc tự do thực — hệ *siêu tĩnh*. `[MEH, idea 30]` chỉ ra chính xác đây là lúc mô hình "vật rắn tuyệt đối" phải được **nới lỏng** thành mô hình đàn hồi (`[MEH, fact 13]`, định luật Hooke $k=AY/L$) để đóng hệ phương trình.

### 3.2 Từ điển B3 — dịch từ khóa ngôn ngữ tự nhiên → phương trình ràng buộc

Đây là bảng được B0 tham chiếu ("tra ngay vào Từ điển B3"). Bảng liệt kê **trọn vẹn** các cụm từ mô tả xuất hiện lặp lại trong `[MEH]`/`[ELK]` và toàn bộ đề thi IPhO/VPhO cùng dạng — đây là công cụ biến "đọc hiểu đề bài" (kỹ năng ai cũng luyện được bằng kỷ luật) thành bước mô hình hoá chính xác, thay vì phụ thuộc "cảm giác vật lý":

| Từ khóa / mô tả trong đề | Ý nghĩa toán học chính xác | Ghi chú / nguồn |
|---|---|---|
| nhẹ, khối lượng không đáng kể (massless) | Hợp lực = 0 **và** hợp mô-men = 0 tác dụng lên vật đó tại **mọi** thời điểm, kể cả khi có gia tốc | `[MEH]` idea 47 — dùng để loại ẩn trung gian (lực căng dây nhẹ, phản lực lò xo nhẹ, dòng qua ampe kế lý tưởng) |
| không giãn / không co dãn (inextensible) | $\lvert \vec r_1-\vec r_2\rvert=$const dọc dây; đạo hàm 2 lần cho liên hệ vận tốc/gia tốc | `[MEH]` idea 32 |
| ròng rọc lý tưởng (nhẹ + không ma sát) | Độ lớn lực căng hai bên ròng rọc bằng nhau; có thể đổi **hướng** nhưng không đổi **độ lớn** | `[MEH]` idea 33 |
| lăn không trượt | Vận tốc điểm tiếp xúc = 0 — **BẮT BUỘC kiểm tra Định lý B** trước khi coi là ràng buộc vị trí (xem §3.1, VD B.1 vs B.2) | `[MEH]` idea 65, K-34 |
| không ma sát / trơn (frictionless, slippery) | Lực tiếp xúc chỉ có thành phần **pháp tuyến** — không có thành phần song song bề mặt | `[MEH]` fact 15 |
| lý tưởng (ideal) — ampe kế / vôn kế / nguồn | $R_{\text{ampe kế}}=0$; $R_{\text{vôn kế}}=\infty$; nguồn lý tưởng: điện trở trong $r=0$ | `[ELK]` §1.2 |
| cô lập về điện / cách điện hoàn toàn | $Q=$const trên vật đó theo thời gian | `[ELK]` §3.6 |
| nối đất (grounded) | $\varphi=0$ tại điểm đó; $Q$ tự do thay đổi | `[ELK]` §3.7 |
| cứng / vật rắn tuyệt đối (rigid) | Khoảng cách giữa **mọi** cặp điểm trên vật không đổi $\Rightarrow$ còn đúng 6 DOF (3D) / 3 DOF (2D) | Bảng 2.A |
| bản lề / khớp trụ (hinge/pin) | Vị trí 2 điểm trùng nhau; góc tương đối **tự do** | Bảng 2.B |
| ngàm / gắn cứng (rigid weld) | Vị trí **và** góc trùng nhau | Bảng 2.B |
| chuẩn tĩnh (quasi-static) | Bỏ qua động năng/lực quán tính; hệ ở cân bằng tức thời tại mọi thời điểm | `[MEH]` §3 (Statics áp dụng liên tục theo thời gian) |
| đủ lâu, ổn định, trạng thái dừng | Mọi đạo hàm theo $t$ của đại lượng "chậm" $\to 0$ | Xem thêm Bảng B8 |
| ban đầu chưa tích điện/chưa nạp | $Q(0)=0$ | `[ELK]` §2.1 |
| ban đầu đứng yên, thả ra, được thả tự do | $v(0)=0$; và (quan trọng) **gia tốc ban đầu song song hợp lực ban đầu** | `[MEH]` idea 31 |
| dây/thanh có khối lượng phân bố đều, "mảnh" | Dùng mật độ dài $\rho$ và tích phân; lực căng **không đều** dọc dây nếu dây có gia tốc (chỉ đều khi cân bằng tĩnh hoặc dây nhẹ) | `[MEH]` §3, pr 12–13 |
| đối xứng cầu / trụ / phẳng (điện tích, dòng) | Cho phép dùng Định lý C2 (Gauss/Ampère) — xem Bảng C mục 4 | `[ELK]` §3.2, §4.2 |
| tụ/cuộn "lý tưởng" trong mạch AC | Trở kháng thuần ảo: $\tilde Z_C = 1/(i\omega C)$, $\tilde Z_L = i\omega L$ | `[ELK]` §6.3 |
| diode lý tưởng | Dẫn hoàn toàn (R=0) khi phân cực thuận, cách điện hoàn toàn (R=∞) khi phân cực ngược | `[ELK]` §1.5 |
| "ngay sau khi", "tức thời", "vừa mới" | Đại lượng có quán tính **liên tục** qua biến cố; đại lượng không quán tính có thể **nhảy bậc** — xem chi tiết Bảng B8 | `[ELK]` §2.4, §5.2 |
| va chạm "đàn hồi tuyệt đối" | Bảo toàn động năng **và** động lượng (2 phương trình độc lập, không phải giả định tùy chọn) | `[MEH]` idea 52, fact 25 |
| va chạm "hoàn toàn không đàn hồi" | Sau va chạm 2 vật có cùng vận tốc tại điểm va chạm (không nhất thiết dính toàn bộ nếu là vật rắn quay) | `[MEH]` pr 45 |

**Bẫy cần nhớ:** cụm "không ma sát" **chỉ** loại bỏ thành phần lực song song bề mặt — **không** đồng nghĩa với "không có lực pháp tuyến"; cụm "nhẹ" áp dụng cho **lực và mô-men**, không phải cho động năng nếu vật đang quay nhanh (hiếm khi xảy ra trong $\mathcal P_{\text{IPhO}}$ nhưng cần cẩn trọng khi bài cho "vật nhẹ nhưng có mô-men quán tính đáng kể" — trường hợp này phải đọc kỹ, không tự động áp dụng Từ điển).

### 3.3 Ràng buộc điện — mở rộng riêng cho mạch (bổ sung cho §Phần 6)

| Ràng buộc | Phương trình | Số phương trình độc lập |
|---|---|---|
| Kirchhoff I (nút) | $\sum_n I_n = 0$ tại mỗi nút | $N_{\text{nút}}-1$ |
| Kirchhoff II (vòng) | $\sum_n U_n = 0$ quanh mỗi vòng độc lập | $b - N_{\text{nút}} + 1$ ($b$=số nhánh) |
| Bảo toàn điện tích tại nút cô lập (tụ nối tiếp không đường thoát) | $Q$ tổng tại "đảo" cô lập = const | 1 mỗi đảo |
| Liên tục từ thông qua vòng siêu dẫn ($R=0$) | $\Phi=$const | 1 |

---

## PHẦN 4 — TRỤ CỘT C: SĂN ĐỐI XỨNG (ĐỊNH LÝ NOETHER)

> **Định lý Noether (diễn giải thực dụng):** *Nếu tồn tại một phép biến đổi liên tục làm cho toàn cảnh vật lý "trông y hệt như trước", thì tồn tại một đại lượng bảo toàn tương ứng.*

Đây là công cụ **mạnh nhất** để giảm bậc tự do *hiệu dụng* mà không cần giải phương trình vi phân — mỗi đối xứng tìm được cho ta **một tích phân đầu** (first integral), tức hạ bậc của hệ phương trình vi phân đi 1.

### 4.1 Thủ tục "săn" đối xứng (6 phép thử chuẩn)

Với mỗi bài, **chủ động thử** từng phép biến đổi sau, hỏi "hiện tượng có trông y hệt không?":

1. **Tịnh tiến** hệ theo mỗi trục — còn ngoại lực dọc trục đó không?
2. **Quay** hệ quanh mỗi trục khả dĩ — còn ngoại mô-men không?
3. **Dịch thời gian** — các lực có phụ thuộc $t$ một cách "ngoại lai" không (ví dụ mặt phẳng nghiêng đang được kéo di chuyển)? Nếu **không** ⇒ năng lượng bảo toàn.
4. **Phản xạ gương / hoán vị nhãn** hai bộ phận — bài có "trông giống" sau khi lật không?
5. **Co giãn tỉ lệ** (đổi thang đo) — cấu trúc bài có lặp lại chính nó không (mạng vô hạn, phân dạng)?
6. **Đảo dấu một biến** (đảo cực nguồn, đảo chiều vận tốc ban đầu) — hệ có đối xứng gì?

> **Cảnh báo (idea 42, idea 58 của `[MEH]`):** Một định luật bảo toàn *chỉ đúng trong một khoảng thời gian/không gian nhất định* — kiểm tra lại điều kiện áp dụng mỗi khi có va chạm, ma sát xuất hiện, hoặc ngoại lực thay đổi bản chất. **Không thể** đồng thời có cả bảo toàn động lượng *và* bảo toàn động năng một cách "miễn phí" trừ khi được chứng minh (va chạm đàn hồi) — nếu bài yêu cầu dùng cả hai mà không nói rõ, ít nhất một trong hai **không** thật sự bảo toàn (idea 58) — đây là bẫy hay gặp.

### 4.2 Định lý C1 (Noether, dạng hữu hạn chiều, biến đổi không gian)

> **Định lý C1.** Cho $L(q,\dot q,t)$ với $q=(q^1,\dots,q^n)$ thoả phương trình Euler–Lagrange $\frac{d}{dt}\frac{\partial L}{\partial \dot q^i}=\frac{\partial L}{\partial q^i}$. Cho một trường véc-tơ $X=(X^1,\dots,X^n)$ trên không gian cấu hình (có thể phụ thuộc $t$), sinh ra họ biến đổi $q^i\mapsto q^i+\varepsilon X^i(q,t)$. Giả sử **với mọi** $(q,\dot q,t)$ (không chỉ dọc nghiệm):
> $$\sum_i\left[\frac{\partial L}{\partial q^i}X^i+\frac{\partial L}{\partial \dot q^i}\frac{dX^i}{dt}\right]=0,\qquad \frac{dX^i}{dt}:=\frac{\partial X^i}{\partial t}+\sum_j\frac{\partial X^i}{\partial q^j}\dot q^j. \tag{$*$}$$
> Khi đó đại lượng $I(q,\dot q,t)=\sum_i \dfrac{\partial L}{\partial \dot q^i}X^i(q,t)$ **bảo toàn** dọc mọi nghiệm: $\dfrac{dI}{dt}=0$.

**Chứng minh.** Dọc một nghiệm $q(t)$:
$$
\frac{dI}{dt}=\sum_i\left[\frac{d}{dt}\Big(\frac{\partial L}{\partial \dot q^i}\Big)X^i+\frac{\partial L}{\partial \dot q^i}\frac{dX^i}{dt}\right]
\stackrel{\text{E-L}}{=}\sum_i\left[\frac{\partial L}{\partial q^i}X^i+\frac{\partial L}{\partial \dot q^i}\frac{dX^i}{dt}\right]\stackrel{(*)}{=}0.\qquad\blacksquare
$$

**Điều kiện $(*)$ là tổng quát và thuật toán:** với **bất kỳ** $X$ *cho trước*, kiểm tra $(*)$ chỉ là đạo hàm riêng và cộng — có thể lập trình bằng phần mềm đại số máy tính, không cần trực giác. Phần "case-by-case" duy nhất trong toàn bộ trụ cột C là: **liệt kê $X$ nào đáng thử**, và Mục 4.4 chỉ ra đây là lớp $G_k$ (tổng-quát-hữu-hạn), không phải $C$ vô hạn.

### 4.3 Ba hệ quả tường minh — kiểm chứng từng bước, khớp `[MEH]`

**(a) Toạ độ cyclic $\Rightarrow$ động lượng suy rộng bảo toàn.**
Nếu $\partial L/\partial q^1\equiv 0$, chọn $X=(1,0,\dots,0)$ (hằng, $dX/dt=0$). $(*)$: $\frac{\partial L}{\partial q^1}\cdot 1+0=0$ — đúng theo giả thiết. $\Rightarrow I=\partial L/\partial \dot q^1=p_1=$const. Đây đúng là ghi chú của `[MEH]` ở Phụ lục 6: *"in the case of translational symmetry we don't even need to use the Noether's theorem: $\partial L/\partial q_i=0$, hence $d/dt\,p_i=0$"*.

**(b) Đối xứng tịnh tiến toàn hệ $\Rightarrow$ bảo toàn động lượng tổng (`[MEH, fact 6]`).**
Xét $n$ chất điểm, $L=\sum_i \frac12 m_i|\dot r_i|^2-V(r_1,\dots,r_n)$, với $V$ chỉ phụ thuộc **hiệu** vị trí (bất biến tịnh tiến toàn cục). Lấy $X_i=\hat n$ (cùng một hằng véc-tơ cho mọi hạt), $dX/dt=0$. Điều kiện bất biến của chính $V$ dưới tịnh tiến toàn cục, lấy đạo hàm theo $\varepsilon$ tại $\varepsilon=0$, cho trực tiếp $\sum_i \nabla_i V\cdot \hat n=0$ với mọi $\hat n$ — đây chính là $(*)$. Vậy $I=\sum_i m_i\dot r_i\cdot\hat n = P\cdot\hat n$ bảo toàn với mọi $\hat n$ $\Rightarrow$ $P=$const. $\blacksquare$

**(c) Đối xứng quay toàn hệ $\Rightarrow$ bảo toàn mô-men động lượng (`[MEH, fact 7]`).**
Lấy $X_i(r)=\hat n\times r_i$ (phép quay vi phân quanh trục $\hat n$), tuyến tính theo $q$ nên $dX_i/dt=\hat n\times \dot r_i$. Với $V$ bất biến quay, cùng lý luận cho $\sum_i\nabla_iV\cdot(\hat n\times r_i)=0$. Số hạng động năng: $\sum_i m_i\dot r_i\cdot(\hat n\times \dot r_i)=0$ (dùng $a\cdot(b\times c)=b\cdot(c\times a)$ và $\dot r_i\times \dot r_i=0$). Vậy
$$I=\sum_i m_i\dot r_i\cdot(\hat n\times r_i)\stackrel{\text{hoán vị vòng}}{=}\hat n\cdot L_{\text{tổng}}$$
bảo toàn với mọi $\hat n$ $\Rightarrow$ $L_{\text{tổng}}=$const. $\blacksquare$

**(d) Đối xứng tịnh tiến thời gian $\Rightarrow$ bảo toàn năng lượng (`[MEH, fact 8]`).**
Định nghĩa $H:=\sum_i \dot q^i \dfrac{\partial L}{\partial \dot q^i}-L$. Tính trực tiếp dọc nghiệm, dùng E-L:
$$
\frac{dH}{dt}=-\frac{\partial L}{\partial t}.
$$
Vậy nếu $L$ không phụ thuộc tường minh vào $t$, $H=$const. Nếu thêm $T$ là hàm thuần nhất bậc 2 theo $\dot q$ (ràng buộc không phụ thuộc $t$ — scleronomic), định lý Euler cho hàm thuần nhất cho $H=T+V=E$. $\blacksquare$

### 4.4 Vì sao trụ cột C là $G_k$ trên $\mathcal P_{\text{IPhO}}$

**Bảng C — danh mục $X$ hữu hạn cần thử:**

| # | Phép thử $X$ | Điều kiện áp dụng (thuật toán kiểm tra) | Đại lượng bảo toàn | Nguồn đối chiếu |
|---|---|---|---|---|
| 1 | Tịnh tiến dọc trục $\hat e_j$ | $q^j$ vắng mặt trong $L$ (cyclic) | $p_j$ | `[MEH]` idea 34, 35, 43 |
| 2 | Quay quanh trục $\hat n$ | thế năng chỉ phụ thuộc khoảng cách/góc bất biến quay quanh $\hat n$ | $L_{\hat n}$ | `[MEH]` fact 7 |
| 3 | Tịnh tiến thời gian | $\partial L/\partial t=0$ | $H$ (và $=T+V$ nếu scleronomic) | `[MEH]` fact 8, method 6 |
| 4 | Đối xứng hình học nguồn trường (cầu/trụ/phẳng) | mật độ điện tích/dòng bất biến dưới nhóm con $SO(3)$/$SO(2)$/tịnh tiến | dạng hàm của $\vec E,\vec B$ suy giảm bậc tự do | `[ELK]` §3.2, §4.2 |
| 5 | Đối xứng gương/hoán vị mạch điện | mạch bất biến dưới một phép phản chiếu/hoán vị nút | các thế nút liên hợp bằng nhau | `[ELK]` §1.4 |

**Vì sao bảng này đầy đủ trên $\mathcal P_{\text{IPhO}}$:** mọi $V$ trong chương trình IPhO chỉ phụ thuộc (i) khoảng cách từng cặp hạt, (ii) vị trí tuyệt đối qua một trường ngoài *đều* (hấp dẫn đều, điện trường đều). Loại (i) chỉ có đúng nhóm đối xứng $SE(3)$ (tịnh tiến + quay) là để lại bất biến. Loại (ii) chỉ bất biến dưới tịnh tiến *trong mặt phẳng vuông góc với trường*. Vậy: **không có đối xứng "ẩn" nào khác có thể tồn tại** ngoài mục 1–3 đối với thư viện lực này.

### 4.5 Mở rộng sang trường liên tục (Gauss/Ampère)

> **Định lý C2 (Đối xứng nguồn $\Rightarrow$ đối xứng trường).** Cho mật độ điện tích $\rho$ đối xứng cầu: $\rho(Rx)=\rho(x)$ với mọi $R\in SO(3)$. Khi đó trường $\vec E(x)=\int \frac{x-x'}{4\pi\varepsilon_0|x-x'|^3}\rho(x')\,d^3x'$ thoả $\vec E(x)=E(|x|)\hat x$ với $E$ là một hàm vô hướng của $|x|$ duy nhất.

**Chứng minh.** *Bước 1 (đẳng biến).* Với $R\in SO(3)$ bất kỳ, đổi biến $x'=Ry$:
$$
\vec E(Rx)= R\int\frac{x-y}{4\pi\varepsilon_0|x-y|^3}\rho(y)\,d^3y = R\,\vec E(x).
$$
*Bước 2 (hướng).* Cố định $x\ne 0$, lấy $R\in SO(2)_x$ (quay quanh trục $Ox$). Bước 1: $\vec E(x)=R\vec E(x)$ — véc-tơ bất động dưới toàn bộ nhóm quay quanh trục đó chỉ có thể song song trục. Vậy $\vec E(x)\parallel \hat x$.

*Bước 3 (độ lớn chỉ phụ thuộc $r$).* Với $|x|=|x'|$, chọn $R$: $Rx=x'$. Bước 1: $E(x')=E(x)$. $\blacksquare$

**Hệ quả — định lý Gauss chỉ là hệ quả của Định lý C2 + định lý Gauss-Ostrogradsky:** vì $E_n=E(r)$ hằng trên mặt cầu $S_r$: $\oint_{S_r}\vec E\cdot d\vec S = E(r)\cdot 4\pi r^2 = Q_{\text{trong}}(r)/\varepsilon_0$. Kiểm chứng bằng số với `[ELK, ul. 72]` ($\rho$ đều, bán kính $R$): $E(r)=\dfrac{\rho r}{3\varepsilon_0}$ ($r<R$) — khớp chính xác. Cùng cơ chế áp dụng cho đối xứng trụ (định lý Ampère) và đối xứng phẳng, chỉ thay nhóm đối xứng.

**Kết luận Phần 4.** Trụ cột C có một lõi **hoàn toàn tổng quát và chứng minh được** (Định lý C1, C2), bọc quanh một danh sách phép thử **hữu hạn, liệt kê đầy đủ** trên thư viện lực IPhO (Bảng C).

---

## PHẦN 5 — TRỤ CỘT D: XẤP XỈ & THANG ĐO

### 5.1 Vì sao trụ cột D là trụ cột "dễ thuật toán hoá nhất"

Trái với trụ cột C (nơi phải *tìm* đối xứng), tham số bé $\varepsilon$ ở trụ cột D **hầu như luôn được đề bài cho tường minh** bằng ký hiệu $\ll$ hoặc $\gg$:

| Bài | Câu chữ tường minh trong đề | Nguồn |
|---|---|---|
| Tụ phẳng | "$d \ll R$" | `[ELK, ul. 52]` |
| Thấu kính electron | "$eU_0 \gg eE_1z_1, eE_2z_2$ và $a \ll z_1,z_2$" | `[ELK, ul. 74]` |
| Vật va chạm liên tục | "Assume that $g\tau \ll v$" | `[MEH, pr. 17]`, method 2 |
| Mạch RC | so sánh $T$ với $RC$ | `[ELK, §2.4, §5.2]` |
| Nêm nhẹ vs khối nặng | "very light and slippery material" | `[MEH, pr. 25]` |

Vì vậy **bước "nhận diện $\varepsilon$" phần lớn không phải bài toán vật lý — nó là bài toán đọc-hiểu đề bài** (một kỹ năng thuần tuý mà học sinh kỷ luật, cẩn thận hoàn toàn làm chủ được, không cần "trực giác vật lý"). Khi $\varepsilon$ không cho tường minh, ta có công cụ tổng quát sau để **suy ra nó bằng thuật toán thuần tuý**.

### 5.2 Định lý D1 (Buckingham $\Pi$)

> **Định lý D1 (Buckingham, 1914).** Nếu một hệ thức vật lý liên hệ $n$ đại lượng, và các đại lượng này được dựng từ $k$ thứ nguyên cơ bản độc lập (thường $k\le 3$: $M,L,T$), thì hệ thức đó **tương đương** với một hệ thức giữa $p=n-k$ nhóm không thứ nguyên độc lập $\Pi_1,\dots,\Pi_p$.

Đây là công cụ **thuần thuật toán**: lập ma trận số mũ thứ nguyên của $n$ đại lượng theo $k$ cơ sở, hạng ma trận cho $k$ thực, không gian hạt nhân (kernel) — tính bằng đại số tuyến tính — sinh ra chính xác các $\Pi_i$. Khi bài không cho $\varepsilon$ tường minh, $\varepsilon$ **bắt buộc** phải là một trong các $\Pi_i$ này.

### 5.3 Định lý D2 (Khai triển tiệm cận theo bậc)

> **Định lý D2.** Cho phương trình $F(x,\varepsilon)=0$ với nghiệm $x_0$ khi $\varepsilon=0$. Đặt $x=x_0+\varepsilon x_1+\varepsilon^2x_2+\cdots$. Khai triển Taylor $F$ theo $\varepsilon$ và **gom theo từng bậc**, mỗi bậc cho một phương trình tuyến tính cho $x_k$ — giải tuần tự.

Đây chính xác là `[MEH, idea 20]` (chuỗi Taylor) và `[MEH, method 2]` (phương pháp nhiễu loạn).

**Cảnh báo cực kỳ quan trọng khi kết hợp B4 với B5 (thứ tự Noether ↔ Lagrangian — trích Phụ lục 6 `[MEH]`, ví dụ "spring-dumbbell"):**

> Nếu một định luật bảo toàn (động lượng, mô-men động lượng — tức các đại lượng chứa **đạo hàm bậc nhất** của toạ độ) được dùng để **giảm số toạ độ suy rộng TRƯỚC KHI** lập Lagrangian/tính $\ddot q$ bằng Phương trình Euler–Lagrange, kết quả **sai** — vì việc cố định một đại lượng có đạo hàm không cố định giá trị toạ độ, làm thay đổi tập điểm đầu/cuối trong nguyên lý tác dụng tối thiểu.
>
> **Quy tắc đúng:** hoặc (a) giữ đủ số toạ độ suy rộng gốc và áp Euler–Lagrange đầy đủ, rồi **sau đó** dùng bảo toàn để đơn giản hoá nghiệm; hoặc (b) nếu bảo toàn đưa được hệ về đúng **1** toạ độ suy rộng hiệu dụng một cách hợp thức (không qua bước rút gọn sai), dùng trực tiếp Method 6 ($\ddot\xi=-\Pi'(\xi)/M$ với $M$ tính đúng từ động năng viết theo $\xi,\dot\xi$ duy nhất).

Đây là bẫy kỹ thuật **tinh vi nhất** trong toàn bộ tài liệu — học sinh giỏi thường mắc phải khi "quá tự tin" dùng bảo toàn để rút gọn biến trước khi kiểm tra điều kiện (b) có thực sự thoả không.

### 5.4 Định lý D3 (So sánh thang thời gian tuyến tính hoá $\Leftrightarrow$ trị riêng)

> **Mệnh đề.** Với hệ phương trình vi phân tuyến tính bậc nhất $\dot y = Ay$ ($A$ hằng), các "hằng số thời gian đặc trưng" chính xác là $\tau_i = -1/\operatorname{Re}(\lambda_i)$, với $\lambda_i$ là trị riêng của $A$. Việc *bài toán biến thiên "nhanh" hay "chậm" so với hệ* quy về so sánh chu kỳ ngoại lực $T$ với $\max_i \tau_i$.

Với mạch $RC$ đơn giản ($\dot U=-U/RC$), $A=(-1/RC)$, $\tau=RC$ — khớp `[ELK, §2.4]`.

**Kết luận Phần 5.** Trụ cột D gần như hoàn toàn thuật toán hoá được: (i) $\varepsilon$ thường **cho sẵn** trong đề; (ii) khi không cho sẵn, Định lý D1 thu hẹp không gian tìm kiếm về hữu hạn ứng viên; (iii) một khi có $\varepsilon$, Định lý D2, D3 là thuật toán tuyệt đối.

---

## B5 — CHỌN TỌA ĐỘ SUY RỘNG TỐI THIỂU (Sinh thiếu trong bản nháp — nay bổ sung đầy đủ)

### 5.B.1 Nguyên tắc

Sau khi có $f_{\text{eff}}$ (từ B2+B3, **và chỉ áp B4 theo đúng cảnh báo §5.3**), ta cần chọn **đúng $f_{\text{eff}}$ toạ độ vô hướng** $q_1,\dots,q_{f_{\text{eff}}}$ mô tả trọn vẹn cấu hình hệ. Đây **không phải** bước "đoán" mà là bước có tiêu chí chọn lựa rõ ràng.

### 5.B.2 Bốn tiêu chí chọn toạ độ suy rộng tốt (thứ tự ưu tiên)

1. **Tiêu chí tối giản (bắt buộc):** đúng $f_{\text{eff}}$ toạ độ — không hơn không kém. Nếu dùng nhiều hơn, phải bổ sung ràng buộc phụ trong Lagrangian (`[MEH]`, Phụ lục 6: *"the number of coordinates should be as small as possible"*).
2. **Tiêu chí liên hệ trực tiếp với biến mục tiêu (biến B0 xác định):** ưu tiên chọn toạ độ mà đạo hàm/giá trị của nó **chính là** hoặc **liên hệ tuyến tính đơn giản** với đại lượng đề bài hỏi — giảm số bước biến đổi ở B9.
3. **Tiêu chí "động năng đẹp":** ưu tiên toạ độ khiến động năng $T$ có dạng **thuần nhất bậc 2** đơn giản theo $\dot q$ (để Định lý C1(d)/`[MEH]` method 6 áp dụng trực tiếp, và để tránh các số hạng "giả-thế năng" ẩn trong $T(q,\dot q)$ như trong ví dụ spring-dumbbell ở §5.3).
4. **Tiêu chí tận dụng đối xứng đã tìm ở B4:** nếu B4 đã lộ ra 1 hướng bất biến (trục cyclic), **luôn** đưa hướng đó thành 1 trong các $q_i$ độc lập (dù sau đó có thể loại nó khỏi phương trình nhờ bảo toàn — nhưng theo đúng thứ tự ở §5.3).

### 5.B.3 Thực đơn toạ độ suy rộng theo loại bài (tra cứu nhanh — $G_k$)

| Loại hệ | Toạ độ suy rộng khuyến nghị | Vì sao |
|---|---|---|
| Nêm + vật trượt trên nêm, nêm tự do trượt trên sàn | $\xi$ = độ dịch của nêm; $\eta$ = độ dịch của vật *so với nêm* | Tách rời chuyển động tương đối, khớp `[MEH, pr 26, 27]` |
| Con lắc/hạt trên đường tròn/rãnh cong | góc $\varphi$ hoặc cung $s=R\varphi$ | Động năng $\frac12 mR^2\dot\varphi^2$ gọn |
| Hệ ròng rọc, dây nối nhiều vật | 1 toạ độ dịch chuyển dọc dây (thường là dịch chuyển của khối được kéo) | Mọi vị trí khác suy ra tuyến tính qua ràng buộc dây (B3) |
| Mạch RC/RL/LC | điện tích $Q$ trên tụ (hoặc từ thông $\Phi$ qua cuộn) làm "toạ độ suy rộng điện" | $L_{\text{điện}}(Q,\dot Q)=\frac12 L\dot Q^2-\frac{Q^2}{2C}$ — tương tự dao động cơ (xem `[ELK]` §2.4, §5.4, §6.4) |
| Hệ va chạm/nổ có bảo toàn động lượng | KHÔNG rút gọn toạ độ bằng $P=$const trước khi lập $L$ — dùng toạ độ khối tâm $R_{CM}$ + toạ độ tương đối $r_{rel}$ làm 2 nhóm biến tách rời (biến đổi chính tắc chuẩn, không phải "rút gọn sai") | Đây là cách hợp thức để dùng bảo toàn động lượng: đổi biến $(r_1,r_2)\to(R_{CM},r_{rel})$ TRƯỚC khi lập $L$, không phải SAU |
| Vật rắn quay tự do quanh trục cố định + vật trượt bên trong | góc quay $\theta$ của vật rắn + vị trí tương đối $s$ của vật trượt dọc rãnh | `[MEH, pr 8]` (bánh xe có lỗ) |

### 5.B.4 Bẫy cần tránh (nhắc lại có hệ thống)

- **Không** dùng đại lượng có đạo hàm bậc nhất bảo toàn (động lượng, mô-men động lượng) làm "toạ độ suy rộng đã rút gọn" trước khi lập Lagrangian đầy đủ — xem cảnh báo §5.3.
- **Không** chọn toạ độ dư (nhiều hơn $f_{\text{eff}}$) mà quên thêm ràng buộc Lagrange nhân tử — nếu bắt buộc phải dùng toạ độ dư (ví dụ để giữ đối xứng bài toán tường minh), phải dùng phương pháp nhân tử Lagrange, nằm ngoài phạm vi "tối giản" nhưng vẫn là kỹ thuật **G** chuẩn nếu cần.

---

## B7 — CHỌN "NGÔN NGỮ CHI PHỐI" ĐÚNG (Method Selection) — TRỌNG TÂM CỦA MÔ HÌNH HÓA

> Đây là bước **hoàn toàn vắng mặt** trong bản nháp gốc dù đã được liệt kê trong sơ đồ 10 bước — và đây chính xác là bước biến "bài Vật Lý" thành "bài Toán thuần túy": một khi đã chọn đúng ngôn ngữ chi phối, phần còn lại (B8–B9) chỉ là kỹ thuật giải toán (đại số/ODE/hình học), không còn cần trực giác vật lý nào thêm.

### 7.0 Nguyên tắc tối thượng: "Biến mục tiêu quyết định phương pháp"

Nhìn lại **câu hỏi thật sự** đã gạch chân ở B0. Đặt câu hỏi:

$$\textbf{"Đại lượng cần tìm có phải là (hoặc suy ra trực tiếp, không qua nhiều bước trung gian từ) một đại lượng BẢO TOÀN/BẤT BIẾN đã tìm ở B4 không?"}$$

- **Có** $\Rightarrow$ ưu tiên tuyệt đối ngôn ngữ bảo toàn (năng lượng/động lượng/mô-men động lượng/điện tích/từ thông) — thường cho lời giải **ngắn nhất**, đại số hoá ngay, không cần giải ODE.
- **Không**, và cần lực/gia tốc/trường tại một điểm/thời điểm cụ thể $\Rightarrow$ cần ngôn ngữ vi phân (Newton từng thành phần, Euler–Lagrange, hoặc phương trình trường vi phân).

Đây **không phải** một lựa chọn nhị phân đơn giản — dưới đây là **cây quyết định đầy đủ**, phân theo 4 nhóm bài lớn của $\mathcal P_{\text{IPhO}}$: (A) Cơ hệ chất điểm/vật rắn, (B) Va chạm/biến cố tức thời, (C) Trường tĩnh điện/từ, (D) Mạch điện (trỏ sang Phần 6).

### 7.1 Cây quyết định A — Cơ hệ liên tục (không va chạm)

| # | Dấu hiệu nhận diện trong đề (kiểm tra được) | Ngôn ngữ chi phối nên chọn | Điều kiện áp dụng | Nguồn |
|---|---|---|---|---|
| A1 | $f_{\text{eff}}=1$ sau B2–B5; mọi lực bảo toàn; **không** cần tìm lực liên kết (căng dây/phản lực) | **Method 6** — năng lượng suy rộng: $\ddot\xi=-\Pi'(\xi)/M(\xi)$ với $\Pi(\xi)+\frac12 M\dot\xi^2=E$ | Đã đúng 1 DOF hiệu dụng (không rút gọn sai, §5.3) | `[MEH]` method 6 |
| A2 | $f_{\text{eff}}\ge 2$; cần phương trình chuyển động tổng quát; không cần lực liên kết | **Euler–Lagrange đầy đủ** cho từng $q_i$ | $L=T-V$ lập được tường minh | `[MEH]` Phụ lục 6, method 6 tổng quát hoá |
| A3 | Đề hỏi **trực tiếp** một lực/phản lực/lực căng tại 1 điểm cụ thể | **Newton từng vật theo thành phần** (Method 4), chiếu trục thông minh (idea 1) | Luôn áp dụng được, có thể tốn thời gian hơn | `[MEH]` method 4 |
| A4 | Đã biết gia tốc (từ ràng buộc/động học) nhưng cần suy lực — thay vì tìm gia tốc từ lực | **idea 36**: đảo chiều suy luận, Newton dùng để suy lực từ gia tốc đã biết | Khi tìm gia tốc trực tiếp phức tạp hơn tìm lực | `[MEH]` idea 36, pr 28–29 |
| A5 | Vật rắn quay quanh trục tức thời **đang tịnh tiến** nhưng khoảng cách tới khối tâm không đổi (vật lăn) | $I\varepsilon=M$ vẫn dùng được quanh trục tức thời (không cần đổi hệ quy chiếu) | Điều kiện: khoảng cách CM–trục tức thời hằng | `[MEH]` idea 65 |
| A6 | Cần cả lực **và** mô-men cho vật rắn, đặc biệt khi 1 phần khối lượng "biến mất/xuất hiện" (dây cuốn/xả) | $\vec F=M\vec a_C$ tổng quát hoá (Method 48), kết hợp Định lý xung lượng hệ mở (idea 72) | Hệ có trao đổi khối lượng với "ngoài" | `[MEH]` method 48, idea 72 |
| A7 | Bài về ổn định cân bằng (stability) | Khảo sát cực trị **bậc 2** của $\Pi(q)$ quanh điểm cân bằng (Taylor, Định lý D2 bậc $\varepsilon^2$) | Xem thêm Phụ lục 5 `[MEH]` — cực tiểu ⇒ ổn định, cực đại có điều kiện ⇒ có thể vẫn ổn định nếu là cực trị *có điều kiện* của 1 đại lượng bảo toàn khác | `[MEH]` idea 19, 21, Phụ lục 5 |
| A8 | Dòng chảy liên tục (cát, chất lỏng, dây xích) | Bernoulli (idea 71) + phương trình liên tục (idea 59) + xung lượng dòng cho hệ mở (idea 72) | Không dùng bảo toàn năng lượng nếu có ma sát/xoáy (idea 58: kiểm tra cái nào thực sự bảo toàn) | `[MEH]` idea 59, 71, 72 |
| A9 | Hệ có ma sát mà **không rõ** có trượt hay không | **idea 51**: liệt kê hữu hạn tổ hợp khả dĩ (trượt/không trượt ở từng mặt tiếp xúc), giải từng trường hợp, kiểm tra tính tự hợp ($F_{ms}\le \mu N$) | Không đoán — thử **toàn bộ tổ hợp hữu hạn**, đúng tinh thần $G_k$ | `[MEH]` idea 51 |

### 7.2 Cây quyết định B — Va chạm / biến cố tức thời (impulsive)

| # | Dấu hiệu | Ngôn ngữ chi phối | Điều kiện | Nguồn |
|---|---|---|---|---|
| B1 | Va chạm chất điểm, đàn hồi tuyệt đối | Bảo toàn động lượng **và** động năng (2 phương trình, đủ cho va chạm 1D; với 2D cần thêm dữ kiện hình học — ví dụ hướng pháp tuyến va chạm) | Cả 2 luôn bảo toàn *đồng thời* trong va chạm đàn hồi — không mâu thuẫn idea 58 | `[MEH]` idea 52, fact 25 |
| B2 | Va chạm không hoàn toàn đàn hồi/dính | Bảo toàn động lượng + điều kiện động học phụ (vận tốc bằng nhau tại điểm tiếp xúc sau va chạm) — **không** dùng bảo toàn năng lượng | idea 58 | `[MEH]` pr 45 |
| B3 | Va chạm có vật rắn quay (gậy đánh, va chạm lệch tâm) | Bảo toàn **mô-men động lượng quanh điểm va chạm** (idea 64) — vì lực va chạm có cánh tay đòn = 0 tại chính điểm đó | Ngoại lực hữu hạn (trọng lực) bị bỏ qua trong thời gian va chạm cực ngắn | `[MEH]` idea 64 |
| B4 | Bài hỏi "hand không bị đau khi đánh" / điểm đặc biệt không truyền xung lực | Tìm điều kiện để xung lượng tại điểm giữ = 0, dùng idea 64 + idea 54 (hướng xung lượng = hướng lực không đổi) | | `[MEH]` idea 46, 54, 64, pr 46 |
| B5 | Nhiều va chạm liên tiếp, hệ nhiều hạt (n hạt trên dây) | Biểu diễn quá trình trên giản đồ $x$–$t$ (idea 55) để đếm số va chạm tối đa mà không "đoán" | | `[MEH]` idea 55, pr 37 |
| B6 | Va chạm với tường có ma sát trượt luôn xảy ra | Tỉ lệ xung lượng vuông góc : song song = $\mu$ (idea 60) | | `[MEH]` idea 60 |

### 7.3 Cây quyết định C — Trường tĩnh điện / tĩnh từ

| # | Dấu hiệu | Ngôn ngữ chi phối | Điều kiện | Nguồn |
|---|---|---|---|---|
| C1 | Cần $\vec E$ hoặc $\vec B$ tại 1 điểm; phân bố nguồn có đối xứng cầu/trụ/phẳng | **Định lý Gauss / Ampère** (hệ quả Định lý C2, Bảng C mục 4) | Đối xứng đủ để $E_n$/$B_l$ hằng trên mặt/đường Gauss chọn được | `[ELK]` §3.2, §4.2 |
| C2 | Không đủ đối xứng, nhưng phân bố nguồn đã biết đầy đủ | **Chồng chập trực tiếp** Coulomb/Biot–Savart (tích phân) | Luôn áp dụng được (tổng quát nhất, nhưng có thể tích phân khó) | `[ELK]` §3.3, §4.3 |
| C3 | Cần công/năng lượng, không cần trường tại từng điểm | Tính **điện thế $\varphi$** (đại số/tích phân vô hướng) trước, dùng công thức năng lượng trực tiếp, **hoặc** suy $\vec E=-\nabla\varphi$ sau cùng nếu cần | Vô hướng dễ cộng hơn véc-tơ | `[ELK]` §3.5 |
| C4 | Có vật dẫn trong trường ngoài, hình học đơn giản (mặt phẳng/cầu/trụ) | **Phương pháp ảnh điện (image charge)** — xem Phần 7.A | Hình học phải khớp 1 trong các case ảnh điện chuẩn | `[ELK]` §3.7, §3.9 |
| C5 | Có vật dẫn hình học phức tạp, hoặc chỉ cần thế trên vật dẫn | Dùng trực tiếp điều kiện biên: $\varphi=$const trên vật dẫn, $E_\parallel=0$ ngay sát bề mặt | | `[ELK]` §3.6 |
| C6 | Có điện môi đồng nhất trong trường đều/gần đều | Giả định phân cực đều $\Rightarrow$ hệ đại số tuyến tính cho $E$ trong/ngoài từ liên tục $D_n$, $E_\tau$ | Chỉ đúng khi hình học đối xứng đơn giản (tấm/cầu/trụ) — xem `[ELK]` §3.8 | `[ELK]` §3.8, ul 111–113 |
| C7 | Lực lên điện môi/vật dẫn tại **biên/rìa** (fringe effect) — không thể tính trực tiếp trường tại rìa | **Phương pháp dịch chuyển ảo (virtual work)**: $F=-\partial\Pi/\partial x$ tại $U$ không đổi (nguồn nối với pin) hoặc tại $Q$ không đổi (cô lập) — **chú ý dấu ngược nhau giữa 2 trường hợp!** | | `[ELK]` §2.3, §3.10, ul 52–54 |
| C8 | Hạt tích điện chuyển động trong $\vec E,\vec B$ | (1) Kiểm tra tọa độ cyclic trước (Bảng C mục 1) $\Rightarrow$ động lượng suy rộng $p'_x=p_x-qyB$ (nếu $E_x=0$) bảo toàn; (2) nếu chỉ có $\vec B$: Lorentz không sinh công $\Rightarrow$ $\lvert v\rvert=$const, quỹ đạo tròn/xoắn ốc; (3) đổi hệ quy chiếu vận tốc $u$ để triệt tiêu 1 thành phần trường nếu khả dĩ | | `[ELK]` §7.1 |
| C9 | Cảm ứng điện từ — hỏi về **trường** (xoáy) chứ không phải mạch | Faraday vi phân: $\oint \vec E\cdot d\vec l = -\partial\Phi/\partial t$ | | `[ELK]` §5.1 |
| C10 | Cảm ứng điện từ trong **mạch** cụ thể | Xem Phần 6 (Mạch điện) | | `[ELK]` §5.2–§5.4 |

### 7.4 Cây quyết định D — Mạch điện

Xem **Phần 6** (mục lục riêng bên dưới) cho cây quyết định đầy đủ về DC/AC/transient/phi tuyến.

### 7.5 Bảng tổng hợp một trang (dùng trong phòng thi)

```
CÂU HỎI CẦN GÌ?
│
├─ Lực/phản lực/căng dây tại 1 điểm cụ thể? ──────────────► A3 (Newton từng vật)
├─ Chuyển động tổng thể, đúng 1 DOF hiệu dụng? ───────────► A1 (Method 6)
├─ Chuyển động tổng thể, ≥2 DOF? ─────────────────────────► A2 (Euler–Lagrange)
├─ Có va chạm/biến cố tức thời? ──────────────────────────► Cây B (B1–B6)
├─ Trường E/B tại 1 điểm, có đối xứng? ───────────────────► C1 (Gauss/Ampère)
├─ Trường E/B tại 1 điểm, KHÔNG đối xứng? ────────────────► C2 (chồng chập)
├─ Thế năng/công, không cần trường từng điểm? ────────────► C3 (thế φ trước)
├─ Vật dẫn/điện môi, hình học chuẩn? ──────────────────────► C4/C6 (ảnh điện / BC)
├─ Lực tại rìa (fringe)? ──────────────────────────────────► C7 (dịch chuyển ảo)
├─ Hạt tích điện trong E,B? ───────────────────────────────► C8
└─ Mạch điện (DC/AC/transient)? ───────────────────────────► PHẦN 6
```

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
| Ampe kế/Vôn kế lý tưởng | R→0 / R→∞ tương ứng |
| Vật dẫn nối đất | φ = 0 |
| Vật dẫn cô lập | Q = const (giá trị ban đầu hoặc 0 nếu "chưa tích điện") |
| Bề mặt chất lỏng tự do gần tường/áp suất khí quyển | p = p_khí quyển tại đó (Fact 30 — Bernoulli) |
| Cực đại/cực tiểu của 1 đại lượng theo thời gian | Đạo hàm theo t của đại lượng đó = 0 tại thời điểm đó (idea 44; với mạch: dI/dt=0 ⇒ U_cuộn=0 lúc I cực đại) |
| Mạch xoay chiều, "ổn định" (steady-state) | Bỏ số hạng transient tắt dần, chỉ giữ nghiệm dao động ở tần số nguồn |
| Diode "vừa mở" | $U_{\text{diode}} = U_d$ (ngưỡng mở), hoặc $U=0$ nếu mô hình lý tưởng |
| "Cắt dây/mở khóa K tại t=0" | Trước $t=0^-$: hệ ở trạng thái xác định từ đề; ngay $t=0^+$: áp lại đúng dòng "liên tục vs nhảy bậc" ở trên |
| Hai điểm cùng điện thế do đối xứng (Bảng C mục 5) | Có thể chập lại thành 1 nút hoặc cắt dây nối — không đổi bản chất mạch |

---

## B9 — GIẢI HỆ (Hộp công cụ toán học thuần túy)

> Đây là bước "thoát khỏi Vật Lý, chỉ còn lại Toán". Bản nháp gốc bỏ trống hoàn toàn phần này — nay bổ sung một hộp công cụ đầy đủ.

### 9.1 Thứ tự ưu tiên khi giải hệ đại số nhiều ẩn

1. **Đếm ẩn = đếm phương trình** trước khi bắt đầu (kiểm tra chéo với $f_{\text{eff}}$ — nếu lệch, quay lại B2–B5).
2. **Khử dần (elimination)** theo thứ tự: khử **trước** các ẩn chỉ xuất hiện tuyến tính trong 1 phương trình (thường là lực căng, phản lực) — càng khử sớm các ẩn "phụ" này, hệ còn lại càng gọn.
3. Nếu hệ có **đối xứng cấu trúc** (ví dụ mạch cầu, hệ 2 vật giống hệt), **đoán dạng nghiệm (ansatz)** tôn trọng đối xứng đó trước (ví dụ giả sử 2 dòng điện liên hợp bằng nhau) — sau đó kiểm chứng bằng cách thay lại. Đây là ứng dụng trực tiếp của Trụ cột C ở tầng giải toán.
4. Với hệ có dạng **phương trình bậc 2 "trá hình"** (ví dụ bài con lắc rút gọn `[MEH, idea 69]`): nhận diện qua việc chỉ có tổng và tích 2 nghiệm xuất hiện $\Rightarrow$ dùng **định lý Viète** trực tiếp thay vì giải bậc 2 tường minh — nhanh hơn và tránh sai số căn thức.
5. Với hệ tuyến tính lớn (mạch điện nhiều nút) — xem thuật toán node-potential ở Phần 6.A, đây thực chất là giải hệ $Ax=b$ bằng khử Gauss có cấu trúc.

### 9.2 Nhận diện nhanh các dạng phương trình vi phân (ODE) chuẩn

| Dạng ODE | Nghiệm tổng quát | Khi nào gặp trong $\mathcal P_{\text{IPhO}}$ |
|---|---|---|
| $\tau\dot x + x = 0$ | $x(t)=Ce^{-t/\tau}$ | Phóng/nạp tụ qua điện trở, τ=RC (`[ELK]` §2.4); dòng qua cuộn+điện trở, τ=L/R (`[ELK]` §5.2) |
| $\tau\dot x + x = f$ (f hằng) | $x(t)=f+(x_0-f)e^{-t/\tau}$ (chồng chập nghiệm dừng + nghiệm thuần nhất) | Nạp tụ qua nguồn+điện trở (`[ELK]` §2.4) |
| $\ddot x + \omega^2 x = 0$ | $x(t)=C_1\cos\omega t + C_2\sin\omega t$ | Con lắc góc nhỏ, mạch LC (`[ELK]` §6.4), dao động ổn định quanh cân bằng |
| $\ddot x + \omega^2 x = f(t)$ | nghiệm riêng theo $f(t)$ + nghiệm thuần nhất ở trên (nguyên lý chồng chập, tuyến tính) | Dao động cưỡng bức, mạch AC quá độ |
| $\ddot x + 2\beta\dot x+\omega^2x=0$ (mở rộng tự nhiên — RLC nối tiếp có điện trở) | Phương trình đặc trưng $\lambda^2+2\beta\lambda+\omega^2=0$; 3 chế độ: quá tắt dần ($\beta>\omega$), tới hạn ($\beta=\omega$), dưới tắt dần dao động ($\beta<\omega$) | Mạch RLC có dao động tắt dần — mở rộng hợp lý cần biết dù `[ELK]` chỉ nêu LC lý tưởng và AC ổn định |
| $I\dot\varphi + $ mô-men ma sát $=$ mô-men ngoài | Tương tự dạng 1 hoặc 2 tuỳ mô-men ma sát tuyến tính hay hằng | Vật rắn quay có ma sát nhớt/khô |

**Thủ tục xử lý ODE bậc nhất tổng quát** (đúng như footnote toán học của `[ELK]`, chú thích 7): với $\tau\dot x+x=f(t)$, nghiệm tổng quát = nghiệm riêng của phương trình không thuần nhất + nghiệm tổng quát của phương trình thuần nhất; nếu $f=$const thì nghiệm riêng chính là $f$ (điểm cân bằng).

### 9.3 Phương pháp đồ thị cho phương trình siêu việt (không có nghiệm dạng đóng)

Khi hệ có phần tử phi tuyến (diode, điện trở phụ thuộc nhiệt độ...), phương trình kết hợp Kirchhoff trở thành **siêu việt** (không giải đại số được). Thủ tục chuẩn (`[ELK]` §1.5, "Graafiline meetod"):

1. Viết phương trình tuyến tính "phần mạch còn lại nhìn từ 2 cực phần tử phi tuyến": $IR=\mathcal E - U$ (đường thẳng trên trục $U$–$I$).
2. Vẽ đường thẳng này (2 điểm: $U=0,I=\mathcal E/R$ và $I=0,U=\mathcal E$) chồng lên đồ thị đặc trưng Vôn–Ampe của phần tử phi tuyến (cho sẵn hoặc đo được).
3. **Giao điểm hai đường** chính là nghiệm — đọc trực tiếp từ đồ thị, hoặc nội suy tuyến tính giữa 2 điểm lưới gần nhất nếu cần độ chính xác số.
4. Nếu có **nhiều phần tử phi tuyến giống nhau nối tiếp/song song**: cộng đặc trưng V-A theo đúng trục tương ứng (nối tiếp: cộng theo $U$ tại mỗi $I$; song song: cộng theo $I$ tại mỗi $U$) trước khi tìm giao điểm.

### 9.4 Kiểm tra thứ nguyên **trong khi** giải (không đợi đến B10)

Sau **mỗi** bước biến đổi đại số quan trọng (không chỉ ở bước cuối), lướt nhanh: các số hạng cộng/trừ với nhau có cùng thứ nguyên không? Đây là cách phát hiện lỗi đại số sớm, tiết kiệm thời gian so với việc chỉ kiểm tra ở B10.

### 9.5 Khi nào chuyển sang xấp xỉ/số thay vì tìm nghiệm đóng

Nếu sau khi thử các kỹ thuật 9.1–9.3 mà phương trình vẫn không đưa về dạng đóng được (ví dụ tích phân không có hàm sơ cấp) — đây chính là tín hiệu quay lại **Trụ cột D** (B6): tìm $\varepsilon$ (thường bài đã cho $\ll$ hoặc $\gg$) và dùng Định lý D2 khai triển tiệm cận, thay vì cố tìm nghiệm đóng chính xác không tồn tại.

---

## B10 — KIỂM TRA NGƯỢC (Verification Protocol)

Không bao giờ nộp bài mà bỏ qua bước này — đây là bước tách biệt điểm 10 và điểm 7-8.

1. **Kiểm tra thứ nguyên** — mọi số hạng cộng với nhau phải cùng đơn vị.
2. **Kiểm tra giới hạn đặc biệt** (idea 37): cho tham số → 0 hoặc → ∞ hoặc → giá trị đối xứng đặc biệt, so với trực giác/công thức đã biết (ví dụ μ→0 phải cho lại kết quả "không ma sát"; ε→1 (chân không) phải cho lại kết quả tĩnh điện chân không).
3. **Kiểm tra dấu** — lực/mô-men/dòng điện có đúng chiều vật lý hợp lý không?
4. **Kiểm tra qua định luật bảo toàn độc lập** — nếu bạn dùng Newton để giải, thử thay số vào biểu thức năng lượng xem có bảo toàn không (hoặc ngược lại).
5. **Kiểm tra bậc tự do** — số phương trình đã dùng có đúng bằng f_eff không? Nếu dư 1 phương trình mà vẫn ra nghiệm hợp lý — có khả năng bạn đã vô tình lặp một ràng buộc; nếu thiếu 1 phương trình mà "đoán" ra đáp số — có khả năng bài có nghiệm nhưng lời giải chưa chặt chẽ, thiếu lập luận cho điểm.
6. **Kiểm tra tính đối xứng của đáp số** — nếu bài có đối xứng hoán đổi 2 vật/2 nhánh mạch, đáp số có tôn trọng đúng đối xứng đó không (ví dụ hoán đổi $R_1\leftrightarrow R_2$ và $1\leftrightarrow 2$ trong công thức có cho lại đúng công thức hoán đổi)?
7. **Kiểm tra bậc của gần đúng** — nếu đã dùng Định lý D2, bậc cao nhất giữ lại có nhất quán với bậc $\varepsilon$ mà bài yêu cầu độ chính xác không (không giữ thừa/thiếu bậc)?

---

## PHẦN 6 — MẠCH ĐIỆN: BỘ CÔNG CỤ ĐẦY ĐỦ (bổ sung trọn vẹn phần `[ELK]` còn thiếu)

> `[ELK]` trình bày rất kỹ Kirchhoff, phương pháp thế nút, phương pháp dòng vòng, định lý Millman, Thévenin ở mức cơ bản — nhưng **không** hệ thống hoá thành một **cây quyết định** đầy đủ, và bỏ ngỏ một số kỹ thuật (siêu vị trí có điều kiện, mạng vô hạn tổng quát, AC phức số một cách bài bản). Phần này lấp đầy khoảng trống đó.

### 6.A Cây quyết định chọn phương pháp phân tích mạch DC

| # | Dấu hiệu | Phương pháp | Vì sao / thủ tục |
|---|---|---|---|
| 1 | Mạch đơn giản, có thể rút gọn dần bằng nối tiếp/song song | **Rút gọn tương đương trực tiếp** | Nhanh nhất khi khả thi |
| 2 | Mạch có cấu trúc **đối xứng** (cầu cân bằng, hình khối lập phương điện trở, mạng tam giác) | **Phương pháp đối xứng** (Bảng C mục 5): tìm các nút cùng điện thế bằng phép quay/phản chiếu mạch, rồi chập/cắt các nút đó | `[ELK]` §1.4; xem thủ tục chi tiết ở 6.C |
| 3 | Mạch không rút gọn được bằng 1–2, có $n$ nút | **Phương pháp thế nút (node-potential)**: chọn 1 nút làm gốc ($\varphi=0$), viết Kirchhoff I tại $n-1$ nút còn lại theo hiệu thế các nhánh, giải hệ tuyến tính $n-1$ ẩn | Luôn dùng được — thuật toán **G** tuyệt đối, tương đương giải $Ax=b$ |
| 4 | Mạch có ít vòng độc lập hơn số nút (mạch "nhiều nhánh song song, ít vòng") | **Phương pháp dòng vòng (mesh current)**: chọn dòng vòng độc lập cho $b-n+1$ vòng, viết Kirchhoff II | Hiệu quả hơn thế nút khi số vòng độc lập $<$ số nút$-1$ |
| 5 | Chỉ cần dòng/áp qua **1 nhánh cụ thể**, mạch còn lại tuyến tính | **Định lý Thévenin/Norton** (xem 6.B) — rút gọn toàn bộ phần còn lại về 1 nguồn + 1 điện trở | Tiết kiệm nhất khi chỉ cần 1 đại lượng, đặc biệt nếu nhánh đó sẽ thay đổi (ví dụ tải thay đổi) |
| 6 | Mạch có **nhiều nguồn**, muốn tách ảnh hưởng từng nguồn | **Nguyên lý chồng chập (superposition)**: tính riêng dòng do từng nguồn gây ra (ngắn mạch các nguồn còn lại), cộng đại số | Chỉ đúng cho mạch **tuyến tính** (chỉ điện trở/nguồn lý tưởng — KHÔNG áp dụng khi có diode) |
| 7 | Nhiều nguồn EMF mắc song song vào 2 nút chung | **Định lý Millman** — công thức trực tiếp $U=\dfrac{\sum \mathcal E_i/R_i}{\sum 1/R_i}$ | Trường hợp đặc biệt của thế nút với 2 nút |
| 8 | Mạng **tuần hoàn vô hạn** (thang điện trở lặp lại) | **Phương trình tự-tương tự (self-similarity, Trụ cột C mục 5 — co giãn tỉ lệ)**: đặt $R_{\text{tđ}}$ là điện trở tương đương toàn mạng; thêm/bớt 1 mắt không đổi $R_{\text{tđ}}$ ⇒ phương trình đại số cho chính $R_{\text{tđ}}$ | `[ELK]` §1.4 "Lõpmatud perioodilised ahelad" |
| 9 | Mạng có tính đối xứng **hình học cao nhưng dòng điện không đối xứng bằng** (mạng phẳng/khối vô hạn) | **Nguyên lý chồng chập theo dòng bơm vào/lấy ra** — bơm dòng $I$ vào 1 nút, rút ra ở vô cực (đối xứng toả tia đều); chồng chập 2 bài toán này để tái tạo bài toán gốc "bơm ở A, rút ở B" | `[ELK]` ul 31, 32 (mạng vô hạn) |
| 10 | Bài dùng khái niệm **điện trở âm** hình thức | Xem đoản mạch = ghép nối tiếp $(+R)$ và $(-R)$ cùng độ lớn; hở mạch = ghép song song $(+R)$ và $(-R)$ — công cụ đại số để "sửa" mạch | `[ELK]` §1.4 cuối |

### 6.B Định lý Thévenin/Norton — thủ tục xác định tham số (2 bước chuẩn, không cần đoán)

Mọi mạch tuyến tính 2 cực (chỉ gồm điện trở + nguồn EMF lý tưởng) nhìn từ 2 cực ra ngoài **tương đương** với 1 nguồn EMF $\mathcal E_{\text{th}}$ nối tiếp điện trở trong $r_{\text{th}}$. Xác định 2 tham số bằng **2 trường hợp giới hạn** (không cần biến đổi mạch phức tạp):

1. **Hở mạch** (2 cực không nối gì, $I=0$): $\mathcal E_{\text{th}} = U_{\text{hở mạch}}$ (đo/tính hiệu thế 2 cực khi để hở).
2. **Đoản mạch** (nối tắt 2 cực): $I_{\text{ngắn mạch}} = \mathcal E_{\text{th}}/r_{\text{th}} \Rightarrow r_{\text{th}} = \mathcal E_{\text{th}}/I_{\text{ngắn mạch}}$.

Đây là thủ tục **G** — luôn dùng được, không phụ thuộc độ phức tạp mạch bên trong (miễn tuyến tính).

### 6.C Thủ tục phát hiện đối xứng mạch một cách hệ thống (không case-by-case)

1. Vẽ lại mạch dưới dạng đồ thị (nút + nhánh), bỏ qua hình dạng vẽ trên giấy.
2. Thử từng phép trong 6 phép biến đổi của §4.1 (đặc biệt phép **hoán vị nhãn nút** và **phản xạ gương**) lên chính **đồ thị mạch cộng giá trị điện trở/nguồn trên từng nhánh** — hỏi: "sau phép biến đổi, đồ thị có nhãn-giống-hệt đồ thị gốc không?"
3. Nếu có, các nút được hoán đổi cho nhau bởi phép đối xứng đó **buộc phải** cùng điện thế (nếu phép đối xứng không đảo cực nguồn) hoặc điện thế **đối nhau qua 1 mốc** (nếu phép đối xứng đi kèm đảo cực nguồn — Bảng C, dòng "đảo dấu 1 biến").
4. Cùng điện thế ⇒ có thể **chập** 2 nút đó lại (không đổi dòng điện trong mạch) hoặc **cắt** nhánh nối 2 nút đó (nếu có nhánh nối trực tiếp) — cả hai thao tác đều **giữ nguyên chức năng điện của mạch** (`[ELK]` §1.4).
5. Mạch sau khi chập/cắt luôn **đơn giản hơn nghiêm ngặt** (ít nút/nhánh độc lập hơn) — lặp lại bước 2 nếu còn đối xứng dư.

### 6.D Mạch tụ điện & bảo toàn điện tích

| Tình huống | Công cụ |
|---|---|
| Tụ nối tiếp/song song, không đổi theo thời gian | Công thức tương đương chuẩn: nối tiếp $\frac1C=\sum\frac1{C_i}$; song song $C=\sum C_i$ |
| Đóng/mở khóa K làm điện tích phân bố lại | **Bảo toàn điện tích tại mỗi "đảo" cô lập về điện** (nút/nhóm nút không có đường thoát ra ngoài) — viết phương trình tổng điện tích tại đảo đó không đổi qua biến cố |
| Hỏi nhiệt lượng toả ra trên điện trở trong quá trình nạp/phóng qua $R$ | **Không** tích phân $I^2R\,dt$ trực tiếp trừ khi bắt buộc — dùng bảo toàn năng lượng dạng tổng quát: $\Pi_{\text{đầu}}+A_{\text{nguồn}} = \Pi_{\text{cuối}}+Q_{\text{toả}}$ (`[ELK]` phương trình (2), §2.2) |
| Phần tử phi tuyến (diode) trong quá trình phóng tụ | Vẫn dùng bảo toàn năng lượng dạng trên, với $A$/$Q$ tính qua tích $U\cdot q$ tại từng đoạn tuyến tính của đặc trưng diode (`[ELK]` ul 47) |

### 6.E Mạch RC/RL quá độ — công thức chủ đạo

$$U(t) = \mathcal E + (U_0-\mathcal E)e^{-t/\tau},\qquad \tau=RC\ \text{hoặc}\ \tau=L/R.$$

Đây là **chồng chập** của nghiệm dừng ($U=\mathcal E$, đạt khi $t\to\infty$) và nghiệm thuần nhất tắt dần từ độ lệch ban đầu $(U_0-\mathcal E)$ — hệ quả trực tiếp của Định lý D3 (§5.4) và Bảng 9.2 dòng 2.

**So sánh thang thời gian** ($T$ chu kỳ tín hiệu ngoài, $\tau=RC$):
- $T\gg\tau$: hệ **chuẩn tĩnh** với tụ — tụ "theo kịp" biến thiên chậm, coi như tụ luôn ở trạng thái cân bằng tức thời với nguồn tại mỗi thời điểm.
- $T\ll\tau$: tụ "đóng băng" — với thành phần biến thiên nhanh, tụ hoạt động gần như hở mạch (dòng biến thiên nhanh không kịp nạp/xả đáng kể qua điện trở lớn).

### 6.F Mạch LC/RLC dao động

- LC lý tưởng: $\ddot Q+\omega^2Q=0$, $\omega=1/\sqrt{LC}$ — tương tự hoàn toàn dao động điều hoà cơ học (khớp Bảng 9.2 dòng 3; xem thêm ánh xạ cơ-điện ở Bảng 5.B.3).
- RLC nối tiếp có dao động tắt dần: xem Bảng 9.2 dòng 5 — mở rộng tự nhiên, cần nắm 3 chế độ nghiệm.
- Cộng hưởng RLC ổn định AC: xem 6.H.

### 6.G Định lý xếp chồng SIN — cộng hai dao động cùng tần số khác pha

Với mạch có 2 phần tử ghép nối tiếp/song song trong chế độ AC, tổng 2 hàm sin cùng tần số:
$$A_1\cos(\omega t+\varphi_1)+A_2\cos(\omega t+\varphi_2)=A\cos(\omega t+\varphi),$$
$$A^2=A_1^2+A_2^2+2A_1A_2\cos(\varphi_2-\varphi_1).$$
Đây **chính là** phép cộng véc-tơ hình học (giản đồ Fresnel) — nhưng khi có **từ 3 phần tử trở lên hoặc pha lệch tuỳ ý**, dùng trực tiếp phương pháp phức số ở mục H thay vì cộng hình học nhiều lần.

### 6.H Phương pháp phức số (Complex Impedance) — thủ tục chuẩn 4 bước

Đây là một minh hoạ tường minh của **B7 — đổi ngôn ngữ chi phối**: khi mạch ở chế độ xoay chiều ổn định, "ngôn ngữ" tối ưu là đại số phức, biến ODE thành đại số tuyến tính thông thường:

1. **Đổi biến:** mọi $x(t)=A\cos(\omega t+\varphi)$ ↔ số phức $\tilde x = Ae^{i\varphi}$.
2. **Đổi phần tử:** điện trở $R$ giữ nguyên; tụ điện $\tilde Z_C=1/(i\omega C)$; cuộn cảm $\tilde Z_L = i\omega L$.
3. **Giải mạch y hệt mạch một chiều** (Kirchhoff, thế nút, dòng vòng, Thévenin — mọi công cụ ở 6.A đều dùng lại nguyên vẹn, chỉ thay số thực bằng số phức).
4. **Đổi ngược:** biên độ thực = $|\tilde x|$; pha thực = $\arg\tilde x$. Công suất trung bình: $P=\frac12\operatorname{Re}(\tilde U\tilde I^*)$ (dùng giá trị biên độ) hoặc $P=\operatorname{Re}(\tilde U_{\text{eff}}\tilde I_{\text{eff}}^*)$ (dùng giá trị hiệu dụng, không có hệ số $\frac12$).

**Cộng hưởng RLC:** $\omega_{\text{res}}=1/\sqrt{LC}$ không đổi dù có $R$ hay không (vì $R$ không ảnh hưởng đến pha lệch giữa $L$ và $C$ triệt tiêu nhau); $R$ chỉ ảnh hưởng **độ rộng** đỉnh cộng hưởng (`[ELK]` §6.4, Hình 62).

### 6.I Phần tử phi tuyến (diode) — xem §9.3 (đã trình bày ở B9)

### 6.J Bảng quyết định tổng hợp Phần 6 (một trang)

```
MẠCH ĐIỆN — CÂU HỎI GÌ?
│
├─ DC, rút gọn được ngay? ─────────────────────► 6.A #1
├─ DC, có đối xứng? ────────────────────────────► 6.C
├─ DC, nhiều nút, không đối xứng? ──────────────► 6.A #3 (thế nút)
├─ DC, chỉ cần 1 nhánh, mạch còn lại phức tạp? ──► 6.B (Thévenin)
├─ DC, nhiều nguồn, cần tách ảnh hưởng? ─────────► 6.A #6 (chồng chập)
├─ Mạng vô hạn tuần hoàn? ───────────────────────► 6.A #8
├─ Có tụ, hỏi theo THỜI GIAN? ───────────────────► 6.D, 6.E
├─ Có L/C, dao động tự do? ──────────────────────► 6.F
├─ Xoay chiều ổn định (steady-state AC)? ────────► 6.H (phức số)
└─ Có diode/phần tử phi tuyến? ───────────────────► 9.3 (đồ thị) + 6.D (năng lượng)
```

---

## PHẦN 7 — CÁC THỦ THUẬT CHUYÊN BIỆT CỦA ĐIỆN–TỪ TRƯỜNG (bổ sung để tránh case-by-case)

### 7.A Phương pháp ảnh điện (image charge) — danh sách hữu hạn các trường hợp chuẩn

Nguyên tắc: thay pháp tuyến điện tích cảm ứng trên vật dẫn bằng (các) điện tích "ảnh" giả định đặt **bên trong** vật dẫn sao cho bề mặt vật dẫn vẫn là mặt đẳng thế đúng như thực tế. Đây là bài toán **duy nhất nghiệm** (theo định lý duy nhất nghiệm của phương trình Laplace với điều kiện biên Dirichlet) — nên **hễ đoán đúng dạng ảnh và kiểm tra thoả điều kiện biên, nghiệm chắc chắn đúng**, không cần biện luận gì thêm.

| Hình học vật dẫn | Vị trí + độ lớn điện tích ảnh | Nguồn |
|---|---|---|
| Mặt phẳng dẫn vô hạn, nối đất, điện tích $q$ cách mặt $h$ | 1 ảnh $-q$ đối xứng gương qua mặt phẳng, cách mặt $h$ phía bên kia | `[ELK]` §3.7, ul 99, 103 |
| Mặt cầu dẫn nối đất bán kính $R$, điện tích $q$ cách tâm $d$ ($d>R$) | 1 ảnh $q' = -Rq/d$ tại khoảng cách $R^2/d$ từ tâm (cùng phía với $q$) | `[ELK]` §3.7, ul 106 |
| Mặt cầu dẫn **cô lập, tích điện $Q_0$** (không nối đất) | Ảnh như trên **cộng thêm** 1 điện tích điểm $Q_0-q'$ đặt tại tâm cầu (để tổng điện tích đúng $Q_0$) | `[ELK]` ul 107 |
| Hai môi trường điện môi phẳng tiếp giáp, điện tích $q$ trong môi trường 1 | Ảnh $q'=\frac{\varepsilon_1-\varepsilon_2}{\varepsilon_1+\varepsilon_2}q$ (nhìn từ môi trường 1); và điện tích hiệu dụng $q''=\frac{2\varepsilon_1}{\varepsilon_1+\varepsilon_2}q$ (nhìn từ môi trường 2) | `[ELK]` §3.9, ul 114 |
| Siêu dẫn phẳng vô hạn (Meissner, $B=0$ trong siêu dẫn), dòng thẳng song song cách mặt $h$ | Ảnh dòng $-I$ đối xứng gương, để $B_n=0$ tại mặt | `[ELK]` §4.8, ul 134 |

**Thủ tục kiểm tra bắt buộc sau khi đoán ảnh (2 bước, thay thế biện luận trực giác):** (1) $E_\tau=0$ hoặc $\varphi=$const trên toàn bộ mặt vật dẫn thật (kiểm tra tại **ít nhất 2 điểm không đối xứng với nhau** trên mặt, không chỉ 1 điểm — để chắc chắn không phải trùng hợp); (2) tổng điện tích ảnh $+$ điện tích thật phải khớp điều kiện đề bài (nối đất: không ràng buộc gì thêm; cô lập: tổng điện tích cảm ứng $=$ giá trị cho trước).

### 7.B Điều kiện biên tổng quát tại mặt phân cách 2 môi trường (thay thế ghi nhớ rời rạc)

| Đại lượng | Tính chất qua mặt phân cách | Điều kiện |
|---|---|---|
| $D_n$ (điện) | Liên tục nếu không có điện tích tự do mặt; nhảy bậc $=\sigma_{\text{tự do}}$ nếu có | `[ELK]` §3.8 |
| $E_\tau$ (điện) | Luôn liên tục (hệ quả $\oint \vec E\cdot d\vec l=0$ tĩnh điện) | `[ELK]` §3.8 |
| $B_n$ (từ) | Luôn liên tục (không có "điện tích từ") | `[ELK]` §4.6 |
| $H_\tau$ (từ) | Liên tục nếu không có dòng tự do mặt; nhảy bậc theo dòng mặt nếu có | `[ELK]` §4.6 |

**Thủ tục chuẩn cho bài "vật liệu đồng nhất trong trường ngoài đều":** giả định phân cực/từ hoá đều $\Rightarrow$ trường trong vật cũng đều $\Rightarrow$ dùng 4 điều kiện trên tại bề mặt để lập hệ đại số tuyến tính cho các hằng số trường trong/ngoài — **không** cần biết chi tiết phân bố điện tích/dòng liên kết bên trong (đây chính là tinh thần Định lý C2 áp dụng cho vật liệu).

### 7.C Mô-men lưỡng cực & khai triển đa cực — khi nào dùng

Khi khoảng cách khảo sát $r$ lớn hơn nhiều kích thước hệ nguồn ($r\gg$ kích thước hệ): khai triển $\varphi(r)$ theo luỹ thừa $1/r$ (Định lý D2 áp dụng cho khai triển không gian thay vì thời gian!). Bậc thấp nhất khác 0 chi phối: điện tích tổng ($1/r$) nếu khác 0; nếu bằng 0, mô-men lưỡng cực ($1/r^2$ cho thế, $1/r^3$ cho trường).

### 7.D Hỗ cảm & mạch ghép từ

$M_{12}=M_{21}$ (chứng minh bằng tính công tổng cộng cần thiết để thiết lập dòng trong 2 mạch — độc lập thứ tự thiết lập, `[ELK]` ul 145) — đây là một ví dụ khác của **Định lý C1** áp dụng cho hệ có 2 tọa độ suy rộng điện $Q_1,Q_2$ với $L=\frac12 L_1\dot Q_1^2+\frac12L_2\dot Q_2^2+M\dot Q_1\dot Q_2-V(Q_1,Q_2)$ — tính đối xứng của số hạng ghép $M\dot Q_1\dot Q_2$ trong $L$ chính là lý do $M_{12}=M_{21}$, tương tự cách ma trận Hess đối xứng trong cơ học nhiều DOF.

---

## PHẦN 8 — THUẬT TOÁN TỔNG HỢP (Master Flowchart — dùng trong 60 giây đầu đọc đề)

```
┌─────────────────────────────────────────────────────────────────────┐
│  B0: Quét đề — gạch chân số liệu, tính từ, động từ, câu hỏi.         │
│      Tra Từ điển B3 (§3.2) cho MỌI tính từ.                          │
└───────────────────────────────┬───────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────┐
│  B1: Thử hệ quy chiếu theo thứ tự bảng §1.2 (6 ứng viên).            │
│      Chọn hệ có ít phép chiếu ràng buộc nhất.                        │
└───────────────────────────────┬───────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────┐
│  B2+B3: Đếm f_raw (Bảng 2.A) → trừ ràng buộc hình học (Bảng 2.B,     │
│         kiểm tra lăn bằng Định lý B nếu nghi ngờ) → f_eff (tạm).     │
└───────────────────────────────┬───────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────┐
│  B4: Săn đối xứng — thử 6 phép biến đổi (§4.1) + Bảng C.             │
│      GHI LẠI đối xứng tìm được nhưng CHƯA rút gọn tọa độ vội!        │
└───────────────────────────────┬───────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────┐
│  B5: Chọn q_1..q_f theo 4 tiêu chí §5.B.2 + thực đơn §5.B.3.         │
│      Tuân thủ cảnh báo §5.3 (không rút gọn sai bằng đại lượng        │
│      bảo toàn có đạo hàm bậc nhất trước khi lập L).                  │
└───────────────────────────────┬───────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────┐
│  B6: Có ε cho tường minh (≪, ≫)? → Định lý D2/D3.                    │
│      Không có? → Định lý D1 (Buckingham) suy ra ε.                   │
└───────────────────────────────┬───────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────┐
│  B7: TRA CÂY QUYẾT ĐỊNH A/B/C/D (§7.1–7.4) hoặc Phần 6 (mạch).       │
│      ⇒ Đây là lúc bài toán CHÍNH THỨC trở thành bài Toán thuần túy.  │
└───────────────────────────────┬───────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────┐
│  B8: Tra bảng điều kiện biên/đầu (§B8) cho MỌI biến cố/mốc thời gian.│
└───────────────────────────────┬───────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────┐
│  B9: Giải — dùng hộp công cụ §9.1–9.5 (đại số/ODE/đồ thị/số).        │
└───────────────────────────────┬───────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────┐
│  B10: Kiểm tra ngược — 7 bước §B10. KHÔNG BỎ QUA.                    │
└─────────────────────────────────────────────────────────────────────┘
```

---

## PHẦN 9 — VÍ DỤ ÁP DỤNG ĐẦY ĐỦ (chứng minh tính khả thi cho học sinh trực giác trung bình)

### Ví dụ 1 (Cơ học) — `[MEH, pr 26]`: khối $m$ trên nêm góc $\alpha$, khối lượng $M$, nêm tự do trượt trên sàn trơn, khối $m$ nối dây qua ròng rọc ở đỉnh nêm, dây buộc vào tường ngang. Tìm gia tốc nêm.

- **B0:** gạch chân "trơn" (không ma sát, mọi mặt), "dây" (không giãn), "ròng rọc" (lý tưởng — Từ điển B3). Biến mục tiêu: gia tốc nêm $a$.
- **B1:** thử hệ phòng thí nghiệm trước (bảng §1.2 mục 1) — vì cả nêm lẫn khối đều chuyển động, không có "vật nền đứng yên" hiển nhiên; giữ hệ phòng thí nghiệm, dùng toạ độ suy rộng để tránh phải đổi hệ quy chiếu.
- **B2–B3:** 2 vật rắn/chất điểm ($M$: 1 DOF ngang trên sàn trơn — thực ra nêm là vật rắn 3 DOF nhưng ràng buộc "trượt ngang trên sàn, không lật" chỉ để 1 DOF hữu ích $\xi$; $m$: 2 DOF thô). Ràng buộc: $m$ luôn tiếp xúc mặt nêm (1 ràng buộc: khoảng cách vuông góc = 0, Bảng 2.B) + dây không giãn nối $m$ qua ròng rọc tới tường (1 ràng buộc). Tổng khử: 2. $f_{\text{raw}}=3+2=5$ (đếm dư an toàn), $f_{\text{eff}}=5-2=3$... nhưng cần thêm ràng buộc dây cố định 1 đầu vào tường: đầu dây tại tường không di chuyển — đây chính là điều làm bài có đúng **1 DOF hiệu dụng** sau khi tính kỹ hình học (chi tiết hình học dây/ròng rọc tự nó là 1 ràng buộc thêm liên hệ vị trí tương đối của $m$ trên mặt nêm với $\xi$) — kết quả cuối: $f_{\text{eff}}=1$, lấy $\xi$ = độ dịch nêm làm toạ độ suy rộng duy nhất (khớp thực đơn §5.B.3 dòng 1).
- **B4:** không có tịnh tiến toàn cục (sàn cố định phá đối xứng tịnh tiến ngang của hệ *nêm+khối*, nhưng lưu ý xung lượng ngang toàn hệ *nêm+khối+Trái Đất qua sàn* không bảo toàn vì sàn tác dụng phản lực ngang lên nêm — không có đối xứng tịnh tiến hữu ích ở đây); có đối xứng tịnh tiến thời gian (không lực nào phụ thuộc $t$ tường minh) ⇒ năng lượng bảo toàn — ghi nhận, dùng ở B7.
- **B5:** $\xi$ = độ dịch nêm (theo thực đơn). Vị trí khối $m$ so với nêm suy ra tuyến tính từ ràng buộc dây.
- **B6:** không có $\varepsilon$ nào được nêu — bỏ qua trụ cột D cho bài này.
- **B7:** tra Cây quyết định A, dòng **A1** ($f_{\text{eff}}=1$, lực bảo toàn (trọng lực + căng dây lý tưởng không sinh công vào hệ vì dây không giãn + phản lực pháp tuyến không sinh công), không cần tìm lực căng cụ thể) ⇒ dùng **Method 6**: viết $T(\xi,\dot\xi)$ và $\Pi(\xi)$, suy $M(\xi)$, giải $\ddot\xi=-\Pi'(\xi)/M(\xi)$.
- **B8:** không có biến cố thời gian đặc biệt trong bài này (hỏi gia tốc tức thời từ trạng thái tổng quát, không cần điều kiện đầu cụ thể).
- **B9:** đại số thuần tuý — khai triển $T,\Pi$ theo $\xi,\dot\xi$ (dùng hình học tam giác cho vận tốc tương đối), đạo hàm.
- **B10:** kiểm tra giới hạn $\alpha\to0$ (mặt nêm phẳng ngang, dây không còn tác dụng kéo theo phương ngang hữu ích) và $M\to\infty$ (nêm không di chuyển) phải cho lại các trường hợp biết trước.

### Ví dụ 2 (Tĩnh điện) — `[ELK, ul 104]`: quả cầu kim loại bán kính $R$ đặt trong điện trường đều $\vec E_0$. Tìm mật độ điện tích cảm ứng và trường bên ngoài.

- **B0:** "kim loại" → vật dẫn (Từ điển B3: $\varphi=$const trên mặt, $E$ trong $=0$); "đều" → $\vec E_0$ không đổi theo vị trí.
- **B1:** không cần đổi hệ quy chiếu (bài tĩnh).
- **B2–B3:** đây là bài toán trường liên tục, không phải hệ hữu hạn chiều — B2/B3 cơ học không áp dụng trực tiếp; thay vào đó dùng **điều kiện biên** (§7.B): $\varphi=$const trên mặt cầu.
- **B4:** không có đối xứng cầu hoàn toàn (vì $\vec E_0$ phá đối xứng cầu tổng thể), nhưng vẫn có đối xứng **trụ quanh trục song song $\vec E_0$** — tra Bảng C mục 4: dạng nghiệm $\vec E$ phải bất biến dưới quay quanh trục này ⇒ nghiệm chỉ phụ thuộc $r,\theta$ (góc với trục), không phụ thuộc góc phương vị — giảm mạnh số ẩn hàm cần tìm.
- **B5:** không có "tọa độ suy rộng" theo nghĩa cơ học; "biến suy rộng" ở đây là **dạng hàm thử** cho $\varphi$: theo gợi ý đối xứng lưỡng cực (Phần 7.C) vì $\vec E_0$ đều tương đương nguồn ở vô cực, thử nghiệm dạng "trường đều + trường lưỡng cực cảm ứng".
- **B6:** không có $\varepsilon$ — nghiệm chính xác cho mọi $R$ (bài không xấp xỉ).
- **B7:** tra Cây quyết định C, dòng **C4**: vật dẫn hình học đơn giản (mặt cầu) trong trường ngoài đều — dùng chính kỹ thuật "quả cầu tương đương lưỡng cực cảm ứng" (`[ELK]` gợi ý dùng lại kết quả bài lưỡng cực ul 94) thay vì ảnh điện kiểu điểm.
- **B8:** biên: $E_r,E_\theta \to E_0\cos\theta, -E_0\sin\theta$ khi $r\to\infty$ (trường trở về đều ở xa); $\varphi=$const tại $r=R$.
- **B9:** đại số tuyến tính giải 2 hệ số chưa biết trong dạng thử (hệ số trường đều + hệ số lưỡng cực) bằng cách áp 2 điều kiện biên.
- **B10:** kiểm tra $R\to0$ (không còn vật dẫn, trường phải về đúng $\vec E_0$ đều — khớp vì số hạng lưỡng cực $\to 0$); kiểm tra $\sigma(\theta)=3\varepsilon_0E_0\cos\theta$ tích phân toàn mặt cầu phải bằng 0 (vật dẫn trung hoà, không có điện tích tự do thêm vào) — $\int\cos\theta\,dS=0$ do đối xứng lẻ, khớp.

### Ví dụ 3 (Mạch + phi tuyến) — `[ELK, ul 47]`: tụ $C=10\,\mu F$ nạp đến $U_0=6\,V$, phóng qua diode (đặc trưng cho ở đồ thị, $U_d=1\,V$). Tìm năng lượng toả ra dạng tia lửa (đóng khoá K).

- **B0:** "diode" → phi tuyến (Từ điển B3); hỏi **năng lượng**, không hỏi $I(t)$ hay $U(t)$ tường minh.
- **B1:** không cần đổi hệ quy chiếu.
- **B2–B3:** hệ điện — 1 "toạ độ suy rộng điện" là điện tích $Q$ trên tụ; ràng buộc: bảo toàn điện tích qua mạch vòng kín (đảo cô lập).
- **B4:** không có đối xứng không gian hữu ích (chỉ 1 vòng); về thời gian: không bảo toàn năng lượng đơn giản vì diode phi tuyến (tiêu tán ở dạng tia lửa) — không dùng B4 ở đây.
- **B5:** $Q(t)$ là biến duy nhất, nhưng vì diode phi tuyến, phương trình vi phân cho $Q(t)$ không có nghiệm đóng đơn giản (đặc trưng diode không cho ở dạng hàm sơ cấp tường minh).
- **B6:** không có $\varepsilon$ nêu tường minh — không cần trụ cột D.
- **B7:** **đây chính là lúc B7 phát huy tác dụng rõ nhất**: vì đề hỏi **năng lượng tổng** (không hỏi diễn biến theo thời gian), và mạch có phần tử phi tuyến (ODE không giải đóng được) — tra Cây quyết định D (Phần 6.D, dòng "hỏi nhiệt lượng...") ⇒ **KHÔNG** giải ODE, dùng trực tiếp **bảo toàn năng lượng dạng tổng quát** `[ELK]` phương trình (2): $\Pi_{\text{đầu}} = \Pi_{\text{cuối}} + Q_{\text{toả}}$, với $\Pi=\frac{CU^2}{2}$ trước/sau, và với diode có ngưỡng $U_d$: điện tích chảy qua đến khi $U_C=U_d$ (điều kiện dừng — diode ngừng dẫn khi $U<U_d$, tra Bảng B8 dòng diode).
- **B8:** trạng thái cuối: $U_C\to U_d$ (không phải $0$, vì diode ngừng dẫn khi hiệu thế xuống dưới ngưỡng — đây là điều kiện biên đặc thù của phần tử phi tuyến, phải tra đúng Từ điển B3/Bảng B8 dòng "diode lý tưởng").
- **B9:** đại số: $\Pi_{\text{đầu}}=\frac12CU_0^2$; $\Pi_{\text{cuối}}=\frac12CU_d^2$; điện tích đã chuyển $q_{\text{qua}}=C(U_0-U_d)$; công "tổn hao" trên diode với sụt áp không đổi $U_d$: $A_{\text{diode}}=U_d\cdot q_{\text{qua}}$; năng lượng toả ra ở tia lửa = phần còn lại: $Q_{\text{toả}}=\Pi_{\text{đầu}}-\Pi_{\text{cuối}}-A_{\text{diode}}=\frac12C(U_0-U_d)^2$.
- **B10:** thay số $C=10\mu F$, $U_0=6V$, $U_d=1V$: $Q_{\text{toả}}=\frac12\cdot10^{-5}\cdot25\approx1.25\times10^{-4}J=125\,\mu J$ — khớp chính xác đáp số gốc "$Q\approx125\,\mu J$". Kiểm tra giới hạn $U_d\to0$ (diode lý tưởng hoàn toàn): $Q_{\text{toả}}\to\frac12CU_0^2$ — đúng bằng toàn bộ năng lượng ban đầu, hợp lý vì không phần tử nào tiêu hao ngoài "tia lửa".

**Nhận xét sư phạm:** cả 3 ví dụ cho thấy: (a) mỗi bước B0–B10 luôn có nội dung tường minh, tra bảng được — không có bước nào đòi hỏi "linh cảm bất chợt"; (b) bước **B7** (chọn ngôn ngữ chi phối) là bước quyết định tốc độ và độ chính xác — ví dụ 3 minh hoạ rõ nhất: một học sinh cố giải ODE phi tuyến trực tiếp sẽ mất rất nhiều thời gian hoặc bế tắc, trong khi tra đúng cây quyết định dẫn thẳng đến phương pháp năng lượng, biến bài toán khó thành 3 dòng đại số.

---

## PHẦN 10 — KẾT LUẬN 

### 10.1 Tóm tắt tính "Tổng quát" đã đạt được

| Trụ cột / Bước | Mức tổng quát đạt được | Công cụ chính |
|---|---|---|
| B1 (hệ quy chiếu) | $G_k$ — 6 ứng viên hữu hạn, tiêu chí chọn định lượng | Bảng §1.2 |
| A — DOF (B2) | **G** cho định lý gốc; $G_k$ cho thư viện tra cứu | Định lý A + Bảng 2.A/2.B |
| B — Ràng buộc (B3) | **G** cho tiêu chuẩn toàn chỉnh; $G_k$ cho từ điển | Định lý B (Frobenius) + Từ điển B3 |
| C — Đối xứng (B4) | **G** cho điều kiện Noether; $G_k$ cho danh mục phép thử | Định lý C1, C2 + Bảng C |
| Chọn tọa độ (B5) | $G_k$ — 4 tiêu chí + thực đơn + 1 cảnh báo bẫy đã chứng minh | §5.B |
| D — Xấp xỉ (B6) | **G** cho Buckingham/khai triển tiệm cận; đề bài thường tự cho $\varepsilon$ | Định lý D1, D2, D3 |
| Chọn phương pháp (B7) | $G_k$ — 4 cây quyết định (A, B, C, D) bao trọn $\mathcal P_{\text{IPhO}}$ | §7.1–7.4 + Phần 6 |
| Điều kiện biên (B8) | $G_k$ — bảng tra cứu đầy đủ | Bảng B8 |
| Giải toán (B9) | Hộp công cụ toán thuần túy, **G** một khi mô hình đã dựng | §9.1–9.5 |
| Kiểm tra (B10) | Checklist 7 bước, áp dụng phổ quát | §B10 |

Không còn bước nào trong toàn bộ quy trình bị bỏ trống hoặc chỉ dựa "cảm giác vật lý" thuần túy — **mọi** bước đều có (a) tiêu chí kiểm tra được, và (b) danh sách hữu hạn phương án khi không suy luận trực tiếp được.

### 10.2 Giao thức luyện tập đề xuất cho học sinh lớp 11 hướng tới IPhO/VPhO 2027–2028

**Xuyên suốt:** mỗi khi giải sai 1 bài, **truy ngược** xem sai ở bước B nào cụ thể (đếm sai DOF? bỏ sót ràng buộc? dùng bảo toàn sai thứ tự với Lagrangian? chọn sai phương pháp ở B7?) — ghi vào "nhật ký lỗi theo bước B" để nhận diện điểm yếu hệ thống, thay vì chỉ nhớ "bài này khó".

### 10.3 Thông điệp cốt lõi

Trực giác vật lý xuất sắc **là kết quả** của việc thực thi thành thạo một quy trình tổng quát, **không phải điều kiện tiên quyết** để bắt đầu. Một học sinh kỷ luật, thực thi đúng B0–B10 cho **mọi** bài luyện tập, sẽ dần hình thành trực giác đúng đắn như một **hệ quả tự nhiên** — chứ không phải phụ thuộc một năng khiếu bẩm sinh không kiểm soát được. Đây chính là cơ sở để tài liệu này khẳng định: **tính Tổng quát và tính Khả thi cho học sinh trực giác trung bình không mâu thuẫn nhau — một quy trình đủ tổng quát, được liệt kê tường minh đến từng chi tiết, chính là con đường duy nhất để "trực giác trung bình + kỷ luật" đạt tới trình độ HCV IPhO/VPhO.**
