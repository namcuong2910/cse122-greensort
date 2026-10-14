# BẢN PHÂN TÍCH BỐ CỤC & THIẾT KẾ FIGMA CHO TRANG: RESIDENT WASTE GUIDE (GREENSORT)
Học phần: Phát triển ứng dụng Web cơ bản – CSE122 (Kiểm tra giữa kỳ)
Đề tài: BTL-05 GreenSort – Phân loại rác & Điều phối thu gom thông minh
Trang thực hiện: `resident-waste-guide.html` (Hướng dẫn & Phân loại rác thông minh)

---

## 1. MỤC TIÊU & ĐỐI TƯỢNG NGƯỜI DÙNG
- **Đối tượng:** Người dân / Hộ gia đình trong khu vực đô thị / sinh viên khu ký túc xá.
- **Mục tiêu:** Tra cứu nhanh cách phân loại rác (Hữu cơ, Tái chế, Nguy hại, Vô cơ khác), tìm kiếm theo tên hoặc danh mục, và sử dụng công cụ mô phỏng AI (AI-1: Waste Classifier) để quét/phân tích vật phẩm rác, đưa ra hướng dẫn xử lý và gợi ý điểm thu gom phù hợp.

---

## 2. HƯỚNG DẪN IMPORT TRỰC TIẾP LÊN FIGMA
Để có file Figma thật và link Figma nộp bài theo tiêu chuẩn 1.5 điểm:
1. Bạn mở [Figma](https://www.figma.com/) trên trình duyệt hoặc app Figma desktop.
2. Cài đặt plugin miễn phí: **"html.to.design"** (hoặc "HTML to Figma").
3. Chạy trang web `index.html` của dự án (hoặc mở trực tiếp file `index.html` bằng trình duyệt).
4. Dùng plugin `html.to.design` nhập URL localhost hoặc kéo thả trực tiếp để plugin tự sinh toàn bộ Frame, Auto Layout, Color Tokens, Typography và Component trên Figma chuẩn 100% khớp với code!
5. Bạn có thể nhấn nút **Share** trên Figma -> "Anyone with the link can view" -> Copy link để đưa vào `README.md`.

---

## 3. DESIGN SYSTEM (HỆ THỐNG THIẾT KẾ CHO FIGMA)

### 3.1. Bảng màu (Color Palette)
- **Primary Color (Xanh lá sinh thái):** `#16A34A` (Tailwind Green 600 / Eco Green)
- **Primary Dark:** `#15803D`
- **Primary Light / Background:** `#F0FDF4` (Green 50)
- **Secondary (Xanh biển tái chế):** `#0284C7` (Sky Blue)
- **Warning (Vàng rác nguy hại/pin):** `#D97706` (Amber)
- **Danger (Đỏ cảnh báo/rác thải y tế):** `#DC2626`
- **Neutral Dark (Văn bản chính):** `#1E293B` (Slate 800)
- **Neutral Light (Nền thẻ card):** `#FFFFFF`
- **Border / Muted:** `#E2E8F0` / `#64748B`

### 3.2. Typography
- **Font chữ:** `'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif`
- **H1 (Hero Heading):** 36px / Bold / Line-height 1.25
- **H2 (Section Title):** 28px / SemiBold
- **H3 (Card Title):** 18px / SemiBold
- **Body Text:** 15px / Regular / Line-height 1.6
- **Badge / Small:** 12px / Medium

### 3.3. Khoảng cách & Hiệu ứng (Spacing & Elevation)
- **Grid Container:** Desktop 1200px (12 cột, Gutter 24px)
- **Mobile Container:** 375px (1 cột, Margin 16px)
- **Corner Radius:** Card 16px (`rounded-3` / `rounded-4`), Button 10px / 999px (Pill)
- **Shadow:** `box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.05), 0 8px 10px -6px rgba(0, 0, 0, 0.05)`

---

## 4. WIREFRAME & BỐ CỤC FIGMA (DESKTOP & MOBILE)

### A. DESKTOP FRAME (1440px x Auto)
```text
┌──────────────────────────────────────────────────────────────────────────────┐
│ [HEADER / NAVBAR] (Sticky-top, Glassmorphism / White)                        │
│  Logo GreenSort (🌿)  | Trang chủ | Phân loại rác | Điểm thu gom | Đặt lịch |  │
│  [ Ô tìm kiếm nhanh ]                         [ Đổi vai trò: Người dân ▾ ]   │
├──────────────────────────────────────────────────────────────────────────────┤
│ [HERO SECTION] (Nền gradient xanh nhạt)                                      │
│  H1: Hướng Dẫn Phân Loại Rác Thông Minh & Chuẩn Xác                          │
│  Sub: Chung tay bảo vệ môi trường, giảm thiểu rác chôn lấp với trợ lý AI     │
│  [ Input tìm kiếm rác: "Nhập vỏ chai, pin cũ, thức ăn thừa..." ] [ Tìm kiếm ]│
│  Badge gợi ý: [Pin cũ] [Túi nilon] [Vỏ lon] [Hộp sữa] [Thức ăn thừa]        │
├──────────────────────────────────────────────────────────────────────────────┤
│ [FEATURED: AI-1 WASTE CLASSIFIER - TRỢ LÝ PHÂN LOẠI AI]                      │
│  ┌── Khung tương tác AI (Card nổi bật có viền gradient) ──────────────────┐  │
│  │ Bước 1: Nhập tên rác hoặc tải ảnh mẫu (Túi bóng, pin, vỏ sò, bóng đèn)  │  │
│  │ Bước 2: Nút [Phân tích bằng AI ✨]                                      │  │
│  │ Bước 3: Trạng thái: Skeleton / Loading Bar                              │  │
│  │ Bước 4: Khối kết quả (Độ tin cậy 98%, Thùng rác tương ứng, Hướng dẫn)   │  │
│  │ Bước 5: Thao tác người dùng: [Chấp nhận] [Chỉnh sửa] [Gửi báo cáo lỗi] │  │
│  └─────────────────────────────────────────────────────────────────────────┘  │
├──────────────────────────────────────────────────────────────────────────────┤
│ [SECTION: 4 DANH MỤC RÁC QUY CHUẨN] (4 Cards dạng lưới)                      │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐         │
│  │ 🍏 HỮU CƠ    │ │ ♻️ TÁI CHẾ   │ │ ⚠️ NGUY HẠI  │ │ 🗑️ VÔ CƠ KHÁC│         │
│  │ Thùng Nâu    │ │ Thùng Xanh   │ │ Thùng Cam    │ │ Thùng Đen    │         │
│  │ 12 vật phẩm  │ │ 18 vật phẩm  │ │ 8 vật phẩm   │ │ 10 vật phẩm  │         │
│  └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘         │
├──────────────────────────────────────────────────────────────────────────────┤
│ [SECTION: TRA CỨU & DANH SÁCH CHI TIẾT CÓ BỘ LỌC + MODAL]                    │
│  [Tabs lọc: Tất cả | Rác hữu cơ | Tái chế | Nguy hại | Vô cơ khác]           │
│  [Thẻ rác 1]   [Thẻ rác 2]   [Thẻ rác 3]   [Thẻ rác 4]   (Grid 4 cột)        │
│  (Mỗi thẻ có icon, tên, loại rác, cách xử lý, nút "Xem chi tiết" mở Modal)   │
├──────────────────────────────────────────────────────────────────────────────┤
│ [SECTION: HƯỚNG DẪN 3 BƯỚC ĐÚNG QUY CÁCH (Infographic)]                      │
│  [1. Phân loại tại nguồn] ──> [2. Làm sạch & ép gọn] ──> [3. Bỏ đúng thùng]  │
├──────────────────────────────────────────────────────────────────────────────┤
│ [FOOTER] (Nền xám tối/xanh rêu nhạt)                                         │
│  Thông tin đề tài CSE122 | Nhóm BTL-05 GreenSort | Bản quyền sinh viên TLU   │
└──────────────────────────────────────────────────────────────────────────────┘
```

### B. MOBILE FRAME (375px x Auto)
- Header thu gọn với nút **Toggle Hamburger (☰)** mở Offcanvas trượt cạnh trái.
- Thanh tìm kiếm Hero chuyển full-width 100%.
- AI Classifier xếp 1 cột dọc: Ô input -> Nút bấm -> Khối kết quả thích ứng.
- Lưới 4 danh mục rác: chuyển thành 2 hàng x 2 cột (hoặc trượt ngang).
- Danh sách thẻ tra cứu: xếp chồng 1 cột (`col-12`), chạm vuốt mượt mà.
- Modal chi tiết hiển thị toàn màn hình trên điện thoại (`modal-fullscreen-sm-down`).

---

## 5. TỔ CHỨC CÁC LAYER TRÊN FIGMA (DÀNH CHO SINH VIÊN BÁO CÁO)
Khi quay video OBS mở Figma, bạn hãy trình bày cây Layer sau:
1. **Frame 1 - Desktop (1440w):**
   - `Navbar`: Brand, Nav-links, Actions.
   - `Hero`: Header text, Search bar, Quick badges.
   - `AI-Classifier-Widget`: Input group, Processing state, Result card, Explanation, Action buttons.
   - `Category-Overview`: 4 Categories cards (Flex/Grid).
   - `Waste-Directory`: Filter tabs, Search result counter, Waste card grid, Empty state.
   - `Step-Guide`: 3 steps with icons.
   - `Footer`: Project metadata, Copyright.
2. **Frame 2 - Mobile (375w):**
   - `Mobile-Header`: Hamburger + Brand.
   - `Offcanvas-Menu`: Slide-in navigation.
   - `Mobile-Body`: Single-column stacked layout.
3. **Components & Modals:**
   - `Card-Waste-Item` (Component có Hover variant)
   - `Modal-Detail`: Dialog phóng to thông tin rác & điểm tái chế liên kết.
