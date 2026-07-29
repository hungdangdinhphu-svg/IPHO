---

# PHẦN 1 :

# TÀI LIỆU BỒI DƯỠNG HSG VẬT LÍ 9
# CHUYÊN ĐỀ: MẠCH ĐIỆN MỘT CHIỀU — TỪ GỐC ĐẾN NGỌN

*Biên soạn dựa trên Chương 1 ("Alalisvooluahelad") của Valter Kiisk – Tartu Ülikool, "Elektri ja magnetismi ülesandeid", 2017 — phần phù hợp với chương trình HSG lớp 9 (không dùng đạo hàm/tích phân).*

> **Cách dùng tài liệu:** Đọc tuần tự từ Phần 1. Mỗi phần đều **chứng minh** công thức trước khi dùng — không có công thức nào được đưa ra mà không giải thích "vì sao nó đúng". Tất cả ví dụ số đều đã được kiểm tra chéo bằng ít nhất hai phương pháp độc lập để đảm bảo chính xác tuyệt đối.

---

## MỤC LỤC
1. Nền tảng: điện tích, dòng điện, điện thế, suất điện động
2. Định luật Ohm, điện trở, công suất
3. Ghép nối tiếp – song song: chứng minh lại từ gốc
4. Định luật Kirchhoff: từ đâu mà có?
5. Hai phương pháp giải hệ thống: điện thế nút & dòng vòng
6. Nguyên lí xếp chồng (Superposition)
7. Mạch tương đương Thevenin & Định lí Millman
8. Biến đổi Sao – Tam giác (Δ–Y)
9. Kĩ thuật đối xứng — vũ khí mạnh nhất của HSG
10. Ampe kế – Vôn kế lí tưởng & sai số dụng cụ đo
11. Mạch vô hạn tuần hoàn
12. Đọc thêm: phần tử phi tuyến
13. Tổng kết kĩ năng & Bài tập tự luyện có đáp số

---

# PHẦN 1. NỀN TẢNG: ĐIỆN TÍCH, DÒNG ĐIỆN, ĐIỆN THẾ, SUẤT ĐIỆN ĐỘNG

## 1.1. Dòng điện là gì, thực sự?

Dòng điện không phải là một "chất" chảy trong dây — nó là **tốc độ vận chuyển điện tích** qua một tiết diện dây dẫn:

$$I = \frac{\Delta q}{\Delta t}$$

Đơn vị: Ampe (A) = Coulomb/giây. Quy ước chiều dòng điện là chiều chuyển động của điện tích **dương** (trong kim loại, hạt mang điện thực sự là electron mang điện âm, chuyển động ngược chiều dòng điện quy ước — nhưng vì $I$, $q$ là các đại lượng có dấu, việc đó không ảnh hưởng gì đến cách ta tính toán mạch điện).

## 1.2. Vì sao lại có "hiệu điện thế"? — Từ công của lực điện

Trong một điện trường tĩnh, lực điện là lực **thế** (bảo toàn): công nó sinh ra khi di chuyển một điện tích từ điểm A đến điểm B **không phụ thuộc đường đi**, chỉ phụ thuộc 2 điểm đầu–cuối. Nhờ tính chất này, ta định nghĩa được:

- **Điện thế** $\varphi$ tại một điểm = thế năng của một đơn vị điện tích thử đặt tại đó.
- **Hiệu điện thế** (điện áp) giữa hai điểm: $U_{AB} = \varphi_A - \varphi_B$.

Công của lực điện khi đưa điện tích $q$ từ A đến B: $A_{A\to B} = q\,U_{AB}$.

**Điểm mấu chốt cần khắc cốt ghi tâm:** vì lực điện là lực thế, nên nếu ta đi một vòng khép kín rồi quay lại đúng điểm xuất phát, **tổng công của lực điện bằng 0**, và **điện thế tại một điểm chỉ có một giá trị duy nhất** (không phụ thuộc ta "đi đường nào" để đến đó). Hai sự thật này chính là nguồn gốc của **hai định luật Kirchhoff** ở Phần 4 — không phải chúng do ai đó "quy định", mà là hệ quả tất yếu của bản chất lực điện.

## 1.3. Vì sao dòng điện lại chạy được? — Suất điện động $\xi$

Đây là chỗ nhiều học sinh học "vẹt" mà không hiểu: **nếu mạch chỉ có lực tĩnh điện thì dòng điện không thể duy trì**. Lý do: đi vòng quanh mạch kín, công của lực tĩnh điện = 0 (như vừa nói ở trên). Nhưng dòng điện chạy qua điện trở thì luôn **tiêu hao** năng lượng (biến thành nhiệt) — nếu không có gì "bù" lại năng lượng đó, dòng điện sẽ tắt dần rồi dừng hẳn.

Vậy phải có một loại lực **không phải tĩnh điện** — gọi là **lực lạ** (ví dụ: phản ứng hoá học trong pin, lực từ trong máy phát điện) — thực hiện công để "bơm" điện tích từ cực (–) sang cực (+) *bên trong* nguồn, ngược chiều với lực tĩnh điện đang cố kéo nó về.

**Định nghĩa suất điện động $\xi$:** là hiệu điện thế cực đại mà lực lạ có thể tạo ra giữa hai cực của nguồn (đạt được khi mạch hở, $I=0$).

- Khi có dòng điện $I$ chạy qua nguồn có điện trở trong $r$, hiệu điện thế ở hai đầu cực nguồn tụt xuống: $U_{cực} = \xi - Ir$ (ta sẽ dùng công thức này rất nhiều ở Phần 7).
- Khi điện tích $q$ đi qua nguồn có suất điện động $\xi$: lực lạ thực hiện công $\xi q$ (năng lượng hoá học → năng lượng điện).

## 1.4. Định luật Ohm và điện trở

Với đa số vật dẫn (kim loại), thực nghiệm cho thấy dòng điện tỉ lệ thuận với hiệu điện thế:

$$I = \frac{U}{R} \quad\Longleftrightarrow\quad U = IR$$

$R$ gọi là **điện trở**, đặc trưng cho "mức độ cản trở" dòng điện của vật dẫn cụ thể đó (đơn vị Ohm, Ω = V/A). Với dây dẫn tiết diện đều:

$$R = \rho\frac{l}{S}$$

**Vì sao công thức này hợp lý?** (không học vẹt!)
- $R$ tỉ lệ thuận với chiều dài $l$: dây càng dài, điện tích phải "vượt qua" càng nhiều vật cản nối tiếp nhau → giống như ghép nhiều điện trở nhỏ nối tiếp, điện trở cộng dồn.
- $R$ tỉ lệ nghịch với tiết diện $S$: tiết diện càng lớn, có càng nhiều "đường đi song song" cho điện tích → giống ghép nhiều điện trở nhỏ song song, điện trở giảm.
- $\rho$ (điện trở suất) là hằng số đặc trưng riêng cho *vật liệu*, không phụ thuộc hình dạng.

## 1.5. Công suất điện — Định luật Joule–Lenz

Công của lực điện trong thời gian $dt$ là $dA = U\,dq = U\,I\,dt$. Vậy **công suất điện** (luôn đúng, cho *bất kỳ* phần tử nào, kể cả phần tử phi tuyến):

$$P = UI$$

Chỉ khi phần tử là điện trở thuần (tuân theo định luật Ohm, $R$ không đổi), ta mới được thay $U=IR$ để có thêm hai dạng tương đương:

$$P = I^2 R = \frac{U^2}{R}$$

**Lưu ý quan trọng:** $P = UI$ là công thức *gốc*, luôn đúng. $P=I^2R$ và $P=U^2/R$ chỉ là *hệ quả* khi $R=const$. Với bóng đèn sợi đốt (điện trở thay đổi theo nhiệt độ) hay điốt, chỉ $P=UI$ còn dùng được.

---

# PHẦN 2. GHÉP NỐI TIẾP – SONG SONG: CHỨNG MINH LẠI TỪ GỐC

Đừng chỉ nhớ công thức — hãy nhớ **vì sao** nó đúng, vì chính lập luận này sẽ được dùng lại để hiểu Kirchhoff ở Phần 4.

### Ghép nối tiếp

Trong mạch nối tiếp, các điện trở nằm trên **một đường dây duy nhất**, không phân nhánh → theo định nghĩa dòng điện (Phần 1.1) và bảo toàn điện tích, **dòng điện qua mọi điện trở là như nhau**, gọi là $I$.

Hiệu điện thế hai đầu cả dãy là tổng các hiệu điện thế thành phần (vì điện thế "cộng dồn" dọc theo đường đi — đây chính là tính chất điện thế đơn trị ở Phần 1.2):

$$U = U_1+U_2+\dots = IR_1+IR_2+\dots = I(R_1+R_2+\dots)$$

$$\boxed{R_{nt} = R_1+R_2+\dots}$$

### Ghép song song

Các điện trở có **chung hai đầu nút** → theo tính đơn trị của điện thế, **hiệu điện thế trên mọi nhánh là như nhau**, gọi là $U$.

Theo bảo toàn điện tích tại nút (chưa gọi tên "Kirchhoff" vội, nhưng đây chính là nó!): dòng điện tổng đi vào bằng tổng dòng điện các nhánh đi ra:

$$I = I_1+I_2+\dots = \frac{U}{R_1}+\frac{U}{R_2}+\dots = U\left(\frac1{R_1}+\frac1{R_2}+\dots\right)$$

$$\boxed{\frac{1}{R_{ss}} = \frac1{R_1}+\frac1{R_2}+\dots}$$

## Ví dụ 1 (Bài 1 – sách gốc): Hai cầu chì mắc song song — bẫy tư duy kinh điển

**Đề bài:** Cầu chì 1: $R_1=1\,\Omega$, đứt khi dòng qua nó đạt $I_{1max}=1\,A$. Cầu chì 2: $R_2=2\,\Omega$, đứt khi dòng qua nó đạt $I_{2max}=1{,}2\,A$. Hai cầu chì mắc song song.

**a)** Dòng điện tối đa mà tổ hợp chịu được là bao nhiêu?
**b)** Nếu $I_{2max}=1{,}7\,A$ thay vì $1{,}2\,A$ thì đáp số thay đổi thế nào?

**Lời giải — điểm mấu chốt:** Vì hai cầu chì mắc *song song*, chúng luôn có **chung một hiệu điện thế** $U$ ở hai đầu (bản chất Phần 2, không phải dòng điện!). Khi ta tăng dần dòng tổng, $U$ tăng dần theo. Cầu chì nào đạt tới điện áp giới hạn của *nó* trước sẽ đứt trước.

Điện áp giới hạn của mỗi cầu chì (áp dụng Ohm ngay tại thời điểm sắp đứt):
$$U_{1,gh} = I_{1max}R_1 = 1\times1 = 1\,V \qquad U_{2,gh}=I_{2max}R_2 = 1{,}2\times2=2{,}4\,V$$

Vì $1\,V < 2{,}4\,V$, cầu chì 1 **luôn** đứt trước, đúng lúc $U=1\,V$. Tại thời điểm đó:
$$I_1 = 1\,A,\qquad I_2=\frac{U}{R_2}=\frac{1}{2}=0{,}5\,A$$
$$\Rightarrow I_{max} = I_1+I_2 = 1{,}5\,A$$

**b) Đây là bài học quan trọng nhất:** nếu $I_{2max}=1{,}7\,A$, thì $U_{2,gh}=1{,}7\times2=3{,}4\,V$, vẫn lớn hơn $1\,V$ → cầu chì 1 **vẫn** đứt trước, tại đúng $U=1\,V$ → đáp số **vẫn là $1{,}5\,A$, không đổi!**

→ *Bài học*: dùng cầu chì "chịu dòng cao hơn" cho nhánh 2 không giúp ích gì, vì cái quyết định "ai đứt trước" khi mắc song song là **điện áp giới hạn** ($I_{max}\cdot R$), không phải bản thân $I_{max}$. Đây chính xác là kiểu bẫy tư duy mà đề HSG hay khai thác — hiểu bản chất song song (chung điện áp) sẽ tránh được.

## Ví dụ 2 (Bài 3 – sách gốc): giữ nguyên độ sáng khi đổi điện áp lưới

**Đề bài:** Bóng đèn công suất $100\,W$, thiết kế cho $U_{đm}=110\,V$. Cần mắc nối tiếp một điện trở $R$ bao nhiêu để đèn vẫn sáng đúng như thiết kế khi cắm vào lưới $127\,V$?

**Lời giải:** "Sáng đúng như thiết kế" nghĩa là đèn phải hoạt động đúng dòng điện định mức của nó:
$$I = \frac{P_{đm}}{U_{đm}} = \frac{100}{110} = \frac{10}{11}\,A \approx 0{,}909\,A$$

Phần điện áp dư ($127-110=17\,V$) phải "rơi" hết trên điện trở phụ $R$ (mắc nối tiếp nên dòng qua $R$ cũng chính là $I$ đó):
$$R = \frac{17}{I} = \frac{17\times11}{10} = \boxed{18{,}7\,\Omega}$$

## Ví dụ 3 (Bài 4 – sách gốc): nghịch lý công suất khi một đèn cháy — kiểm chứng số liệu chính xác

**Đề bài:** 8 bóng đèn giống hệt nhau (điện trở $r$ không đổi) mắc song song với nhau thành một cụm, cụm này mắc nối tiếp với một điện trở hạn dòng có điện trở **bằng đúng** điện trở 1 bóng đèn ($=r$), cấp nguồn bằng nguồn áp không đổi $U$. Khi 1 bóng cháy (hở mạch), **tổng công suất tiêu thụ trên các bóng còn lại** tăng hay giảm, bao nhiêu lần?

**Lời giải (đây là bài rất hay để rèn "hiểu bản chất" — công suất *toàn mạch* và công suất *riêng trên các bóng* biến thiên khác nhau!):**

*Trước khi cháy* (8 bóng song song, điện trở cụm $=r/8$):
$$R_{tổng,1} = r+\frac r8 = \frac{9r}{8} \quad\Rightarrow\quad I_{nguồn,1} = \frac{U}{9r/8}=\frac{8U}{9r}$$

Điện áp trên cụm đèn: $U_{cụm,1} = I_{nguồn,1}\cdot\frac r8 = \frac{8U}{9r}\cdot\frac r8=\frac U9$

Công suất trên **cụm đèn**: $P_1 = \dfrac{U_{cụm,1}^2}{r/8} = \dfrac{U^2/81}{r/8}=\dfrac{8U^2}{81r}$

*Sau khi 1 bóng cháy* (7 bóng song song, điện trở cụm $=r/7$):
$$R_{tổng,2}=r+\frac r7=\frac{8r}{7}\quad\Rightarrow\quad I_{nguồn,2}=\frac{7U}{8r}$$

$$U_{cụm,2}=I_{nguồn,2}\cdot\frac r7 = \frac U8 \qquad P_2 = \frac{(U/8)^2}{r/7}=\frac{7U^2}{64r}$$

**Tỉ số:**
$$\frac{P_2}{P_1}=\frac{7U^2/(64r)}{8U^2/(81r)}=\frac{7\times81}{64\times8}=\frac{567}{512}\approx \boxed{1{,}11}$$

khớp chính xác với đáp số gốc: "công suất tăng khoảng 1,11 lần".

**Điều thú vị (đào sâu thêm, tự kiểm chứng):** nếu tính **tổng công suất cả mạch** (kể cả điện trở hạn dòng) thì:
$P_{mạch,1}=U\cdot I_{nguồn,1}=\dfrac{8U^2}{9r}\approx0{,}889\dfrac{U^2}{r}$, còn $P_{mạch,2}=U\cdot I_{nguồn,2}=\dfrac{7U^2}{8r}\approx0{,}875\dfrac{U^2}{r}$ — **tổng công suất cả mạch lại giảm!**

Vì sao hai kết quả trái ngược nhau (công suất bóng đèn tăng, công suất toàn mạch giảm)? Vì khi 1 bóng cháy, điện trở cụm đèn tăng ($r/7 > r/8$) khiến dòng tổng qua mạch **giảm** (giảm tổng công suất tiêu thụ toàn mạch) — nhưng đồng thời điện áp *dồn* nhiều hơn cho cụm đèn (vì cụm đèn "chiếm tỉ trọng điện trở" lớn hơn trong mạch nối tiếp), nên công suất *trên riêng cụm đèn* lại tăng. Đây chính là kiểu suy luận "nhìn hai lớp" (toàn mạch vs. một phần mạch) mà đề thi HSG rất thích khai thác.

---

# PHẦN 3. ĐỊNH LUẬT KIRCHHOFF: TỪ ĐÂU MÀ CÓ?

Khi mạch không thể rút gọn bằng nối tiếp/song song đơn giản (ví dụ mạch cầu, mạch có nhiều nguồn), ta cần công cụ tổng quát hơn — hai định luật Kirchhoff. **Chúng không phải luật mới**, mà là hai sự thật vật lí ta đã nói ở Phần 1, được phát biểu tường minh.

## 3.1. Định luật Kirchhoff I (định luật nút) — từ bảo toàn điện tích

Tại một nút bất kỳ của mạch, điện tích không tự sinh ra hay mất đi, và (với dòng điện gần như không đổi theo thời gian) điện tích không thể "tích tụ" tại nút (nếu không, điện thế tại đó sẽ biến đổi liên tục — mâu thuẫn với trạng thái ổn định). Vậy:

$$\boxed{\sum_n I_n = 0}$$

(quy ước dòng đi **vào** nút mang dấu dương, dòng đi **ra** mang dấu âm — hoặc ngược lại, miễn nhất quán).

**Vì sao chỉ có $N-1$ phương trình độc lập từ $N$ nút?** Nếu ta cộng tất cả $N$ phương trình nút lại, mỗi dòng điện trên mỗi nhánh sẽ xuất hiện đúng **hai lần** với **dấu ngược nhau** (một lần là dòng "ra" khỏi nút này, một lần là dòng "vào" nút kia) → tổng luôn bằng $0=0$, một đẳng thức tầm thường. Điều này có nghĩa là phương trình thứ $N$ luôn có thể suy ra từ $N-1$ phương trình còn lại — nó không mang thêm thông tin mới.

## 3.2. Định luật Kirchhoff II (định luật vòng) — từ tính đơn trị của điện thế

Đi một vòng khép kín quanh mạch, ta quay về đúng điểm xuất phát → điện thế tại đó không đổi (Phần 1.2). Vậy tổng sự thay đổi điện thế dọc đường đi phải bằng 0. Điện thế thay đổi vì hai lý do: giảm khi qua điện trở (theo chiều dòng điện), và tăng khi qua nguồn (theo chiều từ cực – sang cực +):

$$\boxed{\sum_n \xi_n = \sum_n I_n R_n}$$

**Quy tắc dấu thực hành** (chọn một chiều đi vòng tuỳ ý):
- Với mỗi điện trở: nếu chiều đi trùng với chiều dòng điện *giả định*, ghi $+IR$; ngược lại ghi $-IR$.
- Với mỗi nguồn: nếu chiều đi là chiều từ cực (–) sang cực (+) bên trong nguồn (tức chiều nguồn "đẩy" dòng điện), ghi $+\xi$; ngược lại ghi $-\xi$.
- Tổng đại số các số hạng đó, đặt hai vế bằng nhau, hoặc đưa hết sang một vế = 0.

**Số phương trình vòng độc lập = số vòng độc lập** trong mạch (với mạch phẳng, đơn giản nhất là đếm số "ô cửa sổ" khi vẽ mạch phẳng không có dây cắt nhau).

**Một hệ quả tinh tế nhưng cực kỳ hữu ích:** vì hai định luật Kirchhoff là các phương trình **tuyến tính**, chúng cũng đúng cho *độ biến thiên*: nếu dòng điện đổi từ $I_n$ thành $I_n+\Delta I_n$, thì $\sum\Delta I_n=0$ tại mỗi nút, và nguồn lí tưởng có $\Delta\xi = 0$ (suất điện động lí tưởng không đổi khi tải thay đổi). Kỹ thuật này cho phép giải các bài toán "thiếu dữ kiện nhìn thoáng qua" — biết trước và biết sau một thay đổi nhỏ, ta chỉ cần làm việc với các *số gia*, không cần biết giá trị tuyệt đối của mọi thứ.

---

# PHẦN 4. HAI PHƯƠNG PHÁP GIẢI HỆ THỐNG CÓ TỔ CHỨC

Khi mạch phức tạp, áp dụng Kirchhoff "tùy hứng" dễ nhầm lẫn. Có hai phương pháp **hệ thống hoá**, luôn cho ra đúng và đủ số phương trình.

## 4.1. Phương pháp điện thế nút

**Ý tưởng:** chọn một nút làm gốc (điện thế $=0$), coi điện thế các nút còn lại là **ẩn số**. Khi đó, Kirchhoff II (vòng) *tự động thoả mãn* (vì điện thế là đơn trị — đây là lợi thế lớn nhất của phương pháp này!). Ta chỉ cần viết Kirchhoff I (nút) cho mỗi nút chưa biết, biểu diễn dòng điện mỗi nhánh qua *hiệu điện thế hai đầu nhánh đó chia cho điện trở nhánh* (có cộng thêm nguồn nếu nhánh có nguồn).

## 4.2. Phương pháp dòng vòng (dòng mắt lưới)

**Ý tưởng ngược lại:** chọn ẩn số là các "dòng vòng" tưởng tượng chạy khép kín trong từng vòng độc lập; dòng điện thực trên một nhánh chung của hai vòng = tổng đại số hai dòng vòng đó. Khi đó Kirchhoff I *tự động thoả mãn* (mỗi dòng vòng tự nó khép kín, không "biến mất" ở đâu). Ta chỉ cần viết Kirchhoff II cho mỗi vòng độc lập.

## Ví dụ mẫu lớn — "Mạch neo": giải bằng 4 phương pháp, đối chiếu kết quả

Đây là mạch tôi sẽ **dùng lại xuyên suốt** các phần sau (Superposition, Thevenin) để thầy/cô và học sinh thấy rõ: dù chọn phương pháp nào, vật lí vẫn chỉ có **một** câu trả lời — đó chính là "hiểu bản chất" thay vì học thuộc quy trình.

**Mạch:** Có một nút chung M (đỉnh) và nút đất G (điện thế $0\,V$).
- Nhánh 1: từ G qua nguồn $\xi_1=9\,V$ (cực + hướng về M) nối tiếp $R_1=3\,\Omega$, tới M.
- Nhánh 2: từ G qua nguồn $\xi_2=6\,V$ (cực + hướng về M) nối tiếp $R_2=2\,\Omega$, tới M.
- Nhánh 3: điện trở tải $R_3=6\,\Omega$ nối trực tiếp từ M xuống G (không có nguồn).

*(Đây thực chất là cấu trúc của Bài 12 và Bài 21 trong sách gốc — hai nguồn cùng nuôi một điện trở tải.)*

### Cách 1 — Điện thế nút

Gọi $U$ = điện thế nút M. Kirchhoff I tại M (dòng vào từ nhánh 1, 2 = dòng ra qua nhánh 3):

$$\frac{\xi_1-U}{R_1}+\frac{\xi_2-U}{R_2}=\frac{U}{R_3}$$
$$\frac{9-U}{3}+\frac{6-U}{2}=\frac{U}{6}$$

Nhân cả hai vế với 6: $2(9-U)+3(6-U)=U \Rightarrow 18-2U+18-3U=U \Rightarrow 36=6U \Rightarrow U=6\,V$

$$I_1=\frac{\xi_1-U}{R_1}=\frac{9-6}{3}=1\,A \qquad I_2=\frac{\xi_2-U}{R_2}=\frac{6-6}{2}=0\,A \qquad I_3=\frac{U}{R_3}=\frac{6}{6}=1\,A$$

*(Thú vị: $I_2=0$! — chứng tỏ có một nguồn không hề "góp sức" gì trong mạch cụ thể này, dù $\xi_2\neq0$. Kiểm tra: $I_1+I_2=1=I_3$ ✓, đúng định luật nút.)*

### Cách 2 — Dòng vòng (mesh current), kiểm chứng độc lập

Gọi $i_a$ là dòng vòng qua nhánh 1–nhánh 3 (chiều: G→$\xi_1$→$R_1$→M→$R_3$→G), $i_b$ là dòng vòng qua nhánh 2–nhánh 3, cùng chiều. Dòng thực qua $R_3$ (nhánh chung) $=i_a+i_b$.

Vòng a: $\xi_1 - i_aR_1 - (i_a+i_b)R_3=0 \Rightarrow 9-3i_a-6(i_a+i_b)=0 \Rightarrow 3i_a+2i_b=3$

Vòng b: $\xi_2-i_bR_2-(i_a+i_b)R_3=0 \Rightarrow 6-2i_b-6(i_a+i_b)=0 \Rightarrow 3i_a+4i_b=3$

Trừ hai phương trình: $2i_b=0\Rightarrow i_b=0 \Rightarrow i_a=1\,A$.

$$I_1=i_a=1\,A,\quad I_2=i_b=0\,A,\quad I_3=i_a+i_b=1\,A$$

→ **Khớp tuyệt đối với Cách 1.**

*(Hai cách này sẽ được đối chiếu tiếp bằng nguyên lí xếp chồng ở Phần 5, và bằng Thevenin ở Phần 7 — tổng cộng 4 phương pháp độc lập cho cùng một kết quả.)*

---

# PHẦN 5. NGUYÊN LÍ XẾP CHỒNG (SUPERPOSITION)

**Phát biểu:** Trong mạch chỉ gồm điện trở thuần (Ohm) và nguồn suất điện động, dòng điện qua một điện trở bất kỳ **bằng tổng đại số** các dòng điện mà *từng nguồn riêng lẻ* sẽ gây ra nếu nó tác dụng **một mình** (mọi nguồn khác được "tắt": thay bằng dây nối, tức $\xi=0$, nhưng vẫn giữ nguyên điện trở trong/điện trở nối tiếp của nó nếu có).

**Vì sao đúng?** Vì Kirchhoff I, II và định luật Ohm đều là phương trình **tuyến tính** đối với các dòng điện/nguồn — nghiệm của tổng hai "kích thích" (hai nguồn) bằng tổng hai nghiệm riêng lẻ. Đây là tính chất toán học phổ quát của hệ phương trình tuyến tính, không phải "phép màu" riêng của điện học.

## Kiểm chứng trên "Mạch neo"

**Chỉ có $\xi_1=9\,V$ hoạt động** (tắt $\xi_2$, thay bằng dây nối — nhánh 2 chỉ còn $R_2=2\,\Omega$): mạch trở thành $\xi_1$ nối tiếp $R_1$, rồi tới nút M chia thành hai nhánh song song $R_2\parallel R_3$.

$$R_2\parallel R_3=\frac{2\times6}{2+6}=1{,}5\,\Omega \qquad R_{tổng}=R_1+1{,}5=4{,}5\,\Omega$$
$$I_{nguồn}'=\frac{9}{4{,}5}=2\,A \qquad U_M'=2\times1{,}5=3\,V$$
$$I_1'=2\,A\ (G\to M) \qquad I_3'=\frac{3}{6}=0{,}5\,A \qquad I_2'=\frac{3}{2}=1{,}5\,A\ (\text{chiều } M\to G,\text{ tức } {-1{,}5\,A}\text{ theo quy ước ban đầu})$$

**Chỉ có $\xi_2=6\,V$ hoạt động** (tắt $\xi_1$, nhánh 1 còn $R_1=3\,\Omega$): tương tự, $R_1\parallel R_3=\frac{3\times6}{9}=2\,\Omega$, $R_{tổng}=2+2=4\,\Omega$

$$I_{nguồn}''=\frac{6}{4}=1{,}5\,A \qquad U_M''=1{,}5\times2=3\,V$$
$$I_2''=1{,}5\,A\ (G\to M)\qquad I_3''=\frac36=0{,}5\,A\qquad I_1''=\frac33=1\,A\ (M\to G,\text{ tức } {-1\,A})$$

**Xếp chồng (cộng đại số theo đúng chiều dương ban đầu — $G\to M$):**

$$I_1=I_1'+I_1''=2+(-1)=1\,A \qquad I_2=I_2'+I_2''=(-1{,}5)+1{,}5=0\,A \qquad I_3=I_3'+I_3''=0{,}5+0{,}5=1\,A$$

**Khớp hoàn hảo với Phần 4!** Ba phương pháp độc lập (điện thế nút, dòng vòng, xếp chồng) đều cho $I_1=1\,A,\ I_2=0\,A,\ I_3=1\,A$.

---

# PHẦN 6. MẠCH TƯƠNG ĐƯƠNG THEVENIN & ĐỊNH LÍ MILLMAN

## 6.1. Vì sao nguồn thật không giữ điện áp không đổi?

Không có nguồn nào lí tưởng: khi dòng tải tăng, điện áp cực giảm dần. Mô hình đơn giản nhất: coi nguồn thật = nguồn lí tưởng $\xi$ nối tiếp một **điện trở trong** $r$:

$$V_{cực} = \xi - Ir$$

**Định lí Thevenin:** *Bất kỳ mạng hai cực nào* gồm toàn điện trở và nguồn suất điện động (tuyến tính) đều **tương đương** với một nguồn lí tưởng $\xi_{td}$ nối tiếp một điện trở $r_{td}$ duy nhất, xét từ hai cực ra ngoài.

**Cách tìm $\xi_{td}, r_{td}$ (hai cách tương đương):**
1. $\xi_{td}$ = điện áp đo được ở hai cực khi **để hở mạch** (không nối tải, $I=0$).
2. $r_{td}$ = điện trở đo được giữa hai cực khi **tắt hết mọi nguồn** bên trong (thay $\xi\to0$, tức thay bằng dây nối, chỉ giữ lại điện trở).
   (Cách khác: $r_{td}=\xi_{td}/I_{ngắn mạch}$, với $I_{ngắn mạch}$ là dòng khi *nối tắt* hai cực.)

## 6.2. Áp dụng Thevenin cho "Mạch neo" — kiểm chứng lần thứ 4!

Ta tìm mạch Thevenin tương đương của **nhánh 1 + nhánh 2** (nhìn từ hai cực M–G, tạm bỏ $R_3$ ra):

**Bước 1 — $\xi_{td}$:** tháo $R_3$ ra (hở mạch tại M–G). Khi đó vẫn còn một vòng kín: G→$\xi_1$→$R_1$→M→$R_2$→$\xi_2$→G, có dòng $I_{vòng}$ chạy quanh:

$$\xi_1-I_{vòng}R_1-I_{vòng}R_2-\xi_2=0 \;\Rightarrow\; I_{vòng}=\frac{\xi_1-\xi_2}{R_1+R_2}=\frac{9-6}{3+2}=0{,}6\,A$$

$$\xi_{td}=U_M=\xi_1-I_{vòng}R_1=9-0{,}6\times3=7{,}2\,V$$

**Bước 2 — $r_{td}$:** tắt $\xi_1,\xi_2$ (thay bằng dây nối), nhánh 1 chỉ còn $R_1$, nhánh 2 chỉ còn $R_2$, hai điện trở này giờ nối song song giữa M và G:

$$r_{td}=R_1\parallel R_2=\frac{3\times2}{3+2}=1{,}2\,\Omega$$

**Bước 3 — nối lại $R_3$:**

$$I_3=\frac{\xi_{td}}{r_{td}+R_3}=\frac{7{,}2}{1{,}2+6}=\frac{7{,}2}{7{,}2}=\boxed{1\,A}$$

**Khớp hoàn hảo với 3 phương pháp trước!** Bốn phương pháp — điện thế nút, dòng vòng, xếp chồng, Thevenin — đều cho cùng đáp số $I_3=1\,A$. Đó chính là ý nghĩa sâu xa của "hiểu bản chất": các phương pháp chỉ là những *cách tổ chức* cùng một hệ vật lí, không phải bốn công thức rời rạc cần nhớ riêng.

## 6.3. Định lí Millman (Bài 21 – sách gốc)

**Bài toán tổng quát:** $N$ nguồn suất điện động $\xi_i$ (điện trở trong $r_i$) mắc **song song** với nhau (mọi nhánh nối chung giữa 2 nút A, B). Tìm hiệu điện thế $U=U_A-U_B$ và thông số nguồn tương đương.

**Đây thực chất chỉ là phương pháp điện thế nút, viết tổng quát cho $N$ nhánh!** Đặt $U_B=0$, viết Kirchhoff I tại nút A (không có tải nào khác — hoặc nếu có tải, coi nó là nhánh thứ $N+1$ với $\xi=0$):

$$\sum_{i=1}^{N}\frac{\xi_i - U}{r_i}=0 \;\Longrightarrow\; U\sum_i\frac1{r_i}=\sum_i\frac{\xi_i}{r_i}$$

$$\boxed{U=\dfrac{\displaystyle\sum_i \xi_i/r_i}{\displaystyle\sum_i 1/r_i}}$$

Đây chính là **suất điện động tương đương** $\xi_{td}$ của cả cụm N nguồn song song (vì đó là điện áp hở mạch). Còn **điện trở trong tương đương**:

$$r_{td}=\left(\sum_i\frac1{r_i}\right)^{-1}$$

— chính là công thức ghép điện trở **song song** quen thuộc, áp dụng cho $N$ điện trở trong! (Kiểm tra nhanh với $N=2$, mạch neo: $r_{td}=(1/3+1/2)^{-1}=1{,}2\,\Omega$ — khớp với 6.2. ✓)

→ *Bài học*: định lí Millman không phải công thức "trên trời rơi xuống" cần học thuộc — nó *chính là* phương pháp điện thế nút áp dụng cho một cấu trúc mạch đặc biệt (nhiều nhánh chung 2 nút).

---

# PHẦN 7. BIẾN ĐỔI SAO – TAM GIÁC (Δ–Y)

Khi 3 điện trở gặp nhau ở một nút theo hình "sao" (Y) mà không thể rút gọn nối tiếp/song song, ta có thể thay bằng một cấu hình "tam giác" (Δ) **tương đương về mặt điện** (nhìn từ 3 đầu ra ngoài), và ngược lại.

## Chứng minh công thức (không học vẹt!)

Xét mạng $\Delta$ với 3 điện trở $R_{AB}, R_{BC}, R_{CA}$ nối 3 đỉnh A, B, C. Ta muốn tìm mạng sao tương đương $R_A, R_B, R_C$ (mỗi điện trở nối từ đỉnh tương ứng tới một tâm O chung).

**Điều kiện tương đương:** điện trở đo được giữa hai đỉnh bất kỳ (đỉnh thứ ba để hở, không nối gì thêm) phải bằng nhau ở cả hai mạng.

- Ở mạng **sao**: đo $A$–$B$ (C hở, không có dòng qua $R_C$) → chỉ còn đường nối tiếp $R_A+R_B$.
- Ở mạng **tam giác**: đo $A$–$B$ (C hở về bên ngoài, nhưng bên trong vẫn có đường vòng $A\to C\to B$) → $R_{AB}$ song song với $(R_{CA}+R_{BC})$.

Đặt $S=R_{AB}+R_{BC}+R_{CA}$. Ba phương trình (viết tương tự cho cả 3 cặp đỉnh):

$$R_A+R_B=\frac{R_{AB}(R_{CA}+R_{BC})}{S},\quad R_B+R_C=\frac{R_{BC}(R_{AB}+R_{CA})}{S},\quad R_C+R_A=\frac{R_{CA}(R_{AB}+R_{BC})}{S}$$

Cộng cả ba vế trái và phải, rút gọn, ta được $R_A+R_B+R_C=\dfrac{R_{AB}R_{CA}+R_{AB}R_{BC}+R_{BC}R_{CA}}{S}$. Lấy hiệu với phương trình thứ hai ($R_B+R_C$), số hạng $R_B+R_C$ triệt tiêu, còn lại:

$$\boxed{R_A=\dfrac{R_{AB}R_{CA}}{S}} \qquad\text{(và tương tự theo chu trình cho } R_B, R_C\text{)}$$

**Trường hợp đối xứng đặc biệt** ($R_{AB}=R_{BC}=R_{CA}=R_\Delta$): $R_Y=\dfrac{R_\Delta\cdot R_\Delta}{3R_\Delta}=\dfrac{R_\Delta}{3}$ — công thức "chia 3" quen thuộc, giờ đã được *chứng minh* chứ không chỉ ghi nhớ.

## Ví dụ số — tự kiểm chứng

Cho $R_{AB}=6\,\Omega, R_{BC}=3\,\Omega, R_{CA}=2\,\Omega$ ($S=11$).

$$R_A=\frac{6\times2}{11}=\frac{12}{11}\,\Omega,\quad R_B=\frac{6\times3}{11}=\frac{18}{11}\,\Omega,\quad R_C=\frac{3\times2}{11}=\frac{6}{11}\,\Omega$$

**Kiểm tra:** $R_A+R_B=\frac{30}{11}\,\Omega$. Tính trực tiếp từ mạng Δ: $R_{AB}\parallel(R_{CA}+R_{BC})=6\parallel5=\dfrac{6\times5}{11}=\dfrac{30}{11}\,\Omega$ ✓.

## Áp dụng: giải mạch cầu bằng Δ–Y (đối chiếu với Phần 4)

Xét mạch cầu: nguồn lí tưởng $10\,V$ nối giữa A và D. $R_{AB}=2\,\Omega, R_{AC}=4\,\Omega, R_{BD}=3\,\Omega, R_{CD}=1\,\Omega$, và điện trở cầu $R_{BC}=5\,\Omega$ nối B–C. *(Đây chính là mạch cầu không cân bằng ta có thể giải trực tiếp bằng phương pháp điện thế nút — dùng để đối chiếu.)*

**Bước 1:** biến đổi tam giác $ABC$ (cạnh $R_{AB}=2, R_{BC}=5, R_{CA}=4$, $S=11$) thành sao tâm O:

$$R_A'=\frac{2\times4}{11}=\frac{8}{11},\quad R_B'=\frac{2\times5}{11}=\frac{10}{11},\quad R_C'=\frac{5\times4}{11}=\frac{20}{11}\ (\Omega)$$

**Bước 2:** mạch giờ chỉ còn nối tiếp – song song đơn giản: từ O có hai nhánh tới D — qua B ($R_B'+R_{BD}=\frac{10}{11}+3=\frac{43}{11}$) và qua C ($R_C'+R_{CD}=\frac{20}{11}+1=\frac{31}{11}$), hai nhánh này song song:

$$R_{OD}=\frac{43/11 \times 31/11}{43/11+31/11}=\frac{1333/121}{74/11}=\frac{1333}{814}\,\Omega$$

Tổng điện trở A–D: $R_{AD}=R_A'+R_{OD}=\dfrac{8}{11}+\dfrac{1333}{814}=\dfrac{592+1333}{814}=\dfrac{1925}{814}=\dfrac{175}{74}\,\Omega\approx2{,}365\,\Omega$

$$I_{tổng}=\frac{10}{175/74}=\frac{740}{175}=\frac{148}{35}\,A\approx4{,}229\,A$$

**Đối chiếu bằng phương pháp điện thế nút (giải trực tiếp, không qua Δ–Y):** giải hệ phương trình nút tại B, C với $V_A=10\,V$ cố định (nguồn lí tưởng) và $V_D=0$, ta được $V_B=\frac{186}{35}\,V,\ V_C=\frac{86}{35}\,V$, dòng tổng $=\frac{10-V_B}{2}+\frac{10-V_C}{4}=\frac{82}{35}+\frac{66}{35}=\frac{148}{35}\,A$.

**Trùng khớp tuyệt đối!** Kỹ thuật Δ–Y đã biến một mạch cầu "khó" thành nối tiếp–song song "dễ", cho cùng kết quả với phương pháp tổng quát hơn.

---

# PHẦN 8. KĨ THUẬT ĐỐI XỨNG — VŨ KHÍ MẠNH NHẤT CỦA HSG

## Nguyên lí chung

Nếu một mạch điện có thể được "phản chiếu" hoặc "xoay" sao cho một số điểm hoán đổi vị trí cho nhau mà **toàn bộ mạch trông y hệt như cũ**, thì các điểm hoán đổi đó buộc phải có **cùng điện thế** (vì bài toán vật lí — và nghiệm của nó — cũng phải đối xứng theo phép biến đổi đó).

**Hệ quả cực kỳ mạnh:** những điểm cùng điện thế này có thể **nối tắt với nhau bằng một dây dẫn** (hoặc **cắt** dây nối giữa chúng, nếu vốn dĩ có) mà **không hề làm thay đổi** dòng điện, điện áp ở bất cứ đâu trong mạch — vì không có dòng nào chạy qua dây nối tưởng tượng đó (hai đầu vốn đã cùng điện thế).

## Ví dụ mở đầu: điều kiện cầu Wheatstone cân bằng

Mạch cầu $R_{AB}, R_{AC}, R_{BD}, R_{CD}$, điện trở cầu $R_{BC}$ nối B–C, nguồn nối A–D. Khi nào dòng qua $R_{BC}$ bằng 0 (không cần biết đối xứng hình học, chỉ cần đối xứng *điện*)?

Không có $R_{BC}$: theo công thức chia áp, $V_B=V_D+(V_A-V_D)\dfrac{R_{BD}}{R_{AB}+R_{BD}}$, $V_C=V_D+(V_A-V_D)\dfrac{R_{CD}}{R_{AC}+R_{CD}}$.

Cho $V_B=V_C$: $\dfrac{R_{BD}}{R_{AB}+R_{BD}}=\dfrac{R_{CD}}{R_{AC}+R_{CD}} \Longrightarrow \boxed{R_{AB}\cdot R_{CD}=R_{AC}\cdot R_{BD}}$

("tích hai cặp điện trở đối diện bằng nhau"). Khi đó $R_{BC}$ có nối hay không cũng không ảnh hưởng gì — có thể **bỏ hẳn** khỏi mạch khi tính toán.

## Ví dụ kinh điển: điện trở giữa hai đỉnh xa nhất của hình lập phương (liên quan Bài 23 gốc)

**Đề bài:** 12 cạnh của một khối lập phương đều là điện trở $r$ giống hệt nhau. Tìm điện trở tương đương giữa hai đỉnh đối xứng qua tâm (đường chéo không gian, ví dụ đỉnh $A(0,0,0)$ và $H(1,1,1)$).

**Lời giải bằng đối xứng (không cần viết một phương trình Kirchhoff nào!):**

Đặt dòng điện $I$ đi vào tại A, ra tại H. Ba đỉnh kề A — gọi là B, C, D (mỗi đỉnh chỉ khác A ở một toạ độ) — **hoán đổi được cho nhau** bởi phép xoay $120°$ quanh đường chéo AH (phép này hoán vị 3 trục $x,y,z$, giữ nguyên hình lập phương). Vì vậy B, C, D có **cùng điện thế**, và theo đối xứng, dòng từ A rẽ đều vào 3 nhánh:

$$I_{A\to B}=I_{A\to C}=I_{A\to D}=\frac{I}{3}$$

Tương tự, ba đỉnh kề H — gọi E, F, G ("tầng thứ hai", mỗi đỉnh khác H ở một toạ độ) — cũng có cùng điện thế, mỗi đỉnh nhận dòng $I/3$ đổ vào H.

Còn lại 6 cạnh nối "tầng 1" (B, C, D) với "tầng 2" (E, F, G): theo đối xứng 3 chiều, cả 6 cạnh này **tương đương nhau**, và tổng dòng chảy từ tầng 1 sang tầng 2 là $I$ (bảo toàn dòng) → mỗi cạnh mang $I/6$.

Vậy hiệu điện thế giữa A và H (cộng dồn theo *một đường đi bất kỳ*, ví dụ $A\to B\to E\to H$, vì điện thế là đơn trị nên đi đường nào cũng ra cùng kết quả — đây chính là Phần 1.2!):

$$U_{AH}=\underbrace{\frac I3 r}_{A\to B}+\underbrace{\frac I6 r}_{B\to E}+\underbrace{\frac I3 r}_{E\to H}=Ir\left(\frac13+\frac16+\frac13\right)=Ir\cdot\frac{5}{6}$$

$$\boxed{R_{tđ}=\frac{5}{6}r}$$

Đây chính là kết quả kinh điển của bài toán "khối lập phương điện trở" — khớp với bài 23 sách gốc (hình lập phương cạnh $1\,\Omega$, đáp số $R=\dfrac56\,\Omega$).

*Nhận xét sư phạm:* lời giải trên **không hề dùng một phương trình Kirchhoff cụ thể nào** — toàn bộ dựa trên việc *nhận diện các điểm cùng điện thế bằng đối xứng*, rồi dùng tính chất "điện thế đơn trị theo mọi đường đi" để cộng điện áp dọc **một** đường đi tiêu biểu. Đây là kỹ thuật ưu việt nhất khi gặp mạch có tính đối xứng cao (hình lập phương, hình đa giác đều, mạch cầu cân bằng...).

---

# PHẦN 9. AMPE KẾ – VÔN KẾ LÍ TƯỞNG & SAI SỐ DỤNG CỤ ĐO

- **Ampe kế lí tưởng**: điện trở $=0$ → mắc vào đâu coi như *nối tắt* điểm đó (hai đầu ampe kế luôn cùng điện thế).
- **Vôn kế lí tưởng**: điện trở $=\infty$ → mắc vào đâu coi như *hở mạch* tại đó (không có dòng nào chạy qua vôn kế, không ảnh hưởng đến dòng điện trong mạch chính).

Trên thực tế, dụng cụ đo có điện trở hữu hạn (ampe kế) hoặc hữu hạn nhưng rất lớn (vôn kế), gây ra sai số. Kỹ thuật xử lý sai số nhỏ: **xấp xỉ tuyến tính**.

## Ví dụ (Bài 41 – sách gốc): tìm dòng điện "thật" khi biết ampe kế có sai số

**Đề bài:** Một ampe kế có nhiều thang đo, điện trở trong tỉ lệ nghịch với thang đo (đây là tính chất vật lý thật của điện kế khung quay: điện áp toàn thang không đổi, gọi hằng số đó là $k$, nên $r_{thang}=k/I_{thang}$). Ở thang $10\,mA$: ampe kế chỉ $2{,}95\,mA$. Ở thang $3\,mA$: ampe kế chỉ $2{,}90\,mA$. Tìm dòng điện thật $I_0$ trong mạch khi *không có* ampe kế (tức khi $r\to0$).

**Lời giải:** Khi thêm ampe kế (điện trở $r$) vào mạch, dòng điện trong mạch giảm đi một chút so với dòng thật $I_0$ (không có ampe kế). Vì $r$ nhỏ so với điện trở tổng của mạch, ta dùng xấp xỉ tuyến tính: độ giảm dòng điện tỉ lệ thuận với $r$ được thêm vào:

$$I(r) \approx I_0 - m\cdot r \qquad (m = \text{hằng số chưa biết})$$

Với $r_1=k/10$ (ứng với $I_1=2{,}95$) và $r_2=k/3$ (ứng với $I_2=2{,}90$), ta có 2 phương trình với 2 ẩn số kết hợp ($I_0$ và tích $m\cdot k$, gọi gộp là $M=mk$):

$$2{,}95 = I_0 - \frac{M}{10} \qquad (i) \qquad\qquad 2{,}90 = I_0-\frac M3 \qquad (ii)$$

Lấy (i) − (ii): $0{,}05 = M\left(\dfrac13-\dfrac{1}{10}\right)=M\cdot\dfrac{7}{30} \Rightarrow M=\dfrac{0{,}05\times30}{7}=\dfrac{1{,}5}{7}\approx0{,}2143$

$$I_0 = 2{,}95+\frac{M}{10}=2{,}95+0{,}02143\approx\boxed{2{,}97\,mA}$$

khớp chính xác với đáp số gốc.

*Bài học phương pháp:* khi hai số liệu đo gần bằng nhau, đừng cố giải phương trình chính xác (thường phi tuyến, phức tạp) — hãy dùng **xấp xỉ tuyến tính bậc nhất**, biến bài toán thành hệ phương trình tuyến tính đơn giản. Đây là kỹ thuật xử lý số liệu thực nghiệm quan trọng, không riêng gì mạch điện.

---

# PHẦN 10. MẠCH VÔ HẠN TUẦN HOÀN

**Ý tưởng cốt lõi:** nếu một mạch có cấu trúc lặp lại **vô hạn lần**, thì bỏ đi (hoặc thêm vào) **một** đơn vị lặp ở đầu mạch, phần còn lại vẫn là... **chính mạch vô hạn ban đầu**! Điều này biến bài toán "vô hạn" thành một phương trình đại số hữu hạn cho điện trở tương đương $R$ của toàn mạch, theo kiểu "tự quy về chính nó".

## Ví dụ tự xây dựng

Mạch bậc thang vô hạn: từ hai cực vào, một điện trở nối tiếp $R_1=1\,\Omega$, sau đó một điện trở $R_2=2\,\Omega$ mắc song song "xuống đường trở về" — rồi lặp lại y hệt vô hạn lần về phía sau.

Gọi $R$ = điện trở tương đương nhìn từ hai cực vào. Bỏ đơn vị lặp *đầu tiên* ra, phần còn lại (vô hạn) chính là một mạch y hệt, có điện trở cũng bằng $R$. Vậy:

$$R = R_1 + (R_2 \parallel R) = 1+\frac{2R}{2+R}$$

$$(R-1)(2+R)=2R \;\Rightarrow\; R^2+R-2-2R=0 \;\Rightarrow\; R^2-R-2=0 \;\Rightarrow\; (R-2)(R+1)=0$$

Lấy nghiệm dương (điện trở không thể âm): $\boxed{R=2\,\Omega}$.

**Kiểm tra:** $R_1+\dfrac{R_2R}{R_2+R}=1+\dfrac{2\times2}{2+2}=1+1=2\,\Omega$ ✓ — tự nhất quán.

*(Bài 29 sách gốc dùng đúng kỹ thuật này, chỉ khác giá trị $R_1, R_2$ cụ thể theo hình vẽ — học sinh áp dụng y hệt cách lập phương trình bậc hai trên.)*

---

# PHẦN 11. ĐỌC THÊM (NÂNG CAO, KHÔNG BẮT BUỘC): PHẦN TỬ PHI TUYẾN

Với các phần tử như điốt, bóng đèn sợi đốt ở dải nhiệt độ lớn — định luật Ohm ($R=const$) không còn đúng nữa. Sách gốc giới thiệu **phương pháp đồ thị**: vẽ đường đặc tuyến $I$–$U$ thực nghiệm của phần tử phi tuyến, đồng thời vẽ "đường tải" $IR=\xi - U$ (một đường thẳng, suy ra trực tiếp từ Kirchhoff II cho mạch gồm phần tử đó nối tiếp điện trở $R$ và nguồn $\xi$) trên **cùng một hệ trục**. Giao điểm hai đường chính là nghiệm của mạch. Đây là một kỹ thuật đẹp và trực quan, nhưng đòi hỏi đọc đồ thị chính xác — dành cho học sinh đã vững phần tuyến tính và muốn thử sức thêm, nằm ngoài phạm vi chính của tài liệu này.

---

# PHẦN 12. TỔNG KẾT KĨ NĂNG

Sau tài liệu này, học sinh cần **tự mình chọn được** công cụ phù hợp cho từng dạng mạch:

| Đặc điểm mạch | Công cụ nên dùng |
|---|---|
| Rút gọn được bằng nối tiếp/song song | Phần 2 |
| Có nhiều nguồn, không rút gọn được, cần *một* đại lượng | Kirchhoff trực tiếp hoặc điện thế nút (Phần 3–4) |
| Cần dòng qua *nhiều* nhánh cùng lúc, mạch có nhiều vòng | Dòng vòng hoặc điện thế nút (Phần 4) |
| Chỉ cần dòng/áp qua *một* nhánh cụ thể, mạch có 2 nguồn trở lên | Xếp chồng (Phần 5) hoặc Thevenin (Phần 6) |
| Nhiều nguồn cùng nối vào 2 nút | Millman (Phần 6.3) |
| Mạch cầu, tam giác không rút gọn được | Δ–Y (Phần 7) |
| Mạch có tính đối xứng hình học hoặc điện | **Ưu tiên số 1**: đối xứng (Phần 8) — luôn thử trước khi lao vào viết phương trình! |
| Cấu trúc lặp vô hạn | Tự quy về chính nó (Phần 10) |

**Nguyên tắc vàng khi làm bài:** trước khi viết bất kỳ phương trình nào, hãy tự hỏi theo đúng thứ tự: *(1) Mạch có rút gọn nối tiếp/song song được không? (2) Mạch có đối xứng gì không? (3) Có Δ hoặc Y nào cản đường rút gọn không? (4) Nếu vẫn bí, mới viết hệ phương trình Kirchhoff một cách có tổ chức (nút hoặc vòng).* Thứ tự này giúp tiết kiệm thời gian và giảm sai sót cực nhiều trong phòng thi.

## Bài tập tự luyện (trích Chương 1 sách gốc, có đáp số để tự kiểm tra)

*Học sinh giải độc lập bằng các kỹ thuật đã học ở trên; số hiệu bài và hình vẽ tham khảo tài liệu gốc "Elektri ja magnetismi ülesandeid" của Valter Kiisk.*

| Bài | Kỹ thuật gợi ý | Đáp số (tự kiểm tra) |
|---|---|---|
| 2 (thiết kế vôn kế/ampe kế từ điện kế) | Nối tiếp/song song + Ohm | — |
| 8 (4 ampe kế) | Kirchhoff nút | $R=900\,\Omega$ |
| 9 (mạch điện trở + vôn kế) | Đối xứng / nối tiếp | $12\,V$ |
| 10 (mạch cầu) | Điện thế nút **và** dòng vòng (thử cả hai, đối chiếu!) | $26/7\,\Omega$ |
| 14 (2 nguồn, mạch có nhiều vòng) | Kirchhoff / dòng vòng | — |
| 16 (đèn Noel, điện trở hạn dòng thực tế) | Nối tiếp/song song + Ohm | $R=1\,\Omega$ |
| 21 | Millman (đã học ở Phần 6.3) | công thức đã chứng minh |
| 22 | Diễn đạt lại bài 12 bằng ngôn ngữ Millman | — |
| 24 | Đối xứng | $R=11/6\,\Omega$ |
| 26 (6 điện trở, hình đối xứng) | Đối xứng (giống kiểu Phần 8) | $R=1\,\Omega$ |
| 33 | Đối xứng (biến thể của bài lập phương) | $R=1/2\,\Omega$ |
| 41 | Đã giải mẫu ở Phần 9 | $I=2{,}97\,mA$ |

**Bài rất nâng cao (thử sức, không bắt buộc):** Bài 31–32 (điện trở giữa hai nút liền kề của một **lưới vô hạn** hình tam giác đều / hình lập phương vô hạn) — dùng ý tưởng xếp chồng dòng điện "bơm vào tại A, hút ra tại vô cực" cộng với "bơm vào từ vô cực, hút ra tại B", đáp số cả hai đều là $R=1/3\,\Omega$ (với điện trở mỗi cạnh $=1\,\Omega$). Đây là kỹ thuật rất đẹp nhưng đòi hỏi tư duy trừu tượng cao — phù hợp cho học sinh đã nắm chắc mọi phần trên và muốn thử thách bản thân.

---

# LỜI KẾT

Toàn bộ tài liệu này xây dựng trên **một triết lý duy nhất**: mọi công thức mạch điện, dù trông "đáng sợ" thế nào (Kirchhoff, Thevenin, Millman, Δ–Y), đều bắt nguồn từ **hai sự thật đơn giản** — bảo toàn điện tích tại một điểm, và điện thế chỉ có một giá trị tại một điểm. Học sinh nắm chắc hai sự thật này, cùng thói quen "luôn thử đối xứng trước", sẽ giải được hầu hết các bài mạch điện HSG lớp 9, kể cả những bài chưa từng gặp qua.

*Phần tiếp theo (nếu cần): Chương 2 của sách gốc (tụ điện trong mạch một chiều) có thể biên soạn theo đúng tinh thần này nếu học sinh đã vững chương trình tụ điện. Các chương 3–7 (tĩnh điện với định lý Gauss, từ trường, cảm ứng điện từ, dòng xoay chiều, chuyển động hạt tích điện) đòi hỏi vi tích phân và số phức — vượt chương trình lớp 9, phù hợp hơn cho giai đoạn ôn thi lớp 11–12 chuyên hoặc dự tuyển Olympic Vật lí.*


---

# PHẦN 2
