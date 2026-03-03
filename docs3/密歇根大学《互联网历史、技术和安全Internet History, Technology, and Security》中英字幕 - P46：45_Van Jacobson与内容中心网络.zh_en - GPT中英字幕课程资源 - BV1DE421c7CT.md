# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P46：45_Van Jacobson与内容中心网络.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

🎼你是。🎼Okay。🎼好。🎼宝宝。We're。Having massive scaling problems today。Trying to join together。

The very information centric web model。With very hocentric。

TCPIP model if you look at how the net has evolved。It started as a telephone system for computers。

The model was。Computers wanted to exchange data。People wanted their computers to be able to exchange data。

The model we had for。Communication。For 140 years it been the phone system， so he said， okay。

 they want to have a conversation because communication is conversation over a long distances。And so。

Let's make。Protocols and infrastructure that allows computers to have a conversation。First。

 kind of that。Things like the ARPpanet networks that would handle。Different bandwidths。

Require all of that。Global clock distribution of a telephony network instead they substituted buffering and。

One crucial thing coming out of Paul Beron was。Unlike the phone system where。

The communication was all about building a wire。H by hop link by link between the two endpoints basically。

Instructing the switching system， how to make one long wire， Paul said don't do it that way。

 just identify the endpoints and let the network take care of getting the data there。

 so this is great。Just completely changed the world。 but the bulk of that change was。

Didn't happen in the 70s and 80s and early 90s when the net was first crying out。

 it happened in the late 90s and the 200s when the web took off。

And it had nothing whatsoever to do with computers having a conversation model。

 it had to do with people creating and consuming content。And the web sort of。

Showed us for the first time what happens if。We leave behind this 18th century model of telephony。

Instead， we start to look at。Not the wires， but the information in the wires and the web gave us a structure where you could name information。

 not the process of getting it but the information itself say I want this web page。

 I want this YouTube video， I want this。Amazon personal page and you will get back a setup。Content。

 something thing that represented that name that you gave。 What if we。Greek cast。The way we。

Think about the low level infrastructure。Don't say the web is an overlay on top of DCCPIP。

 which is the way it's implemented today， say。If。99% plus of what we do is web like stuff is there a model that lets us do the same stuff at the packet level of who we make it the basis of our communication rather than saying it has to be an overlay。

So you can create videos， you can put them on your own website and you have to pray that they never get popular because if they get popular。

 your ISP is almost immediately going to shut you down because your link will be completely saturated what we used to call a slash do effect。

That's intrinsic to the conversational model， right。

 we don't do broadcast TV by making phone calls to a TV station if you want to put。

Media distribution over TCPI， you have to figure out some way to lie to the network so that YouTube。

 co， which TCP。Thinks is a location， it's identified by an IP address。

 you've got to make sure that it's not a location that is's spread across the entire planet。

So while we spent。Most of the。90s growing the Internet and having the protocols work for us now if you look at。

YouTube， Google， Amazon， Facebook， Twitter， all of these。Very heavily used。Services。That。

Manifest themselves to the net as an IP address， looks like a single location。

 but if they're a single location with hundreds of millions of users，That。

Traffic in a conversational model always scales like the popularity。

 it scales like the number of consumers。And。You you're doing。

Twitter update or a video that wants to be seen by millions。

You can't deploy it in a conversational model and we spend all our time fully the net information that's sort of qualitatively the same it's all naming or identity information。

 but it's spread randomly across the whole damnm packet so we've got source and destination addresses that conventionally we think of as layer3 and so it's up at front to be used by the network layer and then we've got。

Ports that are layer four， and so they're a little bit deeper in because they're supposed to be used by the end node for its demine to to a particular application。

Then。Inside of that， we've got sequence numbers which are being used when you get to the application for it to reassemble a larger unit。

And inside of that， we've got URLs which are used by。

Higher level part of the application than non transport part of the application you've just got all of this information and it's all fundamentally name information it's what do these bits mean？

If you pull together the source addresses， the ports， the sequence numbers， the URLs。

 they all give you context for the information， they're all the name of the information。

What if rather than having。You know， Amazon's load balancer， which is trying to figure out。

 all right， which of my 50，000 unused machines is currently handling this customer's request。

 so I have to look at the addresses， I have to look at the ports。

 I have to look at the sequence numbers， I have to look at the cookies in order to dispatch the sucker to where it's going。

 what if I say packets have a name on the front？And all of that information just gets collected to the name。

And at any point in the network， you look at as much of that name as you need to look at to doing your job。

 if just the front part will work， because all you're doing is gross level story。

 just look at the front。If you need to look at more of it if we don't have layers。

 what we have is a set of structured information。There's。

We know that we're going to be looking at different parts of it for different reasons。

 so we put topologically sensitive information like Amazon。com， stick that at the front。

Because you can use that to make。Scalable routing tables。But when it gets there。

 we don't want to say there's a transport protocol and there's various layers to say， yeah。

 there's a job that I'm doing when I get to Amazon。com and it requires me to look at this much。

If you don't。Care where you're getting the data。All that matters to you is what the data is。

 not where it comes from。Then。All of this memory that has to be in the network。

As buffering in order to。To manage the multiplexing of the network。Suddenly， that becomes。

A viable source of data。 the way it happens today is。

You're watching a YouTube video that means the bits leaves and server YouTube。

 they go into the downstream gateways memory， they get pulled out of that memory， put into a wire。

 go into the next top gateways memory， and they're going bouncing memory to memory。

Through all these interconnecting wires， do they get to you？If the two of us are watching the same。

Video。Then the immediate upstream Gway gets one copy of the video going to me。

And another separate copy of exactly the same video going to you。

They both went through that gateway's memory。It's。Because of this conversational abstraction that we're putting on。

 because the gateway doesn't know that we're consuming the same content。

 what it sees is two different conversations。Can't look in this memory and say， oh， I've got that。

 I can give it to you。You have to fetch a new copy and you have to fetch it all the way from YouTube。

对面。That's what's giving us the abyspomal scaling。Having。The load scale like the popularity。

Is strictly a function of。The data can only originate at one place。

And if you just cared about the data。Just start going towards that place and as soon as you run into the data。

 okay， now you've got a copy， you're done with your distribution。🎼。

