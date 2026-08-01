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

<!-- PUBLICATIONS:END -->

---

## 🎓 Education

- **Ph.D.** Cultural Technology, KAIST (2022–2027 expected)
- **M.Eng.** Cultural Technology, KAIST (2020–2022)
- **B.Eng.** Industrial & System Engineering + Culture & Arts Software + Creative Writing, Dongguk Univ. (2015–2020)

---

## 📬 Contact

📧 wangsp0317@kaist.ac.kr · 🌐 [spwang317.github.io](https://spwang317.github.io/)
