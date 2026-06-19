# BridgeBeat

**Weigh a moving truck, diagnose hidden damage, and watch a real bridge get repaired —
from vibration alone.**

**Live demo:** https://bypire.github.io/bridgebeat/

A 4-act interactive story:

1. **Weigh** — a truck crosses a bridge; the deck barely sags, but that sag weighs the
   truck while it rolls (Bridge Weigh-in-Motion). Push the speed up and watch the
   dynamic error grow.
2. **Diagnose** — hidden damage softens the bridge, so it vibrates a little slower.
   Slide the damage up and watch its "note" drop.
3. **Real** — not a simulation: the real natural frequency of the **KW51 bridge**
   (Leuven), measured daily for 16 months, drawn like a heart monitor. The pulse steps
   up the day they strengthened it.
4. **Stakes** — fatigue grows with the cube-to-4th power of load, so a small overloaded
   minority does most of the damage — and B-WIM catches exactly those trucks.

## Under the hood

This is the front end for a 2D **vehicle–bridge interaction + B-WIM** engine: an
Euler–Bernoulli beam FEM (consistent M, K, Rayleigh damping), a quarter-car coupling,
RK4 / Newmark-β integration, and a Moses / Tikhonov-regularized / Bayesian inverse —
verified against closed-form references (Frýba, modal frequencies) and **validated
against the real KW51 monitoring dataset**. The numpy-only physics core lives in a
separate repository.

## Data

Derived data only (no raw monitoring records). KW51 tracked modal frequencies are from
Maes & Lombaert, *Monitoring data for railway bridge KW51*, Zenodo 3745914.
