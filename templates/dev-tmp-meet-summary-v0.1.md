# Filename: Mesh/Types/Meetings/(Meeting) [Name] ([YYYY-MM-DD]).md

```markdown
---
id: [generate-uuid4]
tags:
  - "#meet/meeting"
status: [active|archived]
date: [YYYY-MM-DD]
attendees:
  - [attendee name(s) if identifiable from transcript]
  - (continue)
raw: "[[(Meeting) [Name] ([YYYY-MM-DD]) . Raw]]"
/* If corrections were applied: */
cleaned: "[[(Meeting) [Name] ([YYYY-MM-DD]) . Cleaned]]"
[agent]-sessions:
  - "[[agent-session-uuid]]"
template: "[[dev-tmp-meet-summary-v0.1]]"
authors: /* from .flint/identity.json; omit if no identity set */
  - "[[@Person Name]]"
---

## Overview

[1-3 sentence summary of what the meeting covered — topic, purpose, key outcome]

---

## Key Announcements

/* Extract significant announcements, news, or updates shared during the meeting. Group under subheadings if there are distinct topics. */

### [Announcement Topic]

- [Key point]
- (continue)

(continue)

---

## Decisions

/* Capture decisions made during the meeting. Each decision should be clear and actionable. */

- **[Decision topic]** — [What was decided]
- (continue)

---

## Discussion

/* Summarize the main discussion topics. Use subheadings for distinct threads. Include enough context for someone who wasn't present to understand the conversation. */

### [Discussion Topic]

[Summary of discussion — key points, arguments, context]

(continue)

---

## Action Items

/* Extract concrete action items. Mark who is responsible if identifiable. */

### Immediate

- [Action item with owner if known]
- (continue)

### Follow-up

- [Longer-term action items]
- (continue)

---

## Quotes

/* Notable or significant quotes from the meeting. Use blockquotes. Only include quotes that capture important insights or decisions. */

> "[Notable quote]"

(continue)

---

## Related Documents

- [[Related document(s) — tasks, plans, notepads, or other meetings]]
- (continue)
```

/* Notes:
   - Sections are optional — omit any section that has no content (e.g., skip Quotes if none are notable)
   - The Overview should stand alone as a useful summary
   - Action Items should be specific enough to act on
   - Decisions should be unambiguous
   - The summary should be useful to someone who wasn't at the meeting
*/
