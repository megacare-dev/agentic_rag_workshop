```markdown
# 🎓 Slide Outline — Agentic RAG Workshop (3 Days)

---

## 🎯 Slide 0: Workshop Overview (Use at the start of Day 1)

### Slide 0-1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Build an AI system that searches, thinks, and answers on its own
- 3 Days | Hands-on | Google Colab

### Slide 0-2 — 3-Day Roadmap
- **Day 1: 📊 Data Engineering Pipeline**
  - Prepare data: Deduplicate → Chunk → Embed → VectorDB → Search
  - Tech: Qdrant, multilingual-e5-large, BM25, PyThaiNLP
  - 🔗 [Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_data_engineering.ipynb)
- **Day 2: 🤖 Building Agents**
  - Build an AI Agent: Agent + Tools → RAG Agent → Multi-Agent
  - Tech: Google ADK, Gemini API, Session Memory
  - 🔗 [Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_building_agents.ipynb)
- **Day 3: 📏 Evaluation & Optimization**
  - Measure and improve: RAGAS, LLM-as-Judge, A/B Testing, Capstone
  - Tech: RAGAS Framework, Prompt Engineering
  - 🔗 [Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_evaluation.ipynb)

### Slide 0-3 — Grading Rubric
- **3 categories × 3 days = 90 points**
- 🤝 **Responsibility (10/Day)** — submit on time, complete deliverables, run ✅ before submitting
- 💪 **Determination (10/Day)** — complete tasks, try different parameters, explain, debug
- 💻 **Technical (10/Day)** — code runs, results are correct, no copying
- Table:

  | Category         | Day 1 | Day 2 | Day 3 | Total |
  | ---------------- | :---: | :---: | :---: | :---: |
  | 🤝 Responsibility |  /10  |  /10  |  /10  |  /30  |
  | 💪 Determination  |  /10  |  /10  |  /10  |  /30  |
  | 💻 Technical      |  /10  |  /10  |  /10  |  /30  |
  | **Total**        | **/30** | **/30** | **/30** | **/90** |

### Slide 0-4 — Tools Used
- **Google Colab** — write code in the cloud (no local install required)
- **Gemini API** — LLM (2.5 Flash / 2.5 Pro)
- **Google ADK** — build AI Agents
- **Qdrant** — Vector Database
- What you need:
  - Google Account
  - Gemini API Key (free) → store in Colab Secrets

### Slide 0-5 — Ground Rules
- 🔗 Notebooks are shared via link (open in Colab directly)
- 📤 Submit homework via Google Form (Download .ipynb → Upload)
- ⏰ Workshop: Learn → Practice → Homework
- ❓ Questions? Raise your hand anytime!
- ⚠️ Do NOT share your API key!

### Slide 0-6 — 📤 Homework Submission
- **Submit by:** Download .ipynb from Colab → Upload to Google Form
- Submit both the exercise notebook and the homework notebook

| Day   | 🔗 Homework (Colab)                                                                                                                  | 📤 Submission (Google Form)                              |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------- |
| Day 1 | [day1_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_homework.ipynb) | [Submit Day 1](https://forms.gle/R7EXvPvUfZ286CVh8)    |
| Day 2 | [day2_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_homework.ipynb) | [Submit Day 2](https://forms.gle/xTQ5eVNKa4fcQVKb8)    |
| Day 3 | [day3_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_homework.ipynb) | [Submit Day 3](https://forms.gle/yLVHh4YVVt3miogm8)    |

- ⚠️ One submission per day (edits allowed after submission)
- ✅ Run "Check Answers" before submitting every time!

---

## 📅 Day 1: Data Engineering Pipeline

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 1: Data Engineering Pipeline

### Slide 2 — Workshop Overview
- What are we doing in 3 days?
  - Day 1: Data → VectorDB (today)
  - Day 2: Agent + Tools
  - Day 3: Evaluation + Capstone
- Pipeline diagram: Raw → Chunk → Embed → Store → Retrieve → Answer

### Slide 3 — What is RAG?
- **R**etrieval-**A**ugmented **G**eneration
- LLMs are powerful but don’t know our domain data → we must provide context
- RAG = search + generate
- Diagram: LLM-only vs RAG

### Slide 4 — Setup
- 🔗 Open notebook: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_data_engineering.ipynb)`
- Set API Key in Colab Secrets: `GOOGLE_API_KEY`
- ⚠️ Do not share your API Key!

### Slide 5 — Deduplication
- Why dedupe files?
- MD5/SHA256 hash → file fingerprint
- 💡 Note: same hash = identical content

### Slide 6 — Chunking
- Why chunk text? (LLMs have context limits)
- 3 methods:
  - Fixed-size: simple, but may split sentences
  - Recursive: smarter, splits by structure
  - Semantic: best, splits by meaning
- 💡 Note: chunk_size vs overlap tradeoff

### Slide 7 — Thai Tokenization
- Thai has no spaces between words
- PyThaiNLP `word_tokenize()`
- Example: "สวัสดีครับ" → ["สวัสดี","ครับ"]

### Slide 8 — Embedding
- Convert text → vector (numbers)
- Model: `multilingual-e5-large` (supports Thai)
- Diagram: similar text → nearby vectors
- Cosine similarity: measures semantic closeness

### Slide 9 — Hybrid Search
- Dense search: embeddings (semantic)
- Sparse search: BM25 (keyword match)
- Hybrid = Dense + Sparse → best results
- 💡 Note: dense handles synonyms, sparse handles keywords

### Slide 10 — Vector Database (Qdrant)
- Why not use a regular DB? → we need semantic search, not keyword search
- Qdrant: in-memory, fast, easy
- Collection → Points (vector + payload)

### Slide 11 — Indexing & Retrieval
- Indexing: Chunk → Embed → Store in Qdrant
- Retrieval: Query → Embed → Search → Top-K results
- Diagram: Full pipeline flow

### Slide 12 — 🧪 Exercise
- Try it yourself in the notebook
- Adjust chunk_size, top_k and compare results
- 15 minutes

### Slide 13 — Day 1 Summary
- Today we learned: Dedup → Chunk → Embed → VectorDB → Search
- 💡 Key takeaways:
  - Chunk size affects RAG quality
  - Hybrid search beats a single method
  - Embedding model must support Thai

### Slide 14 — Day 1 Homework
- 🔗 Open homework: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_homework.ipynb)`
- 📤 Submit: [Google Form Day 1](https://forms.gle/R7EXvPvUfZ286CVh8)
- Build the pipeline yourself (10 points)
- Download .ipynb → Upload to the form
- Deadline: [TBD]

---

## 📅 Day 2: Building Agents with Google ADK

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 2: Building Agents with Google ADK

### Slide 2 — Review Day 1 + Setup
- Pipeline: Raw → Chunk → Embed → VectorDB → Search
- Today: add an "Agent" that can make decisions
- 🔗 Open notebook: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_building_agents.ipynb)`

### Slide 3 — Agent vs Chatbot
- Chatbot: responds based on a script
- Agent: thinks → decides → uses tools → answers
- Diagram: Input → Think → Act → Observe → Answer

### Slide 4 — Google ADK
- Agent Development Kit
- Build an Agent with a few lines of Python
- Components: Agent + Instruction + Tools + Model

### Slide 5 — First Agent
- `LlmAgent(name, model, instruction)`
- Instruction is the Agent's personality
- Try chatting with the agent

### Slide 6 — Tools (Function Tools)
- Agents get better with tools
- `FunctionTool`: write a Python function → Agent can call it
- Examples: calculate, search, convert units
- 💡 Note: docstrings matter! The agent reads docstrings to decide

### Slide 7 — Gemini API Parameters
- `temperature`: creativity (0 = precise, 1 = creative)
- `top_k`, `top_p`: control diversity
- `max_output_tokens`: response length

### Slide 8 — RAG Agent
- Combine Agent + VectorDB from Day 1
- Tool: `search_knowledge(query)` → search Qdrant
- Agent decides: search first or answer directly

### Slide 9 — Multi-Agent Systems
- One agent not enough? → use multiple agents together
- 4 patterns:
  - Sequential: do A → B → C
  - Parallel: run A + B + C together
  - Loop: repeat until success
  - LLM routing: AI chooses which agent to use

### Slide 10 — Sequential vs Parallel
- Sequential: good for step-by-step tasks (summarize → translate → send)
- Parallel: good for independent tasks (search 3 sources concurrently)
- Diagram comparison

### Slide 11 — Session Memory
- Agents can remember conversation history
- `InMemorySessionService`
- Example: follow-up questions keep context

### Slide 12 — Agentic RAG
- Put it all together: RAG + Multi-Agent + Memory
- Example: Study assistant that searches + summarizes + answers
- 💡 Difference from regular RAG: the agent decides what to do

### Slide 13 — 🧪 Exercise
- Build an Agent + Custom Tool yourself
- 15 minutes

### Slide 14 — Day 2 Summary
- Agent = AI that thinks + uses tools
- Multi-Agent = multiple agents working together
- Agentic RAG = Agent + RAG + Memory

### Slide 15 — Day 2 Homework
- 🔗 Open homework: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_homework.ipynb)`
- 📤 Submit: [Google Form Day 2](https://forms.gle/xTQ5eVNKa4fcQVKb8)
- Build 4 parts: Agent+Tool, RAG Agent, Workflow, explanation
- Download .ipynb → Upload to the form
- 10 points | Deadline: [TBD]

---

## 📅 Day 3: Evaluation & Optimization

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 3: Evaluation & Optimization

### Slide 2 — Review Day 1-2 + Setup
- Day 1: Data → VectorDB → Search
- Day 2: Agent → RAG Agent → Multi-Agent
- Day 3: "Built it, but is it actually good?"
- 🔗 Open notebook: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_evaluation.ipynb)`

### Slide 3 — Why measure quality?
- "Seems to work" ≠ "works well"
- Problems: hallucinations, wrong answers, wrong retrieval
- Measure systematically → targeted improvements

### Slide 4 — RAGAS Metrics
- **Faithfulness**: is the answer consistent with context?
- **Answer Relevancy**: does it answer the question?
- **Context Precision**: is the retrieved context accurate?
- **Context Recall**: is the relevant context retrieved?
- Diagram: 4 metrics quadrant

### Slide 5 — Auto Eval Dataset
- Generate evaluation dataset automatically using Gemini
- Input: document → Output: questions + answers + context
- Reduce days of work to minutes

### Slide 6 — LLM-as-Judge
- Use an LLM to score an LLM
- Prompt: "Rate 1-5 based on criteria..."
- Pros: no manual rule writing
- Cons: bias, requires prompt engineering

### Slide 7 — Agent Testing
- Tool Selection Accuracy: did the agent choose the right tool?
- Response Quality: is the answer good?
- Test cases: ≥ 5 questions → check pass rate

### Slide 8 — A/B Testing
- Compare 2 configs:
  - A: chunk_size=200, top_k=3
  - B: chunk_size=500, top_k=5
- Measure results → choose the better one
- 💡 Note: change one variable at a time to understand results

### Slide 9 — Prompt Engineering
- Before vs After
- Techniques: Role, Few-shot, Chain-of-Thought, Constraints
- Example: improved prompt → better scores

### Slide 10 — Optimization Strategies
- 5 levers to tune:
  1. Chunk size / overlap
  2. Embedding model
  3. Top-K / search method
  4. Prompt template
  5. Model parameters (temperature)
- Measure every change!

### Slide 11 — 🧪 Exercise
- Tune your pipeline → measure Before/After
- 15 minutes

### Slide 12 — ⭐ Capstone Project
- Combine everything: Data + Agent + Evaluation
- Build a RAG Agent that passes tests
- Show results: score, rationale, Before/After

### Slide 13 — 3-Day Summary
- Day 1: 📊 Data Engineering → data ready
- Day 2: 🤖 Agent Building → AI that thinks for itself
- Day 3: 📏 Evaluation → know if it is actually good
- Diagram: Full pipeline from start to finish

### Slide 14 — What's Next?
- Production: Deploy with Cloud Run / Vertex AI
- Advanced: Fine-tuning, Knowledge Graph, Hybrid Agent
- Community: open issues, submit PRs!

### Slide 15 — Day 3 Homework + Final Grade
- 🔗 Open homework: `[Open in Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_homework.ipynb)`
- 📤 Submit: [Google Form Day 3](https://forms.gle/yLVHh4YVVt3miogm8)
- Homework is 10 points | Download .ipynb → Upload to form
- Deadline: [TBD]
- Final grading across 3 days = 90 points:
  - 🤝 Responsibility (30)
  - 💪 Determination (30)
  - 💻 Technical (30)

### Slide 16 — Thank You
- _"The best way to learn AI is to build with AI."_

``` 
