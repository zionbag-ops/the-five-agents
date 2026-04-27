---
title: .obsidian/
tags:
  - config
  - obsidian
---

# .obsidian/

## Overview
תיקיית הגדרות Obsidian — מאשרת שהפרויקט כולו הוא vault של Obsidian. מכילה: app.json (הגדרות כלליות), appearance.json (עיצוב), core-plugins.json (plugins מובנים), workspace.json (מצב הסביבה). תיקיה זו מנוהלת על ידי Obsidian ולא אמורה להיערך ידנית.

## Open Questions
- האם לכלול .obsidian ב-.gitignore (לא לשתף עם צוות) או לכלול ב-Git (לשמור הגדרות)?

## Session Log

### 2026-04-27 — זיהוי vault [shipped]
- **What was done:** התגלה שהפרויקט הוא vault Obsidian פעיל עם תיקיית .obsidian.
- **Decisions:** vault/Meeting Notes/ נוצר בתוך ה-vault לפי הנחיות obsidian-vault-workflow.
- **Notes / Caveats:** app.json ריק {} — vault עם הגדרות ברירת מחדל.
- **Related:** [[skill-obsidian-vault-workflow]], [[skill-obsidian-markdown]]
