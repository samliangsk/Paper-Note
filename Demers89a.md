# Analysis and Simulation of a Fair Queueing Algorithm

# summary

end user can exploit FCFS to get more than their fair share

fix: fair queueing

* emulate round-robin bit-by-bit transmission
* because that is "obviously" fair
* and they can map from bit-by-bit to packet-by-packet

bidding to get better promptness for low-rate flows

review of what the options are
* what to send?
* what to buffer/drop?
* when to send?

* **define max/min fairness**

# Congestion control
source and destination
* ex: TCP BBR
* advantages: minimize complexity in router (and put it in the end-host, where there is lots of spare CPU); easier to deploy; source of the traffic
* disadvantages: end-points might be malicious

router ("gateways"): network layer
* ex: RED, Codel, fair queuing
* advantages: centrally control and enforcement
* disadvantages: cost: in dollars, and CPU cost: routers are busy (especially at the time we need them to do enforcement)

other places?: XCP in bot routers and endpoints

# Fair Queueing

Fairness
* to whom: conversations (new called flows: src-dest addr-port pairs)
* alternatives
* quality: always (not just statistical)
* def: max-min

Priority: maybe we give bonus to people who don't use full share
why is fairness hard?
* routers don't neccessarily have a complete view
  * how mnay connections
  * how fast do they want ot send
* senders are distributed
  * can't tell them all the same thing
  * they have different RTTs -> so some will react slower
* adversarial problem: some people may try to get more, or they have bugs or weak codes
* computational cost
  * big concern about per-flow state in routers
 
# max-min fairness

def:
* no user gets more than request
* no better allocation
* "condition 2 is recursively true" if we remove the minimal user and reduce the total resource accordingly

# Defining terms
Round: let's give something to all active flows
R(t): number of rounds handeled up time t
dR(t)/dt: 1/Nac(t)
Nac(t): number of active flows at time t
Si, Fi: start and finish time of packet i
Bi: "bid"
