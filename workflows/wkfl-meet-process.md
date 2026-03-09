This workflow belongs to the Meetings shard. Ensure you have @init-meet.md in context before continuing.

# Workflow: Process Meeting

Take a meeting file containing a raw transcript and produce a structured summary, preserving the original transcript as a derivative.

# Input

- A meeting file at `Mesh/Types/Meetings/(Meeting) Name (Date).md` containing a pasted raw transcript

# Actions

## Stage 1: Prepare Raw Derivative

1. Read the meeting file
2. Extract the transcript content (everything below the frontmatter, or the entire body if no frontmatter)
3. Create the Raw derivative using [[tmp-meet-raw-v0.1]]:
   - Filename: `(Meeting) Name (Date) . Raw.md`
   - Move the transcript content verbatim into this file
   - Add frontmatter with `#meet/raw` tag and `parent` link to the summary file
4. Clear the body of the original meeting file (keep frontmatter if it exists)

## Stage 2: Clean Transcript

1. Run [[sk-meet-clean]] on the raw transcript to produce a base cleaned version (strip timestamps, speaker tags, filler words, formatting artifacts)
2. **Prompt the user:** "Would you like to apply additional cleanup addons?"
   - **Transcription correction** (`sk-meet-correct`) — uses Flint context to fix misheard domain terms, project names, and concepts
   - **None** — proceed with base cleanup only
3. If addons selected, run them sequentially on the cleaned output
4. If any addons were applied, create the Cleaned derivative using [[tmp-meet-cleaned-v0.1]]:
   - Filename: `(Meeting) Name (Date) . Cleaned.md`
   - Track which corrections were applied in `corrections-applied` field

## Stage 3: Generate Summary

1. Use the cleaned transcript (or base-cleaned if no addons) as source material
2. Read other recent meetings and relevant Mesh context to inform the summary
3. Generate the summary using [[tmp-meet-summary-v0.1]] into the original meeting file
4. Ensure the summary frontmatter links to the Raw derivative (and Cleaned if it exists)

## Stage 4: Review

1. Present the summary to the user for review
2. User can request changes, additions, or corrections
3. Apply any requested changes
4. Once approved, the meeting is complete in `active` status

# Output

- `(Meeting) Name (Date).md` — structured summary (primary artifact)
- `(Meeting) Name (Date) . Raw.md` — original transcript preserved
- `(Meeting) Name (Date) . Cleaned.md` — corrected transcript (if addons applied)
