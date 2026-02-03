# Vault Positions

The LP page displays all active positions the vault holds, giving LPs full transparency into the protocol's exposure and risk.

## Position Dashboard

The positions table shows every active bet the vault is counterparty to:

| Field | Description |
|-------|-------------|
| **Game** | The event being bet on |
| **Market** | Moneyline, spread, or total |
| **Side** | Which outcome the bettor took |
| **Stake** | Amount wagered |
| **Liability** | Maximum payout if bettor wins |
| **Probability** | Current implied probability |
| **Position Value** | Mark-to-market value |

## Position Types

The vault holds positions across multiple bet types:

### Sportsbook Bets
- **Moneylines** - Win/lose bets on games
- **Spreads** - Point spread bets
- **Totals** - Over/under bets

### Parlays
- Multi-leg bets with combined odds
- Higher variance, higher fees
- Shown with all legs listed

### Same Game Parlays (SGPs)
- Multiple bets on a single game
- Correlated outcomes

### Fixed-Odds Events
- Custom markets and props
- User-created picks

## Exposure Aggregation

Positions are grouped by:

1. **Game** - All bets on the same event
2. **Market Type** - Moneyline vs spread vs total
3. **Side** - Home/away or over/under

This allows LPs to see **net exposure** per market:

```
Net Exposure = Away Liability - Home Liability
```

If net exposure is positive, the vault profits if the home team wins. If negative, the vault profits if away wins.

## Real-Time Updates

Positions update in real-time:

- **Live odds feeds** - Probabilities adjust as odds change
- **New bets** - Appear immediately when placed
- **Settlements** - Removed when games complete
- **Cashouts** - Liability decreases when users cash out

### Visual Indicators

- 🔴 **Red flash** - Position value increased (worse for vault)
- 🟢 **Green flash** - Position value decreased (better for vault)
- 📈 **Sparklines** - Show recent price movements

## Understanding Position Value

Position value uses mark-to-market accounting:

```
Position Value = Stake × Fair Probability
```

Where fair probability is the de-juiced odds (removing sportsbook margin).

<Note>
A positive position value means the vault is expected to pay out. A negative value means expected profit.
</Note>

### Example

**Bet: $100 on Lakers -3.5 at -110 odds**

- Stake: $100
- Potential payout: $190.91
- Entry probability: 52.4%
- Current probability: 55%

Position value:
```
$190.91 × 0.55 = $105 (vault expects to pay ~$105)
```

If probability drops to 48%:
```
$190.91 × 0.48 = $91.64 (vault expects to pay ~$92)
```

The $13 difference is unrealized P&L for the vault.

## Risk Metrics

The positions page also shows aggregate risk:

| Metric | Description |
|--------|-------------|
| **Total Liability** | Sum of all maximum payouts |
| **Net Risk** | Probability-weighted expected payout |
| **Exposure by Sport** | Risk breakdown by sport |
| **Largest Positions** | Highest individual exposures |

## Counter Parlay Positions

Counter parlays appear separately:

- **Held Stakes** - USDC held for counter bettors (not LP equity)
- **Counter Exposure** - The vault's exposure if original parlay loses
- **Countered %** - How much of each parlay is countered

<Tip>
Higher counter percentages reduce vault risk, as users take on exposure instead of LPs.
</Tip>

## Why Transparency Matters

Full position visibility allows LPs to:

1. **Assess risk** before depositing
2. **Understand variance** in share price
3. **See diversification** across markets
4. **Track large exposures** that could impact returns

This transparency is a core principle of SportToken - LPs always know exactly what backs their shares.
