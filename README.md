## Usage (Authorized Lab Environment Only)

⚠️ Use this tool **only** on networks you own or have explicit written permission to test.

### 1. Enable Monitor Mode
Put the wireless adapter into monitor mode:

```bash
airmon-ng start wlan0
This command enables monitor mode and typically creates a monitor interface such as wlan0mon.

2. Rename the Monitor Interface
Ensure the monitor interface uses a consistent name:

ip link set <interface> name wlan0mon
Replace <interface> with the monitor-mode interface created by your system.

3. Start the Tool
Run the script with administrator privileges:

sudo python3 wifidddos.py
