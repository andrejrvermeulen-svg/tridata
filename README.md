# TRIdata

**Swim. Bike. Run. Analyze. Improve.**

A single-page triathlon benchmarking app. Log race splits, physiology tests and
training sessions, and see exactly where each one sits against five real
performance gates — from first finish to the professional start list.

No build step, no framework, no server. One HTML file plus icons.

---

## Put it online in about three minutes

You do not need Git, a terminal, or any desktop app. Everything below happens in
your browser.

1. Go to **github.com** and click **New repository**.
   - Name it `tridata`
   - Set it to **Public** (GitHub Pages needs this on free accounts)
   - Do **not** tick "Add a README" — this folder already has one
   - Click **Create repository**

2. On the next screen click **uploading an existing file**.
   - Drag in **everything** from this folder: `index.html`, `manifest.webmanifest`,
     `sw.js`, `README.md`, `.nojekyll`, and all the `.png` icons
   - Click **Commit changes**

3. Go to **Settings → Pages** (left sidebar).
   - Under *Build and deployment* → *Source*, choose **Deploy from a branch**
   - Branch: **main**, folder: **/ (root)** → **Save**

4. Wait about a minute, then refresh the Pages screen. Your link appears at the top:

   ```
   https://<your-username>.github.io/tridata/
   ```

That link is the app. Bookmark it, or open it on your phone and use
**Share → Add to Home Screen** — it installs with the TRIdata icon and opens
full-screen like an app, no app store involved.

### Updating it later

Open `index.html` in the repo on github.com, click the pencil icon, edit, commit.
Pages redeploys on its own within a minute. If a change does not appear, bump
`CACHE = 'tridata-v1'` to `v2` in `sw.js` so browsers drop the old cached copy.

---

## Where your data lives

Everything you log is stored in **your own browser** (`localStorage`) on the
device you logged it on. Nothing is uploaded anywhere and nobody else can see it.

That has one consequence worth knowing: the log does not follow you between your
phone and your laptop, and clearing site data wipes it. So use
**Athlete → Download JSON backup** every so often. That file is your record.

---

## What it measures

| Tab | What goes in |
|---|---|
| **Dashboard** | Your Elite Index, five pillar scores, and each race split against the gates |
| **Race log** | Swim / T1 / bike / T2 / run for every race, all four distances |
| **Benchmark tests** | 28 repeatable measures — CSS, FTP W/kg, 5 km TT, VO₂max, lactate threshold, brick decay, HRV, body composition and more |
| **Training log** | Every session: duration, distance, RPE, average heart rate |
| **Load & recovery** | Weekly volume by discipline, acute-to-chronic ratio, morning HRV and resting heart rate |
| **Athlete** | Profile, target race and time, backups |
| **Standards** | The full benchmark tables for all four distances and every test |
| **Test protocols** | How to run each test so the number means something |

### Times are decimal minutes

Every duration field takes **decimal minutes** — `68.4` is 68 minutes 24 seconds.
You can also type `1:08:24` or `68:24` and it converts as you type, showing both
forms under the field. Everything is stored as a decimal number, so exports drop
straight into a spreadsheet.

### Where the standards come from

The Elite gate on each distance is anchored to a real championship performance
rather than a round number:

- **Olympic** — Matt Hauser, 1:42:42 (17:49 / 54:31 / 29:16), WTCS Grand Final Wollongong 2025
- **70.3** — Jelle Geens, 3:42:52 (23:19 / 2:09:38 / 1:07:35), 70.3 World Championship Marbella 2025
- **Ironman** — Kristian Blummenfelt, 7:21:12 (39:41 / 4:02:40 / 2:35:24), Cozumel 2021; Kona course record 7:35:53, Patrick Lange 2024
- **National gate (Ironman)** — the observed Kona-qualifying band for men 30–44

Full provenance is in the app's **Standards** tab.

---

## Files

```
index.html              the whole app — HTML, CSS and JS in one file
manifest.webmanifest    lets it install to a phone home screen
sw.js                   service worker, so it opens offline after one visit
icon-192.png            \
icon-512.png             |  app icons
apple-touch-icon.png     |
favicon-32.png          /
tridata-logo.png        full logo with wordmark
.nojekyll               tells GitHub Pages to serve the files as-is
```
