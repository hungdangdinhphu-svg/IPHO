# V. VẬT LÍ NGUYÊN TỬ VÀ HẠT NHÂN, VẬT LÍ HIỆN ĐẠI
## Giải quyết Vấn đề 1 (Thư viện công cụ + Tiền xử lý) & Vấn đề 2 (Hình thức hóa chuyển Vật Lý → Toán)

*Phạm vi: 8 mục trong bảng — Mẫu mô hình nguyên tử; Cấu trúc hạt nhân; Phản ứng hạt nhân & năng lượng liên kết; Hiện tượng phóng xạ; Tương đối tính & phép biến đổi Lorentz; Lượng tử ánh sáng & quang điện; Hiệu ứng Compton; Doppler tương đối tính.*

*Không giải Vấn đề 3 (không ra đáp số cụ thể) — chỉ dừng ở việc **nhận diện công cụ + tiền xử lý** (Vấn đề 1) và **dựng hệ phương trình Toán tương ứng** (Vấn đề 2), đúng như phạm vi nhiệm vụ đã giao.*

---

## PHẦN 0 — KHUNG QUY CHIẾU (nhắc lại để tài liệu tự-đủ)

Mỗi bài toán B được mô hình hóa bởi `M = (O, V, L, C, Q, I)`:

- **O** — ontology: hạt/hệ vật lý đang xét (photon, electron, hạt nhân, khung quy chiếu…) và quan hệ giữa chúng.
- **V** — biến: ẩn số, tham số, hằng số cần dùng.
- **L** — thư viện công cụ: mỗi `ℓ ∈ L` có `Dom(ℓ)` (miền hệ vật lý áp dụng được), `Pre(ℓ)` (điều kiện cần), `Suf(ℓ)` (điều kiện đủ để kết luận hợp lệ), `Post(ℓ)` (kết luận/phương trình sinh ra), `Err(ℓ)` (sai số nếu dùng xấp xỉ).
- **C** — ràng buộc: dữ kiện đề bài, điều kiện biên, bảo toàn…
- **Q** — câu hỏi cần trả lời.
- **I** — ánh xạ diễn giải giữa ký hiệu và đại lượng vật lý thật.

**Bài toán tìm kiếm** cho nhóm chuyên đề này luôn quy về: xác định **hệ đang ở chế độ nào** (cổ điển hay tương đối tính? một-electron hay nhiều electron? hai-vật hay dây chuyền phân rã?), vì đó chính là thứ quyết định `Dom` và `Pre` nào được thỏa — tức quyết định *CHỖ* nào dùng được công cụ nào.

### 0.1. Quy trình tiền xử lý CHUNG cho cả 8 chuyên đề (Vấn đề 1 — bước 0, làm trước khi tra thư viện riêng)

1. **Định danh hệ (O):** hạt nào tương tác với hạt nào (photon–electron, hạt α–hạt nhân con, electron–hạt nhân,…), đang ở khung quy chiếu nào (phòng thí nghiệm hay khối tâm).
2. **Kiểm tra thang vận tốc/năng lượng để chọn chế độ:**
   - Nếu có `v/c` xuất hiện tường minh, hoặc năng lượng hạt so được với `mc²` (electron: 0.511 MeV; proton: 938 MeV) → bắt buộc dùng bộ công cụ **tương đối tính** (mục A.5).
   - Nếu `v ≪ c` (hoặc đề cho "bỏ qua hiệu ứng tương đối tính") → dùng cơ học Newton cổ điển.
   - Photon **luôn** dùng `E=hf`, `p=h/λ=E/c` (không có "photon phi tương đối tính").
3. **Liệt kê các đại lượng bảo toàn khả dụng (C):** số khối `A`, điện tích `Z`, năng lượng toàn phần, động lượng (vectơ!), mômen động lượng, số lepton — bảo toàn cái nào phụ thuộc loại tương tác (phân rã, phản ứng hạt nhân, tán xạ).
4. **Xác định V (ẩn cần tìm) và Q (dạng đáp số):** năng lượng? vận tốc? bước sóng? góc? thời gian?
5. **Đối chiếu O vừa dựng với `Dom(ℓ)` của từng công cụ trong thư viện con tương ứng (Phần A.1–A.8)** để lọc ra tập công cụ khả dụng; sau đó kiểm `Pre`/`Suf` để biết dùng công cụ nào tại *CHỖ* nào.

Đây chính là bộ lọc bậc 1 (coarse filter) — nó không thay thế thư viện precondition chi tiết của từng công cụ (bậc 2, nêu bên dưới), nhưng loại được phần lớn nhầm lẫn "dùng công thức cổ điển cho hạt tương đối tính" hay ngược lại — lỗi phổ biến nhất ở mảng này.

---

## PHẦN A — VẤN ĐỀ 1: THƯ VIỆN CÔNG CỤ (L) THEO TỪNG CHUYÊN ĐỀ

### A.1. Các mẫu mô hình nguyên tử

**Dom chung của cả mục này:** nguyên tử/ion có đúng **1 electron** quanh hạt nhân điện tích `+Ze` (H, He⁺, Li²⁺,…), electron phi tương đối tính, bỏ qua spin và hiệu ứng nhiều hạt.

| Công cụ ℓ | Pre(ℓ) — điều kiện cần | Suf(ℓ) — điều kiện đủ | Post(ℓ) — kết luận | Err(ℓ) |
|---|---|---|---|---|
| Cân bằng lực Coulomb–hướng tâm | electron chuyển động tròn đều quanh hạt nhân đứng yên | khối lượng hạt nhân ≫ khối lượng electron (coi hạt nhân đứng yên) | `k Z e²/r² = m v²/r` | Nếu M hạt nhân không ≫ m: thay `m` bằng khối lượng rút gọn `μ = mM/(m+M)` |
| Định đề lượng tử hóa mômen động lượng (Bohr) | trạng thái dừng, quỹ đạo tròn | hệ một-electron, phi tương đối tính | `L = mvr = nħ`, n=1,2,3,… | Không áp dụng cho nguyên tử nhiều electron (tương tác electron–electron phá vỡ) |
| Hệ quả Bohr (từ 2 dòng trên) | hai điều kiện trên đồng thời thỏa | — | `r_n = n²ħ²/(k m e² Z)`; `E_n = −(k²me⁴Z²)/(2ħ²n²) = −13.6·Z²/n² (eV)` | Bỏ qua hiệu ứng tương đối tính và cấu trúc tinh tế (spin–quỹ đạo) |
| Điều kiện sóng de Broglie khép kín | dùng để *diễn giải lại* định đề Bohr (không phải công cụ độc lập, mà là cách "dựng" Pre của dòng trên) | quỹ đạo tròn, sóng vật chất giao thoa tăng cường | `2πr_n = nλ_dB = nh/(mv)` — tương đương `L=nħ` | như trên |
| Bức xạ/hấp thụ photon giữa 2 mức | nguyên tử chuyển giữa 2 trạng thái dừng xác định | năng lượng photon nhỏ so với `mc²` electron (luôn đúng ở đây) | `hf = |E_i − E_f|`; `1/λ = R_H Z² (1/n_f² − 1/n_i²)`, `R_H ≈ 1.097×10^7 m⁻¹` | — |
| Định luật Moseley (phổ tia X đặc trưng) | nguyên tử nhiều electron, electron lớp trong nhảy mức, có hiệu ứng chắn | dùng hằng số chắn σ thực nghiệm (σ≈1 cho vạch Kα) | `√f = a(Z − σ)` | Chỉ là công thức bán-thực nghiệm, `a`,`σ` không suy từ Bohr thuần túy |
| Franck–Hertz (định tính) | dùng để *xác nhận* tính rời rạc của mức năng lượng, không sinh phương trình định lượng trực tiếp trừ khi đề cho thế hãm | — | năng lượng kích thích = `eU` tại các đỉnh cách đều | — |

**"CHỖ" thường gặp (từ khóa nhận diện trong đề):** "nguyên tử/ion giống hydro", "bán kính quỹ đạo Bohr", "quang phổ vạch", "bước sóng dãy Lyman/Balmer/Paschen", "năng lượng ion hóa", "tia X đặc trưng".

**Tiền xử lý riêng:** (i) xác định `Z` của hạt nhân (H: Z=1, He⁺: Z=2,…); (ii) xác định 2 mức `n_i, n_f` liên quan; (iii) nếu đề nói "khối lượng hạt nhân hữu hạn/so sánh được với electron" → bắt buộc dùng khối lượng rút gọn `μ`, đây là bẫy Suf hay bị bỏ qua.

---

### A.2. Cấu trúc hạt nhân

| Công cụ ℓ | Pre(ℓ) | Suf(ℓ) | Post(ℓ) | Err(ℓ) |
|---|---|---|---|---|
| Ký hiệu hạt nhân & thành phần | biết `A` (số khối), `Z` (số proton) | — | `N = A − Z` (số neutron); hạt nhân `_Z^A X` | — |
| Công thức bán kính hạt nhân | hạt nhân coi gần đúng là khối cầu mật độ đều | phù hợp thực nghiệm tán xạ electron | `R = R₀A^{1/3}`, `R₀ ≈ 1.2 fm` | Sai lệch với hạt nhân biến dạng (không cầu), hạt nhân rất nhẹ |
| Hệ quả: mật độ hạt nhân không đổi | từ Post ở trên | — | `ρ = 3m_nucleon/(4πR₀³) ≈ const`, không phụ thuộc `A` | — |
| Độ hụt khối & năng lượng liên kết | biết khối lượng hạt nhân `M(A,Z)` (khối lượng thực đo, không phải tổng khối lượng nucleon) | dùng đơn vị khối lượng nguyên tử nhất quán (thường trừ luôn khối lượng electron nếu dùng khối lượng nguyên tử) | `Δm = [Zm_p + Nm_n] − M(A,Z)`; `E_b = Δm·c²` | Nếu đề cho khối lượng *nguyên tử* thay vì hạt nhân, phải cộng/trừ `Z·m_e` cho nhất quán |
| Năng lượng liên kết riêng | có `E_b` | — | `E_b/A` — đại lượng để so sánh độ bền giữa các hạt nhân (cực đại quanh `A≈56`, Fe) | Không dùng để so hai hạt nhân khác `A` xa nhau về ý nghĩa vật lý tuyệt đối |
| Công thức bán thực nghiệm khối lượng (Weizsäcker/SEMF) — mức nâng cao IPhO | cần ước lượng `E_b` khi không có bảng số liệu | các hằng số `a_V,a_S,a_C,a_A,δ` được cho trong đề (không cần nhớ) | `E_b = a_VA − a_SA^{2/3} − a_C Z(Z−1)/A^{1/3} − a_A(A−2Z)²/A + δ` | Chỉ là mô hình giọt chất lỏng, sai lệch quanh số magic |

**"CHỖ" thường gặp:** "bán kính hạt nhân", "độ hụt khối", "năng lượng liên kết riêng", "hạt nhân bền nhất", "mô hình giọt chất lỏng".

**Tiền xử lý riêng:** luôn hỏi *"đề cho khối lượng hạt nhân hay khối lượng nguyên tử?"* trước khi tính `Δm` — đây là *CHỖ* sai phổ biến nhất trong mục này.

---

### A.3. Phản ứng hạt nhân, năng lượng liên kết (áp dụng liên kết)

**Dom chung:** phản ứng dạng `a + X → Y + b` (hoặc phân hạch/nhiệt hạch), có thể cổ điển hoặc tương đối tính tùy động năng hạt tới.

| Công cụ ℓ | Pre(ℓ) | Suf(ℓ) | Post(ℓ) | Err(ℓ) |
|---|---|---|---|---|
| Bảo toàn số khối & điện tích | mọi phản ứng hạt nhân (không phân rã β liên quan lepton thì vẫn đúng cho A,Z) | — | `ΣA_trước = ΣA_sau`; `ΣZ_trước = ΣZ_sau` | Không bảo toàn số neutron/proton riêng lẻ (chỉ tổng) |
| Năng lượng phản ứng Q | biết khối lượng (hoặc năng lượng nghỉ) các hạt trước/sau | dùng cùng hệ đơn vị khối lượng | `Q = (Σm_trước − Σm_sau)c²` | Q>0: tỏa năng lượng (thuận lợi); Q<0: thu năng lượng (cần ngưỡng) |
| Bảo toàn động lượng + năng lượng toàn phần (dạng tổng quát, tương đối tính) | hệ kín, không ngoại lực | dùng khi động năng hạt tới so được với `mc²` | `Σp⃗_trước = Σp⃗_sau`; `ΣE_trước = ΣE_sau` với `E=√((pc)²+(mc²)²)` | — |
| Bảo toàn động lượng + động năng (giới hạn cổ điển) | `v ≪ c` cho mọi hạt | — | `Σp⃗ = Σm v⃗` (cổ điển); `ΣT_trước + Q = ΣT_sau` | Sai khi hạt tới có động năng cỡ MeV trên hạt nhẹ (ví dụ proton năng lượng cao) |
| Năng lượng ngưỡng phản ứng thu nhiệt (hạt tới bắn vào hạt bia đứng yên) | `Q<0`, cần tìm động năng tối thiểu của đạn để phản ứng xảy ra | khối tâm: sản phẩm sinh ra đứng yên trong hệ khối tâm ở ngưỡng | Cổ điển: `T_ngưỡng = −Q·(m_đạn + m_bia)/m_bia`; Tương đối tính: dùng bất biến `s=(ΣE)²−(Σp⃗c)²` tại ngưỡng bằng `(Σm_sảnphẩm·c²)²` | Công thức cổ điển sai đáng kể nếu đạn có `T` so được với `mc²` |
| Phân hạch / nhiệt hạch (trường hợp riêng của Q-value) | phân hạch: 1 hạt nhân nặng vỡ; nhiệt hạch: 2 hạt nhân nhẹ hợp | dùng đường cong `E_b/A` để biết chiều tỏa năng lượng | năng lượng tỏa ra = tổng `E_b` sản phẩm − tổng `E_b` ban đầu | — |

**"CHỖ" thường gặp:** "viết phương trình phản ứng", "tính năng lượng tỏa ra/thu vào", "năng lượng tối thiểu để phản ứng xảy ra", "phân hạch U-235", "phản ứng nhiệt hạch D-T".

**Tiền xử lý riêng:** (i) cân bằng phương trình phản ứng bằng `A,Z` trước; (ii) xác định khung quy chiếu đề cho (phòng thí nghiệm — bia đứng yên, hay khối tâm); (iii) kiểm tra thang năng lượng để chọn công cụ cổ điển hay tương đối tính (theo Phần 0.1, bước 2).

---

### A.4. Hiện tượng phóng xạ

| Công cụ ℓ | Pre(ℓ) | Suf(ℓ) | Post(ℓ) | Err(ℓ) |
|---|---|---|---|---|
| Định luật phân rã phóng xạ | quá trình phân rã ngẫu nhiên, độc lập từng hạt nhân, hệ chỉ có 1 đồng vị mẹ (không có mẹ nuôi con liên tục) | — | `N(t) = N₀e^{−λt}`; `λ = ln2 / T_{1/2}` | — |
| Độ phóng xạ (hoạt độ) | biết `N(t)` hoặc `λ` | — | `H(t) = λN(t) = H₀e^{−λt}` | — |
| Số hạt nhân con sinh ra (mẹ→con bền) | con không phóng xạ tiếp | bảo toàn tổng số hạt nhân ban đầu | `N_con(t) = N₀(1 − e^{−λt})` | Không dùng nếu con cũng phóng xạ (cần phương trình Bateman) |
| Chuỗi phân rã (mẹ→con→cháu,…), cân bằng thế kỷ/tạm thời | con cũng phóng xạ với `λ_2` | Cân bằng thế kỷ khi `λ_1 ≪ λ_2` (mẹ sống rất lâu so với con) | Cân bằng thế kỷ: `H_1 ≈ H_2` (hoạt độ mẹ = hoạt độ con) sau đủ lâu; tổng quát dùng nghiệm Bateman `N_2(t) = N₁⁽⁰⁾ λ₁/(λ₂−λ₁)·(e^{−λ₁t}−e^{−λ₂t})` | Nếu `λ_1` không ≪ `λ_2`, không có cân bằng thế kỷ, phải dùng nghiệm đầy đủ |
| Động học hai-vật cho phân rã α (hạt nhân mẹ đứng yên) | phân rã `X → Y + α`, mẹ đứng yên trước phân rã | phi tương đối tính (đúng với hầu hết phân rã α) | Bảo toàn động lượng: `p_α = p_Y` (độ lớn); bảo toàn năng lượng: `Q = T_α + T_Y`; suy ra `T_α = Q·M_Y/(M_Y+m_α)` (dùng `T=p²/2m`) | Nếu con ở trạng thái kích thích (phát thêm γ), phải trừ thêm năng lượng mức kích thích |
| Phổ liên tục phân rã β | có ≥3 hạt sau phân rã (hạt nhân con, electron/positron, neutrino) | — | Không thể dùng bảo toàn 2-vật; năng lượng electron trải phổ liên tục từ 0 đến `Q_β`; **không đòi hỏi tính cụ thể động năng electron** trừ khi hỏi giá trị cực đại (`T_e,max ≈ Q_β`, coi neutrino mang ~0 năng lượng) | — |
| Định tuổi phóng xạ (đồng vị mẹ–con bền, ví dụ đá) | biết tỉ số `N_con/N_mẹ` hiện tại, giả thiết mẫu ban đầu chỉ có mẹ | hệ kín (không thất thoát mẹ/con) | Từ `N_mẹ(t)` và `N_con(t)=N_{mẹ,0}−N_mẹ(t)` suy ra `t = (1/λ)ln(1 + N_con/N_mẹ)` | Sai nếu hệ không kín (rò rỉ khí, ví dụ đồng vị khí hiếm) |

**"CHỖ" thường gặp:** "chu kì bán rã", "hoạt độ phóng xạ", "tuổi mẫu vật/đá", "chuỗi phóng xạ tự nhiên", "cân bằng phóng xạ", "động năng hạt α phát ra".

**Tiền xử lý riêng:** đếm số hạt sinh ra sau phân rã — **đúng 2 hạt** (mẹ đứng yên) thì dùng động học 2-vật (Post ở dòng α); **≥3 hạt** (β) thì *không* được viết `T_e = Q` mà phải nhận diện đó là bài phổ liên tục.

---

### A.5. Tương đối tính, phép biến đổi Lorentz, thuyết tương đối hẹp

**Dom chung:** hai khung quy chiếu quán tính `S, S'` chuyển động tương đối với vận tốc `v` không đổi dọc một trục; áp dụng khi `v` so được với `c` (không thể bỏ qua `β=v/c`).

| Công cụ ℓ | Pre(ℓ) | Suf(ℓ) | Post(ℓ) | Err(ℓ) |
|---|---|---|---|---|
| Phép biến đổi Lorentz (tọa độ–thời gian) | 2 khung quán tính, trục `x` trùng phương chuyển động | 2 tiên đề Einstein (vận tốc ánh sáng bất biến, các định luật vật lý như nhau trong mọi khung quán tính) | `x' = γ(x−vt)`, `t' = γ(t − vx/c²)`, `γ=1/√(1−β²)` | Không áp dụng trực tiếp nếu chuyển động không dọc 1 trục (cần biến đổi tổng quát/ma trận) |
| Giãn thời gian | đo khoảng thời gian giữa 2 sự kiện xảy ra **cùng một vị trí** trong khung riêng (proper time `τ`) | — | `Δt = γΔτ` (khung ngoài đo thời gian dài hơn) | Nhầm lẫn phổ biến: áp dụng công thức khi 2 sự kiện không cùng vị trí trong khung riêng — phải quay lại dùng Lorentz đầy đủ |
| Co độ dài | đo chiều dài một thanh **dọc phương chuyển động**, `L₀` đo trong khung thanh đứng yên (proper length) | — | `L = L₀/γ` | Không co theo phương vuông góc chuyển động |
| Cộng vận tốc tương đối tính | vật chuyển động vận tốc `u` trong `S'`, `S'` chuyển động `v` so với `S`, cùng phương | — | `u = (u' + v)/(1 + u'v/c²)` | Với chuyển động không cùng phương cần công thức đầy đủ theo từng thành phần |
| Động lượng & năng lượng tương đối tính | hạt khối lượng nghỉ `m`, vận tốc `v` bất kỳ (kể cả gần `c`) | — | `p = γmv`; `E = γmc²`; hệ thức bất biến `E² = (pc)² + (mc²)²` | Với photon (`m=0`): `E=pc` |
| Bảo toàn năng lượng–động lượng 4 vectơ trong va chạm/phân rã tương đối tính | hệ kín, không ngoại lực | dùng khi ít nhất 1 hạt có `v` gần `c` hoặc là photon | `ΣE_trước=ΣE_sau`; `Σp⃗_trước=Σp⃗_sau`; bất biến `s=E²−(pc)²` như nhau ở 2 khung | công cụ nền cho cả A.3 (ngưỡng phản ứng), A.7 (Compton), A.8 (Doppler) |

**"CHỖ" thường gặp:** "hai khung quy chiếu quán tính", "đồng hồ trên tàu vũ trụ", "nghịch lý hai anh em sinh đôi", "vận tốc gần bằng c", "khối lượng nghỉ", "E² = (pc)² + (mc²)²".

**Tiền xử lý riêng:** luôn xác định rõ *biến cố nào* đang so sánh giữa 2 khung, và *đại lượng nào là "riêng" (proper)* — đây là *CHỖ* dễ nhầm chiều co/giãn nhất (ai đo cái gì, trong khung nào).

---

### A.6. Lượng tử ánh sáng, lưỡng tính sóng–hạt, hiện tượng quang điện

| Công cụ ℓ | Pre(ℓ) | Suf(ℓ) | Post(ℓ) | Err(ℓ) |
|---|---|---|---|---|
| Lượng tử năng lượng photon | ánh sáng tương tác dạng hạt (hấp thụ/phát xạ rời rạc) | — | `E = hf = hc/λ` | — |
| Động lượng photon | photon là hạt khối lượng nghỉ 0 | hệ quả trực tiếp từ `E=pc` (A.5) | `p = h/λ = E/c` | — |
| Phương trình Einstein hiệu ứng quang điện | ánh sáng đơn sắc chiếu vào kim loại có công thoát `W₀` | `f ≥ f₀ = W₀/h` (trên ngưỡng) | `hf = W₀ + T_e,max` | Không tính đến phân bố năng lượng electron trong kim loại (mô hình đơn giản hóa) |
| Thế hãm | đo `T_e,max` bằng điện trường cản | — | `eU_h = T_e,max` ⇒ `hf = W₀ + eU_h` | — |
| Hệ thức de Broglie (sóng vật chất) | hạt có khối lượng (electron, proton,…), áp dụng khi cần xét tính chất sóng (nhiễu xạ, giao thoa hạt) | phi tương đối tính: `p=mv`; tương đối tính: `p=γmv` | `λ_dB = h/p` | Ở tốc độ cao phải dùng `p` tương đối tính, không dùng `p=mv` |
| Nguyên lý bất định Heisenberg | ước lượng bậc độ lớn độ bất định vị trí–động lượng (không dùng để giải chính xác) | dùng như chặn dưới, không phải đẳng thức | `Δx·Δp ≳ ħ/2` (hoặc `≈ħ` tùy quy ước đề bài) | Chỉ cho ước lượng bậc độ lớn, không thay thế phương trình động lực học |

**"CHỖ" thường gặp:** "công thoát", "bước sóng giới hạn quang điện", "thế hãm", "bước sóng de Broglie của electron", "lưỡng tính sóng hạt", "độ bất định vị trí/động lượng tối thiểu".

**Tiền xử lý riêng:** phân biệt rõ 2 vai trò của ánh sáng trong cùng một bài — khi tương tác với electron ở bề mặt kim loại thì dùng công cụ *hạt* (Einstein); khi hỏi về giao thoa/nhiễu xạ thì dùng công cụ *sóng* — đề thường trộn cả 2 vai trò để kiểm tra học sinh có phân biệt được *CHỖ* nào dùng tính chất nào.

---

### A.7. Hiệu ứng Compton

**Dom:** tán xạ đàn hồi giữa **photon** năng lượng cao (tia X) và **electron tự do** (hoặc coi gần tự do), electron ban đầu đứng yên.

| Công cụ ℓ | Pre(ℓ) | Suf(ℓ) | Post(ℓ) | Err(ℓ) |
|---|---|---|---|---|
| Bảo toàn động lượng (vectơ, tương đối tính) | photon tán xạ góc `θ`, electron giật lùi góc `φ` | electron trước tán xạ đứng yên (hoặc "tự do", bỏ qua liên kết với nguyên tử) | `p⃗_photon,trước = p⃗_photon,sau + p⃗_electron,sau` (2 phương trình chiếu) | Nếu electron liên kết mạnh (không tự do) → công thức Compton chuẩn không áp dụng đúng |
| Bảo toàn năng lượng toàn phần tương đối tính | cùng hệ | electron có thể đạt vận tốc lớn sau tán xạ → bắt buộc dùng `E=√((pc)²+(mc²)²)`, không dùng động năng cổ điển | `hf + m_ec² = hf' + E_electron,sau` | — |
| Công thức dịch chuyển Compton (kết quả đã rút gọn từ 2 định luật trên — dùng trực tiếp nếu chỉ cần Δλ) | như trên | đã khử được động lượng/năng lượng electron sau tán xạ | `λ' − λ = (h/m_ec)(1 − cosθ)`; bước sóng Compton `λ_C = h/(m_ec) ≈ 2.43 pm` | Chỉ cho `Δλ`, không cho trực tiếp năng lượng/hướng electron giật lùi — muốn cái đó phải quay lại 2 phương trình bảo toàn gốc |

**"CHỖ" thường gặp:** "tán xạ Compton", "electron giật lùi", "bước sóng photon tán xạ thay đổi theo góc".

**Tiền xử lý riêng:** nếu đề chỉ hỏi `Δλ` theo `θ` → dùng thẳng công thức rút gọn; nếu đề hỏi năng lượng/hướng của **electron** sau tán xạ → phải quay lại hệ 2 phương trình bảo toàn gốc (động lượng theo 2 phương + năng lượng), vì công thức Compton rút gọn đã "giấu" biến electron đi.

---

### A.8. Hiệu ứng Doppler tương đối tính

**Dom:** nguồn phát sóng điện từ tần số `f₀` (trong khung nguồn) chuyển động vận tốc `v` so với người quan sát.

| Công cụ ℓ | Pre(ℓ) | Suf(ℓ) | Post(ℓ) | Err(ℓ) |
|---|---|---|---|---|
| Doppler tương đối tính dọc trục (nguồn ra xa/lại gần thẳng hàng đường nối) | nguồn và máy thu chuyển động dọc đường nối chúng | — | Ra xa: `f = f₀√((1−β)/(1+β))`; Lại gần: `f = f₀√((1+β)/(1−β))` | Không dùng công thức Doppler âm học cổ điển khi `v` so được với `c` |
| Doppler tương đối tính tổng quát theo góc `θ` (góc quan sát trong khung máy thu, so với phương chuyển động nguồn) | biết góc `θ` giữa phương truyền tới máy thu và phương chuyển động nguồn | trường hợp riêng `θ=0,π` cho lại 2 công thức trên | `f = f₀ / [γ(1 − βcosθ)]` | Cần cẩn thận góc đo trong khung nào (nguồn hay máy thu) — hay bị nhầm dấu |
| Doppler ngang (transverse) | `θ=π/2` đo trong khung máy thu (thời điểm nguồn đi ngang qua) | hệ quả trực tiếp từ giãn thời gian, **không tồn tại trong Doppler cổ điển** | `f = f₀/γ` (luôn đỏ hơn, kể cả khi khoảng cách tức thời không đổi) | Dễ nhầm với "không có dịch chuyển tần số khi đi ngang" như trực giác cổ điển — đây chính là hiệu ứng cần phân biệt |

**"CHỖ" thường gặp:** "dịch chuyển đỏ/xanh", "vận tốc lùi xa của thiên hà", "Doppler ngang", "tần số quan sát khi nguồn bay ngang qua".

**Tiền xử lý riêng:** xác định rõ góc `θ` được đo **ở khung nào** (đây là điểm hay gây sai số dấu/độ lớn nhất của cả mục); nếu bài không cho góc và chỉ nói "ra xa"/"lại gần" thẳng hàng → dùng công thức dọc trục trực tiếp, không cần công thức tổng quát.

---

## PHẦN B — VẤN ĐỀ 2: HÌNH THỨC HÓA CHUYỂN VẬT LÝ → TOÁN

Với mỗi chuyên đề, sau khi Phần A đã chọn được tập `ℓ` khả dụng, bước này là **viết cụ thể O, V, C** rồi từ `Post(ℓ)` của các công cụ đã chọn, dựng thành **hệ phương trình/bất phương trình** hoàn chỉnh — tức bài Vật Lý đã chính thức trở thành bài Toán, sẵn sàng cho Vấn đề 3 (không giải ở đây).

### B.1. Mẫu mô hình nguyên tử

- **O:** electron (khối lượng `m`), hạt nhân điện tích `+Ze` (khối lượng `M`, coi đứng yên hoặc dùng `μ`).
- **V:** `n` (số lượng tử, nguyên dương), `r_n`, `E_n`, `λ` (nếu hỏi bức xạ).
- **C:** `Z` cho trước; nếu đề cho 2 mức `n_i>n_f` xác định.
- **Hệ Toán sinh ra** (ghép `Post` của "Coulomb–hướng tâm" + "lượng tử hóa L"):

```
k Z e² / r² = m v² / r        (1)
m v r = n ħ                   (2)
```
Khử `v`: 2 phương trình đại số ẩn `(r,v)` → nghiệm `r_n = n²ħ²/(kme²Z)`. Nếu hỏi bước sóng phát xạ giữa `n_i→n_f`, cộng thêm:
```
hc/λ = E_{n_i} − E_{n_f}      (3)
```
→ bài Toán còn lại thuần túy là đại số/thế số, không còn thao tác vật lý nào khác.

### B.2. Cấu trúc hạt nhân

- **O:** một hạt nhân `(A,Z)`.
- **V:** `Δm`, `E_b` (hoặc các tham số SEMF nếu đề cho).
- **C:** khối lượng `Z` proton, `N=A−Z` neutron, khối lượng hạt nhân/nguyên tử đã cho — **phải quy đồng đơn vị (hạt nhân hay nguyên tử) trước khi lập phương trình**.
- **Hệ Toán:**
```
Δm = Z·m_p + (A−Z)·m_n − M(A,Z)
E_b = Δm · c²
```
— đây là hệ 2 phương trình tuyến tính đơn giản, không cần biến trung gian nào khác một khi đơn vị đã nhất quán (đó là toàn bộ "khó khăn" thật sự nằm ở bước tiền xử lý, không nằm ở đại số).

### B.3. Phản ứng hạt nhân

- **O:** hạt đạn `a` (khối lượng `m_a`, động năng `T_a` hoặc vận tốc `v_a`), bia `X` đứng yên, sản phẩm `Y, b`.
- **V:** `Q`, và ẩn được hỏi (ví dụ `T_ngưỡng`, động năng sản phẩm,…).
- **C:** bảo toàn `A`, `Z` (đã dùng để cân bằng phương trình phản ứng ở bước tiền xử lý — không còn là ẩn Toán nữa).
- **Hệ Toán (trường hợp cổ điển, ngưỡng phản ứng thu nhiệt):**
```
Q = (m_a + m_X − m_Y − m_b)c²                       (1)
p_a = p_Y + p_b   (bảo toàn động lượng, tại ngưỡng: 
                    sản phẩm cùng vận tốc trong hệ khối tâm)   (2)
T_a + Q = T_Y + T_b                                  (3)
```
Với điều kiện "ngưỡng" bổ sung là hệ ràng buộc cực trị: sản phẩm đứng yên trong khung khối tâm ⇒ thay (2),(3) bằng điều kiện khối tâm, ra:
```
T_ngưỡng = −Q(m_a+m_X)/m_X
```
— là một phương trình đại số tường minh, không còn thao tác vật lý.

### B.4. Phóng xạ

- **O:** mẫu chứa `N₀` hạt nhân mẹ tại `t=0`; nếu có chuỗi, thêm hạt nhân con với `λ₂`.
- **V:** `N(t)`, `t`, hoặc `λ` (nếu hỏi ngược từ `T_{1/2}`).
- **C:** `T_{1/2}` hoặc `λ` cho trước; điều kiện ban đầu `N(0)=N₀`.
- **Hệ Toán:** phương trình vi phân tuyến tính bậc 1
```
dN/dt = −λN,  N(0)=N₀     ⇒   N(t)=N₀e^{−λt}
```
đây đã là nghiệm tường minh (không cần giải thêm) — với chuỗi phân rã, hệ trở thành hệ ODE tuyến tính (Bateman):
```
dN₁/dt = −λ₁N₁
dN₂/dt = λ₁N₁ − λ₂N₂
```
Với phân rã α 2 vật, hệ Toán là hệ đại số (không vi phân):
```
p_α = p_Y                         (bảo toàn động lượng, độ lớn)
p_α²/2m_α + p_Y²/2M_Y = Q         (bảo toàn năng lượng, phi tương đối tính)
```
→ 2 phương trình, 2 ẩn `(p, và nghiệm cho T_α)`.

### B.5. Tương đối tính & Lorentz

- **O:** 2 khung `S, S'`, vận tốc tương đối `v`; 2 biến cố `E1, E2` cần so sánh.
- **V:** tọa độ-thời gian của biến cố trong từng khung `(x,t)` và `(x',t')`.
- **C:** tọa độ biến cố trong 1 khung (đề cho), điều kiện "cùng vị trí" hay "cùng thời điểm" nếu có.
- **Hệ Toán (tổng quát nhất, mọi bài con của A.5 đều là trường hợp riêng):**
```
x' = γ(x − vt)
t' = γ(t − vx/c²),   γ = 1/√(1−v²/c²)
```
Giãn thời gian/co độ dài chỉ là hệ quả đại số của hệ trên khi áp thêm ràng buộc `C` tương ứng (ví dụ `Δx=0` trong khung riêng cho giãn thời gian). Với động lượng–năng lượng, hệ Toán là:
```
E² = (pc)² + (mc²)²
p = γmv,  E = γmc²
```
— tất cả các bài "va chạm/phân rã tương đối tính" trong A.3, A.4, A.7 đều quy về giải **hệ đại số phi tuyến** từ bảo toàn `(E,p⃗)` cộng với hệ thức bất biến này.

### B.6. Lượng tử ánh sáng & quang điện

- **O:** photon (`f`, `λ`), electron bề mặt kim loại (`W₀`).
- **V:** `T_e,max`, `U_h`, hoặc `f₀`.
- **C:** `f` (hoặc `λ`) chiếu tới cho trước; `W₀` cho trước (hoặc `λ₀` giới hạn quang điện, tương đương).
- **Hệ Toán:**
```
hf = W₀ + T_e,max
eU_h = T_e,max
```
— 2 phương trình tuyến tính, ẩn `T_e,max`, `U_h`. Nếu bài hỏi thêm bước sóng de Broglie của electron bật ra, cộng:
```
λ_dB = h/√(2m T_e,max)     (phi tương đối tính)
```

### B.7. Hiệu ứng Compton

- **O:** photon tới (`λ`), electron đứng yên (`m_e`); sau tán xạ: photon (`λ',θ`), electron (`p_e,φ`).
- **V:** `λ'` (hoặc `Δλ`), và nếu cần: `p_e, φ`.
- **C:** `λ, θ` cho trước (hoặc `θ` là ẩn cần tìm ngược).
- **Hệ Toán đầy đủ (2 phương trình động lượng theo `x,y` + 1 phương trình năng lượng, 3 phương trình, ẩn `λ', p_e, φ`):**
```
h/λ = (h/λ')cosθ + p_e cosφ
0   = (h/λ')sinθ − p_e sinφ
hc/λ + m_ec² = hc/λ' + √((p_ec)² + (m_ec²)²)
```
Khử `p_e, φ` từ hệ trên (đại số thuần túy) cho ra đúng công thức rút gọn ở A.7. Nếu bài chỉ cần `Δλ(θ)` thì dùng thẳng kết luận đã rút gọn, không cần viết lại cả hệ 3 phương trình.

### B.8. Doppler tương đối tính

- **O:** nguồn tần số riêng `f₀`, chuyển động vận tốc `v`, góc quan sát `θ`.
- **V:** `f` (tần số đo được).
- **C:** `v, θ` (hoặc chỉ "ra xa/lại gần" nếu chuyển động dọc trục).
- **Hệ Toán:**
```
f = f₀ / [γ(1 − β cosθ)],   γ=1/√(1−β²), β=v/c
```
— một phương trình tường minh, ẩn duy nhất `f` (hoặc ngược lại `v` nếu đề cho `f, f₀` và hỏi vận tốc lùi xa — khi đó là phương trình đại số bậc 2 ẩn `β` sau khi bình phương 2 vế).

---

## KẾT — GIỚI HẠN & HƯỚNG MỞ RỘNG

1. Thư viện `L` ở Phần A là **bậc phổ thông chuyên sâu → HSGQG**; với IPhO, một số mục cần mở rộng thêm: mô hình Sommerfeld (quỹ đạo elip) cho A.1, số hạng cặp đôi chẵn-lẻ chi tiết hơn trong SEMF cho A.2, tiết diện phản ứng (cross-section) nếu đề động học hạt nhân nâng cao cho A.3, biến đổi 4-vectơ tổng quát (không chỉ dọc 1 trục) cho A.5.
2. Đúng như tinh thần "Vấn đề 2" đã nêu: mọi `Post(ℓ)` trong Phần A khi ghép lại ở Phần B đều cho ra **hệ phương trình đại số hoặc vi phân tuyến tính đơn giản** — không có bước nào trong 8 mục này đòi hỏi công cụ Toán vượt quá đại số/ODE tuyến tính cơ bản, đúng như kỳ vọng "Vấn đề 3 chỉ cần giỏi Toán chuẩn" đã đặt ra ban đầu.
3. *CHỖ* dễ sai nhất, tổng hợp lại xuyên suốt cả 8 mục, không nằm ở việc thiếu công thức mà nằm ở **3 bước tiền xử lý lặp lại**: (a) chọn cổ điển hay tương đối tính đúng thang năng lượng; (b) xác định đúng đại lượng nào là "riêng"/"trong khung nào" trước khi áp Lorentz/Doppler; (c) đếm đúng số hạt tham gia bảo toàn (2 vật hay ≥3 vật) trước khi chọn công cụ động học.
