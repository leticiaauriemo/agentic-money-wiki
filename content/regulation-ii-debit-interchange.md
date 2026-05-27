---
title: "Regulation II: Debit Card Interchange Fees and Routing"
type: summary
topic: agentic-money
source_type: report
tags: [card-rails, compliance, regulator, bank-api]
sources: ["Regulation II Debit Card Interchange Fees and Routing.md"]
created: 2026-05-27
updated: 2026-05-27
---

# Regulation II: Debit Card Interchange Fees and Routing

**Source:** Federal Reserve Board of Governors, compliance guide
**URL:** https://www.federalreserve.gov/supervisionreg/regiicg.htm

## What it is

Regulation II implements Section 920 of the Electronic Fund Transfer Act (added by Dodd-Frank). It governs **debit card interchange fees** and **network routing** for electronic debit transactions in the US.

## The interchange fee cap

For large issuers (>$10B assets): interchange fee must not exceed **21 cents + 5 basis points × transaction value**, plus up to **1 cent** fraud-prevention adjustment.

Small issuers (<$10B assets) are exempt from the cap (allowing card networks to offer two-tier fee structures that protect them competitively).

## Network routing requirement

All debit card issuers must enable **at least two unaffiliated payment card networks** on each card — preventing monopoly routing. Networks cannot inhibit merchants' ability to route to their preferred network.

In October 2022, the Fed clarified this routing requirement extends to **card-not-present (online) transactions** effective July 2023.

## Relevance to agentic payments

Regulation II shapes the economics of debit card rails that agents could use:
- The 21¢ + 5bp cap on debit interchange is much lower than credit card interchange (~$0.50–$0.80) — making debit rails more economically viable for agent micropayments
- The two-network routing requirement prevents any single network from monopolizing agent debit transactions
- The card-not-present extension (2023) directly affects online agent-initiated debit transactions

The regulatory structure creates a cost gap: regulated debit (capped at ~21–24¢ for large issuers) vs. credit interchange (~$0.50–$0.80) vs. stablecoin rails (<$0.01). Agents optimizing for cost will flow toward the cheapest compliant rail.

## Related pages

- [[bank-readiness-agentic-payments]] — gaps banks face in handling agent debit
- [[stablecoin]] — why stablecoins are cheaper than any card rail
- [[agentic-ai-payments-regulatory-frameworks]] — broader regulatory landscape
- [[visa]] — affected by routing requirements
- [[mastercard]] — affected by routing requirements
