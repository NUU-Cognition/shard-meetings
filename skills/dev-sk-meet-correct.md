> [!important] THIS FILE IS AN INSTRUCTION. WHEN REFERENCED IT IS MEANT TO BE TAKEN AS AN ACTION.

This skill belongs to the Meetings shard. Ensure you have @init-meet.md in context before continuing.

# Skill: Correct Transcription

Context-aware transcription correction that uses the Flint's knowledge to fix misheard words, domain terms, and project names.

# Input

- Cleaned transcript text (output of `dev-sk-meet-clean` or the raw transcript)
- The Flint workspace context (loaded via init files, mesh content)

# Actions

1. Load context from the Flint to build a domain vocabulary:
   - Read `(System) Flint Init.md` for project names, shard names, and key terms
   - Scan recent tasks, plans, and notepads for active terminology
   - Note proper nouns: people, tools, frameworks, concepts specific to this workspace
2. Read through the transcript and identify likely transcription errors:
   - Words that sound like domain terms but were transcribed as common words (e.g., "mesh" → "mess", "shard" → "shared", "flint" → "flinch")
   - Technical terms that were phonetically transcribed (e.g., "typescript" → "type script", "turborepo" → "turbo repo")
   - Project names and proper nouns that were mangled
   - Acronyms that were expanded or misheard (e.g., "NUU" → "new", "CLI" → "see lie")
3. Apply corrections in place, preserving the surrounding context
4. Return the corrected transcript

# Guidelines

- Only correct words that are clearly wrong based on context
- When ambiguous, leave the original transcription
- Do NOT add content that wasn't said
- Do NOT restructure sentences — only fix individual words or short phrases
- Keep a mental note of corrections made for the `corrections-applied` metadata

# Output

- Corrected transcript text with domain-aware fixes applied
