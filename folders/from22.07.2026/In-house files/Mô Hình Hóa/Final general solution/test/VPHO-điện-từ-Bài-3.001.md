BƯỚC 0: Quét văn bản & hình ảnh (B0 - Trích xuất dữ kiện)

Học sinh sẽ không lao vào tính toán ngay mà lấy bút gạch chân các "từ khóa" mang tính định hình mô hình:

"$\sqrt{S} \gg a$": Dấu hiệu kinh điển. Kích thước bản cực rất lớn so với khoảng cách $\Rightarrow$ coi như các mặt phẳng vô hạn.

"$\delta \ll a$": Từ khóa gọi ngay Trụ cột D (B6 - Xấp xỉ hóa) ra làm việc. Khi tính toán các đại lượng vĩ mô chiều dài lớn, $\delta$ có thể bị bỏ qua so với $a$.

"Trạng thái ổn định, các ion... không còn chuyển động có hướng": Từ khóa vàng của B8 (Điều kiện biên ngầm định). Dòng điện vĩ mô bằng $0 \Rightarrow$ Điện trường tổng cộng trong dung dịch (vùng 2) phải bằng $0$.

Đồ thị Hình 3b: Đọc đồ thị không phải nhìn hình dáng, mà phải đọc "bước nhảy" (jump). Tại $t=0$, $I$ nhảy lên $33\text{ A}$, $U$ lập tức nảy lên $0.05\text{ V}$ dù tụ chưa kịp tích điện. Tại $t=14.5\text{ s}$, $U$ tụt từ $1.50\text{ V}$ xuống $1.45\text{ V}$.

BƯỚC 9: Bắt đầu giải quyết từng phần (B9 - Giải hệ)

Ý 1: Xác định điện trường trong các vùng 1, 2, 3

Dựa vào kiến thức nền tảng (nguyên lý xếp chồng), hệ này thực chất là 4 mặt phẳng tích điện vô hạn đặt song song nhau tại các tọa độ: $x = -a$ (điện tích $-\sigma$), $x = -a+\delta$ (điện tích $+\sigma'$), $x = a-\delta$ (điện tích $-\sigma'$), $x = a$ (điện tích $+\sigma$).

Chọn chiều dương của trục $Ox$ hướng từ trái sang phải. Điện trường do một mặt phẳng vô hạn gây ra có độ lớn $E = \sigma_0 / (2\varepsilon_0\varepsilon)$, hướng ra xa nếu mang điện dương và hướng lại gần nếu mang điện âm.

Ta xét hình chiếu điện trường của 4 mặt phẳng lên trục $Ox$:

Vùng 1 (giữa $-a$ và $-a+\delta$):

Nằm bên phải mặt $-\sigma$ và bên trái 3 mặt còn lại.

$$E_1 = E_{(-\sigma)} + E_{(+\sigma')} + E_{(-\sigma')} + E_{(+\sigma)}$$

$$E_1 = \left( -\frac{\sigma}{2\varepsilon_0\varepsilon} \right) + \left( -\frac{\sigma'}{2\varepsilon_0\varepsilon} \right) + \left( +\frac{\sigma'}{2\varepsilon_0\varepsilon} \right) + \left( -\frac{\sigma}{2\varepsilon_0\varepsilon} \right) = -\frac{\sigma}{\varepsilon_0\varepsilon}$$

$\Rightarrow$ Điện trường Vùng 1 có độ lớn $E_1 = \frac{\sigma}{\varepsilon_0\varepsilon}$, hướng ngược chiều dương trục $Ox$.

Vùng 2 (giữa $-a+\delta$ và $a-\delta$):

Nằm giữa mặt $+\sigma'$ và mặt $-\sigma'$.

$$E_2 = \left( -\frac{\sigma}{2\varepsilon_0\varepsilon} \right) + \left( +\frac{\sigma'}{2\varepsilon_0\varepsilon} \right) + \left( +\frac{\sigma'}{2\varepsilon_0\varepsilon} \right) + \left( -\frac{\sigma}{2\varepsilon_0\varepsilon} \right) = \frac{\sigma' - \sigma}{\varepsilon_0\varepsilon}$$

Vùng 3 (giữa $a-\delta$ và $a$):


Do tính đối xứng của hệ (hoặc tính tương tự Vùng 1):

$$E_3 = \left( -\frac{\sigma}{2\varepsilon_0\varepsilon} \right) + \left( +\frac{\sigma'}{2\varepsilon_0\varepsilon} \right) + \left( -\frac{\sigma'}{2\varepsilon_0\varepsilon} \right) + \left( -\frac{\sigma}{2\varepsilon_0\varepsilon} \right) = -\frac{\sigma}{\varepsilon_0\varepsilon}$$

$\Rightarrow$ Điện trường Vùng 3 có độ lớn $E_3 = \frac{\sigma}{\varepsilon_0\varepsilon}$, hướng ngược chiều dương.

Ý 2: Xác định biểu thức của Điện dung $C$

Kích hoạt dữ kiện từ B8: Ở trạng thái ổn định, ion không di chuyển $\Rightarrow$ Điện trường trong Vùng 2 (dung dịch điện li) triệt tiêu.


$$E_2 = 0 \Rightarrow \frac{\sigma' - \sigma}{\varepsilon_0\varepsilon} = 0 \Rightarrow \sigma' = \sigma$$

(Lớp ion màng triệt tiêu hoàn toàn điện trường của 2 bản cực bên trong dung dịch).

Hiệu điện thế $U$ giữa hai bản cực tụ điện bằng tổng độ giảm thế qua 3 vùng:

$$U = \vert{}V(a) - V(-a)\vert{} = E_1 \cdot \delta + E_2 \cdot (2a - 2\delta) + E_3 \cdot \delta$$

$$U = \left( \frac{\sigma}{\varepsilon_0\varepsilon} \right) \cdot \delta + 0 + \left( \frac{\sigma}{\varepsilon_0\varepsilon} \right) \cdot \delta = \frac{2\sigma\delta}{\varepsilon_0\varepsilon}$$

Điện tích của tụ điện là điện tích trên bản cực dương: $Q = \sigma S$.


Biểu thức điện dung:

$$C = \frac{Q}{U} = \frac{\sigma S}{\frac{2\sigma\delta}{\varepsilon_0\varepsilon}} = \frac{\varepsilon_0\varepsilon S}{2\delta}$$

(Bước B10 - Kiểm tra ngược: Kết quả này tương đương với 2 tụ điện phẳng có bề dày $\delta$ ghép nối tiếp. Vùng 2 đóng vai trò như một dây dẫn nối 2 tụ này. Rất hợp lý với vật lý trực giác!)

Ý 3a: Biểu thức $R_0$

Vùng 2 chứa chất điện li đóng vai trò là điện trở thuần nối tiếp với 2 "tụ điện màng" ở hai bên.
Áp dụng công thức điện trở của một vật dẫn hình trụ: $R = \frac{l}{\gamma S}$.

Chiều dài của Vùng 2 là $l = (a - \delta) - (-a + \delta) = 2a - 2\delta$.
Sử dụng B6 (Xấp xỉ hóa): Vì $\delta \ll a$ nên $l \approx 2a$.

Vậy, biểu thức điện trở là:

$$R_0 = \frac{2a}{\gamma S}$$

Ý 3b: Xác định $C$ và $R_0$ bằng đồ thị

Mô hình mạch lúc này là Mạch RC nối tiếp với nguồn dòng không đổi $I = 33\text{ A}$.
Phương trình hiệu điện thế toàn mạch:

$$U_{mạch}(t) = U_R + U_C(t) = I \cdot R_0 + \frac{1}{C} \int_{0}^{t} I dt = I R_0 + \frac{I}{C}t$$

Tại $t = 0$: Tụ chưa tích điện ($U_C = 0$). Dòng $I$ vừa bật lên $33\text{ A}$ lập tức tạo ra sụt áp trên điện trở $R_0$.

Từ đồ thị: $U(0) = 0.05\text{ V}$.

$\Rightarrow I \cdot R_0 = 0.05 \Rightarrow 33 \cdot R_0 = 0.05 \Rightarrow R_0 = \frac{0.05}{33} \approx 1.52 \times 10^{-3}\ \Omega$.

(Có thể đối chiếu lại bằng cách nhìn vào lúc $t = 14.5\text{ s}$, khi ngắt dòng điện $I$, hiệu điện thế tụt ngay một lượng $\Delta U = 1.50 - 1.45 = 0.05\text{ V}$, chính là mất đi $U_R$).

Tính $C$: Đoạn đồ thị dốc lên biểu diễn quá trình nạp điện của tụ. Hiệu điện thế trên tụ tăng tuyến tính.

Tại $t = 14.5\text{ s}$, hiệu điện thế trên riêng tụ điện là $U_C = 1.45\text{ V}$ (do phần $0.05\text{ V}$ là của $R_0$).

Điện tích nạp được sau $14.5\text{ s}$ là: $Q = I \cdot t = 33 \cdot 14.5 = 478.5\text{ C}$.

Điện dung của tụ là:

$$C = \frac{Q}{U_C} = \frac{478.5}{1.45} = 330\text{ F}$$

---

Đối chiếu từng phần với Elekter.pdf:

**Ý 1 (E ở vùng ①②③)**

Yêu cầu : Chồng chất trường từ 4 mặt tích điện phẳng vô hạn

Có nguyên lý (§3.3) + bài mẫu 2 mặt/1 tụ (ul. 67–68, chính là công thức đề bài cho sẵn). Nhưng chưa có bài mẫu 4 mặt — học sinh phải tự tổng quát hoá cách theo dõi dấu.

**Ý 2 (C_0)**

Yêu cầu : Nhận ra trạng thái dừng ⟺ E_② = 0 ⟺ σ′ = σ, rồi ghép 2 tụ nối tiếp

Công thức C = (ε ε_0 S) / d​ và ghép nối tiếp C = (1/C_1​+1/C_2​)^(-1) có sẵn (ul. 48, 92a). Nhưng bước suy luận vật lý "ion hết di chuyển ⟹ trường vùng ② = 0" không được dạy tường minh — đây là chỗ đòi hỏi tự kết nối, đúng kiểu B8 trong file .md có gợi ý ("ổn định ⟹ đạo hàm → 0") nhưng không có công thức cụ thể.
















