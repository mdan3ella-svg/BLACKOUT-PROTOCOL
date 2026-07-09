# VERTASCAN // BLACKOUT PROTOCOL

**AGV-Sentinel Alpha — anti-gravity covert strike**

A AAA-styled single-file stealth shooter for the browser. Pilot the AGV-Sentinel Alpha anti-grav drone through a five-mission infiltration of Site NADIR — a blacksite that does not exist on any map — while MRV-class "MANTA" interceptors hunt you through storm-soaked canyons, a top-secret hangar, a 240-meter ventilation shaft, and the gravity-well reactor at the bottom of it all.

**► PLAY:** `https://mdan3ella-svg.github.io/<REPO-NAME>/`

No install. No build step. One HTML file, two GLB assets, and a browser.

---

## Features

- **Full stealth AI** — four ORB hostile classes (WATCHER / HUNTER / WARDEN / HIVE) with suspicion states, line-of-sight raycasts, detection cones, patrol routes, and a global awareness grid that escalates from GHOST to LOCKDOWN
- **MRV "MANTA" hostiles** — enemies fly the `mantaray-XHD.glb` airframe at ~2× the Sentinel's wingspan, with code-driven hover bob and bank-into-turn flight language, per-type emissive tinting, and hull-accurate hit radii
- **Five-mission campaign** — Perimeter Breach → Blacksite Hangar (fly *into* the bay doors) → The Shaft → Reactor Gallery → Exfiltration (timed, bulkheads sealing behind you)
- **Blacksite structure kit** — enterable hangar with glowing bay aperture, landing pads, comm domes, rotating radar dishes, antenna masts, guard searchtowers, cargo yards
- **Five flight behaviors** — glide, SURGE (loud), cloak field, NULL-DROP freefall, and precision hover
- **Arsenal** — silent Ion Lance, loud Pulse Repeater, chargeable Rail Lance, EMP burst (breaches Warden shields)
- **AAA post pipeline** — EffectComposer with UnrealBloom, SSAO, SSR, NV-optic color grade, LIDAR wireframe sensor overlay
- **Procedural WebAudio** — full synthesized SFX and an ominous score that engages automatically if no soundtrack file is present
- **Desktop + mobile** — keyboard/mouse, or two touch schemes (see below)

## Controls

### Desktop

| Input | Action |
|---|---|
| Mouse | Aim / attitude |
| W A S D | Vector thrust |
| SPACE / X | Ascend / descend |
| SHIFT | SURGE (loud) |
| C | Cloak field |
| F (hold) | NULL-DROP freefall |
| LMB | Fire · 1 / 2 weapon select |
| RMB (hold) | Rail Lance charge |
| E | EMP burst |
| P / ESC | Pause |

### Mobile — two controller options

Switch schemes with the **Controls** button on the title screen or pause menu.

**Touch Pads** — an analog thrust stick appears wherever your left thumb lands; drag the right side of the screen to aim. On-screen FIRE, RAIL (hold-charge), ASC/DSC altitude, WPN, CLK, EMP, and SRG buttons.

**Tilt-to-Fly** — tilt the device to steer: roll left/right to turn, pitch forward/back to dive and climb. Hold THRUST to fly, **tap anywhere to fire, flick upward for an instant Rail Lance snap**. CAL re-zeros the neutral grip angle (also auto-calibrates on every deploy). iOS will prompt for motion-sensor permission the first time you select this scheme.

Touch devices default to the PERFORMANCE render profile; bump to HIGH/ULTRA from the pause menu.

## Deployment

The build is a single self-contained HTML file. Assets are referenced by filename and co-deployed beside it:

| File | Required | Purpose |
|---|---|---|
| `index.html` | ✔ | The entire game |
| `blue.glb` | ✔ | AGV-Sentinel Alpha player drone |
| `mantaray-XHD.glb` | optional | MRV MANTA hostile airframe (procedural orb fallback if absent) |
| `blackoutprotocol.mp3` | optional | Soundtrack (procedural synth score if absent) |
| `blackoutprotocol.jpg` | optional | Boot key art |

To deploy on GitHub Pages: push these files to the repo root, then **Settings → Pages → Deploy from branch → main / root**.

## Tech

- [Three.js](https://threejs.org/) (r160+, ES modules via import map / CDN)
- GLTFLoader, RoomEnvironment IBL, EffectComposer + UnrealBloomPass + SSAOPass + SSRPass + custom ShaderPasses
- Procedural WebAudio SFX + adaptive tension scoring
- Pointer Events touch layer + DeviceOrientation tilt controls
- Zero dependencies to install, zero build tooling

## Render profiles

| Profile | Pixel ratio | SSAO | SSR | Shadows |
|---|---|---|---|---|
| PERFORMANCE | 1.0 | — | — | — |
| HIGH | 1.5 | ✔ | — | ✔ |
| ULTRA | 2.0 | — | ✔ | ✔ |

## License

Source code is released under the **MIT License** (see [`LICENSE`](LICENSE)).

**Excluded from the MIT grant:** the VERTASCAN name, logo, and brand identity, and all bundled art/audio assets (`blue.glb`, `mantaray-XHD.glb`, `blackoutprotocol.mp3`, `blackoutprotocol.jpg`). These remain **© VERTASCAN, all rights reserved** and may not be redistributed or reused outside this project without permission.

---

<p align="center"><sub>VERTASCAN // BLACKOUT PROTOCOL · built with Three.js · © 2026 VERTASCAN</sub></p>
