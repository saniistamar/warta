# Install Warta

This page installs Warta into Goose. You will paste one prompt.

## Before you start

- Goose Desktop is installed. It is free, from goose-docs.ai. Search
  needs no API key; Goose asks you to sign in to an AI provider on
  first launch — pick the free sign-in option or paste an API key.
- git is installed. On macOS, run `xcode-select --install`. On Windows
  or Linux, use the installer from git-scm.com. If installing git is a
  blocker, use the no-git path in Troubleshooting below.
- uv is installed — Warta's search runs through it. One terminal line:
  macOS/Linux `curl -LsSf https://astral.sh/uv/install.sh | sh`, Windows
  `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`
  (from astral.sh/uv). Without uv, Warta falls back to Goose's built-in
  search.
- Make an empty folder for your Warta work — any name, anywhere you
  like. Warta, and every story you run with it, will live in this
  folder. Open it in Goose: File → Open Directory…, then start a new
  session there.

## The prompt

Copy this prompt, paste it into that Goose session, and send it:

```
Install Warta for me. First check if Warta is already installed here:
it is when both .goose/skills/warta/SKILL.md and
.goose/skills/warta/templates/run.yaml exist. If it is not, clone the
repository into the current folder with
git clone https://github.com/saniistamar/warta.git .
(the dot means this folder). If the clone fails, say so and stop — do
not clone anywhere else. One exception: if it failed because the
folder is not empty and holds only hidden desktop files (.DS_Store,
Thumbs.db), delete those and run the clone again. Once Warta is
installed, read .goose/skills/warta/SKILL.md, and from now on in this
session treat "run warta" as: follow that skill. Then tell me how to
start.
```

## After the prompt

Warta is in your folder, and this session already knows it. Say
`run warta` — or say `run warta about "jakarta sinking city"` to start
on a topic right away. Everything you make lands in this same folder.

## Troubleshooting

- The search check happens at stage 1. If Warta stops and says search
  is not configured, that's the integrity stop — see the README.
- Closed Goose mid-run: reopen Goose in this same folder and say
  "resume warta".
- Pasted the prompt twice: harmless. Goose sees Warta is already
  installed and continues — "run warta" works the same.
- Goose does not respond to "run warta" in the install session: start
  a new session in this folder (File → Open Directory…), then say
  "run warta". A fresh session loads Warta the standard way.
- Clone refused because the folder is not empty: the prompt already
  clears hidden desktop files on its own. If something else is in the
  folder, make a new empty folder, open it in Goose, and paste the
  prompt again.
- The clone failed and Goose stopped: fix what Goose named — the
  connection, or git — then paste the prompt again.
- An install was interrupted partway: a partial clone leaves hidden
  files behind, so the folder may look empty but is not — and a
  nearly-complete one can fool the already-installed check. Delete
  the whole folder, make a new empty folder, open it in Goose, and
  paste the prompt again.
- No git on this machine: on the repo page
  (github.com/saniistamar/warta) choose Code → Download ZIP, unzip
  it, open the folder it creates in Goose, and say "run warta".
