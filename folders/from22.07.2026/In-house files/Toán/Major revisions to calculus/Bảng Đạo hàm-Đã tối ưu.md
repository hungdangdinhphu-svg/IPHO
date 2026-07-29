# CHUẨN HÓA LŨY THỪA (ĐẠI SỐ)

Công thức lõi:

$$(x^\alpha)' = \alpha \cdot x^{\alpha-1}$$

Mô hình hóa các dạng đặc thù:

Phân thức: $\frac{1}{x^n} \longrightarrow x^{-n}$

Căn thức: $\sqrt[m]{x^k} \longrightarrow x^{\frac{k}{m}}$


Lợi thế khi đạo hàm bậc cao ($n$):

(Công thức tổng quát hoàn toàn tuyến tính và dễ lập trình thành chuỗi)

$$f^{(n)}(x) = \alpha(\alpha-1)(\alpha-2)...(\alpha-n+1)x^{\alpha-n}$$

# PHÉP CHIA/PHÂN SỐ THÀNH PHÉP NHÂN, CHUẨN HÓA PHÂN SỐ

**Đây là phần khó nhằn nhất, trong khi các phần khác thì rất đơn giản**


Bằng cách áp dụng (nhân nghịch đảo tương đương với phép chia) $G_1 \cdot \frac{1}{G_2} = G_1 \cdot G_2^{-1}$, cấu trúc phân số $\frac{u}{v}$ sẽ được chuẩn hóa thành:

$$\frac{u}{v} \longrightarrow u \cdot v^{-1}$$

Lúc này, bạn có thể sử dụng :

Quy tắc tích (Product Rule): $(f \cdot g)' = f'g + fg'$

Quy tắc lũy thừa tổng quát (Power + Chain Rule): $(v^{-1})' = -1 \cdot v^{-2} \cdot v'$


Thì :

$$(u \cdot v^{-1})' = u' \cdot v^{-1} + u \cdot (-v^{-2} \cdot v')$$

Hãy tưởng tượng bạn phải tính đạo hàm bậc 2 hoặc bậc 3 của một phân số, 


Nếu dùng công thức phân số truyền thống: Sau lần đạo hàm thứ nhất, bạn có một phân số mới cồng kềnh hơn. Đạo hàm lần 2, mẫu số sẽ lên mũ 4 ($v^4$), tử số là một mớ hỗn độn của quy tắc tích và hiệu. Ta sẽ phải tốn công kha khá để rút gọn, quy đồng;


Nếu dùng dạng chuẩn hóa $u \cdot v^{-1}$: Bạn luôn duy trì bài toán ở dạng đa thức tuyến tính. Khi đạo hàm các bậc tiếp theo, bạn chỉ việc dùng chuỗi toán tử nhân và hạ bậc.

Ex : 

Tính đạo hàm bậc 2 của $f(x) = \frac{1}{x^2 + 1}$

$$f(x) = (x^2 + 1)^{-1}$$

=> $$f'(x) = -1 \cdot (x^2 + 1)^{-2} \cdot (x^2 + 1)' = -2x \cdot (x^2 + 1)^{-2}$$

=> $$f''(x) = (-2x)' \cdot (x^2 + 1)^{-2} + (-2x) \cdot \left[(x^2 + 1)^{-2}\right]'$$

$$= -2(x^2 + 1)^{-2} + (-2x) \cdot \left[-2(x^2 + 1)^{-3} \cdot 2x\right]$$

$$= -2(x^2 + 1)^{-2} + 8x^2(x^2 + 1)^{-3}$$



Tuy nhiên, thực tế dù đã đơn giản hơn, nhưng nó vẫn quá phức tạp.

**Nếu chấp nhận sử dụng những kỹ thuật "lạ" thì bạn có thể đọc tiếp, tôi có cung cấp 1 giải pháp khác :**

**CHUYỂN DẠNG ĐƯỜNG THẲNG :**

ta đưa nó về phương trình tích phẳng:

$$f(x) = \frac{u}{v} \Longrightarrow f \cdot v = u$$

Lúc này, thay vì đi đạo hàm một phân số, ta đi đạo hàm cấp $n$ cho cả hai vế của một phép nhân. Công thức Leibniz tổng quát cho phép nhân là một đường thẳng phẳng (tuyến tính) sử dụng tổ hợp $\binom{n}{k}$, tương tự như nhị thức Newton:

$$(f \cdot v)^{(n)} = u^{(n)} \Longrightarrow \sum_{k=0}^n \binom{n}{k} f^{(k)} v^{(n-k)} = u^{(n)}$$

Tách riêng số hạng chứa đạo hàm bậc cao nhất $f^{(n)}$ cần tìm (tương ứng với $k=n$), ta có:

$$f^{(n)} \cdot v + \sum_{k=0}^{n-1} \binom{n}{k} f^{(k)} v^{(n-k)} = u^{(n)}$$

**Tổng quát :**

Rút $f^{(n)}$ ra, ta được :

$$f^{(n)} = \frac{1}{v} \left[ u^{(n)} - \sum_{k=0}^{n-1} \binom{n}{k} f^{(k)} v^{(n-k)} \right]$$

**Trong môi trường tự luận, tôi khuyến khích bạn nên thử dùng cách này :**

Giả sử đề bài yêu cầu tính đạo hàm đến cấp $n$ (với $n$ là một số cụ thể như 2, 3, 4...) của hàm số $f(x) = \frac{u}{v}$.

Bước 1: Khởi tạo dạng phẳng (Tuyến tính hóa)

Tập xác định: $D = ...$

Ta có: $f(x) = \frac{u}{v} \Longrightarrow f(x) \cdot v = u \quad (1)$

Bước 2: Đạo hàm cấp 1

Đạo hàm hai vế của $(1)$ theo biến $x$, áp dụng quy tắc đạo hàm của tích:

$$f'(x) \cdot v + f(x) \cdot v' = u'$$

Từ đây, thế các giá trị $u', v'$ đã biết vào và rút ra biểu thức thu gọn của $f'(x)$.

Bước 3: Đạo hàm cấp 2

Tiếp tục đạo hàm hai vế biểu thức vừa có:

$$\left[ f'(x) \cdot v \right]' + \left[ f(x) \cdot v' \right]' = u''$$

$$\Longrightarrow f''(x) \cdot v + f'(x) \cdot v' + f'(x) \cdot v' + f(x) \cdot v'' = u''$$

$$\Longrightarrow f''(x) \cdot v + 2f'(x) \cdot v' + f(x) \cdot v'' = u''$$

Điền kết quả $f(x)$ và $f'(x)$ đã tính ở các bước trước vào phương trình trên để suy ra $f''(x)$.

Bước 4: Các cấp tiếp theo ($n=3, 4...$)

Cứ tiếp tục đạo hàm phẳng hai vế một cách tuần tự. Cấu trúc lặp Leibniz sẽ tự động ẩn giấu dưới các hệ số đại số ($2, 3, 4, 6...$) khi bạn gom các số hạng giống nhau lại.


# CHUẨN HÓA MŨ VÀ LOGARIT (SIÊU VIỆT)

Trong giải tích, cơ số tự nhiên $e$ là cơ sở duy nhất. Các cơ số $a$ bất kỳ chỉ là một lớp "ngụy trang" của $e$. Việc nhớ đạo hàm của $a^x$ hay $\log_a x$ là dư thừa.

1. Hệ Hàm Mũ:

$$a^x \longrightarrow e^{x \ln a}$$

Đạo hàm bậc cao ($n$):

$$(e^{kx})^{(n)} = k^n \cdot e^{kx}$$

2. Hệ Logarit:

$$\log_a x \longrightarrow \frac{1}{\ln a} \cdot \ln x$$

Công thức lõi: $(\ln x)' = x^{-1}$

Đạo hàm bậc cao ($n$): Ngay sau lần đạo hàm đầu tiên, hàm Logarit lập tức biến thành Hệ Lũy thừa (Hệ thống 1) với $\alpha = -1$. Bạn không cần một công thức riêng nào nữa.

# CHUẨN HÓA LƯỢNG GIÁC (TUẦN HOÀN)

1. Đối với $\sin x$ và $\cos x$:

(Tùy bạn, nếu bạn nghĩ hợp với cách này thì dùng, còn không thì cứ dùng cách truyền thống)


Việc đạo hàm thực chất chỉ là việc dịch chuyển đồ thị về bên trái một góc $\frac{\pi}{2}$.

Công thức lõi:

$$(\sin x)' = \sin\left(x + \frac{\pi}{2}\right)$$

$$(\cos x)' = \cos\left(x + \frac{\pi}{2}\right)$$

Đạo hàm bậc cao ($n$): Không cần suy nghĩ về dấu, cứ cộng dồn pha.

$$(\sin x)^{(n)} = \sin\left(x + \frac{n\pi}{2}\right)$$

$$(\cos x)^{(n)} = \cos\left(x + \frac{n\pi}{2}\right)$$

**Để hợp pháp hóa nó, bạn hãy dùng Phương pháp Quy nạp toán học (Mathematical Induction) :**

Ví dụ :

Với $n = 1$: $y' = \cos x = \sin\left(x + \frac{\pi}{2}\right)$ (mệnh đề đúng).

Giả sử mệnh đề đúng đến cấp $k$ ($k \ge 1$), tức là:

$$y^{(k)} = \sin\left(x + \frac{k\pi}{2}\right)$$

Ta cần chứng minh mệnh đề cũng đúng với cấp $k + 1$. Thật vậy, lấy đạo hàm của $y^{(k)}$, ta có:

$$y^{(k+1)} = \left[ y^{(k)} \right]' = \left[ \sin\left(x + \frac{k\pi}{2}\right) \right]' = \cos\left(x + \frac{k\pi}{2}\right)$$

Áp dụng công thức phụ chéo lượng giác: $\cos \alpha = \sin\left(\alpha + \frac{\pi}{2}\right)$, ta được:

$$y^{(k+1)} = \sin\left(x + \frac{k\pi}{2} + \frac{\pi}{2}\right) = \sin\left(x + \frac{(k+1)\pi}{2}\right)$$

Theo nguyên lý quy nạp, công thức đúng với mọi $n \in \mathbb{N}^*$.

$$\Longrightarrow y^{(n)} = \sin\left(x + \frac{n\pi}{2}\right)$$



2. Đối với $\tan x$ và $\cot x$:

(Cái này thì được cho phép dùng trực tiếp)

Autonomous Form:


Công thức lõi:

$$(\tan x)' = 1 + \tan^2 x$$


$$(\cot x)' = -(1 + \cot^2 x)$$

Lợi thế: Khi tính đạo hàm bậc 2 của $\tan x$, bạn coi nó như một đa thức đại số $u^2$, đạo hàm :

$(\tan x)'' = (1 + \tan^2 x)' = 2\tan x \cdot (1+\tan^2 x)$

Bạn hoàn toàn ở lại trong không gian của hàm $\tan$, không bị nhảy sang không gian của $\cos$.

 























