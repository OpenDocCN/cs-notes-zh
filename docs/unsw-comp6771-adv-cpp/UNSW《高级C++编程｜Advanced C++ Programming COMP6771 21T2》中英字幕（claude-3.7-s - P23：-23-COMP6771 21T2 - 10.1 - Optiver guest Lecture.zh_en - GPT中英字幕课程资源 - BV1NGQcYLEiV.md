# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P23：-23-COMP6771 21T2 - 10.1 - Optiver guest Lecture.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

うん。Hi everyone， welcomelcome to Bein of week 10 as I mentioned last week and throughout the term one of the more exciting parts of this course is that we get to have a guest lecture from Otiva this is something we're doing for a while it's very nice for Rotva to support this course and the kind of work you do in the course we're going to get stuck into it pretty quickly。

From Optiva we have Greg Saunders Saunders That's right And Christina Barr who will kind of be taking over for you I'll just be hiding away in the corner here while they they get to enlighten you with some interesting knowledge and Christina will be kind of looking at the YouTube chat so I'm aware you guys can't interact with the zoom so if you kind of have questions and stuff particularly towards the end feel free to just you know write it in the YouTube chat and whether we answer them at the end or anything else we'll leave that to。

Our guest today， other than that， I'll， I'll let you get going， great。All right， thank you。



![](img/8f5e62952afed07dd4f92f8d4c5921f6_1.png)

LetSee if I can get my presentation working here， Okay， great。

So my name is Greg and this presentation is about low latency development at Octiva。

So as Hayden has already mentioned， we have Christina from our recruitment team on the line here today and then me I'm Greg。

 I'm our head of IT education in our Asia Pacific office。'Been with Octava for about five years。

 five and a half years now， actually coming up on six years now。

 started off as a developer and moved into IT education about three years ago。

So what I want to do quickly today is firstly， I'll just do a bit of an introduction to Otver for those few of you who haven't already heard of us。

Then I'll do the bulk of the talk on low latency development and then at the end I'll talk a little bit about the opportunities we have at Otima。

And hopefully there'll be some time right at the end for questions。So let's dive in。Sir。

What is an ocivva？SoOctaver is a combination of two Dutch words， OpI， which is the financial option。

 which you may have heard of and Verhandelah， which is a person involved in wholesale trade。

 so option trader， so that's basically where whereoctus came from。Octaver is a market maker。

 so what that means is that we provide something called liquidity into the market to help traders trade when they want to and at reasonable prices。

So it's about estimating the price of a financial product like an option right now。

 not what it will be in the future， but what it should be right now。

 and then using that information we want to offer a lower price than anyone else is offering to buyers and we want to offer a higher price than anyone else is offering to sellers。

And by doing that， we make the market more liquid and we provide better prices into the market。

 which makes it easier and less costly for market participants to trade。

So how does it work Well in a nutshell， basically what happens is that information about what's happening。

 what traders are doing flows to us from the exchange like the ASX although we don't currently trade on the Australian market。

 but ASX is an example of an exchange which you might have heard of。

And then our auto traders use that information to estimate those prices and determine if we wish to execute any order operation so that is either place an order or amend an order or cancel an order。

If we do wish to do one or more of those order operations。

 then we send those operations to the exchange and then we wait for more information from the exchange and repeat the whole process。

So that's in a nutshell how it works。Why are we here today why are we speaking to you Well we are very proud sponsors of the advanced C++ Program course at UNSW and the reason for that is because at Octava we build a world class training platform and most of it is done in C++ so our developers at Otva have to design。

 develop and maintain their own systems again live C++。

 they have to choose the right algorithms and data structures for their systems。

 they have to optimize those systems for low latency。

 they have to employ it up todate and best industry practice。And this course Com6771。

 supports all of those skills， and so we are enthusiastic sponsors and we provide a $500 prize for the best performance in this course each year。

All right， so now let's talk about low latency development。

So one important kind of information that the exchange sends to us is something called the order book and there's an example of an order book on your screen right now。

So the order book contains the prices at which traders are willing to trade and the volumes or the amount of shares or the number of lots that those traders are willing to trade at each of those price level so in the order book that you see on the screen we can see that at 122。

56， there is interest in selling 10 lots of whatever this instrument might be。Excuse me。

When we receive this order book from the exchange， we want to respond to that as quickly as possible。

😔，So that is we want to respond to that information or the event of receiving that information with minimal latency。

So we're going to use this concept of an order book as the basis for our exercise in reducing latency in this lecture。

 so how can we do that？🎼Well unfortunately there's no silver bullets for reducing latency。

 there's no quick and easy path to doing that， but there are some golden rules and in a nutshell they are firstly measure it before you fix it if you don't measure before you fix something chances are you'll end up changing the wrong thing the thing that isn't a problem and the thing that is a problem will go unfixed so measure first。

Avoid premature optimization， don't try to optimize things too soon before you really understand what the actual performance characteristics of your system are。

Understand the problem that you're trying to solve。

 you can't just take a superficial level of understanding of a problem and produce the best possible solution。

 you have to really understand the problem in depth in order to produce the best and usually fastest solution。

You have to know the available tools at your disposal and we're going to look at a few of them in this lecture and lastly you have to be aware of the characteristics of your hardware so that you understand why your system performs the way that it does。

So let's try and apply some of those rules to this problem of responding to these order book information from the exchange with minimal latency。

So the first thing you're going to want to do when you're responding to events。

Is you're going to want to identify something we call the hot path。

 that is the code that actually gets executed when the event occurs。

So the code that doesn't get executed when the event occurs is irrelevant。

 right it's only the code that gets executed when the event occurs that really matters and so you have to identify what that is。

So here's a very simple Aud book class。That we might be using to represent our orderbook and let's just say for the purpose of this exercise tonight that the get volume method is part of the hot path for these order book events that we want to respond to。

So we're going to try and reduce the latency of the get volume method by making it as fast as possible。

So。Here's my first attempt at producing a get volume method。

That we might use so you can see I'm using a dictionary to map the prices to the amount of volume availability to those prices and our get volume method takes in a price。

 searches through that map for the price and if it finds it returns the volume associated with that price or otherwise returns zero。

 seems like a pretty decent solution as a first attempt。

Now you might be thinking why on earth am I representing prices using strings and the answer is that basically there are still exchanges。

 functioning today that use ASCI fields in their protocols to represent things like price because of things like the number of decimal places is an issue and you want to be accurate to end decimal places and if you use a floating point representation you might not be able to give that level of accuracy。

So we're using strings for our prices。And we're going to use a map to tell us what the amount of volume is at any given price level。

Okay， so remember that first golden rule was measure before you fixix anything。

 so let's do that and I'm going to be using Google Benchmark to do the measuring。

So it's available on GitHub， you can go and fetch it yourself if you want to use it。

 it's a lot like Google test if you've ever used Google test to do your unit testing and in fact it uses Google test under the hood。

And you can see an example of a benchmark written using the Google benchmarkchmark framework there on your screen right now。

 so what it's doing is it's basically repeatedly getting a price。

 a price that we know exists in the map。And it's calling get volume for that price now it's obviously not doing anything with the result。

 but that benchmark do not optimize line is just telling the compiler not to discard the call the book dash gett volume。

Even though we're not actually using it so that the call to bookarrow get volume doesn't get optimized away。

So that's going to repeatedly call get volume a lot of times and it's going to measure how long it takes to run G volume and then it's going to tell us how long that takes now we could write a similar benchmark a very similar benchmark for that that would also test for prices which aren't in the map prices which don't exist so we can see how long it takes if the prices not in the order book。

So let's see what the output of it looks like， there it is。

So that's what the output of Google benchmarkch looks like and it's telling us that the existing price level benchmark took around 958 nanoseconds of time to run 953 of thosecon of 958 nanoseds were spent actually all in the CPU and it ran approximately 700。

000 iterations of that benchmark， and then we see slightly lower numbers than the non-existing price level。

Okay， great， so now we know how long our get volume method is taking。

 so we've got a baseline that we can use to see if we're actually making things any faster as we make some improvements。

Now the first tool I want to introduce you to， if you haven't seen it already is a tool called Belgrind。

 now Valelgrind was originally a tool for basically debugging memory allocations。

On your program and it sort of evolved into more of a framework for analysis tools and one of the tools is called call grind and what it produces for us is a visualization of the call graph and you can actually see that visualization on the right。

Excuse me， the callalG tool actually produces a file and then there's a tool called KKgri。

 which is a graphical user interface which can load up one of these files produced by callalgri and then give you this nice graphical representation of what's going on。

So what can we see from the call chart or the call graph on the right hand side？Well。

 what we can see is that the 85% of the time that get volume spends running。

 it is spending in the find method of the MA class。And if we drill a little further into that。

Basically， almost the entirety of that time is spent in the find method of a class called_ RB underscore tree。

Whi might be a little obscure to you， but in case you can't guess it's a red black tree， right。

 it's a self balancing tree that is the underlying data structure for a fitted map。

So our get volume method is spending the overwhelming majority of its time searching through a red black tree。

All right， so。The next thing we're going to do is we're going to say。

 are we using the right data structure for the problem at hand？

So this is sort of a high level view of what a red black tree looks like and what it might look like for our order book and so you can see the various prices in each node there。

So when you search the red back tree， of course， it's going to start at the root node of the tree and then it's going to work down the tree left or right until it finds the appropriate node。

Excuse me， and as I'm sure you're all aware， that's going to take logarithmic time。

And that might not be what you are expecting， you might have been expecting a st map to have constant lookup time on average or to one look up time on average。

But in fact， cied map does not have constant lookup tone on average。

 cied map is implemented using a tree。嗯。It's not a hash table and in this use case what we really want is a hash table。

 we want that order one lookup time， so what we should be using is st unaued map。

And so here I've changed my get volume method well in fact I haven't changed the get volume method at all all I've actually done is I've changed the Audible class from using st map to st unaudered map and now we're going to see if that makes any difference to the performance of our get volume method and if it does make a difference how much of a difference does it make so let's。

Run our benchmark again and oh lo and behold it now takes 415 nanoseconds for the existing price level and about 290 for the nine existing price level so suddenly things are a lot better。

That's particularly good news let's look at that in a chart just because it looks kind of szzy and you can see that just by changing the map to an unordered map。

 we've actually cut the running time of the Get volume method better than in half。

 it's actually better than half what it used to be。So great news。

 we've really made some improvement there。All right， so let's see if we can do even better than math。

So let's if I use the Val core grindin tool again and produce the call graph for the new get volume that uses an unaudered map rather than a student map。

Here is the co graph。And for that new version。Now we can see that it is spending around a little over half of its time now searching that unaudered map。

 so the majority of the time is still searching the map and we'll get to optimizing that in just a minute。

But if we look over on the left hand side of the co graph there。Actually。

 what it's doing is it's spending around 11% of its time in the string deor and it's spending about 15% of its time in the string constructor。

So it's spending an awful lot of time creating and destroying strings。😔，Now， why might this be？😔。

Well， the answer is that every time you create a string。

You basically do a memory allocation and unfortunately the screen size isn't big enough here。

 but if you actually scroll down on the call graph here you would actually see it ends up in a call to malloc or free so actually it's a significant amount of the time that it's spending in this string constructor and string deor is just doing memory management that's all that it's doing so the total amount of time that it's spending there is about 25% of its time just managing those strings。

So what can we do about that？Well， what we want to do is we want to avoid those allocations。😊。

And the way that we can do that is we can modify our data structure again and so now you can see down the bottom of the screen here I've changed my unaudered map。

From mapping from a string to a long， so now it's going to map from a string view to a long。

And that's going to mean that when we search the map， we don't need to create a string。

 we just need to give it a string view， which is exactly what we already have and it will be able to search for that string view without constructing a whole new string。

Now in order to have the map from string views to lungs。

 we of course need to store the string somewhere， string views don't store the underlying string themselves。

 there are very lightweight data structure as I'm sure you're aware that doesn't actually store the underlying data that underlying data has to be stored elsewhere。

 so I've added a vector of strings to our data structure which stores the underlying strings。

But the map is now from string view to onsside long and so when we call the fine method。

 we don't have to construct a string and we're going to avoid those costly calls to the string constructor and string deor。

So let's take a look and lo and behold， by making that change。

 we have cut the time down now to 243 nanoseconds。For the existing priceol and 191 for the non existing priceol。

好きですね。All right， so there it is in chart form， we're now down to roughly a quarter of the original running time。

So this is pretty good， we haven't even really made any changes or very few changes to the get volume method itself。

 we've just changed the underlying data structure and we've ensured that we don't do anything silly like creating a string when we look up that data structure。

So here's the call graph of the get volume method now， and as you can see。

 it's gotten rid of all that string instructor， string deor nonsense。

So now it's spending roughly 80% of its time searching the unordered map。

And around about 8% of its time just computing the。And iterator for the unaudered map。Now。

 if we drill into the code， which is searching the map。

You can see that there are three parts to what it's doing。Firstly， it's hashing the string。

So that's taking roughly 25% of the time to search the unordered map。

Then it's finding where the appropriate bucket is in the hash table for the entry that we're concerned about and lastly it's searching through that bucket。

To determine whether the node we're searching for is in fact there and return the value associated with that node。

So that's the three things that it's doing。All right。

 so the next thing I want to talk about is utilizing the cache。😔。

So just in case you don't know and probably as know third year advanced C++ programs as you do know。

 but just in case you don't， modern CPUUs employ casess to mitigate the cost of transferring data to and from memory。

 which is a relatively expensive operation in CPU terms。

And when data is transferred between the memory of the computer and the cache。

 it's transferred in blocks， which are called case lines。And typically。

 these blocks are around about 64 bytes in。And so what that means is if you look up， say。

 a four byte value， it's actually fetching 64 bytes from memory into the cache。

 so it's including a number of bytes， either before or after or both the four bytes that you're really interested in。

And what that means is， if you think about it， is that if you've got a data structure where all of the information in their data structure is stored close together in memory。

🎼Then going you're going to benefit more from the cache than if you're using a data structure where things are relatively far away from each other in memory。

So if you think of a data structure like a vector， a vector is just a stream of bys and so everything is relatively close together in a vector。

 so vector is a good choice if you want to take advantage of the catch。Unfortunately。

 maps are not such a great choice if you want to take advantage of the case。The table。

 the hash table itself is stored in contiguous memory， so the hash table makes good use of the cache。

But the individual nodes of the hash table within each bucket are stored in different places in memory。

 and therefore they don't make good use or they don't take advantage of the case as much as we might like them to。

Excuse me。So what we need is a data structure that's going to take or make good use of the cache。

So something like a vector would be good。And one thing that we can do in this particular instance is we can use something called a circular buffer。

 so a circular buffer is just a say vector or an array。

Where we utilize entries in the array and if we need to sort of go off the end。

 then we just go back to the beginning of the circular buffer。

And if we make our circular buffer significantly larger than the number of prices that we need。

 then we can store those prices in our circular buffer。

 they're going to be contiguous or at least close together in memory and。

We'll be able to take advantage of occasion this way。

So what does that look like in code well here in use？嗯。So now I don't have a map anymore。

 as you can see at the bottom of the screen I have a vector of longs。

 those longs are the volume at each price level。And then the way I use that buffer。

Is I first convert the price from a string into an integer？

And then I basically take the mod or the remainder of the division of that price compared to the size of the buffer and that tells me what entry it's going to be in the buffer and then the lookup is going to be much。

 much faster。Now。Unfortunately the way that this works。

 the conversion of the string to an integer is roughly as expensive as hashing of the hash table is right so in terms of orders of magnitude it's around about as expensive as hashing is。

So it doesn't save us the costs of hashing but what it does do is it does take better advantage of the cache and therefore we should see a reduction in running time because it's utilizing the cache much more effectively so let's see what happens when we run our little benchmark and there it is low and behold we have。

Cut the running time again down to 136 nanoseconds or 132 for non existingist price levels。Okay。

 so that's utilizing the case once again gives us yet another performance advantage and here it is in graphph form and we're now down to roughly 15 odd percent of our original runtime to run our get volume method。

 so we've really made some significant improvement。Okay。

 now the last thing I want to look at is actually optimizing CPU instructions。

 this is really the sort of last level that you could possibly get to in terms of trying to optimize your algorithm。

If you're at this level， you really are talking about shaving tiny amounts of time off your runtime。

 which can be a big difference in a company like Octava。

 so let's take a look and see how we might do that。

So in order to understand the CPU instruction running time of a method like get volume。

 we need a profiler and on Linux， there's a tool called Perf。

Which is a profiler which allows us to measure the running time of specific instructions。Oh。

Excuse me again， and the way that it does that is it uses something called hardware performance counters。

 which are a feature of modern CPUs。Where the CPU measures every time or counts every time a certain kind of event occurs。

 so for example， it can count cache misses or cache hits or things like that。

 crop cycles and that sort of thing。And the PEf tool uses these performance counters to help us understand how long it's taking to run machine code instruction of our get volume method so I've shown an example there of how you would use the PEf tool firstly you run Perf record on your benchmark code and that produces a file and then you can use a tool like Perf annotate that will actually basically show you each instruction of your get volume method and how long the approximately it was taking to execute that instruction so let's take a look at the output of that。

Now I've。Excluded from the output， the section of code concerning the call to STR toD and the calculation of conversion of the string to the unf law。

And so we're just looking here at that second line of the get volume method， the return end volumes。

With the index being the price model of volume size。

And what we can see here is that there's one particular instruction at B903 which is taking 39。

48% of the time that the CPU spends in the get volume function so that's excluding the functions that get volume calls。

 so actually the majority of the time that we wont get volume。

 it's spending converting that string to an integer。

 but in terms of the time it spends actually inside the get volume function。

 it's around 40% in that one instruction， B903 which is a move instruction。Now if if you're like me。

 you might be scratching your head going how can a move instruction be taking so long well the answer is that the way these profiling tools work。

Is that they're trying to attribute the time spent in the function to a particular instruction。

 but because of the way modern CPUs work， they can actually be executing multiple instructions。

At a time and not necessarily in the correct order that they were issued in。

And so sometimes it actually can attribute the performance to the wrong instruction and in fact that's exactly what's happened here。

 the real problem is the div instruction at B900。That's the one that's really causing us a problem and of course the div instruction is necessary for us to calculate the modD operator。

 which is used in our price mod and volume do size expression。

And that's where it's spending the majority of its time in terms of what's happening inside the get volume function。

So what could we do about that if we needed to optimize to an even greater extent than we already have？

Well。If we。Mder changed to our code and we ensured that the vector， the circular buffer。

Always had a size that was a power of two so you know 16384 or 32，768 or you know 65。

536 some power of two if we always made sure that our circular buffer was a power of two in size then what we could do is we could replace that mod expression with a simple binary and expression which I've got on the screen now so the binary and of the price with the size of the the buffer minus1 will give us as an integer。

 the remainder after division by that size。But it only works if the size of the buffer is。

A multiple of two or power of two。So if we do that。

 then we rerun PerF tool then you can see what the annotated output looks like and now the important instruction is the and instruction at B and F8 and it's now taking just1% of the time inside that get volume function。

So we've significantly sped up the get volume code itself。

 but unfortunately in this case we haven't sped up the code that converts the string to an integer。

 which is responsible for the majority of the runtime for this function。

 so it's actually not going to make much difference to the runtime for get volume if we make this change。

 which is an example of not doing premature optimization because we'd be fixing the wrong thing。Okay。

 so that's sort of my example of how we can reduce the latency of a function using tools like Bellgrime。

 Corgo and Perth and Google Benchmark。And choosing the right data structure and so on and so forth so now what I'd like to talk a little bit about before I finish up and give you a chance to ask questions is some opportunities that are available at Ocva for software developers like yourselves。

So。Basically， we hire graduates and interns。Freshly out of university or in terms of graduates。

 you can be less than anywhere up to four years of experience in industry and apply for one of our graduate roles。

For our graduates， the package for graduates starting in 2022 is 200k per annum plus perks so that's our RE package and in terms of the roles that are currently that you can currently apply for we have trade or graduate roles。

 market risk analyst roles and software developer roles now for interns。

 intern roles are available for mostly for penultimate year students but if you're prepinultimate and you have an interesting resume you can still apply and we'll see what we can do so I would encourage you to take a look at our website which I'll give the link for in a minute。

And。Apply for these roles and we'll see what we can do for you so in terms of our interns the package is 100 k per annum plus super but it's only a 12 week program so you're getting roughly three months of that。

Plus perks of course， and we currently have trading and software developer in turn roles available for you to apply for。

And in terms of eligibility， you must be an Australian or New Zealand citizen or an Australian permanent resident or someone who is able to secure working rights through the temporary graduate or skilled independent visasa programs。

So if you're one of those eligible people， I encourage you to go to our website and apply。

So just looking at the roles that we have available， so there's sort of two parts of the business。

 the traders who are the ones that actually control our trading systems and essentially cause them to make trades and control the way that they make trades。

And within that sort of broad department， we have traders who actually use our trading platform to trade。

 we have researchers whose job it is to make our systems better。

 identify opportunities in the market help us better our solutions。

 and risk managers who help us manage our risk， which is of course a huge deal for a market maker like Octava。

 we do take on a fair amount of risk in the trading that we do。

 and so we need to make sure that we keep that risk within limits so that we don't cause any disasters。

In terms of what we're looking for for those roles。For tradeer， you know。

 you're looking for quantitative skills， mathematics， science， engineering， that sort of thing。

You need to be able to sort of think outside the box， you really need a drive to succeed。

 you need to be able to push yourself in that role and it's generally pretty beneficial if you have an interest in trading and financial markets。

Coing experience is not so important for that role， although if you do have it。

 it's certainly beneficial。In terms of research roles， you need to be motivated。

 you need to be able to communicate well， you need to be able to solve problems again those quantitative skills are important and you don't need coding skills but certainly they're a plus and then for risk managers。

You need to be a good communicator， some programming。

 but not necessarily in a language like C++ and an interest in financial markets。

In terms of technology roles， which might be more appropriate for this audience。

 of course we have software developer roles， they're the people that design。

 develop and maintain our trading system。As I said earlier。

 it's mostly in C+ possible although we do do some sea sharp and Python。

We also have production engineering roles， their job is to optimize and maintain our trading platform。

 make sure that we're able to deploy our software safely， monitor it appropriately。

 and then control it appropriately those sorts of things。And we also have roles for FPG developers。

 if you haven't heard of what FPGs are their field programm mobile gateatorways。

 it's kind of like a CPU and a computer except that instead of programming it with a sequence of instructions。

 you program it with a logic circuit， a combination of land and aa a not gates。

And what they are able to do with FPGAs is they're able to essentially execute a very simple program。

 but much， much faster than a computer could do it。And we use FPGAs our work as well。

So in terms of what we're looking for。Obviously an interest in low latency development and high performance systems is vital for us software development roles。

 personal projects where you can show us work that you've done are always helpful。

 the ability to collaborate with others and again of course that experience with either plus+ CSp or Java so you don't have to have done C++ although again this audience will have done it to apply does of our production engineering roles。

 they do do programming so for programming skills are important but they need to be able to work with both our developers and our trailer so good communication skills。

 good collaboration skills， ability to work with different operating systems and so on and then of course our RPPGA developers some experience with VHDL or verylo would be very important and understanding of network protocols and how networks work under the hood very useful and so on。

So I said earlier， I give you the website。So if you're interested in any of our roles。

 then I would encourage you to visit this website and from there you can see a little bit more about Otiva and there are links at the bottom that will take you directly to the roles that we have available at the moment and you can apply for those roles right there on the website so strongly encourage you to have a look at that website。

Okay， that's all the material I have for tonight。So I guess I'll stop at this point and open it up for questions。

😔，So I think there were a couple of questions in the chat。

But if I suppose Greg didn't cover the answer or didn't cover what you needed him to answer。

 just kind of pop your question back in the chat and can we can answer those for you。I think。

I think one question Greg， that came up was， what version of C++ do you guys predominantly use？

So I think the first one Greg is what version of C++。Rice， yes。Great question。😊。

So one of the issues that we have at a company like Octaber is that we have to have a very stable platform。

So we you know we can't just upgrade the operating system or upgrade the compiler and expect everything to just work。

 it's too risky for us to do that， so we tend to be a little bit slower in terms of updating our platform。

However， we are currently using C++ 14 and I think many features from C++ 17 as well in our daily work。

 so definitely modern C++ we don't have to worry about not having C++ modern features。

 but of course we're not on C++ 20 just yet。I think some of the other questions were a little bit more specific。

 Like working backwards， Lucass， wouldn't you get collisions with a simple hash function。

I think that's quite a contextual reference to where you're at in the slides。Yes。

 so if you could write a custom hash function which might do a better job with hashing in your use case。

 in fact the whoever asked this question is correct。

 one of the reasons why it takes a long time to search an unaudered map is because of those collisions so if you recall。

 let me see if I can bring it back up here。嗯。Almost there okay。

 so if you take a look at this core graph， you'll see on the bottom right of the screen it's taking roughly a third of the time。

In terms of searching through the nodes in a given bucket。

 so it's already found the bucket where the node should be。

 but it now then spends about 30% of its time searching through that bucket so if you used a better hash function。

 you might have fewer nodes in each bucket and then you could。

Reduce that time that it's spending searching that bucket。So that's a good observation。

 but you wouldn't reduce it as much as by taking advantage of the case。

 which is what I did as the next step。I think just the last follow up question from Luke is。

Asked in this case， would you lose all of the performance increase you got from the circular buffer with collision checks unless you wrote a more involved function you Yes。

 so another great observation So one of the things I didn't do when I converted to using the circular buffer was check to make sure that there weren't collisions where two prices were so far apart that they actually mapped to the same location on the in the circular buffer。

 Now you could cheat when you're doing this， So if you have plenty of memory available and at octa。

 we have plenty of memory available you could avoid this problem by just making the circular buffer quite large。

 and then the chances of a collision are very low and then you simply make sure that。

No price that you're looking at is outside of a certain range and those tests are very very cheap。

But it is a very good observation that I kind of cheated a little that。

 but I wanted to show you the advantage that you get by utilizing the case。That was my focus。

 but thank you for pointing that out。That's good。 I always tell people one of the challenges of teaching this course generally is that the students are too damn smart sometimes。

I think the last question and someone posted again in the chat if I missed one。

 but one of the last questions I had was from Kai who said。

I think this is back when you're doing benchmarks was I noticed the number of iterations are different for the three benchmarks。

 does that matter in terms of the time？So the number of iterations is calculated or is determined by the。

Theyre Valel grown and coal growing tools， and basically if it doesn't take long to run your function。

 then it will run it more times。But if it takes a relatively long time to run your benchmark。

 then it will run it fewer times， so basically the number of iterations it should increase as you make your function faster。

Co，That makes sense。 And one， one last buffer follow up question from a different student。

What you said made sense， It's just a question is then。But a large buffer makes the memory sparse。

 would we not lose the advantages of the casing at that point？Right good question。

 so remember that what we're dealing with here are prices。And specifically。

 these prices are integers， so as they go back to the beginning。Of my。

Lexa here and going bring up the。Forice the matter。

So if you look at those prices in the price letter。You'll see that they're all one cent apart。

And that's actually not uncommon on the financial markets。

 you have a bunch of prices and they're all very close together。

So even though we might have a large circular buffer。The actual part of the buffer that we're using。

 the really important part of the buffer is relatively small。

 the unused space in the buffer is just unused and so it never ends up in the cache and so we use a large buffer just to make it easier for us to write the program but in fact what ends up in the case is just a very tiny portion of the circular buffer and the parts of that data that are really interesting to us are all bunched up right next to each other in memory so that's what gives us the advantage that we want so that we can really get the best out of the cache。

Yeah， and students asked if a look up like the one you're describing。

 would you typically still implement that in C++ or is that the kind of thing you'd look towards FPGAs for？

It depends on the application。Yes， we are moving a lot of our systems over to FPGA because for simple things。

 the FPGA can respond much more quickly than a CPUU program could。

But that's not to say that everything we do is in FPGAs and where there's complexity that an FPGA couldn't reasonably handle。

 then we need to do it in C++ and those C++ programs still need to respond as quickly as possible。

 so we still need to do this kind of optimization in our C++ programs。



![](img/8f5e62952afed07dd4f92f8d4c5921f6_3.png)

Cool， alright， I'll， I'll stop throwing questions your away。 I think think。

Think that pretty much sums it up， iss there anything else you wanted to share before you wrap up。

 Greg？Nope， that's everything I had， anything you wanted to say， Christina。

I know nothing from my end， we do have expressions of。On our website at the moment。

 if you're interested in intern or grad positions， so you can still apply。Cool sounds good。

 If you pass those on， I'， I'll be sure to circulate that with the students， too。Great， thanks。

Howwesome。Allright， well， thanks again， Greg， thanks again， Christina。

 it was really great having you here。可以。き。

![](img/8f5e62952afed07dd4f92f8d4c5921f6_5.png)

Hello， friends。😔，嗯。Nice to see you all again。 Well， that was fun。 wasn't it C， Like there's a lot。

 they could be crappy guest lectures sometimes， but I think Opta does。 It's like。

 it's a good mix of like。😊，You know， guest lectures where you just have no idea what the hell is happening。

 Like they're just showing you some like some， some crazy stuff that you just like goes over your head。

 And then there's other guest lectures where they just tell you things you already know。

 I think it's like， I think it's always great when you get opportunities to see lectures like that。

 I think Greg does a great job of really。😊，Taking concepts you that you have a grip on and really applying them so at at least that's my take on and I hope you all enjoyed it as much as I usually do。

嗯。The question about my background are those duck's boats。I guess so。 Oh， yeah。 they are。

 I guess they're but， yeah。Yeah， so expressions of interest 2022。Yeah。

 so I'll get that stuff from from Greg and Christina and pass it on probably in next week's notice。

And。I think the only thing that I have to check just as a note is around because you know。

 we're happy to encourage students to apply to optromium。You know， I mean。

 they are kind of the alpha partner of when it comes to。

Of course like C++ they're a big reputable company， my old best friend worked doctor for a few years。

 you know。He had a good time there。呃，Yeah。It's typicalical。

I will just kind of preface to all of you that I'm probably going wrap the lecture up early tonight for a couple of reasons。

 One is that my inbox is overflowing with stuff， and I'd rather probably spend an hour on。

Chugging through things for， you know， the rest of you all。 And secondly， like no here tonight。

 obviouslyca there are like like 30 of you are hi friends。 but like， you know。

 we got like 90% of the course doing the assignment or taking a break。

 So it's probably better to just really talk about the exam tomorrow night in a bit more detail。😊。

Which is good。 The only kind of， the only kind of quick note I need to share with you all is that。

 and I'll remind everyone of this tomorrow night， too， but I。

I had to push the exam sample date to 5 of August from the 3。

 The main reason for this again is just that snowed under with。

With like setting up or 3 auto marking and and sorting out some other things。

 And the main point there is that the reason this is challenging is because I kind of have to write some or really twist them。

 We don't actually have any handy because。We've only done two exams in the new style and they've both been so different that giving you those sample questions。

 you'd all get really yangsty that it's so different understandably so like reasonably like frustrated right you're like。

 well these are the questions for a 24 hour exam This doesn't mean me feel like I practice I have to go and twist and manipulate things and that takes some time which I'm going to find some time for God knows when probably sometime between now and the 5 August so。

That's， that's just that update。 We'll talk about the exam though tomorrow。

 We'll run through this page and everything like that so you can ask your questions there about the exams。

 exam， not plural1 C plus plus exam。 Last comment Opti mentioned prize money。

 I have to check this out。 I think this school told me last year that。



![](img/8f5e62952afed07dd4f92f8d4c5921f6_7.png)

There's some issues at the university level about prize money now or something。

 but I'm out of control here。 Opta is largely out of control。

 They obviously are really excited to support you guys。

 but I have to go check some stuff with the uni and I don't know if rules have changed。

 I can get told everything all the time。 Michael says could you release the old 24 hour exam for extra Shoty material。

 Yes， I'll release everything I have I'm here I'm trying to help。

 So I'll even try and release that earlier if this gets delayed out so that maybe you can do parts of the question。

 but then I think the plan is to release。All of last year's exam as sample material， not reuse it。

Rewrite a whole new exam and then write a whole new exam next year。

 I think that's the current plan so probably I'll probably get stuff to you soon regardless it's just I need to make sure it's the right scale so that you get a good sense of things。

But anyway， that's pretty much it。I'll wrap it up here， big thanks to Opver again。

AndAs I see you all tonight， and I'm sure we'll talk tomorrow night and I'll see some people in the tutorial tomorrow who turn up。

So yeah， have a great night， everyone。