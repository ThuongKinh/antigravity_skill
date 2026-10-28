# LaTeX Project Workflow & Permission Rules

Quy tắc phân loại và cơ chế xin quyền / tự động phê duyệt (Check-in & Approval) cho mọi tác vụ liên quan đến LaTeX.

## 1. Xác định loại dự án LaTeX

Khi bắt đầu làm việc trong một workspace / thư mục dự án LaTeX mới hoặc khi chưa rõ mục đích của tài liệu:
- **Hỏi người dùng** (nếu ngữ cảnh chưa rõ ràng) xem dự án LaTeX này thuộc loại nào:
  1. **Bài tập về nhà (BTVN) / Bài tập thực hành trên lớp**.
  2. **Nghiên cứu khoa học (NCKH) / Dự án cá nhân lớn**.
- **Nhận diện ngữ cảnh:** Nếu ngữ cảnh đã rõ ràng (ví dụ: các file `BT*.tex`, `Buoi*.tex`, bài tập các môn học ĐSTT, Giải tích, Toán rời rạc...), tự động phân loại là **BTVN** mà không cần hỏi lại gây phiền.

---

## 2. Quy tắc hành xử theo loại dự án

### A. Đối với Bài tập về nhà (BTVN) / Bài tập trường lớp
- **Chế độ:** `Auto-allow` / **Tự động bypass check-in**.
- **Quy tắc box đề:** **TUYỆT ĐỐI KHÔNG tự ý viết box đề (`\begin{baitap}...`) hay chép lại đề bài.** Chỉ ghi số thứ tự bài (ví dụ `\noindent\textbf{Bài 1.}`) rồi vào thẳng lời giải (`\begin{loigiai}...\end{loigiai}`).
- **Hành vi của Agent:**
  - Thoải mái, chủ động thực hiện trực tiếp: giải toán, gõ code LaTeX, tối ưu phép biến đổi ma trận/hệ phương trình, sửa file `.tex`, chạy lệnh biên dịch (`xelatex`, `pdflatex`, v.v.).
  - **KHÔNG** dừng lại xin phép ở các bước nhỏ, không bắt người dùng duyệt kế hoạch vụn vặt.
  - Biên dịch PDF, kiểm tra không lỗi, sau đó tóm tắt ngắn gọn các bước chính và kết quả.

### B. Đối với Nghiên cứu khoa học (NCKH) / Dự án cá nhân lớn
- **Chế độ:** `Strict Approval & Batch Execution` (Kiểm duyệt nghiêm ngặt & Làm một lần).
- **Hành vi của Agent:**
  - **BẮT BUỘC xin cấp quyền:** Không được tự ý chỉnh sửa file hoặc cấu trúc dự án khi chưa có sự đồng ý của người dùng.
  - **Lập danh sách việc định làm chi tiết (Checklist):** Nêu rõ từng mục dự định thay đổi (file nào, thêm/sửa/xóa nội dung gì, cấu trúc ra sao) để người dùng kiểm tra từng cái một.
  - **Thực hiện một lần (Batch execution):** Sau khi người dùng đã duyệt và chốt toàn bộ kế hoạch, tiến hành thực hiện trọn vẹn trong một lượt, tránh sửa đổi lắt nhắt làm xáo trộn dự án lớn.
