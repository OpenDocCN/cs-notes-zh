# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P20：-20-Lecture 22 - Time - Triggered Architecture.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Okay， so I guess it's time to start。Good money。Okay so today we are going to talk about time trigger architecture and this one is an architecture that is taking more and more place in industry today and is an interesting discussion because you heard a lot about synchronous model computation so we talk about how to do synchronous in as model computation we talk about the software aspect of synchrony and today we are going to talk about the architecture of a distributed system using this concept now the important thing is that if you look at the evolution of embed the system。

 we are going towards more and more safety critical system and so that's a great interest in synchronous architecture and synchronous everything because that eliminates a lot of the problems that we normally have when we use an event trigger model which is。

For many the most natural way of encoding and representing things now in this particular segment of the class。

 I wanted to show you what are then all the intricacies and issues that you need to resolve when you want to implement red model。

Into reality， into physics。 right， So we have seen that in the case of electronic circuit design。

 the mechanism of implementing synchrony is the。Registers and the clock。

 right And so everything kind of moves。 the computation moves from left to right。

 So to speak across combinational logic。 When you write the register， when the clock comes in。

 you transfer the data into the output buffer and then。You read the data。

 So it this guarantees the fact that you have no races。

 right as long as the computation is within the clock cycle。 So now this is rather simple。

 if you like， and it is a very well known mechanism， everybody plus his brother uses it。

 So then later on， in the history of design， this mechanism was。

Transported into softwareer and then last but not least into the architecture of distributed system。

 So today we're going to talk about that。 and I wanted also to project what is the frontier of industrial development in this domain right and so we will see that the next generation situation will be an attempt of combining the event driven and the time trigger or synchronous model。

 So this are I ranack slides right and left because this one is a topic that has been present under many different angles。

 and so I try to synthesize what is known in a unified presentation with slide from everybody plus is broader so first of all。

 what happens in today's system。 So if you open up the a car today。

 you find more of than 80 processor that are connected。



![](img/895cade4d879c02867c27629670eca43_1.png)

together and and perform different tasks information systems is all what goes around and tells you what is happening。

 the sensor source telling you what is happening in the car。

 the body electronics is talking about air conditioning that warming opening and closing the door。

 the module that is taking care of the lights and then there is the body electronics which is typically the safety critical part of the system so now interesting enough for every one of these functions。

 the connectivity of the components that do that calculation。

Is given by different wires and different protocols。 So it's a real mess。 It's an ugly mess。



![](img/895cade4d879c02867c27629670eca43_3.png)

Now this one is the actual car architecture so I took away the names because it's a confidential information。

 but is's a real car that is running today on your road and so the name of the maker and the name of a car will remain unknown and the name of a various function of being carefully erased otherwise you will find me in jail next month or so so I will not be able to grade your papers。

 but that's what it looks like right and so you have all these different boxes and each boxes is a piece of hardware and the connectivity are buses that float around so in a car today there are something like you wouldn't believe this。

 but how many meters of cables do you think are in a car。How many？I already asked the question， then。

 Okay， so there are lots of wires， right，10 km of wires， right there are some for large cars。

 there are 10 km of wires。 and the weight is correspondingly。 So this is a mess。

 That's the reason why you have so。 So now the point is that if this node are sensors。😊，Of course。

 there are compute elements and there are auators right now the point is that the sensor collect data in the sense of the compute element compute element does computation then actuas the auators right Now the key point is that you want that to happen in a correct fashion right and so the key issue is that how are you going to guarantee that now the other thing is that。

When you look at that architecture I show you before。

 there are different companies that are doing different things。

 So the OEM of the B AndW of this world， the general motors of this world。

 take care of the car in its。Totalality， so they do what is called system integration。

 So they integrate very。 The tier 1 suppliers like Bosch and Delphi and so on， make the boxes。Okay。

 but you saw in the previous architecture， right。And so the point is that and then below inside the boxes where are tier two suppliers that are。

 for example， semiconductor makers。😊，So the flow of information and of design is quite complicated。

 Now， the issue here is that if you want a very clean supply chain。

 you want the people to do the components to be able to design their components in a clean fashion。

 so they just have the requirements theyre designed to vet requirements forget about。

The system integrators would like to take all these components plug them together and hope that everything works now that is a very big if right so that is some are some of Asia that we need to worry about Now this one is the rolling mill so it' paper making machines right and so it's not that different in terms of the global architecture。

 it is also distributed system somewhat you have a main machine interface。

 you have a model quote unquote which is a compute node there is a communication node and then there are auators and sensors。



![](img/895cade4d879c02867c27629670eca43_5.png)

Same basic architecture as any em embedded the systems。



![](img/895cade4d879c02867c27629670eca43_7.png)

嗯。Now， what happens in these systems when something happens。

 so you got the sensor that takes some information， then they communicate this information。

 then the compute node takes this information， manipulates it。

 then through communication sends it to the autor， and the autor puts the action on the environment。

 on the real world。So these phases， for asynchronous model， like for example。

 in automotive is a CA network is in asynchronous model happens wherever right so something essential puts up a data and then everything starts right communication。

 computation atation。😊，Another thing happens and maybe be almost immediately after everything starts and then there is a chance that everything kind of collides so now what is the goal of the synchronous paradigm the synchronous paradigm is to have a computation and the communication occur in non overlapping phases。

So if they are not overlapping phases， then you can put order in this gigantic mess。

 so you are going to have a cycle where all the sensors tell the rest of the world what they are doing and then the communication takes place so it gets distributed to whoever needs to know。

 then the computation occurs， then when the computation is finished。

Then you have a communication phase where this information that the model has being able to compute to be delivered to the auators。

 So how are we going to make this thing work in the actual physical system。

 So we know what is the tricks in the synchronous design， which is the clock and the register。

 how are we going to do this in a distributed system。



![](img/895cade4d879c02867c27629670eca43_9.png)

So that's the goal here。 So the problem is design the distributed system。

 so that the information from the sensors to the model are accurate and timely。

 The results of the computation are delivered to the auators accurately and in time。

 and if more sensor computer node and auators are present all the communication are reliable so we don't have situation where there is a collision between a variety of information so that the action are going to be a real mess Okay so time trigger architecture。

 What is it So is is a platform for the design of safety， critical systems。



![](img/895cade4d879c02867c27629670eca43_11.png)

What are and functionally， what it does， essentially。

 is that the communication is taken care through a TDMA scheme。 Now， TDMA time division would。

The proアス。What does that mean is something that is being known in communication。

 standard communication， and essentially it says that in a round cycle。

 in a round of information of scheduling of the system， every single node has its own reserves law。

So there is a period in which only one of these guys does something。

And then you move to an next one and this guy does something， when you move to an next one。

 this guy does something， then you move to an next one， this guys does something。

 and then you start again right so this is a TDMA cycle。 Now what is the advantage of TDMA。

 It is a time integral model。 So it's kind of a synchronous idea。

 And the point is that you don't want to have overlapping between different guys。

Tling the system what is going on。 Okay， so its TDMA。 Okay。

 now notice that the TDMA method of communication is also very much used today in cellular network。

So， you know， that's something that is used everywhere。So time inger aial bus。

 but bus in our concept of a distributed system is a quote unquote bus we see different architectures that are going to be connected with the TdMA model now is important because we have safety critical things and so the requirements that are in general place on this network is that you have a failure probability below 10 to a minus 10。

Faures per hour for 10 hours。And maximum outage of this few。

Fals that may occur as to be less than 10 millisecond。 I mean， geez。

So you can be fairly safe if you are running on top of an airplane where the guy doesn't go down these are requirements that come from real safety critical systems so you got to be able to guarantee this kind of situation。



![](img/895cade4d879c02867c27629670eca43_13.png)

We say before the Ba is actually a generic term， so what you see here is a TTP in a single channel topology。

 which means that all the boxes are connected to buses。

 but remember that the mechanism of communication， the protocol of communication on the bass is TMA。

Now， most of the buses today are really asynchron， so whichever guy wants to put some information in。

 he puts it in and then he sends it out。Aller we let's hope but everything works fine。

 so in some sense a tiny protocol， which is a way of enforcing a tiny architecture。

 is a layer on top of a physical layer which are in this particular your case the basises。

Now what you see there is a so-called cascaded star topology in which the communication of course between the TTP and the star and the star and another star。

 so in some sense is a distributed concentrators architecture so this is particularly true when you have a bunch of sensors。

 intelligent sensors that connect to a sort of a gateway when the gateway talk to each other and do the computation when they send it to the auators。

Now， what you see on variety is yet another topology that people implement。

 and it is a mixed star and bus architecture。 But this is just to say that the actual physical implementation doesn't matter as long as the protocol of communication is the one。

 that we say before is TDM。

![](img/895cade4d879c02867c27629670eca43_15.png)

Okay， now TDMA， as we said before is is a consists of a cycle of。

Computation and this cycle of computation is divided into slots and every slot is assigned to one actor in the system。

And so this is the mechanism of exchanging of information on the network。



![](img/895cade4d879c02867c27629670eca43_17.png)

O。Now conceptually then the Tt time integratedger architecture is an integration framework and so it's a way in which putting together a value system and we say before it when you put together a value system。

 your goal is that the whole thing works correctly。Okay。

 so that's the key point that the framework is invisible to the interaction of compliant components so you can do independent design。

 remember one of the goal is to have the tier1 suppliers to do their own design in such a way that when you integrate。

 you maintain the properties of a single component。

And so that is this architecture guarantees that this is the case。

Now integrated modular a vonics is a way in which today， for example。

 airbues and Boeing airplanes are designed and it is called integrated modular a yonics just because of this composability issue and in fact the backbone uses this time trigger。

Architecture， okay。Allright， so we said before a TTA apologies is you have these TTP nodes connected to the bus and so interfacing to the bus so the way in which the node talk to the communication structure is critical and does define the TTA concept so you got this thing that communicates through a TDMA method but then we have to say how each of a single block interface to a TDMA protocol so what does it do when it writes into into the bath and so this is exactly the same as when you have in a single circuits。

 what happens when you have a block right and so you compute when you write on a register when the clock comes in you shift this information to another register and then this register is free to have another writing and this register is ready to be read by the rest of the thing。

We have to do something exactly the same， right， We have to try to do the same。

 right in a distributed environment。So the first thing that you have to think about is that if。

 indeed。Time is what keeps things in order。😡，What is the important。

 most important point when it comes to interfacing this node to the bus？Is the notion of。Time。

 right And so everybody has to have the same notion of time。 So if for him is 8 o'clock。

 it has to be 8 o'clock for me as well， because if for me 7。

59 and I'm supposed to write at 8 o'clock， I say I'm not ready to write but he is ready to read。

 So everything goes bananas right So we are back to the a synchronous mode of computation。

 So the sheer notion of time is crucial。😊，Now， in chips， I think that all of you know， I mean。

 the ones who know a little bit about circuit， but one of the most difficult thing in design today for Intel like components。

I。Clock synchronization。Which is exactly the same thing as I'm telling you in distributed this system。

 So so that every block。In the circuit is going to receive the same click at the same time。

 where the same time means absolutely the same time right has to be the same。

 Now on a chip is a small。ing right and so the delays and synchronization issues seem to be not so great。

 but they are still serious， so serious that clock synchronization has its own circuitry to make sure that the clock coincide。

😊，So think about you have this small of thing and you have problem。

Imagine in a distributed system when a plane right， a plane is meters and meters long。

 right big planes are 200 meters long， right。And so it's very difficult to maintain the notion。

 the same notion of time。 So clock synchronization is a key issue。 So in TTP。

 there is a particular way in which you keep the clock synchronized。

And so there are special chips that companies sell that do this synchronization of the various parts。

 but is more difficult than what you have in。啊 in。So one way of doing this is that does it matter if everybody agrees its 8 o'clock。

Or is more important that。When he says now， I say now。 So it doesn't matter8。

 but we kind of are aligned， So we save it。It's time for both of us to do something together。

 So which one of it。The second， right， the most important is that we have to agree。

 So one way in which you can achieve clock synchronization。

Is the fact that there is an external observer， it looks， right。And then he says， well， ge， you know。

 this guy is off in absolute turn with respect to this guy by so much。By。

 I don't know say1 10 microsecond right， And so what I will do then is that I will try to realign with two guys。

 right。And so， but there are 10 such guys。 And yet and everyone is going to have a different kind of situation。

 So the clock are all kind of thesealign。 The notion of time for every very block is kind of not quite the same。

 So what I will do then is that I will decide I'm the outside boss。 and I'm going to say。

That I'm going to synchronize on the central point。 So I'm taking all your notion of time。

 going to average them out。 And I say， guys， the real time is this one。 Everybody lines up on this。

Okay， so I so many cycles， I have to do this， I have to control that the drift of the clocks。

I not do strong。By way， if you want to do some research from this topic there is yet another protocol which is called loosely tiny trigger architecture in which you are allowing the drift of clocks and you are still fine okay and so it is quite interesting if you want if someone is masochistic enough that wants to read these papers that are quite difficult。

Because there is a lot of mathematics and the lining hauler， I'll send you such bit。



![](img/895cade4d879c02867c27629670eca43_19.png)

So is that treatment of physical time is first order quantity is key， as we said。

 you need to have everybody that think the same about time now by way， provides full tolerant。

 global time based， full to meaning that even if a clock breaks have a way of realigning them and one key such scheme is what I told you。

And uses global time to specify the interfaces to a bus because essentially when time comes。

 I will need to transfer the data that I compute to the bus。So am I going to do that。

 I'm going to use the same mechanism as in circuits right I'm going to have a buffer where I write and then I transfer this writing into the reading buffer and the reading buffer is what sends out the data so this is the way in which I'm going to do that the global time again use the specify interfaces between nodes and communication and agreement protocols are the key issues right you work on this so you see here is the middle arrow is the。



![](img/895cade4d879c02867c27629670eca43_21.png)

Communication network。 And that doesn't have to be a bus can be anything。

 but we simplify it with a single line。 So， in fact， it's a communication。

Part and then you have a host， the host is the node that does the computation or the measuring or the ation and then the CC is a communication controller that is this thing right that takes the data from the computation sends them on the bus so it controls that access to the communication network right and so we saw already that one way of doing it is to split it into having a buffer where you write and a buffer where you read。



![](img/895cade4d879c02867c27629670eca43_23.png)

So。All right， so。The TT architecture then consists of the set of electronic modules that are connected to a channel。

 the interconnection network， the communication is performed using a TDMA scheme。

Each electronic module is called a node of a TTP network and a node consists of a host subsystem and a communication subsystem。

 right which is what controls the delivery of the data from the node to the network。

Now communications subsistence consists of communication controller and communication interfaces。

 communication controller when it says go and the communication interfaces where you put the data so that it can be packetized and sent。



![](img/895cade4d879c02867c27629670eca43_25.png)

So the communication subsystem decides autonomously when to transmit a message and whether a particular message is relevant to an node or not。

 so because what I do is that I post the data on the bus and then you on the bus on the communication network and then the receiving node as to realize if that message is for him or not so together with the data I have to also to send。

Who should be interested in the data I'm going to send。RightSo they are dress calling。

 So when the note looks。This is good， reads it right and that's something to it if it says， well。

 my name is not on the address list。

![](img/895cade4d879c02867c27629670eca43_27.png)

I do know， okay。嗯。So again， the notion of the temporal accuracy of real time data is key。

 and so the issues that when you decide， for example， on the TDMA schedule。

You have to make sure that the schedule， the round of information is short enough。

So that the data that I'm working with are not stale。You know， because it may very well happen。

 but he is sensing something， for example， the engine is on fire right when he sends this data on his locked。

 then you go， you go， you go， you go and then finally this information engine is on fire gets to be sent right so you want with this is not too linked for you to blow up with the car right so you have to keep。

The boundary very clearly align。 So the decision on this lot to give him in。Her and so。

Is one decision and the second decision， how long is the entire cycle。

 So you have to decide these two things。 And so the design， for example。

 of a good TDM A T TP network， is to decide these two parameters。So the window and the lock。

And it's a very interesting mathematical problem， by the way。

Now so this is what I just say real time loses its value because if you look at the content of this register which I was talking about is what resulted from the computation and they are sitting there so that is an image of what is going on in the system。

 the real information about what is going on in the system as passed right so because it does all the things in the meantime and so we have to make sure that what is the image that I'm going to send it out and work on and what is the real state of the system is not too distant。



![](img/895cade4d879c02867c27629670eca43_29.png)

So。So this is a real time entity， changes the state as a function of time， if we freeze time。

 that is the situation snapshot of the system。Now the information about the state of an RRT entity at a particular instant is captured by an observation。

 so I'm observing the system looking at what it's doing that is the equivalent of freezing time and say。

 okay here is the status of the system in its Valley the real time image is what I think it is the state of the system but is somewhat delayed by the fact that we use that particular protocol and so the image and the status。

 the real status have to be very close because we are not closed disaster occurs as we said before so the validity of an RT image is time dependent and is likely to be invalidd by the time so if you have a Windows too long of course the data are becoming stale and then you are not providing very information that you need to operate upon。

So an interface is a boundary between two subsystem。

 And so the memory element is that buffer that I was talking about before。

 that is where you write things and you read things。

And it called contains valid art images of the entities or real time entities we saw before that we have to make sure that what I write on the buffer is a faithful representation of what is happening inside the system。

 right？😊，嗯。So it's a dual parted memory in some sense， where on one side， you have a real time。

Status， and the other side is a real time image that you deliver to V。

And so the information consuming subsystem reads this temporary accurate information whenever is needed now this temporary accurate has to be part of the design requirement because that will determine the length of the cycle。

The communication subsystem then connects the interfaces， obviously。

 and transports data elements from one interface to another right so is what interfaces to the communication network。

So this is the sender， sends the data here and gets sent。

 and then there is a writing phase in which the information for that particular node gets written into the appropriate slot for the node to read。

So these points in time when messages are send and delivered are written in a particular table because this is what gives the operation of the interconnection network。

And so the contents of these dispatching tables have to be decided this part of the designer。

 we said how many bits you are going to have and what these bits contain so you divided them in fields。

 one field is the address。 The other thing is a payload， meaning the information。So the computer。

 so the O subsystem is an encapsulated computational machine encapsulated by work by the interface。

So the interface acts as a detachment from the communication thing。 So the Earth computer。

 what does it do， reads the input data in the buffer that is written after the communication phase is done。

And right we I put data into another piece of the memory that then willll get sent So you have these two buffers。

 as I told you before， one in which you read and one in which you write。

So the priority are instance when we input data to the O computer are actually delivered to the interface。

And when they output data from the computer are fetched from the interface。

So you write and read at this priority time。IfOf course。

 if a host computer has to react to a specific state change， So an event that has occur course。

 for example， in the sensor， So you read something new， then what does it do。

 It has to periodically sample the interface right so in that period is the TDMA period right so it has to look at this input buffer。

And trigger some action， if indeed that data that is contained in is read interface contains something that tells you do something sometimes the data is relevant and they are left there and you don't do anything with them and you overwrite them。

 but if it contains some important information， you wake up and do the appropriate operation。

Now the transducer then is what takes again this information about the real time status of the system and delivers it to the rest of the world。

 So again， the transducer are introduced to model the input output system of a real time system。

So it is real time， but it is not right so the important thing is that there is always this sort of a delay which is given by this clocking mechanism that I was telling you before。

 but indeed if wet clock in time is designed correctly。

 it is an approximation that is very close to what really goes on into resistance。😊，Now， by the way。

You may see some in in drones， right， So this autonomous driving airplane。You have two model of。

 for example， of sensors。One is called the push mode and the other one is the pull mode。

The push mode is corresponding to the fact that the sensor sees something and when say I need to push this。

 So it's intelligent。 So I tend to say this is really something that I need to send out right so it is when pushing the data onto a system The pull is when you have this sampling mechanism which the computer says。

 okay， what are you reading， What is your last reading and then the sensor communicates the last reading。

 So the push model is in general is synchronous and the pull model is the synchronous。

Oper so if you look at the most of the autonomous flying system is based on the pool models for all this reason which we say before。

 Okay， so same similar thing as the TTP architecture。



![](img/895cade4d879c02867c27629670eca43_31.png)

So this one is the way in which a processor looks like there is an input output subsystem that we talked about before。

 then there is a communication node interface and then there is a OS processor with memory operating system application software。

 then there is another communication network interface。

 and you have a TTT communication controller that delivers the information to the network that is the one which is based on TDMA。

So a standard nodeman consists of two subsystem， a host computer， and a tiny communication protocol。

 which is that we saw wear。And that。Information that is stored in the communication controller is an internal data structure that is called a message descriptor list and the message descriptor list is describing what are the system that you need to communicate to。

O。So we say before the O computer is the O computer and the TT model， it is a selfcon computer。

 meaning that it has its own memory it tells computation and its own IO subsystem and it interfaces with the communication backplan through a communication network interface。

 which is called CNI， so the CNI is the concrete implementation of the mechanism of communication that we described before。



![](img/895cade4d879c02867c27629670eca43_33.png)

So we say its important。Point， in fact， that's a reason why it's called time trigger is the role of time。

 So time is really what determines everything。And so， in fact， you know。

 we had a very long conversation with Erman Copps and with Edward Lee and others。

 and where we were trying to。Really define what is a good synchronization mechanism。

 And Herman always said， well， we have time， physical time。

 Why don't we use physical time to do that。And that's fine。

 except that even if he says that he' is using physical time， it really doesn't。

 because it does with chopping， right。So it's really logical time。 Okay， And in fact。

 we know that logical time is an essential concept in synchronous。Mechans， right。

But the way in which you read the paper that Herman Copps wrote。

 who is the originator of this TTP architecture， TTA architecture。He says。

 let's use physical time as a synchronization mechanism。

which is kind of right and kind of not right but you know that was the original idea was based on the Newtonian physics so it is not relativistic time of course because relativistic time says that you cannot ever synchronize to clock right so that's Einstein discovery call it and so you have to think in Newtonian physics in which time can be synchronized but in modern physics that's not the case but who cares right again because if we have a mechanism of sloting time and we have mechanism of aligning reactions and who cares it you have real time or it is Einsteinian time。

And that is the notion of logical time because it's a logical operation that follows through。

 So in some sense， again， that's the reason why I always kind of debate with the people are talking about。

 you know physical time when they talk about thinkers mechanism because they are really telling a lie iss not true that you use physical time。

It is convenient to think in terms of physical time。

 because most of the people think of physical time in a natural way， but it's not so， right？😊，O。

So a duration is a section of a timeline， which are thelim by two instance。

 an happening that occurs at an instant is called an event， of course。

 right So an observation of a state of a war is thus an event。

 So I can call an event my snapshot of reality。 So click。This is my reality。

 that is an event that I'm going to transfer to the communication subne。

So how do I timet a particular event， right， in this modern in which again。

 we are talking about this。Boundaries right that are given by the mechanism of computation and communication right so now we say that we times them by assigning the state of a node local global time to the event immediately after the event occurrence so what you do is that you are essentially assigning real time to the clock right when the clock comes in。

😊，And so once more， it is physical time， but it is not because you are pushing the timest to the boundary of the interval that you are working with。

Then a fulltrant internal clock synchronization algorithm establish notion of global time is what I was talking about before。

 when we say if these two guys have a clock that doesn't quite match。

 we try to find the intermediate closest time to the two and then we align with to V right that's a synchronization mechanism。

 It's not the only one。 mind you。 there are all kind of other synchronization mechanism。

 one of your project。😊，Item is about studying this co synchronization issues。

And so you will see that if this just one， there are many other ways of doing clock synchronization。

So the access to the bus is controlled bycyclide division multiple access that is derived from a global notion of time。

 and again every very active electronic module owns a lot so its its own so nobody can interfere in which it is a computation。

After TDMA round is completed， the next TDMA round starts again。 And so， in fact。

 this way of thinking about communication and computation is called a cyclic。嗯Schedule。

So everybody gets his own time and that is fixed forever within the interval of time that is dedicated to the round of pulling of the various node。

So the number of different TDMA rounds determines the length。Of the cluster cycle。

 so if you have a number of nodes they talk to each other and all of that。

 then if I want to have yet another hierarchical notion， I can talk about the cluster of nodes。

 they talk to each other with a TTP。Scheme， but then there is yet another network at higher level of a hierarchy。

 and you want to use TTP again， then you have to think about the entire round of the internal nodes as being one slot in the TTP at the higher level of a higher。

So we say before the message frames contains different information。

 So there are n frames which contains user data and I frames that are system messages that are needed for reconfiguration。

So sometimes you need to reconfigure why， because maybe that some of the node is dead。

 and so you want to cut it up。And you want possibly to redistribute that function to other nodes in。

 in the network so that you are not only。have to say fault aware， but they are also fault tolerant。

 so something goes wrong and you have a way of fixing that problem that does occur。



![](img/895cade4d879c02867c27629670eca43_35.png)

So the timeger communication protocol， that is the one that we just talked about before in sense of how you agree on the interface。

I is the mechanism that provides a co synchronization service right and the TTP communication controller must contain different information。

 its own data structure， but also the message descriptor list which specify a global interaction pattern between various nodes。

 which means the information about the address of various nodes that are going to receive this information。

The temper and value parameters of a communication network interfaces。

 which essentially says what is contained in the communication buffer。



![](img/895cade4d879c02867c27629670eca43_37.png)

Now， there are two different ways in which TTP has been implemented， one is called the TTPA A。

Where A stands for simple， if you like， and it is done for very simple sensor node we are not going to describe that you can find it in the literature because it's really a poor man version of the TTP architecture and the TTPC。

 which is a real TTP。As it it is being sold， so the TTPC communication is organized in TDMA rounds as depicted in the figure that we showed before。

 and a TDMA round is divided into slot and each node of a communication system as it sending slot and must send this frames relative the data and the reconfiguration information。

When the frame size is allocated to the various messages。

 it can go from two bits all the way to 240 bits， according to the different use that you have of this network。

And so this frame in general contains several messages but I have state information and the metal information。

So in different rounds， different message can be submitted。 It's not always true。

 but the same message can be sent。 So sometimes you want to package the message in a different way。

So this one is the TDMA around as we say before， and you have in H TDMA around。

 you have a node A but as you see the medal is written in the first part where you say that the Part node a is sending messageger M1 M2 M3 when you have others lots for different nodes and then node a gives information M1 M6 and8。

 then it goes on and then in node a again post M1 M2 and so on and so forth right so this one is repeating TDMA cycle information and writing on the bus。

And the cluster cycle is the when a certain number of cycles have been taken by the various nodes in the sub network that you are considering now what。



![](img/895cade4d879c02867c27629670eca43_39.png)

About the fold mechanism。 So how can you detect if someone is broken， right So well。

Let's assume two different。Fd mechanism。And one is the one that is most preferred in this kind of application is the。

Futh， silent model。 What is the full silent model。Means that if he is broken。

Is not going to say anything。 So it's mute。 And so it's like you put mute and your communication。

 your microphone you put on mute。So what happens， How do I detect if he is broken？ Well。

 if I have a supervisor and checks this lot， if this lot is empty。

 it means something bad has happened to him because it's not responding。Okay。

 so you have to do something about it， but you realize that there is something that has gone wrong。

Another model that can be taken into consideration by this scheme is a so called bubbling idiot。

The bubbling idiom model。Says that oneNot keeps on talking all the time and doesn't stop all the time。

 And so how you determine that you have a bubbling idiot in your network。

If you notice that the guy keeps on writing， right， even when it is not his time。

 right science lot is。Step over。Which means something wrong has happened because you determine this lot and you tell the note that he has to communicate everything and needs to communicate in thats law。

And so if it oversteps the boundary， it means something went wrong。Okay。

So the essential mechanism to have full tolerance in this TTP architecture is to have an observer the checki either if this lot is empty so the guy is broken or if it has。

Data that spill over the slot that is assigned to it。 Okay。

 so we serve with two mechanisms that can be done。 Now， by the way。

There are ways in which you can design the node so that if something breaks。Their side。So in fact。

 that is a。An implication on the people who are doing the modules of the design。

 remember that we have this vision that there are companies that are designing the blocks and companies that integrate the blocks right so if Im controlling a car I want to know if this module is broken or not and so I will ask the guy who's designing this block if something breaks inside。

You cut every communication。And so you have to design that node in that way。So that's a way。

In which you can take care of the fault robustness or and why is robust right way。

 because in the moment in which I realize that this node is gone wrong， then I'm going to。

 in fact the protocol of TTP is rather complicated because it will allow him to be silent for one cycle if a net cycle is also silent。

 then you know it is broken and so you cut it off because it may be partially。

Absent because something has temporarily happened。那。Once I determine that is broken。

 then I have to reconfigure， right。Because I have to assume that I have a way of replicating the function that E was carrying。

 and so I have to give this function to somebody else。

And so I need to send the reconfiguration message I just say you guys have to reconfigure because you have to take a this function that is not carried out。

 sometimes you have duplication of components or you have for example。

 this node is replicated and this other node was just doing exactly the same thing as this guy was doing it and so if something happened then I shut him off and I go to it。

know so that is the way in which I provide fault robustness right so in such a way that I can take care of the fault itself another way is that say okay guys it's broken。

 I have no way in which I can reassign things and so you better put up a big red flag on the screen or the driver and saying。

五？Llow， stop as soon as you can， because there is a serious problem on the thing。Okay。Now。

 the fact that you are broken or not is expressed with this notion of membership function。

So you belong to around if you are communicating， if you are not communicating。

 it don't belongs So a membership function is false for red particular or not。



![](img/895cade4d879c02867c27629670eca43_41.png)

Now， as we say before， this mechanism is indeed allowing。A topop down design。

 which is the part of the concoction of the various sub blockss together。And in fact。

 you partition the system into a set of nearly autonomous components。

 you specify functionality at a high application specific level。

 you specify the timely information flow so when you need to have the information so that the snapshot of reality and reality itself is not too far。

Then you design the message description list of the communication controllers and determine the point in time when you need to activate the communication。

So the first design phase then results in a specification of temporal firewalls over these boundaries of a TDMA is slot。

Then the component design instead is that the components are designed considering the constraints of the architectural design phase。

😊，So what is it when no points in time where information must be delivered are the deadlines of the components。

 So I have to say to this component， you have to compute your。

Whatever function within this law is what I decided to be your law now then there are two situation。

 one way that you can do that so you can compute within that boundary or you cannot and then what you have to do you have to iterate。

Now， when you design a microproor， this is exactly what you do。

 so you have a clock then you try to do the combinational loging such a way that the propagation time is within that clock。

 if the propagation time of the signal between a register is longer than that。

 you have to go back and readjust the clock。Okay， because it takes longer。

And this is exactly the same kind of mechanic here。 So there is a bottom up part。

 which is very use of components。

![](img/895cade4d879c02867c27629670eca43_43.png)

And so the input firewall parameters determine what a designer is supposed to do。 So for example。

 you can say look， my computation is a bottom up， so I have a bunch of components。

 Each one is characterized， but its response time。And so he's saying， I can do this computation。

With this time， I cannot do faster than this。 This my boundary。

And so if when I do the decision about what should be the overall integration scheme。

 I have to take into consideration that I cannot give him a lot which is short and what he can do that's a bottom up path。

 so when you do the intersection or the top down and bottom up as I say before。

 either to agree or they don't agree you have to change the top down design path。

So this one is very well along the line of the platform based design principle that we took at the second club right so it seems really that everything that you can do in terms of desire reus and so on can be fit in this domain now。



![](img/895cade4d879c02867c27629670eca43_45.png)

I told you that the time triggered communication， of course。

 as is own goodness right and the goodness is the fact that you are。😊，Reactive。Really reactive。

 Something happens。 You immediately take care of it，那。We say before that if you do that。

 then you cannot predict the behavior of the system because the way in which the system reacts depends on the data。

And so if I give you a particular set of data or an order。

 the behavior of the system is going to change now the case of this TTP architecture is not the case。

 it's always going along with lots and doing things along with time， so it is deterministic。

 so you always know what happens。In the time trigger communication scheme is very appealing because it's very performing。

 on the other hand， you don't know what's going to happen right so and that is the sad story。

 Now when you get into the communication of your laptop and so on on the internet now most of its communication scheme actually all of it is。

TheSo called best effort， So which is means that recom is asynchronous。

 there' is no guarantee of anything。嗯，那。In the communication， for example。

 if you have a wire communication， the way in which for example your computer are connected together when you sit on your working table and you have the plug coming in into an appropriate plug most of the time is ethernet so Ethernet what is it is a protocol on one side and it is a physical implementation of the wiring now what is good about Ethernet that Ethernet now is very cheap right Ethernet controllers are very cheap is very well de backed you know so how many years probably 30 years that we use Ethernet。

And is damn cheap， right， our controllers are really cheap。And it's very well performing。

 We know we can go really， very， very fast now。The problem with Internet。

 it is an asynchronous protocol。 And so we have the allvation nondeminism this and up and down。

Given the fact that you can funnel through a lot of data very， very fast。

 there are some people who say， who cares if I don't。

Have determins because the network is so fast that no matter what Im capable of responding to all the reactions of the system。

 so I don't have to worry about it， is immaterial because everything can be taken care of。

Now it's fine as long as you talk about computers， it's fine as long as you talk about toys and robots。

 but it's not fine if you talk about airplanes and cars。So the idea is that can we combine the two。

 right， can we build up a network that has the characteristic of being time triggered。

 and yet the physical underlining system is infinitether。The answer is obviously， yes， right。

 because I can use as a physical mechanism， a lower protocol ethernet。 But on top of it。

 I'm building something that makes it behave synchronously。Now， this is the direction of the future。

 Everybody is doing this。Do you have a car， do you have a plane that works on Vis， not yet。

But every single car company， every single airplane company that I know are thinking about this ethernet plus synchronous protocol。

 Now， one ways to do Tt ethernet， other ways are the AV ethernet， which is similar in concept。

 but is。Synchronizing ether， right So that's the future。



![](img/895cade4d879c02867c27629670eca43_47.png)

We say before that state messages are intrinsic in the notion of synchronous and event messages are intrinsic in the notion of event event comm。

 so an event message contain event information are queued and consumed so there must be a queue that you have available at the computing node so that every time something comes in goes into the queue every time you free time you consume an element in the queue。

Now， of course， risk white is non deterterministic because risk has to be finite。

I cannot have an infinite cube and so by some reason。

 the data come in really fast and I'm slow to react to this data。So happens at some point。

 something gets dropped or something gets overwritten。And so I don't know。 It's nondemin behavioral。

Who knows right and that's one piece of the problem。

They state messages we say before is time trigger。 So whatever I read in the data。

 that is my message。 right， So in the output buffer， that's what it is。

And so I don't have to worry about overr， I don't have to worry about cues。

Body b is plenty good enough。 It's all I need。 So no cus none of。Of course。

 the problem with the state messages is that the state may not be the real state。

And so that's the reason why we have to keep the boundaries of these lots close to each other。



![](img/895cade4d879c02867c27629670eca43_49.png)

Now， so the comparison between eventer and tight communication schemes are。Right there。

 So event messages are in the event trigger， and state messages are in the time trigger。

Now the temporal control is derived from the occurrence right and so it is unpredictable because I don't know which data are going to come。

 I have to look at all possible data streams that can ever appear to decide what is the situation。

Now， on the other hand， in the time， the temporal control is derived from the progression of time。

 and so it's predictable。😊，That is the determining factor。

The event trigger a nice thing is it's flexible because whatever can go。

 you not just plug in a component and everything continues to work， but on the other hand。

 the time trigger in information is about interoperability so that the information can be exchange in a controlled way。

You have large jitter in a vent and of course minimal jitter because you have these boundaries that are sloting the time and so the maximum jitter you can add is the interval between the two boundaries of this slot of the TTP。

In the event trigger you have no precise temporal specification of the interfaces。

 on the other hand in time trigger you have precise temporal specification is very good for sporadic data。

 the event event but is very good for regular data if you have a time trigger architecture。

The memberships of finding out something is broken is very difficult。

 on the other hand in time trigger is easy because of the assumption that you make。

 you have a probabilistic access to the bus or to the communication network on one case and you have a perfect deter is given by theplication of the cycle。

So this are trade。Now， there are situation in which one solution is better than the other。

 and you have a situation where one solution when both of them are not so good。



![](img/895cade4d879c02867c27629670eca43_51.png)

And so how can we do better when each one of them is， of course。Putting it together。 So ethernet。

Is a asynchronous mechanism and so the asynchronous communication。

 the transmission points in time are not predictable and in general is used by very high speed。

 so the imppredictability is covered by the fact are so fast that you hope that no overlapping or no contradiction between data is ever going to occur。

Now the motivation for internet， as we say before， is then low cost， extremely good performance。

 there are lots of chip providers that do internet。Chipps。And so。

The idea is to combine the time trigger architecture of the internet so the lower level is going to be internet and on top of it is going to be TT so all messages。

 the idea to do in the TT internet is to have all messages that are compliant to the internet matter so that existing tools can be leveraged in both cases。

 both for the internet and for the time trigger information。

So internet compatibility enables the user technology that is continuously evolving。

 is faster and faster and is cheaper and cheaper。 So this is very appealing for every company。

 The The problem is that again， it cannot be predicted。 So how are we going to to combine the two。

 So you have crossword communication， which is the。Synchronous approach。

 which is high cost because you have to have synchronization of the clock。

 you have to have controllers of the network， you have to have controllers。

Everywhere the open world communication is there this ethernet and asynchronous domain。

 which is certainly low cost， but is not trustworthy and so there is a market quote unquote between the two。

 Now this one are slides that are provided by Tt tech。

 which is a company that sells this idea of combining Tt with Ethernet。And as I said is the one。

 it is dictating the protocols， the item poly protocols that are going to be adopted as standards in this domain so that's the reason why I am showing you these slides because this is the way of the future。

So not only the interest in T T Internet is because of a low cost and so on。

 but also because there are many systems for many large scale application in which the criticality of the components are different。

 or the messages are different。So there are things that are really critical and you want to deal with them with the time trigger protocol and there are things that who cares。

 are sporadic and doesn't matter if they are really gotten the way in which we are supposed to。

 And so the idea of mixed radicality system is to have particular。

Los for these non critical messages to be communicated as synchronously。

 so I would like to have an overall synchronous mechanism in which I can take care of non important messages in I to say。

 cheap ways。 So there are two。Approaches to take care of this asynchronous information。

 which is paraoradic and is not so so important。 One was given by a protocol that became very fashionable in the past few。

5， six years in cars you find this protocol is called flex rate a flex array combines these two kind of mechanism。

 but in a very constrained way and flex array controllers are even more expensive and the TTP controller。

 So there was a time in which these things were included in the cars。

 but the advent of the TT ethernet and AV ethernet is the way of the future is much less expensive and much more perform。

 So that's the way in which you are going to go。 So this combination of ethernet and timeger protocol。

As they。Nice feature that combines several traffic classes where a time trigger。

As we say before so we kind things that have to be absolutely safety constrained。

 but a rate constraint， which means that there is a constraintss on the rate in which this data occur and best effort and best effort we say this is a basic mechanism of internet communication and computer usage。

So time trigger level dispatches messages according to a predefined communication schedule as we have seen before。

 the rate constraints in four minimum duration between two frames of the same stream and best effort is standard internetthernet which is the standard asynchronous communication so that is the way in which the TT Ethernet packages the messages and you see that there are in between time triggered windows。

 there are things that can occur whatever right so these lots are assigned to communications that belongs either to the rate constraint or to the best model。

 as you can see then time triggers lots are very well assigned and they always occur in the same way at the same cycle but all can occur wherever so you can think that there is a layer of application which is sitting on the time trigger extension of the Ethernet。

So there is a basic protocol on top of it。 There is a。Protocol。

 which is time trigger on top of it where is all the application layer。

 so the application layer looks at the TTthernet as a set of services and the service time trigger communication。

 rate communication and asynchronous， full asynchronous communication are best effort communication。

So it a communication infrastructure when you have the various time trigger ethernet switches and you have the various attachment。

 if you like， but can be anything at all， so you can have parts that are can network in for example。

 for communication of low importance nodes in the network itself there are for example。

 Tx Fx and slots which are flex ray slot and that are safety critical elements and you have TTP buses that can be attached to it and so it is an heterogeneous way of combining any kind of protocols you can dream of with the I would say infrastructure that is extremely wellperforming and extremely cheap so that's the big appeal about TT Ethernet which can be applied hence not only a safety critical but can be applied to anything in the world giving variety of different。



![](img/895cade4d879c02867c27629670eca43_53.png)

对。So its the end of the class about tiny protocol so you see it is a synchronous mechanism。

 but you see all the complication that you need to deal with when you want to implement a synchronous mechanism for distributed system so you have to deal with。

Communication， our communications taking place TDMA。

 you have to deal with how the single nodes interface to a TDMA communication。

 so you have to have this notion of the snapshot of reality or realtime images。

 and you have to study a way of transferring this data into the TDMA。

Saw right so all the combination of all these things then yield a way of implementing a synchronous mechanism onto a physical system which is made of nodes which are connected together by wires can be 10 kilo slot。

Now of course the goal is also to eliminate a lot of these wires and to go down to very few ways now how can you do that only if you have very high performing networks and so that's the reason why Internet is so important and that's the reason why TTE is such an important protocol for the future。

 it is implemented today， not yet。好ですね。Well， the time trigger model is essentially using time is like this notion the time determines with loss so the Izoronous model is an abstract model。

 so the time trigger model is an implementation right iszoronous is an abstraction。Of the of the。

Of the communication， which occurs at the same time。

 So you can say that the time trigger is a way of implementing these optimal。Because is okronous。

 as the reward says， it happens at the same time， iszochrons。

 but that is an abstraction mode and now the timeator is a way of making sure network communication is okronous。

 but it is not in logical time， it is is okronous， but is not really isocnoous。Exactly。Exact。

And so again， the implementation and it has to take care of this issue of the fact that when you lot the time。

RightYou are doing an approximation， so it's an implementation issue。

And so the class today was about， again， explaining how that implementation goes。 in fact。

 time trigger。Architectures， we are talking about architecture and protocols。

 we are not talking about tiny triggered models or abstract models right you could do that but is rather complicated by way。

 all of this can be formally verified because it's a synchronous model and you know the only thing that is almost unverifiable so there have been people who have formally verified with protocol in the architecture so you can be sure that there is no error。

But the thing that makes really life difficult。 can you。

 can you imagine what it is the most difficult thing。They will guarantee。It's not obvious。

So a basic scheme is can be formally verified。 So all the synchronicity and the time trigger get pro everything is fine。

 Its very fault。Toance part of it。Because you have lots of assumption about the full model。

 and then you have to see this membership function， how it works。

 and so making sure guaranteeing that if something goes wrong， you can see。It is very tricky。

 So there is no form of proof that is going to happen。Okay， so。That is the most difficult part。

 So you have to deal with simulation or analysis or whatever you want to do。

 But everything else I say is。Formerally verified， which makes this thing really robust also for even defense application and the life。

In fact， most of a defense application already。D TB since long。Okay， other questions。

Call it today yes until yeah there is an announcement。

 so remember that you know you have to apply for the reding and the deadline is this coming Thursday。

Y。Next Tuesday， okay， so after that， you are dead， okay。



![](img/895cade4d879c02867c27629670eca43_55.png)

不 them啦。