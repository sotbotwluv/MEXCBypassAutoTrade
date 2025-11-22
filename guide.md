This guide will walk you through connecting to your Linux VPS (Virtual Private Server) from a Windows machine, setting up the necessary environment (Python, Node.js), and starting your application using PM2.

**Assumptions:** You already have the VPS created and have its **IP address**, **username**, and **password**.

-----

## 1\. 🛠️ Windows Preparation

You need to install a tool to easily transfer your source code to the VPS.

### 1.1. Install **SSHFS-Win** for File Transfer

**SSHFS-Win** allows you to "mount" a folder on your VPS as a network drive on Windows, enabling easy drag-and-drop file transfers.

1.  Open **Command Prompt** (CMD) or **PowerShell** with **Administrator** rights (right-click the icon and select "Run as administrator").
2.  Type the following command and press **Enter**:
    ```bash
    winget install SSHFS-Win.SSHFS-Win
    ```
      * **Note:** If `winget` is unavailable, you can download the installer directly from the SSHFS-Win website.
3.  After installation, it is recommended to **restart your computer** to ensure the tool integrates correctly.

### 1.2. Open the **Terminal** Window

You will use a command-line interface to connect to the VPS. Use the standard **Terminal** or **Command Prompt** application on Windows 10/11.

-----

## 2\. 🔌 Connect to the VPS via SSH

Now you will use the **SSH** command to log into your VPS remotely.

### 2.1. Log in to the VPS

1.  Open **Terminal** or **Command Prompt**.
2.  Type the following command, replacing the bracketed information with your VPS details:
    ```bash
    ssh [your_username]@[your_vps_ip_address]
    ```
      * **Example:** `ssh user123@192.168.1.100`
3.  The first time you connect, the system will ask if you want to save the security key (it will show a **"yes/no"** prompt). Type **`yes`** and press **Enter**.
4.  The system will then prompt you to enter the **password**. Type your VPS password (it **will not be visible** as you type, this is normal).
5.  If successful, the prompt will change (usually to `[your_username]@[machine_name]:~$`), confirming you are now inside your VPS.

### 2.2. Using SSHFS-Win (Optional)

To transfer files easily:

1.  Run the **SSHFS-Win Manager** application (if installed).
2.  Enter your connection details (IP, username) and choose a drive letter (e.g., `Z:`) to map the VPS folder to your Windows machine.
3.  You can now drag and drop your source code files into this new drive in **File Explorer**.

-----

## 3\. 🐍 Set up the Environment on the VPS

Once inside the VPS, follow these steps to prepare your application's environment.

### 3.1. Navigate to the Source Code Directory

Use the **`cd`** command to move into the directory where you placed your source code (e.g., if you put your code in a folder named `my-app` in your home directory):

```bash
cd my-app
```

### 3.2. Update the System

Always update your system packages first:

```bash
sudo apt update && sudo apt upgrade -y
```

  * This command uses **`sudo`** (administrator rights) and may require you to enter your VPS password again.

### 3.3. Install Python Environment

Assuming you have a **`requirements.txt`** file listing your Python libraries:

1.  **Install Python (if missing) and pip:**
    ```bash
    sudo apt install python3 python3-pip -y
    ```
2.  **Install Libraries from requirements.txt:**
    ```bash
    pip3 install -r requirements.txt
    ```

### 3.4. Install NodeJS and PM2

You need **Node.js** to install and run the process manager tool **PM2**.

1.  **Add Node.js 18 Repository:**
    ```bash
    curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
    ```
2.  **Install Node.js:**
    ```bash
    sudo apt install -y nodejs
    ```
3.  **Install PM2 (Application Process Manager):**
    PM2 keeps your application running in the background, even after you close the terminal window.
    ```bash
    sudo npm install pm2@latest -g
    ```

-----

## 4\. 🚀 Start the Application with PM2

Use **PM2** to run your main code file (**`main.py`**).

1.  **Start the Bot:**
    Type this exact command:
    ```bash
    pm2 start -n bot main.py --interpreter=python3
    ```
      * **`-n bot`**: Names the process **bot** for easier management.
      * **`main.py`**: The name of your main code file.
      * **`--interpreter=python3`**: Instructs PM2 to use **Python 3** to execute the file.
2.  **Check Status:**
    To confirm your bot is running:
    ```bash
    pm2 status
    ```
    If the status shows **`online`**, your bot is running successfully\!

-----

## 5\. ✅ Basic Management Commands

You can use these commands whenever you need to manage your application:

  * **View application logs:**
    ```bash
    pm2 logs bot
    ```
  * **Stop the application:**
    ```bash
    pm2 stop bot
    ```
  * **Restart the application:**
    ```bash
    pm2 restart bot
    ```
  * **Save PM2 configuration** (to make the bot automatically restart when the VPS reboots):
    ```bash
    pm2 save
    ```

When you are done, simply type **`exit`** and press **Enter** to close the SSH session. Your application will continue to run on the VPS in the background.

Would you like a brief explanation of how to use the SSHFS-Win Manager to connect and transfer files?
