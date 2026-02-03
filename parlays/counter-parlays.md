# Counter Parlays

Counter parlays allow users to bet **against** existing parlays. If you believe a parlay will lose (any leg fails), you can counter it and profit from the original bettor's loss.

## How Counter Parlays Work

When someone places a parlay, it creates an opportunity for others to take the opposite side:

1. **Original parlay** - User A bets $100 that Teams X, Y, and Z all win
2. **Counter opportunity** - The vault shows this parlay as available to counter
3. **Counter bet** - User B can bet that User A's parlay will lose
4. **Payout** - If ANY leg of the original parlay loses, the counter wins

### Counter Probability

The counter probability is simply:

```
Counter Probability = 1 - Parlay Probability
```

For example, if a parlay has a 15% chance of winning, the counter has an 85% chance of winning.

## Rebates: Better Odds for Counter Bettors

This is where SportToken becomes unique. **Counter bettors receive rebates** from the fees the original parlay maker paid.

### How Rebates Work

When the original parlay was placed, they paid:
- System fee (0.3%)
- Dynamic market fees (varies by leg)

The **dynamic fee portion** becomes a rebate pool for counter bettors:

```
Total Fee = System Fee + Dynamic Fee
Rebate Pool = Dynamic Fee (available for counter bettors)
```

### Two Rebate Modes

When countering a parlay, you choose how to receive your rebate:

<CardGroup cols={2}>
  <Card title="Autobet Rebate (Default)" icon="rocket">
    Rebate reduces your effective cost and **boosts your odds**.
    
    - Pay less upfront
    - Get better implied odds
    - More capital efficient
  </Card>
  <Card title="Cash Rebate" icon="money-bill">
    Rebate is paid directly to your wallet as **cash back**.
    
    - Pay full stake
    - Receive rebate separately
    - Immediate funds
  </Card>
</CardGroup>

### Example: Autobet Rebate

**Original Parlay:**
- User A stakes $100 (gross)
- Pays $5 total fee ($0.30 system + $4.70 dynamic)
- Net stake: $95

**Counter Opportunity:**
- Counter stake required: $80
- Rebate available: $4.70 (the dynamic fee)
- Your rebate share (100% counter): $4.70

**With Autobet Rebate:**
- Effective cost: $80 - $4.70 = $75.30
- You pay only $75.30 for $80 worth of exposure
- **Boosted odds** compared to fair value

### Rebate Scaling

Rebates scale proportionally:
- If you counter 50% of the parlay, you get 50% of the available rebate
- If live odds change, rebate scales with stake changes
- Multiple users can counter the same parlay (up to 100% total)

## Partial Countering

You don't have to counter the entire parlay:

- **Slider selection** - Choose 1-100% of the available amount
- **Multiple counters** - Multiple users can counter different portions
- **Live tracking** - See what percentage is already countered

## Key Rules

<Warning>
- You cannot counter your own parlays
- Counter parlays use USDC only (no coin bets)
- Odds may change if countering with live odds vs entry odds
</Warning>

## Cashout

Counter parlays can be cashed out before settlement:

- **Exit early** - Take profit or cut losses before games finish
- **Fair pricing** - Cashout value based on current probabilities
- **Rebate symmetry** - If you received autobet rebate, it's factored into cashout fee

## Why Counter Parlays?

<Steps>
  <Step title="Edge the House">
    Get odds better than fair value through rebates
  </Step>
  <Step title="High Win Rate">
    Counter probability is often 70-90% (since parlays are hard to hit)
  </Step>
  <Step title="Help the Protocol">
    Counter bets reduce vault exposure and risk
  </Step>
</Steps>

Counter parlays create a true peer-to-peer market where users can take either side of a parlay, with rebates incentivizing the counter side.
