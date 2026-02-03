# Parlays

A parlay is a single bet that links multiple individual wagers together. All selections must win for the parlay to pay out, but the combined odds create the potential for larger returns from a smaller stake.

## How Parlays Work

When you place a parlay on SportToken:

1. **Select multiple outcomes** - Add 2 or more selections to your bet slip
2. **Combined odds** - The odds multiply together for higher potential returns
3. **All-or-nothing** - Every leg must win for the parlay to pay out

## Parlay Fees

SportToken uses a **compounding fee structure** for parlays:

### System Fee
- **0.3%** base platform fee on all parlays
- **1.0%** for CBB (college basketball) DraftKings-only games

### Market Fee (Per Leg)
Each leg of your parlay incurs a market-based fee that compounds:

- Fee is based on market imbalance (how lopsided the betting is)
- Minimum 0.75% per leg (ensures at least 1.5% retained)
- Fees multiply together: a 2-leg parlay with 2% per leg ≈ 3.96% total

### Example Fee Calculation

**3-Leg Parlay with $100 stake:**
- System fee: 0.3% = $0.30
- Leg 1 market fee: 1.5%
- Leg 2 market fee: 2.0%
- Leg 3 market fee: 1.8%
- Combined market fee: 1 - (0.985 × 0.98 × 0.982) ≈ 5.2%
- Total fee: ~5.5%
- Net stake: ~$94.50

<Note>
Unlike single bets which cap at 3% total fee, parlay fees are uncapped and can exceed 3% due to compounding.
</Note>

## Why Compounding Fees?

Parlays represent higher risk to the liquidity pool because:

1. **Correlated risk** - Multiple outcomes are linked
2. **Higher variance** - Larger potential payouts
3. **Concentrated exposure** - One bettor can create significant liability

The compounding fee structure ensures the vault is adequately compensated for this increased risk while still offering competitive odds.

## Parlay Limits

- Minimum legs: 2
- Maximum legs: 10 (depending on sport)
- Maximum payout: Determined by vault liquidity and exposure limits

## Instant Settlement

All parlays are backed by the SportToken liquidity vault, meaning:
- ✅ Instant bet confirmation
- ✅ No waiting for matching
- ✅ Guaranteed payout for winners
