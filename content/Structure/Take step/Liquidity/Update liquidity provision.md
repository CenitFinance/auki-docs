# Liquidity Provision

Both investors and the treasury are liquidity providers to the AUKI/USD [[../../Agents/AMM]] that acts as the market for the token.

Each of them has a target liquidity provision ratio, which is the percentage of the total tokens available to them that they want to have in the [[../../Agents/AMM]]. Let's call them $R_t$ and $R_i$.

The calculation of the liquidity provision is done as follows:

 * Gets tokens provided by treasury and removes them from the treasury total tokens
 * Gets tokens provided by investors and removes them from the investors total tokens
 * Treasury liquidity provided -> $L_t$
 * Investors liquidity provided -> $L_i$
 * Change in liquidity provided by treasury -> $\Delta L_t = T_t \cdot R_t  - L_t$
 * Change in liquidity provided by investors -> $\Delta L_i = T_i \cdot R_i - L_i$
 * If $\Delta L_t > 0$: the treasury adds tokens to the AMM liquidity pool
 * If $\Delta L_i > 0$ the investors add tokens to the AMM liquidity pool