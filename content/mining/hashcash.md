# Hashcash

A core building block of the Bitcoin protocol is the Hashcash concept. Bitcoin uses Hashcash to provide security from malicious alterations of the Blockchain, by imposing a cost for alteration that a miner must hope to recoup through rewards given for cooperation.

Hashcash is basically a way to publicly prove that energy was spent on solving an arbitrary solution, using a hashing algorithm. Hashing algorithms are cryptographic programs that take a set of data as an input and produce a one way *hash* signature version of that data as an output. In Hashcash a problem is designed where the target hash value is known but very difficult to derive, and very easy to verify

 In Bitcoin the difficulty of the Hashcash problem is varied over time depending on the recent history of solution times, targeting a ten minute solution on average.

## Creation of Hashcash

The Hashcash concept was first proposed by cryptographer Adam Back in 1997 as a part of his work providing an anonymous email service to be used to promote free speech. Back came up with the Hashcash concept as a way to help prevent abuse by giving it an easily verifiable cost.

Adam Back realized that the concept could be useful beyond his own service, and worked to promote the concept to be used for other email services to prevent spam, or for other situations where Sybil resistant rate limiting could be useful. Over time Hashcash became widely known as an innovative idea, and SpamAssassin, Hotmail, Outlook, and I2P all included versions of the concept in their software.

Hashcash was also seen by crypto-anarchists as having the potential to be used in a decentralized money application that was long proposed, by Wei Dai and others, but never realized. Hal Finney made Hashcash a key component of his proposed digital currency, in a process that was very close to what would eventually become Bitcoin.

## Hashing Algorithm

Hashcash as originally proposed used the SHA1 hashing algorithm, but many hashing algorithms are suitable for the concept. In Bitcoin's implement of Hashcash, Satoshi Nakamoto opted to use the newer SHA256 algorithm instead of SHA1. At that time SHA1 had been shown to have a small design flaw in which the difficulty of creating multiple identical results was underestimated by a large degree. Bitcoin actually uses two cycles of SHA256 hashing instead of the standard single hash, this is thought to be because that would have been a way to reduce the impact of the design flaw in SHA1, had it been selected.

Since the time that SHA256 was chosen as Bitcoin's hashing algorithm, a newer version of the algorithm called SHA3 has been designed to directly address the issue found in SHA1 and to be used as a comprehensive upgrade for SHA256. It's possible at some point Bitcoin would upgrade to SHA3, however the benefits from the upgrade would be minimal. Even SHA1 would still work for Bitcoin's purposes had it been selected. The difficulties involved in modifying the network consensus to support SHA3 and limited benefit means that SHA256 may never be replaced.

## ASIC Resistance 

After Bitcoin started to rise in value, it started to become understood that the most efficient way to produce the SHA256 hashes would be using equipment that was specially designed to hash very quickly and efficiently, called ASICs. Since a widely distributed hashing network is seen as desirable for Bitcoin and many existing miners resented the imminent arrival of a new much more efficient competitor, it was proposed that the Bitcoin hashing algorithm be modified to one that would prevent the formation of extremely expensive but vastly more powerful ASICs.

Many in the Bitcoin community turned to the popular *scrypt* hashing algorithm, which was designed to perform key stretching on passwords to prevent brute forcing. Unfortunately, key problems with this plan emerged. The scrypt algorithm is not designed to be fast, it is designed to be slow, meaning verification of the proof of work is also slow, unlike SHA which is very fast.

A major reason scrypt was chosen was due to the perception that ASICs could not be produced for algorithms with high memory requirements. But in actuality scrypt does not fully require its specified memory target, it's simply the most optimal solution. Because of this, an ASIC could be designed with low memory use that simply brute forces its way past the memory requirement. Eventually alternative coins were created to put these theories to the test. ASICs were in fact created for the scrypt proof of work, and the alternative concept of using scrypt failed to gain mass appeal.

Over time it became more well understood that no known algorithm can be constructed to be truly resistant to ASIC creation. Given that constraint, the prevailing wisdom is that an optimal end-game for Bitcoin hashing would be to commoditize ASICs as much as possible, in order to gain the desired distributed hashing network that is seen as the ideal.

## Hashing in Bitcoin

When performing a Hashcash challenge, all hashers may be essentially trying to find the same solution. To avoid all hashers starting at the same places, Bitcoin's hashing algorithm uses the reward Bitcoin address as a randomizer: every miner essentially starts mining at his own address which is a random number.

Bitcoin hashing also includes a counter to increment as hashes are attempted. This counter may be frequently reset as large numbers of hashes are tried, it resets against a random number called an *extraNonce* to create a new results space to search. The counter should also be reset after successfully finding a block.

Satoshi Nakamoto's own blocks are linked together because he did not reset his counter, allowing easy correlation. The counters are also reset to obscure the number of times the individual miner had to iterate to find the solution, to hide his hashing power.

