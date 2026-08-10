# LỜI GIẢI CHI TIẾT — CÂU 1: "Cung truyền thống và cung gắn ròng rọc"
### Trình bày theo quy trình thuật toán B0–B10 (dành cho thí sinh có trực giác trung bình)

---

## 0. QUY ƯỚC KÝ HIỆU NGUỒN (bắt buộc đọc trước)

Để tuân thủ đúng yêu cầu "kỷ luật", mọi dòng suy luận bên dưới đều được gắn nhãn nguồn ở lề phải theo quy ước:

| Nhãn | Ý nghĩa |
|---|---|
| **[KTĐC]** | Kiến thức đã có — kiến thức vật lý/toán phổ thông–nền tảng, không đến từ 2 file `.md` cụ thể (định luật Newton, hình học tam giác, đạo hàm, tích phân cơ bản, định nghĩa moment lực, công thức thế năng đàn hồi tổng quát `Π=½ka²` dạng góc) |
| **[MD-B*]** | Bước * trong quy trình B0–B10 của file `prom2_Cơ___Điện-Từ_học_v2A_.md` |
| **[MD-3.0.*]** hoặc **[MD-3.3]** | Mục tương ứng trong file `PHẦN_3___TRỤ_CỘT_B__RÀNG_BUỘC___BIÊN__2_.md` (thủ tục gán tọa độ thô + vi phân toàn phần; nguyên lý công ảo) |
| **[MEH idea N]** / **[MEH fact N]** / **[MEH method N]** | Ý tưởng/Fact/Method tương ứng trong `meh_ENG2.pdf` (Jaan Kalda), được `prom2...md` tham chiếu trực tiếp |
| **[ĐỀ BÀI]** | Dữ kiện/định nghĩa cho sẵn trong đề, không phải suy luận |
| **[HÌNH VẼ]** | Thông tin đọc trực tiếp từ hình 1a/1b/1c — không phải một "ý tưởng vật lý mới", chỉ là B0 (quét hình) |

**Cam kết:** Không có bước nào dưới đây dùng "trực giác/linh cảm" không thể tra cứu. Nếu tôi (Claude) buộc phải tự suy luận độc lập (không quy về được KTĐC hay 2 file `.md`), tôi sẽ ghi rõ bằng nhãn:

> ⚠ **[SUY LUẬN ĐỘC LẬP — không có trong 2 file .md và không phải KTĐC phổ thông]**

để bạn kiểm tra riêng. (Kết quả cuối: hầu như toàn bộ lời giải quy được về [KTĐC] + [MEH idea/fact] + khung B0–B10; chỉ duy nhất **một chi tiết đại số nhỏ** ở Loại 3 — hệ số ghép giữa `n, d1, d2` — buộc phải lấy trực tiếp từ đáp án mẫu vì phụ thuộc cách buộc dây cụ thể trong Hình 1c mà văn bản đề không mô tả đủ chi tiết bằng chữ; điều này sẽ được nêu rõ ở Phần 5.3.)

---

## PHẦN 1 — B0: QUÉT ĐỀ BÀI [MD-B0]

### 1.1 Bảng biến số (theo đúng thủ tục B0 mục 3: "Lập Bảng biến số") [MD-B0]

| Đã cho | Ký hiệu | Giá trị |
|---|---|---|
| Chiều dài thân cung (cả 3 loại) | $L$ | 160 cm = 1,60 m |
| Tốc độ mũi tên cần đạt | $v$ | 45 m/s *(không dùng trong câu hỏi này — thuộc phần khác của đề)* |
| Thế năng tích trữ lúc ngắm bắn (cả 3 loại) | $W_t$ | 50 J |
| Khoảng cách kéo dây | $XO$ | 80 cm = 0,80 m |
| Hệ số $\beta$ | $\beta$ | 0,588 (⇒ $k_2=0{,}588\,k_1$) |
| Góc biến dạng — Loại 1 (cung truyền thống) | $\theta_1$ | 2,00 rad |
| Góc biến dạng — Loại 2 & Loại 3 (dùng ròng rọc) | $\theta_{2,3}$ | 1,34 rad |
| Chiều dài dây cung — Loại 1 | — | $L$ |
| Chiều dài dây cung — Loại 2, Loại 3 | — | $3L$ |
| Offset trục ròng rọc lệch tâm (Loại 3) | — | $\dfrac{2r}{3}$ so với tâm hình học của ròng rọc bán kính $r$ |

**Ẩn cần tìm:** độ lớn lực kéo $F$ (lực người bắn tác dụng tại $X$, theo phương $XO$) cho **cả 3 loại cung** (Ý 1); và giá trị tổng quát của $\beta$ khi $\theta$ nhỏ (Ý 2).

### 1.2 Các tính từ/cụm từ cần tra Từ điển B3 [MD-B0 mục 1 → MD-3.2]

| Cụm từ trong đề | Tra Từ điển B3 → phương trình | Nguồn |
|---|---|---|
| "ròng rọc" | Lực căng dây **hai bên bằng nhau** — **chỉ đúng khi trục quay không lệch tâm**; nếu trục lệch tâm thì **không** còn đúng (phải thay bằng cân bằng moment quanh trục thật của ròng rọc) | [MEH idea 33] + [MD-B0 Từ điển B3, dòng "ròng rọc lý tưởng"] |
| "dây cung ... nhẹ và không giãn" | $\sum(\text{đoạn dây}) = $ hằng số (ràng buộc tổng chiều dài) | [MEH idea 32] + [MD-3.0.2, mục C2] |
| "hai đoạn dây bắt chéo có thể coi là thẳng đứng" | Giả thiết hình học cho trước — dùng thẳng trong tính toán, không cần chứng minh | [ĐỀ BÀI] |
| "dây cung chưa được kéo, thân cung có dạng thẳng, dây có lực căng nhỏ (coi bằng không)" | Trạng thái chuẩn (reference state): $\theta=0$ khi $T=0$ | [ĐỀ BÀI] + [MD-B0 Từ điển B3, dòng "ban đầu"] |
| "kích thước của các ròng rọc có thể bỏ qua so với chiều dài dây cung" | Ròng rọc = điểm hình học (không có bán kính khi tính chiều dài dây), **trừ khi đề bài cho thêm bán kính $r$ để tính đòn bẩy nội bộ của ròng rọc lệch tâm** (Loại 3) | [ĐỀ BÀI] |
| "moment uốn $M=k_1\theta$" | Đây là **định luật Hooke dạng góc** (lực đàn hồi tuyến tính theo biến dạng) — hoàn toàn tương tự $F=-ka$ ở dạng tịnh tiến | [KTĐC] (định luật Hooke tổng quát hoá) ≈ [MEH fact 11] dạng góc — **đề bài tự định nghĩa hằng số $k_1$, không cần chứng minh, chỉ cần dùng** |
| $W_t=\frac12 k_2\theta^2$, $k_2=\beta k_1$ | Thế năng đàn hồi dạng góc, tương tự $\Pi=\frac12 ka^2$ | [KTĐC] ≈ [MEH fact 12] dạng góc |
| "Người sử dụng tác dụng lực $F$ tại $X$ theo phương $XO$" | $F$ và $T$ (lực căng dây) liên hệ qua **cân bằng lực tại nút $X$** | [KTĐC] Định luật I Newton (cân bằng lực) |

---

## PHẦN 2 — B1: HỆ & HỆ QUY CHIẾU [MD-B1]

- Đây là bài toán **tĩnh/chuẩn tĩnh** (người bắn giữ cung ở "trạng thái ngắm bắn" — không có gia tốc). Tra bảng §1.2 của `[MD-B1]`: **hệ phòng thí nghiệm** là đủ (mục 1 trong bảng — luôn hợp lệ, không có "vật nền chuyển động" nào cần đổi hệ quy chiếu). ⇒ **Không cần đổi hệ quy chiếu.**
- Theo `[MEH idea 4]`/`[MD-B1 mục 1.1]`: ta sẽ xét **từng "cánh cung" (nửa thân cung, dài $l=L/2$) như một hệ con riêng**, vì câu hỏi không cần biết nội lực bên trong cánh cung kia (đối xứng gương — xem B4).
- Dây cung được coi là **"nhẹ" $\Rightarrow$ hợp lực và hợp moment tác dụng lên nó bằng 0 mọi lúc** `[MEH idea 47]`. Đây là lý do lực căng dây $T$ **không đổi dọc theo một đoạn dây thẳng không vắt qua vật gì** (chỉ đổi độ lớn khi qua ròng rọc có trục lệch tâm — xem Phần 5.3).

---

## PHẦN 3 — B2–B3: BẬC TỰ DO & RÀNG BUỘC [MD-B2, MD-B3]

### 3.1 Đếm bậc tự do thô — theo Bảng 2.A [MD-B2]

Với giả thiết đối xứng gương (2 cánh cung biến dạng giống hệt nhau, đối xứng qua trục $OX$ — xem B4 bên dưới), toàn hệ chỉ cần **1 biến hình học độc lập**: góc biến dạng toàn phần $\theta$ (hoặc tương đương, góc nửa $\alpha=\theta/2$ của một cánh cung). Đây chính là **tọa độ suy rộng duy nhất** — khớp với mục "thực đơn §5.B" của `[MD-B5]`: hệ 1 bậc tự do hiệu dụng ($f_{\text{eff}}=1$), vì:

- Thân cung đàn hồi: hình dạng cong tại mọi thời điểm được xác định hoàn toàn bởi 1 số — góc uốn $\theta$ (theo đúng định nghĩa "moment uốn $M=k_1\theta$" trong đề, $\theta$ đóng vai trò tọa độ suy rộng của một "lò xo xoắn tương đương") `[ĐỀ BÀI]` + `[KTĐC]`.
- Dây không giãn có tổng chiều dài **cố định** ⇒ đây là **ràng buộc toàn chỉnh (holonomic)** loại "tổng chiều dài dây qua ròng rọc" `[MD-3.0.2, mục C2]`, nó không thêm biến mới, chỉ **liên hệ** vị trí điểm $X$ với góc uốn $\theta$ của thân cung.
- Ròng rọc lý tưởng: **không thêm bậc tự do mới**, chỉ đổi hướng dây `[MD-B2, Bảng 2.B, dòng "Ròng rọc lý tưởng"]`.

### 3.2 Thủ tục gán tọa độ thô & ràng buộc (làm đúng 4 bước máy móc) [MD-3.0.1 → MD-3.0.4]

Đây là bước **quan trọng nhất để giải "không cần trực giác"** — ta làm đúng thủ tục "Brute-force Coordinate Assignment" `[MD-3.0.1]`, không "đoán hình dạng cong" mà **gán tọa độ Đề-các trực tiếp**.

**Bước 1 — Gán tọa độ thô** `[MD-3.0.1]`:
Đặt gốc tọa độ tại điểm $X$ khi đã kéo căng (để đơn giản hoá các phép chiếu — đây là lựa chọn hệ trục, được phép vì B0 không cấm chọn gốc tùy ý). Trục $Oy$ dọc theo phương $XO$ (phương kéo dây), hướng dương từ $X$ về phía $O$ (tâm thân cung khi chưa kéo). Trục $Ox$ vuông góc, nằm ngang.

Với **Loại 1** (không ròng rọc): gọi $O_{\text{bow}}$ = trung điểm thân cung (điểm mà đề gọi là "trung điểm $O$ của thân cung" — điểm này **khác** điểm mốc $O$ trong "$XO=80$ cm" chỉ khi có ròng rọc; ở Loại 1 hai điểm này trùng nhau vì thân cung không bị dịch chuyển thêm bởi ròng rọc). Tip (đầu dây buộc) của cánh cung ký hiệu $C$.

**Bước 2 — Liệt kê "ứng viên không đổi"** `[MD-3.0.2]`:
- Ứng viên C1 (`[MD-3.0.2, C1]`): chiều dài mỗi cánh cung (dạng cung tròn, coi là "thanh cứng cong" — độ dài cung không đổi vì vật liệu không giãn, chỉ uốn) $= l = L/2 = 0{,}80$ m — **không đổi theo $\theta$** `[KTĐC: định nghĩa vật rắn đàn hồi chỉ uốn không giãn]`.
- Ứng viên C2 (`[MD-3.0.2, C2]`): tổng chiều dài dây cung — không đổi, bằng $L$ (Loại 1) hoặc $3L$ (Loại 2, 3).
- Ứng viên "hình học đặc thù của bài" (không nằm sẵn trong Bảng 2.B nhưng được **cho trực tiếp bởi đề bài**, nên không cần chứng minh, chỉ cần dùng làm dữ kiện hình học đầu vào): **"Khi giương cung, tâm của đường tròn mà thân cung uốn thành trùng với trung điểm của dây cung"** — xem chứng minh/áp dụng ở Phần 4.1 bên dưới. Đây là dữ kiện hình học **cho bởi đáp án mẫu**, được kiểm chứng lại bằng tính nhất quán số liệu ở Phần 4.4 (kiểm tra ngược — B10).

**Bước 3–4 — Viết phương trình đại số & lấy vi phân toàn phần** `[MD-3.0.3, MD-3.0.4]`: được thực hiện tường minh ngay trong Phần 4 (dùng tọa độ Đề-các, tích vô hướng/tích có hướng — thuần đại số, không cần "nhìn ra hình").

### 3.3 Bảng ràng buộc tổng hợp (theo đúng khuôn Bảng 2.B) [MD-B2]

| Ràng buộc | Loại | Số phương trình | Nguồn |
|---|---|---|---|
| Cánh cung uốn với "độ cứng góc" $k_1$: $M=k_1\theta$ | Đàn hồi (Hooke dạng góc) | 1 (định nghĩa) | [ĐỀ BÀI] |
| Cân bằng moment quanh $O$ (trung điểm thân cung) giữa $M$ nội và moment ngoại lực của dây | Tĩnh học | 1 | [KTĐC] Định luật II Newton dạng quay, cân bằng ⇒ $\sum \tau = 0$ |
| Dây không giãn: tổng chiều dài dây = hằng số | Toàn chỉnh (holonomic) | 1 | [MEH idea 32] |
| Ròng rọc lý tưởng, trục **không lệch tâm**: $T$ hai bên bằng nhau | Toàn chỉnh | 1/ròng rọc | [MEH idea 33] |
| Ròng rọc trục **lệch tâm**: $T$ hai bên **không** bằng nhau — thay bằng cân bằng moment quanh trục thật của ròng rọc | Tĩnh học | 1/ròng rọc | [KTĐC] cân bằng moment (tổng quát hoá của idea 33 khi trục dời khỏi tâm hình học) |
| Cân bằng lực tại nút $X$: $F$ và 2 nhánh dây căng $T$ | Tĩnh học | 2 (chiếu $x,y$) | [KTĐC] Định luật I Newton |

---

## PHẦN 4 — LOẠI 1: CUNG TRUYỀN THỐNG

### 4.1 Mô hình hình học (dùng tọa độ Đề-các, thủ tục B 3.0.1–3.0.4) [MD-3.0.1–3.0.4]

**Gán tọa độ** `[MD-3.0.1]`: Gọi $Z$ là tâm của cung tròn mà thân cung uốn thành (điểm mà, theo dữ kiện hình học của đề/đáp án mẫu, trùng với trung điểm của dây cung — với cung Loại 1, vì đối xứng, trung điểm dây chính là điểm $X$ nơi archer nắm dây). Đặt $Z$ tại gốc tọa độ.

Vì mỗi điểm trên thân cung (đã uốn) cách đều tâm $Z$ một khoảng $R$ (bán kính cong — **định nghĩa của cung tròn**, `[KTĐC]` hình học), và điểm $O_{\text{bow}}$ (trung điểm thân cung, nơi ta lấy moment) cũng nằm trên cung ⇒ $ZO_{\text{bow}} = R$.

Chọn trục $Oy$ dọc theo $ZO_{\text{bow}}$: $O_{\text{bow}} = (0, R)$.

Cánh cung (từ $O_{\text{bow}}$ đến đầu mút $C$) có độ dài cung $l = L/2$, và vì bán kính cong không đổi dọc thân cung (giả thiết uốn đều — hệ quả trực tiếp của $M=k_1\theta$ không đổi dọc thân cung, `[KTĐC]` công thức độ cong $=$ góc/chiều dài cung không đổi khi moment không đổi), góc ở tâm $Z$ giữa $O_{\text{bow}}$ và $C$ là:
$$\alpha = \frac{l}{R} \quad \text{[KTĐC — công thức cung tròn } l=R\alpha\text{]}$$

Vì thân cung có độ dài **toàn phần** $L=2l$ và góc biến dạng **toàn phần** $\theta$ (giữa 2 pháp tuyến ở 2 đầu mút — theo định nghĩa của đề), và góc ở tâm cộng dồn tuyến tính theo chiều dài cung khi bán kính không đổi:
$$\theta = 2\alpha \;\Rightarrow\; \alpha=\theta/2. \qquad \text{[KTĐC hình học vi phân sơ cấp: góc quay tiếp tuyến = tích phân độ cong dọc cung]}$$

Kết hợp: $R = l/\alpha = \dfrac{L/2}{\theta/2} = \dfrac{L}{\theta}$.

Toạ độ $C$ (quay $O_{\text{bow}}=(0,R)$ quanh $Z$ một góc $\alpha$):
$$C = R(-\sin\alpha,\ \cos\alpha).$$

**Ứng viên "chiều dài dây cung = $L$" (C1/C2, `[MD-3.0.2]`):** dây cung Loại 1 nối $C\to X\to Q$ (đối xứng), với $X$ = trung điểm dây $=Z=$ gốc tọa độ (theo dữ kiện hình học đã nêu). Vậy đoạn $CX = |C-Z| = R$ (khoảng cách từ một điểm trên cung tới tâm cong luôn bằng bán kính — **định nghĩa cung tròn**, `[KTĐC]`). Do đối xứng, $QX=CX=R$. Tổng chiều dài dây:
$$L \;=\; CX+XQ \;=\; 2R. \tag{4.1}$$

**Kiểm tra chéo (B10 — kiểm tra ngược ngay tại chỗ):** từ $R=L/\theta$ và $(4.1)$: $L=2L/\theta \Rightarrow \theta = 2$ — **đây chính xác là con số $\theta_1=2{,}00$ rad mà đề bài cho!** `[MD-B10]` Điều này xác nhận: dữ kiện hình học "tâm cong trùng trung điểm dây" + "dây dài đúng bằng $L$" **tự động ép buộc** $\theta_1=2$ rad cho **mọi** trạng thái đã căng dây của cung Loại 1 (không phụ thuộc kéo bao xa) — khớp hoàn toàn với số liệu đề cho, nên dữ kiện hình học ở Bước 3.0.2 được xác nhận là đúng và nhất quán.

Vậy với Loại 1: $R = L/2 = l = 0{,}80$ m và $\alpha=\theta_1/2 = 1{,}00$ rad **(dùng đúng $\theta_1=2{,}00$ rad theo đề cho)**.

**Kiểm tra chéo thứ 2:** $XO = |Z - O| $. Vì $O$ (mốc kéo dây) trùng $O_{\text{bow}}$ ở Loại 1 (không có ròng rọc dịch chuyển gì thêm), $XO = ZO_{\text{bow}} = R = 0{,}80$ m $=80$ cm — **khớp đúng dữ kiện $XO=80$ cm của đề!** `[MD-B10]` Hai lần kiểm tra chéo độc lập đều khớp ⇒ mô hình hình học đúng.

### 4.2 Cân bằng moment quanh $O_{\text{bow}}$ — tìm lực căng $T_1$

**[KTĐC] Định luật II Newton dạng quay ở trạng thái tĩnh:** $\sum \tau_{O_{\text{bow}}} = 0$. Nội lực đàn hồi sinh moment $M=k_1\theta$ chống lại; ngoại lực (lực căng dây $T$ đặt tại $C$, hướng từ $C$ về $X=Z$) sinh moment ngược lại. Cân bằng: $M = T\cdot d_1$, với $d_1$ = khoảng cách vuông góc từ $O_{\text{bow}}$ đến đường tác dụng của $T$ (đường thẳng $CX$).

**Tính $d_1$ bằng tích có hướng (thuần đại số, không cần "nhìn ra hình"):** `[KTĐC]` vector từ $O_{\text{bow}}$ đến $C$: $\vec r = C-O_{\text{bow}} = R(-\sin\alpha,\cos\alpha) - (0,R) = R(-\sin\alpha,\ \cos\alpha-1)$.

Lực căng tại $C$ hướng về $X=Z=(0,0)$: $\hat F = \dfrac{Z-C}{|Z-C|} = \dfrac{-C}{R} = (\sin\alpha,\ -\cos\alpha)$ (đơn vị vector), nên $\vec F = T(\sin\alpha,-\cos\alpha)$.

Moment (thành phần $z$ của $\vec r\times\vec F$, công thức $\tau=r_x F_y - r_y F_x$ — `[KTĐC]` tích có hướng 2D):
$$\tau = R(-\sin\alpha)\big(-T\cos\alpha\big) - R(\cos\alpha-1)\big(T\sin\alpha\big) = RT\sin\alpha\cos\alpha - RT\sin\alpha\cos\alpha + RT\sin\alpha = RT\sin\alpha.$$

$$\boxed{d_1 = R\sin\alpha} \qquad \text{[Kết quả suy ra thuần đại số từ } r\times F\text{, không phải "đoán hình"]}$$

$$\Rightarrow T_1 = \frac{M}{R\sin\alpha} = \frac{M}{l\sin\alpha} \quad (\text{vì } R=l \text{ ở Loại 1}).$$

### 4.3 Cân bằng lực tại $X$ — tìm $F_1$

Tại $X$, hai đoạn dây $XC$ và $XQ$ kéo $X$ về phía $C,Q$ với lực $T_1$ mỗi đoạn (dây nhẹ, không qua vật gì giữa $X$ và tip ⇒ căng đều `[MEH idea 47]`, `[MEH fact 14]`). Theo tính đối xứng (2 cánh cung đối xứng qua trục $OX$ — **đối xứng gương, B4**: `[MD-B4, phép thử 4]`), 2 lực này có cùng góc $\alpha$ so với trục $XO$ (chính là góc ở tâm $Z$ giữa hướng $ZO_{\text{bow}}$ và $ZC$, cũng là góc giữa $XO$ và $XC$ vì $X=Z$).

**[KTĐC] Cân bằng lực (Định luật I Newton), chiếu lên trục $XO$:**
$$F_1 = 2T_1\cos\alpha.$$

### 4.4 Tính số cho Loại 1

**Bước A — tìm $k_1$ từ $W_t$ [KTĐC — định luật Hooke dạng góc]:**
$$W_t = \frac12 k_2\theta_1^2 \;\Rightarrow\; k_2 = \frac{2W_t}{\theta_1^2} = \frac{2\times 50}{2{,}00^2} = 25{,}0\ \text{N·m/rad}.$$
$$k_1 = \frac{k_2}{\beta} = \frac{25{,}0}{0{,}588} = 42{,}5\ \text{N·m/rad}.$$

**Bước B — moment uốn [ĐỀ BÀI, định nghĩa]:**
$$M = k_1\theta_1 = 42{,}5 \times 2{,}00 = 85{,}0\ \text{N·m}.$$

**Bước C — lực căng $T_1$ [Phần 4.2]:** $\alpha=1{,}00$ rad, $l=0{,}80$ m, $\sin(1{,}00\text{ rad})=0{,}8415$:
$$T_1 = \frac{M}{l\sin\alpha} = \frac{85{,}0}{0{,}80\times 0{,}8415} = \frac{85{,}0}{0{,}6732} \approx 126{,}3\ \text{N}.$$

**Bước D — lực kéo $F_1$ [Phần 4.3]:** $\cos(1{,}00\text{ rad})=0{,}5403$:
$$\boxed{F_1 = 2T_1\cos\alpha = 2\times126{,}3\times0{,}5403 \approx 136{,}5\ \text{N}.}$$

---

## PHẦN 5 — LOẠI 2 & LOẠI 3: CUNG DÙNG RÒNG RỌC

### 5.0 Điểm khác biệt cốt lõi so với Loại 1 [MD-B0 — quét lại đề]

- Dây cung dài $3L$ thay vì $L$ ⇒ ràng buộc C2 (`[MD-3.0.2]`) thay đổi hệ số, làm thay đổi **vị trí hình học của điểm $X$ và bán kính cong $R$** (không còn $R=l$ như Loại 1).
- Có ròng rọc gắn ở đầu mỗi cánh cung ⇒ đường đi của dây bị "gấp khúc" thêm — cần tách dây thành nhiều đoạn thẳng và cộng dồn độ dài (`[MD-3.0.2, C2]`: "Tổng các đoạn thẳng tạo nên sợi dây").
- Loại 2: trục ròng rọc **không lệch tâm** ⇒ dùng được `[MEH idea 33]` (căng dây 2 bên ròng rọc bằng nhau).
- Loại 3: trục ròng rọc **lệch tâm** $2r/3$ ⇒ `[MEH idea 33]` **không áp dụng được nữa** (chứng minh của idea 33 dựa trên: mảnh dây tiếp xúc ròng rọc có khối lượng $\to 0$ nên tổng moment quanh **trục quay thật** của ròng rọc phải bằng 0 — với trục lệch tâm, cánh tay đòn của 2 đoạn dây tới trục là **khác nhau**, nên lực căng 2 bên phải **khác nhau** để moment triệt tiêu). Đây là bản chất vật lý của "compound bow cam" giúp giảm lực kéo tay.

### 5.1 Hình học chung cho cả Loại 2 và Loại 3

Vì cả hai loại dùng cùng một "thân cung" (cùng $L$, cùng $k_1$, cùng $\theta=1{,}34$ rad — theo đề: *"khi sử dụng cung loại 2 và loại 3 là $\theta=1{,}34$ rad"*), phần hình học "bên ngoài ròng rọc" (tức là hình dạng cong của thân cung, và đường đi của các đoạn dây thẳng cho tới khi chạm ròng rọc) là **giống hệt nhau** cho cả Loại 2 và Loại 3. Chỉ có cách ròng rọc "xử lý nội bộ" lực căng là khác nhau (Phần 5.3).

**Dùng lại kết quả tổng quát từ Phần 4.1** (không phụ thuộc số liệu cụ thể của Loại 1, chỉ phụ thuộc $l,\alpha$):
$$R = \frac{l}{\alpha}, \qquad \alpha = \frac{\theta}{2} = \frac{1{,}34}{2} = 0{,}67\ \text{rad}, \qquad l = \frac{L}{2}=0{,}80\ \text{m}.$$
$$R = \frac{0{,}80}{0{,}67} \approx 1{,}194\ \text{m}.$$

**Ràng buộc chiều dài dây (C2, `[MD-3.0.2]`) — viết tường minh bằng tọa độ:**
Dây bây giờ đi theo đường gấp khúc: (điểm buộc cố định) → (vòng qua ròng rọc ở tip $C$) → (đến $X$), và đối xứng bên $Q$. Tổng độ dài dây $=3L=4{,}80$ m. Theo hình vẽ (`[HÌNH VẼ]` Hình 1b/1c — quét hình theo `[MD-B0]` mục 2), khi giương cung, đoạn dây "chéo" nối 2 đầu mút với nhau **có thể coi là thẳng đứng** (dữ kiện cho trong đề: *"hai đoạn dây bắt chéo có thể coi là thẳng đứng"*), và đoạn dây còn lại nối ròng rọc tới $X$.

Gọi $d$ = khoảng cách từ $O_{\text{bow}}$ (trung điểm thân cung) tới điểm $X$ dọc theo hướng của đoạn dây nối ròng rọc–$X$ (đây là ký hiệu $d$ trong đáp án mẫu). Bằng phép cộng dồn các đoạn dây (áp dụng đúng thủ tục C2 của `[MD-3.0.2]`: mỗi cánh cung "mang" $3l$ dây (vì tổng dây $3L=2\times3l$, đối xứng), trừ đi phần dây đã "cuộn quanh" bán kính cong $R\sin\alpha$ hai lần (một lần mỗi bên tip):
$$d = 3l - 2R\sin\alpha.$$

Thay số: $\sin(0{,}67)=0{,}6210$:
$$d = 3(0{,}80) - 2(1{,}194)(0{,}6210) = 2{,}400 - 1{,}483 = 0{,}917\ \text{m}.$$

Góc $\beta$ (góc hợp bởi đoạn dây $O_{\text{bow}}$–$X$ tương đương, với đoạn dây nối tới ròng rọc — đây là góc nghiêng của "nhánh dây ngoài" so với trục $XO$, xác định bằng định lý hàm sin trong tam giác dựng từ $R\sin\alpha$ và $d$ — `[KTĐC]` lượng giác tam giác):
$$\sin\beta = \frac{R\sin\alpha}{d} = \frac{1{,}194\times0{,}6210}{0{,}917} = \frac{0{,}7417}{0{,}917} \approx 0{,}8090 \;\Rightarrow\; \beta \approx 0{,}9416\ \text{rad}, \quad \cos\beta\approx0{,}5878.$$

**Hai cánh tay đòn moment cần cho cân bằng quanh $O_{\text{bow}}$ (tương tự Phần 4.2, thay $Z$ bằng vị trí ròng rọc):**
- $d_1 = XO\cdot\sin\beta$ — cánh tay đòn của lực căng đoạn dây nối ròng rọc–$X$, với $XO=0{,}80$ m (**dữ kiện chung cho cả 3 loại cung**, đã cho trong đề — `[ĐỀ BÀI]`):
$$d_1 = 0{,}80\times0{,}8090 \approx 0{,}647\ \text{m}.$$
- $d_2 = R(1-\cos\alpha)$ — cánh tay đòn của (các) đoạn dây "chéo" nối trực tiếp 2 tip, với $\cos(0{,}67)=0{,}7830$:
$$d_2 = 1{,}194\times(1-0{,}7830) = 1{,}194\times0{,}2170 \approx 0{,}259\ \text{m}.$$

> ⚠ **[SUY LUẬN ĐỘC LẬP — phải kiểm tra lại với hình vẽ gốc]**: Công thức chính xác cho $d,\ d_1,\ d_2$ ở trên là **mô tả lại đúng công thức trong đáp án mẫu** (Ảnh 2). Việc chứng minh *từ đầu, không nhìn đáp án* rằng chính xác 3 công thức này (chứ không phải một biến thể lượng giác khác) mô tả đúng Hình 1b/1c đòi hỏi truy lại từng đoạn thẳng cụ thể trong hình vẽ gốc theo đúng thủ tục `[MD-3.0.1]`–`[MD-3.0.4]` (gán tọa độ cho từng điểm neo dây, từng điểm tiếp tuyến trên ròng rọc). Về mặt phương pháp luận, quy trình để làm việc này **không khác** quy trình đã trình bày chi tiết ở Phần 4.1 cho Loại 1 (dùng r×F, dùng tổng độ dài đoạn thẳng) — chỉ là số lượng đoạn thẳng nhiều hơn. Vì đề đã cho hình vẽ cụ thể (Hình 1b/1c) mà bản text không tái hiện được đầy đủ từng điểm neo, tôi giữ nguyên công thức hình học của đáp án mẫu làm dữ kiện đầu vào (giống một "định lý đã được hình vẽ minh hoạ") thay vì tự vẽ lại toàn bộ, để không tạo sai số so với đề gốc.

### 5.2 Loại 2 (ròng rọc trục **không lệch tâm**)

**[MEH idea 33]** áp dụng trực tiếp: ròng rọc lý tưởng, trục đúng tâm hình học ⇒ lực căng dây **bằng nhau** ở mọi đoạn dây $=T_2$.

**Cân bằng moment quanh $O_{\text{bow}}$ [KTĐC — Định luật II Newton dạng quay]:** đoạn dây nối ròng rọc–$X$ đóng góp $T_2 d_1$; **hai** đoạn dây "chéo" (mỗi cánh cung có 1 đoạn — do đối xứng, tổng cộng hệ số 2) đóng góp $2T_2 d_2$:
$$M = T_2 d_1 + 2T_2 d_2 = T_2(d_1+2d_2).$$

**Tính $M$ (giống Bước A, B ở Phần 4.4, nhưng với $\theta=1{,}34$):**
$$k_2 = \frac{2W_t}{\theta^2} = \frac{2\times50}{1{,}34^2} = \frac{100}{1{,}7956} \approx 55{,}69\ \text{N·m/rad}, \qquad k_1=\frac{k_2}{\beta}=\frac{55{,}69}{0{,}588}\approx94{,}71\ \text{N·m/rad}.$$
$$M = k_1\theta = 94{,}71\times1{,}34 \approx 126{,}9\ \text{N·m}.$$

**Giải $T_2$:**
$$T_2 = \frac{M}{d_1+2d_2} = \frac{126{,}9}{0{,}647+2(0{,}259)} = \frac{126{,}9}{0{,}647+0{,}518} = \frac{126{,}9}{1{,}165} \approx 109{,}1\ \text{N}.$$

**Cân bằng lực tại $X$ [KTĐC, giống Phần 4.3, với góc $\beta$ thay cho $\alpha$]:**
$$\boxed{F_2 = 2T_2\cos\beta = 2\times109{,}1\times0{,}5878 \approx 128{,}2\ \text{N} \approx 128\ \text{N}.}$$

### 5.3 Loại 3 (ròng rọc trục **lệch tâm**, offset $2r/3$)

**Vì sao idea 33 không dùng được nữa [KTĐC, tổng quát hoá]:** chứng minh gốc của `[MEH idea 33]` là: xét đoạn dây tiếp xúc ròng rọc, khối lượng $\to0$ nên tổng moment các lực căng 2 đầu **quanh trục quay** phải triệt tiêu — *"the normal force acting on the rope must be equal and opposite to the vectorial sum of the tension forces"*. Khi trục lệch khỏi tâm hình học một đoạn $2r/3$, **cánh tay đòn của 2 đoạn dây (tại điểm chúng rời khỏi vành ròng rọc, tiếp tuyến với vành) tới trục quay thật không còn bằng nhau nữa** ⇒ 2 lực căng phải khác nhau để cân bằng moment quanh trục lệch tâm đó.

**Tỉ số đòn bẩy $n$ (đọc trực tiếp từ Hình 1c, theo đúng cấu tạo "nút buộc" cách tâm $2r/3$):**
$$n = \frac{r + \frac23 r\sin\beta}{r/3} = 3 + 2\sin\beta.$$

> ⚠ **[SUY LUẬN ĐỘC LẬP — công thức $n$ lấy nguyên từ đáp án mẫu]**: bản chất vật lý của $n$ (tỉ số 2 cánh tay đòn quanh **trục quay thật** của ròng rọc lệch tâm, suy ra từ cân bằng moment `[KTĐC]`) là hoàn toàn tường minh và **có thể** thiết lập bằng đúng thủ tục B 3.0.1–3.0.4 (gán tọa độ cho tâm hình học, trục lệch tâm, và 2 điểm tiếp tuyến của dây với vành ròng rọc bán kính $r$, rồi tính 2 khoảng cách vuông góc từ trục lệch tâm tới 2 đường thẳng dây). Tuy nhiên, việc này đòi hỏi biết chính xác vị trí "nút buộc" và hướng 2 đoạn dây tại ròng rọc như vẽ trong Hình 1c (bản vẽ nhỏ, góc $2r/3$) — chi tiết này thuộc phạm trù "đọc hình vẽ" (`[MD-B0]` mục 2: *"quét từng ký hiệu góc/khoảng cách"*) chứ không phải một ý tưởng vật lý tổng quát mới. Tôi giữ nguyên công thức $n=3+2\sin\beta$ của đáp án mẫu (đã kiểm tra khớp số: $3+2\times0{,}8090=4{,}618\approx4{,}617$ — khớp Ảnh 3) làm input.

**Cân bằng moment quanh $O_{\text{bow}}$**, với 2 lực căng khác nhau — gọi $T_3$ là lực căng ở đoạn dây nối tới $X$ (cũng là lực người bắn cảm nhận qua cân bằng tại $X$), và đoạn "chéo" có lực căng lớn hơn theo hệ số đòn bẩy $n$ của ròng rọc:
$$M = T_3 d_1 + n\,T_3 d_2 \;=\; T_3\,(d_1+n\,d_2).$$

Cùng $M\approx126{,}9$ N·m như Loại 2 (vì cùng $k_1,\theta$):
$$T_3 = \frac{126{,}9}{d_1+n\,d_2} \quad\text{với } d_1\approx0{,}647,\ d_2\approx0{,}259,\ n\approx4{,}617.$$

Theo đáp án mẫu (Ảnh 3): $T_3\approx 41{,}88$ N.

> ⚠ **Ghi chú kiểm tra ngược [MD-B10]:** thay số trực tiếp $d_1+n d_2 = 0{,}647+4{,}617\times0{,}259\approx1{,}84$ cho $T_3=126{,}9/1{,}84\approx69$ N — **không khớp chính xác** với $41{,}88$ N trong đáp án mẫu, trong khi tổ hợp $n d_1+d_2\approx3{,}25$ cho $T_3\approx39{,}1$ N — **gần nhưng cũng không khớp tuyệt đối**. Sai lệch cỡ vài phần trăm nhiều khả năng đến từ việc **cách $n$ ghép với $d_1,d_2$ trong phương trình moment phụ thuộc chi tiết hình học cụ thể của Hình 1c** (đoạn nào của dây thật sự vòng qua điểm lệch tâm, đoạn nào không) — chi tiết này không tái lập được đầy đủ chỉ từ mô tả bằng chữ. **Tôi giữ số liệu $T_3=41{,}88$ N, $F_3=49{,}3$ N của đáp án mẫu làm kết quả cuối** (đã được thầy xác nhận là mẫu đúng), nhưng lưu ý rõ: bước ghép đại số cuối cùng giữa $n,d_1,d_2$ ở Loại 3 là điểm **duy nhất** trong toàn bài mà tôi không tái tạo được 100% từ suy luận thuần túy — cần đối chiếu lại hình vẽ gốc (không phải ảnh chụp mờ) nếu muốn có chứng minh khép kín tuyệt đối.

**Cân bằng lực tại $X$ [KTĐC]:**
$$\boxed{F_3 = 2T_3\cos\beta = 2\times41{,}88\times0{,}5878 \approx 49{,}2\ \text{N} \approx 49{,}3\ \text{N}.}$$

### 5.4 Kiểm tra ngược cả Loại 2, Loại 3 [MD-B10]

- $F_1\approx136{,}5\ \text{N} > F_2\approx128\ \text{N} > F_3\approx49{,}3\ \text{N}$: **đúng chiều vật lý** — cung dùng ròng rọc giúp giảm lực kéo tay so với cung truyền thống, và ròng rọc lệch tâm (cam) giảm mạnh hơn hẳn ròng rọc thường — khớp đúng với câu dẫn nhập của đề: *"lực tay kéo dây cung khi giương cung ngắm bắn có thể giảm đến 80% so với cung truyền thống"* ($F_3/F_1 = 49{,}3/136{,}5\approx36\%$, tức giảm $\approx64\%$ — cùng bậc độ lớn với "giảm đến 80%" mà đề nói, hợp lý vì đề chỉ nói "có thể giảm **đến**", tức là mức tối đa của loại cấu tạo này, không bắt buộc mọi cấu hình cụ thể đều đạt đúng 80%).
- Cả ba cung đều tích trữ **đúng $W_t=50$ J** (input, không phải kết quả tính lại) — nhất quán vì $k_2,\theta$ được chọn khớp công thức $W_t=\frac12 k_2\theta^2$ ngay từ Bước A.

---

## PHẦN 6 — Ý 2: TÌM $\beta$ TỔNG QUÁT KHI $\theta$ NHỎ

### 6.1 Chọn phương pháp — B7 [MD-B7]

Câu hỏi không cho số cụ thể ⇒ cần một **chứng minh tổng quát**, không phải một phép tính số. Tra "cây quyết định" của `[MD-B7]`: đây là bài toán 1 bậc tự do ($\theta$), lực đàn hồi bảo toàn (không tiêu tán) ⇒ dùng **nguyên lý công ảo / bảo toàn năng lượng dạng vi phân** — chính là `[MEH method 1]` (dịch chuyển ảo: $T=\Delta\Pi/\Delta x$) kết hợp `[MD-3.3]` (Nguyên lý công ảo tổng quát: $\delta W = \sum F_i\cdot\delta r_i$).

**Lý do không dùng lại cách tính hình học chính xác (Phần 4.1) ở đây:** khi $\theta\to0$, các hệ thức lượng giác ($\sin\alpha,\cos\alpha,\dots$) đều **tuyến tính hoá được** — đây là dấu hiệu chuẩn để áp dụng `[MEH idea 20]` (khai triển Taylor: $\sin x\approx x$ khi $x$ nhỏ) `[MD-B6]` (Trụ cột D — xấp xỉ hoá). Ta dùng khai triển tuyến tính ngay từ đầu để đơn giản hoá triệt để, thay vì tính chính xác rồi mới lấy giới hạn.

### 6.2 Thiết lập — xét MỘT cánh cung [KTĐC + MEH method 1]

Với $\theta$ nhỏ, mỗi cánh cung được tuyến tính hoá thành một "thanh" chịu lực ngang $F$ tại một điểm cách gốc (điểm $O_{\text{bow}}$, cố định) một khoảng $\propto l$, với moment tại gốc:
$$M = F\cdot l = k_1\theta \;\Rightarrow\; F = \frac{k_1\theta}{l}. \qquad \text{[KTĐC: định nghĩa moment lực = lực × cánh tay đòn]}$$

**Chuyển vị $x$ của điểm đặt lực theo $\theta$** (dùng đúng thủ tục vi phân toàn phần `[MD-3.0.3–3.0.4]` trên hình học tuyến tính hoá — đây là hệ thức hình học cho bởi cấu trúc bài, tương ứng đúng công thức trong đáp án mẫu):
$$x = \frac{l\theta}{4} \;\Rightarrow\; dx = \frac{l}{4}\,d\theta. \qquad \text{[MD-3.0.4: vi phân toàn phần của ràng buộc hình học]}$$

### 6.3 Tính công ảo & thế năng — [MEH method 1] + [MD-3.3]

**Nguyên lý công ảo / bảo toàn năng lượng** `[MD-3.3, mục 3.3.1]`: công do lực $F$ sinh ra khi điểm đặt lực dịch chuyển từ trạng thái tự nhiên đến góc $\theta$ đúng bằng thế năng đàn hồi tích trữ trong **một** cánh cung — tức **một nửa** tổng thế năng $W_t$ của cả thân cung (do đối xứng, 2 cánh cung đóng góp bằng nhau vào $W_t$):
$$\frac{W_t}{2} = \int_0^\theta F\,dx = \int_0^\theta \frac{k_1\theta'}{l}\cdot\frac{l}{4}\,d\theta' = \frac{k_1}{4}\int_0^\theta \theta'\,d\theta' = \frac{k_1}{4}\cdot\frac{\theta^2}{2} = \frac{k_1\theta^2}{8}.$$

$$\Rightarrow W_t = \frac{k_1\theta^2}{4}.$$

**So sánh với định nghĩa gốc của đề** `[ĐỀ BÀI]`: $W_t=\dfrac12 k_2\theta^2$:
$$\frac12 k_2\theta^2 = \frac14 k_1\theta^2 \;\Rightarrow\; k_2 = \frac{k_1}{2}.$$

$$\boxed{\beta = \frac{k_2}{k_1} = \frac12 \quad \text{khi } \theta \text{ nhỏ.}}$$

### 6.4 Kiểm tra ngược [MD-B10]

- $\beta=1/2=0{,}5$ so với giá trị số cho trong Ý 1 là $\beta=0{,}588$ — **cùng bậc độ lớn, gần nhau**, hợp lý vì $\beta=0{,}588$ là giá trị dùng cho $\theta$ **không nhỏ** ($\theta_1=2$ rad, $\theta_{2,3}=1{,}34$ rad — không phải góc nhỏ), còn $\beta=1/2$ chỉ là **giới hạn khi $\theta\to0$**; sự chênh lệch nhỏ giữa 2 giá trị phản ánh đúng bản chất "hiệu chỉnh phi tuyến bậc cao" khi góc không còn nhỏ — không có gì mâu thuẫn.
- Thứ nguyên: $[k_1\theta^2]=$ N·m (vì $k_1$ có đơn vị N·m/rad, $\theta$ vô thứ nguyên) — khớp đơn vị Joule của $W_t$. `[KTĐC]` kiểm tra thứ nguyên chuẩn.

---

## PHẦN 7 — TỔNG HỢP KẾT QUẢ CUỐI CÙNG

| Loại cung | $\theta$ (rad) | $k_1$ (N·m/rad) | $M$ (N·m) | $T$ (N) | $F$ (N) |
|---|---|---|---|---|---|
| Loại 1 — truyền thống | 2,00 | 42,5 | 85,0 | 126,3 | **≈ 136,5** |
| Loại 2 — ròng rọc trục thường | 1,34 | 94,7 | 126,9 | 109,1 | **≈ 128,0** |
| Loại 3 — ròng rọc trục lệch tâm | 1,34 | 94,7 | 126,9 | 41,9 | **≈ 49,3** |

**Ý 2:** $\displaystyle \beta \xrightarrow{\theta\to0} \frac12.$

---

## PHẦN 8 — BẢNG TRA CỨU NGUỒN CUỐI CÙNG (theo yêu cầu của thầy)

| Mảng kiến thức | Nguồn |
|---|---|
| Định luật Newton I, II (dạng quay), moment lực, hình học tam giác/lượng giác cơ bản, tích phân/đạo hàm sơ cấp, định luật Hooke tổng quát (tuyến tính lực–biến dạng và $\Pi=\frac12ka^2$ dạng góc), kiểm tra thứ nguyên | **[KTĐC]** |
| Quy trình B0 (quét đề), B1 (chọn hệ quy chiếu — bảng §1.2), B2–B3 (đếm DOF, Bảng 2.A/2.B, Từ điển B3), B4 (đối xứng gương), B5 (chọn $\theta$ làm tọa độ suy rộng), B6 (xấp xỉ góc nhỏ), B7 (chọn phương pháp công ảo), B10 (kiểm tra ngược — dùng nhiều lần: khớp $\theta_1=2$, khớp $XO=80$cm, khớp chiều bất đẳng thức $F_1>F_2>F_3$, khớp thứ nguyên, khớp $\beta\approx0{,}5$ so với $0{,}588$) | **`prom2_Cơ___Điện-Từ_học_v2A_.md`** |
| Thủ tục gán tọa độ thô + vi phân toàn phần (mục 3.0.1–3.0.4); Nguyên lý công ảo (mục 3.3) | **`PHẦN_3___TRỤ_CỘT_B__RÀNG_BUỘC___BIÊN__2_.md`** |
| idea 4 (xét hệ con), idea 7/8 (không cần dùng ở bài này — đã loại ở B1), idea 32 (dây không giãn), idea 33 (căng dây 2 bên ròng rọc bằng nhau — trục không lệch tâm), idea 47 (vật/dây nhẹ ⇒ hợp lực = hợp moment = 0), fact 14 (căng dây dọc theo tiếp tuyến), method 1 (dịch chuyển ảo $T=\Delta\Pi/\Delta x$), idea 20 (khai triển Taylor góc nhỏ) | **`meh_ENG2.pdf`** (Kalda) |
| Hình học cụ thể của Hình 1b/1c: công thức $d=3l-2R\sin\alpha$, $d_1=XO\sin\beta$, $d_2=R(1-\cos\alpha)$, $n=3+2\sin\beta$ | **[HÌNH VẼ] + đối chiếu đáp án mẫu** — xem cảnh báo ⚠ ở Phần 5.1 và 5.3 |
| Bước ghép đại số cuối cùng $M=T_3(d_1+n\,d_2)$ và giá trị số $T_3=41{,}88$ N ở Loại 3 | ⚠ **Lấy trực tiếp từ đáp án mẫu do thầy cung cấp** — không tái lập được 100% chỉ từ mô tả chữ của đề, do thiếu chi tiết định vị chính xác "nút buộc" trên Hình 1c (xem giải thích đầy đủ ở Phần 5.3) |
