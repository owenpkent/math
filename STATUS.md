# Status snapshot

A per-problem current-state summary. For the authoritative, always-current view,
read each repo's own `STATE_OF_THE_PROGRAM.md` and `PHASE_STATE.md`.

## Birch and Swinnerton-Dyer
- **Status**: Open. Posture is "attacking it."
- **Where it stands**: Phase 0 infrastructure in place. Candidate proof
  architectures laid out with wrong-approach detectors to keep claims honest.
  Deep phases require expert collaborators and multi-year work.

## Hodge Conjecture
- **Status**: Open.
- **Where it stands**: Scaffolding and testbed experiments in place. The two
  known counterexamples (integral Hodge, Kahler Hodge) are wired in as
  structural wrong-approach detectors.

## Navier-Stokes Existence and Smoothness
- **Status**: Open.
- **Where it stands**: Scaffolding and experimental controls in place. Deep
  analytic work (the supercriticality obstruction) requires expert
  collaborators and sustained effort.

## P versus NP
- **Status**: Open.
- **Where it stands**: Research codebase organized around candidate proof
  architectures and the three barrier theorems (relativization, natural proofs,
  algebrization) that discipline every approach.

## Poincare Conjecture
- **Status**: SOLVED (Grigori Perelman, arXiv preprints 2002-2003, building on
  Hamilton's Ricci flow). Independently verified by Kleiner-Lott, Morgan-Tian,
  Cao-Zhu.
- **Where it stands**: Repo posture is understand, reconstruct, and formally
  verify the known proof, and map the still-open generalizations (notably the
  smooth 4D Poincare conjecture).

## Riemann Hypothesis (zeta function)
- **Status**: Open.
- **Where it stands**: ~50-70% of Phase 0 done. Four candidate RH proof
  architectures laid out; experimental thread tests them. Phases 1-5 require
  expert collaborators and multi-year compute.

## Yang-Mills Existence and Mass Gap
- **Status**: Open. Posture is "trying to solve this."
- **Where it stands**: Phase 0 (infrastructure + landscape) largely built.
  Construction phases require expert collaborators and serious compute. The
  central difficulty: generate the infrared mass gap while keeping the
  continuum limit nontrivial.

## Hadwiger-Nelson (chromatic number of the plane)
- **Status**: Open. Best known bounds: `5 <= chi(R^2) <= 7`.
- **Where it stands**: The most computationally active of the set. Four threads:
  - **Combinatorial / unit-distance-graph (SAT)**: `chi >= 4` Lean-verified
    (Moser spindle); `chi >= 5` multi-solver SAT-verified on the de Grey 1585
    graph and smaller graphs; ongoing search for a chi-6 construction, currently
    blocked by a sharpened cocircularity / UDG-realizability barrier.
  - **Measurable / spectral**: `chi_m >= 5` (Falconer) is best known; `chi_m >= 6`
    is open. Multi-class moment LP built; reduced to one prerequisite (a custom
    sparse conic backend), no new bound yet.
  - **Fractional / Lovasz theta**: reproduced and self-certified Ambrus 2023,
    giving integer `chi_m >= 5`; LP density route capped at `>= 5`.
  - **Set-theoretic / axiomatic**: Shelah-Soifer phenomenon dossier; the 2003
    conditional was made vacuous by de Grey 2018.
