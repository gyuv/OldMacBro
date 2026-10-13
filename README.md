<div align="center">

<img src="docs/assets/hero.svg" alt="OldMacBro: Revive your Intel Mac" width="100%"/>

<br/>

<img src="https://img.shields.io/badge/macOS-12%2B-111827?style=for-the-badge&logo=apple&logoColor=white" alt="macOS 12+"/>
<img src="https://img.shields.io/badge/Intel-x86__64-0071C5?style=for-the-badge&logo=intel&logoColor=white" alt="Intel x86_64"/>
<img src="https://img.shields.io/badge/Apple%20Silicon-M1%E2%80%93M4-A2AAAD?style=for-the-badge&logo=apple&logoColor=white" alt="Apple Silicon M1–M4"/>
<img src="https://img.shields.io/badge/Windows%20%26%20Server-Setup%20%7C%20portable-0078D4?style=for-the-badge&logo=windows&logoColor=white" alt="Windows and Windows Server"/>
<img src="https://img.shields.io/github/v/release/gyuv/oldmacbro?style=for-the-badge&color=5CC7FF&label=Version" alt="Latest version"/>
<img src="https://img.shields.io/github/downloads/gyuv/oldmacbro/total?style=for-the-badge&color=54EDB8&label=Downloads" alt="Total downloads"/>
<img src="https://img.shields.io/badge/100%25-Native-9E7AFF?style=for-the-badge&logo=swift&logoColor=white" alt="100% native"/>

# OldMacBro

### Your 2017 MacBook Air isn't slow. It's just carrying too much.
**OldMacBro finds what's weighing it down and takes it off, in one click.**

<a href="https://github.com/gyuv/oldmacbro/releases/latest">
  <img src="https://img.shields.io/badge/%E2%AC%87%20Download%20OldMacBro-Mac%20%C2%B7%20Windows-54EDB8?style=for-the-badge&labelColor=0b1020" alt="Download for Mac or Windows" height="44"/>
</a>

<sub>Free · Native Swift · No Electron · Tuned for the MacBook Air 13" (2017) · Native on Apple Silicon too · Now on Windows & Windows Server</sub>

<sub>by <b>Uv</b> · <a href="https://github.com/gyuv">@gyuv</a></sub>

</div>

<br/>

> [!NOTE]
> This repository hosts **downloads, documentation and issue tracking** for OldMacBro. The source code is closed. See [About this repository](#-about-this-repository).

---

## 📑 Contents

- [Download & install](#-download--install)
- [Which edition do I need?](#-which-edition-do-i-need)
- [Features](#-features)
- [OldMacBro for Windows](#-oldmacbro-for-windows--windows-server)
- [Why native?](#-why-native)
- [Requirements](#-requirements)
- [Safety promises](#-safety-promises)
- [FAQ](#-faq)
- [Changelog](CHANGELOG.md)
- [Reporting bugs](#-reporting-bugs--requesting-features)
- [About this repository](#-about-this-repository)

---

## ⬇️ Download & install

Latest: **v1.8.0**. Get it from the **[Releases page](https://github.com/gyuv/oldmacbro/releases/latest)**:

| Your computer | Installer | Portable (no install) |
|---|---|---|
| 💻 **Intel Mac** (*Processor* says Intel) | `OldMacBro-1.8.0-Intel.dmg` | `OldMacBro-1.8.0-Intel-portable.zip` |
| 🍏 **Apple Silicon Mac** (*Chip* says Apple M1–M4) | `OldMacBro-1.8.0-AppleSilicon.dmg` | `OldMacBro-1.8.0-AppleSilicon-portable.zip` |
| 🪟 **Windows 10/11 or Windows Server 2012 R2–2025** | `OldMacBro-Windows-1.8.0-Setup.exe` | `OldMacBro-Windows-1.8.0-portable.zip` |

**Mac**

1. **Open** the DMG and drag **OldMacBro** onto **Applications** (or unzip the portable version anywhere).
2. **First launch:** right-click **OldMacBro.app** and choose **Open**, then **Open** again.<br/>
   <sub>You only do this once. The app is ad-hoc signed and doesn't come from the App Store, so Gatekeeper asks first.</sub>
3. Click the **chip icon** in your menu bar, then **⚡ Smart Boost**. Done.

**Windows:** run the Setup, or unzip the portable version and run `OldMacBro.exe` (it asks for admin once). See [OldMacBro for Windows](#-oldmacbro-for-windows--windows-server).

<details>
<summary><b>Recommended one-time setup (Mac)</b></summary>
<br/>

- **Settings → Privileged Helper → Install.** One password prompt lets OldMacBro control the fans, toggle Turbo Boost and run admin clean-ups without asking every time.
- **Tweaks → Apply recommended** for a permanently snappier feel.
- **Settings → Date & Time → Sync now** with *auto-correct at every startup* ticked, if your Mac loses the date when the battery runs flat.
- **Uninstaller blocked by macOS?** Allow OldMacBro in **System Settings → Privacy & Security → Full Disk Access**, and **App Management** on macOS 13 or later.
</details>

<details>
<summary><b>Updating</b></summary>
<br/>

From v1.6.0 OldMacBro **updates itself** on Mac and Windows: new releases download in the background, you see **Update available**, and one click on **Restart to update** installs it. Your settings are kept.

Older versions: quit OldMacBro, install the new version over the old one and choose **Replace**.
</details>

<details>
<summary><b>Verifying your download (optional)</b></summary>
<br/>

Each release includes `SHA256SUMS.txt`. Compare with:

```bash
shasum -a 256 ~/Downloads/OldMacBro-*
```
</details>

---

## 🧭 Which edition do I need?

Click the Apple menu  → **About This Mac**:

| You see | Download | Built for |
|---|---|---|
| **Processor:** Intel Core … | `OldMacBro-x.y.z-Intel.dmg` | x86_64, tuned for the MacBook Air 2017 |
| **Chip:** Apple M1, M2, M3 or M4 | `OldMacBro-x.y.z-AppleSilicon.dmg` | Native arm64, no Rosetta |

Each edition also comes as a portable zip (`-Intel-portable.zip`, `-AppleSilicon-portable.zip`).

<sub>Two editions ship starting with v1.4.0. Releases up to v1.3.0 have a single Intel DMG.</sub>

---

## ✨ Features

### 🍏 Menu bar

<table>
<tr>
<td width="440" valign="top">
<img src="docs/assets/menubar.svg" alt="OldMacBro menu bar panel" width="420"/>
</td>
<td valign="top">

- **Live status item** with CPU %, temperature and RAM. The glyph changes colour as the Mac heats up.
- **Popover** with three rings (CPU · RAM · Temp), a bar per core and a fan-profile switch.
- **Quick actions:** Smart Boost, Flush DNS, Quick Clean and Silent Mode.
- **Right-click** for the full action menu.

<sub>🟢 healthy · 🟠 busy · 🔴 needs attention</sub>

</td>
</tr>
</table>

### ⚡ Smart Boost: the one-click lag fix

<img src="docs/assets/smartboost.svg" alt="Smart Boost" width="100%"/>

Smart Boost works out **why** your Mac is lagging right now and fixes that cause:

| Problem it detects | What it does |
|---|---|
| Idle apps hogging memory | Quits them **gracefully** (apps with unsaved work show their normal "Save changes?" prompt) |
| Running hot | Boosts the fans |
| Low disk space | Helps you clear space |
| GPU struggling | Applies light visuals |

Results appear as an **Overview card with Fix buttons**. It never force-kills an app and never deletes caches without asking.

### 🎛 Control Center

<img src="docs/assets/dashboard.svg" alt="OldMacBro Control Center" width="100%"/>

A dark HUD window whose **ambient lighting reacts to CPU heat**.

| Tab | What's inside |
|---|---|
| **Overview** | Health summary, Smart Boost card and one-click fixes |
| **Processes** | Classifies browser and Electron helpers and zombies. **Lower Priority**, **Terminate**, **Force Kill** or **Freeze** (frozen processes resume after 10 minutes or on next launch; no bulk freeze) |
| **Deep Clean** | Caches, logs, Xcode DerivedData, browser caches, orphaned Application Support, Trash and APFS snapshots |
| **Tweaks** | Turn off window animations, speed up Dock and Mission Control, reduce transparency and motion, force App Nap, Low Power Mode, flush DNS and more |
| **Startup** | Audits LaunchAgents, LaunchDaemons and Login Items. **Silent Mode** turns off auto-updaters (Google, Adobe, …) and saves a JSON backup so you can restore them |
| **Thermals** | Every SMC sensor plus fan RPM and fan profiles |
| **Battery** | Cycle count, design vs. full capacity, voltage, watts and temperature |
| **Settings** | Helper install, refresh rates, widgets and appearance |

### 🗑 Uninstaller

Removes apps **together with their hidden data** in `~/Library`, finds leftovers from apps you deleted long ago, and surfaces large forgotten files. Everything goes to the **Trash**, so nothing is lost by accident.

### 🌡 Telemetry & fans

- **CPU:** load per core, PMU speed limit and `thermalState`.
- **SMC sensors:** PECI, CPU die, proximity, heatsink, exhaust, PCH, palm rest and battery.
- **Fans:** current, min, max and target RPM.

| Fan profile | Behaviour |
|---|---|
| **Auto** | Apple's default control |
| **Balanced** | Targets 75 °C |
| **Aggressive Cooling** | Targets 65 °C |
| **Full Blast** | Maximum RPM |
| **Manual** | You pick the speed |

Fan control is **handed back to macOS automatically when OldMacBro quits.**

### 🧠 Memory

Active, wired, compressed, cached, free, swap and memory pressure. Colours follow **pressure**, not how full RAM is, because a full-but-healthy Mac is normal on macOS.

### 🔋 Power

- **Low Power Profile** moves background apps into the Darwin background band (`PRIO_DARWIN_BG`), so the app you're using gets the CPU.
- **Turbo Boost switch** *(Intel edition)* disables Turbo Boost to keep a hot dual-core Broadwell cool and quiet. It uses the signed kext shipped with [Turbo Boost Switcher](https://github.com/rugarciap/Turbo-Boost-Switcher).

### 🍎 Apple Silicon edition

Native arm64, with features made for M-series Macs:

- **P-core / E-core readings** instead of a clock speed, which Apple Silicon doesn't expose to apps.
- **M-series SMC sensors** for real chip temperatures.
- **Fanless-aware Thermals** that make sense on a MacBook Air M1–M4 with no fan.
- **Rosetta detection** in Smart Boost: spots apps running slowly as translated Intel code.
- **Intel-only apps filter** in the Uninstaller, to find apps that still need Rosetta.

### 🖥 Live Dock icon & desktop widgets

- **Dock icon** with three live rings (CPU, RAM, temp), a **badge when the CPU throttles**, and a Dock menu with quick actions.
- **Desktop widgets:** CPU, Memory, Thermal and Battery glass panels. Drag them anywhere, pin them to the desktop or let them float; they remember their positions.

---

## 🕒 Date & Time repair (new in v1.8.0)

When a Mac's battery drains completely, a worn backup supply can make it start up with the wrong date and time, which breaks websites, iCloud, Wi-Fi logins and updates. OldMacBro checks your clock against Apple's time server every time it opens. If it's wrong, a **Correct it** card shows how far off it is and fixes it with one click. Tick **auto-correct at every startup** and the clock is fixed within seconds of joining Wi-Fi, before you even open the app.

<sub>OldMacBro needs an internet connection to know the right time. The hardware fault itself needs a battery repair.</sub>

---

## 🪟 OldMacBro for Windows & Windows Server

Two ways to get it: **`OldMacBro-Windows-x.y.z-Setup.exe`** (normal install with Start menu and uninstaller) or **`OldMacBro-Windows-x.y.z-portable.zip`** (unzip anywhere, even a USB stick, and run `OldMacBro.exe`).

Built for machines shared by many people. **One run, by one administrator, optimises the whole machine and every user on it:**

| | What it does |
|:-:|---|
| 🩺 | **Why is it slow?** diagnoses the real causes: hard drive vs SSD, disk health, disk hogs, driver memory leaks, duplicate antivirus, OneDrive-redirected folders, dead network drives, slow folder opening and low disk space, each with its own Fix button |
| 🚀 | **Revive this PC** applies every safe fix in one go, with live progress |
| ⚡ | **Smart Boost** finds memory pressure, CPU hogs, stale sessions, heavy visuals, background apps and startup bloat, then applies the safe fixes |
| ✦ | **Deep Clean** empties temp files, browser caches, crash dumps and thumbnails in *every* user profile, plus Windows Update leftovers, logs and Recycle Bins |
| ✧ | **Tweaks** for the machine *and* every user's profile, including signed-out users and the Default profile. All backed up, all restorable |
| ◍ | **Users & Sessions** shows everyone signed in (Remote Desktop included); message them or sign out stale sessions |
| ⏻ | **Startup** and **Services** for the machine and each user |
| ▤ | **Apps** uninstaller with search, multi-select and select all |
| ◍ | **Disk Space** analyzer that drills into drives and folders |
| ⚒ | **Tools**: network repair, DISM + SFC system file check with live progress, restore points, nightly maintenance, HTML health report |
| ⇣ | **Auto-update** in the background; one click on *Restart to update* |
| ⌨ | **Command line** for Server Core and Task Scheduler: `/boost`, `/diagnose`, `/clean`, `/tweaks`, `/restore`, `/report` |

Runs on Windows 10 and 11, Windows Server 2012 R2, 2016, 2019, 2022 and 2025 (and Windows 7/8.1 with .NET Framework 4.8).

---

## 🛠 Why native?

Most "Mac cleaner" and system-monitor apps are web pages in a box. On an 8 GB, dual-core 2017 MacBook Air, that box *is* the lag.

| | **OldMacBro** | Typical Electron utility |
|---|---|---|
| UI framework | Swift · AppKit · SwiftUI | Chromium + Node.js |
| CPU architecture | Separate native builds for Intel and Apple Silicon | Often one Intel build run through Rosetta |
| Web views | **None** | The whole app |
| Third-party dependencies | **Zero** | Hundreds of npm packages |
| Hardware access | Direct, via a ~250-line C bridge to the Apple SMC | Shelling out to CLI tools |
| Idle footprint | Tiny, tuned for 8 GB machines | Often several hundred MB |

- **Made for weak GPUs like the Intel HD Graphics 6000.** Animations are cheap, readings update gently, and windows release their memory when closed.
- **Talks to the hardware directly.** Temperatures and fan speeds come straight from the SMC, not from guesses.
- **Nothing phones home.** No telemetry, analytics or accounts. Your data stays on your Mac.

---

## 💻 Requirements

| | |
|---|---|
| **Tuned for** | MacBook Air 13" (2017, `MacBookAir7,2`): dual-core Broadwell i5/i7, Intel HD Graphics 6000, 8 GB LPDDR3 |
| **Also works on** | Most Intel (x86_64) Macs |
| **Apple Silicon** | M1, M2, M3 and M4 Macs, with the Apple Silicon edition |
| **Windows** | Windows 10/11, Windows Server 2012 R2–2025 (.NET Framework 4.8) |
| **macOS** | Monterey (12) or newer, including newer versions installed through [OpenCore Legacy Patcher](https://dortania.github.io/OpenCore-Legacy-Patcher/) |

---

## 🛡 Safety promises

- **Nothing is deleted without you seeing it first.** Removed items go to the **Trash**.
- **Your active app is never touched.** Boosts and watchers ignore whatever you're working in.
- **Nothing stays frozen.** Paused processes resume after 10 minutes, and whenever OldMacBro starts.
- **Everything is reversible.** Silent Mode, tweaks and fan profiles all restore with one click.
- **Apple is back in charge on quit.** Fan control reverts to macOS automatically.

---

## ❓ FAQ

<details>
<summary><b>Will Smart Boost close something I'm working on?</b></summary>
<br/>
No. It only looks at apps you haven't used for the idle time you choose (20 minutes by default), never the app in front. Apps with unsaved work show their normal save prompt.
</details>

<details>
<summary><b>An app stopped responding after I used Processes.</b></summary>
<br/>
Open the menu bar panel and click <b>▶ Resume Frozen</b>, or use <b>Resume all now</b> in Processes. OldMacBro also resumes anything it froze after 10 minutes and every time it launches.
</details>

<details>
<summary><b>Do I need the privileged helper?</b></summary>
<br/>
Only for fan control, Turbo Boost, Low Power Mode and cleaning system folders. Everything else works without it, and you can remove it any time from Settings.
</details>

<details>
<summary><b>Does it work on Apple Silicon?</b></summary>
<br/>
Yes. From v1.4.0, every release has two editions. The <b>Intel</b> edition is tuned for the 2017 MacBook Air (Turbo Boost control, fan curves, Broadwell-aware Smart Boost). The <b>Apple Silicon</b> edition is native arm64 and adds P-core/E-core readings, M-series sensors, fanless-aware Thermals, Rosetta detection and an Intel-only apps filter.
</details>

<details>
<summary><b>I downloaded the wrong edition.</b></summary>
<br/>
Quit OldMacBro, delete it from Applications, and install the other DMG. An Intel build would still run on Apple Silicon through Rosetta, just slower and without the M-series features.
</details>

<details>
<summary><b>macOS says the app "can't be opened" or is "damaged".</b></summary>
<br/>
Right-click the app and choose <b>Open</b>. If that doesn't help, run <code>xattr -dr com.apple.quarantine /Applications/OldMacBro.app</code> in Terminal and open it again.
</details>

<details>
<summary><b>Is the source code available?</b></summary>
<br/>
No. OldMacBro is free to download and use, but the source is private. This repository is for releases, documentation and issues only.
</details>

---

## 🐞 Reporting bugs & requesting features

Use **[Issues](https://github.com/gyuv/oldmacbro/issues/new/choose)**. For bugs, please include:

- Mac model and chip (Apple menu → About This Mac), macOS version, and whether you use OCLP
- Which edition you installed (Intel or Apple Silicon)
- OldMacBro version (menu bar → right-click → About)
- Steps to reproduce, and a screenshot if possible

---

## 📦 About this repository

> [!IMPORTANT]
> **This is a distribution repository. The source code is closed and private.**
>
> This repo contains only the README, documentation images and compiled releases. It exists so you can **download OldMacBro**, **read about it**, and **report issues**. Pull requests with code changes can't be accepted here.

OldMacBro is **free** to download and use. Redistributing, modifying, decompiling or reselling the app is not permitted without written permission from the author. OldMacBro is provided **as is**, with no warranty. It changes fan speeds, process priorities and system settings, so you use it at your own risk.

*OldMacBro is not affiliated with or endorsed by Apple Inc. Mac, MacBook Air and macOS are trademarks of Apple Inc. Intel and Turbo Boost are trademarks of Intel Corporation.*

---

<div align="center">

### Made with ❤️ for Intel Macs that deserve a second life, and Apple Silicon Macs that deserve to stay fast

**Uv** · [github.com/gyuv](https://github.com/gyuv)

<sub>If OldMacBro gave your Mac a second life, a ⭐ on this repo helps others find it.</sub>

</div>
