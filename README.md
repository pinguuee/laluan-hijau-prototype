# Laluan Hijau 🚑🟢

**AI traffic lights and driver alerts that clear the road for every ambulance.**

Prototype by **Team Bikai** (UiTM Shah Alam) for the **Sime Darby Property University Hackathon 2026: Township of Tomorrow**.

> *No one should die waiting at a red light.*

---

## The problem

- Only **34.1%** of Priority 1 emergencies in Malaysia got an ambulance within 15 minutes in 2025, against the Health Ministry's 50% target.
- Without CPR or defibrillation, cardiac-arrest survival drops **7–10% for every minute** of delay.
- At every red light, ambulance crews face a dilemma: **wait** and lose minutes, or **run the red** and risk a crash they are personally liable for.
- Drivers ahead often can't hear the siren and don't know where to move.

## Our solution

Laluan Hijau has two layers:

| Layer | What it does |
|---|---|
| **1. Smart signal preemption** | AI predicts when the ambulance will reach each junction and turns the light green **30–60 s early**, so the queue has cleared before it arrives. Crossing traffic is held red, and the normal cycle resumes once the ambulance passes. |
| **2. Alerts for drivers ahead** | Drivers in the ambulance's path get an in-app countdown alert with a clear instruction: *move left, slow down, don't run the red.* Roadside LED signs reach drivers who don't have the app. |

**Lights clear the junctions. Alerts clear the road between them.**

## About this prototype

This repository contains an interactive **control-room simulation**. The same ambulance makes the same trip through the same traffic twice, side by side:

- **Today (siren only):** the ambulance stops at red lights and gets stuck behind drivers who notice the siren late.
- **With Laluan Hijau:** junctions turn green early and every driver ahead is alerted in advance.

### Features

- **Live two-lane corridor:** 6 signalised junctions from City of Elmina to the hospital (illustrative route).
- **Realistic traffic:** every vehicle obeys signals and keeps its distance. When the ambulance approaches, each driver either **moves left**, **pulls onto the shoulder**, or **drives forward** to make room.
- **Driver phone view:** a live alert with a countdown and step-by-step instructions.
- **Roadside LED sign:** shows "AMBULANCE · KEEP LEFT" while a junction is held green.
- **AI junction planner:** distance, ETA, queue length and the preemption window for each junction.
- **Event log:** every request is timestamped, ready for reporting to MOH and the council.
- **Network outage toggle:** demonstrates the fail-safe. Junctions return to their normal cycle and nothing is stuck on green.
- **Results summary:** time recovered, red-light stops avoided and drivers alerted.

### How to run

No installation needed. It is a single HTML file.

1. Download or clone this repository.
2. Open `index.html` in any modern browser (Chrome, Edge, Firefox or Safari).

Or view it online through GitHub Pages: *[add your Pages link here]*

### Controls

| Control | Action |
|---|---|
| **Restart P1 run** | Replays the emergency run from the start |
| **Pause / Resume** | Freezes the simulation |
| **New traffic scenario** | Generates new traffic and signal timings |
| **1× / 4× / 8×** | Simulation speed |
| **Simulate network outage** | Tests the fail-safe behaviour |

## How it works (end to end)

1. **Dispatch:** a P1 call is assigned and the crew sets "Emergency active". Only verified vehicles can request priority.
2. **Track:** live GPS position and route stream to the control platform over 4G/5G.
3. **Predict:** the AI estimates arrival time at each junction from speed and queue length.
4. **Preempt:** 30–60 s ahead, the controller runs amber, then all-red, then green for the ambulance's approach.
5. **Alert:** drivers ahead get a countdown alert, and LED signs show "Ambulance: keep left".
6. **Restore and log:** the normal cycle resumes and every run records the time saved.

**Fail-safe:** if the connection drops, the junction returns to its normal cycle. The controller's conflict monitoring is never bypassed.

## Tech stack

- HTML, CSS and vanilla JavaScript (no frameworks, no build step)
- HTML5 Canvas for the traffic simulation
- Seeded random generator so each scenario can be replayed fairly for both runs

## Disclaimer

This is a **prototype simulation**. Corridor length, signal timings, traffic volumes and driver behaviour are **illustrative assumptions**, not measured data from City of Elmina. In Phase 0 of the rollout, they would be replaced with real measurements.

## Team Bikai: Universiti Teknologi MARA (UiTM) Shah Alam

- Alif Harith bin Kamarudin *(Team Leader)*
- Muhammad Nawfal bin Norazam
- Mohamad Irfan Mirza bin Mohamad Madani
- Khairin Azqi bin Zahurim
- Muhammad Aqil bin Syafrul Yamani

## Sources

- Health Ministry statement in Dewan Rakyat, 12 Oct 2026 (Bernama, The Vibes): ambulance response figures
- American Heart Association: survival decline per minute without CPR
- USDOT, *Traffic Signal Preemption for Emergency Vehicles* (2006)
- FHWA Emergency Vehicle Preemption fact sheet (FHWA-HOP-24-019)
- HAAS Alert Safety Cloud: digital driver alerts# Laluan Hijau 🚑🟢

**AI traffic lights and driver alerts that clear the road for every ambulance.**

Prototype by **Team Bikai** (UiTM Shah Alam) for the **Sime Darby Property University Hackathon 2026: Township of Tomorrow**.

> *No one should die waiting at a red light.*

---

## The problem

- Only **34.1%** of Priority 1 emergencies in Malaysia got an ambulance within 15 minutes in 2025, against the Health Ministry's 50% target.
- Without CPR or defibrillation, cardiac-arrest survival drops **7–10% for every minute** of delay.
- At every red light, ambulance crews face a dilemma: **wait** and lose minutes, or **run the red** and risk a crash they are personally liable for.
- Drivers ahead often can't hear the siren and don't know where to move.

## Our solution

Laluan Hijau has two layers:

| Layer | What it does |
|---|---|
| **1. Smart signal preemption** | AI predicts when the ambulance will reach each junction and turns the light green **30–60 s early**, so the queue has cleared before it arrives. Crossing traffic is held red, and the normal cycle resumes once the ambulance passes. |
| **2. Alerts for drivers ahead** | Drivers in the ambulance's path get an in-app countdown alert with a clear instruction: *move left, slow down, don't run the red.* Roadside LED signs reach drivers who don't have the app. |

**Lights clear the junctions. Alerts clear the road between them.**

## About this prototype

This repository contains an interactive **control-room simulation**. The same ambulance makes the same trip through the same traffic twice, side by side:

- **Today (siren only):** the ambulance stops at red lights and gets stuck behind drivers who notice the siren late.
- **With Laluan Hijau:** junctions turn green early and every driver ahead is alerted in advance.

### Features

- **Live two-lane corridor:** 6 signalised junctions from City of Elmina to the hospital (illustrative route).
- **Realistic traffic:** every vehicle obeys signals and keeps its distance. When the ambulance approaches, each driver either **moves left**, **pulls onto the shoulder**, or **drives forward** to make room.
- **Driver phone view:** a live alert with a countdown and step-by-step instructions.
- **Roadside LED sign:** shows "AMBULANCE · KEEP LEFT" while a junction is held green.
- **AI junction planner:** distance, ETA, queue length and the preemption window for each junction.
- **Event log:** every request is timestamped, ready for reporting to MOH and the council.
- **Network outage toggle:** demonstrates the fail-safe. Junctions return to their normal cycle and nothing is stuck on green.
- **Results summary:** time recovered, red-light stops avoided and drivers alerted.

### How to run

No installation needed. It is a single HTML file.

1. Download or clone this repository.
2. Open `index.html` in any modern browser (Chrome, Edge, Firefox or Safari).

Or view it online through GitHub Pages: *[add your Pages link here]*

### Controls

| Control | Action |
|---|---|
| **Restart P1 run** | Replays the emergency run from the start |
| **Pause / Resume** | Freezes the simulation |
| **New traffic scenario** | Generates new traffic and signal timings |
| **1× / 4× / 8×** | Simulation speed |
| **Simulate network outage** | Tests the fail-safe behaviour |

## How it works (end to end)

1. **Dispatch:** a P1 call is assigned and the crew sets "Emergency active". Only verified vehicles can request priority.
2. **Track:** live GPS position and route stream to the control platform over 4G/5G.
3. **Predict:** the AI estimates arrival time at each junction from speed and queue length.
4. **Preempt:** 30–60 s ahead, the controller runs amber, then all-red, then green for the ambulance's approach.
5. **Alert:** drivers ahead get a countdown alert, and LED signs show "Ambulance: keep left".
6. **Restore and log:** the normal cycle resumes and every run records the time saved.

**Fail-safe:** if the connection drops, the junction returns to its normal cycle. The controller's conflict monitoring is never bypassed.

## Tech stack

- HTML, CSS and vanilla JavaScript (no frameworks, no build step)
- HTML5 Canvas for the traffic simulation
- Seeded random generator so each scenario can be replayed fairly for both runs

## Disclaimer

This is a **prototype simulation**. Corridor length, signal timings, traffic volumes and driver behaviour are **illustrative assumptions**, not measured data from City of Elmina. In Phase 0 of the rollout, they would be replaced with real measurements.

## Team Bikai: Universiti Teknologi MARA (UiTM) Shah Alam

- Alif Harith bin Kamarudin *(Team Leader)*
- Muhammad Nawfal bin Norazam
- Mohamad Irfan Mirza bin Mohamad Madani
- Khairin Azqi bin Zahurim
- Muhammad Aqil bin Syafrul Yamani

## Sources

- Health Ministry statement in Dewan Rakyat, 12 Oct 2026 (Bernama, The Vibes): ambulance response figures
- American Heart Association: survival decline per minute without CPR
- USDOT, *Traffic Signal Preemption for Emergency Vehicles* (2006)
- FHWA Emergency Vehicle Preemption fact sheet (FHWA-HOP-24-019)
- HAAS Alert Safety Cloud: digital driver alerts
