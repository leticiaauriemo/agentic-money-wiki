---
title: "Should we give AI a bank account?"
source: "https://www.possible.fm/podcasts/neville/"
author:
published: 2026-03-31
created: 2026-04-21
description: "Possible with Reid Hoffman and Aria Finger"
tags:
  - "clippings"
---
*This transcript is generated with the help of AI and is lightly edited for clarity.*

///

ARIA: You said earlier that most economic transactions in the future will be agent to agent. And you said, this is something we’ll want. Why do we really want that? For all the people who are listening, being like that sounds insane.

SEAN: I think it’s not even the most. I think it’s all. I think it’s every single transaction will be executed by AI in the future. You know, so it sounds a little science fiction, but that’s the world I think we will ultimately want to get to if we have the proper guardrails and it’s sort of aligned with human ethics and so on.

SEAN: I hope it’s not just a chat interface on top of a shopping cart. I hope it’s not just a new sort of search that still has the same underlying mechanics. Agents don’t need shopping carts.

SEAN: Will we see a single person company that can generate a billion dollars or $100 billion? And my response to that, always, why do we need that one person?

///

REID: Most people think about AI as something that helps us work faster. Sean Neville is building for a different future. One where AI doesn’t just assist with finance. It is the customer.

ARIA: Sean co-founded Circle and architected USDC, the $76 billion stablecoin that turned crypto from speculation into actual infrastructure. But even inside Circle, he says not many people believed in it at first.

REID: Now he’s doing it again. Catena Labs is building the first AI native bank. Not a bank that uses AI tools, but a bank designed from the ground up assuming your customer might be an autonomous agent that exists for minutes, executes a transaction, and disappears.

ARIA: This raises questions we’ve never had to answer before. How do you do KYC on something that doesn’t have a Social Security number? Who’s liable when an agent misbehaves? And why do credit cards fail where stablecoins succeed when AI is the one spending the money.

REID: Sean has 100 AI agents doing compliance monitoring right now, overseen by just two humans. He’s navigating regulators who either want to build frameworks for AI finance or believe nothing good can possibly come from letting machines touch money.

ARIA: This conversation is about building at the collision point of two platform shifts and why some infrastructure has to be rebuilt from scratch.

REID: Welcome to Possible. Sean Neville, great to have you here.

SEAN: Thanks.

REID: So you helped start a company called Circle, which helps process, I think now 10 trillion in volume using stablecoins and valued at close to 13 billion. Let’s rewind to 2013. You and Jeremy co-founded Circle with his bold vision of making money move like the Internet. What was the moment or idea that convinced you this needed to exist? And what made you guys go, we’re the right people to build it?

SEAN: Well, so this is actually a third company that Jeremy and I worked on together. And so our previous companies were at the advent of the web, where we saw open standards on the Internet enable people to publish their opinions, express themselves without gatekeepers. So fundamentally, when we look at Circle, that’s really the seminal idea — it should be possible for everyone to plug into the global economy without gatekeepers sort of chopping off your money along the way for the privilege of access. And so the vision, just generally speaking, was, how do we make money work on the Internet the way content and data work on the Internet, where the Internet has new business models, but it wants data transmission to be free, and we view money as just data.

SEAN: So transmission of money should be free or very close to free, so that we can unlock new kinds of businesses for everybody. And so that was generally the idea. Why us? We had a lot of experience in building web companies at that point and working on sort of open standard approaches to it. But we were also hopefully naive about doing that in a regulated industry, because the regulatory pattern for the Internet is quite different than, obviously, financial services. But also, not only did we not have a background in, say, payments or traditional payments, but really any regulated industry — like healthcare or aviation, or pick your regulated industry. So I think it was actually helpful that we were so naive that we thought this is a thing that we could do.

REID: What was the regulatory thing that was kind of the most interesting — like a surprise or a learning or something you’d say to other entrepreneurs? Because I, by the way, have also had similar kinds of things, both in financial systems and in biology and pharma, where I go from being a software guy into it. I’m curious, which one is the most the aha moment in discovery and regulatory?

SEAN: Yeah, it was both an aha at the same time. And I think we embraced the opportunity to educate policymakers. And we felt like even if it took a decade or more to encode some of these ideas in public policy, we were up for that. And that’s what we felt needed to happen.

SEAN: A lot of the early economic philosophy, particularly from Jeremy, my co-founder — and that I embraced as well — was this notion of what’s been referred to as a narrow bank, which is this idea that’s been around since the 20s or 30s. It’s a really simple, almost boringly simple idea, which is just: if you’re a bank and I give you my money and I come back 90 days later, my money is still there and you can give it back to me, because the payment facility and custody facility is separate from the credit facility of the bank. And you’re not allowed to take my $10 and lend it out a hundred times. And that’s a thing that hasn’t actually been allowed by the government. Stablecoins are effectively that — they’re narrow banking.

REID: Yes, exactly. Now one of the cleverest things I think we did on the regulatory side at PayPal was: if we could get the FDIC to say that our deposits are FDIC insured, you basically get all the regulators to go, okay, fine, we’re good. And so what we did is we essentially went to them and said, well, you have this pass-through broker insurance where it allows it. So we’re putting it in banks on behalf of the people, but it’s FDIC insured still, and the FDIC agreed with us. So then our regulatory conversation got a lot simpler because anytime the regulator asked us, well, but you realize they’re protected by the FDIC and they’re like, oh, never mind. Yeah, we don’t need to talk to you anymore. So that was part of it.

ARIA: So, Sean, for our listeners who might not be as familiar with the stablecoin, could you explain to us what it is?

SEAN: Yeah, I don’t love the word stablecoin. I think of it as dollars and money on the Internet. And the origin of it is that we have other kinds of money that can move on these open rails, these open blockchain rails. Bitcoin, for instance, is one, and there are many others. But the problem with those coins is that they change in value. So if I’m sending you money, how much money you receive might be quite different than the money that I sent. And neither one of us can know ahead of time. And so the idea of a stablecoin is that I send you $10 and you get $10, and it’s stable in terms of its value.

REID: So before we get to the really exciting stuff you’re doing now… OpenClaw went from zero to, I think, over 145,000 GitHub stars in two weeks. 1.5 million agents transacting on multiple platforms. Some people are calling it the early singularity. I’m not one of those. Others are calling it a dumpster fire. I’m closer to that. Where do you land?

SEAN: Maybe both, in a way. So I think the positives — I would say very quickly, many more people have suddenly experienced this idea of a layer of abstraction above, say, Claude Code or chat or Copilot, even these new sort of ways they had thought of for how you interact with AI. A layer above that can use all of those things under the covers. And so the appetite is there and the interest and enthusiasm for those kinds of actors is there. More on the dumpster fire side is that there are just tremendous security implications. I think that top OpenClaw skills have malware problems. People are using them without being able to clear the trust chasm.

SEAN: And when it comes to those agents being financial actors, that’s a real problem because people can get hurt and it could go sideways in an ugly way — which is many of the things we want to address. We want to make it safe for agents to be economic actors. I mean, ultimately we think the only economic actors anyone will trust will be agents, but it’s not molts or lobsters or whatever you sort of call them today. So I think the experiment is great, but there’s also a lot of reasons to be worried about the particular form that it’s taken right now.

ARIA: So actually that leads perfectly into my next question, sort of talking about how do you make economic agents trustworthy on the Internet? You stepped back from Circle, the company you co-founded, and started a new company. Can you tell us about it?

SEAN: Yeah. So in many ways it’s a nice trajectory from Circle — and I have to say, I am still on the board, so I’ll bite my tongue on some things on the Circle side. But we got excited about creating dollars on the Internet to unlock new business opportunities. But one of the other problems with the economy is that people don’t have equal access to it. And one of the things that’s exciting about AI is that if we get it right, then the optimistic view is that we’ll be able to provide individuals and businesses everywhere around the world with access they’ve never seen before. And the economics will work and the intelligence will work, and it will leverage things like digital dollars and other currencies on the Internet. But it’ll do more than that.

SEAN: It’ll allow people to take the next step into the global economy that they just haven’t been able to. And so it’s a nice continuation, but it’s also the thing I’ve been most excited about in my life to work on. This is an incredible era to be building.

REID: So walk us through a concrete example. An AI agent tries to pay for something today using existing rails. What breaks? Where does a credit card fail where a stablecoin or other rails succeed?

SEAN: Yeah, so I’ll give a kind of a retail commerce example, even though most of the flows that we’re focused on now are actually more in the enterprise and business-oriented space. But the commerce one is almost easier to illustrate. So it starts with maybe an analogy to how you might buy something today. If you’re purchasing something on Amazon today, we don’t have to really worry that we’re not on Amazon because of SSL and HTTPS and all this stuff. We used to have locks in the browser that would at least give you a signal. Now we don’t even need that. We just trust that the technology handles that. We’re talking to the legit Amazon. And that kind of layer doesn’t exist with agents today. If they’re chatbots on a website, it exists.

SEAN: But with these new surfaces, how do I know that it’s Amazon that my agent is talking to? So this is a fundamental identity mapped back to an institution that I want to have some trust in. And then once I clear that hurdle and I can be sure that my agent is talking to Reid’s agent, how do I put some controls around what those agents are allowed to do? And a simple example would be spending rules — just set up something like: allow my agent to buy my goods on Amazon up to $50, but notify me for anything above that, and don’t let it spend on Etsy without notifying. Simple spending rules. And they can get much more complicated. But just versus identification — there’s rules, and then there’s the auditability of looking back and seeing what actually happened.

SEAN: And that’s particularly important in cases where something went wrong and understanding where the liability lies. And so these are all — you know, who are you, what are you allowed to do, and can you look back and understand what was done? Those are sort of the initial fundamental problems that need to be solved. If agents are the ones that are, whether they’re paying other agents or paying humans or just participating in automation with finance, it’s really all of these things. So loosely we refer to these things as KYA, which is know your agent.

ARIA: Sure.

SEAN: And being aware of who you’re interacting with — and if it’s my agent, how do I make sure it’s trustworthy to your agent? You know, these sorts of things. And so this is kind of a foundational element before we even get to payments that I think we need to address, that we’ve been focused on. Hopefully the solution is not a proprietary vendor solution, but something that is more of a de facto or formal standard that we can all build on, similar to what we saw in early e-commerce.

REID: So what are some of the things that go into this new architecture? Obviously agent identity and certification is one part of it. I’m curious to get a little bit more depth. What are the different kinds of ways that you conceptualize the way the network works when the customers or the engagement services are AI, not humans?

SEAN: So there needs to be a way — and this is nascent, it doesn’t really exist today — there isn’t sort of a DNS of agents to just resolve to, to discover agents out there. Although there are things that are emerging related to MCP server marketplaces, for instance, or now we have OpenClaw skills marketplaces. But there isn’t that mechanism yet. So one of the things that needs to happen is when agents begin to talk to each other, whether it’s through APIs or MCP servers or through these new discovery mechanisms, some verification can happen that maps back to who is the operator of that agent. If it’s a one-to-one scenario, you have your agent and I just need to be sure it’s actually your agent.

SEAN: But it could be much more complex in that we’re all using someone else’s agent to perform some function. And then we need to be sure the operator of that agent is who we think. In the regulated financial situation, it often needs to map back to a licensed entity that’s allowed to execute money transmission or lending or whatever it may be. And so we think of the foundational primitives as largely related to identity. And what are the protocols — meaning just how do you exchange these credentials back and forth in order for agents to do that in a trustworthy way?

ARIA: So Sean, at Circle you were designing APIs for human customers. At Catena, as you just said, you are designing for AI customers. Can you give us another concrete example of what’s different? What are API design choices that you’re making now because you’re specifically building for these AI agents?

SEAN: Yeah, I think API design is just totally different now. As a human developer, do you ever really need to read docs anymore to integrate an API, whether you’re building something in finance or not? A lot of the API docs are now generated for agentic workflows or even just directly for LLMs to be able to parse effectively. And many times — even past the era of vibe coders — principal architects leveraging large language models to build software don’t even look at the underlying APIs anymore because it’s more productive, so long as you can trust the AI. So then you end up designing APIs in a different fashion.

SEAN: There’s a really simple version of this that used to happen prior to some of the latest advancements, which is just how do you get a large language model to use a tool. If you put in these words, how do you get that large language model to recognize, okay, now I need to make an API call? And so there are these function calling mechanisms. And even in that mode you could see — in order to tweak the large language model to understand it should use an API, you kind of had to do some prompt engineering and coax it a certain way.

SEAN: But the real way to make it more reliable is actually to change your API — not so much the function signatures, but the input and output parameters — so that it could understand the schemas and what it was meant to deliver. You would end up changing in a way that was tuned to large language models, not so much human developers who will be looking at a JSON schema to read. And that is only becoming more exacerbated. So I think that’s generally speaking the case. When we build APIs at Circle and help businesses leverage stablecoins, we’re optimizing to make developers productive and happy.

SEAN: With AI, there’s a little more of a governance criterion in place, which is: how do we make this AI trustworthy and how do we help this API be reliably and safely executed by this machine? And there it’s a slight difference because trust is still the biggest hurdle to clear. How can we trust these things with anything, let alone money?

REID: So looking forward a little bit, where do you think the first large-scale adoption of AI transacting on behalf of consumers or enterprises will happen? Are there any obvious industries that might be disrupted or transformed?

SEAN: So I think ultimately it will hit everything, but obviously not all at once. I do have very strong conviction that the only actors we’ll trust with our money will be agents and agentic actors, and it’ll be the only competitive way to earn a return and so on. But we’re certainly not there yet. And so the harder question is what does it hit first? Many of the scenarios that have been outlined are more consumer-oriented, but where we see flows happening today are much more in the enterprise. And I wouldn’t necessarily call them agents even — they’re sort of automated workflows that increasingly have large language models in the loop.

SEAN: And in the world of finance, they’re not sort of the sexy use cases of give me some edge and prick the stock market. It’s more like the disappearing back office. It’s cash flow, basic liquidity management, compliance, reconciliation — these sorts of things. So what happens sooner rather than later doesn’t really look like a trading floor full of agents. It looks like a back office that’s gone in the enterprise.

ARIA: So I was trying to explain to my 10-year-old the other day how people used to buy airline tickets, and I couldn’t remember — what did we do? Did we call someone, like before the Internet? When you think of the consumer side, how do you think consumers will act differently? We went from we can’t trust the Internet for anything, to oh, we can buy books, oh, I guess we can buy clothes, now we can buy cars, buy whatever. Is there going to be a similar trajectory? Just for the sort of everyday person who does online banking or puts their credit card into Amazon — what are they going to expect from this AI agent future?

SEAN: Well, I hope it’s not just a chat interface on top of a shopping cart. I hope it’s not just a new sort of search that still has the same underlying mechanics. Agents don’t need shopping carts — and they don’t need user experience like here’s how your tax is calculated. They can understand a lot of that data effectively. So I think the exciting element for consumers will really be expecting a new kind of interface that does not look like e-commerce that optimizes you to not drop off in a shopping cart experience across a number of pages. What does that experience look like? There are a lot of different experiments there and so I’m not going to predict exactly what it looks like, but I think if we get it right, it’ll look very different than today.

SEAN: But it also won’t be the case that an agent just magically handles all of your payments, because there is some kind of shopping that is just pleasurable and requires sort of an inner introduction of taste. And then there are other transactions — transactions that, actually, I never want to have to buy a train ticket again, I just want it handled for me. But I think there are all of these little pieces to resolve. I think the user experience and the consumer experience is the hardest nut to crack.

ARIA: Gotcha. So getting back to the trust piece — obviously agent-native banking needs a new compliance strategy, and that’s going to be hugely important. Can you tell us a bit how Catena handles compliance monitoring? Like, what do humans do versus what do AI agents handle?

SEAN: Yeah. So first of all, being a regulated financial institution, we’re subject to the regulations that exist. So we can hope to encode into policy additional things related to AI safety, particularly AI safety related to financial flows, which I think ultimately will become very important. But in the meantime there are regulations that exist. So we’re not starting from a blank slate. We police for money laundering, for instance. Maybe put it in two buckets: real-time risk monitoring for things — and we built out these systems obviously at Circle. When you take a fiat money, take a credit card and you want to turn that into stablecoins, you need to make sure that the risk is managed effectively. And that’s often handled in real time.

SEAN: And some compliance pieces are also handled in real time, like screening — hey, this is a counterparty that we’re just not allowed, as a US company, to send money to. OFAC screening, exactly. We can’t facilitate money transmission to North Korea, for instance. That’s just a hard line. As a US company. There are other things that are more complicated on the compliance side that are usually not handled in real time. And a lot of that relates to looking at transaction activity to understand money laundering schemes.

SEAN: The traditional way to handle that is to have a bunch of humans who use tools — they sort of sign into a SaaS dashboard, and they do transaction monitoring, and they open cases and gather evidence and file suspicious activity reports, which is a very sort of secretive process. And a lot of that can be automated very effectively. And it doesn’t eliminate the need for a human compliance and risk expert. But the tasks that human does are very different. When they’re not signing into all these dashboards to do the work, they’re more orchestrating agents that can very effectively do that kind of work.

REID: And how close are you to that team of agents doing this work today?

SEAN: Well, we do that today, and it’ll only get better, is what I say — and we’ll quantify along the way: is it getting better? These things are very measurable in terms of false positives. So we do that today. I think there’s still an open question, though, of how you structure the team to orchestrate them effectively. And the mechanisms to orchestrate them are changing so quickly that the answer today probably isn’t the answer tomorrow. But I think that’s true across many disciplines. We’re talking about compliance and risk, but it’s also true in every other discipline where we’re building this kind of — we’re building an AI-native bank from the ground up. And so it touches every operational aspect.

REID: Makes sense.

ARIA: So speaking about identity — agents don’t have Social Security numbers, they don’t have credit histories. When you think about traditional banking, it’s KYC, know your customer; AML, anti-money laundering. How do you know your customer when your customer is an agent?

SEAN: So in the near term, our version of KYA is mapping back to one of those entities that has been KYC’d and KYB’d. Because an agent can’t apply for a bank account, it can’t get a credit card directly. And so in the future —

ARIA: That’s what I was going to say.

SEAN: In the future, I think that will change. I think we will want it to change.

ARIA: Oh, okay.

SEAN: And we collectively, I think, want it to change because the value that we stand to gain will be great enough to force those sort of policy changes where there will be unique identifiers that are recognized by governments for agents.

ARIA: Even if the agent isn’t identified with a specific human person.

SEAN: Yes. I think we will want it to get there because what we’ll want to see ultimately is really autonomous operations that many of us can kind of own and participate in and generate value from. And so at that point, the agent’s identity really is separate from any one of us. But in the near term it’s more like: if you’re interacting with our AI bank, then it needs to map back to us as the licensed financial institution — because an agent simply can’t be a licensed financial institution. It can’t go out and get money transmission licenses or apply for a charter. So there’s a progression to get there. We have the technology to very reliably map back to the licensed entity.

SEAN: So the KYB business that’s onboarded or the KYC individual — we can use cryptography to do that in a way that means you don’t really have to trust any business or company to see the tie. And so we can see back to, say, this merchant has these credentials that were issued by Visa to this business, even though we’re only interacting with that merchant’s agent.

ARIA: You mentioned that in the future we might not want one agent to track directly to one human — it might be an agent that’s acting on behalf of many people and they sort of have some ownership. Is there a concrete example where we might want that sort of shared ownership of an agent?

SEAN: Yeah, so I’ll answer a different question first and then maybe that’ll help answer that question. There’s been a lot of talk about will we see a single person company that can generate a billion dollars or $100 billion of value. And my response to that always: why do we need that one person?

ARIA: You’re like, forget the one, let’s do zero.

SEAN: I mean, really. So I think what we want is a different kind of relationship between the humans and the companies, the entities. And I think it looks a little different than classic equity. But there is a role for humans that are collectively orchestrating data and behaviors in an autonomous workflow or agent — for them to generate value for themselves, mapped to the value that they’re adding to the agent. And in that situation you want multiple people contributing, not just one sort of orchestrating mastermind running a company that has a bunch of co-pilot workers. So it sounds a little science fiction, but that’s the world I think we will ultimately want to get to if we have the proper guardrails and it’s sorted aligned with human ethics and all these important issues.

SEAN: And then the identity piece becomes interesting because it’s bidirectional between humans and agents. It’s not only can my agent trust Reid’s agent — it’s more can Reid’s agent trust me as a human being when it begins to interact with these workflows? And so then we get to this whole other level of what this could look like. This is more 10, 15 years out. Although now 10, 15 years — maybe that’s three years.

ARIA: But even 10 isn’t that far in the future. And I think also to your point, everyone’s always asking can we trust agents? But there are a lot of non-trustworthy humans around. And so if we could have a situation where we trust agents, that might be a better future.

SEAN: Yes. And the timing is always the hardest thing for me to predict on this. We’re in this world and we see this constantly, but then if I interact with others who are not in this world, you could see this might take a little bit longer than we think to fully — this is the same thing that happened with the Internet and certainly with stablecoins. We’re 13 years into Circle’s tenure and we’re only just now realizing some of the use cases we felt surely would be satisfied by 2014, and they still haven’t been. And so it may take longer than we expect. Although right now this world surely seems, to me, very different than anything else I’ve done.

REID: In May 2025, you released the Agent Commerce Kit. I do think the acronym is a little odd — ACK — but the month before, Google’s A2A or OpenAI’s ACP, and then OpenClaw happened. All of a sudden the future that you’re working towards with agent identity, payment roles, et cetera, suddenly is in an interesting shape, suddenly much closer. What do you think about this kickoff of this open source hobby project accelerating everything, and what are the ways we need to navigate? What are the things we need to be doing in society given this acceleration?

SEAN: I do think that the solution for agentic identity and verification and all the things we’ve been talking about should be an open standard that everyone can build on. I’m a big believer in open standards and the power of open networks as opposed to proprietary solutions offered by one vendor. And I think there has been fragmentation on the AI side when it comes to these kinds of topics today, for a lot of reasons. One of the reasons is that even large incumbents aren’t sure where the value is going to accrue, especially now that tech is not a moat for anybody — one person or Alibaba. It’s sort of past the castle and moats metaphor.

SEAN: We’re in the era of gunpowder and ballistics. And so I think for that reason and many others, the approaches to things like agentic identity are quite fragmented. They’re even more fragmented now than they were a year ago. So it feels like we haven’t made the progress toward a standard that I had hoped for. But there are many ways for standards to emerge. MCP has kind of become a de facto standard — it didn’t emerge through the W3C as a working group, but competitors to Anthropic have embraced it. These projects that achieve a level of virality show real appetite and interest that can shine a spotlight on a use case and cause others to act. Agents suddenly showed up as customers a lot sooner than we expected them to.

SEAN: So that’s a positive way to look at it for ACK and for some of these other protocols. Fundamentally I look at it as, ideally, a set of standards that we can all rely on so that as you’re building agents and others are building agents, they’re all leveraging the same open standard that no one can sort of unilaterally change. And also so that our agents don’t have to try to integrate 20 different approaches to the same thing — we can build much more valuable competitive offerings on top of that base.

ARIA: So when people are worried about AI, they talk about runaway agents. And sometimes that’s sort of more bioterrorism and geopolitics, but often it’s an agent buying 10,000 burritos or making a million-dollar Polymarket bet when you wanted them to put in $10. You talked about guardrails — like you can tell them don’t spend more than $50, or these are the rules. Talk more about your guardrails and specifically whether they’re sort of rules or judgment. Like are we giving these agents values about what to do or are we giving them hard and fast rules to make sure that they still have their autonomy but they’re aligned with humans?

SEAN: Yeah. So it’s a really good question. I think of it in two layers, and this is how we’ve approached what we build today. The first layer is very much — you could just call it the AI layer. And a simple example of a guardrail there — it would be easy to circumvent, but it’s just kind of a prompt suggestion. The problem with guardrails without policy enforcement is they just become suggestions. So you can flesh out many layers of guardrails. We’re talking about an agent, but usually there are many LLMs involved in workflows. And you can have LLMs check the output of other LLMs, and have ones dedicated to guardrails before any activity happens. And so there is a sophisticated tuning of that architecture and orchestration.

SEAN: But when it comes to things like moving money, those are deterministic outcomes — they should not be completely nondeterministic. If I’m moving a million dollars, it either needs to move or it needs to not move. And it can’t say, oh yes, it did move — and it didn’t, or it moved to a different place. Hallucinations or whatever. And so the second layer is really the underlying deterministic layer, which is a place where stablecoins actually excel. Because we can programmatically enforce rules both at the wallet cryptographic key level and on chain — in smart contracts we can write rules that AI can’t possibly circumvent. And so you need both operating in concert.

SEAN: And so that’s sort of how we approach enforcement of these guardrails at a couple of different levels. And I think there’ll be iterations on both of these things, but it’s one of those places where blockchains are useful for moving value. The thing that’s particularly exciting is you can program money on them. You can write these so-called smart contracts that have rules in them that are not controlled inside a bank’s ledger, but publicly on these rails using cryptography. And so that turns out to be really helpful for AI flows and AI actors who are executing money flows, as opposed to just having an API and then trying to deal with the inputs and outputs.

ARIA: So another thing people are really worried about, of course, is external threats. Are the AI agents going to become so good at scams, fraud, et cetera? Are there ways that you think you are better positioned to ward off external threats than traditional banks?

SEAN: Yeah, it’s a problem now. I think a lot of people are approaching it through proof of personhood, which is very useful and will become incredibly more useful. But we really think more about the other side, which is sort of proof of agency — proof that this agent belongs to the operator that it says it does, and that it has these policies that we can be very sure cannot be bypassed. And how do we enforce these restrictions? I think we have a time window here to get that right, but the window won’t be open forever before people are burned. And some of the not-doomsday-but-dire scenarios you mentioned, I think are likely to happen without these guardrails in place, frankly.

ARIA: Absolutely.

REID: In some of your other comments you’ve mentioned that agents are surprisingly bad at marketing content generation, but great at compliance tasks. What other counterintuitive things have you learned about what AI is actually good at — and actually still TBD — in financial services?

SEAN: You know, some of the things that it used to not be so great at, it’s actually not bad at now. And there’s always the thing of — I hear people say, well, I put this in Claude and it told me this, or ChatGPT or whatever. And it’s like, well, that’s what it told you based on what you put in and what you have. It’s like sort of saying, well, I put this in Photoshop and this is the image that came out. If I use Photoshop, it’s quite different than if it’s the real photographer.

ARIA: Maybe you’re the problem here.

SEAN: Yeah. Some of it’s garbage in, garbage out. But it’s also — we have very sophisticated workflows now in terms of managing memory and context and so on when it comes to making these things good at software engineering. Those workflows have made them so good at developing software that the profession is completely different than it was a year ago. And I think that’ll happen to maybe not every knowledge worker domain all at once, but it’ll happen to many of them and it’ll be a similar progression. So a lot of the things that — marketing content just in terms of generating copy — there’s a certain tone. And it’s not just the em dashes or whatever the clichés are, it’s the phrasing. You know, short, long, short. It’s the kind of like freshman-in-high-school sort of this is a good essay kind of thing. But that’s going away with the right context and the right data provided and examples provided and models that teach each other to get better at those things. So I think the other answer to the question is a lot of the stuff that it’s good at — it’s the non-sexy stuff. It’s just really good at parsing a tremendous amount of information, synthesizing it, and turning it around to make you more productive.

ARIA: Well, it’s so clear that you are so excited about this next world and you’re building this whole fleet of financial tools for AI agents. What made you decide that this was the thing to do, this was the first thing you needed to get out into the world?

SEAN: Yeah. I mean, I think if we don’t get this piece out, it’s like an unlock — if we don’t get this piece out then we can’t unlock these new opportunities. There’s sort of a pattern through crypto and stablecoins and Circle that I think is relevant to AI: there’s kind of a toy phase where people are speculating with some random stuff and it seems easy to dismiss but gets some attention. But then there’s this really hard middle ground of infrastructure development where regulators start plugging in — and this middle ground can last a long time — of doing really hard work to unlock new kinds of opportunities, leading to the later phase which is these world-changing applications the likes of which we can’t possibly imagine when we’re in these early stages.

SEAN: And it was similar to when I was young in the early days of the web — couldn’t possibly have predicted all of the things that the Internet and the web would be used for. But we just had a sense this is world-changing. That’s the excitement: to build the unlock. We’re in the infrastructure phase. And it’s often accompanied — if it’s truly valuable — by a speculative element as well. So there’s hype and speculative cycles, but that doesn’t mean it’s not real and important. And the last thing I would say is I think there’s a time window here to get this right and the window is closing. There’s urgency here.

ARIA: Why do you think the window is closing?

SEAN: Because the advancements now are AI-augmented, if you will. So they’re just exponential in terms of capabilities. We’re talking about OpenClaw, which again I think is exciting — I don’t want to poo-poo it — but there are also some real concerns. And what’s next will be augmented by OpenClaw agents building the next thing. And so making sure that we’re capable of working on all of these things to make AI powerful for people, with the kind of guardrails and the alignment that we’ve talked about — this is the time to do that. But there will come a time, if we don’t get it right, where it may be too late.

REID: Crypto has taught us immutability has costs — no chargebacks. Traditional banking has fraud protection and appeals. Where should we be thinking about agent commerce in this?

SEAN: Yeah. So I think one of the big hurdles that people have now, even with agent commerce and just sort of consumer shopping behaviors, is: if a merchant tricks my agent into buying something, who’s liable? The merchant wants to know this, the consumer wants to know this. And these are questions that are answered in, say, the Visa world or the Mastercard world, and they’re not answered yet in agentic commerce. So it’s very difficult to establish liability paths. And this comes back, to me, to agentic identity and understanding who it is, what are the rules it has to follow, and then who is ultimately responsible if an audit shows that an agent bypassed its guardrails. And so these are things that have to be defined. There are lots of different opinions.

SEAN: I’d say some are very traditional, which is more along the lines of: AI is just a surface on the underlying rails. We believe new rails need to be created and that smart contracts and blockchain technology help us get a step forward in creating this.

ARIA: So you said earlier that most economic transactions in the future will be agent to agent. And you said this is something we’ll want — we’ll want these autonomous agents doing that. Can you make the affirmative case? Like, why do we really want that? For all the people who are listening being like that sounds insane.

SEAN: I think it’s not even the most. I think it’s all. I think every single transaction will be executed by AI in the future. And I think we’ll want that to be the case because it will be the safest way to execute transactions. It’ll be safer than trying to trust a web form and a purchase through the whole chain than it is today. And that’s not the case today — we have a ways to get there — but I think that ultimately will be the case. It’ll also be the fastest way to execute commerce at the lowest cost. Thanks to things like stablecoins, we can move a trillion dollars around the world for fractions of a penny and nearly instantly. Connecting those kinds of flows effectively does require a similar level of intelligence.

SEAN: Because now the bottlenecks in terms of speed are not the machine, it’s not the blockchain — it’s all the layers on top of it. And then when it comes to earning a return on our assets, I think it will be the only competitive way to earn a return. Today, things like private banking or certain opportunities are accessible to very few people.

REID: Yep.

SEAN: And the promise of AI is that you have the same level of access that everyone else — all of these high-end businesses or ultra high net worth individuals — have. And the only way that you get there is by trusting these agents, and they will be the only way that you get a competitive return on your underlying assets. And so that’s the optimistic vision, certainly the thing that we’re marching toward.

ARIA: Yep.

REID: So one of the things that technologists know is that these AI systems are inherently interesting probabilistic systems. But when you get to a statement like all commerce transactions flowing through agents because it’s higher reliability, how do you square the probabilistic nature of these things — where we’ve gotten them highly reliable in a certain set of circumstances, but they can go strange very quickly — with the necessity of reliability within the financial system? What’s your thinking about that impedance?

SEAN: Yeah, so I think I’ll start at the user experience level. I think a lot of the tasks that we’ll be executing will involve some level of orchestrating these agents doing a variety of things for us and steering and tuning. And then past the user experience is the underlying infrastructure to take that steering — I would say that’s more at the AI layer, not just at large language models, but with all of the integrations and data that they will touch. And then when it comes to deterministic outcomes, when they’re really doing specific things in the world — moving a car or executing a financial transaction — those things need to be absolutely deterministic and not probabilistic. And so that’s the sort of second layer.

SEAN: But I think the really interesting thing is that rather than clicking a button in an interface and then checking the readout that the button led to what we expected to happen, it will be more like we’re doing less on those surfaces, but we’re doing a lot of steering as needed to orchestrate the agents in the way that we want them to behave. Which is what happens in software engineering today. Software engineering has kind of gravitated toward — you don’t really use IDEs anymore or look at source code so much — because you have a new level of interface which still requires a great deal of attention. Some would say it even requires more right now. But you’re kind of multitasking across a set of orchestrating surfaces, either on a command line or otherwise, to build.

REID: Going up a level — what are the things that we should be doing with our governmental and financial infrastructure to bring our companies, industries, inventions, and society forward? If you just said, hey guys, if you start paying attention to at least a few things, do these — what would they be?

SEAN: I’ll say on the policy side — obviously we’re leaning into being a regulated financial institution, so we’re confronting the existing policy regime. But when it came to building US Dollar Coin and stablecoins, our belief was that in order for the dollar to work on the Internet, the United States government has to say this is how dollars can work on the Internet. And there needs to be public-private sector cooperation and joint innovation. And the way that we usually do that in the West is that there’s public policy and there’s private sector innovation. We thought it might take 10 years. It ended up taking about seven years to get the GENIUS Act passed.

SEAN: For stablecoins, where the government says: you have a dollar on blockchain rails, it needs to be backed by T-bills and cash and overnight repos and so on. Here are the consumer protections, here’s how you can’t return yield because it’s not a mutual fund. Those sorts of things. And when it comes to regulation of AI in finance, I do think that ultimately we’ll have policy requirements around any AI actors that are permitted to touch things like dollars. And that’s where public-private sector cooperation again needs to happen. Because the US dollar is backed by the United States government — it’s not a private sector technology. And so how these things move through agents, similarly to how they move through blockchains, will have to be encoded ultimately in public policy.

SEAN: The way that it’s happening today is there are several different workstreams in D.C. and elsewhere to explore this. Some come out of the AI safety world — AI safety guardrails in general and clearing evals and the like. Others are very much out of finance. My experience so far is that they’re fairly nascent. It’s an important investment toward a long-term result that we’ll need to have in place.

ARIA: So if we go back to March 2023 and Silicon Valley Bank — the whole point of a stablecoin is that it’s stable and that it is pegged, in this case to the US dollar. USDC briefly depegged. Can you take us through what broke, what held, and what did this teach us about stablecoins in that moment?

SEAN: So in terms of the stability of a stablecoin, we did not have the GENIUS Act in place then. So there are many different approaches to how you provide stability. There was no clear reserve framework — you have this token on chains, but it’s backed by reserves, and there are no clear guidelines from the government as to how those reserves should be structured. When we were building USDC over the years, we’ve had different approaches to how we manage our underlying reserves, as has everyone else. Since then, even before the GENIUS Act, we’ve moved into this mode of a very conservative underlying reserve. As long as you have trust in the US dollar and the US government, it’s a very conservative reserve backing, which is how we’re able to ensure stability.

SEAN: But it is the case that stablecoins trade against one another in the marketplace. So we first lacked regulatory clarity to say: this is how we achieve stability and this is how the government will enforce protections for everyone. Now the problem is if you launch a stablecoin and I launch a stablecoin, we can do that because we have regulatory guidelines, but none of our stablecoins will trade as a dollar. It’s this sort of singleness of money problem. If Amazon issues a coin and Walmart issues a coin, they’re going to have a market against one another until we solve this interoperability and this clearinghouse issue. And that hasn’t been clarified by the GENIUS Act or anything else.

ARIA: That’s what I was going to say. So in order to clarify that, do you think we need additional government regulation?

SEAN: There are some technical approaches to it. So I think we’ll see some solutions that people can rely on. And by people I really mean those businesses who just want to look at this as a dollar. They don’t want USDC, they want a dollar that moves more efficiently and is more accessible in their markets. And if they have 20 of those, they want to view all of those collectively as just dollars. And so there are some technical approaches to how to achieve that, but we may also see it addressed in subsequent legislation that comes out in this space.

REID: So many crypto maximalists worry that Circle and other similarly centralized stablecoins can lead to a government having full control over individual citizens’ ability to transact, monitoring all transactions. Do you see this as a risk of heading to a CBDC surveillance world? Is there anything we should be doing to navigate in or out of that?

SEAN: So on CBDC — central bank digital currency — there’s this idea that maybe the federal government should issue its own stablecoin and issue it directly to individuals. And that’s been an approach that has been looked at, say, in China. Here, generally the way we do things is that we have private sector innovation but with public policy. So we have the government saying how to do it, and then we have companies such as Circle and others that are able to actually do that thing. So that’s the kind of difference between stablecoin issuers in the US versus the CBDC approach. But the crux of the question is really related to privacy. And it is important to have an open mechanism for value exchange that also has privacy protections.

SEAN: A simple example: if you’re paid on chain, I shouldn’t be able to see your paycheck.

ARIA: Sure.

SEAN: And so there need to be some privacy protections. Another example is for very large transfers internationally, there’s counterparty info exchange — there’s this thing called the travel rule, even at relatively low volumes. And so that should be private. You don’t need to know my address or Social Security number if I’m part of these transactions. And so there is an imperative to maintain privacy and balance transparency on these open rails with privacy. And so this leads to things like — Circle has created a new blockchain called Ark, which is really designed specifically just for stablecoin payments, as opposed to all the other things you can do on other blockchains. And there have been others that have looked at the same space — Stripe and Bridge have formed Tempo, and we also leverage that on testnet.

SEAN: So as Catena, we just want a solution in place. We’re not necessarily wedded to one. But part of the issue that these payment chains are addressing really is this privacy issue, to avoid the surveillance state on chain.

ARIA: So you talked about how you thought it would take sort of 10 years to get the legislation that you needed, and it took seven or eight to get the GENIUS Act. And it’s so critical to understand the rules of the road and to have this public policy so that we can have innovation — which I think sometimes people don’t appreciate. They think about innovation and regulation actually being at odds. But in some places, in order to have innovation, we need regulation, especially when we’re talking about people’s finances. And I think a lot of people sort of take financial regulation for granted because it’s just what we have. And if there’s fraud on our Visa card, you know, they’ll refund us — all those things.

ARIA: Where do you see this landscape for Catena? Like, how long is it going to take? What do we need to have happen so that we can have the regulation that causes the innovation?

SEAN: Yeah, I’ll say how we’re going about it, because I do think it’s similar to Circle, but it’s different from other tech companies. Typically the way you build things at tech companies is there’s some version of sales and marketing, BD partnerships — that sort of function. There’s some product management and product design. And then there are the engineers. And the three of them are the big stakeholders and everybody else is kind of supporting. When you’re building something in finance, you have a fourth stakeholder at the table, which is related to risk and compliance. And things go wrong when any one of those stakeholders is out ahead of the others.

SEAN: You know, sales is selling things that can’t be built in a reasonable amount of time, or product managers create documents in a strategery cabal but engineering builds amazing tech nobody wants — that kind of stuff. And the same can happen with risk and compliance. So it needs a seat at the table and it needs to be moving in lockstep with the other three. So it’s a compliance-first sort of approach to building out this technology — the same one that we’re taking at Catena. Taking it at Circle certainly caused us to be slower on certain things relative to others who were in the crypto space. But we had absolute conviction that it was the only way ultimately to have the winning solution.

ARIA: You’ve built two generational companies at two massive inflection points. You could have stayed at Circle and worked there a long time. You’re still on the board, which is fantastic. But what drives you towards the chaos of a startup and starting something new?

SEAN: So I’ll give the healthy and unhealthy answer.

ARIA: Great.

SEAN: I’ll give the unhealthy answer first. Which is just — it’s almost like an obsessive disorder. I can’t not do this. As much as I try not to do this, I have to do this. I build things. I haven’t been that successful investing in other people building things, which is a great skill I admire in people, but I build things. And so I have to build this. And then the healthier answer is I do think again that we have a window to get this right. And I feel like I can play at least a small part in getting it right. And that’s a combination of understanding the policy, the underlying tech, how to bring the right people in, and sort of having pattern recognition for what to apply to this stage. And it’s just — I’m excited to get out of bed every day and work on this problem in this space.

REID: Absolutely awesome. So on rapid fire — is there a book, movie, or idea that gives you optimism about the future?

SEAN: Usually I answer with books, but I’ll give a movie answer because that’s what popped in my head. There’s a movie called Arrival. It was based on a Ted Chiang short story.

REID: Yeah, exactly.

SEAN: So it was kind of like an alien first contact movie. But the thing that I think gives me optimism is it was built on this: there’s a language that they need to understand, and the language, as they begin to understand it, doesn’t just allow them to communicate — it changes the way they think and opens up new patterns. And so the thing about developing stablecoins is it unlocks new kinds of business opportunities that can be built with programmable money. AI is like — we’re just learning the grammar today of how to understand this language, and it will unlock new ways of thinking for all of us. So I’m optimistic about that.

ARIA: Awesome. What is a question about crypto or AI that you wish people would ask you more often?

SEAN: I guess both, and it’s kind of a personal answer. My undergrad degree is in English, and I’m a musician. And so when people usually hear that, they’re like, oh, that’s interesting — but I can see what they think. Like, maybe he didn’t know what he wanted to do, or there was career drift, or these sorts of things. And so the question I wish people would ask is: how’s that connected to all the products and companies that you’ve built? Because I think it’s very directly relevant — especially in the age of AI, when skills across multiple domains are incredibly valuable, as opposed to just climbing a career ladder. Those two kinds of workers, I think, will find their tasks most in jeopardy.

ARIA: Instead of leaving your field to start in this field, you used that knowledge, which was incredibly important to what you’re doing today.

SEAN: Absolutely.

REID: The music thing is fascinating because I’ve been thinking about music a bunch. Where do you think the current state of AI music is? What are some of the things that are perhaps off the beaten path — is it an issue with the industry and the creatives? Issues to navigate with copyrights or training or inspiration in order to be generative? Anything that has struck your musical background?

SEAN: I think a lot of the things that are circulating are really good replicas of other things. That’s not entirely bad, but it’s also kind of empty. You know, it’s like lyrics that are a little sloppy, but it kind of bops. There’s a lot of that going around, which is a little more like an echo of originality. And that may come from a number of different originators who are obviously not being compensated and there’s no mapping back to that. There are also experiments more along the lines of electronic music and experimentation, where it is a skill to compose with sounds that you yourself are not capable of making as an instrumentalist. And there’s still a creative element to it.

SEAN: And so I would hope that the future of music moves more in that direction, as opposed to just the millionth copy of Let It Be sung by, you know, Cardi B or whatever it is.

REID: Exactly. So where do you see real progress happening outside of your industry?

SEAN: Outside of my financial and AI foundational domain — what I’m really hopeful about is related to healthcare and the cost of producing drugs coming down, and accessibility to health services increasing. It’s not a domain I’m deeply familiar with, but it’s one that I have personal connection to. I lost my sister from cancer, I lost my mother from cancer. And that personal experience of seeing how the databases are just not connected, and nobody has all the information that they can even use to guide people — there are trials that are available that people don’t even know exist, and they can’t connect. So I’m very optimistic about some of these technologies being able to clear those gaps. And it ultimately comes down to accessibility, which is the same thing that drives a lot of my interest in finance.

ARIA: So as always, our last question. If everything breaks humanity’s way in the next 15 years, what do you think is possible to achieve and what’s the first step to get there?

SEAN: Wow, 15 years. So I think I’ll steer it back to what we’re working on. So if we get this right, then I do think there will be kind of a hyper-personalized private banking experience that will be accessible to businesses everywhere. Whether you’re an entrepreneur in Nairobi, you’re a two-person company in Detroit, or whatever it may be, you have the same access to the global financial system with new opportunities to start new businesses, tap into new mechanisms to go to market that you just haven’t had available before, thanks to the combination of AI agents and underlying financial infrastructure that can make them safe to transact.

ARIA: Amazing.

REID: Awesome. Great talking to you.

ARIA: Great talking to you. Thank you.

SEAN: I enjoyed it. This is fun.

REID: Possible is produced by Palette Media. It’s hosted by Aria Finger and me, Reid Hoffman. Our showrunner is Shaun Young. Possible is produced by Thanasi Dilos, Katie Sanders, Spencer Strasmore, Yimu Xiu, Trent Barboza, and Tafadzwa Nemarundwe.

ARIA: Special thanks to Surya Yalamanchili, Saida Sapieva, Ian Alas, Greg Beato, Parth Patil and Ben Relles. And a big thanks to Victoria Lamson. And The Lighthouse in Venice.