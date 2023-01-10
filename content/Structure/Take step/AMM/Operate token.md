# Trading

Investors, including both external agents and those who receive tokens from the vesting schedule, can buy and sell tokens on the market for the purposes of longing/shorting.

This effect is essentially unpredictable. For the purposes of the simulation, it is assumed that investors take a rational approach when evaluating their investment on the AUKI token, related to its utility demand (app developers buying the token for network credits, and staking), which can be equated to a Monthly Revenue Rate (MRR) for the Hagall network. Therefore, the simulation assumes that investors will buy when the market cap is lower than how they estimate the value of the project based on its MRR, and sell when the market cap is higher than that.

## Calculation

The amount of tokens bought or sold by investors is calculated as the amount needed to take the token price to the point where the market cap is equal to the estimated project valuation. This is calculated as follows:

$$
A = X - \sqrt{K \cdot \frac{S}{V}}
$$

Where:
 * $A$: Amount of tokens to be bought or sold
 * $X$: Amount of tokens in the pool
 * $K$: Constant of the AMM that emulates the market
 * $S$: Supply of tokens
 * $V$: Estimated project valuation

However, there is an additional limitation. If they sell, investors will not sell more than a certain percentage of their tokens yearly (to simulate the fact that holders and project stakeholders will not want to sell all their tokens at once). This results in:

$$
\Delta I = \min\left(A, I \cdot \left( 1 - (1- r_{s, anual})^{\Delta t /\text{seconds in a year}}\right) \right)
$$

where
 * $\Delta I$: Amount of tokens bought or sold by investors in time step $t$
 * $A$: Amount of tokens to be bought or sold to reach the estimated project valuation
 * $I$: Amount of tokens owned by investors
 * $r_{s, anual}$: Anual ratio of tokens to be sold by investors
 * $\Delta t$: Time step