# Hệ số bất định và "Bài toán con" Tổng quát - Method of undetermined coefficients

Wikipedia : https://en.wikipedia.org/wiki/Method_of_undetermined_coefficients

Gemini : https://share.gemini.google/VS3sLYpxbGkG

DeepSeek : https://chat.deepseek.com/share/lw74x9i8ewklwcws8p

**Big Question:**

Coi: f_1(x) là biểu thức ta có. f_2(x) là biểu thức ta cần. f_1'(x) là dạng đa thức "chuẩn" của f_1(x). f_2'(x) là dạng đa thức "chuẩn" của f_2(x).

=> Miễn là việc ta có thể thực hiện biến đổi đại số từ f_1 và f_2 sang f_1' và f_2' thành công thì: f_1 sẽ sang được f_2 thành công.

**I. Problem Statement.**

Cho một biểu thức f(x) có thể biến đổi về dạng đa thức "chuẩn" và thỏa f(x) -> f_dt(x) và f(x) = f_dt(x).
g(x) là biểu thức chúng ta mong muốn, nhưng ta chưa có sẵn. g_dt(x) là dạng đa thức "chuẩn" và thỏa g(x) -> g_dt(x) và g(x) = g_dt(x).

+) Cần xây dựng/sử dụng các phép biến đổi đại số mạnh cho f(x) -> f_dt(x) và g(x) -> g_dt(x). Ngay cả khi f(x), g(x) không phải đa thức, nhưng các phép biến đổi đại số này đủ mạnh để làm việc đó.

+) Còn bước f_dt = g_dt thì dùng phương pháp hệ số bất định (Wikipedia : https://en.wikipedia.org/wiki/Method_of_undetermined_coefficients)

=> Làm đúng cách, ta sẽ có phương pháp biến đổi đại số cực mạnh khi cần chuyển từ f(x) đang có sang g(x) với điều kiện đã biết rõ dạng g(x) tường minh, và 1 số điều kiện nền tảng nhưng thường đáp ứng được khác.
