# BÀI LÀM – HACKATHON 02

- **Mã đề:** 01
- **Họ tên:**
- **Lớp:**
- **Link repository:**
- **Hệ điều hành (Windows/macOS):**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
# Ghi lần lượt các lệnh đã chạy, mỗi lệnh một dòng
Hiển thị đường dẫn tuyệt đối của thư mục hiện tại: pwd
Liệt kê nội dung, gồm cả file ẩn: ls
Di chuyển file ghi_chu_ban_giao.txt vào docs:
mv .\ghi_chu_ban_giao.txt .\docs\
Tạo thư mục backup trong thư mục gốc:
mkdir backup
Sao chép data/dat_san_thang_10.xlsx vào backup:
cp .\data\dat_san_thang_10.xlsx .\backup\
Xoá file .tmp tại thư mục gốc; không xoá file khác:
rm .\temp_002.tmp
Dùng đường dẫn tương đối vào logs, liệt kê nội dung rồi quay lại thư mục gốc:
 cd .\logs\
 ls
 cd ..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
(Dán kết quả vào đây – xoá dòng này)


    Directory: C:\Users\ADMIN\OneDrive\Desktop\Luyen_Tap\starter-kit\st
    arter-kit\san-bong-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
dar--l         11/3/2026   8:37 AM                backup
dar--l         11/3/2026   8:33 AM                data
dar--l         11/3/2026   8:36 AM                docs
dar--l         11/3/2026   8:28 AM                evidence
dar--l         11/3/2026   8:41 AM                logs
dar--l         11/3/2026   8:26 AM                web
-a---l         11/3/2026   8:26 AM             76 .env
-a---l         11/3/2026   8:26 AM           2409 bai_lam.md


    Directory: C:\Users\ADMIN\OneDrive\Desktop\Luyen_Tap\starter-kit\st
    arter-kit\san-bong-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---l         11/3/2026   8:26 AM           6074 dat_san_thang_10.xlsx


    Directory: C:\Users\ADMIN\OneDrive\Desktop\Luyen_Tap\starter-kit\st
    arter-kit\san-bong-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---l         11/3/2026   8:26 AM           6074 dat_san_thang_10.xlsx


    Directory: C:\Users\ADMIN\OneDrive\Desktop\Luyen_Tap\starter-kit\st
    arter-kit\san-bong-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---l         11/3/2026   8:26 AM            154 ghi_chu_ban_giao.txt


    Directory: C:\Users\ADMIN\OneDrive\Desktop\Luyen_Tap\starter-kit\st
    arter-kit\san-bong-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---l         11/3/2026   8:26 AM            956 access.log
-a---l         11/3/2026   8:41 AM            638 loi_500.txt


    Directory: C:\Users\ADMIN\OneDrive\Desktop\Luyen_Tap\starter-kit\st
    arter-kit\san-bong-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
dar--l         11/3/2026   8:26 AM                images
-a---l         11/3/2026   8:26 AM            590 app.js
-a---l         11/3/2026   8:26 AM            529 index.html
-a---l         11/3/2026   8:26 AM            460 style.css


    Directory: C:\Users\ADMIN\OneDrive\Desktop\Luyen_Tap\starter-kit\st
    arter-kit\san-bong-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---l         11/3/2026   8:26 AM           3101 logo-san-bong.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
# Ghi lệnh vào đây (xoá dòng này)
Get-Content .\logs\access.log | Select-String "status=500" > .\logs\loi_500.txt
```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
(Dán kết quả vào đây – xoá dòng này)
2026-10-28 08:24:34 POST /api/thanh-toan status=500
2026-10-28 08:28:45 POST /api/thanh-toan status=500
```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
# Ghi lệnh vào đây (xoá dòng này)
 (Get-Content .\logs\access.log | Select-String "status=404").Count
```

```text
(Dán kết quả đếm vào đây – xoá dòng này)
4
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# Ghi lệnh vào đây (xoá dòng này)

```

### Nội dung file logs/tong_hop.txt

```text
(Dán nội dung file vào đây – xoá dòng này)

```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** 
- **Expected:** 
- **Actual:** 
- **Log:** 

### Câu tìm kiếm Google

```text
(Ghi câu tìm kiếm vào đây – xoá dòng này)

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/dat_san_thang_10.xlsx`, không cần ghi vào đây.
