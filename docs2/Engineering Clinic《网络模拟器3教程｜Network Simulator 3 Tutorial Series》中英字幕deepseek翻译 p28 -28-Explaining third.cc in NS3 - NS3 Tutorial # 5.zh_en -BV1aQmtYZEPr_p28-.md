# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p28 -28-Explaining third.cc in NS3 - NS3 Tutorial # 5.zh_en -BV1aQmtYZEPr_p28-

Hi， friends。Welcome to Engineering Clinic。Today's topic will be on。Wired and wireless networks。

Simulation in。N us 3。 So this is what we are going to see now。

 So simply this is called a third or C5。hi is there comes along with the N network， similar to3。

So we can see how this simulation works。So it includes three kind of networks， P2 P。C SM。

And wireless network。So how we can integrate all these three networkss into this。And of course。

 we can， we can use SQ trace file。Then。We can use wiresha。And we also use netan。

So these three softwares will be using it。For demonstrating it。So， let's first。我 bit。

Copy the file to scratch folder。

![](img/3b914f0a109928b372c3be40505338ef_1.png)

Okay， so what I do is I'll just。So inside this file， use 33。2 name。Then。

So here we have an example folder examples， C examples。Then C tutorial。

In that you have a file called us third dot CC。You can see theres a formula  third docc。So， copy。cc。

Then we can use scratch folder。 I can copy to scratch。 So I did it through terminal more。

 We can try out this in G Y also can easily do that。Okay， then we will come to。This folder。

When you close it now， I will open a new terminal。

![](img/3b914f0a109928b372c3be40505338ef_3.png)

So what I do here is。

![](img/3b914f0a109928b372c3be40505338ef_5.png)

I created a new terminal。I copied the file already。 Ns R in 13。29， then Ns 3。29 here only。I'll check。

 So here I have a folder called scratch。 So this is a folder inside this scratch folder。

 We have the file folderers third do。Okay。So first， let me run this file later I can。

Show you what is the content of this file。 So we have to be in this folder。 So always you check it。

Prescent working directly。 PW meanss percent working directly。

So it shows you that we are in this folder home the commar Ns R in13。29 and Ns 3。29。Here。

 I'll be running this command like this。 dot slash w。Wuble hyphen run， scratch third。

You need not use any extension for the CC file。Now when you check it， so your output indicates that。

This third docc compiled successfully。Re it's running for the first time we take some time to get compiled because it D it depends on form many libraries。

 yes。It has done。 So at two time two seconds， these mini bytes have sent to this port， blah， blah。

Okay， so we will come to modify this code will come shortly。By by the time。

 I will just explain this code how this what this code contains。



![](img/3b914f0a109928b372c3be40505338ef_7.png)

So， you can see。There are so many header models have been included core module dot H。

 point to point model dot H。Network model applications， model， mobility model， CSMA model。

 internet model， Lyons， Wifi helper and A society。This is how the network topology looks like。

 so we have a node n0 and we have a node n1， So these two node connected with their point0 point their IP range starts from 10。

1。1。0。So I will be changing as per my convenience。 What I do is I will be changing to 172 point。11。1。

0， I will change it。Then。This N node is part of another land network。It half 172 point。11 by 2。

0 and up to n 4。Then afterwards， N5 N6 n7， they are all wireless nodes。 This is mobile nodes。

This three。But whereas N is an access point node。 So that's what we is access point。

 So wirelesss have an IP address range 172 point。11。3。0。

 So this is how I am going to change the network so that well have some minor changes initially Later。

 we can go for a bigger changes。 Okay， so I have three network point to point。Lan。

 which we call as CSMA。And here we have lifeA， okay。

NowAl in the first dotcc and second dot CC file we have seen。These two alone in firstcc。

This together from Nar to n4， we have seen in second dotcc。

 Now we have included wifi also into it so that you get a glimpse of only peer to peer network。

 only CSM main network and peer to peer network。 And then we have included all the three networks。

 okay。Okay， now no explanation needed here， because already we have explained in Fast start C。

 you can refer it。There also no explanation。And now we have a main function inside the main function we have bull verbos equal to2。

 So I'll just this is very important not here at the end。

 I'll just tell you what is this purpose of it。And you win 32 p。

 this is nothing but unsigned intesger 32 bits。And CSM and CSsM is3。

 So a number of CSsM nodes is three nodes。And end wfi is number of wfi node is3 nodes and bull tracing equal to false that also please maintain this value。

 So through on the files here。Okay， so then。We have command line。

 So command line it tells you that if at any errors or anything there that has to be displayed。

 So number of CMA node devices， CS SM may number of I stationary station notess and Wifi until equal obligations to log if through and enable P。

 So the packet captures a Y sha accuracy。Okay， so。So we have descend this command。Afterwards。

If N Wifi greater than 18 S TD see out N Wifi should be 18 or less。

 otherwise grid layer exceeds the bounding box。So what here happens is we have a grid kind of layout。

 so the grid wheel can hold a maximum of 18， whether it should be less than or equal to 18。

 it should not be more than 18 so now this value is only 3 so we need not bother about it in case if we are planning more than 18 you have to descend the grid accordingly okay。

Okay， so now well come to this code here， node container。So， create。The P2 P notes。

So the node variable is a P2 P nodes。PT P nodes not create to。 So totally we are creating two nodes。

 sub preferably the node number n 0 and the unknown will be created。Will be created here。

Then we have helper class point to point。So between n n and n1 because between these two node。

 what is the delay and what is the bandwidth， That's what we are going to data rate and the delay。

 So if I M previous is the bandwidth and 2 millisecond is the delay。

 This also we have seen in fast start CC。Next thing is after， after creating the notes。

 we have to create the。Network devices。 So that's what have you to P do。 There is a ethernet cut。

 So we have to allocate and address I S further。 Further， we need to have an ethernet car。

So this Ethernet card will be installed on the P2 P nodes。 This also we have seen in。他 start。

Afterwards， we are creating CSM nodes， node container CSM nodes。

Now here what happens here is so we have Hu n2 and3 and for these three are reddicated only for CSM edge and the land。

 but end1 is common between the peer2 pen network as well as the land。

 So these have a special property。And this can be referenced using two variable names。 Okay。

 but these three， So this N CS SM A value 3 is nothing but this， whereas this N1。

 we have a surprise statement。 So that's what given here。

CSMA nodes run the variable name together here is CSsMA node。And here it is speed minutes。

 please don't forget this because we have to use this in the back。

So PC S may node that add P2 P notes that get up form。So usually when a variable name is declareded。

 So what we do is P to P node dot get tough0 represents。The0 to node。

 that is 0 to node means the first node。In numbers。Whereas P2 P。

Notes dot get tough when the represents there。First node， there are two nodes。

 So first note representss 0 and second note representss 1。 So getta1 means now。

 you know that this is the。This note， okay， so this note part of now the CSsMA。

So further it is first getting added to the CSM not variable and next we are creating create N CSM and CSM is already declared with value number 3。

So totally three nodes are been。Okay， so just to declare a variable name。

So if you are learning for the first time， if you are confident on C programming or C++。

 you might feel it is tougher， but please listen to the lecture carefully。

Next thing is similar like point of point helper we have CSM helper CSMA attribute again data rate and delay so here the data rate is slightly higher because so how many nodes share the common bus so that is why we have 100 V。

And 6。5 micro secondsconds R we can say 6560 nanoseconds。Now we have。

 we have to install the Ethernet cards for。Nots of CSME are the land nodes。

 So that's why we are using。 We are resling these things under the。CSM notes。 Okay， now done。

 Now we are coming into wireless。Okay， so in this wirelesslash node。

What we are going to do is node container， Wifi station notess。So first thing。

 we are creating a Wifi station notes。Wifi station notess dot create n wfi。

 so Nwifi you can remember that we have created totally three values is3 nodes。

 So this Wifi station not nothing but n 5 n6 and n7 all the three are Wifi station node where because this notice in access point node。

So wireless is slightly tougher to generate so。Note n 5， n 6 and N 7。

 That is what these three have been。Notode container wfi E node now I am creating another A node call wfi E node where P2 P node not get up 0。

 So now we understand that this node get up0 will be the node number here note。

This is are node number and not。 Okay， so this nodes。

 this node will be the access point node for this wfi， whereas n1 will be the part of la。Okay。

 now next thing is we have a channel helper since Wifi always deal with Ta。 So the ion means。Yet。

Yet another network simulator thats what the meanss。Because when they design this industry again。

 they use another network simulator。 So that's why they use what name instead are giving any name So they use the name colour Ys。

 yet another network simulator。So this channel ya answerifA channel helper default。

 So we are using the default channel allocation that means the default channel properties If you want to change the channel properties。

 you can go the source code of Y channel helper and they can modify the parameters if you are electronic student。

Or a telecom student， if you are a project on a channel metrics signal to noise ratio of those things。

 frequency modulation， all these things， you can go inside the channel source code and then you can change the parameters。

 but by default， we are using the default parameters。

And it has a physical layer also here there are also。

 we are using the default physical layer because we are not bothering much about what could be the frequency。

 All these things。 Everything is by default。 There is a default set up。 So we are going to use that。

Yes thing is。P H we are set channel， channel do create。 Now we are creating a channel。

 So channel is nothing but creating a communication path。That's what channel means。Okay。So。

 this will be creating。Next thing is wfi helper wfi Okay now wfi usually what happens when whenever we browse internet we will be browsing wfi through a wfi manager or we have a router the router manager is toing so remote station manager so the wfi helper class that helps in setting a wfi for a particular node。

Further， we having a remote station manager。So there are so many station managers are available。

 remoteote managers are available。 So one such manager is art Wifi manager。

So this also belongs to a3 as。Namespace。 So inner 3 level colon or Wifi manager。

Next thing is we have channel。 we have physical layer。

 Now you have Mac Mac media access control who have been given access to access the network。

 So myfi Mac helpper， the variable name is Mac。Then SSD， So SSAD is the broadcast I。

 So suppose whenever you are switch on your mobile phone。

 you can see what are the wfi signals available So that name is nothing but this SSI。 Similarlyly。

 these node have to attach to the SSD。 So what kind of name I can give So the name is given us。

In the same heaven a society。On set type， what kind of Mac it is been set。So station to Wifi in X。

 So what is the medium access control for the station notes And it says say active probing is false。

 So active probing is false means see now we have two different types of nodes in Wifi。

1 is station notes， another is access by node access by node is fixed because。

We have a ether connectivity comes up because it isn't appear to be network， whereas station notes。

 they will be moving here and there。 So we have to have two different models of。That work。

 So active probing equal to it is false。 It is Boolean value false。 That means active pro。

 it never it never keep on probing the SS ID values。 So that's what active probing。

So the value is active probing means。They keep trying to check。

 is there any wfi signals available in the nearby area， So that's what active pro be。

So this type of Mac is set to I phase station notes so now you can see the N container。

 it will be installed。On the whiteway station notes， what are the things its all physical layer。

 Mac layer。On this likeway station。Now well come to another model colour E P Wifi max。

 So this is stationary Wifi Mac or station。This is A P wfi Mac。 So this A P wfi Mac， again。

 we have a value， and this is inana Wifi A P node， P H A and Mac。

 So this Mac is different and this Mac is different。This is for station notess， and this is what。

Access point node， access point node is fixed。Now every wireless node we have a mobility models。

 so we we have seen that in Nna 2 also we have so mobility models in Nna 3 also it supports various mobility models So further we have a think call us mobility helper class so mobility helper mobility。

Mobility that set position allocator。 So we have a grid position allocator as if the nodes will be placed like a grid。

So that is a name of this gridilt person allocator。

 so minimum x minimum y delta x delta delta x is the difference in the value and delta y grid with this3 and layer type is row first。

 so it is row class column so row first。Okay， so that means so。

Minimum x commma 0 goma 0 to phi commma 10。 So that's what it means。 So。

 so every gridit have a value of0，0。In the X axis， it will be5 in our V axis， it will be 10。

So that's how this grid position locator will be。 and the mobility model we use is random mark two dimensional mobility model。

 So that means the node will not jump because they will be moving only on a two dimensional path x and y。

So either it can go in the right side or in the。straighttraight left side， but it won't。

 it won't jump。 the node could not be jump， or the node could not flow in here because the is axis is missing here。

It is a random mark two dimensionsal mobility model。

And rectangle on what value if the node can move this is the and then model is set to by phase station notes。

 please remember again this these node is1 nodes only those nodes have the model for mobility because the access point node is always。

Stationary， it is fixed on the wall or fixed somewhere firmly。Okay， for that。

 we have a constant position mobility model means they are not never mouse。

So in case we want to use all the nodes to be constant mobility model also you can able to replace this random 2 d mobility model model to constant position mobility model in that case you need not specify this rectangle value we need not specify。

Yesエス。So now this thing is now we are come to the setting up of the networks。

 So here what are an internal track。So we install this stack in all the node where CSMA nodes。

 Wifi E notes， Wifi station notess， we install everything。

See now why they have returned is by A P node is just one of the notice on the P2 B node。

And the CSMA node， one of the node is on the P2 P node node number one， this is not number0。

 So there is no P2 P node installed because we are doing everything on the CSMA notes。

 YP P node Y face station notes。Next thing is IP now I have changed IP to 172。t1。Here，1，72。Poin one。

I'm here at once or so。Do you do。Yeah。Don， so these three things。 So we use P2 B interfaces。

 P2 P devices， CS SM interfaces， CSMI devices。And station devices and A P devices。 So that is set。

Now， UDP equal cos server。 So the basic application is equal application。 Again， Ill go with the。

Ralally colour 34 by 6 is the port number。And application container server apps。

 So now what is who is the server E server or install cM not not gett and cM N is 3 so get of 3 So that means。

C SM node will have four values。So this value here will be。Cエスエ me。

So this is where most of the Mil be countries， here a may not chart。Get of 3。

So it will be having four valuesalies，0， comma，1， comma 2 comma 3。Okay， so now we go the。

Wellal here this top。 So this n1 is nothing but C SM node do get of 0。 This will be getta 1。

 get up 2 and get of 3。 So this will be the server。 So n 4 is the。So。

I is a server as per of statement。 This is a server。So now we'll come back here。So this is a server。

 Now the server。Start by 1。0 y by 10。0。 and now。3，4，5 change the port number。

 Now I am going to create that client echo client。the clients have N Valley 1， let's say used to。

A number of seconds is one on the use。2048 by。2048 bikes。

Now the client application in client apps echococlaim or install wfi station notes dot get n wfi minus-1 now we can check this value。

Now just copy this here。So n wfi-1。 So that means N55 is nothing， but the value is 3。

 So 3 minus-1 is 2。So totally， well get a value of to get tough to。Now we can see only ST nodes。

 so EP notes was not mentioned here， ST notess。We go back here。So when I aspect this。

 this is the E node and this the S T nodes。 So E T nodes there are totally three nodes。

So as per this n p n6 M7， So this will be the claim。Hope you got it。

 So N 7 will be the client because get up to get up 0 is this。Gap phone is this。

 and get up to use this。O。No will come back here。This is again of。

 So now this client will be starting at 2。0 and start at 10。0。And I global routing helper。

 popular routing table see now what kind of routing algorithm we have to perform there was no mentioning here。

 but NS3 supports a global routing table so that it generates rootuting table for all the notes by default it have some。

Before protein table so that protein level we are using it in case if I use ADV protocol I use DSDV or any kind of protocol。

 we can include those quotes here。Okay now sulator stop seconds， 10 seconds will will be stopped。

 Okay now we can see if tracing you call do prove。Point to point do enable Pcap hold is this is the packeter capture。

PHO had enable Pcap， A devicess that are get0 and CM had enable Pcap。Third CS SM I Ra 0。 Now。

 tracing equal to2 means this will be enabled。 Now see what is a variable name allocated for tracing。

Traing is given us false。 So what you do is you make it as true here。

If you let me try faster with the policy， the data I will show you how whether the files are generated or not。

So this is the default generation of bracket capture。 So now what I do is I use P2 P。This is for PHY。

 that is Wifi， wireless I use。And this is what CSML useMA。

Now we can see A devices that get0 means so the access point devicess get0 there is only one node and CSM devicess get0。

 so that means CSM databases again you can get only for one node I am going to get the packet capture。

No。I need to create three files some some kind of files I need to create。

So what I do I'll be running this example。 So to run this example， this is the fourth。

Yes we have made some changes so so now we can see two times the code executed here because we have included two packets。

So 1，72，111，72，3。3 like this。 So we have。This packet。 So the code is would keep fine， okay。

We have to check whether the requested files are being created or not。 So no。

 none of the files are being created。So what we do here is we will come back here。

We make the pricing equal to true here。So once you make the tracing equal to 2。

 I will run it again again， you have to compile it。In this case。It will be generating a。Okay。

 now we can check it。So P2 P0，0 Pcap， P2 P 11 dot0 Pcap， CSMA 11 Pcap。And wireless0t want pick。

 So to run this file， let's say I use wireshark。Wreless。

So it will show you what happens to the wireless speakercap。So what happens at each broadcast。

 what is the source was the destination， Whats the broadcast address。

 So you can get the complete information of the wireless network。Even you can statistics。

 you can go for the e graph。So what happens to the e graph during the initial time in the initial time because a broadcast。

The packet copy will be more after that， if P。Was getting down。And it is constant。

 So thats how this works。And。So you can see the beacconons also。 So what beaccon。

It receives how many we。 So those information will be here。To becon frames。

 And this the wireless line I to 1 on wireless。What times the what are the taggged parameters。Sデパム大。

These things。你咋问的不明天。So this way， I can able analyze my W shop。Okay。

 so the white sub have powerful filtering properties。 You can。Re for Bo F graph， you check。

 So even you can check the flow graph also for the internet。It is very powerful。O。Right。

 so this wild wire sha， we have got it because of the trace。No。Rather than going for Vis。

 if you are not confident on Visg， if you want to do some plotting characteristics of something。

 so I can go for creating a ask key。File trace so。嗯SB。Please， help。As key。I create a S key trace。

As keep this as keep this Albert S team。He had to that。原那不。SP。好了。呃。As key。

 the variable in S key dot create。Fight stream。So please remember that I have put a C S capital。

 a first capital letters and A S uppercase letters。By stream， and I use the P2 P dot Tr file。

I create a file well P2 P dot here you can see the brackets completed。

 now I need to use another bracket。So the same variable name I use as a PO。

 you can see what variable name here。He should be very。

This variable name you have to keep in contact on it because you cannot check the wire shock on the device DCM devices rather than you have to check on the helper classes。

So here to helper。And CSM help CSMA。AndP2 P point of point Hilber point of point。

 So only on the Hilper classes， you can verify the trace price。Okay， now I'll just copy， paste this。

Three times， I'll do it。Okay， so now this second time Ill change it to CM。

 third time Ill change it to。Point to point。copypy the variable here。So， sometimes very very。

They will be typing wrongly， so by changing upper case request in that case， you will get some error。

 so P is not P to P is PHY。This is CS me。And this is point。B2 B L B okay。How我 done this全不来げ。



![](img/3b914f0a109928b372c3be40505338ef_9.png)

Yes， normal runy。Scratch。得罪。So like this， your first exercise could be you just take down the codes available in the example tutorial folder or examples folder and then keep running one by one and you can check how the things are working。

 then go and understand the source code。

![](img/3b914f0a109928b372c3be40505338ef_11.png)

Okay， now well check it here。It creates some trace， So BH R T R。P to B Raier and CSME Rat here。

For example， I open some file here， cM。t T。This is how it looks like。So it's completely asky。

So I don't know how many lines。 let me go to the end of this So totally there are totally 40 lines。

And I use PY R Tat also。So you can see this are the information comes。So is said capital name。Now。

 it has totally fight on degree lines。 Okay， so now I will just read out one of the packet here time 0。

 03 to seconds the device list not number one Wifi net device if state transmission mode。

O F DM or rate 6 B S Mac header。 So that is a beconons。to Ds from Ds more fragments re more data。

 So BSSI， so this is a complete information on the wireless network。

So and see what kind of data rate it uses 6 M BB S2 B 24 and V S。So in this data read， this works。

So and then we have some flag values here， and there are some operations here。

 So this is how each line of data。Is generated in the AS trace。 Askt trace field is very powerful。

 You can make use of that。So now we'll see the output of it。 Now we'll see how to process this file。

 So we have another file call us。And close this sky。Yes。

 we have another fairly color trace matrix software。



![](img/3b914f0a109928b372c3be40505338ef_13.png)

So how to use this straight painting I you just go。So we have a folder colour trace matrix here。

 So CD trace matrix。Check my blog again， how to check my YouTube channel that how to install trace metrics。

To very simple。So Java space， hyphener trace。So see the command here。

 so this is how this command works。28。NS201， N 3。 28。And here I have PO here。Exive analysis。

So now this is how this file。 So simulation totally5 over3 lines， as I show you already。

Total send packet1 that they received03，90 and total s damage1 seconds of approximately。

And these are the for 0，5，6 on this access point node and these three are。My case station notes。

And throughput for not majority1， because not much7 was the。嗯。

Plae node and the node material was the access point node that have a connectivity between the server and the plane。

Now there are some little steer result and streams。So it is UDP traffic only。

 so we have echo code traffic。 So we have UDP， all UDP 0， UDP 1。 So all traffic。

 and we have an option here， export graphics。The first and the second are C file。

 I didn't show you this。 but here you can see the export graphics。



![](img/3b914f0a109928b372c3be40505338ef_15.png)

Now， in your exportography， you can able to see a G plot here。

 So require G plot to be installed here。 you should have installed G plot。



![](img/3b914f0a109928b372c3be40505338ef_17.png)

SoThere are so many varieties， so many options here available。 we can use it。

 So now we can just make a view。 So suddenly， you will get a view of it。

So now we can see title all UDP stream comparison， so you can change a name。うUリピ packet flow。

8了 exampleンブ。Okay， so in the title， we can use U to the packet flow。

And the exact is yellow upset there again I use time。うん下げす。How millise secondsd I can use。

I don't know what is the unit of it。Then delay variation by default it is given a delay variation。

 and let me use it。 Now we can see UDP packet flow delay variation and time in mill seconds。

So if you want to enable grid， you can enable grid。 again， you can use this icon。

 This is a refresh icon， and you can use the enable grid。

This is for the delay data to plot this delay and here we have packet delay variation also as for the packet how the delay is。

And this you select it， and click it。So nothing is visible here。And by here， we can use。

Instead of points， plot sale you have will find against these lines also。When I use lines。

 then again even it rises， you can get that delay variation。

 you can see that from here to here we have a delay variation。 So based on lines lines and points。

 it will show you both。I can you reference it。 so you can see the point here。

 you can see a point here。 and these are the delaylays being within。So like this。

 we can in a check every and even we can plot histograms， we can plot legends。And IPDV also。

 we can try out。 So let me try this。 IPDV is no significance of。This work。But thiss what here。

 the P D。And the language， if you wantt increase the language， you can increase。Lame with。

very bold to printing never。And if you want to use cubic planes。

 So there are so many options available。To make this。And even if you want to use a logarithmic scale。

 if you have a huge number of a logithmic scale， you can use。Algorithmic also。

 So even you can use to the base general。Yes， this way you can try your text。可呀。

So this is one good advantage of this export graphic option in。Simp trace metrics。

 And you can you can save this file as a image file。Okay， so now here。

 I think somewhere we are seeing here。Or you can take the screenshot up in or else what you can do is here we have an option of output format it。

P And D JPEC。 So I can use a JPg also。Can visit your back。I can store this。

There should be some anyway。 Just check it。So this is how the way I can able to probe my。

So auto generate output。Can be automatically。Here you can see。JPEC。

 what is the height water unit or pixel cells。Or you can simply take a screenshot of it and then you can。

 and even it can generate the new plot script also so that the script can be stored here whenever you need。

 you can simply plot the characteristics by running the script。For these to execute， here have to。

I install DNA need lot。

![](img/3b914f0a109928b372c3be40505338ef_19.png)

So， this is on。Trace matrix， trace analyzer for network matter。



![](img/3b914f0a109928b372c3be40505338ef_21.png)

Okay， so now this is done。One more thing is pending。 So to see the network simulation。Animation。

 so I use this software called nettanium。 again you can refer my first do CC file given a greater explanation on this nettanium。



![](img/3b914f0a109928b372c3be40505338ef_23.png)

And we will write the code here now。N Sonymon5。Slash N 3。2 in slash。



![](img/3b914f0a109928b372c3be40505338ef_25.png)

That。对。So I'll go to the end of this。 So anything， everything any code we had read before this run5。

Get no net courts。So now the Italian， I need include a library here。TheHead of frame。 So we'll be on。

Can actually include。Industtry slash thetanium。IPhone module， dot H 5。So， after that。

You have to come back here。Animation interface。And name， so I use a file name called us。Third not Xl。

 So because the file name is third of Xl， I use the file name Xl。Then。Anim door set。あして。

Pos because L Con position。 So first thing is， I use。C SM A notess。Dot。ゲたゼロかま。10。0。たma点10。

So there are totally four nodes in this CsM。 let me not use any nor for P2 P。

 I will use the same number here。 So get 0。Get one。2，1，3。I use 3。

 so I use 10 will become common let me use。 I use 30。ゆり？Okay， so now again， I use one more time here。

I use Wifi station also I will go and copy the variable name。 So this。Haii face station notes。

It will be having a again we have 3 not0，1，2，3， okay。So what I do is copy this。So they can be given。

 Okay，0，1 and 2。So， I use 30。305。And 70。 So this， you want to be located away from each other。

That's why。 And the one more note is pending。Wfiエピ。我がフ也ピの。If we know or every know。

 Let me check the variable name。Previous here， but。You won't miss it。 Yeah， it is A P note。

 not A P notes。So if we order get 0。My use of value 10 from 100。So that the notice I will permitted。

So constant position on the wireless wired nodes will be a warning because wired nodes always have located in constant over again。

 you heard a do constant position， but just to show you how network animation works。



![](img/3b914f0a109928b372c3be40505338ef_27.png)

Now， I will run this example right。It just going in the5，3。2 million。ま than。A a1 runs， scratch third。

Like Den。

![](img/3b914f0a109928b372c3be40505338ef_29.png)

A made some errors。곤란や라。Yeah。Inncluding some extra character here。Yes。

 so now can see that's a warning。Does no2 does not have mobility model。 Yes。

 because they don't need a mobility model， okay。Okay。

 fine so now I need to run this example because it it might have created a tri colors。

Something that Xm。 Yeah， you can see third that xm。 Now， this has to be run。

So first I need to go to the previous folderer here I have a file called less Natan。For没。

So what I can do is。Here is an antenna turning folder。 So to run this file dot slash。在带。Net an。

 So the capital N and small capital A。Con thetan name， open it。To that what。 now we can see。Okay。

 so Ill make it slow， the simulation is slow。You can see there are three nodes here。

 There are one node。 There are two node here。 and there is one node here， one node there。 Now。

 once you start the simulation。A guarantee。There is a wireless node， initially。10 come 10。

 So this is a grid size。 And here is all the four nodes in line 1，2，3，4，5，6，7。

 and node number0 is here。 We guess 100 come 10 di。So by seeing the simulation or animation。

 you might not doesn what's happening。 So these three nodes。They can move also， you can see that。

 let me check it if they move。See if we have a slight movement here 5，6，7 north， slight moment。

Will I make it as slow， so they'll be slowly。Let me。So can see see the moving。

The simulation says they are moving。But other no such stationally。

 because they don't have constant position and models。Okay， so after it is done。

 we can go to the statistics。 you can see the statistics of each and every node。

So only if for one models， I can refer。那 al not。And in the packets。

As this how the packet exchange happen， and it generates a table also。

 at what time which know from I D to 0 to 7， no number 0 to 7， what is a。Tranvisition time。

 what time in transmit is 0 to 6。 What happens。And we have another parameter， only three parameters。

So this way， I can enable to。Find out things。And even again。See the graph also。 And this。

 I can able to take it out。And plot some characteristics。So how it happened， which by node sense。

나2分 밖에었。And that this is how these animators on here。

 we have battery models so we can check so many things in this network animation。In Natanium。

 maybe I'll show you a separate video for Natanium。To deliver the properties of al。Nops。

So we have seen two modules， via shark。Trace metrics and what network animation called us net And。

 we have seen three things in this example。

![](img/3b914f0a109928b372c3be40505338ef_31.png)

So。We have done it。 So if you software to my channel。都没加的。And share it with difference。Deference。

 so first start C and second C， also， please。Listen to it。说的。You can understand more。Because I。

 I cannot explain。All concepts in all the videos。 So he explained。More in second。

So thanks for watching my video。Angetic claim。Also， you， there are some source codes available。

 This source code will be uploading in。My website called us H GTPS。ASNM dot com。So in this place。

 you can go and download my。 So thanks for watching。Thank you。



![](img/3b914f0a109928b372c3be40505338ef_33.png)