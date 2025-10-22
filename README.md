# 🧪 EPROJECT – API TEST RESULTS (POSTMAN)
📁 **Ảnh test Postman** nằm trong thư mục:

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

