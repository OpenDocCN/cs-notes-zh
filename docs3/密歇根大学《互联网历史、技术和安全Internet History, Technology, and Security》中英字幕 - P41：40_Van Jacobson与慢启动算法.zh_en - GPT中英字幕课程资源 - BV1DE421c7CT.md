# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P41：40_Van Jacobson与慢启动算法.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

🎼你。🎼，🎼そ。🎼宝宝。🎼お。🎼宝宝。There were lots of campus ethernets because they were really easy to deploy and you could put them。

In a department。Then you could run a wire between two departments and you had a bigger network。So。

We've grown up networks sort of by agglomeration。In lots of different university campuses。

AndCF came up with some money， said， oh。We've got a little bit in our budget where we could get some 56 kilobit lines and tie those campuses together。

And。They did that， made the NSF met phase one， but now you're tying together。

10 megabit campus infrastructure with 56 kilobit wires。And。

It was wildly popular because people that couldn't talk could suddenly talk。

They're sending emails and moving huge files and everybody is really excited about。This technology。

 but。Any one of those campuses could oversubscribe the net by a factor of a00。

We had a lot of packets piling up and getting dropped。

At the time I was a researcher at Lawrence Berkeley Lab。

Which is in the hills up above the Berkeley campus。And I was also teaching。On the Berkeley campus。

Even back in those days， which was mid 80s， we had a。For every class there was。Messages group。

 like a little news group that was set up， all the assignments would be put online。

And I was trying to get course materials。From my office and I'll be held down to a machine in Evans Hall at Berkeley。

诶。There was like zero throughput in the net， it was one packet every 10 minutes or so。

It seemed unbelievably bad and I went down and talked to。My cars who was heading。BSD group。

People that develop Berkeley Unix。He's getting reports of these problems from。All over the country。诶。

In those days， the easiest way to start running TCPIP was to bring up Berkeley unx because there was a。

ArRPpa funded very nice implementation。诶。And everybody was seeing。Poor performance。We talked for。

A long time that day and on succeeding days about well， what's going wrong。

There's some mistake in the protocol implementation， is there some mistake in the protocol？

This thing was working on。Smaller scale tests， and then it suddenly fell apart。

I think we struggled for。Three or four months。Going through the code。

writingriting tools to capture packet traces and looking at the packet traces and trying to sort out。

Which was breaking。And I remember the two of us were sitting in Mike's office。

After we've been pounding our head against the wall for literally months。And one of us。

 I can't remember which one said， you know， the reason I can't figure out why it's breaking is I don't understand how it ever worked。

We're sending these bits out at 10 megabits。They're zipping across campus。

 they're running into this 56 kilobit wire。We expect we to go through that wire。

 pop out on the other side， go through。How could that function。That turned out to be the。

The crucial starting point。At that point。We started saying well。

What is there about this protocol that makes it work。

 how does it deal with all of those bandwidth changes， how does it deal with the multiple hops？So。



![](img/543bd040c1f315de899c400513d5a9bc_1.png)

This picture。That direction is time， this direction's bandwidth。

 so that's a fat pipe and that's a skinny pipe。And。

The scale at the time is this is a 10 megabit pipe， and this is a 56 kiloabbit pipe。And。

Here the difference is about three to one， it was really closer to 100 to one。嗯。And。So time。

Seconds times bit per second equals bits。Each of these little boxes in there。Is。A packet。

 it's the number of bits in a packet。And if you scrunch it down in bandwidth。

 it's got to spread out in time because the number of bits doesn't change。And so。呃。是一个。

First of packets， a Windowsworth of packets gets launched。

 it's going to fly through the net till it hits this faster or slow transition。

And then because the packets have to stretch out in time。

 they all have to sit there and wait as they're fed into the slower wire。And you。They pop out。

The other side。They get spread out by this bottleneck by the slower wire， once they're spread out。

 they stay spread out， there's nothing to push them back together again。They hit a receiver。

 it turns every data packet into an a。So you've got a bunch of axe that are going back towards the centerer and they remember what's the right spacing for that bottleneck。

So the as get back。To。The sender and every act gets turned into a data packet。

 so we can see the data packets flow back。And this is after one round trip time。

Now the packets are coming up perfectly spaced so they go by。系。

A new one goes into the net in exactly the time it takes a packet to exit from the bottleneck。

So these acts are sort of acting as a clock。That you tells a sender when it's safe to inject every new packet。

And therere always going to be space by whatever is the soluce point in the net and the key thing is is how how can you get the steady state sort of most quickly waste state？

The issue of the failure we saw was this works perfectly。

After you've exchanged around trip time worth of packets。But when you're starting up。

When you hear there's no clock。And so the hard part on TCP is not getting it running。

 it's getting it started。Because once you've got it running and you've got a clock tells you exactly what to do。

If you turn them on suddenly you get in this repetitive failure mode where you saturate the buffering that was available at some gateway and then when you retransmit you do the same thing again so you're always losing packets。



![](img/543bd040c1f315de899c400513d5a9bc_3.png)

But if you。Turned it on more gradually than you wouldn't overload the buffering。

 And you'd get enough of a clock going so that you control the amount of。

Backlog to fit the available buffer， but you'd still be growing the number of packets in flight so that you'd eventually get a。

You start with a kind of sporadic clock but you'd eventually fill in the details and get up for pack of clock。

How did you get it to the point where it was in all the TCPIP implementations on the planet because they kind of have to cooperate in a way So remember it was a much simpler time when you're talking about。

All the TCPI implementations on the planet。At that time， there were like four。

So there was the Berkeley Unix one， there was the MIT PCTCP。

 there was a BBN one that was used in butterflies and nymphs。And there was a multiticx one。Took the。

A couple of TCP kernel modules that we've been working on， package them up in a tar。

I had this horrible driver hack that would let us snf packets from the colonel。

 and I it was really a horrible driver hack。The way you said what you wanted to sf was by 80b and the kernel you wrote。

In binary， some new values， these are the ports that I want to look at and the driver would capture those into a circular buffer and you'd read kernel memory to pull that buffer out。

嗯。Craig Laris and Chris Tork， who were working in。My group at。

LBL and we're both longtime Colel hackers were。Embarrassed at this。They put together a really nice。

 clean driver。They go BPF， the Berkeley packet filter that would let you pull packets out of the kernel via a very efficient dial control interface。

 and so we bundled all of that up，And。The TCPI P mailing list， which in those days， was。

GCPIP was very experimental， it was very leading edge。

Pretty much everybody was playing with it was on that mailing list。

Annoce that this stuff was available。A bunchun of people haveed it。啊。Tried it， it blew up。

Sent Colonel Corums and bug reports。Fix the bug reports， and。Put new versions out。

Somebody would immediately come back and say， panicked here， do you want the K cor and I go， oh， no。

 embarrassed。Put out a new version， go out， somebody else would come back and say， panicic here。

Fixed that and cycled like that。 And after about a day。

 we got a version that didn't immediately panic and then started working on the。

The actual algorithms and。A little bit of tuning to make sure that it。Actually。

 did good all the time and didn't do any harm。

![](img/543bd040c1f315de899c400513d5a9bc_5.png)

Just completely a community effort and。sortr of when the community was saying this。

Mostly does good and never seems to do harm。That's pretty much what Mike needed to put it into the kernel。

 so he took the community development modules and rolled them into the BSD release。

