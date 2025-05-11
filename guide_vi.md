# 📘 Hướng Dẫn Thiết Lập Key Cho Bot Giao Dịch MEXC

---

## 🔑 1. Thiết Lập API Key và Secret Key

Để lấy **API Key** và **Secret Key** từ sàn MEXC, bạn làm theo các bước sau:

1. Truy cập ứng dụng **TabTrader** hoặc trang chính thức của **MEXC**.
2. Làm theo hướng dẫn chi tiết tại liên kết:  
   👉 [https://tabtrader.com/helpcenter/android/api-keys/mexc](https://tabtrader.com/helpcenter/android/api-keys/mexc)
3. Khi tạo key:
   - Chọn quyền cần thiết (**nên chọn đọc & giao dịch**).
   - Có thể **hạn chế IP** để tăng cường bảo mật.
   - **Bắt buộc bật xác thực hai bước (2FA)** qua Google Authenticator hoặc SMS.
4. Sao chép **API Key** và **Secret Key** để nhập vào bot.

---

## 🍪 2. Lấy `u_id` Key (Cookie đăng nhập từ trình duyệt)

`u_id` là định danh người dùng nội bộ từ cookie đăng nhập, KHÔNG phải token bảo mật cao.  
Để lấy `u_id`:

1. Đăng nhập tài khoản MEXC trên trình duyệt.
2. Nhấn `F12` hoặc chuột phải chọn **Inspect** để mở **Developer Tools**.
3. Vào tab **Application** hoặc **Storage**.
4. Mở **Cookies** → chọn domain của **MEXC**.
5. Tìm cookie có tên là `u_id`.
6. Sao chép giá trị bắt đầu bằng `"WEB..."` và sử dụng làm `u_id key`.

### 🔐 Về mặt an toàn

- `u_id` chỉ là **User ID hash**, **không phải token xác thực mạnh**.
- Trong trường hợp chỉ lộ `u_id` hoặc `uc_token`, thì **không có nguy cơ nghiêm trọng** nếu **không đi kèm**:
  - `access_token`
  - `auth_token`
  - `jwt_token`
  - `session_id` (bảo mật)

✅ Do đó, việc sử dụng `u_id` là **tương đối an toàn** cho bot client-side.

---

## 🔒 3. Bảo Mật & Miễn Trừ Trách Nhiệm

- Luôn **bật xác thực 2 bước (2FA)** qua Google Authenticator hoặc SMS.
- Đội ngũ phát triển **không chịu trách nhiệm** nếu người dùng bị mất tài sản do không bảo mật key đúng cách.

---

## 🧩 4. Nhập Key Vào Ứng Dụng

Nhập lần lượt các thông tin theo thứ tự sau:

1. `API Key`
2. `Secret Key`
3. `u_id Key`
4. Nhấn **OK** để hoàn tất

➡️ Sau khi nhập xong, bot sẽ kết nối với tài khoản của bạn một cách an toàn.

---

## ⚙️ 5. Mô Tả Hoạt Động Của Bot

- Bot hoạt động theo chiến lược đã lập trình sẵn (Scalping khung 1 phút).
- Volume giao dịch mặc định nên để khoảng **0.1% tài khoản**.
- Trong bản thử nghiệm, **volume cơ sở là 0.2 USDT** mỗi lệnh.
- Tổng khối lượng giao dịch đồng thời tối đa ~3-5% tài khoản.
- Hãy **đảm bảo 0.2 USDT tương đương ~0.1% tài khoản của bạn** để tối ưu quản lý vốn.

📢 **Kênh tín hiệu chính thức:**  
🔗 [Telegram - MEXC Scalping Bypass](https://t.me/mexcscalpingbypass)

---
