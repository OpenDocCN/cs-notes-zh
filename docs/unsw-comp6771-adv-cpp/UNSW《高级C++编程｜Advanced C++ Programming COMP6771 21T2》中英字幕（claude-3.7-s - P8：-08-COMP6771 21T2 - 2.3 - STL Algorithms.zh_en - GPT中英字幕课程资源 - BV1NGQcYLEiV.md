# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P8：-08-COMP6771 21T2 - 2.3 - STL Algorithms.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Hi， everyone。Couning down。I would count numbers， but I don't know when it finishes。Hello。Hi。

Nice nice to see you all today。 I hope you're all doing well。 hi to you too， Ryan。😊。

I'm excited to keep chatting Hi Jiangbin。Easy。ver else。

 I'll try and always say hi to people who say hi in the chat。Make you feel connected。

 I had one of my favorite YouTubeubrs the other day。

 I'm not telling you who they did a live stream at 2 AM or 3 AM。 And I like God on I was just like。

 I'm gonna make them acknowledge me and it was like， you know。😊，400 people watching live and。Yeah。

 they did， so it was good for me。😊，Hi Tom Maria me and Di Ar Mo， Dimd。🤢，Tim Ricky is Sam George。Sham。

 Nathan you all come to life here。嗯。And Ga after3， Oh， I done now。 Okay， that's it。 Everyone else。

 I'll just do blanket high。 So welcome to。STL algorithms。This is the last part of week too。And so。

 just for context。Because I' just repeat this again， because we don't have a Monday lecture in week4。

 it's likely that。We'll have to start this topic today， potentially， maybe not。

 but we'll have to do oh we'll have to do these two next week。We'll figure it out。

 But we just have to juggle some things around。 Richard says， why a giraffe， that'll be the last。嗯。

Kind of， you know， off topic question I answer for now。

 But I just think you're off to strange animals and I I adore them for their weirdness Like。

 I don't know what's going on with their necks。That's about it， they're just weird， weird。

 weird creatures。Oh， sorry， yes。 When I said do these things， I I got that confused。 I meant like。

 we'll have to do these in week 4。 Like we just have to figure out how to do because this is like。

This is。This is basically seven hours of lectures。That we had 8 hours to do。 But now we have 6。

 which would be fine。 It's just like they weren't all fall nicely into a gap。 That's all I'm saying。

 I mentioned that yesterday。 But let's get on to ST TL algorithm， so。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_1.png)

Last two lectures， we covered STL containers。 We covered STL iterators。

 We looked at doing some basic things with them， basically just like storing stuff。

 iterating through them， everything like that。 And today where can actually look at what。

Algorithms STO provide us。Um and。We kind of touched on this yesterday。

 but STL algorithms are basically functions that execute an algorithm based on an abstract notion of a pointer。

 So， you know， if you think about。呃。You think about binary search or something right Like if you were to write a binary search and see。

 you would actually maybe， you know， you might have this like abstract data type or something， right。

 that's all we're really dealing with。 It's just that we're trying to linearize things again。

 So today's a lot of going through some examples。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_3.png)

And a lot of them do with algorithms。 And we probably only need an hour。

 But what is the best way to sum a vector of numbers， So I've got this vector of numbers here。

 vector in nus pretty straightforward。 And if I want to sum them up。

I would simply do a full loop like this so I could use a four range loop or whatever。

 but if we wanted to use an algorithm to do these things。

 we would have to go beyond some of these simple examples。

 which I just mentioned the iterator or the four range loop and we would actually look at using a SDL algorithm like this one here so。

The difference here， you might be thinking， what's the point of this， right， Well。

 let's first look at the code。 So the code is。Sorry， I' just lost a Vlab。😔。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_5.png)

So if I open up the code。😊，And we go to demo 209。 You can see here that compared to demo 208。

 which uses the four range loop or this one， which uses the。

The iterators kind of iterates through them and sums them up。

 The accumulate function here just simply takes in nus begin and nus do end and0。

 So this is essentially a reduction function So for anyone familiar with filter reduce functions。

 this is just a reduce function But it needs to know where the data structure starts and where the data structure ends and that's why it takes in the dot begin in the dot end。

 It also needs a zero because if you're accumulating something。 if you're going through a reduction。

 you need to actually know what are you starting with。

 So this function will take the beginning of a data structure at the end of a data structure and it will add every element it will accumulate all the values of those elements with a base number of what you give it to start which is here。

 And then if we go and build and run that。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_7.png)

Then it'll work， right？Build lectures， lectures to。嗯。And。Demo 2，0，9。15 works like that。

 Now we could have a look at this particular library on。CPP reference。Standard accumulate。

 And you can see here that。It is a C plus plus 20 feature。Okay。

 so computes the sum of the given value and knit， which is the starting value and the elements in the range first to last。

The first version uses operator plus to start at the element。

 the second version uses the given binary operator。 so essentially what this is saying here is that。

You can call this accumulate given the first and last point and a basic。

 and it will just do a standard plus equal like operator plus on them。

 So it'll just add them together。 You know， it could be strings， ins， doubles。

 It doesn't matter like。If a type has a notion of being able to sum two of them together。

 then you can pass it in to accumulate because it will rely on the underlying type's ability to be summed together。

But in other cases， you might actually want to pass in a custom definition of how to actually sum those two things together。

 so you know there'll be some examples here。All these are implementation。 Sorry， yeah。

 some examples are using standard accumulator。 And you can actually see here without getting too into the weirdness。

 but。The binary operator that you can give the accumulator is actually a I'm not sure if it's a value or object。

 but it's basically another part of the Sl library。

 which is simply like it's like a predicate or something where you give this to accumulate。

 and it's like an instruction as to how to actually accumulate things。

 So accumulate by default will be doing a like summation。

 whereasas when we give it this multiplies object It'll be doing a multiplication。

 So this is kind of how you would accumulate numbers into a product because standard accumulate by itself or' just do it as a sum。

 You know， and you can kind of take this further and further。

 And these are some more complex examples， but。The point is it's a really nice abstraction where you just simply give a data structures beginning and end。

You give。The accumulate algorithm。 So this is an algorithm here using the begin and end iterator to effectively go through a data structure that is abstract as far as the algorithms concerned。

And you give it a starting value and the actual what they call the binary operator。

 basically how do you operate on two values， is it a plus is it or whatever。

 and we could look at what standard multiplies is。Function object for performing multiplication effectively calls operator star on two instances of type T Basically this is just a function。

 if you will， like if you want to think about it in like a more sea like fashion imagine this is like a function pointer or you know an anonymous function that you use to actually apply it as you're accumulating through it right。

😊，Yeah， so the other one that exists because you notice this is all C+ plus 20。嗯。Okay。😊。

I don't think I' ever go called that。St here juice。There you go， everyone。

 I'm going to be getting targeted ads for the next week。😊，嗯。I'm dying。 It's so funny。

 For a second there， I was like， sometimes， you know， when you。

 do you ever like want to Google something， you try and Google something and then your brain Google something else。

 And I was like， go， what did I Google。How did I get here？But no， it' I Googled these。😊，Okay。

Yeah yeah yeah yeah yeah， all right。Hope。Yeah。Yeah。

 last time something like this happened and ended up on discussion group。

Oh wow someone got an STD dating app after gogling STD libraries so there's another function out there called standard reduceuce which you'll notice actually looks pretty similar。

 it has like an input iterator to the first input iterator to the last doesn't seem to have that initial value。

😊，诶。But we can kind of look through it。Reducuce behaves like standard accumulate。

 except the elements of the range may be grouped and rearranged in arbitrary order， interesting。

Side by side comparison between reduce and accumulate。 Okay， so what's happening here， we have。

Where's our reduce？So we've got standard accumulate， standard reduce。Doesn't really look that。 like。

 it's a little bit。 I， I think standard accumulate came about to try and simplify。

Some some of the reduced function because it's a pretty basic function， like algorithm， right。

 It's something you'd ideally like to use a lot。是。So。Yeah。

 pretty much we use standard accumulate so standard accumulate is a C plus plus 20 feature if you're using older versions of C++ then you'll have to use a different algorithm but the point is you might look at this and think oh。

 this seems pointless I know how to iterate through something I don't need to use import and using algorithm but the whole point of good software design is that you are reusing semantics as much as you can you are using library so that you know there's a common definition it also allows you to do things like what if someone's figured out a way to make this more optimal now and this one's a pretty simple function。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_9.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_10.png)

But you know， and it's implemented， this is like a rough implementation。

 This is kind of what you'd expect it to be right， We'll get into templates later in the course。

 but beer in general， it's like， yeah， it's just a fall loop。

Looping through each item and summing them upright like it's not that complicated。So。

That's a simple example of algorithms， Now algorithms can get very complicated。

Let's have a look at some more examples here now。This one was shows a couple of things we've looked at。

I don't know why it's so hard to swap windows on my computer， god damn it。I just want to go to Vla。

これい that。Yeah。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_12.png)

So we're going to open another one to 11 Algoes。😊，With this。

 you'll notice that we're using a whole range of algorithms here。

 generally anytime you see STD something， well not like a whole range， but we have a few。

 so we've already talked about accumulate and we've already talked about multiplies like this。

 but you know what you can also figure out the midpoint。Of a。Data structure， right。

 because if I go and get the begin iterator for a data structure like a vector。

 and then I do like a plus equals， you know， like for this vector here， for instance， if I say like。

 you know。Auto it。Eals v dot again that's going to be appointed to the first element。

 Then if I say it plus equals 2， it's going to go from  one to 2 and 2 to 3。

 So now my pointer is to the third element or the midpoint。Right， so I did a tutorial today。

 which you can look up the recording for on Web CMm3。

 I'd probably there's a few things that I'll point you to the tutorial for because I think the tutorial goes through a little bit of detail about this。

 But generally speaking with random access iterators， which is what the vector is。

 you're able to kind of jump randomly across this linear abstraction。

 So if you imagine your iterator is a linear abstraction of the。The array。

 then you can basically just。Jump。Jump to it。So that's what we're actually doing down here when we want to find the midpoint or the like the midpoint pointer。

 we get V dot again， which is a point to the beginning and then we increment it。

By V size on two spots， which in this case is going to be， you know。

5 on2 because size is 5 on two is 2。5， and it's an inch。 So it floors to 2。

 So then we increment it by 2。 So this actually give us a pointer to the the mid point。

 And then we can do some interesting things， for instance， like。

We can sum the first two numbers or sum everything up to the input up to the midpoint。

 but not including it by saying that the sum2 is standard accumulate from V dot again。

 which is where we start to midpoint right so those are both iters they're just in different spot。

 So instead of using v dot and all the way down here we're using midpoint which is an iterator in the middle and that's how we can kind of do like a little bit of an easier sum here。

Now， you see there's a line commented out。Here， which we say like might be a little bit harder to read。

嗯。And this is another way of calculating the midpoint if we need to here。

Just trying to make this smaller。So。Here we say standard next D dot begin。

Standard distance V dot begin V dot and onto。你。It's kind of like。

 I don't think full screen would help that much it， sure。It's like。

 so in this case now let's actually break down what some of these functions do。

 So we already understand what V dot begin and V dot end is， right？嗯。

Though we have to ask ourselves the question what the hell is does distance thing。

 So let's try printing that out。 So we know what V dot begin and V dot end is。

Let's actually print out what the distance is。 So we'll say distance is that。And then I'll put a。

New line at the end， build to 11。Midpoint2 is why is it mad about that？Unused variable。 Okay。

 let's comment that out for now。Buildil 211。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_14.png)

Oh。Hello。Let everything go。There it is。Is it raining for everyone else as well， it's raining here。

 so now you can see that standard distance is literally like a counter。😊。

And you might be thinking what and God's name is that for。 Like we already have a V dot size。

 Why do we need a Why do we need an algorithm that's standard distance that goes from like。You know。

The beginning of an iterator to the end， Like， does anyone know， like， why do we need that。

 Let's look it up。 Let's have a play with it。Let' be scared to Google things for a while。嗯。

The number of increments needed to go from first to last。Okay。

 why do we use it returns the number of hops from first to last。Any ideas， anyone？I mean。

 I don't know like I'm actually asking this as an open question。 I could have some guesses。

 I'm just curious what your guesses are。Any ideas。Ahos like a step。

The length might not be equal to the number of elements。 Yeah。

 so I think there's two things that I thought about。

 And there's probably something else is that number one is there's there could perhaps be some data structures。

 that's even better。 Okay， so there's a few things we've nailed here。 numberumb one。

 there might be perhaps be some data structures who when you iterate over。

 it doesn't give you all of the elements for some reason， right， I don't know if that even exist。

 But like that's a theoretical case where you could want to use it。

 Another reason is if you have some kind of structure that doesn't actually have a sense of its own size。

 So a really good example of this might be a。Like if you want to count how many steps there are when you're iterating through a file right so because there are some iterators that I talked about in my tutorial today where like a file stream where like if you get an input file stream iterator like you're iterating through a file that you've opened to get all the elements the file doesn't really know how big it is sometimes there are some circumstances where the thing you're iterating through doesn't actually bother to keep track of the distance like size because we learned this last night that a standard list。

Kns what its size is right because it just stores that as part of the structure。 it has a size。

 but if a structure doesn't have that， maybe the only way to actually get the size is to iterate through it。

 again I'm not sure what data structures would do that probably none。

 but it's an interesting thought about like what the benefit of that is I think Forward list has a size as well I can't see why all of these structures wouldn't have a size。

Doesn it Oh， maybe it doesn't。Max size， oh， maybe it doesn't。 I've I don't really。

 I've never really used a forward list in my life。 I always just use list， but。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_16.png)

There you go， maybe that's what it is。More space efficient storage。 There you go。

 maybe I'm missing something here， but like this would be a case， right， if， if I'mright about this。

 is that it doesn't store its own size。 So you actually need to like。Look it up。So。What。What I'm。

Most interested in， though， is trying to figure out。嗯。they're very theoretical， right， Like， yeah。

 okay， I might have found one here， but I like what。So I'm just trying to find the comment。

 I was like staring off into the distance。so。Yeah， Jonah， there it is。

 so perhaps you don't want to start at the beginning。

Now this actually makes sense because what we the function we actually have here which is standard distance。

 it's actually asking for the distance not between the start and the end of a container。

But for two iterators。 So you might actually， for instance。

 want to figure out you might find a particular iterator in the middle of a container that you're looking for。

 And then you might want to say how many elements exist after it。

 And that's what standard distance can can be used for。Because you can simply say， all right。

 well this is the distance from say a midpoint or some random thing till the end。

 so it's not really like the most efficient thing you might want to use and in general。

 a lot of these algorithms are not going to be faster than ON。

Like if you're trying to sum something up or loop through something or find something。

 it's like they're all going to be ON because iterators are a linear abstraction of a container and since they're a linear abstraction of a container。

 they're not going to be fancy and fast and stuff。So this will give us the distance。

 this will give us an integer and let me just replace this here now because we know standard distance of this will give us all the elements which is5 on2。

 which we know flooraws to2 so now。I'm going to try and get the midpoint by using standard Next。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_18.png)

And what does standard next do？At the top here， return the nth successor of iterator IT。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_20.png)

So what's the difference between standard next and standard， what was the other one？



![](img/bb50045a4e130df13b3f6c5aaff5f61f_22.png)

The one we just used。Did I just delete it， I did。Distance， okay。

 so there's another thing we use today in the ch。That I want to quickly look up with you here。

 which is that we use standard advance in the tune。Now， standard advance we used in the ch。

 which kind of had a similar looking code example whereby you would get an iterator and then you would advance it by a certain number of spots。

 Does anyone know quickly what the difference between standard next and standard advance would be。

So StanX has returned the ant successor of iterator IT。Sure， somebody knows。Again。

 I know there's a YouTube flag， so I just usually wait。Alvin says Aln， sorry。

 Aln says the iterator stays the same。 Yes， so that's kind of the， the big thing is that。

Standard next actually returns you a new iterator， so you give it an iterator。

 you say I want you to tell me what is like X steps past that and then it gives you that new iterator without actually modifying the argument you've given it。

Whereas standard advance actually modifies the argument， so you can see here we give it B dot again。

 we advance it by two and the actual iterator itself has changed。

So what it abstractly points to is now different。 It's too extra。So。

Like one thing you're probably noticing already is that like the S TO library for algorithms。 I mean。

 there's a lot more than this， but it's not full of like， you know， huge， fanciful things。

 like calculate the shortest path in a graph。 It's full of。Really basic fundamental algorithms。

 which are designed to standardize your code so that when someone reads your code and they understand these algorithms。

 it's not full of loops and all these other things， but it's full of really clear like， okay。

 we're advancing this iterator by this length and stuff like that。

 So that's why even though you see lines like this here。hi look complicated。

 You can actually look at it and say， all right， Well， this is actually going go from B dot again。

 And it's going to get me the iterator that is exactly。嗯。This many steps further。

 which is just the distance to the N divided O by 2， which is just the midpoint， right。

So some other questions that have come up in the chat。 So Richard says。

 would advance be more efficient to use then。I guess。So， irrelevantly， I don't think there'd be much。

😊，嗯。You're basically saying what's the cost of returning a variable which is negligible？嗯。

But it exists， Yes， it would be， I guess， probably more performant。

 but I don't know if that would matter。Ryan says， is there a performance benefits to using accumulate algorithms or is it just for readability to use agos？

Back to the first kind of slide of C plus plus that we did the design principle of C plus plus is that。

 you know you have languages like C which are really efficient because they lack abstractions。

 but they are really yeah， they're really efficient because they lack abstractions。

 but they're really hard to make clean readable code And then on the other end here you have your like Pythons and Javas and stuff which are kind of like more abstract programs that are just really inefficient because they're abstractions are heavy right So lightweight abstraction is kind of this key word we want to think about with all of these things。

 And that's the design principle that is often used with C plus plus。

And a big part of that is that the， the principle is that if you're trying to。Find the next iterator。

 If you're trying to find the distance between these two， if you're trying to advance it。

 if you're trying to accumulate it， the abstractions that the。

STL algorithms provide you should have essentially no performance penalty as opposed to if you implemented these algorithms yourself trivially using the iterators。

 so the idea is that you shouldn't be punished for using these libraries。And so in most cases。

 they're not going to be slower。 The only times you're really going to see ST TL algorithms be slower is when your。

 which will show I'll show you an example with maps and find。 but it's basically whenever。

The container itself has a faster way to do things。

 But if you're talking about working with iterators that the container provides。

 then most of the time the algorithms will be。At worst， the same as yours and at best faster。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_24.png)

Okayキドki sir。嗯。That was a fun little interesting example with Ac。

 and this is actually exactly what I was talking about to do with find。

 except we might not actually go too deep into that yet。😊，Sorry， let me just jump ahead so I can。

Now let's talk about it now， let's talk about fine now。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_26.png)

This was also covered in my tutorial today， we're going to have a look at demo 212。

Here we have a vector。And we want to find something in the vector。

 We want to get the the an abstract pointer an iterator to one of the values in that vector。

 And we do so by saying that an iterator is equal to standard find。 And then we give it the start。

 the end iterator and a。Needle， right， like a needle in a haystack。

 except the haystack here is represented by the begin and the end iterator。嗯。This makes sense。

 And standard find returns you an iterator to the element。 And if it can't find it， it returns you。

The equivalent of the n iterator， right， So if you imagine that nus don't end。Is effectively nu。

Then what you're really saying here is like if stand Find can't find the element you're looking for。

 it will simply return null so I'm looking for it and if the iterator it gives me is not the same as nubs。

 end as in it did find something then I can print out found it and I can actually print out the value of the iterator itself and then we can try and compile and run that。

So found it for， right， so we found the number four successfully if we can't find it。

Then the iterator value will be something else。 And I'll show you this， right。

 So if I try and actually， let's just even try and print out the iterator value here。

We make this a bit smaller again。Sttanancy， let's try and print out the iterator。

So if we can't find it， so let's search for six。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_28.png)

Okay， so you can see it's printing out this， these random numbers here。 And。

 and what these numbers are is， I don't know。 I， I think they're probably random ints because trying to dereence an end iterator is undefined behaviour。

 So it doesn't return null。 I， I said it's like the concept of null in terms of。In theory。

 this points like the iterator abstractly points to the memory address theoretically one past the end of the array。

 so it's not null in this case， but it might be。For instance， if you try and print out the address。

 or if I just try and print out the iterator itself， let's see what it does。Nope。And whent let me。

 it's like， sorry， but you can't do that。嗯。Yeah， it's just grumpy。I could try and void star。

 I don't want to get into that。So。Or the address to the iterator， now let's not do that soap。

That's how you'd find something now， who's asked the question。Someone said about linear。 Yes。

 so Got says is find a linear time process。 Yes， so pretty much every STL algorithm is a。

Best case O N algorithm。 Well， I guess。I could be better。

 I should say that like pretty much all STL algorithms probably have a average case of zero unless they're using a random access iterator。

 which you can use on vectors， so you could actually binary search a vector if it was sorted。

Which is an interesting idea， but generally for something like find because it can only get the start in the end。

 it can only iterate through it linearly then it's going to be， you know， it's going to be。On。

Yeah so。I'll show you another example， let's make a list and this will be a list of events and I'll call it nus two。

 and this will be like one on map， sorry let's do a map。嗯。Y。So， map。

And we'll insert things into the map。 How do we do that again， We go。

 I should do it the proper way that we talked about nus 2 equals this。And then we do in place。

We can be a map of insta doubles。 sure， in place 1 to 1。0。And we'll do this for a few of them。Now。

In this case here， let's see if this works。 So I'm just going replace my numbs。Reference with nus 2。

 and we're going to build it。And run it。No， or not。What have I done wrong here。

 I mean I need to include Matt， that's probably one thing I've forgotten。

I don't think that was the issue， though， was it？Nope。I've tried to print out an iterator。

 So what did we learned yesterday when we looked at the maps is that the iterator to a map is actually a。

If it's a pair， right， it has two elements， so we need to go we need to do something like this and actually say second here。

Because the iterator will give us the actual pair to give us the key and the value in the map and again I'm probably forgetting something more。

 thanks everyone for pointing out my numberss to issue。嗯。What's this one now。C plus plus eras。

 I love them so much。 They make me really happy。What's the problem， invalid opera to binary？Oh。

 this is weird。I have no idea what's going on here。Anyone have any big brain ideas。Yeah。

 I know six isn't in there， but that shouldn't be giving us second compile error if we're getting some template。

Some really strange errors。Oh， should be a pair。 gottcha。 Thank you。 I get what you're seeing。

 So we can do standard pair， and then we'll do int double。Looking for 1 and 1。0。Like that。

 I think that should work。So here we're constructing a type called pair。

 which is the same as the map templates except we have that， so let's let's try this。那。

Have I done this wrong now？It' strange。To the top。Yes， no， there is a fine。 Maybe。

 maybe that maybe you can't actually。Stand a find your work。

 I'm about to get into the nus2 dot fine thing。 I'm just not sure why the。Include。

 I don't think it's that。 What is it， In opera to binary expression。 I just find these。

Let's's Googlegle it， so we got standard map。Stand a map。 Stan it fine。I don't want to， here we go。

 algorithm， stand Find with standard map。Hopefully I'm not making this up。No， okay。Ber， all right。Oh。

No， that should be fun。 So the point， the point I was trying to make here。

 which I'm just going to abandon is that while there are。

 I should have written an example for this in advance。

 But while there are certain cases where like you could say like you could get a map and iterate through it。

 right Like weve， we've seen this before we did this yesterday where we could say。You know。

4 auto I equals nus2 dot begin。IT is not equal to nus2。 n and plus plus IT。

And then we could print them out by simply going like you know standardC I。 second。

 which will get us the value， for instance， and I'll just comment this out for a sec。

So we know that we can' iterate。Through a map。And we know that it'll give us the values there。

 However， if we want to use find on it， which we could if I was smarter， we would。

Be doing it in O N time， right， Because as far as the algorithm is capable of。

 Standard find has to take a linear representation of a data structure to find something。

 So this is us using standard find， the SL algorithm。On。A standard map， the STL container。

But if you actually go to standard map。I'll look up make pair in a sec。 We can try that out。

 If you look up standard a map， you'll actually notice in its list of functions that it has a look up function called find。

And this lookout function called find takes in a certain key。So。If we just try for a second。

 what people have suggested in the。Chat， which is make pair。

 which I remember that I just don't make pe as much。Buildiel 2 and2。Yeah。

I think it takes print this sees as a function call。I don't know。那。Now， I'm digging deep。

 I'm suffering sunk cost fallacy right now。I'm so desperate to make it work that I can't deal with the thought of it not working。

I don't know。ok。Point is， point is irrespective of this。This is such a rabbit hole。

It's's fun to talk about this stuff because I like to remind people that this is a hard language to program in and that like you it's not just like as quick and zippy as something like Python。

 but it actually like is a little bit indirect sometimes which can be fun for the first couple of minutes。

 but here's the thing we have in the map in numberss2， a function called find which takes in a key。😊。

So if I want to look up， say one， instead of having to use standard find。

 I could use nus dot find and nus dot find returns me an iterator as well。

 so I could simply here say auto I equal nus dot find and then I could。Copy this。And check this。

 you know， is it equivalent to the end， even if it's not， I found it。

 And then I could just print the iterator de referenceence because at least I think I could。

 maybe not， I think the iterator might be， no， no， I need to do thisca all iterators to maps are with the pair。

Yes。Okay。So we did find it in this case。So this is exactly what we wanted to do here except instead of using the find STL algorithm we've actually used a member function on the map itself。

 Now what are the pros and cons of this， Well the pros should be pretty obvious complexity logarithmic in the size of the container so we know from yesterday that a map is stored as a tree of some sort and the keys are what's stored in the tree so it's a tree of essentially keys in each of those keys as a value。

So when we try and do find on the actual member function itself。

 because that function is being called within the container。

 it can break its own abstraction and it can essentially use its knowledge of the binary tree or whatever tree it is to find it really quick because it doesn't have to linearize itself into a representation。

 it can just use what it knows about itself。So that's the good thing about that is that it allows you to do。

Things really quickly， but。The downside is that it's less general。

 So if you wanted to say change out this data structure for a different one like a vector or something。

 you might not be able to use that anymore because。诶。How would you put it。Yeah。

 because like it needs to like， it's an actual member function of the type。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_30.png)

嗯。So。You just wouldn't work。 And that's why we don't like it。 I mean， it's not。 we don't like it。

 It's like this kind of breaks a design pattern。 But sometimes you want that because if you're using a map。

 maybe you need to find things really quickly。 So that's just something to keep in mind that there is a difference between using standard find with the actual iterators of the container and just using dot find。

 which is a member function of the container， which just happens to return an iterator。

 I hope that distinction is kind of clear。Yes， Ryan says。

 is it possible to use the dash arrow instead of the de reference I T。 Yes， I just。

 I think I've started teaching with。This sometimes because it's， it， it kind of。

Doesn't introduce a new concept immediately。 It， you know。

 you're just building off what you already know。 But yeah， both are fine， I think。嗯。Okay， great。

 So a couple more。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_32.png)

Algorithms to look at。 Let's have a look at 213 bound。 So what this one does is in this one。

 we have a sorted vector and a sorted linked list， right。

 Both two different data structures stored totally differently， but。In each of these cases。

 we want to find something。The same thing。 So we want to find lower bound。

 So if we Google stand lower bound and we don't get a STD helpline。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_34.png)

Then you'll see that this returns an iterator pointing to the first element that is not。

Less than the value。 So this goes through the list。

 and it gives you an iterator to the thing that is not less than that。 So 5 is okay，6 is okay。

7 is okay，4 is not okay。 So this is really helpful because。

I don't think we're actually doing anything with the return here。

 even though we kind of should is normally you might return something。

 So you might say like auto it equals lower bound。 and then you say like standard C out lower bound as like。

Theore。Here， like the starD reference， which will tell you what it is。

 and then we could do the same thing for this one too。Aoro I T 2 equals that。

 So this is like another simple algorithm。 right， There's a whole bunch of them。 that's just like。

 can you go through that linear representation for me and can you find the first element that's not lower than this。

And iterate it to it。And this is actually a great example of where you would perhaps use standard distance because like if you ask the question now。

 if someone said， hey， can you show for some reason it's like can you tell me how many numbers？

Exist in this after you find the first instance of 5 or something that's not lower than5。 Well， yeah。

 now you can actually use standard distance。 So you could say， well， the lower bound is actually。

 well， actually， let me change that。 I'll say like。Distance from lower bound to end。

Is actually just standard distance， which gets given I， which is the first instance。

 and then it gets given sorted Vex。dotend like that and that's it and now you can find the number of elements which should give you one two。

3， four56。So this is how you can kind of like， you know， when you see a distance algorithm。

 you think， oh， that's kind of stupid。 But it's actuallyca often you can use these and tie these together。

 And therefore， your， your code doesn't become this whole cascading mess of boutique solutions。

 You can actually spend some time。You know， reusing things that other people have made。

 which is really nice and then when other people read it， they're like， oh。

 I know what you're doing there。嗯。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_36.png)

Agoriths with output sequences。 so this one is a little bit more interesting。

 I think most of the algorithms weve looked at so far have been like take in an iterator and just like give us some metadata about it。

 but I want to point you now to standard transform and standard transform is kind of interesting because that actually mutate something so let's have a look at this。

What does standard transform do， It applies a given function to a range and stores the result in another range。

 Okay， so this is super interesting。 So what this does， this is basically a map function。 If again。

 if we go back to like map filter reduce， is if you have like。

 if you have like some lowercase things here， like ABC。

So what you actually give transform is you give it a pointer to the beginning of this。

A pointer to the end of this。 And then you might have like a new data structure ready to go。

Like here and then I think you might give it a pointer to this and a pointer to this and when I say pointer I mean iterator and what it'll do is it'll actually transform these in this case into like capital so what it transforms from and2 is totally up to you but the idea of the transform function is that it essentially takes one container a second container and it transforms all the values one by one based on a given rule。

So you probably don't。 you probably don't need all those iterators。

 But let's have a look at the code example。 Yeah， you don't。 So you don't need this。

You don't need this one here。For instance， oops， that's not what I wanted to do。Yep。

 you don't need this one here。Which makes sense， right。

 because like this is another example of like C++。Like these functions will assume。

 you know what you're doing。 So when you give it the start and the end of the like the initial container。

 that makes sense because。It's like。Well， it needs to know how much it has to copy。

 but you only give it the start of the second container because it's just going to assume that。

 you know that the second container is big enough and it's just going to copy it in blindly because it doesn't know where the end is。

 It's just like I'm just going to keep going till I like have the same number of elements。

So that's what we can see here is we have our S， which is a string， right。

 this is our before container and we give it the start and the end。

Right so it knows where to start and knows where to end。 And then after that。

 we give it out a new string。 This is like an empty string， right。

 we've basically just created a string that has a certain size and we've nullled all the characters So this is saying create me a string with a null character exactly this string size's length。

 So this string has 12 characters I guess， or 11 I'm not sure probably 11 because it probably keeps track of its size so it doesn't need a null operator a null character。

So it just creates a new string with 11 nulls in it basically And what we do here is we're trying to transform from this string into this new string。

 but the rule we want to apply is this function。 So this is kind of like a function point here。

 if you will， U dot begin。😊，To upper， so it's saying old container。

 the beginning of the new container， and here's the mapping function to apply to everything as you transform it。

And that's why if we were to then say， you know， standard CRR， print the string。

And then standard CR print the upper string， which is a new string that's the result of the transform。

Then we're going to get。Me you do。2，1，4。Hello weld and hellello worldld that's yelling and screaming。

So it's pretty cool。 right， The other thing you'll notice here is that the two up is something we've kind of glossed over。

😊，This is a little bit random， but essentially like in this case， all this。

 all this predicate thing needs to be is a function that can be given one of the iterable values。

 So when you iterate over a string， what is each value you're going be， it's going to be a character。

 right If you iterate over a vector of ins。 each kind of item is going to be an int。 So in this case。

 each character， each item is going to be a character， therefore。

 your two upper function simply needs to take a character and return a character。

 All these static cast here are a bit weird， I had to include them to meet this compile。

 But essentially all this function actually does is uses the underlying two upper function that is built into C plus plus which is another algorithm。

 I believe。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_38.png)

I mean， it's probably not an STL algorithm， so STL algorithms are kind of like these big standard ones。

 but it's an abstraction right， you that's where I got it from because it was super confusing。Yeah。

 you're just two upper it。 It just takes a character and uppercase it。

 So that's how you would that's how you would do something like that。 Pre nifty transforms another。

 another cool one。 And then lastly， we have a back inserter， which we'll do this quickly。

 and then we'll take a break， so。😊，嗯。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_40.png)

What a back inserter does。Is it gives you the output iterator for a container that adds to the end of it。

The good thing is this code is pretty simple。We have a string。Hello world。And。

What we're actually doing first here。🤢，Is we are。Using another algorithm for each to actually do like an in place transform So like a transform kind of goes from an old container to a new container so it creates like a new copy of it whereas a for each follows the same principle but it doesn't need the new container it just needs like the beginning of the beginning of the old container the end of the old container and then it says what function am I going to apply to all the variables So after that for each is called here。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_42.png)

All the characters in that string will be upper thecase。The same string， right。

 so it's like it mutates the same string。 So if I build that one。Hello weld， and then oh。

 it should oh。I might have gotten that one wrong。Maybe it， maybe it returns something。

 What does it do？ToThe result of the de referencing every iterator in the range。

I'm not sure what is wrong with this one。 I'm not sure what I've confused myself on。Oh。

I think the function， why is that even compiling？So this is weird because I think the problem here is that the predicate I'm giving it is actually just this string here。

 Oh， it's upper。 I don't know why too upper。 That's not a valid word。

 I don't know why that's compiling。 It should be too upper， yeah。But I don't know why it compiled。

That doesn't make any sense。Oh， now this isn't working。No member named on Osy， Oy， Osy。Yeah。

 I don't know why that worked with just two upper。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_44.png)

That's so weird。I'm not sure。Let。うん。嗯。嗯。Let's look at the examples。

See if I I completely missed something。4 H numberss upt again。Yeah， it should be fine。

 I'm not 100% sure what。Debugging fun times。 So having a great time today。

So I'm not sure why it's not up casing， I feel like we're using it wrong。So someone says。

 does make the two up a reference？

![](img/bb50045a4e130df13b3f6c5aaff5f61f_46.png)

Yeah。I'm not sure。 Yeah， let's see， let's see what's happening here。

 So it's taking in value so we can print that out inside the two upper。 Yeah， it doesn't change it。

's that's my suspicion is that it won't actually mutate it。 It just applies to it。

So I think I've got that wrong， What have I got that wrong with？



![](img/bb50045a4e130df13b3f6c5aaff5f61f_48.png)

4 each， mutate。嗯。Is it okay to mutate objects with four each blah， blah， blah。

Is a non modifying sequence operation。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_50.png)

How is it okay to modify the input sequence。 bh， bh， just give me like what the。

The equivalent is to mutate。I'm not sure there'd be some kind of mut mutation algorithm。

 So this one here is clearly not to mutate。 It's basically just like I don't think it's that it's a string constant or anything。

 I don't think that's the problem。 I feel like the problem is that it's。呃。

Like 4H will apply the function， but it won't do anything with the return value。

But I'm just guessing it， I have to assign the result back。I didn't actually know what this returns。

Anyway， I don't want to get lost into this rabbit hole because we're nearing the break time。

 but the point the point here is that you know this one is not a transform。

 this one is just a standard map on the items itself it's not actually overriding them that's just my fault there。

But this was just to give you a simple example because we need to talk about。The back inserter。

 So if I get myself a string here， let's actually have a talk about what this back inserter is because that's the main point of this。

 We just got an a tangent。Be a lot of rabbit holes。 So when I stand to transform。

 I want to transform my string， my hellello world string here。 So we give it the start in the end。

 And then what did we do previously as we tried to。In the previous example。

 we gave it upper dot again。Now this made sense because for upper dot begin。

 it was like the whole string was totally empty， so we didn't really like care about where to insert it。

 We just wanted to insert it from the front， whereas sometimes what' will happen is you might have a string here like say。

诶。I don't know。 me let me give you another example。 I'll just copy this across。Is， you know。

 I'm actually going to populate this with all A characters now， right？嗯。

And let me just take this back to the previous example I'm like upper dot again。

 and this should in theory。What's this actually going to do for me， let's try it out。

Then we can use the back inserter once we all understand the behavior。So this one now。

Is going to give me the uppercase version of the string。

Because I transformed it from the string begin and to the uppers begin here。

 and it essentially overwrode it because even though I kind of had this string full of A's here。Like。

 I'll show you this。We have these string full of A's。

 We just overwrote them because when we gave it to the transform。

We gave it to the start of the string， so I just completely overwrote them。I'm also print out S here。

So the point of a back inserter is to allow us to easily find the back valid value。

 and I cover this in my tube today so you can also have a look at that。

 It's to find the valid back value， not the end， but the one before it。 And I can show you this。

 for instance， if we get upper dot begin right so upper dot beginner is going to give us an abstract iterator to the beginning of the upper string。

 if I now increase this by2， let's see what happens。

So you can see what's happened here is that the transform has started applying it。2。This spot here。

The the third， the third spot instead of the first， right， Because we've iterated that by two。

 What you've also noticed here is that the string itself hasn't actually included。

All of the remaining characters。 Now like， why is that， Well， it's because string is a fixed size。

 So when we actually allocated that string at the start， it only has so much space and memory。

 and it only gets reallocated when you try and do something like you push back to it or you go read the string library。

 So what's actually happening here is that as I try and insert it further back。😊。

As I try and you increment that iterator to which we're inserting it into。

 oops that was the wrong one。It's just not working because there's not enough space there。Right。嗯。

You know， we could probably get around this by trying this example slightly differently right just by say using a let's use a vector instead and hopefully this like really demonstrates the idea So I'll call my vector of ins I'll just call it S as well and will use numbers 1。

2，3，4，5。Right， this is my starting vector。 and then for my。

So we're not going to be using upper anymore， so we probably don't need that element。

Will this still compile without it？See， I really love going on some like curious rabbit holes with you all because I think it's again。

 fun to explore， though I do sometimes get really。😊，Do you be a vector？

Chahars is not a terrible idea， actually， Thank you。Let's give that one a shot。I like that idea。

 Let's try a vector of chas。So we'll do a standard vector of cha。

 which is basically like a poor man string。And this one will have。You know what？H E LL O， maybe。まか。

So can we for each that， but we're not talking about4 each。

 we create a new upper vector of chas and let's just see how this goes。

Playing around with STL and what it can do。Note， we get a compile error。For function style cost。

 theyll type construction。Oh， we don't need that Esther。 Thank you。And the extra comma。

 I missed the extra comma， but that S was the main problem here， I think。So we can power this one。

Still the same problem。Not the same problem， still a problem。嗯。Let me get rid of a stupid thing here。

Invalid opera to binary expression。 so now it's angry that we're trying to print it out。 Now。

 that makes sense because there's there's no， like， easy way to。

To actually print that out so we could， you know， we could try and like do a little loopy thing。

 We use a four range loop right like we use auto con reference of I in S where S is the vector and then we can just like standard C I with another space like this。

 and then we can standard C R a new line at the end。So we can start with that。Right， build two on5。

Hello， segmentation faultult。So why we got the segmentation fault？That's super interesting。

 Let's get rid of this transform， right， because that's where the problem is。 So Ill show you this。

 If we get rid of this transform here， everything will work。

And the reason is because what this transform is doing right is it is trying to go from the start of the vector and then transform and iterate them in there。

 but the vector is too small I'm pretty sure， so it's not about the plus4 because the vector probably has no items in it。

 I would guess and we know this from the previous lecture because we can look at this just before we try and do the transform。

 Let's put out。S do capacity， right， Because I I think that was it because remember。

 vector has a capacity is in like a total size that it has currently before it has to。Race size。Now。

 you got to remember here。On the way， that's not working， illegal instruction。

Why are we getting illegal instruction now instead of Se fault？

So one of the challenges you have to face with transform is that transform is not like pushback。

 it is not going to dynamically allocate the array for you。

 it is literally just like mutating pointers and this becomes tricky because if you think about what a vector is。

 right？A vector， if you were to try and iterate through a vector right now。

 your vector's end iterator would just be like right at the stop。

So immediately when it tries to like， so it starts off at like upper dot again。

and then when it plus plus that， it's basically plus plusing upper dot end because there's nothing in there。

And remember what we said is when you mutate an end iterator， it's undefined behavior。 So again。

 just to reiterate， you can't， if someone says to you。

 I want you to find me the element at the end of this vector。

 You can't say auto I T equals S dot end and then go I T minus minus Like you can't like S dot n is you know。

1，1 after the the last one。 You can't do that and then go back。 Like the end iterator is， is garbage。

 It's nu。 you can't do anything with it。 That's why we actually have。

Those things like the R begin iterators so that you can actually start at the end value。

So the problem here is that a transform doesn't care what's happening with the vector。

 It trusts you to manage the iterator is okay。 And it's like if you're calling me。

 I'm going to assume that upper has enough stuff in it so we could give upper enough stuff， A B D， E。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_52.png)

Like this and try that， see if this works。This one works。

 Why does this one work Because U actually have the space to do the transform now。

 so if I try and print out upper。You'll see that it actually has the same values。 Yeah。

 when the compiler， when the compiler trusts you and you break， you break its trust， right。

 So this one actually did it upcase it。 And if I made this one even longer， like。

 let's make this vector here longer， I might say。呃。You know， I， I'll show you this， right， No space。

嗯。I don't know。What's a five letter word？I can't believe I have to think about no upper there you。

 that'll do。So we got no upper here。嗯。5，5 little word trust。 Ho。 Yeah。 So what'll happen here， right。

 is that it will override the first five characters。 But if I begin this with a plus 3 or a plus。

 yeah， plus 3， it will actually move across three spots at the start。

 And that's actually how we could override it， for instance， here and have like a。No hello。

 So it's actually overwritten the upper part because we've told it that the place to start the iterator from is actually threepa。

 Now I took this example down a bit of a rabbit hole which got us away from the point of it。

 which I don't really want to spend the time on right away。

 But essentially to go back to what a back inserter is and I actually did cover this in the tube today so you can probably go look there is a back inserter will give you the last element of an iterable object。

 So again， go see the tube today if you want to。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_54.png)

Chat more about it， like see it again， but you know， if you have these like five items here。

And you would like to get the last item。You could use dot R。 You could use R begin， of course。

 but that only works as well in cases where there's actually like a reversible iterator。

 So if I want this number 5 here， what can I do， Well， I can't do and assume this is called Vec。

I can't do V dot end。Because V dot end is this magical thing here， which doesn't exist。

I can't do V dot and sorry。Vc， I can't do V dot n -1 because we know that incrementing or decrementing a dot n iterator is undefined behavior。

 I could do V dot R begin。But this will only work for iterators that are like or dual directional。

 So， for instance， this works for a doubly link list because doubly link lists keep track of the front and the back right。

 So's why you'll see like an R begin and the C begin。 but for a forward list。Which is a singly list。

 singingly list， Sly linked list。 It only has C begin and C end。It does not have a R begin。Right。

 so that's what this， like back insert is for。 because you can't say R begin。

 That's what you normally do for any kind of bidirectional iterator。 So instead。Yan。

You will actually have to use a back inserter。 So what a back inserter does。

 you give a back to a back inserter and it goes and gets Vex begin。And it goes up。

 here's where I start and then it goes who， who， who， who。

 and then it sees the next one's the end and it says， oh， that's not what I want。

 So then it grabs this one。 So the actual back inserter will return you a pointed to that。

 So that's another example of like an STL algorithm that can be useful for things that essentially you can't get to the end right so it does the advancing from the start to the end for you so that you don't have to write that。

Same boilerp code。And I think that's probably a good summary before we take the break that。

A point of a lot of these STL algorithms is not to like cure cancer or anything。

 It's to avoid you writing more and more boilerplate code so that you don't have to like。

Pollute your code with a whole bunch of stuff that takes away from the fundamental logic of what you're doing。

Someone says what happens if we plus plus a back inserter。

 then you'll get the end right because it's just an iterator to this point and if you if you plus plus the the final iterator here then you get well。

 it might be the end or they might be like more empty space or something。

 but basically it like takes you to the last element that's there。Okay。

 let's take a five minute break and then we'll get on to Lambdas。

 which are kind of the last topic for today。😊，Yeah。

 so I'll chat to you in five or six or seven minutes。哦。

Hi everyone and welcome back from the short break So we've spent the last hour basically talking about a whole range of really basic STL algorithms it probably hasn't been the most efficient use of time and I'm sorry about that going into some of these rait holes though I guess for me at least。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_56.png)

You know C++ is kind of defined by its rabbit holes more than its features right because that's where you spend your time you probably notice this on the first assignment right like something that seems very intuitive to work you're like why doesn't this just work why do I have to read all these compileas what's all the detail here？

Though嗯。Kind of the last major thing to talk about when it comes to。嗯。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_58.png)

Algorithms in C plus plus is Lambdas。 Now， if you've done some other courses。

 you might be familiar with Lambdas。 So bear with me， we might be a little bit slow。

Though in C++ we have lambmbdas as well， this is something that isn't a feature of C。

 and essentially all lambmbdas are is a really succinct definition of a function。

That you can use in other functions。 They're often defined anonymously。

 What that means is that the function has a definition。But that it doesn't have a name。U so。

I think what might be a good。呃。I'm so confused by these code examples。 these four each things。

 I think I've been thrown off because。We like this， this code hasn't changed since last year。

 So maybe my brain has changed or something。It's not good。 So what I。

 what I might do to show you here is we've， we've kind of got this string。Here called Hello World。

And。Oh， this one's correct。 Okay， maybe I just did it wrong。 and we have a four each function。

 which you know， S begin to S and references。 Got it。 Thank you。Oh。Okay， I understand now。

 Thank you very much。 So what I want to do is I want to actually modify our previous code example。

 So rather than show you off demo 216， let's actually go back to a previous code example that had that to upper。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_60.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_61.png)

In it like this one。 And let's just simplify this in the lecture。 So we're going to get rid of this。

 I'm going to use our for each。 I'm going to do the fix that。Quunjiang has kindly kindly provided。

 thank you so much for being a bigger brain than me。

 and that is that we will take in a reference so values a reference to an unsigned chart right and let's see if this one works now。

I saw it was mentioned， but it's hard， it's hard to explain。 It's like when you're lecturing。

There is， there is like， there's a lot of stuff going on in your head and on the chat。

 And particularly when there's debugging stuff， you kinda have to just make a like some split second choices about like。

What you know， what are you actually going to look at？嗯。And I just made the wrong choice。

 I just listened to the wrong people。嗯。So what's going on here？



![](img/bb50045a4e130df13b3f6c5aaff5f61f_63.png)

Compared to this one。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_65.png)

Now， I'm like， not even sure why。Oh， okay。I see what's happening here。Let me first take this Lada。

 Let's just let's just copy what this Lada does and then we can。Then we can talk about it。

Stand a type of value， let's start with that， let's see if this one works。That should work fine。No。

 it doesn't。Because it sucks。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_67.png)

Implicit conversion。 Do we need to include all those Danant cars here。 So here's an example。

 implicit。Does it need a return value， I think here， that the problems with the two uppers。

 So this is like， this is an example of some of the C plus plus weird stuff in the previous examples。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_69.png)

It wanted。They wanted us to cast it because it basically standard to upper implicit conversion loses integer precision。

 so it's saying that it's an into a char， so if we dump standard to upper into Google。

 you can see that it actually returns an in here。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_71.png)

And it actually expects it as well。 So that's kind of strange for us because what it means is that we kind of need to static cast this to a char because standard to upper returns an int。

 and then we kind of need to static cast this one to an int because it's a char。Right。

 which is super strange。 and this will probably still give us some grief because I didn't write it correctly。

嗯。But hopefully， this should be okay。214。Oh my God。 the eternal。 Yeah， okay。

 so it does want to stir on something I'm really confused about。How that works。Oh， because it's void。

 I understand thank you。 I was like， why is it trying to take return something。

 that shouldn't be how it works， okay。This might。Thank you everyone。 What an adventure。

 What an adventure we just went on together。 Okay， so we're gonna go back to214 and you'll see that this will you know work as we originally expected to which is that two upper is applied to every function。

 and and I think the kind of distinction here that I was missing before was that it's not an application where it takes in a value and then it returns a value。

 And this is probably my jascript brain， which is what I work with every day working here。

 which is kind of how a map works and jascript is that it returns a value and that's what the mutation is。

 I guess， even though it doesn't actually mutate it。 So I'm probably full of crap but。😊。

The point is we're actually modifying it now， right so we pass in a reference to that value。

 We set the value to be the uppercase version of it。

 and we have to do some weird things with static cast because it's two upper takes in an into an in。

 So that's just a shame。 but that's how it is。This is a normal way you would deal with this kind of predicate style function pointy thing maji for each takes in an iterator an iterator and a function。

 And in fact， let's see what the C++ library calls this function。

 That is not what you search in Google。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_73.png)

What it calls this function is。Uary function。So what in God's name is unary function。

 unary function must meet the requirements of move constructible。Okay， now what does unary mean。

 Uniary means one， and the reason for that I'm pretty sure is because because we're operating on like a4 each element in some kind of iterable structure。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_75.png)

It can only have one parameter， so it needs to be a single parameter function。

 if it wasn't one parameter if it had two or more， it would fail to meet the type check for for each。

 And then naturally the actual type of the iterable here needs to match in some way。

 Otherwise it won't be able to do won't be able to pass it in validly。 And again。

 it't it won't be type check correctly。 So this works now。

The thing is is that if you're only going to use this two upper function once， like literally once。

 then sometimes you want to write it in like a slightly nicer way。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_77.png)

And the slightly nicer way you might want to write it in is as a lambmbda。 Now。

 I usually remember lambmbdas in a very strange way， which is that you can replace a function name。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_79.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_80.png)

And you can define the function in line， and it's made up of bear with me a series of three brackets。

Like this。 And I remember the three brackets because my brain says you start off with the bracket that looks the most serious。

 And then it slowly descends into chaos。 That's how I remember that。

 So square brackets look super rigid and square。 and， you know， stiff like they're wearing a suit。

 And then these ones are kind of bendy and curvy。 And then these ones are basically drunk at this point。

 So that's how I remember， I usually when I'm writing lambmbdas， I write them all down。

 And then I have to sit here and try and remember what the hell they are。 So the first one。

 the square brackets is what you call the capture， right， now， again。

 if you're not familiar with lambmbdas。The capcha is。So as you know， in a function。

 it has its own scope where if you define this function and you use a name that's not defined inside the function scope or declared inside the function scope。

 it'll be like， what's that， I don't know what it is。

 And a capture is a way where you can essentially feed things。

s feed things from outside the function scope。Into the actual function itself。 So in a lot of ways。

 you can actually kind of ignore the， the capture。 This isn't capture， like， you know。

You know what what letters is written in this image。

 This is capture is in like I'm going capture you're a dog and keep it for myself kind of thing。

 And the rest of this is just a normal function， right， This looks like a function， right。

 A function is made up of parentheses and then something in a brace。 So you can just copy this in。

Cha our am and value。 And then what， what does your actual function do， Well， it just does this。

 I'm just gonna copy that in。Now this land is huge because of the static cast。

 so this is maybe not like the ideal case for a lambda because it's quite a lengthy line here I might put this on the next line just so you can see。

 but I'll move it out here a bit。嗯。Yeah， you kind of get the point。The idea here is the lambdas。

 the capture， these， the parameters that you take in。 and then this is the body。

 This is actually what's executed。 Now， typically lambdas are actually quite small。

 I don't even know if I would use a lambda for this one because it's just so big。

 it would be really hard to read in the code I will run click format I just want to visually explain that it's like it's just this little chunk here。

 That's actually what the capture is the rest of this is like inside the for loop。

 So I could actually get rid of this now and then try and compile it again2 on4 and it would work because it's kind of like it's like an anonymous function Like that's essentially what it is。

Though this structure is just a。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_82.png)

You know， what we would call a lambda。 So if we go back to the actual slides。呃。

It replaces function pointers essentially。 And now we're getting into the。

The anatomy of a lambda function。 So we already kind of talked about this。 We have the capture。

 the parameters， the return value on the body。 Now， the return value here， I didn't include， right。

 did I， I just had my three increasingly drunken brackets。

 but I could include this here and say that the return type is a。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_84.png)

Bod。Now， I don't actually think this is necessary in this case。😊。

There might be some cases where it is necessary。Though if nothing else it does help communicate to the programmer。

What is actually happening and the funny thing is you know how we have the C plus plus 20 function syntax where we got the little auto something like。

 you know I'll show you here。 it's like we say auto main dash arrow int。😊。

One of the benefits of this syntax is that it actually aligns more with the lambda captures because there's parts of C plus plus where you would actually define the return value this way and。

呃。You would define the return value this way， so in some ways this like C++ 20 syntax actually helps you standardize your approach to these things。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_86.png)

So。Yeah， that's kind of how you do it， you have your capture。

 and then let's have a look at what some of those things are。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_88.png)

So here's another simple example and let's just dump this straight into our editor and run it or we already have it。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_90.png)

So I'm prepared， I guess。So in this case we have a main function with a vector of three elements。

 again， hint for your assignment， we expect you in your assignments to write things like this。Right。

Auto vehicleh standard vector in with that。 And then we call add n and add n takes in the vector。

 and it takes in N。 Now what in God's name is N。 Well， in this case。

 add n is saying that I would like to add a particular number。

 numerically to every single element in my vector。 So I'd like to add three to all of the vector elements。

 And we can do that pretty simply， right， We take in our vector we take a reference。

 We take a reference so that it works。 And it's also quicker， right。

 references a quicker hintend to assignment1 if you haven't figured that out and N。

 and then we do standard 4 each。Where we give it the vector begin， the vector end。

 and then we give it a lambda。Now what's special about this Lambda。

 Well what's special about it is that we actually are putting something in the capture。

So the rest of this makes sense where you have your parameters which is ant， a reference to an int。

 because every time it loops through it， it wants to take that in wants to modify it and it modifies it by simply saying v equals v plus n or v plus equals n if you want。

Yeah， or。That's pretty。 That's fine。 But we need the capture because the actual function is doing something that requires information that can't be all found and generated inside the function because typically these unary functions will just take one element。

 which is the value， and then they'll do something like two upper didn't need any context whereas this function needs context because how much it actually increases a bias based on n。

 And if you don't have n here， I'll show you what happens。 We go and build it。

And then it says n cannot be implicitly captured in a lambda。With no cap share default specified。

I'm not sure what the message means implicitly captured。Basically here。

I'm not sure if this would work with less strict compilers。 I genuinely don't know。

 We could probably try it。 Let's try and just like， run something random in。

UWith just G plus plus raw G plus plus。No， still doesn't like it and is not captured。 Okay。

 this is what just the standard。G plus plus gives us。

 You can see G plus plus is also complaining about some libraries as well。

 which is quite interesting' because4 each is its own library， which we haven't included here。

 which we really should。It's in algorithm。Tisk， disk。Yeah。

 so we need to actually include and here now。That will make it work because it's outside and essentially what that means is that C++ will make the value of n visible in the scope of this function。

Right。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_92.png)

嗯。And we're going to explain some subtleties of this that are quite critical。

I don't think I have slides for， which is good because I can just explain it。

 So here's a couple things to pay attention to with the。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_94.png)

TheThe Lambda first thing。Let's compile this just to make sure I didn't break anything。

 oop so that's not what I wanted to compile。So I can。What have I done。Oh， 21， random 21。Cool， simple。

 Now， what， what happens now if I would like to。I'll do this a few times just randomly。

 I would just like to for each it a few times。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_96.png)

This will just increase it a lot now， right， it'll go from you know 456 to 10112。

That's not how you can pile。That's not how you can pile though。That's how you compile。

 except we're not printing anything。In fact， I don't even know what I was doing before。

 I must have just been compiling and ignoring what was output。 Okay。

 so let's iterate through this vector for conorto reference item in V。 we'd like to。😊，Standard C out。

 In fact， you could use a4 each for this。 Let's just do that。 Let's do that after we do this。

I'm really dragging this lecture on longer than I think I wanted to。

 but again I like exploring these things。嗯。East cons， by the way， East cont， wrong side。

What's the complaint unused variable items because I'm not putting item out？So here we go。Perfect。

 we run it。 We get 101112。 Let's do this with a 4 each now as well。 Standard 4 each。

 I think we can do it with a4 each。Read up begin。V dot end and then let's make a capture。

 the capture takes in nothing， the parameters are an int reference。Vel。

 and then we're just going to standard C item and then that。There we go。What am I doing wrong。

 It's called Valel not item。 Got it done That should work for us now。

 And what you'll notice in this case is that in a lot of ways。

 it's actually cleaner because we're not having to do any of the fourrange stuff right Like we're just like。

 all right， we just want to iterate over this。 I mean， maybe this one's not cleaner。

 per se it's different。 But the point is a lot of the time you can replace loops Anytime you do a loop over container。

 there's probably an algorithm that will help you do what you want to do。

So now I want to show you some things with Lambdas。First thing。We can define Lambdas。

 We don't have to put them inside function。 So I just want to explain Lambdas。

Can be defined as named functions。 They don't have to be anonymous。 They just can be anonymous。

 And what I mean by that is I could say， I'm going to make like my function is called increment。

I think this works。So this also works because I'm literally just taking this which is a function。

 it's kind of like a function pointer and I'm just storing it here General speaking you never， ever。

 ever define functions anonymously if you use them more than once。

 you might want to use the Lambda syntax to make it a little quicker or a little cleaner but you know this might be how you start and I'll give it a void just to be really clear。

Now， this will also work。Wistful increment everything three times。 However。

 watch what happens when I。Increment n。 So n is the number that's passed and its's 3。

 I want n to increase by 3。Before we actually iterate through things， how will this output change。

So this output will not change because what happens is the capture when it's by value。

Is captured at the moment of definition of the function。So if you think about this program flow。

 line 9 defines the function， but lines 13 to 15 actually execute， so the body of this function。

 the value of n is not actually resolved until it's called on lines 13， 14 and 15。

 but the capture is caught and captured at the moment of definition。

And that's really important because captures can be passed captured by value。

 and then they can also be captured by reference。 So if I actually put an amphiand at the end of this and rerun this。

 you'll see what happens here。It啊。Doing it wrong， aren't I？Oh is it what is it again， is it that？

This syntax always confuses me。it's really weird。 So you write it out the front like it's an address。

 I don't like， I guess that makes sense。I guess that I guess that makes sense'cause you're like int reference n as a reference to n。

 But now I'm probably just stupid， so。This means captured by reference right so now when we run this to watch what happens we get 1920 and 21 and that's because even though we recorded here that we're going to capture the n by we're going to capture it we capture it by reference。

 which means that when we actually use it inside the function call。

 it is using a reference to n of where it's kind of used in the function here。

 So the value here is3 we capture it by reference So we kind of store this reference inside the Lambdacope。

 which is just a reference to n， and then we increment n by3 and then at the function call point。

 it's now using an n that's6。Right because it's three， and then we increased it by three。

 and since it was captured by reference， it's now the higher value。

 So that's basically something to keep your mind on is。

 you know these capture by reference captured by value things。

So changes made to the reference inside the Lada would also change others。 Oh， yeah， it would。

 But God， you would be a monster。 like that would just be bad programming。

 Like I guess you could do n plus equals one here。Oh， I'm getting。是吧。

Feeling sick just thinking about it。哎。哎。🤢，Some terrible coat。Yeah， sure， if you want to be a monster。

 go for it。😊，But yeah， it's all doable， anything's doable。

Just why we were going through this lecture。I also think I realized what actually went wrong with some of the。

So you know how in the examples here， I had。Which examples was it？

We had some examples with the two upper stuff like this， so we didn't run demo 216。

 this is with the first two upper and I want to see what happens if we try and build it。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_98.png)

So。Oh， it's because I modify it， okay？Let's get rid of this cast。 That's what I wanted to test。

 I was a bit flabbergasted。 Then I was like， oh， that's not good。 That's not what I wanted to happen。

 So let's build this as， as per the lecture slides。 Now， as you can see， this doesn't。Compile。

 and it's complaining about the implicit conversion loss soap。

I just want to give some context as to what's happening here。If I try and compile this。

 let me hash include algorithm。If I try and compile this directly with G plus+， right？

So inside lectures2， I'm just going to go G++ demo 216。It compiles and I can run it， right？

Why does it not compile when I build it？ And the reason is because G plus plus by itself。

 even with the wall where are flags。We'll tolerate it。

 but what we're actually using in this course is like with Cm。

 I don't know what it is off the top of my head because again。

 the actual environment was largely set up by Chris。Okay。G plus plus is looking kind of su。

 but essentially the， the environment that we've set up has a whole bunch of other flags that stop you doing things。

 So that's that's pretty much like why a couple of these lecture slides give us grief because I do test them all。

 though I may be im a terrible。😊，Person who's not capable or maybe accidentally miss a couple of them。

 but。I would have just missed that one， but yeah， essentially this would be fine normally。

 but there's some extra flags here and you can actually see it when you build like if you try and build this。

 you actually see the flag that triggered this。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_100.png)

Yeah， so it's， it's right。Well you can see a bunch of them here， but if you go down here。

 it'll actually show you that this implicit conversion loses precision because Inchar loses precision 4 to1 Bs。

 implicit ink conversion。 So this is a warning that's being thrown as an error。😊。

By the implicit ink conversion。So I'm just kind of giving you some I mean you know this whole world is a crazy world right but this is some context as to why this line of code was like in the lecture slides because I think when we ran this last time it was fine because I think we were running it with G++ previously。

 but in this case it's actually failed because of this implicit conversion。

 so you know this is just another reminder that all this stuff is very complicated and you know different build systems。

 different environments it's not quite as virtualized as some other things like Java Python Javascript。

We're pretty much at the end。 I think there's only a couple things to talk about which are iterated categories。

 So I， I again， I actually talked about this in my tutorial today。 So if your tutors didn't。

 you can go to my tutorial and like just jump to the end。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_102.png)

And。But I'll just touch on it very briefly， which is that。When we talk about。

Containers and algorithms being super general， where any container can be used by any algorithm and any algorithm can operate on any container。

That's not strictly true。Because certain algorithms require certain levels of iterators。

 and certain containers only provide levels of iterators。 and I know this is really random。

 but I I remember talking to a pilot once。I was somewhere overseas。

 And I was talking into a pilot who was telling me about like， you know。

 planes when they land right as like every airline pilot plane in an airport or something was rateed to a certain like capable landing。

 right。 So you might have a super advanced plane， but a crappy airport or a super advanced airport and it crappy plane and untrained pilots and stuff。

 And there are all these different levels of landings。

 And I think the top top level of landing was like。Category 3 C or something。 this is five years ago。

 so forgotten。 but basically it's like landing with zero visibility and A380s can do this。

 I'm pretty sure Dubai Airport can do this。 So there'll be instances in some of your lives where planes have landed with like the pilots never having any visibility in front of them like zero visibility。

 And like to do that， you need all these things to be true And I don't know why。

 but I remember thinking about that earlier today because it reminds me a little bit of algorithms and containers where it's like you have algorithms that might be like super capable of stuff and they need to know have certain criteria that then you have containers and only like it doesn't always work right So you have really simple。

Algorithms， like。Advance。Or next， which are just， they only go forward through things。

They pretty much just increment。 That's all they do。 And they're really like advance is a great one。

 Advs like one of the dumbest algorithms out there， just advances the iterator。

 And you can see here all these different types of iterators have the plus plus method。 so it can。

 it can happily advance anything。😊。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_104.png)

But let's have a look at this one。 if you go to。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_106.png)

Standard search。Which is an algorithm that。What does it use under the hood， I don't remember。

Someone might know。I don't think it's linear， what's the time complexity？Depends on the searcher。Oh。

 is this not。 Does this take in。I'm not too sure。I can't remember。

I remember there was a binary search of some kind in C++， but now I'm oh， here it is， Oh it is here。

 great。I thought it was just going to be called search， but basically in C++ there's a binary search。

 but I'm pretty sure it says it only needs a forward iterator。That seems really weird。

I thought it needed。AOkay， cool。😊，Yeah， I'm on the wrong website。

 I'm sorry it was it was just further up in Google。 Please don't get mad。

So this one's actually really interesting because it's actually showing you here that like this binary search。

😊，嗯。Algorithm， which you can see takes in like a Vbn Vn and a thing you're searching for。

 it says it's logarithmic。In in general， but if you give it a non random access iterator。It becomes。

Lineal， right。 And this kind of makes sense because a vectors， a vectors。Iterator is random access。

 So what that means is that， like， if you have a。You know， if I'm just writing this here， but like。

 you know， if you have a vector that's like 10 elements and you say like IT equals V dot n。

And you wantan to， you want to do a binary search on it， right？ And you know， it' 10 elements。

 Let's just say like n size equals 10。 Well， how do you do a binary search， You'd be like， oh， well。

 my first check is gonna to be I T plus 5， the middle。 And then it's like， well， if it's less than。

Right， like if you know。If first check is less than my needle。Then I'm going to say。

 you know IT plus equals。2。5 right I mean， we all get binary search。

 It's like you just keep narrowing in， but you can do that because it's a random access iterator。

 So to actually do that with a vector， the iterator can actually jump five spots in Constantine。

 it just does it because the iterator itself can be moved because it's contiguous bunch of memory。

 it makes sense the iterator is very powerful。 But then if you go to say a doubly linked list。

All it's capable of doing is bidirectional iteration， which means that it can go forward。

 it can go back。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_108.png)

But it can't be looked up directly。 it can't do plus equals， and it can't be minus equals。

 That's all it can do。So this is like a doubly linked list here because a doubly linked list doesn't have random access。

 you should know that because about linked list and then forward is a similar except it can't go backwards because it only points to the next one。

😊，Right。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_110.png)

So the point is that different algorithms behave differently and some algorithms will expect certain things。

 so in the case of binary search I thought it only took random access iterators but what it actually looks like looking at it more。

😊。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_112.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_113.png)

Which I maybe didn't fully understand。Is that it seems like it will actually take like all these iterators。

 like forward bidirectional and random access， but that it won't give you the performance benefits on forward and bidirectional。

 It can only do the login in random access。 So the point is this is something to consider because。

Some containers can't give you random access iterators。

 some containers can't give you bidirectional iterators， etc cetera。

 so keep this in mind you'll kind of see this loadeded around websites like forward iterator and stuff like that so yeah just keep that in mind。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_115.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_116.png)

But。Yeah， I think that's about it for tonight。How did I click on that tab by accident。

And why is that What did I， Oh， okay， I clicked on something。 Im I was like， I'm losing my mind。

All right。嗯。When might you want to use a Lada expression。

 pretty much any time you're writing a really tiny function。 It's about it。

 Like if you're just writing。 and， and sometimes you can actually use。Algorithms kind of as lands。

But yes， you， you come across it。 It's just gonna be tiny functions。嗯。

So that's pretty much it for today。 So just for context。



![](img/bb50045a4e130df13b3f6c5aaff5f61f_118.png)

We will go through。Class types next Tuesday。 I wanted to start it today。

 but like this was good to spend some time on。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_120.png)

嗯。This stuff isn't really that critical for the assignment。

 I don't think it really matters to be perfectly honest with you。

 It's all about classes and constructors。 In fact， it's definitely not critical for the assignment。

 So doing it next Tuesday sounds fine。 So just in terms of lectures。

 what we'll probably see is that we will。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_122.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_123.png)

Keep the schedule exactly how it is， which is doing this next Tuesday。 And then after that。

 we'll do these to the following week。Which should be fine so。Yeah， sounds good。Thanks， everyone。

 for coming tonight。 This wasn't one of my favourite lectures in terms of like。

 I don't like occasionally， you have one of those lectures where you just get stumped by a few things。

 It's the price they pay for trying to be a bit more dynamic and explore things with you。

 rather than like。😊，You know， just be like， here's a predefined example。 So sorry about that。

 I know a lot of you'll be like， oh， it's fine。 But no， I'm genuinely sorry you pay money to uni。

 uni pays money to me。 So we make sure that we do good job。 But thanks， everyone， for coming。 Thanks。

 everyone watching the recording。 Good luck this weekend。With the assignment。

Last quick thing is that Simon， one of the tutors， is writing up a post and were all checking it to post on the fire pinned that is like how to write tests。

Oh， wait， no， So that one's already pinned。 Let me find the post that Simon。Made。

 so I'll just show you now because it'll be up soon， but。Simon's basically helping write a post。

That just gives a bit more information on like how to write tests。

 and I just have to double check it。 He did it like， you know。During the lecture。😊，So yeah。

 hopefully because I know there's been a few questions about that just around testing and and stuff like that。

 And again， yeah， if anyone has any， if anyone's bored and they want to share some， look。

 there's nothing here。 There's nothing in the fun section。That's really sad。

 Someone posts something fun， and then someone else be friendly。

 and then we can all be friendly together。 Yes， thank you， everyone。

 I hope you have a great night and talk to you all next week。

 and I'll see on the forum throughout the week。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_125.png)