# 📊 System Monitor Script

This Python script monitors your system's **CPU**, **memory**, and **disk usage**. If any of these metrics exceed predefined thresholds, it sends **email** and **Slack alerts**.

---

## 🚀 Features
- Real-time system resource monitoring
- Configurable thresholds for CPU, memory, and disk usage
- Sends alerts via **Email** and **Slack**
- Logs all activities to `logs/system_monitor.log`

---

## ⚙️ Configuration
All configurations are hardcoded in `system_monitor.py`:

### 1️⃣ **Thresholds**
```python
self.thresholds = {
    'cpu_percent': 80,       # CPU usage threshold
    'memory_percent': 85,    # Memory usage threshold
    'disk_percent': 90       # Disk usage threshold
}
```

### 2️⃣ **Email Configuration**
```python
self.email_config = {
    'smtp_server': 'smtp.gmail.com',
    'smtp_port': 465,
    'username': 'your-email@gmail.com',       # Your Gmail address
    'password': 'your-app-password',          # App password (not your Gmail password)
    'from_email': 'your-email@gmail.com',     # Sender email
    'to_email': 'recipient-email@example.com' # Recipient email
}
```

### 3️⃣ **Slack Webhook**
```python
self.slack_webhook = 'https://hooks.slack.com/services/YOUR/WEBHOOK/URL'
```

---

## 📧 Setting Up Gmail SMTP
1. **Enable 2-Step Verification** in your Google Account.
2. **Generate an App Password:**
   - Go to [Google App Passwords](https://myaccount.google.com/apppasswords)
   - Select **Mail** and **Other (Custom name)** (e.g., "System Monitor Script")
   - Copy the generated password and use it as `password` in the script.

---

## ⚡ Running the Script
```bash
python system_monitor.py
```

The script will:
- Check system health
- Send email and Slack alerts if any thresholds are breached
- Log activities in `logs/system_monitor.log`

---

## 📂 Log Files
Logs are saved in the `logs/` directory:
```bash
logs/system_monitor.log
```

---

## 🛠️ Dependencies
- `psutil`
- `requests`

### Install dependencies:
```bash
pip install psutil requests
```

---

## 📜 License
This project is licensed under the MIT License.

