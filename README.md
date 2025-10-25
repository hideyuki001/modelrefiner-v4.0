# ModelRefiner v4.0 — Creative Integration Layer  
*A Reproducible Framework for Structured Creativity in AI Localization and Cultural Design*  
© 2025 Hideyuki Okabe — MIT License  

---

## 🧩 Overview  
**ModelRefiner v4.0** is the successor to **ModelRefiner v3.5**, extending its *Refinement & Retraining* loop with a **Creative Induction Layer** that fuses:  

- **HeartScape** → Emotional & symbolic mapping layer  
- **SYNAPSE** → Metaphor & perspective variation engine  

Together, they enable **reproducible creativity** — where emotion, culture, and structure interact transparently within a verifiable QA loop.

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
