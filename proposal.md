# Efficient Synchronization and Reconciliation of Ordered Data Structures

## Abstract

Given two nodes with a bidirectional communication channel, each of them holding a data structure, the *synchronization* problem asks for mirroring the contents of one node's data structure to the other node, the *reconciliation* problem asks for both nodes obtaining any missing data. An efficient solution should avoid redundantly sending data the other node already holds.

We give conceptually simple yet asymptotically efficient solutions based on recursively exchanging fingerprints which summarize the content of subsets of the data structures of exponentially decreasing size. We apply the technique to sets, maps and tries. For data structures containing n items, this leads to O(log(n)) roundtrips, the fingerprints can be computed in O(1) time per roundtrip, based on an auxiliary data structure which requires O(n) space and which can be updated to reflect changes to the underlying data structure in O(log(n)) time.

To minimize roundtrips, the technique requires up to O(n) space per synchronization session. It can be adapted to require only a bounded amount of memory, which is essential for robust, scalable implementations. While this increases the worst-case number of roundtrips, it guarantees continuous progress, particularly in adversarial environments.
