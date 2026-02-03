# Parlays and Vault Profitability

Parlays use the vault for execution, but we price risk differently than single legs to preserve long-term profitability.

## Parlay fee model
- 1.5% fee applied **per leg**.
- Effective total fee on _n_ legs: \(1 - 0.985^{n}\).
  - Example: 5-leg parlay → ~7.3% effective.

## Rationale
- Parlays compound variance. A per-leg fee preserves expected edge so the vault can sustainably offer multi-leg bets with instant fills.

## Fee recycling
- Market-specific fees above the 0.3% base are available to users who take the opposing side from the vault (flattening risk).




















