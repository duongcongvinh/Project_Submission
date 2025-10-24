# 🧪 EPROJECT – API TEST RESULTS (POSTMAN)

📁 **Ảnh test Postman** nằm trong thư mục:
🛍️ E-Commerce Microservices System
📖 Giới thiệu
Dự án mô phỏng hệ thống bán hàng online được xây dựng theo kiến trúc Microservices, triển khai bằng Docker Compose.

Chức năng chính:

Đăng ký, đăng nhập tài khoản.
Quản lý sản phẩm.
Đặt hàng và xem danh sách đơn hàng.
Mục tiêu là phân tách hệ thống thành các dịch vụ nhỏ giúp dễ mở rộng, bảo trì và triển khai độc lập.

🧩 Kiến trúc hệ thống
Hệ thống gồm 4 dịch vụ chính và 2 thành phần hỗ trợ:

Thành phần	Chức năng chính
API Gateway	Tiếp nhận request từ client, định tuyến đến các service khác
Auth Service	Đăng ký, đăng nhập, xác thực JWT
Product Service	Thêm sản phẩm, xem sản phẩm
Order Service	Tạo và xử lý đơn hàng
RabbitMQ	Truyền thông điệp giữa các service (Order ↔ Product)
MongoDB	Lưu trữ dữ liệu riêng cho từng service
⚙️ Công nghệ sử dụng
Node.js / Express.js
MongoDB
RabbitMQ
JWT (JSON Web Token)
Docker & Docker Compose
Postman (dùng để kiểm thử API)
###Các mẫu thiết kế được dùng

Microservices: Tách nhỏ hệ thống để dễ bảo trì.
API Gateway: Gom các service về một cổng gọi chung.
Message Queue (RabbitMQ): Truyền dữ liệu giữa các service.
Repository: Tách phần làm việc với database.
🔗 Cách các service giao tiếp
Client → API Gateway (HTTP)

API Gateway → Auth/Product/Order (HTTP nội bộ Docker)

Order ↔ Product (qua RabbitMQ)

Mỗi service có MongoDB riêng, không dùng chung database.

🚀 Cách chạy dự án
1.Tại thư mục gốc dự án, chạy lệnh:
docker-compose up --build

2. Kiểm thử nhanh (Postman)
Đăng ký: POST http://localhost:3003/auth/register
Đăng nhập: POST http://localhost:3003/auth/login
Thêm sản phẩm: POST http://localhost:3003/products/api/products
Đặt hàng: POST http://localhost:3003/products/api/products/buy
Lấy sản phẩm theo id: GET http://localhost:3003/products/api/products/
---

## 🔐 AUTH SERVICE (`/auth`)
### 🧩 Đăng ký tài khoản
**✅ register.png** – Tạo tài khoản mới thành công.  
<img width="1920" height="1080" alt="register" src="https://github.com/user-attachments/assets/a69aa8cc-cae6-44ab-954c-c7aea8dcf166" />
🧩 Đăng nhập hệ thống
✅ login.png – Đăng nhập thành công, trả về token JWT hợp lệ
<img width="1920" height="1080" alt="login" src="https://github.com/user-attachments/assets/425f88e1-e0a5-463b-bfb2-e0798e20cc76" />
🛍 PRODUCT SERVICE (/products)
🧩 Thêm sản phẩm mới
✅ create_product.png – Tạo sản phẩm mới thành công.
<img width="1918" height="1077" alt="createProduct" src="https://github.com/user-attachments/assets/79d59544-b082-4e2f-9adb-1a3d2a13c559" />
❌ get_product_failtoken.png – Thiếu hoặc sai token → 401 Unauthorized
<img width="1918" height="1073" alt="createProduct_failToken" src="https://github.com/user-attachments/assets/d028ce54-ff73-42fd-b3fa-604b15e6b926" />
🧩 Lấy danh sách sản phẩm
✅ get_product.png – Trả về danh sách sản phẩm thành công.
<img width="1918" height="1078" alt="getProduct" src="https://github.com/user-attachments/assets/6f13abd1-c2e8-459e-9fff-7bdc5281aeba" />
📦 ORDER SERVICE (/orders)
🧩 Tạo đơn hàng mới
✅ create_order.png – Đặt hàng thành công, trả về thông tin đơn hàng.
<img width="1918" height="1078" alt="createOrder" src="https://github.com/user-attachments/assets/7c8628f4-7a5f-4424-9250-5ba843415970" />
📊 DASHBOARD / TOKEN CHECK
✅ dashboard_cussess.png – Token hợp lệ → truy cập Dashboard thành công.
<img width="1918" height="1078" alt="dashboard_success" src="https://github.com/user-attachments/assets/da0da001-60b0-441c-8969-a151b50c2038" />
❌ Dashboard_NoToken.png – Không gửi token → 401 Unauthorized.
<img width="1918" height="1078" alt="dashboard_denied" src="https://github.com/user-attachments/assets/73c4bf8a-92b9-438e-81fb-2ed3c1634cd1" />
❌ Dashboard_InvalidToken.png – Token sai → 403 Forbidden.
<img width="1918" height="1078" alt="dashboard_invalid" src="https://github.com/user-attachments/assets/23865bba-783c-4d19-ab19-b46ebe8ff51c" />
✍️ Người thực hiện: Dương Công Vĩnh-22681711 

