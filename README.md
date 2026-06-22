# Admissibility Monitor

Detecting pre-collapse instability in AI systems via admissibility geometry and multi-view consistency.

## Paper

**Detecting Pre-Collapse Instability in AI Systems via Admissibility Geometry and Multi-View Consistency**  
Gabe Hospelhorn, 2026

This paper introduces an admissibility-based observability framework for detecting instability in AI systems before degradation appears in output behavior.

## Core Idea

Current AI governance frameworks often monitor what models do:

- accuracy
- loss
- reward
- benchmark behavior
- audit outcomes

This work proposes monitoring the geometry of model representations instead.

A system need not be failing to be unstable; it need only become inconsistent across distinct observational views.

## Contribution

The paper introduces:

- a Lyapunov-like admissibility potential `Phi`
- a geometric state signal `DeltaPhi`
- a dynamical flow signal `dPhi/dt`
- a multi-view consistency condition
- a novel failure mode: **parallax instability**
- a noise-aware conjunctive detection protocol

## Parallax Instability

Parallax instability occurs when a system remains admissible in aggregate while becoming inconsistent across distinct observational frames:

- representational
- functional
- perturbational

This can appear before separatrix crossing and before observable performance degradation.

## Interactive Artifact

The interactive monitor is available here:

https://gabehospelhorn.github.io/constraint-geometry/admissibility-monitor.html

The interactive monitor for reorganization is available here:

https://gabehospelhorn.github.io/constraint-geometry/reorganization-vs-collapse.html

## Monitoring Architecture

| Layer | Signal | Question |
|---|---|---|
| Geometry | `DeltaPhi(t)` | Where is the system relative to the boundary? |
| Dynamics | `dPhi/dt` | Is it moving toward or away from instability? |
| Coherence | `Pi_norm(t), S(t)` | Do observational frames agree? |
| Robustness | `sigma_Phi, c, k` | Is the signal real? |

## Status

This repository accompanies the arXiv paper and supplementary artifact.

The simulation is constructive rather than empirical. It demonstrates ordering:

```text
t_Pi < t* < t_perf
