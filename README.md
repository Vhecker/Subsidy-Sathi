# SubsidySaathi V4 — RUNTIME ERROR

**Team:** Arpita · Vedant · Suhana  
**Stack:** Python, Flask, TinyFish, OpenRouter, local TF-IDF RAG, SQLite, HTML/CSS/JavaScript. **No React required.**

## Run

1. Extract the project and open its folder in VS Code.
2. Use Python 3.10+.
3. Install dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

4. Edit the API slots at the **top of `main.py`** (or set environment variables):

   ```python
   TINYFISH_API_KEY = "PASTE_TINYFISH_API_KEY_HERE"
   OPENROUTER_API_KEY = "PASTE_OPENROUTER_API_KEY_HERE"
   OPENROUTER_MODEL = "openrouter/auto"
   ```

   Keep API keys private. Don't commit them to GitHub. OpenRouter model usage may cost money.

5. Start:

   ```bash
   python main.py
   ```

6. Visit **http://127.0.0.1:5000**.

## New in V4

### My Applications tracker

- A beautiful, responsive tracking screen based on the reference screenshot.
- Four metric cards: total records, local drafts, fictional demos, official submissions (not connected).
- Donut graph of draft/demo states, last-seven-days bar chart, individual application milestone timelines.
- Expand a record to see its description, view its document checklist, or visit an official portal.
- Filters for All / My drafts / Demo, a button to add 3 **SIMULATED** sample tracking records, and a button to clear them.
- The dashboard reads actual locally saved drafts from SQLite. A draft is **never** labeled as an official submission.

### Runny the friendly AI chatbot

- Runny responds to small talk (`hi`, `how are you`, `thank you`, etc.) even without an OpenRouter key, with localized starter messages.
- With an OpenRouter key, Runny can converse normally and remember the last few chat messages within the open page.
- Government-scheme questions use local retrieval (RAG) over indexed scheme information, including TinyFish research when you run it.
- Runny is told not to fabricate eligibility, deadline, or government application-status claims. Without an API key, scheme answers fall back to short source notes and general chat is limited to canned responses.
- Main interface language selection supports English, Hindi, Bengali, Telugu. Tracking chart UI labels are presently in English.

### Existing SubsidySaathi features

- Farmer profile, preliminary profile completeness checks for PM-KISAN and PMFBY.
- Document checklist, redacted demo file checks, prefilled sample draft and local draft storage.
- TinyFish research of public official scheme pages and read-only public form field inspection.
- Dark mode, animated farmer and responsive navigation.

## Try the tracking dashboard

1. Click **My Applications**.
2. Click **Show demo progress** to add fictional sample timelines; the sample states are visibly labeled **DEMO / SIMULATED**.
3. Open any sample to inspect its milestones, watch the charts populate, and switch to dark mode.
4. Click **Remove simulated examples** to clear them.
5. Go to **Apply** to save a local draft, then return to **My Applications** to see the draft marked **Not submitted**.

## Safety and factual limits

- No official government submission, payment, KYC, OTP, Aadhaar validation, or live government application tracking is implemented.
- Government portals may restrict automation; TinyFish only does read-only discovery here. No CAPTCHA / OTP bypass.
- The colored tracking statuses are **fictional demo examples**, not official information.
- Do not upload actual identity documents or enter Aadhaar/bank numbers. This is a hackathon prototype. Files uploaded for the optional document check are discarded immediately, and documents are not verified for authenticity.
- Source notes may be sample/offline and can be outdated; verify current requirements on government portals.
- The app is designed for **local demonstration**, not a production multi-user deployment. Add authentication, CSRF protection, consent processes, encryption, and authorized government integrations before any real deployment.

## Folder structure

```
SubsidySaathi_Runtime_Error_v4/
├── main.py
├── requirements.txt
├── templates/
│   └── index.html
├── static/
│   ├── app.js
│   └── style.css
└── README.md
```

## Quick technical validation

- `python -m py_compile main.py`
- `node --check static/app.js` (if Node.js is installed)
- Back-end logic verified with a stubbed Flask test harness; this environment cannot run a real Flask server because Flask isn't installed and package downloads are blocked. API-key calls have not been authenticated or tested against providers in this environment.
