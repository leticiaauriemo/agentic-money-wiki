---
title: "An Overview of EIP-3009: Transfer With Authorisation"
source: "https://academy.extropy.io/pages/articles/review-eip-3009.html"
author:
  - "[[Laurence Kirk]]"
published:
created: 2026-05-03
description: "An overview of EIP‑3009, explaining how its “transferWithAuthorization” meta‑transaction extension lets users sign off‑chain authorisations."
tags:
  - "clippings"
---
I've never been good with the EIP numbers, so if you are like me and wondering what this is about, this EIP is about making authorisation and transfer more user friendly.

One of the most persistent points of friction for web3 devs has been the user experience of on-chain transactions. EIP-3009, titled "Transfer With Authorisation," is a crucial (though still "Draft" status) protocol that directly tackles this problem.

While often discussed alongside other standards, EIP-3009 is a specific ERC-20 extension that, once implemented by a token, provides a new way to move assets. Its adoption by major stablecoins like USDC has made it a foundational component for the emerging machine-to-machine economy.

## The Problem: Gas Fees and Clunky UX

Before EIP-3009, paying for something with an ERC-20 token was a famously clunky, two-step process for a user:

1. **The `approve` Transaction:** A user must first send a transaction to the token contract, calling the `approve` function to allow a smart contract to spend tokens on their behalf. This costs a gas fee.
2. **The `transferFrom` Transaction:** The user (or the smart contract) must then send a *second* transaction, calling `transferFrom` to actually move the tokens. This costs **another** gas fee.

This flow presents two critical problems:

- **Bad User Experience:** It requires two separate transactions, two gas fees, and two wallet pop-ups.
- **The Gas Token Problem:** The user *must* hold the network's native token (e.g., ETH on Ethereum) to pay for gas, even if they only want to spend their USDC. This is a massive onboarding barrier for new users and a non-starter for autonomous AI agents that cannot easily manage multiple wallet balances.

## How EIP-3009 Works: The "Gasless" Authorisation

EIP-3009 solves this by introducing the concept of meta-transactions for transfers. Instead of sending an on-chain `approve` transaction, the user signs an off-chain message that authorises a transfer.

This flow is designed to be handled by a third-party "relayer" or "facilitator."

1. **Step 1: Off-Chain Signing (The Client)** The user (or an AI agent's wallet) does not create a transaction. Instead, it creates a structured, EIP-712 compliant typed message. This message contains the precise details of the transfer:
	- The token holder's address (`from`).
		- The recipient's address (`to`).
		- The `value` to be transferred.
		- A `validAfter` and `validBefore` timestamp (to prevent replay attacks).
		- A unique, random `nonce` (a `bytes32` hash).
	The client signs this message with its private key, producing a cryptographic signature.
2. **Step 2: The Relayer (The Facilitator)** The client sends this signed message (the authorisation) to a relayer. This relayer can be any service willing to submit the transaction and pay the gas fee (e.g., the x402 facilitator).
3. **Step 3: On-Chain Execution (The Contract)** The relayer takes the signed message and calls a new function on the ERC-20 contract: `transferWithAuthorization(...)`.
	This function accepts the signed message parameters (`from`, `to`, `value`, `nonce`, `signature`, etc.). The token contract itself then performs the following logic:
	- It reconstructs the EIP-712 message.
		- It uses `ecrecover` to verify that the signature matches the `from` address.
		- It checks that the `nonce` has not been used before.
		- It confirms the current time is within the `validAfter` and `validBefore` window.
	If all checks pass, the contract executes the `transfer` internally. The user's tokens are moved, and the relayer (who called the function) pays the gas fee.

## Key Technical Features for Developers

For developers, two features of EIP-3009 are particularly important:

- **Atomic Transfer:** Unlike EIP-2612 (`permit`), which only authorises an *approval*, EIP-3009 authorises the *entire transfer*. It is a single-call execution.
- **Non-Sequential Nonces:** A traditional Ethereum account uses a sequential nonce (0, 1, 2, 3...). This creates a bottleneck, as you cannot process transaction 3 until 2 is confirmed. EIP-3009's nonce is a random `bytes32` hash. This is a critical design choice for high-frequency systems, as it allows an agent to generate *thousands* of concurrent, independent payment authorisations without any of them conflicting.

## The Problem: A Fragmented Standard

If you are thinking we have been here before, well yes, there have been a few attempts to solve this problem. In fact EIP-3009's primary weakness is not technical but strategic: it is not the only standard. This has fragmented the ecosystem:

- **EIP-3009 (`transferWithAuthorization`):** The standard for gasless *transfers*. Implemented by Circle for USDC (v2).
- **EIP-2612 (`permit`):** A similar but incompatible standard for gasless *approvals*. Implemented by Maker for DAI.
- **No Standard:** Tether (USDT), the largest stablecoin by market cap, implements *neither* standard and has stated it has no plans to.

This "token exclusivity" is the main limitation of protocols that rely on EIP-3009. While it provides a seamless experience for USDC, it cannot (by itself) support a truly chain-agnostic or token-agnostic payment layer, as it excludes a massive portion of the stablecoin market. Despite this, I wanted to introduce this EIP to you as background for some our next articles about the x402 protocol.