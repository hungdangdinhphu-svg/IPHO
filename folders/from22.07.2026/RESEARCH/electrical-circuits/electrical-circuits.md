# THUẬT TOÁN GIẢI MẠCH ĐIỆN OLYMPIC VẬT LÝ
### (Áp dụng cho: VPhO, Kỳ thi chọn Đội tuyển HSG THPT, và làm nền cho IPhO)
### Đối tượng: học sinh có trực giác Vật Lý **trung bình**, nhưng **kỷ luật, tuân thủ quy trình tuyệt đối**

---

## 0. Mục tiêu tài liệu

Tài liệu này **không dạy Vật Lý mạch điện từ đầu**. Nó dạy một **quy trình đóng khung (algorithm)** để chuyển *bất kỳ* bài toán mạch điện (trong phạm vi resistor + battery + ammeter + voltmeter, mở rộng sang tụ/cuộn cảm/AC ở mục 8) thành một **hệ phương trình tuyến tính**, rồi giải hệ đó **bằng máy tính cầm tay** — không cần "trực giác toán học" hay "biến đổi đại số khéo léo".

Triết lý nền tảng (đã nêu trong đề bài của bạn): một quy trình chỉ được gọi là "algorithm" nếu nó thỏa **cả hai** điều kiện:

1. **Tổng quát (general-purpose)** — áp dụng được cho *hầu hết mọi* bài trong lớp bài toán đã định nghĩa, không phải chỉ vài bài "đẹp".
2. **Cơ giới (mechanical)** — mỗi bước đều là một hành động rõ ràng, không đòi hỏi "nhìn ra" hay "đoán" điều gì; một học sinh trung bình theo đúng từng bước là ra được điểm số, không cần trực giác vượt trội.

Bất kỳ chỗ nào trong tài liệu này còn đòi hỏi phán đoán, nó sẽ được **thay bằng một câu hỏi rẽ nhánh có/không** trong cây quyết định ở Mục 4, để loại bỏ heuristic tối đa.

---

## 1. Vì sao thuật toán này luôn tồn tại — nền tảng chứng minh

Đây là điều **bắt buộc phải hiểu trước khi tin tưởng quy trình**, vì đề bài của bạn yêu cầu "phải chứng minh chặt chẽ", không chỉ đưa ra mẹo.

Trong tài liệu *Electrical Circuits* (Jaan Kalda) mà bạn gửi, **fact 6** phát biểu: nếu biết hết mọi điện trở và mọi suất điện động, và coi dòng điện trong từng nhánh là ẩn số, thì **định luật Kirchhoff (K1, K2) + định luật Ohm tạo thành một hệ phương trình tuyến tính đóng (closed set)** — nghĩa là:

- Số phương trình độc lập **luôn bằng** số ẩn số (dòng điện các nhánh);
- Hệ **luôn có nghiệm duy nhất**.

Đây chính là **định lý tồn tại** cho thuật toán: với **bất kỳ mạch nào** chỉ gồm điện trở + nguồn (kể cả mạch cầu, mạch vô hạn tuần hoàn, mạch không đối xứng...), việc "giải mạch" **luôn** quy được về "giải một hệ phương trình tuyến tính". Không có bài nào trong lớp bài toán này đòi hỏi phải "sáng tạo" ra vật lý mới — chỉ cần thiết lập đúng hệ và giải đúng hệ.

**Hệ quả trực tiếp:** công việc của học sinh chỉ còn hai việc, cả hai đều cơ giới hóa được:

- **(A)** Thiết lập hệ phương trình sao cho *càng ít ẩn càng tốt, càng dễ nhập máy tính càng tốt* → Mục 4 (chọn kỹ thuật).
- **(B)** Đảm bảo hệ đó **tuyến tính** (không có tích của hai ẩn) rồi giải bằng máy tính → Mục 5 (nguyên tắc tuyến tính hoá).

Phần "trực giác Vật Lý" duy nhất còn sót lại là: *chọn ẩn số nào để hệ ít phương trình nhất và tuyến tính*. Đây là phần được huấn luyện qua cây quyết định ở Mục 4 — nó **không phải sáng tạo tự do**, mà là **tra bảng** theo đặc điểm mạch.

---

## 2. Pipeline tổng thể — 3 giai đoạn

```
ĐỀ BÀI (hình vẽ mạch + dữ kiện)
        │
        ▼
GIAI ĐOẠN 1 — TRÍCH XUẤT (≈ 30 giây – 2 phút)
  Chuẩn hoá mạch: gán nhãn mọi nút/điện trở/nguồn,
  liệt kê Biết – Cần tìm – Ẩn số bắt buộc
        │
        ▼
GIAI ĐOẠN 2 — CÂY QUYẾT ĐỊNH (≈ 1–3 phút)
  Dò qua các câu hỏi có/không về cấu trúc mạch
  → chọn đúng 1 (hoặc kết hợp) kỹ thuật trong 9 kỹ thuật chuẩn
  → thu được hệ phương trình ĐẠI SỐ (chưa chắc tuyến tính)
        │
        ▼
GIAI ĐOẠN 3 — TUYẾN TÍNH HOÁ + MÁY TÍNH (≈ 3–8 phút)
  Áp "Nguyên tắc tuyến tính hoá" để chọn đúng bộ ẩn số
  → nhập hệ số vào Casio fx-580VNX (EQN / Matrix)
  → đọc nghiệm, suy ra đại lượng đề hỏi
        │
        ▼
     ĐÁP SỐ
```

Tổng thời gian mục tiêu: **dưới 10–15 phút/bài**, kể cả bài khó, vì không có bước nào phụ thuộc "nghĩ ra ý tưởng".

---

## 3. GIAI ĐOẠN 1 — Trích xuất thông tin bắt buộc

Đây là bước thay thế cho "trực giác đọc đề" của học sinh giỏi. Làm **theo đúng thứ tự**, viết ra giấy nháp, không bỏ bước nào:

### Bước 1.1 — Dán nhãn toàn bộ mạch (idea 5 + kỹ thuật vẽ lại của Kalda)
- Gán chữ cái cho **mọi điện trở** (kể cả điện trở trong của nguồn, ampe kế, vôn kế nếu không lý tưởng): `a, b, c, ...`
- Gán số cho **mọi nút** (2 điểm nối bằng dây trơn = cùng 1 nhãn nút).
- Nếu có nhiều nguồn, gán nhãn cho từng nguồn: `E1, E2, ...`

### Bước 1.2 — Phân loại từng phần tử đo (idea 7)
Với mỗi ampe kế / vôn kế / nguồn trong đề, trả lời:
- Đề có nói "lý tưởng" không? → Nếu **không nói gì** và đây là bài lý thuyết Olympic (không phải bài có số liệu đo thực tế "kỳ lạ") → mặc định **lý tưởng** (ampe kế R=0, vôn kế R=∞, nguồn r=0).
- Nếu đề cho **số liệu đo** mà dùng giả thiết lý tưởng sẽ **vô lý/mâu thuẫn** → đây là tín hiệu phải dùng non-ideal (idea 7).

### Bước 1.3 — Liệt kê 3 danh sách
Viết chính xác 3 danh sách sau, không thêm không bớt:

| Danh sách | Nội dung |
|---|---|
| **BIẾT** | Mọi giá trị số/ký hiệu đề cho: R, E, r, I, V,... |
| **CẦN TÌM** | Đại lượng đề hỏi (dòng qua 1 nhánh? điện trở tương đương? công suất?...) |
| **ẨN SỐ BẮT BUỘC** | Những đại lượng **không biết nhưng bắt buộc phải xuất hiện** để tính ra "CẦN TÌM" |

### Bước 1.4 — Kiểm tra đủ dữ kiện (idea 3)
Nếu (BIẾT) có vẻ **thiếu** so với số ẩn cần thiết → **đừng dừng lại**. Gán tạm các đại lượng còn thiếu là ẩn số phụ (VD: U, R chưa cho) — theo idea 3, các đại lượng "thiếu" thường sẽ **tự triệt tiêu** ở bước rút gọn cuối. Đây là hành động cơ giới, không phải phỏng đoán: *hễ thiếu dữ kiện thì luôn gán ẩn tạm, không bao giờ bỏ cuộc vì "đề thiếu số liệu".*

### Bước 1.5 — Phát hiện đối xứng (idea 19, 22)
Trả lời có/không:
- Mạch có trục/tâm đối xứng hình học không?
- Nếu đổi chỗ 2 nhánh mà mạch **trông y hệt**, thì hai nút đó có cùng điện thế không?

→ Nếu có đối xứng: đánh dấu ngay, việc này sẽ **giảm số ẩn** ở Giai đoạn 2 (dùng idea 20/21: node-merging, edge-splitting).

**Kết thúc Giai đoạn 1** trong dưới 2 phút, bạn phải có: mạch đã dán nhãn đầy đủ + 3 danh sách + cờ đối xứng (có/không).

---

## 4. GIAI ĐOẠN 2 — Cây quyết định chọn kỹ thuật giải

Đi từ trên xuống, dừng ở câu hỏi đầu tiên trả lời "CÓ". Mỗi nhánh dẫn tới **đúng một kỹ thuật chuẩn** (ký hiệu **[K1]**–**[K9]**), tương ứng các *idea* trong tài liệu Kalda.

```
Q1. Mạch có phần "thừa" không nối tới phần còn lại
    ngoại trừ đúng 1 dây (dangling end)?
    → CÓ: cắt bỏ phần đó (dòng qua = 0), quay lại Q1.
                                                   [idea 1]

Q2. Sau khi dọn Q1, mạch có rút gọn hoàn toàn được
    về series/parallel (không còn cầu nào)?
    → CÓ: dùng  [K1] Rút gọn Series–Parallel.  DỪNG.
                                                   [idea 1, idea 5]

Q3. Có ampe kế lý tưởng (R=0) hoặc vôn kế lý tưởng (R=∞)
    nằm đúng ở vị trí "cầu" của mạch?
    → CÓ: 
        - ampe kế ở cầu → CHẬP (short) nhánh đó, giải mạch rút gọn,
          rồi suy ngược dòng qua ampe kế bằng K1 tại nút đó.
        - vôn kế ở cầu → CẮT (open) nhánh đó, giải mạch rút gọn,
          rồi suy ngược điện áp vôn kế bằng K2 dọc mạch.
        Quay lại Q2 với mạch đã đơn giản hoá.        [idea 6]

Q4. Có đối xứng khiến 2 nút chắc chắn cùng điện thế
    (hoặc 1 nhánh chắc chắn dòng=0)?
    → CÓ: CHẬP các nút cùng thế (node-merging) hoặc
      CẮT nhánh dòng=0 (edge-splitting nếu cần tách nút).
      Quay lại Q2.                          [idea 19, 20, 21]

Q5. Mạch chỉ có ĐÚNG 2 cực ra (2-port) và ta chỉ cần
    dòng/áp qua 1 tải nối ngoài (tải có thể thay đổi)?
    → CÓ: dùng [K2] Thevenin/Norton.  DỪNG.
                                                [idea 10, 11]

Q6. Mạch có đúng 3 cực ra và chứa hình tam giác (Δ)
    hoặc hình sao (Y) làm phức tạp việc rút gọn?
    → CÓ: dùng [K3] Biến đổi Y↔Δ  rồi quay lại Q2.
                                                [idea 9]

Q7. Mạch có nhiều nguồn ĐỘC LẬP và ta chỉ cần dòng/áp
    tại 1 nhánh (không cần toàn bộ nghiệm)?
    → CÓ: cân nhắc [K4] Xếp chồng (Superposition) —
      giải lần lượt với từng nguồn, cộng kết quả.
      (Chỉ dùng khi mạch ít nguồn — nếu >2 nguồn, [K5]/[K6]
       thường nhanh hơn vì đỡ phải giải lại nhiều lần.)
                                                [idea 12]

Q8. Mạch PHẲNG (vẽ được không dây nào cắt nhau) VÀ
    số vòng lặp độc lập (số ô/mặt kín) ÍT HƠN
    số nút - 1 rõ rệt?
    → CÓ: dùng [K5] Dòng điện vòng (Loop Current)
      hoặc [K5'] Streamfunction (bản phẳng của Loop Current).
      DỪNG.                                [idea 13, 14, 16]

Q9. (Mặc định — luôn đúng nếu chưa dừng ở trên)
    → dùng [K6] Điện thế nút (Node Potential Method).
      Đây là kỹ thuật "phổ quát nhất": áp dụng được cho
      MỌI mạch resistor+battery, kể cả mạch cầu, vô hạn,
      không đối xứng.                          [idea 15]
```

### Bảng tóm tắt 9 kỹ thuật chuẩn

| Ký hiệu | Tên kỹ thuật | Khi nào chọn (điều kiện đủ) | Idea Kalda |
|---|---|---|---|
| **K1** | Rút gọn Series–Parallel | Mạch không có cầu | idea 1 |
| **K2** | Thevenin / Norton | Chỉ cần 1 tải thay đổi ở 2 cực | idea 10, 11 |
| **K3** | Biến đổi Y ↔ Δ | Có nút bậc-3 khó rút gọn | idea 9 |
| **K4** | Xếp chồng (Superposition) | Nhiều nguồn độc lập, ít nguồn | idea 12 |
| **K5** | Dòng điện vòng / Streamfunction | Mạch phẳng, ít vòng lặp | idea 13, 14, 16 |
| **K6** | Điện thế nút (Node Potential) | **Mặc định phổ quát**, luôn dùng được | idea 15 |
| **K7** | Đối ngẫu (Dual circuit) | Mạch tự đối ngẫu / muốn đổi vai trò V↔I | idea 17 |
| **K8** | Mạch tuần hoàn vô hạn | Mạch lặp lại vô hạn (dạng thang) | idea 18 |
| **K9** | Cận trên/dưới (Bounding theorems) | Đề chỉ hỏi "ước lượng" R, không cần chính xác | idea 27 |

> **Ghi chú tuân thủ kỷ luật:** học sinh **không tự chọn** kỹ thuật theo "cảm giác bài nào hợp" — luôn đi đúng theo cây quyết định Q1→Q9 theo thứ tự. Việc "nhìn thấy ngay đối xứng" (Q4) hay "nhìn thấy ngay mạch phẳng ít vòng" (Q8) không đòi hỏi sáng tạo — chỉ đòi hỏi **đếm** (đếm nút, đếm vòng, so sánh hình học khi lật/xoay mạch), là việc cơ giới.

**Trong 9 kỹ thuật trên, K6 (Điện thế nút) là "phao cứu sinh phổ quát"** — nếu học sinh không chắc dùng kỹ thuật nào, luôn có thể quay lại K6 và vẫn giải được (chỉ có thể chậm hơn, không bao giờ sai hoặc bế tắc), vì K6 chính là bản dịch trực tiếp của Fact 6 (Mục 1).

---

## 5. GIAI ĐOẠN 3 — Nguyên tắc tuyến tính hoá & giải bằng Casio fx-580VNX

Đây là phần **quan trọng nhất** để bài toán không còn phụ thuộc "kỹ năng biến đổi đại số" — vốn là điểm yếu của học sinh trung bình.

### 5.1 Ba dạng phương trình nhánh có thể gặp

Mỗi nhánh nối nút *x* với nút *i* qua điện trở đóng góp một số hạng vào phương trình K1 tại nút *x*:

$$\frac{V_x - V_i}{R_i}$$

Tuỳ vào **cái gì đã biết, cái gì là ẩn**, số hạng này rơi vào đúng 1 trong 3 dạng:

**Dạng A — chỉ TỬ SỐ có ẩn (điện thế V chưa biết, R đã biết).**
→ Đây là trường hợp chuẩn của Node Potential Method (K6). Khai triển:

$$\left(\frac{1}{R_1}+\frac{1}{R_2}+\frac{1}{R_3}\right)V_x - \frac{1}{R_1}V_1 - \frac{1}{R_2}V_2 - \frac{1}{R_3}V_3 = 0$$

→ **Tuyến tính sẵn** theo các V ẩn, vì hệ số $1/R_i$ là số đã biết. Nhập thẳng vào máy tính.

**Dạng B — chỉ MẪU SỐ có ẩn (điện thế V đã biết/đo được, điện trở R chưa biết).**
→ Đặt ẩn phụ **G_i = 1/R_i** (điện dẫn). Khi đó số hạng trở thành $(V_x-V_i)\cdot G_i$, và vì $V_x, V_i$ đã biết, đây **cũng là tuyến tính theo G_i**. Nhập hệ số $(V_x-V_i)$ đã biết, ẩn là $G_i$, giải ra $G_i$ rồi lấy nghịch đảo: $R_i = 1/G_i$.

**Dạng C — cả TỬ và MẪU đều có ẩn (hỗn hợp, nhiều phương trình có loại khác nhau trong cùng hệ).**
→ **Không khai triển đại số.** Thay vào đó, đặt **nguyên cả cụm phân số làm 1 ẩn số dòng điện**:

$$I_x \equiv \frac{V_x - V_i}{R_x}$$

Phương trình K1 tại mỗi nút bây giờ chỉ là **tổng đại số của các $I_x$ đã đặt = 0** → luôn tuyến tính, bất kể bên trong mỗi $I_x$ có bao nhiêu ẩn không tuyến tính với nhau. Sau khi giải ra các $I_x$ bằng máy tính, quay lại **từng nhánh riêng lẻ** và dùng định luật Ohm đơn giản (1 ẩn, không phải hệ) để suy ra đại lượng còn thiếu của nhánh đó ($V$ hoặc $R$).

### 5.2 Nguyên tắc tổng quát (áp dụng được cho MỌI bài, không chỉ 3 dạng trên)

> **NGUYÊN TẮC TUYẾN TÍNH HOÁ:**
> Không bao giờ để một phương trình chứa **tích của hai đại lượng cùng chưa biết**. Nếu một số hạng sắp vi phạm điều này, hãy **đặt nguyên số hạng đó (thường là 1 dòng điện nhánh) làm MỘT ẩn số mới**, đưa nó vào hệ phương trình tuyến tính chính (K1/K2 dạng dòng điện), giải hệ đó trước bằng máy tính; sau đó dùng định luật Ohm **từng nhánh một cách độc lập** (không phải giải hệ nữa, chỉ là 1 phép chia) để tách 2 đại lượng bên trong ẩn số gộp đó.

Nói cách khác: **luôn ưu tiên hệ ẩn = dòng điện các nhánh** (đây chính là bản chất method of loop currents / branch currents, K5) khi thấy hệ điện-thế-ẩn (K6) sẽ bị phi tuyến vì R cũng là ẩn. Việc "khi nào chọn V làm ẩn, khi nào chọn I làm ẩn, khi nào chọn G=1/R làm ẩn" **không phải trực giác** — tra đúng theo bảng dưới:

| Cái đã biết | Cái là ẩn | Chọn ẩn số để nhập máy tính | Dạng |
|---|---|---|---|
| R | V (điện thế nút) | V | A |
| V | R (hoặc G=1/R) | G = 1/R | B |
| — (cả V và R đều lẫn ẩn/biết xen kẽ) | I (dòng nhánh) | I (từng nhánh) | C |
| I | R hoặc V | thay trực tiếp I vào PT, còn lại là A hoặc B | A/B |

### 5.3 Quy trình bấm máy Casio fx-580VNX (hoặc fx-880/991-series tương đương)

**Bước 1 — Đếm số ẩn số n** sau khi đã áp Mục 5.1–5.2 (n = số nút chưa biết thế, hoặc số dòng vòng độc lập, hoặc số G/R chưa biết...).

**Bước 2 — Chọn chế độ theo n:**

- **n = 2, 3, hoặc 4:** dùng **MODE → Equation/Table → Simultaneous Equation (hệ phương trình bậc nhất n ẩn)**. Nhập trực tiếp các hệ số $a_{ij}$ và vế phải $b_i$ của hệ:
$$a_{11}x_1+a_{12}x_2+\dots = b_1,\quad a_{21}x_1+\dots=b_2,\ \dots$$
  Máy trả về nghiệm $x_1, x_2,\dots$ ngay lập tức, không cần tính tay.

- **n ≥ 5:** máy không còn hỗ trợ EQN trực tiếp → chuyển sang **MODE → Matrix**: viết hệ dưới dạng $A\vec{x}=\vec{b}$, nhập ma trận $A$ (n×n) và vector $\vec{b}$, rồi tính $\vec{x} = A^{-1}\vec{b}$ bằng phím nghịch đảo ma trận (`Mat A`⁻¹ `×` `Mat B`). Đây là **cùng một thuật toán**, chỉ khác giao diện nhập liệu — không có gì mới phải học.

**Bước 3 — Kiểm tra sai số nhập liệu:** Ma trận hệ số của Node Potential Method luôn có tính chất: **tổng các phần tử trên mỗi hàng ứng với hệ số của chính $V_x$ trừ đi tổng các hệ số còn lại = 0** nếu không có dòng "rò" ra khỏi nút đó ngoài các nhánh đã liệt kê. Dùng tính chất này để dò lỗi gõ nhầm dấu/hệ số trước khi tin kết quả.

**Bước 4 — Suy ngược đại lượng đề hỏi.** Sau khi có nghiệm số của hệ (V, I, hoặc G), tính đại lượng đề hỏi bằng 1–2 phép toán đơn giản (Ohm, công suất $P=UI$, Thevenin...). Đây **không còn là "giải toán" nữa** — chỉ là thay số.

### 5.4 Ví dụ mẫu — 3 dạng, tái hiện logic đã minh hoạ

**(a) Dạng A (R biết, V ẩn):** nút $x$ nối 3 điện trở $R_1,R_2,R_3$ tới 3 nút có thế $V_1,V_2,V_3$ (một trong số đó có thể cũng là ẩn):
$$\left(\tfrac1{R_1}+\tfrac1{R_2}+\tfrac1{R_3}\right)V_x-\tfrac1{R_1}V_1-\tfrac1{R_2}V_2-\tfrac1{R_3}V_3=0$$
→ Nhập thẳng hệ số $\tfrac1{R_i}$ (đã biết) vào EQN.

**(b) Dạng B (V biết, R ẩn):** cùng cấu trúc nhưng $V_x,V_1,V_2,V_3$ đều đo được, $R_1,R_2,R_3$ chưa biết. Đặt $G_i=1/R_i$:
$$(V_x-V_1)G_1+(V_x-V_2)G_2+(V_x-V_3)G_3=0$$
→ Hệ số $(V_x-V_i)$ đã biết (số), ẩn là $G_i$ — nhập EQN, giải ra $G_i$, rồi $R_i=1/G_i$.

**(c) Dạng C (hỗn hợp):** một số nhánh biết R (ẩn V), một số nhánh biết V (ẩn R), lẫn trong cùng 1 nút. Đặt $I_x=(V_x-V_1)/R_1$ cho **nhánh gây rắc rối**, viết K1 tại nút đó dưới dạng tổng các dòng (đã biết hoặc đã đặt ẩn $I$) $=0$ — luôn tuyến tính theo các $I$. Giải xong, quay lại từng nhánh: nếu nhánh đó biết $R$ thì $V_1 = V_x - I_xR_1$; nếu biết $V$ thì $R_1=(V_x-V_1)/I_x$.

---

## 6. Bảng tra cứu nhanh toàn bộ 31 "idea" (mạch thuần trở, idea 1–31)

Dùng bảng này như một **chỉ mục tra khi bí**, sau khi đã chạy cây quyết định Mục 4:

| Idea | Nội dung cốt lõi | Gắn với kỹ thuật |
|---|---|---|
| 1 | Rút gọn series/parallel + xoá dangling end | K1 |
| 2 | Đại lượng vật lý = diện tích dưới đồ thị (tích phân) | Bài dạng đặc biệt (dây không đều) |
| 3 | Giả sử "biết" dữ kiện còn thiếu, nó sẽ tự triệt tiêu | Bước 1.4 |
| 4 | Kirchhoff áp dụng được cho **độ biến thiên** ΔV, ΔI | Bài "trước/sau khi thêm phần tử" |
| 5 | Vẽ lại mạch cho rõ cấu trúc song song/nối tiếp | Bước 1.1 |
| 6 | Ideal ammeter/voltmeter ở cầu → chập/cắt | Q3 |
| 7 | Non-ideal ammeter/voltmeter → thêm R nối tiếp/song song | Bước 1.2 |
| 8 | K1 áp dụng cho **cả một vùng**, không chỉ 1 nút | Kiểm tra nhanh |
| 9 | Biến đổi Y ↔ Δ | K3 |
| 10 | Định lý Thevenin | K2 |
| 11 | Định lý Norton (nguồn dòng tương đương) | K2 |
| 12 | Nguyên lý xếp chồng | K4 |
| 13 | Phương pháp dòng điện vòng | K5 |
| 14 | Ép dòng I hoặc áp V vào 2 cực để tính R = V/I | Khi đề hỏi "điện trở giữa 2 điểm" |
| 15 | Phương pháp điện thế nút | K6 |
| 16 | Streamfunction (bản đối ngẫu của loop current, cho mạch phẳng) | K5' |
| 17 | Đối ngẫu mạch (duality V↔I) | K7 |
| 18 | Mạch tuần hoàn vô hạn: bỏ 1 chu kỳ đầu, dùng tự đồng dạng | K8 |
| 19 | Phát hiện & khai thác đối xứng | Bước 1.5 |
| 20 | Node-merging: chập 2 nút cùng thế | Q4 |
| 21 | Edge-splitting: tách 1 điện trở thành 2 song song | Q4 |
| 22 | Xếp chồng để đối xứng hoá bài không đối xứng | Bài dạng lưới vô hạn |
| 23 | Điện trở âm giả định để giữ đối xứng | Bài "mạch thiếu 1 cạnh" |
| 24 | Đồ thị I–V cho phần tử phi tuyến (diode...) | Mở rộng phi tuyến |
| 25 | Điện trở vi phân $R_{diff}=dV/dI$ | Mở rộng phi tuyến |
| 26 | Tuyến tính hoá quanh điểm làm việc | Mở rộng phi tuyến |
| 27 | Cận trên/dưới của điện trở (biến phân cực trị công suất) | K9 |
| 28 | Diode lý tưởng: xét 2 trường hợp (dẫn/không dẫn) | Mạch có diode |
| 29 | Diode có ngưỡng $V_c$: thay bằng nguồn $E=V_c$ | Mạch có diode |
| 30 | Tổng mẹo "triệt tiêu" trong hệ phương trình lớn | Bài chứng minh tổng quát |
| 31 | Ổn định: dùng trực giác điện cảm/tụ khi phân tích phi tuyến | Mở rộng (Mục 8) |

---

## 7. Ví dụ áp dụng toàn bộ pipeline (end-to-end, minh hoạ tốc độ ~10 phút)

**Đề bài mẫu (tương tự pr 13 trong Kalda):** Tìm điện trở giữa 2 cực của mạch gồm $2\,\Omega, 3\,\Omega$ (nhánh trên), $5\,\Omega, 1\,\Omega$ (nhánh dưới), và $4\,\Omega$ nối giữa (cầu).

**GIAI ĐOẠN 1 (30s):**
- Nhãn: nút trái = A (cực vào), nút phải = B (cực ra), nút giữa trên/dưới của cầu = C, D.
- BIẾT: 5 điện trở. CẦN TÌM: $R_{AB}$. ẨN BẮT BUỘC: theo idea 14, ép dòng $I$ vào A, ra B, cần tìm $V_{AB}$, rồi $R=V_{AB}/I$.
- Đối xứng: không có đối xứng rõ ràng (5 điện trở khác nhau) → không dùng Q4.

**GIAI ĐOẠN 2:**
- Q1: không có dangling end. Q2: có cầu ($4\,\Omega$) → không rút gọn ngay được → không dừng ở K1.
- Q3: không có ampe/vôn kế lý tưởng ở cầu.
- Q4: không đối xứng.
- Q5: không phải bài Thevenin (đề hỏi thẳng $R_{AB}$, không có tải thay đổi) — nhưng thực chất idea 14 + node potential vẫn là cách chuẩn.
- Q8: mạch phẳng, số vòng độc lập = 2 (ít) → có thể dùng K5 (Loop Current) **hoặc** Q9 → K6 (Node Potential). Chọn **K6** vì tổng quát và ít lỗi hơn khi học sinh chưa quen chọn vòng độc lập.

→ Kỹ thuật: **K6 — Node Potential**, kết hợp **idea 14** (ép dòng $I$, tìm $V_{AB}$).

**GIAI ĐOẠN 3:**
- Đặt $V_A = V$ (biết, do ta chủ động ép), $V_B=0$ (gốc), ẩn số: $V_C, V_D$ (2 ẩn — **Dạng A**, vì mọi $R$ đã biết).
- Viết K1 tại C và D theo mẫu $\left(\sum \tfrac1{R}\right)V_C - \sum\tfrac{V_i}{R} = (\text{dòng ngoài vào C, nếu có})$.
- 2 phương trình, 2 ẩn ($V_C, V_D$) → nhập **EQN 2 ẩn** trên Casio fx-580VNX.
- Giải ra $V_C, V_D$ bằng số → tính dòng vào tại A: $I = \sum \tfrac{V_A - V_{\text{nút kề A}}}{R}$.
- $R_{AB} = V_A/I$ (vì $V_B=0$).

→ Ra đáp số bằng **thao tác máy tính thuần túy**, không cần "nhìn ra mẹo cầu Wheatstone" hay giải tay hệ 2 ẩn.

---

## 8. Mở rộng: khi đề vượt phạm vi thuần điện trở (Tụ điện, Cuộn cảm, AC)

Nếu đề bài chọn đội tuyển/VPhO có tụ điện, cuộn cảm, hoặc dòng xoay chiều, pipeline **không đổi bản chất** — chỉ mở rộng "từ điển tra cứu" ở Mục 6:

| Tình huống | Kỹ thuật tương ứng | Idea |
|---|---|---|
| Mạch DC ổn định lâu (steady-state), có tụ/cuộn cảm | idea 38: tụ → hở mạch (ngắt), cuộn cảm → ngắn mạch (dây) → quay lại pipeline thuần trở ở Mục 4–5 | 38 |
| Ngay sau khi đóng/mở khoá, thời điểm $t=0^+$ | idea 38 (chiều ngược): tụ giữ nguyên V trước đó, cuộn cảm giữ nguyên I trước đó → thay bằng nguồn V hoặc nguồn I tương đương → quay lại pipeline thuần trở | 12, 38 |
| Diễn biến theo thời gian (quá độ RC/RL/LC) | idea 36: nghiệm = nghiệm dừng (dùng idea 38) + nghiệm thuần dao động/tắt dần (dùng fact 12/13/18/19) | 36, 37 |
| Mạch AC hình sin ổn định | **idea 44**: dùng số phức, thay $R\to Z_R=R,\ Z_L=i\omega L,\ Z_C=1/(i\omega C)$, rồi **toàn bộ pipeline Mục 4–5 áp dụng y hệt** trên các trở kháng phức $Z$ thay vì $R$ | 44, 45 |
| Tần số riêng / cộng hưởng | idea 48–49: đặt $Z(\omega)=0$ hoặc $Z(\omega)=\infty$, giải phương trình đặc trưng (dùng đối xứng nếu có) | 47–49 |

**Nguyên tắc tuyến tính hoá ở Mục 5 áp dụng nguyên vẹn cho AC**, chỉ thay số thực bằng số phức khi nhập máy tính (Casio fx-580VNX có chế độ **CMPLX** hỗ trợ cộng/nhân/chia số phức trực tiếp, kể cả trong hệ phương trình nếu máy hỗ trợ hệ số phức — nếu không, tách phần thực/ảo thành 2 phương trình thực).

---

## 9. Checklist thi đấu (dán vào đầu bài làm)

- [ ] **Giai đoạn 1:** đã dán nhãn hết nút/điện trở? đã liệt kê Biết–Cần tìm–Ẩn?
- [ ] Đã kiểm tra ideal/non-ideal cho mọi ampe kế, vôn kế, nguồn?
- [ ] Đã kiểm tra đối xứng (idea 19)?
- [ ] **Giai đoạn 2:** đã đi đúng thứ tự Q1→Q9, không nhảy cóc theo "cảm giác"?
- [ ] Đã xác định đúng số ẩn số tối thiểu?
- [ ] **Giai đoạn 3:** đã kiểm tra mỗi phương trình có tích 2 ẩn không (Dạng C)? Nếu có, đã đặt ẩn dòng $I_x$ chưa?
- [ ] Đã chọn đúng chế độ máy tính theo số ẩn (EQN nếu ≤4, Matrix nếu ≥5)?
- [ ] Đã kiểm tra sai số nhập liệu (tổng hệ số hàng = 0 nếu không có dòng ngoài)?
- [ ] Đã suy ngược đúng đại lượng đề hỏi từ nghiệm số?
- [ ] Đơn vị, làm tròn, và **đối chiếu ngược lại đề bài** (đáp số có hợp lý về độ lớn không)?

---

## 10. Ánh xạ bài luyện tập (pr1–pr111 trong Kalda) theo kỹ thuật cần rèn

Dùng để **luyện từng kỹ thuật riêng lẻ** trước khi luyện tổng hợp:

| Kỹ thuật | Bài nên luyện (số hiệu `pr` trong tài liệu Kalda) |
|---|---|
| K1 — Series/Parallel | pr 1, 2 |
| K1 + vẽ lại mạch (idea 5) | pr 3, 4 |
| Q3 — ideal ammeter/voltmeter ở cầu (idea 6) | pr 5 |
| idea 7 — non-ideal thiết bị đo | pr 6, 7 |
| K3 — Y↔Δ | pr 8, 12 (ghi chú), 21, 22 |
| K2 — Thevenin/Norton | pr 9, 10, 11, 17 |
| K4 — Superposition | pr 12 |
| K5 — Loop current / Streamfunction | pr 13, 14 |
| K6 — Node potential | pr 14 (đối chiếu), 39 |
| K7 — Đối ngẫu | pr 15 |
| K8 — Mạch tuần hoàn vô hạn | pr 16, 20, 51 |
| Q4 — đối xứng (idea 19–22) | pr 18, 19, 20, 21 |
| idea 23 — điện trở âm | pr 22, 47 |
| K9 — cận trên/dưới | pr 26, 27, 50, 53 |
| idea 24–29 — phi tuyến, diode | pr 23, 24, 25, 28, 29, 31, 32 |
| Tổng hợp nhiều nút/ẩn (rèn tốc độ bấm máy) | pr 33–43 |
| Lưới vô hạn (2D) | pr 45, 46, 47 |
| Đa giác đều / n-gon | pr 48, 49, 50, 54 |
| Mục 8 — quá độ RC/RL | pr 57–68, 71–74 |
| Mục 8 — LC dao động | pr 62, 63, 69, 80 |
| Mục 8 — hỗ cảm/biến áp | pr 70, 85, 88 |
| Mục 8 — AC ổn định, cộng hưởng | pr 86–111 |

---

### Ghi chú cuối cùng cho giảng viên

Tài liệu này biến bài toán "học Vật Lý mạch điện" thành bài toán "tuân thủ đúng quy trình 3 giai đoạn". Phần duy nhất học sinh cần **luyện tập nhiều lần đến mức phản xạ** là:

1. Dán nhãn mạch nhanh, chính xác (Giai đoạn 1) — luyện bằng cách vẽ lại 20–30 mạch bất kỳ trong 1–2 phút/mạch.
2. Trả lời đúng 9 câu hỏi có/không của cây quyết định (Giai đoạn 2) — luyện bằng flashcard "cho mạch X, trả lời Q1–Q9".
3. Nhận diện Dạng A/B/C và bấm máy đúng chế độ (Giai đoạn 3) — luyện bằng cách giải lại các hệ 2–4 ẩn thuần túy trên Casio, tách rời khỏi ngữ cảnh Vật Lý, cho tới khi thao tác máy < 1 phút/hệ.

Khi cả 3 kỹ năng trên đạt phản xạ, thời gian giải 1 bài Olympic mạch điện — bất kể độ khó — sẽ hội tụ về ngưỡng 10–15 phút như mục tiêu đề ra, đúng như luận điểm ban đầu của bạn.
