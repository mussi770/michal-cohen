---
name: mussi-price-quote
description: Write a price quote (הצעת מחיר) in Mussi Segal's style, as an interactive, bright, inviting Hebrew web page published as an Artifact. Use this whenever Mussi asks for a הצעת מחיר, הצעה ללקוח/ה, quote, proposal, "כמה לגבות", or wants to present an automation / CRM / Make / Origami / Meshulam project to a client with a price, even if he doesn't say "skill" or "artifact". Also use it when he asks to update, re-price or redesign a quote made this way.
---

# הצעת מחיר בסגנון של מוסי

Mussi Segal builds automations and CRM systems (Make, Origami, Meshulam/Grow, WhatsApp, WordPress) for small Israeli businesses. His quotes are not documents to sign. They are short, friendly web pages the client opens on her phone, understands in a minute, and approves by sending Mussi a WhatsApp message.

The reference implementation is `assets/template.html`, a real quote that Mussi approved. Start every new quote from a copy of it: keep its CSS and its JS as they are, and change only the content. The look is the part Mussi cares about most. A new design made from scratch would lose it.

## Workflow

1. **Collect the facts.** You need: the client's name and business, the problem in her words, what was found (if there was a diagnosis), the deliverables, and the price. If the price is missing, ask for it. Never invent a price, durations or payment terms. Leave out anything Mussi didn't give you, rather than adding a placeholder.
2. **Copy the template** to a new file in the scratchpad and replace the content section by section (structure below).
3. **Publish it as an Artifact** (HTML page, icon `invoice`), and give Mussi the link. Remind him that the page is private until he shares it with the client from the Share menu.
4. **Change it on request** by publishing the same file again (send small changes as `edits`), so the link stays the same.

## Page structure (in this order)

1. **Hero:** a soft colour gradient band.
   - A tag pill: `הצעת מחיר · <date DD.MM.YYYY>`.
   - An H1 that states the result for the client, not the topic. For example "כל תשלום ממשולם, מעודכן באוריגמי", not "הצעת מחיר לסנכרון".
   - A lead of one or two sentences in plain language.
   - `לכבוד <name> – <business> · מאת מוסי סגל`.
2. **מה מצאתי בבדיקה** (only if there was a diagnosis): a grid of small cards. Each card has a status pill (`חלקי` warn, `כבוי`/`נעצר`/`לא קיים` bad, `תקין` good), a bold title, and one short line about what it causes.
3. **מה תקבלי / מה תקבל:** an accordion of stages. The first stage is open, and each stage has its own colour icon (classes c1–c4). Every stage has:
   - a title
   - a one-line benefit
   - 2–3 bullets of what it includes
   
   Mark a stage that was added late with `<span class="new">חדש</span>`.
4. **Live demo** (when the deliverable has a screen, such as a dashboard or a form): an interactive mock-up with realistic **sample** data.
   - Mark it with the yellow `נתוני דוגמה` pill.
   - Use clearly fake names ("לקוחה לדוגמה 1") and masked phones.
   - Show the deliverable through the mock-up, and don't also list its fields or data points. Mussi asked to remove that list, because the mock-up is enough.
5. **סדר העבודה:** numbered pill chips in a row, one short note about how the work is tested and backed up, then two boxes: `לא כלול` and `מה נדרש ממך`.
6. **Price, at the bottom:** one closing card with the gradient background.
   - **One global price** for everything, in big numbers. Don't break the price down by stage, unless Mussi asks.
   - A list of ✓ items for what's included.
   - `מחיר כולל לכל השלבים · תוקף ההצעה 30 יום`.
   - Inside it, a white box: **"לאישור ההצעה — יש לכתוב בוואטסאפ למוסי."** No form, signature, checkbox or approve button.
7. **Footer:** `מוסי סגל · אוטומציות ו-CRM`.

## The look (keep it exactly)

- **Bright only.** The page uses a single light theme on purpose, even when the viewer's device is in dark mode (`:root{color-scheme:light}`, no dark-mode blocks).
- **Fresh and inviting.**
  - The background is near-white with a hint of teal (`#f7fbfc`).
  - The hero gradient runs mint → sky → peach.
  - The accent is teal (`#12a38f`), with sun yellow for "new" and "sample" badges.
  - Cards have rounded corners (16–26px), soft borders and very light shadows.
- **Type:** Rubik (700/800) for headings and big numbers, Assistant for body text.
- **Layout:** Hebrew right-to-left (`dir="rtl" lang="he"` on the wrapper), one column up to 820px wide, airy spacing (about 56px between sections), works on a phone.
- **Status colours** are used only for meaning: red means needs attention, amber means partial, green means OK.

## Content rules Mussi has set

- **Address the client in her or his own grammatical gender** (תקבלי / תקבל). Michal-style clients are addressed in the feminine.
- **Don't mention costs the client already pays,** such as subscriptions to Make, Origami or Meshulam.
- **Don't add a security or "risks" stage, or security findings,** unless Mussi asks. He removed them from the quote he approved.
- **Don't write VAT wording** ("לפני/כולל מע"מ") unless he specifies it. Ask him once instead.
- **Keep the copy short and concrete:**
  - real numbers from the diagnosis, such as "168 קבלות ממתינות בתור"
  - no jargon the client won't know, such as "webhooks"; write "התראות ממשולם" instead
  - no long paragraphs
- **If Mussi asks how long the work will take,** answer in chat with a table of hours per stage, and separately the manual hours he has to do himself. Add durations to the page only if he asks.
