# Peckham, Ong, Nagy & Dunbar (2025) — Transcription normalization in the Faetar benchmark

**Full citation:** Peckham, Leo, Michael Ong, Naomi Nagy & Ewan Dunbar. 2025. Investigating Transcription Normalization in the Faetar ASR Benchmark. ⚠️ Venue to confirm — may be preprint only.
**Link:** arXiv:2508.11771
**Section:** C1
**Read in full:** ⚠️ **no — abstract and opening sections only.** Complete before committing.

## Summary
A follow-up to the Faetar benchmark testing whether the inconsistent transcriptions are what makes the task hard. Using a small hand-built lexicon, the answer is largely no: the inconsistencies are real but not the main obstacle.

## Problem
The benchmark drew repeated comments about the quality of its gold transcriptions — the implicit claim being that reported error rates were inflated by transcription noise rather than by recognition failure. This paper tests that claim directly.

The paper also separates two things that were being conflated: genuine inconsistency, where one pronunciation is written in different ways, and the ordinary consequence of transcribing phonetically rather than lexically or phonemically, where the same word pronounced differently is correctly written differently.

## Method / approach
<!-- Complete from the full paper — this is the section most in need of the
actual text, since the lexicon construction is the whole methodological move. -->

A small hand-constructed lexicon, used to normalize transcriptions and to constrain decoding. Comparison of bigram word-based language modelling against constrained decoding over a finite lexicon.

## Key findings
- Inconsistencies exist in the transcriptions but are **not the main challenge** of the task.
- Bigram word-based language modelling adds no benefit.
- Constraining decoding to a finite lexicon can be beneficial.
- The task remains extremely difficult.

Also issued as an erratum: one of the constrained-task baselines in the original benchmark was reported with a phone error rate that was too low, because the figure actually came from a different, unconstrained model. Corrected in the documentation and on the leaderboard.

## Strengths
It tests an objection to the authors' own benchmark and reports that the objection, which would have been convenient to accept, does not hold. The erratum is published rather than quietly fixed.

## Limitations
One language, one corpus. Whether "normalization is not the bottleneck" generalizes to varieties whose non-standardness has a different source is exactly what is not established.

The lexicon is hand-built and small, which bounds what the constrained-decoding result shows.

## Relevance to my project
<!-- TO WRITE. This is the one review where the honest reading works against
the framing of section C, and that is why it was read early. -->

The problem it creates, stated plainly:

- **This undercuts the default explanation.** If a high Nouchi WER gets attributed primarily to the absence of orthographic convention, this paper is the counterexample that has to be answered. Attributing error to transcription convention requires evidence from Nouchi data, not an analogy to a variety where the same claim was tested and did not hold.
- **But the disanalogy is arguable, and the argument has to be made explicitly.** Faetar's transcriptions are inconsistent because they were made phonetically by fieldworkers over time with no codified standard. Nouchi's would be inconsistent for that reason *plus* lexical volatility and morphological hybridization — the variety keeps generating forms. Whether that second source behaves like the first is an empirical question this paper cannot settle. Do not assume it does.
- **Constrained decoding over a finite lexicon is the concrete adoptable technique**, and it interacts badly with OOV in an interesting way: a finite lexicon is precisely what a variety with continuous lexical innovation resists. Testing where that breaks would be a real contribution rather than a replication. — bears on OOV, FUSED.
- **The bigram-LM null result sits against Ògúnrẹ̀mí et al., where trigram LMs produced the single largest gain.** Different languages, different task, different metric — but the two results should not both be cited approvingly without noticing they point in opposite directions.

Adopt / adapt / reject: <!-- decide -->

## Open questions / ideas
- How exactly was the lexicon built, and what would the Nouchi analogue cost in hours? If the answer is "a few days," this becomes a near-term experiment.
- If normalization is not the bottleneck in Faetar, what is? The answer determines whether section C of this reading list is aimed at the right problem.
- Is there any work measuring ASR error under orthographic variation for creoles or urban vernaculars specifically? Section C2 is currently empty and this is the gap to fill.
- Confirm whether this has an archival venue or remains a preprint.
