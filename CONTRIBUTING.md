# Contributing

Thanks for looking. This repo is prose and prompts — no build, no tests, no
dependencies. Editing a file and opening a PR is the whole workflow.

## Most useful contributions

**Trade-specific variants.** The generic kit fits every small business
roughly and none of them well. A version tuned for a salon, a trades
business, a clinic, a studio or an agency is more useful than the general one
for the people in that trade. Fork the closest version, rewrite the
questions, keep the structure.

**Prompt bug reports.** A sitting is buggy if it:

- drifts — starts batching questions or accepting vague answers
- produces a thin file even when the person answered properly
- asks something meaningless for a whole category of business
- ends up writing answers the person never gave

Open an issue with the sitting number, what you were asked, and what came
out. Paste the transcript if you can.

**Translations.** Nothing blocks this. Keep the file names in English so the
instructions and skills still resolve.

## Please keep these intact

The kit works because of a few specific constraints. If a PR removes one,
please say why in the description.

- **One chat per sitting.** Not one long interview. Length is what causes
  drift.
- **Claude never offers an answer the person can agree to.** The single most
  important rule. Agreeable models plus tired founders produce policy nobody
  wrote.
- **Skipping writes `[UNKNOWN — still to decide]`.** A marked hole beats an
  invented answer.
- **The voice file is built from real examples**, never from adjectives.
- **No partial drafts mid-interview.** People switch from answering to
  editing and the quality collapses.
- **File names are fixed.** The instructions and all five skills resolve
  files by name. Renaming breaks them silently.

## Style

Plain language. Short sentences. Write for someone who is busy, not
technical, and doing this at the end of a working day.

Avoid: marketing register, em-dash asides, "unlock", "leverage",
"seamlessly", and any sentence that would survive being deleted.

## Scope

Things this project is deliberately not:

- a memory server, vector store or ingestion pipeline
- a hosted product
- anything that requires installing software

If a contribution needs a runtime, it belongs in a different repo.

## Licence

By contributing you agree your work is released under the repo's
[MIT licence](LICENSE).
