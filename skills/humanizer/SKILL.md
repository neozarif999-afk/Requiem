---
name: humanizer
description: Rewrite AI-sounding text to read like it was written by a person, using Wikipedia's "Signs of AI writing" essay (WP:AISIGNS) as the detection checklist. Use when asked to "humanize" text, "make this sound less AI," "remove AI tells," "de-slop" a draft, or polish a blog post/essay/article/email that reads stilted, robotic, or ChatGPT-flavored.
---

# Humanizer

Rewrites text to remove the tells catalogued in Wikipedia's community-maintained
essay [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
(shortcut `WP:AISIGNS`). That essay is a field guide Wikipedia editors use to spot
undisclosed LLM-generated edits; used in reverse, it's a checklist for what to strip
out of your own drafts.

The full checklist, with examples, lives in `reference/signs-of-ai-writing.md`. Read
it before doing a rewrite pass — don't rely on memory of the category names alone.

## Core principle

These are **signals, not sins**. The essay itself says the same words and patterns
show up in genuine human writing (LLMs were trained on humans, after all). The goal
is not to purge every word on the list — it's to notice when a text is *leaning on*
these patterns as a crutch, formulaically, in place of an actual human voice, and
fix that. Never mechanically find-and-replace a flagged word with a synonym; that
just swaps one tic for another. Rewrite the underlying sentence.

Never invent facts, sources, or specifics that weren't in the original to make a
sentence sound more "human." Never fabricate a citation to replace one you removed.
If a citation looks hallucinated, flag it — don't silently invent a replacement.

## Workflow

1. **Read the whole text first.** Get the actual content and the author's intended
   voice/register (formal report vs. casual blog vs. Wikipedia article) before
   touching anything.

2. **Flag pass.** Go through `reference/signs-of-ai-writing.md` category by
   category and mark every hit in the text: puffery, overused vocabulary,
   formulaic transitions, editorializing, compulsive summarizing, formatting
   tells, citation problems, leftover chatbot artifacts, rhetorical tics. Don't
   skip categories just because the obvious ones (em dashes, "delve") are absent
   — formatting and structural tells are just as diagnostic and easier to miss.

3. **Rewrite pass.** For each flagged instance:
   - Puffery/importance-inflation → cut it or replace with the actual, specific
     fact that justifies the claim (or delete the sentence if there is none).
   - Overused vocabulary → replace with a plainer word, or better, restructure the
     sentence so no synonym is needed at all.
   - Formulaic transitions / rule-of-three / negative parallelism → break the
     pattern; vary sentence length and structure across paragraphs.
   - Editorializing hedges → cut the throat-clearing phrase, state the point
     directly, or attribute it properly if it's genuinely someone else's claim.
   - Compulsive summaries ("In conclusion," "Overall,") → delete; don't restate
     a section that's short enough to just read.
   - Formatting tells (title-case headers, bold-term bullet lists, formulaic
     spaced em dashes) → convert to the target format's actual conventions.
   - Citation problems → verify the citation supports the claim and actually
     exists; flag anything you can't verify instead of leaving or replacing it
     silently.
   - Leftover chatbot artifacts ("As an AI language model," "I hope this
     helps!," stray tool-call placeholder tokens) → delete outright, these are
     never intentional content.

4. **Voice check.** Read the rewrite against the original register. A casual
   email shouldn't come out sounding like a press release with the AI-tells
   removed, and vice versa. Vary sentence rhythm — real human writing has
   short and long sentences mixed, not uniform, evenly-balanced clauses.

5. **Final pass.** Re-read once for anything that still sounds like it's
   performing importance rather than stating fact, and confirm no fact,
   number, name, or citation was altered or invented during the rewrite.

## Output

Return the rewritten text. If the input was long or the changes were extensive,
briefly note (in a few sentences, not a report) which categories of tell were
most present — this helps the user spot the pattern in their own future drafts.
Don't produce a line-by-line diff unless asked.
