Updates [[../../Agents/App developers]] staked tokens taking the discount into account (amount from [[../App developers/Staked tokens]])

Calculates the USD value that the developers should burn to service the users from the DAUs, credit price and fraction of a day passed in the time step

Undiscounted value in dollars to burn -> $B_{\$,0} = U \cdot P_c \cdot \frac{\Delta t}{24 \cdot 3600}$

The [[../../Agents/App developers]] buy the amount of tokens to burn from the [[../../Agents/AMM]]

Adds the burnt tokens to the variable tracking the amount of tokens burnt since last minting

Adds the burnt tokens to the variable tracking the amount of tokens burnt since the start of the simulation