# Liquidity Pool: How It Works

The SportToken Liquidity Pool (vault) is what makes instant bet fills possible. It is a crowdfunded pool that takes the opposite side of user bets while targeting long‑term profitability through fees and risk caps.

## Instant fills, LP as counterparty
- When a user places a bet, the vault provides the potential payout.
- Example: Packers -150 / Lions +150. Alice bets $150 on Packers to win $100. The vault covers that $100 if Packers win.

## Why the vault expects to profit
- A platform fee applies to every transaction (0.3% baseline).
- A risk-based fee applies when a bet would increase the vault’s exposure on a market. This fee scales with how much of the vault is being risked.
- A position cap prevents overexposure on any single event.

## Key takeaways
- Instant liquidity: bets clear without waiting for another user.
- Dynamic fees: higher exposure → higher fee, aligned with Kelly-style risk sizing.
- Hard exposure cap: we refuse bets that would push risk beyond our limit on any event.

## Why this matters for everyday investors
SportToken Investments (a branch under SportToken) turns the booming sports prediction market into an investable product: everyday people can own a slice of the liquidity pool and share in fees/P&L the vault earns. It’s a differentiated way to participate in sports predictions without needing to place bets yourself—back the house, not just the teams.

> Note: Market fees above the 0.3% base are always offered back to other users who take the position off the vault (they can earn that fee by flattening our exposure).

