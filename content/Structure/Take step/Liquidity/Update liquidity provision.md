Gets tokens provided by [[../../Agents/Treasury]] and removes them from the [[../../Agents/Treasury]] total tokens

Gets tokens provided by [[../../Agents/Investors]] and removes them from the [[../../Agents/Investors]] total tokens

[[../../Agents/Treasury]] liquidity provided -> $L_t$

[[../../Agents/Investors]] liquidity provided -> $L_i$

[[../../Agents/Treasury]] liquidity provided ratio -> $R_t$

[[../../Agents/Investors]] liquidity provided ratio -> $R_i$

Change in liquidity provided by [[../../Agents/Treasury]] -> $\Delta L_t = T_t \cdot R_t  - L_t$

Change in liquidity provided by [[../../Agents/Investors]] -> $\Delta L_i = T_i \cdot R_i - L_i$

If $\Delta L_t > 0$:
	The [[../../Agents/Treasury]] adds tokens to the [[../../Agents/AMM]] liquidity pool
If $\Delta L_i > 0$
	The [[../../Agents/Investors]] add tokens to the [[../../Agents/AMM]] liquidity pool