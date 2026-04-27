---
title: .gitignore
tags:
  - config
  - git
---

# .gitignore

## Overview
קובץ Git סטנדרטי המגדיר אילו קבצים ותיקיות לא יועלו לריפו. מוגדר לפרויקט TypeScript/Node: מתעלם מ-node_modules/, dist/, build/, קבצי .env, וקבצי לוג.

## Open Questions
- none

## Session Log

### 2026-04-27 — יצירת .gitignore לפרויקט TypeScript/Node [shipped]
- **What was done:** נוצר .gitignore עם הכללות בסיסיות לסביבת Node/TypeScript.
- **Decisions:** כלולים node_modules, dist, build, .env, .env.local, *.log — סטנדרט לפרויקטי Node.
- **Notes / Caveats:** ייתכן שיצטרך הרחבה כשיתווספו כלי build ספציפיים.
- **Related:** [[claude-md]]
