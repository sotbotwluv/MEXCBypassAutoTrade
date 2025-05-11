# 📘 Guide to Setting Up API Keys for MEXC Trading Bot

---

## 🔑 1. Set Up API Key and Secret Key

To start automatic trading with the bot, you need to get the **API Key** and **Secret Key** from MEXC. Follow the steps below:

1. Visit the **MEXC** website:  
   👉 [https://www.mexc.com/](https://www.mexc.com/)

2. Log in to your account.

3. After logging in, go to the **User Center** by clicking your username in the top right corner.

4. In the **User Center** menu, select **API Management**.

5. Choose **Create API Key** to start creating a new API Key.

6. You will need to configure the permissions for the API Key:
   - Select the required permissions (**Trading**, **Account Info**, etc.).
   - **Enable 2-factor authentication (2FA)** via Google Authenticator or SMS to secure your account.
   - If desired, you can **restrict IP addresses** to enhance security.

7. After creating the key, you will receive the **API Key** and **Secret Key**. Make sure to save them, as the **Secret Key** will only be displayed once.

---

## 🍪 2. Get `u_id` Key (Login Cookie from Browser)

`u_id` is an internal user identifier from the login cookie, NOT a high-security token.  
To get the `u_id`:

1. Log into your MEXC account on your browser.
2. Press `F12` or right-click and select **Inspect** to open **Developer Tools**.
3. Go to the **Application** or **Storage** tab.
4. Open **Cookies** → select the domain for **MEXC**.
5. Find the cookie named `u_id`.
6. Copy the value starting with `"WEB..."` and use it as the `u_id key`.

### 🔐 Regarding Security

- `u_id` is just a **User ID hash**, **not a strong authentication token**.
- If only the `u_id` or `uc_token` is exposed, **there is no serious risk** as long as the following are not exposed:
  - `access_token`
  - `auth_token`
  - `jwt_token`
  - `session_id` (secure)

✅ Therefore, using `u_id` is **relatively safe** for client-side bots.

---

## 🔒 3. Security & Disclaimer

- Always **enable 2-factor authentication (2FA)** via Google Authenticator or SMS.
- The development team **is not responsible** if users lose assets due to improper key security.

---

## 🧩 4. Enter Keys into the Application

Enter the following information in sequence:

1. `API Key`
2. `Secret Key`
3. `u_id Key`
4. Click **OK** to finish

➡️ After entering the information, the bot will securely connect to your account.

---

## ⚙️ 5. Bot Functionality Description

- The bot operates based on a pre-programmed strategy (1-minute scalping).
- The default trade volume should be about **0.1% of the account**.
- In the test version, the **base volume is 0.2 USDT** per trade.
- The total concurrent trading volume should be a maximum of about 3-5% of the account.
- Make sure that **0.2 USDT equals approximately 0.1% of your account balance** to optimize capital management.
- If you want to test the beta version, it's recommended to have between 30-50 USDT.

📢 **Official Signal Channel:**  
🔗 [Telegram - MEXC Scalping Bypass](https://t.me/mexcscalpingbypass)

---
