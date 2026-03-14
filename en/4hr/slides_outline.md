# 🎓 Slide Outline — Agentic RAG Workshop (3 Days)

---

## 🎯 Slide 0: Workshop Overview (Used to open Day 1 before starting the main content)

### Slide 0-1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Build AI systems that can search, reason, and answer on their own
- 3 Days | Hands-on | Google Colab

### Slide 0-2 — 3-Day Roadmap
- **Day 1: 📊 Data Engineering Pipeline**
  - Prepare data for use: Deduplicate → Chunk → Embed → VectorDB → Search
  - Tech: Qdrant, multilingual-e5-large, BM25, PyThaiNLP
  - 🔗 [Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_data_engineering.ipynb)
- **Day 2: 🤖 Building Agents**
  - Build AI Agents: Agent + Tools → RAG Agent → Multi-Agent
  - Tech: Google ADK, Gemini API, Session Memory
  - 🔗 [Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_building_agents.ipynb)
- **Day 3: 📏 Evaluation & Optimization**
  - Measure and improve: RAGAS, LLM-as-Judge, A/B Testing, Capstone
  - Tech: RAGAS Framework, Prompt Engineering
  - 🔗 [Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_evaluation.ipynb)

### Slide 0-3 — Grading Criteria
- **3 dimensions × 3 days = 90 points**
- 🤝 **Responsibility (10/Day)** — Submit on time, complete information, Run ✅ before submission
- 💪 **Determination (10/Day)** — Complete the work, try different parameters, explain, debug
- 💻 **Technical (10/Day)** — Code works, results are correct, no copying
- Table:

  | Dimension          | Day 1 | Day 2 | Day 3 | Total |
  | ------------------ | :---: | :---: | :---: | :---: |
  | 🤝 Responsibility  |  /10  |  /10  |  /10  |  /30  |
  | 💪 Determination   |  /10  |  /10  |  /10  |  /30  |
  | 💻 Technical       |  /10  |  /10  |  /10  |  /30  |
  | **Total**          | **/30** | **/30** | **/30** | **/90** |

### Slide 0-4 — Tools Used
- **Google Colab** — Write code in the cloud (no need to install anything locally)
- **Gemini API** — LLM (2.5 Flash / 2.5 Pro)
- **Google ADK** — Build AI Agents
- **Qdrant** — Vector Database
- What you need to prepare:
  - Google Account
  - Gemini API Key (free) → put it in Colab Secrets

### Slide 0-5 — Ground Rules
- 🔗 Notebooks will be shared via link (can be opened directly in Colab)
- 📤 Submit homework through Google Form (Download .ipynb → Upload)
- ⏰ Workshop flow: Learn → Practice → Do homework
- ❓ If you have questions → feel free to raise your hand anytime!
- ⚠️ Do not share your API Key!

### Slide 0-6 — 📤 Homework Submission
- **How to submit:** Download the .ipynb file from Colab → Upload it to the Google Form
- Submit both the exercise notebook and the homework notebook

| Day   | 🔗 Open Homework in Colab                                                                                                              | 📤 Submit Homework (Google Form)                         |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------- |
| Day 1 | [day1_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_homework.ipynb) | [Submit Day 1 Homework](https://forms.gle/R7EXvPvUfZ286CVh8) |
| Day 2 | [day2_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_homework.ipynb) | [Submit Day 2 Homework](https://forms.gle/xTQ5eVNKa4fcQVKb8) |
| Day 3 | [day3_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_homework.ipynb) | [Submit Day 3 Homework](https://forms.gle/yLVHh4YVVt3miogm8) |

- ⚠️ You can submit only once (but edits after submission are allowed)
- ✅ Run "Check Answers" before submitting every time!

---

## 📅 Day 1: Data Engineering Pipeline

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 1: Data Engineering Pipeline

### Slide 2 — Workshop Overview
- What will we learn in these 3 days?
  - Day 1: Data → VectorDB (today)
  - Day 2: Agent + Tools
  - Day 3: Evaluation + Capstone
- Pipeline overview: Raw → Chunk → Embed → Store → Retrieve → Answer

### Slide 3 — What Is RAG?
- **R**etrieval-**A**ugmented **G**eneration
- LLMs are powerful, but they do not know our data → we need to provide context
- RAG = Retrieval + Answer Generation
- Comparison visual: LLM-only vs RAG

### Slide 4 — Setup
- 🔗 Open Notebook: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_data_engineering.ipynb)`
- Set API Key in Colab Secrets: `GOOGLE_API_KEY`
- ⚠️ Do not share your API Key!

### Slide 5 — Deduplication
- Why do we need to detect duplicate files?
- MD5/SHA256 Hash → fingerprint of a file
- 💡 Key idea: Same hash = exactly the same content

### Slide 6 — Chunking
- Why do we need to split text? (LLMs have context limits)
- 3 methods:
  - Fixed-size: simple, but may split in the middle of a sentence
  - Recursive: smarter, splits by structure
  - Semantic: best, splits based on meaning
- 💡 Key idea: chunk_size vs overlap is a tradeoff

### Slide 7 — Thai Tokenization
- Thai does not have spaces between words
- PyThaiNLP `word_tokenize()`
- Example: "สวัสดีครับ" → ["สวัสดี","ครับ"]

### Slide 8 — Embedding
- Convert text → Vector (numbers)
- Model: `multilingual-e5-large` (supports Thai)
- Visual: similar texts → similar vectors
- Cosine Similarity: measures similarity

### Slide 9 — Hybrid Search
- Dense Search: Embedding-based (understands meaning)
- Sparse Search: BM25 (matches exact words)
- Hybrid = Dense + Sparse → best of both
- 💡 Key idea: Dense is good at synonyms, Sparse is good at keywords

### Slide 10 — Vector Database (Qdrant)
- Why not use a normal database? → We want to search by "meaning," not just keywords
- Qdrant: in-memory, fast, easy to use
- Collection → Points (vector + payload)

### Slide 11 — Indexing & Retrieval
- Indexing: Chunk → Embed → Store in Qdrant
- Retrieval: Query → Embed → Search → Top-K results
- Visual: Full Pipeline Flow

### Slide 12 — 🧪 Exercise
- Try it yourself in the notebook
- Adjust `chunk_size`, `top_k` and observe the differences
- 15 minutes

### Slide 13 — Day 1 Summary
- Today you learned: Dedup → Chunk → Embed → VectorDB → Search
- 💡 Key Takeaways:
  - Chunk size affects RAG quality
  - Hybrid Search is better than using only one method
  - The embedding model must support Thai

### Slide 14 — Day 1 Homework
- 🔗 Open homework: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_homework.ipynb)`
- 📤 Submit homework: [Google Form Day 1](https://forms.gle/R7EXvPvUfZ286CVh8)
- Build the pipeline yourself (10 points)
- Download .ipynb → Upload to the Form
- Deadline: [Specify]

---

## 📅 Day 2: Building Agents with Google ADK

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 2: Building Agents with Google ADK

### Slide 2 — Review Day 1 + Setup
- Pipeline: Raw → Chunk → Embed → VectorDB → Search
- Today: add an "Agent" that can reason on its own
- 🔗 Open Notebook: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_building_agents.ipynb)`

### Slide 3 — Agent vs Chatbot
- Chatbot: question-answering based on a script
- Agent: think → decide → use tools → answer
- Visual: Input → Think → Act → Observe → Answer

### Slide 4 — Google ADK
- Agent Development Kit
- Build agents with just a few lines of Python
- Components: Agent + Instruction + Tools + Model

### Slide 5 — First Agent
- `LlmAgent(name, model, instruction)`
- Instruction = the Agent’s "personality"
- Try chatting with the Agent

### Slide 6 — Tools (Function Tools)
- Agents become more capable with Tools
- `FunctionTool`: write a Python function → the Agent can call it
- Examples: calculate, search, convert units
- 💡 Key idea: docstrings matter! The Agent reads the docstring to decide when to use the tool

### Slide 7 — Gemini API Parameters
- `temperature`: level of creativity (0 = precise, 1 = creative)
- `top_k`, `top_p`: control diversity
- `max_output_tokens`: answer length

### Slide 8 — RAG Agent
- Combine Agent + VectorDB from Day 1
- Tool: `search_knowledge(query)` → search Qdrant
- The Agent decides on its own: search first or answer directly

### Slide 9 — Multi-Agent Systems
- One agent is not enough? → Use multiple agents working together
- 4 patterns:
  - Sequential: step by step A → B → C
  - Parallel: at the same time A + B + C
  - Loop: repeat until success
  - LLM Routing: AI chooses which Agent to use

### Slide 10 — Sequential vs Parallel
- Sequential: good for dependent workflows (summarize → translate → send)
- Parallel: good for independent tasks (search 3 sources at once)
- Comparison visual

### Slide 11 — Session Memory
- Agents can remember the conversation
- `InMemorySessionService`
- Example: in follow-up questions, the Agent knows the context

### Slide 12 — Agentic RAG
- Combine everything: RAG + Multi-Agent + Memory
- Example: a Study Assistant that can search + summarize + answer questions
- 💡 Key idea: different from normal RAG = the Agent makes decisions on its own

### Slide 13 — 🧪 Exercise
- Build an Agent + Custom Tool yourself
- 15 minutes

### Slide 14 — Day 2 Summary
- Agent = AI that can think + use tools
- Multi-Agent = multiple agents working together
- Agentic RAG = Agent + RAG + Memory

### Slide 15 — Day 2 Homework
- 🔗 Open homework: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_homework.ipynb)`
- 📤 Submit homework: [Google Form Day 2](https://forms.gle/xTQ5eVNKa4fcQVKb8)
- Build 4 parts: Agent+Tool, RAG Agent, Workflow, Explanation
- Download .ipynb → Upload to the Form
- 10 points | Deadline: [Specify]

---

## 📅 Day 3: Evaluation & Optimization

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 3: Evaluation & Optimization

### Slide 2 — Review Day 1–2 + Setup
- Day 1: Data → VectorDB → Search
- Day 2: Agent → RAG Agent → Multi-Agent
- Day 3: "Now that we built it, is it actually good?"
- 🔗 Open Notebook: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_evaluation.ipynb)`

### Slide 3 — Why Measure Quality?
- "Looks like it works" ≠ "works well"
- Problems: hallucination, irrelevant answers, poor retrieval
- Systematic evaluation → targeted improvement

### Slide 4 — RAGAS Metrics
- **Faithfulness**: Is the answer grounded in the context?
- **Answer Relevancy**: Does it answer the question?
- **Context Precision**: Is the retrieved context relevant?
- **Context Recall**: Was enough context retrieved?
- Visual: 4 metrics quadrant

### Slide 5 — Auto Eval Dataset
- Automatically generate a test set using Gemini
- Input: documents → Output: questions + answers + context
- Reduce prep time from days → minutes

### Slide 6 — LLM-as-Judge
- Use an LLM to evaluate another LLM
- Prompt: "Score from 1–5 based on these criteria..."
- Advantage: no need to write rules manually
- Limitation: can be biased, so prompt design matters

### Slide 7 — Agent Testing
- Tool Selection Accuracy: Did the agent choose the correct tool?
- Response Quality: Is the answer good?
- Test Cases: ≥ 5 questions → measure pass rate

### Slide 8 — A/B Testing
- Compare 2 configurations:
  - A: chunk_size=200, top_k=3
  - B: chunk_size=500, top_k=5
- Measure results → choose the better one
- 💡 Key idea: change only one variable at a time, otherwise you will not know the cause

### Slide 9 — Prompt Engineering
- Before vs After
- Techniques: Role, Few-shot, Chain-of-Thought, Constraints
- Example: better prompt → better score

### Slide 10 — Optimization Strategies
- 5 things you can tune:
  1. Chunk size / overlap
  2. Embedding model
  3. Top-K / Search method
  4. Prompt template
  5. Model parameters (temperature)
- Measure results every time you change something!

### Slide 11 — 🧪 Exercise
- Try improving the pipeline → measure Before/After
- 15 minutes

### Slide 12 — ⭐ Capstone Project
- Combine everything: Data + Agent + Evaluation
- Build a tested RAG Agent
- Show: scores, reasoning, Before/After

### Slide 13 — 3-Day Summary
- Day 1: 📊 Data Engineering → prepare the data
- Day 2: 🤖 Agent Building → AI that can reason on its own
- Day 3: 📏 Evaluation → know whether it is truly good
- Visual: Full end-to-end pipeline

### Slide 14 — What's Next?
- Production: Deploy with Cloud Run / Vertex AI
- Advanced: Fine-tuning, Knowledge Graph, Hybrid Agent
- Community: Feel free to open Issues and submit PRs!

### Slide 15 — Day 3 Homework + Final Grading
- 🔗 Open homework: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_homework.ipynb)`
- 📤 Submit homework: [Google Form Day 3](https://forms.gle/yLVHh4YVVt3miogm8)
- Homework: 10 points | Download .ipynb → Upload to the Form
- Deadline: [Specify]
- Total grading criteria across 3 days = 90 points:
  - 🤝 Responsibility (30)
  - 💪 Determination (30)
  - 💻 Technical (30)

### Slide 16 — Thank You
- _"The best way to learn AI is to build with AI."_
