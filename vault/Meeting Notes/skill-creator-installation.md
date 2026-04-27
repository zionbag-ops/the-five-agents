---
title: skill-creator installation
tags:
  - skill
  - claude-code
  - installation
---

# skill-creator installation

## Overview
סקיל מ-GitHub של Anthropic (`anthropics/skills`) להכנת סקילים חדשים ושיפור סקילים קיימים. מכיל workflow מלא: כתיבת SKILL.md, הרצת test cases עם subagents, הצגת תוצאות ב-viewer, וoptimization של תיאור הסקיל לtracking מדויק יותר.

## Open Questions
- none

## Session Log

### 2026-04-27 — התקנת skill-creator מ-GitHub [shipped]
- **What was done:** הורד ונסדר הסקיל המלא מ-`https://github.com/anthropics/skills/tree/main/skills/skill-creator` לתוך `.claude/skills/skill-creator/` — כולל SKILL.md, 3 agent files, references/schemas.md, 9 Python scripts, assets/eval_review.html, ו-eval-viewer/.
- **Decisions:** הסקיל הותקן ב-`.claude/skills/skill-creator/` (לא ב-`src/`) כי זה קובץ הגדרות Claude Code, לא קוד TypeScript של הפרויקט.
- **Notes / Caveats:** הסקריפטים Python דורשים Python מותקן בסביבה. הסקיל מיועד לשימוש ביצירת סקילים חדשים לפרויקט.
- **Related:** [[skill-obsidian-vault-workflow]], [[skill-obsidian-bases]], [[skill-obsidian-markdown]]
