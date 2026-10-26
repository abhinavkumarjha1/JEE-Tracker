# JEE Tracker

A Windows desktop app for tracking JEE Advanced preparation. Everything stays on your computer.

> This repository contains **no source code**. It holds the installer releases, the license and the verification notes.

## Download

Get the latest installer from the [Releases page](https://github.com/abhinavkumarjha1/JEE-Tracker/releases/latest): `JEE-Tracker-Setup-<version>.exe`.

- Windows 10 or 11, 64-bit.
- Installs for the current user (no administrator rights needed). The installer asks you to accept the [license](LICENSE) first.
- A newer version installs over an older one and keeps your data.

## What it does

- **Syllabus progress** for Physics, Chemistry and Maths, chapter by chapter, with lecture / practice / revision tracking and priorities.
- **Study Clock**: timer and countdown, start a session from today's tasks, fullscreen mode that keeps the screen awake.
- **Planner**: side calendar with a time grid, Study and Break tasks, repeating tasks (daily, weekly, monthly, yearly or custom).
- **Logbook**: analysis, task log, session log, an automatic daily log and a mistake log.
- **Study Hours**: totals, streaks, goal tracking and charts.
- **Exam countdown** and **mock score** tracking.
- Six themes (Midnight, Graphite, Dusk, High Contrast, Daylight, Paper) and your own accent color.

## Check your download

Every release lists the installer's SHA-256 and ships a `SHA256SUMS.txt`. Compare it before you run the file.

PowerShell:

    Get-FileHash .\JEE-Tracker-Setup-2.4.1.exe -Algorithm SHA256

Command Prompt:

    certutil -hashfile JEE-Tracker-Setup-2.4.1.exe SHA256

Expected for 2.4.1:

    15a5366729ce274a94dec503d544661b3c89306b1b1195fd274d79f505849ccf

Releases here are **immutable**: once a release is published, GitHub locks its files and its tag, so nobody, the owner included, can swap the installer for a different file under the same version. GitHub also signs a release attestation that records the SHA-256 of every file in the release. If you have the [GitHub CLI](https://cli.github.com/), you can check your download against it:

    gh release verify-asset v2.4.1 JEE-Tracker-Setup-2.4.1.exe -R abhinavkumarjha1/JEE-Tracker

Only installers from this repository's [Releases page](https://github.com/abhinavkumarjha1/JEE-Tracker/releases) are official. Check any other copy against the SHA-256 above.

## "Windows protected your PC"

The installer is **not code-signed yet**, so Windows SmartScreen shows a blue "Windows protected your PC" page the first time you run it.

1. Check that the SHA-256 above matches the file you downloaded.
2. Click **More info**, then **Run anyway**.

SmartScreen builds reputation for unsigned files one file at a time, so this warning comes back with every new version. On Windows 11 with **Smart App Control** turned on, Windows can block unsigned apps with no "Run anyway" option. Microsoft explains both here: [SmartScreen reputation for Windows app developers](https://learn.microsoft.com/en-us/windows/apps/package-and-deploy/smartscreen-reputation).

## Your data and privacy

- No account, no analytics, no ads. The app's own code makes no network requests, and its fonts are bundled.
- Your data is one file, `jee-tracker-data.json`, in `%APPDATA%\jee-tracker\`, with rolling backups next to it. Settings has a Data Backup section. Copy that folder before you upgrade if you want a safety copy.

## License

Copyright (c) 2026 abhinavkumarjha1. All rights reserved.

JEE Tracker is proprietary software, free for personal study use. You may not redistribute, modify, repackage, reverse engineer or reuse any part of it. The exact terms are in [LICENSE](LICENSE). The components that keep their own licenses (Electron, Chromium and three fonts) are listed in [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt).

## Feedback and bugs

Open an [issue](https://github.com/abhinavkumarjha1/JEE-Tracker/issues). Do not paste your data file into an issue. For security problems see [SECURITY.md](SECURITY.md).
