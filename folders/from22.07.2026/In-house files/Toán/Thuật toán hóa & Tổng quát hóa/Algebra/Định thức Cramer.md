https://share.gemini.google/SfRIcoR4IszO

Trong toán học, khi bạn đã có một hệ phương trình tuyến tính theo các ẩn cần tìm (2 hoặc 3 ẩn), tôi đề xuất Cramer. Còn nếu nhiều ẩn thì nên xài khử Gauss.

**Áp dụng được cho mọi hệ phương trình bậc nhất nhiều ẩn.** Đừng quên nhé, không thì dễ tạch.

Xét hệ $n$ phương trình tuyến tính $n$ ẩn số $x_1, x_2, \dots, x_n$:

$$\begin{cases} a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n = b_1 \\ a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n = b_2 \\ \vdots \\ a_{n1}x_1 + a_{n2}x_2 + \dots + a_{nn}x_n = b_n \end{cases}$$

Dưới dạng ma trận: $A X = B$, trong đó:

$A = (a_{ij})_{n \times n}$ là ma trận hệ số cấp $n \times n$.

$X = \begin{bmatrix} x_1 & x_2 & \dots & x_n \end{bmatrix}^T$ là cột biến số.

$B = \begin{bmatrix} b_1 & b_2 & \dots & b_n \end{bmatrix}^T$ là cột hằng số tự do.

**Các định thức thành phần**

Định thức chính $D$ (hoặc $\det(A)$):

$$D = \begin{vmatrix}     a_{11} & a_{12} & \dots & a_{1n} \\     a_{21} & a_{22} & \dots & a_{2n} \\     \vdots & \vdots & \ddots & \vdots \\     a_{n1} & a_{n2} & \dots & a_{nn}     \end{vmatrix}$$


Định thức phụ $D_j$ (với $j = 1, 2, \dots, n$):

Được tạo thành bằng cách thay thế cột thứ $j$ của định thức $D$ bằng cột hằng số $B$:

$$D_j = \begin{vmatrix}     a_{11} & \dots & b_1 & \dots & a_{1n} \\     a_{21} & \dots & b_2 & \dots & a_{2n} \\     \vdots & \ddots & \vdots & \ddots & \vdots \\     a_{n1} & \dots & b_n & \dots & a_{nn}     \end{vmatrix}$$

**Biện luận nghiệm theo định lý Cramer**

Trường hợp 1: $D \neq 0$

Hệ phương trình có nghiệm duy nhất duy nhất $(x_1, x_2, \dots, x_n)$ được tính theo công thức:

$$x_j = \frac{D_j}{D} \quad \text{với mọi } j = 1, 2, \dots, n$$

Trường hợp 2: $D = 0$ và tồn tại ít nhất một $D_j \neq 0$

Hệ phương trình vô nghiệm.

Trường hợp 3: $D = 0$ và $D_1 = D_2 = \dots = D_n = 0$

Hệ phương trình có thể vô nghiệm hoặc vô số nghiệm (cần dùng phương pháp khử Gauss hoặc xét hạng ma trận $\text{rank}(A)$ và $\text{rank}(A\vert{}B)$ để kết luận).


**Công thức tổng quát cho cấp \(n \times n\) (Khai triển Laplace)**

Khi định thức có cấp lớn hơn (\(3 \times 3, 4 \times 4\)), người ta dùng thuật toán hạ cấp bằng cách khai triển theo một dòng hoặc một cột bất kỳ (thường chọn dòng/cột có nhiều số 0 hoặc hệ số đơn giản nhất).

Khai triển theo dòng \(i\):


\(\det (A)=\sum _{j=1}^{n}a_{ij}\cdot (-1)^{i+j}\cdot M_{ij}\)


• \(a_{ij}\): Phần tử tại dòng \(i\), cột \(j\).

• \((-1)^{i+j}\): Dấu vị trí (đan xen dấu \(\pm \) kiểu bàn cờ ca-rô).

• \(M_{ij}\): Định thức con cấp \((n-1)\) có được sau khi xóa bỏ hoàn toàn dòng \(i\) và cột \(j\).
















