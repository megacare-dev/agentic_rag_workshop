# 📋 Pre-Session Slides: Agentic RAG Workshop

## Pre-Workshop Prep (15-20 minutes before the workshop)

---

## Slide 1: Cover
- **Agentic RAG: From Zero to Hero**
- 4-hour workshop
- Faculty of ICT, Mahidol University

---

## Slide 2: What you will learn
- ✂️ Prepare data for RAG (Chunk → Embed → VectorDB)
- 🤖 Build an AI Agent using Google ADK
- ⭐ Create an **Agentic RAG** — an agent that searches + thinks + answers on its own
- 📊 Measure quality using LLM-as-Judge

---

## Slide 3: Workshop Timeline
| Part     | Duration     | Content                                 |
| -------- | :----------: | -------------------------------------- |
| 📢 Part 1 | 1h 20m       | Data Pipeline: Chunk → Embed → Qdrant  |
| ☕ Break   | 10m          |                                        |
| 📢 Part 2 | 1h 30m       | Agent → Tools → RAG Agent → Agentic RAG |
| 🧪 Part 3 | 1h           | Exercises (10 pts) + Q&A               |

---

## Slide 4: 🌐 Register — myhero.megawiz.co.th

### Registration steps
1. Go to **[myhero.megawiz.co.th/student-portal](https://myhero.megawiz.co.th/student-portal/)***
2. Enter your **email** to receive an OTP
3. Enter the OTP from email → log in
4. Fill in **Name** and **Student ID**

### What you get from the system
- 📄 Learning materials (Notebook)
- 📝 Exercises + submissions
- 🏆 **Certificate** after completing the workshop

> 🎯 **Register before the workshop** so we can start right away

---

## Slide 5: ⚠️ What to prepare before the workshop

1. ✅ **Register** at [myhero.megawiz.co.th/student-portal](https://myhero.megawiz.co.th/student-portal/)
2. 🔑 **Create a Gemini API Key**
3. 💻 Make sure you can open **Google Colab**
4. 🧪 Test the API Key in advance

---

## Slide 6: 🔑 How to create a Gemini API Key (Step-by-step)

1. Go to **[aistudio.google.com](https://aistudio.google.com)**
2. Sign in with a Google account
3. Click **"Get API Key"** (top-left)
4. Click **"Create API Key"**
5. Choose a project → **Create API key in new project**
6. **Copy** the API key and keep it safe (do not share!)

> ⚠️ Free tier: **15 RPM** (requests/minute) — enough for the workshop

---

## Slide 7: 🔒 Store the API Key in Colab Secrets

1. Open Google Colab
2. Click the 🔑 **key icon** (left sidebar) → "Secrets"
3. Click **"Add new secret"**
4. Name: `GOOGLE_API_KEY`
5. Value: paste the API key
6. Enable the **"Notebook access"** toggle ✅

> 🎯 Do it once — it works for all notebooks

---

## Slide 8: 🚨 Error 429 — What is rate limiting?

```
google.api_core.exceptions.ResourceExhausted: 429
You exceeded your current quota
```

**Meaning:** You are sending requests too fast / too many.

### Free Tier Limits (Gemini 2.5 Flash):
| Limit              | Value     |
| ------------------ | --------- |
| RPM (Requests/min) | 15        |
| TPM (Tokens/min)   | 1,000,000 |
| RPD (Requests/day) | 1,500     |

---

## Slide 9: 💡 How to fix Error 429

### Quick fix:
1. **Wait 1-2 minutes** and run again
2. **Don't run the cell repeatedly** — wait for output first

### Better fix (recommended):
3. Add **retry + sleep** in your code:
```python
import time
for attempt in range(3):
    try:
        response = client.models.generate_content(...)
        break
    except Exception as e:
        if '429' in str(e):
            print(f'⏳ Rate limit, waiting {30*(attempt+1)} seconds...')
            time.sleep(30 * (attempt + 1))
        else:
            raise
```

---

## Slide 10: 🧪 Test before the workshop

Open Colab → create a new notebook → run:

```python
# 1. Set API Key
from google.colab import userdata
import os
os.environ['GOOGLE_API_KEY'] = userdata.get('GOOGLE_API_KEY')

# 2. Test
from google import genai
client = genai.Client(api_key=os.environ['GOOGLE_API_KEY'])
resp = client.models.generate_content(
    model='gemini-2.5-flash',
    contents='Hello, please respond in one short sentence.'
)
print(f'✅ Success: {resp.text}')
```

If you see ✅ = you're ready!

---

## Slide 11: 📋 Pre-workshop checklist

- [ ] Registered at [myhero.megawiz.co.th/student-portal](https://myhero.megawiz.co.th/student-portal/)
- [ ] Have a Google Account
- [ ] Created a Gemini API Key
- [ ] Stored the key in Colab Secrets
- [ ] Ran the test and saw ✅

> 🎯 Complete the checklist to make the workshop run smoothly!

---

## Slide 12: 🏆 Certificate

After completing the workshop and submitting assignments:
- Automatic grading (AI Grading)
- Receive a **Certificate** via [myhero.megawiz.co.th](https://myhero.megawiz.co.th/student-portal/)
- Download instantly (PDF)

---

## Slide 13: ❓ Need help?

| Issue                    | Fix                                              |
| ----------------------- | ------------------------------------------------ |
| Can't access myhero     | Check spam folder / try again                    |
| Didn't receive OTP      | Check spam / wait 1 minute                       |
| API key not valid       | Create a new key at aistudio.google.com          |
| Error 429               | Wait 1-2 minutes and retry                       |
| Colab is slow           | Runtime → Change runtime type → T4 GPU           |

- Ask the instructor / TA anytime
