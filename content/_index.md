# AUKI Tokenomics Simulation

This documentation describes the simulation of the AUKI tokenomics model available at [https://auki.cenit.finance/](https://auki.cenit.finance/).
Specifically, this simulation tests the behaviour of the tokenomics with the initial utility available in the AUKI Hagall network.

The simulation is written in Python and is designed to test various tokenomics designs and their behavior in a variety of simulated environments.

 * The simulation [[Structure/Setup/Initial state|starts at the TGE]] (Token Generation Event) and evolves through time. The time step is 6 hours by default.
 * Each [[Structure/Take step/Step|step]] loops through a series of events and actions by agents that change the state of the simulation environment, such as worker operators, app developers, or the treasury.
 * The simulation results are dependent upon:
   * Initial state of the environment
   * A set of design parameters that define the tokenomics model
   * A set of hypotheses that define reasonable assumptions about the simulation environment and the behaviour of agents

