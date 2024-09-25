# 【计算机网络 CS144】斯坦福—中英字幕 - P136：p135 9-2 Kevin Fall - 加加zero - BV1qotgeXE8D

 Hi， so I'm here with Kevin Fall at the computer science conference at the Supposium and Operating。

 Systems principles。 I'm really lucky to run into him here。

 and so I thought that actually hearing a bit， about what he has to say about the internet would be interesting。

 So Kevin， you're currently the author of TCP/IP Illustrated。 So how did that happen？

 What's your relationship with TCP/IP and the stuff that you've done in the past？

 What's your background with TCP/IP？ So I guess when I was right after I graduated。

 and shortly after I got to Berkeley， somebody， demonstrated to me that it could send some packet to Europe and back to Berkeley and under。

 a second that networking became sort of an interesting thing to look at。

 Fast forward a number of years， I worked on the networking implementation in Berkeley。

 Unix on a cray to grow wild。 It got me into the little bit of the HPC community。

 But then I worked at Lawrence Berkeley National Lab after my graduate work at UC San Diego。

 So UC San Diego is doing some protocol work and some operating system work。

 But then with the networking group， but LBL， that was all quite a bit in the networking。

 side and worked on network simulators and NS simulator and so on。

 What happened though is I got to know this stuff pretty well and by the early 90s or sort。

 of mid 90s when the internet was becoming more widely known， people took an interest， in this。

 what is this TCP/IP stuff。 And this particular book， TCP/IP Illustrated。

 was the standard reference text and the volume， one is still quite a good book。

 I was teaching out of it， teaching professionals from industries， Cisco and places like that。

 And so I got to know the material quite well but as the years went on and on and on， there。

 were things that it would be nice to be updated in that book。

 And so I had been at places where I had heard some people were approached to rewrite it。

 Other people approached the editor or the addison to rewrite it。 And for whatever reason。

 it never happened。 So I threw in my table of contents and sample chapter and got the job and some seven years。

 later finished off the entire task with something that's over a thousand pages long。 Well。

 so it's an example of something that you thought sort of a change needed to be。

 introduced but wasn't in the original。 One of the major ones is security。

 So there's a hundred pages of security that goes through the introduction of what are the。

 sort of basic primitives， what are the sort of things you might want to protect against。

 And then all the various details of the protocols that actually does that。 Really security。

 not only the cryptographic parts of security but things like firewalls。

 and stuff really barely existed when the first work was done。

 There's also a new chapter at the beginning of sort of the architectural underpinning switches。

 What was in the minds of people when they were thinking about how the design decisions。

 about this sort of stuff was made。 Because I always found that quite interesting and being an operating systems guy originally。

 how people came up with abstractions and how programs access those things and not quite。

 users necessarily but what are the sort of architectural concerns。

 And so I always was quite interested in papers and thoughts and the architectural area。

 So last night we were talking and you said that there is like a today people use the。

 terms data ground， packet interchangeably but those were not interchangeable terms。

 They actually meant something quite different which now should have lost in time。

 So I think I mentioned this in the part of the book but packets were sort of a fascinating。

 new concept right that you could divide your larger messages into little parts and move。

 them around the network。 But they were originally at least some variant were as part of virtual circuits and so for。

 example the destination in a packet was the destination of the index in the table of the。

 next top so you would sort of set up the route ahead of time。

 And then if that failed for some reason you'd have a bunch of work to do to sort of go back。

 and there's all the history of circuits and so on。

 The data ground was maybe even more radical idea in which the destination， the final destination。

 is identified in the packet sort of structure which the way I was when I would teach out。

 of this class would say you know if I laid out the network in a two dimensional space。

 with this data ground type property I could take it and drop it from the air down onto。

 any router and it would just find its way through because the final destination is listed。

 But of course that was a trade off because now you have more bits so you have to allocate。

 because there's presumably a larger number of possible destinations that might be available。

 So these are the kind of nuances that we're actually pretty neat to sort of get the details。

 from by going back in the architectural history and thinking and learning about what people。

 are sort of arguing the time。 Cool so what are you working on now？

 In the sense that like what are the most interesting things do you think in networking and the。

 internet and systems that you're trying to tackle。

 So there's a couple areas that I think are fun and sort of worth mentioning at least one。

 of which we have some work on。 The first one is just we don't have so much work on but is the。

 and I mentioned you Lick， Lighter and I make reference to that in the book as well but the him and some sort of。

 his colleagues and predecessors had envisioned that not only do we have a thing that winds。

 up essentially being today's internet that there's communication in these communities。

 but there's also a physical way of moving things around which is like a global pneumatic。

 tube system so you could take your thing， shove it and it would find its way which would。

 be a very cool thing to have but I don't think we're quite there yet and I'm not sure。

 we're ever going to really wind up with that。 Yeah they sort of needed possible。

 Not pneumatic but it's not quite pneumatic but on the other hand I think the sort of 3D。

 printing technology as combined with what's going on with the sort of free or easy dissemination。

 of information becomes quite interesting especially when you can put things other than。

 plastics and so on。 So I had in my hand a demonstration that was a titanium 3D printed nose replacement part。

 prosthetic nose and it was strands of titanium printed on top of each other and you know if。

 you can load up your device with the right materials pretty much any material thing you。

 want to create almost could be created。 So even into the world of sensor networks things people look to sensing the world maybe even。

 actuating the world but like building the world on demand in combination with those other。

 things is pretty interesting and I wonder if that's not kind of the way to get to the。

 vision of pneumatic tubes but instead of actually moving it you just make another one。

 And so that you know how far in the future will it be that you just carry around in your。

 car your backpack or whatever the basic system and then you just download whatever the thing。

 is you happen to need。 It even goes a little there was literally I think it was not a few months ago there was。

 a meeting in Washington DC about like the security implications of additive manufacturing。

 Well I mean I tell those questions that you can fire on me。 Yeah like 15 was in the lower chassis。

 So generally in firearms there's one particular piece of a gun the one that's strongly regulated。

 it's the thing which kind of everything has to stick onto。

 And somebody 3D printed one it's normally something you need a license for。

 It's sort of this interesting question about what the implications are going for all these。

 kinds of things like DRM。 Yeah and so what is I think those are there's lots of policy questions I think one as is。

 often the case technology will outpace the policy ability to comprehend and sort of instantiate。

 reasonable laws about these things whatever that may be。

 And so this idea that you know bits that are inter become interchangeable with physical。

 objects and we have traditionally have regulated the control of physical objects but now do。

 we have to。 What's your mission with the other？ I mean I remember the creation time。 Yeah so。

 The creation it's pretty interesting so that that's one of the topics and it actually gets。

 into other things that you can compute with and maybe printing compute like synthetic biology。

 I want to you know create a little organism that takes one thing and something comes out。

 the other end。 Well if I have biologicals in my 3D printer and I can download that and have the not just。

 download designs but have the tools to do the designs of the biological systems。

 I think they're hard to try。 It's very very interesting about these implications。

 So that's one whole category I think that when I was thinking about the mnemonic tube。

 system and then looking at 3D printing and its capabilities and now the price has gone。

 down so people can just go get them。 It's a pretty interesting thing。 Cool cool。

 Those are great challenges and thank you for your time。 Yeah， sure。 See you next time。

