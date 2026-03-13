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
| Part     |     เวลา     | เนื้อหา                                  |
| -------- | :----------: | -------------------------------------- |
| 📢 Part 1 | 1 ชม. 20 นาที | Data Pipeline: Chunk → Embed → Qdrant  |
| ☕ พัก     |    10 นาที    |                                        |
| 📢 Part 2 | 1 ชม. 30 นาที | Agent → Tool → RAG Agent → Agentic RAG |
| 🧪 Part 3 |    1 ชม.     | แบบฝึกหัด (10 คะแนน) + Q&A               |

---

## Slide 4: 🌐 ลงทะเบียน — myhero.megawiz.co.th

### ขั้นตอนลงทะเบียน
1. เข้า **[myhero.megawiz.co.th/student-portal](https://myhero.megawiz.co.th/student-portal/)**
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

1. ✅ **ลงทะเบียน** ที่ [myhero.megawiz.co.th/student-portal](https://myhero.megawiz.co.th/student-portal/)
2. 🔑 **สร้าง Gemini API Key**
3. 💻 เปิด **Google Colab** ได้
4. 🧪 ทดสอบ API Key ล่วงหน้า

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
    model='gemini-2.5-flash',
    contents='สวัสดี ตอบสั้นๆ 1 ประโยค'
)
print(f'✅ สำเร็จ: {resp.text}')
```

ถ้าเห็น ✅ = พร้อมเรียน!

---

## Slide 11: 📋 Checklist ก่อนมาเรียน

- [ ] ลงทะเบียนที่ [myhero.megawiz.co.th/student-portal](https://myhero.megawiz.co.th/student-portal/) แล้ว
- [ ] มี Google Account
- [ ] สร้าง Gemini API Key แล้ว
- [ ] เก็บ Key ใน Colab Secrets แล้ว
- [ ] Run ทดสอบผ่าน → เห็น ✅

> 🎯 **ทำ checklist ครบ → วัน workshop จะราบรื่นมาก!**

---

## Slide 12: 🏆 Certificate

หลังจบ workshop และส่งแบบฝึกหัดครบ:
- ระบบตรวจให้คะแนนอัตโนมัติ (AI Grading)
- รับ **Certificate** ผ่านระบบ [myhero.megawiz.co.th](https://myhero.megawiz.co.th/student-portal/)
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
