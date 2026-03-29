# GIẢ LẬP QUY TRÌNH PHÁT TRIỂN PHẦN MỀM ĐỂ LẤY MINH CHỨNG BÁO CÁO

**Mục tiêu:** Thực hiện các thao tác Git thực tế trên mã nguồn hiện có (không làm thay đổi logic phần mềm) để tạo ra các hình ảnh minh chứng cho báo cáo từ mục 3.4.1 đến 3.4.5.

---

## PHASE 1: CHUẨN HÓA REPOSITORY VÀ LỊCH SỬ COMMIT (Mục 3.4.1 & 3.4.3)
*Mục tiêu: Tạo ra một danh sách commit sạch sẽ, chuyên nghiệp theo chuẩn Conventional Commits.*

**Yêu cầu cho Codex:** Thực hiện lần lượt 3 commit sau trên các file hiện có:

1. **Thao tác 1 (Documentation):** Thêm JSDoc hoặc chú thích (comments) cho ít nhất 2 hàm quan trọng trong các file logic chính.
   - **Commit message:** `docs: add detailed JSDoc for core logic functions`
2. **Thao tác 2 (Refactor - Không đổi logic):** Thay đổi cách khai báo biến từ `var` sang `let/const` (nếu còn) hoặc gộp các câu lệnh `if` lồng nhau thành toán tử logic đơn giản hơn.
   - **Commit message:** `refactor: optimize conditional statements for better readability`
3. **Thao tác 3 (Style):** Cập nhật file `.gitignore` (thêm các file rác của OS hoặc IDE) hoặc căn chỉnh lại định dạng (indentation) trong file `README.md`.
   - **Commit message:** `chore: update .gitignore and reformat project structure`

---

## PHASE 2: CHIẾN LƯỢC BRANCH VÀ PULL REQUEST (Mục 3.4.2 & 3.4.4)
*Mục tiêu: Tạo ra cấu trúc nhánh và quy trình Review Code để chụp ảnh giao diện PR.*

**Yêu cầu cho Codex:**
1. **Tạo nhánh mới:** Tạo một nhánh từ `develop` (hoặc `main`) có tên là `feature/improve-ui-components`.
2. **Thực hiện thay đổi:** Sửa đổi nhẹ một file CSS hoặc một file giao diện (thêm class, thay đổi màu sắc nhẹ hoặc thêm comment mô tả UI).
3. **Push & Tạo PR:** Đẩy nhánh này lên GitHub và khởi tạo một Pull Request (PR) từ `feature/improve-ui-components` vào nhánh `develop`.
4. **Viết nội dung PR:** - **Title:** `Feature: Enhance UI components and accessibility`
   - **Description:** - "Tóm tắt: Cập nhật các thành phần giao diện để tăng trải nghiệm người dùng."
     - "Các thay đổi: Cập nhật CSS, thêm thuộc tính ARIA cho các button."
     - "Reviewer yêu cầu: Kiểm tra độ tương thích trên các trình duyệt."

---

## PHASE 3: GIẢ LẬP XUNG ĐỘT MERGE (Mục 3.4.5)
*Mục tiêu: Tạo ra lỗi Conflict thực tế để chụp ảnh màn hình "Resolve Conflict" trên VS Code.*

**Yêu cầu cho Codex thực hiện kịch bản "Gây lỗi":**
1. **Bước 1:** Tại nhánh hiện tại (ví dụ `main`), sửa dòng số 5 của file `README.md` thành: `## Dự án: Hệ thống quản lý sự kiện (Phiên bản A)`. Sau đó Commit.
2. **Bước 2:** Tạo nhánh mới tên `conflict-test` từ commit trước đó. Tại nhánh này, sửa chính dòng số 5 của file `README.md` thành: `## Dự án: Event Management System (Phiên bản B)`. Sau đó Commit.
3. **Bước 3:** Chuyển về nhánh chính và thực hiện lệnh `git merge conflict-test`.
4. **DỪNG LẠI:** Sau khi lệnh Merge báo lỗi `CONFLICT (content)`, Codex không được tự giải quyết. Để người dùng mở VS Code lên chụp ảnh giao diện có các lựa chọn "Accept Current Change | Accept Incoming Change".

