# Trinocular: Understanding Internet Reliability Through Adaptive Probing

# summary

outage detection system

looking for reachability to /24s blocks

adaptive probing
* send packets (ICMP echo request) to see if the block is reachable
* but vary how mnay it sends: try to send "just enough"
* uses Bayesian inference to decide when to stop
* tries to minimize traffic (parsimonious): goal: way less than background radiation
    * (background radiation: the random traffic you get on any public internet when you have public IP)

to bootstrap, it uses block history

probes at regular intervals (every 11 minutes)
* guarantee freshness

Why do we care about background radiation
* we get unsolicited address

What are some aspect that the paper telescipe to cover?

Outage centric
* measuring B(u) belief, from 0 to 1 denoting the certainty that a node is down or up

What cause outage?
* underwater cable break
* gov shutdown
* natural disasters
* DDoS attacks could cause packet loss
* human error
* backhoes cutting terrestrial links
* power outages
* router may fails

Where is affected?
* cuts of major cables can make a big deal for countries
* or smaller regions may be just a neighborhood
* websites
    * from power outages or equipment failure
    * or content providers (but they likely have multiple data centers, or even IP anycast)
* datacenters
    * human errors

Pinging the world: Responses

* possitive reply: reach some destination -> the block is active
* error (negative reply): destination unreachable -> the block is not routable
* no reply: timeout.. why? -> we cannot tell what's there or not
    * maybe they have a firewalls
    * maybe the query was lost? or the reply was lost? (congestion or DDoS)
    * maybe the IP is not in use? or maybe it's no longer in use?
    * in some cases, the block is reachable, but sometimes not

# Trinocular Mechanisms

learn from history

send probes in each round
* basic probe (each 11 min)
* adaptive probes that follows (after timeout 3 sec)
* decision function based on the replies (or non-replies) using Bayesian inference

# Probing politely: Just enough

polite: minimal traffic to your net

positive responses -> block is up

instead: probe one by one

find 1 is up -> stop early

if try is down -> try again

several fail -> block down

# why multiple observers

if there is a failure near a VP, that's really the VP's problem not the internet's.

# Who to probe and what to expect

# Questions

How might increasing use of firewalls affet Trinocular? what alternatives?

* other kinds of protocols

How could Trinocular handle IPv6?

* bigger block size
