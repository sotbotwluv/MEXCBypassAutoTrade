# 📘 MEXC Trading Bot Key Setup Guide

---

## 🔑 1. Setting Up API Key and Secret Key

To obtain your **API Key** and **Secret Key** from MEXC, follow these steps:

1. Open the **TabTrader** app or visit the official **MEXC** website.
2. Follow the detailed instructions here:  
   👉 [https://tabtrader.com/helpcenter/android/api-keys/mexc](https://tabtrader.com/helpcenter/android/api-keys/mexc)
3. When creating your API key:
   - Select the required permissions (**Read & Trade** is recommended).
   - You can **restrict IP access** to enhance security.
   - **Two-Factor Authentication (2FA)** via Google Authenticator or SMS is **mandatory**.
4. Copy your **API Key** and **Secret Key** and enter them into the bot.

---

## 🍪 2. Obtaining `u_id` Key (Login Cookie from Browser)

The `u_id` is a user identifier from your browser's login session, **not a secure authentication token**.  
To obtain it:

1. Log into your MEXC account via a web browser.
2. Press `F12` or right-click → **Inspect** to open **Developer Tools**.
3. Go to the **Application** or **Storage** tab.
4. Under **Cookies**, select the **MEXC domain**.
5. Find the cookie named `u_id`.
6. Copy its value (should start with `"WEB..."`) and use it as your `u_id key`.

### 🔐 Security Note

- `u_id` is only a **User ID hash**, **not a strong authentication token**.
- If only `u_id` or `uc_token` are exposed, there is **no serious risk**, **unless combined** with:
  - `access_token`
  - `auth_token`
  - `jwt_token`
  - `session_id` (secure)

✅ Therefore, using `u_id` is considered **relatively safe** for client-side bots.

---

## 🔒 3. Security & Disclaimer

- Always enable **Two-Factor Authentication (2FA)** via Google Authenticator or SMS to protect your account.
- The development team **takes no responsibility** for any asset loss due to users failing to secure their keys properly.

---

## 🧩 4. Entering Keys into the Bot

Input the following in order:

1. `API Key`
2. `Secret Key`
3. `u_id Key`
4. Click **OK** to complete setup

➡️ Once entered, the bot will securely connect to your MEXC account.

---

## ⚙️ 5. Bot Operation Overview

- The bot runs a predefined strategy (1-minute scalping).
- Recommended trade volume is around **0.1% of your account balance**.
- In testing mode, the **base volume is set to 0.2 USDT** per order.
- Maximum concurrent trade volume is ~3–5% of your account.
- Ensure that **0.2 USDT ≈ 0.1% of your account** for optimal risk management.

📢 **Official Signal Channel:**  
🔗 [Telegram - MEXC Scalping Bypass](https://t.me/mexcscalpingbypass)

---
