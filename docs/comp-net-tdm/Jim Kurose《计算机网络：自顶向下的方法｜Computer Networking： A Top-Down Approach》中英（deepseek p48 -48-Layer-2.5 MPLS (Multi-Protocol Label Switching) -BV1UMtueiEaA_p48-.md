# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p48 -48-Layer-2.5 MPLS (Multi-Protocol Label Switching) -BV1UMtueiEaA_p48-

In this video we're looking at multi protocoltocol label switching， known as MPLS， let's get started。



![](img/2d2a6c76495e98225dca4ee456566cf1_1.png)

Now we'll look at link virtualization using NLS， which stands for multiprotocol label switching。



![](img/2d2a6c76495e98225dca4ee456566cf1_3.png)

MPLS is sometimes referred to as layerer 2 and a2 because it adds a shim header in between the layerer 2 header and the layerer 3 IP header。

It uses this to insert a fixed length identifier， which it uses two forward packets on a preconfigured path through the network instead of having to do longest prefix matching at every hop along the way。

This borrows some ideas from the virtual circuit approach in that the path through the MPS network is preconfigured and then used for many。

 many packets。So here we have our MPS header inserted in between the layer2。

 which could be Ethernet or something else， but outside of the IP header which remains unchanged。

Inside that MLS header， we have the label itself and a couple other fields including a PTL for the MPLS layer。

Note that the implication here is that the IPTTL is not getting touched at each hop in the MS network。

So one can think of the NLS circuit as a tunnel where IP packets go in one end and pop out the other end unchanged。

 and the NLS routers in between may not show up in things like a trace route because they don't touch the IP header。



![](img/2d2a6c76495e98225dca4ee456566cf1_5.png)

MPLS routers， also commonly called label switch routers。

 only look at this label value to determine where to send a particular packet。

 so they're not looking at the IP header nor are they using IP routing and forwarding tables。



![](img/2d2a6c76495e98225dca4ee456566cf1_7.png)

The decision of what MPLS label to assign a particular packet can use principles similar to those we discussed in generalized forwarding where it can look at any header field to determine which MS path a packet should be placed onto。

And so this allows for flexibility in traffic engineering or even giving priority to different flows。

It can also be used to have entire precomputed backup paths that can be substituted very quickly if the primary path fails。



![](img/2d2a6c76495e98225dca4ee456566cf1_9.png)

Let's compare multiprotocol label switching with IP。In this case。

 we have both the blue and green IP flow headed for destinationest A。

And because IP uses destination based forwarding， they will both converge onto the same path through the network。

If instead we make this an NPLS network， then the first router that these flows arrive at that's part of the NPLS network needs to decide what label to assign to each of these flows。

 and it can look at the source address and make a decision based on something beyond just the destination and put these two on different flows if it wants them to take different paths through the network for traffic engineering reasons。

So while we're talking about it later in the course。

 MPLS predates the SDN generalized forwarding that we talked about in previous videos by about a decade。

 but it shares a number of goals in common with generalized forwarding or software defined networks。



![](img/2d2a6c76495e98225dca4ee456566cf1_11.png)

MPLS requires some signaling to set up the precomputed paths and it does this over modified linked state routing protocols。

Note that in MS we have the concept of reserved bandwidth similar to virtual circuit networks。

So it would be possible to prevent congestion from occurring within an NLS network。

When setting up an MPLS path， the router uses the RSVPTE Pro to let the other routers in the network know what label it will be using and what interfaces packets with that label should be forwarded through。



![](img/2d2a6c76495e98225dca4ee456566cf1_13.png)

So here we have a path and we can look at the forwarding tables that implement that path。

R4 is our MPS Ingress router in this case， so the packets coming in have no existing label。

 but it applies the labels to the packets based on their IP source and destination。

 and then forwards them out based on the MPLS forwarding table。

We also note here that the labels themselves change as routers forward them。

 so for the path shown we have label 10 going out interface 0 on R4 and when a label 10 packet arrives at R3。

 it gets assigned to label 6 and forwarded out interface 1。Then when a packet with label 6 arrives。

 at R1， that's the egress from the MPLS network， so it removes the label and forwards it out in phase zero。



![](img/2d2a6c76495e98225dca4ee456566cf1_15.png)

That wraps up our discussion of MPLS or layer 2 and half In our next video we'll be looking at some details of how data center networks are constructed and particular considerations that have to be made due to their vast scale See you then。



![](img/2d2a6c76495e98225dca4ee456566cf1_17.png)

We hope you enjoyed this video， if you found it to be useful please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。

