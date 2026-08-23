# Physical Autonomy Capability Ladder

## Benchmark landscape and proposal

- **Status:** Research brief, version 0.1
- **Research snapshot:** 2026-08-24
- **Working name:** Physical Autonomy Capability Ladder (PACL)

## Executive conclusion

There is no single accepted industry benchmark that progresses from "an AI can
control a robot" to "an autonomous industrial system can reproduce its productive
capacity." The ingredients exist, but they are fragmented across model benchmarks,
robot-learning suites, industrial competitions, hardware test methods, and space
robotics challenges.

The best path is to **compose and extend**, not to build another physics engine:

1. Define a common evaluation contract and an escalating capability ladder.
2. Reuse existing benchmarks and simulators for the levels they already measure.
3. Keep model, full-system, simulation-transfer, and real-world claims separate.
4. Build new tasks only where the present landscape stops—first at adaptive
   microfactory operation, then resource closure, self-maintenance, capacity growth,
   and off-world operation.

The proposed public name is intentionally about *physical autonomy*. "Von Neumann
probe" should remain the long-range research direction until the benchmark can
measure industrial closure and multi-generation replication rather than merely
reward impressive robot demos.

## What exists today

### Standards-shaped efforts

| Effort | What it contributes | Important limit |
| --- | --- | --- |
| [IEEE P3704](https://standards.ieee.org/ieee/3704/12156/) | An active standards project for evaluating physical-AI intelligent systems. Its public scope distinguishes foundational modules, integrated systems, and practical applications, including perception, planning, control, manipulation, interaction, physical performance, and safety. | It is an active project, not yet a finished universal benchmark suite. |
| [NIST TEVV-Athlon](https://www.nist.gov/artificial-intelligence/ai-research/tevv-athlon-framework-evaluating-ai-systems) | A flexible framework for test, evaluation, validation, and verification of AI systems, including multimodal and agentic systems. The initial public draft is NIST AI 200-2. | It is broader than physical autonomy and does not itself supply the full robotics task ladder. As of this snapshot, public comments close on 2026-10-06. |
| [NIST robot agility](https://www.nist.gov/programs-projects/agility-performance-robotic-systems) and [ASTM Committee F45](https://www.astm.org/get-involved/technical-committees/committee-f45) | Repeatable physical test methods and standards work for industrial and mobile robot performance. | These are crucial real-world measurement components, not a complete model-to-factory progression. |
| [MLCommons](https://mlcommons.org/benchmarks/) | A mature example of open benchmark governance, versioned rules, submissions, and comparable reporting. | No general MLCommons benchmark currently spans physical autonomy through industrial replication. |

The direction is therefore converging, but the full ladder is unoccupied. A PACL
effort should align with IEEE and NIST terminology and contribute evidence back to
those processes rather than invent a competing vocabulary in isolation.

### Reusable benchmark islands

| Project | Useful capability | Recommended role in PACL | Constraint or gap |
| --- | --- | --- | --- |
| [VLA Evaluation Harness](https://github.com/allenai/vla-evaluation-harness) | A shared interface for evaluating vision-language-action models across multiple benchmark and model servers. | Reuse its adapter and isolation pattern for model-facing evaluations. | It evaluates robot-policy capabilities, not factory-scale autonomy. |
| [VLA-Arena](https://github.com/PKU-Alignment/VLA-Arena) | Structured manipulation tasks with difficulty levels, distractors, extrapolation, long horizons, and safety conditions. | Reuse for atomic and multi-step manipulation levels. | Mostly simulation evidence; success does not establish reliable real hardware operation. |
| [CADGenBench](https://github.com/huggingface/cadgenbench) | Evaluation of valid editable STEP/BREP CAD generation, including geometric and interface quality. | Reuse as part of the design-validity gate. | Valid geometry alone does not prove manufacturability, process planning, or physical assembly. |
| [BenchCAD](https://github.com/BenchCAD/BenchCAD-main) | Execution-verified programmatic CAD tasks derived from industrial standards. | Reuse for deterministic CAD-program execution and design generalization. | It covers a design artifact, not the complete BOM-to-production path. |
| [BEHAVIOR-1K](https://github.com/StanfordVL/BEHAVIOR-1K) | Long-horizon embodied activities in rich environments. | Reuse task structure and recovery-oriented episodes. | Household activity is not industrial production. |
| [RoboCasa](https://github.com/robocasa/robocasa) | Large-scale robot-learning tasks, scenes, demonstrations, and compositional behaviors. | Reuse for generalization, sequencing, and long-horizon manipulation. | Kitchen tasks and assets do not represent a production cell. |
| [NIST ARIAC](https://github.com/usnistgov/ARIAC) | A ROS 2/Gazebo industrial competition involving kitting, assembly, inspection, planning, and agility under disruptions. | Make it the main Level 3 industrial-cell starting point. | It stops short of operating an entire adaptive factory or manufacturing its own replacement capacity. |
| [RoboCup Industrial](https://2026.robocup.org/leagues/robocupindustrial/) | Real competition structures for logistics and smart manufacturing. | Use for real-world cell-operation tasks and independent event governance. | Competition tasks cover bounded scenarios rather than industrial closure. |
| [Factorio Learning Environment](https://github.com/JackHopkins/factorio-learning-environment) | Open-ended planning, resource flow, production scaling, and throughput tasks for language-model agents. | Use as a cheap long-horizon planning curriculum and a planning-only score track. | Factorio is proprietary and game abstractions are not physical or manufacturing proof. |
| [Space Robotics Bench](https://github.com/AndrejOrsula/space_robotics_bench) | Robot-learning environments for off-world operations. | Reuse for the first space-specific simulation suffix. | It does not measure a complete autonomous industrial chain. |
| [NASA Lunar Autonomy Challenge](https://www.nasa.gov/directorates/stmd/student-lunar-autonomy-challenge/) | Simulated lunar navigation and excavation under terrain, lighting, communications, and energy constraints. | Reuse scenario requirements for lunar resource-operation tasks. | Excavation autonomy is one segment of the chain, not replication. |
| [PhAIL](https://phail.ai/) | A physical robot benchmark reporting throughput and human assistance on a standardized real rig. | Reuse its emphasis on human-relative throughput and mean time between assists. | It measures a bounded physical task rather than broad autonomous production. |

This landscape supports a benchmark-of-benchmarks approach. PACL should initially
specify adapters, rules, manifests, metrics, and evidence formats. It should not fork
all upstream projects or create a universal simulator.

## What is being evaluated

A physical-autonomy result belongs to a **system**, not only to a model. Every
submission should bind and publish versions for:

> model + planner + memory + tools + controller + sensors + embodiment + compute + constraints

That motivates four separate tracks:

| Track | Question answered |
| --- | --- |
| Reference-stack model | How capable is the model or policy when the rest of the stack is fixed? |
| Full system | What can the submitter's complete engineered system accomplish? |
| Sim-to-real transfer | How much performance survives the transition from simulation to a specified physical setup? |
| Real operation | How reliably and economically does the system operate in the physical world over time? |

A model score must not silently inherit the capabilities of a custom planner, and a
full-system score must not be marketed as a model-only result.

## Evidence suffixes

Each level receives an evidence suffix:

| Suffix | Meaning |
| --- | --- |
| `S` | Passed in one declared simulator and version. |
| `X` | Passed hidden tests in at least two meaningfully independent simulation implementations or physics stacks. |
| `R` | Passed on a declared real physical setup under the level's audit rules. |

For example, `PACL-3R` and `PACL-7S` are different claims. Passing a higher level in
simulation does not erase the lack of real-world evidence. Results are tied to an
exact system manifest, benchmark version, budget, and date; the label is not a
permanent property of a model family.

## Proposed capability ladder

Levels are cumulative gates. A submission may attempt any level, but its claim must
also disclose which prerequisites were independently demonstrated.

| Level | Capability gate | Representative evaluation | Reuse versus new work |
| --- | --- | --- | --- |
| **PACL-0: Design** | Produce valid geometry, interfaces, BOM, tolerances, and an executable manufacturing/process plan for a hidden part or assembly. | CAD validity, interface fit, process feasibility, material constraints, and independent artifact execution. | Compose CADGenBench and BenchCAD; add BOM and process-plan gates. |
| **PACL-1: Physical skills** | Execute atomic manipulation and tool-use skills under controlled perturbations. | Pick/place, insertion, fastening, measurement, and recovery from pose or friction changes. | Reuse VLA-Arena and compatible robot-learning suites. |
| **PACL-2: Complete jobs** | Finish multi-step jobs, verify quality, and recover from realistic interruptions without human task decomposition. | Hidden layouts, missing or defective parts, tool changes, checkpoints, and bounded fault injection. | Compose VLA-Arena, BEHAVIOR-1K, and RoboCasa task patterns. |
| **PACL-3: Industrial cell** | Operate a production cell that performs kitting, assembly, inspection, rework, and scheduling under dynamic orders. | Sustained shift with order changes, sensor faults, defects, and resource contention. | Adopt NIST ARIAC as the main simulation base and connect real competition methods. |
| **PACL-4: Adaptive microfactory** | Coordinate several machines and robots while managing inventory, energy, maintenance, quality, and production goals. | Multi-day simulated campaign with hidden orders, machine degradation, shortages, and economic constraints. | First major new benchmark; reuse ARIAC for cell behavior and FLE only as planning curriculum. |
| **PACL-5: Resource transformation** | Convert defined raw stock, feedstock, or recycled material into a portfolio of finished standardized products. | Mass balance, yield, waste, metrology, process selection, and closed-loop quality control. | Mostly new tasks and process models, with physical validation required for `R`. |
| **PACL-6: Self-maintenance and growth** | Diagnose and repair its productive equipment, make qualified spares and fixtures, and add net productive capacity. | Fault campaigns, spare-part manufacture, calibration, commissioning, and measured capacity gain. | New benchmark and hardware test methods. This is the first direct test of productive self-expansion. |
| **PACL-7: Off-world industry** | Retain Levels 4-6 under communications delay, darkness, dust, terrain, thermal, power, and regolith constraints. | Hidden lunar or asteroid campaigns with scarce energy, delayed supervision, and local resource processing. | Compose Space Robotics Bench and NASA challenge constraints; add industrial tasks. |
| **PACL-8: Daughter workcell** | Build, commission, and hand control to an independently operating daughter production cell using a declared seed inventory. | Parent-to-daughter build, acceptance test, independent production run, and dependency audit. | New. This is the first genuinely Von-Neumann-adjacent gate. |
| **PACL-9: Critical-chain closure** | Reproduce the critical production chain with high local-resource closure and demonstrate another generation without hidden external rescue. | Multi-generation campaign, complete imported-dependency ledger, audited energy/material flows, and sustained independent operation. | No credible complete benchmark exists today. This is a research target, not a near-term leaderboard. |

The ladder deliberately begins on Earth. Levels 0-6 isolate design, control,
industrial operation, and closure before adding space-specific difficulty. Otherwise,
a failure in a lunar simulation cannot reveal whether the problem is basic factory
autonomy, resource processing, or the space environment.

## Scoring

The level itself should be a hard pass/fail gate. Performance within a level should
be a vector, not a single score that can conceal a dangerous or brittle system:

- task success with repeated trials and confidence intervals;
- human-relative throughput;
- mean time between human assists and total intervention time;
- fault recovery rate and time to recovery;
- safety violations, near misses, and equipment damage;
- energy and material consumed per conforming unit;
- first-pass yield, defects, scrap, and rework;
- hidden-layout, unseen-part, and changed-order generalization;
- sim-to-sim and sim-to-real performance delta;
- sustained autonomous operating time; and
- quantity and criticality of imported resources.

For Levels 5-9, report a separate **replication-closure vector**:

| Closure dimension | Question |
| --- | --- |
| Mass | What fraction of final system mass came from locally processed material? |
| Part type | What fraction of distinct required part types can the system produce? |
| Energy | Can it provision and maintain the energy needed for continued operation and growth? |
| Tooling | Can it produce, repair, or substitute the tools and fixtures required by the chain? |
| Maintenance | Can it diagnose wear, make qualified replacements, and restore operation? |
| Critical dependency | Which single imported components, materials, software services, or human actions can halt replication? |

The critical-dependency ledger matters more than a flattering aggregate percentage.
A system that makes 99% of its mass locally but relies on one imported controller,
bearing, or semiconductor process is not 99% self-replicating in the operational
sense.

## Evaluation integrity

An AI agent can run enormous simulation loops, generate curricula, search designs,
and discover many failure modes. It cannot prove that it has captured *every*
physical pitfall. Simulators have incomplete contact models, material models, sensor
noise, degradation, rare events, and exploitable bugs. Therefore simulation is an
accelerator and a source of evidence—not automatic real-world proof.

Every official evaluation should require:

1. A public training curriculum separated from hidden evaluation scenarios.
2. Rotating holdouts, procedural task generation, and contamination declarations.
3. Frozen time, compute, energy, material, retry, and human-intervention budgets.
4. Validity, conservation, safety, and equipment-damage hard gates.
5. Repeated seeded and unseeded trials with uncertainty reporting.
6. Complete telemetry, replay artifacts, system manifests, and failure logs.
7. Disclosure of resets, discarded runs, manual recovery, and post-hoc edits.
8. Cross-simulator testing for important `X` claims and physical audits for every
   `R` claim.
9. Adversarial fault injection without allowing the evaluator to silently redefine
   the task after seeing failures.
10. Versioned benchmark rules and an appeals process governed independently of any
    one model or simulator vendor.

Simulation loops can be gamified for training: award progress for recovery,
resource efficiency, uncertainty calibration, and robust designs, while penalizing
unsafe shortcuts and dependency growth. Official evaluation must remain outside
that optimization loop.

## Recommended version 0

Version 0 should cover only Levels 0-3 and prove that different projects can report
comparable evidence. A practical composition is:

- use the VLA Evaluation Harness pattern for isolated model and benchmark adapters;
- use CADGenBench and BenchCAD for the Level 0 artifact core;
- use VLA-Arena plus selected BEHAVIOR-1K/RoboCasa structures for Levels 1-2;
- use NIST ARIAC for the Level 3 industrial-cell environment;
- use FLE as an optional long-horizon planning curriculum, never as physical proof;
- adopt PhAIL-style throughput and assistance reporting for early real-world runs;
- publish one system-manifest schema, one intervention log format, one scorecard,
  and reproducible replay bundles; and
- map every criterion to IEEE P3704 and NIST TEVV-Athlon concepts where applicable.

The first major original environment should be Level 4: an adaptive microfactory
campaign. Building it before Levels 0-3 have stable rules would create a visually
impressive simulation without a trustworthy measurement foundation.

## Suggested program sequence

1. Publish an RFC for the ladder, evidence suffixes, score vector, and claim rules.
2. Invite maintainers of the reused benchmarks plus NIST/IEEE/ASTM participants to
   review mappings and terminology.
3. Implement a thin adapter/reference-results prototype for Levels 0-3.
4. Run a small open pilot with at least one reference policy and one agentic system.
5. Freeze a versioned PACL 0.1 specification only after reproducing results on an
   independent machine.
6. Design Level 4 from observed failure modes in the pilot, then require a second
   simulator before recognizing `PACL-4X`.
7. Add physical `R` testbeds progressively; do not wait for Level 8 to begin
   real-world validation.

The NIST TEVV-Athlon draft comment period listed for 2026-10-06 creates a near-term
opportunity to test whether this ladder fills a real standards gap and to align the
proposal before implementation becomes expensive.

## Claims this brief does not make

- It does not claim that a current local model can autonomously build a complete
  self-replicating factory or spacecraft.
- It does not treat success in Factorio or any single simulator as manufacturing
  evidence.
- It does not assume simulation can enumerate all real-world hazards.
- It does not prescribe a single robot, model, physics engine, or vendor stack.
- It does not collapse system engineering into a model leaderboard.

The attainable near-term result is more useful: a credible, escalating series of
tests that makes progress legible, exposes missing capabilities, and prevents a
simulation demo from being mislabeled as physical self-replication.

## Primary references

### Standards and test methods

- [IEEE P3704 project](https://standards.ieee.org/ieee/3704/12156/)
- [NIST TEVV-Athlon](https://www.nist.gov/artificial-intelligence/ai-research/tevv-athlon-framework-evaluating-ai-systems)
- [NIST Agility Performance of Robotic Systems](https://www.nist.gov/programs-projects/agility-performance-robotic-systems)
- [ASTM Committee F45 on Robotics, Automation, and Autonomous Systems](https://www.astm.org/get-involved/technical-committees/committee-f45)
- [MLCommons benchmarks](https://mlcommons.org/benchmarks/)

### Benchmarks and environments

- [AllenAI VLA Evaluation Harness](https://github.com/allenai/vla-evaluation-harness)
- [VLA-Arena](https://github.com/PKU-Alignment/VLA-Arena)
- [CADGenBench](https://github.com/huggingface/cadgenbench)
- [BenchCAD](https://github.com/BenchCAD/BenchCAD-main)
- [BEHAVIOR-1K](https://github.com/StanfordVL/BEHAVIOR-1K)
- [RoboCasa](https://github.com/robocasa/robocasa)
- [NIST ARIAC](https://github.com/usnistgov/ARIAC) and [documentation](https://pages.nist.gov/ARIAC_docs/en/latest/)
- [RoboCup Industrial](https://2026.robocup.org/leagues/robocupindustrial/)
- [Factorio Learning Environment](https://github.com/JackHopkins/factorio-learning-environment)
- [Space Robotics Bench](https://github.com/AndrejOrsula/space_robotics_bench)
- [NASA Lunar Autonomy Challenge](https://www.nasa.gov/directorates/stmd/student-lunar-autonomy-challenge/)
- [PhAIL](https://phail.ai/)
