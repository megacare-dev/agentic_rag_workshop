# 🎓 Slide Outline — Agentic RAG Workshop (4 ชม. Online)

> สำหรับ Batch AgenticRAG02 | ม.มหิดล ICT | 18 มี.ค. 2569 13:00-17:00

---

## 🎤 Opening (13:00-13:15) — 3 Slides

### Slide 1 — Title
- **Agentic RAG: From Zero to Hero**
- Workshop 4 ชั่วโมง | Online
- 🗓️ 18 มี.ค. 2569 | ม.มหิดล ICT

### Slide 2 — ⏱️ Timeline
| เวลา | ช่วง | กิจกรรม |
|:----:|------|--------|
| 13:00-13:15 | 🎤 Opening | แนะนำตัว, Ground Rules, ตรวจ API Key |
| 13:15-14:20 | 📢 Part 1 | Data → Chunk → Embed → Qdrant → Retrieve |
| 14:20-14:35 | ☕ พัก | 15 นาที |
| 14:35-15:50 | 📢 Part 2 | Agent → Tool → RAG Agent → Agentic RAG |
| 15:50-16:00 | 🔧 Buffer | ดูปัญหา, troubleshoot |
| 16:00-16:50 | 🧪 Part 3 | แบบฝึกหัด (10 คะแนน) |
| 16:50-17:00 | 🎬 Closing | สรุป, ส่งงาน, Certificate |

### Slide 3 — 🌐 Ground Rules (Online)
- 💬 ถามผ่าน Chat ได้ตลอด
- 🎤 เปิดไมค์ถามได้ช่วง Q&A
- ⚠️ Error 429 = Rate Limit → รอ 1-2 นาที
- 🔑 เตรียม API Key ใน Colab Secrets ก่อน

---

## 📢 Part 1: Data Pipeline (13:15-14:20) — 7 Slides

### Slide 4 — RAG คืออะไร?
- LLM เก่ง แต่ไม่รู้ข้อมูลเรา
- RAG = ค้นหา + สร้างคำตอบ
- Pipeline: Text → Chunk → Embed → VectorDB → Retrieve → Answer

### Slide 5 — 📦 Setup
- 🔗 **เปิดใน Colab**: [agentic_rag_4hr.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/th/4hr/agentic_rag_4hr.ipynb)
- ตั้ง API Key → Colab Secrets → `GOOGLE_API_KEY`
- Run Section 0 ด้วยกัน

### Slide 6 — ✂️ Chunking
- LLM มี context limit → ต้องตัดข้อความ
- Fixed-size vs **Recursive** ⭐
- 💡 สังเกต: chunk_size เล็ก = แม่นยำ, ใหญ่ = มี context

### Slide 7 — 🔢 Embedding
- แปลงข้อความ → Vector
- Model: `multilingual-e5-large` (รองรับไทย)
- Cosine Similarity วัดความคล้าย

### Slide 8 — 🗄️ Qdrant (Vector Database)
- ค้นหาด้วย "ความหมาย" ไม่ใช่ keyword
- In-memory mode — ไม่ต้องติดตั้ง
- Collection → Points (vector + payload)

### Slide 9 — 🔎 Retrieval
- Query → Embed → Search → Top-K
- 💡 สังเกต: ถามเรื่อง "แพทย์" → ได้ case_healthcare

### Slide 10 — 📊 สรุป Part 1
- Pipeline ครบ: Chunk → Embed → Qdrant → Retrieve ✅
- ต่อไป: สร้าง **Agent** ที่ใช้ pipeline นี้

---

## ☕ พัก (14:20-14:35) — 15 นาที

---

## 📢 Part 2: Agent + Agentic RAG (14:35-15:50) — 8 Slides

### Slide 11 — 🤖 Agent vs Chatbot
- Chatbot: ถาม-ตอบตาม script
- Agent: **คิด → ตัดสินใจ → ใช้เครื่องมือ**
- Google ADK = สร้าง Agent ด้วย Python ไม่กี่บรรทัด

### Slide 12 — Agent แรก
- `LlmAgent(name, model, instruction)`
- Instruction = "บุคลิก" ของ Agent
- 💡 สังเกต: Agent ตอบจากความรู้ทั่วไป ยังไม่ค้นข้อมูลเรา

### Slide 13 — 🔧 Tools
- FunctionTool: เขียน Python function → Agent เรียกใช้
- ⚠️ **docstring สำคัญ!** Agent อ่าน docstring ตัดสินใจ
- ตัวอย่าง: BMI Calculator

### Slide 14 — Gemini API Parameters
- `temperature`: creativity (0=เป๊ะ, 1=สร้างสรรค์)
- `max_output_tokens`: ความยาว
- `top_p`: diversity

### Slide 15 — 🔍 RAG Agent ⭐
- Agent + VectorDB = **Agentic RAG**
- Tool: `search_knowledge(query)` → ค้นจาก Qdrant
- Agent ตัดสินใจเอง: ค้นหาหรือตอบเลย
- 💡 สังเกต: ต่างจาก RAG ธรรมดา = Agent เลือกได้

### Slide 16 — 🧠 Session Memory
- `InMemorySessionService` → Agent จำบทสนทนา
- ถามต่อเนื่องไม่ต้องอธิบายซ้ำ
- 💡 สังเกต: Memory ทำให้ Agent คุยได้ธรรมชาติ

### Slide 17 — 🚀 Agentic RAG เต็มรูปแบบ
- Agent + RAG + Memory = Agentic RAG
- ค้นหา + คิด + จำ + ตอบ
- ตัวอย่าง: Study Assistant

### Slide 18 — 📊 สรุป Part 2
- Agent = AI ที่คิด + ใช้เครื่องมือ
- Agentic RAG = Agent + RAG + Memory
- Key: คุณภาพข้อมูลสำคัญที่สุด

---

## 🔧 Buffer (15:50-16:00) — 10 นาที
- ช่วย troubleshoot Error 429
- ตอบคำถามก่อนเริ่มแบบฝึกหัด

---

## 🧪 Part 3: แบบฝึกหัด (16:00-16:50) — 2 Slides

### Slide 19 — แบบฝึกหัด (10 คะแนน)
- 🔗 [เปิดใน Colab](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/th/4hr/agentic_rag_4hr_homework.ipynb)
- 3 ขั้นตอน:
  1. Chunk + Embed + Search (3 คะแนน)
  2. Agent + Custom Tool (3 คะแนน)
  3. RAG Agent + LLM-as-Judge (4 คะแนน)
- ⏰ **Deadline: 24 มี.ค. 2569 23:59 น.**

### Slide 20 — 📋 วิธีส่งงาน
- Download .ipynb จาก Colab
- ส่งผ่าน **[ช่องทางที่กำหนด]**
- ✅ Run "ตรวจสอบคำตอบ" ก่อนส่ง!

---

## 🎬 Closing (16:50-17:00) — 3 Slides

### Slide 21 — 📊 สรุป 4 ชั่วโมง
| Part | เนื้อหา |
|------|--------|
| Part 1 | Data → Chunk → Embed → Qdrant → Retrieve |
| Part 2 | Agent → Tool → RAG Agent → Agentic RAG |
| Part 3 | แบบฝึกหัด + LLM-as-Judge |

### Slide 22 — 🏆 Certificate
- ส่งแบบฝึกหัดครบ → รับ Certificate
- ดาวน์โหลดที่ [myhero.megawiz.co.th](https://myhero.megawiz.co.th/student-portal/)

### Slide 23 — Thank You
- _"The best way to learn AI is to build with AI."_
- 📧 ติดต่อ: [ข้อมูลผู้สอน]

---

**Total: 23 Slides** (เหมาะสำหรับ 4 ชม. online)
