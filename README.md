# 🤖 Agentic RAG Workshop: From Zero to Hero

> Build RAG + AI Agents from scratch with Google ADK & Gemini — with full Thai-language support.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Project Structure](#-project-structure)
- [Daily Curriculum](#-daily-curriculum)
- [Prerequisites](#-prerequisites)
- [Teaching Method](#-teaching-method)
- [Homework Submission](#-homework-submission)
- [Homework Grading](#-homework-grading)
- [Tech Stack](#-tech-stack)

---

## 🎯 Overview

This is a 3-day workshop for undergraduate students to learn how to build **Retrieval-Augmented Generation (RAG)** systems and **AI Agents** end-to-end.

```
Day 1: Data Engineering     Day 2: Agent Building     Day 3: Evaluation
─────────────────────       ─────────────────────     ─────────────────
Raw → Chunk → Embed →       Agent + Tool →            RAGAS metrics
VectorDB → Retrieve         RAG Agent →               LLM-as-Judge
                            Multi-Agent →             A/B Experiment
                            Agentic RAG               Capstone ⭐
```

**Highlights:**
- 🇹🇭 Full Thai-language support throughout the pipeline (PyThaiNLP, multilingual-e5-large)
- 🛡️ Anti-cheat homework design (personalized data generated from student IDs)
- 🤖 Automatic grading powered by Gemini 2.5 Pro
- 💡 "Observation" blocks in every section to summarize key ideas
- 🧪 Practice exercises with hints + starter code

---

## 📁 Project Structure

```
agentic_rag_workshop/
├── README.md
├── LICENSE
├── CHANGELOG.md                       # 📋 Change history
├── final_grading.ipynb                # 🏆 Final grading (3 dimensions × 3 days)
├── .agent/
│   └── workflows/
│       └── git-workflow.md            # 🔀 Git workflow rule (Issue → PR)
├── day1/
│   ├── day1_data_engineering.ipynb    # 📖 Lesson content (87 cells)
│   ├── day1_homework.ipynb            # 📝 Homework (18 cells)
│   └── day1_grading.ipynb             # ✅ Grading notebook (11 cells)
├── day2/
│   ├── day2_building_agents.ipynb     # 📖 Lesson content (62 cells)
│   ├── day2_homework.ipynb            # 📝 Homework (22 cells)
│   └── day2_grading.ipynb             # ✅ Grading notebook (11 cells)
└── day3/
    ├── day3_evaluation.ipynb          # 📖 Lesson content (41 cells)
    ├── day3_homework.ipynb            # 📝 Homework (18 cells)
    └── day3_grading.ipynb             # ✅ Grading notebook (11 cells)
```

---

## 📚 Daily Curriculum

### Day 1: Data Engineering Pipeline

| Section | Content |
| ------- | ------- |
| 1.1     | Deduplication — detect duplicate files with hashing |
| 1.2     | Chunking — split text (Fixed / Recursive / Semantic) |
| 1.3     | Gemini Multimodal — convert PDFs with AI |
| 1.4     | Thai Tokenization — Thai word segmentation |
| 1.5     | Embedding — convert text into vectors |
| 1.6     | Hybrid Search — Dense + Sparse search |
| 1.7     | Qdrant — Vector Database |
| 1.8     | Indexing — insert data into VectorDB |
| 1.9     | Retrieval — search and fetch relevant context |

**Homework (10 points):** Build a full pipeline from dedup → chunk → embed → search.

---

### Day 2: Building Agents with Google ADK

| Section | Content |
| ------- | ------- |
| 2.1     | First Agent — create an Agent + Instruction |
| 2.2     | Tools — Function Tools + Gemini API parameters |
| 2.3     | RAG Agent — agent that retrieves from VectorDB |
| 2.4     | Multi-Agent — Sequential / Parallel / Loop / LLM Routing |
| 2.5     | Session Memory — maintain conversation memory |
| 2.6     | Agentic RAG — complete Study Assistant system |

**Homework (10 points):** Build an Agent + Custom Tool + RAG Agent + Workflow Agent.

---

### Day 3: Evaluation & Optimization

| Section | Content |
| ------- | ------- |
| 3.1     | RAGAS — evaluate RAG quality (4 metrics) |
| 3.2     | Auto Eval Dataset — generate Q&A automatically with Gemini |
| 3.3     | Agent Testing — test quality and reliability |
| 3.4     | Prompt / Retrieval Optimization |
| 3.5     | A/B Experiment — compare before vs after |
| 3.6     | Capstone Project |

**Homework (10 points):** Build + evaluate + improve a complete RAG system, then summarize findings.

---

## 🧰 Prerequisites

1. **Google Account** (for Colab)
2. **Gemini API Key** stored in Colab Secrets as `GOOGLE_API_KEY`

---

## 🎓 Teaching Method

### Standard flow for each section

```
1. Explain the concept (Markdown cell)
2. Demonstrate the code (Code cell — run together)
3. 💡 Observation — summarize key takeaways
4. 🧪 Exercise — students practice for 5–10 minutes
```

### Estimated time

| Day   | Total Time | Breakdown |
| ----- | :--------: | --------- |
| Day 1 | ~4–5 hrs   | 3 hrs lesson + 1–2 hrs exercises |
| Day 2 | ~4–5 hrs   | 3 hrs lesson + 1–2 hrs exercises |
| Day 3 | ~3–4 hrs   | 2 hrs lesson + 1–2 hrs capstone |

### Tips

- Run `%%time` cells in advance because pip installs + model downloads take time.
- Ask students to set Colab Secrets before class starts.
- Sections that use `await` must run in Colab (not plain local Python).
- Emphasize **💡 Observation** blocks—they contain each section’s key takeaway.

---

## 📤 Homework Submission

### Submission flow

```
Students                               Instructor
──────────                             ──────────
1. Complete homework in Colab          1. Create Google Form (one-time setup)
2. Run ✅ validation checks             2. Open linked Google Sheets (auto)
3. File → Download → .ipynb            3. Download .ipynb files from Drive
4. Open Google Form                    4. Paste file path in grading notebook
5. Fill in info + upload files         5. Run grading → append to CSV
6. Submit ✅                            6. Continue grading next student
```

### Why Google Form?

| Reason | Details |
| ------ | ------- |
| **Students do not need GitHub** | Just download `.ipynb` and upload via form |
| **One link for everyone** | Share a single link via LINE/Classroom |
| **Auto spreadsheet** | Student metadata goes into Google Sheets instantly |
| **Files stored in Drive** | Uploaded files are safe and easy to download later |

### 📝 Google Form structure

Create one Google Form per day for clarity.

#### Form: "Day X Homework Submission — Agentic RAG Workshop"

| #   | Field Name | Type | Required | Notes |
| --- | ---------- | ---- | :------: | ----- |
| 1   | **Full Name** | Short text | ✅ | Validation: at least 4 characters |
| 2   | **Student ID** | Short text | ✅ | Validation: regex `^\d{10}$` (10 digits) |
| 3   | **Phone Number** | Short text | ✅ | Validation: regex `^0\d{8,9}$` |
| 4   | **LINE ID** | Short text | ❌ | Optional |
| 5   | **Email** | Short text | ✅ | Auto-collected from Google Account |
| 6   | **Lesson + Exercise file (.ipynb)** | File upload | ✅ | In-class workshop file, max 20 MB |
| 7   | **Homework file (.ipynb)** | File upload | ✅ | Homework file, max 10 MB |
| 8   | **Issues encountered** | Paragraph | ❌ | Student explains blockers/problems |

#### Google Form settings

| Setting | Value |
| ------- | ----- |
| Collect emails | ✅ Verified |
| Limit to 1 response | ✅ (editable after submit) |
| File upload destination | Drive folder: `Workshop_Submissions/DayX/` |
| Confirmation message | `✅ Submitted successfully! Results will be shared within 1 week.` |

#### 🔗 Google Form links

| Day   | Link |
| ----- | ---- |
| Day 1 | [Submit Day 1: Data Engineering](https://forms.gle/R7EXvPvUfZ286CVh8) |
| Day 2 | [Submit Day 2: Building Agents](https://forms.gle/xTQ5eVNKa4fcQVKb8) |
| Day 3 | [Submit Day 3: Evaluation & Optimization](https://forms.gle/yLVHh4YVVt3miogm8) |

---

## ✅ Homework Grading

### Steps

```
1. Open Google Sheets (linked from the Form) → download .ipynb files from Drive
2. Upload all files to Colab (or mount Google Drive)
3. Open dayX_grading.ipynb in Colab
4. Run "Setup" once (install + API key)
5. Run the grading function once
6. Paste .ipynb file path → run grading
7. Results append to CSV/JSON automatically
8. Change path → grade next student
```

### Automatic grading system

| Feature | Details |
| ------- | ------- |
| **AI Grading** | Gemini 2.5 Pro grades and provides feedback in Thai |
| **Anti-cheat** | Compare with student-ID-based personalized answer key |
| **Duplicate check** | Detect duplicate submissions and ask before overwrite |
| **Export** | CSV + JSON for importing into grading systems |

### Scoring rubric (each day = 10 points)

<details>
<summary><strong>Day 1: Data Engineering Pipeline</strong></summary>

| Task | Points |
| ---- | :----: |
| Duplicates | 2 |
| Chunking | 3 |
| Embedding + Search | 3 |
| Analysis | 2 |

</details>

<details>
<summary><strong>Day 2: Building Agents</strong></summary>

| Task | Points |
| ---- | :----: |
| Agent + Custom Tool | 3 |
| RAG Agent | 3 |
| Workflow Agent | 2 |
| Explain the results | 2 |

</details>

<details>
<summary><strong>Day 3: Evaluation & Optimization</strong></summary>

| Task | Points |
| ---- | :----: |
| RAG Pipeline | 3 |
| Quality Evaluation (LLM-as-Judge) | 2.5 |
| Improvement (Before/After) | 2.5 |
| Agent + Test | 2 |

</details>

### Output files

- `dayX_scores.csv` — Score table (can be imported to Excel/Google Sheets)
- `dayX_scores.json` — Per-student detailed feedback

---

## 🏆 Overall Evaluation Framework (3 Dimensions)

The final score uses **3 dimensions**, each worth 10 points/day × 3 days = **90 total points**.

### 🤝 Responsibility — 10 points/day

| Criteria | Points | Evidence |
| -------- | :----: | -------- |
| On-time submission | 3 | Google Form timestamp |
| Complete student information | 2 | Name, student ID, phone number |
| Submit all 3 days | 3 | Day 1 + Day 2 + Day 3 present |
| Run ✅ validation before submit | 2 | Validation cell output exists |

### 💪 Determination — 10 points/day

| Criteria | Points | Evidence |
| -------- | :----: | -------- |
| Complete all exercises | 3 | Code cells produce outputs |
| Experiment with parameters | 3 | At least 2 meaningful parameter changes |
| Explain and analyze independently | 2 | Comments explain reasoning |
| Resolve encountered issues | 2 | Debugging / error handling shown |

### 💻 Technical Skills — 10 points/day

| Criteria | Points | Evidence |
| -------- | :----: | -------- |
| Code runs correctly | 3 | No errors/tracebacks |
| Correct output | 3 | Matches personalized anti-cheat data |
| Code quality | 2 | Readable with useful comments |
| No copy/paste / no full AI replacement | 2 | AI-suspected behavior checks |

### 📊 Summary table

| Dimension | Day 1 | Day 2 | Day 3 | Total |
| --------- | :---: | :---: | :---: | :---: |
| 🤝 Responsibility | /10 | /10 | /10 | /30 |
| 💪 Determination | /10 | /10 | /10 | /30 |
| 💻 Technical | /10 | /10 | /10 | /30 |
| **Per-day subtotal** | **/30** | **/30** | **/30** | **/90** |

> Use `final_grading.ipynb` to aggregate all three dimensions across all days, then export final CSV.

---

## 🐛 Known Issues & Fixes (Colab)

Issues found and fixed while running on Google Colab:

| Issue | Problem | Fix | Notebook |
| :---: | ------- | --- | -------- |
| [#19](../../issues/19) | Thai fonts in matplotlib rendered as □□□ | Install `fonts-thai-tlwg` + use `addfont()` | Day 1 |
| [#21](../../issues/21) | ASCII diagrams were misaligned due to Thai character width | Replaced with markdown tables | Day 1, 2 |
| [#26](../../issues/26) | `InMemoryRunner` does not accept `session_service` parameter | Use `runner.session_service` | Day 2, 3 |
| [#17](../../issues/17) | `resp.text.strip()` raised NoneType error | Add `None` check | Day 2, 3 |
| [#30](../../issues/30) | Similarity matrix text layout was misaligned | Replaced with matplotlib heatmap | Day 1 |

> ⚠️ **Note**: All notebooks are designed for **Google Colab**. If you run locally, you may need to adjust paths and install extra dependencies.

## 🛠️ Tech Stack

| Tool | Purpose |
| ---- | ------- |
| [Google ADK](https://google.github.io/adk-docs/) | Build AI Agents |
| [Gemini API](https://ai.google.dev/) | LLM (2.5 Flash / 2.5 Pro) |
| [Qdrant](https://qdrant.tech/) | Vector Database |
| [multilingual-e5-large](https://huggingface.co/intfloat/multilingual-e5-large) | Text Embedding (Thai-capable) |
| [RAGAS](https://ragas.io/) | RAG Evaluation Framework |
| [PyThaiNLP](https://pythainlp.github.io/) | Thai NLP Toolkit |
| [Google Colab](https://colab.research.google.com/) | Runtime Environment |

---

## 👤 Author

**Paripol Toopiroh**
Chief Executive Officer — [Mega Wiz](https://megawiz.co)
🎓 Information Engineering (Class 1), Faculty of Engineering, King Mongkut's Institute of Technology Ladkrabang (KMITL)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/paripol-toopiroh-61273a19b/)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=flat&logo=facebook&logoColor=white)](https://www.facebook.com/paripol.toopiroh)

### 🛠️ Creation Tools

| Tool | Description |
| ---- | ----------- |
| **IDE** | [Antigravity](https://antigravity.dev) |
| **AI Model** | Claude Opus 4.6 (Thinking) |

---

## 🤝 Contributing

Feedback and contributions are very welcome.

- 💬 **Suggestions** → Open an [Issue](../../issues)
- 🐛 **Bug reports** → Open an [Issue](../../issues) with reproduction steps
- 🔀 **Pull Requests** → Fork → Edit → Submit PR

> All contributions are shared under the same license (CC BY-NC-SA 4.0).

---

## 📄 License

[![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

This work is licensed under [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-nc-sa/4.0/).

- ✅ Free for learning and teaching
- ✅ You can adapt and build upon it
- ✅ Attribution is required
- ❌ Commercial use is not allowed

See [LICENSE](LICENSE) for full details.

---

> _"The best way to learn AI is to build with AI."_
