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









































