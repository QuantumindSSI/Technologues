# Technologues

**Agentic and machine-learning systems engineering, written from
scratch over 100 weeks.** Two articles a day, one at 09:00
and one at 17:00, every day.

The full run is 1,406 articles across 100 weeks, 2026-08-20 to 2028-07-22.

The premise is that the skills behind a working agent form a
dependency graph, and that most engineers study the wrong layers of it
first. The series walks that graph from the bottom, one mechanism at a
time, building each one before discussing it.

Every implementation an article discusses lives in this repository. It
is written here, tested here, and then read line by line in the
article. Nothing is summarised from somebody else's code. Every number
quoted in an article came out of running a file you can run too.

## Quick start

Python 3.8 or newer. Standard library only, so there is no install
step, no virtualenv, and no requirements file.

```bash
git clone https://github.com/QuantumindSSI/Technologues.git
cd Technologues

# reproduce a measurement quoted in an article
python3 experiments/week-03/embedding_lab.py

# check the library does what the articles claim
python3 -m unittest discover -s tests -t .
```

Every experiment prints `All assertions passed` and exits 0. Anything
else is a bug, and it is worth telling me about.

## Published articles

2 published so far. Articles appear here on the day they
go out. Nothing is posted early.

### Week 3

- **2026-09-10 AM** [Hands-on: Build an Embedding Layer in an Hour and Find Out It Knows Nothing](https://github.com/QuantumindSSI/Technologues/blob/main/posts/2026-09-10-thu-am-tutorial-embedding-layers.md)
- **2026-09-10 PM** [Follow-up: Five Checks Before You Trust Your Embedding Layer](https://github.com/QuantumindSSI/Technologues/blob/main/posts/2026-09-10-thu-pm-followup-embedding-mistakes-checklist.md)

## The ten pillars

The series rotates through ten subject areas. Each one gets a
two-week block, then hands over to the next, so no single topic runs
long enough to go stale and every topic is returned to later at
greater depth.

| Pillar | Weeks | Articles |
|---|---:|---:|
| System Design Fundamentals | 10 | 140 |
| LLM Internals & Pretraining | 10 | 140 |
| Post-training & Alignment | 10 | 140 |
| Inference & Edge Deployment | 10 | 140 |
| Harness Engineering | 10 | 140 |
| Loop & Graph Engineering | 10 | 140 |
| Evals, Observability & Governance | 10 | 140 |
| MLOps & Infrastructure | 10 | 140 |
| Production Case Studies | 10 | 140 |
| Career, FDE & Interviews | 10 | 140 |

## Five passes over the same ground

Each pillar is covered five times, and the pass decides the
altitude. The first time through a topic asks how it works. The last
time asks what it costs at scale and where it breaks.

1. **Foundations**
2. **Builder's Pass**
3. **Failure Modes**
4. **Scale & Hardening**
5. **Frontier & Mastery**

## The weekly rhythm

The format of each slot is fixed, so the shape of a week is
predictable even when the subject is new.

| Day | 09:00 | 17:00 |
|---|---|---|
| Sunday | theme kickoff | poll |
| Monday | concept deep-dive | annotated diagram |
| Tuesday | concept deep-dive | repo walkthrough |
| Wednesday | case study | code deep-dive |
| Thursday | hands-on tutorial | common mistakes checklist |
| Friday | contrarian take | debate prompt |
| Saturday | recap + quiz | weekend challenge |

## Repository layout

| Tree | What it holds |
|---|---|
| `posts/` | The articles, published on the day they go out |
| `lib/` | Reference implementations the articles walk through |
| `tests/` | The suite proving `lib/` behaves as described |
| `experiments/` | Runnable measurements quoted in specific articles |
| `data/` | Frozen corpora, so a quoted number stays reproducible |

`lib/` is the durable code. `experiments/` is written per article and
left alone afterwards, so a measurement stays reproducible exactly as
it was published.

## How this repository is built

This tree is generated. Articles and code are written in a working
repository and published here once the day arrives, which is why you
will not find editorial notes, drafts, or unpublished articles.
Opening a pull request against a generated file will not stick, so
raise an issue instead and the fix goes in upstream.

Two rules the series holds itself to, and which you should hold it to:

- **Every number names its source.** A figure is either measured by a
  file in this repository, cited to a paper or a vendor document, or
  flagged in the text as unverified. There is no fourth option.
- **Every code listing is copied from a committed file.** If an
  article shows you a function, that function exists here, is tested
  here, and runs.

## Reproducing anything you read

Articles quote the file they came from. Run that file and compare. The
experiments are seeded, so a given article's numbers are stable across
machines and across runs. If a number here does not reproduce for you,
that is a defect worth an issue.
