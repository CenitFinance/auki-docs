# Burn Tokens

The app developers burn tokens in exchange for network credits, with which they pay for the service provided by the Hagall network to run their apps. 
The network credit price is pegged to the dollar, so a higher token price means that the app developers will burn less tokens to pay for the same amount of network credits.

Additionally, discounts from predictive staking are taken into account as well. Staking can result in discounts of up to 50% per network credit. 

## Burn Calculation

First of all, staking discounts are taken into account. The amount of discounted serviced DAUs is calculated as follows:

$$
U_{discounted}(t) = U(t) \cdot \min \left( \dfrac{S(t)}{d}, 1 \right)
$$

Where:
  * $U_{discounted}(t)$ -> Amount of DAUs serviced with a discount at time $t$
  * $U(t)$ -> Amount of daily active users at time $t$
  * $S(t)$ -> Amount of tokens staked at time $t$
  * $d$ -> Amount of tokens per DAU single day service discount

The discounted DAUs are then used to calculate the dollar value of the tokens the app developers need to burn to pay for the service:

$$
B_{USD}(t) = U_{discounted}(t) \cdot P_c \cdot \Delta t \cdot \left(1 - 0.5 \cdot \dfrac{U_{discounted}(t)}{U(t)} \right) 
$$

Where:
  * $B_{USD}(t)$ -> The dollar value of the tokens to burn at time $t$
  * $U_{discounted}(t)$ -> Amount of DAUs serviced with a discount at time $t$
  * $U(t)$ -> Amount of daily active users at time $t$
  * $P_c$ -> Price of service for a single DAU (equal to the network credit price if the network credit serves a single DAU)
  * $\Delta t$ -> Time step length

Finally, the app developers buy the amount of tokens to burn from the AMM, and burn them.
The purchase causes the price of the tokens to increase, and the app developers will need to burn less tokens, but the dollar value will be the same.
