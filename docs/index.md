---
title: Burnward
---

# Burnward

**Keeps your screen alive and burn-free.**

Burnward protects OLED, plasma and other burn-in prone displays from static
image retention. It photographs what is on your screen and sweeps a magnifying
lens across it, so no pixel stays still for long.

It runs on every attached monitor, and quits when you press **Esc**.

**Burnward never sends any data over the internet.** No telemetry, no analytics,
no accounts, no network connections at all.

---

## Get help

| What you need | Where to go |
|---|---|
| Report a bug | [Open a bug report](https://github.com/BadRianDev/burnward/issues/new?template=bug_report.yml) |
| Suggest a feature | [Open a feature request](https://github.com/BadRianDev/burnward/issues/new?template=feature_request.yml) |
| Ask a question | [Ask here](https://github.com/BadRianDev/burnward/issues/new?template=question.yml) |
| Report a security issue | [Privately, here](https://github.com/BadRianDev/burnward/security/advisories/new) |
| Email | [badriandev@gmail.com](mailto:badriandev@gmail.com) |

Support is provided on a best-effort basis by a single developer, so please be
patient.

---

## Frequently asked questions

### Burnward will not start, and Windows says "Access is denied"

Microsoft Defender's attack surface reduction rule *"Use advanced protection
against ransomware"* is blocking it. You can confirm this by looking for event
ID **1121** in the *Microsoft-Windows-Windows Defender/Operational* event log.

This is a false positive. Burnward captures the whole screen and shows
fullscreen always-on-top windows, which looks a lot like a screen locker to an
automated classifier, and new unsigned programs have no reputation to vouch for
them.

What to do:

- **On a work machine**, ask your IT department to allow the folder
  `%LOCALAPPDATA%\Programs\Burnward`. Exclusions you add yourself will be
  overridden by company policy.
- **On your own machine**, add that folder as an attack surface reduction
  exclusion from an elevated PowerShell window.
- **Or install the MSIX package**, which is signed.

Please [report it](https://github.com/BadRianDev/burnward/issues/new?template=bug_report.yml)
so it can be submitted to Microsoft for reclassification.

### My display never switches off while Burnward runs

Right-click the tray icon and make sure **Keep awake** is unticked. When it is
unticked, Burnward leaves your power plan alone and the display sleeps as
normal.

### The screen is still dim after Burnward closes

Brightness is restored automatically when the lens exits normally. If the
process was killed, untick and re-tick **Dim screen**, or set brightness in
*Settings > System > Display*.

### "Dim screen" does nothing on my external monitor

Dimming external monitors relies on DDC/CI. Not every monitor supports it, and
some need it switched on in the monitor's own on-screen menu.

### Why is Burnward invisible in my screenshots?

That is deliberate. Burnward excludes its overlay from screen capture so that
when it re-photographs your desktop every minute, it does not photograph itself
and create a hall-of-mirrors effect. The side effect is that screenshots and
screen recordings show your desktop without the lens.

To show the lens in a bug report, photograph the screen with a phone.

### What does Burnward do with my screen contents?

The captured image is held **in memory only**. It is never written to disk and
never transmitted. It is discarded when the app closes. See the
[privacy policy](https://github.com/BadRianDev/burnward/blob/main/PRIVACY.md).

### Where is the error log?

Right-click the tray icon, then **Help and support > Open error log folder**.

Otherwise it is at:

```
%LOCALAPPDATA%\Programs\Burnward\errors.log
```

If that folder is not writable, such as with the MSIX package, it goes to
`%LOCALAPPDATA%\Burnward\errors.log` instead.

It only appears if something has gone wrong, and contains timestamps, error
messages and stack traces - no screen contents, no personal data.

### How do I uninstall it?

*Settings > Apps > Installed apps*, find **Burnward**, and choose Uninstall.

---

## Links

- [Downloads and releases](https://github.com/BadRianDev/burnward/releases/latest)
- [Support details](https://github.com/BadRianDev/burnward/blob/main/SUPPORT.md)
- [Privacy policy](https://github.com/BadRianDev/burnward/blob/main/PRIVACY.md)
- [Licence](https://github.com/BadRianDev/burnward/blob/main/EULA.txt)
