# BUỔI 2 – BẢNG QUYẾT ĐỊNH: PHÍ VẬN CHUYỂN VÀ GIẢM GIÁ

- **Họ tên:** Nguyễn Thị Ngọc Thảo
- **MSSV:** 65133282
- **Yêu cầu liên quan:** FR-04.1, FR-04.2, FR-04.3, FR-05.2, FR-05.3

## 1. Điều kiện và hành động

| Ký hiệu | Điều kiện | Các giá trị |
|---|---|---|
| C1 | Loại thành viên | Thường / VIP |
| C2 | Tạm tính đạt ngưỡng miễn phí? | Dưới 500.000đ / Từ 500.000đ trở lên |
| C3 | Khu vực | Nội thành / Ngoại thành |

| Ký hiệu | Hành động |
|---|---|
| A1 | Phí vận chuyển |
| A2 | Giảm giá |
| A3 | Tổng tiền = tạm tính − giảm giá + phí |

Số luật của bảng đầy đủ = 2³ = **8**.

## 2. Bảng quyết định đầy đủ

| | L1 | L2 | L3 | L4 | L5 | L6 | L7 | L8 |
|---|---|---|---|---|---|---|---|---|
| **C1** | Thường | Thường | Thường | Thường | VIP | VIP | VIP | VIP |
| **C2** | Dưới | Dưới | Đạt | Đạt | Dưới | Dưới | Đạt | Đạt |
| **C3** | Nội | Ngoại | Nội | Ngoại | Nội | Ngoại | Nội | Ngoại |
| **A1** | 20.000 | 35.000 | 0 | 0 | 0 | 0 | 0 | 0 |
| **A2** | 0 | 0 | 0 | 0 | 5% | 5% | 5% | 5% |
| **A3** | subtotal+20k | subtotal+35k | subtotal | subtotal | 95% subtotal | 95% subtotal | 95% subtotal | 95% subtotal |

## 3. Bảng rút gọn

| | R1 | R2 | R3 | R4 |
|---|---|---|---|---|
| **C1** | VIP | Thường | Thường | Thường |
| **C2** | – | Dưới | Dưới | Đạt |
| **C3** | – | Nội | Ngoại | – |
| **A1** | 0 | 20.000 | 35.000 | 0 |
| **A2** | 5% | 0 | 0 | 0 |
| **A3** | 95% subtotal | subtotal+20k | subtotal+35k | subtotal |

**Giải thích việc gộp:** L5–L8 gộp thành R1 vì VIP được miễn phí vận chuyển ở mọi khu vực và mọi mức tạm tính, đồng thời được giảm 5%. L3–L4 gộp thành R4 vì khi tạm tính đạt ngưỡng, phí vận chuyển bằng 0 bất kể khu vực. Các luật còn lại giữ riêng do phí nội thành và ngoại thành khác nhau.

## 4. Ánh xạ sang ca kiểm thử

| Luật rút gọn | Mã ca trong Buoi02-TestCase.csv |
|---|---|
| R1 | TC-65133282-19 |
| R2 | TC-65133282-20 |
| R3 | TC-65133282-21 |
| R4 | TC-65133282-22 |
| Ca biên 500.000đ | TC-65133282-22, TC-65133282-23 |

**Ghi chú về biên:** Giá các sản phẩm đều là bội số của 50.000đ. Có thể tạo tạm tính 450.000đ, 500.000đ và 550.000đ; không thể tạo 499.999đ hoặc 500.001đ nếu chỉ cộng số lượng nguyên của các sản phẩm có giá đã cho. Ngưỡng được xét trên tạm tính trước giảm giá (FR-05.3).
