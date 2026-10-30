# 9GNetDiag

**A complete system monitor and network toolkit for Android.**
See what your phone is really doing — CPU, GPU, memory, temperatures, battery power, compass, GPS, clock accuracy,
every sensor, and the busiest apps — and diagnose any Wi-Fi, mobile or internet problem, all in one app.

*Copyright © R.N.K 9G5AR, RadioSport · Version 1.04*

---

## Contents
1. [What you get](#what-you-get)
2. [Getting started](#getting-started)
3. [System Monitor](#system-monitor) — the ten tabs
4. [Network tools](#network-tools)
5. [Permissions](#permissions-and-why-the-app-asks-for-them)
6. [Seeing every running app (Shizuku)](#seeing-every-running-app-shizuku)
7. [What Android does not allow](#what-android-does-not-allow)
8. [Troubleshooting](#troubleshooting)
9. [Privacy](#privacy)
10. [License](#license)

---

## What you get

| Part of the app | What it is for |
|---|---|
| **System Monitor** | Live dials and graphs for CPU, GPU, RAM, storage, temperature, battery power, compass, GPS, clock accuracy, all sensors and the busiest processes |
| **Network Doctor** | One tap checks your connection step by step and tells you in plain English what is wrong and how to fix it |
| **Wi-Fi tools** | Wi-Fi Analyzer (channels, access points) and Signal Meter |
| **Network tools** | Ping, Traceroute, DNS, HTTP / TLS, Speed Test, Network Scanner, Port Scanner |
| **Device info** | Connection details, Traffic Monitor, Cellular |
| **Utilities** | Subnet calculator, Whois, public IP, NTP, Wake-on-LAN, TCP client, MAC lookup, port reference |

The app works with the phone's light or dark theme automatically.

## Getting started

1. **Install** the APK (`9GNetdiag_v1.04_release.apk`). You may need to allow *Install unknown apps* for your file manager or browser.
2. **Open 9GNetDiag.** The Home screen shows your connection status at the top (Online / No internet / Offline, network name, IP address, signal strength) followed by tool tiles in groups: *Diagnose, Wi-Fi, Discover, Device, Utilities*.
3. **Tap a tile** to open a tool. Tap the **back arrow** to return.
4. Many tools have a **Copy** and **Share** button in the top bar that sends the results as text.

Requires **Android 8.0 or newer**. Use a real phone — emulators have no Wi-Fi radio, GPS, sensors or modem.

### Tabs and swiping
Screens with tabs — System Monitor, Wi-Fi Analyzer, DNS Tools, HTTP / TLS and Utilities — let you **swipe left and right** to change tab, or tap a tab name. Long tab bars scroll sideways.

---

## System Monitor

Open **System Monitor** from the *Device* group on the Home screen. It has ten tabs. Readings update about once a second, and the app only uses a sensor (GPS, compass, etc.) while the tab that needs it is on screen — so it does not drain your battery in the background.

Colours follow one rule everywhere: **green = fine, amber = busy / warm, red = high**.

### 1 · Overview
Everything at a glance:
- **Dials** for CPU, GPU, RAM, temperature, battery, storage, and — when connected — Wi-Fi and cellular signal in dBm.
- A **mini compass** with magnetic field strength and tilt.
- **Environment** readings your phone has sensors for: light (lux), proximity, air pressure and barometric altitude, humidity, ambient temperature.
- A **status** line: thermal state, battery saver, low memory, charging state, power draw, uptime.

### 2 · CPU · GPU
- **CPU:** load history graph, load of this app, average clock speed, and a bar for **every core** showing its current clock (or load, where Android allows). Also hardware name, number of cores online, governor and clock range.
- **GPU:** graphics chip name, vendor, OpenGL version, and — on phones that expose it — GPU load and clock speed with a history graph.

### 3 · Processes (a "top" for Android)
Shows which processes use the most CPU, ranked, each with a coloured bar, its **user + kernel** split, and the app's name where Android allows it. A red banner appears when one process uses 10 % or more (red at 25 %). Also shown: total CPU, load average, and this app's own busiest threads.

For the **full list of every app** you need Shizuku or root — see [Seeing every running app](#seeing-every-running-app-shizuku). Without them Android only lets the app see itself, and the tab says so.

The **Data source** box lets you choose:
- **Auto** – uses Shizuku when connected (recommended)
- **Shizuku** – force Shizuku
- **Root** – use root (`su`) on a rooted phone
- **Basic** – only what Android shows any app

Percentages are the share of the *whole* CPU (all cores together = 100 %). When the source is Shizuku or root, the numbers are live (measured over the last second).

### 4 · Memory
RAM used, swap / zRAM, internal storage, a RAM history graph, a **low-memory warning**, system RAM details (total, used, available, cached), and how much memory this app itself uses.

### 5 · Thermal · Power
- Dials for **battery temperature**, hottest sensor, **throttle margin** (how close Android is to slowing the phone down to cool it — 100 % means it is about to), battery level, **power draw in watts** and voltage.
- Android's own **thermal status** (None → Light → Moderate → Severe → Critical) and Battery Saver state.
- Temperature and **battery current** graphs (positive = charging, negative = discharging).
- Battery details: health, chemistry, charge counter, estimated full capacity.
- Thermal zones (internal temperature sensors) on phones that allow reading them.

### 6 · Compass
- A **rotating compass card** with the heading in degrees and direction (N, NNE, …).
- **Magnetic or true north.** True north needs location permission once (the app uses your last known position to work out the local declination); a switch lets you choose.
- **Accuracy warnings.** If the compass is unreliable, wave the phone in a **figure-8**. A warning also appears near metal, magnets or speakers (normal Earth field is about 25–65 µT).
- **Spirit level** — lay the phone flat; the bubble turns green within ±1.5°.
- **Motion:** g-force and rotation-rate dials.
- Environment readings (light, pressure, …).

Hold the phone flat for a normal compass; held upright it points where the back camera faces.

### 7 · GPS
Needs Location permission and the Location switch on. Go **outdoors** — a first fix can take from seconds to a few minutes.
- **Status:** 2D / 3D fix, time to first fix, and dials for **satellites used**, **accuracy** and **speed**.
- **Position:** latitude / longitude in decimal and degrees-minutes-seconds, the **Maidenhead grid locator** (6 and 8 characters, handy for amateur radio), altitude, speed, course, accuracy and GPS time in UTC. A button copies the coordinates.
- **Sky view:** a map of every satellite overhead (north at top, centre = straight up). Filled dots are used for your position, hollow rings are only tracked. Colour shows signal strength.
- **Signal strength:** one **thin vertical line per satellite**, labelled by constellation and number (G = GPS, R = GLONASS, E = Galileo, C = BeiDou, J = QZSS, S = SBAS, I = NavIC). Taller line = stronger signal (dB-Hz). Bright with a dot = used in the fix.
- Counts per constellation and accuracy / speed history graphs.

### 8 · Clock
Checks how accurate your phone's clock is.
- **Phone clock** in local time and UTC, with seconds.
- **Check against a time server (NTP):** choose a server and tap **Check clock now**. You get the offset ("+0.35 s, phone is behind"), round-trip time, and a verdict: *Excellent* (under 0.1 s), *Good*, *Drifting*, *Out of sync*.
- **True time:** a corrected clock based on the check — it keeps running accurately even if the phone clock is wrong. Useful for logging in UTC.
- **GPS time:** compares the phone clock with satellite time (needs a GPS fix; accuracy roughly ±0.1–0.5 s).
- **Synchronise the phone clock:** shows whether *Automatic time* and *Automatic time zone* are on and opens **Date & time settings** in one tap. See [What Android does not allow](#what-android-does-not-allow) for why the app cannot set the time itself.
- *Rooted phones only:* an optional **Set system time now (root)** button, with a confirmation.
- Time-zone details: zone, UTC offset, daylight saving, 12 / 24-hour format.

### 9 · Sensors
A live list of **every hardware sensor** in your phone — accelerometer, gyroscope, magnetometer, light, proximity, pressure, humidity, step counter, and any vendor-specific ones — each with its current reading, accuracy, range, resolution and power use. Step counter and step detector need the *Physical activity* permission (the tab offers a button).

### 10 · System
Device model and Android version, security patch level, chip, kernel, **uptime**, awake time and deep-sleep time; display resolution, density, **refresh rate**, brightness, HDR and wide-colour support; and current Wi-Fi and cellular signal.

### Share a snapshot
The **Share** button in the System Monitor top bar sends a text report of everything — CPU, memory, battery, top processes, GPS, clock, compass and every sensor — handy for support or for comparing phones.

---

## Network tools

### Diagnose
- **Network Doctor** – one tap runs a 12-step check (link, Wi-Fi signal, IP address, gateway, DNS, internet access, captive portal, HTTPS and certificates, latency and packet loss, IPv6, clock) and gives a verdict with advice. Share the report as text.
- **Ping** – ICMP or TCP ping with a live graph; shows minimum / average / maximum, jitter and packet loss.
- **Traceroute** – shows every hop to a host with name and delay, plus a per-hop graph.
- **DNS Tools** – look up A, AAAA, CNAME, MX, NS, TXT, SOA, PTR, SRV, CAA records on any DNS server, do reverse lookups, and **benchmark resolvers** to find the fastest. *(swipe between Lookup and Benchmark)*
- **HTTP / TLS** – follow redirects and see a timing waterfall (DNS, connect, TLS, first byte, download), headers, and inspect a website's certificate chain, expiry and supported TLS versions.
- **Speed Test** – latency, jitter, download and upload with a live graph (Cloudflare by default, or your own server).

### Wi-Fi
- **Wi-Fi Analyzer** – *Channels* graph for 2.4 / 5 / 6 GHz with congestion bars and recommended channels; *Access points* list (security, Wi-Fi standard, vendor, estimated distance, band filter); *Signal over time* graph. Export as CSV.
- **Signal Meter** – big live signal gauge with min / avg / max, link speed, estimated distance, and an **audible finder tone** that beeps faster as the signal gets stronger — walk around to find the best spot.

### Discover
- **Network Scanner** – finds devices on your network with names, MAC addresses, vendors and services. Tap a device to ping it or scan its ports.
- **Port Scanner** – checks which TCP ports are open, with service banners; presets or custom ranges.

### Device
- **Connection Info** – IP, subnet mask, gateway, DNS, MTU, Private DNS, proxy, VPN, IPv6, Wi-Fi link details, network interfaces, public IP and provider.
- **Traffic Monitor** – live throughput graph and data counters.
- **Cellular** – operator, network type, roaming, SIM state, signal history, serving and neighbouring cells.

### Utilities
Subnet calculator · public IP · Whois · NTP offset · Wake-on-LAN · raw TCP client · MAC vendor lookup · port reference. *(swipe between them)*

---

## Permissions and why the app asks for them

The app asks only when a feature needs it, and works without them (just with fewer readings).

| Permission | Used for |
|---|---|
| **Location** | Required by Android to list nearby Wi-Fi networks; GPS tab; true-north compass. Your location is never stored or sent. |
| **Nearby Wi-Fi devices** (Android 13+) | Wi-Fi Analyzer |
| **Phone state** | Cellular network type and cell details |
| **Physical activity** | Step counter / step detector on the Sensors tab only |
| **Internet / network state** | All network tools |
| **Shizuku** (optional) | Full process list on the Processes tab |

**Location switch:** Android also needs the *Location* quick-setting turned **on** for Wi-Fi scanning and GPS. The app shows a button to open the setting if it is off.

---

## Seeing every running app (Shizuku)

By default Android lets an app see only itself. To make the **Processes** tab list *every* app **without root**, use **Shizuku**, a free helper app that gives other apps limited developer-level access.

1. **Install Shizuku** on the phone (from its official project page or app store).
2. **Start Shizuku.** Open it and follow its instructions — the usual way is *Wireless debugging* (Android 11+), or a one-time USB command from a computer. It must be started again after each phone reboot.
3. Open **9GNetDiag ▸ System Monitor ▸ Processes**, scroll to **Data source**.
4. Tap **Grant Shizuku access** and allow it in Shizuku's dialog.
5. The header changes to **Full list • Shizuku (adb shell)** and every process appears, with live numbers.

If Shizuku is not running the tab tells you, and has an **Open Shizuku** button. On a rooted phone you can choose **Root** instead.

---

## What Android does not allow

Some things are blocked by Android itself, not by this app. 9GNetDiag works around them where possible and always tells you on screen when it does.

| Limit | What happens |
|---|---|
| **Total CPU load** is hidden from normal apps | The CPU dial shows an estimate from core clock speeds (marked "clock"); this app's own load is exact. With Shizuku or root the Processes tab shows true live load. |
| **GPU load, clock and some temperature sensors** are hidden on many phones | The GPU tab still shows chip and OpenGL details; Thermal uses the battery sensor and Android's thermal status. |
| **Other apps' processes** are hidden | Use Shizuku or root (see above). |
| **Setting the system time** is reserved for the system | The Clock tab measures the error, shows the corrected time and opens Date & time settings so you can switch on automatic time. Rooted phones get an extra button. |
| **Wi-Fi scans are limited** to about 4 every 2 minutes (Android 9+) | Turn off *Wi-Fi scan throttling* in Developer options for continuous updates. |
| **Other devices' MAC addresses** are hidden (Android 10+) | The scanner may show fewer vendors; names via NetBIOS / mDNS still work. |
| **Ping and traceroute** use the system ping tool | If your phone blocks it, use **TCP** mode in Ping. |

---

## Troubleshooting

**Wi-Fi Analyzer shows nothing.** Allow Location permission *and* switch the Location setting on.

**GPS never gets a fix.** Go outside with a clear sky, make sure Location is on, and wait a few minutes. Cloud and buildings block signals. Check the Sky view — you need at least 4 satellites used.

**The compass is wrong or the warning keeps showing.** Move away from magnets, speaker cases, car bodies and metal desks, then wave the phone in a figure-8. Remove magnetic phone cases.

**Processes tab shows only a few entries.** Normal without Shizuku or root — see [Seeing every running app](#seeing-every-running-app-shizuku).

**"Shizuku not running".** Open Shizuku and start it again (it stops when the phone reboots).

**Google Play services (or another system service) shows high CPU.** Services such as Play services serve location, sensors and app scanning for everyone. Watch the Processes tab for a minute with this app on that tab — the app switches its own GPS and sensors off there. If it stays high, check *Settings ▸ Battery* and *Location ▸ Google Location Accuracy*.

**The phone's clock is wrong.** Open the Clock tab ▸ **Open Date & time settings** ▸ turn on *Set time automatically*.

**Speed test, public IP or Whois fail.** These need internet access; try another network.

**Ping to a device fails but it is on.** Many devices and firewalls ignore ping. Try TCP mode or scan its ports.

---

## Privacy

- 9GNetDiag has **no account, no ads and no tracking**, and does not upload your readings anywhere.
- Your **location is used only on screen** and is never stored or sent.
- Some tools contact outside servers because that is their job: Speed Test (Cloudflare), public IP / provider lookup (ipify, ipinfo.io), Whois (public Whois servers), NTP time checks (pool.ntp.org, Google, Cloudflare, Android, Windows), and internet-access checks (Google, Cloudflare). Nothing is sent unless you use these tools or the Network Doctor.
- **Only scan networks and devices you own or have permission to test.**

## License

9GNetDiag is free software: you can redistribute it and/or modify it under the terms of the
**GNU General Public License, version 3** as published by the Free Software Foundation.
It is distributed in the hope that it will be useful, but **without any warranty**; without even the implied
warranty of merchantability or fitness for a particular purpose. The full text is in
[`LICENSE.md`](LICENSE.md), or see <https://www.gnu.org/licenses/gpl-3.0.html>.

Copyright © R.N.K 9G5AR, RadioSport.

The app uses the open-source Shizuku API (Apache License 2.0) and AndroidX / Jetpack Compose libraries
(Apache License 2.0), which are compatible with the GPL.

---

*9GNetDiag — Copyright © R.N.K 9G5AR, RadioSport. Developers: see `BUILDING.md`.*
