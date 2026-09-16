# Claudium, the Small Business Brain

**A guided interview that turns what's in your head into files Claude can actually use and reuse. It forgets less, it hallucinates less, it cheats less because, well, its smarter now.**

Unfortunately, Anthropic's Claude model starts every conversation knowing little to nothing about your business. It doesn't know what you sell, how you sound, or what you decided last month. Maybe it has a summary of a summary of a summary of your prior chats if you are organized enough to bucket them into folders. If not, every chat begins with ten minutes of re-explaining to ensure the context is accurate and not diluted by drift.

This is a fix: eight short markdown files that Claude reads before it answers, and a set of interview prompts that get them written. No software, no dependencies, nothing to maintain. About 90 minutes of your time, once--then it has a place to update to stay fresh and accurate. 

---

## Quick start

1. Download or clone this repo.
2. Read [`WHICH-VERSION.md`](WHICH-VERSION.md) — one person, or several?
3. Open that folder's `00-START-HERE.md`.
4. Start with sitting 00: attach nothing, paste the prompt, find out what Claude already thinks it knows about you.

That's it. There's nothing to install.

---

## Why this exists

Most "AI memory" projects solve the problem with infrastructure: a vector store, a knowledge graph, an ingestion pipeline, a nightly job. That works at scale and needs a technical owner to keep it alive.

A business with two or five people has neither the corpus to justify it nor the person to maintain it. What it has is a few hundred facts that matter, living in one or two heads, and an AI that asks for them again every morning.

Writing them down solves it. The hard part was never storage — it's extraction. Most of this repo is the extraction.

---

## What's in the box

Two versions. They differ by **how many people work in the business**, not by what anyone pays for Claude.

```
├── WHICH-VERSION.md            ← start here
├── solo-operator-brain/        ← you run it on your own
└── shared-business-brain/      ← two or more of you
    ├── 00-START-HERE.md
    ├── 01-interviews/          ← 10–11 prompts, one per sitting
    ├── 02-brain-files/         ← the 8 files, blank
    ├── 03-load-the-brain/      ← getting them in front of Claude
    └── 04-skills/              ← 5 checks Claude runs automatically
```

### The eight files

| File | Holds |
| --- | --- |
| `business.md` | What you do, who buys, what constrains you |
| `offerings.md` | Products or services: prices, contents, timings, restrictions |
| `customer-faq.md` | The questions you answer over and over, plus what to escalate |
| `offer-rules.md` | What you discount, what you never discount, and why |
| `decisions.md` | The log. One line per decision, forever |
| `voice.md` | How you sound, built from real examples |
| `relationships.md` | Clients, partners, suppliers, concentration risk |
| `channels.md` *(shared)* / `how-i-work.md` *(solo)* | Tools and owners / how the week runs and what only you know |

---

## How it works

**Interviews → files → loaded into Claude.**

Each sitting is one file, one chat, ten to fifteen minutes. You attach the blank file, paste the prompt, answer questions. Claude writes the finished file at the end. You save it and close the chat.

Five skills then run checks automatically once the files are in place — voice and fact-checking on customer-facing copy, escalation routing on customer replies, rule-checking on any proposed discount, and a monthly review that catches staleness and contradictions.

---

## Design decisions worth knowing

These are the choices that make it work, and the ones to preserve if you fork it.

**One chat per file, never one long chat.** Over a 70-minute conversation Claude drifts in a predictable direction: it starts batching questions, accepts vague answers, and eventually drafts answers for you to nod at. Short chats keep it sharp.

**Claude is forbidden from offering answers you can agree to.** The single most important rule in every prompt. A fluent, agreeable model interviewing a tired founder about a hard topic will happily suggest "would you describe your voice as knowledgeable but unpretentious?" — and a sentence nobody wrote becomes policy. Every prompt makes you say it in your own words first.

**Skipping is a first-class action.** Every question can be skipped, which writes `[UNKNOWN — still to decide]` into the file. A marked hole is honest and gets filled later; an invented answer becomes a fact the whole business works from.

**Examples beat adjectives.** The voice file is built from five pieces of real writing, not from a description of tone. "Professional yet approachable" describes every business ever registered.

**Sitting 00 harvests, but doesn't trust.** Your Claude has months of accumulated context about you — some told, some inferred, some stale. The first sitting dumps it and marks each line by source. In the shared version, everyone runs it separately and then compares lists, which is usually the most surprising ten minutes in the kit: two people's Claudes have been learning divergent versions of the same business, privately, for months.

**The folder is the brain, not the Project.** Eight text files in a folder you own. A Claude Project is one convenient container. This is what makes it plan-agnostic, shareable, and portable.

---

## Works on any Claude plan, and moves with you

| You have | How you load it |
| --- | --- |
| Team / Enterprise | One shared Project — one upload, everyone has it |
| Pro / Max | Your own Project, built from the same folder |
| Free | Attach the two or three relevant files per chat, plus a condensed instruction block |

Mixed plans work fine — one person on Team, one on Pro, one on Free, all reading the same files and giving the same answers.

And it migrates. The files are plain markdown: they survive plan changes, account changes, someone leaving, and switching to a different AI tool entirely. What doesn't travel is Claude's private memory of your chats — which is precisely the argument for writing things down. See `03-load-the-brain/04-moving-between-plans.md`.

---

## What this does *not* do

It doesn't read your email overnight, enrich contacts while you sleep, or learn on its own. Those systems exist and they need a full-time technical owner. At this size the upkeep costs more than the insight.

And it only works if someone writes to it. After any conversation that settles something, ask Claude to write the line for `decisions.md` and paste it in. Two minutes. **That habit is the entire learning loop — everything else here is scaffolding around it.** A brain nobody writes to is a folder of ageing documents within a quarter.

---

## Adapting it

The kit is written for small businesses in general, which means it fits none of them perfectly. Two intended escape hatches:

- **Sitting 01 (or 02) reshapes the rest.** It ends by telling you which later sittings need adapting for your kind of work — a service business reframes the offerings sitting around rates and availability rather than stock.
- **The prompts are yours.** Every file here is plain markdown with no magic in it. Edit the questions, drop the sittings that don't apply, add ones that do.

If you adapt it for a specific trade, that's a useful fork, and a good PR. Sharing is caring. 

---

## Contributing

Issues and PRs welcome. Particularly useful:

- **Trade-specific variants.** The generic version is necessarily thinner than a tailored one.
- **Prompt fixes.** If a sitting reliably drifts, produces vague files, or asks something that makes no sense in your line of work, that's a bug — please report it with what happened.
- **Translations.** The files are prose; nothing blocks this.

Please keep the design decisions above intact, especially the "never offer an answer to agree to" rule. It's the one that quietly protects the quality of everything downstream.

---

## Provenance

Original was built for a real client — a small Brooklyn tea company — and then generalised to accommodate other use cases. The original was pre-filled from months of consulting context, which made it stronger than this version because correcting is easier than composing, and produces better material.

If you're using this cold, expect the voice file to be the weakest output, and consider doing that sitting with someone else in the room. The more you input, the smarter the brain. 

---

## Licence

[MIT](LICENSE). Use it, fork it, adapt it for your trade, sell services around it — just keep the notice.

## A note on names

This is an independent project. Claude and Anthropic are trademarks of Anthropic, and nothing here is affiliated with or endorsed by them. Just trying to help. 
