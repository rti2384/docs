# Protecting Liquidity Providers

LP funds are centralized in a USDC vault with ERC‑4626‑like share accounting. When a trade is filled, the market computes the maximum potential profit liability and reserves it immediately in the vault. Withdrawals respect outstanding liabilities, and a per‑market exposure cap prevents outsized risk.
