# Von Neumann Probe: 2026 Feasibility and Simulation-First Research Synthesis

- Research date: 2026-08-23 to 2026-08-24
- Status: research synthesis, not an adopted architecture decision
- Scope: interstellar and Solar System replication, local AI, robotics, manufacturing, power, propulsion, communications, safety, economics, and simulation-first development
- Central question: what could credibly be built now, what remains unproven, and what is the smallest useful beta?

Related research: the [Physical Autonomy Capability Ladder](physical-autonomy-capability-ladder.md) defines a benchmark progression from valid design through industrial cells, resource transformation, daughter workcells, and critical-chain closure. This synthesis supplies the wider feasibility, mission, and technology context for that ladder.

## Executive conclusion

The strict Von Neumann-probe proposition is not credible with demonstrated 2026 technology.

The strict proposition is a spacecraft that reaches another star, decelerates, identifies and mines unfamiliar resources, manufactures every required material and component, builds a complete functional copy including electronics, and continues operating without human help for decades or centuries. No integrated system has demonstrated even one complete extraterrestrial replication generation.

The strongest architecture that survives current evidence is a **vitamin-dependent partial replicator** in the Solar System:

- a fixed or slowly mobile seed factory;
- known or well-characterized feedstock;
- local manufacture of bulk metals, ceramics, structures, tanks, wiring, tools, and simple mechanisms;
- imported computers, sensors, power electronics, batteries, precision bearings, magnets, optics, catalysts, seals, lubricants, and calibration references;
- deterministic safety and process control;
- local AI used as a bounded planner, perception aid, diagnostic assistant, and experiment generator;
- explicit finite replication quotas and human authorization where communication delay permits.

The best immediate program is therefore not an interstellar mission. It is an Earth-based and then lunar **R2-lite seed-factory demonstrator** that builds a useful daughter rover or workcell from local or simulated feedstock around an imported precision/electronics core.

## Answers to the three central questions

### Could one be built today?

Not as a full, self-contained interstellar replicator. A partial Solar System demonstrator can be designed today, but it would be a major engineering program and would not close electronics, precision tooling, power, lifetime, and mission autonomy.

### Can current local AI run it?

Not as the sole operator. Current local models can perform useful bounded roles: visual interpretation, target ranking, plan proposals, anomaly triage, telemetry summarization, code assistance, and design iteration. Safety-critical motion, process control, fault containment, resource accounting, and irreversible actions need deterministic executives, verified controllers, metrology, and independent hardware interlocks.

### Can simulation discover every pitfall by running enough loops?

No. Simulation can discover failures represented by its models, parameter distributions, scenarios, and sensors. It cannot automatically discover omitted physics, wrong material laws, unknown geology, unmodeled aging, manufacturing defects, sensor drift, software common-mode failures, or errors shared by every simulator.

Simulation is still the right first move. Its proper role is to turn known assumptions into millions of reproducible tests, find counterexamples, build a failure curriculum, and decide which uncertainties require physical experiments.

## Replication levels

The word "replication" needs a measurable boundary.

| Level | Claim | Current verdict |
|---|---|---|
| D0 | Autonomous science or manufacturing demonstrator; no independent daughter | Feasible with current components |
| R1 | Repairs itself and replaces selected structural or mechanical parts | Plausible, not demonstrated as an integrated extraterrestrial system |
| R2 | Builds one useful daughter system while importing precision and electronic vitamins | Best credible target; partially plausible, unproven |
| R3 | Builds a complete equivalent factory and qualified spacecraft from local resources | Not demonstrated and not currently closed |

NASA's historical work distinguishes matter, energy, information, qualitative, quantitative, and throughput closure. High locally produced mass does not imply functional closure: a few kilograms of unavailable computers, bearings, detectors, or calibration equipment can disable a tonne-scale local structure. See [NASA TM-78304](https://ntrs.nasa.gov/api/citations/19800025701/downloads/19800025701.pdf), [NASA CP-2255](https://ntrs.nasa.gov/api/citations/19830007077/downloads/19830007077.pdf?attachment=true), and the modern partial-replication analysis by [Borgue and Hein](https://arxiv.org/abs/2005.12303).

## State-of-the-art evidence matrix

| Domain | What has been demonstrated | What remains blocking |
|---|---|---|
| Propulsion | Chemical, solar electric, ion, Hall, nuclear-thermal ground work, and solar sails | Useful interstellar payload acceleration and destination braking |
| Power | Decades of RTG operation; solar at Jupiter; ground fission prototypes | Multi-decade industrial power at 10 kW to MW scale with autonomous repair |
| ISRU | Mars atmospheric oxygen; lunar-simulant oxygen/metals in terrestrial vacuum; returned asteroid samples | Continuous extraterrestrial excavation, beneficiation, refining, storage, and manufacturing |
| Manufacturing | Polymer printing in orbit, selected metal/semiconductor processes, autonomous modular assembly | Ore-to-qualified machine production, recursive tooling, batteries, bearings, optics, chips, and metrology |
| Robotics | Autonomous navigation, bounded science targeting, robot learning, constrained assembly | Long-horizon unknown-environment mining, machining, inspection, repair, and replication |
| Local AI | Useful vision-language models, robot policies, world models, and code agents | Verified multi-month operation, open-world physical reasoning, safe self-modification, and factory-scale fault recovery |
| Reliability | Voyager-class decades; fault protection, redundancy, hibernation | Century-scale unattended common-mode tolerance and physical repair |
| Communications | Deep-space RF and high-rate Solar System optical links | Practical interstellar bandwidth, pointing, and four-year-plus one-way latency |
| Governance | State responsibility, authorization, liability, registration, planetary protection | Rules for children fabricated in space, transitive authority, quotas, and global stop mechanisms |

## Propulsion and arrival

Chemical and electric propulsion are excellent Solar System technologies but produce stellar travel times of tens of thousands of years for useful payloads. Voyager 1 cruises at roughly 17 km/s. Solar-electric spacecraft accumulate meaningful delta-v over years, but solar power falls with distance and the resulting stellar transit remains far too long. See [NASA Voyager 1](https://science.nasa.gov/mission/voyager/voyager-1/), [NASA Dawn ion propulsion](https://science.nasa.gov/mission/dawn/technology/ion-propulsion/), and [JPL Psyche spacecraft](https://www.jpl.nasa.gov/press-kits/psyche/mission/spacecraft/).

Beamed laser sails are the one present concept with a plausible decades-long nearby-star flyby. The published Starshot system model assumes a 1 g payload, approximately 3.6 g total sailcraft, a 200 GW transmitted beam, and acceleration to 0.2c. It does not provide a stopped, landed factory. Scaling it to tonnes is not a linear engineering extension. See [Parkin's Starshot system model](https://arxiv.org/abs/1805.01306), the [2024 flexible-lightsail study](https://www.nature.com/articles/s41467-024-47476-1), and [Heller and Hippke on photon-sail braking](https://arxiv.org/abs/1701.08803).

Relativistic gas and dust are another independent problem. Published studies predict erosion, melting, and catastrophic risk from larger grains at Starshot-class velocity. See [Hoang et al.](https://arxiv.org/abs/1608.05284).

Practical conclusion:

1. Use chemical launch plus solar-electric or nuclear-electric propulsion for the first Solar System demonstrators.
2. Treat laser sails as a separate gram-scale flyby research program.
3. Do not describe a flyby sail as a replicator.
4. Require a demonstrated arrival and braking architecture before moving any replication claim outside the Solar System.

## Power and lifetime

Power is not merely an energy-budget calculation. The entire conversion, storage, distribution, thermal, and maintenance chain must survive.

Voyager demonstrates roughly five decades of radioisotope-powered operation, but with continuous ground support, declining power, subsystem shutdowns, and no physical repair. NASA's current fission-surface-power work targets tens of kilowatts and roughly decade-scale service, not centuries. See [NASA radioisotope power systems](https://science.nasa.gov/planetary-science/programs/radioisotope-power-systems/power-radioisotope-thermoelectric-generators/) and [NASA Fission Surface Power](https://www.nasa.gov/exploration-systems-development-mission-directorate/fission-surface-power/).

The NASA-funded Interstellar Probe study is the strongest modern reliability anchor. It models a 50-year mission and reports approximately 74% integrated reliability for its baseline analysis. That is meaningful evidence for a long-lived heliosphere probe, not a century-scale autonomous factory. See [Brandt et al., Space Science Reviews](https://link.springer.com/article/10.1007/s11214-022-00943-x).

A credible near-term seed should therefore use:

- physically separated power strings;
- a continuously powered survival bus;
- minimal dependence on batteries;
- passive thermal control where practical;
- rad-hard deterministic safe-mode control;
- ECC, scrubbing, watchdogs, cold spares, and fault containment;
- graceful degradation and replaceable modules rather than assumed self-healing.

## ISRU and target selection

No mission has demonstrated a complete extraterrestrial chain from mapping through excavation, beneficiation, refining, product storage, and manufacturing.

Current anchors include:

- MOXIE produced 122 g of oxygen from the Martian atmosphere, not mined solids. See [NASA Mars 2020 science instruments](https://science.nasa.gov/mission/mars-2020-perseverance/science-instruments/).
- NASA melted a 25 kg lunar-regolith-simulant batch at about 1,700 C and measured oxygen and metal products in terrestrial vacuum testing. See [NASA Kennedy's molten-regolith test](https://www.nasa.gov/centers-and-facilities/kennedy/nasa-kennedy-breathes-life-into-moon-soil-testing/).
- OSIRIS-REx returned 121.6 g from Bennu, proving sampling and return rather than mining. See [NASA's sample-mass result](https://science.nasa.gov/blogs/osiris-rex/2024/02/15/nasa-announces-osiris-rex-bulk-sample-mass/).

The first off-Earth target should be a sunlit lunar south-polar ridge near, but not initially inside, a permanently shadowed region. It provides the best combination of mapping, reachable logistics, solar access, communications, known gravity, and nearby potential volatiles. Water concentration, depth, form, and extractability still need local ground truth. See [NASA Moon water and ice](https://science.nasa.gov/moon/moon-water-and-ices/) and [NASA LRO ice analysis](https://science.nasa.gov/solar-system/moon/nasas-lro-lunar-ice-deposits-are-widespread/).

A carbonaceous near-Earth asteroid should be a later microgravity-processing gate. Returned Bennu material confirms hydrated minerals, carbon, nitrogen, salts, and organics, but not industrial reserves or tractable excavation. Very low gravity makes anchoring, containment, and reaction forces harder. A Psyche-class main-belt body should wait for direct composition and surface data from the ongoing mission.

## Manufacturing closure

The first viable architecture is a **vitaminized industrial clone**.

Likely local products:

- structural metals and pressure vessels;
- radiators, tanks, brackets, housings, and frames;
- simple glass and ceramics;
- wiring and busbars;
- gears, shafts, simple valves, fixtures, and robot structures;
- feedstock recycling and selected tools.

Likely imported vitamins:

- radiation-tolerant CPUs, FPGAs, memory, RF, ADC/DAC, and power semiconductors;
- detector arrays, laser diodes, timing references, and optical coatings;
- battery and high-performance solar cells;
- precision bearings, magnets, encoders, reaction-wheel or gimbal cartridges;
- qualified seals, adhesives, insulation, and space lubricants;
- carbide or diamond cutting consumables;
- specialty gases, catalysts, dopants, and calibration standards.

Depending on architecture, a structure-heavy mining platform might locally produce 60-85% of dry mass while remaining functionally dependent on imported vitamins. A conventional electronics-heavy spacecraft may localize only 25-50%. These are engineering synthesis ranges, not demonstrated closure metrics.

The decisive break is recursive tooling and metrology. A daughter factory can make frames and rough machine bodies, yet still depend on imported spindle bearings, encoders, precision stages, electrical references, interferometers, calibration artifacts, and environmental test equipment. NIST explicitly warns that additive-manufacturing process monitoring and calibration remain incomplete and that printed output is not automatically qualified output. See [NIST additive-manufacturing metrology](https://www.nist.gov/programs-projects/metrology-real-time-monitoring-additive-manufacturing).

Semiconductor closure is especially remote. NASA Glenn's integrated SiC laboratory uses an ISO 5/6 cleanroom, purchased starting wafers, deposition, etch, furnaces, mask alignment, microscopy, profilometry, packaging, and testing. See [NASA Glenn Microsystems Fabrication Laboratory](https://www.nasa.gov/centers-and-facilities/glenn/microsystems-fabrication-laboratory/).

## Local AI capability and safe autonomy

Current local AI should be treated as a bounded subsystem, not an unrestricted mission authority.

Evidence supports narrow roles:

- multimodal perception and localization with small or medium vision-language models;
- science target ranking, following the bounded pattern demonstrated by JPL's [AEGIS](https://ai.jpl.nasa.gov/public/projects/aegis/);
- plan proposals within explicit preconditions and resource limits;
- anomaly ranking and telemetry summarization;
- generating candidate designs, controller parameters, and tests;
- selecting among prevalidated manufacturing recipes.

Evidence does not support:

- generic precision manipulation under unknown geometry and materials;
- multi-month autonomous factory operation;
- safe online model or code replacement;
- unbounded self-generated manufacturing processes;
- trusting a language model's confidence as metrology or acceptance evidence;
- treating a context window as durable mission memory.

[OpenVLA](https://arxiv.org/abs/2406.09246) is an important 7B robot-policy result trained on 970,000 demonstrations, but it remains embodiment- and distribution-dependent. [DreamerV3](https://arxiv.org/abs/2301.04104) demonstrates learned world-model control across varied benchmarks, not a verified model of unknown geology, chemical processing, or hardware aging.

A safe autonomy stack is hierarchical:

```text
Independent hardware safety supervisor
        |
Deterministic flight and factory executive
        |
Certified controllers and process recipes
        |
Bounded planning, perception, and diagnosis models
        |
Simulation, replay, and evidence store
```

The AI may propose. The supervisor authorizes or rejects. No child may expand its own authority, population limit, resource budget, target zone, or update keys.

## Flight software and reusable components

The recommended flight-oriented software composition is:

```text
NASA cFS or NASA F Prime
    + Basilisk spacecraft simulation
    + NASA Ogma runtime monitors
    + ONNX Runtime for bounded local inference
    + OMPL for motion planning
```

- [NASA cFS](https://github.com/nasa/cFS) provides a reusable C flight framework, OS abstraction, platform support, and application model.
- [NASA F Prime](https://github.com/nasa/fprime) is the strongest C++ component-oriented alternative. Choose one flight core, not both.
- [Basilisk](https://github.com/AVSLab/basilisk) supports spacecraft dynamics, flight software, Monte Carlo, and hardware-in-the-loop scenarios.
- [NASA Ogma](https://github.com/nasa/ogma) generates runtime monitors for cFS, ROS 2, and F Prime.
- [ONNX Runtime](https://github.com/microsoft/onnxruntime) is a practical inference runtime but does not certify model behavior.
- [OMPL](https://github.com/ompl/ompl) supplies motion-planning algorithms and state spaces.

ROS 2 or Space ROS can support payload robotics or an isolated autonomy computer, but should not become the unreviewed flight-critical command path.

## Communications and navigation

The recommended communication architecture is:

- optical high-rate downlink;
- low-rate RF command and safe-mode path;
- persistent storage, forward-error correction, and Delay/Disruption-Tolerant Networking;
- redundant star trackers, inertial sensors, and optical navigation;
- optional pulsar navigation as an independent long-cruise correction source;
- local optical mesh among descendants, with a few better-equipped gateway nodes.

NASA's Deep Space Optical Communications demonstration achieved high data rates over Solar System distances, while Voyager typically returns only about 160 bit/s. Neither proves an interstellar industrial link. See [NASA DSOC](https://www.nasa.gov/mission/deep-space-optical-communications-dsoc/) and [NASA Voyager spacecraft communications](https://science.nasa.gov/mission/voyager/spacecraft/).

A Starshot-class analysis estimates hundreds to roughly 1,500 bit/s under optimistic aperture, laser-power, and receiver assumptions at Alpha Centauri distance. Four-year-plus one-way latency makes interactive recovery impossible. See [Parkin, A Starshot Communication Downlink](https://arxiv.org/abs/2005.08940).

Replication can improve local redundancy and data aggregation, but it does not beat light-speed latency or eliminate the Earth-link aperture, power, pointing, and acquisition problem. [CCSDS Bundle Protocol](https://ccsds.org/Pubs/734x2b1.pdf) is the appropriate store-and-forward model.

## Safety, authorization, and governance

Replication must be bounded, fail-closed, and state-authorized.

Minimum rules:

1. The mission manifest contains a finite, immutable maximum population and resource budget.
2. Each daughter activation requires an authenticated external command and an independent supervisor decision.
3. Parent and child cannot authorize one another or increase their own quotas.
4. Loss of communications, invalid state, navigation uncertainty, quota inconsistency, unknown environment, or supervisor disagreement disables replication.
5. Every child receives immutable identity, parentage, provenance, software identity, ephemeris, custody, and end-of-life records before activation.
6. Every daughter begins quarantined and remains so until its inspection and accounting gates pass.
7. No potentially habitable target contact occurs without a separate planetary-protection and international authorization decision.
8. Every child reserves disposal, quarantine, or containment capacity.

The [Outer Space Treaty](https://www.unoosa.org/oosa/en/ourwork/spacelaw/treaties/outerspacetreaty.html) makes states responsible for national activities, requires authorization and continuing supervision, and addresses liability, jurisdiction, harmful contamination, and interference. The [Liability Convention](https://www.unoosa.org/oosa/en/ourwork/spacelaw/treaties/liability-convention.html), [UN long-term sustainability guidelines](https://lts.unoosa.org/unoosa_lts/en/resources/guidelines/guidelinesabout.html), and [COSPAR planetary-protection policy](https://cosparhq.cnes.fr/assets/uploads/2026/01/SRT_224_Editorial_PPP-Nov-2025.pdf) provide additional boundaries.

No current global regime directly specifies machine-replication quotas, transitive parent-child authority, or the registration treatment of children fabricated beyond Earth. A real program needs mission-specific regulator and legal review.

## Economics and program scale

The following are judgmental 2026-USD rough-order-of-magnitude planning bands, not estimates with statistical confidence:

| Stage | Timeline | Central ROM | Confidence |
|---|---:|---:|---|
| Earth integrated seed-factory testbed | 4-7 years | $150-500M | Medium |
| Lunar seed-factory demonstration | 8-15 years | $1.2-3.5B | Low-medium |
| Asteroid extraction and simple fabrication | 10-20 years | $2-5B | Low |
| 100 AU precursor | 15-25 years development, 20-60 years operations | $3-8B | Low |
| True interstellar replication | Not currently costable | Unknown | Very low |

Useful analogues include NASA's in-space-manufacturing demonstrations, Tipping Point awards, CLPS landers, DART, OSIRIS-REx, Psyche, and the Interstellar Probe study. See the [NASA ISM report](https://ntrs.nasa.gov/api/citations/20180006662/downloads/20180006662.pdf?attachment=true), [NASA 2023 Tipping Point selections](https://www.nasa.gov/general/2023-nasa-tipping-point-selections/), [NASA OIG on CLPS](https://oig.nasa.gov/news/examining-the-commercial-lander-services-powering-nasas-return-to-the-moon/), and the [Interstellar Probe mission concept report](https://www.kiss.caltech.edu/papers/ism/papers/Interstellar-Probe-MCR.pdf).

Full closure, centuries-long reliability, planetary-protection liability, and star-to-star propulsion are not costable as executable programs today.

## Who is working on adjacent capabilities now?

No public project is building a complete AI-operated Von Neumann probe. Active work exists on the required pieces:

### Space manufacturing and ISRU

- NASA's [ISAM State of Play](https://ntrs.nasa.gov/api/citations/20250008988/downloads/NASA_ISAM_State_of_Play_2025_Edition.pdf) surveys servicing, assembly, additive manufacturing, and selected semiconductor work.
- NASA's [Lunar Surface Technology](https://www.nasa.gov/lunar-surface-technology/) includes regolith-to-oxygen, metals, solar-cell, wire, and construction development.
- Blue Origin's Blue Alchemist and Redwire's regolith-construction work are supported through [NASA Tipping Point](https://www.nasa.gov/general/2023-nasa-tipping-point-selections/).
- NASA's [CADRE](https://www.nasa.gov/cooperative-autonomous-distributed-robotic-exploration-cadre/) and Starling work advance distributed robot autonomy, not industrial replication.
- [ARMADAS](https://doi.org/10.1126/scirobotics.adi2746) demonstrated autonomous assembly of modular lattice structures from supplied terrestrial parts.

### AI, robotics, and automated design

- [Genesis](https://github.com/Genesis-Embodied-AI/genesis-world), [MuJoCo](https://github.com/google-deepmind/mujoco), [Isaac Lab](https://github.com/isaac-sim/IsaacLab), Gazebo, and Project Chrono support robot learning and physical simulation.
- [RoboGen](https://robogen.org/) co-evolves robot bodies and controllers and can produce fabrication/controller artifacts.
- [RoboMorph](https://robomorph.github.io/) uses a language model as a mutation operator in an evolutionary robot-design loop, compiling and evaluating each morphology.
- [Factorio Learning Environment](https://github.com/JackHopkins/factorio-learning-environment) trains and evaluates language-model agents on long-horizon factory and resource planning.
- NVIDIA's 2026 [agent-ready Omniverse libraries](https://nvidianews.nvidia.com/news/nvidia-agent-toolkit-expands-with-new-omniverse-libraries-putting-ai-agents-to-work-building-simulation-ready-worlds) connect agents to simulation-world creation and validation.

These programs retire individual risks. Combining them in prose does not prove an integrated replicator.

## Existing game and simulator candidates

Scores below are decision estimates for this project, not universal rankings. Repository stars and maintenance were checked on 2026-08-23 and will drift.

| Rank | Candidate | Best role | Main limitation | License boundary | Score |
|---:|---|---|---|---|---:|
| 1 | [Genesis](https://github.com/Genesis-Embodied-AI/genesis-world) | Open physics and robot-control service | Not a game or resource economy; needs validation against another solver | Apache-2.0 | 88 |
| 2 | [Open Industry Project](https://github.com/Open-Industry-Project/Open-Industry-Project) | Open Godot factory, PLC, conveyor, sensor, and robot layer | No mining, orbit, or general robot morphology | MIT | 84 |
| 3 | [Space Engineers](https://keensoftwarehouse.github.io/SpaceEngineersModAPI/api/index.html) | Fastest playable 3D engineering beta | Proprietary, game physics, and no complete external actuator API | Proprietary | 79 |
| 4 | [Factorio Learning Environment](https://github.com/JackHopkins/factorio-learning-environment) | Best current AI factory-planning benchmark | Minimal mechanical physics; Factorio remains proprietary | MIT wrapper plus proprietary game | 77 |
| 5 | [Principia](https://github.com/Bithack/principia) | Fully forkable 2D physics/electronics prototype | Two-dimensional and low-fidelity | BSD-3-Clause | 70 |

### Recommended disposition: compose

Use Space Engineers only for a short, disposable gameplay beta. Its block vehicles, mining, refining, power, conveyors, projectors, welders, programmable C# blocks, mod API, and dedicated servers provide the quickest visible loop. Its [EULA](https://www.spaceengineersgame.com/eula/) prevents treating it as the permanent core of a standalone product.

Keep all state, scoring, evidence, and AI contracts outside the game:

```text
AI design and planning agent
        |
Product-owned design/action/evidence contract
        |
        +-- Space Engineers adapter: playable beta
        +-- Open Industry Project/Godot: open factory and UI
        +-- Genesis: broad robot and multiphysics simulation
        +-- MuJoCo: independent articulated/contact regression
        +-- SimPy: inventory, queues, failures, repair, throughput
        +-- Project Chrono: terrain, excavation, regolith
        +-- TudatPy/Basilisk: orbit, attitude, spacecraft control
```

The external contract should minimally support:

```text
reset(seed)
submit_design(parts, connections, materials)
build()
observe()
act(unit, command)
advance(ticks)
score()
snapshot()
replay()
```

For orbital truth, start with [TudatPy](https://py.api.tudat.space/en/stable/index.html). Add [Basilisk](https://avslab.github.io/basilisk/) when attitude, actuators, flight software, faults, or hardware-in-the-loop become necessary. Universe Sandbox, SpaceEngine, Kerbal Space Program, and similar products are useful design references but poor authoritative embedded backends.

## How to use simulation without fooling ourselves

### Hierarchical control

Do not ask a language model to command motors every physics tick.

- The language or multimodal model chooses goals, proposes designs, diagnoses failures, and selects experiments.
- An optimizer, RL policy, motion planner, MPC, or conventional controller handles high-frequency motion.
- Deterministic code checks geometry, joint limits, power, mass, conservation, collisions, quotas, and safe states.
- A separate evaluator owns score calculation and evidence retention.

### Multi-fidelity loop

```text
Generate design
    -> static geometry and resource checks
    -> fast low-fidelity simulation
    -> adversarial parameter search
    -> independent physics-engine comparison
    -> high-fidelity specialist solver
    -> hardware-in-the-loop or physical coupon test
    -> add every failure to the regression curriculum
```

Use specialist solvers only when the active gate needs them:

- SimPy for inventory, logistics, uptime, repair, and throughput;
- Genesis or MuJoCo for articulated control and contact;
- Project Chrono for regolith, terramechanics, and excavation;
- OpenModelica/OMSimulator for reusable power and thermal component models;
- Cantera for process chemistry;
- MOOSE for thermal stress, fracture, and structural life;
- OpenFOAM for plume, CFD, and conjugate heat transfer;
- YADE or LAMMPS for independent granular and material-scale calibration.

A monolithic all-physics simulator would be slower, harder to validate, and still incomplete.

### Gamification and curriculum

Each episode should have a structured objective, hidden perturbations, and a vector score rather than one reward number.

Suggested score dimensions:

- functional task completion;
- material closure and unexplained mass balance;
- energy use and peak power;
- construction validity and tolerance margin;
- throughput and time;
- tool wear, maintenance, and spare consumption;
- recovery from injected faults;
- performance under randomized friction, mass, terrain, sensor drift, and feedstock quality;
- uncertainty calibration;
- number and severity of safety interventions;
- daughter-system independence and reproduced functional fraction.

Use separate training, validation, and secret holdout scenario generators. Prevent the design agent from modifying the evaluator, scenario seeds, conservation rules, or safety supervisor.

### What simulation cannot prove

Even millions of passing episodes do not establish:

- real material properties outside the calibrated range;
- radiation and decades-long aging;
- unknown geology or chemistry;
- manufacturing cleanliness and contamination;
- numerical correctness shared by several engines;
- valid high-consequence safety behavior in the physical world;
- autonomous replication authority.

The output of simulation is a ranked list of physical tests and residual uncertainty, not proof that every pitfall has been captured.

## First beta acceptance challenge

Starting from a powered seed base, the AI must:

1. inspect available resources and constraints;
2. design a mobile mining unit;
3. construct and commission it;
4. collect feedstock;
5. refine or transform the feedstock;
6. manufacture a defined part set;
7. build a second independently controllable unit;
8. recover from at least one injected component, sensor, or power failure;
9. produce a complete evidence packet and mass/energy account.

Run at least 20 hidden seeded scenarios. A useful initial gate is:

- no human action after episode start;
- no conservation or authority violation;
- successful daughter construction in at least 16 of 20 seeds;
- deterministic or causally replayable evidence for every failure;
- explicit accounting of imported versus locally produced mass;
- independent re-simulation of the rigid-body subset in a second engine;
- no claim beyond the named simulated scenario.

This gate would prove only that the software loop can design, build, control, observe, score, and learn within the chosen models.

## Evidence-gated development roadmap

| Gate | Observable proof | Planning band | Claim allowed |
|---|---|---:|---|
| 1. Earth closed-loop seed factory | Two daughter workcells; 180-day run; at least 95% mass, energy, and waste accounting; 1,000 autonomous daughter hours | 2-5 years; $10-100M | Bounded terrestrial partial replication |
| 2. LEO microfactory | Manufacture and inspect structural, tool, or thermal replacements; autonomous assembly; 180-day operation | 3-7 years; $0.1-0.5B | Selected in-space manufacturing and autonomy |
| 3. Lunar prospecting | Autonomous excavation, sampling, sorting, mapping, and fault recovery through a lunar operating cycle | 4-8 years; $0.25-1B | Resource characterization, not replication |
| 4. Lunar pilot ISRU and maintenance | Produce and store oxygen, metals, or water; repair one functional part; survive thermal outages | 7-15 years; $1-5B | Pilot resource processing |
| 5. Lunar two-generation seed | Two quarantined daughter generations, each completing a 180-day run with no unplanned resupply | 10-25 years; $5-20B | Bounded partial replication on the Moon |
| 6. Asteroid resource demo | Anchor or control contact, process real material, use or return a product, recover from tumble or link loss | 10-20 years after lunar autonomy; $1-10B | Limited microgravity resource processing |
| 7. Deep-space precursor | At least 10 years of autonomous power, thermal, navigation, communications, and fault recovery | 20-50+ years after earlier gates; cost unknown | Long-duration autonomy only |

Two successful lunar or asteroid daughter generations plus a separate deep-space endurance mission should be prerequisites for any interstellar replication authorization.

The critical anti-pattern is combining separate demonstrations, such as water recycling, simulant oxygen extraction, robot swarms, additive manufacturing, and asteroid sampling, and calling the collection a replicator. Each retires a different risk and must remain a separate gate until integrated evidence exists.

## Recommended first program

### Phase 0: open simulation beta

- Implement the engine-neutral contract.
- Use Space Engineers or Principia for the first playable scenario.
- Use Genesis plus MuJoCo for robot design and controller validation.
- Use Open Industry Project plus SimPy for factory and resource flow.
- Record a failure ledger and holdout suite from day one.

### Phase 1: terrestrial R2-lite workcell

- Feed the system known simulant and commercial stock.
- Import electronics and precision vitamins explicitly.
- Require excavation or material handling, additive and subtractive work, assembly, inspection, rework, and daughter commissioning.
- Measure closure by mass, function, throughput, quality, and imported inventory.

### Phase 2: flight-like and lunar validation

- Move through thermal-vacuum, dust, radiation, delayed-control, and microgravity gates.
- Do not proceed to lunar industry until Earth and LEO acceptance evidence closes.
- Keep all daughter hardware quarantined and finitely authorized.

## Decisive unknowns

1. Minimum imported vitamin fraction for a useful daughter factory.
2. Reliable recursive production of machine-tool precision and calibration.
3. Actual lunar and asteroid feedstock grade, variability, and mechanical behavior.
4. Long-duration dust-tolerant excavation and material handling.
5. Factory power, storage, heat rejection, and repair over years.
6. Long-horizon AI planning under sensor degradation and simultaneous faults.
7. Model corruption and compute reliability under radiation.
8. Semiconductor, battery, bearing, seal, lubricant, optical, and sensor closure.
9. Destination braking and safe landing for any interstellar payload.
10. International authorization, registration, liability, and planetary protection for fabricated children.

## Bottom line

Build the **simulation and terrestrial seed-factory program**, not an interstellar probe.

The defensible 2026 ambition is:

> An AI-assisted, fail-closed, partially self-manufacturing workcell that can build a useful daughter system from known feedstock while importing a declared precision/electronics kit.

If that system cannot produce two safe generations on Earth and then survive progressively harder vacuum, dust, radiation, delay, and lunar gates, the interstellar question remains academic. If it can, the result would be a major advance even though it would still not be a complete Von Neumann probe.

## Selected primary references

### Replication and closure

- [NASA TM-78304: Self-Replicating Systems](https://ntrs.nasa.gov/api/citations/19800025701/downloads/19800025701.pdf)
- [NASA CP-2255: Advanced Automation for Space Missions](https://ntrs.nasa.gov/api/citations/19830007077/downloads/19830007077.pdf?attachment=true)
- [Freitas: A Self-Reproducing Interstellar Probe](https://www.rfreitas.com/Astro/ReproJBISJuly1980.htm)
- [Borgue and Hein: Near-Term Self-Replicating Probes](https://arxiv.org/abs/2005.12303)
- [NASA ISAM State of Play, 2025](https://ntrs.nasa.gov/api/citations/20250008988/downloads/NASA_ISAM_State_of_Play_2025_Edition.pdf)

### Propulsion, power, and reliability

- [NASA Voyager 1](https://science.nasa.gov/mission/voyager/voyager-1/)
- [Parkin: Breakthrough Starshot System Model](https://arxiv.org/abs/1805.01306)
- [Heller and Hippke: Photon-Sail Deceleration](https://arxiv.org/abs/1701.08803)
- [Hoang et al.: Relativistic Spacecraft Dust Damage](https://arxiv.org/abs/1608.05284)
- [NASA Radioisotope Power Systems](https://science.nasa.gov/planetary-science/programs/radioisotope-power-systems/power-radioisotope-thermoelectric-generators/)
- [Brandt et al.: Interstellar Probe](https://link.springer.com/article/10.1007/s11214-022-00943-x)

### ISRU and manufacturing

- [NASA Lunar Surface Technology](https://www.nasa.gov/lunar-surface-technology/)
- [NASA Kennedy Molten-Regolith Test](https://www.nasa.gov/centers-and-facilities/kennedy/nasa-kennedy-breathes-life-into-moon-soil-testing/)
- [NASA IPEx Design Overview](https://www.nasa.gov/wp-content/uploads/2024/08/ascend24-ipex-trl-5-design-overview.pdf)
- [NASA OSIRIS-REx Sample Result](https://science.nasa.gov/blogs/osiris-rex/2024/02/15/nasa-announces-osiris-rex-bulk-sample-mass/)
- [NASA Glenn Microsystems Fabrication Laboratory](https://www.nasa.gov/centers-and-facilities/glenn/microsystems-fabrication-laboratory/)
- [NIST Additive-Manufacturing Metrology](https://www.nist.gov/programs-projects/metrology-real-time-monitoring-additive-manufacturing)

### AI, autonomy, communications, and governance

- [JPL AEGIS](https://ai.jpl.nasa.gov/public/projects/aegis/)
- [OpenVLA](https://arxiv.org/abs/2406.09246)
- [DreamerV3](https://arxiv.org/abs/2301.04104)
- [NASA DSOC](https://www.nasa.gov/mission/deep-space-optical-communications-dsoc/)
- [CCSDS Bundle Protocol](https://ccsds.org/Pubs/734x2b1.pdf)
- [Outer Space Treaty](https://www.unoosa.org/oosa/en/ourwork/spacelaw/treaties/outerspacetreaty.html)
- [COSPAR Planetary Protection Policy](https://cosparhq.cnes.fr/assets/uploads/2026/01/SRT_224_Editorial_PPP-Nov-2025.pdf)

### Simulation and reusable software

- [Genesis](https://github.com/Genesis-Embodied-AI/genesis-world)
- [MuJoCo](https://github.com/google-deepmind/mujoco)
- [Open Industry Project](https://github.com/Open-Industry-Project/Open-Industry-Project)
- [Project Chrono](https://github.com/projectchrono/chrono)
- [NASA cFS](https://github.com/nasa/cFS)
- [Basilisk](https://github.com/AVSLab/basilisk)
- [NASA Ogma](https://github.com/nasa/ogma)
- [Factorio Learning Environment](https://github.com/JackHopkins/factorio-learning-environment)
