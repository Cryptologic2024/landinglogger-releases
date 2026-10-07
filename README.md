# LandingLog

LandingLog is a free Windows logbook for Microsoft Flight Simulator 2024. It runs in the tray, records your flights in the background, and keeps the logbook on your PC.

It's still in beta. If it gets something wrong, please [open an issue](../../issues) so I can fix it.

**[Download the latest release](../../releases/latest)**

## What it does

- Records flights automatically from pushback or taxi to parking. If you start LandingLog while already airborne, it can pick up the flight there. You can also save or stop a flight yourself from the Live tab.
- Keeps the route, airports, aircraft, block and air times, fuel use and landings. Pauses and sim rate are accounted for.
- Shows each landing's rate, G-force, touchdown point, runway position, wind and approach data. There are charts and landing trends if you want to look more closely.
- Lets you browse flights on a map, replay a route, add notes and look at stats for your airports and aircraft.
- Can attach a matching SimBrief plan and show progress and ETA during a flight.
- Has optional weather, airport and navaid layers, plus a route picker. Those layers stay off until you turn them on.
- Imports older flights from Volanta JSON or ElevateX CSV files. You can import a file, zip or folder; duplicates are skipped.

The window can stay closed while you fly. LandingLog keeps recording from the system tray. If the app or PC stops mid-flight, it keeps the interrupted flight as incomplete.

## How it got here

I started LandingLog because I wanted the kind of flight history you get from Volanta, but in a small app that lives on my PC. The idea was to let it sit in the tray, log the flight, and stay out of MSFS's way.

Once that part worked, I kept adding the things I wanted to look back at: the route on a map, how the landing went, SimBrief details, notes, and stats. I also wanted to bring my older flights across instead of starting from zero.

Lately I've mostly been chasing the annoying edge cases: flights that don't start or save when they should, times that are off, and helicopters or multi-leg trips that don't fit the usual pattern. There's still stuff to iron out.

## What's next

I'm mainly going to keep fixing the recording and making sure LandingLog stays light while MSFS is open. I also want to make it easier to bring in old flights and clean up details the app got wrong. After that, I'll follow what people actually run into. I don't have dates for those changes yet.

## What you need

- Windows 10 or 11, 64-bit.
- Microsoft Flight Simulator 2024. MSFS 2020 has not been tested.
- .NET Framework 4.8 and the Microsoft Edge WebView2 Runtime. Setup will tell you if either is missing.
- Internet access for maps, weather, airport data, SimBrief and update checks. Flight recording itself works offline.

## Install

1. Open the [latest release](../../releases/latest). Under **Assets**, download the Setup .exe for the current version.
2. Run the installer and follow the prompts. You can add a desktop shortcut if you want one.
3. Start MSFS before or after LandingLog; it connects when the sim is available.

The installer is unsigned, so Windows may show a "Windows protected your PC" warning. Check that you downloaded it from this release page. Each download has a matching .sha256 file if you want to verify its checksum with PowerShell's Get-FileHash command.

Setup installs for your Windows account, without an administrator password. You can uninstall it from **Settings > Apps > Installed apps**. On first run, LandingLog offers to start with Windows. Airport data and SimBrief are optional and can be set up later in **Settings**.

Closing the window leaves LandingLog running in the tray. Double-click its tray icon to reopen it, or right-click the icon and choose **Exit** to quit.

<details>
<summary>Prefer a portable copy?</summary>

Download the portable .zip for the current version, extract it to a folder you plan to keep, and run **LandingLog.exe**. The installer and portable copy use the same logbook, so you only need one of them.

</details>

## Updates

LandingLog checks once a day for a new release and shows an Update button when one is available. It only downloads the installer after you press the button, checks the download against its published SHA-256 checksum, and waits until you are not recording before installing. You can turn update checks off in **Settings > Updates**.

You can also install a new version manually over the old one. For the portable copy, exit LandingLog and extract the new zip over its folder. Updating does not delete your logbook; LandingLog makes a backup when a new version first starts.

## Your data

Your flights, settings and backups are stored here:

    %LOCALAPPDATA%\LandingLog

Paste that path into File Explorer to open it. There is no LandingLog account, and flights are not uploaded. The app goes online for optional content such as maps, weather, airport data and SimBrief, and to check for updates.

Use **Settings > Data** to back up, export or restore your logbook. Uninstalling leaves the data folder in place. If you want to remove it too, export anything you want to keep first, then delete the folder after uninstalling.

## Problems or feedback

Open **Settings > Help > Copy diagnostics**, then [open an issue](../../issues) with what happened and what you expected. The copied details include the app version, setup information and recent log messages, but not your flights or SimBrief username.

A few things to check first:

- **Nothing records:** Check that the tray icon says LandingLog is connected to MSFS and that you are in a flight, not the main menu.
- **The window is blank:** Install the [Microsoft Edge WebView2 Runtime](https://developer.microsoft.com/microsoft-edge/webview2/).
- **"LandingLog is already running":** Find the tray icon and double-click it.

LandingLog uses [MapLibre](https://maplibre.org/), airport data from [OurAirports](https://ourairports.com/), and weather from NOAA's Aviation Weather Center, RainViewer, EUMETSAT, NASA GIBS and Open-Meteo. It is not affiliated with Microsoft, Asobo, SimBrief, Navigraph, Volanta or ElevateX.