Motivation

An NDN node implements in-network caching through a Content Store (CS), which is widely studied in the literature. NFD, the most popular NDN forwarder implementation, offers only a very limited facility to observe the CS runtime behavior (just plain logging).

This project is to design and implement a Content Store Management protocol for NFD. The protocol would allow experimenters and operators to instrument the CS, to understand the effectiveness of in-network caching. It also includes a command to erase selected CS entries for experiment purposes.

Contribution to NDN

Provide visibility into the Content Store, an important component of an NDN node.

Tasks

CS hit/miss counters: Publish a status dataset at /localhost/nfd/cs/info, providing CS hit/miss counters. Implement nfdc cs info command to show these counters.
CS enumeration: Provide a CS enumeration operation at /localhost/nfd/cs/query/PREFIX (where PREFIX is encoded as a name nested in one component), listing the first 256 Data names (no implicit digest) under the specified prefix. Implement nfdc cs list prefix PREFIX command to execute the query.
CS erase entry command: Add a control command at /localhost/nfd/cs/erase, that erases CS entries under a name prefix specified in the parameters, limited to the first 256 entries. Implement nfdc cs erase PREFIX command to execute the command and show the number of erased entries.
Required Knowledge for Participants

C++11
A computer capable of compiling and running NFD (can be a virtual machine)
Knowledge about NFD internals, especially management, is a plus
Expected Outcome

Use ndnping or ndn-traffic-generator to send traffic through NFD. Demonstrate the nfdc cs subcommands implemented in this project.
