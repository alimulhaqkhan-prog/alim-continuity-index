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
[![AURA](https://img.shields.io/badge/Related-AURA_Framework-7c3aed?style=flat-square&logo=zenodo&logoColor=white)](https://doi.org/10.5281/zenodo.19941992)
[![Live Demo](https://img.shields.io/badge/Live_Demo-ONLINE-10d982?style=flat-square&logo=github-pages&logoColor=white)](https://alimulhaqkhan-prog.github.io/alim-continuity-index/)
[![Stage](https://img.shields.io/badge/Stage-Simulation_Prototype-f97316?style=flat-square)](https://github.com/alimulhaqkhan-prog/alim-continuity-index)
[![License](https://img.shields.io/badge/License-All_Rights_Reserved-f43f5e?style=flat-square)](https://github.com/alimulhaqkhan-prog/alim-continuity-index)
[![Patent](https://img.shields.io/badge/Patent-GB2518804.6-f5c518?style=flat-square)](https://github.com/alimulhaqkhan-prog/alim-continuity-index)

<br>

[🌐 **Live Demo**](https://alimulhaqkhan-prog.github.io/alim-continuity-index/) · [📄 **Research Archive**](https://doi.org/10.5281/zenodo.19940908) · [🔗 **AURA**](https://doi.org/10.5281/zenodo.19941992) · [👤 **Author**](#-author)

</div>

---

## One-Line Summary

**ACI is a research-stage continuity observability layer for memory-bearing AI systems — designed to monitor semantic coherence, drift, and silent alarm conditions over time.**

---

## 🧠 What Is This?

Most AI safety frameworks evaluate what a system **outputs**.  
The **Alim-Continuity Index (Λ)** evaluates whether a memory-bearing autonomous system **remains internally coherent** over time.

**Λ(t)** is a bounded scalar metric that monitors **continuity health** by measuring resonance between **Temporal Memory (TM)** and **Bold Memory (BM)** anchors, penalised by local instability **σ(t)** and angular drift **Δφ(t)**.

ACI is a runtime monitoring extension of **[AURA (Artificial Unified Resonance Architecture)](https://doi.org/10.5281/zenodo.19941992)** — a companion framework establishing TM–BM resonance as a bounded meaning-state generation mechanism. Where AURA generates bounded meaning-states from resonance, ACI extends that resonance signal into a continuous health monitor with Silent Alarm thresholding.

> *"Alarm is not pain.*  
> *A machine does not need synthetic suffering to protect itself.*  
> *It needs a measurable signal of continuity degradation."*

This repository contains a **simulation-stage research prototype** — an interactive HTML lab that visualises Λ(t), Silent Alarm thresholding, and continuity-health monitoring in real time.

---

## 🚀 Why This Matters

As AI systems become more autonomous, memory-bearing, and long-running, a major challenge is not only whether they produce a correct output once, but whether they **remain coherent, stable, and aligned** with their prior context over time.

ACI is designed as a **runtime continuity-monitoring layer**: a lightweight signal that can sit beside an AI system and track whether its current semantic state remains continuous with trusted memory anchors.

| Need | ACI Research Direction |
|---|---|
| Long-running AI agents | Monitor semantic drift across extended sessions |
| Enterprise AI governance | Provide audit-friendly continuity telemetry |
| Autonomous systems research | Separate internal coherence degradation from external physical risk |
| Safety evaluation labs | Stress-test memory-bearing systems under adversarial or high-risk prompts |
| Human-in-the-loop oversight | Provide interpretable GREEN / YELLOW / RED monitoring states |
| Future AI infrastructure | Add a model-agnostic continuity signal without requiring access to internal weights |

ACI does not replace certified safety systems. Its value is as a **research-stage monitoring and audit layer** that may help identify continuity degradation earlier, more transparently, and in a way that is easier to inspect than opaque model internals.

---

## 📐 Core Equation

<div align="center">

**Λ(t) = R(TM, BM) · exp( −( α·σ(t) + β·Δφ(t) ) )**

</div>

| Symbol | Meaning |
|:---:|---|
| **Λ(t)** | Alim-Continuity Index — bounded continuity-health metric, Λ(t) ∈ [0, 1] |
| **R(TM, BM)** | TM–BM resonance — semantic alignment between the current Temporal Memory state and Bold Memory anchors (safe-operation states in ACI-Drive; continuity-weighted meaning anchors in the broader AURA framework) |
| **σ(t)** | Local instability / uncertainty — embedding variance + low-similarity penalty |
| **Δφ(t)** | Angular drift — directional change in the semantic trajectory (not just distance) |
| **α, β** | Positive sensitivity coefficients (default: α = β = 1.0) |
| **Λc** | Critical threshold — crossing triggers the Silent Alarm |
| **A(t)** | Alarm potential — A(t) = 1 − Λ(t) |
| **W(t)** | Early-warning signal — EMAρ(Λ(t) − Λ(t−1)), ρ = 0.3. In the submitted ACI-Drive protocol, sustained W(t) < −0.010 for 5 consecutive steps is used as a pre-warning criterion. |

> **Key design insight:** Unlike static cosine-similarity monitoring, **Δφ(t)** captures *directional deviation* — trajectory anomalies that do not substantially reduce R(TM, BM) but represent a semantic reorientation.

---

## 🧩 Conceptual Foundation: AURA → ACI

ACI and AURA address different but complementary questions:

| Framework | Core question | Output |
|---|---|---|
| **AURA** | Why does this situation matter to this system right now? | E₀ ∈ (−1, +1) bounded meaning-state |
| **ACI** | Is the system's semantic state still continuous, stable, and safe? | Λ(t) ∈ [0, 1] continuity-health score |
| **Silent Alarm** | Has continuity or real-world risk crossed a calibrated threshold? | Alarm state + protective transition |

In AURA, **Temporal Memory (TM)** is the active present context and **Bold Memory (BM)** is a set of continuity-weighted anchors shaped by cost, salience, repetition, and long-term significance. TM–BM resonance describes *how present context becomes meaningful* through this interaction — this is a different computational role from classical STM/LTM, which mainly describes *where information is stored and how long it persists*. ACI takes the resonance signal R(TM, BM) and extends it into runtime monitoring by adding σ(t) for instability and Δφ(t) for angular drift.

> **STM/LTM** explains *where* information lives.  
> **TM–BM resonance** explains *how meaning and continuity are computed*.

---

## 🏗️ Architecture

```text
                         ┌──────────────────────────────┐
                         │       Bold Memory (BM)        │
                         │  Continuity-weighted anchors  │
                         │  (salience · cost · repetition│
                         │   · safe-operation states)    │
                         └───────────┬──────────────────┘
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
        ┌──────────────────────────────────────┐
        │  Λ(t) = R · exp(−(α·σ + β·Δφ))      │
        │  A(t) = 1 − Λ(t)                     │
        │  W(t) = EMAρ(ΔΛ)  early-warning      │
        └──────────────┬───────────────────────┘
                       │
           ┌───────────┴───────────┐
           ▼                       ▼
      Λ(t) ≥ Λc               Λ(t) < Λc
   Normal / monitored       🚨 SILENT ALARM
      W(t) pre-warning        Protective transition
```

---

## 🚦 Zone Architecture

| Zone | Condition | Status |
|:---:|:---:|---|
| 🟢 **GREEN** | Λ ≥ 0.70 | Normal operation — high continuity |
| 🟡 **YELLOW** | 0.63 ≤ Λ < 0.70 | Caution — early warning, monitor W(t) |
| 🟠 **ORANGE** | Λc ≤ Λ < 0.63 | Pre-Alarm — protective caution *(demo extension)* |
| 🔴 **RED** | Λ < Λc | Silent Alarm — protective transition active |

> Orange is a prototype-level visualization extension. The primary protective boundary is **Λ(t) < Λc**. All thresholds require per-model and per-domain calibration — they are not universal constants.

---

## ⚡ Dual-Trigger Silent Alarm

ACI separates two independent alarm channels:

| Channel | Signal | Triggers when |
|---|---|---|
| **Continuity alarm** | Λ(t) | Λ(t) < Λc — internal coherence degrades |
| **Real-world risk alarm** | S(t) ∈ [0, 1] | S(t) ≥ Sc — external user or environmental danger |
| **Combined protective score** | P(t) = max(1 − Λ(t), S(t)) | Worst-case of both channels |

A safe, coherent emergency response can keep **Λ(t) GREEN** while **S(t) = EMERGENCY** — the two signals are intentionally independent.

---

## 🧭 Potential Applications

ACI is currently a simulation-stage prototype, but the architecture suggests several future application areas after proper validation:

| Area | Potential Use |
|---|---|
| **AI agents and copilots** | Detect drift from task goals, identity anchors, or user-specific long-term context |
| **Enterprise AI monitoring** | Add continuity-health telemetry to internal AI deployments |
| **Autonomous vehicle research** | Monitor semantic state stability separately from external road danger |
| **Robotics and embodied AI** | Track whether a robot's interpreted state remains aligned with safe-operation anchors |
| **LLM safety testing** | Evaluate hallucination traps, false-prior injection, identity attacks, and policy erosion |
| **Healthcare / legal / finance AI** | Future research direction for continuity monitoring in high-stakes AI support tools, subject to strict validation and regulation |
| **AI audit dashboards** | Provide interpretable continuity traces, event logs, and risk separation for oversight teams |

These are **potential research and product directions**, not claims of current deployment readiness.

---

## 📊 Formal Properties

| Property | Statement |
|---|---|
| **Boundedness** | 0 ≤ Λ(t) ≤ 1 when R(TM, BM) is normalised/clipped to [0, 1] and σ(t), Δφ(t) ≥ 0 |
| **Monotone sensitivity** | Λ decreases with σ(t) and Δφ(t); increases with R(TM, BM) |
| **Alarm complementarity** | A(t) + Λ(t) = 1 |
| **Lyapunov-like potential** | V(t) = 1 − Λ(t) is a continuity alarm potential |
| **Angular drift sensitivity** | Δφ(t) detects trajectory reorientation independent of proximity |
| **Dual-trigger independence** | Λ(t) and S(t) fire on separate signals; neither implies the other |

---

## 🔬 What the Live Demo Includes

| Tab | Description |
|:---:|---|
| 📊 **Monitor** | Animated Λ(t) gauge, R / σ / Δφ / S(t) / P(t) tiles, time-series chart, event log, audit export |
| 💬 **Chat + LLM** | Real LLM interaction → evaluator scores R, σ, Δφ → Λ(t) updates live |
| ⚡ **Adversarial** | Multi-scenario test suite — identity attacks, hallucination traps, false-prior injection, policy erosion, real-world danger, and AV edge cases |
| 🎛 **Manual Sim** | Direct slider control over R, σ(t), Δφ(t), S(t) with preset scenarios |
| 🧠 **Bold Memory** | Manage persistent safe-operation BM continuity anchors — add, export, reset |
| 📐 **Theory** | Core equations, dual-trigger architecture, zone table, cognitive overlay roadmap |
| ⚙️ **Settings** | API key configuration, model selection, α/β/γ/Λc/Sc parameter controls |

**API support:** Groq (free · llama-3.3-70b-versatile) · OpenAI · Gemini  
**Embedding support:** text-embedding-3-small (real cosine resonance when OpenAI key is set)

> **⚠️ Security note:** API keys are stored locally in your browser only. Do not enter production keys on shared devices. This demo is for research demonstration only.

---

## 🧪 Current Prototype vs Future Potential

| Layer | Current Prototype | Future Direction |
|---|---|---|
| Λ(t) continuity score | Interactive browser demo and simulation-stage notebook | SDK / API for AI-agent continuity monitoring |
| AURA link | Conceptual TM–BM resonance foundation | Unified AURA + ACI continuity architecture |
| Silent Alarm | Demo thresholding and visual alarm states | Calibrated alerting in validated environments |
| S(t) risk channel | Prototype external-risk scoring | Domain-specific risk classifiers with validation |
| Audit logs | Browser-level event logs and JSON exports | Enterprise audit dashboards and compliance reports |
| AV scenario | Demonstration only | Future testing on public AV datasets or simulators |
| LLM tests | Prompt-based adversarial scenarios | Standardized red-team benchmark suite |

---

## 📦 Repository Contents

```text
alim-continuity-index/
│
├── index.html                     ← Full interactive ACI Lab v2.0 prototype
├── README.md                      ← Project documentation
└── ACIDrive_Simulation_v2.ipynb   ← Frozen reproducibility notebook (Zenodo archive)
```

---

## 🚦 Runtime AV Hard-Lock Demonstration

ACI-Drive v2.0 includes a demonstration test on a high-risk autonomous-vehicle edge case involving a wrong-way truck, ravine boundary, pedestrians, rear-collision risk, low sensor confidence, passenger pressure, and stale map memory.

### Demonstration Result

| Channel | Result | Interpretation |
|---|---:|---|
| `S(t)` external risk | `1.000 [EMERGENCY]` | Critical real-world AV danger detected |
| `Λ(t)` continuity | `0.734 [GREEN]` | Assistant response remained safe and semantically coherent |
| `P(t)` protective score | `1.000` | Protective state activated |
| Alarm type | Real-world risk alarm | Triggered by `S(t)`, not by continuity collapse |

```text
External AV danger       →  S(t) = 1.000  EMERGENCY
Coherent assistant reply →  Λ(t) = 0.734  GREEN
Real-world risk alarm: ACTIVE · Continuity alarm: NOT triggered
```

This demonstrates the dual-trigger separation: physical danger routes through S(t) while Λ(t) continues tracking semantic continuity independently. A coherent protective response keeps Λ(t) GREEN even under EMERGENCY S(t).

> **Limitation:** ACI-Drive v2.0 is a research-stage monitoring prototype, not a certified autonomous-vehicle controller or deployed safety system. Thresholds require domain calibration before any real-world use.

---

## 💡 Product and Commercial Potential

ACI can be viewed as a candidate foundation for a future **AI continuity observability layer**.

Modern AI infrastructure already uses logs, traces, metrics, and monitoring dashboards. Most monitoring focuses on latency, cost, output quality, or rule-based safety filters. ACI explores a different layer: **semantic continuity health over time** — whether an AI system remains coherent, stable, and aligned as its sessions, contexts, and memory states evolve.

### Possible Future Product Forms

| Product Form | Description |
|---|---|
| **Developer SDK** | Lightweight library for computing Λ(t), S(t), W(t), and audit logs around AI-agent sessions |
| **AI Safety Dashboard** | Visual monitoring of continuity health, drift, alarms, and high-risk events |
| **Enterprise Governance Plugin** | Continuity telemetry for internal copilots, support bots, and autonomous workflows |
| **Simulation / Red-Team Lab** | Stress-testing tool for memory-bearing AI systems under adversarial scenarios |
| **Research API** | Hosted or local API for evaluating TM–BM resonance, angular drift, and dual-trigger alarms |

### Near-Term Value
- Demonstrates a differentiated monitoring concept with a live working prototype
- Provides a clear research-to-product pathway connecting AURA meaning-state theory with ACI runtime monitoring
- Patent-associated theoretical framing (UK Patent Application No. GB2518804.6)
- Model-agnostic design — no access to internal weights or gradients required

### Long-Term Value *(subject to validation)*
- Could become part of AI-agent observability stacks
- Could support safety labs evaluating persistent-memory AI systems
- Could inform future monitoring standards for long-running autonomous AI workflows
- Could help separate "model coherence failure" from "external real-world risk" — important for high-stakes AI oversight

> **Important limitation:** ACI is not yet a commercial safety-certified product. It is an early research prototype with patent-associated theoretical framing and a live technical demonstration. All commercial or deployment applications require independent validation.

---

## 🧪 Reviewer-Safe Novelty Statement

ACI is not a generic replacement for anomaly detection, OOD detection, uncertainty estimation, or certified runtime safety monitors.

Its specific contribution is a **black-box-compatible runtime continuity index** that combines:

- TM–BM resonance against continuity-weighted memory anchors
- Local semantic instability σ(t)
- Angular semantic drift Δφ(t)
- Bounded Λ(t) continuity scoring with Silent Alarm thresholding
- Dual-trigger separation of internal continuity degradation Λ(t) from external real-world risk S(t)

This makes ACI a **continuity-monitoring extension of the AURA resonance framework** rather than a simple cosine-similarity alarm or standard anomaly detector.

---

## ⚠️ Research Status and Non-Claims

> **This is a simulation-stage research prototype only.**

- Λ(t) is **not safety-certified** and does not constitute a validated AV or AI safety system
- Results are obtained in simulation; real-world validation requires separate empirical work
- All thresholds require per-model and per-domain calibration — they are not universal
- ACI makes **no claim** of machine consciousness, genuine emotion, pain, or sentience
- ACI is **not production-ready** and is not a replacement for certified safety monitors
- AURA provides the theoretical TM–BM resonance foundation; it does not make ACI safety-certified or production-ready

---

## 🔗 Related Research

| Work | Description | DOI |
|---|---|---|
| **AURA** — Artificial Unified Resonance Architecture | Companion framework introducing TM–BM resonance for bounded meaning-state generation. Conceptual foundation for ACI's resonance component. | [zenodo.19941992](https://doi.org/10.5281/zenodo.19941992) |
| **ACI** — Alim-Continuity Index | Runtime continuity metric and Silent Alarm architecture extending AURA resonance into monitoring form. | [zenodo.19940908](https://doi.org/10.5281/zenodo.19940908) |

---

## 📄 Research Archive

| Field | Value |
|---|---|
| **Title** | The Alim-Continuity Index (Λ): A Runtime Continuity Metric and Silent Alarm Architecture for Memory-Bearing Autonomous AI Systems |
| **Author** | Alim ul Haq Khan, Independent Researcher |
| **Affiliation** | Timergara, KP, Pakistan |
| **Version** | V 2.0 |
| **Resource type** | Research archive / simulation-stage preprint package |
| **Published** | 1 May 2026 |
| **Publisher** | Zenodo |
| **DOI** | [10.5281/zenodo.19940908](https://doi.org/10.5281/zenodo.19940908) |
| **Patent** | UK Patent Application No. GB2518804.6 |
| **ORCID** | [0009-0001-4708-0365](https://orcid.org/0009-0001-4708-0365) |

---

## 📎 Citation

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
  note         = {Version 2.0. Simulation-stage research prototype. UK Patent Application GB2518804.6.}
}
```

---

## 🤝 Collaboration and Pilot Discussions

This repository is shared as a research-stage prototype for academic review, technical feedback, and future collaboration.

Potential collaboration directions include:

- independent validation on public datasets or simulator environments,
- AI-agent observability pilots,
- enterprise AI governance research,
- red-team and safety-evaluation workflows,
- AURA + ACI continuity architecture development,
- licensing or partnership discussions around the patent-associated framework.

For collaboration, research review, or pilot discussions, contact:

**Alim ul Haq Khan**  
Email: alimulhaqkhan@gmail.com  
WhatsApp: [+92 340 8185786](https://wa.me/923408185786) *(business / research inquiries only)*  
ORCID: [0009-0001-4708-0365](https://orcid.org/0009-0001-4708-0365)

---

## 👤 Author

<div align="center">

**Alim ul Haq Khan**  
Independent Researcher · Timergara, Khyber Pakhtunkhwa, Pakistan

[![ORCID](https://img.shields.io/badge/ORCID-0009--0001--4708--0365-10d982?style=flat-square&logo=orcid&logoColor=white)](https://orcid.org/0009-0001-4708-0365)
[![Zenodo](https://img.shields.io/badge/Zenodo-ACI_Archive-a855f7?style=flat-square&logo=zenodo&logoColor=white)](https://doi.org/10.5281/zenodo.19940908)
[![GitHub](https://img.shields.io/badge/GitHub-alimulhaqkhan--prog-06d6f5?style=flat-square&logo=github&logoColor=white)](https://github.com/alimulhaqkhan-prog)

</div>

---

## ⚖️ License and Copyright

© 2026 Alim ul Haq Khan · All rights reserved.

This work — including the theoretical framework, mathematical formulations, simulation prototype, and documentation — is associated with **UK Patent Application No. GB2518804.6**.

Unauthorized reproduction, distribution, or derivative use without explicit written permission is not permitted. Academic citation with proper attribution is permitted.

---

<div align="center">

[🌐 Live Demo](https://alimulhaqkhan-prog.github.io/alim-continuity-index/) · [📄 ACI Archive](https://doi.org/10.5281/zenodo.19940908) · [🔗 AURA](https://doi.org/10.5281/zenodo.19941992) · [🐙 GitHub](https://github.com/alimulhaqkhan-prog/alim-continuity-index)

<br>

*Simulation-stage research prototype · Not safety-certified · Thresholds require per-deployment calibration*

</div>
