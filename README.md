# TANUVANSH Lantern Firmware

Firmware releases for the **Seeed Studio XIAO ESP32-C6** lantern: 64 WS2812 pixels on D3/GPIO21.

[Download the latest release](https://github.com/tanuvansh517-web/tanuvansh-lantern-firmware/releases/latest)

## One portal for everything

From firmware **2.3.0**, your local lantern portal has three sections:

- **Light:** power, live color, brightness and Palace / Diya / Breathe / Journey effects. Changes auto-save.
- **Wi-Fi:** scan networks, choose your network and enter its password. The setup AP stays enabled while home Wi-Fi retries. New credentials are saved only after a successful connection.
- **Updates:** Check for updates → Install the available version. The lantern downloads firmware directly from GitHub and verifies it before restarting. Your settings are retained.

## Install cloud updating once

1. While you have internet, open the latest release and download its `TANUVANSH-VERSION-firmware.bin` asset. Do not choose a source ZIP or the manifest.
2. Open the existing lantern portal on the same home network. Alternatively, join the lantern's TANUVANSH setup Wi-Fi and open http://192.168.4.1.
3. Sign in as **admin**, using your existing lantern password.
4. Under **Settings & device care → Firmware update**, select the binary and install it. Keep power connected.
5. After restart, refresh the browser and confirm the running firmware version is **2.3.0 or later**.
6. For subsequent releases, use **Updates → Check for updates → Install**. No manual file downloads are needed after this first installation.

If the installed firmware is already the latest release, the portal correctly reports **Your lantern is up to date**.

Cloud updates require the lantern itself to have internet access through its Wi-Fi network. The setup AP alone has no internet, but still supports controls, Wi-Fi setup and manual recovery uploads. No USB is required while the existing portal works. The Android app loads the new portal without an app update.

This is a local controller, not an away-from-home remote-access service. No Wi-Fi credentials, device passwords or private logs are published here.

## Verification and limits

The unified-portal release passed the exact-board PlatformIO build, actual OTA slot-size check, portal and cloud UI simulations, compatibility/version/URL checks, flame continuity tests and browser preview. Its public download is checked with the firmware's selected HTTPS trust roots and SHA-256. **Hardware verified on 9 November 2026:** the installed lantern downloaded firmware 2.3.2 directly from GitHub, verified it, restarted into 2.3.2 and retained its saved lighting settings. No USB or local firmware-file upload was used for that cloud update. The secure connection timeout is 20 seconds; failed checks can be retried from the portal.

The updater uses verified HTTPS and a SHA-256 manifest, and aborts incomplete/mismatched downloads before activating the image. It does not implement Secure Boot, separately signed firmware or automatic rollback after a defective new application's boot. Maintain power during updates. Manual recovery upload remains available.

## Update feed

[Latest manifest](https://github.com/tanuvansh517-web/tanuvansh-lantern-firmware/releases/latest/download/manifest.json)

Each release includes a firmware binary, manifest and checksum. The manifest specifies version, board, chip, size, SHA-256 and a fixed versioned download URL. Published firmware assets are not replaced; fixes receive a new version.
