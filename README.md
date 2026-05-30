# Workout

A personal gym tracking app built as a single HTML file. No server, no account, no internet required after the first load. Add it to your iPhone home screen and it runs like a native app.

---

## What it does

Tracks your training across five workout types, logs every session to your device, and builds a history of sets, weights, reps, holds, and notes — all stored locally in your browser.

---

## Workout programs

| Program | Focus |
|---|---|
| **Pull + Core** | Back, Biceps, Posture |
| **Push** | Chest, Shoulders, Triceps |
| **Lower Body** | Glutes, Hamstrings, Core |
| **Splits + Flex** | Toward full front split |
| **Conditioning** | Sled, Rower, Mobility |

Every exercise has **3–4 swap alternatives** — gym machine, home bodyweight, band-only — so you always have an option regardless of what equipment is available.

---

## Features

### Workout tracking
- Log sets with reps, weight (kg), or bodyweight
- **Hold timer** for plank, stretch, and isometric exercises — tap to start, tap to stop, seconds logged automatically
- **BW / kg toggle** per set — flick between bodyweight and weighted versions mid-workout
- **Swap alternates** on any exercise with one tap
- **Rest timer** — 0:45 / 1:00 / 1:30 / 2:00 presets with a large pop-out countdown
- **Session timer** — auto-starts on first input, shows total workout duration

### Home screen
- Today's date displayed large with a daily rotating motivational quote
- **Energy check** — log how you feel before training (Average / Strong / Cooked)
- **Session checklist** — Warmup · Main Workout · Core · Stretch · Log notes
- **Quick Start** — one tap to reload your last workout's exercise selection and warmup type
- **Workout day cards** — visual grid of all five programs with background photos

### Warmup
- Select warmup type before each session: **Bike · Rower · Skier · Skipping · Treadmill**
- Log duration in minutes
- Warmup type and duration saved with the session record

### Cool Down / Stretch
- Collapsible cool-down section at the bottom of every workout
- Six guided stretches: Child's Pose, Hip Flexor, Hamstring, Supine Twist, Chest Opener, Box Breathing
- Hold timers on every stretch, logged with the session if completed

### Progress & history
- **Stats bar** — total sessions, sessions this month, current consecutive-day streak
- **4-week heatmap** — calendar grid showing training days
- **Session cards** — tap to expand full detail: exercises, sets, weights, reps, warmup, energy, duration
- **Editable notes** — felt / next time fields are editable directly in the expanded card
- **Delete sessions** — remove a mistaken or duplicate log with confirmation
- **PB tracking** — personal best detected automatically per exercise; badge shown on session card and exercise header
- Multiple sessions on the same day are fully supported and clearly labelled by workout type

### Audio cues
| Moment | Sound |
|---|---|
| Final 3 seconds of rest timer | Ascending scale tones: C5 → E5 → G5 (game-style, one note per second) |
| Rest timer complete | C major arpeggio rising into a full chord hit with bass |
| New personal best logged | Grand fanfare: ascending motif + 7-note chord with room reverb |

### Data
- **Export** — downloads your full session history as a `.json` backup file
- **Import** — restores from a backup file
- All data lives in `localStorage` on your device — nothing leaves it

---

## Installation

No build step. No dependencies. Open the file and go.

```
index-2.html
```

**To use as a home screen app on iPhone:**
1. Open `index-2.html` in Safari
2. Tap the Share button
3. Tap **Add to Home Screen**
4. Tap **Add**

The app runs full-screen without the browser chrome, just like a native app.

**To use in a browser:** Just open the file directly — Chrome, Safari, Firefox all work.

---

## File structure

```
fitness-app/
├── index-2.html          ← the entire app (HTML + CSS + JS)
├── audio-demo.html       ← standalone preview of the three audio cues
├── images/
│   ├── home-banner.jpg
│   ├── pull-card.jpg
│   ├── push-card.jpg
│   ├── lower-card.jpg
│   ├── splits-card.jpg
│   ├── conditioning-card.jpg
│   ├── pull-banner.jpg
│   ├── push-banner.jpg
│   ├── lower-banner.jpg
│   ├── splits-banner.jpg
│   └── conditioning-banner.jpg
└── app-icon-*.png        ← home screen icons (120, 152, 167, 180, 192, 512px)
```

---

## Tech

| Layer | Detail |
|---|---|
| Structure | Single HTML file — no framework, no bundler |
| Fonts | Bebas Neue (display), JetBrains Mono (UI), Inter (body) via Google Fonts |
| Audio | Web Audio API — all sounds synthesised in-browser, no audio files |
| Storage | `localStorage` — data persists across sessions on the same device |
| PWA | `apple-mobile-web-app-capable` meta tags for iOS home screen install |

---

## Backup & restore

Your data is stored only on your device. Export regularly.

1. Tap **Export** in the top-right corner — saves `workout-backup-YYYY-MM-DD.json`
2. Keep the file somewhere safe (iCloud, email to yourself)
3. To restore: tap **Import** and select the backup file

---

## Notes

- Designed for iPhone but works on any modern browser
- Dark theme only
- All weights in kilograms
- Location toggle: City Gym / Home — logged with each session for context
