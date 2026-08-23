# Von Neumann Probe

An open research project for measuring progress from AI-assisted design and robot
control toward autonomous factories and, eventually, self-expanding industrial
systems.

The near-term goal is deliberately narrower than a self-replicating spacecraft:
create an evidence-based ladder of increasingly difficult Earth-first evaluations
that can later extend to off-world conditions.

## Current conclusion

A fully autonomous interstellar probe that lands, mines unknown material,
reproduces every required subsystem, and launches complete descendants is not
buildable with demonstrated 2026 technology.

A narrower Solar System seed factory is physically plausible but unproven. It
would manufacture bulk structures and simple mechanisms locally while importing
high-value "vitamin" components such as computers, sensors, power electronics,
precision bearings, batteries, and metrology references.

Current local models can support perception, planning, diagnosis, experiment
generation, and bounded design iteration. They should not be the unrestricted
flight controller, safety authority, or sole operator of an autonomous factory.

## Research

- [Physical Autonomy Capability Ladder: benchmark landscape and proposal](research/physical-autonomy-capability-ladder.md)
- [2026 feasibility and simulation-first synthesis](research/2026-08-24-feasibility-and-simulation-synthesis.md)

## Recommended first experiment

Build a terrestrial simulation beta in which an AI must design and control a
mining unit, collect feedstock, manufacture parts, and produce a second
independently controllable unit.

Use an engine-neutral action and observation contract. A proprietary engineering
game such as Space Engineers can provide the fastest playable prototype, while
open simulators such as Genesis, MuJoCo, Open Industry Project, SimPy, and Project
Chrono provide the durable validation path.

## Evidence boundary

This repository records research and proposed validation gates. It does not establish:

- a working self-replicating system;
- engineering or numerical accuracy of any simulator;
- flight, release, runtime, or customer readiness;
- adopted mission architecture;
- permission to deploy autonomous replication hardware.

The cited sources remain authoritative for their own claims. Estimates and scores
in the synthesis are explicitly labeled as judgment or planning ranges.
