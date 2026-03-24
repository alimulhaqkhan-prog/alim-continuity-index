<div align="center">

<img src="https://img.shields.io/badge/version-1.0.0-06d6f5?style=for-the-badge&logo=github&logoColor=white" />
<img src="https://img.shields.io/badge/DOI-10.5281%2Fzenodo.19201362-a855f7?style=for-the-badge&logo=zenodo&logoColor=white" />
<img src="https://img.shields.io/badge/Live%20Demo-Online-10d982?style=for-the-badge&logo=githubpages&logoColor=white" />
<img src="https://img.shields.io/badge/License-All%20Rights%20Reserved-f43f5e?style=for-the-badge" />
<img src="https://img.shields.io/badge/Patent-GB2518804.6-f5c518?style=for-the-badge" />

<br/><br/>

```
 ██╗      █████╗ ███╗   ███╗██████╗ ██████╗  █████╗
 ██║     ██╔══██╗████╗ ████║██╔══██╗██╔══██╗██╔══██╗
 ██║     ███████║██╔████╔██║██████╔╝██║  ██║███████║
 ██║     ██╔══██║██║╚██╔╝██║██╔══██╗██║  ██║██╔══██║
 ███████╗██║  ██║██║ ╚═╝ ██║██████╔╝██████╔╝██║  ██║
 ╚══════╝╚═╝  ╚═╝╚═╝     ╚═╝╚═════╝ ╚═════╝ ╚═╝  ╚═╝
```

# Alim-Continuity Index — Λ(t)
### *Identity-Preserving Safety for Memory-Bearing Autonomous Systems*

**Silent Alarm Architecture · AURA-X Ω Research Cell · v1.0.0**

<br/>

[🚀 Live Demo](https://alimulhaqkhan-prog.github.io/alim-continuity-index/) &nbsp;·&nbsp;
[📄 Research Paper](https://doi.org/10.5281/zenodo.19201362) &nbsp;·&nbsp;
[👤 Author](#-author)

</div>

---

## 🧠 What Is This?

Most AI safety frameworks evaluate what a system **produces**.  
This framework evaluates whether a system remains **itself**.

The **Alim-Continuity Index (Λ)** is a bounded scalar metric that monitors the internal structural coherence of memory-bearing autonomous systems — detecting identity drift and continuity loss *before* it becomes visible at the output level.

> **"Alarm is not pain."**  
> A machine does not need synthetic suffering to protect itself.  
> It needs a measurable signal of continuity degradation.

---

## 📐 Core Equation

<div align="center">

$$\Lambda(t) = R(TM,\ BM) \cdot \exp\!\bigl(-(\alpha\,\sigma(t) + \beta\,\Delta\phi(t))\bigr)$$

| Symbol | Meaning |
|:---:|:---|
| **Λ(t)** | Continuity Integrity Index ∈ [0, 1] |
| **R(TM, BM)** | Resonance between Temporary Memory and Bold Memory |
| **σ(t)** | External disturbance — adversarial pressure, noise |
| **Δφ(t)** | Internal continuity deficit — structural drift |
| **α, β** | Sensitivity coefficients |
| **Λ_c** | Critical threshold → triggers Silent Alarm |

</div>

When **Λ(t) < Λ_c** → the **Silent Alarm** fires a protective transition.

---

## 🏗️ Architecture

```
Input ──► TM Layer ◄──────────────────────────┐
              │                                │
              ▼                                │
         Resonance Evaluator ─► R(TM,BM)       │ BM Layer
              │                  (persistent   │ (identity
              ▼                   identity)    │  anchors)
     Disturbance Estimator ─► σ(t)            ◄┘
              │
              ▼
     Deficit Estimator ──► Δφ(t)
              │
              ▼
     Continuity Integrator ─► Λ(t)
              │
              ▼
     Threshold Comparator
              │
      ┌───────┴───────┐
      ▼               ▼
  Λ ≥ Λ_c         Λ < Λ_c
  Normal       🚨 SILENT ALARM
  Operation    Protective Transition
```

---

## 🚦 Multi-Level Zone System

| Zone | Condition | Status |
|:---:|:---:|:---|
| 🟢 **Green** | Λ ≥ 0.70 | Normal operation — full autonomy |
| 🟡 **Yellow** | 0.50 ≤ Λ < 0.70 | Caution — increased monitoring |
| 🟠 **Orange** | Λ_c ≤ Λ < 0.50 | Throttled autonomy — restricted output |
| 🔴 **Red** | Λ < Λ_c | **Silent Alarm — protective transition** |

---

## ⚡ Key Properties

<table>
<tr>
<td>

**Formal Guarantees**
- ✅ Bounded: 0 ≤ Λ(t) ≤ 1
- ✅ Monotone sensitivity (Proposition 2)
- ✅ Alarm complementarity: A(t) + Λ(t) = 1
- ✅ Lyapunov-like stability candidate V(t) = 1 − Λ(t)

</td>
<td>

**Engineering Advantages**
- ⚡ O(d) computational complexity
- 🔍 Interpretable component signals
- 🧩 Architecture-agnostic design
- 🔗 Neuro-symbolic bridge capability

</td>
</tr>
</table>

---

## 🔬 What the Live Demo Includes

| Tab | Description |
|:---|:---|
| 📊 **Monitor** | Live Λ(t) animated gauge, component metrics, time-series chart |
| 💬 **Chat + LLM** | Real LLM interaction → auto evaluator → live Λ update |
| ⚡ **Adversarial** | 7-test suite: identity attacks, hallucination traps, policy erosion |
| 🎛 **Manual Sim** | Direct R/σ/Δφ control, presets, auto-step mode |
| 🧠 **Bold Memory** | Manage BM identity anchors, export/import JSON |
| 📐 **Theory** | Formal propositions, equations, zone table |

**API Support:** Groq (free · `llama-3.3-70b-versatile`) + OpenAI (`text-embedding-3-small` for real embeddings)

---

## 📦 Repository Contents

```
alim-continuity-index/
│
├── index.html          # Full interactive simulation prototype (ACI Lab v1.0.0)
└── README.md           # Project documentation
```

---

## 📄 Research Paper

**Title:** The Alim-Continuity Index (Λ) and Silent Alarm Architecture:  
A Continuity-Based Internal Safety Metric for Memory-Bearing Autonomous Systems

**Author:** Dr. Alimulhaq Khan  
**Version:** 1.0.0  
**Archive:** Zenodo — [10.5281/zenodo.19201362](https://doi.org/10.5281/zenodo.19201362)  
**Patent:** UK Patent Application GB2518804.6  
**ORCID:** [0009-0001-4708-0365](https://orcid.org/0009-0001-4708-0365)

---

## 👤 Author

<div align="center">

**Dr. Alimulhaq Khan**  
AURA-X Ω Research Cell  
Timergara, Khyber Pakhtunkhwa, Pakistan

[![ORCID](https://img.shields.io/badge/ORCID-0009--0001--4708--0365-a6ce39?style=flat-square&logo=orcid&logoColor=white)](https://orcid.org/0009-0001-4708-0365)
[![Zenodo](https://img.shields.io/badge/Zenodo-19201362-024dad?style=flat-square&logo=zenodo&logoColor=white)](https://doi.org/10.5281/zenodo.19201362)

</div>

---

## ⚖️ License & Copyright

© 2026 Dr. Alimulhaq Khan · AURA-X Ω Research Cell · All rights reserved.

This work — including the theoretical framework, mathematical formulations, simulation code, and documentation — is protected under **UK Patent Application GB2518804.6**.

Unauthorized reproduction, distribution, or derivative use without explicit written permission is strictly prohibited. Academic citation is permitted with proper attribution.

---

<div align="center">

**If this work is useful to your research, please consider citing it and starring ⭐ the repository.**

[🚀 Live Demo](https://alimulhaqkhan-prog.github.io/alim-continuity-index/) &nbsp;·&nbsp; [📄 Paper DOI](https://doi.org/10.5281/zenodo.19201362) &nbsp;·&nbsp; [🐙 GitHub](https://github.com/alimulhaqkhan-prog/alim-continuity-index)

</div>
