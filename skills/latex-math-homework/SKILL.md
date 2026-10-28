---
name: latex-math-homework
description: >-
  Use this skill whenever creating, editing, solving, formatting, or compiling math homework, exercises, or assignments in LaTeX/XeLaTeX (e.g., Linear Algebra DSTT, Calculus GT1A, Discrete Math, or HCMUS coursework).
---

# LaTeX Math Homework & Problem Solving Skill

Kỹ năng giải và trình bày bài tập Toán / Đại số tuyến tính / Giải tích bằng LaTeX (XeLaTeX) theo chuẩn của sinh viên Hồ Xuân Phúc (HCMUS - 26TTH2).

## 1. QUY TẮC CỐT LÕI: TUYỆT ĐỐI KHÔNG TỰ Ý VIẾT BOX ĐỀ
- **KHÔNG dùng box đề:** Khi làm BTVN hay giải bài tập, **TUYỆT ĐỐI KHÔNG dùng box đề** (`\begin{baitap}...\end{baitap}`) và **KHÔNG chép lại đề bài**.
- Các khối `baitap`, `dinhly`, `canhbao` chỉ tồn tại trong preamble để dự phòng, **tuyệt đối KHÔNG tự ý chèn vào nội dung bài tập** trừ khi người dùng yêu cầu đích danh.
- **Cấu trúc chuẩn:** Chỉ ghi 1 dòng ngắn gọn tiêu đề câu/bài (ví dụ `\noindent\textbf{Bài 1.}` hoặc `\textbf{\large Bài 1.}` `\textbf{a)}`), sau đó vào thẳng `\begin{loigiai}...\end{loigiai}`:
  ```latex
  \noindent\textbf{Bài 1.}
  \begin{loigiai}
      % Trực tiếp làm lời giải ở đây, không có box đề
  \end{loigiai}
  ```

## 2. Phong cách giải toán: Ngắn gọn, súc tích, tối đa hóa ký hiệu ("Spam ký hiệu")
- **Bám sát phong cách nháp toán học:**
  - Viết trực diện, cô đọng, cắt bỏ tối đa lời văn giải thích dông dài.
  - Sử dụng chuỗi suy luận bằng ký hiệu logic: $\to$, $\Rightarrow$, $\Leftrightarrow$, $\in$, $\forall$.
  - Biến đổi ma trận: ghi rõ từng phép biến đổi dòng sơ cấp trên mũi tên, ví dụ:
    \[
        \xrightarrow[\substack{d_3 \to d_3 - d_1}]{d_2 \to d_2 - 2d_1}
    \]
  - Hệ phương trình: dùng môi trường chuẩn (`cases`, `alignat*`), ma trận bổ sung $\tilde{A}$, ghép ma trận $[A \mid I]$.
  - Biện luận tham số: dùng ngoặc vuông 1 bên $\left[\begin{array}{l}...\end{array}\right.$ thay vì viết câu điều kiện dài dòng.
  - Bỏ đi những thứ không cần thiết: KHÔNG dùng text box / khung viền bao quanh đáp án (bỏ `\boxed{...}`), không dùng các box trang trí thừa thãi.
  - Viết ngắn gọn, cô đọng tối đa: tối giản lời văn, bám sát bản nháp, đi thẳng vào các bước suy luận và đáp số.

## 3. Tự động hoàn thiện phần bỏ trống / ngầm định
- Nếu đề bài hoặc ảnh nháp để lửng (dấu ba chấm `...`, chừa chỗ trống ẩn, chưa xét hết trường hợp, chưa kết luận):
  - Agent **tự động tính toán chuẩn xác** và bổ sung trọn vẹn toàn bộ lời giải.
  - Tuyệt đối không để lại dấu ba chấm hay câu chữ dang dở.

## 4. Biên dịch và kiểm tra
- Biên dịch bằng lệnh: `xelatex <file>.tex`.
- Đảm bảo biên dịch thành công không lỗi nghiêm trọng và xuất ra file PDF hoàn chỉnh.
