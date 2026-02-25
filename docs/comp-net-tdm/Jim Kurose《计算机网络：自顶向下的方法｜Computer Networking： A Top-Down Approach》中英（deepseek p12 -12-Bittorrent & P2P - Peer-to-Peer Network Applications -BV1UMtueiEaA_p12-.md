# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p12 -12-Bittorrent & P2P - Peer-to-Peer Network Applications -BV1UMtueiEaA_p12-

In this video we'll be talking about the principles of peer to peer applications and looking at a BiTrn as an example。

 let's get started。

![](img/12e349fc9f1a76b78b5ef813193923be_1.png)

Let's look at peer to peer applications and Bitorn。

The characteristic features of a peerto peer application is that they do not rely on an always on server listening for connections。

 instead， arbitrary end systems are able to communicate with each other directly in this model peers request service from other peers and provide service to other peers。

It is important for the sustainability of the peer to peer network that the service provided scales at least as well as the service requested。

There are two main challenges to the operations of peer to peerer networks。

One is that the peers may join or leave the network。

 so the service provided by a particular peer will come and go。The second is that over time。

 the peererce IP address is likely to change。The most common peer to peer application today is bitTrn so we'll look at that as an example in a few slides First let's look at a couple calculations to see the potential benefits of a peer to peer file transfer。



![](img/12e349fc9f1a76b78b5ef813193923be_3.png)

In the traditional model， the file originates at the server and it needs to be distributed to a number of clients。

The limiting factor here is the bandwidth available for the server to upload the file and for the clients to download the file。



![](img/12e349fc9f1a76b78b5ef813193923be_5.png)

For all of the clients to receive the file directly from the server。

 the server will have to upload end copies of the file。

 we can calculate the time required to accomplish this by dividing n times the file size by the upload bandwidth that the server is using。

We can also look at the download rates of the clients and determine if those will be the bottleneck。

Each client will only need to download the file one time。

 so the file size divided by the slowest download bandwidth will be the maximum time that it would take for any of the clients to download the file from the server。

 so the total time to distribute the file will either be the time it takes the server to upload all the copies or if longer。

 the time for the slowest client to download one copy this assumes that all the clients make the request at the same time。

So in terms of scalability， we see that this time to download will increase linearly with the number of clients。



![](img/12e349fc9f1a76b78b5ef813193923be_7.png)

Now let's look at the peer to peer scenario。The file still starts out in one place on the server。

The server has to upload at least one copy of the complete file。

Each client also needs to end up with their own copy of the file。So we know that as an aggregate。

 all the clients need n times F bits， but now in the peer to peer model。

 the upload bandwidth of all the clients will also contribute to the rate at which the file can be distributed。

 the whole file distribution process cannot be completed any faster than the server can upload the one copy。

Or any faster than the slowest client can download one copy。However， in the typical case。

 we have the numerator increasing linearly with n， but the denominator is also increasing as additional peers join the network because they'll contribute to uploading the file to additional peers。



![](img/12e349fc9f1a76b78b5ef813193923be_9.png)

So let's compare those on a plot。We see the linear growth of the time it takes for a server to distribute the file to end peers。

 and we also see that as more peers join the peerer to peerer network。

 the time added to transfer the file to each additional peers decreases。

 so the marginal increase gets lower and this performs much better than a linearly increasing distribution time。



![](img/12e349fc9f1a76b78b5ef813193923be_11.png)

So that's the principle how does it work in practice Let's take BiTn as an example as part of the BiTn protocol each file is divided into 256 kilobit chunks This allows the peers to begin sharing bits of the file more quickly as opposed to having to wait for entire file transfer operations to complete as soon as the first chunk is uploaded to one peerer that peer can begin sharing it while they're downloading another chunk。

There are a couple of key terms to keep in mind with bittt。

The torrent is the set of peers that are exchanging a particular file。

So a given peerer can participate in many different torrents at the same time。

 there is also a tracker， which is a server maintaining a list of which peers are participating in a particular torrent。

So from that explanation we can see that bitTorn is not a pure peer to peer protocol because it still hasn't always on server I eat the tracker and if the tracker goes away。

 the protocol will no longer work That being said there have been enhancements to bitTorn that allow it to work with a distributed tracker instead of a tracker centralized on one server。

So let's go through the process of what happens when a new peer wants to join the torrent。

Allast now wants to join the torrent that is already active。First。

 she has to contact the tracker to obtain the list of peers that are participating in this torrent；

 This means that the tracker must be available in a predictable place。

 because otherwise Alice won't be able to find it。

![](img/12e349fc9f1a76b78b5ef813193923be_13.png)

Once she has the list of peers， then Alice can start exchanging chunks。At first。

 Alice has no chunks to contribute， so she needs a way to get some chunks from the pis。

Once she has one or more chunks， then she can begin uploading those chunks while continuing to download more chunks。

The process of peerers coming and going from the torrent is known as churnern。

The more churn that happens in the network， the more challenging it is to deliver all the chunks to all the peers in a timely manner。

Once a Pi has the entire file， it might leave the torrent。

 which is generally considered selfish if it has not yet uploaded at least as many chunks as it has downloaded。

Remaining in the torrent after downloading all the chunks is known as seeing， I。e。

 providing an additional seed or copy of the entire file from which other peers can collect chunks。



![](img/12e349fc9f1a76b78b5ef813193923be_15.png)

As the process progresses， different peers will have different chunks of the file。

It is important that at any given time， all the trunks are still present in the torrent。

Periodically each peer will ask the neighbors that they're connected to for a list of chunks that they have Alice requests chunks that she doesn't already have from her peers。

Starting with the most rare， so for example， if there's only one copy of a particular chunk amongst all her peers。

 Alice would request that first。Once she has gotten a copy of it。

 then there's at least two copies of that chunkun amongst the same group of peers。

This helps preserve the torrent and prevent the case where the only copy of a particular chunk is on a pier that decides to leave the torrent。

 at which point none of the other peers would be able to finish downloading the torrent。

The peers are selective about which peers they send chunks of the file to。

 they prioritize the peers that are currently sending at the highest rate periodically。

 the peer will reevaluate which of their peers are the fastest。

This encourages peerce to upload rapidly if they want to be able to download chunks rapidly。

There' is another component to the process called Opistic Unchoook。

 whereby Alice selects a random pi and sends it one of the chunks that it's requesting。

This is the bootstrapping process by which peers that have no chunks can get started downloading the torrent。



![](img/12e349fc9f1a76b78b5ef813193923be_17.png)

Let's see an example of this tit for TAP process。Bob is asking for chunks。

 but he doesn't have any to upload， or maybe he just doesn't have any that Alice needs。

In either case， Alice randomly picks Bob and optimistically unchokes him。

 this means she begins sending him one of the chunks that he still needs。At this point。

 Bob recomputes his top four providers， and Alice is one of them。

 so Bob reseprocates by sending Alice a chunk。It turns out that Alice and Bob are well connected and so Bob is now one of Alice's top4 providers as well and they both benefit by getting chunks of the file faster This improves overall peerto-peer network efficiency by having peers that are well connected to one another exchange more chunks with each other that completes our brief overview of Peertopeer applications in the next video we will look at the topic of video streaming and content distribution networks See we hope you enjoyed this video if you found it to be useful the like button to be notified when more videos are posted for this class subscribe to our channel and click the bell。



![](img/12e349fc9f1a76b78b5ef813193923be_19.png)

![](img/12e349fc9f1a76b78b5ef813193923be_20.png)