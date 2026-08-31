## Bhavesh Waghmare

Embedded systems and robotics, in Amravati, India. ESP32 firmware, motor drivers and
boards I can repair in the field.

The showcase — screenshots, build photos, the full project list — lives at
**[bhavesh6.github.io/portfolio](https://bhavesh6.github.io/portfolio/)**. You are on the
code side of the house, so this page is the other thing: the rules the firmware in these
repos is actually written to, and the specific thing that taught me each one.

---

### Power and boot

**Relay state lives in NVS, not RAM.** A power cut must not silently change what is
switched on in someone's house.

**On boot, read the state and drive each GPIO straight to it.** Do not pass through the
pin default on the way. Five rooms of relays all snapping to OFF and back is a visible
flicker through the whole house every time the power returns.

**Relays default off, deliberately.** The RO purifier's pump defaults off so an outage
mid-cycle cannot leave it running against a closed inlet.

**Bulk caps on both rails.** An ESP32 node that is stable on the bench will brown out in
the wall once Wi-Fi transmit bursts start pulling on a long, thin mains-adapter run.

### Failure and recovery

**Only a health check may reboot a node. Never a network event.** On the RainMaker
switches a heap-health watchdog can restart a node; a Wi-Fi wobble cannot. Rebooting on
a wobble turns a 2-second outage into a 15-second one, and the wall switch was still
working the entire time.

**Detect what was missed, do not just resume.** The aquarium checks on boot whether a
feed was skipped while it was down, instead of quietly waiting for the next slot. A
resumed schedule looks identical to a working one right up until the fish notice.

**Watchdog the cloud, not the device.** If the IoT cloud connection hangs, that is what
gets reset. The local control loop was never the thing at fault and should not pay for it.

### Debugging

**A frozen dashboard is not a frozen device.** The aquarium's UI hang was duplicate async
route registration in AsyncWebServer — the firmware underneath had been running fine the
whole time. I spent a while suspecting the wrong layer.

**Put the meter on the robot, not the bench.** An INA226 on a 25A shunt sends live current
to the remote's OLED, so a motor starting to stall is something I see during the race
rather than diagnose after it.

### Lines I hold

**Offline is the default path; the cloud is the extra.** Feeding schedules, relay logic
and wall switches all run with the router unplugged. Only the app and voice control need
the internet. This is the constraint most of my design decisions fall out of.

**Anything you would have to re-tune under pressure gets saved.** Per-side motor trim on
the race robot is in NVS, because re-trimming a robot on the starting line is not a thing
anyone has time for.

**Record refusals, not grants.** The PPE gate photographs someone it turns away and never
photographs someone it lets through. Surveillance that only fires on an exception is a
much smaller thing to have to defend.

---

### Where the code is

**Running in the real world** — [five-room switch system](https://github.com/Bhavesh6/esp-rainmaker-smart-switches) (11 relays, bare WROOM-32E modules, hand-wired) · [aquarium controller](https://github.com/Bhavesh6/Smart-Aquarium-ESP32) (feeds, pumps and switches with no internet at all) · [RO purifier board](https://github.com/Bhavesh6/ESP32-Water-Purifier-Controller) (replaces the stock one)

**Competition and team builds** — [SafetyFirst PPE gate](https://github.com/Bhavesh6/PPE-Detection) (RFID + YOLOv8 access control; Team Mojito, FAR AWAY 2026) · [ESP32 race robot](https://github.com/Bhavesh6/ESP32-RoboRace-bot) (two-board ESP-NOW link, 43A drivers)

**In design** — [SigmaDSP Bluetooth speaker](https://github.com/Bhavesh6/SigmaDSP-Marshall-BT-Speaker) (ADAU1701 from raw chips, documented before anything is soldered)

**Not a circuit board** — [PC Dock](https://github.com/Bhavesh6/pc-dock) (old Android phone as a LAN desk dock) · [portfolio](https://github.com/Bhavesh6/portfolio) (no framework, no build step; the robot's face is a real port of `face.py` from my companion-robot firmware)

---

Lead Technician of the R&D Club at Sipna CoET, and an Electronics & Telecommunication
diploma graduate from Government Polytechnic Amravati. 1st in the hardware division at
CMR Hackfest 3.0.

I use AI tools as engineering assistants — research, debugging, documentation and a fair
amount of the code. Worth saying plainly on a page attached to my commits. I verify the
output, make the engineering calls, and test the hardware myself, which is the part no
model does for me.

**bhavesh.waghmare05@gmail.com** — hardware that only fails in the field is my favourite
kind of problem.
