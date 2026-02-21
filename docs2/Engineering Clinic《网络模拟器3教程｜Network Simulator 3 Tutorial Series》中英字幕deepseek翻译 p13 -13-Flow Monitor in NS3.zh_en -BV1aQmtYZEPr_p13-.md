# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p13 -13-Flow Monitor in NS3.zh_en -BV1aQmtYZEPr_p13-

Hi friends， good evening。 I am Zip Kumar again for engineeringer clinic。

 So this time we are going to see a new topic called us flow monitor。So this is again。

 for the support for industry3。So in network simulator 3 so there are various software available that can able to monitor the performance of the networking one such one thing is nothing but the flow monitor wherein you can able to see there are so many parameters you can able to monitor using flow monitor so maybe I'll just show you in the documentation website about what what other the things I mentioned。

So flow monitor Rna3， when you search it in Google。The very first link you can able to see。

 And these are the things that you can able to calculate。

 So you can see that time first transmission packet。Time for lost packet， time for receiving packet。

 time lost receiving packet， delay some jittersome transmission bytes， transmission packets。

 receiving bytes， receiving packets， lost packets， times forwarder， delay histogram。

 jitter histogram。Pcket dropped。 bites dropped。So these things you can able to monitor and along with that。

 you can able to see some parameterrameter， which also maximum per hop delay start time delay by being width。

Jter been with packets has been with flow interruptions been with flow interrupt minimum time。

 So these things we can able to see So this flow monitor generates an XML file like this。

So it generates like this。 So based on this Xl file， we can able to monitor this。

 So in this exercise what we are going to see is。already。There are some examples。Vium S 3。

We will be using one example。Call us third or C。And another example。Call us。Mannet hyphen。

Roouting hi compare that CC。 So already we have seen this this example we have already seen as part of manner routing comparisons。

 Anyway， this is the flow monitor。 So we will be using again these two examples。

 I will show you how these examples are being used。So third orcc。

 we may not see any lost number of lost packets here because it's a very simple network。

 but we couldn't able to find any number of lost packets。

 but Manropic compare is completely a wirelessroding protocol file so we we could expect there are so many packets of in loss are receiving or so many parameters we can able to see So not all networks record all the。

Performance matrix， it depends on the network， what you are selected。You will be selected。So now。

 so this is what we are going to see today。So very first thing is first step is what we do is。St1。

国闭的。He both反。그럼。Examples。Porial。Slide third dotcc。And move it to。폴。Today。

 the first thing we will be doing。And so only third that you see first we will be doing now。Okay。So。

Let me do that。I'll open it。

![](img/901819938fc25a39855358583152eedc_1.png)

So what I is， I'll just go and sit on this。Okay， so I have gone into N 2。3。27。C P。

 service copy examples。Tuttorial， thirdcc。And past it to scratch。 So I'll just。Using this。

 So in case if you are not comfortable with the terminal， you can able to do the copy using the G Y。

 So what you can do is go to this folder here。

![](img/901819938fc25a39855358583152eedc_3.png)

NS volume 3。27， ns 3。27。Go examples。 Go to tutorial。And take the dot C。

And take the dotcc and copy this。 I just copied it here。Then I can you back to N3。

27 here and put scratch。

![](img/901819938fc25a39855358583152eedc_5.png)

很别ityia。走理不理。So this is the way can able do。 So now we can see。Sorry， scratch。



![](img/901819938fc25a39855358583152eedc_7.png)

And you can see I already pasted this。 Similarlyly， Ill be copying this file also here。

So what I do is C examples。Routing man routing k C and put it to scratch。

So what I did is I copied another file list。嗰边。Mnet iPhone routing dot。系分。Comparare that C from。

The example slash a routing slash。And move to scratch folder。

So this what I'll be doing is step number， it's done。Okay， now step number two is。Include the code。

 relevant for。Flow monitor。Okay， so this is what we will be doing。So please follow the steps。

 So there are。2 header files need to be included。To be included。 So what are they。H shape glue。

Nas3 s flow hyp monitor tor。And the hashing blue。In this three sketch。F hyphen monitor。

 hyphen helper dot H。 So we will be including。So what I do is Ill just copy these two header files。

These two。Copy paster， open this file。The addict。道的。いんで。So， the head files。Let me use。

Added for flow monitor。So always， it' is better to give any comment line over there before you do any changes so that when you debu at a later period of time。

 you can able to。See that you have added something Okay。

 so flow monitor dot H and flow monitor hyphen helper dot H we have added。

And come to the end of this line。 So here only we have to add this code here。

So whenever you want add this code we will just go back here， the flow monitor。

 So just four five lines of code will help you to generate the flow monitor。

 so now we can see the typical use they have given in the documentation itself。

 So if you are if you have patience enough so we can able to read the documentation slowly so Ive gone through the complete documentation but anyhow can able to see。

So now what we have done is so from here to here， you copy。So you can see there's a D3 lines。

They have just copied above the simulator stop and similarim run function after the run function。

They are put it to this the Xl file so what Xl file need to be generator Okay so now what they have given the coding is I will just copy first then I will explain you。

So， copy this。といえ。So now you can see stop is here， So somewhere here。I past it。

So this is stop I am pasting it here， So the code you can see pointer pointer flow it is something like this。

 So this syntax is something like this。Flow monitor， star。Then flow monitor。

 So this is what they have been calculated since pointer is not been used because they use templates instead of pointers。

 So it is good that we didn't use pointer， but rather than they use Ptr。

 So P T S pointer flow monitor create object for this。Then similarly， a flow monitor helper。

 here grade helper class。And that will be installed on the entire flow helpers。

 So the form monitor is。The flow monitor object is initialized， too。

The pro helper and install on hold。F， so we are going to monitor the per packet flow。

 So it will be installed on all the packet flows。 So that will be monitored here。

 So that's what these three。Now we have to see list this to the X file that so they use after this run or destroy also we can use maybe we can use after run values use。

So， after this run。Did we go back yet。Sorry。So this link you can copy here。Okay， so。Maybe。

 I'll just copy this here again。Include that。Following零。I heard there。Simulator。看到。并没有能理。So now。

 in this case， not name of the file we can use。 the name is third direction file。

And then same name of name object。 you have to see the what is the name object。

I say it has a flow more。どら。好き。Okay。So now again， I will go back here。

 I'll just copy these two lines。So this what we you be doing it。I just included both。

So now I'll come back here。He saved it here。 name of the file， third direction。So now step 2 is done。

 so we have created。I is added for flow monitor。So flow monitors again very powerful in Ns3。

 so such kind of flow molecule is not there in Ns2。

 so it' is a very great advantage of Ns3 to use this。So now this thing over。

 now we come to step number 3。Step， please。R the example。 That is step 3。

So running the example will catch you。

![](img/901819938fc25a39855358583152eedc_9.png)

来。W A and run， scratch third。Not that extension， So we be using。

So it will be compiling the third docc file。See what other the files are in the sc folder will be compiled。

 Every allll files will be compileelled。 Okay we got it now。

 so we got around some four bytes or five bytes we have bought it。



![](img/901819938fc25a39855358583152eedc_11.png)

Okay， so now still three is on the example。 the command is。嗯。对吧。得出来粉人。Scratch， scratch， third。

So once it is done。

![](img/901819938fc25a39855358583152eedc_13.png)

The example file。 let's start our example。So we have a file full plus third or X file we got created。



![](img/901819938fc25a39855358583152eedc_15.png)

Check for the third。That was greater using。我可。Okay， so the file is present。Open this file to theem。

And it looks like this see the number of packets are just there are only two packet exchanges。

 so you may not see much of the information。So we can see is there any port number we have a destination port number 4915。

3 and destination port number 9， so we have used these two things in the inside of our script。

So that's what we have created。What I do is。Go and say third orcc5。And instead of one packet。

 I can create 1 packets of a00 packet。Can create some hundred packets。So that。I need more。

Dead height to the network。Okay， now we can see。Ive changed it to instead of one packet。

 I made 100 packets and let's see how things are changing。Yeahや。

I can see there are number of packets are very high。Now again， we have got a reload。

So a number of language terms will be height。Again， we have the design pool this thing and。

4 number one5 and four number nine。Now we be processing this file。So now what to process this way。

 So to process。This file。We need to search。Within N S3。发先肥。

So we have found out a location called S Cd。

![](img/901819938fc25a39855358583152eedc_17.png)

SFC C。Then flow monitor。And examples。 So within we got a file called this flow monitor pass results got P。

 Okay， so this file we got it。So， when you see that。



![](img/901819938fc25a39855358583152eedc_19.png)

Directly。Use is the directory。

![](img/901819938fc25a39855358583152eedc_21.png)

So what is the location where we got this file。The name of the file list。



![](img/901819938fc25a39855358583152eedc_23.png)

F on parts results P。So what we do is， we can cop。Can copy this file， too。然 home for。

So now that's what we'll be doing。The C flow on。Then。空。Inus， solid1，3。27 slash N S 3。27。

We copy this file， too。2 point is under the X。Copy 2。U it is failed， though。A location that。

The third do。AX mod this created。Ungene。in our case， this will be the file yes。3パイト三総約カです。Okay。

 so now well go to T。 Now that is step number 4。Step number 4。Paars this phase。Youing the man。You we。

So this have a by time failure。

![](img/901819938fc25a39855358583152eedc_25.png)

So this file is Python fail。So how do we do this？Python space。 So the name of the command is Python。

Flow on dot parts that results the P space， third dot example。おわれなんです。And what will be。Yeah， now Im。

 I am in this folder。 now we can see the file name is。Flow mount pass vessels at P。

 and we have third at X， sober22 files exist。So that I mine is byyth done。Fman paric cells。

 then third att x。So hundred0 is done。It will give you a small compilation here。

 It will give a small flow id there are totally two flow ids， So one flow id get UDp。

 the total time bit rate is this much receiving bit this much and the delay 6。

15 milliseconds similarly here transmitting bit rate is 9。63 receiving bit 9。63 and the delay is。5。

69， so there there the average mean delay across flowidD。 So there are two flows。

 so where the flowidD is given like this。So this is one method there。

So this one method where we can able to see the。Mean delay calculation for two flow edges。 So here。

 the number of flow is just very simple that there are just only two。So for complicated examples。

 we may get the number of flow will be very high。But how can you plot a curve or how can you plot a characteristics based on the entire Xml file so in their case this third orcc may not be sufficient for us to go for it can go for some file that is bigger。



![](img/901819938fc25a39855358583152eedc_27.png)

Okay。そう。把星。Un bloodying。Psing and pack using Pythonscript。Preferably math plot。So using this library。

 we can able to。Loloting， so what I do is Ill be adding the source code。Why am my website。

So that you can download the source code via this website， NSSAname。 co。

 so you can find the relevant post and you can download the source code via this NSSAname。 co。Also。

 I see the description given below I'll be giving the source code。

 So I have another file that' is called us the name of the file is step5 I report it。Step 。

 So the name of the file way I call it as。F达 Bway。It was generated。蛮了。好 called box。The flow monitor。

 X height。O。Okay， so now I will be opening this file。So plan Florida P。So this the float。

I'll just explain this code here， So first its a python file。

 So first we just process this Xml file based on a tree structure because it is like a document object model that is dom on the we have two pars ss in the dom。

 so it is a dom parer。So first we make it the X asset3 and then we try to import data elementary。

 then import system， sometimes people use operating system。

 but we import system and import the plot so we are going to plot something using map plot library so it is something like a graphical graphical。

Graphical processing， wherein you can able to plot characteristics based on this library。

Then pass system don augment given vector1 method means the file that you are going to supply so that will be passed so we create a list bit rates losses and delays so we create three list colors bit rates losses and delays so what about we do is so we are keep on adding to this particular list one by one as and means we encounter any bit rate encounter any losses we encounter any delays from the Xm file because Xml file it' is like a3 so every time it goes in infinite loop so it goes in a loop by loop so in each time every time the loop executes the value will be populated over here。

For what we do is for flow in findal flowtts slash flow。 So that means。Inflow sets under flow。

 So I can go here。In the Xml file， so we can see these the flow strands。

 So these is the flow strands under that we have flow。 So that way we can able to process this flow。

 So flow strs。Slash flowings distinct， so。This we hurried every time。

And when we read IP and4 flow classifier flow。It will go and check whether IP and4 classifier is there。

 So if it is not there， it will be discarded and it will go to the next one。 So that way it will。

Read it。 Then if Fyd is there， get Fd， then break。 And if destination。

So what is the destination port if we come to third of X， we have destination but 4，9，1，5。

3 and we have 9。 So there are two one port， one destination port。 So what we do is we make it as。4，9。

1，5，3。 So relevant to this port destination board。we process it and we go with the last packets and we go with Rx packets。

And we go with bit so bit trace start open means every time whenever we encounter we append it to the bitrate variable。

 so this variable will be app it。Then。Time for receiving packet， time loss， receiving packet。

 So we calculated it， and we found the duration。 This is our calculating delay。

 So delay t1 minus t pin to 10 for minus-9 in nanoconds， we want to find out。So this way we use it。

And here， if we takes it there， then we will append it。Then receiving bys。

 we added it and per duration。And delays up。 So we calculate the sum of the delay。

Then we will be plotting it using the subplot。 So bid rates flow bit rates will be in the X axis and number of flows in。

The number of last packets in the axis， number of flows in the way axis。

Second in the axises and number。AndLi maybe。WhatP this results are P。This is a very simple big。



![](img/901819938fc25a39855358583152eedc_29.png)

With谁白单。Fload R Py space with the name of the file is， third at symbol。Yes。

 so now there is no error that means something on。So what we do is the eventss is the name of the Pdf to open an N 3 R in Linux。

This will start video。

![](img/901819938fc25a39855358583152eedc_31.png)

So once you open， so I can see that。This is the graph what we got generated。

 so you can see delay in seconds。And almost this much delay a number of flows here。

 And here this is the number of lost packets， a number of flow bid rates。



![](img/901819938fc25a39855358583152eedc_33.png)

So this way we got a curve Now what we do is again we come back here。

 So all these thing flow based on 4，9，1，5，3， so I will make the destination port to 9。



![](img/901819938fc25a39855358583152eedc_35.png)

![](img/901819938fc25a39855358583152eedc_36.png)

So， in this case。Again， we turn it。 again， we go with。



![](img/901819938fc25a39855358583152eedc_38.png)

And this time， we got this。So this is a simple example that how the results at P file got generated。

 you can see that even I can remove the results at Pf and then generate again so。



![](img/901819938fc25a39855358583152eedc_40.png)

You can see start at Pdf， no Pd will exist。Okay， so let's file that video。

Maybe they can remove this sort。So no P exists。 So now I'll be running it again。

So Python product P third at x。Yes， now we can see。Res are P generator。 So to open this file。

 the command is varianceins。Results are big。 So there is the file that we got it。



![](img/901819938fc25a39855358583152eedc_42.png)

Okay。

![](img/901819938fc25a39855358583152eedc_44.png)

So this thing the float RRP is just written by some user in online so I have just taken this file and then I modified as to my requirement and I have just included this here maybe I'll just share that source code of the float RRPV also so now what we do is well go with a complicated example。



![](img/901819938fc25a39855358583152eedc_46.png)

然我 will 법。Complicated example。Call us man。Roouting compared C。 So this value will be running it。

So now what I do is I'll just close this third or C file。

I close this third at Xml file and float P Let me have it because I need to change the port number。

 So let me have it。And then I go here， go to scratch。And this， I take it。So this is the place here。

 So now what I do is。I'll include the flow monitor header file。 So first thing is。

I'll do this two here。So what do mine man holding on there。Iclude the flow monitorator heataper。

Then you come back to the end of this line already you can see that this point or the flow mode is already there。

 but they have co out by default， remove the comments or if you want you can include it。

So remove the comments。 So once it is removed。 So these three lines are。Already。And finally。

 after the run command。Be open。See if lets talk a month about it now， in this case。

Okay if your find name colors dark flow mode， So you need not be X always。 So whatever name you can。

 you can give it so you can give dark flow mode。The name of the file。 So what is this T R name。

 I will just check it control C controller。Yeah， TR name is man routing compare。

 So this is a name of this Tr name file。 This is finger。So maybe if you want to give。

 I can give my own name， Philip。Hello， can you like this。

P the flow so that our file generation will be per the flow dot flow flow on。So， we will be。

And generating your file。Card。The deep flow dark。L month。 So this the5 video later。你데也不有这样。

So this what we using seeing now。So， but this， this will take some more some time to。Because already。

 we have seen it to see。More about。The source code。And the explanation。H了。This link。Follow this link。

 So in this link， I just create a link。 You can see the description。I'll see that description。So。

Now I'll run it。 So to run this， the command is w double a can run。Scratch slash， magnetnet， hyphen。

 roing， hyp compact。So this will be seeing it now。

![](img/901819938fc25a39855358583152eedc_48.png)

So what we do is。Yeah， now well be seeing this。 Now， this will take some time to get compelled。

 I'll just show you。How long it takes to compile because the simulation runs from 100 seconds to 10200 seconds。

On various protocols， like DVD， D SR DSSTV protocols at wirelessr。

So I think it will be by default a ADV protocol， so it takes some time to get run。

Once the simulation start。I'll just post this video。 now we can see。From10 is that。

So it up to 200 week go because that's how the simulation is written。

So what I do I just pass the video。Once the simulation is completed， I will enable it。Yeah。

 so this is done。 So take a long time up to 200 seconds in card。Now， see that El do。おまあ。Yeah。

 pretty deep blue。That flow吗。So we got this file generated。 so maybe we just open it。

So when you see this is the flowman file， So totally。Cotal number of lines。

 the huge number of flow here。So you can see the total number of lines are very huge really。

 So a very large file。So you can see up to 8000 lines。 so you can see the number of lines is 8000。

So now we will do the comparison here。Plus do we do it by then。Flow系 flow bus。Po the fighting。

Sorry flowman par， flowman par。Then the name of the file is per flow。That format。

So now we can see there are totally  thousand533 flow， and for every thing it shows the delay value。

23，25，23。And sometimes we do not have the bit rate。 Sometimes we have the bit rate so。

It depends on the port number 6，54。So that's how it get it calculated。Now。

 what I do is I'll just calculate this with my 15。 So Python flow or Py。And previous folder。L mon。

It says float division byarrow。So betray have some issues。



![](img/901819938fc25a39855358583152eedc_50.png)

Maybe I can change the board number， the board number by rep 2654。So here I just change it to 6，54。



![](img/901819938fc25a39855358583152eedc_52.png)

So in this， I'll do this here。Yes。So now again， if you create a file name colors results dot P Y Pdf。

 So Ill just open it thes results dot Pf。

![](img/901819938fc25a39855358583152eedc_54.png)

It so this much。 So number of flows here。And delay in seconds here。

 So it shows you the aspect the flow， how the delay variation is happening here and how many number of last packets at various different。

Number of flows and how how many flows there was a last packet and what is the bit per second inflow bit rate。

 So these many packets have been lost。 and this information is plotted in this。Now what it is。

 I can exchange you to on any other port number， which is there in the flowman file。Destination。不的。

Is there any other port number other than this we will be verifying or checking so that we will plot accordingly these port numbers。

IThink there was no port number anyway fine。 So that means this protocol number is 17 and the destination addresses this that source addresses this。

 and thats how we calculated this。In Florida。Like， we can do some modification there。



![](img/901819938fc25a39855358583152eedc_56.png)

Now， in this example， what we do is in the first example， the flowman par file。

Regardlessgards totally this many flow is，1533， so total mean delay for each and every flow is thispatch。

 but how can we calculate the entire delay for all the thousand533 fluids。

 we can slightly change our code。

![](img/901819938fc25a39855358583152eedc_58.png)

So where we can do it。 So this is the code that I have。In N3 itself， we got this。

So mean delay is given here。 So in this here， we can able to see that flow or fluid is the。

Number flow 8， this。And delay is the mean delay calculation。 So if we divide the delay mean。

And divide by the number of flow I D。 then we can able to get the。Valish in millise secondss。So。

 that's how we can able to。So the case we have to accordingly put it in the loop。

 maybe I'll just check it and done now。Come back。Yes， no you can see this link I have added here。

So actually you have the proper indentation if that needed in Python。

 so this the line is already existed。 So what it is I added this line。En to end delay。

P do to F that means after the do， there will be two decimal。 If we only give four decimal points。

And it will be displayed in some。Milliseconds。Then flow delay means。

 so this same value I have taken flow delay mean into thousands that means I want to display milliseconds and divide it by。

The flow at flow id。 So a number of flow id here。So， to take it。We do is print。Floer。B I， so you can。

 I can print it here。I that what value will similarly print。Fer， delay me。Did there any can。



![](img/901819938fc25a39855358583152eedc_60.png)

Let's see what comes here。 So now I just use flow one here。When I see， this is the delay mean。

 I' am getting it。 And this is the number of。

![](img/901819938fc25a39855358583152eedc_62.png)

So， means that。This flowD can getting。 So we have float flowD is totally。



![](img/901819938fc25a39855358583152eedc_64.png)

So that means the last two players want to be。So we will be getting the average delay。

 So into a delay will be。

![](img/901819938fc25a39855358583152eedc_66.png)

![](img/901819938fc25a39855358583152eedc_67.png)

This end delays around 0。0834 milliseconds。 so this is add it a I mean average of 11 by86 plus that 23。

8 per plus 25。83 from this this and everything added together and divided by a total number of flow is 15 double。



![](img/901819938fc25a39855358583152eedc_69.png)

In that case， we will be getting a value of 0。034 millisecons。 So that's the delay you are。

So this way， you can enable look。So。We have I have readily seen this flow monitor。

So flow monitor is a powerful tool。That。Identate the performanceance of。Chaapters pick up networks。

So。I have just demonstrate only a little little bit with the two different examples。

 one with the third Rcc example， another with the manner ro。So， please follow my channel。

The recommend to your friends。

![](img/901819938fc25a39855358583152eedc_71.png)

Thank you。