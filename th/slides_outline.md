# 🎓 Slide Outline — Agentic RAG Workshop (3 Days)

---

## 🎯 Slide 0: Workshop Overview (ใช้เปิด Day 1 ก่อนเข้าเนื้อหา)

### Slide 0-1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- สร้างระบบ AI ที่ค้นหา คิด และตอบได้ด้วยตัวเอง
- 3 วัน | Hands-on | Google Colab

### Slide 0-2 — Roadmap 3 วัน
- **Day 1: 📊 Data Engineering Pipeline**
  - ทำข้อมูลให้พร้อม: Deduplicate → Chunk → Embed → VectorDB → Search
  - Tech: Qdrant, multilingual-e5-large, BM25, PyThaiNLP
  - 🔗 [เปิดใน Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_data_engineering.ipynb)
- **Day 2: 🤖 Building Agents**
  - สร้าง AI Agent: Agent + Tools → RAG Agent → Multi-Agent
  - Tech: Google ADK, Gemini API, Session Memory
  - 🔗 [เปิดใน Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_building_agents.ipynb)
- **Day 3: 📏 Evaluation & Optimization**
  - วัดและปรับปรุง: RAGAS, LLM-as-Judge, A/B Testing, Capstone
  - Tech: RAGAS Framework, Prompt Engineering
  - 🔗 [เปิดใน Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_evaluation.ipynb)

### Slide 0-3 — เกณฑ์การให้คะแนน
- **3 ด้าน × 3 วัน = 90 คะแนน**
- 🤝 **Responsibility (10/Day)** — ส่งตรงเวลา, ข้อมูลครบ, Run ✅ ก่อนส่ง
- 💪 **Determination (10/Day)** — ทำครบ, ลอง parameter, อธิบาย, debug
- 💻 **Technical (10/Day)** — Code ทำงาน, ผลถูก, ไม่ copy
- ตาราง:

  | ด้าน              |  Day 1  |  Day 2  |  Day 3  |   รวม   |
  | ---------------- | :-----: | :-----: | :-----: | :-----: |
  | 🤝 Responsibility |   /10   |   /10   |   /10   |   /30   |
  | 💪 Determination  |   /10   |   /10   |   /10   |   /30   |
  | 💻 Technical      |   /10   |   /10   |   /10   |   /30   |
  | **รวม**          | **/30** | **/30** | **/30** | **/90** |

### Slide 0-4 — เครื่องมือที่ใช้
- **Google Colab** — เขียน code บน cloud (ไม่ต้องลงอะไรในเครื่อง)
- **Gemini API** — LLM (2.5 Flash / 2.5 Pro)
- **Google ADK** — สร้าง AI Agent
- **Qdrant** — Vector Database
- สิ่งที่ต้องเตรียม:
  - Google Account
  - Gemini API Key (ฟรี) → ใส่ใน Colab Secrets

### Slide 0-5 — Ground Rules
- 🔗 Notebook จะแชร์ผ่าน link (เปิดใน Colab ได้เลย)
- 📤 ส่งการบ้านผ่าน Google Form (Download .ipynb → Upload)
- ⏰ Workshop: เรียน → ฝึก → ทำการบ้าน
- ❓ มีคำถาม → ยกมือถามได้ตลอด!
- ⚠️ ห้ามแชร์ API Key!

### Slide 0-6 — 📤 ส่งการบ้าน
- **วิธีส่ง:** Download .ipynb จาก Colab → Upload ใน Google Form
- ส่งทั้งไฟล์เนื้อหา (แบบฝึกหัด) + ไฟล์การบ้าน

| Day   | 🔗 เปิดการบ้านใน Colab                                                                                                                  | 📤 ส่งการบ้าน (Google Form)                              |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------- |
| Day 1 | [day1_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_homework.ipynb) | [ส่งการบ้าน Day 1](https://forms.gle/R7EXvPvUfZ286CVh8) |
| Day 2 | [day2_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_homework.ipynb) | [ส่งการบ้าน Day 2](https://forms.gle/xTQ5eVNKa4fcQVKb8) |
| Day 3 | [day3_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_homework.ipynb) | [ส่งการบ้าน Day 3](https://forms.gle/yLVHh4YVVt3miogm8) |

- ⚠️ ส่งได้ 1 ครั้ง (แก้ไขหลังส่งได้)
- ✅ Run "ตรวจสอบคำตอบ" ก่อนส่งทุกครั้ง!

---

## 📅 Day 1: Data Engineering Pipeline

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 1: Data Engineering Pipeline

### Slide 2 — Workshop Overview
- 3 วันเรียนอะไร?
  - Day 1: Data → VectorDB (วันนี้)
  - Day 2: Agent + Tools
  - Day 3: Evaluation + Capstone
- ภาพ Pipeline: Raw → Chunk → Embed → Store → Retrieve → Answer

### Slide 3 — RAG คืออะไร?
- **R**etrieval-**A**ugmented **G**eneration
- LLM เก่ง แต่ไม่รู้ข้อมูลเรา → ต้อง "ป้อน" context ให้
- RAG = ค้นหา + สร้างคำตอบ
- ภาพเปรียบเทียบ: LLM-only vs RAG

### Slide 4 — Setup
- 🔗 เปิด Notebook: `[เปิดใน Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_data_engineering.ipynb)`
- ตั้ง API Key ใน Colab Secrets: `GOOGLE_API_KEY`
- ⚠️ ห้ามแชร์ API Key!

### Slide 5 — Deduplication
- ทำไมต้องตรวจไฟล์ซ้ำ?
- MD5/SHA256 Hash → fingerprint ของไฟล์
- 💡 สังเกต: Hash เดียวกัน = เนื้อหาเหมือนกัน 100%

### Slide 6 — Chunking
- ทำไมต้องตัดข้อความ? (LLM มี context limit)
- 3 วิธี:
  - Fixed-size: ง่าย แต่ตัดกลางประโยค
  - Recursive: ฉลาดกว่า ตัดตามโครงสร้าง
  - Semantic: ดีสุด ตัดตามเนื้อหา
- 💡 สังเกต: chunk_size vs overlap tradeoff

### Slide 7 — Thai Tokenization
- ภาษาไทยไม่มีช่องว่างระหว่างคำ
- PyThaiNLP `word_tokenize()`
- ตัวอย่าง: "สวัสดีครับ" → ["สวัสดี","ครับ"]

### Slide 8 — Embedding
- แปลงข้อความ → Vector (ตัวเลข)
- Model: `multilingual-e5-large` (รองรับไทย)
- ภาพ: ข้อความใกล้กัน → Vector ใกล้กัน
- Cosine Similarity: วัดความคล้าย

### Slide 9 — Hybrid Search
- Dense Search: Embedding (เข้าใจความหมาย)
- Sparse Search: BM25 (จับคำตรง)
- Hybrid = Dense + Sparse → ดีที่สุด
- 💡 สังเกต: Dense เก่ง synonym, Sparse เก่ง keyword

### Slide 10 — Vector Database (Qdrant)
- ทำไมไม่ใช้ DB ปกติ? → ค้นหาด้วย "ความหมาย" ไม่ใช่ keyword
- Qdrant: in-memory, เร็ว, ใช้ง่าย
- Collection → Points (vector + payload)

### Slide 11 — Indexing & Retrieval
- Indexing: Chunk → Embed → Store ใน Qdrant
- Retrieval: Query → Embed → Search → Top-K results
- ภาพ: Full Pipeline Flow

### Slide 12 — 🧪 แบบฝึกหัด
- ลองทำใน notebook ด้วยตัวเอง
- ปรับ chunk_size, top_k ดูผลต่าง
- 15 นาที

### Slide 13 — สรุป Day 1
- วันนี้เรียน: Dedup → Chunk → Embed → VectorDB → Search
- 💡 Key Takeaways:
  - Chunk size มีผลต่อคุณภาพ RAG
  - Hybrid Search ดีกว่าใช้วิธีเดียว
  - Embedding model ต้องรองรับภาษาไทย

### Slide 14 — การบ้าน Day 1
- 🔗 เปิดการบ้าน: `[เปิดใน Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day1/day1_homework.ipynb)`
- 📤 ส่งการบ้าน: [Google Form Day 1](https://forms.gle/R7EXvPvUfZ286CVh8)
- สร้าง Pipeline ด้วยตัวเอง (10 คะแนน)
- Download .ipynb → Upload ใน Form
- Deadline: [ระบุ]

---

## 📅 Day 2: Building Agents with Google ADK

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 2: Building Agents with Google ADK

### Slide 2 — ทบทวน Day 1 + Setup
- Pipeline: Raw → Chunk → Embed → VectorDB → Search
- วันนี้: เพิ่ม "Agent" ที่คิดเองได้
- 🔗 เปิด Notebook: `[เปิดใน Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_building_agents.ipynb)`

### Slide 3 — Agent vs Chatbot
- Chatbot: ถาม-ตอบ ตาม script
- Agent: คิด → ตัดสินใจ → ใช้เครื่องมือ → ตอบ
- ภาพ: Input → Think → Act → Observe → Answer

### Slide 4 — Google ADK
- Agent Development Kit
- สร้าง Agent ด้วย Python ไม่กี่บรรทัด
- Components: Agent + Instruction + Tools + Model

### Slide 5 — Agent แรก
- `LlmAgent(name, model, instruction)`
- Instruction = "บุคลิก" ของ Agent
- ลองคุยกับ Agent

### Slide 6 — Tools (Function Tools)
- Agent เก่งขึ้นด้วย Tools
- `FunctionTool`: เขียน Python function → Agent เรียกใช้ได้
- ตัวอย่าง: คำนวณ, ค้นหา, แปลงหน่วย
- 💡 สังเกต: docstring สำคัญ! Agent อ่าน docstring เพื่อตัดสินใจ

### Slide 7 — Gemini API Parameters
- `temperature`: ความ creative (0=เป๊ะ, 1=สร้างสรรค์)
- `top_k`, `top_p`: ควบคุมความหลากหลาย
- `max_output_tokens`: ความยาวคำตอบ

### Slide 8 — RAG Agent
- รวม Agent + VectorDB จาก Day 1
- Tool: `search_knowledge(query)` → ค้นจาก Qdrant
- Agent ตัดสินใจเอง: ค้นหาหรือตอบเลย

### Slide 9 — Multi-Agent Systems
- Agent เดียวไม่พอ? → ใช้หลาย Agent ทำงานร่วมกัน
- 4 patterns:
  - Sequential: ทำทีละขั้น A → B → C
  - Parallel: ทำพร้อมกัน A + B + C
  - Loop: ทำซ้ำจนสำเร็จ
  - LLM Routing: AI เลือก Agent ให้

### Slide 10 — Sequential vs Parallel
- Sequential: เหมาะงานต่อเนื่อง (สรุป → แปล → ส่ง)
- Parallel: เหมาะงานอิสระ (ค้นหา 3 แหล่งพร้อมกัน)
- ภาพเปรียบเทียบ

### Slide 11 — Session Memory
- Agent จำบทสนทนาได้
- `InMemorySessionService`
- ตัวอย่าง: ถามต่อเนื่อง Agent รู้ context

### Slide 12 — Agentic RAG
- รวมทุกอย่าง: RAG + Multi-Agent + Memory
- ตัวอย่าง: Study Assistant ที่ค้นหา + สรุป + ตอบคำถาม
- 💡 สังเกต: ต่างจาก RAG ธรรมดา = Agent ตัดสินใจเอง

### Slide 13 — 🧪 แบบฝึกหัด
- สร้าง Agent + Custom Tool ด้วยตัวเอง
- 15 นาที

### Slide 14 — สรุป Day 2
- Agent = AI ที่คิด + ใช้เครื่องมือได้
- Multi-Agent = หลาย Agent ทำงานด้วยกัน
- Agentic RAG = Agent + RAG + Memory

### Slide 15 — การบ้าน Day 2
- 🔗 เปิดการบ้าน: `[เปิดใน Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day2/day2_homework.ipynb)`
- 📤 ส่งการบ้าน: [Google Form Day 2](https://forms.gle/xTQ5eVNKa4fcQVKb8)
- สร้าง 4 ขั้น: Agent+Tool, RAG Agent, Workflow, อธิบาย
- Download .ipynb → Upload ใน Form
- 10 คะแนน | Deadline: [ระบุ]

---

## 📅 Day 3: Evaluation & Optimization

### Slide 1 — Title
- **Agentic RAG Workshop: From Zero to Hero**
- Day 3: Evaluation & Optimization

### Slide 2 — ทบทวน Day 1-2 + Setup
- Day 1: Data → VectorDB → Search
- Day 2: Agent → RAG Agent → Multi-Agent
- Day 3: "สร้างแล้ว ดีจริงมั้ย?"
- 🔗 เปิด Notebook: `[เปิดใน Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_evaluation.ipynb)`

### Slide 3 — ทำไมต้องวัดคุณภาพ?
- "ดูเหมือนทำงานได้" ≠ "ทำงานได้ดี"
- ปัญหา: Hallucination, ตอบไม่ตรง, ค้นผิด
- วัดอย่างเป็นระบบ → ปรับปรุงได้ตรงจุด

### Slide 4 — RAGAS Metrics
- **Faithfulness**: คำตอบตรงกับ context มั้ย?
- **Answer Relevancy**: ตอบตรงคำถามมั้ย?
- **Context Precision**: context ที่ดึงมาตรงมั้ย?
- **Context Recall**: ดึง context ครบมั้ย?
- ภาพ: 4 metrics quadrant

### Slide 5 — Auto Eval Dataset
- สร้างชุดทดสอบอัตโนมัติจาก Gemini
- Input: เอกสาร → Output: คำถาม + คำตอบ + context
- ลดเวลาจากหลายวัน → ไม่กี่นาที

### Slide 6 — LLM-as-Judge
- ใช้ LLM ตรวจ LLM
- Prompt: "ให้คะแนน 1-5 ตามเกณฑ์..."
- ข้อดี: ไม่ต้องเขียน rule เอง
- ข้อเสีย: มี bias, ต้องออกแบบ prompt ดี

### Slide 7 — Agent Testing
- Tool Selection Accuracy: Agent เลือก tool ถูกมั้ย?
- Response Quality: คำตอบดีมั้ย?
- Test Cases: ≥ 5 คำถาม → ดู pass rate

### Slide 8 — A/B Testing
- เปรียบเทียบ 2 configs:
  - A: chunk_size=200, top_k=3
  - B: chunk_size=500, top_k=5
- วัดผล → เลือกตัวที่ดีกว่า
- 💡 สังเกต: เปลี่ยนทีละตัวแปร ไม่งั้นไม่รู้สาเหตุ

### Slide 9 — Prompt Engineering
- Before vs After
- เทคนิค: Role, Few-shot, Chain-of-Thought, Constraints
- ตัวอย่าง: prompt ที่ดีขึ้น → คะแนนดีขึ้น

### Slide 10 — Optimization Strategies
- 5 สิ่งที่ปรับได้:
  1. Chunk size / overlap
  2. Embedding model
  3. Top-K / Search method
  4. Prompt template
  5. Model parameters (temperature)
- วัดผลทุกครั้งที่เปลี่ยน!

### Slide 11 — 🧪 แบบฝึกหัด
- ลองปรับ pipeline → วัดผล Before/After
- 15 นาที

### Slide 12 — ⭐ Capstone Project
- รวมทุกอย่าง: Data + Agent + Evaluation
- สร้าง RAG Agent ที่ผ่านการทดสอบ
- แสดงผล: คะแนน, เหตุผล, Before/After

### Slide 13 — สรุป 3 วัน
- Day 1: 📊 Data Engineering → ข้อมูลพร้อม
- Day 2: 🤖 Agent Building → AI คิดเองได้
- Day 3: 📏 Evaluation → รู้ว่าดีจริงมั้ย
- ภาพ: Full Pipeline ตั้งแต่ต้นจนจบ

### Slide 14 — What's Next?
- Production: Deploy ด้วย Cloud Run / Vertex AI
- Advanced: Fine-tuning, Knowledge Graph, Hybrid Agent
- Community: เปิด Issue, ส่ง PR ได้เลย!

### Slide 15 — การบ้าน Day 3 + เกณฑ์ Final
- 🔗 เปิดการบ้าน: `[เปิดใน Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/day3/day3_homework.ipynb)`
- 📤 ส่งการบ้าน: [Google Form Day 3](https://forms.gle/yLVHh4YVVt3miogm8)
- การบ้าน 10 คะแนน | Download .ipynb → Upload ใน Form
- Deadline: [ระบุ]
- เกณฑ์รวม 3 ด้าน × 3 วัน = 90 คะแนน:
  - 🤝 Responsibility (30)
  - 💪 Determination (30)
  - 💻 Technical (30)

### Slide 16 — Thank You
- _"The best way to learn AI is to build with AI."_
