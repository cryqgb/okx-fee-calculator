# OKX fee calculator: estimate spot and futures trading costs before placing an order

An OKX fee calculator is useful when it answers a practical question: how much will a trade cost at *your* fee rate, for *your* order size and trading product? A calculator that assumes one universal rate can give a tidy number and still be wrong for your account.

OKX’s fees depend on the product, your fee tier, and whether each fill is executed as a maker or taker. The exchange’s official fee page lists its fee schedule, while its help center explains how to check the rate that applies to your account and how fees are calculated. For an estimate, start with the rate shown for your account and pair, then apply the relevant formula below.

## How to calculate OKX trading fees

For an order-book trade, the basic calculation is:

> **Trading fee = fee rate × executed trade value**

The fee applies when an order fills. A partially filled order incurs fees on the filled portion, not the part that remains open or is cancelled. If you trade in several fills, calculate each fill using its actual price and execution type, then add the fees together.

For a quick estimate, you can use:

text
Estimated fee = trade value × fee rate


Enter the fee rate as a decimal. For example, `0.10%` becomes `0.001`. If a hypothetical trade has a value of 1,000 USDT at that rate:

text
1,000 × 0.001 = 1 USDT


That arithmetic is simple. Finding the right rate is the part that needs care.

## Maker and taker fees: what the calculator needs to know

A **taker** order matches against an order already on the order book. A **maker** order rests on the book and adds liquidity until another order matches it. The fee depends on how the order actually executes, not just on the order type you selected.

Market orders usually execute as taker orders. A limit order can be either: if it matches immediately, it is treated as taker; if it rests on the book and fills later, it is treated as maker. A limit order is not automatically a maker order.

For that reason, a useful calculator should let you compare at least two scenarios:

| Scenario | Formula | Example using an illustrative rate |
| --- | --- | --- |
| Taker execution | Trade value × taker rate | 1,000 USDT × 0.10% = 1 USDT |
| Maker execution | Trade value × maker rate | 1,000 USDT × 0.08% = 0.80 USDT |

These rates are **example inputs, not a statement of current rates for every OKX user or trading pair**. Your actual rates may differ by account, instrument, pair, region, and fee tier. Check the rate shown while logged in before relying on a number. OKX says logged-out fee information may not match the rates attached to your account.

## Spot fee calculator: worked example

For spot and margin order-book trades, OKX describes the fee as the applicable rate multiplied by the amount of crypto bought or sold when the order fills. In practice, the fee’s currency can follow the direction of the trade and the fill details.

Suppose you buy 0.02 BTC at a hypothetical price of 50,000 USDT per BTC. The trade value is:

text
0.02 BTC × 50,000 USDT = 1,000 USDT


If the applicable taker rate for this example were 0.10%, the estimated fee value would be:

text
1,000 USDT × 0.10% = 1 USDT equivalent


That is a convenient way to estimate the cost in quote-currency terms. The actual fee may be deducted in the asset received or in another currency determined by the trade. On a buy, OKX notes that the fee can be taken from the crypto bought, leaving you with slightly less than the gross order quantity. On a sell, it can be taken from the sale proceeds. Check the individual fill details for the recorded fee and its currency.

If the trade executes in multiple chunks at different prices, use each fill’s actual value rather than multiplying the requested order size by a single assumed price. The estimate can differ from the final charge because the order may be partially filled, fill at varying prices, or execute as both maker and taker.

## Futures fees: calculate from position value, not margin

A common calculator mistake is to multiply the fee rate by the margin deposited. For futures, the trading fee is based on the executed contract value, not simply the collateral used to open the position. Leverage can make the fee look larger relative to your margin because it lets you open a larger position.

For a USDT- or USDC-margined contract, OKX gives the general calculation as:

text
Fee = fee rate × number of contracts × contract multiplier × contract size × fill price


The contract details matter, so do not assume every instrument uses the same contract size. As a simplified example, imagine a position with a notional value of 20,000 USDT and a hypothetical taker rate of 0.05%:

text
20,000 USDT × 0.05% = 10 USDT


If the position used 2,000 USDT of margin at 10× leverage, the estimated trading fee is still calculated against the 20,000 USDT position value, not the 2,000 USDT margin. Opening and closing orders can both incur trading fees when they fill.

Coin-margined contracts use a different formula and may settle the fee in the traded cryptocurrency. Options also have their own fee rules and caps. A calculator meant for spot trading should not be used as-is for futures, swaps, or options; select the correct product and enter its contract specifications.

## The OKX fee calculator checklist

Before trusting an estimate, confirm these inputs:

1. **Product:** spot, margin, futures, perpetual swap, or options.
2. **Trading pair or contract:** fee rates and contract specifications can differ.
3. **Your account’s current fee tier:** don’t substitute a rate from an old article or an unlogged pricing page.
4. **Execution type:** estimate maker and taker separately if you do not know how the order will fill.
5. **Executed size and price:** use notional value for the filled quantity, not merely the amount of margin.
6. **Other costs:** for derivatives, account separately for funding and any applicable settlement or liquidation charges.

This list also explains why an online OKX fee calculator may not match your eventual order history. A third-party tool can do the multiplication correctly while using the wrong fee rate, product assumptions, contract size, or fee currency.

## Where to find your actual OKX fee rate

OKX’s help center says you can check your account’s fee tier and schedule after logging in:

- On the website, go to **Assets → My trading fees**.
- In the app, open **Account settings → Profile → Trading fee tier**.
- For a specific instrument, check the **Fees** information in the order placement panel or the app’s fee rules for that market.

The order panel is especially useful when estimating a single trade because it shows the fee rate that applies to the selected pair and account. The exact charge is available after execution in order history, under the fill or transaction details.

Your fee tier can change with qualifying trading volume or asset holdings over the relevant period. OKX says tier levels are based on activity and holdings over the past 30 days, and rates differ across instruments. A saved calculator sheet should therefore treat the rate as an input to review, not a permanent constant.

## Trading fees are not the whole cost

A fee calculator estimates trading fees. It does not necessarily capture every cost or difference between the price you expected and the price you received.

For example, the spread is the difference between available buy and sell prices. If an order fills across multiple price levels, the average execution price may also differ from the best price you saw before placing it. OKX says its Convert and express Buy/Sell flows quote an all-in price rather than displaying a separate order-book maker or taker fee in the same way. Compare the quoted price with the market price when judging the overall cost.

For perpetual futures, funding is separate from the trading fee. It is exchanged between long and short holders according to the funding rate and settlement schedule; it is not part of the basic order-book fee calculation. Depending on the contract and your position, settlement, liquidation, or other product-specific rules may also matter.

Deposits, withdrawals, and payment-provider charges are separate again. An estimate for a buy or sell on the order book should not be presented as an estimate of every cost involved in moving money in or out of an account.

## Does the CASH20 invitation code lower trading fees?

The supplied invitation link uses the code **CASH20**. The information provided with the link describes a 20% referral commission, but that is not the same claim as a 20% discount on a trader’s fees. Don’t subtract 20% from your calculator result unless the registration flow or your account explicitly confirms a user-facing fee benefit and its conditions.

If you plan to register, review the terms presented for your location and account before proceeding. Availability, verification requirements, products, and promotional conditions can vary. You can open the invitation page here: [👉 View the OKX invitation offer](https://okx.com/join/CASH20).

## Common questions

### Is there one OKX fee rate for everyone?

No. Rates vary by product and fee tier, and the rate shown for a logged-in account may differ from information shown to logged-out visitors. Check the rate for your own account and the specific pair or contract.

### Does a limit order always pay the maker fee?

No. A limit order that immediately matches an existing order can execute as taker. It is treated as maker only when it rests on the order book and later matches.

### Are futures fees calculated on leverage or margin?

The fee is calculated on the executed position value using the contract’s rules. Margin and leverage determine how the position is collateralized, but the fee is not simply the fee rate multiplied by the margin amount.

### Why does the fee in order history differ from my estimate?

The actual execution may have used a different rate or price than your inputs, filled in several parts, or included maker and taker executions. Compare the fee with the details for each fill rather than relying only on the order’s original size.

### Can a fee calculator predict my exact total cost?

It can estimate the trading fee when you supply the right rate, product, and execution value. It cannot know the final fill price or execution type in advance, and it may omit spread, funding, withdrawal costs, or other product-specific charges. Treat the result as an estimate, then verify the actual fee in order history.

## Bottom line

For an OKX fee calculator to be useful, it needs more than a trade amount. Use your account’s current rate, distinguish maker from taker, calculate derivatives using contract value rather than margin, and keep funding or spread separate from the trading fee. Then compare the estimate with the fill details after execution. That gives you a number you can audit instead of a reassuring percentage copied from somewhere else.
