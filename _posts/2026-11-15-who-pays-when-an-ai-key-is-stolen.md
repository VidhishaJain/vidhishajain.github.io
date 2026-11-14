---
title: "Who pays when an AI key is stolen?"
description: "An attacker ran up $740,000 on stolen AI keys. The refunds were decided by terms of service, not by any rule. That is the real problem."
---

In October, a company called Railway was hacked. Railway is a US cloud platform. Developers use it to run their apps instead of managing their own servers.

When you run an app on Railway, you store your secrets with it. Passwords, and API keys. An API key is like a prepaid SIM card for an AI service. Anyone holding your OpenAI key can use OpenAI, and the bill goes to you. Thousands of customers had parked these keys with Railway.

Over two days, 20 to 22 October, an attacker got in and hunted for AI keys, ignoring almost everything else. The stolen keys were then used to run about $740,000 of AI usage. The bills went to the customers whose keys they were.

How did it happen? [Railway's own security](https://blog.railway.com/p/incident-report-october-security-incident) failed in three places:

- Different customers' builds ran on one shared machine. The attacker broke out of his section of it.
- An internal credential meant only for builds was accepted by other systems too, including Railway's internal task system, which let the attacker read build histories and fetch a copy of Railway's codebase.
- A powerful decryption key sat in a plain file on a server. That key unlocked the customer secrets.

The attacker is still unknown. Railway believes the stolen keys were passed on and resold. So the thief and the spender may be different people. The FBI is investigating.

Now the harder question. Who pays the $740,000?

The money was spent at six AI providers: AWS, Google, Anthropic, OpenAI, OpenRouter and SpaceXSI. These companies were not hacked. But the stolen keys open their doors, and they billed the usage. Each one is handling the refunds differently:

- AWS and Google: refunding under their existing fraud policies
- OpenRouter: refusing, citing its no-refund terms
- Anthropic: negotiating with Railway
- OpenAI and SpaceXSI: reviewing case by case
- Railway: has promised to cover whatever the providers decline

One incident. Identical stolen keys. Five different answers on who pays. Each answer came from a company's terms of service, not from any rule.

Credit card fraud used to work in this dysfunctional way too. But today, if your card is skimmed at a shop, your card issuer refunds you. Not out of goodwill. The rule says the loss is theirs. That rule changed their behaviour. Once the loss was theirs, fraud detection became worth building. That is why you get a text message the moment your card does something unusual.

AI keys have no such rule, and it shows. The stolen keys ran up $740,000 before anyone's systems asked a question. Where were the spending caps? Where was the alert when a key suddenly started spending at many times its normal rate? An API key is the provider's product. A key with no spending cap and no alerts is like a car with missing airbags. If the airbags fail to deploy in a crash, the carmaker answers for the injuries. We do not hand the passenger the bill.

So here is my position. The customers should pay nothing. The loss should be split between Railway and the AI providers. Not evenly, but by a simple principle: each party bears the loss its own missing control enabled.

- The keys were stolen because Railway's security failed. The breach costs sit with Railway.
- The money was spent because the providers served weeks of abnormal usage without a cap or an alert. The fraudulent spend sits with them.

Railway covering everything the providers refuse sounds generous. However, it lets the providers off the hook. If the breached platform always absorbs the loss, providers never pay for issuing keys with no safety features. Nothing will change before the next incident.

The fix should not depend on goodwill. Platforms like Railway should agree liability terms with their AI providers up front, before an incident, not after one. In time, this belongs in law, the same way credit card liability does. Several governments are writing AI incident reporting rules right now. Liability for misused AI keys should be on the same page.

Someone is already probing the next Railway. The question is whether that bill lands by rule or by press release.

---

Sources: Railway's [security disclosure (21 October 2026)](https://blog.railway.com/p/security-disclosure-wednesday-october-21st), [preliminary report](https://blog.railway.com/p/preliminary-report-october-security-incident), and [full incident report (10 November 2026)](https://blog.railway.com/p/incident-report-october-security-incident). Refund positions as stated in Railway's full report.
