# Alpha

Alpha is an educational wireless security research tool written in Python.  
It demonstrates how wireless interfaces are prepared, monitored, and analyzed
in **authorized laboratory environments only**.

---

## ⚠️ Legal & Ethical Notice

This project is intended **strictly for educational and defensive research**.

- Use this tool **only** on networks you own  
- Or networks for which you have **explicit written permission**

Unauthorized use against third-party or public networks is illegal and unethical.  
The author assumes **no responsibility** for misuse.

---

## Requirements

- Linux-based operating system (Kali Linux recommended)
- Python 3
- Monitor-mode capable Wi-Fi adapter
- `aircrack-ng` suite installed
- Administrator (sudo) privileges

---

## Usage (Authorized Lab Environment Only)

⚠️ Use this tool **only** on networks you own or have explicit written permission to test.

---

### 1. Enable Monitor Mode

Put the wireless adapter into monitor mode:

``
airmon-ng start wlan0
This command enables monitor mode and usually creates a monitor interface such as wlan0mon.

2. Rename the Monitor Interface (Optional)
Ensure the monitor interface uses a consistent name:

ip link set <interface> name wlan0mon
Replace <interface> with the monitor-mode interface created by your system.

3. Start the Tool
Run the script with administrator privileges:

sudo python3 wifidddos.py

