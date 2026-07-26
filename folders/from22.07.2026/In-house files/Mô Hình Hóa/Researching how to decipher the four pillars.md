# Thông tin ban đầu và Target hướng tới

**4 trụ cột :**


| Trụ cột | Câu hỏi trung tâm | Vai trò |
|---|---|---|
| **A. Bậc tự do (DOF)** | Cần bao nhiêu số để mô tả trạng thái hệ? | Xác định "kích thước" bài toán |
| **B. Ràng buộc & Biên** | Cái gì bị giữ cố định/liên kết? | Giảm DOF, cung cấp phương trình |
| **C. Đối xứng & Bảo toàn (Noether)** | Phép biến đổi nào để hiện tượng "trông y hệt"? | Giảm DOF hiệu dụng, cho tích phân đầu |
| **D. Xấp xỉ & Thang đo** | Cái gì "rất lớn/rất nhỏ/rất chậm" so với cái gì? | Tuyến tính hóa, đơn giản hóa |

**Câu hỏi nghiên cứu :** Định nghĩa chặt chẽ chính xác của 4 trụ cột này là gì ? Liệu có tồn tại cách nào để chắc chắn dù đề có khó ở mức độ IPHO, dù có khó đến mức nào, một thí sinh với trực giác trung bình cũng trả lời được "câu hỏi trung tâm" hay không hoặc "gần như" là như vậy (tức là tương đương với việc bài "Vật Lý" hoàn toàn thành bài "Toán") ?

# Định nghĩa

Bất kỳ hệ cơ học, quang học hay điện từ nào cũng có thể được mô hình hóa thành một điểm di chuyển trong một không gian trừu tượng.

**A. Bậc tự do (DOF)**

Định nghĩa chặt chẽ: Bậc tự do là số chiều (dimension) của đa tạp không gian cấu hình (Configuration Manifold) $\mathcal{Q}$ chứa mọi trạng thái khả dĩ của hệ.

Toán học: Nếu hệ có $N$ biến số định vị (tọa độ hạt, điện tích, góc quay) và $k$ ràng buộc độc lập, thì DOF $f = N - k$. Nó chính là số lượng tối thiểu các tọa độ suy rộng (generalized coordinates) $q_1, q_2, \dots, q_f$ cần để đặc tả hệ.

**B. Ràng buộc & Biên**

Định nghĩa chặt chẽ: Là các phương trình đại số hoặc vi phân xác định bề mặt đa tạp mà trạng thái hệ bị buộc phải nằm trên đó.

Toán học:

Holonomic (Ràng buộc toàn chỉnh): Dạng $F(q_1, \dots, q_N, t) = 0$. Ví dụ: Chiều dài dây không đổi $x^2 + y^2 - L^2 = 0$. Loại này làm giảm trực tiếp số DOF.

Non-holonomic (Ràng buộc không toàn chỉnh): Dạng bất phương trình $G(q_i) \ge 0$ (điều kiện biên như vật không xuyên qua sàn) hoặc phương trình vi phân không thể tích phân $\sum A_i dq_i + A_t dt = 0$ (như bánh xe lăn không trượt). Nó giới hạn quỹ đạo tiến triển của hệ.

**C. Đối xứng & Bảo toàn (Định lý Noether)**

Định nghĩa chặt chẽ: Theo định lý Noether, mỗi biến đổi đối xứng liên tục (dưới tác động của một nhóm Lie) giữ bất biến hàm Lagrangian của hệ sẽ sinh ra một tích phân chuyển động (đại lượng bảo toàn).

Toán học: Nếu hàm năng lượng của hệ không phụ thuộc trực tiếp vào một tọa độ $q_i$ (gọi là tọa độ cyclic), thì động lượng tương ứng với nó là một hằng số: $p_i = \frac{\partial L}{\partial \dot{q}_i} = \text{const}$.

**D. Xấp xỉ & Thang đo**

Định nghĩa chặt chẽ: Là quá trình phi thứ nguyên hóa hệ phương trình vi phân để cô lập các nhiễu loạn bậc cao, cho phép tuyến tính hóa không gian trạng thái cục bộ.

Toán học: Biểu diễn các đại lượng dưới dạng $x = x_0 + \epsilon x_1$, với $\epsilon \ll 1$. Nếu toán tử vi phân hội tụ, ta có thể cắt bỏ chuỗi Taylor để giải phương trình tiệm cận.





















