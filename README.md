# KeyLOgger-
# Project

**⚠️ Disclaimer**: Please Unauthorized use of keyloggers is illegal and violates privacy laws. Only use this in controlled environments with explicit consent.

---

## 📌 Overview
This is a **Python-based KeyLogger** with additional features like:
- **Keystroke logging** (with encryption)
- **System information collection** (IP, hostname, OS, etc.)
- **Clipboard monitoring**
- **Microphone recording**
- **Screenshot capture**
- **Webcam snapshot**
- **Email reporting** (encrypted logs sent via SMTP)
- **File encryption** (AES via Fernet)

---

## 🛠️ Prerequisites
- Python 3.8+
- Required libraries (install via `pip`):
  ```bash
  pip install cryptography pynput sounddevice scipy opencv-python pillow requests pywin32
  ```

---

## 📂 Project Structure
```
KeyLogger-main/
├── Cryptography/
│   ├── DecryptFile.py       # Decrypts logged files
│   └── GenerateKey.py       # Generates encryption key
├── main.py                  # Main KeyLogger script
├── .deepsource.toml         # Static analysis config
└── .gitignore               # Git exclusion rules
```

---

## 🔐 Setup & Usage

### 1. Generate Encryption Key
Run `GenerateKey.py` to create a Fernet key:
```bash
python Cryptography/GenerateKey.py
```
This creates `encryption_key.txt`. **Keep this secure!**

### 2. Configure `main.py`
Edit these variables in `main.py`:
```python
email_address = "your_email@gmail.com"  # Disposable email recommended
password = "your_app_password"         # Use Gmail App Password
toaddr = "recipient@example.com"       # Where logs are sent
key = "paste_key_from_encryption_key.txt"
file_path = "C:\\Logs"                # Output directory (must exist)
```

### 3. Run the KeyLogger
```bash
python main.py
```
- Press `Esc` to stop logging manually.
- Logs are encrypted and emailed periodically.

---

## 🔄 Decrypting Logs
Use `DecryptFile.py` with the generated key:
```python
key = "your_fernet_key"  # From encryption_key.txt
```
Run:
```bash
python Cryptography/DecryptFile.py
```
Decrypted logs will merge into `decryption.txt`.

---

## ⚠️ Ethical & Legal Notes
- **Obtain explicit consent** before testing.
- **Do not use maliciously**—this is for **educational purposes only**.
- Test only in **controlled environments** (e.g., your own devices/VMs).

---

## 📜 Features Breakdown
| Feature               | Description                                  | Output File           |
|-----------------------|----------------------------------------------|-----------------------|
| Keystroke Logging     | Logs pressed keys                           | `e_keys_logged.txt`   |
| System Info           | Collects hostname, IP, OS, etc.             | `e_system.txt`        |
| Clipboard Monitoring  | Captures clipboard text                     | `e_clipboard.txt`     |
| Microphone Recording  | Records audio (10s by default)              | `audio.wav`           |
| Screenshot Capture    | Takes screenshots                           | `screenshot.png`      |
| Webcam Snapshot       | Captures webcam image                       | `webCamera.png`       |

---

## 🛡️ Security Notes
- **Encryption**: All logs are AES-encrypted using Fernet.
- **Data Cleanup**: Original files are deleted after encryption.
- **SMTP Security**: Uses TLS for email transmission.

---

## 📌 Example Use Cases (Ethical Only)
- **Penetration Testing**: Audit your own systems.
- **Digital Forensics**: Study malware behavior in labs.
- **Parental Control**: Monitor your child’s device (with consent).

---

## 📄 License
This project is for **educational use only**. Unauthorized distribution or misuse may violate local laws.

---
**🚀 This is my first cyber project and I'm open for corrections.
Thanks.
