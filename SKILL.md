---
name: linkedin-credibility-audit
description: >
  Diagnose LinkedIn profile credibility and professionalism across 7 trust dimensions,
  then provide specific, actionable rewrite and strategy recommendations.
  Use when the user wants to audit, optimize, or improve their LinkedIn profile
  for business development, media outreach, fundraising, or investment pitching —
  or when they mention LinkedIn诊断, LinkedIn audit, LinkedIn优化, LinkedIn profile review,
  LinkedIn credibility, LinkedIn信任度, 领英诊断, 领英优化, or want to make their
  LinkedIn look more professional and trustworthy to陌生客户, 媒体编辑, 投资人, or招商对象.
---

# LinkedIn Credibility Audit

Analyze a LinkedIn profile and deliver a structured credibility diagnosis with specific
rewrite and strategy recommendations. The audit targets three use cases: business
development (developing陌生客户), media outreach (建联媒体编辑/记者), and fundraising or
investment pitching (招商/投资).

## How to Get the Profile Content

### Step 1: Try Direct Fetch

Ask the user for their LinkedIn profile URL. Call web_fetch once.

### Step 2: Check for Login Wall (CRITICAL)

After the fetch, check the result immediately. If the page content contains ANY of
these signals, the profile is behind a login wall and you MUST switch to manual mode:

- "Sign in to view" or "Join LinkedIn" or "Agree & Join"
- "Sign Up | LinkedIn" in the title
- "authwall" in the URL
- Only login/signup forms with no profile data

**DO NOT retry the fetch.** One attempt is enough. Retrying will not bypass the wall.
Instead, tell the user: "This profile is behind LinkedIn's login wall — most are.
Copy these sections from the profile and I'll audit them:"

Then ask for exactly these fields:

```
1. Headline (名字下面那行小字)
2. About section (完整复制)
3. Experience — 最近 2-3 段职位（每段：职位名 + 公司 + 时间 + 描述）
4. Skills — 前 5 个技能
5. 最近 3 条动态（如果有发帖）
6. 头像和 Banner 可以描述一下
```

### Step 3: Manual Content Audit

When the user provides text content, audit it just as thoroughly as if you had
fetched it directly. The scoring framework doesn't change.

For photo and banner: ask the user to briefly describe them. Even a rough
description ("formal headshot, smiling" / "default LinkedIn blue banner") is enough
to score dimension 1.

### Important: Don't Fake Data

If the user cannot or doesn't provide a section (e.g., no recent activity posts),
note it as "无法评估" in the audit — don't guess or fabricate scores for missing data.

## The Audit Framework

Score each dimension on a 1–5 scale (5 = excellent credibility signal).
Explain **why** the score was given before suggesting improvements.

### 1. Profile Photo & Banner — Visual First Impression

Assess:
- Photo quality (lighting, resolution, professionalism)
- Facial visibility and expression (approachable? confident?)
- Background / banner relevance to the user's field
- Consistency with the user's stated professional identity

Weight: HIGH. This is the first thing anyone sees. A bad photo kills credibility
before the text is read.

### 2. Headline — The 3-Second Pitch

Assess:
- Does it say what the user actually does, specifically?
- Does it name a target audience or value proposition?
- Is it keyword-optimized for the user's target reader?
- Does it avoid meaningless buzzwords ("visionary", "passionate about...")?

Good headline formula: `[Role] | [What you do for whom] | [Credibility hook]`

Bad: "CEO at ABC Corp"
Good: "B2B SaaS Growth | Helping Series A startups scale from $1M to $10M ARR | Ex-Stripe"

### 3. About Section — The Trust Narrative

Assess:
- Does it open with a hook that makes the target reader care?
- Does it build credibility with specific results, not adjectives?
- Does it address the reader's problem before listing credentials?
- Is there a clear call to action (what should the reader do next)?
- Length: too short (<3 sentences) lacks depth; too long without structure loses readers

Structure to recommend:
1. Hook (the problem you solve, stated from the reader's perspective)
2. Credibility (specific results, numbers, names)
3. Bridge (why you do this — optional, brief)
4. Call to action (what the reader should do, with a low-friction invitation)

### 4. Experience Section — Proof, Not Promises

Assess each entry for:
- Specific results with numbers (%, $, time saved, scale)
- Action language (led, built, grew) vs passive (was responsible for)
- Relevance to the user's current positioning
- Gaps or inconsistencies that undermine credibility

Bad: "Responsible for managing the sales team"
Good: "Led a 12-person sales team to 40% YoY revenue growth ($2.3M → $3.2M)"

### 5. Skills & Endorsements — Social Proof

Assess:
- Top 3 skills: are they aligned with the user's current positioning?
- Endorsement count: too few looks unverified; asking for endorsements from the
  right people is a legitimate strategy
- Are the skills specific or generic ("Microsoft Office" adds almost nothing)?

### 6. Activity & Content — Thought Leadership Signals

Assess the last 3–5 posts or activity items:
- Does the user post content relevant to their target audience?
- Posting frequency: dormant accounts signal low engagement; daily posting isn't
  necessary, but consistent presence matters
- Content type: original insights > resharing with commentary > bare reposts
- Comment engagement: thoughtful comments on others' posts also build credibility

### 7. Network & Connections — Social Graph Trust

Assess:
- Connection count (visible on profile): too few (<100) looks new; 500+ is the
  visible threshold after which LinkedIn shows "500+"
- Mutual connections with the target audience (hard to assess without the user's
  input — ask about their target industries and roles)

## Strategy Recommendations

After the dimensional audit, provide:

### Connection Strategy
- Who to connect with and why (based on the user's stated target: clients, media,
  investors)
- How to personalize connection requests for each target type
- Whether the user should follow, connect, or engage first before connecting

### Content Strategy
- What types of posts build credibility for the user's target audience
- Suggested post cadence and format (text-only, carousel, video, document posts)
- Specific topics the user could credibly speak about based on their experience

### Quick Wins vs. Deep Fixes
- Distinguish fixes that take 5 minutes (rewrite headline, crop photo) from those
  requiring sustained effort (build content presence, grow network)

## Deliverable Format

Present the audit as:

```
## LinkedIn Credibility Audit for [Name]

**Overall Score: X/35**

### Scores by Dimension
| Dimension | Score | Quick Take |
|-----------|-------|------------|
| Photo & Banner | X/5 | ... |
| Headline | X/5 | ... |
| About | X/5 | ... |
| Experience | X/5 | ... |
| Skills & Endorsements | X/5 | ... |
| Activity & Content | X/5 | ... |
| Network | X/5 | ... |

### Priority Fixes
1. [Highest-impact fix, with before/after example]
2. [Next fix]
3. ...

### Connection Strategy for [Target Audience]
...

### Content Strategy
...

### Quick Wins (5 min or less)
- ...
```

## Edge Cases

- **Empty/minimal profile**: Don't give low scores across the board — explain that
  an empty profile is a blank canvas and prioritize what to build first.
- **Profile in a non-English language**: Audit in the profile's language. If the
  user is targeting international audiences, recommend an English version.
- **Multiple target audiences**: If the user wants to appeal to both investors AND
  clients, note which sections serve which audience and flag conflicts.
- **Login wall (most common case)**: Immediately switch to manual mode after one
  failed web_fetch. Don't retry. See "How to Get the Profile Content" for the
  exact copy-paste fields to request.
- **Partial data**: If the user provides some sections but not others (e.g.,
  experiences but no activity), audit what you have and mark missing dimensions
  as "无法评估 — 缺少数据". Don't invent scores.

## References

Read `references/scoring-rubric.md` when you need detailed criteria for each score
level (1 through 5) on any dimension.
