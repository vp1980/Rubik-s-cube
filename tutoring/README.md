# Year 5 11+ Programme — Operating Model

A tutor-augmented, AI-prepared 11+ training programme for Year 5 pupils. The AI
produces the material and the marking analysis; the tutor teaches and owns the
relationship with the family.

This is the multi-pupil sibling of the single-child `oliver-tutor` programme.
Three differences drive everything else:

| | Oliver | These three |
|---|---|---|
| Age / year | 8, Year 4 | 9–10, Year 5 |
| Runway to exam | 2–3 years | **~12 months** |
| Pupils | 1 | 3, at different levels |
| Delivery | Local machine, parent runs it | Shared folder, tutor runs it |
| Coding strand | Yes | No — 11+ only |

---

## 1. The runway is the whole design constraint

Year 5 pupils now sit the 11+ at the **start of Year 6 — September 2027**.
Registration for most grammar schools closes around June/July 2027.

That is roughly **12 months, or ~40 teaching weeks**, and it is not
negotiable or extendable. Every decision below follows from it:

- **There is no time to mis-pitch.** Oliver's programme can afford two or three
  weeks of calibration because he has years. These three cannot. That is the
  argument for a baseline, and it is decisive — see §3.
- **Content coverage must finish by Easter 2027.** The summer term is
  rehearsal: timed papers, stamina, technique. If you are still teaching
  fractions in May you have already lost.
- **Speed is a target, not a by-product.** At Year 5, `SECURE` is not enough —
  a topic the child can do slowly still costs them the paper. The ladder adds
  `AUTO` as the real goal and the programme times work from week one.

## 2. Delivery: shared folder per family, GitHub for the programme

You asked whether GitHub is a good idea. **Split the question — it has two
different answers.**

**For the programme itself: yes.** The skill, the curriculum ladders, the
marking taxonomy, the report templates, the question banks — this is the
business. It is text, it changes, it benefits from version history, and it is
the thing you would licence or sell. It belongs in this repo.

**For the children's work and records: no.** Three reasons, in order of how
much they matter:

1. **Data protection.** These are identifiable records of named children —
   attainment data, wellbeing notes, in some cases SEN information. Under UK
   GDPR that is personal data about minors, and a Git repository is close to
   the worst possible container for it: history is immutable, so a record
   deleted today is still recoverable from every clone, and "delete this
   child's data" — a request a parent is entitled to make — becomes a history
   rewrite rather than moving a folder to the bin.
   This applies whether or not you charge: UK GDPR governs the processing of
   personal data, not commercial activity, so a tutor holding these records
   during an unpaid trial is a controller from the first session.
2. **Parents will not use it.** A parent photographing homework on a phone at
   9pm will not clone, commit and push. Any friction here does not slow the
   system down, it stops it — and the loop breaks *silently*, which is worse,
   because you carry on pitching at levels that went stale three weeks ago.
3. **You do not need what Git gives you.** Diffs and branches solve merge
   conflicts between concurrent editors. There are none here: one tutor writes
   each log, in sequence.

**The arrangement that works:**

```
Programme (this repo, private)          Pupil data (shared drive, per family)
├── tutoring/skill/                     11plus-<pupil-first-name>/
│   ├── SKILL.md                        ├── this-week/      ← tutor puts work here
│   ├── references/                     ├── completed/      ← family photographs into here
│   └── assets/                         ├── reports/        ← fortnightly tutor report
└── tutoring/baseline/                  └── progress-log.md ← single source of truth
```

Google Drive or OneDrive, one folder per family, shared with that family only.
Phone-native, no training required, and deleting a child's data is deleting a
folder. Keep the progress log in the shared folder rather than in the repo —
it is the pupil record, not the programme.

**Naming and minimisation.** First name plus initial in folder names, no
surnames, no dates of birth, no school names in filenames. Write a one-page
privacy notice for parents at sign-up covering what you hold, why, where, and
for how long. This costs you an hour and is the difference between a hobby and
something a school will refer to.

## 3. Baseline, delivered as a trial lesson — not one or the other

You framed this as a choice. It should not be: the correct answer is a single
session that is **diagnostically a baseline and experientially a trial lesson**,
and `baseline/baseline-paper.html` is built to be exactly that.

**Why a baseline is non-negotiable here.** With three children at unknown and
probably different levels, and twelve months of runway, guessing the pitch is
the most expensive mistake available. Pitch too high and you spend a month
destroying a child's confidence before anyone admits it is not working. Pitch
too low and you burn irreplaceable weeks. Oliver could absorb that; these three
cannot. You also cannot show a parent progress in March without a defensible
measurement from September — and "look how far they have come" is the entire
retention argument for a paid programme.

**Why it must not feel like a test.** This is the family's first contact with
the service. A child who leaves the first session feeling they failed an exam
is a child whose parents do not book a second. A parent who watches their
child sit silently through 50 minutes of assessment has not seen what they are
buying.

**So the session does both:**

| Time | What happens | What it measures |
|---|---|---|
| 0–5 min | Settle, explain it as a puzzle set, no marks announced | — |
| 5–9 min | Number Fluency Sprint, strictly timed | Times-table automaticity (highest-signal item in the whole paper) |
| 9–25 min | Maths mixed set | Coverage across M1–M10 |
| 25–40 min | Reading passage + comprehension + grammar | E1–E9, especially vocabulary and inference |
| 40–50 min | Verbal and non-verbal reasoning | V and N strands, both from cold |
| 50–60 min | **Tutor teaches one thing properly** | Nothing — this is the part the parent is buying |

That final ten minutes is not padding. Take the most interesting error the
child made, teach it, and have them get it right. The parent sees teaching, the
child leaves having succeeded at something, and you still have a complete
diagnostic profile.

**Run it cold.** No revision, no preparation, no warning of topics. A baseline
a parent has coached to is worse than no baseline, because it produces
confident wrong numbers. Say this to parents explicitly and explain why.

**Tell parents what the results are and are not.** They are a starting map, not
a verdict on whether the child will pass. Some will read a low baseline as a
prediction — say before you hand back any numbers that the September figure
exists to be beaten, and that the useful number is the March one.

## 4. The report is the product

The material is commodity — a dozen companies sell 11+ worksheets. What a
private tutor cannot easily produce, and what parents will actually pay a
premium for, is **a fortnightly diagnostic report that says why the child got
things wrong and what changed as a result.**

`skill/assets/tutor-report-template.md` is that artefact. It is written for the
tutor to review, adjust and put their name to — not to be sent raw to a parent.
That distinction matters commercially: the tutor stays the expert and the
accountable professional, and the AI is their preparation and analysis layer.
Sell "your tutor, with a research department", not "an AI tutor".

Two things make the report worth money, and both come from the marking
taxonomy in `skill/references/marking-and-feedback.md`:

- **Diagnosed scores, not raw scores.** 6/10 from careless slips and 6/10 from
  a missing concept need opposite responses. Reporting only the raw number is
  what every worksheet company does and it is nearly useless.
- **Patterns across weeks, not single sheets.** "Careless errors have dominated
  three weeks running — this is a checking habit, not a maths problem" is the
  sentence a parent remembers and repeats to other parents.

## 5. Running three children without tripling the work

- **One ladder, three positions on it.** The curriculum ladder is shared; each
  pupil's log records where they are on it. Never maintain three curricula.
- **Batch by strand, not by child.** Preparing three maths sessions at once is
  far less than three times one, because the topic research is shared and only
  the pitch differs.
- **Common core, differentiated tail.** Same passage, same context, same
  warm-up; the last third of each set diverges by level. This also matters if
  any of them are ever taught together.
- **Never compare them.** Not in reports, not in conversation, not implicitly
  by mentioning what another child is working on. If parents know each other —
  and they often do — this is the single fastest way to lose all three.

## 6. What to do next, in order

1. Confirm target schools and exam board for each child. GL, CEM and ISEB
   differ on extended writing, NVR weighting and paper format, and preparing
   for the wrong shape wastes a term. The ladder is currently board-agnostic;
   it gets a board-specific layer once this is known.
2. Set up the three shared folders and the privacy notice.
3. Run the baseline session with each child, cold, in the format above.
4. Mark with `baseline/marking-key.md`, build each pupil's log from
   `skill/assets/pupil-log-template.md`.
5. First fortnightly reports go out two sessions later — not after the
   baseline. A report needs a trend, and one data point is not a trend.

## 7. Contents

```
tutoring/
├── README.md                          this file
├── skill/
│   ├── SKILL.md                       the multi-pupil tutoring loop
│   ├── references/
│   │   ├── curriculum-ladders-y5.md   topic sequence, Year 5 pacing, 40-week plan
│   │   └── marking-and-feedback.md    error taxonomy and feedback language
│   └── assets/
│       ├── pupil-log-template.md      per-child record (lives in the shared folder)
│       └── tutor-report-template.md   the fortnightly report — the product
├── baseline/
│   ├── baseline-paper.html            the trial-lesson diagnostic, print-ready
│   └── marking-key.md                 answers, diagnostic mapping, banding
└── pupils/                            local scratch only — never commit pupil data
```
