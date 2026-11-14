🚀 AstroNova Cosmic Explorer
A single-file, offline-first cosmos in your browser. Built for the NASA Space Apps Challenge 2026.

NASA Space AppsNo BackendNASA APIsOffline-FirstFile Size

What if the entire cosmos fit inside a single HTML file?

🎯 The Pitch
AstroNova Cosmic Explorer is one self-contained index.html — 216 KB, no install, no signup, no backend, no build step. Double-click the file in any modern browser to run the full offline core (solar system, star catalog, 16 calculators, 5 mini-game trainer, ARIA assistant). When an internet connection is available, live NASA data widgets activate automatically — pulling real imagery and data from four NASA open APIs (APOD, Mars Rover Photos, NASA Image Library, NeoWs).

Built in under 48 hours for the NASA Space Apps Challenge.

✨ Features
1. 🪐 Solar System Explorer
11 bodies in HD — the Sun, all 8 planets, Pluto, and Earth's Moon. Click any body to open a glass-morphism datasheet with real NASA-sourced facts: diameter, mass, gravity, orbital period, moons, temperature, discovery year.

2. 📡 Live NASA Data Widgets
Real-time integration with four NASA open APIs, fetched client-side via fetch():

Widget	NASA API	What it shows
🔭 Astronomy Picture of the Day	api.nasa.gov/planetary/apod	Today's official NASA APOD — image/video, title, copyright, explanation
🚀 Mars Rover Photos	api.nasa.gov/mars-photos/api/v1/rovers/	Curiosity / Perseverance / Opportunity / Spirit images by sol; auto-clamps sol to rover's max_sol
🖼️ NASA Image & Video Library	images-api.nasa.gov	Keyless search of NASA's full image archive (100 results per query)
☄️ Near-Earth Object Tracker	api.nasa.gov/neo/rest/v1/feed/today	Live CNEOS asteroid data — count, diameters, velocities, miss distances, hazardous flags
Resilience built in:

If APOD is rate-limited → falls back to NASA Image Library (keyless) for a real astronomy image
If Mars Rover endpoint is down → falls back to NASA Image Library for real Mars surface photos
All thumbnails render in uniform 1:1 aspect-ratio grids with skeleton shimmer loaders, fade-in on load, and graceful "image unavailable" fallbacks
API errors surface a clear message with a link to get a free NASA key
3. ⭐ Star Catalog
8 scientifically notable stars — Sirius, Betelgeuse, Rigel, Polaris, Vega, Proxima Centauri, Arcturus, and Antares. Each entry includes spectral type, surface temperature, distance in light-years, luminosity, and a narrative on why it matters.

4. 🧮 16 Mission Tools
Practical spaceflight calculators that run live in the browser:

#	Tool	#	Tool
1	Light-speed Comm Delay	9	Cosmic Distance Converter
2	Weight on Other Worlds	10	Synchronous Orbit Altitude
3	Orbital Velocity & Period	11	Tsiolkovsky Rocket Equation
4	Mission Elapsed Time	12	Habitable Zone Calculator
5	Delta-V Budget Estimator	13	Solar Panel Power
6	Radiation Dose Estimator	14	Schwarzschild Radius (Black Hole)
7	Hohmann Transfer	15	Relativistic Time Dilation
8	Escape Velocity	16	Cosmic Velocities
Every tool uses real physics formulas with real constants. Inputs update results instantly — no submit button, no page reload.

5. 🎓 Junior Astronaut Mission Trainer
5 progressive missions — each opens with a themed mini-game, then unlocks a 4-step decision briefing:

Mission	Difficulty	Mini-Game	Badge
🚀 Rocket Launch Sequence	Beginner	Hold THRUST, manage heat through Max-Q, reach 100 km orbit	Launch Specialist
🛰️ ISS Rendezvous & Docking	Intermediate	Thrust/Brake/Align — soft-dock at < 0.2 m/s	Rendezvous Specialist
🌙 Artemis Lunar Landing	Advanced	Tap thrust, dodge boulders, soft-land < 3 m/s	Lunar Lander
🔴 Mars EDL — 7 Minutes of Terror	Expert	Time 4 EDL actions at the right altitude	Mars EDL Specialist
🚷 EVA Emergency Response	Advanced	Fly a SAFER jetpack, rescue crewmate in 60s	EVA Emergency Specialist
Pass one mission to unlock the next. Complete all 5 to earn Junior Astronaut Certification. Progress saved in localStorage.

6. 🤖 ARIA — Built-in Offline AI Assistant
A knowledge engine that runs entirely in your browser — no API keys, no external LLM calls, no telemetry.

40+ curated entries: solar system, stars, NASA missions, astrophysics, the app itself
Topic classifier rejects off-topic questions
Keyword matcher picks the best answer
Toggle with Ctrl+Shift+A or click the floating button
🚀 Quick Start
# Option 1: Just double-click index.html# That's it. No build step. No install.# Option 2: Serve locallypython3 -m http.server 8000# Open http://localhost:8000# Option 3: Deploy# Drop the folder on GitHub Pages, Netlify, Vercel, or S3
Requirements: Any modern browser (Chrome, Firefox, Safari, Edge). JavaScript enabled. The offline core runs with no network; live NASA widgets activate when online.

📁 Project Structure
astronova-cosmic-explorer/├── index.html              ← The entire app (216 KB, ~4,200 lines, HTML+CSS+JS inline)├── README.md               ← This file├── AstroNova_Pitch_Deck.pptx  ← 6-slide pitch deck for judges├── AstroNova_Pitch_Deck.pdf   ← PDF version of pitch deck├── slides/                 ← Source HTML for the pitch deck│   ├── global.css│   ├── slides_brief.json│   └── slide_01..06.html└── images/                 ← 20 AI-generated HD astronomical images (1024×1024)    ├── hero-galaxy.jpg     ← Hero background (spiral galaxy)    ├── sun.png             ← Sun (G2V main sequence)    ├── mercury.png ... neptune.png   ← 8 planets    ├── pluto.png           ← Pluto (Sputnik Planitia heart)    ├── moon.png            ← Earth's Moon    └── sirius.png, betelgeuse.png, rigel.png, polaris.png,        vega.png, proxima.png, arcturus.png, antares.png   ← 8 stars
🛠️ Tech Stack
Layer	Choice	Why
HTML	Single index.html	Zero install, zero build, runs anywhere
CSS	Custom + CSS variables	Glass-morphism design system, no Tailwind dependency
JS	Vanilla ES6+ in an IIFE	No React, no Vue, no jQuery — modern native APIs
NASA APIs	APOD, Mars Rover Photos, Image Library, NeoWs	Live astronomical data via client-side fetch(); graceful fallback on failure
Storage	localStorage	Cadet callsign, mission progress, badges — all client-side
Visuals	Animated canvas starfield	GPU-light, no library
AI	Curated knowledge base	ARIA runs offline, no API keys, no telemetry
No frameworks. No CDNs. No build step. No backend. The core experience is fully offline; live NASA data is an enhancement layer that degrades gracefully when unavailable.

🔌 NASA API Integration
AstroNova uses four NASA open-data REST APIs for its live widgets. All calls are made client-side from the browser using the native fetch() API.

// Example: APOD endpointconst url = `https://api.nasa.gov/planetary/apod?api_key=${DEMO_KEY}&date=${todayStr()}`;const d = await fetch(url).then(r => r.json());
Endpoint	Auth	Rate Limit	Used For
api.nasa.gov/planetary/apod	DEMO_KEY / registered key	10/hr (demo) — 1,000/hr (registered)	Astronomy Picture of the Day
api.nasa.gov/mars-photos/api/v1/rovers/	DEMO_KEY / registered key	same	Mars rover photos by sol
images-api.nasa.gov/search	None (keyless)	No limit	NASA Image Library search + fallback imagery
api.nasa.gov/neo/rest/v1/feed/today	DEMO_KEY / registered key	same	Near-Earth Object (asteroid) tracking
About API keys: The project ships with NASA's public DEMO_KEY for ease of demo. For production traffic, replace it with a free registered key from api.nasa.gov (1,000 requests/hour). A key is not required for the NASA Image Library endpoint, which serves as a keyless fallback for APOD and Mars when those APIs are unavailable.

🎮 Mini-Game Controls
All 5 mini-games support both mouse/touch and keyboard:

Game	Keyboard	Mouse
Rocket Launch	Space (hold)	Hold THRUST button
ISS Docking	↑ ↓ ← →	Tap on-screen buttons
Lunar Landing	↑ or Space + ← →	Tap on-screen buttons
Mars EDL	Space or Enter	Click action button
EVA Rescue	↑ ↓ ← →	Tap D-pad buttons
🧪 Educational Foundation
Every mini-game is grounded in real NASA mission parameters:

Max-Q throttle management — SpaceX Falcon 9 throttles to ~70% through Max-Q
Hohmann transfer — most fuel-efficient orbital transfer (Walter Hohmann, 1925)
Mach 1.7 parachute deploy — Perseverance's 21.5 m chute deployed at Mach 1.75
Skycrane maneuver — invented for Curiosity, perfected by Perseverance
SAFER jetpack — worn by every EVA astronaut since 1994
Apollo 11 landing — Neil Armstrong's manual diversion to avoid West Crater
Every briefing answer includes educational feedback citing Apollo, Artemis, Soyuz, Voyager, Hubble, JWST, and Perseverance.

🖼️ Image Sources
The Solar System Explorer and Star Catalog use 20 AI-generated HD astronomical renderings (1024×1024 each) created using detailed prompts based on real NASA mission imagery:

Body	Reference Mission	Body	Reference Mission
Sun	SDO	Uranus	Voyager 2
Mercury	MESSENGER	Neptune	Voyager 2
Venus	Magellan	Pluto	New Horizons
Earth	Apollo 17 "Blue Marble"	Moon	Lunar Reconnaissance Orbiter
Mars	MRO/Perseverance	Stars	Hubble-style telescope photography
Jupiter	Juno/Hubble	Galaxy hero	Hubble Deep Field style
Saturn	Cassini/Hubble		
Each image was verified with a vision-language model to confirm it depicts the correct celestial body before being included.

The Live NASA Data widgets pull real imagery directly from NASA's servers at runtime — APOD photos, Mars rover camera frames, and NASA Image Library search results are not bundled with the app; they are fetched live.

📊 By the Numbers
Stat	Value
Total file size	216 KB
Lines of code	~4,200
NASA APIs integrated	4 (APOD, Mars Rover, Image Library, NeoWs)
External JS dependencies	0
AI-verified HD images (bundled)	20+
Modules	6
Mission tools	16
Mini-games	5
ARIA knowledge entries	40+
Offline capability	Core runs 100% offline · live widgets need network
🏆 NASA Space Apps Challenge
This project is submitted for the NASA Space Apps Challenge 2026 under the following award categories:

Best Use of Technology — single-file architecture combining 16 live calculators, 5 interactive mini-games, and 4 live NASA open-data APIs with graceful degradation
Art & Technology — AI-generated HD imagery combined with interactive game design and live NASA data widgets
Best Use of Storytelling — Junior Astronaut Trainer narrative across 5 progressive missions
Submission Checklist
 Project page on spaceappschallenge.org
 Source code (single index.html)
 30-second demo video (English subtitles)
 Project description + SI usage statement
 All sources cited (NASA imagery, facts, formulas, APIs)
 Team: AstroNova (registered)
NASA Data Resources Used
For Global Award eligibility, this project uses the following NASA open data resources via their public REST APIs:

NASA Astronomy Picture of the Day (APOD) API — https://api.nasa.gov/planetary/apod
NASA Mars Rover Photos API — https://api.nasa.gov/mars-photos/api/v1/rovers/
NASA Image and Video Library API — https://images-api.nasa.gov
NASA NeoWs (Near Earth Object Web Service) API — https://api.nasa.gov/neo/rest/v1
No API key is needed beyond NASA's public DEMO_KEY; the NASA Image Library endpoint is fully keyless.

👥 Team
AstroNova Team — NASA Space Apps Challenge 2026

Pratham Raj (Team Owner)
Manoj Kumar
Avesh Kumar
Sanjay Kumar
📄 License
Open source — for educational and inspirational use. NASA imagery references are public domain (NASA's open data policy). NASA open-data APIs are used under NASA's public API terms. AI-generated renderings are original to this project.

🔗 Links
Live app: Run index.html locally (offline core; live widgets when online)
NASA Space Apps: spaceappschallenge.org
NASA Open Data: data.nasa.gov
NASA APIs (get a free key): api.nasa.gov
ASTRONOVA TEAM · NASA SPACE APPS CHALLENGE 2026 · #SPACEAPPS

Built for learners, not for likes. A kid with a Chromebook can explore the solar system offline — and pull live Mars rover photos when online.
