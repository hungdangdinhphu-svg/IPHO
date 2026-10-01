
# TỔNG HỢP CÔNG THỨC HÌNH HỌC CẦN THIẾT CHO HSGQG VẬT LÝ

*(Không bao gồm Giải tích — chỉ Hình học phẳng, Hình học không gian, Lượng giác, Vector và các đường Conic)*

---

## 1. LƯỢNG GIÁC CƠ BẢN (nền tảng cho mọi phần)

### 1.1. Hệ thức cơ bản
- $\sin^2\alpha + \cos^2\alpha = 1$
- $\tan\alpha = \dfrac{\sin\alpha}{\cos\alpha}$, $\cot\alpha = \dfrac{\cos\alpha}{\sin\alpha}$
- $1 + \tan^2\alpha = \dfrac{1}{\cos^2\alpha}$
- $1 + \cot^2\alpha = \dfrac{1}{\sin^2\alpha}$

### 1.2. Công thức cộng
- $\sin(a \pm b) = \sin a\cos b \pm \cos a\sin b$
- $\cos(a \pm b) = \cos a\cos b \mp \sin a\sin b$
- $\tan(a \pm b) = \dfrac{\tan a \pm \tan b}{1 \mp \tan a\tan b}$

### 1.3. Công thức nhân đôi, hạ bậc
- $\sin 2a = 2\sin a\cos a$
- $\cos 2a = \cos^2a - \sin^2a = 2\cos^2a - 1 = 1 - 2\sin^2a$
- $\tan 2a = \dfrac{2\tan a}{1 - \tan^2 a}$
- $\sin^2 a = \dfrac{1 - \cos 2a}{2}$, $\cos^2 a = \dfrac{1 + \cos 2a}{2}$

### 1.4. Công thức nhân ba
- $\sin 3a = 3\sin a - 4\sin^3 a$
- $\cos 3a = 4\cos^3 a - 3\cos a$

### 1.5. Biến đổi tổng thành tích
- $\sin a + \sin b = 2\sin\dfrac{a+b}{2}\cos\dfrac{a-b}{2}$
- $\sin a - \sin b = 2\cos\dfrac{a+b}{2}\sin\dfrac{a-b}{2}$
- $\cos a + \cos b = 2\cos\dfrac{a+b}{2}\cos\dfrac{a-b}{2}$
- $\cos a - \cos b = -2\sin\dfrac{a+b}{2}\sin\dfrac{a-b}{2}$

### 1.6. Biến đổi tích thành tổng
- $\sin a\cos b = \dfrac{1}{2}[\sin(a+b) + \sin(a-b)]$
- $\cos a\cos b = \dfrac{1}{2}[\cos(a-b) + \cos(a+b)]$
- $\sin a\sin b = \dfrac{1}{2}[\cos(a-b) - \cos(a+b)]$

### 1.7. Xấp xỉ góc nhỏ (hay dùng trong Vật lý)
- $\sin\alpha \approx \alpha$, $\tan\alpha \approx \alpha$, $\cos\alpha \approx 1 - \dfrac{\alpha^2}{2}$ (với $\alpha$ tính bằng radian, $\alpha \ll 1$)

---

## 2. HỆ THỨC LƯỢNG TRONG TAM GIÁC

Cho tam giác $ABC$ với cạnh $a, b, c$ đối diện các góc $A, B, C$; $R$ là bán kính đường tròn ngoại tiếp, $r$ là bán kính đường tròn nội tiếp, $p = \dfrac{a+b+c}{2}$ là nửa chu vi.

### 2.1. Định lý sin
$$\dfrac{a}{\sin A} = \dfrac{b}{\sin B} = \dfrac{c}{\sin C} = 2R$$

### 2.2. Định lý cos
$$a^2 = b^2 + c^2 - 2bc\cos A$$
(và các hoán vị tương ứng)

### 2.3. Định lý tan (công thức Mollweide/tangent)
$$\tan\dfrac{A-B}{2} = \dfrac{a-b}{a+b}\cot\dfrac{C}{2}$$

### 2.4. Diện tích tam giác
$$S = \dfrac{1}{2}ab\sin C = \dfrac{abc}{4R} = pr = \sqrt{p(p-a)(p-b)(p-c)} \ \text{(Heron)}$$

### 2.5. Đường trung tuyến
$$m_a^2 = \dfrac{2b^2 + 2c^2 - a^2}{4}$$

### 2.6. Đường phân giác trong
$$l_a = \dfrac{2bc\cos\frac{A}{2}}{b+c}$$

### 2.7. Tam giác vuông (hệ thức lượng)
Với tam giác vuông tại $A$, đường cao $h$ từ $A$ xuống cạnh huyền $a$, hình chiếu $b', c'$:
- $b^2 = a\cdot b'$, $c^2 = a\cdot c'$
- $h^2 = b'\cdot c'$
- $\dfrac{1}{h^2} = \dfrac{1}{b^2} + \dfrac{1}{c^2}$
- $a^2 = b^2 + c^2$ (Pythagoras)

---

## 3. HÌNH HỌC PHẲNG — ĐA GIÁC VÀ ĐƯỜNG TRÒN

### 3.1. Tứ giác
- Hình bình hành: $S = a\cdot h$; đường chéo: $d_1^2 + d_2^2 = 2(a^2+b^2)$
- Hình thoi: $S = \dfrac{1}{2}d_1 d_2$
- Hình thang: $S = \dfrac{1}{2}(a+b)h$
- Tứ giác nội tiếp (công thức Brahmagupta): $S = \sqrt{(p-a)(p-b)(p-c)(p-d)}$

### 3.2. Đa giác đều $n$ cạnh, cạnh $a$
- Chu vi: $P = na$
- Diện tích: $S = \dfrac{na^2}{4}\cot\dfrac{\pi}{n}$
- Bán kính đường tròn ngoại tiếp: $R = \dfrac{a}{2\sin(\pi/n)}$
- Bán kính đường tròn nội tiếp (apothem): $r = \dfrac{a}{2\tan(\pi/n)}$

### 3.3. Đường tròn
- Chu vi: $C = 2\pi R$
- Diện tích hình tròn: $S = \pi R^2$
- Độ dài cung ứng góc ở tâm $\alpha$ (rad): $l = R\alpha$
- Diện tích hình quạt: $S_q = \dfrac{1}{2}R^2\alpha$
- Diện tích hình viên phân: $S_{vp} = \dfrac{1}{2}R^2(\alpha - \sin\alpha)$
- Góc nội tiếp bằng nửa góc ở tâm chắn cùng một cung
- Góc tạo bởi tiếp tuyến và dây cung bằng góc nội tiếp chắn cung đó
- Phương tích của điểm $M$ đối với đường tròn $(O,R)$: $\mathcal{P} = MO^2 - R^2$
- Hệ thức tiếp tuyến – cát tuyến: $MT^2 = MA\cdot MB$

---

## 4. HÌNH HỌC KHÔNG GIAN

### 4.1. Khối đa diện cơ bản
**Hình hộp chữ nhật** (cạnh $a, b, c$):
- Thể tích: $V = abc$
- Đường chéo: $d = \sqrt{a^2+b^2+c^2}$
- Diện tích toàn phần: $S_{tp} = 2(ab+bc+ca)$

**Hình lập phương** (cạnh $a$): $V = a^3$, $d = a\sqrt{3}$, $S_{tp} = 6a^2$

**Lăng trụ**: $V = S_{đáy}\cdot h$

**Hình chóp**: $V = \dfrac{1}{3}S_{đáy}\cdot h$

**Hình chóp cụt**: $V = \dfrac{h}{3}\left(S_1 + S_2 + \sqrt{S_1 S_2}\right)$

### 4.2. Hình tròn xoay

**Hình trụ** (bán kính $R$, chiều cao $h$):
- Thể tích: $V = \pi R^2 h$
- Diện tích xung quanh: $S_{xq} = 2\pi R h$
- Diện tích toàn phần: $S_{tp} = 2\pi R h + 2\pi R^2$

**Hình nón** (bán kính đáy $R$, chiều cao $h$, đường sinh $l=\sqrt{R^2+h^2}$):
- Thể tích: $V = \dfrac{1}{3}\pi R^2 h$
- Diện tích xung quanh: $S_{xq} = \pi R l$
- Diện tích toàn phần: $S_{tp} = \pi R l + \pi R^2$

**Hình nón cụt** (bán kính $R, r$, chiều cao $h$, đường sinh $l$):
- $V = \dfrac{\pi h}{3}(R^2 + Rr + r^2)$
- $S_{xq} = \pi(R+r)l$

**Hình cầu** (bán kính $R$):
- Thể tích: $V = \dfrac{4}{3}\pi R^3$
- Diện tích mặt cầu: $S = 4\pi R^2$
- Chỏm cầu chiều cao $h$: $V_{chỏm} = \pi h^2\left(R - \dfrac{h}{3}\right)$, $S_{chỏm} = 2\pi R h$
- Hình đới cầu (giữa hai mặt phẳng song song cách nhau $h$): $S = 2\pi R h$

### 4.3. Góc khối (lập thể giác) — dùng nhiều trong quang học, bức xạ
- Định nghĩa: $d\Omega = \dfrac{dS_\perp}{R^2}$ (đơn vị: steradian, sr)
- Toàn bộ không gian: $\Omega_{toàn} = 4\pi$ (sr)
- Góc khối của hình nón góc mở $2\theta$ (đỉnh ở tâm cầu):
$$\Omega = 2\pi(1-\cos\theta)$$
- Góc khối chắn bởi một mặt nhỏ $dS$ nhìn từ khoảng cách $r$, pháp tuyến hợp góc $\theta$ với phương nhìn:
$$d\Omega = \dfrac{dS\cos\theta}{r^2}$$

---

## 5. VECTOR VÀ HÌNH HỌC GIẢI TÍCH (ĐẠI SỐ, không phải vi–tích phân)

### 5.1. Phép toán vector
- Tích vô hướng: $\vec{a}\cdot\vec{b} = |\vec{a}||\vec{b}|\cos\theta = a_xb_x + a_yb_y + a_zb_z$
- Tích có hướng: $|\vec{a}\times\vec{b}| = |\vec{a}||\vec{b}|\sin\theta$ (phương vuông góc với cả $\vec a,\vec b$, chiều theo quy tắc bàn tay phải)
$$\vec{a}\times\vec{b} = \begin{vmatrix} \vec i & \vec j & \vec k \\ a_x & a_y & a_z \\ b_x & b_y & b_z \end{vmatrix}$$
- Tích hỗn tạp (thể tích hình hộp): $V = |\vec a\cdot(\vec b\times \vec c)|$
- Công thức khai triển tam trùng: $\vec a\times(\vec b\times \vec c) = \vec b(\vec a\cdot\vec c) - \vec c(\vec a\cdot\vec b)$

### 5.2. Hệ tọa độ
**Tọa độ cực** $(r,\theta)$: $x = r\cos\theta,\; y = r\sin\theta$; $r = \sqrt{x^2+y^2}$

**Tọa độ trụ** $(r,\theta,z)$: $x=r\cos\theta,\ y=r\sin\theta,\ z=z$

**Tọa độ cầu** $(r,\theta,\varphi)$ ($\theta$: góc cực tính từ trục $z$, $\varphi$: góc phương vị):
$$x = r\sin\theta\cos\varphi,\quad y = r\sin\theta\sin\varphi,\quad z = r\cos\theta$$

### 5.3. Khoảng cách và góc
- Khoảng cách 2 điểm: $d=\sqrt{(x_2-x_1)^2+(y_2-y_1)^2+(z_2-z_1)^2}$
- Khoảng cách từ điểm đến mặt phẳng $Ax+By+Cz+D=0$:
$$d = \dfrac{|Ax_0+By_0+Cz_0+D|}{\sqrt{A^2+B^2+C^2}}$$
- Góc giữa hai vector: $\cos\theta = \dfrac{\vec a\cdot \vec b}{|\vec a||\vec b|}$

---

## 6. CÁC ĐƯỜNG CONIC (ellip, parabol, hyperbol)

*(Rất quan trọng: quỹ đạo hành tinh, dao động, quang hình học, gương/thấu kính parabol)*

### 6.1. Elip (tâm tại gốc, trục lớn $2a$, trục nhỏ $2b$, $a>b$)
$$\dfrac{x^2}{a^2} + \dfrac{y^2}{b^2} = 1$$
- Tiêu cự: $c = \sqrt{a^2-b^2}$, tâm sai $e = \dfrac{c}{a} < 1$
- Phương trình trong tọa độ cực (gốc tại tiêu điểm):
$$r = \dfrac{a(1-e^2)}{1+e\cos\theta}$$
- Chu vi (gần đúng Ramanujan): $C \approx \pi\left[3(a+b) - \sqrt{(3a+b)(a+3b)}\right]$
- Diện tích: $S = \pi a b$
- Bán kính tại viễn điểm/cận điểm: $r_{max} = a(1+e)$, $r_{min} = a(1-e)$

### 6.2. Hyperbol
$$\dfrac{x^2}{a^2} - \dfrac{y^2}{b^2} = 1$$
- $c=\sqrt{a^2+b^2}$, $e = c/a > 1$
- Phương trình cực: $r = \dfrac{a(e^2-1)}{1+e\cos\theta}$
- Tiệm cận: $y = \pm\dfrac{b}{a}x$

### 6.3. Parabol
$$y^2 = 4px \quad (\text{tiêu điểm } F(p,0),\ \text{đường chuẩn } x=-p)$$
- Dạng đỉnh: $y = \dfrac{x^2}{4p}$ hoặc $y=ax^2$ với $a = \dfrac{1}{4p}$
- $e = 1$
- Tính chất phản xạ: mọi tia song song trục đối xứng khi phản xạ trên parabol đều hội tụ về tiêu điểm (ứng dụng: gương cầu/parabol, ăng-ten)

### 6.4. Phương trình conic tổng quát trong tọa độ cực (một tiêu điểm tại gốc)
$$r = \dfrac{l}{1+e\cos\theta}$$
với $l$ là bán kính thông số ($l = a(1-e^2)$ với elip); $e<1$: elip, $e=1$: parabol, $e>1$: hyperbol.

---

## 7. QUANG HÌNH HỌC (Hình học ứng dụng cho Quang học)

- Định luật phản xạ: $i = i'$ (góc tới = góc phản xạ)
- Định luật khúc xạ Snell: $n_1\sin i_1 = n_2\sin i_2$
- Công thức gương cầu/thấu kính mỏng: $\dfrac{1}{d} + \dfrac{1}{d'} = \dfrac{1}{f}$
- Hệ thức độ phóng đại: $k = -\dfrac{d'}{d}$
- Bán kính cong và tiêu cự gương cầu: $f = \dfrac{R}{2}$
- Công thức thấu kính (người chế tạo): $\dfrac{1}{f} = (n-1)\left(\dfrac{1}{R_1} - \dfrac{1}{R_2}\right)$
- Góc giới hạn phản xạ toàn phần: $\sin i_{gh} = \dfrac{n_2}{n_1}\ (n_1>n_2)$

---

## 8. MỘT SỐ HỆ THỨC HÌNH HỌC KHÁC HAY GẶP TRONG VẬT LÝ

### 8.1. Hệ thức trong dao động/sóng tròn (hình học của pha)
- Liên hệ dây cung – góc ở tâm – bán kính dùng khi tính biên độ tổng hợp hai dao động bằng phương pháp vector quay (giản đồ Fresnel): dùng định lý cos ở mục 2.2.

### 8.2. Định lý Thales (tam giác đồng dạng, dùng trong quang hình học, đòn bẩy)
Nếu $MN \parallel BC$ với $M\in AB, N\in AC$:
$$\dfrac{AM}{AB} = \dfrac{AN}{AC} = \dfrac{MN}{BC}$$

### 8.3. Công thức khoảng cách – hình chiếu (dùng trong cơ học, phân tích lực)
- Hình chiếu của vector $\vec F$ lên phương hợp góc $\alpha$: $F_{//} = F\cos\alpha$, $F_\perp = F\sin\alpha$

### 8.4. Bán kính cong quỹ đạo (hình học thuần, không dùng đạo hàm)
Với quỹ đạo tròn bán kính $R$: liên hệ giữa cung $s$, góc quét $\theta$: $s = R\theta$

### 8.5. Định lý Pythagore mở rộng trong không gian (đường chéo hình hộp)
$$d^2 = a^2+b^2+c^2$$

### 8.6. Diện tích hình chiếu
Diện tích hình chiếu của một mặt phẳng diện tích $S$ lên mặt phẳng khác hợp với nó góc $\theta$:
$$S' = S\cos\theta$$

---

## 9. BẢNG GIÁ TRỊ LƯỢNG GIÁC THÔNG DỤNG

| $\alpha$ (độ) | 0° | 30° | 45° | 60° | 90° | 180° |
|---|---|---|---|---|---|---|
| $\sin\alpha$ | 0 | 1/2 | $\sqrt2/2$ | $\sqrt3/2$ | 1 | 0 |
| $\cos\alpha$ | 1 | $\sqrt3/2$ | $\sqrt2/2$ | 1/2 | 0 | -1 |
| $\tan\alpha$ | 0 | $\sqrt3/3$ | 1 | $\sqrt3$ | — | 0 |

---

*File này tập trung vào các công thức hình học thuần túy (phẳng, không gian, lượng giác, vector, conic) — không bao gồm đạo hàm, tích phân hay các công thức giải tích. Nên dùng kết hợp với tài liệu Giải tích (đạo hàm, tích phân, phương trình vi phân) để có bộ công thức toán học đầy đủ phục vụ HSGQG Vật Lý.*
