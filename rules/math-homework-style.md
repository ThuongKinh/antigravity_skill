# Math & LaTeX Homework Solution Style Rules (Quy Tắc Giải Bài Tập Toán)

Áp dụng cho mọi tác vụ giải bài tập Toán / Đại số tuyến tính / LaTeX khi người dùng gửi đề, gửi ảnh nháp hoặc yêu cầu làm bài / hoàn thiện bài tập.

## 0. QUY TẮC CỐT LÕI: TUYỆT ĐỐI KHÔNG TỰ Ý VIẾT BOX ĐỀ
- **KHÔNG dùng box đề:** Khi làm BTVN hay giải bài tập, **TUYỆT ĐỐI KHÔNG dùng box đề** (`\begin{baitap}...`) và **KHÔNG chép lại đề bài**.
- Các định nghĩa môi trường box (`baitap`, `dinhly`, `canhbao`) vẫn giữ nguyên sẵn trong preamble của template, nhưng **chỉ dùng khi người dùng yêu cầu cụ thể**.
- **Định dạng chuẩn:** Chỉ cần 1 dòng ngắn gọn ghi tên bài, câu (ví dụ: `\noindent\textbf{Bài 1.}` hoặc `\textbf{\large Bài 1.}` `\textbf{a)}`), sau đó vào thẳng `\begin{loigiai}...\end{loigiai}`.

## 1. Phong cách giải: Ngắn gọn, súc tích, tối đa hóa ký hiệu ("Spam ký hiệu")
- **Bám sát phong cách viết trong ảnh nháp của người dùng:**
  - Viết trực diện, cô đọng, tối giản tối đa lời văn giải thích dông dài.
  - Ưu tiên sử dụng ký hiệu toán học và phép suy luận logic: $\to$, $\Rightarrow$, $\Leftrightarrow$, $\in$, $\forall$, v.v.
  - Với biến đổi ma trận: ghi rõ từng phép biến đổi dòng sơ cấp trên mũi tên (ví dụ: $\xrightarrow[\substack{d_3 \to d_3 - d_1}]{d_2 \to d_2 - 2d_1}$, $\xrightarrow{d_3 \to d_3 + d_2}$).
  - Với hệ phương trình: dùng các môi trường toán chuẩn như `cases`, `alignat*`, ma trận bổ sung $\tilde{A}$ dạng `\left(\begin{array}{ccc|c}...\end{array}\right)`, ghép ma trận đơn vị $[A \mid I]$.

## 2. Tự động hoàn thiện các phần bỏ trống / ngầm định
- Khi người dùng gửi ảnh nháp có các phần chừa trống hoặc bỏ lửng (ví dụ: ghi dấu ba chấm `...`, chừa trống ẩn $x, y, z$, chưa viết chi tiết TH1, TH2, vô nghiệm / vô số nghiệm / nghiệm duy nhất, hoặc chưa ghi kết luận):
  - Agent **tự động tính toán chuẩn xác** và bổ sung hoàn thiện toàn bộ lời giải.
  - Các phần tự bổ sung (biện luận, giải hệ bậc thang thế ngược, kết luận, ma trận nghịch đảo, v.v.) phải tuân thủ nghiêm ngặt **Tiêu chí 1** (viết ngắn gọn, ký hiệu hóa, dùng công thức toán rõ ràng, đóng khung kết quả cuối `\boxed{...}`).
  - Tuyệt đối không để lại dấu ba chấm hay câu chữ dang dở.

## 3. Đồng nhất với ngữ cảnh file hiện tại (Đặc biệt trong Session mới)
- Trước khi thêm bài giải mới vào file `.tex`, Agent phải chủ động đọc lại các câu/bài đã giải trước đó trong file:
  - Đồng nhất cấu trúc môi trường: dùng `\begin{loigiai}...\end{loigiai}`, cách đánh số đề mục (`\textbf{\large Bài X.}`, `\textbf{a)}`, khoảng cách `\vspace{10pt}`).
  - Đồng nhất ký hiệu và phong cách trình bày: ký hiệu ma trận bổ sung ($\tilde{A}$), kiểu ma trận, ký hiệu dòng sơ cấp ($d_i$), hàm hạng ($r(A)$ hay $\rank(A)$).
  - Đồng nhất định dạng kết quả cuối: đóng khung bằng `\boxed{...}`.

## 4. Biện luận tham số: Ngắn gọn, dùng ngoặc vuông $\left[\begin{array}{l}...\end{array}\right.$ thay vì viết văn dài dòng
- Tuyệt đối tránh viết văn dông dài dạng: *"Nếu ... hoặc ...: hàng ... của vế trái là dòng 0, suy ra..."*.
- Dùng trực tiếp ký hiệu toán học và chuỗi suy luận logic:
  - Dùng ngoặc vuông 1 bên $\left[\begin{array}{l} m = a \\ m = b \end{array}\right.$ (tuyển logic "hoặc") kết hợp mũi tên suy luận:
    \[
        \left[\begin{array}{l} m = -1 \\ m = -2 \end{array}\right. \implies d_3 = 0 \implies r(A) = 2 < n = 3 \text{ (suy biến / không khả nghịch).}
    \]
  - Trường hợp khả nghịch:
    \[
        m \notin \{-1, -2\} \implies r(A) = 3 = n \text{ (khả nghịch).}
    \]
  - Cắt bỏ mọi câu chữ giải thích rườm rà khi ghép ma trận và chuyển bước khử Gauss sang Jordan.

## 5. Trình bày bài tập về nhà (BTVN)
- **TUYỆT ĐỐI KHÔNG DÙNG BOX ĐỀ:** Khi làm BTVN, **KHÔNG dùng box đề** (`\begin{baitap}...`) và **KHÔNG chép lại đề bài**.
- Các định nghĩa môi trường box (`baitap`, `dinhly`, `canhbao`) vẫn giữ nguyên sẵn trong preamble của template, nhưng chỉ dùng khi người dùng yêu cầu rõ ràng.
- **Định dạng chuẩn:** Chỉ cần 1 dòng ngắn gọn ghi tên bài, câu (ví dụ: `\noindent\textbf{Bài 2.}` hoặc `\textbf{\large Bài 1.}` `\textbf{a)}`), sau đó vào thẳng `\begin{loigiai}...\end{loigiai}`.
