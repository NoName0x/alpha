# Alpha

Alpha is an educational wireless security research tool written in Python.  
It demonstrates how wireless interfaces are prepared, monitored, and analyzed
in **authorized laboratory environments only**.

---

## ⚠️ Legal & Ethical Notice

This project is intended **strictly for educational and defensive security research**.

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

```bash
airmon-ng start wlan0
This command enables monitor mode and usually creates a monitor interface such as wlan0mon.

2. Rename the Monitor Interface (Optional)
Ensure the monitor interface uses a consistent name:

ip link set <interface> name wlan0mon
Replace <interface> with the monitor-mode interface created by your system.

3. Start the Tool
Run the script with administrator privileges:

sudo python3 wifidddos.py
After starting the tool:

Available wireless interfaces are displayed

You are prompted to select an interface by number

Nearby Wi-Fi access points are scanned and listed in real time

Runtime Behavior
Interface Detection
Wireless interfaces are detected automatically

A monitor-mode capable adapter is required

Conflicting network services may be temporarily disabled

Passive Network Scanning
Wi-Fi access points are detected passively

Network details such as BSSID, channel, and ESSID are displayed

No user input is required during the scanning phase

Wi-Fi List Shuffle Behavior
While scanning:

The Wi-Fi list may change order

Signal strength updates can cause reordering

New access points may appear dynamically

Some networks may temporarily disappear and reappear

✅ This behavior is normal
❌ This is not an error

Ctrl + C Behavior
First Ctrl + C
Stops live scanning

Freezes the current Wi-Fi list

Prevents further list shuffling

Displays each access point with a number

After this:

Enter the number of the Wi-Fi access point you want to select

Press Enter to continue

Second Ctrl + C
Stops the testing process

Disables monitor mode

Restores the wireless interface

Exits the program cleanly

✔️ This shutdown order is intentional and correct

Error Handling & Common Issues
No Wi-Fi Interfaces Shown
Possible causes:

Adapter does not support monitor mode

Driver not loaded correctly

Tool not run with sudo

Fix:

sudo python3 wifidddos.py
Wi-Fi List Keeps Shuffling
Explanation:

Live scanning continuously refreshes results

Action:

Allow scanning to run for a few seconds

Press Ctrl + C to freeze the list before selecting

Ctrl + C Pressed Too Early
Result:

No networks displayed

Selection not possible

Fix:

Restart the tool

Wait until networks appear

Press Ctrl + C again

Screen Appears Frozen After Ctrl + C
Explanation:

The tool is waiting for user input

Action:

Enter the access point number and press Enter
