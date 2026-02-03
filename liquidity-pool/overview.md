# Liquidity Pool Overview

The SportToken Liquidity Pool is a single USDC vault that backs all betting markets on the platform. Liquidity providers (LPs) deposit USDC and earn returns from betting fees and favorable outcomes.

## How It Works

<Steps>
  <Step title="Deposit USDC">
    LPs deposit USDC into the vault and receive shares representing their ownership
  </Step>
  <Step title="Instant Fills">
    The vault acts as counterparty to all bets, providing instant liquidity
  </Step>
  <Step title="Earn Returns">
    LPs earn from fees collected and profitable P&L from positions
  </Step>
  <Step title="Withdraw Anytime">
    Redeem shares for USDC at the current share price (subject to risk limits)
  </Step>
</Steps>

## Vault Architecture

The vault is built on an **ERC-4626** style share accounting system:

- **LPs own shares**, not direct USDC
- Share price fluctuates based on vault performance
- Deposits and withdrawals happen at current share price

### Core Formula

```
LP Equity = Total Assets - Net Risk - Held User Stakes

Where:
- Total Assets = USDC balance + Aave deposits (if enabled)
- Net Risk = Probability-weighted expected payout
- Held User Stakes = Counter parlay stakes (held but not LP equity)
```

## What Backs the Vault?

<CardGroup cols={2}>
  <Card title="USDC Deposits" icon="coins">
    Direct USDC from LP deposits
  </Card>
  <Card title="Aave Yield" icon="chart-line">
    Optional yield generation via Aave v3
  </Card>
  <Card title="Fee Revenue" icon="percent">
    0.3% base fee on all bets
  </Card>
  <Card title="Bet P&L" icon="scale-balanced">
    Profit from losing bets, losses from winners
  </Card>
</CardGroup>

## Risk Management

The vault employs several risk controls:

### Per-Market Caps
Each market has a maximum exposure limit to prevent overconcentration on any single event.

### Risk Cap on Withdrawals
Withdrawals are limited to ensure the vault maintains adequate reserves:

```
Max Withdrawable = Assets - (Reserved × 10000 / Risk Cap BPS)
```

Default risk cap: **1.5%** (150 basis points)

### Liability Tracking
Every market contract registers with the vault and reports:
- Current liability (maximum potential payout)
- Position updates as bets are placed/settled

## LP Returns

LPs earn returns through:

1. **Fees** - Base 0.3% on all bets, plus dynamic fees based on exposure
2. **Betting P&L** - The house edge over time
3. **Aave Yield** - Additional yield when USDC is deployed to Aave

<Note>
Returns are not guaranteed. LPs take on the risk of large payouts from winning bets. However, the fee structure and diversification across markets typically favors the house over time.
</Note>

## Getting Started

To become an LP:

1. Connect your wallet
2. Navigate to the LP page
3. Approve USDC spending
4. Enter deposit amount
5. Confirm transaction

You'll receive vault shares representing your proportional ownership of the pool.
