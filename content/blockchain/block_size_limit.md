# Block Size Limit

Bitcoins that move on the Blockchain follow a process where the Bitcoin movement is documented and signed in a *transaction*. A transaction is broadcast to the network to sit and wait in an unconfirmed state until a miner creates a block in the Blockchain that includes it. The rules of the Blockchain are designed in such a way where a block cannot exceed one megabyte, so a block can only include transactions up to that limit.

The block size limit is not an optional suggestion, any miner attempting to exceed the limit will have his blocks automatically disregarded by the other nodes in the network, unless they have altered their standard limit rule. 

## Limitations Imposed

The block size limit has a greater overall implication for the Blockchain system of syncing transaction data: there is a fundamental limit to the movement of funds within a given space of time. This is often referred to as transactions per second that the Blockchain can include, or *TPS*.

Because the limit creates a scarce resource, the limit implies that increased demand for space in a block will result in an increased price attached to every transaction to justify its inclusion.

## Preventing Abuse

The reasoning behind why having a limit might be beneficial to the system revolves around the network cost structure and goals of Bitcoin.

At a very simple level, transactions are simply messages or arbitrary data, not just fund transfers. At that level, there is some demand for using this data in means that are out of scope of the system, such as storing photos or videos, or sending messages to friends. Because the miners prioritize transactions based on fees, it is theorized that the use-cases of storing arbitrary data or sending messages will be curtailed as they pick more economical alternatives.

Another scarce resource on the peer to peer network is the supply of processing and networking power to sync transactions. An attacker might attack the network by sending large numbers of transactions all at once, in a bid to deny service to the network users by increasing their syncing costs. 

The block space limit does not prevent this attack directly, but the presence of the limit means that the attack cannot leave permanent damage beyond a limit, and the limit's indirect encouragement of meaningful fees improves their use as a signaling mechanism to allow the network and individual nodes to intelligently ignore or de-prioritize traffic in a way that makes a disruptive attack monetarily more expensive to execute.

While having meaningful fees is beneficial in a denial of service attack to determine the most critical transactions to process, a smaller block size also acts as an amplifier for the attack at low fees levels. In a scenario where the attacker has the intent to keep blocks full and deny service to very low fee transactions, this attack scenario is helped instead of hindered by the presence of a block limit, due to the aggregate cost of the cheaper transaction space being lower.

## Benefits to a Transaction Space Supply Limitation

The risk analysis that a person makes when accepting a Bitcoin transaction is related to the amount of energy or money used to solve the proof of work: more proof of work performed, lesser risk that a double spend will be performed due to the cost of performing one.

In the design of Bitcoin, after many many years, the block coin subsidy aspect of the system is designed to disappear. Although the system may change in unpredictable ways from now until that time, the only clear and commonly understood reward for mining a block absent the subsidy will be the transaction fees. Since the security that the proof of work mechanism is directly related to the total rewards miners receive for hashing, absent a block reward only the transaction fee monies provide for this necessary security component in a known, permanent way.

An unlimited supply of block space could potentially harm the utility of Bitcoin by creating a market where supply outstripped demand to such a high degree that the price of space in the blockchain was very low, giving miners had a very poor prospect of profiting from their production of blocks, making for a low energy burn proof of work, meaning a weak security guarantee. 

## Adjusting the Block Limit through Hard Fork

The rules surrounding the block limit are very strict in Bitcoin nodes, but ultimately the rules are expressed in software, and thus potentially open to change. If a change did happen, it could potentially create two isolated networks. This could cause confusion, and reduce the benefits of Bitcoin's network effect.

The best case scenario for a block limit adjustment would be to make an adjustment that was obvious to everyone based on the facts at hand. This would minimize the confusion and possibility of multiple separate networks.

## Improving Block Broadcasting Time

When a miner wins a block, there is a small possibility that another miner wins a block as well at about the same time. This is a potentially disruptive situation, and it represents a loss to mining efficiency as the system needs to discard one block and choose the other as the canonical block. The situation can be exacerbated through size based slowdowns in block broadcasting: in broad strokes smaller blocks improve the network's hashing efficiency by making the new block broadcasting process faster.

To reduce the impact of the problem of increased block sizes reducing network security and even discouraging miners from including transactions, software has been developed to make the block broadcasting happen as quickly as possible. This software does not remove the block size as a variable from the equation, it simply improves the efficiency of the broadcasting to reduce the overall impact of a larger block.

## Promoting Miner Decentralization

Another impact of efforts to prevent increased block sizes from impacting broadcasting efficiency is that it also serves to level the playing field so that miners with better bandwidth do not get an advantage and the scope of mining competition is as limited as possible to the hashing proof of work design.

Keeping the mining playing field level is important for the durability of the network because a more level playing field means it is easier for new players to enter and for the overall field of play to have more participants. 

Mining in Bitcoin also has another centralizing problem, which derives from the issue that individual miners can proxy their individual participation in the system to other miners, and realize a benefit for that action. Mining moved to a model of hashing and mining pools, with many miners becoming simply hash workers who proxy their system sovereignty to a mining pool operator. To address this threat to system durability where only a few number of mining pool operators create a weak point of attack due to their proxied power, more advanced forms of proxying were created in which the hasher maintained a no-trust relationship with the mining pool they proxy their hashing power to. However in order to utilize these forms of proxying, the hasher must bear the cost of a full node, a cost that is only limited by the block limit.

Ultimately, there is a firewall against the block size from causing efficiency and miner centralization problems, and that is the block size limit. Keeping this limit low is helpful in designing the overall system because it serves as a safety net for efficiency improvements suffering from some problem. In this way, efficiency improvements can be solidified behind the wall of the block size limit, and when the improvements are proved solid, the wall can in theory be pushed further out.

## Benefits to Node Decentralization

The design of the Blockchain system is one in which the transactions are broadcast to all participants. As the number of participants increase, so does the number of messages between participants, full nodes are not simply processing the messages between themselves, but also all the messages in the entire network. This multiplying effect is known in computer science as an O(n^2) problem, and it means that increases in Blockchain operational membership have an exponentially increasing impact on the system.

Although computing resources are generally understood to themselves be on an exponential path to becoming cheaper and faster, there is still a substantial risk that the path of computing resources does not keep pace with the path of Blockchain membership growth. If computing resource advancements advance more slowly than the membership in the Blockchain system increases, the total system cost will bear the difference in cost, which could easily be exponentially increasing.

The block limit puts a firewall on this problem at both a systemic level and at an individual level. Simply put, there is an upper limit to the costs that an individual node operator must bear, and that is governed by the block limit. This means no matter how much the Blockchain grows, as long as the limit is in place the upper cost of being a member of the peer to peer network remains fixed and the network cost remains linearly related to the number of participants instead of being exponentially related.

The cost to run a node being limited is important to decentralization, or in other words, the durability of the network. A prohibitively expensive cost to participate in the peer to peer network could push many users in the direction of declining or being unable to pay that cost, resulting in a lower number of members in the network. Lower membership numbers in the network can make the cost to attack those members cheaper, and thus increasingly possible. 

If the network is successfully attacked, or even under threat of successful attack, this has a negative consequence on the utility of Bitcoin for making transactions and being a safe store of value.

## Promoting Privacy

Full nodes being affordable to run is an important way to maximize users' financial privacy: full nodes are the most private way to use Bitcoin because they don't leak private financial data to untrusted third parties like other wallet mechanisms do.

In many mechanisms of using Bitcoin that do not bear the cost of syncing the Blockchain, the cost of running a full node is offloaded to a third party who aggregates that information and cost. Information about user finances is leaked when the information is requested, reducing user privacy.

Not only is user privacy an important feature for Bitcoin to a user, privacy also is valuable for Bitcoin's overall use as a currency: a fundamental property of a currency is that it is fungible, meaning that one unit is interchangeable with another unit. Whenever privacy is harmed, this also means that potentially some Bitcoin units have a different value than other Bitcoin units. In limited amounts, this privacy issue does not carry a large negative impact, but the less overall privacy the system presents, the less fungible and therefore useful as a currency Bitcoin becomes.

