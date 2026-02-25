# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p53 -53-How Cellular 4G_5G Networks Work - Wireless Networks -BV1UMtueiEaA_p53-

In this video we look at how cellular 4G and 5G networks work。Let's get started。



![](img/b3cab2e8417f6386d275e364be976eb5_1.png)

Welcome back to chapterer7 and this video we'll be looking at cellular data networks。

These have a number of similarities as well as significant differences from the WiF networks that we looked at in the last video。



![](img/b3cab2e8417f6386d275e364be976eb5_3.png)

As we're probably all aware， cellular networks are the dominant solution among mobile internet services at this time they outnumber fixed broadband devices by a factor of 5 to1。

And while we're all familiar with dead spots and running across areas of no service at some time。

 the vast majority of densely populated areas are covered by cellular broadband service。

The technologies involved are capable of hundreds of megabits per second of bandwidth。

Although the bandwidth observed in practice varies based on numerous factors。

 as with the internet protocols we've looked at， the mobile network protocols are also governed by a number of standards。



![](img/b3cab2e8417f6386d275e364be976eb5_5.png)

Within cellular networks we observe a number of similarities to the internet as a whole。

 though a given carrier will have a core network and an access network that are all part of the mobile cellular network。

This is in addition to being connected to the core of the internet。

There are many different cellular networks making up a network of networks whose customers can communicate with both voice and data services。

Internet data services running over the IP stack are now ubiquitous within the mobile network。

 and we can think of the mobile network as an access network that interconnects subscribers to the wired internet。

Where the mobile wireless networks differ is primarily at layer 2。

 which differs significantly from the 802。11 standards。

Part of this is to enable much greater levels of mobility than are anticipated for wireless lenss。

There is also much stronger notion of billing where a device's identity is tracked in order to build the associated charges back to the correct user。

 and because money is involved， authentication is also required to prevent unauthorized account usage。



![](img/b3cab2e8417f6386d275e364be976eb5_7.png)

So let's see how this looks from an architectural standpoint， the mobile devices。

 which are the hosts in general networking terms， are referred to as user equipment or UEs in the mobile network。

These connect to a base station just typically on a tower， and the UIs might be handled devices。

 laptops or embedded in vehicles， and in some cases even attached to nonmobile facilities like buildings。



![](img/b3cab2e8417f6386d275e364be976eb5_9.png)

These are organized into cells each with their own base station and the cells are connected back to the packet core the packet core is still part of the mobile wireless network in that it explicitly supports mobility amongst the cells and we'll see a bit more about that in a few slides。

Prior to 4G， the packet Co was divided into separate voice and data services。

 but with LTE these are converged and so all services are provided over an IP network in the core。

The UEs are identified by number stored on their SIM card known as the MCZ number。

This international mobile subscriber identity is intended to be unique worldwide。

And is a 64 bit number。Each base station manages its own cell。

 and the base stations also each have an identifier whereby UEs can identify transmissions from one base station versus another all the devices have to authenticate to the base station。

 which requires the base station to interact with elements in the packet core。

The base stationations also coordinate with each other in order to optimize load on the network and facilitate user mobility from one cell to another。



![](img/b3cab2e8417f6386d275e364be976eb5_11.png)

Mobile networks have a strong notion of what the home network is。

 so a subscriber pays their one provider but may roam to other provider' networks。

 and so in this architecture， the home network provides different services than the roaming networks。

The Home network maintains the Home Subr service or HSS for their own customers。

So this is what associates the MZ number with a user's identity。So their name， billing address， etc。

And this would also maintain information about what services the user has active subscriptions to。

We also have some routers， as you might expect with the packet Co。

 and some of these have specific functions， so there is a gateway to the internet known as the packet gateateway。

And we note here that this often provides NA services。

Almost all mobile networks make very heavy use of NA because they have so many devices that there are not enough IPV4 addresses to give each of them a unique public address。

And then we have the Ser gateway， which is the entry point to the packet core used by the base station。



![](img/b3cab2e8417f6386d275e364be976eb5_13.png)

Then we have the mobility management。So while the Home subscriber service manages relatively static data that might get updated by humans from time to time。

 we can think of the mobility management entity as managing the real time state of a device's connection。

 so this includes supporting the authentication of the device。

 keeping track of which cell a device is connected to for call routing。

And assisting in the handoff as the device moves from one cell to another。

It also sets up the tunneling that is used between the device and the packet gateway to get to the internet。



![](img/b3cab2e8417f6386d275e364be976eb5_15.png)

Just as in the rest of the internet， there is a distinction of mobile networks between the control plane and the data plane。

In this case， the data plane makes heavy use of tunneling protocols while the control plane worries about mobility security and authentication。

Because we have a device sending IP traffic， but we also have a core running an IP network。

 we end up using IP over IP tunnels。

![](img/b3cab2e8417f6386d275e364be976eb5_17.png)

The layer2 in this environment can be subdivided into several components。

 including the packet data convergence layer， the radio linknk layer。

 and the medium access control layer。The packetcaada convergence layer worries about things like compression and encryption of the user data。

 while the radiolink controller worries about reliably getting the frames transferred between the user equipment and the base station Lastly the medium access control as we've seen before。

 negotiates the use of radio transmission slots。Though we have a1hop radio access network between the user equipment and the base station。

 which is directly analogous to our 802。11 protocols。

 however in this environment we're performing both FDM and TDM functions。

 meaning that these radios are more technically advanced than 802。11 radios。

Within the shared wireless channel， each device is allocated two or more half millisecond time slots spread across 12 frequencies。

So the radio is constantly hopping between frequencies to send data on these half millisecond time slots。

If you remember back to the scheduling algorithms that we saw before。The most simple， of course。

 is first in first out， but in practice the operator may differentiate between classes of service and prioritize some types of data over others。



![](img/b3cab2e8417f6386d275e364be976eb5_19.png)

On the packet Co side of the network， we have the protocol stack required to enable the tunneling。

 so while our link technologies will be a traditional wired link with IP running over it。

We then see a UDP layer and a tunneling protocol layer。

 so whatever data we got from the user equipment。Which might be， for example。

 an HTTP over TCP over IP packet is now going to be encapsulated inside of this tunneling protocol。

The tunnel then gets back to the serving gateway。Which then decapsulates it but puts it in a new tunnel to get it to the packet gateway。

The benefit to this tunneling architecture is that the user equipment as it moves from place to place can retain its IP address because the subnet inside the tunnel is independent of the subnets over which the tunnel passes。



![](img/b3cab2e8417f6386d275e364be976eb5_21.png)

Now let's look at the process of associating with a base station。

Our user equipment shows up and it will probably hear radio packets from multiple base stations and will request to associate with the one with the strongest signal All the base stations are transmitting synchronization signals every 5 milliseconds。

If you recall， part of this link layer is TDM time division multiplexing。

 which requires tight synchronization between the clocks of all the devices using the channel The mobile device reads this sync signal including sync signals from multiple base stations and from this it learns the radio configurations that it should be using including the bandwidth of the channel。

 what carrier the base station belongs to and other configuration info as a last step the device selects a base station to connect to。

Although the things being equal， it would prefer to connect to the strongest signal， however。

 it may instead prefer to connect to the home carrier even if there's a stronger signal from a different carrier。

This is because the carriers typically make more money when they don't have to pay a third party to transport the data for their own user。

Note that this is just the association to the base station。

 but fully enabling the connection also requires authentication and the establishment of the data plane through the network core。



![](img/b3cab2e8417f6386d275e364be976eb5_23.png)

As we talked about with Wifi and Bluetooth。Power management is an important component of these protocols。

 so mobile devices also support the notion of sleep modes when it's in a light sleep mode。

 it will wake up every 100 milliseconds or so and check with a base station to see if there's frames that it needs to receive。

 but it can also go into a deep sleep mode where it doesn't accept traffic for many seconds at a time。



![](img/b3cab2e8417f6386d275e364be976eb5_25.png)

As we mentioned， the mobile wireless network is a collection of different providers。

 and so these providers peer with one another very similarly to the way the internet's ISPs do。

 using IP interconnects at Internet exchange points。Again。

 this is different from how it was handled in versions before 4G。

 where there were dedicated interconnections for voice services。

The MZ number on the SIM card is a globally unique identifier。

 so no matter what network that device connects to。

 they can look up the home network for that particular MZ number。

The visited mobile Carrier Network will then check back with the Home network to find out what services they will be able to build the home network for in support of the subscriber。



![](img/b3cab2e8417f6386d275e364be976eb5_27.png)

Today we're beginning to see 5G deployments。So let's see a little bit about what's different。

There's a significant goal here in terms of increasing bandwidth however。

 we should really note that 4G has never widely supplied the bandwidths it's capable of to users。

Even though 4G is capable of hundreds of megabits per second。

The user experience is usually in the single digits or tens of megabits per second。

So the 4G protocols were not a limiting factor for offering bandwidth to users。However。

 the real motivating factor between going to 5G is the ability to support many more mobile devices in a dense area。

Meaning the support for multiple simultaneous users is significantly improved。With five G there'。

 also two new frequency bands that have been approved。

And we note that these at least on the upper end， are much higher frequencies than were typically used in the past。

the implication here is that they will not propagate as far。

 and so cells will be geographically smaller in 5G however。

 this is a benefit in very densely populated areas because it allows for greater frequency reuse。

These smaller cells may be referred to as pico cellsll with the diameter in the tens or hundreds of meters。

And the implication here is that service providers will need to deploy large numbers of new cells。

Which is a significant departure from the old model of having relatively few cells based on large towers。



![](img/b3cab2e8417f6386d275e364be976eb5_29.png)

That wraps up a discussion of cellular 4G and 5G networks。We hope that was useful。

 and in the next video we'll move on to seeing more details ofmobilia management。

 both as it applies to cellular networks and to mobile IP networks。



![](img/b3cab2e8417f6386d275e364be976eb5_31.png)

See you then。We hope you enjoyed this video， if you found it to be useful please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。

