# 【计算机体系结构】普林斯顿—中英字幕 p98 97_02_networking-review -BV1ii421D7WR_p98-

So today we are going to be continuing our discussion of interconnection networks。

 and I wanted to say a few notes about interconnection networks。In general。Bband connection networks。

Or how do I put this， Air connection networks can be very broad。

 So sometimes people talk about this as hook together multiple computers。Things like the Internet。

 very wide scale interconnection networks。 You could also think about it connecting things together in a very small place。

 for instance， on a chip or on chip networks and things in between。 So， for instance。

 computers where inside of one chassis， for instance， there's some connection。

 interconnection network between different processors or processors in memory or Io devices。

 processors and memory inside of one box。Betweenween multiple chassis。

 something like a supercomputer or wide area networks。

 all these things broadly fall under what we're talking about here is interconnection networks。

 and I wanted to bring this up because someone came during office hours this last week and said， oh。

 you're talking about switches。And switches are in my networking class。

 we learn about switches as this very well defined thing。 A switch is like an ethernet switch。😊。

You plug some cables into it and the definition of switching that we were using。Oops。

The definition of switching that we were using in our lectures here were not the same as the definitions that were being used as a sort of ethernet switch or ethernet router。

And that's this true。 So we're looking at a much broader。

Class of networks here than just something like Ethernet or IP networks。

We're looking at we call interconnection networks because it can be ways to connect things together。

 It does not have to be of a specific protocol。 So just to recap。Switching is。

The manner in which you connect different things together。

Tology is the layout or the connection of the wires。

Roouting is the algorithm used to route packets across or route packets or data。

 or if it's a circuit switch network， route calls across a network。

 and then we're going to look at flow control a bunch today。

 which is how do you actually prevent data from getting lost on a network。Just to recap。

 we talked about this last time。We have a message which is made up of some number of bytes we'll say。

 or some of our bits。🤧嗯。From a Normenclature perspective。

 we can split this packet into a we split this message。

 excuse me into a packet here and typically you sort of have a head and a tail to a packet and maybe there's a destination and the length is pretty useful in our header and there may even be a tail bit。

 sometimes some networks actually have bits or prologues that say the packet is being completed now。

And inside of our packet， our packet can be made up of multiple flow controlled digits or fls。

A flow control digit is the minimum amount of data which can be flow controlled upon a particular link or the minimum amount of data。

 which is。Accounted for， if you will。But that fl is not necessarily the smallest amount of data here。

 you can actually split that up into your flip， if you will， into multiple fits。

 where the fit is a physical transfer digit。 And a good example of this is if you have a network where let's say all of the data going across this network is always accounted for as three2bit words。

But the links on the network are only8 bits wide。So a good example of this is you're trying to connect together two chips。

You only had eight wires to connect the two chips together。

 so you have eight wires connecting those two chips together。

It makes really no sense to try to flow control on any basis smaller than that word because the smallest thing you're to try to communicate is let's say。

 a 32 bit word。 So you're going to do flow controlling all the accounting。On the 32 bit fl。

 but inside of that， it'll be made up of four bytes or four pumps or four data transfers across the actual physical wires。

 and that's a physical transfer digit。We talked about this last time circuit switching。

 storing forward and cut through or what's known as wormhole routing or wormhole switching。

Circucle switched。Is you physically run a wire？Between point A and point B。

 and you reserve that whole length the whole time。 and there's typically what's called a call setup and a call teardown phase。



![](img/9105459de4750905c04b5bb39def9f56_1.png)

Sttoring forward is that each router are along the path。Will buffer the entire packet。

And wait till the end shows up before it starts to send the head to the next router over。

So it literally stores the whole packet and forwards it and this is actually typically sort of our Ethernet routers and our internet routers will typically try you something like storing For if you don't care about latency。

 this makes a lot of things easier because you don't have to worry about some of the deadlock concerns that we'll see in a little bit with cut through routing。

Cut3 rounding matters if you start to worry about latency。Cut through routing。

 you're actually going to send the head。On to the next router。

 before you've received the tail of the message or the tail of the packet。

So you can actually worm through the network， so one packet will actually could potentially go across multiple routers across the network and one router will not have completed the packet until the next one has started so to draw sort of an example of this。

We have a packet here， which is。Let's say eight words long。

And we have some sort of architecture where there's。Let's say it's a。Ring。

Or one directional taurus looks something like this。 and we're trying to send this packet。

 We inject the packet here。Each one of these are routers。So they have。

Some sort of swishing fabric inside of it in this case， it's a two to1 mux。

 which will take the input and sort of flow through case。And we inject here。

 and let's say this is destined for。This output link here。We're actually going to use。

Multiple of these links or multiple of these routers and links at a time。So we start to send。

 let's say。One， here is the header。We'll start to send the header。

And then the next cycle we'll send the next word， and this can flow over here。 and one can be here。

 and two can be there。The next cycle。One will be in this。

 let's say there's a pipeline register somewhere along the route here。One will be here。

 two will be there， three will be there， and we're about to send four。The next cycle。One has arrived。

Two is there， or three is there， or four is there， five is being sent and continues going on until finally eight。

Slowly moves across the network and goes out。 So we call this。Cut through or wormhole routing。



![](img/9105459de4750905c04b5bb39def9f56_3.png)