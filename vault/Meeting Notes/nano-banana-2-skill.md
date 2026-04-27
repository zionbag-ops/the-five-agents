---
title: nano-banana-2 skill
tags:
  - skill
  - image-generation
  - mcp
---

# nano-banana-2 Skill

## Overview
סקיל ליצירת תמונות באמצעות Google Nano Banana 2 דרך MCP. מקבל prompt טקסט, שולח למודל דרך MCP server, ומחזיר תמונה שמורה. מוגדר ב-`.claude/skills/nano-banana-2/SKILL.md`. ה-MCP server מוגדר ב-`.claude/settings.json`.

## Open Questions
- none

## Session Log

### 2026-04-27 — יצירת הסקיל [wip]
- **What was done:** נוצרו SKILL.md עם workflow מלא, settings.json עודכן עם mcpServers placeholder, תיקיות reference/ ו-outputs/ נוצרו.
- **Decisions:** MCP מוגדר כ-placeholder עם TODO ברור כי "Google Nano Banana 2" לא מוכר — המשתמש ישלים כשהחבילה ידועה.
- **Notes / Caveats:** "Nano Banana 2" הוא הכינוי הקהילתי ל-Gemini 3.1 Flash Image. החבילה `mcp-image` (npm) היא הנפוצה ביותר לClaude Code. יש להגדיר `GEMINI_API_KEY` בסביבה לפני שימוש.
- **Related:** [[yuval-agent]], [[claude-settings]]

### 2026-04-27 — הרצה ראשונה מוצלחת [shipped]
- **What was done:** יצירת תמונת שור דרך Gemini API ישירות (MCP לא נטען כי settings.json עודכן באמצע הסשן). התמונה נשמרה ב-`outputs/bull-2026-04-27-14-11-17-574.png`.
- **Decisions:** שם המודל האמיתי הוא `gemini-3.1-flash-image-preview` (לא `gemini-3.1-flash-image`). ה-API key נמצא תחת `NANO_BANANA_API_KEY` ב-.env. המודל מחזיר base64 (image/jpeg). עודכן settings.json מ-`GEMINI_API_KEY` ל-`NANO_BANANA_API_KEY`.
- **Notes / Caveats:** לכשהסשן הבא יתחיל — MCP יטען אוטומטית ויובל יוכל להפעיל את הסקיל ישירות.
- **Related:** [[yuval-agent]], [[claude-settings]]

### 2026-04-27 — אבחון כשל יצירת תמונות — free tier quota=0 [blocked]
- **What was done:** ניסיון ליצור 4 תמונות ל-`ai-agents-intro.md` ו-`claude-agents-article.md` דרך API ישיר. כל model של image generation (gemini-3.1-flash-image-preview, gemini-2.5-flash-image, gemini-3-pro-image-preview, imagen-4.0-generate-001) מחזיר `quota exceeded, free_tier_input_token_count, limit: 0`.
- **Decisions:** הבעיה אינה ב-API key עצמו (הוא תקין, מאמת) אלא בתוכנית: free tier לא כולל image generation בכלל (limit=0, לא שנגמר). דרוש paid plan ב-Google AI Studio.
- **Notes / Caveats:** Imagen 4.0 מחזיר `400 Imagen 3 is only available on paid plans`. כל models של image generation דורשים billing. לא ניתן לעקוף — הפתרון היחיד הוא הפעלת billing ב-https://ai.dev/projects.
- **Related:** [[yuval-agent]], [[claude-settings]]

### 2026-04-27 — עדכון Google AI Studio API Key [shipped]
- **What was done:** המשתמש עדכן את ה-API key של Google AI Studio (המשמש ל-nano-banana-2 / Gemini image generation).
- **Decisions:** אין שינוי קוד — עדכון key בלבד ב-.env.
- **Notes / Caveats:** ה-key מאוחסן תחת `NANO_BANANA_API_KEY` (ולא `GEMINI_API_KEY` כפי שמופיע ב-.env.example). אם יצירת תמונות לא עובדת, לבדוק שה-.env מעודכן ו-MCP טעון.
- **Related:** [[yuval-agent]], [[claude-settings]]
