> [!important] THIS FILE IS AN INSTRUCTION. WHEN REFERENCED IT IS MEANT TO BE TAKEN AS AN ACTION.

This skill belongs to the Meetings shard. Ensure you have @init-meet.md in context before continuing.

# Skill: Clean Transcript

Strip transcript artifacts from a raw meeting transcript to produce a readable conversation.

# Input

- Raw transcript text (either from a file or passed as content)

# Actions

1. Read the raw transcript
2. Remove or clean the following artifacts:
   - **Timestamps** — remove inline timestamps (e.g., `[00:12:34]`, `0:12:34`, `12:34`)
   - **Speaker tags** — normalize speaker labels if present (e.g., `Speaker 1:` → consistent names if identifiable, otherwise keep as-is)
   - **Filler words** — remove excessive filler (`um`, `uh`, `like` when used as filler, `you know`)
   - **Repeated words** — fix stutters and repeated phrases from transcription (e.g., `the the` → `the`)
   - **Formatting artifacts** — remove transcription tool metadata, headers, footers, or system text
   - **Paragraph breaks** — consolidate fragmented sentences that were split across transcript segments
3. Preserve the conversational structure — keep speaker turns and topic flow intact
4. Return the cleaned text

# Guidelines

- Do NOT rewrite or rephrase — only clean artifacts
- Do NOT change the meaning or content of what was said
- Do NOT merge separate speaker turns
- Keep the transcript readable as a conversation
- When in doubt, leave content in rather than removing it

# Output

- Cleaned transcript text ready for summarization or further processing
