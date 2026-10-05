# Stage 5 — materialize

1. Ask for the medium — text, audio, or visual/video — unless the
   launch parameters set it. Write it to `run.yaml` (`medium`) when
   decided.
2. Write `runs/<slug>/brief.md` from the template. Fill every slot:
   title, topic, angle, audience, why-now, format + target length,
   evidence[] (claim_id, claim, url), key_sources[], visual_ideas[],
   open_questions[], sign_off (ask for the student's go-ahead and
   record it verbatim — rule 3).
3. If the medium is visual or video, also write `runs/<slug>/board.md`
   as a shot grid (shot_no, scene, shot_size, angle, movement,
   description, audio_note). If text or audio, write it as a beat
   sheet (ordered named beats, per-beat intent). Delete the unused
   section.
4. Copy `templates/storyboard.html` to `runs/<slug>/storyboard.html`
   and fill its `storyboard-data` island from board.md: the view
   (`shotgrid` for visual/video, `beatsheet` otherwise), the title,
   the medium, and one island row per board row. board.md stays the
   source of truth; the page is a derived view. Try to open it with
   the system viewer; when that fails, name the path.
5. Copy `templates/deck.md` to `runs/<slug>/deck.md` and fill it from
   brief.md — one slide per section, no content the brief does not
   carry. Then render the deck page:

       npx -y @marp-team/marp-cli runs/<slug>/deck.md -o runs/<slug>/deck.html

   brief.md stays the source of truth; the deck is a derived view. If
   the shell cannot run `npx` (Node missing), keep deck.md, tell the
   student the deck page needs Node (nodejs.org), and name the deck.md
   path. Try to open deck.html with the system viewer; when that
   fails, name the path.
6. Run the checklist aloud, one item per line:
   - every brief slot filled?
   - every evidence[] claim_id resolves to a claim-log row?
   - every URL from results this run actually received?
   - flagged claims all dispositioned?
   - sign-off recorded in the student's words?
   - every deck slide carries only what the brief carries?

Tell the student what they hold: a story brief (and board) that a writer
or a drafting agent can pick up cold, a storyboard page, and a pitch
deck. Point at the files.
