# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p07 -07- L5_ HDL, Verilog II, Timing & Verification.zh_en -BV1iV1XBWEJW_p7-

![](img/a19b516231927e201fb6ab4b83f8c1e1_0.png)

Yeah。我。但是。そ。为什么？Yeah。自水。さ。好。而错到。Yes， video is not on YouTube。I think if I talk thiss what Ni says。

 no， are you sure？Yeah。Okay。おち。あし。你这。在说。あ。这公司。あす。确。もか。公。Yeah。Yeah。Okay。3人好。Good afternoon， everyone。

 let's get us started。YeahYeah。我大。没。Is my audio okay on Zoom。Okay。Okay。Okay。

 welcome back to another lecture in digital design and Comp architecture， lecture five。

 today we first going to continue what we have left off in Harvard。😊。

Description languages and very large。 And then hopefully。

 we're going to have time to start timing and verification。 And tomorrow。

 we're going to basically continue that and finish。Timing and verification。

 and potentially finishing the。First part of this course， which is digital design。And from next week。

 we're going to start learning about computer architecture to use fundamentals that we learned。

 how to design computers， and processor， microprocessor， and so on and so forth。

We had some live stream issues and recording issues last week for for Friday lecture。

 so that's why we actually。Uploaded a new video for the last week lecture if you couldn't attend last week lecture。

 you can actually check that video， which it was premiered actually yesterday。

 but you can also check anytime you want。Okay。Are there any questions？Then we can get started。

So this is agenda for today， which is going to be related to。😊，Hardware description languages。

And these are the readings for this week。😊，This chapter for hardware description language and also this is for today probably and tomorrow about timing and verification we discuss about why we need hardware software。

Hardware description languages last week， but I'm going to quickly go over them to jog your memory so essentially HDTs enable easy description of hardware structures and you know that in hardware we have wires gates a lot of components like flipfl clock and also some specification like rising falling edge as well as combinational sequential logical elements and also in hardware we have a lot of concurrency so defining all these in using normal and you would say general purpose software languages is not easy so that's why people came up with these specialized languages for hardware to basically provide that you know easy description。

😊。

![](img/a19b516231927e201fb6ab4b83f8c1e1_2.png)

![](img/a19b516231927e201fb6ab4b83f8c1e1_3.png)

So we discussed about this key design principle in designing our system that we need to come up with a hierarchy。

And we discussed about this top down design methodology that you have a top level module。

And that is needs to be identified using sub moduleles that they are necessary to build。

 and then sub moduleles can also be divided to leaf cells。

 some other sub moduleules and also in the end some leaves which your leaf cell can be circuits component that cannot further be divided it can be logicgates or sometimes primitive cell library elements that we're going to see a little bit。

We also have this bottom of design methodology that you need to start for your leaves and then make bigger modules and then combine them to construct your top level module and I said that in the end usually we combine both methodology。

 we always kind of think kind of top level top down modules。

 top down design methodology and then when we want to implement we use usually follow bottom of design methodology。

And this is really important for testing and verification as well。

 so once you have this kind of design methodology， you want to make sure that you verify every single module before going to the higher rank。

😊，So if you don't， for example， test your any of these modules that you have here。

 and then you combine them to make this sub moduleule and then you start testing your sub moduleule in this area。

If you get some error， then good luck finding your errors essentially a source of errors because this can be combined some accumulated errors that happening from any of these prior levels。

 so it's important that in any level that you are designing you need to verify your module。

 make sure that is correct and then go to the another level。We're going to learn about verification。

 probably tomorrow， but that's the kind of insight that you need to get here。Okay。

 and then we discuss how we can define the module in very log that essentially you need to define name of the module direction of the ports input output and also name of the ports。

 and then we need to describe the functionality of the module we see this kind of module definition as an example that you have three inputs ABC and one output。

 which is why。And then yeah， we go over these synts and we discussed that these two following codes are essentially the same and it depends on your slide when you're programming。

And also we discussed about having bit vectors that， for example， a here represent a 32 bit value。

 so we prefer define it as 31 to 0 a and we do not use the other way around like 0 to 31 when we want to define beat vectors。

We use this when we want to kind of have an array in your design。 So sometimes in your in your code。

 you want to define an array。 So for that， you can actually make it like this。

 You can also have an array of bit vectorctors essentially so。You can combine all these together。

Okay， and this part， we left off and then we continue from this part。😊。

So now I want to essentially discuss some syntax that we have in verylock so one very important operation that we want to do is manipulating bits。

😊，One of them is bit slicing， which is we want to assign partial bosses so here is an example you have a long bus which is 16 bit and you have a short bus which is8 bit so you can assign short bus to long bus2 to5 which is。

Basically a slice of that long bus essentially so you can actually select portion of that long bus and assign them to your short bus This is one of the syntax that we have Another syntax is concatenation that you can essentially concate a lot of different signal together to make a bigger signal or bigger bit vector So here we know that for example。

 this y is a four bit bit vector and you can actually concate these four basically values here to make it this4 bit vector a2 a1 a0 and a0 for example。

And each of these a2 is1 bit。Another way is to use duplication so you can also use this syntax here we want for x。

 we want to have4 a0 for example， you can write it like this using concatenation command or you can also use this duplication command which essentially youre duplicating a0。

 so these kind of syntax help you to you know write your code a bit easier or maybe a smarter。

There are also some other basic synt that I'm going to go over。

 So very luck is case sensitive someone， some people actually。Find it a bit annoying， which is but。

It depends on your slide， so essentially these some name and some name are not the same in very luck be careful and names can start with numbers so too good is not a valid name。

Wite as spaces are also ignored， you can have comments like these。

It's very similar to C+ plus I guess notation here。

 you can have this slash slash and you have a single line command and then you can also have these slashes start to have multiple multi line command。

So we have two main slide of HDL implementation this is not actually only。

specified to very larges this is actually more or less related to any hardware description language but here also more specifically about very large we can have a structural way of implementation is' also called as gate level but does not need to be essentially gate level the definition is that the module but it contains gate level description of the circuit but these gates can be also some instances of your prior modules so you have sub modules so you have some gates you combine these gates and make some sub modules。

😊，And then you want to combine these sub modules to make your top module essentially。

 so these sub modules， if you instant them， instantiate them your code。

 you are actually using this structural way of programming。So Vi it。

 the module has this gate level description or module instantiation of the circuit。

 and we describe how modules are interconnected。😊，And each module contains other module。

 which is instances and interconnection between those modules。

 and we need to describe a hierarchy of modules that define as gate essentially。

 another way is behavioral which the module body contains the functional description of the circuit。

And contains logical and mathematical operators。 So writing modules in behavioral is。

Usually quite easy， but then because level of abstraction is higher than gate level。

 but it also comes with some issues and overhead that we're going to see later。😊，Okay。And in the end。

 many practical design actually use a combination of boths and you're going to also see in some examples today。

Okay。Any question， Yes， how do we decide where the wires go。Like doesn itt decideally No。

 we're gonna see in this index。 Yeah， so。Okay。So now assume that we have this design。

 there are this top module and this top module actually has two sub module， which is small。

 small module。And you can see that this is the first instantiation in this second one and these are our input to the top module ALC。

 and this is the output and also we have some intermediate wire here n1。😊。

See how we can actually write this code， for example， in very luck。😊。

So we first need to define this top module。I mean， there is no first and second you can actually do it the other way。

 but this is one way， you have this module top， which is you have these inputs a cell。

 C and output y， so you know this notation also there is an intermediate via here that you need to define it via n1。

Read this syntax。And then you have these two sub moduleule。

 you also need to define a module for that module is small。And this has A B Y。

 so AB are the inputs and y is the output。And there should be some description of a small that we kind of ignore at this moment and then end module。

So now we need to instantiate from these small submers essentially So this is the first instantiation small and then the name of this instantiation can be anything。

 So here is that I underline first and then you need to say how these ports are connected So you know that for example。

 input a is going to the。Input a of this first module。 So you just， this is the notation。

 you say that dot a。Is connected to a。So this a here is actually this a。

And dot a is actually saying that the input port of a is connected to that wire。

And you can do it for other things so for B also you can say that dot B is connected to C and dot y。

Which is the output is actually connected to this wire and one。

 that's why we need to define this wire essentially here。

So this is the first instance and the second instance we have it here。

 so essentially yeah the output of it， which is again n1 is going to go to the port a。And then。

 C goes to B。And the output of this module goes to output y。So with that。

 we actually finish the definition of this top module。

 we still need to define the description of the module as small。

 which you kind of ignore at this moment， but this is if you write your code in this aside。

 you are actually using a structural way of programming。Any question？Does that answer your question？

It's sort of this， but like。You could imagine a line like the wire going。Diaagonal or。

Like how does it figure out where to best？How do best like to put the wire。

Conducted chip itself not even So you are defining you are defining it we the endpoint but not the way okay。

 so you you are talking about the routing of that wire。

 So that's actually in another level So when you when you program your HD。

 you need to test and verify and then when you're okay you're sure that your design is at okay and running correctly at that moment you need to synthesize it。

There are other tools for that， which you call them computer aided design。

 so you need to sthesize your HDL code to some gate level using some cell libraries。

 we're going to see actually that a little bit。But then after that。

 when you have the description of that gate level， then you need to use some other tools which they do these place and road and floor planning。

 essentially。So different companies actually have their own tools that they use to place onro and floor planning and the question that you're asking is actually the question for that moment when people want to do floor planning and place onro。

 they need to solve this question that where should I place these components and how should I wires them？

So that's out of a scope of this course， but we can discuss maybe later offline if you want。

Any other question？That's also happening kind of in Vivado also so because for E FiJ you also need to do this operation as so the tool chain that I describe is actually for a kind of design like custom chip but for F FiJ we also have the similar tool chain so your HDL code needs to be synthesized and mapped to some LUTs。

😊，And then these Luts need to do place and wrote， essentially you need to place these Luts and then rot them somehow。

 and that's the job for Vivado too， essentially。嗯。Question， but that was a very good question。Okay。

 great。So we can also have some other form of module iniation。So this kind of notation。

 you can actually also write it as is。A set N。Here you kind of assume basically。

You are relying on the order of the port， so in the definition of a small unit you know that we have three ports。

 A BY。And this is order essentially A B Y， so when you want to connect these ports。

 these wires to these ports， if you put exactly three signals here and you follow the same order。

 you are making sure that you' are connecting correctly essentially。😊，But as you can see。

 this is not reliable， so that's why。😊，Better to use the other notation， which is happening here。

 and that's much better for to reduce basically for better maintainability of your code。Question。😊。

Okay， great。Yeah。I also forgot to mention that these HL very lucky slides that we have are kind of tutorial for you。

😊，So I may actually moving fast on some of these asides。

 but in the end you're going to use a lot of this information in your labs。

 so in the lab assignment that you're going to have you're going to actually look into all these slides and follow the base symbols syntax and all these stuff。

 so don't worry if I'm going over some of these slides a little bit fast。Okay。

 so in a structure actually example， we say that verylock supports basic logic gates as predefin primitives。

 we actually this is very important， so these primitives are logic gates and they are instantd like modules except that they are prettydefin in verylock and we don't need to add a module to define it。

😊，Like these gates like not and and or you can just simply write and and then G do G2。

 and then this is the basically。Insiation of that， like the connection of these ports。So。Yeah。

 so essentially for these kind of primitives， you don't need to define them。

 verylock has already defined them in the library。😊，Here also we can look quickly to this example。

 you can see that this is the definition of this multiplexer and。So you simply say that okay。

 we have these two input D0 and d1 and then this is output y and this our selector， right？

So you can easily write this code。There is also a little bit not here in this tiny knot。

 so you need to define this knot as well so that's why we have this wire Ns。And then we put not J1。

 Ns and S。Another important thing for all these primitives is that the first。

Basically signal that you put in parentencies is actually your output and then the rest is the inputs so that's the syntax little syntax that you need to memorize but that's the onlyity so for not we have this ns meaning that okay this is my output and then s is the input for and we have this y1 which is the output and then this d0 and ns and for this and also we have output is y2 and then d1 and s are the input and then we have this or gate which or y1 and y2 and then output is y。

So that's your definition of your multiplexer two to one， yes。

Is there a preferred option for whether we should be buying inputs and outputs within the brackets or whether。

In the。No， this is actually completely related to your style， essentially。

 whatever I actually I remember I was following this style when I was coding。

 but some people just following the other so。😊，ok。Okay now we are done with a structural HDL example so let's also look into behavioral remember these two main styles in behavioral essentially we are using equations and they can be arithmetic logical equations。

So here this is an example functionality that you can we are providing here。

 like you have this module example and then you have three inputs and one output。😊。

So you are use this is a key word here that we use assign this is you need to always use this keyword when you want to assign you know a value to a signal。

 this is a notation， you need to write a sign and then the output like the。

The output or the signal that we want to assign value to it， which is why here for example。

 and then some equation and here is a for example equation that negate A and negate B and negate C and then or and then many。

 many other things so you can actually do a lot of these that can make your life much easier。😊。

And this can be actually sthesized to exactly this implementation。These are all these ants like。

The first one。And the second one is this end。And the third one is design， and then you need to order。

Yes， they are not automatically simplyified。They are simplified so all these synthesizing tools。

 they also have this logic minimization operation that they are doing。

 so they are trying to do a lot of optimizations and they are simplifying but I should also say that the way the simplification that we learn in this course like very simple it was to make your signal in two levels essentially your circuit in two levels one level is and and the other level is or right and but in reality usually circuits are actually they have much higher depth。

And the reason is that making big， large and operation for and like big gates are not easy。

 having gate that have like。Tens of input is not something that you can assume easily。

 so that's why in order to reduce the number of inputs to your gates。

 synthesizing tool try to increase the depth of the circuit。

So they actually logic optimizations algorithm are much， much more sophisticated。

 they also consider in this area of increasing the depth of the logic。😊。

And that adds a lot of another angle to your optimization， essentially。

 but at the same time they can also， they don't guarantee that they have the best possible。

With somehow some definition of the best because in the end it's actually trade off。

 you need to kind of you have some constraints and you want to make the best out of these constraints essentially。

 but within that also because they are using a lot of heuristic in all these algorithm optimization techniques。

 so in the end they cannot get to optimum whatever design essentially。😊，Yeah。Very good question。嗯。

Okay。So we have the different bitwise operators in the behavior verylo， here is， for example， and Op。

 this is or operation， this is x or this is none and this is no， for example。

 and you can easily use all these operations。😊，And this is a basically synthesized version of or schematic view of your circuit that we have seen here。

😊，We also have reduction operators in behavioral radiolock， assume you want to reduce。

 you want to do reduction and operation in a bit vector。So you have a big vector of eight bit。

 for example， you want to add all the elements。So one way is to write something like this assign y。

 and then you need to add all these elements， but there is also reduction operators that you can just easily say y equals to amperserson A and then its going to be this means that you are reducing over and essentially。

So those operators that they have this meaning of reduction， you can actually use them like。

And this is schematic view of。This synthesized version， like we should say assign sign by。

Because the and A is going to be like this in the end。Okay。

We can also have this conditional assignment， which I think you are aware of this operator in C++ programming also probably。

 but essentially you can， for example， easily say that this kind of implementation of ifL right。

 say that assign y equals to then you check your condition which is S。

 and then S question mark if it is1， then y should be D1。And it is0 is going to be the0。

 So you have a condition and。That if it's true， then we pick the。This second item here。

 and if it is false， we get the third item， you had a question。Okay。

 and the good thing with this question mark operator。

 we can easily implement multiple excs as you can see。You can also make。Multiply exc of4 to one。

 for example。 So you first need to branch out on。The most significant bit of your selector S1。

 and if it is， for example one， then you need to check the value of your second bit of your selector。

 which is S0。And based on that， you can decide on the input that should connect with the output。Any。

As everyone convinced that this is multiplely except4 to one？Okay， good。Yeah。

 this is also another way of writing it， you can， for example， multiple exc。

 you can also write this way like the code is like if something and then you check if again if if else and else if else。

But you can also write it like if as if as if S， for example， and this is another way， for example。

 you can say that y equals to then you check this condition first， if it is true you assign it to D3。

😊，If it's not， then you check another condition， which is kind of else if。Again。

 another is and then in the end， you get your adss value。

These are quite simple because I think you already know from CL+ programming also。对。Which。

 I'm not sure if do you study C++ in your basic programming or？Oh， Java， okay。

 but Java also we have these operators as far as I remember here。😊。

I kind of assume that you learn C+， that was wrong。Okay。

 so we have also this precedence of operations in verylock that you can also check if you are interested。

😊，But I usually prefer to not rely on these precedents and use parenttices， you know。

 just to make sure things are okay。Okay， now let's see how to express numbers in verylock。

 we have a very exciting notation for numbers in Verlock， which is n。

And then the base and then the value。So n is actually a number of bits because in numbers values are actually you need to somehow synthesize them right so you need to have some wires for them or some registers for them so you need to think about okay how many bits you want to use so that's why we have this n here to show the number of bits。

And then we have base。Which you if you for example put B or the values that you are right here is going to be interpreted in binary。

 if you for example H is going to be interpreted in Hxa deimmal or D is deimal or O is octal for example。

 so you need to also specify the base here and then the number。

And in the number you can actually also have x which is invalid and also z which is floating。

 so you kind of know about x which is kind of don't care or in or Z which is floating。

 which we use Z for trit buffer for example， if you all remember。So let's see some examples。

 let's see， for example， this one， we are saying that four。😊。

We have a value which is four bits and then it's going to be binary of 1001 so the stored number is going to be 1001 here we have a very large sorry we have a number which is 8 bit and then binary1001 so whenever you have less number of value here as as much as you need you need to add zeros here so here for example it's going to be stored as 0001001。

Because you need two eight beats here。You can also use these underscore for better readability。

 so this is just for better programming st， it's not something related to。

The number that you' are present。If you don't specify the length。

 it's going to be considered as  32 bits， which is the default size in very lucky。😊。

You can also change the base and。And you can see this example also later。Any question？Good。

So these are kind of reminders for you that we have these floating signals and we use this concept for triid buffer as remember。

And then we talk about how we can use this basically tri buffer in order to manage a shared boss。

 so in this example， for example we have we have CPU and also we have memory and both CPU and memory needs to access a boss like your memory boss。

So both of them cannot drive the bus at the same time。

 so we have this trice buffer in order to gate CPU or gate memory。When it is zero。

 it means that CPU cannot drive the shared bots and memory can drive essentially if the gate memory is one for example。

😊，And we also use these for other， for example， interfaces， as we can see here。

So the true table for and gate with z and x in your input can be something like this， so this part。

It's similar to what you have already seen， which is An gate。But whenever you have， for example。

 Z and x， let's see what's going to happen in your output。😊。

If you if you have zero in one of your inputs。The output is always zero。

 no matter the other input is0 or x， which kind of makes sense for end gate， right。

 whenever you have zero one input zeros， then output should be zero。But in other case。

 when you have one input as one， then the output depends on the other input。

 which going to be z or x and in the end your output in very log notation consider as x so that's why we are so whenever one of your input is z and then the other input for example is one the output that very log going to show you is actually x so very log is not going to show z in the output which kind of makes sense because your output is still connected to。

pull up or pull down network is not float right is's not floating so Z so that that's why we don't use Z for the output in for the and operation。

 for example。😊，And I think you are also aware of this priority circuit that we used for priority encoder。

 for example。And you can easily define it and very like using this notation。Any question？Okay， great。

So now let's see what happens with HDL code once you have your HDL code what you can do it。

 so one is actually sthesizing so you need to you can synthesize your circuit into hardware。

 into primitives in these gates。And then after that gate also needs to be synitsized actually to transistors。

And in the end， your circuit， all these transitionistor needs to be layout。On your chip。Wch is。

Because for that， for example， all these operation process of litgraph that you want to design your IC integrated circuit。

 you need kind of layout of all these transistor and where they are placed such that you make some mask and then based on that mask and you know and this litgraph process you can beat your IC。

So， but essentially the synthesizing is very important and modern tourists are able to map synthesizable HDL code into low level cell libraries。

And they can perform many optimizations， as I said。Like optimization in order to， for example。

 based on your constraints， sometimes your constraints is that you want your circuit to work with。

Frequency of1 gigHtz so that's your constraint and then thethesizing tool tries to synthesize your circuit in a way that can work with that frequency。

So that's a constraint you are providing or for example。

 you are saying that you want your circuit to be。The area the area cost of that circuit needs to be less than one milliime square for example。

 so once you have that constraint then synthesizing tool tries to make sure that your area is not is less than that and all these sometimes this actually constraint can be a bit conflicting so synthesizing tool actually does a lot of job trade off between the constraint that you define and your goals into get you know to make you and designer in the end happy hopefully。

But the problem is that they cannot guarantee that the solution is optimal and it's mainly due to computationally expensive placing and placement and routing algorithms。

Okay。It's actually a bit of our job also that we need to also do our job well。

 so we need to describe our circuit in HDL in a nice tocenttheized way so whenever you program in HDL。

 you need to also think about okay， what would be the hardware structure of that if you don't think about hardware while you're doing HDL you're going to end up something that you don't like in the end。

I'm going to actually show a quote later that has that message。Okay。

 and another important thing that you can do with your HDL is to simulate so we can simulate our code that allows the behavior of the circuit to be verified without actually manufacturing the circuit this is really critical as I said because we don't design we don't make our top level module and then you place enroed and then test it so with every step you want to test and make sure things are okay so every single module needs to be verified and once you are okay with the functionality of that you go a bit higher and then you design combine them make a bigger circuit。

 then you need to test that and also go up and up until you get to the top level once you are fully okay and finally the correctness of your design you can then synthesize it。

And then basically through the place and role， so simulation is actually very。

 very important and exciting part of using HDs。And the good thing is that all these simulators can work on a structure or behavioral skills。

And also for functional and timing verification that we're going to also see later。Okay。

So this recall this example that we have shown and this is the synthesized。😊。

It's going to be a kind of simulation that we're going to do in this course as well。

 so you need to give some basically design this way from diagram so for these inputs you need to value them。

You need to basically make some pulses like in this time frame which when they are going to be  one when they are going to be zero。

 so there is a timeframe and pulse specification for all these inputs and then for the output the simulator is going to generate view the vafor。

And then you can actually convince you yourself that this circuit is working correct or not。Question。

 but this is not as easy as it looks。And I actually test is one of the most expensive and time consuming part of actually designs。

😊，And a lot of money is actually going into making sure that that this design。

 this ship is actually working correctly。So。Vifying our modules and basically circuits is not an easy task。

 especially because of when your design gets bigger and bigger because when you have only this kind of design ABC。

 you know， only three inputs。So， there are only 8。You know， basically。Patterns of ABC。

 and you can actually check every single pattern。You can also go a bit also deeper and say that changing from one pattern to another pattern。

 so there can be a lot of rotation between that， you can also test all of them。

But once your design has tens input or hundreds of input。

 then you cannot test all different patterns So you need to have a kind of sample， you know。

 you need to sample and somehow。s that okay these patterns might be more problematic so I'm going to test them。

 so that's why actually verification is one of the active still active research in CA tools and also design。

Okay， Christian。So this is also a note on hardware sentences。

 you can actually also read it from your book， but I'm going to also read it very， very quickly。

So one of the most common mistakes for beginners is to think of HDL as a computer program rather than a。

Shorthand for describing digital hardware， if you don't know approximately what hardware your HDL should stheize into。

 you probably won't like what you get and that was my point essentially so you need to think about the hardware when you're programming with HDL。

You might create far more hardware than is necessary。

 or you might write code that simulates correctly but cannot be implemented in hardware。

Instead think of your system in terms of blocks of combination logic registers and find machine sketch these blockss on paper and show how they are connected before you start writing code so that's why following this methodology of top down and then implementing bottom up is really important and actually using structure via programming in very lucky。

Kind of very important。 So you can actually use functional behavior。

 behavioral style of programming for some simple some modules， you know that they are。😊。

Close to the leaf， but then after that you need to essentially combine these modules and make bigger。

 bigger modules， so then that's where you use more structural a programming。Okay。

 so these are what we have seen so far， we know how to describe a structure hierarchy。

 we know how to use functional。How to describe functionality using behavioral modeling。

 we know how to write simple logic equation and also design for example multiplexer functionality。

 we can also describe constants there is a keyword for that that you can also check。

But there is more。So the thing is that we can write very low code in many different ways。

We can express the same functionality by developing very low code at the low level of abstraction。

 we have poor readability。But it's easier automated optimization， especially for low level tools。

But at the higher higher level of abstraction， we have better readability。

 but at the same time we have more difficult automated optimizations so let's。😊。

See with this example， we want to compare two numbers。And like this equality check。

So you know from last lectures that equally check can be done easily with x nor and then ending the output of them。

 like if this equal is1， meaning that A and B are completely equal， and if it is zero。

 it means that they are not equal。So one way to write it is completely following gate level implementation。

😊，So， you have。Okay。You can also， I kind of。Ignore this part You can also define these two input X nor gate and also to input and give。

 which is kind of unnecessarynecessarily because I mean these。Gates are already implemented。

As as primitives， so you don't need to do that， but this example wants to show the extreme case that we define everything。

So and then you can actually combine all these gates。诶。In your design。

 so this instantiation of this xn， so we have three xNs and then we have three ans because each an is actually two inputs。

And then basically you can get your equality check。But you can make it simpler。

Using logical operators， you can use assign statement and then for and operation。

 you can make it simple， then you can turn all these three assignment to actually one assignment。

 which is you can use for and operation。电呢。Then actually， yes， you can also instead of。

Instead of ending all these， you can define C as a vector as a bit vector。

 and then you can use this reduction and operation in order to get the equality check。

We also we can get rid of all these xNs definition and then define one assign C as you know。

 xNor of all A and B。We can even get rid of these two assignment and combine them easily with this notation。

 saying that equal if and then the condition is a equal B if true1 if not zero。😊。

So this example wants to show you， you know， kind of how much you can use these operations。

And in order to。Make your code simpler。But you should be careful because some you are actually removing some of the some insight and readability from your code so once you have this kind of XR operations。

 for example， you are shading some information to the reader。😊，whichch might not be needed。

 probably this might not be the best example in the world。

 but in the end this is a trade off that you should be always aware of that that don't overuse this behavioral way of programming。

And also use it as much as possible because that makes your life much easier。Christian。没。

In this exp to would the loss， like would this final solution be slower than the other one。

 because it's bit more difficult。For this example， probably no for more difficult yes， it might be。

Because when a sthesizing tool wants to sitsize your code。

 they make since they don't know what you were thinking of。😊。

They may actually end up adding more gates that's needed， you know？诶。😊，But again。

 I mean this problem rises much more when your design is much， much more complex。

 it's not for such basic designs。But in the end， yeah。

 exactly if you follow a structure survey you're going to get to the hopefully optimize design。

 for example， for a processor， you're going to learn that we have data pass and control unit。😊。

You're not going to you're not open a very large say that module。

 very large and a module processor and then write the whole data pass and control units。

 you're going to have every component data pass also control unit and they're going to instant shape among them。

So let me finish this and then we can take break。So in order to have more reusable very codes。

 sometimes you want to do operation on different widths of numbers，5 bits， six bit or n width。

There is a good way of in Brail light that you can parameterize your modules so you can define this parameter。

 you can see that this hashtag parameter withs8 and this is the default value of this parameter and then you can actually use this parameter to define your bit vectors and with that you can actually set this parameter and this design can be worked with different size。

This is an example of your multiplexer。😊，If you don't specify your parameter。

 is going to be sitized exactly as the default value， which is8。

 so each of these input are8 bit vector。But you can also define this parameter here like hashtag 12。

 meaning that you want to have bit vectors of 12， and this would work。

You can also make it a bit more verbos and then have these dot beats 12。

 which is useful when you have different from several parameters in your design。

 if you have only one parameter， maybe you don't need it。But if you have several parameters。

This notation might be better because you are specifying and much better for readability of your code。

So in very low， we can also add timing to our circuits。But this， I think I will cover it after break。

So let's have a break until during bells again and then real'll continue。😊，自个。Okay。あ。す。看。はさ。し。即。来。

What。あ。就是我看发一个。あそう。さは。要对。一个的。都系。我な。Okay。回。Let's continue。保什的。错。好得所面啊。在这个。

So we talk about how we can define a parameter and how to use it。

But also we can define timings in our very low code。

 so is it possible to define timing relation in very luck， for example。

 you can say that what with the latency of your gates or yeah exactly for every gate you can define latencies。

And also you can add these notations like timing notation to essentially enforce some delay into your circuit。

So this is possible， but you should know that these are only for simulation。

Which is quite useful actually for simulation， when you want to design some test bench， you know。

 when you want to design a test bench to provide a waveform for your input。

You actually use a lot of these notation timing delay notation in very large that you're going to also see in your labs。

Also。Backing to my basically back into my example about synthesizing so you you simulate your code in the functional。

 you do this functional simulation， and then you see that your design works correctly。

 but then you synthesize it。When you syntheize your code your circuit is actually completely different because now your circuit is with all gates that they are defined in the cell library that you gave as an input to your synthesizing to now you want to see that your design actually works correctly with those gates as well so this is actually called as postcentthesizing simulation so it's after after synthesizing you want to simulate and you want to make sure that your design works correctly so for that actually people also add latency of all these gates gates that they are defined in cell library。

😊，In your very low code， in order to see that your design works correctly considering all these delays。

 essentially。So that's why I'm saying that defining these timings are actually very important and very。

 but they are only for simulation。And they cannot be synthesized so whenever， for example。

 when you have a delay of4 nanosecond in your code that4 nanosecond cannot be synthesized。

 so make sure that you don't have these values or timings in your code when on the code that you want to synthesize it on your test bench sure you can do it and you should do it actually。

Okay， so they are used for modeling delays in a circuit， as I said。

 for example here you can see that assign sign sharp5 Z1 neg of a。

 meaning that whenever input a toggles，Output basically z1 will have that value like the negate of a after5 nanosecond。

 for example。Here also for example， we are defining9 second delay， for example。

 you can also define different rise and fall and I don't know minimum maximum typical all these delays。

 but these are not so important at this moment。Okay， let me share some good practice of programming。

 so it's important that we develop and use a consistent consistent naming a style。

We prefer to use multi MSP to LSP ordering for bosses， so we use a 31 for example to0， not a 0 to 31。

 this notation is actually used more or less as I said for array， not for bosses。

And we prefer to define one module per file， so that makes managing your design hierarchy much easier。

And we can use a file name that matches the module name， for example， a module is try this。

 we can have a very logged file which is try this thatt v， for example。Okay。

And we always should keep in mind that very like describes hardware， this is。

 I would say the most important note here that essentially you need to think about the hardware while you are using HDL。

 so you cannot really program HDL as the way you are， for example。

 programming with Java or C plus+ or whatever。Okay。

 so this is a summary of HL4 combinational logic as we have already seen like we have seen an overview of very luck we discuss the structure and behavioral modeling and they studied combinational logic constructs。

 but now let's see how we can define sequential logic using very luck。😊，This is。

A reminder for you that sequential circuit actually consists of combinational circuit and a storage element。

 and we know from FSM for example， that the storage element are states。😊，And we use the flipop flops。

 for example， to store the states， and then we have two combinational circuits。

 one to generate next state， which inputs from external inputs and also the core in the state。

And also we have another combinational circuit for the outputs and that combinational circuit can get input only from external input or which is the move machine or from the external input and also the current state。

😊，Sorry I missed it I message it wrong so the combinational circuit for output if it gets input only for current state that's a more machine。

 if it gets input from both states and external input is going to be the millli machine as you probably know。

😊，Okay， so we need to define blocks that have memory like flip fl latches， final steam machine。

And we know that sequential logic is state transition ined by a clock signal。

 which is like positive edge or negative edge of the clock。

 so there should be a way to define such a specification in very large。😊，嗯。So for that。

 the problem is that combinational HDL constructs that we already covered so far。

 they are not sufficient or I would say easy enough to express sequential logic actually in some cases they cannot work because some of these elected latch logic or default flow flow logic that we already covered it actually works by considering some delays in your gates while you are defining your structure or behavior in that functional simulation you are not considering any delay by default if you don't consider any delay that those circuits may not work。

So that's why I actually very like come up with new constructs in order to define， for example。

 these kind of behavior。So this always block is the block that you're going to use it a lot。

 this is a notation you have always and then at sign and then there is this sensitivity list and one statement and there's one or many actually so these statements are basically should come in the block of always。

😊，That they will be executed if this sensitivity is asserted， essentially。

So whenever the event in the sensitivity release occurs， the statement is executed。

So this is a recall for you the flip flow that we have these two lashes。

So this is the way that we define the flip flow in verylock， for example， so module flowop。

 we have input one clock and also input is actually kind of registered at this moment for。😊。

Bit input and output drag4 bit Q。So this is a notation。

 you say that always add sign and then for the sensitivity least。

 you want to make it sensitive to the positive edge of your clock。😊。

So this is a notation for positive H， you say pause H and clock， and then whenever it happens。

 Q gets the value of D。😊，Okay。And this is a notation。

 so also you cannot use assign a statement as you've seen in this。

Previous slides in the always block， so that notation should only work outside the always block the assign。

And this notation， which is。诶。Smaller smaller or equal this describes a non blocking assignment this is actually a notation for non blocking assignment we're going to actually see what is non blocking and blocking assignment later so。

😊，Here， also I want to emphasize on this definition。 So whenever you want to assign value to a。

To a signal which is in the always block， you always need to define that as rate。😊。

So signals by default are wires in very augmentation。

But if you want to assign them value in all these block， you need to define them as rig。

 but this rig is not actually does not mean register。

So the name rate does not necessarily mean that the value is the register， it could be like here。

But it does not have to be。 so we're going to see examples that we have。Actually era values here。

 but they are sthesized to combinational logic。But this is a notation that you always need to follow whenever you want to assign anything to in the always blog。

 you need to define it as vague。😊，Question。Yeah。Yes。

We also talk about asynchronous and synchronous reset in the past。

 you know that with asynchronous reset， the reset signal is sample independent of the clock and reset gets the highest priority。

And we know that this is sensitive to glitches and may have mental stability issues but。

People are usually。And people prefer asynchronous reset when they want to make it high priority essentially。

We're going to discuss about glitches and mental stability also later in our timing verification lecture。

 we can also have synchronously set that this signal is sample with respect to the clock。😊。

And these research should be active long enough to get sample at the clock edge。

Because this is going to be basically treated as similar as other inputs。

And we discuss about basically overall asynchronous and synchronous state changes in the past。

 also in our lectures。We mostly consider ST synchronous system in this course。

 but this reset can be asynchronous so in our synchronous circuits you can still have a synchronous reset also。

Okay。So this is an notation when you want to define as a synchronous reset so you have this always at a positive edge clock and negative edge reset。

 so you want to make it sensitive to the negative edge of reset。

 which is kind of definition for as synchronous reset。

And in this always below you say that if reset equals0。

 then  Q is 0 and else Q takes the value of the。So yeah。

 clock is rising edge and reset is falling edge we also have need to lose this beginning end when we have multiple lines here actually is not needed。

Because we have this if and else and if else is considered as one block。

 so you don't need to add big end， but it's good to add begin end because it makes your code better for readability is better。

Okay， so first reset is check if reset is zero Q is set to zero。

 and then this is an asynchron reset because we can enter this always block without clock。

 so if without having this positive edge of clock， if we have negative edge of research reset we just entered the always block。

And if there is notice set， then the regular assignment takes effect。

Here is an example for synchronous reset， sore in your sensitiveivities。

 you only should have a positive edge of clo and in this code you say that if reset equals0 then  Q is0。

 the other one， the other case Q takes the value of d。嗯。You can also add enable signal to your。

To your definition， so that enabled D flip flop。So if reset。

 so here is an example it a synchronous reset。You first check the reset if it's zero。

 then  Q is zero， but then you need to check the enable signal if it is enabled Q takes the value of the otherwise Q is to you know keeps the value that already have essentially。

 so there should be a memory here and that's why this is going to be sentized as a register and not a combinational circuit。

对。Question so far。Yes， why do we use the negative edge under this one？嗯。

This can be a positive edge also， I don't know the exact reason。

 usually people prefers to use negative edge I don't know the exact reason。

 but this can be also implemented the other ways。Any other question？Okay。

So another example would be Dlatch， you know that in Dlatch we are sensitive by the so whenever we are。

Basically our enabled or when our latch is in the transparent mode。

 we are moving everything in the input to the output。

So our sensitivity release is sensitive to clock and also the input。

So whenever our clock basically gets active， we need to we enter this always block。ButBaically。

 whenever we have。Exactly， we have some changes in our clock。When if it is1 or is0。

 so when your clock is1。😊，嗯。In the initial situation， you don't enter always， but it is one。

 and then you go to  zero。 So now there is a transition in your clock。

 So this sensitive list is going to be asserted。 So you're going to enter this always。

Then your clock goes to one， then you enter always again so whenever there is a transition you enter right when whenever there is a change essentially。

 but also here we are sensitive to the D also maybe your clock is in the is one。

 maybe your latch is in the transparent mode。😊，And now your input is changing。

 so you want to transparent the input to the output。

 so you need to enter this always and change the output essentially。

 so that's why we put D also in the sensitivity release here actually。Okay。

 so always add clock and D and then if clock Q takes the value of D。And in another case。

 basically Q keeps the value that already has。Okay， so this is a very quick summary。

 sequential the statements are within and always blocked。😊。

The sequentialial block is triggered with a change in the sensitivity list。😊。

And signals assigned we then always must be declared as a rate。

This is important if you don't follow it， you're going to get syntax error essentially with your with your。

 for example， Auto2。And we use non blocking assignment and we do not use a sign within the always block。

This assign as a keyboardword， essentially。Okay， so these are some also basics of always blocks。

 so we can actually have as many always blocks as needed。So you can add as many as you want。

But assignment to the same signal in different always block is not allowed， for example。

 you cannot have special here and also a special here， so that's a compileilr essentially。

 which doesn't make also sense。You want to assignment happens only in one always block。I mean。

 to every single signal。Okay， so， and also why does an always block remember。

 So we need always block to remember specifically for。Memory elements like latches or ph flops。

So here we are saying that this statement describe what happens to signal Q。

But what happens when the clock is not rising？So the value of key is preserved。

 meaning that remember， so that means basically always block remembers the value and you don't need to define it every in all different cases。

But an always block does not always remember， this is an example that for example。

 you have always a sign and these two input as sensitivity。😊。

Invent data and you' are actually defining all different。Basically a combination of the inputs。

 you are saying that if any。Is one。Result takes the negation of data。L is， the result takes the data。

So there is no ambiguity， there is no no so you're defining all the cases。

 there is not such a case that you don't know what to do so in such cases always does not need to memorize and that's why when you sitize your circuit you don't see latches or flip flows for example in such circuit and it's going to be actually your a combinational circuit。

So that's the way you can actually use always block for combinational circuits。

And always block defines combinational logic if all outputs are always continuously updated。

 so you need to mention in all the cases so there shouldn there should not be a situation that you don you don't know what to do with the output right so when you have latch or when you have leaflog you can say that okay。

I know I always know what to do I don't know when I don't have updated value。

 I just keep the current value， but in combination of circuit you don't have that option。

 you always need to assign in different values。So that's why you need to continuous the update。

Meaning that all right hand side signals should be in the sensitive least。

All these right hand so these are right hand and also this if so all these things that you are actually relying on their value。

 they all need to come in the sensitivity list of your always。

And all left hand side signals get assigned in every possible condition of ifL and case blocks。

So it is easy to make mistakes and unintentionally describe memorizing elements like latches。

 Rivado will most likely war you so make sure you check the warning messages so like Rivado for example say that when I'm sthesizingm using I'm sthesizing using latches。

 for example as a warning。😊，If you want latch， then good， but if you don't want a latch。

 then it means that you have a problem in your always statement and that warning can actually be used in order to fix the semantic of your stick。

Okay， so in always block you can actually use a lot of these if errors and cases statement。

 so a lot of these structure that you have used a lot in your programming languages。

 you can also use in all blocks。😊，So let's have some fun， we can actually。

 I'm going to show some circuits and you're going to tell me that if it is sequential or combination。

Let's start with this one， is it sequential or combination？And why。Yeah。Any thoughts？Yes。

 combination combinational y because it always triggers， I guess the is always。Yes， that's correct。

But we had two conditions。Yes， yes。So we fulfilled the first requirement。

 which is we are using always at the start， meaning that all right hand signals are in the sensitive least。

 which is good。😊，But we are not assigning out B in all different cases。

 so that's why it's actually a sequential circuit。So out A is going to be simple combinational。

 but out B actually is going to be synthesized in a latch。In this second。This one， the second one。是。

Yes， why。Oh no， no， it's not combination of data in there。Sorry。So no， it's sequential。Yeah。

 there is no other real。That's true it's sequential because the sensitivity list is not complete essentially。

 so we also need to add this enable in the sensitivity list or use at a star。😊。

Which is actually using this a sign start is a good practice whenever you want to define a combinational circuit。

Wass that easy。Oh。Good。So the always block is not always practical and nice， so here， for example。

 you want to define a multiplexer。😊，So using always， you need to， for example。

 have the essentially list and then say that if cell result gets A and A this result gets B。

While you can easily write this multipler in assign a statement。

Right so you don't have to use always use always block whenever it makes sense and whenever it helps you。

But in some cases， actually all these blockss are quite handy， for example。

 when you want to define case switch cases， for example。

Which is very useful in finite the sleep machine that we're going to see very soon。Okay。

 so in always block we have this if andLs， and they can only be used in always blocks and they always block this combination only if all rigs within the block are always assigned to a signal。

😊，And we should use the default case to make sure that we do not forget an unimmented case。

 which may otherwise result in a latch。We can also use case X a statement to be able to check for don't cares。

 so there are some that makes your basically case structure easier。And faster。

 so you can also summarize。Whenever there are some cases that you can actually combine them。

 you can use this case X notation。Okay， so let's also quickly take a look at non blocking and blocking assignments。

😊，So non blocking assignments， this is a notation and the meaning of that is that all assignments are made at the end of the block。

So whenever you see the evaluation of that assignment takes place。

 but the assignment does not take place until we get to the end of the block。😊。

So here we say that this is nonbing assignment A to basically one。So we evaluated。

 We know that we want to。You know， assign or yeah exactly assign one to a。

 but we don't execute it until we get to this end， meaning that this actually here we can see why is it important when we have this B assignment nonblocking again to a。

 this actually takes the old value or the current value of the a。

 which is not actually2 bit binary01 because this evaluation has happened but we didn't execute it。

While in the blocking assignment， this actually goes completely sequential。

 so you have this a to 2 bit binary 01 and then immediately after this blocking you have this value for a and then when you say that B takes a basically B is going to be 2 bit binary 01。

Makes sense。So why use non blocking assignment non blocking is sending allows operating on old the values and this enable easy sequential logic descriptions so in your actually in your circuit you have a lot of concurrency and that's why we usually want nonbing assignment non blocking assignment makes this a lot of concurrency because all these assignments are kind of concurrent。

They are not really sequential。While in blocking assignment。

 all these assignments are completely sequential because you're going one by one。

So that's why actually for sequential logic， we want to use this non blocking assignment。

But blocking a statement although a sequence of operation。

 which is so people that they want to you know use this slide that they have from programming languages in the very lock。

 they actually tend to use a lot of blocking assignment， which is not necessarily a bad thing。

 sometimes actually blocking assignments can help you to write faster codes。Like faster in。

Your design or time code， not necessarily in your synthesized code。😊。

But basically you can use this opportunity， but not we should be aware of the trade off。

But this is also important if the sensitivity list is correct。

 a block with non blocking statement will eventually evaluate to the same result at the same block with blocking statements。

 but this may require some additional iterations， let's elaborate with this example。😊。

So we have this block and these are the assignment， all of them are actually blocking。

And these are the value for PGS and C out， these all are initially zero。

So after executing this basically always block， sorry， if a changes to one。

 so you have a trigger in your sensitivity list， meaning that you enter this always block。

 and then you're going to evaluate all these statements。So you're going to get to these numbers。

 essentially。You can convince yourself， but essentially every statement you should go one by one。

And update all these values whenever you execute it。While in the non blocking assignment。

 you consider the same situation that a changes to1。P needs to get the value of  one。

 but this will happen at the end of this G needs to get zero。

But here is important look this S reads the old value of P， which is still zero。😊。

Because this is numbering assignment。So it's going to actually get to the value0。

And then see out also you can see that it's going to be zero。

So while at the end of this always you update values to 1000 and then you see that okay now I have aion on P so you have a change in a P so you need to enter your always block again so that's what I'm talking about iterations so now you have another iterations。

And you trigger it the again and then you evaluate。

 and then in the end you get the values that you can get by first iteration in your blocking statements。

Okay。Okay， these are good for exam question。Nothing实 say吧姐。You can't think of the like。Okay。

 so rules for signal assignment， we'd like to use always at whenever we have this at a positive edge clock。

 we tend to use non blocking assignment， so whenever in your you want your defining sequential circuit it's better to use nonbing assignment for many。

 many reasons。One of them is actually keeping the concurrency。

 another one is also the way that sthesizing tool behave when they see non blocking assignments。

We can also use this continuous assignment assigned to model simple combinational logic。

And for blocking assignments， we use them only for complicated combinational logic if we need it。

And we cannot make assignment to the same signal in more than one always block or in a continuous assignment。

 So this is no no， like because you cannot assign。A in two different hallway， this is also no， no。

 you cannot do it like this this is actually wrong in many ways because。

When you want to do this as sign， this a actually needs to be wire in the notation。

When you want to assign to a in all this blocks， this a needs to be read。This is fundamentally wrong。

 you know， you can in many ways。You cannot define a signal via and rate， essentially。Okay。

Now let's see any question by the way。Yes。The theory changeable first duration。Ting well it is not a。

Yeahやや different。继实当中。Well呃。Yeah。So the thing is that non blocking when your sensitive release is correct。

 it like at sign and star。😊，Non blocking assignment will eventually actually converge to the blocking assignment。

 but this takes。Like one sensitive value sensitive7。It's not。No but if it's not。

 if you don't get this change to enter the always block again。That means you don't need iterations。

That means actually your non blocking assignment and blocking are the same。From Get go。

 actually from in the first situation as well。I'm not sure if I understand the question correctly。

然作啊。点な。We can discuss offline moral also。Any other questions？Okay。

 now let's quickly see how we can implement finite state machine with Ver luck iss actually one of the nicest thing about Ver luck。

 I really like how to define FSMs in Ver luck。😊，So you know that each FSM consists of sequential circuit。

 which is state registers and also combinational circuits。

 which is one for next state logic and also one for output logic。

 essentially in your very code needs you need to define all these blocks。😊。

Let's say this example that we want to divide the clock frequency by three。

So you design and effort them for it。When you reset your start from this estate and then after one o'clock you go to another state。

 so in this estate you keep your for example， clock one， the output is one。😊，Then after one clock。

 you go to S1， then after another clock， you go to S2。

And then for the third clock you go back to the S0 and then you get your output again to one。

 so if you use this one as y as your new clock， you can see that you're actually dividing your clock frequency by three。

 even though we're going to see actually later in timing and verification that this is not a way so you don't need to you shouldn't mess up with the clock frequency。

This way this kind of， you know this way， so there is a actually analog logic in your circuits that they actually does these operations。

😊，Because of because since the clock latency is very important， we're going to learn about it later。

 but this is just an example that you can divide your clock frequency by three like this。😊，So。

Now we want to implement this FSM using our basically very large。

 so this is the module name divide by3 FSM。And these are input clock， resets and output queue。

 that output queue is going to be your new clock。So we know that we have three estates。

 so we can code them and code them in two bits， so we have this re1 to0 estate。

 which going be your estate registers and also you need next estate as an input to your estate essentially。

We also define three parameters， S0， S1 and S2 as these values。

 so this way you are encoding actually your estates。Okay。

So this part is also a bit actually optional， you can actually you don't need to do it。

 but if you do it like this and you talk you basically code it as S0。

 then you can make your code much more better， I mean it's more readable。So this but is optional。

So for a state register is actually so easy， you need to write this always at at sign positive age of clock and positive age of research。

This can be actually positive as reset， for example here。

 and then if reset you go to the state S zero。😊，And as you go to that state。

 which is the nextus state， so you input next state to that state。

So this part defines a state register。Question。Okay。Now you need to implement the next estate logic。

😊，So here actually switchcase is very handy， you say based on case case on a state。

 if it's S0 and excess， they should be S1。If a state is is one， nextus is2， and so on and so forth。

And make sure that you have also this default here is actually very， very important because。

We have three estates， but we are encoding three estates to2 bits。

 so there is a codingding 11 which is not related to any of these essays。

 so if you don't have this default。This can actually run into some issues when you synthesize your code。

 some meta stability or for example， some it might happen that you go to the state 11 for notice reason and you cannot get out of the state because there is no way。

But once you have this operation synthesizing tool。

 make sure that whenever your estate is 11 or whatever， next state is going to be a zero。

 so this makes your code safe。And also the outputward logic and other assign that we assign Q to state。

So basically Q should be one whenever we are in the S0， which is a more machine。

So Q equals to a state。Equal to is0 essentially。And then we need to put all these together in a code like this。

This is your module， this is your parameters and always for state register。

 this is the combinational always circuit。Sorry， always a statement for the next state logic and also this part is for output logic。

Easy， right？Good。😡，You can also continue this kind of example with our。

Favorite smiling snail example。So in that example， for example。

 we had these four states in a milli machine。You can define these parameters and then based on these state register。

 you can basically you need to assign。In all ways， if reset a state is S zero。

 otherwise a state is next。Yeah， exactly otherwise。

A state is next a state but now you also need to have always blocked for next logic so you use this switch case but it's also now it matters on the number as well so this should be always at to star and then based on the state for example S0 if number meaning that if number is one next state should be S1 otherwise I would next a state is S0 so you have if if as for all these cases。

So that's your next logic。And for the output logic， we。

Basically our snail smiles when we are in the S3 and the input is one。So a mod equals to number。

And a state should be a zero， each kind of a me type of efficacy。Yes。

And then you need to basically put all these codes together in one module， and that's all。

For our smilinging mis snake。Any question？Okay， so we learn about basic of describing sequential circuit。

 there always a statement， difference between blocking and non blocking statement and how to describe FSMs in Be luck。

😊，And that brings me to the end of。5 a。So。I like to start 5B a little bit just to give you some insight。

 but but definitely we don't have much time， so we're going to finish by four。

Can we switch to 5b very， very quickly？I just want to prepare your mind for tomorrow。Okay。Yeah楚。上。

Yes。そら。あそ。From。不难。で長は。好。Of。对。有说。It。隔看。发为。走。So。Okay， thank you， that's what's fast。Oh。い。

So for timing and verification， these are the readings you can check and also readings for next week。

 these are reminders for extra credit assignments。So what we're going to learn probably tomorrow。

 but I would just want to give you some insight is that so timing in combination circuit we want to learn。

Like how propbagation delay and contamination delay， what are these different delays。

 what are glitches？Also， we want to learn about timing in sequential circuits。

 how we make sure that our sequential circuit actually works。

 considering all these different delays and also delays in our flip flops。😊。

So that's why we're going to define this setup time and hold time。

And we determine how fast a circuit can operate。And after that。

 we're going to see how we can verify our circuit， which is the part for testing verification。😊。

So there are some trade offs in our design like for example， area。

 circuit area is proportion to the cost of device， so sometimes your constraintstrain area you want to optimize for the area。

Sometimes you want to optimize your design for speed and throughput。

 so that's why we want faster and more capable circuits。

Power and energy also are another important design points。Mobile devices， for example。

 they need to work with a limited power supply and high performance devices dissipate more than。

100 watt per centimeter square。So that's definitely， for example。

 these devices cannot be you know added or implemented on the mobile devices， for example。

Design time is also another important metric， which is designers are expensive in time and money。

So you guys are important， are expensive in time and money。And the computation will not wait for us。

 so we want to the time to market is very important and we want to minimize that time to market as much as possible。

 that's why affiliates are very exciting for us that they can reduce time to market。😊，And in the end。

 actually all this trade off depends on the basic for what you are designing。

 if you are designing variable devices， then you probably need to make sure about power so you don't want to put something your ear that's going to consume。

On there's aat， for example。If you are designing for， I don't know， for a rocket。

 you have different radardos and so on and so forth。

 so essentially you always need to know your design。

And your goal and then do your trade off based on that。So for circuit timing。

 until now we investigate logical functionality。But what about timing， how fast is a circuit？

And how can we make a circuit faster？And this is also so interesting what happens if you're on a circuit too fast。

 sometimes if you're on your circuit too fast， then your design may not work。

A design that is logically correct can still fail because of real world implementation issues。😊。

And that will bring us to combinational circuit timing。That I'm going to actually cover tomorrow。

 but that what I wanted to basically motivate you about timing that essentially if you don't consider timing your design sometimes。

A correct the functional design that you， for example。

 you have a correct through table and you quoted nicely， it may not work。

And we need to take into account a lot of different timing values。Okay， so are there any questions？

If not， then I see you tomorrow。And。

![](img/a19b516231927e201fb6ab4b83f8c1e1_5.png)