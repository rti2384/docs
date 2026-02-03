# Share Price and Liquidity

Liquidity providers own shares of the vault. Share price reflects accumulated fees and P&L from acting as counterparty to bettors.

## What moves share price
- **Increases:** collected fees (platform + risk-based), profitable P&L from held positions.
- **Decreases:** losses from held positions.
- **Neutral:** idle capital; deposits/withdrawals occur at current share price.

## Locked capital
- Funds backing active bets cannot be withdrawn until the bet settles or we flatten exposure.

## Handling unavailable odds (“greyed out” markets)
- To protect LPs during odds outages:
  - Deposit share price assumes any unavailable-market bet **wins** (conservative for new LPs).
  - Withdrawal share price assumes any unavailable-market bet **loses** (conservative for exiting LPs).
- Recommendation: wait until deposit and withdrawal share prices converge when a market resumes.

## Position turnover
- If another user takes the opposite side of our position, the market-specific fee above 0.3% is passed through to that user for flattening our exposure.




















