# Alpha: Wi-Fi DDoS & Security Research Tool


**Alpha** is an educational wireless security research tool written in Python. It demonstrates how wireless interfaces are prepared, monitored, and analyzed in authorized laboratory environments. Specifically, it showcases Wi-Fi Denial of Service (DDoS) attacks via the 802.11 deauthentication mechanism.

> [!CAUTION]
> **LEGAL & ETHICAL NOTICE**
> This project is intended strictly for educational and defensive security research. Use this tool only on networks you own or networks for which you have explicit written permission. Unauthorized use against third-party or public networks is illegal and unethical. The author assumes no responsibility for misuse.

---

## 🛠️ Requirements

* **Operating System**: Linux-based (Kali Linux highly recommended).
* **Language**: Python 3.
* **Hardware**: Monitor-mode capable Wi-Fi adapter.
* **Dependencies**: `aircrack-ng` suite installed.
* **Privileges**: Administrator (sudo) privileges.

---

## 🚀 Usage (Authorized Lab Environment Only)

⚠️ **Warning:** Use this tool **only** on networks you own or have explicit written permission to test.

1. Enable Monitor Mode
Put the wireless adapter into monitor mode:
```bash
sudo airmon-ng start wlan0

2. Rename the Monitor Interface
Ensure the monitor interface uses a consistent name:

```bash
sudo ip link set <interface> name wlan0mon
Replace <interface> with the monitor-mode interface created by your system (e.g., wlan0mon).

3. Start the Tool
Run the script with administrator privileges:

```bash
sudo python3 wifidddos.py


⚙️ Runtime Behavior
Interface Detection
Wireless interfaces are detected automatically.

A monitor-mode capable adapter is required.

Conflicting network services may be temporarily disabled to ensure stability.

Passive Network Scanning & Wi-Fi DDoS Prep
Wi-Fi access points are detected passively.

The Wi-Fi list may change order during scanning as signal strengths update. This behavior is normal.

Control Flow (Ctrl + C)
First Ctrl + C: Stops live scanning and freezes the current Wi-Fi list. This prevents shuffling and allows you to select a target.

Action: Enter the number of the Wi-Fi access point you want to target and press Enter.

Second Ctrl + C: Stops the DDoS testing process, disables monitor mode, restores the wireless interface, and exits the program cleanly.


Issue,Cause,Fix
No Wi-Fi Interfaces Shown,Missing sudo or adapter doesn't support monitor mode.,Run with sudo or check iwconfig.
List Keeps Shuffling,Live scanning is active.,Press Ctrl + C once to freeze the list.
Screen Appears Frozen,The tool is waiting for your target selection.,Type the ID number and press Enter.
Ctrl + C Pressed Too Early,No networks had time to appear.,Restart the tool and wait 5-10 seconds before stopping the scan.


📜 Technical Methodology
This tool performs a Layer 2 Denial of Service by:

Transitioning the NIC into Monitor Mode.

Capturing 802.11 Beacon frames to identify target BSSIDs.

Utilizing aireplay-ng to broadcast Deauthentication Frames, which instructs client devices to disconnect from the Access Point.
