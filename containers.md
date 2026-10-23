# The container-theory program

*One categorical idea — the **directed container** — applied across a dozen real
systems, with a Lean-verified spine underneath. This page is the map; each repo is a
different domain stress-testing the same algebra.*

---

## The idea

A **directed container** (Ahman–Chapman–Uustalu) is a model of a system as *positions*
and, at each position, the *directions* you can move and where they take you — exactly
the data of a comonad. It is the dependent-type generalisation of a container
`Σ(s : S). P(s) → X`: a shape, and a set of positions over each shape. The payoff is
**composition**: directed containers compose, their morphisms are the
structure-preserving maps between systems, and the comonad laws say the "focus and move"
operations are coherent.

The bet this program makes is that a surprising number of real systems — a supply
chain, a firm, a federation of servers, a vote, a social graph — *are* directed
containers, and that once you see the container structure, the hard questions (what can
the system do to itself? what does each change cost? when does local agreement assemble
into a global object?) become questions about morphisms and comonad structure you can
actually compute with.

## The spine — theory, reference, and a machine-checked core

- **[macbeth-seed](https://github.com/RaggedR/macbeth-seed)** — the container-theory
  spine: papers, notes, and applied examples (GAs, Lean, Ethereum, orchestration). The
  seed everything else grew from.
- **[category-of-containers](https://github.com/RaggedR/category-of-containers)** — the
  living reference book on container theory (LaTeX + PDF), spun out of `macbeth-seed`.
- **[social-network](https://github.com/RaggedR/social-network)** — the comonad laws,
  **machine-checked in Lean 4**: the extension-functor laws, the container-morphism ≃
  natural-transformation isomorphism, and the directed-container comonad law, all
  `sorry`-free (see the **[Lean index](lean.md)**). This is the formal guarantee that
  the "focus and move" structure the instances rely on actually holds.

*The through-line to the rest of the portfolio: the same insistence on a
machine-checked core that drives the [formal-verification program](verification.md)
sits under the modelling here too.*

## The instances — one algebra, many domains

Each of these takes the container model into a different domain and reports where it
buys something and where it breaks.

| Repo | The system, as a container |
|------|----------------------------|
| [stalin](https://github.com/RaggedR/stalin) | The First Five-Year Plan as a container. Steel and soldiers are substitutes; the price of the second is paid in lives. |
| [federation](https://github.com/RaggedR/federation) | When can local agreement be assembled into a global object, and what stops it? Container morphisms, Čech cohomology, and a Möbius band of servers. |
| [firm](https://github.com/RaggedR/firm) | Three stages in a line — research, product, sales — as containers. Development holds the state and diagnoses the constraint; a CEO above reads that diagnosis and changes the shape of the firm. |
| [org-chart](https://github.com/RaggedR/org-chart) | Two-or-three people per project, two-or-three projects per person. What can the network do to itself, what does each change cost, and who has to agree? |
| [voting](https://github.com/RaggedR/voting) | Delegation is already a container morphism. What does that buy, and where does it break? |
| [three-dates](https://github.com/RaggedR/three-dates) | A dating app that shows you three candidates and makes you choose — matching by an LLM that interviews both sides over time, not a similarity score over a fixed feature vector. |
| [dungeon](https://github.com/RaggedR/dungeon) | Can an untyped oracle be held inside a typed interface when the oracle is the whole game? Three levels, nested languages, each inscribed in the one above it. |
| [supply-chains](https://github.com/RaggedR/supply-chains) | Supply chains as directed containers. |

## Why this matters for a high-assurance reader

The discipline here is **compositional modelling**: describing a complex system as
composable, formally-specified parts, with a machine-checked guarantee that the
composition laws hold. Two threads are directly on-theme for distributed and
trustworthy systems:

- **Local-to-global assembly** ([federation](https://github.com/RaggedR/federation)) is
  the Čech-cohomology question — when do consistent local views assemble into a single
  global object, and what obstruction stops them? That is the mathematics under
  distributed consensus and trust composition.
- **A verified comonad spine** ([social-network](https://github.com/RaggedR/social-network),
  Lean) means the modelling primitives aren't just suggestive analogies — the laws are
  proved, so the composition is sound by construction.

---

*See also: the **[Lean index](lean.md)** for the machine-checked core, the
**[formal-verification program](verification.md)** for the other half of the "make it
formal" habit, and the **[landing page](README.md)**.*
