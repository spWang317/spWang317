# Hi, I'm Sungpil Wang (왕성필) 👋

**Ph.D. Candidate @ KAIST Graduate School of Culture Technology**  
Computational Humanist.

Building pipelines that turn unstructured text into measurable structure.

---

## 🔬 What I Do

I design end-to-end ML pipelines for **unstructured text data** — from large-scale web crawling and OCR preprocessing to embedding-based analysis and LLM-powered applications.

My research sits at the intersection of **Natural Language Processing** and **Computational Humanities**, with a focus on:
- Semantic trajectory modeling in high-dimensional embedding space
- LLM-based surprisal estimation for narrative structure analysis
- RAG pipeline design for domain-specific text retrieval
- Multimodal (text + image) association frameworks

---

## 🛠 Tech Stack

**Languages**
`Python` `R` `SQL` `Cypher`

**ML / NLP**
`PyTorch` `HuggingFace Transformers` `Sentence-Transformers` `scikit-learn` `XGBoost` `LightGBM`

**LLMs & Embeddings**
`Solar-10.7B (4-bit quantized)` `Ko-SRoBERTa` `Whisper` `Tesseract OCR`

**Data & Infra**
`FAISS` `pandas` `NumPy` `Selenium` `MySQL` `Neo4j` `Conda/pip`

**Tools**
`Jupyter` `Git` `Linux (Ubuntu)` `NVIDIA GPU (RTX A6000)`

---

## 📁 Projects

### 🧠 AI Agent for Korean Flash Fiction Generation *(private repo)*

End-to-end generative AI agent pipeline that trains and steers a Korean LLM to produce flash fiction aligned with human narrative archetypes.
- Extracted **8D Narrative DNA** per story: 3 temporal signal trajectories (Surprisal, Coherence, Semantic Shift) resampled to **57-bin corridors** + 5D geometric scalars (Δ, σ, Γ, κ, Ω)
- Clustered 2,542 stories into **9 narrative archetypes** via Bayesian GMM on 176D feature vectors (171-bin trajectories + 5D scalars)
- Fine-tuned **Solar-10.7B** with LoRA SFT conditioned on archetype ID and 8D metrics, then optimized with **PPO** using a dual reward: `exp(−0.5·dM) × exp(−3.0·corridor_penalty)`
- Built a **LangGraph-based NarrativeGraph agent** (diagnose → plan → revise → sanitize → verify) that iteratively realigns generated stories to the target archetype's DNA corridor via CoT reasoning

`Solar-10.7B` `LoRA` `PPO` `LangGraph` `Ko-SRoBERTa` `Bayesian GMM` `bitsandbytes` `trl`

---

### ⚡ [Korean Flash Fiction RAG Pipeline](https://github.com/spWang317/Korean_Flash_Fiction_RAG)

Chunk-based RAG system for 2,900+ Korean flash fiction texts using FAISS vector search + Solar-10.7B generation.
- Implemented **chunk-level FAISS indexing** with safe KSS sentence splitting and tail-merging for context preservation
- Built **best-sentence selector**: re-ranks sentences within retrieved chunks by query similarity before injection
- Deduplication logic ensures diverse retrieval across documents
- Designed for low-hallucination generation via explicit `[근거문장]` prompt format

`FAISS` `Solar-10.7B` `Ko-SRoBERTa` `KSS` `MeCab` `RAG`

---

### 📖 [Korean Flash Fiction Analysis](https://github.com/spWang317/Flash_Fiction_Analysis)

Computational analysis of narrative structure in 2,636 Korean flash fiction stories using sentence-level signal trajectories.
- Ran **Solar-10.7B** (4-bit NF4 quantized) on GPU server for sentence-level surprisal estimation across full corpus
- Computed coherence (Ko-SRoBERTa cosine similarity) and semantic shift (cumulative context deviation)
- Identified **5 structural archetypes** via k-means clustering on normalized 50-point trajectories
- Validated "fracture and leap" cycle: surprisal peaks → coherence drop + semantic shift spike (Wilcoxon, Bonferroni-corrected)

`Solar-10.7B` `Ko-SRoBERTa` `k-means` `KDE` `Kruskal-Wallis` `bitsandbytes`

---

### 📐 [Prose Poetry vs. Flash Fiction: 5D Semantic Dynamics](https://github.com/spWang317/ProsePoetry_against_FlashFiction)

Geometric differentiation of two visually indistinguishable short-form prose genres via semantic trajectory analysis.
- Constructed a **5D coordinate system** (Displacement, Surprisal Volatility, Global Resonance, Curvature, Spectral Centroid) from sentence embeddings
- Applied **PERMANOVA** (pseudo-F = 13.66, p < 0.001) and Levene's test to confirm location-driven separation
- Validated coordinate independence: VIF < 1.2 across all 5 dimensions
- Ablation study (Random Forest probe) confirmed Surprisal Volatility as the strongest discriminating feature

`Ko-SRoBERTa` `PERMANOVA` `OLS regression` `Random Forest` `SHAP-style ablation`

---

### 🎨 [Word–Color Association Framework](https://github.com/spWang317/Word_Color_Association)

Large-scale word–color association via automated web image retrieval and CIELch color space analysis.
- Built a fully reproducible pipeline: Google Image crawling (Selenium) → pixel-level color extraction → 10-dimensional color vector per word
- Applied to **top 100 global brands** (cosine similarity between logos and web images) and **20th-century Anglo-American poetry** (Amy Lowell vs. Georgia Douglas Johnson)
- Language-agnostic framework; open-source module included

`Python` `Selenium` `scikit-image` `Bootstrap resampling` `CIELch`

---

### 🗺 [Prosepoem Atlas](https://github.com/spWang317/prosepoem-atlas)
> *Open dataset — [10.5281/zenodo.20149336](https://doi.org/10.5281/zenodo.20149336), CC BY 4.0*

An atlas of 4,642 Korean prose poems without line breaks, drawn from four major publisher series (2000–2024).
- Redacted public metadata, summary tables, and figures with a full reproduction pipeline under `scripts/`
- Copyright-safe release design: working full texts stay local, only derived artefacts are published

`BERTopic` `Ko-SRoBERTa` `PMI network` `Zenodo` `Hugging Face`

---

### 🔍 [Korean Prose Poetry Reliability Audit](https://github.com/spWang317/korean-prosepoem-reliability-audit)

Multi-axis reliability analysis identifying which motifs genuinely recur across a prose-poetry corpus.
- BERTopic topic identification cross-validated across **parameter, sample, seed, and membership** perturbations
- Six motifs survive all four axes (sea, flora, rain, meta-poetic, music, cat)
- Full reproducibility deposit from SBERT embeddings onward

`BERTopic` `Ko-SRoBERTa` `NNLS` `reliability analysis`

---

### 🎙 Audio Separate & Transcribe *(private repo)*
> *Part of KOCCA-funded broadcasting monitoring R&D (2023–2025)*

Robust speech transcription pipeline with vocal separation for noisy/music-heavy audio.
- **Demucs (HTDemucs)** for source separation with automatic fallback logic (RMS threshold, duration check)
- **Whisper large-v2** for timestamped transcription
- Handles `.mp3` / `.mp4`; designed for large-scale broadcast monitoring

`Demucs` `Whisper` `FFmpeg` `PyTorch`

---

## 📄 Publications

각 논문의 최신 상태는 아래 표가 유일한 기준입니다.

<!-- PUBLICATIONS:START — sync.py 가 생성. 직접 고치지 마세요 -->

| Title | Venue | Status |
|---|---|---|
| [Word–Color Association from Large-Scale Online Data: Methodology and Applications](https://github.com/spWang317/Word_Color_Association) | PLOS ONE | Revision |
| [Information dynamics in compressed narratives: five dynamical regimes and a fracture-and-leap cycle](https://github.com/spWang317/Flash_Fiction_Analysis) | Physica A: Statistical Mechanics and its Applications | Under review · [preprint](https://doi.org/10.21203/rs.3.rs-8619161/v1) |
| [From Kinetic to Resonant Regimes: Geometric Differentiation of Prose Poetry against Flash Fiction](https://github.com/spWang317/ProsePoetry_against_FlashFiction) | Scientific Reports | Under review · [preprint](https://doi.org/10.21203/rs.3.rs-8722451/v1) |
| [Prosepoem Atlas: An Atlas of Korean Prose Poetry without Line Breaks (Four Major Publisher Series, 2000–2024)](https://github.com/spWang317/prosepoem-atlas) | Zenodo | Published · [doi](https://doi.org/10.5281/zenodo.20149336) |

<!-- PUBLICATIONS:END -->

---

## 🎓 Education

- **Ph.D.** Cultural Technology, KAIST (2022–2027 expected)
- **M.Eng.** Cultural Technology, KAIST (2020–2022)
- **B.Eng.** Industrial & System Engineering + Culture & Arts Software + Creative Writing, Dongguk Univ. (2015–2020)

---

## 📬 Contact

📧 wangsp0317@kaist.ac.kr · 🌐 [spwang317.github.io](https://spwang317.github.io/)
