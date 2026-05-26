# Filename: Mesh/Types/Meetings/(Meeting) [Name] ([YYYY-MM-DD]) . Cleaned.md

```markdown
---
id: [generate-uuid4]
tags:
  - "#meet/cleaned"
date: [YYYY-MM-DD]
parent: "[[parent meeting summary file]]"
corrections-applied:
  - [list of correction types applied, e.g. "transcription-correction", "speaker-identification"]
  - (continue)
[agent]-sessions:
  - "[[agent-session-uuid]]"
template: "[[dev-tmp-meet-cleaned-v0.1]]"
authors: /* from .flint/identity.json; omit if no identity set */
  - "[[@Person Name]]"
---

[Cleaned transcript content — the result of running cleanup skills on the raw transcript. This version has corrections applied (misheard words fixed, domain terms corrected, etc.) while preserving the original conversational structure.]
```

/* Notes:
   - Only created if correction addons were applied during wkfl-meet-process
   - The corrections-applied field tracks what was done
   - The parent field links back to the summary file
   - The cleaned version preserves the conversation flow but fixes errors
*/
