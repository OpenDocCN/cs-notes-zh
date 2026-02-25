# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p20 -20-Performance of Reliable Data Transfer - Transport Layer -BV1UMtueiEaA_p20-

In this video we look at the performance of reliable data transfer protocols。

 including the Go back in and selective repeatat algorithms Let's get started。



![](img/d6a0e6d2be924ece2abb1b660564774f_1.png)

Already in this course you've seen some instances where protocol design can have a significant impact on performance One example of this was with HTTP 1。

0 where each request had to start a new TCP connection and that was improved in HTTP 1。

1 allowing subsequent requests to reuse the same TCP connection。

Well we're going to see some similar things with the transport layer。In the last video。

 we talked about the design of a stop and wait protocol for reliable data transfer。

Now we're going to evaluate its performance。We're going to do this in terms of utilization。

This is the fraction of time that the sender is able to utilize the bandwidth of the link they're connected to so with an ideal protocol the utilization would be one to put some numbers on that we'll look at a 1 gigab per second link which has a propagation delay of 15 milliseconds over which we're sending 8。

000 bit packets or 1，000 byte packets。Our transmission delay for one of those packets will be 8 microseconds。

 this is 0。008 milliseconds。Just by looking at the units on those。

 we can see that the transmission delay is extremely small relative to the propagation delay。



![](img/d6a0e6d2be924ece2abb1b660564774f_3.png)

Now let's draw out our stop and way operation on a time sequence diagram。

We see that the sender sends a small amount of time transmitting the packet。

And then a large amount of time waiting for it to propagate to the receiver and waiting for the acknowledgement to propagate back to the sender。

 so our utilization can be calculated from the round trip time and the packet length of the rate。

 which forms our transmission delay。And we're going to divide our transmission delay by the total time used。

Meaning the transmission delay plus around trip time。

Plugging in the numbers from before we see that we have that eight microseconds over approximately 30 milliseconds。

And we know that our end result is going to be a very small utilization。In fact。

 if we're using that one gigabit per second link that we mentioned a couple slides ago。

 we'll only have 33 kilobits per second of utilization。

So while our stop and weight protocol is fully reliable， its performance stinks。

It becomes the limiting factor in performance， even with a host that has a well provisioned network connection。



![](img/d6a0e6d2be924ece2abb1b660564774f_5.png)

If we were to visualize a network connection between opposite ends of the country。

 we see that we have a long pipe but only one packet in it。

 so the solution to our performance problem is called pipelining。

And this is where we enable the protocol to have multiple packets in flight in order to conceptually fill the pipe。

 so in the best case scenario， the sender will be able to keep sending packets back to back until it starts getting the acknowledgments back from the receiver。



![](img/d6a0e6d2be924ece2abb1b660564774f_7.png)

So let's see how that increased utilization works in the time sequence diagram。

Now our sender is able to keep sending packets back to back in this case。

 up to a window size of three packets as those packets arrive at the receiver。

 the receiver starts sending back the acknowledgeledments。And when the sender gets those。

 it's able to send three more packets。So now in the same period of time。

 we're able to send three times as much data， meaning our utilization has tripled。



![](img/d6a0e6d2be924ece2abb1b660564774f_9.png)

Pipelining increases the complexity of the reliable data transfer protocol and there's a couple different ways to implement it One of those is called Go backN With GobackN the sender has a window size of up to end packets that it's allowed to have in flight before they have been acknowledged in order to keep track of these it needs a sequence number in the header of each packet and our one bit sequence numbers no longer going to be sufficient so we'll have some number of bits dedicated to tracking sequence numbers in the header so visualizing our sender's buffer。

We have some packets that have already been acknowledged， and then we have our window of packets。

 some of which are in flight unacknowledged， and we may have some slots available to send more packets。

And then we have some future positions for packets。

 which are not yet usable because they're outside of our in packet window。

With the Go back end algorithm， we use a cumulative act。

So the AC acknowledges all packets up to that sequence number。When one of these acts arrives。

 the window moves forward。To the N+1 position。The sender must maintain a timer for the oldest in flight packet so that if the acknowledgecment doesn't arrive。

 it can be resent， if that timeout happens， the sender is going to go back N。

 meaning go back all the way to the beginning of its window and start retransmitting the packets in order。



![](img/d6a0e6d2be924ece2abb1b660564774f_11.png)

On the receiver side， acts are sent out for the highest sequence number received in order。

If packets are received out of order， the receiver just keeps acknowledging the last sequence number it received in order。

Those out of order packets may be discarded since the receiver knows that the sender will have to go back and retransmit them if an earlier packet timess out。

On the other hand， it's possible that the packets are just deriving out of order。

 and so the receiver could choose to buffer the out of order packets in case the earlier packet arrives later。

So in the receiver's buffer， we'll see the Re base。

 which is the beginning of the window of packets that the receiver will accept。

Sequence numbers below that have already been acknowledged。

And SQL numbers that arrive above that are out of order。



![](img/d6a0e6d2be924ece2abb1b660564774f_13.png)

Now let's look at our go back in algorithm on a time sequence diagram。

We have our sender starting with a window of four packets。

 it sends out the first four packets zero through three。But packet2 is lost along the way。

As the packets arrive with the receiver sends back acknowledgecments。

But note that when packet 3 arrives， the receiver sends a duplicate Act for packet1 because it will only act packets that arrive in order。

As the receiver gets these aments， it's able to shift its window over and send more packets。

This happens for the first couple acgments that arrive， but then the third act is a duplicate。

 and so that has no effect on the window。On the receiver side。

 it's discarding these out of order packets and sending back duplicate acts for packet1 still finally the timeout for the packet2 act。



![](img/d6a0e6d2be924ece2abb1b660564774f_15.png)

Expires and the receiver retransmits。The whole window is starting with packet2。

Since these arrive in order， the receiver acknowledges all the packets。

 you may note that there are some inefficiencies here in terms of resending data that's already been received by the receiver。

This is due to a engineering trade off that was made between complexity of the algorithms and bandwidth efficiency。

When these protocols were being developed， host resources were far more scarce than they are today in terms of computation and memory。

So these are optimized to need as few pointers and timers as possible。

An alternative to go back in is called Selective repeatat。



![](img/d6a0e6d2be924ece2abb1b660564774f_17.png)

In selective repeat， the receiver individually acknowledges each packet。

 even those that arrive out of order， this requires that the receiver buffer those out of order packets until it's able to fill the holes and deliver everything in order to the application。

On the sender side， rather than just maintaining a timer for the oldest packet， in selective repeat。

 the sender needs to maintain a timer for every packet that it sends。As before。

 the center will maintain a window of end packets that it's allowed to have outstanding。



![](img/d6a0e6d2be924ece2abb1b660564774f_19.png)

So now our selective repeatat send buffer may have a mix of unact or act packets。

But the window will not be able to move forward until the oldest packet is acknowledged。

Likewise on the receiver side， we see the acknowledged packets。

 followed by the window of expected packets， some of which may have been received out of order。

But again， the window won't move forward until it receives each packet in order。



![](img/d6a0e6d2be924ece2abb1b660564774f_21.png)

So from the sender perspective， the changes are the addition of multiple timers， one for each packet。

And that the window can only be advanced when the lowest sequence number in it is acknowledged。

 at which point it may need to be advanced multiple values if other packets have been acknowledged out of order。



![](img/d6a0e6d2be924ece2abb1b660564774f_23.png)

On the receiver's side， we have the requirement for an out of order packet buffer。

 and whenever a packet is received in order， the receiver will have to check and see if theres an additional packets that can also be delivered to the application in order。



![](img/d6a0e6d2be924ece2abb1b660564774f_25.png)

Now let's see Selective repeatat on a time sequence diagram。

Just as before we have a window size of N packets and the sender starts out by sending packets 0 through3。

Also as before packetA2 is lost， but this time NTO and packetCAT3 arrives。

 the receiver acknowledges packetA 3 it's not sending duplicate Xs in this case。

As those acts arrive back at the centerer， it's able to move the window forward and send new packets。

When Act 3 arrives， As sender records it， but it's not able to move the window forward because it still doesn't have an acknowledgecment for packet 2 The receiver also keeps acknowledging out of order packets and eventually the timeout expires for packet 2。



![](img/d6a0e6d2be924ece2abb1b660564774f_27.png)

At which point the Cer retransmits packet2？Now when packet 2 arrives at the receiver。

 it's able to deliver packets  two through five in order to the application。

And when Act 2 arrives back at the center， it will be able to move the window forward multiple places because it's already recorded the out of order Accledments。



![](img/d6a0e6d2be924ece2abb1b660564774f_29.png)

So now let's see where we can run into some trouble。

Remember that we have to keep track of the sequence numbers in the packet headers and acknowledgement headers。

 so we need to dedicate some number of fits to this purpose。The more bits we use。

 the more overhead we are creating in terms of larger header sizes on each packet in this example we'll use a  two bit sequence number which allows us to record values 0 through 3 then suppose we want to use a window size of three This send sends out its first three packets and moves the window accordingly。

On the receiver side， as the packets arrive， its window also moves in this case packet 3 gets lost and the second packet  zero arrives out of order。

So far， everything's working as expected and the timeout will trigger replacement for packet 3。

Now let's look at a different loss pattern。In this case。

 the first three packets arrive and the receiver's window moves accordingly。However。

 all three acts are lost。Note that it is not uncommon for losses to happen in bursts in the internet。

 and so this is not an unrealistic scenario。So the next event that will happen on the sender side is a timeout of the timer for packet zero。

And when that packet is res， note where the receiver's window is。It is expecting a packet zero。

 but it's a later packet zero than the first one that had already received。So while the packet zero。

 arriving is a duplicate。The receiver will treat it as new data and deliver this duplicate up to the application out of order。

This is a major problem because one of the guarantees that our reliable transport protocol is supposed to be providing is in order delivery。

This demonstrates the characteristic that we talked about in the previous video that the receiver is blind to the state of the sender。

 except as it can infer through the control messaging， so to fix this。

 we must establish a relationship between our Windows size and the sequence number space。



![](img/d6a0e6d2be924ece2abb1b660564774f_31.png)

In fact， we need a sequence number space that is at least double the size of the window that we want to use。



![](img/d6a0e6d2be924ece2abb1b660564774f_33.png)

That wraps up our discussion of the principles of reliable data transfer。

These principles are what are used in creating the TCP protocol。

 which will be the subject of our next video。See you then。

 we hope you enjoyed this video if you found it to be useful please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。



![](img/d6a0e6d2be924ece2abb1b660564774f_35.png)