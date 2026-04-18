# Sonic App Configuration 🚀

This repository hosts the central configuration for the Sonic mobile application. It manages maintenance modes, native versioning, and Over-The-Air (OTA) update nudges.

## 🛠 Configuration Structure

The `app-config.json` file is structured into three main modules:

### 1. `maintenance`
Controls the app's availability during system upgrades.
- **`enabled`**: (boolean) Set to `true` to block app access and show the maintenance message.
- **`message`**: (string) The text displayed to users when maintenance is active.

### 2. `native`
Manages hard updates for the native binary (APK/IPA).
- **`version`**: (string) The latest available native version.
- **`minRequiredVersion`**: (string) The minimum version required to use the app.
- **`forceUpdate`**: (boolean) If `true`, users below `minRequiredVersion` will be forced to update.
- **`updateUrl`**: (string) Direct download link for the latest APK or Store page.

### 3. `ota`
Manages Expo Over-The-Air update notifications.
- **`version`**: (string) Should match the version in `assets/version.json` within the app.
- **`force`**: (boolean) If `true`, prompts the user to restart the app immediately to apply updates.
- **`message`**: (string) The notification message shown when a new OTA update is ready.

## 🚀 Deployment

Simply update the values in `app-config.json` and push to the `main` branch. The app fetches this configuration on startup to determine its state.

---
*Maintained by the Sonic Dev Team*
