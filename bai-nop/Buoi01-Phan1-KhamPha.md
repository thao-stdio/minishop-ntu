# BUỔI 1 – PHẦN 1: CÀI ĐẶT VÀ KHÁM PHÁ HỆ THỐNG

- **Họ tên:** Nguyễn Thị Ngọc Thảo
- **MSSV:** 65133282
- **Lớp:** 65.CNTT-2

## 1. Môi trường

| Mục | Kết quả |
|---|---|
| Phiên bản Node.js (`node -v`) | | v24.21.0
| Phiên bản npm (`npm -v`) | | 11.19.0
| Phiên bản Git (`git --version`) | | git version 2.55.0.windows.5
| Hệ điều hành | | windows 10
| Kết quả `npm run lint` (số error / warning) | | 16 errors / 3 warnings

Ảnh chụp màn hình (chèn ảnh hoặc đặt file ảnh trong thư mục `bai-nop/hinh/` rồi dẫn link):

- Trang web MiniShop NTU: <img width="1366" height="768" alt="Screenshot (547)" src="https://github.com/user-attachments/assets/7871123d-20c8-41de-b480-fa2c97a430be" />

- Terminal đang chạy server: <img width="1366" height="768" alt="Screenshot (548)" src="https://github.com/user-attachments/assets/637fb9bf-34fc-4d43-8718-6d315489ce98" />

## 2. Kịch bản 1 – Đăng ký với tuổi 17

| Câu hỏi | Trả lời |
|---|---|
| Kết quả thực tế | | Đăng ký thành công
| Kết quả mong đợi (theo SRS, ghi rõ mục) | | FR-01.3	Người dùng phải trên 18 tuổi mới được đăng ký
| Có phải failure không? Vì sao? | | có, vì theo yêu cầu phải đủ 18 tuổi mới được đăng ký, trường hợp trên người dùng khai báo mới 17 nhưng vẫn đăng ký được
| Defect nằm ở đâu (file, số dòng, đoạn mã) | | registration.js, 18, } else if (ageNumber < 17 || ageNumber > 100) {
| Error nào của con người có thể đã gây ra defect này? | | Lập trình viên hiểu hoặc triển khai sai yêu cầu về độ tuổi tối thiểu, viết điều kiện ageNumber < 17 thay vì ageNumber < 18, dẫn đến việc cho phép người dùng 17 tuổi đăng ký.

## 3. Kịch bản 2 – Đơn hàng 500.000đ, nội thành

| Câu hỏi | Trả lời |
|---|---|
| Tạm tính | | 500.000đ
| Phí vận chuyển hệ thống tính | | 20.000đ
| Theo FR-04.2, phí đúng phải là | | Đơn hàng có tạm tính trên 500.000đ được miễn phí vận chuyển --> 20.000đ
| Theo Phụ lục A, phí đúng phải là | | 0đ
| Hệ thống đúng hay sai? Có kết luận được không? Vì sao? | | Chưa thể kết luận hệ thống đúng hay sai chỉ dựa trên hai tài liệu, vì FR-04.2 và Phụ lục A mâu thuẫn nhau tại trường hợp tạm tính đúng 500.000đ
| Defect (nếu có) nằm ở đâu: mã nguồn hay tài liệu? | | Chưa thể kết luận

## 4. Kịch bản 3 – Tự khám phá

| Mục | Nội dung |
|---|---|
| Chức năng | | Đăng nhập và khóa tài khoản khi nhập sai mật khẩu nhiều lần
| Các bước thực hiện | 1. <br> 2. <br> 3. |
| Dữ liệu sử dụng | |
| Kết quả mong đợi (căn cứ: mục nào của SRS) | |
| Kết quả thực tế | |
| Nhận định (failure? mức độ?) | |
