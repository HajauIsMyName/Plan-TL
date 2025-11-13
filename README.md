# 🧠 Giới thiệu về SQL

## 💡 SQL là gì?

**SQL (Structured Query Language)** – _Ngôn ngữ truy vấn có cấu trúc_ – là ngôn ngữ tiêu chuẩn dùng để **truy cập**, **quản lý** và **thao tác dữ liệu** trong cơ sở dữ liệu.

SQL cho phép:

- 🔍 **Truy vấn dữ liệu**
- ➕ **Chèn**, ✏️ **sửa**, ❌ **xóa** bản ghi
- 🧱 **Tạo cấu trúc dữ liệu** và 🔐 **phân quyền truy cập**

> ✅ SQL được công nhận là tiêu chuẩn bởi **ANSI (1986)** và **ISO (1987)**.

## ⚙️ SQL có thể làm gì?

SQL có thể:

- Truy xuất, thêm, sửa, xóa dữ liệu
- Tạo mới cơ sở dữ liệu và bảng
- Định nghĩa **stored procedures**, **views**
- Quản lý quyền truy cập người dùng

## 🗄️ RDBMS là gì?

**RDBMS (Relational Database Management System)** – Hệ quản trị cơ sở dữ liệu quan hệ – là nền tảng của SQL.

> Ví dụ: **MySQL**, **PostgreSQL**, **Oracle**, **SQL Server**, **Access**,...

Dữ liệu trong RDBMS được lưu trong **bảng (table)** gồm:

- **Cột (columns):** loại thông tin (vd: `CustomerName`, `City`)
- **Hàng (rows):** từng bản ghi dữ liệu

### 🧩 Ví dụ:

```sql
SELECT * FROM Customers;
```

---

# ⚙️ Cú pháp của SQL

## 🧱 Câu lệnh SQL là gì?

- Mọi thao tác đều thông qua **câu lệnh SQL**.
- Một câu lệnh gồm **từ khóa mô tả hành động**.

### 🔍 Ví dụ:

```sql
SELECT * FROM Customers;
```

## 🗂️ Bảng trong cơ sở dữ liệu

Một **database** chứa **nhiều bảng**.
Ví dụ bảng `Customers`:

| CustomerID | CustomerName                       | ContactName        | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | ------------------ | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders       | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

> 📊 Gồm **5 hàng (records)** và **7 cột (fields)**.

## 📝 Lưu ý

> SQL **không phân biệt chữ hoa hay chữ thường**

```sql
select * from Customers;
-- tương đương với
SELECT * FROM Customers;
```

## 🔚 Dấu chấm phẩy trong SQL

- Một số hệ quản trị yêu cầu dấu `;` ở cuối mỗi câu lệnh.
- Dấu `;` giúp **tách nhiều truy vấn** trong cùng phiên.

```sql
SELECT * FROM Customers;
SELECT * FROM Orders;
```

## 🚀 Các lệnh SQL quan trọng nhất

| Lệnh              | Chức năng                  |
| ----------------- | -------------------------- |
| `SELECT`          | Truy xuất dữ liệu          |
| `UPDATE`          | Cập nhật dữ liệu           |
| `DELETE`          | Xóa dữ liệu                |
| `INSERT INTO`     | Thêm bản ghi mới           |
| `CREATE DATABASE` | Tạo cơ sở dữ liệu          |
| `ALTER DATABASE`  | Sửa cấu trúc cơ sở dữ liệu |
| `CREATE TABLE`    | Tạo bảng mới               |
| `ALTER TABLE`     | Sửa cấu trúc bảng          |
| `DROP TABLE`      | Xóa bảng                   |
| `CREATE INDEX`    | Tạo chỉ mục tìm kiếm       |
| `DROP INDEX`      | Xóa chỉ mục                |

---

# 🧾 SQL SELECT

## 🔹 Câu lệnh SELECT

Dùng để **chọn dữ liệu** từ bảng:

```sql
SELECT CustomerName, City FROM Customers;
```

### Cú pháp:

```sql
SELECT column1, column2, ...
FROM table_name;
```

> `column1`, `column2` là các cột cần lấy; `table_name` là tên bảng.

---

## 🔹 Chọn tất cả các cột

Dùng ký hiệu `*` để lấy toàn bộ dữ liệu:

```sql
SELECT * FROM Customers;
```

# 🧩 SQL SELECT DISTINCT

## 🔹 Lọc giá trị duy nhất

`SELECT DISTINCT` trả về **các giá trị không trùng lặp**.

```sql
SELECT DISTINCT Country FROM Customers;
```

> Ví dụ trên chỉ liệt kê **các quốc gia khác nhau** trong bảng.

## 🔹 Cú pháp

```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

## 🔹 Không dùng DISTINCT

```sql
SELECT Country FROM Customers;
```

> Trả về tất cả giá trị, kể cả trùng lặp.

## 🔹 Đếm giá trị duy nhất

Dùng `COUNT(DISTINCT column)`:

```sql
SELECT COUNT(DISTINCT Country) FROM Customers;
```
