# Robin Langer — formally-verified mathematics, cryptography & trustworthy ML

Mathematician (PhD) and software engineer. I build systems whose claims a computer can
check: **machine-verified proofs** in Lean 4, **cryptography** from first principles,
**interpretable and epistemically-honest ML**, and **autonomous research agents** whose
reasoning is adversarially verified. The through-line is *rigour you can reproduce* — no
result below asks to be taken on trust.

Start with the two indices — the **[Lean / formal-verification index](lean.md)** and the
**[expository writing index](expository.md)** — or scan the heroes and the category
directory below.

---

## The mathematical program — how the pieces connect

Much of the mathematics here is **not** a scatter of separate projects but one connected
research program in **algebraic combinatorics and representation theory**, increasingly
**machine-checked in Lean 4**:

- **Symmetric graphs ⟷ Hecke algebras.** My thesis studies vertex- and arc-transitive
  graphs through the group acting on them. Every such graph is a coset graph
  `Sab(G, H, D)` (Sabidussi), whose connection set `D` is a union of H–H **double
  cosets** — precisely a basis of the **Hecke algebra** ℋ(G,H) = End_G(ℂ[G/H]), my
  doctoral area. Lorimer's theorem (arc-transitive ⟺ `D` a *single* double coset `HaH`)
  is the smallest non-trivial Hecke case.
  → [`lean-sabidussi`](https://github.com/RaggedR/lean-sabidussi) (formalized, 0 `sorry`),
  [`symmetric-graphs`](https://github.com/RaggedR/symmetric-graphs) (per-graph Hecke
  algebras + example catalogue), [`hecke-algebras`](https://github.com/RaggedR/hecke-algebras).
- **q-series, symmetric functions & positivity.** The same algebra one q-deformation
  over: symmetric functions and Macdonald polynomials
  ([`haskell`](https://github.com/RaggedR/haskell), [`puzzles`](https://github.com/RaggedR/puzzles)),
  cylindric partitions and Warnaar's positivity program
  ([`cylindric-partitions`](https://github.com/RaggedR/cylindric-partitions),
  [`warnaar-glue`](https://github.com/RaggedR/warnaar-glue)), with the **umbral /
  finite-operator calculus** as the Hopf-algebraic backbone
  ([`lean-hopf-algebras`](https://github.com/RaggedR/lean-hopf-algebras),
  [`umbral-calculus`](https://github.com/RaggedR/umbral-calculus)).
- **Formalization as the method.** The graph theorems and the umbral/Hopf structures are
  written in **Lean 4** and certified by `#print axioms` — claims a computer verifies,
  not claims you take on trust. This is the through-line to the cryptography and
  trustworthy-ML work: *rigour you can check.*

*A parallel strand applies **category theory** to the compositional modelling of real
systems — directed containers with a Lean-verified spine
([`macbeth-seed`](https://github.com/RaggedR/macbeth-seed)) and applied instances. Same
habit of mind: find the structure, then make it formal.*

---

## Worth sixty seconds — the heroes

Ordered by what a high-assurance reader scans for first: verification, then
cryptography, then trustworthy ML, then autonomous research, then range.

| # | Project | The claim |
|---|---------|-----------|
| 1 · **Formal verification** | [`lean-sabidussi`](https://github.com/RaggedR/lean-sabidussi) | My **PhD theorem** (Sabidussi representation + Lorimer, for symmetric graphs) **machine-checked in Lean 4** — 0 `sorry`; the headline theorems reduce to Lean's foundational axioms, verified by `#print axioms`. |
| 2 · **Cryptography** | [`homomorphic-encryption`](https://github.com/RaggedR/homomorphic-encryption) | **Paillier homomorphic encryption + Schnorr zero-knowledge proofs**, built from scratch with no dependencies. |
| 3 · **Trustworthy ML** | [`rsk-transformer`](https://github.com/RaggedR/rsk-transformer) · [`trust-boundaries`](https://github.com/RaggedR/trust-boundaries) | A transformer learns the inverse RSK correspondence to **100% exact match** (n=10) and 99.99% at n=15 — 0.00004% of the space seen, so algorithmic generalisation, not memorisation (a baseline MLP gets 3.07%). Paired with a **formally-verified** per-agent trust algebra. |
| 4 · **Autonomous research** | [`warnaar-loop-experiment`](https://github.com/RaggedR/warnaar-loop-experiment) | A loop of amnesiac Claude agents — context cleared each round, notes the only memory — attacking an **open** positivity conjecture (Corteel–Dousse–Uncu / Warnaar). Across 27 agent instances it produced **genuine partial results** (a proof of the Q₁ case, a determinant identity for the Corteel–Welsh system, the Adjugate Monomial Theorem); the full conjecture remains open, and the repo says so. |
| 5 · **Range** | [`categorical-evolution`](https://github.com/lyra-claude/categorical-evolution) · [`embeddings`](https://github.com/RaggedR/embeddings) · [`smoke-flow`](https://github.com/RaggedR/smoke-flow) | A **published GECCO 2026** result (categorical composition of GAs); a math-retrieval embedder that **beats OpenAI's `text-embedding-3-small`** (MRR 0.816 vs 0.461, reproducible benchmark); a real-time **GPU Navier–Stokes** smoke solver. |

---

## The two indices

- **[Lean / formal-verification index →](lean.md)** — every formalized result, with a
  verification status (`PROVEN` = builds + `#print axioms` clean · `PARTIAL` · `STATED`)
  and an honest per-repo scorecard. Centrepieces: the PhD theorem
  ([`lean-sabidussi`](https://github.com/RaggedR/lean-sabidussi)) and the AI-trust
  formalizations ([`trust-boundaries`](https://github.com/RaggedR/trust-boundaries),
  [`trajectory-tracing`](https://github.com/RaggedR/trajectory-tracing)).
- **[Expository writing index →](expository.md)** — the prose behind the proofs, grouped
  by what each piece *demonstrates* for a security reader: cryptography and formal
  methods first, mathematical depth as the foundation.

And two program narratives — how the pieces fit together, not just what they are:
- **[The formal-verification program →](verification.md)** — thesis → machine-checked
  theorem (`lean-sabidussi`) → a local Mathlib development.
- **[The container-theory program →](containers.md)** — a Lean-verified comonad spine
  (`macbeth-seed`, `social-network`) → a dozen applied instances.
- **[Live demos →](demos.md)** — the browser-runnable pieces (GPU physics, generative
  geometry, interactive math), one click each.

---

## Category directory

Every public repository, grouped, strongest/most-relevant first. Claims are stated to
match what the code actually shows.

### 1 · Formal verification & machine-checked proof — see the [Lean index](lean.md) · [program narrative](verification.md)
| Repo | What it is |
|------|------------|
| [lean-sabidussi](https://github.com/RaggedR/lean-sabidussi) | PhD theorem (symmetric graphs ⟷ Hecke algebras), Lean 4, 0 `sorry`, axiom-checked. |
| [lean-hopf-algebras](https://github.com/RaggedR/lean-hopf-algebras) | Hopf algebras and the umbral calculus in Lean 4 / Mathlib (PARTIAL — honest split). |
| [warnaar-glue](https://github.com/RaggedR/warnaar-glue) | Lean glue for Warnaar's A₂ cylindric-partition positivity; `sorry`-free. |
| [trust-boundaries](https://github.com/RaggedR/trust-boundaries) | Per-agent trust-level algebra — zero axioms. |
| [trajectory-tracing](https://github.com/RaggedR/trajectory-tracing) | Epistemic-honesty formalism; `sorry`-free. |
| [social-network](https://github.com/RaggedR/social-network) | Directed-container comonad laws (Haskell + Lean). |
| [symmetric-graphs](https://github.com/RaggedR/symmetric-graphs) | Per-graph Hecke algebras + example catalogue — companion to `lean-sabidussi`. |
| [continued-fractions](https://github.com/RaggedR/continued-fractions) | Legendre's palindrome / √n (STATED — honestly unbuilt). |

### 2 · Cryptography, randomness & number theory
| Repo | What it is |
|------|------------|
| [homomorphic-encryption](https://github.com/RaggedR/homomorphic-encryption) | Paillier homomorphic encryption + Schnorr zero-knowledge proofs, from scratch. |
| [watermark-rs](https://github.com/RaggedR/watermark-rs) | Legendre-sequence spread-spectrum watermarking in the DFT domain (C++). |
| [watermark-attack](https://github.com/RaggedR/watermark-attack) | Diffusion-based attack pipeline vs invisible watermarks (Tree-Ring, Stable Signature, SynthID). |
| [polynomial-primes](https://github.com/RaggedR/polynomial-primes) | Galois theory, irreducibility, Bunyakovsky — the algebra under public-key crypto. |
| [category](https://github.com/RaggedR/category) | A Martin-Löf randomness test that pseudorandom generators provably fail. |

### 3 · Trustworthy & interpretable machine learning
| Repo | What it is |
|------|------------|
| [rsk-transformer](https://github.com/RaggedR/rsk-transformer) | 100% exact inverse RSK (n=10), 99.99% at n=15; mechanistic-interpretability probes of how it computes. |
| [octopus-streams](https://github.com/RaggedR/octopus-streams) | Mechanistic interpretability of transformers via RSK (Pythia-70m). |
| [bijection-transformer-interpretability](https://github.com/RaggedR/bijection-transformer-interpretability) | SAE causal interventions; learning combinatorial bijections. |
| [rsk-manifold-microscope](https://github.com/RaggedR/rsk-manifold-microscope) | The RSK transformer as a manifold microscope. |
| [embeddings](https://github.com/RaggedR/embeddings) | Math-retrieval embedder beating OpenAI `text-embedding-3-small` (MRR 0.816 vs 0.461). |
| [clip-explorer](https://github.com/RaggedR/clip-explorer) | CLIP zero-shot scoring with interactive UMAP. |

### 4 · Autonomous agents & verified reasoning
| Repo | What it is |
|------|------------|
| [warnaar-loop-experiment](https://github.com/RaggedR/warnaar-loop-experiment) | A loop of amnesiac AI agents attacking an open positivity conjecture (Warnaar / Corteel–Dousse–Uncu); produced new partial results (Q₁ case, Adjugate Monomial Theorem). Full conjecture still open. |
| [toy-agent-harness](https://github.com/RaggedR/toy-agent-harness) | A minimal autonomous agent harness — essay + working code. |
| [orchestration](https://github.com/RaggedR/orchestration) | LLM topology-diversity experiments; a sign-flip result via contravariant Kan extensions. |
| [mathematical-systems](https://github.com/RaggedR/mathematical-systems) | Why communication topology, not the fitness landscape, governs multi-agent diversity. |

### 5 · Knowledge representation & retrieval
| Repo | What it is |
|------|------------|
| [description-logic-owl](https://github.com/RaggedR/description-logic-owl) | The logic under ontologies and automated reasoning. |
| [torah-embed](https://github.com/RaggedR/torah-embed) | Talmud retrieval from a centuries-old hand-curated relevance apparatus (Sefaria data, CC-BY-NC). |
| [embeddings](https://github.com/RaggedR/embeddings) | Knowledge-graph-guided fine-tuning of an embedding model (see §3). |

### 6 · Compositional systems modeling (directed containers) — see the [container-theory program](containers.md)
| Repo | What it is |
|------|------------|
| [macbeth-seed](https://github.com/RaggedR/macbeth-seed) | The Lean-verified container spine (proven/stated split — see the Lean index). |
| [category-of-containers](https://github.com/RaggedR/category-of-containers) | The category of containers as a compositional foundation. |
| [supply-chains](https://github.com/RaggedR/supply-chains) · [federation](https://github.com/RaggedR/federation) · [org-chart](https://github.com/RaggedR/org-chart) · [firm](https://github.com/RaggedR/firm) · [stalin](https://github.com/RaggedR/stalin) · [voting](https://github.com/RaggedR/voting) · [three-dates](https://github.com/RaggedR/three-dates) · [dungeon](https://github.com/RaggedR/dungeon) | One categorical idea applied across a supply chain, a federation, an org-chart, a firm, a famine economy, a vote, a dating scenario, a dungeon. |
| [category-theory-you-already-know](https://github.com/RaggedR/category-theory-you-already-know) | A programmer's on-ramp to category theory. |

### 7 · Algebraic combinatorics & representation theory
| Repo | What it is |
|------|------------|
| [hecke-algebras](https://github.com/RaggedR/hecke-algebras) | My doctoral area — representation theory on the double-coset structure. |
| [puzzles](https://github.com/RaggedR/puzzles) | KTW puzzle triangles, Littlewood-Richardson coefficients, Hopf coproduct via transfer operators. |
| [tableaux-mosaics](https://github.com/RaggedR/tableaux-mosaics) | Tableaux, mosaics, and q-analogues. |

### 8 · q-series, symmetric functions & positivity
| Repo | What it is |
|------|------------|
| [cylindric-partitions](https://github.com/RaggedR/cylindric-partitions) | Cylindric partitions and the Warnaar positivity program. |
| [umbral-calculus](https://github.com/RaggedR/umbral-calculus) | Rota's finite operator (umbral) calculus. |
| [haskell](https://github.com/RaggedR/haskell) | q-series algebra and symmetric functions — lazy power series, McIlroy streaming multiplication. |
| [q-bool](https://github.com/RaggedR/q-bool) | q-analogues of Boolean structures. |

### 9 · Game AI & evolutionary methods
| Repo | What it is |
|------|------------|
| [nonaga](https://github.com/RaggedR/nonaga) | A 14-weight genetic algorithm beats a 570K-parameter AlphaZero net 89% of the time. |
| [connect_four](https://github.com/RaggedR/connect_four) | AlphaZero wins head-to-head, but the GA plays better moves per a perfect solver. |
| [blokus](https://github.com/RaggedR/blokus) | Blokus AI — GA heuristics, AlphaZero pipeline, web UI *(collaboration)*. |
| [checkers](https://github.com/lyra-claude/checkers) | TD(λ) self-play, after Samuel's 1959 program. |
| [categorical-evolution](https://github.com/lyra-claude/categorical-evolution) | **GECCO 2026** — GA operators composed as Kleisli morphisms; topology determines diversity. |
| [evolve-evolution-strategy](https://github.com/lyra-claude/evolve-evolution-strategy) | Meta-evolution of migration graphs on deceptive landscapes. |
| [Topology-experiments](https://github.com/lyra-claude/Topology-experiments) | Spectral analysis of migration topologies for island-model GAs (Haskell). |

### 10 · GPU & creative coding — all live, see the [demos index](demos.md)
| Repo | What it is |
|------|------------|
| [smoke-flow](https://github.com/RaggedR/smoke-flow) | Real-time GPU smoke: laminar→turbulent via Navier–Stokes ([live](https://raggedr.github.io/smoke-flow/)). |
| [fire](https://github.com/RaggedR/fire) | Real-time browser fire: buoyant Navier–Stokes + vorticity + combustion ([live](https://raggedr.github.io/fire/)). |
| [reaction-diffusion-screensaver](https://github.com/RaggedR/reaction-diffusion-screensaver) | Music-reactive Gray–Scott reaction–diffusion ([live](https://raggedr.github.io/reaction-diffusion-screensaver/)). |
| [belt-trick](https://github.com/RaggedR/belt-trick) | The Dirac belt trick in 3D — why spinors need 720° (SU(2), Three.js) ([live](https://raggedr.github.io/belt-trick/)). |
| [stomachion](https://github.com/RaggedR/stomachion) | Archimedes' Stomachion — interactive exact-cover puzzle solver ([live](https://raggedr.github.io/stomachion/)). |
| [dancing](https://github.com/RaggedR/dancing) · [kaleidescope](https://github.com/RaggedR/kaleidescope) · [hexstar](https://github.com/RaggedR/hexstar) · [dmt](https://github.com/RaggedR/dmt) · [screen-saver](https://github.com/RaggedR/screen-saver) | More generative / geometric demos — all live (see the [demos index](demos.md)). |
| [sturmian-monster](https://github.com/RaggedR/sturmian-monster) | Sturmian words and continued-fraction structure (Haskell). |

### 11 · Expository writing & essays — see the [expository index](expository.md)
| Repo | What it is |
|------|------------|
| [kerry-questions](https://github.com/RaggedR/kerry-questions) | Information-geometry and LLM-geometry essays. |
| [pde-notes](https://github.com/RaggedR/pde-notes) · [langlands](https://github.com/RaggedR/langlands) · [ml-math-notes](https://github.com/RaggedR/ml-math-notes) | Applied-analysis, Langlands, and ML-mathematics notes. |
| [medium-articles](https://github.com/lyra-claude/medium-articles) | Essays on AI architecture and autonomous agent systems. |

### 12 · Data & finance
| Repo | What it is |
|------|------------|
| [crypto](https://github.com/RaggedR/crypto) | Crypto-currency / commodities momentum trading (a bookmaker fair-price model). |

### 13 · Books & long-form
| Repo | What it is |
|------|------------|
| [steel-book](https://github.com/RaggedR/steel-book) | *The Iron Thread* — a 75,000-word narrative history of steel through civilizations. |

### 14 · Published results & talks
| Repo | What it is |
|------|------------|
| [categorical-evolution](https://github.com/lyra-claude/categorical-evolution) | GECCO 2026: "Composition Determines Diversity." |
| [gecco-2026-talk](https://github.com/lyra-claude/gecco-2026-talk) | Slide deck and per-slide narration for the GECCO 2026 talk. |

### 15 · Infrastructure & tooling
| Repo | What it is |
|------|------------|
| [personal-assistant](https://github.com/RaggedR/personal-assistant) | A CLI for mail, calendar, contacts and messaging — the `pa`/`wa` tools. |

---

*PhD in mathematics (symmetric graphs and Hecke algebras). Trained models are published
as HuggingFace model cards:
[math-embed](https://huggingface.co/RobBobin/math-embed) (math retrieval, MRR 0.816),
[torah-embed](https://huggingface.co/RobBobin/torah-embed) (Talmud retrieval),
[rsk-transformer](https://huggingface.co/RobBobin/rsk-transformer) (inverse RSK, 100%
exact). **Every headline result is verifiable** — the [Lean index](lean.md) tells you
exactly what is machine-checked and what is merely stated, and the
[expository index](expository.md) is the prose behind it.*
