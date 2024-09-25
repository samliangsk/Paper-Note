# Routing Stability in Congested Networks: Experimentation and Analysis

## Solving the OSPF Markov Model
with math, Markov chains can yield closed-form solutions

## u2d OSPF vs BGP

why BGP so complex?

## d2u model of OSPF

## OSPF vs BGP

All about TCP property

### failure

want larger times (so longer until failure)

why? BGP lasts longer, becasue TCP is retrying for you

### rocover

want a small reoery time

TCP takes several successes to bring up the connection and get the KEEPALIVE through

## Questions

### could we use ML to predict future traffic patterns? would that help routing stability?

* Maybe we should dynamically allocate traffic to routing vs. data?

    * can you prioritize routing

* allocate extra buffers to routing when we are busy?

### what if routers could get more processing power during peak loads?

* not very easy

### What would happen to routing stability in different types of topologies? (like mesh networks?)

With lots of links, maybe you can use other paths to sned on

### how would real-time traffic affect routing stability?

might need to consider over capacity

if RT is not congestion reacitve, then RT might be much more challenging to manage (than non-RT)

