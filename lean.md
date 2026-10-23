# Formalized in Lean — Index

*Machine-checked mathematics: claims a computer verifies, not claims you take on
trust. For a high-assurance reader this is the headline capability — the same
discipline that formal methods bring to cryptographic protocols and safety-critical
systems, applied to original mathematics.*

> **How to read the status column.** A result is **PROVEN** only when the project
> *builds* and `#print axioms <thm>` shows the theorem reduces to Lean's foundational
> axioms (`propext`, `Classical.choice`, `Quot.sound`) with **no `sorryAx`**. A raw
> `grep` for the token `sorry` is only an upper bound — it also catches the word in
> comments and docstrings, and in practice badly over-counts (the string "sorry-free"
> in a docstring reads as a `sorry`). Every "proven" claim below was checked with
> `#print axioms`, not grep. Each certifiable repo carries a `Certify.lean` and a
> GitHub Actions workflow that rebuilds and re-runs the axiom check, failing on
> `sorryAx` or on a missing per-theorem report — public, reproducible proof a stranger
> can run, strictly stronger than "it ran on my laptop."

## Scorecard

| Repo | src `.lean` | theorems | status | note |
|------|------------:|---------:|--------|------|
| [`lean-sabidussi`](https://github.com/RaggedR/lean-sabidussi) | 5 | 31 | **PROVEN** (0 `sorry`) | **PhD theorem.** 4 headline theorems axiom-checked clean. The crown jewel. |
| [`warnaar-glue`](https://github.com/RaggedR/warnaar-glue) | 7 | 88 | **PROVEN** (`sorry`-free) | Glue for two Warnaar results; conditional theorems carry their literature inputs as explicit hypotheses, not axioms. |
| [`lean-hopf-algebras`](https://github.com/RaggedR/lean-hopf-algebras) | 15 | 157 | **PARTIAL** (honest) | 5 headline theorems axiom-clean; 3 `sorry` isolated in `Transfer.lean`, which the certified root does not build. |
| [`social-network`](https://github.com/RaggedR/social-network) | 5 | 37 | **PROVEN** (`sorry`-free) | Directed-container comonad laws (Haskell + Lean), no Mathlib dependency. |
| [`trajectory-tracing`](https://github.com/RaggedR/trajectory-tracing) | 25 | 227 | **PROVEN** (`sorry`-free) | Epistemic-honesty formalism: 5 honesty/trajectory theorems, no Mathlib. |
| [`trust-boundaries`](https://github.com/RaggedR/trust-boundaries) | 30 | 249 | **PROVEN** (`sorry`-free) | Per-agent trust-level algebra (meet/join + `cmax` aggregation) — **zero axioms**. |
| [`continued-fractions`](https://github.com/RaggedR/continued-fractions) | 5 | 418 | **STATED** (not built) | Legendre palindrome / √n. Imports Mathlib but ships no Lake project — honestly left unbuilt rather than claimed. |
| [`macbeth-seed`](https://github.com/RaggedR/macbeth-seed) | 85 | 631 | **MIXED** (44 `sorry`) | Container-theory spine. A large fraction is scaffolding *stated*, not proven — said so plainly. |
| [`symmetric-graphs`](https://github.com/RaggedR/symmetric-graphs) | 42 | 365 | **MIXED** | Computational companion to `lean-sabidussi`: per-graph Hecke algebras + example catalogue. |

## Reading the scorecard

- **[`lean-sabidussi`](https://github.com/RaggedR/lean-sabidussi) is the crown jewel.**
  A non-trivial *original* theorem — the Sabidussi representation and Lorimer's
  theorem for vertex- and arc-transitive graphs, from my PhD — machine-checked, 0
  `sorry`. The four headline theorems (`sabidussiIso`, `lorimer_forward`,
  `connectionSet_eq_doubleCoset`, `quotient_cosetGraph_iso`) each reduce to
  `[propext, Classical.choice, Quot.sound]` and nothing else. The connection set the
  construction builds is a union of **double cosets** — a basis of the Hecke algebra
  ℋ(G,H) — so this repo is the formal core of the symmetric-graphs ⟷ Hecke-algebra
  link described on the [landing page](README.md).
- **[`macbeth-seed`](https://github.com/RaggedR/macbeth-seed) is stated honestly.** 44
  `sorry` across 631 theorems means a large part is a *stated* scaffold, not a proof.
  Calling all 631 "formalized" would be exactly the overclaim this index exists to
  prevent; the honest line is "a container spine with N proven, M stated."
- The trust/honesty strand ([`trust-boundaries`](https://github.com/RaggedR/trust-boundaries),
  [`trajectory-tracing`](https://github.com/RaggedR/trajectory-tracing),
  [`social-network`](https://github.com/RaggedR/social-network)) is self-contained — no
  Mathlib, ~25-second CI builds — and fully `sorry`-free. These are the AI-trust
  results, formalized: that an honest trajectory keeps a non-degenerate trust level,
  that a circular trajectory collapses to ⊥, that trust composition is monotone.

## Mathlib-structured formalization *(maintained locally, not upstreamed)*

Beyond the standalone repos above, the same mathematics is also formalized in
**Mathlib's own module structure and conventions**, as a single local Mathlib
development. This is kept **local by deliberate choice** — a personal development, not
a set of public pull requests:

- **Hopf algebras & umbral calculus** — the additive (𝔾ₐ) Hopf/bialgebra structure on
  `R[X]`, delta operators and Rota's classification, umbral operators via generating
  functions, binomial-type sequences (ascending/descending Pochhammer, Lah), and the
  compositional inverse of a formal power series (Lagrange inversion).
- **Symmetric graphs / Sabidussi** — group actions on simple graphs, coset graphs, the
  Sabidussi representation theorem, Lorimer's theorem, and quotient graphs.
- **Named-graph & surface examples** — the Langer graph and Tutte 12-cage; dodecahedron,
  Petersen, Heawood, Möbius–Kantor and other named graphs; voltage-graph constructions;
  the Meinhold and Zhou families as Sabidussi coset graphs; cellular surfaces and CSS
  quantum codes.

Mathlib-conformant in structure and naming, but not submitted upstream.

## Certification mechanics (reproducible recipe)

For Mathlib projects, pin a known-good `lake-manifest.json` to the target Mathlib
revision and `lake exe cache get` rather than running `lake update` from scratch; for
self-contained projects, just build (fast, no cache). Add a `Certify.lean` of
`#print axioms` statements, and a CI step that fails on `sorryAx` **and** on any missing
per-theorem report — accepting both `depends on axioms: [...]` and `does not depend on
any axioms` (a zero-axiom theorem prints the latter). The per-theorem-report check
defeats a vacuous pass from a mistyped theorem name.

---

*See also: the [landing page](README.md) for how this connects to the cryptography and
trustworthy-ML work, and the [expository index](expository.md) for the prose behind the
proofs.*
