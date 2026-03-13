# 📝 Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [1.1.2] - 2026-03-07

### 🐛 Fixed

- Heatmap English □□□ — English Thai font setup (Garuda) English heatmap cell (#41)

---

## [1.1.1] - 2026-03-07

### 🐛 Fixed

- GitHub English render `day1_data_engineering.ipynb` — `metadata.widgets` English `state` key (#39)

---

## [1.1.0] - 2026-03-06

### 🎉 All Notebooks Error-Free on Colab

Notebooks English 3 English + English English Google Colab English error

### 🐛 Fixed

**Day 1: Data Engineering**
- Thai font English matplotlib English □□□ — English `fonts-thai-tlwg` + `addfont()` (#19, #23, #28)
- Similarity matrix text English — English matplotlib heatmap (#30, #32)

**Day 2: Building Agents**
- `InMemoryRunner` English `session_service` param — English `runner.session_service` (#16)
- `resp.text.strip()` → NoneType error — English None check (#17)
- `chat_with_agent` tuple unpacking ValueError — English return value (#16)
- `%%time` + `await` SyntaxError English Colab — English `%%time`

**Day 3: Evaluation**
- `InMemoryRunner` + `session_service` TypeError — English `runner.session_service` (#26)
- `resp.text.strip()` NoneType — English None check (#26)

### ✨ Improved

- ASCII diagrams English Thai text → English markdown table English notebook (#21)
- Pipeline diagram Day 1 + Day 2 → English
- Similarity matrix → heatmap visualization 3 English (#30)
- English KMITL English sample data English

### 📝 Documentation

- README: English Known Issues & Fixes section (#33)
- README: English + Colab note
- English `.agent/workflows/git-workflow.md` — English Issue → Branch → PR → Merge

---

## [1.0.0] - 2026-03-06

### 🎉 Initial Release

Workshop English Agentic RAG English 3 English English

### ✨ Added

**Workshop Notebooks**
- `day1/day1_data_engineering.ipynb` — Dedup, Chunk, Embed, Hybrid Search, Qdrant, Retrieval
- `day2/day2_building_agents.ipynb` — Agent, Tools, RAG Agent, Multi-Agent (Google ADK)
- `day3/day3_evaluation.ipynb` — RAGAS, LLM-as-Judge, A/B Testing, Capstone

**Homework Notebooks**
- `day1/day1_homework.ipynb` — Pipeline English loop (10 English)
- `day2/day2_homework.ipynb` — Agent + RAG Agent + Workflow (10 English)
- `day3/day3_homework.ipynb` — RAG + Evaluation + Optimization (10 English)
- Anti-cheat: student-specific seeded data generation
- Standardized student info: English, English, English, LINE ID

**Grading System**
- `day1/day1_grading.ipynb` — AI grading English Gemini 2.5 Pro
- `day2/day2_grading.ipynb` — Duplicate check + CSV/JSON export
- `day3/day3_grading.ipynb` — Automated scoring + download
- `final_grading.ipynb` — 3 English (Responsibility/Determination/Technical) × 3 English = /90

**Submission System**
- Google Form × 3 English (Workshop notebook + Homework notebook upload)
- Google Drive folder structure

**Documentation**
- `README.md` — English, English, English, English, Tech Stack
- `LICENSE` — CC BY-NC-SA 4.0 (TH + EN)
- `slides_outline.md` — Slide outline 50 slides English Colab + Form links

### 🐛 Fixed
- numpy binary incompatibility on Colab (#1, #2)
- Docling ONNX model file not found (#3, #4, #5)
- typer version conflict with docling
- Cell ordering in Day 1 Section 1.7-1.9 (#6, #7)
