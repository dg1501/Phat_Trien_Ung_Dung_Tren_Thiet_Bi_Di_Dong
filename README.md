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

c) Logic xử lý khi bấm nút "Quay lại"

- Vào thư mục Btn_Back1 $\rightarrow$ Kéo khối when Btn_Back1.Click do ra màn hình làm việc.

<img width="857" height="983" alt="{B72046CF-40CE-4F9B-8787-0013AA60307A}" src="https://github.com/user-attachments/assets/1bad6adf-8381-4224-bd2a-96a131e4495e" /></p>

- Vào mục Control (Màu vàng) $\rightarrow$ Kéo khối lệnh close screen gắn vào trong. Lệnh này có bản chất là giải phóng (đóng) màn hình giải toán hiện tại để ứng dụng tự động quay trở về màn hình chính (Screen1) nằm ở tầng bên dưới.

<img width="942" height="1018" alt="{B63A3E46-21C4-4BF8-8FD1-F1F0E290FDA6}" src="https://github.com/user-attachments/assets/d745adfe-f4f1-4a22-83ce-a963d22b57a0" /></p>

d) Tại Screen_WebView

- Kéo khối when Btn_Back2.Click do -> Chọn khối close screen.

<img width="1920" height="1026" alt="{3F77FAC3-9AE9-411F-8E9E-94A5F9EC0D91}" src="https://github.com/user-attachments/assets/350d00a5-354b-4dcb-962e-4dfd1b5222b7" /></p>

e) Test

BƯỚC 1: Tải ứng dụng MIT App Inventor trên iPhone

- Mở ứng dụng App Store trên iPhone lên.

- Vào ô tìm kiếm và gõ từ khóa: MIT App Inventor (hoặc MIT AI2 Companion).

- Tiến hành tải và cài đặt ứng dụng này về máy (App hoàn toàn miễn phí và chính chủ do học viện MIT phát hành).

BƯỚC 2: Kết nối và đồng bộ ứng dụng từ Máy tính sang iPhone

- Đảm bảo cả máy tính (đang mở trang web code) và iPhone của bạn đang kết nối chung một mạng Wi-Fi (hoặc iPhone phát mạng 4G cho máy tính bắt đều được).

- Trên màn hình máy tính, nhìn lên thanh menu trên cùng $\rightarrow$ Chọn mục Connect $\rightarrow$ Click chọn AI Companion. Lúc này màn hình máy tính sẽ hiển thị một ô chứa mã QR Code và một chuỗi 6 ký tự.

<img width="1920" height="1020" alt="{0DA2A628-BD61-4833-80AF-30DEEEB48D6D}" src="https://github.com/user-attachments/assets/ed6828cc-9099-4972-bf94-485f48544345" /></p>

<img width="1920" height="1027" alt="{AAF0F393-59A4-4A3E-B961-8CE07F5808DD}" src="https://github.com/user-attachments/assets/1548d3d4-b23e-4000-8171-f29c8660841c" /></p>

- Trên iPhone, bạn mở ứng dụng MIT App Inventor vừa tải về lên.

Bạn có 2 cách để kết nối:

- Cách nhanh nhất: Bấm vào nút Scan QR Code (Màu xanh dương) trên iPhone $\rightarrow$ Cấp quyền cho app truy cập Camera $\rightarrow$ Đưa camera lên quét mã QR trên màn hình máy tính.

<img width="870" height="1883" alt="image" src="https://github.com/user-attachments/assets/093ef11f-d741-4489-88f2-aa9e0135b59c" /></p>

- Cách thủ công: Gõ chính xác 6 ký tự hiển thị trên máy tính vào ô character code trên iPhone $\rightarrow$ Bấm nút Connect with code (Màu cam).

<img width="870" height="1883" alt="image" src="https://github.com/user-attachments/assets/eb0fe02a-306a-4a20-8330-6276c4dfed03" /></p>

<img width="870" height="1883" alt="image" src="https://github.com/user-attachments/assets/1432fe52-972d-4be1-be7d-260795fa3b81" /></p>

<img width="870" height="1883" alt="image" src="https://github.com/user-attachments/assets/dd0ccc39-370c-4acb-a347-9e1fc05a6996" /></p>

---

## PHẦN 2: VIẾT APP SỬ DỤNG ANDROID STUDIO (JAVA)

Mở Android Studio -> Tạo Project mới -> Chọn Empty Views Activity (hoặc Empty Activity tùy phiên bản nhưng chọn Java) -> Ngôn ngữ: Java.

<img width="1134" height="812" alt="{E64A089E-01F0-48F8-969F-2B4A4568762E}" src="https://github.com/user-attachments/assets/6d015289-6f53-4821-82cf-3d7b79559818" /></p>

<img width="1129" height="811" alt="{BE786445-D3E5-4D2C-9D22-789D34647707}" src="https://github.com/user-attachments/assets/5cd929a8-e327-46ed-bb1e-94e4d0cc49c1" /></p>

### 1. Kiến trúc Android Cơ bản & Vòng đời (Lifecycle)

***AndroidManifest.xml là gì?***

- Nằm trong thư mục app/src/main/AndroidManifest.xml. Đây là file cấu hình bắt buộc của mọi app Android. Nó mô tả cho Hệ điều hành (OS) biết: Tên app, icon, các Activity (màn hình) có trong app, và các quyền (Permissions) mà app cần hệ điều hành cấp phép để hoạt động.

- Khai báo quyền: Ví dụ app cần quyền Internet và quyền đọc bộ nhớ:

### Cấu hình các quyền trong ứng dụng

Bổ sung các quyền truy cập Internet và bộ nhớ vào file `AndroidManifest.xml`:

### Cấu hình các quyền trong ứng dụng

Bổ sung các quyền truy cập Internet và bộ nhớ vào file `AndroidManifest.xml`:

```xml
<manifest xmlns:android="[http://schemas.apple.com/apk/res/android](http://schemas.apple.com/apk/res/android)" package="com.example.btl_android">
    <uses-permission android:name="android.permission.INTERNET" />
    
    <application ...>
    </application>
</manifest>
```

- Mục đích: Để đảm bảo tính bảo mật. Từ Android 6.0+, các quyền nguy hiểm còn phải được người dùng đồng ý lúc đang chạy ứng dụng (Runtime Permission).

<img width="1390" height="732" alt="{8227AD88-371B-493A-8AA6-E273C569EF2D}" src="https://github.com/user-attachments/assets/75f794e1-aab8-4758-a481-0ebbf7497515" /></p>

***Vòng đời của một ứng dụng Android (Activity Lifecycle)***

- Khi một Activity chạy, nó đi qua các trạng thái được quản lý bởi các hàm callback: onCreate() -> onStart() -> onResume() -> onPause() -> onStop() -> onDestroy().

- Tại sao code tự sinh luôn có sẵn hàm onCreate()? Vì đây là điểm khởi đầu của một Activity. Hàm này chỉ chạy duy nhất 1 lần khi Activity được khởi tạo. Đây là nơi bắt buộc để thiết lập giao diện (gọi hàm setContentView), khởi tạo các biến, ánh xạ các view (findViewById), giúp app có bộ khung trước khi hiển thị lên màn hình cho người dùng thấy.

### 2. Giao diện (XML) & Quản lý Tài nguyên (Resources)

***Khái niệm Tham chiếu thay vì Hardcode***

Trong file giao diện XML (nằm trong res/layout/), thay vì viết cứng chữ: android:text="Nguyễn Văn A" (gọi là Hardcode), ta nên lưu chuỗi này vào file res/values/strings.xml:

```xml
<resources>
    <string name="app_name">BTL_Android</string>
    <string name="my_name">Họ và tên: Nguyễn Đức Dương</string>
    <string name="my_msv">MSV: K225480106093</string>
    <string name="my_class">Lớp: k58KTP</string>
    <string name="btn_to_toan">Giải Toán</string>
    <string name="btn_to_web">Xem Web</string>
</resources>
```

- Cú pháp tham chiếu trong file XML: @string/my_name

- Cú pháp tham chiếu bằng Code Java: R.string.my_name

- Ưu điểm: Dễ quản lý, khi cần sửa đổi text chỉ cần sửa 1 nơi trong file strings.xml thì toàn bộ app sẽ tự đổi theo.

- Cơ chế Tự động (Auto) của OS: Khi ta tạo các thư mục tài nguyên đặc biệt như res/values-en/ (Tiếng Anh), res/values-vi/ (Tiếng Việt), hay res/values-night/ (Theme tối). Khi người dùng thay đổi LOCATION, LANGUAGE, THEME trên máy, Android OS sẽ tự động tìm đến thư mục tương ứng để lấy giá trị mà không cần lập trình viên viết code kiểm tra logical.

- Tác dụng: Giúp ứng dụng dễ dàng Đa ngôn ngữ hóa (Localization) và hỗ trợ các chế độ màn hình (Dark Mode) một cách mượt mà nhất.

<img width="1738" height="958" alt="{F9B2E749-3F5D-4D5E-A5EF-58CB3027B990}" src="https://github.com/user-attachments/assets/9ea05d04-a885-4609-8656-fd6084ace4cf" /></p>

***Đối tượng chứa (ViewGroup) - Ví dụ: LinearLayout***

Là đối tượng dùng để gom các đối tượng con (TextView, Button...) lại theo một quy luật sắp xếp.

Mở file app/src/main/res/layout/activity_main.xml. Sử dụng layout dạng LinearLayout dạng dọc để sắp xếp các thành phần:

<img width="1737" height="960" alt="{0C26E502-E7A6-45A9-AF3F-A3821DC25A13}" src="https://github.com/user-attachments/assets/f7ad4451-3e3f-4f4c-9e8c-9ef3f3c0a222" /></p>

<img width="1735" height="963" alt="{10DCBB96-C94D-4CB6-BF59-6EFB59537F92}" src="https://github.com/user-attachments/assets/65b9c5f8-79f2-4a50-94cb-466e6259d58a" /></p>

### 3. Tương tác Code Java và Layout (Tránh Hardcode & Xử lý Sự kiện)

Mở file MainActivity.java. Chúng ta sẽ thực hiện ánh xạ view bằng findViewById, gán văn bản chuẩn hóa bằng hàm getString() từ tài nguyên, và sử dụng Anonymous Listener (Cách 1) để xử lý sự kiện bấm nút nhảy màn hình thông qua Intent.

Chú ý: Trước khi viết code Intent, bạn cần tạo trước 2 Activity trống mới bằng cách: Click chuột phải vào thư mục gói code (com.example.btl_android) $\rightarrow$ New $\rightarrow$ Activity $\rightarrow$ Empty Views Activity. Đặt tên lần lượt là GiaiToanActivity và WebViewActivity.

<img width="1746" height="1055" alt="{252042ED-B79F-48D5-8965-BA44BF28810F}" src="https://github.com/user-attachments/assets/8845b9f1-cfda-44e7-974f-9c116789ebc7" /></p>

<img width="383" height="741" alt="{6AD6D4CF-0247-4B30-89B2-FFD3E67BC172}" src="https://github.com/user-attachments/assets/bc68e8d3-0ed7-46e7-9c7a-5a28a297a8bc" /></p>

***Xử lý Sự kiện Click Button (2 cách phổ biến)***

Để click vào Button trên Layout chạy một đoạn code:

- Cách 1: Khai báo Anonymous Listener (Viết trực tiếp trong Code Java - Khuyên dùng)

    - Layout XML:

      ```xml
      <Button
        android:id="@+id/btnClickMe"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Bấm vào đây" />
      ```

    - Code Java (trong hàm onCreate):

      ```xml
      Button btnClickMe = findViewById(R.id.btnClickMe);
      btnClickMe.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            // Viết đoạn code muốn thực thi ở đây
            Toast.makeText(MainActivity.this, "Bạn đã click cách 1!", Toast.LENGTH_SHORT).show();
        }
      });
      ```

- Cách 2: Sử dụng thuộc tính onClick trong XML

    - Layout XML: Thêm thuộc tính android:onClick="xuLyClickButton"

      ```xml
      <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Bấm vào đây"
        android:onClick="xuLyClickButton" />
    ```

    - Code Java: Viết một hàm public có tên trùng khớp trong Activity class:

        ```xml
        public void xuLyClickButton(View view) {
            // Viết đoạn code muốn thực thi ở đây
            Toast.makeText(this, "Bạn đã click cách 2!", Toast.LENGTH_SHORT).show();
        }
        ```
<img width="1732" height="965" alt="{924241C3-3C67-44A2-9520-E12DF4288538}" src="https://github.com/user-attachments/assets/5a0e37da-3d9e-4bea-96f4-86e99fb3fe39" /></p>

### 4. Ứng dụng APP 1: Sử dụng Dữ liệu Chuẩn bị trước trong Assets

***Bản chất thư mục assets:***

- Thư mục assets (Tạo bằng cách: Click chuột phải vào thư mục app -> New -> Folder -> Assets Folder). Khi build app, toàn bộ file trong này (txt, json, csv, hình ảnh...) sẽ được đóng gói nguyên vẹn đi theo file APK cài đặt. App có thể đọc các file này kể cả khi không có mạng Internet (Offline).

    - Cú pháp truy cập bằng Java:
      
      `InputStream is = getAssets().open("ten_file.txt");`

    - Lợi ích: Tiết kiệm băng thông, app chạy mượt, dữ liệu tĩnh luôn sẵn sàng ngay khi cài đặt xong app.
 
    - Ứng dụng thực tế: Làm app Cẩm nang bỏ túi, Ẩm thực nấu ăn, hoặc App hướng dẫn học tập.

Bước 1: Tạo thư mục assets và file dữ liệu socuu.json

- Tại cây thư mục bên trái của Android Studio, nhấp chuột phải vào thư mục app $\rightarrow$ New $\rightarrow$ Folder $\rightarrow$ Assets Folder $\rightarrow$ Nhấn Finish.

- Nhấp chuột phải vào thư mục assets vừa xuất hiện $\rightarrow$ New $\rightarrow$ File $\rightarrow$ Đặt tên file là socuu.json.

<img width="1737" height="974" alt="{C4AA7694-0730-4B7D-A1DA-1820AEC25EE8}" src="https://github.com/user-attachments/assets/46fd3108-8fc3-44bc-ba9d-07c818dcc9b1" /></p>

<img width="1833" height="1056" alt="{FFA5A339-4F86-4819-A442-75F6242AE9B4}" src="https://github.com/user-attachments/assets/8d30bf28-384f-4561-be06-3eb07bd948b5" /></p>

- Thêm nội dung cho file vừa tạo

<img width="1739" height="964" alt="{1E277A2A-229D-46E6-B9F0-46B1FB321DE4}" src="https://github.com/user-attachments/assets/954a4957-ad89-4a35-943b-42f2afce3f30" /></p>

Bước 2: Thiết kế giao diện Spinner chọn bệnh (activity_main.xml)

- Vào thư mục res/layout, mở file activity_main.xml ra, xóa hết code mặc định cũ đi và dán đoạn code giao diện này vào:

<img width="653" height="978" alt="{DC1716BD-5B6B-40F9-9C29-5CE99223E587}" src="https://github.com/user-attachments/assets/25eb4ec9-5f5d-4861-8eea-8c9ca813f804" /></p>

<img width="1737" height="962" alt="{A37CE37D-93DF-4BB3-80DD-320E46557619}" src="https://github.com/user-attachments/assets/1c435aa2-aa71-43d3-842e-799c7a42cb72" /></p>

<img width="1738" height="970" alt="{6D343EFA-A9FF-4AEC-981F-09F59BFC33C4}" src="https://github.com/user-attachments/assets/0acff7fb-0775-4762-a59c-60d94c40b1ed" /></p>

Bước 3: Bước 3: Đọc và bóc tách dữ liệu JSON (MainActivity.java)

- Vào thư mục java, tìm mở file MainActivity.java lên. Hãy xóa sạch ruột bên trong đi và dán đoạn code xử lý logic đọc file JSON từ thư mục assets này vào:

<img width="733" height="972" alt="{DAC9E8DF-8FE4-4E24-A712-4F25DB05D62C}" src="https://github.com/user-attachments/assets/c56a34b6-64fd-432d-9987-df3fecc151ee" /></p>

<img width="1738" height="971" alt="{804FF7FD-788F-4E10-AB5C-45861238327F}" src="https://github.com/user-attachments/assets/670f9924-be3e-437d-a769-339bc668c2a8" /></p>

### 5. Ứng dụng 2: Giải phương trình bậc 1 & Gọi API POST dữ liệu lên Server

Bước 1: Cập nhật Giao diện trong activity_giai_toan.xml

- Mở file activity_giai_toan.xml ra, xóa sạch code cũ và dán đè đoạn code thiết kế mới này vào. Giao diện này sẽ gồm 2 ô nhập hệ số $a, b$, một nút bấm tính toán và vùng hiển thị kết quả nghiệm.

<img width="1733" height="959" alt="{6A6794E6-2E9C-401E-8EB7-03C358876FA1}" src="https://github.com/user-attachments/assets/43def2a3-ded0-43be-9794-f41aaeaab278" /></p>

Bước 2: Triển khai Logic Biện luận và Gọi API trong

- Mở file GiaiToanActivity.java lên (nằm trong thư mục java/com.example.app1).

<img width="1735" height="962" alt="{40DED8E2-3F5E-477E-88D1-A30CB3CB724A}" src="https://github.com/user-attachments/assets/7bb6999d-6f87-4f9d-b6a7-854d22379e0b" /></p>

### 6. Khởi tạo và Thiết lập Màn hình WebView (WebViewActivity.java)

Bước 1: Thiết kế Giao diện activity_web_view.xml

- Mở file giao diện tương ứng kéo thả đối tượng WebView dãn tràn toàn màn hình:

<img width="1734" height="966" alt="{8051FA85-4B57-4A8B-BF0E-FF97377DE4C2}" src="https://github.com/user-attachments/assets/ff42a8a8-b83d-488e-976a-7d082fc54342" /></p>

Bước 2: Viết code điều khiển WebView (WebViewActivity.java)

<img width="1749" height="974" alt="{F65B5ACB-C07B-47F1-9AE4-F57A318526F3}" src="https://github.com/user-attachments/assets/7147ceb5-c8bf-430d-b5a3-695abe530b63" /></p>

Bước 3: Kiểm tra quyền mạng Internet (AndroidManifest.xml)

- Bất kể là chạy link trường hay link Google, hệ điều hành Android đều bắt buộc phải có lệnh xin quyền mở cổng mạng. Mở file AndroidManifest.xml lên và kiểm tra xem đã có dòng này chưa, nếu chưa có thì dán vào ngay dưới dòng <manifest ...>

<img width="1738" height="966" alt="{27EB7E17-BB9A-4C04-ABB1-C2BADCDD9C1F}" src="https://github.com/user-attachments/assets/cbde15e7-35db-47dc-b633-5937aa4f1f6a" /></p>

### 7. Test 2 App

a) APP 1

<img width="1737" height="964" alt="{92E92C24-AD09-49CC-A337-2D13088ABBC3}" src="https://github.com/user-attachments/assets/1533385a-99ca-423b-aaf0-5a3b98104905" /></p>

<img width="1742" height="962" alt="{52E37C1B-894F-4252-938A-7ACFF8DC85D2}" src="https://github.com/user-attachments/assets/8488c82c-ea5c-4b09-9ef0-23bc86c0e33d" /></P>

<img width="1738" height="963" alt="{C327C9E7-622F-44A8-BF63-697587C6EB80}" src="https://github.com/user-attachments/assets/db195212-5a40-45c8-a27f-64a52808433d" /></p>

b) APP 2

<img width="1736" height="961" alt="{EA9DC52E-F04E-43A6-95F1-729C9FB027B8}" src="https://github.com/user-attachments/assets/a0e18f5b-19ce-4ead-adc8-fec952686e94" /></p>

<img width="1741" height="963" alt="{7EED73A7-1B21-486E-AE41-7572303D0FD5}" src="https://github.com/user-attachments/assets/72db1298-7275-4e42-864f-3f675217e5b3" /></p>

<img width="1733" height="962" alt="{C2627378-879B-4D5A-B58C-33DC49BDB058}" src="https://github.com/user-attachments/assets/5f7504db-943c-4720-bcdf-5cba5c35577d" /></p>

<img width="1731" height="958" alt="{71DA55FD-73B1-49D1-881A-64CB9E22E155}" src="https://github.com/user-attachments/assets/fa96ce50-e76e-413c-9bee-583fe4bd46e9" /></p>

<img width="1732" height="959" alt="image" src="https://github.com/user-attachments/assets/7514f539-9f1a-4149-b0f5-e5c2f3f21f81" /></p>

<img width="1739" height="963" alt="image" src="https://github.com/user-attachments/assets/1b6b12e0-4649-477a-a4ab-d5b54d25c36e" /></p>




