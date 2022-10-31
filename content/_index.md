+++
title = "Private Payments"
template = "home.html"
paginate_by = 1
+++

Private Payments is a stealth address protocol for Bitcoin, specified by [BIP351](https://github.com/bitcoin/bips/blob/master/bip-0351.mediawiki). Stealth addresses make it possible for two parties to transact using addresses that only they can calculate. Receiving parties generate static payment codes that they share with the world. Every sender-recipient pair calculates a unique set of addresses, leading to increased privacy.

**Example:** Bob places a payment code on his donation page. Alice and Carol wish to donate to Bob because they like the content he is creating. After importing his payment code and sending a one-time notification transaction to Bob, Alice and Carol will be deriving entirely different donation addresses for Bob. Bob can now receive coins from different parties while preserving both his and their privacy.

In other words, Private Payments makes it possible to establish a basic on-chain payment channel without leaking private information.

Read about [Use Cases](/use-cases) for Private Payments.


# Comparison With Other Methods of Transacting

For an in-depth comparison with other on-chain payment standards and why a wallet might choose to implement it, please see the [specification](https://github.com/bitcoin/bips/blob/master/bip-0351.mediawiki#Motivation).
