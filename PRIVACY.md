# Privacy Policy

**Burnward - Keeps your screen alive and burn-free**

Last updated: 13 October 2026

## Summary

**Burnward does not collect, store, or transmit any personal data.** It makes no
network connections of any kind.

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
| Mouse pointer position | The pointer is nudged a few pixels periodically so it cannot burn into the display. | Used immediately, never stored. |
| Your display brightness | So the previous brightness can be restored after the "Dim screen" option is used. | Held in memory while running. |
| Your preferences | To remember the "Keep awake", "Dim screen" and "Start with Windows" settings. | Windows registry, under `HKEY_CURRENT_USER\Software\Burnward`. |
| Error details | So faults can be diagnosed if you report a problem. | A plain text file, `errors.log`, in the app's own install folder. |

### About the screen capture

Burnward photographs your screen in order to magnify it. That image may contain
whatever was on screen at the time, which could include sensitive information.

For that reason the image is **held only in memory**, is **never saved to disk**,
is **never transmitted**, and is **discarded when the app exits**. The overlay
window is also excluded from screen capture, so other screen recorders cannot
capture Burnward's own window.

### About the error log

`errors.log` is created only when something goes wrong. It contains
timestamps, error messages and stack traces. It does not contain screen
contents, keystrokes, or personal information.

It stays on your computer. It is only ever shared if you choose to attach it to
a support request. You can delete it at any time.

## Children

Burnward is a utility application and is not directed at children. It collects
no data from anyone, including children.

## Permissions

Burnward requires no special Windows capabilities. It does not request access to
your files, camera, microphone, location, contacts, or network.

## Removing your data

All data is local. To remove it completely:

1. Uninstall Burnward from *Settings > Apps > Installed apps*.
2. Delete the install folder if any files remain:
   `%LOCALAPPDATA%\Programs\Burnward`
3. Delete the registry key `HKEY_CURRENT_USER\Software\Burnward` if you want the
   saved preferences gone.

## Changes to this policy

If this policy changes, the updated version will be published in this repository
with a new date at the top.

## Contact

Questions about privacy:

- Email: <badriandev@gmail.com>
- GitHub: <https://github.com/BadRianDev/burnward/issues>
