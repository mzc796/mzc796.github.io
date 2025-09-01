---
title: ""
permalink: /research/
layout: single
author_profile: true
classes: wide
---

# Research Philosophy

My research philosophy is grounded in addressing real-world problems with social impact, particularly those that are often overlooked, as they can leave systems open to serious security vulnerabilities. I emphasize experimentation and system-building, informed by cross-disciplinary thinking. I value clarity—making complex ideas intuitive and accessible—and use conciseness as a tool to achieve it. “Less is more” is a principle I learned during my PhD journey, and it continues to guide how I write, present, design research, and live.

# Security Philosophy

![Octopus]({{ "/images/octopus.png" | relative_url }}){: .align-left width="320" }
![Owl]({{ "/images/owl.JPG" | relative_url }}){: .align-left width="320" }
![Chameleon]({{ "/images/chameleon.JPG" | relative_url }}){: .align-left width="320" }
![Security that blends into its ecosystem]({{ "/images/disguise.jpg" | relative_url }}){: .align-left width="320" }
<br clear="all"/>

**The security I strive for:**
- **Lightweight** — small footprint, small overhead
- **Ecosystem-native** — fits naturally into existing workflows
- **Stealthy while protecting** — unobtrusive by default; explicit when needed.
<br clear="all"/>


# PhD Research Paths

## Evolving Network Security in the Era of Network Programmability **[pdf]({{ "/files/CCS_Doctoral_Symposium_Camera_Ready_updated.pdf" | relative_url }})** · **[bib]({{ "/files/ccs_dr_symposium.bib" | relative_url }})**
![SDN Security](/images/research_paths.png){: .align-center width="600"}
<br clear="all"/>

On the one hand, SDN enhances network security. 

On the other hand, SDN exposes network vulnerabilities. 

# Projects
## Manipulating OpenFlow Link Discovery Packet Forwarding for Topology Poisoning **[pdf]({{ "/files/CCS_p3704-chen.pdf" | relative_url }})** · **[bib]({{ "/files/marionette_ccs24.bib" | relative_url }})**


### Flow entry-induced Topology Poisoning ![Marionette / topology poisoning](/images/topo_poisoning.png){: .align-right width="320"}
By identifying an overlooked vulnerability in which flow entries designed for traffic routing can influence topology discovery results, I uncovered a new attack vector such that a malicious application or a malicious controller in a controller cluster may craft poisonous flow entries, leading the legitimate controller to persistently and independently discover a deceptive topology conducive to malicious activities.

I successfully deployed Marionette attacks on both ONOS ([GitHub](https://github.com/mzc796/marionette_onos)) and OpenDaylight ([GitHub](https://github.com/mzc796/marionette_odl)) clusters, and five open-source controllers, while systematically evading existing defenses. I also show that Marionette can attack nine different SDN discovery protocols. The related video demos are on YouTube [ODL cluster](https://www.youtube.com/watch?v=qwHv9tXd-ts&t=5s) [ONOS_cluster](https://www.youtube.com/watch?v=lwAGYcCBOxc&t=15s). The related vulnerabilities I disclosed are [CVE-2024-37018](https://nvd.nist.gov/vuln/detail/CVE-2024-37018), [CVE-2024-46942](https://nvd.nist.gov/vuln/detail/CVE-2024-46942), and [CVE-2024-46943](https://nvd.nist.gov/vuln/detail/CVE-2024-46943).

### Poisonous Topology Computation
Leveraging the globalized topology poisoning attack capability, I designed a reinforcement learning (RL) model to compute a deceptive topology with the same degree sequence and high graph similarity to the real topology, tailored to specific goals. The RL model can generate a poisoned topology that is 92% similar to the original topology while attracting more than 60% additional flows to the eavesdropping point on a 36-node fat-tree topology. The action-prior technology is adopted to accelerate training speed, enabling us to compute the deceptive topology only using CPUs.

---

## Lightweight Coordinated Sampling for Dynamic Flows under Budget Constraints **[pdf]({{ "/files/coord_sampling_icccn24.pdf" | relative_url }})** · **[bib]({{ "/files/coord_sampling_icccn24.bib" | relative_url }})**

### P4-driven Coordinated Sampling ![Coord_Sampling / coord_sampling](/images/overcooked.jpg){: .align-right width="320"}
To address the challenge of high-rate flow-based sampling within the constraints of limited resources on each switch, a coordinated sampling framework is developed to place multiple P4-programmable switches along a flow to sample network packets with coordination. This framework provides dynamic sampling point activation, deactivation, and run-time configuration, capitalizing on the programmability of P4. Our P4 coordinated sampling algorithm incurs negligible overhead on throughput and round-trip time with substantially low activation and deactivation time (around 0.05 seconds) as demonstrated on physical Arista 7170CD switches. The P4 code is on [GitHub](https://github.com/mzc796/coord_sampling).

### Budgeted Maximum Multi-Coverage
Given the substantial cost disparity between P4-programmable switches and ordinary SDN switches, I formulated the placement problem as a budgeted maximum multi-coverage problem to determine the optimal placement of a budgeted number of P4-programmable switches to achieve maximum flow sampling coverage. This NP-complete integer linear programming problem is proven pseudo-polynomial time solvable on a real network topology by leveraging the balanced matrix property, and the experiment aligns with this result. Our budgeted optimal algorithm efficiently places sampling points in evaluated networks, ensuring sufficient flow sampling even under heavy loads. In contrast, the greedy algorithm fails to achieve this with the same budget.

---

## OPTISAN: Using Multiple Spatial Error Defenses to Optimize Stack Memory Protection within a Budget **[pdf]({{ "/files/usenixsecurity24-george.pdf" | relative_url }})** · **[bib]({{ "/files/optisan_usenixsec24.bib" | relative_url }})**

### Protect Spatial Memory Errors ![OPTISAN / opti_san](/images/dr_mario.png){: .align-right width="320"}
Spatial memory errors, such as buffer overflow, have been widely observed but are challenging to mitigate effectively within an affordable performance overhead. OPTISAN addresses this challenge by recognizing that identity-based and location-based defenses can impose varying overhead levels when safeguarding against the same unsafe memory operations. To maximize protection against exploitable objects, OPTISAN strategically applies multiple spatial memory defenses across the call graph.

### Budgeted Multi-defense Placement
Given a program's memory operations and their estimated defense overhead, I developed a mixed-integer non-linear programming formulation to calculate an optimal placement utilizing multiple defenses. The entanglement of multiple dimensions (i.e., monitor point k, defense p, and unsafe operation j) of variables introduces the complexity of non-linearity. We use the [indicator constraint](https://docs.gurobi.com/projects/optimizer/en/current/reference/python/model.html#Model.addGenConstrIndicator) of Gurobi to model this constraint. The results indicate that the placement strategy produced by our budgeted multi-defense placement formulation increases protection by 18.5% on average across ten benchmark programs.

---
