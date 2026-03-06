# 🤖 Agentic RAG Workshop: From Zero to Hero

> สร้าง RAG + AI Agent ตั้งแต่ศูนย์ ด้วย Google ADK & Gemini — รองรับภาษาไทย

---

## 📋 สารบัญ

- [ภาพรวม](#-ภาพรวม)
- [โครงสร้างไฟล์](#-โครงสร้างไฟล์)
- [เนื้อหาแต่ละวัน](#-เนื้อหาแต่ละวัน)
- [สิ่งที่ต้องเตรียม](#-สิ่งที่ต้องเตรียม)
- [วิธีสอน](#-วิธีสอน)
- [วิธีส่งการบ้าน](#-วิธีส่งการบ้าน)
- [วิธีตรวจการบ้าน](#-วิธีตรวจการบ้าน)
- [Tech Stack](#-tech-stack)

---

## 🎯 ภาพรวม

Workshop 3 วัน สำหรับนักศึกษาระดับปริญญาตรี สอนสร้าง **Retrieval-Augmented Generation (RAG)** และ **AI Agent** แบบ end-to-end

```
Day 1: Data Engineering     Day 2: Agent Building     Day 3: Evaluation
─────────────────────       ─────────────────────     ─────────────────
Raw → Chunk → Embed →       Agent + Tool →            RAGAS metrics
VectorDB → Retrieve         RAG Agent →               LLM-as-Judge
                            Multi-Agent →              A/B Experiment
                            Agentic RAG                Capstone ⭐
```

**จุดเด่น:**
- 🇹🇭 รองรับภาษาไทยตลอดทาง (PyThaiNLP, multilingual-e5-large)
- 🛡️ Anti-cheat homework (ข้อมูลเฉพาะตัวจากรหัส นศ.)
- 🤖 ตรวจการบ้านอัตโนมัติด้วย Gemini 2.5 Pro
- 💡 มี「สังเกต」blocks ทุก section ช่วยสรุปแนวคิดสำคัญ
- 🧪 แบบฝึกหัดพร้อม Hints + starter code

---

## 📁 โครงสร้างไฟล์

```
agentic_rag_workshop/
├── README.md
├── LICENSE
├── final_grading.ipynb                # 🏆 ตรวจ Final (3 ด้าน × 3 วัน)
├── day1/
│   ├── day1_data_engineering.ipynb    # 📖 เนื้อหา (87 cells)
│   ├── day1_homework.ipynb            # 📝 การบ้าน (18 cells)
│   └── day1_grading.ipynb             # ✅ ตรวจการบ้าน (11 cells)
├── day2/
│   ├── day2_building_agents.ipynb     # 📖 เนื้อหา (62 cells)
│   ├── day2_homework.ipynb            # 📝 การบ้าน (22 cells)
│   └── day2_grading.ipynb             # ✅ ตรวจการบ้าน (11 cells)
└── day3/
    ├── day3_evaluation.ipynb          # 📖 เนื้อหา (41 cells)
    ├── day3_homework.ipynb            # 📝 การบ้าน (18 cells)
    └── day3_grading.ipynb             # ✅ ตรวจการบ้าน (11 cells)
```

---

## 📚 เนื้อหาแต่ละวัน

### Day 1: Data Engineering Pipeline

| Section | เนื้อหา                                              |
| ------- | -------------------------------------------------- |
| 1.1     | Deduplication — ตรวจจับไฟล์ซ้ำด้วย Hash                 |
| 1.2     | Chunking — ตัดข้อความ (Fixed / Recursive / Semantic) |
| 1.3     | Gemini Multimodal — แปลง PDF ด้วย AI                |
| 1.4     | Thai Tokenization — ตัดคำภาษาไทย                     |
| 1.5     | Embedding — แปลงข้อความเป็น Vector                   |
| 1.6     | Hybrid Search — Dense + Sparse search              |
| 1.7     | Qdrant — Vector Database                           |
| 1.8     | Indexing — นำข้อมูลเข้า VectorDB                       |
| 1.9     | Retrieval — ค้นหาข้อมูล                               |

**การบ้าน (10 คะแนน):** สร้าง pipeline ตั้งแต่ dedup → chunk → embed → search

---

### Day 2: Building Agents with Google ADK

| Section | เนื้อหา                                                    |
| ------- | -------------------------------------------------------- |
| 2.1     | Agent แรก — สร้าง Agent + Instruction                     |
| 2.2     | Tools — Function Tools + Gemini API params               |
| 2.3     | RAG Agent — Agent ค้นหาจาก VectorDB                       |
| 2.4     | Multi-Agent — Sequential / Parallel / Loop / LLM Routing |
| 2.5     | Session Memory — จำบทสนทนา                                |
| 2.6     | Agentic RAG — Study Assistant เต็มรูปแบบ                   |

**การบ้าน (10 คะแนน):** สร้าง Agent + Custom Tool + RAG Agent + Workflow Agent

---

### Day 3: Evaluation & Optimization

| Section | เนื้อหา                                         |
| ------- | --------------------------------------------- |
| 3.1     | RAGAS — วัดคุณภาพ RAG (4 metrics)               |
| 3.2     | Auto Eval Dataset — สร้าง Q&A อัตโนมัติจาก Gemini |
| 3.3     | Agent Testing — Tool Selection + LLM-as-Judge |
| 3.4     | A/B Experiment — เปรียบเทียบ configs            |
| 3.5     | Prompt Engineering — Before vs After          |
| 3.6     | Capstone Project ⭐ — รวมทุกอย่าง 3 วัน           |

**การบ้าน (10 คะแนน):** สร้าง RAG + วัดคุณภาพ + ปรับปรุง + สร้าง Agent + Test

---

## 🔧 สิ่งที่ต้องเตรียม

### สำหรับผู้สอน
1. **Gemini API Key** — ขอที่ [Google AI Studio](https://aistudio.google.com/apikey)
2. อัปโหลด notebooks ขึ้น Google Colab
3. แชร์ข้อมูลตัวอย่าง (PDF) ให้นักศึกษา (Day 1)
4. **สร้าง Google Form** สำหรับรับส่งการบ้าน (ดู [วิธีส่งการบ้าน](#-วิธีส่งการบ้าน))
5. 📊 **[Slide สำหรับสอน](https://docs.google.com/presentation/d/1298peeshWiNPr2JMUTdu1y2A-nuWpGo0N62i25_lvnc/edit)** — Google Slides พร้อมใช้

### สำหรับนักศึกษา
1. **Google Account** (สำหรับ Colab)
2. **Gemini API Key** — เก็บใน Colab Secrets ชื่อ `GOOGLE_API_KEY`

---

## 🎓 วิธีสอน

### แนวทางการสอนแต่ละ Section

```
1. อธิบายคอนเซ็ปต์ (Markdown cell)
2. สาธิตโค้ด (Code cell — Run ด้วยกัน)
3. 💡 สังเกต — สรุปจุดสำคัญ
4. 🧪 แบบฝึกหัด — ให้ลองทำ 5-10 นาที
```

### เวลาโดยประมาณ

| Day   | เวลารวม  | แบ่งเป็น                         |
| ----- | :------: | ------------------------------ |
| Day 1 | ~4-5 ชม. | เนื้อหา 3 ชม. + แบบฝึกหัด 1-2 ชม.  |
| Day 2 | ~4-5 ชม. | เนื้อหา 3 ชม. + แบบฝึกหัด 1-2 ชม.  |
| Day 3 | ~3-4 ชม. | เนื้อหา 2 ชม. + Capstone 1-2 ชม. |

### Tips

- Run `%%time` cells ล่วงหน้า เพราะ pip install + model download ใช้เวลา
- ให้นักศึกษา set Colab Secrets ก่อนเริ่ม
- Section ที่ใช้ `await` ต้อง run ใน Colab (ไม่ใช่ local Python)
- เน้น **💡 สังเกต** blocks — คือ takeaway สำคัญของแต่ละ section

---

## 📤 วิธีส่งการบ้าน

### Flow

```
นักศึกษา                              ผู้สอน
──────────                            ──────────
1. ทำการบ้านใน Colab                   1. สร้าง Google Form (1 ครั้ง)
2. Run ✅ ตรวจสอบคำตอบ                 2. เปิด Google Sheets (auto)
3. File → Download → .ipynb           3. ดาวน์โหลด .ipynb จาก Drive
4. เปิด Google Form                   4. วาง path ใน grading notebook
5. กรอกข้อมูล + อัปโหลดไฟล์             5. Run ตรวจ → ผล append CSV
6. กดส่ง ✅                           6. ตรวจคนต่อไป
```

### ทำไมใช้ Google Form?

| เหตุผล                   | รายละเอียด                           |
| ----------------------- | ----------------------------------- |
| **นักศึกษาไม่ต้องมี GitHub** | Download .ipynb → Upload Form เท่านั้น |
| **1 link แชร์ทุกคน**      | ส่ง link เดียวผ่าน LINE/Classroom      |
| **Auto Spreadsheet**    | ข้อมูลนักศึกษาเข้า Google Sheets ทันที     |
| **ไฟล์เก็บใน Drive**      | อัปโหลดแล้วไม่หาย, ดาวน์โหลดภายหลังได้    |

### 📝 Google Form — โครงสร้าง

สร้าง Google Form 1 ฟอร์มต่อ 1 Day เพื่อความชัดเจน:

#### Form: "ส่งการบ้าน Day X — Agentic RAG Workshop"

| #   | ชื่อ Field                        | ประเภท      | Required | หมายเหตุ                                 |
| --- | ------------------------------- | ----------- | :------: | --------------------------------------- |
| 1   | **ชื่อ-นามสกุล**                   | Short text  |    ✅     | Validation: ≥ 4 ตัวอักษร                  |
| 2   | **รหัสนักศึกษา**                   | Short text  |    ✅     | Validation: regex `^\d{10}$` (10 หลัก)   |
| 3   | **เบอร์โทรศัพท์**                  | Short text  |    ✅     | Validation: regex `^0\d{8,9}$`          |
| 4   | **LINE ID**                     | Short text  |    ❌     |                                         |
| 5   | **Email**                       | Short text  |    ✅     | auto-collect จาก Google Account         |
| 6   | **ไฟล์เนื้อหาและแบบฝึกหัด (.ipynb)** | File upload |    ✅     | ไฟล์ workshop ที่ทำแบบฝึกหัดในคาบ, Max: 20 MB |
| 7   | **ไฟล์การบ้าน (.ipynb)**          | File upload |    ✅     | ไฟล์ homework, Max: 10 MB                |
| 8   | **ปัญหาที่พบ**                     | Paragraph   |    ❌     | ให้นักศึกษาเล่าถ้าติดตรงไหน                   |

#### ตั้งค่า Google Form

| การตั้งค่า                 | ค่า                                                 |
| ----------------------- | -------------------------------------------------- |
| Collect emails          | ✅ Verified                                         |
| Limit to 1 response     | ✅ (แก้ไขหลังส่งได้)                                    |
| File upload destination | สร้าง folder ใน Drive: `Workshop_Submissions/DayX/` |
| Confirmation message    | `✅ ส่งเรียบร้อย! ผลตรวจจะแจ้งภายใน 1 สัปดาห์`            |

#### 🔗 Google Form Links

| Day   | Link                                                                             |
| ----- | -------------------------------------------------------------------------------- |
| Day 1 | [ส่งการบ้าน Day 1: Data Engineering](https://forms.gle/R7EXvPvUfZ286CVh8)          |
| Day 2 | [ส่งการบ้าน Day 2: Building Agents](https://forms.gle/xTQ5eVNKa4fcQVKb8)           |
| Day 3 | [ส่งการบ้าน Day 3: Evaluation & Optimization](https://forms.gle/yLVHh4YVVt3miogm8) |

---

## ✅ วิธีตรวจการบ้าน

### ขั้นตอน

```
1. เปิด Google Sheets (linked จาก Form) → ดาวน์โหลด .ipynb จาก Drive
2. อัปโหลดไฟล์ทั้งหมดเข้า Colab (หรือ Google Drive → mount)
3. เปิด dayX_grading.ipynb ใน Colab
4. Run "Setup" ครั้งเดียว (ติดตั้ง + API Key)
5. Run "ฟังก์ชันตรวจ" ครั้งเดียว
6. วาง path ของไฟล์ .ipynb → Run ตรวจ
7. ผลจะ append เข้า CSV/JSON อัตโนมัติ
8. เปลี่ยน path → ตรวจคนถัดไป
```

### ระบบตรวจอัตโนมัติ

| Feature             | รายละเอียด                                 |
| ------------------- | ----------------------------------------- |
| **AI Grading**      | Gemini 2.5 Pro ตรวจ + ให้ feedback ภาษาไทย |
| **Anti-cheat**      | เปรียบเทียบข้อมูลกับเฉลยจากรหัส นศ.             |
| **Duplicate check** | ตรวจซ้ำ + ถามก่อน overwrite                  |
| **Export**          | CSV + JSON สำหรับนำเข้าระบบเกรด               |

### เกณฑ์คะแนน (ทุก Day = 10 คะแนน)

<details>
<summary><strong>Day 1: Data Engineering Pipeline</strong></summary>

| ขั้นตอน              | คะแนน |
| ------------------ | :---: |
| Duplicates         |   2   |
| Chunking           |   3   |
| Embedding + Search |   3   |
| วิเคราะห์ผล          |   2   |

</details>

<details>
<summary><strong>Day 2: Building Agents</strong></summary>

| ขั้นตอน               | คะแนน |
| ------------------- | :---: |
| Agent + Custom Tool |   3   |
| RAG Agent           |   3   |
| Workflow Agent      |   2   |
| อธิบายผลลัพธ์          |   2   |

</details>

<details>
<summary><strong>Day 3: Evaluation & Optimization</strong></summary>

| ขั้นตอน                  | คะแนน |
| ---------------------- | :---: |
| RAG Pipeline           |   3   |
| วัดคุณภาพ (LLM-as-Judge) |  2.5  |
| ปรับปรุง (Before/After)  |  2.5  |
| Agent + Test           |   2   |

</details>

### ไฟล์ output

- `dayX_scores.csv` — ตารางคะแนน (import Excel/Google Sheets ได้)
- `dayX_scores.json` — รายละเอียด feedback ต่อคน

---

## 🏆 เกณฑ์ให้คะแนนรวม (3 ด้าน)

คะแนนสุดท้ายวัดจาก **3 ด้าน** ด้านละ 10 คะแนน × 3 วัน = **90 คะแนนรวม**

### 🤝 Responsibility (ความรับผิดชอบ) — 10 คะแนน/Day

| เกณฑ์               | คะแนน | วัดจาก                        |
| ------------------ | :---: | ---------------------------- |
| ส่งตรงเวลา          |   3   | timestamp ใน Google Form     |
| กรอกข้อมูลครบถ้วน     |   2   | ชื่อ, รหัส, เบอร์ ครบ            |
| ส่งครบทุก Day        |   3   | ส่ง Day 1 + 2 + 3             |
| Run ✅ ตรวจสอบก่อนส่ง |   2   | มี output จาก validation cell |

### 💪 Determination (ความมุ่งมั่น) — 10 คะแนน/Day

| เกณฑ์                  | คะแนน | วัดจาก                        |
| --------------------- | :---: | ---------------------------- |
| ทำแบบฝึกหัดครบทุกข้อ       |   3   | code cells มี output          |
| ลองปรับ parameter เอง  |   3   | เปลี่ยนค่า ≥ 2 แบบ              |
| อธิบาย/วิเคราะห์ด้วยตัวเอง |   2   | มี comment อธิบายเหตุผล         |
| แก้ปัญหาที่เจอ            |   2   | มี debugging / error handling |

### 💻 Technical (ทักษะเทคนิค) — 10 คะแนน/Day

| เกณฑ์                   | คะแนน | วัดจาก                         |
| ---------------------- | :---: | ----------------------------- |
| Code ทำงานได้            |   3   | ไม่มี error/traceback           |
| ผลลัพธ์ถูกต้อง             |   3   | ตรงกับข้อมูลเฉพาะตัว (anti-cheat) |
| คุณภาพ code             |   2   | อ่านง่าย, มี comment             |
| ไม่ copy / ไม่ใช้ AI ทำแทน |   2   | AI suspected check            |

### 📊 ตารางสรุป

| ด้าน              |  Day 1  |  Day 2  |  Day 3  |   รวม   |
| ---------------- | :-----: | :-----: | :-----: | :-----: |
| 🤝 Responsibility |   /10   |   /10   |   /10   |   /30   |
| 💪 Determination  |   /10   |   /10   |   /10   |   /30   |
| 💻 Technical      |   /10   |   /10   |   /10   |   /30   |
| **รวมต่อ Day**    | **/30** | **/30** | **/30** | **/90** |

> ใช้ `final_grading.ipynb` เพื่อรวมคะแนน 3 ด้านจากทุก Day → export เป็น CSV สุดท้าย

## 🛠️ Tech Stack

| เครื่องมือ                                                                        | ใช้ทำอะไร                   |
| ------------------------------------------------------------------------------ | ------------------------- |
| [Google ADK](https://google.github.io/adk-docs/)                               | สร้าง AI Agent             |
| [Gemini API](https://ai.google.dev/)                                           | LLM (2.5 Flash / 2.5 Pro) |
| [Qdrant](https://qdrant.tech/)                                                 | Vector Database           |
| [multilingual-e5-large](https://huggingface.co/intfloat/multilingual-e5-large) | Text Embedding (รองรับไทย) |
| [RAGAS](https://ragas.io/)                                                     | RAG Evaluation Framework  |
| [PyThaiNLP](https://pythainlp.github.io/)                                      | Thai NLP Toolkit          |
| [Google Colab](https://colab.research.google.com/)                             | Runtime Environment       |

---

## 👤 ผู้จัดทำ

**ปริพล ทู้ไพเราะห์ (Paripol Toopiroh)**
Chief Executive Officer — [Mega Wiz](https://megawiz.co)
🎓 สาขาวิศวกรรมสารสนเทศ รุ่น 1 — คณะวิศวกรรมศาสตร์ สถาบันพระจอมเกล้าเจ้าคุณทหารลาดกระบัง (KMITL)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/paripol-toopiroh-61273a19b/)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=flat&logo=facebook&logoColor=white)](https://www.facebook.com/paripol.toopiroh)

### 🛠️ Tools ที่ใช้สร้าง

| Tool         | รายละเอียด                              |
| ------------ | -------------------------------------- |
| **IDE**      | [Antigravity](https://antigravity.dev) |
| **AI Model** | Claude Opus 4.6 (Thinking)             |

---

## 🤝 Contributing

ยินดีรับ feedback และ contribution จากทุกคนครับ!

- 💬 **ข้อเสนอแนะ** → เปิด [Issue](../../issues) ได้เลย
- 🐛 **พบ Bug** → เปิด [Issue](../../issues) พร้อมระบุขั้นตอนการทำซ้ำ
- 🔀 **Pull Request** → Fork → แก้ไข → ส่ง PR มาได้เลยครับ

> ทุก contribution จะถูกเผยแพร่ภายใต้ license เดียวกัน (CC BY-NC-SA 4.0)

---

## 📄 License

[![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

ผลงานนี้เผยแพร่ภายใต้สัญญาอนุญาต [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-nc-sa/4.0/)

- ✅ ใช้เรียน ใช้สอนได้ฟรี
- ✅ ดัดแปลง ต่อยอดได้
- ✅ ต้องให้เครดิตผู้สร้าง
- ❌ ห้ามนำไปขายหรือใช้เชิงพาณิชย์

ดูรายละเอียดเพิ่มเติมที่ [LICENSE](LICENSE)

---

> _"The best way to learn AI is to build with AI."_
