# DeFi Conservative Portfolio Setup Guide

## Overview
This is your Phase 1 portfolio: Battle-tested protocols, low risk, ~7% annual yield.

**Total Capital**: $5,000 - $10,000  
**Target Allocation**: 40% Aave / 30% Curve / 20% Lido / 10% Cash  
**Expected Yield**: 7% APY (~$35-70/month on $5-10K)  
**Risk Level**: Low (3/10)  
**Rebalance**: Quarterly (every 3 months)

---

## Before You Start

### What You'll Need
- MetaMask wallet (or similar: Ledger, Rabby, Coinbase Wallet)
- Stablecoins: USDC or USDT (buy from Coinbase, Kraken, or Kraken)
- Ethereum on Arbitrum chain (cheaper gas than mainnet)
- ~$50-100 for initial gas fees

### Network Setup
**Use Arbitrum, NOT mainnet Ethereum.** Gas costs are 50-100x cheaper.

1. Open MetaMask
2. Click network selector (top left)
3. Search for "Arbitrum One"
4. Add network
5. Buy USDC on Arbitrum (via Coinbase, then withdraw to Arbitrum)

---

## Step-by-Step Setup

### Position 1: Aave Lending (40% of capital)

**What you're doing**: Lending stablecoins to Aave, earning interest

**Steps**:
1. Go to `aave.com`
2. Click "Supply" 
3. Search for USDC
4. Connect wallet → approve USDC → enter amount (40% of your capital)
5. Click "Supply"
6. Watch it earn 5% APY

**Monitor**: Check APY monthly (it fluctuates 4-6%)

**Exit**: Click "Withdraw", unstake amount, send to wallet

**Gas cost**: $3-8 on Arbitrum

---

### Position 2: Curve Liquidity (30% of capital)

**What you're doing**: Providing liquidity to a stablecoin swap pool, earning trading fees

**Steps**:
1. Go to `curve.fi`
2. Network: Switch to Arbitrum
3. Find "3pool" (USDC/USDT/DAI pool)
4. Click "Deposit"
5. Enter 30% of capital in USDC
6. Click "Deposit" → approve → confirm
7. You now hold LP tokens (like a receipt)

**Monitor**: 
- Check APY weekly (it fluctuates 8-15%)
- Watch for impermanent loss (should be minimal on stablecoins)

**Exit**: Click "Withdraw", convert LP tokens back to USDC

**Gas cost**: $4-12 on Arbitrum

**Why Curve**: Specializes in stablecoins (no price volatility = no impermanent loss risk)

---

### Position 3: Lido Staking (20% of capital)

**What you're doing**: Staking ETH, earning staking rewards

**Steps**:
1. Buy ETH (convert some of your USDC to ETH on Uniswap)
2. Go to `lido.fi`
3. Click "Stake"
4. Enter 20% of capital worth of ETH
5. Click "Submit" → approve → confirm
6. You get stETH (represents your staked ETH + rewards)

**Monitor**: 
- APY is ~3.5% (stable)
- stETH accrues rewards automatically (no action needed)

**Exit**: Unstake stETH → wait 1-2 days → convert to ETH → sell for USDC

**Gas cost**: $8-20 on Arbitrum

**Why Lido**: Oldest, most battle-tested staking solution. Dominates the market.

---

### Position 4: Cash Buffer (10% of capital)

**What you're doing**: Keep stablecoins liquid for emergencies + rebalancing

**Steps**:
1. Keep 10% of capital as USDC in your wallet
2. Optional: Put in Aave for 5% yield while waiting

**Monitor**: Keep this as emergency fund. Don't deploy it unless rebalancing.

---

## Monthly Check-In (15 minutes)

1. **Open your portfolio tracker** (the HTML file)
2. **Log current values**:
   - Aave position value + current APY
   - Curve LP position value + current APY
   - Lido stETH value + APY
   - Cash balance

3. **Check alerts**:
   - Is any position underwater? (No, if you did this right)
   - Are yields still reasonable? (5%, 8-12%, 3.5%)
   - Any gas costs to log?

4. **Record everything** for taxes later

---

## Quarterly Rebalance (Every 3 Months)

After 3 months, your allocation will drift:
- If Aave pumped, it's now 45% instead of 40%
- If Curve tanked, it's now 25% instead of 30%

**Rebalance back to target**:

1. Calculate current total portfolio value
2. Calculate target amounts:
   - Aave: 40% of total
   - Curve: 30% of total
   - Lido: 20% of total
   - Cash: 10% of total

3. Move money:
   - If Aave is too high: withdraw $X, put in Curve or cash
   - If Curve is too low: withdraw from Aave, deposit to Curve
   - Rebalance back to target allocation

**Why rebalance**: 
- Forces you to "sell high, buy low"
- Keeps risk constant
- Compound effect over years

---

## What to Watch For (Red Flags)

| Warning Sign | What It Means | Action |
|---|---|---|
| APY jumps to 50%+ | Protocol is desperate for capital | Exit slowly |
| Protocol launches token | They're incentivizing you to lock capital | Monitor closely |
| Your position loses 20%+ | Impermanent loss (Curve) or price crash (Lido) | Don't panic; check protocol news |
| Can't withdraw funds | Smart contract bug or hack | Exit immediately if you can |
| Gas fees > $100 | Network congestion | Wait for quiet time or move capital |

---

## Tax Implications

**You owe taxes on**:
- Yield earned (if you harvest it) - taxed as income
- Price appreciation (if stETH/tokens gain value) - capital gains
- Trading fees from LP positions - income

**You DON'T owe taxes on**:
- Unrealized gains (as long as you hold)
- Swapping between stablecoins (1:1 = no gain/loss)

**Do this monthly**: Log all activity in a spreadsheet:
- Date | Action | Amount | Token | Cost Basis | Gas Fee

At year-end, export to your tax software or give to accountant.

---

## Year 1 Projections

**Starting capital**: $7,500

| Month | Portfolio Value | Yield Earned | Total Value |
|---|---|---|---|
| 0 | $7,500 | $0 | $7,500 |
| 3 | $0 | $131 | $7,631 |
| 6 | $0 | $267 | $7,767 |
| 9 | $0 | $406 | $7,906 |
| 12 | $0 | $550 | $8,050 |

**By year 5**: $9,530 (27% gain)  
**By year 10**: $14,675 (96% gain)

Not exciting, but bulletproof.

---

## Phase 2: Learning Track

While your portfolio compounds, spend 1 hour per week learning:

### Week 1: Aave Deep Dive
- Read: How Aave lending works (5 min)
- Read: Aave risks & past hacks (5 min)
- Action: Check Aave's audit reports on GitHub (10 min)
- Action: Check current utilization rate (how much capital is borrowed) (5 min)
- Quiz: Could Aave be hacked tomorrow? Why/why not?

### Week 2: Curve Deep Dive
- Read: How AMM liquidity pools work (10 min)
- Read: What is impermanent loss? (10 min)
- Action: Simulate adding/removing liquidity on Curve (5 min)
- Action: Check historical APY data for 3pool (5 min)
- Quiz: If USDC pumps 20% and DAI stays flat, what happens to your LP position?

### Week 3: Lido Deep Dive
- Read: How Ethereum staking works (10 min)
- Read: Lido's risks & centralization concerns (10 min)
- Action: Check stETH discount/premium vs ETH (5 min)
- Action: Monitor validator count (5 min)
- Quiz: What could cause stETH to devalue relative to ETH?

### Week 4: Risk Assessment
- Read: Past DeFi hacks and what caused them (15 min)
- Read: How to read smart contract audits (10 min)
- Action: Find audit reports for Aave, Curve, Lido (10 min)
- Quiz: Which protocol has the highest risk of failure?

**Repeat this monthly** with new protocols (Yearn, Compound, MakerDAO, etc.)

---

## When to Pivot to Phase 3

After 3-6 months, one of these will feel true:

1. **"This is boring"** → Move to arbitrage bot or protocol scouting
2. **"I understand DeFi now"** → Move to more aggressive strategies
3. **"This is working great"** → Keep it for 10 years, stack boring gains

There's no wrong answer. The conservative portfolio is your foundation. Build from there when you're ready.

---

## Questions to Ask Yourself Monthly

- [ ] Do I understand why each protocol is safe?
- [ ] Have I checked the audit reports?
- [ ] Do I know my current APY on each position?
- [ ] Have I calculated my unrealized gains/losses?
- [ ] Am I tracking this for taxes?
- [ ] Would I still own this if APY dropped to 2%?
- [ ] Can I explain this portfolio to someone else in under 5 minutes?

If you answer "no" to any, that's your learning focus for the week.

---

## Resources

**Protocol Monitoring**:
- `defillama.com` - See all TVL (total value locked) and yields
- `apy.vision` - Real-time APY tracking
- `defi-pulse.com` - Protocol health metrics

**Learning**:
- `ethereum.org/en/developers/docs` - DeFi basics
- Protocol whitepapers (search "Aave whitepaper", etc.)
- `YouTube: @Bankless` - DeFi explainers (good for visual learners)

**Tax**:
- `koinly.io` or `cointracker.io` - Auto-import transactions, calculate taxes
- Keep a spreadsheet of all activity

---

## Your Checklist: This Week

- [ ] Set up MetaMask
- [ ] Buy $5-10K USDC
- [ ] Bridge to Arbitrum
- [ ] Deposit 40% to Aave
- [ ] Deposit 30% to Curve 3pool
- [ ] Convert 20% to ETH and stake on Lido
- [ ] Keep 10% as USDC buffer
- [ ] Download portfolio tracker HTML
- [ ] Log first position values
- [ ] Set calendar reminder: Rebalance in 3 months

**Estimated time**: 1-2 hours  
**Estimated cost**: $30-60 in gas fees

That's it. Start there.
