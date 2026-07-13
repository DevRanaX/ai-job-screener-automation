# 🧠 Smart Job Application Screener & Auto-Reply (n8n Workflow)

An enterprise-grade, **AI-powered HR screening automation pipeline** built on **n8n**. This system automates the entire recruitment screening funnel—from receiving job applications, scoring them using LLMs, logging database entries, to executing smart, automated candidate communications.

---

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
