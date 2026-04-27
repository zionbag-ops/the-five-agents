---
title: yael agent
tags:
  - agent
  - content-writing
  - llm-only
---

# יעל — סוכנת כתיבת תוכן

## Overview
סוכנת כתיבת תוכן LLM-Only (ללא MCP/API חיצוניים). קוראת מאמרים מ-`Content/`, משכתבת אותם לפי `Content/style-guide.md`, מבקשת תמונות מיובל כשנדרש, ושומרת תוצאות ב-`Published/`. מוגדרת ב-`.claude/agents/yael.md`.

## Open Questions
- none

## Session Log

### 2026-04-27 — יצירת הסוכנת [shipped]
- **What was done:** נוצרו כל קבצי הסוכנת: `.claude/agents/yael.md`, `Content/style-guide.md`, `Content/.gitkeep`, `Published/.gitkeep`. מדריך הסגנון כולל: קול ואווירה, מבנה מאמר, כללי שפה, הנחיות תמונה.
- **Decisions:** LLM-Only — tools: Read, Write, Agent בלבד. תמונות רק כשיש ערך ויזואלי ממשי. שכתוב שומר על המסר המקורי, משנה רק סגנון. יובל מטפל בכל בקשת תמונה.
- **Notes / Caveats:** כדי להשתמש ביעל — שים קובץ MD ב-`Content/` ובקש מה-CEO "תן ליעל לעבד את <שם הקובץ>". הפלט יופיע ב-`Published/<שם הקובץ>.md`.
- **Related:** [[yuval-agent]], [[ceo-agent-prd]], [[src-agents]]

### 2026-04-27 — שכתוב ai-agents-intro.md [shipped]
- **What was done:** קראתי `Content/style-guide.md` ו-`Content/ai-agents-intro.md`. שכתבתי את המאמר לפי מדריך הסגנון ושמרתי ב-`Published/ai-agents-intro.md`. ניסיתי לקרוא ל-יובל ליצירת 3 תמונות — nano-banana-2 MCP לא זמין בסשן הנוכחי, לכן הוטמעו placeholder image paths.
- **Changes made:** כותרת ראשית חדשה (ממוקדת + מבטיחת ערך), פתיחה קצרה ב-2 משפטים, פסקאות מקוצרות ל-3-4 משפטים, כל המשפטים מתחת ל-20 מילה, הסרת לשון סביל, הסרת מילות מילוי, הוספת 3 מיקומי תמונה עם captionים תיאוריים.
- **Image status:** 3 תמונות מוגדרות עם paths ב-outputs/ — nano-banana-2 לא זמין, placeholders בוטמעו.
- **Related:** [[yuval-agent]], [[nano-banana-2-skill]]

### 2026-04-27 — שכתוב crm-intro.md [shipped]
- **What was done:** קראתי `Content/style-guide.md` ו-`Content/crm-intro.md`. שכתבתי את המאמר לפי מדריך הסגנון ושמרתי ב-`Published/crm-intro.md`. לא בוקשו תמונות — המאמר אינו דורש ויזואלים.
- **Decisions:** שמרתי על הקול האישי של הכותב: סיפור הפיצה, איתי זרם, אמוג'ים (😅 🙂), נוסח ראשון. קיצרתי משפטים ל-20 מילה מקסימום, החלפתי לשון סביל בלשון פעיל, הסרתי מילות מילוי (מאוד, כמובן, בעצם, למעשה). שמרתי את קטע שאלות ותשובות בשלמותו.
- **Notes / Caveats:** המאמר הוא מאמר מותג אישי — לא ניטרלי. טון ישיר, אישי ומחויב בכוונה.
- **Related:** [[yael-agent]], [[alon-agent]]
