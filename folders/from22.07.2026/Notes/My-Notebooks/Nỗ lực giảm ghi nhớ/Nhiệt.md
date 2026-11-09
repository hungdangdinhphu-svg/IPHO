# HẠT NHÂN SINH (Generative Kernel) cho Nhiệt học HSGQG/IPhO

> Mục tiêu: thay vì nhớ T01–T17 + X1–X6 (~23 "công cụ", hàng trăm công thức), chỉ cần nhớ
> **~12 nguyên lý gốc** + **~6 thao tác suy luận**. Mọi công thức trong file nhiệt_hoc.md
> đều là **hệ quả** của (nguyên lý gốc) × (thao tác). Phần cuối có "bảng tra" chỉ ra
> đúng tổ hợp nào tạo ra đúng công cụ nào, và vài ví dụ suy luận sống để bạn tự kiểm tra tốc độ.

---

## PHẦN I — 12 NGUYÊN LÝ GỐC (không thể suy ra từ cái khác, phải thuộc)

Đây là "tiên đề". Tất cả T01–T17/X1–X6 là **tổ hợp** của các dòng này. Học 12 dòng này
kỹ hơn bất cứ gì khác trong tài liệu.

**G1. Nguyên lý 1 (bảo toàn năng lượng).**
`dU = δQ − δW`, với `U` là hàm trạng thái (không phụ thuộc đường đi), `Q, W` phụ thuộc đường.
→ Hệ quả tức thì: mọi "sổ cái năng lượng" chỉ là viết lại G1 cho một hệ con cụ thể.

**G2. Nguyên lý 2 (entropy).**
`S` là hàm trạng thái; với hệ cô lập `ΔS_tot ≥ 0` (`=` khi thuận nghịch).
Cách tính `ΔS` của một đoạn bất thuận nghịch: **bịa một đường thuận nghịch tưởng tượng** nối
cùng hai trạng thái đầu–cuối, rồi tích phân `δQ_rev/T` trên đường đó.
→ Hệ quả: Carnot, hiệu suất cực đại, công mất, mọi "có thể/không thể xảy ra".

**G3. Phương trình trạng thái khí lý tưởng.**
`pV = NkT` (hạt không tương tác, chỉ va chạm đàn hồi, loãng: `n·d³ ≪ 1`).
→ Mọi công thức khí lý tưởng (T06) chỉ là G3 viết cho từng phần khí + ràng buộc hình học/cơ học.

**G4. Định lý phân bố đều (equipartition).**
Mỗi bậc tự do bậc hai trong năng lượng (động năng tịnh tiến theo 1 trục, quay, dao động…)
đóng góp trung bình `(1/2)kT` vào nội năng, **khi cân bằng nhiệt cổ điển**.
→ `U = (i/2)NkT`, `C_V = iR/2`, `C_p = C_V+R`, `γ=1+2/i` — tất cả chỉ là đếm bậc tự do `i`.

**G5. Cơ chế vi mô của áp suất (mô hình va chạm).**
Áp suất = động lượng truyền cho tường mỗi đơn vị diện tích·thời gian, từ các hạt có hình chiếu
vận tốc pháp tuyến `v_n` chạm tường trong "hình trụ xiên" thể tích `v_n·dt·dA`.
→ Từ đây suy ra: `p=(1/3)nm⟨v²⟩`, công thức tường di động (đoạn nhiệt vi mô), dòng hạt qua lỗ
(effusion), áp suất chùm hạt phản xạ/hấp thụ. **Không cần nhớ riêng từng công thức — chỉ cần
dựng lại hình trụ va chạm mỗi lần.**

**G6. Phân bố Maxwell–Boltzmann.**
`f(v) ∝ e^{-mv²/2kT}` (vận tốc), `n(z) ∝ e^{-U(z)/kT}` (thế năng, dạng Boltzmann tổng quát).
Mọi "giá trị trung bình" (`v̄, v_rms, ⟨ε⟩`, dòng hạt, khí quyển đẳng nhiệt theo độ cao…) chỉ là
**một tích phân Gauss/Gamma** trên hàm mũ này với trọng số khác nhau (trọng số theo số hạt vs
theo dòng chảy qua một mặt → khác nhau đúng 1 hệ số `v_n`, đây là nguồn của mọi "bẫy 2kT vs
3kT/2").

**G7. Cân bằng pha = cân bằng hoá thế / cân bằng áp suất hơi.**
Hai pha cùng tồn tại ⇔ cùng `T`, và `p_hơi = p_sat(T)` (hàm chỉ của `T`). Đường `p_sat(T)` tuân
theo một ODE sinh ra từ chính G1+G2 áp dụng cho một chu trình Carnot vi phân *bắc qua* đường
chuyển pha (xem Phần III, mục suy Clausius–Clapeyron).
→ Mọi hiện tượng "bão hoà / ngưng tụ / sôi / độ ẩm / Clapeyron–Clausius" chỉ là đọc lại G7
theo các biến khác nhau.

**G8. Luật Fourier + bảo toàn năng lượng cục bộ.**
`q = −κ∇T` (thông lượng nhiệt tỉ lệ gradient). Kết hợp với "năng lượng tích trong thể tích
`dV` thay đổi = thông lượng ròng vào" (G1 viết cho một thể tích vi phân) → **phương trình
nhiệt** `ρc ∂T/∂t = ∇·(κ∇T)`. Mọi bài dẫn nhiệt (mạng nút, lát vi phân, Stefan, điện trở nhiệt)
là trường hợp riêng của hai dòng này.

**G9. Năng lượng bề mặt.**
Mặt phân cách có năng lượng `E=σ·A`; hệ cân bằng cơ học ⇔ cực tiểu hoá `E_tổng` dưới ràng buộc
thể tích (công ảo). Từ một dòng này suy ra Laplace `Δp=σ(1/R₁+1/R₂)`, Jurin, Young, Kelvin —
không cần nhớ riêng từng cái.

**G10. So sánh thang thời gian/độ dài quyết định xấp xỉ nào dùng được (không phải trực giác —
là phép so sánh có thể tính).**
`τ_cơ (L/v_âm)` vs `τ_quá trình` → quasi-static cơ học hay không.
`τ_nhiệt (L²/D)` vs `τ_quá trình` → đẳng nhiệt hay đoạn nhiệt.
`λ` (quãng đường tự do) vs `L` hệ → liên tục (Kn≪1) hay phân tử tự do (Kn≫1).
→ Đây là "công tắc" chọn giữa: Poisson vs bảo toàn năng lượng; Fourier vs effusion;
thuỷ động vs động học phân tử. **Một phép so sánh, không phải một danh sách từ khoá.**

**G11. Ràng buộc hình học–cơ học của hệ nhiều phần.**
Mọi vật di động (pittông, cột chất lỏng, giọt, mặt băng) phải thoả **cân bằng lực tức thời**
(hoặc Newton nếu không cân bằng); mọi vách kín bảo toàn số hạt riêng của nó; `V` các phần cộng
lại bằng `V_tổng`. Đây không phải "công cụ Nhiệt" — là cơ học/hình học lớp phủ lên trên, nhưng
chiếm hơn nửa số phương trình "bị thiếu" khi làm bài (ràng buộc ẩn).

**G12. Phân tích thứ nguyên / luật tỉ lệ.**
Khi chỉ cần *hình dạng* công thức (không cần hằng số chính xác), ghép các tham số có mặt sao
cho ra đúng thứ nguyên. Dùng để **tự kiểm tra** mọi công thức bạn vừa suy ra ở trên.

---

## PHẦN II — 6 THAO TÁC SUY LUẬN (cách "nhân" các nguyên lý gốc ra công thức)

Mỗi công cụ T0x = (một vài G-nào-đó) **đi qua** một trong 6 thao tác dưới. Thuộc 6 thao tác này
còn quan trọng hơn thuộc G1–G12, vì chúng là "động từ" biến tiên đề thành công thức cụ thể.

1. **Sổ cái bảo toàn** — chọn hệ con + khoảng thời gian, liệt kê vào/ra, viết G1 (năng lượng),
   hoặc bảo toàn số hạt/khối lượng, hoặc G2 dạng bất đẳng thức (entropy). *(→ T02, T04, T09,
   T10, T16, mọi "cân bằng nhiệt lượng kế")*
2. **Vi phân hoá (lấy lát mỏng)** — cô lập một phần tử `dz, dr, dx, dt, dA` và áp cân bằng lực
   hoặc cân bằng năng lượng lên riêng nó → ra một ODE/PDE. *(→ T07 khí quyển, T13 dẫn nhiệt,
   T16 effusion, T11 va chạm tường, T17 Clausius–Clapeyron)*
3. **Giới hạn Pre/Suf bằng số không thứ nguyên của G10** — quyết định công thức nào áp dụng
   được (quasi-static? đẳng nhiệt? liên tục?). *(→ chọn giữa Poisson/bảo toàn năng lượng; chọn
   giữa Fourier/effusion; mọi "Err" trong thư viện)*
4. **Cân bằng cơ học tức thời (G11) hoặc công ảo (G9)** — với vật di động hoặc mặt cong, viết
   lực = 0 (hoặc đạo hàm năng lượng theo biến hình học = 0). *(→ T15 sức căng bề mặt, cân bằng
   pittông/lò xo, mọi ràng buộc ẩn)*
5. **Giả thiết → kiểm tra → chia nhánh** — giả sử một trạng thái đơn giản (vd. "không có lỏng"),
   tính, so với ngưỡng, nếu vi phạm thì chuyển nhánh khác. *(→ T12 hơi ẩm, T04 nhiệt lượng kế có
   đổi pha, T14 hai pha vdW)*
6. **Đổi biến không thứ nguyên + tích phân trên phân bố (G6)** — khi cần một "giá trị trung
   bình" hoặc dạng rút gọn (vdW). *(→ T05 động học phân tử, T16 nâng cao, vdW rút gọn)*

---

## PHẦN III — VÍ DỤ SUY LUẬN SỐNG (tự kiểm tốc độ, không tra bảng)

**(a) Vì sao `C_V = iR/2`, `γ = 1+2/i`?**
G4 (mỗi bậc tự do `(1/2)kT`) → `U = N·(i/2)kT = ν(i/2)RT` → `C_V = dU/dT = νiR/2`, chia `ν`:
`C_V=iR/2`. Mayer `C_p=C_V+R` là định nghĩa `H=U+pV=U+RT` (mol) lấy đạo hàm. `γ=C_p/C_V=1+2/i`.
→ **0 công thức cần nhớ riêng**, chỉ cần G4 + định nghĩa `C_V, C_p, H`.

**(b) Vì sao `pV^γ = const` (Poisson)?**
Thao tác 1: viết G1 vi phân cho khí lý tưởng quasi-static cách nhiệt: `0 = νC_V dT + p dV`.
Thao tác 3: hợp lệ chỉ khi quasi-static (G10: `τ_cơ ≪ τ_quá trình`) + `Q=0`.
Dùng G3 (`pV=νRT` ⇒ `dT` qua `d(pV)`) thế vào, tách biến, tích phân ⇒ `pV^γ=const`.
→ Không cần nhớ 3 dạng Poisson (`pV^γ`, `TV^{γ-1}`, `T^γp^{1-γ}`) — chỉ nhớ *một* và đổi biến
bằng G3 khi cần dạng khác.

**(c) Vì sao hiệu ứng "tường di động → khí nóng lên khi nén" (nguồn gốc đoạn nhiệt vi mô)?**
G5: hạt bật khỏi tường di động với tốc độ `u` thì đổi vận tốc pháp tuyến `v→v+2u` (phản xạ
đàn hồi trong hệ quy chiếu tường). Mỗi va chạm hạt nhận thêm năng lượng ⇒ nén truyền năng lượng
vào khí ⇒ chính là vi mô của "nén đoạn nhiệt làm nóng". **Đây là lý do vật lý của Poisson**,
không phải trùng hợp toán học.

**(d) Vì sao dòng hạt thoát qua lỗ nhỏ mang năng lượng trung bình `2kT` chứ không phải `3kT/2`?**
G6 + thao tác 6: trọng số theo *dòng chảy* là `v_n·f(v)` (G5's hình trụ va chạm), không phải
`f(v)` (trọng số theo *số hạt tĩnh*). Tích phân Gauss với trọng số `v_n` thêm một bậc `v`,
làm lệch trung bình lên `2kT`. **Một con số sai lệch "3/2 vs 2" chỉ vì đổi trọng số tích phân —
nhớ *cơ chế* này thay vì nhớ hai con số.**

**(e) Vì sao đường Clausius–Clapeyron `dp/dT = L/(TΔv)`?**
Dựng một chu trình Carnot vi phân: hệ đi theo đường hai pha từ `(T,p)` đến `(T+dT,p+dp)`, nhận
nhiệt ẩn `L` ở `T`, nhả ở `T+dT` thấp hơn một lượng do hiệu suất Carnot `dT/T` (G2). Công sinh
ra trong chu trình nhỏ là `dp·Δv` (hình bình hành trên `p–V`, G1 cho công). Cân bằng
`W=η·Q_vào`: `dp·Δv = (dT/T)·L` ⇒ `dp/dT=L/(TΔv)`.
→ Một ví dụ mẫu: **G1+G2 áp cho một chu trình vi phân bắc qua ranh giới pha**, không phải công
thức rời rạc cần nhớ. Dùng chính kiểu suy luận này để tự tin khi quên công thức giữa phòng thi.

**(f) Vì sao mặt băng dày theo `x²∝t` (bài toán Stefan)?**
Thao tác 2 (vi phân hoá) trên G8: dòng nhiệt dẫn qua lớp băng dày `x` là `q=κΔT/x` (Fourier,
giả thiết quasi-steady — kiểm bằng G10 số Stefan `St≪1`). Năng lượng để đông thêm `dx` lớp băng
(diện tích `A=1`) là `ρλ dx` (ẩn nhiệt, G1). Cân bằng tại mặt di động: `ρλ dx/dt = κΔT/x`
⇒ ODE tách biến ⇒ `x²=2κΔT·t/(ρλ)`. **Không phải công thức Stefan "phải nhớ" — là G8 + thao
tác vi phân hoá đi qua một ràng buộc năng lượng tại biên di động.**

**(g) Vì sao `Δp=2σ/R` cho giọt, `4σ/R` cho bong bóng xà phòng?**
G9 + thao tác 4 (công ảo): `dE=σ dA`; cân bằng cơ học ⇔ `(Δp)dV=σ dA`. Giọt: `dV=4πR²dR`,
`dA=8πRdR` (một mặt) ⇒ `Δp=2σ/R`. Bong bóng xà phòng có **hai mặt** (trong+ngoài màng) ⇒ nhân
đôi ⇒ `4σ/R`. **Chỉ cần đếm số mặt phân cách — không nhớ hai công thức riêng biệt.**

---

## PHẦN IV — BẢNG TRA: TỪ KERNEL RA LẠI TOÀN BỘ THƯ VIỆN (để tự kiểm, không để học thuộc)

| Công cụ | = (G nào) × (thao tác nào) |
|---|---|
| T01 chuyển pha | G7 × (5) |
| T02 Nguyên lý 1 | G1 × (1) |
| T03 nhiệt kế | định nghĩa affine (không sinh từ G, phải nhớ: 2 điểm chuẩn) |
| T04 nhiệt lượng kế | G1 × (1)+(5), cộng với T01 |
| T05 động học cơ bản | G4 + G6 × (6) |
| T06 pV=νRT | G3 × (ghép G11 cho ràng buộc) |
| T07 lát khí quyển | G3+G11 × (2) |
| T08 Nguyên lý 1 cho khí | G1+G3+G4 × (3) để chọn công thức theo quá trình |
| T09 chu trình | T08 lặp lại trên từng cạnh + (1) tổng sổ cái |
| T10 Nguyên lý 2 | G2 × (1) |
| T11 áp suất động học | G5 × (2)+(6) |
| T12 hơi ẩm | G7 × (5) |
| T13 dẫn nhiệt | G8 × (2), mạng nút chỉ là rời rạc hoá G8 |
| T14 khí thực vdW | phương trình trạng thái mới (phải nhớ dạng vdW) + G1,G2,G9-style công ảo cho Maxwell |
| T15 sức căng bề mặt | G9 × (4) |
| T16 động học nâng cao | G5+G6 × (2)+(6), G10 chọn Kn |
| T17 Clapeyron–Clausius | G1+G2 × (2) qua chu trình Carnot vi phân (xem III.e) |
| X1 giãn nở nhiệt | định nghĩa hệ số (phải nhớ) |
| X2 bức xạ | định luật Stefan–Boltzmann (phải nhớ, không suy từ G1–G12) |
| X3 dòng dừng/tiết lưu | G1 viết cho thể tích kiểm soát hở (mở rộng của (1)) |
| X4 cơ học | = G11, không phải "Nhiệt" |
| X5 Joule | định luật điện (ngoài phạm vi kernel) |
| X6 thứ nguyên | = G12 |

---

## PHẦN V — PHẦN THỰC SỰ PHẢI THUỘC LÒNG (không suy ra được, danh sách cố ý ngắn)

Vì kernel chỉ sinh ra *cấu trúc*, một ít **con số và quy ước** vẫn phải nhớ trần trụi:

1. **Quy ước dấu**: chọn `ΔU=Q−W` (W khí sinh ra) hoặc `ΔU=A+Q` (A nhận vào) — chỉ cần chọn
   một và nhất quán, không có "đúng sai".
2. Hằng số: `R=8,314`, `k=1,381·10⁻²³`, `N_A=6,022·10²³`, `σ_SB=5,67·10⁻⁸`.
3. Số bậc tự do theo loại phân tử: đơn nguyên tử `i=3`, lưỡng nguyên tử thường `i=5` (`7` khi
   dao động kích hoạt), đa nguyên tử phi tuyến `i=6`. (Đây là input cho G4, không phải hệ quả.)
4. Dạng phương trình trạng thái khí thực: `(p+a/v²)(v−b)=RT` (vdW) — là một **mô hình thêm vào**
   G3, không suy ra từ G3.
5. Bảng nhận dạng đồ thị (P6 trong tài liệu gốc): đường thẳng qua gốc trên V–T ⇔ đẳng áp; trên
   p–T ⇔ đẳng tích; hyperbol trên p–V ⇔ đẳng nhiệt. (Thuần là đọc lại G3 trên các mặt phẳng
   khác nhau — có thể suy nhanh nhưng đáng thuộc để tiết kiệm thời gian thi.)
6. Các ngưỡng số không thứ nguyên "bao nhiêu là nhỏ" (G10): `Kn≲0,01`; `Bi≲0,1`; `St≪1` — đây
   là quy ước kinh nghiệm, không suy ra được, nhưng chỉ cần nhớ *có bốn số này tồn tại và vai
   trò của chúng* (chọn xấp xỉ), còn ngưỡng chính xác tra lại khi cần.

---

## PHẦN VI — QUY TRÌNH DÙNG KERNEL TRONG PHÒNG THI (rút gọn B0–B9 gốc)

```
1. Đọc đề → liệt kê hệ con, vách, giao diện (G11).
2. Với mỗi từ khoá mô tả quá trình ("chậm", "cách nhiệt", "đột ngột"...):
   dùng G10 (so sánh thang thời gian) để quyết định quasi-static? đẳng nhiệt? đoạn nhiệt?
   liên tục hay phân tử tự do? — KHÔNG tra từ điển, TỰ SUY bằng so sánh τ hoặc Kn.
3. Chọn 1-2 trong 6 thao tác (Phần II) khớp với loại câu hỏi:
   - cần số liệu cuối cùng của hệ kín  → sổ cái (1), dùng G1/G2/bảo toàn số hạt
   - có gradient không gian/biến thiên theo t → vi phân hoá (2), dùng G3/G5/G8
   - có vật/mặt cân bằng cơ học        → (4), dùng G9/G11
   - có hai pha / hai nhánh khả dĩ      → giả thiết-kiểm tra-nhánh (5), dùng G7
   - cần trung bình thống kê            → (6), dùng G6
4. Viết phương trình trực tiếp từ G-tương ứng (không tra công thức có sẵn trừ khi tiết kiệm
   thời gian — vd γ=1+2/i, hằng số ở Phần V).
5. Đếm ẩn vs phương trình (G11 thường là nguồn ràng buộc còn thiếu).
6. Kiểm bằng G12 (thứ nguyên) + G2 (η≤Carnot, ΔS_tot≥0) trước khi chốt.
```

---

### Tóm một câu

**12 nguyên lý gốc (G1–G12) + 6 thao tác (vi phân hoá, sổ cái, giới hạn Pre/Suf, công ảo/cân
bằng lực, giả thiết–kiểm tra–nhánh, tích phân trên phân bố) tạo ra toàn bộ T01–T17/X1–X6.**
Phần "phải nhớ trần trụi" chỉ còn ở Phần V (một trang). Khi quên công thức giữa bài, quay lại
hỏi: *đây là hệ quả của G-nào, qua thao tác-nào?* — rồi dựng lại, như các ví dụ ở Phần III.
