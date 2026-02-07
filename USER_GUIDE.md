# 📚 PingLogger v1.1 - Complete User Guide

**PingLogger** is a specialized network monitoring utility designed for IT professionals. It allows simultaneous monitoring of multiple IP addresses, logs uptime/downtime, and ensures continuous operation with auto-resume capabilities.

---

## 🚀 Detailed Features

### 1. ⚡ Auto-Resume System
* **How it works:** The app constantly saves its state (Running/Stopped, Single/Multi Mode, Target IPs).
* **Scenario:** If your PC restarts due to a power cut or update, simply launch PingLogger (or let it auto-start). It will detect the improper shutdown and immediately resume pinging the last targets without you clicking anything.

### 2. 🧹 Deep Cleaning (Smart Maintenance)
* **Startup Cleaner:** It scans the Windows Startup folder and removes broken or old shortcuts (e.g., `PingLogger v1.0.lnk`, `Shortcut to PingLogger.lnk`) to prevent duplicate startup entries.
* **Ghost Killer:** If an old instance of the app is stuck in the background (hidden), the "Kill Background Instances" button forcefully clears it using PID filtering.

### 3. 🛡️ App Auto-Close (Safety Guard)
* **Purpose:** To prevent the app from running indefinitely on forgotten maintenance PCs.
* **Settings:** You can set it to close after `1 Week`, `1 Month`, or `1 Year`.
* **Default:** `Never` (But includes a 90-Day safety hard-limit).
* **Action:** When the limit is reached, the app stops logging, removes itself from Startup, and closes completely.

---

## 📖 How to Use

### 🟢 Single Target Mode
*Best for: Detailed monitoring of one critical device (Server, Router).*

1.  **Enter IP:** Type the IP address (e.g., `192.168.1.1`) or Domain.
2.  **Nickname:** Add a label like "Main Server" (Optional).
3.  **Action:** Click **[ START LOGGING ]**.
    * **Left Side:** Controls become disabled to prevent accidental changes.
    * **Right Side:** A large Command Prompt style window shows live ping replies.
4.  **History:** Your typed IP is automatically saved. To delete an old IP, select it and click the small **[ ✖ ]** button.

### 🟣 Multi-Target Mode
*Best for: Monitoring a whole network segment or multiple branches.*

1.  **Activate:** Check the box **☑ Enable Multi-Target Mode**.
2.  **Add Devices:**
    * Enter IP -> Click **[ ADD + ]**.
    * Repeat this for up to 5 devices.
3.  **Start:** Click the purple **[ START MULTIPLE LOGGING ]** button.
4.  **Monitoring:**
    * The list will show **Status** (RUNNING/STOP) and **Reply Time** (e.g., `4ms` or `RTO`).
    * **Live Comparison:** Hold `Ctrl` key and click on multiple IPs in the list. The right panel will split to show live logs for all selected devices.

---

## ⚙️ Settings Menu

### 🔹 General
* **Ping Interval:** Time between pings in milliseconds (Default: `1000` = 1 sec).
* **Auto-Scroll:** Keeps the log view focused on the newest entry.
* **Beep on Fail:** Plays a sound alert if a Request Timed Out (RTO) occurs.
* **Minimize to Tray:** Hides the app from the taskbar when minimized (runs in system tray).

### 🔹 Startup & Automation
* **ENABLE Startup:** Adds the app to Windows Startup folder.
* **Start Minimized:** App launches silently in the background on boot.
* **Resume Last Session:** **(Recommended ON)** Enables the crash-recovery/auto-resume feature.

### 🔹 System Health
* **Kill Background Instances:** Manually triggers the cleanup logic for processes and shortcuts.
* **Auto-Close Timer:** Select a duration after which the app should self-terminate.

---

## 📂 Understanding Logs
Logs are saved in the `PingLogs` folder next to the application.

* **File Naming:** `IP-Address_Date_Nickname.txt`
* **Content:**
    * `[10:00:01] Reply from 8.8.8.8: bytes=32 time=12ms TTL=115`
    * `[10:05:00] [SYSTEM] Windows was OFF for: 0 Hours 5 Minutes` (Auto-detected downtime).

---

### ❓ FAQ

**Q: My Taskbar icon is missing?**
A: This is usually a Windows Cache issue. Try moving the `.exe` to a new folder or renaming it. The app has code to force the icon, so a reboot usually fixes it.

**Q: Why is "Kill Background" not deleting my shortcut?**
A: The cleaner specifically looks for shortcuts containing the word **"PingLogger"**. Ensure your shortcut is named correctly (e.g., `PingLogger.lnk`).

**Q: How do I update?**
A: Simply download the new `.exe` from GitHub Releases and replace the old one. Your `settings.json` and logs will remain safe.
