---
description: >-
  https://www.cloudflare.com/es-es/learning/ddos/glossary/ddos-blackhole-routing/
---

# DDoS blackhole

### What is DDoS blackhole routing?

DDoS blackhole routing/filtering \(sometimes called blackholing\), is a countermeasure to mitigate a [DDoS attack](https://www.cloudflare.com/es-es/learning/ddos/what-is-a-ddos-attack) in which network traffic is routed into a “black hole,” and is lost. When blackhole filtering is implemented without specific restriction criteria, both legitimate and malicious network traffic is routed to a null route or black hole and dropped from the network. When using protocols that are connectionless such as [UDP](https://www.cloudflare.com/es-es/learning/ddos/glossary/user-datagram-protocol-udp), no notification of the dropped data will be returned to the source. With connection oriented protocols like [TCP](https://www.cloudflare.com/es-es/learning/ddos/glossary/tcp-ip), which require a handshake to connect with the target system, a notification will be returned if the data is dropped.

For organizations that have no other means of blocking an attack, blackholing is a widely available option. This method of mitigation may have serious consequences, potentially making it an undesirable option to mitigate a DDoS attack. Similar to the way antibiotics destroy both good and bad bacteria, when implemented improperly this type of DDoS mitigation will indiscriminately disrupt sources of traffic to the network or service. Sophisticated attacks will also use [variable IP addresses](https://www.cloudflare.com/es-es/learning/ddos/glossary/ip-spoofing) and attack vectors, which can limit the effectiveness of this type of mitigation as a sole means of disrupting the attack.

A key consequence of using blackhole routing when good traffic is also affected, is that the attacker has essentially accomplished their goal of disrupting traffic to the target network or service. Even though it can help a malicious actor accomplish their goal, blackhole routing can still be useful when the target of the attack is a small site that's part of a larger network. In that case, blackholing the traffic directed at the targeted site could protect the larger network from the effects of the attack.

### Case study: how a pakistani ISP shut down YouTube with blackhole routing

In 2008 YouTube was down for hours one day thanks to Pakistan Telecom's use of blackhole routing. This happened after the Pakistani Ministry of Communication sent out orders to have YouTube blocked nation-wide in response to a YouTube video that contained a Dutch cartoon depicting the prophet Muhammad. Pakistan's government-owned telecommunication service responded to these orders with a blackhole routing solution, but their solution created unexpected side-effects.

Pakistan Telecom created a blackhole route and broadcast instructions claiming to be the legitimate destination for anyone trying to reach YouTube's web addresses. That traffic was then sent to the blackhole route and dropped. The problem is that Pakistan Telecom used [BGP](https://www.cloudflare.com/es-es/learning/security/glossary/what-is-bgp)\* to share this route with ISPs all over the world. So Pakistan effectively broadcast to Internet providers worldwide that they were the correct destination for YouTube traffic and they then sent all YouTube-bound traffic into a black hole. Fortunately YouTube has a very sophisticated technical team and they were able to identify and fix the problem within hours, but this example shows a serious risk that comes with using blackhole routing.

\*BGP stands for Border Gateway Protocol, it manages how packets are routed across the Internet. Another well-known BGP mix-up even brought Google down, see this [Cloudflare blog post](https://blog.cloudflare.com/why-google-went-offline-today-and-a-bit-about/) to learn more about that.



TODO: resumir esto.



