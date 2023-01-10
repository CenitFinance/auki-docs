# Predictive Staking

App developers stake tokens to get discounted prices on network credits. The amount of tokens staked is optimized to get the best price for the service they need to cover.

A certain dollar value of tokens staked (one of the design parameters of the tokenomics) for a certain period of time (another design parameter) unlocks a 50% discount on the price of a network credit. 

Higher locking periods result in lower token amounts needed for the same discount. This is a complex trade-off for the app developers, and their use of this system will be influenced by many uncontrolled variables. The simulation assumes that, on-average, the app developers use the predictive staking for a certain single locking period (and thus a certain average amount of tokens per network credit discount), and up to a certain efficiency in achieving discounts. Together, they imply the amount of staked tokens they seek.

It is assumed that the tokens are restaked as long as the app developers need them.

## Staking Calculation

The desired amount of tokens at time $t$ is calculated as follows:

$$
S(t) = \dfrac{U(t) \cdot e \cdot d}{P}
$$

Where:
 * $S(t)$: Desired amount of tokens staked at time $t$
 * $U(t)$: Amount of daily active users at time $t$
 * $e$: Efficiency in achieving discounts by the app developers, between 0 and 1
 * $d$: Dollar value in tokens for one DAU daily service discount
 * $P$: Token price in dollars

Thus, the app developers will want to exchange the following amount of tokens for staking:

$$
\Delta S(t) = S(t) - S(t - \Delta t)
$$

If $\Delta S(t) > 0$, the app developers will need to buy more tokens for staking before proceeding with their next purchase of network credits.

Otherwise, if the app developers have more tokens than they need, they will sell the difference on the market if any of them are unlocked in the period.