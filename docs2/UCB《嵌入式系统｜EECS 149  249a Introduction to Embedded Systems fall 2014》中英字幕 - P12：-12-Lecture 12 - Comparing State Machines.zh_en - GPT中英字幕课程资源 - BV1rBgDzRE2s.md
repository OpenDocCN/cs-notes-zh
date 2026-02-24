# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P12：-12-Lecture 12 - Comparing State Machines.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

So。Ready go。So today we are going to talk about how to specify。

A design so people think that the difficult part of the design is to do a design。

 but actually the most difficult part is to say what you want and what the design is supposed to do and in fact。

 you know when you do a design when at the end when you are done。

 when the question is did I really implement what I had in mind？In the first place。

 and so this is also true when you are a company， you know that the way in which companies work is that there is what is called a supply chain。

 meaning that there is a company， say a car company。

 then the subsystems that is putting into car come from other companies。

And so what happens is that they buy。Equipment， or they ask the companies to design equipment for them。

Now the question is that there is a long contract that specifies what the other company is supposed to do now if you forget about something if you want the supplier to do for you。

 then it does something， it delivers it to you， you put it in your car and the car doesn't work。😊。

And then you go to a supplier and say，" you Turkey， you did their a horrible job。

 so I'm going to sue you and I'm going to strip you to death and the guy say， no。

 I did what you told me to do。Then they look at the counter and say oops for God and so its not only an issue of technical issue。

 but it's also a real issue that involves hundreds of millions of dollars。

 so the specification of a design is a key point so you have really to be very precise about what you want and this is through across company boundaries but even inside a large company you have divisions。

And so it's not the same group of people it does the entire design。

 you have the people who do the architecture of the design and they deliver specification to their other divisions that often work in parallel so it's extremely important that everybody is clear in mind what they are supposed to do so one thing is that if you go to industry and you say。

 okay， what is your specification method。So while people use Excel spreadsheet， I am not kidding。

 so they use Excel spreadsheet or at most word statement， word meaning Microsoft Word statement。

And then they have programs that help them。To organize with statements that they talk about。

And that is a very famous program it is around it's called DoRS and it was developed by a company it's called telelog it's weish Company it was acquired by IBM so that is the standard so everybody plus is broader uses doors but doors is a glorified management system for word documents I mean so at some point when you analyze these documents so one thing is that at least you know where they are and at least you know that if you change something you got to change something else okay so structural situation taken care of but what is inside these statements。

 the meaning of these statements is not clear is English so yeah you say English pretty clear well up to a point when you specify for example this thing is to go fast okay define fast I can make something fast with respect to what if the comparison is there's nail when fast is not。

Exactly the same as if you specify with respect to a cheetah right is not so the point is that you have to be precise and you have to say what you mean in the most precise term so that there is no argument so you know what you have to do not only but then you can verify against those statements because being expressed hopefully in a mathematical term。

 then you can run stimulation test， whatever you want， see what comes out and then compare against。😊。

The specification and so you can say yes I made it， no I haven't made it。

 so I need to change my design okay so this is a extremely important part of any design in all your career remember my words if you don't follow them sooner rather than later you will be dead and believe me。

 not literally but that meaning are going to be in real real real tough situation so always try to be as precise as possible and put down things that can be measured because if they cannot be measured how the heck are you going to playing that your design is correct or not and that you have done what you supposed to be。

😊，okay。So。When a design is correct， a design is correct， when it meets a specification， as we say。

 obvious。😊，A designing fat specification cannot be right or wrong because you don't have it。

A comparison， right， to， to run again。 And so simply running a few testament。

 looking at what happens to say， ha ha， this looks pretty cool。 but at going to work。

 So that is the reason why in the specification of your project， it says。😊。

Column thou shall verify your design before implementing it which implies that when you define your project on the platform that we gave you。

 you better tell me what are the properties of this application otherwise you are going to be the first time you are going to be in serious trouble to pass class so it not as scary as when it will happen to you next when you go and work but you know thats okay。

😊，So many embedded systems are deployed in what is called safety critical systems。 So for example。

 cars are safety critical system， of course， airplane safety critical system。

 things that deal with health are safety critical so you know that now one of the largest growing company is a company who makes a Da Vinci robotbo。

 what is a Da Vinci robotbo is the guy that cuts you up right is for operations。😊。

And these robots are so precise when no human can replicate the precision which they can cut you a not very good example。

 if you like， because then you say， how was Da Vinci design？

So you hope it is being designed correctly with formal metal and all of that because it is going to cut you up and so it better be good right better not have bugs right so that is the ratio that。

Security here， safety。 So the challenge of dependable software， of course。

 is that device as we say before， devices that are monitoring your vital science， as well as。

Doing something to you。A built with electronics and so electronics are consisting of software and hardware and you hope that the hardware is not going to break and the software is not going to have backs so that is we think so horrible here。

 the patient collapse while working towards the cashier after refueling his car a week later this patient complaint to his physician about an increasing feeling of unwellbeing since before and so that is actually a software defect of the。

Pacemaker not good at all and it was discovered later that effect was triggered by the electrical field that you have in gas pumps so not good so every time you go buy a gas pump you feel you your pacemaker goes bananas is not very good so all right。

So this is the kind of situations that happen and indeed there is also a very interesting phenomenon and this is due to actually the modeling of your heart because if you want to do a pacemaker youve got to have a model inside the pacemaker itself what your heart is supposed to do and then we a sensors that are sensing in the heartbeat is going up down and stabilizing and all of that。

 so if you have a wrong model。And you' are trying to stabilize your heartbeat Instead of stabilizing it。

 it goes all over the place。 So that is actually has happened a number of times。

 So youve got to be extremely careful then。 So now what is the specification where specification is a mathematical statement of a design objective。

😊，Now notice that I put a mathematical statement about design object meaning that we want to be very precise about what specifying a design is Now a verification problem then is to check if your design satisfy the mathematical formulas that you have used to。

Establish what the property should be。 Now， the controller synthesis is another kind of topic that is connected to it。

 albeit is part of a design itself。Now wouldn't be nice that the design process is guaranteed always。

 that is that is doing what you specify now what will be best if I give you a specification and then there is a wonderful algorithm we take this specification and build the system so that the specification are correct by construction。

Hallelujah， no heart attacks， no nothing， a， and we have it right。

And that is the problem of controllerless synthesis。 So you are given an incomplete design。

 You' are given a specification and get a way either by hand。

 but hopefully better by computer program that implements。😊。

A control loop that makes your device act。As you specify。Okay。

 so remember we talk about model based design in which you start from a model and then you derive the rest of the design I mean this particular sequence so in here you have a model you have requirements and it will be nice to synthesize for from requirement the correct controller so that the model does what is supposed to do so I give you an example of a pacemaker that is a controller It's controlling the rhythm of your heartbeat right so its giving the。

😊，The reference right so that is the controller and the model is the model that you have of your heart and so you want to build that closed loop control so that the system consisting of the heart plus the controller does what a a s heart is supposed to be。

 a hair field is supposed to be。Now of course when you are in design time。

 what you would really like to do is to verify that the requirements are satisfied on this closed loop system and we already say that there may be automatic way actually to get away from verification problem because you do it correct by construction。

 it iss called controller synthesis or you want to be able to run a computer program it tells you whatever you have done up there in the design phase is actually satisfying your requirement。

So among which， for example， there are different。Strategies。

 one of his strategies is what almost everyone uses， which is simulation。Now。

 would you trust for example if I tell you around five minutes of simulation of a pacemaker。

 would you be satisfied to implant your pacemaker in your heart and I see if everybody know you get it。

 why is that because。You want to be reasonably sure but under all possible circumstances。

 your thing is doing the right thing right now with simulation can do it right so simulation is essentially like a virtual test bench in which you put some input you see what the outputs up and so the quality of your verification depends on how good you are in identifying the test cases。

Now there are formal way of defining test cases in such a way that you visit the space with a certain density。

 the space of possible occurrences but you're never sure。

 so people then are very interested in doing what is called formal verification。

 which is again an automatic way of looking at all possible cases。Okay。

 so we need a formal way to write models requirements so that an algorithm can process it and that's formal verification code right that you can buy or you know。

 and but the state of the art。Is not so good， meaning that you can formally verify designs but the complexity of design that you can look at is limited and so that's the reason why I told you about the methodology so if you can break down the methodology into sub steps and every step is reasonably small when you can apply this method if you do flat so you give entire implemented design where every transistor has been implemented and you have a specification all the way here。

 there is no hope whatsoever。No hope whatsoever of being able to verify automatically that this implementation of your design satisfies the required。

 so you have to play given the fact that the problem is mathematically very complex。

 you always have to play the game of restricting the space in which you operate the verification。O。

 so。Talking about this， when you think about your design and you think about what you would like to assert this one assertion is that suppose that I can identify actually vac bad states in which your heart should never go because a fibrillation。

 for example， if you fibrillate not so good so the point is that you want to make sure that no matter what happens。

 for example。Your heart is never going to be in the fibrillation state， right？And so。

How do you express that problem？Right。You want to say that， no matter which trace。

 which sequences of state your system goes， you are never going to touch that particular bad state。

Now， this one is also called a safety property。 So you want to be safe。 Never touch the bed stay。

 Okay So now if you look at this。It says that no matter what the evolution of the system is。

 you never touch the bed scale。Wwhichch implies that you have in mind the fact that the system evolves so there is time involved or in reaction index or whatever you want to call it so there is evolution of your system and your properties have to be expressed in terms of the evolution so are not static properties say oh this state has to be good now you want to save it for all possible evolutions of your state。

 you never touch a bad say。😊，Okay， so that's the reason why we need。Temporal logic。

 so logic is in general a language that we use to express properties in Boolean terms。 So in fact。

 the property is either two or false。 so it's natural to think about the Boolean space to express properties。

 but you want to have a way。 and we know that， for example。

 propositions oral calcluulators or what you want to do is static。So， it's not talking about。

Evolutions and so the point is how can I make assertions in a formal way that talks about evolution in time right and this is what temporal logic is all about now I'm going to post the original papers by Amir Nuelli was a computer scientist from Israel written then at the end of his career went to New York University he was a real real quote unquote genius in the sense that he was very good at logic and mathematics and all about。

 but he had a keen understanding what needed to be done to solve some of the problems that we are a meeting in designs。

😊，So in fact， in 1977， he proposed this temporal logic。

As a way of asserting properties of the design。He ended up eventually winning the Turing Award。

 which is like Nobel Prize of Comp Science for this discovery， for this idea of using this logic。

So now let's look at one example of this， we already say the heart and the heart is in my opinion。

 very good example right and I express you what a property could be another property about the heart is that you want the heart eventually to go to a steadydy state so a regular be and so there is another temporal property。

 you want to say I never want to go into fibrillation but eventually I want to go into a good rhythm so I start bed the controller kicks in I get the impulses given by the pacemaker and then my heart is going to settle down to normal operation so that how would you express that you want to say that eventually so at the end of a trajectory you are going to be in the state that you desire to be the previous one I said you don't want to be in the bad state in this particular case I say eventually you want to be in a good state。

😊，Okay， so are and these are essential to insights that Pnuel had。

 it's like we need these two basic constant eventually and always don't touch robot state right so these two constitute the basis for building temporal logic。

 Okay so this is another example is a space wire protocol is a European space agency standard and it's all about what happens if you detect an error right。

 So something goes wrong And then in general， what do you do when you can' work with your computer blue screen and keep some blue screen and all that。

 what do you do。😊，Reset but that may not even work， right， So what do you do。

 There is the way ultimate reset when you take out the battery right， That's my last resort。

 right if you take out the battery， put it back， still a problem。 your host right， but in general。

 that is the ultimate。😊，What does that do now， what does， for example。

 powering the thing off and restarting or battery yet in taking the battery out why because nothing everything is gone and you have to leave it there for say 30 seconds。

 Why do you have to leave， for example， when you go and call the cable company they say， oh。

 it doesn't want to say take out the modem you know unplug the mode classical and then leave it there for at least 30 seconds？

정화 있어요。Any wild idea why you have to keep the thing there quiet for some second。

So for the capacitor to discharge， the capacitors are keeping the circuit alive right and for example。

 I don't know if you ever heard of a supercapacitor the supercapacitor these uongous structures that are used to store energy so capacitor storing energy now of course it loses energy through leakage gen。

 but in principle。😊，If you put voltage across a capacitor there is an accumulation of charge that stays there forever so now we leave it there 30 seconds because then there is a discharge that occurs because of resistances if there were no resistances it wouldn't work and would be host anywhere okay so a 30 second is because of it so dont do do because it is not going to work it's not really going to reset okay so reset is important now。

Designers。Always think if someone wants to reset a system， you know it， for example。

 you have to put there is a reset button on your to。Aim it with， with a paper clip and all of that。

 Now， what does that do。ーロンペア。一。いや。Not so much for the initialia state， let see。Exactly。

 but what property does wenoa have to have？The。Yes， so it has to be known right。

 so the reset state is something that we know about， right？

Because many of the problems that we got within didn Lewis formal verification。

 we ended up in a bad state and one classical thing of a bad state is that I don't know where I am。

I have no information。 So if I want to do something。

 I have to be sure that Im in that particular state。 So a very set state。

Characteristic is that I know what it is。 And so that is through the initial state。

 but is the ultimate initial state， because I know what it is。

 So I know that I can restart from that because I know where I am。😊，This is what it does。 right。

 So they essentially think says well， if something that happens， Go to the to the。

Reset state and then until the reset signal doesn't disappear you stay there when the reset state disappears。

 you go to a state which is called weight error so you wait for the real input to come in and to restart the operation and it's a protocol right it tells you what to do what sequence of things you got to do and so if you look at the at this specification so this is specification it tells you which sequence of things must happen how long you have to wait in a particular state and what is the next state after you have been in that。

Re reset error state。 right， So all of this imply that you have to give。The name of a state。

 you have to give the property that you want that state to have。

 and you want to also tell something about the evolution from that state on。

 So it's classical case in which you need temporal logic。

Now this one is another good one since you had to fight with it so in your eye robot exercise because what it says is that you have a starting position of a robot and then you have a bunch of obstacles and your case was actually falling down from the ramp and then you want to say that you want to get to your final state and if I remember correctly your exercise was to march up and then march down from the ramp and go back to the initial state so in this particular case the initial in final states are the same it didn't matter what the trajectory was as long as you didn't fall。

So is this a safety property？Only so would you be able to specify what the system has to do just by indicating the bad state or no？

Well， for sure of a bad state， right， you don't want to fall down。The ramp， right。

 So that's the best day off the ramp。It's a property， never off the end。이ザ티나。No， what is missing？

You need to come back right and so eventually do I tell you about no I say as long as it can be 200 years hopefully not。

 but in principle，200 years would be correct。😊，You can put the time。

 but the key point is that eventually you want to be back to the initial state。

 So you save with two propositions like。Same thing here right so eventually you you have to avoid the obstacles and then eventually you have to be in the state phi and for your exercise in your class you have to do it now it would be interesting and I think you would see in your next lab some tool in which you can do things but。

드라이ト。Write down this condition as we just said in mathematical terms and try to verify with the simulation if its properties are two or not in principle。

 you could also synthesize a controller and design that is for advanced gra so we undergra don't panic okay so suppose that end destination when of course where robot you may want to say that I'm going to visit all this destination in sequence right and that's another proposition that I need to state which is related to the evolution so I want to go to through  phi1 Ven5hi2 Ven5hi3 Ven5hi4。

 when5hi whatever okay。Good it's more complicated， of course， than phi。

 but from a mathematical point of view， ain't that more complicated。Now， okay。

 so we saved all of this， and so we have to start building this logic。So logic。

 if any one of you has done any whatsoever little class of logic。

 you know that the first thing you got to say are the atomic formulas。

 so it's where you start building everything so because in general logic or a computer language or anything of that sort you have to start from the basic clauses the basic things upon which you build。

The edface that you want to build now the point is that for example， also in mathematics。

 pure mathematics right these are called the assertions right that is where you start from the postulate that you cannot prove because you don't have anything to prove against right so these are facts so these are the formula so the meaning for example。

 if I write x and x is a pure signal writing x in the formula mean x is present。

Remember that x is present is different from the value of x。

 I can have x which is from 0 to 500 but the fact that x is there or is not there。😊。

Is a logic proposition， I'm here， I'm not here。 The other one is a numeric proposition。😊。

now x equal to 1 means a x is present and S value of 1 this one from 51。😊。

Now S means that machine is in state S。 so these are proposition， basic proposition。

 the value is true or false， you know because that proposition are in ve logical space and so01。

Propositional logic。 So propositional logic formulas。 So at this point， I have to build。

Uuppon this basic stuff right that we said before。 Now， how do I build。

I have to define operations on the basic stuff to get another stuff that belongs to a space of the good stuff。

 right， And so in the logic， you have to define。😊，These separations。

Now the that we have here is and or implies a no so what is or or means p1 or p2 is true and so which means that p1 is true and p2 is false the formula is true。

P1 and P2， both of MF to be true， for the formula to be true。Then you have P1 implies P2。Now。

 this is start getting more interesting， right， P1 implies P2 means if P1 is true。

 then P2 has to be true。This is the formula， so may true or false， by the way。

 So you have your system and the system goes and P1 occurs。When if Pwou is true。

 then the formula is true。😡，So it doesn't have to be 01 or over， it is a logical statement。

 so if P2 is true after p1 is true， then you say that the is satisfied for red P1 and P2 now not p1 is true if p1 is false we all know and so the p1 and P2 that we put there are either the facts that we had before。

Or one of these formulas， so I can add a composition， so I can add p1 and open pair insesis。

 p1 or P2。😊，Actually， let's put P3 or P2 otherwise it's ins。Okay， so that's。

The fact that I can build as many formulas as I like using the basic operations and the data now。😊。

question。 So if a P1 is false， what does the expression P1 implies P to evaluate2。Right， but letC。

Who has。So it says is true。 are there opinions。And why is the。Sa的嘅。Through all fault。In some sense。

 yes， I mean， you have the point is that I'm not saying anything about B1 being in false。

 right in some sense， when I say this， but actually。

The point is since I don't say what it is when P1 is false is true。Because is' a statement， right。

 So if I don't say anything， it evaluates too truth。😊，Is really a don't care between you and me。

 but by I have to say convention， we say is value， also there is another way in which you can state P1 implies P2。

In which you immediately see that。Which is called a contraposition。

So can anyone tell me what is a contraposition corresponding to v1 implies p2。

 which is theneation of this？Well， you can write it down in terms of P1 is always two or something else happens。

 or you can yes。Perfect， not P2 implies， not V1。 and so of course。

 that formula evaluates to true right in because case of P1 is false， right？So here we go。

Execution trace of a state machine so we know execution trace you know is a sequence of states in apples right so is in some sense a recording is I always like to think about it as a black box of the execution of finite state machine the black box the thing that records everything into your plane when it goes down and you pick up the black box and you figure out what happened so this is a black box and execution trace is what is in the black box of the evolution of the finite state machine。

😊，那。As we say， temporal logic is reasoning about evolution， so what do you have to reason about。

 you have to reason about traces。So sequences of states input and outputs。Okay。

We the propositional logic on traces starts with an axiom again that if a property P holds for a trace。

 then it must hold for an initial state and if it goes for an initial state it must hold for every state in there and this is by。

De finish。We say that P holds， if and all if this is true。 So it's not with。It happens， right。

 is by definition。 So we say that， for example， if you have a proposition that is valid in Q0。

 but not in Q1。Then they。Logic formula P does not hold。😡，For veterans。 Okay。

 so its to be true forever， yes。N， no， no， because it's a definition， right， induction you build。

 That's what I want to be very clear about。 right， But is' no reason why you could say if this proposition is true and the initial state must be true for。

There is no。Maybe， maybe not， but then the fact that we say that this proposition holds for the trace implies that is always true。

Okay， so it's a definition。We are not through the induction yet， okay。All right。Is odd。

 but you have to start from somewhere and is's like the initial step of the index。Now。

 what kind of formulas do I have， So P means that p holds in Q 0 a and now we come to the interesting operators。

 Now these operators that are G and F and so on， N X and U。Are not belonging to a standard logic。

 and that's where the temporal aspect comes into play。

So the G means that global is a globally operator， which means that for every traces that I have。

 this must be true。The formula Phi must be true。And that's the reason why we say globally。 So。

 for example， I would use state the safety property。

And never so suppose that phi represent a set of bad state。

 and I want to say that no matter what the evolution of my system is， I never go into a set fee。

How would you express it with a G operator？It's a bit too much， right， so。

So I wanted something very compact。It is what you say， but you have to compactify。

So how would you compactify any guess any。Recommendation， how would I say。

 so globally is true right so I have to use global right。And I say。

 I don't want to be in the state fee， so。Alright， globally not。

So which means that no matter where I am， no matter which sequences I am in。

 I'm never going to be in a set fee， so globally， not fee。Okay， so which is what you say。

 but instead of saying v or red or red or red， just say not fee because globally not fee means for everything。

 never fit。😊，Right，So it's a Yeah， which is essentially， I mean， intuition is what you say。

 But this way the saying it。Yes， because phi is the proposition and globally not p means but for all state okay so now F of p。

 okay， F of P， F， F， what does it mean future， F stands for future， So mnemonics， G globally。

 F future。😊，So now what is the meaning of that in the future， I want to be in some good state。

 right something good must happen。Eventually， so it may not be through at the beginning。

 but Im going to be there。 So this is the。Pacemaking， right， So eventually。

 I want to be in a good state for my heart。 I didn't start that way。

 and all the controls for certain number of steps may go banana steal。 But in the end。

 I want to have the pace that you're supposed to have。I would use the F operator。

So that is true if for a very trajectory Im eventually。That statement holds。 And from where on。

 right So there is a time in which the thing is true。 And then from where on， it always holds。

 and that is F。Now， x of the。Xophy implies the next state。オペレイト so I meanき。K， right。

 I'm in particular state。And if I say x phi， it means that in the next state。

 so I take a transition I'm sitting here， the proposition must be term。Okay。Now then p1 U Phi2。

 that's an interesting proposition as well。 by the way。

 I'm used to say phi because that's the way the Greek people pronounce it unfortunately I did unfortunately I did classics so this is the way in which the ancient Greeks pronounce it but in America say phi in which kind of okay so I can't get myself to say phi and so forgive me。

 but it's the same thing it that funny later so when we say phi。😊，Until phi2， phi1 until phi2。

 what does that matter， So if you start thinking about it。Until right phi1 until Phi2。

 So it means that for a certain number of steps， phi1 is true。Until another proposition becomes true。

 And then I don't care about what V1 does。 It can be always true。 It can be always false。

 I don't give it damn。Okay， so this P1 until P2。 got into that situation。 Okay， I'm cool。

 And no matter tell what P1 does。 So， for example， this one again， talking about the pacemaker。

 P1 could be don't die， Don't go into a fibrillation state until you are in a good state So you don't need anymore to check for fibrillation so P1 is certainly true。

 maybe force， but doesn't matter because I am in a good state anyway。 So okay。

 so this is a use of P1 until V2。 now。😊，There is an interesting point that are all of these statements or these operators necessary or can I express some of this statement in as a function of some others。

 so in other words， what is a minimum set of operators that I can use to express every。

This one is redundant， by the way。 So there is a show。 Well， I'll let you think about it and come up。

I think it's in the book by way， so but if you think about it what will be the minimum set of statements that I need to express everything that I put down there。

 but you have it because it's convenient notation has to meaning one is to of course to describe what you want to do but the other one is to be concise about it a notation helps people to reason about things something more concise it is the better it is so maybe that one of these operators actually as I said it is through can be built as a sequence of other operators but makes my life more complicated。

 just use one later I'm done and so。It is good to have all of this。 So P is a proposition。

 G means globally。 F means finally future Eventually， X next state。 and until U is until。 Okay。

 So we said already， we gave examples。😊，And that's it。 So this is what is a linear temporal logic。

 Okay， so it's called linear temporal logic。Now， as this is all we can do， no。

 there are certain things that I want to say that I can't say in linear temporal logic。

And so people went bananas after Air Newelli started talking about temporal logic。

 then people invented computational tree logic and then people invented computational tree logic star。

 and then all kind of logic and then they say probabilistic temporal logic and PTL and so on。

 so everybody's invented the new temporal logic concept。And why is that because it's not universal。

 so there are properties that I cannot talk about。And so the issue is that I have to enlarge the space of the logic language that I'm going to use now。

 as we all know， the more general you are， the more host you are。

 meaning that to verify if a particular system satisfy that formula。

 may be relatively easy or incredibly difficult。😊，So many of these logics are undecidable。

 which means I never know if it's true or not， right so I cannot have a guarantee。

That if I'm applying my rules and all of that。Im and the answer is maybe， right。

 because I didn't get a counter example。So does that mean it's true， I don't know。

 I have to keep on going。For how long， I don't know Unciderment Okay。

 this is the meaning of undeciidement。オケ， so， for example， the basic。A modelel of a computer。

 which is a touring machine to。Answer the question。

Is my to machine going to halt eventually is anyable。I mean， we are talking about really bad stuff。

 So everything that you do in computers is bugged by by the original。

everything that you can claim about the way in which your computer operates unless you restrict the space。

Is undecidable。 So maybe maybe not。 And so that's the reason why you get the blue screen。

 Maybe maybe not， not， O so。All right。So ge， we already talk about what it means globally。

 so if you have a trace Q0，  Q1，  Q2，  Q3， globally true means that for v sequence must be true。

 but also the sequence  Q1，  Q2，  Q3 has to be true and also Q3， Q4， Q5 and so on。

 so all the sequences that it can build the tail of the sequence that you can build has to be true。嗯。

Now嗯。The globally then is that it must be true for all the forever so of the traces。

 so if it holds for Q0， it must hold for all the secrets。

But you can build all the traces of that system。Okay。So。The LTL formula GP holds for a trace。

 if and only if P holds for a very suffix of a trace。

 so this is related to the fact that we have talked about LTL only for one trace because the linear temporal logic is defined on traces。

Now， when we want to assert that my machine satisfy a machine， not anymore a trace。

 a machine satisfy fee， right， globally satisfy me mindset for any。Trace where。

 right for all of them， right。For all of it。 Okay， so that's the way in which we。

As serveve properties about the system。 We say for very very trajectory of that system。

 we know that this property is true So it is shorten is true for the entire machine。

So Miss we already said and so。So and indeed， when something is globally true for any sequence in the damnm machine。

 then we say it is an invariant， so it doesn't change， it's always true， it's an invariant。

And by way， the invariance， I don't know how many of you have done ever。

Or read papers about proving properties of programs。

The way in which you do that is by proving that invariance hold， right。

And that was the first time that this nomenclature of imvariant came about。F。

 we say before eventually， finally， so it means that thetl formula F P holds for a trace。Q0， Q a。

 if and only if p holds for some suffix of the trace。Now by the way， this small between you and me。

 I never like a definition stated as if and olive because if and olive is a necessary and sufficient condition so I would really very much like you instead of using this notation that unfortunately many people use on this one I have not written this particular piece of slide。

Don't save it。 and say by definition， this is true。 Okay。

 don if and only It's the same thing logically， but not and it's not。

 because it says that you don't have to prove it。Is a definition。So if I say my。For example。

 I can say a sequence of calculation the fixed point theoryorem， for example。

 it says that if you put x0 into f and then you get x1。

 you put x1 into f and you get x2 and so on and so forth its a fixed point calculation So you keep on putting the results of applying f into f right then we say that if certain particular condition on x on the sequence of x's。

 then you know that this is going to converge right so you're going to get x equal to f of x eventually so you put something here comes back identical that's a fixed point。

So there are condition under which this is the rule， now that is a sufficient condition。AS condition。

 for example， is F is a map of a unit circle onto itself。That is a sufficient condition。

Which implies that I may have another function that admits a fixed point that is not from the unit circle to itself。

But。I cannot say， so the difference between necessary and sufficient condition。

And sufficient conditions， that necessary sufficient condition tells you that if this thing is true。

 then this thing converges。But if the computation convergence means that the property is satisfied if and only if。

 but you have to prove this， is not。Instead， if I say。

My system is safe if I never get into a bad state， that is a definition。

 I don't need to prove it is a definition of what it means a system is safe right so don't confuse at all please please please please okay so its a very different statement so this one is not relief and only if is the definition by definition is okay now。

What it means， So if theL formulas， I suppose at some point the formula Phi2 is true at Q2。Okay。

 then from Q to on is always true。 So that's the meaning of the formula now。Yes。😊，Yeah， globally。

no window inva， O。The，Should should also also for Q free Now there is another form of the future。

 and it means it has to happen infinitely often。So in other words， it's true at this point。And then。

It may become false， is false， is false， and then it becomes true again when falses false for。

 it becomes true again right。Okay， so this， for example， when you want to say。

 suppose that you have an item dont when you race right， so for example。

 when you do a cross country race。😊，Then you must go through where correct。

So it must be true that you go through the。Exact points， right， in between， you can do whatever。

 but you have to go through this。Same thing as skiing， right， So you have to go through this。

 Now in between， you can do whatever you want， but you have to go through this。 right。

 So that would be miss。A reppeetition， right， but it doesn't have to be true for all states。 Now。

 and here in this operator and from then on on as through Vietnam。

Now proposition of this another interesting thing is that of course LTL proposition can apply to other LTL proposition so it can have a nest situation and so here you have G so globally must be true that x implies eventually y。

 which means that every time you hit x。You sometimes in the future FY。

And this statement has to be true for all possible theories。Okay， that's globally。Da da da O。

 so I can nest any any formula at Taiwan。Because that's the way in which we build the logic。

So globally。😊，If at any point in time x occurs， then it is eventually followed by y。

 So this evaluate to one if this condition are satisfied， so evaluate to true。

 I shouldn't say one to true。Now， every input x is eventually followed by an output y。

 So this one is what we say before。 Now let's look at what happens in the state so x holds。

And then we got Q1 so if and only if it goes for any suffix of a trace， blah blah。

 so this in this particular case x holds and so y has to be true sometimes in the future so and the y and the y property is the pink circle so this means that every time Q1 holds then I see that eventually sometimes later。

Y holds。So when is a temporal logic formula satisfied by a state machine。

 so we say satisfied a linear temporal logic formula satisfied by a state machine if an olive meaning definition？

Every。Trace in that finite data machine satfi with formula。And it is absolutely trivial definition。

 right， so it's very intuitive。Example， so I have this particular finite state machine that simple couldn't be。

And the statement say， I want to say that globally X implies that there is going to be y eventually。

 Now， is this true or not for this。For this machine。I say someone of you says， yes， is a consensus。

It is always， it is valid。 Yes， looks like it。 So why。Because no matter what happens， I'm in a。

X is present， I go to B。And then， whatever happens。I go to y， true means is always。

 I always take better transition。And so anytime I get an X， which I go to B。

 I always get I have to get back with an up y。 So this is all wisdom。 right。

 no matter which trajectory I take， this is always wisdom through。Okay， now this is a bit trickier。

 Does the following whole G if x is true then eventually y through。 So is that。들어와나。

It looks like almost the same as before。You can prove its false in this particular case。

 How can you give me a trajectory event will make it false。He name me。Yeah。

 and so but what kind of machine is this？Non deterministic。 So you have a choice。

 And so the choice is what kills you。 That is what makes the thing not true because I keep on staying。

 right。Yes。转的照片。Oh yeah， you can to satisfy any kind of property you want。

 This is such a stupid machine。So but the important thing is that that is what we need to prove。

 right。So we don't have to find the largest property whether the machine defines right so this is just to show the simplest thing possible to explain the concept。

 So now notice that something yes。😊，ワピ。No， because remember that this one is after model。

 right so this is presence or absence。So come after that's okay too that's。No， no， no。

 is that whatever， but important things is that from 7。 on is true， which is always true Aeluja。

Be get。Okay， now what is layer trace， we already say what layer trace is and is because of an undeterministic choice right。

All right， third L TL operator， this is stupidest operator。

 it simply says that the property has to hold for the next day okay right so here it is。

 you say formula X P。Must be true in Q1， right， So the next state has to be true。Now。

 the fourth operator is until we already discussed it。 You know， you know。

 this is true until something happens。 and then all the bets are off， right， so it can be true。

 may not be true。 Who gives a them now Fi to。Takes replace or P1。 So when we have Q0。

 So the P1 holds， and then Q1 holds， and then Q2 holds。And then Q3。P2 holds。And now from then on。

P2 holds， and I don't give it them about P1。 That's what it is now。Talking about what you say。

 if P1 continues to be through Aleluia。And in fact。

 there is an operator that is called we until it does exactly right。In some sense。

 so well more of in priority it says that for example I say I don't want to break my leg so I'm running down the steep you know and so I cannot go faster than 10 kilometers per hour until I'm flat。

And then I can go 500 kilometers per hour if my legs allowed。So that's until 10 km after that。

 go to whatever speed you want， right， because it's true my time flight。So I may not be able。 I mean。

 given my speed， I probably you know， well I can go faster and thank you at this better。

 But the point is that I may be。Impeded to go 10 km because I'm old。 and so I get there。

 and I'm flat。 I could go faster， but I keep going 10 km。S which is。Certainly satisfy。

 but I don't care。Okay， we can think， there you go。In which， you know。

 does not require P2 to mention this variant。 doess okay， so remember， So GFP。

 what means that globally eventually peace through and FGP eventually。

Globally peace through and so on， all the kind of combination you can dream of right so you can mix and match whatever you want。

 all the formula is okay because that is the standard rules according to which you build a logic。

Let's say that way any nesting of the basic operators has to belong to the space when you start the firm。

 so any composition of this belongs to the space or linear temporalology。Okay。

 so we already say P holds infinitefinly often GFP FGP eventually P holds ends4 GP implies Fq and every P is eventually followed by a Q。

And this one F P implies X X Q。 If P occurs， then on some occurrenceencies。

 it is followed by a Q2 reaction later。 So I have to use X X in。 Okay， one step， two steps， yes。

Has to be， has to be next state。 But if it is true from then on。Doesn't matter。 Okay。

 so a statement is about the next state。The next。Okay， whenever the arobo is at very ramp edge cliff。

 eventually it moves five centimeters away from the cliff。😊。

So the P propertiess I robot is at the cliff and the Q I robot is5 centm away from the cliff。

 Now that is some properties but your solutions for the I robot to move up and then down as to satisfy。

Now， whenever the distance between cars is less than2 meters， then the cruise control is deactivated。

Well， actually now you have what is called adaptive cruise control。

 and what happens is that you adapt the speed of the guy in front of you。

So you can still go in cruise control。 It maintains very safety distance。

 and you don't have to to mess around with a cruise control。 Okay， so， but this is。Another example。

 temporal operators and relationship， so GFX and U。

 all of them express properties along system traces。And then the question is I say before。

 what is the basic number of operators that you need to be able to express every other operator？

And so can you express F in terms of U， what about x in terms of GF for U。

 and so this is an exercise， the answer is yes。Except for the last one， the last one， intertroim。So。

 for example， can you spread GP pure in terms of F is where it say。

 right G of P means that F of not Phi is never true。Which means that， eventually。I never I fee。

 which means globally， I feel。About F in terms of U， we can say F for P is true until fit， right。

 true is always true。 So you know， it's obviously you obviously can do that， but this cannot be done。

Okay， so the basic operators seem to be。诶F。N U So with F N U N X， I can build G。

Some points to pond there， so a mathematical specification all include properties that the system must or must not have。

 so the point is that there must be some human which says that this is a correct property to assert。

So the bad stuff is always at the beginning。 So the origin of everything。

 are we sure that what we specified is correct。 You know， for example， I mean。

 hold on to your seat because。In some of the standards that you have around。

You can prove that the specification are。インクン systemステム。

Which means that if youre applying a logic formula for all the statement。

 you get a false statement song can never be true。And so I'll come then for example， a specification。

100 plus pages， big volume of the pi buss or pi buss。

 one of many buses where is used inside a laptop or a computer right now in that we try to codify all these things and after。

20 pages we already found1 inconsistencies。 then well let it go， right， And then you say， well。

 but that is a standard， right， And so people build against that standard。You know how it's done。

There must be some。Something that people compare against。

And so what they do is that there is someone in the standard committee that gives you what is called a reference design。

And this reference design is safe， this one， satisfy。The requirements， of course， it cannot be right。

 because the requirements are inconsistent。But someone said， well。

 this is essentially this is the best I can do， and this is good enough。

And so everybody else checks if he's compliant to the standard with respect to the reference design end of story。

 So they don't give a damn about the inconsistency， which I would not。

Follow if we are talking about safety critical system。 you。

 So my specification that I shall not die if I put my pacemaker。

 I want that to be through and not say， well， okay。

 this reference this has not killed anybody so far。So far， okay am I good enough with that statement。

 no， so that is a different。 So in fact， there is a market， if you like。

 for things that check the consistencies of the requirements。

So you can say is everything that I wrote。You know kind of clashing so like I want the cake and eat too。

 you know in Italy we say you want to have your companion drunk and your bottle of wine full right and kind of contradiction right so the point is how do you check kind of contradiction you can do that right so there are programs that do that。

And so you run this test to see if you have not said something obviously stupid。

 So it's analysis of the requirements。 So requirement analysis。Fine。

 so assume that you have this wonderful tool and that you can indeed check all the requirements。

 which implies that all the requirements can be written in temporal logic or some other logic because otherwise。

 how can you do that。😊，But am I。Satisfied enough of my set of requirements or not。

So all what I've wrote， I've written doesn't clash， so it's consistent， okay， good。

Is this a necessary and sufficient condition to be satisfied with what I've done？

Or is they necessary？Necessary for sure。Yeah， so， but is that enough。Now， what is。Complete。

The other thing is completeness。😊，Who tells me that I put down all the requirements？😡，Now。

 who can do it？Go in person， right， because。Where do we compare against and that is the biggest problem of requirement engineering is to be sure that you express all what you wanted your design to have。

 so sometimes you have a wrong design and you have disasters because you forgot some conditions。🤢。

And this is， for example， for rec effects， of things that kind of happen that you never thought could have。

So in fact， there are tools that tells you that explore the space。😊。

Which means they try to poke at a combination of variables that you have say nothing about。

And then they come to you and are saying， look， if set this variables to this value。

 the following happens。A you sure don't want to say anything about it。

And this is called requirements space exploration， right。

 so but this is still you can never be sure So and this， unfortunately， unless we are God。

 we can solve right， the initial step is always。Very difficult。 but if we have everything okay。

 I feel pretty good。Okay， now。Getting a specific version right is often as hard as doing the design。

 My own opinion is that in the end we are going to do everything by synthesis if we do all these steps right and as I say before。

 like platform based design and over。😊，Everything can be done automatically。

 but the original specification。 So the original specification is the design。😊，In the end。

 20 years from now， that will be the design。Is the writing thing that Im a specification？Mmh。

So interesting researchdirect are inferring temporal logic for system traces。

 So in this particular case， I I say， okay， this system is correct。

Now can I see what kind of properties this system has got that I can abstract this s to a question that he asked before and say。

 well gee， that small machine satisfy even stronger conditions and I said but in this particular case it's a reverse problem which is this one so can we build the set of old properties that a particular design that I give you through a set of traces satisfy。

Okay， so that's inferring temporal logic from system traces。

And then the other thing is that remember what I say that everybody does and that everybody uses doors。

 I mean， when I say everybody means everybody in the world， but that is English， right。

 so natural language。😊，Now， can we。Try to extract from the natural language with what these turkeys have written some kind of mathematics。

Now， if that is the case， then is great because in general。

 system designer are not expert in temporal logic and don't blame them， right。😊。

There are all kinds of grain ones in there。 the grain ones is that you constrain the natural language in such a way that you have a formula sitting behind that's called patternter based。

Spation。Capture system pattern base means you can say the following word but don you don't use other words right so the English you can only use words in this sequence and words in this combination right and then I can build a logic temporal I mean a linear temporal logic or a computational tri logic or whatever other logic you want behind the scene。

So you can see when you say are still intuitive。But I can build the thing behind it right now。

 this is a boundary。 This is the place where， for example， we work with IBM。

 IBM is a guys who have doors。And they would love to have such a system， of course。

 because all of a sudden， then we can sell more simulation tools。

 They can do better design everybody's up。So that will tell you。But even at an undergraduate level。

 you can still kind of formulate very modern research problems that there was so big impact in the domain。

 so this specification mining so you got horrible system like that and then you check it out and you find out that all the trajectory of that system satisfied following property at the second time is 7。

25 millisecond and the overshoot is under units， which means that all possible trajectories that I am getting out of that system satisfied is two properties。

So it must be that this is the property event。If I do redesign a Web system， I must assert。 Okay。

 so that's a specification line。Now the space wire specs is the Turkey protocol that we showed before is that very set state。

 what happens when something goes wrong and where you have to go ettera。

 so you can write in temporal logic those specs and also you can also write in temporal logic。

 the I robot specification， that would be interesting because you could do then in the lab try to see whether your implementation of the control。

 satisfy what the design is supposed to be。

![](img/ebc70632d70bdd35771e3c1770a280e6_1.png)

Okay， that's it。 That's the end of class for today， and we are 10 minutes early， so questions。

Of any kind of sort。About soccer games， I can answer that too。Probably better。



![](img/ebc70632d70bdd35771e3c1770a280e6_3.png)