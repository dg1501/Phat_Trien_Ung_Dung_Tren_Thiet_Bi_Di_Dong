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

---

### 2. Lập trình Logic (Blocks)

- Bấm vào nút Blocks ở góc trên bên phải để chuyển sang giao diện lập trình kéo thả.

<img width="1400" height="732" alt="{DBD59746-C409-4756-BE8A-B3D15B1DCB87}" src="https://github.com/user-attachments/assets/20a49ea5-ca5a-4d78-b281-0264b3e988be" /></p>

<img width="1920" height="1023" alt="{580BA35A-42EB-493F-9A5B-DB7527650198}" src="https://github.com/user-attachments/assets/e02399f0-7e8e-4383-bb51-bc13a4b4163c" /></p>

- Kéo khối logic cho từng Screen:

a) Tại Screen1

- Bấm vào Btn_ToiGiaiToan -> Kéo khối when Btn_ToiGiaiToan.Click do.

<img width="1920" height="1029" alt="{270CE57E-47FB-4315-BB38-4485471BC022}" src="https://github.com/user-attachments/assets/bb50eeff-1667-4496-be58-c74baa227c7e" /></p>

<img width="1920" height="1018" alt="{690F87D3-7F1B-47DB-902C-0086DB14BAE7}" src="https://github.com/user-attachments/assets/32be07e9-30b1-4a52-8ba5-13ab29b23fef" /></p>

- Bấm vào mục Control (Màu vàng) -> Kéo khối open another screen screenName.

<img width="1920" height="1034" alt="{E03BDBEF-7273-498F-A810-F6972F2F6EBE}" src="https://github.com/user-attachments/assets/884397e9-51a0-4e21-a82b-cc3e7ca422ed" /></p>

- Bấm vào mục Text (Màu hồng) -> Kéo khối chuỗi trống "", gắn vào và gõ chính xác chữ: Screen_GiaiToan.

<img width="1920" height="1017" alt="{96928F21-3F8E-4852-9862-CA545FC8B9B5}" src="https://github.com/user-attachments/assets/637f226a-56c2-42ad-9e1d-37e936ca2e9e" /></p>

<img width="673" height="182" alt="{6F4DEE8D-EB82-4C99-A694-1E90B1DAA3DC}" src="https://github.com/user-attachments/assets/84f06a52-5263-4fb8-af33-588344db2534" /></p>

- Làm tương tự cho Btn_ToiWebView để mở Screen_WebView.

<img width="1919" height="1019" alt="{DB9A8A19-4522-4553-AC02-B8EC717C4C7C}" src="https://github.com/user-attachments/assets/851b7d16-6286-4d97-940c-4a071d419bad" /></p>

b) Tại Screen_GiaiToan

Bước 1: Logic xử lý khi bấm nút "Giải Phương Trình"

- Bắt sự kiện Click: Vào thư mục Btn_GiaiPT $\rightarrow$ Kéo khối when Btn_GiaiPT.Click do ra màn hình làm việc.

<img width="848" height="922" alt="{271064C6-D983-4E31-A4E4-3147AF1B047D}" src="https://github.com/user-attachments/assets/83de6872-8c1f-45d5-a336-4e3ad68a6803" /></p>

- Khởi tạo cấu trúc điều kiện rẽ nhánh: * Vào mục Control (Màu vàng) $\rightarrow$ Kéo khối lệnh điều kiện if then đặt vào bên trong khối Click.

<img width="1920" height="1026" alt="{6B574A1C-EB11-4464-9251-F42313EC1941}" src="https://github.com/user-attachments/assets/fc0a4ae8-632e-47fd-a6b7-9f51458689ed" /></p>

-- Bấm vào icon bánh răng màu xanh trên khối if vừa kéo, kéo thêm một nhánh else if và một nhánh else từ hộp thoại nhỏ thả vào khối if gốc để mở rộng thành cấu trúc điều kiện 3 nhánh (if - else if - else).

<img width="590" height="327" alt="{3F7B250D-A7C3-49BD-ACF9-6E749EAAFB90}" src="https://github.com/user-attachments/assets/4a1f3b27-0057-4e0e-a8fa-1ec50d112e68" /></p>

Bước 2: Logic các điều kiện phương trình

Nhánh 1: Kiểm tra trường hợp Vô số nghiệm (Nếu $a = 0$ và $b = 0$)

- Vào mục Logic (Màu xanh lục) $\rightarrow$ Kéo khối toán tử and gắn vào ô điều kiện sau chữ if.

<img width="627" height="877" alt="{B6E45B62-63D8-46B7-BF47-4CB5453BB3A4}" src="https://github.com/user-attachments/assets/d06a0fa0-e9b4-4334-9dc0-2eaca4af15a1" /></p>

- Vào mục Math (Màu xanh dương) $\rightarrow$ Kéo khối so sánh [ = ] gắn vào vế trái của khối and. Chọn vế trái là khối Txt_SoA.Text, vế phải là khối số 0 (lấy từ mục Math).

<img width="697" height="878" alt="{B5F4019D-9A91-4838-B4DD-C795DA942DD2}" src="https://github.com/user-attachments/assets/0d046d3b-a4fb-454d-8739-58efe8111b10" /></p>

<img width="746" height="399" alt="{833D6BB6-7CD0-42A4-9CCD-097F824EEACC}" src="https://github.com/user-attachments/assets/8d3b9815-3256-496e-b5a7-7967d55c87d7" /></p>

- Tiếp tục kéo một khối so sánh [ = ] khác gắn vào vế phải của khối and. Chọn vế trái là khối Txt_SoB.Text, vế phải là khối số 0.

<img width="1920" height="1019" alt="{C6F54692-75FD-44E6-A41D-3574C3B942AD}" src="https://github.com/user-attachments/assets/d0b8c12b-d4f3-4b56-a3c8-698800f7ebce" /></p>

- Hành động (then): Vào mục Lbl_KetQua $\rightarrow$ Kéo khối set Lbl_KetQua.Text to gắn vào. Vào mục Text (Màu hồng) $\rightarrow$ Kéo khối chuỗi ký tự trống "", gõ vào nội dung: "Phương trình vô số nghiệm".

<img width="761" height="903" alt="{632EBC50-9381-417B-97FE-CB73E06D1A01}" src="https://github.com/user-attachments/assets/3abb149e-05d8-4602-8a34-482450c4e11d" /></p>

Nhánh 2: Kiểm tra trường hợp Vô nghiệm (Nếu $a = 0$ và $b \neq 0$)

- Thực hiện tương tự như nhánh 1, kéo khối logic and gắn vào sau chữ else if.

- Vế trái khối and: So sánh Txt_SoA.Text bằng 0.

- Vế phải khối and: Kéo khối so sánh đổi dấu thành [ ≠ ] (Khác) để so sánh Txt_SoB.Text với số 0.

- Hành động (then): Kéo khối set Lbl_KetQua.Text to và gắn khối chữ "" với nội dung: "Phương trình vô nghiệm".

<img width="1920" height="1027" alt="{5C7E5F1E-B392-4CAF-ADE5-0EA71F94A718}" src="https://github.com/user-attachments/assets/9125ac4b-435c-468c-b163-0b1af337cee7" /></p>

Nhánh 3: Tính toán nghiệm duy nhất (Trường hợp $a \neq 0$)

- Tại nhánh else cuối cùng, kéo khối set Lbl_KetQua.Text to gắn vào.

<img width="1016" height="537" alt="{767DFEFD-39C7-462B-8F6B-F9F4171D63E2}" src="https://github.com/user-attachments/assets/0951503f-50ef-46ed-8346-05451a175853" /></p>

- Vào mục Text $\rightarrow$ Kéo khối join (khối dùng để ghép các chuỗi văn bản lại với nhau) gắn sau chữ to. Bấm bánh răng của khối join để tăng số lượng chân cắm lên 2 chân (nếu chưa đủ).

<img width="681" height="868" alt="{44C56259-8F32-4541-98DC-3CD79C41A653}" src="https://github.com/user-attachments/assets/ddb7066f-9811-48f8-850d-a8404b06e08c" /></p>

- Chân cắm thứ nhất của join: Gắn khối chữ "" và gõ nội dung: "Nghiệm x = ".

<img width="923" height="517" alt="{E3A74FD3-1454-434E-9E8B-3E1D7E1BC084}" src="https://github.com/user-attachments/assets/a8ee112d-b36d-41ae-97a6-630b590c89cc" /></p>

- Chân cắm thứ hai của join: Vào mục Math $\rightarrow$ Kéo khối phép chia [ / ].

<img width="736" height="1012" alt="{E6F4B17B-F09C-45FC-8CC2-A73BFFA3281A}" src="https://github.com/user-attachments/assets/e7804008-d678-40bc-ab9b-cdf30f8f689f" /></p>

-- Vế trái của phép chia (Tử số): Kéo khối phép trừ [ - ] để tính $-b$, lấy số 0 trừ đi Txt_SoB.Text.

<img width="1155" height="622" alt="{4F753B42-A45D-4262-A449-FE93A197D678}" src="https://github.com/user-attachments/assets/ebd2a171-404a-43ae-b78d-a37080c50444" /></p>

-- Vế phải của phép chia (Mẫu số): Kéo khối Txt_SoA.Text gắn vào.

<img width="1305" height="590" alt="{7B9A1B86-D991-4618-91D4-39D020F74E7A}" src="https://github.com/user-attachments/assets/a7c22aa5-cfcb-4f87-943d-d9b80feb47b3" /></P>
