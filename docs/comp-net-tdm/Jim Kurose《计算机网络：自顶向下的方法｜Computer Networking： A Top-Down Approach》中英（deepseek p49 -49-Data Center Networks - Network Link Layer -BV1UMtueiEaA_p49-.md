# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p49 -49-Data Center Networks - Network Link Layer -BV1UMtueiEaA_p49-

In this video， we're looking at data center networking。Let's get started。



![](img/c283e4b26832ddc577ee8ebe8d1d178f_1.png)

![](img/c283e4b26832ddc577ee8ebe8d1d178f_2.png)

Now we'll look at networking in the data center， and specifically when we talk about data center networks。

 we're talking about many thousands of servers usually hosted as compactly as possible and network together。

These are used by the major cloud providers， content providers， social networks。

 and e-commerce for the most recognizable examples。

But also used in high performance computing centers and anywhere else with significant computing requirements。

The reason we talk about these separately is not because the technology is really different。

 but because there is unique challenges when operating at these scales。

While one of these data centers might serve a particular enterprise。

 that enterprise will almost certainly have multiple applications running within the data center。

 and each of those serves massive numbers of clients。

Also at these scales with commodity hardware there is always something breaking and so the architecture needs to be designed in such a way that it will continue to function as usual。

 even with some components in a failed state。The entire system must be designed to avoid bottlenecks。

 whether it's bottlenecks and data processing bottlenecks in terms of networktre congestion。

 bottlenecks in terms of latency， or even bottlenecks in terms of the availability of power and cooling。



![](img/c283e4b26832ddc577ee8ebe8d1d178f_4.png)

Of course we're not going to address all of these concerns。

 but we do want to take a little time to talk about the considerations that affect networking。

So in general， we'll consider a data center to be filled with racks of servers。

 a typical rack would host about 40 servers。And at the top of each track will be a switch that provides networking to those servers。

For redundancy， it is also typical to have two top of rack switches with each server connected to both switches。

Multiple racks then are aggregated together and connected to a tier 2 switch。

Because we're also aggregating data across the multiple racks。

 the links between the tier 2 and the top of rack switches will typically be higher bandwidth than the links between the top of rack switches and the individual servers。

Across the data center we'll have many of these rack clusters aggregated together in Tier 2 switches。

The tier 2 switches are then connected to tier 1 switches。

 and the goal of this interconnection is not further aggregation。

 but instead to provide a flexible switched backbone across which there are many paths between any two racks。

 or between any rack and a particular border router。

This architecture will vary somewhat depending on whether the client accessing the application is inside the data center or outside the data center。

For typical customer facing applications， the clients will be outside the data center and served through these border routers。



![](img/c283e4b26832ddc577ee8ebe8d1d178f_6.png)

Facebook is a particular example of this sort of data center Sw network architecture。

 where conceptually they have the top of rack switches each connected to many different fabric switches。

 which in turn are interconnected to many different spine switches。



![](img/c283e4b26832ddc577ee8ebe8d1d178f_8.png)

If we go back to our simplified version of this diagram。

 we can see how this allows us to have multiple disjoint paths between any two points in the network。

 which may either allow us to aggregate bandwidth over those paths for increased throughput or allow us to tolerate faults in the network if a particular port or switch were to fail。

Now in our recent discussion of Ethernet， we did not talk about what would happen if a particular Mac address was reachable through two different interfaces on a switch。

 and in fact， the basic self-learning behavior of Ethernet switches does not handle this scenario and if it were to happen that would cause a loop resulting in a broadcast storm。

So this sort of architecture cannot be deployed based on self- learningning ethernet switches alone。

 instead it requires a dedicated controller which will configure these paths through the network。

 likely using some variant of software defined networking as we saw when discussing OpenFlow。



![](img/c283e4b26832ddc577ee8ebe8d1d178f_10.png)

In this example， we also have a dedicated application load balancer。

 which is the client facing server that handles incoming requests and farms those out to the servers in the data center。

So the request comes in， it's sent to a server or a group of server to be answered。

Those servers may talk to each other， but the answer will come back to the application load balancer。

 which in turn will send it out to the client when we talk about client requests。

 we might be talking about something like loading a webp page so for example。

 when you type in a query to a search engine and hit Enter。

 it goes off to this application load balancer which has to talk to a bunch of servers and get the answer back before the web page can load。

And so the time budget for all of this to happen is usually on the order of tens of milliseconds。

 and that's why any bottleneck in terms of congestion or latency will significantly degrade the performance of such an application。



![](img/c283e4b26832ddc577ee8ebe8d1d178f_12.png)

We've seen a number of protocol innovations come about because of the demands of data center networks。

Such things include remote DMA， so that's direct memory access over Ethernet。

Others that we've talked about include explicit congestion notification。

 which while it's difficult to use across the public internet。

 is widely used within data center networks， remember ECN allows us to manage congestion without having to f use and drop packets。

 so very important when we're trying to minimize latency。

There have also been experiments with H by hop congestion control again because it can be performed much faster than waiting for the end to end signaling to happen that's required for TCB congestion control。

 and in general we've seen software deployed networks be adopted the most rapidly within data center type networks。

We've also seen lots of innovation in management to determine how best to schedule applications or how to assign tasks to available compute resources in such a way to minimize the network latency between those resources。



![](img/c283e4b26832ddc577ee8ebe8d1d178f_14.png)

That wraps up her overview of data center networking。

In the next video we'll be looking at a day in the life of a web request which ties together all of the network layers that we've looked at so far to see all the steps that must happen between a client requesting a web page and getting the response back such that it can display that page。



![](img/c283e4b26832ddc577ee8ebe8d1d178f_16.png)

See you then。We hope you enjoyed this video， if you found it to be useful。

 please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。

