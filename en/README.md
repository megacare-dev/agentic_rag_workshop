````md
# 🤖 Agentic RAG Workshop: From Zero to Hero

> Build RAG + AI Agents from scratch with Google ADK & Gemini — with Thai language support

---

## 📋 Table of Contents

- [Overview](#-overview)
- [File Structure](#-file-structure)
- [Content by Day](#-content-by-day)
- [Requirements](#-requirements)
- [Teaching Approach](#-teaching-approach)
- [Homework Submission](#-homework-submission)
- [Homework Grading](#-homework-grading)
- [Tech Stack](#-tech-stack)

---

## 🎯 Overview

A 3-day workshop for undergraduate students on building **Retrieval-Augmented Generation (RAG)** and **AI Agents** end-to-end.

```text
Day 1: Data Engineering     Day 2: Agent Building     Day 3: Evaluation
─────────────────────       ─────────────────────     ─────────────────
Raw → Chunk → Embed →       Agent + Tool →            RAGAS metrics
VectorDB → Retrieve         RAG Agent →               LLM-as-Judge
                            Multi-Agent →             A/B Experiment
                            Agentic RAG               Capstone ⭐
````

**Highlights:**

* 🇹🇭 Thai language support throughout the pipeline (PyThaiNLP, multilingual-e5-large)
* 🛡️ Anti-cheat homework (personalized data derived from student ID)
* 🤖 Automated homework grading with Gemini 2.5 Pro
* 💡 Includes 「Observation」blocks in every section to summarize key ideas
* 🧪 Exercises with hints + starter code

---

## 📁 File Structure

```text
agentic_rag_workshop/
├── README.md
├── LICENSE
├── CHANGELOG.md                       # 📋 Change log
├── final_grading.ipynb                # 🏆 Final grading (3 dimensions × 3 days)
├── .agent/
│   └── workflows/
│       └── git-workflow.md            # 🔀 Git workflow rule (Issue → PR)
├── day1/
│   ├── day1_data_engineering.ipynb    # 📖 Lesson content (87 cells)
│   ├── day1_homework.ipynb            # 📝 Homework (18 cells)
│   └── day1_grading.ipynb             # ✅ Homework grading (11 cells)
├── day2/
│   ├── day2_building_agents.ipynb     # 📖 Lesson content (62 cells)
│   ├── day2_homework.ipynb            # 📝 Homework (22 cells)
│   └── day2_grading.ipynb             # ✅ Homework grading (11 cells)
└── day3/
    ├── day3_evaluation.ipynb          # 📖 Lesson content (41 cells)
    ├── day3_homework.ipynb            # 📝 Homework (18 cells)
    └── day3_grading.ipynb             # ✅ Homework grading (11 cells)
```

---

## 📚 Content by Day

### Day 1: Data Engineering Pipeline

| Section | Content                                              |
| ------- | ---------------------------------------------------- |
| 1.1     | Deduplication — Detect duplicate files with hashes   |
| 1.2     | Chunking — Split text (Fixed / Recursive / Semantic) |
| 1.3     | Gemini Multimodal — Convert PDFs with AI             |
| 1.4     | Thai Tokenization — Thai word segmentation           |
| 1.5     | Embedding — Convert text into vectors                |
| 1.6     | Hybrid Search — Dense + Sparse search                |
| 1.7     | Qdrant — Vector Database                             |
| 1.8     | Indexing — Insert data into VectorDB                 |
| 1.9     | Retrieval — Search for information                   |

**Homework (10 points):** Build a complete pipeline from dedup → chunk → embed → search

---

### Day 2: Building Agents with Google ADK

| Section | Content                                                  |
| ------- | -------------------------------------------------------- |
| 2.1     | First Agent — Build an agent + instruction               |
| 2.2     | Tools — Function Tools + Gemini API parameters           |
| 2.3     | RAG Agent — An agent that searches from VectorDB         |
| 2.4     | Multi-Agent — Sequential / Parallel / Loop / LLM Routing |
| 2.5     | Session Memory — Remember conversation context           |
| 2.6     | Agentic RAG — A full study assistant                     |

**Homework (10 points):** Build an agent + custom tool + RAG agent + workflow agent

---

### Day 3: Evaluation & Optimization

| Section | Content                                                        |
| ------- | -------------------------------------------------------------- |
| 3.1     | RAGAS — Measure RAG quality (4 metrics)                        |
| 3.2     | Auto Eval Dataset — Automatically generate Q&A with Gemini     |
| 3.3     | Agent Testing — Tool Selection + LLM-as-Judge                  |
| 3.4     | A/B Experiment — Compare configurations                        |
| 3.5     | Prompt Engineering — Before vs After                           |
| 3.6     | Capstone Project ⭐ — Bring together everything from all 3 days |

**Homework (10 points):** Build RAG + evaluate quality + improve it + build an agent + test it

---

## 🔧 Requirements

### For Instructors

1. **Gemini API Key** — Get one from [Google AI Studio](https://aistudio.google.com/apikey)
2. Upload the notebooks to Google Colab
3. Share sample data (PDFs) with students (Day 1)
4. **Create a Google Form** for homework submission (see [Homework Submission](#-homework-submission))
5. 📊 **[Teaching slides](https://docs.google.com/presentation/d/1298peeshWiNPr2JMUTdu1y2A-nuWpGo0N62i25_lvnc/edit)** — ready-to-use Google Slides

### For Students

1. **Google Account** (for Colab)
2. **Gemini API Key** — store it in Colab Secrets under the name `GOOGLE_API_KEY`

---

## 🎓 Teaching Approach

### Suggested flow for each section

```text
1. Explain the concept (Markdown cell)
2. Demonstrate the code (Code cell — run together)
3. 💡 Observation — summarize key takeaways
4. 🧪 Exercise — let students try for 5–10 minutes
```

### Estimated time

| Day   | Total Time | Breakdown                         |
| ----- | :--------: | --------------------------------- |
| Day 1 |  ~4–5 hrs  | 3 hrs content + 1–2 hrs exercises |
| Day 2 |  ~4–5 hrs  | 3 hrs content + 1–2 hrs exercises |
| Day 3 |  ~3–4 hrs  | 2 hrs content + 1–2 hrs capstone  |

### Tips

* Run `%%time` cells in advance because pip installs + model downloads take time
* Have students set up Colab Secrets before starting
* Sections using `await` must be run in Colab (not local Python)
* Emphasize the **💡 Observation** blocks — they contain the key takeaways of each section

---

## 📤 Homework Submission

### Flow

```text
Students                              Instructor
──────────                            ──────────
1. Complete homework in Colab         1. Create Google Form (once)
2. Run ✅ to verify answers           2. Open Google Sheets (auto)
3. File → Download → .ipynb          3. Download .ipynb files from Drive
4. Open Google Form                  4. Paste file path into grading notebook
5. Fill in info + upload files       5. Run grading → results append to CSV
6. Submit ✅                         6. Grade the next student
```

### Why use Google Forms?

| Reason                          | Details                                                      |
| ------------------------------- | ------------------------------------------------------------ |
| **Students do not need GitHub** | Just download `.ipynb` → upload to the form                  |
| **One link for everyone**       | Share a single link via LINE/Classroom                       |
| **Auto Spreadsheet**            | Student info goes directly into Google Sheets                |
| **Files stored in Drive**       | Uploaded files are safely stored and can be downloaded later |

### 📝 Google Form Structure

Create 1 Google Form per day for clarity:

#### Form: "Day X Homework Submission — Agentic RAG Workshop"

| # | Field Name                          | Type        | Required | Notes                                                |
| - | ----------------------------------- | ----------- | :------: | ---------------------------------------------------- |
| 1 | **Full Name**                       | Short text  |     ✅    | Validation: ≥ 4 characters                           |
| 2 | **Student ID**                      | Short text  |     ✅    | Validation: regex `^\d{10}$` (10 digits)             |
| 3 | **Phone Number**                    | Short text  |     ✅    | Validation: regex `^0\d{8,9}$`                       |
| 4 | **LINE ID**                         | Short text  |     ❌    |                                                      |
| 5 | **Email**                           | Short text  |     ✅    | Auto-collected from Google Account                   |
| 6 | **Lesson + exercise file (.ipynb)** | File upload |     ✅    | Workshop notebook completed during class, Max: 20 MB |
| 7 | **Homework file (.ipynb)**          | File upload |     ✅    | Homework file, Max: 10 MB                            |
| 8 | **Problems encountered**            | Paragraph   |     ❌    | Let students describe where they got stuck           |

#### Google Form Settings

| Setting                 | Value                                                                     |
| ----------------------- | ------------------------------------------------------------------------- |
| Collect emails          | ✅ Verified                                                                |
| Limit to 1 response     | ✅ (editable after submission)                                             |
| File upload destination | Create a Drive folder: `Workshop_Submissions/DayX/`                       |
| Confirmation message    | `✅ Submission received! Grading results will be announced within 1 week.` |

#### 🔗 Google Form Links

| Day   | Link                                                                                    |
| ----- | --------------------------------------------------------------------------------------- |
| Day 1 | [Submit Day 1 Homework: Data Engineering](https://forms.gle/R7EXvPvUfZ286CVh8)          |
| Day 2 | [Submit Day 2 Homework: Building Agents](https://forms.gle/xTQ5eVNKa4fcQVKb8)           |
| Day 3 | [Submit Day 3 Homework: Evaluation & Optimization](https://forms.gle/yLVHh4YVVt3miogm8) |

---

## ✅ Homework Grading

### Steps

```text
1. Open Google Sheets (linked from the Form) → download .ipynb files from Drive
2. Upload all files to Colab (or mount Google Drive)
3. Open dayX_grading.ipynb in Colab
4. Run "Setup" once (install + API Key)
5. Run the "grading functions" once
6. Paste the path of the .ipynb file → run grading
7. Results will be appended automatically to CSV/JSON
8. Change the path → grade the next student
```

### Automated Grading System

| Feature             | Details                                                           |
| ------------------- | ----------------------------------------------------------------- |
| **AI Grading**      | Gemini 2.5 Pro grades and provides feedback in Thai               |
| **Anti-cheat**      | Compares results against the answer key generated from student ID |
| **Duplicate check** | Detects duplicates + asks before overwrite                        |
| **Export**          | CSV + JSON for importing into grade systems                       |

### Scoring Criteria (each day = 10 points)

<details>
<summary><strong>Day 1: Data Engineering Pipeline</strong></summary>

| Step               | Points |
| ------------------ | :----: |
| Duplicates         |    2   |
| Chunking           |    3   |
| Embedding + Search |    3   |
| Analysis           |    2   |

</details>

<details>
<summary><strong>Day 2: Building Agents</strong></summary>

| Step                | Points |
| ------------------- | :----: |
| Agent + Custom Tool |    3   |
| RAG Agent           |    3   |
| Workflow Agent      |    2   |
| Explain Results     |    2   |

</details>

<details>
<summary><strong>Day 3: Evaluation & Optimization</strong></summary>

| Step                              | Points |
| --------------------------------- | :----: |
| RAG Pipeline                      |    3   |
| Quality Evaluation (LLM-as-Judge) |   2.5  |
| Improvement (Before/After)        |   2.5  |
| Agent + Test                      |    2   |

</details>

### Output Files

* `dayX_scores.csv` — score table (can be imported into Excel/Google Sheets)
* `dayX_scores.json` — detailed feedback per student

---

## 🏆 Overall Grading Criteria (3 Dimensions)

Final scores are measured across **3 dimensions**, each worth 10 points × 3 days = **90 total points**

### 🤝 Responsibility — 10 points/day

| Criteria                             | Points | Measured From                       |
| ------------------------------------ | :----: | ----------------------------------- |
| Submit on time                       |    3   | Timestamp in Google Form            |
| Fill in all required info            |    2   | Complete name, ID, and phone number |
| Submit all 3 days                    |    3   | Submitted Day 1 + 2 + 3             |
| Run ✅ verification before submission |    2   | Output from validation cell exists  |

### 💪 Determination — 10 points/day

| Criteria                               | Points | Measured From                          |
| -------------------------------------- | :----: | -------------------------------------- |
| Complete all exercises                 |    3   | Code cells contain output              |
| Try adjusting parameters independently |    3   | Changed values in ≥ 2 ways             |
| Explain/analyze in their own words     |    2   | Includes comments explaining reasoning |
| Solve problems encountered             |    2   | Includes debugging / error handling    |

### 💻 Technical — 10 points/day

| Criteria                             | Points | Measured From                          |
| ------------------------------------ | :----: | -------------------------------------- |
| Code runs successfully               |    3   | No error/traceback                     |
| Correct results                      |    3   | Matches personalized data (anti-cheat) |
| Code quality                         |    2   | Readable and includes comments         |
| No copying / no AI doing it for them |    2   | AI suspicion check                     |

### 📊 Summary Table

| Dimension         |  Day 1  |  Day 2  |  Day 3  |  Total  |
| ----------------- | :-----: | :-----: | :-----: | :-----: |
| 🤝 Responsibility |   /10   |   /10   |   /10   |   /30   |
| 💪 Determination  |   /10   |   /10   |   /10   |   /30   |
| 💻 Technical      |   /10   |   /10   |   /10   |   /30   |
| **Total per Day** | **/30** | **/30** | **/30** | **/90** |

> Use `final_grading.ipynb` to combine all 3 dimensions from every day → export the final CSV

---

## 🐛 Known Issues & Fixes (Colab)

Issues found and fixed when running on Google Colab:

|          Issue         | Problem                                                  | Fix                                 | Notebook |
| :--------------------: | -------------------------------------------------------- | ----------------------------------- | -------- |
| [#19](../../issues/19) | Thai font in matplotlib displays as □□□                  | Use `fonts-thai-tlwg` + `addfont()` | Day 1    |
| [#21](../../issues/21) | ASCII diagrams break because of Thai character width     | Replaced with markdown tables       | Day 1, 2 |
| [#26](../../issues/26) | `InMemoryRunner` does not accept `session_service` param | Use `runner.session_service`        | Day 2, 3 |
| [#17](../../issues/17) | `resp.text.strip()` → NoneType error                     | Added a None check                  | Day 2, 3 |
| [#30](../../issues/30) | Similarity matrix text alignment is incorrect            | Replaced with a matplotlib heatmap  | Day 1    |

> ⚠️ **Note**: All notebooks are designed for **Google Colab** — if you run them locally, you may need to adjust paths and dependencies.

---

## 🛠️ Tech Stack

| Tool                                                                           | Purpose                        |
| ------------------------------------------------------------------------------ | ------------------------------ |
| [Google ADK](https://google.github.io/adk-docs/)                               | Build AI agents                |
| [Gemini API](https://ai.google.dev/)                                           | LLM (2.5 Flash / 2.5 Pro)      |
| [Qdrant](https://qdrant.tech/)                                                 | Vector Database                |
| [multilingual-e5-large](https://huggingface.co/intfloat/multilingual-e5-large) | Text Embedding (supports Thai) |
| [RAGAS](https://ragas.io/)                                                     | RAG Evaluation Framework       |
| [PyThaiNLP](https://pythainlp.github.io/)                                      | Thai NLP Toolkit               |
| [Google Colab](https://colab.research.google.com/)                             | Runtime Environment            |

---

## 👤 Author

**Paripol Toopiroh**
Chief Executive Officer — [Mega Wiz](https://megawiz.co)
🎓 Information Engineering, Class 1 — Faculty of Engineering, King Mongkut’s Institute of Technology Ladkrabang (KMITL)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat\&logo=linkedin\&logoColor=white)](https://www.linkedin.com/in/paripol-toopiroh-61273a19b/)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=flat\&logo=facebook\&logoColor=white)](https://www.facebook.com/paripol.toopiroh)

### 🛠️ Tools Used to Create This

| Tool         | Details                                |
| ------------ | -------------------------------------- |
| **IDE**      | [Antigravity](https://antigravity.dev) |
| **AI Model** | Claude Opus 4.6 (Thinking)             |

---

## 🤝 Contributing

Feedback and contributions are very welcome!

* 💬 **Suggestions** → Feel free to open an [Issue](../../issues)
* 🐛 **Found a bug** → Open an [Issue](../../issues) and include reproduction steps
* 🔀 **Pull Request** → Fork → Edit → Submit a PR

> All contributions will be released under the same license (CC BY-NC-SA 4.0)

---

## 📄 License

[![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

This work is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-nc-sa/4.0/).

* ✅ Free to use for learning and teaching
* ✅ Can be adapted and extended
* ✅ Must credit the original creator
* ❌ Cannot be sold or used commercially

See [LICENSE](LICENSE) for more details.

---

> *"The best way to learn AI is to build with AI."*

```

A couple of wording upgrades I already made:
- “Google Form” → sometimes “Google Forms” where it sounds more natural in English
- “automated homework grading” instead of “automatic”
- cleaner headings and a more GitHub-native tone

Paste this directly into `README.md`.
```
