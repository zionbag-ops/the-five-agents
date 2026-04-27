---
title: CEO Agent — PRD
tags:
  - agent
  - architecture
  - prd
---

# CEO Agent — PRD

## Overview
סוכן ה-CEO הוא orchestrator מרכזי במערכת "The Five Agents" לפיתוח תוכנה. הוא מקבל כל משימה מהמשתמש דרך CLAUDE.md, מנתח ומסווג אותה, ומנתב לסוכן-משנה המתאים מתוך 4 סוכנים (יוגדרו בהמשך). ה-PRD המלא נמצא ב-`docs/ceo-agent-prd.md`.

## Open Questions
- מי הם 4 סוכני-המשנה ומה תפקיד כל אחד?
- האם CEO יכול להפעיל סוכנים במקביל (parallel) או רק ברצף?
- מה הפורמט המדויק של ה-context שעובר בין CEO לסוכנים?
- האם CEO מתעד החלטות ב-vault בכל משימה?

## Session Log

### 2026-04-27 — יצירת PRD לסוכן CEO [shipped]
- **What was done:** נכתב PRD מלא בעברית ב-`docs/ceo-agent-prd.md` — סקירה, מטרה, ארכיטקטורה, 17 דרישות פונקציונליות, מטריצת החלטות, ניהול state, טיפול בשגיאות, אינטגרציה עם CLAUDE.md, וקריטריוני הצלחה.
- **Decisions:** PRD נשמר ב-`docs/` (לא vault) כי זה מסמך spec קבוע שמפתחים מפנים אליו — לא session log. ה-vault מכיל רק pointer ו-session log.
- **Notes / Caveats:** ממשק הסוכנים (מטריצת החלטות, context protocol) הוא placeholder — יתמלא כשהסוכנים יוגדרו. קובץ `.claude/agents/ceo.md` ייוצר על ידי המפתח, לא Claude Code.
- **Related:** [[src-agents]], [[claude-agents-folder]], [[project-file-documentation]]

### 2026-04-27 — יצירת .claude/agents/ceo.md [shipped]
- **What was done:** נוצר `.claude/agents/ceo.md` עם הגדרת תפקיד מלאה: פרוטוקול vault, מטריצת החלטות, שלבי ביצוע, כללי זהב, וטיפול בשגיאות. עודכן CLAUDE.md עם סעיף "Mandatory Agent Routing" שמפנה לCEO.
- **Decisions:** ה-CEO מוגדר עם `tools: Agent` כדי לאפשר הפעלת sub-agents; מטריצת ההחלטות כוללת placeholders לארבעת הסוכנים שיוגדרו בהמשך.
- **Notes / Caveats:** סוכני-המשנה (agent1–4) עדיין TBD — הטבלה ב-ceo.md תתעדכן כשיוגדרו.
- **Related:** [[claude-agents-folder]], [[claude-md]], [[src-agents]]
