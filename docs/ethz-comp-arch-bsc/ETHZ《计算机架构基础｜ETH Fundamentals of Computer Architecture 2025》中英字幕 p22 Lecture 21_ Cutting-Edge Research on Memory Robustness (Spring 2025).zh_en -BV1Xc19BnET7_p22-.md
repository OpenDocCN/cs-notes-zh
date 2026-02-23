# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p22 Lecture 21_ Cutting-Edge Research on Memory Robustness (Spring 2025).zh_en -BV1Xc19BnET7_p22-

![](img/7f334abb35d970f23850ceddaf8f42f2_0.png)

Hello everyone， let's start today's meeting。 So yesterday we sorry I have to speak here with out love because there's no microphone in this room。

 If it's too much let me know I can make it lower as all。

 So yesterday we talked about memory robustness and Ro hammer and drop problems in general。

 So today we will cover some of the cutting edge research。😊，Pieces projects today。

 so they will be mostly safari papers， but we will also cover some nonsfari works as well。

 So I will give the first presentation。 I hope to finish it in about like25 minutes so but please don't hesitate to stop me and ask questions in between Okay。

 so the first piece of work。 it's called spatial variation very redistance defenses。嗯。

Okay I forget about this so I forget about this yesterday as well so this is a brief self introduction for myself so my name is Giri the full name is not it's important so I've been doing research in safari since August 2016 in different places and I defend my thes' earlier this year so I have a website over there for the full references links to all the works that I did and so on and please don't hesitate to use my Gmail address if you have questions to reach me。

😊，So it's already in the slide and I worked on all fields of computer architecture and hardware security。

 especially focusing on memory and storage systems。😊。



![](img/7f334abb35d970f23850ceddaf8f42f2_2.png)

So let's move on to the paper so the full title is as you see over there。

 this is a paper that was published earlier this year in HPCA high Performance Arch conference one of the top conferences in the architecture field so we will talk about memory isolation as a quick background let's assume that you have this memory and this box represents your memory and you have an access going to a certain memory location。



![](img/7f334abb35d970f23850ceddaf8f42f2_4.png)

And you observe a data change from1 to00 to1。 It doesn't matter in a location that is not actually in the location that you access read or right。

 So it shouldn't happen right because you didn't change that data and when it happens it can lose data loss or corruption it can compromise your applications correctness I gave some examples yesterday about those it can be used to leak private information like stealing your SSHTs and it can be used to take over your computer to get the pseudopeologists as I showed earlier。

 so to avoid this we have the principle called memory isolation。

 basically dictates that an access to one memory address should not have unintended side effects on the other memory addresses。

And this is a really fundamental primitive in terms of security and privacy and reliability。

 basically for your data integrity in your system。😊，However。

 it's difficult to satisfy in modern memory chips because we have D technology as the main memory technology today。

 It's the problem technology because of a lot of tradeoffs in terms of its density。

 access latency and so on。 and we did a D chip。 This is the general organization。

 I'll just quick to go over it。 So we did a D chip， we have multiple banks in each bank。

 we have these。Smaller arrays called sub arrays and within each sub we have ER cells organized in two dimensional arrays of fs and columns and as we discussed yesterday and last week as well。

 we internally we accessed the ER rows and D roogram alert by fetching their data down to the row buffer。

Okay， so inside the your cell， as we discussed earlier。

 there's a capacitor that stores your data in terms of electrical charge and there's an accessor that you access this data so there are several charge leak paths and it's a volatile bit more technologies so it requires refresh operations that need to perform so that you do not lose your data and to access data you need to first perform an operation called raw activation to fetch the rows content into the row buffer and then you perform the column access these to the row buffer as we discussed yesterday again and once you're done with the row。

 you need to perform an operation called treechar to close this row so that you can open another row。

So I'm just going to animate this， so if you open close D rows very frequently you have bit phlips in neighboring cells right so this is called a row hammer and it's a prime example of D re servers as we discussed yesterday。



![](img/7f334abb35d970f23850ceddaf8f42f2_6.png)

Let's move to the executive summary of this paper so as you know redisturance version with technological scaling with newer chips we have vulnerability and existing solutions already have significant performance energy and cost overheads and unfortunately there's no rigorous prior work on the spatial variation of D redisturance across the rows variations and also the variations of implications on future solutions。

 so in this work our goal is to understand the spatial variation redisturance across these different CRM rows and make an information useful to leverage that to improve the existing solutions。

😊，So in this word， we test 144 DDR4 DM chips from three major manufacturers and we characterize all the roads in a bank and we also characterize multiple banks inside of the DM chip and we find out that there is a large variation in the Rohamm or or redistance vs of DM rows。

 when you look at different rows across all these like across within a bank and across banks and this variation does not follow a very regular pattern。

So based on this point we come up with a key idea of dynamical tuning given solutions aggressiveness based on the victim role vulnerable at the level and to this time we propose a new mechanism called S sewward stands for spatial variation a very thes defenses and it turns out as it's also the Swish sword for sword so at some point there can be a Godric grin or sword appear in somewhere I don't remember exactly so seer tunes the solutions threshold preventive actions performing some preventive actions and it's implemented either inside the thera chip or in the memory control。

Okay， so we evaluate the effect of S on existing defenses and sure that it reduce reducedly given solutions performance overhead quite significantly and as a result it provides some speed up to your system to con the randombinary applications as well。



![](img/7f334abb35d970f23850ceddaf8f42f2_8.png)

![](img/7f334abb35d970f23850ceddaf8f42f2_9.png)

Okay， so。Our motivation is about technological stealing as we go to smaller chips and chips get closer to each other。

 we have more than an order of magnitude reduction in the minimum activation coming we need to power to induce a bit further I think when Nia is presenting she will also show like two orders of magnitude reduction this slide is a little bit still and the service worses as D chip density increases and existing solutions become quite aggressive and this aggressive prevention makes them prohibitively expans going forward。

😊。

![](img/7f334abb35d970f23850ceddaf8f42f2_11.png)

And the problem is that no prior work actually regard to study the spatial variation across different theem rows and the variations。

 implications of future solutions altogether。😊。

![](img/7f334abb35d970f23850ceddaf8f42f2_13.png)

![](img/7f334abb35d970f23850ceddaf8f42f2_14.png)

Our goal is in this world is to understand this variation and also to leverage this understanding to improve existing solutions。



![](img/7f334abb35d970f23850ceddaf8f42f2_16.png)

Okay let's move to the experimental characterization so I talked about this infrastructure a little bit yesterday later on today we will also talk about it in more detail。

 but this is the infrastructure that we call D band so DRA bands and FPG design actually that we download to an un board if sits some board that you can just by from xyles and it also supports like several other FPG boards as well and we connect the D module and press it with heater paths from both sides and heater paths are controlled with a temperature controller and we have a PCA host interface that connects this FPG board to a host machine so that we can run our test and we can analyze the experimental data so the important thing is we have fine grain control over D commands with the graler of 1。

5 nanoiseseconds and also we can control temperature with a precision of 0。5 degrees Celsius。😊。



![](img/7f334abb35d970f23850ceddaf8f42f2_18.png)

In this work we test these modules so there are a lot of details here and there are a lot of details in the paper as well I'm not going to go over them。

 but these modules are essentially from three major manufacturers so when you sum up the market share of these three major manufacturers you reach to like zero what that like 98。

5% of the market share or something like that so if you just go to Amazon or Gal and by D randomly probably you'll hit one of these。

And。We cover different densities， dis to see like if our observations are correct across generations as well。

😊，And they implement different chip organizations， and also these are like different kinds of chips from these manufacturers。

😊，And our key takeaway at the end of the characterization study is that v vary significant and irregularly across the Ramro。

😊，And I will show you a part of the characterization data here。

 so in this plot on the x axis we look at this is a histogram by the way this is a distribution plot so on the x axis we will look at the minimum hammer count induced the first bitophillip or AC first and on the Y axis we look at the fraction of DM rows that exhibit this behavior and different colors of bars represent different ERM modules and this is all from the manufacturer S which is Samsung。

So here are some observations Okay， we also show the variation across banks with the error bars and yeah the first observation the worst AC first that we observed across these five modules is 12000 activations per aggressive row in a double sized access pattern and。

When we look at this parameter across different Dem rows。

 we observe that there is a very large variation， so if you look at like S4 here， for example。

 you can find DM rows that exhibit that experience bit fors at 12k activations and there are also rows that do not experience any bits fors until 10028k activations so it doesn't make sense to protect these two sets of rows with the same robust rigor essentially okay。

 so do minimum hammer count to induce the first bit flips significant varies across rows in a Dm bank and we just collect the same data for like other manufacturers as well so I'm showing you these and then I'm going conclude with the same message。

😊，And there are more details and we have like all these minimum average and maximum raw hammer thresholds across I Ros for each module in the paper。

 you can go and check all this data if you're curious， it's available on this archive link。Okay。

 so let's look at the regularity in this spatial variation across the rows。😊，So on the X axis now。

 we have the D row address going from 0 to 6 to 4K，6 to 4K corresponds like 6 to 4。Times2 to the 10。

 so it's like 65536 something like that。On the Y axis。

 we look at the Min Ham County industry first read the terms basically， and this is how it looks。

So you might think that there are some patterns here。

 it's only because like we only test a small number of different AC first of I on the Y axis so pretty much like。

It's it's hard to say that oh there is this like repeating pattern here or there is a correlation between the raw address and the AC first word so our conclusion is that。

There's no visible regularity to my eyes based on the role location and the minimum Home County industry the first bit for it irregularly varies across theier rows。

That was one module from S highlightsx， this is another module from microron。

 this is another module from Samsung and none of them show very clear patterns。

Let's look and be sorry， Go ahead。た。Oh， it's just about the revolution of the image。 basically。

 So you have like。So those dots should be like in different roles， actually。

It's because like this x axis is like zoomed out quite a bit， right？😊。



![](img/7f334abb35d970f23850ceddaf8f42f2_20.png)

Yeah。So so far what I showed you is just like eyeball statistics right I just look at my eye look at the picture with my eyes and I say I don't see anything okay it's not very scientific so we tried some statistical approach so we looked at the predictability of a D rows redisturbance vulnerability based on several spatial features that a row has so we look at the bank address bits we look at the summary address bits roll address bits rose distance the local row offer so these are the spatial features that we can come off with right and then we look at if we can look at these properties or features and then based on these features can we predict the redisturbance v level of a D row。

😊。

![](img/7f334abb35d970f23850ceddaf8f42f2_22.png)

And we cluster D Ram rows into like 15 different pins of rowha vulnerability and we tried to cluster them based on this feature basically。

 and we measure the advanced score for each special feature and the result is that only a few of these special features by a few I mean like among all these bits you only have like a few bits and it's only for D modules from Samsung that show some advanced score that is above 0。

7 which is really not a great advanced score anyway。

So we couldn't find a good prediction based on these features。

 so this is an open resource problem right so it doesn't mean that there is no feature that which I used to predict or it doesn't mean that there is no correlation as well。

 you might look at the data you can analyze it maybe in a better way and then you can find a better correlation or better relation in between。

So the redance vulnerability so far as far as we can investigate very significant and irregular varies across the Rambro and this is the full paper so based on this we。

We design a new mechanism called SAC， so our TH paramountel takeaway is just repeating there it's very significant regularly so our idea is to leverage the variation across thes to enhance our the existing mechanisms。

 so our mechanism is spatial variation where redistance defenses and it dynamically tune the aggressiveness of an existing solution to the victim rosary disturbance vulnerability。

And St essentially performs fewer prevental actions if your row is more resilient to redisturbance pitlips。

 and by doing so it reduces the number of prevent actions prevent ref operations that you perform in your system and as a result。

 your performance overhead reduces and your system performance improves。

So we can integrate we can integrate the work with like。😊，Any given solution today。

 I think it might sound like a bolt clean， but I can substantiate it if necessary。

 but in this paper we cannot test with like all the mechanisms in the world right so we chose like five solutions that are relatively new and state of the art and we integrate to art with those solutions。

 the first one is para。 So if you remember from yesterday。

 what para does is that when a raw activation comes。

It generates a random number and based on that random number。

 it refreshes the neighbor and victim Rose or not， so to make that decision。

 you basically generate a random number and compare a random number against a threshold volume。

And what S does is tune in this threshold for you。For block camera it's another paper that we might talk about in the future we count the number of activations per the row using some filters and the activation counts are compared against the threshold so we change the threshold so that we can change the aggressiveness of block cameras the same story for another mechanism called Hy again there is a threshold so if there's a threshold in your mechanism decision making process then we can change the threshold by using S and we can tune the aggressiveness of your mechanism。

ok。So S art classifies DM rows into several vulnerability level bins and maintains just a few bits per D row。

 let's say we define like 16 different clusters and then we classify the D rows into these 16 classes and we can identify which class a row belongs to by using four bits right so we just maintain those bits and we can maintain those bits inside the D chip or inside the memory controller and the decision is based on wherever your existingservance solution is the memor controller is if if your solution is implemented inside the me controller then you can yeah so then it looks like this right so you have the meor request scheduler you have DM chip you send D commands and address it and this purple boxes is your memorymor controllers and。

You might implement your existing disturbserv social。

 let's say PA in the meor controller and in that case you need to access this information within the meor controller to make a decision so you can add an additional HC first table here and you can feed address to this table and then the table just gives you which H first module to use on Zoom。

I want to encourage people on Zoom to just pick up， but for now。

 I guess you can just come with the question。 is there role vulnerability relatively constant or would it change with different data pattern or。

So it changes with theat， so that's part of the profiling process。嗯。

Should I repeat the question actually， maybe I should repeat the question。So the question is。

 does D Ram Ros read the service vulnerability change over time or with data patterns or？Somehow。

 so it depends on temperature as we talked about yesterday， it depends on the data pattern。

 it depends on some other stuff as well， so there are some sensitivities so in your profiling you need to account for them。

About time， I will talk about it later， so I'm not going to give you the answer yet。

So here you can fit the row address basically first table and I understand which cluster this row belongs to。

Or you can choose to put your metadata inside the D chip so that as you know like D has a higher density compared to SRAM for example。

 right so if you implement or maintain this metadata in memory controllers then you need to implement it with SM kind of structures that can be a bit costly for you problem that's actually be evaluated。

 it doesn't seem very costly but if you consider that as a costly implementation because it's a subjective decision。

 you can also implement them inside the D chip and when you read data from D chip you can also read these metadata bits along with the data because you have some additional bits that you read in most cases like ECCbits for example。

 there are some pins that are not used in certain cases so you can utilize them to access this metadata bits so in that case you move everything to the D chip right so not everything the met。

Inside the armch。So you can basically implement this in two different potential ways。

And if you implement this inside the D chip。Then this is how it looks。

 so inside the DRM chip you have an Iop parafr， you have a refresh controller。

 and then you have your existing disturbance solution here that actually includess some refresh requests and you have your DEM summary here。

So what you do， this is one way of implemented it， you can implement in many other ways in architecture。

 we have usually like several different solutions。 you can explore the design space and five para optimalmal points but this is just one example so you can in a Dra row you have8 kilobytes of data so you need additional four bits for8 kilobyte of data or if you're considering like okay we have multiple chips and we lay out our row so you have8 kilobits of data in a D row and you add four additional bits on next it so it's a very low overhead so explore microplanning before you yes。

But then that also exposes it through to average de。Okay。

What concerns the library because it's the same rule。can cannot also be exposed toham。Yes， so。

 so you protect this。 Okay， I will repeat it。 So we now we put the metadata inside the D row。

 And D row is already vulnerable to read the service。1 bit change。😊。

So ideally you don't want those like you don't want any bit to change in Dam row right so the basic assumption is that your existing disturbance solution over there is already counting activations and refreshing your rope when necessary so that there's no bit fill in your rope。

So when you do the profiling you do the profiling for those bits as well actually。

 right so if you protect your own， those bits are also protected。Yes。Okay。

 let's look at performance simulation， we use Re 2。

0 as our simulation framework I'm going to talk about later today and we evaluate a realistic system。

 we test the system with 120 different eight Cor program codes and we pair square with five different mitigation mechanisms。

😊，And we sweep the AC first Australia， which is Millon He Countyto in first bit Philip。P 400064。Okay。

 so on the X axis we look at the Min Home County industry first bit Philip， and on the Y axis。

 we look at the systems throughput。😊，by using a metric cultivated speedup and this is how para looks when you do not implement anything so purple is no right so we don't have Sar here as we reduce the Rohammer threshold。

 this is the minimum number in the bank that you can find paras para reduce the system quite significantly and then once we apply three different variation profiles that we collected from these real modules H1 and0 and S0。

 these are like a module from each manufacturer when we integrate Sar with para and use these profiles we have this kind of results。

So I guess it's clear that we reduced the performance overhead of PA quite significantly here。

And these are the results for the other for mechanisms。

And these are the speed up numbers that you see like very low extreme thresholds and so are significantly reduces the performance or heterois and solutions basically。

Okay， so we have many other things in the paper that I will not cover so if we look at the deteriorate distribution。

 we look at how it works with press and we have a lot of details we have some reverse engineering data we look at hardware complexity of the mechanism and we showed that it's Army implement at low cost and we also have a preliminary analysis of the effect of aging actually I have a slide about that that I will show you。

Okay， this is that slide so I will go back to the previous question that we had from zoom does the v profile change over time so this this is a really important question for this kind of mechanism and I'm going to show a weakness of this mechanism actually at this point so what we did was like we just kept hammering some rows for many days。

And then I already showed this data to you yesterday， actually。

 and we observed that for some of the rows， your thresholds can reduce over time as you hammer it。

So this means that if you use something like Sart， you have several options again。

 you need to repeat profiling quite often， maybe maybe not that often so we don't know that because we don't know how aging works with redistbance really this is just some preliminary data this is just to motivate further agent studies so you need to understand how agent works and based on that you need to periodically repeat profil in our chips maybe we can find some online profiling tools that you know while youre using chip you can block part of it and then you can do the profiling over there for example。

 and update your profile so S is nice in the sense that once the behavior of your row changes you can just update the metadata and then it works fine。

But you need to have some mechanisms to update that metadata。

 So there is some further research opportunities over there。



![](img/7f334abb35d970f23850ceddaf8f42f2_24.png)

And I want to encourage you to work on that。

![](img/7f334abb35d970f23850ceddaf8f42f2_26.png)

Okay。So， in conclusion。We did the first rigorous experiments on spatial variation among all chips and we show that reduces v significant and irregular varies across D rows are key idea based on this observation to dynamically tune given solutions aggressiveness and to this we propose a mechanism called S it tunes the solutions threshold of and parameter interaction and it's implemented either inside the D chip or in the memory controllers and it significantly reduces the performance overhead of existing solutions and this is the end of my slides I can get further questions。



![](img/7f334abb35d970f23850ceddaf8f42f2_28.png)

Yes， which one you Okay， so sure that you actually speak up。

 but you also like you might view this threshold。 So doesn't affect the performance like the。

What three the same because it could change。

![](img/7f334abb35d970f23850ceddaf8f42f2_30.png)

So are you talking about this to ensure that you get speed up？

Speed up based on the like our baseline is parallel without the， right。

It shows that you still have the same level。I curious。You mean it seems reliable to them？Yeah。

 so we have a security analysis of that as all actually so basically so if you're talking about this point。

 for example， the threshold is 64 right so in 64， it means that the worst draw you have in your bank experience with those at 64 and you have other rows that will not observe experience with those until like 10000 for example。

 so。😊，In par， it just keeps using the same threshold for all rows， but in our case。

 we just use the proper threshold for each row。Based on this like variation profiles that we collected from real chips。

So in that case， the security level of。Ros are the same。

So para basically was making some roles like extra secure so that's the tradeoff' we don't make them like unnecessarily extra secure。

Yeah， you either in my controller or any。's be tested you company paper which。

 And it so every in the hardware or like only sulator level。No， it's just simulation working。 Well。

 there is like experimentally characteristics additional real D chips。 So that part is real。

But the mechanism and the implementation of mechanism are just like。

We basically estimated the cost based on some models that we keep using in the community。可以。Yes。

What percentage of throws have say， for example。The requirement of 46 as I it a small percentage a big percentage。

呃。Yeah， so the weakest throws are actually very small fraction。

And yesterday I showed some other characterization datas coming from another paper that tells you that if you look at like 10% of the roads that are the weakest straws。

And you compare it with the 90% of the rows that are the Roman rows。

This you need like double the activation count to issue a bit further compared to the 10%。

 So there's a very small fraction of the round rows that are like significantly more vulnerable to Hamish。

And you you I think you can find those numbers in in those like histogram plots and the table has。

Table has minimum maximum and average， it doesn't show the population。Yeah。So I mean。

 could it make sense to expose this information to the memory。就。Leverage even more speed up。

 that you access the。The week rose much less。So that's a very good point。

 the question doesn't make sense to expose this information to where the system leads to memorities or yeah。

System software， exactly。 So when you do this hardware software cooperation， basically。

 whenever you do that， you get something really significant out of it。 So it's a good direction。

 And you can expose the information So you can put your security critical data into very like。😊。

Veryry resilient rows that do not observe with Philips then it's very good right then you don't have to keep refreshing all rows and if you can also implement something inside me control。

 for example， that understands like which rows are allocated which rows have some garbage data that I will never use。

If you can pinpoint them， like theres there's definitely some benefits over there。

 I'm going to refer you to a paper called expresspressive memoryory。It was published in。

What was it 2018， 2017， 2018， right， It should got 2018， express a memory。😊，Yeah。

 maybe we can cover it in some other lecture as well I'm not sure if it's in the plan。

 but we can definitely include it。Yes， go ahead such。

So I'm just guessing that they're already doing that because when they manufacture DM chips。

 they actually， let's say you have like you want to have 64K different roles inside a bank right by design。

 They don't implement like that minerals， they implement more rows and they have something called spare roll So after the manufacturing process。

 they test their D rows， some of them turn out to be faulty and they don't want to just like trash that chip So they have some remap and table inside the D chip that redirect some raw addresses to other raw addresses。

 So that kind of thing is already done to improve the term is yield like to improve the manufacturing through put basically and I think it's not。

I'm realistic to guess that they're already doing this as well。

 But these are the chips that we just buy from galaxies， for example， right， So its。

 it's not really like。Back before those tests。DidThey already went through those process。Yes。😊。

Part of it sword with all changes， the threshold。Or is there any other material。So in this mechanism。

 we just change the threshold。And that other。不是。

![](img/7f334abb35d970f23850ceddaf8f42f2_32.png)

Yeah， so。I didn't go through this in detail because it's the same story。

 so for all these mechanisms you always like count something， calculate something。

 and compare it against that threshold。And once you change the threshold。

 you actually change like how frequently they decide to perform prevent or refreshers or not。

 or like in blood commercialmer as it rots accesses so。

It decides throttle or not thttle based on some threshold。 So when you change the threshold。

 you can make a difference in that decision。 So the finding of every。Yes。

 so this profile changes's the data distribution。一場い緒でただけ。嗯，好。You have that this。

So everything based on the profile and data and all these mechanisms， by the way。

 have the own security analysis in those papers and the security analysis starts with the basic assumption of that I have the H first one or I have raw hammer threshold and that's the correct information and if that information is not correct the security analysis is just garbage for all these right and it all depends on the profile and data it all depends on your test methodology。

 how rigorous you go with the test methodology and like we discussed yesterday。

 the vulnerability level changed a lot with temperature， a lot with data patterns。😊。

With access patterns。 So you need to really find the absolute worst to find the correct hammer threshold。

 And it's not practical to do today。With alone， the potential effects of aging， for example。

So that profile can change over time and even if we assume that it doesn't change。

 it's really hard to gather that profile as well and it's an active research problem actually so I don't have a very good question to that because we don't have a solution for that and we need to do like more tests we need to understand how this works better by this I refer to like the error mechanism or disturb serviceance phenomenon we need to understand how it works in a more detail so if we can develop better tests to find those worst cases。

😊，So there's a lot to do in that front。involves counting minimum number of handling。

 but or something。So you basically test hammerrrhin rows with some number of hammer count and now you observe if there's a bit filip and based on that you reduce the number of hammer count or increase the hammer count。

 so you try to find the minimum hammer count you can induce a bit for it and based on that you tune yours or configure your mutation mechanism。

Are there other questions？I guess it's already the time to move to the second talk， right？

Maybe we're a little bit late。あ。But it's good keep asking questions so in this part of the lecture we will talk about low cost and scalable draw hammer mitigations。

Okay， so let me start with a。Introduction。So hi I'm Nia。

 I'm a researcher in Super research group since September 2018。

 I started my PhD almost two years ago and you can contact me with this email。

And my research interests our computer rack sector。

 hardware security is are more focused on memory systems。

So let's continue with some raw hammer mitigations。

 I guess you are already familiar with the slides and the concept but today's D chips are vulnerable to eat disturbance。

 we're repeatedly opening and closing or activating and precharging the same D row results in beat slopes in nearby D cells。

 which we call raw hammer beatthlips。You refer to the hammer drove as the address rope and all other ropes with the bitfs are called victim row。

 and we call the minimum number of activations that cause the bitfb the raw hammer threshold。

And again as you all know， D chips are getting more and more vulnerable to disturbance today and read disturbance pit loops occur at much lower a counts。

 so this is the first work that looked into read disturbance errors and it reported this high low herrhage threshold and these two more recent works from 2020 and 2023 reported much lower activation counts resulting in the disturbance pit flus so the raw herrhage threshold has reduced more than two orders of magnitude in less than a decade。

 and this is exactly why mitigation techniques against street disturbance attacks need to be effective and efficient for highly vulnerable D based systems。

One way to mitigate raw hammer is to preventively refresh potential victim roles when an aggressor reaches a dangerous activation count。

 but doing so requires tracking activation counts of the aggressor rows before these victims experience pits。

And let's look at an overview of approaches to track theamral activation counts。

 so the first approach that comes to mind is to allocate one activation counter per Damral here we have like each of these Drarals have one counter specifically for them and wheneverarrow row is activated。

 we increment one counter so this gives us the perfect tracking mechanism。

The mitigations based on this approach have very low performance and energy costs because they can do preventive refreshes when it is absolutely necessaryces。

But as you can imagine， the area costs are getting very high because we have many DM modes in today's DM devices。

 so we need to store a lot of data to just track these activation code。

And the second approach aim to reduce the number of counters using one observation。

 this observation is that an attacker can only hammer a small set of the DM rows before DM is periodically refreshed。

 so this reduces the number of counters that we need。

 however we need to allocate these counters to specific growth。

 so these approaches these mitigations allocates one activation counter per agress row。

And they use text to understand which counter belongs to each Dam。And again。

 since these counters are incremented when these specific roles are activated。

 the performance and energy costs are still low。However。

 especially at low row hammer thresholds the area cost is getting higher。

 this is because the number of agress rows increases significantly when me can induce when an attacker can induce low hammer bitps with fewer activations。

 this means that they can hammer more D rows and we need to track more counters。

AndSince we are using tags for these counters， these counters are usually implemented with content adjusted flow memory。

 which is also extensive when you consider area and the toward the approach reduces number of counters and look less than one counter per D row either by introducing shared counters that groups and D rows to track them together or by introducing probabil refreshes and since we are reducing the number of counters that we implement the area cost side low。

 however， especially at low row he thresholds， the performance and energy cost increase a lot this is because of the high D bandwidth consumption that these mitigations have so these mitigations use the D bandwidth to do the preventive refreshes and they do unnecessary preventive refreshes because they are not tracking the activation counts perfectly and basically they are doing preventive。

Fs van they can do regular memory operations and ideally we would like to achieve low energy。

 low processorship and D area and low performance overheads and we looked at for state of the art mitigation techniques and as you can see from this radar chart none of the existing mitigation techniques prevent roll hammer at low area performance and energy costs at the same time。

And today I'm going to talk about two papers tackling this issue。

 the first one is called Comt Comp cage basedase roll checking to mitigate roll hammer at low。

 which was presented in HPC of 2024， so our goal again is to prevent raw hammer beat hooks with low area performance and energy overheads in high labor hammer vulnerable V based systems。

We observe that there are two types of counters first one is hash based counters that are low cost and the second one is tag based counters that are highly accurate so we want to get the best of both worlds we want to achieve both local costs and also high accuracy I will explain how we achieve that but before let me explain how these counters work so we have mini DM roles in our DM device and we have some counters that we want to map these DMs too。

And hash based counters do the mapping using hash function。

 so they take the raw ID and give it as an input to the hash function and get the output hash function and use it as an index to counter table。

 so this effectively maps each of these theals to these counters one of the counteries in the counter already。

Since we are using tax functions， hash risk counters can be implemented with local structures because they can do the mapping without using tags。

And also they can aggregate mineral ofs activation counts together because we are basically representing this information with a fixed number of counters。

 so these two things make hash base counters low cost。However as you can see here。

 has based counters have one downside which is some counters are shared with some know some D rows share one counter and in this example whenever we have an activation row zero or row4。

 we increment the same counter so this introduces a little of inaccur and tag based counters have the benefit in that case because each of these tracks one rows activation counts and we basically tag these counters with raw IDs and we increment just one counter when a specific D rows activated so this gives us high accuracy。

And our key idea is to use low cost and scalable hash based counters to track most theorem nerves activations with low area and use highly accurate tag based counters to track only a small set of theorem nerves to achieve low performance overheads。

And to this end we propose， come has two key structures， the first one is the counter table。

 which maps each DM to a group of hash based low cost hash based counters as uniquely as possible using an algorithm frequent item content technique called the Comp technique。

And it triggers a prevent to refresh to an aggresss victim role when the ag counter group reaches an activation threshold this way the counter table tracks D activations at low area costs。

And the second structure is called recent tager table。

 and it allocates highly accurate per Dra row counters for only small set of theem rows too that are activated mean times。

 and this helps us reduce performance penalties by increasing tracking accuracy。

And this is a high level summary of howcom operates。

When there's an activation row A Com first checks the counter table that implements hash based counters and gets an estimation based on that。

 and at the same time it checks the recent tag table that has tag based counters and gets another estimation and Comt uses the recent tager table based estimation when there's a tag match because we know that tag base。

Coters are more accurate and after that comet compares this estimation of the activation count to the prevent preventive refreshed threshold and if that activation count reaches the threshold it prevent aly refreshes victim。

And there are more details， operational details for K in our paper。

 I invite you to read that if you're interested in it。And let's look at the evaluation methodology。

 So we evaluate the performance and energy consumption using cycle。

Level sorry cycle levell simulation using re trend deeppower。

 these are the system level configurations that we use for the simulation。

 We compare comet against four state ortho theral hammer mitigation techniques namely graphene。

 hydrodega and cara and we evaluate all these mitigations across being a single core and eight core work load mixes and all our data and all our source code open source and you can check it out from this link。

So we analyze， let's continue with the hardware implementation and the area analysis。

 we analyze storage and area overhead using cacti and this is the comparison of comet against Grine and hydroa for the raw hemit thresholds of 1k and 125 this is the area overhead of comet so as you can see when we decrease the raw hemit threshold。

 comet has actually a lower area overhead， this is because when we go to lower raw hemit thresholds we need to store fewer bits for the counters。

And this reduces our area overhead。And this is Grene's area overhead。

 as you can see it's much like significantly larger than Com area overhead。

 and this is the area overhead of Hya， which is pretty similar to Comts area overhead So we conclude that comet increased a significantly less area overhead than Grene and a similar area overhead of Hya。

Let's look at the performance and DM energy overheads of comets。

 so we evaluate the average performance and D energy overheads of comet across single core applications here。

 and this is comet's performance normalized to a system with mitigation across different row he thresholds and as the raw he threshold decreases。

 comet has a small performance overhead over the baseline because its issues prevented refreshers as opposed to normal mitigation being in the system。

And this has come as the energy consumption normalized in the same baseline and it shows a similar result。

So we conclude that comet prevent Sps with very small average performance and die energy overheads compared to a baseline with nor hammer mitigation。

And this is a performance comparison across single core applications of come against four stage of mitigation techniques。

 and this is the result for the raw hammer threshold of 1000。

 and when we go to lower row hammer thresholds， as you can see all mitigations have some performance overhead increasing performance overhead because they all start signing preventive refreshes。

And here we see that comet upperforms all low area across mitigation starting from the raw hammer threshold of 500。

And we conclude that comet includes a small performance overhead over graphene and artperforms hydrja at all rh heic thresholds。

And this is the same analysis across eight core mold programs where gold mixes and the trends are pretty similar to single core ones。

 and this is the same analysis but for D energy comparison。

 this is single core applications and as you can see all mitigations have some energy overheads because they are starting to issue more and more preventive refreshes and we see that comes so consumes lessDM energy then all low area cost mitigations for all raw helmet thresholds。

And it incurs a small Dm energy overhead over Grene and consumes less Dm energy than hydra。And。Yes。

 these are multi core work results loss and again， they are pretty similar to single cor ones。

We have more results in the paper starting with secure analysis of comets。

 which shows that comet prevents all row hammer beat loops at all row hammer thresholdshots。

 we have a sensitivity analysis you know sweeping some configuration values with more details and explanations and insights。

And we have comments performed on the adversary of her when there is an attacker run at the same time in the system。

A comparison against stroke wind based mitigation techniques and performs version at hydro her thresholds。

Comt is local source and architect related and I invite you to check our Gi report so let me conclude this part of the talk Our goal is to prevent raw hammer bigs with low area performance and energy overheads in highly raw hammer vulnerable D based systems our key idea is to use low cost and scalable hashbased counters secured to track Dams the proposed comet which tracks most Drals with scalable hash based counters employing the count stage technique to achieve a low area costs and tracks only a small set of Damrals that are activated many with highly accurate per Dral activation counters to reduce performance overheads and our comprehensive evaluation shows that comeE achieves a good tradeoff between area power and energy costs outperforming state of theact techniques。

So I can take your questions ask comments and then we can move on to the other paper。Yes， please。Yes。

 the area overhead。This one。Why is。So usually when we go to lower oh yes。

 so the question is do why those comet has lower8 overhead when we go to lower row he thresholds so。

Let me explain the other mechanisms first， so when we increase the number of aggressors。

 the other mechanisms basically need more counters。Because the aggressors are increasing significant。

 but with comets， since we can use just a fixed number of counters and represent that information by sharing some counters and introducing taglist counters as a backup mechanism。

 we can keep the same table and when we go to a lower row hammer thresholds。

 we can represent that countervalue with less bits。So the tables size， the elements。

 number of elements are the same， but the counters are getting smaller。

 that's why we have a smaller area。counters aSo we don't need a reversible hash function because so let me maybe go back to the mechanism slide so that I can maybe point to things so let's say that we have an activation row a and we check the hash based counters we basically get like an estimation out of a group of counters that are access the hass and let's say that the other part is not important there is no tech so what we do there is we assume only the row a is activated that many times and refresh its victims and we don't do anything for the other Vs that might be sharing the counter but the next time they are access the countervalue still over the threshold or at the threshold so they are also being refreshed。

Any more questions？Thoose if you break now or after a breakfast。Both are fine， I think。Maybe be so。

🤧Okay， okay。So。It's。I expect it to take less time because you already covered the background and the goal。



![](img/7f334abb35d970f23850ceddaf8f42f2_34.png)

So the second paper is called Oocus， all Bank Act counters for Scalable and low overhead drove he Mitigation。

 which was presented in using Security 2024。

![](img/7f334abb35d970f23850ceddaf8f42f2_36.png)

And the problem is the same， no existing mitigation technique prevents raw hammer bit phs at low area performance and energy costs。

 and our goal is to fix that， especially at very low raw hammer thresholds。A book's key idea。

 which I will talk about in the next slide is based on this key observation that we make on how workflows interact with the main memory。

I will show what we observe over an example， and here is a system。

 the system with a CPU and4 DRAM banks， and as you can see each DM bank has a DMR at the same row address highlighted with label row X and a work written on the CPU generates this load request targeting Bank0 and row X in the beginning of this timeline。

Okay。So the CPU shows the request to its target bank enroll and if you piece this access pattern for other banks。

 there might be other requests targeting different drops at the same time。

 but this does not contradict with our observation。

 eventually the CPA accesses the same row address across all banks and we call the roles with the same address sibling rows。

There are two causes for our key observation， first one is the intrinsic special locality in workload memory access patterns。

 so a program usually accesses neighbor and access blockss at around the same time and the prominent access pattern that leads to this behavior is streaming through the elements of an area。

And the second cause is a modern physical address to data mappings that place neighboring cashbs into different banks。

 but into the same data row。And they do this to leverage bank levelual perilism to get the most out of the available DM data transfer band。

And this plot shows our Q observation across many tested workloads。

 I will not go into too much detail of this， but I will explain what we did when a row gets activated row heitation times which is 500 in this figure we record the activation count of that theM rows siblings so each box in this plot shows the distribution of sibling rows activation counts for a tested workload。

😊，So about this horizontal green line in the figure shows that if a robe is activated through hammer threshold times。

 its siblings are activated more than half the row hammer threshold times。😊，And therefore。

 if you can track the sibling with the。Sorry， if we can track a sibling that is activated the most。

 we can get a good estimate for the activation counts of all its siblings。

And we depict this analysis for a smaller raw he threshold， 125 activations。

 and we find the key observation to be more prominent at the smaller raw he thresholds。

Let me quickly introduce an important problem that we did not talk about existing per bank activation counter based mitigation techniques。

 There are many many banks in the Dm chip。 So the number of banks and thereby the number of activation counters increase with the newer Dm generations。

And we have already seen that sibling ros have similar activation counts and our key idea based on that is quite simple。

 it is to use one activation counter for all sibling ropes and reduce the number of counters by a factor of the number of banks。

😊，An obus objective is to track the maximum activation count across all sibling rows using just one count。

If， for example， the activation count of sibling roles look like this。

 then the abicus counter value for the sibling roles will be equal to RV larger than 97。Why， because。

If the abicus country is smaller than the maximum activation count， we cannot mitigate its Philips。

 Therefore， this would make the mechanism not secure。 If it's larger。

 we will have increased performance and energy overheads from unnecessary prevented refreshers so we will have lower performance and because of these two reasons our key design goal for Ooccus is to keep its countryvalue equal to the maximum activation count。

😊，And I am implementationation of Obius leverage's one prior works namely Grene's activation contracting mechanism。

 and for more details on how we implemented this， ObiUS， please check the paper。😊，Yes。

So let's move on to the evaluation， so this is pretty much the same as one I showed you earlier and let's move on to the single core performance and energy overheads of Oocus we show here the system throughs on the y axis across all single core workflows for the raw hammer thresholds that are in the axis and the higher the bar here is the better。

😊，And this is the DM energy overhead， a smaller values better here。

 and we conclude that otheroc prevent fit with very small performance and DM energy overheads compared to the baseline with no he mitigation。

And this is the eight core performance comparison of abacus against these state of the mitigation techniques。

 and this is the full plot and here are the boxes for aoccus showing the distribution of performance across all tested workloads。

And the red boxes show the mitigation and raw he threshold configurationfiation。

 which aoccus art performs。😊，And。We observe that Abucus art performs hja and para at all he thresholds on average across all workloads。

And we also see that Aoccus increased a small performance overhead overhead grip。

 which we attribute to Aoccusus's unnecessary preventive operations due to its low cost agatro activation tracking mechanismss。

Here's the same plot both for D energy， and you observe that aoccus consumes less energy than hydrode and para at all tests to draw he thresholds。

And for example， starting from the raw herit threshold of 1k actually， and for example。

 Abuquecus consumes approximately 20%， 70% and 34% less energy than Hyega and paraa at a very low raw herit threshold of 125。

 and Abuquecus performed similar to graphene in terms of EMM energy。

 that is only 4% higher at the lowest raw herit threshold that we tested。

Let's look at the area overhead of Ooccus。And we again， did this analysis using in cacti。

And this is a comparison against graphene and Hya and as you can see at the Ro1 threshold of 1000cus in is a significantly smaller area overhead than graphene and it takes up smaller area than hydroa。

And at the lowest broitation that we tested， which is 125。

 Oocus takes up significantly smaller area than graphene。

 but hydro area overhead is actually smaller than Ooccus。

 but you know that it comes with a great performance overhead， which I showed you earlier。

 and we did not include Drga and Para in this analysis because they don't have processor area overheads。

 the processor chip area overheads， this is because Regga does not change the processor chip。

 but it introduces intrusive chip modifications， and Para is a secure random number generator。

So we have more stuff in the paper， more analysis and details。

 starting with the security analysis that shows Ooccus prevents all hemeterps at all drug he thresholds。

 we also have these analyses， single core performance and energy comparison and other analysis as well。

And some discussion on Ro press。I invite you again to read our paper for these details and let me conclude my talk。

 so based on the key observation that many workloads access the same row address in different DM banks at around the same time。

 we develop aoccus which uses one counter to track the activation count of many rows with the same address across all D banks and our results show that aocus induce small performance and D manage overheads at very low raw hermet thresholdials and outperforms state of the mitigation techniques。

A bookcase is also open open stars and architect evaluated and you can check this link and test it。



![](img/7f334abb35d970f23850ceddaf8f42f2_38.png)

And this will be all for this part of the talk， I'm ready to take your questions。

I saw him personally。 Okay so the role in one bank has a lot of activation refresh that all the siblings。

 right。Oh。Yes， all the victims of its sibling wrong。 wasn't this。

Block back inter with you are new refreshing all the events。 And the key idea of back interning is3。

Go facts。Okay， I'm not sure if I understood correctly。

 but I will repeat anyways so you can stop me and ask your question again so。Aoccus。

 let's say that we have one robe in one bank that is activated many times Aoccus will still refresh all victims of all the its sibling ros and the key idea of bank level interl is to。

I， I guess I lost you at that point。 Yeah， because you when you access。

 let's say row 1 in fact1 I would immediately after that access row  one in fact2。 Yes。

 but during that time， you're refreshing。I see。 So you're saying that these refreshes。

 preventive refreshes could also take some time and bandwidth so that you are not able to access other banks。

 That's true。 This is also the case。When you have like preventive refreshes regularly without being this。

But so yeah， we could see some slowdown based on that。

 but we did not observe a large slowdown coming from that only。I don't know if that explain。Yes。

 please。 So in slide 36， you describe。

![](img/7f334abb35d970f23850ceddaf8f42f2_40.png)

26， yes。What， which one inside 3636。Oops。I'm trying to go back。那是。Okay。Yeah。Many slides。

 many animations。So this one， yes， this is the post slide。哦。

To do do a single counter across multiple banks is that the number of banks are increasing。So。Here。

 actually， I was explaining why the area overhead of existing mitigations are increasing with the increasing number of banks。

 so they allocate these counters or basically calculate these counters the number of counters based on assuming one bank。

And。When we multiply it to all like Dams all D banks it is like increasing a lot so what we are trying to do is we are trying to come up with a mitigation technique that scales well when we increase number of tank and our observations is that the DMs with the raw with the same raw IDs they are usually activated as like similar amounts right and therefore we are grouping them together basically and we are using just one counter。

Does that explain or answer your question， Yeah， I was thinking you。Second question was。

My understanding is that you implement these you evaluate using so we implement these in the memory controller specifically so I think everyone is back so we can start the next part of our lecture in this part of the lecture we will be talking about industry solutions to the Ar disturbance the sign I gave us some presentations about what we have in academia today and now I will briefly go over what is industrial to prevent roll hammer。

For a brief introduction， I am a researcher at softwareware Research Group and I'm a visiting masters student in EthH2H。

 my research interests are in our contract architecture， memory systems and hardware security。

I have a fun fact about that picture get I told me to prepare a brief self introductiontrouction life for this morning and I realized that I don't have any pictures on myself and while I was going through my pictures。

 I realized that I had a picture from a bridge in Buenos Aires from when I presented the same paper that people talk about today and I think it's also a nice coincidence that you have this such a beautiful bridge while they're talking about industrial relations。

 I think it' is a very principle design example to show that how something can be elegant while。😊。



![](img/7f334abb35d970f23850ceddaf8f42f2_42.png)

While satisfying the needs of a design， so this bridge can。

Allow pedestrians to walk through one side to another and when necessary。

 it can rotate and allow bridges to pass and I think in our designs we should enforce such principle designs as Giri talked yesterday a bit in the earlier days。

 industry solutions， for example PRR， I think weren't that principled because they decided to go for security by obscurity and believed that or maybe they thought that their designs would be unbreakable。

 however， many works show that these earlier versions of the designs were not secure and they could observe bitflips if you reverse engineered them and' flashing two papers that by pasts these earlier versions of mechanisms。

😊。

![](img/7f334abb35d970f23850ceddaf8f42f2_44.png)

I think it is getting better today industry is no longer trying to be obscure with their design。

 they are updating their standards and they're openly telling us how these are being or how these should be mitigated The latest JDC DDR standard as of April 24 introduce introduce the new mechanism that we will talk about today and by the end of the lecture I'll let you decide if this is a principle tohe resolution。

😊。

![](img/7f334abb35d970f23850ceddaf8f42f2_46.png)

So the paper I'm going to talk about today is understanding the security benefits and overheads of industry solutions to DM heat disturbance we presented this paper at DMs Research Ds Workshop。

 Edisca this here here's an executive summary of the paper， as we mentioned multiple times today。

 the A chips are becoming more vulnerable to eat disturbance。

 the latest JD DDR5 standard introduces a per evacuation count mechanism to mitigate these errors。

 however no prior MSD Pras Saan performance overheads。

Our goal in this study is to rigorously analyze and characterize the security and performance overhead of the overhead of these new mechanisms。

 Our mathematical analysis and extensive simulations show that PraC provides security as long as not be lip structure before in accessing a memory location too many times PraC has currently nonnegligible performance and energy overheads for today's the chips and is poorly skilled the future the chips that are more vulnerable to raw hammer where it induces increasing performance and energy overheads。

😊。

![](img/7f334abb35d970f23850ceddaf8f42f2_48.png)

We also show that PraC is a memory performance attack vector where an attack can exploit its preventive actions to mount memory performance attack and hook a significant amount of D throughput。

😊，Our implementations and scripts are promptly available in Reulator too。

 and I believe most of you use Reulatorators already。

 so if you're after the lecture you have some burning ideas about crack or you want to check the implementation or rather some applications yourself。

 you can just use the implementation or how post to it。😊。

So I will go through the background fairly quickly because most of this was mentioned today as you all know D modules have chips in chips。

 we have D banks in each bank we have D cells that contain data。

 these are connected through word lines as roles horizontally and they're connected to sense amplifiers vertically with bit lines to access the DM roll so to access D data and D we perform three operations first we a a role and bring the data into sense amplifiers。



![](img/7f334abb35d970f23850ceddaf8f42f2_50.png)

Then we use read and write operations to retrieve or update the data。

 and then we prechar theol and prepare the DM bank for access to other roles。

Aation and precharge operations take time because the science amplifiers need to reap the charge in the DM cells and restore them doing the while doing these operations so DM manufacturers said timing parameters to make sure that these data the data is being accessed correctly two or three important DM timing parameters that we will talk about today is first TS。

 which denotes the minimum amount of time and almost remain active for before we can safely close it。

And TRP， which knows the minimum one of time you need to wait before closing your row and opening another one these two DM timing parameters combined is the neutralized CRRC。

 which is the role cycle time that defines how frequently they can access DM rows in the same time。

As you all know， if you repeatedly open and close rows in B during induced speed Philips。

 in our study， we refer to the raw he threshold as the number of activationations necessary to induced first bitfi。

😊，You also know that the raw hammer thresholds has been decreasing significantly。

 therefore it is important to efficiently and effectively prevent this bit。😊。

One potential way to prevent these attacks is to prevently refresh victim roles before they observe bitflips and the industry solutions that people talk about today are also using this approach。

 they track or estimate the activation count of aggressors and prevent the refresh victims before they observe bitflips。

😊，嗯。So one might think that okay the manufacturers are starting to employ all miigs and isn't it solved。

 can't we just track activations and perform the refresh。

 a major problem with preventive refresh is when to perform when you're doing to tracking IndiaRA module because the memorial controller does not know when has been activated many times。

And because the preventive refresh is a blocking operation。

 the V module itself cannot decide to start a preventive refresh because at any time the memoryial controller could try to exhaust those block locations and cause fault operation。

😊，To prevent this， one of the early J there specifications to introduce a new RFM comment。

 I think this was around 20 and 20 where they introduced the RFM comment。

 RFM command allows the DM module with time to perform preventative replace。

 you can think of this as a contract between the memory controller and DM module but the memory controller is saying that hey。

 I won't access this location for a set amount of time。

 you can perform necessary activations to that location。😊。

We will cover two industry solutions that use RFM commands。

 first is periodic refresh management or PRM for short where the mem controller periodically sends these RFM command to give time to DM module for preventive refreshes and the second one is the most recent one per evacuation counting ya backup which we will call track where the DM chip internally tracks rawvaations and render all reaches a critical value。

 it requests RFMs from the me controller by sending the new backup signal。

We will start by looking at the execution of PRFM here on the left we have our mem controller and per bank counters and on the right you have our DM module the memor controller defines the memor controller determines the frequency to the RFM command by tracking the activation count of each DM bank in our example。

 the me controller sends activates the DM module out to one of the banks h critical activation threshold which we called RFM threshold once the threshold is reached。

 the meor controller clears the counter and sends an RFFM command to the DM module to allow five more preventive refreshes however。

 as you may guess， PRFM performs tracking with very low accuracy because each DM bank contains thousands of DM rolls and they all share the same counter therefore PRFM results in a high number of preventive refreshes and induces high performance and energys that we will discuss later。

The second inive solution， this is the one that has been introduced in April of this year， is PC。

 this PRC they decided to couple each DM with a counter that tracks the number of times that it has been activated。

So that the mechanism can check these counselors or use these counselors to accurately refresh the victims of each aggress role。

However， currently these counters are not perfect because they are not updated in parallel to DM exses。

 but rather these counters are updated when a DRM rub is closing because of this。

 enabling PRX increasess critical D timing parameters。😊，Yes。

 I have a table for that so these are the most important timing parameters that change as you can see that some of them relating to the minimum amount of time that we can keep through open decrease while the one that are related to keeping the waiting for another rate increases。

 I think the most important timing parameters here is TRP and TRC as you remember TRP is the amount of time the always thermooma stay close for and the TIRC is the Philippp of which we can access the the。

We will talk about the implications of this time in parameters to performance in a bit。

So here I show another memory controller and D module。

 but this time the memory controller is not performing any tracking and the DRA module has further activation counters in a pre system the memorym controller sends activates until one of the rows reach a critical value which we will call the backup threshold once the backup threshold is reached the D module sends a backup signal to the memory controller indicating that it needs time for preventive refreshes once the signal is received the memorum controller has a fixed amount of time where it can continue scheduling requests。

In our example， the memory controller sends another activates， however。

 the memory controller can fit three more activates into this。😊。

Window once the window of normal traffic ends we enter the recovery period where the memorial controller must send an RFM command we didote to track implementations based on the number of RFM command they sent during this period。

 for example in our example the memorial controller will send two RFMs in the recovery period and we will call this implementation for example。

 a track to implementation。😊。

![](img/7f334abb35d970f23850ceddaf8f42f2_52.png)

So these were all described in the documentation that I showed in the beginning of the slides。

 however， what is not shown here is how you should configure these mechanisms and how secure they are based on their configuration。

😊。

![](img/7f334abb35d970f23850ceddaf8f42f2_54.png)

We perform a worst case excess pattern analysis it's been known as the wave attack or the painting attack in the literature to obtain the maximum amount of activations an attacker can achieve and we sleep both the defense and attack parameters to obtain the highest activation count possible and attacker can achieved so I want to talk about the wave attack briefly so one might think that don't behave these thresholds can we just set them to be less than the rohe threshold that they secure against rawhier vips let's look at this example in a PRM system where the raw hammer threshold is five and the PRM threshold is four。

😊，If we attack a single role， we observe that before we can access the amount of activations necessary to induce a bitflip。

 the controller will send an RFFM command and we will refresh the victims of our aggressor successfully preventing the bitfs however we can be a bit more intelligent in our attack and use decoil rows in the second example we will distribute our activations across multiple roles and after four activations the number controller we send an RFFM command and refresh one of our decoy roles。

 we will continue our attack by attacking the roles that were not refreshed in the previous RFFM command where the number controller will send another RFFM to refresh our second decoil role at this point we have a single aggressor that has already the bit activated three times and we have four more activations in the bank therefore we can easily induce bit flips in the system before the next RFM。

😊，Therefore， secure configuration of these mechanisms is nontri and requires extensive analysis to be secure。

So I will share our configurations and secure panel as results。On the x axis。

 we will see the defense parameters that we set while they are confi these mechanisms on the legend for PRFM。

 we will see the attacker parameter that is the v x size。

 the number of rows they stack the attack it and on the y axis。

 we will see the number of activations possible to a single row。😊。

I will show an example on how to read this figure first。

 let's assume that we configure our system with an threshold of 256 and our system has a raw threshold of 1000。

😊，We consider the bars that are below this line safe while any bar that exceeds this line is considered assay for a system to be secure against an attacker all bars for a given configuration must remain below that line。

 therefore this system wouldn't be secure with a threshold of 156。😊。

Now I reveal a lot of the figure to show what each configuration show the security each RFM configuration provides。

 we observed that RFM PRFM must send RFM command very frequently to prevent bit at relatively low low he threshold for example。

 to mitigate a low image threshold of 128， the PRFM would need to send an RFM command AV8 activations。

We repeat the same analysis for track， the xx again shows the back of threshold for the defense parameter。

 the y axis shows the maximum activations possible。

 this time the legend shows our different track configurations defined in the documentation and each bar will show the reverse case possible attack pattern that we choose for the attacker so you don't see the wave type parameters here but each bar displays the verse one。

Once we repeat the analysis， we observe that t is configurable for secure operation against raw hammer thresholds as low as2 because an attacker can obtain 90 activations to a single row on the platform computation configuration。

😊。

![](img/7f334abb35d970f23850ceddaf8f42f2_56.png)

We evaluate the performance and energy of both mechanisms using Reulator22。

 we implement both mechanisms in Reulator 22 external Reulator 2 the here power to able to。😊。



![](img/7f334abb35d970f23850ceddaf8f42f2_58.png)

Analyze the energy overhead of these mechanism， we use a realistic four core system with the DR5 module that has two ranks and 64 banks total We compare has three state of their own mitigation mechanisms first is graph which is the best performing but as Nia short has huge overheads as NH decrease we have para that consumes the least amount of among the mechanisms that we discuss the least area overhead but has highper overheads and Hya that tries to strike a balance between by keeping some stuff in DM while caing them in the memory controller to be able to keep the low area overhead in the processor chip and low performance overhead as well we evaluate 64 64 load mixes from different benchmarks we evaluate four types of industrial solutions first is PRFM as we discussed where we are sending period RFM command。

 the second is and where the me controller sends and RFMs relief back， we combine。

Both and evaluate pre+ PRM where number controller both sends periodic comments and send RFMs when a beov is received and pre optimistic。

 which is our hypothetical implementation that is track forward with no change in the Iran timing parameters。

 So track has two sources of overhead。 The first is that once the PR send a backov signal the number controller starts the execution and starts sending IM format So that induces overhead。

 The second is that pre changes certain Iran timing parameters and reduces the frequency of which we can assess the the rules to be able to assess which overhead is coming from where we have the hypothetical analysis in our results as well。

😊，So I will show our performance results first on the x axis we have the raw he threshold and on the y axis we have the normalized performance。

We first observed that PR induces non negligible performance overheads due to increased excess latency because their hypothetical implementation without these increase timing parameters does not show such overheads。

 we also observe that it relatively highhi thresholds praphine and hydro outperform tract。😊。

We also see that as raw heitation valve decreases tract overheads stay relatively constant due to performing prevent fishes。

 while once we exceed the raw heation of 64， we see that practice performance decreases significantly。

 this is due to trackinging vulnerable to a wave attack and needing to be configured for very low trigger configurations。

We also see that optimistic outperforms all the evaluation all the value mechanisms up until lower he of 64。

 however after this point we see that due to being vulnerable to the wave attack its。😊。

It does not perform better than these mechanisms We also see that PRFM system perform over significant increase as MH degrees。

😊，We also I also show the energy results index axisV the aromahimeter threshold and y axisV the energy results。

 we similarly see that TreC has high D energy overheads due to the increased D timing parameters。

 and we also see that Tre's energy overheads scale well untilmeter threshold of 64。

 however it has large overheads after the aromahimeter threshold of 64。

And we again see that purean diamine hit significantly increases as low habit decrease。😊。

We also evaluate an excess pattern that triggers the most amount of backups。

 at least amount of applications possible， we see that once such an adversary pattern is used to trigger many backups。

 we can hook up to 79% of the Ds throughput of future D chips。

 and this results in a degraded system performance up to 98%。😊。

We have more results in the paper where we describe each mechanism in detail and we share more results or we also explain more about our pet models。

 we also share simulation results about the memory performance attacks。

 our paper is available on archive or theSa Work website whichever you prefer and our implementations are fully open sourced。

😊，Now I'll conclude my talk and mention some future directions about track。

So vi rigorous analyze and characterize the system and performance overheads of these Neil introduced industrial solutions zero meet disturbance。

Our revolution show that Cs security against slow heations down to 20 has high performance and energys for today's data chips and it poorly scales the future data chips indu higher system performance and energy geos。

 we also show that CEC can be exploited as a number performance attack vector so with significant amount of Ds throughput。

We conclude that more research is needed to improve practice by first reducing the overhead between increased data climbing parameters at high level thresholds。



![](img/7f334abb35d970f23850ceddaf8f42f2_60.png)

Solving the exacerbated performance impact due to wave attack as rawhi material decreases and stopping its preventive refreshers from being exploited as memory performance attack vectors。

😊，It grows all the orientations， basically。Thank you for listening。That concludes my talk。

 I cant have any questions you want， if you any。So which of the four mitigation are used in an industry。

 like the archive。Okay， so you're talking about the configurations that we value these right， Yeah。

 which So track is new， and we hypothesized that。 So if someone could have implemented and we wouldn't know。

 for example， professor would showed some slices where there were like patterns showing that they have raw him accounting cells。

 right。S5 x pre is not out there yet， so D chips don't have pre implemented。 However。

 I think RF FM has been out for a while and。If someone is implementing this probably on the other。

So the first one is probably out there and the other three he's not at the moment the J says possible it's optional at the moment correct is it's also very new so it like came out in April so it's very hard for them to roll out chips and memory controllers that support this because changing the D modules is not enough for this you're providing the D chip to become an intelligent agent not totally intelligent but a partially intelligent agent and the memory controller needs to obey that so the process that also needs to support。

So we will need better memory controllers， I'm not sure if it's possible with a form or update but。

You need signal， like doing a read request or。It sense that when the road is closing。

 so once you close the role， it leaves the countries and increments them at that time it can understand that it's hit the threshold and send the signal and it's not an instance thing that it has some latency because it it's on the slow path。

But it starts inserting the signal while or all scores。

Would it be the case the another controller is issuing some other from that。

It can be that's why we have the window of normal traffic so you have a duration for the me controllers to so you're not cutting the execution in place you're just indicating to the memor controller that it should start sending some RFM comments in the near future so you can have some slack it's not that instant。

Do you have some attack patterns in your mind to work on this。No， no，的。三再个时该始。W。监度这边可发责。つけまでよし。She。

对对。So I did not get why could please me on for the。So this is a hypothetical system。😊。

So you're saying that I can't go above without the un， right？

So this is it is because we are evaluating like a PRFM system。

 so we configured di threshold to be four So for every four activations to year and bank。

 the meor controller stands on a command。 So that's the period four activates oneFm4s one of。😊。

So那本来说。Yes， in the second example we do。It induces bit to it because we use the data so maybe I'm not understanding question so the RFM so part set different RFM comment version the one we're talking about just gives you a bank group or bank address and tells the DRA module that you can do your operations for that bank。

 the tracking is done by the DRA module therefore it's not saying that refresh that refresh that it's just saying that per fresh operations in this bank and the DM module is responsible for refreshing the maximal accelerated role。

So we are basically overwhelming the because the period is set period period is constant。

 we are overwhelming the mechanism here okay， so it was not in the plan that I will deliver this lecture but Hason had a health issue so he need to go to go see a doctor so I'm covering for him I hope I will deliver it in the best way possible。

 but yeah help me out here ask questions during the talk well so we can have a more reliable discussion。

So this talk is about drop press so yesterday I mentioned drop press a little bit。

 I talked about the memory access patterns， how you can play with the memory access patterns and you can make the redisturbance exacerbated and here is the full paper that actually explored that so within this talk I'm going to talk about this paper and there's a followup that was published this year in the AsN conference in 204 I will talk about that as well and also some other works from other groups that explored this phenomenon。

So the high level summary is we demonstrate in this paper and analyze a new redisturbance phenomenon that we call Rob press that causes bitweps in real DM chips and we show that WordPress press is a redistance phenomenon that is different than raw Ham much and hopefully I will convince you that it is different by showing some experimental data and we demonstrate that R press can be exploited in a from within a user level program。

 we just have a proof of concept for that but we are expecting security researchers to come up with more effective attacks。

And we also provide some effective solutions to WordPress press in this paper。So let's draw press。

 if you hammer some rows。But while you're hammering， if you keep your row open for longer time。

Then it has an additional disturbance effect， basically it's purely based on keeping a row open for a long time and when you do that you can cause bit phs in adjustment drawers and these bit phs do not require mineral activations。

😊，And in exhibit only one activation is enough to induce a bits followed。

So let's see the experimental data。O。Here's a more pictorial description of this meorial access pattern I already presented to you yesterday。

 so I'm not going to go over it， but essentially as you increase the time your role stays open。

 you can reduce the necessary activationctua count to use a。Okay。

 so Ro significant amplifies Ds vulnerable to read disturbance and it has a different underlying failure mechanism from raw hammer these are are two key takeaways from the experiments of characterization let's talk about the characterization working a little bit so we use this FPG based infrastructure structure again it's the same infrastructure structure called D B and we have the same temperature control and we have finally in control over D command timings etc。



![](img/7f334abb35d970f23850ceddaf8f42f2_62.png)

In this work we test 164 DDR 4DM chips from all three major manufacturers and here the names are already disclosed and as you can see it covers like multiple manufacturers and different times dsities and revisions。

 so whatever we explore in the following results is something common across all these modules。

Unless otherwise specified。So the major takeaway is I already talked about them。

So the key characteristics six of row press are like it amplifies the redistance in Dra in the sense that it reduces the minimum number of raw activations needed to induce a bit oflip and this reduction is as large as like one or two orders of magnitudes。

And in extreme cases， only while activation is enough and it gets worse as temperature increases。

It is different from raw hammer because it affects different set of cells when you look at the intersection of the sets of cells that are vulnerable to raw press and raw hammer。

 it seems quite disjoint。😊，And it appears different as access pattern or temperature change compared to Ohio hour。

Okay， so let's look into the first set of experiments that result in the first T takeaway。

 So now we check how many activation count to industrial hospitals changes as。

We keep roles open for longer time。So in this plot。

 this is pretty much the same organization for across like a lot of plots in this paper。 actually。

 So on the X axis， we have the a row on time。 So it specifies when we open a roll how much。😊。

For how long we keep the row open before we send the prege command。So from left to right。

 it increases from 2 seasonal nanoiseconds to 30 milliseconds。And the marked some importance points。

 7。8 microsecond and 70。2 microseconds are important points because you need to send it refresh。

So there are two types of refresh you can sorry， two types of refresh scheduling that's far from today for the DR for DM chips so you either send the refresh command every 7。

8 microsecond so when refresh comes you need to have your rows closed so you need to send a precharge so you cannot keep your row longer than that time and there's an extended refresh scheme where you can actually have 70。

2 microsecond of time window between two refresh operations so you can keep your row open for that time that much time。

And here the shade around the currp shows the minimum and maximum。

 I forgot to tell you that the y axis shows the minimum activation counts needed to induce the first pits。

So the leftmost point where we keep rows open for 36 nanoconds is the Ro hammermer access pattern and as we go from left to right。

 we actually have first a mixture of rope press and Ro hammermer and it goes through op press later。

And you can see， actually， the first part， there's some plateau until this point。

And then you see that the minimum activation company decreases a lot。

 so that's where ropress becomes more dominant。Okay， I already talked about this。And yeah。

 please pay attention to the slope on the Y axis。 it's a logomic scale， right so between every。Ts。

 actually， we go from like we go down by an order magnitude， okay。

So here is the curve so this curve was only for one module。

 sorry one di revision manufacturer Samsung8 Pgait C die。

 and this is all di revisions from manufacturer Samsung。

 so each curve corresponds to a different di revision and density here。And the common thing is。

 so the important thing is the behavior is common， right。

 we see say the same decrease in all of them。And this is data from all cell manufacturers。

 so we see some similar patterns。And based on our。Among the chips that we test。

 a reduces by 21 x on average when tiagon increases from 2606 to 7。8 microconds。

 so it's quite practical to do actually。And in the extended region。

 each only go for 191 times of decrease。So ropeper significantly reduce the se as tigon increases。

 okay？So here we look at the。Hello，呵呵。😊，Okay， so here we look at the effect of temperature here so here the data any data point below one means fewer activations to cause Bophils so here on the y axis again we have the ACmin but now it's normalized so we run our test at 80 degrees Celsius and then we normalized the value to the value at 50 degrees Celsius so it shows you how much it's affected by increase in the temperature so if the data point is below one then it means that fewer activation cause B Phils at 80 degrees compared to 50 degrees and as you can see in the beginning when your teagon is low then there is not much change actually with the temperature right this is like average across a lot of cells anyway and as you increase Tgon there's a significant decrease around this region around this region around this。

Region and all these are like the low one， right， So it shows a very strong correlation with theal setup。

Relation， let's say， with the between the temperature and the low press v。

 So I increase your temperature， drop press gets worses。Okay， so this is our takeaway。

This is actually part of the proof of like the difference between raw hammer and raw press actually。

 because in raw hammer， if you remember from yesterday。

 it has if it's more complex relation with temperature， when you increase temperature。

 it doesn't necessarily mean that raw hammer will get worse all the time， but for raw press。

 it's a more straightforward relation with temperature。Okay。

 let's look at the difference between lowpress and Rohammer。

 so we look at the cells vulnerable to lowpress and rawhammer in this plot。

 so basically we just calculate the population of the intersection between ropress vulnerable cells and rawhemer vulnerable cells。

😊，So this overlap is like the fraction of the intersection ofunion， right？

And here you can see that we have a large population when the aggress on time is low here and as we increase it。

 it suddenly goes to very volume is very close to zero。

 so it means that as lowpress gets more dominantly disturbance effect going from left to right。

The intersection of ropress and rohea vulnerable cells actually decrease a lot。

And charging 6 nanoconds， for example， is actually pretty much rawhammer anyway。

So whenever it's only like this small fraction of theorem cells are vulnerable to both draw press and raw how。

So it tells us that。These are actually in myths in different types of cells。

And most cells are vulnerable through low press， yeah。

 most of the lowpress vulnerable cells are not vulnerable to。

Then we look at the directionality of the Rohammer and rope press bits Phillips。

 so directionality means that do you Philip bit from1 to0 or0 to1 and the observation based on these tests is that the majority of Rohammer Bi Phillips。

 Philip from zero to one， but raw press bit Phils are more dominant going in direction one to0。

So there's another difference in this behavior。And the last piece is the effectiveness of the memory access pattern in terms of your hammering or pressing from one side or from two sides。

So the takeaway is that S Diegogo increases。Sing sized straw press becomes more effective compared to double size。

So here on the Y axis it's a bit complicated， but let me walk you through that。

 So we have the difference between single and double sided AC so data point below zero here we compare these two AC mean in cases of double sized and single sided access patterns and。

We get the diff of that， right。 So if the dip is below0。

 that means that fewer activations are necessary to cause thes in single side of op press compared to double sided rope press。

 And as you go from left to right again， you make your oppressor more dominantance with star phenomenon。

 then the single sided attack or access pattern becomes more effective than the double sided one。

 And this is completely opposite of Rohammer。 Actually。

 you can see Rohammer point here as well on the left side in Rohammer。

 it's a very widely accepted observation that double sided attacks are way more effective than single sided attacks。

😊，啊。Okay we already talked about sensor to temperature actually。

 so I'm just going to skip that and I'll talk about some real system demonstration。

 as I said earlier this proof of concept in this paper。

 we use the I5 based system that uses a Samsung module that we verify that it implements the TRR mechanism to Mira Ham bit Phillips and yeah RTI needs to proof of concept progress program that keeps D row perform longer by keeping on accessing different cache blocks inside the same row。

So this is our example code， basically you go access an aggressor row and then you go access like another column in the aggressor row。

 another column in the aggressor row， and after that you flush all data and then go back to the loop。

So here as increasing the number of cash blocks that we access， we try to keep the row open longer。

 we actually put some incentive to the memory controller to keep the row open longer。

And we have a test on 1500 victim rows that shows that as we increase the number of cash flow reads。

 we can actually start seeing some pitophillips that we would not see before。 So on the X axis。

 you see the number of cash flows that we read and on the Y axis， it's the。😊。

Excus it's the total number of bits fors。And。And as you go from left to right。

 first you don't have any Biphilips and then after some point you start seeing bit Phillips。

And basically division raw press， our system induces a bit full of。

 You cannot fill it with using raw hammer。So this paper was published in Ike2023， as I said earlier。

But later on， we kept working on this paper。 So if you look at the full paper， actually。

 on the archive version， the original paper is supposed to be like 11 page one。

 and you can see almost like 10 pages of appendix or somethingsung like that after that so the paper size actually almost doubled that's because like we tried we went more rigorous even after the paper published So it's a general tendency that we do in our group actually。

 the research doesn't stop by published paper。 So we keep improving it。 So in this example。

 this algorithm1 old is from a paper that was published as the isco version and then later on we improved this real system demonstration by using algorithm2 we did just like this small change here。

 this flash operation goes to top so that you access the memory more frequently。

And as a result of that， you can induce even more bitphilips so I guess it's important to see that you know you can induce bitphilips but it's also important to say that when you play with your code although it' more you can improve it so there is actually some headron for improvement so Ro press is a new redisturance phenomenon think about Rohammer it was first discovered let's say not published but discovered in like 2012 because the work starts around that time and it was published and widely known by 2014 and we had all these like sophisticated attacks over the last decade right this is just discovered like last year and this is just some proof of concept demonstration on real system。

So。And did this actually change a lot of things because it reduces the necessary activation count in your quite a bit now if your rohe mitigation mechanism is。

😊，Configud for like activation count of， let's say， 500s。

And by using this you change Spwebs at like 300 activations。

 now you change just bypass them right so there is a lot of opportunity from system level research perspective as well。

So how can we mete raw press， so we propose a methodology strategy of adapting the existing raw hammer or mediation mechanism so that they can also mitigatete press and how we do that。

 we basically take the row open time into account and here on the X axis you see like the row open time Rangle left。

It means less robot for locality when you go write more rope press， more robot for locality。

 more rope press。And you have already the service。On the bio axis。

 we see the minimum activation come to in the first bit followed。

 so this is a cartoonish picture of how it changes based on the experimental data， right？

So instead of con yourvi mechanism at this orange point。

What you can do is you can limit the rows open time by changing the row policy in your memorym controller。

 you can ensure that even if you have upcoming aes you can close row at this point so based on this term you can you can get your raw hammer threshold from this Y point to this point So by doing that you can actually protect against row press。

By reducing the threshold's so we explained this like this in the paper。

 you can also think of like from the other way around instead of reducing the threshold effectively you can do the same thing by if if you observe that error is staying active for longer time as as you go like in the memory access pattern you can just keep increments in the activation counts as well right So if you don't close drop for like let's say 15 andseconds。

 you can increase activation count by one even if there's no new activation So when you do that。

 the activation count will increase more rapidly and it will reach the original threshold so it's effectively doing the same thing from the other way around so there's another paper actually in the field that will be published in micro this year like next month。

 basically。Called impress that does that。So these are our in results for so we adapt two of the existing ro mediation mechanisms we are in and para by doing this change and here are our performance overhead results and we concluded our solution metetro press at no additional performance overhead。

Okay， so the conclusion is that we demonstrate this WordPress press。

 a new white special disturbance phenomenon， we characterize a lot of chips and we demonstrate that we can exploit WordPress press from a user level program and we provide effective solutions to WordPress press as well。

So the good thing is all the methodology， everything is open。

 everything is available on GiHub and there artifact evaluated as well。

 so I guess there is this website called Zenodro， I guess they are there as well so you can find all the necessary information there。

😊。

![](img/7f334abb35d970f23850ceddaf8f42f2_64.png)

![](img/7f334abb35d970f23850ceddaf8f42f2_65.png)

Okay， so the interesting question。Now we have raw hammer， we have raw press。What if we combine them。

 So if we craft an access pattern thats partial little hammer， partial littlepress。

 can we make the attack even more effective？ So we are looking for this kind of question。

 Do you think it's reasonable。Or maybe before this， I should stop and ask， like。

 do you have any questions aboutrop？No， okay， any ideas about combining them？

So we did some initialized experimentss。So basically， we have these two rows our aggressor rows。

And we keep hammering one of the rows while pressing the other one。

So they're attacking to the same victim role over there， right？

And this is a paper that was published in the disrupt track of the ASN conference in this year。

 we basically combined these two access patterns and we tests these access patterns in 84 different D chips from three major manufacturers and our team show that combined pattern takes significantly less time to induce the first between compared to both raw press only or raw hammer only and the initial steps Philip are different across rawham Ro press and combined patterns。

And our hypothesis is that the reserv caused by raw press from one of the two aggressoles in a double side pattern is much more significant than the other one。

So our baseline access pattern is like single sided raw hammermer or raw press here。And。

Basically we use the teaagon parametermeter again and sweep it from 2 or6 nanoconds to some other values and this is our conventional double sided th hammerop press attack so we have the rory as a victim and we sandwich it from both sides here right and we agents to the tiagon volume for。

So if I to combine them。We have two different Diego models。So we can perform raw hammer for one。

 draw press for the other one。And we use the same infrastructure again and we look at the two metrics。

 one of them is the time to first bid Philip， so it go ahead。Are youside low press attack。

 Because when you want to do a low press。这个。今 having the same going to go up because we。我好惊啊。Yes行。

It's not simultaneous so you open one row okay the question is like how can you perform double sided row press if you can only activate one row at a time so you open one row you press it for some time。

 you close that row you open the other row and then you press it sometime as well and then close and then do it repeatedly。

系我 find the between like one months or。It totally makes sense。Not with。

 maybe with current chips as all。 I'm not sure。 So the thing is， based on the like the。

There' on Dham communication protocols。You can only open one row at a time in a D batch。

 even though you have sub level parallelism and you have the robot or separate for each sub。

 unfortunately you cannot open like two rows in different subs at the same time。This is by the。

Gedic specifications， you know， if you， if you operate the D Ram chip in the recommended conditions。

But I'm guessing that yeah， actually， owner already talked about it last week and if Mil will probably talk about it sometimestime soon that in real D chips。

 you can actually do that， you can open more than onero。

 actually minerals all of them at the same time and think about the effect of oppress if you just open like 32 different rows all。

😊，Another project。Just see。H。The question was like。

 how can you open the sorry can you open two different rows in two different subines so that you can simultaneously press different rows？

而且。And we look at the AC min。 you're already familiar with ace min。

 So these are the chips that we test。 I'm not going to get into details。

 And let's look at this results。 So the green curve shows the single sided straw press or raw hammer and double the orange one shows the double sided attack and the purple or。

I'm not sure which color is that purple blue， something like that show the combine I'm referring to this chart。

And the important thing that you need to see here is that the blue or purple curve is below the other curves。

 right， So on the Y axis， we look at it the time to first bit Philip。

 So it means that for given aggress on time， if I put a line over here， for example。

 then it cuts the blue。Sooner than orange and green。 So basically by。

Playing with your access patterns by getting a hybrid of hammer and ropepress。

 you can actually reduce the time that you need to induce the first bit for。

 This is the total time of the attack。 And these are some significant reductions。

 And you want these in real real life attack scenarios because it means that the malware detection system。

 for example， does not have enough time to detect your attack。Okay。

 so here we look at the we look at the same comparison。

 but this time for the total activation count and we see that by by combining patterns。

 you can reduce the necessary activation counts quite significantly。

 So while you are pressing one row and hammer in the other row。

It can actually reduce the activation come to the level that your。😊，Press in the row， right。

 But then since you're hammering the other row， the attack takes the total attack time gets much shorter as well。

O。And this is coming across all three manufacturers。

So I guess I already talked about this and the hypothesis is that when we do rope press from one side。

 like the one of the aggressor rows have more effect on the victim role compared to the other one。

AndThere are more results in the paper， Bilip direction and the overlap of Biwills similar to the WordPress press paper。

 and you can see all of them in this full paper you can access from the Cur code and you have all the slides already it uploads on the coursework page so you can find them。

Okay， for the interest of time， I'm going to skip the conclusion I already talked about all those and I'll move to more low level discussions。

If you don't have any questions， but I can get question system。

As a the comparison of the attack then this。我不开始。do that thing just because。I mean。

 as far as I think before。FirstThese minutes， a number of activations。

 but no press because you could keep your movement so long。The character the。Yeah， exactly。 so。

Is it this one， No， I not this one。Okay，So this is not showing it completely， but。Yeah。

 I think you cannot see it here So the question is like can do we have a comparison of the total attack time for Roham and Rodress that that data should be inside that is Ka3 paper check the X archive version it should be there I think。

I don't have it in this slide。It's not on top of my head。 Yeah， because I mean。

 changing a number of activation is。Okay， but again， we want if the time decreases。冇 bigger。

So it depends the question is like does the total attack time decrease in is the bigger problem。

 so it can be a bigger problem if you're racing against those like system level malveitation systems and T wire software blah。

 blah， blah， but at the same time， let's say your raw press takes longer than your raw hammer attack。

But you have some very robust straw defense mechanism。Configud for a high threshold。

And with our press you its your with low threshold， right？Then the attack can' take longer。

 but you achieve it Philips while withdraw Henry Cha get with Phils。

So I think the approach should be like considering all of those altogether。😊，Other questions， Yes。

 so correctly mentioned that row press and roll hammer have different idea temperatures。

wish they tend to work better I think instead that row hammer of a very specific zone temperature low bread generally something different course the higher temperature gets。

 so what I'm talking about the kind of combined attack because you you gave a thing or other they effective。

 I don't think you mention the temperature to which the data is collect is it perhaps the case that well。

 if you buy a specific。attack battery versus a high temperatureable or is thaturistic to determine when they given temperature bound。

 which is the screen better considering now the adding possibility to。That's a very good question。

 yes， so any terrific repeat question。So，呃 so。Essentially。

 does combined Roham ropressz attack work better at all temperatures or because like Rohammer and Roperz have different sestimities to temperature。

 do we take into account， I think in this work？There is another extensive temperature study for this combined attack。

 so the thing that you said about like maybe there is a temperature point that Roham Rone or Rore only works better than a combined。

It's possible， yes。Or you can so about Ro hammer's temperature sensitivity。

 it also varies across the south a lot。And you can't find diram cells that are like ky of vulnerable to raw hammer at let's say。

 80 degrees Celsius。And you know that raw press gets worse as temperature increases。

 so you just try and cut your system temperature to 80 degrees and you will get a better cold mindful。

So anything is possible， I guess in。ok。Other questions。Go ahead。There was just。micro secondcond。Okay。

I' know let stick this。这个个。Let me see if if I understand。Oh。来一首歌吧这死。对那。

7 micro Is that extrapo or actually。So this is based on the FPJ based experiments， right。

 So we can easily go。 it was very easy test to do my FPG based platform。

 So this is real data from real chips。 It's not extrapolation。So， the is。Dal Draship appears。

So you plug a real DRAM chip to any FPG board and FPGA board， we don't have a more controller。

 we have our own design DRAM B and it allows us to do this task。

So if you just try running that test on your laptop， for example。

 it's not possible you cannot keep that open for3 years。Yeah looks too。Yeah。

 it doesn't look very linear actually when you zoom in。

 but it looks linear because both x and y axis are like in log scale here。😊，ok。There other questions。

Okay， so here's a list of paper not to scare you just to give you more data points or pointers that you can check。

 but this is about。Like this is not very comprehensive。

 but I guess we have during in March all the essential papers here。

That talk about the circuit level mechanisms that cause these redististance issues。

 So how many people are from D here， How many people are from D。A lot， okay。

So if you guys are curious about the circuit level phenomenon， I just you can appreciate this more。

For people， it's usually not that interesting， but I think it's really important。

 even if it it can be boring or painful sometimes it's really important to understand these things actually。

 so Im I'm going to go through some brief overview of this。😊。

And then I think we will conclude on time。So。This is how your DM array looks like so so far we were putting some like circles in a two dimensional array and they were connected to our lines and mid liness right so here we have our these like vertical light gray bars and our bit liness。

And the horizontal dark gray ones are the word lines。

 So you basically put a high voltage on this word line。 and now you activate themselves cells， right。

 So in this today， this is more like the six sub square is the。

It's like considered as like the state of the art or the common layout in like today's modern D chips。

 so here the goal is， okay we need to keep in mind that the goal is here to increase density as much as possible。

 right？So here we do not put like D south， like one D cell here， another D cell here。

 another Dm cell here， So D south are actually in this tilted way。

So we have this thing called active region， this blue part here。And on the blue part， on both sides。

 we have two storage nodes， so these storage nodes are essentially your capacitors。

And so we are this is like a top down view right So we look at the chip from top and we see like two capacitors here and there is a bit line contact。

 which is drawn as red color here that overlaps with the bit line。

 So basically this is the contact that connects your D cell to the bit line。And this blue parts。

 the so called active region here form the transistor and this your capacitor is connected to this orange part。

So basically， you have this one capacitor， oneter resistor Dra cell implemented in this way。

So now we will look at this cross section in this axis， so this was like top down。

 we will look strong front like to this side。You look around this site now。呃。It looks like this。

So the color coding is the same， so you have a storage of contact， the orange or yellow ones。

 I'm not really good at colors and this is your midline contact and you have the midline over there So basically this is your bitline connection and this is your Dm cell and this forms an access transistor here and this。

Excuse me。 This AWL is called the。It's the wordline over there。Okay。

 so once you put high voltages to your world， essentially。

 it it formed So it attracts some electrons around the world from the source rate to here， right。

 Some electrons are accumulated here by here。 And as a result。

 you have a channel between your storage node and the bit line。 So that makes your access transistor。

And since these two world lines are too close to each other and they are sharing the same substrate here in the same active region。

There is a cap cross talk。This is like one mechanism that causes the disturbance issues。So。

 essentially。But could。呃。Like high voltage on the victim capacitor and low voltage on the a capacitor。

 And you activate this work。As a result， you have some electron passing and I forming a channel over there。

 right， And since this is。Low voltage here。 This is high voltage here。

 There are some electrons moving in this direction。And once you close the row。

These electrons are released。So they were in the part of the channel here。

 and now you do not attract them by putting high voltage in this aggressceral。So as a result。

 these electrons are just like going wherever they want to go right based on like wherever they' are attracted to and some of them just go back to the like base here。

 the substrate the remaining parts and some of them actually go to the other words line because in another other word the other store is not somewhere here because this is like the same region So you don't have isolation between these。

2 cells， active regions。So this is like important cause of the。Of the诶。Ira service。

So this movement of electrons also creates some charge traps here， sorry。

 there are already some charge traps here and。They cant capture electrons and one electron gets stuck here for example。

 for this charge trap you can see that it's I mean。

 it doesn't have to show it in this picture actually。

 but there can be some charge traps in the oxide of this worldb as well or the gate of the access transistor。

 so when you have some electrons stuck there， the accessor based charge ni。

And that's another reason that you have redisturbance here。而且。🤧。😊，So呃。

I'm not sure what I was explained here。 So okay， okay， so in this case， testing wordline is on。

 So yeah， I didn't talk about this。 So in one active region。

 we have two word lines going through the active region。

And outside of the active region we have also two other worlds that are so the activity stops here。

 it doesn't go to the side， but there's a so we call these passing world so these are not connected to these two cells but they're connected to some neighboring cells maybe I can refer best to here so that it's easier to understand。

So for this cell， these two word lines are going through the active region。But these two word lines。

Are going to going those are the passing robots。 So this is like the other adjacent of the row。

 right， And they are not used for this cell， but they are used for this cell and this cell。🤧。

But they're so close to each other because we have this tilted layout here and it's all for improving density。

Okay。😊，So once you， if you activate your specimen or light。

 what happens was you so you have eye here。And you have some electrons accumulated here， right。

 They're attracted to the high voltage。And then。Once you release this。

 these electrons can go anywhere。So these consider that these electrons are coming from like anywhere in the activities。

And then when you release them， some of them can go to the storage mode。

And some of them can get stucked around there as well， and that causes the exaceated leakage。So呃。

Yeah， not all。So when you have double sided draw hammer access pattern。

 you basically hammer one active or land one person all the time because like those are the two neighbors of。

 let's say， let's say this D self is your victim。You hammer this wordline and this wordline。

 one of them is active， one of them is passive， right？So。So when this one is off。And you turn on PWL。

 electrons， it accelerates electron migration from this active region to the passive or line this age。

 basically。And when you。When you呃呃。Yeah， basically it traps more electrons here。And。It's。

It's basically how we explain like row press here actually， but this is not the slide for that。Okay。

 I'm missing one slightly here， I yes。Maybe we can repeat this class with how later on。

But essentially when you have these two aggress rows， one of them is AWL， the other ones PWL。

 one aggress row is on the other one is off and once you activate this one。

 you attract electron on this side， once you activate this you attract electrons this side and they get stuck around the victim row and this causes the。

R Ham。When you do this very frequently， the electrons go back and forth very frequently and there is a higher chance that they can get stuck and they can exist chargedly because so it's why double size draw hammer is better than single size draw hammer。

 but when we look at the peing gate effect only。This this。

Basically performing a row press kind of access pattern on the specimen word line attracts all the electrons here right and then as a result you have more chargedly and it also indicates that you know the single side that might be better in the circuit load and that's what we see in our empirical observations on real D chips as well。

Of course these kind of studies require like more understanding so there are several groups I will show you the list of papers again。

 I encourage you to take a look at them so several groups that does physics simulations actually by modeling all these circuitry and they observe like which electron is going essentially。

 and they measure all the like exrbated charge leak as a result of that and try to understand。

We have some limited understanding today， we need more。呃。跟。

There are more aspects that we need to cover。So far， I guess this is all I want to say about this。

So are there any questions， yes？So looking at the she。か。Did you that the。

It would be8 next there two victims， but one of them may have more than the other。

Because it's like asymmetric， Which one is your active region and which is the possible。Yeah。

 so is there any as that you observed with one side tax。No。Yes。

 actually there were some modules so the question is is there a symmetry in double side that attacks aggress rows the effect。

One side， one side so yeah，而且而且 I understand。So we perform single sid access pattern and depending on if you choose a passings wordline or the active wordline。

 is there any effect？In some modules， actually， there is a significant difference。

So you hammer this row， it was particularly in some microbe modules， you hammer this row。

 and then you observe bitfibs in this row， you hammer this row， you observe bitfibs in this row。

 but whatever other row you hammer， you don't observe bitfibs in these two rows。

So hammer in this one does not include speech in this one， for example。

So it was something really particular in micro chipps。Some of them。But。At the same time。

 we also observe this。 So you hammer this。And then there are a lot of these cells next to each other。

 right， So you get a bit deterrate across the whole row。Just by hammering this on this victim row。

So put it on one side and then you hammer this and this one in a double sided manner。

Then you observe morbid Phillips in the struggle。So double size still makes an addition。But。

Single size on the passing word line was not really affected between those pitlips。Again。

 this is only true for like a small subset of the chips that we tested for many for for the rest。

 it's like。From both sides， you can just twisting and thes。Any questions？能。

So sometimes we affect the road that are not directly next to us。With only a hour。

 So is there any mechanism that explain like I mean， for example， somehow attack everyone that's two。

Yes， so consider that your。Ba子会。You're attacking this passings wordline。

This is your immediate adjustment， this is your like adjacent in not adjacent neighboring like total distance。

 right？So you can also attract some electrons from here， and they can also travel to there。

With a low probability， way lower probability。 So you， you need many more attacks here。

 So this is what actually the hospital double paper showed。 they do a lot of。

AndActations to this person wordline。 and then some additional activations to this one。

And also the victim refreshers activate this as well， assuming that they will refresh the throat。

And then as a result， the cumulative effect induced some between industrial the。🤧。

Then will for this sports。 it's impossible to program。

 right so you can only hammer your neighbor and to。

Your neighbour neighbor but you cannot time one that right。呃，有发到。喂你说。一个月。Yeah yeah A。Yeah， so。

Maybe I should go to this one。So you hammer this sorry hammer this wordline。

 you can those bit footages here like across this active region let's say and the active regions that this wordline is connected to are like quite far from this wordline so there's always a gap in between in this like cartoonish picture。

So you would expect like the effects being much lower， right？

That's another thing that people keep investigating actually， so I don't have a definitive answer。

 so I cannot say that it's impossible to do that。There are some papers that claim that when you hammer and Rome。

 you can observe bits for in 60 different throws。So where those six different rows are located。

 it's not very clear。But。Yeah， so there are those kind of observations。Yeah。

I saw a hand over there somewheres。No， okay。So I was supposed to talk about the simulation infrastructure and the testing infrastructure as well。

But we don't have time for those， it's only the 4 pm now。So I guess。

 do you have any announcements before we get finish， one more。Okay。

 you will have homework  one release tonight or the following day or tonight。 Okay。

 it will be tonight， and you will have two weeks， right， Yes， and there are some paper reviews。

 there are a lot of， not a lot of some exercises。 but it's care。 as you do more paper reviews。

 You get more bonus points。 So keeping that in mind。😊。

And please submit your homeworks before the deadline so that you get the full grade， hopefully。

Other have time on。But exercisees should be done before the deadline and we have。

So deadline deadline。Yeah also please consider that in the last minute。

 there can be always some issue with servers， you know。



![](img/7f334abb35d970f23850ceddaf8f42f2_67.png)

Okay， yeah， thank you very much。

![](img/7f334abb35d970f23850ceddaf8f42f2_69.png)