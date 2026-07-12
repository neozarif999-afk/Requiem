# Signs of AI writing — reference checklist

Adapted from Wikipedia's essay [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
(`WP:AISIGNS`), which Wikipedia editors use to spot undisclosed LLM-generated
edits. The essay explicitly frames this as a **field guide, not a ban list**:
none of these words or patterns are inherently wrong, and human writers use
plenty of them too. What's diagnostic is *density* and *formulaic use* — several
of these stacked together, used as a crutch instead of an actual sentence.

Use this as a checklist when flagging a draft, then rewrite per the workflow in
`SKILL.md`.

## 1. Puffery and undue emphasis

Language that inflates the importance of something without giving a specific,
checkable reason for the claim:

- "stands as a testament to…", "serves as a reminder of…"
- "plays a vital/crucial/significant/pivotal role"
- "underscores/highlights the importance/significance of…"
- "marks a pivotal moment", "a key turning point"
- "rich cultural heritage", "breathtaking", "stunning natural beauty"
- "enduring legacy", "deeply rooted", "left an indelible mark"
- "symbolizing/reflecting broader themes of…"
- "continues to captivate", "cements its place", "solidifies its status"
- "represents/marks a shift", "setting the stage for…"

Fix: cut it, or replace with the concrete fact that would justify the claim
(a date, a number, a named cause/effect). If there's no such fact, the sentence
was empty and should go.

## 2. Overused vocabulary ("AI word list")

Words that are individually fine but overrepresented in LLM output relative to
normal usage, especially clustered together:

delve, boast/boasts, intricate/intricacies, meticulous/meticulously, tapestry,
testament, vibrant, underscore, pivotal, crucial, garner, bolster/bolstered,
landscape (used metaphorically, e.g. "the evolving landscape of…"), realm,
foster, enhance, leverage (as a verb), robust, comprehensive, notable, key
(as a generic adjective), valuable, interplay, multifaceted, ever-evolving,
groundbreaking, game-changer, "in the world of X", "when it comes to X",
"navigate the complexities of", "unlock the potential of", "focal point".

Fix: swap for the plainest available word, or better, rewrite the sentence
structurally so the word isn't needed. Don't just thesaurus-swap one tell for
another.

## 3. Formulaic transitions and sentence patterns

- Overuse of "moreover," "furthermore," "in addition," "on the other hand,"
  as connective tissue between nearly every paragraph — gives writing a
  stiff, formal, essay-like cadence.
- The "rule of three" overused as a crutch: "the good, the bad, and the
  ugly"-style triplets repeated sentence after sentence, well beyond what the
  content calls for.
- Negative parallelism / false contrast: "It's not just X, it's Y." "Not
  only did X happen, but Y also…" Fine occasionally; a tell when it recurs.
- Uniform, evenly-balanced sentence and paragraph structure repeated across
  the whole piece — real human writing has irregular rhythm, mixed sentence
  lengths, occasional fragments.

Fix: break the pattern. Vary sentence length. Let some paragraphs be short.

## 4. Editorializing and unsourced framing

- Throat-clearing hedges: "it's important to note that…", "it is worth
  noting…", "no discussion would be complete without…", "in the
  ever-changing world of…"
- False balance without real sourcing: "While some argue X, others believe
  Y" with no named parties or citations behind either side.
- Vague, unnamed attribution: "industry reports show…", "some critics
  argue…", "experts believe…" — sounds authoritative, names no one.

Fix: cut the hedge and state the point directly, or attribute the claim to
an actual named source. If there's no real source, don't imply there is one.

## 5. Compulsive summarizing

- Section- or paragraph-ending recaps: "In summary," "In conclusion,"
  "Overall," — restating what was just said, even in passages far too short
  to need a recap. This is a school-essay habit; most professional and
  encyclopedic writing (Wikipedia included) doesn't add "Conclusion"
  sections or wrap-up sentences to short pieces.
- Superficial "-ing" analysis clauses that restate rather than add
  information: "By combining X and Y, this approach demonstrates the
  power of…" — sounds like analysis, says nothing new.

Fix: delete the recap. Trust the reader to have read the preceding text.

## 6. Formatting tells

- **Title Case Section Headings** instead of the target format's actual
  convention (e.g., Wikipedia and most prose styles use sentence case).
- Excessive inline **bolding of "key terms"** that don't need emphasis.
- Bulleted or numbered lists formatted as `**Term**: definition of that
  term`, used as a substitute for a paragraph of connected prose — a
  distinctive chatbot-answer format that reads as a list dump rather than
  writing.
- Numbered lists used where the content is not actually sequential or
  enumerable — paragraphs would communicate it better.
- Markdown emphasis syntax (`**bold**`, `_italic_`) leaking into contexts
  that use a different convention (e.g. Wikipedia's `''italic''` wikitext,
  or a medium with no markdown support at all).

Fix: convert to the actual target format's conventions; turn "Term: definition"
list dumps back into normal paragraphs when the content is genuinely prose,
not a real enumerable list.

## 7. Punctuation: the em dash tell

Human writers use em dashes too, but LLM output uses them noticeably more
often, in place of commas or parentheses, in a formulaic "punched up" way —
and it almost always surrounds them with spaces ( — like this — ) rather than
following normal typographic convention (—like this—, no spaces, or spaced
en dashes depending on house style).

Fix: don't ban em dashes — just check whether a comma, a period, or
parentheses would be the more natural, less performative choice, and whether
the surrounding spacing matches the target style guide.

## 8. Citation and sourcing problems

- Hallucinated references: citations to sources that don't exist, broken
  links, fabricated DOIs, ISBNs with invalid checksums.
- Citations that are real but don't actually support the sentence they're
  attached to.
- Confident, specific-sounding claims with no citation at all where one
  would normally be expected.

Fix: verify every citation actually resolves and actually supports the
claim next to it. If you can't verify one, flag it to the user rather than
silently deleting, replacing, or inventing a new one.

## 9. Leftover chatbot artifacts

Straightforward tells that a chat response was pasted in with no editing:

- "As an AI language model…", "As of my last knowledge update…"
- "Certainly! Here's…", "I hope this helps!", "Would you like me to
  continue?", "Let me know if you'd like any changes."
- Stray tool-call placeholder tokens from browsing-enabled assistants (e.g.
  fragments like `turn0search0` left behind when a citation/link insertion
  didn't get cleaned up).
- Refusal or disclaimer boilerplate that has nothing to do with the
  surrounding content.

Fix: delete outright. These are never intentional content.

## Applying this list

1. None of these are individually disqualifying — flag *density* and
   *formulaic* use, not the mere presence of a word.
2. Preserve the author's actual voice and register; "de-AI-ing" a casual
   note shouldn't turn it into a press release, and vice versa.
3. Never trade accuracy for naturalness — don't invent facts, numbers,
   names, or citations to make a sentence sound more human.
