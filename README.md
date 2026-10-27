# SEC Regulatory Surveillance & Granular Business Triage Pipeline

A Python-based, local-first automation tool designed for compliance officers, legal counsel, and risk architects. It ingests official SEC RSS feeds, universally processes HTML web pages and direct PDF filings, and leverages a local Large Language Model (e.g., Qwen 2.5 via LM Studio) to generate executive, cost-sensitive compliance digest PDFs.

## 
The Core Problem: Monitoring high-volume, unstructured regulatory data and rule filings manually is inefficient.
The Solution: An automated pipeline that fetches, structures, and processes SEC/regulatory documents locally.
The Tech Stack: Built with Python, structured database/storage components, and local parsing tools.

---

## Key Architectural Principles

- **Data Privacy & Local Execution:** Operates entirely locally. Regulatory payloads are parsed locally and evaluated via a local LLM inference server (`localhost:1234`), ensuring zero exposure of proprietary firm workflows or data to external third-party APIs.
- **Rulemaking Stage Awareness:** Distinguishes between binding final rules/enforcement actions, discretionary comment windows (Requests for Comment), and supervisory awareness intelligence (exam priorities and enforcement press releases).
- **Fit-for-Purpose & Cost-Sensitive:** Strips out speculative hypotheses. If a release does not impact a specific business line, that division is cleanly omitted. Prevents operational bloat by avoiding false alarms on proposed rules.
- **Fact-Based & Subjectivity-Free:** Strictly prohibits arbitrary cost estimates, subjective cost adjectives (e.g., "low cost"), or ungrounded resource allocation percentages. All prescriptive actions anchor to recognized regulatory frameworks or standard industry control functions.


## Code

- **The source code for this project is hosted in a private repository to protect proprietary logic/intellectual property. Code samples or an architecture walkthrough can be provided to recruiters upon request.

---

## Disclaimer

This software and its associated codebase (`sec-regulatory-pipeline`) are developed strictly for **educational, internal research, and informational automation purposes**. 

* **Not Legal or Regulatory Advice:** This tool aggregates and processes publicly available regulatory filings (such as SEC releases, SEC enforcement actions, and rule proposals). It does not constitute legal, compliance, or regulatory advice. 
* **No Guarantee of Accuracy:** Automated parsers, scripts, and local models can occasionally introduce parsing errors, hallucinations, or data omissions. Users are solely responsible for independently verifying any regulatory text, filing data, or analytical output against official source materials (e.g., SEC.gov or the Federal Register).
* **Limitation of Liability:** The author(s) assume no liability or responsibility for any errors or omissions in the content of this pipeline or for any compliance breaches, operational failures, or financial losses resulting from its use.

---

## Prerequisites

1. **Python 3.10+** installed on your local machine.
2. **LM Studio** (or an equivalent local OpenAI-compatible inference server) running locally on `http://localhost:1234` with an appropriate model loaded (e.g., `qwen2.5-7b-instruct`).
