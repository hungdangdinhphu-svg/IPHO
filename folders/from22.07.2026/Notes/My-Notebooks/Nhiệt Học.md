# NHIỆT HỌC — Vấn đề 1 & Vấn đề 2

> **Thư viện CÔNG CỤ · họ precondition · thuật toán quét CHỖ · ánh xạ Vật Lý → Toán**
>
> - Phạm vi: chỉ phần **Nhiệt** (17 chủ đề trong bảng syllabus bạn gửi: Nhiệt phần 1 + Nhiệt phần 2).
> - Nhiệm vụ: chỉ **Vấn đề 1** (nhận diện CÔNG CỤ + tiền xử lý) và **Vấn đề 2** (chuyển Vật Lý → Toán). **Vấn đề 3 (giải Toán) cố ý dừng trước bước giải.**
> - Mục tiêu kép: HSGQG Vật Lý Việt Nam + IPhO + nền tảng Vật Lý thực sự.

---

## MỤC LỤC

- **§0** Đọc trước: cam kết trung thực, cách đọc syllabus, quy ước, quy trình tổng
- **§1** Khung hình thức cho Nhiệt: M, Dom/Pre/Suf/Post/Err, **phân loại CHỖ**, thuật toán SCAN, chẩn đoán bế tắc, ràng buộc ẩn, đếm ẩn
- **§2** Tiền xử lý (Vấn đề 1 "tiện thể"): P1–P12 + từ điển "lời đề bài → điều kiện mô hình"
- **§3** Thư viện CÔNG CỤ: T01–T17 (đúng theo 17 hàng syllabus) + X1–X6 (công cụ kề cận)
- **§4** Vấn đề 2: bảng dịch Vật Lý → Toán, sổ cái bảo toàn, 9 thuật toán "kiểu Nodal Analysis" cho Nhiệt
- **§5** Khi nhiều "dạng" cùng lúc: ghép công cụ qua biến giao diện
- **§6** Chín ví dụ hoàn chỉnh (V1 + V2, dừng trước V3)
- **§7** Bảng tra nhanh: dấu hiệu → công cụ; 30 lỗi kinh điển
- **§8** Hạn chế, phần trực giác còn sót lại, kế hoạch kiểm chứng
- **Phụ lục** A: tích phân; B: trị số cỡ; C: ánh xạ syllabus; D: tài liệu; E: phiếu quét CHỖ (mẫu điền)

---

# §0. ĐỌC TRƯỚC

## 0.1. Cam kết trung thực (không "reward hacking")

Mỗi mệnh đề quan trọng trong tài liệu mang một nhãn:

| Nhãn | Ý nghĩa |
|---|---|
| **[CHUẨN]** | Kiến thức đã được thiết lập rộng rãi trong giáo trình (có thể tra ở sách mục D). |
| **[ĐỀ XUẤT]** | Cấu trúc/quy trình do tôi đề xuất **trong khung của bạn**. Chưa được kiểm chứng trên một tập đề thi thật. Đây là giả thuyết làm việc, không phải định lý. |
| **[CẦN KIỂM]** | Tôi không chắc hoàn toàn, hoặc phụ thuộc quy ước/cách hiểu đề. Bạn nên kiểm lại. |

Những điều tôi làm và không làm, nói thẳng:

1. **Kiểm chứng bằng máy.** Các công thức/đồng nhất thức tôi *tự suy ra* đã được kiểm bằng sympy/numeric trước khi đưa vào: nhiệt dung đa biến `C = C_V + R/(1−n)`; điều kiện `dQ = 0` ⇔ `γp + V·p′ = 0`; nhiệt độ khi thoát hạt đoạn nhiệt `T ∝ N^{1/i}`; hằng số tới hạn vdW và dạng thu gọn; đoạn nhiệt vdW `T(v−b)^{R/C_V} = const`; nhiệt độ cuối `T_f = T₁^{C₁/(C₁+C₂)}·T₂^{C₂/(C₁+C₂)}`; nghiệm Stefan `x² = 2κΔT·t/(ρλ)`; hiệu suất Otto/Diesel (so với mô phỏng số); độ dốc đường nóng chảy của nước `≈ −13,5 MPa/K`; tỉ lệ `PE/W = 1/2` khi mao dẫn; các tích phân Maxwell/bán cầu; ví dụ nhiệt lượng kế (§6.A). Công thức "sách giáo khoa" khác tôi không tái kiểm bằng máy, nên chúng chỉ mang nhãn [CHUẨN].
2. **Không có đề thi thật nào bị trích.** Toàn bộ ví dụ là tôi tự soạn theo *dạng*, không phải đề HSGQG/IPhO có thật. Tôi không nhắc "đề năm X câu Y".
3. **Không có thuật toán vạn năng.** Tôi liệt kê rõ ở §8 phần trực giác *vẫn còn* sau khi dùng khung này. Đúng tinh thần "đến đây là tốt rồi" của bạn: giảm chứ không xoá.
4. **Không có link GitHub.** Tôi không mở link repo trong README. Tôi chỉ dựa vào file `.md` và ảnh syllabus bạn gửi. File này là bản để bạn đặt vào đúng thư mục.
5. **Vấn đề 3 không được giải.** Nhiều chỗ tôi dừng ngay khi bài đã thành "bài Toán rõ ràng". Nếu ở đâu đó tôi lỡ ghi kết quả (ví dụ vài đáp số cho bạn tự đối chiếu), tôi đánh dấu là *đối chiếu*.

## 0.2. Đọc bảng syllabus (từ ảnh) và ba chỗ tôi phải diễn giải

Bảng có 17 hàng (Nhiệt phần 1: 4 hàng Vật lí nhiệt + 7 hàng Khí lí tưởng; Nhiệt phần 2: 6 hàng). Tôi giữ nguyên thứ tự và gán mã **T01–T17** (Phụ lục C).

**[CẦN KIỂM] ba chỗ mơ hồ:**

1. **"Bài toán xét vi phân dải khí"** (hàng b.3). Tôi hiểu là *bài toán xét một lớp/dải khí vi phân*: viết cân bằng cho phần tử `dz` (hoặc `dr`, `dx`) rồi ra phương trình vi phân. Ví dụ: khí quyển, cột khí trong trường ngoài, ống quay, khí có gradient nhiệt độ. Nếu ý bạn khác (ví dụ "dải" theo nghĩa khác), hãy báo.
2. **"khí kém"** (Nhiệt phần 2, hàng 5: "Động học phân tử chất khí nâng cao, khí kém"). Đây không phải thuật ngữ tôi chắc chắn. Tôi diễn giải là **khí loãng** (rarefied gas, quãng đường tự do trung bình không nhỏ so với kích thước hệ, Kn không nhỏ). Tôi cũng phủ luôn cách hiểu **"khí kém lí tưởng"** qua T14 và T16. Cách nào cũng được phủ, nhưng hãy xác nhận.
3. **Ảnh bị cắt ở đáy.** Hàng cuối nhìn thấy là "Phương trình Clapeyron–Clausius", và cột trái vẫn tiếp tục xuống dưới. Có thể còn hàng khác (ví dụ bức xạ nhiệt, entropy nâng cao, chuyển pha bậc hai) chưa nhìn thấy. Tôi đã thêm các công cụ kề cận X1–X6 phòng trường hợp đó, nhưng nếu còn hàng, hãy gửi thêm.

Ngoài ra hàng "Nguyên lí thứ 2 … hiệu suất cực đại,…" có dấu "…". Tôi coi **entropy** là thuộc phạm vi (IPhO gần như chắc chắn cần).

## 0.3. Quy ước ký hiệu & dấu (phải nhất quán, ghi ở đầu mọi lời giải)

- `W` = **công do khí (hệ) sinh ra** (giãn: W > 0). `Q` = **nhiệt hệ nhận vào**. Nguyên lí 1: **`ΔU = Q − W`**.
  Sách giáo khoa Việt Nam thường viết `ΔU = A + Q` với `A` là công **nhận vào**, nên `A = −W`. Đây là nguồn nhầm dấu số một; **chọn một quy ước và ghi rõ**.
- `ν` số mol; `N` số phân tử; `n = N/V` mật độ số; `μ` khối lượng mol (kg/mol); `m` khối lượng phân tử (hoặc khối lượng, ghi rõ theo ngữ cảnh).
- `i` số bậc tự do "đang hoạt động"; `C_V = iR/2`, `C_p = C_V + R`, `γ = C_p/C_V = 1 + 2/i` (mol). `c` = nhiệt dung **riêng** (J/kg·K). Mol dùng chữ hoa, riêng dùng chữ thường.
- `T` luôn **Kelvin** khi vào công thức khí. `k = R/N_A`.
- `p_sat(T)` áp suất hơi bão hoà; `p_v` áp suất riêng phần của hơi; `f = p_v/p_sat` độ ẩm tương đối.
- `Kn = λ/L` số Knudsen; `Bo = ρgr²/σ` số Bond; `Bi = hL_c/κ` số Biot; `St = cΔT/L_ẩn` số Stefan.

## 0.4. Quy trình tổng (một dòng cho mỗi bước; chi tiết ở các mục sau)

```
B0. Đọc đề → lập danh sách thực thể (hệ, thành, nguồn nhiệt, pittông, ...)          [§1.1, §2 P1-P2]
B1. Dịch lời đề → điều kiện mô hình (chậm? cách nhiệt? có lỏng dư? ...)             [§2.2]
B2. Lập KHO CHỖ: hệ / trạng thái / quá trình / giao diện / thời điểm / vi phân /     [§1.3]
    chu trình / ranh giới pha / sự kiện vi mô / sổ cái bảo toàn
B3. SCAN: với mỗi công cụ trong thư viện, duyệt mọi CHỖ cùng loại, xét Pre/Suf       [§1.4, §3]
B4. Thu phương trình; lọc trùng; đánh dấu sai số                                     [§1.4]
B5. Kiểm tra ĐÓNG KÍN: số ẩn vs số phương trình độc lập; ràng buộc ẩn                [§1.6-1.7]
B6. Nếu thiếu → chia nhỏ CHỖ / thêm công cụ kề cận / soát lại mô hình, quay B3       [§1.5]
B7. Xuất bài Toán: (ẩn, hệ ràng buộc, cái cần tìm, miền, nhánh)                      [§4]
B8. (Vấn đề 3: giải) — ngoài phạm vi
B9. Kiểm tra sau giải: đơn vị, giới hạn, nguyên lí 2 (η ≤ Carnot), ΔS_tot ≥ 0        [§7]
```

---

# §1. KHUNG HÌNH THỨC CHO NHIỆT

## 1.1. Mô hình `M = (O, V, L, C, Q, I)` được cụ thể hoá cho Nhiệt

| Thành phần | Trong bài Nhiệt cần điền gì | Ghi chú |
|---|---|---|
| **O** (ontology) | (i) Các **hệ con**: từng phần khí (ghi riêng khi ngăn bởi pittông/vách), lỏng, rắn, hơi, nguồn nhiệt (reservoir), bình. (ii) Các **thành/vách**: cách nhiệt hay dẫn nhiệt; cứng hay di động; có ma sát hay không; thấm hay không thấm; có lỗ. (iii) **Trạng thái** (đỉnh của đồ thị trạng thái) và **quá trình** (cạnh). (iv) **Giao diện** (mặt lỏng–hơi, mặt tiếp xúc hai vật, mặt tường–khí). (v) Cấu trúc **topology**: cái nào nối với cái nào. | Sai/thiếu ở O là nguồn lỗi lớn nhất. |
| **V** (biến) | Với mỗi phần khí: `p, V, T, ν` (hoặc `N`), thêm `U, S`. Với mỗi quá trình: `Q, W, ΔU, ΔS`. Hình học: toạ độ `x, h, r`. Thời gian `t`. Tham số: `a, b, σ, κ, L, c`… Cái cần tìm. | Đánh dấu **biến độc lập** đã chọn (P9). |
| **L** (định luật) | Thư viện T01–T17 + X1–X6 (§3), mỗi cái kèm **Dom, Pre, Suf, Post, Err**. | Đây là "hộp công cụ". |
| **C** (ràng buộc) | Dữ kiện đề; điều kiện đầu/biên; đối xứng; bảo toàn; hình học (`V = A·x`); **ràng buộc ẩn** (§1.6). | Đa số bế tắc do quên ràng buộc ẩn. |
| **Q** (câu hỏi) | Xác định **loại**: giá trị số, biểu thức, đồ thị, cực trị, điều kiện tồn tại, hiệu suất, xu hướng, thời gian. | Loại Q quyết định dạng Toán đầu ra. |
| **I** (diễn giải) | Từ điển "lời đề → điều kiện mô hình" (§2.2). | "chậm", "cách nhiệt", "cân bằng", "lỗ nhỏ"… |

## 1.2. Dom, Pre, Suf, Post, Err — và một chỗ logic cần sửa trong README

Với mỗi công cụ ℓ:

- **Dom(ℓ)**: miền mà công thức *có nghĩa* (ví dụ Poisson có nghĩa cho khí lí tưởng; ra ngoài thì sai kiểu).
- **Pre(ℓ)** (điều kiện **cần**): nếu **Post(ℓ) đúng** thì Pre phải thoả. Dùng để **LOẠI** chắc chắn: *Pre sai ⇒ tuyệt đối không dùng*.
- **Suf(ℓ)** (điều kiện **đủ**, kiểm tra được, bảo thủ): nếu Suf thoả thì Post(ℓ) đúng (trong sai số Err). Dùng để **CHẤP NHẬN** chắc chắn.
- **Post(ℓ)**: kết luận (phương trình sinh ra).
- **Err(ℓ)**: đánh giá sai số/xấp xỉ; ghi *tham số nhỏ* nào chi phối (ví dụ `n·d³`, `Kn`, `Bo`, `St`, `Bi`).

Quan hệ logic **[ĐỀ XUẤT], nhưng đây chỉ là logic thuần**:

```
Suf(ℓ)  ⇒  Post(ℓ) hợp lệ  ⇒  Pre(ℓ)
```

Vì vậy quét một CHỖ cho ra **ba** kết quả, không phải hai:

| Kết quả | Điều kiện | Hành động |
|---|---|---|
| ✗ **Loại** | Pre sai | Bỏ. Ghi lý do (đây là "chẩn đoán bế tắc" §1.5). |
| ✓ **Nhận** | Suf thoả | Dùng, sinh phương trình. |
| ? **Vùng xám** | Pre thoả nhưng Suf chưa | *Chỗ duy nhất cần phán đoán.* Dùng kèm Err và ghi rõ "xấp xỉ". Nếu có thể, tính tham số nhỏ để định lượng. |

> **⚠ Chỗ có thể sai trong README (mục "7 điều kiện", điều (2) Hợp lệ).**
> README viết "Nếu Pre(ℓ) được thỏa, thì Post(ℓ) là đúng". Câu đó có dạng *"điều kiện ⇒ kết luận"*, tức là Pre đóng vai **điều kiện đủ**, nhưng README định nghĩa Pre là điều kiện **cần**. Với điều kiện cần thì chiều đúng là *Post ⇒ Pre*, không phải ngược lại.
> Gợi ý sửa: giữ **Pre = điều kiện cần (để loại)**, thêm **Suf = điều kiện đủ (để nhận)**, và chuyển câu "Nếu … thì Post đúng" cho **Suf**. Đây cũng là cách dùng chữ "precondition" trong lập trình (Hoare triple `{Pre} S {Post}` nghĩa là *Pre ⇒ Post sau S*: ở đó Pre thực chất là điều kiện đủ). Nếu bạn giữ tên "Pre" theo nghĩa lập trình thì "điều kiện cần" phải đổi tên thành "Nec". **Chọn một nghĩa và giữ nhất quán.** Trong tài liệu này tôi dùng: **Pre = cần, Suf = đủ**.
>
> Hệ quả cho việc tìm CHỖ: phần "brute-force" trong README (duyệt từng pixel/chữ cái) chỉ an toàn khi Suf được viết *chặt*; nếu chỉ có Pre thì sẽ nhận nhầm (false positive).

**Về "bước tiến có ý nghĩa"** trong định nghĩa bài toán tìm kiếm của bạn: tôi đề xuất định nghĩa được [ĐỀ XUẤT]. Gọi đồ thị hai phía G giữa *biến* và *phương trình*. Một phương trình mới là **có ý nghĩa** khi (a) **độc lập** với các phương trình đã thu (không suy ra từ chúng), (b) chứa ít nhất một biến **chưa được xác định**, và (c) làm tăng hạng (rank) hệ theo hướng nối tới biến trong Q. Với tính cần cù: *ưu tiên phương trình đưa vào ít ẩn mới (≤ 1)* trước.

## 1.3. PHÂN LOẠI CHỖ trong bài Nhiệt (10 loại) **[ĐỀ XUẤT]**

Đây là chỗ mà "vấn đề tìm kiếm" của bạn được cụ thể hoá cho Nhiệt. Mỗi công cụ **gắn với một hay hai loại CHỖ**; duyệt "mọi CHỖ cùng loại" là duyệt hữu hạn.

| Mã | Loại CHỖ | Định nghĩa | Ví dụ | Công cụ gắn vào |
|---|---|---|---|---|
| **χ1** | **Hệ / hệ con** | Một tập vật chất có biên xác định (cố định khối lượng hoặc thể tích kiểm soát) | "khí bên trái pittông", "nước + đá", "khí còn lại trong bình" | T02, T04, T06, T10, P1 |
| **χ2** | **Trạng thái** | Một bộ giá trị `(p, V, T, ν, …)` cân bằng của một hệ con tại một thời điểm | đỉnh 1, 2, 3 của chu trình; trạng thái đầu/cuối | T06, T03, T14, T12 |
| **χ3** | **Quá trình / đoạn quá trình** | Con đường nối hai trạng thái (kể cả đoạn nhỏ chia từ đoạn lớn) | đẳng nhiệt 1→2; đoạn thẳng 2→3; "khi pittông đi đoạn dx" | T08, T09, T10 |
| **χ4** | **Giao diện / biên** | Mặt phân cách hai vùng/hai vật | mặt lỏng–hơi, mặt hai vật liệu, mặt tường–khí, mặt pittông–khí, lỗ | T12, T13, T15, T11 |
| **χ5** | **Thời điểm / khoảng thời gian** | Một lúc xác định hoặc một `dt` | "ngay sau khi mở van", "sau thời gian dài", `dt` bất kỳ | T02, T13, T16, ODE |
| **χ6** | **Phần tử vi phân** | Lát `dz`, vỏ `dr`, đoạn ống `dx`, phần tử diện tích `dA` | lát khí quyển, vỏ trụ dẫn nhiệt, phần tử lỗ | T07, T13, T11, T16 |
| **χ7** | **Chu trình** | Đường đóng trong không gian trạng thái | chu trình động cơ, máy lạnh | T09, T10 |
| **χ8** | **Ranh giới pha / điểm tới hạn** | Điểm/đoạn tại đó pha đổi, hoặc điểm đổi dấu của một đại lượng | bắt đầu ngưng tụ; điểm `dQ = 0`; điểm `T_max` | T12, T14, T17, T08 |
| **χ9** | **Sự kiện vi mô** | Một va chạm, một đường đi tự do, một nhóm vận tốc `d³v` | va chạm với tường; phân tử qua lỗ | T05, T11, T16 |
| **χ10** | **Sổ cái bảo toàn** | Mỗi *(hệ con × khoảng thời gian)* mở ra một dòng sổ cái cho năng lượng, số hạt, xung lượng/lực, entropy | "năng lượng của khí trong bình trong `dt`" | T02, T10, mọi ODE |

Ghi chú **[ĐỀ XUẤT]**:
- Nhiều bài "bế tắc" chỉ vì **kho CHỖ không đủ mịn**. Ví dụ quên rằng một đoạn thẳng trên p–V thực ra là *hai* CHỖ (trước và sau điểm `dQ = 0`, loại χ8), hoặc quên coi *mỗi phần khí* là một hệ riêng (χ1).
- Kho CHỖ là **hữu hạn** khi ta chốt: số hệ con, số trạng thái được gọi tên, số đoạn (kể cả điểm gãy), số giao diện, các thời điểm đặc trưng (đầu, cuối, ngay sau…).

## 1.4. THUẬT TOÁN SCAN **[ĐỀ XUẤT]**

```
SCAN(B):
  Input: mô hình M (từ B0-B1), kho CHỖ 𝒦 = {χ1..χ10}
  Output: tập phương trình E, bảng sai số, danh sách CHỖ bị loại + lý do

  E ← ∅ ; Diag ← ∅
  for ℓ in L_nhiet (T01..T17, X1..X6):           # duyệt theo công cụ
      for c in 𝒦[type(ℓ)]:                        # duyệt mọi CHỖ cùng loại (hữu hạn)
          if not Pre(ℓ, c):      Diag.add(c, ℓ, "Pre fail: " + which)   ; continue
          if Suf(ℓ, c):          eq ← Post(ℓ, c) ; tag ← "exact"
          else:                  eq ← Post(ℓ, c) ; tag ← "approx, Err=" + Err(ℓ, c)
          if meaningful(eq, E, Q):   E.add(eq, tag)
  return E, Diag
```

**Hướng dẫn thực hành** (bản tay, hợp lệ trong phòng thi):

1. **Trước** khi duyệt: lập bảng χ1, χ2, χ3, χ4, χ7 (mấy hệ, mấy trạng thái, mấy đoạn, mấy giao diện, có chu trình không). Đó là xương sống.
2. Duyệt **theo công cụ**, không theo "cảm giác". Với mỗi công cụ, dùng cột *Loại CHỖ & cách quét* ở thẻ T-xx để biết duyệt gì.
3. Cho **mỗi CHỖ**, một dòng: `[χ, công cụ, Pre?, Suf?, phương trình, ẩn mới]`. Phiếu mẫu ở Phụ lục E.
4. Khi căng thẳng: **viết hết ra, rồi lọc** (đúng tinh thần brute-force của bạn). Lọc theo: trùng lặp → độc lập → liên quan Q.
5. Trực giác chỉ dùng để **xếp thứ tự** duyệt và **phát hiện CHỖ chưa liệt kê**, *không* dùng để bỏ qua công cụ.

## 1.5. Chẩn đoán bế tắc: sáu nguyên nhân (và cách chữa)

Khi công cụ áp vào một CHỖ mà "không ra gì" hoặc mâu thuẫn:

| # | Nguyên nhân | Dấu hiệu | Chữa |
|---|---|---|---|
| D1 | **Pre sai** (công cụ không hợp lệ ở đó) | Kết quả vô lý, hoặc phải dùng "xấp xỉ" ngoài Err | Đổi công cụ (ví dụ Poisson → bảo toàn năng lượng) |
| D2 | **Sai loại CHỖ** | Áp công thức của trạng thái lên quá trình | Kiểm tra `type(ℓ)` |
| D3 | **CHỖ quá thô** | Một phương trình chứa quá nhiều ẩn | Chia nhỏ: thêm điểm gãy, tách hệ con, tách `dt` |
| D4 | **Thiếu biến/hệ ẩn** | Ẩn nhiều hơn phương trình | Thêm hệ con (khí phía bên kia pittông, thành bình, nguồn nhiệt) |
| D5 | **Thiếu ràng buộc ẩn** | Hệ dưới-xác-định dù đã dùng hết công cụ | Duyệt bảng §1.6 |
| D6 | **Nhánh (case) chưa xét** | Đáp án phụ thuộc giả thiết ngầm | Giả thiết–kiểm tra–nhánh (ví dụ T04, T12) |

## 1.6. Ràng buộc ẩn — danh sách kiểm (tra từng dòng) **[ĐỀ XUẤT]**

Đây thường là nguồn "thiếu phương trình" số một:

1. **Cân bằng cơ học** của mọi vật di động (pittông, cột thuỷ ngân, giọt) → cân bằng lực → quan hệ giữa các `p`. Nếu pittông *không cân bằng*, phải viết định luật Newton.
2. **Cân bằng nhiệt** cuối cùng (thời gian dài) → cùng `T` ở các phần tiếp xúc nhiệt.
3. **Bảo toàn số hạt/khối lượng** *của từng phần* (nếu vách kín) hoặc của tổng (nếu nối thông).
4. **Hình học**: `V = A·x`, tổng thể tích không đổi, `V_1 + V_2 = V_tot`.
5. **Cân bằng pha**: có lỏng dư ⇒ `p_v = p_sat(T)`; đang sôi ⇒ `p_sat(T) = p_ngoài`.
6. **Liên tục tại giao diện**: `T` liên tục; thông lượng nhiệt liên tục (không nguồn tại mặt); `p` chênh theo Laplace nếu mặt cong.
7. **Điều kiện đầu/biên** cho ODE/PDE.
8. **Tính thuận nghịch** nói trong đề: "thuận nghịch" ⇒ `ΔS_tot = 0`; "tự phát" ⇒ `ΔS_tot > 0`.
9. **Dấu / chiều** của quá trình (nhận nhiệt hay toả nhiệt) ⇒ bất đẳng thức bổ sung.
10. **Năng lượng đi vào chỗ ẩn**: nhiệt dung của bình/pittông; ma sát → nội năng; công chống áp suất khí quyển.

## 1.7. Đếm ẩn — phương trình (kiểm tra đóng kín / well-posedness)

Quy tắc đếm **[CHUẨN về khái niệm, ĐỀ XUẤT về cách gói]**:

- Mỗi **phần khí lí tưởng** ở mỗi trạng thái: 3 biến `(p, V, T)` − 1 (phương trình trạng thái) = **2 bậc tự do**; nếu `ν` cũng chưa biết, tổng 3. (T06)
- Mỗi **quá trình** đã biết (đẳng nhiệt/đẳng áp/…) thêm **1 ràng buộc** giữa hai trạng thái đầu–cuối, nếu quasi-static; nếu bất thuận nghịch phải dùng bảo toàn năng lượng thay vì định luật đường.
- Mỗi **ràng buộc ẩn** ở §1.6 thêm 1 phương trình.
- Mỗi **bảo toàn** (năng lượng, số hạt) cho hệ con thêm 1 phương trình.
- **Đóng kín**: (số phương trình độc lập) ≥ (số ẩn cần để xác định Q). **Thừa** phương trình (mâu thuẫn) phải được giải thích (vì sao bài thừa dữ kiện? có khi có phương trình phụ thuộc).
- **Nghiệm**: kiểm tra tồn tại, duy nhất; nhiều nghiệm ⇒ biện luận (ví dụ nhánh bão hoà/không bão hoà; nghiệm của bậc hai).

---

# §2. TIỀN XỬ LÝ (Vấn đề 1 "tiện thể") — P1–P12

Đây là các **phép biến đổi bài toán về dạng áp dụng được công cụ** (vẫn thuộc Vấn đề 1). Mỗi phép có **Pre riêng**, tức là cũng là "công cụ".

## 2.1. Mười hai phép tiền xử lý

**P1. Chọn hệ và biên (cố định khối lượng).**
Bài toán khí *mất/nhận hạt* (rò rỉ, bơm, lỗ) thường trở thành bài toán khối lượng cố định nếu chọn hệ khôn khéo: chọn **"lượng khí sẽ ở lại trong bình"** hoặc **"lượng khí cuối cùng"** làm hệ; hoặc dùng bảo toàn tổng `Σ p_iV_i/T_i` (khi nối thông). *Pre:* xác định được "phần hạt nào thuộc hệ" trong suốt quá trình. *Cảnh báo:* khi hạt thoát ra, hệ "phần còn lại" **không** bảo toàn năng lượng (vì hạt mang năng lượng đi): xem X3 và ví dụ §6.B.

**P2. Phân loại thành (vách).**
Với mỗi vách/pittông: cách nhiệt (`Q = 0`) hay dẫn nhiệt (cùng `T`)? cứng hay di động? có ma sát? nhẹ (không khối lượng) hay có khối lượng? có lỗ (Kn)? Điều này quyết định ràng buộc ẩn (§1.6).

**P3. Bảng thang thời gian** (quyết định đẳng nhiệt/đoạn nhiệt/quasi-static/dừng). **[CHUẨN về khái niệm; ngưỡng mang tính kinh nghiệm]**
Liệt kê và so sánh:
- `τ_proc`: thời gian quá trình.
- `τ_mech ~ L/v_âm`: thời gian cân bằng áp suất trong khí.
- `τ_th ~ L²/D` hoặc `~ C/(G)`: thời gian cân bằng nhiệt với vật/nguồn.
Kết luận: `τ_mech ≪ τ_proc` ⇒ quasi-static cơ học (áp suất đều). `τ_proc ≫ τ_th` ⇒ đẳng nhiệt (gần nguồn). `τ_proc ≪ τ_th` ⇒ đoạn nhiệt (không kịp trao đổi nhiệt). Nếu `τ_mech` cũng *không* ≪ `τ_proc` ⇒ bất thuận nghịch/động lực học khí (Poisson không dùng được; dùng bảo toàn năng lượng; hoặc sóng âm).

**P4. Chuẩn hoá đơn vị & lượng.**
`°C → K`; `mol` vs `kg` vs `phân tử` (`ν = m/μ = N/N_A`); `lít, cm³ → m³`; `atm, mmHg, cột nước → Pa`; phần trăm thể tích ≡ phần mol (khí lí tưởng, cùng `p, T`).

**P5. Xác định `i` (số bậc tự do) và `C_V`.**
Đơn nguyên tử: `i = 3`. Lưỡng nguyên tử ở nhiệt độ thường: `i = 5` (7 khi dao động được kích hoạt, nhiệt độ cao). Đa nguyên tử phi tuyến: `i = 6`. **Pre:** phân bố đều năng lượng cổ điển. **Err:** "đóng băng" mức năng lượng (vd. H₂ ở nhiệt độ rất thấp). Nếu đề cho `C_V` hoặc `γ` thì dùng số của đề và **không** cần `i`.

**P6. Đổi đồ thị về một mặt phẳng chung (p–V) qua phương trình trạng thái.**
Bảng nhận dạng đường **[CHUẨN]** (với ν cố định):

| Trong mặt phẳng | Dạng đường | Quá trình |
|---|---|---|
| V–T | đường thẳng qua gốc | đẳng áp |
| p–T | đường thẳng qua gốc | đẳng tích |
| p–V | hyperbol `pV = const` | đẳng nhiệt |
| p–V | đường thẳng qua gốc `p = aV` | đa biến n = −1 (`C = C_V + R/2`) |
| p–V | đường thẳng `p = p₀ − bV` (không qua gốc) | quá trình có `T_max`, và có điểm `dQ = 0` (T08) |
| T–S | đường ngang | đẳng nhiệt; đường đứng: đoạn nhiệt thuận nghịch |
| ρ–T (cùng p) | `ρ ∝ 1/T` | đẳng áp |

**P7. Phân chia thuận nghịch/bất thuận nghịch (mỗi cạnh).**
Định luật đường (Poisson, `W = ∫p dV`, `Q = ∫T dS`) chỉ cho cạnh **quasi-static**. Cạnh bất thuận nghịch dùng: `ΔU = Q − W` với `W = ∫p_ngoài dV`; `ΔU = νC_VΔT` vẫn đúng cho khí lí tưởng dù bất thuận nghịch.

**P8. Không thứ nguyên hoá / biến rút gọn.**
Đặt `x = V/V₁`, `θ = T/T₁`, `π = p/p₁`: giảm số tham số; giúp thấy các tổ hợp không thứ nguyên và tự kiểm. Với vdW: biến rút gọn `p_r, v_r, T_r` (T14).

**P9. Lập BẢNG TRẠNG THÁI (State ledger) và chọn biến độc lập.**
Cột: hệ con | trạng thái | `p` | `V` | `T` | `ν` | ràng buộc dẫn tới. Chọn biến độc lập là *biến xuất hiện trong Q* hoặc *biến cho trước* (thường `V` hoặc `T`). Mọi đại lượng còn lại biểu diễn qua nó. (T06)

**P10. Hình học hoá.**
Nối `V` với toạ độ `x`: `V = V₀ + A·x`. Nối `p` với lực: pittông cân bằng ⇒ `p_khí A = p₀A + mg + kx` (nếu có lò xo). Nếu chất lỏng: `p = p₀ + ρgh`.

**P11. Giả thiết cân bằng cục bộ (LTE) và mô tả trường.**
Với hệ liên tục (khí quyển, thanh dẫn nhiệt): định nghĩa `T(x,t)`, `p(z)`, `ρ(z)` cục bộ. *Pre:* thang độ dài của biến thiên ≫ quãng đường tự do trung bình (Kn nhỏ); hệ gần cân bằng cục bộ.

**P12. Ngân sách sai số (Err budget).**
Tính sớm các số không thứ nguyên chi phối xấp xỉ và đánh dấu công cụ nào an toàn:
- `n·d³ ≪ 1` (khí đủ loãng; không khí thường: `n ≈ 2,7·10²⁵ m⁻³`, `d ≈ 3,7·10⁻¹⁰ m` ⇒ `n d³ ≈ 1,4·10⁻³`).
- `Kn = λ/L` (`λ ≈ 68 nm` cho không khí ở 1 atm, 0 °C): `Kn ≲ 0,01` liên tục; `≳ 10` phân tử tự do.
- `Bo = ρgr²/σ` (nhỏ ⇒ sức căng bề mặt chi phối). Độ dài mao dẫn `ℓ_c = √(σ/ρg)` (nước ≈ 2,7 mm).
- `Bi = hL_c/κ` (`≲ 0,1` ⇒ gộp, đồng đều nhiệt độ).
- `St = cΔT/L_ẩn` (`≪ 1` ⇒ Stefan quasi-steady).
- `Ma` (vận tốc pittông/vận tốc âm): `≪ 1` ⇒ quasi-static.

## 2.2. TỪ ĐIỂN I: lời đề bài → điều kiện mô hình **[ĐỀ XUẤT]**

| Lời trong đề | Điều kiện mô hình | Công cụ liên quan |
|---|---|---|
| "chậm", "từ từ", "rất chậm", "cân bằng ở mọi thời điểm" | Quasi-static: `p, T` đều trong khí, mỗi lúc | T06, T08 |
| "tiếp xúc với nguồn nhiệt/bể nước lớn" + "chậm" | Đẳng nhiệt, `T = T_nguồn` | T08 |
| "cách nhiệt", "bình cách nhiệt" | `Q = 0` (kiểm tra thêm nhanh/chậm để chọn Poisson hay bảo toàn năng lượng) | T02, T08 |
| "nhanh", "đột ngột", "thả tự do", "buông pittông" | Có thể bất thuận nghịch ⇒ **không** Poisson; dùng bảo toàn năng lượng | T02, P7 |
| "giãn tự do", "vào chân không" | `W = 0`; nếu cách nhiệt `Q = 0` ⇒ `ΔU = 0` (khí lí tưởng: `ΔT = 0`) | T02, T14 |
| "pittông nhẹ, không ma sát" | `p_khí = p_ngoài`; không tiêu tán | T06, P10 |
| "pittông có khối lượng m" | Cân bằng: `p = p₀ + mg/A`; nếu chuyển động, viết Newton | P10 |
| "bỏ qua nhiệt dung của bình/pittông" | Vật đó không tích trữ nhiệt | T02, T04 |
| "bình kín, cứng" | `V = const`, `W = 0` | T08 |
| "lỗ nhỏ" | So đường kính lỗ với `λ`: `Kn ≫ 1` ⇒ phun phân tử (effusion); `Kn ≪ 1` ⇒ chảy thuỷ động | T16 |
| "đang sôi" | `p_sat(T) = p_ngoài` (kể cả áp suất thuỷ tĩnh), `T` không đổi | T12, T17 |
| "bão hoà", "có nước ở đáy", "còn nước" | `p_v = p_sat(T)` | T12 |
| "độ ẩm tương đối f" | `p_v = f·p_sat(T)` | T12 |
| "nước vừa bay hơi hết" | Trạng thái tới hạn: `p_v = p_sat` **và** toàn bộ lượng chất ở pha hơi | T12 (χ8) |
| "chu trình", "trở về trạng thái ban đầu" | `ΔU = 0`, `ΔS_hệ = 0` | T09, T10 |
| "hiệu suất cực đại", "thuận nghịch" | `ΔS_tot = 0` | T10 |
| "có thể/không thể xảy ra?" | `ΔS_tot ≥ 0` kiểm tra | T10 |
| "ổn định/dừng", "sau thời gian dài" | `∂/∂t = 0`; cùng công suất qua các lớp nối tiếp | T13 |
| "mỏng" | Đồng đều theo bề dày (gộp) | T13, T15 |
| "cân bằng" (đơn độc) | **Mơ hồ**: phải quyết định cơ/nhiệt/pha/hoá; không tự đoán | §1.6 |
| "lò xo" | Lực–biến dạng; thế năng `kx²/2` | P10 |
| "ma sát" | Năng lượng biến thành nhiệt (vào khí? vào vách?): phải quyết định | T02 |
| "khí lí tưởng" | Áp dụng đầy đủ T05/T06 | T05, T06 |
| "gần đúng/ bỏ qua X" | `X` bị loại khỏi C; ghi vào Err | P12 |


---

# §3. THƯ VIỆN CÔNG CỤ (T01–T17, X1–X6)

**Mẫu thẻ** (mỗi công cụ = một "dạng" theo nghĩa của bạn ở PHẦN 0): *Vị trí syllabus → Post → Dom → Pre → Suf-detector → Err → Loại CHỖ & cách quét → Trình tự cố định → Đầu ra Toán (V2) → Bẫy → Ghép với*.

> "Trình tự cố định" là câu trả lời cho câu hỏi của bạn: *nếu KHÔNG dùng trực giác, chỉ tra theo trình tự thì trình tự đó là gì?* Ở mỗi thẻ tôi ghi luôn **phần trực giác còn sót** (dòng "Còn cần trực giác:").

---

## NHIỆT PHẦN 1 — a. VẬT LÍ NHIỆT

### T01. Cấu trúc của chất; sự chuyển thể

**Post [CHUẨN]:**
- Ba trạng thái khác nhau bởi cạnh tranh giữa động năng nhiệt `~kT` và năng lượng liên kết `ε`: rắn (dao động quanh vị trí cân bằng, trật tự xa), lỏng (gần nhau, không trật tự xa), khí (khoảng cách trung bình `n^{−1/3} ≫ d`).
- Chuyển thể ở áp suất xác định, chất tinh khiết, *hai pha cùng tồn tại*: `T` không đổi; nhiệt trao đổi = nhiệt ẩn.
- Nhiệt ẩn là **hiệu enthalpy** (nhiệt ở `p` không đổi), không phải `ΔU`: với hoá hơi, `ΔU_vap = L_m − RT` (mol, hơi lí tưởng, bỏ thể tích lỏng). Nước 100 °C: `40,7 − 3,10 ≈ 37,6 kJ/mol`.
- Ước lượng: `L_m ≈ N_A·ε_eff`. Quy tắc Trouton: `L_vap/T_b ≈ 88 J/(mol·K)` (đúng cho nhiều chất; nước ngoại lệ, `≈ 109`).
- Tỉ số mật độ lỏng/khí `~10³` ở điều kiện thường ⇒ coi `V_lỏng ≪ V_hơi`.

**Dom:** chất tinh khiết, cân bằng pha; `p` xác định.
**Pre:** hai pha có mặt cùng lúc (nếu muốn "T không đổi"); không phản ứng, không hoà tan đáng kể.
**Suf-detector:** đề nói "đang sôi", "đang tan", "hỗn hợp nước–đá", "bão hoà".
**Err:** dung dịch/hợp kim (nhiệt độ chuyển thể trượt); quá lạnh/quá nhiệt (siêu bền); vật liệu vô định hình (thuỷ tinh: không có nhiệt độ nóng chảy sắc nét).
**Loại CHỖ:** χ2 (trạng thái), χ4 (ranh giới pha), χ8.
**Trình tự cố định:**
1. Với mỗi chất ở mỗi trạng thái đầu/cuối: so `(T, p)` với `T_m(p)`, `T_b(p)` (hoặc `p_sat(T)`) để xác định pha.
2. Nếu hai pha cùng tồn tại ⇒ ràng buộc `T = T_pha(p)` (hoặc `p = p_sat(T)`); ghi vào bảng ràng buộc.
3. Ghi thể tích/mật độ từng pha nếu có công chuyển pha `p(V_g − V_l)`.
**Đầu ra Toán:** đẳng thức/bất đẳng thức về nhiệt độ (`T ≷ T_m`) ⇒ **phân nhánh (case split)**.
**Bẫy:** quên hoá hơi đòi công `≈ νRT`; dùng `L` như `ΔU`.
**Còn cần trực giác:** đoán pha cuối khi chưa tính (giải bằng thuật toán T04/T12 để khỏi đoán).

---

### T02. Nội năng + Nguyên lí 1 (dạng tổng quát)

**Post [CHUẨN]:** với hệ kín `dU = δQ − δW` (W: công hệ sinh ra, gồm *mọi* dạng: cơ `p dV`, bề mặt `σ dA`, điện, …). `U` là hàm trạng thái; `Q, W` phụ thuộc đường. Ở `p` không đổi (chỉ công `p dV`): `Q = ΔH`, `H = U + pV`. Khí lí tưởng: `U = ν(i/2)RT`, **chỉ phụ thuộc T** (`ΔU = νC_VΔT` cho *mọi* quá trình, kể cả bất thuận nghịch).
**Dom:** hệ kín; với hệ hở dùng dạng dòng dừng (X3).
**Pre:** hệ và biên đã xác định; **mọi** kênh trao đổi năng lượng đã liệt kê; mọi dạng năng lượng tích trữ trong hệ đã liệt kê (`U`, động năng vĩ mô, thế năng, năng lượng bề mặt, lò xo).
**Suf-detector:** hệ được chọn *kín* (P1) và bảng kênh năng lượng đã đầy.
**Err:** không có sai số vật lí (định luật chính xác); sai số là **sai số mô hình** do sót kênh (ma sát, nhiệt dung bình, công chống khí quyển).
**Loại CHỖ:** χ1 (hệ) × χ5 (khoảng thời gian) = **mỗi dòng sổ cái năng lượng (χ10)**.
**Trình tự cố định (sổ cái năng lượng):**
1. Chọn hệ (P1); chọn khoảng thời gian (đầu → cuối).
2. Liệt kê *đầu vào/đầu ra* qua biên: `Q` (từng nguồn), `W` (từng dạng: pittông, lò xo, khí quyển, điện).
3. Liệt kê *thay đổi năng lượng tích trữ*: `ΔU`, `ΔKE`, `ΔPE`, `ΔE_bề mặt`, …
4. Viết `Σ(thay đổi tích trữ) = Q − W_tổng`.
5. Công của quá trình **bất thuận nghịch** là `W = ∫p_ngoài dV`, **không** phải `∫p_khí dV`.
**Đầu ra Toán:** phương trình đại số tuyến tính (thường) giữa `ΔT`, `Q`, `W`.
**Bẫy:** đổi dấu công; quên công chống áp suất khí quyển `p₀ΔV`; quên năng lượng hạt thoát mang đi (§6.B).
**Ghép với:** T06, T08, T10 (thường xuyên).
**Còn cần trực giác:** chọn hệ (P1) và quyết định kênh năng lượng nào "đáng kể".

---

### T03. Nhiệt độ; thang đo nhiệt độ

**Post [CHUẨN]:** `T(K) = t(°C) + 273,15`; `t_F = (9/5)t_C + 32`; `T_R = (9/5)T_K`. Nhiệt kế đo đại lượng nhiệt kế `X` (độ dài cột, điện trở, áp suất…): **nếu quan hệ tuyến tính** `t = t₀ + (t₁ − t₀)(X − X₀)/(X₁ − X₀)` qua hai điểm cố định. Nhiệt kế khí thể tích không đổi: `T = T_tp·p/p_tp` (giới hạn `p_tp → 0`); điểm ba của nước ≈ 273,16 K.
**Dom:** cân bằng nhiệt giữa nhiệt kế và vật (nguyên lí 0).
**Pre:** (i) nhiệt kế đã đạt cân bằng nhiệt; (ii) nhiệt dung của nhiệt kế ≪ nhiệt dung vật (nếu không, phải tính nhiệt lượng kế/nhiệt kế vào cân bằng); (iii) quan hệ `X–t` tuyến tính (nếu dùng hai điểm chuẩn).
**Err:** hai loại nhiệt kế *khác nguyên lí* không trùng nhau ngoài các điểm chuẩn.
**Loại CHỖ:** χ2.
**Trình tự cố định:** (1) lập ánh xạ affine `f(X) = αX + β` từ hai điểm chuẩn (hai phương trình); (2) hợp các ánh xạ nếu qua nhiều thang; (3) kiểm điểm thứ ba nếu có.
**Đầu ra Toán:** hệ tuyến tính 2 ẩn; hoặc hàm affine.
**Bẫy:** đổi *hiệu* nhiệt độ: `ΔT_K = ΔT_C` nhưng `ΔT_F = 1,8·ΔT_C`. Nhiệt kế sai (điểm 0 và 100 bị lệch) ⇒ hai ẩn `α, β` chứ không phải chỉ cộng bù.
**Ghép với:** T04 (nhiệt kế thả vào nước: có nhiệt dung), X1 (giãn nở nhiệt).

---

### T04. Nhiệt dung riêng, nhiệt nóng chảy, nhiệt hoá hơi (nhiệt lượng kế)

**Post [CHUẨN]:** `Q = mcΔT` (c hằng); nóng chảy `Q = mλ`; hoá hơi `Q = mL`. Ở `p` không đổi với pha ngưng tụ: `ΔU ≈ ΔH`. Cân bằng nhiệt hệ cô lập: `Σ ΔH_i = 0`. Nếu `c = c(T)`: `Q = m∫c dT`. Công suất: `P·t = ΔH`.
**Dom:** pha ngưng tụ, `p` gần hằng, đã đạt cân bằng nhiệt cuối.
**Pre:** (a) hệ cô lập nhiệt (hoặc tổn thất được tính); (b) cùng chốt mốc enthalpy; (c) `c` không đổi trong khoảng `ΔT` (hoặc dùng tích phân); (d) không phản ứng hoá học/hoà tan; (e) thời gian đủ dài để cân bằng.
**Suf-detector:** vật trong bình cách nhiệt, tiếp xúc tốt, "đợi cân bằng".
**Err:** `c(T)` (đặc biệt ở T thấp); nhiệt dung bình (dùng "đương lượng nước" `m_kc_k`); mất nhiệt ra ngoài.
**Loại CHỖ:** χ1 (mỗi vật), χ2 (đầu/cuối), χ8 (ngưỡng đổi pha), χ10 (sổ cái enthalpy).
**Trình tự cố định (thuật toán "H-bracket") [ĐỀ XUẤT]:**
1. Với mỗi vật `i`, dựng hàm `h_i(T)` **từng khúc tuyến tính** có nhảy `mλ` tại `T_m` và `mL` tại `T_b` (mốc chung).
2. Tổng enthalpy đầu: `H₀ = Σ h_i(T_i)` (cộng cả nhiệt/công cấp thêm nếu có).
3. Xét `F(T) = Σ h_i(T)`: **không giảm** theo T, có "đoạn dựng đứng" ở các nhiệt độ chuyển pha. Sắp các nhiệt độ đặc trưng (`T_m, T_b` của mọi chất có mặt); **tính `F` tại từng ngưỡng** (cả hai phía đoạn dựng đứng).
4. Xác định khoảng chứa `H₀`: nếu `H₀` rơi trong một đoạn dựng đứng ⇒ `T_f = T_pha`, và tính tỉ lệ pha; nếu rơi trong một khúc dốc ⇒ giải phương trình **bậc nhất** `F(T_f) = H₀` trong khúc đó.
5. Kiểm tra `T_f` nằm đúng khúc đã giả định.
**Đầu ra Toán:** hàm từng khúc đơn điệu; tìm nghiệm bằng chia khoảng; một phương trình bậc nhất.
**Bẫy:** giả sử "đá tan hết" mà chưa kiểm; sai mốc; bỏ đương lượng nước của bình; trộn nhiều lần liên tiếp ⇒ truy hồi tuyến tính (cấp số nhân).
**Ghép với:** T12 (hơi nước), T13 (cấp nhiệt bằng dẫn nhiệt), T02.
**Còn cần trực giác:** gần như không (đây là thuật toán thuần).

---

## NHIỆT PHẦN 1 — b. KHÍ LÍ TƯỞNG

### T05. Thuyết động học phân tử chất khí (cơ bản)

**Post [CHUẨN]:** `k = R/N_A`; `ν = N/N_A = m/μ`; `n = N/V`; `p = nkT`; `⟨ε_tr⟩ = (3/2)kT`. Tốc độ: `v_rms = √(3kT/m)`, `v̄ = √(8kT/πm)`, `v_p = √(2kT/m)` (tỉ lệ `1 : 1,128 : 1,225` cho `v_p : v̄ : v_rms`). Phân bố đều năng lượng: `⟨ε⟩ = (i/2)kT`; `U = ν(i/2)RT`; `C_V = iR/2`; `γ = 1 + 2/i`. Phân bố Maxwell: `f(v)dv = 4π(m/2πkT)^{3/2}v²e^{−mv²/2kT}dv`.
**Dom:** khí loãng, cân bằng.
**Pre:** `n d³ ≪ 1`; tương tác chỉ qua va chạm ngắn; cân bằng nhiệt (phân bố Maxwell); cổ điển: `λ_dB ≪ n^{−1/3}`; phân bố đều đúng cho bậc tự do đang hoạt động.
**Suf-detector:** khí nhiệt độ phòng, `p` ≲ vài atm, xa điểm hoá lỏng.
**Err:** `i` phụ thuộc T (đóng băng/kích hoạt bậc tự do); khí nén cao ⇒ T14.
**Loại CHỖ:** χ9 (sự kiện vi mô), χ2.
**Trình tự cố định:** (1) gọi tên *đại lượng thống kê* cần (`⟨v²⟩`, `⟨v⟩`, `⟨ε⟩`); (2) tra bảng trên (P5 để lấy `i`); (3) nếu cần trung bình khác: tích phân trên `f(v)` (Phụ lục A); (4) kiểm đơn vị.
**Đầu ra Toán:** tích phân Gauss/Gamma; đại số.
**Bẫy:** nhầm `v̄`, `v_rms`, `v_p`; nhầm `m` (khối lượng phân tử) với `μ` (mol); dùng `i = 5` khi đề cho `γ` khác.

---

### T06. Các định luật khí lí tưởng; phương trình Clapeyron–Mendeleev

**Post [CHUẨN]:** `pV = νRT = NkT`. Lượng cố định: `p₁V₁/T₁ = p₂V₂/T₂` (đẳng nhiệt/áp/tích là các trường hợp riêng). Hỗn hợp: `p = Σp_i`, `p_iV = ν_iRT` (Dalton). Khối lượng riêng: `ρ = pμ/(RT)`.
**Dom:** khí lí tưởng ở trạng thái cân bằng.
**Pre:** (1) *lượng khí của phần đang xét không đổi* (hoặc đếm rõ từng phần); (2) `p, T` đồng nhất trong phần khí (*trạng thái*, không phải giữa một quá trình nhanh); (3) khí đủ loãng, T đủ cao so với `T_c`.
**Suf-detector:** khí nhiệt độ phòng, `p` cỡ atm, "cân bằng", đủ thời gian.
**Err:** khí thực (T14): sai số cỡ `a n/(pV²)` và `b/V_m`.
**Loại CHỖ:** **χ2 (trạng thái) × χ1 (mỗi phần khí)**: mỗi (phần khí, trạng thái) một phương trình.
**Trình tự cố định (bảng trạng thái, P9):**
1. Mỗi phần khí = một hàng; mỗi trạng thái = một cột.
2. Điền các giá trị biết; viết `pV = νRT` cho **mỗi ô**.
3. Liên kết các ô bằng **ràng buộc ẩn (§1.6)**: cân bằng pittông ⇒ `p`; tiếp xúc nhiệt ⇒ `T`; nối thông ⇒ `p` (và `T` nếu tiếp xúc); bảo toàn `ν` từng phần; `V_1 + V_2 = V_tot`.
4. Nếu khí rò/bơm: dùng P1 (chọn hệ khối lượng cố định) hoặc bảo toàn `Σν`.
**Đầu ra Toán:** hệ phương trình đại số (thường hữu tỉ, bậc thấp, dạng song tuyến tính).
**Bẫy:** T tính bằng °C; quên áp suất khí quyển khi tính `p` từ cân bằng pittông; quên nhiệt độ hai phần khác nhau; `ν` bị đổi khi hở van.
**Ghép với:** T08 (quá trình), T07 (thuỷ tĩnh), T12 (hơi ẩm), P10.
**Còn cần trực giác:** quyết định cái nào là quasi-static/cân bằng (dùng P3).

---

### T07. Bài toán xét vi phân dải khí (lớp khí vi phân) **[CẦN KIỂM về cách hiểu tên]**

**Post [CHUẨN]:**
- Cân bằng thuỷ tĩnh cục bộ: `dp/dz = −ρg`; với `ρ = pμ/(RT)`: `dp/p = −(μg/RT(z)) dz`.
- **Đẳng nhiệt** `T = T₀`: `p = p₀ exp(−μgz/RT₀)`; độ cao chuẩn `H = RT/(μg) = kT/(mg)`.
- **Đoạn nhiệt (khí quyển được trộn đối lưu)**: `dT/dz = −((γ−1)/γ)(μg/R) = −g/c_p` (không khí khô ≈ −9,8 K/km); `p ∝ T^{γ/(γ−1)}`.
- **Đa biến `n`**: `dT/dz = −((n−1)/n)(μg/R)`.
- Cột khí quay quanh trục với `ω`: `dp/dr = ρω²r` ⇒ `p ∝ exp(μω²r²/2RT)` (đẳng nhiệt).
- Hệ quy chiếu có gia tốc `a`: thay `g → g_hiệu dụng`.
**Dom:** khí lí tưởng đứng yên (hoặc chuyển động đều) trong trường.
**Pre:** (a) cân bằng cơ học cục bộ; (b) lớp đủ mỏng để `ρ, g` coi như hằng trong lớp; (c) cân bằng nhiệt cục bộ (`T` xác định); (d) khí lí tưởng cục bộ.
**Suf-detector:** đẳng nhiệt: nhiệt độ đều/dẫn nhiệt tốt; đoạn nhiệt: khí bị trộn nhanh, ít trao đổi nhiệt; có chỉ số `n` cho trước.
**Err:** khí quyển đoạn nhiệt khô có "chiều cao hữu hạn" (`T → 0` tại `z = T₀/Γ ≈ 29 km` với `Γ = 9,8 K/km`, `T₀ = 288 K`): đây là **hiện tượng ngoài Pre** (khí lí tưởng, γ hằng, không ngưng tụ) chứ không phải vật lí thật (§6.I).
**Loại CHỖ:** **χ6 (phần tử vi phân)**.
**Trình tự cố định ("lát cắt"):**
1. Chọn trục dọc theo gradient (`z` hoặc `r`); vẽ lát `dz`, diện tích `A`.
2. Cân bằng lực trên lát: `[p(z) − p(z+dz)]A − ρgA dz = 0` (+ thành phần quán tính nếu quay/gia tốc).
3. Thêm **quan hệ thứ hai**: phương trình trạng thái `ρ = pμ/RT` **và** luật nhiệt độ (đẳng nhiệt / đoạn nhiệt / `T(z)` cho trước / từ T13).
4. Khử `ρ` (và `T` nếu cần): được **ODE bậc 1** cho `p(z)` (hoặc hệ `p, T`).
5. Điều kiện biên: `p(0) = p₀`, `T(0) = T₀`.
**Đầu ra Toán:** ODE bậc 1 tách biến / tuyến tính; nếu `T` tuyến tính theo `z` ⇒ luật luỹ thừa.
**Bẫy:** dùng `ρ` không đổi cho khí; nhầm `m` và `μ`; quên T tuyệt đối; khí quyển đoạn nhiệt ≠ đẳng nhiệt (đề yêu cầu nói rõ).
**Ghép với:** T17 (nhiệt độ sôi theo độ cao), T13 (`T(z)` do dẫn nhiệt), T16 (Boltzmann).

---

### T08. Cơ sở NĐLH, Nguyên lí 1 cho khí; bài tập nâng cao về Nguyên lí 1

**Post [CHUẨN]:** khí lí tưởng, quasi-static: `δQ = νC_V dT + p dV`; `C_p = C_V + R` (Mayer). Bốn quá trình chuẩn:

| Quá trình | Điều kiện | `ΔU` | `W` (khí sinh) | `Q` |
|---|---|---|---|---|
| Đẳng tích | `V` hằng | `νC_VΔT` | 0 | `νC_VΔT` |
| Đẳng áp | `p` hằng | `νC_VΔT` | `pΔV = νRΔT` | `νC_pΔT` |
| Đẳng nhiệt | `T` hằng | 0 | `νRT ln(V₂/V₁)` | `= W` |
| Đoạn nhiệt (quasi-static) | `Q = 0` | `−W` | `(p₁V₁ − p₂V₂)/(γ−1)` | 0 |

Poisson: `pV^γ = const`, `TV^{γ−1} = const`, `T^γ p^{1−γ} = const`.
Đa biến `pV^n = const` ⇒ **`C = C_V + R/(1−n)`** (đã kiểm), `W = (p₁V₁ − p₂V₂)/(n−1)` (`n ≠ 1`), `Q = νCΔT`.
Nhiệt dung của quá trình bất kỳ: `C = δQ/(ν dT)`.
Bất thuận nghịch: giãn tự do (vào chân không, cách nhiệt) `ΔT = 0`; buông pittông chống áp `p_ext` không đổi: `νC_V(T₂ − T₁) = −p_ext(V₂ − V₁)` (dùng bảo toàn năng lượng, **không** dùng Poisson).
Dao động nhỏ của pittông (khối lượng `m`, diện tích `A`, khí `V` thể tích, đoạn nhiệt): `ω² = γpA²/(mV)`; vận tốc âm `c_s = √(γRT/μ) = √(γp/ρ)` (đã kiểm).
Điều kiện đổi dấu nhiệt: cho `p = p(V)` bất kỳ: **`dQ/dV = (γp + V·p′)/(γ−1)`**, vậy `dQ = 0` ⇔ **`γp + V·p′ = 0`** (đường tiếp xúc với đoạn nhiệt) (đã kiểm). Cực trị `T`: `dT/dV = 0` ⇔ `p + V·p′ = 0`.
**Dom:** khí lí tưởng.
**Pre:** *Poisson/`W = ∫p dV`/`Q = ∫TdS`* cần **quasi-static**; Poisson thêm `Q = 0`; `C_V` hằng.
**Suf-detector (Poisson):** cách nhiệt hoàn toàn (hoặc nhanh hơn thời gian trao đổi nhiệt) **và** đủ chậm để áp suất cân bằng (`τ_proc ≫ τ_mech`, P3), không ma sát/khuấy; hoặc đề nói "thuận nghịch".
**Err:** `C_V(T)` (dao động phân tử); khí thực.
**Loại CHỖ:** χ3 (đoạn quá trình), χ2 (đỉnh), **χ8 (điểm `dQ = 0`, điểm `T_max`)**.
**Trình tự cố định (đồ thị trạng thái) [ĐỀ XUẤT]:**
1. Đỉnh: bảng trạng thái (T06).
2. Cạnh: gán luật cho từng cạnh (đẳng-V/p/T, đoạn nhiệt, đa biến, đường tổng quát `p(V)`, bất thuận nghịch).
3. Mỗi cạnh: `ΔU = νC_VΔT` (luôn đúng); `W = ∫p dV` (quasi-static) hoặc `∫p_ngoài dV`; `Q = ΔU + W`.
4. Cạnh tổng quát: giải `γp + V·p′ = 0` để tìm điểm đổi dấu `Q`; chia cạnh tại đó.
5. Tự kiểm: tổng `ΔU` quanh chu trình = 0.
**Đầu ra Toán:** tích phân xác định; nghiệm của đạo hàm (điểm đổi dấu); đại số.
**Bẫy:** `Q = νC_VΔT` chỉ đúng đẳng tích; `W = diện tích` chỉ quasi-static; tưởng đoạn thẳng luôn hấp thụ nhiệt; đoạn nhiệt dốc hơn đẳng nhiệt (γ > 1).
**Ghép với:** T09, T10, T06.
**Còn cần trực giác:** không nhiều nếu làm theo bảng.

---

### T09. Tính công, nhiệt dung, hiệu suất chu trình

**Post [CHUẨN]:** `W_chu trình = ∮p dV` = diện tích (**thuận chiều kim đồng hồ trên p–V (V ngang, p đứng) ⇒ động cơ, W > 0**); `ΔU_chu trình = 0` ⇒ `W = Q_vào − Q_ra`; `η = W/Q_vào`. Máy lạnh: `K = Q_lạnh/W`; bơm nhiệt: `K_hp = Q_nóng/W`. Trên T–S: `Q = ∮T dS`. Công thức tham khảo: Otto `η = 1 − r^{1−γ}` (`r = V_max/V_min`); Diesel `η = 1 − r^{1−γ}(ρ_c^γ − 1)/(γ(ρ_c − 1))`; Brayton `η = 1 − (p_thấp/p_cao)^{(γ−1)/γ}` (Otto/Diesel đã kiểm số).
**Dom:** chu trình khép kín của một chất công tác, chế độ tuần hoàn.
**Pre:** mỗi cạnh có luật rõ; cạnh dùng "diện tích = công" phải quasi-static.
**Suf-detector:** đề cho chu trình gồm các quá trình chuẩn hoặc đồ thị.
**Err:** cạnh bất thuận nghịch ⇒ diện tích ≠ công.
**Loại CHỖ:** **χ7 (chu trình)**, χ3, χ8.
**Trình tự cố định:**
1. Lập bảng đỉnh (T06); xác định chiều chu trình (động cơ/lạnh).
2. Từng cạnh (T08): `ΔU, W, Q`. **Chia cạnh tại điểm `dQ = 0`** (χ8) nếu cạnh không đơn điệu về nhiệt.
3. `Q_vào = Σ(các phần `Q > 0`)`, `Q_ra = Σ|các phần `Q < 0`|`.
4. Kiểm: `ΣW = ΣQ`.
5. `η = W/Q_vào`; **kiểm Carnot:** `η ≤ 1 − T_min/T_max` (nếu vi phạm ⇒ sai).
6. Nếu tối ưu hoá (max `η` hoặc max `W` theo tham số): giải đạo hàm bằng 0.
**Đầu ra Toán:** tích phân từng khúc; đại số; cực trị một biến (hoặc nhân tử Lagrange).
**Bẫy:** tính `Q_vào` bằng tổng *tất cả* các cạnh "trông như nhận nhiệt" mà bỏ sót đoạn đổi dấu; tính `η` bằng `W/Q_net`; nhầm chiều.

---

### T10. Nguyên lí 2: máy lạnh, động cơ nhiệt, hiệu suất cực đại, entropy

**Post [CHUẨN]:**
- Clausius: không có quá trình nào *chỉ* truyền nhiệt từ lạnh sang nóng. Kelvin–Planck: không có chu trình chuyển *toàn bộ* nhiệt từ một nguồn thành công.
- Entropy: `dS ≥ δQ/T_nguồn` (dấu `=` thuận nghịch); hệ cô lập `ΔS ≥ 0`; `S` là hàm trạng thái.
- Carnot: `η ≤ 1 − T_c/T_h`; `K_lạnh ≤ T_c/(T_h − T_c)`; `K_hp ≤ T_h/(T_h − T_c)`.
- Khí lí tưởng: `ΔS = νC_V ln(T₂/T₁) + νR ln(V₂/V₁) = νC_p ln(T₂/T₁) − νR ln(p₂/p₁)`.
- Vật `C` hằng: `ΔS = C ln(T₂/T₁)`; nguồn: `ΔS = Q/T`; chuyển pha: `ΔS = mL/T`.
- **Hai vật hữu hạn, động cơ thuận nghịch** (đã kiểm): `T_f = T₁^{C₁/(C₁+C₂)}·T₂^{C₂/(C₁+C₂)}`, `W_max = C₁T₁ + C₂T₂ − (C₁+C₂)T_f`; nếu `C₁ = C₂ = C`: `T_f = √(T₁T₂)`, `W_max = C(√T₁ − √T₂)²`.
- Công mất: `W_lost = T₀·ΔS_tot` (Gouy–Stodola).
- Động cơ nội thuận nghịch ở công suất cực đại (Curzon–Ahlborn): `η = 1 − √(T_c/T_h)` **[CẦN KIỂM: ngoài bảng syllabus, có thể xuất hiện ở IPhO; dùng khi đề nêu mô hình]**.
**Dom:** mọi hệ; cần tính `ΔS` của **mọi** thành phần tham gia.
**Pre:** liệt kê *đầy đủ* thành phần của "vũ trụ" (hệ + mọi nguồn + vật tham gia); `ΔS` tính bằng **đường thuận nghịch giả tưởng** giữa hai trạng thái cân bằng.
**Suf-detector:** "máy hoạt động giữa các nguồn", "hai vật tiếp xúc", "tự phát", "tối đa/tối thiểu", "có thể/không thể", "thuận nghịch".
**Err:** entropy của trạng thái không cân bằng không xác định trực tiếp; luôn đi qua trạng thái cân bằng đầu/cuối.
**Loại CHỖ:** χ7, χ1×χ5, **χ10 (sổ cái entropy — bất đẳng thức)**.
**Trình tự cố định (sổ cái hai cột: năng lượng | entropy) [ĐỀ XUẤT]:**
1. Liệt kê mọi vật (hệ chất công tác + nguồn/vật) và trạng thái đầu/cuối.
2. Cột năng lượng (T02): `W = Q_h − Q_c` (động cơ), hoặc cân bằng nhiệt hữu hạn.
3. Cột entropy: mỗi vật `ΔS_j` (đường thuận nghịch); `ΔS_tot = Σ_jΔS_j`.
4. Áp: "thuận nghịch/cực đại" ⇒ `ΔS_tot = 0`; "tự phát/có thể" ⇒ `ΔS_tot ≥ 0`.
5. Giải hệ (năng lượng + entropy) cho ẩn cần tìm.
**Đầu ra Toán:** phương trình logarit (đưa về đại số bằng lấy mũ); bất đẳng thức; cực trị.
**Bẫy:** quên nguồn khi tính `ΔS_tot`; dùng `ΔS = Q/T` cho quá trình bất thuận nghịch của chính vật (phải dùng đường thuận nghịch); nhầm `T` khi nguồn hữu hạn thay đổi nhiệt độ.
**Ghép với:** T02, T09, T04 (nguồn hữu hạn).

---

### T11. Áp suất chất khí; động năng phân tử; phương trình cơ bản của khí lí tưởng

**Post [CHUẨN]:** `p = (1/3)n m⟨v²⟩ = (2/3)n⟨ε_tr⟩ = nkT`. Tổng quát: áp suất pháp tuyến lên tường = `n m⟨v_n²⟩` (v_n: thành phần pháp tuyến).
- Chùm hạt tới tường (vận tốc `v`, góc `θ` so với pháp tuyến, mật độ `n`): phản xạ gương `p = 2 n m v² cos²θ`; bị hấp thụ hoàn toàn (xung lượng pháp tuyến) `p = n m v² cos²θ`.
- Tường di động chậm với tốc độ `u`: hạt phản xạ đổi tốc độ pháp tuyến `v → v + 2u` (tường lại gần) ⇒ khí nóng lên khi bị nén ⇒ suy được đoạn nhiệt cổ điển (bất biến đoạn nhiệt).
- Hỗn hợp: `p = Σn_ikT`.
**Dom:** khí loãng, cổ điển, va chạm ngắn.
**Pre:** phân bố vận tốc xác định (cân bằng hoặc chùm cho trước); tường đủ rộng so với kích thước phân tử, đủ số va chạm trong `Δt` để bỏ qua thăng giáng; không lực tầm xa đáng kể.
**Suf-detector:** đề nhắc "va chạm phân tử với tường", "chùm phân tử", "áp suất từ động năng".
**Loại CHỖ:** **χ4 (phần tử tường `dA`) × χ5 (`dt`)**, χ9.
**Trình tự cố định ("hình trụ va chạm"):**
1. Chọn phần tử tường `dA` và thời gian `dt`.
2. Phân tử nhóm vận tốc `v` (thành phần pháp `v_n`) chạm `dA` trong `dt` nằm trong hình trụ xiên thể tích `v_n dt dA`.
3. Số va chạm `= n_nhóm·v_n dt dA`.
4. Xung lượng pháp tuyến mỗi va chạm: `2m v_n` (gương) hoặc `m v_n` (hấp thụ, rồi tái phát: xét riêng).
5. `p = Σ xung / (dt·dA)`; tích phân/trung bình trên nhóm.
**Đầu ra Toán:** tổng/tích phân trên phân bố; phép lấy trung bình trên bán cầu `∫cosθ dΩ = π`, `∫cos²θ dΩ = 2π/3` (đã kiểm).
**Bẫy:** quên chỉ *một nửa* phân tử hướng về tường (hệ số ½ khử với `2mv_x`); nhầm khối lượng phân tử/khối lượng mol.
**Ghép với:** T05, T16 (dòng phân tử), T08 (đoạn nhiệt vi mô).

---

## NHIỆT PHẦN 2

### T12. Sự chuyển pha; không khí ẩm

**Post [CHUẨN]:**
- Áp suất hơi bão hoà `p_sat(T)` chỉ phụ thuộc `T`, tăng rất nhanh theo `T`. Nước (kPa, giá trị cỡ): 0 °C ≈ 0,61; 20 °C ≈ 2,34; 40 °C ≈ 7,4; 60 °C ≈ 19,9; 100 °C ≈ 101,3 [CẦN KIỂM nếu đề cho bảng riêng: dùng bảng của đề].
- **Sôi ⇔ `p_sat(T) = p_ngoài`** (áp suất *tổng* tại mặt bong bóng, gồm cả `ρgh` ở đáy).
- Độ ẩm tương đối `f = p_v/p_sat(T) = ρ_v/ρ_sat(T)`; độ ẩm tuyệt đối `ρ_v = p_vμ_w/(RT)` (`μ_w = 0,018 kg/mol`); điểm sương `T_d`: `p_sat(T_d) = p_v`.
- Dalton: `p = p_khô + p_v`. Không khí ẩm nhẹ hơn khô (18 < 29).
- Có lỏng dư trong bình kín ⇒ `p_v = p_sat(T)`; hơi *không thể vượt* `p_sat` ở trạng thái cân bằng.
**Dom:** chất tinh khiết lỏng–hơi, hơi ≈ lí tưởng.
**Pre:** hơi lí tưởng (`p_v` thấp); mặt lỏng phẳng; thể tích lỏng ≪ thể tích hơi; khí không hoà tan đáng kể; đủ thời gian cân bằng.
**Suf-detector (`p_v = p_sat`):** có pha lỏng đáng kể + tiếp xúc tốt + thời gian dài + `T` xác định.
**Err:** giọt cực nhỏ (Kelvin, T15); hơi không lí tưởng ở áp suất cao; siêu bão hoà.
**Loại CHỖ:** χ2, χ4 (mặt lỏng–hơi), **χ8 (điểm bắt đầu/kết thúc ngưng tụ hoặc bay hơi)**.
**Trình tự cố định ("giả thiết – kiểm tra – nhánh") [ĐỀ XUẤT]:**
1. Giả sử **không có lỏng**: toàn bộ chất bay hơi nằm ở pha hơi ⇒ `p_v^giả = ν_tổng·RT/V`.
2. So `p_v^giả` với `p_sat(T)`. Nếu `≤` ⇒ **nhánh khô** (không lỏng). Nếu `>` ⇒ **nhánh bão hoà**: `p_v = p_sat(T)`, `ν_v = p_sat V/(RT)`, `ν_lỏng = ν_tổng − ν_v ≥ 0`.
3. Nếu bài thay đổi `V` hoặc `T`: tìm giá trị **tới hạn** (`V_c` hay `T_c`) tại đó `p_v^giả = p_sat`; chia nhánh tại đó; tính từng nhánh.
4. Nếu đề nói "vẫn còn nước": đặt luôn nhánh bão hoà và **kiểm** `ν_lỏng ≥ 0` sau khi giải.
5. Sôi: so `p_sat(T)` với `p_ngoài + ρgh` để xác định sôi được không.
**Đầu ra Toán:** **hàm từng khúc** với điểm gãy; kiểm tra bất đẳng thức; tỉ lệ/phương trình bậc nhất; nếu `p_sat(T)` cho dạng hàm mũ ⇒ phương trình siêu việt (V3).
**Bẫy:** cho rằng hơi bão hoà nén đẳng nhiệt vẫn tuân Boyle (thực tế `p` không đổi, khối lượng hơi giảm); áp `p ∝ T` cho hơi bão hoà bị nung nóng trong bình cứng khi còn lỏng (thực tế `p = p_sat(T)`, tăng nhanh hơn); quên `p_khô` cũng thay đổi.
**Ghép với:** T06, T17, T04 (nhiệt ẩn), T07.

---

### T13. Dẫn nhiệt

**Post [CHUẨN]:**
- Fourier: `q = −κ∇T` (W/m²). 1D: `P = κA·ΔT/L`. **Điện trở nhiệt** `R_th = L/(κA)`: nối tiếp cộng `R`; song song cộng `1/R`. Trụ: `R = ln(r₂/r₁)/(2πκℓ)`; cầu: `R = (1/r₁ − 1/r₂)/(4πκ)`.
- Phương trình nhiệt: `ρc ∂T/∂t = ∇·(κ∇T) + q_sinh`; `D = κ/(ρc)`; dừng, `κ` hằng, không nguồn: `∇²T = 0`. Thang thời gian khuếch tán `τ ~ L²/D`.
- Gộp (lumped): `mc dT/dt = −hA(T − T_môi trường)` ⇒ `τ = mc/(hA)`.
- Điều kiện giao diện: `T` liên tục; thông lượng pháp tuyến liên tục (không nguồn tại mặt).
- **Stefan (đóng băng hồ)**: `ρλ·x·dx/dt = κΔT` ⇒ `x² = 2κΔT·t/(ρλ)` (đã kiểm).
- Tương tự điện: `T ↔ U`, `P ↔ I`, `R_th ↔ R`, nhiệt dung ↔ tụ nối đất.
**Dom:** môi trường liên tục, cân bằng cục bộ.
**Pre (theo phần):** Fourier: `Kn ≪ 1`, gradient không quá lớn; mạng dừng: **trạng thái dừng** (công suất bằng nhau qua các phần tử nối tiếp), dòng nhiệt 1D (bên cách nhiệt hoặc tiết diện đổi chậm), `κ` hằng từng lớp; gộp: `Bi ≲ 0,1`; Stefan quasi-steady: `St = cΔT/λ ≪ 1` (đá 10 K: `St ≈ 0,06`); và điều kiện `x²/(Dt) = 2St ≪ 1` cho thấy hai điều kiện là một.
**Err:** đối lưu/bức xạ bị bỏ qua; điện trở tiếp xúc; `κ(T)`.
**Loại CHỖ:** **χ6 (lát/vỏ vi phân), χ4 (giao diện), nút (vùng đẳng nhiệt), χ5**.
**Trình tự cố định (ba biến thể):**
*A — Mạng nhiệt ("Nodal Analysis nhiệt")*:
1. Chia hệ thành **nút** = vùng đẳng nhiệt (`Bi ≪ 1`), gán `T_j`; nguồn nhiệt độ = nút cố định.
2. **Cạnh** nối nút với độ dẫn `G_jk = 1/R_jk = κA/L` (hoặc `hA`).
3. Mỗi nút tự do: `Σ_kG_jk(T_k − T_j) + P_j = C_j dT_j/dt` (dừng: `= 0`).
4. Hệ `G·T = P` (ma trận đối xứng, trọng số, dạng Laplace).
*B — Lát vi phân*: lát `dx`: `ρcA dx ∂T/∂t = −∂(qA)/∂x dx + sinh`; dừng: `d/dx(κA dT/dx) = 0`, tích phân được `∫dx/(κA) = ΔT/P`.
*C — Vỏ trụ/cầu*: qua vỏ bán kính `r`, `P = −κ(2πrℓ)dT/dr = const`.
*D — Mặt di động (Stefan)*: cân bằng năng lượng tại mặt: `ρλ dx/dt = q`, với `q` từ profile tuyến tính quasi-steady.
**Đầu ra Toán:** (A) hệ tuyến tính `n×n` hoặc ODE tuyến tính hệ số hằng; (B) ODE/PDE với điều kiện biên/đầu; (C) tích phân tách biến; (D) ODE tách biến.
**Bẫy:** cộng `R` sai cấu hình; nhầm mật độ thông lượng `q` với công suất `P` khi tiết diện đổi; dùng gộp khi `Bi` không nhỏ; quên nút cố định.
**Ghép với:** T04 (cấp nhiệt), T12 (sôi/ngưng), T07 (`T(z)`), X2 (bức xạ).

---

### T14. Khí thực (van der Waals)

**Post [CHUẨN]:** `(p + a n²/V²)(V − nb) = nRT`; theo mol `(p + a/v²)(v − b) = RT`.
- Tới hạn (đã kiểm): `v_c = 3b`, `p_c = a/(27b²)`, `T_c = 8a/(27Rb)`, `Z_c = 3/8`. Dạng rút gọn: `(p_r + 3/v_r²)(3v_r − 1) = 8T_r`.
- `U = νC_VT − aν²/V`; `S = νC_V ln T + νR ln(V − νb) + const`; đoạn nhiệt: `T(v − b)^{R/C_V} = const` (đã kiểm).
- Công đẳng nhiệt: `W = νRT ln[(V₂ − νb)/(V₁ − νb)] + aν²(1/V₂ − 1/V₁)`.
- Giãn tự do vào chân không (cách nhiệt): `ΔU = 0` ⇒ `ΔT = −(aν/C_V)(1/V₁ − 1/V₂) < 0` (khí lạnh đi) (dấu đã kiểm).
- Khai triển virial: `pV/(νRT) = 1 + B(T)ν/V + …`; với vdW `B = b − a/(RT)`, `T_Boyle = a/(Rb)`, nhiệt độ đảo Joule–Thomson tối đa (áp suất thấp) `T_inv = 2a/(Rb) = (27/4)T_c` [CHUẨN].
- Cân bằng lỏng–hơi dưới `T_c`: **quy tắc Maxwell (diện tích bằng nhau)**.
**Dom:** mô hình định tính tốt, định lượng gần đúng.
**Pre:** phân tử cầu cứng hút yếu; dùng đúng đơn vị theo mol hay tổng.
**Suf-detector:** đề nêu `a, b` hay "khí thực", "tới hạn", "khí nén cao", "Joule–Thomson".
**Err:** vdW không chính xác gần điểm tới hạn.
**Loại CHỖ:** χ2, **χ8 (điểm tới hạn, điểm bất ổn `∂p/∂V = 0`)**, χ4 (cân bằng hai pha).
**Trình tự cố định:**
1. Chuẩn hoá theo mol: `v = V/ν` (P4).
2. Xác định vùng: `T > T_c` (đường đơn điệu) hay `T < T_c` (có vùng bất ổn).
3. Điểm tới hạn: giải hệ `∂p/∂v = 0` và `∂²p/∂v² = 0` (hoặc nghiệm bội ba của phương trình bậc ba theo `v`).
4. Cân bằng hai pha (nếu `T < T_c`): ẩn `(v_l, v_g, p_s)`, ba phương trình: `p(v_l; T) = p_s`, `p(v_g; T) = p_s`, `p_s(v_g − v_l) = ∫_{v_l}^{v_g}p dv` (Maxwell).
5. Năng lượng/entropy: dùng `U, S` ở trên; Joule–Thomson: `H = U + pV` không đổi.
**Đầu ra Toán:** phương trình bậc ba; điều kiện điểm uốn/nghiệm bội; ba phương trình phi tuyến (Maxwell).
**Bẫy:** lẫn `V` và `v`; quên dấu của số hạng `a` trong `U`; dùng `p` vdW trong tích phân công mà quên `∫p_hút`.
**Ghép với:** T17 (đường hai pha), T02.

---

### T15. Sức căng bề mặt

**Post [CHUẨN]:**
- `E_s = σA` (`σ` J/m² = N/m); lực trên đoạn mép `F = σℓ`; màng xà phòng hai mặt: `2σℓ`.
- **Laplace**: `Δp = σ(1/R₁ + 1/R₂)`; giọt (một mặt) `2σ/R`; **bong bóng xà phòng (hai mặt) `4σ/R`**.
- **Jurin** (mao dẫn): `h = 2σcosθ/(ρgr)`; **Young**: `cosθ = (σ_SG − σ_SL)/σ_LG`.
- **Công ảo**: cân bằng ⇔ `(p_trong − p_ngoài)dV = σ dA` (cầu: `Δp·4πR²dR = σ·8πR dR ⇒ Δp = 2σ/R`).
- `σ` giảm theo T; năng lượng bề mặt **nội năng**: `u_s = σ − T dσ/dT` (nước: `dσ/dT ≈ −1,5·10⁻⁴ N/m·K` ⇒ `u_s` lớn hơn `σ` cỡ 60% ở nhiệt độ phòng [CẦN KIỂM số]).
- Kelvin: `ln[p_v(r)/p_sat] = 2σμ/(ρRTr)` (giọt).
**Dom:** mặt phân cách sắc nét (độ dày ≪ bán kính).
**Pre:** chất lỏng tĩnh; `r ≪ ℓ_c = √(σ/ρg)` (nghĩa là biến thiên thuỷ tĩnh trong vùng cong không đáng kể) hay `Bo ≪ 1`; `σ` đều (không Marangoni).
**Err:** `r` cỡ nm (σ phụ thuộc độ cong, Tolman); chất hoạt động bề mặt; hiệu ứng động lực học.
**Loại CHỖ:** **χ4 (mặt cong)**, đường tiếp xúc ba pha, **χ3 (dịch chuyển ảo)**.
**Trình tự cố định (ba cách tương đương [ĐỀ XUẤT]):**
1. Xác định *mọi* mặt phân cách và diện tích `A(x)` theo tham số hình học.
2. **Cách lực:** mặt cắt tưởng tượng; cân bằng lực áp suất trên diện tích cắt với lực căng trên chu vi (đếm số mặt).
3. **Cách công ảo:** `dE_tot = 0` với `E = σA − Δp·V`.
4. **Cách năng lượng:** với quá trình, `ΔE_s = σΔA` chuyển thành nhiệt/động năng/khác (T02).
5. Nếu có khí trong bọt: `p_khí = p_ngoài + Δp` (T06); chọn đẳng nhiệt/đoạn nhiệt bằng P3.
**Đầu ra Toán:** đại số; cực tiểu năng lượng; ODE hình dạng Young–Laplace nếu `Bo` không nhỏ (V3).
**Bẫy:** quên hai mặt của màng; chiều góc tiếp xúc; chiều cao mao dẫn đo từ mặt tự do phẳng; **mao dẫn không bảo toàn năng lượng cơ học**: công của lực căng gấp *đôi* độ tăng thế năng (đã kiểm `PE/W = 1/2`), nửa còn lại tiêu tán; dùng `σΔA` thay cho biến thiên nội năng khi đề yêu cầu chính xác cao (§6.F).

---

### T16. Động học phân tử chất khí nâng cao; "khí kém" (khí loãng / khí kém lí tưởng) **[CẦN KIỂM cách hiểu tên]**

**Post [CHUẨN]:**
- Phân bố năng lượng: `f(ε)dε = (2/√π)(kT)^{−3/2}√ε·e^{−ε/kT}dε`. Boltzmann: `n(z) = n₀exp(−U(z)/kT)` (khí quyển, ly tâm, lắng).
- Dòng phân tử qua đơn vị diện tích: `Φ = n v̄/4 = p/√(2πmkT)`. Năng lượng tịnh tiến trung bình của phân tử **thoát ra** (theo dòng): `2kT` (đã kiểm; khác `3kT/2` của phân tử trong bình).
- Phun (effusion) từ bình thể tích `V` qua lỗ `A`: `dN/dt = −(A v̄/4V)N` ⇒ `τ = 4V/(A v̄)`.
- Hai bình nối qua lỗ nhỏ với `Kn ≫ 1`, nhiệt độ `T₁ ≠ T₂`: cân bằng khi **`p₁/√T₁ = p₂/√T₂`** (thermal transpiration), *không* phải `p₁ = p₂`.
- Định luật Graham: tốc độ phun `∝ 1/√μ`.
- Quãng đường tự do: `λ = 1/(√2 π d² n) = kT/(√2 π d² p)`; tần số va chạm `z = v̄/λ`; xác suất không va chạm qua quãng `x`: `e^{−x/λ}`.
- Số Knudsen `Kn = λ/L`: `≲ 0,01` liên tục; `0,01–0,1` trượt; `0,1–10` chuyển tiếp; `≳ 10` phân tử tự do (ngưỡng mang tính quy ước).
- Vận chuyển (mô hình quãng đường tự do, hệ số bậc 1 phụ thuộc mô hình [CẦN KIỂM]): `η ≈ (1/3)ρv̄λ`; `D ≈ (1/3)v̄λ`; `κ ≈ (1/3)ρc_v v̄λ` ⇒ `η, κ` **độc lập áp suất** khi `Kn ≪ 1`; khi `Kn ≫ 1` dẫn nhiệt qua khe `∝ p`.
- Bảo toàn năng lượng khi phun (bình cách nhiệt): `T ∝ N^{1/i}`, `p ∝ N^{1+1/i}` (§6.B, đã kiểm).
**Pre:** effusion: `Kn = λ/d_lỗ ≫ 1`, thành lỗ mỏng, khí trong bình gần cân bằng, ra chân không (nếu không, dòng thực = hiệu hai dòng `(n₁v̄₁ − n₂v̄₂)/4`).
**Err:** `Kn ~ 1` chuyển tiếp; `Kn ≪ 1` là chảy thuỷ động (chế độ ngược, không thuộc syllabus).
**Loại CHỖ:** **χ9 (nhóm vận tốc `d³v`), χ4 (phần tử lỗ)×χ5 (`dt`)**, χ6 (mức thế năng).
**Trình tự cố định ("tích phân trên phân bố"):**
1. Chọn hàm cần trung bình `g(v)` và **trọng số** (theo số hạt: `f`; theo dòng: `v_n f`).
2. Viết `∫g(v)f(v)d³v` (toạ độ cầu; bán cầu cho dòng).
3. Rút gọn bằng bảng Gauss (Phụ lục A).
4. Dán vào sổ cái (T02, χ10): năng lượng, số hạt ⇒ ODE cho `N(t)`, `T(t)`.
**Đầu ra Toán:** tích phân Gauss/Gamma; ODE tuyến tính/tách biến.
**Bẫy:** nhầm trung bình theo dòng và theo số hạt (`2kT` vs `1,5kT`); dùng `p₁ = p₂` khi `Kn ≫ 1`; dùng Bernoulli/thuỷ động khi lỗ nhỏ hơn `λ`.

---

### T17. Phương trình Clapeyron–Clausius

**Post [CHUẨN]:** `dp/dT = L/(TΔv)` (`L` và `Δv` cùng cơ sở: cùng theo mol hoặc cùng theo kg).
- Hơi ≈ lí tưởng, bỏ `v_lỏng`: `d ln p/dT = L_m/(RT²)` ⇒ `p = p₀exp[−(L_m/R)(1/T − 1/T₀)]` (`L` hằng).
- Nóng chảy: `Δv = v_l − v_s`; **nước: `Δv < 0` ⇒ đường nóng chảy dốc âm**: `dp/dT ≈ −13,5 MPa/K` ⇔ điểm đóng băng giảm `≈ 0,0075 K/atm` (đã kiểm).
- `L` phụ thuộc T: `dL/dT ≈ c_p^hơi − c_lỏng` (hơi lí tưởng, lỏng không nén) [CHUẨN, xấp xỉ].
- Suy từ chu trình Carnot vi phân qua đường cân bằng: `dp·Δv = L dT/T`. Hoặc từ `μ₁(T,p) = μ₂(T,p)` ⇒ `dp/dT = Δs/Δv`.
**Pre:** hai pha cân bằng dọc theo đường; chất tinh khiết; xấp xỉ: hơi lí tưởng, `v_l ≪ v_g`, `L` hằng trên khoảng đang xét.
**Err:** `ΔL/L` trong khoảng T; hơi không lí tưởng ở áp suất cao.
**Loại CHỖ:** **χ8 (điểm/đoạn trên đường cân bằng)**, χ7 (chu trình vi phân).
**Trình tự cố định:**
1. Xác định hai pha và chiều chuyển; lấy `L, Δv` tại điểm biết.
2. Viết ODE `dp/dT = L/(TΔv)`.
3. Chọn xấp xỉ hợp lệ và ghi vào Err: (hơi lí tưởng ⇒ tách biến bằng `ln p`); (nóng chảy `Δv` hằng ⇒ `p − p₀ = (λ/Δv)ln(T/T₀)`); (thay đổi nhỏ ⇒ tuyến tính `Δp = (L/TΔv)ΔT`).
4. Điều kiện đầu: điểm ba hoặc điểm sôi tại 1 atm.
**Đầu ra Toán:** ODE tách biến bậc 1 ⇒ logarit/mũ; hoặc xấp xỉ tuyến tính.
**Bẫy:** trộn `L` theo mol với `Δv` theo kg; T °C; dấu `Δv`; dùng `L` hằng trên khoảng rộng.
**Ghép với:** T12 (dạng `p_sat`), T07 (nhiệt độ sôi theo độ cao), T14 (đường hai pha vdW).

---

## CÔNG CỤ KỀ CẬN (không nằm rõ trong bảng, thường xuất hiện) **[ĐỀ XUẤT]**

### X1. Giãn nở nhiệt
`ΔL = αLΔT`; `ΔV = βVΔT` (`β ≈ 3α` cho đẳng hướng); `ρ(T) = ρ₀/(1 + βΔT)`. **Pre:** `ΔT` nhỏ, hệ số hằng. **CHỖ:** χ2. Bẫy: lỏng dãn nở nhiều hơn bình chứa.

### X2. Bức xạ nhiệt
Công suất bức xạ `P = εσ_SB·A·T⁴`; hai vật: `P_tịnh = εσ_SB·A(T⁴ − T_mt⁴)` (`σ_SB = 5,67·10⁻⁸ W/m²K⁴`). **Pre:** vật xám, hệ số nhìn (view factor) hợp lí. **CHỖ:** χ4, cân bằng: `công suất hấp thụ = công suất phát`. Bẫy: `T` Kelvin; hệ số phát xạ = hệ số hấp thụ ở cùng bước sóng.

### X3. Phương trình năng lượng dòng dừng; tiết lưu
Trên đơn vị khối lượng dòng: `h₁ + v₁²/2 + gz₁ + q = h₂ + v₂²/2 + gz₂ + w_s`. Tiết lưu (cách nhiệt, không công, động năng không đổi): **`h` không đổi** ⇒ khí lí tưởng: `T` không đổi; khí thực: hiệu ứng Joule–Thomson. **Pre:** dòng dừng, hệ hở. **CHỖ:** χ1 (thể tích kiểm soát), χ4 (cửa vào/ra). Ghi chú: `pV` của dòng chảy vào/ra (công đẩy) là lí do enthalpy xuất hiện; với hạt thoát qua lỗ (T16) năng lượng mang đi theo dòng là `2kT` tịnh tiến, không phải `3kT/2`.

### X4. Cơ học
Cân bằng lực (pittông, giọt, cột chất lỏng), Newton, dao động, va chạm. **CHỖ:** χ1, χ5. Đây là nguồn của phần lớn ràng buộc ẩn §1.6.

### X5. Nhiệt Joule
`Q = I²Rt = P·t`; nguồn nhiệt `q_sinh = j²/σ_điện`. Tương tự mạng T13(A).

### X6. Phân tích thứ nguyên & luật tỉ lệ
Dùng để **kiểm tra kết quả** (đơn vị) và để suy hình dạng công thức khi chỉ cần luật tỉ lệ (`τ ~ L²/D`, `h ~ σ/(ρgr)`, `v ~ √(kT/m)`). Pre: chọn đủ tham số độc lập.

---

# §4. VẤN ĐỀ 2 — CHUYỂN VẬT LÝ → TOÁN

## 4.1. Bảng dịch (Rosetta): cấu trúc Vật Lý → cấu trúc Toán **[ĐỀ XUẤT]**

Khi quét CHỖ xong (V1), mỗi công cụ để lại một *phương trình có hình dạng biết trước*. Vấn đề 2 là **nhận ra hình dạng Toán** để chuyển sang V3 mà không phải mò.

| Cấu trúc Vật Lý | Cấu trúc Toán tương ứng | Công cụ V3 (chỉ trỏ, không giải) |
|---|---|---|
| Nhiều phần khí + ràng buộc cơ/nhiệt (T06) | Hệ phương trình **đại số** (đa thức bậc thấp, dạng song tuyến tính) | Đại số, phép thế |
| Cân bằng nhiệt có chuyển pha (T04) | **Hàm từng khúc đơn điệu** `F(T) = H₀`, tìm nghiệm bằng chia khoảng | Xét khoảng, phương trình bậc nhất |
| Quá trình `p(V)` bất kỳ (T08) | Tích phân xác định `∫p dV`; **nghiệm của đạo hàm** (`dQ = 0`, `dT = 0`) | Giải tích 1 biến |
| Chu trình (T09) | Tổng tích phân từng khúc; **tối ưu 1 biến hoặc có ràng buộc** | Cực trị, nhân tử Lagrange |
| Nguyên lí 2 (T10) | **Đẳng thức/bất đẳng thức** logarit; hệ (năng lượng + entropy) | Lấy mũ, bất đẳng thức |
| Lát khí vi phân (T07) | **ODE bậc 1** tách biến/tuyến tính | Tách biến, thừa số tích phân |
| Phân bố Maxwell (T05, T16) | **Tích phân Gauss/Gamma** | Bảng tích phân, Gamma |
| Phun hạt (T16) | **ODE tuyến tính bậc 1** (số hạt); ODE tách biến khi thêm năng lượng | Tách biến |
| Mạng nhiệt dừng (T13A) | **Hệ tuyến tính đối xứng** `G·T = P` (Laplace có trọng) | Đại số tuyến tính |
| Mạng nhiệt quá độ | **ODE tuyến tính hệ** `C Ṫ = −L T + P` | Trị riêng/vector riêng |
| Dẫn nhiệt liên tục (T13B) | **PDE khuếch tán** + điều kiện biên/đầu; dừng: ODE | Tách biến, chuỗi Fourier |
| Mặt di động Stefan (T13D) | **ODE tách biến** cho `x(t)` | Tích phân |
| Điểm tới hạn vdW (T14) | **Nghiệm bội ba** của phương trình bậc ba / hệ hai đạo hàm bằng 0 | Đạo hàm, Viète |
| Hai pha vdW (T14) | **Ba phương trình phi tuyến** (đẳng áp hai nhánh + diện tích bằng nhau) | Tích phân, thế số/số học |
| Sức căng bề mặt (T15) | **Cực tiểu năng lượng/công ảo**; ODE hình dạng (Young–Laplace) | Biến phân, ODE |
| Clapeyron–Clausius (T17) | **ODE tách biến** `d ln p/dT` | Tích phân |
| Hơi ẩm (T12) | **Hàm từng khúc có điểm gãy** (nhánh khô/bão hoà) | Xét nhánh |
| Nguội/nóng dần (T13 gộp) | ODE tuyến tính bậc 1 ⇒ hàm mũ | Nghiệm mũ |
| "có thể/không thể" | **Kiểm tra bất đẳng thức** `ΔS_tot ≥ 0` | Bất đẳng thức |
| Đồ thị cho sẵn | Đọc thành **hàm** (đường thẳng, hyperbol, đa biến) bằng P6 | Nội suy đại số |

**Kiểm tra loại Q ↔ dạng Toán (một dòng):**
Q là *giá trị số* ⇒ giải hệ; Q là *hàm/biểu thức* ⇒ giữ ẩn tự do; Q là *cực trị* ⇒ đạo hàm/ràng buộc; Q là *"khi nào"* ⇒ nghiệm của bất đẳng thức/điểm gãy; Q là *"có thể không"* ⇒ dấu của `ΔS_tot`.

## 4.2. Bốn sổ cái bảo toàn (mỗi *hệ con × khoảng thời gian* sinh một dòng) **[ĐỀ XUẤT]**

| Sổ cái | Dạng phương trình | Số hạng hay bị quên | Dấu |
|---|---|---|---|
| **Số hạt / khối lượng** | `Δ(số hạt) = vào − ra` | hơi bay hơi/ngưng tụ, rò rỉ, phun | đẳng thức |
| **Năng lượng** (T02) | `Δ(U + KE + PE + E_s + E_lò xo) = Q − W` | nhiệt dung bình/pittông; công chống khí quyển; năng lượng mang bởi hạt thoát (`2kT`); ma sát | đẳng thức |
| **Xung lượng / lực** | `Σ F = m a` (cân bằng: `= 0`) | áp suất khí quyển; `ρgh`; lực căng bề mặt | đẳng thức |
| **Entropy** (T10) | `ΔS_tot ≥ 0` (`= 0` thuận nghịch) | entropy của nguồn; entropy sinh ra ở cạnh bất thuận nghịch | **bất đẳng thức** |

Đếm CHỖ sổ cái: nếu có `s` hệ con và `k` khoảng thời gian đặc trưng, tối đa `s·k` dòng cho mỗi sổ cái. Thường chỉ một số ít độc lập; đó là lý do §1.7 đếm hạng.

## 4.3. Chín thuật toán "kiểu Nodal Analysis" cho Nhiệt **[ĐỀ XUẤT]**

Đây là các *quy trình máy móc* (mỗi cái đáp lại câu hỏi "trình tự cố định là gì?") và **phần trực giác còn lại**:

| # | Thuật toán | Công cụ | Đầu vào → Đầu ra | Trực giác còn sót |
|---|---|---|---|---|
| A1 | **H-bracket** (enthalpy từng khúc) | T04, T01 | vật + `T` đầu → `T_f`, tỉ lệ pha | ~0 |
| A2 | **Bảng trạng thái** (ledger) | T06, P9 | hệ khí + ràng buộc → hệ đại số | quyết định cân bằng/quasi-static |
| A3 | **Đồ thị trạng thái + chia cạnh tại `dQ = 0`** | T08, T09 | chu trình → `Q_vào, Q_ra, W, η` | ~0 khi cạnh đã biết luật |
| A4 | **Sổ cái hai cột năng lượng–entropy** | T02, T10 | máy/vật + trạng thái cuối → `W_max`, `T_f`, khả thi? | đủ "vũ trụ" |
| A5 | **Lát vi phân** | T07, T13B | trường + luật nhiệt → ODE | chọn luật nhiệt (đẳng nhiệt/đoạn nhiệt) |
| A6 | **Mạng nhiệt (nút–cạnh)** | T13A | vật + tiếp xúc → `G·T = P` | chọn nút đẳng nhiệt (`Bi`) |
| A7 | **Giả thiết – kiểm tra – nhánh** | T12, T04, T14 | biến điều khiển → hàm từng khúc | điểm nào là gãy |
| A8 | **Hình trụ va chạm / tích phân trên phân bố** | T11, T16 | nhóm hạt + tường/lỗ → áp suất/dòng | chọn trọng số (số hạt vs dòng) |
| A9 | **Ba cách cho mặt cong** (lực / công ảo / năng lượng) | T15 | mặt cong → `Δp`, `h`, năng lượng | đếm số mặt |

Nhận xét thành thật **[ĐỀ XUẤT]**: A1, A3 gần như thuần thuật toán; A2, A4, A6, A7, A8 cần *một* quyết định mô hình; A5, A9 cần biết chọn luật phụ (nhiệt/đường). Không có thuật toán nào loại bỏ hoàn toàn việc **chọn mô hình** (§8).

---

# §5. KHI NHIỀU "DẠNG" CÙNG LÚC: GHÉP CÔNG CỤ QUA BIẾN GIAO DIỆN

Theo "Đề xuất cách giải quyết" ở PHẦN 0.2: áp dụng độc lập từng dạng, rồi nối bằng V3 + trực giác. Tôi cụ thể hoá bước "nối":

**Quy trình ghép [ĐỀ XUẤT]:**
1. **Mỗi hệ con** tự sinh phương trình *trong biến của nó* (bằng thuật toán A-tương ứng).
2. **Biến giao diện** là biến xuất hiện ở hai hệ con: `p` (mặt di động), `T` (tiếp xúc nhiệt), **thông lượng** (`P`, `dN/dt`), khối lượng chuyển pha, vị trí `x`.
3. **Điều kiện khớp** tại giao diện (§1.6, mục 6): `p` bằng (hoặc Laplace), `T` bằng, thông lượng liên tục, số hạt bảo toàn.
4. **Thứ tự ưu tiên viết**: (i) đẳng thức cơ/nhiệt; (ii) bảo toàn; (iii) luật cấu thành (khí, Fourier); (iv) nhánh/bất đẳng thức.
5. Đếm hạng (§1.7) cho *toàn hệ*.

**Các cặp hay gặp:**

| Ghép | Biến giao diện | Cách nối |
|---|---|---|
| T06 + X4 | `p` (pittông) | `p = p₀ + mg/A (+ kx/A)` vào ô bảng trạng thái |
| T06 + T07 | `p(z)` | khí quyển/cột chất lỏng: `dp = −ρg dz` vào ràng buộc `p` |
| T08 + T10 | `Q, W, ΔS` | mỗi cạnh: `ΔS` bằng đường thuận nghịch, kiểm `ΔS_tot` |
| T04 + T10 | `T_f` | nguồn hữu hạn: `T` đổi; `ΔS = C ln(T₂/T₁)` |
| T12 + T06 (+ T08) | `p_v`, `p_khô` | Dalton; nhánh bão hoà thêm nhiệt ẩn vào sổ cái năng lượng |
| T12 + T17 + T07 | `p_sat(T)`, `p(z)` | nhiệt độ sôi theo độ cao: `p(z)` từ T07, `T_b` từ T17 |
| T14 + T17 | `p_s(T)` | đường hai pha vdW từ Maxwell so với Clausius–Clapeyron |
| T15 + T06 | `p_khí`, `Δp` | bọt: `p_khí = p_ngoài + Δp`, `ν` cố định |
| T15 + T12 | `p_v(r)` | Kelvin: giọt nhỏ, `p_v` tăng |
| T13 + T04 | `P`, `T` mặt | cấp nhiệt qua vách, mặt băng: T13D |
| T16 + T02 | `N(t)`, `T(t)` | phun: sổ cái số hạt + năng lượng (`2kT`/hạt) |
| T16 + T13 | `κ(p)` | khí loãng dẫn nhiệt `∝ p` (`Kn ≫ 1`) |
| T05/T11 + T08 | bất biến đoạn nhiệt | tường di động: `v → v + 2u` cho đoạn nhiệt vi mô |

---

# §6. CHÍN VÍ DỤ HOÀN CHỈNH (V1 + V2; dừng trước V3)

> Tất cả đề do tôi tự soạn theo dạng; không phải đề thi thật. Mỗi ví dụ: **Đề → V1 (mô hình, công cụ, CHỖ, Pre) → V2 (bài Toán đầu ra, đếm ẩn) → (đối chiếu, nếu có).**

## 6.A. Trộn đá, nước, hơi (T04 + T01 + T12) — H-bracket

**Đề.** Bình cách nhiệt, bỏ qua nhiệt dung bình. Cho 200 g đá −10 °C và 50 g hơi nước 100 °C, `p = 1 atm`. Tìm trạng thái cân bằng cuối.

**V1.** Vật: đá (χ1), hơi (χ1). Ngưỡng (χ8): đá `−10 → 0` (nóng), `0` tan, nước `0 → 100`; hơi ngưng ở `100`. Pre (T04): hệ cô lập, `p` cố định, `c` hằng (`c_đá = 2100`, `c_nước = 4186`, `λ = 3,34·10⁵`, `L = 2,26·10⁶ J/kg`).

**V2.**
1. Nhiệt cần để đá về nước 0 °C: `Q₁ = 0,2·2100·10 + 0,2·3,34·10⁵ = 71 000 J`.
2. Nhiệt cần để toàn bộ về nước 100 °C: `154 720 J`.
3. Nhiệt hơi nước toả tối đa ngưng tại 100 °C: `Q_ng = 0,05·2,26·10⁶ = 113 000 J`; ngưng rồi hạ xuống 0 °C: `133 930 J`.
4. So sánh: `71 000 < 113 000 < 154 720` ⇒ **đá tan hết, hơi ngưng hết, nước cuối ở `0 < T_f < 100`**.
5. Bài Toán: **một phương trình bậc nhất** `71 000 + m_đ·c_n·T_f = 113 000 + m_h·c_n(100 − T_f)`.
*[Đối chiếu V3]:* `T_f ≈ 60,1 °C` (đã kiểm).

**Đếm:** 1 ẩn (`T_f`), 1 phương trình ⇒ đóng kín. Bước "chọn nhánh" là bước 4 (không đoán mà so ngưỡng).

## 6.B. Phun hạt ra chân không, bình cách nhiệt (T16 + T02 + T05 + T06)

**Đề.** Bình cách nhiệt thể tích `V`, khí lí tưởng (`i` bậc tự do), ban đầu `N₀` phân tử, nhiệt độ `T₀`, thông ra chân không qua lỗ diện tích `A` (`Kn ≫ 1`, thành lỗ mỏng). Tìm quy luật `T(N)`, `p(N)`, và phương trình cho `N(t)`.

**V1.** Hệ: **khí còn trong bình** (χ1), *hệ hở* (hạt thoát). CHỖ: (lỗ `A`) × (`dt`) (χ4×χ5). Công cụ: T16 (dòng `n v̄/4`, năng lượng theo dòng), T05 (`U = (i/2)NkT`), T02 (sổ cái năng lượng), T06 (`p = NkT/V`). Pre: `Kn ≫ 1`; bậc tự do nội (quay, …) độc lập với vận tốc tịnh tiến (đúng ở cân bằng) ⇒ mỗi hạt thoát mang thêm năng lượng nội trung bình `((i−3)/2)kT`.
**Loại bỏ công cụ sai:** *Poisson cho phần khí còn lại* thuộc Pre sai (hệ không kín, quá trình chọn lọc hạt nhanh). Nếu áp vẫn sẽ cho `T ∝ N^{2/i}` thay vì `N^{1/i}` (khác số mũ).

**V2.**
- Sổ cái số hạt (`dt`): `dN = −(A v̄/4V)N dt`, `v̄ = √(8kT/πm)`.
- Sổ cái năng lượng: năng lượng mỗi hạt thoát `= 2kT + ((i−3)/2)kT = ((i+1)/2)kT`; `d[(i/2)NkT] = ((i+1)/2)kT·dN` (với `dN < 0`).
- Khử `dt`: **ODE tách biến** cho `T(N)`: `(i/2)N dT = (1/2)T dN`.
- Sau khi có `T(N)`: `dN/dt = −(A/4V)√(8kT(N)/πm)·N` là ODE tách biến cho `N(t)`.
*[Đối chiếu, đã kiểm]:* `T = T₀(N/N₀)^{1/i}`, `p = p₀(N/N₀)^{1+1/i}`.

**Đếm:** ẩn `N(t), T(t)`, hai sổ cái ⇒ đóng kín.

## 6.C. Chu trình tam giác có đoạn thẳng (T08 + T09 + T10)

**Đề.** `ν` mol khí đơn nguyên tử. Chu trình 1→2→3→1 trên p–V (V ngang, p đứng): 1→2 đoạn thẳng từ `(V₁, p₁)` đến `(V₂, p₂)` với `V₂ > V₁`, `p₂ < p₁`; 2→3 đẳng áp nén tới `V₁`; 3→1 đẳng tích. Tìm hiệu suất.

**V1.** Đỉnh (χ2): 1 `(V₁,p₁)`, 2 `(V₂,p₂)`, 3 `(V₁,p₂)`. Cạnh (χ3): 1→2 tổng quát (T08), 2→3 đẳng áp, 3→1 đẳng tích. **Điều kiện đổi dấu Q trên cạnh 1→2 (χ8):** `γp + V·p′ = 0`. Chiều: kiểm bằng dấu diện tích: `V₁→V₂` đi xuống rồi trái rồi lên ⇒ thuận chiều kim đồng hồ ⇒ động cơ.

**V2.**
- Đoạn thẳng `p = p₁ + s(V − V₁)`, `s = (p₂ − p₁)/(V₂ − V₁) < 0`.
- Điểm đổi dấu: **`γ[p₁ + s(V* − V₁)] + s·V* = 0`**, với điều kiện tồn tại `V₁ < V* < V₂`; nếu `V*` ngoài khoảng thì cạnh 1→2 không đổi dấu.
- `Q₃₁ = (C_V/R)V₁(p₁ − p₂)`; `Q₁→V* = (C_V/R)(p*V* − p₁V₁) + (p₁ + p*)(V* − V₁)/2`.
- `W = ½(V₂ − V₁)(p₁ − p₂)` (diện tích tam giác).
- **`η = W/(Q₃₁ + Q₁→V*)`** (phần 1→2 sau `V*` và 2→3 là toả nhiệt).
- Kiểm: `η ≤ 1 − T_min/T_max`.

**Đếm:** tham số `p₁, p₂, V₁, V₂`; `V*` là một nghiệm của phương trình bậc nhất; đóng kín.

## 6.D. Nén đẳng nhiệt không khí ẩm (T12 + T06 + T08)

**Đề.** Xilanh có pittông chứa không khí ẩm `T` không đổi, thể tích ban đầu `V₀`, độ ẩm tương đối `f < 1`, áp suất tổng ban đầu `p₀`. Nén chậm đẳng nhiệt. Mô tả `p(V)` và lượng nước ngưng.

**V1.** Hệ: khí ẩm (khô + hơi, Dalton). Công cụ: T12 (thuật toán A7), T06, T08 (đẳng nhiệt). Pre: hơi lí tưởng, không có lỏng ban đầu, thể tích lỏng ngưng bỏ qua.

**V2.**
- Giả thiết không lỏng: `p_v^giả = f p_sat V₀/V`; `p_khô = p_khô0 V₀/V`, `p_khô0 = p₀ − f p_sat`.
- **Điểm gãy (χ8):** `p_v^giả = p_sat ⇔ V_c = f V₀`.
- Nhánh `V ≥ V_c`: `p(V) = (p₀)·V₀/V` (Boyle cho hỗn hợp).
- Nhánh `V < V_c`: `p_v = p_sat`, `p(V) = p_sat + p_khô0·V₀/V`; `ν_v = p_satV/RT`; lượng ngưng `m = μ_w(f p_sat V₀ − p_sat V)/RT`.
- Kiểm liên tục tại `V_c`: hai nhánh cho cùng `p` (đã kiểm đại số).
Bài Toán: hàm từng khúc có điểm gãy tại `f V₀`, đường `p–V` đổi độ dốc.

## 6.E. Lớp băng dày lên (T13D + T04)

**Đề.** Mặt hồ ở 0 °C (nước dưới đáy giữ 0 °C). Không khí giữ mặt trên băng ở `T_s < 0 °C`. Tìm bề dày băng theo thời gian.

**V1.** CHỖ: giao diện di động (χ4) và lát băng (χ6). Công cụ: T13 (Fourier, Stefan), T04 (`λ`). Pre: `St = cΔT/λ ≪ 1` (`≈ 0,06` với 10 K) ⇒ profile tuyến tính quasi-steady; nước dưới ở đúng 0 °C (không có dòng nhiệt từ dưới lên) (nếu không có thêm số hạng); nhiệt độ bề mặt băng bằng nhiệt độ không khí (giả thiết đã nêu).

**V2.**
- Dòng nhiệt: `q = κΔT/x`, với `ΔT = 0 − T_s`.
- Cân bằng mặt (sổ cái năng lượng tại giao diện): `ρλ(dx/dt) = q`.
- **ODE tách biến:** `ρλ·x·dx/dt = κΔT`, `x(0) = 0`.
*[Đối chiếu, đã kiểm]:* `x² = 2κΔT·t/(ρλ)`; điều kiện quasi-steady `x²/(Dt) = 2St ≪ 1`.

## 6.F. Hai giọt nước hợp nhất (T15 + T02 + T04)

**Đề.** Hai giọt nước bán kính `r` hợp nhất thành một giọt trong hệ cô lập nhiệt. Ước lượng độ tăng nhiệt độ.

**V1.** Hệ: khối nước hai giọt (χ1) ở hai thời điểm (χ5). Công cụ: T15 (`E_s`), T02 (sổ cái năng lượng), T04 (`Q = mcΔT`). Pre: hệ cô lập; năng lượng bề mặt chuyển hoàn toàn thành nhiệt (dao động cơ tiêu tán; bỏ qua bay hơi, bức xạ).

**V2.**
- Bảo toàn thể tích: `R = 2^{1/3}r`.
- `ΔA = 4πr²(2 − 2^{2/3})`.
- Sổ cái năng lượng: `ΔE_s = m c ΔT`, `m = (8/3)πr³ρ`, với **quy ước `E_s = σA`**.
*[Đối chiếu, mô hình tiêu chuẩn]:* `ΔT = 3σ(2 − 2^{2/3})/(2ρcr)`.
**Cảnh báo về mô hình [CẦN KIỂM]:** `σA` là năng lượng *tự do*. Trong bảo toàn năng lượng chính xác, số hạng đúng là *nội năng bề mặt* `u_s = σ − T dσ/dT`, với nước lớn hơn `σ` cỡ 1,6 lần. Đề HSG thường ngầm dùng `σA`; nếu đề cho `dσ/dT`, dùng `u_s`. Đây là **Err** cần ghi.

## 6.G. Khí vdW: điểm tới hạn và cân bằng hai pha (T14)

**Đề.** Khí vdW `(p + a/v²)(v − b) = RT`. (a) Tìm điểm tới hạn. (b) Ở `T < T_c`, tìm `p_s(T)` khi lỏng–hơi cùng tồn tại.

**V1.** Công cụ: T14. CHỖ: (a) χ8 điểm uốn nằm ngang; (b) χ4 cân bằng hai pha. Pre: mô hình vdW.

**V2.**
- (a) Ẩn `(v_c, T_c)`; hai phương trình `∂p/∂v = 0`, `∂²p/∂v² = 0`. *[Đối chiếu, đã kiểm]:* `v_c = 3b`, `T_c = 8a/(27Rb)`, `p_c = a/(27b²)`.
- (b) Ẩn `(v_l, v_g, p_s)`, ba phương trình: `p(v_l) = p_s`, `p(v_g) = p_s`, `p_s(v_g − v_l) = ∫_{v_l}^{v_g}p dv` (Maxwell). Đóng kín (3/3).

## 6.H. Mạng dẫn nhiệt kiểu cầu Wheatstone (T13A)

**Đề.** Hai nguồn nhiệt `T_h` và `T_c`. Bốn thanh nối qua hai nút trung gian `a, b`: `h→a` (`G₁`), `h→b` (`G₂`), `a→c` (`G₃`), `b→c` (`G₄`); và thanh cầu `a↔b` (`G₅`). Bỏ qua mất nhiệt bên. Tìm công suất tổng.

**V1.** Nút: `a, b` là vùng đẳng nhiệt (`Bi ≪ 1`). CHỖ: nút (2 nút tự do), cạnh (5 cạnh). Pre: dừng, dòng nhiệt 1D trong từng thanh, `κ` hằng.

**V2.**
- Nút `a`: `G₁(T_h − T_a) + G₅(T_b − T_a) + G₃(T_c − T_a) = 0`.
- Nút `b`: `G₂(T_h − T_b) + G₅(T_a − T_b) + G₄(T_c − T_b) = 0`.
- **Hệ tuyến tính 2×2** cho `T_a, T_b`; công suất `P = G₁(T_h − T_a) + G₂(T_h − T_b)`.
- **Cầu cân bằng** (`G₁/G₂ = G₃/G₄`) ⇒ `T_a = T_b`, thanh `G₅` không truyền nhiệt (tương tự điện: kiểm được bằng thế vào hệ).
Đóng kín: 2 ẩn, 2 phương trình.

## 6.I. Khí quyển đoạn nhiệt (T07 + T06 + T08)

**Đề.** Khí quyển khô, `μ`, `γ`, `g` hằng, được trộn đoạn nhiệt. Tìm `T(z)` và `p(z)`; hỏi giới hạn trên.

**V1.** CHỖ: lát `dz` (χ6). Công cụ: T07 (lát), T06 (`ρ = pμ/RT`), T08 (quan hệ đoạn nhiệt `p ∝ T^{γ/(γ−1)}` giữa các lớp của khí quyển được trộn). Pre: xem T07.

**V2.**
- Cân bằng lát: `dp/dz = −(μg/RT)p`.
- Luật nhiệt: `p = C·T^{γ/(γ−1)}`.
- Khử `p`: **`dT/dz = −((γ−1)/γ)(μg/R) ≡ −Γ`** (hệ số suy giảm đoạn nhiệt `≈ 9,8 K/km`, đã kiểm).
- `T(z) = T₀ − Γz`; `p(z) = p₀(1 − Γz/T₀)^{γ/(γ−1)}`.
**Err (chỗ mô hình gãy):** `T → 0` tại `z = T₀/Γ ≈ 29 km` (với `T₀ = 288 K`). Đó là **hệ quả ngoài Pre** (không ngưng tụ, `γ` hằng, `g` hằng), không phải kết luận vật lí. Ghi trong bài như một giới hạn mô hình.

---

# §7. BẢNG TRA NHANH VÀ LỖI KINH ĐIỂN

## 7.1. Dấu hiệu trong đề → công cụ → CHỖ cần duyệt **[ĐỀ XUẤT]**

Dùng như **danh sách kiểm** (không phải để bỏ qua các công cụ khác): thấy dấu hiệu ⇒ *chắc chắn phải xét* công cụ đó.

| # | Dấu hiệu | Công cụ | CHỖ duyệt |
|---|---|---|---|
| 1 | "nhiệt độ cuối khi trộn/thả vào" | T04 (A1) | mỗi vật, mỗi ngưỡng đổi pha |
| 2 | "đá", "hơi nước", "tan", "sôi" | T01, T04, T12 | trạng thái, ngưỡng |
| 3 | "nhiệt kế sai/lệch" | T03 | hai điểm chuẩn |
| 4 | "pittông", "hai ngăn", "van" | T06 + X4 (A2) | mỗi phần khí × mỗi trạng thái |
| 5 | "khí thoát/bơm thêm" | P1 + T06 (hoặc T16 nếu "lỗ nhỏ") | hệ khối lượng cố định |
| 6 | "thuỷ ngân/cột chất lỏng trong ống" | T06 + T07 + X4 | mặt tự do, đáy cột |
| 7 | "khí quyển", "độ cao" | T07 (A5) | lát `dz` |
| 8 | "quay", "ly tâm" | T07/T16 | lát `dr` |
| 9 | "chu trình", "hiệu suất" | T09 (A3) | đỉnh, cạnh, điểm gãy |
| 10 | "động cơ", "máy lạnh" | T09, T10 | chu trình, nguồn |
| 11 | "hiệu suất/công cực đại" | T10 (A4) | `ΔS_tot = 0` |
| 12 | "hai vật nhiệt độ khác nhau + máy" | T10 | nhiệt độ cuối `T_f` |
| 13 | "có tự xảy ra không?" | T10 | `ΔS_tot` |
| 14 | "đồ thị p–V không chuẩn" | T08 + P6 | điểm `dQ = 0`, `T_max` |
| 15 | "nhiệt dung của quá trình" | T08 (đa biến) | `C = C_V + R/(1−n)` |
| 16 | "nén/giãn nhanh, đột ngột, buông pittông" | T02 (không Poisson) | bảo toàn năng lượng |
| 17 | "lò xo trong xilanh" | X4 + T08 | cân bằng lực, thế năng |
| 18 | "dao động pittông", "âm thanh" | T08 (γ) + X4 | `ω² = γpA²/mV` |
| 19 | "va chạm phân tử với tường", "chùm hạt" | T11 (A8) | `dA × dt` |
| 20 | "vận tốc căn quân phương", "Maxwell" | T05/T16 | trung bình trên phân bố |
| 21 | "lỗ nhỏ", "phun", "chân không" | T16 | `Kn`, `dA × dt` |
| 22 | "quãng đường tự do trung bình" | T16 | `λ`, `Kn` |
| 23 | "độ ẩm", "sương", "ngưng tụ" | T12 (A7) | điểm gãy `V_c`/`T_c` |
| 24 | "sôi ở núi cao/áp suất thấp" | T12 + T17 + T07 | `p(z)`, `p_sat` |
| 25 | "dẫn nhiệt qua tường/nhiều lớp/thanh" | T13 (A6, B) | nút, cạnh, lát |
| 26 | "lớp băng dày lên" | T13D + T04 | mặt di động |
| 27 | "nguội/nóng dần theo thời gian" | T13 gộp | `Bi`, `τ` |
| 28 | "khí thực", "hằng số a, b", "tới hạn" | T14 | `∂p/∂v`, Maxwell |
| 29 | "giãn vào chân không, hạ nhiệt độ" | T14 + T02 | `ΔU = 0` |
| 30 | "bong bóng", "giọt", "màng xà phòng" | T15 (A9) | mặt cong |
| 31 | "ống mao dẫn" | T15 | `Bo`, góc tiếp xúc |
| 32 | "điểm nóng chảy phụ thuộc áp suất", "trượt băng" | T17 | `Δv`, dấu |
| 33 | "áp suất hơi theo T (hàm mũ)" | T17 | `L`, `T₀` |
| 34 | "bức xạ", "T⁴", "cân bằng bức xạ" | X2 | mặt, hệ số phát xạ |
| 35 | "tiết lưu", "qua nút xốp" | X3/T14 | `h` không đổi |

## 7.2. Ba mươi lỗi kinh điển (kèm công cụ chịu trách nhiệm)

1. **(T02, T08)** Đổi dấu công giữa quy ước `ΔU = Q − W` và `ΔU = A + Q`.
2. **(T08)** Dùng Poisson cho quá trình bất thuận nghịch (nén đột ngột, giãn chống áp suất cố định).
3. **(T08)** Viết `Q = νC_VΔT` cho quá trình không đẳng tích.
4. **(T08/T09)** "Công = diện tích" cho cạnh bất thuận nghịch.
5. **(T09)** Bỏ sót điểm `dQ = 0` trên đoạn thẳng, tính sai `Q_vào`.
6. **(T09)** Tính `η = W/Q_net` thay vì `W/Q_vào`.
7. **(T09)** Nhầm chiều chu trình (động cơ ⇄ máy lạnh).
8. **(T10)** Quên nguồn nhiệt khi tính `ΔS_tot`.
9. **(T10)** Dùng `ΔS = Q/T` cho quá trình bất thuận nghịch của chính vật.
10. **(T10)** Cho `η > 1 − T_c/T_h` mà không nhận ra sai.
11. **(T06)** Nhiệt độ `°C` thay vì `K`.
12. **(T06)** Quên `p₀` khí quyển khi tính `p` từ cân bằng pittông.
13. **(T06)** Nhầm số mol khi hở van; quên bảo toàn `ν` tổng.
14. **(T05)** Nhầm `v̄`, `v_rms`, `v_p`; nhầm `m` (phân tử) với `μ` (mol).
15. **(T07)** Coi `ρ` khí không đổi theo độ cao.
16. **(T07)** Nhầm khí quyển đẳng nhiệt và đoạn nhiệt.
17. **(T11)** Quên một nửa hạt hướng về tường.
18. **(T16)** Nhầm trung bình theo dòng (`2kT`) với theo số hạt (`3kT/2`).
19. **(T16)** Dùng `p₁ = p₂` khi `Kn ≫ 1` (đúng là `p₁/√T₁ = p₂/√T₂`).
20. **(T16)** Dùng Bernoulli khi lỗ nhỏ hơn quãng đường tự do.
21. **(T12)** Áp Boyle cho hơi bão hoà bị nén.
22. **(T12)** Áp `p ∝ T` cho hơi bão hoà còn lỏng khi nung nóng bình cứng.
23. **(T12)** Quên `p_khô` khi tính áp suất tổng.
24. **(T04)** Giả sử "đá tan hết" mà không so ngưỡng.
25. **(T01/T17)** Dùng `L` như `ΔU`; trộn `L` theo mol với `Δv` theo kg.
26. **(T13)** Cộng `R` sai cấu hình; nhầm `q` (W/m²) với `P` (W).
27. **(T13)** Dùng gộp (lumped) khi `Bi` không nhỏ.
28. **(T14)** Lẫn `V` và `v`; dấu sai của số hạng `a` trong `U`.
29. **(T15)** Quên hai mặt của màng xà phòng; sai chiều góc tiếp xúc.
30. **(T15)** Coi mao dẫn bảo toàn năng lượng cơ học (thực tế mất một nửa).

---

# §8. HẠN CHẾ, TRỰC GIÁC CÒN SÓT, KẾ HOẠCH KIỂM CHỨNG

## 8.1. Ba chỗ trực giác vẫn còn (nói thẳng)

1. **Chọn mô hình/hệ (P1, P2, P3).** Quyết định cái nào quasi-static, cái nào đẳng nhiệt, hệ nào kín: khung này *hướng dẫn* bằng từ điển §2.2 và bảng thang thời gian, nhưng vẫn là quyết định.
2. **Vùng xám Pre-đúng/Suf-chưa.** Khi Pre thoả mà Suf chưa (§1.2), phải phán đoán và ghi Err. Đây chính là nơi **giảm** chứ **không xoá** được trực giác.
3. **Phát hiện CHỖ chưa liệt kê.** Kho CHỖ (§1.3) hữu hạn *sau khi bạn chốt nó*; việc quên một hệ con/ràng buộc ẩn vẫn có thể xảy ra. Danh sách §1.6 và chẩn đoán §1.5 giảm rủi ro này nhưng không loại trừ.

## 8.2. Khung có thể thất bại ở đâu?

- Bài cần **mô hình mới** chưa có trong thư viện (ví dụ vật lí thống kê chính tắc, thăng giáng, bức xạ vật đen chi tiết): cần thêm công cụ T18+. Ghi nhận và bổ sung (mẫu ở §8.4).
- Bài mà **mẹo** (đối xứng, đổi biến khéo, tương tự điện) mới là chìa khoá: khung có thể không nhắc tới mẹo; nên ghi mẹo đã gặp vào thư viện như công cụ.
- Bài có nhiều hiệu ứng có **độ lớn cùng cỡ**: việc chọn hiệu ứng nào bỏ qua (Err) đòi ước lượng cẩn thận (P12).
- **Đọc sai đề** (chữ "cân bằng", "chậm") làm sai từ B1; từ điển §2.2 giúp, không thay thế việc đọc kỹ.

## 8.3. Nhận xét về giả thuyết "mỗi bài chỉ có hữu hạn cách giải hợp lý"

Với mức *lời giải khác nhau về công cụ* (năng lượng vs lực; chu trình vs entropy), điều này gần như đúng và tôi thấy khung này khớp. Ở mức *lựa chọn mô hình* (chia hệ con thế nào, gộp/không gộp), số lựa chọn về nguyên tắc không hữu hạn tuyệt đối, nhưng **hữu hạn theo tương đương** (các cách chia cho cùng phương trình sau khi khử biến). Tôi *chưa có chứng minh*; đây là giả thuyết cần kiểm bằng dữ liệu (§8.4). **[ĐỀ XUẤT]**

## 8.4. Kế hoạch kiểm chứng (để không tự huyễn hoặc) **[ĐỀ XUẤT]**

1. Chọn tập ~30 bài Nhiệt thật (HSGQG, IPhO, giáo trình Olympic) *chưa dùng để xây thư viện này*.
2. Với mỗi bài, **trước khi xem lời giải chính thức**, chạy SCAN, điền phiếu Phụ lục E, ghi: công cụ dùng, số CHỖ liệt kê, số phương trình thu, số phương trình *có ích*.
3. So với lời giải chính thức, đo:
   - **Recall**: CHỖ của lời giải chính thức có nằm trong danh sách SCAN không?
   - **Precision**: bao nhiêu phương trình thu được là thừa/vô nghĩa?
   - **Sai Pre/Suf**: công cụ nào bị nhận nhầm/bỏ nhầm?
4. Thêm vào thư viện: công cụ mới (T18+), bổ sung Pre/Suf, thêm lỗi vào §7.2.
5. **Bài kiểm tra "âm"**: chọn bài mà công cụ ngây thơ (ví dụ Poisson) *không* dùng được, xem Suf-detector có chặn đúng không.
6. **Ghi thời gian**: khung này có khả thi trong điều kiện phòng thi không? (SCAN đầy đủ cho toàn bài có thể quá lâu; cần bản rút gọn chỉ duyệt công cụ khớp §7.1.)

## 8.5. Việc còn thiếu (đề nghị bạn xác nhận)

- Cách hiểu **"khí kém"** và **"vi phân dải khí"** (§0.2).
- Hàng còn lại bị cắt của bảng syllabus (§0.2).
- Bạn có muốn tôi tách phiếu SCAN thành bản rút gọn cho phòng thi không.

---

# PHỤ LỤC

## A. Tích phân Gauss/Gamma và trung bình Maxwell (đã kiểm)

`∫₀^∞ x^n e^{−ax²} dx = Γ((n+1)/2) / (2·a^{(n+1)/2})`

| n | 0 | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|---|
| kết quả | `½√(π/a)` | `1/(2a)` | `¼√(π/a³)` | `1/(2a²)` | `(3/8)√(π/a⁵)` | `1/a³` |

Moment Maxwell: `⟨v^k⟩ = (2kT/m)^{k/2}·(2/√π)·Γ((k+3)/2)`. Suy ra:
`⟨v⟩ = √(8kT/πm)`, `⟨v²⟩ = 3kT/m`, `⟨1/v⟩ = √(2m/(πkT))`, `⟨v_x²⟩ = kT/m`.
Trọng số theo **dòng** (`∝ v_n f`): năng lượng tịnh tiến trung bình `= 2kT`.
Bán cầu: `∫cosθ dΩ = π`, `∫cos²θ dΩ = 2π/3`.

## B. Trị số cỡ (kiểm lại theo đề; có thể lệch tuỳ nguồn) **[CẦN KIỂM]**

| Đại lượng | Giá trị cỡ |
|---|---|
| `R` | 8,314 J/(mol·K) |
| `k` | 1,381·10⁻²³ J/K |
| `N_A` | 6,022·10²³ mol⁻¹ |
| 1 atm | 1,013·10⁵ Pa |
| `c_nước` | 4186 J/(kg·K) |
| `c_đá`, `c_hơi` | ~2100, ~2000 J/(kg·K) |
| `λ_đá` | 3,34·10⁵ J/kg |
| `L_nước` (100 °C) | 2,26·10⁶ J/kg |
| `σ_nước` (20 °C) | ≈ 0,072 N/m |
| `μ_không khí` | ≈ 0,029 kg/mol; `γ ≈ 1,4` |
| `κ`: không khí / nước / thuỷ tinh / đồng | ≈ 0,026 / 0,6 / ~1 / ~400 W/(m·K) |
| `ρ_đá` | ~917 kg/m³ |
| Điểm ba nước | 273,16 K; ≈ 611 Pa |
| CO₂ (vdW) | `a ≈ 0,364 Pa·m⁶/mol²`, `b ≈ 4,27·10⁻⁵ m³/mol` ⇒ `T_c ≈ 304 K` (kiểm công thức) |

## C. Ánh xạ syllabus ↔ mã công cụ

| Hàng syllabus | Mã |
|---|---|
| Cấu trúc của chất: lỏng, rắn, khí; sự chuyển thể | T01 |
| Nội năng + định luật 1 nhiệt động lực học | T02 |
| Nhiệt độ; thang đo nhiệt độ | T03 |
| Nhiệt dung riêng, nhiệt nóng chảy riêng, nhiệt hoá hơi riêng | T04 |
| Thuyết động học phân tử chất khí cơ bản | T05 |
| Các định luật về khí lí tưởng; phương trình C–M | T06 |
| Bài toán xét vi phân dải khí | T07 |
| Cơ sở NĐLH, nguyên lí 1 chất khí; bài tập nâng cao về nguyên lí 1 | T08 |
| Bài toán tính công, nhiệt dung, hiệu suất chu trình | T09 |
| Nguyên lí 2 NĐLH: máy lạnh, động cơ nhiệt, hiệu suất cực đại,… | T10 |
| Áp suất chất khí, động năng phân tử, phương trình cơ bản | T11 |
| Sự chuyển pha, không khí ẩm | T12 |
| Dẫn nhiệt | T13 |
| Khí thực | T14 |
| Sức căng bề mặt | T15 |
| Động học phân tử chất khí nâng cao, khí kém | T16 |
| Phương trình Clapeyron–Clausius | T17 |

## D. Tài liệu (để đối chiếu các mục [CHUẨN]) **[CẦN KIỂM chi tiết chương/trang]**

- H. B. Callen, *Thermodynamics and an Introduction to Thermostatistics* (nền tảng nguyên lí 1, 2, entropy, phase equilibria).
- C. Kittel & H. Kroemer, *Thermal Physics*; S. J. Blundell & K. M. Blundell, *Concepts in Thermal Physics* (mức đại học, có bài tập).
- F. Reif, *Fundamentals of Statistical and Thermal Physics* (động học phân tử, vận chuyển).
- Д. В. Сивухин (D. V. Sivukhin), *Общий курс физики*, tập 2: *Термодинамика и молекулярная физика* (rất hợp Olympic).
- I. E. Irodov, *Problems in General Physics* (phần nhiệt học/vật lí phân tử: bộ bài tập luyện).
- R. Feynman, *Lectures on Physics*, vol. I (động học phân tử, nhiệt động lực học).
- Toán (V3): M. L. Boas, *Mathematical Methods in the Physical Sciences*; J. Stewart, *Calculus* (bạn đã nêu).

## E. PHIẾU QUÉT CHỖ (mẫu điền cho mỗi bài)

**E.1. Mô hình**

```
Bài: ________     Q (cái cần tìm): ________ (loại: số / biểu thức / cực trị / "khi nào" / "có thể không")
O: hệ con = [ ... ]   vách = [cách nhiệt? di động? lỗ?]   nguồn = [ ... ]
V: biến độc lập đã chọn = ____
I: từ điển (§2.2): "chậm"→____, "cách nhiệt"→____, "cân bằng"→[cơ/nhiệt/pha]
Err budget (P12): nd³=__  Kn=__  Bo=__  Bi=__  St=__  Ma=__
```

**E.2. Bảng trạng thái (T06)**

| Hệ con | Trạng thái | p | V | T | ν | Ràng buộc dẫn tới |
|---|---|---|---|---|---|---|
| | | | | | | |

**E.3. Kho CHỖ (đánh dấu ✓ khi đã liệt kê)**

```
χ1 hệ: ____   χ2 trạng thái: ____   χ3 quá trình/đoạn: ____   χ4 giao diện: ____
χ5 thời điểm/khoảng: ____   χ6 phần tử vi phân: ____   χ7 chu trình: ____
χ8 điểm gãy / tới hạn / dQ=0 / Tmax: ____   χ9 sự kiện vi mô: ____
χ10 sổ cái: [số hạt] [năng lượng] [lực] [entropy]
```

**E.4. Bảng SCAN (mỗi CHỖ một dòng)**

| # | Công cụ | CHỖ (loại + tên) | Pre? | Suf? | Phương trình | Ẩn mới | Ghi chú Err |
|---|---|---|---|---|---|---|---|
| 1 | | | | | | | |

**E.5. Kiểm tra đóng kín & chẩn đoán**

```
Số ẩn cần để xác định Q: ___    Số phương trình độc lập thu được: ___
Thiếu?  → D1..D6 (§1.5)   → §1.6 ràng buộc ẩn   → chia nhỏ CHỖ?
Nhánh (case) cần xét: ____
```

**E.6. Bài Toán xuất ra (kết thúc V2)**

```
Ẩn: ____   Hệ ràng buộc: ____   Miền/điều kiện: ____   Dạng Toán (§4.1): ____   → chuyển V3
```

---

*Hết. Nếu bạn muốn, phần tiếp theo có thể là: bản rút gọn phiếu SCAN cho phòng thi; các công cụ T18+ (thống kê chính tắc, thăng giáng, bức xạ) nếu ảnh syllabus còn hàng khác; hoặc chạy quy trình kiểm chứng §8.4 trên một số bài thật cùng bạn.*
