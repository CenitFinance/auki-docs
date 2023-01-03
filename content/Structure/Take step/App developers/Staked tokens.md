DAUs -> $D(t)$

Staking period length -> $\Delta t_s$

Max DAUs in staking period -> 
$$
D_s = \max_{T > t - \Delta t_s ; T < t} D(T)
$$

Staked tokens per DAU discount -> $d$

Discount efficiency -> $e ; e \ge 0 ; e \le 1$

Staking average duration -> $\Delta t_s$

Price limit -> $P_l = \frac{P \cdot \Delta t_s}{2 d}$

Minimum tokens to get discount -> $T_m = D_s \cdot e \cdot d$

If $T_m < T_d$:
	The [[../../Agents/App developers]] sell tokens so $T_d = T_m$

If $T_m > T_d$ and $P < P_l$ and $T_a > T_m - T_d$:
	The [[../../Agents/App developers]] buy tokens so $T_d = T_m$

(This is actually done at [[../Burning/Burn tokens]] in the simulation)