# Trinocular: Understanding Internet Reliability Through Adaptive Probing

# summary

outage detection system

looking for reachability to /24s blocks

adaptive probing
* send packets (ICMP echo request) to see if the block is reachable
* but vary how mnay it sends: try to send "just enough"
* uses Bayesian inference to decide when to stop
* tries to minimize traffic: goal: way less than background radiation
    * (background radiation: the random traffic you get on any public internet when you have public IP)

to bootstrap, it uses block history

probes at regular intervals (every 11 minutes)
* guarantee freshness

Why do we care about background radiation
* we get unsolicited address
