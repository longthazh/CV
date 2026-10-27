# Báo cáo kiểm thử — Portfolio CV

**Ngày kiểm thử:** 27/10/2026  
**Đối tượng:** Website portfolio tĩnh trong `index.html`  
**Môi trường:** Microsoft Edge (Chromium), mở trang từ tệp cục bộ; desktop 1440 px và mobile 390 × 844 px.

## Tổng quan kết quả

| Tiêu chí | Kết quả | Tóm tắt |
|---|---|---|
| Tính đúng đắn | Đạt có điều kiện | Nội dung, điều hướng neo, ảnh và xác thực cơ bản của biểu mẫu hoạt động; liên kết dự án vẫn là placeholder. |
| UI/UX | Cần cải thiện | Bố cục desktop hiển thị tốt; ảnh mobile ghi nhận nội dung hero bị cắt ở mép phải. |
| Khả năng vận hành - xử lý lỗi | Đạt một phần | Trang tĩnh mở được; trình duyệt kiểm tra trường bắt buộc và email, nhưng không có xử lý/gửi biểu mẫu phía máy chủ. |
| Bảo mật | Đạt trong phạm vi website tĩnh | Không thấy mã JavaScript, backend hoặc thư viện bên ngoài; chưa thực hiện kiểm thử xâm nhập hay đánh giá cấu hình máy chủ. |
| Chất lượng mã nguồn | Đạt cơ bản | HTML có cấu trúc ngữ nghĩa, CSS tách riêng; chưa có bộ kiểm thử tự động và còn liên kết mẫu. |
| Khả năng triển khai | Đạt cho nội dung tĩnh; Docker chưa xác minh | Trang và tài nguyên mở được từ tệp cục bộ; hướng dẫn Nginx/Docker có trong README nhưng môi trường kiểm thử không có Docker CLI. |

## 1. Tính đúng đắn

- Mở trang thành công; các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ hiện diện.
- Bấm điều hướng **Kỹ năng** đưa URL tới `#skills`.
- Cả 5 ảnh (ảnh đại diện và 4 ảnh dự án) tải thành công, không có ảnh lỗi.
- Biểu mẫu từ chối trạng thái để trống và email sai định dạng bằng kiểm tra HTML gốc của trình duyệt; các trường hợp nhập đủ và email hợp lệ vượt qua kiểm tra này.
- **Chưa đạt đầy đủ:** bốn liên kết “Xem chi tiết” trong thẻ dự án hiện dùng `href="#"`, chưa dẫn tới dự án thực tế.

**Minh chứng:** [Ảnh desktop](screenshots/01-desktop.png), [ảnh mobile](screenshots/02-mobile.png).

## 2. UI/UX

- Ở desktop 1440 px, phần dự án hiển thị dạng lưới 3 cột; thứ bậc nội dung và các vùng chính nhìn thấy được trong ảnh toàn trang.
- Ở mobile 390 × 844 px, ảnh chụp ghi nhận phần mô tả hero và ảnh đại diện bị cắt ở mép phải. Cần điều chỉnh cách co giãn các phần tử trong hero và kiểm thử lại trên thiết bị nhỏ; `overflow-x: hidden` có thể che thanh cuộn ngang mà không giải quyết phần nội dung bị khuất.
- Nội dung giao diện trộn tiếng Việt và tiếng Anh (đặc biệt phần Liên hệ); nên thống nhất ngôn ngữ trước khi phát hành.

**Minh chứng:** [Ảnh desktop](screenshots/01-desktop.png), [ảnh mobile thể hiện vấn đề](screenshots/02-mobile.png).

## 3. Khả năng vận hành - xử lý lỗi

- Trang tĩnh mở được trực tiếp trong Edge và tải các tài nguyên tương đối.
- Các trường `required` và `type="email"` cung cấp kiểm tra dữ liệu cơ bản ở phía trình duyệt.
- Biểu mẫu chưa có backend/dịch vụ tiếp nhận, không gửi thông tin liên hệ và không có trạng thái thành công hoặc lỗi từ dịch vụ. Vì vậy, thao tác gửi biểu mẫu thực tế chưa được xác nhận.
- Không có ứng dụng máy chủ hoặc luồng xử lý lỗi ứng dụng để kiểm thử trong phiên bản tĩnh này.

**Minh chứng:** Ảnh desktop có phần Liên hệ và biểu mẫu; các ảnh chụp nằm trong [thư mục screenshots](screenshots/).

## 4. Bảo mật

- Trong phạm vi các tệp được kiểm tra, website là nội dung HTML/CSS tĩnh, không có mã JavaScript, backend, thư viện bên ngoài hoặc nơi lưu trữ dữ liệu biểu mẫu.
- Kiểm tra email của trình duyệt chỉ hỗ trợ trải nghiệm nhập liệu, không thay thế xác thực phía máy chủ nếu sau này tích hợp dịch vụ nhận dữ liệu.
- Chưa thực hiện pentest, quét lỗ hổng, kiểm thử tải hoặc rà soát cấu hình HTTP/TLS/security headers của máy chủ triển khai. Các cấu hình này phụ thuộc môi trường hosting.

**Minh chứng:** [Ảnh desktop](screenshots/01-desktop.png) ghi nhận trang và biểu mẫu ở trạng thái tĩnh.

## 5. Chất lượng mã nguồn

- Có các vùng HTML ngữ nghĩa như `header`, `nav`, `main`, `section`, `article` và `footer`; CSS được tách thành `assets/css/styles.css`.
- Các trường biểu mẫu có nhãn; ảnh nội dung có văn bản thay thế. CSS có breakpoint responsive, kiểu `focus-visible` và hỗ trợ `prefers-reduced-motion`.
- Chưa có kiểm thử tự động, quy trình lint/validate HTML hoặc CI trong dự án.
- Các `href="#"` của dự án là phần cần hoàn thiện để tránh điều hướng không có đích hữu ích.

**Minh chứng:** [Ảnh desktop](screenshots/01-desktop.png) và [ảnh mobile](screenshots/02-mobile.png).

## 6. Khả năng triển khai

- Xác nhận trang có thể mở trực tiếp từ `index.html`; các ảnh và CSS cục bộ được tải cùng trang.
- README có hướng dẫn phục vụ nội dung tĩnh bằng Nginx/Docker. Không chạy thử container trong lần kiểm thử này vì môi trường hiện tại không có Docker CLI; do đó chưa xác nhận cấu hình container hoặc triển khai production.
- Không có bước build hay dependency cài đặt theo mô tả dự án. Cần thay liên kết mẫu, xử lý vấn đề mobile và quyết định cách tiếp nhận biểu mẫu trước khi phát hành chính thức.

**Minh chứng:** [Ảnh desktop toàn trang](screenshots/01-desktop.png) và [ảnh mobile](screenshots/02-mobile.png).

## Kết luận

Website đáp ứng mức trình bày portfolio tĩnh cơ bản. Chưa nên coi là hoàn tất phát hành cho người dùng thực tế cho đến khi sửa lỗi hiển thị mobile, thay các liên kết dự án mẫu và xác định rõ biểu mẫu liên hệ sẽ được tích hợp hay bỏ chức năng gửi.