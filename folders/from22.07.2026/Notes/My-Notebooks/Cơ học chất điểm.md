# CƠ CHẤT ĐIỂM — THƯ VIỆN CÔNG CỤ CHO VẤN ĐỀ 1 & VẤN ĐỀ 2

**Phạm vi:** Động học · Động lực học · Các định luật bảo toàn · Dao động (trong cơ học chất điểm)
**Mục tiêu:** HSGQG Vật lý (Việt Nam) và IPhO, theo triết lý trong README: *giảm phụ thuộc trực giác bằng cách biến "tìm CHỖ" thành duyệt có hệ thống một thư viện precondition hữu hạn.*
**Phiên bản:** 0.1 (bản đầu, chắc chắn còn sai sót; xem Phần 0 và Phần 9)

---

## PHẦN 0. TUYÊN BỐ TRUNG THỰC, PHẠM VI, CÁCH ĐỌC

### 0.1. Những gì tôi cam kết và không cam kết

Bạn yêu cầu không "lách" và không làm màu. Vì vậy:

1. **Không có thuật toán vạn năng.** Tài liệu này là *thư viện precondition xấp xỉ, hữu hạn, có tổ chức*, đúng như kết luận trong README của bạn. Nó **giảm** vai trò của trực giác chứ **không xóa** được. Ở mỗi công cụ tôi ghi rõ bước nào vẫn cần phán đoán.
2. **Kiểm chứng.** Các công thức dễ sai nhất được tôi kiểm tra bằng sympy/numpy trước khi đưa vào (danh sách ở Phần 9.2). Phần còn lại là kiến thức chuẩn tôi tự kiểm bằng suy dẫn và trường hợp giới hạn, **chưa** chạy code kiểm cho từng dòng.
3. **Không trích đề.** Tôi không có đề HSGQG/IPhO thật để đối chiếu và không muốn bịa nguồn. Mọi ví dụ là *bài dựng lại theo cấu trúc* (ghi rõ), không phải "đề năm X".
4. **Tôi không truy cập được thư mục GitHub bạn nêu** (trang chặn truy cập tự động), nên không biết định dạng file hiện có của bạn. Tài liệu này độc lập; bạn có thể chỉnh định dạng khi đưa vào repo.
5. **Chỗ tôi phải diễn giải hoặc giả định** được gắn nhãn ở Phần 9.1. Đáng chú ý nhất: cụm "Phương pháp/Thuật toán Tọa độ hóa mở rộng" tôi *đoán* nghĩa (xem K7) và bạn nên đối chiếu với ý bạn.

### 0.2. Nhãn độ tin cậy dùng trong tài liệu

| Nhãn | Ý nghĩa |
|---|---|
| **[C]** | Kiến thức chuẩn, đã kiểm bằng suy dẫn / giới hạn (một số có kiểm số, xem 9.2) |
| **[H]** | Heuristic / cách tổ chức của tôi, hữu ích nhưng không phải định lý |
| **[EXT]** | Ngoài đề cương trong ảnh bạn gửi, nhưng cần cho HSGQG/IPhO (ví dụ momen xung lượng chất điểm, Kepler, Lagrange) |
| **[?]** | Tôi chưa chắc hoặc cần bạn đối chiếu |

### 0.3. Phạm vi đã chốt

Theo ảnh bạn gửi, 16 mục chia thành 4 nhóm:

| Nhóm | Mục trong ảnh | Mã công cụ trong tài liệu |
|---|---|---|
| a. Động học | thẳng đều/biến đổi đều · rơi tự do · tròn đều/biến đổi đều · khảo sát bằng phương pháp tọa độ | K1–K8 |
| b. Động lực học | định luật Newton · các lực cơ học · ứng dụng vào bài tập · hệ quy chiếu phi quán tính | D1–D10 |
| c. Bảo toàn | động lượng · công–công suất · cơ năng · va chạm | C1–C9 |
| d. Dao động | DĐĐH cơ bản (v, a) · con lắc đơn/lò xo/vật lý/xoắn · tắt dần–cưỡng bức–cộng hưởng (phương trình vi phân) · DĐĐH chất điểm | O1–O8 |

**Không làm:** động lực học vật rắn (chỉ nhắc ranh giới, và cho mô men quán tính như *dữ kiện đầu vào* khi cần con lắc vật lý/xoắn), chất lưu, sóng, nhiệt, điện từ, tương đối hẹp.

**Điều cần biết về IPhO** (từ syllabus IPhO công khai, bản 2015 và các bản quốc gia dựa trên nó): syllabus có định luật bảo toàn động lượng/momen động lượng/năng lượng, lực quán tính và lực ly tâm cùng thế năng trong hệ quay, cơ học thiên thể (Kepler, năng lượng trên quỹ đạo elip), và ghi rõ rằng đề *không được đòi hỏi* dùng nhiều vi–tích phân hay giải phương trình vi phân, đồng thời đề *có thể chứa khái niệm ngoài syllabus nếu cung cấp đủ thông tin*. Hệ quả cho bạn: **kỹ năng chuyển hóa (Vấn đề 1, 2) quan trọng hơn kỹ thuật giải ODE**, và công cụ "hạng nặng" (Lagrange, ODE tổng quát) là *bonus hợp pháp*, không phải nền tảng. Đề cương HSGQG Việt Nam thay đổi theo năm nên tôi chỉ dựa vào ảnh bạn gửi. **[?]**

### 0.4. Ký hiệu

Vector in **đậm** (**F**, **v**, **a**, **r**); vô hướng in thường. `·` là tích vô hướng, `×` là tích có hướng. Đạo hàm theo thời gian: ẋ, ẍ. ω₀ là tần số riêng; γ = b/(2m) là hệ số tắt; ρ là bán kính cong quỹ đạo. Gia tốc trọng trường g coi là hằng số trừ khi ghi khác.

---

## PHẦN 1. KHUNG HÌNH THỨC ĐỂ "TÌM CHỖ" CÓ HỆ THỐNG

Phần này biến ý tưởng trong README (M = (O,V,L,C,Q,I), họ {Pre(ℓ)}, tìm cặp (ℓ, CHỖ)) thành thứ *có thể duyệt* cho cơ học chất điểm.

### 1.1. Cụ thể hóa mô hình M cho cơ chất điểm

| Thành phần | Nội dung cụ thể trong cơ chất điểm |
|---|---|
| **O** (ontology) | Chất điểm; vật coi như chất điểm (điều kiện: kích thước ≪ mọi độ dài của bài, không quay đáng kể); dây, ròng rọc, lò xo, mặt (nhẵn/nhám, cố định/di động), nêm; hệ quy chiếu; trường (trọng trường, hấp dẫn, quán tính) |
| **V** | Tọa độ tổng quát q_j(t); vận tốc, gia tốc; lực chưa biết (phản lực N, ma sát f, sức căng T); thời gian; các hằng số (m, k, g, μ, e…); *đại lượng cần tìm* |
| **L** | Thư viện công cụ K1–K8, D1–D10, C1–C9, O1–O8 và toán tử tiền xử lý P1–P12, mỗi cái kèm Dom, Pre, Suf, Post, Err (1.2) |
| **C** | Dữ kiện đề; ràng buộc hình học (dây không dãn, tiếp xúc, lăn không trượt); điều kiện đầu/biên; đối xứng; lý tưởng hóa (dây nhẹ, ròng rọc nhẹ, nhẵn) |
| **Q** | Đại lượng cần tìm, dạng đáp án (biểu thức/số/điều kiện tồn tại/cực trị), đơn vị |
| **I** | Ánh xạ diễn giải: từ chữ trong đề sang thực thể O, V, C. **Lỗi lớn nhất thường nằm ở đây** (đọc sai "nhẵn", "không dãn", "va chạm mềm", "bắt đầu trượt"…) |

### 1.2. Bốn thuộc tính của mỗi công cụ ℓ (tách bạch như README yêu cầu)

| Thuộc tính | Nghĩa | Ví dụ với "bảo toàn cơ năng" |
|---|---|---|
| **Dom(ℓ)** | Miền mà định luật *tồn tại/đúng* (bản chất) | Mọi hệ quán tính, tương tác bảo toàn + lực liên kết không sinh công |
| **Pre(ℓ)** | Điều kiện cần *để dùng tại một CHỖ cụ thể* | Trong khoảng [t₁,t₂] mọi lực không thế **không** sinh công tổng cộng |
| **Suf(ℓ)** | Phép thử **kiểm được bằng tay** cho thấy Pre thỏa; đây chính là "dấu hiệu nhận diện CHỖ" | Liệt kê hết lực; lực nào không thế thì chứng minh công bằng 0 (vuông góc dịch chuyển, hoặc ràng buộc tĩnh…) |
| **Post(ℓ)** | Phương trình/ràng buộc mới sinh ra | E₁ = E₂ (một phương trình vô hướng) |
| **Err(ℓ)** | Sai số / mức xấp xỉ nếu Pre chỉ thỏa gần đúng | Bỏ ma sát nhỏ: sai số ~ công ma sát / cơ năng |

**Dom ≠ Pre.** Ví dụ: định luật bảo toàn động lượng có Dom rất rộng (mọi hệ cô lập), nhưng Pre tại một CHỖ cụ thể có thể hẹp (chỉ theo phương ngang, chỉ trong khoảng va chạm). Ngược lại, công thức x = x₀+v₀t+½at² có Dom hẹp (a = hằng số) nhưng Pre tại một CHỖ chỉ là "a không đổi *trên đoạn này*".

### 1.3. "CHỖ" có kiểu: bộ ba (Σ, τ, e)

**Ý tưởng cốt lõi [H].** Trong cơ chất điểm, mọi công cụ đều tác dụng lên một *bộ ba*:

> **CHỖ = (Σ, τ, e)**
> - **Σ** = *hệ được chọn* (một tập chất điểm/vật + lò xo/dây thuộc hay không thuộc hệ)
> - **τ** = *thời điểm hoặc khoảng thời gian/quá trình* (một trạng thái, hay cặp trạng thái đầu–cuối)
> - **e** = *hướng / trục / điểm quy chiếu* (thành phần theo trục nào; momen quanh điểm nào)

Vì Σ, τ, e mỗi cái đều lấy từ một danh sách **hữu hạn và nhỏ** (mục 1.4), số ứng viên (ℓ, CHỖ) hữu hạn và duyệt được. Đó là "duyệt từng pixel" cụ thể hóa cho cơ học. Mỗi công cụ có **kiểu CHỖ** riêng:

| Kiểu | Công cụ điển hình | Cái phải chọn |
|---|---|---|
| **(1 vật, 1 thời điểm, 1 hướng)** | Newton 2 (D1), lực hướng tâm | Vật nào, lúc nào, chiếu lên trục nào |
| **(hệ, khoảng thời gian, 1 hướng)** | Bảo toàn động lượng (C1), xung lượng | Hệ nào, trong khoảng nào, phương nào |
| **(hệ, trạng thái đầu, trạng thái cuối)** | Công–động năng (C3), cơ năng (C4) | Hệ nào, hai trạng thái nào |
| **(hệ, điểm O, khoảng thời gian)** | Momen xung lượng (C7) | O là điểm nào (thường chọn O để **triệt lực chưa biết**) |
| **(điểm/đoạn quỹ đạo)** | Bán kính cong, tọa độ tự nhiên (K5, D6) | Điểm nào trên quỹ đạo |
| **(cặp đối tượng liên kết)** | Ràng buộc động học (K7): dây, tiếp xúc | Sợi dây/điểm tiếp xúc nào |
| **(phương trình chuyển động, vị trí cân bằng)** | Dao động (O1–O8) | Cân bằng nào, tọa độ lệch nào |

### 1.4. Ba danh sách "đặc biệt" để sinh ứng viên CHỖ

**(a) Thời điểm/trạng thái đặc biệt τ** (mỗi cái là ứng viên cho "trạng thái đầu/cuối" hoặc điểm chia giai đoạn)

| # | Trạng thái | Điều kiện toán học sinh ra |
|---|---|---|
| τ1 | Đầu và cuối quá trình | Điều kiện đầu, điều kiện cuối |
| τ2 | Vật dừng tức thời (điểm biên, quay đầu) | v = 0 |
| τ3 | Tốc độ cực trị | dv/dt = 0, tức thành phần **tiếp tuyến** của lực = 0 |
| τ4 | Rời mặt / bắt đầu mất tiếp xúc | N = 0 |
| τ5 | Dây bắt đầu chùng / bắt đầu căng | T = 0 (chùng), hoặc dây thẳng và đủ dài (căng) |
| τ6 | Bắt đầu trượt / dừng trượt | f = μ_s N (sắp trượt); v_rel = 0 (dừng trượt) |
| τ7 | Ngay trước / ngay sau va chạm | Chuyển sang C6; chia giai đoạn |
| τ8 | Lò xo ở độ dài tự nhiên; lò xo dãn/nén cực đại | x = 0; v = 0 |
| τ9 | Hai vật gặp nhau / cách nhau nhỏ nhất | r_A = r_B; **v_rel ⟂ r_rel** |
| τ10 | Đỉnh quỹ đạo / điểm cận–viễn | v_y = 0; **v ⟂ r** |
| τ11 | Vị trí cân bằng / điểm lệch cực đại | F = 0 (∂U/∂q = 0); v = 0 |
| τ12 | Điểm có ràng buộc đổi dạng (dây bắt đầu quấn/thoát vật cản, vật chạm sàn) | Chia giai đoạn (P9) |

**(b) Hệ đặc biệt Σ**

| # | Hệ | Vì sao hữu ích |
|---|---|---|
| Σ1 | Từng vật riêng lẻ | Newton, lực hướng tâm |
| Σ2 | Cả hệ vật nối dây/lò xo (cùng ròng rọc nhẹ) | Triệt sức căng, lực nội |
| Σ3 | Hệ **gồm** lò xo (thế năng đàn hồi thuộc hệ) hoặc **không gồm** (lò xo là ngoại lực) | Chọn cách nào tiện hơn; **không đếm hai lần** |
| Σ4 | Hệ + Trái Đất (thế năng trọng trường thuộc hệ) hoặc lực trọng trường là ngoại lực | Tương tự Σ3 |
| Σ5 | Nêm + vật trên nêm | Triệt phản lực tương tác giữa chúng |
| Σ6 | Hai vật tương tác → chuyển sang chuyển động của **khối tâm** và chuyển động **tương đối** (khối lượng rút gọn) | Bài hai vật (P7) |
| Σ7 | Phần khối lượng "vào/ra" khi khối lượng biến thiên | D8 |

**(c) Hướng/trục/điểm đặc biệt e**

| # | Hướng / điểm | Khi nào |
|---|---|---|
| e1 | Ngang / thẳng đứng | Trọng lực, sàn nhẵn |
| e2 | Dọc dây; dọc mặt nghiêng; vuông góc mặt | Ràng buộc |
| e3 | Tiếp tuyến / pháp tuyến quỹ đạo (t, n) | Chuyển động cong, đổi tốc độ |
| e4 | Hướng tâm / phương vuông góc (r, φ) | Lực xuyên tâm |
| e5 | Đường nối tâm / mặt tiếp tuyến tại điểm va chạm (n, t) | Va chạm |
| e6 | Trục đối xứng của bài | Nơi có bảo toàn (định lý Noether) |
| e7 | Điểm O trên đường tác dụng của lực chưa biết | Chọn O cho momen xung lượng |

### 1.5. Tiêu chí "có ý nghĩa" của một bước (chặt hóa điều kiện (2) trong README)

README nói *Post(ℓ) tạo ra một ràng buộc mới có ý nghĩa*. Tôi đề xuất định nghĩa kiểm được **[H]**:

> Một bước (ℓ, CHỖ) là **có ý nghĩa** nếu phương trình Post của nó
> 1. **độc lập** với các phương trình đã có (không phải tổ hợp tuyến tính/hệ quả của chúng), và
> 2. **hoặc** liên kết ít nhất một ẩn với dữ kiện đã biết, **hoặc** loại được ít nhất một ẩn chưa cần tìm (lực liên kết, thời gian…).

Bước có ý nghĩa nhất là bước **loại được ẩn phiền** mà **không thêm ẩn mới**. Điều này dẫn tới nguyên lý chọn công cụ quan trọng nhất của tài liệu:

### 1.6. Nguyên lý khử ẩn: mỗi định luật bảo toàn là một "máy khử ẩn" **[H]**

Đừng hỏi *"bài này dùng định luật nào?"*. Hãy hỏi *"ẩn nào đang cản mình, và định luật nào khử được nó?"*

| Ẩn phiền | Công cụ khử | Vì sao khử được | Điều kiện (Pre chính) |
|---|---|---|---|
| Nội lực giữa các vật trong hệ | Động lượng (C1), khối tâm (C2) | Nội lực đối nhau, tổng bằng 0 (N3) | Chọn hệ chứa **cả hai** vật tương tác |
| Phản lực pháp tuyến của ràng buộc *tĩnh* | Cơ năng (C4), công (C3) | N ⟂ **v** nên không sinh công | Ràng buộc **không phụ thuộc thời gian**, nhẵn |
| Sức căng dây không dãn | Cơ năng của **cả hệ** (Σ2); ràng buộc hình học | Công tổng của hai đầu dây = 0 | Dây nhẹ, không dãn, không chùng |
| Lực liên kết đi qua điểm O | Momen xung lượng quanh O (C7) | Momen của lực đó quanh O bằng 0 | O nằm trên đường tác dụng của lực |
| Lực xung tại điểm tiếp xúc/dây căng đột ngột | Động lượng/momen xung lượng theo phương/điểm **không có xung ngoại lực** | Xung ngoại lực theo phương đó bằng 0 | Chọn (e, O) đúng (C1, C6) |
| Thời gian t | Công–động năng, cơ năng; hoặc đổi biến v dv = a dx | Phương trình liên hệ trực tiếp v và x | a chỉ phụ thuộc x (K2) |
| Thời gian t **và** vị trí trung gian | Bảo toàn giữa hai trạng thái đầu–cuối | Không cần biết quá trình | Pre của C4 |
| Lực cần biết ở **một thời điểm** | Newton (D1) tại τ đó | Không có công cụ bảo toàn nào cho "lực tức thời" | — |
| Nhiều lực chưa biết trong **cân bằng** | Nguyên lý công ảo (D10) | Phản lực lý tưởng không sinh công ảo | Liên kết lý tưởng |

### 1.7. Kiểm kê ẩn–phương trình (điều kiện Completeness/Closure của README)

Sau mỗi bước ghi hai cột **[H]**:

- **Ẩn:** các thành phần gia tốc/vận tốc/tọa độ chưa biết + mọi lực liên kết chưa biết + các thời điểm chưa biết.
- **Phương trình độc lập:** phương trình động lực (Newton/bảo toàn) + phương trình ràng buộc + điều kiện đầu.

**Đóng kín** khi số phương trình độc lập ≥ số ẩn *và* hệ không suy biến. Một số đếm nhanh thường gặp:

| Tình huống | Ẩn | Phương trình |
|---|---|---|
| Chất điểm, chuyển động phẳng, lực đã biết | a_x, a_y | 2 (Newton) |
| + mỗi dây không dãn / mặt tiếp xúc chưa biết lực | +1 ẩn (T hoặc N) | +1 phương trình ràng buộc hình học |
| + ma sát trượt (mỗi mặt) | +1 ẩn (f) | +1 (f = μN) |
| + ma sát nghỉ (không trượt) | +1 ẩn (f) | +1 ràng buộc (a_rel = 0) |
| Bài va chạm 2 vật 1D | 2 vận tốc sau | 2 (động lượng + hệ số hồi phục e) |
| Bài va chạm 2 vật 2D không ma sát | 4 thành phần sau | 4 (2 thành phần theo t bảo toàn cho từng vật + động lượng theo n + e) |

**Thiếu phương trình?** Quay lại 1.4: còn CHỖ (Σ, τ, e) nào chưa duyệt? **Thừa?** Đó là kiểm tra chéo miễn phí (nếu không nhất quán thì có lỗi mô hình).

### 1.8. Giao thức tổng (thuật toán cho Vấn đề 1 → Vấn đề 2)

```
BƯỚC 0  Đọc đề → viết M = (O,V,L,C,Q,I). Gạch chân từng ràng buộc lý tưởng hóa
        (nhẵn, không dãn, nhẹ, va chạm mềm/đàn hồi…). Ghi Err nếu có xấp xỉ.
BƯỚC 1  Tiền xử lý (Phần 2): chọn hệ quy chiếu, hệ tọa độ, chia giai đoạn theo
        sự kiện, chọn chế độ (dính/trượt, căng/chùng…), không thứ nguyên hóa nếu cần.
BƯỚC 2  Xác định Q → tra bảng "Q → công cụ" (7.1) và bảng "ẩn phiền → công cụ khử" (1.6).
BƯỚC 3  SINH ỨNG VIÊN: với mỗi giai đoạn, liệt kê các CHỖ (Σ, τ, e) (1.4).
        Với mỗi công cụ ℓ ứng viên, chạy phép thử Suf(ℓ) tại từng CHỖ.
        (Đây là bước "brute-force có kiểm soát": ghi ra hết, rồi lọc.)
BƯỚC 4  LỌC: giữ bước "có ý nghĩa" (1.5). Ưu tiên bước khử ẩn mà không thêm ẩn.
BƯỚC 5  CHUYỂN SANG TOÁN (Vấn đề 2): viết Post của từng bước đã chọn theo
        "Chuyển sang Toán" của công cụ đó. Kiểm kê ẩn–phương trình (1.7).
BƯỚC 6  Kiểm tra 7 điều kiện (7.5): thứ nguyên, giới hạn, đối xứng, biên, nhất quán.
        Nếu chưa đóng kín hoặc mâu thuẫn → quay lại BƯỚC 0 (nghi ngờ diễn giải I) hoặc BƯỚC 3.
BƯỚC 7  Xác định "bài toán đích" (7.2) để chuyển cho Vấn đề 3.
```

**Lưu ý trung thực:** BƯỚC 0 (diễn giải) và BƯỚC 1 (chọn hệ quy chiếu/hệ) vẫn cần phán đoán. Tôi cố gắng biến phán đoán đó thành *danh sách kiểm tra* (Phần 2), nhưng không thể chứng minh danh sách là đầy đủ.

---

## PHẦN 2. TIỀN XỬ LÝ (PRE-PROCESSING): ĐƯA BÀI VỀ DẠNG ÁP DỤNG ĐƯỢC CÔNG CỤ

Mỗi toán tử P dưới đây có Pre riêng. Chúng chạy **trước** khi chọn K/D/C/O. Quy ước mỗi thẻ: *Việc làm · Pre · Post · Err/Bẫy*.

### P1. Chọn hệ quy chiếu **[C]**
- **Việc làm:** Xác định hệ quán tính nào có thể dùng (thường: mặt đất; hệ khối tâm; hệ gắn với vật chuyển động đều).
- **Pre:** Hệ đứng yên hoặc chuyển động thẳng đều so với hệ quán tính đã biết; v ≪ c.
- **Post:** Newton 2 viết được ở dạng ΣF = ma **không** thêm lực quán tính.
- **Bẫy:** "Mặt đất là quán tính" chỉ xấp xỉ (bỏ tự quay và công quay quanh Mặt Trời): sai số tương đối cỡ ω²R/g ≈ 3·10⁻³ với ly tâm, và hiệu ứng Coriolis khi chuyển động dài/nhanh. Chỉ cần nêu khi đề đặt câu hỏi về Trái Đất quay.

### P2. Đổi hệ quy chiếu Galileo (tịnh tiến thẳng đều) **[C]**
- **Việc làm:** Sang hệ chuyển động với **u** không đổi: **v**' = **v** − **u**, **r**' = **r** − **u**t; gia tốc, lực, khối lượng giữ nguyên.
- **Pre:** **u** = hằng số (nếu **u** đổi → hệ phi quán tính, sang P4/D9).
- **Post:** Có thể biến bài toán phức tạp thành đơn giản: vật đứng yên, hoặc va chạm với vật nặng vô hạn (tường chuyển động) thành va chạm với tường đứng yên.
- **Bẫy:** **Động năng và công không bất biến** khi đổi hệ. **Định lý công–động năng và bảo toàn năng lượng đúng trong mọi hệ quán tính**, nhưng từng con số ΔK khác nhau giữa các hệ. Đừng trộn số liệu của hai hệ.
- **Mẫu dùng:** Phản xạ từ tường/nêm chuyển động với vận tốc **u**: sang hệ tường, phản xạ đàn hồi đổi dấu thành phần pháp tuyến, rồi chuyển ngược: v'_n = −v_n + 2u_n. **[C]**

### P3. Hệ khối tâm (CM) **[C]**
- **Việc làm:** Đặt **R**_cm = Σmᵢ**r**ᵢ/M, sang hệ chuyển động theo khối tâm (quán tính nếu ΣF_ext = 0, nếu không thì phi quán tính với gia tốc **a**_cm).
- **Pre:** ΣF_ext = 0 (khi đó hệ khối tâm là hệ quán tính). Nếu ΣF_ext ≠ 0, hệ khối tâm là phi quán tính với gia tốc **a**_cm: thêm lực quán tính −mᵢ**a**_cm lên mỗi vật (tổng ngoại lực và quán tính lên hệ bằng 0, nên khối tâm đứng yên trong hệ đó).
- **Post:** Tổng động lượng = 0; động năng K = ½M v_cm² + K' (định lý König, xem C3).
- **Mẫu dùng:** Va chạm (cực kỳ hữu ích: đàn hồi = quay vector vận tốc tương đối, độ lớn giữ nguyên), nổ, phân rã, hai vật quay quanh nhau.

### P4. Chọn hệ phi quán tính *có chủ đích* **[C]**
- **Việc làm:** Khi hệ chuyển động có gia tốc **a**₀ không đổi so với hệ quán tính, ta có thể *coi* mọi vật chịu thêm trường −m**a**₀ và dùng g hiệu dụng: **g**_eff = **g** − **a**₀.
- **Pre:** **a**₀ đã biết; nếu hệ quay thì thêm ly tâm, Coriolis (D10).
- **Post:** Bài toán tĩnh/dao động trong hệ đó dùng g_eff; thế năng trong hệ đó U = −m**g**_eff·**r**.
- **Bẫy:** Lực quán tính **không có phản lực** (N3 không áp dụng cho nó). Tính động lượng/năng lượng của hệ thì phải nhất quán *một* hệ, trong hệ phi quán tính **không** dùng "động lượng tổng bảo toàn" như thường lệ mà không xét lực quán tính.
- **Mẫu dùng:** Con lắc trong xe/thang máy: T = 2π√(l/g_eff); mặt phẳng nghiêng đặt trên xe.

### P5. Chọn hệ tọa độ **[C]**
| Hệ | Khi nào chọn | Biểu thức chính |
|---|---|---|
| Descartes (x,y) | Gia tốc/lực hằng số, mặt phẳng phẳng, va chạm với tường thẳng | v = (ẋ,ẏ), a = (ẍ,ÿ) |
| Cực (r,φ) | Lực xuyên tâm, dây/thanh quay quanh điểm, chuyển động xoắn | **v** = ṙ**e**_r + rφ̇**e**_φ; **a** = (r̈ − rφ̇²)**e**_r + (rφ̈ + 2ṙφ̇)**e**_φ |
| Tự nhiên (t,n) | Vật trên quỹ đạo cho trước; cần lực hướng tâm | **a** = s̈**t** + (ṡ²/ρ)**n**; ρ bán kính cong |
| Dọc–vuông góc với mặt nghiêng | Vật trượt trên mặt nghiêng; ném lên/xuống nghiêng | g phân thành g sinα (dọc), g cosα (vuông góc) |
| Cầu/trụ (r,θ,φ) | Ít gặp trong chất điểm phẳng; chuyển động 3D có trục đối xứng | Tham khảo tài liệu Toán |
- **Quy tắc chọn [H]:** Chọn hệ sao cho (i) ràng buộc trở thành một tọa độ hằng số (ví dụ r = R trên vòng), (ii) các lực chưa biết vuông góc với trục ta cần, (iii) lực đã biết có thành phần đơn giản.
- **Bẫy:** Trong tọa độ cực, **e**_r, **e**_φ **đổi hướng theo thời gian**; không được đạo hàm nhầm coi chúng là hằng.

### P6. Chọn/gộp/tách hệ Σ **[H]**
- **Việc làm:** Dùng 1.4(b) liệt kê ứng viên Σ. Chọn Σ theo bảng khử ẩn 1.6.
- **Pre:** Với Σ nhiều vật: mọi vật trong Σ dùng **cùng hệ quy chiếu**; mọi lực phải được xếp đúng vào *nội* hoặc *ngoại* (một lực không đếm cả hai lần).
- **Bẫy điển hình:** (i) Đưa lò xo vào hệ *và* vẫn ghi lực đàn hồi như ngoại lực; (ii) đưa Trái Đất vào hệ *và* vẫn ghi công của trọng lực; (iii) quên rằng khi hệ gồm nêm + vật, ràng buộc *phụ thuộc thời gian* (nêm di động) làm N của từng vật có thể sinh công dù tổng công của cặp (N, N') vẫn bằng 0.

### P7. Bài hai vật → khối tâm + chuyển động tương đối **[C]**
- **Việc làm:** Đặt **R** = (m₁**r**₁ + m₂**r**₂)/M, **r** = **r**₁ − **r**₂; khối lượng rút gọn μ = m₁m₂/(m₁+m₂).
- **Pre:** Chỉ hai vật; lực tương tác chỉ phụ thuộc **r** và hướng theo **r** (hoặc bất kỳ nội lực nào, cho phần khối tâm).
- **Post:** M**R̈** = ΣF_ext; μ**r̈** = **F**₁₂(**r**) (bài một vật với khối lượng μ). Động năng K = ½M V_cm² + ½μ v_rel².
- **Mẫu dùng:** Kepler với khối lượng hữu hạn, dao động hai vật nối bằng lò xo (ω² = k/μ), va chạm.

### P8. Lý tưởng hóa: bảng hệ quả và sai số **[C]**
| Giả thiết đề cho | Hệ quả (Post) | Err / chỗ hết đúng |
|---|---|---|
| Dây nhẹ, không dãn | (i) sức căng **đều** dọc dây (nếu không ma sát với vật khác); (ii) độ dài không đổi → ràng buộc động học; (iii) chỉ kéo, không đẩy (T ≥ 0) | Dây nặng: T thay đổi dọc dây (viết Newton cho từng đoạn nhỏ, xem D2); va chạm/nảy căng đột ngột sinh **xung** (C6) |
| Ròng rọc nhẹ, không ma sát | Sức căng hai phía bằng nhau | Ròng rọc có khối lượng: mô men quán tính (ngoài phạm vi) |
| Mặt nhẵn | Chỉ có N ⟂ mặt, f = 0 | Ma sát nhỏ: Err ~ μ |
| Lò xo nhẹ, tuân theo Hooke | F = k·Δl dọc lò xo; lực hai đầu bằng nhau | Lò xo có khối lượng m_s: khối lượng hiệu dụng ≈ m + m_s/3 (O3) |
| Vật coi là chất điểm | Bỏ kích thước, bỏ quay | Nêu điều kiện: kích thước ≪ độ dài khác; xem "va chạm lệch tâm" ngoài phạm vi |
| Va chạm tức thời | Bỏ lực hữu hạn (trọng lực, ma sát hữu hạn, lực đàn hồi) trong Δt; giữ **xung** | Nếu Δt không đủ nhỏ, sai số ~ F_hữu hạn·Δt/(xung va chạm) |
| Sức cản không khí bỏ qua | g = hằng số, chuyển động parabol | Khi v lớn hoặc vật nhẹ: xem D5 |
| Trái Đất quán tính, g hằng | Newton chuẩn | Độ cao ~R: dùng GMm/r² |
| Bỏ ma sát hai chiều giữa nhiều vật | Bảo toàn cơ năng khả thi (nếu không va chạm mềm) | Cần kiểm tra Pre của C4 |

### P9. Chia giai đoạn theo sự kiện **[H]**
- **Việc làm:** Quét toàn bộ bài theo trục thời gian, đánh dấu mọi **sự kiện** trong 1.4(a): τ2, τ4, τ5, τ6, τ7, τ8, τ12. Mỗi khoảng giữa hai sự kiện liên tiếp là một **giai đoạn** với bộ Pre riêng.
- **Post:** Trong mỗi giai đoạn, dùng đúng công cụ hợp lệ; tại sự kiện, dùng điều kiện nối (liên tục vị trí; vận tốc liên tục hoặc nhảy theo C6).
- **Bảng "giai đoạn → công cụ hợp lệ":**

| Giai đoạn | Công cụ thường dùng | Công cụ **cấm** |
|---|---|---|
| Chuyển động tự do dưới lực bảo toàn | C4 (cơ năng), D1 | — |
| Va chạm/xung tức thời | C1, C7 (theo phương/điểm không có xung ngoại lực), C6 | C4 **cho hệ có va chạm không đàn hồi**; D1 với lực hữu hạn |
| Trượt có ma sát | C3 (công của ma sát), D1, D3 | C4 chưa tính công ma sát |
| Dây căng đột ngột | C1/C7 theo phương không có xung ngoại | C4 (mất năng lượng khi dây căng đột ngột và vật mất thành phần vận tốc dọc dây) |
| Vật rời mặt / bắt đầu bay | K3 | D1 với N (đã bằng 0) |

- **Bẫy:** Quên một sự kiện (ví dụ dây chùng giữa chừng) làm sai cả lời giải. **Duyệt danh sách τ1–τ12 từng dòng.**

### P10. Chọn chế độ, giả sử rồi kiểm tra ("assume–verify") **[C]**
Nhiều bài có nhánh do các **bất đẳng thức** (ma sát nghỉ ≤ μN, T ≥ 0, N ≥ 0). Thuật toán cố định:
1. Liệt kê mọi biến rời rạc: (ma sát mỗi mặt: dính / trượt lên / trượt xuống), (mỗi dây: căng / chùng), (mỗi tiếp xúc: giữ / rời).
2. Chọn một tổ hợp chế độ; giải hệ phương trình tương ứng.
3. **Kiểm tra bất đẳng thức của chế độ đã giả sử** (f ≤ μ_sN nếu dính; T ≥ 0 nếu căng; N ≥ 0 nếu tiếp xúc; v_rel có hướng phù hợp nếu trượt).
4. Nếu vi phạm → đổi tổ hợp, lặp lại. Số tổ hợp hữu hạn, thường ≤ 4.
5. Tập mọi tổ hợp thỏa = nghiệm hợp lệ. Nếu có 2 tổ hợp cùng thỏa → bài chưa xác định (thiếu dữ kiện) hoặc phải xét lịch sử/điều kiện đầu.
- **Post:** Đáp án kèm **điều kiện tồn tại** (ví dụ "chỉ trượt nếu tanα > μ_s").

### P11. Phân tích thứ nguyên và không thứ nguyên hóa **[C]**
- **Việc làm:** Đặt t = τ₀ t̃, x = L x̃ với τ₀, L chọn từ tham số của bài (ví dụ τ₀ = √(m/k), L = A hoặc l).
- **Post:** Phương trình còn ít tham số; tham số không thứ nguyên chính (như γ/ω₀, μ, m/M, gl/v²) cho biết bài thuộc chế độ nào.
- **Pre:** Không cần gì đặc biệt; luôn làm được.
- **Dùng để:** kiểm tra kết quả (thứ nguyên khớp), nhận biết giới hạn, phát hiện tham số quyết định "dạng nghiệm" (ví dụ γ/ω₀ < 1).

### P12. Khai triển và tuyến tính hóa quanh trạng thái tham chiếu **[C]**
- **Việc làm:** Khi biến thiên nhỏ quanh cân bằng: f(q₀+δ) ≈ f(q₀) + f'(q₀)δ + ½f''(q₀)δ² + … Giữ bậc thấp nhất **không triệt tiêu**.
- **Pre:** δ ≪ tỷ số các đại lượng thứ nguyên (góc nhỏ: θ ≪ 1 rad; biên độ ≪ chiều dài).
- **Post:** sinθ ≈ θ, cosθ ≈ 1 − θ²/2, (1+ε)ⁿ ≈ 1 + nε, √(1+ε) ≈ 1 + ε/2; phương trình vi phân phi tuyến → tuyến tính.
- **Err:** Bậc tiếp theo. Với con lắc đơn: sai số tương đối của chu kỳ ≈ θ₀²/16 (O3).
- **Bẫy:** Giữ đúng bậc: phép trừ hai đại lượng gần bằng nhau có thể làm số hạng bậc cao quan trọng. Với thế năng, cần khai triển **đến bậc 2** mới có ω (ω² = U''(q₀)/m).

### P13. Đổi biến độc lập/biến phụ **[C]**
| Từ | Sang | Khi nào | Kết quả |
|---|---|---|---|
| t → x | v dv/dx = a(x) | a phụ thuộc vị trí (lò xo, hấp dẫn) | ½v² = ∫a dx + C (chính là năng lượng) |
| t → v | dv/a(v) = dt; v dv/a(v) = dx | a phụ thuộc vận tốc (sức cản) | Tích phân tách biến |
| t → θ (chuyển động cực) | d/dt = φ̇ d/dφ với φ̇ = L/(mr²) | Lực xuyên tâm | Phương trình quỹ đạo (Binet, C7) |
| r → u = 1/r | u'' + u = −mF(1/u)/(L²u²) | Lực xuyên tâm | Kepler: u'' + u = mk/L² |
| (x,y) → (s, θ) trên đường cong | tọa độ tự nhiên | Vật bị ràng buộc trên đường | Bài một bậc tự do |
| Đặt x' = x − x_eq | Dời gốc về vị trí cân bằng thật | Dao động chịu lực hằng số | Loại số hạng hằng số |

---

## PHẦN 3. ĐỘNG HỌC (a) — K1 đến K8

Mỗi thẻ có: **Kiểu CHỖ · Nội dung · Pre · Suf (dấu hiệu) · Post · Trình tự cố định (V1) · Chuyển sang Toán (V2) · Bẫy · Nâng cao.**

---

### K1. Chuyển động thẳng đều / biến đổi đều (gia tốc hằng, một trục) **[C]**

- **Kiểu CHỖ:** (1 vật, 1 khoảng thời gian hoặc 2 trạng thái, 1 trục).
- **Nội dung:**
  - v = v₀ + at
  - x = x₀ + v₀t + ½at²
  - v² − v₀² = 2a(x − x₀)
  - x − x₀ = ½(v₀ + v)t
  - Đều: a = 0, x = x₀ + vt.
- **Dom:** Mọi chuyển động thẳng có gia tốc hằng.
- **Pre (tại CHỖ):** a **không đổi theo trục** suốt đoạn đang xét (không có sự kiện τ nào làm đổi lực trong đoạn).
- **Suf:** Dùng D1 chiếu lên trục: nếu *mọi* lực thành phần theo trục là hằng số trong đoạn → Pre thỏa. Nếu có lực thay đổi (lò xo, cản, ma sát đổi chiều) → **không** áp dụng, sang K2.
- **Post:** 5 biến (Δx, v₀, v, a, t), **chỉ 2 phương trình độc lập**. Cần biết 3 biến để tìm 2 biến còn lại.
- **Trình tự cố định (V1 "tìm chọn công thức"):**
  1. Chọn chiều dương của trục, ghi dấu cho v₀, a, Δx.
  2. Ghi 5 biến; đánh dấu *biết* (3), *cần tìm* (1–2), *không quan tâm* (1).
  3. Chọn công thức **không chứa** biến "không quan tâm":

| Biến vắng | Công thức |
|---|---|
| Δx | v = v₀ + at |
| v | Δx = v₀t + ½at² |
| t | v² = v₀² + 2aΔx |
| a | Δx = ½(v₀ + v)t |
| v₀ | Δx = vt − ½at² |

- **Chuyển sang Toán (V2):** Đại số bậc nhất/bậc hai. Bài nhiều giai đoạn: nối bằng *v liên tục và x liên tục* tại sự kiện.
- **Bẫy:**
  - Quãng đường ≠ độ dời khi vật đổi chiều: quãng đường = ∫|v|dt; **chia tại τ2 (v = 0)** rồi cộng.
  - "Chậm dần đều" nghĩa là **a ngược chiều v**, không phải "a < 0" (phụ thuộc trục).
  - "Giây thứ n": Δx trong [n−1, n] = v₀ + a(n − ½) (không phải v₀ + an).
  - Từ trạng thái nghỉ, quãng đường các khoảng thời gian liên tiếp bằng nhau tỉ lệ 1 : 3 : 5 : …
- **Nâng cao:** Bài "gặp nhau": x_A(t) = x_B(t) là phương trình bậc hai theo t. **Tồn tại gặp nhau ⇔ Δ ≥ 0** *và* nghiệm t > 0 nằm trong khoảng hợp lệ. Có thể có hai lần gặp.
- **Đồ thị:** Độ dốc của x–t là v; độ dốc của v–t là a; **diện tích dưới v–t** là độ dời; diện tích dưới a–t là Δv. Bài đồ thị thường giải nhanh hơn bằng hình học.

---

### K2. Chuyển động một chiều với gia tốc **không hằng** **[C]**

- **Kiểu CHỖ:** (1 vật, khoảng thời gian, 1 trục) với tính chất "a phụ thuộc đúng một biến".
- **Nội dung (ba trường hợp):**

| a phụ thuộc | Phương trình | Kết quả |
|---|---|---|
| t | dv = a(t)dt; dx = v dt | v = v₀ + ∫a dt; x = x₀ + ∫v dt |
| **x** | **v dv = a(x) dx** | ½v² − ½v₀² = ∫a dx (đây chính là **năng lượng**), rồi t = ∫dx/v |
| **v** | dv/a(v) = dt; v dv/a(v) = dx | t = ∫dv/a(v); x = ∫v dv/a(v) |

- **Pre:** Chuyển động một chiều (hoặc đã tách thành phần); a là hàm **một** biến (nếu a(x, v) → không tách được, sang O5 hoặc số).
- **Suf (nhìn vào lực):** Ngoại lực theo thời gian (kéo theo lịch trình) → a(t). Lò xo, hấp dẫn, lực thế → a(x). Lực cản → a(v).
- **Trình tự cố định (V1):** (1) Viết a = F/m theo D1; (2) xem F phụ thuộc biến nào; (3) chọn dạng tách biến tương ứng; (4) nếu Q **không cần t** mà a(x) → dùng ½v² (nhanh nhất).
- **Chuyển sang Toán (V2):** Tích phân tách biến, thêm hằng số theo điều kiện đầu.
- **Mẫu dùng (đã kiểm):**
  - Cản tuyến tính (F = −bv): v = v₀e^{−bt/m}; quãng đường dừng hữu hạn **x = mv₀/b**.
  - Cản bậc hai (F = −cv²): 1/v = 1/v₀ + ct/m; x = (m/c)·ln(1 + cv₀t/m) (**không giới hạn**); v(x) = v₀e^{−cx/m}.
- **Bẫy:** Quên hằng số tích phân; chia cho v khi v = 0 (mất nghiệm đứng yên); dấu của lực cản (luôn ngược v, dùng sgn(v)).

---

### K3. Rơi tự do và chuyển động ném (gia tốc g hằng, hai trục) **[C]**

- **Kiểu CHỖ:** (1 vật, khoảng thời gian sau khi rời tay/bắn, 2 trục vuông góc).
- **Nội dung:**
  - x = x₀ + v₀cosθ·t; y = y₀ + v₀sinθ·t − ½gt².
  - Quỹ đạo: y = x tanθ − (g x²/(2v₀²))(1 + tan²θ).
  - Đỉnh: t = v₀sinθ/g; H = v₀²sin²θ/(2g). Tầm xa cùng độ cao: R = v₀²sin2θ/g.
  - **Parabol an toàn (bao hình):** y = v₀²/(2g) − g x²/(2v₀²).
  - **Tốc độ tối thiểu để trúng điểm (x, y):** v₀² = g(y + √(x² + y²)); khi đó tanθ = v₀²/(gx).
  - **Ném lên mặt nghiêng góc β** (θ đo từ phương ngang): R = 2v₀²cosθ sin(θ−β)/(g cos²β); cực đại tại θ = π/4 + β/2, **R_max = v₀²/(g(1 + sinβ))**. Xuống dốc: β → −β, R_max = v₀²/(g(1 − sinβ)).
- **Pre:** (i) Sau khi rời tay chỉ còn trọng lực; (ii) g hằng (độ cao ≪ R_Trái Đất); (iii) hệ quy chiếu quán tính, hoặc dùng g_eff; (iv) vật coi là chất điểm.
- **Suf:** Nhận ra "sau thời điểm bắn, không còn tương tác" hay "vật rơi, chỉ chịu trọng lực".
- **Trình tự cố định (V1):**
  1. Chọn trục (P5): ngang–đứng, hoặc **dọc–vuông góc mặt nghiêng** khi có mặt nghiêng.
  2. Viết x(t), y(t).
  3. Liệt kê **điều kiện CHỖ** (từ 1.4a): đích (x*, y*); đỉnh (v_y = 0); chạm mặt (y = f(x)); trạng thái đặc biệt (v ⟂ mặt…).
  4. Mỗi điều kiện cho một phương trình; khử t (từ phương trình theo x) hoặc khử góc (dùng 1 + tan²θ).
  5. Đếm ẩn–phương trình (1.7).
- **Chuyển sang Toán (V2):**
  - Ẩn là góc → phương trình bậc hai theo **u = tanθ**: (gx²/(2v₀²))u² − xu + (y + gx²/(2v₀²)) = 0.
  - Có nghiệm ⇔ Δ ≥ 0 (đây chính là điều kiện tồn tại nghiệm và cho đường bao).
  - Hai nghiệm u ↔ hai quỹ đạo (nếu cùng độ cao thì góc bù nhau).
- **Kỹ thuật mạnh:**
  - **Mặt nghiêng:** dùng tọa độ dọc nghiêng, g phân thành (g sinβ dọc, g cosβ vuông góc). Thời gian bay của vật ném lên nghiêng: t = 2v_⊥/(g cosβ), với v_⊥ là thành phần vận tốc vuông góc mặt.
  - **Hệ rơi tự do (P4):** hai vật chỉ chịu trọng lực thì trong hệ gắn với một vật, vật kia chuyển động **thẳng đều** với **r**_A − **r**_B = (**v**_A0 − **v**_B0)t. Đây là lý do "khỉ và thợ săn": đạn ngắm thẳng vào khỉ trúng khỉ khi khỉ buông rơi.
- **Bẫy:**
  - Mặt nghiêng: nhầm góc ném đối với phương ngang hay mặt nghiêng.
  - Bỏ nghiệm thứ hai của phương trình bậc hai theo tanθ.
  - Dùng công thức tầm xa R = v₀²sin2θ/g khi độ cao đầu và cuối **khác nhau**.
- **Nâng cao [EXT]:** Nảy nhiều lần với hệ số hồi phục e (dãy thời gian/tầm xa là cấp số nhân, xem C6). Có sức cản (D5): không còn parabol.

---

### K4. Chuyển động tròn (đều và biến đổi đều) **[C]**

- **Kiểu CHỖ:** (1 vật, thời điểm/khoảng, hệ (t, n)).
- **Nội dung:**
  - ω = θ̇; v = ωR; T = 2π/ω; f = 1/T.
  - **a_n = v²/R = ω²R** (hướng tâm); **a_t = dv/dt = Rα**; a = √(a_n² + a_t²).
  - Đều: a_t = 0 (**vẫn có a_n**). Biến đổi đều: α = hằng: ω = ω₀ + αt; θ = θ₀ + ω₀t + ½αt²; ω² − ω₀² = 2αΔθ. Số vòng N = Δθ/2π.
- **Pre:** Quỹ đạo tròn bán kính R = hằng (do ràng buộc). Nếu không tròn hoặc R đổi → K5.
- **Suf:** Có dây/thanh/vòng/mặt giữ khoảng cách đến một tâm cố định.
- **Trình tự cố định (V1):** (1) Xác định tâm và R; (2) tách gia tốc thành a_n, a_t; (3) nếu bài yêu cầu lực → D6; (4) nếu bài yêu cầu thời điểm gặp → dùng điều kiện dưới.
- **Chuyển sang Toán (V2):** Gặp nhau trên đường tròn: **θ_A(t) = θ_B(t) + 2πk, k ∈ ℤ** (giữ **họ nghiệm**, không lấy k = 0 vội). Hai vật cùng chiều quay: thời gian giữa hai lần gặp liên tiếp T_gặp = 1/|1/T_A − 1/T_B|. Ngược chiều: 1/T_gặp = 1/T_A + 1/T_B.
- **Bẫy:** Nhầm ω với f (thiếu 2π); quên rằng chuyển động tròn đều **có** gia tốc; áp dụng a_n = v²/R cho quỹ đạo không tròn (phải dùng ρ, K5).
- **Nâng cao [EXT]:** Tâm chuyển động (bánh xe lăn): v = v_tâm + ω × r' (cộng vận tốc, K6). Điểm trên vành bánh lăn không trượt vẽ **xycloid**: x = R(φ − sinφ), y = R(1 − cosφ); tại điểm cao nhất v = 2v_tâm, tại điểm tiếp đất v = 0.

---

### K5. Chuyển động cong tổng quát: thành phần tiếp tuyến–pháp tuyến, tọa độ cực, bán kính cong **[C]**

- **Kiểu CHỖ:** (1 điểm trên quỹ đạo, 1 thời điểm, hệ (t, n) hoặc (r, φ)).
- **Nội dung:**
  - **v** = ṡ**t**; **a** = s̈**t** + (ṡ²/ρ)**n**.
  - **ρ = v²/a_n = v³/|v × a|**. Cho y = y(x): ρ = (1 + y'²)^{3/2}/|y''|.
  - Cực: **v** = ṙ**e**_r + rφ̇**e**_φ; **a** = (r̈ − rφ̇²)**e**_r + (rφ̈ + 2ṙφ̇)**e**_φ.
  - Tốc độ diện tích: dA/dt = ½r²φ̇ (nối với C7).
- **Pre:** Quỹ đạo khả vi hai lần; ρ ≠ 0. Với cực: r ≠ 0.
- **Suf:** Đề hỏi *"bán kính cong"*, *"gia tốc hướng tâm tại điểm"*, *"lực hướng tâm tại điểm"*; hoặc lực và tốc độ tại điểm đã biết mà quỹ đạo chưa biết → suy ρ.
- **Trình tự cố định (V1):** (1) Tại điểm quan tâm, tính **a** (từ D1) và **v**; (2) tách a_n = **a**·**n** = |**a** × **v**|/v; (3) ρ = v²/a_n.
- **Chuyển sang Toán (V2):** Phép chiếu vector; nếu có quỹ đạo tường minh, đạo hàm bậc 1, 2.
- **Mẫu dùng:** Parabol ném xiên: a_n = g cosα_loc (α_loc là góc của **v** với phương ngang tại điểm đó), do đó ρ = v²/(g cosα_loc); **tại đỉnh**: ρ = v_x²/g = v₀²cos²θ/g.
- **Bẫy:** Dùng R hình học thay ρ; quên rằng chỉ **thành phần pháp tuyến** của lực tạo a_n; nhầm dấu khi chiều của **n** hướng về phía lõm.

---

### K6. Vận tốc tương đối, cộng vận tốc, đuổi bắt **[C]**

- **Kiểu CHỖ:** (cặp đối tượng, khoảng thời gian, không gian vector).
- **Nội dung:**
  - **v**_A = **v**_B + **v**_{A/B} (B chuyển động tịnh tiến đối với A); gia tốc tương tự.
  - **Khoảng cách gần nhất** của hai điểm chuyển động thẳng đều: đặt **r**₀ = vị trí tương đối lúc t = 0, **u** = vận tốc tương đối.
    - t* = −(**r**₀·**u**)/u² (nếu t* < 0 thì gần nhất tại t = 0).
    - d_min = |**r**₀ × **u**|/|**u**| (hai chiều: |x₀u_y − y₀u_x|/u).
    - Va chạm nếu d_min ≤ R₁ + R₂ (hai vật cầu bán kính R₁, R₂).
  - **Thuyền qua sông** (vận tốc thuyền so với nước v, dòng u, rộng d): thời gian ngắn nhất d/v (hướng ⟂ bờ). Nếu v < u, **độ trôi nhỏ nhất** khi **v**_{thuyền/nước} ⟂ **v** thực, cosα = −v/u và độ trôi = d√(u² − v²)/v. Nếu v > u, có thể sang thẳng góc (sinα = u/v).
- **Pre:** Hệ B **tịnh tiến** (không quay) so với A; nếu quay, thêm Coriolis (D10).
- **Suf:** Có "dòng", "gió", "tàu chuyển động", "thang máy"; hoặc đề hỏi khoảng cách gần nhất/thời điểm gặp của hai vật chuyển động đều.
- **Trình tự cố định (V1):** (1) Chọn hệ đơn giản nhất (P2), thường là hệ một trong hai vật; (2) tính **u** và **r**₀; (3) áp dụng công thức d_min hoặc điều kiện gặp.
- **Chuyển sang Toán (V2):** Cực tiểu hóa hàm bậc hai |**r**₀ + **u**t|² theo t.
- **Đuổi bắt (pursuit) [EXT]:** Ràng buộc là *hướng*: vận tốc của vật đuổi luôn hướng tới mục tiêu. Tốc độ thay đổi khoảng cách r giữa hai vật: ṙ = −v_đuổi + v_mt·cosφ, với φ là góc giữa **v**_mục tiêu và đường nối (chiều từ vật đuổi ra mục tiêu). Nên viết trong **tọa độ cực gắn với mục tiêu** (hoặc hệ mục tiêu nếu nó chuyển động thẳng đều). Bài này thường cần biến đổi riêng từng trường hợp, tôi không đưa công thức tổng quát.
- **Bẫy:** Đảo dấu vận tốc tương đối; dùng cộng vận tốc khi hệ B quay; quên điều kiện t* > 0.

---

### K7. Tọa độ hóa mở rộng: ràng buộc động học **[C]**, cách đặt tên **[?]**

> **Ghi chú diễn giải [?]:** Cụm "Phương pháp/Thuật toán Tọa độ hóa Mở rộng" trong README tôi hiểu là: *gán tọa độ cho mọi điểm quan trọng, viết mọi ràng buộc thành phương trình tọa độ rồi đạo hàm theo thời gian.* Nếu ý bạn khác, hãy cho tôi biết; phần thuật toán dưới đây vẫn đúng bất kể tên gọi.

- **Kiểu CHỖ:** (cặp/nhóm đối tượng liên kết: dây, thanh cứng, điểm tiếp xúc, đường dẫn).
- **Nội dung / Thuật toán ALG-K7:**
  1. Chọn hệ trục cố định. Đặt tọa độ (x_i, y_i) hoặc tọa độ suy rộng q_i cho **mọi điểm quan trọng**: mỗi vật, đầu dây, tâm ròng rọc, điểm tiếp xúc, đầu thanh.
  2. **Liệt kê MỌI ràng buộc** (duyệt từng đối tượng nối):

| Loại | Phương trình |
|---|---|
| Dây không dãn (căng) | Σ (độ dài các đoạn) = hằng |
| Thanh cứng / khoảng cách cố định | (x_A−x_B)² + (y_A−y_B)² = L² |
| Điểm nằm trên đường/mặt cho trước | f(x, y) = 0 (hoặc y = h(x)) |
| Tiếp xúc giữ (không xuyên, không rời) | khoảng cách đến mặt = 0 (theo P10: N ≥ 0) |
| Lăn không trượt | v_điểm tiếp xúc = 0 ⇒ v_tâm = ωR |

  3. **Bậc tự do:** f = 2N − (số ràng buộc độc lập) (mặt phẳng).
  4. Chọn f tọa độ độc lập; biểu diễn phần còn lại qua chúng.
  5. **Đạo hàm lần 1** cho ràng buộc vận tốc; **lần 2** cho ràng buộc gia tốc, **có số hạng phụ**.
     - Thanh cứng: Δ**r**·Δ**v** = 0 (tức **thành phần vận tốc dọc thanh bằng nhau**); Δ**r**·Δ**a** + |Δ**v**|² = 0.
  6. Nối với D1: gia tốc trong Newton chính là các đạo hàm tọa độ ở bước 5.
- **Quy tắc rút gọn (đều suy ra từ ALG-K7):**
  - Dây qua ròng rọc cố định: tốc độ (gia tốc) hai đầu bằng nhau theo chiều dây.
  - **Ròng rọc động** (dây vòng qua nó, hai nhánh thẳng đứng): độ dài dây ở hai nhánh là (x_C − y₁) + (x_C − y₂) = hằng, với x_C là tọa độ tâm ròng rọc, y₁, y₂ là tọa độ hai điểm mà dây rời khỏi nhánh (đo cùng chiều dương, chẳng hạn xuống). Suy ra **x_C = (y₁ + y₂)/2 + hằng** và a_C = (a₁ + a₂)/2. Ví dụ: một đầu dây buộc trần (y₁ cố định), đầu kia vắt qua ròng rọc cố định nối vật A treo: 2x_C + x_A = hằng ⇒ a_A = −2a_C.
  - Tổng quát: nếu Σ ℓ_i = hằng thì **Σ ±a_i = 0** (dấu theo chiều dài đoạn tăng/giảm).
  - **Điểm tiếp xúc giữa hai vật cứng:** thành phần vận tốc **pháp tuyến** bằng nhau (giữ tiếp xúc).
- **Pre:** Ràng buộc **holonomic** dạng f(q, t) = 0. Dây chỉ là đẳng thức khi **căng**; khi chùng là bất đẳng thức ℓ ≤ L (P10).
- **Suf:** Có bất kỳ thứ gì *nối*, *ép*, *dẫn* các đối tượng với nhau.
- **Chuyển sang Toán (V2):** Hệ đại số **tuyến tính** cho các gia tốc/vận tốc ẩn; kết hợp với Newton thành hệ đóng kín (1.7).
- **Bẫy:**
  - Dây quấn nhiều đoạn (quên đoạn nào tham gia độ dài).
  - Ròng rọc động: thiếu một ràng buộc.
  - Đạo hàm bậc hai của ràng buộc phi tuyến **bỏ số hạng |Δ**v**|²** (chính là hướng tâm tương đối).
  - Nhầm dấu chiều dương giữa các đoạn dây.
- **Nâng cao [EXT]:** **Tâm quay tức thời** (vật cứng phẳng): vận tốc mọi điểm ⟂ đường nối tới tâm quay tức thời; dựng từ ràng buộc "thành phần dọc thanh bằng nhau". Ranh giới với động học vật rắn: tôi không đi sâu.

---

### K8. Bài toán cực trị và bao hình trong động học **[C/H]**

- **Kiểu CHỖ:** (1 tham số tự do λ — góc, thời gian, hướng, vận tốc — và một đại lượng cần tối ưu).
- **Công cụ:**
  - **(a)** Đạo hàm: dF/dλ = 0 (kiểm bằng đạo hàm hai hoặc biên).
  - **(b)** **Discriminant:** khi điều kiện chạm là phương trình bậc hai theo λ (như K3): Δ ≥ 0 ⇒ miền tồn tại; Δ = 0 ⇒ biên (bao hình).
  - **(c)** **Hình học:** đường tiếp xúc (quỹ đạo tiếp xúc với đường mục tiêu ⇒ nghiệm kép).
  - **(d)** **Bao hình:** họ F(x, y; λ) = 0 ⇒ khử λ từ F = 0, ∂F/∂λ = 0.
  - **(e)** **Nguyên lý thời gian nhỏ nhất (Fermat, dạng động học):** đường đi nhanh nhất qua hai vùng có tốc độ v₁, v₂ thỏa sinθ₁/v₁ = sinθ₂/v₂.
- **Suf:** Đề hỏi "lớn nhất", "nhỏ nhất", "điều kiện để…", "vùng an toàn", "góc tối ưu".
- **Trình tự cố định (V1):** (1) Xác định tham số tự do λ; (2) viết điều kiện chạm/mục tiêu thành phương trình theo λ; (3) chọn (a)–(e); (4) kiểm biên miền.
- **Chuyển sang Toán (V2):** Bài Toán cực trị/bất đẳng thức; đôi khi dùng AM–GM.
- **Mẫu dùng (đã kiểm):** v₀² ≥ g(y + √(x² + y²)) (tốc độ tối thiểu); R_max trên mặt nghiêng; parabol an toàn.
- **Bẫy:** Nghiệm tối ưu nằm ngoài miền (t < 0, góc ngoài khoảng); quên xét biên; Δ ≥ 0 chỉ bảo đảm nghiệm *thực*, còn cần *hợp lý vật lý* (t > 0, chưa chạm đất trước…).

---

## PHẦN 4. ĐỘNG LỰC HỌC (b) — D1 đến D11

---

### D1. Định luật Newton và thuật toán "quét biên" (vẽ lực) **[C]** + thuật toán **[H]**

- **Kiểu CHỖ:** (1 vật, 1 thời điểm, 1 hướng).
- **Nội dung:**
  - N1: tồn tại hệ quán tính (định nghĩa hệ quán tính).
  - N2: **ΣF** = d**p**/dt = m**a** (m không đổi).
  - N3: **F**_AB = −**F**_BA (hai lực đặt lên **hai vật khác nhau**). Dạng mạnh: hai lực còn cùng đường nối (lực xuyên tâm).
  - Nguyên lý chồng chất lực.
- **Dom:** Hệ quán tính, v ≪ c, chất điểm.
- **Pre (tại CHỖ):** (i) đang dùng hệ quán tính, hoặc đã thêm đủ lực quán tính (D9, D10); (ii) khối lượng không đổi (nếu đổi, sang D8); (iii) đã **liệt kê đầy đủ** lực.
- **Suf:** Bất kỳ khi có vật và lực. Nhưng D1 là công cụ **tốn ẩn nhất** (mỗi lực liên kết chưa biết là một ẩn); dùng khi các công cụ khử ẩn ở 1.6 không đủ, hoặc khi cần *lực tức thời*.
- **Trình tự cố định ALG-D1 (V1 + V2):**
  1. Chọn **một vật** (Σ1); vẽ riêng vật đó.
  2. **QUÉT BIÊN:** đi vòng quanh biên của vật (như quét pixel). *Mỗi chỗ tiếp xúc với vật khác cho một lực:*

| Loại tiếp xúc | Lực | Hướng | Ẩn |
|---|---|---|---|
| Mặt | Pháp tuyến N (đẩy vật) | ⟂ mặt, hướng ra khỏi mặt | 1 (N ≥ 0) |
| Mặt (nhám) | Ma sát f | Dọc mặt | 1 (hoặc = μN nếu trượt) |
| Dây | Sức căng T | Dọc dây, hướng ra khỏi vật | 1 (T ≥ 0) |
| Lò xo | Đàn hồi | Dọc lò xo | 0 nếu biết độ biến dạng |
| Vật đẩy/kéo chủ động | F cho trước | — | 0 |

  3. **QUÉT TRƯỜNG:** trọng lực m**g** (luôn), hấp dẫn, lực quán tính nếu hệ phi quán tính.
  4. Ghi hướng giả định cho lực chưa biết (dấu đại số của kết quả sẽ cho biết đúng/sai).
  5. **Chọn trục** để *loại* phản lực chưa biết khỏi một phương trình: chiếu lên phương **vuông góc** với lực ẩn khi có thể.
  6. Viết ΣF_e = m a_e cho từng trục.
  7. Thêm ràng buộc K7 (liên hệ gia tốc), N3 (nối lực giữa các vật, không thêm ẩn mới).
  8. Đếm ẩn–phương trình (1.7). Kiểm bất đẳng thức chế độ (P10: N ≥ 0, T ≥ 0, |f| ≤ μ_sN).
- **Chuyển sang Toán (V2):** Hệ phương trình đại số (tuyến tính theo gia tốc và lực).
- **Chiến lược hệ nhiều vật nối:** (1) chọn Σ = **cả hệ** theo phương dây để tìm gia tốc chung (sức căng nội bị triệt); (2) **cô lập từng vật** để tìm T, N.
- **Bẫy:**
  - **"Lực hướng tâm" không phải một lực mới**; đó là *tổng* các lực theo phương hướng tâm (không vẽ thêm).
  - N3: hai lực của cặp tác dụng lên hai vật khác nhau nên **không triệt tiêu** trên cùng vật.
  - Vẽ "lực đà", "lực chuyển động" (không tồn tại).
  - Chiều dương không thống nhất giữa các vật/trục.
  - Ma sát: hướng ngược **chuyển động tương đối** (hoặc xu hướng).
- **Nâng cao:** Với hệ nhiều vật: **ΣF_ext = M a_cm** (C2) cho phép bỏ qua mọi lực nội. Lực vuông góc với **v** không sinh công (nền tảng cho C3).

---

### D2. Liên kết: dây, ròng rọc, phản lực **[C]**

- **Kiểu CHỖ:** (1 dây hoặc 1 điểm tiếp xúc).
- **Nội dung:**
  - **Dây nhẹ không dãn:** sức căng đều dọc dây (nếu không tiếp xúc nhám với vật khác); chỉ kéo (T ≥ 0); giữ độ dài (K7).
  - **Ròng rọc nhẹ, không ma sát trục:** sức căng hai phía bằng nhau. (Ròng rọc có khối lượng: (T₁ − T₂)R = Iα, thuộc vật rắn nên ngoài phạm vi.)
  - **Dây nặng đồng chất** (khối lượng dài λ): T thay đổi dọc dây; viết Newton cho phần tử dm = λds. Dây treo tĩnh: T(s) = λgs (s tính từ đầu tự do).
  - **Dây vắt qua trụ cố định nhám** (công thức Euler–Eytelwein/"capstan"): **T_lớn = T_nhỏ·e^{μφ}**, với φ là góc ôm (rad). Đúng khi dây **sắp trượt** hoặc đang trượt đều; khi dây đứng yên có thể T_lớn/T_nhỏ ≤ e^{μ_sφ}. Trụ nhẵn: T đều.
- **Pre:** "Dây nhẹ" nghĩa là m_dây ≪ khối lượng vật *và* gia tốc không quá lớn; kiểm bằng T·ẩn.
- **Suf:** Có dây, chuỗi, ròng rọc, xích.
- **Trình tự cố định (V1):** Với mỗi dây: (1) Có khối lượng? (2) Có tiếp xúc nhám với vật khác? (3) Căng hay chùng (τ5, P10)? Với mỗi ròng rọc: (4) nhẹ? (5) trục không ma sát? (6) cố định hay động (K7)?
- **Chuyển sang Toán (V2):** Sức căng là ẩn đại số; dây nặng cho phương trình vi phân theo s; capstan cho phương trình dT/dφ = μT (tích phân tách biến).
- **Bẫy:** Coi sức căng hai phía ròng rọc bằng nhau khi ròng rọc **có** ma sát trục hay có khối lượng; quên rằng dây chỉ **kéo**: nếu nghiệm T < 0 thì dây chùng (đổi chế độ P10).

---

### D3. Ma sát **[C]**

- **Kiểu CHỖ:** (1 mặt tiếp xúc, 1 trạng thái).
- **Nội dung:**
  - **Nghỉ:** |f| ≤ μ_sN; hướng ngược **xu hướng trượt**.
  - **Trượt:** f = μ_kN; hướng ngược **vận tốc tương đối** của hai bề mặt.
  - **Góc ma sát φ_m:** tanφ_m = μ. Phản lực toàn phần **R** = N + f luôn nằm **trong nón ma sát** (góc lệch so với pháp tuyến ≤ φ_m).
  - Vật trên mặt nghiêng α: nằm yên nếu tanα ≤ μ_s. Trượt xuống: a = g(sinα − μ_k cosα).
  - **Lực kéo nhỏ nhất** để kéo đều vật trên mặt ngang: **F_min = μmg/√(1 + μ²)** khi hướng kéo hợp với phương ngang góc θ có tanθ = μ (F kéo lên trên).
  - **Nhiệt do ma sát:** Q = μ_kN·s_rel (s_rel = quãng đường **trượt tương đối**).
- **Pre:** Có tiếp xúc (N ≥ 0). μ_s, μ_k hằng, không phụ thuộc tốc độ hay diện tích (theo mô hình đề cho).
- **Suf:** Có bề mặt nhám tiếp xúc.
- **Trình tự cố định ALG-D3 (P10, tối đa 2^k tổ hợp cho k mặt):**
  1. Với mỗi mặt: **giả sử dính**, giải hệ với f là ẩn.
  2. Kiểm **|f| ≤ μ_sN**.
  3. Nếu vi phạm: đổi sang **trượt**, f = μ_kN (hướng theo v_rel dự kiến), giải lại; kiểm v_rel đúng hướng đã giả sử.
  4. Với nhiều mặt, lặp qua các tổ hợp (mặt 1 dính/trượt × mặt 2 dính/trượt × …) đến khi có tổ hợp nhất quán.
- **Chuyển sang Toán (V2):** Hệ đại số + các bất đẳng thức của chế độ; đáp án kèm **điều kiện** (ví dụ F ≤ …).
- **Mẫu dùng (đã tự kiểm bằng D1):** Vật m đặt trên vật M, sàn nhẵn, ma sát nghỉ μ_s giữa hai vật.
  - Lực F kéo vật **dưới** M theo phương ngang: hai vật không trượt tương đối ⇔ **F ≤ μ_s(M + m)g**.
  - Lực F kéo vật **trên** m: hai vật không trượt ⇔ **F ≤ μ_s m g (M + m)/M**.
- **Bẫy:**
  - Nhầm μ_s và μ_k.
  - Ma sát nghỉ có thể **cùng chiều** chuyển động của vật (băng chuyền, xe tăng tốc).
  - Nhầm N ≠ mg khi có lực xiên/nghiêng.
  - Trượt là so với **bề mặt kia**, không phải so với đất.
  - Coi ma sát nghỉ là tỏa nhiệt. Nếu không có trượt tương đối thì không tỏa nhiệt; ma sát nghỉ vẫn có thể sinh công dương lên vật này và công âm lên vật kia, tổng của cặp bằng 0.

---

### D4. Lực đàn hồi, lò xo **[C]**

- **Kiểu CHỖ:** (1 lò xo, 1 trạng thái biến dạng).
- **Nội dung:**
  - F = k|l − l₀|, hướng đưa lò xo về l₀.
  - **Ghép nối tiếp:** 1/k = Σ1/k_i. **Song song:** k = Σk_i.
  - **Cắt lò xo:** đoạn chiếm tỉ lệ f chiều dài có k' = k/f.
  - Thế năng đàn hồi ½k(Δl)².
  - **Lò xo có khối lượng m_s** (dao động chậm, lò xo đồng đều): khối lượng hiệu dụng **m + m_s/3** (đã kiểm: ∫½(m_s/L)(ẋs/L)²ds = m_sẋ²/6).
- **Pre:** Biến dạng trong giới hạn Hooke; lò xo nhẹ (lực hai đầu bằng nhau); dây đàn hồi chỉ kéo (chùng → lực 0, sự kiện τ8/τ5).
- **Suf:** Có lò xo/dây co giãn.
- **Trình tự cố định (V1):** (1) Xác định l₀; (2) đặt tọa độ **từ vị trí cân bằng tĩnh** (P13): trọng lực và lực đàn hồi tĩnh triệt nhau ⇒ chỉ còn −kx; (3) kiểm lò xo không bị nén quá mức (dây chùng: chia giai đoạn).
- **Chuyển sang Toán (V2):** Phương trình m ẍ = −kx (O1).
- **Mẫu dùng:** Hai vật m₁, m₂ nối lò xo: ω² = k/μ (P7), μ = m₁m₂/(m₁ + m₂).
- **Bẫy:** Nhầm độ giãn với chiều dài lò xo; k ghép sai; lò xo cắt: k **tăng** khi đoạn ngắn hơn; hai vật nối lò xo có **hai** gia tốc khác nhau.

---

### D5. Lực cản (chuyển động trong môi trường) **[C]**

- **Kiểu CHỖ:** (1 vật, khoảng thời gian, trục theo v).
- **Nội dung:**
  - **Cản tuyến tính** F = −bv: v = (mg/b)(1 − e^{−bt/m}) khi rơi từ nghỉ; **v_t = mg/b**; hằng số thời gian m/b.
  - **Cản bậc hai** F = −cv|v|: **v_t = √(mg/c)**; v = v_t·tanh(gt/v_t); độ cao rơi y = (v_t²/g)·ln cosh(gt/v_t); v(y) = v_t√(1 − e^{−2gy/v_t²}).
  - **Tuyến tính tách được hai trục** (chuyển động ném có cản tuyến tính: x(t) và y(t) độc lập); **bậc hai thì không tách**.
- **Pre:** Đề cho dạng lực cản (không suy đoán).
- **Suf:** "Lực cản tỉ lệ với v (hoặc v²)".
- **Trình tự cố định (V1):** (1) Vận tốc giới hạn tìm **không cần ODE**: đặt a = 0 ⇒ v_t; (2) cần v(t) hoặc v(x) ⇒ K2 (đổi biến, tách biến).
- **Chuyển sang Toán (V2):** ODE tách biến bậc nhất.
- **Bẫy:** Hướng cản luôn **ngược v** (dùng −b**v**, không −b|v|); v_t đạt **tiệm cận** (không đạt hữu hạn thời gian); nhầm dạng cản.

---

### D6. Chuyển động cong: lực hướng tâm và tiếp tuyến **[C]**

- **Kiểu CHỖ:** (1 vật, 1 điểm trên quỹ đạo, hệ (t, n)).
- **Nội dung:** **ΣF_n = mv²/ρ** (hướng vào tâm cong), **ΣF_t = m dv/dt**.
- **Pre:** Xác định đúng tâm cong (K5); hệ quán tính.
- **Suf:** Vật đi trên quỹ đạo cong (vòng, cầu, nón, cua, dây quay).
- **Trình tự cố định ALG-D6:**
  1. Xác định điểm quan tâm và **tâm cong** (hướng **n**).
  2. **Chiếu** mọi lực lên **n** (hướng tâm dương) và **t**.
  3. Viết Σ(lực hướng vào tâm) − Σ(lực hướng ra) = mv²/ρ.
  4. Nếu cần v: lấy từ **năng lượng** (C4) giữa trạng thái đã biết và điểm đó; sau đó thay v vào phương trình hướng tâm để tìm lực (chuỗi công cụ **Năng lượng → v → Newton hướng tâm → lực**).
  5. Kiểm điều kiện chế độ: N ≥ 0, T ≥ 0 (τ4, τ5).
- **Mẫu dùng (đã kiểm):**
  - Con lắc đơn: T = mg cosθ + mv²/l; kết hợp v² = 2gl(cosθ − cosθ₀) ⇒ **T = mg(3cosθ − 2cosθ₀)**.
  - **Con lắc nón:** cosθ = g/(ω²l) (ω² = g/(l cosθ)).
  - **Đường cua nghiêng góc α, không ma sát:** tanα = v²/(gR). Có ma sát: v²_max = gR(tanα + μ)/(1 − μ tanα), v²_min = gR(tanα − μ)/(1 + μ tanα).
  - **Vòng xiếc bán kính R** (vật chất điểm, nhẵn): v_đỉnh² ≥ gR ⇒ v_đáy² ≥ 5gR; thả từ nghỉ ở độ cao h so với đáy: **h ≥ 5R/2**.
  - **Dây** quay tròn thẳng đứng: v_đáy² ≥ 5gl; **thanh cứng**: v_đáy² ≥ 4gl (chỉ cần v_đỉnh ≥ 0).
  - **Trượt trên bán cầu (nhẵn):** rời mặt tại **cosθ = 2/3** (θ đo từ đỉnh).
- **Bẫy:** Dùng R hình học thay ρ; nhầm dấu hướng tâm/ly tâm; quên rằng tại điểm N = 0 vật chuyển sang chuyển động ném (K3).

---

### D7. Lực hấp dẫn và trường hấp dẫn **[C]**

- **Kiểu CHỖ:** (2 vật hoặc 1 vật và trường).
- **Nội dung:**
  - F = GMm/r². g(h) = GM/(R + h)² ≈ g(1 − 2h/R).
  - **Vệ tinh tròn:** v² = GM/r; T² = 4π²r³/(GM).
  - **Vỏ cầu đồng chất:** bên trong lực bằng 0; bên ngoài như khối lượng tập trung tại tâm. **Trong cầu đặc đồng chất** (r < R): g(r) = GMr/R³ (dao động điều hòa qua đường hầm xuyên tâm: ω² = g/R, T ≈ 84 phút).
- **Pre:** Vật đối xứng cầu hoặc chất điểm.
- **Suf:** Có hai thiên thể/vệ tinh, hoặc "độ cao lớn", "vệ tinh", "đường hầm".
- **Trình tự cố định (V1):** (1) Chọn Σ; (2) **quỹ đạo tròn**: D1 hướng tâm; **quỹ đạo tổng quát**: C4 và C7 (Kepler); (3) g biến thiên: dùng thế năng −GMm/r chứ không dùng mgh.
- **Bẫy:** Dùng mgh ở độ cao ~R; nhầm khối lượng "hiệu dụng" trong cầu rỗng/đặc; nhớ Trái Đất quay khi hỏi "trọng lượng" (D10).

---

### D8. Khối lượng biến thiên **[C] + thuật toán [H]**

- **Kiểu CHỖ:** (hệ cố định gồm khối lượng tại t và phần sắp vào/ra, khoảng dt, hướng).
- **Nội dung:** **F = m dv/dt** *không* áp dụng trực tiếp khi khối lượng đổi. Dạng đúng:

> **m d**v**/dt = F_ext + (dm/dt)(u − v)**

với dm/dt là tốc độ đổi khối lượng của vật (âm khi phóng ra), **u** là vận tốc (trong hệ quán tính) của phần khối lượng bị thêm vào/tách ra.
- **Hệ quả:**
  - **Nhận khối lượng đang nằm yên** (u = 0): F_ext = d(mv)/dt.
  - **Tên lửa** (vận tốc phóng khí so với tên lửa là −u_rel, u_rel > 0 theo chiều ngược chuyển động): **m dv/dt = u_rel·|dm/dt| + F_ext**; không trọng lực: **Δv = u_rel ln(m₀/m)**; có trọng lực đều (bay lên thẳng đứng): v = u_rel ln(m₀/m) − gt.
  - **Xích thả từ nghỉ, treo thẳng đứng, đầu dưới sát mặt bàn, rơi tự do xuống bàn** (mắt xích dừng ngay khi chạm bàn): lực bàn = **3λgx** (x là chiều dài đã nằm trên bàn): gồm λgx (trọng lượng phần trên bàn) và λv² = 2λgx (đổi động lượng).
- **Pre:** Xác định **rõ hệ** và vận tốc phần vào/ra trong hệ quán tính.
- **Trình tự cố định (V1):** (1) Chọn hệ **cố định về mặt vật chất tại t** (gồm phần chính + phần dm sắp vào/ra); (2) viết p(t + dt) − p(t) = F_ext·dt; (3) chuyển thành d**p**/dt; (4) chiếu.
- **Bẫy:** Dùng **bảo toàn cơ năng** khi có va chạm mềm/mắt xích dừng đột ngột (mất năng lượng); áp dụng F = m dv/dt sai; nhầm hệ quy chiếu của **u**.

---

### D9. Hệ quy chiếu chuyển động có gia tốc tịnh tiến **[C]**

- **Kiểu CHỖ:** (hệ quy chiếu với gia tốc a₀).
- **Nội dung:** Lực quán tính F_qt = −m**a**₀ (không có phản lực). **g_eff = g − a₀**. Thế năng của lực quán tính (a₀ hằng): U = m**a**₀·**r**; cùng với trọng lực: U = −m**g**_eff·**r**.
- **Pre:** Biết **a₀ của hệ** (không phải của vật đang xét).
- **Suf:** Vật/hệ đặt trong xe, thang máy, nêm có gia tốc cho trước hoặc dễ tính.
- **Trình tự cố định (V1):** (1) Xác định a₀; (2) tính g_eff (vector); (3) làm bài trong hệ đó như trường g_eff (K3, D6, O3).
- **Mẫu dùng:** Trọng lượng biểu kiến trong thang máy gia tốc a hướng lên: N = m(g + a). Con lắc trong xe gia tốc a: cân bằng nghiêng tanφ = a/g; chu kỳ 2π√(l/√(g² + a²)). Mặt nghiêng trên xe: g_eff.
- **Bẫy:** Nếu **a₀ chưa biết** (nêm bị vật đẩy): không dùng hệ này ngay; viết Newton cho nêm trong hệ quán tính trước (thêm ẩn a₀). Lực quán tính **không** có cặp N3.

---

### D10. Hệ quy chiếu quay: lực ly tâm, Coriolis **[C]**

- **Kiểu CHỖ:** (hệ quay với trục và ω xác định).
- **Nội dung:** Trong hệ quay đều tốc độ góc **ω**, phương trình cho vật có vận tốc **v'** so với hệ quay:

> m**a'** = **F** − 2m **ω** × **v'** − m **ω** × (**ω** × **r'**)

  - **Ly tâm:** F_cf = mω²r_⊥ (hướng ra xa **trục**, r_⊥ là khoảng cách đến **trục**); thế năng U_cf = −½mω²r_⊥².
  - **Coriolis:** F_C = −2m**ω**×**v'** (⟂ **v'** nên **không sinh công**).
  - Nếu ω đổi: thêm −m(d**ω**/dt)×**r'**.
- **Hệ quả:**
  - **Bảo toàn "năng lượng hiệu dụng" trong hệ quay đều:** E' = ½mv'² + U(r) − ½mω²r_⊥² = hằng (nếu U đứng yên trong hệ quay).
  - **Trái Đất quay:** g_eff = g − ω×(ω×R); rơi tự do từ độ cao h lệch về phía **đông** một đoạn d = (1/3)ωcosλ√(8h³/g) (λ là vĩ độ; đã kiểm số).
- **Pre:** Xác định trục quay và ω; hệ quay có ω hằng (hoặc thêm số hạng Euler).
- **Suf:** Vật chuyển động trên/trong vật quay; vật nằm yên trên đĩa quay; bài Trái Đất quay; đề nói "quan sát trong hệ quay".
- **Nên dùng khi nào [H]:** Nếu vật **đứng yên hoặc chuyển động đơn giản** trong hệ quay ⇒ bài **tĩnh** trong hệ quay (dễ). Nếu vật chuyển động phức tạp trong hệ quán tính, dùng **tọa độ cực trong hệ quán tính** (P5) thường an toàn hơn.
- **Trình tự cố định (V1):** (1) Xác định trục, ω; (2) có thể thêm F_cf, F_C; (3) chọn phương chiếu (dọc bán kính/vuông góc).
- **Mẫu dùng (đã kiểm):**
  - **Hạt trượt nhẵn trên thanh quay đều** (thanh vuông góc trục): r̈ = ω²r ⇒ r = Ae^{ωt} + Be^{−ωt}; phản lực N = 2mω ṙ (Coriolis cân bằng bởi N).
  - **Hạt trên vòng bán kính R quay quanh trục thẳng đứng với ω:** θ̈ = sinθ(ω²cosθ − g/R); cân bằng mới cosθ₀ = g/(Rω²) (tồn tại nếu ω² > g/R); dao động nhỏ: **ω_dđ² = ω² − g²/(R²ω²)**.
- **Bẫy:** Cộng ly tâm vào Newton ở **hệ quán tính**; lấy khoảng cách đến tâm thay vì đến **trục**; sai dấu Coriolis; quên rằng **F_C không sinh công** nhưng làm đổi hướng và đòi phản lực.
- **Ghi chú syllabus [?]:** IPhO nêu lực quán tính, ly tâm, thế năng trong hệ quay, và có ghi "cộng gia tốc không có số hạng Coriolis; nhận ra khi nào Coriolis bằng 0". Hiểu là *không bắt buộc nhớ công thức Coriolis*, nhưng cần biết khi nào nó hiện diện và khi nào bị cân bằng bởi phản lực.

---

### D11. Cân bằng tĩnh và nguyên lý công ảo (chất điểm) **[C], phần công ảo [EXT]**

- **Kiểu CHỖ:** (1 hệ ở trạng thái cân bằng, một dịch chuyển ảo).
- **Nội dung:**
  - ΣF = 0. **Ba lực** cân bằng: đồng quy, tam giác lực khép kín; định lý Lami: F₁/sin α₁ = F₂/sin α₂ = F₃/sin α₃ (α_i là góc đối diện).
  - **Công ảo:** với liên kết **lý tưởng**, cân bằng ⇔ **ΣF_i^{(chủ động)}·δ**r**_i = 0** với mọi dịch chuyển ảo tương thích với ràng buộc.
  - **Cân bằng bảo toàn:** dU/dq = 0; **ổn định** nếu d²U/dq² > 0.
- **Pre:** Liên kết lý tưởng (nhẵn); δ**r** tương thích với ràng buộc tại thời điểm "đóng băng".
- **Suf:** Nhiều vật liên kết, cần tìm góc/lực cân bằng mà không cần các phản lực.
- **Trình tự cố định ALG-D11:** (1) Chọn tọa độ suy rộng q; (2) cho δq nhỏ, tính δ**r**_i theo δq; (3) viết Σ**F**_i·δ**r**_i = Q_q δq; (4) Q_q = 0.
- **Bẫy:** Đưa ma sát vào như phản lực lý tưởng; δ**r** ≠ chuyển động thực khi ràng buộc phụ thuộc thời gian.

---

### Bảng "kiểu bài ứng dụng" → chuỗi công cụ (mục "Ứng dụng định luật Newton và các lực cơ học vào bài tập") **[H]**

| Kiểu bài | Chuỗi công cụ | Điểm mấu chốt |
|---|---|---|
| Mặt phẳng nghiêng + ma sát | P5 (dọc–vuông góc) → D1 → D3 (P10) | Kiểm f ≤ μ_sN trước khi coi là trượt |
| Atwood, ròng rọc (động) | K7 (ràng buộc) → D1 mỗi vật → D2 | Tìm gia tốc chung bằng Σ = cả hệ, rồi cô lập |
| Hai vật chồng lên nhau | D1 mỗi vật → D3 (P10) | Điều kiện không trượt là bất đẳng thức |
| Vật trên nêm **di động** | K7 (a_rel và A) + D1 (vật, nêm); **hoặc** C1 (ngang) + C4 | Kiểm N ≥ 0; ràng buộc phụ thuộc thời gian |
| Xe, thang máy gia tốc | D9 → g_eff | Xác định a₀ **của hệ** |
| Cua nghiêng, vòng xiếc, cầu lồi | D6 + C4 | Năng lượng cho v; hướng tâm cho lực; N ≥ 0 |
| Trượt trên bán cầu / vật rời mặt | C4 + D6 + (τ4: N = 0) | Sau rời mặt: K3 |
| Dây trượt/dây nặng trên bàn | C2 (khối tâm) hoặc D2 (dây nặng); chú ý D8 nếu va chạm mềm | Cơ năng không bảo toàn khi mắt xích dừng |
| Lò xo + vật | D4 → O | Đặt gốc tại cân bằng tĩnh |
| Rơi có cản | D5 + K2 | v_t: đặt a = 0 |
| Đĩa quay / vật nằm yên trên vật quay | D10 (hoặc D6 ở hệ quán tính) | Trục quay đúng; f_ms nghỉ cung cấp hướng tâm |
| Nhiều vật nối + lực nội | C2 hoặc D1 (Σ = cả hệ rồi cô lập) | Triệt nội lực bằng N3 |

---

## PHẦN 5. CÁC ĐỊNH LUẬT BẢO TOÀN (c) — C1 đến C9

Nhắc lại nguyên lý ở 1.6: **mỗi định luật bảo toàn là một máy khử ẩn.** Vì vậy mỗi thẻ ở đây có mục "Suf-test" dưới dạng thuật toán kiểm điều kiện, đây là nơi phép "duyệt từng pixel" trong README hiệu quả nhất.

---

### C1. Xung lượng và bảo toàn động lượng **[C]**

- **Kiểu CHỖ:** (Σ, khoảng thời gian [t₁, t₂], phương e).
- **Nội dung:**
  - **p** = m**v**; ΣF_ext = d**P**/dt.
  - **Định lý xung lượng:** ∫ΣF_ext dt = Δ**P** (vector, viết theo từng thành phần).
  - **Bảo toàn theo phương e:** nếu ΣF_ext,e = 0 (hoặc xung ngoại lực theo e bằng 0) thì P_e không đổi.
- **Dom:** Hệ quán tính.
- **Pre (tại CHỖ):** Trong [t₁, t₂] và **theo phương e**: (i) mọi ngoại lực có thành phần theo e triệt tiêu, hoặc (ii) **xung** ngoại lực theo e ≪ xung nội (va chạm: Δt → 0, ngoại lực hữu hạn).
- **Suf-test ALG-C1:**
  1. Chọn Σ **chứa mọi vật tương tác** mà ta muốn khử nội lực (1.6).
  2. Liệt kê **mọi ngoại lực** lên Σ trong khoảng đang xét (quét biên D1, quét trường).
  3. Với từng phương e ứng viên (e1, e2, e5 trong 1.4c): xét thành phần của từng ngoại lực theo e:
     - Tất cả bằng 0 ⇒ **bảo toàn chính xác** theo e.
     - Chỉ là lực hữu hạn nhưng Δt rất ngắn ⇒ **bảo toàn gần đúng**, ghi Err: ε_p ≈ F_ngoại·Δt/|Δp_nội|.
     - Có **xung ngoại** lớn (phản lực tường, mặt cố định, dây căng đột ngột, chốt) ⇒ **không** bảo toàn theo phương của xung đó.
  4. Viết Σm_iv_{i,e} (sau) = Σm_iv_{i,e} (trước).
- **Post:** Một phương trình vô hướng cho mỗi phương e thỏa.
- **Chuyển sang Toán (V2):** Phương trình đại số tuyến tính theo các vận tốc.
- **Mẫu dùng:**
  - Vật trên nêm, sàn **nhẵn**: sàn chỉ có phản lực đứng ⇒ chỉ bảo toàn theo phương **ngang**.
  - **Súng–đạn, nổ, phân rã:** nội lực ≫ ngoại lực trong Δt.
  - Người đi trên thuyền: xem C2.
- **Bẫy:**
  - Va chạm với tường/mặt cố định: động lượng theo **pháp tuyến** *không* bảo toàn (tường tác dụng xung).
  - Trọng lực làm P_y không bảo toàn về nguyên tắc, nhưng bỏ qua được trong va chạm tức thời.
  - Bảo toàn động lượng phải viết trong **cùng một hệ quán tính**, đủ dấu.
  - Bài có ràng buộc (dây căng đột ngột): xung của sức căng ⇒ phương dọc dây **không** bảo toàn.

---

### C2. Khối tâm và định lý chuyển động khối tâm **[C]**

- **Kiểu CHỖ:** (Σ, khoảng thời gian, phương e).
- **Nội dung:**
  - **R** = Σm_i**r**_i/M.
  - **M a_cm = ΣF_ext** (mọi nội lực triệt).
  - Nếu ΣF_ext,e = 0: V_cm,e = hằng; nếu ban đầu nghỉ, **X_cm,e = hằng** ⇒ Σm_iΔx_{i,e} = 0.
- **Pre:** Xác định đúng ΣF_ext (kể cả phản lực từ ngoài hệ).
- **Suf:** Đề hỏi *dịch chuyển* của vật khi vật khác dịch chuyển trong một hệ **không có ngoại lực theo phương đó**; hoặc gia tốc chung của hệ nhiều vật nối.
- **Trình tự cố định ALG-C2:** (1) Chọn Σ; (2) tính ΣF_ext theo phương e; (3) nếu = 0 và ban đầu nghỉ: đặt Σm_iΔx_i = 0; (4) biểu diễn Δx_i qua **dịch chuyển tương đối** đã cho.
- **Mẫu dùng (đã kiểm):** Người khối lượng m đi được đoạn L so với thuyền (khối lượng M) trên mặt nước nhẵn: thuyền lùi Δ = mL/(m + M).
- **Bẫy:** Dùng dịch chuyển **tương đối** như dịch chuyển so với đất; quên rằng V_cm ≠ 0 nếu ban đầu không nghỉ.

---

### C3. Công, công suất, định lý động năng **[C]**

- **Kiểu CHỖ:** (Σ, trạng thái 1, trạng thái 2).
- **Nội dung:**
  - dA = **F**·d**r**; P = **F**·**v** = dA/dt; P̄ = A/Δt.
  - **ΔK = A_tổng** (công của **mọi** lực tác dụng lên từng vật, kể cả nội lực).
  - **König:** K = ½MV_cm² + K' (K' trong hệ khối tâm).
  - Nội lực: A_int = ∫**F**₁₂·d(**r**₁ − **r**₂) (chỉ phụ thuộc dịch chuyển **tương đối**).
- **Công đặc biệt:**

| Lực | Công |
|---|---|
| Trọng lực | −mgΔh (Δh là độ cao **tăng**) |
| Đàn hồi | ½k(x₁² − x₂²) (x là độ biến dạng) |
| Ma sát trượt | −μ_kN·s (s là **quãng đường** tương đối) |
| Pháp tuyến ⟂ v, lực hướng tâm | 0 |
| Sức căng dây không dãn (cả hệ) | Tổng hai đầu = 0 |
| Lực hằng | **F**·Δ**r** |

- **Pre:** Hệ quán tính; dịch chuyển tính đúng cho **điểm đặt** lực.
- **Suf:** Đề hỏi v theo vị trí (không hỏi t); lực thay đổi theo vị trí; có lực không thế.
- **Trình tự cố định ALG-C3:** (1) Chọn Σ và hai trạng thái; (2) **quét biên + quét trường** cho *từng vật* trong Σ; (3) với mỗi lực xác định công (tính, hoặc bằng 0 vì ⟂ dịch chuyển, hoặc triệt theo cặp); (4) ΔK_tổng = ΣA.
- **Công suất:** P = Fv cosα. Xe chạy đều trên đường: lực kéo = lực cản ⇒ **v_max = P/F_cản**.
- **Bẫy:** ΔK phụ thuộc hệ quy chiếu (P2); dùng **độ dời** thay quãng đường cho ma sát; cộng công nội lực của **thanh/dây không dãn** (tổng bằng 0 chỉ khi không biến dạng và không trượt); pháp tuyến của mặt **di động** có sinh công.

---

### C4. Thế năng và bảo toàn cơ năng **[C]**

- **Kiểu CHỖ:** (Σ, trạng thái 1, trạng thái 2).
- **Nội dung:**
  - Lực bảo toàn ⇔ **F** = −∇U ⇔ ∮**F**·d**r** = 0 (miền đơn liên: ∇×**F** = 0).
  - **U:** trọng trường đều mgh; đàn hồi ½kx²; hấp dẫn −GMm/r; ly tâm (hệ quay) −½mω²r_⊥²; lực quán tính hằng m**a**₀·**r**.
  - **E = K + U; E₂ − E₁ = A_không thế.**
- **Dom:** Hệ quán tính (hoặc hệ có tính thế của lực quán tính).
- **Pre (tại CHỖ):** (i) Lực **không thế** có công tổng bằng 0 hoặc được tính vào A_nt; (ii) lực liên kết không sinh công tổng cộng (N ⟂ v; T dây không dãn của cả hệ); (iii) trong khoảng đang xét **không** có va chạm không đàn hồi/dây căng đột ngột/dừng đột ngột.
- **Suf-test ALG-C4 (thuật toán kiểm điều kiện):**
  1. Chọn Σ và hai trạng thái (τ1, hoặc τ2, τ11…).
  2. **Quét mọi lực** lên từng vật (D1). Phân loại:
     - **Lực thế** (trọng lực, đàn hồi, hấp dẫn): đưa vào U, **không** đếm thêm công (P6).
     - **Lực không thế** (ma sát, cản, lực kéo cho trước): tính A_nt.
     - **Lực liên kết:** N *tĩnh* ⟂ **v** ⇒ 0; T của dây không dãn: đưa **cả hệ** vào Σ để tổng công bằng 0.
  3. **Kiểm ràng buộc phụ thuộc thời gian** (nêm di động, ống/mặt quay): N của từng vật có thể sinh công. Chọn Σ **gồm cả** vật chuyển động của ràng buộc để tổng công N = 0 (nhưng E của **từng** vật không bảo toàn).
  4. **Kiểm sự kiện mất năng lượng** trong khoảng: va chạm mềm, dây căng đột ngột, mắt xích dừng… Nếu có, **chia giai đoạn** (P9), dùng C6 tại sự kiện.
  5. Viết E₁ + A_nt = E₂.
- **Post:** Một phương trình vô hướng.
- **Chuyển sang Toán (V2):** Đại số; thường kết hợp với D6 (lực hướng tâm) hoặc C1.
- **Bẫy:**
  - Đếm **hai lần** (đưa lò xo/Trái Đất vào Σ mà vẫn tính công của chúng).
  - Chọn gốc thế năng khác nhau ở hai vế.
  - **Cơ năng không bảo toàn khi va chạm mềm** dù mọi lực khác là thế.
  - Hệ quy chiếu: C4 đúng trong mọi hệ quán tính nhưng số ΔK khác nhau.
  - Mặt di động: **N sinh công**.

---

### C5. Đồ thị thế năng 1D: cân bằng, biên, chu kỳ **[C]**

- **Kiểu CHỖ:** (hàm U(q), một mức năng lượng E).
- **Nội dung:**
  - **Vùng cho phép:** K = E − U(q) ≥ 0.
  - **Điểm dừng (biên):** U(q) = E.
  - **Cân bằng:** U'(q₀) = 0. **Ổn định** nếu U''(q₀) > 0.
  - **Dao động nhỏ:** ω² = U''(q₀)/m_eff, m_eff là hệ số của ½q̇² trong động năng (nếu K = ½M_eff(q)q̇²).
  - **Chu kỳ chính xác:** T = 2∫_{q₁}^{q₂} dq/|q̇| = **√(2m)∫_{q₁}^{q₂} dq/√(E − U)**.
  - Tốc độ cực đại tại cực tiểu của U; E > U_max ⇒ chuyển động không bị giới hạn (thoát khỏi hố).
- **Pre:** Một bậc tự do; lực bảo toàn; nếu nhiều vật: đã quy về một tọa độ q qua ràng buộc (K7).
- **Suf:** Đề cho U(x) hoặc đường trượt; hỏi cân bằng, tần số, vùng chuyển động, vận tốc thoát.
- **Trình tự cố định ALG-C5:** (1) Viết U(q) và M_eff(q); (2) giải U' = 0; (3) dùng U'' để phân loại; (4) vẽ E − U ≥ 0; (5) tần số hoặc chu kỳ tương ứng.
- **Bẫy:** U'' = 0 (cần bậc cao hơn ⇒ dao động không điều hòa); quên M_eff **phụ thuộc q**; nhầm cân bằng bền/không bền.

---

### C6. Va chạm **[C]** (một số mục mở rộng **[EXT]**)

- **Kiểu CHỖ:** (Σ, khoảng va chạm [t⁻, t⁺], (n, t) tại điểm tiếp xúc).
- **Nội dung:**
  - **Xung** là đại lượng cốt lõi; lực hữu hạn bị bỏ qua trong Δt.
  - **Hệ số hồi phục (Newton):** e = −(v₂' − v₁')_n/(v₂ − v₁)_n, 0 ≤ e ≤ 1 (dọc **pháp tuyến n**).
  - Thành phần **tiếp tuyến** của mỗi vật **không đổi** (bề mặt nhẵn: xung ⟂ mặt).
  - **1D:**
    - v₁' = [(m₁ − e m₂)v₁ + m₂(1 + e)v₂]/(m₁ + m₂)
    - v₂' = [(m₂ − e m₁)v₂ + m₁(1 + e)v₁]/(m₁ + m₂)
    - Mất động năng: **ΔK = ½μ_r(1 − e²)(v₁ − v₂)_n²**, μ_r = m₁m₂/(m₁ + m₂) (đã kiểm).
  - **Đàn hồi (e = 1), m₁ = m₂:** trao đổi vận tốc. **Va vào vật nặng vô hạn chuyển động u:** v' = 2u − v (P2). **Va vào tường cố định:** v_n' = −e v_n, v_t' = v_t.
  - **Hoàn toàn không đàn hồi (e = 0):** cùng vận tốc theo **n**; mất K cực đại.
  - **Nổ/phân rã (hai mảnh):** P bảo toàn; trong hệ khối tâm p = √(2μE_giải phóng) mỗi mảnh.
  - **Tán xạ đàn hồi (P3), vật 2 đứng yên** [EXT]: tanθ₁ = m₂sinΘ/(m₁ + m₂cosΘ) (Θ là góc tán xạ trong hệ khối tâm). Nếu m₁ > m₂: **sinθ_max = m₂/m₁** (đã kiểm). Nếu m₁ = m₂: hai vật bay ra **vuông góc** (θ₁ + θ₂ = 90°).
  - **Bài đếm số va chạm** (hai khối và tường, đàn hồi) [EXT]: dùng tọa độ (√m₁v₁, √m₂v₂); mỗi va chạm là một phép phản xạ; số va chạm liên quan π. Với tỉ số khối lượng 100ⁿ, số va chạm là ⌊π·10ⁿ⌋ (n = 0, 1, 2 cho 3, 31, 314 va chạm).
- **Pre:** Δt ngắn; ngoại lực hữu hạn bỏ qua; đối tượng nhẵn (xung tiếp tuyến bằng 0) hoặc đã biết xung tiếp tuyến.
- **Suf:** Đề có "va chạm", "nổ", "đạn ghim vào", "bật lại", "dây căng đột ngột".
- **Trình tự cố định ALG-C6:**
  1. Xác định **Δt ngắn**; bỏ lực hữu hạn (trọng lực, ma sát hữu hạn, lò xo, sức căng thường) trong Δt.
  2. Xác định **điểm/mặt va chạm và pháp tuyến n**; chọn trục (n, t) (e5).
  3. Liệt kê **xung ngoại lực** (phản lực tường/mặt cố định, chốt, dây căng đột ngột), xác định phương của từng xung.
  4. **Bảo toàn động lượng** theo mọi phương e **không có xung ngoại** (C1). **Bảo toàn L_O** với điểm O nằm trên đường tác dụng của xung ngoại chưa biết (C7).
  5. **Điều kiện hồi phục** e cho thành phần **n** (một phương trình cho mỗi cặp tiếp xúc).
  6. Đếm ẩn–phương trình (1.7).
  7. Kiểm: sau va chạm hai vật tách ra (v_rel,n ≥ 0); không xuyên qua nhau.
  8. **Không dùng bảo toàn cơ năng** trừ khi e = 1 và không có tổn thất khác. Sau va chạm chuyển sang giai đoạn kế (P9), thường C4/D6.
- **Dây căng đột ngột (dây không dãn):** thành phần vận tốc **dọc dây** bị triệt (hoặc đổi dấu theo e nếu dây đàn hồi), thành phần vuông góc dây giữ nguyên; mất năng lượng ½mv_dọc². **Xung sức căng dọc dây** ⇒ dọc dây không bảo toàn động lượng của vật.
- **Mẫu chuỗi công cụ:** **Đạn ghim vào con lắc (chất điểm treo dây):** C1 (ngay sau va chạm, phương ngang) ⇒ C4 (sau va chạm) ⇒ D6 (điều kiện dây căng tại đỉnh). Vòng đầy đủ cần v_đáy² ≥ 5gl.
- **Bẫy:** Dùng cơ năng cho va chạm không đàn hồi; quên xung phản lực của tường; nhầm "va chạm mềm" (e = 0 **chỉ cho thành phần n**, không có nghĩa dính hoàn toàn nếu thành phần t khác 0 và có ma sát); quên kiểm hướng tách; va chạm xiên có ma sát cần thêm xung tiếp tuyến (ngoài phạm vi).

---

### C7. Momen xung lượng của chất điểm, lực xuyên tâm, Kepler **[EXT]**

- **Kiểu CHỖ:** (Σ, khoảng thời gian, **điểm O** hoặc trục e).
- **Nội dung:**
  - **L**_O = **r** × **p**; d**L**_O/dt = **M**_O = **r** × **F**, với O cố định trong hệ quán tính (hoặc O là khối tâm).
  - Hệ nhiều chất điểm: d**L**_O/dt = **M**_ext,O (nội lực **đối nhau và cùng đường** triệt).
  - **Bảo toàn L_e** nếu M_ext,O·**e** = 0.
  - **Lực xuyên tâm F(r)r̂:** **L** bảo toàn ⇒ chuyển động **phẳng**; tốc độ diện tích dA/dt = L/(2m) = hằng (định luật Kepler 2).
  - **Năng lượng hiệu dụng:** E = ½mṙ² + U_eff(r), U_eff = L²/(2mr²) + U(r). Biên: E = U_eff. Quỹ đạo tròn tại r₀: U_eff'(r₀) = 0; **ổn định nếu U_eff'' > 0** (lực hút ∝ r^{−s} ổn định khi s < 3).
  - **Kepler (U = −k/r, k = GMm):**
    - Quỹ đạo: r = p/(1 + e cosφ); p = L²/(mk); **e = √(1 + 2EL²/(mk²))**.
    - E < 0 (elip): **a = k/(2|E|)** (**không phụ thuộc L**); r_min = a(1 − e), r_max = a(1 + e); p = a(1 − e²).
    - **T = 2π√(a³/(GM))**, tức T² ∝ a³.
    - **Vis-viva:** **v² = GM(2/r − 1/a)**.
    - Quỹ đạo tròn: v = √(GM/r); thoát: v_esc = √(2GM/r).
    - Hai vật: dùng khối lượng rút gọn (P7); T² = 4π²a³/(G(m₁ + m₂)) với a là bán trục lớn của quỹ đạo **tương đối**.
  - **Chuyển quỹ đạo Hohmann** (từ tròn r₁ sang tròn r₂):
    - Δv₁ = √(GM/r₁)·(√(2r₂/(r₁ + r₂)) − 1)
    - Δv₂ = √(GM/r₂)·(1 − √(2r₁/(r₁ + r₂)))
- **Pre:** O cố định (hệ quán tính) hoặc O là khối tâm; nội lực xuyên tâm.
- **Suf-test ALG-C7 (chọn O):**
  1. Chọn Σ và điểm O ứng viên.
  2. Với mỗi ngoại lực, tính **M**_O = **r** × **F**, hoặc kiểm **F** đi qua O (M = 0), hoặc song song trục e (M_e = 0).
  3. **Chọn O sao cho lực chưa biết đi qua O** (phản lực trục, sức căng dây xuyên tâm, xung tại điểm va chạm): khi đó M_ext,O chỉ còn lực đã biết.
  4. Theo từng phương e: M_e = 0 ⇒ L_e bảo toàn.
- **Mẫu dùng:**
  - **Hạt trên mặt nhẵn nối dây kéo qua lỗ:** sức căng đi qua lỗ ⇒ L bảo toàn ⇒ mvr = hằng (v ∝ 1/r); công của lực kéo bằng ΔK (C3).
  - **Chuyển động dưới lực hút ∝ 1/r²:** dùng chuỗi **C7 (L) → C4 (E) → tìm r_min, r_max**.
- **Bẫy:** Chọn O **có gia tốc** (không có d**L**/dt = **M**); nội lực không xuyên tâm (làm dL_tổng ≠ 0); nhầm bán trục lớn với bán kính trung bình; quên khối lượng rút gọn; lấy T² ∝ r³ khi quỹ đạo không tròn (phải dùng a).
- **Ghi chú [?]:** Momen xung lượng của **vật rắn** (động học quay, mô men quán tính) là phần khác, tôi không làm ở đây.

---

### C8. Quét đối xứng và chọn giữa các định luật **[H], gốc: định lý Noether**

**(a) Quét đối xứng.** Với hệ và trường lực đang xét, kiểm ba phép biến đổi:

| Phép biến đổi | Nếu hệ bất biến ⇒ bảo toàn |
|---|---|
| Dịch chuyển theo phương e | Động lượng thành phần P_e |
| Quay quanh trục e | Momen xung lượng thành phần L_e |
| Dịch chuyển thời gian (không có ràng buộc/lực phụ thuộc t tường minh) | Năng lượng E (hoặc hàm Jacobi h nếu ràng buộc phụ thuộc t) |

**Cách kiểm cụ thể:** thế năng U và ràng buộc **có đổi khi dịch chuyển / quay / dịch thời gian không?** Đây chính là "Suf" hiệu quả nhất và nhanh nhất cho C1, C4, C7.

**(b) Chọn công cụ khi có nhiều ứng viên (ba câu hỏi) [H]:**

| Câu hỏi | Trả lời | Ưu tiên |
|---|---|---|
| Có cần **thời gian**? | Không | C3/C4 (nối trạng thái) |
| Có **xung/va chạm/sự kiện đột ngột**? | Có | C6 với C1, C7 theo phương không có xung ngoại |
| Lực nào **chưa biết và cần tìm**? | Lực tức thời | D1 tại đúng thời điểm đó |
| Quan tâm **chuyển động khối tâm** hay **dịch chuyển tổng thể**? | Có | C2 |
| Có **lực xuyên tâm** hoặc điểm O đặc biệt? | Có | C7 |
| Có **ràng buộc phụ thuộc thời gian**? | Có | P6: chọn Σ chứa nó; E của Σ bảo toàn, E từng vật thì không |

**(c) Chuỗi công cụ thường gặp:** C6 → C4 → D6 (đạn–con lắc); C7 → C4 (quỹ đạo Kepler); C1 + C4 (nêm và vật: hai phương trình cho hai vận tốc); D1 → K2 → C4 (từ lực đến năng lượng).

**(d) Xấp xỉ bảo toàn và sai số Err:** ε_p ≈ |xung ngoại|/|Δp_nội|; ε_E ≈ |A_nt|/E. Ghi Err khi dùng "xấp xỉ bảo toàn".

---

### C9. Lagrange (phiên bản rút gọn) **[EXT]**

- **Khi nào dùng:** Nhiều tọa độ, ràng buộc phức tạp, phản lực khó triệt bằng công cụ cơ bản. Đây là công cụ "hạng nặng hợp pháp" nhưng **không thuộc nền tảng** (syllabus IPhO không yêu cầu). Nếu hai cách cùng cho kết quả, hãy ưu tiên cách cơ bản vì trình bày dễ kiểm chứng. **[?]**
- **Nội dung:**
  - L = T − U; **d/dt(∂L/∂q̇) − ∂L/∂q = Q** (Q là lực suy rộng của lực **không thế**).
  - **Tọa độ cyclic** (∂L/∂q = 0) ⇒ p_q = ∂L/∂q̇ = hằng (tổng quát của bảo toàn động lượng, momen xung lượng).
  - h = Σq̇∂L/∂q̇ − L bảo toàn nếu L không phụ thuộc t tường minh.
- **Pre:** Ràng buộc holonomic, lý tưởng (phản lực không sinh công ảo).
- **Trình tự cố định ALG-C9:** (1) Chọn f tọa độ độc lập (K7: f = 2N − #ràng buộc); (2) viết T, U theo q, q̇; (3) L; (4) phương trình E–L; (5) tuyến tính hóa (O4).
- **Đã kiểm:** Hạt trên vòng quay: L = ½mR²(θ̇² + ω²sin²θ) + mgR cosθ ⇒ θ̈ = sinθ(ω²cosθ − g/R), khớp D10.
- **Bẫy:** T sai (quên nêm chuyển động); bỏ lực không thế; quên rằng khi ràng buộc phụ thuộc t thì h **không** bằng E.

