# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p29 p28 Week 05, Segment 5 - The Physical Internet -BV11QQcYmEzD_p29-

Hello and welcome back to CS615 System Administration。 This is week 5 segment 5。

 and we're going to be talking about a few of the physical aspects of the internet。

We saw in the last video that there's a logistical component of the Internet。

 There's a nonprofit governance body for at least some aspects of it。

 And we also noted that theres a geographical division。

Certain I spaces allocated to specific geographical regions。 Now。

 this has necessarily political implications。 And we get back to those a bit later。

 But having moved on from the abstract structure of I packets to how addresses are allocated。

 Let's now take a look at just how packets flow。 by that， we don't mean how do we route packets。

 although that's also interesting and relevant and something we'll discuss in the future。

 But we actually mean how does a packet get from A to B physically。

So we'll start down here at the bottom of the stack。Now， if you have a point to point link。

 then it's rather obvious what path the packetet takes。 Packs go in here。 Packets come out there。

 You can follow the physical cable from one end to the other。



![](img/fd8c142678af11f962962e81a009caa4_1.png)

![](img/fd8c142678af11f962962e81a009caa4_2.png)

Even if you're talking communications between your laptop and your WiF access point。

 it's still reasonably easy to understand the connection。

Once the packet arrives at the access point and then goes into the cable and then from there。

 it is delivered from your ISP to some switch port in a machine room or data center somewhere。

Where let's say the packets enter the matrix。At this point。

 most people start to lose the overview of what's going on。

 even CS majors may only have an abstract idea of what the internet looks like at this level。

And claiming that it's a series of tubes is really not that terrible an analogy as people like ridicule it to be After all。

 we are hooking up cables here and there and packets flow through them taking turns。

 being redirected and so on。But the internet is a global network。

 it's easy enough to imagine physical cables being run across the country between buildings。

 and you can of course correlate a lot of the data flow with population。

 which is why most of the action does happen just exactly where you see lights here on this image from NASA。

But now let's think about where we find the largest spots of concentration here。

And just how are we going to get our packets from here to there？

But it turns out that it's not really a new problem。

 We've been trying to get communications between the continents for hundreds of years now。



![](img/fd8c142678af11f962962e81a009caa4_4.png)

In fact， we've been doing that since the 1850s when people first started stringing really long cables across the ocean floor to enable telegraph communication between America and Europe。

And just like back then。We still do just that， which I find fascinating。

 That is We're actually running these long， long cables from one country to the other by dropping them on the ocean floor。

 using these huge， special purpose ships that have thousands of kilore of network cables rolled up in these huge coils and which are buried on the ocean floor with special submarine cable plows。

😊，But they're not always buried， sometimes they are just left on the ocean floor。

 but yeah that's what we did。It's simultaneously high tech and yet still obviously simple。

 a really long cable。And this is one of those physical aspects of the internet that is useful to keep in mind because there are a number of implications。

On the one hand， you can't possibly get a faster network connection than well。

 with a distance of roughly 5800 kilometers between New York and Paris and the speed of light being almost 300。

00 kilometers per second means that a launch of packet cannot possibly be faster than 40 milliseconds though of course theres some overhead and we haven't quite reached pure light speed between any two points。

But anyway， so we've been stringing cables between countries。

 cables known as the submarine Internet cables。 They are operated by different companies。

 including communications providers， as well as some of the Internet giants。This website here。

 submarinecablemap。com， allows you to zoom in and inspect all the various cables。

 which is really interesting。But think about what it means running a cable on the ocean floor。

 There's all sorts of things that can go wrong with a network cable just sitting there， right。

One thing that's pretty interesting here is that of course these cables carry electrical signals。

 and many animals have pretty acute electrical sensors。

So it's really no surprise that they will every now and then get curious about what this long string on the ocean floor is all about。

And there have been cables that were damaged by curious sharks。

 because when you're a shark and you send something of interest， What are you going to do。

 You take a nibble to see just whether or not you should eat the thing。 You know， might be tasty。

But you know what else can happen when you have a cable set out there in the open。Well。

 think about where the cables are run。As we can see。

 these submarine cables are not only out in the open ocean。

 but oftentimes are closely hugging the coastlines。

 but theres a lot of industrial ships carrying cargo。

 and what do ships do when they are waiting outside the city's harbor。They throw their anchor down。

 which scrapes across the ocean floor to keep the boat from moving。

And such an anchor may actually cut the internet cables by accident。

 which in turn may lead to significant internet outages。

But let's take a closer look at some of these cables here。As you can tell。

 there's quite a lot of them。Let's pick。This one here。😔，Half through AEC2， which connects Denmark。

 Norway and Ireland to the United States， an almost 8000 long cable run by a consortium。

 including Facebook and Google， able to carry 18ter per second。

The lending point in the US is right around the corner from Stevens in the illustrious。Wall Township。

 New Jersey， run by the New Jersey fiberber Exchange or NJFX， where several cables land。

The confluence 1 cable running down the East Coast， for example。As well as the Seabs 1 cable。

 which goes all the way down to Brazil， over 10，000 kilometers in length。

Over here on the other side of the US， we have cables crossing the Pacific Ocean。

 such as the Japan US cable。Which makes a puts stop in Hawaii。Then over here。In Karachi， Pakistan。

 we see the Southeast Asia， Middle East， Western Europe cables。Which one from Singapore to France。

And which in a major global internet knowledge taking place in 2008 were accidentally cut。

 leading to several countries at least partially losing internet connectivity。So as you can tell。

 there's a significant risk of severe impact if these major communication lines are disrupted。

 whether by accident。Or by intent。Now of course you may have heard this quote by John Gilmore。

 that net interprets censorship as damaged and rods around it。

Whit tends to stress the benefits of the by and large distributed nature of the internet。

 but unfortunately， this is not entirely true。That is。

 if you are committed in a position of significant power and willing to accept the consequences。

 then you certainly can censor or disrupt the internet for a large portion of your citizens。

 and dictators and authoritarian governments have been increasingly making use of their powers here。

As I'm sure you're aware， people in power are quite afraid of the common people's ability to communicate freely。

 and so the internet necessarily represents a great threat to them。

Whenever there's a revolt in uprising or political upheaval。

 you can bet that the government in power will try their best to suppress the people's ability to communicate with one another。

Just yesterday there was an example of Myanmar cutting off its people from the internet amidst the public protests of the Kuratar by the Myanmar military in February。

What you see here is a graph of the average network connectivity in Myanmar。Since early February。

 the local ISPs had been ordered by the military to block Facebook amongst other sides。

 with increasing blocks since then。And this is not a rare occurrence every day governments are willing to pull the plug and cut off their own people off the internet。

 such as Iran in 2019， when the Supreme National Security Council ordered a complete blackout during the ongoing protest there at the time。

 which was one of the biggest complete shutdowns for a large country like Iran。

But it's not just authoritarian countries like these。



![](img/fd8c142678af11f962962e81a009caa4_6.png)

India， the world's most populous democracy， is currently the sad leader in the number of internet shutdowns。

 where the government frequently orders parts of the Internet to be turned off or restricted。

India holds a sad record of having imposed the longest shuttle in history。

 when the Jamu and Kashmir regions were put into a preemptive lockdown。

Which after six months incurred a cost of over $2。4 billion and half a million jobs。

 illustrating that access to the internet at this point really is a basic human right that governments are unfortunately increasingly willing and still able to restrict that will。

If you control the legal entities in charge of physically moving packets back and forth。

 you can restrict people's access。But such power does not media extent to a binary on or off state of the internet。

Rather， you are able to access all of the communications flowing through the physical devices that you control。

And so if you have the legal power to force even a private enterprise to eavesdrop a all packet zipping by。

 then it's no surprise that governments like that of the United States also do this。

What you see here is room 641 a， a secret network closet and AT&T's SBC communicationications building in San Francisco。

Or rather， it was secret until an employee at AT&T noticed that for some reason there was this locked room that apparently all network traffic was mirrored in。



![](img/fd8c142678af11f962962e81a009caa4_8.png)

The employee who noticed this was Mark Klein， who then became a whistleblower。

 alerting the public with the fact that the US government performed warrantless spying on not only global communications。

 as just about any large intelligence agency does， but also why attempt and data mindd US citizens' communications。

And all of this is to once more iterate the point that no matter how much we may focus on bits and bytes and software and system administration at the end of the day。

 we are still all operating on layer 9 up here。All the work we do is inherently political。

 Work on the Internet enables or prohibits the free flow of information。

 connectivity and routing and network protocol design all must take into account accidental or intentional abuse。

 we must understand the impact and abilities of powerful actors。 such as your own government。

 And as Mark Kin showed， at times， we must make difficult decisions with consideration of the political impact above that of your job security。

Because even if we don't ourselves run the cables between different jurisdictions。

 the physical aspects of the internet remain an never present factor in our work。

We'll pick up the ethical dilemmas we may encounter in our line of work in future videos。

 Then in our next segment we'll look a bit more at network ownership and how we can see the political structure of the physical internet。

Until then， please make sure to check out the various links included in the slides。

 read up on the various internet outs， and perhaps research some of the other major disruptive events on the internet。

I'm sure you'll find a lot of interesting information that perhaps so far you hadn't considered in much detail。

 and perhaps you begin to see the internet as a more tangible physical thing。Thanks for watching。

 See you next time， cheer。