# 🔍 GitScan – GitHub Repo Keyword & Secret Scanner

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg?logo=python)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![GitHub API](https://img.shields.io/badge/API-GitHub--based-lightgrey?logo=github)](https://docs.github.com/en/rest)

> 🚀 A lightweight GitHub repository scanner that detects secrets, credentials, and patterns from public code using the GitHub API – **without cloning!**  
> 📤 Sends results directly to your Telegram bot.

---

## ✨ Features

- 🔎 **No cloning needed** – Scans via GitHub API
- 🧠 **Custom keyword + extension filters**
- 🧪 **Scans multiple repos in one shot**
- 📄 **Generates structured JSON reports**
- 🤖 **Sends output via Telegram (optional)**
- 🧰 **Easy setup – plug & play**

---

## 🗂️ Directory Structure
```
GitScan/
├── scanner.py # Main script
├── telegram_notify.py # Telegram sending logic
├── utils.py # GitHub API scanning logic
├── repos.txt # List of target GitHub repos
├── keywords.txt # Keywords to match
├── extensions.txt # File types to scan
├── output/
│ └── scan_report.json # Final result
├── requirements.txt
└── README.md
```
---

## 🛠️ Installation

```
git clone https://github.com/youruser/GitScan
cd GitScan
python3 -m venv myenv && source myenv/bin/activate
pip install -r requirements.txt
```

⚙️ Configuration
1️⃣ Add GitHub Token
Open utils.py
Replace this block:

python
Copy
Edit
token = "ghp_yourgithubtoken"
headers["Authorization"] = f"token {token}"

2️⃣ Add Telegram Credentials
Open scanner.py
Set your bot token and multiple chat IDs:

python
Copy
Edit
TELEGRAM_BOT_TOKEN = "your-bot-token"
TELEGRAM_CHAT_IDS = ["123456789", "987654321"]
✅ You can send reports to multiple users
🆔 To get chat_id, talk to your bot and visit:

3️⃣ Add Repositories to Scan
Edit repos.txt like this:

bash
Copy
Edit
https://github.com/n8n-io/n8n
https://github.com/dr5hn/countries-states-cities-database
✔️ One repo URL per line
✔️ Supports scanning multiple public repos

▶️ Running the Tool
bash
Copy
Edit
python3 scanner.py
You’ll see output like:

less
Copy
Edit
[+] Scanning https://github.com/n8n-io/n8n
[+] Scanning https://github.com/xyz/another-repo
[+] Scan complete. Results saved to output/scan_report.json
If Telegram is set, a message + report file is sent 📩
