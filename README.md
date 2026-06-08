## PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG 
### HỌ TÊN: NGUYỄN ĐỨC DƯƠNG
### LỚP: K58KTP
### MSSV: K225480106093

---

## PHẦN 1: PHÁT TRIỂN ỨNG DỤNG TRÊN MIT APP INVENTOR

### 1. Quy trình tạo phần mềm & Thiết kế Giao diện (Designer)

- MIT App Inventor hoạt động trên nền web. Truy cập `https://www.google.com/search?q=http://ai2.appinventor.mit.edu` . Đăng nhập bằng tài khoản Google và ấn **New project** -> **Đặt tên cho Project**

<img width="1399" height="736" alt="{0E4276B7-BC52-4FE6-8B88-91776A251141}" src="https://github.com/user-attachments/assets/520c9bca-57a8-4551-a31f-cddb32ca1ccf" /></p>

<img width="449" height="348" alt="{C948FD00-E006-4FC1-BC74-D109FF1F3871}" src="https://github.com/user-attachments/assets/d0ac7fb0-bb0a-476f-ac5c-0a3938f3b15d" /></p>

Giao diện chia làm các khu vực chính:

- Palette (Thanh công cụ): Nơi chứa các thành phần (giao diện, cảm biến, lưu trữ...).

- Viewer: Màn hình điện thoại mô phỏng để kéo thả.

- Components: Cây danh sách các đối tượng đã kéo vào màn hình.

- Properties: Nơi thay đổi thuộc tính (Màu sắc, kích thước, text...) của đối tượng được chọn.

---

**Bước 1: Tạo các Screen và Thiết kế Giao diện**

- Ở phía trên cùng, bấm nút Add Screen để tạo đủ 3 Screen: ***Screen1 (mặc định)***, ***Screen_GiaiToan***, và ***Screen_WebView***

<img width="1413" height="709" alt="{19282960-C0D1-4180-A784-FD947E625DBE}" src="https://github.com/user-attachments/assets/cbdc89eb-a927-4de1-abca-e64116c9fbc8" /></p>

a) Cấu hình Screen1 (About bản thân & Điều hướng)

- Kéo thả: Vào **Layout** -> Kéo **VerticalArrangement** vào màn hình (Đặt thuộc tính Width = Fill parent, AlignHorizontal = Center).

<img width="1920" height="1029" alt="{3AB86503-5F4D-4C0E-9454-EC1368C5A697}" src="https://github.com/user-attachments/assets/41a2c971-8f23-4800-a6a1-ef9fd437dbdd" /></p>

- Vào **User Interface** -> Kéo 3 Label và 2 Button vào trong vùng Layout vừa tạo.

<img width="1920" height="1025" alt="{BF020D45-4728-43EE-AE06-88C3A7D61A14}" src="https://github.com/user-attachments/assets/f76f1462-9f4e-4b87-b2d5-cd748a941ab3" /></p>

- Thay đổi thuộc tính (Properties):

Label1: Đổi Text thành "Họ và tên: Nguyễn Đức Dương"

Label2: Đổi Text thành "MSV: K225480106093"

Label3: Đổi Text thành "Lớp: K58KTP"

Button1: Đổi Name thành Btn_ToiGiaiToan, Text thành "Giải Toán"

Button2: Đổi Name thành Btn_ToiWebView, Text thành "Xem Web"

<img width="1920" height="1027" alt="{CA29ABC9-9845-498D-B89E-FF1436588320}" src="https://github.com/user-attachments/assets/1cd8c6ec-2df0-4304-8c84-f7aeaf090a48" /></p>

b) Cấu hình Screen_GiaiToan (Giải phương trình bậc nhất ax + b = 0)

- Để xây dựng giao diện nhập hệ số và hiển thị kết quả cho bài toán phương trình bậc nhất, ta truy cập vào thanh công cụ Palette, chọn thẻ User Interface và thực hiện kéo thả các thành phần sau vào vùng hiển thị (Viewer):

2 TextBox: Dùng làm nơi cho người dùng nhập hai hệ số $a$ và $b$ của phương trình.

1 Button (Giải toán): Đối tượng kích hoạt sự kiện tính toán sau khi người dùng điền đầy đủ dữ liệu.

1 Label (Kết quả): Thành phần tĩnh dùng để xuất kết quả của phương trình (Vô nghiệm, Vô số nghiệm hoặc Nghiệm duy nhất) ra màn hình.

1 Button (Quay lại): Nút chức năng điều hướng để quay trở về màn hình chính (Screen1).

<img width="1919" height="1024" alt="image" src="https://github.com/user-attachments/assets/1a09d1e0-6e52-496b-a529-2c15099eb2d8" /></p>

- Thay đổi thuộc tính đối tượng (Properties)

| Tên mặc định | Tên mới (Rename) | Thuộc tính cần thay đổi (Properties) | Mục đích sử dụng |
| :--- | :--- | :--- | :--- |
| **TextBox1** | `Txt_SoA` | - **Hint**: "Nhập hệ số a..."<br>- **NumbersOnly**: Tích chọn (True) | Nhận dữ liệu đầu vào của hệ số $a$. Chỉ cho phép bàn phím số hiển thị để tránh lỗi nhập chữ. |
| **TextBox2** | `Txt_SoB` | - **Hint**: "Nhập hệ số b..."<br>- **NumbersOnly**: Tích chọn (True) | Nhận dữ liệu đầu vào của hệ số $b$. Chỉ cho phép nhập số. |
| **Button1** | `Btn_GiaiPT` | - **Text**: "Giải Phương Trình"<br>- **BackgroundColor**: Chọn màu tùy ý (ví dụ: Blue) | Bắt sự kiện Click của người dùng để bắt đầu chạy thuật toán giải phương trình. |
| **Label1** | `Lbl_KetQua` | - **Text**: "Kết quả sẽ hiển thị ở đây"<br>- **FontSize**: 18<br>- **TextColor**: Chọn màu đỏ để nổi bật | Vùng hiển thị câu kết luận nghiệm và giá trị nghiệm $x$ sau khi tính toán. |
| **Button2** | `Btn_Back1` | - **Text**: "Quay lại Màn hình chính" | Bắt sự kiện Click để thực hiện lệnh đóng màn hình hiện tại, trả ứng dụng về màn hình trước đó. |

<img width="1920" height="1021" alt="{A4236907-A17E-45DB-8E96-C7D25A7D9B84}" src="https://github.com/user-attachments/assets/d643457d-d9d4-46e2-8347-aa12eb8eed3b" /></p>

c) Cấu hình Screen_WebView (Hiển thị trang web):

- Kéo thả: Vào mục User Interface -> Kéo đối tượng WebViewer thả vào màn hình. Kéo thêm 1 Button đặt phía dưới: Đổi tên thành Btn_Back2, Text: "Quay lại".

- Chọn WebViewer1 -> Nhìn sang cột Properties -> Tại mục HomeUrl, dán link hỗ trợ giao diện điện thoại vào (Ví dụ: https://m.tinhte.vn hoặc https://google.com).

<img width="1920" height="1024" alt="{8D6BF69D-3D18-49B3-835B-A7EB67DEAE11}" src="https://github.com/user-attachments/assets/d5ef2fef-750a-4f0c-9050-542654b40cf2" /></p>
