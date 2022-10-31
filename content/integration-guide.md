+++
title = "Integration Guide"
+++

See the Rust [reference implementation](https://github.com/private-payments/rust-private-payments).

## Exposing the Payment Code

The payment code public and private keys are derived on the wallet's BIP32 seed path. Each code declares the supported receive address types that the user is willing to accept. These may be chosen by power users of more advanced wallets or simply set to a single type for simpler wallets. Wallets should expose a quick access button for users to display their payment code QR or copy its data to the clipboard.

## Normal Receive Operation

Wallets scan the `OP_RETURN` data in each block looking for relevant Private Payments notifications, which resolve to a series of stealth addresses. For each notification, the wallet derives stealth addresses and adds those to its internal keystore, scanning incoming transactions for activity.

## UTXO Handling

Wallets should warn of privacy loss when joining UTXOs received via different stealth address chains.

## Transaction Labeling

Incoming stealth payments should be labeled `Private Payment` in transaction lists.

## Recovery

Full recovery is possible even in the event of a complete loss of wallet or device. All that is needed in such a scenario is a seed and some block height corresponding to the wallet creation time. A wallet can then rescan the blockchain and reconstruct its state. Otherwise, a wallet might do regular backups. Such a backup should include a list of all `OP_RETURN` notifications ever received by the wallet. This enables fast state restoration.

## No Full Node?

While the standard requires access to full Bitcoin blocks in order to detect notifications encoded in `OP_RETURN` payloads, this requirement can be obviated by outsourcing this search to a service. One such implementation is available [here](https://github.com/private-payments/notification-repository). A wallet provider might want to deploy and run such a service in-house instead of relying on a third-party deployment.
