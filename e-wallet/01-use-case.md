# Use Case: E-wallet

## Actors
- **Guest** — chưa đăng nhập
- **User** — đã có tài khoản
- **Admin** — quản trị hệ thống

## Use Case Diagram

```mermaid
graph TD
    Guest --> UC1[Register]
    Guest --> UC2[Login]
    User  --> UC3[View Balance]
    User  --> UC4[Top Up]
    User  --> UC5[Transfer]
    User  --> UC6[Pay QR]
    User  --> UC7[View History]
    Admin --> UC8[Manage Users]
    Admin --> UC9[View All Transactions]
```