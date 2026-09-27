# BIÊN BẢN REVIEW TÀI LIỆU YÊU CẦU

## Thông tin chung

| Mục | Nội dung |
|---|---|
| Họ tên |  Nguyễn Thị Ngọc Thảo |
| MSSV |  65133282 |
| Tài liệu được review | MSN-SRS – Đặc tả yêu cầu MiniShop NTU, phiên bản 1.0 | 
| Loại review | Review theo checklist (cá nhân) |
| Ngày |  27/9/2026 |
| Bước 1 – Khởi động | từ 19g00 đến 19g05 |
| Bước 2 – Đọc lần 1 (theo trình tự) | từ 19g05 đến 19g35 |
| Bước 3 – Đọc lần 2 (đối chiếu chéo) | từ 19g35 đến 19g55 |
| Bước 4 – Hoàn thiện biên bản | từ 19g55 đến 20g15 |

## Danh sách lỗi

Loại lỗi: MƠ HỒ · MÂU THUẪN · THIẾU · KHÔNG KIỂM THỬ ĐƯỢC · KHÔNG KHẢ THI · THUẬT NGỮ · SAI SỐ LIỆU
Mức độ: Major · Minor

| STT | Vị trí (mã yêu cầu / mục) | Mô tả lỗi | Mã checklist | Loại lỗi | Mức độ | Tìm thấy ở lần đọc (1/2) | Đề xuất sửa |
|---|---|---|---|---|---|---|---|
| 1 | Mục 2.2 và FR-01.3| Mục 2.2 quy định người dùng phải từ 18 tuổi trở lên, nhưng FR-01.3 lại quy định người dùng phải trên 18 tuổi. Hai yêu cầu mâu thuẫn tại trường hợp 18 tuổi|C2|MÂU THUẪN|Major|2|Xác nhận lại điều kiện tuổi là >= 18 hay > 18 và thống nhất trong SRS |
| 2 |FR-01.4 | Yêu cầu quy định mật khẩu phải “đủ mạnh” nhưng không nêu tiêu chí cụ thể để xác định mật khẩu mạnh|C4|KHÔNG KIỂM THỬ ĐƯỢC|Minor|1|Bổ sung tiêu chí cụ thể về độ dài, chữ hoa, chữ thường, chữ số, ký tự đặc biệt,... |
| 3 | FR-02.3 và NFR-03|FR-02.3 quy định tài khoản bị khóa sau 3 lần đăng nhập sai liên tiếp, trong khi NFR-03 quy định sau 5 lần|C2|MÂU THUẪN|Major|2|Xác nhận số lần chính xác là 3 hay 5 và thống nhất hai yêu cầu |
| 4 |FR-03.4|Cụm “một số lượng sản phẩm hợp lý” không quy định số lượng cụ thể nên không xác định được giới hạn để kiểm thử|C1|MƠ HỒ|Minor|1|Quy định số lượng sản phẩm tối đa cụ thể trong giỏ hàng |
| 5 | FR-04.1 và Phụ lục A – Ví dụ 2|FR-04.1 quy định phí vận chuyển ngoại thành là 35.000đ, nhưng Phụ lục A ghi trường hợp ngoại thành có phí 30.000đ|C2|MÂU THUẪN|Major|2|Xác nhận phí ngoại thành là 30.000đ hay 35.000đ và sửa cho thống nhất |
| 6 | FR-04.2 và Phụ lục A – Ví dụ 3|FR-04.2 quy định đơn hàng trên 500.000đ được miễn phí, nhưng Phụ lục A cho trường hợp đúng 500.000đ được miễn phí|C2|MÂU THUẪN|Major|2|Xác nhận ngưỡng miễn phí là > 500.000đ hay >= 500.000đ |
| 7 | FR-05.3|Quy định “khách hàng thân thiết được giảm 5%” nhưng chưa định nghĩa điều kiện để xác định khách hàng thân thiết|C3|THIẾU|Major|1|Bổ sung tiêu chí/điều kiện xác định khách hàng thân thiết |
| 8 | NFR-02|Yêu cầu hệ thống “hoạt động 100% thời gian và không bao giờ xảy ra lỗi” là yêu cầu tuyệt đối, không có tiêu chí đo lường cụ thể|C4|KHÔNG KHẢ THI|Minor|1|Chuyển thành tiêu chí đo được, ví dụ tỷ lệ uptime và thời gian downtime tối đa |

## Thống kê

| Loại lỗi | Số lượng |
|---|---|
| MƠ HỒ | 1|
| MÂU THUẪN | 4|
| THIẾU | 1|
| KHÔNG KIỂM THỬ ĐƯỢC | 1|
| KHÔNG KHẢ THI | 1 |
| THUẬT NGỮ | 0|
| SAI SỐ LIỆU | 0 |
| **Tổng** | 8 |
| Trong đó Major / Minor | 5 / 3 |

## Các điểm cần hỏi lại BA (em chưa chắc ý đồ tác giả)

1. Điều kiện tuổi đăng ký chính xác là từ 18 tuổi trở lên hay trên 18 tuổi?
2. Tài khoản bị khóa sau 3 lần hay 5 lần đăng nhập sai liên tiếp?
3. Phí vận chuyển ngoại thành chính xác là 30.000đ hay 35.000đ?
4. Đơn hàng có tạm tính đúng 500.000đ có được miễn phí vận chuyển hay chỉ đơn hàng trên 500.000đ?
5. Tiêu chí cụ thể để xác định mật khẩu đủ mạnh là gì?
6. “Một số lượng sản phẩm hợp lý” cụ thể là bao nhiêu?
7. Điều kiện để xác định khách hàng thân thiết là gì?
8. NFR-02 “hoạt động 100% thời gian và không bao giờ xảy ra lỗi” cần được đo lường theo tiêu chí nào?

## Kết luận review

Đánh dấu một lựa chọn:

- [ ] **Chấp nhận** – tài liệu dùng được ngay
- [ ] **Chấp nhận có điều kiện** – dùng được sau khi sửa các lỗi đã nêu, không cần review lại
- [X] **Review lại** – phải sửa và tổ chức review lần 2

Lý do: Tài liệu còn nhiều lỗi mâu thuẫn giữa các yêu cầu và một số yêu cầu chưa đủ rõ ràng để kiểm thử. Các lỗi liên quan đến điều kiện tuổi, số lần khóa tài khoản và phí vận chuyển có thể dẫn đến việc các bên hiểu và triển khai yêu cầu khác nhau. Vì vậy cần BA xác nhận, sửa SRS và thực hiện review lại.

## Tự đánh giá (3–5 câu)

Qua lần review này, em phát hiện được một số lỗi mâu thuẫn giữa các phần khác nhau của SRS. Đặc biệt, việc đối chiếu giữa yêu cầu chính và các ví dụ trong Phụ lục giúp em phát hiện các vấn đề về giá trị biên và dữ liệu không thống nhất. Em cũng nhận ra rằng một yêu cầu muốn kiểm thử được cần có điều kiện và tiêu chí cụ thể, tránh các từ ngữ như “đủ mạnh” hoặc “hợp lý”. Lần sau em sẽ chú ý đối chiếu chéo giữa các yêu cầu thay vì chỉ đọc từng yêu cầu riêng lẻ.
