# Share Price

The share price represents the USDC value of each vault share. It fluctuates based on the vault's performance and is the key metric for LP returns.

## How Share Price Works

When you deposit USDC, you receive shares based on the current share price:

```
Shares Received = Deposit Amount / Share Price
```

When you withdraw, your shares are redeemed at the current price:

```
USDC Received = Shares × Share Price
```

## Share Price Calculation

The share price is calculated in real-time:

```
Share Price = LP Equity / Total Shares

Where:
LP Equity = Total Assets - Net Risk - Held Stakes
```

### Components

| Component | Description |
|-----------|-------------|
| **Total Assets** | USDC in vault + Aave deposits |
| **Net Risk** | Probability-weighted expected payout to bettors |
| **Held Stakes** | Counter parlay stakes (held but excluded from LP equity) |
| **Total Shares** | All outstanding LP shares |

## What Moves Share Price?

<CardGroup cols={2}>
  <Card title="Increases Share Price" icon="arrow-up">
    - Fees collected from bets
    - Bettors losing (favorable P&L)
    - Aave yield accrual
  </Card>
  <Card title="Decreases Share Price" icon="arrow-down">
    - Large payouts to winners
    - Unfavorable P&L
  </Card>
</CardGroup>

### Neutral Events

These do NOT change share price:
- New LP deposits (receive shares at current price)
- LP withdrawals (redeem at current price)
- Bet placement (assets and liabilities change equally)

## Mark-to-Market (MTM) Valuation

The vault uses **real-time probability-weighted** valuation:

```
Expected Payout = Σ (Position Payout × Current Probability)
Net Risk = Total Liabilities - Expected Payout
```

This means:
- If odds shift in favor of bettors → Net Risk increases → Share price drops
- If odds shift against bettors → Net Risk decreases → Share price rises

<Note>
Share price updates continuously based on live odds feeds, not just when bets settle.
</Note>

## Example

**Scenario: $1,000,000 vault with 1,000,000 shares**

Initial state:
- Share price: $1.00
- Total assets: $1,000,000
- Net risk: $0

After a day of betting:
- Fees collected: $3,000
- Net favorable P&L: $2,000
- New total assets: $1,005,000

New share price:
```
$1,005,000 / 1,000,000 = $1.005
```

LPs earned **0.5% return** that day.

## Checking Share Price

On the LP page, you can see:

- **Current Share Price** - Real-time value
- **Your Shares** - How many you own
- **Your Value** - Shares × Share Price
- **Historical Performance** - Share price over time

## Important Considerations

<Warning>
Share price can decrease if bettors win big. LP returns are not guaranteed and depend on overall betting outcomes.
</Warning>

### Timing Deposits/Withdrawals

- **Deposit when** share price is stable or you believe the vault will profit
- **Withdraw when** you want to lock in gains or reduce exposure
- Share price at transaction time determines your rate

### Long-Term View

Over time, the fee structure and house edge typically favor LPs:
- 0.3% base fee on all volume
- Dynamic fees that scale with risk
- Diversification across thousands of markets

However, short-term variance from large winners can cause temporary drawdowns.
