# 【计算机体系结构】普林斯顿—中英字幕 p17 16_06_motivation-for-caches -BV1ii421D7WR_p17-

![](img/d3fee2d690a23da9f0878614f26f14fa_0.png)

So now that we've talked about these different memory technologies。

Let's move on in talking about an introduction to caches and why we have caches and where this really comes from from sort of first principles perspective。

And to start off motivating caches。Let's draw the most basic memory system we can draw。

 So in our abstract computer model， we have a processor and it connects to somewhere to store our data and our instructions or our main memory。

And。嗯。You know， the， the time it takes to actually access something like our main memory can many times be much。

 much larger than our cycle time。 the latency can be much much larger。 So that D Ram I passed around。

 you know， to get to get a bite out of or to get like the first bite out of something like a modern days D Ram。

 youre basically， it's gonna be thousands of instructions。😊，If you， if you or probably run。

It's probably right around 1000 actually， in a modern day computer。 It's gotten a little bit better。

 as we'll see on the next graph for， for a funny reason， but。😊，And， and the bandwidth。

 we're gonna define as the sort of number of accesses per unit time。 So as I said。

 for the close in arrays， you can usually access them much faster and have more bandwidth through them。

 sort of by definition。But for things far away， you have to。

 to have less bandwidth kind of by definition because you probably go through some pins or some buses。

 They have to go very far away。 And then were to define the bandwidth delay product as the amount of data that can be in flight at the same time。

 And as you have sort of things farther away and more bandwidth this bandwidth delay product gets bigger because you're multiplying sort of the amount of stuff the amount of bandwidth you have times where everything can be in the pipe and you basically have a a big pipeline of serve thousands of values in flight。

So this is what I was alluding to about the， the gap happening between Dr Ram， bandwidth。

And processor performance。So。Meory technology has been sort of slowly getting faster。

And processor technology got a lot faster。The one thing that's at least not so bad anymore for is for。

 for single scale for single processor performance， we've sort of flattened out at this point。

So now Ram is getting faster。 Unfortunately， you know， this is still keep going exponentially here。

 If you sort of look at multi core， if you have multiple cores in the same chip， you know。The。

 the amount of aggregate processor performance is， is going up relative to the memory。

Performance and things get worse。So here we have a four issue。

2 gigHz superscalear X 100 nano second memory。 D Ram。 you know。

 can execute 800 instructions during the time to access that one memory reference。 And you know。

 we have things faster than 2 gigHz now。 And we also have slower memories you know。

 depending what memory system you put in It could， you know。

 somewhere roughly about about 1000 instructions。Okay， so what's。

 what's the important first order effect when we're looking at memory systems。 Well。

 size does matter as you have larger and larger memory systems， it just takes longer time。

 There's more capacitance。 You have to drive。 and you have to go physically farther。

 And you can't fundamentally fight the speed of light。

 It's gonna take you certain amount time to go a certain distance。 And if that distance is farther。

 it's gonna take you longer。So you also have sort of more fan out if you have bigger。

 bigger memory systems。 So our physical size is is important here when we're thinking about memory systems。

Okay， so let's now introduce a cache。Or idea of why， why cache is is good。

So let's look at a notion of memory hierarchy。Unlike this picture。

 where we had a processor connected to all of memory in the system。

We're now going to put some intermediary levels。So we have a processor。And we're going to put small。

 fast memories here。And we're hopefully going to try to hit the access these small and fast memories instead of accessing this big。

 slow Dr Ram。Let's look at the capacity here。Registers。

So your general purpose registers or registers that hold。

 let's say your program counter specialized registers in your processor has very small capacity。

S Ram has more capacity。 The E Ram has even more capacity。

 And it's sort of double less thans there to accentuate that you can fit a lot more in the same space。

Though the latency follows that same。Hiererarchy there。

An important other thing to think about when you're building memory hierarchies is that on chip memory bandwidth is typically a lot higher than off chip memory bandwidth。

 If you're on chip， you can run wires there。 But the second you have to go off chip。

 You have to go out the pins of the chip。You're gonna be limited。

 And what this really boils down to is the pins or balls or solder columns。 So modern day chips。

 we don't actually have pins on them anymore。 Instead， we have ball grid array。

 what is little tiny solder balls the size of those。

 The pitch of those is still much larger than the wire on chip。

 A wire on chip is so much smaller than the solder ball。

 which or modern day actually like something like here， X 86 core I 5 or something like that。

 or Intel corei 5， actually has it's called land grid array， where we have a little array of little。

They're pads， little metal pads on the bottom of the chip。

 And then there's these little pins are actually located in the socket on little。

 they're call them pogo sticks。 but they're basically little pieces of metal on springs。

 And you put the chip in。 And then the little pogo stick hits the piece of metal。

 And that's the contact。 on older chips， you actually had the pins on there on the chip itself。

 and you sort of put it into a big socket And in the middle is ball grid array。 But anyway。

 all those things， the connection technology to get off the chip is much larger。

 So you can fit fewer of them in the same area than if you were to wire on chip。

 And that's really this insight here that on chip bandwidth is a lot larger than off chip bandwidth。

And because of this， you're gonna want to think about putting。Small， fast memories close by on chip。

We can store， store data。 Okay， so what happens in。This memory hierarchy。When we go to access data。

If the data is in our fast memory here， we're going to go here， hit in our liliency。

 S Rammble saying， and come back。If data is not in the fast memory。

 we have to go all the way out to our DRA and come back。And。Memory hierarchies。Work only if。

You're going to find useful data here。So if you go build a small， fast memory close by。

But you never find any information in there that you need。Why did you build this structure。

 You're just sort of doing extra work and burning extra power。

And this is one of the key insights of why we have caches。Or what a cache is。

 is that when we go to build a memory hierarchy like this and we introduce something like a cache。

By finding the data nearby。That's going to be faster to access。

We need to find the data there with high probability。Otherwise。

 we should just not built it and just gone out to main memory all the time。

 We were just wasting everyone's time and area and cost。So memory hierarchies only work if you have。

 your fast memory actually is， is useful。Okay， so let's look at different memory axis patterns。

And try to come up with。A couple different techniques that we can exploit to。

Increaseed the probability that the data we're going to need is in that small， fast memory。So。

 we are。Interesting graph here。 And I want to explain what this is。

 And we we're to look at a a toy example first。 and then we're gonna look at a memory trace memory reference trace from a real operating system with a real program running under it。

 But let's start off with some some examples here。😊，We have time on the horizontal axis。

 and we have address。On the vertical axis。 And it's something like your machine。

 let's say it has 4 GB of Ram。 We actually have sort of a line across here for every single address in the machine。

 And then we have time。 And as the program executes and goes and accesses different pieces of memory。

 we're gonna put a dot on this graph。So let's start off by looking at something like an instruction to fetch。

Typically， programs will execute in order。 They'll execute the first instruction。

 and the next instruction， and the third instruction at the address is sort of monoettonically increasing unless you hit a branch。

So let's， let's take a look at。Some instruction fetches， we start off by executing。Some code。

And then we're going to actually execute a loop here。So when we're in the loop。

 we're gonna be executing the same piece of code over and over again。

 And if you look at that from an address perspective， we start off not in the loop。

 So we have some address here， some different address。 and we execute these three addresses。

 and we execute those three addresses again and those three addresses again。

 those three addresses again。 we keep fetching。Those three dresses over and over again from our memory system。

 And at some point， we exit the loop and go execute something else。Okay。There's a pattern there。 Now。

 we're going to think about whether we can exploit that pattern in a second。Next。

 let's talk about accessing the stack。So computer programs typically have stacks。

 This is where you either spill or fill registers for。 Typically， you also use it to pass arguments。

And you spill and fill， most modern compilers will do that when you make a function call or return from a function call。

And the argument passing is around function calls。 Also， you'll put arguments that。

 the later functions need on， on the stack。 and then you go execute that。Alternatively。

 you can store the arguments and registers， but in something like X 86 we say you're going to put arguments onto the stack and you also put local variables onto the stack。

BecauseBecause it gives you a convenient place to put it。

So let's take a look at what happens when you go to do a subrtine call。When a summer team call。

 the stack is at one address。 The stack pointer is somewhere here。And when you go do a subr call。

 you're gonna to push all of your registers onto the stack。 So you're going to put something here。

 put something here， put something here， put here。 in the stack pointer is going。Logically increase。

And then once you're in the function that you called， you're going want to access the arguments。

And those are usually very close together。 They're all right next to the other on the stack。

 Or you might have to go access the argument over and over again。You know， this is。

 if you don't have enough registers like our first lecture。

 we looked at a stack based architecture and a stack based architecture， we had to actually。

Push onto our stack the same value multiple times。 It's pretty common to reuse the same local variable or reuse the same argument because because you don't have enough registers and youre go load that data from your stack over and over again。

 So it's pretty common to access very close together on the stack。

 maybe probably the same within a cache line or access the data very close by。

 And then when you're done， you return from the subroutine And you're going to pop all the data off the stack。

So time increasing this way。 So you're gonna。Remove in reverse order。Okay。

 let's look at some data aes。The one I wanted to focus on here is actually vector aes。

So what's a vector axis。 Well， this is something that can array and arrays。 A lot of times。

 you'll be reading the first word， or the first byte。

 then read the next byte and then you read the next byte。

 Then you're doing some operation across all of it。 So let's say we're taking a matrix addition。

 We have one matrix。 and we're adding it to another matrix。 and there。Single dimensional matrices。🤧嗯。

You're actually going to be reading different addresses。

 but they're gonna be in some pattern and they're gonna be sort of close by。 Now。

 if you're accessing， let's say every fourth element in an array。This distance here， we get larger。

 The， the address distance is going get larger and your access patterns are going get a little bit farther apart。

And scar values。These are sort of。Single1 values。 So a good example here is。

 let's say this array that we're doing here is we're trying to take an array。

 instead of add two arrays together， we're going take one array。

 and we're gonna add 5 to every single or some variable X， which has。

 willll say5 in it to every single element of the array。So what your machine would。

 your processor would do is it would first load the thing you're gonna be adding to。

 So the the data from the matrix and then add and then load from the scourour value X from main memory。

 Do the ad and do a store。Then you're gonna load to the next location of the vector， load the file。

 load the X， do the ad， put it back and continue that on。Okay， so can we， can we try to exploit。

Different。Types of locality。 And this slide is really important to grasp what's going on in caches。

 This is probably the most important slide in in today's lecture is to。

 to grasp what's going on here with the different patterns we're seeing and how do we exploit these patterns。

Okay， so there's two types of patterns I want to talk about。

And your standard cache system is going to exploit these two patterns。 But let's， first of all。

 look at。them individually。And we'll be able to see the patterns。呃。Here。

First one we're going to talk about is。Temporal locality。Tempor locality。

Is this notion that if you access a piece of data。You're likely to access that piece of data again in the not too distant future。

 So it might be useful to keep that data nearby。So tempo will Cal say again， is if if。

 a location is referenced， it is likely to be referenced again in a short period of time。

So let's try to identify that in these diagrams so far。Okay， well， I see that a few places。

These argument access， we access some value。 We're gonna access that value again pretty soon then again。

 pretty soon and again pretty soon and again pretty soon。

 And we are basically accessing something with high temporal locality。Likewise。

 these scalar values here， these scalar axis we're accessing again and again and again。

 So this is exact same address。 And the time between one axis to the next axis is pretty。

 pretty close by。Okay， now。Let's look at this and see。

 are there other interesting access patterns here？Well。Interestingly， on a stack。

When we go to access a value and we're pushing our values onto the stack。It's very common。

To access a value， at， say， address。1000， and then go access 1000 plus 4，100 plus 8。1000 plus 12。

1000 plus 16。And access all of the nearby values。So what are we gonna call that。 Is that。

 is that a common pattern。 Well， yeah， it's， it's pretty common。 And we see that here。

 we see it in loops for instructions。 We're actually accessing one instruction。

 It's very common for us to go access later instructions very close by， packed。

 let's say next to it this is pretty common that you just fall through in your code。

 So we're gonna define this and call this spatial locality。

And spatial locality says if a location is referenced。

It is likely that locations nearby it are going to be referenced in the near future。

And these are both just heuristics。 There's nothing magical about these。

 These are just heuristics of how programs happen to work out。 And。

 but we're gonna to build systems that try to leverage these two heuristics or these two characteristics。

 rather as two types of locality to improve the performance of our processors or be able to use those small little ras that we're going to put in our memory hierarchy and actually store useful data in them。

😊，I also wanted to sort of point out that you can have both spatial and temporal locality mixed together。

So if we look at something like。Running a program which has lots of loops。We have spatial locality。

Because we're executing instructions nearby。 But we also have temporal locality here。

 because we're reusing all this data again and again and again in a short period of time。

 So in the near future， we are accessing sort of the same， same data over and over again。

 even though it's not the exact same piece of data as it's nearby。

 So we're sort of seeing both spatial and temporal locality exhibited there。Okay。

 so let's look finally at a real memory reference pattern， or real memory reference trace。

 And this has the same aes of what we saw before。 We have time。😊，And there's one dot per axis。

And then we have memory addresses。 I don't know what the unit on the vertical is， it's probably not。

It's probably in like thousands or millions or something like that。

And this is from a study that some people at IBM did many years ago。 And。

 but we're going to look at this and see。Different patterns show up here。

So the first thing I want to circle here is spatial locality。So， we see that。Along this line here。

 we access the first piece of data at， let's say。This address。

 and we then go on and access all of the data subsequently。 So this is。

 as if we were like reading an array。 We just read all the values in the array。

 So we have spatial locality that because we went accessed element  one in the array， theres。

High probability that we're going to go access。Other data values which are nearby in that array。

 in a nearby time。Let's take a look at temporal locality。

 So horizontal lines here are temporal locality。 And we can see that this program is accessing this value over and over again。

Or at least value is very close by。 It's hard to tell on this resolution。

 But this is temporal locality that we're actuallying the same values or or mostly the same values over and over and over again。

And then finally， we can see both temporal and spatial locality in these little blocks here。

 We can see that we're accessing similar sorts of addresses。😊，Which is going to be spatial locality。

 And we're doing it all within a short period of time。 So were。

 we're seeing temporal locality of reference。And cashs。Can exploit both of these。

Cashs are going to exploit。Temporal locality。By keeping data that gets used and reused many。

 many times。Nearby。So when you see accesses which are temporarily close by or temporal spaced。

 So in time， our space nearby， what's going happen is a cache。

Is going to sit somewhere here before you get to a main memory system。

 And when you go to access a value， it's going to memorize that and keep that value nearby。

 So if you go to access it again in time。 And if your program exhibits temporal locality。

 that data value will be close by and you won't have to go out to the big slow Ram。And。

Css can exploit spatial locality。 And the way caches go about exploit spatial locality is that when you go to access a particular piece of data。

 your cache is going to pull in。Data around that piece of data。

And we'll talk more about this next time how， how that works。 But we're gonna segment。

Data into what we call cache blocks or cache lines。And that's typically。

Those those cachebox or cache lines are aligned。 and when you go to access a piece of data。

 it might be somewhere at the beginning or at the end， but or might be in the middle。

 you pull in all the data around that。 and the heuristic here is that if you access some piece of data。

 let's say you only go access the first byte in a cache line。

 you're likely to go access other bytes in a block。 So multiple pieces of data around that。

 So we're able to exploit spatial locality here。

![](img/d3fee2d690a23da9f0878614f26f14fa_2.png)

![](img/d3fee2d690a23da9f0878614f26f14fa_3.png)

![](img/d3fee2d690a23da9f0878614f26f14fa_4.png)