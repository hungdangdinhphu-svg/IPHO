# TOÀN TẬP TOY MODEL & LÝ THUYẾT — ĐIỆN & TỪ HỌC (VPHO)
### Hệ thống hóa theo khung nguyên tắc 1.0–1.5, dùng để ôn luyện chuyên đề **Điện và Từ** cho Kỳ thi Chọn Học sinh Giỏi Quốc gia THPT (VPHO)

---

## PHẦN 0 — KHUNG NGUYÊN TẮC & CÁCH DÙNG TÀI LIỆU

**0.1. Mục đích.** Tài liệu này cung cấp một tập hợp **hữu hạn** các Toy Model & Lý thuyết (ký hiệu **TM**), được lựa chọn/hệ thống hóa sao cho *mọi* bài toán Điện–Từ có thể xuất hiện trong đề VPHO (phạm vi xác định bởi đề cương VPHO — hai ảnh đính kèm) đều có thể quy về việc **nhận diện mẫu hình rồi áp dụng đúng quy trình** của một (hoặc một tổ hợp) TM trong danh sách này — tức là áp dụng theo cách "tầm thường" (không vi phạm mục 1.2), không đòi hỏi phát minh phương pháp mới trong phòng thi.

**0.2. Quan hệ với 1.0 (kỹ năng giải toán thuần túy).** Danh sách TM dưới đây là kiến thức **vật lý**. Để biến TM thành lời giải hoàn chỉnh, học sinh còn cần kỹ năng toán thuần túy (đại số, hình học, lượng giác, vector, đạo hàm/tích phân cơ bản, phương trình vi phân tuyến tính bậc 1, số phức sơ cấp) — tài liệu này **không** dạy lại phần toán đó, coi nó là điều kiện cần đã có sẵn (mục 1.3, ý thứ hai).

**0.3. Cấu trúc thống nhất của mỗi Toy Model:**
- **Nhận diện** — dấu hiệu/từ khóa trong đề bài cho biết cần dùng TM này (Pattern Recognition — mục 1.1);
- **Phát biểu** — công thức/định lý chính xác, đã được chứng minh chặt chẽ trong tài liệu nguồn;
- **Quy trình áp dụng** — các bước thực hiện tuần tự, thuần túy tra cứu + tính toán;
- **Điều kiện/giới hạn áp dụng**;
- **Bài tập gốc tham chiếu** — số bài trong *Kiisk (2017)* để luyện áp dụng trực tiếp.

**0.4. Nguồn.** Khung lý thuyết bên dưới dựa chủ yếu vào: Valter Kiisk, *Elektri ja magnetismi ülesandeid*, Tartu Ülikooli Teaduskool, phiên bản 2.0 (2017) — gọi tắt **Kiisk (2017)**. Theo đúng lời tựa của tác giả, tài liệu này được biên soạn nằm **trong** phạm vi Đề cương IPHO (`ioc.ee/~kalda/ipho/Syllabus-new.pdf`), tức là một tập lý thuyết **rộng hơn** phạm vi VPHO (VPHO ⊂ IPHO về nội dung Điện–Từ cổ điển). Do đó, việc dùng Kiisk (2017) làm xương sống là hợp lý để đảm bảo tính "đầy đủ" (mục 1.4).

Đúng như bạn đã lưu ý: **Kiisk (2017) không đầy đủ về mạch điện** so với nhu cầu thi VPHO thực tế (một số kỹ thuật mạch điện được nêu rải rác, không hệ thống thành định lý độc lập). Các chỗ này được **bổ sung** từ kiến thức mạch điện chuẩn, đánh dấu rõ **[BỔ SUNG]**.

**0.5. Tính khả thi trong phòng thi (mục 1.5).** Mỗi TM được viết ở dạng "công thức tra cứu nhanh": nhận diện 10–30 giây, áp dụng 1–5 phút (với học sinh đã luyện tập đủ — mục 1.3, ý "chăm chỉ"). Việc **chứng minh** mỗi TM chỉ cần làm **một lần lúc học** (xem lại trong Kiisk 2017 hoặc SGK/tài liệu chuyên); trong phòng thi chỉ cần **nhớ và áp dụng**, không chứng minh lại — nếu không, thời gian 180 phút sẽ không đủ (đảm bảo không vi phạm mục 1.5).

**0.6. Quy ước ký hiệu (chuẩn SI, theo Kiisk 2017):** ε₀ = 8,85×10⁻¹² F/m; μ₀ = 4π×10⁻⁷ H/m; k_e = 1/(4πε₀) ≈ 8,99×10⁹ N·m²/C².

---

## PHẦN 0.5 — BẢNG ĐỐI CHIẾU: ĐỀ CƯƠNG VPHO ↔ TOY MODEL ↔ NGUỒN

*(Cấu trúc lấy đúng theo 2 ảnh đề cương: mục **III. ĐIỆN TỪ HỌC** gồm 3 nhóm — Tĩnh điện / Từ học / Điện từ nâng cao; cấp độ Nền tảng hay Chuyên sâu ghi theo đúng màu/khung trong ảnh gốc.)*

| # | Mục đề cương VPHO | Cấp độ | Toy Model | Mục tương ứng trong Kiisk (2017) |
|---|---|---|---|---|
| 1 | Lực tương tác tĩnh điện, điện trường | Nền tảng | I.1.1 – I.1.4 | 3.1, 3.3 |
| 2 | Điện thế, hiệu điện thế | Nền tảng | I.2.1 – I.2.3 | 3.5 |
| 3 | Tụ điện, năng lượng của tụ điện | Nền tảng | I.3.1 – I.3.4 | 2.1 – 2.3 |
| 4 | Mạch điện, định luật Ohm cho toàn mạch, mạch phức hợp | Nền tảng | I.4.1 – I.4.13 | 1.1 – 1.5 |
| 5 | Công, công suất, dòng điện, nguồn điện | Nền tảng | I.5.1 – I.5.3 | 1.1 |
| 6 | Mạch chứa tụ và điện trở | Nền tảng | I.6.1 – I.6.4 | 2.4 |
| 7 | Từ trường, định luật Biot–Savart | Chuyên sâu | II.1.1 – II.1.4 | 4.1, 4.3 |
| 8 | Lực từ | Chuyên sâu | II.2.1 – II.2.7 | 4.2, 4.4, 4.5, 7.1, 7.2 |
| 9 | Cảm ứng điện từ | Chuyên sâu | II.3.1 – II.3.2 | 5.1 |
| 10 | Tự cảm | Chuyên sâu | II.4.1 – II.4.6 | 5.2 – 5.4 |
| 11 | Dòng điện xoay chiều | Chuyên sâu | II.5.1 – II.5.5 | 6.1 – 6.4 |
| 12 | Định lí O–G (Gauss) | Chuyên sâu | III.1.1 – III.1.3 | 3.2 |
| 13 | Thế năng tương tác của hệ điện tích | Chuyên sâu | III.2.1 – III.2.2 | 3.5 |
| 14 | Lí thuyết lưỡng cực điện | Chuyên sâu | III.3.1 – III.3.3 | 3.4 |
| 15 | Điện môi | Chuyên sâu | III.4.1 – III.4.4 | 3.8 – 3.10 |
| 16 | Vật dẫn | Chuyên sâu | III.5.1 – III.5.4 | 3.6, 3.7 |
| 17 | Mạch 1 chiều, phi tuyến | Chuyên sâu | III.6.1 – III.6.4 (+ I.4.*) | 1.4, 1.5 |
| 18 | Dao động điện từ, điốt | Chuyên sâu | III.7.1 – III.7.2 (+ II.5.4–5) | 6.4, 5.4, 1.5 |
| 19 | Chữa bài tập bộ sách "Điện cầu vồng" | Chuyên sâu | — (áp dụng tổng hợp I–III) | — |

---
---

# PHẦN I — TĨNH ĐIỆN *(Học trong khoá Nền tảng)*

## I.1 Lực tương tác tĩnh điện, điện trường

**TM I.1.1 — Định luật Coulomb**
- *Nhận diện:* đề cho điện tích điểm (hoặc phân bố quy được về điện tích điểm/đối xứng cầu — xem I.1.4), hỏi lực tương tác.
- *Phát biểu:* $F = k_e q_1 q_2 / r^2$, hướng dọc đường nối 2 điện tích; $F>0$ là lực đẩy.
- *Quy trình:* (1) liệt kê mọi cặp điện tích tương tác với đối tượng cần tính; (2) tính từng $F_i$; (3) cộng vector (→ I.1.2); (4) chiếu lên hệ trục chọn theo đối xứng bài toán để giảm số ẩn.
- *Giới hạn:* chỉ đúng nguyên dạng cho điện tích điểm.
- *Tham chiếu:* Kiisk ül. 61–65.

**TM I.1.2 — Nguyên lý chồng chất (lực & trường)**
- *Phát biểu:* $\vec F_{tổng}=\sum \vec F_i$; $\vec E(\vec r)=\sum_i \dfrac{q_i}{4\pi\varepsilon_0|\vec r-\vec r_i|^2}\hat{(\vec r-\vec r_i)}$. Phân bố liên tục: tổng → tích phân.
- *Quy trình:* (1) chia hệ thành điện tích điểm/vi phân; (2) tận dụng đối xứng để loại trước các thành phần triệt tiêu; (3) cộng phần còn lại; (4) nếu tích phân cồng kềnh và có đối xứng cao → chuyển sang TM III.1.1 (Gauss).
- *Tham chiếu:* Kiisk ül. 61, 62, 65, 96.

**TM I.1.3 — Điện trường & đường sức**
- *Phát biểu:* $\vec E=\vec F/q_0$ (giới hạn $q_0\to0$). Đường sức xuất phát từ (+), kết thúc ở (–); mật độ đường sức ∝ |E|.
- *Dùng để:* kiểm tra một hình vẽ đường sức cho trước có hợp lệ vật lý không; suy luận định tính hướng/độ lớn khi chưa cần con số.
- *Tham chiếu:* Kiisk ül. 66, 90.

**TM I.1.4 — Định lý "vật đối xứng tâm ≡ điện tích điểm"**
- *Phát biểu:* nhìn từ ngoài, một quả cầu/vỏ cầu tích điện đối xứng tâm tạo lực & trường giống hệt điện tích điểm bằng tổng điện tích, đặt tại tâm (chứng minh bằng Gauss — xem III.1).
- *Hệ quả:* hai quả cầu như vậy tương tác đúng như 2 điện tích điểm.
- *Tham chiếu:* Kiisk ül. 77.

## I.2 Điện thế, hiệu điện thế

**TM I.2.1 — Định nghĩa & tính điện thế**
- *Phát biểu:* $\varphi_B-\varphi_A=-\int_A^B \vec E\cdot d\vec l$. Điện tích điểm: $\varphi(r)=q/4\pi\varepsilon_0 r$ (chọn $\varphi(\infty)=0$).
- *Quy trình 2 chiều:* biết $E(r)$ → tích phân ra $\varphi$; biết $\varphi(r)$ → $\vec E=-\nabla\varphi$.
- *Chiến thuật quan trọng:* với hệ nhiều điện tích, tính $\varphi=\sum q_i/4\pi\varepsilon_0 r_i$ (cộng **đại số**, không phải vector) thường dễ hơn nhiều so với cộng trực tiếp $\vec E$; sau đó lấy đạo hàm nếu cần $\vec E$.
- *Tham chiếu:* Kiisk ül. 83, 89, 91, 94, 96.

**TM I.2.2 — Công của lực điện & thế năng**
- *Phát biểu:* $A_{A\to B}=q(\varphi_A-\varphi_B)$; trường tĩnh điện là trường thế (công theo chu trình kín = 0, công không phụ thuộc đường đi).
- *Dùng để:* giải bài toán động học hạt tích điện bằng bảo toàn năng lượng $W_{đ}+q\varphi=\text{const}$, thay vì tích phân lực theo thời gian.
- *Tham chiếu:* Kiisk ül. 89.

**TM I.2.3 — Thế năng hệ điện tích điểm (dạng cơ bản)**
- *Phát biểu:* $\Pi=\frac12\sum_i \varphi_i q_i$ ($\varphi_i$: điện thế do các điện tích *khác* gây ra tại vị trí $q_i$; hệ số ½ vì mỗi cặp bị đếm 2 lần). *(Dạng tổng quát hơn — xem III.2.)*
- *Tham chiếu:* Kiisk ül. 93.

## I.3 Tụ điện, năng lượng của tụ điện

**TM I.3.1 — Quan hệ Q–U của tụ điện**
- *Phát biểu:* $Q=CU$; $I=dQ/dt=C\,dU/dt$. Tụ phẳng: $C=\varepsilon\varepsilon_0 S/d$ ($d\ll$ kích thước bản).
- *Tham chiếu:* Kiisk pt. (1); ül. 45.

**TM I.3.2 — Năng lượng tụ điện**
- *Phát biểu:* $\Pi=Q^2/2C=CU^2/2=QU/2$.
- *Dùng để:* tính nhiệt tỏa ra, công nạp/xả (kết hợp I.6.2).
- *Tham chiếu:* Kiisk ül. 46, 47.

**TM I.3.3 — Ghép tụ điện**
- *Phát biểu:* song song $C=C_1+C_2+\dots$; nối tiếp $1/C=1/C_1+1/C_2+\dots$
- *Tham chiếu:* Kiisk ül. 48, 49.

**TM I.3.4 — Lực cơ học lên bản tụ (dịch chuyển ảo — virtual work)**
- *Phát biểu:* hệ cô lập điện tích ($Q$=const): $F=-d\Pi/dx$. Hệ nối nguồn thế không đổi ($U$=const): $F=+d\Pi/dx$ (dấu đổi vì nguồn cấp thêm công — hai cách tính phải cho cùng 1 lực vật lý).
- *Quy trình:* (1) viết $\Pi(x)$ theo biến hình học cần tìm lực; (2) đạo hàm; (3) **chú ý điều kiện biên** ($Q$ hay $U$ cố định) để lấy đúng dấu.
- *Tham chiếu:* Kiisk ül. 51, 52, 53, 54.

## I.4 Mạch điện, định luật Ohm cho toàn mạch, mạch phức hợp

**TM I.4.1 — Ohm & ghép điện trở**
- *Phát biểu:* $I=U/R$; $R_{nt}=\sum R_i$; $1/R_{ss}=\sum 1/R_i$; $R=\rho l/S$.
- *Tham chiếu:* Kiisk ül. 1–7.

**TM I.4.2 — Hai định luật Kirchhoff**
- *Phát biểu:* (I) $\sum I_{vào\ nút}=0$; (II) quanh 1 vòng kín, $\sum U_{rơi}=\sum \mathcal E$ (đại số, theo đúng chiều đi vòng).
- *Quy trình:* (1) đặt chiều dòng giả định mỗi nhánh; (2) viết $N-1$ phương trình nút; (3) viết đủ số phương trình vòng độc lập (= số nhánh − số nút + 1); (4) giải hệ.
- *Tham chiếu:* Kiisk ül. 8–14.

**TM I.4.3 — Phương pháp thế nút**
- *Nhận diện:* mạch nhiều nút, ít vòng độc lập hơn.
- *Quy trình:* chọn 1 nút gốc $\varphi=0$; viết Kirchhoff I tại mỗi nút còn lại theo hiệu thế các nút lân cận; giải hệ tuyến tính.
- *Tham chiếu:* Kiisk, mục "Potentsiaalide meetod".

**TM I.4.4 — Phương pháp dòng vòng**
- *Quy trình:* chọn dòng vòng độc lập cho từng vòng cơ sở (Kirchhoff I tự động thỏa); viết Kirchhoff II theo dòng vòng; giải hệ.
- *Tham chiếu:* Kiisk, mục "Kontuurvoolude meetod".

**TM I.4.5 — Nguyên lý chồng chất trong mạch tuyến tính**
- *Phát biểu:* mạch chỉ gồm điện trở thuần & nguồn sđđ lý tưởng: dòng qua 1 phần tử = tổng đại số dòng do từng nguồn gây ra riêng lẻ (các nguồn sđđ khác bị nối tắt khi xét riêng từng nguồn).
- *Tham chiếu:* Kiisk ül. 12.

**TM I.4.6 — Biến đổi tương đương sao–tam giác (Δ–Y)**
- *Phát biểu:* $R_A=\dfrac{R_{AB}R_{AC}}{R_{AB}+R_{AC}+R_{BC}}$ (tuần hoàn); $R_{AB}=R_A+R_B+\dfrac{R_AR_B}{R_C}$ (tuần hoàn). Đối xứng: $R_Y=R_\Delta/3$.
- *Nhận diện:* mạch cầu / mạch không rút gọn được thuần bằng nối tiếp–song song.
- *Tham chiếu:* Kiisk ül. 15.

**TM I.4.7 — Định lý Thevenin & Norton**
- *Phát biểu (Thevenin):* mọi mạch tuyến tính 2 cực (điện trở + nguồn sđđ lý tưởng) ≡ 1 nguồn $\mathcal E_{th}$ nối tiếp $r_{th}$.
- *Phát biểu (Norton, đối ngẫu):* ≡ nguồn dòng $I_0=\mathcal E_{th}/r_{th}$ song song $r_{th}$.
- *Quy trình 2 bước "tầm thường":* (1) tính $U$ khi hở mạch ngoài ⇒ $\mathcal E_{th}$; (2) tính $I$ khi ngắn mạch ngoài ⇒ $r_{th}=\mathcal E_{th}/I_{ngắnmạch}$ (hoặc: nối tắt mọi nguồn sđđ rồi tính điện trở tương đương nhìn từ 2 cực).
- *Tham chiếu:* Kiisk, mục "Elektromotoorjõud ja takistus jadamisi"; ül. 16–21.

**TM I.4.8 — Định lý Millman**
- *Phát biểu:* $N$ nguồn $\mathcal E_i$ nối tiếp $R_i$, mắc song song giữa 2 nút: $U_{AB}=\dfrac{\sum \mathcal E_i/R_i}{\sum 1/R_i}$.
- *Tham chiếu:* Kiisk ül. 21, 22.

**TM I.4.9 — Phương pháp đối xứng**
- *Nhận diện:* mạch có đối xứng gương/quay (rõ hoặc ẩn).
- *Quy trình:* (1) tìm phép biến đổi (phản chiếu/quay/đảo cực mọi nguồn) giữ mạch bất biến; (2) suy ra các nút tương ứng cùng điện thế ⇒ nối tắt được hoặc cắt được nhánh nối giữa chúng mà không đổi tính chất mạch; (3) mạch rút gọn còn thuần nối tiếp–song song.
- *Lưu ý:* đảo cực **mọi** nguồn cũng là một phép đối xứng hợp lệ (mọi dòng/áp đổi dấu).
- *Tham chiếu:* Kiisk ül. 23–28.

**TM I.4.10 — Ampe kế & Vôn kế lý tưởng**
- *Phát biểu:* ampe kế lý tưởng $R=0$ (nối tắt 2 nút); vôn kế lý tưởng $R=\infty$ (hở mạch).
- *Tham chiếu:* Kiisk ül. 27, 28.

**TM I.4.11 — Mạch tuần hoàn vô hạn (mạch thang)**
- *Quy trình:* gọi $R$ là điện trở toàn mạch vô hạn; thêm/bớt 1 mắt xích không đổi $R$ (do vô hạn); lập phương trình $R=f(R,\text{các phần tử 1 mắt})$; giải (thường bậc 2, chọn nghiệm dương).
- *Tham chiếu:* Kiisk ül. 29, 30.

**TM I.4.12 — Mạng vô hạn 2D/3D (kỹ thuật đối xứng dòng)** *[ưu tiên ôn thấp — IPHO-level, liệt kê để đủ theo 1.4]*
- *Quy trình:* chồng chập 2 nghiệm: bơm dòng $I$ vào 1 nút rồi rút ra ở vô cực (dòng tỏa đối xứng); bơm từ vô cực rút ra ở nút khác; cộng 2 nghiệm.
- *Tham chiếu:* Kiisk ül. 31–33.

**TM I.4.13 — Điện trở âm (công cụ hình thức)**
- *Phát biểu:* dùng $R$ âm để mô tả "sửa mạch" (nối tắt = 2 điện trở $\pm R$ bằng nhau nối tiếp).
- *Tham chiếu:* Kiisk ül. 33.

## I.5 Công, công suất, dòng điện, nguồn điện

**TM I.5.1 — Công suất**
- *Phát biểu:* $P=UI=I^2R=U^2/R$ (2 công thức sau chỉ đúng cho phần tử thuần trở tuyến tính).
- *Tham chiếu:* Kiisk mục 1.1.

**TM I.5.2 — Nguồn thực (sđđ + điện trở trong)**
- *Phát biểu:* $V=\mathcal E-Ir$. Công suất ra ngoài cực đại khi $R_{ngoài}=r$ (phối hợp trở kháng), $P_{max}=\mathcal E^2/4r$.
- *Tham chiếu:* Kiisk ül. 17, 18.

**TM I.5.3 — Ghép nguồn song song** (trường hợp riêng của Millman I.4.8)
- *Tham chiếu:* Kiisk ül. 21.

## I.6 Mạch chứa tụ và điện trở

**TM I.6.1 — Mạch RC: phương trình vi phân & nghiệm mũ**
- *Phát biểu:* không nguồn: $RC\,dU/dt+U=0 \Rightarrow U(t)=U_0e^{-t/RC}$. Có nguồn $\mathcal E$: $U(t)=\mathcal E+(U_0-\mathcal E)e^{-t/RC}$. Hằng số thời gian $\tau=RC$.
- *Quy trình "tầm thường" (không giải lại ODE mỗi lần):*
  1. Tìm giá trị **xác lập** $U(\infty)$ (thay tụ = hở mạch khi dòng nạp/xả đã dừng);
  2. Tìm giá trị **ban đầu** $U(0^+)$ (điện tích/hiệu điện thế trên tụ **không nhảy bậc** — liên tục);
  3. Tìm $\tau=R_{tđ}\cdot C$, với $R_{tđ}$ là điện trở tương đương nhìn từ 2 cực tụ **sau khi nối tắt mọi nguồn sđđ lý tưởng**;
  4. Viết ngay $U(t)=U(\infty)+[U(0)-U(\infty)]e^{-t/\tau}$.
- *Tham chiếu:* Kiisk ül. 55–59.

**TM I.6.2 — Bảo toàn năng lượng cho quá trình chuyển tiếp**
- *Phát biểu:* $\Pi_{đầu}+A_{ngoài}=\Pi_{cuối}+Q_{tỏa nhiệt}$.
- *Dùng khi:* chỉ cần tổng nhiệt lượng, không cần $U(t),I(t)$ chi tiết — tránh tích phân $I^2Rdt$.
- *Lưu ý:* nhiều điện trở nối tiếp trong 1 nhánh nạp/xả ⇒ nhiệt tỏa trên mỗi điện trở tỉ lệ thuận với chính điện trở đó (cùng dòng qua).
- *Tham chiếu:* Kiisk ül. 46, 47, 49, 50.

**TM I.6.3 — Bảo toàn điện tích trên "đảo cô lập"**
- *Phát biểu:* nếu 1 phần mạch bị cô lập về truyền điện tích (không nối đất/nguồn), tổng điện tích trên phần đó là hằng số theo thời gian.
- *Tham chiếu:* Kiisk ül. 49.

**TM I.6.4 — Mạch RC với áp vào dạng xung vuông, 2 trường hợp giới hạn**
- *Phát biểu:* $T\ll RC$ hoặc $T\gg RC$ cho công suất/biên độ dao động dạng đóng gói sẵn (xem Phụ lục A).
- *Tham chiếu:* Kiisk ül. 58, 59.

---
---

# PHẦN II — TỪ HỌC *(Học trong khoá Chuyên sâu)*

## II.1 Từ trường, định luật Biot–Savart

**TM II.1.1 — Định luật Biot–Savart**
- *Phát biểu:* $d\vec B=\dfrac{\mu_0 I}{4\pi}\dfrac{d\vec l\times\hat r}{r^2}$. Chiều xác định bằng quy tắc đinh ốc (vặn $d\vec l$ về phía $\vec r$ theo góc nhỏ hơn).
- *Tham chiếu:* Kiisk ül. 116 (vòng dây trên trục).

**TM II.1.2 — Nguyên lý chồng chất cho $\vec B$**
- *Tham chiếu:* Kiisk ül. 121.

**TM II.1.3 — Trường dây thẳng dài vô hạn** (công thức đóng gói)
- *Phát biểu:* $B=\mu_0I/2\pi r$.
- *Tham chiếu:* Kiisk ül. 118.

**TM II.1.4 — Trường trên trục vòng dây tròn**
- *Phát biểu:* $B(x)=\dfrac{\mu_0R^2I}{2(R^2+x^2)^{3/2}}$; tại tâm ($x=0$): $B=\mu_0I/2R$.
- *Tham chiếu:* Kiisk ül. 116, 122.

## II.2 Lực từ

**TM II.2.1 — Định lý lưu số Ampère (Circulation theorem)**
- *Phát biểu:* $\oint \vec B\cdot d\vec l=\mu_0\sum I_{trong}$.
- *Quy trình (chỉ hiệu quả khi có đối xứng cao):* (1) nhận diện đối xứng (trụ dài / mặt phẳng / solenoid) ⇒ $B$ song song $d\vec l$ và hằng số trên đoạn thích hợp; (2) chọn đường Ampère phù hợp; (3) giải $B$ từ tích phân trở thành phép nhân đơn giản.
- *Kết quả đóng gói:* dây thẳng $B=\mu_0I/2\pi r$; solenoid dài bên trong $B=\mu_0nI$ (đầu solenoid: $B=\mu_0nI/2$); trụ dẫn đặc bán kính $R$, mật độ dòng đều $J$: $B=\mu_0Jr/2$ ($r<R$), $B=\mu_0JR^2/2r$ ($r\ge R$); mặt phẳng dòng vô hạn, mật độ dòng mặt $\alpha$: $B=\mu_0\alpha/2$.
- *Tham chiếu:* Kiisk ül. 117–120, 122.

**TM II.2.2 — Lực Ampère & lực Lorentz**
- *Phát biểu:* $d\vec F=I\,d\vec l\times \vec B$; $\vec F=q\vec v\times \vec B$.
- *Tham chiếu:* Kiisk ül. 124.

**TM II.2.3 — Lực giữa 2 dây song song**
- *Phát biểu:* $F/L=\mu_0I_1I_2/2\pi r$.
- *Tham chiếu:* Kiisk ül. 124.

**TM II.2.4 — Lưỡng cực từ trong trường ngoài**
- *Phát biểu:* mô-men từ $\vec p_m=I\vec S$ (chiều theo đinh ốc); $\vec M=\vec p_m\times\vec B$; $\Pi=-\vec p_m\cdot\vec B$; trường không đều: $F_x=p_m\,\partial B/\partial x$.
- *Tham chiếu:* Kiisk mục 4.5.

**TM II.2.5 — Chuyển động hạt tích điện trong từ trường đều**
- *Phát biểu:* $\vec v\perp\vec B$: quỹ đạo tròn, $R=mv/|q|B$, chu kỳ $T=2\pi m/|q|B$ (không phụ thuộc $v$). Có thành phần $v_\parallel$: quỹ đạo xoắn ốc (helix), $v_\parallel$ không đổi.
- *Tham chiếu:* Kiisk ül. 162, 163.

**TM II.2.6 — Bộ lọc vận tốc / trôi trong $E\perp B$** *(mức ưu tiên trung bình — dạng cơ bản hay gặp, dạng cycloid đầy đủ thuộc IPHO)*
- *Phát biểu:* $\vec E\perp\vec B$ đều: hạt có $v_0=E/B$ theo hướng $\hat B\times\hat E$ đi thẳng không lệch (lực điện cân bằng lực từ). Tổng quát: chuyển động = trôi đều $\langle\vec v\rangle=\vec E\times\vec B/B^2$ cộng chuyển động tròn quanh vận tốc trôi (quỹ đạo cycloid).
- *Tham chiếu:* Kiisk ül. 164–166.

**TM II.2.7 — Hiệu ứng Hall**
- *Phát biểu:* $\vec E_{Hall}=\dfrac{1}{nq}\vec B\times\vec J$ ($J$: mật độ dòng, $n$: mật độ hạt tải, $q$: điện tích hạt tải).
- *Tham chiếu:* Kiisk ül. 167–174 (mục 7.2), đặc biệt ül. 172.

## II.3 Cảm ứng điện từ

**TM II.3.1 — Định luật Faraday & định luật Lenz**
- *Phát biểu:* $\mathcal E=-d\Phi/dt$, $\Phi=\int\vec B\cdot d\vec S$. Dấu trừ ⇒ dòng cảm ứng chống lại biến thiên từ thông.
- *Quy trình:* (1) chọn pháp tuyến dương cho mặt $S$ (⇒ xác định nhất quán chiều dương của $\Phi$ và dòng cảm ứng); (2) tính $\Phi(t)$; (3) đạo hàm.
- *Hai nguồn gốc của $d\Phi/dt$:* (a) $B$ biến thiên tại vị trí cố định ⇒ điện trường xoáy, $\oint\vec E\cdot d\vec l=-\partial\Phi/\partial t$; (b) mạch thay đổi hình học/vị trí trong $B$ không đổi ⇒ sđđ chuyển động trên từng đoạn dây, $d\mathcal E=(\vec v\times\vec B)\cdot d\vec l$.
- *Tham chiếu:* Kiisk ül. 135–137.

**TM II.3.2 — Suất điện động chuyển động (trường hợp riêng thường gặp)**
- *Phát biểu:* thanh dẫn dài $l$, vận tốc $v\perp B$, trên 2 ray dẫn: $\mathcal E=Blv$.
- *Tham chiếu:* Kiisk ül. 136.

## II.4 Tự cảm

**TM II.4.1 — Định nghĩa độ tự cảm & phương trình mạch**
- *Phát biểu:* $\Phi=LI$ (nhiều vòng: $\Phi=N\varphi_{1vòng}$); $U=L\,dI/dt$.
- *Tham chiếu:* Kiisk pt. (7); ül. 138–141.

**TM II.4.2 — Hằng số thời gian mạch RL** (hoàn toàn tương tự TM I.6.1, đổi vai trò $U\leftrightarrow I$)
- *Phát biểu:* $\tau=L/R_{tđ}$ ($R_{tđ}$ nhìn từ 2 đầu cuộn cảm, nguồn sđđ nối tắt). **Dòng qua cuộn cảm không nhảy bậc** (liên tục) — đóng vai trò như $U$ trên tụ.
- *Quy trình:* áp dụng đúng 4 bước của TM I.6.1, thay $U_{tụ}\to I_{cuộn}$.
- *Tham chiếu:* Kiisk ül. 138–141.

**TM II.4.3 — Năng lượng từ trường**
- *Phát biểu:* $W=LI^2/2$; mật độ năng lượng từ trường $w=B^2/2\mu_0$.
- *Tham chiếu:* Kiisk ül. 143.

**TM II.4.4 — Hỗ cảm (Mutual inductance)**
- *Phát biểu:* $\Phi_1=L_1I_1+MI_2$, $\Phi_2=L_2I_2+MI_1$ ($M_{12}=M_{21}=M$ — định lý tương hỗ luôn đúng); $M\le\sqrt{L_1L_2}$ (dấu = khi ghép chặt hoàn toàn).
- *Tham chiếu:* Kiisk ül. 145–149.

**TM II.4.5 — Máy biến áp lý tưởng**
- *Phát biểu:* $U_2/U_1=n=N_2/N_1$; $I_2/I_1=1/n$ (điều kiện: $L_1,L_2\to\infty$, ghép chặt hoàn toàn, không tổn hao).
- *Tham chiếu:* Kiisk ül. 158.

**TM II.4.6 — Điều kiện cực trị dòng/áp trong mạch L, C**
- *Phát biểu:* dòng cực trị qua cuộn cảm ⇒ $dI/dt=0$ ⇒ sđđ cảm ứng = 0. Áp cực trị trên tụ ⇒ $dU/dt=0$ ⇒ dòng qua tụ = 0.
- *Dùng để:* làm điều kiện biên, tránh giải ODE đầy đủ.
- *Tham chiếu:* Kiisk ül. 150, 151.

## II.5 Dòng điện xoay chiều

**TM II.5.1 — Giá trị hiệu dụng (RMS)**
- *Phát biểu:* $I_{eff}=\sqrt{\langle I^2\rangle}$; dòng sin: $I_{eff}=I_0/\sqrt2$.
- *Tham chiếu:* Kiisk mục 6.1.

**TM II.5.2 — Phương pháp trở kháng phức (phasor)** *— Toy Model trung tâm của cả chương AC*
- *Phát biểu:* $\tilde Z_R=R$; $\tilde Z_L=i\omega L$; $\tilde Z_C=1/(i\omega C)$. Ohm & Kirchhoff áp dụng y hệt mạch một chiều nhưng với số phức.
- *Quy trình:* (1) chuyển mọi phần tử sang trở kháng phức; (2) giải mạch bằng **toàn bộ kỹ thuật của Phần I.4** (nối tiếp/song song, Kirchhoff, Thevenin, Δ-Y...) nhưng với số phức; (3) biên độ = $|\tilde Z|$, lệch pha = $\arg(\tilde Z)$; (4) công suất trung bình $P=\frac12\text{Re}(\tilde U\tilde I^*)=U_{eff}I_{eff}\cos\Delta\varphi$.
- *Tham chiếu:* Kiisk ül. 155–158.

**TM II.5.3 — Cộng hai dao động điều hòa cùng tần số**
- *Phát biểu:* $A_1\cos(\omega t+\varphi_1)+A_2\cos(\omega t+\varphi_2)=A\cos(\omega t+\varphi)$, tính $A,\varphi$ như cộng 2 vector phẳng (giản đồ Fresnel).
- *Tham chiếu:* Kiisk mục 6.2.

**TM II.5.4 — Cộng hưởng mạch LC/LCR**
- *Phát biểu:* $\omega_{res}=1/\sqrt{LC}$. Mạch nối tiếp: $Z\to 0$ tại cộng hưởng (cộng hưởng áp). Mạch song song: $Z\to\infty$ (cộng hưởng dòng). Có $R$: đỉnh cộng hưởng bị "làm tù" nhưng $\omega_{res}$ không đổi.
- *Tham chiếu:* Kiisk mục 6.4, ül. 159–161.

**TM II.5.5 — Dao động tự do mạch LC kín**
- *Phát biểu:* $d^2Q/dt^2+\omega^2Q=0$, $\omega^2=1/LC$ — dao động điều hòa của điện tích/dòng/áp.
- *Tham chiếu:* Kiisk ül. 159–161.

---
---

# PHẦN III — ĐIỆN TỪ NÂNG CAO *(Học trong khoá Chuyên sâu)*

## III.1 Định lí O–G (Gauss)

**TM III.1.1 — Định lý Gauss dạng tích phân**
- *Phát biểu:* $\oint_S E_n\,dS=Q_{trong}/\varepsilon_0$.
- *Quy trình "tầm thường" (chỉ hoạt động khi có đối xứng phẳng/trụ/cầu):* (1) xác định phương $\vec E$ từ đối xứng; (2) chọn mặt Gauss sao cho $E$ hằng số & song song pháp tuyến trên từng phần mặt; (3) tích phân → phép nhân $E\cdot S$; (4) giải ra $E$.
- *Kết quả đóng gói sẵn (không suy lại mỗi lần):*
  - Mặt phẳng vô hạn, mật độ mặt $\sigma$: $E=\sigma/2\varepsilon_0$ (mỗi phía);
  - Tụ phẳng: $E=\sigma/\varepsilon_0$ giữa 2 bản, $E=0$ ngoài;
  - Dây thẳng vô hạn, mật độ dài $\lambda$: $E=\lambda/2\pi\varepsilon_0 r$;
  - Mặt cầu (vỏ mỏng) $Q$: $E=0$ ($r<R$); $E=kQ/r^2$ ($r\ge R$);
  - Khối cầu đặc $\rho$: $E=\rho r/3\varepsilon_0$ ($r<R$); $E=\rho R^3/3\varepsilon_0 r^2$ ($r\ge R$);
  - Trụ đặc dài vô hạn $\rho$: $E=\rho r/2\varepsilon_0$ ($r<R$); $E=\rho R^2/2\varepsilon_0 r$ ($r\ge R$).
- *Tham chiếu:* Kiisk ül. 67–74.

**TM III.1.2 — Kỹ thuật "hốc rỗng" (chồng chất 2 phân bố ± lệch tâm)**
- *Phát biểu:* hốc cầu lệch tâm $\vec r_0$ trong khối cầu tích điện đều $\rho$ ⇒ trường trong hốc **đều**: $\vec E=\rho\vec r_0/3\varepsilon_0$. Tương tự cho 2 trụ/cầu tích điện trái dấu lệch tâm giao nhau.
- *Quy trình:* coi hốc = khối đặc $\rho$ (không hốc) **chồng chất với** khối nhỏ mật độ $-\rho$ lấp đúng vị trí hốc; cộng vector 2 trường.
- *Tham chiếu:* Kiisk ül. 75, 76.

**TM III.1.3 — Áp suất tĩnh điện trên bề mặt tích điện**
- *Phát biểu:* $p=\sigma^2/2\varepsilon_0$ (dùng $E/2$ — nửa trường tổng — làm "trường ngoài" tác dụng lên chính điện tích mặt, tránh nghịch lý tự-lực).
- *Tham chiếu:* Kiisk ül. 79, 80.

## III.2 Thế năng tương tác của hệ điện tích

**TM III.2.1 — Công thức tổng quát**
- *Phát biểu:* $\Pi=\frac12\sum_i\varphi_i q_i$; với vật dẫn/tụ có $\varphi$ đồng nhất trên toàn vật: $\Pi=\frac12 Q\varphi$ mỗi vật, cộng lại.
- *Tham chiếu:* Kiisk ül. 93.

**TM III.2.2 — Mật độ năng lượng trường tĩnh điện**
- *Phát biểu:* $w=\varepsilon_0E^2/2$ (chân không); $w=\varepsilon\varepsilon_0E^2/2$ (điện môi). Năng lượng toàn hệ $=\int w\,dV$.
- *Dùng để:* kiểm tra chéo TM III.2.1, hoặc tính trực tiếp khi biết $E(\vec r)$ khắp không gian.
- *Tham chiếu:* Kiisk ül. 92.

## III.3 Lí thuyết lưỡng cực điện

**TM III.3.1 — Mô-men lưỡng cực & trường lưỡng cực**
- *Phát biểu:* $\vec p=q\vec d$ ($\vec d$: từ $-q$ đến $+q$). Trường tại $(r,\theta)$, $r\gg d$: $E_r=2p\cos\theta/4\pi\varepsilon_0 r^3$, $E_\theta=p\sin\theta/4\pi\varepsilon_0 r^3$. Thế: $\varphi(\vec r)=\vec p\cdot\hat r/4\pi\varepsilon_0 r^2$.
- *Tham chiếu:* Kiisk ül. 81–83, 94.

**TM III.3.2 — Lưỡng cực trong trường ngoài**
- *Phát biểu:* $\vec M=\vec p\times\vec E$; $\Pi=-\vec p\cdot\vec E$; trường không đều: $F_x=p\,\partial E/\partial x$.
- *Tham chiếu:* Kiisk ül. 84–87.

**TM III.3.3 — Vật phân cực nhìn từ xa ≈ lưỡng cực điểm**
- *Phát biểu:* quả cầu dẫn/điện môi phân cực trong trường đều $E_0$, nhìn từ xa, tạo trường bổ sung giống hệt 1 lưỡng cực điểm tại tâm.
- *Tham chiếu:* Kiisk ül. 104, 105 (vật dẫn — xem III.5); ül. 113 (điện môi).

## III.4 Điện môi

**TM III.4.1 — $D$, $\varepsilon$ và điều kiện biên**
- *Phát biểu:* $\vec D=\varepsilon\varepsilon_0\vec E$. Mặt phân cách 2 môi trường, không điện tích tự do: $D_n$ liên tục, $E_\tau$ liên tục.
- *Tham chiếu:* Kiisk mục 3.8.

**TM III.4.2 — Điện môi trong trường đều: phiến/trụ/cầu** (đóng gói)
- *Phát biểu:*
  - Phiến phẳng, pháp tuyến hợp góc $\theta$ với $E_0$: $E_\parallel=E_0\sin\theta$; $E_\perp=E_0\cos\theta/\varepsilon$;
  - Trụ dài, trục $\parallel E_0$: $E=E_0$; trục $\perp E_0$: $E=2E_0/(\varepsilon+1)$;
  - Cầu: $E=3E_0/(\varepsilon+2)$.
- *Quy trình:* giả sử trường trong vật đồng nhất (đúng cho 3 hình dạng này); vật = chồng chất 2 khối tích điện lệch nhẹ (TM III.1.2); khớp điều kiện biên $D_n,E_\tau$ để tìm $E$ trong.
- *Tham chiếu:* Kiisk ül. 111–113.

**TM III.4.3 — Lực hút điện môi vào vùng trường mạnh (dịch chuyển ảo cho điện môi)**
- *Phát biểu (trường hợp mép tụ phẳng, bề rộng phiến $a$, $U$ cố định):* $F=(\varepsilon-1)\varepsilon_0 aU^2/2d$.
- *Tham chiếu:* Kiisk ül. 53, 110, 115.

**TM III.4.4 — Phương pháp ảnh điện trong điện môi**
- *Phát biểu:* điện tích $q$ gần mặt phân cách $\varepsilon_1,\varepsilon_2$ ⇒ trong môi trường 1: trường = trường của $q$ + ảnh $q'=\dfrac{\varepsilon_1-\varepsilon_2}{\varepsilon_1+\varepsilon_2}q$ (đối xứng gương); trong môi trường 2: trường = trường của điện tích hiệu dụng $q''=\dfrac{2\varepsilon_1}{\varepsilon_1+\varepsilon_2}q$ tại đúng vị trí $q$.
- *Tham chiếu:* Kiisk ül. 114.

## III.5 Vật dẫn

**TM III.5.1 — Ba tính chất cơ bản của vật dẫn cân bằng tĩnh điện**
- *Phát biểu:* (1) $E=0$ trong vật dẫn; (2) điện tích dư chỉ ở bề mặt; (3) vật dẫn là mặt đẳng thế, $E\perp$ bề mặt bên ngoài.
- *Tham chiếu:* Kiisk mục 3.6.

**TM III.5.2 — Điện dung vật dẫn cô lập**
- *Phát biểu:* $C=Q/\varphi$ ($\varphi$ đo so với vô cực). Quả cầu bán kính $R$: $C=4\pi\varepsilon_0R$.
- *Tham chiếu:* Kiisk ül. 98–101.

**TM III.5.3 — Phương pháp ảnh điện trong vật dẫn**
- *Phát biểu & công thức đóng gói:*
  - $q$ cách mặt phẳng dẫn nối đất khoảng $h$: ảnh $-q$ đối xứng gương; lực hút $F=q^2/16\pi\varepsilon_0h^2$;
  - $q$ cách tâm quả cầu dẫn nối đất bán kính $R$ khoảng $d>R$: ảnh $q'=-Rq/d$ tại khoảng cách $R^2/d$ từ tâm. Quả cầu **cô lập** (không nối đất): thêm ảnh thứ 2 tại tâm để đúng tổng điện tích.
- *Quy trình:* (1) đoán vị trí ảnh theo hình học biên (phẳng/cầu/trụ); (2) xác định độ lớn ảnh bằng 1 trong 2 điều kiện tương đương ($E\perp$ bề mặt HOẶC bề mặt đẳng thế); (3) trường/lực **ngoài** vật dẫn = trường điện tích thật + ảnh (bỏ ảnh khi xét **trong** vật dẫn, ở đó vốn $E=0$).
- *Tham chiếu:* Kiisk ül. 102, 103, 106, 107, 108.

**TM III.5.4 — Vật dẫn cầu/trụ trong trường ngoài đều**
- *Phát biểu:* mặt cầu dẫn bán kính $R$ trong $E_0$ đều: $E_r=(2R^3/r^3+1)E_0\cos\theta$, $E_\theta=(R^3/r^3-1)E_0\sin\theta$, $\sigma(\theta)=3\varepsilon_0E_0\cos\theta$. (Trụ: công thức tương tự với số mũ 2 thay vì 3.)
- *Tham chiếu:* Kiisk ül. 104 (cầu), 105 (trụ).

## III.6 Mạch 1 chiều, phi tuyến

*(Kỹ thuật mạch 1 chiều "cơ bản" đã có ở I.4; mục này bổ sung phần tử phi tuyến — điểm mà Kiisk 2017 tự nhận là không phủ hết toàn bộ nhu cầu mạch điện của kỳ thi.)*

**TM III.6.1 — Phần tử phi tuyến & đường đặc trưng V–A**
- *Phát biểu:* $P=UI$ luôn đúng; nhưng $P=I^2R=U^2/R$ **không** đúng trừ khi $R$=const cục bộ.
- *Tham chiếu:* Kiisk mục 1.5.

**TM III.6.2 — Mô hình diode & quy trình "đoán–kiểm tra"**
- *Phát biểu:* diode lý tưởng: $R=0$ thuận, $R=\infty$ ngược. Mô hình ngưỡng $U_d$: mở hẳn khi $U=U_d$, đóng hoàn toàn khi $U<U_d$.
- *Quy trình "tầm thường hóa" bài toán phi tuyến:* (1) đoán trạng thái mỗi diode (dẫn/không dẫn); (2) giải mạch tuyến tính tương ứng; (3) kiểm tra tự hợp: diode giả định dẫn ⇒ dòng qua nó phải dương; diode giả định khóa ⇒ điện áp ngược đặt lên nó phải $<U_d$; (4) nếu mâu thuẫn, đổi giả định, lặp lại.
- *Tham chiếu:* Kiisk ül. 34–38.

**TM III.6.3 — Phương pháp đồ thị (đường tải — load line)**
- *Phát biểu:* phần tử phi tuyến nối tiếp $R$ và nguồn $\mathcal E$: $IR=\mathcal E-U$ (đường thẳng) giao đường đặc trưng $I(U)$ tại nghiệm.
- *Quy trình:* vẽ đường thẳng qua 2 điểm $(U=0,I=\mathcal E/R)$ và $(I=0,U=\mathcal E)$; tìm giao điểm với đồ thị $I(U)$ cho trước.
- *Tham chiếu:* Kiisk ül. 36, 38.

**TM III.6.4 — Điện trở vi phân & ổn định nghiệm** *[ưu tiên ôn thấp — hiếm gặp ở VPHO]*
- *Phát biểu:* $R_{diff}=dU/dI$ tại điểm làm việc; $R_{diff}<0$ ⇒ nghiệm có thể mất ổn định (thyristor, tunnel-diode, hysteresis).
- *Tham chiếu:* Kiisk ül. 39, 40.

## III.7 Dao động điện từ, điốt

**TM III.7.1 — Mạch chỉnh lưu diode + tụ lọc** (kết hợp TM I.6.1 + TM III.6.2)
- *Tham chiếu:* Kiisk ül. 60, 150.

**TM III.7.2 — Dao động LC lý tưởng & tắt dần định tính** (xem lại TM II.5.4, II.5.5)
- *Bổ sung định tính [BỔ SUNG — vượt phạm vi gốc Kiisk, mức tùy chọn]:* thêm $R$ nối tiếp nhỏ ⇒ dao động tắt dần, biên độ ∝ $e^{-Rt/2L}$; tần số gần đúng không đổi nếu $R\ll\sqrt{L/C}$ (chế độ dưới tới hạn).

## III.8 Chữa bài tập trong bộ sách "Điện cầu vồng"

Mục này **không phải** một Toy Model/Lý thuyết mới, mà là hoạt động **luyện tập tổng hợp**: áp dụng toàn bộ TM ở Phần I–III vào bộ đề tương ứng. Quy trình đề xuất: với mỗi bài, (1) tra Phần 0.5 hoặc Phụ lục A để xác định TM nghi ngờ cần dùng; (2) làm theo đúng "Quy trình áp dụng" của TM đó; (3) nếu không khớp TM nào trong danh sách — đây là tín hiệu cần bổ sung tài liệu (xem Phụ lục C).

---
---

# PHỤ LỤC A — BẢNG NHẬN DIỆN NHANH (Pattern → Toy Model)

*(Bảng này là công cụ thực chiến quan trọng nhất — hỗ trợ trực tiếp mục 1.1 "Pattern Recognition" và tính khả thi 1.5. Dùng để quét đề bài, khoanh vùng TM cần dùng trong 10–30 giây.)*

| Dấu hiệu / từ khóa trong đề | Toy Model gợi ý |
|---|---|
| Đối xứng cầu/trụ/phẳng, phân bố điện tích đều | III.1.1 (Gauss) |
| Hốc rỗng lệch tâm trong vật tích điện đều | III.1.2 |
| Hai quả cầu tích điện, tương tác | I.1.4, III.1.1 |
| Mạch cầu, không rút gọn được nối tiếp/song song | I.4.6 (Δ–Y), I.4.9 (đối xứng) |
| Mạch tuần hoàn / vô hạn | I.4.11, I.4.12 |
| "Ngay sau khi K đóng/mở", "vừa đóng công tắc" | I.6.1 / II.4.2 — dùng giá trị **đầu** (liên tục) |
| "Sau thời gian dài", "trạng thái xác lập/ổn định" | I.6.1 / II.4.2 — dùng giá trị **cuối** |
| Diode, đường đặc trưng V–A | III.6.2, III.6.3 |
| Quả cầu/trụ điện môi trong trường đều | III.4.2 |
| Vật dẫn gần mặt phẳng/quả cầu nối đất, "ảnh điện" | III.5.3 |
| Cuộn dây, sđđ tự cảm, "vừa ngắt dòng" | II.4 |
| Biến áp, 2 cuộn dây chung lõi | II.4.4, II.4.5 |
| Cộng hưởng, tần số góc $\omega$ thay đổi | II.5.4 |
| Hạt tích điện bay vào vùng có từ trường | II.2.5, II.2.6 |
| Hiệu ứng Hall, tấm dẫn trong từ trường có dòng | II.2.7 |
| Cần tìm lực bằng đạo hàm năng lượng theo 1 biến hình học | I.3.4, III.4.3 (dịch chuyển ảo) |
| Bài yêu cầu nhiệt lượng tỏa ra qua quá trình chuyển tiếp | I.6.2 |
| Mạch không tuyến tính hoàn toàn nhưng có thể tuyến tính hóa quanh 1 điểm | III.6.4 |
| Dòng xoay chiều, pha lệch, trở kháng | II.5.2 (số phức) |
| Cần điện thế trước rồi mới ra điện trường | I.2.1 |

---

# PHỤ LỤC B — CÔNG THỨC TRA CỨU (rút gọn theo từng Phần)

**Tĩnh điện – Mạch DC (Phần I):** $F=k_eq_1q_2/r^2$ • $Q=CU$, $\Pi_C=CU^2/2$ • $C_{ss}=\sum C_i$, $1/C_{nt}=\sum 1/C_i$ • $R_{nt}=\sum R_i$, $1/R_{ss}=\sum 1/R_i$ • $P=UI=I^2R=U^2/R$ • $V=\mathcal E-Ir$ • $U(t)=U(\infty)+[U(0)-U(\infty)]e^{-t/RC}$.

**Từ học (Phần II):** $dB=\dfrac{\mu_0I}{4\pi}\dfrac{d\vec l\times\hat r}{r^2}$ • $B_{dây}=\mu_0I/2\pi r$ • $B_{solenoid}=\mu_0nI$ • $\vec F=q\vec v\times\vec B$ • $F/L=\mu_0I_1I_2/2\pi r$ • $\mathcal E=-d\Phi/dt$ • $\Phi=LI$ • $W_L=LI^2/2$ • $\tilde Z_L=i\omega L$, $\tilde Z_C=1/i\omega C$ • $\omega_{res}=1/\sqrt{LC}$ • $R_{cyclotron}=mv/qB$.

**Nâng cao (Phần III):** $E_{mặt phẳng}=\sigma/2\varepsilon_0$ • $E_{cầu đặc}$, $E_{trụ đặc}$ (xem III.1.1) • $\Pi=\frac12\sum\varphi_iq_i$ • $w=\varepsilon_0E^2/2$ • $\vec p=q\vec d$; $\vec M=\vec p\times\vec E$, $\Pi=-\vec p\cdot\vec E$ • $\vec D=\varepsilon\varepsilon_0\vec E$ • $C_{cầu cô lập}=4\pi\varepsilon_0R$ • ảnh điện: $q'=-Rq/d$ tại $R^2/d$ (cầu nối đất); $q'=-q$ đối xứng gương (mặt phẳng nối đất).

---

# PHỤ LỤC C — CHECKLIST TRƯỚC KHI VÀO PHÒNG THI (đảm bảo mục 1.5)

1. Đã thuộc lòng (không cần tra) toàn bộ công thức "đóng gói sẵn" ở Phụ lục B chưa?
2. Với mỗi TM ở Phần I–III, đã tự làm ít nhất 2–3 bài tham chiếu trong Kiisk (2017) chưa?
3. Đã luyện quy trình 4 bước cho mạch RC/RL transient (TM I.6.1/II.4.2) đến mức phản xạ chưa?
4. Đã luyện quy trình "đoán–kiểm tra" cho mạch diode (TM III.6.2) với ít nhất 3 mạch khác nhau chưa?
5. Đã đọc đề cương VPHO (Phần 0.5) để biết mục nào **không** nằm trong phạm vi thi (ví dụ: mạng vô hạn 2D/3D — I.4.12; hysteresis — III.6.4) để không mất thời gian ôn quá sâu chỗ ít điểm?
6. Có thói quen đọc đề theo kiểu quét "pixel" (không bỏ sót chi tiết số liệu/hình vẽ nào — theo đúng yêu cầu mục 1.3) chưa?

---

# PHỤ LỤC D — GHI CHÚ VỀ TÍNH "ĐẦY ĐỦ" (mục 1.4) & GIỚI HẠN CỦA TÀI LIỆU

**D.1. Cơ sở của tuyên bố "đầy đủ".** Toàn bộ TM ở Phần I–III được xây dựng từ Kiisk (2017) — tài liệu tự xác nhận nằm trong phạm vi Đề cương IPHO, vốn rộng hơn hẳn phạm vi VPHO về Điện–Từ. Bảng đối chiếu ở Phần 0.5 khớp **từng mục** của đề cương VPHO (theo đúng 2 ảnh gốc) với ít nhất một nhóm TM cụ thể — không có mục nào trong đề cương bị bỏ trống. Do đó, trong khuôn khổ giả định "đề thi VPHO chỉ ra bài trong phạm vi đề cương đã công bố", tập TM này thỏa điều kiện 1.4.

**D.2. Phần đã [BỔ SUNG] ngoài Kiisk (2017)** — đúng theo lưu ý "tài liệu này không đầy đủ về ELECTRICAL CIRCUITS":
- Phát biểu tường minh định lý Thevenin/Norton như 1 TM độc lập (TM I.4.7) — Kiisk chỉ có phần rời rạc;
- Quy trình "đoán–kiểm tra" hệ thống cho mạch nhiều diode (TM III.6.2) — Kiisk có ví dụ nhưng không đúc thành quy trình chung;
- Ghi chú định tính về dao động tắt dần RLC (TM III.7.2) — Kiisk chỉ có LC lý tưởng, không có R.

**D.3. Nội dung có trong Kiisk (2017) nhưng nằm ngoài 2 ảnh đề cương VPHO đã cung cấp** (không bị xóa, chỉ bị hạ ưu tiên và ghi chú "phạm vi IPHO"): mạng vô hạn 2D/3D (I.4.12), điện trở âm hình thức (I.4.13), hysteresis/tunnel-diode (III.6.4), quỹ đạo cycloid đầy đủ trong $E,B$ vuông góc (một phần của II.2.6). Nếu đề cương VPHO thực tế (bản đầy đủ, không chỉ 2 ảnh chụp một phần) có bổ sung các mục này, chỉ cần nâng độ ưu tiên ôn luyện, KHÔNG cần bổ sung TM mới vì đã có sẵn trong tài liệu.

**D.4. Không overfitting vào file cũ.** Tài liệu này được xây dựng lại từ đầu dựa trên Kiisk (2017) + đề cương VPHO, **không** kế thừa trực tiếp nội dung của "prom2.Cơ & Điện-Từ học v2A+.md" như đã yêu cầu.

**D.5. Giới hạn còn tồn tại (trung thực, theo đúng tinh thần mục 1.5 — không tô hồng tính khả thi).** Tài liệu chưa bao gồm: (a) bộ đề luyện tập trực tiếp bằng tiếng Việt bám sát định dạng câu hỏi VPHO (Kiisk 2017 là tài liệu tiếng Estonia, số liệu/đơn vị/văn phong đề bài khác VPHO); (b) các bài tập tổng hợp nhiều TM cùng lúc ở mức độ khó tương đương vòng 2 VPHO. Đây là công việc **luyện tập** (mục III.8), không phải thiếu sót về mặt lý thuyết.
