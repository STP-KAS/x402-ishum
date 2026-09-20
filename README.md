> **Experimental only. Not a product.** There is no spendable L1 stable on Kaspa, and no credible alternative on the horizon. Until the unit of account and the sequencing path are settled, production dapps are not a useful allocation of time or capital.
>
> Do not use wallet integrations on this GitHub. STP remains a clown. [DISCLAIMER.md](DISCLAIMER.md)

# x402 / ishum

**This name is a comparison. Ishum is not x402.**

Repo name exists because the desk asked for `x402/ishum`. The first sentence is the review: **do not put a till in the 402 row.**

Subject: [STP-KAS/ishum](https://github.com/STP-KAS/ishum)
Compared to: [elldeeone/kaspa-x402](https://github.com/elldeeone/kaspa-x402) `v1.0.0-rc.1`
Pins: [kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) freeze 13 Sep 2026
Date: 2026-09-14
Not Kaspa core. Not a KIP.

Sister reports: [x402-vs-grok](https://github.com/STP-KAS/x402-vs-grok) · [402-is-not-x402](https://github.com/STP-KAS/402-is-not-x402)

---

## grok test

Local tree `C:\Users\<user>\Documents\kaspa\ishum` matches GitHub `STP-KAS/ishum` (pushed 11 Sep 2026).

| Probe | Result |
| --- | --- |
| String `x402` / `PAYMENT-REQUIRED` / `PAYMENT-SIGNATURE` / `x402Version` | **Zero hits** |
| HTTP 402 status | **Not spoken.** Invoice API is 200 / 401 / 400 / 404 |
| `scheme: exact` / `batch-settlement` | Absent |
| Live settlement | **KAS only.** Watch `api.kaspa.org`. `kaspa:` URI. Paste txid. Process never holds keys. |
| kUSD | `Live: false`. No asset, no covenant, no reserves. Demo settle without `ISHUM_DEMO` |
| USDT | `KindGuest`, `Issuer: "Tether"`, `Freeze: true`, `Live: false`. Same demo button |
| Default store | `storecfg.Init` turns **all three** rails on if none selected |
| Confirmations | `virtual blueScore − accepting_block_blue_score`. kaspa-x402 **refuses** that subtraction |
| README “~1s blocks; 10 conf ≈ 10 seconds” | **Stale.** Master-file pin is **10 BPS** (Crescendo). 10 selected-chain confirmations is ~1 second of blocks, and is still not finality |
| Matching | payload `message=<invoice-id>` first; else sompi salt `0–999` + last-20-tx poll. `Claim` can take **any** inbound tx to the store address |

Did not run a shop with real mainnet KAS. Did not demo-settle kUSD (that would only prove the button).

---

## grok analyse

**Ishum is a BTCPay-shaped till.** Keypad / cart → invoice JSON file → QR → webhook. Track 1 POS. Unit of account is **EUR/USD**. Settlement that exists is **native KAS**.

**kaspa-x402 is a protocol binding.** Agents and APIs. Sompi strings. `PaymentRequired.accepts`. Exact one-shot or escrow vouchers. TN10 RC.

They share one honest idea: the desk should not hold the merchant’s keys. They do not share a wire format.

| | Ishum | kaspa-x402 |
| --- | --- | --- |
| Job | Human coffee / invoice | Machine-payable call |
| Envelope | Greenfield JSON | x402 v2 |
| Asset live | KAS | KAS |
| Asset seats | kUSD, USDT | none (and must not grow them) |
| Covenant | none | escrow-v4 on batch |
| Finality story | blue-score delta, “~10s” | `accepted` vs 30 selected-chain (policy) |

Sutton 11 Sep is used as décor. “Store ≈ Core, invoice ≈ pair/quote” is a file-per-invoice matcher. It is not Argent ICC. Related sub-series for one coffee ticket is real. It is not a protocol.

---

## grok reasoning

Three boxes, not one:

1. **Bind x402 v2** = speak the envelope. That is elldeeone. Ishum does not.
2. **Fourth envelope** = a new 402 dialect. Ishum does not emit 402, so the **binary** is not a fourth envelope.
3. **Till that quotes fiat** = Ishum.

The danger is **naming**. `x402-ishum` on GitHub puts a till in the 402 catalog. That is how you get a fourth envelope without writing one. The master-file kill-if is “a fourth 402 envelope · calling k402 x402.” Same kill for calling Ishum x402.

**kUSD** is a reserved seat: “a Kaspa dollar if someone posts reserves.” There is no issuer and no collateral UTXO. Checkout still shows the rail and a **Mark settled (demo)** button. That is a delusional Kaspa-dollar *chair*, not a peg. Master file: dollars **0–0**. Do not invent kUSD as a peg.

**USDT guest** is honest about freeze. It is still a **centralised stablecoin on the keypad**. Master-file principle: skip centralised stablecoins for dapps. Default-on `EnableUSDT` teaches a king as checkout even while the README refuses Tether-as-gas.

**USDT in does not un-decentralize GHOSTDAG.** True and cheap. It also does not make USDT Kaspa money.

Paste-txid “claims any payment to this address” is a real collision. 1000 sompi salt is not an HD address.

---

## grok advice

1. Public one-liner: *self-hosted Kaspa till; quotes EUR/USD; settles native KAS; not x402.*
2. Do not start a 402 implementation from this tree. Bind [kaspa-x402](https://github.com/elldeeone/kaspa-x402) when you charge a **call**. Steal k402’s lock if you need a **channel**. Never “adopted KCC-0402.”
3. Default `EnableKUSD` / `EnableUSDT` **off**. kUSD stays a comment until capital and a covenant exist — and even then it is not this binding’s `asset`.
4. If the till is the product: unique address or **mandatory** payload match; stop claim-any-payment; confirm on selected-chain, not blue-score delta; talk to a node you run.
5. Fix the 1 BPS leftover in the README. 10 BPS is live.
6. Do not list Ishum under x402, KCC-0402, or “Kaspa dollar.” List it under Track 1 POS.

**One sentence:** Ishum is a coffee till that prices in euros and keeps a chair for a dollar; kaspa-x402 is the meter; do not weld their names except as this warning.

---

> **Standard disclaimer.** This GitHub, not the topic above.
>
> Intentions are good; thought process is questionable. STP remains delusional. Si vis pacem, para bellum.
>
> Intern at https://sixpack.wtf/  
> X: https://x.com/StppStp · GitHub: https://github.com/STP-KAS
