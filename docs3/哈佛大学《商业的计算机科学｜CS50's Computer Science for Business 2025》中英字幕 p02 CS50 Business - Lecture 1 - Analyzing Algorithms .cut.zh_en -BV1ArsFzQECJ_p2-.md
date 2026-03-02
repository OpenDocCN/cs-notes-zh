# 哈佛大学《商业的计算机科学｜CS50's Computer Science for Business 2025》中英字幕 p02 CS50 Business - Lecture 1 - Analyzing Algorithms .cut.zh_en -BV1ArsFzQECJ_p2-

Hello， world。 We're back for another of C S 50's live streams。 This for C。

 S 50's new and improved version of C S 50 B， the course on computer science for business。

 I'm here with C S 50's zone。😊，Doug Lloyd and Doug will be presenting this lecture on on analyzing algorithms。

 and I'll be sitting in the audience as in the past answering any questions via the chat that you all might have as well as verbalizing some of them by raising my hand for Doug。

 So please do feel free to participate in that way along the way。

 we like to begin these live streams with a bit of a fun fact。 And Doug。

 I hear that you have a pilot's license for how long if you had that。 I do。

 So I got my private pilots license。 I had for six years now。

 So flyplains periodically rent plane and go cruising around amazing。

 So you might remember from Doug from such C 50 films as the C 50 shorts。

 So he's here today to give us this full fledged lecture inspired by also our collaboration on C 50 for lawyers。

 which some of you might have come across as well。 Give us just a moment。 And we will begin。

 Thanks for joining us all。😊，All right， so this is analyzing algorithms and before we start to analyze algorithms。

 it's probably a good idea to actually discuss what an algorithm is。

 so algorithms are processes that are designed to complete a specific task now you may not have called it by this name in the past。

 maybe you've referred to it as a recipe or a routine。😡。

That's basically the idea for what an algorithm is。

 You're just trying to complete some task that you go through every day。 so for example。

 you might have a morning routine or a morning algorithm as I do。

 I turn off my alarm on my phone and then the first thing I do is play a game of Wordle's a way to wake up my brain in the morning and even going through the process of solving a wordle is someone's routine or there's an algorithm for doing it Most folks who do so choose a starting word and always will go off of that word。

 and then you go step by step iterating through。😡，Trying to solve that puzzle。 that is an algorithm。

 algorithms complete specific tasks。 They also have welldefined inputs and outputs。 So for example。

 let's go back to the idea of a recipe。 if you're trying to make scrambled eggs for breakfast。

 you have all of your ingredients at the beginning。

 and you're trying to accomplish some objective at the end。

 namely a nice warm plate of scrambled eggs。In order to do so。

 you need to go through a sequence of steps that are clear and ordered。😡。

And unambiguous so you don't， for example， when you're making scrambled eggs。

 put your eggs in the pan immediately first you have to crack the eggs into a bowl and then add seasonings and add whatever else you'd like into your eggs。

 turn the oven and on and you're going through these steps in a particular order because if you do things out of order。

😡，You end up with a cold pan or egghells in your breakfast， which is probably not ideal。

 and so that would be an example of。The basics of an algorithm towards making scrambled eggs。

 unambiguous ordered clear instructions to complete a specific task and ideally。😡。

This algorithm does not go on forever。 This does not， for example， though。

 preclude the opportunity to repeat something over and over。 So if you're， for example。

 having an algorithm to count out numbers out loud， the algorithm might be。

 say the number you're starting at。 So let's say we're starting at0。😡，0。

 the next step could be add one to that number in your head。 say the next number out loud。

 and you go back and forth through those two steps over and over。

 The algorithm itself has a finite number of steps in this case， to add one。

 say the next one out loud。 add one， say the next one out loud， but this algorithm will run forever。

 So algorithms can be。😡。

![](img/80be6e1b19f6c21df49614851e952bc8_1.png)

Take an infinite amount of time to run， but they have a finite number of steps associated with them。

 So now that we have this idea of what an algorithm is。



![](img/80be6e1b19f6c21df49614851e952bc8_3.png)

A set of instructions for completing a task with the caveats we just discussed。

Let's talk about how we analyze algorithms in a computer science context。

 There are basically two ways that we will do so。The first is based on how much time。😡。

That algorithm takes to run， and we're going to discuss this at length in a little bit。

 but we care about how long it takes some process to run。

 and we may find- we'll certainly find today that there are several ways to do the same thing that take different outs of time。

😡，The other way， which we've talked about a little bit today is how much space or how much memory on your computer this algorithm takes up。

 and sometimes we'll see that that tradeoff can be very important。

 we may take up far more memory on our computer in order to save time doing something。😡，Um。

 the reason。There's a bit of a catch here， which is that we don't exactly use time as a metric because different computers had different processors。

 The first computer that I got when I was a kid in the。

90s was a lot slower than the computer that I have now and the same algorithm。😡。

Same code or some same process running on both of those machines would run at very different amounts of time。

 So instead of using time literally like seconds， minutes， hours， we instead。

Consider how many steps an algorithm might take and in particular。

 we care about how many steps an algorithm might take as the data that that algorithm applies to gets bigger and bigger so we care about what an algorithm will tend to do as some huge data is thrown at it to give us a sense of how it will generally perform because again。

 different processors， different computers are all going to handle things slightly differently。😡。



![](img/80be6e1b19f6c21df49614851e952bc8_5.png)

![](img/80be6e1b19f6c21df49614851e952bc8_6.png)

![](img/80be6e1b19f6c21df49614851e952bc8_7.png)

And so we only care about the。The general idea， the general number of steps it might take without focusing too heavily on literal minutes and seconds。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_9.png)

There are also。Different situations that might come up when we're analyzing algorithms。

 something a data set that we have may not be the cleanest。

 it may not be the best option available or it may not be organized in a way that is very conducive to what we want to do and so we have to consider what if this is this data is just in the worst possible shape and we need to do something to it and what if this data is in the best possible shape and we need to do something to it。

 the runtime or how long it takes or how many steps it takes to deal with that data may vary based on whether that data is in good shape or in bad shape or worst case and best case and these terms by the way。

😡，If you have done any other study in computer science or if you have any formal training in mathematics。

 these are actually kind of。😡，Kind of loaded terms。 these have particular meaning。

 And so when we're discussing worst case and best case scenarios。

 those terms do actually are sort of terms of art in the formal study of algorithm analysis。

 but we're going to use it in more of a layman's terms context today。😡。

And whenever we're talking about an algorithm， algorithms are always operating on some data。

 some inputs， and yielding some output， and we use the letter N or the variable N to represent the size of the data that we are working with。

😡，So you'll see that term the letter n， mathematical variable n， come up a lot。😡。



![](img/80be6e1b19f6c21df49614851e952bc8_11.png)

All right。I mentioned that we have this concern about what data will tend to do。😡。

And I want to illustrate this by way of pointing out a couple of。

Algorithms whose runtime or how many steps they take have completely made these up。

 but it's to illustrate a point about why we care about what an algorithm tends to do and how we will use terminology。

😡，To describe what this algorithm tends to do over time。

 so let's just imagine for a second that we have these three algorithms again， I've made them up。

 we're never going to get into this level of detail。

 This first algorithm in this first column here runs in n cubed time。 we'll describe it that way。

 which basically means it takes n cubed steps to run the second algorithm n cubed plus n squared again。

 we're just completely making this up。's going illustrate a point in a moment and the third one is that funky mathematical expression over there。

😡，Let's see what actually happens or how many steps these algorithms might take over time。😡。

So if we have a data set of size1， for example。😡，This first algorithm will run in one step。

 one cubed is one。The second one will run in two steps and the third will run in 13 steps。

 so it suddenly this seems like this last algorithm is pretty bad， right。

 it seems that way because it takes 13 times the amount of time to run compared to the first one now with the computers these days they can perform billions of operations per second。

😡，So we probably won't ever notice this。 but you can imagine a situation where。

You would notice some- we were talking about a computer。

 we were talking about some general algorithm， you would notice that amount of time。😡。

As the data gets bigger， though， things change。 So that's why we don't care about n as a particular value。

 we care about n as its scales， because now， if our data set is of size 10。The first one takes 1。

000 steps， the second takes 1100 steps， that's probably roughly the same。

 but now the third algorithm， which was the worst by far at size1 is actually better and only takes 400 steps to run。

😡，So again， we're seeing differences here， but as we get even bigger。

 So now we talk about a 1000 size data set。This takes a billion steps。 That's a lot。

 This takes a billion and a million steps。 That's a lot。

 but that's not materially different from what a billion steps is。

 and this takes just shy of a billion steps。 This is 992 million steps。

So what we are seeing here is that as this data set tends to get bigger。😡。

The algorithm tends to stop caring about this term。😡，And these terms。

 it's really the n cubed term that matters。 And so when we say an algorithm runs in N cubed time。😡。

What we usually mean by that is that。That's generally the term that's going to dominate how long or how many steps it takes to do something。

 We don't concern ourselves with lower lower order terms like n squared。

 and we don't concern ourselves with constant factors because those lower order terms。😡。

Don't contribute as much to how many steps something takes to run and those constant factors can be eliminated by having faster processors or having more powerful machines that analyze this data for us。

 and just to really hammer home the point here If we had a data set of size a million。

 This is if my math is correct， one quintillion。 It's a very large number。

 this is one quintillion and a little bit more。 and that is one quintillion and a little bit less。

 So all three of these algorithms on small data sets we see very big ranges in whatever they can do or how long it takes them to do whatever they're doing。

 And again weve just made these up。😡。

![](img/80be6e1b19f6c21df49614851e952bc8_13.png)

![](img/80be6e1b19f6c21df49614851e952bc8_14.png)

But as the data set gets bigger， they all tend to take exactly the same amount of time。

 And that is the language that we use to discuss。

![](img/80be6e1b19f6c21df49614851e952bc8_16.png)

Run times of algorithms is what they tend to do as the data gets bigger and bigger。

 so all three of these we would say tend toward running an n cubed time。

 that is generally how that algorithm behaves given a data set。😡。

If these were represented as the worst case scenario and we discussed this a concept of worst case and best case。

 if these were represented as the worst case scenario runtimes for these algorithms。

 we would say that they run in big O or capital O big O of N cube。

 that is just the terminology for it on the order of N cubed steps。😡。

If instead those were the best case scenario runtimes。😡。

We use this symbol omega to represent the best case scenario， runtime。😡，Can we stop here？

Can we stop here， Yeah can you take our mics down？So for all three of the algorithms that we just talked about on the preceding table。

 all of those generally， as we saw as those numbers got larger。

 tend towards running in what we would call N cubed time as that data gets bigger。

 that is generally how many steps that algorithm takes to run。😡。



![](img/80be6e1b19f6c21df49614851e952bc8_18.png)

If those times that we just discussed represented the worst case scenario runtime。

 we may describe them as big O of n cubed， big O is on the order of。

 and we would describe that as in some ways an upper bound on how many steps that algorithm would take again。

 in the worst case， and conversely if they represented the best case scenario that would be represented with this symbol omega here。

😡，Omega of n cubed as the lower bound on how many steps it may take for that algorithm to run and so that's how we would describe algorithms using time。

😡，There are a variety of ways that we can categorize how an algorithm runs or what class we might say it falls into。

 so algorithms can run in constant time， regardless of the size of the data set。

 it will always take one step or four steps or something like that。

 some constant number of steps because again remember we disregard constant factors in this analysis so O of one。

 big O of one again these all represent worst case or upper bound runtime。😡，Logarithmic time。

 log of n， big O of log n。😡，Rather， and for the mathematically inclined because we're talking about computers and computers typically operate in binary。

 you can just imagine there's a little subscript2 here next to the log oh of log to the base2 of n。

 and we have linear time these are representing increasingly more time being taken on these algorithms they take longer and longer to run as we go so linear time if it's 100 size data。

 it will take 100 steps again， maybe differing by a constant factor or a lower order term log linear time is n log n n times log n。

 we'll see in a couple of examples of algorithms of that later on。 polynomial time， n to some factor。

 So n squared n cubed for example， would be polynomial time。

 exponential time now we're starting to get real bad these are going to be very long running times2 to again imagine 10002 to 1000。

3 to 1000 not very good factorial time。 those numbers get very big。Quickly and infinite time and yes。

 there are infinite time algorithms and no you generally don't want to have them running in your business or have a computer running an infinite time algorithm if you can at all avoid it and just as a quick aside。

 perhaps you've heard of this concept in computer science or this famous problem called P equals NPP the P。

😡，In P equals NPP refers to this idea of can an algorithm or can something be expressed。

 the P there is polynomial time， that's what that actually refers to。

 there's a million dollar prize for anybody who can solve this problem of whether P equals NP and if you happen to solve it。

 just remember where you heard about it first。😡。

![](img/80be6e1b19f6c21df49614851e952bc8_20.png)

I wanted to take another second。To show how some of these runtimes can really explode as we get into the really。

 really rough ones。 So again， a data set of size 10。If it runs in log n steps。

 that's only four steps， n would be 10， and log N 40， so you can see that these get worse over time。

 n factorial with just even 10。😡，takes3 million steps。

 so you don't want to have a factorial time algorithm if you can avoid it。😡，With 1000。

 I don't even know what that number is， it's very， very large，  four times 10 to the 2，567th power。😡。

You probably don't want that algorithm to be running and my computer。

 my calculator would not even tell me what 100，000 factorial is。 So yeah these。😡。

Increasingly get bad。Quite quickly， especially once we get out of polynomial time and into exponential time algorithms。

😡，As data sets get bigger， this is why we care about how efficiently we can run some algorithm or how many steps something takes。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_22.png)

And again， here's a visual representation of that same idea where we have log n as data sets get bigger。

 if the algorithm runs in logN， very slow growth， it won't take much longer， but very quickly。

 and logN and squared， all of those algorithms really will run away and take substantial amounts of time as we go。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_24.png)

So real quick again， just this idea of constant time algorithms。

 they will always take a fixed number of operations regardless of the size of your data set。

 so for example， an algorithm that always outputs the first element of a list。

 typically we refer to lists by their first item， so it's the first easiest thing to get a hold of。

 so if doesn't matter how big the list is if you're always just saying what's the first element。

 that's a constant time operation。😡，An algorithm that adds two numbers together is also a constant time operation。

 it's not one step per se， maybe it's four， if you think about it， we need to get the first number。

 get the second number， add them together， output the result。

 but it's always some constant number of steps is' no trickery or an algorithm that just completely ignores the data entirely and does something else so an algorithm that gives you the link to a viral YouTube video it has nothing to do with the data that'll be a constant time operation。

😡，Linear time operations by contrast always are always directly proportional to the size of the data。

 so it may be one for one， one step for every one element。

 it may be three steps for every one element， but it's directly proportional to the size of that data。

😡，An example of this might be an algorithm that tries to find the number five in a list for this list here。

 it may take five steps because we have five elements in the list for this one here。

 it might take six steps because we have six steps or six items in the list。

 it may not take that in a better case scenarios as we'll see in a second。😡。

And as the list gets bigger， it takes more and more steps。

 it is directly proportional to the size of the list in question。😡，And this leads us into our。😡。

One of our two big topics for discussion for the rest of today's class。

 which is the concept of searching。 And then later on。

 we're going to talk about the concept of sorting。 So searching for a value is one of the most fundamental things that we can do with a data。

 And this is true in computer science， but this is true。For any business operation， for example。

 if you have a client list you need to go through or you have a product list of skuws that you need to go through。

 you're going to be searching through that data quite a bit。😡。



![](img/80be6e1b19f6c21df49614851e952bc8_26.png)

![](img/80be6e1b19f6c21df49614851e952bc8_27.png)

There are a couple of ways to solve this problem with basic lists。😡。

We'll look at more advanced data structures a little later in the course， but with basic lists。

 there are only a couple ways to solve this problem。😡，And we're going to look at two of them。

 but they behave differently， and they require slightly different situations to be true。

 one of them can be done on any list， one of them requires us to tweak that list a little bit in order to be able to take advantage of an efficiency。

 but let's start with the more fundamental one， which is linear search and linear search is basically what we were showing a second ago on these slides。

😡，Where we have some list of data。And we have some target that we're trying to find in that list。😡。

We're looking for the number five， for example， in a list。😡。

And this is what's called pseudocode or we could go through this as a just an algorithm。

 this is a series of operations， these are our steps that we're going to go through to operate this algorithm of linear search as long as we have not gone past the end of the list so we know how big this list is as long as we haven't run out of items。

 we're going to check to see if the current item we're looking at matches the target we're looking for。

😡，If so， we can stop because our search was successful。

 otherwise we go to the next item and go back to this first step here。😡。

So this is a finite number of steps， remember algorithms have finite numbers of steps。

 but there is this looping procedure or iteration procedure where we keep going back to the beginning until we run out of data to check。

😡，And if we get past all of this， and now we have gone past the end list， so this is no longer true。

😡，We have searched the entire list and the search was unsuccessful。😡，So this is a basic algorithm。

 these steps here of linear search， so let's see it visually to see if that makes a bit of sense。

 so here is a list， there are 15 items in this list and we'll note that here by saying there are 15 items in the list and let's just say we are looking for the number 9。

9 is our target in this list。😡，So what are we going to do what we need to start stepping through this list now that we probably want to do is have a way to refer to the items in this list and so we're going give them all an address or just a number。

 something to indicate a position Imagine this like a neighborhood of houses where every house has an address and you may notice that we have a little zero here in computer science we typically start our count from zero for a variety of reasons so we'll do that here as well so there are 15 items in this list that range from index zero。

😡，Up through index 14， those are the addresses， those are the numbers on the houses as we walk by and check to see if nine lives in any of these houses。

 so we'll go through the algorithm。😡，Starting at element0。

As long as we haven't gone past the end of the list。

 which we can check by seeing are we looking at a number that is over here。

 are we looking at 15 or 16 or something that doesn't exist in the list as long as we haven't gone past the end。

 let's go through our process check to see if the current item being examined matches the target so 11 didn't match the target so instead we're going to advance to the next item and return back here does 23 match the target no so we advance and we keep doing this over and over until one of two things is true either we found what we're looking for or we run off the end of the list in this case we do find what were looking for。

 we find the number nine in the list and so we advance at this point here。

 we have reached the target we are successful。😡，Now。

 let's try and find a different element that we can see with our eyes is not in the list。

 the number 28。😡，We'll do the same thing again， we'll start at the beginning， we've indexed。

 we've reset our element counter back to0。And we're going to step through。

 So as long as we haven't gone past the end of the list， check to see if we found the target。If so。

 we can stop， if not， we advance， so we're going to keep stepping through this one。

And we know what's going to happen here， right， We have I。 We know that there's no 28 in this list。

 but the algorithm does not。 The algorithm doesn't have any extra information。

 The computer doesn't have this wide angle view of what we're doing。

So we eventually reached the end of the list and then we would advance past element 14 to element 15。

 There is no element15 in this list， right we have gone past the end of the list。

 so this condition here highlighted in white or the white background rather is no longer true and therefore we have examined the full list and the search was unsuccessful Now I want to draw something I want to draw attention to something real quick。

 which is this is not necessarily mean that the algorithm was unsuccessful。

 or the algorithm was incorrect， we did exactly what we were trying to do。

 we were trying to step through to find an element。 we didn't find the element。😡。

But our search was still correct。 We still exhaustively made sure that that element did not exist in the data。

 I see we have a question from the audience。

![](img/80be6e1b19f6c21df49614851e952bc8_29.png)

If the size of the list is 15， how come there isn't an element 15。

 so in computer science the general idea is that we start counting from zero。

 so there are 15 elements in this list， but there is no element 15 because we started our counting from index0 it's just we gave it an arbitrary address we could have instead increased these numbers all by one and said this is element 12 and so on。

 and this is element 15， but just as a computer science norm we typically refer to the first element in a list as element or item or index0。

😡，It's a great question， so that's why there's no element 15 in this list。

 but there are 15 elements in the list numbered from0 up through and including 14。😡，Okay。

So let's use the language we discussed at the very beginning or a little while ago， rather。

 to talk about how this algorithm can be analyzed or how we would classify this algorithm using that terminology we discussed before。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_31.png)

In the worst case scenario， we have to look through the entire list to find either that the item we're looking for is in the last spot position 14。

 index 14， or that the item we were looking for wasn't in the list at all in that case that would be the worst case scenario that would the maximum or the upper bound on the number of steps that this algorithm might take to do its job。

😡，In the best case scenario as you might imagine， it could be that the target we're looking for is at the very beginning of the list。

 so we don't have to go through that entire process and when we were looking for nine a moment ago。

 we didn't have to go 15 we didn't have to look at all 15 elements we only have to look at6 or so and so the best case scenario would be 9 is at the very front we only have to look at one element and so using that language we discussed earlier。

 we could say that this algorithm runs in big O of n or in the worst case scenario or the upper bound on the number of steps this algorithm takes is n or proportional to n。

😡，And in the best case scenario， big omega， it's one because it may be that we find it right away on the first step。

😡，Okay， so that's linear search， and I mentioned is's another way to do this and that's binary search。

 but binary search is a little bit different because it has a special condition attached to it。

 which is instead of considering any list， we now have to consider a sorted list and we haven't talked about sorting algorithms yet。

 but we will。😡，The list needs to be sorted in binary search to take advantage of something and we'll see what that is in a moment。

😡，So we're going to have a list of known size， a target to search for， same as linear search。

 and we're also going to take note of the locations of the endpoints。😡。

And we're going to call them start and end or beginning and end。

 and we'll see why in a moment that that's going to be very helpful for us。And then。

 and this might look weird at the moment， we'll get there as long as the start is less than or equal to the end。

 which is trivially true at the beginning。😡，We find the midpoint of those two values。😡。

So we're going to look at the beginning， look at the end。

 find out where the middle of the list is at that point， check to see if that matches。

 if so we can stop just like linear search， search was successful。😡，If not， though。

 and this is where we can take advantage of the fact that this array or this list rather is sorted。😡。

And what we are looking for is less than the current element。

 so you can imagine that would be to the left of the current element。😡。

We can instead change our endpoint to look at a smaller subset of that list effectively we're going to do then is be able to throw away half of the list because we know things are sorted。

 if I'm looking for something smaller than what I found in the middle。

 I don't need to look at everything that's bigger than what I found in the middle so we're going have an efficiency that we can take advantage of that we'll see makes binary search run more quickly or in a different runtime class from those that we discussed earlier so if not it's less than what we're looking for。

 we change our endpoint and look at a smaller subset and by contrast of what we're looking for is's bigger。

 we're going to do the opposite we're going to change our start point and look at only the larger items as opposed to only the smaller items。

😡，And again， same as before， if we have done something where we have。

As we move those endpoints closer and closer to the middle。

 we eventually get to a point where they cross over each other potentially if the item we're looking for is not in the list and if that happens。

 we can declare the search to be unsuccesful at that point because we have compressed our list that we're searching through into nothing and therefore that item cannot possibly be in the list so here's our list again let's give everything an address and pull up our algorithm for this process and not forget that we need to indicate the start and endpoints again we're gonna to use the indexes here 0 and 14。

 we're looking for the number 19 and we need to make sure for binary search that our list is sorted so we'll do a little bit magic here to sort it and we'll talk about a way to do that in a moment now we have a sorted list now we can go through this procedure as long as the start is less than or equal to the end that is true。

 start right now is zero。The beginning of the list， end is 14， the end of the list。

 we're going to calculate the midpoint。Midpoint is seven。So we find。Number seven here。

Then check to see is that what we're looking for， it's 15 what we're looking for， the answer is no。

 so in that case what we're going to do is say the target what we're looking for is greater than 15 target member is 19 so if it's going to exist in this list because this list is sorted。

 it must exist over here to the right， it cannot exist over here to the left if it did that would mean that our list is unsorted and this trick。

 this efficiency we're trying to take advantage of would not be possible。😡，And so what we do。

 we set the new start point just to the right of the current midpoint。

 so if we've set the midpoint right now to seven that's in the center of our list。

 what we're going to do now is say I only want to look at this part of the list that's the only place 19 could be if it exists and so we'll set our new start point to eight and what we effectively do then is take this portion of the list out of consideration and hopefully that makes sense as to why we can do that and why we can only do that if this list is sorted with linear search we couldn't necessarily throw away half the list because there's no rhy or reason to our ordering but here there is。

😡，So start still is less than end， we're starting now our list is just this portion from 8 to 14 so we can go through this process again。

😡，Calulate the new midpoint to be position 11， check to see if that's what we're looking for。

 the answer is again， no， 23 is now too high， it's the opposite problem。

So what we'll do instead is set the new end point to be just to the left。

 so now I don't need this part anymore， I just need these items here。😡。

And we can basically disregard the far right portion of the list。

And then we'll just keep going back to this process， start is still less than end。

 we haven't crossed endpoints yet， we calculate the midpoint to be9， and we can see。

 again visually this is going to be a successful search。

 we found the number 19 where we hoped we would。😡，The search was successful。If you think about it。

 how many times do we have to go through this process， go back to linear search for a moment。

 we had to， when we couldn't find what we were looking for， go through this in this case 15 times。

 but here if you were counting， we only went through it three。

 we only had to look we only iterate through this loop three times so that feels faster。

 even if it's a little bit more heady， it feels faster。😡，And in fact， it is faster。

Now let's see what happens if we have an unsuccessful search just to confirm that this algorithm will still be correct or we'll still behave the way that we want it to。

 so it's the same process we're looking now for the number 16， which if it existed would exist here。

 it doesn't， so let's see what happens with binary research and see if it's still a successful or correct algorithm。

😡，Calculate the midpoint， the midpoint is7。15 is not 16， it's close， it's not quite there。😡。

So instead what we're looking for is greater than 15， we're going to do the same thing as before。

 change our start point to be number eight just to the right of the current position。

And then throw out that portion of the list。😡，We go through this process again。

 this is going to be the same start as the last one or the same sequence of operations 23 is 23 is too big。

 16， the target is less than 23， and so we can now eliminate all of this portion to the right we set the new endpoint to be 10。

And we can disregard the far right portion of the list。Now again。

 what's the midpoint between8 and 10， it's 9 is the value at position9 what we're looking for。

 unfortunately no， it's less than that， and so we can set the new end point just to the left of where we've calculated the midpoint to be。

 position 8 and disregard the remainder of the list。😡，Now our endpoints haven't crossed yet。

 they're in the exact same spot， so this part is still true。

 start is still less than or equal to the end point， and so we can still go through this process。

 what is the midpoint of 8 and8。😡，Well， it's  eight， so we'll recalculate the midpoint there。😡。

We'll check to see if the value at position 8 in our list is what we're looking for。 It is not。

 We are looking for something that is less than that。

 And so we are going to set our we're going to set our endpoint just to the left of where we currently are again。

 we're trying to。😡，Home in on where this item would be in the list if it existed in the list。

In this case now we set our endpoint to7， one less than the current midpoint。

 and now we have triggered the condition where this search is complete but was unsuccessful。

 the algorithm was still correct， the algorithm confirmed that the number 16 did not exist in this list so even though it was an unsuccessful search it was still a correct run through of the binary search algorithm。

 so that took fewer steps， it was probably more talking because we were going through this idea of compressing the list in eliminating things versus the stepwise nature of linear search。

😡，But we went through that process of going back to the beginning and trying again far fewer times in this case。

So as you can potentially imagine， this algorithm is， again。

 given the condition that the list is sorted。going to be faster in general。

 we're able to toss out half of the list every time。 So worst case scenario。

 we have to cut this list in half repeatedly as many times as possible down to a single element。😡。

That is either what we're looking for or has wiped out the whole list because we've gone through that process so many times。

 In the best case scenario， it would be that the very first time we calculate a midpoint from beginning to end。

We found what we're looking for right in the middle。So in this case。

 the best case we'll go do this in reverse for a second， The best case lower bound is one。

 it takes one run through the algorithm， one step to calculate or defined what we're looking for and in the worst case or the upper bound on steps it's log N that's where that earlier I mentioned there's a sort of a hidden subscript to number two here。

 log to the base two， that basically means we are cutting this list in half over and over。

 and every time we do so we can disregard or throw out half of the list。😡，And so binary search again。

 with the caveat that requires a sorted list is more efficient than linear search， but how do we get？

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_33.png)

Asorted lists that's going to be a problem we have to solve。

 And we're going to solve that in just a moment right after we have a question from the audience。

Is this algorithm essentially the same then as tearing a phone book in half and again and again is this algorithm the same as tearing a phone book in half over and over and the answer is yes in a phone book assuming the phone book of course is sorted if it was not sorted this would not work but it's like opening in the middle of a phone book finding that the name you're looking for is not on the page you happen to have opened up to but it is on one side or the other ripping the phone book in half and throwing away the portion that does not have the name in it。

 you don't have to look at those several hundred pages worth of information because you know that what you're looking for is in this part over here not the part over there and similarly。

 you can keep tearing that part in half over and over so you could have a thousand steps remember earlier we showed a slide of how many steps it might take for log N or N given a size for 10 for size 10 which is a phone book is they have a lot more than 10 names in it it only takes four steps for1 thousand I think it it wasn't much more than that I don't recall off top of my head but we're not looking。

100 steps here， we're looking at a very， very small number as the charts we saw earlier too。

 as that number gets bigger and bigger， the log N graph tends to get quite flat。

 so even though our input doubles in size every time our input doubles in size。

 we only have to add one more step because we can eliminate half of the problem basically canceling out that doubling every time we go through a step。

😡，Okay。So sorting is the other type of algorithm we're going to talk about quite a bit today。

 and I want to stress at this point， though we're talking about searching and sorting pretty exclusively today。

 these are not the only kinds of algorithms there are right like there are algorithms to make breakfast。

 there's algorithms to do anything theres algorithms to figure out what you want to recommend to a customer who is purchased a particular item and you want to try and suggest that they purchase a different item that's neither a searching nor sorting algorithm。

 but there is a set of steps that goes through an analysis of what they might want we're talking about searching and sorting data because they are very easy to visualize。

 but these are not the only kinds of algorithms we have。

 but since we just talked about binary search。😡。

![](img/80be6e1b19f6c21df49614851e952bc8_35.png)

And the fact that we need to sort in order to use binary search。😡。

We should probably talk about sorting， so organizing data is also very important for any business operation we're doing。

 we need to keep our client lists maintained， we need to keep our SkuUs maintained。

 we need to keep our databases in order， and so keeping things sorted is very important to do。😡。

There are a lot of ways to do it， there are far more ways to sort than there are to search through lists of things。

We're going to talk about several options today， but they are non exhaustive， I want to be clear。

And let's use our language of runtime to talk about these various algorithms starting with selection sort。

 so the way selection sort works， one of the five we're going to talk about today。😡。

Consider that we have this list and it's unsorted。 Obviously， if it was sorted。

 that would be a lot easier。 but we're going to consider an unsorted list。

 And we're going to say that the whole thing at the beginning is unsorted。

 We don't know anything about the state of this list。

 So we're going to describe the entire thing as unsorted。

 Our objective is to find the smallest item left in the list so we can use， for example。

 linear search to do this。 We can step through to find the smallest item left in the list。

And then we can swap that such that that item becomes the beginning of the list if we walk through the entire list and we find the smallest thing。

 and then we put that thing at the front。😡，We can now no longer need to be concerned about what this item is。

 the first item is， and we can just repeat that process again with the remaining elements in order to effectively sort the list。

 and we'll go through this visually to see this in a moment。😡。

So let's imagine we have this list of six items， we're going to go through this list of six items for all of our sorting algorithms today。

😡，And as we can see it is unsorted， so we're going to go through our algorithm。

 our algorithm in this case is just a couple of steps。

 find the smallest item remaining in the unsorted portion of the list again。

 we can just use linear search for this。😡，Then once we have found the smallest item。

 swap it with whatever the first element is of the unsorted portion at the beginning here。

 the entire array is unsorted as items become sorted， we'll indicate that visually。😡。

And expand our sorted portion so we'll see how that goes so we need to first find the smallest item in the list so we're going to start at the beginning as we do with any list and step through to find the smallest one so we look at the beginning so far five is the smallest thing we have seen we go through two is now the smallest thing we have seen so we're going to keep track of that。

😡，Then if we go again， one is the smallest thing we have seen， keep track of that。

We go to element 3 or the fourth item in the list。 number is three。

 that is not smaller than what we've seen。 So that is。

 we don't need to indicate that we're just going keep stepping through。

 see if we find anything smaller and the answer is no， we don't。

 So once we've gone through the list and found the smallest item。

 we are going to swap that item with whatever the first element is of the unsorted portion of the list。

 The whole thing is unsorted at the beginning。 So we're going to take one and5。

 and we're going to switch their positions。And then we can declare。

 since we have found the smallest thing that this element， this one must be sorted。

 and so now we have a fairly small sorted portion of our list。😡。

And five elements remaining in this six element list that are unsorted。

 And we can just go through this process again。 So we're going to find the smallest element in the list。

 We step through all of them。 We find that the smallest one is2。

We don't actually have to do any swaps here， two， we swap two with itself and declare that two is now sorted。

 we go through again， we find that three is the smallest item remaining， we swap three with five。😡。

And declare that that is now sorted， and hopefully you can see that this is building over time this sorted list and it does not take too too long in a six item list。

 a bigger list it might take a little bit longer to get all of the elements in position。😡。

At the very end， we saw five into place， six is the only thing left。

 so six must necessarily be the last thing that we can add to the sorted portion of the list。

 and now after going through this process， quite a few times if you saw as we were going through。

 we keep iterating through， we have sorted everything。How do we analyze this though？😡，So。

It's not quite as straightforward as linear search， right， in linear search。

 we went through the list。😡，Trying to find something。

 but we only had to go through the list once from beginning to end。

Here we went through the list from beginning to end multiple times。

 How many times did we do it was it turns out we actually did that process roughly again down to a constant factor because the list got a little bit smaller as went along roughly n times so we went through n elements of the list。

😡，And again， the list got a little bit smaller every time as we went roughly n times again。

 there's a constant factors here， so it's not exactly that， but when we disregard those。

 that's what we get to so the worst case scenario we need to look at every element in the list on each pass and we have to repeat that process n times because we only get one element right every time we run through this。

In the best case scenario。It's exactly the same。 We have no way to check to see if things are already in the right position。

 we still have to step through， we don't have any other metadata or any other variables we're using to keep track of things so there's no like efficiency we can gain with this particular algorithm。

😡，And so in this case， the worst case scenario or the lower bound on runtime or sorry。

 the upper bound on runtime and the lower bound on runtime are exactly the same。

 They are both considered n squared algorithms。 And again。

 that's because we need to run through the list of n elements。😡，N times。

 we have to repeat that process。 So it's n across and down， you can kind of visualize it that way。

 That is how we get to n squared。 So the question is， can we do better than that， And the answer is。

 yes， we can。And so let's take a look now at bubble sort to see if bubble sort can help us out。😡。

A little bit。So with bubble sort， we're going to start with the same basic idea。

 the idea is that we have a list that is completely unsorted at the beginning。

 and over time we're hoping to build a sorted portion。😡。



![](img/80be6e1b19f6c21df49614851e952bc8_37.png)

Differently though， this time we're going to look at two elements at a time。

 and if the two elements are out of order， we're going to switch their position。😡。

What this effectively does is bubble the bigger element further and further to the right as we go。

 and so it's sort of the opposite of selection sort and as much as we were trying to find the smallest and pull it to the front by swapping and bubble sort we're kind of pushing the biggest element to the end and if we push the biggest element to the final position。

 that element is correctly positioned and we can just keep repeating that process over and over。😡。

Theres one other thing we're going to do which is keep track of how many times we make a swap。

It may seem strange at the moment， but we'll get to why that is actually a pretty good idea in just a moment。

So same list that we have been looking at， let's go through this process again。

 here is our algorithm and we're going to keep track again。

 as I mentioned of how many swaps we have if two adjacent elements are out of order， swap them。

 then look at the next pair and do it again and at the end of one pass once we have gone through the entire thing once hopefully the largest element should have bubbled or been pushed as far to the right as possible。

😡，So let's say， so we're going to start by looking at this pair of elements， five and  two。

 if we're imagining this being sorted left to right in increasing order。😡。

We need to swap them and so we will exchange the position of those two values and make note that we have made one swap in our swap counter now we look at the next pair the next pair is not one and three。

 the next pair is five and once we're looking at every pair。😡，Of numbers carefully， five and one。

 they are also out of order， we will swap them and we will increase our swap counter by one。

Three and five， five and three rather are also out of order。

 so we need to swap them and increase our swap counter again。😡，F and six are correct。

 We don't need to swap them。 where again， we're only looking in this algorithm at just this pair at a time。

 This pair happens to be correct， so we don't have to make any swaps here。 We look at six and 4。

 six and4 are out of order。😡，We swap them。And now we have pushed the largest element as far to the right as it can go。

 there's no other pair to look at。So we can declare at this point that the largest element has bubbled to the end。

 and we can say that that is sorted， okay？😡，So we have pushed it all the way to the end it is sorted。

 this is now this orange portion here is our unsorted portion。

 the blue is the sorted portion Once we go back to the beginning。

 we want to reset how many times we've made a swap。😡，And we'll go through this process again。

 our two and one out of order， yes， we're going to swap them。Our two and three out of order， no。

 we'll leave that alone， our three and five out of order， no， we'll leave that alone。

 but five and four are out of order， we're going to switch those and again indicate that we have added one more swap to our swap counter。

😡，at this moment we as humans can see this happens to be correct， we know that this is sorted。

 but this is only because we can see more at once than the computer can see at once。

 so the only thing the computer can guarantee at this point is that or the algorithm can guarantee at this point is that the five which is the largest element in the unsorted portion has been bubbled all the way across and so only can we say at this point that the five has been sorted。

😡，But now we're going to see why that swap counter is going to come in handy。

 We'll reset it again and we'll start comparing pairs， so one and two don't need to swap。

 two and3 don't need to swap， three and4 don't need to swap and now we're done and we made no swaps if we didn't have to change the position of any values。

 then everything else has to be correct and so we don't just get one。

 we potentially can now get all of it， we do in this case get all of it and can say that everything left because we didn't have to change anything。

 must be in the correct order。😡，So that's an advantage we didn't have to go through the looping process n times。

 we did it in this case three times instead of having to do it six times， so that feels better。

 is it actually better， well the answer is again because we're keeping track of how many swaps， yes。

 it is better， but in the worst case it's actually still just as bad that was a medium case that was pretty okay the list wasn't completely in backwards order。

 but if it was we would have had to keep bubbling just the first element over then the next。

 then the next and we would only get one at a time in the worst case， a completely backwards list。

 but that wasn't the case here。

![](img/80be6e1b19f6c21df49614851e952bc8_39.png)

But in the worst case， that would happen in the best case， though。

Imagine that we had a completely sorted list。😡，If that was the case。

 when we went through it one time。Our swap counter would be zero when that was done and therefore we would only need to make one pass through the entire list and so the upper bound on runtime。

 the worst case situation is that this algorithm runs in big O of n squared。

 having to look at all n elements and bubble the biggest one over n times again disregarding constant factors and so on。

 but in the best case we only have to make one pass。😡。

Looking at each of the n pairs or n minus1 pairs。😡，Or N elements。

It's not omega of1 because we still had to look at all of the elements， it's omega of n。

 so that is in fact an improvement over selection sort in the best case。😡，All right。

 so let's talk about another one。😡，And I'm going to reveal now that this is actually going to have exactly the same runtime as bubble sort。

 but it's going to do it in a very different way。So this is an example of how two algorithms that appear to be quite different can actually have the same effect and can run in the same amount of time but do so in very different ways。

 so with insertion sort， we're going to again start with a completely unsorted list and can call the whole thing unsorted。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_41.png)

Arbitrarily， we're going to say the first thing we see has been sorted。😡，seemsms kind of weird。

 but okay， we declare the first thing sorted， then we look at the next element and if it is out of order。

 we're going to shift or rearrange the elements that are sorted to fit that one into place。😡，So okay。

 so as we go through， we declare the first thing sorted。

 and we're just going to keep shifting things around to make room as we go。

 so we'll look at one element at a time， put it in the right spot， look at one element at a time。

 put it in the right spot。😡，Let's see how this looks with our typical starting list here。

So we arbitrarily decide we're going to declare the first element sorted， five is sorted。😡，Again。

 we can see that that seems wrong， but we'll go with it， we'll trust the algorithm here。

Then we look at the next one and we either。😡，Append it to the sorted list。

 so if it's larger than the largest thing in the sorted list， we can just tack it on。😡。

Or we shift things around， so now we're going to look at the two。😡，2 is clearly before5。

 It's supposed to be there to the left。 So what we're going to do is kind of set it aside temporarily。

 We're going to slide 5 over。And then we're going to pull the two back to where the five was。😡。

And now this portion in blue has been sorted， okay？😡，Now we look at one。

 one clearly also belongs to the left here。😡，So we'll pull that out。We'll push these two over。

And it'll pull the one back into the starting position。We go through that process again for three。

 we don't have to move everything， but we do have to push the five over and then pull the three back into position。

 the six is greater than the five so we can actually just tack that on。

 we don't have to move anything around， it happens to be bigger than the biggest thing we have sorted thus far and so we can just tack that on to the end and the four also requires the six and the five to move over。

😡，To be put into position there。 So we have made one pass through the list， right。

 that's different than bubble sort。 Bu sort， We went all the way to the end。

We've got one thing in position。And then we to go back to the beginning and do it again here we went one element at a time。

 but every time we looked at just one element we maybe had to push a lot of things out of the way。

 so that's maybe where these two algorithms even though they have the same runtime behave very differently one of them we're looping through multiple times this one we're having to push potentially up to n elements for each of the n elements right if we have six elements here。

 we might need to push five of them out of the way to make room for just the one that we need and that's going to be the same math believe it or not as bubble sort n times n in the worst case scenario。

😡，So I've kind of buried the lean there。Worst case scenario， same as bubble sort。

 if it's in reverse order， we have to potentially push up to n elements out of the way。😡。

Best case scenario， we just keep tacking on as the example here a moment ago with five and6。

 we can just keep tacking on if we find everything's in the right order。

 we just keep appending it to the end of the sorted portion。

 so same exact outcome as bubble sort in terms of runtime。

 but it is a very different approach to that same idea。😡。



![](img/80be6e1b19f6c21df49614851e952bc8_43.png)

I'm going to take a minute if that's all right。So the algorithms we've talked about so far have done。

This iterative process， we go through the steps， we start at the beginning。😡。

We continue on and oftentimes we go back to the beginning again that process is called iteration In order're going to talk about the next sorting algorithm。

 we're going to have to take a bit of a detour here and talk about this concept called recursion。

 which is also a very important problem solving technique in computer science and is going to be the way we need to we need to get our heads around this idea before we can discuss this next sorting algorithm。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_45.png)

As I mentioned， we're going to keep doing something in an iterative algorithm until some trigger occurs。

 either we've reached the end of the list or we found what we are looking for。

 we go back to the beginning and do it again。😡，In a recursive algorithm。

 it's slightly different concept instead we try and make the problem we're trying to solve a tiny bit smaller and just solve a teeny portion of that problem and then sort of play a game of telephone where we call somebody else up。

Recall the algorithm again on a slightly modified version of the problem and wait for their response to answer the question and way we're going to illustrate this and we've heard this word already today is through the concept of the factorial function in math and if you recall from your math days with the factorial function is it is is a calculation that represents the product of all integers from one up to and including the number you are looking for。

 so the factorial of3 would be3 times 2 times1， the factorial of4。

 which is' an illustration we're going gonna get through in a moment is4 times3 times 2 times 1 or 24。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_47.png)

So this algorithm， calculating effect factorial and another example of an algorithm that's not searching or sorting。

 but it's probably also not something you're doing every day in your company perhaps can be expressed iteratively。

 set a running product value that we keep track of to1。

 not zero because we're multiplying things by zero that we just go to zero forever。

 so we start the value at one。😡，We set a counter equal to one where we're going to start counting up from。

😡，And then as long as the counter is less than or equal to the number we want to calculate the factorial of。

 we multiply it by the current product and increase the counter by one。

 so if we're calculating the factorial of four， we start at one。And we have our counter at  one。

1 times 1 is1。One times two。Is2， two times 3 is 6，6 times 4。

 which is that we're trying to calculate the factorial of 4 is 24。

 So that's an iterative approach to calculating the factorial。

 but we can also have this idea of a recursive approach where we are trying to solve a slightly smaller version of the same problem and we keep asking it's like a game of telephone It I think a great way to think about it。

 We call somebody up and say， hey， do you happen to know the next this other version of this problem that might be a little bit easier for me to solve let's let's see this in action。

 maybe that'll help visualize this idea a bit。 So if the value the algorithm is currently operating on So we're going start at fourth。

 kind of the opposite in this case， we're going to count down towards one if the value we are operating on is less than。



![](img/80be6e1b19f6c21df49614851e952bc8_49.png)

Or equal to one。 We return a value of one。 This is oftentimes when you're talking about a recursive algorithm called the base case。

 It's the simplest problem we can definitely solve。😡，The factorial of1 is one。

 the factorial of any number less than1， also if you're curious is just defined to be1 because if it was 0。

 it would mess everything up。😡，If we have that specific case。

 we can solve that very specific problem and say the answer is one。 Otherwise。

 we return whatever we're currently operating on， multiplied by the factorial of the number one number smaller。

 So we're kind of trying to get towards that base case。

 We we're trying to get a slightly smaller version of the same problem。😡。

And we're going to wait we're gonna be on hold on the phone waiting to get the answer from somebody else down the line to then give that answer back to us so it's a different approach。

 let's take a look at it so we're going to calculate the factorial of four so what is the factorial of four well according to my rule if it's one factorial of1 I know it's just one otherwise though it's factorial four four times the factorial of three but what's the factorial of three。

😡，I don't know。I don't know they answer that one off top of my head， but I can just recur。

 I can do this process again on a slightly smaller version of the same problem。

 so what's the factorial of three。😡，It's not one， but I do know by this case。

 that it must be three times the factorial of  two。 It's the same rule I just applied a moment ago。

 So what's the factorial of 2。😡，I don't know。But I do know that it is two times the factorial of1。😡。

So what's the factorial of one？I do know that by definition of the recursive algorithm we've discussed。

 the base case we've set up， that value is one， and so factor of 1 is one。😡。

And now I've sort of played telephone， I've been waiting on hold for everybody else to tell me the answer。

 one says I'm one that gets kicked back up， I'm two， that gets kicked back up。

 I'm two times three or six， and now four times3， four times6， rather 24。

 so that's the idea of this factorial sorry this recursive process is that we are operating on successively smaller or easier to nibble on bits of the same problem until we get to one that we definitely know and then all this information can immediately flow back to what we originally started with。

😡，So we end up with a value of 24， the same way we would with the iterative algorithm and the reason we talk about this is to get into the next algorithm we're going to talk about。

 which is merge sort and merge sort behaves quite differently from the other algorithms we've already discussed today to do sorting。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_51.png)

And requires us。It doesn't actually require us， but it's a lot easier to conceive of as a recursive algorithm as opposed to an iterative one。

😡，So so far， the best we've been able to do for speed。😡，In the worst case。

 the upper bound on runtime。Is O of n squared？Merge sort will allow us to do better。

 but we have to think outside the box。And we have to come back to that original tradeoff we discussed。

 which is this idea that algorithms and things we care about are time。😡，And memory or time and space。

 And in this case， we're going to use more memory。😡。

To solve the problem as opposed to more time if that's a tradeoff we're willing to make。

 merge will allow us to do a little bit better in terms of time as long as we have those resources available to us to spare。

Every algorithm like I said we've talked about has been done in place。

 we're working on that same array， we're just exchanging values or we're rearranging values or we're pushing values to the end in Mer we can't do that。

 we can't just use that same one single array of six elements over and over。

 we have to make duplicates or triples of that and do a couple of things elsewhere in memory holding things in place while we do something and then eventually put the pieces back together。

😡，So that's what we're going to do here， and we're going to be leveraging recursion to implement this algorithm。

 so let's take a look at the merge sort algorithm。😡，Sort the left half of the list。

Then sort the right half of the list。And then merge the two halves together。😡。

If you're looking at this and you're saying。That doesn't seem like you're solving a problem。😡。

You're right， this alone， I'm kind of outsourcing the problem， sort the left half of the list。

Unless that list is of size1， which is something I do know how to sort。

 I guess a list of size1 is automatically sorted。😡，I don't know what to do。

 but what I can do is recursively apply this algorithm。😡，To say， well。

 if I have a list that's bigger than one， I guess I can just do this again on it and keep splitting and keep splitting until I get to something I can do a list of size 1 trivialally sorted。

 It's the only thing that's in it。 and then start merging the pieces together。

 So we're gonna walk through this one quite a bit more slowly just to get your head around this idea of what is happening。

😡，So merge sort， same list， let's sort it using this approach。

 we're going to sort the left half of the list。That's this。

That's all the algorithm tells me to do I don't know how to do that and also just for visual's sake so we can discuss this without saying the left of the left of the left repeatedly。

 I'm going to call this the yellow list for the rest of this discussion and we're going to call this the purple list but this is still the left half of what we started with。

 and this is the right half of what we started with but it will allow us to not have to go so many layers down in our discussion today。

😡，So instead ofm saying sort the left half of the list， I've just changed this to now。

 sort the yellow list。😡，Well， I don't know how to do that。

 and the only thing I have for an algorithm are these three steps and the fact that I remember that a list of size1 is trivially sorted。

😡，So what can I do？The only option I have is to。Do it again。

 take this yellow list and apply our algorithm to it。😡，So sort the left half of the yellow lift。

 I can do that。 Now it's a list of size 3。 So what do we do with it， It's not like it splits evenly。

 a list of size 6 split nice and evenly into two equal parts in the event that we have unequal parts we'll just arbitrarily say that the left one should always be smaller。

😡，We're just going to pick that arbitrarily， So I want to sort the left half of the yellow list。

 Can I do that？This is the left half of the yellow list。

 this would be the right half of the yellow list。This I can do， this is a list， again。

 I'm kind of like if you think about it as like layering down， I'm just focusing on this piece。😡。

That I can do。That's a list of size one that is trivially sorted， so we're going to say， okay。

 we'll put a pin on that， that is sorted。😡，Now I need to sort the right half of the yellow list。

 that's those two elements there。😡，I don't know how to sort a list of size2 the only thing I know how to sort is a list of size1。

 and so faced with this problem， the only thing I can do is start this process again。

 kind of putting a pin in everything else and trying this again so what I need to do instead is sort the left half of the right half of the yellow list。

😡，Okay， so now I'm back to just focusing， I want to sort this right here。

The left half of the right half of the yellow list。Is an element of size1 is a list of size1。

 I do know how to sort that。 That's2。😡，The right half。诶。Of the right half of the yellow list。

That is a list of size1， I do know how to sort that。😡，So now one， so I have now sorted the left half。

😡，Of the left half of the yellow lift。I have done。These individual。Fraactctions of this list。

 but now I'm going to come down to this step， which we haven't talked about yet。

 merge the two halves together。😡，Of。This portion here。

How do I do that well I look at each of the two lists and I say which one is smaller？😡。

I take whichever one is smaller and I put that into position。😡。

And then I do that over and over now in this case， it's just two lists of size one。😡。

But if I had bigger list， I would look at the first element of both of those lists， compare them。

 put into position， then I would look at what's next for both of them put into position。

 So among these two options， which one is the smaller one。 if I want to put things in order。

 it's the one。😡，So I put the one into position。And then all I have left is the two。

 I put the two into position。 So we have now sorted the right half。Of the yellow list。So now。

 if you're thinking about this in terms of where we started， we had this full list。

We split it into a yellow list and a purple list， and now we're trying to drill through this idea of sorting the left half of that overall list。

 we're getting pretty close at this point。😡，We now need to sort these pieces together and once we have done that we will have sorted these three items overall I know this is a bit strange。

 you have to keep in mind that we're layering down and then we're kind of like undoing it's sort of like that telephone call for factorial we're making calls down the line and sorting smaller and smaller problems and then we kind of back our way back out back to where we started。

😡，So let's merge this list of size1， the five， and this list of size2。

 the one and2 into a single sorted portion， and that will complete the overall objective of sorting the left half of the whole list that we started with。

 hopefully that makes sense。😡，So we look which one of these is lower， five or one。

 that's the only comparison we have to make when we're sorting the two halveps together。

 the one is lower。😡，And so we put that into position here。Now we've already excluded the one。

 we've already got the one in place， we look at the again the first element of this list and the next available element of this list。

 which is smaller， the two。And then which is smaller， five or nothing， in this case， five。Okay。

 so quick pause， where are we？😡，We have now sorted。😡，The yellow list， which as we recall。

 was the left half。Of the whole list that we started with。

 So in the overall process of this algorithm， we have done the first step。

 which we said was sort the left half of the list。😡。

Now we have to repeat that process again on the right。

 but just for context and grounding as to where we are。

We kept breaking our problem down from a list of size6 to a list of size three。

 to a list of size1 and two， we had to split that two into a couple small lists and then we built them back up in a sorted order so if we go back a second and just look at the where we ended。

 we took this piece here， 521。😡。

![](img/80be6e1b19f6c21df49614851e952bc8_53.png)

And through a whole bunch of layering and recursive application of this algorithm， we end up with 1。

2，5。This 1，2，5 is a correct sort of this yellow list。 We still have the other half list to deal with。

 but we have correctly sorted the left half of the overall list。😡，All right。

 so let's do this process again with the right half of the list。

 and hopefully this will start to make a bit more sense now that we've seen it once before。

 So now we're going to handle that until we get。With a sorted right half of the list。

 and then we'll do one more merge together and we'll be all squared away。

So we need to sort we just sorted the left half of the whole list and now we're going to sort the right half of the whole list which we have called the purple list。

 so let's sort the purple list how do we do that the a list of size3。

 we don't know how to sort a list of size3 so we're going to go back to the beginning and start again and we're going to sort the left half of the purple list the left half of the purple list again we're deciding if we have an uneven number of elements and odd number of elements we are going to pick the left side gets the smaller piece we do know how to sort a list of size1 and so we will declare the element3 to be sorted We do not know how to sort a list of size2 and so we recursively go back and apply this process again now just to that two element list64。

😡，Can we sort the left half of that sublist， the left half of the right half？Of the purple list。

 the answer is， yes， we can do that because that is a list of size 1。

So we can declare that that is sorted。Can we sort the right half of the right half of the purple list？

Yes， that is also a list of size1。 we know how to sort a list of size1 because it is trivially true that it is sorted。

And we declare that that is in position。 So now we need to merge these two halves together。

To complete that section of the algorithm。How do we do that， we look。

 and we decide which one is smaller。The smaller one is four。Then whats smaller6 or's nothing left。

 so it has to be 6。Okay， so now we have sorted the right half of the whole purple list。

 and now we need to merge the two halves of the purple list together。😡，Now again。

 visually we can see that that's the case but the computer doesn't know that。

 so we have to make a comparison between three and four which is smaller， three。

 and then between four and nothing，4 and then between six and nothing six。

 and so ultimately now through this process we have sorted this list。

 the purple list is sorted the yellow list， the left half of our original list is sorted。😡。

So there's only one thing left to do。So again， let's just frame ourselves as to where we are。

 We have sorted both of those halves of our original list， so we have completed step two of our。😡。

Big overall original problem of。Sorting the list， we've sorted the left half of the list。

 and we've sorted the right half of the list， and so now all we have to do is merge those two halves together。

😡，Now I'm going to do a little bit of cleanup here。😡。

We're going to just blank out a bunch of this stuff and we're going to return our original array color scheme back。

 so this was all the work that we did， this represents the space that we sort of took up while we were doing work。

😡，Because again， remember in mergege saltt， we're making this trade off of time and space。

 this represents sort of space that we did to do our work。

And now all we need to do is merge this left half of the list and right half of the list together。

 and we'll put them back into our original list。 So let's just clear that list out。

 we'll just make room for everything we're about to copy in。😡，And we'll begin our comparisons。

 which is smaller between one and three， the beginning elements of the lists that we are starting with。

 it's one。Now which is smaller， two or three， those are our two options so the elements the front of our lists。

 two is smaller， which is smaller five or three， three。😡，Five or four， four， and then five。

 and then six。Merge sort is weird and if your head's spinning a little bit， that's okay。

 especially if you've never seen this concept of recursion before。

 but what we did was we kept breaking this problem down into smaller and smaller pieces until we got to a piece we knew how to solve a list of size one。

And then we just started reassembling， it's like taking a set of blocks， tearing it all apart。

 and then rebuilding it back together in a different order。It's kind of the same idea。

 so once we have finished putting all these together， the list is sorted。



![](img/80be6e1b19f6c21df49614851e952bc8_55.png)

And。You're probably going to think that that felt like it took a lot longer than bubble sort or selection sort or insertion sort。

 and that's probably because we spent a lot of time talking about it， but in fact。

 when we get to very large data sets， this is actually significantly faster。😡。



![](img/80be6e1b19f6c21df49614851e952bc8_57.png)

If you're willing to make the trade off of time versus space。😡，Worst case scenario。

 the list is in a completely reverse order， it makes no sense the algorithm though will never know this because the only thing it knows how to do is sort elements of sort lists of size one and then put them back together and then put those you keep comparing those lists merging them back together。

 it does not matter what order the original list is in。

 the algorithm has no shortcuts to get around it。😡。



![](img/80be6e1b19f6c21df49614851e952bc8_59.png)

The best case scenario is exactly the same。 the algorithm knows nothing about the list。

 and so it can't there's no tricks or efficiencies like we have with bubble sort。😡。

Or insertion sort where we could just keep with bubble sort for example。

 keep you track of how many swaps were made or with insertion sort just keep adding things to the end。

 there's actually no efficiencies we can gain here so in the worst case scenario or the upper bound on runtime。



![](img/80be6e1b19f6c21df49614851e952bc8_61.png)

Merge sort is better。It runs an n times log n， which is generally for n， as again。

 we care about how things as n grows。😡，For large n， that is significantly better than n squared time。

😡，But the lower bound on runtime is actually。Her， it's n times log n as opposed to n。

 which was the case for bubble sort or insertion sort。

 there were tricks we could take advantage of with bubble sort or with insertion sort to make it run quicker。

😡，Or that would allow it to end more quickly rather than run quicker if the list happened to be in order。

 but the merger doesn't have any tricks like that up its sleeve。

 So the worst case of the upper bound runtime is higher， but or sorry lower。

 but the lower bound run time is worse， hopefully that makes sense。Okay。

 and then I just want to quickly get back to why this is n times log n。

 so we have n elements in this list。😡，So in this case six。

 and we may need to merge a single element back in log n times， so log n， a log of 6。

 log the base2 of6 is slightly is between two and3， we always round that up。

 so there are three potential merges that need to happen and six elements so that's why it's n times log n and in the number of elements。

 log n in this case represents the number of merges that may need to happen for that to come into play。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_63.png)

One more sorting algorithm I'd like to talk about today is called Bogo sort。

 is this going to be better than anything else we've seen so far so let's see。😡。

Let's go back to our original concept of we have a list that's completely unsorted。😡。

And we want to try and sort it， so the whole list is on sort at the beginning。

 What are we going to do in this algorithm？😡，We're going to randomly shuffle the elements of the list and check to see if it is sorted。

😡，We can just do that via linear search， make sure that everything is increasing or greater than or equal to。

If not， repeat the whole process until it is， so we reshuffle the whole list and try again。😡。

Is this going to be better you probably can guess what's going to happen here， So we start here。

 great， This is sorted。No， it's not。That's okay， we'll try again。All right， this is sorted。

 this is sorted， this is sorted， okay， we're doing good， no。That's not going to work。We do this okay。

 problem again。And we can do this for a really long time， a really， really， really long time。

 keep reshuffling， keep reshuffling， and eventually we hit upon this after years of waiting。

With a six element array， hopefully won't take years， but with a very large one it might。

 and we can start going through this again， is this in order。

 is this in order the answer is finally yes。😡，This one is in order。😡，That was exhausting。

 This is an example of a very bad， very， very bad sortoring algorithm。

 Hopefully you're not using this in any way。 let's do this in reverse。

 the best case scenario is what we just saw if it happens to be that the random shuffle happens at the beginning。

 that would be great。 It's in order that actually would end up being better in that case than the best case scenario for merge sort。

😊。

![](img/80be6e1b19f6c21df49614851e952bc8_65.png)

![](img/80be6e1b19f6c21df49614851e952bc8_66.png)

But the worst case scenario is that we reshuffle that list over and over。

 and we never find the correct order， which is possible because we're not keeping track of all the permutations that we've done。

And so。We may check the same permutation multiple times over and over。

 and so this is kind of an interesting case where we have an unbounded runtime for this algorithm。

 It theoretically could run， add infantite， it could go on forever and so there is no way to classify this as having a runtime it is unbounded。

 but in the best case scenario it actually is just as good as the potential best case scenarios for bubble sort or for insertion sort。

😡，Which is that it would run in omega of n and bogo sort， by the way is short for bogus sort。

 it's not actually a real sorting algorithm， but it's kind of a fun way to express this concept that there are algorithms that despite having very few steps involved。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_68.png)

Can run for insanely long amounts of time to the point where there is no way to conceive in the framework that we've been discussing today。

😡，A way to express that other than to say it just is unbounded and goes on forever。 Yeah。

 I see we have a question。Would you ever want to actually use Bogosort you would not want to use Bogo sort other than for a fun illustration of what can happen with a very short algorithm if you are not careful about what you're doing or you introduce randomness into an algorithm。

 you don't want to use Bogo sort though to actually do anything with your own data that's for sure。

 but it's a good way to illustrate this idea that。Algorithms are not necessarily just confined to these nice little。

Time classes that we've been describing that if you're not careful about being precise with your algorithm。

 it can become a monster into itself。😡，Just a quick summary of where things were at the end of the day today this summarizes all of the sorting algorithm we talked about。

 we talked about five of them so generally these runtime merge sort for example。

 generally pretty good， the best case runtimes for bubble insertion and theoretically bogo sort but don't use bogo sort are better than the best case runtime for merge sort generally merge sort is considered an algorithm that is going to be among the best options that you have there are other ones that in certain situations can be better there's an algorithm called Raatic sort which does work but it it constrains the values that are in play so you can't have arbitrarybitrarily large numbers in your list for example。

 counting sort is another one you need to have kind of an arbitrary amount of space and if you can make additional constraints on your list as opposed to just being whatever happens to be in the list yes。

 you can do a little bit better than merge sort but merge sort is kind of considered the gold standard。



![](img/80be6e1b19f6c21df49614851e952bc8_70.png)

![](img/80be6e1b19f6c21df49614851e952bc8_71.png)

For large lists to sort things。All of these algorithms did exactly the same thing。😡。



![](img/80be6e1b19f6c21df49614851e952bc8_73.png)

5 ways in sorting to solve the same problem。 All of them are correct of maybe put an asterisk on Bogo sort in this case。

 But given infinite time。It is correct， so all these algorithms do the same thing。😡。

They all are correct， but they have very different runtime。

 and they have very different ways of achieving those runtime。

 bubble sort and insertion sort is's a great pair to consider because they run。

 we would classify them using our notation exactly the same way。😡。

But the process by which they do this is very， very different。😡，So。

Coming back to just bring things full circle today。

We have discussed two main ways or two main types of algorithms to talk about。

 right sorting and searching， there are far more algorithms than this that you will encounter that have nothing to do with sorting or searching at all。

 and it's very likely that you will not be in a position to be。😡，Implementing these yourself。

 but you may be in a position to be a decision maker for what resources are relevant。

 what are we going to spend our time on， what are we going to spend our money on are we going to get more server space to handle whatever large sets of data come into play and so having a vocabulary about these algorithms and being able to communicate with some of the more technical members of your team will hopefully pay dividends for you in the future thanks for joining me and we'll see you next time。

😡。

![](img/80be6e1b19f6c21df49614851e952bc8_75.png)

![](img/80be6e1b19f6c21df49614851e952bc8_76.png)

![](img/80be6e1b19f6c21df49614851e952bc8_77.png)

![](img/80be6e1b19f6c21df49614851e952bc8_78.png)