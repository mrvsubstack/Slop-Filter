---
name: stop-the-slop
description: >
  Eliminate AI writing patterns from prose — humanizations, rewrites, edits, scoring, and diagnostics.
  Use this skill whenever the user says "humanize this" "rewrite this," "edit this," "make this better",
  "clean this up," "make this sound human," "write naturally," "review this draft," 
  "too much AI slop," or pastes text and asks for feedback. Also trigger when the user 
  shares a paragraph and says anything like "Make it clear," "too formal," "does this sound AI?" "too robotic," "fix the voice,"
  or "this doesn't sound natural." "make it better" "improve this" If prose is involved and quality is the question, use this skill.
---

# Stop the Slop

**Job:** Score, diagnose, and rewrite prose to eliminate predictable AI patterns.

**Default output sequence:**
1. Score (use the scoring table below)
2. Diagnosis — list each failure with the exact phrase
3. Rewrite — clean version with no explanation

If the user only asks for a rewrite (no score), skip to step 3.

---

## Reference Files

| Task | File to read |
|------|-------------|
| Specific banned phrases and adverbs | `references/phrases.md` |
| Structural patterns to avoid | `references/structures.md` |
| Before/after examples | `references/examples.md` |

Read `phrases.md` and `structures.md` for any scoring or rewriting task. Read `examples.md` when the user asks to see examples or when you need calibration.

---

## Core Rules

1. **Cut filler phrases.** See `references/phrases.md` for the full list.
2. **Break formulaic structures.** Binary contrasts, negative listings, rhetorical setups, false agency. See `references/structures.md`.
3. **Active voice.** Every sentence needs a human subject doing something.
4. **Be specific.** No vague declaratives. Name the thing.
5. **Put the reader in the room.** "You" beats "People." Specifics beat abstractions.
6. **Vary rhythm.** Mix sentence lengths. Two items beat three. No em dashes.
7. **Trust readers.** State facts directly. No softening, no hand-holding.
8. **Cut quotables.** If it sounds like a pull-quote, rewrite it.

---

## Quick Checks

Run before delivering any prose:

- Any adverbs? Kill them.
- Any passive voice? Find the actor, make them the subject.
- Inanimate thing doing a human verb ("the decision emerges")? Name the person.
- Sentence starts with a Wh- word? Restructure it.
- Any "here's what/this/that" throat-clearing? Cut to the point.
- Any "not X, it's Y" contrasts? State Y directly.
- Three consecutive sentences match length? Break one.
- Paragraph ends with punchy one-liner? Vary it.
- Em-dash anywhere? Remove it.
- Vague declarative ("The implications are significant")? Name the specific implication.

---

## Scoring
 
Rate 1–10 on each dimension using the anchors below.
 
| Dimension | 10 /10| 5/10 | 1/10 |
|-----------|-----|---|---|
| Directness | Immediate point | Mixed setup | Buried point |
| Naturalness | Human voice | Mixed AI signals | Template-heavy |
| Rhythm | Varied sentence flow | Moderate repetition | Mechanical pacing |
| Clarity | Precise meaning | Slightly vague | Abstract filler |
| Density | No waste | Some filler | Bloated |
 
**Thresholds and actions:**
 
| Score | Label | Action |
|-------|-------|--------|
| 46–50 | Clean | Deliver as it is |
| 36–45 | Light edit needed | Fix it and deliver |
| <35 | Rewrite required | Full rewrite before delivering |

---

## Inline Example

**Before:**
> "Here's the thing: building products is hard. Not because the technology is complex. Because people are complex. Let that sink in."

**After:**
> "Building products is hard. Technology is manageable. People aren't."

**What changed:** Removed opener, binary contrast, emphasis crutch. Three direct statements.

See `references/examples.md` for more.
