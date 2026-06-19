# BridgeBeat

An interactive walkthrough of a vehicle-bridge interaction and Bridge Weigh-in-Motion model.

**Live demo:** https://bypire.github.io/bridgebeat/

Five sections:

1. **Weigh.** A truck crosses a bridge. The deck deflects by less than a millimetre, and that
   deflection, measured at a single point, recovers the truck's weight while it is moving (Bridge
   Weigh-in-Motion). Increasing the speed increases the dynamic amplification and the recovery error.
2. **Diagnose.** A loss of stiffness lowers the bridge's natural frequency. Increasing the damage
   moves the spectral peak to a lower frequency, which a passing vehicle can detect without sensors
   on the bridge.
3. **Real data.** The measured natural frequency of the KW51 bridge (Leuven), recorded daily for
   sixteen months and coloured by deck temperature. A retrofit in 2019 raises the frequency by about
   two percent.
4. **Why it matters.** Fatigue damage scales with roughly the cube to fourth power of axle load, so
   a small overloaded minority causes most of the wear, and B-WIM identifies those trucks.
5. **A viaduct under traffic.** A 500 m multi-span viaduct carrying a stream of cars and trucks,
   with a running tally of load, overloads, and accumulated fatigue cost.

## Under the hood

This is the front end for a 2D vehicle-bridge interaction and B-WIM model: an Euler-Bernoulli beam
finite-element model (consistent mass and stiffness, Rayleigh damping), a quarter-car coupling, RK4
and Newmark-beta integration, and a Moses, Tikhonov-regularised, and Bayesian inverse for the axle
weights. It is verified against closed-form references (Frýba, modal frequencies) and validated
against the measured KW51 monitoring dataset. The numpy-only physics core is in a separate
repository.

## Data

Derived data only; no raw monitoring records. The KW51 tracked modal frequencies are from Maes and
Lombaert, *Monitoring data for railway bridge KW51*, Zenodo 3745914.
