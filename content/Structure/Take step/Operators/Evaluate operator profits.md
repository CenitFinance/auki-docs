# Evaluate operator profits

Once new rewards have been distributed, operators sell the token in order to cover their costs and make a profit. They evaluate their profits or losses and some decide whether to leave the network or not.

Additionally, if prospective profits are attractive, new operators might want to join the network. This is modeled as the potential yield, calculated as the yearly profit from an initial investment equivalent to the staking amount.

## Calculation

First, we take into account the from selling the token delivered as rewards on the aggregated AMM that emulates the market in order to calculate the profits, as well as the costs from running the nodes.

$$
P_{o} = E_{o} - C_{o}
$$

where
 * $P_{o}$ is the profit per operator
 * $E_{o}$ is the earnings per operator from the sale of the token (incluing any possible slippage on the AMM)
 * $C_{o}$ is the costs per operator

$C_{o}$ is calculated takes into account fixed costs and variable (network) costs.

$$
C_{o} = C_{o, fixed} + c_{o, network} \cdot T_{o}
$$

where
 * $C_{o, fixed}$ are the fixed costs
 * $c_{o, network}$ are the variable costs per unit of traffic served
 * $T_{o}$ is the traffic served per operator

If $P_{o} > 0$, operators are, on average, profitable and will continue to operate. Otherwise, if $P_{o} < 0$, some will leave the network. This is modeled linearly with the losses as:

$$
\Delta N_{o} = r_e \cdot P_{o} \cdot \Delta t
$$

where
 * $\Delta N_{o}$ is the change in the number of operators
 * $r_e$ is the exit rate
 * $P_{o}$ is the profit per operator (negative in this case)
 * $\Delta t$ is the time since the last profit evaluation

On the other hand, if $P_{o} > 0$, new operators might want to join the network. This is modeled as the potential yield, calculated as the yearly profit from an initial investment equivalent to the staking amount. The yield is calculated as:

$$
Y_{o} = \frac{P_{o}}{S_{o}}
$$

where
 * $Y_{o}$ is the yield per operator
 * $P_{o}$ is the profit per operator
 * $S_{o}$ is the staking amount per operator (in dollars)

The amount of new operators is calculated as:

$$
\Delta N_{o} = r_j \cdot \left(Y_{o} - Y_{minimum} \right) \cdot \Delta t
$$

where
 * $\Delta N_{o}$ is the change in the number of operators
 * $r_j$ is the join rate
 * $Y_{o}$ is the yield per operator
 * $Y_{minimum}$ is the minimum yield required to incentivize new operators to join
 * $\Delta t$ is the time since the last profit evaluation

If new operators join the network, they purchase token from the AMM in order to stake it. If they leave, they sell the token in the AMM. The amount of token exchanged is calculated as:

$$
\Delta T_{o} = \Delta N_{o} \cdot \dfrac{S_{o}}{P}
$$

where
 * $\Delta T_{o}$ is the change in the amount of token exchanged
 * $\Delta N_{o}$ is the change in the number of operators
 * $S_{o}$ is the staking amount per operator (in dollars)
 * $P$ is the price of the token in dollars after the exchange
