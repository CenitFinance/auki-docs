The [[../../Agents/Treasury]] makes sales to the [[../../Agents/AMM]] according to the [[Treasury sales schedule]] capped by the number of tokens the [[../../Agents/Treasury]] currently holds

The [[../../Agents/Investors]] buy/sell tokens according to their valuation and the [[../../Agents/AMM]] current token price

This is modified by the daily rebalancing ratio (hypothesis), the fraction of the day passed in the time step and the amount of tokens that the investors currently hold (when selling)

The investors then [[../AMM/Operate token]] for that amount

The amount of tokens held by the [[../../Agents/Investors]] is modified by their acquisitions