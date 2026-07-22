# ALGORITHM HÓA KINEMATICS
### Khung phương pháp cho kỳ thi Chọn Đội Tuyển HSG THPT (VPHO) & tham chiếu IPHO — Lớp 11
*Dựa trên "Problems on Kinematics" (Jaan Kalda, bản 29/11/2017) + luận điểm của giảng viên*

---

## 0. Đối tượng & Mục tiêu

- **Đối tượng:** học sinh lớp 11, trực giác vật lý ở mức **trung bình**, nhưng **kỷ luật và tuân thủ tuyệt đối quy trình**.
- **Kỳ thi:** "KỲ THI CHỌN ĐỘI TUYỂN HỌC SINH GIỎI THPT NĂM HỌC 2027-2028 (TP.HCM, Môn Vật Lý)", tham chiếu tầm IPHO/VPHO.
- **Mục tiêu:** với **mọi** bài Kinematics ở độ khó nêu trên, học sinh phải:
  1. Dùng **dưới 30–60 giây** để trích xuất toàn bộ thông tin BẮT BUỘC từ đề (Giai đoạn A).
  2. Nhận diện đúng "khuôn" lời giải đã chuẩn bị sẵn ở nhà, và chỉ còn việc "lắp số vào công thức" (Giai đoạn B).
  3. Tổng thời gian giải: **dưới 10–15 phút/bài**, không phụ thuộc độ khó (miễn nằm trong phạm vi đã định).
- **Điều kiện tiên quyết để một quy trình được gọi là "algorithm"** (không phải ảo giác "algorithm"):
  - (a) Chi tiết đến mức một học sinh trung bình có thể *cơ giới hóa* (mechanical) từng bước, không cần "sáng tạo" hay "đại số ẩn".
  - (b) Tổng quát cho **cả lớp bài toán**, không chỉ 1 bài lẻ.
  - (c) Đã được **chứng minh chặt chẽ** bằng kiến thức có sẵn, và **không bị cấm** trong syllabus của kỳ thi.

---

## 1. Ví dụ chuẩn hóa: thế nào mới thực sự là "Algorithm"?

Ví dụ tham chiếu do giảng viên cung cấp (Nodal Analysis + KCL cho mạch tuyến tính, bấm trực tiếp trên Casio fx-580VNX) đạt chuẩn "algorithm" vì:

1. **Cơ giới hóa hoàn toàn bước 1 (Vật Lý → Toán):** mọi nút X có nhánh điện trở đáng kể đều cho phương trình dạng
   `(Vx - V1)/R1 + (Vx - V2)/R2 + (Vx - V3)/R3 = 0`
   → tách phân số → gom hệ số của Vx → chuyển các nút khác sang vế phải → thu được **dạng chuẩn tuyến tính** `G1·Vx - G1·V1 - G2·V2 - G3·V3 = 0` với `Gi = 1/Ri`.
2. **Cơ giới hóa bước 2 (giải hệ phương trình):** đặt ẩn phụ (Gi, hoặc Ix nếu tử số có ẩn) để đưa mọi trường hợp — mẫu số ẩn, tử số ẩn, hoặc cả hai — về **cùng một dạng hệ phương trình tuyến tính bậc nhất**, bấm thẳng trên máy tính cầm tay.
3. **Không có bước nào đòi hỏi "trực giác điện"** — chỉ cần nhận diện đúng loại ẩn (mẫu số/tử số) rồi tra đúng "khuôn" biến đổi tương ứng.

**Đây chính là chuẩn** mà mọi "algorithm" cho Kinematics bên dưới phải đạt tới: *một bảng tra cứu (dispatch table) + một quy trình cơ giới cho từng mục trong bảng đó*.

---

## 2. Luận điểm cốt lõi (nhắc lại & hình thức hóa)

| | HSG Lý thông thường (Heuristic) | Mục tiêu của tài liệu này (Algorithm) |
|---|---|---|
| Bước 1 | Hiểu bản chất, dùng trực giác đọc đề, "cảm" ra dữ kiện cần thiết | **Quét đề theo một checklist cố định** để trích xuất dữ kiện — không cần "cảm" |
| Bước 2 | Dùng trực giác + kiến thức vượt chương trình để giải | **Tra bảng dispatch → áp dụng đúng sub-algorithm đã thuộc lòng** |
| Rủi ro | Phụ thuộc hoàn toàn vào phong độ, kinh nghiệm bản thân | Rủi ro thấp: chỉ cần *nhận diện đúng mẫu* (pattern-match), không cần phát minh |
| Thời gian | Không kiểm soát được | Kiểm soát được: mỗi bước có ngân sách thời gian riêng |

Nói cách khác: ta không cố "nâng cấp trực giác" của học sinh, mà **thay thế phần lớn trực giác bằng một quy trình tra cứu tất định (deterministic lookup)**, chỉ chừa lại phần trực giác *tối thiểu* (nhận diện mẫu đề bài — việc mà bộ não con người vẫn làm tốt hơn máy tính, và không thể/không cần algorithm hóa 100%).

---

## 3. KHUNG TỔNG QUÁT — Master Algorithm (2 giai đoạn)

```
ĐỀ BÀI
  │
  ▼
[GIAI ĐOẠN A] Information Extraction Algorithm  (mục tiêu: ~30–60s)
  │   → Danh sách: Vật thể | Đại lượng đã biết | Đại lượng cần tìm
  │     | Ràng buộc/ghi chú ẩn | Tín hiệu (signal) nhận diện dạng bài
  ▼
[GIAI ĐOẠN B] Dispatch & Solve Algorithm  (mục tiêu: ~9–14 phút)
  │   → Tra Bảng Dispatch (§5) bằng các tín hiệu ở Giai đoạn A
  │   → Chọn 1 hoặc nhiều Sub-Algorithm (SA-xx, §6)
  │   → Thực thi cơ giới từng SA đã thuộc
  ▼
ĐÁP SỐ + kiểm tra thứ nguyên/giới hạn (bước chốt, ~30s)
```

---

## 4. GIAI ĐOẠN A: Thuật toán trích xuất thông tin

Đây là bước thay thế "trực giác đọc đề" (mục 2, bước 2 trong mô tả HSG thông thường) bằng một **checklist cố định, luôn quét theo đúng thứ tự** — không được bỏ sót, không được đảo thứ tự (để tránh phụ thuộc "may rủi" khi đọc đề dưới áp lực thời gian).

### 4.1 Checklist quét đề (luôn theo thứ tự này)

1. **Đếm vật thể chuyển động** (bodies) và gán tên/ký hiệu (A, B, C, hoặc số 1, 2...).
2. **Với mỗi vật:** liệt kê vận tốc/gia tốc đã biết (độ lớn + phương/chiều nếu có), và toạ độ/điểm xuất phát.
3. **Đại lượng được hỏi** (target quantity) — viết ra chính xác, kèm đơn vị mong đợi (m/s, s, m, rad/s...) — đây là "kim chỉ nam" chọn công thức cuối.
4. **Quét từ khóa ràng buộc** (constraint keywords) — bảng tín hiệu ở mục 4.2.
5. **Quét hình vẽ/đồ thị đi kèm** — nếu có đồ thị (v-t, a-v, α-t...), ghi nhận ngay: đây là tín hiệu cho SA-05/SA-06.
6. **Quét câu "thừa" (redundant-looking sentences)** — theo *idea 9* của Kalda: nếu đề cho một dữ kiện tưởng như không cần thiết để tính bằng công thức "hiển nhiên", đó luôn là tín hiệu có ẩn ý (thường trỏ tới ma sát/lực cản, hoặc ràng buộc hình học phụ).

### 4.2 Bảng tín hiệu (Signal Table) — từ khóa trong đề → ý nghĩa vật lý

| Tín hiệu trong đề | Ý nghĩa/Diễn giải bắt buộc | Trỏ tới |
|---|---|---|
| "không ma sát", "smooth", "nhẵn" | Bảo toàn năng lượng cơ học dọc theo quỹ đạo | SA-07, SA-16 |
| "đàn hồi" (elastic bounce/collision) | Bảo toàn động năng + động lượng; thành phần pháp tuyến đảo dấu | SA-04, SA-16 |
| "không trượt" (rolling without slipping) | v_tâm = ωR tại điểm tiếp xúc | SA-04, SA-09 |
| "vận tốc không đổi", "constant velocity" của **khung/vật khác** | Tín hiệu chọn hệ quy chiếu gắn với vật đó → nó "đứng yên" | SA-01 |
| Hai đại lượng bằng nhau về độ lớn ở hai thời điểm/hai vật khác nhau | Tín hiệu **đối xứng ẩn** — đổi biến để khai thác | SA-01 (idea 3) |
| Đồ thị góc/khoảng cách theo thời gian, hỏi "tại một thời điểm đặc biệt" | Dùng tiếp tuyến `dy/dx`; nếu độ dốc = 0 tại thời điểm đó → "unusual coincidence" | SA-05 |
| "tốc độ ánh sáng/tốc độ sóng khác nhau ở 2 môi trường", hoặc bài toán "đường đi nhanh nhất" với vận tốc khác nhau theo hướng/miền | Fermat's principle + Snell's law | SA-10 |
| Vận tốc phụ thuộc **hướng di chuyển** (vd bơi trong nước chảy) & Fermat không áp dụng trực tiếp | Huygens' wavefront (đảo ngược quá trình – idea 26) | SA-11 |
| "bắn với tốc độ v0 cố định, hướng bất kỳ", hỏi "vùng có thể tới được" | Ballistic range / Envelope parabola | SA-12 |
| Dây/thanh không giãn, bản lề, ràng buộc độ dài cố định | Đạo hàm phương trình ràng buộc theo t | SA-08 |
| Cuộn chỉ/ống chỉ (spool) quấn/nhả trên vật lăn | "Rope-balance equation" | SA-09 |
| Dòng xe/dòng chất lỏng ổn định, hỏi vận tốc lan truyền của biên | Continuity law | SA-13 |
| Ảnh chụp phơi sáng dài / vệt khói / vệt sáng, hỏi tốc độ gió hoặc hướng | Dựng lại hình học từ giao điểm các vệt | SA-14 |
| Giọt nước/mảnh vỡ tách ra từ vật quay tại các điểm khác nhau cùng lúc | Tập hợp hạt phụ (auxiliary ensemble) | SA-15 |
| Phương trình vi phân xuất hiện tự nhiên nhưng "không được học" | Tìm đại lượng bảo toàn ẩn (không phải E, p, L thông thường) | SA-16 |
| Bài toán 1D nhưng có 2-3 giai đoạn/đối tượng thay đổi theo thời gian, cần "nhìn" đồng thời | Thêm trục thời gian → đồ thị 2D/3D | SA-17 |
| Hai sóng/hai lược chồng lên nhau, hỏi về vân/dải tối | Chồng chập sóng hình sin | SA-18 |

---

## 5. GIAI ĐOẠN B: Bảng Dispatch (tra cứu nhanh)

Sau khi có tín hiệu từ Giai đoạn A, **tra bảng này để chọn Sub-Algorithm (SA)**. Nếu nhiều tín hiệu cùng xuất hiện → áp dụng tuần tự nhiều SA (thường 2, hiếm khi >3, trong phạm vi độ khó VPHO/IPHO).

| Mã | Tên Sub-Algorithm | Ứng với "idea" của Kalda |
|---|---|---|
| SA-01 | Chọn hệ quy chiếu tối ưu | idea 1, 3, 7, 19, 22, 26 |
| SA-02 | Cộng/phân tích vector — hình học vs đại số | idea 2, 4, 14, 15, 16 |
| SA-03 | Tách rời các trục độc lập (decoupling) | idea 20, fact 4 |
| SA-04 | Vật rắn quay & hệ quy chiếu quay | idea 12, 13, 17, 33, 34, 35 |
| SA-05 | Đọc đồ thị → tiếp tuyến/đạo hàm | idea 5, fact 10 |
| SA-06 | Diện tích dưới đồ thị → tích phân | idea 18, fact 2 |
| SA-07 | Tối ưu hóa không cần đạo hàm | idea 6, 8, 10, 31, fact 10, fact 11 |
| SA-08 | Đạo hàm phương trình ràng buộc cứng | idea 38 |
| SA-09 | Cân bằng dây/ống chỉ (rope-balance) | idea 36, 37 |
| SA-10 | Nguyên lý Fermat + định luật Snell | idea 25, fact 5 |
| SA-11 | Nguyên lý Huygens (mặt sóng) | idea 26, 27 |
| SA-12 | Ballistic range / Envelope parabola | idea 28, 29, 30, fact 6–9 |
| SA-13 | Định luật liên tục (continuity/flux) | idea 39 |
| SA-14 | Dựng hình từ vệt/ảnh phơi sáng ("thám tử") | idea 40, 43 |
| SA-15 | Tập hợp hạt phụ (auxiliary ensemble) | idea 42 |
| SA-16 | Tìm định luật bảo toàn ẩn | idea 32, 45 |
| SA-17 | Thêm trục thời gian / đồ thị nhiều chiều | idea 41 |
| SA-18 | Chồng chập sóng / moiré | idea 44 |

---

## 6. THƯ VIỆN SUB-ALGORITHMS

Mỗi SA có cấu trúc cố định: **Trigger** (khi nào dùng) → **Precondition** (điều kiện áp dụng được) → **Procedure** (quy trình cơ giới, đánh số) → **Formula** (công thức chốt) → **Ref** (bài mẫu trong PDF) → **Pitfall** (lỗi thường gặp).

### SA-01 — Chọn hệ quy chiếu tối ưu
- **Trigger:** có ≥2 vật chuyển động; hoặc một vật có vận tốc "phức tạp" trong hệ phòng thí nghiệm (lab frame).
- **Precondition:** hệ quy chiếu ứng viên chuyển động **tịnh tiến** (không quay) nếu muốn cộng gia tốc trực tiếp; nếu quay, phải dùng SA-04.
- **Procedure:**
  1. Liệt kê mọi hệ quy chiếu ứng viên: gắn vào từng vật, hoặc gắn vào "môi trường" (nước, không khí, gió, mặt phẳng ma sát).
  2. Với mỗi ứng viên, kiểm tra 3 tiêu chí: (i) có vật nào đứng yên? (ii) có thành phần vận tốc nào triệt tiêu? (iii) chuyển động có trở nên đối xứng?
  3. Chọn hệ thỏa nhiều tiêu chí nhất.
  4. Giải bài toán trong hệ đó (thường đơn giản hơn hẳn).
  5. Đổi ngược lại hệ phòng thí nghiệm bằng `v_lab = v_rel + v_frame` (chỉ cộng gia tốc tương tự nếu khung tịnh tiến).
- **Formula:** `v_lab = v_rel + v_frame`; `a_lab = a_rel + a_frame` (chỉ khi khung không quay).
- **Ref:** pr1 (khung nước), pr2 (khung 1 máy bay), pr6 (khung băng chuyền), pr28 (khung dòng xe ổn định), pr38/40/48/54/62 (khung rơi tự do/nêm/mặt bàn).
- **Pitfall:** quên đổi ngược về hệ lab; dùng công thức cộng gia tốc cho khung đang quay (sai — phải dùng SA-04).

### SA-02 — Cộng/phân tích vector: hình học vs đại số
- **Trigger:** bài có từ 2 vector trở lên cần cộng/trừ, hoặc điều kiện vuông góc/song song.
- **Precondition:** biết rõ đại lượng nào là "cố định độ lớn" và đại lượng nào "cố định phương".
- **Procedure:**
  1. Viết điều kiện đề bài dưới dạng **hình học** trước (tam giác vector) — nếu bài cho góc, độ dài cố định.
  2. Nếu điều kiện được phát biểu qua **hình chiếu** (component), chuyển sang đại số: chọn 2 trục vuông góc "tối ưu" (không nhất thiết ngang/dọc).
  3. Áp dụng 1 trong các định lý nền: (a) khoảng cách ngắn nhất điểm–đường thẳng là đường vuông góc; (b) tam giác 2 cạnh cố định, góc đối lớn nhất khi tam giác vuông; (c) 2 vector vuông góc ⇔ tích vô hướng = 0; (d) tam giác vuông xác định bởi 1 góc + 1 cạnh.
  4. Giải phương trình lượng giác/đại số thu được.
- **Formula:** `a·b = 0` (vuông góc); modulus theo 1 góc + 1 cạnh: `v = w/sin(α)`.
- **Ref:** pr2, pr3, pr4, pr8 (2 cách giải), pr35, pr47.
- **Pitfall:** chọn trục không tối ưu khiến phương trình dài dòng — luôn thử cách hình học trước khi "brute-force" đại số.

### SA-03 — Tách rời các trục độc lập (Decoupling)
- **Trigger:** chuyển động 2D/3D mà gia tốc theo 1 trục không phụ thuộc tọa độ/vận tốc trục kia (ví dụ: rơi tự do, va chạm không ma sát với mặt phẳng).
- **Precondition:** mặt tiếp xúc **phẳng** (không cong) — nếu cong, phải quay lại dùng nguyên vẹn SA-02/SA-04 vì các trục không còn tách được toàn cục (chỉ tách được cục bộ dọc trục song song bề mặt).
- **Procedure:**
  1. Chọn trục x dọc theo phương "không đổi" (song song mặt/không có lực), trục y vuông góc.
  2. Giải độc lập `x(t)` và `y(t)`.
  3. Khử `t` để ra phương trình quỹ đạo nếu cần.
- **Formula:** `x = v0x·t`; `y = v0y·t - ½gt²` (rơi tự do); parabol khi khử t.
- **Ref:** pr12, pr13, pr14 (mặt cong → cẩn thận), pr37, pr45.
- **Pitfall:** áp dụng "tách trục" cho bề mặt cong toàn cục — chỉ hợp lệ với mặt trụ/lăng trụ có 1 trục song song bề mặt xuyên suốt.

### SA-04 — Vật rắn quay & hệ quy chiếu quay
- **Trigger:** có bản lề, thanh cứng, đĩa/bánh xe quay, hoặc "tâm quay tức thời".
- **Precondition:** biết ≥2 điểm có phương vận tốc đã biết (không song song), hoặc 2 điểm có vận tốc song song + vuông góc với đường nối chúng.
- **Procedure:**
  1. Tìm **tâm quay tức thời O**: (a) giao điểm 2 đường vuông góc dựng từ 2 điểm theo phương vận tốc của chúng; hoặc (b) nếu vận tốc 2 điểm song song & vuông góc đường nối, O là giao điểm đường nối 2 điểm và đường nối 2 mũi vector vận tốc.
  2. Với mọi điểm P trên vật rắn: `v_P = ω·r_OP`, hướng vuông góc `OP`.
  3. Gia tốc mỗi điểm (nếu trục quay cố định): thành phần hướng tâm `ω²r` + thành phần tiếp tuyến `εr` (⊥ nhau).
  4. Nếu trục quay là **tức thời** (không cố định) → công thức gia tốc hướng tâm `ω²r` KHÔNG dùng trực tiếp được — chuyển sang tính đạo hàm vận tốc theo thời gian, hoặc đổi hệ quy chiếu để trục quay hóa cố định tạm thời.
  5. Khi đổi hệ quay: vận tốc góc cộng như vector tịnh tiến (`ω_lab = ω_rel + ω_frame`), kể cả khi không cùng phương.
- **Formula:** `v = ωr`; `a_n = ω²r = v²/r`; `a_t = εr`; hình chiếu vận tốc 2 điểm lên đường nối chúng luôn bằng nhau (vật rắn).
- **Ref:** pr9, pr23, pr24, pr25, pr26, pr27, pr44, pr53.
- **Pitfall:** dùng `a = ω²r` khi trục quay đang dịch chuyển có gia tốc — chỉ hợp lệ khi gia tốc của trục quay tức thời bằng 0.

### SA-05 — Đọc đồ thị → tiếp tuyến/đạo hàm
- **Trigger:** đề cho đồ thị `y` theo `x` (ví dụ góc theo thời gian) và hỏi đại lượng liên quan tốc độ biến thiên.
- **Procedure:**
  1. Xác định đại lượng vật lý `z` cần tìm có liên hệ với `dy/dx` hay không — thử biểu diễn `z` qua `dx, dy` nhỏ rồi rút gọn về tỉ số `dy/dx`.
  2. Nếu đề có "thời điểm đặc biệt" (độ dốc = 0, hoặc trùng hợp bất thường khác) → **luôn khai thác trùng hợp đó**, thường giúp giản lược cực mạnh.
  3. Tính tiếp tuyến bằng số liệu đồ thị (đo trực tiếp nếu là đề dạng ảnh chụp/scan).
- **Ref:** pr4, pr50, pr54, pr59, pr63 (đo trên hình).
- **Pitfall:** bỏ qua "thời điểm đặc biệt" mà đề cố ý gợi ý (độ dốc = 0 tại đúng thời điểm được hỏi không phải ngẫu nhiên).

### SA-06 — Diện tích dưới đồ thị → tích phân
- **Trigger:** đồ thị `v(t)` hoặc `a(v)`... và hỏi quãng đường/vận tốc tích lũy; hoặc gia tốc là hàm của vận tốc (không phải hàm của t).
- **Procedure:**
  1. Nếu `a = a(v)` (không tường minh theo t): viết `dt = dv/a(v)`, suy ra `s = ∫ v/a(v) dv` — diện tích dưới đồ thị `v/a(v)` theo `v`.
  2. Nếu có đồ thị `v-t`: quãng đường = diện tích có dấu (phần dưới trục t là âm).
  3. Với gia tốc không đổi: `s = v0t + ½at² = (v1²-v0²)/2a` (hình thang).
- **Formula:** `s = ∫v(t)dt`; `s = ∫ v/a(v) dv` khi a=a(v).
- **Ref:** pr10, pr11 (đồ thị a-v).
- **Pitfall:** quên đổi biến tích phân khi hàm cho theo biến khác t.

### SA-07 — Tối ưu hóa không cần đạo hàm
- **Trigger:** bài hỏi max/min nhưng đối tượng "trung bình" (theo giả định của tài liệu) — tránh Cauchy-Schwarz/AM-GM (không phải algorithm phù hợp, xem mục 9).
- **Procedure:**
  1. Thử quy về **hình học thuần túy**: tổng 2 vector với 1 vector cố định, 1 vector có phương cố định → min khi tạo tam giác vuông (SA-02 mục c).
  2. Nếu có "biến thiên nhỏ" `Δx` quanh điểm nghi ngờ là cực trị: dùng `Δf = f(x+Δx) - f(x)` là **bậc hai nhỏ** (bỏ qua bậc nhất) — đây là thay thế hoàn toàn cho đạo hàm, chỉ cần đại số.
  3. Nếu 2 vector gần bằng nhau về độ lớn và hiệu của chúng rất nhỏ → hiệu đó gần như vuông góc với cả hai (fact 11) — dùng để suy ra điều kiện vuông góc tại cực trị mà không cần tính đạo hàm.
- **Ref:** pr6, pr8, pr10, pr12 (giải bằng chuyển hệ + idea 10), pr21, pr22.
- **Pitfall:** cố áp dụng bất đẳng thức đại số (Cauchy-Schwarz, AM-GM) — không đạt chuẩn "algorithm" cho đối tượng trung bình (xem mục 9).

### SA-08 — Đạo hàm phương trình ràng buộc cứng
- **Trigger:** 2 điểm/2 vật nối bởi đoạn có **độ dài cố định** (thanh, dây không giãn) và cần tốc độ/gia tốc của 1 điểm khi biết điểm kia.
- **Procedure:**
  1. Viết ràng buộc bằng tọa độ: `l² = x² + y²` (ví dụ thang trượt tường) hoặc tổng bình phương nhiều đoạn.
  2. Lấy đạo hàm theo t **toàn bộ hai vế** (dùng quy tắc chuỗi), vì `l` là hằng số nên đạo hàm của nó = 0.
  3. Với gia tốc: đạo hàm bậc 2 (lặp lại bước 2 một lần nữa).
  4. Giải hệ đại số tuyến tính thu được cho ẩn cần tìm.
- **Formula mẫu:** `0 = x·(dx/dt) + y·(dy/dt)`.
- **Ref:** pr27, pr36, pr42, và thay thế cho SA-04 khi không muốn dùng tâm quay tức thời.
- **Pitfall:** quên rằng đạo hàm của 1 tổng bình phương vẫn cần quy tắc chuỗi đầy đủ — dễ bỏ sót dấu.

### SA-09 — Cân bằng dây/ống chỉ (Rope-balance)
- **Trigger:** vật hình trụ/ống chỉ quấn/nhả dây trong lúc lăn hoặc trượt.
- **Procedure:**
  1. Xác định tốc độ **nhả dây** (tốc độ dây rời khỏi ống): nếu phần dây chưa nhả không quay, tốc độ nhả = `ΩR` (Ω: tốc độ góc ống, R: bán kính); nếu phần dây đó cũng quay, dùng hiệu 2 tốc độ góc (idea 17).
  2. Viết "phương trình cân bằng chiều dài dây": tổng chiều dài không đổi ⇒ liên hệ tốc độ nhả với vận tốc của ống chỉ.
  3. Dựng 2 trạng thái **rất gần nhau về thời gian** của hệ (idea 37) để tính biến thiên chiều dài một cách hình học/đại số đơn giản.
- **Ref:** pr26, pr44, pr46.
- **Pitfall:** nhầm `ΩR` là tốc độ ống chỉ tịnh tiến — đây là tốc độ TƯƠNG ĐỐI của việc nhả dây, cần cộng thêm vận tốc tịnh tiến của ống nếu có.

### SA-10 — Nguyên lý Fermat + Định luật Snell
- **Trigger:** đường đi nhanh nhất giữa 2 điểm khi vận tốc khác nhau theo từng miền/môi trường (không phụ thuộc hướng trong từng miền).
- **Precondition (cảnh báo bắt buộc):** chỉ áp dụng được khi **vận tốc như nhau theo mọi hướng trong mỗi miền**, và 2 điểm đầu/cuối **đứng yên** trong hệ quy chiếu đang xét. Nếu không thỏa (ví dụ vận tốc bơi phụ thuộc hướng do có dòng nước) → chuyển sang SA-01 để đổi hệ quy chiếu (loại bỏ dòng chảy) rồi mới áp dụng lại SA-10, hoặc dùng SA-11.
- **Procedure:**
  1. Kiểm tra precondition ở trên trước tiên.
  2. Áp dụng Snell: `sin(α1)/sin(α2) = v1/v2` tại biên giữa 2 miền.
  3. Nếu đường thẳng/mặt phẳng là đích đến (không phải 1 điểm): thay bằng "điểm ở vô cực theo phương vuông góc" — tương đương chùm tia song song chiếu vuông góc lên đường/mặt đó.
- **Ref:** pr17, pr18 (sau khi đổi hệ quy chiếu).
- **Pitfall:** áp dụng Fermat trực tiếp khi vận tốc phụ thuộc hướng (ví dụ có dòng nước/gió cộng vào) — đây là lỗi phổ biến nhất, **luôn kiểm tra precondition trước**.

### SA-11 — Nguyên lý Huygens (mặt sóng)
- **Trigger:** SA-10 không áp dụng được (vận tốc phụ thuộc hướng) nhưng vẫn cần "đường đi nhanh nhất".
- **Procedure:**
  1. (Tùy chọn) Đảo ngược bài toán theo thời gian nếu giúp đơn giản hơn (idea 26).
  2. Từ điểm xuất phát, dựng liên tiếp các "mặt sóng" — quỹ tích mọi điểm đến được sau cùng 1 khoảng thời gian `T`, bằng cách đặt nguồn Huygens phụ tại mọi điểm của mặt sóng trước đó.
  3. Mặt sóng lan tới đích tại thời điểm `T` = thời gian ngắn nhất; truy ngược nguồn Huygens nào tạo ra điểm chạm đích → đó là quỹ đạo tối ưu.
- **Ref:** pr18, pr61.
- **Pitfall:** quên rằng đây là kỹ thuật thay thế Fermat chứ không phải bổ sung — chỉ dùng khi Fermat bị cấm bởi precondition.

### SA-12 — Ballistic range / Envelope parabola
- **Trigger:** "bắn/ném với tốc độ ban đầu v0 cố định, hướng bất kỳ" + hỏi vùng tới được, hoặc tốc độ nhỏ nhất để trúng 1 điểm cho trước.
- **Procedure:**
  1. Ghi nhớ: biên của vùng tới được luôn là 1 **parabol bao (envelope)**, và pháo/điểm bắn nằm tại **tiêu điểm (focus)** của parabol đó.
  2. Nếu hỏi tốc độ nhỏ nhất để trúng điểm T: quỹ đạo tối ưu và biên parabol **tiếp xúc nhau tại T** (cùng tiếp tuyến).
  3. Dùng tính chất tiêu điểm: tổng (khoảng cách từ 1 điểm trên parabol đến tiêu điểm) + (khoảng cách đến "đường chuẩn" ở vô cực, tức độ cao) = hằng số → thiết lập phương trình đại số thuần túy, KHÔNG cần đạo hàm.
  4. Trường hợp đặc biệt: nếu T ở cùng độ cao pháo → góc bắn tối ưu luôn là 45°.
  5. Nếu cần phương trình chính xác (không chỉ định tính): tham số hóa theo góc bắn `α`, khử `t`, đưa về phương trình bậc 2 theo `tan(α)` (không phải `cos(α)` trực tiếp — tránh căn thức), rồi dùng điều kiện "biệt thức = 0" để tìm biên vùng tới được.
- **Formula:** biệt thức của phương trình bậc 2 theo `tan α` triệt tiêu ⇒ điểm nằm trên biên `R`.
- **Ref:** pr19, pr20, pr21, pr22, pr49.
- **Pitfall:** khai triển `cos^-2(α)` sai — luôn quy về `tan(α)` làm ẩn chính vì `cos^-2 = 1 + tan²`.

### SA-13 — Định luật liên tục (Continuity/Flux)
- **Trigger:** dòng ổn định của "vật gì đó" (xe, chất lỏng...) và hỏi tốc độ lan truyền của 1 biên/nhiễu loạn.
- **Procedure:**
  1. Đổi sang hệ quy chiếu làm cho dòng chảy **ổn định** (dùng SA-01 trước nếu cần — ví dụ hệ gắn với đầu hàng xe đang dừng).
  2. Trong hệ đó: lưu lượng vào = lưu lượng ra qua mọi mặt cắt.
  3. Biểu diễn lưu lượng = (mật độ tuyến tính)×(vận tốc tương đối) ở 2 phía biên, cho bằng nhau, giải ra vận tốc biên.
- **Ref:** pr28, pr57, pr58.
- **Pitfall:** áp dụng continuity trực tiếp trong hệ lab khi dòng chưa ổn định ở đó.

### SA-14 — Dựng hình từ vệt/ảnh phơi sáng ("thám tử")
- **Trigger:** đề cho ảnh chụp (vệt khói, vệt sáng, ảnh phơi sáng dài) và hỏi tốc độ/hướng của tác nhân ẩn (gió, dòng nước).
- **Procedure:**
  1. Nếu 2 vật di chuyển và để lại vệt, **giao điểm 2 vệt = vị trí chúng gặp nhau** (nếu có gặp).
  2. Trong hệ quy chiếu của "tác nhân ẩn" (gió/nước), vệt phải là đường thẳng nối vị trí xuất phát và vị trí hiện tại — dựng tam giác vận tốc từ đó.
  3. Đo đạc trực tiếp trên hình (dùng tỉ lệ đã cho) để suy ra các cạnh tam giác vận tốc.
- **Ref:** pr29, pr50, pr56, pr63.
- **Pitfall:** đo sai tỉ lệ hình vẽ; quên rằng vệt phản ánh vận tốc **tương đối** với môi trường, không phải vận tốc so với đất.

### SA-15 — Tập hợp hạt phụ (Auxiliary ensemble)
- **Trigger:** 1 hạt tách ra khỏi vật đang quay/chuyển động phức tạp tại 1 điểm — bài toán khó hình dung quỹ đạo của riêng nó.
- **Procedure:**
  1. Tưởng tượng **đồng thời** nhiều hạt phụ tách ra từ mọi điểm khác của vật tại cùng thời điểm.
  2. Trong hệ quy chiếu phù hợp (thường là hệ rơi tự do), tập hợp hạt phụ này luôn giữ 1 hình dạng đơn giản (thường là đường tròn) tại mọi thời điểm sau đó.
  3. Điều kiện đề bài (ví dụ "hạt đầu tiên chạm đất") tương đương với "hình tròn đó vừa chạm 1 đường/mặt cho trước" → dùng SA-06/SA-02 để giải ra thời gian.
- **Ref:** pr31.
- **Pitfall:** quên đổi lại hệ quy chiếu ban đầu sau khi tìm được thời điểm/góc.

### SA-16 — Tìm định luật bảo toàn ẩn
- **Trigger:** bài dẫn đến phương trình vi phân "không được học giải" (đề thi sẽ không bắt giải PT vi phân bậc cao/không tách biến được) — đây là **tín hiệu** rằng có 1 đại lượng bảo toàn không chuẩn (không phải E, p, L) đang chờ được phát hiện.
- **Procedure:**
  1. Liệt kê các đại lượng động học xuất hiện trong phương trình vi phân (tọa độ, vận tốc — KHÔNG lấy đạo hàm cao nhất đang được lấy vi phân).
  2. Thử các tổ hợp tuyến tính/đơn giản của các đại lượng đó (thường là tổng/hiệu 2 khoảng cách, hoặc `½v² - gh` kiểu năng lượng riêng).
  3. Chứng minh tổ hợp đó có đạo hàm thời gian = 0 (thường bằng cách chỉ ra 2 tốc độ thay đổi bằng nhau về độ lớn, ngược dấu).
  4. Dùng giá trị bảo toàn này (biết tại 1 thời điểm) để suy luận tại thời điểm khác — thường là thời điểm cần tìm (cực trị khoảng cách...).
- **Ref:** pr21 (idea 32: `½v² - gh` không đổi), pr34 (khoảng cách "hiệu chỉnh" giữa chó và cáo).
- **Pitfall:** cố giải trực tiếp phương trình vi phân — vượt quá công cụ cho phép, luôn ưu tiên tìm bảo toàn trước.

### SA-17 — Thêm trục thời gian / đồ thị nhiều chiều
- **Trigger:** bài toán có 2-3 vật thể chuyển động thẳng đều (1D) và hỏi về việc chúng có "gặp nhau"/"va chạm" hay không, dựa trên các điều kiện tương đối phức tạp.
- **Procedure:**
  1. Dựng đồ thị `x` theo `t` (2D cho bài 1D; 3D `x,y,t` cho bài phẳng) — mỗi vật là 1 đường thẳng.
  2. Va chạm/gặp nhau ⇔ 2 đường giao nhau ⇔ 2 đường **đồng phẳng** (áp dụng sự kiện hình học: 3 điểm luôn đồng phẳng; đường thẳng + 1 điểm xác định 1 mặt phẳng).
  3. Dùng tính chất hình học không gian (đồng phẳng/giao nhau) để suy luận thay vì tính toán đại số trực tiếp.
- **Ref:** pr30, pr66 (đếm số cặp va chạm = số cặp đường thẳng giao nhau).
- **Pitfall:** quên đây là công cụ hình học thuần túy — không cần viết phương trình chuyển động tường minh.

### SA-18 — Chồng chập sóng / Moiré
- **Trigger:** 2 "lược"/2 sóng tuần hoàn chồng lên nhau, hỏi tốc độ của vân/dải sáng-tối xuất hiện (hiệu ứng moiré).
- **Procedure:**
  1. Biểu diễn mỗi lược như 1 sóng hình sin `a(x,y,t) = sin(k·r - ωt)`.
  2. Vân tối/sáng ứng với tích `a1·a2 ≈ 1` (2 răng lược trùng vị trí).
  3. Khai triển tích 2 hàm sin thành tổng/hiệu 2 hàm cos (công thức tích thành tổng) → nhận diện đây là 1 sóng hình sin "chậm" với vector sóng = hiệu 2 vector sóng ban đầu.
  4. Tốc độ vân = ω_hiệu / |k_hiệu|.
- **Ref:** pr33.
- **Pitfall:** quên công thức biến đổi tích thành tổng lượng giác — đây là bước đại số duy nhất cần thuộc.

---

## 7. QUY TRÌNH THI ĐẤU — Ngân sách thời gian 10–15 phút/bài

| Bước | Thời gian | Nội dung |
|---|---|---|
| A. Trích xuất | 30–60s | Chạy checklist §4.1, ghi ra giấy nháp: Vật thể / Biết / Cần tìm / Tín hiệu |
| B1. Tra dispatch | 15–30s | Đối chiếu tín hiệu với Bảng §5, chọn (các) SA |
| B2. Thực thi | 6–10 phút | Chạy đúng quy trình cơ giới của từng SA đã chọn (§6) |
| C. Kiểm tra | 30–60s | Thứ nguyên, giới hạn (trường hợp riêng có ý nghĩa không?), dấu |
| **Tổng** | **≤ 10–15 phút** | |

**Quy tắc dừng khẩn cấp:** nếu sau khi tra bảng dispatch mà **không có tín hiệu nào khớp** trong 60 giây đầu của B1 → đây là bài "ngoài khuôn" (hiếm ở tầm VPHO/IPHO nếu đã luyện đủ §11) → tạm bỏ qua, quay lại sau, **không** cố "sáng tạo" giữa chừng khi đang chạy đua thời gian.

---

## 8. MINH HỌA: chạy Master Algorithm trên 3 bài mẫu

### 8.1 pr2 — Hai máy bay (SA-01 + SA-02)
- **A:** Vật thể: 2 máy bay. Biết: v1=800, v2=600 km/h, quỹ đạo vuông góc nhau tại 1 thời điểm, cả 2 cách giao điểm quỹ đạo `a=20km`. Cần tìm: khoảng cách nhỏ nhất. Tín hiệu: "2 vật chuyển động thẳng đều, hỏi khoảng cách nhỏ nhất khi vận tốc không đổi mãi mãi" → SA-01 (đổi hệ) + SA-02 (khoảng cách ngắn nhất = đường vuông góc).
- **B:** Chọn hệ gắn máy bay đỏ (SA-01). Trong hệ đó máy bay xanh chuyển động thẳng theo hướng hợp góc `α=arctan(3/4)` với 1 trục — áp dụng SA-02 mục (a): khoảng cách nhỏ nhất = đường vuông góc từ máy bay đỏ (gốc, đứng yên trong hệ mới) đến đường thẳng quỹ đạo tương đối.
- **Kết quả:** đáp số 4 km (khớp đáp án PDF).

### 8.2 pr17 — Cậu bé câu cá bên vịnh (SA-10)
- **A:** Vật thể: cậu bé. Biết: vận tốc chạy `v`, vận tốc thuyền `u<v`, hình học vịnh góc `α`. Cần tìm: điểm `x` trên bờ OM để tối ưu thời gian. Tín hiệu: "tốc độ khác nhau ở 2 miền (bờ/nước), tìm đường đi nhanh nhất" → SA-10.
- **B:** Kiểm tra precondition: vận tốc `v` (chạy) và `u` (chèo) đều không phụ thuộc hướng → Fermat áp dụng được trực tiếp, không cần đổi hệ quy chiếu. Áp dụng SA-02 trước để thấy đoạn tới bờ OM phải vuông góc bờ đó (do đích là 1 đường thẳng ⇒ thay bằng điểm ở vô cực vuông góc, xem SA-10 bước 3). Sau đó dùng Snell tại điểm khúc xạ trên bờ OP.
- **Kết quả:** biểu thức `x`, `t` như trong đáp án PDF (mục 9, đáp án 17).

### 8.3 pr21 — Ném đá qua mái nhà dốc (SA-07 + SA-12)
- **A:** Vật thể: hòn đá. Biết: bề rộng mái `b`, 2 cạnh cao `a, c`. Cần tìm: `v_min` để ném qua mái. Tín hiệu: "tốc độ ném nhỏ nhất, hướng + điểm ném tự do" → SA-12 (ballistic range) + SA-07 (chứng minh quỹ đạo phải chạm cả 2 mép mái, dùng biến thiên bậc hai chứ không đạo hàm).
- **B:** Bước 1 (SA-07): chứng minh bằng phản chứng — nếu quỹ đạo không chạm cả 2 mép, có thể giảm tốc độ hoặc dịch điểm ném, mâu thuẫn với "nhỏ nhất". Bước 2: quy về trường hợp `c=0` bằng bảo toàn `½v² - gh` (SA-16 nhẹ). Bước 3 (SA-12): dùng tính chất tiêu điểm của parabol bao để suy `v_min = √(g(a+b+c))` mà không cần đạo hàm.
- **Kết quả:** khớp đáp án PDF: `v_min = √(g(a+b+c))`.

---

## 9. GIỚI HẠN & KIỂM TRA "KHÔNG BỊ CẤM" (theo IPHO Syllabus)

Trước khi đưa 1 sub-algorithm vào "kho thuộc lòng", **bắt buộc kiểm tra** nó không dùng công cụ nằm ngoài syllabus của kỳ thi mục tiêu. Đối chiếu với **IPHO Syllabus** (nguồn: ipho-new.org/statutes-syllabus), các công cụ dùng trong §6 đều **được phép chính thức**:

- **Kinematics** (mục 2.2.1 Syllabus): đạo hàm vị trí, cộng vận tốc/vận tốc góc, cộng gia tốc (bỏ qua Coriolis + nhận diện khi Coriolis = 0), vật rắn quay quanh tâm quay tức thời → **chính là nội dung SA-01, SA-02, SA-04**.
- **Calculus** (mục 4.7): đạo hàm, tích phân (kể cả đổi biến), Taylor/tuyến tính hóa, phương pháp nhiễu loạn (perturbation) → hợp thức hóa SA-05, SA-06, SA-07 (biến thiên bậc hai).
- **Waves** (mục 2.4.2): "Fermat's principle, Snell's law" được liệt kê **tường minh** → hợp thức hóa SA-10.
- **Interference/diffraction** (2.4.3): "Huygens' principle" tường minh → hợp thức hóa SA-11.
- **Geometry** (4.3): "properties of conic sections including... parabolae" tường minh → hợp thức hóa SA-12 (tính chất tiêu điểm parabol).
- **Hydrodynamics** (2.2.5): "continuity law" tường minh → hợp thức hóa SA-13.

⚠️ **Lưu ý riêng cho SA-07:** Cauchy-Schwarz/AM-GM (ví dụ đối chứng của giảng viên) **không nằm trong mục "Theoretical skills"** của Syllabus (chỉ có "Algebra: quadratic/biquadratic equations") — do đó bất đẳng thức đại số cấp cao **không được ưu tiên làm "algorithm chuẩn"** cho SA-07; ưu tiên biến thiên bậc hai (fact 10) và hình học (fact 8, mục b SA-02) vì đây là công cụ **cơ giới hóa được** và **nằm trong syllabus**.

⚠️ Với kỳ thi VPHO/Chọn đội tuyển TP.HCM cụ thể: syllabus có thể **khác/hẹp hơn hoặc rộng hơn** IPHO tùy quy định của Sở/Bộ GD từng năm — học sinh **phải tự đối chiếu đề cương ôn tập chính thức** của kỳ thi 2027-2028 trước khi coi mục này là "được phép tuyệt đối". Tài liệu này chỉ đối chiếu được với IPHO vì đó là nguồn công khai duy nhất được cung cấp.

---

## 10. CHEAT-SHEET CÔ ĐỌNG (học thuộc trước khi vào phòng thi)

```
BƯỚC 1 (≤60s): Vật thể? | Biết gì? | Hỏi gì? | Quét từ khóa bảng §4.2

BƯỚC 2: Tra bảng dispatch §5 theo tín hiệu:
  - "hệ khác đơn giản hơn?"        → SA-01
  - "vector/góc/vuông góc?"        → SA-02
  - "rơi tự do / va chạm phẳng?"   → SA-03
  - "bản lề / đĩa quay / tâm quay?"→ SA-04
  - "đồ thị, hỏi tại 1 thời điểm?" → SA-05
  - "đồ thị v-t hoặc a(v)?"        → SA-06
  - "max/min, đối tượng trung bình"→ SA-07 (KHÔNG Cauchy/AM-GM)
  - "dây/thanh cố định độ dài?"    → SA-08
  - "ống chỉ quấn/nhả?"            → SA-09
  - "tốc độ khác miền, đường nhanh nhất, ko hướng-phụ-thuộc" → SA-10
  - "như trên nhưng có dòng chảy/gió cộng vào" → SA-11
  - "bắn v0 cố định, vùng tới được?" → SA-12
  - "dòng ổn định, biên lan truyền?" → SA-13
  - "ảnh phơi sáng / vệt khói?"     → SA-14
  - "hạt tách từ vật quay, nhiều điểm cùng lúc?" → SA-15
  - "PT vi phân lạ xuất hiện?"      → SA-16
  - "nhiều vật 1D, hỏi có gặp không?" → SA-17
  - "2 sóng/lược chồng, vân tối?"   → SA-18

BƯỚC 3: Chạy đúng Procedure đã thuộc của SA đó (§6) — không tự sáng tác.

BƯỚC 4 (≤60s): Kiểm tra thứ nguyên + giới hạn (case riêng có hợp lý không?).
```

---

## 11. BẢN ĐỒ LUYỆN TẬP: 66 bài trong PDF → Sub-Algorithm tương ứng

*(Dùng để luyện phản xạ tra bảng dispatch — che đáp án cột phải, tự đoán SA trước khi mở PDF)*

| Bài | SA áp dụng chính | Bài | SA áp dụng chính |
|---|---|---|---|
| pr1 | SA-01 | pr34 | SA-16 |
| pr2 | SA-01, SA-02 | pr35 | SA-02 |
| pr3 | SA-02 | pr36 | SA-08 |
| pr4 | SA-02, SA-05 | pr37 | SA-03 |
| pr5 | SA-01 | pr38 | SA-01 |
| pr6 | SA-01, SA-07 | pr39 | SA-04, SA-09(ý) |
| pr7 | SA-01, SA-02, SA-03 | pr40 | SA-01 |
| pr8 | SA-02, SA-04 | pr41 | SA-08 (PT vi phân tách biến) |
| pr9 | SA-04 | pr42 | SA-08, SA-01, SA-04 |
| pr10 | SA-06 | pr43 | SA-01, SA-02 |
| pr11 | SA-06 | pr44 | SA-04, SA-09 |
| pr12 | SA-01, SA-03 | pr45 | SA-03 |
| pr13 | SA-03 | pr46 | SA-04(idea21) |
| pr14 | SA-03, SA-04(idea21) | pr47 | SA-02 |
| pr15 | SA-01 | pr48 | SA-01 |
| pr16 | SA-08(idea24-tham số hóa) | pr49 | SA-12, SA-16 |
| pr17 | SA-10 | pr50 | SA-05, SA-14 |
| pr18 | SA-10, SA-11 | pr51 | SA-06, SA-17(ý) |
| pr19 | SA-12 | pr52 | SA-04 (như pr3) |
| pr20 | SA-12 | pr53 | SA-04 |
| pr21 | SA-07, SA-12, SA-16 | pr54 | SA-01, SA-14 |
| pr22 | SA-12, SA-16 | pr55 | SA-13, SA-05 |
| pr23 | SA-04 | pr56 | SA-01, SA-14 |
| pr24 | SA-04 | pr57 | SA-13 |
| pr25 | SA-04, SA-08 | pr58 | SA-13 |
| pr26 | SA-04, SA-09 | pr59 | SA-02 (hình học màn trập) |
| pr27 | SA-04, SA-08 | pr60 | SA-05, SA-16(ý) |
| pr28 | SA-01, SA-13 | pr61 | SA-11 |
| pr29 | SA-14 | pr62 | SA-01, SA-14 |
| pr30 | SA-17 | pr63 | SA-01, SA-14 |
| pr31 | SA-15 | pr64 | SA-01 (khung rơi tự do) |
| pr32 | SA-14 (phân tích scan-line) | pr65 | SA-01 |
| pr33 | SA-18 | pr66 | SA-17, SA-04 (va chạm đàn hồi) |

---

## 12. Phụ lục — Ví dụ chuẩn hóa gốc (Nodal Analysis, tham chiếu mục 1)

Ba trường hợp mẫu số côt/tử số ẩn từ ghi chú gốc của giảng viên (không lặp lại chi tiết ở đây để tránh trùng lặp) được giữ nguyên trong 3 ảnh gốc đính kèm cuộc trò chuyện — dùng làm **bài kiểm tra chuẩn ("acid test")**: nếu 1 quy trình mới được đề xuất cho Kinematics **không thể** được viết lại theo đúng cấu trúc 3 bước (Trigger → Procedure cơ giới → Formula bấm máy trực tiếp) như 3 ảnh đó, quy trình ấy **chưa đạt chuẩn "algorithm"** và cần được làm chi tiết thêm trước khi đưa vào §6.

---

*Hết tài liệu. Khuyến nghị: in Mục 10 (Cheat-sheet) ra 1 trang A4 riêng để ôn lại mỗi ngày trước khi luyện đề theo Mục 11.*
