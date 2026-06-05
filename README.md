# math

A high-level index of my mathematics problem repos. Each problem lives in its
own standalone repository (its own git history and GitHub remote); this repo is
the landing page that ties them together.

Every problem repo follows the same "deep study repo" structure: a layered set
of explanations from intuitive through research level (`docs/`), a computational
experimental thread (`experiments/`), Lean formalization (`lean/`), a reference
library (`sources/`, `references/`), and an operational layer that runs each one
as an AI-augmented research program (`STATE_OF_THE_PROGRAM.md`, `OPERATIONS.md`,
`PHASE_STATE.md`).

## The problems

| # | Problem | Repo | Millennium? | Posture |
|---|---------|------|:-----------:|---------|
| 1 | Birch and Swinnerton-Dyer Conjecture | [birch-swinnerton-dyer](https://github.com/owenpkent/birch-swinnerton-dyer) | Yes | Open. Attacking it. Phase 0 infrastructure in place. |
| 2 | Hodge Conjecture | [hodge-conjecture](https://github.com/owenpkent/hodge-conjecture) | Yes | Open. Scaffolding + testbed experiments in place. |
| 3 | Navier-Stokes Existence and Smoothness | [navier-stokes-smoothness](https://github.com/owenpkent/navier-stokes-smoothness) | Yes | Open. Scaffolding + experimental controls in place. |
| 4 | P versus NP | [p-vs-np](https://github.com/owenpkent/p-vs-np) | Yes | Open. Research codebase across candidate architectures. |
| 5 | Poincare Conjecture | [poincare-conjecture](https://github.com/owenpkent/poincare-conjecture) | Yes | Solved (Perelman, 2002-03). Comprehension + formalization. |
| 6 | Riemann Hypothesis (Riemann zeta function) | [zeta-function](https://github.com/owenpkent/zeta-function) | Yes | Open. ~50-70% of Phase 0 done. |
| 7 | Yang-Mills Existence and Mass Gap | [yang-mills-mass-gap](https://github.com/owenpkent/yang-mills-mass-gap) | Yes | Open. Attacking it. Phase 0 largely built. |
| 8 | Hadwiger-Nelson (chromatic number of the plane) | [hadwiger-nelson](https://github.com/owenpkent/hadwiger-nelson) | No | Open. `5 <= chi(R^2) <= 7`. Active SAT + Lean + spectral threads. |

Seven of the eight are Clay Millennium Prize Problems, and all seven are
tracked above. The full Millennium set is: Birch and Swinnerton-Dyer, Hodge,
Navier-Stokes, P vs NP, Poincare (solved), Riemann Hypothesis (the zeta
function repo), and Yang-Mills.

Hadwiger-Nelson is not a Millennium problem but is included as an active
open problem in combinatorial geometry.

## One-line summaries

- **Birch and Swinnerton-Dyer**: relates the rank of an elliptic curve's group
  of rational points to the order of vanishing of its L-function at `s = 1`.
- **Hodge**: on a projective complex manifold, every Hodge class is a rational
  combination of the classes of algebraic cycles.
- **Navier-Stokes**: do smooth, globally defined solutions to the 3D
  incompressible Navier-Stokes equations always exist, or can they blow up?
- **P vs NP**: is every problem whose solution can be verified quickly also
  solvable quickly?
- **Poincare**: every simply connected closed 3-manifold is homeomorphic to the
  3-sphere. Proved by Perelman via Hamilton's Ricci flow with surgery.
- **Riemann Hypothesis**: all nontrivial zeros of the Riemann zeta function lie
  on the critical line `Re(s) = 1/2`.
- **Yang-Mills mass gap**: prove a nontrivial quantum Yang-Mills theory exists
  on R^4 and has a strictly positive mass gap.
- **Hadwiger-Nelson**: the smallest number of colors needed to color the plane
  so no two points exactly distance 1 apart share a color.

## Layout of each repo

```
<problem>/
  docs/            # Layered explanations: 00_intuitive -> 03_research
  experiments/     # Computational thread (PLAN.md, LEARNINGS.md, code)
  lean/            # Formal verification
  sources/         # Reference library (papers, notes)
  references/      # Citations and reading notes
  visualizations/  # Figures and animations
  README.md
  STATE_OF_THE_PROGRAM.md   # One-page strategic snapshot
  OPERATIONS.md             # How to operate the program
  PHASE_STATE.md            # Current state
```

See [STATUS.md](STATUS.md) for a fuller current-state snapshot per problem, and
[AI_AMENABILITY.md](AI_AMENABILITY.md) for a 2024-2026 survey of which Millennium
problems are most likely to be advanced by AI.
