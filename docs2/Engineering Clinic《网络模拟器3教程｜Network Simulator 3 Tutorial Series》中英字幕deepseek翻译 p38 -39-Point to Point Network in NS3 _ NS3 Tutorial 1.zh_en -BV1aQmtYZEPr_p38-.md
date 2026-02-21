# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p38 -39-Point to Point Network in NS3 _ NS3 Tutorial 1.zh_en -BV1aQmtYZEPr_p38-

Good morning France today we are going to see a simple point of point network current between two nodes so there is a node n0 and theres a node n1 between these two nodes we are going to have a physical cable which have a bandwidth and delay factor okay so after that we are going to find out the network animation how the packets are exchange between them and we are going to complete the throughput of the particular complete network throughput then we are going to find out the plotting solutions also so everything we are going to find and here's a problem shipment for the laboratory experiment found P2 P network Good evening France welcome to engineering clinic in this video today we are going to see。

This statement on point to point end working。So the question here is design two wide nodes that can connect to each other through a point to point network that handles the data rate of 50 MBps and a delay of 5 milliseconds the first node access as a server and the second node access as a client and they exchange at least 10 packets in a total。

Simulation time of 20 seconds。 The maximum packet size is  thousand24 B and5ol bys。

 P the throughput of each nodes for the above packet sizes。

 Use any charting solution you are comfortable with。

 So this is one of a laboratory experiment for N S 3， which I am going to explain you now。

 So the source code along with the methodologyology to run everything I am going to explain you now。

 So I am going to take。The example of。Fusted dot CC file。

 so which is available in the example tutorial folder。 So Yens hyphen 3。

38 slash examples slash tutorial。 So in this folder I have this fast dot CC file。

 So this file Ill be using it。 So to start with move the above file or copy the above file。

 So copy the above file。To scratch folder。So scratch is here。 So 3。38。

 So you have to move the file to the scratch folder。

 So first what I do is I'll just go to the browser window。And。N is only in 13。38。Then Nus 3。38。Then。

 examples。Then tutorial。And first dotcc。 So this is the file。 So control C， Im just using control C。

Then back and move to scratch inside the scratch， I am pasting it here。

Now this way I have just now I open this file。Now， this is the file I am going to use。 Now。

 this is how the way the question is asked。 So n0 n1。Add is a point to point network， so 10。1。1。

0 this an IP address ranging is given。So to to explain you the source code I already given my given a video in my channel on explaining Fast dotcc file。

 but I will briefly explain it again。So。First， anytime we will be using namespace N S3 using Naspace N S3。

 which is similar like using namespace S TD when we do in a general C++ programming。

And we create a main function in the main function we have argument count and argument vector so this is argument。

 so while we need an argument count you can able to check that in the second or CC file。

So now the time resolution time is on nanosecond time resolution so far that we create a。

Cls here this research resolution belongs to the time class。

 That's why we time scope operator and set resolution。

 We are going to use an application called as UDP E client and UDP E server application。

 So the server will be echoing the number of packets， and the UDP will be receiving those packets。

 This is what we are going to do。Now the node container node the node container is the name of a class that creates a node object。

The nodes that create two。 So totally we are creating two nodes。So within these two nodes。

 we want to create a point to point helper class。 So we create an object name called us point to point So point to point set device attribute the data rate is 5 m it is given。

 So now what I am going to do is I am going to use 50 Mps here。

 So the as the problem statement I am going to use 50 Mps。 So let me change it to 50 Mps。Then。

 the delay is。I am going to use a delay of 20， I mean。

5 milliseconds can which is given here as 5 milliseconds。

 So this I am going to use as 5 milliseconds。Okay， so now we have once we have set the note。

 then we have created the point to point helper class。

 then we are going to create a net device container。

 So net device means its this is the place where we can able to set the Is。

 we can able to set the hardware and software for a network interface card。Further that。

 we create an object colour devices。 So device is equal to point0 point do install on these nodes。

 So nodes is a variable， I mean， this is the variable here notess。

 So there we are going to install the point0 point helper class in this okay。Now afterward。

 we want to queue network connectivity to both the nodes in0 n1 for that we create an object call internet stack helper。

 We want to establish network connectivity or internet connectivity for all the nodes。

 So now again install these things in the notes that is a stack dot install notes install this next thing is we want to set the IP and 4 address so we can able to set IP and 6 also but in this example I am just telling you only on the IP and 4 address helper So create an object colors address Now first we are going to set the base address base address means 10 do1 do10 So now we can see that this0 means this is a first address of the network So usually0 will not be allocated to any single computer it is called as an network address So we set the base address here and the sub masking is given here 252525 upon0。

Then afterwards create an interfaces and assign these IP address to all the devices。

 So devices is a variable name only we have created as a net device container Now assign each and every IP address to these devices。

 So that means any number of nodes when you created all these IP addresses will be allocated automatically by N S3。

 So now in this case we have two nodes。 So one node will be 10。1。1。1 Another node will be 10。1。1。

2 that will be allocated so now we have created the node we have created the channel we have created the net device container we have created the internet Internet were。

😊，We set the IPO and forwarders and we we create the interfaces also now our application。

Now in this application we have UDP E server helper E server so the name of the E server and here the port number is 9 is given port number in case we have a doubt I can give it as 8080 port number 8080 Now application container server apps E server dot install node dot get1 now who is the server and who is the client Now as per this program I said that the first node access as the server that means the first node will be the server first node is presented as this way So this is a first node that win node dot get of0 is the first node。

He is the first two note。I'll use the commenting line here。And the second notice。Note that get off。

One is the second node， so these are the two things that we can able to set on。Okay。

 so now what we do is so the node of gets 0 is a server， So I will make it as server here。

 So it is 0。 There is a server。Okay， so first the echo server， I am setting the node 0 as the server。

And server apps Im starting the server at 1。0 as per the time simulation I given us 20 seconds。

 So 20 seconds they want to exchange packet as per this program I asked them for 20 seconds。

 Okay so then I am going to set the UDP client helper So in the UDP client helper they wanted to exchange 10 packets with each other within each other。

 So I am creating us 10 packets here is here it is given us one packet I am going to create 10 packets。

 Now E client will be the get address of。😊，One here interfaces not get。

 So who will be the client that we we are going to do now， the client is one here。

And the port number is 8080。 So instead of 9 we have created to 8080 is is a port number。Now。

 total number of packets is 10， and now the thing comes up here。

 The maximum packet size is  thousand24 bys and5hi total bit。 So you have to do two simulations。

 one simulation with 1024， Another simulation with52 bit so that will do that Now by default I have 20024 here。

 Now application container。 So I am going to create node node that get one means that is a second node。

 So this is a second node will be the client Okay， So the client。

 the client will be starting from 2 to 20 so。This 20 seconds we right。

So no but we need to plot the throughput characteristics。

 So what we do is we have to write the code here。For AS key trace， we have to write the code。

 so ask key trace helper。Ski。So this one line we have write it then afterward。As key is over as key。

 then we will create an object here so this object is this an object we are going to establish the AS key for this point to point channel。

So in this， what we do is point to point channel dot。Enbel。As key， all。Then ask key dot。

 create file stream。Create file stream。So we are going to reiteratedirect all this information to thousand24 dot ti the trace file we are going to。

Write everything here。 Now， these are the three two lines we can able to do it on a As key trace helper As key。

 So this is for Askki trace。 Now this is for。Neanim。Nate enemies I want to use。Animation interface。

Anim， I want to create a file name colors P2 P dot。Exm， I want to create this file name。

Thats it enough P2 p dot Xm I can give so for animation to work， we have to include a headerphy。

So the header file is given like this hash include。N S sorry， N S 3 slash net anim， hyphen。

Module dot H。 So this file we Im going to include it here。

 So now network network animation is done and AS key trace is also done。

But in case if we want to establish Pcap， also we can use here P cap or wire shark。

This also we can able to use here。 So for that。What we can do is。Okay。

 so nettanium and asquiris both we have written。 So now we are going to run the simulation for two types。

 okay， so。No here。😔，To run this file。Let's open a terminal。So C D N S， hyphen， all in one hyphen。3。

38， slash N S hyphen 3。38。38， then。The command is。As simple as to run。 So dot s n S3， run scratch。

Slash first dotcc。So this file， we can run it and。제인지다。Thouous24 to5hi 12。As specet says。And change。

I told a tier in the trace file。And道。Comple target it。So。

 you have to do the two tense compilation so first time will be like this and second time one more time you have to do the compilation like this。

 so we have to get two files so。So so we are going to now。R the example that P2 P example。

 So C D nus only in 1，3。38， shlash yus hyphen 3。38。Then dot slash in 3 run。

We have the file in the scratch folder， the name of the file is fast to dotcc， so once we run it。

You can see that the output we got it here so but the client is sending the server is not sending。

 so that means we need to edit the file again so。Scratch first dotcc， So when we edit it。

So we can see here。唔好。This change。 So we have to give get at of 0。 the first at of 0。

 we have to give it。Okay now we'll run it again。When we run this。Okay， you can see here now。

So at two seconds the client sent the bytes and then 2。

0051 seconds server received it at the same time server also sent one more104 bytes and the client received1024 bytes so this way that 1024 bytes simulation we have just1 it。

Now we have to do the same process again for the fight tool so now we can check it here。

 we got one file dollars 1024。t tr is created and p2 p xm dot xml is created we will see how that network animation can be viewed but now we will go for creating the fight tool。

So again， we will open this file。For changing that fight well， so now instead of 1024。

 we use Ph well and instead of 1024 here， we change it to fight well。

So you have very simple logic here， so we have this thing fight well and let this fight2。Okay。

 so now we willll be running it again。ICl the screen。And I will be running this again dis firstted。

cc。Yes you can see but you here it doesn't mention anything about the throughput here we have to calculate the throughput okay now click this Ls now we got two files one is 10 t424 dotier one is5able dottier and we got the P2b directmal file so P2b directxmal file is only one file there can be run using it using the software call us nettanium so for nettanium。

Again， you can open a new terminal or you can directly up here， So N is all in  one 3。38。

Inside this folder， we have something or an atanium。So。

 inside this all in one we have netanium is one package n 3。3 is another thing。

 so we are going now with a CDd netanium。So， once we go here click El you can see there is one green color file this file net an you can see any uppercase letter ya also uppercase letter so what we have to do is we have to run this example like this dot slash net an。

So， do slash means in the current folder in the current director we have one executable call us netan execute that run that that is what it means so once you open it。

So， this datatanium。Just open this file in the top left， then go to N all in 1 ns 3。

38 and we got the file colors P2 B dot Xml， so just open this file。So once you open this file。

 you can see that we got these two nodes， so to make it bigger。

You can make it to the node is number 5， and if you don't want the grid， you can disable the grid。

 So you got the screen so0 and1。 So there are two nodes here。

Now here there is a simulation button here， so the play button， so once you start playing it。

You can see that the packet exchange is happening here。So。

 since we have given 10 packets so every time there will be for one exchange there will be four packets because client is sending server is sending back and client receiving back so you will be getting that time frame so you can see the timer is running here five seconds now。

Likewise， after 20 second simulation we have done it。

 but before that if the packet exchange is completed then。The complete simulation gets over。

So this is just for checking whether the code is working or not for that we use something called as a network an。

 so network animation。Our animator。Okay， so this thing is done。

 So now our main part is that in our question， what we have created is we are the same to。Fnda。

To be open that file。Yes。So now in this example， what we have to do is we have to plot the throughput of each nodes for the above packets so we have to plot the throughput so in that case what we have to do is。

We have to run the example， so now here we are going for。Another software call trace matrix。

So this thing， this， we have done it。Then。哦我本。Another terminal。AndGo to。C D， N S， all in one。

 iPhonehen 3。38 slash。Net anim iPhone 3。109 slash then。Dot slash net an。So once you do that。

Open the example file。And then check the output in the animation window， animator window。

So now next is to find the。Next to find the blue。就不。Did the help Bob。Help of a software called。

Race matrix。It is already installed。手职。The video。In my channel。For installing。Trace matrix。So。

That's what now again。Open another terminal。Or use the existing table。

So now what you do is Cd and put enter， then Cd trace matrix。Chasmatictics I will show you now。

 so open another terminal， let me go into the next next terminal。So Cd pra matrixs。

 you can see that this command so Cd pramatics。Then we go with the Java。

Hhen jar press matrix structure， so this command we can run it。傻。唔有啊，系瞓唔着。Trasmatic structure。

 So once we run this commander。A window gets open like this and this is what the trace analyzer。

 a trace analyzer for Ns3 so click file， choose file。And go to the location of Ns all in 1 3。38。

 then Ns 3。38 and we have two files 1024 and 5 all that here so now 1024 I am just opening。

Execcutute analysis once I do the execution。We can see that how many number of lines on the file all this thing is there。

 so now the throughput here is the throughput and the goodput we have two things。

 so in this example we ask only for the throughput but maybe just control C right click on copy or control C。

Then come to the editor window。And。For 10，24 dot here。Here is a throughput okay， so the zero node。

 the throughput is this the first node， the throughput is this and this value is a good put so good put is not needed so now so we will remove the good put。

Okay so in case if you want to use so only to two disimals you can use that this is for 1024 signal for 10 512 you can able to see apart from that we have other results also here but in this question we have asked only for the throughput but if you want to plot any others also you can able to plot it here so again it will go with file choose file。

I'll go to52 dot Tr， execute analysis。Once it is done now when you come to the throughput here。

 so these are the things here。So now what we do is。For5 total do here。This is the throughput。

So from here to here， I will just delete that。So，0 for 957 and 1957 and0 for both are same so for only since there is only two nodes here and we have a bandwidth established between these two nodes this is what we are expecting but if you have more number of node you can able to really find the throughput well and good and we can able to find the average throughput also will be varying drastically so when the number of nodes are a different kind of network and different kind of。

I mean nodes are different types of nodes like that。

 so the throughput might vary so since it is a simple network。

 this is what the throughput we got now we want to plot this so we have 01 so node number is 01 and for 4024 and for 5 12。

Soう。

![](img/9a395badcbba20885af10f5af172f773_1.png)

We can able to plot like this， so maybe I'll just open one charting solution colors。

I'll go with the Lib office。

![](img/9a395badcbba20885af10f5af172f773_3.png)

So since traditional this Linux， I am going with the labor office in case if you want to use GNU plot。

 you can able to use GNU plot。So what you can do is 1，0，2 4。His was a5，5，2，1，0，2，4。

So these two things click a new insert row above。So， this is。들로 볼。And here， node 0， n 0。音文。

So for5hi2， the value is 492。27。From here，957。28。So when you plot the insert chart here。

 so you insert a chart。And in this chart， either you can give。Can see has even throughput for5。

Its there like this， and this is for this so throughput。



![](img/9a395badcbba20885af10f5af172f773_5.png)

![](img/9a395badcbba20885af10f5af172f773_6.png)

Yes， if you want to go with the GN new plot on this thing we can able to do the different things on a G new plot so what you can do is we will have this these things I will just copy this thing in a new file。

So0 and1。 So these two things。人道。Let me close this window。And 957。28482。27， so will copy this。

So let's say we will go with the G plot。 So this thing。And this so here， this will be 492 point。492。

27。492。27。And4 92。21。 So this is what。드볼티 자로。Throughput dot Txt。

 I give the data name throughput dot Txt I have just given here。Now。

 I have ready one more file called this controlless G N U。Dot PlD PlD is a plot file。

 I am going for a plot file here。So what I do is set terminal Pdf。

 so I am going to create a output of a Pd file set output the name of the P file is through output。

Startt PDFdf then set title I am going to give us throughput versus。诶。

Tput versus packet size packet size， so this is what we are going to do it now set x label is x label is packet node x label I can say that node number。

And the set while is while label as a throughput。T put in bits per second。Okay， so then plot。

We are going for TH R U Gh throughput dot Txt。Using one column2 one column2 means first column and second column。

With the alliance points with the lines points。So， title is。It's 1，0，2，4， 1，0，2，4 s。10，24， okay。

 comea again， T H， R U， G H throughput dot T x t。Uing啊。要先。One column 3， on column3 with lines points。

Title file tool so these are the two things so this is a simple thing here so terminal PDFs I going write the output in the PDF format the name of the PDF file and the title is above the graph then the x what is x axis and what is a away axis and that the plot is a command and then command I am going to use the throughput or text file so from this file I am going to one column2 means one first column and second column and first column and third column so column number one is common with both the graphs so now I am going to run this example。

Now， as usual I go to this terminal put cd and enter。

 then G plot put the code G dot p so this this is the name of the file so once you do that no errors then we go back to。

This， you can see that。We have the file throughput。So through put dot PDFdf now yes。

 this was generated now when you see the through put dot PDFdf。

So we can see here so one line is got we got it here so we can see the pink color line then another line we got it got it here so the green color line。

 so this is the throughput that what we got in the each and every node but if you want to take the average throughput so take the average of all the values then you plot it so that we also enable able to take the so we can see that now this is the title。

And this is the v axis and this is the x axis， so thats what。The file we got generated。

So hope you understand this how to plot it， but the plotting is you can able to do different method of plotting I use this method。

 you can use any other tool like Microsoft Excel sheet or Lib office or whatever tool you like you can able to do that。

So， so thanks for watching this video， friends， so subscribe to my channel。

And share it to your friends also。 Thank you。

![](img/9a395badcbba20885af10f5af172f773_8.png)