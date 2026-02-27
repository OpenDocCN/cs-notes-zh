# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P16：-16-COMP6771 21T2 - 7.2 - Custom Iterators.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

🎼。Good evening。Hi everyone， nice to see you all again。I guess since we last spoke。

Many of you would have， oh my god， many of you would have submitted an assignment。

Or some of you are probably still working on it now， given that you can still get 92% of the mark。

 Oh my God， this chipp。Sorry， we go。 Yeah， given that you can still get 92% of the mark。

 I assume there's been a bunch of people tempted to keep working on it， so。

We're going to keep moving on。 We're going to keep discussing content， and。The core topic of today。

 which relates to your third assignment， is going to be custom iters。 Now。

 couple things on this firstly。We will talk about your assignment。Next week。

 I prefer to talk about assignments and lectures。After everyone's had a chance to really look at it and sink their teeth into。

Which about a quarter of you will do this weekend， right， maybe a bit more， maybe third。

So that's really great to talk about next week because there'll be some better questions The other thing is that as part of custom iterators。

 when I teach this topic I often try to not over preparepare the examples because I think that C++ custom iterators are actually a little bit confusing and there's some topics with this language and I do this with other courses too where I like to leave myself enough space to forget some things because it helps remind me what all of you forget sounds like a perfect excuse to be lazy right。

😊。

![](img/21104176e331387dea78d85347debcac_1.png)

![](img/21104176e331387dea78d85347debcac_2.png)

That'd be funny if that was the case。 But I think custom iterators are kind of hard because it's a little bit like operator overloading。

 It's very boilerlate。 You have to kind of get a few certain things， right， but essentially。

This whole topic is when we define our own types， like you would have done in assignment too with Euclidean vector。

 sometimes we want them to be iterable。嗯。And in fact， when it comes to assignment two。

 you've probably thought， oh， wouldn't it be cool if I could use dot begin and dot end？On my。呃。

On my Euclidean vector， just like the vector that lies underneath now。

 in a much older version of the Euclidean vector assignment， and in fact。

 the Euclidean vector assignment was adapted from another assignment。

 which was adapted from another assignment。

![](img/21104176e331387dea78d85347debcac_4.png)

Which was actually an assignment that I did as an undergrad a long time ago。

 And in those original specifications， what they actually had was what they called a dumb iterator where。

They would have a class， like， say， Euc couldian。Beectctor and inside that class。

 they would inside the public section， they would define a。Well like a pointer to a double say。

 this is not how it was be done called like Be。嗯。And。That would return。Magnitudes。

I'm just doing this like really roughly。That would return magnitude 0。

And then they would return double and， which would return you null pointer or something like this。

And then you could do dot begin plus plus and whatnot。

 Now that's not really an iterator right that's kind of what a very old version of the assignment asked students to do before we taught iterators。

 but that's not what an actual iterator is。 And the main reason you can tell it's not an iterator beside the fact that you know there's problems with it is that a real iterator you can have many instances of it at the same time。

 And it's an actual object like an iterator is an object for an STl container。

 It's a whole separate class。 So we're going to talk about custom iterators。

 We're going to talk about iterator and validation and then we're going to talk about iterator types So a quick bit of revision on iterators is that iterators are an abstract notion of a pointer。

 we learn this in week2。 they're an abstract container。

 they are a class themselves where they abstract something whether it's a tree， a graph a list。

 an array as a linear sequence of objects。

![](img/21104176e331387dea78d85347debcac_6.png)

![](img/21104176e331387dea78d85347debcac_7.png)

They help us glue containers and algorithms together and your job as an iterator designer is to make sure that and again。

 typically iterators are attached to the STL container。

 your job is to make sure that if you define your iterator correctly。

 then someone who has an algorithm like a sort or a search or a for each doesn't need to be concerned with the details of your data structure。

嗯。Yes， and that also means that your STL container doesn't have to provide all these different。

Access operations。Now。In terms of iterator invalid， this is something we glossed over a bit。

 by the way， I don't think we'll need two hours tonight。

 and I'm sure a lot of you are tired from the assignment。 so we won't use the whole time。

In terms of iterator invalidation， this is something we glossed over in week 2。

 and iterator invalid is。Basically a state。 it's something that occurs not not at a compiler level。

 but at a conceptual level when you modify the container whilst using an iterator so。

If you have a look at。嗯。The first container here， we have V。

And what I'm going to do is I'm going to loop through all the elements of V。 and if。

The value that I'm looping through is2， I'm going push to the end of the iterator。

So what that means is that throughout the iteration of this loop。

 the container size has gone from five to6。Okay， now that's not good。嗯。It's freaking chat。

It's breaking the， the iterator going from 5 to 6 is not good because when an iterator is created。

 it kind of assumes a certain。Like size。 Like it's kind of like takes a snapshot of it in a way。

 So if we mutate。The container。Whilst we're iterating through it and that includes a eras like in the one below。

 then the iters become what we call invalidated。 Now you might be asking， you know。

 what does this mean， Well， we could probably try this out。 I'm just going to grab a random。



![](img/21104176e331387dea78d85347debcac_9.png)

![](img/21104176e331387dea78d85347debcac_10.png)

Let's describe a random file。We'll paste this into it。That's， that's。That's some worknot。



![](img/21104176e331387dea78d85347debcac_12.png)

Got damn it。Great， so we've got ourselves a standard of vector here。😊，I will just do vector。

 and then let's try and compile this one。 So we've got a standard vector。

 Let's make it all pretty syntax。 Then we want to iterate through it twice and push back。

 and let's see what happens here now like what do you expect will occur。So here I might say。

 you know， autocon。X， oop， sorry。Auto constants X in V。 Let's just print it out。

 So we'll go standard C out。X。Yeah， let's do that。Let's see if this compiles probably missing a library。

Nope， everything's fine。 And then we'll just run it。Demos 7，5，0。Yay， memory  error。

 Let's comment some stuff out and let's have a look at what's happening here。

 So let's first comment this out。😊，See what happens to this program now。Okay。

 we're still getting memory arrow。So why are we getting a memory error。

 Does anyone have any idea is it something I'm doing wrong， I don't normally run this piece of code。

 I just thought it would be interesting to run today。A dress sanitizer sure seems mad。

It's obviously this pushback， right， and we can validate that pretty quickly by， you know。

Running that code again， and it works fine。 so the pushback is clearly causing it grief。

Let's try putting some other stuff in our code and let's turn the debug off so we can actually see what happens without the address sanitizer。

So let's just see what happens if I try and print out the iterator at each point。

Good old printf debugging。So let's try this one。 We'll get rid of our debug build here。

Let's see what would happen to this kind of code in production。

Jin says you are modifying the data when you're looping through it， yes， we are。

Why would that be causing a problem， though？Like that's kind of that's kind of the question I I'm getting at。

 So someone earlier said Psin's that infinite loop， so Psin。Looks like you're right。

 Why do you think we're getting an infinite loop here？Like， why is this。

 Why is this code just looping infinitely。So another thing， let's explore some more。

 let's try and see what happens if we see out。Iterator。And then let's try and see our V dot again。

 And maybe we can see our V dot N。 Let's， I can't remember if we can print。

 I don't print point as much。Nope。Can we avoid style these。 Dont don't do this。

 This is bad and naughty。Technically， they'll want the address。 I'm not going to do that。

 That's too complicated。 So let's see what people have said。

 I just tried to overcomplicate that example， so。George， okay， so Pyn says it's adding two。

 then at the next two it adds2。George says， doesn't it create a new pointer。Well。

 that's a great point。 So I think five Ss probably nailed it here。

 so let's if we let me get rid of that silly line I have。

So if we go and we have a look here and we run this code。And then I stop it really quickly。

 And let's actually output it to a file。 So I'm going output the output of this to a file。

 Sometimes this is an easier way to， to。Do something。 If I open that out file。

 let's have a look at it。 Not that the first value here is one， then it's 2。

 Then it's a giant number， Then it's 0。 then it's 5。 then it's 0， then it's。Another number then at 0。

Sir。It's adding two then the next two adds to， well， maybe。Want to go further down， though。

We're not really seeing this problem。 It's a lot of garbage again。

Is it because it resets the iterator soap？There's not really a reset that happens with the iterator。

 One of the main problems here I'm guessing is that you're essentially confusing。

 let's look at how this starts again， So I'm just going back up to the top。So we get a one。

 we get a two， and then we get a gibberish number。 The thing we have to be careful of here is that we are。

 in this case， potentially changing where the end of the iterator is。

If we pause this one for a sec and we just go and have a look at say the next example down here。

Where we erase things。 So look， if you look at this example where。We are。嗯。

We're just trying to remove one thing。Right， let's try and compare this one。

 see if we can dig in I just want you all thinking about thiscause iterators are easy source of bugs。

 So we have this vector of five items。 and then we're gonna delete the second one。

 What do you think will happen in this case here。Okay， print out nothing。 Maybe that's a good sign。

 least we're not stagfolding。 Let's actually try and print out what the state of the array looks like after the state of the vector。

Okay， so we get one， three， four， five。That one seems okay。Shuo。Maybe that's okay。 Maybe that's not。

Phiin says， does it reallocate it when you push back。So it refers to a different vector。Well。

 so firstly， yes， it will reallocate it when you push back。

 We've kind of learned this from previous lectures。 So again， if we explore this。

Top piece of code here。Let's every loop， let's print out， let's stand it see out the。V dot capacity。

And let's actually see how this capacity changes as well each time。

And I will have to print that out to a file again。5，5，10，10，10，10，10，10，10。Okay。

 so what clues can we pick up from this， Well， the clue here is not that it just continues to resize itself Okay。

 and you can tell that because it started off with a5。 it loop through one， it loops through2。

 And then when it loop through2 it pushed back to， which increased the capacity to 10。

 So clearly we've added more to this vector。 And again you could also look for clues by printing out。

V dot size here。 So let's run this one more time， print out V dot size。To see how big it actually is。

Okay， so it's five， it's five， it's 1， it's6。Okay， so it's actually adding it correctly right。

 so it's resizing it fine， it's adding it correctly。

 it doesn't change the size of vector or anything like that。

Does it reallic when you push back yet does reallic， So it refers to a different vector。

 different space and memory， same point of it less values。

So it's okay to make it smaller and not larger。 well。

 what I'd like to do here and this is kind of a last。Thing I'd like to do。

 I've just forgotten how to print out V dot again。 So like if I want to print out V dot again。嗯。

V dot again gives me an iterator， so if I want to print out。

I wonder what happens if I avoid star this？If I wantna print out the address of V dot again。

Use of old style cost go away。Gowei。How do you print out a pointer again？Im print out a pointer。

 I mainly print out pointers and see that these days。Hm。Or we could try， could try G plus plus it。

 That's not my favourite solution to things， but。When you need it。



![](img/21104176e331387dea78d85347debcac_14.png)

By the way， really quick tangent。One thing you'll notice here。

 And I'm not sure a G plus plus version I was just compiling that with。But。Oh， it didn't like that。

 So what you'll notice here is that when I just tried to use G plus+ on the command line here。

 what actually happened was that it actually complained it said missing template arguments for the open brace。

 Now， if you remember from the templates lecture， we actually talked about this in terms of template what you call template argument deduction and we didn't touch on it a bunch last night。

 I think we touch on it more next week， but this code originally compiled with CMake when we just said vector of this because the compiler was able to look at the types you were populating the vector with。

And tell that it's a vector of ins。 but I， I don't know when that was introduced。

 but it was definitely introduced in a like it seems fine in C plus plus 17， for instance。

Same with okay， so C plus plus 17。 so you can see there that when I get the compiler to compile with C plus plus 17。

 right？Its ability to deduce the template argument there。It works like classic example of light。

 I't know。I'm not show what the exact name for it is。嗯。Here you go， I this it。

 I'm not too sure I haven't looked this up， but。Class template argument deduction is a core language feature。

Blah， blah， blah，'m sure it's something like here。 Nathania might have a more interesting link。

I'm pretty sure that sounds like， I mean， this is， this is where I've looked at it previously。

 So again， just I like to point out tidbits of language。



![](img/21104176e331387dea78d85347debcac_16.png)

Like language versions and whatnot。So cool， anyway。

 the point is if you're using an older version of C++ like before 17。

 you'd actually need that in there because the compiler wouldn't really be too friendly with them。😊。

With deducing that， the the real thing that I'm pretty sure is hurting here willll come back to this example after。

 but when you are mutating a vector， particularly modifying it。Here。

 we're really throwing off the value of dot N。 So essentially。

 what you are seeing here from us is that we are。Iterating kind of nonstop。 So essentially。

 this condition here is never quite。Set to a。False， right， It's like always true。 So essentially。

 our iterator never seems to be equal to dot end。 right。

 The details of that will maybe try and come back to。

 But the actual mutation of the iterator has basically done what we call invalidated。

 That's why we call it iterator invalid， because if we're mutating the data structure。

 Then all bets are off。 So we often talk about undefined behavior and other things like that。

 In this case， it's kind of like that。 It's like once you mutate。A container。

 any active iterators you have to it should be considered invalid and won't guarantee you any expected behavior。

 So in a piece of code like this， generally speaking the right practice to do something。

Like to break。So that this should。This should work now， right And if we。

 if we try and print this out， we'll get the same。Get the same results。

 Sorry I don't know if you can hear the dog screaming。From a few doors down，1，2，3，4，5，2。

 And then if we remove this。What we should see is。Well， what's going to happen here。

 this one will get interesting， what do we think it'll do？Segmentation fault。 So that worked before。

 Why did that work before， That work before， Because we had one，2 in the vector。

 So if I don't actually add this other two to the vector， we don't have any problem here， do we。

 It should just work fine。 We get 1，3，4，5， because This vector had 1，2，3，4。

It eras something from the vector。And。Yeah， the vector is resized， I guess。But it's still actually。

 yeah， the vector was resized， but it just kept going Pin says。

 does it have something to do with the two being at the end。 Yes， it does。 So Jesus that dog。😊。

Got damn dog。 Yeah， it does。 So let's， let's try it out。 So let's actually see what happens each。

Each iteration we do。So let's build with this。Okay， so what is it actually printing out here。

 It does1，2，4，5，2，2。That's really interesting。So why do we think it's doing2，2。

 so you can see it does one that makes sense on the first loop， the second loop it does two。Sure。

 that makes sense。 Then what the vector did。 So if you imagine for a second， the vectors here，1，2，3。

4，5。 and let's have a look where the iterator is。 So the iter is at the start there。 It's at one。

 Great。 It goes through。IT plus plus， it then goes to the two。It checks。

 is the dereference of the iterator is the value to。 Yes， it is。 So we're going to erase it。

 So what happens now is that the actual container is mutated and it's erased。

So then you finish that loop， you plus plus the iterator， which moves it to4。

 And now the next element you get is a4。And then you plus plus the iterator and you move it here。

And you get a 5， and then you plus plus the iterator， and you get it here。

 which I'm pretty sure is just。

![](img/21104176e331387dea78d85347debcac_18.png)

Looks like beyond the bounds of memory， basically。Yeah， so it can't reach dot n， so。

The only thing I'm kind of mental mental blanking is just。

I can't remember how to print out an iterator with the C make。

How to print out the pointer of an iterator， I don't know if we can print out。

I don't think we can print out the address Anyway， Someone will tell me。

 Someone tell me how to print out and iterate as。Addresscause then we can have a look at the contiguous memory。

 which， which should help us make more sense of this。

freakreing hell I knew it was something stupid like that。Yeah， so。😊。

N Nathanathiel's told me what it was。 and this is what I was thinking it might be before。

 but it sounded so ludicrous that I was like， oh， maybe not。

 So I'll just put the brackets in here for fun。 So here's the tricky thing about iterators， right。😊。

V dot begin。Returns you an iterator。 An iterator is a class。 It's an object。

 It's an abstraction of a value。 When you do de reference on an iterator。

 you get the actual value that its pointing to。 So， you know， if you have like an iterator here， I T。

Like this。 and you have your actual container there。I just kind of abstractly points to this。

 right When you say I would like to dereence I， it gives you this actual value here。

 the concrete value。And then after that， when you ampersand it， you get the address of this thing。

 If you just try and get the address of the iterator， you're going to get an address。

 I believe to the iterator object， I don't think it's operator overloaded。

W whichch isn't what you want because you don't want the address of the object。

 you want the address of the actual。Value， so if we go back to the code here。



![](img/21104176e331387dea78d85347debcac_20.png)

And then， just for fun。嗯。Well， let's try and print out a couple of things。 I mean， let's first。

 just before we do that， you know， let's try and print。 Can we do this， Can we do V0。

 the address of v0 memory， the first element。嗯。I mean， I would have to overload the amand if。Yeah。

Anyway， let's if we do this a few times， right， we can see what you can see that these things are contiguous in memory and then we can try and print out。

 So let's just have a look at this first so。We have our array。 Now， these are the memory addresses。

28，0，28，4，288，28 C2，9，0。 Now， that makes sense。 Now。

 let's print out what the address of V dot beginners。 And maybe I'll do this。Here as well。

 so we're going to print out。The address of what V dot begin points to。 So V dot begin。

 Let's get the value that it points to。 And then let's get the address of that value that it points to。

 That's what's happening here。 We'll build it， run it。

 And then what we'll see is that it's the same address。 Now， this makes sense。

 This also makes sense that we could get all the values from this pretty easily just by saying V dot begin plus 1 V dot begin plus 2 plus 3 and plus 4。

 And then we could also get。

![](img/21104176e331387dea78d85347debcac_22.png)

V dot end。 See what this one is。Now， generally speaking， you don't want to do reference V dot end。

Because it's not guaranteed to be a valid value， I believe I could be wrong。

 I'm pretty sure that I'm pretty sure that dot endpointers reserve the right to point to garbage。

 so I don't think you have a guarantee that you could dereference it and get its value because it might point to null or something。

But you can see here it's kind of a similar thing now。What's really interesting about this。

 as you can see is that the end pointer here is pointing to what looks like8 bytes。After the end。

 so it goes 80 because in 4 bytes right， 80，8488，8C，90。😊，98。 So that dot end， that， yeah。

 the dot end iterator， the value it points to is is two spots after。 Now。

 that doesn't really matter too much because， you know， even though in， even though in reality。

 what's happening is that all of your five values here。Are contiguous。

And then it looks like our end iter is like there。This doesn't really matter where it is in memory because that's the whole point of an iter。

 the whole point of an iterator is so that when you're going through it， it just does this for you。

 it's like that， that，It just figures that out。

![](img/21104176e331387dea78d85347debcac_24.png)

嗯。So someone said there's another two at the end， right。 Well， oh， sorry， yeah， there is my bad， but。



![](img/21104176e331387dea78d85347debcac_26.png)

So。Yes， that's correct now。The point here is I think a mistake some students make is that they kind of assume that the dot end iterators are always literally or like are required to be literally at the end of contiguous memory and that's not an assumption you can make here So I was kind of rolling with this because the point is you' you can't just assume that it's like sitting right at the end and make some assumptions about that fact。

 this is particularly true for linked structures like linked list and stuff because all of the nodes in a linked list are totally disjoint they aren't contiguous in memory So your end iterator would not really be meaningfully predictable。



![](img/21104176e331387dea78d85347debcac_28.png)

Like able to be predicted。Sir。Let's see what happens when we erase it。 Okay， so we printed out these。

 And you're right， there's a， there's a， there's a fifth value here that I'm missing。 Thank you。

Let's print out these。嗯。And then let's see what happens after we erase it。

 So we've already printed out。 and we saw， what did it do before it's Seg faulted， didn't it。

So we're going to get another sec fault here and you can see it prints out 1，2，4，522。

 Now let's have a look at what the end iterator is every loop in this function。

And let's have a look at what the address of IT is as well。Okay， so we'll build this one。Okay。

 so we're starting the loop now。This makes sense we start off at 80。 We're going till 98， we go to 8。

4， we go to 88， we go to 8 c， we go to 90。But have a look at what's happened here is that the end iterator has changed。

Now。The reason for this， in the case of the loop， and this is where the details of a programming language get really tricky is that this V dot end is called every single loop。

🤢，So every time this program loops it is calling this condition and it is getting the value here。

 so what happens is we do it once， we do it twice on the second time because IT is equal to 2。

 we erase it， what does erasing it do， It decreases the size of the vector by1 from 6 to5。

Which therefore changes the end iterator， because the end iterator in the way that。

A vector is defined as now one step closer。So therefore， the end iterator is one step closer here。

 and then。What that means so if I just draw it out again。If we have like one，2，3，4，5，2。

We start off here， we increase it to here。We increase it sorry we increase it to here。 We have a two。

 we and let me leave you where the end iterator is。 So right now the end iterator is here。I guess。

 so maybe I should say it's here。So we get to the two。

 we delete the two that moves the end deerator down because the enderator kind of points to one past the end of the array。

 we increase I。Which is why we never print out the three。And then we increase I again。Right。

And then we increase I again。But then we delete the two here。



![](img/21104176e331387dea78d85347debcac_30.png)

Which moves the end iterator there。And then， we increase I again。

And now suddenly we get lost in one or two situations， which is either some kind of loop。

 potentially where I just continues to increment until it seg faultults or it segvolults immediately。

 because we're accessing memory that's not ours。 So just a particular way that we loop through this with an iterator has caused a Seg fault because we essentially deleted and then jumped over the end iterator before we ever had a chance to conditionally check if we met it。

Susshas， doesn't that contradict the contiguousness of the memory。 I don't really know how it would。

 I'm not too sure you mean， sorry so。As you can see。

 the kind of outcome from this is that the dot n iterator in the case of a vector。

Does change what it actually is。In in this instance。

 so we we delete from a vector and the dot end doesn't guarantee that it refers to the same spot。

This is tricky for us， then， because that means we。Can't rely。On那。

It's saying the same when we mutate it。 So whenever you mutate anything。

 all the iterators you've been using， you have to assume that they've been invalid。

 You can still use them。 There's nothing stopping you using them， right。

 It's not like the compiler or some runtime engine says， oh， sorry。

 I can see that your iterator is invalidated。You can try it， it will just fail。

So that's what you need to keep in mind。 Very long window we chatted about that。

 But I think I think it's an interesting kind of revision on。

Objects and iterator objects and and memory and and containers and everything else。

 So using an innovate using an invalid iterator is considered undefined behavior。

 just like indexing an array。Larger than its size。 Sureish。

 when you mentioned and might not always be at the end。The point is that。A container stores data。

Right， an array based container store it contiguously， a list， a linked based container like a。

Ordered set will store it in the binary tree。 Other things will use a hashm。

An iterator is an abstract linearization of a container。An end iterator， an itererate at the dot end。

 is an abstract notion。Of a step past the last element。It's an abstract notion of that concept。

 It doesn't。 There is no requirement that it's actually。Reflective in the underlying data structure。

 Now， obviously， for things like arrays， library implementers have decided to stick with it being literally one past the end of the container because it fits the model。

 It's very easy to do。 But again， for link structures or for hash based structures。

There is no real end to it。So in some other structures you might see like VNB a null pointer or something。

And that's that's why that's why you can't really just like assume anything。

 And the whole point here is that you can't just assume that you understand。

How the dot end works because you're dealing with an abstraction of the container and the second you mutate the container。

 you have to assume that you've invalidated that abstraction and you need to loop again。



![](img/21104176e331387dea78d85347debcac_32.png)

Jin says。If we add IT equals v dot end break at the end of the loop。

I'm not sure what you mean by the I equals V and break， but generally speaking， any time you。

 anytime you're iterating through something and you are。Mutating it。

 you just brake to leave the loop。 That's kind of the process that we follow。



![](img/21104176e331387dea78d85347debcac_34.png)

嗯。Okay， so we we've already kind of talked about this。 but like just a quote CPP reference here。

 there's a line from CPP reference that says， if the new size is greater than capacity。

 then all iterators and references are invalidated， otherwise only。The past。

 the end iterator is invalidated。So this is specifically for the pushback function。

 So the statement about anytime you mutate an iterator。

 you should assume that it's invalidated is just a broad statement to kind of get your head around it。

 but the details are a bit more complex than that because in the case of a vector right so on a case by case basis。

 we just kind of understood how a vector works when you add to a vector。

 it increases it by one and when you remove from a vector it decreases it by one。



![](img/21104176e331387dea78d85347debcac_36.png)

![](img/21104176e331387dea78d85347debcac_37.png)

And what we saw earlier was that if we just add to a vector。Like this。We get rid of all this stuff。

What did we see happened here？We got a Se fault here。



![](img/21104176e331387dea78d85347debcac_39.png)

Why do we get a se fault there。Oh yeah， because the new size gradient in capacity。 Yeah， yeah。 so。

 but。

![](img/21104176e331387dea78d85347debcac_41.png)

I'll demonstrate you slightly the different example in a sec。



![](img/21104176e331387dea78d85347debcac_43.png)

Read the docs on these things， because what pushback says is that。If。

If size is greater than capacity， then everything' is invalidated。 But I think what that might mean。

嗯。No， it says otherwise only the past past the enderator is invalidated shot。嗯。Yeah。

 so what this one is specifically saying is that。If you have to resize the vector。

 then all iterators you have are invalidated， but if you don't have to resize the vector。

 then it's only your usage of V dot n that's invalidated and you need to rethink that So in this case here we're obviously resizing it which is a problem let's watch so what if we do this first what if I say push back6。



![](img/21104176e331387dea78d85347debcac_45.png)

And the reason for this is remember all vectors are initialized with the exact size。

 So the size equals capacity during vector initialization。 when we push back the6 here。

 the capacity is going to go from 5 to 10 and the size will go from 5 to 6。

 So when we push this here， we're not actually going to be resizing the vector。

 We still do get a segmentation fault here though I believe because we are still using the V dot n iterator and we could go through the memory and stuff to have a look at that but that's what they mean here by only the past the end iterator is invalidated。

 So it's kind of like if you resize it， every iterator you have is invalidated otherwise just the past the n iterator is invalidated。

 And what do we mean by that what we mean by that is that if I say here autocon or if I say autoconst。



![](img/21104176e331387dea78d85347debcac_47.png)

![](img/21104176e331387dea78d85347debcac_48.png)

嗯。Begin equals v dot begin。And then down here I say standard C out。Begin like this。



![](img/21104176e331387dea78d85347debcac_50.png)

The begin there is still considered valid。 This should work。 Yeah。

 so the begin here is still considered valid because according to the pushback rules。

If we aren't resizing， if we aren't expanding the size of the vector。

 then it's only the V dot n that becomes invalidated here。Otherwise otherwise upon mutation here。

 this would become invalidated too。I'm assuming the reason for that。嗯。Is。

 is mainlycause I I guess with the vector size， the actual addresses probably change in memory。

We could also test that out really quick too like this is the thing about like C and all this other stuff is you can just try things out really freely right so I could say okay。

 what's the address of v0 here and what's the address of v0 So let's actually see if the memory location changes you know some of you will know this because you're curious cats and look at that there you go like that's one big reason why all iterators are invalidated after a resize。

😊，Because it's actually a different memory now。嗯。So you know。

 if if you've had a previous iterator that points to a particular address。And then you incremented。

 it could now be pointing to invalid memory。嗯。Yes， and and Nathan's made a sorry。

 Nathaniel's made a good point here too， which is that。

Using V dot N here because this has resolved every single loop。

It's technically still fetching the iterator each time， which is okay。

I'm going to try and summarize this for you because I can I can feel that this has been slightly stressful。

So。At this point here， we have a vector of size 6。And we're going iterate through it。

 and we're going to add a seventh element to it。Now when we add a seventh element to it。

 one or two things are going to happen， either the vector is going to resize or it's not。

If the vector resizes， any active iterator we have has to be essentially tossed and or refreshed。

So what is an active iterator we have， Well， it's IT。

 So like if I get rid of this pushback for a second。 so the vector size 5。When we push back2。

This is going to be a resize or a reallic。 Now， the pushback rules say that all vectors are invalidated。

 That means that I is now considered to be invalidated。 So as of this line here。

 I is no longer a valid iterator。So we would have to either break out of the loop or call dot begingner again or call V dot search like there's a few ways youd kind of get around it。

 but the point is that the IT that you had before that mutation before that resize is not valid。

But if you， if you don't resize it， then the only thing that's invalid is the V dot end。

 But the point Nathaniel's trying to make， which is a really good nuance here is that。

It's only any current iterators you have。 So， for instance， if isnt if it isn't resized。

 if it's kind of resized up here， So it's size 6 capacity 10， and then when we push to it。

 it's going to be now size 7 capacity 10。 There's no resize here and the rules say it's just the past the end iterator that's invalidated。

 the point is if I have any current past the end iterators that have already been captured from the vector I need to update though so that the contrasting example here is if I say auto n equals v dot n。

 And then I loop like this。Because I got the value from V dot end before I started iterating。

 so I got the value for V dot end。I pushed back， which invalidated the end iterator。

So therefore I can't use this end value again。 I can't use I either。

 Well I can sorry I can use I in this case because we haven't resized。 So without a resize。

 my I is still valid because it's only the end iterator。

 So here I could naturally say like a couple things， you know， as I could say。

 you know end equals V dot end I think would be one option。 I don't know how clean that would be。

Or alternatively， you could just do what we had before， which is probably better up。

Which is just saying I equals V dot n doesn't equal v dot n because every single loop。

 that particular function called a dot end will be resolved， and it'll give you a valid。

And pass the enderredo。

![](img/21104176e331387dea78d85347debcac_52.png)

嗯。We can see with a race here that a invaliddates iterators and references at or after the point of the erase。

 including the end iterator。 So again， every particular kind of method has its own rules。

 And this one is saying that。At or after the point of the erase。

 So what this means here in the case of the erase function， let me just get rid of some of this code。



![](img/21104176e331387dea78d85347debcac_54.png)

Is that。If you have something like this。And you erase it。

We do have to break because the I T iterator is no longer valid。

Because it was basically captured or defined before that invalidation happened。

We also can't do things like say I We also can't do things like say I minus minus。

Because at the point of the erasure。IT became invalidated because it says it invalidates any iterators or references at or off the point of a race。

So I is bust for us now because it was at the point of eraia。 However， if we did something else。

 like we said， auto。Begin equals V dot begin， like here。And then I said auto IT equals begin。

Then we can still actually do something here， like， say， begin plus plus。

 or we could standard see out begin like we can do this because。Begin。

Here isn't just an iterator to the start。 It's before the point of eraia。

 whereas like here I was like moving along and it was at or after the point of erasure when when that happened。

 So again， just things to keep in mind with these rules。🤢，So， in general。



![](img/21104176e331387dea78d85347debcac_56.png)

The thing you need to be careful of。Is essentially when I've been using the word mutating a lot。

 What I've really been meaning is mutating the structure， like adjusting the structure。

 We don't mean changing the values。 So it's like you have to be really careful and you probably it's probably just best to assume this unless you want to read the rules that your iterators had become invalid once you。

Add or remove from a container。And as we've seen here。嗯。

There are different rules for pushback for a race， different ones for different containers as well。

 as you can see the comment here is the hash maps， the unordered sets and the unordered maps。

 they invalidate everything when you add elements like literally everything so you have to be careful about that。

Now the the next thing， so we don't we don't have a time to go through tonight。

 but most of what we're about to go through next， we'll probably do this after the break is I want to define a custom iterator with you。

So most， most of this will just be coding。 So we're just going to define a custom iterator and then we're just going to talk about some properties iterators。

 and that's kind of it。 But thankfully， that's essentially the topic on iterators。

 So let's take a 10 minute break and get stuck back into iterators。😊。



![](img/21104176e331387dea78d85347debcac_58.png)

And get some practice with it。Hi， everyone。嗯。Welcome back from the break。

I am just unwinding some changes I made。So。We're going to run through， basically， a。Demo of。嗯。

How you could interact with how you could actually define your own iterator。

This is not with a generic or templated type， this is just with this like a a static type and I'm not going to be writing much code here。

Just because we're going to be using the card。

![](img/21104176e331387dea78d85347debcac_60.png)

So， sorry。嗯。And all of it kind of comes from these slides here。



![](img/21104176e331387dea78d85347debcac_62.png)

When we're actually defining an iterator， when we're creating our iterator type。

Every iterator in C plus plus has a fairly straightforward boilerplate structure。

 at least prior to C plus plus 20。 And you have to specify some things。 Firstly， for this iterator。

 remember an iterators for a container or something， What is the category of the iterator。

 Is it input output forward by directional random access， We talked about that in week2。

 you know what are the limitations of the iterator， What's its value type， I in if you say to me。

 get a value of this iterator， What is it What's its reference type， what's its point to type。

 And then also what's its difference type， that one's a little bit weird。

 But these are like the five things you generally need to tell the compiler for it to make sense of your iterator for you Here is an example。

Of a generic。Iterate a class。So remember how I said before like you have your STL container。

 which is a class。But then you have an iterator， which is essentially a whole separate object。

This is an example here of how you might go and define that iterator。

We've done this here with Ts as placeholders， just for simplicity。 But in reality。

 you would have a little bit more detail to this。 I'll just move my head for a sec。 But essentially。

 this is what an iterator is。 It's a class。 It's a class that has a whole bunch of。😊，Definitions。

 it has a overload for operator dereference。 It has an overload for operator plus。

Post like post increment and pre increment。 it has an overload for the operator de referenceference via pointer。

And it also has an equals in a not equals friend overload too So these are all things that are overloaded to make the iterator work。

 and that makes sense right， because you've worked with iterators before。

 you know that you can plus them， dereference them， you can equal them， not equal them。



![](img/21104176e331387dea78d85347debcac_64.png)

What we're going to look at。Is that in the context of。A class。

And probably the most important structural thing to get with an iterator is that the way it works is that if you have a container。



![](img/21104176e331387dea78d85347debcac_66.png)

In C plus plus， you know， the container might be say like this。

 This might be your instax or something or a vector or whatever。 Your iterator is a class as well。

 but it sits inside of that ins stackax。So this might be your inst。Iterator like this。Okay。



![](img/21104176e331387dea78d85347debcac_68.png)

Now。Pay attention to this piece of source code here because this is meant to represent the actual container。

 so this is the representative of a stack of the array of the unordered map and you can see that the classes of the container。

Right but what we have is we have our iterator class inside of it。

 so it's basically a nested class essentially and then we have a bunch of methods which is dot begin and dot end。

😊，Right， so that's how you get the begin iterator and the end iterator。

 and then we have our dot begin dot end and dot C begin dot C and for our const iterators。

 So the whole point of iterators is that your actual class the container all its job is is to provide the dot beginss on the dot ends and those dot beginss and dot ends simply return you an instance of the iterator class that you've defined as a nested class within your container this is also starting to give you a bit of an understanding of how you can call dot begin on both a cons and a noncons object because if you call dot begin on a con object right because this one's consqu you just get a const iterator and if you call dot begin on a noncons object you just get a nonconst iterator So these are all handled。

 this is how these classes like vector are defined now。We're going to totally dissect a。



![](img/21104176e331387dea78d85347debcac_70.png)

A piece of code that I've prepared earlier called InsStack and InsStack is as you'd expect。

 it's a stack of integers。The class has。嗯。Sorry， I'm just having a look at how it's。Implement it。

 just refreshing my brain soap。What's important about。This structure。嗯。It's also。

 so Kays mentioned isn't using STD， isn't。Isn't using using STD something bad。

 So what we've said in the course previously is that there's pretty much never an excuse to use using namespace and then the namespace。

 but there are certain circumstances where it's okay to use。呃。You know。嗯。

How would you put it like using a specific type or a specific。Yeah， specific reference， I guess。

 Now what's， what's interesting about this in stack， we've chosen to implement this as a linked list。

And the reason we've chosen to implement it as a linked list is mainly so that you can start to try and get your head around link structures a bit more。

 which is what assignment 3 is going to be about。 So as part of our Instac。

 we've actually got this kind of subclass up the top which is a node Now this is just a standard kind of linked list thing where you can create a node in a link list and that consists of a value and a next pointer this is a constructor here。

And the node is made up of a value and a next pointer。 and we're wrapping this in a unique pointer。

So that。We don't have to worry about fraing memory， okay？So。

That's that's all just like a linkless structure here。 Now， ignore this bit。

 do I how do I make things disappear in VS code， I just do this， right？Bm。Is that it？

How do I make it all Oh， cool。So I'm just showing you the container at the moment。

 And the container just has thisstruct subclass。 Remember astruct is just a class where all the methods are private by default。

 Everything's， everything's public by default。 sorry， So I've got my private thing up here。

 And then I've actually got my。Stack here。 And you can see the stack has a bunch of fairly standard functions you'd expect。

 You can get a reference to the top of the stack。 You can get a cons reference to the top of the stack。

 although that' ones， that one is cons qualified， you can pop off the top of the stack。

 And in this case， what we're doing is we're actually moving。



![](img/21104176e331387dea78d85347debcac_72.png)

We're actually moving off the stack so to pop， we're actually returning the value via move。

 this is a way of you know not having to copy， it's just an efficient way of dealing with resources。

And remember， what we're actually moving out is a， a node， so。Oh， sorry， dont no， my bet。

 I misreading that。 The point we're not returning anything on P。

 but the point is that when we're moving resources around inside of our stack。

 we want to use move so that we're not copying anything because you know that is potentially of course。

 very costly for us。 we have push and you can see what push does is if you give us a value。Right。

 we will make a new node with that value。 And then what we'll do is we'll say like。

 we'll move the head to the。To the next element。 So essentially what's happening here is that the stack is growing upwards。

 So it's like we have like a linked list like this。And what happens is when you add to this stack。

 we're taking this and moving it up and adding something underneath like that。

So this is always the head， the head is always here。



![](img/21104176e331387dea78d85347debcac_74.png)

So saying that when we push something， the new head of the stack is a new node。

And we're simply moving the head to like the next node。

Some of the standard move and whatnot you can go and look at in your own time。

 it's not like the standard move， some of that and the link list is not critical to the understanding of iterators。

 it's just we've given you a slightly different code example。

 but you know the SAC operations are pretty standard here。On top of that。

We have our sixth fairly standard。Iterator functions or our container functions that expose the iterator。

 That's begin and C begin C end and begin and end for con qualified for constant objects。

 These are pretty much boiler platelate， iterator， begin iterator and cont iterator， begin and C。

 begin and C end。Now， you can see that we've also bootstrapped some of these in the sense that we have our。

Begin， actually return something。And our C begin actually returns something。

 but our begin consqu just returns C begin， so we are bootstrapping ourselves a little bit here。Now。

 what you'll also notice is that all these begin and end functions do is actually construct an iterator object。

 Now what is that iterator object， Well， this is a type here right so this is like an inter double。

 It's just a type iterator and constant iterator art types。

 Now what we've done here is we've just alias these。To。A particular。Cllas。

So we've created this iterator class and what we've said is that when someone calls dot begin or dot end or they call C begin or C end。

 we're going to create an itator class。And we are going to return it to them。

Ass everyone following so far， the only question right now is what exactly is this iterator class？

So again just for clarity the point is that someone can come along and say what's this insStac so someone can come along and say auto I equals insStac sure I don't even think we have a constructor here for it so we create a new insStac and then you say I do push5 I push6 and then we could say4 auto IT equals I dot begin。

I T is not equal to I do end。Pluss plus I， and then we could do something with it。Right。

 so the point is that we want it。 We want this behaviour to exist where we can simply iterate through it。

 And， and we've got， we've got our。Classs， we've got our push。

It's just that our dot begin dot and returns some magical iterator object。

 it's just what exactly is that magical itator object。Now。

 what that magic litator object is is defined up here。This is a subclass。

That means that if it was public， which it's not， it's private。You would access it by going。

 and in fact， you can access it， sorry。You can access this because it's public by going。In stack。

Get it right。You can't say InsSt iterator with a capital eye because that's not exposed to you。Right。

 that's， that's up here。 So this is all private。 But we've aliasated in the public section。 Now。

 you might be asking， why are we aliasing it， Why don't we just Oh， Miss chair。

 Why don't we just define it in the public section， And the reason for that is because this way。

 like with containers。嗯。We like to have a fairly standard format。

 which is that the non constants iterator is lowercase iterator and the constant iterator is constant discerator。

 so it's pretty much just an abstraction that lets you name this whatever you want。

 put it wherever you want without having to worry about it。

Phi S does making it an iterator allow us to do four range four range base loops， Yeah。

 so with C++ four range loops。Quite literally， just use。The iter is underneath the hood。

 so you could do this as well。That is what would be available if you implemented your itererate correctly。

And I mean， in general and C plus plus it's like， you want to use four range loops wherever you can unless you need to do something kind of funky and muty。

 like change the structure in which case you'll tend to lean on iterators。

So we've got that now we need to look at our iterator class。 Now iterator class。

 it has a bunch of things。 it's got some private things and some， some non private things， but。

Let's analyze this together。 So what？Is going on here。I'm just having a look at。These things。Yeah。

 so what our iterator consists of quite literally is this is its constructor。



![](img/21104176e331387dea78d85347debcac_76.png)

And what its constructor says here is that we take in a node。So an iterator again。

 if you imagine an ins stack， an ins stackaxs like an ins stackac might be like this theoretical concept or whatever。

 when you create an iterator which is an abstract pointer to that stack。

 it's going to take in a node so that it knows where it's pointing to because an iterator is an object that at any given time is pointing to a particular element。

So when we construct this， we need to give it the node that we're pointing to。

And you can see this is actually stored here。Inside the private member。

 So this is the only private member of。The iterator。

 it basically stores a pointer to a node and your instaxs made up of nodes。

And when we construct our iterator object， we just give it a node， a point to a node。

 And then that's what we store。 So really simple。 it's like it's literally destroyoring a node。

 like a point to a node。 So you've got this stack here with all these different elements。

 And it's just which one are you pointing to。 That's， that's all the question really is。

 So you construct an iterator。 It's just this object over here。 You could construct another one。

 The points to this node or whatever。 It's all just a to a node。



![](img/21104176e331387dea78d85347debcac_78.png)

![](img/21104176e331387dea78d85347debcac_79.png)

And then we have all these standard functions here。 So we have operator equals。 Now。

 this one is quite straightforward， too， because。If you have two iterators that are both just objects that point to a node。

The iterators are equal if they're pointing to the same thing。That makes sense。

And the iterators are not equal。 if that's not the case。

 So our friend operator equals and not equals is。Relatively。Clear there， I think。嗯。

Then we have a few other key functions here like we have the plus plus increment we have pre increment and post increment。

 You can see that the behaviour between these is not particularly complicated。

 It's like the pre increment plus plus simply says my current node is now equal to the next node。

So like， you know， if。If this is here， then when you say you know iterator plus plus。

 you it's basically saying， okay， well， all right， well I point to this thing and this thing has a next pointer of that。

So I'm now going to point to that thing。That's what's actually happening here。

So it's saying I as a my node that， you know， I'm an iterator object and I point to a node。

 The node I point to is now going to be what my current node points next to。

 So I'm going to look over here now linked list logic。Oh， is it My face is on top of the diagram。 no。

 Al right， Let me explain that one more time really quick without my head in the way， so。Oops。

 did I move that， No， that's all good。 So what I'm saying is that this is the iterator here。

It currently points to the first element of our stack。These are linkedlesss， by the way。

 even though I've drawn this like an array， and what we say is when we say plus plus in this。

 we know that the first element points here， so now we're telling the iterator to point to the first elements next。

So the iterator now points to what the first elements next was。



![](img/21104176e331387dea78d85347debcac_81.png)

And that's why it says here the， you know the node pointer of the iterator points to what the node's pointing to next。

 So that's just how we move up it and the post increment。Is exactly the same thing here。诶。

Except we have to copy it first you can go back to week four if you want to review。

The post increment iterator。Then we have the other two and these two are pretty straightforward。

 it's like the operator dereence and the operator。呃。Stab symbol， whatever we all called it。

 So the de referenceence operator here it just gets you the value。

 which makes sense because if someone tries to dereence your iterator。

 remember your iterator is just an abstract notion of a pointer。

 So if you have a pointer to the first element。

![](img/21104176e331387dea78d85347debcac_83.png)

And you dereence it， you actually get the value here。So if I have an iterator。

And it points to the second element， and I de reference that I want to get the value there。

 So that also makes sense because my node is a pointer to a node。



![](img/21104176e331387dea78d85347debcac_85.png)

And I want to get the value at that node。Because that's how this structure appears defined， right。

 So I've pointed to a node。 I want to get the value at that node。

 and then I can bootstrap my my stab stab operator to reuse my operator dereence。

 So you can actually see that the logic behind the iterators are not very complicated。嗯。

They very boil the plate。And then if you look up here。

We've got these five key definitions that we said before we need to tell the compiler。

Which is what category are iter is in forward iterators。 That means we can only move forward。

 We can't move backwards。The value type is an int。 That means that our container stores inse。

Our reference is an int reference。 That makes sense。 Get a reference to an element in our container。

 gives us an int reference。 a pointer to an element in our container gives us int pointer and our difference type is int。

 This one is essentially like what's the you know how big is the element really。

 what's this one is usually int I believe。Yeah， let's， let's， let's。

 let me read up on that one again。

![](img/21104176e331387dea78d85347debcac_87.png)

Standard difference， not a difference type。My fingers are freezing， I can't even type。嗯。So啊。

Whereas what is I looking for， Clicked on the wrong thing。Iterator traits。

 So what what we're actually looking at here is iterator traits。

 that's what these five things are here。😊，So。Essentially， most of it is really straightforward。

 Like a lot of these are just that you the value and then like the point of version。

 the reference version， iterated categories 1 of5 that we talked about。 Nathaniel on the chat said。

The only other kind of difference type you come across is standard point di so。Pointed di type。嗯。

Standard point di type is essentially， I believe， just the space between two pointers。Yeah， oh yeah。

 so when you subtract。Two pointers together。You get a type。 that makes sense。

So the compiler will automatically assign that type。

I guess that's probably relevant if you if you have an iterator of pointers。



![](img/21104176e331387dea78d85347debcac_89.png)

In this case， though， our itererate is just an iterator of。



![](img/21104176e331387dea78d85347debcac_91.png)

A。

![](img/21104176e331387dea78d85347debcac_93.png)

But anyway， this this is one area I would encourage you to go and try and read more about as well because it's not something you'll have to think a ton about for your assignment。

 you'll just kind of put something down and you'll figure it out。

 but read up on the iterator traits to it's a worthwhile page that gives you just a little bit of information about how iterators work。

 A lot of it's kind of overkill though。嗯。Great， it， again， I， as you can also see here。

All this iterator stuff is kind of up till C plus plus 17。 so you'll see this becoming less and less。



![](img/21104176e331387dea78d85347debcac_95.png)

This pattern become less and less commonly used。 We opted not to teach it this year because we felt it was still a little bit。

Not widely adopted， but that'll change within a year or two so。Now， I've got my iterator here。

 and all these kind of functions make sense。 So when I come back down here and I look at my begin method。

You can actually see that what the begin does is it says。

 I want to create a new iterator and the node that I want to give it to。

 the node pointer is just going be my head， the head of my。My stack。That makes sense。

 And my k null point to here is just going to be the end of my stack。That also works Now。

 why does null work， Well， because the way we construct our nodes。Is that I'm just trying to find it。

Where's the constructor。Losing my land。嗯。Ope， sorry。 Someone one's distracted me。

Kai says is using like type de， but recommended in C plus plus。 Yeah， so using as is an alias。

 And it's pretty much what you would use instead of type de and C plus plus。 but I mean。

 type des are really just。I mean， type depths you typically put at the top of your file using as is more like an alias like。

I'm pretty sure using has scope， for instance， which is another reason why it's quite nice because it。

Yeah， it actually has a sense of scope。Someone says， okay， so another great question。

 Sush says why is the constructor private， That's a great question。

 So why is this iterator constructor private。Why is it not public？What we've done here。

Is we have made it。Private， but then we've made Instac a friend of this class。

Which might be a little bit strange， but essentially what this means。Is that。In stack。嗯。Is able to。

Well， okay， so the the short answer without getting into the technicalities is that when it comes to an iterator's constructor。

 we want to be able to construct it inside of the Instac。 But if we made this public。

Other people could construct it because see how all these things here are like。U public。

And we said at the bottom here that the type inst iterator is actually valid。

 it's just like with a vector。

![](img/21104176e331387dea78d85347debcac_97.png)

RightSo to give you an example， a standard vector。Has a type in it。

 It has a subclass in it for an iterator。 and that iterator is。Can I just do vector slash iterator。

 Will that work。No。Not' sure where to find it。 Stan a vector iterdo。Anyway。

 I don't know if it's clear in the docks。 Maybe I just don't know where it is。

 But the point is that somewhere out there like standard vector int iterator。



![](img/21104176e331387dea78d85347debcac_99.png)

Is a valid type， right， It's actually a valid type。 You can use it if you'd like to。

 but you can't construct it。And that makes sense because we wouldn't want you constructing your own vector iterator。

 Like the only， the only way you should be able to get a value of that type is if the container gives it to you。

 So by making our iterator constructor private。We can allow the scope of this class to be public so that people can call the interface methods on the iterator。

But they can't construct it。 So it's pretty much just like a。You know。

 prevents dumb things happening。 And I'm pretty sure we make it a friend of Instac so that Inst is able to。

Access things。 And I can't remember class scoping off the top of my head。 I'm sorry。 but。

 but generally speaking， the point is we want the we want Instac to be able to construct iterators and not anyone else。

And you might think， oh， well， like， sure。Why don't we just make the whole thing private？You know。

 well， the whole thing is private but。um。Then it's like if the whole thing's private。

 then we won't then people like you and me won't be able to use the itator methods。

And if the whole thing is public， then they might be able to construct。The iterator themselves。

 which we don't want。 So we make the interface public。 We make the constructor private。

 and then we give Instac permissions to construct it essentially。

 So that's why we can do things down here like actually construct this。

 Otherwise I'm pretty sure we'd get a scoping error。

 It would be like sorry you're trying to use a private part of the iterator type。

So that's why we have that there。Now， let's try and run this。 I don't think I've modified anything。

 I just have all that stuff crap down the bottom。So let's try and run this。 I've got demo 7。

50 stacks， so。嗯。Oh boy。 So this is an old piece of code that I found。To run it。

 but let's just ignore that for a second。There's a lot of stuff there。

Let's see if this compiles first。Great。Means my prep wasn't a waste of time。Oh。

 I just did get check out。Great， yeah， build， run it。 Okay， so it runs fine。

 I just get checked out my file， which got rid of the comments。😊，So this runs fine。

 We managed to push to the stack。 Okay， let's try and get an iterator for it。

 Iterator begin equals L dot begin。Okay， now we have an error unused variable。

Sursed I'm getting that  error。I thought I'd turn those chs off。嗯。I'm not sure that's really weird。

 but you know， we can we can print this out， right， standard CR dot begin。

 and this should give us our first element。We get a one。And now we can use it on a loop too。

 We could say， you know， four auto I equals。L dot begin。 I does not equal to L dot end。

Plus plus IT and then standard C IT。Like that，750。Yep， and then we can run it。And then we get  one，2。

3，4，5 as you'd expect， right。嗯。And that's， that's really all there is to it。 right， Like， it's like。

 okay， well。You have a container。

![](img/21104176e331387dea78d85347debcac_101.png)

We had to add these functions to it， which are all pretty standard， you know。See， begin C N。

 begin an end for const。 begin an n for non const。 They all just construct an iterator。

 They begin ones construct an iterator that takes in first object。

 The end ones construct an iterator that takes in a notion of the last object or null pointer is pretty standard with linked structures。

Our actual iterator itself just stores a pointer。To an object or some kind of reference to an object point is generally fine。

 and then it has a whole bunch of standard public interface methods like equals not equals plus plus D reference。

 whatever with these iterator traits。 I mean the good thing about iterators is you can you can largely like assignment 3。

 which we will talk about next week。Is a much more complicated version of all of this with templates。

 right， It's a graph。 You're trying to build a templated graph with its own iterator and。

That's complicated。But it's still all basically， it's all the basics are all still from here。

 You're still having a class with a subclass in it， and that subclass is an iterator。

 And that I stab its iterator traits and。Has to have these general kinds of methods。



![](img/21104176e331387dea78d85347debcac_103.png)

So some questions， Jin says why we use C star pointers here。😊。

We like to use C style pointers in libraries generally。What。Well， I mean。

 most of the pointers here are what you call。嗯。Like the main thing to avoid here is not the use of pointers because pointers can be beneficial it's that we're not doing any explicit memory management。

 that's the most important thing and a lot of the pointers you see are like the this pointer or the de referenceence operator we not actually doing much pointer arithmetic here which is one of the most important things。

嗯。But just to kind of move on from here， if you wanted to say， take your。



![](img/21104176e331387dea78d85347debcac_105.png)

Iterator， your， your object and create a bidirectional iterator。

 You would just have to add more methods to it。RightNow， usually in the case of a reverse iterator。

Try to remember so sometimes you can reuse your iterator。 sometimes you can't。

 I think for a reverse iterator。We might need a separate。Oh， sorry。



![](img/21104176e331387dea78d85347debcac_107.png)

Yes， so for forgetting， forgetting that for a sec。嗯。



![](img/21104176e331387dea78d85347debcac_109.png)

I hope this is， let me just triple check this is not C plus plus tiny。It should be fine。嗯。

So Pin says， could I run standard sort on Inst， That's a good question。

 Let's look at the algorithm standard sort。 Let's see if we can。



![](img/21104176e331387dea78d85347debcac_111.png)

Figure out what it takes in。 So you can see that standard sort expects a random access iterator。

 We couldn't provide that at best， we could provide a bidirectionalal iterator。

 So remember the iterator types you have， we have our。Where are they。

Input output forward by directional and random access。 Now， generally。

 we're not going to be worried about input and output。

 But forward makes sense we want to move in one direction。

 We could modify our iterator to move in another direction potentially。

 like here you can see we've got this plus plus and minus minus。Can we make it。

 Can we make it go in the other direction。Like， is that possible？Depends on your container， right。

 In this case， our container， we would struggle to because we have a forward link a forward list structure。

 right， We would have to， yes， we would have to modify quite substantially for the time we have left。

 I wouldn't want to just do that ad hoc。 We'd have to modify it to add a prev。

Pointer so a doubly link list。 And then we could start adding things like operator minus minus。

 operator minus minus post increment。And then that would allow it to be a。Well。

 an iterator you could move in， I mean， let me go back to the iterator's lecture because think I think this has a useful slide in it。

That we want to refer to。At least I think it does。 or I might have put it in algoes。

 over feelinging I might have put it in algoes。Where is it。Yeah yeah， iterated categories。



![](img/21104176e331387dea78d85347debcac_113.png)

Essentially， this is a really useful diagram to refer to in terms like forward iterators need to。

 you know， have the stab stab。 They need to be able to be de referenceenced and get a reference to it。

 which is an important thing。 Like， if your de reference has to return some notion of。



![](img/21104176e331387dea78d85347debcac_115.png)

呃。Like a reference， see that here how our dereence operator actually gives us a reference。😊。

To an object， not a value， not a copy because otherwise you can't do reference assignment。

 you can't like de reference and assignment， it has to have plus plus and it has to have double equals and not equals。

A bi directionionalal iterator， we just need to put the operator minus minus in and stuff like that。

 That's being able to move in both directions。A randomandom access iterator we obviously couldn't do as well。

 typically random access iterators only work with like random access。Containers。

 actually something that's contiguous。 We talked about this back in week 2。

 but random access means that you can jump an arbitrary number of steps。

 essentially in constant time， like in a in less than nonlinear time。Less than linear time， sorry。

So bidirectional， we can't really do with this structure。

 That's why some structures don't have bidirectional iterators。 They just have forward iterators。

 One thing we can potentially do， though， is create ourselves a reverse iterator or we can't even do that in this case。

 actually， I was gonna to say we could do that together， but I don't think we can with this example。

 So a reverse iterator， if you think about it would be maybe a structure like this。

 except when you create it， you give it the end iterator and the plus plus operator。



![](img/21104176e331387dea78d85347debcac_117.png)

On the reverse iterator， I just moves through it backwards。

So this is kind of how you get to manage this abstraction because you would you know your plus plus would actually be going to the prev So your reverse iterator when you plus plus it it would be starting at the end and going to the prev like that until it reaches the start。

 Both of these things are only really feasible if we were to complicate our data structure here。

Which， again， as you know why， like， if we go and look at like standard lists and standard board list。

In C plus bus， these are just different structures with different capabilities。 So， you know。

 standard list here。It's see begin。I'm not sure where we find what type of iterator it is。OhYeah。

 here we go。😊，So you can see here that for。Iterator and constant iterator。

The trait of that iterator is a bidirectional iterator。 Fort the legacy part。 That's just。

That's long winded story， but the forward list is a similar thing， right， It's a forward iterator。

 so you can only do what forward iterators can do on a forward list。

And you can do bidirectional stuff on a bidirectional list。嗯。Yeah。Back to the slides。



![](img/21104176e331387dea78d85347debcac_119.png)

One cool feature about C plus plus is like beyond， you know。

 you could go and define a reverse iterator and put I begin an R end and CR R begin and CR RN and stuff。

 or you can use an automatic reverse iterator so。

![](img/21104176e331387dea78d85347debcac_121.png)

A。When your iterator has operator minus minus on it and it's essentially bidirectional。嗯。

You are able to easily define reverse iterators using the STD reverse iterator。Type type trait。

 I don't know what you'd call it。 And it's basically like a rapid that takes your type。 and it， it。

 you know， statically converts it to something that could be reversed。

 This is a very cool and handy thing。 In some instances。 I haven't used it a bunch。

 but you can see that it's essentially a whole whole bunch of。You know， your。

 your your everything here is exactly as you would normally do it。 if you define a custom。

 it's just that instead of specifying that the reverse iterator alias point like refers to a class object that you've created。

 you simply say， oh， no， this is actually just a。Basically。

 a converted type of my iterator that's reversible。

 And you can do the same thing for the constant iterator as well。

So that's a great way if you would like to create a bidirectional iterator and remove a whole bunch of boilerplate code in a lot of ways。

 a lot of the advances I think we've seen in。😊，Le in my opinion。

 it's like C plus plus 11 was a massive jump in terms of。Providing。A whole bunch of algorithms。

 data structures， call functionality libraries so that。嗯。Programmers could write programs easier。

And a lot of the things that I've seen personally since C+ plus 11 like in 14 and 17 seem to be。

Really trying to just stop making your codes over both， because a lot of。

A lot of C++ still has a lot of boilerplate， and you've probably seen that with assignment2 and some of the operator overloads。



![](img/21104176e331387dea78d85347debcac_123.png)

And。Yeah， this。

![](img/21104176e331387dea78d85347debcac_125.png)

Yeah。More just detail on this front。 The last kind of comment here would just be on random access iterators。

 so。Random access iterators are exactly what you'd expect they have。The same methods they。

 they have well。Yeah， well not the same methods， but you can see the main methods they have。

 they have like a plus or a plus equals ability and they have a minus or a minus equals ability and they have the index look up as well。

 the subscript operator and you know this is kind of what you would expect a STL vector to essentially be implemented like。

Yeah。This is actually a good example of where the difference type is kind of relevant because。

You can see that for the plus equals and the plus and the minus。

 what you're essentially doing is jumping elements， right in those cases。

 So you're jumping elements from here to here and in those cases。

The difference type is essentially saying， what is the space between those elements， which， again。

 for。For most， kind of concrete。Containers that just store values。

 it's pretty much just going to be type in or type T or essentially the type or whatever your container is storing。

Anyway， that's actually kind of it today that Instac code。

 which I think many of you will find quite instrumental in getting started on assignment 3 is actually in the lectures repo so you can kind of go and have a look at that yourself But yeah just since we're at the end now I just wanted to check to people are there any questions people have anything I need to address at the end here。



![](img/21104176e331387dea78d85347debcac_127.png)

PIyn says， will we learn more about how standard algorithms do their template since it assumes specific functions exist？

呃。Well， no is a short answer。嗯。No， that's just not something we cover a lot in the course。

I don't actually have a lot of detail on that。嗯。But I mean。

 the algorithms will just be just we'll be taking in iterator types。

That so like the algorithms that we are to take in a generic iterator type that looks at the iterator traits。

At compile time to figure out how it can interact with it。Ryan says，  what can I do to get into 6080。

 sadly I don't handle any enrolment stuff so I don't really know how to help anyone with enrolment stuff。

Any other questions tonight？Jin says， can you explain using a bit more using is like using is really like Kai referred to it as a type de。

 So like you， you could do something like this， right， You could say type de。



![](img/21104176e331387dea78d85347debcac_129.png)

Yeah， I'm just trying to remember type F iterator。

![](img/21104176e331387dea78d85347debcac_131.png)

Iterdo。So that's kind of how you'd normally do a type def and C It's just type defs typically sit at the top of your file and are essentially。

How would you put it？You know， they're， theyre， they're in the scope of the whole file。 So using。

 it's using iterator equals iterator。Very similar， I mean。

 it's pretty much the same thing conceptually， it just happens that it's you can scope it into particular parts of the code。

 there might be some other benefits I'm unaware of as well。Kai says。

Since iterator traits had deprecated what's the new way to do stuff I may be try and share that somewhere on the lectures page。

 but we'll share we we did a we did a couple of lectures last year with C+ plus 20 features and the feedback we kind of got from students was just that。

It was。Very hard to understand。 And they couldn't find many resources online for it。

 So we kind of opted to stick with this for this year and probably next year， potentially as well。

I mean， it's still very modern right Like there's a lot of C plus plus code bases out there that are still running like C plus plus 11 or prior So it's not like we're behind the curve or anything on this stuff。

😊，But yeah， well， I'll try and put that up so you can check it out。

Nathaniel's answered some other questions。Yeah， there' there's another like there's another type when it comes to operator overloading。

嗯。Called the spaceship operator， for instance， So just as a quick comment。

 So it's like C plus plus 20 has a spaceship operator。



![](img/21104176e331387dea78d85347debcac_133.png)

Which was basically a。嗯。Once people realise like two。

To do all of the less than greater than less than or equal to。

 greater than or equal to equals equals and net not equals 2， people kind of realized that。

All of those comparisons really just rely on like a few basic things like what's equal to and what's less then。

🤢，So for instance another C++ 20 feature and this is another one that will probably come in next year but well it's it's in the compiler now but like we'll probably introduce it into the course next year is this because at the time last year again it just wasn't very well documented and there weren't a lot of great examples online but basically。

They're not gonna give me what I want， probably。This was the other problem。 It's just like。嗯。

The idea was that you， you define。ち。One function， instead of having to define all six of these。

 right， which are all the relational and quality operators， you're able to justify define。

1 like this。In this case， it's defaulted。W whichhich is just because you know。

 thestruct wrapper is just going to do a member wise comparison of the value。

But I don't know if's this this was kind of the problem we had last year as well is that some students were like looking for some actual examples of these and there was just very little that we could point them to because pretty much every example online was just like default。

But yeah the idea here is that this is trying to remove boiler plates。

 instead of having to define those six operators you can actually just use one operator and that's a C++ 20 feature。



![](img/21104176e331387dea78d85347debcac_135.png)

To make your code more concise and avoid repetition and all that boilerplate avoid avoidance that I mentioned earlier。

Cool al right。 Well， the questions， I we haven't got too many questions， so。

Let's wrap up for tonight， check out assignment3 sometime between now and next Monday。

 we'll chat about it next Monday， maybe Tuesday I don't know。

Gueests choose David we'll see how we go on Monday。And yeah。Congrats on getting assignment2 done。

 youre two thirds of the way through the assignments in the course。

 this course has a fairly small exam so。You know， keep up the good work， everyone and。Yeah。

 that's really it。Nothing's really due till the start of week 10 now in this course。

 Sir good luck with your other subjects and catching up on sleep。

 you probably didn't get during flex week。嗯。Yeah， have a great night， everyone。 Oh， and。

 and feedback。 Oopsy， Oopsy， always forget， You know， fill this out on your way out， too。

 That would be great。😊。

![](img/21104176e331387dea78d85347debcac_137.png)