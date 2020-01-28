---
layout: post
id: 5a6ed8cc-1f2f-4939-b72a-98fb44f7eecb 
title : Computer Networks 
description: Conceptual understanding of computer networks 
tags: computers networks communication data 
category: [knowledge]
redirect_from:
  - /networks
version: 0.1
---

- [Scope](#scope)
- [Overview](#overview)
  - [Why do we need computer networks](#why-do-we-need-computer-networks)
  - [Main problems in building computer networks](#main-problems-in-building-computer-networks)
- [High-Level Understanding](#high-level-understanding)
- [Routing Layer Perspective](#routing-layer-perspective)
  - [Hands On](#hands-on)
- [Application Layer Perspective](#application-layer-perspective)
  - [Hands On](#hands-on-1)
- [Security](#security)
- [Virtual Networks](#virtual-networks)
  - [Cloud Provider Networking Reference](#cloud-provider-networking-reference)
- [Some History ( if interested )](#some-history--if-interested)

# Scope

The objective is to provide a high-level conceptual understanding of the why's and how's of computer networks. The means is by providing a series of references which explain concepts well and provide a roadmap through those resources. Finally the aim to resolve the gaps through a series of q&a/faq.

# Overview

## Why do we need computer networks

Computers are machines which can execute digital logical operations and store digital data. They are ubiqutous and are used in knowledge storing and searching, communication, computation, sensors, agents. The main thing they do is consume data, process data and emit data. Computers have finite computation and data resources. Without connecting them thier power is limited and data cannot be shared. Generally the problem of networking is how to make computers communicate. Either people or computers need to 'message or communicate' between other computers. The essential function of a network is to communicate. The problem solved by networking mechanisms is to provide the digital mechanisms for people and computers to communicate to other computers.

The analogous model, which is useful for understanding, is the postal mail system where we used to send messages to other people or organizations. Just like people, different computers speak different lingo, computers are spatially seperated in vast geographies, the person sending the mail does not know how to route it to the destination, etc. Most of the mechanisms provided by current computer networks is very analogous to how 'postal mail' works. Where necessary, I will try to explain a concept w.r.t this analogy

These are the general class of communications that occur between people and computers betweem other computers
- Request a service / function by communicating a series of commands. Eg. web-search, store data remotely, purchase tickets, ring a bell etc, send a whatsapp message
- Consume or Read the data from a different computer

Note : A 'computer' is a vague term. It can mean a single machine like your laptop or a data-center server. With todays ubiqutous world, it is more fluid. It is some unit 'actor' which has some share of computation and memory resources which can be connected-to/communicate-with the network. Eg. virtual machines, IOT devices like washing-machines, fridges, mobile-phones, virtual-services

## Main problems in building computer networks

* **Electrical communication mechanisms at the physical layer** - mainly a problem of we can encode and trasmit 'information' over electrical medium. Its broadly studied in the field of Information Theory, mechisms to encode and transmit 'digital' information over 'analog' medium. I have not discussed anything about this as this is too low-level for this scope.
* **Language / Protocols** by which computers can understand and co-operate on 'how to communicate' and communicate 'data'. Heterogenity exists everywhere. 'postal mail' from US to India reaches regardless of which language you wrote the letter to. Postal mail systems in the US and India are following some protocols to get your mail to your destination.
* **Addressability & Routing** How do we discover & identify other computers, provide unique identity to billions of devices, how to organize them into a network and how are messages actually 'routed' from end to end. How does you 'postal mail' get from you to your destination magically?
* **Systemic problems** which exist at scale of a distributed large scale network like availability, congestion, reliability etc. Think of problems in traffic networks. It is essentially the same. Again I have not discussed anything about this as it relates to engineering of the underlying system.
* **Security issues and models** How do we address problems like : a) I sent a secret message in the 'postal mail'. How can I gurantee that nobody read it other than the intended target,  b) I have sensitive data, how can gurantee that I share only privately, etc. These are solved in multiple-ways, there is no one solution fits all, but some general principles are followed.

# High-Level Understanding 

The following resources explain the high-level concepts in building the network. This is important to get your grounding - esp when you are encountered with a situation or question - and you first need to relate to what problem or aspect that is addressing before you understand the how.

- [Chapter 1 of this textbook][networkstopdown] This textbook is unique and I see this is used in lot of structured courses. However, for the limited scope, I suggest you only read Chapter 1 (will share the doc)
- [Chapter 1 of this book][systemsapproach] 
- [This chapter][datanets]
- [First two in Lecture Notes][cs144]

# Routing Layer Perspective

Invoking the analogy to the 'postal-mail' system, this is the layer of the network which is responsible for routing a message from address A to address B. When we write a letter, we put it in an envelope. The postal system does not care about what is in the envelope. There are two main things on the envelope - From and To address. The postal system is built to define addressing schemes, building delivery networks to route the envelope between From and To. It is the service it provides. Different countries have different addressing schemes inside themselves, but there are some global common properties like 'country' and 'zipcode'. A mail from US, knows that it only needs to send it somewhere in India. In India, some receiver knows only to send it to some State or City, so and so forth till the last-mile.

This is the core-service provided by computer networking. There are ways to heirarchically build networks locally to global Internet scale and protocols to route efficiently between them. Few things to pay attention to while understanding the 'routing' layer are
- Hierarchy of networks
- Packet Swithing - All information is sent as packets ( think of envelopes ) and there are exchanges which recevie, sort and forward this packets at magically unbelievable speeds and scale.
- This wholistically is called 'Internet Protocol' for the global Internet.
- IP address scheme and CIDR ( resources below )
- Local networks and Ethernet ( not to worry about details here )
- DNS. All addressing is some number. Think of this as a directory which maps www.google.com -> the numerical address in the IP layer

Read the following to understand this layer :

- [Week 3 and Week 5 Lectures][cs144]
- [chapter 3][systemsapproach]
- [chapter 4][networkstopdown]
- [guide][ibmnetguide]
- [dns][dnswhat]
- [CIDR & Subnetting][cidr]

## Hands On

- DNS

This is an example to query the directory for www.google.com. See how it answers back with the IP address to use. Try out other domain names which you like. 

```text
➜ dig www.google.com

; <<>> DiG 9.10.6 <<>> www.google.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 46707
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;www.google.com.			IN	A

;; ANSWER SECTION:
www.google.com.		96	IN	A	172.217.3.164

;; Query time: 2 msec
;; SERVER: 192.168.1.1#53(192.168.1.1)
;; WHEN: Tue Jan 28 09:57:11 PST 2020
;; MSG SIZE  rcvd: 59
```

- IP Packet Route

We can inspect the route a packet takes to reach the destination IP. We can see the mulitple hops where the exchanges are which recieve and forward on the packets based on routing protocols. Nobody know the global route. It is all distributed protocols which are designed to effectively route. The intermediaries are called 'routers' and they only look at the envelope. They don't care about what is inside them.

  - Remote server located very 'close' on the path
```text
➜ traceroute -I 172.217.3.164 
traceroute to 172.217.3.164 (172.217.3.164), 64 hops max, 72 byte packets
 1  rt-b07fb9909ca5 (192.168.1.1)  2.760 ms  0.853 ms  0.681 ms
 2  67-218-102-107.cust.layer42.net (67.218.102.107)  7.565 ms  7.595 ms  7.778 ms
 3  cr1-tukhe-a-be151.bb.as11404.net (174.127.182.56)  9.341 ms  8.057 ms  7.607 ms
 4  be10.agg4-sea-a.bb.as11404.net (174.127.150.162)  8.216 ms  8.858 ms  8.103 ms
 5  hu0-0-0-22.cr3-sea-a.bb.as11404.net (65.50.198.48)  9.398 ms  8.532 ms  9.644 ms
 6  be55.cr2-sea-a.bb.as11404.net (65.50.198.67)  7.637 ms  10.094 ms  9.488 ms
 7  72.14.198.216 (72.14.198.216)  7.581 ms  7.548 ms  7.912 ms
 8  108.170.245.97 (108.170.245.97)  8.921 ms  8.553 ms  8.222 ms
 9  108.170.233.157 (108.170.233.157)  9.418 ms  7.582 ms  8.713 ms
10  sea15s11-in-f164.1e100.net (172.217.3.164)  7.959 ms  8.289 ms  8.228 ms
```
  - Remote server geographically seperated by a large distance
```text
➜ traceroute -I 104.87.240.94
traceroute to 104.87.240.94 (104.87.240.94), 64 hops max, 72 byte packets
 1  rt-b07fb9909ca5 (192.168.1.1)  2.705 ms  0.840 ms  0.766 ms
 2  67-218-102-107.cust.layer42.net (67.218.102.107)  7.617 ms  7.553 ms  8.000 ms
 3  cr1-tukhe-a-be151.bb.as11404.net (174.127.182.56)  8.951 ms  8.019 ms  7.991 ms
 4  be10.agg4-sea-a.bb.as11404.net (174.127.150.162)  8.473 ms  9.622 ms  7.523 ms
 5  hu0-0-0-22.cr3-sea-a.bb.as11404.net (65.50.198.48)  8.157 ms  9.171 ms  8.256 ms
 6  be55.cr2-sea-a.bb.as11404.net (65.50.198.67)  9.351 ms  8.802 ms  9.777 ms
 7  sea-b2-link.telia.net (62.115.49.138)  7.717 ms  8.764 ms  13.249 ms
 8  ntt-ic-337606-sea-b2.c.telia.net (213.248.70.13)  9.385 ms  9.525 ms  9.709 ms
 9  ae-1.r22.sttlwa01.us.bb.gin.ntt.net (129.250.2.9)  9.950 ms  8.432 ms  8.332 ms
10  ae-13.r30.tokyjp05.jp.bb.gin.ntt.net (129.250.4.143)  184.182 ms  203.792 ms  205.301 ms
11  ae-2.r03.tokyjp05.jp.bb.gin.ntt.net (129.250.3.33)  204.333 ms  204.363 ms  204.716 ms
12  ae-5.akamai.tokyjp05.jp.bb.gin.ntt.net (61.213.160.42)  119.887 ms  123.021 ms  165.682 ms
13  a104-87-240-94.deploy.static.akamaitechnologies.com (104.87.240.94)  204.893 ms  203.965 ms  204.570 ms
```

# Application Layer Perspective

- TODO

## Hands On

- Netcat based exercises
```text
$> nc -l 1300
$> nc localhost 1300
```

- Http Request/Response

```text
>> establish tcp connection from myhost <-> webserver at port http/80
09:20:05.657283 IP myhost.53989 > webserver.http: Flags [SEW], seq 2901166647, win 65535, options [mss 1460,nop,wscale 6,nop,nop,TS val 1013261041 ecr 0,sackOK,eol], length 0
09:20:05.666769 IP webserver.http > myhost.53989: Flags [S.], seq 2555443522, ack 2901166648, win 60192, options [mss 1380,sackOK,TS val 3530189958 ecr 1013261041,nop,wscale 8], length 0
09:20:05.666835 IP myhost.53989 > webserver.http: Flags [.], ack 1, win 2052, options [nop,nop,TS val 1013261050 ecr 3530189958], length 0
<<

>> myhost sends http request
09:20:28.836833 IP myhost.53989 > webserver.http: Flags [P.], seq 1:16, ack 1, win 2052, options [nop,nop,TS val 1013284199 ecr 3530189958], length 15: HTTP: GET / HEAD/1.1
09:20:28.846762 IP webserver.http > myhost.53989: Flags [.], ack 16, win 236, options [nop,nop,TS val 3530213138 ecr 1013284199], length 0
09:20:30.860359 IP myhost.53892 > webserver.https: Flags [.], ack 3156708017, win 4100, length 0
09:20:30.868600 IP webserver.https > myhost.53892: Flags [.], ack 1, win 1005, options [nop,nop,TS val 159075118 ecr 1013240820], length 0
09:20:31.336058 IP myhost.53989 > webserver.http: Flags [P.], seq 16:17, ack 1, win 2052, options [nop,nop,TS val 1013286690 ecr 3530213138], length 1: HTTP
09:20:31.344761 IP webserver.http > myhost.53989: Flags [.], ack 17, win 236, options [nop,nop,TS val 3530215637 ecr 1013286690], length 0
<<

>> webserver replies back with response
09:20:31.345048 IP webserver.http > myhost.53989: Flags [.], seq 1:1419, ack 17, win 236, options [nop,nop,TS val 3530215637 ecr 1013286690], length 1418: HTTP: HTTP/1.0 400 Bad Request
09:20:31.345050 IP webserver.http > myhost.53989: Flags [P.], seq 1419:1713, ack 17, win 236, options [nop,nop,TS val 3530215637 ecr 1013286690], length 294: HTTP
<<

>> webserver has also closed the TCP stream on it's end 
09:20:31.345051 IP webserver.http > myhost.53989: Flags [F.], seq 1713, ack 17, win 236, options [nop,nop,TS val 3530215637 ecr 1013286690], length 0
09:20:31.345078 IP myhost.53989 > webserver.http: Flags [.], ack 1713, win 2025, options [nop,nop,TS val 1013286698 ecr 3530215637], length 0
09:20:31.345095 IP myhost.53989 > webserver.http: Flags [.], ack 1714, win 2037, options [nop,nop,TS val 1013286698 ecr 3530215637], length 0
<<

>> myhost closes the TCP stream from it's end
09:20:31.345248 IP myhost.53989 > webserver.http: Flags [F.], seq 17, ack 1714, win 2048, options [nop,nop,TS val 1013286698 ecr 3530215637], length 0
09:20:31.356523 IP webserver.http > myhost.53989: Flags [.], ack 18, win 236, options [nop,nop,TS val 3530215648 ecr 1013286698], length 0
09:20:35.927085 IP myhost.53887 > webserver.https: Flags [.], ack 2759801338, win 2048, length 0
09:20:35.937100 IP webserver.https > myhost.53887: Flags [.], ack 1, win 1050, options [nop,nop,TS val 3530220228 ecr 1013200256], length 0
<<
```

# Security

- TODO

# Virtual Networks

- TODO

## Cloud Provider Networking Reference

# Some History ( if interested )

- [Architectural decisions][mitintro]
- [Stability of the architecture][internetworks]
- [Overview][berkeleyintro]

[networkstopdown]: https://www.amazon.com/Computer-Networking-Top-Down-Approach-7th/dp/0133594149 "Computer Networks Top Down Approach"
[systemsapproach]: https://book.systemsapproach.org/index.html "Networking Systems Approach"
[mitintro]: http://web.mit.edu/6.829/www/currentsemester/materials/lecture2.pdf "MIT 6.829 Internet Architecture"
[cs144]: https://cs144.github.io/ "Stanford CS144"
[datanets]: https://web.mit.edu/dimitrib/www/Intro_Data_Nets.pdf "Intro To Data Networks Dmitri"
[berkeleyintro]: https://people.eecs.berkeley.edu/~wlr/Tutorials/nets.htm "Key Idea In Networking Berkeley"
[internetworks]: http://web.mit.edu/6.829/www/currentsemester/papers/only-just-works.pdf "Why the Internet only just works"
[ibmnetguide]: https://www.ibm.com/cloud/learn/networking-a-complete-guide "IBM Networking Guide"
[shulerinternetwork]: http://www.theshulers.com/whitepapers/internet_whitepaper/index.html "How does the Internet Work - Shuler"
[lifepacket]: https://www.youtube.com/watch?v=d0TJ8szp4AE "Life Of A Packet"
[iplookup]: https://securitytrails.com/blog/ip-lookup-strategy "IP Lookup Tools"
[cidr]: https://www.ionos.com/digitalguide/server/know-how/cidr-classless-inter-domain-routing/ "CIDR and Subnetting"
[ports]: https://www.experts-exchange.com/articles/22179/Network-Ports-what-they-are-and-they-work.html "Ports"
[dnswhat]: https://cloudacademy.com/blog/how-dns-works/ "How DNS Works - CloudAcademy"