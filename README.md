# ESP32 Radio Pogoda Firmware Installer - Loader and Updater 2026

> **Browser-based firmware tool for preparing and flashing Radio Pogoda firmware onto ESP32-S3 RLCD-4.2 devices using a compatible desktop browser.**

[![Loader](https://img.shields.io/badge/Type-Loader-blue?style=flat-square)](https://github.com)
[![Platform](https://img.shields.io/badge/Platform-ESP32--S3-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/florianw95/radio-pogoda-esp32-installer?style=flat-square)](https://github.com/florianw95/radio-pogoda-esp32-installer)

---

<p align="center">
  <a href="https://florianw95.github.io/radio-pogoda-esp32-installer/">
    <img src="https://img.shields.io/badge/Download-ESP32%20Radio%20Pogoda%20Installer-brightgreen?style=for-the-badge" alt="Download ESP32 Radio Pogoda Installer">
  </a>
</p>

> **[Download ESP32 Radio Pogoda Installer](https://florianw95.github.io/radio-pogoda-esp32-installer/)**

---

[Download Latest Build](https://florianw95.github.io/radio-pogoda-esp32-installer/)

---

## Overview

ESP32 Radio Pogoda Installer is a web application for loading firmware onto ESP32-S3 boards used by the RLCD-4.2 Radio Pogoda project. Through Web Serial and ESP Web Tools, a supported desktop browser can communicate directly with the connected device and transfer the firmware.

Before writing the firmware, the utility can prepare the board by erasing its flash. It handles both firmware packages made up of multiple files and complete firmware images. Because the installer is published through GitHub Pages, users can access the flashing interface without configuring a separate command-line environment.

---

## Included Capabilities

- Install firmware from a browser to ESP32-S3 hardware
- Support for RLCD-4.2 Radio Pogoda devices
- Automatic flash cleanup before installation
- Flashing workflows for multi-file firmware layouts
- Full-image flashing through `esptool-js`
- Serial communication using Web Serial and ESP Web Tools
- Use with supported desktop versions of Chrome and Microsoft Edge
- Static deployment through GitHub Pages

---

## Installation Procedure

1. Attach the ESP32-S3 RLCD-4.2 device to the computer using a USB cable.
2. Visit the [ESP32 Radio Pogoda Installer](https://florianw95.github.io/radio-pogoda-esp32-installer/) in Chrome or Microsoft Edge.
3. When prompted, choose the serial device corresponding to the connected ESP32-S3.
4. Follow the on-screen steps to erase the flash and write the firmware.
5. Leave the board connected until the transfer has completed.
6. Restart the device if the installer or the device procedure asks you to do so.

This utility runs in the browser, so there is no command-line command required to start it.

### Required Browser and Connection Support

- Desktop Chrome or Microsoft Edge
- Browser support for Web Serial
- A USB data connection exposing the ESP32-S3 as a serial device
- Permission to use the selected serial port

---

## Available Build Options

The installer works with the firmware build made available by the project rather than maintaining separate stable, beta, and nightly tracks.

| Option | Description |
| --- | --- |
| Latest build | Opens the current firmware installer at the project's deployment URL |
| Manual build | Flash a firmware layout or image available locally through a compatible workflow |
| Reinstall | Erase the device flash and write the chosen firmware again |

---

## Troubleshooting Guide

### No ESP32-S3 device appears

- Make sure the USB cable carries data, not only power.
- Unplug and reconnect the board, then open the browser's serial-device selector again.
- Quit any other program that could be holding the serial port.
- Confirm that you are using Chrome or Microsoft Edge with Web Serial support.

### Serial-port access is denied

- Approve the serial-device permission request.
- Choose the correct ESP32-S3 entry in the browser dialog.
- Temporarily disconnect unrelated serial devices so the correct port is easier to identify.
- After changing the USB connection, reload the installer.

### Erasing or flashing does not complete

- Do not unplug the board while the operation is running.
- Test a different USB port or cable.
- Reset or reconnect the ESP32-S3 and begin the installation again.
- If the board was unplugged during the transfer, repeat the flashing process.

### The board boots unexpected firmware

Flash erase is part of the install sequence. Before starting, verify that the selected build is the intended Radio Pogoda firmware.

### The deployed installer cannot be opened

Check the GitHub Pages deployment URL and try again once the site is available. To run a local copy, serve the static project files with a local web server that meets the browser's Web Serial requirements.

---

## Frequently Asked Questions

### What hardware does this support?

The target hardware is ESP32-S3 devices used with the RLCD-4.2 Radio Pogoda project.

### Which browsers are supported?

Use a supported desktop version of Chrome or Microsoft Edge with Web Serial enabled.

### Is the flash erased automatically?

Yes. The installation process includes an automatic flash erase before firmware is written.

### Can the tool write multiple firmware files?

Yes. It supports both multi-file firmware layouts and complete firmware images, with full-image flashing handled through `esptool-js`.

### Can locally stored firmware be flashed?

Yes, provided the local files follow the expected firmware layout and are intended for the target hardware. Both multi-file and full-image workflows are supported.

### Is an older firmware build supported?

An earlier compatible build can be used when it is available for the device and can be provided to the flashing workflow. There is no dedicated rollback channel.

### Where can I find installation logs?

This is a browser utility rather than a desktop application. Review status information and errors in the browser interface or developer tools; the installer does not create a separate desktop log directory.

### Does it work without an internet connection?

The installer is delivered through GitHub Pages. Offline operation requires the installer files and firmware resources to be available locally, along with a browser environment that supports Web Serial.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
