# 🚀 AstroNova Cosmic Explorer

**A single-file, frontend-only cosmos in your browser.** Built for the NASA Space Apps Challenge 2026.

[![NASA Space Apps](https://img.shields.io/badge/NASA-Space%20Apps%202026-7df9ff?style=flat-square)](https://www.spaceappschallenge.org)
[![No Backend](https://img.shields.io/badge/backend-none-4dffb0?style=flat-square)]()
[![No API Keys](https://img.shields.io/badge/API%20keys-none-4dffb0?style=flat-square)]()
[![Offline Ready](https://img.shields.io/badge/offline-100%25-ffc84d?style=flat-square)]()
[![File Size](https://img.shields.io/badge/size-181%20KB-ff4d5e?style=flat-square)]()

> What if the entire cosmos fit inside a single HTML file?

---

## 🎯 The Pitch

AstroNova Cosmic Explorer is **one self-contained `index.html`** — 181 KB, no install, no signup, no API keys, no backend. Works by double-clicking the file in any modern browser, online or offline. Combines reference, calculators, and interactive training in one cohesive NASA-themed experience.

Built in under 48 hours for the NASA Space Apps Challenge.

---

## ✨ Features

### 1. 🪐 Solar System Explorer
**11 bodies in HD** — the Sun, all 8 planets, Pluto, and Earth's Moon. Click any body to open a glass-morphism datasheet with real NASA-sourced facts: diameter, mass, gravity, orbital period, moons, temperature, discovery year.

### 2. ⭐ Star Catalog
**8 scientifically notable stars** — Sirius, Betelgeuse, Rigel, Polaris, Vega, Proxima Centauri, Arcturus, and Antares. Each entry includes spectral type, surface temperature, distance in light-years, luminosity, and a narrative on why it matters.

### 3. 🧮 16 Mission Tools
**Practical spaceflight calculators** that run live in the browser:

| # | Tool | # | Tool |
|---|---|---|---|
| 1 | Light-speed Comm Delay | 9 | Cosmic Distance Converter |
| 2 | Weight on Other Worlds | 10 | Synchronous Orbit Altitude |
| 3 | Orbital Velocity & Period | 11 | Tsiolkovsky Rocket Equation |
| 4 | Mission Elapsed Time | 12 | Habitable Zone Calculator |
| 5 | Delta-V Budget Estimator | 13 | Solar Panel Power |
| 6 | Radiation Dose Estimator | 14 | Schwarzschild Radius (Black Hole) |
| 7 | Hohmann Transfer | 15 | Relativistic Time Dilation |
| 8 | Escape Velocity | 16 | Cosmic Velocities |

Every tool uses real physics formulas with real constants. Inputs update results instantly — no submit button, no page reload.

### 4. 🎓 Junior Astronaut Mission Trainer
**5 progressive missions** — each opens with a **themed mini-game**, then unlocks a 4-step decision briefing:

| Mission | Difficulty | Mini-Game | Badge |
|---|---|---|---|
| 🚀 Rocket Launch Sequence | Beginner | Hold THRUST, manage heat through Max-Q, reach 100 km orbit | Launch Specialist |
| 🛰️ ISS Rendezvous & Docking | Intermediate | Thrust/Brake/Align — soft-dock at < 0.2 m/s | Rendezvous Specialist |
| 🌙 Artemis Lunar Landing | Advanced | Tap thrust, dodge boulders, soft-land < 3 m/s | Lunar Lander |
| 🔴 Mars EDL — 7 Minutes of Terror | Expert | Time 4 EDL actions at the right altitude | Mars EDL Specialist |
| 🚷 EVA Emergency Response | Advanced | Fly a SAFER jetpack, rescue crewmate in 60s | EVA Emergency Specialist |

Pass one mission to unlock the next. Complete all 5 to earn **Junior Astronaut Certification**. Progress saved in `localStorage`.

### 5. 🤖 ARIA — Built-in AI Assistant
A knowledge engine that runs **entirely in your browser** — no API keys, no external calls, no telemetry.
- 40+ curated entries: solar system, stars, NASA missions, astrophysics, the app itself
- Topic classifier rejects off-topic questions
- Keyword matcher picks the best answer
- Toggle with `Ctrl+Shift+A` or click the floating button

---

## 🚀 Quick Start

```bash
# Option 1: Just double-click index.html
# That's it. No build step. No install.

# Option 2: Serve locally
python3 -m http.server 8000
# Open http://localhost:8000

# Option 3: Deploy
# Drop the folder on GitHub Pages, Netlify, Vercel, or S3
```

**Requirements:** Any modern browser (Chrome, Firefox, Safari, Edge). JavaScript enabled. That's all.

---

## 📁 Project Structure

```
astronova-cosmic-explorer/
├── index.html              ← The entire app (181 KB, HTML+CSS+JS inline)
├── README.md               ← This file
├── AstroNova_Pitch_Deck.pptx  ← 6-slide pitch deck for judges
├── AstroNova_Pitch_Deck.pdf   ← PDF version of pitch deck
├── slides/                 ← Source HTML for the pitch deck
│   ├── global.css
│   ├── slides_brief.json
│   └── slide_01..06.html
└── images/                 ← 20 AI-generated HD astronomical images (1024×1024)
    ├── hero-galaxy.jpg     ← Hero background (spiral galaxy)
    ├── sun.png             ← Sun (G2V main sequence)
    ├── mercury.png ... neptune.png   ← 8 planets
    ├── pluto.png           ← Pluto (Sputnik Planitia heart)
    ├── moon.png            ← Earth's Moon
    └── sirius.png, betelgeuse.png, rigel.png, polaris.png,
        vega.png, proxima.png, arcturus.png, antares.png   ← 8 stars
```

---

## 🛠️ Tech Stack

| Layer | Choice | Why |
|---|---|---|
| **HTML** | Single `index.html` | Zero install, zero build, runs anywhere |
| **CSS** | Custom + CSS variables | Glass-morphism design system, no Tailwind dependency |
| **JS** | Vanilla ES6+ in an IIFE | No React, no Vue, no jQuery — modern native APIs |
| **Storage** | `localStorage` | Cadet callsign, mission progress, badges — all client-side |
| **Visuals** | Animated canvas starfield | GPU-light, no library |
| **AI** | Curated knowledge base | ARIA runs offline, no API keys, no telemetry |

**No external dependencies. No CDN. No frameworks. No build step.**

---

## 🎮 Mini-Game Controls

All 5 mini-games support both **mouse/touch** and **keyboard**:

| Game | Keyboard | Mouse |
|---|---|---|
| Rocket Launch | `Space` (hold) | Hold THRUST button |
| ISS Docking | `↑ ↓ ← →` | Tap on-screen buttons |
| Lunar Landing | `↑` or `Space` + `← →` | Tap on-screen buttons |
| Mars EDL | `Space` or `Enter` | Click action button |
| EVA Rescue | `↑ ↓ ← →` | Tap D-pad buttons |

---

## 🧪 Educational Foundation

Every mini-game is grounded in real NASA mission parameters:

- **Max-Q throttle management** — SpaceX Falcon 9 throttles to ~70% through Max-Q
- **Hohmann transfer** — most fuel-efficient orbital transfer (Walter Hohmann, 1925)
- **Mach 1.7 parachute deploy** — Perseverance's 21.5 m chute deployed at Mach 1.75
- **Skycrane maneuver** — invented for Curiosity, perfected by Perseverance
- **SAFER jetpack** — worn by every EVA astronaut since 1994
- **Apollo 11 landing** — Neil Armstrong's manual diversion to avoid West Crater

Every briefing answer includes educational feedback citing Apollo, Artemis, Soyuz, Voyager, Hubble, JWST, and Perseverance.

---

## 🖼️ Image Sources

All 20 images are **AI-generated HD astronomical renderings** (1024×1024 each) created using detailed prompts based on real NASA mission imagery:

| Body | Reference Mission | Body | Reference Mission |
|---|---|---|---|
| Sun | SDO | Uranus | Voyager 2 |
| Mercury | MESSENGER | Neptune | Voyager 2 |
| Venus | Magellan | Pluto | New Horizons |
| Earth | Apollo 17 "Blue Marble" | Moon | Lunar Reconnaissance Orbiter |
| Mars | MRO/Perseverance | Stars | Hubble-style telescope photography |
| Jupiter | Juno/Hubble | Galaxy hero | Hubble Deep Field style |
| Saturn | Cassini/Hubble | | |

Each image was verified with a vision-language model to confirm it depicts the correct celestial body before being included.

---

## 📊 By the Numbers

| Stat | Value |
|---|---|
| Total file size | **181 KB** |
| External dependencies | **0** |
| AI-verified HD images | **20+** |
| Offline capable | **100%** |
| Modules | **5** |
| Mission tools | **16** |
| Mini-games | **5** |
| ARIA knowledge entries | **40+** |
| Lines of code | **~3,200** |

---

## 🏆 NASA Space Apps Challenge

This project is submitted for the **NASA Space Apps Challenge 2026** under the following award categories:

- **Best Use of Technology** — innovative single-file architecture with 16 live calculators and 5 interactive mini-games
- **Art & Technology** — AI-generated HD imagery combined with interactive game design
- **Best Use of Storytelling** — Junior Astronaut Trainer narrative across 5 progressive missions

### Submission Checklist

- [x] Project page on spaceappschallenge.org
- [x] Source code (single `index.html`)
- [x] 30-second demo video (English subtitles)
- [x] Project description + SI usage statement
- [x] All sources cited (NASA imagery, facts, formulas)
- [x] Team: **AstroNova** (registered)

---

## 👥 Team

**AstroNova Team** — NASA Space Apps Challenge 2026

---

## 📄 License

Open source — for educational and inspirational use. NASA imagery references are public domain (NASA's open data policy). AI-generated renderings are original to this project.

---

## 🔗 Links

- **Live app:** Run `index.html` locally (offline-ready)
- **NASA Space Apps:** [spaceappschallenge.org](https://www.spaceappschallenge.org)
- **NASA Open Data:** [data.nasa.gov](https://data.nasa.gov)

---

<div align="center">

**ASTRONOVA TEAM · NASA SPACE APPS CHALLENGE 2026 · #SPACEAPPS**

*Built for learners, not for likes. A kid with a Chromebook and no wifi can become a Junior Astronaut.*

</div>
