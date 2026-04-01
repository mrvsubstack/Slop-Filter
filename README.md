# stop-the-slop
Use this when you want your writing to sound like a real person. Use it when drafting, rewriting content, editing, or reviewing text to eliminate predictable AI tells.

This skill is triggered whenever you use these words: 

"rewrite this," "edit this," "does this sound AI?",
"clean this up," "make this human," "score my writing," 
"Review this draft," "Make it clear," "too formal," 
"too robotic" "write natural." 

Or paste a text and ask Claude for feedback

## Skill Structure

```
stop-slop/
├── SKILL.md              # Core instructions
├── references/
│   ├── phrases.md        # Phrases to remove
│   ├── structures.md     # Structural patterns to avoid
│   └── examples.md       # Before/after transformations
├── README.md
└── LICENSE
```

## Quick start

**Claude Code:** Add this folder as a skill.

**Claude Projects:** Upload `SKILL.md` and reference files to project knowledge.

**Custom instructions:** Copy core rules from `SKILL.md`.

**API calls:** Include `SKILL.md` in your system prompt. Reference files load on demand.

## What it catches

**Banned phrases** - Throat-clearing openers, emphasis crutches, business jargon, all adverbs, vague declaratives, meta-commentary. See `references/phrases.md`.

**Structural clichés** - Binary contrasts, negative listings, dramatic fragmentation, rhetorical setups, false agency, narrator-from-a-distance voice, passive voice. See `references/structures.md`.

**Sentence-level rules** - No Wh- sentence starters, no em dashes, no staccato fragmentation, no lazy extremes, active voice required.

## Scoring

Rate 1-10 on each dimension:

| Dimension | 10 /10| 5/10 | 1/10 |
|-----------|-----|---|---|
| Directness | Immediate point | Mixed setup | Buried point |
| Naturalness | Human voice | Mixed AI signals | Template-heavy |
| Rhythm | Varied sentence flow | Moderate repetition | Mechanical pacing |
| Clarity | Precise meaning | Slightly vague | Abstract filler |
| Density | No waste | Some filler | Bloated |

Below 35/50: revise.

## License

MIT. Use freely, share widely.
