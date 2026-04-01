# stop-the-slop 🧹

### The only Claude skill that catches what other tools miss

**Score prose · Diagnose failures · Rewrite clean · Two-pass validation**

---

## The problem with AI Humanizers
The real problem with AI writing isn’t the fancy words.

Run your text through any “humanizer” and it’ll happily swap “utilize” for “use,” delete every “furthermore,” and its Done.

A real person reads it anyway and still spots it instantly.

Because the giveaway isn’t the fancy words. It's the patterns underneath them — the lazy connectors, the topic sentences that spoil the whole idea in the first line, the paragraphs that circle back and say exactly what they said at the start. Those deeper patterns survive every surface-level polish.

This skill catches them.

---

## Before & After

**Before:**
> "Here's the thing: building products is hard. Not because the technology is complex. Because people are complex. Let that sink in."

**After:**
> "Building products is hard. Technology is manageable. People aren't."

**What changed:** Opener removed. Binary contrast cut. Emphasis crutch gone. Three direct statements.

---

**Before (subtle failure — passes most tools):**
> "When you're deep in a project, it's easy to lose sight of the original goal. This happens to most teams."

**After:**
> "Most teams drift. Nobody notices until the deadline."

**What changed:** "When you're deep in" is a slow conditional entry. "This happens to most teams" observes from a distance instead of naming who does the thing. Neither phrase appears on a standard banned list. Both produce the same softness. The skill catches both.

---

## What it catches

### Two layers — most tools only do one

**Layer 1: Sentence-level patterns**

| Category | Examples caught |
|----------|----------------|
| Throat-clearing openers | "Here's the thing:" · "It turns out" · "The uncomfortable truth is" |
| Emphasis crutches | "Let that sink in." · "Full stop." · "Make no mistake" |
| Business jargon | navigate · leverage · lean into · circle back · game-changer |
| All adverbs | really · just · literally · genuinely · actually · crucially |
| Meta-commentary | "Let me walk you through..." · "In this section, we'll..." |
| Vague declaratives | "The implications are significant" · "The stakes are high" |
| False agency | "the decision emerges" · "the culture shifts" · "the data tells us" |
| Binary contrasts | "Not because X. Because Y." · "The answer isn't X. It's Y." |
| Passive voice | every construction where a human subject can be named instead |
| Em dashes | removed, always |

**Layer 2: Second-generation tells (what survives the first pass)**

These don't appear on any standard list. They survive because they look clean sentence-by-sentence. They fail at the paragraph level.

| Pattern | Why it fails |
|---------|-------------|
| "This means that..." | Lazy connector — the writer didn't earn the transition |
| "When you X, you Y" as an opener | Conditional filler — sounds thoughtful, reads as stall |
| "There's something about X that..." | Circling instead of landing |
| "What this looks like in practice..." | Announcing the example instead of giving it |
| "It's a reminder that..." | Moralizing closer |
| "And yet." (standalone) | Performative tension |
| 3+ sentences opening with "The" or "This" | Opener uniformity |
| Last sentence of a paragraph restating the first | Semantic repetition |
| Every paragraph beginning with a topic sentence | Topic sentence pattern |

---

## Scoring

Start every dimension at 10. Deductions are specific and enumerable — same text produces the same score every session.

| Dimension | Deduct when |
|-----------|-------------|
| **Directness** | Context-setting before the point · restated conclusion · passive constructions |
| **Naturalness** | Banned phrases · second-generation tells · adverbs · register shifts |
| **Rhythm** | Uniform sentence lengths · repeated openers · consecutive punchy closers · em dashes |
| **Clarity** | Vague declaratives · inanimate subjects doing human verbs · lazy extremes |
| **Density** | Paragraph's last sentence restates its first · same idea across paragraphs · cuttable sentences |

**Thresholds:**

| Score | Action |
|-------|--------|
| 46–50 | Clean. Deliver as-is. |
| 36–45 | Light edit. Fix and deliver. |
| <35 | Full rewrite before delivering. |

**Two-pass rule:** After any rewrite, the skill runs all checks again before scoring. The second pass catches what the first one missed.

---

## What makes this different

| Feature | Stop-the-Slop | Standard humanizers | "Make this sound human" prompt |
|---------|:---:|:---:|:---:|
| Sentence-level pattern removal | ✅ | ✅ | ⚠️ inconsistent |
| Second-generation tells | ✅ | ❌ | ❌ |
| Paragraph-level diagnosis | ✅ | ❌ | ❌ |
| Opener uniformity check | ✅ | ❌ | ❌ |
| Semantic repetition across paragraphs | ✅ | ❌ | ❌ |
| Topic sentence pattern detection | ✅ | ❌ | ❌ |
| Calibrated deduction scoring | ✅ | ❌ | ❌ |
| Two-pass validation | ✅ | ❌ | ❌ |
| Asks before inventing facts | ✅ | ❌ | ❌ |
| Same score on same text every session | ✅ | ❌ | ❌ |

---

## Who this is for

**Newsletter writers** who use AI to draft and need the output to sound like them, not like a model trying to sound helpful.

**Ghostwriters** reviewing AI-assisted drafts before they go to clients.

**Content teams** who run everything through a final quality check before publishing.

**Founders and operators** who write their own content and want a fast second pass before hitting send.

---

## What it won't do

It won't make writing sound like *you specifically* — that's a voice problem, not a slop problem. This skill removes what's wrong. A separate skill handles installing what's yours.

It won't guarantee AI detection scores. Detection tools measure statistical patterns. This skill measures whether prose sounds like a person wrote it. Those are different problems. Optimizing for detector scores produces broken grammar. This doesn't.

---

## Skill structure

```
stop-the-slop/
├── SKILL.md                    # Core instructions, scoring, quick checks
├── references/
│   ├── phrases.md              # Banned phrases + second-generation tells
│   ├── structures.md           # Structural patterns with generative rules
│   └── examples.md             # 13 before/after examples (5 obvious, 8 subtle)
├── README.md
└── LICENSE
```

---

## How to install

**Claude Projects:** Upload `SKILL.md` and the `references/` folder to project knowledge.

**Claude Code:** Add this folder as a skill.

**API / system prompt:** Include `SKILL.md` in your system prompt. Reference files load on demand.

---

## How to trigger it

Say any of these and the skill activates:

> "rewrite this" · "edit this" · "does this sound AI?" · "clean this up" · "make this sound human" · "score my writing" · "review this draft" · "too formal" · "too robotic" · "this doesn't sound like me"

Or paste text and ask for feedback. If prose quality is the question, the skill runs.

---

## License

MIT. Use freely, share widely.
