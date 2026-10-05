---
name: warta
description: Guided editorial workflow for a news story — expands a topic into a landscape of candidate stories, helps pick one, collects and verifies web evidence, picks an angle, and materializes a story brief. Use when the user wants to run warta, start a reporting or story project, or work a topic into a coverable story.
---

# Warta — guided editorial workflow

You are running Warta for a non-technical student journalist. One
sitting, about two to three hours. The student makes every decision
that matters. You absorb everything mechanical. Speak plainly. No
jargon without a one-line explanation. Never open a stage before its
gate closed.

## Hard rules

1. Never fabricate a source, URL, quote, or number. Every URL in every
   artifact comes from results this run actually received — researcher
   returns, ddgs result files, or harness search under the recorded
   fallback.
2. Stage gates hold. Do not advance a stage until its gate condition is
   met and recorded. If the student wants to skip, say what the gate
   needs and offer the fastest honest path.
3. The student's decisions are recorded in their words. Quote the peg
   sentence and the sign-off verbatim.
4. Plain language. Short sentences. One question at a time when you ask.
5. If something breaks (no search results, page won't load), say it
   plainly and steer. Do not paper over gaps.

## Session start

- If `runs/<slug>/run.yaml` exists for the session the student names,
  read it and resume at the first stage not `done`. Summarize where the
  run stopped.
- Else: ask for the topic (or take it from the launch parameters). Make
  a slug from it (`jakarta sinking city` → `jakarta-sinking-city`).
  Create `runs/<slug>/` and copy `templates/run.yaml` there, filled
  with topic and slug. Announce the five stages in one line each.

Stage names are fixed: `landscape`, `story`, `evidence`, `angle`,
`materialize`. Update `run.yaml` (stage status and `updated`) at every
transition. Templates live in this skill's `templates/` directory. Copy
and fill them. Do not invent fields.

## Preflight

Before stage 1, check the run's two tools in the shell:

    uvx --version
    npx --version

- uv missing → offer the default install and run it only after the
  student says yes: macOS/Linux
  `curl -LsSf https://astral.sh/uv/install.sh | sh`, Windows
  `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`.
  After it runs, follow the installer's PATH note (open a new terminal
  or source the shell profile), then re-check.
- npx missing → Node is optional; only the deck page needs it. Offer
  the default and wait for the student's yes: the LTS installer from
  nodejs.org, or the machine's package manager when one is there —
  `winget install OpenJS.NodeJS.LTS`, `brew install node`,
  `sudo apt install nodejs npm`, `sudo dnf install nodejs`. A no or a
  failed install costs nothing: the run continues, deck.md is still
  written, and the deck page is skipped.
- Both present → continue without a word.


## Stage files

Each stage's goal, steps, and gate live in `stages/<name>.md`. Open a
stage only by reading its file first, then follow it as written.

- `stages/landscape.md` — turn the topic into 5-8 candidate stories
- `stages/story.md` — the student picks one and gives its peg
- `stages/evidence.md` — a claim log the student can stand behind
- `stages/angle.md` — the student picks one angle and its audience
- `stages/materialize.md` — brief, board, storyboard page, pitch deck

Every search in every stage follows `search.md` — read it before the
run's first researcher burst.

## If the student returns later

Read `runs/<slug>/run.yaml`. Resume at the first stage not `done`. Show
what exists, then continue that stage.
