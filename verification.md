# The formal-verification program

*From a PhD theorem to a machine-checked proof to a local Mathlib development. The
claim a high-assurance reader should take from this page: the mathematics here is not
asserted, it is **verified by a computer**, and the verification is reproducible.*

---

## 1. The origin — the thesis

My doctoral thesis, *Symmetric Graphs and their Quotients*, studies vertex- and
arc-transitive graphs through the group acting on them. The central objects are coset
graphs `Sab(G, H, D)` (Sabidussi): a graph on the cosets `G/H` whose connection set `D`
is a union of **H–H double cosets** — and those double cosets are exactly a basis of the
**Hecke algebra** ℋ(G,H) = End_G(ℂ[G/H]). Lorimer's theorem — a graph is arc-transitive
iff `D` is a *single* double coset `HaH` — is the graph-theoretic face of the smallest
non-trivial Hecke structure.

*(The thesis PDF bundles third-party copyrighted material, so the repository is kept
private; the document is available on request.)*

## 2. The theorem, machine-checked

The core theorem is no longer only on paper. In
**[lean-sabidussi](https://github.com/RaggedR/lean-sabidussi)** the Sabidussi
representation theorem and Lorimer's theorem are **formalized in Lean 4 with 0 `sorry`**.
The four headline results —

- `sabidussiIso` — every vertex-transitive graph is a coset graph,
- `connectionSet_eq_doubleCoset` — the connection set is a union of double cosets,
- `lorimer_forward` — arc-transitivity forces a single double coset,
- `quotient_cosetGraph_iso` — the quotient construction is well-behaved —

each reduce, under `#print axioms`, to Lean's foundational axioms
(`propext`, `Classical.choice`, `Quot.sound`) and **nothing else**. The computational
companion, **[symmetric-graphs](https://github.com/RaggedR/symmetric-graphs)**, builds
the per-graph Hecke algebras ℋ(Aut Γ, Stab v) and an example catalogue. This is the most
defense-relevant single line in the portfolio: a non-trivial *original* theorem, checked
by machine, reproducibly.

## 3. The program around it

The same method extends across the research program (full scorecard in the
**[Lean index](lean.md)**):

- **[lean-hopf-algebras](https://github.com/RaggedR/lean-hopf-algebras)** — Hopf algebras
  and Rota's umbral / finite-operator calculus (honest PARTIAL: five headline theorems
  axiom-clean, three `sorry` isolated in a module the certified root does not build).
- **[warnaar-glue](https://github.com/RaggedR/warnaar-glue)** — the connecting arguments
  for two results on Warnaar's A₂ cylindric-partition positivity, `sorry`-free, with the
  literature inputs carried as *explicit hypotheses* rather than smuggled in as axioms.
- **The trust / honesty strand** —
  [trust-boundaries](https://github.com/RaggedR/trust-boundaries) (a per-agent
  trust-level algebra, **zero axioms**),
  [trajectory-tracing](https://github.com/RaggedR/trajectory-tracing) (an honest
  trajectory keeps a non-degenerate trust level; a circular one collapses to ⊥), and
  [social-network](https://github.com/RaggedR/social-network) (the directed-container
  comonad laws). AI-trust claims, formally verified.

## 4. A local Mathlib development *(not upstreamed — by choice)*

Beyond the standalone repos, the same mathematics is formalized in **Mathlib's own
module structure and conventions**, maintained as a single **local** Mathlib checkout —
a personal development, deliberately **not submitted as public pull requests**:

- **Hopf algebras & umbral calculus** — the additive (𝔾ₐ) Hopf/bialgebra structure on
  `R[X]`, delta operators and Rota's classification, umbral operators, binomial-type
  sequences, and the compositional inverse of a formal power series (Lagrange inversion).
- **Symmetric graphs / Sabidussi** — group actions on simple graphs, coset graphs, the
  Sabidussi and Lorimer theorems, quotient graphs.
- **Named-graph & surface examples** — the Langer graph and Tutte 12-cage; Petersen,
  Heawood, Möbius–Kantor and other named graphs; voltage-graph constructions; the
  Meinhold and Zhou families as Sabidussi coset graphs; cellular surfaces and CSS
  quantum codes.

Mathlib-conformant in structure and naming, kept local.

## 5. What it demonstrates

High-assurance work means claims a stranger can re-check, not claims you take on trust.
Each certifiable repo carries a `Certify.lean` and a GitHub Actions workflow that
rebuilds the project and re-runs `#print axioms` on the headline theorems, failing on any
`sorryAx` or on a missing per-theorem report. The result is a public, reproducible proof
— strictly stronger than "it ran on my laptop," and the same discipline formal methods
bring to cryptographic protocols and safety-critical code, applied to original
mathematics.

---

*See also: the **[Lean index](lean.md)** (the scorecard), the
**[container-theory program](containers.md)** (the other half of the "find the
structure, then make it formal" habit), and the **[landing page](README.md)**.*
