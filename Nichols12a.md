# Controlling Queue Delay

# entities in the networks

router
* sending packets wherever
* avoid huge queues, but also want to keep the link busy

TCP
* reliably retransmit
* avoid drops
* wants to go as fast as it can

user's goal
* go as fast as possible

interaction
* with multiple users
* and tension between user low latency and routers wanting to stay busy

what next?
AQM: Active Queue management

# key ideas

Bufferbloat: when we have big, standing queues -> lots of unnecessary delay

user sojourn time to estimate how busy the router is

and idea of good queues vs. bad queues
* good: resolved in one RTTs -- want to be able to absorb bursts
* bad queue: long-term, never clearing queues


we should drop things early
* and if we think we're over capacity, then we want the senders to slow down
* propose CoDel: an easy to deploy AQM that will help
    * improve over RED

What is (ideal) equilibrium?
high utilization

what's the problem in this diagram? (Figure 2 in Nichols12a).

good: it's actually sneding at exactly the bottleneck rate

bad: we have a standing queue of 5 packets, just before the bottleneck

codel's fix
* BBR: drain stage
* codel: drop a packet

RED disadvantage: a few parameters and we dont know how to set them 

Track minimum queue size:
* what?
    * look at queues over last RTTs
* why?
    * minimum helps us tell if the queue cleared at sometime
* goal? 
    * does the queue ever clear?

measure queue size by sojourn time
* what
    * time form packet entering queue to leaving
* why 
    * actual delay
    * minimum sojourn time captures if the queue drains

codel vs RED

delay:
* both case are pretty good

utilization
* RED utilization drops when latency is high

Wireless example: bitrate varies over time
droptail: throughput goes up when

RED: low latency but when bitrate changes, RED has a hard time adapt

Codel: adapt better than RED

How do they track packet arrival time? 
* record now when it enters the router,and compute delay when it leaves 