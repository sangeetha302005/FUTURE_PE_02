# Tools, Technologies & Development Stack

> **Project:** Future Interns — Task 2: AI Content Marketing Using UGC Ads  
> **Repository:** `FUTURE_PE_02`  
> **Author & Intern:** Sangeetha S  
> **Application:** PromptAdsCraft AI Creative Studio  

---

## 1. Complete Technology Stack Overview

```
┌────────────────────────────────────────────────────────────────────────┐
│                      TECHNOLOGY STACK ARCHITECTURE                     │
├─────────────────────┬──────────────────────────┬───────────────────────┤
│ LAYER               │ TECHNOLOGY               │ PURPOSE               │
├─────────────────────┼──────────────────────────┼───────────────────────┤
│ Web Application     │ Streamlit (Python)       │ High-performance Dark │
│ UI & Studio         │                          │ Studio web dashboard  │
├─────────────────────┼──────────────────────────┼───────────────────────┤
│ Synthesis Engine    │ Pure Python (Custom)     │ Deterministic multi-  │
│                     │                          │ variable copy engine  │
├─────────────────────┼──────────────────────────┼───────────────────────┤
│ Data Validation     │ Pydantic v2              │ Input schema bounding │
│                     │                          │ & payload validation  │
├─────────────────────┼──────────────────────────┼───────────────────────┤
│ Automated Testing   │ pytest                   │ 78 unit & integration │
│                     │                          │ automated test suites │
├─────────────────────┼──────────────────────────┼───────────────────────┤
│ Browser Automation  │ Playwright (Chromium)    │ Visual evidence and   │
│ & Verification      │                          │ screenshot capture    │
├─────────────────────┼──────────────────────────┼───────────────────────┤
│ Report Generation   │ ReportLab                │ Professional PDF      │
│                     │                          │ project report build  │
├─────────────────────┼──────────────────────────┼───────────────────────┤
│ Cloud Deployment    │ Streamlit Community Cloud│ Free, zero-dependency│
│                     │                          │ public web deployment │
└─────────────────────┴──────────────────────────┴───────────────────────┘
```

---

## 2. In-Depth Component Breakdown

### 1. Multi-Variable Prompt Synthesis Engine (Pure Python)
- **Role:** Generates ad copy, hooks, scene-by-scene scripts, CTAs, captions, and platform adaptations.
- **Why Pure Python?**
  - **Zero Cost & Infinite Quota:** Zero reliance on third-party API keys (OpenAI/Gemini), meaning the application never runs out of credits, encounters rate limits, or costs money to demonstrate.
  - **Sub-Second Execution:** Completes end-to-end multi-format campaign generation in under 150 milliseconds.
  - **100% Reliable:** Guarantees deterministic, reproducible outputs that adhere strictly to user-provided product facts without hallucinations.

### 2. Streamlit Web Framework & Custom Dark Studio UI
- **Role:** Interactive web application hosting 8 modular creative workspaces:
  1. `🏠 Dashboard`: Performance metrics and quick-start draft templates.
  2. `🚀 Campaign Generator`: Form inputs with Pydantic validation.
  3. `📊 Campaign Results`: Scene-by-scene studio editor and section regenerator.
  4. `🎨 Creative Gallery`: Visual display filterable by creative format.
  5. `🌟 Sample Campaigns`: Dedicated read-only reference campaign library.
  6. `📁 Campaign History`: Local JSON storage manager and search index.
  7. `🔍 Prompt Inspector`: Real-time inspection of templates and variables.
  8. `⚙️ Settings`: Optional neural API credentials and connectivity tester.
- **Custom CSS Engine:** High-contrast, dark creative studio theme with custom pill badges, clean typography, and zero-white-bar button overrides.

### 3. Pydantic v2 Validation Layer
- **Role:** Strict validation of user form submissions prior to generation.
- **Key Schemas Enforced:**
  - `CampaignInput`: Validates brand name length (1–100 chars), product name (1–150 chars), description (10–1000 chars), duration bounds (15, 30, 60 seconds), and hook count (3–10 hooks).
  - Sanitization of user strings to prevent prompt injection or broken formatting.

### 4. Automated Testing Suite (`pytest`)
- **Role:** Regression testing and test-driven development (TDD).
- **Test Coverage:** All **78 automated test cases** pass with 100% success:
  - `test_validators.py`: Input boundary and error-handling tests.
  - `test_prompt_builder.py`: SafeDict token substitution and preview tests.
  - `test_quality_checker.py`: Heuristic compliance and claim-flagging tests.
  - `test_storage.py`: JSON persistence, campaign ID generation, and indexing tests.
  - `test_exporters.py`: Markdown, Plain Text, and JSON serialization tests.
  - `test_ai_service_and_generator.py`: Pipeline execution and synthesis integrity tests.

### 5. Playwright Browser Automation
- **Role:** End-to-end headless browser orchestration for capturing genuine visual evidence and screenshots directly from the running web application.
- **Environment:** Chromium engine rendering at `1400 x 900` high-DPI resolution.

### 6. ReportLab PDF Generation Suite
- **Role:** Programmatic compilation of the formal internship project report (`FUTURE_PE_02_Project_Report.pdf`) featuring structured headers, metadata tables, code blocks, and professional typography.

### 7. Deployment Environment
- **Live URL:** `https://promptadscraft-302005.streamlit.app`
- **Infrastructure:** Streamlit Community Cloud (Linux container environment running Python 3.10+).
