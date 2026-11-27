Giải tích (Calculus) là một môn học khác so với Algebra, Geometry. Nếu "Cơ sở hình học Euclid" và Đại số nổi trội với việc cực kỳ chặt chẽ và nghiêm ngặt, mọi thứ rất logic, dễ tiếp cận về mặt ký hiệu. Mặc dù Calculus hiện đại ngày nay cũng chính xác tuyệt đối và chặt chẽ tuyệt đối, tuy nhiên do "bề dày lịch sử", xuất phát điểm từ Newton, Leibniz hay Fluxion, "rất nhỏ", "vô cùng nhỏ" từ rất lâu về trước, các ký hiệu vốn từ trước đến nay đã "bẫy" người mới rất nhiều, nó có thể xảy ra tình trạng "thiếu thông tin" và "không thể phân biệt", không phân biệt được hằng số, tham số, hàm số..., thậm chí là hiểu nhầm tai hại từ tận "gốc rễ".

Vấn đề là rất nhiều tài liệu hiện nay đều không ý thức được việc này, có thể chính người viết cũng vậy. Mới đầu, bạn có thể vẫn thấy khá ổn khi "học vẹt" với đạo hàm, tích phân, nhưng càng về sau, kiểu như khi đến phương trình vi phân hay Vật Lý chuyên sâu... thì sẽ không ổn đâu.

**Tôi thường dùng quy ước dưới đây để viết:**

# Hàm số (Function)

Một hàm số là một quy tắc gán mỗi giá trị của một đại lượng (gọi là **biến độc lập**) cho đúng một giá trị của một đại lượng khác (gọi là **biến phụ thuộc**).

Thường vật lý sẽ chỉ sử dụng biến độc lập là thời gian t, và khi giải Vật Lý, tôi thường chỉ sử dụng biến độc lập là thời gian t.

Mọi đại lượng vật lý mà ta quan tâm nếu có thể phụ thuộc được vào t thì sẽ là hàm của t.

y = y(t); v = v(t); x = x(t); q = q(t);...

Tôi ghét việc sử dụng tham số, tôi 'yêu' hàm số hơn.

Ở đây thì: t là biến độc lập (independent variable);

y(t), v(t),... là biến phụ thuộc (dependent variable) — giá trị của nó phụ thuộc vào biến độc lập t; Bạn có thể coi nó là hàm;

Trong Vật Lý, tôi gần như chắc chắn luôn coi t là biến độc lập, những biến khác dù có là góc theta hay gì đó thì tôi cũng cho nó phụ thuộc vào t hết. Vì t rất tuyệt, bài nào cũng có t.

**Hãy ghi nhớ kỹ ý nghĩa của hàm số, và lý do tôi không dùng tham số.**

# Đạo hàm (Derivative)

Chỉ sử dụng ký hiệu Leibniz! Và không dùng tham số nào cả, chỉ dùng hàm hoặc biến độc lập thôi!

ex: dy(t)/dt thay vì dy/dt;

ex: dy(t) = f(t)dt

# PTVP

1 ví dụ đơn giản: 

y' = f(y)

Vậy thì rốt cuộc y' là cái gì? 

Cái f(y) là hàm phụ thuộc vào y; Nhưng nó rất kỳ cục. Vì vốn dĩ đạo hàm của hàm y chắc chắn không thể là dy/dy, vậy nên nó sẽ là dy/dt;

Đến đây mọi thứ càng rối hơn nữa, cái f(y) kia nhìn mâu thuẫn vậy?

Quên hết chúng đi! Hãy nhìn kết quả sau khi tuân theo **Quy tắc chung** chuẩn mực:

dy(t)/dt = f(y(t))

# Vế 1 biến thiên thì vế 2 không thể là hằng số

Ta có k, m là hằng.

Khi quan tâm -k * v_Bx(t), gọi đó là vế 1.

Và ta có vế 2 được miêu tả như sau: Là tích của khối lượng m và gia tốc a_Bx nhưng chưa rõ là hằng số hay hàm số.

**Quy tắc:** Nếu về 1 biến thiên, thì vế 2 buộc phải biến thiên, vế 2 không thể là hằng.

Nên: m * a_Bx(t) = -k * v_Bx(t)

# Những thứ còn lại tương tự!

**Quy tắc chung:** Không dùng tham số, chỉ dùng biến độc lập và hàm. Và chỉ dùng ký hiệu Leibniz.

Dùng quy tắc này cho phương trình vi phân, đạo hàm, tích phân,... Cho mọi thứ!


**Lưu ý:** Nếu là tự luận, ngay từ đầu bài giải, hãy viết một câu định nghĩa rõ ràng nhé.

Ví dụ: "Gọi $y = y(t)$ là hàm số mô tả sự biến thiên của $y$ theo biến độc lập $t$..."

**Bổ sung về nền tảng:**

Tôi hứng thú với Non-standard Analysis, nên dùng cái này nếu bạn học vật lý, theo tôi =))

Tin tôi đi =)), thật sự là ngày xưa, tôi thực sự vì nhận ra có điều gì sai sai giữa divergence với derivative thông qua cái giải thích hình ảnh trực quan của 3blue1brown, tôi thấy khá nghi ngờ hiểu biết của mình, kiểu như divvectorF(x_0,y_0) thì nó xét tại điểm (x_0, y_0) nhưng vấn đề là tôi lại ban đầu nghĩ rằng (x_0, y_0) là một điểm thuần túy (tức ko có vectorF nào tại điểm đó), và kiểu như bên trái là x_0 - dx còn bên phải là x_0 + dx, thì tức là nếu nói đơn giản theo mỗi trục x (thay vì thêm cả y,z, tại tôi lười nghĩ) thì là lấy đạo hàm giữa 2 điểm x_0 + dx và x_0 - dx, cơ mà nó cứ cấn cấn, sau đó tôi bắt đầu nghĩ kỹ lại về trường vectorF(x,y), kiểu như cứ mỗi điểm (x,y) bất kỳ hay với mọi điểm (x,y) trên mặt phẳng thì có điểm nào không có vector F hay không, tôi rất nghi ngờ, và tôi rất lười đọc mấy cái thuộc Standard Analysis, nhìn chung sau đó tôi đã tự bịa ra một cái tập số mới =)) (và hóa ra tôi đã bịa trúng cái tập số Hyperreal R* của Non-standard Analysis NSA, shock, tái phát minh) thậm chí tôi còn tự nêu ra tính phi archimedes cơ =)), mãi sau thì tôi mới biết đó là NSA, wow, nhìn chung thì tôi đã nhận ra rằng trong khoảng (x, dx) thì không tồn tại số thực nào cả, nhưng dx > 0, nói chung hóa ra tôi vô tình làm một công việc khá nặng 1 cách bản năng =)), hèn j lâu; cơ mà nếu nói rằng là việc t quay lại kiểu trăm năm trc để phát minh lại ra NSA thì cx ko nên nói như v, ý t là, dù t ko đọc trực tiếp NSA trước đây, nhưng mà kiểu ngày nay nó tồn tại nhiều thứ kiểu có cấu trúc khá giống 1 cách kỳ lạ để "gợi ý" ấy, kiểu như tích phân thì sẽ giống các pixel trên màn hình máy tính, ừ ừ kiểu v =)), nhìn chung thì dù về cơ bản t đã tái phát minh lại hyperreal R*, cơ mà t chơi kiểu thuần bẻ cong logic th =)), còn về hình học thì t vẫn thấy dị hợm, kiểu tự dưng 1 đường thẳng mượt mà của R thực lại có thể có vô số điểm số thực, nhưng lại tồn tại khoảng cách ngắn nhất giữa 2 điểm là dx, wow, nghe dị hợm vc, thậm chí là băm ra thành dx/2 hay gì đó :skull:, tức cx ko phải ngắn nhất







