# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p18 -18-GPSR (Greedy Perimeter Stateless Routing) protocol in ns3.zh_en -BV1aQmtYZEPr_p18-

これ。Does it come here for the very clinic。So welcome to engineering clinic。

 So today we are going to see a protocol called GR。So we call it as breedy perimeter。

stateless floating protocol。So this is what we will be seeing now。So this is mainly used for vans。

 so we call it asvehicular around milk。So this is what we'll be seeing today。

So there are three versions of GPSR protocol， part of our GPS GPSR protocol， EmM GPSR protocol。

And GPS a product。So if you are undergraduate and postgraduate。Postate。

You can use the module as it is。And competitive。But these products。Qu了。Ps。

 so this way you can try out。If you are undergraduate for graduate， if you are a scholar。

Youre a PhD scholar。You can modify the protocols。系0。The same you were one。TP is alternative。

So in this example， in this video。Well be seeing the installation。Of GPSF。And some source goods。

So the next video， I will explain the complete source code。And in this video。

 I will just tell you the how to install this package。

You can get to know what are the how to run any GPS protocol examples in NS3。

So I have tried this example in NS3。27 version。Which。I could not succeed。So。I prefer。

I'm going to N S version 3。23 for this。So I will be having two folders in my installation right one is for NS 3。

27 another for NS 3。23 so we can parallel run both of these both versions in the same Linuxux operating system。

So， we can then。Multiple versions of N S3。So， I am going to run。Nus hyp，352，3，4。GB up。

And other simulations。べ。啦四欢至翻到十啦。And the in S version，3。29。

So no issues in that so that we will be doing it。 I will come to。Installation。

If you are installing NS3 for the first time you are。Im starting。In three for the first time。

Install these packages。Sese the following package。So can copy past。Poffpy based。From得啊咁唔 from得。

Copy paste。天扑壁。So these are the packages that we need to install pseudo app。

 so from here to here we can copy。Forge to here， we can copy and then install。

 So we will open the terminal。

![](img/f4ce06ce562c8c8320926656f49fcc18_1.png)

How来 doです。

![](img/f4ce06ce562c8c8320926656f49fcc18_3.png)

Ill copy it from here， I already installed it， but since you are installing for the first time NS3。

 you just try this。

![](img/f4ce06ce562c8c8320926656f49fcc18_5.png)

So first， these are the prere for prerequisites or requirements for install industry。So， again。

 download load yet。记个 password万全制要数到 here。

![](img/f4ce06ce562c8c8320926656f49fcc18_7.png)

I give you the password。Yeah， so now nothing is needed。 So because all the softwares are in。

 But in your case， it might be taking some time to get installed so that。

The prerequisite is completed。So， next thing is。We download by cable。downloadown。In us 3。23 back。

You can download from their website or directly use the commander， So better than。Use that。今度は。

Yes given below。So you can use one by one as given below so far as。SoThis is W get。

 So W grid is nothing， but you can download the package。 So even it can use W get， I can see。

That means even if some internet get disconnected in between， Do grid still works fine。

 So just copy this。

![](img/f4ce06ce562c8c8320926656f49fcc18_9.png)

Tl window， clear this screen。Con me。 So once you ran it。你本。Go and process the N S name or G。

 And for downloading this software。So already retrieve。

 So that been said already I have downloaded this package。 so in only13。23。

 please see that I already have in only1 3。27 years， I also downloaded in。3。23， dot dott， V，0，2。

So now what I do is I will be writing a commandar。X Jf。啊啲 x three者系间。だげな。1，3，5。

Street or turn down Vi2。 So X for extract。V for verboose， when during section。

 we can able to see what file is being extracted。JFR extracting the B2 file and F4 so。

So this is what we both wants running。So after completing everything。Well get a folder get formed。

 So N S 3。23 is is formed here。 Now we are going to reach our insides。



![](img/f4ce06ce562c8c8320926656f49fcc18_11.png)

I will not take it over。 Ill just come back。The next command is。Yes。That， is a。X， JV。



![](img/f4ce06ce562c8c8320926656f49fcc18_13.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_14.png)

Now， once it is done。Have this。Com is。So we will go and get this folder now。



![](img/f4ce06ce562c8c8320926656f49fcc18_16.png)

So， what we do is。C D， N， S honey，3。23。 We go inside this border。

So what I do is I'll just copy this command。

![](img/f4ce06ce562c8c8320926656f49fcc18_18.png)

C D， A7， all in one。3503。

![](img/f4ce06ce562c8c8320926656f49fcc18_20.png)

Sohow until these done。Will be。Now， we' will be downloading this package inside this command here。

 I have a command call Git git。It's from a downloading from Github clone this ID and PhGPSR has already been given over that。

So just cloing into it。 So cloning is nothing downloading the package in the current folder。

From the server to the。A local machine。 So that's what been drawinging means。

 I will open this Se data window now see。

![](img/f4ce06ce562c8c8320926656f49fcc18_22.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_23.png)

I'll just show you here see P GP is being downloaded now。 So here we have。



![](img/f4ce06ce562c8c8320926656f49fcc18_25.png)

Yeah downloading this yeah。Everything is done。Now we can see PhD P is downloaded here。

 We have examples。We have figures。 they are already given tons of figures over here。



![](img/f4ce06ce562c8c8320926656f49fcc18_27.png)

You can see there are three protocols compared PA GR， GPSR。你晚唔知俾晒啲水啲。

And see all the they have given it here。

![](img/f4ce06ce562c8c8320926656f49fcc18_29.png)

Then we have results。 So GPS results per5。啊大跟。In past 20， I guess a name of GPSR， the P GPS app。

Then the PL files， so hand scripts。So there are some Madla scripts available there。Then source。

 So in the source， we have。3 models， MM GPSR。Location service， GPSR all these models are available。

The source now what we do is we copy all these things if you have a corresponding for。

And we'll be doing that。So that is what we are going to do now so it is available in this location。

 so from this location we have to copy these files and paste it in a particular case thats what we will be doing in now So either we do graphically or we do using commands。

So Ill show you what of this。So that you are you can easily do that using graphically。

Rather than in the command mode。Okay， so no。Just copy these phones here。So yes see what it is。

 just copy all these files I'll just use control C。Copy this。And go to NF Ali 3。

23 here inside that we have source folder， inside the source folder。

Paste it control V can see that we have pasted。All the four folder inside say this。Then again。

 we'll come back here。We have examples， so we have only one file here。

 control C to complete this file。Usually all the examifier will be past in the scratch folder。

 So what we do is N 3。23 scratch folder。And paste it here。 So this will be pasted here。

 Thank give the command also， don't worry。等。Again， well go back。FirstRe and scripts。 So these things。

Again， copy。Contency。These things I can go and see here。Inside this folder， and 3。23。And别这铁。

So that means figures， results， mind as such， scripts。All these things been pastered in N S 3。2。

So this comments also Ill be showing you。So what I do is after we done this。

 just these the companies are the commands to copy。So。The following。Other commentss。

To copy the product。2 endless 3 folder。But I have shown you graphically， so I have shown。How to copy。

理は。So it's your choice to give whether you use this and that。So can I have shoe both。Mly。And us 3。2。

long。乳比十。Since I am also doing for the first time I。Iread yesterday， but for recording this video。

 I am just doing for this next time。とだた。I have deleted the folder or whatever I install I delete it。

 and I am doing con fresh。So we have the command here。 So first I go inside the folder。

So first of all， I is open and terminal。Open a terminal and go to this place C， D， N S。可年。Iyhen 3。

23 slash in iPhone，3。23。So this is a photo I we will be going to。



![](img/f4ce06ce562c8c8320926656f49fcc18_31.png)

Okay， so what I do is I'll be going here。So it zip。Put exit。 So now I am in this folder。

 Now I am in the home folder。寿司啲人。对 you。S a  second 3，5，2，3。 Now， this is the place I will be going。



![](img/f4ce06ce562c8c8320926656f49fcc18_33.png)

Then what I do is。I need to compile it now。 So usually what we do is this is a compilation we use not s back。

Sorry， builder or P。Enable hyphen examples。Enable hyp test。This why we usually doing it。

But now in this case， since the medicineison library is sold there， so we will be using this。

C plus plus flags。 So what flags。 So this means all compile mathrimetics will be calling all the flags。

Flas and then的。This is a syntax for these two examples。Instead of this， I am using this。



![](img/f4ce06ce562c8c8320926656f49fcc18_35.png)

Don't know what I do。 saying just go here。like。

![](img/f4ce06ce562c8c8320926656f49fcc18_37.png)

How this will be compiling this entire N S 3。23。So now is done。

So there are some models that are not being enabled by with。 there are some models no issues now。苏都。

Slashlash。Yeah， so now all totally there are three，3，9， three packages we can start。

So the installationulation might be taking some 20 minutes。

 15 to 20 minutes according to the speed of your machine。

So my machine is running with the solid straight drive。 So it's a MacBook app。 So I think it will be。

Taking some 10 to 150 minutes time。 So anyway， just pause this video after the installation I will come back。

So I got a mirror in between。So， I got some error。So I need to in first in this。

 So we I need to give。The only that I will be giving。So rushlash bath。

So you have to give dot slash web on now that command is running now。



![](img/f4ce06ce562c8c8320926656f49fcc18_39.png)

So we have only 202，27，237 packages。 So after this package is installed。有咁病。F friends it's done。

 So I have just built all the modules here。 You can see now。GPSR with the nope Python is installed。

 MM GPSR is installed。And P GPSps are also installed。

 so all the three models are installed and these are the models which have not been built。

 so no issues choose for us now， So all other models have been built in this GPSPS app protocol。



![](img/f4ce06ce562c8c8320926656f49fcc18_41.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_42.png)

So now。The installation is done here。There is enough GPS。I that maybe。Now。

 so if we this example only。で続。And这。Alread have a fight。でコだ。いらねて。

So what we do is we go to the fold up there。

![](img/f4ce06ce562c8c8320926656f49fcc18_44.png)

So， do slash5。W分 then。BPS。H from me， you can see this that。是らね。Since the GPSR is already installed。

 P GPSR is installed。You can get the。な不ラ。Sreing that he notes。impacts？And this will compute。

So many folders， so many results， all these things will compute。

So starting situation about 200 seconds。Starting simulation for speed to 15 milliseconds。

so the simulation might be taking it longer time。The simulation is now 10 seconds。

 So every 10 seconds， it will show you the simulation。Now in another video。

 I' will be showing you I explaining the source code for GPSr。

Along with that I will run the simulation and plot the characteristics。

 so for timing being this video， just check whether how the file is running。

 how the GPSR5 is running。We wait for 200 seconds。Now only practice seconds。

So still the simulation is going on now it is 160 seconds， I will wait for some more time。

So you can see output operations are successfully performed on under performed2。

 So the total 200 seconds of simulation is done。

![](img/f4ce06ce562c8c8320926656f49fcc18_46.png)

It has taken some time。 So now we can check with。

![](img/f4ce06ce562c8c8320926656f49fcc18_48.png)

There are many results already， we have seen the results scratch and everything。

 So in the results folder， it might happen been。product。 So here we have P pieces another steps。

So you can see that number of C is this。 Last package is this。 total ton and。

If this receiving is this packet delivery ratio， this hop comp is this。Delayze this。 So like this。

 we have。Got the data。 So anyway， we will be seeing this data in the next video。



![](img/f4ce06ce562c8c8320926656f49fcc18_50.png)

So for timing being， this is just for。Insulation of GPS up for。So thanks for watching。おるよ？

你 suspect speak。And share a your them。So for any source code download， you can use。

Ww dot n S A dot com。 So this is also my website， we can。Download the source course from here。

 So thank you very much for watching。

![](img/f4ce06ce562c8c8320926656f49fcc18_52.png)

拜拜。