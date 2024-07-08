---
title: HE.NET 網域被停止解析
description: 網域註冊商因為錯誤處置，導致網域名稱被停止解析
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

前幾天適逢美國獨立日，許多企業也放假一天。

然而，就在這天，大型網路服務提供商 Hurricane Electric (HE, AS6939) 的網域名稱 [HE.NET](https://he.net/) 被停止解析。這起事件在 NANOG (North American Network Operators' Group) 的 Mailing List 引起很大討論。

## 事件起因

HE.NET 在 2024-07-04 時，其網域被全面停止解析。這次是由於網域註冊商 Network Solutions 將該網域名稱置於 "Client Hold" 狀態，同時 X 平台上也有人分享該事件。

<blockquote class="twitter-tweet" data-width="300" data-height="400"><p lang="en" dir="ltr">Public Service Announcement: Hurricane Electric’s bgp dot he dot net was unreachable for a bit. Looks like the fine folks over at <a href="https://twitter.com/henet?ref_src=twsrc%5Etfw">@henet</a> forgot to renew their domain and it expired. Oops! It’s now back; but, maybe still unreachable for a few because <a href="https://twitter.com/hashtag/DNS?src=hash&amp;ref_src=twsrc%5Etfw">#DNS</a>. <a href="https://t.co/DtYFvWoAsd">pic.twitter.com/DtYFvWoAsd</a></p>&mdash; Dr. Peering (@DrPeering) <a href="https://twitter.com/DrPeering/status/1808943281482706963?ref_src=twsrc%5Etfw">July 4, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

HE 的 Senior Director - Reid Fishler 也在 NANOG Mailing List 中發布[聲明](https://mailman.nanog.org/pipermail/nanog/2024-July/225901.html)，表示 Network Solutions 因為接到一個釣魚網站的投訴，因此將整個網域置於 Client Hold 狀態。這個投訴涉及的一個網頁，實際上只是一個關於另一個網域資訊的頁面，位於 bgp.he.net 子網域上。

> [bgp.he.net](https://bgp.he.net) 是 HE 推出的一個 BGP Toolkit，裡面包括各種不同的 AS、Prefix。在 AS 頁面中，會 Preview 從 PeeringDB 抓到的網站。

HE 的高層已經嘗試打電話和發送電子郵件給 Network Solutions，但他們拒絕以任何緊急情況來處理這個問題。同時，他也在 X 上吐槽 Network Solutions 中，負責處理此問題的團隊沒有辦法透過電話聯絡。

<blockquote class="twitter-tweet" data-width="300" data-height="400"><p lang="en" dir="ltr">It would be amazing if someone at <a href="https://twitter.com/netsolcares?ref_src=twsrc%5Etfw">@netsolcares</a> was aware of how the internet worked, or even was able to speak about major outages as they occur. Their call center says the office that handles such things &quot;does not have a phone&quot;.</p>&mdash; Hurricane Electric (@henet) <a href="https://twitter.com/henet/status/1808953880404787288?ref_src=twsrc%5Etfw">July 4, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Client Hold 是什麼？

Client Hold 是一種網域狀態碼，用來指示該網域目前被註冊商暫停，並且不會在 DNS 中解析。這也代表網域將無法被訪問或使用。這個狀態通常由註冊商設置，通常在法律糾紛、未付款或網域要被刪除時會出現。

要解決這個問題，只能聯絡網域註冊商，請他們移除這個狀態碼。

> 有興趣可參考 ICANN 官網的 [Extensible Provisioning Protocol (EPP)](https://www.icann.org/resources/pages/epp-status-codes-2014-06-16-en) 資訊。

## 這次受到的影響有多大？

HE 除了 IP Transit 業務以外，還有提供 NS (Name Server) 解析服務。因為這次的網域中斷事件，導致 DNS 伺服器無法被正常解析，大量客戶的網域也跟著解析失效。更糟糕的是，發生事件的當下，是美國一年一度的獨立日假期。

同時，HE 的 Support Mail 也仰賴該網域，在網域中斷期間，所有報修 Email 也無法正常運作。只能透過電話報修。

這次問題主要在網域註冊商的處理流程及態度，後期只能看看 Hurricane Electric 會不會將網域名稱遷移到其他註冊商了。

## 延伸思考

不知道大家有沒有想到，如果像 Google、Apple 這種公司的網域也停擺了，那會造成多大的影響呢？