# Tài liệu kiểm thử phần mềm: Bank Transaction App

## Mục lục
1. [Giới thiệu](#giới-thiệu)
2. [Mô tả chức năng](#mô-tả-chức-năng)
3. [Test cases](#test-cases)
   - [Kiểm thử chức năng phân tích file CSV](#kiểm-thử-chức-năng-phân-tích-file-csv)
   - [Tính tổng lợi nhuận và lỗ](#tính-tổng-lợi-nhuận-và-lỗ)
   - [Tính tổng tiền giao dịch theo tháng](#tính-tổng-tiền-giao-dịch-theo-tháng)
   - [Tính tổng tiền giao dịch theo loại](#tính-tổng-tiền-giao-dịch-theo-loại)
4. [Kết luận](#kết-luận)

## Giới thiệu
Ứng dụng Bank Transaction App cho phép người dùng quản lý và phân tích các giao dịch ngân hàng từ file CSV hoặc JSON. Các chức năng chính bao gồm tính toán lợi nhuận, thống kê giao dịch và tạo báo cáo.

## Mô tả chức năng
- **Phân tích file CSV**: Đọc và lưu trữ các giao dịch từ file CSV.
- **Tính tổng lợi nhuận và lỗ**: Tính toán tổng số tiền giao dịch.
- **Đếm số giao dịch trong tháng**: Đếm số giao dịch trong một tháng cụ thể.
- **Lấy danh sách top N chi tiêu**: Trả về danh sách các giao dịch chi tiêu nhiều nhất.
- **Lấy danh mục chi tiêu nhiều nhất**: Tìm kiếm danh mục chi tiêu có tổng chi tiêu lớn nhất.

## Test cases

### Kiểm thử chức năng phân tích file CSV
1. **Test Case 1**: Tải file CSV hợp lệ
   - **Input**: `"valid_transactions.csv"`
   - **Expected Output**: Danh sách giao dịch không rỗng với các trường hợp hợp lệ.

2. **Test Case 2**: Tải file CSV không hợp lệ
   - **Input**: `"invalid_transactions.csv"`
   - **Expected Output**: Thông báo lỗi hoặc ngoại lệ được ném ra.

3. **Test Case 3**: Tải file CSV rỗng
   - **Input**: `"empty_transactions.csv"`
   - **Expected Output**: Danh sách giao dịch rỗng.

4. **Test Case 4**: Kiểm tra định dạng dữ liệu
   - **Input**: `"mismatched_format_transactions.csv"`
   - **Expected Output**: Thông báo lỗi cho các dòng có định dạng không hợp lệ.

5. **Test Case 5**: Kiểm tra file CSV với các trường dữ liệu thiếu
   - **Input**: `"missing_fields_transactions.csv"`
   - **Expected Output**: Thông báo lỗi cho các giao dịch thiếu trường bắt buộc.

### Tính tổng lợi nhuận và lỗ
1. **Test Case 1**: Tính tổng lợi nhuận và lỗ từ file hợp lệ
   - **Input**: `"valid_transactions.csv"`
   - **Expected Output**: Tổng lợi nhuận và lỗ chính xác.

2. **Test Case 2**: Tính tổng lợi nhuận và lỗ từ file rỗng
   - **Input**: `"empty_transactions.csv"`
   - **Expected Output**: Tổng lợi nhuận và lỗ = 0.

3. **Test Case 3**: Tính tổng lợi nhuận và lỗ với dữ liệu không hợp lệ
   - **Input**: `"invalid_transactions.csv"`
   - **Expected Output**: Thông báo lỗi hoặc ngoại lệ.

### Tính tổng tiền giao dịch theo tháng
1. **Test Case 1**: Tính tổng tiền giao dịch theo tháng từ file hợp lệ
   - **Input**: `"month_transactions.csv"`
   - **Expected Output**: Tổng tiền giao dịch cho từng tháng chính xác.

2. **Test Case 2**: Tính tổng tiền giao dịch theo tháng từ file rỗng
   - **Input**: `"empty_transactions.csv"`
   - **Expected Output**: Tổng tiền giao dịch theo tháng = 0 cho tất cả các tháng.

3. **Test Case 3**: Tính tổng tiền giao dịch theo tháng với dữ liệu không hợp lệ
   - **Input**: `"invalid_month_transactions.csv"`
   - **Expected Output**: Thông báo lỗi hoặc ngoại lệ.

### Tính tổng tiền giao dịch theo loại
1. **Test Case 1**: Tính tổng tiền giao dịch theo loại từ file hợp lệ
   - **Input**: `"type_transactions.csv"`
   - **Expected Output**: Tổng tiền giao dịch cho từng loại chính xác.

2. **Test Case 2**: Tính tổng tiền giao dịch theo loại từ file rỗng
   - **Input**: `"empty_transactions.csv"`
   - **Expected Output**: Tổng tiền giao dịch theo loại = 0 cho tất cả các loại.

3. **Test Case 3**: Tính tổng tiền giao dịch theo loại với dữ liệu không hợp lệ
   - **Input**: `"invalid_type_transactions.csv"`
   - **Expected Output**: Thông báo lỗi hoặc ngoại lệ.

## Kết luận
Tài liệu này cung cấp hướng dẫn chi tiết để kiểm thử các chức năng của ứng dụng Bank Transaction App. Các test cases đã được xác định rõ ràng để đảm bảo tính chính xác và độ tin cậy của ứng dụng. Việc thực hiện các test case này sẽ giúp phát hiện lỗi và cải thiện chất lượng sản phẩm.
