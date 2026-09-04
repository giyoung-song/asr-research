# Research: Speech Recognition for Code-Mixed African Urban Vernaculars

Giyoung Song · [email / site — optional]

This repository collects my research on automatic speech recognition (ASR) for
African urban vernaculars such as **Nouchi** and **Camfranglais**, where
language mixing is a conventionalized norm rather than occasional
code-switching or borrowing (approaching what Auer terms a *fused lect*).

It has two parts:

## 📂 [`nouchi-asr/`](nouchi-asr/) — Project

A working research log: transcribing Nouchi speech, locating where ASR and
speech-translation systems fail, analyzing *linguistically* why word error
rate (WER) is high, and testing how those errors might be reduced. Includes
experiments (cascaded Whisper/MMS + NLLB vs. end-to-end SeamlessM4T) and a
linguistically grounded error taxonomy.

→ See [`nouchi-asr/README.md`](nouchi-asr/README.md) for details.

## 📂 [`reading/`](reading/) — Literature reviews

Structured reviews of the literature on low-resource, code-switched, and
fused-lect ASR, organized by theme. Each review is read through one lens: what
it contributes to recognizing densely mixed speech — and where it would break.

→ See [`reading/README.md`](reading/README.md) for the thematic index.

---

The two parts feed each other: methods surveyed in `reading/` are tested in
`nouchi-asr/`, and failures found in `nouchi-asr/` send me back to the
literature. Together they sit at the interface of sociolinguistic description
and computational speech modeling.
