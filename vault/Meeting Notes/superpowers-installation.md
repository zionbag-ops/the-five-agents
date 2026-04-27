---
title: superpowers installation
tags:
  - plugin
  - claude-code
  - installation
---

# superpowers installation

## Overview
פלאגין Claude Code מאת Jesse Vincent (obra) המוסיף מתודולוגיית פיתוח תוכנה מלאה: TDD, debugging, collaboration patterns, ו-subagent workflows. מותקן ברמת user scope דרך מנגנון ה-plugin marketplace של Claude Code.

## Open Questions
- none

## Session Log

### 2026-04-27 — התקנת superpowers [shipped]
- **What was done:** הוספת marketplace `superpowers-dev` (obra/superpowers) לפרויקט דרך `claude plugin marketplace add obra/superpowers --scope project`. הפלאגין עצמו הותקן ב-user scope דרך `claude plugin install superpowers`.
- **Decisions:** `.claude/` ב-repo של superpowers הוא gitignored — הקבצים מגיעים דרך ה-plugin system, לא דרך git clone. הגישה הנכונה: marketplace add → plugin install. settings.json עודכן אוטומטית עם `extraKnownMarketplaces`.
- **Notes / Caveats:** הפלאגין מותקן ב-user scope (גלובלי), לא רק לפרויקט. גרסה: 5.0.7. יכול להשתמש בסקילים כמו TDD, debugging ו-brainstorming בכל סשן.
- **Related:** [[skill-creator-installation]], [[claude-settings]]
