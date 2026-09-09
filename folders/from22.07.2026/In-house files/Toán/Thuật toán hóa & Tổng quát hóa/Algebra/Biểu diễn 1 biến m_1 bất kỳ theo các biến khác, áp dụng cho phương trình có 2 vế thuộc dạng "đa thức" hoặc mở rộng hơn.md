# Biểu diễn 1 biến m_1 bất kỳ theo các biến khác, áp dụng cho phương trình có 2 vế thuộc dạng "đa thức" hoặc mở rộng hơn

## Problem Statement & Quy trình

Ta có phương trình sau : f_1(m_1,m_2,...,m_n) = f_2(m_1,m_2,...,m_n)

Với m_i được hiểu là biến, nếu có một biến m_i (từ m_1 đến m_n) nào chỉ tồn tại ở một trong hai hàm f_j (j thuộc {1;2}) thì tại hàm f (tức là tại hàm không tồn tại biến m_i tường minh) đó, ta coi như 0*m_i = 0;

Biết rằng f_1 và f_2 đều có "dạng" đa thức. Nếu không phải đa thức, đặt ẩn phụ theo u = √(u') và u_2 = 1/(u_3) và u_1 * u_2 = u_1 * (1/u_3) ;

Gọi:

Bước 1: Biết rằng ta đang muốn m_1 = g_0(m_2, m_3,...,m_n)

Bước 2: Áp dụng các kỹ thuật bên "Bài Toán Lớn" & Bảng Quy Tắc Biến Đổi Đại Số THCS để đưa về cấu trúc m_1 * theta = gamma

Bước 3: Biện luận (if any) và xong!

**Lưu ý lớn:** Trong trường hợp có tồn tại (m_1)^n (với n > 1) thì cần xử lý tiếp sau bước m_1 * theta = gamma một cách đúng đắn, về cơ bản vẫn là chuyển hàm chứa m_1 bên vế phải sang vế trái, rồi đảm bảo hàm z' bên vế trái chứa toàn bộ các m_1 (mà z' có dạng là chỉ có các m_1 xuất hiện trên tử số), sau đó tiếp tục áp dụng dạng m_1 * theta' = gamma'


## Bài Toán Lớn

*Note: Nên chú ý quan sát vì sao tôi lại đặt phương trình kỳ lạ như vậy nhé.

```txt

Bước 1: Khai triển tích và triệt tiêu số hạng chung
Phương trình ban đầu:
$$(m_1 m_2) + (m_1 m_3)(m_4 m_5) + m_1 = (m_1 m_2') + (m_1 m_3')(m_4' m_5') + m_1 + m_6' + m_7' + m_8'$$
Theo tính chất kết hợp của phép nhân:
$(m_1 m_3)(m_4 m_5) = m_1 \cdot (m_3 m_4 m_5)$
$(m_1 m_3')(m_4' m_5') = m_1 \cdot (m_3' m_4' m_5')$
Thay vào phương trình:
$$m_1 m_2 + m_1(m_3 m_4 m_5) + m_1 = m_1 m_2' + m_1(m_3' m_4' m_5') + m_1 + m_6' + m_7' + m_8'$$
Triệt tiêu số hạng $m_1$ ở cả hai vế:
$$m_1 m_2 + m_1(m_3 m_4 m_5) = m_1 m_2' + m_1(m_3' m_4' m_5') + m_6' + m_7' + m_8'$$
Bước 2: Chuyển vế và đặt nhân tử chung chứa $m_1$
Chuyển tất cả các hạng tử chứa $m_1$ sang vế trái:
$$m_1 m_2 + m_1(m_3 m_4 m_5) - m_1 m_2' - m_1(m_3' m_4' m_5') = m_6' + m_7' + m_8'$$
Đặt $m_1$ làm thừa số chung:
$$m_1 \left[ (m_2 - m_2') + (m_3 m_4 m_5 - m_3' m_4' m_5') \right] = m_6' + m_7' + m_8'$$
Bước 3: Biện luận và biểu diễn nghiệm $m_1$
Đặt mẫu số:
$$D = (m_2 - m_2') + (m_3 m_4 m_5 - m_3' m_4' m_5')$$
Trường hợp $D \neq 0$ (tức $(m_2 - m_2') + (m_3 m_4 m_5 - m_3' m_4' m_5') \neq 0$):
Phương trình có nghiệm duy nhất:
$$m_1 = \frac{m_6' + m_7' + m_8'}{(m_2 - m_2') + (m_3 m_4 m_5 - m_3' m_4' m_5')}$$
Trường hợp $D = 0$:
Nếu $m_6' + m_7' + m_8' = 0$: Phương trình nghiệm đúng với mọi $m_1$.
Nếu $m_6' + m_7' + m_8' \neq 0$: Phương trình vô nghiệm.

```
