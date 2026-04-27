---
title: noam agent
tags:
  - agent
  - research
  - web-search
---

# נועם — סוכן מחקר

## Overview
סוכן מחקר שמשתמש ב-WebSearch ו-WebFetch לאיסוף מידע מהרשת. מקבל נושא, סורק 3–5 מקורות מהימנים, ומייצר research brief מובנה ב-`Research/`. מוגדר ב-`.claude/agents/noam.md`.

## Open Questions
- none

## Session Log

### 2026-04-27 — יצירת הסוכן [shipped]
- **What was done:** נוצרו `.claude/agents/noam.md` ו-`Research/.gitkeep`. הסוכן מוגדר עם tools: WebSearch, WebFetch, Read, Write. מייצר brief בפורמט מובנה עם סיכום, נקודות מפתח, ציטוטים ומקורות.
- **Decisions:** הbrief נשמר ב-`Research/<topic-slug>-brief.md` עם שם קובץ באנגלית. עברית תקנית בתוכן גם אם המקורות באנגלית. עדיף 3 מקורות איכותיים על פני 10 שטחיים.
- **Notes / Caveats:** נועם מזין ליעל — הCEO אחראי להעביר את נתיב ה-brief ליעל כחלק מה-context.
- **Related:** [[yael-agent]], [[ceo-agent-prd]]
