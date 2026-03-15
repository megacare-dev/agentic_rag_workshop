# 📝 Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [1.2.0] - 2026-03-15

### 🌍 English Version — International Workshop Ready

The `en/` notebooks are now fully optimized for **international students** learning Thai Agentic RAG.

### ✨ Added

**For International Students**
- README: "For International Students" section with Thai vs English comparison table (#60)
- Thai language explainer cell at the top of every notebook (#54)
- Sample data summary table (5 case studies with topics & key points) (#55)
- Thai Quick Reference glossary — 15 common Thai words with pronunciation (#60)
- `# [EN]` paragraph-level English translations for all Thai case study data (#55)
- Inline `# "translation"` annotations for every Thai string literal (#54)

**Teaching Enhancements**
- Day 1: Explanation of why Hybrid Search matters more for Thai (alpha=0.7+) (#60)
- Day 2: Cross-language retrieval note — EN query → TH data via multilingual embeddings (#60)
- Day 3: Thai RAGAS scoring note — expected score differences vs English benchmarks (#60)
- Issue #58: Docling OCR downloads wrong language models (Chinese instead of Thai)

### 🔄 Changed

- All `print()` messages changed to English (from PR #52 by @Khantdotcom) (#57)
- All comments and docstrings in English (#54)
- All markdown cells in English (#54)
- Sample data (string literals) restored to Thai with English annotations (#54)

### 👥 Contributors

- [@Khantdotcom](https://github.com/Khantdotcom) — English translation of Thai notebooks (PRs #48, #49, #50, #51, #52)

---

## [1.1.3] - 2026-03-13

### 🐛 Fixed

**Day 2: Building Agents**
- `day2_homework.ipynb` — `chat_with_agent()` `session_service` constructor arg `InMemoryRunner` → `runner.session_service` pattern (#46)

**Day 3: Evaluation**
- `day3_evaluation.ipynb` — RAGAS evaluation cell (embedding setup, Dataset, evaluate() call, try block) parse error (#45)

---

## [1.1.2] - 2026-03-07

### 🐛 Fixed

- Heatmap □□□ — Thai font setup (Garuda) heatmap cell (#41)

---

## [1.1.1] - 2026-03-07

### 🐛 Fixed

- GitHub render `day1_data_engineering.ipynb` — `metadata.widgets` `state` key (#39)

---

## [1.1.0] - 2026-03-06

### 🎉 All Notebooks Error-Free on Colab

Notebooks 3 + Google Colab error

### 🐛 Fixed

**Day 1: Data Engineering**
- Thai font matplotlib □□□ — `fonts-thai-tlwg` + `addfont()` (#19, #23, #28)
- Similarity matrix text — matplotlib heatmap (#30, #32)

**Day 2: Building Agents**
- `InMemoryRunner` `session_service` param — `runner.session_service` (#16)
- `resp.text.strip()` → NoneType error — None check (#17)
- `chat_with_agent` tuple unpacking ValueError — return value (#16)
- `%%time` + `await` SyntaxError Colab — `%%time`

**Day 3: Evaluation**
- `InMemoryRunner` + `session_service` TypeError — `runner.session_service` (#26)
- `resp.text.strip()` NoneType — None check (#26)

### ✨ Improved

- ASCII diagrams Thai text → markdown table notebook (#21)
- Pipeline diagram Day 1 + Day 2 → 
- Similarity matrix → heatmap visualization 3 (#30)
- KMITL sample data 

### 📝 Documentation

- README: Known Issues & Fixes section (#33)
- README: + Colab note
- `.agent/workflows/git-workflow.md` — Issue → Branch → PR → Merge

---

## [1.0.0] - 2026-03-06

### 🎉 Initial Release

Workshop Agentic RAG 3 

### ✨ Added

**Workshop Notebooks**
- `day1/day1_data_engineering.ipynb` — Dedup, Chunk, Embed, Hybrid Search, Qdrant, Retrieval
- `day2/day2_building_agents.ipynb` — Agent, Tools, RAG Agent, Multi-Agent (Google ADK)
- `day3/day3_evaluation.ipynb` — RAGAS, LLM-as-Judge, A/B Testing, Capstone

**Homework Notebooks**
- `day1/day1_homework.ipynb` — Pipeline loop (10 )
- `day2/day2_homework.ipynb` — Agent + RAG Agent + Workflow (10 )
- `day3/day3_homework.ipynb` — RAG + Evaluation + Optimization (10 )
- Anti-cheat: student-specific seeded data generation
- Standardized student info: , , , LINE ID

**Grading System**
- `day1/day1_grading.ipynb` — AI grading Gemini 2.5 Pro
- `day2/day2_grading.ipynb` — Duplicate check + CSV/JSON export
- `day3/day3_grading.ipynb` — Automated scoring + download
- `final_grading.ipynb` — 3 (Responsibility/Determination/Technical) × 3 = /90

**Submission System**
- Google Form × 3 (Workshop notebook + Homework notebook upload)
- Google Drive folder structure

**Documentation**
- `README.md` — , , , , Tech Stack
- `LICENSE` — CC BY-NC-SA 4.0 (TH + EN)
- `slides_outline.md` — Slide outline 50 slides Colab + Form links

### 🐛 Fixed
- numpy binary incompatibility on Colab (#1, #2)
- Docling ONNX model file not found (#3, #4, #5)
- typer version conflict with docling
- Cell ordering in Day 1 Section 1.7-1.9 (#6, #7)
