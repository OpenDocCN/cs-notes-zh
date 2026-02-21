# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p01 -01-Explaining second.cc with Ascii trace and NetAnim - -BV1aQmtYZEPr_p1-

Hi friends， this is Praip Kumar here。Today we are going to see NSS3 secondcc file。

You will see the demonstration。As well as how to use this file。Use this file。 Okay。

 so if you want to goboard the first CC file。Which is based on。Peer to peer network。

So which which says that。There are two nodes like this。So， note number one。AndNot number two。Here。

 node number one， node number two。And they just exchange with some packets。

 So this is what we have seen in the。Example now， now in this example， what we are going to do is。

We are going to use peer2 pair network as well as CME network。So， P2 P。And CSMA。

 So CMA the sense that。Carrier sends multiple access。

So that means it is a land network so simply call us it is land。

 so the source node will send a packet to the destination node。

 but the packet will be put onto the bus。 So every node in the network receives that packet and whichever node it is intended for only that node accepts the packet others simply see the packet and if it is not in for them they simply neglect it So that's how this carrier sense multiple access box。

 So when it happens multiple access means if the there are different nodes sending the packet at the same point of time。

There could be collision， so that's what we we studied in CSMA， Cd and CSMA。CA。

 that is collision detection and collision avoidance there are two concepts here。

 So collision detection as well as collision avoidance， So CSMA leads to that。

 but in this example we will be seeing only on P2 P and CSMA so these are the two things will be shown here。

So first let us go with second orcc file， the location here is。Under re i 3。27 slash examples。

Slash tutorials， tutorial。So。First， let me copy this file， copy this file too。Enna iPhone 3。

27 slash or a to zone slash scratch。

![](img/3438204fa1b6a7e8f9918377c765ad11_1.png)

In this folder we will be copying this file。 So what I do is I will just copy this file。

C P example tutorial， second dot C。Scratch， so I am just copying this file in scratch folder。

So we will see this C D scratch unless you can see already we have done first startcc simulation and we are going to see now second startcc。

So time being， I'll just open this file and I'll show you what is the content of this file。



![](img/3438204fa1b6a7e8f9918377c765ad11_3.png)

So here， this file also have been。Designed with this tf topology。

 So now we can see the topology given here n not n1 as we have already seen in fastercc。

 but n1 here is part of the land network as a faster note then n2 n3 and N 4 So the peer to pair I is 10。

1。1。0 and the land I is 10。1。2。0 So far understanding what we do is we change this I address as per our convenience172161。

0。And La output 172。16。2。0。 So we will have this way so that well have our our own network。 Okay。

 so these things will reflect in our。So code， okay。As we see。

This is a log first thing is using namespace N S3 as we have already seen that。

 so most of the conference I will be I will not be explaining it here because we have already discussed these concepts in fast dot CC。

So users are requested to refer back the first startcc。Then this is the second script example。

 So if someone sees your code， you have to know that what kind of script they have written thats why this thing。

And we have main function or given count and argument given vector。And verbo equal totro。

 So Ill show you what is this ver on ver means something。Running in the command。 See， for example。

 this is the ver mode。 So what we do is。

![](img/3438204fa1b6a7e8f9918377c765ad11_5.png)

So yes hyphen V。

![](img/3438204fa1b6a7e8f9918377c765ad11_7.png)

Okay， and L G show you later。 What is your boss。Okay， now we have event 32 bit type。

 So here the purpose is unsigned integer。32 bits。 that's what it means。 So that's what even。

You win that2 underscore t N csM andCA number of csMA node is 3 it is given us 3。

 please see that this a variable name is very important I will tell you why we is important。

And we have command lane command。The number of extra CS SM nodes will be N SA total number of extra CSsM nodes is3 plus you can it here n2 n 3 n4 will be the CSsM nodes。

 whereas n1 is part of the point to point node or peer to peer， So it is not peer to bear。

 it point to point fine。Then verbo mode tell E applications to log if through。

 so that means whether verbo means whatever we are doing， it will be recorded。

 That's what call us verbo mode。Then， if verbo。If verbo log component enable a UDP codeline application。

And U across server applications。 So these are the two applications。

 which will be running in this example。 Now we can see if where both。

That means the Web values boolean， and it is true。 That means if true， it will print。

 suppose if you want。This has false。 Then this ver will not be printed because ver is false if false。

So that' is why this value boolean true or false。Fine， then well come here。

 Suppose if no nodes are there in NSM， so then it will be taken as one node thats what the tenary operator here NSM equal to NSMA W equals 0。

Yeslse， it is1 on the N CSsM， so if no nodes are there， then the total value will be 3 nodes。Okay。

 now we will come to node container P2 P nodes， so we are creating two nodes node container P 2 P nodes。

 P 2 P nodes are To we are creating two nodes here。Then， we will be creating。

Note container CS SMA nodes。 So we are declaring a variable C SM node。

 Please remember CMA node is different from N CSMA。

 So this N CSSMA already declared as3 and this CS SM node。 Okay。

 so CS SMA node that add P2 P note that get 1。 Now please understand。In this case， yet not is。

Suppose if we want to refer end not。Maybe I'll just use the other file。

So the node is not referred as。P2 P。Note that getta is 0。

Because you can understand now n node is referred as this and whereas n1 is part of CSsM as well as it is part of P 2 P。

 so this can be referred as。Any one can be。I referredd as。CSMA node dot get T0。😔，Har。P2 P notes。

Dot get tough1。Please remember。So this can be written as in both case this is possible here a node of get 0 or it can be written P 2 P nodes of get 1。

Because always the index starts with the0 and it descending at one here， 0 and1。

Whereas here the index starts at 0 here now we will come to the code you can understand。

So what here happened is。P 2 P notd， get one。 So C S notra add。

P2 P node that get one means so this will be added to the CMA node has variable name then CSsMA nodero create N CSMA So already we have created three first node is been created and next later we can add three nodes。

 we get this variable refer value of three。Then CSMA I write as a command。N CS SM equal to 3。

Already declared。So， make the faster node。Okay， so totally， we have four nodes。 Okay。

 now well come to point to point helper， point to point， the helper class。The device attribute。Again。

5 m S and 2 milliseconds that is a device attribute and net container P2 P devices。

 So net device means it is a ethernet car along with the stack。

Point to point at install P2 B nodes and install on the P2 B nodes。Then similarly。

 we have CSMA helper， though this is what something different now because we didn't use this the first do C。

So it is a CSM helper class since CSM helper class， you can see as per this diagram。It is a full bus。

 so it is a land， so land will be having more bandwidth and delay。So in that case。

The data it is10 a B B S and it is in nanoseconds。 So 6，5，6，0 nanoseds when you convert microseconds。

 it can be around 6。56 microseconds or something。So that is a delay， so it is given in nano secondsd。

So the channel attribute here is 10 BB bandwidth and 6。5 nano microseconds。

And here also will will install the CSMA devices so the a device container here a P2 P device is installed on P2 P nodes and CSMA device is installed on CSM nodes。

Then we'll have。Internet stack helper stack P2 P not are get 0。 So first what we do is。

P2 P no that gets0 and stacked our insults here amino。 Now please understand that。

P2 Pers or get1 is not installed， so Ill write down the line， stack dot install。P2 P node dot。

Get tough1。Its not installed， so that means。For this line。There is no。Need to install this stack。

Because in this next line stack missile CSsM nodes， CM nodes have totally four nodes，0，1，2，3。

 so one23 will be and the third node the first0 node will be the。P 2 B node not get one。 So okay。

 so on the logic says， P 2 P。Note that getta 1 will be equal to。😔，CSMA notes that get tough 0。

 so both are same。So because of this reason， we could not inulate no issues in that。

 so don't get confused， don't include this line。So then IP version certain for address helper address Now this is what we have changed172。

16。1。0。And here， 1，72 point，16 point。2。0。So。We are installing IP version 4 interface container to P2 P interfaces and assign it to the P2 P devices。

 similarly the CSM interfaces assign it to CSME devices。

UDP E server helper now will come for UDP application。Ecoes server， the port number is be on，2，3。

4 is the port number I' am going to use。And application server who is the server CSsM not just get tough in CSsM。

So here the example here is。When you see the server is。Csma node dot get of3。So this is a server。

 So now we please understand who is the server。So in this example。

 N SM is 3 that means get of3 means we have four nodes get 0， get 1， get2， get 3。

So that means this is the server。And4 will be this server。Okay。I think hope we understand that。

And see， so in this case， n4 is a server， n4 is a server。Okay， so the server is starting from 1。

0 to 10。0。 Now next thing comes to the client again， client the value is 1。

23 for the port number is 1，234。Again get address of in CSMA that means get address of3 so that means CSM interfaces get address of3 means the third address you are going to get。

Then maximum packet is 1 interval is 1。0 will be I can use let me use I can use two packets so that the maximum packets can be two Also interval is one seconds and packet size is 1024 in case I wantt increase a packet size I can increase2。

2048 by。 Okay， now who is the client。Application container client apps echoco client that install P2 P node do get of 0。

 So0 is the client Now who is the client。When you come to this diagram， this is the client。

So yen0 is that client。Okay， so n 0 will be the client where is that yes。So I light it here。

 So in this case， n0 is the client。In the topology。Okay， now client is starting from 2。

0 and ending at 10。0。 Okay now IB lesson for global routing helper， pop routing table。

 so populate all the routing table all the notess。Then here now there there is a new thing called point to point that enable Pcap all second。

The name of the file second gi have given and CSM at enable Pcap second CSM devices dot get1。Soう。

Get one means C SM devices in install done C SM nodes。

 So CM nodes get one means they want to get the packet of the second node and the can send access true。

 Suppose in case you want to get packets of other nodes also you can use it。Enable Pcap second。

So you get tough。3， also， can use it。Okay。Now here， Pal。

Second all means for point to point and find the peak packet packet capture for all。

 So P cap will be run using。fact will be opened。Using either。Wre shark。Or TCP dump。

So wire circuitrc is very popular。 so can we can see how wire Crc uses this file second。

It will create the B carefulL for all the point to point channels。

 whereas in CSMA we have going to create for get one and get3 okay。Then simulator run。

So a very simple program。 So once you understand the first startcc。

 most of these things are replicated here only example is。



![](img/3438204fa1b6a7e8f9918377c765ad11_9.png)

It has CM nodes。Okay， now I will run this example。

![](img/3438204fa1b6a7e8f9918377c765ad11_11.png)

So to run this， the command is。To run the example， the command is。Dot slash v， double hphone run。

 scratch， slash second。Not enough any extension。

![](img/3438204fa1b6a7e8f9918377c765ad11_13.png)

So we have A F and1。Scratch， second。

![](img/3438204fa1b6a7e8f9918377c765ad11_15.png)

It compiles。After it compiled， it will give you the packet structure。 Yes。

 now we can see at time 2 seconds clients and 2048 by to 172，162。4。 at port number 1，234。

 Then at this point， then at this time， then three seconds like this。

Suppose so I have given two packets here。 So in this example。I have given two packets， maximum value。

 so I can see this line here。I will change it to one packet， just only one packet， maximum packet。

 Now we can see。I run the same example you will get only one packet transmitted between the client and the server。

 now we can see two seconds the client send these mini packets and this this is what it comes。

And total 2048 bys， but earlier it was 1 thousand34 bys。So I use three packets now。

Maxum packets are three。Now， when I run this example。

So if you are a beginner user you can first use this kind of simple modification like changing the API address changing the port number。

 then changing the number of packets and changing the delay and then changing the packet size so these things are bandwidth the delay so these parameters you can change first in the beginning。

And later on， you can modify the source code， so that is the best way for you to learn the complete architecture of the networks Okay now this is let me use three packets now。

No issues in the three packets。 Now I will check the files。

You can see the file name is second2 do 0 pcap， second4 do0 pcap，0 do0 pcap，1 do0 pcap。

 So there are so many files I've created okay。So timing being， I delete all the P files。

I'll give some other names， okay。So what I do is here for P2 P， Ill use P2 P。Here I use CSMA1。

Here I use CSMA 3。I use file name1 and three， so for a better understanding， I can use that。

So that in the beginning， you need not con。Now we will run again。This time in AC C。P 2 p0，0， pcap。

 P2 B1 dot10 pcap that been between node 0 and 0 and between node 120。The packet capture。

And CSM can see CSMA 220 and 420 because we have created only get device of node number one and node number3。

 that is what we have done。Okay， get1 and get 3。 That's why it is showing this。

 Suppose if we want to open this file a wire shark。P2 P1， hyphen 0 dot P cap。

Now this is how this packet sector works like this。So you can see IP version 4。

 what is the IP version 4， what is the frame structure encapsulation。

 what so you entire packet type you can able to analyze and point to point protocol IP version4 version 4。

And header length， what is header length and differentiated services。And flags。

 What are the flags affected， What are the flags set are not said， Time to lose is how many。

How many hopps it is totally 60 for What is a protocol UDP， the protocol number is 17。

What is the source that does， what is the destination，1 do 1 is a source，12。4 is a destination。

And data and the size of the data。 So data we didn't use anything because。Mostly data values are。

0ero is only because there is no data we have sent only packets we have sent。

So this way we can able to analyze the packet and here it is UDP now UDP about UDP because yes are send UDP packets。

And encapsulator type。And thepo time。Then point to point the internal protocol。

 So the same thing in UDP also。And data again 2048 B， so completely zeros。And so spot number is 4，9。

1，5，3。 destination is 1，2，3，4。A length is 2056 that includes8 bys extra sex missing。

So it simply just show you the packet because we didn't do much about this， just three packets。Okay。

 so this is how。The valleys are been red。 So TB dumper， if we have the yen。T R， then P2 P。H one one。

TCB10 R hyp R。😔，1 point derive。 So this also will rate like this。

So reading from file and linked this is how the command will use TCB D hyphen0。

 So before YR came when people are using Uniix， they use TCB D command for reading the Packer capture file Okay。

 so this thing now the same thing I gives Y Shark CM A I use the CMA。Hve3， haven for okay。

So these are the CM。 so CSMA can see they have ARP also because address Re protocol to find out to which node the packet is intended for。

 So that's why we use ARP also。So at resolution， you can see frame number 6， 64 bytes on wire。

Ethan at2， what is a source destination， What is a padding frame check sequence。And the ERP replay。

So hardware type is Ethernet， IP version 4 hardware I 6 protocol size 4 of reply to Mac address。

So like this。 so like this， we can able to read the packet。 And there is one other thing in this is。

 we can check the i graph in statistics， we can check something called as igraph。

It will show you how the e graph had been used from starting time to the ending time of simulation。

 so it will also show you it shows all the packets。Similarly， can check。C SA 1。

I'll check the e graph。From this， also。Yes， we can see this are the e graph。 Similarlyly。

 I can check for P2 P2。Statistics。最後から。Yeah Hy graph we can see peer to peer。

The packet didn't go down。 So it is in a straight line。说。🤧。This is the basic simulation。

Now well come to。Nework animation。Ed work animation here。

 So now what we code you is first we have to include header file。The header file is。Ash include。

In S3 slash net andim。Iyonmod dot H。Then you bring it down here。

 here we willll write animation interface。Andim， the name of the file， second dot xm I use the name。

Second dot Xml。Any name you can use it。So， an dot。S。Constant position。

So what we is P2 P nodes dot getta 0。 this is very important10。0 come 10。0。

 What it is important is the node number names and we need to know。

So some my students usually use lowercase instead of uppercase letters。So P2 P notess like this。

 instead of that， I can use CSMA node。 Please see that instead of this small capital line if I Ma then。

 it will be error。 Okay， so please be careful in selecting the variable names。 Okay， get 0。And20。😔。

So I copy this line。Three times help paste。Wen。😔，2 and3。At least 30，40，50。

Maybe I can increase this also，20。30，40，50。So that you can able to see how the packet moves from client to source。

See now in this example， what I have done is P2 P node or get 0。

 I put the location 10 comma 10 and C SM node are get 0 to de 1 that de that like that。

 So this node is only one node that is very common with two different variable names。

 So either I can use CSM node or I can use。P 2 B notes dot get a phone I can use。

I can use both way it is possible， so maybe if you want， you can check it。



![](img/3438204fa1b6a7e8f9918377c765ad11_17.png)

So to run this example again。呃，Yes， scratch。

![](img/3438204fa1b6a7e8f9918377c765ad11_19.png)

Now after I run this example， it will create a file called a second or X Ml。

 Now it will always give a warning on mobility concern mobility because there are wide notes。

No need of giving constant position for a wide note。 So that's why it is giving it。

 Now we can check it。Second， yeah， here， the file is that second Xml。 Now how to run this file。

Dot dot slash nettanim。Ne an。Please remember， nettan name the final list available in。

Neanium hyphen 3。008 folder inside that we have a file colors netanium。Hin caps and the Acaps， so。

Open it。Then second Xml。Yes。Open。So now we can see in 2，4，0，1，2，3，4 something like that it we。

Now I will go with the slow simulation。Then， start this。Now， we can see 0。

The node is sending the packets totally I have given three packets。

So the client will be sending packets to。The server three times。See second bucket。

You can use the fast simulation also in case you will be fast。

NowWe can parallel can take the time also here。There is a third packet。Two packets， one。

 Now this third packet comes up。And every time it comes， the server number is。This is a server。

 and this is the client。Okay。So anyway， so this is how the simulation works。

 And here this is statistics。Here it is a packet， you can see。0 to one。

 so first time it is sending and second and third packet， so three times it is sending。

And the Arab markets in both the say their bins。 The server is also responding。 And here we can see。

This are the way the table comes so from0 to 1 at time。From 0 to 1 at time， and 12 0， this time。

120 this time。And 0 to1，3 that this time and 0 to 1 again this time，12，0，1，2，0，0 to 1。

0 to 1 and 1 to 0。 So between these two nodes， how the transmission happens。Okay。

 so this is all the way。The animator works。 So let me close it。O。So I have closed it now。

 So now what we do is well go for。啊。As key trace metrics。

 So this is the next thing we will be going for。As key trace matrix。

So not enough adding any headophil here directly we can add the code here。As key trace helper。

As key I created a variable name called AS key。Then。

So we have two variable names in the helper class on is。C SMA another is point to point。

 please either point to point the variable name you can see or better we can copy this control C I made I copy this。

He come here。 So that。Enable。Enable S key hall。嗯。As key dot。Create file。Stream。

The name of the file I can use is P2 P dottr。Already， I would for a second faster file。

 So let me use。Point。To point dot here， I use this name。So that you will not have any confusion。

 so controlr C。Then control V。Here now CSMA dot enable SQL create file strip CM。😔。

CsM2 doth had been this for the second file。Okay， so I create these two files。

So these is S key trace matrix。

![](img/3438204fa1b6a7e8f9918377c765ad11_21.png)

I'll send the example， again。So， when it is compiled。Yes， it is compiled。 I show you the output。

 also。Now I can check there is the two trace file creators， CM2 dot ti R and。

There is one more file P2 point2 point， yeah。Point of point are de。

 So these two trace fields have been created。 Now we will see the what is the throughput analysis of only on the CSMA and only on the point of point。

For that， we have to go to a file called as trace matrix we already added trace matrix。

 So please refer to fast CC example I have given the descriptive。Description there， the Javava space。

 i jar。Psmatic strip are。So trace matrix， it's a jar file。 its get opened using the command。

 Java space， hyphen jar， trace matrix jar。File， choose file。Here， nus all in one， nus 3。2。 Okay。

 now it will show you all the trace files。Now we need CSsMA first， let me use CSMA。

And execute analysis。So total lines on the file is 52， total N Q is 16。

 cent packet 16 received 20 note after packets and time of analysis is zero seconds and notes。

So note number one， if you want， you can check node number 2，3 and 4。 So as you remember。

 the CSM may have totally four nodes， so it will show you all the four nodes。

But the first node is common to P2 P as well as CSsM。Now we can check the throughput。

 So this is a throughput D node number one。n number 2 and 3 doesnt play any role， the reason being。

They were not either source or destination nor they were just there are on the land channel。

 that's it。But here， the node number 4 is a server and node number 1 is common between。

Point to point under。CsmaA， so that means node number 0。

 the P2 P node of faster node is sending the packet to this node。

This node takes a packet and send it to the land and this node receives it。

Thats sorry the other two node doesn't have any throughput or output。

Now latest results here we have this lambda， E f W， V F E and E F， N W， so this value we can use it。

 as I already mentioned that I do not aware of what is this values about if you have any interest we can please check it in the literature。

And streams。I can have UDP stream。So here we have complete UDP。About it。So。In details。Okay。

 nothing was mentioned。 Yes， so this is how we can able to find a。



![](img/3438204fa1b6a7e8f9918377c765ad11_23.png)

Through put of these two nodes。 So this is on。Rrase matrix， so。We have network animation。

 We have askI trace metrics， and we have HRr also。So， in this example。In this example。We have seen。

Trace matrix。A wire shark。Ne an。 So we have seen， we have seen all the three things in this example。

So please make use of this。 So this example is available in the。

Cloud directory where I will be posting this code。 So check the comment section of my video。

 the file will be available for your。downownload。So thanks for watching this video。

Please subscribe to my channel and please share it to your friends。

For making this channel popular in networks， Thank you。So refer my website also。ESM dot com。

And you dot com s T S pre。Our search as engineering clinic。



![](img/3438204fa1b6a7e8f9918377c765ad11_25.png)

Thank you。