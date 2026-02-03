# Fees and Risk Controls

We use a two-part fee model plus strict exposure caps to keep the vault profitable over time.

## 1) Baseline platform fee
- 0.3% on all transactions across the platform.

## 2) Risk-based fee (linear with exposure)
- When a bet increases vault risk on a side, we charge a fee proportional to the added risk.
- We target Kelly-style optimal sizing: fee ≈ added risk as a % of vault.

### Example: first bet on a side
- Vault size: $100,000.
- Market: Packers -150 / Lions +150, zero existing exposure.
- Alice bets $1,500 on Packers. Vault risk: ~$1,000 (1% of vault).
- Fee charged ≈ 1% → Alice effectively bets $1,485 to win ~$990.
- The fee curve moves from 0% to ~2% after this bet; Alice pays the average over that move.

### Example: subsequent bet on same side
- After Alice, vault risk on Packers is ~2% on Lions side.
- Bob wants another $1,500 on Packers. That would push risk to ~4%.
- Average fee over that move ≈ 3% ((2% + 4%) / 2) → applied to Bob’s stake.

## 3) Hard exposure cap (per event)
- We never willingly risk more than ~1.5% of the vault on a single event from new bets.
- If a new bet would exceed that cap, we partially fill only up to the cap (e.g., Bob can only place ~$750 in the example).
- Positions can exceed 1.5% only if odds move in our favor after acceptance (P&L drift).

## Fee recycling
- Any market-specific fee above the 0.3% base is made available to users who take the opposing side from us (flattening our risk).

> Proofs and deeper math: formal Kelly-style derivations will be published separately.




















