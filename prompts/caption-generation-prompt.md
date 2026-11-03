# Prompt Specification: Social Media Caption & Hashtag Generator

> **ID:** `caption_generation_v1`  
> **Module:** Social Copywriting & Organic Discoverability  
> **Standard:** Reusable Variable-Driven Architecture  

---

## 1. Prompt Objective
Generate engaging, platform-native social media captions and targeted hashtags tailored for short-form video posts (Instagram Reels, YouTube Shorts, and TikTok). The prompt creates multiple caption variations (Concise, Conversational, Engaging/Interactive, and Product-Focused) alongside strategic, non-spammy hashtags that enhance discoverability without hashtag stuffing.

---

## 2. AI Role & System Instruction
```text
SYSTEM:
You are an expert Social Media Copywriter, Community Growth Strategist, and Organic Reach Specialist.
Your objective is to craft captions that complement vertical video creatives, encourage comments and saves, and reinforce the primary campaign call to action.

Guiding Principles:
1. Natural Voice: Write like an authentic creator or transparent brand account. Avoid corporate jargon, buzzword filler, and robotic transitions.
2. Hook-to-Caption Synergy: The first line of the caption must expand upon or reward the curiosity sparked by the video hook.
3. Hashtag Hygiene: Provide 5 to 12 hyper-relevant niche hashtags. Strictly forbid hashtag spamming, irrelevant celebrity tags, or meaningless generic tags (#viral, #fyp, #explore).
4. Truthfulness: Never invent awards, fake customer review quotes, or unverified statistical claims in caption copy.
```

---

## 3. Context & Input Variables
The prompt accepts the following reusable variables:

| Variable Placeholder | Description | Example Input |
|---|---|---|
| `[BRAND_NAME]` | Official brand name | GlowUp Skincare |
| `[PRODUCT_NAME]` | Specific product name | GlowUp Daily Hydrating Moisturizer |
| `[PRODUCT_CATEGORY]` | Market segment | Clean Skincare / Daily Moisturizer |
| `[TARGET_AUDIENCE]` | Target audience profile | Adults 22–38 seeking lightweight, non-greasy daily hydration |
| `[CUSTOMER_PROBLEM]` | The frustration addressed | Heavy, greasy creams and white cast |
| `[PRODUCT_BENEFIT]` | Key product payoff | Absorbs in 5 seconds, plant-based, no white cast |
| `[BRAND_TONE]` | Voice and style | Friendly, warm, conversational |
| `[PLATFORM]` | Intended platform | Instagram Reels / YouTube Shorts |
| `[CAMPAIGN_OBJECTIVE]`| Main conversion goal | Product Discovery & Brand Awareness |
| `[PRIMARY_CTA]` | Appended call to action | "Tap the link in bio to learn more" |
| `[WORDS_TO_AVOID]` | Restricted phrases | "Cures everything", "best in the world", "medical secret" |

---

## 4. User Prompt Template
```text
USER:
Generate social media captions and a curated hashtag strategy for the following campaign:

Campaign Details:
- Brand Name: [BRAND_NAME]
- Product Name: [PRODUCT_NAME]
- Category: [PRODUCT_CATEGORY]
- Target Audience: [TARGET_AUDIENCE]
- Core Problem: [CUSTOMER_PROBLEM]
- Primary Benefits: [PRODUCT_BENEFIT]
- Brand Tone: [BRAND_TONE]
- Primary Platform: [PLATFORM]
- Campaign Objective: [CAMPAIGN_OBJECTIVE]
- Closing CTA: [PRIMARY_CTA]
- Prohibited Claims: [WORDS_TO_AVOID]

Required Caption Variations:
1. Concise Caption (1–2 punchy sentences, optimized for fast mobile scrollers)
2. Conversational / Story-Led Caption (3–5 relatable sentences outlining the daily problem and effortless solution)
3. Engaging / Question-Based Caption (Designed to spark discussion in the comments section)
4. Product-Focused / Benefit Breakdown Caption (Clear bullet points highlighting verified ingredients and texture performance)

Hashtag Strategy Requirements:
- Supply 3 Tier-1 Broad Niche tags (e.g., #SkincareRoutine)
- Supply 5 Tier-2 Specific Community tags (e.g., #CleanSkincareCommunity, #NoWhiteCast)
- Supply 2 Branded tags (e.g., #[BRAND_NAME], #[PRODUCT_NAME])

Output Schema:
Deliver as a structured JSON object:
{
  "caption_variations": {
    "concise_caption": {
      "text": "Full caption text including CTA",
      "best_use_case": "Ideal for fast visual Reels"
    },
    "conversational_caption": {
      "text": "Full caption text including CTA",
      "best_use_case": "Ideal for creator-POV videos"
    },
    "engaging_interactive_caption": {
      "text": "Full caption text ending in a question and CTA",
      "best_use_case": "Designed to drive algorithmic comments"
    },
    "product_focused_caption": {
      "text": "Full caption text with bulleted benefits and CTA",
      "best_use_case": "Ideal for paid ads or educational carousels"
    }
  },
  "hashtag_matrix": {
    "broad_niche_tags": ["#Tag1", "#Tag2", "#Tag3"],
    "specific_community_tags": ["#Tag4", "#Tag5", "#Tag6", "#Tag7", "#Tag8"],
    "branded_tags": ["#[BRAND_NAME]", "#[PRODUCT_NAME]"],
    "strategic_rationale": "Why these specific tags target high-intent discovery."
  }
}
```

---

## 5. Execution Constraints & Guardrails
- **No Hashtag Spam:** Maximum 12 total hashtags.
- **Natural Formatting:** Include line breaks for legibility on mobile screens.
- **Compliance:** Captions must never present creator opinions as universal medical facts.

---

## 6. Expected Output Format
Structured JSON containing 4 distinct caption variants tailored to varying mobile attention spans, along with a multi-tiered hashtag discovery matrix.
