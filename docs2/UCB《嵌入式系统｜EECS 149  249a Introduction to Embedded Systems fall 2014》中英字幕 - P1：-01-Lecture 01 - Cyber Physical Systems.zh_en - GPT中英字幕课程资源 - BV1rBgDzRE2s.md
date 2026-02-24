# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P1：-01-Lecture 01 - Cyber Physical Systems.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

So I guess it's time to start the class。So welcome to a class introduction to Embed the systems。

 I'm Albertto San Joiovanni Vincentte， clearly from Sweden， but。😊。

And I'm teaching this class with Edward Lee who is also a co of the book that we are going to use for the class now before we start I wanted to alert you that I mean many of you were many some of you were waitlisted so we decided to take you all so all the people in waitlist will make it except for people who are not regular students of the university so extension people we cannot accommodate already like this we are way oversubscribe especially for Val now second thing is that graduate students should be enroll in the graduate numbering and the undergraduate students should be in the undergraduate numbering so some of you kind of went this way so not good so you have to register according to your status。

Other thing is that everyone who' is taking the class has to be enrolled in a lab session now since we didn't have enough lab sessions to accommodate all of you we added a new one so where it's going to be a new session that you can take but all of you have to be enrolled in the lab now the people in scheduling are arranging this situation so right now you probably will still find the limitation on the lab so you cannot enroll in all that but by tomorrow everything should be done so since the first lab is on Tuesday then you got to have all of this done over weekend okay from tomorrow to to Monday you have to have this thing resolved so this are the initial kind of。

😊，Addds and now how I structure the first class is to give you first some motivation about what this class is all about and why it is important and then we'll go into some of the administrative stuff which is much less fun so Ill kept it at the very end so now let's go to the point so what is the main subject of the classes is and about the system。

 but actually since the class was started， there is another wave of topics that have been very much interesting to people it's called cyber physical systems right so the name sounds very appealing is more or less and we see how different they are but it more or less。

Sitting on the same principle， so I would like to give you some view of what this embedded cyber physical system are all about so what you see here is a combination of things that are actually can be considered and all of them embedded system or cyber physical system so first of all。

 what is a cyber physical system is a combination of logic so for example a computer program that runs on a microprocessor and the physical world so it's a combination of it and that's a reason why we are called cyber physical is's a combination of these two different words now how different is this from standard computing system is obvious because in standard computing system the aspect of the physical world is not there so in fact the basic abstraction of computer sciences that time doesn't matter。

 power doesn't matter matter all the sequences of operation。

You take okay and so that is to deal with this system is their wrong abstraction。

 so we will discuss this and we willll show you how you can approach the design of this system in such a way that you do take care of physical variables in the system itself now there is not a single thing today that is not。

诶。ま。Related to embedded systems， so there is always a microcro someplace and there is always some logic。

 someplace in almost any physical system that you deal with today， cars， airplanes。

 manufacturing lines， as you see where defense systems， avionics。

 so airplanes is all based on electronic intelligence that is placed inside these systems。😊。

Now you also have seen， especially in the automotive domain that there have been tons of recalls so the system doesn't quite work as the people who design hoped it to work and so you have to recall it to fix it now we all know about the mega promise General Motor said about the famous ignition switch and there were also a few death around and that was a major disaster not only for the loss of lives but also for the company for General Motors who lost billions in the process。

😊，So the more complex you have a system， the more stuff you put into a system。

 the more likely is that something is wrong or there are some unexpected interaction between different parts of the system so that you end up with a situation that you wouldn't like to be in so these systems are becoming more and more pervasive but there are more and more difficult to design and there is no and inside so it's going to be more and more and more and more until we will reach a situation where we can possibly design this system any longer so now this one is is an example that you can find in the book and there is more flying object it quadrootor right is a sort of helicopter with four engines and why four engines because it can make it do all kind of weird stuff okay so。

😊，The kind of thing that you need to do to make this fly is quite amazing right so this is an independent there is no man that drives so these guys go alone so there is an intelligence in there that it is performing a task in this particular your case the task could be to follow someone on the ground or to take some load someplace。

😊，And the interesting thing is that it is indeed unhooked to human beings。

And so you have to make sure that this thing doesn't crash。

 doesn't crash on your head or doesn't kill someone， hopefully。

And at the same time does what is's supposed to do so you have then to do modeling of this system to control it because of course if you don't put a controller in it。

 it will go anywhere and will do all kind of bad stuff so you need to model flight dynamics so what is the dynamic of the way in which this guy flies and this is chapter2 of your books you have to look at the modes of operation am I landing am I taking off am I cruising alone this modes modes of operation of the system then how you transition between a mode and order how you compose behavior of the subsystems that are interacting in this system and then also and we will see some interesting movies about it。

😊，You may have a fleet of these guys that are talking to each other。

 So how do you handle the communication between all these different guys and why do you want them to communicate。

And that is in chapter6 now when you go down to the actual design of the electronic part of this system。

 you got to worry about sensor and nauators because sensor and nauators are the interfaces of the cyber system with the physical world so sensor and nauators are the hands auators and the hence the foot and so on and the sensor are your sensors right so that is what the cyber physical system does in some sense it's similar to what we do so processor are of course intelligence。

 memory system is the way in which you store information。

 of course then the way in which you interface a variety of different sensors that have to collaborate to give you an over picture of what the context is then you want to be able to write concurrent software so software that is。

😊，Running， possibly on different。Quadro rotors， but it has to interact somehow。

 So writing concurrent software is one of the most difficult tasks you can think of。 It is very。

 very complicated。And then real time scheduling。 so you have to react to possible situation in real time really fast。

 So what does it mean real time There is not such a thing as real time right so there is always an approximation to real time。

 what we intend as real time is something that you cannot detect that there is a delay in it so that's what is called real time。

 All right， then you have to， of course， before you put this in flight。😊。

You want to debug it now you can't possibly debug it while the guy is flying because he may kill someone okay so that's not a good idea so what you have to do is you have to go through a virtual debugging。

And so it's called analysis， right， analysis， you analyze the model of a system。

To verify that the system does what is' supposed to do。 It doesn't kill people around。

 Maybe you are designing to kill someone。 That's a definition， but we will not deal with it。

And you want to achieve safe behavior， verifying the safe behavior and guaranteeing timeliness so meaning that all the controls have to arrive in time and that you have the right context and you are not doing something stupid okay so now what is the actual platform computing platform upon which this system relies so it is you can see where the yellow boxes where are three microprocessor three right so there a free computing stuff that are going on in parallel there are two PC104 and stargate are standard computing engines if you like not so robottics。

 robottics is a particular lowle microprocessor that deals with the low-le control of the quadroroor which essentially making sure that the engine that what's supposed to do all the rest is the thinking and the decision making that goes on when we think。

😊，Flies now you see on variety is wfi that is the connection to the outside world where you send information。

 so you send information to your friends that are flying with you or to the ground to the people down that can shoot the guy if it goes bananas。

 you take it down。😊，Now the robotics that you see here in fact。

 as some interesting tasks that you see here and this IMU ranger and ranger so what do they do they essentially assess where the quadra rotor is is locationing is that to decide where you are now it looks like what is a big deal it is difficult it is very difficult so today in fact precise organizationization is still an open question to do it quickly。

 nicely， precisely and cheaply okay so that this part here is。😊，That one。

 notice that to find out where you are， if youre flying is not only a two dimensional problem。

 like if you're working or running or whatever， but it's a three dimensional problem right so youve got to have one more information now。

The planes， you know big planes where 787， whatever are flying based on two systems。

 one is GPS global positioning system， but then there is another one which is called the inertial system that was they1 that people used B GPS was available and they had only that one。

😊，Now， the problem with the IN S is that it be it can be very precise locally， but it drifts。😊。

So you may think that you are on top of San Francisco actually in Los Angeles very precisely right in terms of location and X and Y coordinate。

 but it drifts and so GPS instead， of course cannot drift in our satellites and so the combination of it is the best way to do this Now this is another important aspect of designing embedded system is sensor fusion。

 So you're taking two different sensors and INS and GPS and you fuse them you use both information to do what you need to do okay and then you have a stereochem。

 which is actually a video system so that the quadro rotor can see if something comes on its way a bird。

 for example and is trying to avoid it。 So how do you see a bird right so you have to have some kind of camera。

 you can use a visual system or you can use an infrared system。

 which is more or less the same thing so you have to。See what is around you。

 And that upper part is it。 Now， looks like a stupid little thing。

 And look how much complexity is to。A master and to make this thing do what you want。All right。

 so what is this course all about is about designing these things。

 It's about making things fly not really there will be a part of it in which we will show as examples how you do these things。

 but the main point of the class and in general in a。😊，School， that has some。

Pretence of being a good school is about foundation。

So what you want to do is that you want to learn from the class， what is important。Okay。

 so that in the future， you know， technology changes all the time。 right。

 I say before the GPS was not there， right， when you were flying only IN S。

But you had other ways of doing sense of fusion， so if I taught you how to do sense of fusion in the abstract sense。

 once you have a GPS， you have to put with INS， certainly we are two different system what you did before but the principal are the same you have to make two different set of sense or talk to each other right so the whole point of this class is to teach you about abstractions。

 composition rules modeling this kind of stuff so if tomorrow you are going to have a super duper incredible neural network based。

 whatever processor。The principle is still the same， so you can still work on this thing。In fact。

 there are two ways in which you can go about this very complex system one is hacking right so you go and start doing right and then hope for a best cross your finger and say now and then if it doesn't work say damn right but that's not scientific right now interesting enough 99% of the embedded system of the past we're exactly designed like that say let's go and do it on boom。

😊，Now this is okay when you have a very simple system because boom okay I understand why you did boom right so you fix it and the thing works now because of the complexity of today this method doesn't work even if it does boom to figure out why it did boom is extremely difficult so that's not a good idea so the focus then is a models is mathematical abstractions of the system that you do so that you can analyze it before you put it in practice。

😊，Okay so now what is the difference in your book is organized along three different axes。

 if you like parallel to each other， is about modeling， design and analysis。

 so modeling is indeed is a process of understanding how your system does or writing equations。

 lets put it in this way。😊，And what you do with modeling is describing what your system does。😊。

Or what is supposed to do So one is descriptive what it does， or what it should do is prescriptive。

Okay， so both models are important。 So one is the guy who's designing and say。

 I want my system to do this with math and a rights equation a ball。

Now you have a real system and what you want to do is you want to describe this real system and then see what it does so on two different processes。

They still use model， but it's two different point of view。 One I'm looking this way。

 the other looking that way。 Okay and so any engineering design is about meeting in the middle is between the top down and the bottom up。

Now the design is a starter a creation of artifacts and specify how your system is supposed to do what。

😊，It does so it implements your idea the analysis is a process of understanding better what the system does and why it does what it does so that if it does boom in simulation you can then backtrack and say aha。

 this is where I went on right the same thing as when you debug a computer program。😊，Now。

 this is much more complicated than a computer program。

 It' already the backing computer program is not easy okay。

So that's just to give you an idea of what so in this class we are going to address all three topics but in the design part。

 especially you will see we will start actually with vets so that you can start your lab is more about the hardware aspect and the implementation aspect than higher level of design that nevertheless we have to face so now let's look at why are these things relevant well we already say they are everywhere right so they are in cars and airplanes and this and that so it seems natural that we are important things but if you look at who makes money today in the web in the webs in the world is about cell phones web that can stuff so what are the largest companies that we find both in terms of market evaluations and in terms of revenues are people like Google。

アマゾ。Apple， especially number one， Apple。Right and do they do any of this cyber physical system in their products where we make $1 gazillion dollar actually no and then you say so are you selling smoke here in this class you know this is a real stuff right and this crap that you are talking about may be interesting but it doesn't hack it if I want to become gazillionai thats not what I should invest。

Well guess what okay so McKinsey Hollly so McKinsey big consulting companies is supposed to be the think tank of the companies and the way in which strategy is laid out so every year they put out a report about what is the most disruptive technology around so they put out this analysis and you have what 12 topics of great importance。

😊，Now， these 10 topics were at at least four which are。😊，Related to this class。

 one is the Internet of things， which is probably the most related one。

 So here my friend Christopher Brooks， who is actually the guy who' is behind most of the kind of things that we do in the labs and in programming and all of that。

 So he's the guru of these things。 Well， he says， well look， you know， the garer。

 which is a marketing company every year puts out the hype factor right So the think that are。😊。

Highest in the interest of people， but they are you know bogus right kind of there is an over inflated expectation。

 Well， guess what Internet of thinks is the top of the hyp curve right。😊，Well。

 do we believe that Well， you know， I like， I still like it， right， maybe high， but maybe not。😊。

And let's see what people do about it， that cloud technology， everybody knows about it。

Advance robotics is a big， big， big， big， big， big issue。Now。

 robotics is a task of designing a mechanical object。

 it is a lot of intelligence right It does very complex task and is supposed to coordinate with humans and with other objects so that is the typical system as we start in this class and then last but not least is autonomous and semi autonomous vehicles so cars that ride by themselves now if 10 years ago you went around and say okay we are going to have cars that ride by themselves and people who take you for crazy and just bring you to the hospital right now well not so any longer so autonomous and near autonomous vehicles are actually the most important thing that car companies are investing on and they're investing1 gazillion dollars。

😊，So if you want to be gazillionaire， if you had a way of doing autonomous driving vehicles that don't crash into people in other cars in wves。

 you would be gazillionre so that is a big issue but do you think that is simple of course not right can you imagine how many things we have to worry about when you drive but for certain one thing is clear if you indeed have a way of creating autonomous driving car。

 you are not going to have nearly as many accents as you have today。

 99% of the accent are today is due to a human factor because you know I saw that myself I was driving down to the Silicon Valley and was a lady with her foot on the steering wheel painting her nails while driving right I mean gee。

 I say I want to be away from this car right？😊，But if not， all the people did even crazy things，Bad。

 right， so people drink you know it's not so very good。 people talk on the cell phone。

 So you know Apple and company have to do something right because they are killing people by inventing these objects okay。

All right， so this is important stuff。 So economic potential。 now， again， hyp factor， whatever。

 But the potential is like for Internet to think $36，$ tri million， right。

 almost like in budget of the United States。Cloud technology，1。7 tri to free triion。

 interesting enough cloud。 everybody talks about cloud。

 you know greatest things since the bottle of the。 But the Internet of things is 20 times as big。

 so S potential。😊，addance robotic6 tri already advanced robotic is more than the cloud。

 so the point is that again if you want to become zillionaire。

 that is the field and it is the field is interaction between the physical world and the computing world。

😊，All right， autonomous near autonomous vehicle for trillions or tons of money now。Do people。

 I mean like Google are so stupid lets say who cares like in the old time some of the companies would disappear。

 say about new technologies， say who cares and there were some people will say I can't see what a computer can be used for from about 1940s so don't panic nobody would say the same today but Google has done a few things right first of all。

 the first real autonomous driving car that has been put in the street is a Google car so you saw it probably running around in around Palo Al and really you know the drive by itself。

😊，And it had only one failure， but it nothing to do with intelligence， dis and that and so on。

 So with just a mechanical failure。 So it is possible to do that。 Now， unfortunately。

 it's slightly expensive。So in order to have a car that refuses to crash。

 you have to give it a lot of senses and you want to do it even better when a human。

 so can you see through walls？😊，I can't， maybe some of you superhuman Gazillionai， can see throughs。

 but I can't。Can a car see through us， the answer is yes， how with a radar。

 So indeed the eyes of the autonomous driving cars are radars。😊。

And so you can even see behind the corners。 And so that's the reason why you are preventing a lot of accident from eping。

 Unfortunately， it costs $70000 M dollars， right just。

Rers right so it is slightly too expensive right but as we all know if you have a way of doing things and you put a lot of engineers like us on the problem and then from $70。

000 it will end up costing 7 cents and then we are talking right because 7 cents everybody can afford okay。

😊，the range finder is mounted on the top is aveloine 64 beam laser， right It's like Star Wars。😊。

Now there is also another use for the laser if I were driving since I come from Sweden you know if you ever drive in Rome right you want to have lasers all over the place because you want to zap people around you to try not to have accidents okay now so they invested in making this car right now everybody and I were for many long years for General Motors and BNW Mercedes so I am very familiar with the automotive domains。

 guess what they were scared to death oh my God Google is becoming a car maker。😊，Could be。

But I don't think so。 And so the reason why they wanted to do this is because they want to own the infrastructure。

 right。To make the vehicle a reality。 So I say， look， it can be done。 And by the way。

 you need all this infrastructure from Google to make it go。 rights so we sell more of their stuff。

 fine， but we close a 3。2 billion purchase of nest。 Now， what is nest。😊，Does anyone know what N does。

 okay？A thermostat now thermostats in Google， why do they want to know if their computer overhes？😊。

They always do， right， of course。 But that's not probably the reason why， right。

 Why do they want to do that， Any， any guess， Why guess I I'm trying to over。You know。

 interpret what we do， yes。这。Okay。Okay。Binggo bingo， bingo， bingo。 So my my guest was right。

 So they want to own the the how。 So the car， autonomous driving car。

 they want to own transportation。Nest， they want to own the house。 Now， do they want， you know。

 to sell one gazillion thermostats。Not in the car。 So what they want to do is they want to use the thermostat as a door into the。

Framework， right， And so in fact， we publishing of a new standard communication for the home and blah。

 blah。 that is the game。 All right， now not over yet。 remember the famous sectors。

 There is also the sectors of robotics， right， So what did they do， They went off and bought。😊。

Glo Boston Dynamics right Boston Dynamics is the most exciting robotics company I've seen if you look at some of YouTube you see this monster and is walking down like this and say my God and Frankine is coming and it lies down in the snow and on the ice on the lake you know and it is for military application and you say how come Google wants to become a military company not at all。

 So what do you want to do with advanced robotics Well you want to own the manufacturing plants So now you have the home the manufacturing plants。

 the transportation system， what is left。😊，Right， so that is the， you know。Strategy。

 and that is the reason why these guys are' entering into that， but it's not over yet。

 What did they buy in another company， you know。Drones， you know。

 they bought a drone company and Facebook also， you know。

 they bought flying machines like the Ecudada Rotorro was talking about， flying machines。

 unman flying machines， and said， what the heck do you do with unman？

Besides going in Afghanistan and doing crazy stuff。Which this guys， some of these guys did right。

 but Google I don't think they are in that domain， also because Eric Schmidt was a student here。

 I know him very well and is's not exactly to ver right。😊，Rather than on the left。

 so it's not in the cards。😊，So， well， they want to do that for two reasons。

 One is the declare reason， which is the same as Facebook， is that if you use drones， you bring。

Internet to everybody Okay now the other reason is because you can monitor what is going on in a particular regions。

 so for example， suppose that you know we had the big earthquake in Napa support is bigger and what was there then all the communication are broken right so so you have these drones flying over and they connect。

Everybody together and you can find out what went wrong and if people are stuck in places。

 So it is that。 Now， in addition， I can use these to do what maps。Now。

 maps is a big business and everybody says， well， what is so difficult about maps， Talk to Apple。

 right。Wait me。Okay， next。Apple， you know， what does Apple want to do， You know。

 Google is very clear， very intelligent。 They are going everywhere。 Well， guess what。

 Apple is talking to Tesla。😊，And I have reason to believe that they are interested in purchasing Tesla by Tesman。

😊，Os。They are becoming a car company。Right。And why Tesla， because what does Tesla use batteries。

 right？And what was one of the 12 disruptive technology batteries and batteries are really important everywhere you do everything you do。

 batteries are it， so Tesla and Apple are very interested in making batteries in fact they have a joint manufacturing plane with are all kind of plane to do that one gazillion dollar invested in making batteries。

 but if you look at the way in which Tesla is perceived is we're saying in the world of cars its very similar to what Apple is perceived in the world of computing。

😊，High class expensive， nice properties， everybody wants to have one I'm not so sure because if you really buy a Teessla you don't know how to drive it。

 you kill yourself like a Ferrari actually even worse because it doesn make noise and so if you have a Tesla behind you you don't realize you have so you go like this and boom you know。

Okay， so the future of CP。 So this is the present。 So even big companies are investing this interaction between the physical and the cyber。

 So there is not going to be any single company whos not going to be interested in this。

 So you are in the right class。 And in fact， we are way oversubscribed。

 So you must have read some some article someplace okay， now what is going to happen。

 So emerging IT scene。 So this one is something that we have been。😊。

Talking about for many years in particular Professor Arabi is the author of this slide which is very nice。

 that's when I started when I started you know I must say that I graduated in 1971 now in 1971 there was no terminal okay。

We were programming the computer with cards。 So we carved the readers。 And I didn take with cards。

whichch youre not the credit card reader。 we're reading these cards were holes and the host were zeros and ones。

 right， So okay， that's where I come from。 So we had these big computers that were less than one mi and we're occupying three times as much as this space。

 Okay， that' 1971。 So fast forward where are we today。 today we are on the。😊。

Cellphones that's the access and mobile access， cell phones and laptops right in the I world。

 What is in future So we are saying is a sort of digitalja where all the action happens today but in a few years no action at all。

 So it's a very mature kind of technology even though you think is still very cool and there are some very interesting projects going on and you have Samsung and you have Apple were going at each other and like with vengeance we see But the future is about what we call the sensor is warm and the sensor is warm is one gazillion different sensors that are going to interact and we are going now okay other question to the class。

 What is this。😊，Bad sensor。Any idea。What。Is it。No， well， yes， but。Yes， is is an interface to neurons。

 So is E C G， but you these needles go inside the neurons。

So you have to take the guy this thing in the brain，Actually it happens this way。

 so it is possible to do that So that is called brain machine interface。

 So you're going to get a guest class as a bonus。 I just call one of my friends here at Berkeley with does this kind of things。

 So it's going to give you a class about how to do these things and and then some one of you will volunteer and we do。

😊，A test of it。 Okay， so， of course， the center of the world is not going to be anymore more of a big main frame。

 and the like is going to be the cloud， which is a virtual concert to say is all the intelligence that we can put together the one gazillion computers connected together。

 So the world is going to be changing。 I mean， most of the people are not going to use this stuff anymore。

 right， forget about the cell phone。 So gives to them。

 So what happens is that you are going to be immersed into。😊，The electronic world。

 if you like right so assume that all these walls are going to be covered plastered with sensor sensor can be temperature by the way。

 as you can see the temperature is raising but probably because your brains are working very hard and we consume energy and energy comes out。

So they will sense that and they will always keep the temperature constant in the nest of the future right they're almost at the future but it's also going。

 for example， I don't need this anymore I can do like this and the new slide comes up and I can even put together different slide by moving my head。

 you know just standard stuff that you see in movies science fiction and all of that。😊。

But it is going to be possible now if you want to see the future just look at Star Trek。

 there is't one thing that I would love to be possible。

 I don't think it will be ever possible but it's teletrans， B me up Scott in。😊。

is one gazillion there for you right there so now what do you do if this sensor is warm well the sensor is warm。

 you can instrument almost anything and the key points that you can gather synthesize and apply information that will change completely the way in which we do things and already IBM for example as gotten big contracts with governments like for example the government of Brazil to manage towns。

 entire towns so everything so from you know the dispatching the police getting you know there are if you go to Dubai or Abu Dhabi you see that every single post has a camera in there。

So， what do you do with all this data， You continuously collected， big data， cloud technology。

Machine learning is all that kind stuff。 So to try to figure out what it is that you're trying。

To understand， so I would not try to steal anything anymore in the future。 Okay。

 so if you have any idea about that， well probably you can't do that anymore。

 So it's going to be a thing of the past because everything we do is going to be monitored right no question about it。

Already today， anybody can know where you are by following your cell phone， easy。

And so when people talk about privacy， when you always have to ask them are you using your cell phone sure。

 are you worried about privacy， oh yes， don't use your cell phone anyway。

 so how many people say oh no， cell phone is mine okay okay I see a guy why are you here？😊。

It's the wrong class。😊，Anyway， so because this is a privacy with a big bar on top of it know you know a complement to price okay now it is a biocyber system so linking the cyber and biological words another thing that is possible and so it's already been done that you get monkeys for theing being monkeys so you have the monkeys sitting in R university is controlling an arm which is at MIT。

😊，Okay。With his brain， right no typing no nothing， just thinking about what he wants to do。Okay。

 so this is the famous you know that sensor that I was talking about implanted in the brain of a poor guy。

 this is the architecture of the electronic system that is implanted in there and what is the most difficult part here is to nail the thing on the brain。

Easy， so what is difficult。He has already taken the class。

 not worth it That's exactly What is the most difficult thing is to interpret what goes on in your brain。

 So you have to establish a map between your brainwa and what you want， right so in fact。

 the training is about that stuff right so your training the system and not necessarily you have to think about I want you know that coffee right So I want the coffee then in the future he says I want the coffee。

 the robot will come here， say， sir， here is your coffee。😊。

But the point is that in order to have a coffee， you may have to think red。

And if we want cappuccino has to think blue because the red and blue are easier to detect than coffee or cappucci。

 So and that is the most difficult part， right now。😊。

We say that we have an emphasis on modeling because it's very difficult to test this stuff in reality。

 So you want to do a。After representation of system。So now this one is a physical system， is a robot。

 this is actually a rear robot that is used to manufacture cars。😊。

And now you have an embedded system， which is a computational parts of the boards。

 that control the operation of the robot， and they are networked together and these boards are placed in various parts of the robot。

And then the sensors are telling you what the position of the drilling tape or other machinery that where robotbo is actuating。

 these guys do computation and then they give an actuation command like for them the drill here。

 boom and they the drill。Now， in order to make this thing go is that we have to marry a physical。

 the physical is that this guy moves right so its operation， if you want to describe how it moves。

 you have to use the financial equation right because it' is a continuous system。😊。

And a continuous system is best described with differential equation。 Okay， it's not the only way。

 but I don't want to go into statistical modeling of that kind of stuff。

 You can even model it at the level of the atoms。Not in the cards that will be very stupid。

 which tells you also that modeling is something that you have to think about to decide what is the level of accuracy you want。

😊，So if you want to determine what is the movement of this thing， atoms don't matter。Very any matter。

 but we are inside so you don't care。 You look at the envelope of the of all the material that is in there。

 So equation based model。 and so the abstraction is a physical model in process So is the bottom up path。

 So you got the physical system。 you represented by eliminating unnecessary details because the goal is to have something that is easy to play with。

With respect to the original system and yet as all the information that you want to assess。

 so modeling is a really serious issue and so people who know how to do modeling they are very much sought after not gazillionaires not in the least but let's say a few 20000 I mean。

100，0200，000 all the time okay。For doing this。 Okay， now， on the other side。

 you got this stupid printer circuit board with microproster on it and software rans on it。

 So do you want to use a partial differential equation。😊。

For what to describe what the computer does you could right because after all the there are electron that moves and all that but y right iss way too detailed so the issues that we say before the programming doesn't have a concept of time and so you have models of computation so way in which the computer execute now you got a differential equation one side and you got。

This abstract behavior of computer programs。 Now， how do you marry the two， right。

 How do you make sure that the composition of the two does something useful。

 And here we go with the models。 Theres a reality。 So this one is Solomon Goam。

 So that pretty I to say。Unsettling guy so if you look a criminal minds probably will be a good character for criminal minds。

 but it nevertheless was a mathematician as often mathematicians are kind of you know。

 oh my God what's going to happen so anyway so is was。😊，Interested， of course， in modeling processes。

 And one of the things that he did is in essentially invented ties right。

 but with mathematical concept about it。 and it was the first one to talk about the the issue of abstraction。

 So in fact， you will never strike oil by drilling through a map。 So what does that mean。

 So a model is a map， if you like， of the。😊，Physical system is like the map of the streets right It's Google Maps now when you don't drive on the Google mapps。

 right you drive in the streets， but the Google map is used to make you go in the right direction。

 So that's what models are all about is making you go in the right direction。

 but you don't actually use it to go right You use it to decide where to go。

 same thing is what he was talking about。 So you cannot get oil by drilling from a map。😊。

So but this does not， of course， diminish the value of a met because it's a guiding principle It's something that tells you what you should be doing。

 Now Vi。 Herman Cotz is a good friend， both of Edwardverley and myself。

 and in many it is philosophizing about the fact that people say this system as a following property and what they mean is that the model of that system is this property。

Because the system itself is very difficult to analyze， to say besides the property。

 but what you can analyze is a model， so a model is a property。

So the name of a game then is to say if I say that the model is this property。

 can I infer that the system has the same property？And this is called fidelity。 So when more than。

As fidelity， with respect to the system。Doesnt have to be accurate to be to have fidelity。

 Fidelity is tracking if you like。 Does' I have to do exactly the same thing。

 But if you ask the question， you should have the same answer， okay。Now。

 there is another interesting thing that is related for those of you who are in electrical engineering and have studied designing circuits。

😊，And its about synchronous modeling right synchronous architectures right so when did we start using synchronous architecture the idea of synchronous essentially you have latches and you have computation that is carried through a set of transistors that are combinational logic and so the dynamic behavior of the computer。

 for example， of the brain of the computer of the CPU is through this sequences of operation you have a latch you read the ledtch。

 you compute， you store value in a ledtch， the next logic reads that value it keeps on going this way now what did that do。

Well， actually， that methodology was used only for one thing is to get rid of asynchronous behavior of。

Physics， because physics all are synchronous， right， So if you think about transistors。

 there are synchron。You know the flow of signals， through transistors is very asynchronous now by putting these boundaries here and there and say I don't care between time T0 and time t1。

 whatever happens I don't care， I only care at the end when everything is done is said and done by doing that you decouple completely the functionality of the circuit from timing。

Okay， so that's what synchronous Digital logic did。

 And it was wonderful because when you didn't have race conditions。😊。

And race condition I essentially be following it depending on the data that you pump into a circuit。

 you may have a result or another result and you can never tell a priority you have to actually execute the system to figure out and that is called a nondeterminate model so you cannot predict what is going to do you have actually to look at it to see what it does now in synchronous you don't have that because you don't have race condition same input come in。

 same outcome concept。So that's a great idea for that。

 so now in the case of electronics is that since you add a synchronous model behind then you can put on top of it abstractions you can put on top of it instructionsion sets and you can put on top of it or system compilers and the old name of the game。

 and then you have a potential model of what is going on as a computer program as a single threadit imperative program okay。

😊，Now， so you have a physical system which is described by differential equation， as we said before。

 and this is in general， is determined。 Well， it's always like that。😊。

So if I give you a continuous equation， can we say deter terminate always？嗯 now。Yeah， well， besides。

 I mean， assume at the initial conditional given。Because that is part of the system。

 So you have to give it。We are getting there。 So the point is。If you have differential equations。

S price as x dot equal to f of x。 and F is lipshi continues。 O， The solution exists and is unique。

 The behavior is determined。😊，Now， suppose that you have a mix of differential in algebraic equation。

So you can have mixed with a differential equation x dot equal to something。

 You have also G of x equal to 0。Now， when you have a no linear equation， static equation。

 no derivatives around， how many solutions do you have to G of x equal to 0， can you tell？

You can have no solution。 You can have a single solution。 You can have multiple solutions。

When you have multiple solution。Can you tell which one is right， they're all right？

And so you cannot tell what the solution is， it's one of those。

 and so you can have even in this differential equation， non deterministic behavior。Now。

 in all the kind of things that we do， for example。

 in analyzing this system and applying numerical analysis。

We try to avoid this by assuming that the right inside is continuously is continuous。 At this point。

 we have theorems。 that's say we are homephrey。

![](img/2e2db10707d77681b761343a84d19ade_1.png)

Okay so combination of course are nondetermininated。

 so if you put in sequences of instruction and you marry it with a differential equation you don't know what's going on。

 really don't because the abstraction are so different but there is no common ground。I's like。

 you know now I start speaking Swedish。 I don't know how many people know Swedish here， but I don't。

Presum many， and then is a one way conversation， right， So it's not a conversation actually。

Same thing。 So one guy speaks Swedish， the other one speaks Croatian。No common thing。

So the schematic of a simple CP， when it's a physical plane， you have a computational platform。

 a network fabric that is v1 which is used to distribute the information。

 And that's what you need to characterize。 So computation is。

 in general given in an untime imperative language。 C is exactly right。 So there is not a。😊。

There is no variable time， I mean you can write equations with time in it。

 but the execution of C in itself。The abstract execution is no notion of time。



![](img/2e2db10707d77681b761343a84d19ade_3.png)

Well， of course， the physical plan has all kinds of things。

 So now what do people do in order to try to bet yes， there was the question。8。Yeah。Yes and no。

 but because the model of the computer program is divided by the notion of the clock。

 the clock is attached to the machine that executes the code。

 so the program itself doesn't have that notion。😊，So the marriage of it too， yes。

Which is a problem because when you write in C， you don't know right So you have to to write C when you have deploy it into the machine and you have to see how many instruction you go through and know that。

 and you have to analyze the behavior of the platform。And then you can associate time to it。

But the abstraction doesn't have a notion of effect。

The abstract is the C program set so now what do people do so they fake it right so that the fragment of code in there is assuming that there is a sort of a clock right it is a clock but that is a artifice every time you go through a loop is a very timer count gets increment by one so that is a poor man way of talking about time and in fact this this control of timing is very approximate because you don't know what the actual clock cycle is of your computing machine。

😊，Okay， so time behavior actually emerges from the combination of the what I just say to you is the marriage between the code and the actual processor。

And by way there is also a very interesting phenomena because I don't know how many of you know that probably most of you that in the modern architecture or computing system。

 you have out of order executions so you actually execute this instruction that are supposed to come later before and when you for the best that everything is going to combine right know so just outside the domain of time。

 you can do anything you want is an abstract domain with first day to time So when you marry it to when you can talk about So now what have we done in the past to come where this kind of of complexity。

 we already say right in VLSI we did this sequential， I mean this synchronous design method。

 So this one is a paper I wrote in 2010 about the history of E。

 what is EA EDA is electronic design automation is a body of theories and computer programs。

That attempt to help people to design systems。At the origin were electronic system circuits and that thisynchronous assumption came out of this kind of way of thinking now it's interesting that this one gave as we see in the next slide。

 it tremendous power to increase the complexity of what we could design so what were the tricks that we use one trick was and we say we use because we originated in Berkeley this field and we founded the two dominating companies getting synapses were founded by Richard Newton and myself so kind of novic field very well so did we do this through abstractions so for example synchronous as abstraction is one way so you deal with transistor as they were just doing computation with no timing in it and tools。

😊，You know， in general， when you want to design something quickly and accurately， you need tools。

You it's something that the computer is going to execute for you and give you answers。Okay。

 so simulation is a typical case， is like a virtual lab。 So you execute the equation。 And you see。

 But the combination of it to actually， if I have to look back and see what it is that really made a difference was the combination。

 methodologyologies。

![](img/2e2db10707d77681b761343a84d19ade_5.png)

Now， methodology is way of doing things。Now， methodology are no good unless they are imperative。

 So what are they are like。The1 commander。Thou shall do it so in micropro design。

 you go at a certain sequence of operation Intel insists that you do it and if someone doesn't do it gets fired。

😊，So in fact methodologies you can think about methodologies freedom from choice so it's preventing you from getting in trouble right so don't do that because you are going not be able to design if you do this we are going to provide you with tools with proofs with everything known to men so please do it okay so that's an important lesson so what were we able to do we started again 1971 when I graduated you know what was the largest integrated circuit that we were capable of designing any idea。



![](img/2e2db10707d77681b761343a84d19ade_7.png)

It was a four gate gate array， four gates multiplied by three or four number of transists。

 to alternate。12 trans。 Now， how many transs do you see today in。Intelships。Ting bath。야， 사람 안완냐？

12 to 1 billion。Okay， so I'm not Matusalem， right， but I started with 12 transistor。

 end up with one billion transistor。 So in very short time。😊，Comparatively speaking。

 we were able to do this。 So now that is the Mooreer law that says that every two years。

 the number of transistor double。 and then we are going to reach the limit of what we can do is about 10 billion transistor on the chip。

 So we are close。 And then what the next who knows what is going to be。 But actually。😊。

The technology we were able to develop here and the two companies that we founded were behind this curve so we thought this couldn't do it。

 no way of doing it， no way so methodologies， abstraction and tools and that's what I said I mean this class is going to be about methodologies abstractions and tools for cyber physicalical systems Now these one are incredibly simpler。

Then what we are going to talk about in this class， I mean。

 integrated circuits and integrated circuits， more of physics， single physics。

 we know the abstractions。 we have done a lot of work in it and so we know what we are doing in the other domain not so much。

 so how do we then implement the methodology whereas essentially two basic principles and one is horizontal and one is vertical。



![](img/2e2db10707d77681b761343a84d19ade_9.png)

The horizontal principle is composing and decompos。

So composing meaning that if I want to build a complex system， I take many pieces。

 I plug them together。So that simplifies life because I already have pieces and I plug them up is like Lego blocks。

 right same thing。😊，The opposite process is decomposing。 So I have a complex system。

 I cut it into pieces and analyze one piece at a time。 So one operation is the opposite of the other。

 composition， decomposition。😊，Now， what is the verticalan？Verically is abstraction refinement。

So abstraction means I have a very complex system， a generalphysical system。

 and I want to write models that have simplified version of these things， abstract。

Now refinement means I have an idea and I'm going towards implementation。

 so every time I do a step in the design， I add more details， abstract refine。The other one。😊。

Issue is that complexity sometimes not only you do with decomposition， composition。

 abstraction refinement， but you make sure that in your design methodologyologies。

 some bad things can never happen。Okay， and that is synchronous design， for example。

 which is based on abstraction， decomposition all the。 but is making sure no race condition。

Don't have to worry about。So is complexities managed by construct。Okay， thank you。 Okay。

 challengeslles in applying this principle。 So the first thing is we say composition， right。

 So how do you compose right， So you put together things Now。

 what is the problem putting together things。Well， is that if I put two Lego block that have different size pins。

They don't stick together， right， It's very difficult to make men stick together。

If I have sizes that don't combine to make the house that I wanted to do。

 I'm going to build some kind of monster，So the issue that is plug and play。

 which more I plug and play now。 And so you put together things for best。😊。

The name of the game is that even simple things can be complicated。

And so you don't want to be in the plug and play， which is the same thing go， go， go， go。

 let's it doesn't work。 Okay no， that's forbidden。 So if you want to pass this class。

 if you do something like this， you are going to be dead okay。😊。



![](img/2e2db10707d77681b761343a84d19ade_11.png)

Now， there is another thing is this one so is horizontal。 Now let's look at vertical side。😊。

Vertical side is about specifying what you want to do and then doing it， right。So I love art。

 and I love in particular， Picasso。 So that's Picasso Blueper。 Okay。

 so this remember Picasso was an abstract painter， but at the beginning was not abstract English。

 Look at that painting。 It's wonderful。 So this is a specification。😊。

And this is a guy whos designed the cyber physical system， a car that refuses to have accident。

 gives it to the engineers and they come back with this。😊。



![](img/2e2db10707d77681b761343a84d19ade_13.png)

So more or less， this is a Picasso real Picasso， I mean late stage Picasso。

It is still a woman but is not exactly the same right there are pieces that are sticking out of all the different parts and then you give it to engineers give it back and say here it is and say not exactly so a guy who did the design looks at it and say maybe this is what I want so it's another Picasso blue period and so it's a very complicated process it's a refinement abstract because you have to have first of all a clear idea of what you want to do don't forget pieces as much as you can and then with guys who are implementing。

 they have to understand what you want and so sometimes people understand their own thing。😊。



![](img/2e2db10707d77681b761343a84d19ade_15.png)

![](img/2e2db10707d77681b761343a84d19ade_16.png)

Okay， so again， the hardware of which we build computers capable of delivering correct computation and precise timing and so synchronous abstraction is okay。

 but we have to make sure that we characterize that and we marry。😊。

This physical view is what your friend back there was saying after all。

 you know Michael Proso has the concept of latches and there is the clock and by the way。

 this is another thing that I tell all my students since 40 years ago is that the first guy but tells me that the synchronous design is based on clocks your5 you know just change Uni go to MIT。

😊，Because they will always tell you where and hes wrong because that is a way of implementing synchrony。

😊，Using the clock。But in the abstract stack。No is a different thing。 Okay。

 so let's make sure that you understand what is the specification and what is the implementation。

So you have to think critically。 All right， So can we change the way in which to do， for example。

 embed the software so that we can put timing inside。The operation of the software。

 and we can put power and other physical conditions。

 So that's an interesting goal that we are setting for。For ourselves and we need deter CPS。

 determined means that I don't want to say， let's hope for the best， I want to know。

 and so I have to have deter models， otherwise I will not going to be able to do it。😊。

So how can we overcome the powerful inertia of people are using writing in or C plus plus or whatever。

 an embedded system or written insane C plus plus bad news guys。😊，They can be implemented。

 maybe even automatically。 but the meaning of that program has to come。

From a higher level abstraction。Then the implementation take platform。

 very same way which microprocessor has a synchronous assumption。

 but you implement it with transistors which are asynchronous components。😊，O。Now we need open minds。

 so we need to try to break out of the old ways of doing things。Now。

 my channel CP system is that in general， in any company I visited and I did consulting work for and all of that is always this case。

😊，Theyre all gazillian people， the guy who' was dying doing the hardware。

 the guy is doing the software， we never talk to each other。

 and they put things together and never worked。So bad news， why。

 because there is not a single person who has a global view。That is called the chief architect。

Sometimes you do but its very rare， so chief architects don't abound and so everybody goes about putting together a system by plugging and praying the various component right so this one is actually a very interesting system that you may find yourselfs dealing with in one of the project which is an electric power distribution system so in all your airplanes you have such a system which is a set of generators that deliver electricity to your loads。

 your entertainment system is fed by this air conditioning system is fed by this the movement of the allers and the breaking of the wheels come from the generator systems。

The main engine is thrusting thing on， but there are secondary generators that do this now。

 its very interesting because if you lose power on the sky，You lose the plane。 So boom， right。

 Don't want that to happen。 right， So what you want to do is you want to assess properties of this system。

 And you have to make sure it is。Falult resistance。 So how do you make it full resistant。

 You duplicate things， and you put switches in such a way that the critical loads are always served。

Or one probability over a million。Ma something bad may happen， but you don't want that to happen。

 so that is a design challenge， a very interesting one And so if you look at what the components here are。

 there is a generator， contactor a bus load that are considered disturbances to the power distribution systems and then you have the intelligence。

 the controller that open and close the contacts and all of that so the generator is and letterme system。

 the contactor is a mechanical is a big gigantic switch because you have to make hundreds ofmps going back。

 the buses and letter system the PID is a controller so it's a control system。

 as apps are a control system， a supervisor finite aid machine is a software system。

 you have the communication between the switch and a supervisor control which is a communication network and then you have a switch which is actually commanded by some human operator so you have main machine interface。

That is complicated， okay。Now， a team of this course is think critically。

 any course that tell you that how to design this thing is going to last two years and when you are out of the job and going to work。

The technology will change， so what we try to do is to give you a foundation so that you can deal with changes in technology。

Okay， so which I say just at the very beginning of this class。 So keep this in mind。



![](img/2e2db10707d77681b761343a84d19ade_18.png)

Now， say this， we go to the boring part of the stuff that is what we are going to do to you。

In terms of。ha I got you immediately interested。Okay， in terms of how we are going to。

To evaluate a class okay so the book is Leon session and by way there is a new version is 1。

5 iss not publicly available as yet， but you have it in your B course domain you go down you can download it and print it if you want to。

Now， the organization， as I say before， is about modeling， it's about design。

 and it's about analysis， and there are be three mainstay of the class right there。😊，Now。

 this is a list of the lectures and who is going to teach it。

 Now this one is subject to change right is a classical。

Disclaimer so this is what we intend to do but someone may get sick。

 someone may be called someplace so but this is idea that's what we would like to do you are going to get homework to do and the first homework is due on 911 sorry for the day but that's it and the homework number one is about the topic that are covered in the next week okay now this is a guy who help setting up the labs the first six weeks of the lab is Jeff Jensen was a student here now is at national instrumentnstrument so you will see that the tools that we use in the labs are provided by this company is giving us for free so thank you national instrument and。

And he's also paying for the lab。 Thank you， nationalist。😊。

And we have also some of the national instruments people are going to help in some of the projects and thank you National instrumentnstruments and we have here our friend forever was the director of the National instrumentments。

 La in Berkeley， thank you National instrumentment。😊。

For giving us a lab in beautiful Berkeley so now this one is the manual of the lab in intradoural Le embedded cyber Africa system。

 and by way， all the ES stuff that I talk to you about we have to say thanks to all the companies in the world right because everybody supported our work。

😊，In addition to D NSF future stuff， but we the company supporting these things。

 when you do design work， you always want to have companies involved because otherwise you solve a problems that may not be enough。

Cour project now， course project in the past， we let the students come up with proposals。 So。

 for example， you would come to me and say， oh， we would like to build， you know。

 a wonderful quaro does this listen matter and say， gee， nice idea。 So go and do it。 And that's it。

 Now， this works when you have 20 students。 When you have 120 students ain't going to work。

 So this is forget it。😊，So we will give you projects and we like very much you to pick one of this now in case some of you is the next Bill Gates Zuckenberg and will entertain the motion。

 especially if you give us a few stock of your new company。

 but the key point is that its very difficult to evaluate then what you do right so pretty stick as much as supposed to this。

😊，We encourage you to form actually we will tell you to form groups of four people and then given the number there will be multiple teams working on the same project in competition yes and then at the end of the class you will see who wins that competition okay so if you want to see some of the project you can look at of the past you can look at the course website this are some of the things you know autonomous flight now a word of caveats in the past was a disaster everybody who wanted to do something like that they had crashes hundreds of dollars from down the drain because the thing would bump everywhere so in any case but you are free to play if you want to。

And in fact， this is another interesting project is。Using a Lego Minstorm and， you know。

 it's doing essentially seway。 So it's balancing on two wheels。 That was a very interesting project。

 very complicated。 But I have an idea。 I would like you to do this。 oops， how do you make this video。

