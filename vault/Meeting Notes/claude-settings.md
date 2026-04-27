---
title: .claude/settings.json
tags:
  - config
  - claude-code
---

# .claude/settings.json

## Overview
קובץ הגדרות ברמת הפרויקט של Claude Code. שולט בהרשאות (allow/deny) לפקודות ופעולות שClaude Code מורשה לבצע בתוך הפרויקט. קובץ זה מתחייב ל-Git ושיתוף עם כל המשתמשים בפרויקט.

## Open Questions
- יש להגדיר אילו הרשאות נדרשות כשהפרויקט מתפתח.

## Session Log

### 2026-04-27 — יצירת settings.json ראשוני [shipped]
- **What was done:** נוצר עם מבנה ריק של permissions allow/deny.
- **Decisions:** נשמר ריק בכוונה — הרשאות יתווספו לפי הצורך.
- **Notes / Caveats:** קיים גם settings.local.json (לא מתחייב) להגדרות אישיות.
- **Related:** [[claude-settings-local]], [[claude-md]]
