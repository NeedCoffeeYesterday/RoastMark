
# ☕ Roastmark

**Coffee roast tracking for home roasters.**  
Real-time temperature graphs, BLE probe auto-logging, cloud sync, and Excel export. Free on web and Android.

🌐 [roastmark.coffee](https://roastmark.coffee) · 📱 [Download APK](https://github.com/NeedCoffeeYesterday/RoastMark/releases/latest)

---

## Features

- **Real-time roast tracking** — log temperature, weight, and milestones as you roast
- **Rate of Rise graph** — monitor RoR and see a reference line at first crack
- **DIY BLE probe** — connect an ESP32 + MAX6675 thermocouple over Bluetooth for automatic temp logging
- **Roast profiles & templates** — create templates from past roasts and use them as overlay guides
- **Roast comparison** — overlay up to 4 past roast curves on the live graph
- **Batch cost analysis** — track energy, labour, packaging, and custom line items per roast
- **Excel export** — export full roast data including RoR at first crack
- **Cloud sync** — Firebase-backed, works across devices. Offline fallback via localStorage
- **C/F toggle** — switch temperature units any time; all data stored in Celsius internally
- **Web + Android** — same codebase, Firebase hosted web app + Capacitor Android APK

---

## DIY Bluetooth Probe

Build your own wireless temperature probe using an ESP32-C6 and two MAX6675 thermocouple modules. The probe streams bean temp (BT) and environment temp (ET) to the app over BLE.

📖 [Probe build guide](https://roastmark.coffee/probe-guide.html)

**Parts:** ESP32-C6 · MAX6675 × 2 · K-type thermocouples × 2 · Jumper wires  
**Cost:** ~$25–35 CAD from AliExpress

---

## Tech Stack

- **Frontend:** React + TypeScript + Vite
- **Mobile:** Capacitor (Android)
- **Backend:** Firebase Auth + Firestore
- **Ads:** AdMob (Android) · AdSense (web)
- **Hardware:** ESP32-C6 · MAX6675 · BLE 5.0

---

## Android APK

The latest signed APK is available on the [Releases page](https://github.com/NeedCoffeeYesterday/RoastMark/releases/latest).

To sideload on Android, enable **Install from unknown sources** in your device settings, then open the downloaded APK.

---

## Architecture Notes

- All temperatures stored in Celsius internally, converted on display via `tempUtils.ts`
- All weights stored in grams, displayed in kg
- Firebase project ID stays as `roast-log-815bc` (backend only, not user-facing)
- BLE scan filter looks for device named `"Roastmark Probe"`

---

Built by a home roaster, for home roasters. [roastmark.coffee](https://roastmark.coffee)
