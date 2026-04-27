---
title: alon agent
tags:
  - agent
  - distribution
  - social-media
  - llm-only
---

# אלון — סוכן הפצה

## Overview
סוכן הפצה LLM-Only שלוקח מאמרים מ-`Published/`, מתאים אותם לפלטפורמות שונות ושומר ב-`Distribution/`. מייצר 3 גרסאות: LinkedIn, Twitter/X thread, תקציר. מוגדר ב-`.claude/agents/alon.md`.

## Open Questions
- none

## Session Log

### 2026-04-27 — יצירת הסוכן [shipped]
- **What was done:** נוצרו `.claude/agents/alon.md` ו-`Distribution/.gitkeep`. הסוכן מוגדר עם tools: Read, Write בלבד (LLM-Only). שומר תוצאות ב-`Distribution/<article-name>/` עם 3 קבצים: linkedin.md, twitter.md, summary.md.
- **Decisions:** LinkedIn: 150–300 מילה + 3-5 hashtags. Twitter: thread של 3–5 tweets עם סימון [N/N]. תקציר: 2–3 משפטים. כל הגרסאות בעברית.
- **Notes / Caveats:** אלון הוא הסוכן האחרון בפייפליין: נועם → יעל → יובל → Published → אלון → Distribution.
- **Related:** [[yael-agent]], [[yuval-agent]], [[ceo-agent-prd]]
