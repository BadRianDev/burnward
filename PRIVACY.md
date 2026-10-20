# Privacy Policy

**Burnward - Keeps your screen alive and burn-free**

Last updated: 20 October 2026

## Summary

**Nothing Burnward handles ever leaves your computer.** It makes no network
connections of any kind, and the developer receives no data about you.

To magnify your screen, Burnward necessarily reads what is displayed on it, and
that image may contain personal information. It is held in memory, never saved,
and never sent anywhere. The sections below set out exactly what the app
touches, why, and where it goes.

## Data the developer receives

**None.**

Burnward contains no telemetry, no analytics, no crash reporting, no
advertising, and no update checks. It does not create an account, and it does
not require one. There is no server, so there is nowhere for data to go.

The developer receives information about you only if you choose to contact them
directly, by opening an issue on GitHub or sending an email. In that case the
developer receives whatever you choose to put in that message.

## Data the app handles on your device

To do its job, Burnward processes the following locally. None of it leaves your
computer.

| Data | Why | Where it goes |
|---|---|---|
| An image of your screen | This is the image the magnifying lens moves across. It is re-captured about once a minute while running. | Held in memory only. Never written to disk, and discarded when the app closes. |
| Mouse pointer position | Read so the pointer can be shifted a few pixels periodically while the lens is running. | Used immediately, never stored. |
| Your display brightness | So the previous brightness can be restored after the "Dim screen" option is used. | Held in memory while running. |
| Your preferences | To remember the "Keep awake", "Dim screen" and "Start with Windows" settings. | Windows registry, under `HKEY_CURRENT_USER\Software\Burnward`. In the Microsoft Store version these are kept inside the app package and removed when you uninstall. |
| Error details | So faults can be diagnosed if you report a problem. | A plain text file, `errors.log`. See "About the error log" below for its location. |

### About the screen capture

Burnward photographs your screen in order to magnify it. That image may contain
whatever was on screen at the time, which could include sensitive information.

For that reason the image is **held only in memory**, is **never saved to disk**,
is **never transmitted**, and is **discarded when the app exits**. The overlay
window is also excluded from screen capture, so other screen recorders cannot
capture Burnward's own window.

### About the error log

`errors.log` is created only when something goes wrong. It contains timestamps,
error messages and stack traces. It never contains screen contents or
keystrokes.

Stack traces and error messages can include file paths, and a path under your
user profile contains your Windows user name. Beyond that, the log holds no
personal information.

Where the file is written depends on how Burnward was installed:

| Installed from | Location of `errors.log` |
|---|---|
| Microsoft Store | `%LOCALAPPDATA%\Burnward\errors.log` |
| `Setup.exe` | `%LOCALAPPDATA%\Programs\Burnward\errors.log` |

The Store version is packaged, and a packaged app cannot write into its own
installation folder, so the log is written alongside your other local
application data instead. The tray menu can open the file directly, whichever
location applies.

It stays on your computer. It is only ever shared if you choose to attach it to
a support request. You can delete it at any time.

## Children

Burnward is a utility application and is not directed at children. It collects
no data from anyone, including children.

## Permissions

Burnward does not request access to your camera, microphone, location, contacts,
or network.

The Microsoft Store version is a packaged desktop application, so its listing
shows the permission **"Uses all system resources."** That phrase sounds much
broader than what Burnward does, and it is worth explaining rather than leaving
to guesswork.

Windows applies that single label to every traditional desktop program
distributed through the Store, because such programs run with the same rights
as any application you install yourself. It describes the *category* Burnward
belongs to, not features it uses. Burnward needs those rights for one reason:
to photograph the desktop and draw a window over it, which the restricted
sandbox used by other Store apps does not permit.

What Burnward actually does with that access is listed in the table above, and
nothing in it leaves your computer.

## Removing your data

All data is local. Start by uninstalling Burnward from
*Settings > Apps > Installed apps*.

**If you installed from the Microsoft Store**, that is all that is needed.
A packaged app's settings are stored inside the package rather than loose in
the registry, so they are removed with it. If you want the error log gone too,
delete `%LOCALAPPDATA%\Burnward`.

**If you installed using `Setup.exe`**, two items are left behind deliberately,
so that reinstalling keeps your preferences. Remove them by hand if you want
nothing left:

1. The install folder, if any files remain: `%LOCALAPPDATA%\Programs\Burnward`
2. The registry key `HKEY_CURRENT_USER\Software\Burnward`

## Changes to this policy

If this policy changes, the updated version will be published in this repository
with a new date at the top.

## Contact

Questions about privacy:

- Email: <badriandev@gmail.com>
- GitHub: <https://github.com/BadRianDev/burnward/issues>
