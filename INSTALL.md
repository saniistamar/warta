# Install Warta

This page installs Warta into Goose. You will paste one prompt.

## Before you start

- Goose Desktop is installed. It is free, from goose-docs.ai. Search
  needs no API key; Goose asks you to sign in to an AI provider on
  first launch — pick the free sign-in option or paste an API key.
- git is installed. On macOS, run `xcode-select --install`. On Windows
  or Linux, use the installer from git-scm.com. If installing git is a
  blocker, use the no-git path in Troubleshooting below.

## The prompt

Open a new Goose session. Copy this prompt, paste it in, and send it:

```
Install Warta for me: clone the repository
https://github.com/saniistamar/warta.git into the folder ~/warta
(create it if needed). If ~/warta already exists from an earlier
attempt, use it as it is — do not clone again. After cloning, check
that the file .goose/skills/warta/SKILL.md exists, then tell me the
next step to start working in that folder.
```

## After the prompt

Open the `warta` folder in Goose: start a new session in that folder,
or use File → Open Directory…. You can also click the folder name at
the bottom of the Goose chat and pick the `warta` folder. Then say `run warta` — or say
`run warta about "jakarta sinking city"` to start on a topic right
away.

## Troubleshooting

- The search check happens at stage 1. If Warta stops and says search
  is not configured, that's the integrity stop — see the README.
- Closed Goose mid-run: reopen it in the same folder and say
  "resume warta".
- Pasted the prompt twice, or `~/warta` already exists: tell Goose
  "Warta is already cloned at ~/warta, continue from there".
- No git on this machine: on the repo page
  (github.com/saniistamar/warta) choose Code → Download ZIP, unzip it,
  open the folder in Goose, and say "run warta".
- The file check fails after an interrupted clone: delete or rename
  the `~/warta` folder, then paste the install prompt again.
