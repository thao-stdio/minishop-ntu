# BUỔI 2 – BẢNG PHÂN HOẠCH TƯƠNG ĐƯƠNG VÀ GIÁ TRỊ BIÊN

- **Họ tên:** Nguyễn Thị Ngọc Thảo
- **MSSV:** 65133282

## 1. Tuổi khi đăng ký (FR-01.3)

| Lớp tương đương | Hợp lệ? | Khoảng giá trị | Giá trị đại diện | Mã ca |
|---|---|---|---|---|
| Dưới giới hạn | Không | tuổi < 18 | 17 | TC-65133282-01 |
| Trong giới hạn | Có | 18 ≤ tuổi ≤ 100 | 25 | TC-65133282-03 |
| Trên giới hạn | Không | tuổi > 100 | 101 | TC-65133282-05 |

**Giá trị biên:** 17 (dưới), 18 (đúng biên), 100 (đúng biên), 101 (trên).

## 2. Mật khẩu khi đăng ký (FR-01.4)

| Lớp tương đương | Hợp lệ? | Mô tả | Giá trị đại diện | Mã ca |
|---|---|---|---|---|
| Độ dài dưới 8 | Không | 7 ký tự, có chữ và số | Abc1234 | TC-65133282-06 |
| Độ dài 8–20, đủ chữ và số | Có | Hai điều kiện đều đạt | Abc12345 | TC-65133282-07 |
| Độ dài 8–20, chỉ chữ | Không | Thiếu chữ số | Abcdefgh | TC-65133282-10 |
| Độ dài 8–20, chỉ số | Không | Thiếu chữ cái | 12345678 | TC-65133282-11 |
| Độ dài trên 20 | Không | 21 ký tự | Abcdefghijklmnop12345 | TC-65133282-09 |

**Giá trị biên:** 7, 8, 20, 21 ký tự. Kiểm tra thành phần ký tự độc lập với độ dài.

## 3. Số lượng một sản phẩm trong giỏ (FR-03.2)

| Lớp tương đương | Hợp lệ? | Khoảng giá trị | Giá trị đại diện | Mã ca |
|---|---|---|---|---|
| Dưới 1 | Không | n < 1 | 0 | TC-65133282-12 |
| Trong khoảng | Có | 1 ≤ n ≤ 99 | 1 | TC-65133282-13 |
| Trên 99 | Không | n > 99 | 100 | TC-65133282-15 |

**Giá trị biên:** 0, 1, 99, 100.

## 4. Tổng số lượng sản phẩm trong giỏ (FR-03.4)

| Lớp tương đương | Hợp lệ? | Khoảng giá trị | Giá trị đại diện | Mã ca |
|---|---|---|---|---|
| Không vượt giới hạn | Có | tổng ≤ 200 | 199 và 200 | TC-65133282-16, TC-65133282-17 |
| Vượt giới hạn | Không | tổng > 200 | 201 | TC-65133282-18 |

**Giá trị biên:** 199, 200, 201. Do mỗi dòng tối đa 99, cần kết hợp ít nhất ba sản phẩm để tạo tổng gần 200.

## Ghi chú

SRS quy định miền số hợp lệ nhưng chưa nêu rõ thông báo cụ thể khi nhập chữ, để trống hoặc số thập phân vào trường tuổi/số lượng. Không tự đặt thông báo; cần xác nhận với BA. Các ca trên tập trung vào miền giá trị đã được đặc tả.
