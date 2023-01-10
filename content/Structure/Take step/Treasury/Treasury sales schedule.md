# Treasury sales

The treasury sells tokens on the market to cover its expenses. For the purposes of the simulation, this happens according to a predefined schedule (yearly percentage of the current reserve)

## Calculation

The amount of tokens to be sold is calculated as follows:

$$
S_t = T_t \cdot \left(1 - \left(1 - r_{s, anual} \right)^{\Delta t / \text{seconds in a year}} \right)
$$

where
 * $S_t$ is the amount of tokens sold in time step $t$
 * $T_t$ is the amount of tokens in the treasury in time step $t$
 * $r_{s, anual}$ is the anual ratio of tokens to be sold
 * $\Delta t$ is the time step

