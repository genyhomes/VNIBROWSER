# VNIBrowser — Trình Duyệt Ẩn Danh & Chống Phát Hiện (Anti-Detect Browser Suite)

<img src="https://raw.githubusercontent.com/genyhomes/VNIBROWSER/refs/heads/main/VNIBrowser2.png">

> **VNIBrowser** là giải pháp trình duyệt chống phát hiện (*Anti-Detect Browser*) thế hệ mới, được tối ưu hóa chuyên sâu từ mã nguồn C++ của Chromium. Ứng dụng cung cấp môi trường duyệt web ẩn danh tuyệt đối, giúp quản lý hàng trăm tài khoản độc lập, vượt qua mọi hệ thống kiểm tra và bảo vệ khắt khe nhất hiện nay (Cloudflare Turnstile, DataDome, reCAPTCHA v3, Akamai, GeeTest, Kasada).

Download: https://forumviet.com/threads/vnibrowser-anti-detect-browser-chay-truc-tiep-tren-may-tinh-khong-gioi-han-profiles-mien-phi.6151/
---

## 🌟 Tính Năng Nổi Bật

### 1. Công Nghệ Vá Lõi C++ Độc Quyền (Source-Level C++ Patches)
Khác biệt hoàn toàn so với các công cụ thông thường chỉ can thiệp bằng JavaScript injection (rất dễ bị phát hiện qua phân tích nguyên mẫu prototype, thuộc tính getter hay timing attacks), VNIBrowser can thiệp trực tiếp từ cấp độ mã nguồn Chromium:
- **Canvas & WebGL Fingerprint**: Ngẫu nhiên hóa nhiễu ảnh và mô phỏng card đồ họa (NVIDIA GeForce RTX, Intel Iris/UHD, Apple Silicon Metal, ARM Mali, Qualcomm Adreno) với tính nhất quán phần cứng 100%.
- **WebRTC Zero-Leak**: Cơ chế cô lập UDP độc quyền, ngăn chặn triệt để nguy cơ lộ địa chỉ IP thật của máy chủ kể cả khi chạy qua Proxy.
- **AudioContext & Font Metrics**: Giả lập thông số âm thanh và tập font hệ thống chuẩn xác theo từng hệ điều hành.
- **Client Hints & Navigator**: Đồng bộ hoàn toàn giữa chuỗi User-Agent, kiến trúc CPU, số luồng vi xử lý, dung lượng RAM và thông số đồ họa.

### 2. Hỗ Trợ Đa Hệ Điều Hành (Windows, macOS, Linux, Android)
- Tùy biến dấu vân tay theo các hệ điều hành: **Windows 10/11**, **macOS**, **Linux** và đặc biệt là **Android Mobile / Tablet**.
- Tự động điều chỉnh độ phân giải màn hình chuẩn di động (Galaxy Standard, Android Mobile, Android Tablet) và mô phỏng cảm ứng màn hình trung thực.

### 3. Mô Phỏng Hành Vi Người Thật (Humanize Engine)
- Tích hợp thuật toán di chuyển chuột theo đường cong tự nhiên (Bézier curves).
- Ngẫu nhiên hóa tốc độ gõ phím, độ trễ nhấn nút và quán tính cuộn trang.
- Hỗ trợ các cấu hình: **Mặc định** (*Balanced*) và **Cẩn trọng** (*Careful - dành cho antibot khó tính*).

### 4. Quản Lý Profile Chuyên Nghiệp & Độc Lập
- Mỗi profile sở hữu môi trường lưu trữ riêng biệt (cookies, cache, localStorage, IndexedDB, extensions).
- **Thư mục dữ liệu định danh theo tên Profile**: Toàn bộ dữ liệu phiên được lưu trữ trong `./vnibrowser_data/profiles/<Tên_Profile>/`, giúp người dùng dễ dàng theo dõi, sao lưu hoặc di chuyển dữ liệu.
- Phân nhóm (Group/Tag), tìm kiếm nhanh theo từ khóa, lọc theo trạng thái *Đang chạy* hoặc *Đã dừng*.
- **Thao tác hàng loạt**: Khởi động đồng loạt, tắt hàng loạt hoặc xóa hàng loạt chỉ với một cú nhấp chuột.

### 5. Trình Quản Lý Cookie Đa Năng (Cookie Manager)
- **Nhập Cookie (Import)**: Hỗ trợ đa định dạng:
  - JSON Array (`[{"name": "...", "value": "...", "domain": "..."}]`)
  - Định dạng J2TEAM (`{"url": "...", "cookies": [...]}`)
  - Netscape format (`cookies.txt`)
  - Chuỗi Base64
  - Chuỗi Raw Header (`c_user=...; xs=...; datr=...`)
- **Xuất Cookie (Export)**: Xuất ra JSON chuẩn (tương thích Cookie-Editor, EditThisCookie, Playwright), Netscape hoặc Header string.
- **Kiểm tra Cookie (Cookie Inspector)**: Xem danh sách chi tiết các cookie đang lưu trữ trong profile, lọc theo domain, xóa từng mục hoặc xóa sạch chỉ trong 1 giây.

### 6. Cập Nhật Nhân Chromium Tự Động (One-Click Core Update)
- Tích hợp kiểm tra phiên bản mới nhất từ kho lưu trữ Chromium Stealth.
- Tải về và cài đặt trực tiếp từ giao diện bảng điều khiển với thanh tiến trình trực quan.
- Chế độ cài đặt cưỡng bức (*Force Reinstall*) khi cần làm mới nhân trình duyệt.

### 7. Hỗ Trợ Đa Ngôn Ngữ (i18n)
- **Tiếng Anh (English)**: Thiết lập làm ngôn ngữ mặc định của ứng dụng.
- **Tiếng Việt (Vietnamese)**: Bản địa hóa giao diện trực quan, rõ ràng, chuẩn thuật ngữ chuyên ngành.
- Chuyển đổi ngôn ngữ tức thì (*Live Switch*) ngay trong mục **Cài đặt ứng dụng**.

### 8. Trang Khởi Động Mặc Định
- Trang kiểm tra IP và độ ẩn danh mặc định: **`https://ipfighter.com`** (thay đổi được dễ dàng trong Cài đặt).

---

## 🚀 Đóng Gói Thực Thi & Tính Di Động (Portable)

VNIBrowser được thiết kế dạng **100% Portable (Chạy Ngay Không Cần Cài Đặt)**:
- **Tệp thực thi `VNIBrowser.exe`**: 
  - Khởi chạy trực tiếp, giao diện hiện đại với biểu tượng ứng dụng tích hợp.
  - Tự động chạy ngầm máy chủ và mở Bảng điều khiển trên trình duyệt.
  - Thu nhỏ vào khay hệ thống (**System Tray**) với menu tiện ích: *Mở Bảng điều khiển, Dừng tất cả profile, Mở thư mục dữ liệu, Thoát hoàn toàn*.
  - Kiểm soát đơn phiên (Single-Instance): Tránh khởi động trùng lặp máy chủ nếu người dùng mở nhiều lần.
- **Đóng gói sẵn Python Runtime**: Không cần máy tính phải cài đặt Python hay bất kỳ thư viện ngoài nào.
- **Gói nén di động `dist/VNIBrowser-Portable.zip`**: Sẵn sàng sao chép sang bất kỳ máy tính Windows nào để sử dụng ngay lập tức.

---

## 💻 Hướng Dẫn Sử Dụng Nhanh

### 1. Khởi động ứng dụng
1. Nhấp đúp vào tệp **`VNIBrowser.exe`** (hoặc `Start_VNIBrowser.bat`).
2. Trình duyệt mặc định của bạn sẽ tự động mở trang điều khiển: `http://127.0.0.1:7977`.
3. Biểu tượng VNIBrowser sẽ xuất hiện dưới khay hệ thống (System Tray).

### 2. Tạo Profile trình duyệt mới
1. Nhấp vào nút **`+ New Profile`** (hoặc **`+ Tạo Profile Mới`**).
2. Nhập **Tên Profile**, chọn **Nhóm** (nếu có).
3. **Cấu hình Proxy** (nếu cần): Tích chọn *Enable Proxy*, dán chuỗi proxy nhanh dạng `IP:Port:User:Pass` và nhấp *Check Proxy*.
4. **Cấu hình Vân tay (Fingerprint)**: Chọn Hệ điều hành (Windows, macOS, Linux hoặc Android), hoặc nhấp **`🎲 Randomize Fingerprint`** để hệ thống tạo ngẫu nhiên toàn bộ thông số phần cứng.
5. Nhấp **`Save Profile`** để lưu.

### 3. Khởi chạy và Quản lý Profile
- Nhấp nút **`Start`** (Mở) trên dòng Profile để khởi chạy trình duyệt ẩn danh.
- Khi cần tắt, nhấp **`Stop`** (Dừng).
- Nhấp biểu tượng 🍪 để nhập hoặc xuất cookie cho profile đó.

### 4. Thay đổi cài đặt
- Nhấp vào biểu tượng bánh răng **Settings** trên thanh tiêu đề:
  - Chọn ngôn ngữ: **English** hoặc **Tiếng Việt**.
  - Đổi trang khởi động mặc định (mặc định: `https://ipfighter.com`).
  - Kiểm tra và cập nhật nhân Chromium Stealth mới nhất.

---

## 📁 Cấu Trúc Thư Mục

```text
VNIBrowser-Portable/
├── VNIBrowser.exe               # Tệp thực thi chính (Chạy ứng dụng 1-click)
├── Start_VNIBrowser.bat         # Trình khởi động qua Batch script (dự phòng)
├── Start_VNIBrowser_Silent.vbs  # Trình khởi động chạy ẩn qua VBScript
├── app.py                       # Máy chủ ứng dụng & API điều khiển
├── app_icon.ico                 # Biểu tượng ứng dụng chính thức
├── core/                        # Nhân Chromium Stealth đã được vá C++
├── runtime/                     # Môi trường nhúng Python 3.13 Portable
├── static/                      # Giao diện Web Dashboard (HTML5, CSS3, JS ES6)
├── manager/                     # Module điều khiển (Profile, Proxy, Update, Settings)
├── vnibrowser_data/             # Thư mục lưu trữ cấu hình & dữ liệu người dùng
│   ├── profiles/                # Dữ liệu tách biệt của từng Profile
│   └── settings.json            # Cài đặt toàn hệ thống (Ngôn ngữ, Startup URL,...)
└── GIOI_THIEU_VNIBROWSER.md     # Tài liệu giới thiệu & hướng dẫn chi tiết
```

---

## 🔒 Bản Quyền & Bảo Mật

- **VNIBrowser** hoàn toàn độc lập, bảo mật dữ liệu cục bộ trên máy của bạn (Local Storage First).
- Không gửi dữ liệu tài khoản, mật khẩu hay cookie của người dùng lên bất kỳ máy chủ bên thứ ba nào.
