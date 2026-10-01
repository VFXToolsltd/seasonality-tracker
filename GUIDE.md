# Seasonality Tracker — how to log a card

## Once: set up (5 minutes)

1. Install the app — **[INSTALL-MAC.md](INSTALL-MAC.md)** (Mac) or the README (Windows).
2. Double-click the **setup file** the office sent you (`… .tvsetup`). It fills in your
   initials, the timezone and the location list. *(Or: Settings → Open setup file…)*
3. **Settings → Library folder**: choose where your files go — a folder on your laptop
   or your portable drive. Give it a name when asked, e.g. `AB – T7`.

No internet is needed, ever. Everything is saved in your library folder.

## Every card

1. **Choose folder or card…** — pick the card (or the folder you copied it to).
   Every shot appears as a picture. A RAW+JPEG pair is one picture.
2. **Tag the whole card** with nothing selected. Three things are required:
   - **Location**
   - **Phase** — how far the leaves have turned
   - **Scene / slate** — or tick **Generic** if it is not for a particular scene
   The rest is optional but valuable: tree, angle, % turned, leaf litter…
   Tags from your last card are already filled in — check them.
3. **Shots that differ** — click them (Shift-click / Cmd-click for several) and change
   just those. **Select next burst (B)** picks the next run of shots taken without a
   pause — usually one tree — so you can tag it in one go; press B again for the next.
   A **●** marks a shot with its own tags. **Esc** goes back to the whole card.
4. **Blurry or useless shot?** Select it and press **X** (or **Leave out**). It
   disappears and is not copied or logged; nothing on your card is changed. The app
   remembers, so it stays out if you choose the card again. Changed your mind? Tick
   **Show left-out**, select the greyed shot and press **X** again.
5. **Same tree over time?** Pick it in **Tree**, or **+ New tree** the first time you
   shoot it. New trees get your initials, e.g. `AB-T004`, so nobody else's numbers
   can clash with yours. That is how we follow one tree through the season.
6. **Camera clock wrong?** Take a photo of your phone's clock. Select that photo,
   click **Camera clock**, type the time the phone showed.
7. **Preview…** — shows every new name, anything missing and the shots you left out.
   Fix what it lists.
8. **Ingest** — copies and checks every file. Your originals are never changed.

In the tag panel, locations on the shoot schedule on the day your card was shot are
listed first with ★, and ones still needing a visit are marked — hints, not choices.

## The log

Every file you ingest gets a row in **`Seasonality_Log.xlsx`** in your library folder.
**Open log** (top bar) opens it.

- You can **correct tags** in it (phase, angle, scene, notes…) — the tag columns have
  dropdowns. Your corrections are kept; the app only ever adds rows at the bottom.
- The grey columns (file name, checksum, camera data) are locked: they are the file's
  identity. To add a column of your own: **Review → Unprotect Sheet** (no password).
- **Excel open while ingesting?** On Windows the log cannot be updated while it is
  open. Nothing is lost — close Excel and press **Write log**; the top bar says when
  the log is behind.

## Keep the card

**Do not format the card until your library has been combined at the office.**
Until then the card is one of only two copies.

## Handing in

Bring your library — the portable drive, or the laptop folder copied to a drive — to
the office Mac mini. The office combines it: every file is checked against the
fingerprint taken when you ingested it and copied to the office drive, and your log
joins the master spreadsheet. After that, your card can be formatted and the laptop
copy cleared — that is your decision; the app never deletes anything.

### At the office (Seasonality Tracker Combine)

1. Plug in the drive (or open the folder on the network). **Choose library…**
2. Read the card: how many files are to copy, anything marked ⚠.
3. **Combine.** Wait for the message. "Every file of this library is on the central
   drive" means the card may now be formatted — by its owner, when they choose.
4. Amber rows in the master are the same file logged twice with different tags —
   agree which is right and correct it in the owner's log; the next Combine takes it.

The master (`Seasonality_Master.xlsx` on the office drive, **Master ▾ → Open
master**) is rebuilt on every Combine. Never type into it — correct tags in the
library's own log.

- **Coverage** — which EXT locations still need a visit, most urgent first. New places
  or shoot dates: **Import locations…** with the location list (CSV — see below).
- **Package…** — name the vendor, pick what they get, **Build package**. The folder
  (in `_packages` on the office drive) is ready for Aspera; files they already have
  are left out.
- **Audit…** — Quick (sizes, minutes) or Full (every fingerprint, overnight). It
  only reports.
- **Team ▾ → Export reference file…** — after new locations, trees or the window
  dates: send the file to the team (they use **Settings → Load file…**). **Setup file
  for a team member…** — everything a new person needs, in one file.

The office sends a fresh setup or reference file now and then (new locations, trees
others have started). **Settings → Load file…** takes it.

## The location list

The places to shoot come from a **location list** — a spreadsheet saved as **CSV**
(in Excel: *File → Save As → CSV UTF-8*). Nothing about a location is built into the
app; loading the list is what starts the data.

| Column | Example | |
|---|---|---|
| **Real Address** (filmed at) | `Market Square` | the place — each different one becomes a location |
| **Script Location** | `HARBOUR - NIGHT` | the script's name for it — several can share a place |
| **Shoot Dates** | `2026-09-09` | one or more, YYYY-MM-DD |
| **Episode / Scene** | `101-4` | |
| **Slates** | `104, 104A` | what reference can later be matched to |
| INT/EXT | `EXT` | optional — without it every row counts as exterior |

Columns are found by name, in any order; others (such as a slate count) are ignored.
One row per place per scene per day is fine — rows for the same place are merged.
Loading an updated list adds new places and refreshes dates and scenes; coordinates
and notes someone typed are kept.

- **The office:** Combine → **Coverage → Import locations…**, then **Team ▾ → Export
  reference file…** to send it to everyone.
- **In the field** (if sent the list directly): **Settings → Load file…**

## If something goes wrong

- **"Log not updated"** — close the log in Excel, press **Write log**.
- **A time marked ⚠** — the camera had no proper time; check it in the Preview.
- **"Timezone not known"** — open your setup file again (Settings → Open setup file…).
- Anything else: tell the office, and keep the card.
