# Vật Lý Từ First Principles — Một Sợi Chỉ Xuyên Suốt

> *"Không biết nếu hiểu sâu sắc được những thứ thầy gửi, em có thấy mọi đề thi HSGQG Lý hay rộng hơn nữa, là cả Vật Lý, đều 'hiển nhiên' và 'dễ khủng khiếp' hay không...?"*

> *"Có vẻ giống việc này: Số lượng tiên đề và định luật, những thứ nền tảng của Vật Lý cốt lõi là rất ít. Chúng ta đang được học quá nhiều thứ chỉ đúng trong những trường hợp riêng lẻ, hoặc là hệ quả. Khi nhìn vào đề thì chúng ta không biết nên xài công cụ gì, nhưng thực tế nếu chúng ta học những thứ nền tảng nhất của Vật Lý (dĩ nhiên rào cản lớn vẫn là Toán học), thì chúng ta có quá ít công cụ để thắc mắc bản thân cần dùng công cụ vật lý nào."*

## Lời nói thật trước khi bắt đầu

Mình sẽ làm đúng thứ bạn yêu cầu: dựng một bộ khung khiến toàn bộ Vật Lý nhìn như hệ quả của **một** ý tưởng. Nhưng có một sự thật cần nói thẳng: **"hiểu first principles" không miễn phí "kỹ năng giải toán"**. Một đề IPhO khó không phải vì nó dùng định luật bạn chưa biết — nó khó vì nó buộc bạn *kết hợp* 3-4 nguyên lý quen thuộc theo một cách bạn chưa từng thấy, dưới áp lực thời gian, với một mô hình hoá (modelling) tinh tế. First principles cho bạn *bản đồ* — nó không đi bộ hộ bạn. Nhưng bản đồ tốt làm số bước đi giảm 10 lần, và đó chính xác là thứ tài liệu này cố làm.

Cấu trúc tài liệu: mọi thứ bắt nguồn từ **một phiếm hàm tác dụng** $S$, và quy luật "tự nhiên chọn đường đi làm $S$ dừng (stationary)". Từ một câu đó, bạn sẽ thấy cơ học Newton, điện từ Maxwell, tương đối hẹp, và (một cách khái niệm) tương đối rộng và trường lượng tử đều là **cùng một phương trình**, chỉ khác nhau ở việc "L là gì" và "không gian cấu hình là gì".

---

# Phần 0 — Tiên đề trung tâm: Nguyên lý tác dụng tối thiểu

## 0.1 Phát biểu

$$S[\,q(t)\,] = \int_{t_1}^{t_2} L(q, \dot q, t)\, dt$$

Trong tất cả các đường đi khả dĩ $q(t)$ nối hai điểm cố định $(t_1, q_1)$ và $(t_2, q_2)$, đường đi *thật* mà hệ thống tuân theo là đường làm $S$ **dừng** (stationary — không nhất thiết là nhỏ nhất, dù tên gọi nói vậy):

$$\delta S = 0$$

## 0.2 Vì sao phát biểu này "sâu" hơn $F = ma$?

$F = ma$ là một mệnh đề *vi phân cục bộ* (local, differential): nó nói bạn "ở thời điểm này, tăng tốc thế nào". Nguyên lý tác dụng tối thiểu là một mệnh đề *toàn cục* (global): nó nói "trong tất cả các lịch sử khả dĩ, lịch sử thật là lịch sử đặc biệt này". Hệ quả quan trọng:

- Nó **không phụ thuộc hệ toạ độ**. Viết lại $q \to Q(q)$ bất kỳ, phương trình chuyển động rút ra từ $\delta S=0$ tự động đúng dạng trong toạ độ mới. Đây là lý do toạ độ suy rộng (generalized coordinates) hoạt động — bạn không cần "quy đổi lực" qua toạ độ cong, bạn chỉ viết lại $L$.
- Nó cho một **công thức universal** để sinh ra phương trình chuyển động cho *bất kỳ* hệ nào, miễn bạn viết đúng $L$ — con lắc, dây, trường điện từ, hạt tương đối tính, hay (sau này) trường lượng tử.
- Nó là cánh cửa trực tiếp vào **định lý Noether** (Phần 2): đối xứng của $S$ ⟺ đại lượng bảo toàn. Đây là lý do momentum, năng lượng, điện tích... đều được bảo toàn — không phải "vì thực nghiệm thấy vậy", mà vì không-thời gian có đối xứng tịnh tiến/quay/dịch thời gian.

## 0.3 Suy ra phương trình Euler-Lagrange (first-principles, không học thuộc)

Cho $q(t) \to q(t) + \epsilon\, \eta(t)$ với $\eta(t_1)=\eta(t_2)=0$ (biến phân giữ cố định hai đầu mút). Khai triển bậc nhất:

$$\delta S = \int_{t_1}^{t_2} \left( \frac{\partial L}{\partial q}\eta + \frac{\partial L}{\partial \dot q}\dot \eta \right) dt$$

Tích phân từng phần số hạng thứ hai (biên triệt tiêu vì $\eta(t_1)=\eta(t_2)=0$):

$$\delta S = \int_{t_1}^{t_2} \left( \frac{\partial L}{\partial q} - \frac{d}{dt}\frac{\partial L}{\partial \dot q} \right) \eta\, dt$$

Vì $\eta(t)$ **tuỳ ý**, biểu thức trong ngoặc phải triệt tiêu tại mọi $t$ (bổ đề cơ bản của phép tính biến phân):

$$\boxed{\frac{d}{dt}\frac{\partial L}{\partial \dot q} - \frac{\partial L}{\partial q} = 0}$$

Đây là **phương trình Euler-Lagrange**. Với $L = \tfrac{1}{2}m\dot x^2 - V(x)$, bạn lập tức có lại $m\ddot x = -\partial V/\partial x = F$. Vậy Newton là **trường hợp riêng**, không phải điểm xuất phát.

## 0.4 Hamilton — đổi biến Legendre

Định nghĩa động lượng suy rộng $p = \partial L/\partial \dot q$, và Hamiltonian:

$$H(q,p) = p\dot q - L$$

(đây là phép biến đổi Legendre — về bản chất toán học giống hệt phép chuyển giữa năng lượng tự do Helmholtz/Gibbs trong nhiệt động lực học — một liên hệ ẩn mà đa số học sinh không để ý). Phương trình chuyển động trở thành hệ đối xứng đẹp:

$$\dot q = \frac{\partial H}{\partial p}, \qquad \dot p = -\frac{\partial H}{\partial q}$$

**Vì sao quan trọng với bạn ngay bây giờ**: $H$ thường chính là *năng lượng* của hệ. Phương trình Hamilton là nền tảng để nhảy sang cơ học lượng tử (Phần 7) qua phép lượng tử hoá chính tắc $p \to -i\hbar \partial_q$, và là công cụ mạnh nhất cho các bài toán HSGQG có ràng buộc, dao động nhỏ, hệ nhiều bậc tự do.

---

# Phần 1 — Cơ học cổ điển: hệ quả, không phải tiên đề

## 1.1 Ba định luật Newton nhìn lại

- **Định luật 1**: hệ quy chiếu quán tính tồn tại — đây thực ra là *định nghĩa* của hệ quy chiếu mà trong đó $L$ không phụ thuộc tường minh vào vị trí tuyệt đối (đối xứng tịnh tiến, xem Noether).
- **Định luật 2**: là phương trình Euler-Lagrange cho $L = T - V$.
- **Định luật 3** (tác dụng-phản tác dụng): là hệ quả của việc $V(\vec r_1, \vec r_2)$ chỉ phụ thuộc $|\vec r_1 - \vec r_2|$ — tức đối xứng tịnh tiến của *hệ hai hạt*, cộng với định lý Noether cho bảo toàn động lượng toàn phần.

## 1.2 Ràng buộc (constraints) — vũ khí bí mật của đề thi khó

Khi có ràng buộc $f(q_1,...,q_n,t)=0$ (vật trên mặt cong, con lắc kép, hệ ròng rọc), bạn có hai lựa chọn:

1. **Giảm bậc tự do**: tham số hoá trực tiếp bằng toạ độ suy rộng độc lập (ví dụ góc $\theta$ cho con lắc) rồi viết $L(\theta,\dot\theta)$. Đây là cách *thanh lịch* nhất và là cách Lagrangian toả sáng so với Newton: bạn không cần tính lực căng dây, lực pháp tuyến gì cả.
2. **Nhân tử Lagrange**: nếu bạn *cần* biết lực ràng buộc (ví dụ lực căng dây để kiểm tra dây có đứt không), thêm $\lambda(t) f(q,t)$ vào $L$ và coi $\lambda$ như một toạ độ thêm.

**Mẹo thi đấu**: 80% bài cơ hệ HSGQG/khu vực khó là vì thí sinh cố dùng $F=ma$ cho hệ có ràng buộc phức tạp (hai vật nối, mặt phẳng nghiêng chuyển động, con lắc trên xe...). Viết $L = T - V$ bằng toạ độ suy rộng tối thiểu, Euler-Lagrange làm phần còn lại — "hiển nhiên hoá" chính là thói quen *luôn thử Lagrangian trước* khi hệ có hơn 1 vật tương tác hoặc có ràng buộc.

## 1.3 Dao động nhỏ & normal modes

Mọi bài "hệ dao động ghép" (lò xo-khối lượng nhiều vật, phân tử) đều có cùng một cấu trúc: khai triển $V$ quanh cực tiểu đến bậc 2:

$$L \approx \frac{1}{2}\sum_{ij} T_{ij}\dot q_i \dot q_j - \frac{1}{2}\sum_{ij} V_{ij} q_i q_j$$

Phương trình chuyển động là bài toán trị riêng tổng quát $V\, \vec a = \omega^2 T\, \vec a$. Mọi "mode riêng", "tần số riêng" trong đề thi — dù là dây đàn, phân tử ba nguyên tử, hay mạch LC ghép — đều chỉ là bài toán trị riêng này được nguỵ trang.

---

# Phần 2 — Định lý Noether: tại sao các định luật bảo toàn *phải* tồn tại

## 2.1 Phát biểu (bằng ngôn ngữ vật lý, không hình thức luận vi phân)

> **Mỗi đối xứng liên tục của tác dụng $S$ (một phép biến đổi làm $S$ bất biến) sinh ra đúng một đại lượng được bảo toàn theo thời gian.**

| Đối xứng của $L$ | Đại lượng bảo toàn |
|---|---|
| Dịch thời gian ($L$ không phụ thuộc tường minh $t$) | Năng lượng $H$ |
| Tịnh tiến không gian ($L$ không đổi khi $\vec r \to \vec r + \vec a$) | Động lượng $\vec p$ |
| Quay không gian ($L$ không đổi khi quay hệ) | Mô-men động lượng $\vec L$ |
| Đổi pha trường (gauge, Phần 5) | Điện tích $Q$ |

## 2.2 Chứng minh ngắn gọn (trường hợp đối xứng nội — minh hoạ ý tưởng)

Giả sử $q \to q + \epsilon K(q)$ là phép biến đổi vô cùng nhỏ làm $\delta L = 0$. Khai triển:

$$0 = \delta L = \frac{\partial L}{\partial q} \epsilon K + \frac{\partial L}{\partial \dot q}\epsilon \dot K = \epsilon\left[\left(\frac{d}{dt}\frac{\partial L}{\partial \dot q}\right) K + \frac{\partial L}{\partial \dot q}\dot K\right] = \epsilon\, \frac{d}{dt}\left(\frac{\partial L}{\partial \dot q} K\right)$$

(bước giữa dùng chính phương trình Euler-Lagrange để thay $\partial L/\partial q$). Vậy:

$$\frac{d}{dt}\left(\underbrace{\frac{\partial L}{\partial \dot q}}_{p}\, K(q)\right) = 0 \quad\Rightarrow\quad Q \equiv p\, K(q) = \text{hằng số}$$

Đây *chính xác* là cơ chế sinh ra bảo toàn động lượng ($K=1$, tịnh tiến), mô-men động lượng ($K = $ vector sinh của phép quay), và tổng quát hơn là mọi định luật bảo toàn bạn từng "học thuộc".

## 2.3 Vì sao điều này khiến đề thi "hiển nhiên"

Khi gặp một bài va chạm/hệ phức tạp, câu hỏi đầu tiên không nên là "dùng công thức nào" mà là: **"hệ này có đối xứng gì?"** Không ma sát theo phương ngang ⟹ động lượng ngang bảo toàn. Lực xuyên tâm ⟹ mô-men động lượng quanh tâm bảo toàn (đây là lý do định luật Kepler II — diện tích quét đều — là hệ quả *tầm thường* của lực hấp dẫn xuyên tâm, không cần tích phân quỹ đạo). Thế năng không phụ thuộc thời gian ⟹ năng lượng bảo toàn. Việc "nhìn ra đối xứng trước khi viết phương trình" là kỹ năng phân biệt học sinh giỏi với học sinh xuất sắc.

---

# Phần 3 — Điện từ học cổ điển: Maxwell từ tác dụng

## 3.1 Bốn phương trình Maxwell (dạng vi phân, đơn vị SI)

$$\nabla \cdot \vec E = \frac{\rho}{\epsilon_0} \qquad (\text{Gauss})$$
$$\nabla \cdot \vec B = 0 \qquad (\text{không có đơn cực từ})$$
$$\nabla \times \vec E = -\frac{\partial \vec B}{\partial t} \qquad (\text{Faraday})$$
$$\nabla \times \vec B = \mu_0 \vec J + \mu_0\epsilon_0 \frac{\partial \vec E}{\partial t} \qquad (\text{Ampère-Maxwell})$$

## 3.2 Tại sao chỉ cần "nhớ" 2 trong 4 phương trình

Hai phương trình thuần (không nguồn) — $\nabla\cdot\vec B = 0$ và $\nabla\times\vec E = -\partial_t\vec B$ — **tự động thoả mãn** nếu bạn định nghĩa thế vector $\vec A$ và thế vô hướng $\phi$:

$$\vec B = \nabla \times \vec A, \qquad \vec E = -\nabla\phi - \frac{\partial \vec A}{\partial t}$$

vì $\nabla\cdot(\nabla\times\vec A)\equiv 0$ và $\nabla\times\nabla\phi \equiv 0$ là đồng nhất thức toán học thuần tuý, không phải vật lý. Đây là lý do bài toán điện từ phức tạp (bức xạ, sóng điện từ trong môi trường) luôn giải nhanh hơn nhiều bằng $(\phi, \vec A)$ thay vì $(\vec E, \vec B)$ trực tiếp.

## 3.3 Hai phương trình còn lại — từ nguyên lý tác dụng tối thiểu (xem Phần 5)

Hai phương trình "có nguồn" (Gauss, Ampère-Maxwell) chính là phương trình Euler-Lagrange của tác dụng điện từ $S = \int(-\tfrac14 F_{\mu\nu}F^{\mu\nu} - A_\mu J^\mu)\,d^4x$ — y hệt công thức "Thanh lịch" mà bạn đã chép ở đầu bài. Nói cách khác: **Maxwell không phải 4 định luật độc lập — nó là 1 tác dụng, cộng với 1 đồng nhất thức hình học**. Chi tiết dạng hiệp biến ở Phần 5.

## 3.4 Sóng điện từ — hệ quả tất yếu, không phải "tiên đề thêm"

Lấy curl của phương trình Faraday, thay Ampère-Maxwell (chân không, $\rho=J=0$):

$$\nabla\times(\nabla\times\vec E) = -\frac{\partial}{\partial t}(\nabla\times\vec B) = -\mu_0\epsilon_0\frac{\partial^2 \vec E}{\partial t^2}$$

Dùng đồng nhất thức $\nabla\times(\nabla\times\vec E) = \nabla(\nabla\cdot\vec E) - \nabla^2\vec E = -\nabla^2 \vec E$ (vì $\nabla\cdot\vec E=0$ trong chân không):

$$\nabla^2 \vec E = \mu_0\epsilon_0 \frac{\partial^2\vec E}{\partial t^2}$$

Đây là phương trình sóng với vận tốc $c = 1/\sqrt{\mu_0\epsilon_0}$. **Ánh sáng là điện từ** không phải vì "người ta đo thấy trùng nhau" — mà vì phương trình sóng rơi ra *tự động* từ 4 phương trình Maxwell, và giá trị $c$ tính từ $\mu_0,\epsilon_0$ (đo bằng thí nghiệm tĩnh điện/tĩnh từ thuần tuý) trùng khớp vận tốc ánh sáng đo quang học. Đây cũng chính là khe hở lịch sử dẫn thẳng tới thuyết tương đối hẹp (Phần 4): nếu $c$ là hằng số xuất hiện trong phương trình trường, mà phương trình trường đúng trong mọi hệ quy chiếu quán tính (tiên đề tương đối), thì $c$ phải bất biến với mọi quan sát viên quán tính.

---

# Phần 4 — Thuyết tương đối hẹp

## 4.1 Hai tiên đề

1. **Nguyên lý tương đối**: mọi định luật vật lý có cùng dạng trong mọi hệ quy chiếu quán tính (tổng quát hoá nguyên lý tương đối Galileo sang *toàn bộ* vật lý, kể cả điện từ học).
2. **Tốc độ ánh sáng bất biến**: $c$ như nhau với mọi quan sát viên quán tính, không phụ thuộc vận tốc nguồn sáng.

Chỉ 2 câu này — kết hợp thuần đại số — bắt buộc phép biến đổi giữa các hệ quy chiếu phải là **Lorentz**, không phải Galileo.

## 4.2 Suy ra biến đổi Lorentz (sơ đồ, không cần nhớ công thức)

Xét xung ánh sáng hình cầu phát từ gốc toạ độ lúc $t=0$. Trong hệ $S$: $x^2+y^2+z^2 = c^2t^2$. Trong hệ $S'$ chuyển động vận tốc $v$ dọc $x$: $x'^2+y'^2+z'^2=c^2t'^2$ (tiên đề 2!). Đại lượng bất biến dưới cả hai là:

$$ds^2 = c^2dt^2 - dx^2-dy^2-dz^2$$

Đây là **khoảng không-thời gian** (spacetime interval) — bất biến Lorentz, đóng vai trò như $ds^2 = dx^2+dy^2$ bất biến dưới phép quay trong không gian Euclid thường. **Tương đối hẹp = hình học Lorentz của không-thời gian 4 chiều**, y hệt lượng giác là hình học của phép quay. Từ $ds^2$ bất biến, bạn suy ra trực tiếp: giãn thời gian $\Delta t = \gamma \Delta\tau$, co độ dài $L = L_0/\gamma$, với $\gamma = 1/\sqrt{1-v^2/c^2}$.

## 4.3 Động lực học tương đối tính — từ tác dụng, không học thuộc công thức

Tác dụng của hạt tự do tương đối tính phải là đại lượng vô hướng Lorentz, tỷ lệ với độ dài thế giới tuyến (world-line) — lựa chọn đơn giản nhất:

$$S = -mc^2\int d\tau = -mc^2\int \sqrt{1-\frac{v^2}{c^2}}\, dt$$

Vậy $L = -mc^2\sqrt{1-v^2/c^2}$. Động lượng:

$$p = \frac{\partial L}{\partial v} = \frac{mv}{\sqrt{1-v^2/c^2}} = \gamma m v$$

Hamiltonian (năng lượng, Phần 0.4):

$$E = pv - L = \gamma mc^2$$

Khai triển Taylor $v \ll c$: $E \approx mc^2 + \tfrac12 mv^2 + ...$ — **động năng Newton xuất hiện như số hạng bậc hai**, còn $mc^2$ là năng lượng nghỉ. Công thức nổi tiếng $E=mc^2$ không phải "định đề thêm vào" — nó là hệ quả tất yếu của việc viết tác dụng bất biến Lorentz đơn giản nhất có thể. Hệ thức bất biến quan trọng nhất cho bài thi:

$$E^2 = (pc)^2 + (mc^2)^2$$

## 4.4 Vì sao phần này làm bài thi "hiển nhiên"

HSGQG/IPhO phần tương đối hẹp gần như luôn quy về: (a) dùng bất biến $ds^2$ hoặc $E^2-(pc)^2$ thay vì biến đổi toạ độ trực tiếp (nhanh hơn 5 lần), (b) nhận ra nghịch lý (cặp song sinh, con tàu-ga tàu) luôn giải được bằng cách *chọn đúng khung quy chiếu có một sự kiện*, dùng bất biến, rồi đổi khung — không bao giờ cần "cãi nhau" về ai đúng ai sai.

---

# Phần 5 — "Thanh lịch": gauge symmetry và tác dụng QED

$$S = \int \left( -\frac{1}{4} F_{\mu\nu} F^{\mu\nu} - A_\mu J^\mu \right) d^4x$$

## 5.1 Giải mã từng ký hiệu

- $F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu$ là **tensor trường điện từ**, gói trọn cả $\vec E$ và $\vec B$ vào một đối tượng hình học 4 chiều (ma trận phản đối xứng 4×4): $F_{0i} = E_i/c$, $F_{ij} = -\epsilon_{ijk}B_k$.
- $F_{\mu\nu}F^{\mu\nu} = 2(B^2 - E^2/c^2)$ — số hạng này đóng vai trò "động năng của trường" — hoàn toàn tương tự $\tfrac12 m\dot x^2$ trong cơ học hạt, chỉ thay $\dot x \to \partial_\mu A_\nu$.
- $A_\mu J^\mu = \phi\rho - \vec A\cdot\vec J$ — số hạng tương tác giữa trường và nguồn (điện tích/dòng).

Biến phân $S$ theo $A_\mu$ (Euler-Lagrange cho *trường*, tức toạ độ suy rộng là $A_\mu(x)$ tại mỗi điểm không gian) cho ra chính xác $\partial_\nu F^{\mu\nu} = \mu_0 J^\mu$ — tức Gauss + Ampère-Maxwell. **Đây là lúc Phần 3.3 khép lại vòng tròn**: toàn bộ điện từ học là Euler-Lagrange của một hàm $L$ duy nhất.

## 5.2 Đối xứng gauge: lý do sâu xa nhất của bảo toàn điện tích

$F_{\mu\nu}$ không đổi dưới phép biến đổi $A_\mu \to A_\mu + \partial_\mu \chi$ với $\chi$ bất kỳ (vì $\partial_\mu\partial_\nu\chi$ đối xứng, trong khi $F_{\mu\nu}$ phản đối xứng). Đây gọi là **đối xứng gauge**. Theo Noether (Phần 2), đối xứng này sinh ra đại lượng bảo toàn: chính là **bảo toàn điện tích**, $\partial_\mu J^\mu = 0$.

**Insight quan trọng nhất của toàn bộ vật lý hiện đại**: lực điện từ *tồn tại* chính xác vì tự nhiên "yêu cầu" pha của hàm sóng electron là một đối xứng gauge cục bộ (gauge lượng tử, Phần 9). Tương tác không phải thứ "thêm vào" lý thuyết — nó là *cái giá phải trả* để giữ một đối xứng cục bộ. Đây là khuôn mẫu sinh ra cả lực mạnh và lực yếu trong Mô hình Chuẩn.

---

# Phần 6 — Vật lý thống kê & Nhiệt động lực học

## 6.1 Tiên đề nền: các vi trạng thái khả dĩ đẳng xác suất

Với một hệ cô lập ở năng lượng $E$ cố định, tiên đề cơ bản của vật lý thống kê là: **mọi vi trạng thái (microstate) tương thích với các ràng buộc vĩ mô có xác suất bằng nhau.** Đây *là* toàn bộ nội dung vật lý — phần còn lại là tổ hợp học (combinatorics).

## 6.2 Entropy Boltzmann — cầu nối vi mô-vĩ mô

$$S = k_B \ln \Omega$$

với $\Omega$ là số vi trạng thái tương thích với trạng thái vĩ mô. Tại sao $\ln$ chứ không phải hàm khác? Vì entropy phải **cộng tính** ($S_{12} = S_1+S_2$ cho hai hệ độc lập) trong khi số vi trạng thái **nhân tính** ($\Omega_{12}=\Omega_1\Omega_2$) — hàm duy nhất biến tích thành tổng là logarithm.

## 6.3 Nhiệt độ — định nghĩa, không phải cảm giác "nóng lạnh"

$$\frac{1}{T} \equiv \frac{\partial S}{\partial E}\bigg|_{V,N}$$

Từ đây, hai hệ tiếp xúc nhiệt sẽ trao đổi năng lượng cho tới khi $\partial S_1/\partial E_1 = \partial S_2/\partial E_2$ — tức **cân bằng nhiệt = cân bằng entropy marginal**, đây là lý do *vì sao* nhiệt chảy từ nóng sang lạnh (định luật 2 nhiệt động lực học là hệ quả thống kê thuần tuý: trạng thái có $\Omega$ lớn hơn *áp đảo số lượng* nên gần như chắc chắn xảy ra — không phải một "định luật" độc lập, mà là xác suất).

## 6.4 Phân bố Boltzmann — suy ra bằng tối đa hoá entropy (nguyên lý biến phân, giống Phần 0!)

Cho hệ tiếp xúc với bể nhiệt ở $T$, cực đại hoá $S = -k_B\sum_i p_i \ln p_i$ (entropy Shannon = entropy Boltzmann cho phân bố không đều) với ràng buộc $\sum p_i = 1$ và $\sum p_i E_i = \langle E\rangle$ cố định, dùng nhân tử Lagrange (đúng kỹ thuật ở Phần 1.2!):

$$p_i \propto e^{-E_i/k_BT}$$

**Đây là liên kết sâu sắc nhất của chương này**: phân bố Boltzmann không phải "công thức vật lý riêng" — nó là *nghiệm của bài toán tối ưu entropy có ràng buộc*, dùng đúng kỹ thuật nhân tử Lagrange bạn đã học ở cơ học. Lý thuyết thông tin (Shannon entropy) và nhiệt động lực học là **cùng một toán học**, khác tên gọi.

## 6.5 Vì sao phần này "hiển nhiên hoá" bài thi

Mọi bài khí lý tưởng/động cơ nhiệt quy về: (1) đếm $\Omega$ hoặc dùng phân bố Boltzmann cho bài vi mô, (2) dùng $dU = TdS - pdV$ (vi phân toàn phần của năng lượng nội tại — hệ quả của nhiệt động lực học định luật 1+2 viết dưới dạng biến phân) cho bài vĩ mô. Entropy *luôn* là đại lượng dẫn đường nhanh nhất cho bài "quá trình bất thuận nghịch" — tính $\Delta S_{universe} \geq 0$ thường nhanh hơn multiple lần so với tính công/nhiệt trực tiếp.

---

# Phần 7 — Cơ học lượng tử

## 7.1 Nguyên lý nền: biên độ xác suất, không phải quỹ đạo

Thay vì hạt có một quỹ đạo $q(t)$ xác định, tự nhiên gán cho **mỗi đường đi khả dĩ** một biên độ phức $e^{iS[q]/\hbar}$ (công thức tích phân đường Feynman), và xác suất quan sát là modulo bình phương của tổng biên độ trên mọi đường. Đây là phần mở rộng lượng tử trực tiếp của Phần 0 — nguyên lý tác dụng tối thiểu **là giới hạn $\hbar \to 0$** của tích phân đường: khi $S \gg \hbar$, các đường đi không dừng ($\delta S \neq 0$) giao thoa triệt tiêu lẫn nhau, chỉ đường có $\delta S = 0$ sống sót — đây chính xác là cách cơ học cổ điển *xuất hiện* từ cơ học lượng tử, không phải hai lý thuyết tách biệt.

## 7.2 Lượng tử hoá chính tắc — con đường thực dụng hơn cho bài thi

Thay cặp $(q,p)$ cổ điển (Phần 0.4) bằng toán tử thoả mãn hệ thức giao hoán:

$$[\hat q, \hat p] = i\hbar$$

Phương trình Hamilton cổ điển $\dot q = \partial H/\partial p,\ \dot p = -\partial H/\partial q$ trở thành **phương trình Schrödinger**:

$$i\hbar \frac{\partial}{\partial t}|\psi\rangle = \hat H |\psi\rangle$$

Trong biểu diễn vị trí, $\hat p = -i\hbar\, \partial/\partial x$, cho dạng quen thuộc:

$$i\hbar\frac{\partial \psi}{\partial t} = -\frac{\hbar^2}{2m}\nabla^2\psi + V(x)\psi$$

## 7.3 Nguyên lý bất định — hệ quả toán học, không phải "giới hạn đo lường"

Vì $[\hat x,\hat p]=i\hbar \neq 0$, hai toán tử không giao hoán ⟹ không có trạng thái riêng chung ⟹ bất đẳng thức Cauchy-Schwarz cho hai toán tử Hermitian không giao hoán *bắt buộc*:

$$\Delta x \,\Delta p \geq \frac{\hbar}{2}$$

Đây không phải tiên đề riêng — nó là **định lý toán học thuần tuý** một khi bạn chấp nhận hệ thức giao hoán chính tắc. Cùng cấu trúc đại số này áp dụng cho mọi cặp biến liên hợp: năng lượng-thời gian, góc-mô-men động lượng góc — và là lý do "tại sao" có độ rộng vạch phổ tự nhiên, hạt nhân phóng xạ có thời gian sống hữu hạn, v.v.

## 7.4 Lượng tử hoá = chu kỳ tác dụng là bội của $h$ (trực giác Bohr-Sommerfeld, cực mạnh cho đề thi)

Với hệ gần cổ điển (số lượng tử lớn), điều kiện lượng tử hoá:

$$\oint p\, dq = n h$$

Công thức này (không cần giải phương trình Schrödinger đầy đủ) suy ra ngay mức năng lượng dao động tử điều hoà, nguyên tử Hydro (mô hình Bohr), hạt trong hộp — và là công cụ **ước lượng nhanh** cực kỳ hiệu quả trong phòng thi khi không có thời gian giải phương trình vi phân đầy đủ.

## 7.5 Spin, thống kê lượng tử, và nguyên lý loại trừ Pauli

Hạt có spin bán nguyên (fermion: electron, proton) có hàm sóng **phản đối xứng** khi hoán đổi hai hạt; spin nguyên (boson: photon) có hàm sóng **đối xứng**. Phản đối xứng ⟹ hai fermion không thể cùng trạng thái lượng tử (nguyên lý Pauli) ⟹ cấu trúc electron trong nguyên tử (bảng tuần hoàn), áp suất suy biến electron (sao lùn trắng), độ cứng của vật chất — tất cả bắt nguồn từ *một* mệnh đề đối xứng hoán vị, kết hợp định lý spin-statistics (hệ quả của lượng tử hoá trường tương đối tính, sâu hơn phạm vi THPT nhưng đáng biết là nó tồn tại).

---

# Phần 8 — Thuyết tương đối rộng (khái niệm + cấu trúc, đủ để "thấy hiển nhiên")

## 8.1 Nguyên lý tương đương — hạt giống của toàn bộ lý thuyết

> Trong một vùng không-thời gian đủ nhỏ, không thí nghiệm nào phân biệt được giữa "đứng yên trong trường hấp dẫn đều" và "gia tốc đều trong không gian không có hấp dẫn".

Hệ quả tức thì: nếu gia tốc (hệ quy chiếu phi quán tính) làm cong đường đi ánh sáng và làm chậm thời gian (điều này suy ra *thuần tuý từ tương đối hẹp* áp dụng cho hệ quy chiếu tăng tốc), thì **hấp dẫn cũng phải làm vậy**. Hấp dẫn không phải một lực theo nghĩa Newton — nó là biểu hiện của **độ cong không-thời gian**.

## 8.2 Từ nguyên lý tác dụng tối thiểu đến phương trình trắc địa

Hạt tự do trong không-thời gian cong vẫn tuân theo "nguyên lý tác dụng tối thiểu" của Phần 0 — chỉ khác là bây giờ cực đại hoá thời gian riêng $\tau$ dọc theo đường trong không-thời gian cong, với mêtric $g_{\mu\nu}$ thay vì mêtric phẳng $\eta_{\mu\nu}$ của Phần 4:

$$S = -mc\int ds, \qquad ds^2 = g_{\mu\nu}dx^\mu dx^\nu$$

Euler-Lagrange cho tác dụng này cho ra **phương trình trắc địa** — quỹ đạo "thẳng nhất có thể" trong không gian cong, đóng vai trò giống hệt đường thẳng trong hình học Euclid. "Quỹ đạo elip của hành tinh quanh Mặt Trời" trong GR không còn là nghiệm của phương trình lực $F=GMm/r^2$ — nó là **đường trắc địa** trong không-thời gian bị uốn cong bởi khối lượng Mặt Trời.

## 8.3 Phương trình trường Einstein (biết để nhận diện, không cần tự suy)

$$G_{\mu\nu} = \frac{8\pi G}{c^4} T_{\mu\nu}$$

Vế trái ($G_{\mu\nu}$, tensor Einstein) mã hoá độ cong hình học của không-thời gian; vế phải ($T_{\mu\nu}$, tensor năng-xung lượng) mã hoá vật chất/năng lượng. Câu nói nổi tiếng của Wheeler tóm gọn chính xác: **"Vật chất bảo không gian phải cong như thế nào; không gian bảo vật chất phải chuyển động ra sao."** Trong giới hạn trường yếu, phương trình này rút gọn về định luật hấp dẫn Newton $\nabla^2\phi = 4\pi G\rho$ — một lần nữa, lý thuyết cũ là **giới hạn** của lý thuyết mới, không bị "xoá bỏ".

---

# Phần 9 — Theory of Everything: khép vòng tròn

## 9.1 Bảng tổng kết — một tác dụng, nhiều $L$

| Lý thuyết | Toạ độ suy rộng | $L$ hoặc nguyên lý |
|---|---|---|
| Cơ học Newton | $q(t)$ hữu hạn chiều | $T - V$ |
| Điện từ Maxwell | trường $A_\mu(x)$ | $-\tfrac14 F_{\mu\nu}F^{\mu\nu} - A_\mu J^\mu$ |
| Tương đối hẹp | world-line trong Minkowski | $-mc^2\sqrt{1-v^2/c^2}$ |
| Tương đối rộng | world-line trong $(M,g_{\mu\nu})$ | $-mc\int ds$, cộng $S_{Einstein-Hilbert}=\int R\sqrt{-g}\,d^4x$ |
| Cơ học lượng tử | biên độ trên *mọi* đường | $e^{iS/\hbar}$, tổng trên mọi $q(t)$ |
| Nhiệt động/thống kê | phân bố xác suất $p_i$ | cực đại $S=-k_B\sum p_i\ln p_i$ với ràng buộc |

Mọi dòng trong bảng này là **cùng một phép biến phân**: cho một phiếm hàm, tìm điểm dừng, áp ràng buộc bằng nhân tử Lagrange nếu cần. Đây là lý do thực sự khiến "mọi thứ trông hiển nhiên" một khi bạn nội tâm hoá nó — bạn không còn học 6 môn con riêng biệt, bạn học **một kỹ thuật toán học** áp dụng 6 lần.

## 9.2 Vì sao chưa có "Theory of Everything" thật sự

Vấn đề mở lớn nhất của vật lý hiện đại: $S_{Einstein-Hilbert}$ (hình học, Phần 8) và cơ học lượng tử (Phần 7) **không hoà hợp trực tiếp**. Lượng tử hoá các trường gauge (điện từ, hạt nhân mạnh/yếu — "Mô hình Chuẩn") hoạt động tốt bằng kỹ thuật lý thuyết trường lượng tử (quantum field theory — về bản chất là áp dụng tích phân đường của Phần 7.1 cho trường $A_\mu(x)$ thay vì hạt điểm $q(t)$). Nhưng áp dụng kỹ thuật tương tự cho $g_{\mu\nu}$ (hấp dẫn) cho ra các đại lượng vô hạn không khử được (non-renormalizable) — đây là vấn đề trung tâm mà lý thuyết dây, lực hấp dẫn lượng tử vòng (loop quantum gravity)... cố giải quyết, và **chưa có lời giải được kiểm chứng thực nghiệm.** Nói thẳng: không ai trên Trái Đất hiện nay — kể cả các nhà vật lý giỏi nhất — có câu trả lời "hiển nhiên" cho câu hỏi này. Đó là ranh giới thật của hiểu biết nhân loại, và biết chính xác ranh giới nằm ở đâu cũng là một phần của "hiểu sâu sắc".

## 9.3 Trả lời câu hỏi "giấu tên" một cách trung thực

Nếu bạn nội tâm hoá được **(a)** nguyên lý tác dụng tối thiểu và kỹ thuật biến phân, **(b)** định lý Noether (đối xứng ⟹ bảo toàn), **(c)** cách mỗi ngành chỉ là chọn $L$/ràng buộc khác nhau cho cùng một cỗ máy toán học — thì phần lớn đề thi HSGQG, kể cả phần "nhìn lạ", sẽ quy về việc bạn **nhận diện đúng cấu trúc ẩn** rồi áp dụng công cụ quen thuộc. Đề IPhO khó không nằm ở kiến thức ngoài khung này — chúng nằm ở (i) mô hình hoá vật lý thực tế thành toán học sạch, và (ii) tốc độ + độ chính xác tính toán dưới áp lực. Khung này giải quyết triệt để nhóm (i); nhóm (ii) chỉ có được qua **luyện đề** — không có đường tắt nào, kể cả first principles, thay thế được việc giải hàng trăm bài thật.

---

# Lộ trình luyện tập đề nghị (để biến "bản đồ" thành "phản xạ")

1. **Tuần 1-3**: Tự suy lại Euler-Lagrange, Noether, và giải lại 10 bài cơ học lớp 10-12 *chỉ* bằng Lagrangian — kể cả bài bạn đã biết đáp số bằng $F=ma$.
2. **Tuần 4-5**: Viết lại 4 phương trình Maxwell dưới dạng thế $(\phi,\vec A)$, giải bài toán sóng điện từ, bức xạ lưỡng cực đơn giản.
3. **Tuần 6**: Tự suy $E=\gamma mc^2$, $E^2=(pc)^2+(mc^2)^2$ từ tác dụng; giải lại mọi bài "nghịch lý song sinh" bằng bất biến $ds^2$.
4. **Tuần 7-8**: Giải bài phân bố Boltzmann bằng nhân tử Lagrange từ đầu (không tra công thức); áp dụng cho khí lý tưởng, bức xạ vật đen (Planck).
5. **Tuần 9-10**: Lượng tử hoá Bohr-Sommerfeld cho 5 hệ khác nhau; giải phương trình Schrödinger cho hố thế, dao động tử điều hoà.
6. **Song song, mọi tuần**: 3-5 đề thi thật (Olympic 30/4, HSGQG các năm, IPhO shortlist) — **không phải để học thêm kiến thức**, mà để luyện phản xạ "nhìn bài → nhận diện cấu trúc ẩn → chọn công cụ trong bảng Phần 9.1".

---

*Tài liệu này là bộ khung (scaffold), không phải giáo trình đầy đủ — mỗi Phần ở trên có thể mở rộng thành một cuốn sách riêng (và đã có: Landau & Lifshitz cho cơ học/trường, Griffiths cho điện từ/lượng tử, Schutz cho GR, Kittel cho thống kê). Giá trị thật của nó là **sợi chỉ nối liền** — khi bạn thấy "À, bài này chỉ là Noether cho đối xứng tịnh tiến" hay "đây chính là nhân tử Lagrange của Phần 1.2 áp lại cho entropy", đó là lúc Vật Lý ngừng là một danh sách công thức và trở thành một ngôn ngữ bạn nói trôi chảy.*
