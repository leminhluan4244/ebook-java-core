# Xử lý Form trong Servlet
## Phương thức GET
Phương thức GET là phương thức mặc định để chuyển thông tin từ trình duyệt đến máy chủ web và tạo ra một chuỗi dài xuất hiện trong hộp địa chỉ của trình duyệt của bạn. Không bao giờ sử dụng phương thức GET nếu bạn có mật khẩu hoặc thông tin nhạy cảm khác để chuyển đến máy chủ. Phương thức GET có giới hạn kích thước: chỉ có 1024 ký tự có thể được sử dụng trong một request.

Thông tin này được truyền bằng cách sử dụng tiêu đề QUERY_STRING và sẽ có thể truy cập qua biến môi trường QUERY_STRING và Servlet sẽ xử lý loại yêu cầu này bằng cách sử dụng phương thức doGet().

## Phương thức POST
Một phương thức truyền thông tin phổ biến hơn, đáng tin cậy hơn là phương thức POST. Phương thức này gói thông tin theo cách chính xác giống như phương thức GET, nhưng thay vì gửi nó như một chuỗi văn bản sau một ? (dấu chấm hỏi) trong URL thì phương thức này gửi nó như một thông điệp riêng biệt. Thông báo này đi kèm với chương trình backend dưới dạng đầu vào tiêu chuẩn mà bạn có thể phân tích và sử dụng cho quá trình xử lý của bạn. Servlet xử lý kiểu yêu cầu này sử dụng phương thức doPost ().

## Đọc dữ liệu từ Form trong Servlet
Servlet xử lý dữ liệu từ một Form bằng cách sử dụng các phương thức sau đây tùy thuộc vào tình huống:
- **getParameter()** - Lấy giá trị của một tham số của form.
- **getParameterValues()** - Gọi phương thức này nếu tham số xuất hiện nhiều lần và trả về nhiều giá trị, ví dụ checkbox.
- **getParameterNames()** - Gọi phương thức này nếu bạn muốn có một danh sách đầy đủ của tất cả các tham số trong yêu cầu hiện tại.

