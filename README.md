# Warta

Warta is a guided editorial workflow for a news story, run in the Goose
desktop app. You bring a topic. It walks you through five stages —
landscape, story pick, evidence, angle pick, materialization. You make
every decision that matters. You finish with a story brief a writer can
pick up cold. One sitting, 2-3 hours.

## Status

v0.1.

## Quick start

1. Install Goose Desktop — free, from goose-docs.ai. Search needs no
   API key; Goose asks you to sign in to an AI provider on first
   launch — pick the free sign-in option or paste an API key.
2. Make an empty folder and open it in Goose.
3. Paste the prompt from [INSTALL.md](./INSTALL.md).
4. Say "run warta".

## Requirements

- Goose Desktop.
- git (or the no-git ZIP path in [INSTALL.md](./INSTALL.md)).
- Optional: better search via a Tavily or Exa MCP — see the MCP guides
  on goose-docs.ai.

## Docs

- [START-HERE.md](./START-HERE.md) — what a Warta sitting is and what
  you decide.
- [INSTALL.md](./INSTALL.md) — the paste-prompt that sets Warta up in
  Goose.
- [Course runbook](./docs/course-runbook.md) — for instructors:
  provisioning, distribution, and coaching a sitting.
- [Glossary](./docs/glossary.md) — Warta's vocabulary.

## Resuming

Reopen Goose in the folder where you ran Warta and say "resume
warta". It picks up where you stopped.

## License

MIT — see [LICENSE](./LICENSE).

## Troubleshooting

- Warta stops at stage 1 and says search is not configured: search
  isn't set up. Warta refuses to invent sources — that's a feature.
  Set up search — a Tavily or Exa MCP, see the MCP guides on
  goose-docs.ai — then say "resume warta".
- Session died: reopen Goose in the same folder and say "resume warta".
- No git on the machine: on the repo page choose Code → Download ZIP,
  unzip it, open the folder it creates in Goose, and say "run warta".
- Storyboard page seems blank or won't open: `storyboard.html`
  renders offline in any browser; if it shows an error, the board was
  not filled — say "resume warta".
