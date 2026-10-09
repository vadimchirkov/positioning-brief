---
name: positioning-brief
description: Build a one-page brief before writing or rewriting a landing page, product or integration page, README or user docs for any project. Use when asked to improve a site or docs, write for a new audience or integration, or when existing text describes the code instead of what the reader needs. The brief comes first; pages and docs are generated from it, with code used only to check facts.
---

# Positioning brief

Text generated from the code describes the code. Readers need their problem, the
alternative they use today, and why to switch. Write the brief first, get the user to
confirm it, then write pages and docs from it.

Keep the brief in the project next to the page it drives, e.g. `docs/<page>-brief.md`.

## Process

1. **Read what exists, list what's wrong.** Read the current page or doc as plain text.
   Mark every internal identifier shown to the reader, every number and every claim.
   Check each number against the repo (`grep` the value). A number with no source in
   the repo is removed or attributed to its owner. Demo, stub or mock output is
   wiring, not a result.
2. **Ask the user who the reader is and what the page is for.** Reader, goal and
   positioning are the user's call. Ask in one message: who reads it, what they already
   know, what they want to do, and what the page must achieve. Offer concrete options
   based on what you learned in step 1: reader roles you can infer from the existing
   page, likely goals (installs, signups, docs visits, demo requests), awareness levels
   (knows the problem / knows solutions exist / knows us). Let the user pick or correct,
   not start from blank. Draft only after that; mark your own guesses `[?]`. One brief
   per audience: two different readers means two briefs, not one blended page.
3. **Research the reader's real problems and words.** Search for published failures,
   surveys, practitioner reports and papers in the reader's area. Keep numbers and
   links. Collect the reader's own phrasing from issues, forums, discussions and support
   threads; headings use their words, not ours. Read competitors' docs, not their
   marketing, to learn what they actually do and where they stop. Date every external
   fact: competitors and numbers change.
4. **Map each problem to a mechanism in the code.** For every claim, find the code that
   makes it true. If nothing backs it, drop the claim or list it under "does not do".
5. **Write the brief** (template below) and hand it to the user to edit. Do not write
   the page until reader, moment and differentiation are confirmed.
6. **Write from the brief.** Outline first: one idea per section, a heading plus one
   line each. Then copy. Use the brief's dictionary; internal names stay in code blocks
   and reference docs. Split docs by Diátaxis (tutorial, how-to, reference,
   explanation). A landing page links to a tutorial, not to the reference.
7. **Check.** Run every example the page quotes and paste the real output. Then a naive
   reader check: a fresh agent or prompt that gets only the page, no repo, retells what
   the product does, for whom and how it differs, and lists every term it didn't
   understand. Compare with the brief's "30 seconds" section and rewrite where they
   differ. Finish with a style pass under the project's writing rules, if it has any.
8. **Test with real readers.** Show the page to two or three people who match section 1
   for five seconds, then ask what it is, who it is for and whether they would try it.
   No agent replaces this; if it can't happen, say so in the handoff.
9. **Keep it current.** The brief and every page built from it carry a date. When the
   product, evidence or competitors change, update the brief first, then the pages.

## Brief template

```markdown
# Brief: <page>

## 0. Goal
What this page must make the reader do, and how we will know it worked.

## 1. Reader
Role, what they already have, what they know (do not explain it), what is new to
them (explain it). Who this page is not for.
Awareness: do they know they have the problem? Do they know solutions exist? Do they
know us? The answer sets where the page starts: the problem, the approach, or the
product.

## 2. Moment
Situations in which they look for a product like this. Each with a sourced example
or number.

## 3. What they use today
Each alternative: what it really does, from its docs. Where it stops.

## 4. What we have
Category: what the reader should file this under, in words they already use. If it is
a new kind of thing, name the known category it differs from and how.
The main idea in one sentence. Then problem from section 2 → mechanism that answers
it. Then what the product does not do, stated plainly.

## 5. Evidence
Only measured results, each with a link to method and raw numbers. Then other proof if
real: named users, adoption, quotes with permission. List what may not be claimed
(unmeasured, demo-only, unsourced) and which measurement would close the biggest gap.

## 6. Objections
The reader's questions with short, factual answers (effort, cost, data needed,
comparison with the alternative).

## 7. In 30 seconds the reader understands
Three or four points. This is the test the naive reader must pass.

## 8. One action
The primary CTA and a second one. Prefer "run X" or "try X" over "star us".

## 9. Dictionary
| In code | On the page |
Internal names → the reader's words. Names that never appear on the page.

## 10. Out of scope
What goes to reference or explanation docs, not to the page.
```

## Rules

- Evidence only from real measurements. No demo output as a gain, no unsourced numbers,
  no other projects' results presented as yours.
- Negative results stay out of marketing pages; they belong in changelogs, lessons or
  example READMEs. Honest limits ("does not do X") are scope, not negative results, and
  stay on the page.
- When evidence is thin for the chosen reader, name the missing measurement and propose
  the run. Do not fill the gap with copy.
- Concrete numbers and names over adjectives. Follow the project's writing rules
  (AGENTS.md, CLAUDE.md, style guide) when it has them.
