---
name: stop-the-slop
description: "Eliminate AI writing patterns from prose — rewrites, edits, scoring, and diagnostics. Use this skill whenever the user says \"rewrite this,\" \"edit this,\" \"does this sound AI?\", \"clean this up,\" \"make this sound human,\" \"score my writing,\" \"review this draft,\" \"too much AI slop,\" or pastes text and asks for feedback. Also trigger when the user shares a paragraph and says anything like \"too formal,\" \"too robotic,\" \"fix the voice,\" or \"this doesn't sound like me.\" If prose is involved and quality is the question, use this skill."
---

# Stop the Slop

**Job:** Diagnose and rewrite prose to eliminate predictable AI patterns.

**Default output sequence:**
1. Diagnosis — list each failure with the exact phrase
2. Rewrite — clean version, no explanation

If the user only asks for a rewrite, skip to step 2.

**Scoring is opt-in.** Only run the scoring rubric if the user explicitly asks for a score, asks "is this clean enough to publish?", or asks "how far off is this?" Do not lead with a number by default — the diagnosis already contains everything the score summarizes, with more precision.

---

## Reference Files

| Task | File to read |
|------|-------------|
| Banned phrases, adverbs, second-generation tells | `references/phrases.md` |
| Structural patterns to avoid | `references/structures.md` |
| Before/after examples including subtle failures | `references/examples.md` |

Read **all three files** for every scoring or rewriting task. No exceptions. `examples.md` is not optional — it contains calibration for both standard failures and narrative writing principles that cannot be inferred from rules alone.

---

## Core Rules

1. **Cut filler phrases.** See `references/phrases.md` — includes second-generation tells that survive surface edits.
2. **Break formulaic structures.** Binary contrasts, negative listings, rhetorical setups, false agency. See `references/structures.md`.
3. **Active voice.** Every sentence needs a human subject doing something. No passive constructions.
4. **Be specific.** No vague declaratives. Name the thing. No lazy extremes doing vague work.
5. **Put the reader in the room.** "You" beats "People." Specifics beat abstractions.
6. **Vary rhythm.** Mix sentence lengths. Two items beat three. No em dashes.
7. **Trust readers.** State facts directly. No softening, justification, or hand-holding.
8. **Cut quotables.** If it sounds like a pull-quote, rewrite it. Exception: a story ending that earns its resonance through specific detail ("She thanked me for not rushing her") is not a quotable — it's a fact that lands. The test is whether the sentence is a general aphorism or a specific thing that happened. Aphorisms get cut. Specific facts that carry meaning stay.

---

## Quick Checks

**Multi-pass rule:** Run these checks twice. First pass clears obvious patterns. Second pass catches what survived. Deliver only after the second pass clears.

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
- Any second-generation tells? See `references/phrases.md`.

**Pattern checks (run on the full piece, not per sentence):**

- Do 3+ sentences open the same way? ("The", "This", "It", "You") — vary the openers.
- Does the same idea appear in different words across paragraphs? Cut one instance.
- Does every paragraph start with a topic sentence that summarizes what follows? Break the pattern — start one paragraph mid-thought.
- Do all paragraphs end at similar lengths? Vary the exit — cut one short, let one run.

---

## Feature Gap Targets

Removing bad patterns is half the job. The other half is closing the gap toward human writing on specific dimensions. After clearing slop, check these targets:

**Sentence length variance** — Human writing has spikes. A 6-word sentence next to a 22-word sentence. If all sentences cluster between 12–18 words, force an outlier in both directions.

**Opener diversity** — Scan the first word of each sentence across the piece. If more than 3 start with the same word, restructure. Human writers start sentences with names, numbers, verbs, conjunctions, time references — not just "The" and "This."

**Specificity ratio** — Count vague nouns vs. named things. "Teams struggle" is vague. "The engineering team at Stripe" is specific. If a paragraph has no proper noun, number, or named entity, it's floating.

When a floating paragraph is found, stop before fixing it. Ask the user:

> "This paragraph has no named reference points. To ground it, I can add one of these:
> - A number or statistic
> - A named person, company, or place
> - A personal example or anecdote
> - An analogy to something concrete
>
> Which fits what you're trying to say here?"

Wait for the answer. Then apply it. Do not invent facts, estimates, or examples to fill the gap — the user owns the specificity, the skill removes the vagueness around it.

**Paragraph exit variety** — How each paragraph ends shapes rhythm. AI tends to close every paragraph with a conclusive statement. Mix it: end one with a question, one with a fragment, one mid-argument that forces the reader into the next paragraph.

**Semantic freshness** — Read the last sentence of each paragraph. Does it restate the first? If yes, cut it. The paragraph already made the point.

---

## Scoring

Only run this section when the user explicitly requests a score.

Start every dimension at 10. Apply deductions. Final score = sum of all five dimensions.

**Directness** — start at 10
- −2 per sentence that opens with context-setting before the point ("When X happens, Y..." / "In order to understand...")
- −2 if the piece restates the opening claim in the conclusion
- −1 per passive construction where active would work

**Naturalness** — start at 10
- −2 per banned phrase found (see `references/phrases.md`)
- −2 per second-generation tell found
- −1 per adverb remaining after edit
- −1 if tone shifts register mid-piece (casual → formal or reverse)

**Rhythm** — start at 10
- −2 if all sentences cluster between 12–18 words with no outliers
- −2 if 3+ consecutive sentences open with the same word
- −1 per paragraph that ends with a punchy one-liner when the previous one did too
- −1 if em-dash appears anywhere

**Clarity** — start at 10
- −2 per vague declarative ("The implications are significant" / "This is important")
- −2 per inanimate subject doing a human verb ("the decision emerges")
- −1 per lazy extreme ("every," "always," "never") doing vague work

**Density** — start at 10
- −2 per paragraph whose last sentence restates its first
- −2 if the same idea appears in different words across two or more paragraphs
- −1 per sentence that could be cut without losing meaning

**Minimum per dimension: 0. No negatives.**

---

**Thresholds and actions:**

| Score | Label | Action |
|-------|-------|--------|
| 46–50 | Clean | Deliver as-is |
| 36–45 | Light edit needed | Fix and deliver |
| <35 | Rewrite required | Full rewrite before delivering |

---

## Inline Example

**Before:**
> "Here's the thing: building products is hard. Not because the technology is complex. Because people are complex. Let that sink in."

**After:**
> "Building products is hard. Technology is manageable. People aren't."

**What changed:** Removed opener, binary contrast, emphasis crutch. Three direct statements.

**Subtle failure example:**

**Before:**
> "When you're deep in a project, it's easy to lose sight of the original goal. This happens to most teams."

**After:**
> "Most teams drift. Nobody notices until the deadline."

**What changed:** "When you're deep in" is a slow entry. "This happens to most teams" observes from a distance instead of naming the actor. The rewrite puts the reader in it and names who does the thing. Neither phrase in the original triggers an obvious rule — that's the point.

See `references/examples.md` for more.
