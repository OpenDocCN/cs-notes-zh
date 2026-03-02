# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P14：-15-EECS 281_ W21 Lecture 15 - Intro to Hashing.zh_en - GPT中英字幕课程资源 - BV1snk5BWEfc

Okay， that's interesting。 I didn't think for the for the preview。

 I didn't think I actually had my microphone turned on as a source。Yeah。

 I think based on the questions I saw people asking in the midterm I thought people were really pretty prepared and I was really excited to see people sharing what they knew and learned to anyone。

I'll say just a few words about cooking before I got started。

 the nice thing about cooking is that it it。Has a defined recipe。 It takes a finite amount of time。

And at the end of that time。I objectively know whether I succeeded or failed。

 And that's so unlike most of what I do during the day that it's relaxing for me。

I'll give people a few more minutes to sort of filter in we've got a pretty healthy number of people so far。

 but I'll just maybe wait one more minute before I get started。

So for those of you who wish you could cook， it's just a skill like everything else。

 and it just takes practice。I've had the advantage of having more years of time to be able to practice。

But that's really all it's about。Okay， let's get started for today。

So welcome back from the midterm everyone， there are still a few people who haven't taken it yet。

 I'm going to come back to that in a minute， but we're going to continue our conversation about data structures and algorithms with something called hash tables and hash tables are an implementation of an abstraction called a dictionary。

And these turn out to be things that we'll be looking at quite a bit。Um。So the dictionary。

 of course is on the left hand side of the slides and on the right hand slide that's some corn beef hash that I make my own corn beef。

 I actually started doing that before the pandemic。

 it has turned out to be very useful during the pandemic。Because I don't have anywhere else to be。

 but my kitchen。quick reminder there are a few people who haven't yet taken the midterm due to illness or other reasons and so please don't discuss the midterm until the grades go out I know that you're going to want to talk about it and it's fine if you talk privately with friends in the class that you know have had taken the exam。

But please don't do it in chat or on Piazza in public posts or。

In a couple or in the lab because there may were're still scheduling the last few people who had illnesses or other other issues that popped up。

 Also， as a reminder， if you haven't done it yet， please make sure that you complete the honor code quiz item on canvas related to the exam and and think about it you know I'll say a few words I wasn't around for the introduction as much。

 So I'll just say a few words about the honor code really quickly as。

People who go out into the world， whether you're a practicing software engineer or you use computation in your work or it's other or you're working in another space。

 all of us are likely to work in areas where we produce content or produce intellectual property for。

The company， maybe it's a startup company， maybe it's the company we work for and thinking really carefully about where you source that material from has implications。

 not just for you and for your careers， but also for your company， so， for example。

 there are a few horror stories of people who used Good do public license。

Open software code and if you use GPL license code or something like it。

 that taints the entire project that you include that code in and it turns it all into open source and so maybe that was your intention。

 maybe it's not but if it's not your intention it's a really unfortunate way to find out after you've done it that it's happened。

Today， what we're going to talk about is we're going to start by defining an abstract data type called a dictionary。

And we'll talk a little bit about how to implement those and there are a variety of ways to implement them。

There are containers that have keylookup， the simplest of those are bucketbased data structures and we'll also talk about hashing and hash tables which are a little bit more flexible bucket-based data structures in the simplest form index things directly hashing allows you to index things indirectly hash functions and compression are the two pieces of being able to do that indexing and then there's a piece a longer conversation on collision resolution we're going to save most of that for next Tuesday so we'll talk a little bit about what collisions look like。

 but we really won't talk about how to handle them until until we meet again on Tuesday。

So let's start by just defining what is a dictionary ADT。Dictionary ADT， it's a container of items。

 usually they are key value pairs， like a word and its definition。

And these this container supports two basic operations， we can insert a new item into the container。

And we can or a new pair， a new key value pair， or we can search the container and given a key。

 retrieve the pair or the value associated with that key。There are really two primary uses。

 two primary applications we use these things for if we want to track sets。

So check if something is in the set， where are the students currently enrolled in ES 281 by student ID number。

 or we could do key value storage， look up the values by keys for a given student ID。

 what are their scores on the labs and projects so far。So that's the basic idea behind a dictionary。

There are a set of operations that are that are typically desirable for a dictionary or things we might want to be able to do。

 and I'll focus mostly on the first three in today's lecture。

 So insert a new item into the dictionary。Given the particular key。

 search to see if is there is an item or one or more items with that given key and return them or remove a specified item or items defined by a key from the dictionary。

We might also want to sort the dictionary， we might want to select the Ca largest item in a dictionary。

 we might want to take two dictionaries and join them together。

Those last three tend to be a little less common in most of our applications for hash tables。

 although we'll see an example today of using。This for for all of these opt or at least for insertion。

Searching， removing and selecting the K largest ones。Other， of course。

 any basic container operations you can construct them， you can see if they're empty。

 you can destroy them， copy them， assign them， et cetera， et cetera， et cetera。嗯。So okay。

 if we want to think about dictionaries， let me go back a slide。

 so the two things we really want to make sure fast。Are these two things。

 we really want to make sure insert and search are fast。So what of the ones we know so far。

 what are the containers that are fast at searching and fast for inserting for some arbitrary key value pairs where the key is the way we search for things？

Well， if we have assorted vectors， insertion in the worst case and in the average case is going to be linear time because we have to move about half of the elements on average or all of the elements in the worst case。

So insert search is pretty fast， search is logarithmic， but insertion is going to be pretty slow。

Unsorted vectors， well， it's in certain as easy， just pp it at the end constant time。

 but searching is linear we're going to have to。Inspect half of the elements on average。

 or we have to inspect all of them in the worst case。Okay， linked lists， well， again， linked lists。

Insertion can be pretty simple， but search is again going to be linear because we have to lock the entire linked structure to see if a particular key is an element in the dictionary。

We have seen in 280 and we've talked about them in 281 binary search trees in the standard Temple Library。

 this is implemented by something called a map。And on average， this pretty good， you know。

 search is on average logarithmic insert is on average logarithmic because the tree。

 if given a random set of inputs that are given to it will end up being roughly balanced but in the worst case if we have a tree that we give it elements in exactly the wrong order。

 we end up having a really big stick and not a tree so stick not tree and then。In those cases。

 the worst case， it's linear， but those don't tend to happen too much unless we have some really pathological inputs。

 However， there's something that's even faster and that's called a hash table。

 and that's what we're going to be talking about today and on Tuesday in the standard template library。

 this is implemented by something called an unordered map。And for hash tables。

 search and insert on average or constant time。Now in the worst case they're still linear。

 so this is still a worst case linear algorithm， but for many common applications and for clever designs of our halfh table。

 these are going to tend to be constant time for most practical applications and you know constant time you just don't get better than that so these are these are really。

 really really， really welll well suited。Data structures for a lot of really important problems。

So how do we build this Well the easy way is if the set of keys are really small because if the set of keys are really small we can just have a vector of pairs so for example。

 if we had a calendar and we wanted to represent a year we just wanted one year out of a calendar well it's you know 366 days if it's a leap year。

 365 days if it's not that's pretty small we can just have a vector that has 366 entries where each entry was a pair and the key was the day of the year so we are currently I didn't do the math I should have done the math about this but it's 31 plus 28 plus 11 days that's the day that we're currently in and we can just look that up in constant time because we can index a vector in constant time and so every day is represented by one of those entries it could be a pair。

 some other fancy container。嗯。So if we have a range of integers that fits into memory。

 everything's really pretty simple， you know months of the year， days of the week。

 but the interesting question is what happens if we don't so for example。

 if I wanted to have a data structure that could include any student at the University of Michigan indexed by student ID that's an eight digit。

Digit number and so that's 100 million different possibilities and if you had8 bytes per entry which is pretty modest。

 that's just a pointer， that's going to be gigabytes and gigabytes and gigabytes of memory and you just don't have that laying around。

So hash tables to the rescue。 And the idea is that a hash table takes a very large universe。

Of entries and maps it。Into a smaller。Manageable set of entries that's much faster and easier to look up。

Okay。So the idea is we have this table。We want to locate items in the table by some key。

 the key space is larger than the table size。So the total number of keys that we could possibly have is larger than the number of entries we have in our table。

And so what we're going to do is we're going to define some function and we'll call it H。And H。

 given a key， will produce an index into this table。Okay。

So there are three pieces we need to make this work。The first is a translation step。Translation。

 given a key， converts it to an integer。Now that integer itself may be bigger than the table size that we have。

 so we then take that integer and pass it to the next stage， which is called compression。

And compression limits the integer into a valid index inside this table that we've created。Now。

 because we're mapping from a very big space to a smaller space。

 it's impossible to represent all of them without possibly having some collisions and a collision is when two different keys hash to the same value。

 sort of like when we looked at string comparisons。

 two different strings could have the same ravine fingerprint。And so we would have to check them。

 so we're going to also need some mechanism to handle what happens when two distinct keys hash to the same value and we're again。

 we'll talk about that a little bit today， but we'll really solve that problem on Tuesday。

So if we were using direct indexing like days of the year where the universe of keys is pretty small and we could represent the entire universe of keys inside the table so they're the same size。

Then we can just use the keys directly and maybe they're offset from zero。

 but we can fix that and just map it directly， so the key two would be at index 2。

 key3 would be at index 3 and so on and so forth， pretty straightforward where the key and then we just store the data that we care about in that space。

For hatched dressinging， the size of the universe is much smaller than this or sorry。

 much larger than the size of the table。So that the set of possible keys is much larger than the number of entries we have on our table。

 and that's when we use these hash functions， so the hash function of K1 might be equal to 2。

So it sits in index2 hash of key4 might be equal to3 Now the hash of key2 and the hash of key5 may happen to be the same thing they may both equal5 so we're going to have to think about how to handle that but we'll be able to talk about that later so the things we usually talk about we talk about the universe of keys we talk about the table size and the table size we typically denote as M So when you see M in the lecture what we're usually talking about there is table size。

So the table goes from  zero to m minus1 because it's zero index。

 but there are M entries in the table。Okay， we'll start by talking about translation so this first part。

 so given an arbitrary key， how do we produce an integer so convert the key to an integer and again。

 what we're eventually getting to is a hash function。

 which is going to combine that translation plus compression and we'll see how that works in a sec but for now we're talking only about the translation step。

The standard template library has a function that does this for you for most fundamental and ordinary container types called standard hash。

 and this provides translation not compression So what you get out of this is something that fits in an integer。

 then you have to be。Excuse me， you have to do something else to eventually get it into the size from 0 to m minus1。

So for example， if we're hashing names of fruits。We might choose the first。Letter。Subtract it from A。

And that gives us a zero based index of the alphabet。 So a is equal to 0。 B is equal to 1。

 C is equal to 2 and so on。So if we were given banana。Well， banana looks at the first letter。

 the first letter is B， B minus a is1， so banana sits at index1 in our hash table。

And if we're looking up what the value is， it would return the value that's associated with banana and that's three。

You can also play pretty simple tricks with floating points if they have a known range in advance。

So simple ways that will take the key， and this actually is this this will turn out to be both hashing and translation because we're constructing it by knowing the value of M。

We can take the key， multiply it by M and take the floor of that。

 which is just truncating the things past the decimal point。

 and that gives us the element or the bucket location in the array or in the vector。

Now this is a generalization of any range we happen to know so if we know the values are between S inclusive and t non inclusive。

 then we have this more general version and if you think about how this works。

 it's k minus it fors01， k minus0 over1 minus0 times M floor， which is the same as k times M floor。

 which is how we get this version。Deriveve from the general version。So as an example。

 we'll look at a range， we we say we happen to know the measurements we're going to be taking on a sensor are going to fall between the values of 1。

38 and 6。75， and we're going to create maybe we want to know a histogram and we want to know how many readings are in each equivalently sized chunk of that and we're going to look at 13 different buckets。

Well， what's the hash value of say， 3。65？And so the way we think about this， again。

 we have our function key minus S over t minus S times M。The key was 3。65， the lower bound was 1。38。

Divided by the width of the range， the upper bound was 675。 lower bound was 1。38 times 13。

 and then the floor simplifying， that's 2。27。 Take my word for it。 I checked it earlier，2。

27 divided by 5。37 times 13。It's 5。495， we're going to just take the floor of that。

 which is ignoring the park past the decimal point， and that puts 3。65 into bin5。Okay。嗯。

So pretty simple for floating points， integers are even easier。

 the translation of an integer is the integer。And then if we're going to take compute the hash value。

 we need to compress that into the table size， we just take the integer modo， the table size。

So if our table size is 13 and our integer was 15， well 15 mod 13 is equal to 2。

 so' just that's index2。This is great if the keys are randomly distributed because if the keys are randomly distributed。

 then we're going to get good dispersion， So one of the ways we talk about hash functions。

 one of the properties we talk about for hash function is its dispersion or to put simply the chances that any two keys chosen out of our input set will hash the same value。

 we want that probability to be low。Well， if the keys are randomly distributed。

 well then this can work really really well， unfortunately it's just not often the case。

 so keys are often not randomly distributed， for example。

 in the midterm for the multiple choice section all of the scores for the multiple choice section or multiples of 2。

5 because every question is worth 2。5 points and you either got it right or it's either right or it's wrong there's no partial credit on the multiple choice bits so。

So that's an example of where things just aren't particularly very random。

Another example picking a number from one to 1 that's clearly not random In fact。

 if you actually ask people to pick large random numbers like if they're picking their own lottery numbers。

 those tend to have very strong patterns to them， so when you're picking your own lottery numbers it turns out you're not very random at all even when you think you're being pretty random unless you have a source of cool randomness。

The other trick to this is that you want to pick a really good value for M。And in particular。

You don't want M in the key to always have common factors because then if they often have common factors。

 they'll often end up sort of in the same place in the ring for modular or arithmetic。

So one easy way to pick a good M is to make sure that it's prime。So you know。

 prime numbers don't have common factors with anything else unless there are multiples of that prime number。

 so that's usually a pretty good choice to pick。For translating strings。

 this is going to be very reminiscent of the searching algorithm we talked about before the midterm。

 So a simple hash function on strings just sums all of the ASI character codes and as we saw when we were comparing strings and trying to compute fingerprints over strings that is a real problem if all we have is the same characters in different order。

 So stop top pots， tops， pots and spot are all the same four characters in different permutations。

 if this is our function where we're just adding the values together they're all going to be exactly the same values。

 So not a great idea。 So that's kind of a bad choice。The solution， again。

 we're going to appeal to the same intuition that we used when we were searching strings。

Is to take advantage of character position， so just like 123 and 321 are different numbers。

Because they have the ones position。The one's position。

 the ten's position and the hundred's position。We'll do the same thing with characters。

And this is just going to be reminiscent of exactly what we talked about the Tuesday before the midterm or a week ago。

 I guess a week and a half ago now。That instead of adding up the character codes。

 we'll view them as decimal numbers and we'll have this， we'll take the first one。

 multiply it by some factor， then add the second one。

 multiply the entire set by the same factor at the third one and so on and again we're using base 10 just to illustrate we usually use a larger number and we use the sort of numbers that we talked about when we were talking about ra fingerprinting。

And the advantage of things like raine fingerprinting or other techniques that use position。

To be able to influence the output or the order in which you see them influences the output is that just having permutations of the same inputs usually gives you a different output。

Okay， I'm going to just do a quick break and see it doesn't look like we have any new questions again。

 please feel free to use questions in the chat I believe we have someone who's moderating the chat for us and who can address them and I'll also periodically take a break and take a look and see if there's anything there。

Okay。So once we have this integer， so we have some way of taking most of the things we know about so far and converting it into an integer。

 we need to compress that into the range of0 to m minus1 for our table。

So the tables from0 to M minus1。And of course， the thing that we produced from our translation function could be less than0。

 or it could be equal to M or greater than M， which would put it outside of the index of the range。

So there are two techniques we usually use if we control the choice of M。

 so if the person writing the hash function。Also controls the choice of M。

Then we'll pick M to be prime and then just use straightforward modular arithmetic。

If we can't choose both the hash function， sorry the hash function and the size of the table。

 what we do is we ensure that our hash function has some prime factors in it to minimize the chance that they have common factors between the two。

So we'll take two prime numbers A and B， we'll multiply the hash integer by a。

 we'll add another prime B to it， that will probably not have very many factors in common with M that someone else has chosen for you。

And the really important part is that a mod M had better not be equal to zero because again。

 because of the way module arithmetic works， if a mod M is0， if a mod M，Is 0。Then a times anything。

Moud M is also zero which takes the hash in doubt of the equation。So as long as we're choosing。

Different numbers for A and M or A is not a multiple of M。 We're usually in pretty good shape。

 A is not going to be a multiple of M because A is prime。 So as long as A and M are't equal。

 we're in pretty safe territory。Okay this together， this composition of the translation。

 which given a key gives us an integer and compression。

 given given that integer gives us an index into a table of known size is the index for the table。

So going back to our fruits example。Lemon。So L minus a is 11。11 is larger than seven。

 so we're going to mod we're going to have to take 11 mod8 because our table is  eight。Oops。

I got jumping a little ahead of myself， so this is off the end of the table we're going to have to do something about managing this piece。

So how do we pick M？Because picking M well， so let me step back a minute。

As you're designing a hash table。You have basically three choices to make how do you compute the hash function？

And or how do you compute the translation function， And that should take。

 given this set of input that you expect should give you a relatively low low。Random output。

Given that。Compress it into the index。So you have choice of the hash function。

 you have choice of the compression function and you have choice of M the table size。

 so we've looked a little bit about how to pick translation translation functions that work well for individual elements we just want to map them into the range for larger things we want to take advantage of serialization and the order in which we see them。

嗯。When we control the size of M， we just pick a prime number when we take the modulus of it。

 we don't control the size of M， we have this multiply and divide or multiply an addition technique of multiplying it by a prime and then adding another prime。

But that still leaves the choice of exactly what are we going to pick for them。

And the basic idea is that we want it to be about the number of elements that we're going to see if we're not entirely sure we want to guess a little high because the idea is we want the indexes that come out of this composite function of translation and compression or the indexes that come out of the hash function to be scattered across the entire table and try and use all of it is possible。

 if the table is much smaller than the total number of elements we're going to see we're definitely going to have a lot of collisions and then we start running we start running a file of this constant time idea that we're trying to get to。

嗯。So one of the other tricks that happens for example， in the STLs version。

It picks just like the vector picks an initial size and start creating if you start need more space。

 it'll grow it。The hash table implementations in the STL will also monitor how large they get and if it looks like they've chosen too small of a size。

 it'll automatically grow the table and growing that table is an expensive operation。

 but it allows you to keep the individual operations much less expensive。So for the example。

 and like I said， I got a little bit ahead of myself。We're going to start with lemon。Lemon gave us。

11。For this。11 mod 8 is 3， so the index for lemon is 3， and we'll put it in。Three。

 and if we had mango， while mango would go in four， pair would go in seven。

Now let's imagine we have orange， orange goes through this。Orange is one is before pair。

 so it's going to end up being where grape sits in six。And。That's a collision。

We're going to we're going to have to figure out what to do with that and again。

 we will solve that problem， but we're going to solve it on Tuesday。Okay。So。The basic idea so far。

 how do we think about these？Hash tables are a。A data structure designed to make insertion。

 search and removal by key very， very fast。Hhing a key。

Takes any arbitrary data element and converts it into an index into the table。Does that in two steps。

 It translates the key into an integer。then takes that integer and maps it into the range 0 to M-1。

 So the hash function is the composition of T and C。Okay。

 we have a question I'm still confused on how search and insert both run in constant time we're going to talk about that next we're going to talk about the performance analysis。

 but the idea is if you don't have collisions，If you don't have collisions。

If you never have collisions。Then everything is in a unique space and there are never two trying to be in the same space。

The hash function is constant time。Because it's independent of the size of the table or the number of elements in it。

And then indexing into a table is constant time， that's just indexing。Yes。

 oh and that's exactly right so hatching is constant constant and and when I say constant I mean constant in the size of the table and in the number of elements in the table。

 it's not constant in the size of the elements so。If that is a little bit。

 but when we're talking about data structures， usually we're talking about the number of elements in the data structure as our N。

 we will sometimes think about other things in our complexity analysis， but from 50。

000 feet we're really looking at just the number of elements in our container。

Would I mind slowing the pace of lecture a bit， that's a good question， thank you， and I apologize。

 I do tend to go really fast。Um， it is one of the things that I am。

 it's one of the reasons why if I if we were doing this in person， I would not use slides。

Writing on the board forces me to go more slowly。And I will try and do that now， I'll try and。

Slow myself down I apologize i'm not used to doing this remotely yet and it's easy for me to go faster so Michael thank you for for bringing that up and bringing that to my attention。

嗯。So let's come back then for those of you who have found this a little fast， can you？

Can you pose a question for me because maybe we have a little bit of time and I'll come back to the summary page。

And this is one of those times I really wish I had background music。Okay。First question from Elliott。

 do we have to worry about what is actually happening in the hash function or will that be abstracted in the future？

And the answer to that is it depends。The STL， which we'll see in a minute has a hash function that you can use actually I think we've already talked about it briefly that knows how to hash individual elements。

 so all of the basic data types， strings and containers。But containers by identity， not by contents。

There are ways to compose those as well， and there's a library called Boost that gives you a pretty effective way of doing that。

U but if you're writing your own hash table containing your own kinds of containers。

 often you also have to write your own hash function and you can use these individual elements to compose them together。

 but you will still have to sometimes think about that。嗯。Okay。

 if we want M to be about and what is the advantage of using the hash table？

The advantage of using the hash table is it doesn't have to be perfect。And so。

Because there are collisions in practice。And so you're going to need something to manage collisions if we never had collisions。

 this is pretty simple stuff， but it turns out we're going to have to deal with collisions。

Will we be implementing one of these I think so I haven't looked I haven't taught this class before。

 so I don't remember， I don't actually know what we have in store for you because I'm discovering it while you are too。

 but I think the answer to that is going to be yes I think you're going to get to implement one of these。

嗯。Septic， that's right， you've given a key， you translate it into an integer。Given the integer。

 you compress it into the range of your hash table and then make you have to deal with what collisions look like。

How do you pick M， you pick M basically by guessing you have to know a little bit about your application or you could write a version that's adaptive。

 so if it turns out you pick M and you ended up picking an M that's too small。

 you can take a bigger M and convert everything from your old table into this new bigger table and then move on。

 just like if you have a vector that you run out of space for。

 you allocate a bigger chunk of memory you copy the old vector into the new vector sorry I felt myself going fast again。

You copy the old vector into the new vector， and then you go on that copying and building and growing operation is itself very expensive。

But again， because of amortized analysis， we get to spread that over a bunch of prior insertions。

So as long as， for example， if we're growing our if we decide our hash tables occupancy rate is too high。

 as long as we're growing our hash table proportional to its original size， some function of that。

 we get to amortize the growth costs over all of the insertions。Alan。

 what is the advantage of making a custom hash function？There are a couple。

 one is that sometimes for more complex classes and structures。

 there isn't a predefined version of the hash function available， so sometimes you just need it。

There are also times in which you may know more about the input than the generic hash function knows。

 so the generic hash function is written under with some assumptions that the input is roughly random that it doesn't have repeatable patterns if you happen to know something different about your input。

 you know， for example， it has distinct patterns in it。Then， there are。

Then there are some reasons why you might want to write your own。And why can't we combine。

 translate and compressed by just making sure we translate into the range of M， we can sometimes。

 and for example， when we looked at the version of ranges of doubles or floating point numbers。

 that did both in one step， but sometimes we sometimes the reason to keep them separate。

Is something called separation of concern。So it may be the case that the person implementing the instantiation of the table doesn't know in advance how big it's going to always be。

 in which case they have to be decomposable。The advantages and disadvantages of individual translation and compression methods。

 I'm going to save that one maybe for the end of the lecture because it's really subtle and it depends a lot on exactly what your input is and exactly what your table size is。

And even for the stuff that happens to be in the STL， they're a little ad hoc。Okay， so again。

 thank you for letting me know I was going too fast。I really appreciate it， yes， Connor。

 the worst case is still linear and it occurs exactly if all of the elements hatch to exactly the same value it's linear and that can happen。

嗯。So now we'll talk a little bit about how to analyze these and some applications of them。

 and I've also got a demo lined up today as well。

![](img/997e10cf19c63a912dab876423818527_1.png)

Okay， so this actually speaks a little bit to Michael's question about advantages and disadvantages of good translation and compression functions。

So hash tables for hash tables to work。You have to have good hash functions and good is in quotes for a reason。

嗯。So there are some musts。They have to be easy， they have to be fast。If the hash function is really。

 really slow， then it doesn't matter what else anything else does because it will dominate your time because you have to call the hash function every single time you insert or look up in the hash table。

 so every operation on the hash table invokes the hash function at least once。It must be complete。

So if you have a key， you've got to have ah function， a hash value for it。

You can't have keys for which you can't compute hash functions。So for example。

 if you're ever dividing by the key， while the key can't ever be zero。

 that's not a good hash function。Also， it has to be deterministic。So by deterministic。

 let me write that down。Deterministic。A deterministic function。

 given the same input always gives you the same output。

So if you call the function on the same key twice， you would better get the same value。

So these are the absolute must dos， those are not optional。There's also some shoulds。

So your hash function should distribute the keys roughly evenly in the table。

And that minimizes these collisions， and remember， a collision is just when two keys hash to exactly the same value in the table。

 that's a collision。Okay。So let's take a trivial function， which is just given a key return zero。

Well， it satisfies the musts。It's easy to compute， I just return zero， that's not too hard。

 It computes a hash for every key。 there's always an answer， it's zero。

 and it computes the same value if you give me two different key two keys。

 you give me the same key two different times， I'm going to give you the same answer， it's zero。

No problem， but it's really， really bad distribution and it maximizes collision so that's a terrible idea。

Okay， whats the complexity of hashing， assuming we have a really great hash function。

 So if we assumed perfect hashing， in other words， for the inputs that we happen to have in practice。

And the table size we've chosen will never have a collision。Okay， that's， that's perfect hashing。

Well， if we never have a collision。Then when we run the hash function。

 the hash functions constant time。We look in the index， indexing is constant time。

That's one same for search， same for removal。 We always find the right place in the table Comp this constant hash function。

 And there's nothing else to do once we found the right place in the table were done。

So that'd be great， it'd be nice to live in a perfect world， I really wish the world were perfect。

Ain so so for example， remember the birthday paradox that if you have a group of people chosen at random。

How many people do you have to have in the room？Before you have a 50% chance that two of them have the same birthday and I look this up。

 it's about 23。So there are 366 different potential birthdays， let's ignore leap day。

 365 potential leap days， but as soon as you have 23 people in the room。

Ods are better than average that you've got two people with the same birthday。

 So pervataing just isn't something that will ever depend on。

And then to get back to the question that we've talked about a little bit。

The worst case run time is linear because if they all hash to the same value， you get the same thing。

嗯。Yes， exactly， Frank， it's 203 Prion Hall。They that's linear。

 the average runtime is the average number of collisions you have typically。

 and as long as you've chosen good ash functions and good sizes。

 that average is pretty small and roughly constant。

The STL provides several different mechanisms that give us hash tables。Seets。

Are data structures that just want to count membership so they don't really they don't have key value pairs。

 it's just the key and the question is whether or not the key is in the set。

Multiets allow you to have more than one instance of the key。Seets are unique。

 there's only one instance of the key at most。Maps are pairs。Actually， let me fix that。走。



![](img/997e10cf19c63a912dab876423818527_3.png)

So maps are key。Value pairs using。The pair template。

A map has only one instance of a pair per key at most， it has either zero or one per key。

 a multimap allows you to insert more than one pair with the same key。

If you've ever used a database and you have the indices of a database are built on top of hash tables。

 compilers use hash tables to track identifiers in this set。嗯。

So here's a really simple program that uses。Unored map。 and before I look at this。

 let me take a look。Would unordered sets so the question is do unordered sets and maps only work with perfect caching。

 the answer that is no， so the STL versions of these account for collisions as well。

So using an unordered map what we're going to do is we're going we're going to store the number of days that each month has now we were really doing this we would track we would convert months to integers January would be zero February would be one and so on。

 but let's assume that we're not doing that so we're going to map from strings。To integers。

So given a string， we're going to be able to talk about an integer。

The simplest way to add items to an unordered map。Is to use the subscript operator。

So the subscript operator brings the object into existence by calling its default。Constructor。

 so the default constructor for integers is defined。 It will set it to 0。

 So this instantiates an entry in January map to 0 and then sets it to 31。

And we're going to do this for all of the other months by recording the number of days and again we're going to ignore leap year because it's just a pain。

Then we're going to ask the user well， give me a month。I'll tell you how many days are in that month。

Well， the simple way is to look it up， but you know， that doesn't mean if the user handss us。

Super caliraagulistic exppilaosius， that's not one of the months。

 but if we subscript it it will create it and this will tell us that the month supercaliraagulistic exppiialidosius has zero days。

 so this part not a good idea。Instead， we use the find method on the key。

So find take something of the keys type。And it returns an iterator。The iterator。

 we check to see if it's equal to the end iterator on that container。

 if it's equal to the end iterator， that means it wasn't in the container， otherwise we found it。

The first value of the pair is the key， so that's the month。

 the second value of the pair is the value， that's the number of days so if I had entered February which happens to be my favorite month because my birthday is in February。

 then we will say February has 28 days again accepting leap day。Okay。

 where do these things get used most often？If we're creating sets， integer values we've seen。

 strings that we've read， images we've processed， class objects we've observed。嗯。

Setets of collections of things we can ask， is something in the set。

 we can detect whether there are duplicates。嗯。Find unique elements and and one of the other cool things you can find matching elements for pairs。

 So for example， if you wanted to see if the negation of something is in the set。

 so a plus if a is4 we're looking for the value that we add to a that we give you zero we can look up negative for in the set So if we're looking for matching elements sometimes that happen that's a useful trick。

For key value storage， so these are the set。Types for the maps。Or the key value storage。

 where we're looking at values by keys， one thing we might do is count instances。

So the value type is an integer。So how many times have I seen the word super caliraagilistic Xbiodosius？

We might use it to maintain sparse vectors， so the space we're measuring is very， very large。

 but the population of that space is quite small， in which case the key is the index in the larger vector。

We could also use it to maintain link structures where the two types are the same。

And the value for one key is the key for another value。And we create chains of things that way。

 So are a bunch of different ways that this can be used。What about sorting a hash table？

Sorting's tricky。Because of the way the hash functions work。

 we're going to end up sort of randomly distributed things that are not going to be in sorted order when we have them。

 and we cannot sort them in place。And we can't sort them in place。Because that's funny。

 happy be birthday to everybody here unless it happens to be your birthday today。

 if it's your birthday today， happy birthday。Um， and happy onbi to the rest of us to continue my Disneya sort of theme。

We can't sort these in place because the hash if。Grape moves higher in the list will never be able to find it again。

 So when we sort a hash table， what we usually do。I we copy it into another structure， sorry。

 let me go back what we usually do is we copy it into another structure and then we sort that or we insert it into a sorted structure。

And so one thing， if you need a hash table sorted and you're going to need it sorted a lot。

We often will just store the same elements in two different structures， one that keeps them sorted。

 one that doesn't。We could also use there are ordered versions of the map。

 which we could also use if we only need it sorted at the very end of doing a bunch of inserts and lookups。

 we then we'll just do the copy and sort it somewhere else trick。So to sort of catch up。

hing is hashing when you choose good hash functions and good table sizes is very efficient for insertion。

Search and removal。It's not particularly efficient for either sorting or equivalently selecting the K largest item because you can't do either of those in place。

 you have to copy them into some structure。They're not asymptotically slower than the obvious algorithms to do that。

 given all the insertions and removals， but they do require this extra copy step。

So another example where you might want to use something like a hash table is a book index。

So for each term of interest and maybe you define the set of terms that you really care about。

You scan the entire book and you store all of the page numbers at which each of those terms exists。

At the end， then you sort the terms alphabetically。😡，And then。

You can produce the overall sorted index。After you've computed the page numbers。

 so computing the page numbers using a hash table for each term is relatively fast。

 and then we're just going to sort it， there's an extra copy step。

 but hopefully the number of terms is small relative to the size of our book。

 otherwise the index is going to be half of the book。Okay。

 this gets to a little bit why might we want to worry about other hash creating our own hash functions？

So for example， suppose we wanted to map all of the places that are currently providing takeout in Ann Arbor。

So we would put dots over individual geographic locations。

And we would want to hash the longitude latitude pairs or hash the XY coordinates in our map。

So how do we combine those two functions？Well， one is that we can hash the first value。

Haash the second value multiply it by some interesting number， probably a prime。

 and take its modulus。And the question is， does that generalize to larger objects？

It doesn't generalize in the easy straightforward way。

By just multiplying some things by P and other things not。So if we're only multiplying a single time。

Because remember， our good hash functions have to be fast。

And they have to provide even distribution of values。

 and they have to not provide collisions commonly。So if we just take a hash value and multiply the other ones by some prime P and add them all together。

 then we lose the order of。Everything other than the first one。Because these two are the same。

Because p times H3 plus p times H2 is the same as p times H2 plus p times H3。This。

Is the combiner I alluded to earlier。That's in the boost。Library。

So the boost library takes a of boost library combine， takes a sequence ofary elementary components。

 an integer， a double， a string， a container， things for which the individual hash function is defined。

 and combines them using this particular function。This is an XOR for those of you who have taken 270。

 or I think we also talk about this in 203。U。C as some interesting large prime number。

 this is bit shifting to take the prior value and spread its bits out and plug the next one sort of you can think of in the middle。

So this turns out to be pretty good in practice， although I don't know that there's a formal analysis of it。

 and again， it is one that's provided in something called the Boost library and I'll put a pointer on Piazza to some of the documentation for that after the lecture' is over。

All right， so the next thing that'll come up is that it is often pretty common for once you learn about hash tables。

 you're going to want to use them everywhere because they're so cool right， I mean maps。

 if I have a thing and I want to look up some other thing， let's just use a map it's great。嗯。Now。

 there are some reasons why you might not want to use a hash table and use a simpler data structure。

The first is that there's， there's a pretty serious space overhead。

 So every single one of these elements in your table。Contained。

Some pair now it may be the uninitialized pair， maybe the empty pair。

But but it contains space to hold a pair or a pointer to that pair。

 So there's a bunch of space overhead， especially if you end up mapping from keys to some other complex data type。

 now you're starting to talk about some pretty serious space if you're not doing it by reference。

Second reason is that every access computes the hash function， again。

 if you can get away with just indexing directly， index directly and avoid the hash tables because the hash functions do add time。

And as we mentioned， sometimes they are linear in worst case and that includes the STL implementations。

 so you sometimes even though maps are conceptually simple。

 they're a little bit more complicated in theirre easier， simpler ways to handle things。

So what are those times？Again， we talked about this at the beginning of lecture when the key space are small。

 a small integer range， just use bucket arrays。So in the example we used earlier where we mapped strings of month names to keys。

 it might be easier just to map from month numbers to days and then have a lookup table just on the months。

You're still doing the comparison， but even that's pretty quick because you only have to compare the first several letters of each right。

 I think once you get to three， you're done because JU is the only prefix that that applies to more than two months if I remember correctly off the top of my head。

So lots of things can be coerced into a small integer space， enumerations。

 so if you're using an enum type that can be coerced into a small set of integers。

 simple fractions can be coerced because you can order them。Months and the example I used before。

 so anything like that where you have a really small universe of keys that you can somehow map to zero to n minus1。

 just use a vector。If you're not doing a lot of dynamic insertions and removals or insertions or removals。

 you're just going to create a big bunch of data and then do a bunch of lookups on it later。

 so in other words the insertions or the creation of the data structure happens and then later you're going to do a lot of lookups。

Maybe you just want to sort the thing and do binary search because logarithmic is still pretty fast。

 I don't get upset about logarithmic time。 I'm happy about logarithmic time。Also。

 sometimes you're not doing individual lookups， but you're going to have a set of key value pairs that you're going to repeatedly compute over in a streaming algorithm that you're going to compute whenever you compute over any of them。

 you compute over all of them。And when you're doing that and you're not looking them up randomly and individually。

 a list or a vector is just fine because you can do the walk of the thing really fast。

 because then lookup doesn't have to be quick。So for this version。

We're not we don't have to interleave insertions and lookups and so building a sort of data structure allows lookups to always be fast enough。

For this version， lookup doesn't need to be fast， just insert。Okay。So the next thing I'm going to do。

 and I'm going to give you a little bit of time， take a couple minutes。To download if you'd like。

 from a web browser， you can download the hash table。

 the example word count from a terminal you can use W get and then this is how you obtain。

The source file and if you want to compile it yourself， this is how you compile it。

 So I'm gonna give people just a couple minutes to do that。

 I'm gonna to get up and refill my water glass and then when I come back we're gonna take a look at first any questions that might have come up in the chat I also like to find out if I managed to slow down a little bit I think I did I'm not sure So if I did manage to do a little bit of a better pace there please let me know and then we'll come back and we'll take a look at this word count demo we'll take a look at the code we'll run it on a couple examples and check it out I slow down ya I slowed down that's awesome All right I'll be right back。

Is that a zero？Or the letter O on the W get line。Good question， It's probably supposed to be an O。

But it probably is a zero。Yeah thank you， Yeah it should be it should be a letter。

 but I'm wondering if maybe it's not。Yeah。And we can do a couple more minutes if other questions pop up into the chat。

Yes。One thing that I'm also doing， and I'm going to put this in the chat。

 I'm also using the text from Hamlet。If you want to grab that。

There's a GitHub repository that has the text， you can download it。It is public domain。オッケー。

Let me get things set。So if I'm going to go ahead and navigate away from this。

 the slides are online if you haven't quite downloaded it yet or you're having trouble downloading it or compiling it。

 the slides are online so you can get access to the command line。And then。

 but I'm going to go ahead and switch to my editor。Okay。This is the program as it's downloaded。

I'm going to。Move it a little bit for myself。So what I usually do when I'm looking at a program。

 I start at Maine and sort of。Look at it top down rather than bottom up。 So let's do that。

 Control S searches for main。Oh， and I'm using Vmax because I'm old me。

I don't learn new tools very well。So this is our main function。

The first thing you'll notice is that we're using an unordered map。This maps from strings to sizes。

 and so the idea is that we're going to look at each of the words in an input file and we're going to count how many times we see that word。

A couple other functions， there are a couple other variables we need， we need a file name。

 the name of the file that the user is going to give us to open。

 we need a little variable to hold the word that we're looking at right now。

The input file is what we're going to use the file name to open。This other thing is kind of cool。

 this vector of word count pair。Which is the sortable version of it。

 So what we're going to do is we're going to read our words into the map and count the number of instances。

After we've read them all in， we're going to sort。By the number of。

ByBy the number of occurrences and then print out the top few of them。

So I also want to look at this word count pair because this is kind of a cool thing。

So reverse search。So this。is basically a type declaration。

So this declares word count pair to be a new type。And that type is a pair。

Of string as its first element。And a size T as its second element。Okay。😊，So come back down to。う。Okay。

So this is our vector of word count pairs。嗯。Then we're going to。Ask the user to give us a file name。

I'm trying to type it into the wrong thing last user to give us a file name。嗯。

Then we'll attempt to open it。If we were not successful opening it。

 we're going to ask the user to input another file name again。

 so this is kind of taking advantage of the fact that open leaves in file in a false state if the file doesn't exist。

Once we've got the file open， we're going to loop reading every word out of the input file。

And then there's a cleanup function and I'm not going to scroll up to look at it。

 you can take a look at it offline， but the basic idea is that it removes any punctuation。嗯。

So removing punctuation would include this so。I the apostrophe becomes isn't without an apostrophe。

 another example， size T would become size T without the underscore。And then forced to lowercase。

Just does things like Hamlet。Becomes hamlet。And so on。Then we're going to clean up the word。

And if the word has any length at all， in other words。

 if it wasn't just punctuation or something that doesn't have any letters in it。

 because the cleanup is going to remove anything that's not alpha numeric。

Then we're going to increment the count。In our map， remember counts。Is a map？From strings。

Two integers。We're going to increment the entry at this word。Buy one。Okay。So this， once we're done。

 once we get out of this loop。We've read all of the words from the file。

We've converted them to this normal form。And we've counted the number of times we've seen each one。

Now what we want to do。Is we want to sort。The unordered map。

 if we just iterated over the unordered map directly。

 we would see things in some kind of weird random order。

 just whatever the hash function tended to produce for indexes。嗯。

If you use a map instead of an unordered map， so that's an unordered map。

 and remember that's what we chose is we chose an unordered map。If we used a map。嗯。

Rather than an unordered map， they would be sorted by key value。So。Oh， I can't remember。 I。

 I should remember the characters from Hamlet。 I don't remember at the top。

 so his old would be before or actually no H。HI， his sold would be after Hamlet。

 it would help if I remembered the alphabet。So if we switch to a map， they would be ordered。

 but in the orders of the key names， not in the orders of the values。

 we want to sort on the order of the values because we want the most common words。嗯。

So the simple way。Is push the pairs。Because remember， counts is a map of pairs。

Push them back into asorted assorted assorted。Thing instead。

 we're going to do this usual trick we do。 We know how big we want the array that we're going to sort will eventually be。

 It's the size of our map， so we're going to resize it。Then we're going to use copy。

From this input iterator range， this should be a little familiar from。Question when， well， maybe not。

This will take the input range from counts。It will copy it into the range at beginning and sortable。

And then we're going to use the standard algorithm sort to sort the whole thing for us。

Then we're going to。Get the minimum number of。Of those display count。So either display count。

 which is a constant and I think it's 10。Let's remind myself what it is。Yeah， so it's 10。

 so we're going to， we're going to count the 10 most。Common words in our text。So。

But if the number of words we saw was fewer than 10。We better not print more than that。

 so we're taking the minimum of either how many words total we saw in our input and the number that we want to print。

And then for each of those， we're going to print it out。All right。So I didn't。

 I don't think I changed this other than add in some comments， so I'm going to compile it。

And I've already compiled it once， so my editor remembers the compile command。Okay， it's compiled。

Now I'm going to run it。It's a word count。I don't think I have a food bar text， so that didn't work。

 it didn't open。Instead， I'm going to use Hamlet text。Great， it worked。

 so the most common word in the play Hamlet is the。The second most common word is and。Boy。

 this is really I interesting。Let's see what if we can find something more interesting。

 so instead of looking at these small sort of one， two， three letter words。

 let's take a sort of a minimum size of the word that we're going to treat before we before we consider it significant enough to count。

So let me go back to the word count。So this is the thing I'm going to change what I'm going to do instead is。

Let's have five instead of， let's say if it doesn't have five characters， we're not interested。

 this still will get us some kind of boring ones， I think， but we'll try it。诶。Recompile it。

And run it again。Interesting， so better。You know， unsurprisingly。

 the word Hamlet is the most common word in the play Hamlet should is next father the father was。

 if you've read the play， you know， father is complicated， Horatio。

 so I'll take a quick look at the questions to see if we have questions and I'm happy to stick around if people want to insert questions into the chat。

啊。VA video for word distribution okay I haven't oh yes so yeah。

 it turns out if you're using words as random sources。

 they're not good at all Zfslaw for those of you don't know Zflaw it means the most common word is really the most common word。

 it also turns out that if you know why would you care about things like this。

 well if you're looking at encrypted data and you know under the language of the underlying data happens to be English。

 you know with high probability the word thus surrounded by two spaces is there a lot。

That knowledge turns out to give you a lot of really interesting leverage to be able to start decrypting the crypto system。

诶。It took me a lot longer to read Hamlet， N it took me a lot longer to read Hamlet too。

But it did run relatively quickly and the ham's not that big so。You know， there are only 90192。

000 characters in Hamlet total。Um， it's 32，000 words， not that big， you know， I mean， yeah。

 it took me a yeah， it took me a long time to read it too。

 butum in the in the in the sort of what it means to be a computer， that's pretty。

 that's pretty teeny。嗯。I haven't seen akira。Sounds like I might not need to。

 but I'm happy to take other questions otherwise if you want to move on with your day you're welcome to do that too and I'll stick around until we haven't gotten questions for a good couple of minutes yet。

So could we find the longest， most uncommon word？Yeah。

 so the way we could find the most uncommon words。I think。

Would be to switch the inversion of countor。So count sort is our comparator。

So let's invert that sense and this should give us the least common words。So。

Only once and fulfilled wouldve probably had an apostrophe in it。

There are probably lots of others that only had one word in it。

 and so this is just the ones that happened to appear earlier。嗯。Do I have an ETM project two grades？

Think they are close I don't remember if we've done final grading on them yet。

 I think we wanted to we had some students who were still submitting due to illness and some other reasons so we had to hold on to final grading for a little bit and we don't want to use the auto graders during the exam for anything either so they should be coming but I'm not sure exactly when。

Reverse iterators to accomplish the least common ones。

 I think you need to switch the comparator function Yes。

 you actually you could use reverse iterators now that I think about it in the。In the loop。

So in this loop， if we started at the end of sortable and work backwards， yes， that would also work。

How does the STL pick hash and compression functions for the ownerode map？

So the STL controls the size of the map。unless you tell it otherwise。

 and so it picks good numbers and then it uses hash functions that are defined and actually it's interesting that the implementation of the STL has a lot of freedom and how it implements those hash functions。

 there are only some sort of loosely stated and qualitative requirements。嗯。

And I'll put a link to that in the。In the chat。So and one of the things that's really interesting about it。

And this is just a quote directly from whoops。This is going to be a quote directly from that page。

So the actual hash functions are implementation dependent and are not required to fill any other quality criteria。

 which is just they have to be， they have to exist， they have to give you the same value。

 and they have to give you good dispersion。Notably some implementations use trivial or identity hash functions。

 which map an inju to itself。Not that surprising。You are welcome。

So when from bucket arrays are let me go back to the slide。



![](img/997e10cf19c63a912dab876423818527_5.png)

So this is the example that I was thinking about。So if the set of keys are small。For example。

 you just wanted to represent the days in one year。

 you would just create a vector of the elements you wanted to store as the values in your key value pair and you just use the indexes into the array for each day。

There are only 366 of them on a leap year that's small enough that you don't really need to worry about it。

Yep， you're very welcome。All right， it looks like we aren't going to get any more questions so thanks for coming I will see you on Tuesday we'll talk about how to handle hash collisions then be well everyone and take care and enjoy this wonderful weather we're having so unusual for March。

 but I will absolutely take it。Cheers。