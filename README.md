<div align="center">
  <img src="https://github.com/user-attachments/assets/f3cd2dbf-92d0-4984-a21e-16878dcbbab1" alt="ScuttlePod Logo" width="96" height="96" />
  <h1>ScuttlePod</h1>

  <a href="https://play.google.com/store/apps/details?id=com.sphereforge.scuttlepod">
    <img alt="Get it on Google Play" src="https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png" width="200"/>
  </a>
</div>

ScuttlePod is a secure app lock overlay and anti-theft data rescue utility for Android. It is designed to protect selected folders and restrict app access under scenarios of physical coercion, device snatching, or duress.

Unlike standard lock screens or passive app lockers, ScuttlePod provides dynamic “panic” trigger systems that can securely overwrite local files, execute background cloud backups, or lock down specific apps depending on which PIN is entered.

---

## Technical Features

### 🔑 The Multi-PIN Security Gateway
ScuttlePod operates on top of your native Android lock screen, acting as a security overlay. It uses four specialized PINs to trigger different behaviors:
* **Master PIN:** Unlocks the overlay and grants access to ScuttlePod configurations.
* **Guest PIN:** Keeps restricted apps protected behind an overlay. It allows basic device usage but immediately blocks access if a restricted app is launched.
* **Panic-Backup PIN (Delay Tactic):** Mimics a successful unlock into Guest Mode to buy you time under pressure. While appearing unlocked in Guest Mode, ScuttlePod silently uploads your selected folders to your cloud account in the background. The moment an intruder attempts to open a restricted app, the lock screen drops, forcing a decision: unlock or wipe.
* **Panic-Wipe PIN:** Triggers a customizable countdown (10–60 seconds). Only the Master PIN can abort it. This countdown is persistent and survives device reboots. Includes an optional **Silent Mode** that disables the alarm sound and red warning screen in favor of a discreet dot countdown and 2 short vibrations.

### 🛡️ Lock Screen Customization & Hardware Protections
* **Custom Rotating Wallpapers:** Add up to 7 custom lock screen wallpapers with individual crop/zoom and automatic 24-hour rotation. Images are EXIF-corrected, capped to screen resolution (up to 2560px), and stored strictly inside ScuttlePod's private app storage.
* **Master PIN Setup Safety Net:** Displays a discreet one-time 5-second Hold-to-Reset option on the lock screen right after creating a new Master PIN, permanently hiding itself after your first successful Master PIN unlock.
* **Relock on SIM Removal:** Opt-in toggle that immediately locks the device if an active SIM card is ejected. 
* **Anti-Uninstall & Capture Protection:** Uses Accessibility protections to prevent unauthorized uninstalls and blocks screenshots and screen recording inside ScuttlePod.

### 🔥 Under the Hood: Secure Wipe Engine
Standard file deletions only unlink the file, leaving the raw blocks recoverable on storage. ScuttlePod implements a multi-step secure erasure pipeline:
1. **Byte-Level Overwriting:** Files are opened in write-truncate (`wt`) mode and overwritten chunk by chunk with cryptographically secure random bytes matching the exact size of the file.
2. **Metadata Scrambling & Deletion:** Files and target user-created directories are renamed to randomized 6-digit numbers to erase original filenames before the final deletion is executed.
3. **Root Folder Protections:** To prevent system instability, ScuttlePod cannot rename or delete root volumes or system directories (such as the primary storage root, `Android`, or `Download` folders). However, it will securely overwrite and delete all targeted user subfolders and files nested inside them.

### 📲 Remote Emergency Triggers
* **Notification Interceptor:** Executes a remote backup or wipe when a custom secret keyword is detected in an incoming notification. (Note: Your targeted messaging app must have its system notifications enabled for ScuttlePod to intercept the keyword). If the device is offline or the connection drops mid-upload, ScuttlePod immediately aborts the backup and triggers the secure local wipe.
* **Cloud Canary:** Automatically generates the file `[SCUTTLEPOD_CANARY] - TRASH TO WIPE PHONE.txt` in your cloud’s directory. If this file is moved to the trash or deleted from another device, ScuttlePod detects its absence during its periodic check, starts the backup, and wipes your selected folders.
* **Dead Man’s Switch:** If the device is not unlocked for a set period (7, 14, 30, or 90 days), ScuttlePod safely uploads your selected folders to the cloud, then permanently disables the trigger. It pings Google’s UTC servers directly to find the accurate date and time, preventing accidental backups caused by local system clock drift.

### 📸 Intruder Logs
When an incorrect PIN is entered on a restricted app or the overlay, ScuttlePod silently captures a photo using both the front and back cameras. It logs the timestamp and the target app attempt.
(Note: Android system-level camera privacy indicators will still display normally during capture).

---

## Security & Privacy Model

* **Zero Backend Servers:** ScuttlePod does not run any proprietary backend databases or servers. I have absolutely no access to your files, encryption keys, or credentials.
* **Bring Your Own Cloud (BYOC):** File transfers stream directly from your device using secure OAuth connections to your personal Google Drive or Dropbox account.
* **PIN Hashing:** PINs are never stored in plain text. They are hashed using `PBKDF2WithHmacSHA256` with 10,000 iterations and a cryptographically secure 16-byte random salt.
* **Encrypted Sandbox:** Intruder logs, captured photos, and app settings are stored strictly inside ScuttlePod’s private, sandboxed internal storage, hidden from the system photo gallery and protected by Android’s hardware-level file-based encryption (FBE).

---

## 🔗 Links & Support
* 🌐 **[Official Website](https://scuttlepod.com/)**
* 📱 **[Download on Google Play](https://play.google.com/store/apps/details?id=com.sphereforge.scuttlepod)**
* 🐞 **[Report an Issue](https://github.com/SphereForge/Scuttlepod/issues)**
* 📄 **[Privacy Policy](https://scuttlepod.com/scuttlepod-privacy.html)** ([GitHub Mirror](https://github.com/SphereForge/Scuttlepod/blob/main/PRIVACY_POLICY.md))
