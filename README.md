# Portfolio CV - Bùi Thành Long

Website portfolio cá nhân giới thiệu Bùi Thành Long, Frontend Developer. Dự án được xây dựng bằng HTML và CSS thuần, hướng đến giao diện gọn gàng, dễ đọc và tương thích với nhiều kích thước màn hình.

## Mục lục

- [Mô tả dự án](#mô-tả-dự-án)
- [Chức năng](#chức-năng)
- [Công nghệ sử dụng](#công-nghệ-sử-dụng)
- [Yêu cầu môi trường](#yêu-cầu-môi-trường)
- [Cài đặt](#cài-đặt)
- [Cấu hình và tùy chỉnh](#cấu-hình-và-tùy-chỉnh)
- [Chạy thử](#chạy-thử)
- [Chạy bằng Docker](#chạy-bằng-docker)
- [Thông tin liên hệ](#thông-tin-liên-hệ)

## Mô tả dự án

Đây là website portfolio dạng tĩnh, trình bày thông tin cá nhân, kỹ năng và một số dự án mẫu. Giao diện được thiết kế theo hướng mobile-first; bố cục tự điều chỉnh trên điện thoại, máy tính bảng và máy tính để bàn.

## Chức năng

- Điều hướng nhanh đến các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Giới thiệu chủ sở hữu portfolio và vai trò Frontend Developer.
- Hiển thị các kỹ năng như HTML5, CSS3, Flexbox, Grid, JavaScript, responsive design, Git/GitHub và Figma.
- Trình bày các thẻ dự án mẫu: Landing Page, Todo List, Weather Dashboard và Blog cá nhân.
- Hiển thị ảnh đại diện và ảnh minh họa dự án từ thư mục `assets/img/`.
- Bố cục responsive, hiệu ứng điều hướng và hỗ trợ `focus-visible` cũng như tùy chọn giảm chuyển động của hệ điều hành.
- Có biểu mẫu liên hệ gồm email và tên.

> **Lưu ý:** Biểu mẫu hiện chỉ có giao diện HTML; dự án chưa có backend, dịch vụ gửi email hoặc mã JavaScript xử lý gửi biểu mẫu. Dữ liệu chưa được gửi đến email hay dịch vụ tiếp nhận nào.

## Công nghệ sử dụng

- **HTML5:** cấu trúc và nội dung trang.
- **CSS3:** tạo kiểu, responsive design, Flexbox, CSS Grid và media query.
- **Ảnh JPEG:** ảnh đại diện và ảnh minh họa trong `assets/img/`.
- **Nginx (tùy chọn):** phục vụ trang tĩnh khi chạy bằng Docker.

Dự án hiện không sử dụng framework, thư viện bên ngoài, trình quản lý gói hoặc quy trình biên dịch.

## Yêu cầu môi trường

### Để xem trang

- Trình duyệt hiện đại có hỗ trợ HTML5 và CSS3, chẳng hạn Chrome, Edge, Firefox hoặc Safari.
- Không cần cài Node.js, npm hay máy chủ ứng dụng.

### Để chạy máy chủ phát triển

- Windows: Python 3 (lệnh `py` hoặc `python`) nếu muốn dùng máy chủ tích hợp của Python.
- macOS/Linux: Python 3 (lệnh `python3`) nếu muốn dùng máy chủ tích hợp của Python.
- Có thể thay Python bằng tiện ích mở rộng **Live Server** trong Visual Studio Code.

### Để chạy bằng Docker

- Docker Desktop trên Windows/macOS hoặc Docker Engine trên Linux.
- Docker CLI có thể truy cập từ Terminal/PowerShell.

## Cài đặt

1. Tải hoặc clone mã nguồn dự án về máy.
2. Nếu tải tệp ZIP, giải nén toàn bộ dự án; cần giữ nguyên cấu trúc thư mục, đặc biệt là `assets/css/` và `assets/img/`.
3. Mở thư mục dự án trong Visual Studio Code hoặc trình quản lý tệp.

Không cần cài đặt dependencies.

## Cấu hình và tùy chỉnh

- **Nội dung trang:** chỉnh sửa `index.html`.
- **Kiểu dáng, màu sắc và breakpoint responsive:** chỉnh sửa `assets/css/styles.css`.
- **Ảnh đại diện và ảnh dự án:** thay ảnh trong `assets/img/` hoặc cập nhật đường dẫn `src` trong `index.html`. Giữ các đường dẫn tương đối và tên tệp khớp chính xác.
- **Thông tin liên hệ:** cập nhật phần liên hệ trong `index.html` và cung cấp email/mạng xã hội thật nếu muốn người xem liên lạc. Trong phiên bản hiện tại, phần này là biểu mẫu giao diện và chưa có tích hợp gửi tin nhắn.
- **Liên kết dự án:** thay các liên kết mẫu `href="#"` bằng URL dự án thật.

Không có tệp cấu hình môi trường (`.env`) hoặc cấu hình build riêng.

## Chạy thử

### Windows

**Cách nhanh nhất:** mở thư mục dự án, nhấp đúp `index.html` để xem bằng trình duyệt.

**Dùng Python:** mở PowerShell tại thư mục dự án và chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có nhưng đã cài Python, thử:

```powershell
python -m http.server 8000
```

### macOS

Mở Terminal tại thư mục dự án. Có thể mở `index.html` trực tiếp bằng trình duyệt, hoặc chạy máy chủ thử nghiệm:

```bash
python3 -m http.server 8000
```

### Linux

Mở Terminal tại thư mục dự án. Có thể mở `index.html` trực tiếp bằng trình duyệt, hoặc chạy máy chủ thử nghiệm:

```bash
python3 -m http.server 8000
```

### Truy cập trang

Sau khi máy chủ khởi động, mở địa chỉ sau trong trình duyệt:

```text
http://localhost:8000
```

Để dừng máy chủ, nhấn `Ctrl+C` trong cửa sổ Terminal/PowerShell đang chạy lệnh.

> Máy chủ Python tích hợp chỉ phù hợp để xem/thử nghiệm cục bộ, không nên dùng làm máy chủ triển khai production.

## Chạy bằng Docker

Docker sử dụng image Nginx để phục vụ trang tĩnh. Các lệnh dưới đây chỉ mount `index.html` và thư mục `assets`, không mount toàn bộ thư mục dự án.

### Windows (PowerShell)

Chạy tại thư mục dự án:

```powershell
docker run --rm --name portfolio -p 8080:80 -v "${PWD}\index.html:/usr/share/nginx/html/index.html:ro" -v "${PWD}\assets:/usr/share/nginx/html/assets:ro" nginx:alpine
```

### Windows (Command Prompt)

Chạy tại thư mục dự án:

```cmd
docker run --rm --name portfolio -p 8080:80 -v "%cd%\index.html:/usr/share/nginx/html/index.html:ro" -v "%cd%\assets:/usr/share/nginx/html/assets:ro" nginx:alpine
```

### macOS và Linux

Chạy tại thư mục dự án:

```bash
docker run --rm --name portfolio -p 8080:80 -v "$(pwd)/index.html:/usr/share/nginx/html/index.html:ro" -v "$(pwd)/assets:/usr/share/nginx/html/assets:ro" nginx:alpine
```

Mở trang tại <http://localhost:8080>. Nhấn `Ctrl+C` trong terminal đang chạy container để dừng và xóa container.

Nếu cổng `8080` đã được sử dụng, thay `8080` ở phía trái của `-p` bằng một cổng trống khác, ví dụ `8081:80`, rồi truy cập cổng tương ứng.

## Thông tin liên hệ

- **Tên:** Bùi Thành Long
- **Vai trò:** Frontend Developer
- **Email và mạng xã hội:** Chưa được cung cấp trong mã nguồn. Vui lòng bổ sung thông tin liên hệ thực tế tại đây và trong phần liên hệ của `index.html` trước khi phát hành website.