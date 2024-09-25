#

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

