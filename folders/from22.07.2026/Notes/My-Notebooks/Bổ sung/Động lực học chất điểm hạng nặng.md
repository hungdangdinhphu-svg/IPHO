# ĐỘNG LỰC HỌC CỦA CƠ HỌC CHẤT ĐIỂM
### Cấu trúc giữa Vật Lý và Toán Học — Vấn đề 1 (Vật Lý → Toán) & Vấn đề 2 (Cấu trúc Toán + Bài toán Tìm kiếm)

Phạm vi (theo ảnh mục **b. Động lực học**):
1. Các định luật Newton
2. Các lực cơ học
3. Ứng dụng định luật Newton và các lực cơ học vào bài tập
4. Chuyển động trong hệ quy chiếu phi quán tính

Mục tiêu kép: (i) hiểu như một nhà vật lý (biết điều kiện áp dụng, biết khi nào một "định luật" thực ra là một mô hình), (ii) đủ công cụ, đủ quy trình để xử lý đề HSGQG Vật Lý và đề kiểu IPHO ở phần này.

---

## 0. ĐỌC TRƯỚC: độ tin cậy, phạm vi, và tự kiểm điểm

### 0.1. Nhãn độ tin cậy dùng trong tài liệu

| Nhãn | Ý nghĩa |
|---|---|
| **[A]** | Kết quả/định nghĩa chuẩn của Vật Lý–Toán, có trong giáo trình chuẩn. |
| **[B]** | Kết quả định lượng do tôi **đã kiểm chứng lại bằng tính toán** (sympy / tích phân số) trong lúc soạn tài liệu này: bài ròng rọc động, nêm chuyển động, cản bậc hai (độ cao cực đại, tanh), lệch Coriolis khi rơi tự do, hạt trong ống quay, rời mặt cầu ở cosθ = 2/3, dây xích rơi N = 3λgx, ma sát khô trong dao động lò xo, nghiệm KKT của con lắc. |
| **[C]** | **Khung/heuristic do tôi đề xuất** để trả lời "Vấn đề tìm kiếm" (thư viện toán tử, độ thiếu δ, quy trình…). Đây là *giả thuyết làm việc chưa được kiểm định trên tập đề thi thật*. Cần bạn thử, sửa, và phản biện. |

### 0.2. Những điều tôi KHÔNG làm (để tránh "lừa dối" giả vờ đầy đủ)
- Không nêu số hiệu/năm của đề HSGQG hay IPHO cụ thể, vì tôi không thể xác minh chính xác nội dung từng đề. Thay vào đó tôi mô tả **dạng cấu trúc** thường gặp.
- Không khẳng định "mọi bài IPHO đều rơi vào bảng dưới đây". Điều tôi khẳng định được chỉ là: với Động lực học chất điểm, **tập các toán tử cơ bản là hữu hạn và nhỏ** (mục 6.2), còn phần "sáng tạo" thực sự nằm ở *chọn mô hình*, *chọn hệ quy chiếu / hệ tọa độ*, và *chọn chỗ cắt hệ*.
- Không khẳng định quy định chính xác về việc được dùng Lagrange/KKT trong phòng thi. Hãy kiểm tra thể lệ; tôi chỉ nói về **giá trị toán học** của chúng (mục 6.7).
- Nhiều đề HSGQG chạm sang phần khác (bảo toàn, dao động, vật rắn, hấp dẫn). Tôi chỉ dùng các phần đó như *công cụ hỗ trợ* khi cần, không triển khai đầy đủ.

### 0.3. Nhận xét thẳng về khung ý tưởng trong file gốc (để bạn cải thiện)
Bạn đã dặn "có sai sót và lỗi nghiêm trọng". Đây là những điểm tôi thấy nên chỉnh, nói thẳng:

1. **"Luôn luôn cùng một cấu trúc Toán"** là mệnh đề quá mạnh nếu hiểu theo nghĩa toán học nghiêm ngặt. Thực tế một dạng bài Vật lý thường có **vài cấu trúc Toán tương đương** (ví dụ giải bằng Newton–ODE hoặc bằng năng lượng hoặc bằng Lagrange). Nên đổi thành: *"thường có một (hoặc rất ít) cấu trúc Toán tự nhiên nhất, và các biến tấu thường giữ nguyên nó"*. Phần lõi của ý bạn vẫn đúng và có giá trị.
2. **"Pre(ℓ) được thỏa"** là điều kiện *cần* để bước ℓ **hợp lệ**. Nó **không** đảm bảo bước đó **hữu ích**. Bạn cần thêm một tiêu chí thứ hai cho "bước tiến có ý nghĩa". Tôi đề xuất tiêu chí **độ thiếu δ** ở mục 6.4 (đếm ẩn − đếm phương trình độc lập). Đây chính là chỗ điều kiện cần/đủ của bạn nối sang được Vấn đề 2: *Pre = điều kiện cần cho tính đúng; δ = 0 và định thức ≠ 0 = điều kiện đủ cho tính giải được.*
3. **Ký hiệu `C ∪ L ⊢ Q`** dùng dấu suy dẫn logic. Trong Vật lý cụ thể, nó nên đọc là "hệ phương trình (C ∪ L) đủ xác định Q". Các chữ cái trong bộ sáu `M = (O, V, L, C, Q, I)` chưa được định nghĩa trong file; ở dưới tôi **giả định** nghĩa như sau (nếu bạn định nghĩa khác, hãy sửa):
   - **O**: đối tượng (chất điểm, dây, ròng rọc, mặt phẳng, lò xo, môi trường)
   - **V**: biến (tọa độ, vận tốc, gia tốc, các lực chưa biết, thời gian)
   - **L**: luật/công cụ (Newton II, Newton III, Hooke, Coulomb…)
   - **C**: ràng buộc và điều kiện đặc biệt (dây không dãn, tiếp xúc, N = 0 khi rời mặt…)
   - **Q**: câu hỏi (đại lượng cần tìm)
   - **I**: dữ kiện và điều kiện đầu
4. **"Tập A hữu hạn và nhỏ, dễ tìm cho mọi bài IPHO"** là hy vọng hợp lý nhưng chưa là định lý. Bài toán *tìm* A là bài toán tìm dạng của các toán tử; với Động lực học chất điểm tôi làm được (mục 6.3). Với toàn bộ IPHO thì chưa ai làm trọn, và tôi cũng không giả vờ là đã làm.
5. Bạn viết rằng bạn "đuối khủng khiếp, gồng não rất căng". Đó là dấu hiệu tải nhận thức cao. Tài liệu này cố ý được viết theo kiểu **tra cứu + quy trình** để bạn không phải nhớ hết: cần gì tra đó.

---

## 1. KHUNG HÌNH THỨC CHO ĐỘNG LỰC HỌC CHẤT ĐIỂM

### 1.1. Phát biểu cấu trúc trung tâm [A]/[C]

> **Động lực học chất điểm = hệ phương trình vi phân bậc hai (Newton II) + hệ ràng buộc (hình học/tiếp xúc/dây) + điều kiện đặc biệt (bất đẳng thức, chuyển chế độ) + điều kiện đầu.**

Về mặt Toán, đó là một **DAE** (hệ vi phân–đại số) khi có ràng buộc, và là **ODE** khi chất điểm chuyển động tự do trong trường lực đã biết.

Sơ đồ:

```
Bài Vật lý ──(Vấn đề 1: mô hình hóa)──▶ M = (O, V, L, C, Q, I)
                                              │
                          (Vấn đề 2: nhận diện cấu trúc + chọn toán tử)
                                              ▼
       Hệ đại số  |  ODE giải được  |  ODE + nhánh chế độ  |  DAE (ràng buộc)
                                              │
                                              ▼
                              Nghiệm ──▶ kiểm tra (thứ nguyên, giới hạn, dấu)
```

### 1.2. Nguyên lý đếm cân bằng (nền của mọi bài có ràng buộc) [A]/[C]

Xét hệ gồm **N chất điểm** chuyển động trong không gian d chiều (d = 1, 2, 3), với **k ràng buộc** độc lập.
- Số biến chuyển động (gia tốc): **N·d**.
- Nếu mỗi ràng buộc được "thực thi" bởi một lực liên kết ẩn (N, T, lực nghỉ) thì có thêm **k** ẩn.
- Số phương trình: **N·d** (Newton II theo từng thành phần) **+ k** (ràng buộc viết ở dạng gia tốc).
- Tổng ẩn = N·d + k = tổng phương trình. **Hệ tự cân bằng khi mô hình hóa đúng.**

Hệ quả thực chiến:
- **Nếu bạn đếm ra thừa/thiếu ẩn ⇒ mô hình sai** (thiếu một ràng buộc, quên một lực liên kết, hoặc đếm hai lần một lực).
- **Mỗi lực liên kết ẩn độc lập tương ứng với đúng một ràng buộc.** Đây là "kiểm tra sức khỏe" nhanh nhất của một bài động lực học.
- Bậc tự do: **f = N·d − k**. Số phương trình chuyển động độc lập (sau khi khử lực liên kết) = f.

### 1.3. Hai loại lực (phân loại cấu trúc quan trọng nhất) [C]

| Loại | Đặc điểm Toán | Ví dụ | Vai trò trong hệ phương trình |
|---|---|---|---|
| **Lực cấu thành** (constitutive) | Cho dưới dạng **hàm đã biết** của vị trí/vận tốc/thời gian | mg, −kx, −bv, Lorentz, hấp dẫn, μN khi biết N | Vế phải của Newton II, không tạo ẩn mới (trừ khi phụ thuộc N) |
| **Lực liên kết** (constraint) | **Ẩn**, độ lớn do ràng buộc quyết định | N, T, ma sát nghỉ | Mỗi cái là 1 ẩn, đi cùng 1 ràng buộc (mục 1.2) |

Ma sát trượt f = μN là **lực nửa liên kết**: hướng biết (ngược chiều vận tốc tương đối), độ lớn liên hệ với ẩn N.

---

## 2. CÁC ĐỊNH LUẬT NEWTON (mục 1 trong ảnh)

### 2.1. Định luật I [A]
- **Nội dung**: tồn tại các hệ quy chiếu (HQC) — gọi là **HQC quán tính** — trong đó chất điểm không chịu tác dụng lực (hoặc hợp lực bằng 0) thì đứng yên hoặc chuyển động thẳng đều.
- **Ý nghĩa sâu**: Newton I **không** phải trường hợp riêng của Newton II. Nó *định nghĩa* lớp HQC mà Newton II có dạng đơn giản. Bạn chọn HQC trước, rồi mới có "định luật".
- **Toán**: `ΣF = 0 ⇒ a = 0`, nhưng ý quan trọng là mệnh đề tồn tại HQC.
- **Thực chiến**: HQC gắn với mặt đất thường được coi là quán tính (bỏ qua quay của Trái Đất). Khi đề cho **vật/nêm/xe có gia tốc** và bạn muốn đứng trên đó thì phải dùng phần 4 (HQC phi quán tính).

### 2.2. Định luật II [A]

Dạng tổng quát (đúng trong HQC quán tính, cho **chất điểm**):
```
dp/dt = F,        p = m v
```
Với **khối lượng không đổi**:
```
m a = ΣF          (vectơ)          ⇒  m d²r/dt² = F(r, v, t)
```
- **Cấu trúc Toán**: ODE **bậc hai** trong r. Lực chỉ quyết định **gia tốc**, không quyết định vận tốc. Vì vậy cần **hai** điều kiện đầu (r(0), v(0)). Đây là chỗ sinh ra "quỹ đạo phụ thuộc điều kiện đầu".
- **Tính xác định (determinism)**: nếu F đủ trơn (Lipschitz theo r, v) thì nghiệm tồn tại và **duy nhất** (định lý Picard–Lindelöf). Cảnh báo: bài có ma sát khô/ràng buộc "một phía" (N ≥ 0, T ≥ 0) là **hệ không trơn** — có thể có nhiều chế độ và thậm chí (ở vật rắn có ma sát) có nghịch lý không tồn tại/không duy nhất nghiệm (kiểu nghịch lý Painlevé). Với chất điểm bình thường ta không gặp, nhưng điều này giải thích vì sao các bài ma sát cần **phân nhánh chế độ** (mục 6.5).
- **Chiếu lên trục**: `m a_x = ΣF_x`, `m a_y = ΣF_y`. Chọn trục sao cho ẩn cần loại nằm vuông góc trục là kỹ thuật cơ bản nhất (toán tử ℓ₂ ở mục 6.3).
- **Tọa độ tự nhiên** (quỹ đạo có bán kính cong ρ): `m dv/dt = ΣF_τ`, `m v²/ρ = ΣF_n` (F_n hướng vào tâm cong).
- **Tọa độ cực** (r, θ): `a_r = r̈ − r θ̇²`, `a_θ = r θ̈ + 2 ṙ θ̇`.

#### 2.2.1. Khối lượng biến thiên — bẫy kinh điển [A]
Nhiều tài liệu viết `F = d(mv)/dt` rồi áp dụng bừa. **Sai** khi khối lượng đổi mà phần khối lượng thêm vào/bớt đi có vận tốc khác vật. Dạng đúng, trong HQC quán tính:
```
m dv/dt = F + u_rel · dm/dt
```
trong đó `u_rel` = vận tốc của phần khối lượng được **thêm vào/tách ra so với vật chính** (ngay trước/sau khi nhập/tách).
- Tên lửa: khí thải có `u_rel = −u_e` (ngược chiều bay), `dm/dt < 0` ⇒ lực đẩy `= u_e |dm/dt| > 0`. Phương trình Tsiolkovsky (bỏ ngoại lực): `Δv = u_e ln(m₀/m)`.
- Nếu phần khối lượng thêm vào **đứng yên** trong HQC (giọt mưa rơi vào toa) thì `u = 0` và `u_rel = −v`, ta lại *ngẫu nhiên* nhận được `F = d(mv)/dt`. **Chỉ đúng trong trường hợp này.**
- Cách an toàn: luôn viết **định lý xung lượng cho hệ kín gồm vật + phần khối lượng liên quan** trong khoảng dt, không dựa vào công thức nhớ.

### 2.3. Định luật III [A]
- **Nội dung**: nếu A tác dụng lên B lực **F_AB** thì B tác dụng lên A lực **F_BA = −F_AB**. Hai lực **cùng bản chất, cùng phương, ngược chiều, cùng độ lớn, đặt lên hai vật khác nhau** ⇒ không bao giờ triệt tiêu nhau *trong cùng một phương trình chuyển động của một vật*.
- **Dạng yếu** (bằng nhau ngược chiều) và **dạng mạnh** (thêm điều kiện nằm dọc đường nối). Định lý xung lượng dùng dạng yếu; bảo toàn mômen động lượng của hệ cần dạng mạnh.
- **Giới hạn**: tương tác điện từ giữa các điện tích chuyển động, và tương tác có độ trễ, không tuân theo Newton III "chỉ tính hạt" (trường mang xung lượng). Trong bài cơ học thường bỏ qua.
- **Lực quán tính không có phản lực** (không phải tương tác giữa hai vật) — nếu bạn tìm phản lực của lực quán tính là bạn đang sai (mục 8.1).
- **Vai trò cấu trúc**: Newton III là công cụ "cho không" các phương trình liên kết giữa hai vật tiếp xúc: `N_AB = N_BA`, `T` ở hai đầu một dây nhẹ là như nhau.

### 2.4. Nguyên lý độc lập tác dụng / chồng chất lực [A]
Hợp lực = tổng vectơ các lực; gia tốc gây ra bởi từng lực cộng vectơ. Toán: **F là tuyến tính trong các lực thành phần** ⇒ ta được quyền phân tích một lực thành các thành phần.

### 2.5. Hệ quả cho hệ chất điểm [A]
Cộng Newton II của các vật và dùng Newton III (dạng yếu):
```
d P/dt = Σ F_ngoại,     P = Σ m_i v_i = M v_cm
M a_cm = Σ F_ngoại
```
- **Lực nội bị khử.** Dùng khi chỉ cần chuyển động *tổng thể* và không cần lực tương tác bên trong.
- **HQC khối tâm**: gắn HQC vào khối tâm (tịnh tiến với gia tốc a_cm so với HQC quán tính). Trong đó tổng xung lượng luôn bằng 0. Nếu a_cm ≠ 0 thì mỗi vật chịu thêm lực quán tính `−m_i a_cm`, và tổng các lực quán tính này bằng `−M a_cm = −ΣF_ngoại`, triệt tiêu tổng lực ngoài; vì vậy khối tâm đứng yên trong HQC đó (xem mục 4.9a).

### 2.6. Bất biến Galilê và thứ nguyên [A]
- Phương trình `m a = F` giữ nguyên dạng dưới biến đổi Galilê `r' = r − V t` (V hằng) ⇒ mọi HQC chuyển động thẳng đều so với một HQC quán tính cũng là quán tính.
- Thứ nguyên: `[F] = M L T⁻²`. Mọi đáp số cuối cùng **phải** qua kiểm tra thứ nguyên (mục 8.2).

---

## 3. CÁC LỰC CƠ HỌC (mục 2 trong ảnh)

Với mỗi lực: công thức, **điều kiện áp dụng (Pre)**, **cấu trúc Toán** (cấu thành hay liên kết), và **bẫy**.

### 3.1. Trọng lực và hấp dẫn [A]
- Hấp dẫn: `F = G m₁ m₂ / r²`. Trọng lực gần mặt đất: `P = m g`.
- Ở độ cao h: `g(h) = G M /(R+h)²`; nếu `h ≪ R`: `g(h) ≈ g₀ (1 − 2h/R)`. **Pre của g = const: h ≪ R** (và vùng chuyển động nhỏ).
- **Trọng lượng biểu kiến** (đọc trên cân) khác trọng lực khi HQC có gia tốc: mục 4.9.
- **Cấu thành.**

### 3.2. Lực đàn hồi (Hooke) [A]
- `F = −k (l − l₀)`. **Pre**: biến dạng nhỏ, lò xo nhẹ (khối lượng ≈ 0, nên lực như nhau ở mọi tiết diện).
- Ghép **song song**: `k = k₁ + k₂` (cùng độ dãn). Ghép **nối tiếp**: `1/k = 1/k₁ + 1/k₂` (cùng lực).
- Cắt lò xo: `k · l = const` (lò xo dài gấp đôi thì mềm gấp đôi ⇒ nửa lò xo có độ cứng 2k).
- **Bẫy**: dùng độ dãn Δl tính từ **chiều dài tự nhiên**, không phải từ vị trí cân bằng, trừ khi bạn đã hấp thụ trọng lực vào vị trí cân bằng (khi đó dao động quanh vị trí cân bằng mới vẫn là `−kx`).
- **Cấu thành.**

### 3.3. Lực căng dây [A]
- **Liên kết**, luôn hướng dọc dây, **T ≥ 0** (dây không đẩy). Nếu giải ra T < 0 ⇒ dây chùng ⇒ giả thiết "dây căng" sai ⇒ đổi chế độ (T = 0).
- **Dây nhẹ + không ma sát trên ròng rọc nhẹ ⇒ T như nhau ở mọi điểm dọc dây.** Mỗi điều kiện "nhẹ", "không ma sát" là một **Pre** của kết luận này. Nếu ròng rọc **có khối lượng** (quay được) thì hai nhánh dây có T khác nhau (cần mômen — ngoài chất điểm).
- Dây **có khối lượng** (mật độ dài λ): T **biến thiên dọc dây**. Mỗi đoạn ds có khối lượng λ ds, nên hiệu lực căng hai đầu đoạn (khi không có lực ngoài dọc dây) bằng `λ ds · a` (a là gia tốc của đoạn đó dọc dây). Tức nhánh phía sau chịu lực căng khác nhánh phía trước.
- Dây quấn ma sát trên trụ cố định, góc ôm φ, hệ số ma sát μ, dây sắp trượt: **`T_lớn = T_nhỏ · e^{μφ}`** (công thức Euler–Eytelwein). **Pre**: dây nhẹ, sắp trượt hoặc đang trượt đều.
- **Ẩn/ràng buộc**: mỗi dây không dãn tạo **1 ẩn T** và **1 ràng buộc** độ dài (mục 4.2).

### 3.4. Phản lực pháp tuyến [A]
- **Liên kết**, vuông góc mặt tiếp xúc (mặt nhẵn hay có ma sát, thành phần pháp tuyến), **N ≥ 0** (mặt không kéo). `N = 0` ⇔ **sắp rời mặt**. Đây là mẫu "điều kiện đặc biệt" phổ biến nhất trong đề.
- **N không phải lúc nào cũng bằng mg cos α.** Chỉ bằng khi vật không có gia tốc vuông góc mặt. Ví dụ: vật trên nêm chuyển động, vật trong thang máy, vật trên mặt cong: N do ràng buộc quyết định.

### 3.5. Ma sát (Coulomb) [A]
| Chế độ | Định luật | Cấu trúc |
|---|---|---|
| Nghỉ (v_rel = 0) | `0 ≤ f ≤ μ_s N`, **f do ràng buộc quyết định** | ẩn (liên kết) + bất đẳng thức |
| Trượt (v_rel ≠ 0) | `f = μ_k N`, hướng **ngược vận tốc tương đối** | cấu thành theo N |

- **Bẫy #1**: `f = μN` **chỉ đúng khi trượt hoặc sắp trượt**. Ở trạng thái nghỉ, f được tính từ cân bằng lực.
- **Bẫy #2**: hướng ma sát là hướng ngược với vận tốc **tương đối giữa hai bề mặt**, không phải ngược vận tốc đối với đất.
- **Góc ma sát**: `tan φ_s = μ_s`. Vật nằm yên trên dốc góc α khi `tan α ≤ μ_s` (không phụ thuộc khối lượng).
- **Kéo vật trên sàn ngang bằng lực F hợp góc β so với ngang (vận tốc đều)**: `F = μ m g /(cos β + μ sin β)`; F nhỏ nhất khi **tan β = μ**, `F_min = μ m g / √(1 + μ²)`. (Đạt cực đại của `cosβ + μ sinβ = √(1+μ²)`.)
- **Ma sát lăn** thuộc vật rắn (nằm ngoài chất điểm).

### 3.6. Lực cản của môi trường [A]
- **Tuyến tính** (Stokes, số Reynolds nhỏ): `F = −b v`. Thời gian đặc trưng `τ = m/b`, vận tốc giới hạn `v_T = m g / b`.
- **Bậc hai** (tốc độ lớn): `F = −k₂ v |v|` (tức `−½ C_d ρ S v²` theo hướng ngược v). Vận tốc giới hạn `v_T = √(m g / k₂)`.
- **Cấu thành phụ thuộc vận tốc** ⇒ ODE có thể **tách biến** (mục 4.5).

### 3.7. Lực Archimedes và thủy tĩnh [A]
`F_A = ρ_lỏng V_chìm g`, hướng lên, đặt tại tâm khối lượng của phần chất lỏng bị chiếm. Với chất điểm: chỉ cần độ lớn. **Pre**: chất lỏng tĩnh (nếu chất lỏng có gia tốc, thay g bằng g_hiệu dụng).

### 3.8. Lực Lorentz [A]
`F = q (E + v × B)`. **Lực từ vuông góc v ⇒ không sinh công.** Trong B đều, vận tốc vuông góc B: chuyển động tròn `r = m v /(|q| B)`, tần số góc `ω = |q| B / m` (không phụ thuộc v).

### 3.9. "Lực hướng tâm" không phải một loại lực [A]
Chỉ là **tên gọi cho thành phần pháp tuyến của hợp lực** khi vật chuyển động cong: `Σ F_n = m v²/ρ`. Đừng bao giờ vẽ nó thêm vào hình lực bên cạnh các lực thật (N, T, mg…). Đây là lỗi phổ biến nhất của học sinh khi bắt đầu.

### 3.10. Lực quán tính (phi quán tính) [A]
Chỉ xuất hiện khi làm việc trong HQC phi quán tính; **không có phản lực**, không thuộc Newton III. Chi tiết ở mục 4.9.

### 3.11. Bảng tổng hợp lực theo cấu trúc [C]
| Lực | Loại | Ẩn? | Có bất đẳng thức? | Điều kiện đặc biệt điển hình |
|---|---|---|---|---|
| mg, hấp dẫn, Hooke, cản, Archimedes | cấu thành | không | không | — |
| N | liên kết | có | N ≥ 0 | N = 0: rời mặt |
| T | liên kết | có | T ≥ 0 | T = 0: dây chùng |
| f nghỉ | liên kết | có | \|f\| ≤ μ_s N | \|f\| = μ_s N: sắp trượt |
| f trượt | nửa liên kết | qua N | hướng theo v_rel | đổi dấu v_rel: đổi chế độ |

---

## 4. CẤU TRÚC TOÁN CỦA CÁC DẠNG BÀI (mục 3 trong ảnh, và phần lõi Vấn đề 2)

Mỗi mục dưới đây có: **dạng Toán**, **dấu hiệu nhận diện trong đề**, **công cụ**, **kết quả chuẩn**, **Pre / bẫy**. Đây là "thư viện cấu trúc" S1…S9 [C: cách phân loại là của tôi; bản thân kết quả là A].

### 4.1. S1 — Cân bằng chất điểm (hệ đại số tuyến tính)
- **Dạng Toán**: `ΣF = 0`, tức hệ 2 hoặc 3 phương trình tuyến tính trong các ẩn lực.
- **Dấu hiệu**: "cân bằng", "đứng yên", "vừa đủ", "vừa sắp".
- **Công cụ**: (i) chiếu hai trục, (ii) **tam giác lực** (3 lực đồng quy ⇒ tạo tam giác kín), (iii) **định lý Lami** `F₁/sin α₁ = F₂/sin α₂ = F₃/sin α₃` (α_i là góc **đối diện** F_i, tức góc giữa hai lực còn lại), (iv) phương pháp đồ thị.
- **Pre**: chất điểm (đồng quy). Nếu là vật rắn, 3 lực không song song cân bằng phải đồng quy — đó là bài vật rắn.
- **Nhận diện chế độ**: "sắp trượt", "sắp rời", "sắp căng" ⇒ đổi bất đẳng thức thành đẳng thức tại biên.

### 4.2. S2 — Hệ vật nối bằng dây/ròng rọc/tiếp xúc (hệ tuyến tính nhờ ràng buộc)
- **Dạng Toán**: n phương trình Newton (theo phương chuyển động có nghĩa) + k ràng buộc gia tốc ⇒ hệ **tuyến tính** trong (a₁…aₙ, T₁…) ⇒ giải bằng khử hoặc Cramer.
- **Dấu hiệu**: "dây không dãn", "ròng rọc nhẹ", "nối với nhau", "đặt lên nhau", "đặt trên nêm".
- **Công cụ chính = viết ràng buộc**:
  1. *Dây không dãn*: **tổng độ dài các đoạn = const** ⇒ đạo hàm hai lần ⇒ ràng buộc gia tốc.
  2. *Ròng rọc động nhẹ*: hợp lực lên ròng rọc = 0 ⇒ lực trục = **2T** (khi hai nhánh song song).
  3. *Tiếp xúc không rời*: thành phần gia tốc **vuông góc mặt tiếp xúc** của hai vật bằng nhau (trong HQC quán tính).
  4. *Dây xiên*: KHÔNG chiếu gia tốc như chiếu vận tốc. Ví dụ vật trên bàn kéo bởi dây qua ròng rọc ở độ cao h: `l² = x² + h²` ⇒ `l̇ = ẋ cos θ`, còn `l̈ = ẍ cos θ + ẋ² h² / l³`. Thành phần thứ hai (≈ v²/l) là thành phần "hướng tâm" hay quên.
- **Ví dụ kết quả [B]** (ròng rọc động): xem ví dụ E1 mục 7.
- **Kiểm tra cấu trúc**: số ẩn (a's và T's) = số phương trình (Newton theo phương cần + ràng buộc). Nếu không, quay lại mục 1.2.

### 4.3. S3 — Ma sát và chuyển chế độ (đại số có nhánh + bất đẳng thức)
- **Dạng Toán**: bài có **bất đẳng thức bổ sung** (complementarity): với mỗi tiếp xúc, *hoặc* nghỉ (`a_rel = 0`, `|f| ≤ μ_s N`) *hoặc* trượt (`f = μ_k N`). Chỉ một chế độ nhất quán.
- **Dấu hiệu**: "có ma sát", "bắt đầu trượt", "F tối thiểu để…", "vật này trượt trên vật kia".
- **Thuật toán nhánh (giả thiết–kiểm tra)** [C] — chi tiết ở 6.5:
  1. Giả sử tất cả tiếp xúc **nghỉ** ⇒ giải hệ đại số ⇒ tính f cần thiết.
  2. Kiểm tra `|f| ≤ μ_s N` cho từng tiếp xúc. Nếu thỏa hết ⇒ xong.
  3. Nếu vi phạm ⇒ chọn tiếp xúc trượt (hướng trượt do hướng f cần thiết), viết `f = μ_k N` ngược hướng vận tốc tương đối, giải lại, **kiểm tra hướng trượt có nhất quán và các tiếp xúc còn lại có nghỉ được không**.
- **Ngưỡng**: điều kiện "vừa đủ để trượt" = tại biên `|f| = μ_s N` (đẳng thức của nhánh nghỉ).
- **Kết quả chuẩn**: dốc góc α, trượt xuống: `a = g (sin α − μ cos α)`; đi lên (giảm tốc): `a = g (sin α + μ cos α)` (độ lớn).
- **Xe trên đường nghiêng (đường vòng có bờ nghiêng)** [A]: giữ nguyên trên quỹ đạo tròn bán kính R với góc nghiêng α, hệ số ma sát μ: `v²_max = R g (tan α + μ)/(1 − μ tan α)`, `v²_min = R g (tan α − μ)/(1 + μ tan α)`; μ = 0 ⇒ `v² = R g tan α`.

### 4.4. S4 — Chuyển động cong: tọa độ tự nhiên/cực + điều kiện biên
- **Dạng Toán**: Newton chiếu **tiếp tuyến** và **pháp tuyến**; thêm **điều kiện đặc biệt** (N = 0, T = 0) tại một điểm; thường kèm **năng lượng** để có v tại điểm đó (vì hai phương trình tiếp tuyến/pháp tuyến không đủ để tách v khỏi ODE theo góc).
- **Dấu hiệu**: "con lắc", "vòng tròn thẳng đứng", "mặt cầu", "chuyển động tròn", "rời mặt", "dây căng tối thiểu".
- **Công cụ**: `Σ F_n = m v²/ρ` với ρ là bán kính **cong**; `m dv/dt = Σ F_τ`; kết hợp `v dv/ds = a_τ` hay bảo toàn cơ năng.
- **Kết quả chuẩn [A]/[B]**:
  - **Trượt nhẵn từ đỉnh mặt cầu** bán kính R (vận tốc đầu ≈ 0): `N = m g cos θ − m v²/R`, `v² = 2 g R (1 − cos θ)` ⇒ rời mặt khi **cos θ = 2/3**. [B]
  - **Vòng tròn thẳng đứng trong lòng** (không rời mặt): đỉnh cần `v_đỉnh ≥ √(g R)`, tương ứng đáy `v_đáy ≥ √(5 g R)`. [A]
  - **Con lắc nón**: `ω² = g /(l cos θ)`, `T = m g / cos θ`. [A]
  - **Con lắc đơn**: `T = m (g cos θ + v²/l)` (T lớn nhất ở đáy). [B] (khớp KKT ở 6.7)
- **Bẫy**: dùng ρ = R chỉ khi quỹ đạo là đường tròn. Quỹ đạo elip/parabol có ρ thay đổi.

### 4.5. S5 — Lực phụ thuộc vận tốc: ODE tách biến
- **Dạng Toán**: `m dv/dt = F(v) (+ hằng)` ⇒ **tách biến** `dv/F(v) = dt/m`.
- **Dấu hiệu**: "lực cản", "trong chất lỏng nhớt", "không khí", "vận tốc giới hạn", "sau bao lâu thì…".
- **Công cụ cốt lõi**: hai dạng của cùng ODE:
  - Cần **v(t)** hoặc **t**: dùng `dv/dt`.
  - Cần **v(x)** hoặc quãng đường: dùng **`dv/dt = v dv/dx`** (đổi biến độc lập thời gian → vị trí).
- **Kết quả chuẩn**:
  - **Cản tuyến tính, rơi**: `v(t) = v_T (1 − e^{−t/τ})`, `τ = m/b`, `v_T = m g /b`. Quãng đường đến dừng khi bắn ngang với v₀ (không g): `x_max = v₀ τ`.
  - **Ném xiên với cản tuyến tính** (v₀x, v₀y): `x(t) = v₀ₓ τ (1 − e^{−t/τ})`, `y(t) = τ (v₀ᵧ + g τ)(1 − e^{−t/τ}) − g τ t`.
  - **Cản bậc hai, rơi**: `v(t) = v_T tanh(g t / v_T)`. [B]
  - **Cản bậc hai, ném thẳng đứng lên** vận tốc v₀: độ cao cực đại **`H = (v_T²/(2g)) ln(1 + v₀²/v_T²)`**; `t_lên = (v_T/g) arctan(v₀/v_T)`. [B: H kiểm bằng tích phân số, sai lệch ~10⁻¹¹]
- **Nhận diện giới hạn**: khi v_T → ∞ (không cản), `H → v₀²/(2g)`. (Kiểm tra bằng khai triển ln(1+u) ≈ u.)

### 4.6. S6 — Lực phụ thuộc vị trí: ODE tự trị và năng lượng
- **Dạng Toán**: `m ẍ = F(x)` ⇒ nhân với ẋ / đổi biến `ẍ = v dv/dx` ⇒ **tích phân đầu**: `½ m v² − ∫F dx = const` (đây chính là định lý động năng/bảo toàn cơ năng, xuất hiện như một *tích phân đầu* của ODE).
- **Dấu hiệu**: "lò xo", "lực hấp dẫn thay đổi theo r", "đến độ cao / vị trí nào", "vận tốc tại vị trí x".
- **Công cụ**: (i) hạ bậc ODE bằng năng lượng, (ii) **khai triển nhỏ quanh vị trí cân bằng** ⇒ `ẍ = −ω² x`, (iii) tích phân thời gian `t = ∫ dx / v(x)`.
- **Dao động điều hòa** [A]: `ẍ + ω² x = 0`, `x = A cos(ωt + φ)`, `ω = √(k/m)`. **Pre: biên độ nhỏ (xấp xỉ tuyến tính hóa).** Con lắc đơn: `ω = √(g/l)` khi θ ≪ 1.
- **Ma sát khô trong dao động lò xo (ODE từng đoạn)** [B]: `m ẍ = −kx ∓ μ m g`, dấu theo hướng vận tốc. Với μ_s = μ_k:
  - Biên độ giảm **tuyến tính** (không phải mũ): mỗi **nửa chu kỳ** giảm `2 μ m g / k`.
  - Chu kỳ **không đổi** `2π √(m/k)`.
  - Vật dừng vĩnh viễn tại điểm dừng đầu tiên có `|x| ≤ μ m g / k`.
  - (Kiểm bằng tích phân số: nửa chu kỳ đầu từ x₀ = 1 kết thúc tại x = −0,608 với k = 10, m = 1, μ = 0,2, khớp `−(x₀ − 2μmg/k)`.)

### 4.7. S7 — Lực phụ thuộc thời gian / xung lực
- **Dạng Toán**: `m dv/dt = F(t)` ⇒ `m v(t) = m v₀ + ∫F dt` (định lý xung lượng) ⇒ tích phân trực tiếp.
- **Dấu hiệu**: "tác dụng trong khoảng thời gian", "va chạm ngắn", "lực biến thiên theo t".
- **Ghi chú**: lực xung (rất ngắn, rất lớn) ⇒ dùng xung lượng thay vì Newton từng thời điểm; các lực hữu hạn khác có thể bỏ qua trong khoảng đó.

### 4.8. S8 — Khối lượng biến thiên / dòng khối lượng
- **Dạng Toán**: Newton II cho **hệ hạt cố định** trong dt, hoặc `m dv/dt = F + u_rel dm/dt` (mục 2.2.1).
- **Dấu hiệu**: "tên lửa", "dây xích rơi", "băng chuyền", "giọt mưa", "xe hứng cát".
- **Kết quả chuẩn [A]/[B]**:
  - Tên lửa (bỏ ngoại lực): `Δv = u_e ln(m₀/m)`.
  - **Dây xích** mật độ dài λ rơi lên bàn từ trạng thái mép dưới vừa chạm: phần đã rơi dài x, đoạn đang rơi có `v² = 2 g x`. Lực tổng của bàn: `N = λ g x + λ v² = 3 λ g x` (3 lần trọng lượng phần đã nằm trên bàn). [B]
  - **Băng chuyền** tốc độ v không đổi nhận khối lượng với tốc độ dm/dt: lực kéo `F = v dm/dt`, công suất `F v = v² dm/dt` bằng **2 lần** tốc độ tăng động năng ⇒ một nửa bị tiêu hao (ma sát/va chạm mất mát). [A]
- **Bẫy**: dùng `F = d(mv)/dt` bừa bãi (xem 2.2.1).

### 4.9. S9 — Hệ quy chiếu phi quán tính (đổi biến để "đưa Newton về dạng cũ")
**Cấu trúc Toán**: đây là **đổi biến** `r = R(t) + r'` (hoặc thêm phép quay). Sau đổi biến, ODE cũ có thêm các số hạng phụ; các số hạng phụ được diễn giải là "lực quán tính". Kỹ thuật đổi biến này *biến bài toán có nền chuyển động thành bài toán tĩnh/đơn giản hơn*.

#### (a) HQC tịnh tiến có gia tốc **A** (đối với HQC quán tính) [A]
```
m a' = F − m A
```
Lực quán tính `−m A` (tịnh tiến). Vật *đứng yên* trong HQC: a' = 0 ⇒ `F = m A` (thường dùng "trọng lực hiệu dụng" `g_eff = g − A`).
- Thang máy gia tốc a lên: `g_eff = g + a` (lên là dương). Trọng lượng biểu kiến `m(g + a)`.
- Xe gia tốc a nằm ngang: con lắc lệch góc `tan θ = a/g`, `g_eff = √(g² + a²)`, chu kỳ `T = 2π √(l / g_eff)`.
- **Bẫy**: nếu HQC gắn với **vật có gia tốc chưa biết** (nêm bị vật đẩy), A **cũng là ẩn**; cần thêm phương trình cho vật đó (Newton II của nêm). Ví dụ E2 mục 7.

#### (b) HQC quay đều với vận tốc góc **Ω** (quanh trục cố định) [A]
Với r' và v' là vị trí/vận tốc trong HQC quay:
```
a = a' + 2 Ω × v' + Ω × (Ω × r') + (dΩ/dt) × r'
m a' = F − 2 m Ω × v'  −  m Ω × (Ω × r')  −  m (dΩ/dt) × r'
```
- **Lực Coriolis**: `F_C = −2 m Ω × v'` — vuông góc v' ⇒ **không sinh công**; **chỉ xuất hiện khi vật chuyển động so với HQC**.
- **Lực ly tâm**: `−m Ω × (Ω × r') = + m Ω² r'_⊥` (hướng ra khỏi trục, độ lớn `m Ω² d`, d là khoảng cách tới trục). Trong HQC quay đều, nó là **lực có thế**: `U_cf = −½ m Ω² d²`. (Vì vậy trong HQC quay đều có tích phân năng lượng (tích phân Jacobi) `½ m v'² + U + U_cf = const` nếu U không phụ thuộc t.) [A]
- **Lực Euler**: `−m (dΩ/dt) × r'` — chỉ khi Ω đổi.
- **Không có phản lực của lực quán tính.**

#### (c) Ứng dụng chuẩn
- **Hạt trong ống quay đều, nhẵn, ω không đổi** (hạt trượt trong ống thẳng quay quanh trục vuông góc ống): trong HQC ống: `r̈ = ω² r` ⇒ nghiệm `r = A e^{ωt} + B e^{−ωt}`; với `r(0) = r₀, ṙ(0) = 0`: `r = r₀ cosh ωt`, phản lực ống `N = 2 m ω ṙ = 2 m ω² r₀ sinh ωt` (cân bằng Coriolis). [B: nghiệm số khớp]. Trong HQC quán tính: `a_r = r̈ − r ω² = 0` (không lực xuyên tâm), `a_θ = 2 ṙ ω = N/m`. Hai cách nhất quán.
- **Mặt chất lỏng quay đều** (trong bình quay ω): mặt là paraboloid `h(r) = ω² r² /(2 g)`. [A]
- **Trái Đất quay**: `g_eff = g − Ω × (Ω × R)`; ở vĩ độ λ, thành phần ly tâm hướng vuông góc trục; `Ω = 7,29×10⁻⁵ rad/s`.
- **Rơi tự do từ độ cao h ở vĩ độ λ**: lệch về **phía Đông** một đoạn
  `Δx = (2√2/3) Ω cos λ √(h³/g)` (bỏ ly tâm, bậc thấp nhất). [B]
  Với h = 100 m, λ = 45°: **Δx ≈ 1,55 cm** (kiểm số: 1,553 cm, chu kỳ rơi 4,52 s).
  Suy ra từ: trục x Đông, y Bắc, z lên; `Ω = Ω(cos λ ŷ + sin λ ẑ)`; `v ≈ −g t ẑ`; `a_C = −2Ω × v = 2 g t Ω cos λ x̂` ⇒ `x = (1/3) g Ω cos λ t³`.
- **Chuyển động ngang trên Trái Đất**: gia tốc Coriolis ngang có độ lớn `2 Ω v sin λ`, **lệch phải** ở Bắc bán cầu, lệch trái ở Nam bán cầu. [A]

#### (d) Khi nào chọn HQC phi quán tính? [C]
Chọn khi: (i) hỏi **cân bằng tương đối** (a' = 0 ⇒ Newton I của tĩnh học), (ii) vật gắn trong/trên vật có gia tốc **đã biết**, (iii) quay đều và vật đứng yên hoặc đi trong ống/rãnh.
Chọn HQC quán tính khi: (i) A chưa biết và phức tạp, (ii) có nhiều vật cùng có gia tốc khác nhau, (iii) muốn tránh nhầm lực quán tính.

### 4.10. Bảng nhận diện nhanh: đề nói gì ⇒ cấu trúc ⇒ toán tử đầu tiên [C]

| Đề nói gì | Cấu trúc | Toán tử đầu tiên (xem 6.3) |
|---|---|---|
| "cân bằng", "đứng yên" | S1 đại số | ℓ₂ chiếu hoặc tam giác lực/Lami |
| dây + ròng rọc + nhiều vật | S2 tuyến tính | ℓ₅ ràng buộc dây, ℓ₁ Newton từng vật |
| "có ma sát", "bắt đầu trượt", "tối thiểu" | S3 nhánh | ℓ₉ giả thiết nghỉ, ℓ₁₀ kiểm tra |
| "rời mặt", "căng tối thiểu", "vòng tròn" | S4 cong + biên | ℓ₃ tọa độ tự nhiên, ℓ₁₁ N=0/T=0, ℓ₁₇ năng lượng |
| "lực cản", "sau bao lâu", "vận tốc giới hạn" | S5 ODE F(v) | ℓ₁₂ đổi biến v dv/dx, ℓ₁₃ tách biến |
| "lò xo", "dao động nhỏ" | S6 ODE F(x) | ℓ₁₉ tuyến tính hóa, ℓ₁₇ |
| "tác dụng trong Δt", "xung" | S7 | ℓ₁₆ xung lượng |
| "tên lửa", "dây xích", "băng chuyền" | S8 | ℓ₂₀ định lý xung lượng cho hệ hạt cố định |
| vật trên nêm/xe/thang máy, "quay đều", "Trái Đất" | S9 | ℓ₁₄ đổi HQC |
| nhiều vật, chỉ hỏi chuyển động chung | hệ + khối tâm | ℓ₁₅ coi cả hệ |

---

## 5. VẤN ĐỀ 1: CHUYỂN BÀI VẬT LÝ VỀ BÀI TOÁN (MÔ HÌNH HÓA, XẤP XỈ, ĐỌC DỮ KIỆN, VẼ HÌNH)

### 5.1. Quy trình 9 bước [C]

| Bước | Việc phải làm | Sản phẩm (đưa vào M) |
|---|---|---|
| P1 | Đọc đề, **gạch dưới mọi dữ kiện định lượng và định tính** ("nhẵn", "nhẹ", "không dãn", "vừa sắp", "chậm") | Danh sách I |
| P2 | Xác định **đối tượng** và mô hình hóa từng đối tượng: chất điểm? dây nhẹ? mặt nhẵn? lò xo lý tưởng? | O |
| P3 | Chọn **HQC** (quán tính hay không, vì sao) và **hệ trục** | Khung quan sát |
| P4 | **Vẽ hình**, chọn chiều dương cho từng vật, ghi ký hiệu biến (vị trí, gia tốc) | V |
| P5 | **Sơ đồ lực tự do (FBD)** cho từng vật (quy tắc 5.2) | Danh sách lực và ẩn |
| P6 | **Ràng buộc** (dây, tiếp xúc, ròng rọc) và **điều kiện đặc biệt** (N=0, T=0, sắp trượt…) | C |
| P7 | **Đọc câu hỏi Q** và xác định đại lượng cần tìm, đại lượng trung gian | Q |
| P8 | **Đếm ẩn – đếm phương trình** (mục 1.2). Không cân ⇒ sửa mô hình | Kiểm tra sức khỏe |
| P9 | Nhận diện **cấu trúc** (bảng 4.10) ⇒ chuyển sang Vấn đề 2 | Cấu trúc S? |

### 5.2. Quy tắc vẽ sơ đồ lực tự do (FBD) [A]/[C]
1. **Cô lập** vật (hoặc hệ con), xóa mọi thứ xung quanh, thay bằng **lực mà chúng tác dụng lên vật**.
2. Chỉ vẽ **lực tác dụng lên vật đang xét** (không vẽ lực vật tác dụng lên vật khác).
3. Đi vòng quanh **đường biên** của vật: mỗi chỗ tiếp xúc (dây, mặt, lò xo, tay) sinh **tối đa** một lực liên kết (pháp tuyến + ma sát nếu có); mỗi trường (trọng trường, điện trường) sinh một lực từ xa.
4. **Không** vẽ "lực hướng tâm", **không** vẽ lực quán tính nếu đang ở HQC quán tính.
5. Mỗi lực liên kết chưa biết ⇒ ghi thành **ẩn** (đánh dấu); giả sử chiều, chiều thật sẽ được dấu quyết định.
6. **Chọn chiều dương cho gia tốc nhất quán** với chiều đã giả sử của chuyển động, đặc biệt ở hệ nhiều vật nối dây.

### 5.3. Từ điển ngôn ngữ đề ⇒ ngôn ngữ Toán [C]
| Đề nói | Nghĩa Toán |
|---|---|
| mặt phẳng **nhẵn** / không ma sát | f = 0 |
| dây **nhẹ** | khối lượng dây = 0 ⇒ T đồng nhất dọc dây (khi không có lực ngang lên dây) |
| dây **không dãn** | ràng buộc độ dài không đổi |
| ròng rọc nhẹ, không ma sát | T như nhau hai bên |
| lò xo nhẹ | lực như nhau hai đầu; khối lượng ≈ 0 |
| **chất điểm** | bỏ kích thước, bỏ quay |
| **cân bằng** / đứng yên / đều | a = 0 |
| **vừa bắt đầu trượt** / "vừa đủ" | \|f\| = μ_s N |
| **vừa rời mặt** | N = 0 |
| dây **vừa chùng** | T = 0 |
| **vận tốc giới hạn** | a = 0 (lực cản = lực phát động) |
| **lần đầu tiên** / "cực đại" | điểm dừng/ điểm có v = 0 hay đạo hàm = 0 |
| "**rất nhỏ**" / "rất lớn" | dùng khai triển (Taylor) / lấy giới hạn |
| M ≫ m | coi vật M đứng yên hoặc HQC gắn M là quán tính |
| va chạm ngắn | định lý xung lượng, bỏ lực hữu hạn trong Δt |

### 5.4. Xấp xỉ có điều kiện (mỗi cái là một toán tử với Pre) [C]
| Xấp xỉ | Được phép khi | Kiểm tra sau khi giải |
|---|---|---|
| g = const | h ≪ R | Δg/g ~ 2h/R nhỏ |
| Bỏ lực cản không khí | v_T ≫ v, hoặc `k₂ v² ≪ mg` | so `k₂v²/(mg)` |
| Tuyến tính hóa (sin θ ≈ θ) | θ ≲ 0,1 rad (sai số ~ θ²/6) | biên độ thực sự nhỏ |
| Dây không dãn | độ cứng dây ≫ lực căng | độ dãn ≪ chiều dài |
| Ròng rọc nhẹ | m_ròng rọc ≪ m các vật | so sánh |
| Trái Đất là HQC quán tính | thời gian quan sát ≪ 1 ngày, vận tốc/khoảng cách nhỏ | Ω t ≪ 1 |
| Bỏ ly tâm khi tính Coriolis | Ω² r ≪ 2Ω v | so hai số hạng |

### 5.5. Chọn hệ trục [C]
- Chọn trục sao cho **lực ẩn không cần biết vuông góc với một trục** (loại ẩn sớm).
- Trên mặt phẳng nghiêng: trục dọc mặt và trục vuông mặt.
- Chuyển động tròn: trục tiếp tuyến/pháp tuyến, hoặc cực.
- Bài đối xứng trục: dùng tọa độ trụ/cực.
- Nếu ràng buộc đơn giản ở một hệ tọa độ (ví dụ r = const) thì chọn hệ đó để ràng buộc "tự biến mất" (nguyên tắc của tọa độ suy rộng, mục 6.7).

---

## 6. VẤN ĐỀ 2: DÙNG CẤU TRÚC TOÁN ĐỂ GIẢI — BÀI TOÁN TÌM KIẾM CHO ĐỘNG LỰC HỌC CHẤT ĐIỂM

### 6.1. Cụ thể hóa "CHỖ" và "CÔNG CỤ" trong Động lực học [C]

Theo file gốc: bài toán tìm kiếm là tìm dãy `(ℓ₁, CHỖ₁), …, (ℓₙ, CHỖₙ)` sao cho `Pre(ℓᵢ)` thỏa tại `CHỖᵢ`, `Post(ℓᵢ)` sinh ràng buộc mới có ý nghĩa, và cuối cùng `C ∪ L ⊢ Q`.

Trong Động lực học chất điểm, các **CHỖ** có thể liệt kê được:

| Loại CHỖ | Là gì | Ví dụ |
|---|---|---|
| **CH-a** | Một chất điểm (hoặc vật coi như chất điểm) | Vật m₁ |
| **CH-b** | Một **hệ con** (nhóm vật) | Cả hệ để khử lực nội |
| **CH-c** | Một **mặt cắt** của dây/lò xo để lộ lực căng | Cắt dây tại một điểm |
| **CH-d** | Một **điểm/khoảnh khắc đặc biệt** | Sắp rời mặt, dây vừa chùng, điểm dừng, lúc đạt v giới hạn |
| **CH-e** | Một **cặp tiếp xúc/liên kết** | Dây nối, mặt tiếp xúc, ròng rọc |
| **CH-f** | Một **trục chiếu / hệ tọa độ** | Dọc dốc, tiếp tuyến |
| **CH-g** | Một **HQC** | HQC gắn nêm |

**CÔNG CỤ** = toán tử ℓ trong thư viện 6.3.

### 6.2. Vì sao không gian tìm kiếm ở đây là hữu hạn và nhỏ [C]
Với mô hình đã chốt gồm n vật và k ràng buộc:
- Số **CH-a** là n; số **CH-e** là k; số **CH-f** là bậc của hệ tọa độ (2 hoặc 3 trục) — tất cả đều **O(n + k)**.
- **CH-b** (hệ con) về mặt tổ hợp có thể tới 2ⁿ, nhưng **chỉ có vài hệ con có ý nghĩa**: từng vật, cả hệ, và các hệ con "cắt theo dây/tiếp xúc" tại chỗ cần biết lực (O(k)).
- **CH-d** (điểm đặc biệt) bị giới hạn bởi các bất đẳng thức đã có (N≥0, T≥0, |f|≤μN) và bởi câu hỏi Q.
- Số **toán tử** ℓ trong thư viện ~ 20 (6.3).

⇒ Với *một mô hình đã chốt*, việc "tìm chỗ" là **hữu hạn và nhỏ**; điều khó thật sự chuyển sang: **(1) chọn mô hình (Vấn đề 1), (2) chọn HQC/hệ tọa độ, (3) chọn hệ con/mặt cắt, (4) biết khi nào cần chuyển chế độ**. Đó là chỗ trực giác còn vai trò; tài liệu này cố **thu hẹp** phần trực giác, chưa loại bỏ nó.

Điều này cũng giải thích lời bạn viết về Nodal Analysis: nó mạnh vì **bỏ qua bước "tìm chỗ"**: nút nào cũng là chỗ dùng KCL (CH = mọi nút). Ở mục 6.7 tôi chỉ ra "Nodal Analysis của cơ học".

### 6.3. Thư viện toán tử ℓ (Pre / Post / dấu hiệu CHỖ) [C]

Nhắc: **Pre(ℓ)** = điều kiện *cần* để bước ℓ **đúng**. Nếu vi phạm ⇒ **kết quả sai**. **Post(ℓ)** = phương trình/ràng buộc mới sinh ra.

**Nhóm I — Toán tử Newton (sinh phương trình chuyển động)**

| ℓ | Tên | Pre | Post | Dấu hiệu CHỖ / Bẫy |
|---|---|---|---|---|
| ℓ₁ | Newton II tại chất điểm | HQC quán tính (hoặc đã cộng lực quán tính); khối lượng const (hoặc dùng ℓ₂₀); **đã liệt kê đủ lực** (FBD đúng) | `m a = ΣF` (vectơ) | Mỗi vật có gia tốc chưa biết/ hoặc cần lực. Bẫy: quên/đếm thừa lực |
| ℓ₂ | Chiếu lên trục | Trục **cố định** trong HQC đang dùng | `m a_x = ΣF_x` … | Chọn trục vuông góc với lực ẩn cần loại. Bẫy: trục xoay theo vật (tọa độ tự nhiên) phải dùng ℓ₃ |
| ℓ₃ | Tọa độ tự nhiên / cực | Quỹ đạo (hoặc r, θ) được xác định bởi ràng buộc | `m dv/dt = ΣF_τ`, `m v²/ρ = ΣF_n`; hoặc `a_r`, `a_θ` cực | Vật đi theo cung/mặt cong. Bẫy: ρ ≠ R nếu quỹ đạo không tròn |
| ℓ₄ | Newton III | Hai vật **thật** tương tác (không phải lực quán tính) | `F_AB = −F_BA`, `N_AB = N_BA` | Mỗi tiếp xúc/dây: cho **miễn phí** một phương trình liên kết |

**Nhóm II — Toán tử ràng buộc (sinh phương trình hình học)**

| ℓ | Tên | Pre | Post | Dấu hiệu / Bẫy |
|---|---|---|---|---|
| ℓ₅ | Ràng buộc dây | Dây **không dãn** và **luôn căng** (T > 0) | `Σ ± lᵢ = const` ⇒ `Σ ± vᵢ… = 0`, `Σ ± aᵢ… = 0` | Dây nối vật. Bẫy: dây xiên (thêm v²/l); dây chùng thì ràng buộc thành bất đẳng thức |
| ℓ₆ | Ràng buộc tiếp xúc | Hai vật **không rời nhau** (N > 0) | `a_n` bằng nhau (theo phương pháp tuyến, trong HQC quán tính) | Vật trên nêm, vật đặt trên vật. Bẫy: `N = 0` nghĩa là rời ⇒ ràng buộc mất |
| ℓ₇ | Ròng rọc nhẹ | Ròng rọc **khối lượng ≈ 0**, **không ma sát** | T bằng nhau hai bên; ròng rọc **động** nhẹ ⇒ lực trục = 2T (hai nhánh song song) | Bẫy: ròng rọc có khối lượng ⇒ T hai bên khác nhau (cần mômen) |

**Nhóm III — Toán tử chọn hệ / phân rã**

| ℓ | Tên | Pre | Post | Dấu hiệu / Bẫy |
|---|---|---|---|---|
| ℓ₈ | Hệ con / mặt cắt | Xác định rõ biên hệ con và **lực ngoài** tại biên | Newton II cho hệ con (chỉ lực ngoài) | Muốn lực tại đúng một chỗ ⇒ cắt chỗ đó |
| ℓ₁₅ | Coi cả hệ / khối tâm | Newton III dạng yếu | `M a_cm = ΣF_ngoại` | Chỉ hỏi chuyển động chung; lực nội không cần |

**Nhóm IV — Toán tử điều kiện (chế độ, biên)**

| ℓ | Tên | Pre | Post | Dấu hiệu / Bẫy |
|---|---|---|---|---|
| ℓ₉ | Giả thiết nghỉ (ma sát) | Có tiếp xúc ma sát; chưa biết trượt hay nghỉ | `a_rel = 0` (thêm phương trình), f trở thành ẩn | Bẫy: nhớ kiểm tra `|f| ≤ μ_s N` ngay sau |
| ℓ₁₀ | Ma sát trượt (Coulomb) | Đã biết/giả thiết đang trượt; biết hướng v_rel | `f = μ_k N`, hướng ngược v_rel | Bẫy: hướng phải nhất quán với kết quả cuối |
| ℓ₁₁ | Điều kiện biên đặc biệt | Đề nêu "sắp/vừa/tối thiểu/giới hạn" | `N = 0`, `T = 0`, `|f| = μ_s N`, `a = 0`, `v = 0`… tại điểm đó | Bẫy: chọn nhầm ẩn nào bị triệt tiêu tại điểm đó |

**Nhóm V — Toán tử biến đổi ODE (hạ bậc, tách biến, đổi biến)**

| ℓ | Tên | Pre | Post | Dấu hiệu / Bẫy |
|---|---|---|---|---|
| ℓ₁₂ | Đổi biến `dv/dt = v dv/dx` | Chuyển động 1 chiều (hoặc một tọa độ suy rộng); F chỉ phụ thuộc x, v | ODE bậc 1 theo x | Hỏi v tại vị trí/quãng đường |
| ℓ₁₃ | Tách biến | ODE dạng `dv/dt = f(v)` hoặc `dx/dt = g(x)` | `∫dv/f(v) = t` | Lực cản, tăng dần đều |
| ℓ₁₇ | Năng lượng (công–động năng) | Lực **bảo toàn** hoặc biết công; lực liên kết **vuông góc** với chuyển dời ⇒ không sinh công | `ΔK = ΣA` | Hỏi v qua vị trí, không cần thời gian. Bẫy: ma sát **không** bảo toàn, phải tính công ma sát |
| ℓ₁₆ | Xung lượng | Lực ngắn, hoặc F(t) biết | `Δp = ∫F dt` | "tác dụng trong Δt", "va chạm" |
| ℓ₁₉ | Tuyến tính hóa (Taylor) | Độ lệch **nhỏ** quanh vị trí cân bằng | `ẍ = −ω² x` | Dao động nhỏ. Bẫy: nhớ đưa điều kiện biên độ nhỏ vào đáp số |
| ℓ₂₀ | Xung lượng cho hệ hạt cố định | Khối lượng biến thiên; xác định đúng hệ hạt | `m dv/dt = F + u_rel dm/dt` | Tên lửa, dây xích, băng chuyền |

**Nhóm VI — Toán tử đổi HQC**

| ℓ | Tên | Pre | Post | Dấu hiệu / Bẫy |
|---|---|---|---|---|
| ℓ₁₄ | Đổi HQC (lực quán tính) | Biết A(t) (hoặc thêm A làm ẩn); biết Ω(t) | `m a' = F − mA − 2mΩ×v' − mΩ×(Ω×r') − mΩ̇×r'` | Vật trên nêm/xe/thang máy/vật quay. Bẫy: không phản lực; không lẫn 2 HQC trong cùng phương trình |

**Nhóm VII — Toán tử giải**

| ℓ | Tên | Pre | Post | Dấu hiệu / Bẫy |
|---|---|---|---|---|
| ℓ₁₈ | Giải hệ tuyến tính (khử / Cramer / ma trận) | Hệ tuyến tính trong các ẩn, `δ = 0` (mục 6.4), định thức ≠ 0 | Nghiệm duy nhất | Hệ n vật nối dây. Bẫy: hệ suy biến ⇒ mô hình thiếu/thừa |

**Toán tử "nặng"** (chưa tính vào 20 toán tử): KKT/ma trận ràng buộc và Lagrange (mục 6.7). Dùng khi hệ nhiều vật, nhiều ràng buộc, cần thuật toán ổn định (giống vai trò Nodal Analysis).

### 6.4. Độ thiếu δ: tiêu chí "bước tiến có ý nghĩa" cho toán tử [C]

File gốc để lại một khoảng trống: `Pre(ℓ)` chỉ cho biết **ℓ hợp lệ**, chưa cho biết **ℓ có giúp không**. Đề xuất:

**Định nghĩa (độ thiếu).** Trạng thái bài toán gồm tập ẩn `U` (các đại lượng chưa biết độc lập: gia tốc/vận tốc/lực ẩn/thời gian) và tập phương trình độc lập `E`. Đặt
```
δ = |U| − rank(E)
```
- **δ > 0**: còn thiếu phương trình (chưa giải được). Cần thêm ràng buộc/toán tử.
- **δ = 0**: **số** ẩn = số phương trình độc lập. Kết hợp với **định thức ≠ 0** ⇒ có nghiệm duy nhất (hệ tuyến tính).
- **δ < 0**: thừa/ mâu thuẫn; có thể hai phương trình phụ thuộc hoặc mô hình thừa dữ kiện — cần kiểm tra.

**Một bước (ℓ, CHỖ) là "có ý nghĩa" nếu:**
1. **Pre(ℓ) thỏa tại CHỖ** (hợp lệ), **và**
2. **Post(ℓ) làm δ giảm** (Δδ < 0), **hoặc** nó **hạ bậc** một ODE (một tích phân đầu), **hoặc** nó **giảm số chế độ cần xét** (loại nhánh).

Cách đo cho từng bước: `Δδ = (số ẩn độc lập mới) − (số phương trình độc lập mới)`. Ví dụ: Newton II cho một vật kèm 1 lực liên kết ẩn mới ⇒ Δδ = 0 (phương trình mới vừa bù ẩn mới); ràng buộc dây thêm 1 phương trình mà không thêm ẩn ⇒ Δδ = −1. Vậy phần lớn "tiến bộ thật" nằm ở các bước ràng buộc, Newton III và điều kiện đặc biệt, không phải ở việc viết thêm Newton II.

**Liên hệ với điều kiện cần/đủ của bạn** [C]:
- **Điều kiện cần** (Necessary): `Pre(ℓ)` thỏa ⇒ nếu vi phạm thì **chắc chắn sai**; thỏa chưa chắc **có ích**.
- **Điều kiện đủ** (Sufficient): `δ = 0` **và** hệ không suy biến ⇒ **chắc chắn** giải được (đại số).
- Đếm δ = 0 **chỉ là điều kiện cần** cho giải được: hệ có thể suy biến. Đây là ví dụ đúng của phân biệt bạn nhấn mạnh.

### 6.5. Thuật toán nhánh chế độ (ma sát, dây chùng, rời mặt) [C]

Vấn đề: **Pre của một toán tử phụ thuộc vào kết quả** (ví dụ ℓ₅ cần "T > 0"; ℓ₆ cần "N > 0"; ℓ₁₀ cần "hướng trượt = hướng giả thiết"). Đây chính là "họ precondition có tham số" bạn gợi ý.

```
Thuật toán CHẾ ĐỘ (giả thiết – giải – kiểm tra)
1. Liệt kê các "công tắc" c₁…c_m: mỗi công tắc là một bất đẳng thức của bài
     (T_j ≥ 0, N_j ≥ 0, |f_j| ≤ μ_s N_j, hướng trượt).
2. Chọn một chế độ khởi đầu hợp lý (thường: tất cả căng, tất cả tiếp xúc, tất cả nghỉ).
3. Giải hệ (ℓ₁…ℓ₁₈) trong chế độ đó ⇒ có nghiệm, kể cả các lực liên kết.
4. Kiểm tra mọi công tắc bằng nghiệm vừa giải.
     - Nếu mọi bất đẳng thức thỏa ⇒ ĐÂY LÀ CHẾ ĐỘ THẬT. Dừng.
     - Nếu công tắc c_j bị vi phạm ⇒ đổi chế độ tương ứng
       (T_j<0 ⇒ dây chùng: T_j := 0, bỏ ràng buộc dây;
        N_j<0 ⇒ rời mặt: N_j := 0, bỏ ràng buộc tiếp xúc;
        |f_j|>μ_s N_j ⇒ trượt: f_j := ±μ_k N_j, bỏ điều kiện a_rel = 0).
5. Lặp lại từ bước 3 với chế độ mới. Kết thúc khi nhất quán.
```
- **Số chế độ** tối đa là 2^m nhưng bài thực tế m ≤ 3.
- **Nhất quán hướng**: sau khi đổi sang trượt, phải kiểm tra vận tốc tương đối đúng chiều đã giả sử (nếu không, chế độ đó không nhất quán ⇒ thử chế độ khác).
- **Ngưỡng**: điều kiện "vừa đủ" là **biên** giữa hai chế độ ⇒ đặt đẳng thức ở biên (ℓ₁₁).
- **Khuyến cáo [C]**: trong bài nhiều tiếp xúc ma sát, tính "lực cần" ở mỗi tiếp xúc trong chế độ tất cả nghỉ, rồi so từng tỉ số `f/(μ_s N)`; tiếp xúc có tỉ số vượt 1 sớm nhất khi tăng tải thường là tiếp xúc trượt trước. **Đây là heuristic** (tôi không chứng minh nó đúng cho mọi cấu hình); luôn kiểm tra lại toàn hệ ở bước 4.

### 6.6. Chiến lược chọn CHỖ (heuristic H1–H8) [C]

Đây là những mẹo chọn chỗ dựa trên cấu trúc, để giảm phụ thuộc trực giác. **Chưa được kiểm thử thống kê**, hãy xem như giả thuyết:

| H | Quy tắc | Lý do (theo cấu trúc) |
|---|---|---|
| H1 | Bắt đầu Newton ở vật có **ít lực ẩn nhất** | Mỗi phương trình có ít ẩn ⇒ dễ khử |
| H2 | Chỉ hỏi chuyển động chung ⇒ **coi cả hệ** (ℓ₁₅) | Lực nội khử nhờ Newton III |
| H3 | Cần lực tại **một điểm** trên dây/thanh ⇒ **cắt tại điểm đó** (ℓ₈) | Lực nội thành lực ngoài của hệ con |
| H4 | δ > 0 ⇒ tìm **ràng buộc chưa dùng** (dây, tiếp xúc, ròng rọc); nếu chỉ có ràng buộc vận tốc ⇒ **đạo hàm thêm một lần** | Thiếu ≈ quên ràng buộc |
| H5 | Hỏi theo **vị trí/quãng đường** (không hỏi thời gian) ⇒ **năng lượng hoặc `v dv/dx`** | Loại biến t |
| H6 | Hỏi theo **thời gian** ⇒ tích phân theo t hoặc tách biến theo t | Giữ t |
| H7 | Bài **cực trị/ngưỡng** ⇒ đặt **đạo hàm = 0 hoặc bất đẳng thức tại biên** | Ngưỡng nằm ở biên chế độ |
| H8 | Có **đối xứng** (lực xuyên tâm, tịnh tiến, quay) ⇒ dùng **đại lượng bảo toàn** tương ứng (mômen động lượng `L = m r² θ̇`, xung lượng theo phương không lực) | Hạ bậc ODE |

**Mẹo chọn HQC (H9)**: hỏi "có vật nào **gia tốc đã biết** để gắn HQC không?" Nếu có ⇒ ℓ₁₄ có thể biến bài động thành bài tĩnh (a' = 0). Nếu gia tốc chưa biết ⇒ cứ HQC quán tính.

### 6.7. Toán tử "nặng": KKT (ma trận ràng buộc) và Lagrange — "Nodal Analysis của cơ học" [A]/[B]

Đây là câu trả lời trực tiếp cho câu hỏi "có thuật toán bỏ qua bước tìm chỗ không?"

**(a) Ma trận ràng buộc (KKT).** Cho **tọa độ Descartes** `q ∈ ℝⁿ` của mọi chất điểm, khối lượng `M = diag(m…)`, lực cấu thành `F(q, q̇, t)`. Ràng buộc holonomic `φ_k(q) = 0` (k = 1…K). Đặt `A = ∂φ/∂q` (ma trận K×n).
```
M q̈ = F + Aᵀ λ                 (lực liên kết = Aᵀ λ, λ = nhân tử Lagrange)
A q̈ = − (dA/dt) q̇              (đạo hàm hai lần của φ = 0)
```
Viết một hệ tuyến tính duy nhất (ẩn: q̈ và λ):
```
[ M   −Aᵀ ] [ q̈ ]   [  F         ]
[ A    0  ] [ λ  ] = [ −Ȧ q̇      ]
```
- **Pre**: (i) ràng buộc holonomic (hoặc tuyến tính theo vận tốc), (ii) **lực liên kết lý tưởng**: song song `∇φ`, tức **không ma sát**, (iii) `A` **đủ hạng hàng** (các ràng buộc độc lập).
- Toán tử này **không cần bạn tìm chỗ**: tất cả vật và mọi ràng buộc đều vào hệ; giải xong có cả gia tốc lẫn **mọi lực liên kết** (T, N).
- **Kiểm chứng [B] (con lắc)**: `φ = x² + y² − L²`, `A = (2x, 2y)`, `Ȧ q̇ = 2(vₓ² + v_y²)`. Giải ra `λ = m (g y − v²)/(2 L²)`. Lực liên kết `Aᵀλ` có thành phần theo bán kính bằng `2 λ L` (âm ⇒ hướng vào tâm), nên độ lớn lực căng là `T = −2 λ L = m (g cos θ + v²/L)` khi `y = −L cos θ`, khớp công thức con lắc đơn ở 4.4.

**(b) Lagrange (tọa độ suy rộng).** Chọn **tọa độ suy rộng** `q₁…q_f` (f = số bậc tự do) sao cho ràng buộc **tự thỏa** ⇒ lực liên kết (lý tưởng) **biến mất khỏi phương trình**:
```
L = T − V
d/dt (∂L/∂q̇_i) − ∂L/∂q_i = Q_i    (Q_i = lực suy rộng không có thế, ví dụ ma sát trượt, cản)
```
- **Pre**: ràng buộc holonomic; lực liên kết **không sinh công ảo** (lý tưởng); nếu muốn lực liên kết (T, N) phải quay lại nhân tử λ.
- **Kiểm chứng [B] (ròng rọc động, ví dụ E1)**: chỉ một tọa độ y (độ chìm của ròng rọc), `T = ½(m₂ + 4m₁) ẏ²`, `V = −(m₂ − 2m₁) g y` ⇒ `(m₂ + 4m₁) ÿ = (m₂ − 2m₁) g`, đúng kết quả Newton.
- **Ưu điểm**: một dòng/tọa độ, **không tìm chỗ**. **Nhược**: không cho lực liên kết miễn phí; ma sát cần Q_i; cần tính T, V chính xác.

**(c) So sánh với Nodal Analysis (theo ý bạn):**

| | Mạch tuyến tính | Cơ học chất điểm có ràng buộc |
|---|---|---|
| Vấn đề tìm kiếm | Áp KCL/Ohm ở đâu? | Áp Newton ở đâu, ràng buộc nào? |
| Thuật toán mạnh | Nodal Analysis (ẩn = điện thế nút) | **KKT** (ẩn = q̈, λ) hoặc **Lagrange** (ẩn = q) |
| Pre | mạch tuyến tính tĩnh | ràng buộc lý tưởng, holonomic |
| Cái được "bỏ qua" | chọn vòng/nút | chọn hệ con, chọn cắt, khử lực liên kết |

**Cảnh báo pháp lý/thực tế [không chắc chắn]**: tôi **không** biết quy định cụ thể của từng kỳ thi (ví dụ được dùng phương pháp Lagrange đến mức nào). Cần tự kiểm tra. Về Toán, chúng hợp lệ; về chấm điểm, phụ thuộc thể lệ và barem.

### 6.8. Cây quyết định khi ODE không tự giải được (S5/S6) [C]
```
Lực phụ thuộc gì?
├─ chỉ t          → tích phân trực tiếp (ℓ₁₆)
├─ chỉ v          → tách biến (ℓ₁₃): theo t  (hỏi v(t), t)
│                                        theo x  (hỏi v(x), x) dùng ℓ₁₂
├─ chỉ x          → năng lượng (ℓ₁₇) hoặc ℓ₁₂;  nhỏ ⇒ tuyến tính hóa (ℓ₁₉)
├─ x và v tuyến tính (lò xo + cản tuyến tính)
│                 → ODE hệ số hằng: thử x = e^{λt} ⇒ phương trình đặc trưng
│                    (dao động tắt dần: ω₀² = k/m, γ = b/2m; γ<ω₀ dao động, γ>ω₀ quá tắt)
├─ t và x (cưỡng bức) → nghiệm = nghiệm riêng + nghiệm thuần nhất (ngoài phạm vi phần này)
└─ không giải tích được → điều kiện biên + đại lượng bảo toàn; hoặc tuyến tính hóa; hoặc số
```

### 6.9. Tự phê bình khung tìm kiếm [C]
- **Đã làm**: (i) tập toán tử ℓ với Pre/Post cho Động lực học chất điểm; (ii) tiêu chí δ cho "bước có ý nghĩa"; (iii) thuật toán chế độ; (iv) KKT/Lagrange làm phương pháp mạnh.
- **Chưa làm/không thể khẳng định**: (i) chưa thử trên ngân hàng đề thi thật, nên chưa biết tỉ lệ bài được "giải nhờ thư viện"; (ii) H1–H9 là heuristic; (iii) **bước chọn mô hình** (Vấn đề 1) vẫn cần hiểu vật lý, không thể tự động hóa hoàn toàn; (iv) bài IPHO thường **trộn** động lực học với nhiệt/điện/quang, thư viện này chỉ phủ phần cơ.
- **Kiểm định (falsifiable)**: lấy 30–50 bài cũ, với mỗi bài ghi dãy `(ℓ, CHỖ)` đã dùng (mẫu ở mục 9). Nếu có bài mà lời giải dùng toán tử **ngoài** thư viện ⇒ bổ sung toán tử đó. Nếu nhiều bài cần cùng một toán tử mới ⇒ thư viện thiếu. Thư viện đúng nghĩa là nó **hội tụ** (ngày càng ít toán tử mới).

---

## 7. VÍ DỤ CÓ LỜI GIẢI CẤU TRÚC (mỗi ví dụ ghi rõ cấu trúc, CHỖ, toán tử) [B]

### E1. Ròng rọc động (S2)
**Đề**: dây không dãn, nhẹ; một đầu buộc vào trần, dây đi xuống vòng qua ròng rọc động nhẹ P (treo m₂), đi lên qua ròng rọc cố định F ở trần, đầu kia buộc m₁ (rơi xuống). Tìm gia tốc của P và lực căng T.

**Mô hình (P1–P8)**: chiều dương **xuống** cho cả hai vật. Ẩn: `a_P`, `a₁`, `T`. Ròng rọc nhẹ ⇒ T đồng nhất; ròng rọc động nhẹ ⇒ lực từ vật m₂ lên P bằng lực dây kéo P lên **2T**.

**CHỖ và toán tử**:
- (ℓ₁, m₂): `m₂ g − 2T = m₂ a_P` (vì tổng lực lên P bằng 0 ⇒ lực từ m₂ xuống P = 2T; vật m₂ chịu 2T kéo lên).
- (ℓ₁, m₁): `m₁ g − T = m₁ a₁`.
- (ℓ₅, dây): chiều dài `L = 2 y_P + y₁ + hằng` ⇒ `a₁ = −2 a_P`.
- Đếm: 3 ẩn (a_P, a₁, T), 3 phương trình ⇒ δ = 0.

**Giải**: thế `a₁ = −2a_P`: `T = m₁ g + 2 m₁ a_P`. Vào phương trình 1:
```
a_P = (m₂ − 2 m₁) g / (m₂ + 4 m₁),      T = 3 m₁ m₂ g /(m₂ + 4 m₁)
```
**Kiểm tra**: `m₂ = 2m₁ ⇒ a = 0, T = m₁ g` ✓ (cân bằng). `m₂ → ∞`: `a_P → g`, `a₁ = −2g`, `T → 3 m₁ g = m₁(g + 2g)` ✓. `m₁ → ∞`: `a₁ = −2 a_P → g` (m₁ rơi tự do) ✓. **Một dòng bằng Lagrange** (6.7b) cho cùng kết quả.

### E2. Nêm chuyển động (S2 + S9: chọn HQC)
**Đề**: vật m trượt **không ma sát** trên nêm khối lượng M, góc nghiêng α; nêm trượt **không ma sát** trên sàn ngang. Tìm gia tốc nêm, gia tốc tương đối, phản lực.

**Mô hình**: mặt nghiêng đi lên về bên trái ⇒ phản lực pháp tuyến lên vật hướng lên phải; nêm bị đẩy về **trái** với gia tốc A. Chọn **HQC gắn nêm** (H9: nêm có gia tốc A **ẩn**, nhưng ta thêm phương trình cho nêm ở HQC quán tính).

**CHỖ/toán tử**:
- (ℓ₁, nêm, HQC quán tính, chiếu ngang): `M A = N sin α` (nêm chỉ chịu thành phần ngang của N; trọng lực và phản lực sàn theo phương đứng).
- (ℓ₁+ℓ₁₄, vật, HQC nêm, chiếu **pháp tuyến**): vật không có gia tốc vuông góc mặt ⇒ `N − m g cos α + m A sin α = 0`.
- (ℓ₁+ℓ₁₄, vật, HQC nêm, chiếu **dọc mặt**): `m a_rel = m g sin α + m A cos α`.
- Ẩn: N, A, a_rel — 3 phương trình ⇒ δ = 0.

**Giải**:
```
N = M m g cos α /(M + m sin²α)
A = m g sin α cos α /(M + m sin²α)
a_rel = (M + m) g sin α /(M + m sin²α)
```
**Kiểm tra**: `M → ∞`: `A → 0`, `a_rel → g sin α`, `N → m g cos α` ✓ (nêm cố định). `m → 0`: `A → 0` ✓. Kiểm tra bằng HQC quán tính (theo phương ngang và đứng của vật): hai phương trình đúng (sympy: hiệu = 0). [B]

### E3. Hai vật, ma sát và chuyển chế độ (S3)
**Đề**: vật m đặt trên tấm M, hệ số ma sát giữa hai vật μ (μ_s = μ_k), sàn nhẵn. (a) Lực F ngang lên **M**: tìm ngưỡng F để m trượt trên M, và gia tốc mỗi vật khi trượt. (b) F lên **m**.

**Thuật toán chế độ (6.5)**:
- Giả thiết **nghỉ**: `a = F/(M+m)` (ℓ₁₅). Ma sát nghỉ lên m: `f = m a = m F/(M+m)`. Kiểm tra `f ≤ μ m g` ⇒ **`F ≤ μ (M+m) g`**.
- Nếu `F > μ(M+m) g` ⇒ **trượt**: `f = μ m g` (lên m, cùng chiều F) ⇒ `a_m = μ g`, `M a_M = F − μ m g`. **Nhất quán**: `a_M > a_m ⇔ F > μ(M+m) g` ✓ (M đi nhanh hơn m, đúng hướng giả thiết).
- (b) F lên **m**: nghỉ chung `a = F/(M+m)`; ma sát lên M (phát động M): `f = M a = MF/(M+m) ≤ μ m g` ⇒ **`F ≤ μ m g (M+m)/M`**. Khi M → ∞: `F ≤ μ m g` ✓.
- **Nhận xét cấu trúc**: cả hai ngưỡng là **biên chế độ** (ℓ₁₁: `|f| = μ_s N` tại đó); hai ngưỡng khác nhau vì **CHỖ** (tác dụng F ở đâu) đổi **lực nghỉ cần thiết**.

### E4. Trượt trên mặt cầu, điều kiện rời mặt (S4)
**Đề**: vật nhỏ trượt không ma sát từ đỉnh mặt cầu nhẵn bán kính R (v₀ ≈ 0). Tìm vị trí rời mặt.

- (ℓ₃, pháp tuyến): `m g cos θ − N = m v²/R`.
- (ℓ₁₇, năng lượng): `v² = 2 g R (1 − cos θ)` (N vuông góc chuyển dời ⇒ không sinh công).
- Hai phương trình hai ẩn (N, v²) ⇒ `N = m g (3 cos θ − 2)`.
- (ℓ₁₁): rời mặt ⇔ `N = 0` ⇒ **`cos θ = 2/3`** [B].
- Ghi chú cấu trúc: đây là ví dụ **CH-d** (điểm đặc biệt N = 0) kết hợp năng lượng (v² từ ℓ₁₇), không cần giải ODE theo θ.

### E5. Ném lên với lực cản bậc hai (S5)
**Đề**: ném thẳng đứng lên với v₀, lực cản `k₂ v²`. Tìm độ cao cực đại.

- (ℓ₁): `m dv/dt = −m g − k₂ v²`. Đặt `v_T² = m g/k₂` ⇒ `dv/dt = −g (1 + v²/v_T²)`.
- (ℓ₁₂: hỏi độ cao ⇒ dùng `v dv/dx`): `v dv/dx = −g (1 + v²/v_T²)`.
- (ℓ₁₃): `∫₀^{v₀} v dv /(1 + v²/v_T²) = g H` ⇒ `(v_T²/2) ln(1 + v₀²/v_T²) = g H`.
- **`H = (v_T²/(2g)) ln(1 + v₀²/v_T²)`** [B].
- Kiểm tra: `v_T → ∞`: `ln(1+u) ≈ u` ⇒ `H → v₀²/(2g)` ✓. Số: `g = 9,8`, `v_T = 20`, `v₀ = 30` ⇒ `H = 24,05 m` (tích phân số khớp).
- **CHỖ**: bài này *không* có ràng buộc; toàn bộ độ khó nằm ở việc **chọn biến độc lập x** thay vì t.

### E6. Hạt trong ống quay (S9)
**Đề**: ống thẳng nhẵn quay đều quanh trục vuông góc, tốc độ góc ω; hạt m trong ống, ở r₀ với ṙ(0) = 0. Tìm r(t) và phản lực.

- HQC gắn ống (quay đều, ℓ₁₄). Theo ống: `m r̈ = m ω² r` (ly tâm). Vuông góc ống (không chuyển động): `N = 2 m ω ṙ` (Coriolis cân bằng).
- Giải: `r̈ = ω² r`, `r(0) = r₀, ṙ(0) = 0` ⇒ **`r = r₀ cosh ωt`**, **`N = 2 m ω² r₀ sinh ωt`**. [B]
- Kiểm tra bằng HQC quán tính (ℓ₃ cực): `a_r = r̈ − r ω² = 0` (không lực xuyên tâm), `a_θ = 2 ṙ ω = N/m` ✓ (hai HQC nhất quán).
- **Lưu ý cấu trúc**: nghiệm là **cosh** (chuyển động tăng theo hàm mũ) vì hằng số tuyến tính hóa là **+ω²** (không ổn định), khác `−ω²` của dao động điều hòa.

---

## 8. BẪY THƯỜNG GẶP VÀ KIỂM TRA SAU KHI GIẢI

### 8.1. Danh sách bẫy [A]/[C]
1. Vẽ **lực hướng tâm** như một lực thật.
2. Cộng **phản lực (Newton III)** vào cùng vật với tác dụng của nó (chúng đặt lên hai vật khác nhau).
3. Dùng `f = μN` cho ma sát **nghỉ**.
4. Cho rằng `N = m g cos α` khi vật có gia tốc vuông góc mặt (nêm chuyển động, thang máy, mặt cong).
5. Coi T **hai bên ròng rọc có khối lượng** bằng nhau.
6. Dùng **`F = d(mv)/dt`** cho khối lượng biến thiên bừa bãi.
7. **Ràng buộc gia tốc dây xiên**: quên thành phần `v²/l`.
8. **Chiều dương không nhất quán** giữa các vật nối dây (lỡ giả sử chiều chuyển động sai; dấu kết quả sẽ sửa, nhưng phải **nhất quán** trong ràng buộc).
9. Kết quả **T < 0**, **N < 0**, hoặc `|f| > μN` mà không đổi chế độ.
10. **Lẫn hai HQC** trong cùng một phương trình (a tuyệt đối với a' tương đối).
11. Thêm **lực quán tính có phản lực** (không có).
12. Lấy `g = const` khi độ cao lớn.
13. Tuyến tính hóa nhưng **quên điều kiện biên độ nhỏ** trong đáp số.
14. Bỏ **ma sát nhưng dùng năng lượng bảo toàn** (sai) hoặc quên công của ma sát.
15. Dùng `Σ F_n = m v²/R` với R là bán kính vòng cong hình học thay vì **bán kính cong ρ** của quỹ đạo.
16. **Quên điều kiện đầu**: ODE bậc hai cần 2 điều kiện.

### 8.2. Các phép kiểm tra sau khi giải [C]
| Phép kiểm | Cách làm | Bắt được lỗi nào |
|---|---|---|
| **Thứ nguyên** | Mỗi biểu thức có thứ nguyên đúng | Sai mũ, quên g, thiếu m |
| **Giới hạn** | `M → ∞`, `m → 0`, `μ → 0`, `α → 0/90°`, `t → ∞` | Sai cấu trúc công thức |
| **Trường hợp đã biết** | Rút về Atwood, mặt phẳng nghiêng, rơi tự do | Sai hệ số |
| **Dấu/bất đẳng thức** | `T ≥ 0, N ≥ 0, |f| ≤ μ_s N` | Sai chế độ |
| **Bảo toàn** | Năng lượng (nếu không ma sát), động lượng theo phương không lực | Sai phương trình |
| **Hai cách giải** | Giải trong hai HQC / hai hệ tọa độ | Sai lực quán tính |
| **Số** | Thay số, tích phân số | Sai đại số |

---

## 9. LỘ TRÌNH LUYỆN TẬP, MẪU "THẺ CẤU TRÚC", VÀ PHẠM VI CHƯA PHỦ

### 9.1. Mẫu "thẻ cấu trúc" để ghi mỗi bài đã giải [C]
```
Bài: ______ (nguồn / độ khó)
Mô hình M: O=… ; V=… ; L=… ; C=… ; Q=… ; I=…
Cấu trúc: S? (S1…S9), số bậc tự do f, số ràng buộc k, δ ban đầu
Dãy (ℓ, CHỖ): (ℓ__, CH-_ …), (ℓ__, CH-_ …), …
Chế độ/điều kiện đặc biệt: …
Bẫy đã gặp: …
Kết quả tổng quát + kiểm tra giới hạn: …
Toán tử NGOÀI thư viện đã cần: … (nếu có ⇒ bổ sung 6.3)
```

### 9.2. Bậc thang luyện tập (theo cấu trúc, không theo số đề) [C]
1. **Nền**: S1, S2 đơn giản (Atwood, mặt phẳng nghiêng, hai vật nối dây); FBD 100% đúng; đếm δ.
2. **HSG cấp tỉnh/thành → HSGQG cơ bản**: S2 với ròng rọc động, S3 (nhiều tiếp xúc ma sát, ngưỡng), S4 (vòng tròn, con lắc, rời mặt), S5 (cản tuyến tính, v_T), S9(a) (thang máy, nêm).
3. **HSGQG nâng cao**: S2+S9 (nêm/vật chuyển động, HQC ẩn), S8 (dây xích, băng chuyền, tên lửa), S9(b) (ống quay, mặt quay, Trái Đất), ma sát dây Euler–Eytelwein, S6 với ma sát khô.
4. **Mức IPHO (chỉ phần cơ)**: kết hợp nhiều cấu trúc trong một bài (ví dụ ma sát + HQC quay + dao động nhỏ + năng lượng), yêu cầu **phân tích chế độ** và **đánh giá bậc độ lớn/xấp xỉ có kiểm tra**; dùng KKT/Lagrange để tự kiểm.

### 9.3. Phần cần đào sâu thêm (nằm ngoài phạm vi này) — tôi thẳng thắn liệt kê
- **Chuyển động trong trường xuyên tâm/Kepler** và **hấp dẫn** (bảo toàn mômen động lượng, thế hiệu dụng).
- **Dao động** (tắt dần, cưỡng bức, cộng hưởng, dao động ghép).
- **Các định luật bảo toàn** đầy đủ và **va chạm**.
- **Vật rắn** (mômen quán tính, lăn không trượt).
- **Cơ học giải tích** (Lagrange–Hamilton đầy đủ, ràng buộc phi holonomic).
- **Phương pháp số** cho bài không giải tích.

### 9.4. Tài liệu tham khảo gợi ý (tôi gợi ý theo hiểu biết chung; hãy tự kiểm chứng nội dung và phiên bản) [không chắc chắn về chi tiết]
- D. Kleppner, R. Kolenkow — *An Introduction to Mechanics* (Newton, HQC phi quán tính, khối lượng biến thiên).
- D. Morin — *Introduction to Classical Mechanics: With Problems and Solutions* (bài tập từ dễ đến rất khó, nhiều ví dụ ma sát/dây).
- L. D. Landau, E. M. Lifshitz — *Mechanics* (khung Lagrange).
- H. Goldstein — *Classical Mechanics* (Lagrange, ràng buộc).
- Đề và lời giải của HSGQG/IPHO các năm (tự xây "ngân hàng thẻ cấu trúc" để kiểm định thư viện 6.3).

### 9.5. Tóm tắt một trang (để ôn nhanh) [C]
1. **Cấu trúc chung**: `m a = ΣF` + ràng buộc + bất đẳng thức chế độ + điều kiện đầu. ODE bậc 2 hoặc DAE.
2. **Đếm**: N·d gia tốc + k lực liên kết ⇔ N·d Newton + k ràng buộc. Lệch ⇒ mô hình sai.
3. **Lực**: cấu thành (biết hàm) vs liên kết (ẩn, có bất đẳng thức).
4. **Quy trình**: đọc ⇒ mô hình ⇒ HQC/trục ⇒ FBD ⇒ ràng buộc + điều kiện ⇒ đếm δ ⇒ nhận diện S? ⇒ toán tử ⇒ giải ⇒ kiểm.
5. **Công cụ mạnh nhất** khi hệ phức tạp: **KKT/Lagrange**. Khi hệ đơn giản: chọn hệ con + ràng buộc dây.
6. **Chế độ**: giả thiết ⇒ giải ⇒ kiểm bất đẳng thức ⇒ đổi nhánh.
7. **HQC phi quán tính**: chỉ đổi biến; lực quán tính không có phản lực; Coriolis không sinh công.
8. **Kiểm**: thứ nguyên, giới hạn, dấu, hai cách giải.
