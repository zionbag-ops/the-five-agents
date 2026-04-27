---
title: src/skills/
tags:
  - source-code
  - typescript
  - skills
---

# src/skills/

## Overview
תיקיית קוד המקור ל-skills (כישורים) שה-agents יכולים להשתמש בהם. Skills הם פונקציות/כלים שה-agents יכולים לקרוא — חיפוש, כתיבה, קריאת API וכד'. כרגע ריקה — בשלב תכנון.

## Open Questions
- אילו skills יפותחו? כלי Claude API? גישה לקבצים? API חיצוני?
- מה הקשר בין src/skills/ ל-.claude/skills/ (סקילים של Claude Code)?

## Session Log

### 2026-04-27 — תיקיה נוצרה [planned]
- **What was done:** נוצרה עם .gitkeep לשמירה ב-Git.
- **Decisions:** מופרדת מ-src/agents/ לפי עקרון הפרדת אחריות.
- **Notes / Caveats:** .claude/skills/ הם סקילים של Claude Code CLI — שונה לחלוטין מ-src/skills/ שהוא קוד TypeScript לפרויקט.
- **Related:** [[src-agents]], [[skill-obsidian-vault-workflow]]
