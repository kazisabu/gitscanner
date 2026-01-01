# 🔍 GitScan – GitHub Repo Keyword & Secret Scanner

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg?logo=python)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![GitHub API](https://img.shields.io/badge/API-GitHub--based-lightgrey?logo=github)](https://docs.github.com/en/rest)

# GitScan: GitHub Repository Keyword & Secret Scanner

GitScan is a lightweight security tool designed to detect secrets, credentials, and specific patterns within public GitHub repositories. Unlike traditional scanners, GitScan leverages the **GitHub API** to inspect code without the need for local cloning, making it fast and resource-efficient.

---

## Key Features

* **API-Based Scanning:** Analyzes code directly via GitHub’s REST API (no `git clone` required).
* **Customizable Filters:** Define specific keywords and file extensions to target.
* **Bulk Processing:** Scans multiple repositories in a single execution.
* **Structured Output:** Generates JSON reports for easy integration with other tools.
* **Automated Notifications:** Optionally delivers results and report files via Telegram.

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

## Configuration
1. GitHub Authentication
To avoid rate limiting, provide a GitHub Personal Access Token (PAT) in utils.py:
```
token = "ghp_yourgithubtoken"
headers["Authorization"] = f"token {token}"
```
## 2. Telegram Integration
Configure your bot credentials in scanner.py. You can specify multiple recipients:
```
TELEGRAM_BOT_TOKEN = "your-bot-token"
TELEGRAM_CHAT_IDS = ["123456789", "987654321"]
```
3. Define Targets
Add the repositories you wish to scan to repos.txt, ensuring there is one URL per line:
```
https://github.com/target_1/target_repo_1
https://github.com/target_2/target_repo_2
```
One repo URL per line
Supports scanning multiple public repos

Usage
Execute the scanner using Python:
```
python3 scanner.py
```
If Telegram notifications are enabled, the bot will transmit a summary and the JSON report file upon completion.
