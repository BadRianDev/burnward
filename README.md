# Burnward

**Keeps your screen alive and burn-free.**

Burnward protects OLED, plasma and other burn-in prone displays from static-image
retention. It takes a snapshot of what is currently on screen and sweeps a
magnifying lens across it, so every pixel is constantly changing instead of
sitting still.

It runs on **every attached monitor at once**, and quits the moment you press
**Esc**.

> **Burnward never sends any data over the internet.** No telemetry, no
> analytics, no accounts, no network connections of any kind. Everything stays
> on your device.

---

## What it does

| Protection | How it works |
|---|---|
| Moving magnifier | A lens roughly 1/8 of the screen sweeps diagonally, bouncing off the edges, covering the whole screen within about 90 seconds. |
| Tiered magnification | The centre of the lens magnifies most and the magnification falls off towards the translucent rim, so no fixed edge is ever burned in. |
| Global pixel shift | The entire image drifts slightly over time, so even unmagnified pixels keep moving. |
| Cursor nudge | The mouse pointer is shifted a few pixels every 15 seconds so the cursor itself cannot burn in. |
| Shifting exit hint | "PRESS ESC TO EXIT" is drawn in the inverse of the colour behind it, and moves with the pixel shift so the hint cannot burn in either. |
| Periodic re-capture | The snapshot is refreshed every 60 seconds, and the lens resumes its exact position and direction afterwards. |

## Tray application

Burnward installs a tray icon. Right-click it for:

- **Run...** - start the lens
- **Keep awake** - stop the machine sleeping *while the lens is running*
- **Dim screen** - drop the display brightness to 15%, restored automatically when the lens exits
- **Start with Windows** - load the tray at sign-in
- **License / About** - the licence and support details
- **Exit**

**Keep awake** and **Dim screen** are preferences, not immediate actions. They
apply when the lens runs and are undone when it exits, so Burnward never leaves
your machine awake or dimmed with nothing on screen.

With **Keep awake** switched off, Burnward deliberately does not interfere with
your power plan: the display will still switch off on its normal schedule.

---

## Installing

Download the latest build from the
[Releases page](https://github.com/BadRianDev/burnward/releases/latest).

**Option 1 - installer:** download and run `Setup.exe`. It installs per-user to
`%LOCALAPPDATA%\Programs\Burnward`, needs no administrator rights, and can be
removed from *Settings > Apps > Installed apps*.

**Option 2 - MSIX package:** install `Burnward.msix`. The signing certificate
must be trusted before Windows will accept a package that did not come from the
Microsoft Store.

### Requirements

- Windows 10 version 2004 or newer (Windows 11 supported)
- .NET Framework 4.x, which ships with Windows

---

## Known issue: Windows may block the app from starting

Microsoft Defender's attack surface reduction rule **"Use advanced protection
against ransomware"** can block Burnward from launching. The symptom is
**"Access is denied"**, with event ID 1121 in the
*Microsoft-Windows-Windows Defender/Operational* log.

This is a false positive, and an understandable one: Burnward captures the whole
screen and shows fullscreen always-on-top windows, which is behaviourally close
to what a screen locker does. Freshly built, unsigned executables with no
download history are treated with suspicion.

If this affects you:

1. On a **managed work machine**, ask IT to allow `%LOCALAPPDATA%\Programs\Burnward`.
   Local exclusions are overridden by policy and will not help.
2. On your **own machine**, add that folder as an attack surface reduction
   exclusion from an elevated PowerShell window.
3. Install the **MSIX package** instead, which is signed.

Please [open an issue](https://github.com/BadRianDev/burnward/issues/new/choose)
if you hit this, so it can be reported to Microsoft for reclassification.

> **Note:** Burnward's overlay is deliberately excluded from screen capture, so
> it will not appear in screenshots or screen recordings. This is intentional -
> it is what lets the app re-photograph the desktop without photographing
> itself. Use a phone camera if you need to show the lens in a bug report.

---

## Support

- **Report a bug or request a feature:** [open an issue](https://github.com/BadRianDev/burnward/issues/new/choose)
- **Questions and help:** [SUPPORT.md](SUPPORT.md)
- **Email:** <badriandev@gmail.com>

See [SUPPORT.md](SUPPORT.md) for what to include in a report, and
[SECURITY.md](SECURITY.md) for reporting security issues privately.

When reporting a problem, please attach the error log if it exists:

```
%LOCALAPPDATA%\Programs\Burnward\errors.log
```

If the install folder is not writable, such as for the MSIX package, the log
goes to `%LOCALAPPDATA%\Burnward\errors.log` instead. The tray menu has
**Help and support > Open error log folder**, which opens whichever one is in
use.

---

## About this repository

Burnward is commercial software, so its source code is not published here. This
repository hosts the downloads, documentation and support channels.

---

## Privacy

Burnward makes no network connections whatsoever. Screen captures stay in memory
and are never written to disk. The only file it writes is an error log in its
own install folder. See [PRIVACY.md](PRIVACY.md).

## Licence

Burnward is provided **as is**, with no warranty of any kind, and the developer
and publisher accept no liability for any claim or damage. See [EULA.txt](EULA.txt)
for the full terms, which you accept by installing or using the software.
