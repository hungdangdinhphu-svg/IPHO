

## 0.1. 2 VẤN ĐỀ LỚN CHÍNH


Vấn đề 1 : Chuyển Bài Vật Lý về Bài Toán, thường sẽ là Mô Hình Hóa, Xấp Xỉ, Đọc dữ kiện và vẽ hình.

Vấn đề 2 : Dùng cấu trúc Toán Học để giải.

Vấn đề 2 là 1 trong vấn đề lớn, và phần này ta sẽ chỉ bàn sâu về nó.

## Phát biểu về cấu trúc giữa Vật Lý và Toán

Mỗi dạng bài Vật lý sống trong một cấu trúc Toán học. Cấu trúc đó quyết định cách bài toán được giải. Biến tấu của bài Vật lý của người ra đề thi thì không phá vỡ cấu trúc — nó chỉ thay đổi vỏ bọc.

Nói cách khác:

Vật lý là biểu hiện. Toán học là cấu trúc bên dưới.

Cùng một cấu trúc Toán có thể sinh ra nhiều dạng bài Vật lý khác nhau.

Cùng một dạng bài Vật lý luôn nằm trong cùng một cấu trúc Toán.

Đây không phải là một quan sát triết học suông. Nó là một nguyên lý thực chiến có hệ quả trực tiếp:

Thành thạo cấu trúc Toán A ⇒ giỏi mọi bài Vật lý thuộc cấu trúc A.

Không thành thạo cấu trúc Toán A ⇒ dù học thuộc hàng trăm bài Vật lý thuộc A, vẫn sẽ dễ kẹt khi gặp biến tấu mới.

Một bài Vật lý, sau khi mô hình hóa, trở thành một bài Toán. Nếu không có Toán, bạn không có gì để giải. Vậy nên:

Bước chuyển Vật lý → Toán là bước quyết định.

Cấu trúc của bài Toán quyết định phương pháp giải.

Phương pháp giải là thứ bạn cần thành thạo, hãy biết dùng "thuật toán" để giảm tải.

Cấu trúc Toán là "ẩn" nhưng hữu hạn,

Một bài Vật lý có thể trông rất khác một bài Vật lý khác. Nhưng sau khi mô hình hóa, chúng có thể cùng một cấu trúc Toán.

Biến tấu Vật lý không phá vỡ cấu trúc! Bạn chỉ cần nhận diện cấu trúc, rồi áp dụng phương pháp.

## Pre & Suf

Điều quan trọng: Bản chất vật lý & Precondition, sufficient condition (Tôi có nêu suốt ngày) để giới hạn cấu trúc toán lại.

**Điều kiện cần** (Necessary condition) khác **Điều kiện đủ** (Sufficient condition), vậy nên hãy hiểu bản chất cả hai nhé.

**Necessary condition**: Là điều kiện BẮT BUỘC phải có, nếu thiếu nó thì chắc chắn không xảy ra; Nhưng chỉ có nó thì chưa chắc;

**Sufficient Condition**: Chỉ cần có nó thì chắc chắn xong rồi;

## Quy Trình Và Phương Pháp cố định và xác định để giải Tổng Quát một Dạng

Quy trình này nó cũng rất giống thuật toán, nhưng không phải thuật toán, vì thuật toán là dành cho máy tính. Nhờ Phương pháp và quy trình này sẽ giảm tải nhận thức ,trực giác, **"vấn đề tìm kiếm"** cực kỳ mạnh cho thí sinh tham dự HSGQG, IPHO, VPHO, TST, và kể cả Researchers. Thật ra, giải pháp cho **"vấn đề tìm kiếm"** bắt buộc phải dựa trên cấu trúc giữa Vật Lý và Toán.

## Vấn đề tìm kiếm ?


Insight: Thật ra, có vẻ như gần như mọi bài Vật Lý từ Nâng cao đến HSGQG Vật Lý, IPHO mà ta không thể giải dễ dàng bằng cách phương pháp thông thường theo cách "tầm thường" được (Tức là vẫn dùng các CÔNG CỤ, Phương pháp mà ta đã được học để giải, nhưng nó rất khó khăn với chúng ta) đều là do vấn đề tìm kiếm.

Một số ví dụ: 

+) Trong mạch điện tuyến tính, nếu ta chỉ dùng Ohm's Law, Kirchhoff (Không dùng Phương pháp cực mạnh bưng từ Đại học xuống là Nodal Analysis hoặc Phương pháp điện thế nút) để giải, với các bài ở độ khó thi chuyên vào 10. Ta sẽ rất mệt mỏi với nó, vấn đề là gì? Đó là ta không biết áp dụng các CÔNG CỤ (Ohm's Law, Kirchhoff) vào các phần nào (**CHỖ**) của mạch điện ra giải được.

+) Hay là bài Động học mà không dùng các công cụ hạng nặng (như Phương pháp/Thuật toán Tọa độ Hóa Mở rộng,...) mà chỉ dùng các CÔNG CỤ thông thường đã được học như v=s/t; vận tốc góc w; vận tốc dài;... Thì ta sẽ vẫn rất khó để tìm được phần nào (**CHỖ**) của bài Vật Lý đó để dùng CÔNG CỤ để lập ra hệ phương trình/phương trình để giải ra được.

Nói dễ hiểu: Vấn đề tìm kiếm hiểu sơ sơ là : Vấn đề tìm kiếm ra được những/một **CHỖ** mà mình cần dùng những CÔNG CỤ mình có để giải được. Điều này tổng quát và kinh khủng đến mức nó có thể bao gồm được cả Mô Hình Hóa.

**Vì sao những thứ như Nodal Analysis lại mạnh như vậy?**

Đơn giản là vì nó là Thuật Toán. Có điều nó tuyệt vời đến mức Học Sinh có thể dùng được hợp pháp trong phòng thi mà không cần mang theo 1 cái Computer. Còn nếu ai lập luận bảo rằng Giải Hệ Phương Trình n ẩn n phương trình từ Nodal Analysis là mệt thì thật ra là do họ gà thôi, vì cái "pattern" của cái hệ phương trình đó rất dễ nắm bắt (chuẩn bị trước).

**Những suy nghĩ của tôi:**

```txt

Tôi có 1 thói quen đó là những gì tôi thấy muốn làm nhưng gặp khó khăn, tôi sẽ định nghĩa rõ vấn đề, và rồi tìm cách giải nó...mặc dù tôi đã kiệt sức. Khá giống với cái tư tưởng nào đó hồi tôi làm coder, rằng là chưa làm xong thì không có đi đâu hết. Nhưng tôi thật sự đuối khủng khiếp, không giống các vấn đề thông thường, tôi nhìn lướt qua biết hết sạch và nhẹ tênh, thì cái này tôi phải vắt và gồng não rất căng:\; Nên là có thể sẽ có vấn đề nghiêm trọng.

Nhưng đây là ý tưởng: Mỗi 1 bài toán, chỉ có hữu hạn (thường là rất ít, hoặc chỉ 1 cái) cách giải hợp lý. Vậy nếu ta có thể dùng cái **Điều kiện cần/đủ** cho Vấn Đề 1, vậy nếu ta làm nó còn mạnh mẽ hơn nữa để nó sang được Vấn đề tìm kiếm của Vấn đề 2 này thì sao?

Tức là, trong 1 bài Vật Lý, thì sẽ có những **CHỖ** mà phải thỏa những điều kiện đặc biệt nào đó, một khi ta biết được những điều kiện đặc biệt đó thì ta sẽ biết được những **CHỖ** đó vì đơn giản là **CHỖ** thỏa mãn, và ta để có thể áp dụng CÔNG CỤ.

Thế nếu "những điều kiện đặc biệt nào đó" là hữu hạn, và ít, và cách xác định chúng là tương đối dễ dàng cho gần như mọi bài Vật Lý dù là ở độ khó IPHO, VPHO thì sao?

Well.... Dĩ nhiên là vẫn sẽ cần trực giác, nhưng tôi đang hướng đến việc giảm sự phụ thuộc lớn vào nó.


**Tôi nói nó chi tiết và rõ ràng hơn:**

Vấn đề: Tìm ra một/nhiều **CHỖ** để sử dụng CÔNG CỤ mà mình có, để giải được vấn đề.

"giải" ở đây có thể được hiểu kỹ hơn là chuyển bài Vật Lý về bài Toán.

+) Thường (gần như chắc chắn) các bài của HSGQG, HSGTP đều chỉ có hữu hạn (1 hoặc rất ít) cách giải hợp lý.

+) Những **CHỖ** mà khi ta áp dụng công cụ vào thì sẽ gặp bế tắc là do nó không thỏa tập điều kiện tổng quát hữu hạn A (Viết tắt là Tập A).

+) Ngược lại, nếu thỏa, thì những **CHỖ** đó sẽ giúp ta giải được hoặc giải được 1 phần hoặc là 1 bước có ý nghĩa trong hành trình giải.

+) Một khi ta biết được tập A thì: Ta sẽ biết được những **CHỖ** thỏa tập A, hay giúp ta giải được Vấn đề trên.

+) Phải đảm bảo rằng ta có được tập A & tập A có tồn tại, hoặc gần như được như vậy. Hoặc có được ít nhất 1 cách để tìm được tập A cho bài bất kỳ thuộc HSGQG mà nó phải : Dễ dàng để áp dụng & Dễ dàng để tìm ra tập A (if any).

+) Với chương trình phổ thông/HSG, có thể xấp xỉ bằng một thư viện hữu hạn và khá nhỏ. Với IPHO/VPHO, đây là 1 vấn đề lớn, thế nên tôi mới ghi thêm là "cách để tìm được tập A cho bài bất kỳ thuộc HSGQG". Nhìn chung, tôi cũng thấy khó khăn khi phân tích những thứ này.

+) Kiểu như tập A là tập precondition của các toán tử biến đổi. Và có vẻ như vừa là “tìm biểu diễn + chuỗi biến đổi + precondition” và vừa là tìm **CHỖ**. Có vẻ như nó có thể là một họ precondition có tham số.


```

**Nói chặt chẽ, sửa sai và hoàn thiện hơn**

Bài Toán Tìm Kiếm là :

Tìm cặp (ℓ, CHỖ) sao cho Pre(ℓ) được thỏa tại CHỖ, và việc áp dụng ℓ tại CHỖ tạo ra bước tiến có ý nghĩa.

Giờ tôi sẽ gọi nó như vầy nhiều hơn cho an toàn: họ precondition {Pre(ℓ)} thay vì "Tập A".

Bài toán tìm kiếm (Search Problem): Cho bài toán B với mô hình M = (O, V, L, C, Q, I). Tìm một dãy hữu hạn các cặp (ℓ₁, CHỖ₁), (ℓ₂, CHỖ₂), ..., (ℓₙ, CHỖₙ) sao cho:

1. Pre(ℓᵢ) được thỏa tại CHỖᵢ trong trạng thái bài toán sau bước i-1.

2. Post(ℓᵢ) tại CHỖᵢ tạo ra một ràng buộc mới có ý nghĩa trong C.

3. Sau bước n, C ∪ L ⊢ Q.


### Model Specification, Well-posedness & Derivation Validity

Nói ngắn: Bài toán không khó vì không biết dùng công cụ, mà khó vì mô hình chưa đúng, chưa đủ, chưa nhất quán, chưa hợp lệ, hoặc chưa đóng kín. Khi mô hình đã đạt các tính chất đó, việc giải thường trở nên máy móc. Khi nó chưa đạt, mọi nỗ lực “tìm kiếm” đều thành rất đáng lo.


**1. Phát biểu hình thức**

Cho một bài toán B. Muốn giải nó, ta không chỉ cần công cụ. Ta cần xây dựng một mô hình hình thức:

M=(O,V,L,C,Q,I)

Trong đó:

O: ontology — các thực thể, trạng thái, cấu trúc, topology của bài toán...

V: biến — ẩn, tham số, hằng số, đại lượng cần tìm...

L: tập định luật/công cụ — mỗi định luật phải kèm:

miền xác định Dom(ℓ),

*Dom(ℓ) và Pre(ℓ) là hai thứ khác nhau; Một định luật có thể có Dom rộng nhưng Pre hẹp, hoặc ngược lại. Cần tách bạch.



điều kiện cần Pre(ℓ),

điều kiện đủ Suf(ℓ),

kết luận Post(ℓ),

sai số/xấp xỉ nếu có Err(ℓ).

C: ràng buộc — dữ kiện, điều kiện biên/đầu, đối xứng, bảo toàn, liên hệ hình học, điều kiện lý tưởng hoá...

Q: câu hỏi — cần xác định cái gì, dạng đáp án, đơn vị...

I: ánh xạ diễn giải.

Giải bài là tìm một dẫn xuất:

C∪L⊢Q

sao cho M là well-posed và dẫn xuất là sound + complete.

**2. Bảy điều kiện của Vấn đề 0**

Một mô hình được gọi là “hiểu rõ bản chất, đủ, không nhầm lẫn” khi thoả:


(1) Diễn giải đúng — Interpretation

(2) Hợp lệ — Soundness

Mọi định luật chỉ được dùng khi điều kiện cần của nó thoả.

Nếu Pre(ℓ) được thỏa, thì Post(ℓ) là đúng trong phạm vi Dom(ℓ). 

Mọi định luật ℓ chỉ được áp dụng khi Pre(ℓ) được thỏa. Nếu Pre(ℓ) chỉ được thỏa xấp xỉ (ví dụ: góc nhỏ, vận tốc nhỏ so với c), thì phải cẩn thận.

(3) Đầy đủ / Đóng kín — Completeness / Closure

Tập C∪L phải đủ để xác định Q.

(4) Nhất quán — Consistency

Không được có hai ràng buộc/định luật mâu thuẫn nhau trong cùng mô hình.

(5) Xác định — Well-posedness

Nếu là xác định nghiệm thì, Nghiệm phải:

tồn tại,

duy nhất (hoặc phải biện luận mọi nghiệm),

ổn định với nhiễu nhỏ nếu bài toán yêu cầu.

(6) Đầy đủ biên & trường hợp — Boundary/Case Completeness

Mọi trường hợp phải được xét.

(7) Biến đổi hợp lệ — Derivation Validity

**Khi đã biết rõ và cực kỳ chặt chẽ Điều kiện đủ (sufficient condition) thì đây là khá ngon để tìm ra CHỖ để dùng các CÔNG CỤ:**

Sau khi chọn công cụ n, DUYỆT ĐẦY ĐỦ (kỹ kiểu như từng "pixel" nếu là Hình Ảnh, từng chữ cái nếu là Văn Bản) xem coi có chỗ nào áp dụng được không, và nếu áp dụng thì nó có vẻ có ý nghĩa gì không?

Còn nếu như căng thẳng quá thì có thể ráng viết hết ra, rồi lọc. Yea, khá là "brute-force":);

Dĩ nhiên trực giác có thể hỗ cực kỳ chủ chốt cho việc này để giảm bớt gánh nặng "brute-force", nhưng hãy cực kỳ cẩn trọng vì trực giác có thể lừa bạn hoặc bỏ qua những thứ cần phải làm.


## Insight

Nếu ta coi **CÔNG CỤ** không chỉ đơn giản là những thứ tôi từng nói, mà nó bao gồm cả Cấu Trúc Toán Học, thì tức là ngay khi nhìn vào bài Vật Lý, ta chỉ cần duyệt nhanh trong đầu (trực giác nhưng đầy đủ) xem coi bài Vật Lý đó dùng Cấu Trúc Toán Học nào rất dễ dàng, sau đó ta sẽ tự nhận rằng để áp dụng trực tiếp Cấu Trúc Toán Học đó có cần Mô Hình Hóa không, và Mô Hình Hóa ở CHỖ nào cũng rất dễ dàng, lý do là vì ta đã đi ngược cách làm thông thường. Đây là 1 cách mạnh trong Vấn Đề Mô Hình Hóa.

Sau khi biết rõ Cấu Trúc Toán Học mà bài Vật Lý đó đang dùng, thì ta sẽ chuyển bài Vật Lý sang Toán bằng cách sử dụng **Quy Trình Và Phương Pháp cố định và xác định để giải Tổng Quát Một Dạng Vật Lý**.

Sau đó, ở bước giải Toán, ta sẽ sử dụng **Quy Trình Và Phương Pháp cố định và xác định để giải Tổng Quát Một Cấu Trúc Toán Học**;

Tức là ta cần chuẩn bị trước ở nhà những thứ chính sau:

**Quy Trình Và Phương Pháp cố định và xác định để giải Tổng Quát Một Dạng Vật Lý**; **Quy Trình Và Phương Pháp cố định và xác định để giải Tổng Quát Một Cấu Trúc Toán Học**; Và những thứ khác tôi có nói rồi...

**Ví dụ kinh điển:** Mạch điện tuyến tính ở Kỳ thi tuyển sinh vào THPT Chuyên (Lớp 9 lên Lớp 10) thực chất là cấu trúc toán học Nodal Analysis Đại Số Tuyến Tính, well, quá kinh điển rồi nên tôi không nói nữa. Nhưng học sinh lớp 9 thi vào chuyên dĩ nhiên không thể biết được điều này, nên họ sẽ chỉ xài mỗi Ohm's Law + Kirchhoff và kỹ năng giải toán & trực giác luyện đề của mình để cố mò mẫm cách giải.
