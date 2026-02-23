# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p39 -39-Software Defined Networks & OpenFlow - IP Network Layer -BV1UMtueiEaA_p39-

In this video we're looking at the software defined networking control plane。

 including SDN controllers and the Openflowlow Pro Let's get started。



![](img/523b51647ee825cfd06972c0808d7453_1.png)

Now we'll begin looking at the control plane of software defined networks。



![](img/523b51647ee825cfd06972c0808d7453_3.png)

As we've been saying in previous videos， the internet control plane has generally been implemented using a distributed per router approach。

 meaning that each router contains elements that pertain both to the control plane and the data plane。

 and these router control planes communicate with one another using the standardized protocols that we've seen so far such as OSPF and BGP。

However， this meant that routers were limited to a fairly specific set of operations。

 primarily that of destinationbased forwarding， and when other functions were needed。

 those were implemented in some sort of middle box that was not exactly a router and could look at other layers of the protocol and make different decisions。

So there's been quite a bit of interest in the last 15 years or so in unifying the network control plane。

 rather than having two distinct categories of devices that are either routers or something else。

 that there would be one type of device that could unify many of these functions and provide the majority of the services that are desired from the network layer。

And this is how we arrived at the software Def networking architecture where we have SDN switches that provide generalized forwarding capabilities。



![](img/523b51647ee825cfd06972c0808d7453_5.png)

As a reminder in the traditional routers， when the packetact arrives with a certain destination address in its header。

The router will look in its forwarding table and perform destination based forwarding。Meanwhile。

 in the control plane that's implemented in each of those routers。

 the routing algorithms will talk amongst the routers and will inform these forwarding tables such that they are able to construct consistent paths through the network to all of the needed destinations。

 and so we divide the control plane in the data plane within each of these routing devices This is in contrast to the SDN architecture which can look at various values in the packetheader but separates the logical data plane functionality from the control plane。

 with a control plane implemented in remote SDN controllers。

 these controllers construct the flow tables and send those out to the SDN switches。



![](img/523b51647ee825cfd06972c0808d7453_7.png)

In this model， the control plane and the data plane functionalities are separated and implemented in distinct devices。

Having looked at the traditional router control plane architecture in previous videos。

 we'll now dive into the SDN architecture in more detail。



![](img/523b51647ee825cfd06972c0808d7453_9.png)

First we'll look at the motivation for why we would want to make this shift away from what has worked for the internet for so long。

One of the primary motivators is to make network management easier， not out of laziness。

 but primarily to avoid misconfiguration。There have been a number of surveys of network operators which indicate that misconfiguration is the number one cause of network outages across the internet。

So if we can decrease the likelihood that these misconfigurationations will occur。

 we can go a long way to increasing the reliability of the internet。In addition。

 we can have increased flexibility for doing traffic management。

So perhaps differentiating between classes of traffic that have different requirements in terms of latency or bandwidth。



![](img/523b51647ee825cfd06972c0808d7453_11.png)

As we've noted with some of the distributed writingut protocols。

 designing distributed algorithms is difficult， and there are certain inherent limitations both in terms of performance and in terms of the complexity that can be realistically achieved。

Centralized programming Authoring tables alleviate some of this and makes it easier to do complex routing operations while still having assurance that connectivity will not be compromised。

Another motivation here is opening up the control plane to innovation by developing open source controller software。



![](img/523b51647ee825cfd06972c0808d7453_13.png)

There are definitely some parallels here between the move from traditional routing to software defined networks。

 with the move from centralized mainframes to PCs distributed in everyone's home。

So mainframes were a monolith that consisted of hardware and operating system and application that were all part of the one ecosystem that only worked with each other。

Whereas when PCs were developed， the hardware interface was opened up such that multiple operating systems could interoperate with it。

And a plethora of applications could be developed on top of these operating systems。

And this led to an explosion of innovation and development of new applications that had never been envisioned in the mainframe environment。

So while it's yet to be realized， the hope is that the move to software defined networks will provide similar benefits。



![](img/523b51647ee825cfd06972c0808d7453_15.png)

Here we'll look at an example of a fairly straightforward traffic engineering task that is difficult to accomplish using traditional routing protocol。

We see that the flow of traffic from U to Z is following the least cost path through the network as we would expect。

However， we have an operator that for traffic engineering reasons。

 needs to change the path of this traffic。With traditional routing。

 we need to redefine the link weights so that the new path will be the lower cost path between these two endpoints。

 however there are clearly many other flows to the network and manipulating the link weights will affect all of those as well。

 not just the one that we're trying to control。Now what if instead of just moving that traffic flow。

 the operator actually needs to split it to divide the load over two different paths。

 this becomes yet more challenging and would require additional configuration beyond what a typical routtting protocol could achieve so typically a load balancing configuration would be constructed outside of the routtting protocol because that service is not supported directly within the routtting protocols。

Here's another example where we could have two flows in play and for whatever reason we need to separate these flows between W and Z Again this is not something that we can achieve with destination based forwarding。

 however with generalized forwarding we can look at other fields and so we could achieve such an outcome。



![](img/523b51647ee825cfd06972c0808d7453_17.png)

Now back to our SDN architecture， you'll note that on top of the controller we've introduced some bubbles such as routing access control and load balancing。

 and these represent the logical functionalities that we need the controller to provide。

Within the controller there's different architectures。

 but one could think of these as applications running on top of the controller that each contribute to the body of information that will be used to build the flow tables。

Since Openflowlow is the dominant SDN technology， we'll generally use the Openflowlow terminology to describe the different parts of this architecture。

 so we have our flow tables in the routers data plane。

Your separation between the control plane and data plane， our control plane functionality。

 and ro on top of that our control plan applications。

 which can both get input from the network in order to make context where decisions and define forwarding rules for the network。



![](img/523b51647ee825cfd06972c0808d7453_19.png)

To flesh out some details， we have fast， relatively simple commodity switches that can run at the data plane。

Because we have a standardized interface between the data plane and the control plane。

 we can mix and match vendor's devices and not be locked into using the same vendor for both the control plane and the data plane。

The control plane supervises the computation of the forwarding table and the installation of those forwarding tables onto the switches。

And it does so using the API that defines what part of the switch operations are controllable and which are not。



![](img/523b51647ee825cfd06972c0808d7453_21.png)

Then we have the SDN controller， which is an application running on a server。

But we can also think of this as the operating system that is managing the resources of the whole network。

This controller must keep track of various state across the network and has two API interfaces。

 one with which to interact with the SDN switches， and the other which allows it to interact with the network control applications。

While it varies from one SDN controller to another， certainly in the ideal case。

 the SDN controller is distributed acrossing multiple servers in order to achieve scalability and survivability。

Then the top layer of this architecture is the network control applications Of course to know that routing is one of the essential portions of this since we have taken away the old control plane that implemented routing on the devices themselves。

 but we may also incorporate features typically associated with middlebox。

 such as firewalls or traffic engineering。These applications are able to interact with the controller through the API provided such that they both can observe the state of the network。

Respond to particular events。And update rules and flow tables。Again。

 depending on the particular STN controller in question。

This API may be an open standard and so third parties can provide network control applications or and users may be able to configure their own。



![](img/523b51647ee825cfd06972c0808d7453_23.png)

Let's break down the SDN controller in a bit more detail。

There are certainly some details here that depend on the specific controller in question。

 but in general there will be some modularity and a set of concerns that the controller must deal with。

The controller will have components dedicated to communicating with the switch devices。

 for example using the Openflowlow protocol and maybe the SNMP protocol in addition。

 the simple network management protocol。The controller will also need to keep track of the state of the network these are things like what physical links are connected and what switches are registered to this controller。

In addition， the controller should know what flow tables have been published to the switches and also be reading back statistics from these flow tables about the device usage and the traffic flows across the network。

Then we have the API Li can interface with the network control applications。

And these can be relatively simple or provide a richer view of the network state Exles of this might be a network graph abstraction。

 a restful API， and some notion of policy intent。

![](img/523b51647ee825cfd06972c0808d7453_25.png)

So let's look at the Openflow protocol， This is what's used over the connections between the switches and the controller。

It operates over TCP and in more recent versions， supports encryption。

We can break down the Openflow messages into three categories。

 which include the controller to switch messages。Such as deploying a new flow table rule。

 asynchronous messages where the switch is volunteering some information to the controller。

And symmetric messages， for example， where the controller is querying information from the switch。

 and this is distinct from the Openflowlow API which is used to specify the generalized forwarding actions that we talked about when looking at the SDN data plane。



![](img/523b51647ee825cfd06972c0808d7453_27.png)

Here are some of the key controller to switch messages。

One allows the controller to ask the switch what features it supports。For example。

 a more basic switch may be able to perform the forwarding required by OpenFlow。

 but not able to do a more advanced feature such as rate limiting a particular link。

The controller can also send the switch configuration message。

 which either requests a state of or sets the state of a particular setting。

And then we have the flow table manipulation via modified state messages。

A particularly interesting one is the packet out message。

 where the controller can encapsulate a packet and send it to the switch and tell the switch to send that packet out a particular port。



![](img/523b51647ee825cfd06972c0808d7453_29.png)

Then on the switch to controller side we have messages such as packet In。

 this is where the switch has received a packet that is not sure what to do with。

 and encapsulates it and sends it over to the controller for the controller to make a decision about。

We have the flow removed message， this usually means that a particular flow roll has timed out and so it's been removed from the flow table at the switch。

And the switch can inform the controller of a change in state own of it's ports。

One can envision this information being used by the controller to do something along the lines of Link state routing。

Of course， the operators of the network don't send or receive these messages directly。

 but they rely on the abstractions provided by the controller to generate and interpret the messages。



![](img/523b51647ee825cfd06972c0808d7453_31.png)

SoLet's follow an example interaction to the architecture In this case we have a link failure in the network。

 the link between S1 and S2 is out， so S1 notifies the controller of the change in its port status and so the links state info at the controller is updated。

 which propagates up to the network graph abstraction and that can be used by Dyster's Li state routing algorithm running as an application to compute new flow ruless for S1。



![](img/523b51647ee825cfd06972c0808d7453_33.png)

These are sent to the flow table state maintenance in the controller and then propag it out to the routers。



![](img/523b51647ee825cfd06972c0808d7453_35.png)

Just like there are different operating systems we can run on PCs。

 there are different vendors providing SDN controller software。

One of these is the Open daylight controller this provides basic network functionality as well as some enhanced services。

It has a service abstracttraction layer which interacts with the messaging to the switches。

 using some of the methods that we've talked about and exposes a restful API to the applications that can be built on top of this controller。



![](img/523b51647ee825cfd06972c0808d7453_37.png)

Another available controller is the Onus controller This is based on a distributed core that keeps track of the state of the network includes a number of abstractions for the links and devices in the network as well as supporting the open communication with those devices。



![](img/523b51647ee825cfd06972c0808d7453_39.png)

And supports an intent framework with the goal of allowing the network control application to provide a high level specification of what is desired in a service。

Rather than having to supply the details of how that service should be enabled。

There is also considerable emphasis placed on distributing the core to improve reliability， however。

 software defined networks certainly aren't settled science。



![](img/523b51647ee825cfd06972c0808d7453_41.png)

There is still much to be done， especially along the lines of preventing the control plane from becoming a single point of failure in the network。

Certainly one would envision that attackers would want to target these controllers to either gain control of the network or cause service outages。

While security certainly wasn't baked in from day one because OpenFloid didn't even support encryption to start with。

It has come a long way in that respect， and so now communication between the switches and the controllers has been secured。

 assuming that operators have updated to the more recent versions of the OpenFlow protocol。However。

 this is still fundamentally IP based。And so it is still a challenge to provide guarantees about service performance。

It's also important to realize that this is primarily an alternative to IntraA traditional routing。

And has not directly addressed questions of whether or how this would replace InterA routing M BGP。

 so the benefits of SDN are difficult to translate across AS boundaries。However。

 within individuals providers networks， SDDNs are becoming more and more widely deployed。

 especially in the mobile provider space。

![](img/523b51647ee825cfd06972c0808d7453_43.png)

We've been talking about SDNs being able to compute routing tables centrally and the advantages that might offer over distributed routing。

 but that's just one example， one could also envision using SDNs to provide congestion control rather than relying on the endpoints to make guesses about how to provide congestion control。

But fundamentally， it's not clear at this point how future SDN services will evolve and how they will interact with established network protocols。



![](img/523b51647ee825cfd06972c0808d7453_45.png)

That wraps up our discussion of the SDN control plane。In the next video。

 we'll be looking at internet control messaging and network management， See you then。



![](img/523b51647ee825cfd06972c0808d7453_47.png)

We hope you enjoyed this video， if you found it to be useful。

 please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。

