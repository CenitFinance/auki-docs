time += time_step -> $t_s = t_{s-1} + \Delta t$

[[../Structure/Take step/DAUs/Update DAUs]]

[[Vesting/Update vesting]]

[[Liquidity/Update liquidity provision]]

App developers [[Burning/Burn tokens]]

If the minting interval has passed: [[Minting/Mint tokens]]

Token TWAP is updated

If the rewards interval has passed: [[Operators/Distribute rewards]] to [[../Agents/Operators]] and then [[Operators/Evaluate operator profits]]

[[Metrics]] are extracted for the step
