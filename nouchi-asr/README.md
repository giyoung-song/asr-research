repo1_nouchi-asr-error-analysis_README
Nouchi ASR Error Analysis
Diagnosing where and why automatic speech recognition and speech
translation break down on Nouchi — an Ivorian urban vernacular in which
language mixing is a conventionalized norm rather than occasional
code-switching or borrowing.
This repository is a working research log, not a finished system. It documents
transcription, error localization, linguistic analysis of high word error rate
(WER), and proposed corrections.
Motivation
Mainstream ASR and speech-translation systems assume (near-)monolingual or
cleanly switched input. Nouchi violates that assumption: French, Ivorian
languages, and coined forms are fused within single utterances. This project
asks what happens to current systems under those conditions — and what the
failures reveal about the variety's linguistic structure.
Research questions
Where in densely code-mixed Nouchi speech do ASR / speech-translation
systems fail most (measured by WER and aligned error positions)?
Are those failures linguistically patterned — concentrated at borrowing,
switch points, fused-lect morphology, or tone-bearing items?
Can linguistically-informed interventions (lexicon, tokenization, targeted
fine-tuning) reduce error at those points?
Pipeline
Cascaded: Whisper / Meta MMS (ASR) → NLLB (MT)
End-to-end: SeamlessM4T
Scoring: WER / CER with position-aligned error extraction
Analysis: each error site tagged with a linguistic category (below)
Error taxonomy (linguistically grounded)
Tag
Description
BORR
Lexical borrowing integrated into the matrix
SWITCH
Inter-/intra-clausal switch point
FUSED
Fused-lect morphology (mixing at the sub-word level)
TONE
Tone-bearing distinction lost or confused
PHON
Phonological reduction / non-standard realization
OOV
Out-of-vocabulary coined form
Repository structure
.
├── README.md
├── data/              # NOT committed — see Data & ethics
├── transcripts/       # gold transcriptions (de-identified)
├── experiments/       # scripts + configs for each model run
├── error-analysis/    # aligned errors tagged by taxonomy above
├── notes/             # running linguistic observations
└── results/           # WER tables, per-category breakdowns
​
Data & ethics
Raw audio from real speakers is not committed to this repository
(privacy, consent, and licensing). Only de-identified transcripts and
aggregate results are shared here. [Describe your collection/consent setup.]
Status
Pilot in progress ([month/year] – present). [Update with a one-line current
status as you go — this is the commit history reviewers will read.]
Related
Companion reading repository: [link to Repo 2] — literature on low-resource,
code-switched, and fused-lect ASR that informs the interventions tested here.
