# PHẦN 3 — TRỤ CỘT B: PHÁT HIỆN & ĐỊNH LƯỢNG HÓA RÀNG BUỘC (Constraints & Boundary)


Nguyên lý nền tảng của Trụ cột B:

**Mỗi ràng buộc hình học/vật lý độc lập là một phương trình đại số (hoặc vi phân) mà ta có thể viết ra một cách có hệ thống mà không cần hiểu rõ chuyển động của hệ. Phần khó khăn duy nhất là xác định hàm nào không đổi. Tuy nhiên, phạm vi các hàm này là hữu hạn và có thể liệt kê.**

# 3.0 LUỒNG 1 - THỦ TỤC PHÁT HIỆN RÀNG BUỘC "ĐẢM BẢO" (The Watertight Procedure)

Mục tiêu: Dành cho thí sinh đang bối rối và không có trực giác hình học. Quy trình này loại bỏ hoàn toàn việc phải "tưởng tượng" hệ chuyển động như thế nào.

**Cấu trúc của thủ tục:**

Bước 3.0.1: Gán tọa độ thô (Brute-force Coordinate Assignment).

Bước 3.0.2: Liệt kê "Các ứng viên Không đổi" (The Invariant Candidates).

Bước 3.0.3: Viết phương trình Đại số (The Algebraic Equation).

Bước 3.0.4: Lấy Vi phân toàn phần (The Total Differential).

Bước 3.0.5: Phân loại Ràng buộc (The Classification).

Hãy đi vào từng bước một cách chi tiết.

**Bước 3.0.1: Gán tọa độ thô (Brute-force Coordinate Assignment)**

Hành động cơ bản: Bạn không cần tìm "hệ trục tọa độ thông minh". Hãy chọn một hệ tọa độ Descartes (x, y) cho 2D hoặc (x, y, z) cho 3D. Đặt nó ở một điểm bất kỳ (ví dụ: góc dưới bên trái của hình vẽ).

**Thủ tục tuần tự (Hãy làm theo thứ tự này, KHÔNG được bỏ qua):**

1. Xác định tất cả các vật thể "điểm" (chất điểm, khối tâm của vật rắn, tâm của ròng rọc, các đầu mút của thanh/dây).

2. Gán một ký hiệu (ví dụ: (x_1, y_1), (x_2, y_2), ...) cho tọa độ của mỗi vật thể điểm đó.

3. Xác định tất cả các "điểm chốt" cố định (điểm treo tường, bản lề cố định, điểm nối đất).

4. Gán một ký hiệu cố định (ví dụ: (X_1, Y_1), ...) cho các điểm này. Chúng sẽ là hằng số trong các phương trình.

**Ví dụ.** Cho một ròng rọc cố định tại điểm O, một dây vắt qua ròng rọc, một đầu treo vật nặng A, đầu kia nối với vật B trượt trên mặt phẳng ngang.

Điểm cố định: O = (0, h)

Vật A: (x_A, y_A) (và vì nó chỉ chuyển động thẳng đứng, ta có thể đặt x_A = 0 cho đơn giản, nhưng bắt buộc phải viết ra).

Vật B: (x_B, y_B) (và vì nó chuyển động trên mặt bàn, y_B = 0, nhưng bắt buộc phải viết ra).

**Bước 3.0.2: Liệt kê "Các ứng viên Không đổi" (The Invariant Candidates)**

Vấn đề: Làm thế nào để biết đại lượng nào là "không đổi" (bị ràng buộc) mà không cần tưởng tượng?

Giải pháp: Thay vì tưởng tượng, ta liệt kê tất cả các loại đại lượng hình học có thể xảy ra trong bài toán Vật lý phổ thông. Danh sách này là hữu hạn. Bạn chỉ cần kiểm tra từng ứng viên trong danh sách.

**Bảng 3.0.2: Danh sách "Ứng viên Không đổi" (The Invariant Candidates List)**

#Đọc như này :

**Loại ràng buộc .... : "Ứng viên" (Hàm f) phải là hằng số .... : Điều kiện áp dụng / Công thức toán học .... ;**


C1. Thanh cứng, dây không giãn (nối 2 điểm) : Khoảng cách Euclid giữa hai điểm. : |r_1 - r_2| = L (hằng số). Công thức: sqrt( (x_1-x_2)^2 + (y_1-y_2)^2 ) = L. Thủ thuật (tránh căn): Dùng bình phương: (x_1-x_2)^2 + (y_1-y_2)^2 = L^2. ;

C2. Tổng chiều dài dây (nối nhiều điểm qua ròng rọc) : Tổng các đoạn thẳng (có thể gấp khúc) tạo nên sợi dây. : Ví dụ: Sợi dây tạo thành 3 đoạn: A→ròng rọc1, ròng rọc1→ròng rọc2, ròng rọc2→B. f = (x_A-x_R1)^2 + ... . Công thức: f = Σ (chiều dài đoạn thứ i) = const. ;

C3. Vật tiếp xúc với một bề mặt cố định (sàn, mặt phẳng nghiêng) : Khoảng cách (có dấu) từ vật đến bề mặt theo phương pháp tuyến. : Nếu bề mặt là đường thẳng y = a x + b, thì khoảng cách có dấu là: f = (y - a*x - b)/sqrt(a^2+1) = const. ;

C4. Vật tiếp xúc với một bề mặt di động (ví dụ: khối nêm đang trượt) : Khoảng cách có dấu giữa vật và bề mặt di động. : Nếu bề mặt nằm trên một vật khác có tọa độ (X, Y), ta phải tham số hóa vị trí của bề mặt đó theo tọa độ của vật. **Phương pháp chuẩn: Dùng hình học vector** (xem Chi tiết Bước 3.0.3). ;

C5. Vật rắn tuyệt đối : Khoảng cách giữa mọi cặp điểm trên vật. : Do vật rắn có 6 DOF (3D) hoặc 3 DOF (2D), ta thường biểu diễn nó bằng tọa độ khối tâm và góc quay. Công thức: Với mọi điểm P_i trên vật, |r_i - r_CM| = const. ;

C6. Bản lề nối hai vật : Vị trí của điểm bản lề là như nhau đối với cả hai vật. : r_1_hinge = r_2_hinge. Tương đương với hai phương trình (trong 2D): x_1 = x_2 và y_1 = y_2. ;

C7. Ràng buộc điện - Điện tích cô lập : Tổng điện tích trên một tập hợp các vật dẫn không nối với nguồn. : Σ Q_i = const. ;

C8. Ràng buộc điện - Mạch điện : Tổng điện áp rơi trên một vòng kín. : Σ U_i = 0 (Định luật Kirchhoff 2). Đây không phải là một hàm tọa độ, nhưng là một ràng buộc. ;

C9. Lăn không trượt : Điểm tiếp xúc giữa hai vật có vận tốc bằng nhau. : Đây là một ngoại lệ quan trọng! Nó là ràng buộc vận tốc, không phải vị trí. KHÔNG áp dụng phương pháp vi phân toàn phần ở Bước 3.0.4 cho nó. Thay vào đó, ghi nhận nó là một "Ứng viên vi phân" và chuyển sang Định lý B ở mục 3.1. ;

**Bước 3.0.3: Viết phương trình Đại số (The Algebraic Equation)**

Mục tiêu: Với mỗi "Ứng viên" tìm được ở Bước 3.0.2, ta viết ra một phương trình toán học có dạng:

f(x_1, y_1, x_2, y_2, ..., t) = 0 hoặc f(x_1, y_1, x_2, y_2, ...) = C (hằng số).

Quy tắc vàng cho phương trình này:

**1. Luôn ưu tiên dạng bình phương để tránh căn thức.**

ex :

Sai: sqrt((x_A - x_B)^2 + (y_A - y_B)^2) = L

Đúng: (x_A - x_B)^2 + (y_A - y_B)^2 = L^2

**2. Tham số hóa mọi thứ.**

Ví dụ: Một thanh cứng có chiều dài l, một đầu gắn bản lề cố định tại (0,0), đầu còn lại tự do. Tọa độ đầu tự do là (x, y). Phương trình ràng buộc là: x^2 + y^2 = l^2.

Ví dụ: Một nêm có khối lượng M trượt trên sàn, mặt phẳng nghiêng của nêm tạo với phương ngang góc α. Một vật m nằm trên mặt nêm. Tọa độ khối tâm của nêm là (X, 0). Vị trí của vật m trên nêm được xác định bởi khoảng cách s dọc theo mặt phẳng nghiêng. Khi đó, tọa độ của m là:

x_m = X + s*cos(α)

y_m = s*sin(α)

Phương trình ràng buộc ở đây chính là việc x_m và y_m được tham số hóa bởi X và s, và ta có thể thay trực tiếp vào Lagrangian sau.

**3. Xử lý bề mặt di động:**

Giả sử có một rãnh tròn bán kính R trên một vật di động có tâm tại (X, Y). Một hạt chuyển động trên rãnh đó. Tọa độ của hạt là (x, y). Ràng buộc là: (x - X)^2 + (y - Y)^2 = R^2. Lưu ý rằng X, Y cũng là các biến và đã có sẵn trong danh sách tọa độ thô của bạn.

**Bước 3.0.4: Lấy Vi phân toàn phần (The Total Differential)**

Mục tiêu: Chuyển đổi phương trình đại số (ở Bước 3.0.3) thành một phương trình vi phân tuyến tính. Đây là bước "máy móc" nhất. Bạn KHÔNG CẦN suy nghĩ về chuyển động.

**Thuật toán:**

1. Viết lại phương trình ràng buộc dưới dạng: F(q_1, q_2, ..., q_n, t) = 0, với q_i là các tọa độ thô.

2. Tính vi phân toàn phần của F: (Đây là công thức toán học duy nhất bạn cần dùng trong bước này)

Công thức:

$$dF = \frac{\partial F}{\partial q_1} dq_1 + \frac{\partial F}{\partial q_2} dq_2 + \dots + \frac{\partial F}{\partial q_n} dq_n + \frac{\partial F}{\partial t} dt = 0$$

**Hãy hình dung nó như sau:**

Với mỗi biến q_i trong danh sách, bạn tính đạo hàm riêng của F theo biến đó (coi tất cả các biến khác là hằng số).

Sau đó, bạn nhân đạo hàm đó với δq_i (hoặc dq_i).

Cuối cùng, bạn viết một phương trình tuyến tính với các số hạng (hệ số) * δq_i.

**Trong cơ học Lagrange/d'Alembert:**

Vi phân thực $dq_i$ có tính đến sự phụ thuộc thời gian $dt$.

Dịch chuyển ảo $\delta q_i$ là dịch chuyển tức thời tại $t = \text{const}$ ($\delta t = 0$).

**Tôi không chắc "Công thức" ở trên là chính xác hoàn toàn cho lắm, hãy kiểm tra kỹ lại nhé, sorry!**

**Sự khác biệt :**

lấy đạo hàm theo thời gian ra vận tốc $\sum A_i v_i + A_t = 0$

phương trình dịch chuyển ảo dùng cho nguyên lý công ảo ($\sum A_i \delta q_i = 0$

**Ex.** Ví dụ: Thanh cứng: F(x, y) = x^2 + y^2 - l^2 = 0

∂F/∂x = 2x

∂F/∂y = 2y

Phương trình vi phân: 2x*δx + 2y*δy = 0 => x*δx + y*δy = 0.

Phương trình này cho bạn biết mối quan hệ giữa dịch chuyển ảo theo phương x và y. Chia cả hai vế cho dt, bạn có x*v_x + y*v_y = 0, là đạo hàm bậc nhất của ràng buộc vị trí.

**Bước 3.0.5: Phân loại và Kết luận (The Classification)**

Sau khi có được phương trình dạng Σ A_i δq_i + A_t δt = 0, bạn cần thực hiện 2 nhiệm vụ:

1. Rút ra số bậc tự do bị khử:

Phương trình vi phân này cho thấy δq_1 có thể được biểu diễn qua các δq_i khác. Điều này có nghĩa là số biến độc lập (bậc tự do) đã giảm đi 1. Hãy giảm f_raw của bạn đi 1.

2. Kiểm tra tính "Toàn chỉnh" (Holonomic vs. Non-holonomic):

Câu hỏi: Phương trình Σ A_i δq_i = 0 có thể tích phân được để trở lại dạng F(q) = const không?

Đối với 99.9% các bài toán cơ học trong chương trình phổ thông: Mặc định nó là toàn chỉnh. Chỉ cần bạn phát hiện ràng buộc từ một ứng viên trong Bảng 3.0.2 (thanh cứng, dây không giãn, bề mặt, v.v.), thì nó là toàn chỉnh. Bạn không cần phải lo lắng về Định lý Frobenius cho các trường hợp này.

NGOẠI LỆ DUY NHẤT: Ràng buộc lăn không trượt. (Xem mục 3.1 bên dưới). Đây là trường hợp duy nhất bạn phải dùng đến Định lý B để kiểm tra. Nếu không phải là lăn không trượt, bạn có thể bỏ qua mục 3.1.


# 3.1 TRƯỜNG HỢP ĐẶC BIỆT: RÀNG BUỘC LĂN KHÔNG TRƯỢT & ĐỊNH LÝ B

**Tình huống phát sinh:** Khi bạn gặp cụm từ "lăn không trượt" (rolling without slipping), bạn KHÔNG ĐƯỢC áp dụng Bước 3.0.4 một cách cảm tính. Lý do: ràng buộc này thường có dạng ràng buộc vận tốc (v = Rω), và nó có thể là không toàn chỉnh (non-holonomic), nghĩa là nó không làm giảm không gian cấu hình, mà chỉ làm giảm không gian vận tốc.

**Quy trình xử lý bắt buộc (checklist):**

1. Nhận diện: Nếu thấy "lăn không trượt", DỪNG LẠI. Đừng cố gắng viết ngay ra một phương trình vị trí.

2. Viết ràng buộc vận tốc: Ngay lập tức viết ra đẳng thức vận tốc của điểm tiếp xúc:

v_diem_tiep_xuc_cua_vat_1 = v_diem_tiep_xuc_cua_vat_2

3. Đưa về dạng Pfaff: Biểu diễn đẳng thức này dưới dạng Σ A_i(q) dq_i = 0.

4. Kiểm tra bằng Định lý B (Tiêu chuẩn Frobenius): Đây là bước duy nhất cần một chút toán, nhưng nó là một thuật toán. Bạn có thể làm nó một cách máy móc.

**Định lý B (Tiêu chuẩn Frobenius).**

Cho ràng buộc Pfaff ω = Σ A_i(q) dq_i = 0. Ràng buộc này là toàn chỉnh (tức là nó làm giảm số bậc tự do của cấu hình) **khi và chỉ khi**:

ω ∧ dω = 0

Nếu ω ∧ dω ≠ 0, ràng buộc là không toàn chỉnh (non-holonomic). Nó KHÔNG làm giảm số bậc tự do của hệ, nhưng nó làm giảm số vận tốc độc lập.

**Hướng dẫn thực hiện kiểm tra (máy móc):**

Bước 1: Xác định ω.

Bước 2: Tính dω (vi phân ngoài của ω).

Công thức: Nếu ω = A dx + B dy + C dz, thì dω = (∂B/∂x - ∂A/∂y) dx∧dy + (∂C/∂x - ∂A/∂z) dx∧dz + (∂C/∂y - ∂B/∂z) dy∧dz.

Bước 3: Tính tích ngoài ω ∧ dω.

Bước 4: Nếu kết quả bằng 0, ràng buộc là toàn chỉnh (giảm DOF). Nếu khác 0, ràng buộc là không toàn chỉnh (GIỮ NGUYÊN DOF).

**Ex.**

Đĩa tròn lăn trên đường thẳng: ω = dx - R dθ. dω = 0, nên ω ∧ dω = 0. Toàn chỉnh. Giảm DOF.

Đĩa tròn lăn tự do trên mặt phẳng (xe đạp): Hệ có 3 DOF (x, y, θ). Ràng buộc không trượt ngang: -sin θ dx + cos θ dy = 0. Ta có ω ∧ dω = - dx ∧ dy ∧ dθ ≠ 0. Không toàn chỉnh. Không giảm DOF.

**Kết luận cho B2: Khi tính f_eff, chỉ trừ đi các ràng buộc toàn chỉnh (tích phân được). Ràng buộc không toàn chỉnh (ví dụ như lăn tự do 2D) thì KHÔNG được trừ, mặc dù nó tồn tại.**


# 3.2 Ràng buộc một phía (Unilateral Constraints & Detachment)

# 3.3 Nguyên lý Công ảo & Biểu diễn Lực liên kết qua Ràng buộc






























