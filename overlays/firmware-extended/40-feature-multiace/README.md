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


License: GPL-3.0 (same as PAXX).
