# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p04 -04-Underwater Sensor Network Simulation using NS3 _ Aquasim _ -BV1aQmtYZEPr_p4-

Good do you need， friends？ This is Praip Kummar here。

Today we are going to see how to install aqua simulator in network simulator 3。Actually。

 the history behind aos sulator， it was launched。 It was developed by research mainly for N S2。

 for mainly for underwater sensor networks。it was having a 3D model as well as a  two dimensional model both So after for 10 years or so。

 there was no support from Iin。Because of the change in operating systems like Uuntu Linuxux Mint and federalera。

Aosm was not supported in all these operating systems。

 So it was a three days process to customize aossm for N N S2。 Also。

 the3 three dimensional aossm is still more tough to deal with it。 So now recently。

 your professorsor colour Martin， PD student。He has done。

The aqua he is maintaining the aquaium new next generation for N3 since N3 is picking up in the market。

 So aquam Nng is been very popular in installing under N3 the main advantages it supports the three dimensional model to dimensional model and various medium access control vector based forward algorithms and there are so many algorithms and protocols。

 architectures available for am later。 Now in this post。

 what we are going to see is we'll be seeing how to install。

This echo simulator in network simulator 3。So here comes to the section。So， installation of。Quassim。

In N S3， this is what our topic is all about。 So the first thing and foremost thing is before we install aos。

 we should have installed N S3 already in our package and you can refer my website N Sam dot com for installing N S 3 in U to16。

04 I used here Linux Mint 18。1 So which is developed from U to 16。

04 the same repository repository it uses So the same whatever instruction I am telling you here will be working out very well for Ubu 2 16。

04。Okay， so coming to this point， I assume that。N3 is already installed。

 assume that Ns3 is installed already。And now we are going for additional instructions。

 So the very first section is， so I am using the Yis Linux Min。



![](img/99bc508e0b72c20cc510420cd5a56c78_1.png)

18。1。Then yes where a three version is。

![](img/99bc508e0b72c20cc510420cd5a56c78_3.png)

NS hyphen 3。27 so I am using the version Ns hyphen 3。27 so that on the a Nng was tested in Ns 3。

242526 and 27 so now the recent version of Ns3 is Ns 3。

28 which was not tested but it still works fine as I have already tried it still looks fine So let us go to the instructions of how to install this aquasm。

So I have a folder available。In a solid1，3。27。Then Cd NSs 3。27 and C SRC。

So this is the place that I' will be going。 So what you do is you can execute this command like this。

So Ill just give the instructions on how， how to use this command As assume I have installed industry3 in my home folder。

 So in the home folder， you need to give this commander。N S Ali iPhone 3。27 slash N 3。

27 slash S because we need to download the am package into this source folder。

 and then we have to compile it。 So for downloading this source code from the website Either we can use the Github website through cloning or we can download and then extract it。

 So there are two methods but Github seems to be a better option as the folder name folder structure。

 everything will be as per their design， it will be installing successfully but I have tried with the separate download。

 So you need to rename the folder according to the specification。

 what they have mentioned According the am will work。Yes， now， now the instruction for this will be。

 So we have to use git clone。So already we have installed this software Gi Gis after through the repository using a pseudo app space install space G I T Git all it right。

 Now Ill be using a URL here。 So you can see Ht Tps Github dot com or Martinfi aquam hyphen N dot gi。

 So this is the command。 So you can access all this comments in the YouTube channel itself Ill give you。

So， get loan。Then this commander。 So once you give this command here， this will be downloading。

Or the cloning the accuracyquaing directly from that website to our folder here。

Okay done so when you check it here so we have seen that we can see that there is a folder called this aquam can see that aqua hyphen Sim hyphen N So it is mandatory mandatory to mention the folder name like this aqua hyphenm hyphen N I have tried with simply with aquasm without any gap between them and I have tried with aquaquasyim hyphen N hyphen master as the download H I was getting some installationsulation error when I was installing this so better I tried to have this keep this name。

Ito it。So， that's what。This second command So after it is added to the source， we have to run it。

 So to run this， what we have to do is。So to install this first we have to come out of this source directory。

 So Ill be coming here now， so I am in the directory N S 3。27。

 So here is the commander dot slash valve。So， enable hyphen examples。In enable。Hyon test。Configu。

So we have to give this command。So we will just copy this command。I will be giving it。

 pasting it here。 So first thing is you have to come out of this。And then use this command。

 So this is the command。 So let's see then these command also are not。

Sometimes this command might throw an error because it may be giving a error in Python。

 So then after that we will give this command graph。So this command is door slash our next command。

So we can see that the accuracy models are been compiled here， so there are 275 packages。

 so if you have installed NS3 already。So， the time taken will be very less。

 but if you are installing industry for the first time along with the acquisitionqua then it will be taking some more time to get it installed。

So you may be getting an error sometimes so because of some python binding error。

 if you get any error on Python bindings， so what you can do is in the same command。

You can use disable Python， disable。Hi， friend， Pyton， you can use this command。

So along with the v enable example， enable test configure， you can disable Python here。

 So this is to indicate that there is no python pending needed for compiling as in Hegi。

 so you can disable it。 So in my case， I think so far， I didn't get any error。

 But if I encode any error。 then I need to give the command again here here。 that's less v。

Configure disable Python with the examples enable and that test enable。

So let's wait for another two minutes， so that。The software will be installed successfully。

It's no again see。The model is built here， so I will just maximize this window here。



![](img/99bc508e0b72c20cc510420cd5a56c78_5.png)

And the models are built， you can check it here aquam energy has also built successfully。

 so that indicatesics that aquaoussm energy model is been built successfully。

And if you want to run any examples over there so you can what you can do， you can go to the source。

 you can go to aqua same folder and you can go to examples。

 So there you can able to see there are so many examples Bm do CC D does dotcc flat test gold string broadcast Mac example like that so you can able to run so many examples here。

 So these examples you can able to run by bringing it to the scratch folder and then you can start running。

So let me give a small example here。

![](img/99bc508e0b72c20cc510420cd5a56c78_7.png)

So what I do is I do an example graph。Double a control。嗯。Broadcast。Meg。And underscore score example。

So what I do is I will bring the broadcast Mac， for example。

Into the scratch folder So whatever it is I go to Src than I go to aqua in。Then I go to examples。

 so here I will be copying this broadcast example。So broadcast Mac and an example at C， C 2。

Previous folder。Previous folder， scratch。So what I do what I did is I just copy if I using the command C。

I'm in the source director， I'm in the example directory here。So Ill just use this command here。

 the CP broadcast Mac example that is go to the corresponding folder where this file is located。

And then go to the previous directory， one more directory， one more director。

 you say that we have a scratch folder so in the scratch folder we copy this。So after you copy this。

 you just come to the。NS 3。2 sound folder。 So this is a location where I will be running it。

 So what I do where。W I and run， scratch。Broadcast。Mac underscoreco example。

 So since for running the C plus plus file， you do not specify any extension here。

 So we are not specifying anything and Ill be running it here。



![](img/99bc508e0b72c20cc510420cd5a56c78_9.png)

So， this is the first example that。啊。Acrosm users here。

 So you can see this here how many nodes have been created。

 There are these many nodes with the position is being created， and this is simple simulation。

So complicated simulations like how to see the three dimensional because aossm uses underwater sensor networks wherein in the underwater sensor that when the sensors are thrown into the water。

 so they will form a three dimensional mapping where the nodes may not sink to the ground。

 but it will be floating。So during flood also， it will be trying to send the packets and we should have a supporting a medium access control and the first and foremost thing is a broadcast because when they all the nodes in the water。

 they broadcast themselves to form the network first。

 So these example shows as a broadcast Mac example for aquasm particularly for underwater sensor networks。

So this is a basic introduction of how to in aossm in Ns3。

So this video is recorded mainly for the purpose of my students that some of them are doing their work on underwater sensors。

 The first and foremost difficulty is to how to install this software in Linux， particularly in N3。

 So that's why this is there。 So maybe subsequently I'll give you some more examples on how to use aossm examples and how to predict the performance characteristics of underwater sensor networks。

 So thank you。 So if you want to。Help me out so you can subscribe to my channel。

So I have a channel here in YouTube You dot com s T S Pre coa Also refer my website H T T P。嗯。ASNM。

t co。So please join my website as well as subscribe to my channel。 So thanks for listening。

 Thank you。