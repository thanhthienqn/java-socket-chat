=> Class cho server
ServerGUI.java: sử dụng để thao tác với server như bật, tắt server. Ngoài ra còn hiển thị các thông tin server như: IP, Port, số lượng người kết nối, các protocol mà client gửi lên.
ServerCore.java: Đây là class để quản lí server, gồm đầy đủ thông tin, chức năng chính của server:
-Tạo một SocketServer.
-Quản lí danh sách các user đang online
-Tạo một thread là WaitForConnect để xử lý các request kết nối từ user. Có thể là yêu cầu dăng nhập, thoát ứng dụng, lấy thông tin user đang online. Nếu đăng nhập thành công, trả về cho client danh sách user đang online, nếu không sẽ trả về một protocol từ chối đăng nhập.

=> Class cho client
-MainGUI.java: GUI class để hiển thị danh sách user khác đang online, bắt sự kiện gửi yêu cầu chat của user.

-ChatGUI.java: Xử lí việc chat, gửi nhận File giữa hai user. Hiển thị nội dung chat giữa hai user.

-ClientServer.java: Tạo và quản lí ServerSocket của mỗi user. Xử lí request chat gửi đến từ user khác.

-Client.java: Quản lí thông tin hiện tại của user. Nó sẽ tạo một thread để liên tục gửi request tới server để cập nhật danh sách user. Ngoài ra nó còn xử lí request chat tới user khác.

=> Các class khác
-DataFile.java: Tạo một đối tượng File để gửi đi.
-Peer.java: Tạo một đối tượng Peer có các thuộc tính: IP, port, name.
-Tags.java: Định nghĩa các protocol được sử dụng trong ứng dụng.
-Encode.java: Định nghĩa các phương thức user đùng để gửi request lên server.
-Dedode.java: Giải mã các phương thức để lấy thông tin user, port hay ip...
