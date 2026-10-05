# Course runbook — running Warta in a class

> How an instructor provisions, distributes, and coaches Warta for one
> course sitting. Follow it top to bottom before the first class.

## 1. What you are running

Warta is a guided editorial workflow that runs inside the Goose desktop
harness. Students give it a topic. It walks them through five stages —
landscape, story pick, evidence, angle pick, materialization — and leaves
a story brief backed by a claim log. One sitting, about 2-3 hours.

- **The skill carries the method:** `.goose/skills/warta/SKILL.md`.
- **The recipe is for CLI users:** `.goose/recipes/warta.yaml` — the
  Goose CLI loads it automatically; the Desktop app runs the skill
  directly.
- **Students decide; the agent absorbs the mechanical work.**

## 2. Install Goose

- Students need the Goose desktop app on their own laptops. Download
  from goose-docs.ai. The app is free. No API key is needed for search.
- Tested with Goose **1.53.0**. The desktop binary refuses to run headless —
  use a display, or use the CLI.
- Docs live at goose-docs.ai. The source repository is
  github.com/aaif-goose/goose.

## 3. Check search

Goose ships a built-in `web-search` skill, enabled by default
(DuckDuckGo). Verify before class: run Goose in the repo folder and
ask it to search anything. A result list means search works.

Warta fires its searches through researcher subagents. In the same
probe, check the `delegate` tool answers (Summon extension, standard
since Goose 1.25). When it is absent, Warta searches inline, tells the
student, and records `search: inline` in run.yaml.

- To upgrade source quality, configure a search MCP: Tavily (needs
  `TAVILY_API_KEY`, quick-install deeplink in the docs) or Exa. Both are
  documented on goose-docs.ai under MCP guides.
- Without a working search tool, Warta stops at stage 1 on purpose. It
  never invents sources. Treat that stop as a provisioning signal, not a
  failure.

## 4. Distribute

Students install from the public repository. Send them the repo's
INSTALL.md (or its URL). Each student makes an empty folder, opens it
in Goose, and pastes the prompt from that page. Goose clones the
repository into that folder and the same session is ready — they say
"run warta" without leaving it.

For machines without git: on the repository page choose Code →
Download ZIP, unzip it, open the folder it creates in Goose, and say
"run warta".

## 5. Run the session

Coach the sitting on the clock:

| Minutes | Stage | The student decides |
| --- | --- | --- |
| 0-20 | Landscape | topic, steering |
| 20-35 | Story pick | one story, the peg in their words |
| 35-95 | Evidence | best-source calls, flagged-claim dispositions |
| 95-115 | Angle pick | one angle, the audience |
| 115-130 | Materialize | medium (if unset), sign-off |

- The gates hold until the student decides. If a student feels stuck,
  the move is steering, not skipping.
- A session that dies mid-run resumes: reopen Goose in the same folder
  and say "resume warta". The skill reads `runs/<slug>/run.yaml`.

## 6. Method sources

The workflow adopts named newsroom practice. Key sources:

- Poynter, "3 guidelines for a good story pitch":
  www.poynter.org/educators-students/2016/3-guidelines-for-a-good-story-pitch
- Poynter, "What makes a good pitch? NPR editors weigh in":
  www.poynter.org/educators-students/2017/what-makes-a-good-pitch-npr-editors-weigh-in
- The Open Notebook, "Why Now? Find a Hook to Make Your Pitch Timely":
  theopennotebook.com/2026/02/24/why-now-find-a-hook-to-make-your-pitch-timely/
- Verification Handbook (EJC): verificationhandbook.com/
- Mike Caulfield, "SIFT: The Four Moves":
  hapgood.us/2019/06/19/sift-the-four-moves/
- First Draft (archived — the site is frozen, hosted by the Internet
  Archive), "Verifying online information":
  firstdraftnews.org/long-form-article/verifying-online-information/
- Princeton Library, triangulation:
  libguides.princeton.edu/medialiteracy/triangulation
- SAGE, Key Concepts in Journalism Studies, "News Angle":
  sk.sagepub.com/dict/mono/key-concepts-in-journalism-studies/chpt/news-angle
- Media Helping Media, "Lesson: How to develop news angles":
  mediahelpingmedia.org/lessons/lesson-news-angles/
- GIJN, "From Relationships to Ranking":
  gijn.org/stories/from-relationships-to-ranking-angles-for-your-next-data-story/
- GIJN, beat reporting tips:
  gijn.org/stories/tips-for-beat-reporters-to-investigate-on-the-side/
- Idaho Pressbooks, news judgment:
  idaho.pressbooks.pub/introductiontojournalismandnewswriting/
- SHSMD story brief template: shsmd.org/tools/story-brief-template
- NPR Training, "A blueprint for planning storytelling projects":
  npr.org/sections/npr-training/2025/05/30/g-s1-65812/a-blueprint-for-planning-storytelling-projects
- StudioBinder, shot list vs storyboard:
  studiobinder.com/blog/shot-list-vs-storyboard/
