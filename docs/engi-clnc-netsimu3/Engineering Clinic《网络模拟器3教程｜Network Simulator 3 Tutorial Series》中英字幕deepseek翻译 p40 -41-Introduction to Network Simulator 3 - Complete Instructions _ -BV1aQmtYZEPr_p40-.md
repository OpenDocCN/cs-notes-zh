# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p40 -41-Introduction to Network Simulator 3 - Complete Instructions _ -BV1aQmtYZEPr_p40-

The lecture here。On introduction to NS3 architecture。

So first directly what I do is NS 2 already many of you have might have heard about NSS2 so Ns2 is there from 1990 up to 2011 the time frame is only for just 12 years but 2015 onwards we have a tool called us NSs3 so before the it was under development for now it is almost mature。

And now industry focus mainly on C++ and Python programming， So if you are comfortable in C++。

 we can go into C++ if you are comfortable in Python， we can go into Python programming。So。

 it is a discrete event simulator like most of the network simulations there are discrete events so it is everything is based on a finite number of events so one event packet sending is one event packet receiving is only event plotting the results is only event so everything is based on the discrete set of events。

Actually NS2 and NS3 both were from the same university so same university have done it so whatever NS2 models where they just imported into NS3 or they reused the model or programming into NS3 so whatever you do the performance in NS2 can be equally be done in NS3 as well so so it is NSS3 is a new simulator。

 but some of the models were imported from N2 to NS3。

So now I have just given operating system Buuntu virtual machine image I have just given you we can make use of that because most of the times installing this software will have a tough time so to avoid that I have a greater VM image so that Vm image can be used by all of you so the VM image since we don't want received only to the paid participants whoever register for our workshop we have given the VM image so if they wanted to use they can also use so we have already shared it I'll just show you how that Vm image can be then I mean after the explanation gets over。

Okay so we can use in Windows also and we can use in Linux as well。

 so in Windows there is a separate processor procedure there I will be showing you that also because in my machine I have in Windows I have a Linux everywhere I have this NS3 installed I'll tell you how to do that。

So again shortly by tomorrow we will give a manual also so manual means exercise number one Ex number two。

 three，4 like that we just we are in the preparation of this manual so we thought of giving at the end of the five days only but anyway if I give tomorrow then at least we can have a flavor of working out before the session gets over so that's why we will be giving a manual also tomorrow whatever we see we document it then then give it to you。

So N3。Now it worked with the Windows several levels with Linux perfectly in Windows we have one model called us Windows subs systemtem for Linux generally we call it as W v。

So。I list。So in Linux be used in Linux。Generally， Linuxux。And in Windows。We use one model called Wsl。

 so Wsl means Windows。Subsystem file Linux so this also we can able to use Ns3 head so these are the two things so we have already sent one Vm image so the Vm image is already been shared anyway just share that in the text window also if we want it can download both this I mean this operating system so this is where NSS3 have a support on this。

And increase a phone。So， day1，5。So NS2 versus NS3 so NS2 uses OtclL and C plus plus whereas NSS3 uses only c plus plus So only if you know how to read a code。

 how to understand a code it's fine because now it is a chat GT era where the codes can be generated through artificial intelligence and we can able to directly use those codes but I have tried for NS3 using chat GT and Google Gei but many of the times the codes were not working are not compiled properly。

 maybe I'll show you a demo also So even for if the code is not working to make it work。

 you should have some basic knowledge on how NSS3 is operating So it is a fundamental thing that everyone has to know what is whenever you see the code what is this code you need to understand that So that kind of programming knowledge is there it it's a prerequisite for this understanding and we have many tools with NSS3 so we can see some of the tools here。

So these many tools are therefore for in street， so we need have wire shark。

Then we need netanium network animation we need trace metrics for normal ASI trace and we need AS key trace files that will be generated from N3 we have packet capture files we have flow monitor to handle the packet flows and we have G plot for plotting and visual show a lesson so visual laser is a bug so it is not been used because we use nettanim so visual lesson we need not use so these are some of the tools that we can able to do so in the first two hour sub I'll show you everything here so that we can at least when whenever you feel oh I can do this work so like that you have a clarity on how to use these tools I'll be showing you that。

Okay， so now this is how the way Ns2 and NSS3 were so Ns2 was just still in many of the countries Ns2 was still being used but Ns3 now they are migrating and there are so many difficulties in NS3 as well because of this difficulty many many students or research colours they can they reframe themselves in coming into Ns3 because NSs3 can able to solve many of the world's problem today and anyway we will see how we can able to do all these stuff Okay now these are the five abstractions that we see in Ns3 so you just please understand these5 what is a node。

What is an application channel networking device and topology helpers so your entire industryry was categorized into these five abstractions Okay so abstraction means it is these are the sum of set of classes that is available in industry NS3 is completely un object oriented。

So。So inner3 is an object oriented。So abstract and number one is node。Number two is channel。

Number three is application。Number four is net device。Number five is aology。Generally helper classes。

 generally we call these error helper classes。So these are the five things that you need to know about N S3 Okay so what is a node。

 what is in channel， What is an application， What is a device a topological part okay so now generally when when we see a blind model a node means a computing device generally we call a node which a computer is a node So we call the node as a computing device channel means a communication path between the nodes。

 generally we have two nodes， node one and node2 if you want establish a communication path between the two nodes that we call it as a channel So the channel can be a wired channel or wireless channel wireless channel means no physical connectivity will will be there。

 but we have some medium access control it deployed in one node and medium access control deployed in another node So both can able exchange packets via wireless medium So that is we call channel。

 there is wireless channel Wired channel means we have ethernet communication and we have。

I mean Ethernet then we have optical fiber and there are many acoustic fibers。

 so we have many kind of wire communication is possible between two different nodes so node is computing generally a computing device channel is the communication part established between the multiple nodes application means what kind of application running in node number one and what kind of application run in node number two So when maybe node one can be acting as a server and node two can be acting as a client So in that case an application a server application is running in the node one and server application client application is running in the node number two So far that I define some application So generally not only this application this is one application Another application means UDP E server are a streaming server So all these things are we call as an application or HttP application or S andmp application So that's what we call as an application So a node。

Talks to another node via a communication path which we call it as a channel and the node uses an application called as HtTP application which is running on either of these notes。

 so that's what we call application。So net device means networking device。

 So networking device is a combination of software and hardware。 So every node needs one address。

 Okay， so address means on what IT S and 4 address we end it。 So generally for net device we need。

あです。So generally we need IP v4。Or IP p6 so we need a mattress six so net device is nothing but a networking device that we can able to share the address not only that we need the sub mask also。

😊，Subent mask。 So how do we do the subend mask 25 do 255。0。0。

 So something we do the in sub mask for all these things to be done， we need the net device。

 So this is where we have this net device okay so finally topology helper is nothing。

 but all other classes comes topology helper classes。

 So if you want to use over Dv if you want DSDV if you want to use DSR。

 if you want to use store if you want to use。Any other protocol I mean RP the routing information protocol。

 So for all these protocols we call something called say helper classes So everything comes under topology So these are the five different abstractions available in NSS3 So node channel application database and topology help whenever you see the source code having these names you can immediately understand that okay this is telling about node this is telling about channel this is about application like then you can able to fix it up So that's what here we have the abstraction So this slide it's very important for you to understand what are the different abstractions in NSS3 Okay so now we have just explained it here so what is remember a node。

What is my by application we can see some application is UDP Eco client and we have UDP E server。

 so we have an E server application and we have an E client application so this also we can able to use in our program I will be showing our program and how we can able to use that。

Now channel is， you can see the channel what I used here is CSMA channel。

Point to point channel and Wifi channel。 So we have three channels here。 we have used here。

 For example， These are the three classes that is used in N3 on CSsM channel。 I mean。

 some of the examples here for channel CsM means carrier sense multiple access So that means what channel will be there where multiple nodes can able to compute for resource destination node in that case theres a carrier sense multiple access So that means multiple access will be possible and if one node1 to send packet to another node it can able to send the packet in the bus the bus will select which is there's a destination and accordingly it will be sending So during this time we have a collisions there because multiple packet hit each other we call it as collisions So this way we can use the CsM channel as one of the carrier send multiple access channel point to point channel means only between two nodes we can able to have a point to point connection So node one will be there and node will be there if you have a physical connectivity between these two we can establish a point to point connection Wifi channel means it is spread across。

Fency spectra， So if you see frequency， so in Wifi channel。For example， let me write it here。

wiifi channel。So the channel properties means we say 8 not 2。

11 so that' is what we have a byfi standard。 So now we call a P G N Y C。

Then ya x now B E Now this how the way the standard gone。

 So now we have the recent thing is y5 6 and now y5 6 e。

 So these are the standards what we think about Okay。

 so this is in what way they use the frequency of operation is 2。4 gigahHz。

Then 5 gigahHtz Now we are going towards the6 gigHtz frequency spectrum so that means so this how the way so 2。

4 gigahHtz have some good ranger。Good ranger， but 5 gig and 6gHz a less range so that means but powerful connective will be there。

 but range connect the range will be less。 suppose if I have a router in my next room if I use a5 gigHtz then my connection will be very less enough but if I sitting in the same room I have a very good powerful connection high bandwidth I can able to use but 2。

4 gigahHtz I have a low data rate but I have a good range means even after the third room I still get a good connection but。

😊，The bandwidth I can have a limitation there， so this is what these wfi these channels。

 So if I want to establish a networking like this further I need to select which Mac protocol I can use what kind of mobility model I can use support the nodes moving here and there so how do I how I can able to position my nodes so all these things comes under this wfi channel。

So we have channel parameter parameter so I'll be showing you where the channel parameters we can go through it okay what is the gain what is the transmission gain and what is the L factor what is the frequency that we set upon everything we can able to configure for each of these channels here so first thing is the node。

And second application third in his channel and fourth exitnet device you can see the net devices we have a point to point net device CSMA net device wfi net device and see wfi net device uses Wifi channel point to point channel uses point to point net device and CSMAnet device uses CSM channel so CSMnet device uses CSM channel so this is how the way it works So for each of these channel to work we need to have the networking device so it is something like a ethernet card what we have behind our desktop inside our laptop so that's what we have so nowadays laptop they don't come with the ethernet but they have come with a wfi so that means internally there is a wfi hardware is available to make your device to access as a wfi so that hardware is nothing but the net device so how do we model the hardware in simulation is the NSS3 has answer called net device So generally what we do is generally we call network adapt。

Network adaptive for Wifi。Whi is in the hardware， but if you want to use the software for that I can call the natives。

Net device。Isian software。Model per handling there。Actual hardware， so this is the net device。

 so it's an answer for Ns3。Okay， so anyway， all these things whenever I say you may be blank but after I show you the source code you can understand。

 oh， this is a purpose I am just writing the net device。

 Okay so what I do is I'll be explain the complete source code of it。

 how we can able to use then you can able to understand how really this things works so now this is the net device what we can able to use and finally we have topology helpers So topology helper means all the protocol stack then Mac address everything that deals other than all these four classes we call the topology helpers So topology helper means everything else is in N S3 so this I know I'll share the presentation also and we will go into the models now now having said these basics now theoretically if we go through it we can there are so many things there but let us go into how we can able to use our I mean a demonstration so first is demonstration。

 but please I expect。😊，That as I already sent to a mail saying that there will be no quiz or no exams at the end of 50 day。

 but we expect that those who attend this FtP， you please go through。With some exercises。

 what we give。 So we are giving some exercises and simple exercises will tell you the source code。

 and we ask you to modify something only when you do that。

 you will have a good understanding of how this N S3 works。 Okay， so now。😊。

Let's move into into the demo。So anyway， this is recorded Ill be giving the complete video also so that you can you can understand later also you can able to check it Okay now first thing is I already shared one Google drive Okay。

 so this is my Google drive I want to 22。04 I just shared it So this comes around 10 gb okay。

 so already I have just downloaded that as well。You can see here。Yeah，10 gb， so 10。3 gb。

 I have just downloaded。Just two hours go morning when I downloaded so this is my office I did this everything in my home so I just downloaded and after downloading it I just unzipped it here So where I unzipped this。

Okay， so this is where I unzipped U 2 22。04， so here I is this unzpped okay。So。

 this is the place where I just completely uned you can see the size of that is 33 gb。

So total size is 33 tb， so this way you can have 33 tb then。Okay。

So first thing is I give the steps also here step is step on this。Install。Arracle virtual box。

Referably。Else， you can try， you can install。啊。We am a Otation player。

So any one of these things you can use either install oracle virtualual box or you can use VMware Oation player okay so Oation player now the version is 178 so you can use player version number 17 soation player is free for academic use but it is only paid for professional and any other commercial applications but it can use freely but articleacle virtual box is completely free so it is open source completely free so now first I go into this oracle virtual box。

Once you do this， you have this website， Okay， articleac virtual box。 so just open this。

Here you can see that you have virtual bug sound point0 click it now it will be asking you what is a host you are so host means my host operating system where I am going to install in my case I have Windows because I am just running my Windows voice you can see I am just running my Windows voice。

And Mac OS win it is Mac and Linux is this so we I am running in Windows first， so click it here。

 you can download you can see。😊，The virtual box you can download and you can install it。

 I already done that have just done the installation。 Now what I do is。

First thing is step  one downloader step2 is。Step 2 is。Inst after it in selling。And download。

The VM image。Provided to you。Okay， so and unzip it。And zip it。So this is 10。3 gb。

And unzip will take 33。3 gb， so the unziping will take 33。3 gb okay unzeip bit。

So now I have unzipped it in D drive， okay， so again， I just give that use DR E drive。

Do not use C to C colon， I'll just tell you why okay now in my Y， you can see that this PC can see。

You can see here D drive is 80 gb free and here67 gb free and here it is 90 gb free okay because C drive is in a different hard disk and D and D in different hard disk that is why this G3 so which are have highest free space use that particular drive but prefer not to use the C drive okay by default it will show you a C drive but don't use that okay now let me open it。

对。😊，Now here is a procedure to open it step  three。So open virtual box。And do that。Installation。

It is not in， just use use a message， okay， now I am just using virtual boxs。Okay。

 so this is oracle VM virtualual box， I'm just opening it。

Okay now this will be this is how the way the screen looks like okay now first there are two options there first thing is add are you can use new new or add so anyone is there so I just go with a new。

Okay， so virtual machine。Operating system， you can see the name of the oasis I am using U2。

Undersco 5 g， underscore 6 g， I Q and name。R 5G6 I can give a name like this Port you can see this is giving in c colon by default gives in c colon but don't give c c drive。

 I just click other。And then I select that de so this PC。De wave。

I create one folder okay I did I will leave it as it is select folder so I am just doing the folder in D IO image don't do anything now and that type is  Linux O and 64 bit So let it be as it is don't give select an IO image because if you want to install from the first time。

For the new ways you can select IO else don't select anything， click next。Okay， now base memory。

 the Ram is2 gb and number of processor one CPU it is given。

 so actually I have a tool CPU machine with a 16 gb Ram Okay。

 so I am giving 202 m2 gb let it be2 gb instead of one CPU I give two CPU Yes ma'am can you please confirm with this because I feel it your past。

Can we the install it when along with you or Robert？No， no。

 ma'am just I'm just here telling you now because LC will take most so much amount of time。

 just I'm just showing you ma'am just Im confirm from the beginning。 So click new。😊。

we can install it later or we can just see what you're doing first you see this map maybe after the break so after 2 o'clock we have two hours break till 2 o'clock that time we can try it yes yeah。

😊，So U 2 5 g，6 g。And as instead of C drive， I just go there and select other， click the D drive。

So in Drive， select folder， so Drive and Linux U to 64 bit， click next。Okay。

 now the base memory is to GBb Ram and processor。2 CPUs。 Okay， now here there is a take aroundnda so。

Give 2 G B Ram。If you have total。8G B Ram。 We have total 8 G B。So8 to beat up。But1 G B。

If you have4 GBBM in your machine， in your computer。Okay。

 so it depends 2 gb or 4 gb you can give and even for 16 gb ram I can give 4 gb also no shoes here。

 but let me refrain with only with the 2 gb okay and。Proces is。Give two processor。Two processes。

 okay， in some cases， you can give one processor， two processor or one processor。Our one processor。

Okay， so this way you can allocate the resources， so this is the resource allocation Ill just come back here so 2 GBb I just given and two c I just given click next。

Okay so now it is asking for a hard disk virtual hard disk create a virtual hard disk now use an existing virtual hard disk and do not have a virtual hard disk now in this case click the second option so this is very important this screen is very important you can click the second option because I already gave you a virtual hard disk with a 10 gb or what I have given that is your virtual hard disk。

😊，So click empty， click it here， this icon you have to click it。Once you click it。

Nothing is there you click add you click add here once you add it you go to the D drive where I just unzipped it here so here only I just unzipped that over to 22。

 here for double click it。😊，The first file where u to 64 bit you are having this file now。

 so this file you selected open。After selecting it the actual size it will be showing you 33 gb already we have done it this 33 gb okay。

 click choose。So， once it is chosen you can see that use an virtual hard disk file the total size allocated is 40 gb so when now I created I created that 40 gb disk okay among the 33 gb is already used remaining8 gb3 so this is for the Uuntu virtual hard disk please remember this is very important step here in the virtual hard disk if you click new virtual hard disk here it will be empty so you will have completely everything be empty so don't do that go for a existing virtual hard disk file then click next。

After that， it will be showing you what option you have selected， what is a machine folder。

 everything it will be showing you。😊，You can have everything here and click finish。😊，Okay。

 so now my o is。Im done here， okay， now my voice is coming here powered of。

 but it says that it is powered of now double click it。I'm just clicking it here。Here you can see。

Now I go to file， I mean， the voice is opening。

![](img/5876017ddf3a5b8c8c40792f13922445_1.png)

![](img/5876017ddf3a5b8c8c40792f13922445_2.png)

Professor in Uunto what the version you are going to install the professor this Uunto So I use the Uunto 22。

04。Okay， my。 okay， now I just that also I'll just make a note of it。



![](img/5876017ddf3a5b8c8c40792f13922445_4.png)

So here。What I use to here is。部分2。22。0 this what I used。This year， 22 means 2022，4 win April。

So 2022 April month it was launched， so it is one of the long term support。

LT S okay it is a long term support LT S so always go with the LTS because other version support only for nine months。

 but long term support will be supported for five years yes so now if you have a paid model they can support up to 10 years also。

 but we version nine five years it have a support。😊，So my supported there。But for L okay。

 so I am using U to 22。04。Okay， so now see that my voice got booted up here。Now， this is out of it。

My voice is， my voice is up and running。Okay， so right click， you can see I have a terminal。

 so I have the voice here now let me show you the folder。

I have just opened the folder you can see here I install all the software。😊，So Nus all in 13。38。

 which is which is the Nus 3 with 6 g。This installed and NSs3 millimeter wave new handover。

 so this is for 5 g。At net simizer， this is one kind of a I mean visualizer a three dimensional visual laserizer for a flying net for a drone if you want to see how a drone is flying you can able to see on the net simizer。

Then we have trace matrix so we can run trace matrix here。And the contiMg is installed here。

So all these afterward installed here， I have just given how to install also I have given the installation procedure also that。

So we have everything available in this bundle of packages this is what you are also going to work on I am also going to work on for the next four or five days okay so because if you want to install this the faster three days we are to settle for installation alone so to avoid that the Vm will be helpful for you so even if you want to give it to your friends also who is working on this area you are free to give this voice it is currently free。



![](img/5876017ddf3a5b8c8c40792f13922445_6.png)

Okay， so now let me check it on small programming， whether it is working or not。So what do I do is。

I click。From the beginning， I will go okay now this is what the left hand side window here I click it。



![](img/5876017ddf3a5b8c8c40792f13922445_8.png)

Then I select terminal。

![](img/5876017ddf3a5b8c8c40792f13922445_10.png)

Terminnal youll get a terminal gets opened。Okay。So now in this terminal。

The password in case if it is asking the password is one，2，3，4，5，6。😊，Let me put that also。



![](img/5876017ddf3a5b8c8c40792f13922445_12.png)

The password。For the would oaseis。One， two， three， four five， six。And the username is。

The the to so this is the username and password is one to 34 and the but whenever the voice is booting up it never ask you a password。

 but whenever you want to install something it will last for the password that time you to use。1，2，3。

 four，5，6 this is the password okay so but username here is a the。



![](img/5876017ddf3a5b8c8c40792f13922445_14.png)

Okay， okay now here it is this is what my username， So if you see PwD， if you use the command PwD。

 you can say this is my home slash form slash for the part this is my home folder okay。And。

We have the list of files here and uss all in 13。38。

Then N millimeter wave new handover and now let me go into 3。3 gate so Cd。Inless， hyphen。

All in one soFC actually whenever you want to type something here you need not type like this ns hyphen all in1 hyphen 3。

38 like this this also one method to type it are first what you do is first few letters yes as I am typing and put a tab two times one time second type now it will be telling you two folders with the same name starting with ns now this has a hyphen here or can see these a hyphen so click hyphen and put a tab one more time it auto of completes so instead of typing the full sentences you can able to use the tabs okay so。



![](img/5876017ddf3a5b8c8c40792f13922445_16.png)

Useす。Tabs。T for auto completion。Intermininate。The next10 minutes。Okay。



![](img/5876017ddf3a5b8c8c40792f13922445_18.png)

系。So now this is how the way it does then again when I go into Ns you can see here there is a thing or Ns 3。

38 and here we have something called network animation netanim So these are the two folders that we have so when is netanim。

Another is Ns3。38 so these are the two folders within all in one so all in one means everything in one one package NS is giving inside that we have two folders main folders that we need is Ns 3。

38 another is network animation 3。108 okay now clear is to clear the screen now what I am doing Im going with a net an so type N E and put a tab see N E and put a tab it auto completes okay。



![](img/5876017ddf3a5b8c8c40792f13922445_20.png)

Now， this is nettanium。You can see here the green color in this the green color file indicates it is an executable file or a call as a binary file okay so this is a nettanium which is already installed so if you want to run this nettanium you have to use a command colors dot slash。

😊，Okay， let me run the right that。To run any file。With。Green color in Linux is to use a。Dotless。

So the command is dot slash net can， so this is the command here。

So dot slash means current directory。Dot slash means it is current director so in the current director I have one file call netanium use that and then put enter okay so this is a simple command here so now we can see here clear dot slash net anium so once I do that。



![](img/5876017ddf3a5b8c8c40792f13922445_22.png)

![](img/5876017ddf3a5b8c8c40792f13922445_23.png)

The network animation window gets open。Yes， you can see this is the network animation window then a file you can open the file and then what is the animation file we can able to do anyway we will do the all these things later first I am showing you what software is already there inside this。



![](img/5876017ddf3a5b8c8c40792f13922445_25.png)

N S3 okay， so this is one window on nettan so we have to go inside this folder okay now I use Pwd。

To make it and to make you to understand what I do is。



![](img/5876017ddf3a5b8c8c40792f13922445_27.png)

To open nettanium。Here are the is here are the steps。Okay， so what do you do is。Open a new terminal。

Open a new terminal。😊，あ、シリ。En a Sa， all in one。Iyhen 3。38 slash。



![](img/5876017ddf3a5b8c8c40792f13922445_29.png)

The folder name is netanium hyphen 3。109。

![](img/5876017ddf3a5b8c8c40792f13922445_31.png)

Letan。Iyhen 3。109 slash。Then this command。Okay。So yeah， window gets open。Okay。

 so this is one thing on nettanium we will use on nettanium Okay second thing is after that if you want to come out of one folder C space dot dot。

 if you do that one folder up we just come so the same way in Windows also we have this one folder will come up okay now again I put a less。



![](img/5876017ddf3a5b8c8c40792f13922445_33.png)

We have N S 3。3 now this is one of the important folder we ever have in Ns 3， so Cd Ns hyp。3。38。

So when I put Ls， LS is listing the files， all the files and folders， I am just listing it here。😊。

You can see here I have all the files here， so we have build we have bindings， we have contribution。

 so this is one important thing we will see we have contribute and we have examples。

We have scratch where we write all the files we store here and then we'll run it。

 and source source means already the existing libraries precompiled libraries are available in the source directory。

 All the source codes relevant to your research will be available here。

 SRC and this green color and this green color means they are exhibitable file so we can execute directly using dot slash this NS S3 and this test Py forget about the test Py。

 this is very important for us。 this NS S3。 Okay， we'll see that now before that we go into the source。

 What are the different source directors available and how we understand it。 So S C C D space Src。😊。

Now， once you go here， now this is where。Your research comes here。 Okay， now antenna E O D now。

 let's say。And just play it。You can see here antenna means if you want to do something relevant to antennas so the antenna level source codes will be available here then Yvo Dv protocol source codes are available here applications source code bridging bridge repeats routers relevant courses will be here bright is a university specific source code buildings if you want to design buildings for3 dimension animation you can use this buildings here click is a software router and CSMA CSM layer core means it is on networking core like the core libraries like what are the different things on networking switching routing than packets then applications everything is available here in the core the networking core then DSDV then DSR then energy then this nets you can see the net here then flow monitor this also we are going to see then internet relevant source codes then internet applications then load。

Data red W pen W pen is wireless personal area networks if you want to work on a Zig B and W rare pen you can be able to use LTG long term evaluation reason 4G 4G networking LT is there then mobility is there mesh networking is there MP is multi processingces interface is there the net an is there the networking related there。

Then while lesser I don't know what is this so wireless lesser protocol open flow for software defined networking then point to point then propagation if you want to use propagation layers like what are the different propagation loss model propagation delay model those people they can able to use6low pan。

 it is for internet of things6low pan spectrum if you want to deal with various spectrums in communication you can use a spectrum here then statistics this is an bridging some kind of bridging then topology here traffic control。

Then virtual networking device visual a laser。wave isvehicular environment， wfi and Y max。

 So these are the different source codes available for N S3。 Okay。

 so this is where our NS S3 source codes have been written。

 So we can able to use the source code or we can able to modify the source code whichever way we like we can able to do Okay。

 now let we come out of the source。

![](img/5876017ddf3a5b8c8c40792f13922445_35.png)

![](img/5876017ddf3a5b8c8c40792f13922445_36.png)

We have something else contribute C and TR， so contra means contribution external contribution C contribute。

And I am in contract now now we can see here I have net simulator is one contribution Another is a TH E THS says nothing with a terraim for66 generation we use something called aterraha simulator generally in short we call theterraim this is where I compiled it I compile the terasim is a third party software I compiled it for NS3。

38 and I in just make it worth okay this is the TH E compiler okay now when I want to see what is the TH E contents。

😊，You can see everything contains a document。Some examples。

 some helper classes are otherwise ways we call topology helpers。

 some models results and some tests so these are the different folders available on a each and every application now the ter hat also it contains like this okay so if you see a model classes C model I just go into Cd model。

Here you can see。You can see what are the different source codes here。

Soterrahatz channel terrahatz channel dot H then Terlantonna then terrahatz energy model。

 then medium access control， the Mac headers macro access points macro mode and nano mode there are two kinds of modes anyway we are going to see all the 6 when we do the third year or 43 so then nano models there than net device there than physical layer macro and physical layer for nano so macro means it is working under a longer distance range nano means very shorter distance ranger for 66 gigahHtz spectrum 60 spectrum further we are going to use it then spectrum proagation less signal parameters than spectrum waveform and UDP client UDP server UDP trace client and traffic generator so all these things are available for 60 networking everything is available in the models here so this isn't the model okay now I come back to I go to helper classes so we can see something helper classes here CDd helper。

Now in the helper classes you can see these many things are directional laantana helper。

 energy model helper， then simple terraha helper， Mac macro access point helper macro client helper。

😊，Then nanoheler， then macro helper physical layer。

 nanoheler physical layer UDB clean server helper and traffic generator helper So all the helper helper classes will be available in the helper folders so not only here terrahas in all the source code it will be available here this is helper next thing is we do the research first time when we start the research our job is to go to the examples make it run okay how these examples are working what is it all about So that's where we go for examples Cd examples Now once we go for the examples they are two examples one for nano or another for macrocent so that means in the nano mode in the a networking for 6G how an examples is there in macro mode central controller I mean instead of the distributor controller interraha how it works So these are the two examples that we can start with so if you are planning to start your research in six generation this is the first2 files you have to start with macro mode and nano。



![](img/5876017ddf3a5b8c8c40792f13922445_38.png)

![](img/5876017ddf3a5b8c8c40792f13922445_39.png)

After after that modify the source code so that you can understand your concept well and good Okay so this is on the model that the contribution model now this is the contribution is third party have make it compiled for N 3。

38 but。What comes with the N3 is this folder。Okay， so this folder I just show that this is the place it is very important slash home slash pre commanda slash n S all in 13。

38 Ns 3。38。 Now inside this I have all my things running here。 So now I go into source called Cd。SRC。

 so once I go here I have these applications now one example is I will go into Yvo Dv protocol okay C d A Dv C D Evo Dv。

You can see again， we have doc examples， helper model and test。

 so these are the classes now go into the model mode。In the model here we have。Evo Dv data packets。

 Yvo IDc Yv packet dotcc routing protocol main main routing protocol source code will be here routing table dotcc routing  Q docc and neighbor allocation and thats all header files and the dotcc files so this is how the way the source code have been written here this is on the model if you want to go to the helper classes C helper。

We can see helper doccheler dot just only two files to help it so everything comes inside the source code we can able to use the source code it is for reusing it is a pre compileiled libraries so all source codes we have precompiled so pre compileiled means they have already readily it compiled you are just going to use the source codes inside your c plus plus applications This is what。

This Ns3 do okay， so in for this， all these source codes are available in this folder。Okay。

 so this is the folder where you have all the source called C Src。Okay。

 so whichever way you like you can able to use it Now one example here is let me go into the anma so there is some folders anma Cd anma。

So， if many of you are fascinating about this antenna， so we have no helper classes for An。

 but we have model okay， so CDd model。If you go now we can see that the antenna are what are the different antenna model supporter general antenna model cosine antenna isotropic antenna parabolic antenna phase array antenna3 g antenna model and uniform planar array model so these many antenna models are already supported by N3 okay so cosine isotropic parabolic phase array3 g antenna model and uniform planar array antenna model so that means this are already precompiled and further that we have angles also anglescc and we have an modelcc now one example parabolic antenna model let me open it so I need to open with a tool call us G edit。

It is something like a texture reader， we have a tool call G。Varabolic， enter model dotcc。

When they use it。

![](img/5876017ddf3a5b8c8c40792f13922445_41.png)

Okay， so this is my an word， okay。Now we can see in the antenna model parabolic an model。

 this is my type I here for antenna model and what are the different attributes beam with。Okay。

 by default the beam width is 60， so the 3 decibel beam with degrees in 60 degrees。

And another orientation is then another attribute。 So one thing a beam bit。

Orientation and maxim matination maxim matination is just 20。0 and orientation is by default it is 0。

 So if you want to change you can change the orientation in the source code where you write So there are only three parameters of parabolic antenna beam with orientation and maxim matination supposeupp I want to do your research on parabolic antenna I want to add one extra attribute which is not there in N S3 then you can what you do is you can use another model here just what you do is just control C。

Control B。Okay， so like this you can add on activation of activation I can add something else。

 so let's say one model is angles。Angle， the maximum angle。Of the antenna。Rotation。

So let me use 3630 degree。I can use like this so maybe I am just doing this and here the variable name I need to change it as a angle。

So this way I can able to add one extra attribute for my parabolic antenna model so this is how the way I can able to do my modification of my existing source code okay now this is for advanced users those who are planning for it but in these five days I cannot handle this because everyone research idea will be different here so but this is the method I can able to do my modification first thing is I run with existing examples after I analyze it try try to change parameters here and there and try to see how my network works how my antenna works everything you do after that include something new。

And I do your research。 So this is we called as a research and we will just delete that。



![](img/5876017ddf3a5b8c8c40792f13922445_43.png)

Okay， so this is one parabolic antenna model what we are planning for okay now one examples we have to see the examples now so examples you can go oh actual an there is no examples okay because antenna is only a aiding pattern only for the networking there are examples not for separate antenna antenna because every network has some kind of antennas okay okay now this is antennas now let's say I going with the proagation model so let's say I am going with proagation Cd proagation。

Here you can see I have examples， I have model， I have test and I have Doc now let me go into model CD model。

I can see that what are the different proagation model here。

 So we have a proagation last model there and propagation delay model also there so we can see。

Const that even proagation last model。ITU R 1411 last proag last model。

Then Jake's propagation last model。Then y loss over rooftop proagation last model。

 then couldn 2300 megahertz proagation last model， then Okuura Hata proagation last model probabilitybil v2 v channel condition model。

Then proagation delay model， propation environment， proation loss model here。

 3 g propagation loss 3 g B2v。ProbationSo these mini probagation loss models are available in N S3。

Okay， so in case if you are doing some research in proagation last model or a delay model。

 you can you need to work on this particular folder。Okay。

 so further that I want to check an example now you come back to the previous folder and we have something or examples here now go to the examples。

Okay， this is an example， so there are two examples one is J propagation and main propagation loss dotcc。

So this is main problem now let me open that main propagation last dotcc so when I open it。



![](img/5876017ddf3a5b8c8c40792f13922445_45.png)

Here you can see。It comes like this。So here it is first thing is the propagation last model。

So x label， y label， so x axis is O axis。And then。First thing is constant position mobility model。

 we create something。Then first thing is， okay， this is for GNU plot。Yeah， no first。Yeah。

 now here it comes。So here we have。Still， yeah。See。

 freeze propagation loss model is one thing we collect it。And log distance propagation loss model。

Then random propagation loss model。Then JX's propagation last model。And here again， Jake's here。Then。

3 log distance propagation last model。Then Nakami Proagation last model。Then okay。

 this when the last propagation model， they just plot it in G plot。

 So this is the source code which is given。 maybe I'll just execute it after some time I will execute this propagation last model code。

 then you can understand how my propagation last model is working。 Okay。

 so this way I can able to understand the source code of it。

 So whenever I see the source code I should understand what is the source code all about。

 So this is where my understanding liesce Okay， so now this is a propagation。

 Now these are the source codes that comes with N3 Okay， now let me go into one example called us。



![](img/5876017ddf3a5b8c8c40792f13922445_47.png)

We have one example folder， so in the SRC， see we have an examples in NS3。38。

 we have an example folder CD examples。The first examples we can solve is here only。

You can see channel models， energy。Errr model IP version 6 naming routing socket traffic control tutorial wireless and UDP clients。

 so these are the different things available in。This， so first let me go into routing， Okay。

 so C D routing。Okay， now the routing， I have one example， there are so many examples there。

Here I have something called mannet routing Compcc， I have one source code called。

Mannet routing comprcc okay， so this was called I'll be doing it here now PwD， I use which folder。



![](img/5876017ddf3a5b8c8c40792f13922445_49.png)

Now I'll do everything here。系。Okay， no。We are going to see。You are going to see one example。

Regardlessless。Mnet。A routing iPhone Compcc file。Which is located in the following directory。

In the following directory， So this is the following directory where it is located okay。

Move this file to。EnS。Ihen 3。38 slash n i 3。38 slash scratch。Scrach folder。But execution。Okay。

 so move this file or copy this file。So I can say copy this file。Copy this file。

To NSs all in one ns3。38 slash ns3。3 scratch folder so all the files if you want to run it they have to come to the scratch folder Scch folder has extra permissions and extra modules。

 extra linkages to run the NSs3 dotcc files or dot Python files it has to move to the scratch folder okay。

So all dot CC files。But execution。Have to be。冇都度。Grat for。Okay。

 so this is where we are going to move everything to the scratch folder Okay， so now let be5b day1。

Okay， so now this is where I am going to move。 So I can either use G U Y to move or through command I can do。

 So for your understanding， I will go in the。G A mode。 So now I have the file。H S all 13。38。Enus 3。

38。😊，诶。Examples， the folder examples。Routing。Routing。And we have on5 colors， magnetnet。

A routing compare。 So here this is the file。 right click， copy。And see I'm just copying it here。

 copy。Reick click copy and go to Ns 3。38 and scratcht folder。Basit kid。Best。

So now this magnet routing comparedcc I just pasted out here now this is what I am going to see for the next one hour okay actually this is one project this is one project and most of the students across the world they do for comparing four protocols okay so what are the four protocols。

Okay so。This panel loading apart。is that？Comparison project。For comparing。4 protocols。

Wireless protocols， namely。Evo DV DSDV DSR and Voser so these are the four things they are going to compare so in many in the world there are many peoples they use this project YvoDv DSDv DSR and Voser now what I'm going to do is in the next one hour I'll be completing this project okay so assuming that I know NS3 I know how to read a code then I want to do this project just in one hour I can able to complete this project okay this is what I' am going to explain you so I already have a video also on this Ill share the video link also even this video link also I'll be sharing it for the end of the day so that today evening if you have a time you can go through this okay。

So this way I am just going it going into it now and now I am just opening this file。

Opening this file now。What explanation？

![](img/5876017ddf3a5b8c8c40792f13922445_51.png)

Okay。So， now here。Now I am in this folder N S 3。38。G it。Scratch。

Mannet routing comp CC now this is the file I am just opening。



![](img/5876017ddf3a5b8c8c40792f13922445_53.png)

Now open to him。Now this is what the file what I have。Okay。

 so you can see the total number of lines in this file is almost around 428 lines。

The total number of lines in this file。Okay， anyway I'll just explain you everything is how it works。

Before that you can see in the top， they have given some explanations here about this this example you can see here。

This example program allows one to run Ns3 DSsTv， Yvo Dv or wirelessr under a typical random waypoint mobility model。

 so we are using a random waypoint mobility model and for these three protocols DSsTv by default the simulation runs for 200 simulator seconds of which。

The first 50 are used to our startup time。The number of nodes is 50 nodes move according to a random way point mobility model with a speed of 20 meters per second。

And no pass time within a 3002500 meter region。The wfi is ac mode with the 2 MBbs rate。

Using a not by 0 and B under fri loss model， fri propagation loss model。

 the transmit power is set as disceable。啊。liam。Okay， so 1。5 dpm。

Deciable milliseconds it is possible to change the mobility and density of the network by directly modifying the speed and number of nodes you can change the speed and number of nodes it is also possible to change the characteristics of the network by changing the transmit power。

As the power increases the impact of mobility decreases and the effective density increases。

 so you can able to alter the transmit power also the transmit power is 1 by 5 dbM you can change it to 10 dbm also and just see how the performance varies。

By default， wirelessr is used。By specifying a value of2 for the protocol will cause AODv。

 specifying a value of 3 will cause DSDV okay so we can use YLSr ADv and DSDv for all our work。

By default， there are 10 source sync data pairs sending UDP data at an application rate of 2 MB per second that is two points are it2 kilobs per second each。

This is typically done at the rateta4 64 by packet that means four number of 64 byte packets per second。

Application data is started at random time between 50 to 3 seconds and continues to the end of simulation so total number of simulation is 200 seconds can see。

200 seconds among that first 50 is startup time。And after 51。

 it continues to the end of the simulation。So the program outputs a few items packet receptions are notified to SDD out。

And this is what okay now this is what the explanation of the source code。

 but anyway I will just go and then tell you the source code of how this is being written。ok。So。

First thing is we have some header files， which is included here。The headerflr A DV module。

 applications module4 module， DSTb， DSR internet module， mobility module network module。

 wirelessr module and Yns Wifi helper， so we have a wfi also so that's why we have a Wifi helper。

And F stream for file stream， ivo stream for input output stream， Okay。

 because we want to write something to the file output and we want to read from the streams also that's why we use the F stream1 ivo stream。

 So these are all C plus plus objects。 But please understand again， I am just selling。

you need to understand this， you don't need any source code to be。

Return over there Okay so you do not write a source code right from the beginning Al source codes are there only thing is you need to understand what is the code is all about so once you understand it then you can modify simple things you can modify even if you want to modify upgrade something you can able to do that once you start doing the codings。

ok。So now I have two thing namespace NS S3 and DSR so DSR have a special meaning thats why there is a they we use a namespace so namespace means something like this for example。

 using anyway I just write down this here。呃。Using namespace。If I use V8， channel， okay。

 if I use like this。Then when whenever I say VD Che dot。FDP dot。Wireless dot。

 so let me take some name here。Someone is， lets say first thing is start receive bowl， okay that。

小个 bo。系。Okay， suppose if it is like this every time whenever I want to use。

 I will be using like this okay hium space instead what I do is directly I can able to use。😊。

If a namespace is there， I need not tell every time we H and。Just only this thing， okay。

 FTBR wireless receiverci balloon means this FTBR wireless receiver balloon belongs to VHT and。😊。

Okay， so this how the way I can able refer every time so this is the purpose of having a name space okay so again one more example is so I am predumar so if I use Vh and if I dont use this。

😊，So let's say if I don't use this， then we and dot per smart。B and with three。

Like that we had right so if I use name space here I am simply use to give pointss。

Pic more belongs to be HM wait will belongs to be a D so this is the this is the why we write the name space here Okay so NS3 means all the classes which you use in the source code will have a tag of NS3 every time we need not write NS3 so to avoid that we use it。

😊，We have to use like this NSS3。Colon double colon。Let's say， yas。Wifi helper。

like this we would write every time if NS3 if names is declared simply write beyond 50 per Py。😊。

Equal to new Y Wiifi helper。Like this， if NSs3 is not that。

 then what you have to do is we have to use NSs3 Poland。And NSS3。

Tuble call this is how the way we have to write the source code So to avoid that we use the namespace Okay。

 so now the purpose of namespace， you might be knowing why we write the name space here。

 So the name space here is in 3 and DSr Okay there are two name space okay。

Now log component means when I want to do the logging log means when I want to when it set the log files。

 then I need to know we what is the name of the log file it is man routing compare so I am just going for manage this mobile logdc networks routing comparison that is what I am just doing。

Okay， now class routing experiment first thing is I have a class， so this is a C plus plus class。😊。

And public roing experiment， this is called the concept。

One sector see one source code I will just explain you completely and in 60 also I will explain you and then flag networks also I will explain the source code completely so that you will understand okay this is the source code analysis and after that we can go inside for simulation okay。

Our rotationtic asron is a conceptor， so conceptor on the class name will be having the same name as we have studied in object orientation。

 the conceptor on the class will be holding the same name。😊，Okay， least。

Now wide run so we have a run function that uses number of things trans power and CSV file name。

 CSV file name for sending the data to my CSV files okay。

So I am having command setup in argument count and character argument vector。

 so this again argument count and vector is very important in general in C programming。

It is very important maybe just show you one small coding as include。Its 3D。啊一 lady。Age。Then。

 hash include。Etra at Hch。Then integer mean。Int are given count director Stra here GV。

So rather I am just editing a faster program， so I will just name this file as file do C。

 I'm just name it as file C。And what I do here is indiger y equal to。In re equal2。嗯。You to I。offff。

Air G up。Yeah on GF。Wen。Int B equal to a to I。爷や。GB F2。ok。Pinte C equal to a plus B。Print of。

C is percent as D。手干嘛？See， okay， I'm just using this。So。

 this is my body so what I did here is argument count and argument vector see that I am not sending any value for EabB so but I am going to read the value from argument count of one I want to send it。

1 value arguing of2 I want to send another value the whatever value I' am sending is character array means it is string but I want to convert the string into intesger further I use a function well a to I A means string I means intesger so I want to convert in the string into intesger that is allocated to a and that is allocated to B2 variables now C equal to a plus B whatever A and B holds I am just sending to C andm printing the value of C Now this is my program okay now once you understand this concept well then Ns3 R n2 any discrete programming you can easily understand。



![](img/5876017ddf3a5b8c8c40792f13922445_55.png)

So now I'll just come back here。Open a new terminal。You can see I have a file Ry。

 this is a file Drc compile it Gcc。Piledzi。Okay， now errors。

 you can see one file regardless Y output got created， so this is output file which work got created。

Now， dot slash get out as he told you already any file， if you want to run from the current folder。

 you have to use a dot slash get out6 comma8。I am just using two numbers6ide or can say C is 14。Mc。😊。

6 plus 8 is 14 now when I want to say 6 plus 10。C is 16， now，6，9，9。

Now this is 17 double line 8 so what I am doing here is I am using a argument count and argument vector instead of changing this value every time I just send the value through command line arguments so this we called as the。



![](img/5876017ddf3a5b8c8c40792f13922445_57.png)

Command the line arguments。Okay I am just sending the value else what you do is every time you change the value and then recomple recomple the program so you need to recomple every time the program the values have being changed but here no year of recompilation just change the value here now if you give empty value it will share a segment fault but you need to give like this now 0。

1 comma。2 if you say that it will give 0 because it is only integer I convert everything to integer not into float so it know only about the numbers so let me use 100。

96 200。7。

![](img/5876017ddf3a5b8c8c40792f13922445_59.png)

The value is 300， 100 plus 200 will be 300。Now， this is we call as a command line as。

 okay so this program。

![](img/5876017ddf3a5b8c8c40792f13922445_61.png)

This is what we have argument count and argument vector is used here。Okay。

 so this is the argument count and argument vector， so double servant it is a string character array。

Okay。Now I have a packet receiving function。Reive packet the parameters are the socket as a parameter here the address IP version 4 address is a parameter and then a number of node this is the set packet received。

😊，And check throughput now I want to complete the throughput of my packets。

 I want to have a function for checking the throughput。Then port number。

 so port number I want to use unsed in desire 32 bits then total bytes I want to calculate received the bytes and total packet received。

Then I want to use a CSV file name further I create one string file name。

Number of things I want to use the number of sync nodes then the protocol name。

 so here the protocol name I want to use is He Dv while Sar。DSTV and DSR。

 these are the protocols I want to use it here， okay。

Then double EMtX means transmission power here it is 1。5 dbM。Comine play。Bや。Then trace mobility。

 you want to say no the nodes are moving here and that。

 you want to trace the how they are moving in their case， it is a Boolean variable。

The name of the protocol that I want to。Select number  one，2， three。

 four like that now routing experiment， I am just creating one conceptor。

What number by default is port number 9。The total number of bytes to be installed initiated is0。

The you the packet is0 the name of the CSc file is manner routing output do CSv Now what I do is I will just change it to。

Ptic and RRCS。Okay， I'm just doing this V CSsv。Then trace mobility false I am not going to trace the mobility I make it as false to I mean initial number protocol number 2 is over D Okay now what I have given here is。

You see here in the text here。Wil Sr is default。2 for re D，3 for DSSTV。And one far。

 I think oil is I think lets see you will see what is that。So， but two means over D。

Okay so now the print received a packet whenever I want to receive one packet from so received one packet from address which you know who is sending the address who is the send address and from where we are receiving so this is the first one receiving the packet from who print received a packet so this code is about printing the received packet。

Next thing is every time a received a packet is received from the socket。

 it upgrades bytes totally equal to packet of get size and packet received equal to plus equal to this thing so what does it mean is。

😊，equalqu to。Backet received plus one。This is what it means。

So packet received whenever a packet is received it will be upgraded with one packet okay one packet。

 second packet， third packet like that plus one will be upgraded here。😊。

So this is what the packet received logic means。O。So now routing experiment。

So we have check throughput， so the throughput is computer like this。Okay。

 total kilobits per second is bytes total bytes received into8 that is converting bytes into bits8 divided by000 because in bits per second now it is milliseconds I am going to convert into seconds。

😊，Then that will be printed to the CSV file name so in the CSV file name that will be printed there and that will be running for the check through port so this experimentation is。

U the experiment is for checking the throughput， we are plotting the throughput values。

Next thing is set packet receive so what kind of packet I am going to use i' am going to use UDP soet factory so you know we have two kinds of packets one is UDP another is tP in the transport layer I' am going to use UDP means no acknowledgecledgment simple to implement that is what I am going to use it here。

Okay， now here we have command set up now I said that CSv file name。

Trace mobility and protocols protocol can see one means Ysr2 means0 DV3 means DSSDV4 means DSsR。

 so this number you need to keep it ready。And every time when the CSF file we can we can convert the CSF file so this name also can see trace mobility and protocol。

 so we are going to use these two CSF file name and protocol will be using it I will show you how they can be done。

Now we use a CSV file name here。And this will be sent to this simulation second receive rate。

Packet received number of thingss routing protocol name and trans power。

 all these four parameters will be center number of sinks is 10 and trans power is 1。5 tbm。

That will be sent across， okay。So the total number of wfi nodes is 50 so total number of wfi node I want to use is 50 nodes if you want you can use 100 200 like that so 50 nodes。

15 nodes are 100 nodes or 115 nodes like that if you want you can able to increase the number of nodes according to your comparison。

So total simulation time is 200 seconds。So 200 is if you think 200 is vast time。

 you can reduce that also， but let's see how the 200 thing works。

 The rate that we den is to to2048 B。 so this means。2。048。KVps kilobits per second term。

This is what it means。So， the physical layer mode， I am using a D2s radio model with Elzava and Bps。

 so this is nothing but 8 not 2。11 b。And the name of the trace file is man routing compare is the name of the trace file this also converted VT Chennai。

Okay， and node speed is 20 meters per second okay so if you want to say 10 meters per second how the parameter changes if you want 20 meters per second how it changes if you want to use 30 meters per second how it changes。

 you can vary that。Okay， so let me use to T， there is no past time in the notes。

 so let it be 0 the protocol name variable name is protocol。Okay。Now。

 we have the on of application of packet size and data rate。

 so either full packet data rate or no packet data rate， so packet size is full or 64 or 0。So。

 if 64 is there， the full packet says zero means no packets， Similarlyly data rate is rate is 2。

048 is the rate 2。048。If it is on of application means either full or no no data rate。

 that is for earn enough application， either 0 or 10 means 0，1 means 2048 Bps。

Here a packet is 0 means 0，1 means 64。Okay。Then Wifi remote station manager。

 so we just create one Wifi because all the nodes are going to use Wifi only so further we use a remote station manager like a access point。

So if we create the number of node now can see the first thing node container。

 I will recall our first class upse is node。In NS3 first upse we use note container。Okay。

 bus up second we are using。Ac nodes， the name of the variable is orthooc nodes create totally 50 nodes。

 so we are creating 50 nodes here。15 notes。Because already ywifi we have created 50 here。

 so these are 50 nodes that we are creating here。Okay， now standard is wfi standard 8。 2。

11 b we create one wfi helper helper classes okay this is a wifi helper classes so we call this a topology helper。

Tropology helper glasses。We have seen okay， then we have a physical layer and we have a channel here。

Channel， so the second channel in NS S3。 So the node we have used and we have used the channel also in NS3。

 So node in NS S3 and channel in NS S3。And propagation delay is constant speed propagation delay model that means what whenever you move in a constant speed there there will be a delay in the propagation So that's what constant speed propagation delay model and propagation loss model is fri proagation loss model so we just go for a this and create a channel path so create a communication part with this available parameters what are the parameters my standard is 802。

11 B I have a physical layer I have a w-fi channel established with the delay and loss model so using that you create a channel okay then after the physical layer then we have to have a Mac layer so medium access control So on what speed the data rate so here concentrate wfi manager that means all people in the room will have a same wfi speed that means constant wfi manager so under that we have two modes on is data mode on the risk control model。

And transmission power starting here is 1。5。Ending also sound by 5。

 so we have starting an ending sound by 5 Dbm。So there means no loss in there。Disbels， okay。

 so one by way B up。So， on both the cases， then for a type ag devices it is adog by ag means there is no access point。

 but everything is based on a all the nodes can they conduct to each other。这说 all。Wify nuts。た수제だ。

So this is what adoc mode， so if it is an access point board means you need to define one access point and some nodes that can talk to the access point so it is infrastructure mode but we are going everything in the Rdoc wfi Mac okay and establish this Rdoc wfi Mac into the net device now can see the net device here。

Net device。Unanimously。So we have a channel， we have net device， we have node net device container。

 Okay， so this is a net device read solid so we install wfi5 wfi Mac and our doc notes。

 so we install everything wfi Mac。Then this and this wfi P。

 everything you inulate on all the attack nodes attack notess is totally how many nodes we have created。

50 nodes， there is 5 node we have greater for all the 50 nodes we established the。A dog位飞妹。Okay。

 so then mobility helper now how they are moving in a mobility fashion。

 So there we have using a position allocator call us。A randomand rectangle position allocator Okay。

 so that means I have a rectangular position in the rectangangleular position the nodes will move here and there slightly they have a moment So far that I am using one rectangular position allator So X axis here is 300 y axis is。

Thousand500 headwinds。X and over yes。300 cross thousand0 by00。The area， the work area。

 so that means all the nodes are positioned in 300 plus500 that means the x axis is 30 and v axis is 500 so it is something like a rectangle so the area is something like a rectangle maybe Ill just show you that。

You can observe it， just open the browser。Okay， whenever anything is asked like this， give1， two。

 three， four，5，6。Okay， so 300 plus  thousand500。え旦个。You can see it looks like this 300 plus。

This thing is people。Yeah Ic it is something like this 300 this side and thousand500 decide so that is what 300 trust thousand500 so in this area only we are going to make the notes to move okay just to make it 300 trust thousand00 work area。

ok。Now in this position and here I have the node speed is we have totally node speed is 20 and minimum is0 max is 20 we have a varying speed that's why we use a uniform random variable because one node will move at 0。

31 node will move at 20 another node will move 10。34。57。

9 but I want to give a mean max the minimum is 0。0 and the maximum is 20 meters per seconder similarly constant node passes0 only so that's what I am using and mobility model is random waypoint mobility model so randomly they will move within the position allocator so if I use the position allocator they cannot move beyond the position allator but they can move in a random day fashion so within 300 or1 thousand500 I can move but I cannot go beyond thousand500 in o axiss beyond 300 in x axis That is what here the mobility model will do。

Now that is done now we are coming into the Evo E E helper avoid EV。WilSR， wirelessSR， DSTV。

 DSSTV and DSR Albert， DSR， we have the four protocols， A DV VSR DSTV， DSR。

Now I 4 list routing internet stack now I use a switchhi case。In C programming。

 we use each case algorithm here， so here the young protocol， if it is one means OLsr。

If it is two means over or DV。If it is three means DHDV， if it is four means。PsR。

 so we have these four protocols here。And if any other number is there。

 it is no such protocol because we are configuring only for4 protocols Yr AvoDv， DSTv and DSR。

If M protocol less than 4 then we use this and if it is equal to 4 we use this or dark nodes because DSsR dynamic source routing has a different mechanism thats way far that alone we have internet out install but for less than 4 we have a routing helper。

Because DSR uses a caching， but other three protocol they don't use caching。

 that is why for caching we use this DSR main。Since they don't use these four protocol。

 they don't use caching， so we use the center routing helper， okay。

Now we give for address help so for the what is IP address we want to allocate so set base 10。1。1。

0 to55 this。And we go for UDP circuitet factory。And on of we are using on of helper on time。

Constant random variable 1 and constant random variable 0。

 this is where UDP circuitcket factory is what we are going to use So number of sink we already have 10 So as per the number of sinks I am just sending the value start from 100 to 1 not1。

Okay， total time is 200 seconds。So this value is being printed。Or of that。And that is a simulation。

 So finally it will be printing the throughput。So simulator destroy after that。

 we destroy the simulation and then we run it。So this is a simple example of AODV protocol okay now what do I do is I have two variable here。

The variable name is Ill just make a note of it， so one is CSc file name another is protocol this is what I am going to use。

I' am going to use YSr A O Dv DSTV and DSR Now I have another 25 minutes time remaining in the 25 minutes what do I do is I will plot one variation between all these four protocols Okay so this is a manuting upper which is there in the scratch fold。



![](img/5876017ddf3a5b8c8c40792f13922445_63.png)

Okay， I'll just open the terminal。Okay， there is the terminal here。So to run any protocol。

 okay now I'll just come back here。

![](img/5876017ddf3a5b8c8c40792f13922445_65.png)

To run a dot CC file in NSs3。Here is the command then。Command is。Again。

 I'll just send from the beginning here， open a new terminal。あ、Cリ。Beenless， haven。All in one。IPhen 3。

38 slash inner' iPhone。D38。O。Now here is dot slash in S 3 space run。

You see already it is is cross scratcht slash。Now in this case， mannet。

A routing hyphen Comparator CC。Now this is a file we will be running。ok。So Cns all1 3。38， ns 3。38。

Now， the command to run is this the command to run dot slash ns3 run。

And after that scratch manner routing hyp compare dotcc now this is the file we are going to use it now。

 this is what we are going to run so before that。冇得。Dot CC file to。Watch folder。And。😊。

Open a new terminal。 Okay， so we have already moved it。



![](img/5876017ddf3a5b8c8c40792f13922445_67.png)

Now we are going for it。Okay， now I am already in this folder now。Dot slash n3。可能。Scratch。

Manner roing comparecc you can see this is the command to run。Okay。Of first will be run it。

Or you also， whenever you do this program also。It will be exactly the same way it will run。

You can see it。100 。2627 received one packet from this 10。

5117 node number 7 received one packet from this IP like that it can go up to。

Because the total simulation time is 200 seconds。😊。

But only after 100 only the packet started rec so up to 100 seconds。The network is idle。

 it is not doing anything only after 100 it works okay， so you can customize this as per you need。

Okay， so now this is what we got up to 199。763 stopped okay， now we need check Ls。

I have see the payweight Chenaar CSv。V dot Mvo V。And this is where I have two files I got generated okay。

 now I have open both these files。

![](img/5876017ddf3a5b8c8c40792f13922445_69.png)

So go to the terminal there。NS 3。38 here I have Vhhn or CSv。I think just will open here。Yeah。

 it's opening， it's getting open。So what protocol will we see it？Okay can see here。

simulationimulation second0， receive rate0 packet received0 number of 6 10 EWb ro protocol this is YDb。

Tranfi power is 1。5 okay now see that up to 196 up this we have this。

 but after 100 onwards you can see。The second parameter is receive rate and packet received。😊。

It changes of 200， it is him。Because after 100 day the simulation runs okay。

 so receive rate 10 over dv and this thing is same okay。

And see here this is how the way the CE file got generated。Okay。

So this is on E D now I want to run for DSTv and DSR also I want to run okay。

 this is only for E Okay now I further I do on a small tweaking。



![](img/5876017ddf3a5b8c8c40792f13922445_71.png)

Now let me use mobile also M B also， so this is a mobility position for each and every node。Okay。

 what time what position the not moves， so this is the mobility， so totally for under clients。Okay。

 so now what I do is。I'll just go to the sourceport here， so I have Cc file name。I have protocol。

 so one means Osr。wo means over D3 means DSSCV4 means DSsr now this is very very important and the name also CSV capital letter file have small letter and name is yen capital letter okay。



![](img/5876017ddf3a5b8c8c40792f13922445_73.png)

Now I am just running the same simulation one more time。

Four times I want to run so dot slash n S3 now this is what very important then then using double code scratch。

Manner routing compare space。Double hyphen。

![](img/5876017ddf3a5b8c8c40792f13922445_75.png)

Just come back to the source code， copy this CSV file name。



![](img/5876017ddf3a5b8c8c40792f13922445_77.png)

隔壁。And already， I have double slash here。I just paste it here。Anyway。

 just run it over here just wait。So you can easily understand if you do the copy。



![](img/5876017ddf3a5b8c8c40792f13922445_79.png)

To run the file for Y DV。DSTV。OilSR and DSSR。Yet is there sticks。Okay。Okay。Butrry what you。O。

So now what I do is this is the command dot slash ns3 run scratch manage， so CSc file name equal to。

Now I want to use Ydv， so I want to create a file name call Edv dot csv。Space。Then again。

 I go back here， protocol。Okay， hi just copy this one is Yr 2 is D， Okay， now two I want to compare。

 Okay， now double hyphen protocol。😊，Equal to2。2 is forever。 Okay， now close it。No。カピーです。

See the command name so the command line argument is without recompiling。

 I am just creating the file name as Ad or csv and protocol is2 there have been duties for Avodv right and you will just run it。

😊。

![](img/5876017ddf3a5b8c8c40792f13922445_81.png)

I click paste。Now， this is for here D。But we have to wait to 200 because I have only 2 Gb Ram I have just fixed。

So we have to wait up to 200 anyway， just plot also， lets see how do we plot it。

 that's not very beauty of this。We will plot the easy rate for all the four protocols okay。Yes。

 it is ending note。嗯， then。Okay now we can see we have one Y what are CS we can see this file Y what we are CSv okay。

 so keep it like this now one more time I need to do for what we have to do is for O lesser for while lesser the same command。



![](img/5876017ddf3a5b8c8c40792f13922445_83.png)

Here instead of Y D file， I want to create a wireless or R csv protocols now this is where we have protocols1 so this number I want to make it as1。



![](img/5876017ddf3a5b8c8c40792f13922445_85.png)

Well， okay， so now I compare this file control C。Can I come back here？Clear。Reg clicklic paste。

I see Yscc protocol is one now in when I run it。Yes， this is where oil is are。Yesス。

See that I have another file hereard CSv。😊，I have Oser docc can you see two files gone generated A and A already created first time Oser second time now again I come back here。

😊。

![](img/5876017ddf3a5b8c8c40792f13922445_87.png)

Now this three for DSTV，4 for DSR， okay。So now the same program， what I do is。Or的SDB。For DSSP。

 what I do is it is3 now， so the protocolto name is 3。And here the file name is TSTv。Similarly。

Or DSr。Protocol is 4。This is。But usually DSsR sometimes misbehaves， but lets see okay， so DSsDv。



![](img/5876017ddf3a5b8c8c40792f13922445_89.png)

And clear the screen and right click。Paste。Now， this is about DSSTV。

Nots and what is a different nodes and Sco means nodes means the number of nodes participate in the simulation Schic means number of destination nodes I want to make which are the nodes who receive the packet only。

不啲 think格。Soce to destination that is what we are telling now source to sync sync means they receiving notess。

Out of 15 nodes， only 10 nodes receive the packets Okay， thats what it means。Okay。

 so now we can see this is for。W less our one file， Y wordWv another file， DSDV also got created。



![](img/5876017ddf3a5b8c8c40792f13922445_91.png)

Now， finally we have this thing。DSSR L C。

![](img/5876017ddf3a5b8c8c40792f13922445_93.png)

Beve the screen。Okay。Okay， this is DSAT。I think DSR takes a little bit time。at the end day。

 there is some absolute thing fallback and notice DSR usually do that。😊。



![](img/5876017ddf3a5b8c8c40792f13922445_95.png)

Okay， now we can see we have Ed csv， dsr cv， DSsr csv and Osr csv。

 okay so now let me open all these files from this SRC from here O Sr。They open with the node pad。

Okay， and this opening this way。ok。So this is the file I'm just opening it here， this is for A Db。

Similarly， I can open all the other file DSDV， DSsR and OLS all the C files I am just opening。对。

So this is for DSTV。And this is for TsR。Okay， and finally， this is for oil Ler。

You can see automatically the name of the protocol is here YsR， the name is DSR。

The name is DSDV and the name is A。Okay， now second parameter is receive rate。😊。

And third parameter is packet received okay， so we have a variation in second and the third parameter so。

Second is this parameter and third is this parameter 33 like this。The number of packets received。

now I go since four values are there， I want to have a comparison between all the four。Y what DSDV。

 DSR and O asset， so if you know any comparison methods you can try how we can try is。Straet。1，99。

Okay， this thing is。Okay one method is you can able to try Excel sheet。

 you can use Excel sheet and then you do the plotting but I have NSS3 has one GNU plot has one software so I can write a small source code for handing this thing so maybe it is easy for you I'll just show you that。

Said terminal PDF。I am going to print everything in PDFdf okay。

 so I mean we have  wordv and perto protocol dot plot the name of the Phist P word0 plot。

That's what I am going to save it protocol do plot， okay。Then， set。Output， the name of the file is。

Protocal compare that PDF I can say the name of the filehi compare that PDF。Okay， so set X label。

So x axis is time time。In seconds。Set oil level O access is。Received it。Receive it。

And packet received， there are two things here。Prackets received。Okay， so。Then plot。So。

 I need to plot what are the parameters here is plot for spring isdv。 cb。This plot AW or CSv。

Which parameter is？the first line you delete it because first line is the text line， so we will have。

Okay， delete that first name。Save it and kma also you remove it because commma is also not command in control hit。

Coma will be removed and instead of comma you will have a blank space replacer。

Can see everything removed Okay， so similarly for DSSTv。运到咧。The b。Only this control edge。😔，对 place思。

Similarly， this。近到系你起身。First the line alone I delete the first line is a text line。

 which I am going to process it。So how the method is easy， okay now first parameters。

That is a X axis。Second is the V axis and third is also V axis first second and third I am going to use the first column second column and the third column in all the four files well for all the four files resemble the same thing only ring it the protocol is different and now what I do is plot A csv。

Using one column2。1 column2 means first column is x axis and second column is so it is like x column y that is what first column it will be x axis second column is axis with。

😊，Plans。With only points， title is。给我礼。什么。I use the same thing now。我 be here。One more time。

One more time， one more time。So second time is one colon three only。

 but instead of this now boil aer。Oillesser， the titan is also oilerer。Then here it is DSr。

 the title allows on DSr。So then this is DSSTV。He a last command I delete it。Okay。

 so this is faster thing it is receive rate。Okay， and now Ill use this thing here。

And same thing here， x label v label。Now I copy this again， one more time。Second graph。

 oil label is now packet received it。Okay。So we have one column 2 now one column  three because third column is a packet received。

But all other things remain same。ok。So I have two graphs L ready。

 so oil label x level is common time is seconds O label is receive rate。😊，And here is also。

 maybe if you want， you can use this also control C。About。ok。Maybe here can you set title？

Said title us。Receive rate and packet received。Title title of the graph Okay now this is my code of a G U plot so very easy set terminal Pdf I am going to use the terminal last Pdf the output of the file is compared at Pf the title is this x label what is the x axis what is the V axis and plot is the commander Thats all Okay now I will be running this example。



![](img/5876017ddf3a5b8c8c40792f13922445_97.png)

そう啊。GNU plot。啊。Protocol do flood。

![](img/5876017ddf3a5b8c8c40792f13922445_99.png)

Yes， no errors。Now I go back here。Here you can see compared that PDF。

Now I got two graphs you can see here。Avo Dv plus while SR is this and BsR is this and DSDV is this this is for receiver rate and the packet receive title。

And here it is packet received in the V axis and the x axis time in seconds only after 10 only the simulation starts otherwise it is。

 but it is only point I have given points that is why this this error now what I do is。

I'll go back ahead instead of point L lines。Lines instead of points， Ill share lines。

Okay control H instead of points。And feelings。Okay，那让你だけ。No can see。

Now this is the graph for receive rate and the packet received， so this is one column2。

And we can do this other the way up to 100， nothing happens because up to 100 there was no simulation only after 100 to 200 as simulation runs here。

 so avo Dv is a pink color。Wless are in green and Ds are in blue and DST in this。

 So when you see that the maximum is YoD only the receiver rate is very high in YD can see the maroon color so if you want to increase the graph size or if you want to increase。

Tit level away after that if you use line width line width the3。

And everywhere you can use a line with the three。A rule like this。



![](img/5876017ddf3a5b8c8c40792f13922445_101.png)

Now again， I run it。

![](img/5876017ddf3a5b8c8c40792f13922445_103.png)

You can do this line with。You can see how the graph line width increases so second thing I didn't do。

 but only with the first thing it is increasing。😊，So now in this case， the I mean。

 by seeing the graphel we can directly see that A we have a better receive rate compared to the other thing。

 so in the way axis you can see the maximum thing。The DSR clock is 24 at one point of time it was at 160 it has 1 I mean124 obviously but many times you can see 20 around 20 yeah clock2 times and around 16 17clock multiple times and。

But I the lawyer to performing is。Lest performing is。

 I think DSSDV protocol So DSDV is the lowest receiving rate。

 whereas A DV head there here similarly packet received also same thing。

But back at the you can see it is 50， the O axis is the maximum is 50 here and up to 35 to 40 that EDv and have received it。

😊，On an average， Y did well and。That is what DSDV performed less compared to the other protocols。

 so this is the way we can able to generate graphs in the receive rate。Okay， so。Actually。

 this is one project done by your PG students as performance comparison enough。

Wreless a routing protocols， but using this one file you can able to do many results you can able to do okay so now what I do is now in this case what they said is 1。

5 dbM I will go with some higher DbM。DBM I will make with the higher milliseconds Db so intra 1。

5 I make it something but I need to run for four types Okay。

 so what do I do I'll just close these files。Okay。In this close is well， so controlt F 7。5。

 I'll just check it 7。5。Or here transfusion power is 0。5。 so what do I do is。I change2。9。5。

Llls increase there to 9。5。Okay， same 15 nodes here。

 so I am not altering 150 nodes so you can alter anything as per your wish so you can do that Okay now what I do is。



![](img/5876017ddf3a5b8c8c40792f13922445_105.png)

I going to go back here。呃。

![](img/5876017ddf3a5b8c8c40792f13922445_107.png)

I just run all the file files again on more time。So first， to control C。



![](img/5876017ddf3a5b8c8c40792f13922445_109.png)

Now my YDV that CC file also will change because now this is for new， I mean DBM。Earer， it was 1。

5 now it is 9。5 I can able to compare。The old with the new also there can able to compare so this way I can able to do multiple termss。



![](img/5876017ddf3a5b8c8c40792f13922445_111.png)

O。

![](img/5876017ddf3a5b8c8c40792f13922445_113.png)

So。The time is2 now， maybe another five，10 minutes I'll just take。



![](img/5876017ddf3a5b8c8c40792f13922445_115.png)

Okay， this is your to we know next thing also， I'll just say。Now。

 the receive rate will compare with the new receive rate okay， so for DBM is there any。

 I mean is there any change in the DBM that will compare。



![](img/5876017ddf3a5b8c8c40792f13922445_117.png)

But 200 is the highest two point there 200 seconds， that's why you have to wait for some time anyway。

And posts。

![](img/5876017ddf3a5b8c8c40792f13922445_119.png)

Okay， it is done now next thing is。

![](img/5876017ddf3a5b8c8c40792f13922445_121.png)

我了 that。

![](img/5876017ddf3a5b8c8c40792f13922445_123.png)

Next thing is DSDV。

![](img/5876017ddf3a5b8c8c40792f13922445_125.png)

ok。

![](img/5876017ddf3a5b8c8c40792f13922445_127.png)

Next thing is DSDV and finally we have DSR。

![](img/5876017ddf3a5b8c8c40792f13922445_129.png)

![](img/5876017ddf3a5b8c8c40792f13922445_130.png)

So if you have any queries， you please let me know in the chat box so that I can Ars I will learn example。

 can you can try the same example。

![](img/5876017ddf3a5b8c8c40792f13922445_132.png)

![](img/5876017ddf3a5b8c8c40792f13922445_133.png)

Exercies for you。Okay， now again see。

![](img/5876017ddf3a5b8c8c40792f13922445_135.png)

This is an exercise。Okay， now this is done the meantime I will just run this。

 I'll just explain you how that can be done。

![](img/5876017ddf3a5b8c8c40792f13922445_137.png)

This is DSr。Now the exercise is in the managed routing compared that CC file in the same file what I work now。

B the character6 of E even wirelessser alone， I have not use other two protocols for the average receive rate when the number of nodes are 30。

50， 80 and 100 so that means。Now the number of node is by default 50 now what you do is you just change it to 30 then one more time change it to 80 and one more time change it to 100。

For that， take the running for the Y U and DSS Oaser for both the times。

And then average receive rate means you compute the average value from the Excel sheet from the CSV file。

 compute the average receive rate， then plot。😊，For 30 in the x axis is 50， 80 and 100。

 what is average receive rate？For the number of nodes you have to have two graphs。

 one is for AW and that for Y lesser now this in exercise。



![](img/5876017ddf3a5b8c8c40792f13922445_139.png)

It very easily can be done。Okay， now still is done I will just show you another receiver I already have their graph this graph I keep it ready。

😊。

![](img/5876017ddf3a5b8c8c40792f13922445_141.png)

![](img/5876017ddf3a5b8c8c40792f13922445_142.png)

And I'll plot one more thing also。完上好了。か。Okay， now this thing， I just keep it ready like this。



![](img/5876017ddf3a5b8c8c40792f13922445_144.png)

Yeah， it just don'。

![](img/5876017ddf3a5b8c8c40792f13922445_146.png)

やさ。So now control war。I just open open。All the fourphys。Avo DV， DSSEV， DS app and O， all the four。

Po the parameter I delete Controlless control H。怎么。Bland space replace all。少。They place on。

谂度 less频度 h。你唔起身。A多。Until bench， they place a sick。



![](img/5876017ddf3a5b8c8c40792f13922445_148.png)

Okay， so now again， what I do is I'll open the protocol file。



![](img/5876017ddf3a5b8c8c40792f13922445_150.png)

In that protocol are Pld， the blood file。Here compare means here it is compare 2。

I create one more file with the same data because everything is same only。



![](img/5876017ddf3a5b8c8c40792f13922445_152.png)

Now let me run a GNU plot。

![](img/5876017ddf3a5b8c8c40792f13922445_154.png)

Yes。Now it will create one more compare our two file。What can you see here？And is he hip？呃。Okay。

So you can see now this is the left hand rate compared to is now recently got we done so we have increased discibel the transmission power to 7。

5 to 9。5 dBM for that how the received rate packet received affected and the right hand side we have the deccibel rate is dBM is 7。

5 so for the 1。5 dbM you can see how the performance in the initial time you can the blue color see it is DSR and the initial time say up to 100 immediately it clockus 20 receive rate。

But here it goes up to 160 so because of the highest trans power it instantiates very high in the peak in the peak so most of them are in the peak you can see thev also how many time it clocks clo it we can even you can see the original or DSDV so it has cloing somewhere around 14 in the comparative to in the comparative plus nominal so increase in DVM will increase the transfu power so if you compute energy then obviously you can compute the energy occupation will be more when the DVM is more if it is less when the DVM is less so this way you can compare through graphs with receive rate and packet receiver just I have just generally pack receiver rate but we can able to compare throughput flow energy everything we can able to do on this comparison。

Okay， so this way we can able to compare our research， our manual routing protocol。

Our wireless communication protocol with the available to。

 so I have not gone anywhere the file is already there in NSS3。

Only thing is we need to use the file and make it to our description and then we have to change it as per our convenience then we analyze it So this is our second step first step is to understand the code that we already done second step is run the code with the various parameters that also we have done it Third work is we can do some small experiments or something so that I have given you fourth even is we can modify something okay oh this this part is lagging here let me modify this protocol that is what the first step that is where we call that as a research but till this time we can able to do everything as per our convenience。



![](img/5876017ddf3a5b8c8c40792f13922445_156.png)

ok。So。