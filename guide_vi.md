# 📘 Hướng Dẫn Thiết Lập Key Cho Bot Giao Dịch MEXC

---

## 🔑 1. Thiết Lập API Key và Secret Key

Để bắt đầu giao dịch tự động với bot, bạn cần lấy **API Key** và **Secret Key** từ MEXC. Làm theo các bước dưới đây:

1. Truy cập vào trang **MEXC**:  
   👉 [https://www.mexc.com/](https://www.mexc.com/)

2. Đăng nhập vào tài khoản của bạn.

3. Sau khi đăng nhập, vào mục **User Center** bằng cách nhấp vào tên người dùng của bạn ở góc trên bên phải.

4. Trong menu **User Center**, chọn **API Management**.

5. Chọn **Create API Key** để bắt đầu tạo API Key mới.

6. Bạn sẽ cần thiết lập các quyền cho API Key:
   - Chọn các quyền cần thiết (**Trading**, **Account Info**, etc.).
   - **Bật xác thực 2 bước (2FA)** qua Google Authenticator hoặc SMS để bảo mật tài khoản.
   - Nếu muốn, bạn có thể **hạn chế địa chỉ IP** để tăng cường bảo mật.

7. Sau khi tạo key, bạn sẽ nhận được **API Key** và **Secret Key**. Hãy lưu lại chúng, vì **Secret Key** sẽ chỉ hiển thị một lần.


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

## Lưu ý:
u_id cookie sẽ có thời gian giới hạn, hãy đảm bảo kiểm tra thông tin thường xuyên để có thể cập nhật key mới qua [BOT](https://t.me/sot_mexc_global_auto_trade_bot)


---

## 🔒 3. Bảo Mật

- Luôn **bật xác thực 2 bước (2FA)** qua Google Authenticator hoặc SMS.
- 
---

## 🧩 4. Nhập Key Vào Ứng Dụng

Nhập lần lượt các thông tin theo thứ tự sau:

1. `API Key`
2. `Secret Key`
3. `u_id Key`
4. Nhấn **OK** để hoàn tất

➡️ Sau khi nhập xong, bot sẽ kết nối với tài khoản của bạn một cách an toàn.

---

## ⚙️ 5. Mô Tả Hoạt Động Của Bot - Version 2.0

- Bot hoạt động theo chiến lược đã lập trình sẵn (Scalping khung 1, 3, 5 phút).
- Volume giao dịch mặc định nên để khoảng **0.08% tài khoản**.
- Mặc định sau khi đăng ký, **volume cơ sở là 0.2 USDT** mỗi lệnh. (Mỗi lệnh có hệ số vol khác nhau, vol cơ sở sẽ nhân với hệ số ra vol thực tế khi vào lệnh)
- Tổng khối lượng giao dịch đồng thời tối đa ~8-12% tài khoản.

📢 **Kênh tín hiệu chính thức:**  
🔗 [Telegram - MEXC Scalping Bypass](https://t.me/sotcforme)

---
