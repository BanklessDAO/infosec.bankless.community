---
title: "Slope Finance Update — 11 August 2022"
date: 2022-08-11T10:07:21+06:00
# post image
image: "images/blog/slope-update.jpeg"
# author
author: "stackthat"
type: "regular"
# meta description
description: "This is meta description"
# post draft
draft: false
---

To the Slope Community,

Thank you for your support and patience over the course of the last week. We apologize for not being more communicative during these challenging times.

It is important to us that we provide you with independently verified facts and a solid plan for the near future, rather than adding to further speculation. Starting from day one, the team has been focused on investigating the root cause of the wallet hack incident and the recovery of assets. We have been working tirelessly over the last week with the auditors OtterSec and SlowMist, and the cybercrime firm TRM. The auditors received full access to all databases, data pipelines, server logs, and application source code. The auditors’ investigations are nearing their conclusion, and we feel it’s now appropriate to provide regular updates.

Before we get to that, we want first to say that we sincerely apologize to all those who were affected by the wallet hack last week. We are genuinely sorry for all the losses suffered and are doing everything we can to make it right.

Here are the most important findings from the independent audits:

There was a vulnerability in the Slope on-premise 3rd-party application monitoring service on Slope Wallets on mobile from July 28th to August 3rd that inadvertently logged sensitive data in cases where the apps generated an error event.
There is no evidence that all security layers (e.g., transmission and storage) were compromised. All the transmission to the 3rd-party application monitoring server is protected through HTTPS end-to-end encryption, and access to the 3rd-party application monitoring server is controlled through 3-factor authentication.
As confirmed in previous interim reports from Ottersec, the investigation team has cross-compared all hacked addresses (9,232 addresses in total) vs. all exposed addresses from the vulnerability in the 3rd-party application monitoring database:
-The number of all hacked addresses is larger than the total number of addresses ever exposed from the 3rd-party application monitoring server.
-A fraction (1,444 addresses) of the total exposure from the 3rd-party application monitoring server has been confirmed drained in cross-comparison.
Although there is no conclusive evidence from the auditors to link the Slope vulnerability to the exploit, its very existence put a lot of assets in danger. This is nowhere near the security standard that Slope set out to establish and maintain, and we are deeply regretful of these occurrences. Security is paramount to us, and our user base is everything. We should never have let this happen.

We found no additional vulnerabilities during the investigation and intense scrutiny by multiple parties. Therefore, we believe the latest patched version of Slope Wallet is safe to use. The Slope team will continue to obtain regular audit reports and work with security professionals on a rolling basis.

We will work hard to earn your trust back, hunting down the hacker, recovering stolen assets, and making our users whole.

So where do we go from here?

Expect regular updates on the following topics:

Detailed fact-sheet walk-throughs of the full scope of the vulnerability and everything we’ve learned and improved on going forward.
A revamped product roadmap that doubles down on security.
Details on the asset recovery measures for compromised wallets.
Thank you again for your patience and understanding as we work through this. Please monitor our official Twitter account (@slope_finance) for further updates.

Sincerely,
Slope Team

[Official announcement of the Slope Finance update]: https://slope-finance.medium.com/slope-update-11-august-2022-31d678d7cd97