# Geovana Neves

Aerodynamics and flight dynamics engineer. Graduate student at Instituto Tecnologico de Aeronautica (ITA), researching propeller airframe aerodynamic interaction in collaboration with TU Delft.

Curiosity is common. Contribution is curiosity with a method.

## What I believe about doing research

Doubt is the beginning of wisdom, and the unknown is not a threat. It is an itinerary. An honest "I do not know" is a coordinate on the map, not a confession of weakness. Questions are lapidated rather than born perfect, so it is right to start before the question is ready and let it ripen inside the work. An error is the beginning of a journey, not the end of one.

The same stance carries into how I work with an AI assistant. The human owns the questions, the physics, the claims, and the decisions, and that ownership never transfers no matter how good the drafts get. The value is in the friction: an assistant that always agrees is a mirror, not a peer. Context is a deliverable, not a favor you hope for. And merit is not measured in suffering. Nobody prices the Pythagorean theorem by the pain of its proof.

Everything below is that stance made into artifacts. The teaching material first, because it is the reasoning; the libraries after, because they are the consequence.

## The didactic material

### [from-curiosity-to-wisdom](https://github.com/nevesgeovana/from-curiosity-to-wisdom)

Materials on research craft and AI assisted research methodology. Each folder is one complete, self sufficient contribution, produced by the very method it teaches.

**[From Curiosity to Contribution](https://github.com/nevesgeovana/from-curiosity-to-wisdom/tree/main/from-curiosity-to-contribution)** is the first one. It exists because colleagues kept asking how an AI assistant became part of real, published research work, from the first draft to the conference talk. It is not a tool tutorial. It is a method, demonstrated end to end on a real paper presented at AIAA AVIATION 2026, and it assumes no prior experience with AI tools.

Three artifacts, all in the repository:

| Artifact | What it is |
|---|---|
| An 89 page deck | Twelve parts, LaTeX sources and compiled PDF |
| A mobile cheat sheet | Eleven cards, 90 x 160 mm, one topic per swipe |
| A cloneable workspace | A generic research workspace skeleton: seven skills, two agents, catalogs, rituals. Unzip, rename the example threads, begin |

What the deck covers, in order: the mindset (doubt, lapidated questions, error as raw material), the method as eight consolidated concepts each with a lived episode, three cognitive traps and their antidotes, one researcher's mental map in everyday words, the working contract with an AI assistant, a full case study taking one paper from blank page to AIAA, the rituals that keep it running, the research workspace behind it, a practical guide plus the template, and an invitation to reflect on merit and complementarity.

Two reading paths. The deep path reads every slide and the deck is self sufficient. The fast path reads only the gold takeaway boxes: about five minutes for the full storyline. The pocket path is the cheat sheet.

Content under CC BY 4.0, workspace template and scripts under MIT. Use it, adapt it, teach from it.

## The libraries

Both are Python, MIT licensed, published on PyPI and archived on Zenodo. Both exist for the same reason: an analysis has to stay defensible months later, to someone who was not in the tunnel that week. Both also publish their specification, their decision record, and their open questions, because a requirement that lives only in the author's head is not a requirement.

### [itaca](https://github.com/nevesgeovana/itaca)

```bash
pip install itaca
```

Integrated Toolkit for Aerospace Computation and Analysis. It manages multidimensional experimental and numerical datasets, wind tunnel campaigns, CFD post processing, flight test data, engineering computations, with mandatory provenance, automatic GUM compliant uncertainty propagation including covariance, and an origin tag on every value. Every operation returns a new frame and records itself in the history, so a result can always be traced back to the raw channel it came from. Where a propagation rule is not yet frozen, the operation raises instead of returning a number, because refusing is more honest than guessing.

Pre release, API not frozen, latest v0.2.1. [PyPI](https://pypi.org/project/itaca/) and DOI [10.5281/zenodo.21482648](https://doi.org/10.5281/zenodo.21482648).

### [pyflightstream](https://github.com/nevesgeovana/pyflightstream)

```bash
pip install pyflightstream
```

Version aware, didactic Python driver for the FlightStream panel method solver. The solver version is an explicit input: every command it emits is validated against a per version command database, and old versions are only ever added, never dropped, so a campaign stays reproducible across solver upgrades. It also carries campaign workspaces, run matrices, and optional aeroelastic coupling.

Latest release v0.4.0. [PyPI](https://pypi.org/project/pyflightstream/) and DOI [10.5281/zenodo.21482924](https://doi.org/10.5281/zenodo.21482924).

### The workspace is open source too, not only the library

Both repositories commit the `.claude/` workspace I built to develop them: the agent charters, the skills, the hooks, and the guard scripts that enforce them. The library is what you install. The workspace is how it was built, and it is public for the same reason the code is. A method you cannot inspect is a method you cannot trust, and a solo maintainer who reviews only her own work has one documented failure mode: self review blindness.

**Six agent charters.** Every one of them is read only. They report findings, they never edit, because the implementer must not be the only reviewer of the change.

| Agent | What it reviews |
|---|---|
| `architect-reviewer` | Structural conformance: public API, module boundaries, imports, dependencies |
| `qa-engineer` | Test design in the ISTQB tradition, defect prevention rather than detection: whether the tests would catch the defects this change could introduce |
| `vv-engineer` | Verification and validation in the tradition of AIAA G-077 and NASA-STD-7009: evidence is documented, never asserted |
| `tech-writer` | Documentation currency and didactic quality: docs may never drift silently from the code, and facts live in one home |
| `api-designer` | Interface ergonomics: signatures, CLI, error messages, and examples reviewed the way a UX designer reviews a screen |
| `incident-analyst` | A failure that already happened. It finds the structural cause, designs the guard that makes recurrence impossible, and proves the guard blocks the original failure |

**The process, as invocable skills.** The loop is `plan`, `develop`, `role-review`, `audit`, `handoff`, and it runs in that order.

- `plan` keeps the plan ledger and the milestone map, and proposes the next work window.
- `develop` executes one work item in the repository's own order: pin it to an authority, write the usage example, write the falsifying test and measure it RED on the base, minimal implementation, refactor, records in the same step, gate, commit.
- `role-review` runs the applicable reviewer passes on the item's diff and drives every finding to fixed or registered. No work item closes without it.
- `audit` sweeps the committed tree for drift against the specification and the adopted external guides, and turns each finding into an update, a deletion, or a plan item.
- `handoff` closes the session: what was decided, what is open, the single next action. Context is a deliverable, so continuity is written, not hoped for.
- `version-control` and `release` carry the commit and release sequences as templates, so an operator never reconstructs them under pressure.

pyflightstream adds the skills its domain demands: `add-command`, `derive-requirements`, `fts-version-update`, `run-validity`, and `run-physics`, the last two of which spend a licensed solver seat and say so in their own metadata.

**And the gates that make the process non optional.** Hooks refuse to let a work item close without its review attestation, and a set of guard scripts checks the release gate, the review rounds, the shipped surface, the side effect declarations, the version identity, and the pre push receipt. Each guard ships with a mutation test whose only job is to prove the guard actually fails when it should, because an unverified guard is decoration.

What stays with me and is never delegated: product owner, domain expert, numerical analyst. The assistant drafts, derives, audits, and challenges. It does not decide.

## What lives in private repositories

Two workspaces are not public, and they are where most of the daily work happens.

- **aeropropulsive-research**, my research workspace. Enumerated corpus and bibliography, a register of research questions, a logbook, and the planner that carries a question from an idea to a run to an analysis to a deliverable. It is private because it holds material I cannot redistribute, not because the method is a secret. The method is the deck above.
- **ClaudeCoordinator**, the coordination level above the libraries and the research workspace. It owns what belongs to no single repository, and it carries the methodology the others are built with: a process kit, a knowledge base, a scope registry that decides what may ever be published, and a scaffold that wires the process into a new project.

If you work in wind tunnel testing, aeropropulsive integration, or research automation and any of this is close to what you are trying to build, ask. I am glad to share the practical shortcuts, the templates, the reasoning behind a structural decision, and the mistakes that produced it. Reproducing a workflow should not cost you the two years it cost me.

Open an issue in any of the public repositories above, or reach me on LinkedIn.

## Selected publications

- Neves, G., Bienemann, R., Barbosa de Araújo, T., Annes da Silva, R.G. Interchangeable Aircraft Framework for Propeller Integration and Aeropropulsive Studies. Journal of Aircraft, Article in Advance, 2026. DOI [10.2514/1.C038629](https://doi.org/10.2514/1.C038629)
- Neves, G., Araujo, T.B., Sinnige, T., Annes da Silva, R.G. Decomposing Aeropropulsive Phenomena Governing Stability and Control Sizing of Aft-Propeller Aircraft. AIAA AVIATION 2026. DOI [10.2514/6.2026-4720](https://doi.org/10.2514/6.2026-4720)

## Find me

- [LinkedIn](https://www.linkedin.com/in/nevesgeovana/)

The unknown is not a threat. It is an itinerary.
