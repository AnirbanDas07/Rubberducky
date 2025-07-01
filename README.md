# Rubberducky
Rubberducky v1
# USB HID Multi-Payload Injector – README

This script turns a **Raspberry Pi Pico** (or similar CircuitPython-enabled device) into a **USB HID injector**, executing a sequence of **malicious PowerShell payloads** on Windows systems.

> ⚠️ **Warning:** This script is designed for **authorized penetration testing and red team exercises only**. Unauthorized use is illegal and unethical.

## 🔧 What It Does

When plugged into a Windows machine, this device simulates keyboard input to execute the following payloads:

1. **Download and execute a remote executable**
2. **Disable Windows Defender**
3. **Exfiltrate stored Wi-Fi passwords**
4. **Create a persistent backdoor using a scheduled task**
5. **Establish a reverse shell connection**

Each payload runs in sequence after elevating privileges via UAC prompt simulation.

## 🧰 Requirements

- **Raspberry Pi Pico** or other RP2040-based board
- Micro USB cable
- [CircuitPython](https://circuitpython.org/ ) installed
- Libraries:
  - `adafruit_hid`
- File:
  - `code.py` – Place this script as the main file on the device

## 🛠️ Usage

1. Flash CircuitPython onto your device.
2. Copy the `adafruit_hid` library to the `lib/` folder.
3. Save this script as `code.py` on the root of the device.
4. Plug the device into the target Windows system.

> By default, the script runs in **Attack Mode** and executes all payloads.

## 🛡️ Setup Mode

To temporarily disable payload execution (e.g., for safe testing or configuration):

- Connect **GPIO 0 (GP0)** to **GND** before plugging in the device.
- The script will print `"Setup Mode: Payload injection is disabled."`

## 🔒 	Important Notes:
Replace all placeholder URLs like https://example.com/... with your actual C2 server or payload host.
Replace ATTACKER_IP and ATTACKER_PORT in the reverse shell payload with your listener's IP and port.
This script assumes you're using CircuitPython and have properly installed the adafruit_hid library.

## ⚠️ Legal Disclaimer

This tool is intended solely for **ethical hacking**, **cybersecurity training**, or **authorized red team operations**. Using it without permission on systems you do not own is **illegal** and may result in criminal charges.

## 💡 Tips for Blue Teams

Monitor for:
- Unexpected PowerShell windows opening
- Suspicious network activity (e.g., connections to unknown IPs/domains)
- Creation of scheduled tasks or registry persistence entries
- Use of `Invoke-WebRequest`, `iex`, and `netsh wlan` commands

## 📜 License

MIT License – See full license in `LICENSE`.

> ✅ Always operate responsibly and ethically.  
> 🔒 Respect laws, privacy, and system ownership.
