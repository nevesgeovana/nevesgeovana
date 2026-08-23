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

### How they are built

Both libraries are built with a disciplined AI assisted process. Independent reviewer roles that report findings and never edit, because the implementer must not be the only reviewer of the change. A loop that plans, develops, reviews, audits and hands off, in that order. Gates that refuse to close a work item without its review evidence. Every guard carries a mutation test whose only job is to prove the guard actually fails when it should, because an unverified guard is decoration.

That process used to be committed alongside the code, on the reasoning that a method you cannot inspect is a method you cannot trust. I still hold the second half of that sentence. What changed is the first: the method turned out to be the part of this work that compounds, and publishing it by default meant giving away the asset while the artifacts it produces are the deliverable.

So the method is no longer shipped incidentally with the libraries. What I publish about it is deliberate, and it is the didactic material above: [From Curiosity to Contribution](https://github.com/nevesgeovana/from-curiosity-to-wisdom/tree/main/from-curiosity-to-contribution) is the method taught properly, end to end on a real paper, and it is the export I maintain for exactly this purpose.

What stays with me and is never delegated: product owner, domain expert, numerical analyst. The assistant drafts, derives, audits, and challenges. It does not decide.

## What lives in private repositories

Two workspaces are not public, and they are where most of the daily work happens.

- **geoverse-research**, my research workspace. Enumerated corpus and bibliography, a register of research questions, a logbook, and the planner that carries a question from an idea to a run to an analysis to a deliverable. It is private because it holds material I cannot redistribute, not because the method is a secret. The method is the deck above.
- **The control level above them**, which owns what belongs to no single repository: the shared process, the knowledge base, the registry that decides what may ever be published, and the identity and evidence rules the others are built with. It is private, and it is where the method lives now.

If you work in wind tunnel testing, aeropropulsive integration, or research automation, I am glad to talk about how to work well with an AI assistant: the reasoning behind a structural decision, the traps worth knowing, the mistakes that produced the rules. What I no longer hand over is the working method itself, charters and templates included. It took two years to build and it is the part I keep. The deck above is the version I chose to teach, and it is complete on its own terms.

Open an issue in any of the public repositories above, or reach me on LinkedIn.

## Selected publications

- Neves, G., Bienemann, R., Barbosa de Araújo, T., Annes da Silva, R.G. Interchangeable Aircraft Framework for Propeller Integration and Aeropropulsive Studies. Journal of Aircraft, Article in Advance, 2026. DOI [10.2514/1.C038629](https://doi.org/10.2514/1.C038629)
- Neves, G., Araujo, T.B., Sinnige, T., Annes da Silva, R.G. Decomposing Aeropropulsive Phenomena Governing Stability and Control Sizing of Aft-Propeller Aircraft. AIAA AVIATION 2026. DOI [10.2514/6.2026-4720](https://doi.org/10.2514/6.2026-4720)

## Find me

- [LinkedIn](https://www.linkedin.com/in/nevesgeovana/)

The unknown is not a threat. It is an itinerary.
