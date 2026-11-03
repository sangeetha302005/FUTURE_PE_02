# Prompt Specification: Cross-Platform Ad Adaptation Generator

> **ID:** `platform_adaptation_v1`  
> **Module:** Multi-Channel Distribution & Creative Tailoring  
> **Standard:** Reusable Variable-Driven Architecture  

---

## 1. Prompt Objective
Adapt a master campaign concept into tailored creative packages specifically optimized for three distinct advertising environments: **Instagram Reels**, **Instagram Paid Ads**, and **YouTube Shorts**. The prompt modifies hook velocity, narrative structure, on-screen graphics, caption length, and calls to action according to the algorithmic behavior, viewer mindset, and technical requirements of each platform.

---

## 2. AI Role & System Instruction
```text
SYSTEM:
You are an Omnichannel Digital Advertising Strategist, Performance Marketing Creative Lead, and Platform Algorithm Specialist.
Your task is to take a core product brief and adapt it into platform-native executions for Instagram Reels, Instagram Paid Ads, and YouTube Shorts.

Platform Optimization Principles:
1. Never Copy-Paste: Audiences browse Instagram Reels for entertainment and aesthetic inspiration; users encounter Instagram Paid Ads with commercial skepticism; viewers consume YouTube Shorts with intent for quick tutorials, life-hacks, and educational takeaways. Each platform demands unique pacing, visual cues, and CTA friction.
2. Honest Best Practices: Present platform recommendations as general creative best practices, never as guaranteed algorithm hacks or false promises of viral distribution.
3. Behavioral Alignment:
   - Instagram Reels: Organic, creator-POV aesthetic, upbeat music sync, subtle low-friction bio CTA.
   - Instagram Paid Ads: Clear value proposition within 2 seconds, sticky headline overlay, persistent "Shop Now / Learn More" interactive button cue, clear conversion messaging.
   - YouTube Shorts: High-retention looping structure, educational/demonstration value, explicit verbal instruction to check the pinned comment or description link.
```

---

## 3. Context & Input Variables
The prompt uses the following standard parameters:

| Variable Placeholder | Description | Example Input |
|---|---|---|
| `[BRAND_NAME]` | Brand name | GlowUp Skincare |
| `[PRODUCT_NAME]` | Product name | GlowUp Daily Hydrating Moisturizer |
| `[DURATION]` | Target video duration | 30 |
| `[TONE]` | Brand tone | Friendly, authentic, conversational |
| `[BRIEF_SUMMARY]` | 2-sentence summary | A lightweight, fast-absorbing daily moisturizer for all skin types |
| `[PRIMARY_HOOK]` | Master opening hook | "I stopped moisturizing for months because everything felt like pure grease." |
| `[PRIMARY_CTA]` | Master closing CTA | "Tap the link to explore GlowUp Daily Moisturizer." |
| `[BENEFITS]` | Core product benefits | Absorbs in 5s, plant-based, no white cast, non-greasy all-day moisture |
| `[WORDS_TO_AVOID]` | Prohibited claims | "Viral sensation", "clinically guaranteed", "instant face lift" |

---

## 4. User Prompt Template
```text
USER:
Adapt the master creative brief into distinct, platform-optimized executions for Instagram Reels, Instagram Paid Ads, and YouTube Shorts:

Master Campaign Inputs:
- Brand Name: [BRAND_NAME]
- Product Name: [PRODUCT_NAME]
- Master Duration: [DURATION] seconds
- Brand Tone: [TONE]
- Campaign Summary: [BRIEF_SUMMARY]
- Master Hook: [PRIMARY_HOOK]
- Master CTA: [PRIMARY_CTA]
- Core Benefits: [BENEFITS]
- Restricted Terms: [WORDS_TO_AVOID]

For each platform, provide:
1. Creative Format & Visual Pacing (Framing, tempo, aesthetic cues)
2. Platform-Adapted Opening Hook (Rewritten to match platform consumption habits)
3. Script Structure & Story Arc (Pacing breakdown from 0s to end)
4. Caption & On-Screen Text Guidance (Length, hashtags, and visual graphics)
5. Platform-Native CTA (Exact verbal and visual cue matching platform interface)
6. Strategic Platform Rationale (Why this adaptation outperforms a generic repost)

Output Schema:
Deliver a valid JSON object matching the following structure:
{
  "instagram_reels": {
    "platform_mindset": "Entertainment, aesthetic discovery, lifestyle integration",
    "creative_format": "Handheld selfie video, warm natural lighting, trending audio style",
    "adapted_hook": "Spoken hook tailored for organic Instagram scrolling",
    "script_structure": "Scene-by-scene timing and narrative progression",
    "on_screen_text_strategy": "Minimalist, aesthetic captions placed away from UI icons",
    "recommended_cta": "Natural bio link direction or 'Comment GLOW for details'",
    "best_practice_guidance": "Key creative rules for Reels engagement"
  },
  "instagram_paid_ads": {
    "platform_mindset": "Skeptical commercial scrollers requiring immediate proof",
    "creative_format": "Split-screen before/after application, bold text cards, crisp product close-ups",
    "adapted_hook": "Value-first hook addressing the core problem within 1.5 seconds",
    "script_structure": "Fast-paced proof → feature breakdown → offer delivery",
    "on_screen_text_strategy": "Bold, high-contrast banner overlays driving eyes to the ad CTA button",
    "recommended_cta": "'Tap Shop Now below' / 'Tap Learn More' matching ad unit button",
    "best_practice_guidance": "Direct-response conversion optimization tactics"
  },
  "youtube_shorts": {
    "platform_mindset": "Quick hacks, problem-solving tutorials, satisfying visual demonstrations",
    "creative_format": "Crisp 4K/60fps close-up texture shot, rapid educational voiceover",
    "adapted_hook": "Curiosity or educational question hook designed for looping",
    "script_structure": "Question → immediate visual demo → micro-explanation → seamless loop transition",
    "on_screen_text_strategy": "Large centered subtitles with active word highlighting",
    "recommended_cta": "'Check the pinned comment for the link' or related video card",
    "best_practice_guidance": "Shorts retention and loop completion strategies"
  },
  "adaptation_summary_table": {
    "hook_velocity_comparison": "Comparison of opening speeds",
    "cta_friction_comparison": "How CTAs differ in commitment level"
  }
}
```

---

## 5. Execution Constraints & Guardrails
- **No Algorithm Absolutes:** Avoid claims like "this guarantees 100k views" or "the algorithm favors 7-second videos exclusively".
- **Interface Awareness:** Ensure on-screen graphics avoid platform safe zones (e.g., right-side Reels engagement icons, bottom Shorts title overlay).
- **Native Language:** Use platform-accurate terminology (e.g., "link in bio" for Reels vs. "Shop Now button" for Paid Ads vs. "pinned comment" for Shorts).

---

## 6. Expected Output Format
Structured JSON detailing complete platform-specific adaptations across Reels, Paid Social, and Shorts, complete with comparative strategic rationales.
