# 🧪 EPROJECT – API TEST RESULTS (POSTMAN)

📁 **Ảnh test Postman** nằm trong thư mục:


---

## 🔐 AUTH SERVICE (`/auth`)
### 🧩 Đăng ký tài khoản
**✅ register.png** – Tạo tài khoản mới thành công.  
![register](public/results/register.png)

**❌ register-exist.png** – Tên tài khoản đã tồn tại, trả về 400.  
![register-exist](public/results/register-exist.png)

---

### 🧩 Đăng nhập hệ thống
**✅ login.png** – Đăng nhập thành công, trả về token JWT.  
![login](public/results/login.png)

**❌ login-fail.png** – Sai mật khẩu, trả về 401 Unauthorized.  
![login-fail](public/results/login-fail.png)

---

## 🛍 PRODUCT SERVICE (`/products`)
### 🧩 Tạo sản phẩm mới
**✅ createProduct.png** – Tạo sản phẩm thành công với đầy đủ thông tin.  
![createProduct](public/results/createProduct.png)

**❌ createProduct-failToken.png** – Thiếu token → 401 Unauthorized.  
![createProduct-failToken](public/results/createProduct-failToken.png)

**❌ createProduct-requiredName.png** – Thiếu trường `name` → 400 Bad Request.  
![createProduct-requiredName](public/results/createProduct-requiredName.png)

**❌ createProduct-requiredPrice.png** – Thiếu trường `price` → 400 Bad Request.  
![createProduct-requiredPrice](public/results/createProduct-requiredPrice.png)

---

### 🧩 Lấy danh sách sản phẩm
**✅ getProducts.png** – Lấy danh sách tất cả sản phẩm thành công.  
![getProducts](public/results/getProducts.png)

**❌ getProducts-failToken.png** – Thiếu token khi gọi API → 401 Unauthorized.  
![getProducts-failToken](public/results/getProducts-failToken.png)

---

## 📦 ORDER SERVICE (`/buy`, `/status/:orderId`)
### 🧩 Tạo đơn hàng
**✅ createOrder.png** – Mua hàng thành công, trả về `orderId` duy nhất.  
![createOrder](public/results/createOrder.png)

**❌ createOrder-failed.png** – Gửi body rỗng hoặc sai định dạng `ids` → lỗi xử lý.  
![createOrder-failed](public/results/createOrder-failed.png)

**❌ createOrder-failToken.png** – Thiếu token → 401 Unauthorized.  
![createOrder-failToken](public/results/createOrder-failToken.png)

**❌ createOrder-serverError.png** – Lỗi máy chủ khi tạo đơn (500).  
![createOrder-serverError](public/results/createOrder-serverError.png)

---

### 🧩 Kiểm tra trạng thái đơn hàng
**❌ getOrderStatus.png** *(chưa có ảnh hoặc đang 404 do ordersMap reset)*  
> Khi test thành công, chụp màn hình trả về JSON trạng thái đơn hàng và thêm vào thư mục `/public/results/`.

---

## 📊 DASHBOARD / TOKEN VALIDATION
**✅ dashboard-success.png** – Truy cập Dashboard hợp lệ với token đúng.  
![dashboard-success](public/results/dashboard-success.png)

**❌ dashboard-denied.png** – Không có token → truy cập bị từ chối.  
![dashboard-denied](public/results/dashboard-denied.png)

**❌ dashboard-invalid.png** – Token không hợp lệ → 403 Forbidden.  
![dashboard-invalid](public/results/dashboard-invalid.png)

---

## 🧾 TỔNG KẾT TEST

| Nhóm API | Pass | Fail | Ghi chú |
|-----------|------|------|---------|
| Auth | ✅ 2 | ⚠️ 1 | Kiểm tra logic đăng ký & đăng nhập ổn định |
| Products | ✅ 2 | ⚠️ 3 | Đã bắt được lỗi thiếu trường & token |
| Orders | ✅ 1 | ⚠️ 3 | Cần cải thiện kiểm tra `ordersMap` |
| Dashboard | ✅ 1 | ⚠️ 2 | Token validation hoạt động chính xác |

---

## 💬 Ghi chú
- Toàn bộ test thực hiện bằng **Postman** trên địa chỉ: http://localhost:3003/

- Các API yêu cầu `Authorization: Bearer <token>` đều dùng token lấy từ endpoint `/auth/login`.
- `ordersMap` lưu tạm trong RAM nên sẽ mất khi restart service → cần gọi GET status **ngay sau khi mua**.
- Ảnh test nằm tại thư mục `public/results/` để minh chứng kết quả từng API.

---

**© 2025 – EProject NodeJS Microservices (Auth / Product / Order)**  
*Thực hiện bởi [Trần Chí Tiến – 22707291]*  

