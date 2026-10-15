# Chaz BONELAB Tool

An unofficial BONELAB backup APK for Meta Quest 3S, with built-in wireless-debugging pairing. The app itself is named **BONELAB Backup**.

[Download the APK](https://github.com/LCP-Git-Hub/Chaz-Bonelab-tool/releases/download/v0.1.1/BONELAB-Backup-Quest-v0.1.1.apk) · [Release and source archive](https://github.com/LCP-Git-Hub/Chaz-Bonelab-tool/releases/tag/v0.1.1)

## Installation fix: v0.1.1

The original v0.1.0 APK compressed its resource table, which Android 11+ rejects at installation. v0.1.1 keeps the table uncompressed and four-byte aligned, and adds a final-APK regression check. Download the new APK rather than reopening the old file. No BONELAB uninstall or game-data changes are needed for this fix. On-device installation remains unverified.

## Use on Quest

1. Download the APK in the Quest browser and open it with the headset's package installer.
2. Open BONELAB Backup. Enable Android **Wireless debugging**, then pair using the code and pairing port shown on the headset.
3. Connect using the separate connection port from the main Wireless debugging screen.
4. Fully quit BONELAB and choose **Back up Saves only** or **Back up external files + OBB assets**.
5. Wait for **VERIFIED FILE COPY**. Completed ZIP files appear in **Downloads/BONELAB-backups**. A `.partial` file is incomplete.

No separate Shizuku app is installed or required. Firmware must permit wireless debugging and access to BONELAB's external files. This app cannot enable access without your authorization.

## What it does

- Creates a new ZIP without overwriting earlier backups.
- Checks archived files against the originals using SHA-256.
- Detects missing/empty saves, changed source files, and incomplete copies.
- Keeps data on the headset; connects only to the local debugging service.
- Never patches, uninstalls, deletes, or restores BONELAB.

**Experimental: not tested on a Quest device.** Eight automated backup-engine tests pass, and the APK's signature and alignment were verified. Pairing, UI, firmware compatibility, and actual Quest 3S file access remain unverified.

It copies external files only, not private Android app storage. There is **no restore button**, and successful file verification does not prove a working restore or guarantee progress survives patching. Keep BONELAB installed until you have established a restoration method.

## Source and licenses

The release includes **BONELAB-Backup-Source-v0.1.1.zip**, full setup notes, and an APK SHA-256 checksum. The source archive contains app code, build instructions, dependency binaries, notices, and the LGPL Spake2 library's corresponding sources.

Application source: GPL-3.0-or-later. Dependencies retain their respective licenses: libadb-android (Apache-2.0 option), Spake2 (LGPL-3.0), Conscrypt (Apache-2.0), Bouncy Castle (MIT-style), and AndroidX Annotation (Apache-2.0).

Not affiliated with Stress Level Zero, Meta, LemonLoader, or Shizuku.
