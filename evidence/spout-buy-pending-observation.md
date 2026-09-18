# Spout after-hours order observation

Observed 10 September 2026, approximately 00:16–00:18 UTC, in the authenticated beta on Solana devnet. Only test assets without monetary value were used.

- Entered 10 USDC, NVDA, leverage 1x. Pressed Buy once after legitimate fee funding.
- Confirmation: `Order confirmed`; `Your purchase has been confirmed`; `You own 0.04 NVDA`; `Bought at $223.77`; `Total paid $10.00`.
- The same dialog also stated: `Market is closed. Your order fills at 9:30 AM ET, 10 Sep`.
- Portfolio: 10 USDC remaining, overview $0.00, No Holdings, No Positions.
- Open order: NVDA `HXBz…o4vi`, Buy, $10.00, Executing, Sep 9, Cancel action available. Cancel was not pressed; no second purchase was made.
- Market help: closed; pending orders fill from Thursday 9:30 AM ET, equivalent to 10 September 13:30 UTC / 08:30 Bogota.

The finalized transaction is [W3o7ng…H3DXL8 on Solana devnet](https://explorer.solana.com/tx/W3o7ngR4ciS7W2eF8RpRd4GHgXTK8YKJCUGzXEcoCJYZg5gyut6q1NrPU2GFG9CWeNZKWNSMpJae2vPGuH3DXL8?cluster=devnet), slot 495881855, blockTime 1788999376, execution error null and fee 5000 lamports. Saved raw response: `spout-buy-order-devnet-receipt.json`.

Its log identifies `PlaceBuyOrder` in program `SPoRXgsB4gWZmWPwyndoRWQrmZXKUc7o7oPMdkkGRcG`. The wallet's test-USDC account decreased from 20 to 10; the program destination received 10. The wallet retained 999995000 lamports. The order account is `HXBzeuVWHWfVWojSHhWbhFRTztdJqzAoGrTDJ5RMo4vi`.

This proves order placement. It does not prove a stock fill, real-world share ownership, collateralization or a loan. The program log explicitly identifies a devnet mock for KYC; no real KYC or regulated custody was tested.

At approximately 00:23 UTC, Portfolio → Transaction History finished loading and displayed a row under Today: time `7:16 PM`, activity `Bought NVDA`, details `$10.00 order placed`, amount `$10.00`, value `$0.00`, fees `--`, status `Executing`. Available test cash remained 10 USDC. The details identify order placement while the activity wording still suggests a completed purchase. The `--` fee field was not interpreted as a zero fee; the actual network fee is recorded above from the receipt.

## Feedback

Use `Order accepted — awaiting market open` and `Estimated shares` until the fill is observed. Show the funds committed to pending orders alongside available cash and acquired holdings. Replace an undifferentiated `Executing` state with a scheduled state and fill timing when the market is closed. Preserve the order identifier and link to the actual transaction so readers can distinguish on-chain acceptance from the later fill.
