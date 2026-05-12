# User Stories: E-wallet

## Epic: Quản lý ví

| ID   | As a... | I want to...               | So that...                  | Priority |
|------|---------|----------------------------|-----------------------------|----------|
| US01 | User    | Xem số dư ví               | Biết còn bao nhiêu tiền     | High     |
| US02 | User    | Nạp tiền qua VNPay         | Tăng số dư để giao dịch     | High     |
| US03 | User    | Chuyển tiền cho người khác | Thanh toán / gửi tiền nhanh | High     |
| US04 | User    | Xem lịch sử giao dịch      | Theo dõi chi tiêu           | Medium   |
| US05 | User    | Nhận notification          | Biết tiền vào/ra kịp thời   | Medium   |
| US06 | Admin   | Xem toàn bộ giao dịch      | Kiểm soát và audit          | High     |

## Acceptance Criteria

### US03 — Transfer

**Scenario 1: Thành công**
- Given: User đã đăng nhập, số dư ≥ 10,000đ
- When: Nhập to_user_id hợp lệ, amount ≤ số dư
- Then: Trừ tiền sender, cộng tiền receiver, tạo transaction record, trả về 200

**Scenario 2: Không đủ số dư**
- Given: User đã đăng nhập
- When: Nhập amount > số dư
- Then: Trả về 422 Insufficient balance, không thay đổi số dư