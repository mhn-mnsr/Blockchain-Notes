Alternative Consensus and Enterprise Blockchain 
===============================================

At the most fundamental level, all public blockchains rely on efficient
and secure consensus algorithms. In our analysis of Bitcoin and
Ethereum, we learned how the Proof-of-Work algorithm allows both
networks to come to consensus on blocks. Consensus algorithms in general
ensure that the network on which it is deployed agrees on a singular
blockchain as the only truth, and that malicious users cannot
successfully break or fork the blockchain. In study, we find that
Proof-of-Work wastes enormous amounts of energy for computation, may
lead to centralization where electricity (for mining) is cheap, and in
general does not scale well. This note will discuss some alternative
consensus protocols, and how they are used both in public and private
blockchains.

Properties of a Distributed System 
==================================

Recall that a state is a condition at a specific period of time. Think
the state of your bank account, and the balance included in it. Think
the state of the Ethereum network, and the balances of all the accounts
in Ethereum. In order to ensure correctness of state, distributed
systems must have two essential properties.

The first essential property is **liveness**, which says that the
current state of a system satisfies liveness if there is some path from
the current state to some future state where the liveness property also
holds true. In simpler terms, the liveness property guarantees that a
network will always make progress, and that something good will happen
eventually. In the context of consensus algorithms, liveness guarantees
that all nodes will eventually decide on a value, whih ultimately
defines a state. (Note the use of the word *decide* and *agree*, because
a node may have to conform to what is agreed upon by the rest of the
network.)

The second essential property is **safety**, which says that the current
state guarantees the safety property if *all* the future states that can
be reached from the current state also satisfies the safety property. In
simpler terms, the safety property guarantees that something bad will
never happen. In regards to consensus algorithms, safety guarantees that
no two nodes will decide on different values.

In the **Fischer Lynch Paterson (FLP) Impossibility Theorem**, there are
a total of three fundamental properties of distributed systems. We
introduced liveness and safety already. The third property is fault
tolerance, which guarantees that if one node in a system fails, the
entire node will not fail. FLP Impossibility states that in any
consensus system, only two of the three properties can be satisfied at
once. Although fault tolerance is important, we will focus mainly on how
to ensure safety and liveness in this note.

Distributed Properties in Consensus 
===================================

In an asynchronous distributed system, we cannot guarantee decisions
(safety) and correct decisions (safety) at the same time. You can only
guarantee eventual liveness or eventual consistency. This means that if
no new updates are made to a data item, eventually all access to that
item will return the last updated value. Everyone sees the same thing.
In terms of consensus on a blockchain, eventual consistency means that
all nodes in a network will eventually share a common view of the state
of the blockchain. Keep in mind that blockchains are immutable — blocks
can only be appended to the end of a blockchain, and that it is
difficult to alter the middle of a blockchain.

Key Consensus Protocol Problems 
===============================

Two key problems that consensus protocols must tackle are Sybil attacks
and the Byzantine Generals Problem. Recall that Sybil attacks involve
flooding a network with false identities and transferring malicious
information to other nodes. Bitcoin makes Sybil attacks difficult
because of its underlying Proof-of-Work algorithm and also some design
considerations, including restrictions on connecting with geographically
close IP addresses.

The Byzantine Generals Problem is a classic agreement problem that
involves a group of Byzantine generals surrounding a city, each in a
different location.

Key Terms 
=========

A collection of terms mentioned in the note which may or may not have
been described. Look to external sources for deeper understanding of any
non-crypto/blockchain terms.

1.  **VOCAB WORD** — Definition.


