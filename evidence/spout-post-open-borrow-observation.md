# Post-open Spout observations - 10 September 2026

These observations were recorded during the authenticated browser session after market opening on 10 September 2026. They are written observations; no archived screenshot is claimed for these particular screens. The separate public RPC receipt corroborates the fill and token balance, not every UI label below.

## Portfolio and filled holding

- Portfolio value: approximately $9.88.
- Holding: 0.045302013 NVDA; available borrowing approximately $4.94.
- Available cash: 10 test USDC.
- Filled holding matches the quantity delivered by the devnet fulfillment transaction at 13:31:09 UTC.

## Borrow reproducible path

1. Use the existing authenticated devnet account after the single 10 test-USDC NVDA order has filled.
2. Open Borrow and allow account data to load. The general Borrow page and NVDA-specific borrowing route both show:
   `CollateralType: unexpected length 213 (expected 165, or 149 pre-migration)`.
3. Select NVDA and enter 2.40 test USDC. The preview displays 24% LTV and health factor 4.12, with displayed available borrowing approximately $4.94.
4. Press Borrow once. The interface rejects before a wallet signature with:
   `Borrowing $2.40 exceeds the $0.00 this position supports`.

No loan transaction was signed or executed in this attempt. No debt was created, so partial repayment, full repayment and debt-associated collateral release could not be tested. This is an observed product blocker. The account-decoding error suggests a schema/configuration issue to investigate but does not establish a root cause.

## NVDA holding detail

The holding detail displayed average buy price $196.44 and gain approximately $0.99 / 11.1%. Observed order spend was 10 test USDC and delivered quantity was 0.045302013. Cash committed divided by delivered units is approximately $220.740743 per unit. The displayed average price implies approximately $8.8991 of cost basis. No fee adjustment, premium credit or other reconciliation explaining that difference was established in this session. This is an unexplained presentation discrepancy, not proof of asset loss or an independently verified accounting defect.

## Scope and privacy

All values are from Solana devnet and test assets without monetary value. No email address, access code, private key or login information is included. Brief transitory pre-load placeholder states are excluded from confirmed financial findings. Observations distinguish filled assets, available cash and inaccessible loan lifecycle.
