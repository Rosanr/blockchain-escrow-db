# 🪙 Blockchain Escrow Database (PostgreSQL)

Đây là **cơ sở dữ liệu nội bộ** cho đồ án *"Ứng dụng Blockchain trong thương mại điện tử"*  
– được dùng để lưu thông tin người dùng, sản phẩm, đơn hàng và các giao dịch escrow.  

---

## 🧩 1. Cấu trúc dự án

| File | Mô tả |
|------|-------|
| `db_blockchain.sql` | Toàn bộ **schema + dữ liệu mẫu** được export từ pgAdmin |
| `erd_ecommerce_escrow.svg` *(nếu có)* | Sơ đồ ERD thể hiện các bảng và mối quan hệ |
| `README.md` | Hướng dẫn khởi tạo database và sử dụng |

---

## 🗃️ 2. Các bảng trong cơ sở dữ liệu

1. **users** – Thông tin người dùng (buyer, seller, admin)  
2. **products** – Sản phẩm được người bán đăng  
3. **orders** – Đơn hàng giao dịch giữa buyer & seller  
4. **payments** – Giao dịch thanh toán (escrow)  
5. **deliveries** – Thông tin giao hàng  
6. **oracle_messages** – Giao tiếp giữa hệ thống nội bộ và blockchain  
7. **audit_logs** – Nhật ký hoạt động (log)

---

## ⚙️ 3. Cách khởi tạo cơ sở dữ liệu (chạy trên máy cá nhân)

### 🔹 Bước 1: Cài PostgreSQL
Tải tại [https://www.postgresql.org/download/](https://www.postgresql.org/download/)

### 🔹 Bước 2: Tạo database trống
Mở pgAdmin hoặc Terminal, chạy:
```sql
CREATE DATABASE escrow_db;
### 🔹 Bước 3: Import file .sql

Cách 1 – Dùng pgAdmin

Chuột phải vào database escrow_db → Query Tool

Nhấn biểu tượng thư mục 🗂 → chọn file db_blockchain.sql

Nhấn Execute (⚡) để chạy.

Cách 2 – Dùng psql (command line)

psql -U postgres -d escrow_db -f db_blockchain.sql
