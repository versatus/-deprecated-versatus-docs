# Language Standard Libraries

Web Assembly is designed to be very secure and to limit what an executing program is able to do. As a result, many things you might ordinarily expect to be able to do in a program written in your language of choice may be limited or disabled entirely. This includes things like file and network I/O and multi-threading.

However, when you consider a smart contract and how it is executed (either traditionally or on Versatus), the reasons for limiting these types of I/O become a little more obvious. A smart contract is executed across a large quorum of nodes on a network -- in some networks, this may be all of the nodes on the network. Now imagine if a smart contract were able to make a bunch of network connections outside of the smart contract environment. This might make it possible for a smart contract to be developed to target one or more services on the internet, and for that to create a Distributed Denial-Of-Service (DDOS) attack. This is just one example from the whole security attack surface.

In order to keep things simple and secure to develop, host and audit, we severely limit these kinds of operations for smart contracts. At least in the short term.
