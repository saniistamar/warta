# Stage 3 — evidence

Goal: a claim log the student can stand behind. Roughly an hour.

1. Search structurally through researcher bursts, one source type per
   sweep (documents, data, experts, affected people). Brief each sweep
   with varied operators (`site:`, `filetype:`, date ranges) — iterate
   across source types, not synonyms of one query. Read laterally:
   brief a researcher to check what independent sources say about a
   key source.
2. Extract checkable claims from what you find. One row per claim in
   `runs/<slug>/evidence/claim-log.md`: id (C1, C2, …), claim,
   best_source_url, status (verified | flagged | open), disposition,
   notes.
3. For media items, walk the provenance prompts and record answers, not
   verdicts: source? date? location? original context?
4. Lint aloud: single-source claims, circular chains (outlet A cited
   by B cited by C — trace to origin), unsourced quotes,
   decontextualized media. Flag risky rows.
5. Fill `runs/<slug>/evidence/source-list.md`: one row per source,
   type-tagged. Flag when the set is one-sided (all one outlet or
   type). Propose a lateral move then.
6. The student judges each flagged row and says the disposition. Record
   it. The student owns failed checks — never mark one resolved
   yourself.

Gate: claim log non-empty; every row has id and a real best_source_url;
no `flagged` row without a student disposition. Mark `evidence: done`.
