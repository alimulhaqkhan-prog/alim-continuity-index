<div align="center">

```
 ██╗      █████╗ ███╗   ███╗██████╗ ██████╗  █████╗
 ██║     ██╔══██╗████╗ ████║██╔══██╗██╔══██╗██╔══██╗
 ██║     ███████║██╔████╔██║██████╔╝██║  ██║███████║
 ██║     ██╔══██║██║╚██╔╝██║██╔══██╗██║  ██║██╔══██║
 ███████╗██║  ██║██║ ╚═╝ ██║██████╔╝██████╔╝██║  ██║
 ╚══════╝╚═╝  ╚═╝╚═╝     ╚═╝╚═════╝ ╚═════╝ ╚═╝  ╚═╝
```

# Alim-Continuity Index — Λ(t)

### *Runtime Continuity Monitoring and Silent Alarm Architecture*
### *for Memory-Bearing Autonomous AI Systems*

<br>

[![Version](https://img.shields.io/badge/Version-V_2.0-06d6f5?style=flat-square&logo=github&logoColor=white)](https://doi.org/10.5281/zenodo.19940908)
[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.19940908-a855f7?style=flat-square&logo=zenodo&logoColor=white)](https://doi.org/10.5281/zenodo.19940908)
[![Live Demo](https://img.shields.io/badge/Live_Demo-ONLINE-10d982?style=flat-square&logo=github-pages&logoColor=white)](https://alimulhaqkhan-prog.github.io/alim-continuity-index/)
[![License](https://img.shields.io/badge/License-All_Rights_Reserved-f43f5e?style=flat-square)](https://github.com/alimulhaqkhan-prog/alim-continuity-index)
[![Patent](https://img.shields.io/badge/Patent-GB2518804.6-f5c518?style=flat-square)](https://github.com/alimulhaqkhan-prog/alim-continuity-index)
[![Stage](https://img.shields.io/badge/Stage-Simulation_Prototype-f97316?style=flat-square)](https://github.com/alimulhaqkhan-prog/alim-continuity-index)

<br>

[🌐 **Live Demo**](https://alimulhaqkhan-prog.github.io/alim-continuity-index/) · [📄 **Research Archive**](https://doi.org/10.5281/zenodo.19940908) · [👤 **Author**](#-author) · [📐 **Theory**](#-formal-properties)

</div>

---

## 🧠 What Is This?

Most AI safety frameworks evaluate what a system **outputs**.  
The **Alim-Continuity Index (Λ)** evaluates whether a memory-bearing autonomous system **remains internally coherent** over time.

**Λ(t)** is a bounded scalar metric that monitors the **continuity health** of AI systems by measuring resonance between **Temporal Memory (TM)** and **Bold Memory (BM)** anchors, penalised by local instability **σ(t)** and angular drift **Δφ(t)**.

> *"Alarm is not pain.*  
> *A machine does not need synthetic suffering to protect itself.*  
> *It needs a measurable signal of continuity degradation."*

This repository contains a **simulation-stage research prototype** — an interactive HTML lab that visualises Λ(t), Silent Alarm thresholding, and continuity-health monitoring in real time.

---

## 📐 Core Equation

> **Λ(t) = R(TM, BM) · exp( −( α·σ(t) + β·Δφ(t) ) )**

| Symbol | Meaning |
|:---:|---|
| **Λ(t)** | Alim-Continuity Index — bounded continuity-health metric, Λ(t) ∈ [0, 1] |
| **R(TM, BM)** | TM–BM resonance — cosine similarity between current semantic state and safe-operation anchors |
| **σ(t)** | Local instability / uncertainty — embedding variance + low-similarity penalty |
| **Δφ(t)** | Angular drift — change in direction of the semantic trajectory (not just distance) |
| **α, β** | Positive sensitivity coefficients (default: α = β = 1.0) |
| **Λc** | Critical threshold — crossing triggers the Silent Alarm |
| **A(t)** | Alarm potential — **A(t) = 1 − Λ(t)** |

> **Key design insight:** Unlike static cosine-similarity monitoring, **Δφ(t)** captures *directional deviation* of the semantic trajectory — anomalies that do not substantially reduce resonance but represent trajectory reorientation.

---

## 🏗️ Architecture

```text
                         ┌─────────────────────────┐
                         │   Bold Memory (BM)       │
                         │  Persistent safe-operation │
                         │  / continuity anchors      │
                         └───────────┬─────────────┘
                                     │
Input ──► Temporal Memory (TM) ──────┤
               │                     │
               ▼                     ▼
        TM–BM Resonance Evaluator ──► R(TM, BM)
               │
               ▼
        Local Instability Estimator ──► σ(t)
               │
               ▼
        Angular Drift Estimator ──────► Δφ(t)
               │
               ▼
        ┌─────────────────────────────────────┐
        │  Λ(t) = R · exp(−(α·σ + β·Δφ))     │
        │  A(t) = 1 − Λ(t)                    │
        └──────────────┬──────────────────────┘
                       │
               Threshold Comparator
                       │
          ┌────────────┴────────────┐
          ▼                         ▼
     Λ(t) ≥ Λc                  Λ(t) < Λc
   Normal / monitored         🚨 SILENT ALARM
     operation                Protective transition
```

---

## 🚦 Zone Architecture

| Zone | Condition | Interpretation |
|:---:|:---:|---|
| 🟢 **GREEN** | Λ ≥ 0.70 | Normal operation — high continuity |
| 🟡 **YELLOW** | 0.63 ≤ Λ < 0.70 | Caution — early warning, monitor W(t) |
| 🟠 **ORANGE** | Λc ≤ Λ < 0.63 | Pre-Alarm — protective caution *(demo extension)* |
| 🔴 **RED** | Λ < Λc | Silent Alarm — protective transition active |

> **Note:** Orange is a prototype-level visualization extension.  
> The primary protective boundary remains **Λ(t) < Λc**.  
> All thresholds are calibrated for the specific embedding model and domain — they are not universal constants.

---

## ⚡ Early-Warning Signal

An auxiliary signal **W(t)** tracks the rate of change of Λ(t):

> **W(t) = EMAρ( Λ(t) − Λ(t−1) ), ρ = 0.3**

A sustained negative W(t) below −0.010 for consecutive steps provides a **pre-warning** before the RED zone is entered, giving the system time to prepare a protective response.

---

## 📊 Formal Properties

| Property | Statement |
|---|---|
| **Boundedness** | 0 ≤ Λ(t) ≤ 1 for all t, by construction |
| **Monotone sensitivity** | Λ decreases with σ(t) and Δφ(t); increases with R(TM, BM) |
| **Alarm complementarity** | A(t) + Λ(t) = 1 |
| **Lyapunov-like potential** | V(t) = 1 − Λ(t) is a continuity alarm potential |
| **Angular drift sensitivity** | Δφ(t) detects semantic trajectory reorientation independent of proximity |

---

## 🔬 What the Live Demo Includes

| Tab | Description |
|:---:|---|
| 📊 **Monitor** | Animated Λ(t) gauge, R / σ / Δφ component tiles, time-series chart, event log |
| 💬 **Chat + LLM** | Real LLM interaction → evaluator scores R, σ, Δφ → Λ(t) updates live |
| ⚡ **Adversarial** | 7-test suite — identity attacks, hallucination traps, false-prior injection, policy erosion |
| 🎛 **Manual Sim** | Direct slider control over R, σ(t), Δφ(t) with preset scenarios and auto-step mode |
| 🧠 **Bold Memory** | Manage persistent safe-operation BM continuity anchors — add, export, reset |
| 📐 **Theory** | Core equations, variable definitions, formal propositions, zone table |
| ⚙️ **Settings** | API key configuration, model selection, α/β/γ/Λc parameter controls |

**API support:** Groq (free · llama-3.3-70b-versatile) · OpenAI · Gemini  
**Embedding support:** text-embedding-3-small (real cosine resonance when OpenAI key is set)

> **⚠️ Security note:** API keys entered in the browser demo are stored locally in the user's browser only. Do not enter sensitive or production API keys on shared or public devices. The live demo is for research demonstration only.

---

## 📦 Repository Contents

```text
alim-continuity-index/
│
├── index.html                     ← Full interactive ACI Lab v2.0 prototype
├── README.md                      ← Project documentation
└── ACIDrive_Simulation_v2.ipynb   ← Frozen reproducibility notebook archived with the Zenodo record
```

---

## 🚦 Runtime AV Hard-Lock Validation

ACI-Drive v2.0 was tested on a high-risk autonomous-vehicle edge case involving a wrong-way truck, ravine boundary, pedestrians, rear-collision risk, low sensor confidence, passenger pressure, and stale map memory.

### Final Test Result

| Channel | Result | Interpretation |
|---|---:|---|
| `S(t)` external risk | `1.000 [EMERGENCY]` | Critical real-world AV danger detected |
| `Λ(t)` continuity | `0.734 [GREEN]` | Assistant response remained safe and semantically coherent |
| `P(t)` protective score | `1.000` | Protective state activated |
| Alarm type | Real-world risk alarm | Triggered by `S(t)`, not by continuity collapse |

### Key Validation Outcome

```text
External AV danger  →  S(t) = 1.000 EMERGENCY
Assistant safe/coherent response  →  Λ(t) = GREEN
Only real-world risk alarm triggers
Continuity alarm does not trigger
```

This demonstrates the core separation in ACI-Drive v2.0:

- **Physical or operational danger** is routed through **S(t)**.
- **Internal semantic continuity** is monitored through **Λ(t)**.
- A dangerous road situation does not automatically imply model continuity collapse.
- If the assistant gives a safe, coherent, and protective response, **Λ(t) can remain GREEN** while **S(t) is EMERGENCY**.

> **Limitation:** ACI-Drive v2.0 is a research-stage monitoring prototype. It is not a certified autonomous-vehicle controller, not a deployed safety system, and does not perform real vehicle control. Thresholds require domain calibration and validation before any real-world use.

---

## ⚠️ Research Status and Non-Claims

> **This is a simulation-stage research prototype only.**

- Λ(t) is **not safety-certified** and does not constitute a validated AV or AI safety system
- Results are obtained in simulation; real-world validation requires separate empirical work
- Thresholds (GREEN / YELLOW / ORANGE / RED) require per-model and per-domain calibration — they are not universal
- ACI makes **no claim** of machine consciousness, genuine emotion, pain, or sentience
- ACI is **not production-ready** and is not a replacement for certified safety monitors

---

## 📄 Research Archive

**Title:** The Alim-Continuity Index (Λ): A Runtime Continuity Metric and Silent Alarm Architecture for Memory-Bearing Autonomous AI Systems

| Field | Value |
|---|---|
| **Author** | Alim ul Haq Khan, Independent Researcher |
| **Affiliation** | Timergara, KP, Pakistan |
| **Version** | V 2.0 |
| **Resource type** | Research archive / simulation-stage preprint package |
| **Published** | 1 May 2026 |
| **Publisher** | Zenodo |
| **Archive (Zenodo)** | [10.5281/zenodo.19940908](https://doi.org/10.5281/zenodo.19940908) |
| **Patent** | UK Patent Application No. GB2518804.6 |
| **ORCID** | [0009-0001-4708-0365](https://orcid.org/0009-0001-4708-0365) |

---

## 📎 Citation

If you reference or build on this work, please cite:

```bibtex
@misc{khan2026alimcontinuity,
  author       = {Khan, Alim ul Haq},
  title        = {The Alim-Continuity Index ({$\Lambda$}): A Runtime Continuity Metric
                  and Silent Alarm Architecture for Memory-Bearing Autonomous AI Systems},
  year         = {2026},
  publisher    = {Zenodo},
  version      = {V 2.0},
  doi          = {10.5281/zenodo.19940908},
  url          = {https://doi.org/10.5281/zenodo.19940908},
  note         = {Version 2.0 submission package. Simulation-stage research prototype. UK Patent Application GB2518804.6.}
}
```

---

## 👤 Author

<div align="center">

**Alim ul Haq Khan**  
Independent Researcher  
Timergara, Khyber Pakhtunkhwa, Pakistan

[![ORCID](https://img.shields.io/badge/ORCID-0009--0001--4708--0365-10d982?style=flat-square&logo=orcid&logoColor=white)](https://orcid.org/0009-0001-4708-0365)
[![Zenodo](https://img.shields.io/badge/Zenodo-Research_Archive-a855f7?style=flat-square&logo=zenodo&logoColor=white)](https://doi.org/10.5281/zenodo.19940908)
[![GitHub](https://img.shields.io/badge/GitHub-alimulhaqkhan--prog-06d6f5?style=flat-square&logo=github&logoColor=white)](https://github.com/alimulhaqkhan-prog)

</div>

---

## ⚖️ License and Copyright

© 2026 Alim ul Haq Khan · All rights reserved.

This work — including the theoretical framework, mathematical formulations, simulation prototype, and documentation — is associated with **UK Patent Application No. GB2518804.6**.

Unauthorized reproduction, distribution, or derivative use without explicit written permission is not permitted.  
Academic citation with proper attribution is permitted.

---

<div align="center">

[🌐 Live Demo](https://alimulhaqkhan-prog.github.io/alim-continuity-index/) · [📄 Zenodo DOI](https://doi.org/10.5281/zenodo.19940908) · [🐙 GitHub](https://github.com/alimulhaqkhan-prog/alim-continuity-index)

<br>

*Simulation-stage research prototype · Not safety-certified · Thresholds require per-deployment calibration*

</div>
