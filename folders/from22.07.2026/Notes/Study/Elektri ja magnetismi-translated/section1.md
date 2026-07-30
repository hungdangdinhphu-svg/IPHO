cat >> /home/claude/build/dientu.tex << 'LATEXEOF'
\section{Mạch điện một chiều}

\subsection*{Lời nói đầu}

Bài viết này nhằm mục đích làm tài liệu hỗ trợ cho học sinh trung học phổ thông đang chuẩn bị tham dự Olympic Vật lý quốc tế. Do đó, nhìn chung các bài tập được xem xét ở đây nằm trong giới hạn của chương trình Olympic Vật lý quốc tế (\url{http://www.ioc.ee/~kalda/ipho/Syllabus-new.pdf}).

Đôi chỗ cần biết những kiến thức cơ bản của giải tích vi phân và tích phân, cũng như các phép toán cơ bản với vectơ và số phức. Tuy nhiên, trọng tâm vẫn là việc vận dụng một cách sáng tạo những ý tưởng vật lý và thủ thuật toán học tương đối đơn giản vào nhiều tình huống mới mẻ đối với vật lý phổ thông. Hy vọng rằng bài viết cũng sẽ hữu ích cho sinh viên chuyên ngành vật lý.

Tất cả các công thức được biểu diễn trong đơn vị SI. Về sau, không bình luận thêm, chúng tôi sẽ dùng các hằng số bắt nguồn từ việc sử dụng hệ SI: $\varepsilon_0 = 8{,}85\times10^{-12}$~F/m (độ điện thẩm của chân không) và $\mu_0 = 4\pi\times10^{-7}$~H/m (độ từ thẩm của chân không).

Để ký hiệu các đại lượng vectơ, ta dùng chữ in đậm ($\mathbf{a}, \mathbf{b}, \dots$). Dấu mũ phía trên vectơ cho biết đó là vectơ đơn vị (chẳng hạn $\hat{\mathbf{a}}$ là vectơ đơn vị theo hướng $\mathbf{a}$, vectơ đơn vị theo pháp tuyến mặt là $\hat{\mathbf{n}}$, v.v.). Độ lớn (môđun) của vectơ $\mathbf{a}$ được ký hiệu là $a$, môđun của một biểu thức vectơ, chẳng hạn $\mathbf{a}-\mathbf{b}$, được ký hiệu $|\mathbf{a}-\mathbf{b}|$. Tích có hướng ký hiệu $\mathbf{a}\times\mathbf{b}$, tích vô hướng ký hiệu $\mathbf{a}\cdot\mathbf{b}$ hay đơn giản là $ab$. Mỗi vectơ có thể được phân tích thành thành phần vuông góc (pháp tuyến) và thành phần song song (tiếp tuyến) với một mặt cho trước. Để chỉ các thành phần này ta dùng chỉ số tương ứng $n$ và $\tau$ (ví dụ $\mathbf{E} = \mathbf{E}_n + \mathbf{E}_\tau$).

\subsection{Kiến thức cơ bản}

Cường độ dòng điện được định nghĩa là điện lượng đi qua tiết diện của vật dẫn trong một đơn vị thời gian: $I = \Delta q/\Delta t$ (đơn vị SI là ampe, $\mathrm{A} = \mathrm{C/s}$).\footnote{Ít nhất là trong kim loại, hạt tải điện là các electron, có điện tích âm vì lý do lịch sử, do đó chiều chuyển động của chúng ngược với chiều dòng điện. Tuy nhiên điện tích, cường độ dòng điện và các đại lượng điện khác dù sao cũng là các đại lượng có dấu, và ít nhất trong phân tích mạch điện, bản chất vi mô của dòng điện hoàn toàn không quan trọng. Bản chất của hạt tải điện chỉ bộc lộ trong những thí nghiệm phức tạp hơn, như hiệu ứng Hall.}

Điện tích có thể chuyển động dưới tác dụng của nhiều loại lực khác nhau. Lực tĩnh điện là lực bảo toàn và có thể được đặc trưng bởi thế năng. Điện thế $\varphi$ tại một điểm trong không gian được định nghĩa là thế năng tĩnh điện của một điện tích thử đơn vị đặt tại điểm đó (đơn vị vôn, $\mathrm{V}=\mathrm{J/C}$). Hiệu điện thế, hay điện áp $U$ giữa hai đầu vật dẫn, là nguyên nhân gây ra dòng điện (lực tác dụng lên hạt tải điện có hướng làm giảm thế năng). Hiệu điện thế được duy trì bởi các lực phi tĩnh điện, hay còn gọi là ngoại lực, ví dụ như phản ứng hoá học trong nguồn điện. Hiệu điện thế cực đại mà ngoại lực có thể tạo ra được gọi là suất điện động của thiết bị tương ứng. Như vậy, khi điện tích $q$ đi qua một nguồn điện có suất điện động $\mathcal{E}$, thế năng của nó tăng thêm $\mathcal{E}q$, còn khi đi qua một vật dẫn (chẳng hạn điện trở) với độ sụt áp $U$, thế năng của nó giảm đi $Uq$. Đối với nguồn điện có thể sạc lại (ắc-quy), cũng có thể cho dòng điện chạy theo chiều ngược lại, khi đó công $\mathcal{E}q$ được dùng để phục hồi năng lượng hoá học bên trong nguồn.

Phần lớn các vật dẫn điện tuân theo định luật Ohm: cường độ dòng điện qua vật dẫn tỉ lệ với hiệu điện thế gây ra dòng điện ở hai đầu vật dẫn: $I = U/R$. Đại lượng $R$ được gọi là điện trở của vật dẫn cụ thể đó (đơn vị ôm, $\Omega = \mathrm{V/A}$). Từ định nghĩa của cường độ dòng điện và hiệu điện thế, ta thấy rõ ràng rằng trong mắc song song, dòng điện của các phần tử cộng lại, còn trong mắc nối tiếp, hiệu điện thế của các phần tử cộng lại. Do đó ta có các biểu thức quen thuộc để tính điện trở tổng của mạch nối tiếp và song song các điện trở:
\[
R_{\text{nt}} = R_1 + R_2 + \dots, \qquad \frac{1}{R_{\text{ss}}} = \frac{1}{R_1} + \frac{1}{R_2} + \dots
\]

Với lý luận tương tự, cũng dễ thấy rằng điện trở của một vật dẫn dài, tiết diện đều, tỉ lệ với chiều dài $l$ của vật dẫn và tỉ lệ nghịch với diện tích tiết diện $S$: $R = \rho l / S$, trong đó $\rho$ là đại lượng đặc trưng cho vật liệu, gọi là điện trở suất. Điện trở suất (như một đại lượng vi phân) cũng cần thiết khi sự phân bố dòng điện trong không gian hoặc tiết diện vật dẫn không đều (mục 7.2, bài 7).

Dựa vào định nghĩa cường độ dòng điện và hiệu điện thế, ta có công suất điện chuyển hoá thành nhiệt trong vật dẫn $P = UI$, mà đối với vật dẫn tuân theo định luật Ohm có thể viết dưới dạng khác $P = I^2 R = U^2/R$ (định luật Joule--Lenz).

\baitap{1} Để có một cầu chì bảo vệ quá dòng phù hợp, người ta mắc song song hai cầu chì. Cầu chì thứ nhất có điện trở $1\,\Omega$ và dòng điện cực đại (mà tại đó dây nối chảy ra) là $1\,\mathrm{A}$. Cầu chì thứ hai có các thông số tương ứng là $2\,\Omega$ và $1{,}2\,\mathrm{A}$. a) Dòng điện cực đại qua tổ hợp cầu chì này là bao nhiêu? b) Câu trả lời sẽ là gì nếu dòng điện cực đại của cầu chì thứ hai là $1{,}7\,\mathrm{A}$?

\baitap{2} Thang đo của một microampe kế là $100\,\mu\mathrm{A}$. Ở cường độ dòng điện đó, trên các cực của ampe kế xuất hiện độ sụt áp $0{,}1\,\mathrm{V}$. Cần mắc thêm điện trở như thế nào và có giá trị bao nhiêu vào mạch để biến nó thành: a) một vôn kế có thang đo $100\,\mathrm{V}$; b) một ampe kế có thang đo $10\,\mathrm{A}$?

\baitap{3} Một bóng đèn có công suất $100\,\mathrm{W}$ được thiết kế cho hiệu điện thế $110\,\mathrm{V}$. Cần mắc nối tiếp một điện trở có giá trị bao nhiêu để đèn sáng với cùng độ sáng trong mạng điện $127\,\mathrm{V}$?\footnote{Trên thực tế đây có lẽ là dòng điện xoay chiều, nhưng cách giải bài toán không thay đổi vì đó, vì $110\,\mathrm{V}$ và $127\,\mathrm{V}$ là các giá trị hiệu dụng của điện áp xoay chiều (mục 6.1).}

\baitap{4} Tám bóng đèn sợi đốt giống hệt nhau được mắc với một nguồn điện áp không đổi theo cách như trên Hình~1. Nối tiếp với nguồn điện là một điện trở hạn dòng, có điện trở tình cờ bằng điện trở của một bóng đèn. Tổng công suất toả ra trên các bóng đèn tăng hay giảm khi một trong các bóng đèn bị cháy? Tăng/giảm bao nhiêu lần? Có thể bỏ qua sự phụ thuộc của điện trở dây tóc vào nhiệt độ.

\dapso{Tổng công suất tăng xấp xỉ 1,11 lần.}

\baitap{5} Từ một dây điện trở đặc biệt, người ta cắt ra một đoạn có tổng điện trở $R_0$. Từ đoạn dây này uốn thành một vòng khép kín hình nhẫn (Hình~2). Trên vòng nhẫn, tại hai điểm được hàn hai tiếp điểm. Tìm điện trở giữa hai tiếp điểm nếu góc $\alpha = 120^\circ$!

\dapso{$R = (2/9)R_0$.}

\baitap{6} Để xác định điện trở suất của nước biển, một nhà hải dương học nhúng xuống nước một cáp có gắn ở đầu hai điện cực hình trụ đồng trục, cao $50\,\mathrm{mm}$. Đường kính ngoài của điện cực trong là $40\,\mathrm{mm}$, đường kính trong của điện cực ngoài là $45\,\mathrm{mm}$. Điện trở giữa hai điện cực là $9\,\Omega$. Tìm điện trở suất của nước!

\dapso{$\rho \approx 24\,\Omega\cdot\mathrm{m}$.}

\baitap{7} Trên một dây kim loại tiết diện đều (diện tích $1\,\mathrm{mm}^2$) có khắc một thang đo milimét, với các vạch cách nhau $1\,\mathrm{mm}$. Dây được kéo giãn không đều, sao cho khoảng cách $a$ giữa các vạch không còn là hằng số nữa mà phụ thuộc vào khoảng cách $l$ tính từ đầu dây, như trên Hình~3. Tổng chiều dài dây sau khi kéo giãn là $4\,\mathrm{m}$, và mật độ của dây không đổi trong quá trình kéo giãn. Tìm tổng điện trở của dây sau khi kéo giãn! Điện trở suất vật liệu là $1{,}0\times10^{-6}\,\Omega\cdot\mathrm{m}$. \emph{Ghi chú.} Nếu trong một bài toán, một phần dữ kiện được cho dưới dạng đồ thị, thì lời giải thường quy về việc tìm diện tích của đồ thị, độ dốc của nó, hoặc giao điểm của các đồ thị.

\includegraphics[width=0.42\linewidth]{page-04.png}\hfill\includegraphics[width=0.42\linewidth]{page-04.png}

\emph{(Hình 1, 2, 3: xem Phụ lục, trang gốc 4 -- các hình vẽ gốc chỉ chứa ký hiệu vật lý, không có văn bản cần dịch.)}

\subsection{Các định luật Kirchhoff}

Khi phân tích các mạch điện có độ phức tạp tuỳ ý, cơ sở là các định luật Kirchhoff. \emph{Định luật Kirchhoff~I}: tổng các dòng điện đi vào một nút bất kỳ của mạch điện bằng tổng các dòng điện đi ra khỏi nút đó. Điều này bắt nguồn, một mặt, từ định luật bảo toàn điện tích (chính xác hơn, từ điều kiện liên tục của dòng điện), và mặt khác, từ giả thiết rằng điện dung của dây dẫn và các nút của chúng là không đáng kể (điều này ít nhất đúng với các quá trình có tần số đủ thấp).

Ở đây, các cường độ dòng điện (cũng như hiệu điện thế và suất điện động) là các \emph{đại lượng đại số}, có thể nhận cả giá trị dương lẫn âm (chiều dương của dòng điện--điện áp trên mỗi phần tử tất nhiên phải được quy ước thống nhất từ trước).\footnote{Tương tự, ví dụ trong quang học tia sáng khi dùng công thức thấu kính, cả khoảng cách vật/ảnh tới thấu kính lẫn tiêu cự của thấu kính đều có thể mang giá trị âm nếu quy ước về dấu tương ứng được đặt ra một cách nhất quán.} Ví dụ, nếu trên một đoạn mạch, dòng điện tính ra âm thì điều đó đơn giản có nghĩa là chiều thực của nó ngược với chiều đã giả định ban đầu. Vậy nếu mạch chỉ chứa các phần tử thuần trở, không cần thiết phải phân tích riêng biệt mọi tổ hợp có thể của chiều dòng điện hay cực tính điện áp. Như vậy, nếu trong ngữ cảnh định luật Kirchhoff~I ta định nghĩa chiều dương của dòng điện là hướng về phía nút, thì có thể phát biểu định luật này như sau: tổng đại số các dòng điện hội tụ về một nút bất kỳ của mạch điện bằng không, tức $\sum_n I_n = 0$ (một vài $I_n$ tất nhiên phải mang giá trị âm). Nếu mạch có $N$ nút, thì theo định luật Kirchhoff~I có thể lập được $N-1$ phương trình độc lập.

\emph{Định luật Kirchhoff~II}: tổng đại số các suất điện động và các độ sụt áp dọc theo một vòng kín bất kỳ của mạch điện bằng không, tức $\sum_n U_n = 0$. Nếu độ sụt áp (trên phần tử thụ động) được lấy dấu dương, thì suất điện động gây ra dòng điện trong vòng phải được đưa vào phương trình với dấu âm. Định luật này xuất phát từ việc: khi đi vòng quanh theo mạch, ta quay trở lại đúng điểm có cùng điện thế -- tại các độ sụt áp, thế năng của hạt tải điện giảm (biến thành nhiệt Joule), còn khi đi qua suất điện động thì thế năng tăng (nhờ công do ngoại lực thực hiện). Theo định luật Kirchhoff~II có thể viết ra số phương trình bằng đúng số vòng độc lập trong mạch.

Trong những trường hợp đơn giản, khi biết một phần thông tin về các phần tử của mạch điện, có thể lần lượt biểu diễn tất cả các đại lượng chưa biết bằng cách áp dụng các định luật Kirchhoff. Ngược lại, cần phải lập một hệ phương trình. Để làm điều này một cách hệ thống, có thể dùng một trong các phương pháp sau.

\textbf{Phương pháp điện thế nút.} Ta xét điện thế của các nút trong mạch (so với một nút được chọn tuỳ ý) như là các đại lượng chưa biết cần tìm. Với cách này, định luật Kirchhoff~II tự động được thoả mãn. Bây giờ ta có thể viết định luật Kirchhoff~I cho mỗi nút, tính các điện áp trên các nhánh như hiệu điện thế giữa các nút lân cận.

\textbf{Phương pháp dòng điện vòng.} Trong phương pháp này, các đại lượng cần tìm là các \emph{dòng điện vòng}, tức là các dòng điện thực trên các nhánh của mạch, chung cho hai hay nhiều vòng, được xem là tổng đại số của các dòng điện vòng tương ứng (với mỗi vòng cần giả định một chiều đi vòng quanh). Với cách này, định luật Kirchhoff~I tự động được thoả mãn. Bây giờ ta có thể viết định luật Kirchhoff~II cho tất cả các vòng độc lập của mạch.

Các định luật Kirchhoff là tuyến tính nên cũng đúng cho các biến thiên (số gia) của dòng điện và điện áp. Giả sử chẳng hạn tại thời điểm ban đầu các dòng điện hội tụ về một nút là $I_n$, và sau một khoảng thời gian nào đó trở thành $I_n + \Delta I_n$. Định luật Kirchhoff~I đúng ở cả thời điểm đầu lẫn thời điểm cuối: $\sum_n I_n = 0$ và $\sum_n (I_n + \Delta I_n) = 0$, do đó quả thực $\sum_n \Delta I_n = 0$. Đương nhiên, điện áp của một nguồn suất điện động lý tưởng không thay đổi, tức $\Delta \mathcal{E} = 0$. Ví dụ cho điều này là bài~11, thoạt nhìn có vẻ thiếu dữ kiện, nhưng lại giải được dễ dàng nhờ ý tưởng vừa nêu.

\baitap{8} Trên Hình~4 là một phần của một mạch điện lớn hơn. Vào mạch có nối bốn ampe kế giống hệt nhau, mỗi cái có điện trở trong $100\,\Omega$. Số chỉ của ampe kế thứ nhất và thứ hai lần lượt là $3\,\mathrm{mA}$ và $5\,\mathrm{mA}$. Tìm điện trở $R$.

\dapso{$900\,\Omega$.}

\baitap{9} Mạch điện trên Hình~5 gồm các điện trở giống hệt nhau và các vôn kế giống hệt nhau. Số chỉ vôn kế thứ nhất là $19\,\mathrm{V}$, số chỉ vôn kế thứ ba là $9\,\mathrm{V}$. Tìm số chỉ vôn kế thứ hai!

\dapso{$12\,\mathrm{V}$.}

\baitap{10} Tìm tổng điện trở của mạch trên Hình~6 bằng cả hai phương pháp: điện thế nút và dòng điện vòng. \emph{Ghi chú.} Để đơn giản biểu thức, có thể coi rằng dòng điện qua mạch là $1\,\mathrm{A}$, hoặc rằng các cực ra của mạch được nối với nguồn điện áp $1\,\mathrm{V}$; trong trường hợp thứ nhất, độ sụt áp xuất hiện giữa hai đầu mạch về giá trị bằng số bằng điện trở của nó, trong trường hợp thứ hai, dòng điện vòng tương ứng về giá trị bằng số bằng nghịch đảo của điện trở.

\dapso{$26/7\,\Omega$.}

\baitap{11} Trong mạch điện trên Hình~7, $R_1/R_2 = 4$. Khi mắc thêm bóng đèn, số chỉ ampe kế tăng thêm $0{,}1\,\mathrm{A}$. Cường độ dòng điện qua bóng đèn là bao nhiêu? Nguồn điện và ampe kế là lý tưởng, các đặc tính của bóng đèn chưa biết.

\textbf{Nguyên lý chồng chất.} Định luật Ohm và các định luật Kirchhoff là tuyến tính, do đó trong một mạch điện chỉ chứa điện trở thuần và nguồn suất điện động, \emph{nguyên lý chồng chất} có hiệu lực dưới dạng sau: cường độ dòng điện tổng hợp qua một điện trở cho trước bằng tổng đại số các cường độ dòng điện mà mỗi nguồn suất điện động, nếu tác dụng riêng lẻ, sẽ gây ra qua điện trở đó (tức là tất cả các nguồn suất điện động khác đều bị nối tắt).

\baitap{12} Tìm cường độ dòng điện qua điện trở $R_3$ trong mạch điện trên Hình~8.

\baitap{13} Tìm dòng điện qua điện trở $8\,\Omega$ trong mạch trên Hình~9.

\baitap{14} Tìm cường độ dòng điện qua cả hai nguồn suất điện động trong mạch trên Hình~10.

\emph{(Hình 4--10: xem Phụ lục, trang gốc 5.)}

\subsection{Sơ đồ tương đương}

\textbf{Mắc hình sao và mắc hình tam giác.} Mắc hình sao luôn có thể biến đổi thành mắc hình tam giác tương đương về mặt chức năng điện, và ngược lại (Hình~11). Ta gọi đây là phép biến đổi $\Delta$--Y. Công thức biến đổi như sau:
\[
R_A = \frac{R_{AB}R_{AC}}{R_{AB}+R_{AC}+R_{BC}} \ \text{và tương tự theo chu kỳ},
\]
\[
R_{AB} = R_A + R_B + \frac{R_A R_B}{R_C} \ \text{và tương tự theo chu kỳ}.
\]

Các công thức này có dạng đặc biệt đơn giản trong trường hợp $R_{AB}=R_{AC}=R_{BC}=R_\Delta$ và $R_A=R_B=R_C=R_Y$. Khi đó rõ ràng $R_Y = R_\Delta/3$.

\baitap{15} Tìm điện trở của mạch trên Hình~12.

\textbf{Suất điện động và điện trở mắc nối tiếp.} Ai cũng biết rằng không một nguồn suất điện động thực nào (pin điện hoá, máy phát điện, v.v.) có thể duy trì điện áp không đổi trên các cực khi tải tăng lên. Mô hình đơn giản nhất cho một thiết bị như vậy giả định sự tồn tại của một \emph{điện trở trong} $r$, mắc nối tiếp với một nguồn suất điện động lý tưởng $\mathcal{E}$, trên đó xuất hiện độ sụt áp $Ir$ do dòng điện tiêu thụ, sao cho điện áp trên các cực của thiết bị là $V = \mathcal{E} - Ir$. Có thể thấy rằng bất kỳ mạch điện hai cực nào được cấu tạo từ các phần tử tuyến tính (điện trở thuần, nguồn suất điện động lý tưởng) đều tương đương với mô hình như vậy, tức là với một suất điện động $\mathcal{E}$ và một điện trở $r$ mắc nối tiếp (còn gọi là định lý Thévenin). Để kiểm chứng điều này đối với một mạch điện cụ thể, cần chỉ ra rằng điện áp trên các cực ra phụ thuộc vào cường độ dòng điện tiêu thụ $I$ theo hệ thức $V = \mathcal{E} - Ir$. Trong quá trình đó cũng sẽ tìm được các giá trị $\mathcal{E}$ và $r$ của sơ đồ tương đương. Một cách đơn giản hơn để tìm $\mathcal{E}$ và $r$ là viết hai phương trình cho hai trường hợp biên, với hai ẩn số: (1) điện áp trên các cực ra phải bằng suất điện động tương đương $\mathcal{E}$ khi mạch ngoài bị ngắt ($I=0$); (2) khi nối tắt các cực ra, dòng điện ngắn mạch phải bằng $\mathcal{E}/r$.

Đơn giản nhất và cũng thường gặp nhất là \emph{bộ phân áp} (sơ đồ phía trên trên Hình~14). Các tham số tương đương của nó đáng để ghi nhớ.

\baitap{16} Để làm đồ trang trí Giáng sinh, Juku đã tìm được 10 bóng đèn pin giống nhau (điện áp định mức $3\,\mathrm{V}$, công suất định mức $0{,}6\,\mathrm{W}$) và một bộ chỉnh lưu có điện áp trên cực $5\,\mathrm{V}$. Trên cơ sở đó anh thiết kế một sơ đồ mạch điện như trên Hình~13. Anh tính rằng cần mắc nối tiếp với bộ chỉnh lưu một điện trở $R$ có giá trị bao nhiêu, để điện áp trên các bóng đèn bằng điện áp định mức. Khi bật bộ chỉnh lưu, hoá ra các bóng đèn sáng mờ hơn nhiều so với dự kiến. Kiểm tra bằng đồng hồ vạn năng cho thấy điện áp trên cực bộ chỉnh lưu đã giảm xuống còn $4\,\mathrm{V}$ khi có tải, còn điện áp trên các bóng đèn là $2{,}3\,\mathrm{V}$. Cần chọn giá trị điện trở $R$ bằng bao nhiêu để các bóng đèn sáng với độ sáng bình thường?

\dapso{$R = 1\,\Omega$.}

\baitap{17} Dòng điện cực đại ($\mathcal{E}/r$) tất nhiên nhận được từ nguồn điện khi điện trở mạch ngoài bằng không (tức các cực bị nối tắt). Nhưng trong trường hợp đó, công suất điện tiêu thụ ở mạch ngoài cũng bằng không. Hãy chỉ ra rằng công suất hữu ích cực đại nhận được từ nguồn điện khi điện trở tải bằng điện trở trong của nguồn.

\baitap{18} Công suất điện cực đại nào có thể lấy được từ các cực ra của các mạch điện trên Hình~14?

\baitap{19} Giải lại bài~14 bằng cách sử dụng sơ đồ tương đương.

\textbf{Nguồn dòng lý tưởng.} \emph{Nguồn dòng lý tưởng} là thiết bị tạo ra một dòng điện có cường độ không đổi, không phụ thuộc vào điện trở mạch ngoài (hay điện áp trên các cực). Ký hiệu quy ước của nó được vẽ trên Hình~15 (vòng tròn nhỏ có mũi tên, mũi tên chỉ chiều dòng điện). Nguồn dòng lý tưởng thực sự (cũng như nguồn áp lý tưởng thực sự) không tồn tại trong thực tế. Bất kỳ mạch điện hai cực nào được cấu tạo từ các phần tử tuyến tính đều tương đương với một tổ hợp gồm một nguồn dòng lý tưởng $I_0$ và một điện trở $r$ mắc song song. Dễ dàng kiểm chứng rằng nguồn áp với suất điện động $\mathcal{E}$ và điện trở trong $r$ tương đương với một nguồn dòng lý tưởng $\mathcal{E}/r$ mắc song song với điện trở trong $r$.

\baitap{20} Tìm điện áp trên các cực ra và cường độ dòng điện qua điện trở $10\,\mathrm{k}\Omega$ trong mạch điện trên Hình~15 khi khoá $K$: a) mở; b) đóng.

\baitap{21} $N$ nguồn suất điện động được mắc song song. Suất điện động của nguồn thứ $i$ là $\mathcal{E}_i$, điện trở trong là $r_i$. Các tham số của nguồn tổng hợp thu được là gì? \goiy{Bước đầu, dễ hơn là tìm các tham số của nguồn dòng lý tưởng tương đương.}

\dapso{$\mathcal{E} = \dfrac{\sum_i \frac{1}{r_i}\mathcal{E}_i}{\sum_i \frac{1}{r_i}}, \quad r = \left(\sum_i \frac{1}{r_i}\right)^{-1}$.}

Với lời giải của bài toán cuối cùng này, ta đã chứng minh được định lý Millman: nếu mạch điện chứa hai nút $A$ và $B$, được nối với nhau bằng $N$ nhánh, trong đó nhánh thứ $i$ chứa một suất điện động $\mathcal{E}_i$ (đại lượng có dấu!) nối tiếp với một điện trở thuần $R_i$, thì hiệu điện thế giữa $A$ và $B$ được biểu diễn dưới dạng trung bình có trọng số
\[
U = \frac{\sum_i \frac{1}{R_i}\mathcal{E}_i}{\sum_i \frac{1}{R_i}}.
\]

\baitap{22} Hãy dùng định lý vừa phát biểu để viết ra đáp số của bài~12.

\emph{(Hình 11--15: xem Phụ lục, trang gốc 5--6.)}

\subsection{Các thủ thuật đặc biệt}

\textbf{Tính đối xứng.} Sự tồn tại một tính đối xứng nào đó trong mạch điện là dấu hiệu cho thấy một số điện áp, điện thế hay cường độ dòng điện là bằng nhau. Ngay cả khi để giải bài toán cần lập các phương trình dựa trên định luật Kirchhoff, thì các tính chất đối xứng của mạch cũng giúp giảm số ẩn số. Nếu có thể phản chiếu hay xoay mạch điện sao cho một số nút đổi chỗ cho nhau theo cách mà sơ đồ mạch vẫn giữ nguyên như ban đầu, thì điện thế của các nút đó phải bằng nhau. Các nút có cùng điện thế tất nhiên có thể được nối tắt (hoặc ngược lại, ngắt kết nối giữa chúng) mà không làm thay đổi chức năng điện của mạch. Tính đối xứng của mạch cũng có thể được phân tích đối với việc đổi cực tính nguồn điện, vì đối với các phần tử tuyến tính, điều này đơn giản có nghĩa là tất cả các độ sụt áp và cường độ dòng điện đổi dấu. Nếu sau thao tác này, sơ đồ mạch thu được trùng với sơ đồ ban đầu, thì suy ra, nhờ tính đối xứng, điện áp và cường độ dòng điện của các phần tử tương ứng phải bằng nhau.

Sơ đồ mạch điện ban đầu trong đề bài có thể được vẽ một cách khá tuỳ tiện, khiến cho sự tồn tại của các tính chất đối xứng cần thiết không hề rõ ràng (ví dụ, sơ đồ giữa trên Hình~16).

\baitap{23} Tìm điện trở của các mạch trên Hình~16.

\baitap{24} Tìm điện trở của mạch trên Hình~17.

\dapso{$R = 11/6\,\Omega$.}

\baitap{25} Tìm dòng điện qua tất cả các điện trở trong mạch trên Hình~18 (các nguồn suất điện động là lý tưởng).

\baitap{26} Sáu điện trở được nối với nhau như trên Hình~19. Tìm điện trở giữa hai đầu cực bất kỳ!

\dapso{$R = 1\,\Omega$.}

\textbf{Ampe kế và vôn kế lý tưởng.} Điện trở trong của ampe kế lý tưởng bằng không và về bản chất nó nối tắt các nút tương ứng. Điện trở trong của vôn kế lý tưởng là vô hạn và mạch có thể được xem là hở tại vị trí đó. Có thể xảy ra trường hợp sau đó mạch điện được đơn giản hoá thành tổ hợp nối tiếp và song song của các điện trở. Khi đó có thể trực tiếp tính dòng điện--điện áp riêng biệt trên từng điện trở và áp dụng quy tắc Kirchhoff để biểu diễn các dòng điện--điện áp chưa biết.

\baitap{27} Tìm số chỉ của ampe kế lý tưởng trong mạch điện trên Hình~20.

\baitap{28} Tìm số chỉ của ampe kế và vôn kế trong mạch điện trên Hình~21. Cả hai dụng cụ đo đều lý tưởng.

\dapso{$1\,\mathrm{mA}$, $4\,\mathrm{V}$.}

\textbf{Mạch tuần hoàn vô hạn.} Đối với các mạch có cấu trúc lặp lại tuần hoàn vô hạn, việc thêm hoặc bớt một mắt xích không làm thay đổi tổng điện trở của mạch, do đó ta có thể biểu diễn điện trở $R$ của mạch như một tổ hợp của $R$ và điện trở của một mắt xích đơn lẻ, rồi từ hệ thức thu được, giải ra $R$ cần tìm.

\baitap{29} Tìm điện trở của mạch vô hạn trên Hình~22.

\baitap{30} Tìm các tham số của nguồn suất điện động tương đương với mạch điện tuần hoàn vô hạn trên Hình~23.

\textbf{Lưới tuần hoàn vô hạn.} Các bài toán sau minh hoạ tình huống trong đó mạch điện có tính đối xứng vật lý rất cao, nhưng tính đối xứng của dòng điện chạy trong mạch lại thấp hơn. Trong một số trường hợp, có thể dựa vào nguyên lý chồng chất để xây dựng các bài toán con sao cho dòng điện chạy trong đó cũng có tính đối xứng.

\baitap{31} Tìm điện trở giữa hai nút lân cận của một lưới tam giác phẳng vô hạn (Hình~24). Điện trở của đoạn dây nối hai nút lân cận ở khắp nơi đều là $1\,\Omega$. \goiy{Ta ký hiệu hai nút cần tìm điện trở giữa chúng là $A$ và $B$. Gọi $C$ là một nút nào đó ở cách xa vô hạn so với $A$ và $B$. Cho dòng điện $I$ đi vào từ nút $A$ và lấy nó ra ở nút $C$. Vì $C$ ở rất xa, dòng điện tại nút $A$ phân kỳ đối xứng theo mọi hướng. Tương tự, nếu cho dòng điện $I$ đi vào từ nút $C$ và thu nó lại ở nút $B$, thì có thể khẳng định rằng dòng điện hội tụ về nút $B$ đối xứng từ mọi hướng.}

\dapso{$R = 1/3\,\Omega$.}

\baitap{32} Tìm điện trở giữa hai nút lân cận của một lưới lập phương vô hạn. Điện trở của đoạn dây nối hai nút lân cận ở khắp nơi đều là $1\,\Omega$.

\dapso{$R = 1/3\,\Omega$.}

\textbf{Điện trở âm.} Điện trở của một vật dẫn điện rõ ràng luôn là đại lượng dương. Tuy nhiên, như một thủ thuật toán học, cũng có thể hình dung điện trở âm, nhờ đó đôi khi có thể ``sửa chữa'' mạch điện theo cách phù hợp. Ví dụ, đoản mạch giữa các nút của mạch có thể được xem như mắc nối tiếp hai điện trở dương và âm bằng nhau về giá trị tuyệt đối, còn mạch hở lại tương ứng với mắc song song hai điện trở cùng loại như vậy.

\baitap{33} Giải lại bài~31 trong trường hợp đoạn dây nối hai nút $A$ và $B$ bị cắt đứt.

\dapso{$R = 1/2\,\Omega$.}

\emph{(Hình 16--24: xem Phụ lục, trang gốc 6--8.)}

\subsection{Phần tử mạch phi tuyến}

Tỉ lệ thuận giữa dòng điện qua vật dẫn và điện áp đặt vào thường bị vi phạm, và đôi khi vì những lý do khá đơn giản, ví dụ do phần tử nóng lên khi có dòng điện chạy qua. Ví dụ nổi tiếng nhất là bóng đèn sợi đốt, trong đó nhiệt độ hoạt động của sợi đốt lên tới hàng nghìn độ và không thể áp dụng định luật Ohm trong một khoảng điện áp rộng. Đáp ứng phi tuyến mạnh cũng do sự chuyển động phức tạp của hạt tải điện trong các linh kiện bán dẫn và trong phóng điện khí.

\textbf{Điốt lý tưởng.} \emph{Điốt} là một linh kiện bán dẫn dẫn dòng điện khá tốt theo một chiều, và gần như không dẫn theo chiều ngược lại. Điốt được gọi là lý tưởng nếu điện trở của nó bằng không khi phân cực thuận và vô cùng lớn khi phân cực ngược. Nói cách khác, khi phân cực thuận, điốt lý tưởng hoàn toàn không có độ sụt áp và về bản chất nối tắt mạch, còn khi phân cực ngược thì làm hở mạch và có thể chịu một điện áp có giá trị tuỳ ý trên nó. Khi biết rõ cực tính của điện áp đặt vào điốt, những mạch điện thoạt nhìn phức tạp có thể trở nên khá đơn giản.

Một mô hình đường đặc trưng vôn--ampe của điốt thực tế hơn (nhưng vẫn được lý tưởng hoá) được vẽ trên Hình~25, trong đó điốt mở hoàn toàn khi đạt tới một điện áp dương $U_\mathrm{d}$ nào đó, và đóng hoàn toàn ở các điện áp thấp hơn giá trị đó. Mô hình này cũng thường được dùng thành công trong thực tế, vì dòng điện qua điốt khi phân cực thuận tăng gần như theo hàm mũ theo điện áp.\footnote{Ví dụ, đối với điốt silic, $U_\mathrm{d}$ có giá trị cỡ $0{,}7\,\mathrm{V}$.}

Đối với phần tử phi tuyến (kể cả mô hình điốt vừa mô tả), công suất điện toả ra dưới dạng nhiệt vẫn được biểu diễn bằng công thức tổng quát $P = UI$. Trong khi đó, công thức $P = I^2 R = U^2/R$ ($R = \text{hằng số}$) chỉ đúng cho phần tử thuần trở.

\baitap{34} Cường độ dòng điện qua nguồn điện áp trong mạch trên Hình~26 thay đổi bao nhiêu lần nếu đổi cực tính của nguồn? Tất cả các điện trở đều bằng nhau, các điốt và nguồn suất điện động là lý tưởng.

\baitap{35} Tìm công suất nhiệt toả ra trên tất cả các điốt trong mạch điện trên Hình~27. Các điốt tuân theo mô hình trên Hình~25, với $U_\mathrm{d} = 1\,\mathrm{V}$.

\textbf{Phương pháp đồ thị.} Xét một mạch điện trong đó phần tử phi tuyến mắc nối tiếp với một điện trở thuần $R$, và mạch được đặt vào một suất điện động $\mathcal{E}$ (nếu cần, phải biến đổi mạch về dạng này bằng các thủ thuật đã nêu trước đó). Độ sụt áp $U$ và cường độ dòng điện $I$ trên phần tử phi tuyến là các đại lượng chưa biết, và định luật Ohm không áp dụng được cho toàn mạch. Tuy nhiên, đường đặc trưng của điện trở vẫn có thể biểu diễn qua $U$: $IR = \mathcal{E} - U$. Nghiệm rõ ràng là giao điểm của đường thẳng này với đường đặc trưng của phần tử phi tuyến.\footnote{Về mặt toán học, đây là việc giải đồ thị một phương trình siêu việt $f(x) = ax+b$, cần tìm giao điểm của các đồ thị $y=f(x)$ và $y=ax+b$.} Để vẽ đường thẳng chỉ cần hai điểm, chẳng hạn $U=0, I=\mathcal{E}/R$ và $I=0, U=\mathcal{E}$.

Nếu có nhiều phần tử phi tuyến mắc nối tiếp hoặc song song, cần cộng các đường đặc trưng của chúng tương ứng theo dòng điện hoặc theo điện áp, để được đường đặc trưng vôn--ampe tổng hợp.

\baitap{36} Cường độ dòng điện trong mạch trên Hình~28 là bao nhiêu? Đường đặc trưng vôn--ampe của điốt được cho trên đồ thị kèm theo.

\dapso{$I \approx 8\,\mathrm{mA}$.}

\baitap{37} Tìm cường độ dòng điện qua điốt $D_2$ trong mạch trên Hình~29! Các điốt giống hệt nhau và đường đặc trưng vôn--ampe của chúng tương tự như trong bài~36.

\baitap{38} Trên Hình~30 là đường đặc trưng vôn--ampe của một loại bóng đèn sợi đốt nào đó. Bóng đèn được nối với nguồn điện áp như trên sơ đồ kèm theo. Công suất toả ra trên bóng đèn là bao nhiêu?

\dapso{$P \approx 0{,}48\,\mathrm{W}$.}

\textbf{Độ ổn định của nghiệm, hiện tượng trễ.} Nếu đường đặc trưng của phần tử phi tuyến có hình dạng khá đặc biệt (đèn phóng điện khí, thyristor, điốt đường hầm, v.v.), có thể có nhiều giao điểm. Một số trong đó thường không ổn định. Để nghiên cứu tính ổn định, ta phân tích điều gì xảy ra khi điện áp $U$ lệch một chút khỏi giá trị cân bằng do một nhiễu loạn nào đó. Để làm điều này, ta giả định rằng có một tụ điện nhỏ mắc song song với phần tử phi tuyến.\footnote{Một biến thể khác là mắc nối tiếp với thiết bị một cuộn cảm. Thực ra, bất kỳ phần tử mạch nào cũng có một điện dung và điện cảm ký sinh nhất định.} Nếu điện áp trên phần tử tăng lên một chút, thì dòng điện qua phần tử phi tuyến và qua điện trở không còn bằng nhau nữa, và tụ điện sẽ bắt đầu nạp hoặc xả tuỳ thuộc vào độ dốc tiếp tuyến của đường đặc trưng phần tử phi tuyến (tức điện trở vi phân) tại giao điểm. Nếu hoá ra $dU/dt > 0$, thì điện áp sẽ tiếp tục tăng cho đến khi hệ đạt tới một điểm cân bằng khác. Như vậy dễ thấy rằng chẳng hạn trường hợp (a) trên Hình~31 là ổn định, còn (b) không ổn định. Trường hợp sau tương ứng với tình huống điện trở vi phân của phần tử phi tuyến (sẽ được nói tới sau) là âm. Nếu có nhiều nghiệm ổn định, thì nghiệm nào thực sự xảy ra trên thực tế sẽ phụ thuộc vào lịch sử (cách điện áp đặt vào mạch đã được thay đổi trước đó như thế nào). Với một số dạng đường đặc trưng nhất định, điều này có thể gây ra \emph{hiện tượng trễ}: khi thay đổi tuần hoàn điện áp hay dòng điện trên phần tử, ta thu được trên đồ thị $I$--$U$ một đường cong dạng vòng lặp (xem bài~39 và~140).

\baitap{39} Trên Hình~32 là sơ đồ nguyên lý đường đặc trưng của thyristor. Thyristor được mắc nối tiếp với điện trở $R$. Điện áp cực tiểu $U_0$ nào cần đặt vào mạch để thyristor mở (tức cường độ dòng điện trong mạch tăng đột ngột)? Hãy phác hoạ sự biến thiên của cường độ dòng điện trong mạch khi điện áp đặt vào tăng dần từ 0 đến $U_0$ và sau đó giảm trở lại về không!

\dapso{$U_0 \approx U_1 + I_1 R$.}

\textbf{Điện trở vi phân.} Nếu dòng điện qua phần tử phi tuyến biến thiên trong một giới hạn đủ nhỏ mà trong phạm vi đó đường đặc trưng của phần tử có thể xem là tuyến tính, thì khi phân tích mạch điện đối với thành phần xoay chiều, có thể thay thế phần tử này bằng một điện trở thuần tương đương, có giá trị được xác định bởi độ dốc $\Delta U/\Delta I$ của đường đặc trưng, hay còn gọi là \emph{điện trở vi phân}, trong vùng đường đặc trưng đang xét. Khác với điện trở tích phân ($R = U/I$), điện trở vi phân cũng có thể mang giá trị âm.

\baitap{40} Do cấu tạo đặc biệt, đường đặc trưng của điốt đường hầm có dạng gần giống như trên đồ thị Hình~33. Cũng được cho là sơ đồ bộ khuếch đại đơn giản nhất dựa trên điốt đường hầm. Tìm số lần khuếch đại tín hiệu xoay chiều biên độ nhỏ đưa vào đầu vào.

\dapso{$\sim 3$ lần.}

\baitap{41} Để xác định cường độ dòng điện trong mạch điện, người ta mắc vào mạch một ampe kế có thang đo thay đổi được. Ở thang đo $10\,\mathrm{mA}$, số chỉ ampe kế là $2{,}95\,\mathrm{mA}$, ở thang đo $3\,\mathrm{mA}$ là $2{,}90\,\mathrm{mA}$. Cường độ dòng điện trong mạch khi không có ampe kế là bao nhiêu? Có thể giả định rằng đây là ampe kế kiểu điện từ, có điện trở trong tỉ lệ nghịch với độ rộng thang đo. \goiy{Vì độ chênh lệch giữa các số chỉ ampe kế là tương đối nhỏ, có thể dùng phép gần đúng tuyến tính và coi độ biến thiên cường độ dòng điện do điện trở phụ thêm vào mạch tỉ lệ với giá trị điện trở đó.}

\dapso{$I = 2{,}97\,\mathrm{mA}$.}

\textbf{Bóng đèn sợi đốt.} Trong mô hình đơn giản nhất của bóng đèn sợi đốt, có thể bỏ qua tổn hao do dẫn nhiệt và giả định rằng toàn bộ điện năng tiêu thụ được tiêu tán dưới dạng bức xạ. Khi đó sợi đốt có thể được xem như vật đen tuyệt đối, tức cường độ bức xạ của nó trên một đơn vị diện tích tỉ lệ với $\alpha\sigma T^4$, trong đó $\alpha$ là tham số đặc trưng cho khả năng bức xạ của bề mặt (đối với volfram xấp xỉ $0{,}5$). Sự dẫn nhiệt cũng đóng góp một phần, nhưng phần đóng góp này, trong xấp xỉ đầu tiên, tỉ lệ với hiệu nhiệt độ. Do đó, đóng góp của dẫn nhiệt trở nên vô cùng nhỏ ở nhiệt độ cao. Đối với các quá trình diễn ra rất nhanh, cũng có thể tạm thời bỏ hẳn tổn hao nhiệt.

Khía cạnh rắc rối nhất là sự phụ thuộc của điện trở vào nhiệt độ. Sự phụ thuộc của điện trở hay điện trở suất vật dẫn vào nhiệt độ, trong một khoảng nhiệt độ hẹp, thường được mô tả bằng hiệu chỉnh tuyến tính theo nhiệt độ:
\[
R(T) = R_0[1+\alpha(T-T_0)],
\]
trong đó $R_0$ là điện trở tại nhiệt độ $T_0$ (ví dụ nhiệt độ phòng). Trong khoảng nhiệt độ rộng hơn (đối với bóng đèn sợi đốt, cỡ vài nghìn độ), nên tính thêm một số hạng hiệu chỉnh bậc cao hơn, ví dụ
\[
R(T) = R_0[1+\alpha(T-T_0)+\beta(T-T_0)^2].
\]
Tiếc rằng dựa trên những hệ thức như vậy, việc thu được các kết quả giải tích tổng quan đơn giản là khó khăn. Đôi khi có thể dùng một mô hình khá thô, trong đó điện trở kim loại được lấy tỉ lệ thuận với nhiệt độ tuyệt đối. Trên Hình~34 là sự phụ thuộc thực tế đối với volfram, làm ví dụ.

\baitap{42} Hãy chỉ ra rằng nếu lấy điện trở sợi đốt tỉ lệ với nhiệt độ tuyệt đối, thì đường đặc trưng vôn--ampe của bóng đèn sợi đốt là $I \propto U^{3/5}$.

\baitap{43} Trên đế của một bóng đèn sợi đốt có ghi: $26\,\mathrm{V}$ \ $0{,}12\,\mathrm{A}$. Ở nhiệt độ phòng, điện trở sợi đốt đo được là $R_0 = 24\,\Omega$. Hãy ước lượng chiều dài $l$, đường kính $d$ của sợi đốt và nhiệt độ hoạt động $T$! Sợi đốt làm từ volfram, có điện trở suất ở nhiệt độ phòng là $\rho_0 = 5{,}3\times10^{-8}\,\Omega\cdot\mathrm{m}$.

\dapso{$l \approx 12\,\mathrm{cm}$, $d \approx 5{,}8\,\mu\mathrm{m}$, $T \approx 2650\,\mathrm{K}$.}

\baitap{44} Chiều dài sợi đốt của bóng đèn halogen là $5\,\mathrm{cm}$. Sợi đốt làm từ dây volfram, có khối lượng riêng $19300\,\mathrm{kg/m^3}$ và nhiệt dung riêng $134\,\mathrm{J/(kg\cdot K)}$ có thể coi là không đổi trong khoảng nhiệt độ ta quan tâm. Sự phụ thuộc điện trở suất của volfram vào nhiệt độ được cho trên Hình~34. Do sơ suất, bóng đèn được cấp một điện áp một chiều quá lớn là $120\,\mathrm{V}$. Cần bao lâu để nhiệt độ nóng chảy của volfram $3410^\circ\mathrm{C}$ đạt được?

\emph{(Hình 25--34: xem Phụ lục, trang gốc 8--11.)}

LATEXEOF
echo "section1 written, wc:"; wc -l /home/claude/build/dientu.tex
