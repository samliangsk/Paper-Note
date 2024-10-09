# Congestion Control for High Bandwidth-Delay Product Networks

# key ideas

Let's design a transport protocol and router **from scratch**

Let the router tell the transport layer what to do

we have to do this ebcause tomorrow's links are often high bitrate/delay and need 100s or 1000s of packets in flight

XCP is the Explicit Control Protocol

sperate fiarness from congestion control

and do this without per-flow state in the router

# fairness:

AIMD
* increase evenly?
    * adding the same to everyone helps the pooorest converge no the median

* decrease in proportion
    * biggest person can slow down the most

* why shuffle?
    * mix things around so we dont get stuck in a steady state that is unfair

# xcp utilization

why not before?
* overheads, routers are very slow back in the days



# Understanding XCP Feedback

if you have per-flow state, its easy:
T_p = h+max(phi, 0): positive feedback
T_n = h

...

# negative feedback

idea:  penalize relative to rate



