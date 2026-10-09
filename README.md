# positioning-brief

A Claude Code skill that writes a positioning brief before any text meant for
people: landing pages, product pages, docs, READMEs, guides, announcements, or
integration pages. The brief forces you to answer: who reads this, what problem
brought them here, what they use today, and what evidence you actually have. Text is
written from the brief.

## Why

Generated text describes the internals: code structure, technical details, how things
are built. It explains from the technical side, but readers think in value: what
problem it solves, what changes for them, why they should care. A brief catches this
gap before you write.

## Install

Copy `SKILL.md` to your Claude Code skills directory:

```sh
mkdir -p ~/.claude/skills/positioning-brief
cp SKILL.md ~/.claude/skills/positioning-brief/
```

Or clone and symlink:

```sh
git clone https://github.com/vadimchirkov/positioning-brief.git ~/positioning-brief
ln -s ~/positioning-brief ~/.claude/skills/positioning-brief
```

## When it triggers

The skill handles three entry points:

| You say | What happens |
|---|---|
| "Improve this page" / "rewrite these docs" | **Entry A.** Audits specific content you pointed at, builds a brief, proposes what to rewrite, merge, split, or drop |
| "Look at what docs we have" / "let's improve our texts" | **Entry B.** Finds all user-facing text in the project, lists what exists, proposes where to start. Then continues as A |
| "Write a landing page for X" / "I need docs for Y" | **Entry C.** No text exists yet. Skips audit, builds brief from the idea |
| "I have a brief, write the page" | **Entry D.** Validates existing brief, proposes deliverables, writes |

## How it works

### Brief phase (steps 1-5)

1. **Audit** existing text: flags internal names, unsourced numbers, demo output
   presented as results. Skipped when writing from scratch.
2. **Ask the reader questions** with concrete options to pick from: reader roles,
   page goals (installs, signups, docs visits), awareness level, scope. You pick
   or correct, not start from blank.
3. **Research** the reader's real problems: published failures, practitioner reports,
   competitor docs. Collects the reader's own words from issues and forums.
4. **Map** each claimed benefit to a verifiable fact. No fact, no claim.
5. **Write the brief** and hand it to you. No page until you confirm reader, moment,
   and differentiation.

### Write phase (steps 6-9)

6. **Propose deliverables** based on the brief. Offers options: landing page,
   tutorial, integration guide, README rewrite, reference docs, or a combination
   with suggested order. For rewrites, shows what changes section by section. You
   pick, then it outlines before writing.
7. **Check:** runs every quoted example, then a naive-reader test against the brief's
   "30 seconds" section.
8. **Recommend real-reader testing:** 2-3 matching people, 5 seconds each.
9. **Keep current:** brief and pages carry a date. Product changes go to the brief
   first, then pages.

## Brief sections

| # | Section | Purpose |
|---|---------|---------|
| 0 | Goal | What the page makes the reader do; how you know it worked |
| 1 | Reader | Role, knowledge, awareness stage, who it's not for |
| 2 | Moment | When they look for this, with sourced examples |
| 3 | What they use today | Each alternative from its own docs, where it stops |
| 4 | What we have | Category, main idea, problem-to-mechanism map, what it doesn't do |
| 5 | Evidence | Measured results only; what can't be claimed; biggest gap |
| 6 | Objections | Reader's questions with short factual answers |
| 7 | In 30 seconds | 3-4 points the naive reader must get right |
| 8 | One action | Primary CTA and a fallback |
| 9 | Dictionary | Internal names to reader's words |
| 10 | Out of scope | Goes to reference/explanation docs, not the page |

## Rules

- Evidence from real measurements only. Demo output is wiring, not a gain.
- Negative results stay off marketing pages. Honest limits ("does not do X") stay on.
- When evidence is thin, name the missing measurement and propose the run.
- Follow the project's writing rules when it has them.

## License

MIT
