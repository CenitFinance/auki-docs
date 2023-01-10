# Automated Market Maker

The Automated Market Maker (AMM) is a smart contract that facilitates the exchange of tokens for USD. It is a decentralized exchange that allows users to exchange tokens for USD without the need for a centralized exchange or an order book.

For the purposes of the simulation, the AUKI token market has ben modeled as a single AMM, which emulates the shared liquidity of all centralized or decentralized exchanges between AUKI and dollar-pegged currencies.

## AMM Pool

The pool follows a constant product formula, which is a mathematical model that describes the relationship between the amount of tokens and the amount of USD in the pool.

$$
K = X \cdot Y
$$

Where:
 * $K$: Constant of the AMM that emulates the market
 * $X$: Amount of tokens in the pool
 * $Y$: Amount of USD-pegged currency in the pool

As long as liquidity remains the same, any tokens can be exchanged for USD at a constant $K$ value. This sets the price of the token in the market.

$$
X' \cdot Y' = (X + \Delta X) \cdot (Y + \Delta Y)
$$

$$
P = \dfrac{Y}{X}
$$

Where:
 * $X'$: Amount of tokens in the pool after the exchange
 * $Y'$: Amount of USD-pegged currency in the pool after the exchange
 * $\Delta X$: Amount of tokens exchanged
 * $\Delta Y$: Amount of USD-pegged currency exchanged
 * $P$: Price of the token in the market