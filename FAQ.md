# FAQ – Frequently Asked Questions

### ❓ What hardware do I need?
You'll need a **Raspberry Pi Pico** or another RP2040-based board running CircuitPython.

### ❓ Can I use this on macOS or Linux?
The payloads are written for **Windows PowerShell**, so they will not work natively on other OSes.

### ❓ Why is Setup Mode useful?
Setup Mode disables payload execution by checking if GP0 is connected to GND. This lets you safely update or configure the device without triggering payloads.

### ❓ Do I need internet access on the target machine?
Yes — most payloads require outbound internet connectivity to download tools or exfiltrate data.

### ❓ Is there a way to detect this attack?
Yes. Monitor for suspicious PowerShell activity, UAC bypasses, and unexpected network connections.

### ❓ Can I add my own payloads?
Absolutely! The script is modular — just define a new function and call it in `main()`.

### ❓ How can I make this stealthier?
Some techniques include:
- Obfuscating PowerShell commands
- Using encoded commands with `-EncodedCommand`
- Leveraging registry run keys instead of scheduled tasks
