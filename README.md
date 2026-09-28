<p align="center">
  <img src="docs/Seasonality_Tracker.png" alt="Seasonality Tracker" width="100%">
</p>

<h1 align="center">Seasonality Tracker</h1>

<p align="center">
  Log, name and safely store seasonal reference photography and footage — on location, offline.<br>
  By <a href="https://vfxtools.co.uk">VFX Tools Ltd</a>.
</p>

<p align="center">
  <a href="../../releases/latest"><img src="https://img.shields.io/github/v/release/VFXToolsltd/seasonality-tracker?label=latest&color=0f6e56" alt="Latest release"></a>
  <img src="https://img.shields.io/badge/platform-macOS%20%7C%20Windows-lightgrey" alt="Platforms">
  <img src="https://img.shields.io/badge/licence-proprietary-black" alt="Licence">
</p>

---

This repository carries the **downloadable builds** of Seasonality Tracker. The
source code is private; only the finished applications are published here.

- **[⬇ Download the latest release](../../releases/latest)**
- **[Install on a Mac — step by step](INSTALL-MAC.md)**
- **[How to log a card — the team guide](GUIDE.md)**
- [Terms of use](TERMS.md) · [Security](SECURITY.md)

---

## What it does

Seasonality Tracker is for teams shooting **seasonal reference** — the same trees,
streets and landscapes photographed again and again as the season turns, so that
plates shot out of season can be matched and corrected later.

**Seasonality Tracker** (everyone in the field)

- Point it at a camera card or a folder. Stills and footage from Canon, Sony and
  phones appear as pictures; a RAW + JPEG pair is one picture.
- Tag the whole card once — location, phase of the season, scene — and just the
  shots that differ.
- **Ingest** copies every file into your own library under a standard name and
  folder, **re-reads each copy and checks it matches the original**, and writes a
  sidecar with its tags. Your originals are never moved, renamed or changed.
- Every file gets a row in a spreadsheet log in your library. You can correct tags
  in it; the app only ever adds rows.
- Works **fully offline**. No account, no internet, no cloud.

**Seasonality Tracker Combine** (the office)

- Combines each person's library onto one central drive, checking every file
  against the fingerprint taken when it was ingested.
- Rebuilds one master spreadsheet of everything, shows what is still only on
  people's cards and laptops, and which locations still need a visit.
- Builds vendor packages (full-resolution originals, checksums, a spreadsheet and a
  contact sheet) and audits the central drive.

---

## Download

From the **[Releases](../../releases/latest)** page:

| File | Who | For |
|------|-----|-----|
| `Seasonality-Tracker-V<version>-macOS-arm64.zip` | Everyone | macOS on Apple silicon (M1 and later) |
| `Seasonality-Tracker-V<version>-Windows-x64.zip` | Everyone | Windows 10 / 11, 64-bit |
| `Seasonality-Tracker-Combine-V<version>-macOS-arm64.zip` | The office only | macOS on Apple silicon |
| `Seasonality-Tracker-Combine-V<version>-Windows-x64.zip` | The office only | Windows 10 / 11, 64-bit |

If you are logging cards, you only need **Seasonality Tracker**. Each release also
ships a **`SHA256SUMS`** file — see [Verifying your download](#verifying-your-download).

---

## How to install

The app is not code-signed, so macOS and Windows warn the first time you open it.
That is expected for an in-house tool; you clear the warning **once**.

### macOS — short version

1. Unzip, drag **Seasonality Tracker** into **Applications**.
2. Open **Terminal** and run, once:

   ```bash
   xattr -cr /Applications/Seasonality\ Tracker*.app
   ```

3. Open it from Applications, then double-click the **setup file** (`.tvsetup`)
   the office sent you. It carries the location list; the office can also send
   the list itself as a CSV ([format](GUIDE.md#the-location-list)).

Full walkthrough, with what each prompt means: **[INSTALL-MAC.md](INSTALL-MAC.md)**.

### Windows

1. Download the Windows zip. **Right-click → Properties → tick "Unblock" → OK.**
2. Right-click → **Extract All…** to a permanent folder (e.g. in Documents).
3. Run **Seasonality Tracker V<version>.exe** from that folder. If SmartScreen shows
   *"Windows protected your PC"*, click **More info → Run anyway**.
4. Open the setup file the office sent you: **Settings → Open setup file…**

---

## System requirements

|         | Minimum |
|---------|---------|
| macOS   | macOS 13 (Ventura) or later, Apple silicon (M1 or later) |
| Windows | Windows 10 or 11, 64-bit |
| Disk    | ~150 MB for the app, plus room for your photos and footage |
| Network | None |

No Python, ExifTool or other software is needed — everything is bundled.

---

## Updating

The app never checks for updates on its own. When the office tells you there is a
new version, download it from the [Releases](../../releases/latest) page and
install it the same way. Your settings and your library are kept — they live
outside the app.

---

## Verifying your download

Optional, but quick. In Terminal:

```bash
cd ~/Downloads
shasum -a 256 Seasonality-Tracker-*.zip
```

Compare the long code it prints with the line for the same file in the release's
`SHA256SUMS`. If they match, the download arrived intact.

---

## Troubleshooting

| Symptom | Fix |
|---------|-----|
| macOS: *"…is damaged and can't be opened"* or *"cannot be opened because the developer cannot be verified"* | Run the `xattr -cr` line above. It is the unsigned-app warning, not a broken download. |
| macOS asks to allow access to a card, a drive or Documents | Click **Allow** — the app needs to read your card and write your library. |
| *"Timezone not known"* | Open your setup file again: **Settings → Open setup file…** |
| *"Not enough space on the library drive"* | The app refuses to start a copy that would not fit. Free space, or choose a bigger drive in **Settings**. |
| *"The last ingest into this library was cut off"* | The laptop slept, lost power or a drive was pulled. Files already copied are recorded; ingest the card again — they show as duplicates. |
| *"Log not updated"* | The log is open in Excel. Close it and press **Write log**. Nothing is lost. |

Anything else: tell the office, and **keep the card**.

---

## Uninstalling

- **The app** — drag it from Applications to the Bin (Windows: delete its folder).
- **Your settings** — `~/.seasonality_tracker/` in your home folder (in Finder:
  **Go → Go to Folder…**, type `~/.seasonality_tracker`).
- **Your library** — the folder or drive you chose. It holds your photos and footage:
  **do not delete it until the office has combined it.**

---

## Privacy

Everything stays on your own machines and drives. The app makes **no network
connections**, sends no telemetry and does not use any AI service.

## Terms

© VFX Tools Ltd. All rights reserved. Provided **as is**, without warranty, and with
no liability accepted — see **[TERMS.md](TERMS.md)** (also the **About** button in
the app). This repository contains compiled builds only — no source code.

## Support

Questions or problems: **[vfxtools.co.uk](https://vfxtools.co.uk)**.
