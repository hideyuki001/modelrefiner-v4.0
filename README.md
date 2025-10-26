# 🚀 ModelRefiner v4.0 — Creative Integration Layer  
*A Reproducible Framework for Structured Creativity in AI Localization and Cultural Design*  
© 2025 Hideyuki Okabe · MIT License  

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Build](https://img.shields.io/badge/Build-Stable-success)](#)
[![ΔS Metric](https://img.shields.io/badge/ΔS-Creative%20Entropy-ff69b4)](docs/rope_metrics.md)
[![HeartScape × SYNAPSE](https://img.shields.io/badge/Integrated-HeartScape%20×%20SYNAPSE-9cf)](#)
[![GitHub Stars](https://img.shields.io/github/stars/hideyuki001/modelrefiner-v4.0?style=social)](https://github.com/hideyuki001/modelrefiner-v4.0/stargazers)

---

## 🧩 Overview

**ModelRefiner v4.0** extends the v3.5 *Refinement & Retraining* loop  
with a **Creative Induction Layer** that fuses:

- 🪞 **HeartScape** → Emotional & symbolic mapping layer  
- 🧠 **SYNAPSE** → Metaphor & perspective variation engine  
- ⚙️ **QA Synth Pro** → Structural QA evaluation backbone  

Together, they enable **Reproducible Creativity** —  
where emotion, culture, and structure interact transparently within a verifiable QA loop.

> “Beyond optimization — toward *structured emergence*.”  

---

## 🌈 Core Architecture

```mermaid
graph TD
    A[Input: Source Text / Locale / Constraints] --> B[Evaluation → ΔS Calculation]
    B -->|ΔS ≥ 0.15| C[Creative Induction Layer]
    B -->|ΔS < 0.15| D[QA-Only Mode (v3.5)]
    C --> E[HeartScape Emotional Mapping]
    C --> F[SYNAPSE Metaphor Reconfiguration]
    E --> G[ModelRefiner Core Integration]
    F --> G
    G --> H[QA Synth Pro Re-evaluation]
    H --> I[Refined Output + Metrics + ΔS_new]


---

## 🎯 Intended Audience  
Localization researchers, translation QA specialists, AI linguists, and creative QA developers working on:  
- Generative content evaluation  
- Multilingual cultural adaptation  
- Brand tone alignment  
- Structured creative rewriting  

---

## 📘 Documentation  
| File | Description |
|------|--------------|
| [`docs/system_instructions.md`](docs/system_instructions.md) | Full technical specification (8K-level transparency) |
| [`docs/translation_matrix.md`](docs/translation_matrix.md) | Cross-locale mapping and creative axes |
| [`docs/rope_metrics.md`](docs/rope_metrics.md) | ΔS (Creative Entropy) & Creative Fit metrics |
| [`docs/examples.md`](docs/examples.md) | Practical use cases and sample data |

---

## 🧠 Core Evolution from v3.5  
| Category | v3.5 | v4.0 |
|-----------|------|------|
| Loop | Evaluate → Refine → Retrain | **Evaluate → Induce → Refine → Re-eval** |
| Creative Layer | None | **Creative Induction Layer (HeartScape × SYNAPSE)** |
| Metrics | Fidelity, Structure, Style, Culture | **＋ ΔS, Creative Fit (Novelty × Utility × Brand Alignment)** |
| Architecture | Single model | **Dual-AI Protocol (Claude = emotion / ChatGPT = structure)** |
| Domain Coverage | QA & Localization | **＋ Cultural Design, UX Text, Education, NPC Dialogue** |

---

## 🧪 Examples  
- [`examples/in_lyrics.json`](examples/in_lyrics.json) — Lyrics localization (EN→JA)  
- (TBD) UX Microcopy — CTA tone & rhythm adaptation  
- (TBD) Education — Pedagogic metaphor restraint  

---

## ⚙️ Usage  

pip install -r requirements.txt
python v4/scripts/pipeline_cli.py --in examples/in_lyrics.json --out out.jsonl
The CLI is a mock implementation for demonstration.
Replace induce() and refine() with actual LLM API calls using the provided prompts in v4/prompts/.

🧭 Notes
Transparency-first: Every creative step is logged and reproducible.

Safety hooks: copyright, bias, and cultural constraints enforced.

Cultural intelligence: honors rhythm (ma/間), metaphor, and indirectness.

📜 License
MIT License — see LICENSE

🪶 About
ModelRefiner v4.0 extends the foundation of v3.5 into the realm of creative reproducibility —
a framework where structure feels and emotion thinks.
It aims to bring together fidelity, empathy, and brand-aligned creativity
within a unified, auditable system for AI-driven localization and cultural QA.

---
### 🧭 Project Navigation
- [📘 Documentation](./docs/)
- [🧪 Examples](./examples/)
- [🚀 Latest Release](https://github.com/hideyuki001/modelrefiner-v4.0/releases/tag/v4.0.0)
