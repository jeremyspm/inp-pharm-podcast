# BN2 Exam Podcast: INP and Pharm (unlisted, `noindex`: https://jeremyspm.github.io/inp-pharm-podcast/)

The two finals with no case booklet, as podcasts. HS2's podcast could read every question she wrote; INP and Pharm have
no such list, so each episode here is a **forecast**: the questions the lecturers pointed at, each answered in the shape
they asked for. Every track says out loud, and the player shows, why it is in. The questions are this podcast's, never
presented as the lecturers'.

| Episode | Tracks | What is in it |
|---|---|---|
| **INP Final — The forecast** (`#inp`) | 28 | Mon 2 Nov · 40 multi-choice + 15 short answers at 4 marks. 25 short-answer tracks, one per Exam Content theme (29 themes, grouped), Lisa's half then Janine's, each from their revision decks (Lisa's 102 slides, Janine's 111) and the 27 Oct session; answers built on Lisa's marking guide (her falls question, slide 101: 1 mark identify, 1 describe, 2 explain). Then two closed-question tracks: every key of the lecturers' 19 Canvas quizzes that no short-answer track says. Rapid-fire last. |
| **Pharm Final** (`#pharm`) | — | Next: Thu 5 Nov. |

## Where the INP forecast comes from

- **The Exam Content page** (8 Oct, 29 themes, one flat list): scope. Every theme has a track.
- **Lisa's revision session, 27 Oct** (transcribed in `pharm-final/transcripts/`): the topics the class voted for in her
  survey, her command words (identify, describe, explain, discuss, compare), "about 150 words", and two worked practice
  questions with her model answers (emotional intelligence, falls). She said the practice questions are made up, not in
  the exam; they are here as the shape.
- **Both revision decks** (`INP Sem 2 2026 - NotebookLM/1 Upload these to NotebookLM/01 Revision - what the lecturers said
  is on the exam.md`). Janine's was never talked through in a recorded session.
- **The lecturers' quiz keys** (`inp-final/bank`): the multi-choice tracks.

Not used for ranking: nothing. Lisa sets no practice short answers and the quizzes are flat, so no theme outranks another
on evidence; the order is the course's, Lisa's half then Janine's.

## Build

Ported from [hs2-podcast](https://github.com/jeremyspm/hs2-podcast)'s `podcast.py` on 31 Oct 2026: the same voices
(af_heart, the examiner am_puck), paragraph cache, subtitles, videos, script PDFs, download zips and feeds. Its README
explains all of that. What changed:

- The player's question and answer lines come from the script (`@ ask: Question (N marks) || line | line`), not a Paper
  Sim's bank, so there is no coverage gate. Instead the **forecast gate**: every track has an `@ why:` (who pointed at it,
  where; the player shows it under "Why this is in the forecast") and every track but the intro an `@ ask:`.
- `@ scen:` shows a scenario above the questions (for Pharm's clinical scenarios).
- `SAY_AS_WORD` gains ISBAR, SOAP, TIME, SMART, OLD, CARTS, ECHO, PHARMAC; `IPA` gains the te reo Māori of the Te Tiriti,
  pou and Health Strategy tracks (espeak said "tee" for te and "pee" for pae) and a few clinical words.
- Work files in `D:/hs2-audio/exam-podcast` (cache, zips, videos); the model is shared with hs2-podcast.

    python podcast.py inp --dry      # words, minutes, every gate
    python podcast.py inp --audit    # every long word with its phonemes (read it after any script edit)
    python podcast.py inp --no-build # voice (run two or three at once)
    python podcast.py --build        # MP3s, index.html, episodes.json, feeds, zips
    python podcast.py --release      # upload the zips to the "downloads" release
