Simple Keylogger Demo

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)

Overview
This repository contains simple Python-based keylogger scripts designed for educational and demonstration purposes only. These scripts demonstrate basic keystroke capture and logging techniques using the pynput library. One script logs keystrokes to a file, while the other sends periodic logs via email.
Key files:

Keylogger.py: Captures keystrokes and emails them in batches (every 100 characters).
Keyloggers.py: Captures keystrokes and appends them to a local log.txt file.
KEYLOGGERS.docx: Detailed documentation including input/output examples and screenshots (images 1-6).
log.txt: Sample output from Keyloggers.py.
image1.png - image6.png: Screenshots of script execution and outputs (referenced in the .docx).

These tools are not intended for production use, surveillance, or any unauthorized monitoring. Always obtain explicit consent before running on any device.
Features

Real-time Keystroke Capture: Monitors keyboard input globally.
Custom Key Handling: Maps special keys (e.g., space to ' ', enter to '\n').
Batch Logging: Email version sends logs securely (after configuration).
File Output: Simple append-to-file logging with timestamps.
Cross-Script Compatibility: Both scripts use pynput for consistent behavior.

Requirements

Python 3.8 or higher.
Windows OS (tested; may require adaptations for other platforms).
Administrative privileges (for global keyboard access).

Dependencies
Install via pip:
textpip install pynput
See requirements.txt for exact versions.
Installation

Clone the repository:textgit clone https://github.com/username/keylogger-project.git
cd keylogger-project
Install dependencies:textpip install -r requirements.txt
(Optional) Review and edit Keylogger.py for email configuration (see Usage below).

Usage
Running Keyloggers.py (File Logging)
This script logs keystrokes to log.txt and prints them to the console. Press Esc to stop.
bashpython Keyloggers.py
Sample Output in log.txt:
textKey.caps_lock s Key.caps_lock a t y a m Key.space Key.caps_lock c n s Key.space Key.enter p Key.caps_lock a s s 1 2 3 4 Key.esc
Running Keylogger.py (Email Logging)
This script accumulates keystrokes and sends an email every 100 characters. It runs indefinitely until manually stopped (Ctrl+C).

Configure Email (Critical Security Step):
Replace hardcoded credentials in the script with your own:
Use a Gmail App Password (generate at myaccount.google.com/apppasswords).
Or use environment variables:pythonimport os
from_email = os.getenv('EMAIL_FROM')
password = os.getenv('EMAIL_PASS')
to_email = os.getenv('EMAIL_TO')
Set vars: export EMAIL_FROM=your@email.com (or equivalent on Windows).


Run the script:bashpython Keylogger.py

Behavior:

Logs alphanumeric keys, spaces, enters, etc.
Ignores shifts/tabs; marks backspace as <.
Emails subject: "Victim's Keystrokes" (customize as needed).

Stopping: Use Ctrl+C. Logs reset after each email.
Viewing Documentation

Open KEYLOGGERS.docx for detailed input/output traces.

Troubleshooting

Permission Denied: Run as Administrator on Windows.
pynput Import Error: Ensure pip install pynput succeeded.
Email Fails: Check Gmail 2FA/App Password setup; test SMTP manually.
Special Keys Not Logging: Review log_happykey or on_press functions for mappings.

If issues persist, open an issue with details.
Disclaimer and Ethical Warnings
⚠️ This project is for educational purposes only. Keyloggers can capture sensitive data (e.g., passwords, personal info).

Legal: Unauthorized use violates privacy laws (e.g., Wiretap Act in the US). Obtain consent; use only on your own devices.
Security: Never commit real credentials to Git. Use .env files and .gitignore.
Responsibility: Developers/hosters are not liable for misuse. Test in isolated VMs.

By using this code, you agree to these terms.
Contributing
Suggestions welcome! Fork, PR, or discuss in issues. Focus on security/educational enhancements.
License
This project is licensed under the MIT License - see the LICENSE file for details.

Built with ❤️ for learning cybersecurity basics.
