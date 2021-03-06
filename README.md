# QMK Firmware Build

[![CI](https://github.com/GreatWizard/qmk-firmware-build/actions/workflows/ci.yml/badge.svg)](https://github.com/GreatWizard/qmk-firmware-build/actions/workflows/ci.yml)
[![Publish](https://github.com/GreatWizard/qmk-firmware-build/actions/workflows/publish.yml/badge.svg)](https://github.com/GreatWizard/qmk-firmware-build/actions/workflows/publish.yml)
[![License: GPL-3.0](https://img.shields.io/github/license/GreatWizard/qmk-firmware-build)](https://github.com/GreatWizard/qmk-firmware-build/blob/master/LICENSE.md)
[![Liberapay](https://img.shields.io/liberapay/patrons/GreatWizard.svg?logo=liberapay)](https://liberapay.com/GreatWizard/)

This project uses [QMK Firmware](https://qmk.fm).

It builds all the via/vial keyboard firmwares configured in the repository.
If vial firmware is not available, the default firmware is built as a fallback.

## Release

Every night the script is executed by Github Actions and updates the `nightly` tag.

You can download the files directly here:
https://github.com/GreatWizard/qmk-firmware-build/releases/tag/nightly

## How to flash a firmware

Follow steps from this guide: [Flashing your keyboard](https://docs.qmk.fm/#/newbs_flashing).

## VIA or VIAL?

VIA and VIAL are cross-platform (Windows, Linux and Mac) GUI for configuring your keyboard in real time.
VIA is a closed-source and integrated natively in QMK Firmware.
Vial is an open-source and is based on a QMK fork.

### VIA

See documentation here: https://www.caniusevia.com/

### VIAL

See documentation here: https://get.vial.today/

## Add my keyboards

You can add your keyboards by doing a pull request with the following content:

- create a new user in the `users` directory that is exactly you GitHub nickname
- for QMK firmwares, add a file `keyboards.yml` in your directory following this structure:

```yaml
---
- keyboard: kprepublic/jj50 # required
  keymaps: [greatwizard] # required
- fork: # optional
    username: piit79 # required
    repository: qmk_firmware # optional, defaults to qmk_firmware
    branch: master # optional, defaults to master
  keyboard: 42keebs/mysterium/v15d # required
  keymaps: [via] # required
```

- for vial firmwares, add a file `vial.yml` in your directory following this structure:

```yaml
---
- fork: # optional
    username: greatwiard # required
    repository: vial-qmk # optional, defaults to vial-qmk
    branch: jj50 # optional, defaults to vial
  keyboard: kprepublic/jj50 # required
  keymaps: [vial] # required
```

## Alternative places to get firmwares

- https://qmk.fm/keyboards/
- https://qmk.tzarc.io/
- https://github.com/filterpaper/build_qmk_dev
- https://github.com/Xelus22/QMK-VIA-Hex-Develop
- https://github.com/Xelus22/QMK-VIA-Hex
- https://www.caniusevia.com/docs/download_firmware
