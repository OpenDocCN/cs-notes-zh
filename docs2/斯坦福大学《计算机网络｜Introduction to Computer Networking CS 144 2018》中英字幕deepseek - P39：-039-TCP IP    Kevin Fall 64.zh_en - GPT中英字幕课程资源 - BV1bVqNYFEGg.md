# 斯坦福大学《计算机网络｜Introduction to Computer Networking CS 144 2018》中英字幕deepseek - P39：-039-TCP IP    Kevin Fall 64.zh_en - GPT中英字幕课程资源 - BV1bVqNYFEGg

Oh。Hi so I'm here with Kevin fall at the computer Science Conference at symmposium on Opera System Principles and I was really lucky to run into him here and so I thought that actually you hearing a bit about he has to say about the internet would be interesting so Kevin you're currently the author of TCPIP illustrated so how did that happen like what's your relationship with TPIP and the stuff that you've done in the past and？

What's your background with TCPIRP？So guess when I was right after I graduated。

And as shortly after I got to Berkeley， somebody demonstrated to me that they could send some packet to Europe and back to Berkeley and under a second thought network。

Sort of an interesting thing to look at fast forward a number of years。

 I worked on the networking implementation in Berkeley UniX on a Cray for a while that got me into a little bit of the HPC community。

But then I worked at Lawrence Berkeley National Lab after my graduate work at UC San Diego。

 so at UC San Diego I doing some protocol work and some operating system work。

 but then with the networking group at LBL that was all quite a bit in the networking side and worked in network simulators。

NS simulator and so on what happened though is I got to know this stuff pretty well and by the early 90s or sort of mid 90s when the internet was becoming more widely known。

 people took an interest in this， what is this TCPIP stuff？

And this particular book TCPIV illustrated was the standard reference text and the volume one is still quite a good book。

 I was teaching out of it， teaching sort professionals from industries， Cisco and places like that。

And so I got to know the material quite well， but as the years went on and on and on。

 there were things that it would be nice to be updated in that book and so I had been at places where I had heard some people were approached to rewrite it。

 other people approached the editor or。Adddison to rewrite it and for whatever reason it never happened so I threw in my table of contents and sample chapter and got the job and some seven years later finished off the entire task with something that's over a thousand pages long Well so what's an example of something which you thought sort of a change which needed to be introduced but wasn't in the original。

One of the major ones is security， so there's a。I think 100 pages of security that goes through introduction of what are the sort of basic primitives。

 what are the sort of things you might want to protect against。

 and then all the various details of the protocols that actually does that。Really security。

 not only the cryptographic parts of security， but things like firewalls and stuff really barely existed when the first work was done There was also a new chapter at the beginning as sort of the architectural underpinnings which is what was in the minds of people when they were thinking about how the design decisions about this sort of stuff was made because I always found that quite interesting and being an operating systems guy originally how people came up with abstractions and how programs access those things and not quite users necessarily but。

What are the sort of architectural concerns and so I always was quite interested in papers and thoughts in some of the architectural area so last night we were talking and you said that there is like a today people use the terms datagram packet interchangeably but those were not interchangeable terms they actually meant something quite different which now lost in the sort of lost in time unless you want to talk a little about that so I think I mentioned this in that part of the book but it。

Packets were sort of a fascinating new concept that you could divide your larger messages into little parts and move them around the network。

 but they were originally at least some variant where as part of virtual circuits and so for example the destination in a packet was the destination of an index in the table of the next top so you would sort of set up the route ahead of time and then if that failed for some reason you'd have a bunch of work to do to sort of go back and there's all the history of circuits and so on。

 but datagram was maybe even more radical idea in which the destination the final destination is identified in the packet sort of structure which the way when I would teach out of this class would say know if I had laid out the network in a two-dimensional space with this datagram type property I could take it and drop it from the air down onto any router and it would just find its way through because the final destination is listed。

 but of course that was a tradeoff because now you have more bits that you have to allocate。

There's presumably a larger number of possible destinations。

Maybe available so these are the kind of nuances that were actually pretty。

Neat to sort of get the details from by going back in the architectural history and thinking and learning about what people were sort of arguing the time cool so what are you what are you working on now in sense of like what are the sort of the most interesting things do you think in networking and the Internet and systems。

that you're trying to tackle。A couple areas that I think are fun and sort of worth mentioning at least one of which we have some work on the first one is just。

We don't have so much work on， but is the。And I mentioned you Li lighter。

 and I'd make reference to that in the book as well， but the。

Him and some sort of his colleagues and predecessors had envisioned that not only do we have a thing that winds up essentially being today's internet that there's communication in these communities。

 but there's also a physical way of moving things around which is like a global pneumatic tube system so you could take your thing s it and it would find its way which would be a very cool thing to have but I don't think we're quite there yet and I'm not sure we're ever going to really wind up at that they sort of made possible not pneumatic but it's not quite pneumatic but on the other hand I think the sort of 3D printing technology as combined with what's going on with the sort of free or easy dissemination of information becomes quite interesting especially when you can put things other than plastics and so on so I had in my hand a demonstration that was a titanium 3D printed nose replacement part prosthetic nose and it was strands of titanium printed on top of each other and if you can。

Lad up your device with the right materials， pretty much any material thing you want to create almost could be。

Created， so we've even into the world of sensor networks， things we've， you know。

 people looked at both sensing the world， maybe even actuating the world。

 but like building the world on demand in combination with those other things pretty interesting。

 And I wonder if that's not。Kd of the way to get to the vision of pneumatic tubes but instead of actually moving it you just make another one and so that you know how far in the future will it be that you just carry around in your car your backpack or whatever the basic system and then you just download whatever the thing is you happen to need it even goes little there was literally I think it was not a few months ago there was a meeting in Washington Dc about like security implications of additive manufacturing I mean there's all those questions about firearms Yeah like gun was lower chassis So generally in firearms there's one particular piece of the guns the one that's strongly regulated is the thing which kind of everything has to stick onto and somebody 3D printed one and it's only something you need a license for there' sort of this interesting question about what the implications are going for all these kinds of things like DM yeah and so what is I think those are there's lots of policy questions I as is often the case technology。

G will outpace the policy ability to comprehend and sort of instantiate reasonable laws about these things。

 whatever that may be。So this idea that you bits that are become interchangeable with physical objects and we traditionally have regulated the control of physical objects。

 but now do we have to is the creation time Yeah creation it's pretty interesting so that that set of implications So that's one of the topics and actually gets into other things that you can compute with and maybe print and compute like synthetic biology I want to you know create a little organism that takes one thing and something comes out the other end。

 well if I have biologicals in my 3D printer and I can download that and have the。

not just download designs， but have the tools。To do the designs of the biological systems I just always hard on very concerned about these implications。

So that's one whole category， I think that when I was thinking about the pneumatic tube system and then looking at 3D printing and its capabilities and now the price has gone down so people can just go get them。

 this is a pretty interesting thing。Cool， cool， it was great chatting with you and thank you for your time Okay and yeah see you next time。

