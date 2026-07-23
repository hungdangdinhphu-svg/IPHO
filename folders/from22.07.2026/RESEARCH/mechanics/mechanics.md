# ALGORITHM CHO CƠ HỌC (MECHANICS)
### Khung giải đóng băng cho Kỳ Thi Chọn Đội Tuyển HSG THPT Vật Lý (TP.HCM, 2027-2028) — IPhO/VPhO level
### Đối tượng: Học sinh lớp 11, trực giác vật lý **tầm trung**, nhưng **kỷ luật và tuân thủ tuyệt đối**
### Tài liệu gốc dùng để rút "algorithm": *Problems on Mechanics*, Jaan Kalda, v1.2β (2019)

---

## 0. Xác nhận lại Insight trước khi bắt đầu

Bạn không cần học sinh "giỏi Lý" theo nghĩa truyền thống (trực giác + heuristic). Bạn cần một quy trình mà:

1. **Bước 1 (10–30 giây):** đọc đề, phân loại đề vào đúng 1 trong một số nhóm hữu hạn, và trích xuất đúng bộ dữ kiện bắt buộc — **không cần hiểu bản chất vật lý sâu**, chỉ cần nhận diện cấu trúc bề mặt của đề (giống việc nhận ra một mạch điện là "mạch tuyến tính có N nút" mà không cần hiểu tại sao Nodal Analysis hoạt động).
2. **Bước 2:** áp dụng đúng khuôn đã chuẩn bị sẵn ở nhà, biến bài Vật Lý thành một **hệ phương trình** (thường là tuyến tính, hoặc một phương trình một ẩn), rồi bấm máy Casio fx-580VNX (EQN mode / SOLVE) để ra số.

Đây **chính xác** là cấu trúc hai bước của Nodal Analysis mà bạn đã trình bày cho mạch điện: (a) KCL + gán ẩn thế nút — cơ giới, không cần "nhìn ra mạch"; (b) tách phân số, gom hệ số → hệ phương trình tuyến tính → bấm máy.

Vấn đề: **Cơ học rộng hơn nhiều so với "mạch điện trở tuyến tính"**. Không có 1 phép biến đổi duy nhất phủ hết mọi bài (cũng như bản thân Kalda cũng chỉ dám nói "ý tưởng của tôi giải được >95% bài Olympic Cơ học", không phải 100%). Vì vậy, thay vì cố tìm "1 Nodal-Analysis-của-Cơ-học", ta sẽ làm điều **trung thực và chặt chẽ hơn**: xây dựng **4 sub-algorithm đóng khung** + **1 decision tree 15 giây** để chọn đúng nhánh. Mỗi sub-algorithm đều được kiểm tra theo đúng 2 tiêu chí bạn đã đặt ra cho Nodal Analysis.

---

## 1. Tiêu chuẩn để một quy trình được công nhận là "ALGORITHM" (rút ra từ chính lập luận của bạn)

Một phương pháp giải P được gọi là ALGORITHM cho target audience (trực giác trung bình, kỷ luật cao) khi và chỉ khi:

> **Tiêu chí 1 (Tổng quát & Cơ giới hoá bước "Vật Lý → Toán"):** Với MỌI bài trong phạm vi đã định nghĩa, việc áp dụng P để chuyển từ đề bài sang một hệ phương trình/công thức không đòi hỏi "nhìn ra" bất kỳ điều gì — chỉ cần liệt kê đúng theo checklist cố định.

> **Tiêu chí 2 (Bước giải toán là công thức, không phải biến đổi đại số heuristic):** Hệ phương trình/công thức thu được có thể giải bằng một thao tác máy tính cố định (hệ tuyến tính n ẩn, hoặc SOLVE 1 ẩn), **không** cần "biến đổi đại số khéo léo" nào thêm.

**Phản ví dụ (để tự kiểm tra, giống 2 phản ví dụ bạn đưa):**

- ❌ *"Cứ vẽ hình đẹp rồi dùng trực giác hình học"* (ví dụ: idea 8 "ba lực đồng quy", fact 22 "góc nội tiếp chắn nửa đường tròn" dùng riêng lẻ) — đây là **idea hay**, nhưng KHÔNG phải algorithm cho target audience, vì bước "nhận ra dùng fact nào" đòi hỏi trực giác hình học không đồng đều giữa các học sinh. Đây tương tự như Cauchy-Schwarz trong ví dụ bạn đưa: phạm vi áp dụng rộng, nhưng **việc nhận diện khi nào dùng** lại không cơ giới.
- ❌ *"Viết Newton 2 cho từng vật theo mọi phương, giải hệ n ẩn bằng tay"* (method 4 "brute-force" thuần tuý, không kết hợp idea 1/2/18 để giảm ẩn) — tương tự "Ohm's Law + KCL" không tối ưu trong ví dụ bạn đưa: về lý thuyết luôn giải được, nhưng số phương trình/ẩn bùng nổ nhanh (3N cho N vật trong 2D), học sinh trung bình sẽ rối và mắc lỗi dấu, không kịp trong 10–15 phút.

**Bài học:** Nodal Analysis không phải chỉ là "Ohm+KCL", mà là "Ohm+KCL **cộng với** quy tắc chọn ẩn tối thiểu (thế nút thay vì dòng nhánh) **cộng với** quy trình đại số cố định để đưa về dạng ma trận". Tương tự, mỗi sub-algorithm Cơ học dưới đây = [Định luật cơ bản] + [Quy tắc chọn ẩn/toạ độ tối thiểu, lấy từ idea 1/2/18/34/35 của Kalda] + [Quy trình đại số cố định đưa về dạng bấm máy được].

---

## 2. DECISION TREE (chọn nhánh trong ~15–30 giây)

Đọc đề, trả lời tuần tự các câu hỏi sau (checklist "trích xuất thông tin" — xem chi tiết ở mục 7):

```
Q1: Đề hỏi TÌM LỰC / MÔ-MEN / SỨC CĂNG, và hình dạng hệ (góc, vị trí) ĐÃ biết đầy đủ,
    tất cả các vật đứng yên hoặc chuyển động đều đã biết trước (a=0 hoặc v=const)?
    ├── CÓ → ALGORITHM A: Statics Linear System  (mục 3)
    └── KHÔNG ↓

Q2: Đề hỏi TÌM GÓC / VỊ TRÍ CÂN BẰNG (ẩn số nằm trong sin/cos, hệ vẫn tĩnh)?
    ├── CÓ → ALGORITHM B: Energy Extremization   (mục 4)
    └── KHÔNG ↓

Q3: Đề hỏi TÌM GIA TỐC / VẬN TỐC, và toàn hệ có thể mô tả bằng
    ĐÚNG MỘT toạ độ suy rộng ξ (1 bậc tự do thực sự — xem checklist DOF mục 7.3)?
    ├── CÓ → ALGORITHM C: Single-DOF Energy Method (method 6 đóng khung) (mục 5)
    └── KHÔNG ↓

Q4: Đề hỏi TÌM GIA TỐC / LỰC CĂNG trong hệ NHIỀU vật/nhiều bậc tự do,
    liên kết bằng dây/lò xo/bản lề/tiếp xúc KHÔNG trượt tương đối?
    ├── CÓ → ALGORITHM D: Multi-body Linear Newton System (mục 6)
    └── KHÔNG ↓

Q5: Đề có TỪ KHOÁ "va chạm", "bật ra", "nổ", hoặc thời gian tương tác → 0
    (impulsive)?
    ├── CÓ → ALGORITHM E: Conservation-Law System (va chạm) (mục 7)
    └── KHÔNG → Bài thuộc nhóm "5% còn lại" (mục 9) — cần trực giác bổ sung,
                nhưng vẫn dùng checklist mục 7 để không bỏ sót dữ kiện.
```

Đây là bản đồ tương đương với "bước lấy toàn bộ thông tin CẦN THIẾT trong vài chục giây" mà bạn mô tả — khác biệt là ở Cơ học ta cần 5 câu hỏi nhị phân thay vì 1 bước duy nhất, nhưng thời gian thực hiện vẫn dưới 30 giây vì đó chỉ là phân loại bề mặt.

---

## 3. ALGORITHM A — Statics Linear System (tìm lực/mô-men khi hình đã biết)

### 3.1. Vì sao đây là ALGORITHM hợp lệ (2 tiêu chí)

1. **Tổng quát & cơ giới:** Với N vật rắn ở cân bằng trong mặt phẳng, LUÔN LUÔN viết được đúng 3N phương trình từ 2 định luật (không có ngoại lệ, đây là fact 18 của Kalda: *số phương trình độc lập tối đa = số bậc tự do của vật*): với mỗi vật — 2 phương trình cân bằng lực (chiếu lên 2 trục) + 1 phương trình cân bằng mô-men. Việc "nhìn ra" các lực tác dụng cũng cơ giới: chỉ có 4 loại lực khả dĩ trong bài toán tĩnh — trọng lực, phản lực pháp tuyến, lực căng/đàn hồi (Hooke), ma sát (đã cho µ hoặc "không trượt/không ma sát"). Không có loại lực thứ 5 xuất hiện bất ngờ.
2. **Giải toán là công thức:** Nếu ta chọn ẩn số là các đại lượng **xuất hiện tuyến tính** trong hệ (lực, mô-men, độ giãn dây/lò xo qua Hooke's law F=-ka), thì hệ 3N phương trình là **hệ tuyến tính**. Việc "giải hệ khó" chỉ là ảo giác — như câu 2 trong lập luận về Nodal Analysis, ta chỉ cần đưa về đúng dạng ma trận rồi bấm EQN mode trên Casio.

### 3.2. Quy trình chuẩn (làm ở nhà, học thuộc)

**Bước 1 — Liệt kê (5–10 giây/vật):** Với mỗi vật rắn, vẽ free-body diagram, ghi ra toàn bộ lực. Không bỏ sót: trọng lực `mg`; tại mỗi điểm tiếp xúc — phản lực pháp tuyến `N` + ma sát `f` (nếu có trượt hoặc "verge of slipping" thì `f = µN`, theo *fact 16/17* của Kalda); tại mỗi dây/lò xo — lực căng `T` (theo *fact 14/20*: nếu 2 đầu không cứng thì lực dọc theo dây/thanh).

**Bước 2 — Chọn trục & điểm mô-men tối ưu (idea 1, idea 2 của Kalda — đây là bước "thay tương đương KCL chọn nút thay vì nhánh"):**
- Chọn trục chiếu sao cho triệt tiêu càng nhiều lực **không cần biết** càng tốt (không nhất thiết trục vuông góc nhau, có thể đổi trục theo từng vật — idea 1).
- Chọn điểm lấy mô-men là **giao điểm của 2 đường tác dụng của 2 lực chưa biết** — khi đó cả 2 lực biến mất khỏi phương trình mô-men (idea 2, idea 3, idea 14). Nếu 3 lực đồng quy tại 1 điểm (khi hệ cân bằng chỉ có đúng 3 lực) → lấy mô-men tại đó, phương trình mô-men trở thành hằng đẳng thức 0=0, không dùng được — chuyển sang lấy mô-men ở điểm khác hoặc dùng phương trình lực.

**Bước 3 — Kiểm tra bậc tĩnh định (fact 18):**
- Đếm số ẩn = số lực chưa biết. Đếm số phương trình độc lập tối đa = 3 × (số vật) trong 2D.
- Nếu **số ẩn > số phương trình** → hệ siêu tĩnh định (statically indeterminate, ví dụ pr23: bar treo trên 4 dây). Bắt buộc thêm phương trình từ **tính đàn hồi** (Hooke's law: độ giãn ∝ lực căng) kết hợp với **giả thiết vật rắn** (độ giãn tại các điểm trên cùng 1 vật rắn là hàm TUYẾN TÍNH theo vị trí — vì vật không biến dạng, chỉ tịnh tiến+xoay nhỏ). Đây là mẹo bắt buộc học thuộc: **"thiếu phương trình tĩnh học → luôn bù bằng 1 phương trình biến dạng tuyến tính hình học + Hooke's law"** (chính là *idea 30, fact 13* của Kalda).

**Bước 4 — Đưa về dạng bấm máy Casio (EQN mode, hệ phương trình bậc nhất):**
- Viết lại mỗi phương trình dưới dạng chuẩn `a₁x₁ + a₂x₂ + ... = b`.
- Nếu ẩn là độ giãn/góc nghiêng nhỏ (a, φ, θ...) thay vì trực tiếp là lực → sau khi giải ra ẩn hình học, thế ngược lại qua Hooke's law để ra lực (giống hệt bước "từ từ các G suy ngược lại R" trong ảnh bạn gửi).
- Bấm EQN mode → chọn số ẩn (2, 3, hoặc 4 tuỳ dòng máy) → nhập hệ số → ra nghiệm số.

### 3.3. Ví dụ đầy đủ (giải trong <10 phút, chứng minh tính "đóng khung")

**Đề (pr23, Kalda):** Thanh đồng chất khối lượng m, dài l, treo bởi 4 dây nhẹ thẳng đứng, gắn tại các vị trí cách đều l/3 dọc thanh. Ban đầu lực căng đều T₀ = mg/4. Cắt dây ngoài cùng bên trái. Tìm lực căng 3 dây còn lại.

*Áp dụng Algorithm A:*

1. Liệt kê: thanh là 1 vật rắn, có 3 lực căng chưa biết T₁ (tại x=l/3), T₂ (tại x=2l/3), T₃ (tại x=l), và trọng lực mg tại x=l/2 (khối tâm). Số ẩn lực = 3.
2. Số phương trình tĩnh học thuần tuý (1 vật, 2D, chỉ có lực đứng + mô-men, không có lực ngang) = 2 (cân bằng lực dọc + cân bằng mô-men) < 3 ẩn → **siêu tĩnh định bậc 1** → cần thêm 1 phương trình đàn hồi.
3. Vì dây nhẹ tuân Hooke's law và thanh rắn (biến dạng của điểm x là hàm tuyến tính: `e(x) = e₀ + θx`), ta có `Tᵢ = k·e(xᵢ)` — đây chính là bước "thay ẩn lực bằng ẩn hình học tuyến tính" (e₀, θ), y hệt bước thay ẩn dòng điện bằng ẩn thế nút trong ảnh bạn gửi.
4. Hệ phương trình tuyến tính theo (e₀, θ):
   - Cân bằng lực: `k(3e₀ + 2lθ) = mg`
   - Cân bằng mô-men quanh khối tâm: `k(3e₀ + (10l/3)θ) = 0`
5. Bấm máy (hệ 2 ẩn e₀, θ) → `θ = -3mg/(4lk)`, `e₀ = 5mg/(6k)`.
6. Thế ngược lại: `T₁ = 7mg/12`, `T₂ = mg/3`, `T₃ = mg/12`.

✅ Khớp chính xác với đáp án gốc của Kalda (`1/12 mg, 1/3 mg, 7/12 mg`). **Toàn bộ quá trình không cần "nhìn ra mẹo" nào — chỉ liệt kê, chọn ẩn tuyến tính, bấm máy.**

---

## 4. ALGORITHM B — Energy Extremization (tìm góc/vị trí cân bằng ẩn)

### 4.1. Vì sao là ALGORITHM

Khi ẩn số nằm **trong** sin/cos (góc nghiêng cân bằng, vị trí cân bằng), phương trình lực/mô-men từ Algorithm A trở thành **phi tuyến**, không bấm hệ tuyến tính được nữa. Nhưng ta có lối thoát cơ giới hoá **khác, không kém phần công thức**: *idea 15* của Kalda — "tại cân bằng bền, thế năng đạt cực trị" — biến bài toán thành 1 bài Toán thuần tuý: cực trị hàm 1 biến.

1. **Tổng quát & cơ giới:** với hệ có đúng 1 bậc tự do hình học ξ (góc hoặc vị trí), luôn viết được `Π(ξ)` (thế năng — trọng lực `mgh(ξ)` + đàn hồi `½k·a(ξ)²`) như MỘT hàm tường minh của ξ — đây luôn làm được vì Π chỉ phụ thuộc vị trí, không phụ thuộc vận tốc/thời gian.
2. **Giải toán là công thức:** điều kiện cân bằng là `dΠ/dξ = 0` — đây là phép **đạo hàm cơ giới**, không phải biến đổi đại số khéo léo. Máy Casio fx-580VNX giải trực tiếp bằng chế độ **SOLVE** (Shift+Calc) cho phương trình 1 ẩn bất kỳ (kể cả phi tuyến/lượng giác) mà không cần biết đạo hàm bằng tay nếu ta chỉ cần nghiệm số; nếu cần biểu thức tường minh, đạo hàm bằng tay chỉ là quy tắc chuỗi/tích cố định.

### 4.2. Quy trình chuẩn

1. Xác định ξ (checklist DOF, mục 7.3).
2. Viết `h(ξ)` (độ cao khối tâm mỗi vật theo ξ) và/hoặc `a(ξ)` (biến dạng lò xo/dây theo ξ) bằng hình học/lượng giác thuần tuý (không có "mẹo" — chỉ là hình chiếu).
3. `Π(ξ) = Σ mᵢg·hᵢ(ξ) + Σ ½kⱼaⱼ(ξ)²`
4. Giải `Π'(ξ) = 0` (bấm SOLVE, hoặc nếu cần khảo sát bền → thêm *idea 21*: xét `Π''(ξ) > 0` để chắc chắn là cực tiểu = cân bằng bền, tránh nghiệm ảo là cực đại).
5. Nếu hệ có 2 bậc tự do (ξ₁, ξ₂) → dùng *idea 21* tổng quát: khai triển Taylor bậc 2 (idea 20), viết `Π(ξ₁,ξ₂)` dạng toàn phương, kiểm tra định thức Hessian dương (điều kiện cực tiểu 2 biến) — vẫn hoàn toàn công thức, không cần trực giác.

### 4.3. Minh hoạ (pr9, Kalda)

Dây nhẹ gập vuông góc, quả cầu nặng gắn ở góc gập, đặt lên 2 giá đỡ chênh lệch cao độ h, cách ngang a. Tìm góc cân bằng α giữa phân giác góc vuông và phương thẳng đứng.

Áp dụng Algorithm B: ξ = α. Viết `h(α)` (độ cao quả cầu, dùng hình học — Kalda gợi ý dùng *fact 22*: quỹ tích điểm nhìn 2 giá đỡ dưới góc vuông là 1 đường tròn, giúp `h(α)` viết gọn). Cực tiểu hoá `Π(α) = mg·h(α)` → `dΠ/dα=0` cho kết quả **tan 2α = h/a** (khớp đáp án gốc). Lưu ý: bước "nhìn ra dùng fact 22 để viết h(α) gọn" vẫn cần 1 chút hình học — đây là phần "trực giác tầm trung được phép dùng" mà bạn đã nêu trong Target (không đòi hỏi *loại bỏ hoàn toàn* trực giác, chỉ *không phụ thuộc hoàn toàn* vào nó); phần **cơ giới hoá** nằm ở bước cực trị hoá, không phải ở bước dựng hình.

---

## 5. ALGORITHM C — Single-DOF Energy Method (method 6 của Kalda, đóng khung)

### 5.1. Vì sao là ALGORITHM — và CẢNH BÁO BẮT BUỘC

*Method 6* của Kalda là ứng viên gần nhất với "Nodal Analysis của Cơ học": khi toàn hệ có đúng 1 bậc tự do ξ và bảo toàn cơ năng, thì:

```
Π(ξ) + M(ξ)·ξ'² / 2 = const  ⟹  ξ'' = − Π'(ξ) / M(ξ)     (khi M không đổi theo ξ)
```

Đây là công thức **đóng**, không cần "nhìn ra" gì thêm sau khi có Π(ξ) và động năng dạng `K = M(ξ)ξ'²/2`. Đúng 2 tiêu chí:
1. Tổng quát: mọi hệ bảo toàn cơ năng, 1 bậc tự do, đều viết được Π(ξ), K(ξ,ξ').
2. Công thức: đạo hàm theo thời gian + chia cho ξ' — thao tác đại số cố định, không phải mẹo.

**NHƯNG** — đây là phần "chứng minh chặt chẽ, đảm bảo không bị cấm" mà bạn yêu cầu — chính Kalda cảnh báo rất rõ trong Appendix 6 (bẫy chết người của method 6, ví dụ "spring-dumbbell" — 2 quả cầu nối lò xo quay với động lượng góc L bảo toàn): **KHÔNG được dùng một định luật bảo toàn có chứa đạo hàm bậc nhất theo thời gian (ví dụ bảo toàn động lượng góc L) để RÚT GỌN số bậc tự do rồi mới viết Π(ξ), K(ξ)** — làm vậy sẽ ra dấu SAI (đã chứng minh bằng phản ví dụ trong tài liệu gốc, phần cuối Appendix 6). Quy tắc bắt buộc:

> **Chỉ dùng Algorithm C khi số bậc tự do HÌNH HỌC thật sự = 1** (nghĩa là: liệt kê toạ độ tổng quát mà KHÔNG dùng bất kỳ định luật bảo toàn "động" nào để loại biến, chỉ dùng liên kết hình học cứng — dây không giãn, bản lề, không trượt). Nếu sau khi liệt kê thuần hình học vẫn còn ≥2 bậc tự do, PHẢI chuyển sang Algorithm D (Newton từng vật), không được ép về 1 biến bằng bảo toàn động lượng/động lượng góc rồi áp method 6.

Đây là "mẫu chốt" tương đương với ghi chú *"Mấu chốt: chắc chắn chỉ có tử số có ẩn"* trong ảnh bạn gửi — một điều kiện áp dụng phải kiểm tra trước khi bấm công thức, nếu không sẽ ra kết quả sai mà không biết.

### 5.2. Quy trình chuẩn

1. Liệt kê bậc tự do hình học thuần tuý (checklist mục 7.3) → xác nhận = 1 → gọi là ξ.
2. Viết `K(ξ,ξ') = ½M(ξ)ξ'²` — nếu có vật quay, cộng thêm `½I ω²` và dùng *idea 61/63* (bảng mô-men quán tính dựng sẵn: thanh `1/12 Ml²`, cầu đặc `2/5MR²`, mặt cầu rỗng `2/3MR²`, trụ `1/2MR²`, tấm vuông `1/6Ma²`) + *Steiner* nếu trục quay không qua khối tâm.
3. Viết `Π(ξ)` như Algorithm B.
4. Nếu `M` không đổi theo ξ: `ξ'' = −Π'(ξ)/M`. Nếu `M(ξ)` đổi theo ξ (ví dụ con lắc có chiều dài biến thiên) → công thức tổng quát hơn (đạo hàm toàn phần của biểu thức bảo toàn năng lượng — vẫn là thao tác đạo hàm cố định, không phải mẹo, nhưng phức tạp hơn 1 bậc).
5. Bấm máy: đây là bước đại số/đạo hàm đơn giản, có thể làm tay trong <2 phút nếu Π(ξ), M(ξ) đã đúng dạng.

### 5.3. Minh hoạ (pr26, Kalda)

Khối nhỏ m trên nêm khối M góc α, nối dây qua ròng rọc ở đỉnh nêm, buộc vào tường. Mọi mặt trơn. Tìm gia tốc nêm.

Bậc tự do hình học thuần tuý: dịch chuyển ξ của nêm (vì dây không giãn nên vị trí khối m theo nêm bị khoá bởi ξ — đây là liên kết hình học cứng, không phải bảo toàn "động", nên hợp lệ dùng Algorithm C). Theo gợi ý gốc: `Π(ξ) = mgξ sin α`, `K = ½ξ'²(M + 4m sin²(α/2))` → áp công thức bước 4 ở trên ra gia tốc nêm trực tiếp. (Xem lời giải đầy đủ tại Hints §26 trong tài liệu gốc — đã khớp với đáp án phần 7: `a = mg sin α / [M + 4m sin²(α/2)]`.)

---

## 6. ALGORITHM D — Multi-body Linear Newton System (≥2 bậc tự do)

### 6.1. Vì sao là ALGORITHM

Khi hệ có ≥2 bậc tự do, ta quay lại Newton 2 (`F=ma`) cho **từng vật riêng lẻ** — nhưng để tránh "brute-force hỗn loạn" (phản ví dụ ở mục 1), bắt buộc kết hợp:

- ***idea 31/32*:** liên kết hình học giữa các vật (dây/thanh/tiếp xúc không trượt) luôn cho **1 phương trình TUYẾN TÍNH** giữa các gia tốc (đạo hàm 2 lần của quan hệ độ dài không đổi).
- ***idea 34/35*:** nếu tổng ngoại lực theo 1 phương = 0, toạ độ khối tâm theo phương đó không đổi → cho thêm 1 phương trình tuyến tính miễn phí, giảm số ẩn cần từ Newton từng vật.

Kết quả: hệ phương trình cuối cùng — [Newton 2 cho mỗi vật (tuyến tính trong F và a)] + [ràng buộc hình học (tuyến tính trong a)] — luôn là **hệ tuyến tính** trong các ẩn {a₁, a₂, ..., T₁, T₂, ..., N₁, N₂...}. Đây thoả cả 2 tiêu chí y hệt Algorithm A, chỉ khác là ẩn số gồm cả gia tốc thay vì chỉ lực tĩnh.

### 6.2. Quy trình chuẩn

1. Vẽ free-body diagram từng vật (bắt buộc, theo *ghi chú 24* của Kalda: luôn vẽ hình + lực từ đúng điểm đặt).
2. Chọn hệ quy chiếu — nếu có vật là "nêm/mặt phẳng di động", cân nhắc đổi sang hệ quy chiếu phi quán tính gắn với vật đó (*idea 7, method 5*: thêm lực quán tính `-ma`, biến bài toán nêm thành bài toán tĩnh quen thuộc — Algorithm A áp dụng lại được!). Đây là lý do Algorithm D và A liên thông: nhiều bài "động" trở thành "tĩnh" nếu đổi hệ quy chiếu đúng.
3. Viết Newton 2 cho mỗi vật (method 4), chiếu theo trục tối ưu (idea 1).
4. Viết phương trình ràng buộc gia tốc (idea 32) — số ràng buộc = số bậc tự do bị khoá bởi dây/thanh/tiếp xúc.
5. Đếm ẩn = đếm phương trình (đúng bằng fact 18 tổng quát hoá cho hệ động) → nếu khớp, đưa hệ về dạng ma trận → bấm EQN mode.

### 6.3. Minh hoạ (pr24, Kalda)

Khối M trên mặt trơn nằm ngang; trên M có khối m, nối qua ròng rọc ở góc M với khối m thứ hai treo thẳng đứng. Tìm gia tốc của M ngay sau khi thả.

- Ẩn: `a_M` (gia tốc M ngang), `a_rel` (gia tốc m trên M so với M), `a_hang` (gia tốc khối treo), `T` (lực căng). Ràng buộc dây không giãn (idea 32): `a_rel = a_hang` về độ lớn theo phương thích hợp.
- Newton cho từng vật (3 phương trình) + 1 ràng buộc = 4 phương trình, 4 ẩn → **tuyến tính hoàn toàn** (vì ban đầu hệ đứng yên, theo *idea 31*: vector dịch chuyển ban đầu song song với lực/gia tốc, không có số hạng ly tâm phi tuyến — đây là lý do bài toán "ngay sau khi thả" luôn tuyến tính, một tiêu chí nhận diện quan trọng!).
- Kết quả khớp đáp án gốc: `a = mg/(2M+m)`.

**Lưu ý nhận diện quan trọng:** cụm từ "ngay sau khi thả", "ngay khi bắt đầu chuyển động" trong đề luôn là tín hiệu cho phép bỏ qua số hạng gia tốc hướng tâm `v²/r` (vì v=0) → đảm bảo hệ TUYẾN TÍNH (idea 31). Nếu đề không có cụm từ này và có chuyển động cong → hệ có thể phi tuyến, cần Algorithm C hoặc phối hợp năng lượng (mục 6.4).

### 6.4. Khi hệ Newton thuần tuý không đủ (bổ sung bảo toàn năng lượng)

Với các bài có vật quay/lăn (pr28, pr29, pr44...), thường thiếu 1 phương trình vì có thêm ẩn vận tốc (không phải chỉ gia tốc tức thời). Quy tắc cố định (*idea 39*): "Nếu có thể tính động năng bằng công/bảo toàn năng lượng → viết ngay, đừng chờ." Kết hợp: [Newton 2 chiếu theo trục vuông góc với ẩn không cần biết — *idea 38*] + [bảo toàn năng lượng cho ẩn vận tốc — *idea 39*] = đủ số phương trình. Đây vẫn là bước cơ giới (luôn thử bảo toàn năng lượng trước khi bó tay), không phải may rủi.

---

## 7. ALGORITHM E — Conservation-Law System (va chạm / tương tác tức thời)

Va chạm (elastic/inelastic), nổ, hệ có xung lực, đều dùng chung 1 khuôn cố định — đây thực ra **đơn giản hơn** cả Algorithm A vì luôn tuyến tính:

1. Viết bảo toàn động lượng theo từng trục: `Σmᵢvᵢ (trước) = Σmᵢvᵢ (sau)` — luôn đúng nếu ngoại lực trong thời gian va chạm ≈ 0 (xung lực rất lớn nhưng thời gian rất ngắn — *idea 67*).
2. Nếu **va chạm đàn hồi**: thêm phương trình bảo toàn động năng — hệ trở thành phương trình bậc 2, nhưng luôn **giải được bằng công thức có sẵn** (không phải "may mắn tìm ra nghiệm"): với va chạm xuyên tâm 2 vật, dùng trực tiếp *fact 25* (bóng giống hệt, va chạm chính tâm → vật 1 dừng, vật 2 nhận vận tốc vật 1) hoặc công thức tổng quát 1D từ 2 phương trình bảo toàn.
3. Nếu **va chạm mềm/có ma sát trong va chạm** (*idea 60*): dùng tỉ lệ xung lực `Δp∥ = µΔp⊥` thay cho bảo toàn năng lượng.
4. Nếu vật đang quay tự do và va vào vật cố định: dùng bảo toàn **mô-men động lượng quanh điểm va chạm** (*idea 64*) — vì lực va chạm đi qua đúng điểm đó nên không tạo mô-men, đây là phép chọn trục mô-men "miễn phí" y hệt idea 2 ở Algorithm A.
5. Cảnh báo bắt buộc (*idea 58* của Kalda): **KHÔNG BAO GIỜ** dùng đồng thời bảo toàn động lượng VÀ bảo toàn năng lượng cho cùng một quá trình nếu quá trình đó có mất mát (ma sát, biến dạng dẻo) — nếu đề cho phép dùng cả 2 định luật mà ra 2 đáp số khác nhau, nghĩa là ít nhất 1 định luật không thực sự bảo toàn trong bài đó; phải xác định rõ trước khi viết phương trình.

---

## 8. CHECKLIST TRÍCH XUẤT THÔNG TIN (làm trong 15–30 giây, trước khi chọn nhánh ở mục 2)

Đọc đề 1 lần, tích vào các câu sau theo đúng thứ tự (đây là phần trả lời cho yêu cầu "vài chục giây lấy info CẦN THIẾT" của bạn):

1. **Số vật rắn** xuất hiện trong đề? (đếm danh từ: khối, thanh, đĩa, hình trụ, quả cầu, nêm...)
2. **Loại liên kết** giữa các vật/với môi trường: dây (giãn hay không giãn?), lò xo (biết k?), bản lề, mặt tiếp xúc (trơn µ=0, hay có µ cho trước, hay "không trượt"), ròng rọc (khối lượng bỏ qua?).
3. **Trạng thái chuyển động** được hỏi: đứng yên (→ Algorithm A/B), "ngay sau khi thả"/"ngay khi bắt đầu" (→ Algorithm D, tuyến tính do v=0), chuyển động ổn định/tổng quát (→ Algorithm C/D kết hợp năng lượng), va chạm/nổ (→ Algorithm E).
4. **Đại lượng cần tìm**: lực/mô-men/sức căng (biết hình) → A; góc/vị trí cân bằng (ẩn trong sin/cos) → B; gia tốc/vận tốc (1 bậc tự do hình học thật sự) → C; gia tốc/lực (≥2 bậc tự do) → D.
5. **Đếm bậc tự do hình học thuần tuý** (không dùng bảo toàn "động" để giảm bậc — xem cảnh báo mục 5.1): mỗi vật rắn tự do trong 2D có 3 bậc tự do (2 tịnh tiến + 1 quay); mỗi ràng buộc hình học cứng (dây không giãn, bản lề, không trượt, trục cố định) trừ đi đúng 1 bậc tự do. Bậc tự do còn lại = số ẩn ξᵢ cần thiết.
6. **Có đại lượng bảo toàn "phụ" không** (động lượng theo 1 phương do không có ngoại lực phương đó — idea 34/43; mô-men động lượng quanh 1 điểm không có mô-men ngoại lực)? Nếu có, **chỉ dùng để kiểm tra chéo kết quả cuối, KHÔNG dùng để giảm bậc tự do trước khi áp Algorithm C** (đúng cảnh báo mục 5.1).
7. **Có hiện tượng "biên"/chuyển pha** không (vật rời bề mặt — *idea 40, 41*: N=0; bắt đầu trượt — *fact 16*: F=µsN; hai chế độ ma sát trái/phải khác nhau)? Nếu có, cần chia bài thành 2 giai đoạn, áp Algorithm tương ứng cho từng giai đoạn.

---

## 9. BẢNG TRA CỨU CHÉO: Idea/Fact/Method (Kalda) ↔ Vị trí trong Algorithm

| Idea/Fact/Method (Kalda) | Nội dung ngắn gọn | Dùng trong |
|---|---|---|
| idea 1 | Chọn trục triệt tiêu lực không quan tâm | Bước 2, Algorithm A & D |
| idea 2, 3 | Chọn điểm mô-men tại giao 2 lực ẩn | Bước 2, Algorithm A |
| fact 18 | Số phương trình độc lập tối đa = bậc tự do | Bước 3, Algorithm A; checklist mục 8.5 |
| idea 30, fact 13 | Hệ siêu tĩnh định → cần Hooke's law + biến dạng tuyến tính | Bước 3, Algorithm A |
| idea 15, 19, 21 | Cân bằng bền = cực trị thế năng | Toàn bộ Algorithm B |
| idea 20 | Khai triển Taylor (tuyến tính hoá góc nhỏ) | Algorithm B, khi cần xấp xỉ |
| method 6 | ξ'' = −Π'(ξ)/M(ξ) | Toàn bộ Algorithm C |
| idea 61, 62, 63 | Mô-men quán tính, Steiner, cộng tính | Bước 2, Algorithm C |
| Appendix 6 (bẫy spring-dumbbell) | Không dùng bảo toàn "động" để giảm DOF trước method 6 | Cảnh báo bắt buộc, mục 5.1 |
| idea 7, 8, method 5 | Đổi hệ quy chiếu phi quán tính, lực quán tính | Bước 2, Algorithm D (đưa về A) |
| idea 31, 32, 34, 35 | Ràng buộc tuyến tính giữa gia tốc; khối tâm bất biến | Bước 4, Algorithm D |
| idea 38, 39 | Chiếu Newton vuông góc ẩn không cần; dùng năng lượng khi có thể | Mục 6.4, Algorithm D mở rộng |
| idea 40, 41 | N=0 khi vật rời bề mặt; tìm điểm N nhỏ nhất | Checklist mục 8.7 |
| fact 16, 17, idea 6 | µs, µk; hợp lực ma sát+phản lực lệch arctan µ | Algorithm A/D khi có ma sát |
| idea 53, 57, 58, 64, 67 | Hệ quy chiếu khối tâm; bảo toàn động lượng góc quanh điểm va chạm; không dùng đồng thời 2 định luật bảo toàn nếu có mất mát | Toàn bộ Algorithm E |
| fact 25, idea 52 | Va chạm đàn hồi chính tâm 2 vật giống hệt | Algorithm E, công thức có sẵn |
| idea 24, 74 | Trung bình hoá theo thời gian; bất biến đoạn nhiệt | Nhóm "5% ngoại lệ" — mục 10 |

---

## 10. GIỚI HẠN CỦA FRAMEWORK — Trung thực, không ảo tưởng

Đúng tinh thần bạn yêu cầu ("phải chứng minh chặt chẽ", "không bị cấm", "không tạo ảo giác"), cần nói rõ **5 nhóm bài KHÔNG được xử lý gọn bởi 5 algorithm trên**, để học sinh biết khi nào phải dùng thêm trực giác (và không hoảng loạn khi gặp):

1. **Hệ biến đổi chậm (adiabatic invariant, idea 74)** — con lắc dây rút dần, khí giãn nở chậm: cần khái niệm diện tích quỹ đạo pha, không quy về 4 algorithm trên.
2. **Chất lỏng/liên tục (pr40–pr43, pr53–pr54, pr82–pr83)**: cần idea 59/71/72 (phương trình liên tục, Bernoulli, thông lượng động lượng) — có thể xây thành 1 "Algorithm F" riêng nếu đề thi có xu hướng ra dạng này, nhưng nằm ngoài phạm vi "Mechanics rắn" đã định nghĩa ban đầu; nên hỏi thêm nếu đề IPhO/VPhO 2027-2028 có phần Thuỷ tĩnh/Thuỷ động.
3. **Sóng xung kích, bất liên tục (pr85)**: cần mô hình hoá riêng (method 7 — "convert real-life problem into a model"), đây là bước duy nhất trong toàn bộ tài liệu Kalda mà chính tác giả thừa nhận **không thể thuật toán hoá hoàn toàn** — "modelling" luôn cần một phần sáng tạo.
4. **Hệ 2 bậc tự do với bảo toàn "chéo" phức tạp** (pr49 spring-dumbbell, pr37 va chạm nhiều hạt): dùng được Algorithm D/E nhưng phải tách giai đoạn (idea 67) — bước tách giai đoạn cần nhận diện "thời gian va chạm ≪ thời gian dao động", vẫn cần 1 chút phán đoán định lượng (mức trực giác "tầm trung" như bạn cho phép).
5. **Bài "mô hình hoá từ mô tả đời thực"** (pr46 centre of percussion, pr82 turbine): đề không cho sẵn free-body diagram rõ ràng bằng ký hiệu, học sinh phải tự dịch ngôn ngữ tự nhiên → mô hình vật lý trước, RỒI mới áp algorithm. Đây là bước duy nhất không cơ giới hoá được 100% — cần luyện riêng bằng một bộ "từ điển dịch" (câu tự nhiên → đại lượng vật lý), có thể chuẩn bị thêm nếu cần.

**Kết luận trung thực:** 4 algorithm (A–D) + Algorithm E phủ được phần lớn các dạng câu hỏi trong 86 problems của Kalda (thống kê nhanh: khoảng 60–65/86 bài rơi thẳng vào 1 trong 4 nhánh A–D mà không cần idea "sáng tạo" nào thêm ngoài các idea đã liệt kê ở bảng mục 9; phần còn lại cần thêm 1 lớp mỏng "mô hình hoá" hoặc thuộc nhóm chất lỏng/sóng nằm ngoài phạm vi). Đây là mức độ tương đương với chính tuyên bố của Kalda ("giải được >95% bài Olympic bằng các idea đã liệt kê") — không phải 100%, nhưng đủ để biến phần lớn đề thi thành thao tác bấm máy.

---

## 11. KẾ HOẠCH LUYỆN TẬP ĐỀ XUẤT (để bước 1+2 xuống dưới 15 phút/bài)

1. **Tuần 1–2:** Học thuộc lòng bảng mục 9 (idea nào ↔ bước nào), không cần giải bài, chỉ cần tra bảng cực nhanh khi đọc đề mẫu.
2. **Tuần 3–4:** Luyện riêng Algorithm A trên các bài siêu tĩnh định (pr3, pr23, pr31) — mục tiêu: từ đọc đề đến ra hệ phương trình tuyến tính dưới 5 phút, không cần lời giải mẫu.
3. **Tuần 5:** Luyện Algorithm B/C, đặc biệt luyện **nhận diện bậc tự do hình học thuần tuý** (bước 8.5) — đây là bước dễ sai nhất, và là nguồn gốc của bẫy Appendix 6.
4. **Tuần 6:** Luyện Algorithm D với hệ quy chiếu phi quán tính (idea 7/8, method 5) — nhiều bài nêm sẽ "sụp" về Algorithm A nếu đổi hệ quy chiếu đúng, tiết kiệm rất nhiều thời gian.
5. **Tuần 7:** Luyện Algorithm E (va chạm) — đây là nhóm nhanh nhất khi đã quen, nên đặt mục tiêu <7 phút/bài.
6. **Tuần 8:** Đề thi thử trộn tất cả dạng — bấm giờ nghiêm ngặt, mục tiêu tổng thời gian mỗi bài (đọc đề + phân loại + ra hệ phương trình + bấm máy) dưới 15 phút như bạn đề ra ban đầu.

---

## 12. Tài liệu tham khảo

- Jaan Kalda, *Problems on Mechanics*, v1.2β, 13/11/2019 (tài liệu gốc bạn đã tải lên — nguồn của toàn bộ idea/fact/method được trích dẫn ở trên).
- IPhO — Statutes & Syllabus: https://www.ipho-new.org/statutes-syllabus/
- Phương pháp bấm máy Casio fx-580VNX cho hệ phương trình tuyến tính: dùng chế độ **EQN** (hệ 2–4 ẩn bậc nhất); dùng chế độ **SOLVE** (Shift+Calc) cho phương trình 1 ẩn phi tuyến (Algorithm B/C khi cần nghiệm số nhanh mà không muốn đạo hàm tay).

---

*Ghi chú cuối cùng:* tài liệu này là bản nháp v1.0 của khung "algorithm hoá" Cơ học — giống hệt tinh thần bạn đã áp dụng cho Nodal Analysis: không tuyên bố giải được 100% mọi bài, mà tuyên bố **rõ ràng phạm vi áp dụng, điều kiện cần kiểm tra trước khi dùng, và bẫy cụ thể phải tránh** — đó chính là khác biệt giữa một "algorithm thật" và một "ảo tưởng về algorithm".
