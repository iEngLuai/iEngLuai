# Luai Al Ibrahim

**Reliability Engineer | RCM & FMEA | CMRP** · MSc Maintenance and Reliability Engineering, KFUPM

I build AI tools for maintenance and reliability of rotating equipment, with a focus on refinery and gas-plant pumps.

Below are **two separate projects**, both carried out as part of my **MSc in Maintenance and Reliability Engineering at KFUPM**. They share one idea: turn vibration and process data into decisions a maintenance team can act on.

| | Project | In plain words | Status | Link |
|---|---|---|---|---|
| 1 | **RotatingSense** | A "control room" for a whole plant. It shows which pumps are healthy and which need maintenance first, and why. | **Under development** | [Open RotatingSense](https://rotatingsense.onrender.com) (sign-in required) |
| 2 | **V0 (PumpGuard AI v6.1)** | An AI that reads a pump's vibration, spots a developing fault, estimates how long it can keep running, and recommends the maintenance action. | Complete, public demo | [Open V0](https://portly-chi.vercel.app) (no sign-in) |

---

## 1. RotatingSense: plant-level predictive maintenance

> **Status: under development.** Features, screens and data change often. MSc in Maintenance and Reliability Engineering, KFUPM.

**[Open RotatingSense](https://rotatingsense.onrender.com)**: live demo (sign-in required; message me for a demo account).

**In plain words:** instead of looking at one pump, you see the whole plant and what to fix first. A separate project that applies the V0 pump models (project 2 below) at plant level. It follows the way a plant is organised: **plant → unit → pump**.

<p align="center"><img src="assets/rotatingsense-plant.png" alt="RotatingSense plant overview: two units, ten pumps, five health states" width="100%"></p>

- **Plant overview:** live process map, pumps running against pumps needed, flow against demand, and a ranked "needs attention" list.
- **Unit page:** live P&ID of the pump train with each pump's health state, flow, vibration and bearing temperature.
- **Pump page:** 3D model with sensor readings, trends, diagnosis, RCA, FMEA and RCM.
- **Five health states, one palette:** Healthy, Monitor, Degraded, Advanced, Near failure. They look the same on every page.
- **Alarms come from measured values only (ISA-18.2).** The AI explains and recommends on request; it never raises an alarm.
- **Reliability analytics:** Weibull, MTBF, MTTR, availability, bad actors, PM compliance.
- **Failure stories:** 11 researched pump failure scenarios (cavitation, seal flush, misalignment and others) that change the process readings.
- **Same results as V0:** the PumpGuard v6.1 models are unchanged, checked by a parity test (55 cases, 0 differences).
- **Quality:** 185 automated tests plus a screen audit at phone, tablet and desktop sizes.

All plant data is **simulated**. Built with FastAPI, Supabase Postgres, React, Vite and react-three-fiber.

<p align="center"><img src="assets/rotatingsense-unit.png" alt="RotatingSense unit page: live P&ID of a six-pump crude shipper unit" width="100%"></p>

---

## 2. V0 (PumpGuard AI v6.1): AI pipeline for pump health

**[Open V0](https://portly-chi.vercel.app)**: public demo, no sign-in.

> **How to test the model:** click the **settings icon** (gear, top right of the page) and switch on **Show demo scenario buttons**. Then pick a preset scenario card and press **Run Analysis**. You can also upload your own vibration file.

<p align="center"><img src="assets/v0-settings.png" alt="V0 dashboard settings: switch on Show demo scenario buttons" width="360"></p>

**In plain words:** pumps shake in a specific way before they fail. This AI listens to that vibration and warns early. A separate project: my MSc course project (ISE 619, Maintenance and Reliability Engineering, KFUPM). A three-stage machine-learning pipeline for centrifugal pumps.

<p align="center"><img src="assets/v0-pumpguard.png" alt="PumpGuard AI v6.1: AI pipeline flow and 3D vibration sensor map" width="100%"></p>

- **Anomaly detection** (Isolation Forest), then **fault classification** (XGBoost: normal, misalignment, unbalance, cavitation, coupling failure).
- **Remaining useful life** (LSTM) from run-to-failure bearing data.
- **RCM decision:** the result is turned into a maintenance recommendation, not only a score.
- **3D sensor map** coloured by ISO 10816 vibration zones.
- Trained on public datasets (NLN-EMP and XJTU-SY). It is an academic proof of concept, designed to be retrained on a plant's own data.

---

### Contact
Reliability Engineer, Saudi Arabia · CMRP · RCM · FMEA
