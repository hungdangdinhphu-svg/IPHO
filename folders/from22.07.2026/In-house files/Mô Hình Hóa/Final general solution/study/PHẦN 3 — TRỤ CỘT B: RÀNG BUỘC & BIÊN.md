Lưu ý : Tài liệu bên dưới giả định rằng mọi ràng buộc hình học đều đưa được về dạng holonom, chứ không bao gồm Non-holonomic Constraints. Hoặc Ràng buộc một phía (Unilateral Constraints / Inequality Constraints), Ràng buộc biến dạng & Biên dạng liên tục động, Ràng buộc do đề bài tự sáng tạo (Novel/Exotic Constraints),...v.v

> **Cách dùng file này:** thay thế toàn bộ khối *"Thủ tục (ver 2)"* + hộp *"Vấn đề phát sinh 3.1"* hiện có trong PHẦN 3 của tài liệu gốc bằng nội dung dưới đây. Các mục §3.1 (Frobenius), §3.2 (Từ điển B3), §3.3 (ràng buộc mạch điện) giữ nguyên — thủ tục mới bên dưới **gọi tới** chúng chứ không thay thế.

---

## 0. Chẩn đoán chính xác: lỗ hổng nằm ở đâu, không phải ở đâu

Xét lại 4 bước của "ver 2":

| Bước | Nội dung | Có đòi hỏi trực giác không? |
|---|---|---|
| 1. Gán tọa độ thô bạo | Vẽ trục $(x,y)$, đặt tên điểm | **Không** — thuần cơ học |
| 2. Viết phương trình hình học | *"Tìm đại lượng bị ràng buộc... viết $f(q)=C$"* | **CÓ** — đây chính là chỗ yêu cầu "nhìn ra" |
| 3. Vi phân toàn phần | Áp công thức $df=\sum \partial f/\partial q_i\,\delta q_i$ | Không — thuần toán |
| 4. Rút gọn Pfaff | Nhóm số hạng | Không — thuần toán |

Vậy **toàn bộ vấn đề nằm gọn trong 5 chữ "tìm đại lượng bị ràng buộc"** ở Bước 2. Không cần sửa Bước 1, 3, 4. Chỉ cần biến Bước 2 từ "suy luận" thành "tra cứu".

**Chìa khóa:** tập hợp loại ràng buộc hình học có thể xuất hiện trong $\mathcal P_{\text{IPhO}}$ là **hữu hạn và đã được liệt kê sẵn** — chính là Bảng 2.B (đã có trong tài liệu, dùng để đếm DOF). Nghĩa là **học sinh đã phải nhận diện loại ràng buộc này một lần rồi, ở B2 bước 2, khi tra Bảng 2.B để trừ DOF.** Lỗi thiết kế của ver 2 là bắt học sinh nhận diện lại **lần thứ hai** một cách tự do (không có bảng tra) chỉ để viết ra phương trình. Cách sửa: **hợp nhất hai lần nhận diện thành một**, bằng cách gắn thêm một cột "phương trình mẫu" ngay vào Bảng 2.B (nay gọi là Bảng B3.4). Từ đó, mỗi lần học sinh tra Bảng 2.B để trừ DOF, họ **đồng thời** có luôn phương trình để viết — không có bước nhận diện nào bị lặp lại, không có bước nào cần "linh cảm".

---

## 1. Thủ tục (ver 3) — 6 bước, không bước nào cần trực giác

**B3.0 — Liệt kê điểm chốt (thủ tục 5 dòng)**

Một "điểm chốt" là bất kỳ điểm nào thỏa **ít nhất một** trong các điều kiện sau (kiểm tra được, không mơ hồ):

1. Với **mỗi vật rắn** đã đếm ở B2 bước 1: điểm chốt là **bộ ba tọa độ thô** của nó, $(x_C,y_C,\theta)$ nếu là vật rắn 2D, hoặc chỉ $(x,y)$ nếu là chất điểm — lấy nguyên từ Bảng 2.A, không cần đặt thêm.
2. Với **mỗi cặp vật có tương tác hình học** mà bạn đã tra Bảng 2.B ở B2 bước 2 (dây, thanh, bản lề, tiếp xúc, lăn...): điểm chốt là **điểm vật lý nơi tương tác đó xảy ra** (hai đầu dây, vị trí khớp, điểm tiếp xúc...).
3. Với **mỗi điểm neo cố định trong không gian** (tường, trần, sàn, tâm ròng rọc gắn cố định): 1 điểm chốt "tĩnh", tọa độ là hằng số đã biết hoặc đặt tên.
4. **Biến mục tiêu** (đã gạch chân ở B0) luôn phải quy được về tọa độ của ít nhất một điểm chốt đã liệt kê — nếu chưa, bổ sung điểm đó.

> **Vì sao bước này không cần trực giác:** danh sách ở dòng 1 và 2 **đã có sẵn** — đó chính xác là hai danh sách bạn vừa lập xong ở B2 (Bảng 2.A và Bảng 2.B). B3.0 không tạo ra thông tin mới, chỉ **đặt tên điểm** cho thông tin đã có.

**B3.1 — Gán tọa độ thô**

Lập bảng: | Điểm chốt | Loại (tĩnh / vật rắn / chất điểm) | Tọa độ | — điền $(x,y)$ hoặc $(x,y,\theta)$ cho từng dòng ở B3.0. Điểm tĩnh: điền số hoặc hằng số đã biết. Điểm động: điền ký hiệu ẩn.

**B3.2 — Tra Bảng B3.4 (§3 dưới đây), chép phương trình**

Với **từng dòng bạn đã tra ở Bảng 2.B (B2 bước 2)** — không thêm, không bớt — mở Bảng B3.4, tìm đúng dòng có cùng tên loại ràng buộc, **chép nguyên mẫu phương trình**, thay ký hiệu điểm chốt tương ứng vào. Không có phép "chọn" hay "đoán" nào ở bước này — chỉ có tra cứu và thay thế ký hiệu.

**B3.3 — Vi phân toàn phần** *(y hệt ver 2, không đổi)*

$$df = \sum_i \frac{\partial f}{\partial q_i}\delta q_i = 0$$

**B3.4 — Rút gọn dạng Pfaff** *(y hệt ver 2, không đổi)*

Nhóm các $\delta q_i$, chia cho $dt$ nếu cần liên hệ vận tốc.

**B3.5 — Kiểm tra chéo (bước mới, thay cho "hy vọng đã đúng")**

Đếm số phương trình vừa viết ra ở B3.2. Con số này **bắt buộc phải bằng đúng** $k_{\text{hình học}}$ mà bạn đã tính ở B2 bước 2 (tổng DOF khử theo Bảng 2.B). Nếu lệch:
- **Thiếu** ⇒ bạn đã bỏ sót một dòng của Bảng 2.B ở B2 — quay lại B0, kiểm tra xem còn tính từ/cặp vật nào chưa gạch chân.
- **Thừa** ⇒ hai dòng bạn tra thực ra diễn đạt cùng một ràng buộc (trùng lặp) — thường gặp khi bản lề và một ràng buộc khoảng cách được đếm hai lần cho cùng một cặp điểm.

> Đây là điểm khác biệt cốt lõi so với ver 2: ver 2 không cho cách nào để *biết mình đã viết đủ phương trình chưa* ngoài cảm giác. Ver 3 cho một con số cụ thể để đối chiếu, lấy thẳng từ B2 — không cần thêm giả định nào.

**Kết luận cho Vấn đề phát sinh 3.1:** "làm sao viết được phương trình hình học mà gần như không cần trực giác" được trả lời bằng cách **không đòi hỏi một bước nhận diện nào mới cả** — toàn bộ khối lượng nhận diện đã được dồn về đúng **một** chỗ duy nhất (tra Bảng 2.B ở B2), và B3 chỉ là **tra cứu lại chính kết quả đó** trong một bảng mở rộng (B3.4) để lấy phương trình thay vì chỉ lấy con số DOF. Vì Bảng 2.B là $G_k$ (tổng-quát-hữu-hạn, liệt kê trọn vẹn trên $\mathcal P_{\text{IPhO}}$ — đã chứng minh ở §2.2 gốc), nên Bảng B3.4 (chỉ là Bảng 2.B cộng thêm 1 cột) cũng $G_k$ theo đúng nghĩa đó.

---

## 2. Bảng B3.4 — Thư viện tra cứu trực tiếp (mở rộng Bảng 2.B)

Cột "Loại ràng buộc" **giữ nguyên tên** như trong Bảng 2.B để tra song song dễ dàng.

| # | Loại ràng buộc (= tên dòng trong Bảng 2.B) | Điểm chốt cần | Phương trình mẫu — chép trực tiếp | Ghi chú |
|---|---|---|---|---|
| 1 | Dây/thanh cứng nối 2 điểm bất kỳ | $P_i(x_i,y_i)$, $P_j(x_j,y_j)$ | $(x_j-x_i)^2+(y_j-y_i)^2=L^2$ | Luôn dùng bình phương khoảng cách, không căn |
| 2 | Dây qua $k$ ròng rọc lý tưởng | Chuỗi điểm theo đúng thứ tự dây đi qua: $P_0,P_1,\dots,P_{k+1}$ (2 đầu dây + tâm mỗi ròng rọc) | $\displaystyle\sum_{n=0}^{k}\sqrt{(x_{n+1}-x_n)^2+(y_{n+1}-y_n)^2}=L$ | Ròng rọc chỉ đổi hướng, không thêm ẩn; `[MEH]` idea 32, 33 |
| 3 | Bản lề (khớp trụ) nối 2 vật rắn tại 1 điểm | Vật A: $(x_A,y_A,\theta_A)$, offset khớp trong khung A: $(a,b)$; vật B tương tự $(x_B,y_B,\theta_B)$, offset $(c,d)$ | $x_A+a\cos\theta_A-b\sin\theta_A = x_B+c\cos\theta_B-d\sin\theta_B$ <br> $y_A+a\sin\theta_A+b\cos\theta_A = y_B+c\sin\theta_B+d\cos\theta_B$ | Công thức quay `[MEH]` idea 28; nếu gốc tọa độ vật đặt ngay tại khớp thì $a=b=c=d=0$, rút về $x_A=x_B,\ y_A=y_B$ |
| 4 | Ngàm cứng (rigid weld) | như dòng 3 | 2 phương trình như dòng 3, **cộng thêm** $\theta_A-\theta_B=\text{const}$ | 3 phương trình, khớp đúng "3 DOF khử (2D)" ở Bảng 2.B |
| 5 | Con trượt trong rãnh thẳng cố định (prismatic) | Vật rắn $(x,y,\theta)$; rãnh cho bởi đường thẳng cố định $n_x x+n_y y=c$, hướng rãnh $\theta_0$ | $n_x x+n_y y=c$ <br> $\theta-\theta_0=\text{const}$ | 2 phương trình; nếu chọn trục sao cho rãnh nằm ngang: $y=\text{const},\ \theta=\text{const}$ |
| 6 | Chất điểm ràng buộc trên đường cong **cố định** $F(x,y)=0$ | $P(x,y)$ | $F(x,y)=0$ | Thay thẳng tọa độ điểm vào phương trình đường cong đã cho |
| 7 | Chất điểm/khớp ràng buộc trên đường cong gắn liền một **vật rắn khác đang chuyển động** | Vật mang đường cong: $(x_{\text{body}},y_{\text{body}},\theta_{\text{body}})$; hình dạng đường cong trong khung riêng của vật: $(g_1(s),g_2(s))$, $s$ = tham số tự do mới (thường là độ dài cung) | $x_P=x_{\text{body}}+g_1(s)\cos\theta_{\text{body}}-g_2(s)\sin\theta_{\text{body}}$ <br> $y_P=y_{\text{body}}+g_1(s)\sin\theta_{\text{body}}+g_2(s)\cos\theta_{\text{body}}$ | Đây là dạng **định nghĩa tọa độ** (không phải phương trình $=0$): khử đúng 1 DOF của $P$ vì $P$ giờ chỉ còn phụ thuộc 1 ẩn mới $s$ thay vì 2 ẩn $(x_P,y_P)$. Dùng khi khối trượt trên mặt nêm, hạt trên thanh quay, v.v. |
| 8 | Lăn không trượt trên đường thẳng cố định | Tâm vật lăn $(x_C,y_C,\theta)$, bán kính $R$ | (a) giữ tiếp xúc: $y_C=R$ (thường đã chọn trục để mặc định đúng, không tính là ẩn phải khử thêm) <br> (b) lăn: $x_C-R\theta=\text{const}$ | **Bắt buộc kiểm tra Định lý B trước khi dùng (b)** — xem §3.1 gốc, đã tự động đúng trên đường thẳng |
| 9 | Lăn không trượt trên mặt cong cố định | $s$ = cung đã lăn qua trên mặt cong, $\theta$ = góc quay vật | $s-R\theta=\text{const}$ | Tương tự dòng 8, theo tọa độ cung |
| 10 | Tiếp xúc trượt tự do (không ma sát) giữa 2 biên dạng cho trước, tham số hoá $(x_A(t),y_A(t))$ và $(x_B(u),y_B(u))$ | 2 tham số cong $t,u$ | (i) chạm nhau: $x_A(t)=x_B(u),\ y_A(t)=y_B(u)$ <br> (ii) pháp tuyến trùng phương (tiếp tuyến song song): $x_A'(t)y_B'(u)-y_A'(t)x_B'(u)=0$ | Trường hợp tổng quát nhất trong cơ; 3 phương trình cho 2 ẩn mới $(t,u)$ + vị trí ⇒ khử đúng 1 DOF thực (còn 1 biến tự do chạy dọc bề mặt) |
| 11 | Vật cô lập về điện | $Q(t)$ | $Q=\text{const}$ | Đã có sẵn ở §3.2/§3.3 gốc, không cần sửa |
| 12 | Nút mạch (Kirchhoff I) | dòng $I_n$ tại nút | $\sum_n I_n=0$ | Đã có sẵn ở §3.3 gốc |
| 13 | Vòng siêu dẫn | từ thông $\Phi$ | $\Phi=\text{const}$ | Đã có sẵn ở §3.3 gốc |

**Ba lưu ý bắt buộc khi dùng bảng:**

- **Dòng 3–4–5–7** dùng công thức quay `[MEH]` idea 28: $x'=x\cos\varphi-y\sin\varphi,\ y'=y\cos\varphi+x\sin\varphi$. Chép nguyên, không cần hiểu "tại sao" mới dùng được.
- **Dòng 2**: nếu đề bài nói "dây được cuốn/thả thêm một đoạn $\ell(t)$" (ròng rọc có mô-tơ, hoặc dây tự xả như `[MEH]` pr 32/47), chỉ cần đổi vế phải $L\to L(t)=L_0-\ell(t)$, phần còn lại của mẫu giữ nguyên.
- Nếu một ràng buộc **không khớp dòng nào** trong bảng, xem §3 (thủ tục dự phòng) — đây là trường hợp hiếm, không phải trường hợp mặc định.

---

## 3. Thủ tục dự phòng (khi không có dòng nào trong Bảng B3.4 áp dụng)

Đây là bản siết chặt của "phép dịch chuyển ảo" (ver 2), buộc phải đi qua Từ điển B3 thay vì "cảm giác vật lý" tự do:

1. Xác định 2 (hoặc nhiều) điểm chốt biên của ràng buộc đang nghi ngờ.
2. Quay lại **Từ điển B3 (Bảng 3.2, đã có sẵn trong tài liệu)**: tìm tính từ/cụm từ trong đề bài mô tả ràng buộc này (ví dụ "không giãn", "diện tích quét không đổi", "thể tích khí không đổi"...). Đại lượng không đổi **phải trùng với vế "Ý nghĩa toán học chính xác"** ghi trong Từ điển B3 ứng với tính từ đó.
3. Nếu **không tìm được dòng nào trong Từ điển B3** khớp với mô tả đề bài ⇒ đây có thể **không phải là một ràng buộc thật sự** — dừng lại, quay về B2 để xác nhận trước khi viết bất kỳ phương trình nào (tránh lỗi kinh điển: thêm ràng buộc không có thật, làm hệ trở thành siêu tĩnh giả).
4. Nếu tìm được, viết chính đại lượng đó dưới dạng $f(\text{tọa độ các điểm chốt})=C$, rồi làm B3.3–B3.5 như bình thường.

Việc bắt buộc đi qua Từ điển B3 (một bảng hữu hạn, đã liệt kê) thay vì hỏi "cái gì thấy hợp lý là không đổi" loại bỏ nốt phần trực giác còn sót lại ngay cả ở trường hợp dự phòng này.

---

## 4. Ví dụ kiểm chứng đầy đủ B3.0 → B3.5

Dùng lại **Ví dụ 1** đã có trong Phần 9 gốc (`[MEH]` pr 26: khối $m$ trên nêm $M$ góc $\alpha$, nêm trượt tự do trên sàn trơn, dây nối $m$ qua ròng rọc ở đỉnh nêm rồi buộc vào tường), để chứng minh thủ tục ver 3 chạy được **không cần một lần "nhìn ra" nào**.

**B3.0 — điểm chốt** (theo đúng 4 dòng của thủ tục):
- Vật rắn "nêm": $(x_M,y_M,\theta_M)$ — dòng 1.
- Vật "khối $m$" (coi là chất điểm): $(x_m,y_m)$ — dòng 1.
- Tương tác 1 (nêm trượt trên sàn, tra Bảng 2.B ra "con trượt trong rãnh thẳng cố định"): điểm chốt là chính $(x_M,y_M,\theta_M)$ đã có.
- Tương tác 2 (khối $m$ tựa trên mặt nêm, tra Bảng 2.B ra "chất điểm trên đường cong gắn liền vật khác"): điểm chốt là $(x_m,y_m)$ đã có, cộng thêm điểm quy chiếu trên nêm — chọn trùng gốc tọa độ nêm để đơn giản, đặt là đỉnh nêm (nơi có ròng rọc).
- Tương tác 3 (dây qua ròng rọc, buộc vào tường): điểm chốt là đỉnh nêm (tâm ròng rọc, = gốc tọa độ nêm), và điểm neo trên tường $P_{\text{wall}}=(X_w, h)$ cố định.

**B3.1 — gán tọa độ:** chọn sàn là $y=0$, trục $x$ nằm ngang. Vì nêm không rơi/không lật: $y_M=0,\ \theta_M=0$ suốt quá trình (đã biết trước là hằng số nhờ chính ràng buộc "trượt trên sàn"). Đỉnh nêm (điểm chốt gắn liền nêm) ở tọa độ $(x_M, h)$ với $h$ = chiều cao nêm, hằng số hình học đã cho. Khối $m$: $(x_m,y_m)$, ẩn.

**B3.2 — tra bảng, chép phương trình:**

- Dòng 5 (con trượt): $y_M=0,\ \theta_M=0$ — 2 phương trình, đã dùng ngay để đơn giản hoá các bước sau.
- Dòng 7 (điểm trên đường cong gắn liền vật khác): mặt nêm trong khung riêng của nêm là đường thẳng $g_1(s)=s\cos\alpha,\ g_2(s)=-s\sin\alpha$ ($s\ge 0$ là khoảng cách từ đỉnh nêm dọc mặt nghiêng). Với $\theta_M=0$: 
$$x_m = x_M + s\cos\alpha,\qquad y_m = h - s\sin\alpha.$$
— 1 tham số mới $s$ thay cho 2 ẩn $(x_m,y_m)$: khử đúng 1 DOF.
- Dòng 2 (dây qua 1 ròng rọc): chuỗi điểm là [khối $m$] → [đỉnh nêm] → [tường]:
$$\underbrace{s}_{\text{đoạn }m\to\text{đỉnh, đúng bằng }s\text{ theo cách dựng ở trên}} + \underbrace{(X_w-x_M)}_{\text{đoạn ngang tới tường}} = L.$$

**B3.3 — vi phân toàn phần:** từ phương trình dây: $\delta s+(-\delta x_M)=0\Rightarrow \delta s=\delta x_M$ (tức $\dot s=\dot x_M$).

**B3.5 — kiểm tra chéo:** Raw DOF $=3\ (\text{nêm, Bảng 2.A}) + 2\ (\text{chất điểm }m) = 5$. Số ràng buộc vừa viết: dòng 5 (2) + dòng 7 (1) + dòng 2 (1) $=4$. $f_{\text{eff}}=5-4=1$ — **khớp chính xác** với "$f_{\text{eff}}=1$, lấy $\xi=x_M$" đã nêu ở Ví dụ 1 gốc, và hệ thức $\dot s=\dot x_M$ tìm được cũng khớp với gợi ý hint gốc của `[MEH]` pr 26 ("nếu nêm dịch $\xi$ thì khối dịch cùng lượng đó so với nêm").

Không có bước nào trong ví dụ trên yêu cầu "nhìn ra" — mỗi phương trình đều được chép thẳng từ Bảng B3.4 sau khi đã có sẵn danh sách điểm chốt từ B2.

---

## 5. Hệ quả phụ (không mở rộng, chỉ ghi chú)

Vì Bảng B3.4 chỉ là Bảng 2.B cộng thêm cột phương trình, việc hợp nhất B2–B3 nói trên **cũng tự động thu hẹp phần "Vấn đề phát sinh 2.1"** (viết phương trình hình học ở bước đếm DOF) xuống còn đúng cùng một bảng tra duy nhất — tuy bạn chỉ yêu cầu sửa Phần 3, nhưng vì hai vấn đề dùng chung một cơ chế nên tiện thể ghi nhận ở đây để tài liệu không bị mâu thuẫn nội bộ giữa Phần 2 và Phần 3 nữa.
