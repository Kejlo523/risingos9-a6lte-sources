# DRAFT — DO NOT POST YET

XDA does not allow placeholder development threads. Before publishing, replace
every `REQUIRED` marker with a working direct download link and attach actual
screenshots from the A6 build.

---

## [ROM][17][a6lte][COMMUNITY] RisingOS Revived 9 for Samsung Galaxy A6 (2018)

**RisingOS Revived 9**<br>
**Android 17 for Samsung Galaxy A6 (2018) — a6lte**<br>
**CORE GApps included • SELinux Enforcing • August 2026 SPL**

### Disclaimer

```text
/*
 * Your warranty is now void.
 *
 * I am not responsible for bricked devices, dead SD cards,
 * lost data or missed alarms.
 *
 * Make a backup and understand the installation process
 * before flashing. You are choosing to modify your device.
 */
```

### Information

- Device: Samsung Galaxy A6 (2018) — a6lte
- Tested model: SM-A600FN
- ROM: RisingOS Revived 9
- Android: 17
- Build type: COMMUNITY / userdebug
- GApps: CORE (included)
- Security patch: 2026-08-01
- SELinux: Enforcing
- Status: Initial Android 17 release

### How it looks

**REQUIRED BEFORE POSTING:** attach real screenshots from this build here.

### What works

Boot, RIL, calls in both directions, mobile data, Wi-Fi, hotspot, Bluetooth,
NFC, GPS, camera, audio, sensors, vibration, charging, fingerprint, MTP,
recovery, account settings and RisingOS customizations.

### Known issues

- Double tap to wake is not working yet.
- VoLTE/VoWiFi availability may depend on the carrier.
- Report anything else in this XDA thread with logs.

### Requirements

- Unlocked bootloader
- Latest Android 10 Samsung firmware for your exact A6 variant
- Included recovery image
- Full backup — formatting data erases internal storage

### Installation

1. Flash the included recovery:

```bash
heimdall flash --RECOVERY recovery.img --no-reboot
```

2. Boot directly into recovery with **Volume Up + Power**.
3. Select **Factory reset → Format data/factory reset**.
4. Select **Apply update → Apply from ADB**.
5. Flash the ROM:

```bash
adb sideload RisingOS-9-REQUIRED-GAPPS-COMMUNITY-a6lte.zip
```

6. Reboot system and allow several minutes for the first boot.

A clean flash is required. Do not manually wipe System and do not flash a
separate GApps package.

### Downloads

- ROM: **REQUIRED — add a working direct download link**
- Recovery: **REQUIRED — add a working direct download link**

Passwords must be stated here if either file is password protected.

### Sources

- Pinned build manifest: https://github.com/Kejlo523/risingos9-a6lte-sources
- RisingOS: https://github.com/RisingOS-Revived/android/tree/seventeen
- Device: https://github.com/Kejlo523/android_device_samsung_a6lte/tree/rising-17-a6lte
- Device common: https://github.com/Kejlo523/android_device_samsung_universal7870-common/tree/rising-17-a6lte
- Kernel: https://github.com/Kejlo523/android_kernel_samsung_exynos7870/tree/rising-17-a6lte
- Vendor device: https://github.com/Kejlo523/android_vendor_samsung_a6lte/tree/rising-17-a6lte
- Vendor common: https://github.com/Kejlo523/android_vendor_samsung_universal7870-common/tree/rising-17-a6lte

### Bug reports

Include the exact build name, device model, firmware version, clean/dirty flash
status and steps to reproduce. Attach logs from the failing session:

```bash
adb logcat -b all -d > logcat.txt
adb shell dmesg > dmesg.txt
adb shell getprop > props.txt
```

Development support is provided in this XDA thread. Do not redirect bug reports
to an off-site chat platform.

### Credits

- RisingOS Revived team
- LineageOS
- Samsung Exynos 7870 contributors
- Testers and community

— Kejlo
