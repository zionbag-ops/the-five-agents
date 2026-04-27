---
title: yuval agent
tags:
  - agent
  - image-generation
  - creative
---

# Agent: יובל (yuval)

## Overview
סוכן קריאייטיב שמתמחה ביצירת תמונות עקביות ויזואלית לפרויקט. סורק תמונות מתיקיית `reference/`, מנתח סגנון/פלטה/קומפוזיציה, מחלץ רכיבים רלוונטיים, מנסח prompt מותאם, ומפעיל את הסקיל `nano-banana-2`. שומר פלט ב-`outputs/`. מוגדר ב-`.claude/agents/yuval.md`.

## Open Questions
- none

## Session Log

### 2026-04-27 — יצירת הסוכן [shipped]
- **What was done:** נוצר `.claude/agents/yuval.md` עם 7 שלבי עבודה מוגדרים: סריקה, ניתוח, מיצוי, ניסוח prompt, הפעלת nano-banana-2, שמירה, דיווח.
- **Decisions:** יובל מבקש אישור prompt לפני ביצוע — נותן למשתמש שליטה על מה שנשלח למודל. שמות קבצי output כוללים timestamp למניעת דריסה.
- **Notes / Caveats:** תלוי בסקיל nano-banana-2 שעדיין בסטטוס wip. יפעל מלא רק אחרי השלמת הגדרת ה-MCP.
- **Related:** [[nano-banana-2-skill]], [[src-agents]]

### 2026-04-27 — ניסיון יצירת 4 תמונות לפרסומים [blocked]
- **What was done:** CEO ניסה להפעיל יובל ליצירת 4 תמונות חסרות: `ai-agent-diagram.png`, `multi-agent-team.png`, `ai-agent-workflow.png`, `claude-agents-workspace.png`. בוצעה סריקת reference (תמונת reference אחת: פורטרט business), ניתוח style_profile, ניסוח 4 prompts באנגלית. ניסיון הפעלת API ישירה נכשל.
- **Decisions:** כל ניסיונות ה-API נחסמו: `limit: 0, free_tier_input_token_count`. הבעיה ב-account tier, לא ב-key עצמו. Prompts מוכנים ומחכים להפעלה.
- **Notes / Caveats:** הפתרון: הפעל billing ב-Google AI Studio (https://ai.dev/projects) ואז חזור להריץ את המשימה. ה-API key הנוכחי יעבוד מיד לאחר הפעלת billing.
- **Prompts מוכנים:**
  - `ai-agent-diagram.png`: "An AI agent receiving a goal and activating multiple tools to achieve it. Central glowing blue brain node connected by arrows to icons: file reader, web browser, code editor, email client. Dark navy blue background, warm amber and electric blue accent colors, minimalist flat design with subtle depth, professional tech illustration, high quality, modern infographic style"
  - `multi-agent-team.png`: "Three specialized AI agents working together as a team: research agent, writing agent, review agent. Each represented as a distinct glowing node connected by data flow arrows. Dark navy blue background, electric blue and warm amber accents, minimalist tech illustration, professional flat design, high quality"
  - `ai-agent-workflow.png`: "Clear workflow diagram showing the process of defining a specific task for an AI agent: input box with specific goal arrow pointing to AI agent icon arrow pointing to output result. Dark navy background, amber highlights, clean minimal infographic, professional business style"
  - `claude-agents-workspace.png`: "Building an AI agent team: from idea to working product. Multiple AI agent icons arranged as a working team, connected by workflow arrows, with a central orchestrator. Professional tech illustration, dark navy blue and gold tones, modern flat design, business concept art"
- **Related:** [[nano-banana-2-skill]], [[claude-settings]]

### 2026-04-27 — ניסיון שני: יצירת 4 תמונות לאחר עדכון API key [blocked]
- **What was done:** המשתמש דיווח שעדכן API key ל-paid plan. CEO בדק שני keys מה-.env: `GEMINI_API_KEY` ו-`NANO_BANANA_API_KEY`. שניהם נבדקו ישירות מול MCP server (JSON-RPC) עם מודל `gemini-3.1-flash-image` (fast) ומודל `gemini-3-pro-image` (quality). שניהם חזרו עם שגיאת `RESOURCE_EXHAUSTED` + `free_tier_requests: limit: 0`.
- **Decisions:** הבעיה היא שה-API keys מקושרים ל-Google Cloud Projects שאין להם billing מופעל — לא מספיק ש"יש paid plan", צריך שה-project הספציפי שאליו שייך ה-key יהיה עם billing פעיל. Google AI Studio ו-Google Cloud Billing הם שני מערכות שונות.
- **Notes / Caveats:** יש שני דרכים לפתור:
  1. ב-Google AI Studio (https://ai.dev/apikey) — לחץ על ה-key, בדוק לאיזה project הוא שייך, הפעל billing על אותו project ב-Google Cloud Console.
  2. צור key חדש ב-Google AI Studio תוך כדי בחירת project עם billing מופעל.
  מיד לאחר הפעלת billing, אותו key יעבוד — לא צריך להחליף key.
- **Related:** [[nano-banana-2-skill]], [[claude-settings]]
