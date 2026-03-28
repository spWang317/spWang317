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

### 🧠 [AI Agent for Korean Flash Fiction Generation](https://github.com/spWang317/AI_Agent_For_Generation-Korean_Flash_Fiction-)

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

### 📖 [Korean Flash Fiction Analysis](https://github.com/spWang317/Korean_Flash_Fiction_Analysis)
> *Submitted to **Nature Humanities & Social Sciences***

Computational analysis of narrative structure in 2,636 Korean flash fiction stories using sentence-level signal trajectories.
- Ran **Solar-10.7B** (4-bit NF4 quantized) on GPU server for sentence-level surprisal estimation across full corpus
- Computed coherence (Ko-SRoBERTa cosine similarity) and semantic shift (cumulative context deviation)
- Identified **5 structural archetypes** via k-means clustering on normalized 50-point trajectories
- Validated "fracture and leap" cycle: surprisal peaks → coherence drop + semantic shift spike (Wilcoxon, Bonferroni-corrected)

`Solar-10.7B` `Ko-SRoBERTa` `k-means` `KDE` `Kruskal-Wallis` `bitsandbytes`

---

### 📐 [Prose Poetry vs. Flash Fiction: 5D Semantic Dynamics](https://github.com/spWang317/ProsePoetry_against_FlashFiction)
> *Submitted to **Scientific Reports***

Geometric differentiation of two visually indistinguishable short-form prose genres via semantic trajectory analysis.
- Constructed a **5D coordinate system** (Displacement, Surprisal Volatility, Global Resonance, Curvature, Spectral Centroid) from sentence embeddings
- Applied **PERMANOVA** (pseudo-F = 13.66, p < 0.001) and Levene's test to confirm location-driven separation
- Validated coordinate independence: VIF < 1.2 across all 5 dimensions
- Ablation study (Random Forest probe) confirmed Surprisal Volatility as the strongest discriminating feature

`Ko-SRoBERTa` `PERMANOVA` `OLS regression` `Random Forest` `SHAP-style ablation`

---

### 🎨 [Word–Color Association Framework](https://github.com/spWang317/Word_Color_Association)
> *Submitted to **PLoS ONE***

Large-scale word–color association via automated web image retrieval and CIELch color space analysis.
- Built a fully reproducible pipeline: Google Image crawling (Selenium) → pixel-level color extraction → 10-dimensional color vector per word
- Applied to **top 100 global brands** (cosine similarity between logos and web images) and **20th-century Anglo-American poetry** (Amy Lowell vs. Georgia Douglas Johnson)
- Language-agnostic framework; open-source module included

`Python` `Selenium` `scikit-image` `Bootstrap resampling` `CIELch`

---

### 🎙 [Audio Separate & Transcribe](https://github.com/spWang317/Audio_Separate_and_Transcribe)
> *Part of KOCCA-funded broadcasting monitoring R&D (2023–2025)*

Robust speech transcription pipeline with vocal separation for noisy/music-heavy audio.
- **Demucs (HTDemucs)** for source separation with automatic fallback logic (RMS threshold, duration check)
- **Whisper large-v2** for timestamped transcription
- Handles `.mp3` / `.mp4`; designed for large-scale broadcast monitoring

`Demucs` `Whisper` `FFmpeg` `PyTorch`

---

## 📄 Publications

| Title | Venue | Status |
|---|---|---|
| The Fracture and Leap Cycle: Quantifying Narrative Surprise in Flash Fiction | Nature HSSC | Preprint (Research Square) |
| From Kinetic to Resonant Regimes: Geometric Differentiation of Prose Poetry | Scientific Reports | Preprint (Research Square) |
| Word–Color Association from Large-Scale Online Data | PLoS ONE | Under Review |

---

## 🎓 Education

- **Ph.D.** Cultural Technology, KAIST (2022–2026 expected)
- **M.Eng.** Cultural Technology, KAIST (2020–2022)
- **B.Eng.** Industrial & System Engineering + Culture & Arts Software + Creative Writing, Dongguk Univ. (2015–2020)

---

## 📬 Contact

📧 wangsp0317@kaist.ac.kr
