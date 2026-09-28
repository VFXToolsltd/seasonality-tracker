# Installing Seasonality Tracker on a Mac

About ten minutes, once. You need:

- a Mac with **Apple silicon** (M1 or later) on **macOS 13 Ventura or later**
  — check with  → **About This Mac**: it should say *Chip: Apple M…*;
- the **setup file** the office sent you — a file ending in **`.tvsetup`**;
- the drive or folder your photos will live in (your laptop, or a portable drive).

---

## 1. Download

1. Open the **[latest release](../../releases/latest)**.
2. Under **Assets**, click **`Seasonality-Tracker-V<version>-macOS-arm64.zip`**.
   *(Not the one with "Combine" in the name — that is the office app.)*
3. It lands in **Downloads**. Double-click it to unzip. You now have
   **Seasonality Tracker V<version>**.

## 2. Move it to Applications

Drag **Seasonality Tracker V<version>** from Downloads into **Applications** in the
Finder sidebar.

> Upgrading? Drag the old version to the Bin first. Your settings and your library
> are not inside the app, so nothing is lost.

## 3. Clear the "unidentified developer" block — once

The app is built in-house and not signed with an Apple certificate, so macOS blocks
it the first time with *"…can't be opened"* or *"…is damaged"*. It is not damaged.

1. Open **Terminal** (Applications → Utilities → Terminal, or press **⌘ Space**
   and type *Terminal*).
2. Copy this line, paste it into Terminal and press **Return**:

   ```bash
   xattr -cr /Applications/Seasonality\ Tracker*.app
   ```

   Nothing is printed when it works. That is normal.
3. Close Terminal.

This removes the "downloaded from the internet" flag from this one app. You need
to do it again only after installing a new version.

## 4. First launch

1. Open **Seasonality Tracker** from Applications.
2. It opens with a welcome box: click **Open setup file…** and choose the
   **`.tvsetup`** file the office sent you. *(Or just double-click the setup file
   in Finder.)* It fills in your initials, the timezone and the location list.
3. macOS may ask whether the app can access **Documents**, **Downloads**, a
   **removable volume** (your card) or a **network volume**. Click **Allow** — it
   needs to read your cards and write your library.

## 5. Choose your library

1. **Settings → Library folder → Choose…** — a folder on your laptop, or your
   portable drive.
2. Click **Save**. It asks for a **name** for the library, e.g. `AB – T7`. The name
   is written into the folder, so it follows a portable drive between machines.

The top bar now shows your library. You are ready: **[how to log a card](GUIDE.md)**.

---

## Check it worked

- **Settings** shows your initials, your library and a timezone.
- The warning strip at the top of the window is gone.
- The **About** button (top right) shows the version and the terms of use.

## Where things are

| What | Where |
|------|-------|
| The app | `/Applications/Seasonality Tracker V<version>.app` |
| Your settings | `~/.seasonality_tracker/` (Finder: **Go → Go to Folder…**) |
| Your photos, footage and log | the library folder you chose, e.g. `/Volumes/T7/Seasonality/` |
| The log spreadsheet | `Seasonality_Log.xlsx` inside your library |

## Problems

| You see | Do this |
|---------|---------|
| *"…can't be opened because Apple cannot check it for malicious software"* | Step 3 was missed, or the path was typed wrongly. Paste the `xattr` line again exactly. |
| *"…is damaged and can't be opened. You should move it to the Bin"* | Same — step 3. The download is fine. |
| The app opens and immediately closes | Check the Mac has Apple silicon (M1 or later). Intel Macs are not supported. |
| *"Timezone not known"* | Settings → **Open setup file…** and choose your `.tvsetup` again. |
| It cannot see your card | System Settings → Privacy & Security → **Files and Folders** → allow Seasonality Tracker for removable volumes. |

Still stuck: tell the office, and keep the card.
