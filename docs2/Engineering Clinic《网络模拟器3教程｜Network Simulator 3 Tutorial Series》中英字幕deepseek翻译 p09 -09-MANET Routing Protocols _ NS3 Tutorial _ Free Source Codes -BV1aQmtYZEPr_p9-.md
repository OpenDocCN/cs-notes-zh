# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p09 -09-MANET Routing Protocols _ NS3 Tutorial _ Free Source Codes -BV1aQmtYZEPr_p9-

Good evening， France， Wele to Engineering Clinic。Trey。

 I am going to tell you about a new project called less comparison of man routing protocols。

These four protocols we can enable to compare AO Dv and DSSTV， DSsR。

 wirelessR using network simulatorulator 3。So if you are a final aid student。

 if you are planning to do your project of for B tech E tech。Or even PD。

So you can first step is you can think of some project where you can able to understand the networks。

 understand the wireless networks and their protocols。

 So this is where the place that you can land upon doing where a project work。

So this topic can be related to reactive versuss。Proactive routing。Protocols。

Performance comparison of。Mannet protocols。Then A O DV versus。DSDV comparison。Like this， you can。

 you can do this project。Using this network simulator 3 tool so。

You need not purchase any project anywhere， so just listen to this lecture because but this lecture will be crossing more than one hour。

But I have just give the detailed explanation of the source code。

 as well as I will provide some extra source code for a your results and you need to have Python libraries for plotting the graphs and the characteristics。

 Okay， so all these things I will be giving in my blog also。

So all the source code I will be sharing freely through my blog。NSAname。t co。And also。A they。

At my channel， so I will be publishing the source code in my channel as well as in my blog。

 so you can refer my blog also for downloading the source code on the full explanation okay。

So having said that will be going into directly into the source code So you need not write any source code here N S3 comes by default with the source code。

So before that what version I am using I'm using version N S hyphen 3。29。

 but he can use any version N S hyphen 3。28 or 3。27 or 3。26 etc。 you can use it。

 but I am just taking 3。29 version this this is what I I'll be dealing with it。My U to ois。

my Uo I is U to 18。04。 So that's what I'm using here。 can check it here。 It is LSB release。

 I can see that I'm using 18 point。0，4。Okay， so just the terminal is coloured in blue and black。

 So it's for my convenience。 So well go to the source code。 So initially， N S 3 have a source code。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_1.png)

I'll just open it so we will just go inside default folder in allline 13。29。Inside that N S 3。29。

Inside that examples and inside that routing。 So inside this， we have so many examples available。

 So if you are planning to do so many examples and you can try out all these examples here。

 So we'll be doing on example call man routing compared CC。

 This is a file that we will be using it now。 So what I do is。So， this is the location。

So home networks， sendna or 3。29，3。29 examples， routing， Man routing compare CC。

 So this is the file that we are going to use it。This file， we are going to use for。Simulation。

 but simulation takes a little bit of time， but the analysis takes more amount of time。

 So if you are an engineer， you have to do the analysis to a greater extent， okay。

So first step is step 1 S。Copy the above file into。The scratch folder。

So you assume that you already know Ns3 the basic folder structures of Ns3。

 If not you please refer my previous videos to understand the introduction to Ns3。

So inside this folder， Ns 3。29。We have a folder called a scratch folder。

 So just copy and paste this file into the scratch folder。

So what I do here is I'll just copy this file。And you can see N 2。39。

 This is a place where we have a sketch folder。 I'll paste it here。

So already I have this file now I will be replacing it。So Ill just pasted this file。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_3.png)

说。You can see this here。Scratch， so you can see this man routing comparecc。

 So this is a file that we will be dealing with now。 So first what I do is I' just open this file。

 So let me explain the source code completely to you。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_5.png)

You need patience to listen to the source code。Because most of the people are struggling to understand this source code mainly Nus 3。

Because NS3 is completely dealing with c plus plus so understanding the source code is not a very big task it is a very easier one when compared to NS2 the source codes are in TclL where we do not have any idea on how TL works but c plus plus since we have been practiced to use c plus plus so it is very very easy for us to understand the source code in c plus plus so first let me open this file。

So this is 5， I'll just max。For timing no。So this is the file， so already N S3 comes with this file。

 so just for the comparison of the routing protocols okay so in case we want to read the commenting line mean some information they have given。

We can check this this example program allows one to run NS 3 A DSSDV。

 AO DV O Sr at a typical random waypoint mobility model so you can use this mobility model。

And you can run these three protocols by default， the simulation runs for 200 simulator seconds of which the first 50 are for start up time。

The number of nodes is 50 nodes move according to random waypoint mobility model with the speed of 20 meters per second and no past time within a 300500 meter region。

The wfi is in a dark mode with a 2 M P rate with a standard of 8 or 2。11 B and a freeze loss model。

 the transmit power is it to 1。5 dis。So that's what we are given here。

 So we can read the complete information if you want to know more about it。 So first。

 let us go to the source code。 So we have。F file stream， myvo stream core model， network model。

 internet model， mobility model， A DV model wireless or model DSDB DSR applications and Liance's Wifi helper model。

 so all the headerophils have been included。When we have namespace N 3 and DSsR there are two name spaces because DSsR needs a separate name space。

 so that's why they use DSsr also and we have Ns3。And the total log logging is manner routing compare。

 So whenever you try managed routing compare， you can directly execute this example。Okay， so first。

 we have a class routing experiment。 We have a class。 So， you know。

 a C plus plus class containss public private and protected members。 So under public。

 we have routing experiment and then is a constructor。And there is a function called as run。

 So this run function will run with the number of sync node， sync nodes transmission。

And as CSV file name a name of the particular file and in the command setup we have argument counts on the argument vector。

 So this is for contracting the routing experiment。Now， next thing is in the private part。

We have a pointer to the socket it is a template libraries set up a packet receive with the IP version 4 address and the node so the node with the IP IP version 4 that is what the receiving the packet and receive packet function it deals with the socket number so whenever you have the socket number as one of the parameter so the receive packet will be。

Pet will be received via a particular soet and check throughput so you can check the throughput of a particular。

A network。And unsigned into the 32 bits。 So we have port。

Which port number and the total number of bytes the packet is received。

And we have a CV file name which file we are going to record all the data。

 so that is a file name and number of sync notes and the name of the protocol。

And trans power trace mobility。And the name of the protocol。

 which I am going to use because there will be four protocols of what protocol we will be using。

 So thats what here， this routing experiment。So the first class name is class routing experiment。

 so we have one constructor and we have some functions So how we define these functions on constructor we see。

Now in the routing experiment， there is a conceptor。

So I'll write it there so that you can understand。Constructor so port number  nine total bytes is by by making a 0 by packet received 0 The name of the CSV file name is manner routing dot output do cv。

 This is a file that we are going to use trace mobility So whether you want to trace the mobile mobility means mobility of the node you want to take a trace if in case you want to make it true we can make it also initial is2 false and the name of the protocol is2 So we are using E D is 2 and well see what is one what is2 and what is3。

We see head。Yeah， you can see。 So there is a switch protocol switch case function。

 the case1 is for YSR， case2 for A D， case 3 for DSSDV and case 4 for DSR。

So the protocol 2 is used that means we are going to use A protocol。So you can name accordingly。

You want to use A D v or the name of the file。 So here manner routing is there what I do is Ill use a file name call A D or CSV。

 So for each protocol I will be changing the name according to the protocol that I am using。

 So first I will be conducting an experiment on A D protocol okay。Right。

Next thing is print received a packet， so print received packet means so what packet I want to print it So in the terminal So further what I use I use a socket。

 a packet and an address who is a send address。And string O string string means the string is been sent to a particular file。

 so I create an object。This object is outputting。 So even when you are dealinging with C plus plus。

 you can be using something like the C out。That means you are sending to the file output。

 so similarly here voice is sending out to simulator now dot get secondary at this current time。

After a blank space， then so or get node get I， so get the node and they get the I so that will be sent there。

And the center it is matching。Then you can send a message that received one packet from so on so node from the IP address So this we can see there's an output terminal when we deal with it。

 supposeupp if it is not from an IP address， then received just one packet so but we if it don't if it doesn't know the IP IP address。

 then it will simply print a message called us。This you one packet， so this will be for。

Print the received a packet。 So how many packets have been printed。

 So that is what printing they received a packet this one function。

Next thing is receive packet function。 So in the receive packet。

 we have the parameter socket and we have a packet center address。

Well packet equal to socket do receive from center address。

 then bytes total equal to bytes total plus packet or get size。 So that means the number of bytes。

The receive packet the number of bits received so the bytes will be keep on adding and similarly every time when the packet is get added it increments to one value。

Okay， so that is what the receive packet。 next thing is check throughput。 So throughput。

 it is double kilobits per second bytes total into8 divided by thousand will give the value  in kilobits per second。

And that will be recorded to a particular file name colors MC file name do C stream and i app。

 So that is input output stream So what are the data record is the throughput。

The packets received the number of sinks。The protocol name， the trans， I mean， trans power。So。

 these things will be output to a particular CSV file name so this also will be seeing okay so the firsttive value return is the current time simulator now dot get seconds so after the file we get the file Ill just tell which component is compared to。

What data record is in the file？Once the file is open， we have to close the file。

And packet received and schedule the experiment。Now， set up packet receive。

 So now we are to set up the function for receiving the packet。

 So far that we have a UDP circuitet factory。And then we have a sync node。

 so we have to open a soet or create a circuitet and then open it。Then。

Make a call back to the routing experiment， receive packet。 So that means receive set。

 receive call back， make call back routing experiment， call and receive packet。

 So that means set up packet receive function well call the receive packet function。

 Now we can just go to the function here， class。So this this function we are writing now。

 this function will be calling this function。So the first function will be calling the second function。

 so that is what the code written here according to the logic and the return sync so this is what they are setting up the packet receive function。

Next thing is command function command setup we have one more function called command setup here we have a CSV file name trace mobility and protocol so we have a one means YSR2 means AW3 means tV4 means DSSR and enable mobility tracing so in case we want to add mobility trace you can enable it the name of the CSV output file name so in this case now we have the file name call A DV。

AndRe the file， so the first level class is over。First class is over the name of the classes。

Routing experiment。Now we have a main function。As every C+ plus program starts with the main function。

 so we have a main function。So we can see that the routing experiment experiment。

 So there is a fast fast class it is been called。The class is called。Object is created。Okay。

 now the CSV file name experiment dot command setup argument count argument vector。

 Now we can see CSv what is the name of the CSv file name experiment dot command setup so command setup in this function So this function is called here。

We have the CSV file name here。And。Will be sending all the data as a string Okay。

 so what we send simulation second receive rate packets received number of things ro protocol and transmission power。

 So these are the values will be sent to a particular。C SV file， okay。

 so a number of things notice 10， then transmission power is 1。5。

Un experiment dot run n 6 transfiion power and CV file La。 So this is the run experiment。

 you can see the run experiment run function where it is。You can see these are run function。

 so run function number of things trans power and the file name， so this will be running。

Inside the main function。 So it's very easy to understand this code。

Okay now in the run function when we implement the run function number of things trans power on the CSF file name first we use enable printing so packet enable printing so first we are enabling the printing so that the packets while data will be printed。

Then M underscore n 6 equal the n 6 because this function is mapped with this。

 So hope you remember this logic here。Maybe I'll write it down here has more logic。

What I do is function integer A comma integer B。So what we do use here is。

They study equal called today。We'll be using this dot be equal to B。

 So we'll be using something like this Rls， the class value is X。

 So we'll be using x equal to y and y equals B willll be using this。 So that means。

The class variables are compared to the。Parameter variables。 Okay。

 so this way we will be adding the same way here in C plus plus， they will be using the。

We have different variable names。 So here they use n6 here they use the underscore n6 in the class variables。

 So here you getting this so whenever you send the run function when now the number of things here it will be allocated to assign it to this value and this will be this value and this will be to this value。

A number of wfi nodes is 50。 so this value this you can control as per wish。

 So we are going for 50 nodes first later we can go with  hundred nodes if we want 50 nodes through 0 nodes whenever you want to compare any results。

And total time is 200 seconds。Don 2048 bits per second， so there is 2 kilobits。

And the physical layer mode is D reless radio with11 B speed。And the T R file name。

 So now this also will be going for Yvo D。 So first we will be changing the name to Evo Dv don't give any extension because the extension is been at attach attached at the end in all the。

Examples。Okay， node speed is 20 m per second and node pass there is no past time between the nodes。

 so there is 0 and the protocol M is according to the protocol one means O SR 2 means 0 D V 3 means DS SDV and4 means DS SR。

And on of application so string value is 64 and data rate is the rate so rate is 2048 and the packet size is 64 byte so as enter the 64 in case you want to increase the packet size you can increase it。

So that the packet phase will be increased。Then we will have the re wfi remote station manager non Unicast mode。

 So that means the package what already been sent will be sent to all the node。

 It is not reference to one particular node。 it is for a non Unicast。Okay。

 so now we will come to NS3 codes Note container ad hoc notess。Create the number of wfi node。

 So N wfi we have a value call us 50 so we can see that this value is 50 so we are creating a node for 50 nodes we are creating。

 So if you want to know more about this refer my other video on introduction to industry or wired and wired application wireless application in industry will understand to a greater extent。

Then we have a wfi helper， wfi。Then set standard。 So what standard we have will be using will be using 8 2。

11 B B standard。Then we have we have to set the channel s layer， all these six Mac layer。

 So yarns wfi helper So already we have told you about this yars is yet。Another network simulator。

That's what Dan refers to。So they have a physical layer with a default set of parameters and channel we have a wfi channel。

The propagation delay model is constant speed propagation delay model。

 so that is a channel propagation model and freeze propagation loss model we have So if you are a electronics and communication warranted student you can try out these propagation models。

And create a wfi channel so that is for creating a wfi channel so whenever the channel is open channel means is the communication part whenever the channel is open how you want to deal the losses and how you want to deal the propagation So further what kind of model you will be using。

That's what we mentioned here。Next thing is rate control and Mac， so we will be using a Mac。

So here constant rate wifi analysis。 So that means irrespective of the users in the particular network。

 everyone will get the wfi at a constant speed。 So all the nodes will get the constant rate at which the wfi。

 the wireless services will be provided。And here we have Tx power start transmission power start and times power end so that means without affecting the trans power everyone will get the concentrator and the name of the wfi mag is ad hoc Wifi Mac so there are different wfi maxs available in NS S3 so in case if you want to compare the Mac protocols of these wfi you can adjust this parameter。

I talk about F Mac。And install these wfi Macs into the Ad devices， wfi， PHY， wfi Mac and Ad notess。

So， that means we have an database container so again these are all the theoretical concept behind NS3 I already have a detailed video on this in my channel so we can refer the channel。

For getting to know about the particular information on the Vi wire network and wireless networks。

So I have explained to the core。So you may not have any doubts when you refer to that video and then come back to this video you will have a better clarity。

And mobility helper so mobility helper means on what kind of mobility models this node will。

Work so further we have random rectangle position allator。

 So that means how the nodes are positioned the nodes are positioned in a rectangangleular fashion that will be allocated in random So the x axis will be minimum 0。

0 and maximum is 300 and the y axis will be minimum 0。

0 and maximum is  thousand500 so we can say the thousand500。

 So we are entire x y axis will be 300 cross  thousand500 So that is what here meters。So。

 that is a random rectangle position， so the nodes will be positioned according to the random function defined inside this position allocator function。

Next thing is create the position allocationation and assign the indexing there。Okay。

 and the node speed because all the nodes cannot be maximum speed of 20 me per second。

 but they can adjust the speed so far that what we do is we use uniform random variable here starting from 0 to maximum of 20 me per second。

 So that means the node can move at a minimum speed of0 at a maximum speed of 20 me per second in between they can move Similarlyly the past time is0 and node passes also0 So there is no value of past time so it is0。

Okay now this also you allocate to the particular mobility attack and will be installing to the attack node so every node will be positioned before this position allator the node speed everything will be given to the nodes。

Now we will come to the protocols so how to design the protocol so in case if you want to write only for aW protocol if you want to design a source code you can use this example to design your source code if you want to do only YSr you can do that if you want only DSSDV you can do that。

So now in the protocol section。Now in the protocol section we have see that A DV helper。

 A DV OLSr helper， DSDV helper DSR and DSR will be since it is using caching so it deals with the different source source files so we will be using another class also main DSSR main helper。

Then protocol so we can use case 1， case 2， case 3， case4 and default。

So we have the listed at OSR 100 A00， DG100 and DR protocol。If it is less than4。

 then you set the routing helper that means the list will be added here。If it is equal to 4。

 then it will be for DSsR。Else， there is nothing else。

There is no such protocol it will be giving you no such protocol here。O。

So assigning I now next thing is we will come to the network addressing So addressing also I explained in the greater extent in the previous examples we can refer that So IP version4 for setting the node10。

1。1。0 starting base address and this is the。Sub masking address so you can check that you can use your own addressing also here。

Then on off helper so we will be using on time and off time。

 So the constant random variable will be the on time and off time is 0 on time is one。 so thats what。

We have mentioned Dehir as honor of helper。Then packet receive。

 So number of nodes it's varying from I to number of sinks。

 number of sinks means how many sink notes。We'll go to the top and come back。

The variable allocation number of things。Number of things。 Yeah。

 number of things you can see that are totally。10 en is 10。So here it is varying up to 10。

 so pointer sync equal set packet receive adog interfaces are get address of I means this I will be varying from 0。

12，3，4 up to 9 and get this value up to 9。Then get the address of it。

 And that's what this remote value。 So address value remote address and get address of I comm port number port number where is port number 9。

 So that means the nodes have to know which port number。The packet has to be received。

 so that's why we use the port number over that。Un starting time is， can see that。

The application container temp one of install or getta i plus number of things。

 So that means the node of get i is varying from 10 so 10。0 plus 10，1 plus 10。

2 plus 10 like that 1011 tool that up to 20 values so that will be incremental and the values simulation will be starting somewhere within 10 to 200 an。

1。0 and star will be the total time。 So total time already we have seen is 200 seconds。

 so it will be stopped over there。Next thing is。What are the things to be output or how the things will be output。

 So again， number of wfi not 50。That is what given here and node speed。Nor pass。

At the rate at which it works。And this data will be recorded to the particular file name。

So these value is commented out here， so we will enable as and when when we need it。

 we will will enable1 by one。So here we have ASI trace helper ASI。

So we want to enable the ASI file stream here。 So mobility helper enable AS key also So that means we want to enable the mobility trace。

 So if you want to enable the ASI。It will be sending to the file call T R name plus dot mob。

 So that means T R name is we have given Yvo D。 So Yvo D dot mobile file dot mo will be created。Okay。

 on flow monitor， they have given it。Flow monitor。 So I enable this。

This is one another very powerful tool。Powerful。To。In N 3 called us。Flow monitor。Flow monitor。

This will create a。Xm L Phi。And。One can use Python。Eleementary。To passse this。

So we will do that we will do that。 So that's what here the flow monitor。

 So Ill enable the flow monitor also here。So pointer these are the three lines。

 so any NS3 file you can use it and the。On this file， you can enable these three lines， Per， pointer。

 flow monitor flow1。Flow monitor helper， flow on helper， flow1 equal to flow1 helper or install all。

 So that means it will just install this and you can take packet drops as packet traces so everything you can able to take。

Okay， so these three lines and this will be recording the data to the Xml file the name of the Xml file is it will be always after the run function。

 so flow monitor code alone will be always initiated after the run function。

 So comment uncom this line also。So flow1 dot serialize to X file Tr name dot flow1。

 so this file will be created。And that will be。Getting created in the folder where we run this example。

 Okay， so this is so how many files well be creating， we will be creating on dot flow on。

1 file and a dot CSV file and we have a dot mobility file， so we have a dot mop file。

And we have something like dot mobility file， dot cv file。 So we will be creating three files。

It will be recorded。 So how to run this example will come to this now。So， once。

You understand the code。Now， let's。Then this example。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_7.png)

So， what we do is。So， step 2。Run this code。 Okay， so that is step to use。

Understand this code is already done。Now we go to step 3， run this code。

So what we do is how to run is go to the folder。So as to open the terminal。Open the terminal。

Go to NSS Sphon 3。29。L that。F link command。Dot slash web double a and run。Scratch slash， mannet。

 hyphen routing hyphen。Compared， So this is an example。 So what do we do is。嗯。CD in this。CDN S。

 then dot slash v， w if and run scratch。Mnet roing Comp。 So for C file。

 there is you do not specify any extension。To run。And， run this。Now。

 you need to have patient enough because the simulation will be running for 200 seconds。

So till that20 second， it will be reed。 so now we got an error。Flow on Cized to Xl file。

 so we got some error over here。We have got some error here， so we have to correct this error。

So the reason being is it doesn't know what is flow monitor。What is flow monitor it doesn't know。

 So that means we have to include in the header file。So what I do is， so the headophil is missing。

 So what I do is here。Ash include。In the three slash。Sorry， NS3 slash。flow气分。

Monitor hyphen helper dot H。So there is a file color flow monitor haven。Tot， now Ill turn it again。

Because for enabling flow monitor immunity enable the particular helper files。I think now， yeah。

 now it got compiled。So please remember， whenever you enable this。

 please have a note I will write it here。So the what I'm typing here。

 I will be giving at the description side in the below the description of the video。

 So re enable the。The following headphy。Haash include。Within double codes， in3 slash。

Flow hyphen monitor， hyphen helper dot H。Okay， so。So this is here to enable it。Yeah。

 now we can see as per the simulation。 you can see it starts10 because we have seen that 10 to 10 and 1。

0。The simulation was running。 so maybe I'll just show you in the code。C  hundred。0。

 so you can see the value starts at10 to 20 and1。0。 So this is where。This function was running。

This temp start start。 This was running。Okay， so that's a。It is starting here。Okay， so we'll。

 well wait because it takes some time。For to get process。 So I evaluate。

I'll just pass the video for time being so that once 199。9， it comes here。

The simulation thing gets over。 I'll pass it。Yeah， back。 So we can see now we have 1，188。

94 note number 3 received one packet from this I so like this we have。

Go recorded these mean information。In this file。 So the same source code what we have seen here。See。

 received one't packet。You can see mostly we have IP address。

 The packets have been received from different IP addresses。Okay。

 so if you want to record these data into a particular file。 So then what we can do is。

The same command， dot f， double A and run S scratch manner routing compare。

And I can give this amperserson。We than symbol and temp。Dot data。

 so you can send this data this output together。Particular。Temp on data file。 So all the output。

 whatever this is recorded will be recorded in a separate file。Okay。Okay， now let it go as it is。

 So now what we do is now we will process this file。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_9.png)

I'll just open it。 So what I do now is now we will see the files， list of files。So we have a E CSV。

 E E flow1， E E M V， So we have totally three files cards generated from this script。

I' will open all the files。 Avo D v dot star。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_11.png)

So F I'll just open these files。So you can see here simulation second receive rate。

Packers received number of things， a routing protocol。And transmission power。

 So all this information。So first thing is simulation second0 and received at0 packet received0 number of sync is10 Y D protocol。

And 7。5 is the drive。Okay， so this is one。C record。 Next thing is a D flowmon。 Actually。

 now the file is going on now。Because we already run this example again。

So you can see that after 100 only the simulation started。I mean，1 not1，5。

632 is the received rate and there is the received packet under this thing。So still， it will go。

And these are flow monitor。 we can see that the flow monitor file is。

You can see it will a flow ID and time faster transmission packet at what time it have sent and time for our receiving packet。

 time loss transmission packet， time loss receiving packet， delay some lost delay receiving packets。

 lost packets， transmission bytes， receiving bys cheatter some times forward forwarder。So like this。

 you can see the number of lines of this file will be crossing。呃。Aund 10000。

So you can see total number of length is 1065。 So this is an X Ml file that can be processed。So。

 flow I。So this is very important file。 we call it as flow monitor。 and one。

 if you know how to process this file， so then you can able to play around the results of this。

F monitorator。And this is a mobility file。 So at 0。0。

 not 0 where it goes which position and not what as what speed。So， maybe。We'll go with some。

Modify the timing。Because the simulation happens only after 100 time minutes。So。This file。

 So if we that mob we that flowman。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_13.png)

And they what we do。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_15.png)

So let it go。 So actually let still again this running。 So once it is done。 So we have three files。

Anyway， I'll just get it。So， three files got generated。Evo D cv， Evo D mob， Evo D dot。F on and。

F mana and one more file this file。 So again is template data。So， four fights。

So now when you see that number of nodes。50 number of things。等。Then mobility model。

The propagation model。Last model。Proagation loss model。So， it is freeze。The propagation model。

Constant speed。Proagation delay。And position allocated。Pos allocator is rectangular random。Random。

Rectangular。 So whenever you are doing any paper， when writing any research paper。

So all this information is mandatory for you and Mac。Or wfi Mac。And max standard。So8， not 2。01 b。😔。

Then throughput bit per second。2 K B per second。And the number of nodes is 50。

 So in case we want increase the number of nodes， we can use so total simulation time。Ne seconds。

And speed， not not speed。20 m per second。Then node past time。0。

 so these are some of the parameters that we have calculated。Okay。

 so these things you can able to write and protocol finally。Protoal， So A O D。 So like this， you can。

对对。Okay， so still it is being still the data has been written here。 so we will wait。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_17.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_18.png)

Okay， so。Hope you bought it now。 So now what I do is。

But after this data get ready only we can I pause this video now。Yes， so now we got all the files。

 So I'll just show you the files。All these for failure what CE， A flow1， A we M or be okay。

So now I will go with A DV dot flow1。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_20.png)

First， let me go with this。Okay。So， this is the file。So using this file。

 I want to re record the information。 So I already wrote one code cut float or python。

I return a code of load or Python。 So what I do is So this is a Python code。

 So even if you don't understand， Ill give the code， we can make use of this。 So from Xl do E3。

 So I want to pass the Xl files。Accussing the element colours elementary as E T。

So system I am importing un map plot lift for plotting the library and I use the variable name gal pile lab。

 So first I will be using E T called to E T that parts。

 So that means the elementary I am going to passse the input file through argument vector 1。

 So bes a real list I am making empty list losses until delays。Okay。

 so now for flow in E T dot find our flow stats dot flow slash flow。 suppose， for example。

 if we want to find all this。See， these are flow stas。 Okay。

 so flow stas and slash flow means the next cycle flow。 So we will be coming here。

 So first thing is flow stas。 Next thing is flow。Okay， so afterward if our TPL。

In E T dot find IP version for flow classifier slash flow。Again， I'll go inside。

So I pick and inside this also a have flow okay。F and destination board number 6，54 is there。 Okay。

 source board is 60 destination board is 6，54。So， next thing is。In the case。

 if T PL are get flow equal to float or get flowid then break if TL are get destination particles 654 continue So as long as 6 to a destination body continue Now last is that happened float get last packets。

 So let me go and copy paste this。So you can see the last packets values are been calculated。Okay。

 how many last packets will be calculated okay。So then rx packet equal to floater get Rx packets if rx packet equal to 0 bit rates start up n 0 because if there are no packets。

 then no packets are been received else time first Rx packet and time lost rx packet and duration is even minus t into 10 power minus-9 and bit rates start upend floater r x by divided by duration into on 10 power minus3 So they want to convert into seconds that's why bit rates bits per second kilobits per second then delays start up and float delay sum and again we are using the request packet so I am getting delay also So now plotting the characteristics sub plot。

A bit rate total number of binary is 40 so flow bit rates the first graph number of flows and bit rates。

 number of last packets， number of flows in the way axis and now delay in seconds in the X axis a number of flows in the way axis Now horizontal space is point4 and everything will be stored in the result start PF file So this byy screen I got from my internet somewhere and I just modified aspect to make convenience。

 So in case if you want to analyze some data from this flow one file。

 you can able to find it out now Ill run this file how to run this file。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_22.png)

So what Python。So let me clear it。排单。<|OTHER|>I'll just update this here。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_24.png)

To run the flow on file。Use of temper Py is。Advised。To run the file。Use the following。

So there is the prompt of use Python float or Py space。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_26.png)

Avo Dt flow1。 So this is a commander。Pyon。Floer P A D v dot。Flo one。So once you have done it。Yeah。

 now it is done。 So now we will check the P F file。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_28.png)

The results are P file in the。All in one。 have we got the results start by T。

So here the number of flows in the way axis everywhere and the excessive flow beat rate bits per second。

 So how many bits per second and number of lost packets across time time duration。

And delay in seconds will be the duration here。 A number of flows will be this much。

 So this is a simple graph that we can able to analyze the flow。

Moniitor this monitoring the flow packet flow in the particular network。

So this is one example where you can able to plot the characteristic using the Python script。

So find the Python script here。So that you can download or you can download as a file also。Yeah。

End of script。Okay， so now we'll go to the next file。

 So flow1 let me close it and flow pi will let me close it。

 So please remember all these examples we are doing only for node 50 nodes。

 suppose in case if we want increase to 100 nodes， everything else will be changing。

 so you have to work accordingly。So let me go with the CSV file。 So CV file， what I do is。

First remember，7。5 Y would E V10。 all the last three columns are constant columns。

 So let me show you how to do this。Please remember this simulation second receive rate packets received。

Number of sinks and routing protocol and other things I don't want。

 So what I do is Ill just remove those things。So let me use only these three packets receive receive rate。

And simulation time。 Okay， so I will receive this， delete this also。Okay。

 so now what I instead of commma， I'll just replace it with。BM space。

 I'll tell you why Im want to replace with the empty space。 So what I can replace。

AFinder replace using control H。Give a blank space， and replace all。

So now we can see the entire file got replaced with。My own data。

 So first first column is this column number one is on simulation seconds column2 is on receive rate and column 3 and packets received。

 Okay， so now I'll save this file。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_30.png)

Now， the name of this file is over E CsV。 So now what I do is。There are two options here。

 So G it G N u plot dot code。 I use a coding colour G N plot dot code。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_32.png)

So， set terminal。PD F set output。Packet rate dot Pf this the name of the file I want to create。Then。

 set title。receivedceived rate。And packets received。This， I am going to plot in one K F set X level。

So the X level will be。Simulated seconds。Set while， whileable will be。Receive rate。

Then plot the name of the file is A DV。Thats EV。Using one color two means， one is X axis 2 is E axis。

 sorry。Yeah， what is x axis that means the simulator second in x axis 2 will be the invo axis with alliance points。

With the line points。A title。It festival is receive rate， right。

A receive rate title is receive rate comma again， we have Y Vr CSv， another curve。

Using one column 3 that meanss first in the third column with lines points。Title is packets received。

Okay， so now I have done this code。 So this code also。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_34.png)

We be releasing using G N U plot。 So we have a video here in YouTube channel my my YouTube channel。

 G N U plot in S3， please refer that also。Now I will run the code G plot space G plot dot code。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_36.png)

So if no errors， again， I will go and check the folder。

In the folder I can see I can written this thing。So receive written packets as you please see that 0 to 100。

 there was no simulation only after 100 of simulation over and up to 200 it was running。

 So this is for the 50 nodes。 So receive written packets received。

 So since we use lines and points it mention both lines and points in case if you want to mention only lines let me show you now。

Only lines for both。Again， you run the command， now we can see。So it's only lines。

 So this graph seems to be okay when compared to the previous one。

 So this is another kind set of things。 So again， everything this is for a W protocol Okay。

 so the similar thing will run for DSD protocol wireless or protocol。

 something like that everything will be running differently for this okay so for example for comparison what I do is I use the receive rate here。

Okay， so receive rate。Ill compare for both AW D and wirelesser。

 So what I do is I need to run the simulation again for wirelessLr protocol， so。Please。

Through patients。Is the ultimate。 So now I have Y Dcc。 Now I have1 file let it go。

And manual routing about what I do is now I will replace while I at CSv Okay， so wherever。I C Y d。

Tier name here it is Y aser。This coac is no props。This wireless is protocol is number one。

 So we'll change the protocol  to。Number one。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_38.png)

你vo地的V。😔，Yeah， fine。 So， so I change it to wirelesser。

 So now what I do is I will be running this example again。Howeverever。Wle if and run， scratch。

Manner rout compare。 Now， Ill be getting everything in wirelesser protocol。So again。

 I need to wait for some more time。For completing the simulation。Because this will be running again。

But， let me compare this。So now what I do in the the receive rate I will be comparing for AWV protocol and wirelesser protocol so both protocols are in two different categories AV is and reactor routing and wireless sorryW and proor roing and wirelessr will be in the reactor routing so let's say how do we compare both these protocols and the receive rate and the packet received so using two different files So we have AW cv and we have wireless or cv using these two files how do we do that。

So let me pass the video for some time so that。This wirelessr gets completed。Okay， friends。Now。

 it's done。So now well have two files now。 So what I do is now I'll open both the files。Jit。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_40.png)

Oril is are CSv。So this file also will open， so totally you can see。U the last two point。

 we have valuess。Simulation second receive rate and packet received。 Okay。

 I'll delete all these things。Then， control hitch。The comma will be replaceive with the blank space。

Replace all， yeah，1。Okay， now what I do is。I will plot in a single characteristics。

 So wireless I do cV and we CSv。 So now I'll open one another graph。Here， the name is GU plot dot co。

Yeah， now this code。 Now what I do is say at CSV。Here， I use。Oil Ser CSV。So here， receive rate。

Well sir。 sorry yeah what I do is。I use receive rate。Receive rate is a heading the title。

Receive rate and Air E or CSv using one column with the line title。Evo D。

 right E D v and wireless are using that title wirelesser。

So I am going to print the receive rate calculation for boilaser。

 so now with the wirelessaser we will be having one column2 here also。

Because in every we our CC file， the first column at the second column and the boil is our first column of the second column。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_42.png)

Okay， so now what I do is I'll just run this G U plot page G N plot dot code。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_44.png)

AndThen I open this file again。Now， we can see this is the difference between both these things。

 So A D and Y SR for 15 nodes。Okay， so from0 to 10， there was now nothing but after that。

 it was now in the same example， again， I'll write one more。Avo D。

 what I do is receive it and packets received。So what I do， I'll just copy paste this。

So delete the first two and here。Packets received。Yet。Packets， number of packets。

Number of packets received in the X axis。Okay， and here we have one colon three。

That one color to already be plotted， and here it is one color 3。Yes， now code ready。 and now again。

 I'll run it。😔，Okay now Ill be getting two graphs in the single page。 You can see this。So。

So iss the first graph on receive rate， second graph on the packets received。

So hope you got a how to plot using in the plot。So all these examples， we have done it。

For the 150 nodes。 So what we can do is。So we can plot using GNU plot。😔，And mat plot Lib。

We have done it in a flow monitor。And gen you plot through the CSC file。So， all these examples。

Parents。4 15 notess。How suppose whenever you want to compare。So， whenever。You compare。Protocols。Have。

th3 different。Seets of notes。Note numbers。 So what you do is take 10 notess。15 notess。

And hundred dots。Uncompar。Comparare them with various metrics。As mentionedable。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_46.png)

So。Whatever reward we have done is。 So we have got the graphs。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_48.png)

For the received rate in the packets received。And we have got other files， like。Ress at P F。

 So here we have got results for P number of lost packet delay。Under the flow bid rates。

 we have done it。And there are so many a lot more to do。 So even you can see graphics。

 you can check tracematics AskI tracematic is one another thing so that we have not a trader。

 so maybe I'll just show you how that can be tried。As key trace。Yeah， askki trace helpper here。

So what we do here is enable this。Ak T R name dot ti R。

 So now it will create a file name call us T R。 Now， currently， while S I is running。 Okay。

 so now what I do is the simulation second I change2 instead of 200， Ill change2。Hund and 50 or 1 20。

20 seconds。 I will change it。Because it takes more time for the simulation to get completed。So。

 let me change the timing。Somebody I have seen。Conttrol F 200。Yeah。Total left。

 So what it is output 1 totally0。Becauseas from 1 hundred0， it starts only for 20 seconds。

 the protocol will be running。 So now it is while Ser。 I am just running with the Y Sr by default。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_50.png)

Okay， so now Ill compare this oil as。Now Ill run this， so it will be completing within。Minutes 10。

But then some， it will be completing。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_52.png)

So ask key， that's showing an error。😔，嗯Yeah。O。So already。

 we have mob also getting the enabled for mobility helper。 Now， physical air also enable it。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_54.png)

So now I think it will working fine。你。So again， it'll pass the video for some time。

 So after the thing is done， Ill come back。Yes， back。 So now up to 120 we have done。

 So it is closing at 120。 So now what I do is there is another file called dot ti R also got created wireless or dot T R。

 Similarlyly， we can create over EBITDAbit T also now we' will open the file wireless or dot T R。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_56.png)

So its a very long file。For the entire 120 seconds。The simulation takes。

 So the size will be very huge。And you can see here。T is the transition。At what time。

 what is the name of the class w in and device physical layer and the physical layer parameters matrix and the receiving So t for transal for receiving plus means in Q minus means D cube。

So， like this。We have this total number of lines is one lack 78000 lines， so we can see here。

So this file also can be processed for so many various reasons。

 but we have a software called the trace matrix。So to analyze the dot tier files， we need to use。

Tras matrix。It's a Java file。 It's a Java file。That can be unus。知道吧。Ihen jar。Trace matrix。

This is the thing that we are going to use。 I already have this downloader。



![](img/d481ec03e01e2fe5b3f9a4893d20b763_58.png)

In the home folderer。So what I do here is。CD trace matrix。 I have a folder。

 So the folder have three files。 Library folder should be there。In the chas jar。

 the library also should be there within the same folder if not transmatictics will not work。So。

 Java space， hyphen jar。Traceement structure。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_60.png)

So， a software will open。Our file choose file。Select the trace file name。 So I'll go and select。

Willll show you wireless do here。 So open this file。Exxi good analysis。It takes some time， because。

It has more than one lack files。So some it takes more time too。So it takes more time。

 let me close it。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_62.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_63.png)

Okay， so I'll stop it here rather than I'll show you the tracematics in some other file。

 So how to analyze this process this file because0 to 1 hundred seconds the simulation was empty because nothing was happening。

 So after 1 only， we have considerable simulation。So maybe there could be the reason that it is taking so much time。

So I'll just stop it here。 So trace matrixs alone， I will be showing you。

In then main extra simulation。So hope。You would have got a。Got an idea on how to。Simulate。

Wireless protocols。Using industry。Download the source code。Through my blog。NSC name dot com。And also。

Subscribe to my channel。嗯。Share it to your friends。Thank you。Thanks for watching。

 Thanks for watching。 Thank you， bye。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_65.png)