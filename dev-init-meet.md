# Meetings Shard

Process meeting transcripts into structured summaries. Takes raw audio transcriptions (e.g. from Whisper), cleans them up, and produces organized meeting summaries with key decisions, action items, and quotes.

## Rules

1. **Meetings are date-anchored.** Every meeting file includes a date in the filename. The date is the meeting date, not the processing date.
2. **Raw transcripts are preserved.** The original transcript is always kept as a `. Raw` derivative. Never modify the raw file after creation.
3. **Cleaning is optional and additive.** Base cleanup (stripping transcript artifacts) always runs. Additional addons like transcription correction are prompted during the workflow.
4. **Summaries follow the template.** Use `dev-tmp-meet-summary` to produce consistent, structured output.
5. **Derivatives use dot notation.** Raw, Cleaned, and any other derivatives follow the `(Meeting) Name (Date) . Derivative.md` pattern.

## Lifecycle

```
active → archived
```

| Status | Meaning |
|--------|---------|
| `active` | Meeting recently processed, still relevant |
| `archived` | Meeting complete, action items extracted |

## File Structure

| File | Purpose |
|------|---------|
| `(Meeting) Name (Date).md` | Structured summary (primary artifact) |
| `(Meeting) Name (Date) . Raw.md` | Original transcript, preserved verbatim |
| `(Meeting) Name (Date) . Cleaned.md` | Transcript with corrections applied (optional) |

- Location: `Mesh/Types/Meetings/`
- Archive: `Mesh/Archive/Meetings/`
- Tags: `#meet/meeting` (summary), `#meet/raw` (transcript), `#meet/cleaned` (corrected)

## Naming

```
(Meeting) Name (Date).md
```

- **Name**: descriptive topic or recurring meeting name
- **Date**: `YYYY-MM-DD` format, always in parentheses
- Examples: `(Meeting) Flint Architecture (2025-12-03).md`, `(Meeting) Weekly Sync (2026-03-05).md`

## User Flow

1. User creates `(Meeting) Name (Date).md` in `Mesh/Types/Meetings/`
2. User pastes raw transcript into the file body
3. Agent runs `dev-wkfl-meet-process` to process the meeting

## Skills

| Skill | File | Purpose |
|-------|------|---------|
| Clean | `dev-sk-meet-clean.md` | Strip transcript artifacts (timestamps, speaker tags, filler) |
| Correct | `dev-sk-meet-correct.md` | Context-aware transcription correction using Flint knowledge |

## Workflows

| Workflow | File | Purpose |
|----------|------|---------|
| Process Meeting | `dev-wkfl-meet-process.md` | Full pipeline: rename to Raw, clean, optional addons, summarize |

## Templates

| Template | File | Purpose |
|----------|------|---------|
| Summary | `dev-tmp-meet-summary-v0.1.md` | Structured meeting summary |
| Raw | `dev-tmp-meet-raw-v0.1.md` | Raw transcript derivative |
| Cleaned | `dev-tmp-meet-cleaned-v0.1.md` | Cleaned/corrected transcript derivative |
