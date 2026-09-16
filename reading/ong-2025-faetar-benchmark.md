# Ong et al. (2025) — The Faetar Speech Recognition Benchmark

**Full citation:** Ong, Michael et al. 2025. The Faetar Speech Recognition Benchmark. *Interspeech 2025.* ⚠️ Full author list to confirm from the ISCA record.
**Link:** ISCA Archive `interspeech_2025/ong25_interspeech` · arXiv:2409.08103 · leaderboard `perceptimatic.github.io/faetarspeech/`
**Section:** C1
**Read in full:** ⚠️ **no — abstract, introduction and partial text only.** Complete before committing this review.

⚠️ **Title differs between versions.** arXiv v2 is titled "The Faetar Benchmark: Speech Recognition in a Very Under-Resourced Language." Cite the Interspeech form.

## Summary
An ASR benchmark built from field recordings of Faetar, a Franco-Provençal variety of Italy, deliberately designed around the worst case rather than the average: noisy audio, about five hours transcribed, and no standard orthography, so that the transcriptions are internally inconsistent.

## Problem
Demonstrations of pre-training and cross-language transfer for low-resource ASR are usually broad evaluations aggregated across many languages at once, which hides enormous variation between them. The benchmark exists to make one hard case visible instead of averaging it away.

## Method / approach
<!-- Complete from the full paper. What is here is partial. -->

Corpus: field recordings from Faetar speakers in Celle di San Vito and a heritage community in Toronto. Roughly 5 hours with matching transcriptions, plus about 20 hours unlabelled. Source transcriptions came from ELAN files and from Word documents in legacy phonetic fonts, remapped to UTF-8. Utterance segmentation and alignment via an adapted JHU Arabic MGB-3 Kaldi recipe with a monophone speaker-independent GMM-HMM seed system, then PyAnnote 3.0 for boundary adjustment and diarization, then manual filtering.

Evaluation is by **phone error rate**, not word error rate. Baselines are multilingual speech foundation models; the best result comes from continuing pre-training on the unlabelled portion.

## Key findings
- Best baseline phone error rate 30.5%, via continued pre-training of a foundation model on the unlabelled set — the unlabelled portion carries real value.
- The transcriptions are "dirty" in two distinct senses, which the follow-up paper separates: genuine inconsistency (one pronunciation written more than one way), and the consequence of transcribing at a phonetic rather than lexical or phonemic level (one word pronounced differently is written differently). These are not the same problem and should not be conflated.
- The authors name the absence of a standardized orthography as perhaps the single most significant source of difficulty in the task.

## Strengths
It refuses the convenient move. Most low-resource benchmarks are assembled from the best available data; this one is assembled from what actually exists in an archive, and reports the resulting number without softening it. The unlabelled subset is a design decision that matches the real situation of most fieldwork collections.

## Limitations
**The one that matters here:** the authors filtered out utterances in Italian and English, noting that code-switching is common in Faetar speech but that removing substantially mixed utterances cost little data. They then treat "transcribing Faetar with minimal code-switching" as a reasonable approximation of the real task.

That is a defensible choice for Faetar and an impossible one for Nouchi. It means the benchmark isolates the orthography problem *from* the mixing problem.

Also: Faetar is a heritage and homeland variety of a Romance minority language, not an urban vernacular with an ideological stance toward the standard. The absence of an orthography has a different cause — no codification effort — than in Nouchi, where non-standardness is partly constitutive of what the variety is for.

## Relevance to my project
<!-- TO WRITE. -->

The open questions this raises for the Nouchi setup:

- **Phone error rate instead of word error rate.** Is that choice forced by the absence of an orthography, and does the same reasoning force it here? A PER sidesteps the question of what counts as a word — which, for a variety built on truncation and hybridization, is not a minor convenience. But it also discards exactly the lexical-level phenomena the linguistic argument is about. Decide whether to report PER, WER, or both, and say why. — bears on FUSED, OOV.
- **Continued pre-training on unlabelled audio.** The clearest adoptable method here: unlabelled Nouchi audio is far easier to obtain than transcribed Nouchi audio. Worth testing regardless of the rest.
- **The filtering move as a stated non-option.** This is the cleanest way to state what is distinctive about the Nouchi task. Faetar's authors could remove the mixing and keep the object; here, removing the mixing removes the object. That sentence belongs in the project's framing.

Adopt / adapt / reject: <!-- decide -->

## Open questions / ideas
- Full author list and exact pagination from the ISCA record.
- How did they define the phone inventory for scoring, given that (per the follow-up) the phoneme inventory of Faetar is itself still under discussion? Any answer here is directly reusable.
- What would a Nouchi equivalent of the unlabelled 20-hour subset look like, and where would it come from?
- Read alongside Peckham et al. (2025), which revises the assumption that transcription inconsistency is the dominant difficulty.
