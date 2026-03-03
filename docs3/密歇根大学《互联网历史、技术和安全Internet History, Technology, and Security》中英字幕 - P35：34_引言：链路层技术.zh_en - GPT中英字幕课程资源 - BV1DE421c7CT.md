# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P35：34_引言：链路层技术.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

Oh， oh hi， sorry， I was in the forums。I guess it's time for this week's video。小我。

This week we're moving from history to technology and in a sense we're going to tell the same story again you know we'll sort of start at the beginning but we're going to start from the bottom and work upward so since we're kind of talking about the same things but just from a more technical perspective don't worry you'll be fine we're not going to over there's no math I promise there's no programming don't worry about that so of course I appreciate IEE Computer magazine who I write for to let me use the articles that are associated with some of the videos as well as the folks from Open Michigan who have helped me so I to say。

No， hang out， got a phone call， I'll be right back。Okay。

 well that's been sent sorry for that interruption again I thank everybody for the use of the copyright materials part of my hidden agenda in this class is that you will be able to look at this XKCD comic and you'll understand the humor so I'm going to stop for a moment and let you look at it and see if you get the humor。

Okay， so maybe it did， maybe it didn't， but hopefully by the time we're done。

 we'll have a better chance of getting the human。So if you recall the most academics throughout the 60s。

70s and '80s， the best they had access to was this store and forward networking where you would send a message and it would go into a computer and it might sit for some time then it would find its way across a network and it would sit for a little while longer in hop and there's these multiple hops。

 we call these hops and each of these would be a couple hundred miles perhaps and to go from say Michigan to Stanford。

 there might be 15 or 20 hops， hops are is much defined by geography where we're all trying to optimize the cost of these long distance connections。

So the thing that really characterized St forward networking was that there wasn't a lot of sharing。

 one message was being sent across one of these links at a time and all the other messages just kind of waited in line。

Now that the innovation that happened。In the research networks in the '60s through the '80s。

Ultimately unbodied in the aRPpanet was the fact that they were going to be packet networks first how do we share one link so that a long message doesn't clog it up and how do we deal with outages more dynamically with the idea that eventually you could send a packet across the country and back into a computer and back out and maybe half of a second and that was seen as something to do rather than somewhere between 10 minutes and a day or two。

So how to do this efficiently， it was a research project and it was a research project that lasted almost 20 or 20 years and 20 or more years and one of the neatest things about this is they were able to throw it away and rewrite it a bunch of times so that they could put something in production。

 see its flaws， see what was good about it then they had the money from DARPA to throw it away and rewrite it。

 now by the late 1970s， it had you know 10- computers on it and here's a picture and these are not the schools。

 these are the computers， these are you know listing all of the computers that are there。

And so the engine， the innovation that they spent 20 years perfecting was the notion of packet switchishing。

 so how can we simply move data simultaneously across a connection and the essential brilliant idea is break the message into packets。

Again， to sort of review here I have a message and I have postcards that only can handle 10 characters and I'm going to send this hello。

 there have a nice day message to Daphne in California。And so I have three，10 character postcards。

 I basically put a from address and a two address on each postcard and a sequence number on each postcard。

 one， two， and three and I put 10 characters on each， and then I stick them in my mailbox。

 I just put them in， put the sign up， and then I wait。Now。

Let's just say you know that the post office person comes and picks this first one up and it goes to Chicago many from Michigan and then it goes to Omaha goes to Denver and then the second one kind of falls on the floor and it ends up going to Charlotte。

 North Carolina and then they're like why is this here and then they send it to Atlanta to get checked and then they make sure and this one goes and number three ends up going to St。

 Louis and then Tulsa and then Colorado and this one gets routed back to Charlotte because they weren't sure why they send it to them in the first place and then they send it to Memphis。

 Tennessee and then this one makes it to California and then this other one sort of goes to Phoenix and this one finally gets to Dallas。

 Texas and this other one goes finally and then this third one goes to Tucson。

 Arizona and then Las Vegas， Nevada and finally it makes it right so these poor little postcards that I put。

They have each a different journey right， It's a little adventure for each of the postcards that they go through and so。

We't I don't see how this works on my end， I put in three postcards I numbered them1， two3。

 but on the far end in California Daphne opens her mailbox and has scribbling all over a mailbox oh the shame no actually get rid of the scribbling so Daphne opens up her mailbox and she doesn't know how these packets got there IV postcards how they got there out comes the first one she goes oh it looks like I of got a message from Chuck。

 but I've only got part of it then out comes the second one shortly thereafter and then after a long period of time finally the third one comes out but it's actually the second one and now she understands that she's got the entire message and she reassesmbbles it in a way we go and so this is the basic notion of how all those postcards can share the infrastructure all they can all be in at the same time they can take different paths you don't have to connect them all together like trains basically。



![](img/3a92f2914bc0395079e4ef7f83653280_1.png)

And this led to a shared network infrastructure and so the computers that were in a storeor and forward network went from sort of big。

 powerful computers with disk drives to really tiny computers with a single purpose of forwarding packets rather than long-term storage of message and so the storing forward had long-term storage of messages is in the routers but I mean not in the routers and in the storing forward the old one。

 long-term storage was somewhere in the network， but this was only short term， shortterm storage。

 short-term storage， and so when a packet comes out。

 it simply has to find its way through a series of hops。

 it still hops and it's still connections but basically it has to find its way across the internet。

 and then we would take whole campuses like University of Michigan say or Stanford for example。

 and then we'd have sort of various kinds of local networks on those campuses and computers on the campuses and servers and various things。

And they would route all their packets， all their data out to the internet。

 and then the packets would find their way across the internet and then we might have a home connection as well that might connect and so the shared network infrastructure focuses only on packets。

 not reliability or anything else。So this notion of hops didn't go away as a matter of fact。

 I don't know how many hops it took to get from An Arbor to Palo Alto in using Binet。

I'm going to guess it might have been 16 or 20 and these days it takes 16 or 20 hops。

 the difference is in the internet， the 16 or 20 hops happens in 10th of a second or a tenth0th of a second。

So the notion of hops and the notion of intermediate computers is still present in the internet。

And the TCPIP networks that we use today。 And so your message sort of。

Geaves you the host that you're in。Hops to the first router and then hops to however many routers dot dot dot。

 this is more of a dot dot dot thing and then finally hops its way out to the far host and so this is sort of either your computer。

 maybe Stanford's web server and then there's this series of routers in the middle that it hops through。

Okay， and so the problem of。What data goes between here and here？

Is you got to solve a lot of problems right， how to all kinds of problems。

 and so in order to simplify the solution or break the solution into simpler， more manageable parts。

They came up with a layered network model Now this is a cartoon and computer people love drawing cartoons and saying this is our architecture。

 this is our framework， this is our approach， sometimes they're helpful。

 sometimes they're not helpful， sometimes the cartoon is just kind of a cartoon。

But what's usually being communicated in these kinds of pictures is they're taking a big problem and breaking it down into some subset some set of smaller problems。

 so the whole problem that they've got to solve of getting data reliability reliably across the whole country is that big and if we can break it into four pieces。

And work separately and come up with ways to let these pieces interact。Work separately with each one。

 then maybe we'll have a better solution。Okay， so take a problem that's so large and so complex that we might not be able to solve it and break it into four smaller problems。

Gives us a better chance of solving the four problems。

 Now there's a certain art to picking how you break the problem up and there's more than one network model。

 The one that we use in the Internet is the TCPI or Internet protocolto suite model。

 and we'll meet some of the people who designed that。

 There was also a model called the seven layer OSI model， open system interconnection model。

 So there's a model out there that has。one， two， three， four， five， six。

 seven layers and they all have names and they all have purposes and they all have definitions was not quite as this was not very popular and I doubt that it's many places because the TCPI model is the one that kind of one and so that's the one that we're going to study。

 but that doesn't mean that that has to be the only one。

 but it is the one that has become popular on the internet。

So once you break the problem down from a big problem into four small problems。

 you have to develop documents about how these layers work together。

 how various computers work together， how routers work， all these things。

And so early in the process of the development of the ARPE。

 they created an open process to build these specifications。

Where they would invite engineers from all kinds of companies and universities and who knows what any expertise to show up at a meeting several times a year。

 I mentioned the IETF meeting when I was talking about the history of the Internet and the Timberners Le off that only 15 people showed up to that's this meeting it's the Internet engineering task force which is just a bunch of engineers that get in a room。

 get in many rooms and solve a bunch of problems and so the standards that come out of this and you can go read them they're all open documents they're very throwback documents they've got this text thing and it's got is like。

Beautiful uppercase that reminds me of when back when printers didn't have lowercase。

 and these are documents that describe how most of the components of the internet work together。So。

The layered architecture that I just described。Where you have a computer。

 and then it sends data out the back of it and then hop， hop， hop， hop， hop through routers。

 and then the data rises at destination computer。And then the destination sends it back ands hop。

 hop， hop， hop， hop coming back and it comes to you， we're going to expand on this a little bit。

 so each of these hosts。On the two ends is going to expand to this much right here。

 so that's one host， that's another host， and each of these routers is going to expand into this。

So this bottom picture is just an expanded version of this upper picture so that we can see how the internet layers work together。

So when you send a message。In on your computer， this is all software， application， transport。

 internet link， so this is all software， and then it comes out the little plug on the back of your computer。

 right？So maybe your computer has a little plug like this on the back of it right that's an ethernet plug and here's an ethernet wire and Im plug my local area network in right and so this right here。

Is that right there that's kind of the plug， it might be Wifi， which means it's kind of like air。

 but if you have a wire like this， then it's a little more tangible and there's something on the other end of that wire。

This is a very short wire， but there would be a router on the other end of that wire。

The router takes the data off the wire and then forwards it， just like a post office。

 intermediate post office would do on to the next link。

Onto the next link and this would be multiple hops in here they're only showing two hops and then finally it's on the last link going to that computer at Stanford and then it goes up through these four layers of software and then goes and does whatever it's going to do now when they send you the response back it kind of goes the other way chop hop pop pop pop and back up and back to you So if this was you in a web browser you know and then here's me。

And here's a slide I've got right this web browser and you move in your cursor in the web browser is sending stuff back and forth to the Coursera servers kind of here。

 and that's what's happening right so if as we look at this picture over here。

This left column is the host you're coming from， the right column is the host you're going to。

 and the routers are these things in the middle， okay？ok。So let's start looking at all four layers。

 we are going to start at the bottom， at the link layer and then we're going to move up。

So if you recall， when I talked about the basic reason why we even have a layered architecture at all is to simplify the problem。

 to simplify the problem。 So the idea of the link layer is the link layer is a。

It all only worries about getting the data across one hop， right。

 Only worries about getting the data from across one piece of wire。

 What like voltage goes on these little wires and。How we send this stuff and if more than one computer is using the same wire。

 how do we share。It's a complex enough problem， but we don't worry about the whole world。

 we worry about this one link layer， and so the link layer is sort of like the connection。

Out of one computer and into another computer。And this might be fiber optic might be you know 40 miles or it might be 40 feet for all we know。

 but it's one link okay and then a router pulls it off that link and then forwards it onto another link if you go to the post office you could think of the person who picks your mail up from your house with the thing on their shoulder that's one link then they put it in a truck which takes it to a place that puts it in a semitruck and then they puts it to another place that puts it on a train and the semitruck and the train and the postman or postwo are these little link layers each person or semitruck is not taking it all the way。

 they're just getting a little farther so that's the link layer。

So the link layer doesn't worry about the rest of the stuff it really the stuff that is defined on this wire really doesn't even care if there's a worldwide web or anything its job is to get data across one f。

 that's what its job is is it up is it down how do we share it doesn't care it's got a very narrow view so what it means is we can zoom in on this problem right we can zoom in。

And focus and ignore everything else。So the link layer basically asks questions like， you know。

 I've got some data inside the computer and I want to send it out。How do I encapsulate it。

 what if this is shared， how do I deal with that， and common link technologies that we see are like ethernet or Wifi or cable modem。

 DSL， satellite or optical， these are all links， layers of one form or another。

So if you're going back to this ethernet link layer。

 which is one of our favorites because it's kind of ubiquitous。Other than wireless。

 it's probably Ether as the most ubiquitous link layer。So。

When the manufacturer builds an ethernet or a wireless adapter。They actually build into it。

 which is probably right here。ll be right here。They build into it a serial number。

 so they mark this as having a serial number。And you can actually whether on Windows or Mac。

 you can work your way down to find the serial number for your actual manufactured piece of equipment。

 so there's one on the Mac， that's an example one on the Mac and that's an example one on the PC。

They tend to be。6， two digit。Numbers concatenated together often with colons in this case。

 in windows it shows dashes。And so this is a raspberry pie and all the raspberry pies are going to actually have similar prefixes and then serial numbers within that prefix。

And so the raspberry pies get manufactured， they come out of the manufacturing line with this sequence number just kind of going ch took chug up up。

 up up up， and then they get shipped to all corners of the world。

And so these numbers are not the numbers for this to get across the world。 All the number。

 all these serial numbers at the link layer are good for is。

To get across one connection in case that connection is shared and if you were to plug this into a hub and you're plugging other computers into that same hub。

 well then you're sharing that connection and this computer might see the traffic for that other computer and so we use the physical addresses so that this computer knows which of the packets belong to it on the piece of water so wired ethernet or w-fi。

 certainly if you're sitting in a room with a bunch of Wi-fi computers， you're sharing the air。

 so you have to come up with rules how to share this， how to share nicely and how to behave。

So the way it works。Is。You could this ethernet could easily have a bunch of other computers hooked to it right。

 because it's really shared and so they're all sitting here and they're all talking simultaneously。

But we have a pair of computers that want to talk， so it's not just one it's got a bunch of folks sitting here。

Just draw a bunch of them， bunches of folks。They're all talking， or all potentially talking。

 and we got to figure out how in the shared medium like this is think of this as a hub and they're all connected into this hub。

 including the two we want to talk， they're all connected in the hub。

including the two that we want to talk， and how can these two make sure that the data goes is the data that's sent with the intention of going to this computer。

 this router， how can it make sure that it gets there， well。

 if it knows the address of the sending and receiving unit， it just encodes that in the packet。

And that way it sort of goes by all these folks。Let me change colors here。

The packet we send goes by all these folks and even if they all heard every one of the packets。

 they all know that it doesn't belong to them because they all have a different number and this is the only one that responds to it so that allows them to share the wireless or the wire and。

Share the wireless or the wire and have it all work out for them。So。

So that's the idea of the link layer now again， remember this might only be 50 feet or 50 yards or 50 meters well make it meters。

 it's only 50 meters， but you still have to share the network in that 50 meters。

And then the router takes it off of that and forwards it on a different link。

 and that's how we get across the country， but that's the next layer up and let's not worry about that for now。

 so the idea is，Think about one link， whether it's fiber optic or CA or wireless or WiF。

And so what are the kind of problems that you have to solve on this link layer？Well。

 so one of the things that's cool about many link layers is like wireless and Ethernet is they can be shared and it makes it really easy to just plug new computers in so you just sort of like here's a hub and you just plug another computer and it's on the network。

But they have to come up with a way to avoid the chaos when they're sharing。

And so the way Ethernet does this is with a technique called Carer sense media access with collision detection。

And as you'll see， a lot of the things that we do on the internet have a lot to do with courtesy。

Meaning that。We're just nice and if everybody's nice， it all works out。Kind of like driving in a car。

Everyone can't run through the stop sign at same time， so we've got to stop， got green light。

 your turn， my turn， whatever。This probably wouldn't work so well with cars because sometimes you do have a collision of packets。

 you just have to wait。Packet collisions don't crush your car they just slow your data down so here we go this is basically carrier sense media access with collision detection the first thing you do if you want to send some data。

Say we got some data inside our little computer when' I send it out。

 knowing that there might be other data going by， the first thing we do is we listen。

We listen to what's on there if it's not silent， we just wait until it goes silent and then we start sending so if someone's already using it。

 why crash into their data and crush their data because it's shared there's only one you can't both be sending it at the same time。

So first you listen。Once it's silent， you begin transmitting data。And then what you do is you also。

Listen to your own data and if your own data is coming back then it's sounding pretty good。

And then if there is a collision， because there's a chance that two computers will want to send at the same time and they'll collide。

 then what they have to do is back off and they have a sophisticated random number calculation so that they back off。

 not always the same amount， each computer backs off a different amount。

 and they make it so that it's fair so one computer's not always backing the most off so it's very fair。

 so it's when you detect a collision。You retransmit。After a random backup， first。

 you avoid collisions。 But in the， in the rare case that you have a collision， then you do this。

 And so。I want to introduce you to the person who invented。Ethernet。Ethernet。This is Robert Metcalf。

 and he was。Working at Xerox Palo Alto Research Center Park， everyone calls it Park。

And they had they were building what is most considered the first computer， the Alto computers。

 they were connecting line printers our fast printers to these Xerox was building the first。

Laser printers。And they needed something faster and so they just started building it and they built this thing called ethernet now it's a little different than the ethernet that we see the first ethernet that they built is a little different you can see a picture of it down here if you ever go to Xerox Park and get in you will go see this little museum they have it used a single piece of cable。

That ran along， they just ran it down the hallway and they would connect a tap in and then they would use that to send the data so it would go down the hallway and a tap would come out in each office and they were truly sharing the media This is not shared except when you plug it into a hub that's what makes this shared。

And it was inspired by an earlier wireless network where they were doing not collision detection but retransmission called Aloha。

 and a lot of early network packet network inspiration comes from the AloA net and come from University of Hawaii because。

They didn't have anything except wireless， but they did have wireless。

 they did a lot of really cool early research on wireless， and so let's go ahead and meet Bob Metcal。

 the inventor， one of the inventors of Ethernck。