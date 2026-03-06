# 📝 Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [1.1.0] - 2026-03-06

### 🎉 All Notebooks Error-Free on Colab

Notebooks ทั้ง 3 วัน + แบบฝึกหัด ผ่านการทดสอบบน Google Colab ไม่มี error

### 🐛 Fixed

**Day 1: Data Engineering**
- Thai font ใน matplotlib แสดงเป็น □□□ — ใช้ `fonts-thai-tlwg` + `addfont()` (#19, #23, #28)
- Similarity matrix text ไม่ตรง — เปลี่ยนเป็น matplotlib heatmap (#30, #32)

**Day 2: Building Agents**
- `InMemoryRunner` ไม่รับ `session_service` param — ใช้ `runner.session_service` (#16)
- `resp.text.strip()` → NoneType error — เพิ่ม None check (#17)
- `chat_with_agent` tuple unpacking ValueError — แก้ return value (#16)
- `%%time` + `await` SyntaxError บน Colab — ลบ `%%time`

**Day 3: Evaluation**
- `InMemoryRunner` + `session_service` TypeError — ใช้ `runner.session_service` (#26)
- `resp.text.strip()` NoneType — เพิ่ม None check (#26)

### ✨ Improved

- ASCII diagrams กับ Thai text → เปลี่ยนเป็น markdown table ทุก notebook (#21)
- Pipeline diagram Day 1 + Day 2 → จัดให้ตรงและสวยงาม
- Similarity matrix → heatmap visualization 3 ช่อง (#30)
- เพิ่มข้อมูล KMITL ใน sample data ทุกวัน

### 📝 Documentation

- README: เพิ่ม Known Issues & Fixes section (#33)
- README: อัพเดทโครงสร้างไฟล์ + Colab note
- เพิ่ม `.agent/workflows/git-workflow.md` — บังคับ Issue → Branch → PR → Merge

---

## [1.0.0] - 2026-03-06

### 🎉 Initial Release

Workshop สอน Agentic RAG ครบ 3 วัน พร้อมระบบตรวจการบ้านอัตโนมัติ

### ✨ Added

**Workshop Notebooks**
- `day1/day1_data_engineering.ipynb` — Dedup, Chunk, Embed, Hybrid Search, Qdrant, Retrieval
- `day2/day2_building_agents.ipynb` — Agent, Tools, RAG Agent, Multi-Agent (Google ADK)
- `day3/day3_evaluation.ipynb` — RAGAS, LLM-as-Judge, A/B Testing, Capstone

**Homework Notebooks**
- `day1/day1_homework.ipynb` — Pipeline ครบ loop (10 คะแนน)
- `day2/day2_homework.ipynb` — Agent + RAG Agent + Workflow (10 คะแนน)
- `day3/day3_homework.ipynb` — RAG + Evaluation + Optimization (10 คะแนน)
- Anti-cheat: student-specific seeded data generation
- Standardized student info: ชื่อ, รหัส, เบอร์โทร, LINE ID

**Grading System**
- `day1/day1_grading.ipynb` — AI grading ด้วย Gemini 2.5 Pro
- `day2/day2_grading.ipynb` — Duplicate check + CSV/JSON export
- `day3/day3_grading.ipynb` — Automated scoring + download
- `final_grading.ipynb` — 3 ด้าน (Responsibility/Determination/Technical) × 3 วัน = /90

**Submission System**
- Google Form × 3 วัน (Workshop notebook + Homework notebook upload)
- Google Drive folder structure

**Documentation**
- `README.md` — ภาพรวม, โครงสร้าง, วิธีสอน, เกณฑ์คะแนน, Tech Stack
- `LICENSE` — CC BY-NC-SA 4.0 (TH + EN)
- `slides_outline.md` — Slide outline 50 slides พร้อม Colab + Form links

### 🐛 Fixed
- numpy binary incompatibility on Colab (#1, #2)
- Docling ONNX model file not found (#3, #4, #5)
- typer version conflict with docling
- Cell ordering in Day 1 Section 1.7-1.9 (#6, #7)
