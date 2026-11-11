# BÀI LÀM – HACKATHON 02

- **Mã đề:** 05
- **Họ tên:**Lê Qang Hào 
- **Lớp:**CNTT1
- **Link repository:**https://github.com/phanthithuy012008-dot/_HN-KS26-CNTT1_Nhap-mon-CNTT_Hackathon02
- **Hệ điều hành (Windows/macOS):**Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -Recurse -force
mv quy_dinh_thue.txt docs/
mkdir backup
cp data/don_thue_thang_5.xlsx backup/
rm *.tmp
cd logs; ls; cd ..
Get-ChildItem -Recurse -Force
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
    Directory: C:\Users\lequanghao\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   7:38 AM                backup
d-----        11/11/2026   7:35 AM                data
d-----        11/11/2026   7:37 AM                docs
d-----        11/11/2026   7:35 AM                evidence
d-----        11/11/2026   7:36 AM                logs
d-----        11/11/2026   7:32 AM                web
------         11/3/2026   7:07 AM             72 .env


    Directory: C:\Users\lequanghao\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6132 don_thue_thang_5.xlsx


    Directory: C:\Users\lequanghao\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6132 don_thue_thang_5.xlsx


    Directory: C:\Users\lequanghao\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            159 quy_dinh_thue.txt


    Directory: C:\Users\lequanghao\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            934 rental.log


    Directory: C:\Users\lequanghao\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   7:32 AM                images
------         11/3/2026   7:07 AM            582 app.js
------         11/3/2026   7:07 AM            534 index.html
------         11/3/2026   7:07 AM            460 style.css


    Directory: C:\Users\lequanghao\Downloads\starter-kit\starter-kit\thue-do-cam-trai-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
------         11/3/2026   7:07 AM           3090 logo-campgo.png


```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
Get-Content logs/rental.log | Select-String "status=500" | Set-Content logs/loi_500.txt
Get-Content logs/loi_500.txt -TotalCount 2
```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-05-28 08:17:12 POST /api/kho-do status=500
2026-05-28 08:20:23 POST /api/thue-do status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
(Get-Content logs/rental.log | Select-String "status=404").Count

```

```text
4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\tong_hop.ps1
```

### Nội dung file logs/tong_hop.txt

```text
Dang tao bao cao...
Hoan thanh!
```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | file:///C:/Users/lequanghao/Downloads/starter-kit/starter-kit/thue-do-cam-trai-website/web/images/logo.png  | network | Sửa đường dẫn logo.png thành logo-campgo.png |
| 2 | file:///C:/Users/lequanghao/Downloads/starter-kit/starter-kit/thue-do-cam-trai-website/web/images/logo.png | console | Kiểm tra file app.js và xử lý lỗi theo thông báo |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** Website GreenField gặp lỗi khi kiểm tra chức năng bảng 
- **Expected:** Bảng hiển thị đầy đủ dữ liệu từ hệ thống
- **Actual:** Bảng không hiển thị dữ liệu trên trang web
- **Log:** app.js:18 Uncaught ReferenceError: getElementById is not defined
[NEW] Explain Console errors by using Copilot in Edge: click  to explain an error Learn moreDon’t show again


### Câu tìm kiếm Google

```text
site:stackoverflow.com "THÔNG BÁO LỖI TRONG CONSOLE"
```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_thue_thang_5.xlsx`, không cần ghi vào đây.
