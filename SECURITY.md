# Security Policy

## Supported versions

The most recent release is the only supported version.

| Version | Supported |
|---|---|
| 1.0.x | Yes |
| older | No |

## Reporting a vulnerability

**Please do not report security vulnerabilities in public issues.**

Report privately by either:

- GitHub's [private vulnerability reporting](https://github.com/BadRianDev/burnward/security/advisories/new), or
- Email to <badriandev@gmail.com> with `SECURITY` in the subject line.

Please include a description of the problem, the steps to reproduce it, the
Burnward and Windows versions, and the impact as you see it.

You can expect an acknowledgement within 7 days. Because this project is
maintained by one person in their spare time, a fix may take longer, and you
will be kept informed. Credit will be given for responsible disclosure unless
you prefer otherwise.

## Scope

Burnward runs entirely on the local machine with the privileges of the user who
started it. It has no network functionality, no server, and no update mechanism,
so there is no remote attack surface.

Areas worth scrutiny:

- The installer (`Setup.exe`), which writes to `%LOCALAPPDATA%`, the
  `Run` registry key, and the Start Menu.
- The in-memory screen capture, which may contain sensitive screen contents.
- The error log written to the install folder.
- Brightness control via DDC/CI and the WMI brightness interfaces.

## Antivirus false positives are not vulnerabilities

Microsoft Defender may block or flag Burnward. It captures the whole screen and
displays fullscreen always-on-top windows, which resembles screen-locking
malware, and unsigned low-prevalence binaries are treated with suspicion.

This is a false positive and is tracked as a normal issue, not a security
report. See the
[Known issue section in the README](README.md#known-issue-windows-may-block-the-app-from-starting).

If you believe Burnward is genuinely doing something malicious, that **is** a
security report - please use the private channels above.
