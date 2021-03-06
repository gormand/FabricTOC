# A Blockchain network

## Think: Network, Identity and Permission

Hyperledger Fabric is a technology designed to address the diverse needs of the multiple organizations who collaborate in a blockchain network. Because of the many requirements that arise in these networks, **Hyperledger Fabric has a rich set of concepts** that you may initially find overwhelming! Don't worry though -- the principles that underly these concepts are easy to understand if you group them into three categories: **Network**, **Identity** and **Permission**.

| ![NetworkElements](./Network.diagram.1.png) |
| :---: |
| Three major concept groups in Hyperledger Fabric: Network, Identity and Permission |

Let's help you understand these categories by introducing some of the key concepts in each one. You don't need to understand every new idea -- but do try to get a feeling for the categories and why they are important.  If there's a term you come across that you'd like to know more about, then check out the [glossary](../).

## Network

Think of the concepts in this category as the fundamental **building blocks** of a blockchain network. **Cooperating organizations** form the blockchain network from these fundamental building blocks in order to **provide services** for **service consumers**. In addition to the organizations who formed the network, there will be a much larger set of participants who consume network services.

|![NetworkResources](./Network.diagram.2.png)|
| :---: |
| Some of the building blocks of a Hyperledger Fabric blockchain network. You'll understand the the nature of these relationships as you read more detailed information.|

You'll learn how a **network** can be partitioned into **channels** that enable private communications between the different members of a **consortium**. Moreover, within a channel, you'll see that **ledgers** and **smart contracts** are hosted on **peers** which endorse and validate transactions that are sequenced and distributed by **orderers**.

You'll discover more about these ideas as you read the [Concepts](./KeyConcepts.md) section and you'll solidify that learning with the real-world [DRIVENET example](../HowOrganized/DriveNetSample.md). For now, just think of these resources as the most fundamental elements which form the network.

## Identity

**Everything** and everyone that consumes services of a Hyperledger Fabric network **requires an identity**. For example you'll see that **users**, **administrators**, **applications**, **Certificate Authorities** and **organizations** all have to identify themselves whenever they interact with the network. Hyperledger Fabric has a general term for the things that have an identity -- a principal. **Principals are the main consumers of a blockchain network**.

| ![NetworkPrincipals2](./Network.diagram.4.png) |
| :---: |
| The principals in a Hyperledger Fabric blockchain. The consumers of a blockchain network are called principals, and each one has an identity. Notice that the external consumers of the network - organizations, users, administrators, applications have an identity. Notice also that some of the building blocks of a Hyperledger Fabric can also be principals -- they also have an identity. |

You'll see that sometimes **network resources** -- those fundamental building blocks you saw previously -- **also have an identity**. That's because one part of the network can sometimes consume services from a different part of the network. For example, peers and orderers use channel services to communicate with applications. It's this kind of relationship which makes it helpful for network resources to be principals with identity.

You'll discover why identities and principals are important in a moment, and later on, you'll start to understand the importance of a **public key infrastructure** (PKI) to **establish trusted identities** for the principals in the network. But for now, just remember that there are lots of identities associated with a network.

## Permission

**Permission is the final piece of the Hyperledger Fabric puzzle**, and it's the concept that **makes Hyperledger Fabric unique** among blockchains.   

**Permissions** are defined in configuration policies which **control the rights of different principals** over different resources. For example, applications may have permission to read from a ledger, but not to write to it. Similarly, administrators may have permission to change the organizations participating in a channel but not the organizations that are defined in a consortium.

As you can see, permissions are associative -- they require both network resources and identities to exist before they can be defined. That's because they define the **relationship** between principals and resources and only make sense once both these elements exist (in the same was as the rules for driving only make sense if roads and cars already exist).

|![NetworkChannelPermissions](./Network.diagram.5.png)
| :---: |
| Examples of network and channel permissions. There's a network policy which defines how three different principals can control the organizations in a consortium. There's also a channel policy which determines how three different principals can access the channel, and resources connected to it.|

There are two types of permissions policy that can be defined in Hyperledger Fabric - **network permissions** and **channel permissions**.  

* **Network permissions** relate to those resources that operate across the whole network. For example, a network permission might control which organization can define the members of a network consortium.

* **Channel Permissions** relate to those resources that relate to an individual channel rather than the whole network. For example, a channel permission might define which applications can read and write to the channel's ledger.

Hyperledger Fabric makes **extensive use of permissions** to support **networks with different constitutions**. For example, a network can be defined where every organization has equal permissions over network resources. At the other extreme, a network can be set up where a single organization has overall control. The idea of a network constitution is important, as it reflects and supports the balance of control between the different organizations in a blockchain network.

Most powerfully, policies may also define the rights to **modify the current policy** -- to support the fact that organizations may adapt and evolve their relationships with each other over time. For example, a network which was initially configured with three organizations -- of which two have operational control -- could be modified by either of the these two organizations to grant the third organization equal rights.

While this provides the greatest degree of flexibility to the founders and administrators of a Hyperledger Fabric network, it means that the permissions policy in the network must be defined very carefully.

## That's it!

That was easy, wasn't it? You can summarize Hyperledger Fabric as a technology which helps users build a blockchain network, which is consumed by principals with identities, with agreed and evolving rights over the different types of resources that make up the network.

And if you think about it for a little while, any computer system can be described in this way -- a set of resources, principals, and permissions. The thing you now need to do is understand the concepts in more detail, and how they interact with each other!

[Next:Consortia](./Consortia.md)
