<img width="1899" height="871" alt="Screenshot 2026-08-19 131819" src="https://github.com/user-attachments/assets/f881d87f-e58f-422c-9829-8d01f20fa0d9" /># DEEPCRAFT — 3D Hackathon Landing Page

An interactive, voxel-cave-themed landing page for a 24-hour college hackathon, built as a
navigable 3D scene rather than a traditional scrolling page. Visitors move through a mine/cave
system — each chamber reveals a section of hackathon information — and end their journey at the
End Portal, which opens the registration flow.

**Live demo:** https://raghav-1407.github.io/deepcraft-hackathon-landing/

---

## Overview

Instead of a standard scroll-based landing page, DEEPCRAFT reimagines the "Discover → Understand
→ Get Excited → Register" user journey as a first-person cave exploration. The user (or an
automated camera, on entry) moves between themed chambers — Cave Mouth, Mineshaft, Crafting
Chamber, Lava Pool, Mob Chamber, Deep Dark, Stronghold, and the End Portal — each surfacing a
different piece of event information through an in-world UI panel. A fully accessible 2D fallback
view is included for reduced-motion preferences, low-end devices, and screen readers.

## Features Implemented

- **3D explorable cave scene** built with Three.js, including a world-load screen with progress
  readout before entry
- **Chamber-based information architecture** — each region of the cave maps to a required section:
  - Cave Mouth → Hero / event intro
  - Mineshaft → About the event
  - Crafting Chamber → Timeline
  - Lava Pool → Prize pool
  - Mob Chamber → Judges / mentors
  - Deep Dark → Rules & eligibility
  - Stronghold → Sponsors & FAQs
  - End Portal → Registration
- **In-world chamber panel UI** that surfaces contextual info (stats, chips, key-value rows) as the
  user enters each region
- **Region navigator (hotbar)** for direct/fast-travel navigation between chambers, doubling as a
  progress/section indicator
- **Touch controls** for mobile/tablet navigation alongside desktop WASD + mouse-look
- **Depth readout HUD** (`Y −54 · REGION 01`) reinforcing the mining/exploration theme
- **Registration modal** styled as an in-world dialog, with a confirmation state after submission
- **Accessible standard view** — a complete text/2D fallback of every section for
  `prefers-reduced-motion`, low-end devices, and non-3D navigation, toggleable from the UI
- **Responsive layout** across desktop and mobile viewports, with safe-area handling for notched
  devices

## Technologies & Libraries Used

- **HTML5 / CSS3** — custom properties (CSS variables) for theming, no CSS framework
- **Vanilla JavaScript** — scene logic, state management, UI interactions
- **[Three.js](https://threejs.org/) (r128)** — 3D scene rendering, camera, and cave environment
- **Google Fonts** — Bebas Neue (display), IBM Plex Sans (body), IBM Plex Mono (UI/labels)

No build step or bundler is required — the entire experience runs from a single static HTML file.

## Setup Instructions

This is a static, dependency-free project — no `npm install` required.

1. Clone the repository
   ```bash
   git clone https://github.com/<your-username>/deepcraft-hackathon-landing.git
   cd deepcraft-hackathon-landing
   ```
2. Open `index.html` directly in a browser, **or** serve it locally (recommended, avoids
   file:// CORS issues with some assets):
   ```bash
   # using Python
   python3 -m http.server 8000

   # or using Node
   npx serve .
   ```
3. Visit `http://localhost:8000` in your browser.

## Project Structure

```
deepcraft-hackathon-landing/
├── index.html          # Entire application: markup, styles, and scene/UI logic
├── screenshots/         # Images used in this README
├── .gitignore
└── README.md
```

> The project is intentionally kept as a single self-contained file for this build. In a larger
> production version, the 3D scene logic, UI components, and styles would be split into separate
> modules (see "Future Improvements" below).

## Screenshots

| Cave Entrance | Chamber Panel | End Portal / Registration |
| [Cave entrance](<img width="1899" height="871" alt="Screenshot 2026-08-19 131819" src="https://github.com/user-attachments/assets/64efafd5-fd8b-4b1a-83bd-ba18668faf49" />)
| [Chamber panel](<img width="615" height="89" alt="Screenshot 2026-08-19 131944" src="https://github.com/user-attachments/assets/7699f36c-4a4b-46a5-805c-64ce254333ef" />) 
| [End portal](<img width="1897" height="855" alt="Screenshot 2026-08-19 131925" src="https://github.com/user-attachments/assets/12c9ee65-69d9-4896-99f9-190d4d7cbe89" />) |

## Future Improvements

- Split into modular components (React Three Fiber) for better maintainability
- Add physics-based collision for more natural movement through the cave
- Persist registration submissions to a backend/database instead of local state

## Deployment

Deployed on: **[GitHub Pages]** — https://raghav-1407.github.io/deepcraft-hackathon-landing/

---

Built for [CSI WEB TASK] as a frontend & UI/UX evaluation submission.
