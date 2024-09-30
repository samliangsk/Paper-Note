# Why Is It Taking So Long to Secure Internet Routing?

## Key ideas

### BGP is easy to attack
route hijacking: someone else announces your route, getting your traffic
* prefix hijack
* sub-prefix hijack

route leaks

### There are some defenses that we are working on 

prefix filtering

RPKI: originator if the route is verifiable

BGPSEC: make every hop of BGP verify its neighbor

### BGP has lots of policies in it so it can be harder to get agreement

## (sub)prefix hijacking

### prefix hijack

someone else announces 128.9/16 (USC prefix)

people apply BGP, and some of them may prefer that attackers announcement

if the attackers is closer to you, you will believe them

### subprefix hijack

someone else annouces a LONGER prefix (128.9.128/17)

everyone prefers the longer prefix

Google in Dodo/Indonesia

## Route leaks

you announce routes for too many networks (ones that are not yours)

an accidental hijack

example: Pakistan's announcements trying to block Youtube

### Filtering

each AS should filter what routes it announces and what it accepts

* implemented as accept list in one's BGP config (in you RIB)
* info comes either from yourself (ex: w/your customers)
* Big databases (ex: Routing Arbiter and IRR) of publicly provided routing policies, so they can know about what happens w/ ASes that are not their customers
* Tier-1 ASes, because they have lots of clients and peers, and also their clients have clients...
* IXP: does not filter, because there's no such need, and they are mostly private connections
* CDN/hypergiants (Google/Meta): Lots of peers, and there are a ton of customers,


### RPKI: Resource Public Key Infrastructrure

* each originator of a prefix has a signed (with their public-private key pair) record (RPKI record) that says who they are
* anyone can find AS's public keys, and confirm their signatures -> verify the correct person is announcing the prefix
* pro: all the security is offline, and can be done daily (so router CPU does not matter)
* con: only protects the origin, but most routing requires several hops

### BGPSEC

* sign all BGP messages with your peers, and verify them
* pro: lets us validate every hop on the path (not just the originator)
* con: online cryptography (and people that router processors are not very fast)
