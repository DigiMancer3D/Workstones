# Workstones

[![GitHub Repo stars](https://img.shields.io/github/stars/digimancer3d/workstones?style=social)](https://github.com/digimancer3d/workstones) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![Issues](https://img.shields.io/github/issues/digimancer3d/workstones)](https://github.com/digimancer3d/workstones/issues)

### Revitalizing Aging Hardware: From Scrap to Productive Powerhouse! 🛠️✨

**Workstones** is your ultimate guide to breathing new life into old, locked, or underpowered machines (Linux 16–24+ compatible). We're talking dusty laptops, forgotten desktops, and "dead" hardware transformed into reliable workstations for home offices, creative projects, or even VTubing setups.

- **Why Workstones?** Unlike the original [Workstone](https://github.com/digimancer3d/workstone) repo (optimized for portable thumbstick-PCs), **Workstones** focuses on full installs on standard (but older) hardware. Start with a PeppermintOS (FL-Devuan) live USB for a deep clean and hardware reset, then overlay Kubuntu for a polished, feature-rich OS. Boom! Your relic is reborn! 💥

This method is battle-tested on Kubuntu 22 & 24. It's generic enough for most Ubuntu/Debian derivatives, but tweak commands for your distro.

> **Pro Tip:** Always back up data before wiping drives. We're restoring hope, not causing heartbreak! ❤️

</br></br>

## 📋 Table of Contents
- [Prerequisites](#prerequisites)
- [Step 1: Prepare Your Bootable USBs](#step-1-prepare-your-bootable-usbs)
- [Step 2: Restore with PeppermintOS](#step-2-restore-with-peppermintos)
- [Step 3: Overlay Kubuntu](#step-3-overlay-kubuntu)
- [Post-Install Setup](#post-install-setup)
  - [Enable Universe Repo & exFAT Support](#enable-universe-repo--exfat-support)
  - [Display Drivers (DisplayLink)](#display-drivers-displaylink)
- [Install Essential Apps](#install-essential-apps)
  - [Production & Media](#production--media)
  - [Browsers](#browsers)
  - [Creative Tools](#creative-tools)
  - [Video Editing](#video-editing)
  - [Gaming](#gaming)
  - [Audio & Synthesis](#audio--synthesis)
  - [Messaging](#messaging)
- [VTuber Setup: SysMocap & Tips](#vtuber-setup-sysmocap--tips-)
  - [Installation](#installation)
  - [Running & Flags](#running--flags)
  - [Troubleshooting White Screen Errors](#troubleshooting-white-screen-errors)
- [Final Touches](#final-touches)
- [Contributing](#contributing)
- [License](#license)

</br></br>

## Prerequisites
- A USB drive (8GB+ for each ISO).
- Target machine capable of booting Linux (UEFI preferred; handle Secure Boot as noted).
- Internet connection for downloads and updates.
- Rufus 4.5+ (for UEFI/MBR compatibility): [Download Rufus](https://rufus.ie/en/).

| Tool/ISO | Source | Notes |
|----------|--------|-------|
| PeppermintOS (FL-Devuan) | [peppermintos.com](https://peppermintos.com/download-and-install/) | For initial hardware reset. |
| Kubuntu | [kubuntu.org](https://kubuntu.org/download/) | Main OS; select full install for drivers. |
| Rufus | [rufus.ie](https://rufus.ie/en/) | Handles Secure Boot + MBR; avoid Ventoy if Secure Boot is on. |

</br></br>

## Step 1: Prepare Your Bootable USBs
1. Download ISOs.
2. Use Rufus to burn each to a USB:
   - Select ISO > Start (defaults work for UEFI).
   - **Warning:** Rufus ensures DisplayLink drivers play nice with Secure Boot—skip if using Ventoy (may require disabling Secure Boot).

## Step 2: Restore with PeppermintOS
1. Insert Peppermint USB, boot into BIOS (ESC/F2/F10/F12/DEL).
2. Set USB as first boot device > Save & Exit.
3. Boot live session > Install (wipe drive for full reset; select "fully loaded" for drivers).
   - This "washes" hardware—cleans configs, resets peripherals.

**Expected Time:** 20–45 mins. Reboot when done.

</br></br>

## Step 3: Overlay Kubuntu
1. Insert Kubuntu USB, re-enter BIOS, set USB first.
2. Boot live > Install (wipe drive to "wash over" Peppermint, or "rinse" alongside if dual-boot).
3. Choose full install for proprietary drivers.

**Expected Time:** 30–60 mins. Welcome to your refreshed Kubuntu!

</br><hr></br>

## Post-Install Setup

### Enable Universe Repo & exFAT Support
Unlocks extra packages and exFAT mounts (for external HDDs).

```bash
sudo add-apt-repository universe
sudo apt update
sudo apt install exfat-fuse exfat-utils  # For Linux 20–; skip if on 22+
```

</br></br>

### Display Drivers (DisplayLink)
For multi-monitor setups (e.g., J5create adapters). Kubuntu 22+ handles most GPUs natively so, test first!

1. Download Ubuntu driver: [Synaptics DisplayLink](https://www.synaptics.com/products/displaylink-graphics/downloads/ubuntu).
2. Extract ZIP > Make `.run` executable (right-click > Properties).
3. Run:
   ```bash
   cd ~/Downloads  # Adjust path as needed
   sudo apt update && sudo apt dist-upgrade
   sudo ./displaylink-driver-*.run
   ```
4. Handle Secure Boot prompt: Set temp password > Reboot > Enroll MOK (select "Enroll" in blue menu) > Reboot.

**Troubleshoot:** If no prompt/errors, skip: you likely don't need it. Readjust BIOS boot order post-reboot.

</br><hr></br>

## Install Essential Apps
Run commands in order (use ↑ arrow to reuse `sudo apt install` prompts). Skip as needed. These were tested on Kubuntu 24.

</br></br>

### Production & Media
| App | Command | Purpose |
|-----|---------|---------|
| VLC | `sudo apt install vlc` | Media player extraordinaire. |
| OBS Studio | `sudo apt install obs-studio` | Streaming/broadcasting beast. |

</br></br>

### Browsers
| App | Commands | Purpose |
|-----|----------|---------|
| LibreWolf | `sudo apt install librewolf` | Privacy-hardened Firefox. |
| Ungoogled Chromium | `sudo add-apt-repository ppa:xtradeb/apps`<br>`sudo apt update`<br>`sudo apt install ungoogled-chromium`<br>`ungoogled-chromium` | De-Googled Chrome for devs/creators. |

</br></br>

### Creative Tools
| App | Command | Purpose |
|-----|---------|---------|
| Blender | `sudo apt install blender` | 3D modeling & animation. |
| Inkscape | `sudo apt install inkscape` | Vector graphics editor. |
| GIMP | `sudo apt install gimp` | Raster image powerhouse. |

</br></br>

### Video Editing
| App | Command | Purpose |
|-----|---------|---------|
| Kdenlive | `sudo apt install kdenlive` | Non-linear video editor. |
| Shotcut | `sudo apt install shotcut` | Cross-platform video trimmer. |

</br></br>

### Gaming
| App | Commands | Purpose |
|-----|----------|---------|
| Lutris | `sudo apt install lutris` | Game launcher & Wine wrapper. |
| Wine | `sudo apt install winehq-devel` | Run Windows apps/games. |
| Steam | `sudo apt install software-properties-common apt-transport-https curl -y`<br>`sudo apt install steam-installer steam-devices` | Valve's gaming ecosystem. |

</br></br>

### Audio & Synthesis
| App | Commands | Purpose |
|-----|----------|---------|
| Audacity | `sudo apt install audacity` | Audio recording/editing. |
| Yoshimi | Download `.tar.gz` from [GitHub](https://github.com/Yoshimi/yoshimi/tags).<br>`cd ~/Downloads`<br>`sudo tar -xvzf yoshimi-*.tar.gz`<br>`cd yoshimi-*`<br>`sudo make install` | Polyphonic synthesizer. |

</br></br>

### Messaging
| App | Commands | Purpose |
|-----|----------|---------|
| Telegram Desktop | `sudo snap install telegram-desktop` | Cloud-synced messenger (great for file transfer). |
| Signal Desktop | `curl -fsSL https://updates.signal.org/desktop/apt/keys.asc \| sudo gpg --dearmor -o /etc/apt/keyrings/signal-desktop-keyring.gpg`<br>`echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/signal-desktop-keyring.gpg] https://updates.signal.org/desktop/apt xenial main" \| sudo tee /etc/apt/sources.list.d/signal.list`<br>`sudo apt update && sudo apt install signal-desktop` | Secure, end-to-end encrypted chat. |

</br><hr></br>

## VTuber Setup: SysMocap & Tips 🎭
SysMocap (motion capture for VTubing) shines on Linux via Lutris/Wine. Pair with OBS for streams!

</br></br>

### Installation
```bash
git clone https://github.com/xianfei/SysMocap.git  # No sudo
sudo apt install nodejs
cd SysMocap
npm install  # No sudo; skips audits—SysMocap deps may flag vulnerabilities
```

</br></br>

### Running & Flags
Launch with GPU-optimized flags (tune for your hardware; e.g., NVIDIA/AMD/Intel):
```bash
npm start -- --disable-gpu-sandbox  # Basic launch; add for white screen fix
# Or for better perf: npm start -- --enable-gpu-rasterization --ignore-gpu-blacklist
```
- **System Flags:** Set via export before run: `export ELECTRON_DISABLE_SANDBOX=1` (for Electron apps like SysMocap on restricted setups).
- Permissions: `chmod +x ./start.sh` if script exists; run as non-root.

</br></br>

**Lutris/Wine Tips (Alternative Runner):**
1. Install via Lutris > Add MSI/EXE > Use Wine-GE runner.
2. Runners: Ubuntu 22 rebuild (no esync/fsync for stability).
3. Winetricks: Core fonts, .NET, DirectX, codecs.
4. Fonts: Install TTFs for UI polish.
5. Test: Launch > Configure cams > Exit > Tweak runner > Relaunch.

</br></br>

### Troubleshooting White Screen Errors
Common on Kubuntu 24 (Vue.js rendering clash with GPU/Node). Fixes in order:

| Issue | Cause | Fix |
|-------|-------|-----|
| White screen on launch | Vue3 global conflict (SysMocap uses Vue2) | Lock deps in `package.json`: `"vue": "^2.7.0"`. Then `rm -rf node_modules && npm install`. |
| Blank Vue render | GPU blacklist or sandbox | Add flags: `npm start -- --no-sandbox --disable-web-security`. Or export `NODE_OPTIONS="--max-old-space-size=4096"`. |
| Persistent freeze | Kernel/GPU mismatch | Update kernel: `sudo apt install linux-generic-hwe-24.04`. Reboot. Test with `prime-run` (NVIDIA). |
| Install hang | NPM audit false positives | Skip: `npm install --no-audit --legacy-peer-deps`. |
| No cam detection | Permissions/USB | `sudo usermod -a -G video $USER` > Log out/in. |

If stuck, check logs: `npm start --verbose`. Community: [SysMocap GitHub Issues](https://github.com/xianfei/SysMocap/issues).

</br><hr></br>

## Final Touches
1. Reboot: `sudo reboot`.
2. Update everything: `sudo apt update && sudo apt full-upgrade`.
3. Customize: Themes in System Settings > Add Flatpaks via Discover for extras.
4. **Thumbstick Mode?** For portable use, see the original [Workstone](https://github.com/digimancer3d/workstone) repo—boot from USB without full install.

</br></br>

Your machine is now a **Workstone**! 🚀 Share your revivals in Issues.

</br></br>

## Contributing
Fork > Branch > PR. Ideas? Open an issue. Let's make more hardware immortal! 🌟

</br></br>

## License
MIT © [DigiMancer3D](https://github.com/digimancer3d). See [LICENSE](LICENSE).

</br></br></hr></br>
