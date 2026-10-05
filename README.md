# iTaxViewer Web

Ứng dụng HTML chạy cục bộ trên trình duyệt để đọc hóa đơn điện tử/XML hồ sơ thuế, hiển thị dữ liệu dễ đọc và xuất hồ sơ sang PDF.

## Mở ứng dụng

Mở trực tiếp file:

```text
iTaxViewer-Web.html
```

Hoặc kéo file `iTaxViewer-Web.html` vào Chrome, Microsoft Edge hoặc trình duyệt Chromium tương thích.

Ứng dụng không cần máy chủ web và không cần cài đặt thư viện bổ sung để đọc XML.

## Tính năng chính

- Đọc một hoặc nhiều file XML.
- Hiển thị hóa đơn điện tử theo bố cục dễ đọc.
- Hỗ trợ xem tờ khai và báo cáo tài chính theo định dạng được ứng dụng hỗ trợ.
- Tìm kiếm dữ liệu trong phần tóm tắt và nội dung hồ sơ.
- Highlight từ khóa tìm kiếm.
- Lọc hồ sơ theo loại tài liệu.
- Chuyển đổi giao diện sáng/tối.
- Hỗ trợ tiếng Việt và tiếng Anh.
- Xuất hồ sơ sang PDF khổ A4.
- Khôi phục XML được nhúng trong PDF do ứng dụng xuất.
- Xử lý dữ liệu cục bộ trong trình duyệt.

## Tra cứu hóa đơn điện tử

Khi đọc hóa đơn, ứng dụng có thể nhận diện mã tra cứu và hiển thị nút mở trang tra cứu tương ứng.

Các nhà cung cấp được hỗ trợ:

- Petrolimex
- Sapo Invoice
- Viettel Vinvoice
- CellphoneS

Ứng dụng hỗ trợ các dạng mã phổ biến như:

- `MaTraCuu`
- `MaTimKiem`
- `Fkey` hoặc `FKey`
- `LookupCode`
- `InvoiceLookupCode`
- `TransactionID`
- `Mã số bí mật`
- `Mã TC`
- `Mã nhận hóa đơn`
- Mã được lưu trong thuộc tính `DLHDon@Id` khi không có mã tra cứu cụ thể hơn

Việc nhận diện nhà cung cấp có thể dựa trên:

- Tên, địa chỉ, email và MST bên bán.
- Nội dung `TTKhac`.
- `MSTTCGP`.
- Nhãn và cấu trúc mã tra cứu riêng của từng hệ thống.

## Extension autofill tùy chọn

Thư mục `petrolimex-autofill` chứa browser extension hỗ trợ tự điền mã tra cứu trên website của các nhà cung cấp.

Extension có thể:

- Đọc mã được truyền trong URL fragment từ iTaxViewer.
- Tự điền mã tra cứu trên Petrolimex, Sapo, Viettel và CellphoneS.
- Tự điền MST bên bán trên Viettel khi có dữ liệu.
- Dán mã từ clipboard sau khi người dùng bấm nút tương ứng.
- Làm nổi bật và đưa focus tới ô CAPTCHA.

CAPTCHA không được tự động giải hoặc vượt qua. Người dùng phải tự nhập CAPTCHA và tự bấm nút tra cứu.

### Cài extension ở chế độ phát triển

1. Mở `chrome://extensions/` hoặc `edge://extensions/`.
2. Bật **Developer mode**.
3. Chọn **Load unpacked**.
4. Chọn thư mục:

   ```text
   petrolimex-autofill
   ```

5. Nếu đã sửa extension, bấm **Reload**.
6. Mở menu **Extensions** và ghim extension nếu muốn icon xuất hiện trên thanh trình duyệt.

Extension cài bằng **Load unpacked** bắt buộc phải bật Developer mode. Muốn tắt Developer mode, extension cần được phát hành qua Chrome Web Store/Edge Add-ons hoặc được cài bằng chính sách quản trị doanh nghiệp.
**Đang trong quá trình upload lên Microsoft Edge Add-ons**

## Quyền riêng tư

- XML được đọc và xử lý cục bộ trong trình duyệt.
- Ứng dụng không tải XML lên máy chủ.
- Ứng dụng không thu thập hoặc gửi dữ liệu hóa đơn.
- Extension chỉ đọc clipboard khi người dùng chủ động bấm nút dán mã.
- CAPTCHA vẫn do người dùng nhập thủ công.

## Lưu ý

- Nên kiểm tra lại mã và thông tin hiển thị trước khi tra cứu.
- Trang tra cứu của nhà cung cấp có thể thay đổi giao diện hoặc tên trường nhập liệu.
- Nếu autofill không hoạt động sau khi cập nhật extension, hãy bấm **Reload** tại trang quản lý extension rồi mở lại trang tra cứu.
- Không cung cấp mã CAPTCHA hoặc dữ liệu nhạy cảm cho bên thứ ba.

## Theme được dùng AI để nâng cấp, còn lại mọi thứ đều được phát triển bởi @lylyhecker

## Tệp chính

- [iTaxViewer-Web.html](./iTaxViewer-Web.html): ứng dụng đọc XML và xuất PDF.
- [petrolimex-autofill/manifest.json](./petrolimex-autofill/manifest.json): cấu hình browser extension.
- [petrolimex-autofill/content.js](./petrolimex-autofill/content.js): logic tự điền mã tra cứu.
- [petrolimex-autofill/popup.html](./petrolimex-autofill/popup.html): nội dung popup của extension.
