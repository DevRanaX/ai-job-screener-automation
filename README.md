# 🧠 Smart Job Application Screener & Auto-Reply (n8n Workflow)

An enterprise-grade, **AI-powered HR screening automation pipeline** built on **n8n**. This system automates the entire recruitment screening funnel—from receiving job applications, scoring them using LLMs, logging database entries, to executing smart, automated candidate communications.


## 🚀 Key Features

* **Instant Collection:** Captures applicant data (Name, Email, Skills, Experience, Cover Letter) via an interactive **n8n Form**.
* **AI Candidate Evaluation:** Utilizes **Groq (GPT-OSS LLM)** to analyze and grade the applicant's profile and experience, returning a clean, dynamic fit score (0-100).
* **Automated Applicant Tracking (ATS):** Updates and logs candidate information along with the generated AI-Score into **Airtable** in real-time.
* **Smart Decision Router:** Filters candidates instantly using conditional routing logic (Threshold: >70 Score).
* **Automated Candidate Communication:**
  - **High-Fit Candidates (>70):** Triggers an immediate "High-Fit Candidate Alert" email to the internal HR team and sends a congratulations/shortlist email to the candidate.
  - **Low-Fit Candidates (<70):** Sends a polite, automated rejection/talent-pool notification email to keep the employer brand warm.

---

## 🛠️ System Architecture


```text
[Form Submission] ➔ [LLM Evaluation (Groq)] ➔ [Log to Airtable]
                                                    │
                                             [IF Score > 70?]
                                             /              \
                                          (Yes)             (No)
                                           /                  \
                    [Internal HR Alert + Shortlist Email]   [Polite Rejection Email]

# ai-job-screener-automation
An automated AI-powered recruitment screening system built with n8n, Airtable, Groq (LLM), and Gmail that scores candidates and automates customized HR &amp; candidate email pipelines.


```
## 📦 How to Deploy

### 1. Prerequisites
* **A running n8n instance.**[cite: 1]
* **An active Airtable account and Base setup** with fields matching: `Name`, `Email`, `Experience`, `Skills`, `CoverLatter`, and `AI-Score`.[cite: 1]
* **Groq API Key** (or any model configured in the LLM Chain).[cite: 1]
* **Gmail credentials** configured in n8n.[cite: 1]

### 2. Import Workflow
1. **Download** the `smart-job-screener.json` file from this repository.[cite: 1]
2. **Open your n8n dashboard**, click on the menu icon on the top left, and select **Import from File**.[cite: 1]
3. **Load the JSON file**, link your credentials for Groq, Airtable, and Gmail, and click **Publish**![cite: 1]

---

## 🧑‍💻 Built With
* **n8n** - Workflow Orchestration & Logic[cite: 1]
* **LangChain & Groq** - LLM Integration & Fast Inference[cite: 1]
* **Airtable** - Cloud Database & ATS Ledger[cite: 1]
* **Gmail API** - Unified Notification & Auto-Response Mailer[cite: 1]
