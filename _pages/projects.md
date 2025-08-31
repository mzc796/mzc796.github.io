---
title: "Research & Projects"
permalink: /_pages/projects/
layout: single
author_profile: true
classes: wide
---

## Manipulating OpenFlow Link Discovery Packet Forwarding for Topology Poisoning
**[pdf](https://drive.google.com/file/d/1v5k8l3S4j4d2eW0b1r7S8mS0yHcD8m8t/view?usp=sharing)** · **[bib](https://drive.google.com/file/d/1d2Z3wQkXf-bib-example/view?usp=sharing)**

### Flow entry-induced Topology Poisoning
By identifying an overlooked vulnerability in which flow entries designed for traffic routing can influence topology discovery results, I uncovered a new attack vector such that a malicious application or a malicious controller in a controller cluster may craft poisonous flow entries, leading the legitimate controller to persistently and independently discover a deceptive topology conducive to malicious activities.

I successfully deployed Marionette attacks on both ONOS and OpenDaylight clusters, and five open-source controllers, while systematically evading existing defenses. I also show that Marionette can attack nine different SDN discovery protocols. The related video demos are on YouTube [ODL](https://www.youtube.com/watch?v=dQw4w9WgXcQ) [ONOS_cluster](https://www.youtube.com/watch?v=dQw4w9WgXcQ). The related vulnerabilities I disclosed are [CVE-2024-37018](https://nvd.nist.gov/vuln/detail/CVE-2024-37018), [CVE-2024-46942](https://nvd.nist.gov/vuln/detail/CVE-2024-46942), and [CVE-2024-46943](https://nvd.nist.gov/vuln/detail/CVE-2024-46943).

### Poisonous Topology Computation
Leveraging the globalized topology poisoning attack capability, I designed a reinforcement learning (RL) model to compute a deceptive topology with the same degree sequence and high graph similarity to the real topology, tailored to specific goals. The RL model can generate a poisoned topology that is 92% similar to the original topology while attracting more than 60% additional flows to the eavesdropping point on a 36-node fat-tree topology.

The action-prior technology is adopted to accelerate training speed enabling us to compute the deceptive topology only using CPU.

---

## Lightweight Coordinated Sampling for Dynamic Flows under Budget Constraints
**[pdf](https://drive.google.com/file/d/1LL-ICCCN-paper-example/view?usp=sharing)** · **[bib](https://drive.google.com/file/d/1LL-bib-example/view?usp=sharing)**

### P4-driven Coordinated Sampling
To address the challenge of high-rate flow-based sampling within the constraints of limited resources on each switch, a coordinated sampling framework is developed to place multiple P4-programmable switches along a flow to sample network packets with coordination. This framework provides dynamic sampling point activation, deactivation, and run-time configuration, capitalizing on the programmability of P4.

Our P4 coordinated sampling algorithm incurs negligible overhead on throughput and round-trip time with substantially low activation and deactivation time (around 0.05 seconds) as demonstrated on physical Arista 7170CD switches. The P4 code is on [Github](https://github.com/mzc796).

### Budgeted Maximum Multi-Coverage
Given the substantial cost disparity between P4-programmable switches and ordinary SDN switches, I formulated the placement problem as a budgeted maximum multi-coverage problem, to determine the optimal placement of a budgeted number of P4-programmable switches to achieve maximum flow sampling coverage.

This NP-complete integer linear programming problem is proven pseudo-polynomial time solvable on a realist network topology by leveraging the balanced matrix property and the experiment aligns with this result.

Our budgeted optimal algorithm efficiently places sampling points in evaluated networks, ensuring sufficient flow sampling even under heavy loads. In contrast, the greedy algorithm fails to achieve this with the same budget.

---

## OPTISAN: Using Multiple Spatial Error Defenses to Optimize Stack Memory Protection within a Budget
**[pdf](https://drive.google.com/file/d/1OPTISAN-paper-example/view?usp=sharing)** · **[bib](https://drive.google.com/file/d/1OPTISAN-bib-example/view?usp=sharing)**

### Protect Spatial Memory Errors
Spatial memory errors, such as buffer overflow, have been widely observed but are challenging to mitigate effectively within an affordable performance overhead. OPTISAN addresses this challenge by recognizing that identity-based and location-based defenses can impose varying overhead levels when safeguarding against the same unsafe memory operations. To maximize protection against exploitable objects, OPTISAN strategically applies multiple spatial memory defenses across the call graph.

### Budgeted Multi-defense Placement
Given a program's memory operations and their estimated defense overhead, I developed a mixed-integer non-linear programming formulation to calculate an optimal placement utilizing multiple defenses. The entanglement of multiple dimensions (i.e., monitor point k, defense p, and unsafe operation j) of variables introduces the complexity of non-linearity. We use the [indicator constraint](https://www.gurobi.com/documentation/9.5/refman/constraints.html#subsubsection:IndicatorConstraints) of Gurobi to model this constraint.

The results indicate that the placement strategy produced by our budgeted multi-defense placement formulation increases protection by 18.5% on average across ten benchmark programs.

---

**Email:** mzc796@psu.edu
