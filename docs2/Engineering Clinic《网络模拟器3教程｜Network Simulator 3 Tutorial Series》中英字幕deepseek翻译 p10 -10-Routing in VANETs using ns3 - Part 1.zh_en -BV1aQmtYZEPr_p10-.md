# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p10 -10-Routing in VANETs using ns3 - Part 1.zh_en -BV1aQmtYZEPr_p10-

Good evening friends， I am Pradip Kumar， welcome to Engineering Clinic。So today。

 we are going to see a topic on。We have that is wireless access。发了。V heicularar。Environments。So。

 this is a topic we will be seen so for that we will be using an example called us van compare。That一。

Okay， I'll just check with that。So we not roing compare， so this example we will be seeing today。

So this example will be seen today， it might take。More than an hour。More thanな数。The readers are。

Requested to be patient。So， so we have already seen one example on vannet mobility comparison。

 so using the NSS2 mobility software that we have tried it。

 so in this example we will be seeing this software so more。Then，1 it。And the ro comparison。

 rout comparison。So this is what we will be seeing。 so I will be defining these steps here。

 So first step is explain。The full source code。That is the first thing。The second thing will be。

Creating a。A real scenario。Using。Po isism that is open street map。Open street map。

Open streetreet map web Viizard， So this is what we are going to use here。

So in case if you want to install Suo， you can try it， I have another video， a couple of videos。

 earlier videos， it install Suo。And how to use summa basically that also you can use it。Then。

 finally。Performance analysis， performance analysis。Analysis。For various。Val protocols。

So this is what we'll be seeing this day。So the explaining the full source code。

 the source code is almost around 1500 lines， so 1500 plus lines of code。

So we need to learn it to the complete stuff so that's why it might take some extra time so the video might run more than one hour but I will be explaining the source code not line by line by block by block I will be explaining so that I can cover in a short time so after that we will do some simple exercise or experiments that can lead to the performance analysis of the managed routing protocols so already we have another example on man routingcompcc that already is there in my website in my YouTube channel so we can refer my channel in case if you want to download the source code you can try out。

In my website call us nnaaname。com so this is my website domain name where I will be sharing my source codes in this website。

 usually I share it through Google Drive and give the link of the Google Drive over in my website so I can download the source codes。

So over and above this， if you need any help you can always give a comment below the video or I can send it to my email address。

 you can see my email address in my about page of the YouTube channel。

So now we will go to the source code， So the source code location is。Location of the source code is。

Soce code this so we can see here。So C， SFC C， C examples。City wheel。Then see the examples。

 this is where this。I is there a source code。So， in my opinion， I mean in my home。

 my home is home Pradip Kmar and I have installed Ns1 3。27 and I have installed Ns3。

27 and inside the source folder there is a example colors view and there is a folder colors examples under that we can see the example file called as banner routing commandcc。

So to run this file first， we have to move this file。Move this file to the scratch folder。

Scratch folder for。Inclusion of all modules。So you can execute the same example directly without scratch folder but some models may not be included for examples network animator may not be included and there are some models that need some special direct permission so scratch folder have all these permissions so always move this file to the scratch folder okay now wave means wireless access forvehicular environments so this is what the name of wave so don't think it's something like a wave for communication so it is a wireless access for vehicular environments so it could be any vehicle a car or a track or a bus or even。

Bcycle or whatever we can say。 Okay， now we will go to the step number one， step one。

This two explanation of source code。

![](img/7b334764ebad78de243e4aaff84b4dab_1.png)

So now I'll just go to the new window， I only opened it。



![](img/7b334764ebad78de243e4aaff84b4dab_3.png)

So， these is open emit so you can see that I have stored in the file in the scratch folder。

 so this is to maintain that this scratch folder。I would like to run this example the scratch folder so we can see any example whenever you start there is a explanation given so most of the students most of the scholars I have seen they have have never seen this what is the blue colour the commenting line so they never see but of course we can see it now here。

So， this example proves allows one to run vehicleh attack network simulation scenarios in NS3。

 so it uses a Mac layer of 802。11 p， so there is a P layer is mainly for wireless vehicular attack networks。

And deuce proagation last model colors freeze propagation last model and two rayground last propagation on this ITp model。

An application traffic using basic safety message so this is the BSM they call in short they call it us bSM so this will be seeing the packet delivery ratio of the safety message we can see so between the cars between the vehicles the BSM messages can be transmitted。

The routing traffic is DSDb AWB OLS or and DSR so all the major routing protocols are being compared here so you can dynamicly change this value whenever you want to run it you can they have given a number there so the number you can correspondingly you can change it to run accordingly so by default it runs with the AWB protocol。

So here it uses a synthetic highway scenario that is a random waypoint mobility model。

Or by playing back mobility trace file so that N2 movement files only will be using。

 so we will be creating a dot TclL file and from this dot TlL file will be coming back here。

And here this script allows many parameters to be modified so whatever a scenario1 runs for 10 simulator seconds with 40 nodes moving occurring to random wave mobility model with the speed of 20 meters per second and no past time within a range of 30050 meters region the wfi is8 not to known with continuous access to 10 megaHtz。

Control channel for all traffic。 So with this， we will just go into the source code。

So we have can we can go through the complete reading of this file and there are so many CSV files are being generated。

So first thing is we have the headerophil， so there are so many models have been included。

 so we have a header file。And I have added one more vi network animation I will just show you at later how to see the animation and we have two name spaces NSSR and DS NSs3 and DSR so that is for NS3 by default and DSSR I will be using an agent so I am creating a DSR。

TheFirst first class is routing statistics， so for routing statistics for printing routing str we have get receiving bys。

Get cumulative receiving bys， get receiving packets， get cumulative receiving packets。

So you can see that an you 32 t means unsigned in desire 32 bytes so by 32 bits that is what it means unsigned in D 32。

So reading packets and increment receiving pi bytes， increment receiving packets， set RX bys。

 set Rx packets， set transcent bys， get cumulative trans bys。And packets。

 cumulative transition packets and increment transition packets， increment transition packets。

 and this is bys here。And set trans bys and set trans packets So all these things is dealing with so many functions colorss receiving a trans so increment the packets decreement the packet packets setting the packets receiving the packets and the packets separate and bys are separate so this is just to plot。

The various metrics and similarly we have a variables variable names also。So Rx bys。

 squility RX bytes， Rx packets like this。And everything is initialized to0。

 so this is the routing status is a class name， so we it is a conceptor。

 so everything initialized to0。Construct everything initial is to0。

 Now next thing is one by one function is getting implemented So R x bytes。

 so it is just returning it。And return cumulative bytes。

And you can see an increment bytes Rx packet plus plus cumulative Rx packet plus plus so you just see their variable name just added with the plus plus。

Then setting the bys so whatever value you are setting you can set it down。

So I think these are all very easy to handle。Now， next thing is we have a routing helper。

 so it just inererate the property from the object class。

 so the object is a topmost class or degeneerrating。Again。

 does type I routing helper and we have a constructor and we have a distractor。

And we we can install the particular node container net device container IP and4 interface container double total time what is a protocol number of sinks and routing tables so we have this many parameters now we can see that data is given there protocol is one means OSr2 means Avo DV3 means DSsDV and4 means DSsr so we have the numbers here so by default the value protocol in protocol this could be two means it will be for ADv one means a Osr and three means DSsDV and4 means DSsR number of sinks node act will act as a data sink and routing double dumb routing table at t5 seconds so0 is no and1 isS so thats what the routing tables so0 for no and1 for so just only we have two values。

And on off trace。 So tracing file many based run on and off。

Roouting statistics get routing statistics will Sun said lot so all these things we have included in a class call us routing stats。

and set up routing protocol and assign as so all these examples we have seen in fast rcc and second artcc that is also there the videos is there already you can refer this videos for for understanding the basics of this NSs3 there is a node application network net device containers then protocols then topology helpers so these things we have a first lecture on fastcc and second rcc can refer it。

So based on this， the net device container net device container， nothing but a network card。

And IP and 4 we are allocating the device and we are using the transmission interfaces。

Then routing messages so roing messages again， we are just setting up at the notes。

Then set up routing packet receive so we are ready to receive the packets because the main purpose is is bM as you showed in the bin is bSm and we have total simulation time number of protocols0 none1 wirelessr 2 A 3 dSGV and 4 DSSr and port number number of sinks。

The routing table。And routing statistics like this and we can see that routing helper is the routing table 0 number of the port number is 9 the protocol is 0 is 0 which currently additional。

Roing protocol is 0 and total simulation time is 300 seconds as per this。

And we are installing this so for each and every class how we are installing it。

 so all the implementation of the individual functions belonging to the routing helper class。

Now we can see inside say the setup ro protocol， we have object A DV helper， wirelessr helper。

 DDV helper， DS or helper。Ds are many helper， IP version  for list routing， internet stack helper。

Until time round trip time is five seconds after5 seconds the protocols will be the I mean。

 the road will be dumped。And we have a routing table file stream also。

 so we can be able to create a file stream on routing table and a case statement。

 So case zero for none case one for。OL Sr， case2 for Avo DV and case3 for DSSDb and case4 for DSsR。

And up to less than4 there is no use but for4 there is a separate DSR main because DSR uses an agent so we need to use the DSR main so except all other the protocol DSR is having having a different strategy so that is why we are using the same protocol number as 4。

Now next thing is assigning A address again this is also one of the function how do we assign the simulation from As is 1。

1。0。0 on this thing and this will be assigned to all the node here。

And routing messages so for the routing messages we are using UdP circuitet factory we have on time end of time and according the value will be from 0 to 1 that is on a probabilistic value。

So， that is what the routing receive and remote address also will be using it so we have start we are starting from 1。

0 to 2。0 and total simulation time already we have 300 seconds so starting will be from 1 to 2 maybe any time 1。

0 to 2。0 the simulation will start and the ending by 300 seconds that is what we have mentioned over here。

And how to receive the print routing packet so it will be received on packet from we will get the IPA so we see in the whenever this program is running we will be showing you that。

And receive roing packet。 so this also will be receiving。

And logging so how if you want to log the all the information that is for log and now next third class is wfi physical layer statistics so that is because we will be using wfi access for the vehicleicular environment so we need to use wfi also so for that we have wfi stats the name of the class which is inering again from object class so we have type I we have statistics for this and districtor for this。

And again we have1 bytes receiving bytes， drop packet dropping the bytes and all these things we can use it here So NS3 already provides a type8 colors wfi stat so we can use that so by default the physical layer transient bytes and trans packets are0。

And we have a tracing also。And dropping also。And class Wifi app。 so once it is done。

 then we have a wfi app class so this wfi app again， we have a conceptor the。And we are simulating。

 so this a sim is for argument count and argument vector。

And we have some function over here pars the commands。

 so we will see that how to configure the channels， how to configure devices。

 how to configure mobility， how to configure applications configure tracing run simulation and process output we will see one by one so we have a contractor and we have a distractor。

After then the simulations we have all these things so we can see simulate here so default attributes configure notes configure all the functions are being called one by one the default attributes not default attributes we have set so it is empty so we have to supply all the default all the parameters when the program is running on configure notes everything is empty now。

Unconfixt to our helper is next class。Again what kind of configuration you want to use you want to save the configuration so that means whenever you want to run a simulation you want to load the simulation value because every time you cannot supply a new set of parameters rather than you can store it and after that you can load it so that is the purpose of this config store helper class。

And you can see what is a file name that is to be stored and what is a file format RA format and what is a mode that is a load mode so these things we can able to configure it。

And save config how we can save it so this is for load confi and this is for save config so what are the three parameters we can save you can save using file name file format like this。

Now we will come to the next experiment class vner routing experiment but this is inering the property from Wifi app now we just think that this wfi app is already having empty functions here this function we are going to use it here inside this vner routing experiment so this is the main experiment that we have R seeing now we can see almost we have come to the thousandth line of this code。

So a bannerner routing experiment。So， we have default attributes passing the line commands。

 configurefi notes configurefi channels because these are all virtual function because already these functions are being implemented in in another class we are going to import this so we will be virtually importing this so that the child class the superclass subclass issues will not be there that is what is virtual so if you want to know more about it learn something about virtual functions in C++ so we can understand that。

Okay， so now we have done it。All these function we have defined set up part devices see along apart from the virtual functions we have some other function belonging to the bannerner routing experiment cluster series running wide run wide command set up wide check through put。

Set up log file， set up logging， configure default， set up a mobility node， set up a devices。

 set up wave messages， routing messages， setup scenario， right CSv header。

This year remains we are going right in a particular file。

And global is from config so what CSF I name you want to use create a variable name。

 so last model PHy mode 8 not 2。11 mode， so we have so many variables here。So。

 just to see that every variable there is a commenting line there so that you can understand what is the purpose of this variable in case if we have any issues and any doubts when you run this simulation maybe you can give the command。

Give a comment below the video so that I can help you on the particular comment。

Okay so and we have transitioncent safety range1，2，3。

4 up to 10 so because mostly we are using the safety messages only so the safety messages have a different ranges so what kind of ranges we will be offering so totally we are defininging a variable or 10 ranges。

Okay， and then now we have a round routing experiment that is tower constructor。In this contractor。

 the port number is 9。The name of the CSV file is van not routing output dot CSv and CSv file name2 is van not routing output2 dot csv we are going to create two files number of sync is 10 nodes。

 the total number of things will be 10 nodes and the protocol name is protocol transfu power is number 20。

Then trace mobility is false then the mobility trace is not been operated and protocol is2。

 so that means we will be using。We will be using。We will be seeing aW protocol last model is 3 again we have a2 ray ground model fading  zero last model fact I am not knowing about this communication part so those are from electronication communication branch or the school of communication Telegram you can just understand these things so Yfdm rate 60ps bandwidth 10 megaHs so that is a physical layer mode 8 2。

11 mode is 1 that is for one it is 80 2。11 p it is 0 means some other value。

And there is no trace file message。And we have lock file， we have mobility。

 we have a number of nodes 146 total simulation type 300， the rate is 2800 bit per second。

 2048 bit per second。The physical layer radio is d reless radio and the trace file name is when routing node speed is 20 meters per second node pass there is no passing time。

We have packet size is 20， 200 bytes wave interval is 0。

1 verbse maybe do you want a verbo or you don't want ver so by default it doesn not have any verbo so0 scenario is 1。

GPS accuracy is 40 maximum delay mill limit emit。Milliseconds is 10 routing table 0 as it is0 P cap load cont or text shall save con there is no file。

And safety range 5010 150 to like that， so incremental by 10 by 50。And that is what the construct。

Once the contract the default values， so the global value。

And trace mobility So these are some of the configuration item that has been already defined away in the wave of the wave models。

 so if you want to know more about this wave model so you can refer the source folder the helper classes so N S 3。

27 source。

![](img/7b334764ebad78de243e4aaff84b4dab_5.png)

Vi。And here we have。Helper classes， sorry， wave helper classes。

We have so many helper classes here and we have model。

So model we have so many files here so you can see VSA manager and we have Mac channel manager so all these things they just belong to one of these metrics over here so that what different here and what kind of fading it use what kind of Vrc mode it use see0 means a 211 a1 means a 211p。



![](img/7b334764ebad78de243e4aaff84b4dab_7.png)

Okay， so we have used one value over there， so that is a random viewpoint。Is one。

0 mobility mode 0 equal to random wave point one means mobility trace file。

And we as a number number of node vehicles is 1656。

 I dont know why they have used it and tried the weapon mobility model。

The node pass there is0 and size in bytes of wave BSM is 200。Packet size and we were both more。

 So these are the default values so packet capture do we want any wire shark files so by individual D value is0 so we are telling it is no but in case we want yes we can make it as yes。

 so let us generate that also。Okay， so then trans safety ranges 500。

This is for PD inclusion so packet delivery rate when the distance is 50 meters，100 meters。

 1 50 meters， 200 like that， so that is why we have up to 500 after that transcent power in DbM is 1 by5。

Total time is the total simulation time already 300 seconds。

And the wave B interval is wave VM and the accuracy of GPS。

So all these things have already set set after it is been set。We have the command line parsing。

 so which command have to pass what。And this is what we have been using this total number0 min range 1。

 two min range2， two min  three， three min 4， four min file like this。Then configure the nodes。

 So am 100 nodes that create the number of nodes so you can see how many number of nodes just and just copy this value。

And just check it here。What is the value。So a number of nodes is 156， so if it is 156。

 the number of nodes will be 40。So that's what somewhere it is given here。So totally 99。

 so somewhere we have given 99， so we have a different scenarios accordingly we have this scenario have been set up here。

Okay， so I think。发。Yeah， we here only we have stop andconfi the channels and configurefi the devices。

 so in the devices we have a transmission。呃。Physical aid and drop。

 physical level receiving drop these are three devices and configure mobility so we can configure the mobility and configure applications so we can set up the routing messages and set up the view messages。

Further， we have using the application layer application colors on of application。

Then configure tracing so right CSP enter setup block file set log and ask key trace S trace will be defined a file name called dot mo so already trace file name was their man routing compare will will be getting a dot means mobility file and run simulation we simply call the run function and process output so how to process the output so this is the value that will be getting the PdR value1 so gave wave BM states is a function。

Cumulative BM P so this also will be having a calculation accordingly according to the distance we have 5000150200 to 50 up to 500 we have this So for each and every valley we will be seeing it and if we can process that also I will just show you that。

Then total number of bytes it will be calculating a double bys by same and it will be calculating the total good put also。

So so this will be recording there so what is a BSM P there is safety message Pdr 1 safety message PDdr 2 so PDdr 1 means at the distance of 50 meters10 1502002 50 300350 like this up to 500 and it will be giving a value of a mag by P also so there is a good put it will give you apart from that it will give this value also this will be printed on the output in the terminal。

Then it will be printing the CSV file also then run so in the running the simulation we have run simulation function check the report。

Simulation total simulation time is totally 300 seconds on the run and destroyed so here will be manipulating something here so what I do is before the run function I will be creating an animation interface。

So that I can see I able to see the animation， so for now I will be using the filem van a dot X。

So this file I will be using for animation， so the ver xmal file will be for animation to run。

Under net anim so you can refer another video on how to create using net anim so that also I have just given in my video already so that you can try out。

So I that I am fast because I need to complete it within one hour。Because else it a。

 it's a boring thing if you want to keep on learning for the。It's a prolonged time， okay。So。

 and then we have vector position， so the position of the node that is and velocity the what speed the cars the vehicles are moving and it is at current what is the current location so further that we have a。

Roing is course change so we have e is 1。5 because it is at a distance of the antenna is at a distance of 1。

5 meters from the ground so that means you can think about a car which is a height of 1。

5 meters maybe the driver seating will be there the driver might be seating or people are seating just 1。

5 me above the level so that means the antenna will be working。Not at the surface of the road。

 it is just 1。5 me above the。Surface of the road， maybe from the drivers seat or are from the seat。

So， that is what here get ID the id of the node and the get seconds and what time it is there if t on greater than our equal 1。

0 get nodes moving because we have start the simulation between。

1 coma2 you have starting the simulation maybe one co2， so that means after 1。0 only。

The nodes will be started moving， so that' is where we have to get it up to  one， it is not。Okay。

 and then it will be per displaying the value to the。

Pos velocity x y is that will be displaying that so this will be displayed to a particular mobility file。

Next thing is we have throughput。So throughput how we are calculating the throughput。

 so we have a various formula over here， so using this formula。The throughput will be calculated。

Okay。So the throughput will be displayed somewhere。

So it is given us out only so anyway we will be checking the throughput also。

So once the throughput is done， then we have con from globals so in are double string values。

And how to deal with all the values So that is given over here。

Then again these are all config so we are not going to use the config anyhow and the command setup so the command setup here is the CSc file name total time all these thing these are the command setups so these commands we can able to run when the simulation is running so we can use a command dot。

W。You can use the total time， so in case if you want to configure total times we are given us 300 seconds。

 but in case the 300 is very large time you want to reduce you to lets say 10 seconds so in their case how can I use 10 seconds so you can use。

Dot wave runs scratch the file name and within double hyphenon total time equal to 10 you can use it so that means the simulation will be running just for 10 seconds。

 Similarly if you want to configure the number of nodes you can use this so that is what is command indicate so you can low command lane over it so that means doing the well command lane。

Can overrriide the constant values， the default values。 Thats what here。And press mobility。

 let's say I want to use the protocol。Is A D， Okay， so maybe I'll just show you that。And last model。

 so for all these things， we have a command over here。And once it is done。

 then we have setup block file and setup logging， so we have N2 mobility helper logging。

Enable printing， so it will be printed there and printing packet says， other stuff。

And set up mobility nodes， so mobility uniform random variable we used random box position allocator。

And we have used a random waypoint mobility model so that is what the speed and the past time speed is 20 meters per second past time is0 and the position allocator is given us random box position allocator so that means carsis has a whole body it has to be placed in kind of a box kind of stuff so thats why we use random box position allocator so there are various position allator also available。

So this simulation uses the random approximation position like it。Then last model。

 so there are various last models like this fri propagation I are2 grey ground and this model。

 so we have one means fri propagation two means this three means this in case if you want to do some vehicular network with the。

Communication last model is you want to compare a last model for the regular network then you can use this same example only thing is keep all other keep all other default values and making only these four will to vary。



![](img/7b334764ebad78de243e4aaff84b4dab_9.png)

![](img/7b334764ebad78de243e4aaff84b4dab_10.png)

Lug distance propagation model20 ground and I R 1411 pre propagation so that we can have a comparison of how the network performance varies according to the different last models。

Okay， then frequency mode， so what kind of frequency mode this has。

And we have frequency 5 by 9 return power9 that is 5。 9 gigahHtz for 802。11 p for b is is just 2。

4 gigahHtz so you know2040 megahertz that is what 802。

11 b and will will be using this P also so in case of comparison you can compare B and P also so。

This also can and we have wes I channel helper there is yet another network simulator ya yas we have a constant speed propagation delay model。

And the frequency value。And the channel these are the channel parameters or channel properties of the physical layer。

And the wfi at what rate the wfi is supplied so it is concentrate rate wfi manager so irrespective of the distance of the node the rate of wfi supply is at the consent rate。

 so the rate does not change。And the mode so whether you want V Mac or you want Wifi 8220 on P Mac or simply Wifi Mac。

So this thing， Im gra a trace field dot Tr file。And we have a banner routing compare pickupup so that we have a peak packet capture file that is for wire wire shock we already make it as one year if the value is0 order there it won't generate if the value is 1 it will be generated so I have given already the value  one so it will be generating and setup scenario。

And what scenario you want number of node is 156 it is 40 total simulation time if it is 30 minutes you is 10 okay。

 so there is 4 m scenario number1。Else， number number two。

 we have number of nodes 99 total emission of 300 node speed0 select this。

 so they have given a realistic regular trace in 4。6 kilometer 3 kilo suburban zero。

Load engine anti internal vehicles for this thing。They have a 300 plus thousand00 synthetic highway 10 seconds so we can see what kind of things we have used it。

And writing to the CSV header， so what are the values have been returned to the CSV header。

 so this is what will be returned there。And finally， close。

So when routing experiment experiment experiment or simulate argument count or given vector so from this the simulation starts。

So let me save this file。Okay， friends back。

![](img/7b334764ebad78de243e4aaff84b4dab_12.png)

So now we will be running this example， So what I do now is I will just go here。And。Yeah。

So explanation is done。 so now copy the file to scratch folder。



![](img/7b334764ebad78de243e4aaff84b4dab_14.png)

So now what I do is sell us， so C1net。From take a back。

So you can directly copy or you can directly use。The folder。

 the commander you can directly use through Gy to copy the file。Yeah， and three was scratch。

 So I'm just copying this， so it's copied。I will come to the Ns 3。2 zone folder。

 Now now we are in this folder now。So we are in this folder now。

 so from this folder we had to run the command in the back。AA front run， scratch。We a ro copper。

 So this is a simple example that we be doing。Now we can see it is A only showing only A DV。

Because the number is given us2。No， I will just I will be changing this number to something else。

 I don't know till what time the simulation will run。

The simulation will be running only for 10 seconds we have already is given a scenario number one。

So now number two will be running for 300 seconds。And let us show you how to process these data now you can see BSMP 1 for 50 meters。

 BSMP 2 for 100 meters， 150 meters。200，250，300。3，50，400，4，50 and 500。After the good put is 2。

8 kilobits per second and Mac the is this value。So what we doing is what we will be doing is。

This is the example。So now in the same example， what I do is to run this。

 I will just minimize the command。One size。So， what I do is。

Scratch cannot compare within double go space。Then protocol name protocol equal to number one，1 is4。

Olesser now we can see that the same example I am running。Now。

 can you see that the value have been changed to orr。

So that reds that so in the same simulation I can override。Of the number of node。

 I didn't mention anything about the number of notes， but again， still use that。Okay， so there again。

 the time is far this much。And again you can see the goodput is 5。

17 only for while lessr for Mac it is this value and basically BM P this thing will be vary for each and every protocol so you can compare four different protocols for this and again protocol number 3 I will use it。

This is for DSsDV。So in the DSDV， we have again。AndLet's see what is a good put at the end of it。

You can see received on packet from the I address， so the I address is the eye address for each and every vehicle。

Okay， so now the goodput is for 10。9568 at the end of the thing at the end of the 10 seconds。

 Now finally we have number four。Our first days are slightly different。But anyway。

 that is written in the code， so DSR handles。So I think among that oil laser was slightly faster than compared to the other three protocols。

 let us see what is。Good put for radi is or protocol。So goodput here is 14。8 for it。

 so the goodput is very good for DSsr when compared to the other three protocols okay。So again。

 I can give0 also zero means no protocol。So this is how the way we can able to overwride。This thing。

 so you can see there is no protocol， so no routing。I mean the cars are not exchanging their packets。

 they simply run with the number of timing， so you can see the goodput is0 kilobits which say second everywhere it is 0。

So， that means it doesn't take。Any good any packet attention doesn't happen that what is no protocol。

So， this is one example now we can see what are the files got generated so the file got generated is vner routing compared that mobility vner routing output 2 or vner routing output do c3 vner or Xml。

So this is a one Xml file， so what we do is we will be running in thetanium so dot dot slash。

Let an name， so it will go to the previous folder。

![](img/7b334764ebad78de243e4aaff84b4dab_16.png)

The file name nettanium， it opens a nettanum window。Open it the name of the file is when at X。

 I already created it。So it takes some time and then node size I just make it to 10 so that you can see the node size。

Even I can make2 tea also， so actually these 20 they have given us 300 across  thousand500 simulation that they have given。

But if you want to change our own map， let us say if you want。

 if you are living in some particular place， you want to do a real time mapping。

You can take the values from OM maps and then you can make use of that。You can see that。

 So this is a network animation that is shown。The packet exchange between the cars happened here。

So you can， even you can zoom also， let me zoom it。So。

 this the zooming so you can see from the x axis here， 0 to 300 here。

 the way axis and 0 to 000 is the x axis。So， this is how the way the packet exchange happens in the node so I will increase the size of the node of 20 that is。

Mac filmfl。A number of lines。Just only three legs。So this is a simple simulation that。

 but now the time is just only one second。If you want to have a faster simulation。

 you can see faster。The time also will be running very fast。 So again， this increase hit。

But still more。Because we exit it up to 10 seconds。

 so it will be showing you and the packets information that also will be shown here。

And the statistics about a particular note will be shown here。

 so you need to have a reasonably a good processor machine。

To handle the such a huge packet rate hill your machine might be hanging。

 so I have a solid straight drive here still it is hanging。They can resist it。

And I you don't look it yeah。So even though I have a solid straight drive still the machine is hanging。

 so you need to you else don't go for any network animation just to show the how the network animation works。



![](img/7b334764ebad78de243e4aaff84b4dab_18.png)

That's what I have given it here。We， I just close this window。Now。

 the last one is because using this， we can able to process so many things here。

 So maybe what I do is Ill stop here maybe in the。Next version of my video。

 I'll just continue with the。Processing of this data。So this data will just open one by one file。

 so what it contains。So， G。One at routing。Compare dot mob so is for mobility so you can see then mobility the node number 0 what is a position that is one for14。

34 do66 why access this is that access this and velocity it is not moving so maybe because after 1。

0 only they will be moving。

![](img/7b334764ebad78de243e4aaff84b4dab_20.png)

So that is how it was programmed， so that is a mobility here。Then next to file is。

Wner ro output dot CSv， so this is a CSV file。So， we have various simulation against receive rate brackets received number of sinks。

 the routing protocol， the transmission power。Wave packets send wave packet received wave packets these things。

 so you can see so many metrics are there， so can me the values are being generated here。

So these were totally 10 seconds， so the values are generated according to the second01，2，3，456，78。

 nine10 so totally for 10 seconds， so if you want bigger graphs you can able to generate for more than 10 seconds。

The second output is the ES sum。BSM Pdr。 So this is for。The BSM therefore for the various values。



![](img/7b334764ebad78de243e4aaff84b4dab_22.png)

So there is an exit thing have。And one more file is。So mobility file when at Xml is what this and。

Roouting table。 So nothing was。That。And。Okay， so thats all so maybe in the second video I' will just tell you how to process it and plot some various。

Characteristics， I already tried it。 Maybe they show you that so that。The next example。

 we will see that。So we I have plotted the flow matrix here。



![](img/7b334764ebad78de243e4aaff84b4dab_24.png)

So a number of flows flow bit rate number of flow packets and delay in seconds。

 so that is what I plotted here using the flow flow monitor， so there is a tool called flow monitor。



![](img/7b334764ebad78de243e4aaff84b4dab_26.png)

A powerful tool in NS3 for。

![](img/7b334764ebad78de243e4aaff84b4dab_28.png)

Xl file based research analysis so that I will be carrying out in the the part two of this video。

 so I will stop it here。So thanks for watching my videos。

So please subscribe to my channel Engineering Clinic。Any queries， any doubts。

 you can always comment me。So this is just part one。Part one of these。

F00 comparison because I have not done the sumo part。

 so sumo part again another it takes another 15 20 minutes to do。And we have analysis also。So。

 part one。So thanks for watching。Wait for the part to video。Wait for part 2。



![](img/7b334764ebad78de243e4aaff84b4dab_30.png)

Thank you。