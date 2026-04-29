---
title: "The new stack for global finance: Stablecoins edition"
source: "https://a16zcrypto.com/posts/article/global-finance-stablecoins-new-stack"
author:
  - "[[Noah Levine]]"
  - "[[Guy Wuollet]]"
  - "[[Robert Hackett]]"
published: 2026-04-27
created: 2026-04-28
description: "Stablecoins are reshaping global finance—unlocking faster payments, dollar access, and a new onchain stack for banking, credit, and markets."
tags:
  - "clippings"
---
The financial system is being rebuilt on new infrastructure, and it’s happening faster than most people outside of crypto realize.

[Stablecoins](https://a16zcrypto.com/posts/tags/stablecoins/) are a catalyst. They have [evolved](https://a16zcrypto.com/posts/article/stablecoin-data-charts) from a niche trading instrument into foundational plumbing, and they are becoming the layer on which a new generation of global financial products [gets built](https://a16zcrypto.com/posts/podcast/stablecoins-bridge-founder-circle-usdc-creator/). The market map accompanying this post captures our view of the transformation that’s underway. The specific companies are likely to change, and the categories will likely blur and evolve — but the more important story is structural: How the new stack for global finance is coming together, where it’s maturing, and what gaps remain.

The organizing idea is that stablecoins are giving rise to a new form of [banking-as-a-service](https://a16zcrypto.com/posts/article/understanding-stablecoins-banking-history/) (BaaS). The prior BaaS wave was about fintechs renting bank licenses and plugging into legacy core systems. This one is structurally different: Companies building on onchain infrastructure, using self-custodial wallets to reduce friction and their reliance on intermediaries; while also combining account, payment, FX, and credit primitives into end-to-end financial products.

The result is a set of capabilities that would have required a host of regional licenses and local bank partners a decade ago, now accessible to any team with the right stack.

Stripe’s [acquisitions](https://a16zcrypto.com/posts/article/stripe-bridge-acquisition-stablecoins/) of [Bridge](https://a16zcrypto.com/posts/videos/bridge-ceo-zach-abrams-stablecoins-are-the-next-platform-for-money/) and Privy, and Mastercard’s of BVNK, show that the incumbents are navigating the shifting landscape by similar maps. They’re making consolidation plays, looking to secure key pieces of the stack before the new infrastructure layer gets settled.

These are just some of the signals that the transition to onchain finance is already past the point of no return. The choice is to [adopt and embrace](https://a16zcrypto.com/posts/article/why-wall-street-is-moving-onchain), or be left behind.

![](https://dwt2zme5yrom6.cloudfront.net/uploads/2026/04/BACK-STABLECOIN-MARKET-MAP-4-2048x1602.jpg)

## Blockchains: three categories

The old assumption that all blockchains are competing for the same use cases is breaking down. Three distinct categories have emerged, each based on varying sets of requirements and entailing different performance tradeoffs. Understanding their differences matters for understanding where fintech activity is happening:

#1 **General-purpose chains** — Solana, Ethereum and its major L2s — remain the primary home of [crypto capital markets](https://a16zcrypto.com/posts/article/future-onchain-markets-role-predictability): trading, lending, DeFi. This is a large and durable market, but it does not describe the full picture of what’s happening.

#2 **Payments-specific blockchains** represent another category emerging explicitly for financial services use cases. Networks like Stripe’s Tempo and Circle’s Arc are competing on features that the general-purpose layer was never optimized for: stablecoin-native gas fees, [privacy guarantees](https://a16zcrypto.com/posts/podcast/privacy-moat-crypto/), and, critically, predictable transaction costs.

For a fintech processing millions of payments, the ability to model costs is essential. The companies building in this area are betting that payments-oriented chains will become the preferred settlement layer for the next generation of financial infrastructure.

#3 **Institutional networks** are the third category of networks like Canton that are designed for regulated entities that need programmability and privacy without surrendering the compliance frameworks they’re legally required to maintain. As bank- and asset-manager adoption accelerates, this category could become increasingly load-bearing in ways we’re starting only now to see.

## Banking: the choke point is loosening

For most of the past decade, the banking layer was where crypto-native financial services hit a wall. Banking partner relationships were hard to establish, easy to lose, and the source of most existential risk for companies in the space.

That dynamic hasn’t disappeared, but it’s meaningfully better. A cohort of crypto-friendly banks is actively building connectivity between crypto-native infrastructure and traditional fiat systems.

The on-ramp and off-ramp problem, which was once the dominant operational challenge for most players, is becoming more tractable. Fiat connectivity is essential to the operations of stablecoin-native fintechs. That matters not just for payments, but across the stack.

## Stablecoin issuers: a charter race with long-term consequences

The stablecoin issuance layer is more competitive than it has ever been, and the competitive dynamics have shifted in a specific direction: regulatory positioning. Since the passage of the [GENIUS Act](https://a16zcrypto.com/posts/article/stablecoin-law-genius-road-ahead/), there has been a scramble among issuers to obtain an OCC National Trust Charter.

The immediate benefit is legitimacy — a federal imprimatur that matters to regulators and institutional partners.

The longer-term stakes are higher. If regulators eventually extend OCC National Bank Charter holders direct access to Federal Reserve rails, the issuers that secure that charter early will become integrated into the core of the financial system, enabling them to become central players in its digital transformation.

The race is less about branding than it is about where in the payment hierarchy you end up sitting. And increasingly, it’s about who will provide a foundation upon which credit and capital markets can flourish.

## Liquidity providers: the last-mile problem

Stablecoins have made genuine progress on the “middle mile” of cross-border payments; that is, the intermediary steps involved in moving money digitally from one country to another. Stablecoins provide faster settlement, reduced dependence on pre-funded correspondent accounts, and lower friction for international transfers.

The remaining problem is liquidity between stablecoins and local fiat currencies, particularly for flows in emerging markets. In most geographic corridors, that liquidity is still thin; and thin liquidity means slippage, delay, and unreliable pricing. If these [challenges](https://a16zcrypto.com/posts/article/how-stablecoins-become-money) remain unaddressed, they could severely hinder business-to-business use cases where stablecoins have significant potential.

That gap is beginning to close through three channels:

- stablecoin-compatible foreign exchange (FX) providers (like OpenFX and XFX);
- regional exchanges with deep local fiat relationships (Bitso in Latin America, Yellowcard in Africa, Coins.ph in Southeast Asia); and over time,
- banks that support stablecoin settlement for FX trades directly.

All three are necessary. The FX providers bring technical integration; the regional exchanges bring local market depth; the banks bring the balance sheet and the correspondent relationships. No single channel closes the gap on its own.

## Bank connectivity: the unglamorous critical layer

The stablecoin infrastructure stack has been built almost entirely outside traditional banking by fintechs, non-bank payment companies, and crypto-native entities. That’s been a source of speed and openness, but it has created a structural problem: Stablecoin infrastructure is architecturally incompatible with the legacy core systems most banks run. Integrating them requires a dedicated translation layer.

The “bank connectivity” category is that layer. These companies are building the infrastructure that lets banks offer stablecoin capabilities alongside their existing systems, without requiring a full-on system transplant that most banks won’t undertake.

Some of the most forward-thinking players here are already expanding their scope beyond crypto capital markets and payments into onchain lending and other areas where banks will eventually want to extend stablecoin infrastructure.

## Applications: convergence, and new primitives

Two dynamics are reshaping the application layer.

The first is the convergence between fintech neobanks and crypto wallets.

Exchanges are adding virtual accounts, cards, and rewards; neobanks are integrating crypto and traditional investment products. The distinction between these categories is narrowing fast, and the end state is almost certainly a unified financial application that serves both crypto-native and mainstream users from a single interface.

The companies that will win this race [aren’t necessarily](https://a16zcrypto.com/posts/article/enterprise-blockchain-adoption/) the ones with the best product today. They’re the ones that will combine distribution and trust with offerings that can match customer demand.

![](https://dwt2zme5yrom6.cloudfront.net/uploads/2026/04/APP-STABLECOIN-MARKET-MAP-4.jpg)

The second dynamic is the adoption of stablecoins for corporate banking. In markets where local dollar banking infrastructure is limited, unreliable, or prohibitively expensive (as in large parts of Latin America, sub-Saharan Africa, and Southeast Asia), stablecoins are enabling dollar-denominated operations in ways that were previously inaccessible to most businesses. This includes vendor payments, global collections, and treasury management.

The story has less to do with crypto than it has to do with dollar access, and it is driven by the practical needs of businesses operating in environments with weak or unstable local financial infrastructure.

But the more important long-run dynamic at the application layer is *what comes after the account*.

Dollar access is the wedge. Once a user has a stable, dollar-denominated balance — whether they’re a small business owner in Lagos, a freelancer in Buenos Aires, or a saver in Jakarta — they have the on-ramp to a full suite of financial products they’ve never meaningfully had access to before: credit, investing, wealth management, insurance.

The neobanks and super-apps that win the account relationship will be positioned to cross-sell across all of these categories, in markets where the incumbent financial system has never fully served these customers. The payments layer is where the account gets opened. The credit and investing layers are where the business gets built.

## The credit question: significant second-order effects

If payments is the first act, then credit is likely to be the second and, perhaps, even more consequential one.

The conventional framing of stablecoin growth leads to a version of narrow-banking at scale: dollars tokenized, held in wallets, used for settlement, redeemable on demand. But that framing misses what happens when stablecoin issuance reaches genuine mass scale. A world with trillions of dollars in stablecoin float is a world with enormous demand for somewhere to put that capital to work. Businesses holding stablecoin treasuries will want to seek out productive uses for those balances. Protocols will need liquidity. And the users at the end of the stack will eventually want to borrow.

The result, almost inevitably, is a new onchain credit market. Not the self-referential trading products that characterized DeFi’s earliest cycles — where crypto was lent against crypto to speculate on crypto — but something closer to the productive credit economy that banking was originally designed to provide: capital formation, lending against real assets and receivables, working capital for businesses operating in markets where local banking infrastructure is inadequate or absent.

The wild early days of DeFi are giving way to something more durable and mature: the era of onchain finance.

This dynamic rhymes with what’s happened in private credit over the last decade. As banks retreated from certain lending categories under regulatory pressure, private credit funds filled the gap. They grew from a niche alternative asset class into a multi-trillion dollar market that now competes directly with syndicated lending. The onchain credit market is structurally similar: Capital forming outside the traditional banking system, in new structures, serving borrowers that the legacy system underserves. The difference is the infrastructure layer underneath, which is open, programmable, and global in a way that private credit funds are not.

Traditional credit managers are taking notice, and the institutions that recognize this early — and build or acquire accordingly — will define what the future of onchain capital markets looks like.

## Dollar dominance and geopolitics

There is a story inside this market map that is bigger than fintech, and it cuts in two directions.

For the individuals and businesses gaining access to a new global financial system, it’s practical economic empowerment. People get protection from local currency devaluation, access to global payment rails, and the ability to operate in the world’s most liquid currency. A farmer in sub-Saharan Africa, a manufacturer in Southeast Asia, or a small importer in Latin America can now hold dollars, transact in dollars, and save in dollars without a U.S. bank account, without a correspondent banking relationship — and without any of the legacy gatekeepers that previously made dollar access a privilege rather than a utility. That is a genuinely new thing.

For the United States, it is an amplification of existing power. For most of the last century, dollar dominance was enforced through institutions: the IMF, the World Bank, the correspondent banking system, the network of bilateral agreements that gave the U.S. Treasury and the Federal Reserve outsized influence over global finance. Now stablecoins add a new and more direct channel: Every stablecoin wallet holding dollars is, in effect, a new node in the network of a dollar-based financial system that can, for the first time, settle value between any two points almost instantly and at negligible cost. The broader the adoption, the more valuable it becomes for all users, potentially deepening the dollar’s penetration into economies where it previously had limited reach.

This is a far-reaching consequence of the stablecoin story: With the passage of laws like the GENIUS Act, the U.S. government is not simply regulating a new financial product. It is making a bet that stablecoins infrastructure serves the longer-term goal of dollar primacy at a moment when that leadership has faced more challenges than at any point since Bretton Woods.

## Beyond payments

The new stack for global finance is still under construction, and the stakes are larger than the payments story alone suggests.

What’s being built here is a wholesale system upgrade. The underlying rails are open, programmable, interoperable by default — and increasingly capable of serving the places, people, and use cases that the legacy system was never designed to reach. That includes not just global payments at low cost, but:

- dollar access in markets where local banking infrastructure fails,
- returns on capital that would otherwise sit idle,
- credit for borrowers the traditional system underserves, and
- investing products for the billions of people who have never meaningfully participated in capital markets.

The companies building across the layers of this stack today are the ones who will define what global finance — and the global dollar economy — looks like for the next era.

![](https://dwt2zme5yrom6.cloudfront.net/uploads/2026/04/STABLECOIN-MARKET-MAP-5-scaled.jpg)

\*\*\*

*Acknowledgments: This piece benefited from the input of many people across the a16z crypto team. Thanks in particular to Maggie Hsu, Christian Crowley, Pyrs Carvolth, and Liz Harkavy for their feedback and contributions.*

\*\*\*

**Noah Levine** is an investment partner at a16z crypto.

**Guy Wuollet** is a general partner at a16z crypto.

**Robert Hackett** is features editor and head of special projects at a16z crypto.

\*\*\*

*The views expressed here are those of the individual AH Capital Management, L.L.C. (“a16z”) personnel quoted and are not the views of a16z or its affiliates. Certain information contained in here has been obtained from third-party sources, including from portfolio companies of funds managed by a16z. While taken from sources believed to be reliable, a16z has not independently verified such information and makes no representations about the current or enduring accuracy of the information or its appropriateness for a given situation. In addition, this content may include third-party advertisements; a16z has not reviewed such advertisements and does not endorse any advertising content contained therein.*

*You should consult your own advisers as to those matters. References to any securities or digital assets are for illustrative purposes only, and do not constitute an investment recommendation or offer to provide investment advisory services. Furthermore, this content is not directed at nor intended for use by any investors or prospective investors, and may not under any circumstances be relied upon when making a decision to invest in any fund managed by a16z. (An offering to invest in an a16z fund will be made only by the private placement memorandum, subscription agreement, and other relevant documentation of any such fund and should be read in their entirety.) Any investments or portfolio companies mentioned, referred to, or described are not representative of all investments in vehicles managed by a16z, and there can be no assurance that the investments will be profitable or that other investments made in the future will have similar characteristics or results. A list of investments made by funds managed by Andreessen Horowitz (excluding investments for which the issuer has not provided permission for a16z to disclose publicly as well as unannounced investments in publicly traded digital assets) is available at https://a16z.com/investment-list/.*

*The content speaks only as of the date indicated. Any projections, estimates, forecasts, targets, prospects, and/or opinions expressed in these materials are subject to change without notice and may differ or be contrary to opinions expressed by others. Please see https://a16z.com/disclosures/ for additional important information.*