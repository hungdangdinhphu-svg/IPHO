# BÀI TẬP THỰC HÀNH CHUYÊN SÂU: NGUYÊN HÀM & TÍCH PHÂN (VPHO LEVEL)

Bộ bài tập này được thiết kế để "vắt kiệt" mọi kỹ thuật trong tài liệu "General Algorithm". Hãy tuân thủ sơ đồ quyết định (Mục 0) trước khi bắt đầu mỗi bài.

---

## PHẦN I: BÀI TẬP LUYỆN TẬP

### Phần 1: Chuẩn hóa lũy thừa & Tuyến tính
1. Tính $I_1 = \int \frac{dx}{\sqrt[3]{(2x-5)^5}}$.
2. Tính $I_2 = \int \frac{(x^2+1)^2}{x^3} dx$.

### Phần 2: Hàm hữu tỉ $P(x)/Q(x)$
1. Tính $I_3 = \int \frac{x^4}{x^2-1} dx$.
2. Tính $I_4 = \int \frac{dx}{x^3-x^2}$. (Yêu cầu dùng Heaviside cover-up).
3. Tính $I_5 = \int \frac{dx}{(x^2+4x+5)^2}$. (Sử dụng công thức truy hồi).

### Phần 3: Hàm mũ & Logarit
1. Tính $I_6 = \int x^3 e^{-2x} dx$.
2. Tính $I_7 = \int \ln(x + \sqrt{x^2+1}) dx$.

### Phần 4: Hàm lượng giác
1. Tính $I_8 = \int \sin^5 x \cos^4 x dx$.
2. Tính $I_9 = \int \frac{dx}{3 + 5\cos x}$. (Dùng phép thế Weierstrass).
3. Tính $I_{10} = \int \tan^5 x dx$. (Dùng công thức truy hồi).

### Phần 5: Hàm vô tỉ
1. Tính $I_{11} = \int \frac{dx}{x\sqrt{x^2+4x+1}}$. (Dùng phép thế Euler).
2. Tính $I_{12} = \int \frac{\sqrt[3]{1+\sqrt[4]{x}}}{\sqrt{x}} dx$. (Kiểm tra điều kiện Chebyshev).

### Phần 6: Tích phân từng phần (DI Method/LIATE)
1. Tính $I_{13} = \int e^{3x} \cos(4x) dx$. (Cyclic IBP).
2. Tính $I_{14} = \int x^4 \sin(x) dx$. (Dùng DI Method).

### Phần 7: Tích phân xác định & Vật lý
1. Tính $J_1 = \int_0^\pi \frac{x \sin x}{1 + \cos^2 x} dx$. (Quy tắc King).
2. Tính $J_2 = \int_0^{\pi/2} \sin^6 x \cos^4 x dx$. (Công thức Wallis).
3. Tính $J_3 = \int_0^\infty \frac{e^{-x} - e^{-3x}}{x} dx$. (Feynman's trick).

### Phần 8: VPHO Master Level (Cực khó)
**Bài 1:** Tính nguyên hàm $I_{15} = \int \frac{dx}{x^4\sqrt{1+x^2}}$.
*(Gợi ý: Nhận diện vi phân nhị thức, đưa về hàm hữu tỉ phức tạp và dùng phương pháp tách đạo hàm mẫu).*

**Bài 2:** Tính tích phân $J_4 = \int_0^1 \frac{x^a - 1}{\ln x} dx$ với $a > -1$. 
*(Yêu cầu: Sử dụng Vi phân dưới dấu tích phân/Feynman's trick).*

---

## PHẦN II: LỜI GIẢI CHI TIẾT (ALGORITHMIC SOLUTIONS)

### Phần 1: Chuẩn hóa lũy thừa
**Bài 1:** $I_1 = \int (2x-5)^{-5/3} dx$.
- **Nhận diện:** Hàm hợp tuyến tính $ax+b$ với $a=2, b=-5, \alpha = -5/3$.
- **Thực hiện:** Áp dụng quy tắc chia hệ số góc:
  $I_1 = \frac{1}{2} \cdot \frac{(2x-5)^{-5/3+1}}{-5/3+1} + C = \frac{1}{2} \cdot \frac{(2x-5)^{-2/3}}{-2/3} + C = -\frac{3}{4\sqrt[3]{(2x-5)^2}} + C$.

**Bài 2:** $I_2 = \int \frac{x^4+2x^2+1}{x^3} dx = \int (x + 2x^{-1} + x^{-3}) dx$.
- **Nhận diện:** Một khối duy nhất, chuẩn hóa về tổng các lũy thừa đơn.
- **Thực hiện:** $I_2 = \frac{x^2}{2} + 2\ln|x| - \frac{1}{2x^2} + C$.

---

### Phần 2: Hàm hữu tỉ
**Bài 1 ($I_3$):** Chia đa thức: $x^4 : (x^2-1) = (x^2+1) + \frac{1}{x^2-1}$.
- $I_3 = \int (x^2+1) dx + \int \frac{dx}{x^2-1}$.
- Áp dụng Mục II (dạng đặc biệt): $I_3 = \frac{x^3}{3} + x + \frac{1}{2}\ln\left|\frac{x-1}{x+1}\right| + C$.

**Bài 2 ($I_4$):** $f(x) = \frac{1}{x^2(x-1)}$.
- Phân tích: $\frac{1}{x^2(x-1)} = \frac{A}{x} + \frac{B}{x^2} + \frac{C}{x-1}$.
- **Heaviside cover-up** cho $C$ (tại $x=1$): Che $(x-1)$, thế $x=1$ vào $1/x^2 \Rightarrow C = 1$.
- **Heaviside** cho $B$ (tại $x=0$, nghiệm bội cao nhất): Che $x^2$, thế $x=0$ vào $1/(x-1) \Rightarrow B = -1$.
- Để tìm $A$: Cho $x=2 \Rightarrow \frac{1}{4} = \frac{A}{2} - \frac{1}{4} + 1 \Rightarrow A = -1$.
- Kết quả: $I_4 = -\ln|x| + \frac{1}{x} + \ln|x-1| + C$.

**Bài 3 ($I_5$):** $x^2+4x+5 = (x+2)^2 + 1$. Đặt $t = x+2$.
- $I_5 = \int \frac{dt}{(t^2+1)^2}$. Đây là $I_n$ với $a=1, n=2$.
- Áp dụng công thức truy hồi Mục II: $I_2 = \frac{t}{2(t^2+1)} + \frac{2(2)-3}{2(2-1)} I_1 = \frac{t}{2(t^2+1)} + \frac{1}{2}\arctan t + C$.
- Trả biến: $I_5 = \frac{x+2}{2(x^2+4x+5)} + \frac{1}{2}\arctan(x+2) + C$.

---

### Phần 4: Hàm lượng giác
**Bài 1 ($I_8$):** $n=5$ (lẻ), $m=4$ (chẵn).
- **Thuật toán:** $n$ lẻ $\to$ Đặt $t = \cos x, dt = -\sin x dx$.
- Biến đổi: $\sin^4 x = (1-\cos^2 x)^2 = (1-t^2)^2$.
- $I_8 = -\int (1-t^2)^2 t^4 dt = -\int (t^4 - 2t^6 + t^8) dt = -\frac{\cos^5 x}{5} + \frac{2\cos^7 x}{7} - \frac{\cos^9 x}{9} + C$.

**Bài 2 ($I_9$):** Không thỏa mãn test đối xứng $\to$ **Weierstrass**.
- $t = \tan(x/2), dx = \frac{2dt}{1+t^2}, \cos x = \frac{1-t^2}{1+t^2}$.
- Thế vào: $I_9 = \int \frac{1}{3 + 5\frac{1-t^2}{1+t^2}} \cdot \frac{2dt}{1+t^2} = \int \frac{2dt}{3(1+t^2) + 5(1-t^2)} = \int \frac{2dt}{8-2t^2} = \int \frac{dt}{4-t^2}$.
- Dạng đặc biệt Mục II: $I_9 = \frac{1}{2(2)}\ln\left|\frac{2+t}{2-t}\right| = \frac{1}{4}\ln\left|\frac{2+\tan(x/2)}{2-\tan(x/2)}\right| + C$.

---

### Phần 5: Hàm vô tỉ
**Bài 2 ($I_{12}$):** $\int x^{-1/2} (1+x^{1/4})^{1/3} dx$.
- **Nhận diện:** $x^m(a+bx^n)^p$ với $m=-1/2, n=1/4, p=1/3$.
- Kiểm tra Chebyshev:
  1. $p = 1/3 \notin \mathbb{Z}$ (Loại 1).
  2. $\frac{m+1}{n} = \frac{-1/2+1}{1/4} = \frac{1/2}{1/4} = 2 \in \mathbb{Z}$. (Thỏa mãn Loại 2!).
- **Thuật toán:** Đặt $a+bx^n = t^s$ (với $s$ là mẫu số của $p=3$).
- Đặt $1+x^{1/4} = t^3 \Rightarrow x = (t^3-1)^4 \Rightarrow dx = 4(t^3-1)^3 \cdot 3t^2 dt$.
- Thế vào và rút gọn (bài toán trở thành tích phân đa thức cực kỳ dài nhưng hội tụ).

---

### Phần 7: Tích phân xác định
**Bài 1 ($J_1$):** Cận $[0, \pi]$. Thử **Quy tắc King**: $x \to \pi - x$.
- $J_1 = \int_0^\pi \frac{(\pi-x)\sin(\pi-x)}{1+\cos^2(\pi-x)} dx = \int_0^\pi \frac{\pi\sin x - x\sin x}{1+\cos^2 x} dx$.
- Suy ra $J_1 = \pi\int_0^\pi \frac{\sin x}{1+\cos^2 x} dx - J_1 \Rightarrow 2J_1 = \pi \int_0^\pi \frac{\sin x dx}{1+\cos^2 x}$.
- Đặt $u = \cos x \to 2J_1 = \pi \int_1^{-1} \frac{-du}{1+u^2} = \pi \int_{-1}^1 \frac{du}{1+u^2} = \pi [\arctan u]_{-1}^1 = \pi(\pi/4 - (-\pi/4)) = \pi^2/2$.
- Vậy $J_1 = \pi^2/4$.

**Bài 3 ($J_3$):** **Feynman's trick**.
- Xét $I(a) = \int_0^\infty \frac{e^{-x} - e^{-ax}}{x} dx$. Ta cần tính $I(3)$.
- Đạo hàm dưới dấu tích phân theo $a$: $I'(a) = \int_0^\infty \frac{\partial}{\partial a} \left( \frac{e^{-x} - e^{-ax}}{x} \right) dx = \int_0^\infty \frac{x e^{-ax}}{x} dx = \int_0^\infty e^{-ax} dx$.
- Tích phân sơ cấp: $I'(a) = \left[ \frac{-1}{a} e^{-ax} \right]_0^\infty = \frac{1}{a}$ (với $a > 0$).
- Lấy nguyên hàm theo $a$: $I(a) = \ln|a| + C$.
- Tìm $C$: Tại $a=1$, $I(1) = \int_0^\infty \frac{e^{-x} - e^{-x}}{x} dx = 0$. Vậy $\ln(1) + C = 0 \Rightarrow C = 0$.
- Vậy $I(a) = \ln a$. Đáp số $J_3 = I(3) = \ln 3$.

---

### Phần 8: VPHO Master Level
**Bài 1 ($I_{15}$):** $I = \int x^{-4}(1+x^2)^{-1/2} dx$.
- Chebyshev: $m=-4, n=2, p=-1/2$. $\frac{m+1}{n} + p = \frac{-3}{2} - \frac{1}{2} = -2 \in \mathbb{Z}$ (Loại 3).
- **Thuật toán:** Đặt $ax^{-n}+b = t^s \Rightarrow x^{-2}+1 = t^2 \Rightarrow t = \frac{\sqrt{x^2+1}}{x}$.
- Biến đổi: $x^2 = \frac{1}{t^2-1}$, $dx = -\frac{t}{(t^2-1)^{3/2}} dt$.
- Thế vào: $I = \int (t^2-1)^2 \cdot \frac{1}{t/\sqrt{t^2-1}} \cdot \left(-\frac{t}{(t^2-1)^{3/2}}\right) dt = -\int (t^2-1) dt = -\frac{t^3}{3} + t + C$.
- Trả biến: $I_{15} = -\frac{1}{3}\left(\frac{x^2+1}{x^2}\right)^{3/2} + \frac{\sqrt{x^2+1}}{x} + C = \frac{(2x^2-1)\sqrt{x^2+1}}{3x^3} + C$.

**Bài 2 ($J_4$):**
- Đặt $I(a) = \int_0^1 \frac{x^a-1}{\ln x} dx$.
- $I'(a) = \int_0^1 \frac{\partial}{\partial a} \left(\frac{x^a-1}{\ln x}\right) dx = \int_0^1 \frac{x^a \ln x}{\ln x} dx = \int_0^1 x^a dx = \left[\frac{x^{a+1}}{a+1}\right]_0^1 = \frac{1}{a+1}$.
- $I(a) = \ln(a+1) + C$.
- Tại $a=0, I(0) = 0 \Rightarrow C = 0$.
- Kết quả: $J_4 = \ln(a+1)$.

---
**Lời nhắn gửi:** Bạn vừa đi qua toàn bộ các "ngõ ngách" của giải thuật tích phân. Từ những phép thế Euler cồng kềnh đến sự tinh tế của Feynman's trick, mọi thứ đều tuân theo quy trình. Hãy luyện tập lại nhiều lần để biến các bước này thành bản năng! Chúc bạn chinh phục VPHO thành công.
