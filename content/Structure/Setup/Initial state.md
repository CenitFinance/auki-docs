# Initial state

The initial state of the simulation is the Token Generation Event. From this point forwards:
 * The first tokens have been minted and distributed or sold to investors
 * The token economy is live, with a market facilitating the exchange of tokens for USD
 * The token utility is available, with app developers being able to exchange tokens for network credits
 * Vesting schedules for investors and the treasury begin to vest
 * The minting events beggin to occur periodically

Most simulation variables are initialized at this point. Additionally, some specific actions are taken to initialize the simulation environment, described below.

## Network

Initially, no decentralized workers exist in the network. 
There is an initial number of centralized workers providing the service, which is a design parameter of the simulation.

## Staking

Both worker operators and app developer stake are initialized to 0.

## Vesting

The vesting schedules for investors and the treasury are initialized to at time 0.
This includes the distribution of some tokens that constitute the initial circulating supply, including the public sale.

## Market

In the initialization, an [[../Agents/AMM|AMM pool]] is created to act as the simulated market environment.

There is an initial provision of liquidity to this AMM, set as a percentages of the total tokens avaiable to the investors and the treasury. This initial liquidity is provided at the price point of the public sale, which is therefore the initial price of the token.

Both the investors and the treasury will try to adjust their liquidity provision to this percentage throughout the simulation, providing liquidity to the market when the percentage is too low and removing liquidity when the percentage is too high.
