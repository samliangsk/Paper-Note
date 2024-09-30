# In Search of the Elusive Ground Truth: The Internet’s AS-level Connectivity Structure

## AS topologies

* compare ground truth and public view
* graph where nodes are ASes and edges are if those ASes have a business relationship
    * can two ASes echange traffic? do they have an active BGP session?
* who cares about AS topologies?
    * ASes control where traffic goes on the internet
    * if we want to understand or simulate that, we need to know the topology
    * can reveal business disputes, like when 2 ASes cannot agree to exchange traffic
    * can reveal political choices, like de-peering due to sanctions

## Limitations of current methods

* there are invisible and hidden links, they could be missed, or seen if we are careful

## Types of AS business relationships

customer-provider
* TRANSIT
* provider send all routes to their customers
* provider expports customer's routes to everyone
* the provider takes the customer's money

peer-peer
* Tier-1 ASes connected with each other
* announce their customer's routes (and traffic) peer
* but do not anounce your other peers
* settlement free

sibling-sibling
* connections between non-tier-1 ASes
* often settlement free
* usually between large enterprices or reginal networks

Other types of links
* backup: a non-perferred path from one AS out
    * invisible in the AS PATHs
* PNI (Private Network Interconnect): a direct link between two ASes

## public views

the routing table from many locations

Route views and other public BGP sources

R&E (research and education) netowrks do share their topologies

## Private:

* data from one tier-1
    * router configs: what they say they want
    * syslog: what actually happens

* and one tier-2

What's ground truth?
* actual topologies for GEANT and Internet2

## invisible links we cannot see

each routing table the best path out of that location to each prefix

* so we see lots of customer-provider path

but hard to see connections lower in the hierarchy
* ex: sibling connections between reginal ASes

* no valley routing
    * go to your transit and up to a tier-1
    * then you go down to your destination
    * you only see sibling links when they're preferred, and they are only preferred if you have an observer on one side of the link

# Hidden links

* backup links
* not usually active, only become active with the primary link fails
* and links don't usually fail
* so we need to observe for a long time



