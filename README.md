
# CMDHACK WiFi Scanner 🔍

**Professional WiFi Security Analyzer for Termux**  
*By ComradeHacker Team CMDHACK*

[![Termux](https://img.shields.io/badge/Termux-API-blue?logo=android)](https://termux.com)
[![Python](https://img.shields.io/badge/Python-3.8+-green?logo=python)](https://python.org)
[![License](https://img.shields.io/badge/License-GPL_3.0-yellow)](LICENSE)
[![Version](https://img.shields.io/badge/Version-2.0.0-orange)](https://github.com/cmdhck/Wifi-scan)

> Advanced WiFi network scanner with distance estimation, security analysis, and real-time threat detection.

## ✨ Features

| Feature | Description |
|---------|-------------|
| 📡 **Real-time Scanning** | Auto-refresh with configurable intervals |
| 📏 **Distance Estimation** | Calculate approximate distance in meters |
| 🔒 **Security Analysis** | Detect WPA3/WPA2/WPA/WEP/OPEN networks |
| ⚠️ **Threat Detection** | CRITICAL/HIGH/MEDIUM/LOW/SAFE threat levels |
| 📶 **Band Analysis** | 2.4GHz vs 5GHz detection |
| 🎨 **Interactive UI** | Color-coded table with keyboard controls |
| 💾 **Export Results** | Save scans to JSON/TXT files |

## 🚀 Quick Start

### 1. Install Requirements
```bash
pkg update && pkg upgrade -y
pkg install termux-api python -y
termux-setup-storage
termux-location  # Grant location permission
```

2. Run the Scanner

```bash
git clone https://github.com/cmdhck/Wifi-scan.git
cd Wifi-scan
python wifiscanner.py
```

🎮 Controls

Key Action Description
Q Quit Exit the scanner
R Refresh Manual scan refresh
+ Faster Decrease scan interval
- Slower Increase scan interval
D Details View network details
E Export Save results to file
S Settings Open settings menu

📊 Sample Output

```
╔══════════════════════════════════════════════════╗
║      COMRADEHACKER TEAM CMDHACK WIFI SCANNER    ║
╠══════════════════════════════════════════════════╣
║ Scan #15 | Networks: 8 | Refresh: 5s            ║
╚══════════════════════════════════════════════════╝

┌──────────┬──────────────────────┬──────────┬──────┬──────────┬─────────────┐
│ Threat   │ SSID                 │ Signal   │ Ch   │ Dist     │ Security    │
├──────────┼──────────────────────┼──────────┼──────┼──────────┼─────────────┤
│ ⚠ HIGH    │ Home_WiFi           │ -42dBm   │ 6    │ 2.0m     │ WPA2-PSK    │
│ MEDIUM   │ GuestNetwork        │ -68dBm   │ 11   │ 20.0m    │ OPEN        │
│ LOW      │ Office_Secure       │ -55dBm   │ 36   │ 5.0m     │ WPA3        │
└──────────┴──────────────────────┴──────────┴──────┴──────────┴─────────────┘

📊 STATS: 8 Networks • 2 Suspicious • 3 Secure
🎮 CONTROLS: [Q]uit [R]efresh [+]Faster [-]Slower
```

🔧 Advanced Usage

Command Line Options

```bash
python wifiscanner.py --interval 3     # 3-second refresh
python wifiscanner.py --output scan.json  # Export results
python wifiscanner.py --no-color       # Disable colors
```

Export Formats

```python
# JSON Export (full data)
{
  "scan_time": "2024-01-15T14:30:00",
  "total_networks": 8,
  "networks": [
    {
      "ssid": "Home_WiFi",
      "bssid": "AA:BB:CC:DD:EE:FF",
      "signal": -42,
      "distance": 2.0,
      "security": "WPA2-PSK",
      "threat": "HIGH"
    }
  ]
}

# TXT Export (readable report)
SSID: Home_WiFi
BSSID: AA:BB:CC:DD:EE:FF
Signal: -42 dBm | Distance: ~2.0m
Security: WPA2-PSK | Threat: HIGH
```

🛠️ Technical Details

Distance Estimation Algorithm

```python
# Signal strength to distance conversion
if signal >= -30: distance = 0.1m    # Very close
elif signal >= -40: distance = 1.0m  # Close
elif signal >= -50: distance = 3.0m  # Near
elif signal >= -60: distance = 10.0m # Medium
elif signal >= -70: distance = 20.0m # Far
else: distance = 35.0m+              # Very far
```

Security Classification

· WPA3/WPA3-Enterprise → "Not Crackable" 🔒
· WPA2-PSK → "Crackable (Weak Pass)" ⚠️
· WPA-PSK → "Easily Crackable" 🚨
· WEP → "Very Easy to Crack" 💀
· OPEN → "No Security" 🔓

⚠️ Troubleshooting

Problem Solution
No networks found Run termux-location and grant permission
Permission denied Execute termux-setup-storage
Termux API missing pkg install termux-api -y
Python not found pkg install python -y

📁 Project Structure

```
Wifi-scan/
├── wifiscanner.py          # Main scanner script
├── README.md              # This documentation
├── LICENSE               # GPL v3 License
└── examples/            # Sample outputs
    ├── sample_scan.json
    └── sample_report.txt
```

📄 License

GNU General Public License v3.0 - See LICENSE file.

⚠️ Legal Disclaimer

FOR EDUCATIONAL AND AUTHORIZED SECURITY TESTING ONLY

· Only scan networks you own or have permission to test
· Comply with all applicable laws and regulations
· The ComradeHacker Team is not responsible for misuse

🤝 Contributing

1. Fork the repository
2. Create a feature branch (git checkout -b feature/AmazingFeature)
3. Commit changes (git commit -m 'Add AmazingFeature')
4. Push to branch (git push origin feature/AmazingFeature)
5. Open a Pull Request

🌟 Support

If you find this tool useful:

· ⭐ Star the repository
· 🐛 Report issues
· 💡 Suggest features
· 🔄 Share with others

---

ComradeHacker Team CMDHACK
Cybersecurity Research & Ethical Hacking

"Knowledge shared is power multiplied"

---

https://img.shields.io/badge/GitHub-cmdhck/Wifi--scan-black?logo=github
https://img.shields.io/badge/Termux-Required-3DDC84?logo=android
https://img.shields.io/badge/Powered_by-Python-3776AB?logo=python

```

This README is:
1. **Short and clear** - Easy to understand at a glance
2. **Feature-focused** - Highlights key capabilities
3. **Practical** - Quick start guide with copy-paste commands
4. **Branded** - Clearly shows ComradeHacker Team CMDHACK
5. **Professional** - Includes badges, tables, and clear sections
6. **Legal** - Includes disclaimer and license info
7. **GitHub optimized** - Good formatting for GitHub markdown
