# Sideline — Soccer Coach Tracker

A single-file, offline browser app for coaching a 9v9 (11U) soccer team:
track positions, substitutions, playtime, and goals during games, then
review minutes / partnerships across the season.

**Everything is one file: `index.html`.** No build, no internet needed at the field.
Data auto-saves to the browser's local storage on the device you use.

## Get it on your phone
Pick one:
- **Netlify Drop (easiest):** go to https://app.netlify.com/drop and drag the
  `soccer-app` folder onto the page. You get a URL; open it on your phone and
  "Add to Home Screen" so it launches full-screen like an app.
- **Same Wi-Fi:** run `python -m http.server 8755` inside this folder on your
  computer, then open `http://<computer-ip>:8755` on your phone.
- **Just try it:** double-click `index.html` to open in any browser.

> Local storage is per-device/per-browser. Use the **same device** all season,
> and use **Export** (JSON) periodically as a backup.

## Two pages — tabs at the bottom
- **⚽ Field:** the half-pitch + bench (who's on, in what position).
- **📊 Game data:** captains, live playtime bars, goals log, and game notes.
Switch with the **tab bar at the bottom**. The score + clock header stays pinned.

**Swipe lock (🔒 in the header):** the page is **locked by default** so grabbing a
player never slips you onto the other page. Tap it to **🔓 unlock** swipe if you
prefer gestures. Either way the tabs always work, and dragging a player never
moves the page.

## Formations & custom positions
Pick a shape in **☰ menu → Formation**: **3-4-1** (default — 1 striker, 4 mid,
3 defense), 4-3-1, 2-4-2, 3-3-2, 3-2-3, 2-3-3. Or tap **✎ Edit positions** to
drag each spot exactly where you want it — that saves as your **Custom** layout.
Players are shown as **rectangular tiles** (number + name).

## How to use it (game-day flow)
1. **Roster** (bottom-right): add your players (name, number, color). A demo
   roster is preloaded — edit or delete it.
2. **＋ Add** (bench header): quick-add a player — type a name and hit Enter
   (number and color auto-fill). **Here?** marks absent players, who drop off
   the bench for that game. New games start with everyone present.
3. **Pre-prepare a lineup:** drag your starters into positions, then in **☰ menu →
   Save lineup as default**. New games auto-load that lineup (skipping anyone
   marked absent), so game day opens pre-populated. You can also tweak the
   active game ahead of time — it's saved automatically.
4. **▶ Start** the clock at kickoff — playtime begins for everyone on the field.
5. **Subbing:** drag a bench player onto an on-field player. It **queues**
   (shown ghosted/italic under the spot) — it does NOT go in yet.
   - Tap a queued sub to choose whether the player coming off goes to the
     **bench** or **moves to another open position**.
   - Queue as many as you want, then hit **"Send in ▶"** when the ref waves
     them on — they all swap at once.
6. **Move a player** (no sub): drag an on-field player to another spot (swaps
   or repositions immediately).
7. **Take someone off:** drag them onto the bench area.
8. **Captains** (Data page): tap up to two players. A gold **C** shows on their
   token; counts are tracked across the season for equity.
9. **Goals:** **+ Goal** under your score → pick scorer + optional assist.
   **+ Goal** under the opponent just bumps their score.
10. **Notes** (Data page): type, or tap the 🎤 to dictate (uses your phone's
    speech-to-text). Saved per game and included in the CSV export.
11. **Tap any player** to see playtime, bench time, position breakdown, goals.
12. **☰ menu:** opponent, formation (3-3-2 / 3-2-3 / 2-3-3), halves, lineup
    tools, playtime/goals sheets, **New game**, and **Export**.
13. **Season summary** (menu): total minutes, goals, captaincies, and "most time
    together" pairs across every game — exportable to CSV.

## Notes
- The master clock pauses playtime too (halftime = no one accrues minutes).
- **↶ Undo** reverses the last action (mis-drags happen on the sideline).
- Bench tiles + playtime bars are sorted least-played-first so under-played kids
  surface — quick equity check at a glance.
- Dictation uses the browser's speech recognition (best in Chrome on Android).
  On iPhone, if the mic button is disabled, use the keyboard's mic key instead.
