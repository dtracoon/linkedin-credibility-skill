# LinkedIn Credibility Audit

A Cola skill that diagnoses LinkedIn profile credibility across 7 trust dimensions and provides specific, actionable optimization advice.

## Who This Is For

- **Business Development** — making your profile trustworthy before cold outreach
- **Media Outreach** — helping journalists and editors see you as a credible source
- **Fundraising & Investment** — signaling competence to investors before the first meeting

## What It Audits

| Dimension | What We Look For |
|-----------|-----------------|
| Photo & Banner | Visual first impression, professionalism, relevance |
| Headline | 3-second pitch clarity, keyword optimization, value proposition |
| About Section | Trust narrative, specific results, call to action |
| Experience | Proof over promises — specific numbers, action language |
| Skills & Endorsements | Social proof alignment with positioning |
| Activity & Content | Thought leadership signals, posting consistency |
| Network & Connections | Social graph trust, mutual connection potential |

## How to Use

1. Install the skill in your Cola skills directory
2. Send your LinkedIn profile URL to Cola (or paste profile content)
3. Receive a structured audit with scores, before/after rewrites, and strategy recommendations

## Example Output

```
Overall Score: 23/35

Priority Fixes:
1. Headline: "CEO at ABC Corp" → "B2B SaaS Growth | $1M→$10M ARR | Ex-Stripe"
2. About: Add specific revenue numbers, replace adjectives with results
3. Photo: Current photo is a cropped wedding shot — use a headshot with direct eye contact
```

## Installation

```bash
# Clone into your Cola skills directory
git clone https://github.com/dtracoon/linkedin-credibility-skill.git ~/.cola/skills/linkedin-credibility-audit
```

## Structure

```
linkedin-credibility-skill/
├── SKILL.md                        # Main skill definition
├── README.md                       # You're reading it
└── references/
    └── scoring-rubric.md           # Detailed 1-5 scoring criteria per dimension
```
