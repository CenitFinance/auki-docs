# Predictive Staking

App developers stake tokens to get discounted prices on network credits. The amount of tokens staked is optimized to get the best price for the service they need to cover.

A certain amount of tokens staked (one of the design parameters of the tokenomics) for a certain period of time (another design parameter) unlocks a 50% discount on the price of a network credit. 

Higher locking periods result in lower token amounts needed for the same discount. However, since this is a complex trade-off for the app developers, and their use of this system will be influenced by many uncontrolled variables, the simulation assumes that, on-average, the app developers use the predictive staking for a certain single locking period (and thus a certain average amount of tokens per network credit discount), and up to a certain efficiency in achieving discounts, which together imply the amount of staked tokens they seek.

If is assumed that the tokens are restaked as long as the app developers need them.

## Staking Calculation

The desired amount of tokens at time $t$ is calculated as follows:

$$
S(t) = U(t) \cdot e \cdot d
$$

Where:
 * $S(t)$ -> Amount of tokens staked at time $t$
 * $U(t)$ -> Amount of daily active users at time $t$
 * $e$ -> Efficiency in achieving discounts by the app developers, between 0 and 1
 * $d$ -> Amount of tokens per DAU single day service discount

Thus, the app developers will want to exchange the following amount of tokens for staking:

$$
\Delta S(t) = S(t) - S(t - \Delta t)
$$

If $\Delta S(t) > 0$, the app developers would need to buy tokens. They will only actually buy tokens if at that point it makes economical sense in terms of the effective discount achieved within a certain period of time. This period of time is assumed to be the staking period, and it is assumed to be a constant value. This implies a certain limit token price above which they will not proceed with the purchase.

$$
P_{limit} = 0.5 \cdot \dfrac{P_c \cdot T_s}{d}
$$

Where the $0.5$ comes from the 50% discount, and the rest of the variables are defined as follows:
 * $P_{limit}$ -> Limit token price above which the app developers will not buy tokens
 * $P_c$ -> Price of service for a single DAU (equal to the network credit price if the network credit serves a single DAU)
 * $T_s$ -> Staking period length
 * $d$ -> Amount of tokens per DAU single day service discount

On the other hand, if the app developers have more tokens than they need, they will sell the difference on the market if any of them are unlocked in the period.