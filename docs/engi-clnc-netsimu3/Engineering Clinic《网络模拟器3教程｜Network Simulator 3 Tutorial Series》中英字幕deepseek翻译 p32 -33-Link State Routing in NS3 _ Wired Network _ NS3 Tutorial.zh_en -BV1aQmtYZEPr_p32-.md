# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p32 -33-Link State Routing in NS3 _ Wired Network _ NS3 Tutorial.zh_en -BV1aQmtYZEPr_p32-

P in entrance， welcome to engineering clinic， so in today's lecture we are going to see something called link state ro。

So this we are going to see。 So already， I have just given a。

Definition of wirelessS or protocol that is optimized links to routing protocol for wireless networks。

 so today we are going to try and wide network。So we are going to find the shortest path。

we are going to prove that the shortest path in link state ro。

 So this is what we are going to do today。 we are going to use wire network with various。

Bandth and delay requirements between each and every node， so thats what we are going to see today。

So first let me design the network， So what do I do is so as per this。

I just wanted to design this network like this， so this will be the net R1 is the。But do one。

And here， this will be R0。Here this will be。あと。And here this will be。Are4。And this will be。あテリ？So。

So these are the multiple links that I will be having， so I just give this link over here。

So this is the link， so essentially it is wired network。

 so we need to have the wire link between each and every node。ok， so。So there are totally five nodes。

 so in this case we have。Fhi nodes。 and we have six links。 So 1，2，3，4，5，6， totally6 links。So。

 we are going to do the simulation of how this can be done using networks ofulator 3。

 so this is what we are going to try。So for the better understanding， what we do is each and every。

link will be having the characteristics， so usually link characteristics will be usually what happens is。

Lnk characteristics will be either delay and data it so these are the two parameters that can be specified。

So data rate and the delay， So what do we do is we will be fixing the delay and the data rate in this case。

 so for let me say。2 millisecond。And 10 Mps。 So let me say。

This way so2 millisecond delay and 10 M is a data rate between node r0 and r1。

 so between r1 and r 4 what I can have is 10 milliseconds。5 MBmbps。 So this way I can。Have it。

 So now here it is one comm1。 So it bids 1 millisecond1 MB then 5 milliseconds second here with the。

 let's say，5 MB P。 so I can have like this。So then sometime here this will be2 millisecond delay and 2 Mps。

Banditit， So for this。2 millisecond and finally for this link we just to give 50 MB sorry 50 milliseconds。

And 50 Mps。 So let's say this is what。The design of this networkper So what we are going to do is across all the links so we have just set the bandwidth and the delay requirements So now in this case what we are planning is we are going to find out between r12 r2 So let's say r1 to r2 so between r1 to r2 how the path will form so either。

The path can go to or not then。It comes to R2， so this is one method which is possible our other way around So other way。

 what we can do is so it can come this way R 1。A 4。A three。

And auto so this method are also possible so in this case we can able to verify so theoretically when you learn link straight rotate so you can able to find out some weight between each and every node and based on the shortest path we can able to find out but let's say in the simulation let's see how the simulation works according to the part we have given so2 aps and sorry2 millisecond delay and 10 millisecond5 delay then 2 millisecond then 2ps delay that 5 millisecond5 delay11 a millisecond delay and 5 millisecond 50 delay。

So in this network， we are going to simulate using single。Industry。

 and we will be verifying the animation as well， so。

So what we do is so the steps will be help we fillinging the source code of it。

 so steps1 is the source code。So sos good。So next thing is step two will be a compilation or compilation using NS3。

So that will be on step number three， then search step  two。

 step  three will be using the network animation we can able to see。

So network animation we can see So in case of any result processing。

 we can able tie the result processing So if possible。

 I can show you the result processing as well in the。Video。

 so result per usually will be as key trace matrix。So S cube trace matrix， we can able to try。

So this is the things that we are going to see today。

 so next thing we are going to see is the source code。So further after this。

 the simulator will take care of it and I will be explaining this diagram I will be using it further。

Usage of during the simulation as well。So go to the simulation now。

Hello friends and this is the program， so this is the link state routing program。

 So in this program we are going to design the network。As per the diagram given here。

 So this is the diagram that we have seen。And as for this diagram。

 we are going to descend the complete template。So we will name the variable accordinglyically。

 so this is link state routing for wide networks。So we are going to use Vo Ser class for this So Vo Ser class first thing is some of the head field that is given。

Then we have this name space。 So NS3， so all the functions of this program will be belonging to this name space NS3。

 so simple 00。1 example is given。 so anyway it's only a log。

And we have the packet size and data it so the total packet size is around210 which the size of the packet and the data rate is around 440 kilobs per second in the overall this is the traffic UP traffic。

The UDP traffic generation using 448 kilobits per second。So in case we want to change it also。

 we can able to change it for multiple results if you want to change and compare the performance。

 we can able to do that。Next thing if we have command line arguments to send it to command line but anyhow we don't need any use for command line in this program then we will create nodes so next thing is we are going to create the nodes so totally node container C the name of the node container C that we are creating totally five nodes so as per this diagram so totally R0 R r2 r3 and for totally5 node so we are creating it。

Then next thing is。Natally this example node 0 to 1。

 so node 0 to1 you can see that r0 and r 1 so node 0 to 1 the node container is0 under1 so that means so we are giving0 under1 so that means c dot get0 means that is node number 0 and c dot get1 means node number1 so like the 01。

2，3，45。And node container n 14， so n 14 means between1 and 4， so between 1 and 4。This is the node。

 so we are going to create the link So this node container is for creating the node this node container is for creating the link between them。

Then 4，3， so we have4，3， So r 4 and r 3 we can see this So then 30。

 So we have3 and 0 here and we have02 so02 means r0 and R 2 and we can see n 23 So n 23 means between2 and3。

 So all the six links are found as per this。Nothing and we will be parallel we will be rating this also see that get force we are get to all these things So next thing is we create an object called us wirelesslessr helper so in this wirelessser helper simply create an object wirelessLr So this is by default coming along with NS3 so you can able to see that wirelesser helper class also been used here。

Okay。So this is the IP version for static routing helper since its Voeser so we are going to create the static routing object here so because each and every node we are going to decide the route so in which route the packet has to move so thats why we go for a static routing so now in IP version 4 since we are going to allocate IP version 4 addresseses for all the nodes so in that we are going to we we are going to add that list for the IP version 4 list to the Voer protocol so that means we have a list of IP version 4 machines so to this computers we are going to attach a static routing along with the Voeser so thats what we are doing this in this both statement so listed or add static routing andlisted at that Voer。

Then afterwards we are going to stack internet stack heaper。

 so we are going to provide the networking stack to the all the nodes of the network。

 so in their case we have to enable the internet stack helper。

 so that' is what internet does to team。List an internet or install see So in the particular range node C is the variable pointed by the node。

 so all the fine node， so we are going to install the internet over there。

So next thing is we are going to create the channel here。

 so already I have just tested with some different values now I am going to change the value here。

 so we are going to use point to point helpilt between each and every node so let's say for example large0 to R1。

2 millisecon，10 m， you can see， So we have just going to create。How many values want totally6 links。

 So what we are going to do will form into。Likewise。So what we'll do is。So this we can paste it here。

So， then。The device controllers。 and this we can paste it here。So， then，x。YesSo totally。

 we have to have。5 links。 So total is6 links we have。 So what do we do is， So this is the third link。

And。Let me copy this。3。4，5，6。So totally we'll be using six links there。

So that you can be easily remembered。Okay， so six links totally so the six links first thing first link is0 under  one。

 so between 0 and 12 millisecond and Nps。So between 01， so I give the name as indeed01。

 2 milliseconds and 10 mps so I will be changing the number two。10 Mps。 So there is the first one。

So next thing is1 for R，1 for 10 millisecond5 mmbbs。So 10 millisecond。

 it is kilo width per second is and5 MBps。So this is on N14。

 so N14 this and that will be installed on the n14 node so the n14 node container means in this node this will be installed so in their case in this contains2 node get1 and get4。

Okay。So that is1。 so next thing is Nd 43，43 here。This this value here2 milliseconds， to Mps。So four。

 three is twobil second。And2 Mps。 So that also will be done。 It's done。 So now we have 30。

 So we have 30 here。 So well change the value to 30。And here also， this also will be changed to 30。

So in 30， we have 5 milliseconds5 MBps， so change it to 5 MBps。唔费你食。So next thing is。02。

 so we'll be giving a value。02 here also we have to give 02。So in 02， the value is somewhere around。

1 millisecond and1 MBS still so1 mill secondd。And1 Nps。 So then finally。The last value is R 2， r3。

 So there is R 2，3。N D23， So in this N D23， we have。Vley scholars。T N D to3 already done。So sorry。

 So fourth this is 2 millisecond and。20 B delay， sorry。So。

 as for the design2 millisecond is this and two devices whereas this43 is 5。

 50 milliseconds and 50 mps so that means。50 milliseconds and 50ps。Okay。

 so the link bandwidth so the link bandwidth and the link delay have been set。

So now we are going to give the IP address allocation step， so we are going to give the IP address。

So totally there are six links there， so we can see 0，1，1，4，4，3，3，0，0，2，2，3。

So 02 to3 everything is there， so we have given the link as 10。1。1。0。

 so usually we will give only the network address so the0 always the end0 will always be called as a network address so 1。

2。03。04。05。0。And 6。0。 so parallel we are allocating that two。ND 23 and N D02 N D 30 like that。

 so that means because N3 mainly uses IPs and4 IPs and6 photographs。

 so it is our duty to allocate the IP or4 addresses to all the nodes in the network。Okay。

 so now after this done， so anyway， this will it。You create a normun of application to send UDP diagramgrams of size 2 10 bytes a derivative。

448 kilobs per second already we have seen。Suate disease from some other example。Okay。

So now we are going to create applications， so in this application。

 we are going to use port number  nine， so let me change it to port number 8000。Soう。

So this is 8000 so now we are going to use UDP soet factory so that is we are going to open the UDP sockets So in this we are going to use a of helper so where。

This i02 get address of 1 port number， so port number is already 8000 is the port value and i02 does get address of 1。

 so this value indicator get address of 1 means i02 so i02 means between 0 and 2 is i02。

Get address of0 means this value and get address of1 means this value So the destination is this node number two。

 so we are going to get the address of I0 that means the second node address we are going to get it。

So this is what and the consent rate is around 440 kilob per second as we indicated and this an of f will be installed on the get1 node so get1 win see or get1 wins this node So this are one node So the address of this link is asked for and。

The installation is done on this the UDp the on of application is done on R1 so that means r12 r2 will be happening according to the connection so there is 10 to2 so 10 to 20 so this will be for so this is something some other example。

So now in case we want to use packet sinks for getting the sync packet So then in the case we will be getting so the node container syncs Car get2 and get1 so that means get2 get1 wins so get2 and get1 so between R R r1 and R2 how the packet will move so but already we have mentioned R0 to R1 link connectivity and r0 to r2 Also the connect we have mentioned now the packet sync can be between R2 and r1 so that's what here C r get2 and c R get1。

So， this is the sync app so the st will be installed and all the sync notes as we have seen that in the K 2 and get1 it will be installed then that will be starting from 0。

0 to 21。0。So ASi trace help ASi， so then Ela do T here。And NABP cap。

 So this is for packeter captures。 that is for。Or iss that。And total simulation will be any further。

 So now here what we do is we use something else animation interface。

 So we want to see the animation。Ne an name， so animation interface， I'll just give this file to。

Hill us are dot X。 So using this command。I will be using animation interface and Hda Alda x number。

Okay， so this second view， but in that case， I can able to set the node location， so set constant。

Anim but constant position。Then C that gets 0。Come up， we have to give X y X。 we'll give one by one。

So let me copy all the values here。So in this case， what we do is let's say。If you。

 if you make a0 and0。So， so this is the X and O axis， so r3 will be at the bottom of str thing。

 so maybe I'll just take it as。啊 fifty咁嘛。0， so that limit x x is is 50 where x is 0。 So r3 will be。

When you will just copy this line。For all the notes。For all the finals， I just the taken the copy。So。

So， get one。2，3， and 4。So totally fine because the look and feel should be literally what we are designing。

 so the look and fill should be like that。So un that constant position get 3 will be 50。0 comm 0。0。

 so that means y axis is 0。3， so note number。R 0 will be y axis is 50， X axis is 0， so 0 comm 50。

A0 is 0。0， comma，50。0。So this I'll be using it。So next thing is this no number r will be 50 comm 50。

A2 is 50。0 comm 50。0。So this is notmato， so then node of 4 will be around let me say this is 100。

 so in their case the x axis is 100。So then y axis is 50， so then 100 comm 50。

So node 4 is100 come half。And five zero deep0。Okay， so then finally R one is somewhere at 100。And我也。

X axis is 50 O is 100， so 50 gam 100。So， 50。0 of0。0。So it given the location of the nodes as well。

 So now I need to compile this file。 So when I want to compile this。

So the command for compilation is。We have to open a terminal。So then in the prompt， you use Cd in S。

All in one hyphen 3。29 slash kindness hyp 3。29。上 then。that。Double hypphone run。

Scratch slash E x p 11 dotcc Ex p 11， So given the name of the file that's E X P 11。

 So first thing is the file has to be。So， this file。EXb 11。cc have to be。St in。Scratch for。

So this is a ultimate requirement of it。So in the7 3。2 name slash scratch。

 So in this scratch folder this。This file has to be stored。So first， let me store it here。

 experiment of 111 Rrc， so file。Sve us。 So first， I be saving this file in。Minus 3 N Nus only13。29。

N 3。29 and。Scratch， so here I will be storing this file save。 So solid it is there replace。

We have made some changes， so replace it。Okay， so now the name of the trace field what we are getting is Els rat here。

Nillesser is a packet capture file。 So this file also we may be needing for running with trace matrix。

 So now in this example， what we are going to do is。We are going to run this example， as for this。



![](img/97203087f7821a5ba14cbbd9ccc26c2f_1.png)

Stment here。そう。The first thing is C。Hus s1， then ns 3。29。Then don't s f Aa1 run。Scratch。

 then you experiment11 dot。That is 11， so no dotcc is not data， so we have to run。



![](img/97203087f7821a5ba14cbbd9ccc26c2f_3.png)

So if it is having any error， then it will be showing it。

 but there are some warnings are given for the animation interface because all the notes are wide notes so we need not set the location for the white notes。

 but that's why the warning is been shown but let us not bother about the warning So now well check it there what are the different。

So LSr P caps so these are the Pap files that what we got for all the entire Pcap and the LSR T here is the trace field and the LSR the Xml is the XmL field for the network animation。

So now to run the network animation。To run network animation。So within the same window。

Or if you open a new terminal again， open a new terminal。Then in the front。

 what you do is head nearness。Hhen， all in one。Iphone 3。29 slash。Ne anim。Ion 3。108。

 so using this you can go so then after thats， you can write this command that ra net any。

So you can see that the N and D both are in uppercase letters， so you have to use this same。首先就。



![](img/97203087f7821a5ba14cbbd9ccc26c2f_5.png)

I open a new terminal。And Ill be doing this inner so1。The netanim hyphen 3。108， so then thatlash。



![](img/97203087f7821a5ba14cbbd9ccc26c2f_7.png)

Ne on it。 So once you've done it。It will give it will open a window。

 so then select the Elra Xml file。So in this case， I have various Xl files。

So let's say in the sort X file Here it is。 open it。

So once you open it it shows you in a different direction。

 so anyhow noise shoes Ill make the size of the notes to be bigger。

 so let's say I give the name of the。Size will， let's say56 so maybe bigger notess。 now。

 once I start the simulation it automatically。Shows you the location as for the position。

 so let me run it here。Yes you can see it。So this is a method we are just running it here。Now。

 the packets are been exchanger。 So let me use the simulation as fast as simulation you can see here in the top here。

I use the fast simulation， so see that how the packets are moving there。

So maximum the packets are moving from。Noode 1，0 and2， so 1，0 and2。

You can see that actually this graph is upside down because we have taken 00 here。But here it is 0。

0 is here。 So that's say the。1，02， it is a part that what we have。

So we can see that the maximum packets are going from 102 so this is the based on the link state ro protocol。

 So according to the oil lets there is optimize link state roing。

 So there are some packets are moving between other nodes， but maximum packets are moving via 102。

 so this is the perfect simulation up。Li state ro。Okay， so up 30 seconds we are run the simulation。

 so thats say up to 30 seconds the simulation will done。

So now this is the best resource code and if you want to find a throughput and other stuff so we can use this software regardless trace matrix。

Tres matrix again， what we do is open a new terminal to use trace matrix。Open a new terminal。

 So then I already installed this statesmatics in。Cd。Rceement tricks。I 1。4。0。

Then it is a Java based application， so Java space hyphen jar。Trace matrix D。

 so this is a file that we can run it。And the Ls are that Tr file， we have to open it。

 So now what I do， I will just open a terminal now。



![](img/97203087f7821a5ba14cbbd9ccc26c2f_9.png)

So， in this terminal。CD trace matrix， Javava hyp Z。



![](img/97203087f7821a5ba14cbbd9ccc26c2f_11.png)

caseasement taste turnsza。So once it is done。Hed open a terminal， sorry to open a window。

 So from this window， we just select。This ns only known 3。29 ns 3。29。

Here you just go and check the LSR rat here file， this LsR rat here open it。And ex。

Now this is the exhibition here， so totally 28。54323 second it executed and how many notess so totally there are five nodes so these are the details are about the notes and throughput。

So you can see the throughput of node 012 there because maximum packets are there for 0，1，2。

 but 3 and 4 only throughput is said there is no goodput。Okay， so this grass we can able to plot。

Using any plotting solutions or characteristics， So let me show you that how we can able to plot these characteristics。

傻。Just copy these values。

![](img/97203087f7821a5ba14cbbd9ccc26c2f_13.png)

Just a selectal and control C foot control C。系老板你尿得啦。Is it。So there is a value here。

 so we can able to plot it here。So， then， we can use。In of a tab， use a blank space。

So that it can be easily be plotted。goodput we don't need， so in case if you don't need。

 we can delete it。十么般。Since some of these values are0， so we can delete it。

So only thing is we need only these two es， so this。Maybe we can use come out here。

Second you sleep what do you see。Lal office。 So save this。呃グプ。So I store this file less。

Throughput dot cv， so comm separatedpar values， I just put it。

He place it somewhere in the industry threefold。我没 phone for that。

So in the home folder just store this way。Not seriously。So once it is done。So this file。

 I can open it using Lib office。So on the liver celk， So in the liver celk。

I'll just open this file controller over。And to put that。Cv。So once I open it， so it shows that。

There are two values。 Okay， so now we can use。Insert。Chat。So， in this chart。If you want to use line。

So this thing you can use。说。So， this is what。So0，1，2，3。So this is what the value。

 what what we what it is shown， so maybe the0，1，2 have0 and1 have higher throughput whereas 2， three。

4 have in hundreds so that's why this is the orange signal。

It shows 20000 there and 100 in a smaller small length。So。

 this is the throughput characteristics of this particular network。O。

So it's very simple logic to implement this link state routing protocol。

And it can be very easily handled。So， so thanks for watching this video。

 So in case if have liked this video。Begin now。Subscribe and share a difference in case if you want to download the source code of it。

You can refer my website， MSsname。com。Because I cannot share the source code directly in the description window。

 so I just have a blog， so in the blog I will be sharing the code along with a description of it。

So please subscribe to my channel。And I use my website for download source code。

 so thank you very much。Bye bye。

![](img/97203087f7821a5ba14cbbd9ccc26c2f_15.png)