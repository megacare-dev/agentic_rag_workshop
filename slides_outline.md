# 🎓 Slide Outline — Agentic RAG Workshop (3 Days)

---

## 🎯 Slide 0: Workshop Overview (English Day 1 English)

### Slide 0-1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- English AI English English English
- 3 English | Hands-on | Google Colab

### Slide 0-2 — Roadmap 3 English
- **Day 1: 📊 Data Engineering Pipeline**
  - English: Deduplicate → Chunk → Embed → VectorDB → Search
  - Tech: Qdrant, multilingual-e5-large, BM25, PyThaiNLP
  - 🔗 [English Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_data_engineering.ipynb)
- **Day 2: 🤖 Building Agents**
  - English AI Agent: Agent + Tools → RAG Agent → Multi-Agent
  - Tech: Google ADK, Gemini API, Session Memory
  - 🔗 [English Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_building_agents.ipynb)
- **Day 3: 📏 Evaluation & Optimization**
  - English: RAGAS, LLM-as-Judge, A/B Testing, Capstone
  - Tech: RAGAS Framework, Prompt Engineering
  - 🔗 [English Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_evaluation.ipynb)

### Slide 0-3 — English
- **3 English × 3 English = 90 English**
- 🤝 **Responsibility (10/Day)** — English, English, Run ✅ English
- 💪 **Determination (10/Day)** — English, English parameter, English, debug
- 💻 **Technical (10/Day)** — Code English, English, English copy
- English:

  | English              |  Day 1  |  Day 2  |  Day 3  |   English   |
  | ---------------- | :-----: | :-----: | :-----: | :-----: |
  | 🤝 Responsibility |   /10   |   /10   |   /10   |   /30   |
  | 💪 Determination  |   /10   |   /10   |   /10   |   /30   |
  | 💻 Technical      |   /10   |   /10   |   /10   |   /30   |
  | **English**          | **/30** | **/30** | **/30** | **/90** |

### Slide 0-4 — English
- **Google Colab** — English code English cloud (English)
- **Gemini API** — LLM (2.5 Flash / 2.5 Pro)
- **Google ADK** — English AI Agent
- **Qdrant** — Vector Database
- English:
  - Google Account
  - Gemini API Key (English) → English Colab Secrets

### Slide 0-5 — Ground Rules
- 🔗 Notebook English link (English Colab English)
- 📤 English Google Form (Download .ipynb → Upload)
- ⏰ Workshop: English → English → English
- ❓ English → English!
- ⚠️ English API Key!

### Slide 0-6 — 📤 English
- **English:** Download .ipynb English Colab → Upload English Google Form
- English (English) + English

| Day   | 🔗 English Colab                                                                                                                  | 📤 English (Google Form)                              |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------- |
| Day 1 | [day1_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_homework.ipynb) | [English Day 1](https://forms.gle/R7EXvPvUfZ286CVh8) |
| Day 2 | [day2_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_homework.ipynb) | [English Day 2](https://forms.gle/xTQ5eVNKa4fcQVKb8) |
| Day 3 | [day3_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_homework.ipynb) | [English Day 3](https://forms.gle/yLVHh4YVVt3miogm8) |

- ⚠️ English 1 English (English)
- ✅ Run "English" English!

---

## 📅 Day 1: Data Engineering Pipeline

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 1: Data Engineering Pipeline

### Slide 2 — Workshop Overview
- 3 English?
  - Day 1: Data → VectorDB (English)
  - Day 2: Agent + Tools
  - Day 3: Evaluation + Capstone
- English Pipeline: Raw → Chunk → Embed → Store → Retrieve → Answer

### Slide 3 — RAG English?
- **R**etrieval-**A**ugmented **G**eneration
- LLM English English → English "English" context English
- RAG = English + English
- English: LLM-only vs RAG

### Slide 4 — Setup
- 🔗 English Notebook: `[English Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_data_engineering.ipynb)`
- English API Key English Colab Secrets: `GOOGLE_API_KEY`
- ⚠️ English API Key!

### Slide 5 — Deduplication
- English?
- MD5/SHA256 Hash → fingerprint English
- 💡 English: Hash English = English 100%

### Slide 6 — Chunking
- English? (LLM English context limit)
- 3 English:
  - Fixed-size: English English
  - Recursive: English English
  - Semantic: English English
- 💡 English: chunk_size vs overlap tradeoff

### Slide 7 — Thai Tokenization
- English
- PyThaiNLP `word_tokenize()`
- English: "English" → ["English","English"]

### Slide 8 — Embedding
- English → Vector (English)
- Model: `multilingual-e5-large` (English)
- English: English → Vector English
- Cosine Similarity: English

### Slide 9 — Hybrid Search
- Dense Search: Embedding (English)
- Sparse Search: BM25 (English)
- Hybrid = Dense + Sparse → English
- 💡 English: Dense English synonym, Sparse English keyword

### Slide 10 — Vector Database (Qdrant)
- English DB English? → English "English" English keyword
- Qdrant: in-memory, English, English
- Collection → Points (vector + payload)

### Slide 11 — Indexing & Retrieval
- Indexing: Chunk → Embed → Store English Qdrant
- Retrieval: Query → Embed → Search → Top-K results
- English: Full Pipeline Flow

### Slide 12 — 🧪 English
- English notebook English
- English chunk_size, top_k English
- 15 English

### Slide 13 — English Day 1
- English: Dedup → Chunk → Embed → VectorDB → Search
- 💡 Key Takeaways:
  - Chunk size English RAG
  - Hybrid Search English
  - Embedding model English

### Slide 14 — English Day 1
- 🔗 English: `[English Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_homework.ipynb)`
- 📤 English: [Google Form Day 1](https://forms.gle/R7EXvPvUfZ286CVh8)
- English Pipeline English (10 English)
- Download .ipynb → Upload English Form
- Deadline: [English]

---

## 📅 Day 2: Building Agents with Google ADK

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 2: Building Agents with Google ADK

### Slide 2 — English Day 1 + Setup
- Pipeline: Raw → Chunk → Embed → VectorDB → Search
- English: English "Agent" English
- 🔗 English Notebook: `[English Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_building_agents.ipynb)`

### Slide 3 — Agent vs Chatbot
- Chatbot: English-English English script
- Agent: English → English → English → English
- English: Input → Think → Act → Observe → Answer

### Slide 4 — Google ADK
- Agent Development Kit
- English Agent English Python English
- Components: Agent + Instruction + Tools + Model

### Slide 5 — Agent English
- `LlmAgent(name, model, instruction)`
- Instruction = "English" English Agent
- English Agent

### Slide 6 — Tools (Function Tools)
- Agent English Tools
- `FunctionTool`: English Python function → Agent English
- English: English, English, English
- 💡 English: docstring English! Agent English docstring English

### Slide 7 — Gemini API Parameters
- `temperature`: English creative (0=English, 1=English)
- `top_k`, `top_p`: English
- `max_output_tokens`: English

### Slide 8 — RAG Agent
- English Agent + VectorDB English Day 1
- Tool: `search_knowledge(query)` → English Qdrant
- Agent English: English

### Slide 9 — Multi-Agent Systems
- Agent English? → English Agent English
- 4 patterns:
  - Sequential: English A → B → C
  - Parallel: English A + B + C
  - Loop: English
  - LLM Routing: AI English Agent English

### Slide 10 — Sequential vs Parallel
- Sequential: English (English → English → English)
- Parallel: English (English 3 English)
- English

### Slide 11 — Session Memory
- Agent English
- `InMemorySessionService`
- English: English Agent English context

### Slide 12 — Agentic RAG
- English: RAG + Multi-Agent + Memory
- English: Study Assistant English + English + English
- 💡 English: English RAG English = Agent English

### Slide 13 — 🧪 English
- English Agent + Custom Tool English
- 15 English

### Slide 14 — English Day 2
- Agent = AI English + English
- Multi-Agent = English Agent English
- Agentic RAG = Agent + RAG + Memory

### Slide 15 — English Day 2
- 🔗 English: `[English Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_homework.ipynb)`
- 📤 English: [Google Form Day 2](https://forms.gle/xTQ5eVNKa4fcQVKb8)
- English 4 English: Agent+Tool, RAG Agent, Workflow, English
- Download .ipynb → Upload English Form
- 10 English | Deadline: [English]

---

## 📅 Day 3: Evaluation & Optimization

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 3: Evaluation & Optimization

### Slide 2 — English Day 1-2 + Setup
- Day 1: Data → VectorDB → Search
- Day 2: Agent → RAG Agent → Multi-Agent
- Day 3: "English English?"
- 🔗 English Notebook: `[English Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_evaluation.ipynb)`

### Slide 3 — English?
- "English" ≠ "English"
- English: Hallucination, English, English
- English → English

### Slide 4 — RAGAS Metrics
- **Faithfulness**: English context English?
- **Answer Relevancy**: English?
- **Context Precision**: context English?
- **Context Recall**: English context English?
- English: 4 metrics quadrant

### Slide 5 — Auto Eval Dataset
- English Gemini
- Input: English → Output: English + English + context
- English → English

### Slide 6 — LLM-as-Judge
- English LLM English LLM
- Prompt: "English 1-5 English..."
- English: English rule English
- English: English bias, English prompt English

### Slide 7 — Agent Testing
- Tool Selection Accuracy: Agent English tool English?
- Response Quality: English?
- Test Cases: ≥ 5 English → English pass rate

### Slide 8 — A/B Testing
- English 2 configs:
  - A: chunk_size=200, top_k=3
  - B: chunk_size=500, top_k=5
- English → English
- 💡 English: English English

### Slide 9 — Prompt Engineering
- Before vs After
- English: Role, Few-shot, Chain-of-Thought, Constraints
- English: prompt English → English

### Slide 10 — Optimization Strategies
- 5 English:
  1. Chunk size / overlap
  2. Embedding model
  3. Top-K / Search method
  4. Prompt template
  5. Model parameters (temperature)
- English!

### Slide 11 — 🧪 English
- English pipeline → English Before/After
- 15 English

### Slide 12 — ⭐ Capstone Project
- English: Data + Agent + Evaluation
- English RAG Agent English
- English: English, English, Before/After

### Slide 13 — English 3 English
- Day 1: 📊 Data Engineering → English
- Day 2: 🤖 Agent Building → AI English
- Day 3: 📏 Evaluation → English
- English: Full Pipeline English

### Slide 14 — What's Next?
- Production: Deploy English Cloud Run / Vertex AI
- Advanced: Fine-tuning, Knowledge Graph, Hybrid Agent
- Community: English Issue, English PR English!

### Slide 15 — English Day 3 + English Final
- 🔗 English: `[English Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_homework.ipynb)`
- 📤 English: [Google Form Day 3](https://forms.gle/yLVHh4YVVt3miogm8)
- English 10 English | Download .ipynb → Upload English Form
- Deadline: [English]
- English 3 English × 3 English = 90 English:
  - 🤝 Responsibility (30)
  - 💪 Determination (30)
  - 💻 Technical (30)

### Slide 16 — Thank You
- _"The best way to learn AI is to build with AI."_
