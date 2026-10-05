# Search

The default search tool is `ddgs`, run through `uv`. Run it in the
shell, then read the JSON file it writes — `text` rows carry `title`,
`href`, `body`; `news` rows carry `title`, `url`, `source`, `date`:

    uvx ddgs text -q "<query>" -m 10 -o runs/<slug>/search/<label>.json
    uvx ddgs news -q "<query>" -m 10 -t d -o runs/<slug>/search/<label>.json

`text` sweeps web pages, `news` sweeps news. `-m` caps results;
`-t d|w|m|y` limits by time (day, week, month, year) — use it where a
burst asks for a date range. `site:` and `filetype:` operators go
inside the query string. Record `search: ddgs` in run.yaml the first
time it works.

If the shell cannot run `uvx ddgs` (uv missing, network failure), fall
back to the harness's built-in web-search, tell the student, and record
`search: goose` in run.yaml. If no search tool works at all, the
integrity stop at stage 1 holds. The fallback is recorded, never
silent.

## Researcher bursts

Search runs in researcher subagents. You keep the dialogue, the gates,
claim extraction, and every artifact. A researcher gets one bounded
question and returns distilled rows. Fire them with the `delegate`
tool.

Every burst gets:

- one bounded question: the source types to sweep and the run's topic
- distilled rows back: one line per find, each with its URL
- never fabricate — a URL appears only if the researcher saw it
- "nothing found" is a valid return; report failure plainly

Stage 1 fires three to four bursts in parallel — news; data and
reports; local voices; recent events — and collects every return
before the landscape table. Stage 3 sweeps one source type at a time,
in sequence, and reads laterally on key sources.

If the `delegate` tool is absent, search inline with the tools above,
say so to the student.
