# multiACE PAXX overlay

This folder is a drop-in overlay for the
[PAXX SnapmakerU1-Extended-Firmware](https://github.com/paxx12-snapmaker-u1/SnapmakerU1-Extended-Firmware)
build system. It adds multiACE support to a PAXX firmware image.

## Usage

1. Clone or fork the PAXX firmware repo.
2. Copy this `40-feature-multiace/` directory into
   `overlays/firmware-extended/40-feature-multiace/` of your PAXX fork.
3. From the PAXX fork root, run:
   ```sh
   make PROFILE=extended build
   ```
   (Docker required — see PAXX `docs/development.md`.)
4. The resulting `firmware/firmware.bin` includes multiACE.

## What's in the image

- Klipper extras (`ace.py`, protocol handlers, FA modules) at
  `/home/lava/klipper/klippy/extras/`
- Extruder kinematics at `/home/lava/klipper/klippy/kinematics/`
- `[include extended/ace.cfg]` wired into the user's `printer.cfg` via
  PAXX's firmware-config tweak system (toggle in the PAXX UI)
- The full multiACE source bundle under `/home/lava/multiace/`, but
  the Web service is **not** started by default — see below.

## Optional Web UI

The Web dashboard is bundled but dormant. To enable it after flashing:

```sh
ssh root@<printer>
bash /home/lava/multiace/install_web.sh
```

Sets up a Python venv with FastAPI + uvicorn, installs an nginx snippet
on the existing Fluidd port, starts the multiace-web service.

Reach it at `http://<printer-ip>/multiace/`.

To remove later:
```sh
bash /home/lava/multiace/install_web.sh --remove
```

## Source

multiACE source lives at https://github.com/stasia-berg/dirk-3d
(see the multiACE version stamped into `ace.py`).

License: GPL-3.0 (same as PAXX).
