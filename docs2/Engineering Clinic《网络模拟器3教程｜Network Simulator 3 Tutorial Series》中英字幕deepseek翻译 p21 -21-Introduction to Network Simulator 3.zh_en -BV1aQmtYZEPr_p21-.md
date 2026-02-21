# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p21 -21-Introduction to Network Simulator 3.zh_en -BV1aQmtYZEPr_p21-

Hi， Leers， welcome to elements of network simulation。So this is a big two lecture。

So hope you have enjoyed the big one lectures。So now we are good inside the network simulations。

 So by way we need a simulator on what is the purpose and。They see what is。

The introduction of network simulator 3， What are its tools So in this week we will be considering mainly on the network simulator part。



![](img/8a0d4b236b8363420410532251087606_1.png)

So。The industry3 simulator is a discrete even simulator。 So discrete even meanss。

 the number of events will be discrete。So that's why we call us a discretereet even simulator。

It is targeted primarily for research and educational use。

 so it is mainly considered for research and educational purpose。

Because most of the corporates before investing huge amount of money on the networking devices and the equipment。

 they first upfront they just try to simulate the network later on based on the successful rate so they might procure。

The actual experiments。 So thats how the discretere even simulators are very helpful。

 So earlier we were having two simulators in N S2 and now we have N S3。 So N S2 was there since 1998。

And the last version was up to 2011。 So now after 2011 there is no version in Ns2。

 so we just go for Ns3 So in the entire course so you can able to know more about Ns3。



![](img/8a0d4b236b8363420410532251087606_3.png)

![](img/8a0d4b236b8363420410532251087606_4.png)

So the main advantage here is it is free as well as open source。

 so is is completely open source you are free to use。

 we are free to modify anything and you can free to supply to the code base of fitness3 also。

But industry is not a backward competitive election from industry。

 as you say that the version number 4 and version number 5。 So it is not like that。

So version number 4， version number 5。So。Ins tree is not backward compared in us， too。

It is a new simulator。 Some models from N2 have already been。Pored from N 2 to N 3。

 So some of the models which are they did not redesign or recordcode this N 3 for their purpose。

 they just simply reuse the source source code from N 2。 So that's how this。



![](img/8a0d4b236b8363420410532251087606_6.png)

N S3 was evolved older。

![](img/8a0d4b236b8363420410532251087606_8.png)

So。Ins3 is designed a set of libraries that can be combined together also with other external software libraries。

 so industry3 is not a standalone software along with this NS3 software we are so many other tools also third party tools also included in the simulation。

Several external animators and data analysis visualization tools can be used with N S3。However。

 Hu should expect to watercut the command line and with c plus+ and Python software development tools。

 So the prerequisite for this course will be another prerequisite so you can learn so by C plus plus and Python。

So mainly we will consider mainly at the C++ because Python there are different set of libraries are there so we will mainly consider this c++ because the code base on the support is very huge in C++ particularly for NS3 but for data analysis and visualization we might use Python frequently but the students should also be working on the terminal mode so they should be wellvis in command line mode so maybe you can during this V2 lecture you can refer some of my。

L based lectures。In our course so that you can get a better understanding of how to use the command based operations so industry is primarily used on Linux systems as I already point out that we need to use Linux so thats why I have given you a Vm image also virtual image also for you in case if you want to configure it for Macwise you can configure it but you need to have the X to be installed there。

As well as you need to you cannot use Windows because still for visual studio。

 still the support is being developed， but as of now nobody will know none of them have succeeded in deploy NS3 for Windows so either you can use Macwis or you can use Linux systems so we suggest you to use Linux systems for the。

Greatter support and bug3 operations in NS3 and finally NS3 is not an officially supported software product of any company。

 so no company maintains any officially supported software it is of an organization that is helping in developing this NS3 software。



![](img/8a0d4b236b8363420410532251087606_10.png)

![](img/8a0d4b236b8363420410532251087606_11.png)

![](img/8a0d4b236b8363420410532251087606_12.png)

So now what are the tools we might be learning so these are some of the tools that we are sure to learn in this course but what are the tools is G plot for plotting the characteristics where else are for packet capture so it is for plotting any characteristics。

So the wires are for packet capture。As the name says Netime is network animation trace metrics for processing the ASI trace。

 So ASI trace will format， it will be processing it。

Then flow monitor is to monitor the flow of packets。 So this is， again。

 a powerful tool of industry3 so we can able to。Find out how various flows and what is a packet loss packet transmission rate receiving rate and all these steps we can find out and visual laser is another network animation less similar like an atanium so we have two different kinds of visual laser and animation is are available apart from that we'll be learning some more software like escapecade arrays and we can packet capture Pcap so there are so many other things also we be learning in this course。

And now we will come to N3 abstractions。 So what are the different abstractions So before we go to any network simulator So they will be giving an Apa so based on this Apa we have a turn of algorithms。

 So main advantage days here is most of the simulators they give a source code。Complete source code。

 they give free。 So complete source code you one might get。In the industry in any。Network simulator。

 So in this also they will give so many complete so many source code for so many algorithms。

 protocols， packets， cues network elements for all these things they will be giving a source code。

 So based on this source code， we can understand we can modify and then we can redessign anything we can do。

 or if you want to start from scratch that we want to a new protocol right from the scratch it is possible to develop。

Could there all this NS S3 abstracts。We consider and there are five different kinds of classes have been implemented in93。

 so one is node。Application channel， net device and topology helpers。

 So the end NS S library will be entire NS3 library will be categorized in this five。Obtractions。

 So we see only one， what is member node， what is when channel， What is， What is application。

And what is my aology Her。So now first thing is a node so node is a basic computing device of NSs3。

 so that means that it is a basic computing device so as you say a computer。

 so simply we call a node as a computer。Similarly， how a computer what computer behaviors。

 the same thing will be applicable for the node also name of the C plus plus classes is node。

 so usually we can create a node using the node class so that we can able to see so we have a class in in a three colors node container。

So that means it's a con， it's a container。 It contains so many nodes like this。

 So this how we can able to。Okay so the name of the glasses is node is like a computer which can be added with peripherals。

 applications， protocol sets and drivers to do useful Similarlyly。

 a node of NSS3 can be equated to a computer。They can be attached with the peripherals applications。

 protocol sexs and drivers。 So thats what this node。



![](img/8a0d4b236b8363420410532251087606_14.png)

Next it is application So industry3 applications run on the NS3 nodes to drive simulation in the simulator world。

 So that we said we have a node。And we need to have an application here。 So this。

 let's say this is a node and this is an application。

 So what kind of application I can run on these forms。

 So that's what here N S3 nodes to drive simulations in the simulator world。

 these applications run over it。Okay， so for example， we can use TP application。

 or we can use U DP application， or we can use a co。There are so many and aco land equal。

 There are so many obligations we can never think of。So。

 you can see this here the name of the abstraction classes application here。

 so one good example here is UDP Eco client application is one and UDP Eco server application is one。

So that means a client that the server will be there。

 There are some servers other the client will be sending a packet here。한 우샌겐 바겠어요。

So it's an echo packet。 So how the clients are receiving the packets from this server。

 that's what they say。So the echo server will be allocated to this node。

 whereas echo client application is sent to these two nodes。So that means， this is how the way。

The simulated world will be。Simulating the particular network。 So that means any network， any node。

 if you want to consider particular echo server calculate， we can able to do that。



![](img/8a0d4b236b8363420410532251087606_16.png)

So next thing is channel。 So channel， you know the communication channel。

 So simply we call the communication path is nothing but a channel between two different notess。

Between two different nodes。 So what kind of communication is possible。 So either it can be。

line to rank camera1 point to point connection P2 P we can say switch or a hub connection。

 So we call it a cMA or it could be completely wireless so that means wireless。

So these are the different possible of channels。 So in the real world what what is in a channel one can connect to a computer to a network。

 often the media over which data flows in these networks are call us channels So channels mean its a medium so in what through what medium the data is transmitted whether it have a wide medium or wide medium in wide medium which was a different medium fiber opttake ethernet。

And P2 P， there are so many options and wireless means specify what kind of medium access control it not 2。

118 not 2。15。4 whether it could be a wfi or Bluetooth or Ymax， so that is what we define channel。

So in the N3 what wines one connects a node to an object representing a communication channel here the basic communication sub word abstract is call as a channel and the presented by a C plus plus class call channel so we represent it with a class name call channel so one example you can see we have CSM channel。

We have point to point channel， and we have a E channel。

 So that means that the channel means the communication part of network。We call CSM S。

 So CSMM is carries sense multiple axis。Point to point means between two different nodes I want to just connect a single line so that both of them can able to communicate with each other CM channel means it is something like this so the nodes are connected to a common bus So this is CSsM channel we can say so in this all the nodes are connected to this and this channel is allocated herefi means completely wireless so there are so many nodes and there is a node So all the nodes are wireless so we have a wireless area and this will be connected to the Wifi channel so this is how the way the channel is model does。



![](img/8a0d4b236b8363420410532251087606_18.png)

In C plus plus class in inner3。Next thing is net device。 So net device。

 So net device is a combination of software plus hardware software。差吧。

So that's what the net device will do。 So net device means one。

So usually what happens is in any computer。If you want to connect enet， there will be a N card。

 So the N card will be network interface cards。So network interface card。

 So what this network interface card will do is it will have。

It is the card itself is a hardware piece， so it can be attached to the motherboard of your computer。

 but for activating this card you need to have a software。

So well be writing a network device into your Linux machine or a Windows machine。

 according to the operating system。This software will control the hardware。

 So that is how the way the nas have been programmed。 if there is actual。Net devices。

 but how I can model it using a simulator。 That is a challenge here。

 so far that a net device in NS3 will be meaning that it is a combination of software as well as hardware。

So， that is what。嗯，第四。90。So in NS3 the native subse covers both the software driver and the simulateimd hardware and native is installed in a node in order to enable the node to communicate with other nodes in the simulation via channels So wire channels these native ways can communicate one node can communicate to other nodes via are these natives so now we can understand that。

We have。In order。This is an obligation。There is another note。sAnother application。If they vote。

 if they do， if they both of them want to talk to each other， we need to have a。Net device。

 So via this net， they can talk to each other。This is an application。This a channel。你生六。

So that's how the way node channel。 And this thing called us， this dot is called us a device。

So only one more is pending in the topology。

![](img/8a0d4b236b8363420410532251087606_20.png)

So that's what the topology helpers。 So the topology helpers is the send。

In a real network you will find host computers with add and are built in N in NS3 we would say you will find nodes with attached internet devices in large simulated network you will need to arrange many connection between the node so for example I have a node here I have a node I have a node。

Have not haven。Okay， so let's say this is source note and let's say there is another this destination note is for source D for destination。

 So how can I send the packet， I can send the packet like this like this。Or again like this。

 And then I can reach it。 So this is one part。So another path might be I can go here， go here。

 go here， over here。So this defines that a policy。 So suppose this part says。1，2，3，4 totally4 this 1。

2，3，4 totally4 or four Okay， suppose I have another node here。Now， this takes4。In fact。So，3，4 and5。

So this way I can say there are five hopps the hop number1235 hopps so in this side we can have only four hopps so I can decide on the last number of hops so it will best network so in their case I can decide on this topology can be good so these things can be decided on these topology helpers in this NS3 so there are so many different protocols available different applications different algorithm there are so many things available so we will see one by one how can be implemented in S3。



![](img/8a0d4b236b8363420410532251087606_22.png)

So， now， do。Conclude this with a comparison statement So what node means in N S3。

 what does it mean in general， what does it mean application means what in NS3 specifics。

 what in real in reality， what is specific similarly channel similarly here also。



![](img/8a0d4b236b8363420410532251087606_24.png)

So the same way， na of policy help。

![](img/8a0d4b236b8363420410532251087606_26.png)

So now what NS is built with。So industry there are so many in models so for these models to run you need not be a full fl engineer to do that so the existing models can be directly been imported to the U C plus plus source libraries and you can able to simulate this network。

So one good example， devices， bridge。Bridge means similar like a switch and router spectrum。

 So even you can handle the spectrum， CAss multiple access， then EMu。

 then UA some kind of access networks， point to point Wifi networks machine network。

 long term evolution network LTE Yax So these things are already been available as a source code。

 you can simply use the source code and run this application and method of performance of it。

So thats how then protocols protocol means a set of rules and regulations for a network。

 So we have wireless protocols called us on demand distance vector U O DV。

Destination sequence distance vector， object link state and routing。

 click router next vector open flow。 This is the software for HD D and software Def networking。

The neutral scale a visual laser。Flow monitor， netanium topology and statistics。

 So all for configuration store everything is there in core there been the network coordinates what pointers call back events scheduler logging gracing these things also it is supporting for industry system level and the node level。

 we have node sockets， queues packet， etcter。So whatever you would like to do if you want to create a new packet I can do that if you want to create a new queue I can do that if you want to create a new socket I can do that if you want to create a new node I can do that。

So like that we can able to do whatever we can able to do。

 we can do it here in this network simulation。So we will see in the due course of time。

 we will see how to simulate these kind of networks。



![](img/8a0d4b236b8363420410532251087606_28.png)

So now how to build this so as of now we will be knowing how to build a particular application in NSs3 generally in Linux so maybe I will give a video so you can refer the video。

next。Building applications。 So I'll just show you that how it can be happening in V。

 So based on this video， you can able to understand what are the different built mechanisms available in。

net。So in this build system we have dot slash w configure and we have dot slash w build so it is w is kind kind of build system different for NS3 so in3 support different build system so one build system is a w so it is just you can able to check in Google code that what is this v contains so similarly in this case we have a configuration colors dot slashva configure。

And dot slash wave builder So this is for configuring this is for building the entire system for NS3 hope you have if you have tried NS3 to install on your machine you might have tried these methods to do that。

So it is python based a v is a python based framework for configuring compelling and installing day applications。

 so this application is used in NSs3， so NSs3 also have two different things called as big。

And mercurial。 So there are two different insulation system。

 but we are not using that rather than we are using the W system。ok。So we will be seeing in detail。



![](img/8a0d4b236b8363420410532251087606_30.png)

So now these bad systems usually in generally water happens make a dot s configure。

 so usually whenever I want run any application first what I is I use dots s configure。

So once all the required configuration is done， then I'll simply type a command make。

So let's say is the prompt。And I will be using this dolash configure and make。

 So this is one custom method for building any project in Linux So even in Windows also you can use the same doless configure and you can use a c make。

Or something like there are end make or something。 So you can Linux in Windows。

 you can do the end makers you made。Here the next is is NS3 uses dot slash builded or P there is a Python file on dot s5 this is for building projects and applications so these two so these only we are seeing we will be seeing for NSs3 Anyhow I'll just give a comparison of file write a simple see program on how to create a configuration to make file I'll just show you that in one other video can refer。

Only the working directory I can use do slashb So this is working directory。

 so I will just tell you how I have just formulated the working directory so my working directories s home。

Slash per dipummer。 So this is my home directory。So this is my home。

 So this directory only in my VM image also I have given you slash home slash pre in this I have installed an application colors N S all in one。

Iyhen 3。27。 I have taken a 3。2 zone version。Because of bug free another thing。

 but if you want to use the latest version is 3。30。1， you can use it。But let us go with the N 3。

27 and inside that we have N 3。27。Yenna7，3。20。So inside this folder only。

 we can use this dot slash path after we give this commander C。This command。

 then I can use directly do s w。And the command name so we will see these command name So if you want to clean delete all the object files I can use the command colors in jar slashva clean So any of these is only a practical command。

 so I will be showing you in another video with all the detailed command using Linux operating system。



![](img/8a0d4b236b8363420410532251087606_32.png)

So in this session， I think we are at the end of the session。 In this session， I'll just。

toldold you about what are the different key abstract abstractions in NSS3 like node channel application topology helpers and net devices。

 so just I am just checking whether did you install NSs3 in your machine。If not。

Have you downloaded the V image I have given to you。

Al already run the first example and hello simulator。So in the next video。

 I'll be showing you more of her。Examples on how to simulate a particular network in sulator 3。

So actually this course is just 10 to3 course so that meansja1 hour is the theoretical part and towards the practical part。

 I expect the learners to extensively work more on practical rather than only reading because reading is just only slides but only the working knowledge make you comfortable on the simulation simulation aspects of networking。

So， thank you very much， Los。

![](img/8a0d4b236b8363420410532251087606_34.png)