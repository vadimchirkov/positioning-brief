# positioning-brief

A Claude Code skill that writes a positioning brief before any landing page, docs
page, or README. The brief forces you to answer: who reads this, what problem brought
them here, what they use today, and what evidence you actually have. Pages and docs
are written from the brief, not from the code.

## Why

Text generated from code describes the code. It uses internal names, quotes demo
output as results, and explains things the reader already knows while skipping what
they don't. A brief catches this before you write.

## Install

Copy `SKILL.md` to your Claude Code skills directory:

```sh
mkdir -p ~/.claude/skills/positioning-brief
cp SKILL.md ~/.claude/skills/positioning-brief/
```

Or clone and symlink:

```sh
git clone <repo-url> ~/positioning-brief
ln -s ~/positioning-brief ~/.claude/skills/positioning-brief
```

## What it does

1. Reads existing page, flags internal names and unsourced numbers.
2. Asks who the reader is, what the page should achieve, and offers concrete
   options based on what it found. You pick or correct.
3. Researches the reader's real problems: published failures, practitioner reports,
   competitor docs. Collects the reader's own words from issues and forums.
4. Maps each claimed benefit to code that backs it. No code, no claim.
5. Writes a brief (template in `SKILL.md`) and hands it to you. No page until you
   confirm reader, moment, and differentiation.
6. Writes from the brief: outline first, then copy. Internal names stay in code
   blocks and reference docs. Docs split by Diataxis. Landing page links to
   tutorial, not reference.
7. Checks: runs every quoted example, then a naive-reader test against the brief's
   "30 seconds" section.
8. Recommends testing with 2-3 real readers for 5 seconds each.
9. Keeps the brief dated. Product or competitors change: update brief first, then pages.

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
