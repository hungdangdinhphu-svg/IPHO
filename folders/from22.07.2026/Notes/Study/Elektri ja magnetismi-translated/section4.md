cat >> /home/claude/build/dientu.tex << 'LATEXEOF'
\section{Từ tĩnh học}

\subsection{Định luật Biot--Savart}

Một trong những bài toán cơ bản của từ tĩnh học là tính từ trường do các dòng điện dừng (tĩnh) tạo ra. Mặc dù nguồn gốc của từ trường là các điện tích chuyển động, các định luật cơ bản của từ tĩnh học thường được biểu diễn qua dòng điện. Mỗi dòng điện được mô tả bởi một mạch dòng và cường độ dòng điện $I$ chạy trong đó. Nếu ta ký hiệu dịch chuyển vi phân dọc theo mạch dòng theo chiều dòng điện là $d\mathbf{l}$, thì đại lượng $Id\mathbf{l}$ được gọi là \emph{phần tử dòng điện}. Phần tử dòng điện đóng vai trò trong từ tĩnh học tương tự như điện tích điểm trong tĩnh điện học. Có thể xem \emph{định luật Biot--Savart} là tương tự của định luật Coulomb, theo đó phần tử dòng điện $Id\mathbf{l}$ đóng góp vào cảm ứng từ ở khoảng cách $r$ một lượng
\[
d\mathbf{B} = \frac{\mu_0 I}{4\pi}\frac{d\mathbf{l}\times\hat{\mathbf{r}}}{r^2}.
\]

Tích có hướng của hai vectơ luôn vuông góc với cả hai vectơ đó, do đó vectơ $d\mathbf{B}$ vuông góc với cả phương dòng điện và bán kính vectơ $\mathbf{r}$. Hướng của $d\mathbf{B}$ dễ tìm nhất theo quy tắc vặn đinh ốc sau: nếu quay vectơ thứ nhất trong tích có hướng, $d\mathbf{l}$, một cách hình thức về phía vectơ thứ hai, $\mathbf{r}$ (theo góc nhỏ hơn!), thì hướng của tích có hướng là hướng chuyển động của một đinh ốc quay theo chiều kim đồng hồ (đinh ốc tay phải).

Trường do một cấu hình dòng điện bất kỳ tạo ra có thể tìm được nhờ định luật Biot--Savart và nguyên lý chồng chất. Dễ thấy rằng các đường sức cảm ứng từ do một dòng điện thẳng tạo ra là các đường tròn đồng trục. Từ đó ta có một quy tắc vặn đinh ốc thuận tiện hơn để xác định hướng vectơ $\mathbf{B}$, được minh hoạ trên Hình~48.

Vì dòng điện là chuyển động có hướng của điện tích, từ định luật Biot--Savart ta cũng suy ra được trường do một điện tích điểm $q$ chuyển động với vận tốc $\mathbf{v}$ tạo ra:
\[
\mathbf{B} = \frac{\mu_0 q}{4\pi}\frac{\mathbf{v}\times\hat{\mathbf{r}}}{r^2}. \tag{6}
\]

\baitap{116} Tìm cảm ứng từ trên trục một vòng dây tròn, tại khoảng cách $x$ tính từ mặt phẳng vòng dây. Cường độ dòng điện trong vòng là $I$, bán kính vòng là $R$.

\dapso{$B(x) = \frac{1}{2}\mu_0 R^2 I/(R^2+x^2)^{3/2}$.}

\subsection{Định lý lưu số}

Vì trong tự nhiên không tồn tại từ tích (đơn cực từ), định lý Gauss đối với từ trường có dạng sau:
\[
\oint_S B_n\,dS = 0.
\]
Điều này có nghĩa là các đường sức cảm ứng từ khép kín (không bắt đầu và không kết thúc ở đâu cả). Ví dụ, các đường sức cảm ứng từ do một phần tử dòng điện tạo ra là các đường tròn đồng trục, như ta đã thấy ở trên khi xét định luật Biot--Savart.

Gọi $\Gamma$ là một đường cong kín bất kỳ. Ta ký hiệu $d\mathbf{l}$ là dịch chuyển vi phân dọc theo đường cong, và $B_l$ là hình chiếu của vectơ $\mathbf{B}$ lên vectơ $d\mathbf{l}$. \emph{Lưu số} của trường vectơ $\mathbf{B}$ dọc theo đường cong $\Gamma$ được gọi là tích phân đường
\[
\oint_\Gamma \mathbf{B}\cdot d\mathbf{l} = \oint_\Gamma B_l\,dl.
\]

Khái niệm lưu số một lần nữa có thể minh hoạ thuận tiện qua ví dụ dòng chảy chất lỏng. Lưu số khác không của vectơ vận tốc phần tử chất lỏng có nghĩa là trong chất lỏng xảy ra chuyển động xoáy, tức nhiễu loạn (turbulence).

Vì các đường sức cảm ứng từ tạo thành các đường cong khép kín, rõ ràng lưu số của $\mathbf{B}$ dọc theo một đường kín nói chung phải khác không. Điều này được biểu diễn bởi \emph{định lý lưu số}, hay còn gọi là \emph{định luật tổng dòng điện}, mà ta trình bày ở đây không chứng minh:
\[
\oint_\Gamma B_l\,dl = \mu_0\sum_i I_i,
\]
trong đó tổng lấy theo tất cả các dòng điện $I_i$ được bao bọc bởi đường cong $\Gamma$. Các dòng điện $I_i$ cần được xem là các đại lượng đại số. Những dòng điện có chiều liên hệ với chiều đi vòng theo quy tắc vặn đinh ốc cần được lấy dấu dương. Đường cong $\Gamma$ nên được chọn sao cho việc tính tích phân đường trở nên đơn giản, tức sao cho ít nhất trên từng phần của đường cong, $B_l = \text{hằng số}$.

Định lý lưu số cho phép, trong một số trường hợp đơn giản (trường của dòng điện thẳng, của ống dây), tính dễ dàng cảm ứng từ. Định lý lưu số đóng vai trò trong từ tĩnh học giống hệt vai trò của định lý Gauss trong tĩnh điện học.

\baitap{117} Tìm cảm ứng từ do một dòng điện phẳng vô hạn tạo ra. Mật độ dòng điện (A/m) ở khắp mọi nơi bằng nhau và bằng $\alpha$.

\dapso{$B = \mu_0\alpha/2$.}

\baitap{118} Tìm cảm ứng từ tại khoảng cách $r$ tính từ một dây thẳng dài vô hạn. Cường độ dòng điện trong dây là $I$.

\dapso{$B = \mu_0 I/(2\pi r)$.}

\baitap{119} Tìm cảm ứng từ tại khoảng cách $r$ tính từ trục một dây dẫn tiết diện hình trụ, nếu mật độ dòng điện (A/m$^2$) đồng đều trong toàn bộ tiết diện dây và bằng $J$. Bán kính hình trụ là $R$.

\dapso{$B(r) = \begin{cases}\mu_0 J r/2 & r<R\\ \mu_0 J R^2/(2r) & r\ge R\end{cases}$.}

\baitap{120} \emph{Ống dây (solenoid)} là tên gọi một dây dẫn mảnh được quấn đều và sát nhau trên một khung hình trụ. Xét một ống dây rất dài, trong đó số vòng dây trên một đơn vị chiều dài dọc theo trục là $n$, và cường độ dòng điện trong dây là $I$. Ống dây như vậy là tương tự về từ của tụ điện phẳng. Hãy chứng minh rằng: a) bên trong ống dây, từ trường đều và hướng dọc theo trục; b) bên ngoài ống dây, từ trường bằng không; c) giá trị cảm ứng từ bên trong ống dây là $B = \mu_0 n I$.

\subsection{Nguyên lý chồng chất}

Nguyên lý chồng chất và các biến thể tinh vi hơn của nó có hiệu lực trong từ tĩnh học về cơ bản giống như trong tĩnh điện học. Nhờ bản chất của định luật Biot--Savart, có thể giải một cách dễ dàng ngay cả một số bài toán mà trong tĩnh điện học sẽ đòi hỏi phải tính tích phân (ví dụ bài~121).

\baitap{121} Trên Hình~49 là hai mạch dòng điện, có cường độ dòng điện là $I$ (các đoạn thẳng của dòng điện kéo dài tới vô cực). Tìm giá trị cảm ứng từ tại điểm được đánh dấu chấm đen, ứng với mỗi mạch dòng.

\baitap{122} Giá trị cảm ứng từ tại đầu (trên trục) của một ống dây dài là bao nhiêu? Số vòng dây trên một đơn vị chiều dài dọc theo trục ống dây là $n$, cường độ dòng điện là $I$.

\dapso{$B = \frac{1}{2}\mu_0 n I$.}

\baitap{123} Xác định cảm ứng từ trong khoang rỗng, được tạo thành do sự giao nhau của hai dây dẫn thẳng dài vô hạn, tiết diện hình trụ song song (Hình~50). Mật độ dòng điện trong hai dây bằng nhau nhưng ngược chiều ($\pm\mathbf{J}$), bán kính mỗi dây là $R$ và khoảng cách giữa hai tâm là $\mathbf{d}$.

\dapso{$\mathbf{B} = (\mu_0/2)\mathbf{J}\times\mathbf{d}$ (trường đều, thẳng đứng).}

\subsection{Định luật Ampère}

Phần tử dòng điện $Id\mathbf{l}$ chịu tác dụng của lực trong từ trường $\mathbf{B}$
\[
d\mathbf{F} = Id\mathbf{l}\times\mathbf{B}.
\]

Từ đây, ta có thể suy ra lực gọi là \emph{lực Lorentz} tác dụng lên điện tích điểm $q$ chuyển động với vận tốc $\mathbf{v}$:
\[
\mathbf{F} = q\mathbf{v}\times\mathbf{B}.
\]

\baitap{124} Tìm lực tác dụng trên một đơn vị chiều dài giữa hai dây dẫn thẳng song song dài vô hạn, nếu cường độ dòng điện trong các dây là $I_1$ và $I_2$, khoảng cách giữa hai dây là $r$.

\dapso{$F = \mu_0 I_1 I_2/(2\pi r)$.}

\subsection{Lưỡng cực từ}

\emph{Lưỡng cực từ} là tương tự của lưỡng cực điện. Vì không tồn tại từ tích, lưỡng cực từ là gần đúng thô nhất để mô tả từ trường do một hệ dòng điện bất kỳ tạo ra ở những khoảng cách lớn. Mô hình đơn giản nhất của lưỡng cực từ là một mạch dòng điện phẳng vô cùng nhỏ. Mạch dòng này được đặc trưng bởi \emph{mômen từ} $\mathbf{p}$, có độ lớn bằng $SI$ ($I$ là cường độ dòng điện trong mạch và $S$ là diện tích mạch), phương được xác định bởi pháp tuyến của mặt phẳng mạch và chiều theo quy tắc vặn đinh ốc. $p$ không phụ thuộc vào hình dạng của mạch. Lưỡng cực từ $\mathbf{p}$ tạo ra tại điểm không gian $\mathbf{r}$ một trường mà trong toạ độ cực được biểu diễn như sau (so sánh với công thức 4):
\[
B_r = \frac{\mu_0 p}{2\pi r^3}\cos\theta, \qquad B_\theta = \frac{\mu_0 p}{4\pi r^3}\sin\theta.
\]

Trong trường ngoài $\mathbf{B}$, lưỡng cực chịu tác dụng của mômen quay $\mathbf{M} = \mathbf{p}\times\mathbf{B}$, có xu hướng làm quay vectơ $\mathbf{p}$ cùng hướng với $\mathbf{B}$.

Năng lượng lưỡng cực từ trong trường ngoài $\mathbf{B}$ là $\Pi = -\mathbf{p}\mathbf{B}$. Do đó, trong trường không đều, lên lưỡng cực tác dụng một lực có thành phần theo $x$ là $F_x = p(\partial B/\partial x)$.

Trường của lưỡng cực từ có thể mô tả, ví dụ, từ trường ở khoảng cách lớn do một khối vật liệu bị nhiễm từ (nam châm vĩnh cửu) tạo ra. Mômen từ tương ứng khi đó là tổng vectơ mômen từ của các dòng điện vi mô cơ bản tồn tại trong vật chất (xem thêm mục 4.6).

\baitap{125} Điện tích $Q$ phân bố đều trên bề mặt một mặt cầu bán kính $R$. Mặt cầu quay với vận tốc góc $\omega$ quanh trục đi qua tâm. Tìm mômen từ của hệ như vậy. \goiy{Chia bề mặt mặt cầu thành các lớp mỏng vô hạn và lấy tổng. Diện tích của một đới cầu mỏng được xác định bởi bề dày $\Delta h$ của nó: $\Delta S = 2\pi R\,\Delta h$.}

\dapso{$p = QR^2\omega/3$.}

\baitap{126} Một nam châm vĩnh cửu được treo bằng một sợi dây. Mômen từ của nó là $p$ (vectơ $\mathbf{p}$ nằm trong mặt phẳng nằm ngang) và mômen quán tính đối với trục thẳng đứng đi qua điểm treo là $I$. Với chu kỳ nào sẽ xảy ra các dao động nhỏ tự do, nếu tạo ra trong không gian một từ trường ngang đều với cảm ứng từ $B$?

\dapso{$T = 2\pi\sqrt{I/(pB)}$.}

\baitap{127} Hai nam châm vĩnh cửu (mômen từ $p_1$ và $p_2$) được đặt cách nhau một khoảng $r$, lớn hơn nhiều so với kích thước của chúng. Tìm lực tác dụng giữa hai nam châm.

\dapso{$F = -\dfrac{3\mu_0}{2\pi r^4}(p_1\hat{\mathbf{r}})(p_2\hat{\mathbf{r}})$.}

\baitap{128} Tỉ số giữa mômen từ và mômen động lượng tương ứng của một hạt cơ bản được gọi là \emph{tỉ số hồi chuyển từ}. Hãy tìm tỉ số hồi chuyển từ đối với chuyển động quỹ đạo của electron, dựa trên lý thuyết Bohr về chuyển động của electron.\footnote{Theo lý thuyết Bohr, electron chuyển động trên quỹ đạo tròn quanh hạt nhân, trong đó mômen động lượng quỹ đạo của electron bị lượng tử hoá: $mvr = n\hbar$, với $n=1,2,3,\dots$.}

\dapso{$p/L = -e/2m$.}

\subsection{Từ trường trong vật chất}

Cho tới nay, ta đã xét các bài toán từ tĩnh học trong đó sự phân bố dòng điện trong không gian được cho trước và cố định. Khi đưa từ trường vào một khối vật liệu, ta phải tính đến sự \emph{nhiễm từ} của vật chất, tức sự định hướng lại của các dòng điện phân tử tuần hoàn bên trong vật chất dưới tác dụng của từ trường. Các dòng điện phân tử này bắt nguồn từ các electron chuyển động tuần hoàn trong nguyên tử và từ mômen từ riêng của chúng (spin). Như vậy nguyên tử và phân tử có mômen từ. Khi không có trường ngoài, các mômen từ này được định hướng hỗn loạn (trừ các chất sắt từ), và các trường vi mô của chúng triệt tiêu lẫn nhau. Khi bật trường ngoài, các lưỡng cực này có xu hướng định hướng ưu tiên theo phương trường -- vật chất bị nhiễm từ. Bên trong vật chất, các dòng điện vi mô vẫn triệt tiêu lẫn nhau, nhưng trên bề mặt vật chất, các dòng điện phân tử đều chạy theo cùng một chiều và tạo thành một dòng điện vĩ mô nào đó. Như vậy, vật chất bị nhiễm từ tạo ra một trường phụ, được xác định bởi các dòng điện mặt này. Ví dụ, trường của một nam châm vĩnh cửu hình trụ, nhiễm từ đều dọc theo trục, hoàn toàn giống trường của một ống dây có cùng kích thước; trường của nam châm vĩnh cửu hình ống rỗng có thể biểu diễn như trường tổng hợp của hai ống dây đồng trục, v.v.

Để xử lý từ trường trong vật chất, ngoài cảm ứng từ, dùng thêm \emph{cường độ từ trường} $\mathbf{H} = \mathbf{B}/\mu\mu_0$, trong đó độ từ thẩm tương đối $\mu$ là một hằng số đặc trưng cho vật liệu. Đối với chất sắt từ $\mu \gg 1$, đối với mọi chất khác $\mu \approx 1$. Tương tự như độ điện dịch, cường độ từ trường chỉ được xác định bởi sự phân bố dòng điện dẫn tự do trong không gian. Định lý lưu số, viết theo vectơ $\mathbf{H}$, có dạng
\[
\oint_\Gamma H_l\,dl = \sum_i I_i,
\]
trong đó lần này $I_i$ là các dòng điện dẫn được bao bọc bởi đường cong $\Gamma$ (tức không tính vào $I_i$ các dòng điện phân tử cảm ứng trên bề mặt vật liệu nhiễm từ). Từ đó dễ suy ra rằng $H_\tau$ phải liên tục trên mặt phân cách hai môi trường. Ngoài ra ta biết rằng các đường sức của $\mathbf{B}$ khép kín, do đó $B_n$ cũng liên tục trên mặt phân cách các môi trường.

Cũng như trong tĩnh điện học, đối với từ trường ngoài đều, thường hợp lý khi giả định rằng trường bên trong vật liệu từ cũng đều và sự nhiễm từ là đồng đều. Khi đó chỉ còn phải xác định xem, với cách chọn phù hợp giá trị cường độ trường và độ nhiễm từ, có thoả mãn được điều kiện liên tục của $B_n$ và $H_\tau$ trên khắp bề mặt vật liệu từ hay không.

Các phương trình cơ bản của tĩnh điện học và từ tĩnh học nói chung có cấu trúc tương tự nhau, khác biệt duy nhất là sự vắng mặt của từ tích. Do đó có thể vận dụng thành công sự tương tự giữa các đại lượng tương ứng ($\mathbf{E}\leftrightarrow\mathbf{H}$, $\mathbf{D}\leftrightarrow\mathbf{B}$, $\varepsilon\leftrightarrow\mu$) để giải một số bài toán từ tĩnh học, nếu biết lời giải bài toán tĩnh điện học tương ứng, hay ngược lại.

\baitap{129} Mômen từ của nguyên tử sắt là $p = 2{,}2\mu_B$, trong đó $\mu_B = e\hbar/2m_e \approx 9{,}27\times10^{-24}\,\mathrm{A\cdot m^2}$ là \emph{magneton Bohr} (mômen từ riêng của electron). Khoảng cách giữa các nguyên tử lân cận trong mạng tinh thể lập phương của sắt là $d=2{,}3\,\text{Å}$. Cảm ứng từ trong sắt bị nhiễm từ tối đa, khi không có trường ngoài, sẽ lớn bằng bao nhiêu?

\dapso{$B = \mu_0 p/d^3 \approx 2{,}1\,\mathrm{T}$.}

\baitap{130} Tìm cảm ứng từ bên trong một ống dây dài vô hạn, nếu ống dây được lấp đầy vật liệu có độ từ thẩm tương đối $\mu$. Số vòng--ampe trên một đơn vị chiều dài dọc theo trục ống dây là $nI$.

\dapso{$B = \mu\mu_0 nI$.}

\baitap{131} Một khối cầu từ tính có độ từ thẩm tương đối $\mu$ được đặt vào từ trường đều $\mathbf{B}_0$. Tìm cảm ứng từ bên trong khối cầu. \goiy{Cảm ứng từ bên ngoài một khối cầu nhiễm từ đều tương tự trường của một lưỡng cực từ đặt tại tâm khối cầu.}

\dapso{$B = \dfrac{3\mu}{2+\mu}B_0$ (so sánh bài~113).}

\subsection{Chất sắt từ}

Đặc điểm của chất sắt từ là $\mu \gg 1$ và phụ thuộc vào $H$. Đồng thời $\mu$ (cũng như $B$) không phải là hàm đơn trị của $H$. Nếu $H$ biến đổi tuần hoàn, thì trong hệ trục $B$--$H$ hình thành một \emph{vòng trễ (hysteresis)}, diện tích của nó (tức $\oint HB\,dH$) bằng nhiệt lượng toả ra trong một đơn vị thể tích chất sắt từ trong một chu kỳ (gọi là \emph{công từ hoá lại}). Trong trường rất mạnh, độ nhiễm từ của vật liệu đạt tới giá trị cực đại hữu hạn (tất cả các dòng điện phân tử đều được định hướng theo cùng một chiều) và do đó $\mu \to 1$.

Khi nghiên cứu sự gãy khúc của các đường sức tại bề mặt chất sắt từ, do điều kiện $\mu \gg 1$, ta đi đến kết luận rằng trong chất sắt từ, $\mathbf{B}$ gần như song song với bề mặt, còn bên ngoài chất sắt từ thì gần như vuông góc với bề mặt. Do đó, trong các bài toán về mạch từ, có thể xem các đường sức cảm ứng từ tập trung chủ yếu bên trong chất sắt từ, và bỏ qua sự ``rò rỉ'' của chúng qua bề mặt bên của chất sắt từ.

\baitap{132} Một nam châm điện dùng trong phòng thí nghiệm gồm một lõi sắt (độ từ thẩm tương đối $\mu$), quanh đó quấn một cuộn dây $N$ vòng (Hình~51). Bề rộng khe hở không khí $d$ nhỏ hơn nhiều so với bề dày lõi. Tổng chiều dài lõi là $l$. Cảm ứng từ trong khe hở không khí là bao nhiêu, nếu cường độ dòng điện là $I$?

\dapso{$B = \mu_0 NI/(l/\mu + d)$.}

\baitap{133} Một nam châm điện gồm lõi $1$ và phần ứng (armature) $2$ (Hình~52); độ từ thẩm tương đối của mỗi phần là $\mu$. Trên lõi có quấn một cuộn dây $N$ vòng, có dòng điện $I$ chạy qua. Diện tích tiết diện của lõi và phần ứng là $S$ và tổng chiều dài là $l$. Tìm lực hút mà lõi giữ phần ứng. \goiy{Ở đây có thể dùng phương pháp dịch chuyển ảo. Đồng thời cần lưu ý rằng, khi thay đổi khoảng cách giữa lõi và phần ứng, trong cuộn dây sẽ cảm ứng một suất điện động, mà nguồn điện phải thực hiện công chống lại nó.}

\dapso{$F = -\mu^2\mu_0 S N^2 I^2/l^2$.}

\subsection{Chất siêu dẫn}

Bên trong chất siêu dẫn luôn có $\mathbf{B}=0$, kể cả đối với trường tĩnh (gọi là hiệu ứng Meissner). Hệ quả: a) ngay sát bên ngoài chất siêu dẫn, $B_n=0$, tức các đường sức song song với bề mặt; b) theo định lý lưu số, bên trong chất siêu dẫn $I=0$, tức dòng điện chỉ có thể tồn tại trong lớp bề mặt. Nếu đưa một dây dẫn có dòng điện lại gần chất siêu dẫn, trên bề mặt chất siêu dẫn sẽ cảm ứng các dòng điện sao cho vừa đúng triệt tiêu từ trường ngoài bên trong chất siêu dẫn. Trong một số trường hợp đơn giản, có thể tìm tác dụng của các dòng điện mặt này bằng phương pháp ảnh điện. Dòng điện ngoài và dòng điện ảnh phải tạo ra một trường tổng hợp sao cho $B_n=0$.

\baitap{134} Cách bề mặt một chất siêu dẫn phẳng vô hạn một khoảng $h$, có một dây dẫn thẳng dài vô hạn song song với bề mặt chất siêu dẫn, có cường độ dòng điện $I$. Tìm lực tác dụng lên một đơn vị chiều dài của dây dẫn này.

\dapso{$F = \mu_0 I^2/(4\pi h)$.}

\emph{(Hình 48--52: xem Phụ lục, trang gốc 21--25.)}

LATEXEOF
echo done; wc -l /home/claude/build/dientu.tex
