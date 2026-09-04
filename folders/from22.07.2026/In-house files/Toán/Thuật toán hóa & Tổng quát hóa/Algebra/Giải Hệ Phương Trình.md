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

# Cách đấm vỡ mồm m + n > 4 :

## Đây là Định lý kết hợp (Thuật toán Euclid cho Resultant):

Nguyên lý bất hủ: Nếu $P(x)$ và $Q(x)$ có nghiệm chung, thì khi chia $P$ cho $Q$ lấy dư $R(x)$, cặp $(Q, R)$ cũng có nghiệm chung đó.Cụ thể: $\text{Det\_Sylvester}(P, Q) = 0 \iff \text{Det\_Sylvester}(Q, R) = 0$ (sai khác hằng số vô hại).Vì vậy, ta dùng phép chia lấy dư để hạ bậc cho đến khi tổng bậc $\le 4$ rồi mới bấm Casio.

## "MẸO CHIA ĐA THỨC CỰC NHANH" (Dùng đạo hàm & Hệ số bất định)

Để tránh việc chia cột dài dòng, ta dùng Đạo hàm (Taylor) tại 0 hoặc đơn giản là Đồng nhất hệ số – cách này tất định và chỉ cần 4 phép tính cộng trừ nhân chia.Giả sử bạn cần chia A(x) bậc $m$ cho B(x) bậc $n$ (với $m > n$).Ví dụ điển hình: Chia bậc 3 cho bậc 2 (tổng $5 > 4$), ta chỉ cần tìm dư $R(x) = Cx + D$.

Cách làm siêu tốc (cho bậc 3 $\div$ bậc 2):

Cho $A(x) = a_3x^3 + a_2x^2 + a_1x + a_0$

Cho $B(x) = b_2x^2 + b_1x + b_0$

Giả sử thương là $qx + p$, dư là $Cx + D$.

Viết phương trình đồng nhất:

$$a_3x^3 + a_2x^2 + a_1x + a_0 = (qx + p)(b_2x^2 + b_1x + b_0) + (Cx + D)$$

Mở ngoặc và so sánh hệ số, bạn có công thức truy hồi cực nhanh:

$q = \frac{a_3}{b_2}$

$p = \frac{a_2 - q \cdot b_1}{b_2}$

$C = a_1 - q \cdot b_0 - p \cdot b_1$ (Đây chính là đạo hàm cấp 1 tại 0 của phần dư)

$D = a_0 - p \cdot b_0$

Chỉ 4 phép tính là ra đa thức dư $R(x) = Cx + D$.

Tương tự, nếu chia bậc 4 cho bậc 2, bạn làm tương tự, tìm thương bậc 2 (cần 3 biến) và dư bậc 1 (2 biến) – cũng chỉ giải hệ 5 ẩn bằng cách đồng nhất, cực ngắn.

## QUY TRÌNH "CỰC MẠNH" KHI m + n > 4

Bước 1 (Lặp Euclid):

Nhìn vào 2 đa thức chứa biến cần khử (ví dụ $x$).

Lấy đa thức bậc cao hơn chia cho đa thức bậc thấp hơn bằng mẹo đồng nhất hệ số ở trên để ra dư $R(x)$.

Thế đa thức bậc cao bằng dư $R(x)$ đó.

Lặp lại cho đến khi tổng bậc của 2 đa thức mới $\le 4$.

Bước 2 (Bấm Casio thẳng):

Lúc này, vì tổng bậc $m' + n' \le 4$, ma trận Sylvester có kích thước tối đa 4x4. Bạn lập ma trận đó, vào Casio MODE -> Matrix -> Det , bấm ra định thức (phương trình mới không còn biến $x$). Cực kỳ nhanh!


## VÍ DỤ THỰC TẾ (Bạn thử làm theo, sẽ thấy nó nhanh hơn mò nghiệm)

Giả sử cần khử $x$ khỏi 2 phương trình bậc 3 (tổng $6 > 4$):

$$P(x) = x^3 + 2x + y = 0 \quad \text{(bậc 3)}$$

$$Q(x) = x^3 - x + y^2 = 0 \quad \text{(bậc 3)}$$

Thực hiện Euclid cực nhanh trên giấy:

Lấy $P - Q$ ta được: $$P - Q = (x^3 - x^3) + 0x^2 + (2x - (-x)) + (y - y^2) = 3x + (y - y^2)$$

Vậy dư $R(x) = 3x + (y - y^2)$ (bậc 1).

Lúc này, thay vì bấm ma trận 6x6, ta chỉ việc khử $x$ giữa Q (bậc 3) và R (bậc 1).
Tổng bậc = $3 + 1 = 4 \rightarrow$ Vừa khớp Casio 4x4!

Bạn lập ma trận Sylvester 4x4 ngay.

Bấm Det trên Casio ra luôn phương trình 1 ẩn $y$ mà không cần khai triển dài dòng.

## VẬY "ĐẠO HÀM" ĐƯỢC DÙNG Ở ĐÂU ĐỂ CHẶN DÀI?

Bạn cho phép dùng đạo hàm, tôi xin chỉ ra chiêu cuối để làm hệ "xấu" trở nên cực ngắn:

Trước khi chia Euclid, hãy kiểm tra UCLN của hai đa thức bằng cách tính $\gcd(P, P')$ (dùng đạo hàm). Nếu chúng có nghiệm bội, bậc của đa thức sẽ giảm ngay lập tức (nghiệm bội bị loại bỏ), khiến tổng bậc $m + n$ tụt xuống dưới 4 mà không cần phải chia nhiều lần.

Tuyệt chiêu bấm máy: Để tìm UCLN bằng tay cực nhanh, bạn chỉ cần tính P mod P' (dùng đồng nhất hệ số như trên). Thao tác này chỉ tốn 5 giây.

