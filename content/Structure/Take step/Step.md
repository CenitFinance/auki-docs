# Simulation step

Each step advances the simulation by a time step, which is 6 hours by default.

$$
t_s = t_{s-1} + \Delta t
$$

After that, a series events and actions meant to simulate the behavior of agents in the simulation environment are executed.

![Diagram of the simulation loop that executes within a time step, along with the design parameters and hypotheses it depends on](AUKI_diagram.jpg)
 
## Update of time-dependent variables

1. [[DAUs/Update DAUs|Update DAUs]]: Update the number of daily active users (DAUs) in the AUKI Hagall network
2. [[Vesting/Update vesting|Update vesting]]: Vest tokens for investors and the treasury according to their vesting schedules

## Actions

1. [[Liquidity/Update liquidity provision|Liquidity provision]]: Update the liquidity provision of the [[../Agents/AMM|AMM]] pool by investors and the treasury according to their target liquidity provision
2. [[App developers/Staked tokens|App developers stake]]: Based on the serice they need to cover, app developers optmize their stake to get discounted prices on network credits
3. [[Burning/Burn tokens|Burning]]: App developers burn tokens to get network credits
4. [[Minting/Mint tokens|Minting]]: If the minting epoch has passed, mint tokens  
5. [[Operators/Distribute rewards|Distribute Rewards]]: Rewards are distributed to operators according to their participation in the network and the service they provided
6. [[Operators/Evaluate operator profits|Evaluate operator profits]]: Once new rewards have been distributed, evaluate the profits of worker operators. 
7. [[Operators/Evaluate operator profits|Update decentralized operators]]: Based on these profits (or losses), operators may decide to leave the network, or new operators may decide to join the network.
8. [[Operators/Centralized node management|Centralized node management]]: AUKI Labs updates the numeber of centralized nodes based on the number of decentralized nodes in the network, targetting a certain ratio of centralized nodes
9. [[Treasury/Treasury sales schedule|Treasury sales]]: the treasury sells tokens on the market to cover its expenses. For the purposes of the simulation, this happens according to a predefined schedule (yearly percentage of the current reserve)
10. [[AMM/Operate token|Trading]]: investors buy and sell the token for the purposes of longing/shorting. 
