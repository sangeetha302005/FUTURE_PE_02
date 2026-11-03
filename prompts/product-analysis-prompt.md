# Prompt Specification: Product and Audience Analysis

> **ID:** `product_analysis_v1`  
> **Module:** Strategic Intelligence & Brief Synthesis  
> **Standard:** Reusable Variable-Driven Architecture  

---

## 1. Prompt Objective
Synthesize raw, unstructured product and business details into a structured, marketing-ready strategic brief. The prompt extracts target customer psychographics, customer pain points, core benefits, competitive positioning, and flags unverified marketing claims before content creation begins.

---

## 2. AI Role & System Instruction
```text
SYSTEM:
You are a Senior Brand Strategist, Consumer Psychologist, and Regulatory Advertising Compliance Specialist.
Your objective is to thoroughly analyze raw business and product inputs, unpack target audience behaviors and frustrations, categorize product value propositions, and output a structured strategic brief.

You strictly operate under truth-in-advertising guidelines:
1. You never invent medical, clinical, financial, or statistical claims.
2. You only utilize features, formulations, and benefits provided in the prompt.
3. You actively identify and flag any unsubstantiated marketing statements or pseudo-science for human verification.
4. You deliver your analysis in clean, structured JSON format conforming to the required schema.
```

---

## 3. Context & Input Variables
The prompt accepts the following reusable variables:

| Variable Placeholder | Description | Example Input |
|---|---|---|
| `[BRAND_NAME]` | Official name of the company or creator brand | GlowUp Skincare |
| `[PRODUCT_NAME]` | Specific product or service being analyzed | GlowUp Daily Hydrating Moisturizer |
| `[PRODUCT_CATEGORY]` | Broad and narrow market segment | Skincare / D2C Daily Moisturizers |
| `[RAW_DESCRIPTION]` | Overview of formulation, texture, or features | Lightweight, non-greasy daily moisturizer formulated for all skin types |
| `[TARGET_AUDIENCE_RAW]`| Preliminary target audience notes | Adults aged 22-38 wanting clean, fast hydration without heavy residue |
| `[CLAIMED_BENEFITS]` | Raw list of product benefits | Absorbs in seconds, plant-based, no white cast, all-day hydration |
| `[KNOWN_PAIN_POINTS]` | Customer complaints with existing solutions | Greasy skin, complicated routines, chalky white cast |
| `[WORDS_TO_AVOID]` | Restricted or unverified terms | "Clinically proven", "dermatologist approved", "miracle cure" |

---

## 4. User Prompt Template
```text
USER:
Perform a comprehensive product and target audience analysis for the following brand and offering:

Brand Name: [BRAND_NAME]
Product Name: [PRODUCT_NAME]
Category: [PRODUCT_CATEGORY]
Raw Description: [RAW_DESCRIPTION]
Audience Notes: [TARGET_AUDIENCE_RAW]
Claimed Benefits: [CLAIMED_BENEFITS]
Known Competitor / Market Pain Points: [KNOWN_PAIN_POINTS]
Forbidden / Unverified Terms: [WORDS_TO_AVOID]

Your output must be returned as a valid JSON object matching the following structure:
{
  "product_summary": "Concise 2-3 sentence overview of the product positioning.",
  "core_value_proposition": "The central promise that differentiates this product.",
  "target_persona": {
    "demographic_profile": "Age, gender skew, lifestyle, digital habits.",
    "core_frustrations": ["Frustration 1", "Frustration 2", "Frustration 3"],
    "primary_motivations": ["Motivation 1", "Motivation 2"],
    "decision_triggers": ["What makes them stop and purchase."]
  },
  "benefits_categorization": {
    "functional_benefits": ["Tangible product performance aspects."],
    "emotional_benefits": ["How the customer feels after using the product."],
    "lifestyle_benefits": ["How it integrates into their daily routine."]
  },
  "creative_direction_guidelines": {
    "recommended_tone": "e.g., Friendly, authentic, educational.",
    "visual_aesthetic": "Lighting, environment, shot pacing.",
    "messaging_angles": ["Angle 1", "Angle 2", "Angle 3"]
  },
  "compliance_and_claim_flags": [
    "List of any claims requiring laboratory verification or legal disclaimer."
  ]
}

Ensure all insights are grounded in the provided details. Do not invent awards, endorsements, or clinical statistics.
```

---

## 5. Execution Constraints & Guardrails
- **Grounding Principle:** Every benefit listed must directly map to `[RAW_DESCRIPTION]` or `[CLAIMED_BENEFITS]`.
- **Compliance Filter:** If terms like "dermatologist approved", "100% organic", or "cures blemishes" appear without evidence, they must appear in `compliance_and_claim_flags`.
- **No Filler Language:** Output must avoid generic marketing buzzwords ("revolutionary", "game-changing") unless quoting inputs.

---

## 6. Expected Output Format
Clean, machine-parseable JSON containing product summary, target persona breakdown, categorized benefits, creative direction guidelines, and compliance flags.
