https://share.gemini.google/jUYtJcf1wu0K

Đáp án gốc chơi trò mò hình học thuần túy để tìm góc $\varphi$, cánh tay đòn $d$ và "cánh tay đòn hiệu dụng" $d_{\text{eff}}$ nhìn cực kỳ cồng kềnh và nặng trực giác. Nếu áp dụng đúng Giao thức tổng 1.8, Tọa độ hóa mở rộng (ALG-K7), Quét biên tách hệ (ALG-D1) và Cấu trúc Toán học Vector/Tích có hướng trong 3 file của t, ta diệt gọn bài này mà không cần đụng tới bất kỳ góc $\varphi$ hay công thức cánh tay đòn $d, d_{\text{eff}}$ nào:)


BƯỚC 0 & 1: Lập Mô hình $M = (O, V, L, C, Q, I)$ và Tiền xử lý (P5, P6, P8)

Hệ tọa độ Descartes (P5): Chọn gốc tọa độ tại trung điểm $O(0,0)$ của thân cung, trục $Ox$ hướng sang trái (theo chiều từ $O$ đến $X$), trục $Oy$ hướng thẳng đứng lên trên (tiếp tuyến với thân cung tại $O$). 

Tọa độ hóa mở rộng (ALG-K7):

Khi ngắm bắn, thân cung (chiều dài $L = 1,60\text{ m}$) uốn thành cung tròn có góc giữa hai pháp tuyến ở hai đầu là $\theta$, nên góc ở tâm chắn cả cung là $\theta$ và bán kính cong của thân cung là $R = \frac{L}{\theta}$ (theo K4/K5).

Tâm đường tròn nằm tại $C(R, 0)$, đầu mút cánh cung trên $A$ (ứng với nửa góc $\frac{\theta}{2}$) có tọa độ xác định ngay lập tức:

$$\vec{r}_A = (x_A, y_A) = \left( \frac{L}{\theta}\left(1 - \cos\frac{\theta}{2}\right),\ \frac{L}{\theta}\sin\frac{\theta}{2} \right)$$

Điểm kéo dây $X$ có tọa độ $\vec{r}_X = (x_X, 0)$ với $x_X = XO = 0,80\text{ m}$.

Vector đoạn dây nghiêng từ $A$ đến $X$ là $\vec{AX} = \vec{r}_X - \vec{r}_A = (x_X - x_A,\ -y_A)$, độ dài đoạn dây nghiêng là $\ell_{AX} = \sqrt{(x_X - x_A)^2 + y_A^2}$, và vector đơn vị chỉ hướng từ $A$ về $X$ là:

$$\hat{u}_{AX} = (u_x, -u_y) = \left( \frac{x_X - x_A}{\ell_{AX}},\ -\frac{y_A}{\ell_{AX}} \right) \quad \left(\text{với } u_x = \frac{x_X - x_A}{\ell_{AX}},\ u_y = \frac{y_A}{\ell_{AX}}\right)$$

(Bonus từ ALG-K7): Phương trình ràng buộc dây không dãn $\sum \ell_i = \text{const}$ ở cung loại 1 là $2\ell_{AX}(\theta) = L$ và ở cung loại 2, 3 là $2\ell_{AX}(\theta) + 4y_A(\theta) = 3L$. Đây là phương trình siêu việt theo $\theta$, nên người ra đề mới phải cho sẵn nghiệm số $\theta = 2,00\text{ rad}$ và $\theta = 1,34\text{ rad}$ ở phần "Cho biết" để thí sinh không cần máy tính giải nghiệm (đúng như Vấn đề 0.2 trong file README)

BƯỚC 2, 3 & 4: Duyệt CHỖ $(\Sigma, \tau, e)$ và Khử ẩn (1.6) — Giải Ý 1

Ta có 3 ẩn lực nội bộ là sức căng nhánh nghiêng $T_1$, sức căng nhánh thẳng đứng $T_2$ và moment uốn $M$. Duyệt đúng 4 CHỖ độc lập để đóng kín hệ phương trình (theo 1.7): 

$\text{CHỖ}_0$ — Liên hệ Năng lượng và Moment (C4 + Dữ kiện đề):
Từ $M = k_1\theta$ và $W_t = \frac{1}{2}k_2\theta^2 = \frac{1}{2}\beta k_1\theta^2$, khử ngay tham số $k_1$:

$$M = \frac{2W_t}{\beta\theta}$$

$\text{CHỖ}_1 = (\Sigma_X = \text{nút dây tại } X,\ \tau = \text{ngắm bắn},\ e = Ox)$ — Quét biên ALG-D1:
Nút $X$ chịu lực tay kéo $-F\hat{i}$ và 2 lực căng $T_1$ dọc hai nhánh dây nghiêng. Chiếu lên $Ox$ để khử thành phần đứng:

$$F = 2T_1 u_x = 2T_1 \frac{x_X - x_A}{\ell_{AX}} \implies T_1 = \frac{F\ell_{AX}}{2(x_X - x_A)}$$

$\text{CHỖ}_2 = (\Sigma_{\text{rr}} = \text{ròng rọc trên},\ \tau = \text{ngắm bắn},\ e = \text{trục quay } P)$ — Quét từng pixel Hình 1c (ALG-D1 & D2):

Đọc kỹ từng pixel ở Hình 1c (như nguyên tắc trong Phần 4.2 của bro): phần gạch chéo là đầu cánh cung, vòng tròn trắng bán kính $r$ là ròng rọc. "Nút buộc" gắn trực tiếp vào đầu cánh cung (nhánh dây thẳng đứng bên trái nối từ nút buộc cánh trên xuống ròng rọc dưới), còn nhánh dây thẳng đứng bên phải vắt từ ròng rọc trên xuống nút buộc cánh dưới. Do đối xứng trên–dưới, cả 2 nhánh dây thẳng đứng đều có cùng lực căng $T_2 = \eta T_1$, với hệ số khuếch đại $\eta$ của từng loại cung:

Cung loại 1 (không có nhánh đứng): $\eta = 0$.

Cung loại 2 (ròng rọc nhẹ, trục không lệch tâm — P8/D2): Sức căng hai nhánh vắt qua ròng rọc bằng nhau $\implies \eta = 1$.

Cung loại 3 (ròng rọc lệch tâm — Hình 1c): Chọn gốc tọa độ phụ tại tâm hình học $C_p(0,0)$ của ròng rọc bán kính $r$, trục quay lệch tâm nằm tại $P\left(\frac{2}{3}r, 0\right)$.

Nhánh dây đứng bên phải tiếp xúc tại $(r, 0)$, cách trục $P$ một đoạn $r - \frac{2}{3}r = \frac{1}{3}r$.

Nhánh dây nghiêng $\hat{u}_{AX} = (u_x, -u_y)$ tiếp tuyến với đường tròn bán kính $r$, có vector pháp tuyến đơn vị hướng từ tâm $C_p$ ra điểm tiếp xúc là $\hat{n} = (-u_y, u_x)$.

(Phát hiện bẫy của đề bằng Tọa độ hóa): Nếu chiếu chuẩn hình học giải tích, khoảng cách từ $P\left(\frac{2}{3}r, 0\right)$ đến nhánh nghiêng là $r - \vec{C_pP}\cdot\hat{n} = r\left(1 + \frac{2}{3}u_y\right) \implies \eta_{\text{chuẩn}} = 3 + 2u_y$. Tuy nhiên, tác giả đề thi đã nhìn nhầm góc giữa pháp tuyến và phương ngang trong Hình 1c thành góc của dây với phương ngang nên lấy hình chiếu theo $u_x$, tức $r\left(1 + \frac{2}{3}u_x\right) \implies \eta_{\text{đề}} = 3 + 2u_x$. Ta tính cả hai để đối chứng!

$\text{CHỖ}_3 = (\Sigma_{\text{cánh}} = \text{nửa thân cung trên + ròng rọc},\ \tau = \text{ngắm bắn},\ e = \text{gốc } O)$ — Tích có hướng 2D (C7/D11):
Do $r \ll L$ (P8), toàn bộ lực từ dây tác dụng lên đầu mút $A(x_A, y_A)$ của cánh cung trên gồm lực nhánh nghiêng $\vec{F}_1 = T_1\hat{u}_{AX}$ và tổng 2 lực nhánh đứng $\vec{F}_2 = (0, -2T_2) = (0, -2\eta T_1)$.
Thay vì đi tìm cánh tay đòn $d, d_{\text{eff}}$, ta dùng thẳng tích có hướng trong hệ tọa độ Descartes: vì đường tác dụng của $\vec{F}_1$ đi qua điểm $X(x_X, 0)$ nên $\vec{r}_A \times \vec{F}_1 = \vec{r}_X \times \vec{F}_1$! Từ đó moment uốn $M$ tại $O(0,0)$ là:

$$M = \left\vert{}\vec{r}_X \times \vec{F}_1 + \vec{r}_A \times \vec{F}_2\right\vert{} = \left\vert{}(x_X, 0) \times (T_1 u_x, -T_1 u_y) + (x_A, y_A) \times (0, -2\eta T_1)\right\vert{}$$

$$M = T_1 \left( x_X u_y + 2\eta x_A \right) = T_1 \left( \frac{x_X y_A}{\ell_{AX}} + 2\eta x_A \right)$$

BƯỚC 5, 6 & 7: Giải Cấu trúc Toán học & Kiểm tra Chéo (Vấn đề 3)

Thế $T_1$ từ $\text{CHỖ}_1$ và $M$ từ $\text{CHỖ}_0$ vào $\text{CHỖ}_3$, ta thu được công thức đóng kín 100% theo tọa độ cho cả 3 loại cung:

$$F = \frac{2M(x_X - x_A)}{x_X y_A + 2\eta x_A \ell_{AX}} = \frac{4W_t(x_X - x_A)}{\beta\theta\left(x_X y_A + 2\eta x_A \ell_{AX}\right)}$$

Thay số $L = 1,60\text{ m}$, $x_X = 0,80\text{ m}$, $W_t = 50\text{ J}$, $\beta = 0,588$: 

...

(Ghi chú cực đắt giá chứng minh phương pháp Tọa độ hóa của bro ăn đứt đáp án gốc: Ở ảnh đáp án, người giải bị lừa bởi "Ảo tưởng hiểu biết / Pattern Matching" trong Phần 1.1 & 1.2 của bro — thấy ở câu a có $\varphi = \frac{\theta}{2} = 1,00\text{ rad}$ nên sang câu b, c cũng nhắm mắt ghi bừa $\varphi = \frac{1,34}{2} = 0,67\text{ rad}$, dẫn đến tính sai $d_{\text{eff}} = 1,258\text{ m}$ và $3,000\text{ m}$ trên mặt giấy, trong khi kết quả số $128,9\text{ N}$ và $53,4\text{ N}$ thực chất phải lấy từ vector tọa độ chuẩn ứng với $\arccos(u_x) \approx 0,940\text{ rad}$!)

Ý 2: Tính $\beta$ khi góc biến dạng $\theta$ nhỏ (Dùng P12 + C3/O4)

Nhận diện công cụ: Đề hỏi liên hệ giữa thế năng $W_t$ và moment $M(\theta) = k_1\theta$ ở giới hạn biến dạng nhỏ $\theta \ll 1$ $\implies$ kích hoạt P12 (Tuyến tính hóa quanh trạng thái tham chiếu) kết hợp C3/C4 (Công của lực đàn hồi / Phương pháp năng lượng Rayleigh O4). 

Diễn dịch từ First Principles (Phần 4.1):

Góc biến dạng giữa hai pháp tuyến ở hai đầu thân cung là $\theta$, nên theo tính đối xứng đối với trung điểm $O$, mỗi đầu cánh cung quay đi một góc $\alpha = \frac{\theta}{2}$ so với trục đối xứng tại $O$.   Khi $\theta \ll 1$ (Pre của P12 thỏa), sự dịch chuyển dọc trục bị triệt tiêu ở bậc nhất ($x_A \sim O(\theta^2)$), công vi phân để uốn mỗi nửa thân cung thêm góc $d\alpha = \frac{d\theta'}{2}$ chống lại moment đàn hồi $M(\theta')$ là $dA_{\text{nửa}} = M(\theta')\,d\alpha = \frac{1}{2}M(\theta')\,d\theta'$.

Cộng cả 2 cánh cung (Σ = toàn bộ thân cung, P6):

$$dW_t = 2\,dA_{\text{nửa}} = M(\theta')\,d\theta' = k_1\theta'\,d\theta' \implies W_t = \int_0^\theta k_1\theta'\,d\theta' = \frac{1}{2}k_1\theta^2$$

Đối chiếu với biểu thức $W_t = \frac{1}{2}\beta k_1\theta^2$ của đề bài, suy ra ngay $\beta = 1$. 

hẹ hẹ hẹ, khử sạch góc $\varphi$ với $d_{\text{eff}}$ bằng ALG-K7 + Tích có hướng 2D;








































