# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P9：-09-Lecture 08 - Modeling Modal Behavior.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Okay， I guess that。We can start this。Tell me not canonical birthday time。Okay， so let's see。

 does this work？Okay。So not so great。I don't understand why。Okay。

 so today we are talking about design methodologies as your TAs have done。

 they have written you and note， you know there are new slides in this part。

 the class is going to be rather different， what has been done in the past so please download the new material。

😊，So as you remember from the first class， methodologies are really the most important part of design。

 Meologies is the way in which you organize your thought process and the way in which you approach the problem。

😊，And if you are rigorous about it and well organized。

 then the design is going to be much better than if you just go fasterly and saying okay。

 let me try this， let me try that and then check so methodology is always an intellectual process and as such is based on certain principles most of the methodology are based on very simple principles because way of organizing thought are not that many and in general they better be simple the details are going to be complicated but the overall framework is simple and yet you can always say something new even at that generic level so we are going to talk about some of the model of designs that have been used in the past。

And I would like to give you also some industrial perspective so who does what in industry。

 which companies are using one method， which companies are using the other method and what we believe is a good approach to design。

 so come on。反正 ok。So and I'm going to use again an example that I know very well and that in general is very appealing because it's something that everybody knows。

 which is the automobile right so now if you look at the challenges today in the development of the car is essentially in the electronics part today more than 50% of the value of the car is in electronic。

 so everybody thinks that a car is a mechanical component。

 not longer is an electronic component dressed with mechanical parts。

 but the electronic part is the most important thing。😊，So when you think about safety。

 fuel efficiency， reduce emission without electronics， you cannot achieve it。

 So the big development in the past 20 years has always been on the electronic control side。嗯。

And of course， there is a great pressure from government。😊，Do have the minimum amount of。Accidents。

 right， so or malfunctioning， so which implies that the parts that are in a car have to be extremely reliable。

😊，So much reliable that， you know， when you're talking about 10 per per million is almost an impossible fitat to accomplish almost because。

 of course， people they。😊，Think about it。 And then in the end， they are capable of achieving it。 Now。

 if you want to know my honest opinion about all the advances in automotive。

 what we're due to not the customer the customer the only thing the customer cares is about showing off so the beauty of the car and two of entertainment system。

 everything else you couldn't give a damn right and so the people who are designing carss that want to make money they don't want to think about safety。

 they don't want to think about security， because nobody is willing to pay for it。

 after your debt maybe reconsider it。 but that is the point。 nor they care about pollution。

 maybe 1% of a population do like some of you may in Berkeley， maybe 90% of a population does。

 but in general in the world， nobody cares and so the only way in which you are going to introduce innovation is because the government。

Either you do this or you don't sell a damn car，0，1。 Okay。

 so you do it or otherwise you're out of a business。

And so the value of regulation is extremely important， not only in this domain。

 but also in another important domain that you may have read on newspapers a lot is about this net zero energy buildings。

 So buildings that don't consume energy。 they produce and they use their own energy。

 So this is a goal that the state of California set by year 2018，2020 that no new building。

Should ever have to consume energy。 Okay so it's a very challenging goal。 Now。

 you may worry about it because you pay the price of energy。

 but the price that you pay for energy in your home， it is sizable， but is not that sizeable。

 So thinking that consumers can drive innovation and can drive societal impacts。Is a dream， right？

 So you really have to have government in input。 So as we say before now it's by 2015。

 actually earlier， right now， is's about 50%。 So it's much faster than what was anticipated。

And the software shares grown up to 13%。 So now the other important thing is the pressure on time to market。

 Now in the past， to bring in a new car took about five years right， so you start from the concept。

 you do the mock cap， when you do the preliminary design， then you do the mule。😊。

It a that you drive around and you check it， everything goes wrong and then many things go wrong。

 so you fix the bugs and so and so forth， you build another mule。

 many things go wrong and you build yet another one and you build yet another one。

 So this was the past So five mules in general， five different prototypes were brought to market。Now。

 that is impossible to do any longer because the cycle is long and there are companies that can master new designs much faster time。

If you are interested， I will point actually we will post some slide by Fogen and we will see that method that I'm going to present today is what Volsewagen is used。

 but the time to market of a new Volsewagen vehicle is between six months。😊，Okay to a year， right。

 So huge improvement。And that is achieved by methodology and by eliminating all these mules right so if you think about when I started my career 1971。

 many， many ages ago， what happened is that you were designing a micro micropross not to be seen yet so it was 1980s when the micropross or era started。

 but when you design an integrated circuit， you just made it， when you test it， doesn't work。

 you fix it， you test it， you fix it， you test it now that was the same thing as automobiles like five years ago exactly the same。

😊，But now how come that now we don't？Make mules quote unquote for an integrated circuit because it costs too much right and you want to other products like cell phones and so on to come out to market really fast。

 And so what did you do， You re to what is called virtual engineering。

 So everything is done on the computer。Most everything， Okay， most everything。

There is still something that you have to screw drive around。

 but hopefully we are not going to need that any long okay so now why cars are so interesting because the functionality that a car has today is incredibly complex so what you see here is all kind of things that you have today so you got ABS you have electric steering。

 active suspension， electronic stability and so on and so forth right so many， many。

 many many different things most of the new stuff is related to safety so things that prevent accident to occur。

And there are two kinds of things。 One is called passive。

Safety and passive safety is like the thing blows in your face。 I mean air back。 right。

 So that's a passive safety device。 So you have an accident， and they。Prevent you from dying。 Okay。

 that's passive safety。 Now， the active safety is that if you find out that you are kind of falling asleep。

 the car stops or wakes you up。 Okay， that's active。

 So the maintaining the a distance from the front vehicle automatically is an active action。 Okay。

 And so the trend is to go from passive action to active action。 And eventually to go to complete。

 as we said， the first class to complete autonomous driving。 Okay， so now in order to do that。

 you have tons and tons and tons of devices。😊，And of course。

 you need tons of sensors because in order to see this distance from the guy front。

 you have to measure that distance in order to prevent you from bumping into a bicycle driver。

 you got to know that。So I would。On the side， you have recognition。

 So you have to do image recognition。 if you like， if you don't trust， receive that。Cyclist。

And then you have to take action based upon that， so tons of sensors or readers。

 or we say first class radar， cameras and so on so forth。

 then you have to have almost a nuclear computer in there because you have to do a lot of computation。

 for example， image recognition is not for faint of heart it takes a lot of computing。

plus you have to actuautor right so you have the braking and you have the steering of the wheels and so on and so forth。

 so you have autor， sensor computing， standard embedded system stuff except but now the number of devices that you have in the car is very。

 very large so it's a very distributed system and you have tons of functionality that you have to put into webcar。

Today， actually we say today0 minus， so today a couple of months ago。

 three months ago or something like that， the big design methodology for the architecture of the car was to consider one particular box which means a board for one function。

😊，There was the。Identification of one function， one box。 Okay。

 so it's like you have that your TV set is separate from your refrigerator。 Okay。

 so the same thing in separate function， separate things。 So each time a new function is required。

 Then the guy who is making the car ask his supplier， please make me a box。

 the box comes in and the supplier has to integrate this box into his frame。 Now。

 in order to be able to do that， then you have to have a very flexible in interconnection。😊。

In addition， does anyone know how many meters of cable is in a car today？Caabling。

 so just wires going all over。Well， guess。嗯。How much。Clloose， not white。No， no， not quite meaning it。

More。It'Twice as much as2 kilometers going to4。😊，Now， if you consider that stuff is copper。

 you multiply the kilometers by the average weight of the thing， and you get a lot of weight。

 which then implies that you are going to consume a lot of fuel， just to carry the wires， right。

 which doesn't seem to be so wise。 now， So why don't people go wireless。 Wi， wonderful， right。

 So I save tons of money because copper is expensive by the way。 any。

 any reason why I shouldn I should。Right， and why， because you can。

 you know you can hack into wireless。 But in any case， that is what they tell you。

 but that's not the reason。Yeah I mean， it's already connected right with talking about connected cars。

 you know there are all kinds of connections。 So you know General motors onstar。

 if you're hiking into onstar， you can take control of your car and it is wireless by way so that is what they tell you is not exactly accurate。

 what is more accurate is the fact that wireless connection is un reliableable per se。

 meaning that if the sun has decided to be slightly upset right so your wireless can be upset so if you get a signal from a sensor and this is not。

Received because the sun had an emission of electromagnetic something when you are in a problem。

 So is there a reliability more than anything else。 It's not so much the hacking。

 It is a consideration but it's also the electromagnetic compatibility。

 meaning that you are polluting the environment。 I mean。

 meaning polluting not in sense that you die carbon monoxide I all that can stuff but you are making the nearby of the car full of electro electromagnetic radiation。

 So if another car goes by and it's doing the same thing。

 you get the signal mix up I don't know how many of you are runners。

 but if you ever try to do a marathon or something with a lot of people around you and you have this beautiful things that measure your heartbeat and this net and up and down and your speed and then all of a sudden you realize that you are making for means per mile and you say great it's not you is the other guy And so that's the same thing。

😊，Is this cross correlation。 But that is a target。 I mean。

 the automotive companies are really thinking hard if that could be achieved。

 Another way is to have connectivity that is more effective。 Now， in the past。

 the connectivity of these things were mostly point to point。

Now is's no longer possible to do point to point。 So they have networks inside the car right And so in fact。

 that's the reason why， for example， for embedded system of a new generation。

 you have to know networking。And so that's the reason why I embed the system so interesting because you got to know about technologies of the sensor of technology。

 what is around， what is possible to do with the sensor of accuracy， drifting。

 reliability and all of that plus you have to know networking， plus you have to know computing。

So it's a lot of stuff that you have to know So this class is a little bit of everything right so the past week and a half you have heard about interrupts and V andette which is pretty low level stuff right is how to make a microprocessor work right now we are going to see how you do design methodology which pretty abstract thing so it is a very complex and interesting feel just because of the diversity that you have in front of you。

😊，Now。The interesting thing is that today is based on that because OEs， so the BNW。

 Mercedes and so on of this world didn't know much about electronics at all。😊。

So they needed somebody else to provide the boxes。 Now。

 what happens is that if you realize the teleic is the key。To the competitiveivity of your car。Then。

 you don't want。Other people to determine whether you can sell more car or not。

 you would like to be in charge， not only， but the value that the Os are capturing by whispering is very large。

 the margins。Of the Ter1 suppliers are much higher than the。So big mess， right。

 so the OEMM say vitamin， who sells the car， who makes the car。

 So we have to have the how to say the benefit of this。 So we are going to control。😊，Right。

So no more of the Ter1 supply。 But if you say one box， one function。

 the Os are always going to screw you。 Now， no question about it。 Okay。

 so the big thought about the Os about 15 years ago was。We take control。 So now on。

 the architecture of the car is us。Okay， and new OEM has to comply to what we tell you。 Okay。

 so think that they had to bring in a lot more in in。Intellectual capabilities is about me design。

 but in a different form， because it's about integration。😊，Anyway。

 so this one is the results was the proliferation of ECUs now if you take a BNW top of the line it about 100 ECUs。

 which means more than 100 microprosors in a car。😊，Okay， so you talk about complexity and power。

 computing power， that is really。Something to， to work。

On so there is a lot of cross functional side effects。

 all kind of stuff that is going on and of course there are missing opportunity for commonalizing the stuff it is becoming commodities by now and in fact if you start thinking that the electronic component is very interesting novel part for example。

 if you think about engine control so the actual engine is a commodity because more or less everybody does the say so why don't we buy standard functions of engine control so that that's the idea that was going around so tomorrow and actually almost today the idea is integrated modular architecture。

Now， what does it mean integrated model or architecture。 So if I give you right。

 So today you are after one week of class or maybe you don't have a feeling for these kind of things。

 but if I tell you。I want to reduce the number of ECs。100 is too many。

 but I want to use the same functionality as I used before。 So what would you do。

You had say 150 functionalities and 60 micropros。What can you do？ What do you have to do。

You have to put more functions on the same thing。One more thing。

 if you want to make your car more resistant to failure， what would you like to do？

Rundancy in what sense， because we have reduced the number of processor。

 how can you achieve redundancy？That's it。 So you have the same function and implement。

 So there is no more， not no matter how you look at， there is no more correspondence， one function，1。

Object， right in two ways。 One is that one object， when EC can carry more than one function and that one function can be distributed over。

Several components， right， So there is no more correspondence。 Now， if that is the case， really。

 the car manufacturer is the guy that calls a shop because he has a complete vision of all the application。

And so what will be the game， what is the game of the OEM to reach this conclusion is the fact that he will ask the Tier1 supplier to give him pieces of the architecture or some of his ECs right。

 so just the algorithm， just the algorithm， maybe the operating system on it， Yes， that's it。

And to some other provider， they will ask they。Soft。

And then they are coupling of the software with the platform。Is done by V OEM。 And this is Auto of S。

 Autotoar is a big deal。 You know， it's a huge consortium of everybody plus his brother that is thinking about this integrated modular architecture。

 Okay， So if execution architecture is completely selected and implement by V OEM。

 the OEM are free to standardize anything they want。 And each time a new function is required。

 the OEM starts a request of a supplier for a new functional content software to be integrated with rest。

Now， this achieves two goals。 right， So one is we already say。 I mean。

 it's the fact that you reduce the。Power of the supplier。 The second thing that it achieves is the。

Flexibility， now， for example， if how many times do you upgrade the softwareer on this baby。

 So maybe once a day。 So there is the fixes of your operating system。

 There is itTunes that gives you just now， you know， under megabyte or stuff， you know。

 any happens every time， right So think about the same thing for cars， right。

 So what happens is that you can make your car go faster。 for example。

 by downloading a new engine code not let type， you know， advocate this。 but in principle。

 you could do that， right。So that is flexibility that you can gain。

 So there is a new thing that you are putting in and then you connect to rest and the challenges are moving from specification of VCs to specification of software。

 Now what is the most serious problem when you do that now if I had you know standard computing things。

 I can always do this we have been doing it for 30 years。

 So why is more critical in the automotive domain。To do this approach。

 right so I add a piece of software， slap it into the existing platform and everything works fine。

What is the problem， What is one of the problems or actually the most serious problem？

And this will bring also to a very important component of the class of the teaching that we are doing to you。

 So what is going to be abroad？So when you have safety critical things。

 what do you need to worry about？Of course right and yeah the given the fact that functionally also Microsoft is always correct right so you know okay。

 let's give that as given right Corness is fine， but correctness functional correctness right And we are talking about when in the science that it does what's supposed to do。

 but there is one thing。😊，Yes， yes， yes， yes。 performance is timing。 Now。

 if I give you a platform that exists already in very software， a ransom a them platform。

 where I put in another function， who guarantees me。😊，That the timing is going to be maintained。

 right Now， do we have a good way of modeling timing in microprosor， The answer is， N， O， no。

Because all these babies are based on best effort。 so you hope that it iss going to go fast and the faster the better。

 but you don't know how long it's going to take。 There is no intrinsic mechanism that is guaranteeing you that the time is correct。

 right So the most important thing is。😊，If you do this。

 this approach is to guarantee that you add something to something that already exists and you are not disturbing timing。

My God， you know， that's not easy at all。 So being able to characterize the time which is associated with the execution of a particular piece of software on an existing platform where other things are running。

😊，Is of paramount importance。 So this is a basic challenge。That you need to face。

 Its a technical challenge。 That is a lot of research associated to it even today。 Okay。

 so it's not a solve problem。It is approachable， but is not a solve probe。 Now， of course。

 how did we cope with complexity， We already did this we have abstractions with tools and most of all is with methodologies which are freedom from choice。

 Now timing by way could be approached in some sense。 I mean。

 at least you can have an idea on what's going on。

![](img/d6a071a05bd08a10641cdec4df3f4954_1.png)

If for the communication in the network of the car， you are using。T division multiplex， TM。

RightY time division multiplexing because， you know。

 it's based on a synchronous assumption and there are times lots。

 So you know how it's much easier to control if you are staying within a。Boundary of a cycle or not。

 So using a rigorous rigorous restricted method for communication is a potential solution。 So。

 in fact。If you look at the most important evolution of the automotive field。

 you have that everybody is directing their attention to synchronous protocols。

So you hear about what is called T T。A， which is time trigger architecture。

 which is TDM Aオ now you hear about time T TP time trigger protocol。 You hear about T T ethernet。

 This is an interesting one。because when you say I want to have a synchronous execution right or something。

 does that imply that your actual wiring and networking be synchronous or not no？

What I can do is that I can write a layer， an abstraction layer that will make my application look the。

Connectivity and the protocoltos as being synchronous， But the reality where is synchronous。

 So the actual mechanism is asynchronous。But the abstraction is synchronous。

I can still predict timing。Now same thing when you do synchronous design in electronics， you know。

 just simple microprocessor stuff。You how do you accomplish it by the introduction of a clock。

 but the transistor per se are as synchronous right so when the signal propagates between registers。

 it goes at its own speed right， whatever。But the key assumption is that when you read the data that have been written by this。

A synchronous process。This data are stable。And that is a basic assumption of synchronicity。

 so you can always the word is asynchronous， so what surrounds us is based on real time。

 meaning physical time， which is a real number。😊，Plus asynchronicity right so we make it synchronous by restricting our use of the components。

 So is freedom from choice。 So it's a restriction of what we do Now this one is the V model。

 Now anyone who's anyone in industry as heard of the thenv model Now for me is one of the most horrible thing ever done but at least it some kind of thing that help people to reason about things。

 but is not a good way of doing things。 and I'll articulate why that is the case。

 but if you read any book of anything or you read any paper from industry。

 the like everybody is going to say， oh， we use the V model according to the V model we do this we do this we do this beside the fact that is not true。

 but is really not good right now what is the V model idea。

 now notice that this started in the 60s and guess。



![](img/d6a071a05bd08a10641cdec4df3f4954_3.png)

イventンティ。Any， any idea iss kind of funny， because I。I thought was the automotive industry is no。

Was the defense industry， but which country。The United States he was saying no is German。

 so Germany 30 years ago or more and said， okay， this is the way in which the design process goes on and their view of a design process is purely a linear process。

You go from the idea conception of your system， you go from the functional implementation。

You choose the architecture， you do the final application。 You integrate everything。

 and then you test。So that's the reason why it's called V model。 This is a design phase。

 and then there is a verification phase。 design verify。 Why is bad。Of course。

 you need to test during design。 This is the solution。 But what is the problem of doing Zoom， Zoom。

At the end， right so you have to redo your design。Know what your original design is going to be。

 And that was one of the major reasons。 The second thing is that what if you wanted to reuse part of your design that you had before。

Can do it right because you are starting top down right So you go w and if you hit something that you already had before。

 alleluja， but may be completely different right， So it says this one is in some sense。

 and nobody for better reason really is using the mode。

But it was possible to use it when the complexity was such that。

 you didn't need to verify right away， this was when we said before you had the rapid prototyping。

 you were measuring things after you build it and you could debug after you build okay。So that was O。

 was not great， but was O today is。Not good。 yet most of the people use this。Okay。

This is a very interesting point because if you look at the system industry， after all。

 system industry is what is producing very interesting products and the product that we use in our everyday life forget about cell phones。

 but everything else or computers， but everything else if we do use anything else rather than computers and cell phones。

 but assuming that we do when most of that stuff is developed with methods and approaches that are 40 years old。

So it's scary。 airplanes are done this way。Oh， airplanes。 Yes， airplanes， okay。

So you develop a subsystem， mechanical parts， ACU， the software， vein implementation， when to， to。

 to， to， you verify。😊，Now， many of you have pointed out already that the issue is finding the error late is a disaster。

 Now look at this tank， this is a demonstration。So the stage one at the requirements assume that finding about plus 1 to find the bag of software design cost 5 in looking at maintenance。

 So after you send out the product and you discover that there is an error cause 500， so 500 x。

The cost of discovering a bug。 So the sooner you do it， the better it is。 So this is not a good way。

 And so what do you do Well， you want to bring verification as early as possible in the design process as simple as that Now if I you see why the V model was proposed when you were doing prototypes because youd go all the way to the final product when you test it because you have the thing that you want to see if it works or not。

Now， we say that doing that is expensive。 So all of a sudden start thinking， okay。

 if I don't want to do the prototype， what do I have， The only thing I have is a computer。

 The only thing I can do is to do it abstractly。 The only thing I can do is to use mathematical models。

😊，Which implies though， that I can do verification early。

 but there is no need to wait until I have the entire thing to do the testing because in the computer world everything is virtual so I can do anything I want at any time。

 even if I don't have the actual piece。So all of a sudden then you can do the small V's or the small V in big V。

 so which means that every step has its own loop， lets say I design。😊，Check。Fix。And move。

So this is the process that actually most of the people are moving into。 Now。

 in order to be able to do that， though， you have to have a way of evaluating what your platform is going to do to your implementation。

 right。And so what you need is a model of the component of the platform。

 so the model of the computers， the model of the cabling， and all of that。😊。

And if you want to reuse some pieces of your design that you had five years ago and so on。

 that can be。Wonderful， because the models that you have for a platform are going to be very accurate。

😊，And so whatever you are going to do in the first phase of the design is going to be reflecting much better refiner implementation。

 So this is the way， Okay so to do verification early try to model what is going to happen in the future。

 right in terms of a selection of the component and so on， Allright。

So now we come to a platform- based design concept now this one turns out we proposed it like 25 years ago。

 but by now it is the way in which things are done now I completely forgot to insert the slides of the presentation of the CEO or Volsewagen just a few months ago。

 where he said that the only way in which Volsewagen is going to do where vehicles is to use platforms。

And to use platform based design。So the interesting thing is that this is not only for a electronic pair。

 but also for a mechanical pair。😊，So what does it mean to have a plus？The idea， in some sense。

 is that I want to have something that is mostly。Done， right， So that I have available。

 And I want to produce a new product by doing minor adjustments， right。

 but adjustments that are enough to fulfill the need of a custom。So， for example。

 in a Volkswagen case， in the mechanical part， what they did is that they fixed。😊。

The design of the front part of the car， you know， the axle， the front axle of the back。

 the back axle。We think that they last three， according to the models of where car is the distance。

Between the axon， that's it， right。So you customize your car by varying this parameter。

So that is really freedom from choice。 So you tell all your car designers， this is it。

 This component， don't touch it， don't even dream about it。 You can vary this if you want。

And I'll tell you which tools to use and how to do that。Very constrained。

 But this is a key to get more model correctly in the market really well。 Okay， so let's say I now。

The other important point of platform based design is the fact that a design is always based on two parts。

The part is what I want to do， so a function that I want to achieve， for example， safety。

 I want to make sure that I maintain the distance and how I do that right so then how I do that is the hardware platform。

 if you like right is's the kind of things that I use to be capable of sustaining this application。

So， for example， if I want to maintain the distance。

 what I need is a sensor that is measuring the distance right， how many such sensor there are many。

 but there are a limited number of so if I don't want to invent a new sensor I have a library of sensors。

 each one of them is characterized by a cost by performance accuracy， for example， by time。

 response time nowhere， and so according to my goals of my functional design。

 I will choose that sensor rather than that or rather than that。But， I have a。

A method right now of selecting the components of the platform。 So in some sense。

 the platform is the combination of all the elements that I have in the libraries right。

That that's all there is So now if you think about some of you know about designing electronic circuits。

 the AsIs right and application specific integrated circuits。😊。

Are design the digital part based on gates。 now， most of the people use logic synthesis So synthesize from a functional description into the implementation by selecting。

Gates out of the fixed library。It's the same concept。

Which brings me to the point that I told you before the design methodologies are good across a wide variety of different applications。

I a way of organizing your thoughts Now why am I why did I propose this method 25 years ago。

 because my opinion was capable of capturing this separation of function in architecture or function platform on one side and the other side of the fact that you can do the design by a steps selecting out of a library something and coupling it with the functionality that you need to select okay now if you frame your thinking in that way。

 you immediately realize that this methodology is not like the in which you go from the top and you go all the way to implementation but is a meeting in the middle。

Why it is emit meeting in the middle because my requirements come from the top is my goals。

 what I want to do with my design and the bottom up part is。😊，The libraries。

 right so that is something I have available。😊，It's an existing design that I characterize。

 and I decompose it in terms of these basic， beautiful components。 Now。

 in order for this thing to work。😊，I need to have all the component in the library。 that can be。

Plauck together， right， So I have to tell you if this component can be。Mix with this component。

 they can go together or not， because otherwise I run very risk of putting two things that don't。

Work together， right， So remember the Lego block kids。 you know， I remember very well， I mean。

When I was。For whatever it， I was trying to put Lego blocks that had separate different shapes。

 And so it wouldn't fit。Thats it that's exactly the same concept。

 The Lego blocks were the first example of platform based design with the connection with the rules about how you put together things。

 so you must have to do this， you have a functional model or abstraction what the system is supposed to do an architectural model is what describes what you can choose。

😊，And the mapping， the mapping is that process of taking the functionality and distributing it on the platform。

 on the hardware platform。Yes。HahaI knew next slide。😊，So now I give you a challenge。

 So this is a very good question now， how would you solve that phenomenon。

 So I have a platform existing， So I have a bunch of components， but I want to innovate。

 So do I want to innovate everything， Probably not， So maybe a piece， right。

 a critical piece that I had a great idea about， So how would I solve that phenomenon of introducing a new piece anyway。

😊，Any wild idea。There is the way， of course。The interface right， so for example。

 if I want to introduce a new piece， I want to make sure that the interface is。

And when I design that piece， let the interfaces comply with the rest of the world right or where I want to put it。

That one。Second thing is that how do you then， how do you。Organize your design for web piece。

 So one thing is very right is first thing we have to think is that interface。Now。

 the other thing that you need to think about， how do you go about it？Yeah。

 so the first thing that you want to do is that you want to have， you know， why do we want this path。

 you want to because it does something right with a certain characteristic， right。

 So you put in the functionality plus the requirements， right Now。

 what is the difference between a new object and an existing object， existing object。

It can already tell you what it can do what performance can support。

 when you have a book where you read when you design electronics is a dataship so it has all you want to know now for a new component it doesn't exist right？

The data sheet is actually your requirements， is what you tell it to do， right。😊，It doesn't exist。

 so that's a way you pose the problem so you pose the problem by saying by postulating that you have a piece that does what you want right。

And so what you do is that you give to the guy he is the guy you's supposed to design your new piece。

He has the constraints from you。 and then he's going off and doing that design。 Now。

 if he's capable of doing it， he's coming back to you， say here it is。 Now。

 you know that he is capable of doing that。 It works because you are design it in that way。

So you don't need to do the integration anymore and you don't need to verify the integration because it is correct by construction suppose you cannot do that and say I cannot do it so it comes back and say this is the best I can。

 then you have to reaccommodate with top level design and this is the smallly right。Okay。

 so that's the way you do it for。Yes， yes。All that。Platform， yeah， well， okay， So first of all。

 what is the definition of the platform， right， So if you think about it and how people use it。

 you can have all kind of different things， right， So a platform， for example， for some people is is。

And an architecture， a given architecture is a buff。Do you think that is a restrictive definition？

It is right， because it， it's one only thing that you have available to you。 It is a special case。

 right， So what you would like to think about， remember what Volwagen did， right， So thank God。

 they call it Pla based design。 So it's good for me。 But the key point is。😊，That they are。

They have a flexibility。Right。And so， you have to。Determine what is the flexibility that you want to give to your platform。

 platform is not any longer a singles。Pace， but is a family of pieces that satisfy a set of requirements。

For example， he very rightly said that the interfaces。

 so one constraint of the platform would be that all the interfaces are synchronous interfaces vi so pins have to be arranged this wayaving other way so on。

 right？So that is a constraint。 So that is a way of constraining the choice， freedom from choice。

 right。Now， it's interesting that most of the company I'm working on today。

Are coming from the point of view of doing custom design。

 Asistant companies love to do custom design， especially the big ones。 So I say， oh。

 my customer wants this。How takes 10 years， right？ I mean。

 suppose that you want to do the power distribution system of an airplane， right？ I mean。

 Jesus a big design， right？ And I say， oh， my cousin Boeing wants this。 and Ibus wants that。

 So I have to do two different design。 So， wait a minute。Power distribution is power distribution。

 right So you have different constraints， right， performance， maybe size， weight， whatever。

 but it is power distribution。 The function is the same。

 right Con may be different function is the same。 Why can't I organize my design using the platform。

 which means I have previous designs。 I have components of the design sitting around And the first thing I'm going to try is to see whether I can plug in my different components and satisfy Boeing。

 When I already satisfy Airbus。 Where is the difference， I may choose different components。😊。

But they all come from the same library， right， So I save a ton of money and a ton of time right instead of starting from scratch all the time。

 So the name of a game in any of his big system companies today is reuse。😊。

But if you don't put this framework around reuse， then you are on the risk of constraining too much。

And then you are not able to follow with technology advances and listen and up and down。

That's where the intelligence in design goes， right。

 So architect of the design is to choose what are the components， what are the rules。

And when you are allowed to add a new component as you pointed out。

 what do we do with new components， there you go。 So there is a librarian is this is exactly what I'm doing today。

 right I'm writing a paper for the UTC with Dea so thank you for asking I was on top of this Okay allright so so just to give you another rendition of what I'm talking about the difference between the platform which is a family of solutions which are parameterized by the library。

😊，And the behavioral components on the other side。 So what you do is that you have the representation of the behavior。

 representation of the platform， and the design progresses by allocating functionality to the platform so which is this mapping。

😊。

![](img/d6a071a05bd08a10641cdec4df3f4954_5.png)

So now when you refine your design， it's always a process of marrying pieces of things you want to do with pieces of stuff that can do things。

It's like you have wine and you have glasses， right。

 And then what you do is that you pour the wine in the glasses。

 The glasses have capabilities of a size。 how much wine you can put in the demo。

Glass and what are the characteristic of a glass I think that some of you may know that for good red wines of age。

 you need a glass that is made like this why because there is a performance associated to it and the performances。

😊，Oxygenating。The red wine。 Now， if you put like this， a white wine， you kill it， right。

You may realize that I like one。 Okay， and so there is a reason why for every wine。

 there is a difference。😊，Kind of glass。 And that is platform based design。 It is best。

 So you got the bottle。 you got the glasses。 you open your drawer and say， okay。

 what glasses are best for this bottle。 Sam thing， not different， the same。

 So platform based design of the drinking whites。 Okay。

 so now in order to evaluate if your design is good or not。

 you have to do performance analysis is not enough to do correctness of the functionality。

 It is extremely important to verify that the performance are okay， Why。

 Because in embedded systems are in general cyber physical system。😊。

The performance are key to the correct working of the system because if I give you a signal from the crash to the airbag which is delayed。

 you die， right， it can't be， it has to be that timing or less whatever。😊，Because otherwise。

 you have very serious consequences。 So we first pay to many other application embedded better the system do have to take into consideration performance to evaluate the correctness of the design。

There's one very few cases in which this is true Allright。

 so when you refine in the sense that if you like it， then you marry the functionality to the blocks。

 but now you may have some virtual block and you need to repeat the same reasoning one level below when you have everything that is available you say I'm done。

Anytime you still have pieces to work out， you go down in the cross。

So now if the performance analysis says bad， when you come back and you change something。

 you change a functionality， you add a new component， change you buy a more expensive processor。

 you put more memory， whatever and at the end of this process of evaluating alternative and so on when you are satisfied。

 you go and you go to implementation， so it' is another way yes。Is an architecture calling it Yes。

 so in fact， another way of looking at things， you know there is always a functional view and a functional view for those of you who are more advanced in terms of computer science and all is like a declarative language and this is what I want to do。

😊，So in mathematical terms， as I want to find x such that f of x is equal to0。

 I don't tell you how this is a characteristic of my solution， right。

Or I can tell you use the new toresan algorithm， what I'm doing give you a solution。

 and that solution is the connection of sub algorithmgos。

And so the platform has a component which is structural and structural means that there are components that are connected together。

Okay， so the components and their interconnection is。Characterize a platform， instance。

Because the platform is integral of all possibles，Given by by the。

One single connection with the wires and the block and all of that is one instance of the remaining solutions。

 right so that's the reason why I call it platform instance and that's the reason why I was saying before that is a special case right when when we discuss it okay。

Allright， so now if I take this view that I just gave you right this functional architecture marrying and so on。

 I take the view that I gave you over of the platform which was like the hourglas right in fact they are called ASV triangles with many initials over hourglass model because it looked like an hourglass right now you twist it around and you have a bow eye model is's the same but just twist it around so that you can can underline the importance of this process of you know functionality in architecture and marrying so the platform is a library resources right it's an infinite infinitefins a finite set of potential solution。

And notice with interfaces that they identify legal interconnection。 As you pointed out correctly。

 that is the key a key part of the of the。metodology， then you have resources。

 these resources do contain virtual components that are components that do not exist placeholder I want to design things。

That have that cup of meat。Very important resources are interconnection and communication protocol now the interfaces depend on interconnection right so because when I want to interface it's a special case that I want to interconnect within Martin directly I may want to interconnect through a network and then the network interconnect to Martin to you and so on so the network is a very important thing because we are talking have a distributed system。

😊，So and this is what I call the fractal nature of design because the process repeats always equal to itself at all layer of abstractsection。

 we say before the component doesn't exist。😊，So I have to implement it and I'm going to do the same thing all over again。

And so you can go down up to the atom level if you want to， So the reasoning is always the same。

So now this reasoning also implies that you have to have。I mean。

 you cannot do all this analysis that I was talking about the correctness with seeing if things can be plugged together and so on and so forth。

 unless I have a mathematical representation。RightOf all this processes。

Because this is a way of organizing your thought， but when I go down and do it， really do it。

 I need tools。And tools are based on mathematics because computers that what they are capable of doing。

And mathematics implies a representation of the word in mathematical terms。😊，All right。

 so is this is a fractionractal nature of design as we say it for automotive。

 so you have vehicle dell level， subsistent level， is U node level and down all the way to silicon level and the top down part is the partlet that refines the specification and the bottom up part is what。

Exports， the characteristic of the components that you have available or that you are design。

So that's the reason why it's meeting the needle， right， You have a top down bottom process。

But keep on going at all time。O。Now this one is another rendition of what you can do with this view。

 This one is the platform， you have network and computing elements。

 that is the representation in your functionality Now a question$1 million question。

The stuff that you see there is the functional，Is it， Yes， it is what you need to do。Now。

 is that an architecture or is that functional。He he。嘿嘿。你谁？Getting there。Think， think， think。 anyone。

 volunteers。Yes。It doesn't depend on the layer。Not really。

 the key point is that an architecture is always a combination of sub system or sub components。

 so what you see up there。Is an architecture of functions。

Is an architectural view of the functionality of the system。Is already decomposed into parts。

And so the fact that you can have a platform which sits all the way up here。 So in some sense。

 that is a platform it。From yet another layer on top of it that says I want my car to drive when I to go on the street and not to have accident。

And that is a way in which I'm going to decompose， you know， that requirement into pieces， right。

 parts that I'm going to implement。 So the concept of architecture is independent of fact that you have a hardware or software can be also software architecture。

 In fact， many people talk about software architecture。Yes。Ha哈。😊。

Haha remember what I say practicalal nature of design right So this one。

 if you look at at the top level functionality and this view here is this view is the bottom and the notational description of what the car should do is the top next layer down what we are talking about here。

 that one。😊，Is the top and that one down is the bottom。

So Matt is the point depends on what stage of your design process you are sitting。

So everything can be at the top or the bottom， it depends where you are。Okay。

 so now you see the marriage， now this is the mapping， so I'm marrying functions， Yes Nik Kji。

 you have a question？解？嗯。Now， it's a collection of architectures， what I mean。Right。在保。らいぐらい。Meicカ。

No， no， fact。 In fact， the library， as I say before。

 the library are the components of the architecture。 and in fact， in the library。

 not only you have to put the blocks。But you have also to put the connections。

The connections are element of a library。 Remember what the prayers like。So for example。

 you could say that you are considering in your car and in fact it is。

 right if you look at the car today you open it。You see at least three different networks that are going on。

 There is a CA network， the L network， and sometimes there is a flex rate。

 So there are three different networks。The L network is the one that connects with the sensors is point to point。

The CA network is the network， a synchronous network that has been used forever in automobiles。

 and then third one is flex ray is time trigger， partially time trigger architecture。

 which is the first attempt of the automotive industry to move to synchronous architecture， yes。

先给 tire大。Yes。你的。But those of the blocks that are in the library are the parameterization of all the components that you can build out of this。

系い。Okay。So this is a mapping， so when you marry the values function onto the ECUs。

Then you assume execution parameters such as Gitter latency， accuracy， worst case execution time。

 you assume the load and utilization levels， the resource usage。

 and then you map the two So in summary way， what did we learn Vi engineering is taking over。

No more rapid proizing。Okay， very。 So most of the design approaches are based on virtual engineering。

 So virtual testing on mathematical models， that's what is done。

 Top down linear process is not the way to go。 Never has been。

 It was a way of organizing thoughts when you had。Real prototypes， not virtual prototypes。

 and verification was only possible when you add the piece in your hand。😊。

Design is a medium middle process， so you have the specification from the top and you have what is available from the above the essential part of any design methodologies let that be the model horrible or platform based design wonderful is the fact that you have to have models right because any virtual。

Approaches as to add models。 And so now we are diving into the modeling part of the class。 Okay。

 so this is to explain why models are important。 right now。

 you may have heard and you heard a lot about model based design。

So model based design is actually any methodology that is based on models。 but in reality。

 the term model based design came from a specific approach to design。

 which was a particular step that was to go from a mathematical model to software called Auto。

 So to compile software out of mathematical representation， mathlab。😊，Siming description code。

 C code。 Okay， that was that transformation， right。

 that rewriting of the model into code that would go directly into the microprocesor， that process。

 It is called also code generation or code synthesis， whatever you want to call it， that was or。

Historically。Called model based design。 Then people kind of extended it to everything。

 plus his brother。 But that's where it was coming for。

 So it's not a general design methodology is a generic term。

 If you solve the possible methodology or it is related to a very specific set。

Of the steps of the design process。So what is modeling。 So， well， we know modeling is， okay。

 I have a system。 I'm trying to represent it in such a way that I can predict what this system is going to do。

When I deploy。So you do models because you want to be able to explain and predict。

So a model that explains but does not predict is not good because clearly。

It is following too much what you see and not what the truth is。So in any process of modeling。

 model modeling， like for example， machine learning in approximations and all of that。

 there is always this aspect。Where is the training set， and there is the test set。

 The training set is the data I give you to build your model。And then there is the test set。

 which verifies if what your wrote can predict。 Now， how come that we came to quantum mechanics。

I mean， Newton was pretty good， right， Newton mechanics。 We can design things with Newton mechanics。

 and all of a sudden， quantum mechanic， why， Because Newton mechanics was not capable of predicting behaviors。

That we observed when we started looking at atoms and all they kind stuff。

 So the theoretical physicists had to invent a new model。 And by way。

 that new model had to contain as a special case Newton right。😊，Now。

 what is the difference there is the difference of scale， Newton is macro。Quantum mechanics is micro。

I's a refiner， right， in some sense， but the also explains the macro because the macro is based on。

Abstractions of the micro， right， now， which means that modeling is also dependent on the level that you place yourself。

喂。Now， if you want to cope with a very large system。

 would you rather stay at the micro level or at the macro level？Marcro level of course。😊。

But what is the problem with the macro level。No no， no， no， no， no， no， no， no， no， no， no， no， no。

 no， no， no， that's not the question of my composition， lack of compositiononality is fidelity。

 Fidelity means the capability of predicting。So at the macro level， you may， you know。

 what does it mean macro level means a micro level describes everything but you know is the lowest level on which you can detect or you know what is going on in order to abstract what you need to do。

What is the basic operation that you are going to do？Live out stuff， right， you live out stuff。

 right， You forget about things， So the question is that are the things you forget important or not。

So the art of modeling。😊，Is detecting what is necessary at that level of abstraction。Okay。

 so there is not a real truth or real true model。A model is only valid with respect a question that you are asking。

为矛盾多案子。So， for example， a spice model for circuit is a aggregated model of what is going on at the level of electrons and holesse in a transistor。

 right？😊，Now do we need to understand how a circuit behaves to go to the electron and horse， no。

 but now we know that right we know they're doing a particular abstraction and working at the ordinary differential equation level。

 we can do a lot of stuff。So and that is the beauty of circuit simulation is the capability of abstracting things out and now when you design digital circuit。

 do you need ordinary differential equation or not？😊，Now， what do you do。

 which kind of representation do you use？Bllion， right， Boions， right， zero ones， right。

Bullions plus you can put the delays and that kind of stuff。

 but Boolean right and Boolean is representing the fact that it transistor switches it goes close open almost closed almost open right because you have a resistance is capacitance but for the goal of detecting if your logical implementation is correct a boolean representation is plenty good enough so if you go one more level down you are dead I mean you can never tell if your digital circuit work or now so the abstractions are essential and the art of abstraction is a capability of living out the stuff that you don't care about。

Okay， so let's say。So， so imitates system process or artifactact of interest。

 The mathematical model is a model in the form of a set of equation。 Okay， good。

 so now in the design methodology that I presented you， what do we need to model， everything。

 We need to model functionality， but also the components， the sensors， the auators。

 the ECs and so on。😊，And then we want to construct possibly the implementation from the model。

 So this model is designed。 So you have the model， and you want to implement this model into physical processes。

Now， this also sometimes explains why you have weird the effects in your design is because when you analyze your design。

 you made some assumptions that are not really verified in a reality。

So the key to platform and by way， just because of that， you know， you forgot about certain things。

 So what is。The most important thing that people forget about。Is they？Environment。

So it's what surrounds the design。 You are designing a piece， and then you are making assumptions。

About what is around you。So for example， if you build a car， for example。

 assume that you build a car with free steering wheel。Now， will that work or not？Free steering wheel。

So in order to make it go you need。F， of course not， we don't have six hours。

AndSo that is an assumption that the driver is going to have two hours。😊，Seems silly。

 but that's what it is？😊，Is that you have to assume what is surrounds you， what surrounds you。

 And so the most difficult part is modeling the environment。

 So to predict what the world is going to do to your design。so well in any case。

 the key to platform based design， we say before components， composition rules。

 refinement rules and abstraction rules to build the models。😊，Now。

 there is a very interesting thing that is coming out， and this one is rather a， so we just quote it。

 it is the last fashion。😊，And everybody's talking about this stuff。 It's contract based。

Now contracts， what the heck is a contract。Right well， we know right so for example。

 if I want to sell you a piece of land， I'm going to represent that that land essence properties。

 this big this lines and on and so forth， and you buy based on the assumption that I gave you right information that is the content。

And so if that assumption is right， the price is appropriate。Assume。

 assume that the line is done like this。 And I give a guarantee。

 So the contract is a pair of assume assumption and guarantees。 let's say。So when I do my design。

 I assume what is around me assumption。And I guarantee that if these assumption are right。

 so they represent the world， then my design does this is a contract。

Between my design and the environment。His。As simple as that now。

 using this notion of contract when I can you know become creative。 right So for example。

 we said before that we had the elements of a library。😊。

And I wanted to know if I could plug two things together， right。Well that is a contract， right。

 isn't it， So I want to have the word to be represented to me at my pins in this particular way。

if that is the case。 then I guarantee you that my performance are like that。 Now。

 this is important because， for example， I don't know how many of you do microwave design。

 but some of you may have done a microwave design course， but remember a 500m rule。

That you have to have an input impedance of a maximum power transfer from module A to module B occurs when you have 50 on。

That is an assumption， right？Assumption 500， right， So this component is good in the design。

 If facing input impedance 500。Assum guarantee， microwave design。Car design， anything。

Is a general concept。 So by same token， when you do modeling。

 So assume can you cast the problem of doing an abstract model correctly in terms of the contract。

You certainly can。 if you think about it is。I， if this is my lower model。

 so I assume that this is my lower model。Then I guarantee that this higher model is representing in a particular space。

 the behavior of this model。So not only you can do the composition based on counters。

 you can do all sub fine。SoAnd that is introducing contracts so for every component。

 you associate the contract that says when you can compose things。

And what are the assumptions that you make when you compose things？Now， so in other words。

 what I recommend is that for every component you have a contract around it。

 the contract says where and how I can use a component。If I don't do that。

 I ran the risk of doing all kind of bad stuff。 Okay so enriching components with contracts， I mean。

 you can call it instead of calling contracts， you can call it whatever you want。

 but you have to make it explicit。What is your assumption when you do with design？

So what are the modern techniques that we are encountering in this class。

 we are modeling physical phenomena with ordinary differential equation in your book。

 you have lots of examples of helicopters， torque equations in three dimensions， and all of that。

And that is， in general， who is the guy who writes models of components like mechanical components or a letter components are either they originally are the physicist right so the physicists discover the law of nature and then they write the behavior of a component in terms of this equation now now that we know some of the rules is the engineer。

 the mechanical engineer writes where the model right so writes what he thinks is important。Now。

 it's interesting that when you go to design airplanes， for example。

 you have people that insist in describing every single section of the plane at that level of abstraction。

 And we want to know if the plane is not going to tip over in on landing。 I mean。

 have you seen how big is a 7，8，7 or a 7，4，7。 Now it can never do that。 And then you tell them， look。

 you know， it's fine。 You know， we are good。 You know。

 we can do many things in in electronic design automation in design automation。

 but this way too much， right， Oh， when I don't trust the result。 I have to build the plane。

 I said donnk。No depends which question you ask。 And if you ask the question if the airplane is going to tilt over。

 you don't need to represent everything at the level of partial differential equation of the components。

But most of engineers that do this kind of design are still used to say that the more detailed the model is。

 the better it is。And of course it's like you know wish you was you thinking you know aha I do that so I save my us right so this is the most detailed model。

 so something goes wrong， you know it's not my fault。

 it's the fault of Newton is the fault of Eisenberg is not my fault but you have to take your responsibility in building the model。

 okay audience。😊，Feedback control system， feedback control system。 You can have analog， feedback。

RightSo， for example， our body is all based on feedback loops， right。

So why don't we fall when we walk， There is a feedback loop。

 So it's a pressure that we feel from our legs， what we see close the loop and the that I apply to my legs are such that I don't tilt to right in this case。

 not a plane is a human till so。 Okay so now how do you but most of the control loops that are in use today use microprocessors。

And Michael Brus。Are using algorithms and algorithms are discrete and not continuous。

And so there is a time domain modeling is in the discrete sense， is not in the continuous sense。

 or is a continuous time。 the notion of time is something that is continuous。

 is a continuous value real on the real axis。Mododeing model behavior， model behavior is you would。

Think about you when you drive a car， you don't know but it is done that way。

 There are modes in which the car operates。 So， for example， when you accelerate。The car is a mode。

 when you take your pedal off， that's another mode。 When you break， that's another mode。

When you start the car， that's another mode， so each one of these why do you determine this mode。

 why do you talk about these different modes of ther。

 because for each mode there is a different controller which works best in terms of the engine and or doing a general global controller for all the possible way in which the car is going to run is out of a question。

 it's too complicated。And so you break it down right the usual problem of design is also breaking down into manageable parts。

 So you break it down。 Each of these parts is a mode。Right。

And so when you say that you are in a mode， think about a diagram that represents a mode with a node and so when you go from one mode to the next。

 you put an arc and you say， zoom， this is a possible transition。

So is it possible to go from full acceleration all at once into full bra？No。

 because you have to lift the unless you are crazy and you put both at the same time。

 but if you drive as any human does， is that you take off your pedal and then you apply。

The breaking action， then it means that you go through two modes from acceleration to breaking。

 So that is this model thing。 And this is called a finite state machine。 So it's a number of states。

 and you are transitioning from state to state according to a particular input。

Foot down this mode foot up transition。 So the cause of that transition is foot up。

 So the input is my foot position。Let's final state the machine。Not sensor naurators， well you know。

That is a special case of a hardware， So you have to look at calibration noise and so on。

 moderning software。 remember the software is a very interesting object because per se doesn't have a performance associated。

😊，It depends on which platform it runs on。 That's the reason why platform based design is so important to export the characteristic of the platform。

Software doesn't have time in it。Is is orthogonal to a notion of physical time。

 And so the only thing that you can talk about is concurrency。 If things are independent。

 So the notion of time is partial order In the case of software。 iss not time like 0。1 second。

出さないってメ。When you marry a softwareer to a particular microprosor， you can talk about execution type。

 And then modern in networks， latencies， error rates， bucket loss， all of these kind of things。

 which explains that for every layer， for every kind of object that I have， I will have a different。

Model meaning that I focus on particular issues that are of importance when I use that component。

And so these are examples so I'd'd rather you read it。

 so the most important thing is just simply how you write the equation of using ordinary differential equation how you build torque models and this one is just。

 I mean any one of you has done basic mechanics is able to recover this equation but the most important thing is that the use of this equation。

 the use of equation is for design and using equation for design means asking the right to a model and using the right level of abstraction。

So what I instead want to focus on is。ok。Is this thing is the exercise so what you could do is that based on what you have in your book try to think about reformulating the helicopter model so that it has two inputs instead of one and then try to simulate the behavior of an helicopter using Matlab or simri now the question then that I would like you to think about is that can the equation of a controller be implemented in software or not and this is not as trivial a equation as it may seem because the controller when you develop the controller loads you are assuming that you are working in real time in time continuous time now when you implement the controller you have to use a discrete time so you have a change of。

Space right and changing the space may not preserve the property。



![](img/d6a071a05bd08a10641cdec4df3f4954_7.png)

Now other moderning techniques that we'll talk about in the future classes， state machine。

 synchroous reactive models， data flow models， discrete event models。

 time driven continuous time models now what is the difference between all these moderning techniques is an ocean of time so time is the most important thing that you have to think about and notice that is not only a question of engineering and physics you know Einstein built all these relativity based on this it's also philosophical terms so time is really something that has in two humans since the beginning right so we will discuss all of these different uses of time and this will be done in the next lecture so you。

the's name。