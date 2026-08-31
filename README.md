## Bhavesh Waghmare

**I build hardware that works when the internet doesn't.**

Embedded systems, robotics and IoT. ESP32 firmware, motor drivers and boards I can
actually repair in the field. Electronics & Telecommunication diploma graduate from
Government Polytechnic Amravati, and Lead Technician of the R&D Club at Sipna College
of Engineering and Technology.

My process starts with the problem, not the parts list: understand it, compare the
approaches, prove the concept, then move into hardware. Even when a project already
exists, I ask what I can do differently so the finished build earns its place.

The thing most of my firmware has in common is that it assumes the network will fail.
Wall switches keep switching with the cloud down. A tank keeps feeding its fish with
the router unplugged. Relay state survives a power cut because it was written to NVS,
not held in RAM. That is the constraint I design to, and it is why these builds are
still running rather than sitting in a drawer.

---

### Selected work

| Project | What it is |
|---|---|
| [SafetyFirst PPE Checkpoint](https://github.com/Bhavesh6/PPE-Detection) | An access-control gate for a work site, not a monitoring dashboard. RFID badge in, YOLOv8 checks hardhat/vest/mask against a policy an admin can change mid-shift, gate opens or refuses with the reason recorded. Team Mojito, FAR AWAY 2026. |
| [RainMaker Smart Switches](https://github.com/Bhavesh6/esp-rainmaker-smart-switches) | A five-room house running on hand-wired bare ESP32-WROOM-32E modules. Eleven relays, no flicker on boot, and wall switches that keep working with Wi-Fi and the cloud fully down. Live in five rooms. |
| [Smart Aquarium Controller](https://github.com/Bhavesh6/Smart-Aquarium-ESP32) | Offline-first ESP32 automation: scheduled feeding, pump cycling, four relays, mobile dashboard served off SPIFFS. Detects missed feeds on boot and reboots itself if the cloud hangs. The cloud is a layer, never a dependency. |
| [ESP32 Race Robot](https://github.com/Bhavesh6/ESP32-RoboRace-bot) | Tank-drive race robot on a two-ESP32 ESP-NOW link, built for minimum latency with telemetry coming back. Two BTS7960 43A drivers, live current on the remote's OLED, per-side motor trim saved to NVS. |
| [SigmaDSP Marshall BT Speaker](https://github.com/Bhavesh6/SigmaDSP-Marshall-BT-Speaker) | A portable speaker built from raw chips instead of a module. ADAU1701 SigmaDSP, ESP32-WROVER over LDAC, TPA3116 + TPA3110 Class-D, live EQ over I²C. Fully documented before a single part is soldered. |
| [RO Purifier Controller](https://github.com/Bhavesh6/ESP32-Water-Purifier-Controller) | Replaces the stock board in a residential RO purifier. Sequenced inlet/pump/UV cycle, TDS monitoring, dual filter life in EEPROM, relays that default off so a power cut cannot leave the pump running. |
| [PC Dock](https://github.com/Bhavesh6/pc-dock) | An old Android phone turned into an always-on desk dock: live CPU and GPU meters, media remote, configurable macro pad. Served over the LAN, no cloud. |
| [Portfolio](https://github.com/Bhavesh6/portfolio) | My site. Plain HTML/CSS/JS, no framework, no build step. The robot's face is a real browser port of `face.py` from my elder-care companion robot — same presets, same eyelid-curve maths. |

Also: a hybrid GSM/GPS tracker with coordinate buffering, a YOLO traffic-light
retimer bridged to hardware over serial, an ESP32-CAM attendance system logging to
Sheets, and a B2B site for a steam and valve manufacturer (client work, private).

---

### Things I reach for

**Silicon** — ESP32 / ESP8266 · Arduino framework · Embedded C/C++ · AsyncWebServer · Raspberry Pi

**Talking to things** — ESP-NOW · I²C / SPI / UART · BLE · CAN bus · GSM / GPS

**Hardware** — Motor drivers · Sensor integration · PCB and circuit design · Power electronics · LiPo BMS

**Software** — Python · OpenCV · YOLO · HTML / CSS / JS · Arduino IoT Cloud · Google Sheets API

---

### Wins worth framing

- **1st place, hardware division** — CMR Hackfest 3.0 (national), representing the Sipna CoET R&D Club
- **2nd runner-up, overall** — CMR Hackfest 3.0, against teams from across India
- **Multiple robo-race podiums** at college level; at one event our entries took 1st, 2nd and 3rd outright

---

### A note on how I work

I use AI tools as engineering assistants — for research, debugging, documentation and a
fair amount of the code. I say so plainly because the interesting part was never typing
it out. I verify the output, make the engineering calls, and test the hardware myself,
which is the part no model can do for me.

---

**Portfolio** → [bhavesh6.github.io/portfolio](https://bhavesh6.github.io/portfolio/) · **Email** → bhavesh.waghmare05@gmail.com · **Based in** Amravati, Maharashtra, India

*Got a hardware problem that keeps failing? I like the ones that only break in the field.*
