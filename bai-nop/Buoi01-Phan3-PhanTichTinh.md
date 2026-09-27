# BUỔI 1 – PHẦN 3: PHÂN TÍCH TĨNH VỚI ESLINT

- **Họ tên:** Nguyễn Thị Ngọc Thảo
- **MSSV:** 65133282

## 1. Kết quả chạy công cụ

Lệnh: `npm run lint:lab`

| Tổng số problem | Số error | Số warning |
|---|---|---|
| 19 | 16 | 3 |

Ảnh chụp kết quả: <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/bc1694d1-c4f6-4d9e-a3ff-1bc91955821e" />

## 2. Bảng phân tích

Phân loại: **DEFECT** (chắc chắn gây sai/dừng chương trình) · **SMELL** (khó bảo trì, tiềm ẩn rủi ro) · **CHẤP NHẬN** (không cần sửa, giải thích lý do)

| STT | Dòng | Rule | Vấn đề (giải thích bằng lời của bạn) | Hậu quả nếu chạy chương trình | Phân loại | Cách sửa |
|---|---|---|---|---|---|---|
| 1 | 9| no-unused-vars|Biến fs được khai báo nhưng không sử dụng. |Không làm chương trình dừng nhưng tạo mã thừa, khó bảo trì. |SMELL |Xóa const fs = require('fs'); nếu không sử dụng. |
| 2 |14 | no-dupe-keys| Object SHIPPING_CONFIG có 2 key noiThanh.|Giá trị noiThanh: 20000 bị key phía sau noiThanh: 25000 ghi đè. |DEFECT |Xóa key trùng và giữ lại giá trị đúng. |
| 3 |21 |no-unused-vars | Biến total được tính nhưng không được sử dụng đúng cách.|Logic tính tổng có thể bị bỏ phí; mã khó bảo trì. |SMELL |Sử dụng total khi return hoặc xóa biến nếu không cần. |
| 4 | 23|no-undef |	totl chưa được khai báo, có khả năng là lỗi gõ nhầm total. | Khi chạy tới dòng này có thể xảy ra ReferenceError.|DEFECT | Đổi totl thành total.|
| 5 |28 |eqeqeq | Sử dụng == thay vì ===.|JavaScript có thể tự chuyển kiểu dữ liệu, dẫn đến kết quả so sánh ngoài ý muốn. |SMELL | Sử dụng ===.|
| 6 | 31| no-cond-assign|Dùng phép gán = trong điều kiện if. |Gán qty = 100, làm thay đổi giá trị và điều kiện hoạt động sai. |DEFECT |Dùng phép so sánh, ví dụ qty === 100. |
| 7 |31 |no-constant-condition | Điều kiện trở thành điều kiện hằng do phép gán ở dòng 31.| Điều kiện có thể luôn đúng, làm sai luồng chương trình.|DEFECT |Sửa điều kiện để kiểm tra đúng giá trị qty. |
| 8 |39 | valid-typeof| typeof price === 'numbr' sử dụng chuỗi không hợp lệ.|Điều kiện kiểm tra kiểu dữ liệu không hoạt động như mong muốn. | DEFECT|Sửa thành typeof price === 'number'. |
| 9 | 42|use-isnan | So sánh trực tiếp price === NaN.| NaN không thể được kiểm tra bằng phép so sánh thông thường.| DEFECT|Dùng Number.isNaN(price). |
| 10 | 54|no-fallthrough | no-fallthrough|Khi vào noi-thanh, chương trình chạy tiếp sang ngoai-thanh, làm sai phí vận chuyển. | DEFECT| Thêm break sau fee = SHIPPING_CONFIG.noiThanh.|
| 11 | 68|no-dupe-else-if |Hai điều kiện if kiểm tra cùng customer.type === 'VIP'. | Nhánh giảm 10% không bao giờ được thực hiện.|DEFECT |Sửa điều kiện thứ hai theo đúng loại khách hàng cần giảm 10%, hoặc xóa nhánh nếu không có yêu cầu. |
| 12 | 72|no-unreachable | console.log() nằm sau return 0, nên không bao giờ chạy.|Đoạn code không thể thực thi. |DEFECT |Đưa console.log() lên trước return hoặc xóa nếu không cần. |
| 13 | 72|no-console| Sử dụng console.log() trong code.| Có thể tạo log không mong muốn trong môi trường thực tế.| SMELL| Xóa log debug hoặc dùng cơ chế logging phù hợp.| 
| 14 |77 |no-unsafe-negation | Viết !productId in cart.|Toán tử ! được áp dụng trước in, dẫn đến logic kiểm tra sai. |DEFECT |Viết !(productId in cart). |
| 15 | 87| no-unused-vars|Biến e trong catch không được sử dụng. | Không làm chương trình dừng nhưng tạo biến thừa.|SMELL |Bỏ biến nếu không cần hoặc sử dụng e để xử lý lỗi. |
| 16 |87 | no-empty| Khối catch rỗng.|Lỗi xảy ra có thể bị bỏ qua hoàn toàn, gây khó khăn khi phát hiện lỗi. |SMELL |Xử lý lỗi hoặc ghi log phù hợp. |
| 17 | 92|complexity |Hàm xepHangKhachHang có complexity = 9, vượt giới hạn 5. |Hàm nhiều nhánh, khó đọc, khó kiểm thử và bảo trì. | SMELL|Tách hàm hoặc đơn giản hóa các điều kiện. |
| 18 | 116|no-console | Có console.log() trong hàm tinhTongDon.|Có thể tạo log không cần thiết khi chạy chương trình. |SMELL |Xóa console.log() hoặc sử dụng logging phù hợp. |
| 19 |121 | no-unused-vars|Tham số kyHieu được khai báo nhưng không sử dụng. | Code thừa, gây khó hiểu cho người bảo trì.|SMELL |Xóa tham số hoặc sử dụng nó để định dạng ký hiệu tiền tệ. |

## 3. Sau khi sửa

Kết quả `npm run lint:lab` sau khi sửa (ảnh chụp hoặc dán kết quả):
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/090e78ef-073a-4d88-a11a-389f9b56a190" />

## 4. Lỗi logic ESLint không phát hiện được

| STT | Hàm | Mô tả lỗi | Căn cứ (chú thích hàm / mục SRS) | Vì sao ESLint không phát hiện được? |
|---|---|---|---|---|
| 1 |function tinhTongDon | Tính tổng đơn hàng sai| Tổng tiền phải trả = tạm tính - giảm giá + phí vận chuyển| Vì biểu thức hoàn toàn hợp lệ về cú pháp JavaScript. ESLint không biết quy tắc nghiệp vụ của hệ thống rằng phí vận chuyển phải được cộng vào tổng tiền.|
| 2 | function kiemTraSoLuong(qty)|Kiểm tra số lượng sản phẩm không đúng yêu cầu | Số lượng hợp lệ: số nguyên từ 1 đến 99 | ESLint có thể phát hiện lỗi cú pháp/code smell như == hoặc phép gán trong điều kiện, nhưng không biết yêu cầu nghiệp vụ rằng số lượng hợp lệ phải nằm trong khoảng 1–99.|

## 5. (Không bắt buộc) Nhận xét về phân tích tĩnh trong trình soạn thảo

