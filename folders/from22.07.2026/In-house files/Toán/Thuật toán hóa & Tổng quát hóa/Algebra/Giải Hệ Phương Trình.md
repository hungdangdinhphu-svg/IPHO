*Có lỗi hiển thị.

# PHƯƠNG PHÁP ĐỊNH THỨC SYLVESTER (PHÉP KHỬ DẦN BIẾN)

Bản chất: Thay vì dùng trực giác để đặt ẩn phụ hay thế biến, ta sử dụng Ma trận Sylvester và tính Định thức (Determinant) của nó để loại bỏ một biến một cách tự động. Máy Casio fx-580VN X có chức năng tính định thức ma trận cấp 4x4, cực kỳ phù hợp để làm việc này.

QUY TRÌNH 4 BƯỚC "CỰC MẠNH" (Áp dụng được cho n ẩn)

## Bước 1: Hữu tỉ hóa và đa thức hóa (Preprocessing)

Đây là bước duy nhất không hoàn toàn cơ học, nhưng rất đơn giản:
Đặt ẩn phụ để khử căn thức, phân số mũ âm. Mục tiêu đưa hệ về dạng đa thức (chứa các biến mới với số mũ nguyên dương).

Ví dụ: sqrt(x) đặt là a ; 1/(x+y) đặt là u . Lúc này ta có hệ đa thức chuẩn.

## Bước 2: Khử biến bằng Định thức Sylvester (Bước cốt lõi)

Giả sử cần khử biến x khỏi 2 phương trình (coi các biến khác là tham số):

Phương trình 1: $P(x) = 0$ (bậc $m$)

Phương trình 2: $Q(x) = 0$ (bậc $n$)

Lập ma trận Sylvester (cấp $m + n$):

Hàng 1 $\rightarrow$ m: Ghi hệ số của $P(x)$ dịch chuyển dần sang phải.

Hàng (m+1) $\rightarrow$ (m+n): Ghi hệ số của $Q(x)$ dịch chuyển dần sang phải.

Điền số 0 vào các ô trống.

Bấm Casio:

Vào MODE -> Matrix khai báo ma trận. Vào OPTION -> Det để tính định thức của ma trận này.
Cho Định thức = 0, bạn vừa thu được một phương trình mới, trong đó biến x đã bị khử hoàn toàn!

## Bước 3: Lặp lại thuật toán (Triangularization)

Áp dụng Bước 2 một cách tuần tự để giảm dần số biến:

Từ hệ $n$ phương trình $n$ ẩn:

Ghép cặp (PT1, PT2) $\rightarrow$ khử $x_n$ $\rightarrow$ được PT mới (PT A).

Ghép cặp (PT1, PT3) $\rightarrow$ khử $x_n$ $\rightarrow$ được PT mới (PT B).

...

Sau khi khử hết, ta có hệ mới chỉ có $(n - 1)$ phương trình và $(n - 1)$ ẩn.
Tiếp tục lặp lại cho đến khi chỉ còn 1 phương trình duy nhất chứa 1 ẩn.

## Bước 4: Giải và thế ngược

Giải phương trình cuối: Vì chỉ còn 1 ẩn, hãy nhập phương trình này vào Casio fx-580VN X.

Nếu bậc $\le$ 3: dùng MODE -> EQN .

Nếu bậc > 3 hoặc chứa tham số phức tạp: dùng chức năng SHIFT + CALC (SOLVE) để bấm ra nghiệm số ngay lập tức.

Thế ngược: Lần lượt thay nghiệm đã biết vào các ma trận Sylvester bậc thấp hơn để giải các biến còn lại (dùng SOLVE tiếp).

## LƯU Ý VÀNG VỀ CASIO fx-580VN X (Cực kỳ quan trọng)

Máy tính này hỗ trợ ma trận tối đa 4x4. Vì vậy, nếu bậc của 2 đa thức cần khử có tổng bậc $m + n > 4$, ta không lập ma trận trực tiếp.

Giải pháp: Trước khi lập ma trận, hãy dùng máy tính tìm ước chung (UCLN) của hai đa thức bằng thuật toán Euclid (dùng phép chia đa thức trên giấy). Nếu chúng có nghiệm chung, ta rút gọn được bậc. Nếu không, hãy thay đổi cách ghép cặp phương trình để có tổng bậc nhỏ hơn hoặc bằng 4.



## VÍ DỤ MINH HỌA (Hệ 2 ẩn)

Giải hệ (không thể bấm trực tiếp Casio):

$$\begin{cases} x^2 + y = 3 \\ x + y^2 = 5 \end{cases}$$

Thực hiện thuật toán:

Bước 1: Đã là đa thức (khỏi biến đổi).

Bước 2 (Khử $x$):

Coi $y$ là hằng số.

$P(x) = x^2 + 0x + (y - 3)$ (bậc 2)

$Q(x) = 1x + (y^2 - 5)$ (bậc 1)

Ma trận Sylvester cấp (2+1)=3:

$$M = \begin{bmatrix} 1 & 0 & y-3 \\ 1 & y^2-5 & 0 \\ 0 & 1 & y^2-5 \end{bmatrix}$$

Bước 3: Bấm máy tính det(M) = y^4 - 10y^2 + y + 22 .

Cho det = 0, ta được phương trình 1 ẩn: $y^4 - 10y^2 + y + 22 = 0$.

Bước 4: Nhập y^4 - 10y^2 + y + 22 = 0 vào Casio, bấm SOLVE (chọn giá trị đầu $y = 1 \rightarrow$ ra $y = 2$). Thế $y = 2$ vào hệ đầu, bấm SOLVE tìm được $x = 1$. (Bạn hoàn toàn có thể tìm hết 4 nghiệm bằng cách đổi giá trị đầu).

