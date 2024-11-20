### Bản thiết kế bài toán Bank Statement Analyzer (UML)
![Diagram](https://www.planttext.com/api/plantuml/png/X5F1IiD04BtdA-ROGli3HKgnM11Q4Li44G_ZPesBcvsmEocA-6KU_2H_mKcxRRS9afmsRz-yUVCc-Vt-cGL6ptLfCsKn1DXuT04L6tBmcO4yOrYpDww075b79AVwsMh0ach7vombh8Bynmw5L6-Gw8pE9KRjwc4iZp3J_Z0OPbzPT3fVtzzfpBMFFW6M9l15qd0ANWW941QUIgaxE55Xkp1M9wANwDww4S31hKAhQYiUDyHeRpsz65vI28DkQqxQ7gOnZa4rywQUhjsA7B_sI1mJAXloWqO__7VgGlE6ggltIhkW-xoDTgwOgfjMvdkLjOZayZgFY-cTz1Zb2iqfF_dAs2ZOaicXb8kuWSSdG5_igzBOn-Dfijy9r397TWAQwvG-0IMRPk7icZRNxKL6ZJRSLQeyAHqQxamcbn_Z3m00__y30000)
### Giải thích cách tác giả sử dụng để giải quyết các vấn đề về: SRP, cohesion, coupling
 #### 1. Single Responsibility Principle (SRP)
 * Định nghĩa SRP: SRP yêu cầu rằng mỗi lớp chỉ nên có một lý do duy nhất để thay đổi, tức là mỗi lớp chỉ nên chịu trách nhiệm cho một chức năng cụ thể.

 * Cách giải quyết:

- Lớp Transaction: Chịu trách nhiệm duy nhất cho việc lưu trữ thông tin về một giao dịch (ngày, số tiền, và danh mục). Không có logic nào khác trong lớp này.
- Lớp CSVReader: Chịu trách nhiệm đọc dữ liệu từ file CSV và tạo danh sách các đối tượng Transaction. Nó không thực hiện bất kỳ xử lý nào khác ngoài việc đọc và phân tích dữ liệu.
- Lớp BankTransaction: Tập trung vào các phép toán và tính toán liên quan đến danh sách giao dịch. Nó chỉ thực hiện các chức năng như tính tổng lợi nhuận, đếm giao dịch, và tìm kiếm danh mục chi tiêu.
#### 2. Cohesion
 * Định nghĩa: Cohesion đề cập đến mức độ mà các thành phần của một lớp hoặc module liên kết với nhau. Lớp có tính cohesion cao có nghĩa là tất cả các phương thức và thuộc tính của nó đều liên quan chặt chẽ đến nhau.

 * Cách giải quyết:

Mỗi lớp trong chương trình đều có tính cohesion cao:
- Transaction: Tất cả các thuộc tính và phương thức đều liên quan đến thông tin giao dịch.
- CSVReader: Tất cả các phương thức đều liên quan đến việc đọc và xử lý file CSV, không có phương thức nào không liên quan đến chức năng này.
BankTransaction: Các phương thức trong lớp này đều tập trung vào việc xử lý các giao dịch, từ đó giúp tăng tính cohesion.
#### 3. Coupling
 * Định nghĩa: Coupling đề cập đến mức độ phụ thuộc giữa các lớp. Coupling thấp là đặc điểm mong muốn vì nó cho phép các lớp hoạt động độc lập hơn.

 * Cách giải quyết:

Sử dụng interface hoặc lớp độc lập: Các lớp không phụ thuộc trực tiếp vào nhau. Ví dụ, BankTransaction sử dụng danh sách Transaction mà không cần biết rõ cách thức Transaction được tạo ra. Điều này cho phép dễ dàng thay đổi cách thức tạo ra giao dịch mà không ảnh hưởng đến các phép toán tài chính.
Tách biệt chức năng: Việc sử dụng lớp CSVReader để đọc dữ liệu làm giảm sự phụ thuộc giữa các lớp chính (BankTransaction và Main). Nếu cần thay đổi cách đọc file, chỉ cần thay đổi lớp CSVReader mà không ảnh hưởng đến các lớp khác.
