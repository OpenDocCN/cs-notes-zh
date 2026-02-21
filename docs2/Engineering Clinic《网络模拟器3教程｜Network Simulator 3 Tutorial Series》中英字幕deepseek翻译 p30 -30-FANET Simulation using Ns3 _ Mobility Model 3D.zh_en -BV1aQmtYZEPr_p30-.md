# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p30 -30-FANET Simulation using Ns3 _ Mobility Model 3D.zh_en -BV1aQmtYZEPr_p30-

Hi， friends。 welcomelcome to engineeringer Clinic。This is Dr Praip Kumar。 So in this session。

 we are going to see。Flying attack nines。Using industry。

So we are going to simulate this flying attack networks。

 so we have heard about so many things like magnets。Vans， and now we call it as fence。

So now this is what we are going to see。So the main purpose here is we are going to use the existing mobility models。

For three dimensionsal mobility models。So， 3D mobility models。

So one such mobility model is implemented in NS3 is called us。Gas Markco mobility model。

So it comes with N S3。So this model only we are going to deploy and we are going to use。

Playing a dark simulation in NSS3。So what I do is I have taken a source code like this。

 so first let me explain you with the source code。So what my source code contains。

 I will explain to you。And so if you want to know line by line source code。

 you can just refer my other videos， firstcc， secondcc and thirdcc。Explanation。

 I will give it in the description description link also you can able to check it check those links。

Now in this case， I will just explain you， so we have totally have 20 nodes here。

 so 20 wireless nodes。And wfi helper we have a wfi object the standard of 802。11 b。

 so we have ABg and letterra there are so many models available so we are going to use a Mac standard up80211 b in case if you want to use yen also can use even the latest one wfi 6 also you can use so the list are。

H211 year is supported H211 b is supported H211 year is supported H211 A D CSE supported H211 ya x is also supported。

So apart from that in Yenan D， we have two things 2。4 gigahertz。

And P gear has also both are been supported here。 So industry3 supports all these stuffs。

For this w5 physical layer standard， you can use it in case if you want to use y 802。

11 p also supported this is for veh networks。So we call vs。 It's called this view。

Wireless access in vehicular environment， that's what we call as wavess。

So this out the way this helper class is supported， so NQ O is no longer available in NS3。31。

 so we will just remove this NQ helper。And。Ill create a simple object here。So， this is the Mac。

So we have a simple Wifi Mac helper Mac。So then we have adc bypha math。

 so in this we have again various things called us adc bypha math。Then we have it is D。飞 mac。

你 have粤B为飞。So NSS3 supports this kind of Mac so Addag Wifi Mac is the Mac with all the nodes are in Adac mode they can able to form the network so this only we are going to use for flying a networks because when the nodes are flying in the cable of the ground so they will be talking to each other through without any interceptor so A5F Mac means we need to have a router for handling it。

 station Wifi Mac is also similar like ada Wifi Mac but。

It will be used in the ground so with the antler will be pointing towards the ground so that is how the way this station device format will work。

Okay so now we have this remote station manager so consent rate byfi manager so all of them will have a consent rate byfi manager so there we have a data mode so we have a data 54 MBPS so the B standard supports 54 MBps a maximum so even if you want to have O MBmbps if you want to have1 MBps we can able to set that so NSS3 have the support for all these six。

Then we have a physical aid helper or Y means。Hit another network simulateim。

Then we have a channel so in this channel we have two things propagation last model and propagation delay model。

 so constant speed propagation delay model and first propagation loss model if you are from electronics background you can refer the documentation of these two source codes。

Proagation loss and propagation delay models。Then we are creating a channel。

 so these are all channel properties， so once we create the channel its a communication path is established。

Then the net device container。 So the networking device。

 So it is it is a hardware and software combination of。You are a networking device。

 so we are installing this on the physical layer of Wifi， PHY。Then Mac。

 it is a Mac wfi Mac helper and C is the number of node。

 so we can call it C dark so C is the number of notes， so this is what we are doing。

And enabling A rout on all backbone node， So we are going to have enable AW protocol。

So YW protocol is being used。For finance as well so in our examples we are we are going to use finance here。

 so thats how the way the AW protocol be so we can use other protocol as well like DSR OLSR DSTV all these protocols also we can use it but in this example we are going to use only AODV。

Then we have a routing helper A DV and internet at install C。

 so we can install it on the all D node Cs number of nodes node containers。

 so totally 20 node it install。Then we are setting the addresses for each and every node 192160。

0 and the masking address is this and creating a asing this address to all the devices C devices C devices means so what are the networking devices for all the devices so we are installing these addresses here。

Now comes the mobility model， So this is where the mobility model。

Mobility model so what it is given here is a 2D mobility model I will show you two two things first thing I run with this existing model then Ill change it to gas markco mobility model Okay so now in this case what happens is we have a position allocateator so this is a 2D mentals mobility model 2D mobility model。

So here mobility helper mobility and we have a position allocator so in the position allocator we have the minimum x minimum y and delta is a change in x and change in y the grid width is2 and row first the name of the mobility model is random of two dimensional mobility model so we have a value of x and y that is minus 1000。

us 100。 So this is the how this is how the way the accent way works。 So maybe if you feel。

 for example， minus100 comm 100。Thiss one x away。This is on the x axis， for example。

 under the y axis we have so lets say in the x axis when we what we can see is so this is the center for example if this is 0。

So， this side will be。Minus0 so this are the way the minus 00 box and the other side we have a place under so similarly in the y axis is also we can have a minus0 on this side and sorry plus under on this side and minus0 on this side so that means the node can move in direction from left to right so thats how the way we are just planning it here okay so this is what the two dimension but we are making to running three dimensionals is it axis also we are going to run so that is what we will be seeing it。

Then mobility that itself So install this mobility pattern in all the nodes。

 So there is all the nodes and the application， but we are going to use UDP packets。

 So the port number is number nine we are starting the。

Second are1 and 10 and the first node get0 receiver get zero means this is a number of nodes get0 and the first to node the0 node will be the server and the client will be the first to node okay so on the this thing and we are enabling the packet capture so this is how the way things run so we will see the graphical user also so network animation also will include so first let me include the code for network animation。

So here we have a include NSs3 in attanim module doth。

 so already it is included so we have to include this。And when I come here， I will just include。

Animation。Interface。Hning， so the name is finite。I had example， dot example。

 So this is an example file。I am just including fanex dot Xml。

 So this is a file that we are going to create。 So this is what。Let' go honeyで。调先 net pen。

So the following。Now I need to create a askI trace file also， so in that case。As key dry help。

the name of the object object， I want to give it as ask。

So this ST sper will be tra the physical air type so in this we have a physical errors wfi PA。

So just copy this variable。And then we can use dot。Enable has key， So enable。

The ASI for this50 P so you the ASI cannot be enabled for all the things since the physical layer is a channel so we can able to create the ASI so then ASI dot。

Create file stream。So the name of the file， I want to give it as valid it。X do T。So this that。

TSo I have just enabled the haske risk matrix。Ask this matrix。Can be processed using。

Trace matrix software。Trasme software so this is the way we can able to use this so so in this example we have seen a simple example so if you want to know more about the entire coding you can refer to the first three videos first startcc second artcc and third artcc so you can understand better about the line be understanding of the code okay。

So after it is done， let me run this example。So I open the terminal。



![](img/e52b11bfc23a9e9e158786b405dcc0c0_1.png)

![](img/e52b11bfc23a9e9e158786b405dcc0c0_2.png)

So let me store this file in save us。File， save us are you stored in the scratch folder。No loads。

N S 3。31 scratch。

![](img/e52b11bfc23a9e9e158786b405dcc0c0_4.png)

In this scratch， I store it as wfiev docc then supply L storing。

Now we will be running it Cd in a solid one， Cd and a 3。31。Dot slash w， double a and run， scratch。

So once I run this。So for no errors。 So no errors are there。

 So now we can see we have this second these things。



![](img/e52b11bfc23a9e9e158786b405dcc0c0_6.png)

Here， just check it， check the code here。Here we have the enable Pack capture。

 so this is a wire shot Pack capture。So packet capture is enabled。

 So that's why all the file names coming with second。 So let me use wfi。So， I use fannet。E。

 so wherever it comes， I will change it to finite E X。 Okay， so now we will be running it again。



![](img/e52b11bfc23a9e9e158786b405dcc0c0_8.png)

So let me delete everything for。Start our Pcap。 Let me delete all the Pcap files。

 So now we don't have any packet capture file。 Now I will be running it。



![](img/e52b11bfc23a9e9e158786b405dcc0c0_10.png)

Okay so now we can check it so we can see all the finite110，120，30 like then make out the phase。

 So because we are enabling the packet capture for。

This wfi PHy as well as we have enabled the packet capture for this ASI for wfi PH。

 so in the wfi PHY。Between node 1120220 that20 because 0 is a server so all the claims how they interact with the server so that's how the way these packets are being generated okay so now what I do is。

I'll just show you any one of these file， so let me use10 here。Its a wire sha。And then。

And it text hyp11， hyp0 thatca。So you can see this is the Yshck file that what we got it here。

And you can see the statistics here， So what is a hi graph， So how the graph performs。

Packets per second。 How many packets per second at what timing。

So this will be listed out here so you can able to check the packet level analysis here so what happens to UDP packet IP version 4 logic packet then P layer so all these steps you can able to check it here using this and there are so many other information as well you can able to check the complete summary of all these things。

Okay， so this is on。W sha till we go to the animation So in the animation we have。你丹 name。This。

 I'll open it。The name of the file is finite x dot xml， so finite x over。

SoSo far we are not doing any finite here we are just doing only。And note number okay。

 I' will make the notes to size 2 this。Then， I'll run it。

So you can see that 20 nodes are moving here and there according to their。Distance。Okay。

 so that's all the way。The notes are moving。Canada。

So this is a simple animation that we can able to see， and we can able to check the。Aski file also。

 so J it。烦 it。な啲啊。So this is the S key phase so this is SI trace what we got so here in the S trace the first command is a t means it transmission。

A means receiving。Plus means Cn Q minus means in Dq。So D mean drop， So that's out the way。

The packets are exchanged between these notes。Okay， so this can be processed using trash matrix。

 but trace matrix may not support all the protocols what we get it。

 It will support only some list of protocols。 So accordingly， the trace matrix will work out。

 So this is on。A simple two dimensional，3D model。 Okay， so now in the same case。

 I am going to use three dimension here。Okay， so let me use Google for that so that you can also easily can able to do。

 So gas Markco model。Induly。I it right。So we have a gas Marco mobility model in N3 somewhere here。

Andです。这问题 yeah。So this reference， you go to the Ga Markco mobility model。

So there we have a given an example here， So this is an example here。

 So from here to here I will just copy it here So if you want。can。

 if you are doing some research on flying attack networks are mobility models。

You can able to try this page and there are so many other relevant pages as for three dimensional mobility model so this is the only protocol in NSS3 only mobility model in NS3 that supports three dimension is gas Marco mobility model Now what I do is in this example Ill go to the mobility model code here。

Okay， so first what I do is I just make to comment。I'll just comment and note from here。

Ive guilt here。 so now other is Ill be using。Mobility model。这里。Can' 3D here。

So this is 3D model and paste it here。So I just pasted it here so the following is the 3D mobility model so you can see that the mobility model mobility helper mobility the same variable name please use the same variable name whatever mentioned here else will have a confusion I' will show you that also。

So set mobility model N S3 gas Margo mobility model see the bounds， so bound box value。

 so it is something like a three dimensional box， so0 to one like 50000 means around。

Thousand00 kilometers， so that' is what the box here。

 So let us go with a simple thing called this 10 meters，0 to 100 meters。H00 meters。

So x axis is 0 or x is 0 and these x 0 in case if you want， you can have this also。Minus unders。

 you can have minus under to 100。So let me go with0， so let's have the starting origin as 0。

So time step is every time step point5 seconds alpha， so based on this parabolic I mean。

 probability value only the mobility， the nodes are moving。

And mean velocity is minimum is 800 and maximum is 200 so this also you can able to change the minimum velocity to a lesser value as well direction so direction is minimum0 maximum 6。

2 this also direction so you can able to refer the complete theory behind this grossmer co mobility model then mean pitch so when the nodes are moving so in what pitch they will be moving so minimum and maximum the pitch is given as a constant 0 and05 so this also if you want it can vary then normal velocity normal direction and normal pitch so this is in average and this is the normal so in the normal we have random variable so starting from 0 the variance and the bound so bound is 0。

4 and based on the variance。The value will be adjusted， so this is the way the normal pitch workss。

So next thing is probably a position alligator， so how the position of the north will be placed so again we have maximum00。

Here it is 10， and here also it is0。So hunter class under class under we can see the cuboid we called as a cuid where all seat are equal to 10 meters so that means it is something like a three dimensionsal box within the box that drones the unmanned a vehicles the node of the flying a box are just flying。

Okay， so un mobility install Wifi station node， so that's what the station node。

 so we will use the variable name see here。Okay， because we are using the C is the number of nodes here。

Okay， so now the packets will change it here， so finalex。Gss， I will use fan gas Similarlyly。

 I can use。Gas， and I can use some gas here。Okay， so I have got these three three names just renamed so finite gas finite example finite example refers to 2D and finite gas ofverse 3 d or let be use 3D rather than it will be better to understand。

Fannet 3 d， So the LA re is finite 2 d in。It's not finite the simple manners。Okay， fine。

 So now Ill be running this example again。So when I compile this example you might be getting some errors as well okay so no errors。

 so that means I program comp successfully now we can see fan 3D。Okay。

 so now final x also there in P capture and the final 3 d also there in packet capture now I use the same thing here final 3 d10。

So where answer are。系咧。3D hyp，1 hyp0 dot bigcap。So once you have this。

 you just go to the statistics here， igraph。So you can see that after time4 it was completely。系啊。

It is one only so number of packets per second is simply simply one and total this also is simply。

 but when there whereas in this case I will open one more window。



![](img/e52b11bfc23a9e9e158786b405dcc0c0_12.png)

W shift。Fnet V X， hyphen 1， hyp0， not pick。

![](img/e52b11bfc23a9e9e158786b405dcc0c0_14.png)

Now we can see here these statistics involves it is both same only。

 but only thing is the mobility model is changed。So now we can see that at time number7 time minutes。

 it was different。 So this mobility model have a。roll on this packet。

 so it is only one packet after repeated up this concern because the notes are flying in three dimension but in this case the notes are flying into dimension are not playing the notes are moving into dimension。

Whereas in the 3D model， it is just flying across。So this other the way it works。

 So now I'll just close this。 So let me go and open this in the。ネタねそネね。

So the net an will just open this file。Fannet 3D direct symbol yeah。So slightly different here。

 so let me use not familiar not about1 so ten so you see that they are just scattered in 3 d models。

And I'll remove the node ID。You can see so they are just flying here and there。

 so according to the random position model， so the speed also differs from 8100 to200 meters per second。

So it is a very huge speed， but in case if you want to adjust the speed， you can able adjust it。

So even you can see the statistics or statistics of the each and every node。

 the node IP is also you can see。Yeah， now the simulation over。

 sos have given only 10 seconds the simulation gets over。Okay， so similarly。

 the packet capture will give you the more information， and I'll show you the。Fannet 3D dot ti。

 the trace file also。 So this is a trace file。What we got is a trace file。

 so you can see the number of lines。The trace fell somewhere around this。

Two not three lines the same way。They have this planet yicks。In the final case。

 it is around2 not8 lines， so this2 or3 and2 not8 lines。

And the various packets have been used in the same way。

 but only thing is the statistics might be changing in the。White shark。

 so white shark may have a major difference here。Maybe I'll just show you some more thing 110 Hphone0 in Pcapap。

So the statistics can I see。So this how the way it works so one packet per second then two packets per second and it goes like this and not only that we can see other statistics as well。

 for example， packet length。So what are the different packet lengths here。

 so totally 10 packets from packet size of 82 and 59。So， this comes here。And。We have。

Protoal hierarchy so what are the different protocol hierarchy also so how many percentage of weights。

 how many bits per second for each and every protocol so what is used in the particular。不决定。

So we can able to analyze so many other information as well。

 but you just refer the documentation of IShar to get more details on this particular health so the purpose of this example is just to show you how it works in。

3 dimensional mobility model，So then the trace will also done。And。So in future。

 we will have the another thing called us。Using OpenStet map。Open street。Sumo already。

 we have a sumo。 So banners。 So banners we already have。 So that means if we use。

3D model in the vanex it becomes planets。 So flyinging cars。

 that's what we call us flying car simulation。So this also， we can able to try。

 but we need more time to simulate。This kind of networks so this other way we can able to do the simulation here so in future we will be doing this kind of simulation also in our here in my YouTube channel here。

So now in this example， I have just explained to you about the gas marker mobility model。

So thanks for watching and thanks for listening if you want to plot any characteristics graphs using flow metrics all these things you just please refer my other videos relevant to NSS3 tutorials in my channel there are more than 25 video access available that categors all the performance metrics all the graphical tools。

 all the performance tools are available for plot。And please subscribe to my channel and share it to your friends。

 so thank you。 Thanks for watching。

![](img/e52b11bfc23a9e9e158786b405dcc0c0_16.png)