# Reading: Low-Resource, Code-Switched & Fused-Lect ASR

Structured reviews of the literature on building ASR for languages where
mixing is frequent and annotated resources are scarce. Each review is read
through one lens: *what does this contribute to recognizing densely
code-mixed, fused-lect speech such as Nouchi and Camfranglais — and where
would it break?*

Reviews are organized by theme, not chronologically. The organization is
itself an argument about how the problem space decomposes.

---

## Themes

### 1. Code-switching, language mixing & fused lects (theory)
The linguistic foundation: the distinction between switching, borrowing, and
conventionalized mixing, and where varieties like Nouchi sit on Auer's
continuum (code-switching → language mixing → fused lect).
- [ ] [author-year — short title](reviews/...)

### 2. Low-resource ASR
Methods for training/adapting speech recognition with little labeled data:
multilingual pretraining, adapters, data augmentation, self-supervision.
- [ ] [author-year — short title](reviews/...)

### 3. Code-switched speech recognition
Systems and evaluation targeting intra-utterance mixing directly.
- [ ] [author-year — short title](reviews/...)

### 4. African-language NLP & speech
Resources, benchmarks, and models for African languages, including
francophone/anglophone urban vernaculars.
- [ ] [author-year — short title](reviews/...)

### 5. Tone & ASR
How tonal information affects recognition, and what its loss predicts about
error — the bridge from my MA work on tonal features.
- [ ] [author-year — short title](reviews/...)

---

## Review format

Every review follows [`TEMPLATE.md`](TEMPLATE.md): bibliographic info →
problem → method → findings → **relevance to my project** → open questions.
The "relevance" section is the point of this repository; the rest is summary.

## Starting reading list

A curated ~10 to read deeply rather than a long shallow list. **Verify every
citation's exact details before committing it** — these are pointers, not
confirmed bibliography.

- Auer (1999) — *From codeswitching via language mixing to fused lects.* [Theme 1]
- Sitaram et al. (2019) — *A survey of code-switched speech and language processing.* [Theme 3]
- Radford et al. (2023) — Whisper: *Robust speech recognition via large-scale weak supervision.* [Theme 2]
- Pratap et al. (2023) — Meta MMS: *Scaling speech technology to 1,000+ languages.* [Themes 2, 4]
- Seamless Communication (2023) — *SeamlessM4T.* [Themes 2, 3]
- NLLB Team (2022) — *No Language Left Behind.* [Theme 2]
- Bartelds et al. (2023) — *Making more of little data: low-resource ASR via data augmentation.* [Theme 2]
- Adebara & Abdul-Mageed et al. — AfroLID / SERENGETI (African language ID & pretraining). [Theme 4]
- Adelani et al. — MasakhaNER and related African NLP benchmarks. [Theme 4]
- Levow et al. — computational work on tone function in ASR. [Theme 5]

## Related

Companion project repository: [link to Repo 1] — where interventions drawn
from these readings are tested on Nouchi.
