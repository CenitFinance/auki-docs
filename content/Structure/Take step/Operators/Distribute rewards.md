From the minted tokens since last minting and the rewards ratio, get the base number of tokens that should go to the [[../../Agents/Treasury]] and the [[../../Agents/Operators]]

Minted tokens -> $m$
Rewards ratio -> $r_r$

[[../../Agents/Treasury]] rewards tokens -> $R_t = m(1-r_r)$
[[../../Agents/Operators]] rewards tokens -> $R_o = mr_r$

Get the incentives ratio from the [[Incentives schedule]] and use that to calculate the final amount of tokens the [[../../Agents/Treasury]] and [[../../Agents/Operators]] should receive

Incentives ratio -> $r_i$
Incentives given by [[../../Agents/Treasury]] to [[../../Agents/Operators]] -> $I=r_iR_t$

Add the [[../../Agents/Treasury]] tokens to the [[../../Agents/Treasury]] total tokens

Add the [[../../Agents/Operators]] tokens to the [[../../Agents/Operators]] rewards for the current step