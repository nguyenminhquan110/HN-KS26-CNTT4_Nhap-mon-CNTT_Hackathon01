# BÀI LÀM – HACKATHON 01

- **Mã đề:** 03
- **Họ tên:** Nguyễn Minh Quân  
- **Lớp:** HN-KS26-CNTT4
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** macOS

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
- Hiển thị đường dẫn tuyệt đối của thư mục hiện tại: pwd
- Liệt kê nội dung, gồm cả file ẩn: ls
- Di chuyển các file lich_tap.txt vào docs, các file logo vào media:
+ mv lich_tap.txt docs
+ mv logo_phong_gym.PNG media
- Sao chép logo từ media vào backup: cp media/logo_phong_gym.PNG backup 
- Xoá file .tmp tại thư mục gốc; không xoá file khác: rm temp_103.tmp
- Dùng đường dẫn tương đối vào logs, liệt kê nội dung rồi quay lại thư mục gốc: 
+ cd logs
+ ls
+cd ..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
.		.DS_Store	backup		data		logs
..		.env		bai_lam.md	docs		media

./backup:
.			..			logo_phong_gym.PNG

./data:
.			..			dang_ky_thang_11.xlsx

./docs:
.		..		lich_tap.txt

./logs:
.		..		member.log

./media:
.			..			logo_phong_gym.PNG
```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
- cat logs/member.log
- grep "ERROR" logs/member.log
- grep "ERROR" logs/member.log >> logs/daily_report.txt

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2025-11-28 07:26:18 [ERROR] Khong tim thay trang /lich-tap (404)
2025-11-28 07:29:18 [ERROR] Het thoi gian cho (timeout)
```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [X] Heading 1: tên dự án
- [X] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [X] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [X] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [X] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [X] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# Script: auto_report.sh
# Tac gia: NGUYEN_MINH_QUAN
# Ngay tao: 15/10/2026
 
echo "Dang loc log..."
 
echo "=== BAO CAO LOI ===" > logs/auto_report.sh
cat logs/member.log | grep "ERROR" >> logs/auto_report.sh
echo "Hoan thanh!"


```

### Kết quả hiển thị

```text
2025-11-28 07:26:18 [ERROR] Khong tim thay trang /lich-tap (404)
2025-11-28 07:29:18 [ERROR] Het thoi gian cho (timeout)
2025-11-28 07:32:18 [ERROR] Khong tim thay trang /lich-tap (404)
2025-11-28 07:35:18 [ERROR] Het thoi gian cho (timeout)
2025-11-28 07:38:18 [ERROR] Het thoi gian cho (timeout)
2025-11-28 07:47:18 [ERROR] Khong doc duoc the tu hoi vien
2025-11-28 08:05:18 [ERROR] Khong tim thay trang /lich-tap (404)


```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
- grep -c "ERROR" logs/member.log

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
7
```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
# Ghi lần lượt các lệnh đã chạy, mỗi lệnh một dòng (xoá dòng này)
-echo "===TONG HOP LOG===" >> logs/tong_hop.txt
- grep "WARNING" logs/member.log >> logs/tong_hop.txt
- grep "ERROR" logs/member.log >> logs/tong_hop.txt
```

### Nội dung file logs/tong_hop.txt

```text
===TONG HOP LOG===
2025-11-28 07:14:18 [WARNING] Phong tap dong nguoi
2025-11-28 07:56:18 [WARNING] Phong tap dong nguoi
2025-11-28 07:59:18 [WARNING] The tu sap het han
2025-11-28 07:26:18 [ERROR] Khong tim thay trang /lich-tap (404)
2025-11-28 07:29:18 [ERROR] Het thoi gian cho (timeout)
2025-11-28 07:32:18 [ERROR] Khong tim thay trang /lich-tap (404)
2025-11-28 07:35:18 [ERROR] Het thoi gian cho (timeout)
2025-11-28 07:38:18 [ERROR] Het thoi gian cho (timeout)
2025-11-28 07:47:18 [ERROR] Khong doc duoc the tu hoi vien
2025-11-28 08:05:18 [ERROR] Khong tim thay trang /lich-tap (404)
```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/dang_ky_thang_11.xlsx`, không cần ghi vào đây.
