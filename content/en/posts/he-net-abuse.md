---
title: HE.NET Domain Outage
description: Due to an error made by the domain registrar, the domain name was suspended.
toc: true
authors:
  - steveyiyo
tags:
categories:
series:
date: '2024-07-07T00:00:00+08:00'
lastmod: '2024-07-07T00:00:00+08:00'
featuredImage:
draft: false
---

A few days ago, it was Independence Day in the United States, and many businesses took the day off.

However, on this very day, the domain name of major Internet Service Provider Hurricane Electric (HE, AS6939), [HE.NET](https://he.net/) was suspended. This incident sparked significant discussion on the North American Network Operators' Group (NANOG) Mailing List.

### The Incident

On July 4, 2024, HE.NET was entirely suspended. The reason for this was that their domain registrar, Network Solutions, placed the domain in "Client Hold" status. The incident was also shared on X.

<blockquote class="twitter-tweet" data-width="300" data-height="400"><p lang="en" dir="ltr">Public Service Announcement: Hurricane Electric’s bgp dot he dot net was unreachable for a bit. Looks like the fine folks over at <a href="https://twitter.com/henet?ref_src=twsrc%5Etfw">@henet</a> forgot to renew their domain and it expired. Oops! It’s now back; but, maybe still unreachable for a few because <a href="https://twitter.com/hashtag/DNS?src=hash&amp;ref_src=twsrc%5Etfw">#DNS</a>. <a href="https://t.co/DtYFvWoAsd">pic.twitter.com/DtYFvWoAsd</a></p>&mdash; Dr. Peering (@DrPeering) <a href="https://twitter.com/DrPeering/status/1808943281482706963?ref_src=twsrc%5Etfw">July 4, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

HE's Senior Director, Reid Fishler, released [a statement](https://mailman.nanog.org/pipermail/nanog/2024-July/225901.html) on the NANOG Mailing List, explaining that Network Solutions had placed the domain on Client Hold due to a phishing website complaint. The complaint involved a webpage on the bgp.he.net subdomain, which was actually just an informational page about another domain.

> [bgp.he.net](https://bgp.he.net) is a BGP Toolkit provided by HE that includes various AS and Prefix information. The AS pages preview sites grabbed from PeeringDB.

Executives from Hurricane have been calling and emailing Network Solutions for HOURS trying to have this addressed. Meanwhile, Fishler also vented on X about the inability to reach the team handling the issue by phone.

<blockquote class="twitter-tweet" data-width="300" data-height="400"><p lang="en" dir="ltr">It would be amazing if someone at <a href="https://twitter.com/netsolcares?ref_src=twsrc%5Etfw">@netsolcares</a> was aware of how the internet worked, or even was able to speak about major outages as they occur. Their call center says the office that handles such things &quot;does not have a phone&quot;.</p>&mdash; Hurricane Electric (@henet) <a href="https://twitter.com/henet/status/1808953880404787288?ref_src=twsrc%5Etfw">July 4, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### What is Client Hold?

Client Hold is a domain status code indicating that the domain is currently suspended by the registrar and will not resolve in DNS. This means the domain cannot be accessed or used. This status is typically set by the registrar in cases of legal disputes, non-payment, or when a domain is about to be deleted.

To resolve this issue, one must contact the domain registrar and request the removal of this status code.

> For more information, you can refer to the [Extensible Provisioning Protocol (EPP)](https://www.icann.org/resources/pages/epp-status-codes-2014-06-16-en) on ICANN's official website.

### The impact this time

Apart from IP Transit services, HE also provides NS (Name Server) resolution services. Due to this domain suspension incident, their DNS servers couldn't be resolved, causing many customers' domains to fail as well. To make matters worse, the incident occurred during the annual Independence Day holiday in the United States.

Additionally, HE's support emails rely on this domain. During the suspension, all support emails couldn't function properly. The only way to report issues was via phone.

The main problem lies in the handling process and attitude of the domain registrar. It remains to be seen whether Hurricane Electric will migrate their domain to another registrar.

### Further Thoughts

Have you ever wondered what kind of impact it would have if companies like Google or Apple had their domains suspended?