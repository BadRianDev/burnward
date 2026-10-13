# Support

Burnward is maintained by one developer in their spare time. Support is offered
on a best-effort basis, with no guaranteed response time.

## Where to go

| What you need | Where |
|---|---|
| Report a bug | [New issue](https://github.com/BadRianDev/burnward/issues/new?template=bug_report.yml) |
| Request a feature | [New issue](https://github.com/BadRianDev/burnward/issues/new?template=feature_request.yml) |
| Ask a question | [New issue](https://github.com/BadRianDev/burnward/issues/new?template=question.yml) |
| Report a security problem | See [SECURITY.md](SECURITY.md) - please do **not** open a public issue |
| Anything else, or you cannot use GitHub | <badriandev@gmail.com> |
| Purchase or refund of a Microsoft Store copy | Microsoft Store support, not here - see below |

Please search [existing issues](https://github.com/BadRianDev/burnward/issues?q=is%3Aissue)
before opening a new one.

## What to include in a bug report

The issue form asks for these, but if you email instead, please include:

1. **Burnward version** - right-click the tray icon, *License / About*.
2. **Windows version** - press `Win+R`, type `winver`, and copy the version and build.
3. **How you installed it** - `Setup.exe`, the MSIX package, or the Microsoft Store.
4. **What happened**, and what you expected instead.
5. **Steps to reproduce**, if you can find them.
6. **Monitor setup** - how many displays, their resolutions, and your display
   scaling percentage (*Settings > System > Display > Scale*). A large number of
   issues are specific to multi-monitor or mixed-DPI setups.
7. **The error log**, if present.

### Finding the error log

The easiest way is the tray menu: right-click the tray icon, then
**Help and support > Open error log folder**.

Burnward writes unexpected errors to:

```
%LOCALAPPDATA%\Programs\Burnward\errors.log
```

If that folder is not writable, such as when installed from the MSIX package,
the log goes to `%LOCALAPPDATA%\Burnward\errors.log` instead.

Paste the path into File Explorer's address bar to open the folder. The log
contains only timestamps, error messages and stack traces. It contains no
personal data and is never transmitted anywhere - you choose whether to share it.

### Screenshots

Burnward's overlay is deliberately invisible to screenshots and screen
recorders, because the app excludes itself from screen capture so it can
re-photograph your desktop without photographing itself. A screenshot will show
your desktop *without* the lens.

If you need to show the lens, take a photo with a phone.

## Common problems

**"Access is denied" when launching.** Microsoft Defender's attack surface
reduction rules are blocking it. See the
[Known issue section in the README](README.md#known-issue-windows-may-block-the-app-from-starting).

**The display never switches off.** Check that **Keep awake** is unticked in the
tray menu. With it unticked, Burnward does not interfere with your power plan.

**The screen stays dim after exiting.** Brightness is restored when the lens
exits normally. If the process was killed, untick and re-tick **Dim screen**, or
adjust brightness in *Settings > System > Display*.

**Brightness control does nothing.** Dimming uses DDC/CI for external monitors.
Not all monitors implement it, and some require it to be enabled in the
monitor's own on-screen menu.

## Store purchases

If you bought Burnward from the Microsoft Store, refunds and billing are handled
by Microsoft, not by this repository. Use
<https://support.microsoft.com/> or your Microsoft account's order history.

Technical problems are still welcome here.
