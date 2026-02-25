# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P8：-08-Lecture 10 - Composition of State Machines.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Okay， guys， let's。Let's start after all， with setting up of the machinery。

Okay so today we are continuing on on the finite state machine discussions and we are going to extend the model that we have seen the basic model that we have seen last time with additional features and make finite state machine usable in a more general context and so we are going to talk about extended finite state machines and in particular there is a topic that has been very much studying the last 10 years or so its called hybrid systems。

And hybrid system actually is。A mathematical formulation that is very much used in。

Field that now is very， very， very， very， very fancy。 It's called cyber physical system。

 we talk about it in the introduction。 so without further ado。

 let's go on so the questions for our model is how to represent a system that we want to analyze for systematic analysis and so that a computer program can manipulate that model。

😊，Okay， so it can optimize it， it can simulate it， it can change it。Now。

 the other thing is that how you model the environment which a model is going to be。

Inserted and also how you want to compose。Different models to to build a bigger one is like a little go block approach right so you take different pieces you want to piece them together so that you get a bigger thing right so now in general a this one is as I say it is a general concept when you model something you can do it what is called at the lowest level So we also say you model the system flat in general。

 when you model system flat， you have way too many。If it is large， way too many equation。

 way too many。Things to worry about。 So most of us think in abstract terms。

 So we try to get away things now there are two kinds of simplification that take place。

 One simplification is is abstractions you throw away things that you don't want to see so in some sense you aggregate parts of your model so that you can handle it。

😊，The other way is to think about the whole as being。

Composed by a number of smaller parts that you plug together。

 So this one is composition is a composition operation。

 Now composition is a basic concept also in computer science in algorithms。

 whatever field you want to think about this notion of building bigger things by aggregating stuff is a general one。

 So now the point is that what are the rules according to which you put them together and that what makes the stuff interesting and not obvious。

So let's get this out of the way。Okay。Now， recall the F state machine notation。

 we have states that are labeled with a name and are encoded in a particular form when you have a guard。

😊，That tells you when you can take a transition on the finite aid machine。

 corresponding to that transition， there is a setting of an output and so the way in which we indicate that we say guard slash action。

We also have to give an initial state so an initial state we have to indicate it somehow。

 I told you that in general， in a finite state machine notation。

 you put a double circle to indicate where you start。Okay， and then of course， you have cell flu。

 which means that under a particular set of conditions， then you stay in the same style。😊。

So you do an action， and reaction action is。Stay there right So since it is a transition staying there in this model。

 it means that during that transition， you can output something right So you keep on looping。

 but maybe but something changes and is the output during this looping okay。

Now Gar counter example we already did this， we have a model that has M states where M is the total number of positions that are available in the garage and so it is a pretty stupid finite aid machine if you like is all the same right so M times repetition of the same thing。

😊，So what would you immediately think about simplifying this one。

 does anyone have a wide idea about how you can simplify this continuous repetition on the same thing？

Exactly， so what you could do is that this one is essentially a counter， right。

 it counts up and comess down right and so at every transition you output something。

But that is always the same actions， so why don't I reduce all of this？Just with one state。

And this one state is character by a self loop， which outputs the counterpl one， right。😊。

And so this is a way of implementing a counter it iss just a single state and so that's the way it goes here it goes right and so there are two self loop one which says okay the counter goes up by one so there is a new car coming in and one goes the other direction a car leaves so you have a self loop and the count is decreased by one now notice that the output at this point in time is no longer a pure signal is an integer which corresponds to one。

2，3，4，5 n。😊，And so this one strictly speaking， is not a pure finite state machine。

 a finite state machine whose output。😊，Is a natural number， okay。走。

But it simplifies the notation of the finite estate machine greatly。😊。

So what you do is that you encode that information that the state is changing， right。

 all same goes up and goes down and saidter is capture。By the self loop and by the variable。

 that is assigned with a transition。😊，AndSo that variable grows by one or decreases by one。

 And that takes into account all what we said。 Now。

 notice that the condition under which you take a transition， a self loop contains。

The variable that you have inserted the count variable， and so if count is larger than 1。

 then you can decrease if count is equal to0， then nothing doesn't make sense to decrease because it' is an invisible situation。

😊，A car cannot live in a place where there is no car so that is what this representation does and so the output instead of being a pure signal so absent present at this point in time is a notch on them。

😊，Okay。Now， the interesting point is that what is the size of a state space because the state space before was M and this time it seems just one。

😊，But remember that you have also to take into consideration the space that is indexed by the output variable。

 so the state space still the same。 this one is a shorthand notation to avoid to say stupid fake okay。

😊，Now， the general notation then for extended the machines is the fact that the outputs。

Can be variable。Okay， so let's say instead of being pure sickness， they become variables。

So I can take real numbers， I can take values on when set of natural， whatever you want。

So this is the extension of the notation of the finite state machine。😊，And so there is a guard。

 there is an output action and a set action， the set action means set the variable to a value。😊。

That before they didn't have sense， because didn't make sense because we had the pure signal。

 So the fact01 is all you need to say。嗯。Okay， so that's the extended finite aid machine。

 Its interesting to find out。😊，There。If you take values， very variable。Take value on a finite set。

 Then this is still a finite state machine。 Remember 0 to M。 we know we already dised into M states。

 So we know it is a finite state machine。 As that the。

Set action involves variables that are in the real。Okay， so the real numbers。

Can you claim with that so you have which states， but the output instead of taking values in a finite set takes value in a real。

 okay in the set of real number， is that a finite state systems or not according to you？😊，No。

 no its not。 It's no longer。 And so， in fact， it's very interesting because。😊。

Certain questions about the behavior of the finite aid machine。

 when you have these outputs that take value on the res。😊，Cannot be decided。 So you cannot say， yes。

 it works。 No， it doesn't work。 So it's an undecidable problem。 So incredible。

 right So you set a variable。In the Rios， and the entire complexity of the game changes dramatically is no longer a finite state system。

😊，But it's very convenient to model things right so when you can do which trick can you do well you put the bound of the ear。

 it cannot be larger than20 its say and then you discretize and all of a sudden the thing that was not finite becomes finite but because you start throwing away stuff and so there are tricks in which you can still answer questions and things like that。

 but you have to do an additional simplification。😊。

Now let me give you a realistic example what the controller of the traffic light looks like now this traffic lab。

 can you tell me what he' saying？😊，What is the operation of it。

 so read the model and tell me what this traffic light is supposed to do。Traffic。

 light control and supposed to them。So what do we see， We see。ure pureure signal， which is red。

 yellow and green， that of course， is either red or yellow or green， it cannot be partially yellow。

 partially green or something like that。 So that is a pure signal。😊。

We are pedestrian pedestrian means there is a guy who wants to cross the state。

 and so also that there is， there is no right So that's as simple as that。

 and we have a count which takes value on a discrete set。So it is still a finite state system。

 and this set is0，1，2，3，4，5， up to 60。So if you look at that。

 so we start from an initial state and assume that the initial state is red， what does we say？😊，Well。

 it says that I'm staying sitting on the red。By incrementing the count， right。

 so count plus one count。Is 0， so it becomes1， it becomes2， it becomes 3。 it becomes4。

 So it stays red。Now。When the count is larger or equal than 60。😊。

I take the transition and I go to green。And I reset the counter。 So what is this counter。

What does it represent？Time is time， right， is how long is going So assume that one count is one second。

 So it means it stays there for one minute right in the right。

And when the count is larger and one minute， then it goes to green。

 but it reset a counter why because now same thing。 So I'm going to green。

 and so I have to decide when I'm going to go from green to yellow。 Now what happens there。

 So if count is say as long as counter is less than 60 I count plus one。Now。

 if I see a pedestrian that is there， M count is less than 60 when I do pending and I increment counter by  one。

If the if the pedestrian encounter is larger than 60。

 then I go to a yellow signal and then eventually I move to red。

 Now what this says is that you don't want to turn a signal green in the other direction if there is a pedestrian then so you don't want it to be run over。

😊，So okay， so this is what this thing does and essentially stays into the green red here。经点问。

Because there may be an error， for example， in this situation。

 you can start with the counter which is larger than 60。

Because I assume that did because I told you that that was in Asia' state I could have been another state in principle and you always put larger equilibrium just to make the sure right so in fact。

 if I start from there and there， it can never go above but there could be sometimes you put that too so because there may be a misreading of a sensor。

😊，And so it should be 60， but it's 61 right so you don't want to stay there forever right so you say as long as it' is larger than 60。

 get out of it。😊，O so when does a reaction occur， so we already say it when the count reaches a specific value then it takes a transition now the faculty takes a transition it depends on two things right one is the pedestrian is there or not and the second one is the time as e lapse to 60 or not。

😊，So they， of course， these are exogenous variables are things that are not under the control of the system itself。

 So the inputs come from somewhere else。 So the condition under which you move are given by the environment。

 Now notice that we say that very is discounter right，1，2，3，4，5 and all of that， right。

 So which means that this model is。😊，Time trigger。 So you take a transition If the counter is particular value。

 So it's time trigger。So when， for example， a pedestinrian gets in is not necessarily through it。

 I do immediately enact。😊，So I have to wait for when the counter gets upgraded。

O now if indeed you take this finite state machine， there is no counter where so it input and output。

 then the semantics of the finite state machine is intrinsically reactive。

 which means it event trigger。😊，So the transition takes place when something changes in the environment。

 the guard becomes true and you take the transition。So in fact， if you have， for example。

 a node with 22 inputs the semantic of a pure finite aid machine。

 not ty trigger says that whenever any of these guys changes its value， I take a transition。😊，Okay。

Now， if I had a synchronous implementation。All of them have to change， right？

And so that is the basic difference between event integrity， and if you like， and synchronous time。

Okay now suppose that x and y are discrete and pure signals right so this S1 the condition is not x right so when does this transition occurs？

Well， the point is that it can never occur， right， because you can take a transition when x is present。

 but the gar says now you cannot go。😊，When the Gar says you can go。

 there is nothing in the input or nothing you can do。

RightSo this one is a kind of contradictory finite aid machine in the sense that you will never move。

 So stay always stays in this one。So when the environment triggers the reaction and x is absent and this is a complete inter model。

 then the transition will never be taken because in order to to be taken， x is not to be there。

 but the reaction occurs when x is there。😊，So you don't move nothing in。O。

Now let's get back to our wonderful traffic light and then the traffic light controller we already said is a time trigger because there is a counter and the transition of taken are guarded by the value of account。

😊，Okay so this time trigger model we assume that1 to6 means one minute so every tick is one second now notice immediately that the same mathematical characteristic of this model occurs when the unit of time can be ours right in principle so there is a indsization in terms of a unit of measure takes which is also a nice feature of this abstract model that you can make them parameterized with respect the variables that you want to set。

Yeah。Yeah。咁啊即诶。あた大臣。Then if they get in， so which means that is that there is no pedestrian that is trying to cross on the other side。

Yeah， then that。现在正他。that has only town。Yeah， but there is the transition goes to yellow。

 You see that pedestrian count large means 0。Now you're right， this there is a mistake。

 should be pedestrian and count large Ri zero you go to yellow。

 so instead of end because otherwise you can never take a transition and the counter can go up so this is a mistake。

 Thank you for pointing out。So let me make sure that I'm saying that I think。And they发。

So if pedestrian is not very stable， right？Itcount large in 60s so pedestrianine is not very nothing you can do。

 so it's inconsistent。So we'll fix it。Thank you for pointing it up。Okay。

 so now I told you about this wonderful thing which are called hybrid systems。

 What are our hybrid systems， hybrid systems are models that combine。😊，A finite state machine。

 with continuous evolution。Its the combination of the。

Now in what sense is a combination of it to assume that I'm a robot right so I'm set forward right of this toy that you give to children right and the robot goes like this boom hits something and then what happens remember I mean the toy。

😊，It and goes that way。 So what happened is that when something happens。

 So when the continuous trajectory hits the wall。You change mode， right， So instead of going forward。

 you go backward， right。So what does this mean that the guard？Is determined by the evolution。

Of the mechanical system， in this particular case by Cinematic in particular。

And so there is a differential equation that is taking place and when the variable that is described by this differential equation reaches a value or a threshold。

😊，Then you jump state。You change the mode of a base， right？So that is the general model， if you like。

 of the hybrid system。 So it's a combination of a continuous evolution and a discrete evolution。😊。

Now if a robot goes like this and finds nothing in front of him， their transition is never enabled。

 right？And so which means that you're always going to stay in that state and the continuous system will continue its evolution。

Now but theain't talkingken if you are driving a car then you are remember once in a while。

 there is a signal comes up right the sensor says， all right right I stop， stop。

 stop do something but you hope that this will not happen because it's a bad signal so if the behavior is nice if you like。

 then I will continue driving my car forever so I don't need to change state So the change of state corresponds to a triggering event that makes the differential equation change its evolution radical and in fact this for example。

 boom if thats very resets its initial state。😊，And stays into that node until some boundary is hit。

Now， what that set where we stay there and we don't change。 It's called the invariance set。

 So the set where nothing changes。 So I keep the differential equation is what takes place and nothing else。

 So it's invariant with respect to the finite aid machine。 So what we use this for。

 So this is pretty。Someone had a question， no， I heard the voice okay。So all right。

 so where do hybrid system arise， Digital controller or physical plan。

 the digital controller of physical plane was the example of a robot， right。

 hit the wall when there is the digital controller which sets the motion in reverse。😊。

Trstat is one point in time we saw it already last time the model or finite aid machine model of a thermostat。

 but the temperature， we say if temperature this this that when do we。

 now if we want to model also the environment， then the temperature is a continuous variable so it evolves and so the action of the controller takes place only when temperature hits a threshold。

😊，Aircraft auto of pilot。 So that that's something with intelligent cruise control in cars。

Or a phase operation of natural phenomena like for example we see。

 I'll give you a concrete example which is actually used in designing controller for engines in cars bouncing ball so if you have a ball and you let it drop right so when it hits the ground then it changes its direction it deforms and changes its direction so that can be represented as a hybrid system a biological cell growth same thing so now you can also model what is called multiageent systems so for example if you have multiple planes right so you have multiple planes air traffic controller how does it work so you have this planes coming in and then point so it continuous differential equation and then you see that there is a collision occurring potentially so as soon as you see that the condition for a collision happens you change the control and you tell one guy to go up。

😊，And so that is a discrete change caused by control action due to a triggering event。

 which is a continuous system。Interacting robots。 So if you want to have five robots that are playing soccer。

 then they have to coordinate， right， So they have to tell each other what to do in this particular case。

 and you have the overall。Controller， a supervisory control that tells each of a robot what they need to do。

 and then we take the feedback from whatever happens on the field， and then we change the operation。

Okay， so automotive。😊，He hey， good question。 So embeddedbed systems is anything that has a sensor autor and a controller A A。

Computing platform meaning， right， So it is independent of a mathematical model that you use to represent it。

Hybrid system is whatever is a combination of two different incompatible model of computation。

So finite state machine continuous system is a hybrid system。Now。

 a hybrid system may not even have a control nor a sensor on an autor。 In fact。

 we see aanging control that goes up and down， up and down， up and down。In actually。

 the engine itself is modeled like a hybrid system with no control。

So that is not an embedded system per is a mechanical system。

And then a cyber physical system is exactly the same as hybrid system plus embedded system。

 so it's a combination of the two， except that the only difference that you see in cyber physicalical system is the fact is the conceptual view that you have multiple of this。

😊，So there is a network system。That's not。 But the other important thing is the fact that you are co designing the controller of the embedded system with the physical plant Okay so that's a real。

Most serious things。 But remember that if you remember my first class。

 I told you that same thing gets renamed。For political reasons， tonight。

 political reasons is that you want more money。 you want to put the emphasis on a particular aspect。

 you want to go on newspapers。 You want the industry to get excited about， you know。

 then you may ask， what is the difference between Internet of things and cyber physical system。

 none but yet you have 2 gazillion dollars in IoT， you have 2 gazillion dollars and CP and everybody that is a nice name。

 Internet of things sounds good。 And then now there is Internet of everything。

In which you put the human in the loop And so guys， don't laugh， this is your life right。

 it's going to be your life。 So believe me， after 40 years。

 I can guarantee you that that's going to happen all the time。 So once in a while。

 there is a real major change of paradigm。😊，But for example。If you talk about swarm systems。

 then is a different story， so it could be a swarm system could be seen what is a swarm system by the word swarm。

 it means that there are gazillion devices or gazillion things that you need to play with you need to control you need to verify you need to use so the difference between the internet of things and this warmwarm systems is a fact the internet of things in principle you could control every piece of it there is no intrinsic notion of redundancy of things like that in thiswarm like this warmwarm of bees of ends all of these other characteristic are present So in some sense swarm systems are in evolution of internet of things cyber a cyber physical system and wireless sensor network。

 all evolution warmwarm systems but it's always this continuous kind of trying to find what we can innovate to get to a new。

Market to make more money or to write more papers， same story， right different measure， same thing。

 So in academia you write more papers in industry you make more money。

 but that's you define new fields to do this kind of stuff。 Okay。

 so now this one is the representation what happens in a car seen as a global。Object。

So and this one is also called a model model in the sense that each of a node correspond to a model operation of a car。

 so a way of operate。😊，So now。You present for example， you are in a stop state。

 which means n is the number of the revolution of the engine and F is the torque that is produced by the engine。

 So if the car is。Park and it stop。 It doesn't move。 So no revolutions。

 and it doesn't generate torque because it doesn't move。Now， at the start， what do you do。

 you put the key in and you turn the key。 Now， what happens with respect a stop mode。

 there is only one thing that happens。Is that the number of revolution of engine。

Is whatever right so according to how much you push the accelerator pedal。

 but you don't start moving right away right so you're in Ile and then you have to move somewhere right to make the car go So that is the startup。

Now， then these other seven states are corresponding to the following idle。😊。

Ile't means that you are going at the minimum amount of revolutions。

In the engine that prevents the car from stopping So when you are there and you are not the gear is not engaged。

 For example， you are waiting at a traffic light。That is when you have the idol。 So there is no。

Force snow toque being transmitted to the dry train， but you don't want the engine to stop。

 And so there is a minimum number of revolution that will prevent your engine for stopping。 Now。

 most modern cars to save fuel， you actually。Turn off engine。

 And then you restart when you press accelerator plane， right。

That's another mode that is not captured here and will make the finite aid machine big。

The RPpM tracking it means that there is the guy who is controlling the car and is sitting there and he is like he has a Ferrari and he wants to start really fast when the signal becomes green so it does boom boom that's RPM tracking so your gas pedal is telling the engine to go up and down in terms of number of turns but the car doesn't move okay so it's another way of operation notice that there is a reason why you want to decompose the behavior of the car in this way because for every very region of operation there is a different controller。

😊，And so this is a way of making the problem simpler to solve。Now嗯。

I want you to think about what is the fast positive force transient？Now。

 have you ever say you are in a race with your friend at the traffic light so what you want to do is if you want to accelerate the car maximally。

 you want to get warm right so that is what is called fast positive force transit。😊。

Which means I really want to go from 0 to 100 in5 seconds。

 that is the measure of it give you for a car and say how long does it take to go from 0 kilom per hour at 100 kilo per hour they use this mode。

 so fast taste possible。😊，Acceleation now notice that this is corresponding to G dot。

Largeger amount 0 G is the movement of the gas pedal。So if the velocity right is larger。

 I mean 0 means that your gas pedal goes down right， So it goes like this。

 So your foot is pushing the gas belt。Now you have constraints。

 so the two constraints are the fact that the fuel consume must be less than a particular amount。

 so you don't go an infinite revolution per minute and the other thing that is very important is the comfort。

😊，So if you have for example， a Ferrari nobody cares about discomfort comfort。

 so if you accelerate or Tesla or met matter so when you doing in fast positive force transient you are like this which is not pleasant but some people is exciting but you can have your next snap so that is red D larger than Dmin in this particular case demin is absolutely zero right in the normal cars you don't want to be killed so。

The situation there now the fast negative force transient is when you take your pedal your foot off the pedal and so you want the car to decrease the number of revolution as fast as possible。

😊，And in fact， when you hear about the the engine， which acts as a brake。

 is when you do that operation。 So the controller will take your engine essentially to。

Try to go to 0 revolution per second， because then it taxes a。

Break and so the drive train is actually pushing the engine。

So his engine is not giving talkrque to the right terrain is the opposite。So by doing that。

 you slow down the movement of a car then speed tracking is when you have the you know。

 cruise control。😊，An idle and transmission on is when you leave， for example。

 if you have an automatic gear shift right and you're sitting at your traffic light。

 that's whatever right so you are idle but the transmission ease and in fact if you are on a I don't know if the very nicely designed cars if you're sitting on a slope journey like this and you have a red traffic light San Francisco you're sitting there then。

😊，Is kind of tricky， right， because you have to push the brake p other way to go back But this modern cars。

 if you're sitting there idle like this， it will generate after to keep you stable You don't go back。

 So you don't need to use your brake pad。 It's not an easy problem to solve。

 but that is the controller that you can put in that position。

 So this is a way of specifying the way in which the car operation can be seen And this is a specification because it will tell you what to do in each of these states。

 And you are left to design a controller。 It does exactly what is written in this nodes。

This is a hybrid system， why because the guards are related to the speed of the pedal are related to the speed of a car are related to the number of the revolution of the car。

 So it' a hybrid system。 There is a mechanical system that evolves。😊。

In triggers action from a controlled point of view。 So that is one use of hybrid system。

 Another use is actually to describe the operation of an engine and the drive line and the manifold。

 Okay so this is a diagram of what very simplified diagram of the car in which you have a manifold。

 The manifold is is the。Pippe that takes you from the valve into a engine and modulate the amount of air it gets in。

Into the car and so for example， when you price accelerator pedal， you open the throttle。

 so you increase the amount of air that gets into the car。

 and that is the basic mechanism according to which you accelerate the vi car。The engine subsystem。

 so there is an engine， the engine is the normal combusttion engine。

 you have pistons and you have fuel and you have to inject the fuel into the piston and you have to give it a spark to make it inite right so in diesel is not that way because the pressure is enough so you don't need the sparks but for gasoline you do need the spark。

Now the combination of the spa timing， the injection and the air that comes in gives you a torque that then gets given to the drive line。

 The drive line is whatever is attached to the engine right it is what makes your cargo so it is what connects to the wheels right so that's a drive light now the operation of a drive line is a purely mechanical system so it turns and they will turn and you have to overcome iner over kind of stuff is a purely mechanical system。

 The manifold is a frottle is a valve that continuously moves from a zero position to 90 degree position and that is also continuous system。

😊，So these two parts are described by originally differential equation。Now。

 how about the engine itself？So well the engine itself。

 you can moderate at a very low level of details by looking at the actual movement of the piston up and down and about what happens inside the piston so you have to model for example。

 the process theus combustion process a combustion process like an explosion so there is an explosion and gives the toque to a piston。

😊，If you want to， you can solve the explosion equations which actually are very difficult to represent and are described by a large set of partial differential equations。

😊，Now do you really care about it or is too much now what do you really care to find out well essentially what you want to know is how much torque is my engine going to deliver to a dry if you have a four cylinder car。

How many cylinders give you talk on the dry line？Did you ever think about it？2 right and y。

 because the two cylinder go up， right， then there is aign go down and the other two are actually。

Taken by the first two。 So and what do we do， They spend right， when the explosion occurs。

 and then they are pushed back by the other two。 And what do we do when they do is。

They push away the exhaust gas。 And that's what comes out of your。Back， right。

 And so there are two pistons at all times being active right and correspond to。Now。

 when this thing occur ideally。This explosion occurs when the torque is being generated is so-called the expansion phases。

 only one cycle of the four cycle， only one cycle where you get torque for every single sin out of four phases。

 just one。Now， the other ones correspond。 I mean， when do you change the phase， right。

 So you go compression。Boom， expansion， exhaust。Aspiration， compression。Explosion。

Throughhrowout the bed stuff and suck in the new gas。 So four phases。

 So that's what we know we need to know is the four phases。 Each phase is characterized by， in fact。

 that the piston reaches its topmost position。 It's called dead center。So a piton goes up。

 changes phases， goes down， change phases， goes up， change phases goes down。

 So four states for each cylinder， there are four states。

Which correspond to the fact that I'm going up and going down， I'm pushing away the bad stuff。

 I'm taking in the good stuff first aid， so I can use a finite aid machine。Now。

 what is the trigger that tells me when I need to change？The state right is the reaching of the。

Topmost position， right？Now。How can I see when I reach the topmost position， What is the。

L that I have to look at to find out when I get to the topmost position。What is the dependency。

 so what makes me go there？Well， it is。The amount of。Speed， if you like。

 the amount of motion that I get from the drive line， right， the right line is， you know。

 have you ever seen a drive line for a car is like this。

And this corresponds where the piston come in。 And in turns like this。 So actually。

 the drive line pushes the piston up and down， right， So when when you don't get the。

Stngth explosion， you get pushed by the drag line so what you need to know is you need to solve the motion of the drive line to figure out when the piston is going to reach the topmost so which means that the finite state machine is guarded。

By the evolution of a differential equation， it describes。The movement of the drive light。

 Okay so it's a hyper system。There are states， the four states。

And the condition under which you go from which state to the next is dictated by the driveline。So。

 okay， yeah。And that is also correct。 In some sense， what you see is actually a feedback。

 right a feedback loop。 So I。Control you。 and you control me。

So my position the position of dryline is due to the fact that I give you force。

But my movement is due to you，And so that is the beauty。 Otherwise wouldn't be in a hybrid system。

 right， It has to be。Altogether， right。So because it would， I mean， if it were decoupled。

 it would be nice， So the piston goes up and down and this thing does his own thing。

 but it ain't happening。 right， So they are tied together because they are。I have to say。

 on the same mechanical component。 So essentially yeah connected。

And so and this is the interesting thing it comes up。Right。

 but that is a differential equation where the input comes from the。

From the explosion the torque that I give to the right line， but also to determine yes。

 and when I determine when the thing gets the push right is by the differential equation So the finite state machine。

😊，As an input into the differential equation and the differential equation as an input into a finite machine。

😊，Because it tells when changes stay so that is in my opinion is a really nice nice thing now not because we did it like 15 years ago。

 this one of the first papers in which you actually link hybrid system to controller in cars。

And right now， most of the controllers are designed this way。 So pretty good。

 So we have a continuous system that is intake manifold。 that is a position。 Press Al is the angle。😊。

That is impacting the cylinders， the cylinders are receivinggestion auators and the ignition auators。

 they go to the crankshaft， there is a clutch which goes to a primary drive line when there is a secondary drive line and you get to the motion of the car。

 that's entire car right， let's say power train of the car。

Okay now there is something interesting that I would like to point out because we talk about the finite aid machine and the position of the mechanical system。

 but there are two other things that we need to take into consideration right？😊。

To figure out how much torque do I get， what will be the dependency， the amount of torque that I get。

 the force that I get on the piton depends on what。I know that there are some Mkey here。

 so you should know。Think about。So when you push by accelerator pedal， the car goes faster。

 so which means there is more darkrque。And what happens when you push the asciator pedal， the angle。

 the intake manifold， changes its pressure。So， which means that。Exactly right。

 so what happens is that what the dependency on the amount of torque is on the mix that comes into the ceiling。

So there is a rich mix， means its a lot of gas in there。

 And so what happens when you give a spark boom， it gets a lot of force right。😊。

And so the speed increases， so you absorb more stuff， and so you go faster and faster and faster。

 and so that is exactly right。Okay。Now， there is another variable。

 so we know now that it depends on how much fuel gets intovene。イントベピストン。There is another variable。

Which is。Yes。Well， yes， but that is given， right， right， timing。 So you are making。 No。

 you like ours。 Yes， O， so is is the time of ignition。 right， So why is that because。😊，そい政府。你还干保。第保。

可到。Exact so what happens is that in the old times you couldn't do well right in the old times it was all deterministic was mechanic so you couldn't get what is called sparkk at dance so you cannot control the time of ignition right。

😊，So the time of ignition is a controlling variable。

 so suppose that you are in the situation where you took your foot off the pedal because you want to stop the car or you want to decrease the speed of the car。

😊，Remember the decision how much gas is going to go into the piston because of the four phases has been taken long ago two phases before and so now you have all these gas and you don't want to create too much force because you are accelerating and you dont want to accelerate so how do you do the trick you say aha this guy goes up？

😊，I don't give a spark。 I wait this coming down because the other guys are pulling it down。

 and I give the spark when I'm halfway through。 So the push that I get is much smaller。

 right because we。😊，Chahamber， where I'm going to take this pension， is already expanded。

So that's the trick。 And what is called。Spark delay right now。Can I do also the opposite。

 Can I also put this spark。Before I reach the top mo。And why should I do well？ The answer is yes。

 of course。 But why should I do it。Now， why am I telling you this。

 Because I want you to think what goes into the process of modeling a problem。

 an engineering problem into a mathematical model okay in the most abstract sense because believe me no one in the world was using finite state machines to represent the behavior of the engine while if you think along these lines that we are thinking now is the process that allows you to build the finite state machine that represents faithfully the engine for your purposes。

 which is controlling the motion of the So why do you want to to。

Put the spark before you reach the topmost。Any idea。Now。

 that was the delay that we already discussed。If you you before you actually。

 so what happens is that you get， well， you start the combusttion process before you hit this point。

 so what could it have？喂喂。Right for example， one okay we'll get to it this is a side effect which is a negative side effect if you do it too much and this is called knocking have you ever heard your engine I mean the old engine when cling clling clingling that's bad right and so essentially is when you are in third gear and you're going one kilometer per hour when you clk cl clk clk and the thing is that the gas is actually auto combusting right so the spark it doesn't do anything and so you get this spark in the wrong moment and you destroy your engine okay not good。

😊，But it could be positive and why， because。As any dynamical system。

 right any dynamical system there is delays， right So there are things that occurs that need time to develop right。

😊，So the combusttion process is a physical process。😊，It does take time to ignite。

 I mean time we are talking about in the order of milliseconds， but it does take time。

So if I give this spark just at the right moment， I actually maximize。😊。

Because I start the combustion process already so when I am the top most I actually get the maximum expansion in the shortest possible time because I already started generating this nonlinear phenomenon which is the ignition so remember I told you we had four states now with the spark advance。

😊，Can I use four states or I need to be。More clever， I need to put more stuff in it。

Because now there is another variable that you may need to represent， which is the advanced， right？😊。

Positive or negative。 So it's another01 variable that I need to put in。

 And so a number of states has to go up。 And so let's see how it can be done。

 So this is a cylinder that are sitting there with the quantity of gasoline comes in with spark。

Hello， okay， seen， compression， expansion， exhaust。

Thinkh we already discussed it this is a mathematical model now and that finite state machine that you see there is the spark and the amount of and the movement of the drive line that takes you to the various position and then the output is the of what the torque will look like now here it is that's the finite state machine。

😊，No more for states， but if you look at it， there are six states。

And the six states correspond to the fact if I anticipate the spa or I delay the spa。😊，Okay。

 now you could do a continuum between delay and spark， but nobody does it too complicated。

 So there are only two states， either anticipate or delay end or start。 right。

 And so that's the reason why six states are good enough。So the H up there is exhaust phase。

 then if you reach a desktop center。You move from H to I， which is the intake。

The intake after you reach the next debt center goes to BS right BS is not bullhiing but is actually the phase in which you are ready to take the decision of igniting not igniting what to ignite and so on。

 so if the spark comes in you go B toS and spark advance。

 which is PA if you get this one is negative advance，And if exactly if you don't take no advance。

 no delay， you go directly。To the explosion phase so these two different paths corresponds to the decision。

 three paths from one state to the next depend on the decision that you are taking for the advance in the spark or delay of the spark。

 so this one will be the path unfortunately red doesn't read very well but what is written there。

 it says that this occurs course the spark occurs in anticipation then you go to the state PA。

 when you move to the expansion phase which is the one which is characterized by ASS。Now。

 if indeed you delay spark， you take whisper。So according to the fact that you take this spark early or later。

 you do a different path in the finite state machine。

 the composition of all of this is a hybrid model for range。Now， this one is accurate。

 this one is as accurate as you can get。😊，With small， yet。

We don't look at the explosion of the mix in the pistons。

 We don't look at the dynamic movement of a piston。 We don't describe that movement is no use， right。

 We can abstract it way。We cannot abstract away the behavior of the drive line because that dictates where the distance are going to be。

 so I cannot move them out。 So this one is a process that you follow。

To have a complicated physical phenomenon and try to find what matters。They throw away。They。

Unnecessary details。And yet be accurate enough that you can take good decisions on the control action。

 which is when you give a back。Now you know what before what people did before using this finite aid machine model。

 they use average values for everything so instead of taking up down。

 up down we took the average to decide what control action to take and of course you had knocking。

 you had all kind of bad stuff。So the fact that you introduce a finite state machine is increasing complexity a little bit。

 but it gives you so much more。😊，诶。And of course， nobody was trying to solve all the equations with partial differential equation or the energy differential equation all the kind of stuff no one is ever tried。

So this is a again， what I would like you guys to come out from an embedded system design class is the thinking process that goes into designing these things。

That is the modeling process and the modeling process implies that you have to find mathematical expressions for the physical phenomenon that you are trying to master。

😊，You must use a mathematical model for reactions that you are going to take on the system。

 and then you have to analyze the mathematical model。😊，And then finally， you move to implementation。

 If you have done things right， if you have used ver tools and all of that， you can even。😊。

Do all the integrated details of implementation automatically by generating the actual code that goes into a controller。

😊，Now anticipation by the weekend your TS will generate together with me。

 we have spent all this morning the decision on how the project is going to look like and this is it。

 so I want you to apply this particular process to an application of your choice。😊。

But I also want you to think about the general methodology about designing embedded system。

 so we are going to give you a given platform， so its something that you cannot get away from。

 you have to use pieces out of a library。So you will have available sensors with their characterization。

 You are going to have available a。Computing platform， which will be Arduino boards。

 or I always remember in。I later came。And these are the computing parts of the platform。

 and then you are going to have a set of actuators。This is what's given to you。

 So it's like a Lego box。Now build your own building。Okay。

 so find me an application using this set of stuff。

And the best application will get a nice price bottle of Italian wine。 Yeah， together with a plus。

 right okay。😊，So people don't drink wine， we'll discuss and a bottle of Coke may not so great。😊。

So I volunteer the price for thewin， not for Rico。LastSo I want you to think about the application。

 how you model the application， how you choose the components。

 how you map the mathematical thinking onto the platform and I want you to verify and what you do is actually correct before you do it。

😊，And so we'll ask you to use either simullink or lab view。 Both of these things will generate code。

 They are capable of generating code， So they are capable of。

Not to say making your platform do what you want without doing the low level coding。

 but if you want to do the low level coding， be my guest。

 you will see that it's more much more likely that you aret going to make mistakes。

 but it's also more likely that you are going to find a better implementations trade off right。O。Now。

 so coming back， among all the possible hybrid system where there is this differential equation that govern the mechanical part of the system or thelateical part of the system。

 for example， there is another application where this hybrid behavior shows up in spades and is the power distribution system in airplane。

😊，You know， airplanes are a little electrical power plane。

 right so how do you get electricity in the plane to make the movies go and all of that？Any idea？

With yes。Yes， as an engine is a secondary drive line， right。

 So the equivalent of a secondary drive line that we see in cars is the same thing。 So there are。

Trbines， right， they generate electricity， So these electricity are motors， know。

 And so they get delivered to motors。 So they are generators and have to deliver electricity to them。

 Now， what are the secondary loads。 Yes， movies and all that， but also。😊。

What else do you get with electricity in your plate？Well。

 if you look at the brothers right to make the plane go up or down， there had the pedals。

 so the people were pushing on the pedal and flap will come up。

 And so do you think it's the same way now。No， right。

And so how do you when you land you see this thing coming up and making a lot of noise and then if you look underneath it underneath it。

 you see a lot of hydraulic crap in there， so who activates this stuff right？Engines， right。

 electric motors。Let the flip is thing up and down， right？

So you have to have a generators deliver this thing to。 So if by any chance the generator breaks。

 what happen。Yeah boom， right， And it's not that you don't see your movies。

 You go down because you can't do any anything to the plane。 There is no mechanical system。

 There is all the letter。So what do you have to think about， You have to give redundancy， right。

 So you've got to have at least two。Motors， right， to generators in the plane。But now。

 so you have the right generator and the left generator。 and you have buses that take the power。

To the appropriate part of your system。 Now， suppose， I mean。

 it may very well happen with one the of the generator blows up， right， very possible。

So what happens， Oh my God。 And right after the plane goes down no。

What happens is that the buses can be crossed。So this poor generator with had to do only the left part gets to do the right part as well。

😊，Now， what happens when you have a generator a test to deal with too many loads？

Bad right so no good because boom again， right So think about it。

 What can you do So the thing is that you want to keep the thing going right。

 who cares about the movies right So what you do is that you shut down the things that are not as important is the fundamental thing so you keep bad going right。

Now this isn't that a controller， Is that a set of discrete action， What are the discrete action。

 This guy is blown up。 I need to bridge the buses。 What is the discrete variable， right。

 So it actually is called a contactor。It's a huge switch， right， There's a catch on， right。

 It does's like serious speaking。 It's that catchup， horrible noise。So they boom。

And then you have to take out the loads， right， and what do you need to do to take out the loads。

Blip your bin。Other contactors right so you close this you open there so that is a hybrid system right so this is a discrete there is a number of states。

 this is down， this is up can2 to the n of this switches up and down and this is the number of states。

And use which from one state to an x is something happens。 right Okay， so let's say。

 So this particular modeling strategy is very， very effective。😊，Now， unfortunately。

If you want to demonstrate something， if you want to say， okay， under all possible circumstances。

 my design is correct。Can do it。Why， because with no more a finite state system。

 it's an infinite state system and a combination of raina differential equations。

Fized aid machine is a pest of a pest of a pest of a pest of a problem， so not so good to verify。

 you can simulate， you can simulate so you can see how it goes。

 but to demonstrate that you're never going to have a problem is a very serious point。

So which means that the model is nice， you can do a lot of things， but you have to use it carefully。

😊，So。Among all the possible hybrid system， there is one which is absolutely simple。😊。

And is actually in between in complexity。 You don't have to say， I don't know what happens。

 You can say what happens。 It's very complicated， but you can say what happens。

 And these are called timed automata。Now time and demata are the only differential equation that goes on is the advancement of time。

 so instead of having a discrete counter you have t dot equal to 1 t dot equal to1 is simply is a straight line right and is the passing of time。

 lets say。😊，Well， you look at it and say， okay， if I look from a theoretical point of view。

 where it' iss not much different， it's still a differential equation。

So this problem may be undecidable， wrong。 It is decidable， and actually there is a transformation。

 It takes this timed automata into normal automata。 It has a gaziion state， but feel finite。

 So that's a nice thing。 That's the reason why I say this in between。

 And so in this particular case is a continuous variable。

 The inputs are click single double which is the click of the mouse。😊。

And so when you want to move the cursor you say mouse up， mouse down。

 so this is the finite state machine that is describing this and there is x dot t equal to 1 is essentially in fact that various time goes by so this simple form of hybrid system is called a time autometerta where dynamic is just passing of time。

Big deal。But from a opposite theoretical point of view。

 the two guys who discovered this tiny automata。 One was a professor at Anzinger。

And another one was a Rajival Lure from University of Pennsylvania， made a fortune。Academic fortune。

 not$1 Gaziion dollars alone， you know。Bill Gates， but we made a fortune in the sense that this was a very nice theoretical result to show that this differential equation are easily handled with this system。

 this cyber system。😊，So how many states does this automaton have。

 this is the greater result of Han lure and deal， actually this guy from Stanford so this Vi results actually says that there is an equivalent。

😊，Final state system that describe the stuff。Now， if you want to challenge yourself， try。

Actually the idea was very simple but the old point is like the komus egg right once you want to make the eggs stand up。

 you just cr put it there oh stands up right so there is a very simple trick that these guys did and they could make that through。

😊，So now this one is hybrid automata of a traffic light controller where you have x dot t equal to 1 which simply says that time is passing。

 you will limit the counter and you put x dot t equal to1， it doesn't change anything essentially。

 but that is the same representation as before now though is done with a time auto。

So there is a timer， for example， but you can use this thing。 How many。

 how would you model a timer which generates a T is time T time unit eapses。

That you can do it with a hybrid system。 You have x dot t equal to1。

 So it goes like this when it hits a threshold k on resets。And does it take。 So the actual movement。

In dynamic space， it goes like this to， to， to， to， and they。

A change of state corresponds to a discontinuity in the of a differential equation。

 because when you go here， it's a reset， you go here， starts again， take with that。Tak goes down。

 okay。So that is essentially what it is。 So you have a self loop， you have S large than equal T。

 you have to tick。 Otherwise you said S T equal to0。 Okay， let's say。Very simple。

So a similar time in auto can model a generator of a timer interact。

 So you have seen the interact mechanism in in your labs and you can generate， I mean。

 you can have a generator of interrupts using this。Mechans of counting time。Now。

 this one is the other example in which you can use。Hybrid automaton。

 what you see there is a bouncing ball， and the change of state is when it hits the ground。

And changes direction。 So you can say ordinary differential equation moves down。

 Kaachung change state。 Or differential equation goes up this way。

Then it reaches with that center goes down， So at this point changes again。

 changes state and going down。 So the states are。Going down， going up。

 and there are two points I hit the ground。And I hit the top must okay so it's it。

 so it's the same thing as we saw before except that this is again。

 given that the mass is always the same， there is no input and so on and so forth。

 this can be modern as a time autoomic。So what you will look like， you see the tin time， T time。

 T time， which is the velocity， the speed as this discontinuity， which corresponds to the two。

Topmost position of the ball。 And when it hits the ground。

So notice that if you want to plot the trajectories of the hybrid system。

 every time you change state， you have to discontinu it。

You may have a discontinuity in the variable of themselves or in their derivatives。

 but there is always a discontinuity because it's discrete change of mode。Okay。So and again。

 this when do reaction occur in hybrid automaton is when the ordinary differential equation hit the boundary and then you change my mod of operation。

So call continually with a continuous state variable being continually updated when it reaches a particular threshold。

 you change condition。So now suppose x and Y are discrete and pure signal when does this transition occur at this point since you have the advancement of time embedded in the model。

 then you can say that the earliest time T， when x is absent after entering S1。

 this will be the same time S1 is entered， you can as an exercise decide y is the case。

 if x is absent， when s1 is entered， then the transition is taken at that time。

 if x is present when s1 is entered， then it will be absent the time infinite it is similar large。

 and so introducing the notion of time， you can make thatting contradiction that when we had everything discrete go away。

If you want to right because this is more physical phenomena by introducing these delays。

 especially what you are doing is that you are introducing the concept of the delay okay that's it。

 so I'll see you next week。

![](img/3c4ce1d60d242a4f6c7484df07cb98c9_1.png)

![](img/3c4ce1d60d242a4f6c7484df07cb98c9_2.png)