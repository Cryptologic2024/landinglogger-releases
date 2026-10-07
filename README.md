# LandingLog

**A free, automatic logbook for Microsoft Flight Simulator 2024.**

LandingLog sits quietly in the Windows system tray and records every flight by itself: where you left from, where you landed, the route you flew, your block and air times, your fuel, and a detailed look at every landing. You don't press anything to start or stop a flight. Just fly.

> LandingLog is in beta. Your logbook stays on your own PC.

**[⬇ Download the latest version](../../releases/latest)**

---

## What it does

### Records your flights for you
- Starts recording when you push back or taxi off the gate (or when you take off, if you start LandingLog in the air).
- Saves the flight once you're parked with the engines off: after 1 minute with the parking brake set, or after 5 minutes without it (handy for GA aircraft, helicopters and gliders). You can also save or stop a flight yourself from the **Live** tab.
- Keeps off-block, takeoff, landing and on-block times in UTC and local time, with taxi-out and taxi-in. Sim pauses and sim rate are taken into account.
- Works from the tray even if you never open the window, and shows a notification when a flight is saved.
- If LandingLog or your PC crashes mid-flight, the flight is kept as incomplete instead of being lost.

### Tells you how your landing really went
- Landing rate (fpm), G-force, touchdown distance past the threshold, centreline offset and runway left, drawn on a to-scale runway with the touchdown zone and aiming point.
- **Approach check** from 500 ft down to 50 ft: sink rate, speed changes, bank, gear and flaps, with a clear "Stable approach" or "Unstable approach" and the reasons.
- Speed at 500 ft, over the threshold and at touchdown, the float, and how far you rolled after touchdown.
- The wind at touchdown drawn against the runway, with headwind or tailwind and crosswind.
- An approach chart of height, speed and vertical speed down to touchdown. Press **Analyse** for a large view.
- Landing trends for each aircraft type, so you can see if you're getting smoother.

### A logbook you'll actually enjoy browsing
- **Flights**: every flight on a map, coloured by altitude, with a replay, notes and an event timeline (engine start, takeoff, touchdowns, pauses, weather changes).
- **Airports**, **Aircraft** and **Stats**: most-visited airports, hours and landings per aircraft type (liveries and add-ons of the same type are grouped), hours per month, landing grades, on-time rate and personal records.
- Fuel at off-block, takeoff, landing and on-block, compared with your SimBrief plan when you have one.
- Three themes: Night café, Paper chart and Dusk.

### SimBrief and live tracking
- Enter your SimBrief username and your latest plan is attached automatically when the departure matches.
- Read your OFP inside the app, and see your flight on schedule: early, on time or late.
- The **Live** tab shows your phase of flight, altitude, speeds, next waypoint, progress along the route and ETA.

### Maps, weather and a route picker
- Real-world weather on the map: airport METARs and TAFs, radar, satellite clouds, SIGMETs and AIRMETs, pilot reports and winds aloft. Every weather layer is off until you switch it on.
- IFR-style navaid layers, and taxiways, gates and parking read straight from MSFS when you zoom into an airport.
- **Add-on scenery stars**: LandingLog scans your Community folder (and any add-on folders you choose) and marks airports with add-on scenery with a gold star, and Asobo's handcrafted airports with a white star.
- **Plan**: pick a departure (or let it choose one at random), set distance or time, runway and weather wishes, and LandingLog suggests destinations. It can stick to airports with add-on scenery, and opens SimBrief with the route filled in.

### Bring your old flights
Import your history from **Volanta** (.json) or **ElevateX** (.csv), as single files, a .zip or a whole folder. Duplicates are skipped.

---

## What you need

- Windows 10 or 11, 64-bit.
- Microsoft Flight Simulator 2024. (MSFS 2020 hasn't been tested.)
- .NET Framework 4.8 and the Microsoft Edge WebView2 Runtime. Both already come with Windows 11 and an up-to-date Windows 10. Setup tells you if either is missing.
- An internet connection for the extras (map, weather, airport data, SimBrief and the update check). Recording flights works without one.

---

## Install

1. Open the **[latest release](../../releases/latest)** and, under **Assets**, download `LandingLog-<version>-Setup.exe`.
2. Double-click the file you downloaded.
3. Windows will probably show a blue box saying **"Windows protected your PC"**. This is normal for small free apps: LandingLog isn't signed with a paid code-signing certificate, so Windows doesn't recognise the publisher yet. It doesn't mean anything was found in the file. Click **More info**, then **Run anyway**.
4. Tick **Put a LandingLog shortcut on the desktop** if you'd like one, click **Install**, then **Finish**. LandingLog starts and is added to the Start menu.

Setup installs for your Windows account only, so it never asks for an administrator password. LandingLog then shows up under **Settings > Apps > Installed apps**, where you can uninstall it like any other app.

**First run:** a welcome card offers to turn on **Start with Windows**, so LandingLog is always waiting in the tray. In **Settings** you can also download airport data (so landings show airport names and runways) and add your SimBrief username. Both are optional. You can start LandingLog before or after MSFS; it connects by itself.

Closing the window doesn't quit LandingLog: it keeps running in the tray (click the **^** arrow at the bottom right of the taskbar) so it can keep recording. Double-click the tray icon to open it again, or right-click it and choose **Exit** to quit.

<details>
<summary>Prefer a portable copy?</summary>

Download `LandingLog-<version>.zip` instead, right-click it, choose **Extract All...**, put it somewhere you'll keep it (for example your Documents folder), and run `LandingLog.exe` from the extracted folder. Use either the installer or the zip, not both: they share the same logbook.
</details>

<details>
<summary>Checking the download (optional)</summary>

Each file has a matching `.sha256` file with its checksum. In PowerShell, run `Get-FileHash <file you downloaded>` and compare the result with the text in the `.sha256` file.
</details>

---

## Updating

- Once a day LandingLog checks this page for a newer version. When there is one, an **Update** button appears in the left menu and you get a notification.
- Press **Update** (or **Settings > Updates > Install update**). LandingLog downloads the new installer, checks it against the release's checksum, waits until you're not recording a flight, installs it and restarts. Nothing is downloaded until you press the button.
- You can also just download the newer Setup from this page and run it over your current version.
- You can turn the daily check off under **Settings > Updates**.
- Portable copy: quit LandingLog from the tray, download the new zip and extract it over your old folder.

Updating never touches your logbook, and LandingLog backs it up the first time a new version starts.

---

## Your data stays on your PC

Your logbook, settings and backups are kept in this folder on your own computer:

```
%LOCALAPPDATA%\LandingLog
```

(Paste that into the File Explorer address bar to open it.) There's no account and no sign-up, and your flights aren't uploaded anywhere. LandingLog only goes online to fetch things for you, such as map pictures, weather, airport data, your SimBrief plan and the daily update check.

- **Settings > Data** has **Back up now**, **Export full logbook** and **Restore backup**.
- Installing, updating and uninstalling leave this folder alone. To remove your logbook completely, delete the folder after uninstalling (export your flights first if you want to keep them).

---

## Found a problem?

1. In LandingLog, open **Settings > Help** and press **Copy diagnostics**. This copies the version, some setup details and the end of the log. It doesn't include your flights or your SimBrief name.
2. Open the **[Issues](../../issues)** tab on this page, click **New issue**, describe what happened and what you expected, and paste the diagnostics in.

Some quick fixes first:
- **"LandingLog is already running"**: it's in the tray. Double-click the tray icon.
- **The window is blank**: install the WebView2 Runtime from [Microsoft's download page](https://developer.microsoft.com/microsoft-edge/webview2/) (the "Evergreen Bootstrapper").
- **Nothing gets recorded**: check the tray icon says it's connected to MSFS, and make sure you're in a flight, not the main menu.

---

LandingLog uses [MapLibre](https://maplibre.org/), airport data from [OurAirports](https://ourairports.com/), and weather from NOAA's Aviation Weather Center, RainViewer, EUMETSAT, NASA GIBS and Open-Meteo. It isn't affiliated with Microsoft, Asobo, SimBrief, Navigraph, Volanta or ElevateX.
