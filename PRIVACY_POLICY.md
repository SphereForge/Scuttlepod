# Scuttlepod Privacy Policy

**Effective Date:** June 23, 2026

I, the developer of Scuttlepod, have built this application (the "App") as a secure, personal device lock, parental control, and remote-wipe anti-theft utility. This Privacy Policy is here to tell you in plain English exactly how Scuttlepod protects your data.


## Scuttlepod Privacy Philosophy is simple:

*   **No Personal Data Harvesting:** I do not collect, harvest, monitor, store, share, or transmit any of your personal data, files, PINs, or security logs to myself or any third-party marketing/analytics networks.
*   **100% Local Storage:** All your security configurations, saved PINs, incorrect PIN logs, and captured intruder photos are stored locally and securely in the App's private, sandboxed internal storage directory on your device. This data is fully controlled by you and can be permanently deleted at any time from within the App's settings.

---

## Permissions Justification and Use (Your Setup Choices)

To protect your device, Scuttlepod needs you to enable several permissions. Here is exactly what they do and why they are needed.

### Required Permissions:

*   **Accessibility Service:** Used strictly to protect your device by detecting when a blocked/restricted app is opened so the lock overlay can display, and to block guests from going into settings to force-stop or uninstall Scuttlepod. This runs completely offline on your device.
*   **Display Over Other Apps (System Alert Window):** This is the permission that physically allows Scuttlepod to draw its security lock screen over your home screen and restricted apps.
*   **Battery Optimization (Unrestricted):** Must be set to "Unrestricted" so that Android does not put Scuttlepod to sleep in the background, which would leave your locked apps unprotected.

### Optional Permissions:

*   **Camera Access:** Used strictly to snap silent photos with the front and back cameras if an incorrect PIN is entered on your lock screen. These photos are saved directly inside Scuttlepod’s private, sandboxed internal storage, making them completely invisible to all other applications on your device. Furthermore, they are stored on your device’s hardware-encrypted partition, which is only decrypted when you unlock your device.
*   **Notifications:** Used to send you system alerts if critical security features are accidentally turned off or revoked.
*   **Notification Access (Notification Interceptor):** Allows Scuttlepod to scan incoming notification headers locally on your device for your custom, secret remote-trigger keyword.

---

## Background System Permissions

For transparency, the App also declares a few automatic background permissions in its configuration file. These do not require manual switches on your setup screen:

*   **Query All Packages:** This is the permission that allows Scuttlepod to see the list of apps installed on your device so you can choose which ones to lock.
*   **Foreground Service (Data Sync):** Keeps the backup engine safely running in the background during a remote-wipe trigger so your files finish uploading securely before they are locally deleted.
*   **Receive Boot Completed:** Allows the App's security lock screen to launch immediately the moment your device powers on, preventing bypasses after a forced reboot.

---

## Third-Party Cloud Integrations & Privacy Links

Scuttlepod allows you to link your personal Google Drive or Dropbox accounts so you can safely rescue your files and receive remote status updates during backup.

*   **Direct Uploads:** All backups and Scuttlepod's backup percentage status logs are uploaded directly and securely from your device to your own private Google Drive or Dropbox storage. These status logs are sent only during an active backup task to report the upload progression, followed by a final confirmation file that is uploaded immediately after a secure remote wipe has successfully completed. Your data never passes through me or any third-party middleman.
*   **Third-Party Privacy Policies:** Because Scuttlepod utilizes these external platforms to store your backups, your cloud storage is subject to their respective privacy terms. I encourage you to read them here:
    *   [Google Privacy Policy](https://policies.google.com/privacy)
    *   [Dropbox Privacy Policy](https://www.dropbox.com/privacy)

---

## Children's Privacy

This app is intended for a general audience and is not directed to children under the age of 13 (or the relevant age in your jurisdiction). I do not collect, store, or solicit any personal information from children or anyone else, as the App processes all data and app-restriction rules strictly locally on the device.

---

## Changes to This Privacy Policy

I may update this Privacy Policy from time to time. You are advised to review this page periodically for any changes.

---

## Contact Me

If you have any questions about this Privacy Policy or wish to report a bug, please do not hesitate to contact me at:

*   **Email:** [sphereforge.apps@gmail.com](mailto:sphereforge.apps@gmail.com)
*   **Official GitHub Repository:** [github.com/SphereForge/Scuttlepod](https://github.com/SphereForge/Scuttlepod)
