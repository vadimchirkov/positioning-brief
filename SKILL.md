---
name: positioning-brief
description: Build a one-page brief before writing or rewriting any text meant for people: landing pages, product pages, docs, READMEs, guides, announcements, or integration pages. Use when asked to improve existing text, write for a new audience, or when existing text explains how things work instead of what changes for the reader. The brief comes first; text is generated from it.
---

# Positioning brief

Generated text explains how things work. Readers care about what changes for them:
what problem goes away, what gets easier, why to switch. Write the brief first, get
the user to confirm it, then write from it.

Keep the brief in the project next to the page it drives, e.g. `docs/<page>-brief.md`.

## Entry points

Identify what the user brought and start there.

**A. Specific content.** User points at a page, several pages, a docs folder, or a
README. Read all of it in step 1, audit as a set. One brief covers the whole
surface; step 6 proposes which pages to rewrite, merge, split, or drop.

**B. Discovery.** User says "look at what docs we have" or "let's improve our
texts" without pointing at specific files. Find all user-facing text in the project:
docs/, README, site pages, examples with READMEs. List what exists with a one-line
summary of each. Propose which to tackle first based on what's weakest or most
visible. After the user picks, continue as entry A.

**C. An idea.** User describes what they want: "make a landing page for X", "write
docs for our SDK integration", "I need a page that explains Y". No text exists yet,
maybe no repo either. Skip step 1. Start at step 2 with what the user said as
context.

**D. Brief already exists.** User has a brief from a previous run and asks to write
from it. Read the brief, check it has all template sections filled. If any section
is empty or stale, flag it and ask the user before continuing. Then start at step 6.

**C. Brief already exists.** User has a brief from a previous run and asks to write
from it. Read the brief, check it has all template sections filled. If any section
is empty or stale, flag it and ask the user before continuing. Then start at step 6.

## Process

### Build the brief (steps 1-5)

1. **Audit existing content.** *(Skip for entry C.)* Read every page or doc the user
   pointed at. For a site or docs folder, read all files and note how they relate:
   what overlaps, what contradicts, what's missing. For each page, mark every internal
   identifier shown to the reader, every number and every claim. Check each number
   against the repo (`grep` the value). A number with no source in the repo is removed
   or attributed to its owner. Demo, stub or mock output is wiring, not a result.
   Hand the user a short summary: what's wrong, what overlaps across pages, and which
   pages serve the same reader vs. different audiences.
2. **Ask the user who the reader is and what the page is for.** Reader, goal and
   positioning are the user's call. Ask in one message, and offer concrete options
   to pick from based on what you know so far:
   - **Reader:** roles you can infer from the existing page or repo (e.g. "backend
     developer using framework X", "team lead evaluating tools", "existing user
     upgrading"). Include 2-3 options plus "other".
   - **Goal:** what the page must achieve: installs, signups, docs visits, demo
     requests, upgrade to paid. Pick the 2-3 most likely.
   - **Awareness:** does the reader know they have the problem / know solutions
     exist / know this product? This sets where the page starts.
   - **Scope:** one page or several (landing + tutorial, docs set, README only).

   Let the user pick, combine, or correct. Do not draft until they confirm. Mark
   your own guesses `[?]`. One brief per audience: two different readers means two
   briefs, not one blended page.
3. **Research the reader's real problems and words.** Search for published failures,
   surveys, practitioner reports and papers in the reader's area. Keep numbers and
   links. Collect the reader's own phrasing from issues, forums, discussions and support
   threads; headings use their words, not ours. Read competitors' docs, not their
   marketing, to learn what they actually do and where they stop. Date every external
   fact: competitors and numbers change.
4. **Map each problem to a verifiable fact.** For every claim, find what makes it true:
   code, data, a measurement, a policy. If nothing backs it, drop the claim or list it
   under "does not do".
5. **Write the brief** (template below) and hand it to the user to edit. Do not write
   anything until reader, moment and differentiation are confirmed.

### Write from the brief (steps 6-9)

6. **Propose what to write.** Based on the brief's goal (section 0), reader (section 1)
   and scope, propose specific deliverables. Offer options:
   - **Landing page** if goal is installs, signups, or awareness.
   - **Tutorial** ("get started in N minutes") if goal is first use.
   - **Integration guide** if reader uses a specific SDK or framework.
   - **README rewrite** if existing README is the main entry point.
   - **Reference docs** if reader needs API surface, not narrative.
   - **Several of the above** with suggested order (landing first, tutorial second, etc.).

   For a rewrite (entry A): show what changes compared to the existing text, section by
   section. Name what stays, what gets rewritten, and what gets removed.

   Let the user pick. Then for each deliverable: outline first, ordered by section 5
   (reader's priorities), one idea per section, a heading plus one line each. Get a
   nod, then write. Use the brief's dictionary;
   internal names stay in code blocks and reference docs. Split docs by Diataxis
   (tutorial, how-to, reference, explanation). A landing page links to a tutorial,
   not to the reference.
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

## 5. Priority for the reader
Rank what matters most to the reader, not what's most impressive technically.
1. ...
2. ...
3. ...
This order drives page structure: first section covers #1, last section covers the
lowest priority. Anything below the line goes to docs, not the page.

## 6. Evidence
Only measured results, each with a link to method and raw numbers. Then other proof if
real: named users, adoption, quotes with permission. List what may not be claimed
(unmeasured, demo-only, unsourced) and which measurement would close the biggest gap.

## 7. Objections
The reader's questions with short, factual answers (effort, cost, data needed,
comparison with the alternative).

## 8. In 30 seconds the reader understands
Three or four points. This is the test the naive reader must pass.

## 9. One action
The primary CTA and a second one. Prefer "run X" or "try X" over "star us".

## 10. Dictionary
| In code | On the page |
Internal names → the reader's words. Names that never appear on the page.

## 11. Out of scope
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
