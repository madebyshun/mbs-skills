# Example — web3-ux-audit

## Input

> Audit this Web3 product. It's a DEX on Base — users connect wallet, select tokens, enter amount, and swap. There's no slippage setting visible by default. Error messages just say "Transaction failed." The onboarding assumes users already have a Base wallet.

## Output

**Wallet Connection**
Works if you already have MetaMask or Coinbase Wallet. But there's no fallback for users on mobile without a browser wallet, and no WalletConnect option mentioned. For a Base DEX, Coinbase Wallet deeplink + WalletConnect v2 are table stakes.

**Onboarding Flow**
Assuming users have a Base wallet is the single biggest drop-off point. Most users arrive with ETH on mainnet. You need a visible bridge prompt or at minimum a "Don't have funds on Base?" helper link. Silence here reads as broken to new users.

**Transaction Clarity**
Hiding slippage by default is fine — but it needs to be accessible in one tap, not buried. When a swap is likely to fail (low liquidity, high price impact), warn the user *before* they hit confirm, not after. "Transaction failed" with no reason is the worst possible error message — show: what failed, why, and what to do next.

**Error Handling**
Three error states you must handle explicitly: insufficient gas, slippage exceeded, and low liquidity. Each needs a plain-language message and a clear next action.

**Trust & Safety Signals**
No audit badge, no TVL displayed, no "powered by" protocol transparency. A first-time user has no reason to trust this with real money. Add at minimum: an audit link, total volume processed, and token contract verification links.

---

**Biggest UX debt:** The bridge gap for non-Base users and "Transaction failed" errors — fix these first.
