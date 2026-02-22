# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p19 Lecture 18_ Emerging Memory Technologies (Spring 2025).zh_en -BV1Xc19BnET7_p19-

![](img/9d957a701b0acf81890f56d4b01a0258_0.png)

So in this lecture， we're going to discuss a little bit about what are these emerging memory technologies。

 some we're going to see some case studies。And。Techniques that we have developed and other people have developed to enable these technologies。

As we also discussed in the past like D we showed a lot of scalability issues for D and it's true that we need to work on D and make it smarter like using you know intelligent memory controllers such that you can push the boundaries and make D better and better。

 but at the same time it's also good to think about。

Other tech memory technologies that they can potentially replace data or some other also memory。呃。

Memory， basically modules， not only data。So if you think about flash memory。

 flash memory was also emerging memory technologies in the very， very past， I'm actually not very。

 very past like me。嗯。Yeah， in 1980s。Back then， basically。

And people have a work on it to make it work。And there were also a lot of people that were quite pessimistic about this architecture。

But at some point， all these research and development that people have made that paid off。

And now flash memories are， I would say， one of the。Key reasons that。

 you know we all can have these smartphones in our pocket。Otherwise， how can I carry， you know。

 a smartphone that has， for example， hard disk， you know， and is's going to like rotate in my pocket。

 you know， it's just impossible， right？So we're going to actually have a very thorough lecture on flash memory and solid the state drives next week。

So stay tuned for that。But today we are going to also look into more， you know， memory technologies。

Like they are still emerging。So flash memory is not considered emerging anymore， I would say。

 so it was emerging in the past。Okay。So we discuss a lot about limits of charge memory， let's just。

You know， it a very quick。Remindder to jog your memory。

So we have difficult charge placement and control in flash memory we have a floating gate and you need to control the charge in that floating gate。

 we're going to learn about background of flash memory in detail actually next week so I don't want to spend much time today and for data also we have this capacitor that you need to store charge。

And essentially there is this transistor leakage。In flash also， you have some leakage。

It's not that fast as data， so in Dm you need frequent refresh。But in flash memory also。

 you need to do refresh at some point。So if you， for example。

 store data on your flash memory and don't touch your flash memory for a few years。

It's very unlikely that you can recover your data。Nicely。

 there might be some data that you cannot even recover them at all。But fortunately。

 our flash memories are implemented and are integrated into SSDs now。

 and SSD use a quite intelligent controller。SD controller and flash controller and those controllers actually you do a lot of intelligent stuff to make flash work。

But we're going to learn about them next week， hopefully。Okay。

 so reliable sensing becomes difficult charge a storage unit size reduces and that's quite understandable so when you want to scale it down。

 they're going it will get smaller and smaller and at some point you cannot do re sensing because you cannot reliably store charge and you cannot reliably sense that charge。

So that's why these architectures have fundamentally have basically。呃。Scaling issues。

We discuss about different solutions like the solution one was the newme architectures that we want to overcome memory shortcomings with memory centric system design。

 for example， novel memory architectures， interfaces， functions， better waste management。

That for example， you have seen in our latency work， you know that。

We don't need to design always for divorce caing you know and also for the voltage。

 you know we we or for refreshing， for example。So there are some key issues to tackle and we actually tackle many of them in the works that we have discussed in the past few weeks。

Like to enable reliability at low cost， reduce energy。

 reduce latency you have seen a lot in our lectures， how to improve bandwidth， how to reduce waste。

And enable computation close data there are there were also some works that we didn't discuss like compression。

 for example， we didn't discuss memory compression that you can compress your data to improve your effective capacity and that can be quite useful in order to provide let's say。

you can utilize your current memory capacity for more data。

 and that can actually solve some of the basically push for more scaling and skill because one reason to do more scaling and scaling is to provide capacity。

 provide density。But sometimes by using this compression， you can， for example。

 you can with the same capacity， you can store， let's say， four times。You know， larger data。

And these are some works that we also have discussed some of them in the past weeks。

But now we want to focus on solution two， which is emerging memory technologies。

 there are some emerging resistive memory technologies and they seem more scalable than Iran and they are also non。

Remember that D is volatile5， meaning that you need to have it connected to the， you know。

 the electricity to keep it charged and you also refresh it。But these resistessive memory。

 they are no volatile， so they don't need electricity to keep their data。

There are some examples here， one， like face change memory。

Data is stored by changing phase of material。There is this material here。

 which well see about it in a few next slides。But basically。

 depending on the phase of this material that can have two phases， Omorphphs and crystalryline。

You can consider like zero and one， you can decode it， encode it to that。

And data read by detecting materials resistance。This actually PCM has been developed in。1960s， 1960s。

 if I'm not mistaken， and this has been actually used in。Reritable cities。Because these these PCM。

 like the material also has。different。呃。Light reflexes。

So if if you shine light on the material and depending on how the material reflects that。

 you can actually encode0 and1 and that has been used to write Cs and basically rertable C。

 Of course， thats that's not a fast writing or programming and reading process。

But that has been used for retable cities， but later on， people have worked on it and realize that。

That phase of material can also cause resistive memory and that can be also translated to electrical current and people design some circuits。

 some sensing circuitry， if you will， and based on that circuitry。

 they could decode the state of that material， and they can encode it to zero1。IBM for example。

 has done a lot of work in this area Intel and other companies have done as well。

So this is work one of the earliest work， I guess， from IBM。

Which has published in IBM Journal of Research and Development in 2008。

And they design a prototype of PCM at 20 nanometer。

 And this is also quite interesting that you can see that。This prototype in 2008 was in 20 nanometer。

 while Dran technology reached to that around the 20 nanometer in。2015 or so。

 so that showed these architecture are easier to scale， this is Ki。

And when D Im also reached to that 20 nanometer scale， then you observe more issues as well。

And it's interesting that these architectures are expected to be denser than DM as well because they can store multiple bits per cell。

So here in my example， I said that you're resistive， you can encode it to0 and1。

 but if you chop that resistive window into， let's say， four regions。You can encode it to two bits。

 for example， or if you chop it to eighth region， you can encode it to three bits， for example。

 of course， at some point it might not be reliable。But this is possible， and people have done that。

 for example， flash memory that we're going to see later。However。

 emerging technologies have many shortcomings and the question is that can they be enabled to replace。

Which is quite hard to achieve。But augmenting and surpassed theorem might be easier。

By augmenting to Dran might be easier， but basically this going to be the topic of this lecture that we're going to see and we're going to actually touch on upon all these techniques like。

For example， can we replace DM completely with PCM？Or can we， but augmenting。

 can we do use PCM and Dm together or can we use some。So， there are some also。

Characteristics of these technologies that they are not available in Dra， for example。

 as we discussed these architecture， these memory technologies are normal at， that means you can。

 for example， use them for persistent memory。Currently， when you have persistent data。

 you always need to rely on your disk or SSD， essentially。But if if you have a main memory。

 which is normal et， you can also consider that as a persistent memory and you can program that and use that as a persistent memory。

 so that can actually improve the performance for many database for some applications， you know。

 because you have much faster access for persistent memory。



![](img/9d957a701b0acf81890f56d4b01a0258_2.png)

Yeah， we're going to see a lot about these topics and here are some example works that we're going to also discuss today。

Not all of them， of course， but。Yeah， so industry also looked into this architecture。

 and this was one of the architectures that was commercialized。

Intel obtainedane persistent memory in 2019。This is of course non my memory based on 3DX point technology。

 they call it 3DX point technology， but if you really look into the data sheet and learn papers about it。

It's essentially very much similar to PCM。诶。Yeah， but。They equal 3D point。

I'm not sure if it's still available to buy because Intel put this obtained out of the business。

 but in the past it was available。Maybe it's still available to buy， but not sure。 Does anyone know。

Yeah， but back then was also quite expensive to buy。

But people have bought these thems and they put these thems to their computers， for example。

 as a replacement of the D for example， and they have done a lot of research on them you know to how they can help。

But that's good that we are also observing movement from industry to for these emerging memory technologies。



![](img/9d957a701b0acf81890f56d4b01a0258_4.png)

This paper is going to be one of the main papers that we're going to discuss today that we want to discuss how we can architect face change memory as a scalable DRA alternative。

 so here we are quite aggressive， so if we want to just replace D completely with PCM and then we want to see how it works and then if it's not if it's not good。

 how can we fix it you know shortcomings or how can we eliminate them to make it happen。And yeah。

 so if you want to learn more also you can check this， but we will also discuss this paper today。

So now let's also get before going into too much detail。

 let's discuss a little bit back about charge versus resistive memories。

 So in charge memory like data and flash， you write data by capturing charge。

And read data by detecting voltage， essentially。In resistive memory like PCM。

 SATTM brand that you're going to see later and memory store that you're going to also see later。

You write data by pulsing current。And you read data by detecting resistance R。

 so that's the main difference。There are promising resistive memory technologies like PCM that you inject current to change material phase and resistance determined by phase。

In STTM Ram you inject Cor to change magnet priority， so in STTMM you have a there is a magnet。

 quite a small magnet， you can call it that nanomagnet， let's say。

And resistance determined by polarity of that magnet， essentially。

Memory store RM and Rerun that we're not going to discuss a lot about them today。

 but they also have similar basically fundamentals， I would say， similar like approach。

Like you inject cor to change atomic structure and resistance determined by atomomic distance。

 basically。呃。Basically， you can change there is a way that you need to。

 you can change or determine resistance， and that's the key difference here。

That provides a lot of good things because。Resistance as we discussed， is novelat。And。

For resistance you can actually fundamentally you can basically scale it down easier。

 but at the same time also provide some other issues like when you want to inject current and change these colorrate for examinationTM change magnet polar or in PCM change material phase。

 essentially you need to spend a lot of energy， a lot of temperature and those will cause a lot of issues that we're going to see。

We will start with TM， what is face change memory？Face change material。Is the。

Citegonite glass exists in two estates， omorphs， which is a low optical reflexivity and high electrical resistivity。

And Chris Stalin which is high optical reflexivity and low electrical resistivity。

 so we already discussed that using these optical reflexivities you can actually use that for reritable CDs。

 but now we are more interested in you their differences in electrical resistivity。

So this is the PCM material that you have essentially， this is the。

The material and this is the heater and the metal， which is the axis。

 like this is the like the access transistor here。And you can consider your resistance here as a variable resistance that you can tune the resistance by that。

So PCM is a resist memory and in high resistance you can encode it to zero， for example。

 and road resistance， you can encode it to one。And the PCM set can be switched between states reliably and quickly。

 but that quickly， we'll see it's not that quick。 It's not as quick as， for example， datara you know。

So how does PCN work then you want to write？You need to change phase via your current injection。

So there's two basically fundamental operations set and reset。For set， you need to sustain accor。

B this。You need to sustain current to heat cell above a temperature like crystalline temperature。

So you provide the。Current and you need to keep it sustainable。

Such that you can heat up that material above the temperature for krisalli。

It's very important that you need to do it longer time， so that's the main difference here。

For reset operation， you need to you basically inject quite high currents。

 so cell heated above melting temperature。And you quickly quench it。And that can cause。Basically。

 you can get to Omorphfu essentially state。And then for reading。

 you need to detect phase via via this material resistant like you're in Omorphus or crystalline。

Interesting thing is that when you do set and for crystalline， you will get to。

The resistance of 1 k to 10。10 k oh basically， but in the omorphous estate you have high resistance and this is quite a lot like one mega around or 10 mego so you can see clear difference between these two resistant state and thats a huge difference is important in order to make it possible that you can read you know reliably from these memory。



![](img/9d957a701b0acf81890f56d4b01a0258_6.png)

So there are some opportunity that PCM provides like it scales better than Dham flesh and flesh。

It requires current pulses which scale linearly with feature size。

And is expected to scale to9 nanometer that's a report from ITRS in 2022。

And we have even prototype at 20 nanometer from IBM。I love work。

And it can be denser than urine because first of all it can actually scale down better。

 but also it can store multiple beats per cell due to the large resistance range there are some prototype with two beats per cell。

Like in this paper， in this conference， ISSCC。And four beats per set in another prototype in 2012。

But there is， of course， a trade of itminda so when you increase the number of beats per cell。

So you observed that you had quite good difference between resistance value， right？

So it's difference is quite large if you consider you have only twos。

But if you want to chop it down to four states， then the differences is not that huge。

If you want to chop it down to 16 estates in order to store four bits， for example。

 then your difference is not that much， and then the problem is that your cens secretary needs to be quite accurate。

To detect the differences， basically。Any question， yeah。在。Like how expensive？Yeah。Yeah。

 here also iss not。Yeah， I cannot say it's cheap， it's expensive， of course。😊。

But similar to DRA like the overhead can be amortized when you design a main memory because you are shading that circuitry from several you know for the whole array for example。

 so if you want to have several many small emerging memory technologies you know and puts all these sense in circuitry for all of them then yes the overhead might be actually huge right but as long as you have sense in circuitry and you are using that for a quite you know big array。

 then you the cost can be amortized。It's very similar to the， of course also。

I don't really have that。Number or on top of my head。Any other questions？Okay。

But that's very good questions。Yeah， and PC is also novel high。

 it can retain data for more than 10 years at 85 centigrades。Which is quite good。

So without refreshing the PCM， the retention time is greater than than 10 years。No refresh needed。

 low id talk。So here we will discuss that how we can chop this resistance value like1 and0。

 we can have chop it down to two， we can also have multilevel cell PCM as we discuss。

 and you can chop it down， for example， chop this cell resistance window to four， for example。

 here you are storing two bits per cell。Then of course。

 you have less margin between values and need more precise sensing modification of cell contents。

Higher latency and energy and two times for reads， for example， and for times for rightss。

So compared to SLC， like single level cell PCM here。

 you need to spend more time and more energy in order to read and write， essentially。

 is which makes sense， I guess。Does it make sense to you as well？Because you need to control it more。

You know。So phase change memory properties， we wanted to learn about PCM properties and we did some survey prototypes。

From 2003 to 2008， from different conferences， including ITRS。嗯。Electron devices meeting。

 for example， VLSI and so on and so forth， and there were some people that they were working on that and they were designing prototypes。

 reporting characteristics。So we look into all these numbers and we come of。With this table。

 essentially。So you can see that like， for example， there are some prototypes that you don't need。

 you don't know much， unfortunately。So there are only like this set time。

 which is like 100 nanoseconds。Like the set current， which is 200 micromper。

Reset time which is 50 nanosecond and reset currentth。

 which is 600 micronmper and also of course you have this right endurance。

Do you know what is endurance， we're going to actually learn about it。

 but it means that essentially how many times you can write to your cell。Pliably。

 so if you if you have if you for examine this prototype。😊，If you write to that PCM cell。

 more than 10 to the power seven。Then you can think of like that that your cell is going to be dead。

 basically。There are different reasons for that， and sometimes。Your cell is not dead。

 but it's not reliable。Then that means in order to avoid errors you need。Much powerful， let's say。

 ECC thing。And that kind of cause a lot of issues。But there are also some memories that after this endurance。

 theyre completed dead， for example， they have this stuck at zero for example。

 so every time you access it， you will only read zero for example， you know。

So endurance is actually one of the unfortunate issues。🤧On of all these。Emerging memory technologies。

 unfortunately， and you can see that endurance for PCM like the survey that we had。

From different works is ranging from 10 to the power of four。Which is quite pessimistic。

 in my opinion。To10 to the power 9 or so， it seems。A bit optimistic。So yeah。

 so you can see that basically when you want to do research on emerging memory technologies。

 you don't know much unfortunately， so there are we look into many reports。

 many reports from prototypes。From industry， from academia。And we wanted to just， you know。

 get some numbers。 but you can see that essentially these numbers are not also consistent much。

Because sometimes people have used different methodologies。

People may have design actually different sense in p circuitiatry。

 so the sense in psiatry can be also different。So how are you going to use these numbers？So yeah。

 that bring me also to this part of， you know， the doing research in emerging memory technologies or emerging technology。

 essentially， it's not easy and you always need to make some estimations， you know some guess。

And working on a range of parameters is always a good idea。

 so it's very hard to pick on one parameter or say that the latency of PCM is， for example。

 four times longer than data。That might not be the very good decision。

 So it better that you consider a range， for example， you know。

 and you show the sensitivity of your design when while you're varying this this。This parameter。

 for example。Okay， let me discuss about this few next and then we can take a break So where can PCM fit in the system。

 we have this main memory caches and storage。We wanted to replace it as a， I mean。

 consider as a main memory if youre look into this。Blot here， like this scale。

 you can see that the X axis is the typical axis latency in terms of processor cycles for a four gigahHtz processor。

So for example here， L1 cache is here like the axis is around two cycles and we have last level cache and main memory system。

你啲啦。And and also disk。So you can see that between Dam and hard disk drive。

 we have quite a lot like gap and that's why actually flash found it's very nicely， you know。

 so flash filled the gap nicely between hard disk drive and Dam。

So now the question is that how PCM can find this way， for example。

 so PCM latencies are close to data， but not as good as data。So， but yeah， in this work。

 we'd like to see how we can。Use PCM for data。Red latency of PCM is around 50 nanosecond。

I mean using all these study， for example， which is four times longer than Iranran。

But it's faster than non flash memory， for example。Right latency is around 1150 nanosecond。

 which is 12 times longer than the。Right pan this is also。Lower than the。

And it's similar to N flashlash memory。TheDyna energy is unfortunately is also higher than Dam。

 like two times， I assume two times is for RE。So read dynamic energy for PCM is two times of the and right dynamic dynamic energy you consume for right is 43 times。

Lger than地人。And dynamic energy is similar to N flashlash。And for endurance。It's like。

10 to the power minus eight times of D so for Dm we don't know actually endurance because there is no report for that we don't know actually if Dm has endurance problem。

 at least we haven't observed endurance problem of Dm。Until we use our system。

 at some point you also you just fill out your whole system as well。But Di also doesn't， I mean。

 at least from what we can also see， the architecture doesn't have that kind of issues that can cause endurance problem。

But in PCM， clearly we have that problem。But as a good thing， cell size is better than the。Basically。

It's denser。And you can also scale it better。With using M and C。Technique。Sorry。

 actually cell size is larger， cell size is larger than the number it's not that larger。

It's also larger than non flash memory。But you can also scale it better with feature size and using MC technology。

So yeah， the takeaway here is that you can see that it's very unlikely that PCM can replace Dran because there are many shortcomings。

But yeah， let's conclude again about pros and cons over the。

 like the pros is that we have better technology scaling， as we discussed， we have non volatilityat。

 persistent memory and low id power， so we don't have a refreshing issue。

But we have higher latencies， higher active energy and lower endurance and reliability issues。

So we don't， for example， have。呃。Issues like。Like Rohamir， for example。

 you know that you have this read disturb disturbance， for example。

 is not but you have similar other issues here as when in PCM that accessing your PCM or memory at some point can cause some resistance shift so your resistance window can shift and if you don't update your references you're going read basically wrongly and that's also the case for flash memory and that's why we always need to update our reference voltage in for flash memory as well。

So there are challenges in enabling PCM at DM replacement。

 so to mitigate PCM shortcomings and find the right way to place PCM in the system。

So here are different example like this system can be like completely de。

 this one is most likely the way that we're going to have a PCM in the future， probably if we have。

It's going to be kind of hybrid that you have both Thetum and PCM。

And also a bit like more aggressive solution that you completely replace D with PCM。

So this work that we discuss we will discuss today is actually consider this hybrid solution and this work that we're going to also discuss consider completely replacement of data。

And that was one of the initial study that we want to replace D completely with PC。Okay。

So before going into this paper， let's have any question before。Yes。😊，Yes。So you have some circuitry。

 right， sensing circuitry and those are。You know， see space probably or whatever。

 so they also consume some over here。Any other questions， I mean。

 that that's one reason I can't think of， but can be also other things。Okay， so let's。

Take a break until。2，35。 so we want to completely。Replace the Iran with PC in this work。

And here all the numbers that we consider like for the latency is like four times。

Higher lead expectancy，12 times longer， write laancy， energy is two times。

For read and 43 times for write and endurance is also 10 to the power 8。

 So these are the numbers that we come of。From all these surveys。

And we did some simulation that we basically replaced the with PCM in a four corere4 megabyte L2 system。

And PC organized the same as DM， so we consider that basically PC is designed as architecture is completely like the D like the robot of banks prefer out everything the same。

 but we just consider that okay when you access that cell you need to spend more time you know all the time so at the simulation level you can do such things。

So the long story short is that results are not good。So we have around 60% longer execution time。呃。2。

2 times energy。Higher energy。And 500 hour average lifetime。And this is actually average。

 there are some applications that。Basically， the lifetime is even much lower， like for FFT。

 for example。And there are some applications that delay like this is also 60% is on average。

For some applications， our performance overhead is much more。

So the results are not good and that's kind of we were expecting。

 you know by just replacing all these numbers， you cannot get good performance of course and good energy。

 but now the question is that can we overcome these issues and we look into it？

So this paper have discussed different ideas that we don't have time to look into it。

 but I'm going to only。Showcase two idea of that paper。

 the first idea is that we can use multiple narrow row buffers in each PCM chip。So in Dam。

 we have a big sense amplifier because while you're reading from Dran read operation is this。

Disrupive， right， and you need to this sense amplifier to do this charge illustration to make sure that everything is correct。

 but PCM。Doesn't have that issue right So you don't need that sense amplifier to be as long as big as the whole array。

 the whole like the row of the data so you can actually have a smaller size sense amplifier。

And with that， you gain some area。Like area budget。

 And you can use that area budget to add some latches， some buffers。

 And with those latches and buffers， you can essentially。

 you can hide latencies so they can act as your cash， if you will。Make sense， yeah。不。Yeah， in PC。

 we don't need basically send splifier as as big as the whole row so you can just。

Put the sense amplifier for a few blocks or whatever that you are reading。You care at that moment。

Yes是。Yeah， it kind of comes into， yes， less robot for locality。Yeah。

 but you can do that consecutiveive of time， right？就。There are different ways。

So you need to basically， you know， fill up these latches， you know。

 you can fill up these latches and these latches can be filled up by the。By this。

Blocks or words from the same role， you know， by reading， you know， conly into the time。

 or you can actually fill out these lecturetches from different roles。

 So that's a key difference here， you know， but indeed， you cannot do that at all because。Yeah。

 so essentially that's since Iplifier shoot， although there are some new Dm architectures like S or Dam that Atobviic has published recently。

That you know， by redesigning D architecture， you can actually also implement some。

Lower granity access。But in general， it's not easy indeed。Yeah。That's a good question。

The second idea is that we want to write into array at cash block or word granerularity。

So you don't need to。So in DR， when you want to write。

 you write to the same sample first essentially， and then you need to basically weight such that that value。

 which is in that right buffer should be restored in the DM row。But here in PCM。

 you don't have to basically， you know， update the whole row。 You can only update。

The part that is that is different。 Maybe you only change a byte， you know。

 or two bytes or a board or a cash block。 So you'll only want to update that。

 And that can essentially reduce a lot of basically right cycles。

 Remember that we have this endurance issue。 So with that you can reduce a number of rights。

 There are actually some works that they also look into it a bit even more aggressively。

 and they want to control individual bits。 Samsung has done also work that。

And so essentially whenever you want to write， you only update beats。

 you only write to beats that they are different， so you capture。

 you read the what you have and you know what you want to write and there are some differences and you only program those differences and that can essentially reduce a lot of programs。

So these two ideas by implementing them， you can get like。

Performance improvement compared to the baseline that you had。

 but still you're increasing the execution time by 20%， your energy consumption is on par。

And the average lifetime is longer。 there are some applications that。You know the。

Like their lifetime is not that long， but。For the average is good。But there are some caveats here。

First of all， worst case lifetime is much shorter， so we don't have guarantee here。

 which is not good。Second caveat is that intensive applications。

See large performance and energy hits。Which is again， I mean expected。And caveat3 is that。

Do we even consider optimistic PC parameters？Because we didn't know right。

 we surveyed through a lot of papers and become come up with these set of parameters but。

Are these parameters even optimistic or pessimistic？

It turns out actually in future that some of these parametersters was actually very optimistic。

 some of them not that， maybe even pessimistic， but some of them optimistic。That's the thing。

 So when youre if you're thinking of completely replacing main memory with PCM， then。

You don't get performance improvements。While you actually you get degradation and also there are some issues like that。

 there is no guarantee on lifetime and many other things that we already discussed。

If you want to learn more， you can check this paper。



![](img/9d957a701b0acf81890f56d4b01a0258_8.png)

And this is also the theme that we discussed about it like Intel Obane that realized in 2019。

Which again， technology  to is explain point by is very similar to PCM。



![](img/9d957a701b0acf81890f56d4b01a0258_10.png)

不。Yeah and。So， of course， when you have this PCM based main memory。

 you can also think about how you can do efficient data mapping and buffering techniques for multilevel self exchange memories。

 I think I'm gonna， yeah， I have some slide for a bit。 So yeah， essentially， the thing is that。

When you， maybe this。Yeah， so when you have multiple multile cells like here。

You're storing two beats in one cell， so you have different latencies when you want to write。

 essentially， you can see that， right？So you need to if you want to write11。

 you can actually do it quite fast。But when you want to write 10， you need to wait more and 0。

 one longer and0，0 longer。So that's the difference。说。

Then we have this observation that we have est ingredients reads。

The rate latency and energy of bit 1 is lower than of bit0。Why is that。You can actually see here。

Like the bit1 is the most significant bit， you know， in order to ensure the most significant bit。

 you only need to wait until T2， right， But if you want to make sure about the least significant bit。

 you need to wait until T4。 So you have this esymmetric。Oh。So yeah， if you can also show。

 we can also show it in this simplified example that we。

There is a capacitor field with reference voltage。And when we connect MLCPCM cell with unknown resistance。

 depending on how what's the resistance， this is actually the simplified version of our sensing circuitry depending on the chart that depending on the resistance of that。

 you might have different current basically and that current would determine how fast these capacitor will be basically。

He charged。So yeah， in here you can see that this was the initial voltage of that capacitor。

And we connected and then。If this amount of time takes to discharge that capacitor。

 we can then encode it to 01， basically， right？So in the existing devices。

 both mCBs are read at the same time and we must wait maximum time maximum time to read both beats however we can infer information about bit1 before this time and then we can only。

Basically we can use that like so time to determine bits one value， like the most significant bit。

Is faster， so we can actually read faster for that。So how you can benefit from that。

There are different ways， which I'm not going to into detail of that， but you can think of。

 for example。You can store， consider one。Like one page of memory in MSP and the other page in LSP。

 basically， and the page that you have in most significant bit is faster。

And LSP is a slower and then you can think of how you can handle it or control it as a like a cache。

 for example， you know that data that they are latntency sensitive。

 you can map them to the pages that they are mapped to the MSP beats that they are faster and the other to the LSP so there are different base this one just an example。

But for that， you can also read the paper。For more detail。We also have asymmetry for rights。

 depending on what's the initial estate we have。😊，We have different latencies。To get the final value。

So essentially， for example。Then the value is01 and we want to write。

 we want to go to the state of 00。You have quite。Yeah， it's quite faster， for example。

 so you can also use that and benefit potentially from that by using no data mapping and buffering techniques。

I haven't discussed， I haven't explained like how this can be implemented。

 like how you can benefit from these techniques if you want， you can also check this paper。

 but you can assume from the example I mentioned I guess。Any questions？

Now we want to see how is sitium run。Can replace as main memory。

First of let's see what what is a CtM Bra a CTM Bra has magnetic tunnel junction， MTJ device。

 you can see the device here。And there is a reference layer with a fixed magnetic orientation。

This is the reference layer。And there is also free layer that it can be parallel or un parallel。

So when inhabit is freely parallel with the reference layer， you can encode it to logical zero。

And when it is on parallel， you can encode it as logical one， for example。

So magnetic orientation of the free layer determines a logical estate of device high versus low resistance。

And for right， you need to push large current through MTJ to change orientation of free layer essentially。

 and for read， you need to sense current flow essentially。If you want to learn more about CMR。

 this paper you can actually check， people have looked into using CM RAM。诶。

Instead of actually s as well。Because latencies of a CM Ram is actually。

 you're going to see that it's actually much。Better than the。

But they are also they are not but they are not better than ERA。

 but at the same time the problem with STTM Ram is density。

 so unfortunately Dm is I mean STTM Ram is not as dense as D。So their density is very similar to STM。

 so that's why people also look into how they can use CM RA an SRAM together and they design different architectures like caches for GPU。

 CPU and other basically devices。But in this work we are discussing about how we can use C Ram as a replacement for DRAM。

 so there are some fs over DM like better technology scaling， capacity and cost。

And it's nonat oil again so it's good persistent and low id power at the same time also CTMM latencies might be even faster than DM as well。

 but there are also cons for right latency unfortunately CTMM has higher light latency and so for RE latency STMM might be better and right energy is also high。

Unfortunately， it has proved density。And。reliability of a cityM RamM is also questionable。

For the cityMM， there are still a lot of work going on to see you to make it reliable so。

That's why we have this question mark here。But this memory technology is actually quite interesting because of this level of freedom as well。

😊，So you can trade off non volatility of this memory for lower light latency and energy。

So when you reduce the size of this emptyJ。You can reduce retention time。Potentially， at some point。

 your retention time is not that high， such that you need to refresh it。

But for memories like cash that you frequently update data or registerify for example。

 that you frequently update that， you may not need that actually high retention time as right so you can think of this tradeoff by reducing this MTJ and that essentially caused a lot of reduction in right latency and energy。

But at the price of non volatilityat， I mean， it can it like reducing non volatilityat characteristics。

 So at some point you， your sitting room actually needs refreshing and people look into it。

People are even looking into designing different SDTMM architectures in one chip， like as a cache。

 they have some SDTMM part that they consider as a high retention。which is slow。

 they consider as a like bigger cache and also a smaller CM Ram cache。

 which has low retention time but is faster and they try to you know cache most of the important like the working set in that basically smaller resistance like the CM RA cache。

So it's quite interesting that you have this level of freedom and you can do a lot of trade off analysis here as well。

So by architecting a city in Ram's main memory， you can see in the same。😊，Meethodology。

 you can see that we have less performance dose compared to PCM。So it's only 6%。

 and we even have 60% energy saving compared to data， which is good。So that's why actually。

CTM RAM has some potential to basically replace Dran， but at the same time， the problem， as I said。

 is its density and its reliability。So。It's not still clear。

And you can check this paper for more detail as well。But now let's look into the other approach。

 which is hybrid main memory。Remember this picture from the past that we discussed about like having like CPU and different controller。

 so you have D controller， for example， that control data which is fast and durable。

 however it's small， leaky， volatile and high cost。

 and there can be another memory technology like face change memory。

 which is large nonvolatt and low cost， however it slow versus out and has high active energy。

So while using these two together， hopefully you're going to benefit from you know to achieve the best of multiple technologies。

 so that's the idea of using this as a hybrid memory。

 but of course this also has a lot of challenges， for example， how do you map your data。

 how you decide which data should go to Dran which should go to PCM for example。

 how you migrate them。And or are you going to architect it as a cache。

 like the D is going to be the cache for PCM？Or Dam is part of the。Memory addresses space。

 so like DM and face change memory together you know constructs the whole address memory memory address space so thats if that's the case then the programmer needs to work on it as well like you know use some you know have some instructions to store data in DM part or some instructions to store data in PCM part for example。

 or compiler can also help but it can be also as a cache like DM can be cache for the PC。

I should also say that this doesn't need to be at the only main memory。

There has been work that people try to use this hybrid。A CTM brand is cash， for example。嗯。

In my PhD actually， I did also research on designing hybrid register file that I use the SM with a normal lifetime memory as a GPU register file。

 so it can be also in that level at the register file of GPU for example。

 it can be actually outside the storage system that you have different storage devices with different characteristics and you want to design it this hybrid technique。

But this is quite interesting， so the goal is to like providing the best of multiple metrics with multiple memory technologies。

😊，And that's the area that basically heterogeneousity comes to play and configurable programable memory systems。

Of course， as I said， there are many questions or challenges to address like the are we designing as a cache versus main memory as I discussed？

What should be the graity of the data movement or management should be fine grain or coarse grain。

Should be hardware control or hardware software cooperative？As you can guess。

 probably should be hardware software。When to migrate data like because migration is always costly so when to schedule it essentially and how to design a scalable and efficient large cache sometimes if you want to use it as a cache。

That cash is going be quite large。 It can be like。Tens of or hundreds of like giggay right so that cache is quite large so how do you design it like the tag area is going to be also huge so these are really important questions and questions that they are hard to answer。

But one option is that we can consider D as a cache for PCM。

So PCM is the main memory and DRAM caches memory rows and blocks。

 the benefit is that it reduces latency on DRM cache heat and it also does right filtering so improve it can eliminate the right endurance problem of PCM。

And memory controller hardware should manage the DM cache。

 so it benefits that it eliminates system software overhead。But there are at least three issues。

So what data should be placed in Dam versus kept in PCM？

So how you're going to manage your cash intelligently， essentially。

And what's the graity of data movement across them and how to design the low cost the hardware manage the DM cache？

So there are two idea directions here， like locality of data placement。

And chip tigerau and d gravity that we're going to also see a little bit later。

So data as a cache for PCM， the goal as we discuss is that achieve the best of both data and PCM or NVM。

So it minimize amount of D without sacrificing performance and endurance and D has cash to tolerate PCF latency and right bands。

And of course， PCM has main memory to provide large capacity at good cost and power。

So here is your D buffer， how you manage your D buffer is a very good question to ask and there are some technique that this paper also discussed。

Like for light filtering techniques， you can actually have this approach of lazy rights when you bring data from flash or hard disk drive。

 you don't write them immediately to PCM you just you first write them to this D buffer as a lazy right and pages and then after after all if you realize that they are needed or basically or they are dirty because you got some you capture some rights in that D buffer so you need to write them back to this PCM but at some point you don't need to write them back even to PCM you just write them back to the flash or hard disk drive so you can also do this page bypass so you just discard pages with poor to use on D ection if you want to learn more about detail you can check this paper of course。



![](img/9d957a701b0acf81890f56d4b01a0258_12.png)

Here are some results， so this paper did some analysis。

 the simulation that they have done is actually a bit at higher level compared to what we have done in the other work that I showed。

Is actually like。It's a combination of also some analytical models that they have。

 but essentially they consider that they have the simulation of 16 core system with8 gig byte Dran。😊。

And the main memory axis is at 320 cycles。It has also HD at 2 millisecond with also flash memory at 32 microsecond and they consider that flash heat rate is 99%。

 so 99% of request will hit in flesh and you don't need to go to the HD。

And their assumption was that PCM is four times denser。

 So here they they even also consider this good thing about PCM。 So in our work。

 the other work that I discussed， we haven't。We consider that both PCM and DM they have the same density。

 we only take into account difference between their latencies and like access latencies and energy consumption。

 but here in this work they considered that PCM is also denser so they are using these properties to provide better performance。

And they also consider that PCM is four times slower than theham， which is。

whichhich is quite optimistic， in my opinion， like in our work here for example。

 we consider see that PCM was 12 times， at least the right latency， 12 times longer than data。😊。

And the on block size is equals to pay PC and page size。 So you can see some results here that。

Like while you go from and the Y axis is normalized execution time， so lower the bidder。

And here are some workload from IBM assume。And so when you have this8 gigabyte D。Trave。

Re are normalized to this baseline。So having a PCM memory。As a standalone memory with 32 gigabyte。

You actually， on average， you observe some performance benefits。

Why is that because you have larger memory so now you're actually interfering the good thing about you know having the larger then larger capacity Dm so once you have larger memory you go to the access flash less frequently right so that's why you're observing better performance compared to DRA but comparing these two baseline like the PCM and Dam they both have exactly the same capacity you can see that Dam provides better performance and actually these results is very similar to the results that we also we reported in that work actually this paper and that work was quite parallel both of them was published in Eco 2009。

So it is also quite interesting in that sense as well。But having a 32 gigabyte PCN。

Plus one gigabyte the as a cash， you can actually get the performance benefit。

And the performance on average is very quite close to 32 gigabyte D baseline。

So you can almost get the performance of 32 gigabyte Dm by using 32 gigabyte PCM plus1 gigabyte Dm as a cache。

Which is good we wanted that actually as a from a hybrid memory system。李。



![](img/9d957a701b0acf81890f56d4b01a0258_14.png)

ok。Great。😊，So yeah， here also we discuss about。how energy and also the lifetime。

 you can see that basically the hybrid design provides better like energy consumption and better energy delay。

 like the kind of energy efficiency metric。And the average lifetime is around also 10 years。

 but of course， there is no guarantees because worst case scenario can actually wear out your system quite fast。

Yeah， but if you want to learn more， you can check this paper。

 actually it was also from IBM research。Scalable high performance main memory system using face change memory technology。



![](img/9d957a701b0acf81890f56d4b01a0258_16.png)

Any question？Yes。啊。你个意思。Yes， yes。Yes， very good question and that's true。

 we will have one brief slide actually on that at the end。

 but yeah we potentially that's actually one of the issues as well in D you need to do that cold would attack。

 but you really need to you know cold your Dm a lot you know to very low temperatures such that retention time is long enough such that you know you can just。

😊，Remove your D from that system and put it on another system。 But with normal letteral memory。意思。

Everything is there like normal et， so they potentially you can actually steal data and have security issues。

And people have done research on that as well very good question。That question， actually。

 I would say very good comment。Okay， great。 so let's。

Let's think about this data placement and hybrid memory at a little bit higher abstractseion。

So essentially， you have these core caches and memory controllers and several channels can be and one channel can be memory A。

 which is fast and small and channel B can be memory B， which is large and slow And the idea is that。

You want to， basically。Ilocate your pages to these。Different memories。

So at some point want to you move page two， you migrate page two to channel A because you want to have faster access。

But the problem is that。So it caused some data movement。But in addition to that。

 now you also have some contention on China A。 So it can also comes at the price of some lower bandwidth if you implement like this as well。

So which memory do we place each page in to maximize system performance， these are the question。

 but at the same time you should also answer other questions that like you shouldn't basically make channel be ideal and potentially cause load balance issues。



![](img/9d957a701b0acf81890f56d4b01a0258_18.png)

Okay。So data placement between D and PCM， the idea is that how to characterize data access patterns and guide data placement and hybrid memory。

But there are workloads that they have streaming access。So when you have a stream access。

 they can be as fast in PCM as in data。However， in random excesses， they are much faster in data。

Because for random access， you always， you need to pay for。Acccesess latency。

 But when you have stream access， hopefully you can hide those latencies by benefiting from your bandwidth。

 essentially。 So that's why if you for the applications that they have stream access。

 you can actually map them， for example， in this example， to PCM。 And for random accesses。

 you can map them to the data。 And that's the idea of this work。

 like place random access data with some reuse。Reusability is also important。

 so you also need to consider some locality as well。So random accesses， with some reuse。

 we mapped them into DM and for streaming data to PCM。

And here are more detail about it like so row buffers exist in both D and PCM。

 so row heat latency is similar in D and PCM however row miss latency is small in D and large in PCM so that's why I actually。

LR conflict is costly for PCm so that's why you don't like random accesses。

 So while you have streaming excesses， you can actually benefit from your robot bufferer locality so that's why you can actually map them to Dm or PCm and both can work but when you have random accesses most likely you're going to issue you're going to have a lot of row conflict and that's why it's better to have a。

ran uses a memory that has this mis latency。Question。Okay。

So place data in Dm which is likely to miss in the row buffer， low row buffer locality。

 which means Peanti is a small end D and is reused many times。

 which is catch only the data worse the movement cost and D in space。

 so these are the two criteria that if they are met。

 you can actually move that or migrate that data to the data。

And here are some results for that that you can see good speed up。

You can check this paper also to learn more about this work。

 how you can benefit from Rob buffer locality that make your hybrid memory management technique ava of robe buffer locality and as well as yeah。

 exactly so memory access pattern。Okay， so yeah there are some weaknesses of existing solutions。

 they are all heuristic that consider only a limited part of memory access behavior and do not directly capture the overall system performance impact of data placement decisions。

So since we don't have enough time， I'm going to skip these slices。

 I'm going to just give you some idea about it like in the end。You want to get some。Yeah。

 you want to define some utility technique。Basically utility based hybrid memory management。

 So a memory management that works for any hybrid memory。 So this work granted to， you know。

 to design a memory management， hybrid memory management technique that can be extend extended or can be applied to different。

Baselines。So essentially you need to define a metric which is called utility。So for each page。

 we need to use comprehensive character six to calculate estimated utility。

 which is a performance impact of that decision。Here。

 the decision is migrating page from one memory to the other one。

And we only migrate pages with the highest utility。

 and that means pages that improve system performance the most when migrated so how we define this utility metric and how we capture it and calculate it。

 of course you need also some modeling。嗯。You need some performance model at the run time here you can see some formula。

 for example， formula for that。And based on that， you make your decisions。Yeah。

 but you can learn more about it as part of your potential learning reading as well that you can do from homework tree。

 I guess。Okay， so any questions so far。Yes。So，Yes。Why is that。可以。this。是他。那其实还黑色上。嗯。Yeah， you can I I。

 no， I， I think you can consider the same size in that exam。 Yeah， in that sense， yeah。

No so the thing is that when you have me in row buffer locality。

 you need to pay for when you have miss in row buffer， you need to read again。

 you need to sense a PCM row right and you need to pay for PCM access latency but when you have row hit you just need to pay for kind ofstr access latency right because row buffer is essentially。

The spa memory kind of things， right？O。So yeah， there are a challenge and opportunity like enabling an emerging technology to augment DRM and managing hybrid memories and designing effective large DRM cache。

This is one issue here。So let's also look into this problem that we have with large DM caches。

 so when you have this large DM cache it requires a large metadata like T+ block based information store。

 how do we design an efficient DM cache basically？🤧。So when you issue a load request。

 you first check the you want to see if the data can be achieved from this DRM cache right so you need check the metadata so you need to access it and then if it's hit you can get the data from DRA basically。

Otherwise you can you should go to the PCM so then the idea is that how we store tags。

 so if store tags in the same one idea is that we can store tags in the same row as data in the data。

So in your D row， you have cash blocks and also you have tags。So unfortunately the downside is that。

 I mean the benefit is that you don't need on cheap tiger storage overhead because actually that's a huge overhead。

 your ti array needs to be quite high， you can actually do some calculation at home。But essentially。

 that's because your'。Cash your DM cache is quite peak here。

 and then you need quite large ti metadata。So you don't need to pay for that。

 but there are some downsides that cash hit determined only after a Dax。

Which is quite basic time consume。And cache heat requires two DRAm axises。

 so you need to access DRA to get the tag。And then after checking the tag。And if it's a hit。

 then you need to access again and read the block basically。So that's an issue again。

The second idea is that because the idea of first idea， we can still store all metadata in Dra。

But we can reduce metadata storage overhead。Sorry， we can so that's because you're going to reduce metadata storage overhead。

 but you can also cache a part of that metadata in an oncheest strand for frequently access metadata。

 so those blocks that you are accessing them more frequently you can cache the metadata of them in a strandRAM base。

So yeah， so that can actually reduce the cost for accessing metadata so now you have probably both fast metadata access and as well as also lower storage overhead metadata access together。

And the third idea can be like dynamic data transfer gra。

 so there are some applications that benefit from caching more data so they have good special locality potentially you can consider that they have larger cash blocks。

Others do not， so large graity waste bandwidth and reduce cache utilization。

 so the third idea is that we can have simple dynamic caching graity policy。

By cost benefit analysis to determine base data and cash block size。

And then they can group main memory into set of rows， for example。

 and then different sample rows sets follow different fixed caching glities。

The rest of my memory follows the best bi， for example。



![](img/9d957a701b0acf81890f56d4b01a0258_20.png)

Yeah， you can check the paper for more detail， but with this technique combine combining all these together。

 you can actually get the performance very， very close to the ideal。Case that you store like ideal。

 but very costly that you store the whole tag into in your in the strand basically。

 so in this baseline strand， the whole tag array is stored in a s。But from this technique。

 we have Tiger in the Dam， but all this technique that we build on top of that。

We can actually get the performance very similar to that， but with quite lower complexity。

In terms of energy efficiency， you can get better energy efficiency because you don't reduce Per as much。

 but you reduce the cost and power a lot because of lower storage。



![](img/9d957a701b0acf81890f56d4b01a0258_22.png)

Okay， so you can also check this paper if you are interested to learn more。

 it's going to also be part of your reading as well。But essentially， D caches。

 there are many also recent options。People also have work on it a lot， we have worked。

 other people have worked also a lot and there are many different studies like different that we can see here。

 different scheme， this paper actually has done a really nice comparison across them like compare all these schemes or techniques in terms of like DM cachehe。

 how they handle D cachehe， how they handle D cacheshms。How they handle replacement traffic。

 replacement decision， and so on and so forth。So if you're interested。

 you can actually check this paper as well。Okay。Any questions？

So now I want to look into other opportunities with emerging memory technologies。So。

Here I'm going to lease some of these basic opportunities， we're going to cover a few of them。

One opportunity， potential opportunity is merging of memory and storage。 So currently they are not。

To merge like we have Dam and we have SSD or RDs， so potentially with emerging memory technologies because they are non volatile。

 you can actually merge them and you use a single interface to manage all data。

You can also consider new applications like Ultrafa checkpoint and Restore。

 which is quite important for persistent memory。You can have more robust system design by reducing data loss。

And also， you can think of processing tightly coupled with memory like using this processing in memory techniques。

So I recall our first in using memory lectures， I'm not going to go over them again。

 like we can do a lot of computation， for example， using Dran like Ambeat and roll clonean。

 same Dran。

![](img/9d957a701b0acf81890f56d4b01a0258_24.png)

![](img/9d957a701b0acf81890f56d4b01a0258_25.png)

People have shown that， for example， emerging memory technologies。

 they can also do both like Bwiseys operations。And Ro loan in this work Pnotable。

 you can check it if you are interested。But interestingly。

 these architectures can do also some operations that processing using DM cannot do， for example。

 easily。And that's because the way that they are built， like in memory cross for array operations。

So these architectures are like designed in a crossbar way。

 like some emerging NVM technologies have crossb array structure like memory store， resistive RA。

 face change， memory Siem RA， and these crossb arrays can be used to perform dot for dot operations。

Using analog computation capability， so by doing dot for operations。

 potentially you can do matrix vector multiplication。

 potentially you can do neural network convolution neural network so and many。

 many other these techniques。So they can operate on multiple pieces of data using Kov's law。

And B9 corin is a so that's a clearov law right B9 corin is a sum of for of ward9 voltages times conductive of each cell。

And computation is in analog domain， so inside the crosspar so that's why you need prefl circuitry like digital to analog and analog to digital conversion to for the inputs and answerss。

Here is one example， so you can see we have these digital to analog converters。

And here is your trustspar area。This is a sample and hold if I'm not mistaken。

 like you can think of as a latch， you know， that you sample your analog data print here and you have analog to digital converter here。

So essentially what's happening here is that the voltage that you apply here。

 which can be determined based on your input vector。

 so you have some input values like0 and1 and you use this dash like design digital to analog converter to map them to some voltage value。

 right？So these voltages can cause some current。To this line to this line， sorry。

Depending on the conductance of。Of this resistor。And then the current value。And。

In this basically bit line is going to be some of these current values based on Kovs law right so that's why you can actually you can see that this is actually kind of dot product you know。

 so you can use this analog perspective and then use it that convert it to digital to do easily dot product。

And people have done it。So I already explained that this you can also see it more from this。

Like animations。It's like this is the current value that you can get。

So essentially you can consider that， for example， you have this input input array and this is your metrics。

Your weight matrix and you can have your weight matrix as the resistive value。In your trustsperity。

And then you input all these values to the input voltages and then you get out， essentially。

So that can implement， yeah。Right。不的。Yeah，那是。Yeah， you need to pay for。Basically， right energy。

 right latency to program like a CM brand， for example， right or Ri。 And that's also part of the。

Like the endurance issue， like people have shown that， for example。

 using Ri array is quite good for inference。That you program your rates for one time for example。

 and then you do a lot of inference a lot， but once you want to do training that you need to update your rates。

 then your CRper is going to wear out very， very quickly。Yeah， so。

And this has been actually basically presented first in。But you know， people have used it for。

Accelelerating convolution neural network in Iac paper， for example。诶，系。

Do remember that paper very clearly because the first author of Isaac paper was my first mentor。

In 200s。11。When I was doing when we were doing together research on。

Aaptive routing algorithms or interconnection network but we're going to also see some lectures on that as later。

But yeah， so later on， he。Join the University of Utah and he worked on this topic as a P in and now I'm not sure where he is but。

I also learned a lot from you， as。Okay， so yeah， so you can think of how you can use this idea for convolution so heres an example convolution that you essentially have input feature map and there is this window that you are moving or sliding through your input。

And you're doing some computation whenever you know， at each step。

 and then you calculate the output feature map， essentially。So of course。

 you also need to do some padding such that you make sure that， you know。

 you always have some data because there are some regions that your window。

And can go outside your input feature。So yeah， so you can actually think about it and then you can use it for doing。

This operation for。嗯。P convolution or a network。But in convolution or a network。

 you don't only do basically dot products， there are also some other layers like non nonlinear layers。

Likereello。That those also so in your chip， essentially。

 you can have this NVM based team array that you do these dot for。

And also you need to do some nonlinear function array you can consider as a processing near memory engine。

That they also integrated here such that they can accelerate non nonlinear neuro patients。

And with that， they could basically improve performance。

We also have done work on this topic like Gen Pet。That John might also discuss a little bit about this work tomorrow in our genomic lecture。

So in and this work also swordfish， I'm not sure if we are going to discuss it tomorrow， but I'm。

It's going to be also part of one of your reading。 So this is also quite interesting because people have used the read a lot。

 you know this。Basically memory stores for doing。NoFor doing the neural networks。

 basic for doing this convolution neural network or these applications like deep neural network。

But the problem is that these memory resources are non ideal。And then as a result of that。

 whenever you do computation， you have some errors。

So this work actually try to look into how these errors can make your you know assumptions wrong and how these。

 you know， essentially you get accuracy loss or performance loss by using these memories。

 so it's very good to know about all these issues， you know such that you can design techniques to overcome them。

Yeah， this is the Isaac paper that I mentioned and also other papers in this area。



![](img/9d957a701b0acf81890f56d4b01a0258_27.png)

That people have developed。And it's also part of， I would say。

 lecture in historic area and convolution， if you're interested。

 that's a beautiful topic that you can also check from Professor Mos lecture。



![](img/9d957a701b0acf81890f56d4b01a0258_29.png)

Okay， now let's look into the other。Any questions。I like to finish the lecture and it's doable actually。

But it might be at the price of no break。Is it fine or do you guys prefer have a like very short break legs？

Two or three minutes。H。啊。Who on five minute break。Okay， then I will continue。Apparently。

 the topic is quite fascinating。Okay。So we discussed about merging of memory and storage。

 let's jump into it a little bit more so you can have actually。



![](img/9d957a701b0acf81890f56d4b01a0258_31.png)

So this is a conventional system， essentially， right， you have a memory and you have a storage。😊。

And so processor or access D with instructions with load and store instructions。

 however to access these， we need to look going into IoB， basically subsystem， Io block。

 basically stack， and you need to open file， read the IO and then update on whatever。

So that shows that whenever you want to access storage。

 you need to pay for an operating system overhead essentially， and that wasn't the case in very。

 very early in this computer system that we had a core memory if you know about it。

There was core memory that people use that as as a main memory as a story as everything that wasn't also very big memory。

 but that was the only memory that people had， but later on by advancement in technology and people have developed like Dran then。

😊，Time to time， basically these interface actually get got diverged。

 so now we have different interfaces to access main memory and also access storage。

So we know that hardy thrive is novel， but it's slow and block addressable。

And we know that DRA is volatile， fast， and by addressable。



![](img/9d957a701b0acf81890f56d4b01a0258_33.png)

At the same time， we also know that there are some novel attempt memory like PCM or ACT RA that they are relatively fast at least compared to flash memory or RD drive。

And they are both addressable， and they are non volatile。 So now the question is that。

 can we use these non volatile memories to combine。

Memory and storage such that we have one shared interface across them。



![](img/9d957a701b0acf81890f56d4b01a0258_35.png)

So that's the idea of a two level memory and a storage model。

 so the traditional two level storage model is a bottleneck with NVM。The reason is that。Yeah。

 so yeah， the reason is that when you。Yeah， consider this example like the two level store。Yeah。

You have this processor and caches and you need to whenever you want to access your storage。

 you need to go into operating system and fly system process essentially。

But that overhead might be okay because hard disk drive is slow by itself， you know。

 so you can you can pay for that overhead because。That basically audio block latency might not be that long compared to the latency of accessing or disk。

But it turns out that actually that's not true for SSD。

 and that's why people have developed emerging also interfaces to access SSD like NVME interface that we're going to also learn about it next week。

However， if we consider that we have PCM here， so PCM is much faster than SSD。

 for example than F and then HDD， so now the you need to pay a lot of latency going through the operating system and then your access latency to that PCM is quite fast。

So clearly that's not a good decision， so now you can see that this design of two level is above lake while we are using NmbM nonvolat memory as a storage。

So。Yeah， I already explained all this， okay。So the goal is that we want to unify memory and storage management in a single unit to eliminate waste at work。

 to locate， transfer and translate data。So and that can improve both energy and performance。

 of course， and simplifies programming model as well so programming。

Program model does not need to deal with difference， basically。Like a different class of memory。

 And if also it's persistent or not on different interfaces。 So everything is just unified。

 So that's that naturally provides program ease。So with the NVM you can provide persistent memory as we discuss。

 and that's the opportunity to manipulate persistent data directly in the NVM memory。



![](img/9d957a701b0acf81890f56d4b01a0258_37.png)

So here is an example， for example。😊，So you have different memory modules。Like Dam， flash。

 NVM and HD， like different memory technology， let's say， and they are all at the hardware。

 but they are。You' are unifying the interface。As a persistent memory manager， essentially。

And you access this persistent memory manager between load and store and this manager will access D and flash NVM HD。

 so processor we only see these load NS store， essentially in the end and there are also some hints from software O and runtime and you can use these hints to map your data intelligently across D and flash NVM and HDD essentially。

So it isn't a very。Easy like let's say example of persistent object there is a file that you just you know allocated as a persistent object and then you can you know map that file exists a persistent object to flash or NBM or HtD depending on the。

Basically， characteristics of that。Yeah， as I said， persistent memory manager。

Use as access and hint information to allocate， locate and migrate and access data in the heterogeneous array of devices。

So the Per memory manager exposes a load stored interface to access persistent data。

 which that is the key difference here， and applications can directly access persistent memory。

 there is no conversion and translation and location overhead for Per data。

And it manages data placement， location， persistence and security to get the best of multiple forms of storage。

And also it manages metadata storage and retrieval。This can lead to overhead that need to be managed。

 of course， and exposes interface for system software， hooks and interfaces for system software。Okay。

 so for efficient data mapping among heterogen in devices just to give you some idea about it。

 like a persistent memory exposes a large persistent addresses space。

But it may use many different devices to satisfy this goal， like from fast， low capacity。

 volatile D run to a slow， high capacity， nonvolat HDD or flash。

 so you have different basically like memory technologies or storage devices that you can manage them nicely。

And there are also other NVn devices in between so performance and energy can benefit from good placement of data among these devices。

 that's why you really need to learn from these hints and you know map your data nicely and utilizing the strengths of each device and avoiding the weaknesses if possible。

 for example， consider two important application characteristics like locality and persistence。

Here is one example， like you have one applications like database applications。

 like columns in a column store that are scanned through only infrequently placed on flash。

So clearly， it has less locality because that is infrequent and you also use a scan through。

But it is persistent because it's part of your database。So you it is like two dimensional。

Let's say characteristics， you can classify it as this note。At the same time。

 there can be some application like frequently updated index for a content delivery network like CDN。

 and that has more locality and also temporary， so you need to place it here and that's the way you can actually manage basically your storage。

 your persistent memory。So， we evaluated this。Like this idea using you know these systems。

 we consider that we have HD baseline， like the traditional system with volatile D memory and persistent HD storage。

We also so of course， this has overhead operating system and price system code and buffering as well as also HD access latency。

We also consider NVM baseline time， which is exactly the same as HTT baseline time。

 but HTT is replaced with NVM。So that's the good thing is that this still has still the problem is that we have that operating system and fight system overhead but。

Because of this two level storage model， but you have faster xs compared to HD unfortunately。

 back then we didn't have let's say。😊，SSD baseline as well。

 there should be also F or SSD based on here as well。That's one of the limitation of this work。

And produce a memory that we use we use only NVM。And no they to ensure full system persist。

And all data access using loads and its source， so there is no two level of storage model essentially。

And it does not waste time on system calls and data is manipulated directly on the NVM device。

So you can see that going from HD2 level to NVM2 level， we got 24 times speed up。Which is quite good。

Because NDM is quite fast。And by going from NVM2 level to persist a memory。

 we are getting like five five times a speed ofD。So and that shows also the effectiveness of this idea。

 I believe a flash memory is somewhere around here。You know， if you have it。

 like because the latency of flash memory。嗯。I mean， it's much better than the HD。Like for example。

 accessing HD takes around 10 millisecond。But accessing read latency of SSD considering all other latency going on can be around like 200 microsecon or so。

 for example， so it is like orders of magnitude faster access by using flash memory。

And in terms of energy， also， you can observe a quite great speed up when you use a persistent memory。

If you want to learn more， you can also check this paper for more detail。But yeah。

 so these are a like challenge and opportunity that we also discuss here。

 like the combined the memory and storage in a unified interface to all data。

And so people industry have done work on it， I mean this is slide I have shown multiple times today。

 but these obtained memory。People actually have shown that how they can add this obtained memory as add that。

 I mean， insert it as one of the， one of the des of the system。

 and you can see that it's actually like DDR beams basically right？

And then they use it as a persistent memory， and people develop libraries that they can use this obtain memory as the persistent memory and they report result compared to having a Dran。

 like as a non persistentist memory and a storage， SSD as a persistent memory that you have。



![](img/9d957a701b0acf81890f56d4b01a0258_39.png)

And people also add。

![](img/9d957a701b0acf81890f56d4b01a0258_41.png)

Processing data I engine， I'm not sure why this is here but yeah。Anyway。

So there are many also challenges in persistent memory。

 one key challenge that I like to pointed out here is that how to ensure consistency of system data if all memory is persistent。

Like there are two extremes like a programmer transparent， let the system handle it。

So you don't want programmer you know do anything， you want to provide quite program ease。

 so system should handle it。It's very good for a program， but it's very hard to implement， of course。

 And programmer only that did the programmer handle it。

And there are many alternatives in between that I believe actually the good solution probably should be in between。

 but in research， sometimes it's also good to take extreme actions you know。

 because you want to see how what are the challenges you're going to achieve and you're going to face up and how you're going to work on them when you want to push boundaries and that's why also doing research in emerging memory technologies is quite interesting。



![](img/9d957a701b0acf81890f56d4b01a0258_43.png)

So this is an example like this crash consistency problem， which is actually quite well known。

 so you want to for example， add a note to a link list。

So there is a link to the two next and also a link to the previous node right。

 so you always want to do it in atomic manner。Because if you don't do it and a crash happen。

 then you you may get to this kind of link list that the connection to the previous node is there。

 but the connection to the next is not there。And then your link list is not。

Basically is broken essentially。So that's actually a known problem。

And cause an inconsistent memory of state。

![](img/9d957a701b0acf81890f56d4b01a0258_45.png)

So there are according solutions that basically explicit interfaces to manage consistency。

 essentially you need to do it in atomicva， essentially。

 so there are some atomic begin an end that you insert your code here to make sure that all this operation will happen in atomic bay like。

Either both of them will happen or none of them， essentially。

 so that's the key that you need to ensure when you're drinking in anatomy rate。

But of course it's a limit adoption of NbM because you have to rewrite code with clear partition between volatile and non volatile data essentially so that that's why you know this this idea this you know。

Futting the burden into the programmer and compiler。Is not， is not a good idea。



![](img/9d957a701b0acf81890f56d4b01a0258_47.png)

So there are also some quote here that I'm not going to back show you can check it later if you are interested。

But essentially， there are some。Let me see。Yeah， so you need to use a transactional memory。🤧Yeah。

In order to basically make sure that you are doing it in an atomic way。

And there are also some lists here that in library access that you need to do it gain transactional memory such that you make sure that the gains has been done in an atomic way。

But you've got the idea basically， so it should be like manual declaration of persistent components。

And sometimes you need a new implementation and also thirdered party court can be inconist state。

So you need to put them in a basically transactional memory access。But yeah。

 so essentially you need to benefit from these libraries。

And in these codes to provide consistent code。

![](img/9d957a701b0acf81890f56d4b01a0258_49.png)

But we wanted to have an approach which like the software transparent consistency。

In persistent memory and completely we wanted to be completely software transparent。



![](img/9d957a701b0acf81890f56d4b01a0258_51.png)

So the key idea is that periodically we want to checkpoint the state and to recover to previous checkpoint when crash happens basically。



![](img/9d957a701b0acf81890f56d4b01a0258_53.png)

So there is a new hardware based checkpointing mechanism that checkpoints at multiple granetities to reduce both checkpointing latency and metadata overhead。

 and we overlap checkpointing and execution to reduce checkpointing latency。

 and it adapts to DRA and NVM characteristics。So。We have done a lot of work in this and that wasn't really easy and it's not also easy。

I'm not sure if we should actually also recommend people to use it because it adds a lot of complexity to the system。

 of course。And so in this work also we consider that we have one single note that you only you need to deal with you your memory your storage。

 essentially， but assuming that you are thinking of a distributed system and you have data coming from I coming from network。

 for example， your network card。So how are you going to checkpoint that， you know。

 and people have looking to also checkpointing in a distributed system like in a database。😊。

But you can assume you know how much overhead that can basically that can cause like all the checkpointing can cause a lot of also data movement and energy。

 essentially， so that's why actually finding a solution in the middle between the you know completely put it on programmer and completely program transparent is probably the best way to go。

But we also we get very good results like our performance was within 5%， 4。

9% of an idealized D with zero cost consistency。

![](img/9d957a701b0acf81890f56d4b01a0258_55.png)

We have done also work on how we can do overlapping checkpointing and execution。

 because if you do such things that you're on。And then spend time to checkpoint and then run and checkpoint that is quite dumb right because you add a lot of overhead for checkpointing so the idea is that。

You want to overlap these checkpointing by running other。Caness， other threads or whatever。

 so essentially you should be able to schedule them nicely such that you can overlap checkpointing and execution as much as possible。



![](img/9d957a701b0acf81890f56d4b01a0258_57.png)

Yeah， if you want to learn more， you can check this paper it's going to also be one of the readings in your homework。

But there are another key challenge in persistent memory as well。

 like the program is to exploit persistence。And people have worked on it a lot， you can。

 if you're interested to learn more， you can check these papers as well。

Now we reach to this security and data previous issue that。Your colleague actually brought it up。

So essentially in NVM， we have these security and privacy issues。So first of all。

 with endurance problems， we have these where attacks。

So people actually can design attacks cause you're cheap to wear out quickly， for example。So if you。

 for example， attack here， for example， issue or yeah issue a lot of rights to your PCMA memory。

 for example， you know。That can cause， you know， we're out of that sheet。Of course。

 there are some techniques like very leing that people have been using， trying to limit the you know。

 the the number of rice， like for example， in your PCM。

Assuming that endurance is 10 to the over 8 and if you write to one cell only 10 to over8。

 then that set is going to be， right？But if you balance your right。

 you use some technique like a word leveling that you basically try to， you know。

 write in a balance way in your the whole memory array。 then hopefully you can actually。You know。

 tolerate more rights， essentially but。When you're designing an attack tech。

 attack techer can actually be also intelligent enough or creative enough and try to， I don't know。

 to trick your we labeling techniques， such that essentially cause a lot of rights to your sales。

So in hybrid memories， you can also have performance attacks， for example。

 people have work on it as well。呃Da。The thing that actually your colleague mentioned that data not erased after power off。

 so in D when you just power off your system your data is cleaned up。

Unless you want to do this cold boot attack and you know cool your D a lot， but in general。

 when you pour it off， things are done。呃。But things are basically yeah completely erased。

 but in normal lifetime memory that's not the case and you might have some privacy issues here that you need to look into it。

So let's conclude any questions？I was a bit fast in some slides， but I tried to convey。

Tey ideas as much as possible。So hopefully you got the very good insights。

 some good insights from this lecture。So the future of emerging technologies is bright。

 regardless of challenges in underlying technology and overlaying problems requirements。

It can enable orders of magnitude of improvements and new applications and compute systems。

And yet we have to think across the stack as we discuss all the time。

And designed to enabling systems so here is a very good example like you have a new device。

This emerging memory technology。😊，And you can design different techniques， you know。

 like we have observed like techniques that micro architecture software。

And people have done work on algorithm design， you know。

 such how you can change your algorithm in order to have less number of rights， for example。

 you know。So when you design your algorithm normally you don't consider that at all。

 right like with the DRam， you never thought， okay， how many rights I have， you know。

 but with this new like angle here， like computer science also need to be awareed that people that they are working on theoretical computer science that's say that these algorithms should be alsova of the number of rights as。

 you know， and people have done interesting work in that direction as well。And of course。

 if in doubt， refer to flash memory， a very doubtful emerging technology that for at least two decades。

But now you can see that flash memory is， I mean， everywhere， I mean， in all our pockets。

And we're going to also learn a lot about flashlash memory next week。

There are many research and design opportunities in this area like enabling completely persistent memory。

 as we also discussed， computation in or using NVM based memories， hybrid memory systems。

 security and privacy issues in persistent memory， reliability and endurance related problems。

 virtual memory systems for NVM and like，Example is rich block interface。

 so this is also interesting as a kind of foot for thought。😊。

Like the reason that virtual child memory has emerged is that basically your main memory was not large enough。

And that actually made， you know， that was making life for programmingr quite hard， you know。

 the way that they wanted to design program， so people have developed this brilliant idea of virtual memory that basically that gives illusion of much bigger memory。

But using this NVM， you can actually have quite large memory。So like tens of hundreds of terabytes。

So we need to rethink about all these things， do we really need virtual memory anymore， you know。

 and all these things are quite interesting to look into and such topics are quite interesting you know when you want to when you are when you want to work on emerging memory technologies。

You in order to overcome the issues， you really need to rethink the whole stack and rethink all the assumptions that you have made decades and decades。

 you know， and that's quite insightful and that can you know push the boundaries and you know you know you can overcome with many out of the box solutions to the issues。

So this virtual block interface is one of the work that we have done also to you know think about virtual memory a little bit different。

 you can check it if you're interested or you can watch Naran's talk in one of the。



![](img/9d957a701b0acf81890f56d4b01a0258_59.png)

Computer architecture， lecture in fall 202 four years ago。



![](img/9d957a701b0acf81890f56d4b01a0258_61.png)

And with that， I'm concluding this lecture。And we are five minutes early。意见。Christians。

We could take that five minute break。

![](img/9d957a701b0acf81890f56d4b01a0258_63.png)

Okay， then I see you all tomorrow， have fun。

![](img/9d957a701b0acf81890f56d4b01a0258_65.png)