# API Flow: E-wallet

## Auth
| Method | Endpoint       | Auth | Description          |
|--------|----------------|------|----------------------|
| POST   | /api/register  | No   | Đăng ký              |
| POST   | /api/login     | No   | Đăng nhập → token    |
| POST   | /api/logout    | Yes  | Đăng xuất            |

## Wallet
| Method | Endpoint             | Auth | Description           |
|--------|----------------------|------|-----------------------|
| GET    | /api/wallet/balance  | Yes  | Xem số dư             |
| POST   | /api/wallet/topup    | Yes  | Nạp tiền              |
| POST   | /api/wallet/transfer | Yes  | Chuyển tiền           |
| GET    | /api/transactions    | Yes  | Lịch sử giao dịch     |

## Request / Response Example

### POST /api/wallet/transfer
**Request**
```json
{
  "to_user_id": 5,
  "amount": 100000,
  "note": "Trả tiền cà phê"
}
```

**Response 200**
```json
{
  "message": "Transfer successful",
  "balance": 400000,
  "transaction_id": "TXN-20240512-001"
}
```

**Response 422**
```json
{
  "message": "Insufficient balance"
}
```