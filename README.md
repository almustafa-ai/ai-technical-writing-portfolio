<div align="center">

# ✍️ AI Technical Writing Portfolio

### Professional documentation, tutorials, and explainers for AI products and teams

*By Almustafa Emanuel Joseph-Alo — AI Technical Writer | Hausa & French Language Specialist*

[![Profile](https://img.shields.io/badge/GitHub-almustafa--ai-181717?style=flat&logo=github)](https://github.com/almustafa-ai)
[![Specialty](https://img.shields.io/badge/Specialty-AI%20Documentation-blue?style=flat)](https://github.com/almustafa-ai/ai-technical-writing-portfolio)
[![Languages](https://img.shields.io/badge/Languages-Hausa%20%7C%20French%20%7C%20English-green?style=flat)](https://github.com/almustafa-ai)

</div>

---

## What I Do

I write technical documentation that makes AI products understandable, usable, and trusted — for developers, business users, and non-technical audiences alike.

My background is uncommon in technical writing: **15+ years as a professional Hausa and French translator and localiser**, combined with hands-on technical writing experience at **Turing Enterprises**, where I documented Python, JSON, JavaScript, and frontend/backend systems.

This means I bring three things most technical writers cannot:

- **Linguistic precision** — 15 years of professional translation trains you to find the exact right word, not approximately the right word
- **Cultural intelligence** — I understand how AI fails multilingual users and how to document AI products for African and francophone markets
- **Technical fluency** — I have worked directly with developers, understood codebases, and explained complex systems to non-technical audiences

---

## Services

| Service | Description | Best for |
|---|---|---|
| **API Documentation** | Getting Started guides, endpoint references, code examples, error handling | Developer-facing products |
| **AI Concept Explainers** | Plain-language explanations of ML concepts for business audiences | Non-technical stakeholders |
| **Tutorials & How-to Guides** | Step-by-step guides with troubleshooting sections | User onboarding |
| **Multilingual AI Docs** | Documentation review and adaptation for Hausa and French markets | African & francophone expansion |
| **Documentation Audits** | Gap analysis and quality review of existing documentation | Startups with incomplete docs |
| **Prompt Engineering Guides** | Best-practice documentation for teams using LLMs internally | Enterprise AI adoption |

---

## Writing Samples

---

### Sample 01 — API Documentation

**Type:** Getting Started Guide
**Audience:** Developers new to a REST API
**Demonstrates:** Technical accuracy, code annotation, clear structure, error handling

---

#### Getting Started with the OpenWeatherMap API

OpenWeatherMap provides real-time and forecast weather data for any location worldwide via a simple REST API. This guide will have you making your first API call in under 10 minutes.

**Prerequisites**

Before you begin, you will need:
- A free OpenWeatherMap account (sign up at openweathermap.org)
- Your API key (found in your account dashboard under "My API Keys")
- Python 3.7+ installed, or any HTTP client (curl, Postman)

**Base URL**

All API requests are made to the following base URL:
https://api.openweathermap.org/data/2.5/

**Authentication**

OpenWeatherMap uses API key authentication. Pass your key as a query parameter on every request:
?appid=YOUR_API_KEY

**Your First Request — Current Weather**

To retrieve current weather for a city, make a GET request to the `/weather` endpoint:

```python
import requests

API_KEY = "your_api_key_here"
CITY = "Abuja"

url = f"https://api.openweathermap.org/data/2.5/weather"

params = {
    "q": CITY,
    "appid": API_KEY,
    "units": "metric"  # Use 'imperial' for Fahrenheit
}

response = requests.get(url, params=params)
data = response.json()

print(f"City: {data['name']}")
print(f"Temperature: {data['main']['temp']}°C")
print(f"Condition: {data['weather'][0]['description']}")
```

**Example Response**

A successful request returns a JSON object. The key fields you will use most often:

```json
{
  "name": "Abuja",
  "main": {
    "temp": 31.4,
    "feels_like": 34.2,
    "humidity": 62
  },
  "weather": [
    {
      "main": "Clouds",
      "description": "scattered clouds"
    }
  ],
  "wind": {
    "speed": 3.6
  }
}
```

| Field | Type | Description |
|---|---|---|
| `name` | string | City name as recognised by the API |
| `main.temp` | float | Current temperature in the unit specified |
| `main.humidity` | integer | Relative humidity as a percentage |
| `weather[0].description` | string | Human-readable weather condition |
| `wind.speed` | float | Wind speed in metres per second (metric) |

**Common Errors and How to Fix Them**

| Error code | Message | Cause | Fix |
|---|---|---|---|
| `401` | Invalid API key | Key is wrong or not yet activated | Check your dashboard — new keys take up to 2 hours to activate |
| `404` | City not found | City name is misspelled or not recognised | Try passing coordinates instead: `lat=9.07&lon=7.40` |
| `429` | Too many requests | Free tier limit exceeded | Implement request caching or upgrade your plan |

**Next Steps**

- [5-day forecast endpoint](https://openweathermap.org/forecast5) — retrieve weather predictions in 3-hour intervals
- [Geocoding API](https://openweathermap.org/api/geocoding-api) — convert city names to coordinates for more precise requests
- [Units of measurement](https://openweathermap.org/weather-data) — full reference for metric, imperial, and standard units

---

### Sample 02 — AI Concept Explainer

**Type:** Plain-language explainer
**Audience:** Business decision-makers with no ML background
**Demonstrates:** Clarity, analogy-based explanation, structure, practical framing

---

#### What Is Retrieval-Augmented Generation (RAG) — And Why Does It Matter for Your Business?

You have probably noticed that AI assistants sometimes confidently state things that are wrong — or that they cannot answer questions about your company's internal data, recent events, or specialised industry knowledge.

Retrieval-Augmented Generation (RAG) is the approach that fixes this. Here is what it is, how it works, and why it matters.

**The core problem RAG solves**

A standard large language model (LLM) like GPT-4 or Claude is trained on data up to a certain date. After that cutoff, it knows nothing about what has happened in the world. More importantly, it knows nothing about *your* organisation — your products, your policies, your client history, your internal documents.

Asking a standard LLM about your company is like asking a very well-read stranger who has never met you to answer questions about your personal life. They will sound confident. They will often be wrong.

**How RAG works — the reference library analogy**

Think of how a professional translator works. Before translating a specialised document — a legal contract, a medical report, a technical manual — an experienced translator does not rely purely on memory. They consult reference materials: glossaries, style guides, previous translations of similar documents, client-specific terminology lists.

RAG gives AI the same ability. When a user asks a question, the system:

1. **Searches** a connected knowledge base — your documents, database, website, or any structured data source
2. **Retrieves** the most relevant passages or records
3. **Passes** those retrieved pieces to the language model alongside the question
4. **Generates** a response grounded in your actual data, not just training memory

The model is no longer guessing. It is reading your documents and answering based on what is actually there.

**What this means practically**

| Without RAG | With RAG |
|---|---|
| AI answers from training data only | AI answers from your documents and data |
| Knowledge cutoff limits accuracy | Always current — update your docs, update the AI |
| Cannot reference internal policies | Can cite specific policy documents |
| Hallucinations are common | Responses are grounded and verifiable |
| One-size-fits-all responses | Responses tailored to your organisation |

**When RAG is the right choice**

RAG is particularly valuable when:
- Your use case requires up-to-date information (news, market data, recent policy changes)
- You need the AI to reference proprietary internal knowledge
- Accuracy and verifiability matter more than creativity
- You need to cite sources for compliance or audit purposes

**The bottom line**

RAG is the bridge between the general intelligence of large language models and the specific knowledge your organisation actually needs. It is one of the most practical and immediately deployable AI techniques available today — and understanding it is the first step to knowing whether it belongs in your AI strategy.

---

### Sample 03 — Tutorial / How-to Guide

**Type:** Step-by-step developer tutorial
**Audience:** Beginner Python developers
**Demonstrates:** Clear steps, code examples, troubleshooting section, professional structure

---

#### How to Summarise Text Using the Claude API in Python

In this tutorial you will build a simple Python script that sends text to the Claude API and receives a concise summary in return. By the end you will have a reusable function you can integrate into any Python project.

**What you will build**

A Python function that:
- Accepts any block of text as input
- Sends it to the Claude API with a summarisation instruction
- Returns a clean, concise summary
- Handles common errors gracefully

**Prerequisites**

- Python 3.8 or higher
- An Anthropic API key (get one at console.anthropic.com)
- Basic familiarity with Python functions and pip

**Step 1 — Install the Anthropic SDK**

Open your terminal and run:

```bash
pip install anthropic
```

Verify the installation:

```bash
python -c "import anthropic; print('SDK installed successfully')"
```

**Step 2 — Store your API key securely**

Never hardcode your API key in your script. Store it as an environment variable instead:

On Mac/Linux:
```bash
export ANTHROPIC_API_KEY="your_api_key_here"
```

On Windows (Command Prompt):
```bash
set ANTHROPIC_API_KEY=your_api_key_here
```

**Step 3 — Write the summarisation function**

Create a new file called `summarise.py` and add the following code:

```python
import anthropic
import os

def summarise_text(text: str, max_words: int = 100) -> str:
    """
    Summarise a block of text using the Claude API.
    
    Args:
        text: The text you want to summarise
        max_words: Approximate maximum word count for the summary (default: 100)
    
    Returns:
        A concise summary of the input text
    """
    
    # Initialise the client — automatically reads ANTHROPIC_API_KEY
    client = anthropic.Anthropic()
    
    # Build the prompt
    prompt = f"""Please summarise the following text in approximately {max_words} words. 
Focus on the main points and key information. Write in clear, plain language.

Text to summarise:
{text}"""
    
    # Send the request
    message = client.messages.create(
        model="claude-opus-4-5",
        max_tokens=300,
        messages=[
            {"role": "user", "content": prompt}
        ]
    )
    
    # Extract and return the summary
    return message.content[0].text


# Example usage
if __name__ == "__main__":
    sample_text = """
    Artificial intelligence is transforming industries across the globe. 
    In healthcare, AI systems are helping doctors diagnose diseases earlier 
    and more accurately than ever before. In education, personalised AI tutors 
    are adapting to individual student learning styles. In manufacturing, 
    predictive AI is reducing equipment failures and cutting downtime. 
    However, these advances also raise important questions about employment, 
    privacy, and the ethical use of automated decision-making systems.
    """
    
    summary = summarise_text(sample_text, max_words=50)
    print("Summary:")
    print(summary)
```

**Step 4 — Run the script**

```bash
python summarise.py
```

You should see output similar to:
Summary:
AI is revolutionising healthcare, education, and manufacturing through
earlier diagnosis, personalised learning, and predictive maintenance.
However, its rapid adoption raises concerns about jobs, privacy, and
ethical decision-making.

**Step 5 — Use the function in your own project**

Import and call the function from any other Python file:

```python
from summarise import summarise_text

my_text = "Your long text goes here..."
result = summarise_text(my_text, max_words=75)
print(result)
```

**Troubleshooting**

| Problem | Likely cause | Fix |
|---|---|---|
| `AuthenticationError` | API key not found or incorrect | Check your environment variable is set: `echo $ANTHROPIC_API_KEY` |
| `ModuleNotFoundError: anthropic` | SDK not installed | Run `pip install anthropic` again |
| Empty or truncated summary | `max_tokens` too low | Increase `max_tokens` to 500 or higher |
| Rate limit error | Too many requests too quickly | Add `time.sleep(1)` between calls in a loop |
| Summary too long | Model ignoring word limit | Make the word count instruction more explicit in the prompt |

**What to try next**

- Modify the prompt to summarise in a specific language — try Hausa or French
- Add a `bullet_points=True` parameter to return summaries as lists
- Build a simple web interface using Flask or Streamlit
- Process an entire folder of text files in a loop

---

### Sample 04 — Multilingual AI Thought Leadership

**Type:** Industry insight article
**Audience:** AI product teams, NLP researchers, startup founders
**Demonstrates:** Domain expertise, strategic thinking, unique perspective

---

#### Why Your AI Product Is Failing Hausa Speakers — And What to Do About It

You built an AI product. You added multilingual support. You included Hausa in your language list. And yet your adoption numbers in Northern Nigeria are flat, your user feedback from Hausa-speaking testers is lukewarm, and you cannot quite diagnose why.

Here is the diagnosis: **technical multilingual support and genuine linguistic competence are not the same thing.** Your product speaks Hausa the way a phrasebook speaks a foreign language — technically intelligible, culturally hollow, and immediately recognisable as foreign to anyone who actually lives in the language.

**The three gaps that matter most**

*Gap 1 — Register.* Hausa has distinct formal, semi-formal, and colloquial registers that differ not just in vocabulary but in grammar and social function. Products that default to a single register feel wrong to users across all contexts — too formal for casual interaction, too casual for institutional communication.

*Gap 2 — Cultural framing.* Communication in Hausa-speaking communities is embedded in social and religious context. Greetings, acknowledgements, expressions of urgency, and responses to difficulty all carry cultural weight that a linguistically correct but culturally naive AI will miss entirely. Users notice. They disengage.

*Gap 3 — Trust signals.* In communities with limited prior exposure to AI tools, trust is earned through familiarity — familiar language patterns, familiar references, familiar ways of structuring information. A product that feels foreign in its language cannot build the trust necessary for adoption, regardless of how useful its features are.

**What the fix looks like**

It starts with professional linguistic review — not crowdsourced translation, not automated back-translation testing, but evaluation by professional Hausa translators who can assess register, cultural appropriateness, and the subtler dimensions of linguistic naturalness.

It continues with culturally informed prompt design — building system prompts and interaction patterns that reflect how Hausa speakers actually communicate, not how English speakers imagine they do.

And it requires genuine community feedback loops — Hausa-speaking users who are empowered to report not just bugs but cultural mismatches, and product teams equipped to act on that feedback.

The market for AI products in Northern Nigeria and across the Hausa-speaking Sahel is enormous and largely untapped. The barrier to entry for competitors who do it right is high. Getting the language genuinely right — not just technically correct — is the foundation everything else rests on.

---

## Skills Demonstrated Across These Samples

```text
API Documentation      Endpoint reference · Code examples · Error handling · Getting Started guides
Concept Explanation    Analogy-based · Business audience · Plain language · Practical framing  
Tutorial Writing       Step-by-step · Troubleshooting · Code annotation · Next steps
Thought Leadership     Domain expertise · Strategic insight · Unique cultural perspective
Technical Fluency      Python · REST APIs · JSON · LLMs · Prompt engineering
Multilingual Lens      Hausa · French · African market AI · Localisation strategy
```

---

## Engagement & Rates

| Engagement type | Starting rate |
|---|---|
| API documentation (per endpoint set) | From $300 |
| Concept explainer (800–1200 words) | From $200 |
| Full tutorial with troubleshooting | From $250 |
| Documentation audit and gap report | From $400 |
| Monthly retainer (20 hrs/month) | From $1,500 |
| Multilingual AI consulting (per hour) | From $80 |

---

## Let's Work Together

I am available for freelance contracts, retainer arrangements, and research collaboration.

- 📧 **Email:** almustafa.josephalo@gmail.com
- 🌍 **GitHub:** [almustafa-ai](https://github.com/almustafa-ai)
- 📍 **Location:** Abuja, Nigeria — available for remote work worldwide
- 🕐 **Availability:** Open to new clients

---

*Samples in this portfolio are original work created to demonstrate range and capability across documentation types.*