---
layout: post
id: 
title : Computer Networks 
description: Conceptual understanding of computer networks 
tags: computers networks communication data 
category: [knowledge]
redirect_from:
  - /networks
version: 0.1
---

# Scope

The objective is to provide a high-level conceptual understanding of the why's and how's of computer networks. The means is by providing a series of references which explain concepts well and provide a roadmap through those resources. Also fill in the gaps where needed. Finally we will resolve the gaps through a series of q & a.

# Why do we need computer networks

Computers have computation and data resources. Computers, like people, need to communicate for specific purposes . Without connecting them thier power is limited and data cannot be shared. Generally the problem of networking is how to make computers communicate. Either people or computers need to 'message' between other computers. The analogous model is the postal system where we used to send messages to other people or organizations. The essential of a network is to communicate. The problem of networking to provide the digital mechanisms for people and computers to communicate to other computers. Just like people, different computers speak different lingo, computers are spatially seperated in vast geographies. Most of the solutions provided by current computer networks is very analogous to how 'postal mail' works.

These are the general class of communications that occur between people and computers betweem other computers
- Invoke a command for a provided service ( web-search, store data remotely, purchase tickets, ring a bell etc, send a whatsapp message )
- Read the data from a different computer

A 'computer' is a vague term. It can mean a single machine like your laptop or a data-center server. With todays ubiqutous world, it is more fluid. It is some unit 'actor' which has some share of computation and memory resources which can be connected-to/communicate-with the network. Eg. virtual machines, IOT devices like washing-machines, fridges, mobile-phones, virtual-services

# Main problems in building computer networks

* **Electic communication mechanisms at the physical layer** - mainly a problem of we can encode and trasmit 'information' over electrical medium. Its broadly studied in the field of Information Theory, mechisms to encode and transmit 'digital' information over 'analog' medium. 
* **Language / Protocols** by which computers can understand 'how to communicate' and communicate 'data'. Heterogenity exists everywhere. 'postal mail' from US to India reaches regardless of which language you wrote the letter to. Postal mail systems in the US and India are following some protocols to get your mail to your destination.
* **Addressability & Routing** How do we discover & identify other computers, provide unique identity to billions of devices, how to organize them into a network and how are messages actually 'routed' from end to end. How does you 'postal mail' get from you to your destination magically
* **Systemic problems** which exist at scale of a distributed large scale network like availability, congestion, reliability etc. Think of problems in traffic networks. It is essentially the same
* **Security issues and models** Problems like : a) I sent a secret message in the 'postal mail'. How can I gurantee that nobody read it other than the intended target,  b) I have sensitive data, how can gurantee that I share only privately, etc. These are solved in multiple-ways, there is no one solution fits all, but some general principles are followed.

# First Steps Introduction

The following resources explain the high-level concepts in building the network. This is important to get your grounding - esp when you are encountered with a situation or question - and you first need to relate to what problem or aspect that is addressing before you understand the how.

- This textbook is unique and I see this is used in lot of structured courses. However, for the limited scope, I suggest you only read Chapter 1 ( will share the doc )
- https://web.mit.edu/dimitrib/www/Intro_Data_Nets.pdf
- [berkeleyintro]: <https://people.eecs.berkeley.edu/~wlr/Tutorials/nets.htm> "Key Idea In Networking Berkeley"

- https://cs144.github.io/
- https://www.youtube.com/watch?v=d0TJ8szp4AE
- https://www.ibm.com/cloud/learn/networking-a-complete-guide
[systemsapproach]: <https://book.systemsapproach.org/index.html> "Networking Systems Approach"

# Application Layer Perspective

- http://www.theshulers.com/whitepapers/internet_whitepaper/index.html
[shulerinternetwork]: <http://www.theshulers.com/whitepapers/internet_whitepaper/index.html> "How does the Internet Work - Shuler"

# Hands-On

- TODO
- Netcat based exercises
- dig
- traceroute


# Some History ( if interested )

[internetworks]: <http://web.mit.edu/6.829/www/currentsemester/papers/only-just-works.pdf> "Why the Internet only just works"
[mitintro]: <http://web.mit.edu/6.829/www/currentsemester/materials/lecture2.pdf> "MIT 6.829 Internet Architecture"