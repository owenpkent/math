# Which Millennium problems are most AI-amenable

A cross-cutting survey of the current state (2024-2026) of AI and machine
learning work on the unsolved Millennium Prize Problems, and a ranked assessment
of which are most likely to be solved or substantially advanced by AI.

This is a research snapshot, not a claim about any repo in this index. Sources
are cited inline; several load-bearing references are recent, non-peer-reviewed
arXiv preprints and are flagged as such. Last compiled 2026-06-05.

## Headline

As of mid-2026, no Millennium Prize Problem has been solved or substantially
proved by AI, and the Clay Institute has accepted no resolution. AI's real
contribution so far is to accelerate discovery, numerical search, and
pattern-finding, not to produce proofs of the major conjectures
(Dean & Naibo, *Philosophia Mathematica* 2025, arXiv:2408.03345). The problems
separate cleanly by how much AI traction actually exists today.

## Ranking

| Rank | Problem | AI status |
|------|---------|-----------|
| 1 | **Navier-Stokes** | Active, concrete results (DeepMind PINNs, computer-assisted nonuniqueness proof). The blow-up route fits AI search. |
| 2 | **Birch and Swinnerton-Dyer** | Active, data-driven (murmurations, ~95% analytic-rank prediction). Some patterns now made rigorous. |
| 3-5 | **Riemann / Yang-Mills / Hodge** | Little to no direct AI activity. No obvious numerical search target or labeled dataset. |
| 6 | **P vs NP** | Least amenable: proven barrier theorems rule out current technique families; LLMs fail at SAT reasoning. |

## 1. Navier-Stokes Existence and Smoothness

The most AI-active of the set, by a wide margin, via the blow-up / singularity
route. Finding any finite-time singularity *is* the unsolved problem, and the
field believes no stable singularities exist for boundary-free 3D Euler and
Navier-Stokes, so unstable singularities are the hypothesized blow-up mechanism.
AI is well-suited to hunting unstable objects that are hard to reach by hand.

- **DeepMind unstable-singularity discovery (Sept 2025).** A Google DeepMind
  team with Buckmaster (NYU), Gomez-Serrano (Brown), and Lai (Stanford) used
  physics-informed neural networks (PINNs) plus a high-precision full-matrix
  Gauss-Newton optimizer to achieve the "first systematic discovery of new
  families of unstable singularities" across fluid equations (IPM, Boussinesq,
  CCF). Sources: arXiv:2509.14185; DeepMind blog "Discovering new solutions to
  century-old problems in fluid dynamics"; *Physics World* coverage.
- **Computer-assisted nonuniqueness proof (2025-26).** Hou, Wang, Yang give the
  first rigorous computer-assisted proof of nonuniqueness of Leray-Hopf
  solutions to the *unforced* incompressible 3D Navier-Stokes equations, harder
  than the 2022 forced-case result of Albritton-Brue-Colombo. Source:
  arXiv:2509.25116 (submitted Sep 2025, revised Mar 2026).
- **Tao's program.** AI search is conceptually aligned with Terence Tao's 2019
  "approximately discretely self-similar fluid computer" blow-up program
  (terrytao.wordpress.com, 2019), which postdates AI methods that now pursue the
  same target.

**Caveats.** The singularities were found in IPM, CCF, Boussinesq, and Euler
*with a boundary*, not in the boundary-free 3D Euler / Navier-Stokes that the
Millennium problem concerns. For CCF the team improved precision on already-known
solutions rather than finding a new family. Some researchers (e.g. Hassanzadeh)
question whether the numerical blow-ups are genuine or self-regularizing. None of
this resolves the Millennium regularity / existence problem.

## 2. Birch and Swinnerton-Dyer Conjecture

The most data-driven problem and second most AI-active. ML literally discovered a
new phenomenon here.

- **Murmurations.** Rank-dependent oscillations in the average Frobenius trace
  `a_p` over elliptic curves as the prime `p` varies, first spotted accidentally
  during an ML classification assignment. Source: arXiv:2204.10140 (He, Lee,
  Oliver, Pozdnyakov), published in *Experimental Mathematics* 2024; *Quanta*
  "Elliptic Curve Murmurations Found With AI," March 2024.
- **Generalization and rank prediction.** ML (PCA, LDA, CNNs) predicts the
  vanishing order / analytic rank of rational L-functions at ~95% accuracy across
  ~248k L-functions; murmuration-like patterns appear across broad L-function
  families. Source: arXiv:2502.10360 (Bieri et al., Feb 2025).
- **Deeper invariants (medium confidence).** A March 2026 preprint ties the order
  of the Tate-Shafarevich group |Sha| to murmuration shape on ~3M Cremona curves.
  Source: arXiv:2603.04604. Single recent unreviewed preprint; treat as an
  empirical statistical observation, not a theorem. A related claim that ML
  predicts |Sha| directly from Frobenius vectors did not survive verification.

**Caveats.** These are empirical / data-science advances, not proofs. The most
promising signal is that some patterns have been made rigorous (Zubrilina's
GL(2) murmuration density theorem; Sarnak's general framework), showing the
AI-found patterns can convert into real theorems. "Vanishing order = rank" is
rigorous for elliptic curves but conjectural in general (BSD /
Beilinson-Bloch-Kato).

## 3-5. Riemann Hypothesis, Yang-Mills mass gap, Hodge Conjecture

The survey turned up no direct AI breakthroughs on any of these three. The
Riemann Hypothesis is tangentially touched by the L-function ML work above.

The "least AI-amenable" label here is an inference from absence of evidence, not
a proven negative. Plausibly these simply lack an AI-friendly handle: no
numerical search target, no labeled dataset, no exploitable combinatorial
structure. This is the weakest-supported part of the ranking and the most likely
to change with more research attention.

## 6. P versus NP

The research argues this is the least AI-amenable, for two concrete reasons.

- **Proven proof barriers.** Relativization, natural proofs, and the
  Aaronson-Wigderson algebrization barrier are theorems showing that entire
  families of current techniques (arithmetization plus diagonalization) provably
  cannot resolve P vs NP. Source: Aaronson-Wigderson, "Algebrization: A New
  Barrier in Complexity Theory," STOC'08 / ACM ToCT'09. Recent work
  (Chen-Hu-Ren, arXiv:2511.14038, ITCS'26) extends and reinforces the barrier
  rather than overturning it. This is a stronger negative than "we lack ideas":
  the ideas we have are ruled out.
- **LLMs do not reason about SAT.** On random 3-SAT, non-reasoning LLMs (GPT-4o,
  Claude 3.7 Sonnet, Gemini 2.0 Flash, DeepSeek V3) collapse to ~10% accuracy in
  the hard region near the satisfiability threshold (alpha_c ~ 4.267), indicating
  reliance on statistical shortcuts rather than multi-step reasoning. Source:
  arXiv:2504.03930 (Hazra et al., COLM 2025).

**Nuance.** These two points concern different things (proving the meta-theorem
vs. solving SAT instances), but together they make P vs NP the hardest target for
current AI.

## Context: AI theorem-proving capability

- **AlphaProof** (AlphaZero-style RL in Lean, Gemini-based autoformalization)
  reached IMO 2024 silver-medal level: 28 points, solving formal proofs for P1,
  P2, and P6 (P6 solved by only 5 of ~600 human contestants). Source: *Nature*
  2025, s41586-025-09833-y. It required human Lean translation and up to ~3 days
  of compute vs. the human 4.5-hour limit, and has since been surpassed on broad
  benchmarks (Seed-Prover, Goedel-Prover-V2). Gemini Deep Think later reached
  gold at IMO 2025.
- This is olympiad and formalization capability, not research-level conjecturing.
  Benchmarks such as FrontierMath (epoch.ai) confirm a large gap between contest
  math and frontier research math.

## Bottom line

If you are betting on AI involvement in a *first* resolution, Navier-Stokes (via
an AI-found singularity later proved rigorous) and BSD (via data-driven number
theory) are the only two with live momentum. Even there, the realistic role is AI
as a collaborator that finds a construction or pattern, with humans supplying the
proof.

Two reliability notes carried from the underlying research:

1. Several load-bearing sources are recent, non-peer-reviewed preprints (the
   |Sha|-murmuration result especially).
2. The "least amenable" verdict for Riemann, Yang-Mills, and Hodge rests on
   absence of evidence rather than a positive finding.

## Open questions

- Will AI-discovered unstable singularities in boundary cases transfer to the
  boundary-free 3D Euler / Navier-Stokes setting the Millennium problem requires,
  and are the numerically-found blow-ups genuine or self-regularizing?
- Can the empirical murmuration and ML rank/|Sha|-prediction results be converted
  into rigorous theorems that advance BSD itself, beyond Zubrilina's GL(2) result
  and Sarnak's framework?
- What concrete expert timelines exist for AI substantially advancing any
  specific Millennium problem? (Timeline coverage in the source pass was thin;
  Metaculus and Manifold markets exist but were not deeply mined.)
- Is the low AI activity on Riemann, Yang-Mills, and Hodge due to a genuine lack
  of AI-amenable structure, or simply less research attention to date?

## Primary sources

- arXiv:2509.14185 - DeepMind, unstable singularities in fluid equations (PINNs + Gauss-Newton)
- arXiv:2509.25116 - Hou, Wang, Yang, computer-assisted nonuniqueness, unforced 3D Navier-Stokes
- terrytao.wordpress.com (2019) - Tao, "Searching for singularities in the Navier-Stokes equations"
- arXiv:2204.10140 - He, Lee, Oliver, Pozdnyakov, "Murmurations of elliptic curves"
- arXiv:2502.10360 - Bieri et al., ML prediction of L-function vanishing order
- arXiv:2603.04604 - Wachs, |Sha| modulation of murmuration shape (medium confidence)
- Aaronson-Wigderson, "Algebrization: A New Barrier in Complexity Theory" (STOC'08)
- arXiv:2504.03930 - Hazra et al., LLM reasoning via 3-SAT phase transition (COLM 2025)
- Nature s41586-025-09833-y - AlphaProof, olympiad-level formal reasoning with RL
- arXiv:2408.03345 - Dean & Naibo, "Artificial intelligence and inherent mathematical difficulty"
