# 🏥 Hospital Management System (HMS)

## 🧩 Kiến trúc tổng thể

Hệ thống HMS là một ứng dụng web gồm 3 lớp chính:
- **Frontend**: Giao diện người dùng viết bằng React.
- **Backend**: API xử lý logic nghiệp vụ, sử dụng Java Spring Boot (hiện tại dùng Node.js, có thể thay thế NodeJs runtime bằng JVM runtime nếu chuyển sang Spring Boot).
- **Database**: Lưu trữ dữ liệu với SQL Server.

---

## ⚙️ Thành phần chính

### 🌐 2. Frontend (React)
- **View**: Hiển thị giao diện, nhận dữ liệu từ API và render lại UI.
- **Controller**: Điều phối hành vi, gọi API đến backend.
- Gửi/nhận dữ liệu dưới dạng JSON thông qua các API.

### 🛠 3. Backend (Spring Boot)
Chịu trách nhiệm xử lý logic nghiệp vụ và truy cập dữ liệu:

| Thành phần         | Mô tả chức năng |
|--------------------|------------------|
| `API Endpoint`     | Nhận/gửi request đến frontend |
| `Drug`             | Quản lý thuốc |
| `Consultation`     | Quản lý khám bệnh |
| `Payment`          | Quản lý thanh toán |
| `Account`          | Quản lý người dùng, vai trò |
| `Security`         | Xác thực, phân quyền |
| `Socket`           | Hỗ trợ giao tiếp real-time |
| `Data Access`      | Giao tiếp với cơ sở dữ liệu SQL Server |

### 🗄 4. Database (SQL Server)
- Lưu trữ toàn bộ dữ liệu y tế, bệnh nhân, bác sĩ, hóa đơn, thuốc, ...
- Kết nối với backend qua lớp `Data Access`.

---

## 🔄 Luồng hoạt động

1. Người dùng truy cập website HMS qua trình duyệt.
2. React frontend gửi yêu cầu API đến backend.
3. Backend xử lý nghiệp vụ, truy vấn SQL Server nếu cần thiết.
4. Kết quả được trả về frontend và hiển thị cho người dùng.

---

## 🧱 Ưu điểm kiến trúc
- Phân tách rõ ràng frontend và backend.
- Dễ mở rộng, bảo trì theo từng module (Drug, Account, ...).
- Có thể tích hợp thêm chức năng như socket real-time (trao đổi bác sĩ - bệnh nhân).

---

## 📝 Ghi chú
- Kiến trúc hiện tại sử dụng NodeJS Runtime trong sơ đồ, tuy nhiên có thể thay thế bằng Spring Boot runtime (JVM) nếu bạn triển khai bằng Java.
- Bảo mật có thể tích hợp Spring Security.
- Có thể triển khai với Docker + CI/CD cho môi trường production.

---

## 📌 Công nghệ sử dụng
| Thành phần  | Công nghệ |
|-------------|-----------|
| Frontend    | React + Vite |
| Backend     | Spring Boot (Java 17+) |
| CSDL        | SQL Server |
| Realtime    | WebSocket |
| Auth        | Spring Security |