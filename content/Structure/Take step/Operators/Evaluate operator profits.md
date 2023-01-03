The [[../../Agents/Operators]] immediately sell the [[../../Agents/Operators]] rewards from to the [[../../Agents/AMM]]

Only decentralized operators get the rewards, so only they have earnings

Set the [[../../Agents/Operators]] rewards to 0

Get the [[../../Agents/Operators]] network costs from the DAUs, cost per DAU and fraction of a day passed in the time step

DAUs -> $U$
Cost per DAU -> $C$
Fraction of a day passed -> $\Delta d = \frac{\Delta t}{24 \cdot 3600}$

Network costs -> $C_n = CU\Delta d$

Split those costs between the centralized and decentralized [[../../Agents/Operators]] using the decentralization factor

Decentralization factor -> $d$
Centralized costs -> $C_{n,c}$
Decentralized costs -> $C_{n,d}$

Calculate the fixed node costs from the fixed daily costs (hypothesis)

Fixed node costs -> $c_f$
Number of decentralized nodes -> $n_d;n_d \in \mathbb{R};n_d>0$
Costs per node -> $c = \frac{C_{n,d}}{n_d} + c_f$

Calculate the node profits as the difference between the earnings from selling the rewards and the fixed + network costs per node (only for the decentralized nodes)

Earnings -> $E$
Earnings per node -> $e=\frac{E}{n_d}$
Profit per node -> $p = e-c$

The max network profit is calculated as the [[../../Agents/Operators]] earnings minus the decentralized nodes costs

Max network profit -> $P_{max}=E-C_{n,d}$

We get the prospective profit as the possible profit per operator if the would've been 1 operator more in this step

Prospective profit -> $p_p=\frac{P_{max}}{n_d+1}-c_f$

The prospective yield is calculated from taking the prospective profit for a whole year over the current USD value staking for the operator

USD value staking -> $s$
Prospective yield -> $y_p=p_p\frac{365}{\Delta d}\frac{1}{s}$

If the prospective profit is below 0,  some of the [[../../Agents/Operators]] want to exit according to the exit ratio (hypothesis), prospective profit (negative) and fraction of a day passed in the time step

The exits are limited by the number of operators exiting where the prospective profit becomes positive (they no longer have a reason to exit) and the max variation in decentralized [[../../Agents/Operators]] per time step (20%)

Exit ratio -> $r_e$
Operators leaving from exit ratio -> $E_r = r_e p_p \Delta d$
Operators that need to leave to reach profitability -> $E_p=n_d - \frac{P_{max}}{c_f}$
Max variation in operators -> $E_{max} = 0'2 n_d$

Operators leaving -> $\min\{E_r, E_p, E_{max}\}$

If the prospective profit is less than the minimum incentivized yield (hypothesis), no new [[../../Agents/Operators]] want to enter, so there is no change

If the prospective profit is above the minimum incentivized yield, new [[../../Agents/Operators]] want to enter according to the yield eagerness (hypothesis), yield incentive (diff between prospective yield and minimum incentivized yield) and fraction of a day passed in the time step

The enters are limited by the number of operators entering where the prospective profit becomes less than the minimum incentivized yield (I'm not 100% sure I got the formula right, so this may be wrong), and the max variation in decentralized [[../../Agents/Operators]] per time step (20% + 1 to account for the starting point where there are no decentralized [[../../Agents/Operators]])

Yield eagerness -> $r_e$
Minimum incentivized yield -> $y_{min}$
Yield incentive -> $y_i = y_p - y_{min}$
Operators entering from yield prospects -> $E_y = r_e y_i \Delta d$
Operators that need to enter to have yield below minimum -> $E_p = P_{max}\left(\frac{s y_{min}}{365 {\Delta d}^{-1}} + c_f\right)$
Max variation in operators -> $E_{max} = 0'2 n_d$

Operators entering -> $\min\{E_y, E_p, E_{max}\}$

After this, we [[Update the number of operators]] (this includes optimizing the staking for the existing operators) and get the change in tokens from it

We now [[../AMM/Operate token]] for the change in tokens from the [[../../Agents/Operators]] update

If the centralization objective (design parameter) is not satisfied, new centralized [[../../Agents/Operators]] enter or exit the network to satisfy it (these make no token staking or selling)