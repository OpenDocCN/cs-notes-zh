# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P2：-02-Lecture 02 - Sensors and Actuators.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

It's time。Can you guys in the back of the room hear me， okay？Thank you。I tend to talk loud enough。

 so I'm not going to actually I'm not even sure is the amplification working？Oh， all right。嗯。

So I'm Edward Lee， I'm sorry I wasn't here on the first day of class， and my colleague Alberto。

 I'm sure gave you a great introduction to the class。I was。

Deliverring my daughter to as a freshman in college， so where you guys were just a few years ago。

 so I have a new found empathy for。Your situation。So a few announcements， one， very important。

You must be enrolled in a lab for this course， the lab is a very important part of it。

 the way the lab is structured is that the first six weeks are fairly structured with well defined assignments。

 with well defined goals。The rest of the semester。A little more chaotic， okay。

 you have a lot more freedom and you'll be doing projects in teams of three or four people or two is also possible。

 but nothing outside those ranges， don't even ask， okay？嗯。If you're not already enrolled in a lab。

 our main limitation for enrollment in this class is our lab capacity， that is the key limitation。

 you've got to be enrolled in a lab， if you're not already enrolled in one。

 you should see John at the end of the class today， the lab start today this afternoon。

 if you miss the first lab it's going to be hard to catch up。So yes， question。

the Monday lab will start on Monday， next Monday。RightSo because of the holiday。

The week is shifted by one day。嗯。I should have said what and you didn't go yesterday。嗯。YouSee。

 this is my newfound empathy。So I apologize， I have listed office hours for this afternoon。

 but my younger daughter， who is not in college broke her kneecap。And。

I've got to take her to the doctor this afternoon， and so I've scheduled an extra office hour on Thursday to make up for that three to four and my office hours will be available as normal tomorrow。

嗯。For I've seen a couple of questions about the textbook， so you should read the instructions， okay。

 we're using Edition 1。5， I'll let you in on a little secret。 Edition 1。

5 is because we didn't meet our deadline to complete edition2。And so this is a temporary edition。

Just for you guys， okay it'。Widely advertised or anything， it is openly available。

You can download a free PDF。You can buy a hard copy of Ed 1。

5 I know that some of you have bought hard copies of edition1 and there's only one chapter that's different。

 the sensors and actuaators chapter， which is actually the main topic today。So。

Your hard copy is still good， except that from chapter 7 on， the chapter numbers are shifted。

But please don't use an edition one。Book to decide which homework problems to do。

The homework problem numbers are referencing Ed 1。5 and there's a whole bunch of new homework problems。

 the numbering of the homework problems is completely different。Use Ed 1。

5 to determine which homework problems to solve or you're going to solve the wrong problems， okay？

but the hard copy is still good for the text in all but one chapter for the first edition。

 so if you have a hard copy， keep it， it's worth it。All right， any questions？Okay。

 I want to encourage you to keep tabs on this web page yeah。Yeah。

It'll be taken care of if you're in a section and there's room for you in that section we'll get to you in on t bears eventually。

 the tele bear system seems to be kind of clumsy。All right。Today's topic。😊，Is one of my favorites。

 sensors and auators。And。So。嗯。There's a。Some homework assignments about this。

 and one thing that I'd like to emphasize to you is that if you don't like to read。

 you're going to have trouble with the homework because I'm not going to lay out everything in lecture that's in the book。

 in fact you're going to be expected， especially things that are a little bit more mathematical。

 I think you know it's better to sit in a comfortable chair and puzzle over them。

you know then it is to try to stay awake while I run through a bunch of calculus for you or something right so I'm going to try to give you the sense of the math but to really need to read the text to you know get the real substance of it okay？

嗯。So。Sensors and auators are about connecting the computational world with the physical world。呃。

What Alberto called on Thursday cyber physicalical Systems， which is a relatively new term， okay？

Is about systems that combine some kind of physical dynamics with some kind of computational system。

There's a huge variety of sensors and auators here。

 but there's been an explosion in recent years of capabilities and also an explosion of our ability to make use of them of these sensing capabilities in computational systems。

No。I'd like to start out today's lecture with a challenge problem。

 and this is a challenge problem for you guys， you're going to be hitting the world of practicing engineers or researchers or scientists very soon。

 if you aren't already there。And you are going to solve this problem。ok。In fact。

 I'd be willing to bet several of you in the room will be working on the technology that will prevent this kind of thing。

From ever happening again。If you look back at a video like this in a few years。

We're all going to be scratching our heads and saying。Wow。😮。

They actually allowed vehicles on the road that would do that。And you're going to say。Wow。😮。

There were machines out there。That we're using humans as sensors。That's what that truck was doing。

It was a machine using a human as its。Sensing device to see what's going on around it。

That's going to change。ok。Humans are pretty good sensors。But engineers can build better sensors。

And we're well on our way to doing that。 Okay， And if you can integrate those sensors with the machines。

And develop the control systems， you can actually prevent this kind of thing from happening。

So this is happening as we speak。So cars are getting。A huge variety of different sensors on them。

They have been for some time。The Model T Ford had a temperature sensor。Now there， you know。

 the feedback control system was a dial on the dashboard， if it had exceeded a threshold。

 a human was expected to turn off the car because otherwise the engine would be damaged。Right？嗯。

You still needed humans， in that case， the human was the actuator。ok。

To react to what the sensor was detecting。But we're going to see the humans play a diminishing role。

 And if you think this is such a brand new thing， this video。It was from a demonstration project。

A demonstration of a project and it was filmed in 1999， okay， that's 15 years ago。

 how old were you guys in？Okay。Not many of you were kind of young， right？

So self driving cars were not invented by Google。But the technology has improved tremendously when the Pa project developed this demonstration effort。

 first of all， they were using cars that were not drive by wire cars。

So the steering was controlled by mechanical actuators。

So they had to retrofit this steering with comb gears。

 they had a bunch of mechanical engineers that would。Retrofit this。

 that's the trunk full of computing equipment。 it's pretty much filled up the whole trunk。

And they had to retrofit it with the auators that would control the car。

 but they were able to demonstrate driverless platooning on San Diego highways in 1999， okay。

That particular technology that they developed in that project has actually been deployed。Since。

2005 in this context。Okay， it's used to drive snow plows in this sierra。

 How many of you have driven over Route 80 in the winter in a snowstorm？if you haven't done it。

 I recommend it。It's pretty exciting。U。You can get absolute white out conditions。

 and these snow plows have been outfitted with a system。That will steer them to quite high precision。

It's a little difficult to see it here， but this snowplow is three to four inches away from the guardrail。

ok。And you can't even see the guardrail。No idea where it is。Right。So let me ask you this。

What are the sensors that are being used to control this snowp？Let's hear some suggestions。Yes。Sorry。

Passive IR。嗯。No。Because。Remember you can get white out conditions。

It'll pretty much block any infrared signal。PPS。No， can't get three to four inches of precision。What？

Xray， oh， that would be an interesting one。啊。嗯。Yeah。

 to be able to see through the whiteout conditions。Maybe。But remember that what would you be seeing。

 you'd probably be looking for the guardrail， but guardrails are imperfect， they have gaps。

 they have densets， where do you think the dents come from？

Drivers driving over the sierras in a snowstorm。So yeah。

 actually seeing the guardrail isn't going to help all that much。Ultrasound。嗯。I don' you know。

 I'm not sure， but I doubt that ultrasound progress propagates too well through snow。In fact。

 have you ever noticed in a snowstorm how things get very quiet。

 I think snow is a really good sound absorber。Inductive proximity sensing。

 that would be an interesting one。 but again， that would rely on the。

The guardra being undted and continuous。Something that touches the guardrail。No。

 that would be foiled by ice， probably。Other ideas。Yes。Radio beacons， yeah， you could do that。

 you could make your own little localization system and put radio beacons。

 It would be an expensive solution though。Because you have to power the radio beacons。Right。

 which means。Doing a lot of wiring onto miles and miles of road。What's your name？Alex， you nailed it。

That's what they did。They just。Drilled a hole in the road。Every 10 feet or so， dropped the magnet in。

10 feet， why 10 feet well。嗯。In theory， you've all taken Es20。

 you've looked at the aliasing phenomenon。Roads in the Sierras are sinusoids。

To a first approximation。And if you sample with a sampling period of 10 feet。

Given that roads don't- they're not really high frequency sinusoids because cars don't deal with high frequency sinusoids very well。

 right？So every 10 feet is a reasonable period for sampling。And that's what they did so they had。

Equipped these snow plows。And I'll。Start up this video until yeah。

 so this is a bar that they put under the under the。Snowplow that has a bunch of magnetoomes in it。

And then they have a control system that just tries to keep the magnet in the middle of the snowplow。

Okay， and you can get the three to four inches of precision that you need to get close to the guardrail with that。

So one of the。Part of the art of working with cyber physical systems。

Is figuring out what the best sensing and actuation mechanisms are that are available to you。Okay。

 sometimes incredibly simple sensors will work really， really well。

And sometimes you need something much more elaborate。

 GPS is actually would be an extremely elaborate solution for this。

 and it would require precisions that would also require adding to the GPS radio beacconons。

 so you can get three to four inches of precision with GPS。



![](img/1f6f2ec7a64362bc97a34ded60791f3d_1.png)

If you add local beacons， okay？嗯。And that might be a reasonable solution today。

 it might even be cost effective to do that today because of the ubiquity of GPS。Right。

The solution that they picked here was relatively simple。

 it did require some modification of the infrastructure to embed those magnets。

 but the magnets don't require any maintenance。So infrastructure that doesn't require maintenance is generally better than infrastructure that does。

How do magnetoometers work？They use an effect that's been known about since。1879。

 when Edwin Hall discovered it， so it's called the Hall Eff。

Which is simply that if you run a current through a conductor， that's a plate。

That's sitting in a magnetic field。The electrons get deflected by that magnetic field。

 they tend to prefer to go along one side of the plate。

And you can measure a voltage from top to bottom on that plate。 It's a very simple effect。

 the infrastructure required to。You could implement a hall effect magnetometer yourself quite easily。

Just。You know hook up an A toD converter through one of these plates and you could measure electric fields。

Now， in the lab， we're going to use accelerometers。

And accelerometers are a really interesting sensor actually。Have been。

Used rather extensively in cars for quite a few years now。Approximately 15 years。In particular。

 the first widespread deployment of accelerometers was in airbag systems。Okay。

These accelerometers are responsible for deploying an airbag if you have a crash now how does an accelerometer work Well。

 a simplified view of an accelerometer is shown here。You've got。A fixed frame。

This is attached to the thing whose acceleration you want to measure， so you bolt it to the car。

And then you have a floating plate attached by a spring。

and so now you can see if I shove this thing up。The plate will get closer to the fixed frame because the spring will compress。

If I yank it down。The spring will elongate， so the plate will get further away from the fixed train。

So if I can measure the distance between the fixed frame and the plate。

 I can measure the acceleration， right？How would I measure the distance between the fixed frame and the plate？

Yes。Yeah， measure the capacitance， right？So if you've taken E 40。

 you hopefully understand more or less how that works， okay， you measure capacitance。Now。

 there is a challenge here， which is that you're not just measuring acceleration。

Look what happens when you rotate this thing。In a gravitational field。When it's standing straight up。

The floating plate is being pulled down by gravity。And it's standing straight up the other way。

 the floating plane is being pushed down by gravity onto the spring。

And when it's in the horizontal position， the floating plank， the spring is presumably neutral。Okay。

So the distance measurement depends not just on acceleration。

 but also on orientation within the gravitational field。In fact。

 there's no way really to tell the difference between。A gravitational field and an acceleration。Okay。

 there's no way to measure that difference。嗯。You knowIf you're in a free falling elevator。

It feels like you're not in a gravitational field， you're just floating you're weightless right and in fact。

 it's exactly the same phenomenon and there's no way for you to tell whether you're actually in a free falling elevator or。

In outside of any gravitational field， there's no way to tell the difference。

So accelerometers are in fact very good for measuring orientation。

Now I'm going to try something here which doesn't always work because it always works in my office。

 but as soon as I get into a room with approximately 100 Bluetooth devices。

Then the Bluetooth connection doesn't always work。

![](img/1f6f2ec7a64362bc97a34ded60791f3d_3.png)

Nevertheless， I am going to attempt。To connect to this。Remote。Sorry。No。

It has to's attempting to pair。Yeah， as I said。Can you all shut off your Bluetooth devices， please？

Oh there we go， we got it。Got it。Here we go。All right， so this particular accelerometer。Is， in fact。

 the one that you're going to use in the lab as an accelerometer because it comes in a very convenient form factor。

And it comes with this little Bluetooth connection。

 so it makes it relatively easy to hook it up to stuff when the Bluetooth works。

 and it's a three axis accelerometer。And you can see it measures acceleration。Okay。嗯。

You can also see。That it measures orientation。ok。And you can also see。Actually。

 let me set this up because I would like to be able to capture。嗯。Capture what happens here。

If I drop it。It I didn't like it。It will。Ever so briefly。呃。Ever so briefly。

 that wasn't a very good specimen。Let's try this again。See if it'll pair again。Come on， guy。

Paired up。I think I had too much tumble in that drop。Yeah doesn't want to pair again， all right。

 well you're going to have to take my word for it。That。Ever so briefly。

When you you put an accelerometer into a free fall。All three axes。

 which are actually three independent accelerometers， will all measure zero。Okay。This is。Actually。

 routinely deployed as part of disk drives these days。

 So if you have an older laptop that doesn't use a flash drive and uses a disk drive instead。

It'll have a three axis accelerometer in it， and if you drop your laptop。

 it will retract the disc head before your laptop hits the floor。Okay。

 and it prevents a head crash which prevents data loss， your disk drive may get smashed。

 but the disk itself is protected， so your data is protected。So that's how that mechanism is done。

Give this guy one more chance。Com on。I won't pair， yeah， I mean。

 you're going to have this problem in the lab too， by the way。

When you get enough Bluetooth devices in a room。The protocol doesn't really work very well and yeah。

Or really is I looking in the wrong place？Okay， I didn't capture the graph。Yeah。Okay， all right。

 well， you you can experiment with that in the lab if you do。

 please put one of these little plastic sheaths around the。Around the we。hm。All right。



![](img/1f6f2ec7a64362bc97a34ded60791f3d_5.png)

Okay， so orientation versus acceleration can't really tell the difference。嗯。

Here's a model of the accelerometer。 Now， one of the things that you're going to notice when you read the chapter on sensors and auators is that we put a lot of emphasis on the models for these things。

And there's a very good reason for that， and it's kind of consistent with the general theme of this course。

 right。嗯。You can work in this field as just a hacker where you just try stuff until you get it to work。

ok。But then you're not going to be the engineer designing those self drivingriv cars。Okay。

 nobody's going to let you deploy safety critical systems if you're just a hacker。Right。

In safety critical systems， it's really important that you understand。The components。

And the way they interact in your system。In order to promote that kind of understanding。

 we put a heavy emphasis on the modeling side in this course and on the analysis side。ok。

So how do you model an accelerometer？F equals MA。Anybody remember that？Newton's second law right。

 so this will also give you a sense of， you know， some of you have asked me questions like， well。

 how much math do I need to have under my belt to take this course？

And the answer is really that there's two branches of math that we rely on in this course。

 and one is for the cyber side and the other is for the physical side。

 and it turns out they're really quite different those two branches of mathematics。On the cyber side。

 it's logic。And in our experience， most of the people who are undergraduates here in engineering。

Have a woefully inadequate exposure to logic， and so we kind of give that to you in a more self contained way。

For the cyber side， you've all taken physics。You've probably taken Es 40 and 20。嗯。

You've got the mathematics under your belt for doing what we want to do。

And the kind of thing we want to do is understand how f equals MA makes an accelerometer react to combinations of gravity and acceleration so for example。

Suppose that I want to use this remote。As a way of measuring。Where I am。ok。

So I start at a known point。Right here。And then I want to measure。

Measure the acceleration in order to determine where I am a few minutes later。

How well do you think that's going to work？Anyone want to comment on that？Yes， right in the back。

Yeah， so that's one is that get you could get a significant amount of drift is the term and we'll look at how the model tells us about this in a second。

 yeah another。You need to know your original velocity and the accelerometer doesn't tell you anything about that。

 it tells you only about changes in velocity and any error in your original velocity is going to compound in your estimate of where you are。

 that's so two good problems there's a third one which is even nastier。Anyone want to yeah。

That's a good question， so sensitivity is a big issue and it isn't in fact， okay， in fact。

 usually accelerometers like this for this kind of application are tuned to measure accelerations on the scale of one to five gravitational forces。

 okay？So and that's because of their gaming， their use in gaming， so this is the weote。

 which is used with the Nintendo Wi and the most important piece of information that the accelerometer gives to the gaming gonzel is actually orientation。

So you can aim at something， for example。The motion measurement is actually used much more crudely。

 orientation is the main use， and in fact， for detecting motion。

 the weote uses a much more precise motion detector， which is an infrared camera。Okay。

 this little window here is an infrared camera。And the Nintendo Wi comes with a little bar that you put either underneath your TV or above your TV that has a pair of infrared LEDs。

ok。So。The camera can tell where the screen is。As you move it around。Okay， and。

ThatThat gives you a much more precise measurement of motion because you can see that motion in the movement of the LEDs in the camera。

 field of view。嗯。So that's one， there's another。What if I start moving and at the same time start tilting？

What is the acceleration that I'm seeing in that axis？It's mostly gravity。

I can't tell the difference between moving in this direction and tilting。

Versus moving in this direction with a much more aggressive acceleration。

 there is no way to tell the difference。And you're going to get a very different measurement of position。

If you assume that it's rotating。Okay， you might estimate the position is here。

 but if you don't know that it's rotating， you're going to estimate the position is way over there。

Huge errors that you get。This technique， by the way， of measuring changes in motion。

 is called dead reckoning。Okay， and originally dead was spelled DED， not DEAD。

 but it's gotten widely misspelled and so people usually spell it DEAD these days。But。

DED comes from deduced。And it's an old navigation term from sailing days， right？

You measure how fast you're going through the water。

You use your compass to measure what direction you're going in， you know where you started。

 you started in Liverpool。Okay， and you have a clock。

And you can figure out approximately where you are from those pieces of information， okay。

 so that's deduced reckoning。All right， so with the accelerometer。

 you can model the accelerometer using f equals MA， so if x is the position。

 then the second derivative of x is the acceleration。Mass timess acceleration is equal to the forces。

And。If you have a spring mass system， you have a force due to spring extension。

 a force due to viscous damping that is proportional to the speed at which it's moving， okay？

And then you should also add to this the gravitational force， okay， but in this case。

 this simplified model is assuming that the accelerometer is laying on a horizontal surface。

 so the gravitational force is having no effect in this case。

 the component of gravitational force is zero。To take into account the component of gravitational force。

 you need to do a little trigonometry。Because what you're interested in is the component of the gravitational force that is in the direction of the axis of rotation of the accelerometer。

Okay， and this is the reason that you have to take into account the orientation if you're using an accelerometer to actually measure acceleration。

If you fail to take into account the orientation， you're going to get numbers that are incredibly far off。

So the comment from the back， the very first one， what's your name？Colin。Colllin。嗯。

About drift you can also get from this model， right， this is a very very for basic physics。

 right position is your initial position plus the integral of your velocity。ok。Your velocity。Your。

Velocity is your initial velocity plus the integral of the acceleration。Okay。

If your measurement of acceleration is a little bit off。How fast does the error grow？

In your measurement of position， say your measurement of acceleration is always biased to be a little bit positive。

And how fast does the error in your position estimate grow？对呀。It grows quadraically with time。

so that means after a certain amount of time， you've got a pretty useless measurement of position。嗯。

Dynamic range， was it you that brought up the dynamic range question， what's your name？Bally。嗯。

Mark Lemkin got his PhD here under Bernard Boser。In 1997。And I credit him with probably。

Saving more lives than anyone I know。Because it was his invention that made airbags。

Effectively deployable。He developed this technique that enabled accelerometers to be implemented very。

 very cheaply using silicon processes that were already widely deployed for semiconductor manufacturing。

And here is a photograph。Of one of the chips that he built in the microlab。

 which was at the time on the fourth floor of Corey Hall。Now it's been。

Completely redone and is now in Suutarcha Di Hall， but this one was implemented in Corrry Hall and it's a very clever design。

 so the springs。In this case， and the floating masses are just floating silicon fingers。So picture。

 he etched in a bunch of silicon valleys。So ridges and valleys。And then inside of the valleys。

 suspended a silicon finger that could swing from side to side。Okay。

 so you could then measure the distance between the fixed。The fixed ridge and the swinging finger。

Okay， in response to acceleration。But if you did that naively。

A small acceleration would cause a collision。Or。If you made the floating finger really stiff。

 then you would have a device that's not very sensitive。

 it would only measure very large accelerations， so the dynamic range of that wouldn't be very good。

So what Mark figured out how to do was。Well， instead of just letting the thing swing and measure the capacitance。

Turn it into a cyber physical system。And apply some feedback。

So when your capacitance tells you that the arm is swinging this way and coming close to the ridge。

Then apply a voltage that will apply a countervailing electrostatic force that will push the finger away。

so if you watch these things in action， even under heavy accelerations。

 the fingers are barely moving。Because what's actually happening is that the electrostatic force is changing。

So the other thing he did was he figured out that the electrostatic force could be applied in a bang bang strategy。

Where you just turn on and off a voltage。You don't have to apply a proportional voltage。

 proportional to capacitance。You just， when the finger gets too close， you turn on a voltage。

When it's far enough away， you turn it off。And he discovered that when you built that feedback system。

That turning on and off the voltage was a digital signal that directly gives you a digital read of the acceleration。

You don't need an AT toD converter。Okay， you get the digital signal straight out of the feedback system that's applying this bang bang control to this silicon finger。

Extremely clever design。And it's the design that is used in all virtually all silicon accelerometers today。

 some variant of that design。Invented here。Now， what about this question of orientation？

Suppose I really do want to do dead reckoning。In fact。

 dead reckoning is extremely useful and it's used， for example， all commercial aircraft。

Are required to have navigation equipment。That can tell where the aircraft is。

For an hour without GPS。To within a half annautical mile。ok。嗯。

In a blanket of fog or in the clouds where they can't see anything。How do they do that？Well。

 they measure acceleration， but they have to also measure orientation。

Because of this problem that I can't tell the difference between a rapid acceleration here and a lesser acceleration plus a rotation。

There's no way to tell the difference just using an accelerometer。

Anybody know how you could tell the difference？I think multiple accelerometers isn't really going to help in this case。

 okay because with this particular scenario that I indicated， okay。

 there's three aes of accelerometer， there's， there's that axis。Oh， I guess， no， that's true。

 actually， there would be two。There are two of them that are affected by this rotation。Yeah。

So you could。You could combine those， yes， you're right。Or you could use a gyroscope。Okay。

A gyroscope is a completely different sensor right and the easiest way to understand a gyroscope is from the mechanical version of a gyroscope。

 which is just a spinning disk with a certain amount of mass and a spinning disc likes to keep its orientation。

 it's hard to get it to go in a different orientation。So if you mount it on a double gimbal。Okay。

Then the mounting can rotate， but the spinning disc stays still。Okay， so if you。

Make your frame of reference。The outside ring of the double gimbal。

It's going to look to you as if the disc is actually spinning around。

And that spinning around is a direct measure of your change in orientation。Okay。Now。

 mechanical gyroscopes are heavy。And they require a lot of maintenance。

 so there's a variety of different techniques that have been used to make integrated circuit scale versions of those。

One of the ones that I really like is this optical gyroscope which uses a laser。

That it splits so that the laser goes in two directions around a ring。Okay。

And when the ring is rotating。The light will travel a slightly different distance in one direction versus the other。

And that slightly different distance you can measure as an interference pattern。

Of the laser beam with itself。ok。So you measure this。

 whether you're getting constructive or destructive interference from the laser beam。

 and you can tell how quickly the ring is rotating。ok。That's a rather clever technique。

So inertial navigation systems combine these things。



![](img/1f6f2ec7a64362bc97a34ded60791f3d_7.png)

And。Typically because。No matter how。Good a job you do with your accelerometer and with correcting any errors and calibrating it and combining in the gyroscope。

 you're still going to get errors that are going to compound。

So a typical inertial navigation system will combine with GPS and will anchor your measurement according to a GPS signal periodically。

Okay。Now。嗯。Here's a potential use for accelerometers。 This is courtesy of Ross Bodock。



![](img/1f6f2ec7a64362bc97a34ded60791f3d_9.png)

We've all had this problem of going to a web page that you can't really read on your small screen so if you could really make good measurements。

 maybe you could sort of pan your device over the screen。One time when I showed this in this class。

 one student pointed out， well what's going to happen if you're stopped at the Bart station。

 you're reading the newspaper and the train starts up。

The newspaper is going to slide out from under you。呵。It's going to be a very weird experience。嗯。Yeah。



![](img/1f6f2ec7a64362bc97a34ded60791f3d_11.png)

Some sensors are very simple。strain gauges are devices where the resistance changes depending on flex。

I had the pleasure of participating in one of the hackathons that they had in the invention lab in May。

 and one of the people on my team used a strain gauge to make a really beautiful piece of jewelry she took a string of LEDs。

And。And they would change color depending on how they were bent。

 she attached a strain gauge to them and so you would get these really weird color patterns depending on just the bending of this chain of LEDs that she was wearing around her neck。

 it was really cute， I liked it。嗯。One of the challenges with this， of course。

 is if all you've got is resistance changing。Versus flexing。

 you have to measure that resistance somehow and convert it into a digital signal to then control those LEDs。

 so how would you measure changes in resistance？Somebody surely has taken E40。Yeah。

 run a fixed current through it and measure the voltage。

A toD converters are very good at measuring voltages。Okay， so you need a current source。

 which you have to take one of our circuits classes to figure out how to make that。And。

And you can use that to measure changes in resistance。All right。

 so there's a lot of issues that come up when designing with sensors。

 you should always understand what your sensor is measuring and what it's not measuring， okay。

 because I you know， I've seen people in their projects who will。You know。

 be beating their heads against the wall for weeks because they're trying to use an accelerometer to measure what a gyroscope measures。

And it's difficult， it's not impossible， but it's difficult。

 right You got to know what your sensor is actually measuring。And。

It's worth spending some time just modeling the behavior of the sensor。Caibrating it。

 how does the measurement actually relate to the physical phenomenon that you're measuring？

 the first lab this week is really going to be about understanding that for accelerometers。

Understanding nonlinearities。诶。Proportional change in the physical quantity you're measuring may translate into a disproportional change in your measurement depending on the magnitude of the change。

 okay that's a nonlinearity。Sampling of course， with cyber physical systems becomes a big problem。

 and so you probably remember from Es 20， the aliasing phenomenon， which is illustrated at the top。

 which is that here in this plot we have two sinusoids。One with frequency， one kilohertz。

 the other one with frequency，9 kilohertz。And they're being sampled at 8 kilohertz。

 so the dots are the samples。You can't tell the difference。

Between the 1 kHz sine waveve and the 9 kHz sine wave， they give you the same set of samples。

That's aliasing。The set of samples represents not just one sinusoid。

But many possible sinusoids that might have given you the same samples。Okay。

So you need to pick your sample rates。By the way， one of the interesting things about taking his class right now today。

Is there's a lot of hype out there these days about the Internet of things， right it's really。

 really hype。Right now。And a lot of the internet of things， the way it's getting deployed these days。

 gives you almost no control over sampling rates。Which makes it rather challenging to use this kind of technology in a lot of applications。

Nevertheless， it's something to consider， you also get aliasing phenomena with images。

Where images that are sampled can give you interesting distortions because of the sampling。嗯。

Noise is a problem with all sensors and it's a fairly sophisticated topic and we don't really cover it in this course because。

It really requires stochastic signal processing to understand it completely。So if you take。126， 121。

 226， and courses that depend on those。You'll get plenty of exposure to how to do this kind of signal conditioning。

 but we're not really going to cover it in this course。

So I'd like to talk a little bit about auators。嗯。And in particular。I can promise you that。

Many of you in doing your projects。Are going to。Fry on Arduino board。Or something。ok。

And you're going to do it because you're not paying attention to the problem of delivering power to an actuator。

Okay。It's it。If you're a computer scientist， you think everything's just zeros and ones， right。

 so I just make it one and it'll go。I make it zero and it'll stop。

The physical world doesn't really work that way， you have to somehow translate those zeros and ones into a source of power if you connect up an LED directly to a GPI open with no resistor。

You're going to fry the board。Okay， because you're going to put a level of current through it that is going to make it extremely hot and it makes the silicon melt。

Which isn't good for the chip。Okay， so you have to pay attention。To these things。

Motors are particularly interesting ones because they actually， I mean， in a lot of applications。

 they require substantial power。So I was just talking with a。

A fellow that we're working with on a research project。

Who happens to come from a Japanese company called IHI that is a large industrial conglomerate。

They make really， really big machinery， okay， things like power plants。

 and they make backhoes that could sweep away this building in one scoop。ok。

And they're trying to robotize all these pieces of equipment。Okay， so they're envisioning a future。

Of。诶。呃。You know， a construction site。Where the machinery is all orchestrating itself and building the building。

But it requires delivering a lot of energy and controlling a lot of energy to these devices。

 and you've got to do that from these little tiny little microprocessors， right？

It can only sink and source so much current。So you have to pay a lot of attention to this。嗯。

You can make machinery that is also extremely precise， one of my favorite examples。

 which is a little old male， so I'm sure this has gotten improved a lot。

 but this is it's effectively a bionic arm。嗯。It's controlled from neural signals rather crudely。

 okay， so you know basically the wearer of this thing learns to say say to it， grasp。

It doesn't learn。To say， you know， move the fingers until you feel a certain amount of pressure。

 It just can either tell it to grasp or not grasp。And then the microprocessors in this device themselves have kind of a pre programmegrammed control system internally to grasp and grasp means apply just enough pressure to hold this thing。

 so you got pressure sensors on the fingers。And you're driving motors and you're delivering a very precise amount of power to them。

They were very proud of the fact that they could grab a paper cup without crushing it。Okay。

 that's actually a pretty difficult accomplishment and it requires very precise control over the power that you deliver to the motors。

So how do you do that？Well。One way to do it， first of all， you sort of need to understand motors。

Go and study mechanical engineering。They study motors， how many of you are mechanical engineering？

Majoors。That's a relatively small proportion。A good， I don't know。

 quarter of the class that are Emmys。嗯。But anyway， MEmys understand motors for the most part。

You know that if you have a DC motor， the torque that's applied by the motor is proportional to the current that flows through the motor。

 okay so what you're trying to do is control that current。

So you could do that in a naive way by saying， well。

 let's build a piece of electronics that's a completely analog thing。

So if I want to apply more torque。I increase the current by a certain amount。

 if I want to apply less torque， I decrease the current by a certain amount。

But that's actually really kind of difficult to do， especially if you need large torques。

Because then you have to control large currents and you have to control small fluctuations in large currents。

And that's not very easy to do。That requires power amplifiers that are going to take a small weak signal from a microprocessor。

 goes to a DA converter， the DDA converter can't drive much power。

And now youve got to run it through a piece of electronics that can really put some。Force behind it。

 okay and it's got to do it in a way that's linear。So your control signal。

 when your control signal varies a little bit， you want your power signal to vary by a little bit。

But the electronics to do that is expensive， power electronics is difficult to make linear and expensive。

 and fortunately for motors you don't usually need to do that。

So what should you do with motors instead？Plse with modulation， are you one of the Macs？Okay。Yeah。

Motors， it turns out， are big inertial devices with a lot of inducts。Okay， the inductance。

 if you remember from E 40， is kind of like electrical inertia。

Inductance is really the phenomenon that。Where currents don't like to change quickly。ok。

If you've got a current flowing， it wants to keep flowing。All right， so it's electrical inertia。

In addition， a motor has mechanical inertia， it's got this rotating frame。

 which likes to keep rotating。Okay。If you change the voltages that you apply very quickly。

You just jolt it by a little bit， and it doesn't react with big jolts because of all that inertia between the inductance and the mechanical inertia。

It reacts rather smoothly。So here's a plot。Here's the control signal that we're applying to a motor。

 we're just， this is again， a bang bangang controller like Mark Lemkin's accelerometer。

Where you just switch on a voltage and then switch it off。And then switch it on， switch it on。

 this has about a 10% duty cycle， so you've got the voltage on about 10% of the time。

If you increase it to 12%。You will apply more force with the motor。Okay， decrease it to 8%。

 you apply less force， and you can use this as a feedback system。

 just vary the amount the percentage， the fraction of time。

 the duty cycle at which you're applying as voltage。Delivering power。for a signal like this is easy。

Comparatively， it's just a switch。 You just need a switch that can handle large currents。

 and making a switch that can handle large currents is much easier than making an amplifier that can handle large currents。

Okay， just turn it on and off。So。So on the time scale of seconds。For this particular motor model。

 you get with this particular signal， if you start applying it at time zero。

 you see a very gradual rise in the angular velocity of the motor。

 it takes it at a good two seconds to stabilize at a certain speed。

If you look closely at the details of the model， you'll see that， well。

 the motor is actually accelerating。Its angular velocity is increasing while the voltage is on and decreasing while the voltage is off。

 it's decreasing because of friction。And electrical losses， okay？嗯。But。Nevertheless。

 you get an overall， rather smooth motion。So here is the model that that plot was generated from。

 okay？And again， this should help to remind you of， you know。

 this is kind of the level of math that we expect you to be able to handle。For this class。

 all right if this is。If there's too much for you， you might want to consider postponing taking the class until next year or something。

 okay？But these two equations are， well， this one is just f equals MA。ok。Let me walk you through it。

 it's the mechanical model，s this is the rotational version of F equals MA。

So when you're talking about rotating， instead of talking about mass。

 you talk about a moment of inertia。So a mass。Is a measure of the reluctance of a mechanical thing to move。

The bigger the mass， the harder you have to push it。

Mo of inertia is the reluctance of a thing to rotate。

So it's just like mass except it's talking about rotational motion。So。

The mass is a moment of inertia， the acceleration is the derivative of the angular velocity。

So this is。MA。Okay。So the other side should be F， the force。But we're interested in rotational force。

So I mentioned that a motor。Reacts to current。Okay， the torque。

In a motor is proportional to the current。And the proportionality constant is just an empirical quantity that is。

 how good is your motor？Right。Good motors will have a relatively high constant。

Poor motors will have a lower cut well， maybe not poor， I mean。

 it depends on what you're trying to design it for。

 but each motor design will have some torque constant that will apply a force that's proportional to the current。

Friction is another force on the motor。Again， an empirical quantity that depends on the motor。

 you just have to measure it。And it's proportional to the angular velocity。And then the load。

 whatever is connected to the motor。Also could be providing a torque。ok。In fact。

Motors and generators。Are actually pretty much the same mechanical devices。

A generator is a motor where the load applies the torque。

And a motor is a generator where the current applies the torque。喂。But they're really the same device。

So it just depends on where the energy is coming from， if the energy is coming from the load。

 you have a generator， if the energy is coming from the current， you have a motor。Okay。All right。

 so that's the mechanical system， F equals MA。And the electrical model is given up above。

This is the first part of that is just OhM's law， voltage is proportional to current。

 and the proportionality constant is a resistance。Motors don't tend to have much capacitance so that it doesn't figure into these equations。

 but they have a lot of inductance， they have a lot of inductance because they're made with coils of wire。

Which tend to give you inductance。Okay， so voltage is proportional to the rate of change of current。

 Remember， inductance is the reluctance。Of current to change。Okay。

That reflects in the equations by when current changes quickly， voltage changes quickly。Okay。

 so the voltage is proportional to the rate of change of current。

And the proportionality constant is called the inductance。

And then the third term is the most interesting one。

Because a motor and a generator are the same thing。When the motor is spinning。

It's actually generating。And it's going to generate a back electromagnetic force。

That will counter the action of the motor。Okay， so that factors into that electrical equation there。

Okay， so this is we won't go， we won't do anything。In modeling physical systems。

 any more detailed than this。The limit， right so if you can kind of understand these equations。

 you're fine。Okay。And we're not going to ask you to derive equations like this。

 we're not going to ask you to do the physics。ok。诶。So that's just for the。Physical modeling side。

All right， cameras， I mentioned that this infrared camera here in the we， right？

The Wi is kind of an older gaming console， right？Xbox introduced the Connect。

Which is also a camera based system， the way the connect works。

Is that it actually floods the room with an infrared grid。Okay， you can't see it because we don't。

Humans are not very good sensors， actually。We can make machines that are better sensors than humans。

 and the machine can see the infrared grid and it can do very precise measurements of the distance of an object from the connect by just looking at how big the squares are。

Right。Not quite because they'll be affected by the orientation of the surface。

But they can look for keystoneing。Okay。Which is the phenomenon that if you send out an infrared square and it hits a slanted surface。

It's going to look like a rhombuus instead of a square。

So you do that analysis on the visual system and you can tell about orientation and distance of objects。

Relatively easily。There's a lot you can do with cameras and one of the things that I'd like to emphasize is that I think we're going to see much more interesting uses of cameras over the next few years。

I think the emphasis in cameras so far has been anthropomorphic。

People always think cameras are trying to do what the human visual system does。

So we're trying to get a rectangular field of view， well。

 humans don't have a rectangular field of view， okay， they were trying to do what。

What the television version of the human vision， okay rectangular field of view okay that gives you this two dimensional image of you know window into the world that's a very anthropomorphic view and when we think about what machines can do。

😊，They don't need。There's no particular reason why you have to organize your vision that way。

So one of my favorite devices is this phase based device， we have an installation of this。

 theres actually two installations， one in Corrry Hall， one in Suharcho Di Hall。

That are being used by researchers who are looking at。

Coordinated multi vehicleh coordination of drones， for example。

 so they fly a bunch of drones around in a room。And they can tell very precisely where they are with this motion tracking system。

 which was first popularized when used in the movies and in fact。

 the first movie that really made extensive use of the system was pirates of the Caribbean。

 which came out in 2003。Okay。And。So the way that this works is you instrument your actors or whatever you're trying to track。

 with these infrared beacons。

![](img/1f6f2ec7a64362bc97a34ded60791f3d_13.png)

And you deploy them in a space that has。Cameras array around them。

 but these are really interesting cameras。They don't take very good pictures。

They're not anthropomorphic cameras。In fact。The cameras have 7，200 pixels。How manys。

How many pixels do you have on your phone？Well， you the cheapest phone today has two million pixels。

And you know， you can get phones with 14 million pixels。These have 7，200 pixels。Okay， not a lot。

And guess what， they're arranged like this， 3，600 pixels in one direction， 3。

600 pixels in the other direction。It's not trying to create。

A rectangular image for human consumption， it has no interest in doing that。Okay。

 it's just trying to find out where these infrared beacons are in three dimensional space。

And this turns out to be a much better arrangement for the camera than you would have if you just used a rectangular array of beacons。

O。嗯。So you can have a motion suit that can detect positions rather nicely。

 And what I'd like to do as a closing。Is show you what you can do with this now for the webcast。

We are going to have to cut off the recording now because I'm going to show you something that is copyrighted material。

And I'm permitted to do that under the fair use clause of the copyright law because I'm commenting about the technology used。

But I'm not permitted to repost the video。Okay， that's not allowed by the fair use clause。

 so for those of you who are relying on the webcast， sorry， you lose out。

