# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p51 -51-Wireless & Mobile Link Challenges - Wireless Networks -BV1UMtueiEaA_p51-

In this video we're beginning chapter 7 of the book where we look at challenges specific to wireless networks and the technologies that are used to address them。

 let's get started。

![](img/77a714a56455d106638e41f0c0922a50_1.png)

We've now reached chapter 7 of Kos and Ross the top down approach。As before。

 we're using the slides supplied by the authors to accompany the book。

We've completed the first six chapters where we worked our way down from the application layer all the way to the link layer。

And now we begin looking at approaches that are specific to the wireless environment。



![](img/77a714a56455d106638e41f0c0922a50_3.png)

Let's set the stage a little bit before diving into the details of wireless and mobile networks。

At this point in time， there are 10 times as many mobile phone subscribers as Landline phone subscribers and five times as many mobile wirered internet connected devices as there are fixed broadband subscribers。

In addition， within 4G and 5G networks there has been a shift converting the network core from a circuit based architecture to an IP based architecture。

The shift to wireless devices is clearly driven by demand and convenience， however。

 brings with it some high levelvel challenges which translate into numerous technical challenges within the network stack One of those high levelvel challenges is the nature of wireless channels。

 so just maintaining communication over a wireless link。

 which is far more difficult than maintaining communication over a wiredlink。

The untethered nature of wireless also lends itself to mobility。

 but that brings with it a host of additional challenges。

Keep in mind that the IP Pro stack was designed exclusively for wired networks。

 and so these wireless and mobile challenges are completely outside the scope of what was originally designed into the IP network service。



![](img/77a714a56455d106638e41f0c0922a50_5.png)

In today's video we'll be introducing wireless and the associated challenges and some of the characteristics of wireless links。

Later on in this chapter we'll get to 80211 based networks， as well as cellular networks。

We'll also look at the issues surrounding mobility and some of the specific techniques that are used to support it。



![](img/77a714a56455d106638e41f0c0922a50_7.png)

First let's look at an overview of some of the elements of a wireless network and we note here that in general a wireless network is an extension of a horror wirered network。

 so the wireless links are part of the access network。

 but the core of the network is still the wired core of the internet that we've been discussing throughout the class so far so within the wireless domain we have wireless hosts which are things we're all familiar with like laptops and smartphones and IoT devices and these are the things that are running the applications that generate traffic that traverses the wireless network。

We also want to note that not all wireless devices are mobile。

Sometimes it's just too difficult or too expensive to get a wired connection to a particular device。

 and so even though that device doesn't need to move。

 it will still be connected over a wireless network。Then in addition to the wireless hosts。

 we have the wireless infrastructure typically referred to as base stations or access points。

These can be anything from the wireless LA access points in your home to the base stations that are mounted on cell towers。

We typically think of base stations as being fixed and associated with a particular geographic area that they cover also in most cases the base station has a wired backhaul link that connects it to the internet。

There are， of course exceptions to these where the base station may be mounted on a vehicle and where the base station's backhaul link may also be wireless。

And common examples of this include wireless hotspots that have been around for a decade or so。

 as well as an option for an access point in more and more new car models。

Between our base stations and wireless hosts， we have the wireless link this layer2 environment can have various data rates and operational ranges and may use one or more channels over which to communicate。

The Wireless Multi access control protocol， or Mac coordinates access to the link amongst all the wireless hosts and base stations。



![](img/77a714a56455d106638e41f0c0922a50_9.png)

We typically see tradeoffs between bandwidth and range。

 usually because it is easier to create high bandwidth links over higher frequency carriers。

 but the higher the frequency band， the more rapidly it loses energy as it propagates。

 and so lower frequencies are better for long distance links。

This chart is certainly not comprehensive in that there are microwave and satellite wireless link technologies that propagate far longer than these。

So in this plot， we're just looking at wireless lenss and wireless cellular technologies。

Most current consumer devices are using 80211。AC protocol， which is backwards compatible with 80211N。

 G and B。We're also starting to see consumer devices marketed as WiF6。

 which is the marketing name for 80211 AX。We should also note that the faster speeds here rely on bonding multiple channels together。

 and so many devices do not support the peak speed that is supported by the protocol。



![](img/77a714a56455d106638e41f0c0922a50_11.png)

So far we've just been talking about infrastructure based wireless networks。

 meaning the wireless network relies on fixed infrastructure in the form of space stations and cell towers and wired backhauls in order to function。

The wireless nodes do not talk to one another directly they only talk to the base stationation。

There are also handoff mechanisms in place so that a mobile wireless node can transition from one base station to another relatively seamlessly。



![](img/77a714a56455d106638e41f0c0922a50_13.png)

In contrast to this， we have ad hoc wireless networks。

 where the wireless hosts communicate with one another directly。

They have to organize themselves into a network and can only communicate within the range of their radios。

 there's no base station to relay transmissions from one note to another， however。

 being able to create such a network is certainly advantageous in environments where infrastructure doesn't exist or if the infrastructure has been damaged or is otherwise unavailable。

 so the most common wireless networks that we run into are infrastructure-based singleh networks。



![](img/77a714a56455d106638e41f0c0922a50_15.png)

Where each wireless host communicates only with a base station and that base station has a backhaul link to connect to the rest of the internet。

You may also hear the term mesh networking。And this is where there are multiple wireless hops before getting to a device that is directly connected to the internet。

So devices such as Wifi repeaters might fall into this category。

We also have examples of infrastructureless wireless Onehb networks and these are things like Bluetooth or Wi-fi Direct。

 and then probably the least common but very interesting to consider our multih wireless networks。

 where there's no infrastructure and so devices that are participating in the network as wireless hosts also route and forward packets for neighboring devices。

Such networks are often called mobile ad hoc networks， Vens， orvehicular ad hoc networks， Vens。



![](img/77a714a56455d106638e41f0c0922a50_17.png)

Now let's look at how wireless links compare to wired links。

One important difference is the effect of attenuation on wireless signals。

While wired signals certainly attenuate。It happens at a much lower rate than in the wireless environment。

 and in addition， wireless signals are dramatically affected by propagating through solid objects。

 like buildings， as compared to propagating through air。In addition。

 wireless links are highly susceptible to interference。

For the wireless lenss that we're used to dealing with。

 they use frequency bands that are shared with a host of other radio devices。

 as well as other electronics that may emit noise in some of the same frequencies and also microwaves that also operate at 2。

4 gigHtz and tend to emit large amounts of radio noise。

It can also easily be the case that there are more than one wireless network trying to operate on the same channel at the same time and interfering with one another。

In addition to being attenuated by objects， radio waves also reflect off objects and these reflections can interfere with the original signal。

 so between the attenuation and the multipath interference。

 even a seemingly simple wireless link can be quite challenging and prone to corrupting packets。



![](img/77a714a56455d106638e41f0c0922a50_19.png)

In order for a wireless link to be useful， there is usually a threshold SNR signal and noise ratio over which it must operate and below this the receiver will be unable to correctly decode packets。

So in order to increase our signal to noise ratio， we need to transmit at higher power or have a better tuned antenna to pick up the signal。

 so as transmission power increases， the signal to noise ratio increases and the bit error rate decreases。

However， device limitations and regulatory restrictions limit the amount of power that we can transmit。

And so if we are restricted to a given SNR， then we want our link layer to adapt accordingly so that they can get the most usable data through the link at the current SNR。

And so on this chart we're seeing three different encodings which correspond to three different data rates。

 and as the quality of the link degrades， the device could fall back to lower data rates。

 meaning codingings that achieve a lower per error rate at the given SNR。



![](img/77a714a56455d106638e41f0c0922a50_21.png)

Another problem we run' into in wireless environments is the hidden terminal problem。

 which is where we're running some distributed media access control algorithm。

 but not all the nodes can hear one another， so we' trying to use a mechanism like carrier sensing。

 it assumes that all of the nodes can hear one another。

 so the hidden terminal problem can result in unexpected collisions。In this example。

 B can hear both A and C， but A and C can hear one another。

Most of the frequency ranges that we deal with in these networks are considered line of sight transmission。

 meaning they are attenuated so significantly by the ground that there is essentially no transmission if there is a hill or mound between two endpoints。

So drawing out the signal attenuation from A and C， we can see that they reach B。

 but are greatly attenuated by the mountain in between and so they don't reach one another。

This means that F A and C both sends the channel and one begins transmitting。

 the other won't hear it so the other one may begin transmitting at the same time。

 causing a collision， which means that B won't be able to extract either communication。

So there are additional mechanisms that we can use to deal with。

 and we'll talk about those a little later on。

![](img/77a714a56455d106638e41f0c0922a50_23.png)

Back at the beginning of the link there， we talked about bandwidth sharing mechanisms。

 and the ones that we described were TDMA， time division multiple access。

 and FDMA frequency division multiple access。And we mentioned that there's one more。

 which is CDMA code division multiple access however this is not used in wired environments and so we saved it for the wireless chapter to talk about in this case a unique code is assigned to each user。

So all the users transmit on the same frequency unlike FDMA， but before they can transmit their data。

 they have to encode it using their assigned chipping sequence。

These chip sequences are orthogonal to one another。

 so the encoding just consists of taking the inner product of the original data with the chipping sequence。

 and it can be decoded by taking the summed inner product of the encoded data and chip sequence。



![](img/77a714a56455d106638e41f0c0922a50_25.png)

So in this example， we're going to look at just encoding two slots worth of data from the receiver and then decoding it at the receiver。

In this case， each slot is transmitting one bit of actual data。

 but we see that there's an eight bit shipping sequence within that slot。

Since the bit being transmitted here is a1， when the inner product is taken。

 we see that the output is just the shipping sequence。

 then in the next slot we're transmitting a zero。And so we see that the inner product results in transmitting the inverse of the chipping sequence。

 then the channel output arrives at the receiver。And it needs to extract the original data。

 and it knows the chipping sequence of the sender。So it's able to take the sum dinnerner product of these two transmissions and retrieve the original data。

So we encoded and decoded one sender to one receiver。

So where this gets interesting is where you have multiple senders and of course we said this is a mechanism for partitioning the available bandwidth across multiple users so now we have two senders。



![](img/77a714a56455d106638e41f0c0922a50_27.png)

And these sends have orthogonal chipping sequences。

So they both encode two bits of data and their time slots are aligned。

 so what's broadcast on the channel is the interference of these two transmissions。

 which is another way of saying the sum of the two transmissions。

When the receiver gets a summed transmission， it's able to choose which sender's shipping sequence to apply to it and retrieve the original data from that sender only。

So even though we have multiple senders transmitting simultaneously in the same time slots。

We're able to use the interference constructively in a way that it allows us to retrieve all of the data sent。

Now we'll note that the sender is having to encode each single bit of data into multiple bits on the channel with the chip sequence。

So there's no free lunch here， each sender is only getting a fraction of the available bandwidth because they're having to transmit in this case。

 eight bits for every one bit of data。

![](img/77a714a56455d106638e41f0c0922a50_29.png)

That wraps up our introduction to the wireless environmentron and wireless links。In the next video。

 we'll begin looking at 802。11 wireless lenss。See you then。



![](img/77a714a56455d106638e41f0c0922a50_31.png)

We hope you enjoyed this video， if you found it to be useful。

 please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。

