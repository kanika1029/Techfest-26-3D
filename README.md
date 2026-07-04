# Techfest/26 — Ground Control

A 3D interactive website concept for Techfest, built with **Three.js** and **GSAP ScrollTrigger**.

**Live demo:** https://kanika1029.github.io/Techfest-26-3D/

---

## Concept

Instead of a normal scrolling webpage, the site is framed as a **mission control console**. A persistent HUD overlay (corner brackets, live clock, altitude/velocity/scroll-progress telemetry) stays on screen the whole time, so scrolling feels like piloting a launch rather than reading a page.

The scroll journey:

1. **Hero** — mission briefing / launch pad
2. **Launch** — a 3D rocket (built from Three.js primitives) lifts off as you scroll; camera tracks it, exhaust particles ignite, live telemetry readout ("MAX-Q", "STAGE SEPARATION") updates in real time
3. **About** — camera settles near a rotating wireframe "core" station; stats count up
4. **Tracks** — five event categories orbit the core as **interactive 3D nodes** — drag to rotate the array, click a node to open its mission file (Robotics, AI/ML, Hackathon, Space Tech, Game Arena)
5. **Timeline** — camera drifts in a slow ambient orbit around the station while the 3-day schedule sits in the foreground
6. **Register** — camera goes to warp (FOV stretch + star-streak dolly through the core), a screen-flash transition, then a live countdown to the fest date and a registration CTA

## Tech stack

- **Three.js (r128)** — 3D scene, rocket/core/orb geometry, particle systems, camera control
- **GSAP + ScrollTrigger** — scroll-position tracking that drives camera movement and object states
- **Vanilla JS / CSS** — no framework, single self-contained HTML file
- Custom cursor, loading sequence, and `prefers-reduced-motion` support

## Run it locally

No build step — it's a single HTML file.

```bash
git clone https://github.com/kanika1029/Techfest-26-3D.git
cd Techfest-26-3D
# just open index.html in a browser, or serve it:
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Notes

- All copy (dates, venue, prize pool, participant numbers) is placeholder content — update it with the real fest details.
- The registration button currently shows a placeholder alert — wire it up to the real registration form/link.
- Best viewed on desktop; mobile layout is responsive but the 3D scroll effects are most impressive on larger screens.
