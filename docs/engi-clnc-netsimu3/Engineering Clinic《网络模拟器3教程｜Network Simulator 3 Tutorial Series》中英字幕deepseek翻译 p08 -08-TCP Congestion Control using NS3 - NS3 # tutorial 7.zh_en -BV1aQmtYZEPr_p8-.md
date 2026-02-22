# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p08 -08-TCP Congestion Control using NS3 - NS3 # tutorial 7.zh_en -BV1aQmtYZEPr_p8-

Good evening。 This is Pradip Kumar。 Today， we are going to see something like congestion control。

In T C protocol， using N3。This is what we are going to see now。

So NS S3 already have a source code like this。 The source code name is 7 dotcc。And of6 to dotcc。

 so you can use either of these things for plotting congestion control window calculation。

So what if by congestion control。So congestion control is having three stages when the TCP protocol starts building a bit of traffic。

So first thing is slow start threshold。Second， second thing is。Conditional avoidance。

The third thing is。Congestion detection。 So these are the three phases of congestion control。

 So slow str threshold means。First。Exponential increase。Exponential increase of packets。

 So that's what here， the first thing。 So exponentially， the packet will increase。

 Next thing is additive increase once the congestion is need to be avoided。

Then this will be multiplicative decrease。After the congestion detector。

So these are the three stages， so you can read more about countries you be congestion and control through online。

through any books we can refer， but these are the three stages of congestion control 3 phases we have we call slow start threshold。

 usually it will be mentioned as a parameter face thsh。This first slow str threshold。

 congestion avoidance。 So after a period of time， once the the packets are being congested。

It will slowly the traffic will be built up so usually the congestion window value will be set as one initially then afterwards it will be increment to2 then4 then8 so it will be exponentially increased to a particular stage where the network can anticipate a traffic congestion so that time it has to avoid it So that time it slowly starts the packet increase in additive increase has been 35 minutes363738 So even after some time the congestion detector it suddenly brings down the。

Value to half of the window size。 So Windows size and the congestion window size will be reduced to almost the half of this window size。

 So after the congestion is detected， it comes to again。

 the starting value of one as the congestion window。

 So this is how the traffic the TP traffic usually works in networks。 So you can。

Refer to this more in in the theoretical part， but today what we are going to see is how this is implemented in N S3 using the 10cc or the 60cc So it is a very handy tool。

 So if you want to see how congestion works， it is a very easier tool that is available。So first。

 let us first。Open this file。

![](img/bd882857254978b7dc48214b975485f2_1.png)

7th do C。 So what I do is I already have。In Nol in 13。27 in Sc， I already have this file。



![](img/bd882857254978b7dc48214b975485f2_3.png)

7th rocc with the file。So let me explain you this file。So these。

 these are the header files included here， hash include files。Here we have some the script example。

 So and here there are two nodes， N S 3 TCP and N S3 T cP here， node 0， note 1。

The Is of node0 is this and the Is of node1 is this and both uses point to point protocol and the data rate and the bandwidth is5 B and 2 milliseconds delay。

So this is what we are going to design in this example。

 so between this how congestion builds up and how the congestion is avoided， we will see that。

So since it is a complete C programming。Since it is a complete C program。

We will just go through how this is this implemented。 So we have a class my app。

It ineriting the property from public application。Then my app is a conceptor。

So it's a conceptor here， the districtor here。Concepted and deed。

Then we have a function called type A D， get type A D。

And setting up setup is a function which is declared here。Which has a parameter of socket。

Address and 32 bit packet size and 32 bit number of packets and the data it。

 So this is setting up of the protocol and the circuitcket number and everything。

And private functions， start application， start application。On schedule transmission， send packet。

And here。The variables。Since we don't use pointer inside NS 3。

 so bigger inside of pointer we have we use templates here。 so so I get pointer。

E soet address MP because there are two nodes， node0， node1 and packet size。

 then in packet data rate。Even tidy on whether it is running or not， a number of packets enter。

And first， calling the consecutiveor。So， in this conceptor。addmiizing the value of soet to 0。

 there is no P is empty packet is 0， number of packet0 data at 0 send event and running is false by default we are making it false and packet sensor 0。

And this is what。The m soet equals 0。 So that means sevenever the deor is called this M soet will be。

And this less to 0。On type I， the name of the application which is being called as a Mayap is a name of the thing and this one of a tutorial so you can see this the mayap is the name of the glass which will be called as a type I。

On set up now the setup function。 So our purpose is we have designed a class C C class。

Under the purpose is to implement all the functions。 Now we have the function get type I D。

Set up start application start application schedule and send packet。 So1，2，3，4，5，6。

 totally6 functions need to be implemented。And here before the contract extract is called after their get type is the first function to be implemented。

Which was the name of the app itself。And here is set set function。 So we have socket， address。

 packet size， number of packets and data rate。 So this is allocated to。

So you can remember this something like。Soet they called this start soet。

 so you might have remembered this kind of statement we usually do in C progressive press plus the same way we are doing it here。

A underscore score soet is the soet， which is belonginged to the class class member and socket is the。

啊。Prameter of the particular function。Then start application if am running equal to true here。

 we initialize that to false now it is true。Number of packets since also to 0。Now here if I net soet。

 the internet sakeet address is matching type m， then name soet bind L same soet bind 6。

 so that means when you start the application whether you want to start the application either in IP and 4 or IP and 6。

In case of IP version 4， you can use bind in case of IP version 6， you can bind de I IP version 6。

 that is bind to 6。And connectnect with the peer。 So how each node is connecting to each other。

 That's what this start start application will do。And stop application since for running equal to true we use start application。

 we will make a M running equal to false for stopping the application and whenever it is running。

 we will just cancel the event and then we stop it。And well close the soet。

 So it' is always good to close this soet whenever you don't need or whenever you want to start the application。

Then send packet function。 So packet pointer again， we use a pointer here。

 So pointer packet create packet with a packet size。

A name so send packet and if f is less than the total number of packet scheduled transmission。

 So in this case， the trans the trans will be scheduled。In the control， in a con control。

And here schedule T X。 now this is end packet and this is a scheduled transmission。

 So when do we start the transmission E we am running since Im running is。A bullan variable。

 either it can be false or true。 So in this case， what happens is when it is running So how what is the size of the packet when it is going So m packet is into with packet is is given in byte it will be converted to bits and divided by the bit rate bit rate is speeds per second rate So this time will be calculated and based on this end event simulator schedule。

 the simulator will be scheduled to send the my application the name of this file my application。

To the corresponding timing， and it is transmitting the packet。

 So that is how the schedule D x works。First compute the timing。After the timing and the bit rate。

In the simulator schedules the event。That is why it is called the end event the parameters are the time。

The name of the app and packet。And this， this means the corresponding schedule T x。Okay。

 so now congestion window change。 So the main congestion control is happened with the congestion window change。

 So we have a function called static or congestion window change。

 So this function is already implemented in now。One of the headerophil here， which is given。

One of the header file here。 So in this header file， this function is there。

 So this function would simply calls it。And we have a stream output stream wrapper means we want to print something to a particular file。

 So what has to be printer So we have to print the congestion window calculation so that's why we have this stream。

Ooldd congestion window and the new congestion window。

 So usually what happens is we have two congestion window calculation。

 So usually the congestion window calculation always starts with the value 1。

And it keeps incrementing a period of time after a period of time。

 once the congestion is being start to gearing up that time it will be instead of exponential addition。

 it will go for additive increase。After some time once the congestion is detected。

 it will go for multiplicative degrees。Okay， so further we need to know every time we need to know what is a old congestion window and what is a new congestion window。

So similarly， every time when the is a packet is transmitter。

 it allows maintain the two values old and the new value。So in this case。

 what we give is this statement is a simple seven simulator。

Scope now gets second means the current instance now。At this instant， after a tab。

 the new congestion window value， which will be output to a particular file will show you the file at the end of the simulation。

Next thing is get stream， so stream gets stream。Simulator now seconds again。

 this value the current timing and the old congestion window and the new congestion window and end line。

 So that means every line will be having three parameters。The time。

The old congestion window and the new congestion window will plot both this congestion window value when we can see。

How things are there。 But whenever the congestion is detected， there will be a receiving drop。

 that means the particular receiver node doesn't。Receive the packet so the packet might be dropped in that case what are the drop packet that also we have to record it So that is recorded using R x drop at simulator Now instance so at what time the particular packet is dropped that also we can able to write to a particular file So this also will show you where to write and how to calculate the R x drop this also。

Soon after all this is done， we will create a main function。So in this main function。

First use versionson 6 equal to false。 So that means what we are going to use only IP S and 4。

 We are not going for IP Sn 6。 We are reducing false in case if we want to go for IP S N 6。

 you can make this as true。Okay， now we are creating two nodes。 So node container nodes。

 node that create two。 So if you want to see more about this， check for。First start CC file。

We can check for first do CC file in my same YouTube channel。 you can refer for it。

For explanation of this complete code and we have a point to point helper。

 the name of the object point to point， we have a data rate of IM2 milliseconds as we see in the beginning diagram。

So this is the place where I showed you that。For a BP and 2 millisecond is the。

Datad between the two different nodes。So after that we used net device container net phase for enabling the network services in a particular node。

 so for that we will be installing the net device container to this node the node is an object of the node container。

Then we have error rate models because we are going to find out。

Or how much error rate that means the congestion controller mainly be based on the error rate。

 that means how much number of packets will be received or how much packet will be dropped this kind of things we have to have。

 So we have we are using a receive error model and error model。In this work， afterward。

 we just Ill send theip in the port number。 So further we use internet stack helpaper stack。

Ins this stack on the particular nodes and the port number we use is 8080 and S address。

 any address and we use if use v6 equal to false。Then we go for IP and4 address。

 So further we have a protocol here。 the IP set 10。1。1。0。

 usually we always set the network address to be last value to be 0 and we have a subnet mask。

 then assign these value to the interfaces。Then sync at equaled get at of one。

 So get letters of0 will be the first node。 getre of one will be the second node。 Thats a sink port。

And any address equal to get any any image any of this node there is a sync。

 So we have sync address and the any address。 So we have both these things let me show you in this diagram here。

So this is the get of 1 and this is get of 0。 So the first0 thrown will be get up 0。

 and this will be getta1。 The index always starts at 0。Okay， so after it is done。

We just allocate the probe type to be I IP version 4 packet probe and the tracepa this how this is the tracepa that for transmitfiing the packet so IP version 3 layer3 pro IP version 4 layer 3 protocol in transmission so that's what this will be helpful for analyzing in the trace file so that also we will see。

Suppose in case if we v6 equal to true， then this will be this will be the IP address for the particular node in this case。

 so in this case what we have done is v6 equal to false so that's why we have we have used only this IP address so we will try use IP 6 also。

After that， we use TCP socket factory because there are two options UDP and TCP socket factory。

 so we go for T cP soet factory because it is a congestion and it is for reliability So we have we are going for TCP socket factory。

And application sync apps so in the packet thing we already is we use node dot get1 that means the first two node the second node node0 and the node 1。

 so node1 we are using starting at0 and ending at 20 and here this is a tCP socket that we use and create soet node dot get0 so and。

We are allocating the node the first to node the0 to node to have the TCP socket and the sync is allocated for node number one。

 So hope you understand that。 So from node 0 to node 1， we are going to have a packet exchange。

And then pointer myap app create object。 So we have created the type I D here。

 So here we will call the simply myap function because myap function is separately completely different from the main function。

 So inside the main function， we are going to call the myap。 So further。

 what we do is we create a pointer for it。 and then we call it。

And app set up So you know that this for this variable we have a setup function available in the Maya application So where it has a N3 TCP socket。

 so this variable value。Then sync address， sync address is nothing but this address what we have designed here。

And 1040 will be the。The data rate is only a B and thousand and040 we can see the setup function here。

St up function。 Yes， so add packet size and the number of packets。

 So thousand4 is the packet size and number of packets is  thousand。 So 40。

 the reason being TCP needs an acknowledgecknowledment。

 So40 bits of acledment will be returned from it。 So that also will be included in the source。

Thats what packets and number of packets， then nodes get0 add application app。

 So that means in the node order get0 we are adding the app app is nothing， but this application。

Then start time 1。0 and start time 40。0。Then record these value to a particular。

File colour 700 c w and D thats a congestion window value。 So for that we use Sci trace helpper。

 So this Sq trace helpper will create a file colour 700 c W1 D。

 So in this 70 cw1 D all the values will be recorded here。

And this tissue should trace connect without contact without contact this congestion window value also will be printed。

Also， we have Pcap helper that is simply for wireshark。

 so we have creating a wire shark file also in this7 third Pcap。

And we can get the PHA or extract also， So this also will be recorded in a particular file。

And once we get this file， we can able to plot using Gi plot helper。

 So anyway here this will have a Gi plot helper class。

 so it will automatically create a plot file where you can directly plot using G plot that also will show you how this can be done。

 So in case we have a file called uni plot helper plot helper。

This GN plot is already include the support for GNU plot is available in NS3。

Let me see the hydrerophile contents are not。So maybe somewhere in any of this file。

 maybe in the stat model， it might be that J Eion plot codes might be there。

But N S3 supports G N E plot， which is power very powerful graphing solution。

So in this configure plot the first argument is a file name prefix for the output file generated。

 the second third fourth arguments are respect the plot at x is y axis levels So in this configured plot the first argument is a file name prefix for the file name in this is the name of the file that we will be getting。

And the second third， the second argument will be the plot title and the third argument will be the x axis and this will be the O axis。

 so like this we have four parameters。Then the probe type so product probe what are things to be probe so here output bys packet by count and aggregateator means it keep adding every value。

 whatever it has。And in the file helper will be getting a file aggregator for aggregating all the files。

 whatever output has to be recorded will be recorded via this con file。And finally。

 send the value into deform time seconds and packet by count。

 so both these values will be sent one by one。And these are right upward by will be written here。

The simulation stops at 20 seconds and run de dry。So very simple application。But。This application。

 once you understand。

![](img/bd882857254978b7dc48214b975485f2_5.png)

Congestion control is very simple。 Now， what I do is I'll just run this file。

We already stored this v。W a and1， scratch seventh。So there is no extension needed。



![](img/bd882857254978b7dc48214b975485f2_7.png)

So extension not needed。To run the file。We use。In the prompt web。W F and run。Scratch。Slash and。



![](img/bd882857254978b7dc48214b975485f2_9.png)

So， once we do that。It will compile。And you can see some values are being printed here。

There will be R X stop available here。O。At various locations。

 R X drop is available here here Also we have R X drop。Okay， so this can be recorded externally。

 but there is a file also being recorded inside the folder can check this file。

So there are so many files like seventh that3 W and D，7 packet by 0 count。

 one count that file plot file， S file。And some of the are Pcap。

 So we have so many files it's got recorded。So plot is a file that you can use G plot。

 so simply the command is G plot。7eventh hyp packet count dot P T。

So if you write this command to plot， it will pro directly。



![](img/bd882857254978b7dc48214b975485f2_11.png)

So first what2 is we will use GN U plot first。

![](img/bd882857254978b7dc48214b975485f2_13.png)

So this is a command G plot。Let me not use this now for simply use G plot after you get the plot。

 you will get a plot within double codes，7 hyphen。Dot P L T within double courts。So， once you get it。

It's not ploting。 Let me check it。

![](img/bd882857254978b7dc48214b975485f2_15.png)

Let me let me check what is the content of the file。



![](img/bd882857254978b7dc48214b975485f2_17.png)

![](img/bd882857254978b7dc48214b975485f2_18.png)

Okay， fine。So it is not that way。 So what we do is。



![](img/bd882857254978b7dc48214b975485f2_20.png)

Tectly， I can use it。So， I understand。So here what you can do is G and you plot directly。

 you can use this command So these two plot。

![](img/bd882857254978b7dc48214b975485f2_22.png)

So。

![](img/bd882857254978b7dc48214b975485f2_24.png)

This will directly added。So no error have come， but when you check the folder。



![](img/bd882857254978b7dc48214b975485f2_26.png)

A file name called us A P And D is getting created。 So when you open this file， this is the file。

You can see packet by cone versus time。T source path。 What is a pro path。

 that path and time in seconds packet by count 0 refreshs this color and packet by count1 refer this color and packet by count will be in the y axis X axis will be time and the way axis is packet bit count。

 So as per the generation of graph this how。

![](img/bd882857254978b7dc48214b975485f2_28.png)

The graph card generator， but this is not a congestion window。 congestion window。

 we have a separate file colour us73 or3 w wind0。

![](img/bd882857254978b7dc48214b975485f2_30.png)

So this is the congestion window file。So you can see that this old congestion window is a new congestion window。

 There are three values。This a time。This starting with0 old congestion new congestion 5hi36。

 like this5hi36。10and seventy， thousands72 thousand。

 so you can see that this value is coming here and this value is coming here so every time。

This will become the world value here for the new packet。 And this this is a new value。

 The next value， this becomes a new world， and this becomes new。 So this is how。

This congestion window value get incremental。And see that after a period of time once once it goes up to this value。

 it kgan can be bring down to thousand72 from there again it starts。

 This is the congestion avoidance。And similarly， it， it runs to the high for some time。Again。

 you can see after 160196， again it comes so this is a value 6。57 again it comes to thousand72。

So this is how the way the congestion window have been working out。

So how this value is calculated that we will see。Okay。So what we do is we have two values here。

 So I'll write another congestion window。 So this is a file here。So to process this file。

 what do I do is first select me。Go with。This space， Ill go with one space。

 Ill change it to one space。 So copy this control hedge。Replace with a small blank space。

 replace all。You can see now here it becomes one space name of the fe 7 are C0。 Okay。

 so now I will be running one。File here。Set terminal。呃，BNG。Set output。Condition that。

Congestion dot P， E and G I re name it set title。Unjust send window calculation。Set X level。

So xtable will be。呃，代。Time in seconds。Set oil label。 so you can refer my z uni plot video。

 which is already there in my YouTube channel。 You can check it。And congestion window。

So we can use C W and D。There is a congestion window in the O level。所以利别。

So even if one spelling is wrong， it won't record won't comp。

Now plot the name of the file7 the dos Ew10。Using first thing is one column 2。

 that means first column as the second column。 So you can see that we have totally three columns。

 This column is time。 This is old congestion window。 This is a new congestion window。

 So it will be pra two curves， one with first column on second column。

 other with first column on the third column。So using one column2 with lines points。This one。

titleitle。W。感iction。Don come on。Again， well have。70 C W and D。Using one column3 with lines points。

Title。New condition。Okay， so we will save this file， so I'll use congestion dot。PL T。

 I use this name as send got Pl T。This。Now， what I do is I go to the terminal。



![](img/bd882857254978b7dc48214b975485f2_32.png)

GN plot。Congestion dot。Plt。Once I do this， it will create a file called us congestion P And you can see this。



![](img/bd882857254978b7dc48214b975485f2_34.png)

![](img/bd882857254978b7dc48214b975485f2_35.png)

Is that。Application available。

![](img/bd882857254978b7dc48214b975485f2_37.png)

You can see this here， but you cannot see any difference between both this new and the old congestion value because both almost have the same value。

 So old congestion have this magenta colour and new congestion in the green colour。

So green cloud is prevailent because it is the new value what we got it。

 So what happens here is in when you understand this congestion this is the time in seconds at time this time。

The con starts here。 It goes to a maximum of more than a lack。After that。

There was a congestion it directed， Suddenly it came bring down 2072 as we see any in the file。

Then it goes for additive increase， so it will slowly add  one by one So up to 16000 it has come after that。

 again， it comes 2072， then it comes like this around 10000 or something again it will around 10000。

So after a period of time， the congestion the network stabilizes here。 This is between two nodes。

 just node0 and node 1。 This is how congestion is calculated。



![](img/bd882857254978b7dc48214b975485f2_39.png)

And this is how the congestion window is been printed。So we have already day a session on N S2。 Also。

 there is a congestion window calculation is there。 And in N S 3 also。

 we have a congestion window calculation。 So in case if you are doing a project on network simulator。

3， you can use this video， or you can use 6 dotcc also as one of the congestion window calculation。



![](img/bd882857254978b7dc48214b975485f2_41.png)

So thanks for listening to my video。So please subscribe。Subscribe。Share and sharere my video。

 Please subscribe and share。Engineering clinic。Also， I have my website for source codes。

You can contact my website。NSNname dot com。

![](img/bd882857254978b7dc48214b975485f2_43.png)

Thank you。