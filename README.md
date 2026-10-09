# SWD392 - Group 5 - Model-View-Controller (MVC) Architecture

> **Môn học:** SWD392 — Software Architecture and Design  
> **Giảng viên hướng dẫn:** Nguyễn Mạnh Cường  
> **Nhóm thực hiện:** Group 5 (Nguyễn Đức Mạnh, Nguyễn Đức Thủy, Nguyễn Tiến Dũng, Nguyễn Văn Thành, Đỗ Việt Tiến)

Dự án slide thuyết trình tương tác trực tiếp (Interactive Single-Page Slide Engine) đóng gói trong 1 file duy nhất `index.html`. Không cần server backend, không phụ thuộc thư viện bên ngoài (Zero npm/node_modules), tự chứa toàn bộ CSS, JavaScript và vector SVG.

---

## 🚀 Hướng dẫn Deploy

### Cách 1: Deploy lên Cloudflare Pages (Khuyên dùng - Cực nhanh)

#### Phương án 1A: Kéo thả trực tiếp (Direct Upload - Không cần Git)
1. Đăng nhập [dash.cloudflare.com](https://dash.cloudflare.com/) → Chọn mục **Workers & Pages**.
2. Bấm **Create application** → Chọn tab **Pages** → Bấm **Upload assets**.
3. Đặt tên dự án (ví dụ: `swd392-mvc-group5`).
4. Kéo thả thư mục chứa file `index.html` vào khung upload (hoặc nén zip rồi kéo thả).
5. Bấm **Deploy site**. Trang web sẽ online ngay sau 5 giây với HTTPS miễn phí (ví dụ: `https://swd392-mvc-group5.pages.dev`).

#### Phương án 1B: Kết nối GitHub Repo
1. Đẩy mã nguồn lên GitHub repository cá nhân.
2. Tại Cloudflare Pages, chọn **Connect to Git** → Chọn repo vừa tạo.
3. Cấu hình Build settings:
   - **Framework preset:** None
   - **Build command:** để trống
   - **Build output directory:** `/` (hoặc để trống root)
4. Bấm **Save and Deploy**. Mỗi khi `git push` code sẽ tự động cập nhật.

---

### Cách 2: Deploy lên GitHub Pages

1. Khởi tạo Git và đẩy mã nguồn lên GitHub:
   ```bash
   git init
   git add .
   git commit -m "feat: init MVC presentation slide engine"
   git branch -M main
   git remote add origin https://github.com/<username>/<repo-name>.git
   git push -u origin main
   ```
2. Mở repository trên trình duyệt GitHub → Chuyển sang tab **Settings**.
3. Ở menu bên trái, chọn mục **Pages** (dưới nhóm *Code and automation*).
4. Tại phần **Build and deployment**:
   - **Source:** chọn `Deploy from a branch`.
   - **Branch:** chọn nhánh `main` và thư mục `/ (root)`.
5. Bấm **Save**. Sau khoảng 1–2 phút, GitHub sẽ cấp URL dạng:  
   `https://<username>.github.io/<repo-name>/`

---

### Chạy thử nghiệm Local (Offline)
- Mở trực tiếp file `index.html` bằng bất kỳ trình duyệt nào (Chrome, Edge, Firefox, Safari).
- Hoặc dùng tiện ích **Live Server** trong VS Code / chạy lệnh `python -m http.server 3000`.

---

## ⌨️ Phím tắt & Tính năng Slide Engine

| Phím tắt | Chức năng |
| :--- | :--- |
| `→` / `Space` / `PageDown` | Chuyển sang slide tiếp theo |
| `←` / `PageUp` | Quay lại slide trước |
| `Home` / `End` | Về slide đầu tiên / slide cuối cùng |
| `G` | Bật / tắt chế độ xem lưới (Grid Overview 18 slides) |
| `T` | Chuyển đổi giao diện Dark Theme / Light Theme |
| `F` | Bật / tắt chế độ toàn màn hình (Fullscreen) |
| `?` hoặc `H` | Mở bảng hướng dẫn phím tắt |
| `Esc` | Đóng menu Grid hoặc Help Modal |
| `Lăn chuột` / `Vuốt chạm` | Lăn chuột (debounce 350ms) hoặc vuốt trái/phải trên màn hình cảm ứng |

---

## 📑 Danh mục 18 Slides

1. **Slide 1:** Bìa thuyết trình (SWD392 · Group 5 · MVC Architecture)
2. **Slide 2:** Thông tin Giảng viên hướng dẫn & 5 Thành viên nhóm
3. **Slide 3:** Agenda — Bản đồ nội dung bài báo cáo
4. **Slide 4:** Khởi nguồn & Bối cảnh lịch sử (Trygve Reenskaug 1979 & Vấn đề Spaghetti code)
5. **Slide 5:** Triết lý cốt lõi (Separation of Concerns & Single Responsibility Principle)
6. **Slide 6:** Thành phần 1: Model — Quản lý dữ liệu, Domain entities & Nghiệp vụ lõi
7. **Slide 7:** Thành phần 2: View — Giao diện hiển thị, Template & Passive View
8. **Slide 8:** Thành phần 3: Controller — Tiếp nhận Request, Điều phối & Điều hướng
9. **Slide 9:** Sơ đồ tương tác 3 chiều tổng thể (Interactive SVG Vector)
10. **Slide 10:** Luồng xử lý Request Web MVC (Mô hình Model 2: DispatcherServlet → Controller → Model → View)
11. **Slide 11:** Desktop MVC (Active Model / Observer) vs Web MVC (Passive Model / Stateless)
12. **Slide 12:** Ma trận so sánh kiến trúc tương đương: MVC vs MVP vs MVVM
13. **Slide 13:** Ứng dụng thực tế Enterprise (Spring Boot MVC & ASP.NET Core MVC)
14. **Slide 14:** Anti-Patterns nguy hiểm (Fat Controller, Anemic Model, View DB Leaks)
15. **Slide 15:** Best Practices & Chuẩn hóa (Skinny Controller, Rich Model, DTOs, ViewModels, DI)
16. **Slide 16:** Đánh giá thuộc tính chất lượng kiến trúc (Testability, Scalability, Modifiability)
17. **Slide 17:** Tổng kết & Key Takeaways
18. **Slide 18:** Kết bài (Kết thúc bài báo cáo & Cảm ơn)
