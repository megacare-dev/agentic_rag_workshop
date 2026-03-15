# 🤖 Agentic RAG Workshop: From Zero to Hero

> Build RAG + AI Agent from scratch with Google ADK & Gemini

---

## 🌐 Language / ภาษา

| Language | Link |
|----------|------|
| 🇹🇭 **ภาษาไทย** (Thai) | [📖 เข้าสู่เนื้อหาภาษาไทย](th/README.md) |
| 🇬🇧 **English** | [📖 Go to English version](en/README.md) — v1.2.0 ✅ |

---

## 📋 Overview

A 3-day hands-on workshop for undergraduate students, teaching end-to-end **Retrieval-Augmented Generation (RAG)** and **AI Agent** development.

```
Day 1: Data Engineering     Day 2: Agent Building     Day 3: Evaluation
─────────────────────       ─────────────────────     ─────────────────
Raw → Chunk → Embed →       Agent + Tool →            RAGAS metrics
VectorDB → Retrieve         RAG Agent →               LLM-as-Judge
                            Multi-Agent →              A/B Experiment
                            Agentic RAG                Capstone ⭐
```

**Key Features:**
- 🇹🇭 Full Thai language support (PyThaiNLP, multilingual-e5-large)
- 🛡️ Anti-cheat homework (student-specific seeded data)
- 🤖 Automated grading with Gemini 2.5 Pro
- 💡 「Observation」blocks in every section for key takeaways
- 🧪 Exercises with hints + starter code

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| [Google ADK](https://google.github.io/adk-docs/) | AI Agent Framework |
| [Gemini API](https://ai.google.dev/) | LLM (2.5 Flash / 2.5 Pro) |
| [Qdrant](https://qdrant.tech/) | Vector Database |
| [multilingual-e5-large](https://huggingface.co/intfloat/multilingual-e5-large) | Text Embedding (Thai supported) |
| [RAGAS](https://ragas.io/) | RAG Evaluation Framework |
| [PyThaiNLP](https://pythainlp.github.io/) | Thai NLP Toolkit |
| [Google Colab](https://colab.research.google.com/) | Runtime Environment |

---

## 📁 Project Structure

```
agentic_rag_workshop/
├── README.md                  # This file (bilingual index)
├── LICENSE
├── th/                        # 🇹🇭 Thai version
│   ├── README.md
│   ├── CHANGELOG.md
│   ├── day1/                  # Data Engineering Pipeline
│   ├── day2/                  # Building Agents with Google ADK
│   ├── day3/                  # Evaluation & Optimization
│   ├── 4hr/                   # 4-hour condensed variant
│   └── final_grading.ipynb
├── en/                        # 🇬🇧 English version (v1.2.0)
│   ├── README.md
│   ├── CHANGELOG.md
│   ├── day1/                  # Data Engineering Pipeline
│   ├── day2/                  # Building Agents with Google ADK
│   ├── day3/                  # Evaluation & Optimization
│   └── 4hr/                   # 4-hour condensed variant
└── docs/                      # Landing page (GitHub Pages)
```

---

## 👤 Author

**Paripol Toopiroh (ปริพล ทู้ไพเราะห์)**
Chief Executive Officer — [Mega Wiz](https://megawiz.co)
🎓 Information Engineering, Batch 1 — Faculty of Engineering, KMITL

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/paripol-toopiroh-61273a19b/)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=flat&logo=facebook&logoColor=white)](https://www.facebook.com/paripol.toopiroh)

### 👥 Contributors

| Contributor | Role | PRs |
|:------------|:-----|:----|
| [@Khantdotcom](https://github.com/Khantdotcom) | 🇬🇧 English Translation — Translated Thai notebooks to English, enabling the international workshop version | [#48](../../pull/48), [#49](../../pull/49), [#50](../../pull/50), [#51](../../pull/51), [#52](../../pull/52) |

## 🤝 Contributing

Contributions are welcome! See each language folder for detailed contribution guidelines.

- 💬 **Suggestions** → Open an [Issue](../../issues)
- 🐛 **Bug Report** → Open an [Issue](../../issues) with reproduction steps
- 🌐 **Translation** → Create a PR adding content in `en/` folder
- 🔀 **Pull Request** → Fork → Fix → Submit PR

> All contributions are licensed under the same license (CC BY-NC-SA 4.0)

---

## 📄 License

[![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

This work is licensed under [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-nc-sa/4.0/)

- ✅ Free to use for learning and teaching
- ✅ Modify and build upon
- ✅ Credit the original author
- ❌ No commercial use

---

> _"The best way to learn AI is to build with AI."_
