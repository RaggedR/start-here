# Selected Expository Writing

*Mathematics and systems, written to be read. Organized by what each body of work
demonstrates — not by subject. Cryptography and formal methods lead; the mathematical
depth is the foundation beneath, not the headline. Every link is a public repository.*

---

## The program — one connected body of work

Most of what follows is **not** a scatter of unrelated projects. It is one research
program in **algebraic combinatorics and representation theory**, pursued with a
growing insistence that the proofs be **machine-checked**. The pieces connect:

- **Symmetric graphs ⟷ Hecke algebras.** My thesis, *Symmetric Graphs and their
  Quotients*, studies vertex- and arc-transitive graphs through the group acting on
  them. Every such graph is a coset graph `Sab(G, H, D)` (Sabidussi), whose connection
  set `D` is a union of **H–H double cosets** — and those double cosets are precisely a
  basis of the **Hecke algebra** ℋ(G,H) = End_G(ℂ[G/H]), my doctoral area. Lorimer's
  theorem (arc-transitive ⟺ `D` is a *single* double coset `HaH`) is the graph-theoretic
  face of the smallest non-trivial Hecke structure.
  → formalized in [`lean-sabidussi`](https://github.com/RaggedR/lean-sabidussi);
  per-graph Hecke computations and the example catalogue in
  [`symmetric-graphs`](https://github.com/RaggedR/symmetric-graphs); the representation
  theory in [`hecke-algebras`](https://github.com/RaggedR/hecke-algebras).
- **q-series, symmetric functions & positivity.** The same algebraic world one
  deformation over: symmetric functions and Macdonald polynomials, cylindric partitions
  and Warnaar's positivity program
  ([`cylindric-partitions`](https://github.com/RaggedR/cylindric-partitions),
  [`warnaar-glue`](https://github.com/RaggedR/warnaar-glue)), with the **umbral /
  finite-operator calculus** as the Hopf-algebraic backbone
  ([`lean-hopf-algebras`](https://github.com/RaggedR/lean-hopf-algebras)). Double
  cosets, orbital algebras, and q-deformed symmetric functions are all facets of the
  same representation-theoretic machinery.
- **Formalization as the method.** Increasingly the program is written in **Lean 4** and
  certified in CI — the graph theorems, the umbral/Hopf structures, and the Warnaar glue
  are claims a computer verifies, not claims you take on trust. This is the through-line
  to the cryptography and trustworthy-ML work below: *rigour you can check.*

A parallel strand applies **category theory** to the compositional modelling of real
systems — directed containers, with a Lean-verified spine
([`macbeth-seed`](https://github.com/RaggedR/macbeth-seed)) and applied instances
([`stalin`](https://github.com/RaggedR/stalin),
[`firm`](https://github.com/RaggedR/firm),
[`federation`](https://github.com/RaggedR/federation), …). Distinct in subject, same
habit of mind: find the structure, then make it formal.

The sections below are grouped by *what each piece demonstrates* for a security reader;
the paragraph above is the map of how they fit together as research.

---

## 1. Cryptography, randomness & number theory
*Breaking and building the primitives security rests on.*

- **A Martin-Löf Test That Pseudorandom Generators Fail** —
  [`category`](https://github.com/RaggedR/category). A computability-theoretic
  randomness test that provably distinguishes PRG output from true randomness. Directly
  about the soundness of cryptographic randomness.
- **Galois Theory and the Shield Bound** —
  [`polynomial-primes`](https://github.com/RaggedR/polynomial-primes). How far a
  polynomial can beat Euler's bound; irreducibility and Galois structure — the algebra
  under public-key cryptography.
- **Bunyakovsky's Conjecture** —
  [`polynomial-primes`](https://github.com/RaggedR/polynomial-primes). Prime values of
  irreducible polynomials.
- *Companion code:* [`homomorphic-encryption`](https://github.com/RaggedR/homomorphic-encryption)
  (Paillier + Schnorr ZK), [`watermark-rs`](https://github.com/RaggedR/watermark-rs)
  (Legendre spread-spectrum), [`watermark-attack`](https://github.com/RaggedR/watermark-attack)
  (adversarial robustness).

## 2. Formal methods & machine-checked proof
*High-assurance: claims a computer verifies, not claims you trust.* See the dedicated
**[Lean index](lean.md)** for the full scorecard.

- **From Polynomials to Proof / Umbral Calculus in Lean** —
  [`lean-hopf-algebras`](https://github.com/RaggedR/lean-hopf-algebras),
  [`umbral-calculus`](https://github.com/RaggedR/umbral-calculus). Formalizing Rota's
  finite operator calculus; a PhD-theorem-grade result, machine-checked.
- **The Category of Containers** —
  [`category-of-containers`](https://github.com/RaggedR/category-of-containers). A
  compositional foundation with a Lean-verified spine
  ([`macbeth-seed`](https://github.com/RaggedR/macbeth-seed)).
- **Sabidussi / Lorimer for symmetric graphs** —
  [`lean-sabidussi`](https://github.com/RaggedR/lean-sabidussi). My PhD theorem,
  formalized (0 `sorry`, axiom-checked). The connection set it builds is a union of
  **double cosets** — a basis of the Hecke algebra ℋ(G,H) — the formal core of the
  symmetric-graphs ⟷ Hecke-algebra link.

## 3. Trustworthy & interpretable machine learning
*Knowing why a model decides — model assurance, not just accuracy.*

- **Causal Interventions on Sparse-Autoencoder Features** &
  **Learning Combinatorial Bijections with Transformers** —
  [`bijection-transformer-interpretability`](https://github.com/RaggedR/bijection-transformer-interpretability).
  What a transformer's internal features actually represent, tested by intervention.
- **The RSK Transformer as a Manifold Microscope** —
  [`rsk-manifold-microscope`](https://github.com/RaggedR/rsk-manifold-microscope).
- **Mechanistic interpretability of small transformers** —
  [`octopus-streams`](https://github.com/RaggedR/octopus-streams),
  [`rsk-transformer`](https://github.com/RaggedR/rsk-transformer) (100% exact at n=10,
  99.99% at n=15; probing whether it learned a parallel growth-diagram rule).
- **Trajectory Tracing for Epistemically Honest AI Agents** —
  [`trajectory-tracing`](https://github.com/RaggedR/trajectory-tracing); **per-agent
  trust descriptors** — [`trust-boundaries`](https://github.com/RaggedR/trust-boundaries).
  Evaluating whether an agent's reasoning is *honest* — AI trust, directly on-theme, and
  formally verified (see the [Lean index](lean.md)).

## 4. Knowledge representation & reasoning
*Formal structure over knowledge — the backbone of analysis and retrieval systems.*

- **Description Logic, OWL, and Semantic Reasoning** —
  [`description-logic-owl`](https://github.com/RaggedR/description-logic-owl). The logic
  under ontologies and automated reasoning.
- **Knowledge-Graph-Guided Fine-Tuning of Embedding Models** —
  [`embeddings`](https://github.com/RaggedR/embeddings). A domain retrieval model that
  beat OpenAI's `text-embedding-3-small` on mathematical search (MRR 0.816 vs 0.461).

## 5. Autonomous agents & systems
*Automation you can reason about.*

- **A Toy Agent Harness** —
  [`toy-agent-harness`](https://github.com/RaggedR/toy-agent-harness). A minimal
  autonomous agent harness, essay + working code.
- **Why Topology Determines Diversity** —
  [`mathematical-systems`](https://github.com/RaggedR/mathematical-systems) / GECCO 2026
  work. How communication topology (not fitness landscape) governs multi-agent diversity.

## 6. Compositional modeling of real systems (category theory)
*Modeling complex systems as composable, formally-specified parts.*

- **Supply Chains / Social Networks / Federations / Org-charts as Directed Containers** —
  [`supply-chains`](https://github.com/RaggedR/supply-chains),
  [`social-network`](https://github.com/RaggedR/social-network),
  [`federation`](https://github.com/RaggedR/federation),
  [`org-chart`](https://github.com/RaggedR/org-chart),
  [`firm`](https://github.com/RaggedR/firm),
  [`stalin`](https://github.com/RaggedR/stalin),
  [`voting`](https://github.com/RaggedR/voting),
  [`dungeon`](https://github.com/RaggedR/dungeon). One categorical idea applied across a
  famine economy, a federation, a firm, a social graph.
- **The Category Theory You Already Know** —
  [`category-theory-you-already-know`](https://github.com/RaggedR/category-theory-you-already-know).
  A programmer's on-ramp.
- **Containers: From Syntax to Semantics** —
  [`macbeth-seed`](https://github.com/RaggedR/macbeth-seed).

## 7. Mathematical foundations
*The depth the above is built on — rigor as a baseline.*

- **Cylindric partitions & the Warnaar positivity program** —
  [`cylindric-partitions`](https://github.com/RaggedR/cylindric-partitions) (with
  [`warnaar-glue`](https://github.com/RaggedR/warnaar-glue), the Lean-formalized
  connecting arguments).
- **Hecke algebras** — [`hecke-algebras`](https://github.com/RaggedR/hecke-algebras) (my
  doctoral area). The representation theory sitting on top of the double-coset structure
  that [`lean-sabidussi`](https://github.com/RaggedR/lean-sabidussi) formalizes and
  [`symmetric-graphs`](https://github.com/RaggedR/symmetric-graphs) computes per graph.
- **Puzzles, tableaux & mosaics; q-analogues** —
  [`tableaux-mosaics`](https://github.com/RaggedR/tableaux-mosaics),
  [`q-bool`](https://github.com/RaggedR/q-bool).
- **Continued fractions & Legendre's palindrome** —
  [`continued-fractions`](https://github.com/RaggedR/continued-fractions).
- **PDE / applied analysis** — [`pde-notes`](https://github.com/RaggedR/pde-notes).
  **Langlands notes** — [`langlands`](https://github.com/RaggedR/langlands).
- **Information geometry & LLM geometry essays** —
  [`kerry-questions`](https://github.com/RaggedR/kerry-questions).

---

*Why this ordering: a cyber/defense reader scans for cryptography, formal verification,
and trustworthy ML first; the mathematical depth (§7) is the foundation that makes those
credible, so it anchors the list rather than leading it.*
