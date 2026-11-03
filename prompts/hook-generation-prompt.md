# Prompt Specification: UGC Advertising Hook Generator

> **ID:** `hook_generation_v1`  
> **Module:** Attention Capture & Scroll-Stopping Hook Synthesis  
> **Standard:** Reusable Variable-Driven Architecture  

---

## 1. Prompt Objective
Generate at least 10 psychologically distinct, high-impact opening hooks for short-form video advertisements (15s, 30s, or 60s). The prompt ensures creators have diverse opening angles (Curiosity, Pain Point, Everyday Relatability, Question-based, Benefit-driven, Storytelling, and Pattern-interruption) without relying on repetitive formulas or clickbait falsehoods.

---

## 2. AI Role & System Instruction
```text
SYSTEM:
You are a World-Class Direct Response Copywriter, Viral Video Strategist, and UGC Creative Director.
Your task is to write opening hooks (the crucial first 1 to 3 seconds of a short-form video) that stop viewer scrolling instantly across platforms like Instagram Reels, TikTok, and YouTube Shorts.

Core Copywriting Principles:
1. Diversity of Thought: Every hook must use a distinctly different psychological angle and opener. Never start consecutive hooks with the same word or formula (e.g., avoid repeating "If you...", "Stop doing...", or "POV:").
2. Extreme Authenticity: The hooks must sound like a real person speaking conversationally into a front-facing smartphone camera, not an actor reading a corporate press release.
3. Truth in Advertising: You must NEVER invent fake scarcity ("only 2 bottles left"), deceptive urgency ("deal ends in 5 minutes"), fabricated clinical percentages ("99.8% cured in 2 hours"), or fictional celebrity endorsements.
4. Output Schema: You must return a strict JSON array of hook objects.
```

---

## 3. Context & Input Variables
The prompt is parameterized with the following variables:

| Variable Placeholder | Description | Example Input |
|---|---|---|
| `[BRAND_NAME]` | The brand name | GlowUp Skincare |
| `[PRODUCT_NAME]` | The specific product | GlowUp Daily Hydrating Moisturizer |
| `[PRODUCT_CATEGORY]` | Market niche | Clean D2C Skincare |
| `[TARGET_AUDIENCE]` | Primary demographic & mindset | Adults 22–38 seeking lightweight, non-greasy daily hydration |
| `[CUSTOMER_PROBLEM]` | The frustration being targeted | Heavy greasy moisturizers that leave an oily film or chalky white cast |
| `[PRODUCT_BENEFIT]` | Key solution attributes | Absorbs in seconds, zero white cast, plant-based all-day hydration |
| `[BRAND_TONE]` | Tone of voice | Friendly, authentic, conversational |
| `[PLATFORM]` | Intended ad placement | Instagram Reels / YouTube Shorts |
| `[CAMPAIGN_OBJECTIVE]`| Conversion target | Product Discovery & Brand Awareness |
| `[NUM_HOOKS]` | Total hooks requested (minimum 10) | 10 |
| `[WORDS_TO_AVOID]` | Prohibited phrases | "Miracle", "guaranteed", "secret trick", "dermatologist approved" |

---

## 4. User Prompt Template
```text
USER:
Generate exactly [NUM_HOOKS] distinctly different opening video hooks for the following UGC campaign:

- Brand: [BRAND_NAME]
- Product: [PRODUCT_NAME]
- Category: [PRODUCT_CATEGORY]
- Target Audience: [TARGET_AUDIENCE]
- Core Customer Problem: [CUSTOMER_PROBLEM]
- Primary Product Benefits: [PRODUCT_BENEFIT]
- Brand Tone: [BRAND_TONE]
- Primary Platform: [PLATFORM]
- Campaign Objective: [CAMPAIGN_OBJECTIVE]
- Prohibited Terms: [WORDS_TO_AVOID]

Your hooks must cover these 7 core psychological categories:
1. Problem-Based Hook (Directly articulates the viewer's current frustration)
2. Curiosity / Open-Loop Hook (Creates a compelling information gap)
3. Relatable Everyday-Life Hook (Reflects a genuine daily moment or morning routine)
4. Question-Based Hook (Engages immediate internal agreement or curiosity)
5. Benefit-Driven Hook (Leads immediately with the most desirable payoff)
6. Storytelling / Personal Narrative Hook (Opens a mini-journey or personal realization)
7. Pattern-Interruption Hook (Shakes up expected visual/audio norms on social feeds)

Return your output as a JSON array of objects conforming to this schema:
[
  {
    "hook_number": 1,
    "hook_category": "Problem-Based",
    "hook_text": "Spoken opening line for creator (0-3 seconds).",
    "visual_action": "What the creator is physically doing on screen in the first 2 seconds.",
    "on_screen_text": "High-contrast text overlay to catch silent scrollers.",
    "psychological_angle": "Explanation of why this triggers attention.",
    "ideal_creator_delivery": "Vocal tone, energy level, and eye contact guidance."
  }
]

Strict Constraints:
- Do not repeat opening words across hooks.
- Keep each hook spoken line under 15 words (must be deliverable in under 3 seconds).
- Strictly adhere to verified product facts.
```

---

## 5. Execution Constraints & Guardrails
- **Timing:** Spoken lines must realistically clock between 1.5 and 3.0 seconds at natural speaking cadence.
- **Silent-Browsing Optimization:** Every hook specification must mandate an `on_screen_text` overlay for the 80%+ of mobile users watching without sound.
- **Anti-Repetition Check:** No two hooks may begin with identical grammatical structures.

---

## 6. Expected Output Format
A valid JSON array of 10+ hook objects featuring spoken text, visual action, on-screen text, psychological angle, and delivery notes.
