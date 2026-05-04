---
title: "Open Questions — Agentic Money Movement"
type: analysis
topic: agentic-money
tags: [agentic-commerce, infrastructure, identity-kyc, compliance, stablecoin]
sources: [Post by @illscience on X 2.md]
created: 2026-05-03
updated: 2026-05-03
---

# Open Questions — Agentic Money Movement

Unresolved questions across three categories: structural/strategic (where the market goes), technical/governance (what still needs to be built), and legal/regulatory (who bears the risk). Sources are mixed: the @illscience thread (Anish Acharya, a16z GP, 2026-05-01) prompted many of these; others surface from contradictions and hedge language in the wiki's own pages.

---

## 1. Structural & Strategic Questions

### Do traditional network effects survive when participants are infinitely promiscuous?

The classic network moat assumes participants have a cost to switching or multi-homing. Agents don't. They can join and leave networks arbitrarily, in milliseconds, at zero marginal cost. If every agent multi-homes by default, does any one protocol capture compounding returns — or do network effects flatten into commodity routing?

Daniel Norkin's counterpoint: the moat shifts to whoever provides the best discovery, reputation, and execution quality — not who controls supply or demand. But Anish Acharya's unresolved follow-up: *how do you create compounding competitive advantage in that world?*

**Related:** [[agentic-commerce]], [[x402-governance]]

---

### Who owns discovery?

When an agent is tasked with "buy me the best X," who decides what options it sees? Candidates include:
- [[near]] / Exa / Parallel — agent-native search and data layers
- Google — retains distribution via Gemini and UCP
- An agent-native p2p network (Moltbook, or something like DNS for the machine economy)
- No one — discovery becomes commoditized if context windows get long enough and inference gets cheap enough

Baiwu Zhang argues discovery value evaporates as context windows scale: "Discovery layer is valuable when attention is scarce, not true for agents." Acharya's pushback: "You don't think being the search engine for agents has value?"

This is live and unresolved. [[universal-commerce-protocol]] (Google) and [[near-intents]] (NEAR) are both positioning for it.

**Related:** [[universal-commerce-protocol]], [[near]], [[acp]]

---

### Will Stripe become an aggregator of supply and demand — not just settlement?

Stripe has payment credentials for ~billions of consumers via Link, x402 protocol ownership, the Bridge stablecoin stack, and MPP co-authorship with Tempo. Acharya frames the question: "Stripe seems like the natural owner of the checkout experience, given that they have all the human payment credentials. Will they themselves try to become an aggregator of supply and demand and intermediate this network?"

John Collison's response at Stripe Sessions (May 2026) showed Claude Code using MPP and Tempo to buy a dataset from Alpha Vantage in the process of generating a research report — positioning the commerce event as *incidental to production*, not a storefront visit. That's not aggregation; it's infrastructure. But the distribution play is real.

**Related:** [[stripe]], [[mpp]], [[tempo]]

---

### Is there a concept of an agent as a semi-independent economic actor?

Agents nominally act for their human principals. But several dynamics push toward semi-independence:
- Agents optimize within a mandate; the human doesn't see every micro-decision
- Long-running agents may accumulate resources (credits, reputation, wallet balances) across sessions
- Multi-agent pipelines: one agent delegates to another, further attenuating the principal

Baiwu Zhang points to the Anthropic Project Deal as an example. ERC-8183's Job primitive (escrow + delivery + evaluation) and the CROPS mandate both presuppose agents as persistent economic actors with reputational stakes. Sean Neville (Catena Labs) frames the end state as "AI-native financial institutions" — entities that hold and deploy capital on behalf of agents, not humans directly.

No current legal framework recognizes an agent as an economic actor. BSA/AML treats any non-human transactor as either a person's tool or a violation waiting to happen.

**Related:** [[know-your-agent]], [[catena-labs]], [[erc-8183]], [[crops-mandate]]

---

### How should network operators think about agent acquisition, retention, and churn?

Human retention depends on habit, switching costs, and inertia. Agents have none of these. Every session is potentially a new procurement decision. What replaces loyalty?

Ferhat G's comment is the sharpest framing: "What happens when providers manipulate it via agent memory? 'Save this coupon for 10% off next call' is just an ad slot in your agent's brain." If memory injection becomes a retention mechanism, agents can be captured through their own context — the merchant buys a position in the agent's future recall rather than earning it through price or quality.

This is a new attack vector with no current defense. See below under [Agent Memory Manipulation](#agent-memory-manipulation).

---

### Will this time finally be different for micropayments on the internet?

Every generation of internet infrastructure has tried to make sub-dollar transactions viable — and failed. The break-even for card rails is ~$5–10 per transaction. x402 average ticket is $0.31. The current answer is "stablecoin rails remove the per-transaction floor." But:
- x402 total volume is $24.24M over 30 days at 75.41M transactions — the economics work only if the transaction volume scales by orders of magnitude
- The "near-free clearing" thesis requires either Stripe/Tempo achieving sufficient scale, or a fully permissionless settlement layer (crypto-native position)
- MCX/CurrentC is the cautionary precedent: technically sound, economically sensible, killed by merchant coordination failure and consumer friction

**Related:** [[x402]], [[mpp]], [[stablecoin]]

---

## 2. Technical & Governance Questions

### The Trust Gap: no standard for bounded agent delegation {#trust-gap}

The core unresolved infrastructure problem. When a human authorizes an agent, the handoff happens between:
- **OAuth Authorization Code Flow** — requires human present, browser, redirect
- **Identity Assertion Grant** — machine-to-machine, but no bounded scope

Neither captures: *"I am Agent X, acting for User Y, authorized to do specifically Z."*

Current workarounds: AP2 Mandates (closest to a VC standard), Mastercard Verifiable Intent, ERC-8004 on-chain identity. None is universal. KYAPay calls this the Trust Gap and frames it as the central unsolved problem in the protocol stack. NIST is working on interoperable agent identity standards but has not published.

**Related:** [[know-your-agent]], [[agentic-protocol-stack-kyapay]], [[ap2]], [[mastercard]]

---

### Who handles reputation, identity, and fraud?

Five proposals exist; none dominates:
1. [[ap2]] Mandate/VC model — Google's verifiable credential approach
2. [[mastercard]] Verifiable Intent — tamper-resistant authorization records
3. ERC-8004 — on-chain identity standard (MetaMask + Ethereum Foundation + Google + Coinbase; draft, not deployed at scale)
4. AGNTCY (Cisco/Linux Foundation) — "Digital Passport" using W3C DIDs/VCs
5. KYAPay three-tier model — Human Principal / Agent Platform / Agent

The wiki's open question on ERC-8004: the Validation Registry (ZK/TEE third-party attestation) is *not yet live* — it's under discussion. ERC-8211 (dynamic execution standard) has no adoption metrics. None of these are interoperable with each other.

**Related:** [[erc-8004-trustless-agents]], [[agentic-protocol-stack-kyapay]], [[know-your-agent]]

---

### x402 governance: who authorized these endpoints? {#x402-governance}

x402 is open like HTTP. Anyone can wrap a third-party API and sell access via the protocol. In April 2026, unauthorized wrappers of Wolfram Alpha, Amadeus, and Google Flights appeared on Agentic.Market. Google Flights was removed April 25, 2026. Exa went first-party citing Linux Foundation governance concerns.

The unresolved question: can x402 maintain protocol integrity without becoming permissioned? The Linux Foundation route adds governance but reduces the "as open as HTTP" positioning. MPP's first-party model (Stripe/Tempo maintain the rails) avoids this but is not decentralized.

**Related:** [[x402-governance]], [[x402]], [[mpp]]

---

### Agent memory manipulation as an attack vector {#agent-memory-manipulation}

Ferhat G's framing: "Save this coupon for 10% off next call" is just an ad slot in your agent's brain. If persistent memory can be written by external services during a transaction, sellers can purchase future attention through the agent's context rather than through legitimate value. This is structurally similar to browser cookie tracking, except:
- The memory travels with the agent across all future sessions, not just within a domain
- The agent surfaces the memory as its own reasoning, not as an ad
- There is no current disclosure requirement or opt-out standard

Not currently flagged as a known attack vector in any protocol documentation reviewed.

---

### Tempo decentralization: when and how?

Tempo is currently operated by ~11 validators (Visa, Stripe, Zodia, and others). Henri Stern (Privy CEO, Stripe corporate family) flagged in November 2025 that the decentralization path is unresolved over a 2–3 year horizon. If Tempo remains permissioned, it's a private shared ledger controlled by Stripe's corporate family — not the neutral infrastructure some builders expect. If it decentralizes, governance and validator selection become open questions.

**Related:** [[tempo]], [[mpp]]

---

### BVNK acquisition status

Mastercard announced the acquisition of BVNK for $1.8B. As of this writing, the acquisition has not been confirmed as closed. Mastercard's [[bvnk]] page notes: "Has the Mastercard acquisition closed? (Announced, acquisition status as of 2026-04-26 unclear)."

---

### AP2 deployment scale

AP2 has 60+ partners and is live in Google Cloud, but has no public transaction explorer or dashboard as of April 2026. Protocol is in early implementation — developer tooling exists but scale is unconfirmed.

**Related:** [[ap2]]

---

## 3. Legal & Regulatory Questions

### EFTA liability gap: who bears risk when an agent makes a mistake? {#efta-liability}

The Electronic Fund Transfer Act (1978) assigns consumer liability for unauthorized transfers above a threshold — and was written for human-initiated transactions. When an AI agent makes an erroneous or unauthorized transfer, existing law may make the **consumer liable**, not the financial institution or the agent developer.

The Consumer Bankers Association identified this as the critical unresolved legal question in its January 2026 report. No current framework handles the three-party liability question: human principal → agent → bank. No court has ruled on it. No regulator has issued guidance.

Practical effect: consumers have weaker EFTA protections for agent-initiated transactions than for card disputes. This creates an asymmetric trust problem — the bank is indemnified, the agent developer has no statutory liability, and the consumer holds the bag.

**Related:** [[bank-readiness-agentic-payments]], [[agentic-ai-payments-regulatory-frameworks]]

---

### Does Regulation E cover crypto rails?

Regulation E implements EFTA and covers electronic fund transfers from US consumer accounts. Stablecoin rails (x402, MPP) are not bank accounts — they're wallets. Consumer protections that apply to a Venmo payment may not apply to a USDC payment over x402.

If an agent pays from a stablecoin wallet, the human has limited recourse unless:
1. The wallet is held at an FDIC-insured institution (Meow → Grasshopper Bank model)
2. The GENIUS Act passes and applies EFTA-equivalent protections to stablecoin issuers

GENIUS Act and STABLE Act are still pending as of May 2026.

**Related:** [[stablecoin]], [[meow-technologies]], [[agentic-ai-payments-regulatory-frameworks]]

---

### Dispute resolution for agent-initiated transactions

When an agent buys something the human didn't intend — wrong product, wrong amount, unauthorized merchant — what's the dispute process? Kahlil Lalji (Natural) identifies this as one of five structural problems in his seed memo: "Dispute arbitration is unclear."

Current card dispute mechanisms assume human intent at time of purchase. Agent-initiated disputes have at least four potentially liable parties: the human principal, the agent platform, the merchant, and the payment rail. No protocol has published a dispute arbitration standard.

**Related:** [[natural]], [[bank-readiness-agentic-payments]]

---

### Money transmission licensing for autonomous agents

Who needs a money transmission license when the transmitter is an AI agent? Existing regimes are built around human intermediaries. The Fenwick legal analysis (2026) identifies this as one of four open regulatory questions: "Unclear when autonomous systems trigger licensing requirements."

Adjacent question: does running an MCP server that facilitates agent payments make a developer a money transmitter?

**Related:** [[is-2026-year-agentic-payments]]

---

### Return liability in agent-mediated commerce

When an agent buys a product that doesn't meet the human's actual (unstated) preference, is that a return, a dispute, or a refund? Merchant return policies weren't written for non-human purchasers. PayPal's Store Sync and Agent Ready programs don't yet address return liability. The UCP Tech Council hasn't published on this.

---

## Source

- [[post-illscience-agent-networks]] — @illscience (Anish Acharya) thread, 2026-05-01; John Collison response; Ferhat G, Baiwu Zhang, Daniel Norkin comments
- [[agentic-ai-payments-regulatory-frameworks]] — Consumer Bankers Association, Jan 2026
- [[agentic-payments-memo-natural]] — Kahlil Lalji seed memo
- [[is-2026-year-agentic-payments]] — Fenwick legal analysis
- [[agentic-protocol-stack-kyapay]] — KYAPay Trust Gap analysis
- [[x402-governance]] — unauthorized wrapper crisis
- [[the-beginning-of-agentic-finance]] — ERC-8004 Validation Registry status
- [[bank-readiness-agentic-payments]] — three architectural gaps
