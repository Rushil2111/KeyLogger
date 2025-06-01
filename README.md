# KeyLogger with Surveillance Features

## Description

This is a Python-based tool that captures:

* Keystrokes
* System and clipboard information
* Microphone audio (10 seconds)
* Screenshots
* Webcam snapshots
* Sends encrypted logs via email

---

## Features

* Key logging
* System info and IP retrieval
* Clipboard monitoring
* Audio recording using microphone
* Screenshot capture
* Webcam snapshot
* AES Encryption via Fernet
* Auto-email logs to specified address

---

## Requirements

* Windows OS (for `win32clipboard`)
* Python 3.7+
* Required packages:

  ```bash
  pip install pynput sounddevice scipy cryptography requests opencv-python pillow pywin32
  ```

---

## Setup Instructions

1. Clone the repository or copy the script.
2. Set the following fields in the script:

   * `email_address`: Sender's email
   * `password`: App-specific or actual password (use securely!)
   * `toaddr`: Receiver email address
   * `key`: A Fernet encryption key (`Fernet.generate_key()`)
   * `file_path`: Absolute directory to save logs (e.g., `C:\\Users\\YourUser\\Documents`)
3. Run the script with administrative privileges:

   ```bash
   python keylogger.py
   ```

---

## Encryption

The script uses the `cryptography` library to encrypt sensitive log files before sending them via email. Ensure the Fernet key is securely stored.

---

## Cleanup

The script deletes sensitive files after exfiltration. You may want to disable this during testing by commenting out:

```python
os.remove(file_merge + file)
```