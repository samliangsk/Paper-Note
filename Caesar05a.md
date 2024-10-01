# BGP Routing Policies in ISP Networks

There are iBGP and eBGP, which are for internal ASes and External. Border routers will distribute the route learned to internal and possibly other border routers using iBGP.

BGP is set to be "**Incremental**," which means only the changes are communicated. which also mean it is stateful.

BGP is also a path-vector protocol, where advertisements contain a list of ASes used to reach the destination.

BGP is prefix based, and it will advertise all the ASes it can reach.

## BGP update messages

* a list of prefixes being advertised
* a list of prefixes being withdrawn
* a list of route attributes that describe various characteristics of each advertised route

## interior gateway protocol (IGP)

IGP is the protocol that BGP routers learn internal routes and topology.

Each router combines the BGP and IGP information to construct a forwarding table that maps each destination prefix to one or more outgoing links along shortest paths through the network to the chosen border router.

## Metrics that influence the decisions of BGP

### LocalPref

The first step of the decision process

### MED (multi-exit discriminator)

Help decide which peering link to use when there are multiple links between ASes

### 


to be continued: P7 1/4
