# Bruce Firmware Tools

Bruce is a versatile ESP32 firmware that supports many offensive features focused on Red Team operations, and is compatible with M5Stack products such as Cardputer, Sticks, M5Cores, T-Decks, and T-Embeds. [Bruce GitHub](https://github.com/pr3y/Bruce).


### WiFi Tools

| Tool | Category | Description | Features |
|------|-----------|------------|--------------|
| **Connect to WiFi** | Connection | Connect to WiFi Network | Manually Connect to WiFi Networks |
| **WiFi AP** | Hotspot | Create Access Point | Create a Custom WiFi Hotspot |
| **Disconnect WiFi** | Management | Disconnect WiFi | Disconnect from WiFi Networks |
| **WiFi Attacks** | Attack | Suite of WiFi Attacks | Various Types of Wireless Attacks |
| **Beacon Spam** | Attack | Beacon Spam | Sends fake beacons to confuse scanners |
| **Target Attack** | Attack | Targeted Attack | Specific attacks on a selected target |
| **Target Deauth** | Attack | Deauthentication | Disconnects specific devices |
| **EvilPortal + Deauth** | Attack | Captive portal + deauth | Combines fake portal with deauthentication |
| **Deauth Flood** | Attack | Deauthentication Flood | Disconnects multiple targets simultaneously |
| **Wardriving** | Reconnaissance | WiFi Mapping | Scans and maps WiFi networks on the move |
| **TelNet** | Connection | TelNet Client | TelNet connections for remote administration |
| **SSH** | Connection | SSH Client | Secure SSH connections |
| **RAW Sniffer** | Analysis | Traffic Sniffing | Capture Raw WiFi Packet(s) |
| **TCP Client** | Network | TCP Client | Custom TCP Connections |
| **TCP Listener** | Network | TCP Server | Listen for Incoming TCP Connections |
| **DPWO-ESP32** | Exploit | Data Plane Without OS | OS Bypass Exploit |
| **Evil Portal** | Attack | Captive Portal | Create Fake Login Portals |
| **Scan Hosts** | Reconnaissance | Host Scanner | Scan Active Hosts on the Network |
| **Wireguard Tunneling** | VPN | VPN Tunnel | Establish Wireguard Tunnels |

### Bluetooth/BLE Tools

| Tool | Category | Description | Feature |
|------|-------------|--------------|--------------|
| **BLE Beacon** | Beacon | Bluetooth Beacon | Emulate custom BLE beacons |
| **BLE Scan** | Reconnaissance | BLE Scanner | Scan Bluetooth LE devices |
| **AppleJuice** | Attack | iOS Notification Spam | Send Spam Notifications to iOS Devices |
| **Sour Apple** | Attack | AirDrop Attack | Apple AirDrop Exploit |
| **SwiftPair Spam** | Attack | SwiftPair Spam | Windows Pairing Notification Spam |
| **Samsung Spam** | Attack | Samsung Spam | Spam Notifications for Samsung Devices |
| **NRF24 Jammer** | Jamming | 2.4GHz | Jam 2.4GHz Signals with NRF24 Module |
| **Mousejack** | Exploit | Wireless Mouse Attack | Wireless Mouse/Keyboard Exploit |

### Brucegotchi

| Tool | Category | Description | Feature |
|------|------------|-------------|--------------|
| **Pwnagotchi Friend** | Social | Pwnagotchi Compatibility | Interact with other Pwnagotchis |
| **Pwngrid Spam** | Spam | Spam faces & names | Send spam to Pwngrid |
| **DoScreen** | Display | Long name and face | Show very long names/faces |
| **Flood Peer IDs** | Flood | Flood identifiers | Flood unique peer identifiers |

### RF/Radio Tools

| Tool | Category | Description | Feature |
|------|-------------|-------------|--------------|
| **Custom SubGhz** | Replay | Replay Sub-GHz | Replay signals as Flipper Zero |
| **RF Spectrum** | Analysis | Spectrum Analyzer | View RF Spectrum |
| **Jammer Full** | Jamming | Full Jammer | Send Full Square Wave |
| **Jammer Intermittent** | Jamming | Intermittent Jammer | Send PWM Signal |
| **CC1101 Sub-GHz** | Module | CC1101 Management | CC1101 Module Control |
| **RF Frequency** | Configuration | Frequency Setup | Configure RF Frequency |
| **2.4G Spectrum** | Analysis | 2.4GHz Spectrum | Analyze 2.4GHz Band |

### RFID/NFC Tools

| Tool | Category | Description | Functionality |
|------|--------------|---------------|
| **Read Tag** | Read | Read RFID/NFC tags | Read RFID and NFC tags |
| **Read 125kHz** | Read | Low-frequency reading | Read 125kHz tags |
| **Clone Tag** | Cloning | Tag cloning | Clone RFID/NFC tags |
| **Write NDEF** | Write | Write NDEF records | Write standard NFC records |
| **Amiibolink** | Gaming | Nintendo Amiibo | Manage Nintendo Amiibo |
| **Chameleon** | Emulation | Advanced emulation | Tag emulation with Chameleon |
| **Write Data** | Write | Write data | Write custom data |
| **Erase Data** | Management | Erase data | Erase data from tags |
| **PN532** | Module | PN532 management | PN532 module control |
| **PN532Killer** | Exploit | PN532 Exploit | Exploit for PN532 Modules |
| **Emulate Tag** | Emulation | Tag Emulation | Emulate Different Tag Types |

### Infrarossi (IR) Tools

| Tool | Category | Description | Features |
|------|------------|-------------|--------------|
| **TV-B-Gone** | Control | Turn Off TV | Turns off TV universally |
| **IR Receiver** | Reception | IR Receiver | Receives and decodes IR signals |
| **Custom IR** | Replay | Custom replay | Supports NEC, SIRC, Samsung32, RC5, RC6 |

### Other Tools

| Tool | Category | Description | Features |
|------|-------------|-------------|--------------|
| **Mic Spectrum** | Audio | Microphone Spectrum | Microphone Audio Spectrum Analyzer |
| **QRCodes** | Utilities | QR Generator | Generate Custom QR Codes |
| **PIX** | Payments | Brazilian Payment System | Manages PIX (Brazil) |
| **SD ​​Card Manager** | Storage | SD Management | Manage SD Card Files |
| **View Image (JPG)** | Media | Image Viewer | View JPG Images |
| **File Info** | Utilities | File Info | Show File Details |
| **Wigle Upload** | Wardriving | Upload Data | Upload Wardriving Data to Wigle |
| **Play Audio** | Media | Audio Playback | Play Audio Files |
| **View File** | Utilities | File Viewer | View File Contents |
| **LittleFS Manager** | Storage | File System Manager | Manages LittleFS File Systems |
| **WebUI** | Interface | Web Interface | Remote Control Web Interface |
| **BADUsb** | Exploit | USB Keyboard | Malicious USB Keyboard Emulation |
| **Openhaystack** | Tracking | Tracking System | Openhaystack Integration |
| **iButton** | Hardware | iButton Management | Dallas iButton Key Support |
| **LED Control** | Hardware | LED Control | RGB LED Control |

### Configuration and Setup

| Tool | Category | Description | Features |
|------|------------|-------------|--------------|
| **RF TX/RX Pin Config** | Configuration | RF Pin | Configure Transmit/Receive Pin |
| **RF Module Config** | Configuration | RF Module | Select RF Module |
| **IR TX/RX Pin Config** | Configuration | IR Pin | Configure Infrared Pin |

### Security

**IMPORTANT**: Bruce firmware is designed exclusively for authorized security testing and legitimate Red Team operations. Use for malicious or unauthorized purposes is strictly prohibited.