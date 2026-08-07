# THUẬT TOÁN TỔNG QUÁT MÔ HÌNH HÓA VẬT LÝ
### Dành cho luyện thi IPhO / VPHO / Đội tuyển HSG Vật Lý — Chuyên đề: **Cơ học** & **Điện – Từ**

> *"Người ra đề có thể đổi cách hỏi, nhưng họ không thể đổi luật của Vũ trụ."*

---

## GHI CHÚ MỞ ĐẦU (đọc trước khi dùng tài liệu)

1. **Về nguồn:** Trong thư mục tải lên chỉ có 2 file — `Elekter.pdf` (Kalda, *Elektri ja magnetismi ülesandeid*, tiếng Estonia) và `meh_ENG2.pdf` (Kalda, *Problems on Mechanics*, tiếng Anh). Không có file `.md` "khung sườn" nào khác được tìm thấy trong hệ thống — có thể bạn quên đính kèm. Vì vậy tài liệu này được **xây dựng lại từ đầu, hoàn chỉnh 100%**, dùng hai file trên làm "Kiến Thức Đã Có" (KTĐC — kho *idea/fact/method* gốc), đối chiếu với **Syllabus IPhO chính thức** (mục Mechanics & Electromagnetic fields, tra cứu trực tiếp từ ipho-new.org) để đảm bảo độ phủ đúng khung thi. Nếu bạn có file gốc khác, gửi lại để tôi hợp nhất.
2. **Cách dùng tài liệu:** Đây không phải là một cuốn "cheat-sheet công thức". Đây là một **hệ điều hành tư duy** (operating system) đặt *phía trên* các công thức. Học sinh phải học **Phần I–II trước tiên**, thuộc lòng nó như một quy trình vận hành, rồi mới học Phần III–IV như "thư viện hàm" được gọi ra từ quy trình đó.
3. **Ký hiệu:** Các mục tham chiếu tới sách Kalda được ghi dạng `[Cơ-idea 19]`, `[Cơ-pr 26]`, `[Đ&T-fact §3.6]`, `[Đ&T-ul 106]`... để bạn tra lại nguyên bản khi cần chi tiết đầy đủ. Nội dung được diễn giải lại bằng ngôn ngữ riêng, không chép nguyên văn.

---

# PHẦN 0 — TRIẾT LÝ NỀN: "NHÀ VẬT LÝ LÝ THUYẾT" THỰC SỰ LÀM GÌ?

## 0.1. Trả lời thẳng câu hỏi triết học của bạn

Không hề có phép màu, và cũng không có "trực giác thiên bẩm bí ẩn" nào cả. Cái mà bạn cảm nhận là "trực giác hiển nhiên, nhẹ nhàng" của một "Nhà Vật Lý Lý Thuyết" thực chất là **một quy trình quyết định (decision procedure) đã được tự động hoá đến mức vô thức**, giống hệt cách một người lái xe thành thạo không còn "nghĩ" về việc đạp côn — không phải vì họ không cần quy trình, mà vì quy trình đã ăn vào phản xạ.

Có **một hệ tri thức logic đằng sau họ**, và hệ đó nhỏ hơn rất nhiều so với "kho đề" mà một học sinh trung bình cố nhồi. Nó gồm ba tầng:

- **Tầng 1 — Luật của Vũ trụ (bất biến, hữu hạn):** Định luật Newton (hoặc dạng suy rộng: bảo toàn động lượng — mô-men động lượng — năng lượng), phương trình Maxwell (hoặc 4 định luật tích phân: Gauss điện, Gauss từ, Ampère, Faraday) + luật cấu thành vật liệu (Hooke, Ohm...). **Không quá 10 phát biểu gốc** cho toàn bộ Cơ + Điện từ cổ điển.
- **Tầng 2 — Ngữ pháp toán học hoá (10 công cụ phổ quát, xem Phần II):** đối xứng, đếm bậc tự do, chọn hệ quy chiếu/gốc toạ độ, biến phân, xấp xỉ, tương tự cấu trúc, chia để trị, giới hạn, thứ nguyên... Đây là phần "dịch" từ tình huống vật lý cụ thể sang một bài toán thuần tuý (đại số / vi phân / hình học).
- **Tầng 3 — Từ điển tra cứu (idea/fact theo từng chủ đề, Phần III–IV):** đây là phần *phái sinh* — mọi "idea" trong sách Kalda thực ra chỉ là **một lần áp dụng cụ thể của Tầng 2 lên Tầng 1** trong một cấu hình hình học nhất định. Học sinh case-by-case học thuộc Tầng 3 mà bỏ qua Tầng 1–2 sẽ sụp đổ ngay khi đề bài đổi hình học. Học sinh học Tầng 1–2 vững thì **tự suy ra được** phần lớn Tầng 3 tại chỗ, và chỉ cần nhớ Tầng 3 như "các ví dụ đã kiểm chứng" chứ không phải "công thức phải nhớ".

**Hệ quả sư phạm quan trọng nhất:** Việc "cày đề" không sai, nhưng **mục đích của việc cày đề phải là luyện Tầng 2 chạy nhanh và chính xác**, KHÔNG phải là ghi nhớ lời giải của Tầng 3. Hai học sinh cày cùng 100 bài, một người luyện đúng Tầng 2 sẽ giải được bài thứ 101 chưa từng gặp; người còn lại thì không. Đó là ranh giới giữa "pattern recognition case-by-case" (nguy hiểm, dễ vỡ) và "tổng quát hoá" (an toàn, mở rộng được).

## 0.2. Định nghĩa "Mô hình hoá"

> **Mô hình hoá vật lý** = ánh xạ một tình huống vật lý (đối tượng, tương tác, ràng buộc, câu hỏi) thành một **bộ ba** (State, Laws, Constraints) sao cho việc tìm câu trả lời trở thành **thuần tuý là giải toán** trên bộ ba đó.

- **State (Trạng thái):** tập hợp tối thiểu các biến số mô tả đầy đủ cấu hình hệ tại một thời điểm — gọi là **toạ độ suy rộng** (generalized coordinates). Số lượng biến này = **số bậc tự do** (DOF).
- **Laws (Luật):** các phương trình gốc (Newton II, Kirchhoff, Gauss...) áp vào State.
- **Constraints (Ràng buộc):** dây không giãn, mặt không thấm, bảo toàn điện tích tại nút, điều kiện biên...

Khi (State, Laws, Constraints) đã viết ra thành phương trình, bài toán vật lý **kết thúc** — phần còn lại (giải hệ, lấy giới hạn, biện luận) là **toán học thuần tuý**, không còn "vật lý" nữa. Sai lầm phổ biến nhất của học sinh trung bình là **nhảy vào giải toán khi State/Laws/Constraints còn mơ hồ**, dẫn đến phương trình sai hoặc thiếu.

---

# PHẦN I — THUẬT TOÁN TỔNG QUÁT (7 BƯỚC), ÁP DỤNG CHO MỌI BÀI CƠ & ĐIỆN-TỪ

Đây là quy trình **bắt buộc chạy trong đầu theo đúng thứ tự** trước khi đặt bút viết phương trình đầu tiên. Với người mới, hãy viết ra giấy nháp từng bước (mất 2–3 phút); khi thành thạo, nó sẽ tự động hoá còn vài giây.

### **BƯỚC 1 — Xác định Hệ và vẽ "biên hệ" (System & Boundary)**
Hệ gồm những vật/điện tích/dòng nào? Cái gì là "trong hệ", cái gì là "ngoại lực/ngoại trường" tác dụng từ ngoài vào? (Việc chọn biên hệ sai là nguồn lỗi số 1 — vd quên một vật, hoặc coi nội lực là ngoại lực.)

### **BƯỚC 2 — Đếm bậc tự do (DOF) và chọn toạ độ suy rộng**
Hỏi: *"Cần bao nhiêu con số độc lập để mô tả trọn vẹn cấu hình hệ ngay bây giờ?"* Đây chính là tổng quát hoá của **`[Cơ-fact 18]`**: số phương trình độc lập tối đa có thể viết = số bậc tự do của hệ. Nếu bạn không biết DOF, bạn không biết mình cần bao nhiêu phương trình, và sẽ hoặc thiếu hoặc thừa (viết phương trình dư — hệ quả tất yếu — luôn phụ thuộc tuyến tính vào các phương trình khác).

*Ví dụ:* một chêm trên sàn trơn + khối trên chêm, đều chuyển động thẳng: DOF = 2 (vị trí chêm, vị trí khối trên chêm). Mạch RLC nối tiếp có 1 nguồn: DOF = 1 (điện tích tụ, hoặc dòng điện).

### **BƯỚC 3 — Quét đối xứng → rút gọn DOF bằng định luật bảo toàn**
Với mỗi phép đối xứng của hệ (tịnh tiến, quay, phản xạ, đổi dấu điện tích/dòng, đổi chiều thời gian...), có MỘT đại lượng bảo toàn tương ứng (đây là bản chất định lý Noether, không cần chứng minh ở mức phổ thông, chỉ cần *nhận diện*):

| Đối xứng của hệ | Đại lượng bảo toàn | Nguồn Kalda |
|---|---|---|
| Không ngoại lực / tổng ngoại lực = 0 theo 1 trục | Động lượng theo trục đó | `[Cơ-idea 43]` |
| Không mô-men ngoại lực quanh 1 trục/điểm | Mô-men động lượng quanh trục/điểm đó | `[Cơ-fact 7]`, `[Cơ-idea 64,66]` |
| Lực bảo toàn, không ma sát/va chạm mềm | Cơ năng | `[Cơ-fact 8]` |
| Hệ có mặt phẳng/trục đối xứng hình học | Một số đại lượng tại các điểm ảnh của nhau bằng nhau (điện thế, vận tốc, lực căng...) | `[Cơ-idea 12]`, `[Đ&T-§1.4 Sümmeetria]` |
| Mạch kín, không tụ | Tổng ∆(dòng nút) = 0 mọi lúc (Kirchhoff I là hệ quả bảo toàn điện tích) | `[Đ&T-§1.2]` |
| Mặt Gauss kín bất kỳ | Thông lượng điện = Q_trong/ε₀ (hệ quả đối xứng cầu/trụ/phẳng cho ra trường đều trên mặt) | `[Đ&T-§3.2]` |
| Không có từ tích | Thông lượng từ qua mặt kín = 0 luôn | `[Đ&T-§4.2]` |

**Đây là bước quan trọng nhất và hay bị bỏ qua nhất.** Một học sinh giỏi luôn tự hỏi: *"Bài này có đối xứng gì mà tôi có thể lợi dụng để KHÔNG phải giải hệ phương trình đầy đủ?"* trước khi lao vào viết Newton II cho từng vật.

### **BƯỚC 4 — Chọn "ngôn ngữ luật" phù hợp nhất với ẩn số cần tìm**
Cùng một hệ có thể mô tả bằng nhiều "ngôn ngữ" luật tương đương — chọn sai ngôn ngữ khiến bài toán dài gấp 10 lần. Bảng quyết định:

| Bạn cần tìm... | Ngôn ngữ tối ưu | Vì sao |
|---|---|---|
| Lực/phản lực/mô-men tại 1 điểm, tại 1 thời điểm | Newton II dạng lực + mô-men (`method 4`) | Trực tiếp nhất |
| Gia tốc khi hệ có ràng buộc, 1 DOF | Năng lượng → đạo hàm theo toạ độ suy rộng (`method 6`, "Lagrangian rút gọn") | Tự động loại bỏ lực liên kết/lực căng không cần biết |
| Lực căng dây/lực liên kết ẩn | Dịch chuyển ảo (`method 1`) hoặc tách hệ con `[Cơ-idea 47]` | Không cần giải toàn hệ |
| Vận tốc cuối, va chạm, nổ, phóng | Bảo toàn động lượng + năng lượng (`idea 39,43,53`) | Không cần biết lực chi tiết trong va chạm |
| Vị trí cân bằng, ổn định | Cực trị thế năng (`idea 15,19,21`) | Không cần viết lực tức thời |
| Trường tĩnh điện/từ với đối xứng cao | Định lý Gauss / Ampère tích phân | Biến tích phân mặt/đường thành đại số |
| Trường không đối xứng, do phân bố điện tích rời rạc | Nguyên lý chồng chất (`superposition`) | Chia nhỏ nguồn, cộng vector/vô hướng |
| Mạch DC tuyến tính phức tạp | Kirchhoff + (Norton/Millman/nút thế) hoặc symmetry | Xem Phần IV.2 |
| Mạch có tụ/cuộn, đáp ứng theo thời gian | Phương trình vi phân bậc 1/2 tuyến tính (τ = RC hoặc L/R; ω = 1/√LC) | Nghiệm mũ/dao động chuẩn |
| Mạch AC ổn định (steady-state) | Phương pháp phức: Z = R, iωL, 1/(iωC) | Biến vi phân thành đại số phức |
| Vật dẫn/điện môi trong trường ngoài | Phương pháp ảnh (image charges) hoặc giả sử trường đều bên trong rồi kiểm tra biên | `[Đ&T-§3.7,3.9]` |

### **BƯỚC 5 — Viết phương trình: dịch Vật lý → Toán học thuần túy**
Tại bước này, **cấm dùng bất kỳ từ vật lý nào nữa** trong lúc thao tác — chỉ còn là đại số/hình học/giải tích. Đếm lại: số phương trình độc lập viết ra phải **bằng đúng** số ẩn số (không hơn không kém — nếu lệch, quay lại Bước 2–3).

### **BƯỚC 6 — Giải bài toán Toán học bằng công cụ thích hợp (xem Phần II mục F, H)**
Tuyến tính hoá nếu có tham số nhỏ (`idea 20` Taylor), tìm nghiệm đối xứng trước, dùng giới hạn đặc biệt để giảm số biến, dùng số phức nếu là dao động điều hoà...

### **BƯỚC 7 — Kiểm chứng ngược (Sanity Check) — bắt buộc, không được bỏ qua**
- Thứ nguyên đúng chưa?
- Trường hợp giới hạn (R→0, R→∞, m→0, t→0, t→∞, µ=0...) có cho kết quả "hiển nhiên đúng" theo trực giác vật lý không?
- Có đối xứng nào của bài toán mà đáp số phải tôn trọng không (vd đổi 2 điện trở giống nhau thì đáp số phải đối xứng theo)?
- Dấu (hướng) có hợp lý không?

> **Ghi nhớ:** Bước 7 chính là thứ phân biệt "Nhà Vật Lý Lý Thuyết" với "máy tính toán": họ luôn nghi ngờ đáp số của chính mình bằng vật lý, không chỉ tin vào đại số.

---

# PHẦN II — MƯỜI TRỤ CỘT CÔNG CỤ TOÁN-HỌC-HOÁ (TOOLKIT PHỔ QUÁT)

Đây là "thư viện hàm" dùng ở Bước 3–6. Mọi `idea` trong Kalda đều quy về một (hoặc vài) trụ cột dưới đây — học kỹ 10 mục này thay vì học rời rạc hàng trăm `idea`.

## II.1 — Đối xứng → Bảo toàn (đã nói ở Bước 3, xem bảng)
**Hệ luỵ mở rộng:** đối xứng còn dùng để **suy ra hình dạng nghiệm** mà không cần giải phương trình, ví dụ: nếu bài toán bất biến khi phản xạ qua 1 mặt phẳng, thì nghiệm (trường, lực, dòng...) tại các điểm đối xứng nhau qua mặt đó phải bằng nhau hoặc đối nhau — đây chính là ý tưởng `[Cơ-idea 11,12]` (thay một vùng "0" bằng chồng chất 2 vùng dấu ngược nhau) và `[Đ&T-§3.9 phương pháp ảnh]`.

## II.2 — Đếm bậc tự do & chọn toạ độ suy rộng tối ưu
Nguyên tắc chọn: toạ độ suy rộng tốt là toạ độ khiến **ràng buộc tự động thoả mãn** (không phải viết thêm phương trình ràng buộc). Ví dụ dây không giãn qua ròng rọc → dùng độ dài dây bị "mất" ở một đầu làm toạ độ chung (`[Cơ-idea 32]`); vật lăn không trượt → dùng góc quay hoặc quãng đường lăn (ràng buộc `v = ωR` tự động đưa vào định nghĩa toạ độ).

## II.3 — Chọn trục chiếu / điểm mô-men để triệt tiêu ẩn không cần biết
Đây là kỹ thuật đại số thuần tuý nhưng cực kỳ mạnh: khi viết cân bằng lực, **chiếu lên trục vuông góc với lực bạn không biết và không cần biết** để nó biến mất khỏi phương trình (`[Cơ-idea 1]`). Khi viết cân bằng mô-men, **chọn điểm đặt là giao điểm của 2 đường tác dụng lực không cần biết** để cả hai cùng biến mất (`[Cơ-idea 2,3,14]`). Đây là lý do "phương trình mô-men" thường mạnh hơn "phương trình lực": nó triệt tiêu được đúng 1 lực bất kỳ (chọn điểm nằm trên đường tác dụng của nó), còn phương trình lực chỉ triệt tiêu được thành phần vuông góc với 1 hướng đã chọn.

## II.4 — Đổi hệ quy chiếu (không quán tính, khối tâm, đồng chuyển động)
Ba loại đổi hệ quy chiếu dùng liên tục:
- **Hệ khối tâm:** động lượng tổng luôn = 0 → đơn giản hoá va chạm, nổ (`[Cơ-idea 53]`).
- **Hệ không quán tính tịnh tiến/quay:** thêm lực quán tính `-ma`, lực ly tâm `mω²r`, lực Coriolis `-2mω×v` (`[Cơ-idea 7,8,9]`). Chọn hệ sao cho vật khảo sát **đứng yên** trong hệ đó → bài toán động lực học biến thành bài toán tĩnh học (dễ hơn nhiều).
- **Hệ đồng chuyển động với sóng/mặt phân cách:** dùng khi khảo sát vận tốc truyền sóng, mạch điện chu kỳ vô hạn, dòng chảy ổn định (`[Cơ-idea 73]`).

## II.5 — Nguyên lý biến phân / dịch chuyển ảo / "Method 6" (Lagrangian rút gọn)

*Note : Khi thi VPhO, nếu dùng Method 6/Lagrange, học sinh bắt buộc phải trình bày cực kỳ chi tiết các bước trung gian, vì nguy cơ bị trừ sạch điểm thành phần là rất cao.

Với hệ **1 bậc tự do** ξ, nếu viết được động năng dạng K = ½M(ξ)ξ̇² và thế năng Π(ξ), thì gia tốc suy rộng:
```
ξ̈ = − Π'(ξ) / M         (khi M không phụ thuộc ξ)
```
suy rộng hơn (khi M phụ thuộc ξ), dùng trực tiếp bảo toàn năng lượng rồi đạo hàm theo t (`[Cơ-method 6]`). Đây là công cụ **mạnh nhất cho bài có ràng buộc phức tạp** (chêm, ròng rọc, con lắc ghép) vì nó **tự động bỏ qua mọi lực liên kết** (phản lực, lực căng dây) — điều mà Newton II theo từng vật không làm được.

Với lực căng/lực liên kết cần tìm tường minh: dùng **dịch chuyển ảo** — cho ẩn số cần tìm "làm việc" một đoạn ảo `Δx`, cân bằng công ảo với biến thiên thế năng: `T = ΔΠ/Δx` (`[Cơ-method 1]`).

**Lưu ý an toàn kỹ thuật (rất hay bị bỏ qua):** không được rút gọn số bậc tự do bằng một *định luật bảo toàn chứa đạo hàm bậc 1* (như bảo toàn mô-men động lượng) rồi áp dụng trực tiếp Method 6 lên toạ độ còn lại — sẽ ra sai dấu (xem phân tích chi tiết cuối `[Cơ-appendix 6]`). Chỉ rút DOF bằng ràng buộc hình học (không chứa đạo hàm) trước khi dùng Method 6.

## II.6 — Xấp xỉ có kiểm soát (Taylor, tuyến tính hoá, nhiễu loạn, bất biến đoạn nhiệt)
- **Taylor bậc 1–2:** khi đề cho "góc nhỏ", "biến dạng nhỏ", "nhiễu loạn nhỏ" → luôn tuyến tính hoá lực/mô-men, hoặc lấy bậc 2 nếu khảo sát năng lượng gần cực trị (ổn định) (`[Cơ-idea 20]`).
- **Nhiễu loạn (perturbation):** giải bài "gốc" (không có nhiễu) trước, sau đó cộng số hạng hiệu chỉnh bậc nhất do nhiễu gây ra, KHÔNG giải lại từ đầu (`[Cơ-method 2]`).
- **Bất biến đoạn nhiệt:** khi tham số hệ biến thiên **chậm** so với chu kỳ dao động riêng, diện tích quỹ đạo pha (x, p) được bảo toàn gần đúng (`[Cơ-idea 74]`) — dùng cho bài "nêm thay đổi từ từ", hạt trong từ trường biến thiên chậm (mô-men từ quỹ đạo bảo toàn) v.v.

## II.7 — Tương tự cấu trúc (Analogy) — vũ khí tiết kiệm thời gian số 1 trong phòng thi
Vì phương trình gốc của nhiều hiện tượng có **cùng dạng toán học**, một khi giải xong 1 bài, ta có ngay lời giải của "bài song sinh":

| Cơ học | ↔ | Tĩnh điện | ↔ | Từ tĩnh/Mạch | Ghi chú |
|---|---|---|---|---|---|
| Lực hấp dẫn `F=Gm₁m₂/r²` | ↔ | Lực Coulomb `F=q₁q₂/4πε₀r²` | | | `[Cơ-fact 9]` ↔ `[Đ&T-§3.1]`, cùng dạng 1/r² → cùng kỹ thuật Gauss, cùng thế năng ~ −1/r |
| Khối lượng `m` | ↔ | Điện dung `C` | ↔ | Độ tự cảm `L` | |
| Lò xo `F=−kx`, `Π=½kx²` | ↔ | Tụ điện `U=Q/C`, `Π=Q²/2C` | ↔ | Cuộn cảm `U=L dI/dt`, `Π=½LI²` | Cùng là "phần tử tích năng lượng thế/động" |
| Ma sát nhớt `F=−bv` | ↔ | Điện trở `U=IR` | | | Cùng là "phần tử tiêu tán" |
| Định luật Newton `F=ma` | ↔ | Định luật vòng Kirchhoff `U=L dI/dt` | | | Phương trình vi phân bậc 2 cùng dạng ⇒ dao động cơ ↔ mạch LC |
| Dao động điều hoà `ẍ+ω²x=0`, `ω²=k/m` | ↔ | Mạch LC `Q̈+ω²Q=0`, `ω²=1/LC` | | | `[Đ&T-§6.4]` |
| Điện trường `E` | ↔ | Từ trường `H` (trong vật liệu) | | | `E↔H, D↔B, ε↔μ` (`[Đ&T-§4.6]`) — bài từ tĩnh có thể "dịch" trực tiếp từ bài tĩnh điện đã giải (quả cầu điện môi ↔ quả cầu từ môi, `[Đ&T-ul 113]`↔`[Đ&T-ul 131]`) |
| Thế hấp dẫn `φ=−GM/r` | ↔ | Điện thế `φ=Q/4πε₀r` | | | Dấu ngược do hấp dẫn luôn hút |

**Nguyên tắc dùng:** khi gặp bài mới, luôn tự hỏi "Bài này có 'bài song sinh' nào tôi đã giải trong nhóm khác không? Nếu phương trình vi phân/tích phân cùng dạng, đáp số chỉ khác tên biến."

## II.8 — Chia để trị & xếp chồng nghiệm ảo (Superposition / phương pháp ảnh)
- **Chồng chất tuyến tính:** với hệ tuyến tính (Ohm, Coulomb, Newton trong giới hạn nhỏ), đáp ứng tổng = tổng các đáp ứng riêng lẻ của từng nguồn (`[Đ&T-§1.2 superpositsiooniprintsiip]`, `[Đ&T-§3.3]`).
- **Vùng "trống" = chồng chất 2 vùng "đầy" trái dấu:** dùng khi một hình có lỗ khoét — coi như hình đặc trừ đi phần lỗ mang mật độ âm (`[Cơ-idea 11]`, ví dụ hốc trong quả cầu tích điện đều `[Đ&T-ul 76]`).
- **Phương pháp ảnh (image method):** thay điện tích cảm ứng trên vật dẫn/biên bằng một (hoặc vài) điện tích ảo đặt sao cho biên vẫn là mặt đẳng thế đúng như ban đầu (`[Đ&T-§3.7]`). Bản chất: định lý duy nhất nghiệm (uniqueness) của phương trình Laplace — nếu tìm được MỘT cấu hình thoả điều kiện biên, đó chính là nghiệm thật, không cần biết chi tiết vi mô.

## II.9 — Trường hợp giới hạn & Đối xứng nghiệm (dùng để KIỂM TRA hoặc RÚT GỌN)
Trước khi giải tổng quát, thử vài giới hạn cực trị/đối xứng để đoán trước dạng nghiệm hoặc rút gọn số biến: R→0 (nối tắt), R→∞ (hở mạch), m→0 (vật nhẹ ⇒ tổng lực = 0 tức thời, `[Cơ-idea 47]`), t→0 (giá trị đầu), t→∞ (trạng thái dừng), α→0 hoặc α→90°...

## II.10 — Kiểm tra thứ nguyên & tính hợp lý định tính
Luôn luôn thực hiện ở Bước 7. Ngoài ra, thứ nguyên còn dùng để **đoán trước dạng công thức** khi bí (ước lượng bằng phân tích thứ nguyên) — kỹ năng chính thức nằm trong Syllabus IPhO ("ability to make appropriate approximations").

---

# PHẦN III — CHUYÊN BIỆT HOÁ: CƠ HỌC

## III.1 — Cây quyết định tổng quát cho một bài Cơ học

```
BẮT ĐẦU
 │
 ├─ Hệ đứng yên hoặc chuyển động đều? ──YES──▶ TĨNH HỌC
 │                                             → ΣF=0, ΣM=0 quanh điểm khéo chọn (II.3)
 │                                             → Nếu >3 ràng buộc cho hệ phẳng: hệ siêu tĩnh
 │                                               (`[Cơ-idea 30]`) → phải đưa độ cứng vào (Hooke)
 │
 ├─ Có va chạm / nổ / biến cố tức thời? ──YES──▶ BẢO TOÀN ĐỘNG LƯỢNG (± mô-men động lượng
 │                                                quanh điểm va chạm `[Cơ-idea 64]`) trong
 │                                                khoảng thời gian va chạm; NGOÀI va chạm
 │                                                dùng lại cây quyết định bình thường
 │
 ├─ Có ma sát/lực tiêu tán VÀ cần vận tốc/quãng đường? ──YES──▶ Công–năng lượng
 │                                                (nhiệt sinh ra = lực ma sát × quãng đường
 │                                                trượt tương đối, `[Cơ-idea 56]`)
 │
 ├─ Số bậc tự do = 1 & không cần lực liên kết? ──YES──▶ METHOD 6 (II.5) — nhanh nhất
 │
 ├─ Cần TÌM lực liên kết/lực căng tường minh? ──YES──▶ Dịch chuyển ảo (Method 1) hoặc
 │                                                tách vật + Newton II từng phần
 │                                                (`[Cơ-idea 47]` nếu có vật/dây khối lượng ~0)
 │
 ├─ Có vật rắn quay? ──YES──▶ Mô-men quán tính (Steiner `I=I₀+Ma²`), K=K_cm+½Mv_cm²
 │                             (`[Cơ-idea 61,62,63]`), L=Iω, M=Iε (`[Cơ-idea 45]`)
 │                             → nếu trục quay tức thời không cố định nhưng khoảng cách
 │                               tới khối tâm không đổi: vẫn dùng Iε=M (`[Cơ-idea 65]`)
 │
 ├─ Có hệ quy chiếu tự nhiên không quán tính (chêm di động, đĩa quay...)? ──YES──▶
 │                             đổi hệ quy chiếu (II.4) trước khi làm bất cứ gì khác
 │
 ├─ Đề cho "biến thiên chậm"/"nhiễu nhỏ"? ──YES──▶ Nhiễu loạn / Bất biến đoạn nhiệt (II.6)
 │
 └─ Chất lỏng/khí liên quan? ──YES──▶ Bernoulli (bảo toàn năng lượng theo dòng) +
                                       liên tục (σv=const) + động lượng cho hệ hở
                                       (`[Cơ-idea 71,72,59]`)
```

## III.2 — Bảng ánh xạ nhanh: Ideas Tĩnh học Kalda → Trụ cột (Phần II)

| Idea gốc | Nội dung (diễn giải) | Thuộc trụ cột |
|---|---|---|
| idea 1 | Chọn trục chiếu để khử lực không cần biết | II.3 |
| idea 2, 3 | Chọn điểm lấy mô-men để khử lực không cần biết | II.3 |
| idea 4, 6 | Trên biên trượt: tổng lực ma sát+phản lực lệch góc arctan µ so pháp tuyến | II.9 (đặc thù ma sát) |
| idea 7, 8, 9 | Đổi hệ quy chiếu không quán tính + lực quán tính/ly tâm | II.4 |
| idea 10 | Khi nào lực trọng trường/quán tính coi như đặt tại khối tâm | II.1 (đối xứng khối lượng) |
| idea 11, 12 | Xếp chồng vùng âm/dương để đối xứng hoá bài toán | II.1, II.8 |
| idea 14 | 3 lực đồng quy tại 1 điểm nếu hệ cân bằng | II.3 (hệ quả trực tiếp) |
| idea 15, 19, 21 | Cân bằng bền ⇔ cực tiểu thế năng | II.5 |
| idea 17, 18 (dây võng) | Cân bằng từng phần tử dây + thành phần ngang không đổi | II.3 (tách hệ con) |
| idea 20 | Khai triển Taylor cho góc/biến dạng nhỏ | II.6 |
| idea 22 (mở phẳng mặt trụ) | Đổi biểu diễn hình học để bài toán 3D → 2D | II.2 (chọn toạ độ khéo) |
| idea 28, 29 | Toạ độ Descartes xoay; "trải phẳng" bề mặt | II.2 |
| idea 30 | Hệ siêu tĩnh cần đưa độ đàn hồi vào | II.2 (đếm DOF đúng) |

## III.3 — Bảng ánh xạ nhanh: Ideas Động lực học Kalda → Trụ cột

| Idea gốc | Nội dung (diễn giải) | Thuộc trụ cột |
|---|---|---|
| idea 31, 32, 33 | Ràng buộc dây/ròng rọc ⇒ hệ thức tuyến tính giữa các chuyển vị | II.2 |
| idea 34–38 | Chọn trục chiếu Newton II để khử ẩn không cần | II.3 |
| idea 39, 44 | Bảo toàn năng lượng; cực trị vận tốc khi gia tốc = 0 | II.1, II.9 |
| idea 40, 41 | Lực pháp tuyến triệt tiêu khi vật rời bề mặt (điều kiện biên) | Luật gốc (Newton) + II.9 |
| idea 42, 43 | Bảo toàn có điều kiện theo thời gian/theo trục | II.1 |
| idea 45, 46, 61–63 | Mô-men quán tính, định lý trục song song, L và K cộng tính | Luật gốc (Newton quay) |
| idea 47 | Vật/dây khối lượng ≈0 ⇒ hợp lực = 0 tức thời | II.9 (giới hạn m→0) |
| idea 48, 49 | Newton II cho khối tâm hệ nhiều vật; công thức khối tâm | II.1 |
| idea 50 | Khối tâm không dịch chuyển ⇒ hợp ngoại lực = 0 | II.1 |
| idea 51 | Liệt kê mọi khả năng trượt/dính khi có ma sát giữa nhiều vật | II.9 (case đầy đủ, không phải case-by-case học thuộc mà là *liệt kê có hệ thống*) |
| idea 52, 53, 57 | Hệ khối tâm cho va chạm; vector động lượng | II.4, II.1 |
| idea 54, 60 | Xung lực cùng hướng lực; va chạm luôn trượt ⇒ tỉ lệ xung = µ | Luật gốc + II.9 |
| idea 55 | Biểu diễn trực quan (đồ thị x–t) | II.9 (công cụ hỗ trợ, không phải luật) |
| idea 58 | Nếu tưởng cả năng lượng lẫn động lượng cùng bảo toàn — kiểm tra lại, thường 1 trong 2 SAI | II.1 (kiểm tra tính hợp lệ của đối xứng/bảo toàn) |
| idea 59 | Phương trình liên tục cho dòng vật chất | Luật gốc (bảo toàn khối lượng, ↔ Kirchhoff I) |
| idea 61–63, 65 | Động năng vật rắn = động năng khối tâm + động năng quay quanh khối tâm (Steiner) | Luật gốc |
| idea 64, 66 | Bảo toàn mô-men động lượng quanh điểm va chạm/tiếp xúc | II.1 |
| idea 67, 68 | Chia quá trình thành pha "va chạm tức thời" + pha "chậm" | II.9 (giới hạn thời gian) |
| idea 69 | Con lắc vật lý: chiều dài quy đổi, 2 trục cho cùng chu kỳ | Luật gốc + II.6 |
| idea 70 | Khối lượng hiệu dụng khi vật chuyển động trong chất lưu | II.4/II.5 (Method 6 mở rộng) |
| idea 71–73 | Bernoulli, xung lực dòng chảy hở, hệ quy chiếu đồng chuyển động với sóng | Luật gốc + II.4 |
| idea 74 | Bất biến đoạn nhiệt | II.6 |

## III.4 — Bảy "Method" (Kalda) — bảng chọn nhanh
`Method 4` (Newton từng vật, chiếu trục) — dùng mặc định khi DOF nhỏ và cần lực tường minh.
`Method 5` (Newton trong hệ quy chiếu không quán tính) — dùng khi có 1 vật "chuẩn" đứng yên tự nhiên trong 1 hệ quy chiếu (chêm, đĩa quay).
`Method 6` (năng lượng suy rộng, "Lagrangian rút gọn") — dùng khi DOF = 1 và không cần lực liên kết — **ưu tiên số 1 nếu áp dụng được**.
`Method 1` (dịch chuyển ảo) — dùng khi cần lực căng/lực liên kết tường minh trong hệ nhiều ràng buộc.
`Method 2` (nhiễu loạn) — dùng khi có 1 lực/tham số "nhỏ" thêm vào bài toán đã biết nghiệm gốc.
`Method 3` (vi tích phân hoá — chia nhỏ vật thể/khoảng thời gian) — dùng cho vật liên tục (dây xích, băng chuyền, cát rơi) hoặc mô-men quán tính.
`Method 7` (mô hình hoá tình huống thực tế) — dùng khi đề bài dùng ngôn ngữ đời sống ("không bị đau tay", "không giật") — nhiệm vụ đầu tiên là dịch câu chữ định tính đó thành 1 điều kiện toán học định lượng.

---

# PHẦN IV — CHUYÊN BIỆT HOÁ: ĐIỆN & TỪ

## IV.1 — Cây quyết định tổng quát cho bài Điện – Từ

```
BẮT ĐẦU
 │
 ├─ Đề cho mạch điện (R, C, L, nguồn, khoá K, điốt...)? ──YES──▶ Sang IV.2 (MẠCH ĐIỆN)
 │
 ├─ Đề hỏi điện trường/thế/lực do phân bố ĐIỆN TÍCH tĩnh gây ra? ──YES──▶
 │        Có đối xứng cầu/trụ/phẳng? ──YES──▶ Định lý Gauss (chọn mặt Gauss khéo, II.3)
 │        Không đối xứng cao? ──YES──▶ Chồng chất (tích phân/tổng vector) hoặc
 │                                      tách lưỡng cực nếu ở xa (`[Đ&T-§3.4]`)
 │        Có vật dẫn/biên cố định thế? ──YES──▶ Phương pháp ảnh (II.8) hoặc
 │                                               giả sử trường đều bên trong + kiểm biên
 │                                               (`[Đ&T-§3.6, ul 104-105]`)
 │        Có điện môi? ──YES──▶ Thêm D=εε₀E, điều kiện biên D_n liên tục, E_τ liên tục
 │
 ├─ Đề hỏi từ trường/lực do DÒNG ĐIỆN tĩnh gây ra? ──YES──▶
 │        Đối xứng trụ/phẳng/solenoid? ──YES──▶ Định lý lưu số Ampère (II.3)
 │        Không đối xứng? ──YES──▶ Biot–Savart + chồng chất, hoặc lưỡng cực từ nếu xa
 │        Có vật liệu từ (µ)? ──YES──▶ H=B/µµ₀, biên: H_τ liên tục, B_n liên tục
 │
 ├─ Đề có TỪ THÔNG biến thiên / mạch chuyển động trong từ trường? ──YES──▶
 │        Định luật Faraday: E=−dΦ/dt (Φ tính bằng II.3: chọn mặt/đường khéo)
 │        Có 2 mạch ghép? ──YES──▶ Hỗ cảm M (`[Đ&T-§5.3]`), tương tự cơ học ghép cặp
 │
 ├─ Đề hỏi chuyển động hạt mang điện trong E, B? ──YES──▶
 │        Lực Lorentz F=qE+qv×B → Newton II như Cơ học (Phần III) với lực này
 │        Đối xứng trụ quanh B ⇒ chuyển động xoắn ốc; dùng bảo toàn "xung suy rộng"
 │        p'_x=p_x−qyB khi E_x=0 (`[Đ&T-§7.1]`) — đây LÀ định luật bảo toàn kiểu Noether
 │        áp dụng cho hệ có đối xứng tịnh tiến "lệch" do từ trường
 │
 └─ Đề hỏi dòng trong vật dẫn khối (không phải mạch tập trung)? ──YES──▶
          Mật độ dòng J=σE (Ohm vi phân), phương trình liên tục ∇·J=0 (dạng tích phân:
          dòng vào = dòng ra mọi mặt kín) — bản chất giống Kirchhoff I nhưng liên tục
```

## IV.2 — MẠCH ĐIỆN: bộ công cụ đầy đủ (bao gồm phần **bổ sung** vì Elekter.pdf chưa phủ hết)

> Đây là phần bạn lưu ý tài liệu gốc "không đầy đủ về ELECTRICAL CIRCUITS". Theo Syllabus IPhO chính thức, phần Circuits yêu cầu: điện trở tuyến tính & Ohm, công suất Joule, nguồn thực (có điện trở trong)/nguồn dòng lý tưởng, ampe kế/vôn kế/ôm kế (thực & lý tưởng), phần tử phi tuyến (đặc trưng V–I cho trước), tụ điện & điện dung (kể cả điện dung 1 vật dẫn so với vô cực), tự cảm & hỗ cảm, hằng số thời gian RC/RL, mạch AC (biên độ phức, trở kháng, giản đồ pha, cộng hưởng, công suất tác dụng). Dưới đây hệ thống hoá **toàn bộ** thành một quy trình.

### IV.2.1 — Hai định luật gốc (không thể thay thế)
- **Kirchhoff I** (nút): Σ dòng vào nút = Σ dòng ra — hệ quả bảo toàn điện tích + giả thiết tụ điện tại nút không đáng kể. Với N nút → N−1 phương trình độc lập.
- **Kirchhoff II** (vòng): Σ (sụt áp đại số) quanh 1 vòng kín = 0 — hệ quả trường tĩnh điện bảo toàn (thế đơn trị). Số vòng độc lập = số nhánh − số nút + 1.

**Đây là 2 định luật DUY NHẤT bạn thực sự cần "nhớ"** cho mọi mạch DC tuyến tính. Mọi kỹ thuật dưới đây chỉ là **cách viết lại 2 định luật này một cách thông minh** để giảm số ẩn (đúng tinh thần Bước 4–5 của Phần I).

### IV.2.2 — Bộ kỹ thuật rút gọn (chọn theo cấu trúc mạch)

| Kỹ thuật | Khi dùng | Cơ chế |
|---|---|---|
| Nối tiếp/song song | Mạch có cấu trúc cây rõ ràng | R_nt=ΣR; 1/R_ss=Σ1/R |
| Biến đổi Sao–Tam giác (Y–Δ) | Mạch cầu, mạch không rút gọn được bằng nối tiếp/song song | `[Đ&T-§1.3]`: R_A=R_AB·R_AC/(R_AB+R_AC+R_BC)... |
| **Phương pháp thế nút** (Node/Potential method) | Mạch nhiều nhánh, ít nút | Ẩn = điện thế từng nút (so với 1 nút gốc); Kirchhoff I tự động cho ra hệ phương trình tuyến tính theo thế nút — **tổng quát hoá của định lý Millman** `[Đ&T-ul 21]`: với N nhánh nối 2 nút A,B, mỗi nhánh có nguồn εᵢ nối tiếp Rᵢ: `U_AB = (Σεᵢ/Rᵢ)/(Σ1/Rᵢ)` |
| **Phương pháp dòng vòng** (Mesh method) | Mạch nhiều vòng độc lập, ít vòng hơn nút | Ẩn = dòng vòng; Kirchhoff I tự động thoả |
| **Nguyên lý chồng chất** | Mạch tuyến tính nhiều nguồn | Giải riêng từng nguồn (nối tắt các nguồn áp khác, hở mạch các nguồn dòng khác), rồi cộng đại số |
| **Định lý Thevenin/Norton** | Cần biết đáp ứng của mạch phức tạp tại 1 cặp cực, khi tải thay đổi | Mọi mạch tuyến tính 2 cực ⇔ 1 nguồn áp lý tưởng ε nối tiếp điện trở trong r (Thevenin), hoặc 1 nguồn dòng I₀=ε/r song song r (Norton). Tìm ε: đo U hở mạch; tìm r: đo I ngắn mạch, hoặc r=ε/I_ngắn mạch |
| **Đối xứng mạch** | Mạch có trục/mặt đối xứng hình học rõ | Các nút đối xứng cùng điện thế ⇒ có thể nối tắt hoặc cắt rời mà không đổi tính chất mạch (`[Đ&T-§1.4]`) |
| **Mạch tuần hoàn vô hạn** | Mạch lặp lại vô hạn (thang, lưới) | Thêm/bớt 1 mắt không đổi R tổng ⇒ phương trình đại số cho chính R (`[Đ&T-§1.4]`); với lưới vô hạn dùng chồng chất dòng bơm vào/rút ra ở vô cực (`[Đ&T-ul 31-32]`) |
| **Phần tử phi tuyến (điốt, bóng đèn...)** | Đặc trưng V–I cho bằng đồ thị/công thức | Với 1 phi tuyến nối tiếp 1 tuyến tính: vẽ "đường tải" `I=(ε−U)/R` lên cùng đồ thị V–I của phần tử phi tuyến, nghiệm = giao điểm (`[Đ&T-§1.5, phương pháp đồ thị]`). Với nhiều phi tuyến: cộng đặc trưng V–I theo dòng (nối tiếp) hoặc theo áp (song song) trước khi tìm giao điểm |
| **Ampe kế/Vôn kế/Ôm kế thực** | Đề cho nội trở dụng cụ đo | Ampe kế lý tưởng: R→0 (nối tắt); Vôn kế lý tưởng: R→∞ (hở mạch); dụng cụ thực → coi như 1 điện trở thêm vào mạch, dùng lại toàn bộ kỹ thuật trên |
| **Nguồn thực & nguồn dòng lý tưởng** | Có điện trở trong r | Nguồn áp thực ε,r ⇔ nguồn dòng lý tưởng I₀=ε/r song song r (tương đương Thevenin↔Norton, `[Đ&T-§1.4]`) |
| **Công suất cực đại truyền tải** | Tải thay đổi được, nguồn có r cố định | P_tải cực đại khi R_tải=r (chứng minh bằng khảo sát hàm P(R) hoặc bất đẳng thức AM-GM) `[Đ&T-ul 17]` |

### IV.2.3 — Mạch có tụ điện / cuộn cảm: quá trình quá độ (transient)

**Nguyên lý chung (Bổ sung — tổng quát hoá đầy đủ hơn Elekter.pdf):**
1. Viết Kirchhoff II cho vòng chứa phần tử tích năng lượng → được **phương trình vi phân tuyến tính** bậc 1 (mạch chỉ có R-C hoặc R-L) hoặc bậc 2 (mạch có cả L và C).
2. **Bậc 1** (RC hoặc RL): dạng `τ ẋ + x = f(t)`. Nghiệm = (nghiệm riêng ứng với trạng thái dừng, thường là hằng số nếu nguồn không đổi) + (nghiệm thuần nhất `Ce^(−t/τ)`). Hằng số C xác định từ điều kiện đầu (điện tích/dòng không đổi tức thời qua tụ/cuộn). τ=RC hoặc τ=L/R.
3. **Bậc 2** không tắt dần (LC lý tưởng): `ẍ+ω²x=0`, ω²=1/LC → dao động điều hoà thuần tuý (analogy trực tiếp với con lắc lò xo, xem II.7).
4. **Bậc 2 có tắt dần (RLC)**: `ẍ + (R/L)ẋ + x/LC = 0` → nghiệm mũ phức, 3 chế độ (dao động tắt dần / tới hạn / quá tắt dần) tuỳ dấu biệt thức — **đây là phần cần bổ sung ngoài Elekter.pdf**, học sinh cần thành thạo giải phương trình vi phân tuyến tính hệ số hằng bậc 2 (theo đúng yêu cầu Toán trong Syllabus IPhO, mục Calculus).
5. **Quy tắc điều kiện đầu bắt buộc nhớ:** điện tích trên tụ (⇒ hiệu điện thế) và dòng qua cuộn cảm **không thể nhảy bậc tức thời** (vì I=dQ/dt, U=L dI/dt hữu hạn) — đây chính là "hằng số tích phân" cần để khớp nghiệm, và là bản chất của các bài "ngay sau khi đóng/mở khoá K" (`[Đ&T-§2.4, §5.2, ul 138-141]`).
6. **Bảo toàn năng lượng + điện tích** để tính nhiệt toả ra trong quá trình quá độ mà KHÔNG cần giải chi tiết I(t): `Π_đầu + A_nguồn = Π_cuối + Q_nhiệt` (`[Đ&T-§2.2]`) — ưu tiên dùng cách này thay vì tích phân `∫I²Rdt` khi chỉ cần tổng nhiệt.

### IV.2.4 — Mạch xoay chiều ổn định (AC steady-state): Phương pháp phức

Quy trình chuẩn (bắt buộc nhớ như 1 thuật toán con):
1. Biểu diễn mọi đại lượng sin bằng số phức: `x(t)=X₀cos(ωt+φ) → x̃=X₀e^(iφ)`.
2. Thay: điện trở `Z̃_R=R`; tụ `Z̃_C=1/(iωC)`; cuộn `Z̃_L=iωL`.
3. Áp dụng **y hệt** kỹ thuật mạch DC (nối tiếp/song song/Kirchhoff/Thevenin...) nhưng với số phức thay vì số thực.
4. Trở kháng tổng `Z̃=Ze^(i∆φ)` ⇒ biên độ `Z=|Z̃|`, độ lệch pha dòng–áp `∆φ=arg Z̃`.
5. Công suất tác dụng (trung bình theo chu kỳ): `P=½U₀I₀cos∆φ=U_hd·I_hd·cos∆φ = ½Re(Ũ Ĩ*)`.
6. **Cộng hưởng**: nối tiếp → Z cực tiểu (=R) tại `ω_res=1/√LC`; song song → Z cực đại tại cùng ω_res (`[Đ&T-§6.4]`).

## IV.3 — Bảng ánh xạ nhanh: Tĩnh điện & Từ tĩnh

| Mục Kalda | Nội dung | Trụ cột |
|---|---|---|
| §3.2 Định lý Gauss | Chọn mặt Gauss theo đối xứng để biến tích phân mặt thành đại số | II.3 |
| §3.3 Chồng chất | Cộng vector trường từ nhiều nguồn điểm/phân bố | II.8 |
| §3.4 Lưỡng cực | Khai triển trường ở xa theo 1/r, 1/r², 1/r³... | II.6 (xấp xỉ khi r lớn) |
| §3.6 Vật dẫn | Trong vật dẫn E=0; mặt vật dẫn là mặt đẳng thế | Luật gốc (hệ quả trực tiếp Gauss + cân bằng tĩnh điện) |
| §3.7, 3.9 Phương pháp ảnh | Thay điện tích cảm ứng bằng điện tích ảo giữ nguyên điều kiện biên | II.8 |
| §3.8, 3.10 Điện môi | D=εε₀E; biên D_n, E_τ liên tục; lực hút điện môi vào vùng trường mạnh | Luật gốc + II.5 (dịch chuyển ảo cho lực trên điện môi) |
| §4.1–4.4 Biot–Savart, Ampère | Tương tự Gauss nhưng cho từ trường (tích phân đường thay tích phân mặt) | II.3, II.7 (đối ngẫu Gauss↔Ampère) |
| §4.5 Lưỡng cực từ | Tương tự lưỡng cực điện | II.6, II.7 |
| §4.6, 4.7 Từ môi, sắt từ | H=B/µµ₀; đối ngẫu hoàn toàn với điện môi | II.7 |
| §4.8 Siêu dẫn | B=0 trong lòng (Meissner); dòng chỉ tồn tại ở bề mặt | Trường hợp giới hạn µ→0 hiệu dụng / điều kiện biên đặc biệt |

## IV.4 — Bảng ánh xạ nhanh: Cảm ứng điện từ, LC, AC

| Mục Kalda | Nội dung | Trụ cột |
|---|---|---|
| §5.1 Faraday | E=−dΦ/dt; tách 2 nguồn gốc (từ trường đổi theo t VÀ mạch đổi vị trí/hình dạng) | Luật gốc; chọn mặt lấy thông lượng khéo (II.3) |
| §5.2 Tự cảm | Φ=LI; U=L dI/dt; năng lượng ½LI² | Luật gốc + II.7 (tương tự lò xo) |
| §5.3 Hỗ cảm | Φ₁=L₁I₁+MI₂...; M₁₂=M₂₁ (chứng minh bằng năng lượng) | II.1 (đối xứng cấu trúc năng lượng) |
| §5.4 | Cực trị dòng qua L hoặc áp qua C ⇔ đạo hàm = 0 | II.9 |
| §6 AC | Phương pháp phức (xem IV.2.4) | II.6 (biến vi phân → đại số) |
| §7.1 Hạt mang điện trong E,B | Lực Lorentz; xung suy rộng bảo toàn khi 1 thành phần trường = 0; siêu bất biến `L±½qBr²` không đổi trong từ trường thuần | II.1 (đối xứng tịnh tiến "xoắn" và đối xứng trụ) |
| §7.2 Dòng trong vật dẫn khối | J=E/ρ; hiệu ứng Hall; tương tự bài toán "2 quả cầu trong môi trường dẫn" ↔ tụ điện | II.7 (tương tự tĩnh điện ↔ dẫn điện, vì cùng phương trình Laplace) |

## IV.5 — Ghi chú riêng: Chuyển động hạt mang điện (thường bị coi là "khó" vì lai Cơ + Điện)

Đây thực chất **không phải chủ đề riêng** — nó là **Phần III (Cơ học, Newton II)** với lực `F=qE+qv×B` thay cho trọng lực/lực đàn hồi. Toàn bộ Phần I–III áp dụng nguyên vẹn:
- DOF, chọn hệ quy chiếu (thường đổi sang hệ quy chiếu trôi với vận tốc `u=E×B/B²` để triệt tiêu điện trường hiệu dụng, `[Đ&T-ul 166]` — đây chính là kỹ thuật II.4).
- Bảo toàn năng lượng vẫn đúng (lực Lorentz thành phần từ không sinh công).
- Đối xứng trụ quanh B ⇒ mô-men động lượng suy rộng `L+½qBr²` bảo toàn (bản chất Noether với đối xứng quay quanh trục B).

---

# PHẦN V — QUY TRÌNH LUYỆN TẬP: KỶ LUẬT HOÁ TRỰC GIÁC

Mục tiêu: biến Phần I–IV thành phản xạ, KHÔNG phải nhồi nhét lời giải. Một học sinh trực giác trung bình **hoàn toàn có thể** đạt được mức "Nhà Vật Lý Lý Thuyết" nếu tuân thủ đúng kỷ luật luyện tập dưới đây — vì bản chất đó là *tự động hoá một quy trình hữu hạn*, không phải "tài năng bẩm sinh vô hạn".

## V.1 — Nghi thức TRƯỚC khi đặt bút (bắt buộc, viết ra giấy nháp cho tới khi thành phản xạ)

```
[ ] 1. Hệ gồm những gì? Biên hệ ở đâu?
[ ] 2. DOF = ? Toạ độ suy rộng chọn là gì?
[ ] 3. Đối xứng nào có thể khai thác? Đại lượng nào bảo toàn?
[ ] 4. Ẩn số cần tìm là gì → chọn "ngôn ngữ luật" nào (bảng Bước 4)?
[ ] 5. Có "bài song sinh" (analogy, II.7) đã biết lời giải không?
[ ] 6. Có tham số nhỏ / trường hợp giới hạn nào giúp đơn giản hoá không?
```
**Chỉ sau khi trả lời đủ 6 câu, mới được viết phương trình đầu tiên.**

## V.2 — Nghi thức SAU khi giải xong (quan trọng hơn cả lúc giải — đây là nơi "học" thực sự xảy ra)

Với MỌI bài đã giải (kể cả giải đúng), viết lại 5 dòng:
1. Bài này DOF = ?, dùng ngôn ngữ luật nào? (đối chiếu bảng Bước 4)
2. Bước quyết định (breakthrough) nằm ở trụ cột nào trong 10 trụ cột Phần II?
3. Nếu đổi 1 chi tiết hình học (vd góc, số vật, có/không ma sát) — quy trình có còn chạy y hệt không? Đâu là phần "công thức riêng" phải tính lại, đâu là phần "quy trình chung" không đổi?
4. Bài này là "bài song sinh" của bài Cơ/Điện nào khác đã giải? Ghi rõ.
5. Nếu tự bịa 1 biến thể mới (đổi số vật, đổi hình dạng), mình có tự tin dựng lại từ Phần I–IV mà không cần nhớ lời giải cũ không?

Nếu câu 5 trả lời "Không" → bài đó CHƯA được học xong, dù đã "giải đúng".

## V.3 — Sổ tay "Idea Log" — tổ chức theo TRỤ CỘT, không theo chủ đề

Sai lầm phổ biến: ghi chú theo chương ("Tĩnh điện", "Cảm ứng điện từ"...). Đúng: ghi chú theo **trụ cột công cụ** (II.1 → II.10), mỗi trụ cột liệt kê các bài đã gặp áp dụng nó, bất kể thuộc chương nào. Việc này ép não liên kết chéo (transfer) giữa Cơ học và Điện–Từ — đúng bản chất "Luật vũ trụ không đổi, chỉ có lớp áo thay đổi".

Mẫu 1 trang trong sổ (ví dụ cho trụ cột II.5 — Method 6 / dịch chuyển ảo):
```
TRỤ CỘT II.5 — Biến phân / dịch chuyển ảo
- [Cơ-pr 26] chêm+khối trên mặt trơn        → ξ = dịch chuyển chêm
- [Cơ-pr 11] giàn hình thoi treo trọng vật   → ξ = độ giãn dây
- [Đ&T-ul 52] tụ 2 nửa vòng tròn quay        → ξ = góc quay α (mô-men từ dW/dα)
- [Đ&T-ul 53] lực hút điện môi vào tụ        → ξ = độ sâu điện môi lọt vào
⇒ Nhận xét chung: mọi bài "tìm lực/mô-men mà không cần biết chi tiết trường/
  ứng suất tại biên" đều giải được bằng Π(ξ) rồi lấy đạo hàm.
```

## V.4 — Lộ trình luyện tập theo tuần (đề xuất cho học sinh lớp 11, mục tiêu VPHO→IPhO)

| Giai đoạn | Nội dung | Cách luyện |
|---|---|---|
| Tuần 1–2 | Thuộc lòng Phần I (7 bước) + Phần II (10 trụ cột) — chưa giải bài khó | Tự diễn giải lại bằng lời mình, không nhìn tài liệu |
| Tuần 3–6 | Giải lại TOÀN BỘ bài "màu xanh/dễ" trong Kalda Cơ+Điện, mỗi bài đều làm nghi thức V.1+V.2 | Ưu tiên tốc độ nhận diện trụ cột, không ưu tiên tốc độ ra đáp số |
| Tuần 7–10 | Bài "màu vàng/trung bình", bắt đầu ghi Idea Log theo V.3 | Sau mỗi 10 bài, tự viết 1 bài tổng hợp: "10 bài này dùng chung trụ cột nào?" |
| Tuần 11–16 | Bài "màu đỏ/khó" + đề IPhO cũ theo chủ đề | Làm dưới áp lực thời gian; sau đó BẮT BUỘC làm V.2 dù đúng hay sai |
| Định kỳ | Thi thử full-length, chấm nghiêm theo barem kiểu IPhO (xem Phụ lục D) | Đối chiếu lỗi sai với: lỗi Bước nào trong Phần I bị bỏ qua? |

---

# PHẦN VI — VÍ DỤ MẪU: ÁP DỤNG TOÀN BỘ QUY TRÌNH TỪ ĐẦU ĐẾN CUỐI

## VI.1 — Ví dụ Cơ học: `[Cơ-pr 26]` — khối m trên chêm góc α khối lượng M, dây qua ròng rọc đỉnh chêm nối tường ngang, mọi mặt trơn. Tìm gia tốc chêm.

- **Bước 1 (Hệ):** {chêm M, khối m, dây (khối lượng 0), ròng rọc lý tưởng}. Ngoại lực: trọng lực, phản lực sàn, phản lực tường (qua dây).
- **Bước 2 (DOF):** Vị trí chêm (1 toạ độ ξ, trượt ngang) + vị trí khối trên chêm so với chêm (do dây không giãn, ràng buộc trực tiếp vào ξ) ⇒ thực chất **DOF = 1**. Chọn ξ = độ dịch chuyển chêm.
- **Bước 3 (Đối xứng/bảo toàn):** Không có ngoại lực ngang khác ngoài phản lực tường qua dây (biến thiên) ⇒ không bảo toàn động lượng ngang trực tiếp, nhưng **năng lượng** bảo toàn (mọi mặt trơn, dây không giãn không tiêu tán) — đây là chìa khoá.
- **Bước 4 (chọn ngôn ngữ luật):** DOF=1, không cần lực căng dây tường minh ⇒ chọn **Method 6** (II.5), không phải Newton từng vật (sẽ dài hơn nhiều lần).
- **Bước 5 (viết phương trình — thuần Toán):** Khi chêm dịch ξ, khối trượt thêm đúng ξ so với chêm (ràng buộc dây), hợp vận tốc khối = tổng vector 2 thành phần ξ̇ (ngang, theo chêm) và ξ̇ hướng dọc mặt chêm (so với chêm), góc giữa chúng = α. Bằng quy tắc cộng vector: `v_khối² = ξ̇²+ξ̇²+2ξ̇²cos α = 2ξ̇²(1+cos α) = 4ξ̇²cos²(α/2)`.
  - Động năng: `K = ½Mξ̇² + ½m·4ξ̇²cos²(α/2) = ½ξ̇²(M+4m cos²(α/2))`
  - Thế năng: khối hạ độ cao `ξ sin α` khi trượt thêm ξ dọc mặt chêm ⇒ `Π = −mgξ sin α` (giảm dần).
- **Bước 6 (giải toán):** Áp Method 6: `ξ̈ = −Π'(ξ)/M_hd = mg sin α / (M+4m cos²(α/2))`.
- **Bước 7 (kiểm chứng):** Thứ nguyên: [gia tốc] ✓. Giới hạn m→0: ξ̈→0 ✓ (không có gì kéo chêm). Giới hạn M→0: ξ̈→g sin α/(4cos²(α/2)) — hữu hạn, hợp lý vì hệ vẫn có quán tính từ m qua ràng buộc dây. Giới hạn α→0: ξ̈→0 ✓ (mặt phẳng ngang, không có thành phần trọng lực kéo).

→ Không một "mẹo" case-by-case nào được dùng — chỉ thuần Phần I–II áp dụng máy móc.

## VI.2 — Ví dụ Điện–Từ: `[Đ&T-ul 104]` — quả cầu kim loại bán kính R đặt vào điện trường đều E₀. Tìm mật độ điện tích cảm ứng và trường bên ngoài.

- **Bước 1 (Hệ):** {quả cầu dẫn điện, điện trường ngoài E₀ (coi như "cho trước", không đổi vì quả cầu nhỏ so với nguồn tạo E₀)}.
- **Bước 2 (DOF – ở đây là "bậc tự do hàm"):** Cần tìm hàm phân bố điện tích mặt σ(θ) và trường E(r,θ) bên ngoài — vô hạn ẩn nếu làm trực tiếp!
- **Bước 3 (Đối xứng):** Hệ đối xứng trục quanh phương của E₀ ⇒ nghiệm chỉ phụ thuộc (r,θ), không phụ thuộc góc phương vị. Đây là đối xứng **quyết định** giúp đoán trước dạng nghiệm.
- **Bước 4 (chọn ngôn ngữ luật):** Đây là bài "vật dẫn trong trường ngoài" ⇒ theo cây quyết định IV.1, dùng **giả sử trường bên trong = 0 do là vật dẫn** rồi tìm trường phụ do điện tích cảm ứng gây ra ở ngoài. Vì ở xa, phân bố điện tích cảm ứng (tổng = 0, đối xứng "dương 1 nửa – âm 1 nửa") trông giống một **lưỡng cực điện đặt tại tâm** (áp dụng trụ cột II.6 — xấp xỉ khai triển đa cực, vì đã biết dạng lưỡng cực từ `[Đ&T-§3.4]`).
- **Bước 5 (viết phương trình — thuần Toán):** Giả sử `E_ngoài = E₀ (đều) + E_lưỡng_cực(p)` với p chưa biết (ẩn số DUY NHẤT, nhờ Bước 3–4 đã nén "vô hạn ẩn" xuống còn 1 ẩn số vô hướng!). Điều kiện biên: thành phần tiếp tuyến `E_τ=0` tại r=R với mọi θ (mặt vật dẫn là đẳng thế).
- **Bước 6 (giải toán):** Thay công thức lưỡng cực `[Đ&T-công thức 4]` vào điều kiện biên, cân bằng hệ số theo `sin θ` ⇒ `p = 4πε₀R³E₀`. Từ đó suy `σ(θ)=3ε₀E₀cos θ` (đạo hàm D_n tại biên).
- **Bước 7 (kiểm chứng):** Tại r→∞: E→E₀ ✓. Tích phân `∮σ dS = 0` ✓ (đúng trung hoà điện). Trường hợp E₀=0: σ=0 ✓.

→ Đây chính xác là kiểu bài "trông có vẻ cần giải phương trình Laplace phức tạp" nhưng với đúng trụ cột II.6 (xấp xỉ đa cực) + II.1 (đối xứng) + định lý duy nhất nghiệm (II.8), bài toán "vô hạn ẩn" co lại thành đại số 1 ẩn.

---

# PHẦN VII — BẪY TƯ DUY: "CASE-BY-CASE" vs "TỔNG QUÁT"

| Dấu hiệu ĐANG pattern-match case-by-case (nguy hiểm) | Dấu hiệu ĐANG mô hình hoá tổng quát (an toàn) |
|---|---|
| "Bài này giống bài tôi từng làm, chép lại cách làm" | "Bài này có DOF, đối xứng, ràng buộc gì? Trụ cột nào áp dụng?" |
| Viết phương trình ngay khi vừa đọc đề | Trả lời đủ 6 câu hỏi V.1 trước |
| Nhớ CÔNG THỨC cuối (vd `R=(2/9)R₀`) | Nhớ QUY TRÌNH tạo ra công thức đó (đối xứng vòng dây, đổi biến góc) |
| Khi đề đổi 1 chi tiết nhỏ (vd góc α thay vì 90°) → bối rối, không biết bắt đầu từ đâu | Khi đề đổi chi tiết → chỉ 1–2 dòng trong Bước 5–6 thay đổi, phần còn lại y nguyên |
| Học theo "dạng bài": "dạng lưỡng cực", "dạng chêm", "dạng RC"... | Học theo "trụ cột công cụ": đối xứng, biến phân, đổi hệ quy chiếu... |
| Không giải thích được TẠI SAO bước đó đúng, chỉ biết "làm vậy sẽ ra" | Giải thích được từng bước bằng đúng 1 trong 10 trụ cột |
| Gặp bài lạ (không có trong "kho đề") → bỏ cuộc | Gặp bài lạ → chạy lại Phần I từ đầu, vì Phần I không phụ thuộc "đã gặp chưa" |

**Bài kiểm tra nhanh cho chính bạn (giáo viên) khi chấm bài học sinh:** hỏi ngược "Nếu thầy đổi số 2 vật thành 3 vật / đổi điện tích thành điện tích trái dấu / đổi góc 90° thành α bất kỳ — em có tự tin dựng lại lời giải mà không cần nhớ bài cũ không?" — Nếu học sinh trả lời được ngay bằng cách chỉ ra "chỗ nào trong 7 bước sẽ thay đổi, chỗ nào không" → học sinh đã đạt Target.

---

# PHỤ LỤC A — Bảng tương tự Cơ – Điện đầy đủ (mở rộng từ II.7, dùng để tra cứu nhanh)

| Đại lượng Cơ học | Đại lượng Điện | Vai trò toán học chung |
|---|---|---|
| Toạ độ x | Điện tích Q | Biến trạng thái |
| Vận tốc ẋ | Dòng điện I=Q̇ | Đạo hàm biến trạng thái |
| Khối lượng m | Độ tự cảm L | Hệ số quán tính (trước ẍ / trước İ) |
| Độ cứng lò xo k | Nghịch đảo điện dung 1/C | Hệ số "phục hồi" (trước x / trước Q) |
| Hệ số cản nhớt b | Điện trở R | Hệ số tiêu tán (trước ẋ / trước İ) |
| Lực ngoài F(t) | Suất điện động ε(t) | Số hạng cưỡng bức |
| Thế năng ½kx² | Năng lượng tụ Q²/2C | Năng lượng "thế" |
| Động năng ½mẋ² | Năng lượng cuộn ½LI² | Năng lượng "động" |
| Tần số riêng ω=√(k/m) | Tần số riêng ω=1/√(LC) | Nghiệm dao động điều hoà |
| Định luật Hooke F=−kx | Định luật tụ U=Q/C | Quan hệ tuyến tính "lực–biến dạng" |
| Ma sát nhớt F=−bẋ | Định luật Ohm U=IR | Quan hệ tuyến tính "lực–tốc độ" |

---

# PHỤ LỤC B — Đối chiếu độ phủ với Syllabus IPhO chính thức (mục Mechanics & EM fields)

*(Tra cứu trực tiếp từ ipho-new.org/statutes-syllabus, để xác nhận Phần III–IV bên trên phủ đủ khung thi.)*

**Mechanics (Syllabus §2.2):** Kinematics, Statics (khối tâm, cân bằng lực/mô-men, Hooke/Young), Dynamics (Newton II, động năng tịnh tiến+quay, thế năng, bảo toàn động lượng/mô-men động lượng/năng lượng, công–công suất, hệ quy chiếu không quán tính, mô-men quán tính+Steiner), Celestial mechanics (lực hấp dẫn, Kepler, năng lượng quỹ đạo elip — **lưu ý: mảng này KHÔNG có trong Elekter/meh_ENG2, cần tài liệu bổ sung riêng nếu ôn phần Celestial Mechanics**), Hydrodynamics (áp suất, lực đẩy Ác-si-mét, liên tục, Bernoulli, sức căng mặt ngoài — sức căng mặt ngoài KHÔNG có trong 2 file gốc, cần bổ sung).

→ Phần III của tài liệu này (Cơ học) phủ **đầy đủ** Kinematics/Statics/Dynamics; **thiếu** Celestial mechanics và Surface tension (nằm ngoài phạm vi 2 PDF gốc) — đề nghị bổ sung riêng nếu mục tiêu là IPhO đầy đủ (không ảnh hưởng tới VPHO/chọn đội tuyển cấp thấp hơn vì các phần này thường không trọng tâm ở vòng trong nước).

**Electromagnetic fields (Syllabus §2.3):** Basic concepts (Coulomb, Kirchhoff), Integral forms Maxwell (Gauss E&B, Ampère, Faraday, điều kiện biên, ảnh điện), Vật liệu (điện trở, điện môi, từ môi, sắt từ–hysteresis, dòng Foucault, chuyển động hạt trong B), **Circuits** (điện trở/Ohm/Joule, nguồn thực/nguồn dòng, dụng cụ đo, phần tử phi tuyến, tụ+cuộn+hỗ cảm, hằng số thời gian, AC/trở kháng/cộng hưởng/công suất).

→ Phần IV của tài liệu này phủ đầy đủ Basic concepts, Maxwell tích phân, Vật liệu; mục **IV.2 (Mạch điện)** đã được **viết bổ sung chủ động** (không chỉ dựa Elekter.pdf) để phủ đúng toàn bộ mục Circuits theo Syllabus, gồm cả các phần Elekter.pdf còn sơ sài: định lý Thevenin/Norton tổng quát, ampe/vôn/ôm kế thực, quá độ RLC bậc 2 tổng quát, quy trình chuẩn phương pháp phức cho AC.

---

# PHỤ LỤC C — Checklist một trang (in ra dán bàn học / mang vào phòng luyện đề)

```
┌─────────────────────────────────────────────────────────┐
│  TRƯỚC KHI VIẾT PHƯƠNG TRÌNH ĐẦU TIÊN:                    │
│  1) Hệ? Biên hệ?                                          │
│  2) DOF? Toạ độ suy rộng?                                 │
│  3) Đối xứng → cái gì bảo toàn?                            │
│  4) Ẩn cần tìm → chọn ngôn ngữ luật (Newton/năng lượng/    │
│     Kirchhoff/Gauss/Ampère/Faraday/phương pháp phức)      │
│  5) Có "bài song sinh" Cơ↔Điện đã biết không?              │
│  6) Tham số nhỏ / giới hạn đặc biệt nào dùng được?         │
│                                                             │
│  KHI VIẾT PHƯƠNG TRÌNH:                                    │
│  - Số phương trình = số ẩn (không hơn, không kém)          │
│  - Chọn trục/điểm mô-men để khử ẩn không cần biết          │
│                                                             │
│  SAU KHI RA ĐÁP SỐ:                                        │
│  - Thứ nguyên? Giới hạn đặc biệt? Đối xứng nghiệm? Dấu?    │
│  - Có tự dựng lại được nếu đổi 1 chi tiết đề bài không?    │
└─────────────────────────────────────────────────────────┘
```

---

# LỜI KẾT DÀNH CHO NGƯỜI DẠY

Bản chất "trực giác hiển nhiên, nhẹ nhàng" của một nhà vật lý không đến từ việc họ có ít bước hơn học sinh — mà đến từ việc **7 bước ở Phần I đã chạy dưới ngưỡng ý thức**, giống một quy trình đã compile. Nhiệm vụ của người dạy không phải là "truyền cảm hứng sáng tạo" (điều không dạy được), mà là **ép học sinh chạy đúng và đủ 7 bước một cách tường minh, lặp đi lặp lại, có ghi chép (Phần V), cho tới khi nó tự động hoá**. Đây là một quá trình cơ khí, kỷ luật, hoàn toàn nằm trong tầm với của một học sinh trực giác trung bình nhưng chăm chỉ — đúng như mục tiêu ban đầu bạn đặt ra.

Không có "tủ đề" nào trong tài liệu này. Chỉ có **10 công cụ (Phần II)** áp lên **2 hệ luật gốc (Newton / Maxwell tích phân)**, chạy qua **1 quy trình 7 bước (Phần I)**, được kiểm chứng lại bằng hàng trăm bài trong Kalda như *ví dụ đã kiểm tra*, chứ không phải *đáp án cần thuộc*.
