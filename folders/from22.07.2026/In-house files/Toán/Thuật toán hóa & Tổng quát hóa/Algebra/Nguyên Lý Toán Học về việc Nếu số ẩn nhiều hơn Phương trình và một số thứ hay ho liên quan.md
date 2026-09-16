Bản chất của "trò" này xoay quanh một vấn đề rất cơ bản trong toán học: Số ẩn và Số phương trình.

Theo nguyên tắc của toán học: Để tìm ra giá trị cụ thể của từng ẩn bạn cần số phương trình bằng đúng số ẩn.

Trong toán học, khi các phương trình có sự đồng bậc (các ẩn nhân chia với nhau chứ không cộng trừ với một số tự do), thì dù không tìm được từng ẩn, ta vẫn có thể tìm được tỉ lệ giữa chúng.

**Ví dụ về "Ép 3 ẩn thành 2 ẩn" :**

Lấy phương trình đầu tiên: $$3 = \frac{s}{v_n + v}$$

Bây giờ, chia cả tử số và mẫu số ở vế phải cho $v_n$:

$$3 = \frac{\frac{s}{v_n}}{\frac{v_n}{v_n} + \frac{v}{v_n}}$$

$$3 = \frac{\frac{s}{v_n}}{1 + \frac{v}{v_n}}$$

Đến đây, bạn hãy coi $\frac{s}{v_n}$ là một ẩn lớn (gọi là $X$), và $\frac{v}{v_n}$ là một ẩn lớn khác (gọi là $Y$). Phương trình trở thành:

(Do có 2 phương trình btw)

$$3 = \frac{X}{1 + Y}$$

Và

$$6 = \frac{X}{-1 + Y}$$

>> nếu thấy thiếu dữ kiện (cho ít phương trình hơn số ẩn), đừng hoảng! Hãy kiểm tra xem đề có đang hỏi tỉ số hay không. Nếu có, bạn chỉ cần xem một đại lượng bất kỳ là "đơn vị chuẩn" hoặc chia tất cả cho đại lượng đó là bài toán sẽ tự giảm số ẩn xuống.


# Gặp hệ $n > m$ (số ẩn nhiều hơn số phương trình) là "đặc sản" của các bài toán Toán – Lý nâng cao. Trong toán học, đây được gọi là hệ thiếu (underdetermined system).

**Những vấn đề (cạm bẫy) thường gặp khi $n > m$ :**

1. Bẫy "Đồng nhất thức" (Circular Logic)

2. Sai lầm mục tiêu (Tâm lý cố chấp): Tâm lý chung là muốn tìm ra đáp án cụ thể kiểu $x = 5, y = 10$. Khi có $n > m$, bạn sẽ hoảng loạn vì nghĩ mình làm sai hoặc đề thiếu dữ kiện, trong khi thực ra đề bài chỉ yêu cầu tìm một biểu thức quan hệ (như $x/y$, $x+y$) hoặc tìm giá trị lớn nhất/nhỏ nhất.

3. Bỏ sót "Phương trình ẩn" (Hidden Constraints): Bạn nghĩ rằng hệ có $n > m$, nhưng thực ra $n = m$. Phương trình bị thiếu thường nằm ở các ràng buộc hình học hoặc tính chất vật lý tự nhiên mà đề không thèm nhắc tới (ví dụ: dây không dãn thì gia tốc hai vật bằng nhau $a_1 = a_2$, hoặc bảo toàn động lượng, bảo toàn năng lượng).

4. Nghiệm rác và điều kiện biên: Khi hệ có nhiều ẩn hơn phương trình, nó sẽ tạo ra vô số nghiệm về mặt toán học. Tuy nhiên, về mặt vật lý, nhiều nghiệm trong đó vô lý (ví dụ: thời gian âm, khối lượng âm, cosin góc lớn hơn 1). Nếu không có kỹ năng chặn khoảng nghiệm, bạn sẽ kết luận sai.

# Skills :

**1. Gom biến (Lumping Variables)**

Thay vì cố giải từng ẩn đơn lẻ, hãy nhìn cấu trúc của phương trình để gom nhiều ẩn thành một "khối" (cụm đại lượng).

Nếu bạn thấy $x$, $y$, $z$ luôn xuất hiện cùng nhau dưới dạng $x+y$ hoặc $x/y$, hãy đặt ngay $X = x+y$ hoặc $Y = x/y$.

Thao tác này ngay lập tức nén số ẩn $n$ xuống một con số $k$ nhỏ hơn, và nếu $k = m$, hệ của bạn lại giải được bình thường.

**2. Chuẩn hóa số liệu (Normalization)**

Kỹ năng này dùng cho các phương trình đồng bậc (mọi số hạng đều có cùng tổng số mũ của các ẩn).

Khi đề bài không cho bất kỳ một con số cụ thể nào (chỉ cho tỉ lệ hoặc tham số), bạn có quyền "bịa" ra một con số cho một ẩn bất kỳ.

Ví dụ: Trong bài toán động lực học, bạn có quyền cho khối lượng $m = 1\text{ kg}$, hoặc trong bài toán quang hình, bạn cho tiêu cự $f = 1\text{ cm}$. Việc gán giá trị này lập tức giảm số ẩn xuống mà không làm thay đổi bản chất của các tỉ số cuối cùng.

**Phương trình đồng bậc (còn gọi là phương trình thuần nhất hoặc phương trình đẳng cấp) là phương trình mà mọi hạng tử (các thành phần cộng trừ) đều có tổng số mũ của các biến số bằng nhau.**

**3. Tham số hóa (Parameterization)**

Thay vì đi tìm giá trị cụ thể, hãy chấp nhận thực tại: hệ có vô số nghiệm.

Bạn hãy chọn $n - m$ ẩn làm "tham số tự do" (coi chúng như hằng số đã biết).

Sau đó, giải $m$ ẩn còn lại theo các tham số tự do đó. 

**4. Dùng Bất đẳng thức và Đạo hàm (Đánh giá biên)**

Khi $n > m$, phương trình biểu diễn một tập hợp nghiệm chứ không phải một điểm. Lúc này, đề bài thường sẽ hỏi: "Tìm giá trị lớn nhất/nhỏ nhất của đại lượng $Z$" hay gì đó...

ex :

Bước 1: Dùng phương trình có sẵn để dồn $Z$ về thành hàm số của một ẩn duy nhất (ví dụ $Z = f(x)$).

Bước 2: Dùng đạo hàm, lấy vi phân, hoặc áp dụng các bất đẳng thức (Cauchy-Schwarz, AM-GM) để tìm điểm cực trị của hàm đó.

**5. Truy quét Ràng buộc (Constraint Hunting)**

Trong Vật lý, toán học chỉ là công cụ. Khi thấy thiếu phương trình, hãy buông bút xuống và nhìn lại hệ thống vật lý để tìm các phương trình liên kết:

Liên kết hình học: Chiều dài dây không đổi $l = x_1 + x_2 + \dots$, quỹ đạo cong (vận tốc góc $\omega = v/R$).

Liên kết động học: Vật không lún xuống sàn thì gia tốc theo phương đứng $a_y = 0$, hai vật trượt trên nhau có lực ma sát trượt thì $F_{ms} = \mu N$.

Bảo toàn: Các định luật bảo toàn năng lượng, động lượng, mô-men động lượng chính là những phương trình bí mật.

...

---

