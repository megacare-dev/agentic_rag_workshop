# 📋 Pre-Session Slides: Agentic RAG Workshop

## Before You Start (15–20 minutes before the workshop)

---

## Slide 1: Cover
- **Agentic RAG: From Zero to Hero**
- 4-hour Workshop
- Faculty of ICT, Mahidol University

---

## Slide 2: What You Will Learn
- ✂️ Prepare data for RAG (Chunk → Embed → VectorDB)
- 🤖 Build AI Agents with Google ADK
- ⭐ Build **Agentic RAG** — an agent that can search + reason + answer on its own
- 📊 Evaluate quality with LLM-as-Judge

---

## Slide 3: Workshop Timeline
| Part      |    Duration    | Content                                  |
| --------- | :------------: | ---------------------------------------- |
| 📢 Part 1 | 1 hr 20 mins   | Data Pipeline: Chunk → Embed → Qdrant    |
| ☕ Break   |    10 mins     |                                          |
| 📢 Part 2 | 1 hr 30 mins   | Agent → Tool → RAG Agent → Agentic RAG   |
| 🧪 Part 3 |     1 hr       | Exercises (10 points) + Q&A              |

---

## Slide 4: 🌐 Registration — myhero.megawiz.co.th

### Registration Steps
1. Go to **[myhero.megawiz.co.th/student-portal](https://myhero.megawiz.co.th/student-portal/)**
2. Enter your **email** to receive an OTP
3. Enter the OTP sent to your email → log in
4. Fill in your **full name** and **student ID**

### What You Will Get from the System
- 📄 Learning materials (Notebooks)
- 📝 Exercises + assignment submission
- 🏆 **Certificate** after completing the workshop

> 🎯 **Please register before attending** so we do not waste time on the workshop day

---

## Slide 5: ⚠️ What You Need to Prepare Before Class

1. ✅ **Register** at [myhero.megawiz.co.th/student-portal](https://myhero.megawiz.co.th/student-portal/)
2. 🔑 **Create a Gemini API Key**
3. 💻 Make sure you can open **Google Colab**
4. 🧪 Test your API Key in advance

---

## Slide 6: 🔑 How to Create a Gemini API Key (Step-by-Step)

1. Go to **[aistudio.google.com](https://aistudio.google.com)**
2. Log in with your Google Account
3. Click **"Get API Key"** (top-left corner)
4. Click **"Create API Key"**
5. Select a project → **Create API key in new project**
6. **Copy** your API Key and keep it safe (**do not share it!**)

> ⚠️ Free tier: **15 RPM** (requests per minute) — enough for this workshop

---

## Slide 7: 🔒 How to Store Your API Key in Colab Secrets

1. Open Google Colab
2. Click the 🔑 **key icon** in the left sidebar → "Secrets"
3. Click **"Add new secret"**
4. Name: `GOOGLE_API_KEY`
5. Value: paste the API Key you copied
6. Turn on the **"Notebook access"** toggle ✅

> 🎯 You only need to do this once — it will work for all notebooks

---

## Slide 8: 🚨 What Is Error 429 — Rate Limit?

```python
google.api_core.exceptions.ResourceExhausted: 429
You exceeded your current quota
````

**It means:** you are sending requests too quickly or too many times

### Free Tier Limits (Gemini 2.5 Flash):

| Limit              | Value     |
| ------------------ | --------- |
| RPM (Requests/min) | 15        |
| TPM (Tokens/min)   | 1,000,000 |
| RPD (Requests/day) | 1,500     |

---

## Slide 9: 💡 How to Fix Error 429

### Immediate Fix:

1. **Wait 1–2 minutes** and run again
2. **Do not rerun cells too quickly** — wait for the output first

### Permanent Fix (Recommended):

3. Add **retry + sleep** to your code:

```python
import time
for attempt in range(3):
    try:
        response = client.models.generate_content(...)
        break
    except Exception as e:
        if '429' in str(e):
            print(f'⏳ Rate limit hit, waiting {30*(attempt+1)} seconds...')
            time.sleep(30 * (attempt + 1))
        else:
            raise
```

---

## Slide 10: 🧪 Test Before Class

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
    contents='Hello, reply in one short sentence.'
)
print(f'✅ Success: {resp.text}')
```

If you see ✅ = you are ready!

---

## Slide 11: 📋 Checklist Before Class

* [ ] Registered at [myhero.megawiz.co.th/student-portal](https://myhero.megawiz.co.th/student-portal/)
* [ ] Have a Google Account
* [ ] Created a Gemini API Key
* [ ] Stored the key in Colab Secrets
* [ ] Test run completed successfully → saw ✅

> 🎯 **Complete this checklist → your workshop day will go much more smoothly!**

---

## Slide 12: 🏆 Certificate

After completing the workshop and submitting all exercises:

* The system will grade your work automatically (AI Grading)
* You will receive a **Certificate** via [myhero.megawiz.co.th](https://myhero.megawiz.co.th/student-portal/)
* It can be downloaded immediately as a PDF

---

## Slide 13: ❓ Having Problems?

| Problem              | Solution                                |
| -------------------- | --------------------------------------- |
| Cannot access myhero | Check your spam email / try again       |
| OTP not received     | Check spam folder / wait 1 minute       |
| API key not valid    | Create a new key at aistudio.google.com |
| Error 429            | Wait 1–2 minutes and try again          |
| Colab is slow        | Runtime → Change runtime type → T4 GPU  |

* Feel free to ask the instructor or TA for help
