# StudyLab | Group 6 • PSYC 402

A static GitHub Pages experiment about learning preferences and immediate cued recall. Revised November 2026 from the original StudyLab app. This project is the last activity in Chain B (Teams 4 → 5 → 6 → Qualtrics).

## Deploy / replace files

Extract the ZIP and replace **index.html, styles.css, script.js, README.md** at the root of your existing StudyLab repository. Commit to `main` (suggested message: `Add per-round recall, fuzzy scoring, DataPipe and credit redirect`). GitHub Pages should already be enabled on that repository. No build step or server. Do not upload this ZIP or participant CSVs to the public repository. Do not create a second StudyLab site if Group 5 already has your live URL.

## Chain configuration (provided by the instructor)

- Team 6; Chain B; LAST activity.
- DataPipe experiment ID: `ajMubu8R0J6J` (not a secret).
- DataPipe POST: `https://pipe.jspsych.org/api/data/`.
- Instructor destination folder: `Team6_402_Fall2026`.
- Credit survey: `https://stlawu.qualtrics.com/jfe/form/SV_dhuzwAkMKUaZetM`.
- Team 5 must send participants to **your actual public GitHub Pages URL**, preserving `sid` and `chain=B`. Example: `https://YOUR-USERNAME.github.io/YOUR-REPO/?sid=EXAMPLE123&chain=B` (example only). IDs are expected to contain letters, numbers, hyphens or underscores, 1–128 characters.
- Missing or wrong-chain IDs block the task. Team 6 never creates a replacement ID. A valid ID is a linkage value, not proof of prior completion: the instructor verifies DataPipe records for all three teams.
- The final evaluation submission automatically saves the summary and trials CSVs. Successful 201/202 responses and a 400 `FILE_EXISTS` response are accepted under the instructor's retry rules; no redirect occurs until both files have been accepted. Failed requests show a retry option and backup download buttons. Retries use identical frozen data and filenames. Complete the survey only after the app saves successfully.
- Final redirect: `https://stlawu.qualtrics.com/jfe/form/SV_dhuzwAkMKUaZetM?sid=EXAMPLE123&chain=B&source_team=6` (example only).

## Experiment design

**Question:** Does presentation format (written words, pictures alone, spoken words) influence immediate cued recall of concrete object pairs? Does the predicted best format correspond to the observed best format?

Within-person design: 3 randomized study modalities, 6 pairs per modality, 18 total. The three original stimulus lists are randomly assigned to the three formats independently of block order. Items are randomized within each block, and recall order is randomized within the same block. Two stimulus labels were updated to match their existing pictograms (river → wave, snow → snowflake) in all modalities. All other pair content remains unchanged.

Each round: instructions → six pairs (6 seconds each; audio starts when Play is tapped) → 30-second subtraction-by-three distractor with a new randomly drawn 3-digit starting value → six written-cue recall questions. There is no answer feedback until all three rounds are complete. The picture condition shows only paired pictograms during study. At recall, the written cue and typed response are the same across modalities. Audio uses browser speech synthesis and falls back to text if an error is detected; check the flagged audio trials and participant audio difficulty rating. The final score chart includes overall and modality-specific scores, ties, preference comparison, an item review and a scientific interpretation. Optional app evaluation (clarity, ease, engagement, audio difficulty) is included in the summary. The final evaluation submission automatically starts saving and then redirects.

### Scoring

Case-insensitive, punctuation-insensitive normalized restricted Damerau–Levenshtein (optimal string alignment) similarity: `1 − editDistance / max(responseLength, targetLength)`. Insertions, deletions, substitutions, and adjacent transpositions cost one edit. Blank responses score zero. Similarity >= 0.75 is correct (inclusive). For example, `APPLE` = 100%, `aple` = 80%, `moom` vs `moon` = 75%. It is a spelling similarity heuristic, not a semantic or synonym test. Short words have stricter absolute tolerance and unrelated similar-looking words can be accepted. Review exact vs fuzzy matches when analyzing the data. Pictograms may have multiple plausible names; consider pilot-testing their legibility (do not change scoring or stimuli mid-collection without instructor approval).

### Scientific interpretation

Pictures of concrete objects are often remembered better than written labels (picture superiority). Proposed explanations include visual and verbal coding, visual distinctiveness, and richer sensory or semantic processing. We use this as a tentative prediction, not a universal hierarchy or an established norm for this particular pair-association task. Preferences for presentation modality are real, but matching teaching to a purported fixed learning style lacks convincing empirical support. Written recall cues may favor verbal encoding, the picture-only condition requires naming, audio exposure duration/quality varies, and short six-item lists yield noisy scores. Randomization reduces systematic order/list effects, but does not eliminate carryover, item difficulty, or measurement noise. This is not a learning-style diagnostic or long-term retention test. Do not report a real class average until actual data are collected.

Sources:
- Nelson, D. L., Reed, V. S., & Walling, J. R. (1976). Pictorial superiority effect. *Journal of Experimental Psychology: Human Learning and Memory, 2*(5), 523–528. https://pubmed.ncbi.nlm.nih.gov/1003125/
- Pashler, H., McDaniel, M., Rohrer, D., & Bjork, R. (2008). Learning styles: Concepts and evidence. *Psychological Science in the Public Interest, 9*(3), 105–119. https://pubmed.ncbi.nlm.nih.gov/26162104/
- Dunlosky, J., Rawson, K. A., Marsh, E. J., Nathan, M. J., & Willingham, D. T. (2013). Improving students’ learning with effective learning techniques. *Psychological Science in the Public Interest, 14*(1), 4–58. https://doi.org/10.1177/1529100612453266

## Data output / privacy

- `summary_<sid>.csv`: one participant row, session identifiers, timestamps, preference, randomization, accuracy by format, total score, totals and condition-specific distractor performance, audio flags, optional evaluation, version and scoring rule.
- `trials_<sid>.csv`: 18 rows, one per recall item; identifiers, condition, list/order fields, cue and target, blank indicator, exact-match flag, normalized spelling similarity, binary score, response time, preference, and trial-level audio fallback flag.
- Typed recall strings are used locally for scoring and review but are **not uploaded** (or included in the backup CSVs), minimizing risk of accidental personal information. No names, emails, or credit details are collected here. Evaluation ratings are saved in the summary, so no separate evaluation CSV is necessary. The instructor-controlled DataPipe storage is separate from Qualtrics credit records. The same sid links them for instructor verification. Do not publish individual data in the GitHub repository.

## Required testing before recruiting students

1. Verify your actual live GitHub Pages URL opens a blocked screen when no `sid` is present and also when `chain=A` is used. Confirm Team 5 has the exact public URL of Team 6.
2. Coordinate with Dr. Onyper before using a unique test ID (e.g., `?sid=TEST-G6-20261118-01&chain=B`). This is a real DataPipe integration, so clicking the final submit on your live site uploads test CSVs. Do not reuse someone else's ID. Mark tests clearly and notify your instructor; don't delete or modify stored data yourself.
3. Confirm the study rounds contain six pairs each; pictures are unlabeled; sound works, and the timer advances; complete all three subtraction phases and six recall questions after each. Use capitalized, near-miss and clearly incorrect answers to check results. Check mobile/desktop and audio quality.
4. Read the final score chart and interpretation, choose optional ratings, then click **Submit & continue to course credit**. Verify automatic upload occurs before navigation; ask the instructor to confirm both files arrived. Check one summary row and 18 trial rows, matching `session_id`, `team_id=6`, `chain_id=B`.
5. Verify final Qualtrics URL includes the same sid, `chain=B`, `source_team=6`; do not submit a fake credit claim. Confirm instructor's Qualtrics embedded data settings capture these parameters.
6. Check the save-failure behavior (e.g., disconnect before submitting a coordinated test, reconnect and retry). The app must not navigate on failure. Confirm backup CSV downloads and retry behavior. Test the full chain with the instructor and other teams as requested, and retest on another device/browser.

**Verification performed during development:** JavaScript syntax passes; simulated DOM, timer, and mocked HTTP tests passed for all three task rounds, 18 recalls, 75% scoring, two CSV exports, missing/wrong chain blocking, failed upload, identical-data retry, 201/202/FILE_EXISTS handling and final redirect construction. Real browser navigation was restricted in the development environment. No real DataPipe POST or real Qualtrics submission was made. Live hosting, voice playback, delivery to instructor storage and end-to-end chain require group verification.

## Suggested analysis

Compute mean number correct out of six for each format; plot within-person scores or condition means with uncertainty. Compare preferred/predicted format vs highest-scoring format, reporting ties separately; a preference-by-modality interaction would be necessary for a stronger test of learning-style matching. Summarize ease, clarity and engagement ratings, and report audio-fallback exclusions/sensitivity analysis. Report that each participant studied different lists in different orders. Treat small-sample results as exploratory. Use only actual collected, anonymous data.
