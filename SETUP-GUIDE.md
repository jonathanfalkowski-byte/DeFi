# DeFi Conservative Portfolio Setup Guide

> **Not financial advice.** This is an educational guide, not a recommendation. DeFi carries real risk of total loss (smart-contract bugs, hacks, stablecoin depegs, phishing). Only use money you can afford to lose, and check current protocol details yourself before acting. Yields and fees quoted here are illustrative, not guaranteed.

## Overview
This is your Phase 1 portfolio: established protocols, lower risk than most of DeFi (but not risk-free), roughly 5-6% blended yield in a typical market.

**Total Capital**: $5,000 - $10,000  
**Target Allocation**: 40% Aave / 30% Curve / 20% Lido / 10% Cash  
**Expected Yield**: ~5.7% blended APY (about $25-50/month on $5-10K), variable  
**Risk Level**: Moderate-low (see "Risks" below). The 20% ETH leg is volatile.  
**Rebalance**: Quarterly (every 3 months)

How the blended figure is calculated (0.40 x 5% + 0.30 x 10% + 0.20 x 3.5% + 0.10 x 0%): 2.0 + 3.0 + 0.7 + 0 = **5.7%**. If the cash buffer sits in Aave at ~5%, it is ~6.2%. The Curve figure is an optimistic assumption; stablecoin pools often yield less, so treat 5.7% as a ceiling-ish estimate and compare it with a T-bill or money-market fund, which carries no smart-contract risk.

---

## Risks (read before you deposit)

- **Smart-contract risk**: Audits reduce but never eliminate the chance of a bug or exploit. Even the biggest protocols have had incidents.
- **Stablecoin depeg**: USDC, USDT and DAI have each traded below $1 before (USDC in March 2023). Your "stable" positions are only as stable as the issuer.
- **stETH can trade below ETH**: it did in 2022. Withdrawals from Lido go through a queue that can take days.
- **ETH price risk**: The Lido leg is exposed to ETH's price, so a 50% ETH drop costs you about 10% of the portfolio.
- **Layer 2 / bridge risk**: Arbitrum adds sequencer and bridge risk on top of the protocol's own risk.
- **Phishing and wallet theft**: the most common way retail users lose funds. See "Wallet Security".
- **Rates are variable**: Aave and Curve yields move with market demand and can fall well below the numbers here.

No strategy here is "bulletproof"; the goal is to keep risk understood and sized, not eliminated.

---

## Wallet Security (do this first)

- **Bookmark every protocol site** (app.aave.com, curve.fi, lido.fi) and only open them from the bookmark. Never click links from search ads, DMs, or emails. Fake clones of these sites are common.
- **Never type your seed phrase into any website or app prompt.** No protocol, support agent, or "wallet validator" will ever need it.
- **Use a hardware wallet** (Ledger, Trezor) for anything beyond pocket money, and keep the seed phrase offline.
- **Limit token approvals**: approve the exact amount you are depositing rather than "unlimited", and periodically review and revoke old approvals at `revoke.cash`.
- **Do a small test transaction** ($10-20) before moving the full amount.
- **Verify contract and URL details** before signing; read what MetaMask shows you instead of clicking through.

---

## Before You Start

### What You'll Need
- MetaMask wallet (or similar: Ledger, Rabby, Coinbase Wallet)
- Stablecoins: USDC or USDT (buy from Coinbase or Kraken)
- A little ETH on Arbitrum for gas, plus ETH for the Lido position (see below)
- ~$20-50 for initial gas fees on Arbitrum; more if you stake on Ethereum mainnet

### Network Setup
**Use Arbitrum for Aave and Curve.** Gas is typically a small fraction of mainnet's. **Lido staking is the exception**; see Position 3.

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
1. Open the Aave app from your bookmark (`app.aave.com`)
2. Switch to the Arbitrum market
3. Click "Supply" and search for USDC
4. Connect wallet, approve the exact amount of USDC, enter amount (40% of your capital)
5. Click "Supply"
6. Expect roughly 4-6% APY (variable)

**Monitor**: Check APY monthly (it fluctuates)

**Exit**: Click "Withdraw" on the supplied asset and send the funds to your wallet

**Gas cost**: usually a few dollars or less on Arbitrum

---

### Position 2: Curve Liquidity (30% of capital)

**What you're doing**: Providing liquidity to a stablecoin swap pool, earning trading fees

**Note on pools**: The classic **3pool (USDC/USDT/DAI) lives on Ethereum mainnet**. On Arbitrum, Curve's stablecoin pool is the **2pool (USDC/USDT)**. Confirm the current pool list on `curve.fi` and pick a large, long-running stablecoin pool; avoid new pools with unusually high APY.

**Steps**:
1. Open Curve from your bookmark (`curve.fi`)
2. Network: Switch to Arbitrum
3. Find the main USDC/USDT stablecoin pool (2pool) and check its TVL, age, and audits
4. Click "Deposit"
5. Enter 30% of capital (the pool takes USDC and USDT; a single-sided USDC deposit is fine)
6. Approve, then confirm the deposit
7. You now hold LP tokens (like a receipt). If the pool offers a gauge, staking the LP token there earns extra CRV rewards but adds another contract to trust

**Monitor**:
- Check APY monthly (stablecoin pools commonly yield low single digits, sometimes more)
- Watch the pool's balance: if one coin is far below $1 or the pool is badly lopsided, that is a depeg warning

**Exit**: Click "Withdraw", convert LP tokens back to USDC

**Gas cost**: usually a few dollars on Arbitrum

**Why Curve**: Specializes in stablecoins, so there is little price divergence between assets. Impermanent loss is small **unless one stablecoin depegs**, in which case you can end up holding the weaker coin.

---

### Position 3: Lido Staking (20% of capital)

**What you're doing**: Staking ETH, earning staking rewards

**Important**: Staking directly on `lido.fi` happens on **Ethereum mainnet**, so it costs mainnet gas. On Arbitrum, Lido exists only as **wstETH** (wrapped stETH) which you buy on a DEX rather than stake directly. Pick one:

- **Option A (cheaper for small amounts)**: On Arbitrum, swap USDC/ETH for **wstETH** on a major DEX (Uniswap, Camelot). Check the price is close to the wstETH/ETH rate and the pool is deep.
- **Option B (direct staking)**: Bridge or withdraw ETH to Ethereum mainnet, stake at `lido.fi`, receive stETH. Expect noticeably higher gas; this makes more sense at the larger end of the capital range.

**Steps (Option B shown)**:
1. Hold ETH worth 20% of capital
2. Open Lido from your bookmark (`lido.fi`)
3. Click "Stake", enter the amount
4. Confirm the transaction
5. You get stETH (represents your staked ETH + rewards; the balance grows daily)

**Monitor**:
- APY is ~3-4% and varies
- Check the stETH/ETH market price occasionally; a persistent discount is a warning sign

**Exit**: Request a withdrawal from Lido (queue time varies from about a day to several days) or sell stETH/wstETH on a DEX for ETH, then swap to USDC.

**Gas cost**: A few dollars on Arbitrum for a DEX swap; mainnet staking can cost much more depending on network congestion.

**Why Lido**: The largest and longest-running liquid staking protocol. Its size also means concentration risk for Ethereum itself.

**Be aware**: This leg is priced in ETH, so its dollar value moves with the ETH price. It is not a stable position.

---

### Position 4: Cash Buffer (10% of capital)

**What you're doing**: Keep stablecoins liquid for emergencies + rebalancing

**Steps**:
1. Keep 10% of capital as USDC in your wallet
2. Optional: Put in Aave for ~5% yield while waiting

**Monitor**: Keep this as emergency fund. Don't deploy it unless rebalancing.

---

## Monthly Check-In (15 minutes)

1. **Open your monthly monitor** (`monthly-monitor.html`)
2. **Log current values**:
   - Aave position value + current APY
   - Curve LP position value + current APY
   - Lido stETH/wstETH value + APY
   - Cash balance

3. **Check alerts**:
   - Is any position below what you put in? (Compare against cost basis.)
   - Are yields still reasonable? (about 5%, 2-10%, 3-4%)
   - Any gas costs to log?

4. **Record everything** for taxes later

---

## Quarterly Rebalance (Every 3 Months)

After 3 months, your allocation will drift:
- If Aave grew faster, it's now 45% instead of 40%
- If ETH fell, Lido may be 15% instead of 20%

**Rebalance back to target**:

1. Calculate current total portfolio value
2. Calculate target amounts:
   - Aave: 40% of total
   - Curve: 30% of total
   - Lido: 20% of total
   - Cash: 10% of total

3. Move money:
   - If a position is too high: withdraw the excess and add to the one that is too low (or to cash)
   - Check that gas and swap costs are small relative to the amount moved; skip tiny rebalances

**Why rebalance**: 
- Trims what has grown, adds to what has lagged
- Keeps risk close to your intended mix
- Note that each move may be a taxable event (see Tax Implications)

---

## What to Watch For (Red Flags)

| Warning Sign | What It Means | Action |
|---|---|---|
| APY jumps to 50%+ on a normally stable pool | Something unusual: incentives, a depeg, or a risk the market is pricing in | Investigate before adding; consider withdrawing |
| Protocol launches token / incentives | Yield may be subsidized and temporary | Monitor closely |
| A stablecoin trades below ~$0.98 | Depeg risk | Review exposure to that coin; consider withdrawing |
| stETH trades at a persistent discount to ETH | Stress in staking market | Don't add; reassess |
| Your position is worth much less than you put in | Price move (ETH) or loss in a pool | Check protocol news first; don't act on panic |
| Can't withdraw funds, or the UI behaves oddly | Possible exploit, outage, or a fake site | Stop, verify you're on the correct site, check official channels. If a real exploit is confirmed, withdraw whatever is still possible |
| Gas fees unusually high | Network congestion | Wait for a quiet time before moving funds |

---

## Tax Implications

**Tax rules differ by country and change over time. This is a general outline, not tax advice. Talk to a qualified tax professional.** The notes below describe the US as an example.

**Generally taxable**:
- Interest and staking rewards, often as income when received
- Trading fees from LP positions
- **Any swap or disposal**, including USDC to ETH and ETH back to USDC, produce a capital gain or loss, even if small
- Withdrawing from a pool can be a disposal of the LP token

**Generally not taxable**:
- Simply holding an asset whose price has moved (unrealized gains)
- Moving your own tokens between your own wallets

**Do this monthly**: Log all activity in a spreadsheet:
- Date | Action | Amount | Token | Cost Basis | Gas Fee

At year-end, export to tax software or give to your accountant.

---

## Year 1 Projections

**Assumptions**: starting capital $7,500; flat 5.7% blended APY, compounded; no ETH price change; no fees or taxes. Real results will differ.

| Month | Portfolio Value | Yield Earned (cumulative) |
|---|---|---|
| 0 | $7,500 | $0 |
| 3 | $7,605 | $105 |
| 6 | $7,711 | $211 |
| 9 | $7,818 | $318 |
| 12 | $7,928 | $428 |

**By year 5**: about $9,895 (+32%)  
**By year 10**: about $13,056 (+74%)

These are a best-case-ish steady line. In practice yields move, ETH moves, and a single exploit or depeg can erase years of yield.

---

## Phase 2: Learning Track

While your portfolio compounds, spend 1 hour per week learning:

### Week 1: Aave Deep Dive
- Read: How Aave lending works (5 min)
- Read: Aave risks & past incidents (5 min)
- Action: Check Aave's audit reports on GitHub (10 min)
- Action: Check current utilization rate (how much capital is borrowed) (5 min)
- Quiz: Could Aave be hacked tomorrow? Why/why not?

### Week 2: Curve Deep Dive
- Read: How AMM liquidity pools work (10 min)
- Read: What is impermanent loss? (10 min)
- Action: Simulate adding/removing liquidity on Curve (5 min)
- Action: Check historical APY data for your pool (5 min)
- Quiz: If one stablecoin in the pool depegs by 20%, what happens to your LP position?

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

**Repeat this monthly** with new protocols (Yearn, Compound, Sky/MakerDAO, etc.). Use `protocol-evaluation.html` as a starting checklist, not a verdict.

---

## When to Pivot to Phase 3

After 3-6 months, one of these will feel true:

1. **"This is boring"** → Move to arbitrage bot or protocol scouting
2. **"I understand DeFi now"** → Move to more aggressive strategies
3. **"This is working great"** → Keep it for years, stack steady gains

There's no wrong answer. The conservative portfolio is your foundation. Build from there when you're ready.

---

## Questions to Ask Yourself Monthly

- [ ] Do I understand why each protocol is considered safe, and what could go wrong?
- [ ] Have I checked the audit reports?
- [ ] Do I know my current APY on each position?
- [ ] Have I calculated my unrealized gains/losses?
- [ ] Am I tracking this for taxes?
- [ ] Would I still own this if APY dropped to 2%?
- [ ] Can I explain this portfolio to someone else in under 5 minutes?

If you answer "no" to any, that's your learning focus for the week.

---

## Resources

**Protocol Monitoring** (verify each is still maintained):
- `defillama.com` - TVL, yields, and protocol/hack data
- `l2beat.com` - Layer 2 risk assessments (Arbitrum)
- `rekt.news` - Exploit history
- `revoke.cash` - Review and revoke token approvals

**Learning**:
- `ethereum.org/en/developers/docs` - DeFi basics
- Protocol docs and audit pages (search "Aave audits", etc.)

**Tax**:
- `koinly.io` or `cointracker.io` - Auto-import transactions, calculate taxes
- Keep a spreadsheet of all activity

---

## Your Checklist: This Week

- [ ] Set up your wallet and secure the seed phrase offline
- [ ] Bookmark the protocol sites
- [ ] Buy $5-10K USDC
- [ ] Send a small test transaction first
- [ ] Bridge to Arbitrum
- [ ] Deposit 40% to Aave
- [ ] Deposit 30% to a Curve stablecoin pool
- [ ] Convert 20% to ETH and stake on Lido (or buy wstETH on Arbitrum)
- [ ] Keep 10% as USDC buffer
- [ ] Open the monthly monitor and log first position values
- [ ] Set calendar reminder: Rebalance in 3 months

**Estimated time**: 1-2 hours  
**Estimated cost**: roughly $20-60 in gas on Arbitrum; more if staking on mainnet

Start small, verify each step, and scale up only once the first deposits behave as expected.
