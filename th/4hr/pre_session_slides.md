# 📋 Pre-Session Slides: Agentic RAG Workshop

## แนะนำก่อนเริ่มเรียน (15-20 นาที ก่อนวัน workshop)

---

## Slide 1: ปก
- **Agentic RAG: From Zero to Hero**
- Workshop 4 ชั่วโมง
- คณะ ICT มหาวิทยาลัยมหิดล

---

## Slide 2: สิ่งที่จะได้เรียนรู้
- ✂️ เตรียมข้อมูลสำหรับ RAG (Chunk → Embed → VectorDB)
- 🤖 สร้าง AI Agent ด้วย Google ADK
- ⭐ สร้าง **Agentic RAG** — Agent ที่ค้นหา + คิด + ตอบเอง
- 📊 วัดคุณภาพด้วย LLM-as-Judge

---

## Slide 3: Timeline วัน Workshop
| เวลา | ช่วง | กิจกรรม |
|:----:|------|--------|
| 13:00-13:15 | 🎤 Opening | แนะนำตัว, Ground Rules, ตรวจ API Key |
| 13:15-14:20 | 📢 Part 1 | Data Pipeline: Chunk → Embed → Qdrant |
| 14:20-14:35 | ☕ พัก | 15 นาที |
| 14:35-15:50 | 📢 Part 2 | Agent → Tool → RAG Agent → Agentic RAG |
| 15:50-16:00 | 🔧 Buffer | ดูปัญหา Rate Limit, ช่วย troubleshoot |
| 16:00-16:50 | 🧪 Part 3 | แบบฝึกหัด (10 คะแนน) |
| 16:50-17:00 | 🎬 Closing | สรุป, วิธีส่งงาน, Certificate, Q&A |

---

## Slide 3.5: 🌐 Ground Rules — สอน Online

### การสื่อสาร
- 💬 **ถามผ่าน Chat** ได้ตลอดเวลา — TA จะตอบ
- 🎤 **เปิดไมค์ถามได้** ช่วง Q&A และช่วงแบบฝึกหัด
- 📷 **เปิดกล้องไม่บังคับ** แต่ชอบเห็นหน้าทุกคน 😊

### Troubleshooting
- ⚠️ **Error 429 (Rate Limit)** — รอ 1-2 นาที แล้ว Run ใหม่ (40 คนรันพร้อมกัน อาจเกิดบ่อย)
- 🔄 **Colab ค้าง** — Runtime → Restart session → Run ใหม่ตั้งแต่ต้น
- 🆘 **ติดปัญหา** — อย่าเงียบ! พิมพ์ถามใน Chat ทันที

---

## Slide 4: 🌐 ลงทะเบียน — hero.megawiz.co.th

### ขั้นตอนลงทะเบียน
1. เข้า **[hero.megawiz.co.th](https://hero.megawiz.co.th/)**
2. กรอก **อีเมล** เพื่อรับ OTP
3. ใส่รหัส OTP ที่ได้จากอีเมล → เข้าสู่ระบบ
4. กรอก **ชื่อ-นามสกุล** และ **รหัสนักศึกษา**

### สิ่งที่จะได้จากระบบ
- 📄 เอกสารประกอบการเรียน (Notebook)
- 📝 แบบฝึกหัด + ส่งงาน
- 🏆 **Certificate** หลังจบ workshop

> 🎯 **ลงทะเบียนก่อนมาเรียน** เพื่อให้วัน workshop ไม่ต้องเสียเวลา

---

## Slide 5: ⚠️ สิ่งที่ต้องเตรียมก่อนมาเรียน

1. ✅ **ลงทะเบียน** ที่ [hero.megawiz.co.th](https://hero.megawiz.co.th/)
2. 🔑 **สร้าง Gemini API Key**
3. 💻 เปิด **Google Colab** ได้
4. 🧪 ทดสอบ API Key ล่วงหน้า

---

## Slide 5.5: 💻 Google Colab เบื้องต้น

### Google Colab คืออะไร?
- **Notebook** บน cloud — เขียน Python ได้เลย ไม่ต้องติดตั้งอะไร
- ใช้ผ่าน **Browser** (Chrome แนะนำ)
- ฟรี! มี GPU/TPU ให้ใช้

### วิธีเปิดใช้งาน
1. เข้า [colab.research.google.com](https://colab.research.google.com)
2. Login ด้วย **Google Account**
3. คลิก **"New Notebook"** เพื่อสร้าง notebook ใหม่

### สิ่งที่ต้องรู้
- **Cell** = กล่องเขียนโค้ด → กด `Shift + Enter` เพื่อ Run
- **Code Cell** = เขียน Python / **Text Cell** = เขียนข้อความ
- ▶️ **Run ทีละ cell** ตามลำดับ (บนลงล่าง)
- ⚡ **Runtime → Restart session** ถ้า notebook ค้าง

### Tips
- 📁 ไฟล์จะอยู่ใน Google Drive (`Colab Notebooks/`)
- 🔑 เก็บ API Key ใน **Secrets** (ไม่ใช่ใน code!)
- 💾 Colab **Auto-save** ให้ — ไม่ต้องกด save เอง

---

## Slide 5.6: 📋 วิธี Copy Notebook ตัวอย่างไปไว้ใน Drive ตัวเอง

### ทำไมต้อง Copy?
- Notebook ที่อาจารย์แชร์เป็น **"View only"** — แก้ไขไม่ได้
- ต้อง **Copy ไปไว้ใน Drive ตัวเอง** ก่อนจึงจะ Run / แก้โค้ดได้

### ขั้นตอน
1. เปิด Notebook ตัวอย่างจากลิ้งก์ที่ได้รับ
2. คลิก **File → Save a copy in Drive** (บนเมนูบาร์)
3. Colab จะสร้างสำเนาใน Google Drive อัตโนมัติ
4. ไฟล์ใหม่จะมีชื่อ `Copy of ...` — เปลี่ยนชื่อได้ตามต้องการ
5. เริ่ม Run / แก้โค้ดได้เลย ✅

### ⚠️ สิ่งที่ต้องระวัง
- **อย่าแก้ไขไฟล์ต้นฉบับ** — ถ้าไม่ Copy จะแก้ไม่ได้อยู่แล้ว
- Copy จะอยู่ใน **My Drive → Colab Notebooks/**
- ถ้า Copy หลายครั้ง จะมีหลายไฟล์ → ลบตัวที่ไม่ใช้ได้

### 🔗 Notebook ที่ใช้ในวัน Workshop
| Notebook | ลิ้งก์เปิด Colab |
|:---------|:---------|
| 📓 เนื้อหาหลัก | [agentic_rag_4hr.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/th/4hr/agentic_rag_4hr.ipynb) |
| 📝 แบบฝึกหัด | [agentic_rag_4hr_homework.ipynb](https://colab.research.google.com/github/megacare-dev/agentic_rag_workshop/blob/main/th/4hr/agentic_rag_4hr_homework.ipynb) |

> 🎯 **Copy ก่อน → แก้ไขทีหลัง** — ทำแค่ครั้งเดียวต่อ Notebook

---

## Slide 6: 🔑 วิธีสร้าง Gemini API Key (Step-by-Step)

1. เข้า **[aistudio.google.com](https://aistudio.google.com)**
2. Login ด้วย Google Account
3. คลิก **"Get API Key"** (มุมบนซ้าย)
4. คลิก **"Create API Key"**
5. เลือก Project → **Create API key in new project**
6. **Copy** API Key เก็บไว้ (ห้ามแชร์!)

> ⚠️ Free tier: **15 RPM** (requests/minute) — เพียงพอสำหรับ workshop

---

## Slide 7: 🔒 วิธีเก็บ API Key ใน Colab Secrets

1. เปิด Google Colab
2. คลิก 🔑 **ไอคอนกุญแจ** (แถบซ้าย) → "Secrets"
3. คลิก **"Add new secret"**
4. Name: `GOOGLE_API_KEY`
5. Value: วาง API Key ที่ copy มา
6. เปิด toggle **"Notebook access"** ✅

> 🎯 ทำแค่ครั้งเดียว — ใช้ได้ทุก notebook

---

## Slide 8: 🚨 Error 429 — Rate Limit คืออะไร?

```
google.api_core.exceptions.ResourceExhausted: 429
You exceeded your current quota
```

**แปลว่า:** ส่ง request เร็ว/เยอะเกินไป

### Free Tier Limits (Gemini 2.5 Flash):
| Limit              | ค่า        |
| ------------------ | --------- |
| RPM (Requests/min) | 15        |
| TPM (Tokens/min)   | 1,000,000 |
| RPD (Requests/day) | 1,500     |

---

## Slide 9: 💡 วิธีแก้ Error 429

### แก้ทันที:
1. **รอ 1-2 นาที** แล้ว run ใหม่
2. **อย่า run cell ซ้ำเร็วๆ** — รอ output ก่อน

### แก้ถาวร (แนะนำ):
3. เพิ่ม **retry + sleep** ในโค้ด:
```python
import time
for attempt in range(3):
    try:
        response = client.models.generate_content(...)
        break
    except Exception as e:
        if '429' in str(e):
            print(f'⏳ Rate limit, รอ {30*(attempt+1)} วินาที...')
            time.sleep(30 * (attempt + 1))
        else:
            raise
```

---

## Slide 10: 🧪 ทดสอบก่อนมาเรียน

เปิด Colab → สร้าง notebook ใหม่ → Run:

```python
# 1. ตั้ง API Key
from google.colab import userdata
import os
os.environ['GOOGLE_API_KEY'] = userdata.get('GOOGLE_API_KEY')

# 2. ทดสอบ
from google import genai
client = genai.Client(api_key=os.environ['GOOGLE_API_KEY'])
resp = client.models.generate_content(
    model='gemini-3.1-pro-preview',
    contents='สวัสดี ตอบสั้นๆ 1 ประโยค'
)
print(f'✅ สำเร็จ: {resp.text}')
```

ถ้าเห็น ✅ = พร้อมเรียน!

---

## Slide 11: 📋 Checklist ก่อนมาเรียน

- [ ] ลงทะเบียนที่ [hero.megawiz.co.th](https://hero.megawiz.co.th/) แล้ว
- [ ] มี Google Account
- [ ] สร้าง Gemini API Key แล้ว
- [ ] เก็บ Key ใน Colab Secrets แล้ว
- [ ] Run ทดสอบผ่าน → เห็น ✅

> 🎯 **ทำ checklist ครบ → วัน workshop จะราบรื่นมาก!**

---

## Slide 12: 🏆 Certificate

หลังจบ workshop และส่งแบบฝึกหัดครบ:
- ระบบตรวจให้คะแนนอัตโนมัติ (AI Grading)
- รับ **Certificate** ผ่านระบบ [hero.megawiz.co.th](https://hero.megawiz.co.th/)
- ดาวน์โหลดได้ทันที (PDF)

---

## Slide 13: ❓ มีปัญหา?

| ปัญหา              | วิธีแก้                                   |
| ----------------- | -------------------------------------- |
| เข้า myhero ไม่ได้   | ตรวจอีเมล spam / ลองใหม่                 |
| ไม่ได้รับ OTP        | เช็ค spam folder / รอ 1 นาที             |
| API key not valid | สร้าง key ใหม่ที่ aistudio.google.com      |
| Error 429         | รอ 1-2 นาที แล้วลองใหม่                   |
| Colab ช้า          | Runtime → Change runtime type → T4 GPU |

- ถามอาจารย์ / TA ได้เลย
