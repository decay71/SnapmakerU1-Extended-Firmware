# SnapmakerU1-Extended-Firmware (decay71 fork)

PAXX-based firmware for the Snapmaker U1 with **multiACE 0.99.2** pre-installed (Anycubic ACE Pro V1 + V2 / ACE 2 support, web UI, online updater).

This repository contains the **firmware source code only**, provided to satisfy the GPL-3.0 Corresponding-Source requirement (§6(d)).


## Build from source

```sh
git clone https://github.com/decay71/SnapmakerU1-Extended-Firmware
cd SnapmakerU1-Extended-Firmware
sudo ./dev.sh make PROFILE=extended build

```

## ℹ️ A quick note before you flash

multiACE firmware is a **community project** — built by hobbyists, for hobbyists. Worth taking a moment before you flash:

- The project is **not endorsed or supported by Snapmaker, Anycubic, or the PAXX upstream maintainers** — and hasn't been verified by them either.
- Running custom firmware **may affect your manufacturer warranty**. Snapmaker support generally cannot help with a modified printer.
- As with any firmware flash, an interrupted process can leave the printer in a state you'd need SSH access or a stock image to recover from. Rare in practice, but worth knowing.
- This software comes **without warranty** — formally covered by GPL-3.0 §15–17. Translation: I do my best, but the responsibility for using it stays with you.

If any of that doesn't sit right, no worries — the Snapmaker stock firmware and the official PAXX builds remain available. If you're on board: have fun, and feedback / issues are always welcome.
