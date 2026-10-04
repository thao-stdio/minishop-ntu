# BUỔI 2 – CHUYỂN TRẠNG THÁI: ĐĂNG NHẬP VÀ KHÓA TÀI KHOẢN

- **Họ tên:** Nguyễn Thị Ngọc Thảo
- **MSSV:** 65133282
- **Yêu cầu liên quan:** FR-02.1, FR-02.2, FR-02.3, FR-02.4

## 1. Trạng thái và sự kiện

| Ký hiệu | Trạng thái | Mô tả |
|---|---|---|
| S1 | Hoạt động, bộ đếm sai 0–2 | Có thể đăng nhập; ghi nhận số lần sai liên tiếp |
| S2 | Bị khóa | Đã sai 3 lần liên tiếp; khóa 15 phút |
| S3 | Đã đăng nhập | Xác thực thành công; bộ đếm được đặt về 0 |

| Ký hiệu | Sự kiện |
|---|---|
| E1 | Nhập đúng email và mật khẩu |
| E2 | Nhập sai email hoặc mật khẩu |
| E3 | Hết thời gian khóa 15 phút |

## 2. Sơ đồ chuyển trạng thái

```mermaid
stateDiagram-v2
    [*] --> S1
    S1: S1 - Hoạt động
    S2: S2 - Bị khóa 15 phút
    S3: S3 - Đăng nhập thành công
    S1 --> S3: E1 / bộ đếm = 0
    S1 --> S1: E2 lần 1 hoặc 2 / báo Sai email hoặc mật khẩu
    S1 --> S2: E2 lần 3 / khóa 15 phút
    S2 --> S2: E1 hoặc E2 / từ chối, báo tài khoản bị khóa
    S2 --> S1: E3 / mở khóa, bộ đếm = 0
    S3 --> S1: Đăng xuất
