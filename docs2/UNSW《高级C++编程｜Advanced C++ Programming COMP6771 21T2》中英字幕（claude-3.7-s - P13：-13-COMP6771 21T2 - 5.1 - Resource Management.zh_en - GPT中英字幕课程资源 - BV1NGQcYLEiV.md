# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P13：-13-COMP6771 21T2 - 5.1 - Resource Management.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Good evening， everyone。 Welcome to。Beginning of week， five。So fast。

 I feel like we're already kind of like so far into time。

 I think the end of this lecture marks the midway point for。All of the lectures in this course。

 because there's nine weeks and we'll have done four and a half worth of content at the end of today。

 so。Congrats for making it this far。 I guess the any other interesting updates are。

Many of you probably know this from getting emails from UNSW， but the census state has been。

Extended till the end of this week， We still ending to get your assignments back。

To you at the end of this week， probably on Friday， when I send out the notice。

 So keep an keep an eye out for that， though， yeah， I mean， not。

 not that like a ton of you are just going drop suddenly because your assignments are bad or anything like that。

 And generally speaking， most people's assignments are very good。So we'll see how we go but。Yeah。

 so you'll get that at the end of the week。 I think the only other update that I have to share with everyone would be around assignment。

 too， so。There was a good foreign post。A question about。So if we go look at assignment2。

One really interesting part about assignment too that some of you might have glossed over is that。

You are dealing with a Euclidean vector which consists of a series of doubles right so your Euclidean vector always stores doubles and it mightte store。

 it's a two dimensional Euclidean vectors two doubles and 10 dimensional stores 10。

 but they're all doubles and when you're writing tests for this assignment， you know， maybe I can。

You know when I'll just quickly clone this again when you're writing tests for this assignment。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_1.png)

You will be naturally trying to。Create a。It's fine you'll be trying to create a Euclidean vector。

 populate it with something and then immediately after that you're probably going to do an operation on it like maybe an addition subtraction。

 whatever， some kind of mutation and then you'll be comparing values okay so there's going to be a lot of comparing that happens in this assignment and the reason I point that out is because。

If I just go look at our most basic test file here。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_3.png)

Then， you know， you'll be doing something like。Check。A1。

0 plus a like say you're doing something like this right now this doesn't even make sense what I'm writing here。

 but whenever you're doing these kinds of checks， what you're doing is you're comparing doubles Okay。

 because the Euclidean vector is made up of doubles and anytime you deal with double comparisons in this assignment。

 you're going to be dealing with some potential form of floating point error。And。

That's not good because that floating point error can result in cases where 1。0 is not equal to 1。0。

Not literally like there， it's obviously the same， but like two things that should be the same are not because of floating point errors。

If you aren't familiar with floating point errors， you don't have to be extensively。

 I'd probably spend a little bit of time Googling it because it's an interesting concept regardless。

 but。The way we're going to get around this in this course is through you know epsilon testing。

 which is the same way you kind of get through it in a lot of courses so let's say for a second that we have a vector like a one here。

And then let's just say that for example， I want to say a1 times equals 2。

I want to you know multiply all the things by two and then I might create another。

Another Euclidean vector called B1 which just consists of three elements that are all 6。

0 right so a1 times equals 2 and now what you might expect is you might say require or check that a10 equals B10 so this is a bit more of a concrete example now this case has the well maybe not this case specifically but these kinds of tests have the potential fail because doubles aren't always precise so the way we get around that is fairly standard epsilon testing which is that rather than checking if two things are equal you simply subtract the two。

And then you check if the difference between that subtraction is less than some kind of threshold。

Now I I don't remember off the top of my head what a reasonable threshold is for it。

 it's something like that generally speaking， that kind of thing will be okay。

And I too many brackets there。 but' that's kind of what you do。

 So instead of saying you're going to check that a1 is equal to B1， the zeroth element。

 you do something like this， because this is kind of guaranteed to still pass if there's very slight floating point errors with the doubles so。

How you go about that is totally up to you。 You can define this as a constant somewhere because we introduce this late not late I mean。

 it's only a third of the way into the assignment release。

 but since we like introduced it not at the start I'm pretty happy to be flexible on how we mark this time So it's like you know if you want to do this as a global typically you'll have some people do like epsilon like this。

 and then you'll just compare it like that for all your tests So it's always using the same number and I think using this number is fine again。

 I can't remember the specific standard yes， and then Ryan's pointed out an even better way to do it。

 which is how we would have asked you to do it if if we'd kind of remembered to do this at the start and I'm sorry that I forgot but catch2 so that was just kind of showing you in a very very literal way how you deal with that problem though catch2 has a bunch of really helpful libraries in it that would。

Even cleaner and make more sense in your code。 And I haven't worked with these extensively。

 So I'm seeing if there's like a。不是。Simple。Example。But essentially， if you go， yeah， here we go。

 that's kind of closest to something。 So you'll kind of see here that catch2 has a whole bunch of things like this where what you do is。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_5.png)

You require that the difference between two numbers。

 which in this case might be like a value in two separate Euclidean vectors。

 you just check that that's less than the approximate value of zero with this margin。

 which is basically what I wrote， it's just it's a slightly nicer abstraction。Yes， that's。

 that's kind of the general g。 So， you know， or something like this is all fine。

 Like you'll find like there's a few different ways to do this。

 But the point is that a prox is a catch to。Library function。

 I don't think you need to include anything because the。

 the way catch2 works is that when you actually build your tests。

 you would have noticed in your C make list for your。Tess。

RightLike when you go to your C make list here you would have noticed that you link all of your tests with catch2 and then I believe that in test main it actually hash it includes catch2 So essentially the HPP of catch2 the header file is included in every test file by how the build configure done so that's how you can just use check and require without having to hash include anything because the link is actually linking the cppP file that's just hash including that So if we didn't have this you could also just hash include you could also just hash include like catch2/lash catch do HPPP at the top of yours as well。

Yeah， catch to us a whole bunch of stuff about floating points and whatnot。

 So the point is that you will have to consider this。

 It's super trivial to consider I've just kind of walked through it in like all of a few minutes because otherwise your test might fail if you just do literal comparisons Chelo says are we supposed to do this for the equality operation overload as well。

 So the point is that in any in any case where you're comparing if two doubles are equal。

 you're gonna have to do this generally。Yeah， so I mean， if you don't do it。

 you might actually even fail your tests in the worst case。

 but if you do pass your tests it's still like a best practices mark reduction。

Last year we we told students that we're only going to give them whole number doubles because we didn't think about that till the last minute and then this year。

😊，Just kind of slip past us again， so we make a whole bunch of adjustments to assignments every year and that one slip past us。

Yeah， so Pson says so double double so double equals， we have to change it to doing the abs thing。

 Yeah， that's correct。 So it's pretty much just what I wrote here before。

 It's like you don't want to do this where either side of the equality are。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_7.png)

Doubles， you'd prefer to do something like this or even better what we talked about with using the catch to libraryro stuff because that's even cleaner and clearer。

嗯。Yeah， it's well， oh yeah。 So。 And then shelo said so in the Euclidean vector library itself。

 when checking two vectors are equal。 Oh sorry， I understand what your question is now。 Yes， yes。

 essentially。Essentially， anytime you're doing comparison this is true for all of computing。

 this isn't like an assignment two thing。 Anytime you're doing any actual comparisons of doubles。

 it's usually good practice to do epsilon checks， particularly if the doubles could be very small and very large because that's where floating point errors occur like in reality。

 this won't produce a floating point error because there's gonna be no precision loss。

 So when I said like it's good practice， even that might not always be necessary it's like。

This test is probably not necessary， but definitely for your quality operator。

You would need something like that。 Pson says， how do we decide the epsilon then， I mean。

 I already told you this kind of things fine， Like it's a somewhat arbitrary number。

The the the the higher it is like the bigger the value of the epsilon， the more likely it is that。嗯。

Things with really subtle。Differences won't pass， but the lower it is the。How would you put it。

My brain just blank。 Yeah， like if it's a really， really tiny number， then it's like false， positive。

 false negative kind of thing。 but this kind of number is fine like。The thing is。

 is that for the scale of testing you're doing in this assignment and the scale of testing we're doing。

In a lot of ways。The epsilon could probably be zero and you get away with it a lot of the time。

 so it's more just about trying to build in best practices here than get something specifically right in this scenario。

Anyway， that's all I wanted to say on that。Yep， so。

I want to move on to this week's today's lecture because that's pretty critical。

 And this week's lecture is on resource management。

 So resource management is kind of the beginning of。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_9.png)

诶。Oh my god， what's it。My phone is telling me that it's。😔。

🎼I don't know why I need to know that it's 6 18 pm， but I do。Do。Jesus。All right， well， that was fun。

 wasn't it？前も。え这这。Well， that was an absolute。Miss， thank you for that。嗯。Yeah。

 so we're going to be looking at resource management today。

 And this is really exciting because this is kind of the first time。😊。

We really get to talk about heat memory and we actually start to understand even more details of how some of these library。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_11.png)

Libraries are written like STL containers and stuff。So。嗯。Yes， is， as I just mentioned。To date。

 we've kind of just glossed over he resources， you know。

 we've kind of said this in assignments and in lectures that we don't want you dealing with new and delete。

 we don't want you mallicing stuff。Everything you do should kind of like everything you work with should be a stack resource。

 There are some stack resources like vectors and unordered sets that。

Will actually use heat memory like malic and free in the background。

 but you interact with their abstraction。 So to a large extent up until this point。

 heat memory has been abstracted away from you。🤢，But we want to understand it， because。You know。

 if you are a programmer of any sort， you don't just always use libraries。

 sometimes you write libraries。So this is really about understanding how the mechanics work under the hood and the things we're going to be talking about in new and delete。

 copy and move semantics， which is very relevant to your assignment。

 D structuresors and then L values and R values。Just as a concept because they'll come up a little bit more throughout the course。

First thing is a bit of a revision on objects so we talked about this back in week three about what is an object in C++ and one of the things we talked about is that you know an object is a region of memory associated with a given type so you know in standard vector they're all regions of memory somewhere on the computer that have a particular type that is defined by you or one of the other libraries。

😊，Now one difference again between a language like C++ and a language like Java or something is that C++ treats ints and bulls and whatnot as an object。

 it doesn't treat it as some kind of separate primitive type。

 so that's why in C++ we've been able to do things like say auto A equals int 5 because this is essentially treating an int like an object that has some kind of construction。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_13.png)

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_14.png)

You know， we're constructing this int with value 5。Now。

A notable thing about objects is that you can create objects， you can destroy objects。

 you know they have a construct and a destructor， you can copy objects or you can move objects and moving objects might be a new concept to a lot of people here。

 so that's definitely something that we can spend a little bit more time looking at。Now。This is。

This is also something that you probably all kind of learned when you did see at some point。

 which is that。When you first would have learned how to program with C。

 you would have been just putting variables on the stack and then at some point someone says，Well。

 what happens if we were going to create a variable inside a function？



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_16.png)

You know， say we have a。

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_18.png)

嗯。Say we have a function like， you know。Function A and then inside of that we want to like say you know。

 int B， and then we want to return or like， you know， standard vector。

Int B or even better auto B equal that。 And then say we want to return that。Now in a language like C。

 you can't do a lot of returns in a language like C plus plus。

 we know that you can return pretty much anything from a function， I'll just make this a bit clearer。

🤢，You can return anything from a function at the end， because。It will。

Copy it right so if you use this then in a main function。

 this is not something I'm going to run if you use this in a main function like you say okay well like auto C equals do stuff。

 then C will become a standard vector in and it will have been created inside the function and then and copied back up。

And due to the way C plus plus works， this copy is pretty efficient， though， generally speaking。

 if you want to create something that has a much longer lifetime， that' say， you know， isn't。

 isn't tied to the stack。We know you have to use Malik for that。

 that's kind of one of the first examples of you know when we come across Malik and C。😊。

The other reason is because we can't really have long life you can't really return a reference to something that was created in a function which we'll talk about in a sec。

 So generally speaking， there are three ways to try and have give a variable a longer lifetime than the scope it's defined in。

 that's either copy it out of the function upon return that's either returning it via a reference。

 which is bad and what we talk about in a sec or that's returning it as a heatap resource。

 essentially malicking it， malicing the memory so that we're controlling it。

 So if you think about stack memory as programme controlled memory。

 And if you think about heat memory or malic stuff as programmer controlled。

 then you know that's kind of in our hands and it doesn't get free automatically for us on the stack。

 Now one thing we're just going to totally rule out is trying to。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_20.png)

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_21.png)

Create longer lifetimes with references to avoid kind of copying things。So generally speaking。

 what this example is trying to demonstrate is that if your function returns a reference to something such as in these cases on the left hand column reference to end and reference to constant。

Then you always want to make sure that what it's returning is something that was actually passed into that function。

Because generally speaking， the only things the function will return are resources that were created inside the function and resources that were passed into the function as arguments。

 So that's why we we only want to do that in this case here because you can see that in this case I is passed in。

As an argument in both instances。Whereas on the right here we have a case where eyes passed in sorry passed in as an argument。

By reference is the important part I passed in here as a non referenceence。

 so it's actually copied into the function， so it forms part of the functions like local stack and in this case here we're actually creating a variable on the functions local stack so but we're actually returning in here now。

😊，This here。I think in some situations will work and sometimes it goes okay。

 but generally speaking it's bad practice。 So if you want to say create something inside a function and then return it。

Without， you know like。without kind of copying it back out then we don't want to do something like this。

 so let's just steer clear of references as a way to try and solve our like long life problem The way we solve our long life problem in C plus plus is the same way we do it in C which is that we store objects on the heap and objects on the heap stay there and they don't really get garbage collected they don't get popped off the stack as functions are being called and completed right because stack is totally you know managed by。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_23.png)

嗯。I don't really know what you describe it as managed by it。

 you wouldn't say managed by the compiler， but it's baked into how the language works that。

If something's put on the stack。When its name goes out of scope。😡。

The destruct is called on it automatically。 So in this case here， like。

 let's think about this program for a second。 I always like。

 I always like to ask this question to people， which is like。

In this probe let me remove a few lines just to start off and my question to you and I wait 10 seconds for people to reply is how many resources are created here。

 like tell me all the resources， how big are they are they on the stack or the heap is there one is there two is there three is there four is there five like what's actually created during the duration of this programs running？

In terms of memory that like we've created by writing it。Swaing for the。

Good old laggy lag to to catch up。 Sorry for those who have already answered in a listening。Okay。

 we've got a few answers， four bytes of an int。Someone says， would it be a heap？

If one says main function in， Richard says main。D Vche says 16 bits of memory to store four integers。

嗯。Kai says A is created on the heat。I really want to emphasize this because I don't think anyone seemed to quite nail it but。

Yeah， Jason's kind of getting close， but so in a line like this。

 think I think a common misconception people have is that you're actually creating memory here like this line is creating memory on the heap Yeah and Shirlo seems to be getting it so two things are actually created here one is a what we call a named resource which is a stack resource。

Which is a integer pointer。And its name is actually A。So stack objects typically have a name。

 sometimes we call them named resources or named variables or named data I guess。

 but it's a type integer pointer which on the CSE machines I think will be8 bytes because I think they're all 64 bits and then we have an unnamed resource。

 which is a he resource， which is what we malled。With like new or think of it and new as Malik。

 I think I'd probably just glossed over that， which is four bytes because it's just it's an integer right now in C plus+ I probably just did gloss over that from this example。

 we deal with Malik and free and C plus+ by using the new and delete command and C plus+ is a little bit smarter than C in the sense that it'll actually figure out the size of the type based on this here。

 So you know it just will figure out how big something needs to be。😊。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_25.png)

So a new and delete are essentially keywords that's like。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_27.png)

Add to the heat free from the heat， But this is really important because on this line here these two variables。

 these two pieces of memory are kind of like created and it's not really true to say that a refers to the maled the nude memory because a doesn't A refers to a pointer So everything every variable name is always a stack name it' it's a named resource on the stack。

 it's just that some of those named resources on the stack like a in this case point to an unnamed piece of heat memory because no heap memory has a name Every time you mal something。

 it has no name， it just happens that something with a name is pointing to it。

So that's the kind of situation we have in a program like this now。Because this is a stack resource。

 because this is put。Yeah， because this is on the stack。

 what it means is that the rules that we learned back in week  three about resources apply。

 which is that。When。A goes out of scope and it goes out of scope typically when we come across like the end of the function or something。

 when it goes out of scope， it immediately， it gets popped off the stack， it gets cleaned up。

 it gets destructed So all resources have the destructor called when they go out of scope So A goes out of scope at the end of this function。

 then it's a destructors called that's what happens to all stack resources are named resources。

But just I can see。Our unnamed resources are our he resources don't go out of scope。

 that's why they're really beneficial。 that's why we like using these he resources。

If I didn't do this， delete A here。This heap object that was created。Never goes out of scope。

 It never sorry it never has its destructor call because we didn't free it explicitly。

 And that's an important contrast because it it really isn't really like fair to say that A never got deleted because A did get deleted。

 A's a pointer。 what a pointed to didn't get deleted。

 So that's what this means in terms of C plus plus So you were saying create a new he object。

 typically you wouldn't even use in style。 you just do auto。

 but I like to do that just because it's a bit more explicit here。

And that would delete it at the end of the program。 So you know， if we tried to run this now。

 demo 501。嗯。Yep， and then。We get four。 Now this isn't constrained to really primitive types in C plus plus you can do this with tons of stuff。

 So here I've actually got myself a standard vector。

 So I'm creating a new standard vector on the heap that's constructed with this。

 So this is saying construct a standard vector with these three arguments on the heap。

 Store it in the name stack variable B。 And then we do something with it。

 and then we'll free it at the end。Oops， yeah。 So this all， this should work now as well。

 and we should get4 and one。Now， here's some interesting stuff。 Let's get rid of this。

 So we'll say auto B now and that'll still work for us。 Well this still work。

 What happens if I just say B0。

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_29.png)

So this one got really mad at me here， let me scroll all the way back up to the top。

Um and I think you just have a little reflection about like what's actually going on here because as we saw before。

 B's actually a pointer。😊，Bes a pointer to a。Heap object。So to actually get that he object。

 we have to de referenceence it first， and then we have to index it。 So when I say B0。

 I'm actually essentially just saying， I want to print。The start of the vector。

 like the start of the vector object， you know， so in terms of like， you know， paint。

 It's like the vector object might be this massive thing。

 And here's like the actual numbers we're storing like 1，2 and 3。34。

 and then B over here is just a pointer to this object， so when I say B0。

It's the equivalent of saying sorry when I see B0 in this case， it's the equivalent of saying。

 can you please get me， can you de referenceence？What's it address B plus0？

And that's like trying to dereference a vector。 So that's like no different to just like you having a vector appointed to a vector and saying printed out。

 And that's actually what this error error message is consistent with because what it's saying is that this is the same message you get when you try and print a vector right Like when you when you back in assignment1 tried to just print out a standard vector it complained about this It said I don't have any opera ans to the。

Output operator。Of this kind of thing。嗯。So a star gives us four because a' is just a pointer。

 I want to stress you。 this is this is not the same as int4。 Okay， this is just be really clear。

 So I think I've seen a few people in the chat get confused about this。

 This is not an integer array with four items。 This is actually saying a single integer with four in it。

 So when you de reference a you get you get the four。 Now to a couple of questions here。

So Dimid says so if you don't delete a then the heat memory will become a memory leak Yeah exactly so a memory leak is just memory that's been created on the heat that hasn't been freed correctly。

 typicallyy memory leaks are a problem because a lot of memories created inside a loops or programs that have any notion of loops so as the loop goes on they leak memory because resources aren't freed。

😊，Ef says is delete like free and C。 Yeah， so these lines。

 like to give you like the C equivalent of these lines。

 this one would be in star a equals malik of size of int times1 or something like that。

 And then this line down here， these ones would just be。😊，Free a like that。嗯。

So Charlie says probably missed it， but what's the logic for using new instead of just going auto a equals 4 That's a great question we'll talk about that in a sec so and then the last question is does delete work with destructors。

 so delete simply calls the destructor like the lifecycl of a resources similar no matter whether it lives on the stack or a heap it's constructedor at some point it's used and then it's destructed。

🤢，Totally standard doesn't matter what type it is。 It all follows that object model。

 The difference is that when you create something on the heap， it is not the memory is not delocated。

 It is not freed， and therefore the deor is not called until you explicitly do it。嗯。Yeah， so。

But to Charlie's question， what's the logic for using you instead of that？ Well。

 the logic is actually。Relatively simple， which is that if you don't use new。

If you don't like Malic something， it's just like in C。

 there are certain constraints with what you can and can't do with it， so for instance。

 if you want to return something from a function，😊。

That has like a longer life than the function call and its function call and everything else Then sometimes we like to use。

呃。New because it， you know， again， it won't just get popped off the stack for us。

 Another thing is that there's a lot of operations that sometimes like。

 and you'll see this in assignment too， is if you want to create in C or C plus plus a raw double array。

 which is something we generally discourage， right， So like auto B equals double1，2 through O C。A。

I'm not sure how to inline construct double arrays because I don't do it much， but。In C。

 for instance， if you want to create a， this is just a， say， say a sea line。

If you want to create a double array in C like this， so this is an array of doubles from C。

You actually need to know the size of that a compile time for it to be a stack object。

 the compiler wants to know that size of compile time。 It doesn't have to be a number there。

 It could be a magic number， but it can't be based on user input So like back to kind of C 101。

 you can't really say scan FD。嗯。You can't really do this and see right You can't really say I'm going to read the size in and then I'm going to create a stack objective of that size。

 I mean， in some circumstances you can， but generally one of the main reasons that we use Malik is for like dynamic sizing of things things where with the size could be big or small it really depends on some things that we don't actually know until the program runs So the dynamicness of heat memory is a big part of it。

 the other reason is that that stack is really small。 So if you want to say Malic。You诶。

You want to malic like1 GB vector with like a billion items in it。

 I don't think in a lot of situations that'll go down very well if you try and make， well， okay， so。

Vectctor is a funny example。 So I was just thinking what I said wasn't quite true because what a vector actually is is vector is just a stack object that actually Malic stuff underneath for you。

 So when when your arrays being resized as you're adding stuff to your vector or your set。

 it's doing all these Malic or news all the time for you。

 It's just hiding them away from you so that your programming experiences a lot better。

 And if you actually tried to create like a billion size。😊，Double array on the stack。

 sometimes the stack will run out of memory because the he will often have more memory。

Richard says based on my drawing， it seemed like we allocate memory for an object and a small portion of that objects memory is used for the vector。

 shouldn't the vector be using all of the object's memory My point here was more like a vector will probably have some other things in it maybe like its size。

 like in size and incapacity there's probably a couple of actual objects that probably a couple of pieces of information that are actually inside the vector itself。

 My point was that B in this case wasn't pointing to the start of some array。

This is an encapsulated object， so B just points to the object generally。

 It's like B points to a struct， it's the same kind of concept。嗯。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_31.png)

Yeah， so that's kind of a very this is something we haven't done in previous terms。

 but I think we underestimated how much people understood heat memory from their earlier courses at unI so that's the point is that sometimes we create heat memory obviously this example so straightforward that you're kind of like what's the point of that but a Euclidean vector is actually a really good example because like think about your assignment let's say someone can create a Euclidean vector with one element or a billion What size do you make your double array if it's not in the heat。

You can't like， you can't like re， it's one of those things like go and try and do it。

 like if you wanted to go and try and actually make your Euclidean vector with a double array。

Without。Heat memory。 you can only define your array once kind of a compile time。

 It can't like rejoin like re size and things like that。 And I think this emphasizes the last point。

 which is some people kind of ask me like， why can' I use like。You know。

STD vector in my Euclidean vector because that seems a lot better than double arrays because Hayden you said that C style arrays are bad and it's like。

Ct arrays pointers are all pivotal critical parts of C+ plus the point is that they are prone to mistakes are they are a massive surface area of problems。

 so it's really great if we can put those in the libraries that are really heavily peer reviewed get a lot of attention。

😊，Et cetera。 And then the people like us， state to A people actually， you know。

 use abstractions of it like standard vector。 So the the point of。

The assignment is to kind of give you a sense of like， what actually happens under the hood。

 And you get to be part of that abstraction that you're normally used to working with。 Gil says。

 didn't you say we wouldn't use new in our assignment， Oh， you're not。

 We're gonna use some fancy tools。 Not really。'， we're going to avoid it。 And I'll show you how。

 but I think I've done enough on。New and delete 101 here。 Oh， what is that slide transition。

I must have click the button by accident。Oh， I had another example。 Oh my God。 What have I done。

T like a can't。We at computers today。My goodness， okay。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_33.png)

I think I， I think I've actually answered。Someone's question the slides here which is that like why do we like heat resources。

 I've talked about this stuff already， but again one of the examples of it here。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_35.png)

Is that if I have a piece of code like。Why doesn't that build。Come on， build。

I must have not put that in the Seemakerlist file。Silly， silly， silly， silly。This is our new code。

 I've been rewriting some of these lectures。So。In this case here。

 in this demo 502 it's slightly off in the slides is that one of the most basic uses for heat memory is being able to just create something inside of a function and then return it。

And then it can be dynamically sized， and it can be somewhat。Ridiculously sized。

There are benefits for it。 The stack's convenient， but it's not great in every use case。That's why。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_37.png)

That's why we do that。Anyway， that's new and delete。嗯。We're going to come back to。

Ways to make pointers safer and ways to avoid the new keyword。嗯。Tomorrow。

 so that's like so today's like resource management generally。

 tomorrow is like how to make pointers and stuff safer。And that's very relevant for your assignment。

 So these two just today and tomorrow， quite relevant。 So firstly。

 let's have a think about vector for a second。 So someone asked before about you know how vectors implemented。

 and we're going to try and explore ideas around resource management by theorizing about what a vector might be So in week 3 we learn about classes and you could imagine today that this might be a reasonable estimation of what a vector is Now we know a few things about a vector。

 It keeps track of all your data because it's a list of stuff Now this one we can assume as a vector of。

 we're not getting into generic types today。 that's for week 7。

 but you can see a vector has an instar data， which we kind of can guess is going to be an array。

 It's going to be a pointer to some kind of Cst array that actually stores the data because a vector implementation can't use itself we need it needs to someone's got to use the C style array at some point and then a vector also has a size and a capacity It sizes how many elements it has at the moment its capacity is how many elements it can。

Before it has to dynamically resize the array itself。

We've got a destructor that does nothing and then we've got a constructor that takes in a size。

 this is just how we've defined it， we could add more if we want。

 and that simply creates a new C style array of integers with that size and then it populates size and capacity with that size as well。

This here， new， just like Mai can see， always returns a pointer。

Because new creates an unnamed resource on the heap。

 and then we get a pointer to that unnamed resource returned。 So that's why a new int。

Like this means new interray with exactly size elements gets created。

 and then the pointer to that unnamed resource gets assigned to this pointer here。

 which is kept inside the object。So。Yeah， that's kind of the start of it。 Go I'm stuck， sorry。

That's kind of the start of this。And then if we keep kind of exploring it。

 let's first talk about de structuresors， so we know from week three that de structures are called when the object goes out of scope。

Typically， that means when it gets to the end of the scope， it's defined in。

 which makes sense for stack variables。We love destructors because it can do things for us like close files and free pointers and clean up stuff。

 but he objects don't really have that。One problem that occurs from this is that let's say in in a class like this。

 if I kind of have this class in a file， so let's say I I'll just butcher this for a second。

 Let's say I had a class like this in a file。 and then I said。🤢。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_39.png)

呃。Auto Mv equals my Vc。And the size will be 5。 So a vector of size 5。

 So take a look at this program for a second and think about what's happening here is that we have a class that is constructed。

And this actual class object sits on the stack because， you know， we haven't malled anything here。

 It's just sitting on the stack。 But the class object itself， when it's constructed。

OrWhat is it constructing， Well it constructs an ate by it。Pointa。

Cause pointers on 64 B machines equals 8 B。 It's constructing a 4 B。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_41.png)

Int， because I think alls all standard ins are just 4 bys， I believe， and a second 4 byte int。

So what did we learn about how classes initialize with the constructor。

 Well it does the initialr list， then it default constructs what's not already constructed and then it calls the body。

 So in this case the value of size is going to be populated with the input size。

 the value of capacity is going to be populated with that and the value of data is going to be populated with a pointer。

To the heat memory。 So let's say I populate this with 5。 What this means is that if。

 if you kind of think about。Over here in our program， we have our like stack and our heap over here。

We will have our main function。And inside that main function， we created a。My deck object， which has。

 you know。16 by of space。So we created this thing， this named stack resource called My Vc。

Which is 16 bytes。And inside of that is， you know， three things。Which is our。

Or was it data underscore our instar Instar data？Which is 8 B。 And then we have our。

Size and capacity。 So I won't write that in， but it's like he is your size and he is your capacity。

So that's actually what it looks like。But。When we constructed it， because we used the new keyword。

 what actually happened here was that this constructeded a piece of heap memory。An integer array。

 a C style integer array that is size。 That is size ins。 So over here。There was a block of memory。

 20 bytes。Created。That consists of。5 in and this pointer over here points to that C style array。

So that's kind of the state of our program as we've created it。

 that should hopefully make some sense， but then what happens is as soon as they move from line 17 to 18。

This M V goes out of scope now， because I'm at the end of the scope。

 I defined M V as an object inside a scope， and we're out of the scope。

 So the resource has to be destructed。 So the resource destructor is called， which does nothing。

 which isn't terrible。But when a destructor is called in C+ bus。嗯。

What happens is is we call the destructor on all of the member objects。

But the member objects are just what's like like what's here because these are the members of the actual class。

 the object this over here is just something important pointed to。

 This is some programme and managed piece of memory it pointed to。

 So what happens is is these three things are freed。

 these are popped off the stack just like every other variable you deal with and at the end of this main function。

 everything that we created inside this class has been destroyed。 everything named。

 but this piece of memory remains here。

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_43.png)

So what we then do is if we wanted to actually get this working properly in our destructor because we decided to explicitly manage memory。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_45.png)

Ourelves with date malic or you， we then have to delete it。

So this needs to be in the destructor so that when this object is destructed。

 it doesn't just get rid of its members， but it calls the destructor， which calls delete on this。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_47.png)

So like C++ when you call delete on an array， it frees the whole array now。

 there's only two commands in C++。Really simple， you can either say auto i equals new。

 you can either say like X pointer。Let me write this in something bigger。

 There's only really a few things you can do with new and delete。 You can either say x。

 something v equals new X like this。 You can say x something v equals new x array and then give it like a size。

And the two things those are paired with， let me just let me just do this is you can call delete X and you can call delete Y。

Oops， sorry， delete why。So。😊，With C++， you can either create。

An object that could be a standard vector of nts， right。

 Like a standard vector with a million ants is still one object。

Or you can create a C style array with that object。So you could， in theory。Do autova equals。Newsed。

 you could do this newsest int。You can do new standard vector events。With 1，2，3。

Or you could do autovi equals new standard vector int。1，2， I'm not sure how to do that。

 but you could。 you could do this。 You could do like something like this。

 I'm not sure if you could initialize them all like that， but。

This here is actually creating a C style array of standard vector of ints because you have to remember。

 again， everything is an object。 int， double standard vector， standard vector of ints strings。

 They're all just objects。 and all new and delete know how to do is create。

Is Malic space for one object or Malic space for a C style array of objects。

 and they're the two things it can do and they're described in these two use cases up here。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_49.png)

So in this case here we have the delete brackets because data was a pointer to a C style array heap object because again it can either just be like an int or an array。

 they're the only two kinds of things you can have。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_51.png)

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_52.png)

Okay。Someone says，Does Line 9 call the assignment operator after？



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_54.png)

呃。Yes， so I mean， new standard vector inch。This will create some heat memory。

 this whole expression here will return a pointer and then that pointer will be assigned to the left hand side。

And last question I answer P S says， could you use var in declaring the array of the vector like vector vectorec 3？

I don't think so。嗯。And then Dim says， how does delete data know the length of data。

 That's a great question。 So how does this， how does this line here know to delete the exact size of that。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_56.png)

I'm not a low level expert， this is about as low level as my programming goes。

I'm pretty sure that every piece of heat memory has a size associated with it。

So that when you call free on it。You actually， you're actually able to free that exact piece of memory because like the heap is managed。

 like the heap is managed， like the heap itself knows how much space it has。

 and it's got chunks and stuff ready to go。 And it has like metadata associated with each piece of malic memory。

 It just doesn't free it automatically。 So it's not like the Wild West。

 The heap knows how big a particular piece of memory is。😊，Um。Yeah。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_58.png)

cause like the heap itself， and again， it would probably vary in many scenarios， but like if。

 if you have like the heap like this and you imagine it as like this massive array。

 say when you ask for a new piece of memory， it's gonna to carve out like a tiny bit of data up the front。

 that's like all the like the head data and then your actual memory is gonna be here。

 and then when someone asks for another piece of memory， the heap's like oh。

 I've got to make my little head of data to keep track of things， and then it creates the data here。

And then so forth。 And again， I'm not familiar on the details of it。

 but typically then heaps heaps are kind of like kept as as a big link list or the headers are like or can be kept like that they're all talking to each other and that's how the heap works So it knows how big it is when you ask to free it because when you say hey I want you to free like this piece of data here It's like oh。

 let's look at what's associated with that I have information here that says it's this big and then I'll get rid of it。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_60.png)

So that's how it does it in a nutshell。 I'm not an expert on it。

 but I hope that gives enough comfort。Let me look 655， let's see if we should take a break。Yeah。

 let's take a break and then we'll get into the rule of five because that gets beyond the destructor。

嗯。The tilder in line 6 is a is a destructor operation。 Yeah。

 I think we covered that in in the week  three lectures。 But yes， if。

 if you have a tilder in front of a class name and that's the function， then that's a destructor。

 So let's， let's take a five minute break and then。

Then we'll get stuck into the rest of learning about how to kind of manage and resources in our。

In a structure like this。 So sounds good。All right， welcomee back。呃。So let's keep going。

 I' just been reading the chat on the YouTube。 But I think an important thing to take away from this is that everything we're talking about is real and it happens because C plus plus in。

 in many ways， is just a。See with more， a lot more。 but this is so we understand things。

 There's not really going to be a lot of situations you're having to deal exactly with what we've been talking about today。

 but。The the point of today is largely that。When you are creating classes that manage their own HeAP resources or their own unnamed resources。

 like a standard V does。There are certain things you need to keep in mind。

 And that's what this rule of5 is about。 And we've already touched on one of these， the D structure。

 And so the point here is that。If you are creating an object that manages he resources。

 Euclidean vector， standard vector。You know， standard unordered map。

You need to think about what happens in the cases of destruction， copy construction， copy assignment。

 move assignment and move construction now I'm sorry that the order of constructor and assignment has swapped around there I'm sure that upset someone with OCD rest assured it was actually more chaotic before I cleaned it up in the prelecture but we need to understand these five operations。

 whether to default them， delete them or custom define them。So we already talked about destruct。

 I just want to make that clear， so like。Ruleer five。

 these are five things we need to do and we talked about destructors because the point was because we are mallaching on newing our own memory because we have some heap objects。

That we are storing as part of our resource that we're creating。

 we need to often define our& D structure because the kind of standard object life cycle。

 lifetime will not free our resource for us， so we need to handle that explicitly。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_62.png)

Now， talking about the other ones。Firstly， let's just like think about them all in perspective for a second。

If you have a class， like my Vic。Whether you define them or not。

 the compiler has these things kind of baked into your object。

 It has a kind of default constructor It has a copy constructor， a copy assignment。

 a move constructor we'll talk about that after in move assignment and a destructor by default。

 these do exactly what the language says they do right so like a copy constructor will by default copy all the data members across to the new object So you could create a Myvec object like that's the interesting thing about C plus plus is that I could create a Myvec object like this and let's first see if this compiles。

呃。Oh bugger off。 Let me， let me just use G plus plus for today，'cause。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_64.png)

This code wasn't meant to run。 but let'， let's say demo 5，02 here。And we need to make these public。

Sorry about this。 again， this code wasn't meant to be run。嗯。Great， so we've actually compiled this。

 and then this will run now， right for us。 I'll just make this slightly bigger。

 So this is code that will run if we run a dot out now。😊，I haven't defined a copy instructor。

 but I could say autoMV2 equals myV M， and this should work for us。Don't build it， Run it here。Right。

 so this should work。 So the compiler has created what we call a synthesized copy constructor。Now。

 back in week 3， we learned about synthesized constructors。 Do you remember that。

 We learned about how if you don't define a constructor， a compiler will generate one for you。

 and it will follow a standard behavior。 The same thing is true for copy assignment and constructor。

 move assignment and constructor and the deor。 And that's where this rule of five comes in。

 So in every class you create， even in if you've started assignment2， and you've started。

Making your Euclidean vector， these five things are synthesized created by the compiler when you compile your code。

 even if you just define the constructor and the whole point of this lecture is that if you are managing your own resources。

 you need to think about all these five things， you can't just say oh the compiler will probably get it right because it probably won't because once you start dealing with he objects。

The synthesized rules don't really work too well and that's what we just saw with the destructor but now we're going to be talking about these other four here。

 the copy constructor， copy assignment， move constructor and move assignment。

 these are kind of demonstrated down here， for instance this is a copy constructor here。

 this one is a copy assignment right so copy constructors are called even when you even though this looks like an assignment。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_66.png)

It's a constructor because the LHS is defined there， the left hand side。

And then these two are move constructors and move assignments。

 Now I know standard move to nearly all of you like what the hell is that？We will talk about that。

 but it's actually， it's pretty much what it sounds like instead of copying object A to object B。

 you actually just move object A to object B。 It's a little bit weird， not my favourite thing， but。

We will talk about it， so let's focus on copy first。If you have a class。

 let me get rid of my stupid head。What。嗯。Mu。Oh， what in that world。Just casually swapping screens。

Okay。嗯。Someone says， why did it ab， What do you mean， What a what a bought。Oh。That's a good question。

Double freak out， vote。Okay， I'll explain why that aborted in a sec。

 It's a very straightforward answerr。Becauseuse we didn't。

 we didn't do what we're about to do The point is that it compiled。 sorry my point， That's a great。

 sorry that I gloss over that。 So the point here is that this actually compiled。 It was valid code。

 like the compiler created this for you。 if it didn't if it didn't synthesize a copy constructor。

 then it would simply fail to compile because it would look at this code and say。

 I don't know what the hell you want from me。 I don't have any constructor that takes in myself。

 I just doesn't exist。 So so it compiled， but it ran and it failed。

 And I'm really glad you asked that because it actually motivates the whole purpose of this。

 which is that。😊，This is again what our class looks like by default back in week three。

 we talked about defaulting and deleting。Certain member certain synthesized member functions。

 So you don't actually have to add this to your class。

 This is what the compiler does for you right it defaults it。

 And if you add this you're basically telling the compiler what it was already gonna do anyway。

 which is like hey， can you synthesize this for me。The problem with copying is。

 if you think back to our。M S paint example。Where would。Here， the problem is that if you have like。

 what are we gonna call this one， This one is。MV。So if we have our MV here。Like that。Sure。

 that makes sense， but here's what happens when we copy it when we say to the compiler。

 when we say to the MV2 is a copy of it， the compiler will synthesize it and be like， all right。

 I know how to copy things。 I go get all of the data members。

And I copy and paste them and then I copy everything across。 So they're all total new copies。

 There's no references to anything。 these all of these data items are a total separate thing。

 there's 16 more bytes that exist now that didn't before。

 But the problem is the compiler the synthesized copy construct has no sense。

Of what anything points to。 So this int data here still points to the same piece of memory。

And that's kind of wherein lies the problem here， because it doesn't know how to copy heat memory。

 Remember， like heat memory is just。Super not managed for you。

 you kind of have to manage it very explicitly。When I created this copy here。

 we had two objects on the stack， but both of their datas pointed to the same memory。

 and that's actually why this one failed here because I got a double free error because this one was destructed first。

I can't remember which order the destructs things in， so one of them was destructed first。

 so it called delete data， so compile the synthesized destructor deleted all the members like it only does for everything。

 and then it called the actual destructor body which got rid of the heap memory。

But then when the second myvec object。Was taken off the stack， and its destructor got called。

 It tried to delete the exact same piece of memory because both of them pointed to the same thing。

So that's why we need to think about what happens when we copy things。

 whether it's copy assignment or copy construction both are kind of the same thing right little like boiler plate's a bit different but conceptually they have the same solution and that's why we have to look at something here。

This right here is the copy constructor。😡，It's a Myvec name that takes in a reference to a constant Myvec。

And then we construct our copyied thing with it。We can't rely on the compiler for this because we are managing resources explicitly。

 so we're going to do something like this instead。And let's copy this in and let' like let's just have a look at this。

So。What's actually happening here。If I was to just say， get rid of all of this。

 this would look like a standard copy constructor。 That's what a standard copy constructor that does nothing would look like。

 when I have this now。Think about what's happening。 I am using my initialized list。

My uniform initialization to populate all of the values。Of my new。Object now。

 if I had got rid of this line here for a second and we just kept it really， really simple。

This gives you a sense of what the compiler would try and generate for us by default。

 this is basically what it does。It it takes the old object and it uniform initializes all of the new objects。

So it takes the new object totally， and then it uniform initializes all of the new objects data members with the old objects data members。

 right it just like slots them all in like copy， copy copy like that。 I mean。

 this one should probably be capacity to be fair。 That's probably just a typo in the slides。

 I'm sorry about that， but it just copies them all across， but we don't want to do that because。

Since we're creating a new object down here， we actually want to create another 20 bytes here like that。

 one，2， three，4，5 like that， so there's our new 20 bytes。

And then we want our new pointer to instead of there we want it to point to there。

So it doesn't come up here anymore。 It points to there。 So to do that， we first need to create。

The new heat memory， we need to say new inch。Original size。 Or dot size。Now that'll work well。

 but the one thing we're still missing from this is the actual population of the data because this one here has could have data in it like you know one。

 two， three， four five but this one's totally new and it doesn't have any other data in it。🤢。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_68.png)

So I need to copy them across。 Now， we could obviously do this with a really simple follow loop。

 I could say like。嗯。4 in type was 0ed。 in her eyes less than original dots size。I， plus plus。

 And then I could say my nu。Data I equals a ridge。Dot dot I。 And I think this would work。

Let's try this out。No， because that's not what its name is。

And I don't need this because I'm defining the header file。

 I don't only need this if I was defining it outside the class。

But I'm defining it inside the class body。So now this works。

 and now this will run and it will not break because they are two。Separate pieces of heat memory now。

 so the copy constructor has successfully handled that for us。Which is very handy。

 So the copy constructor has like， so again， because we're managing heap resources。

 the copy constructor falls into the rule of5。 we need to think about and。嗯。Bam done。

We don't want to do that though because we want to avoid C style4 loops。

 I mentioned this in one of the the spec clarifications on the weekend is like you can do this for the assignment though it's much better practice and it's I'm talking like you know this is like a。

Half a mark out of 15 kind of thing or more， it's much better practice something around there to actually use STL algorithms where we can。

So here we're actually using the standard copy algorithm。

 which takes in essentially pointers or it takes in iterators。

 which are just pointers and it's saying， I want you to copy original data。

I want you to copy this many blocks of memory。Into the new data。 So it's saying old。Sorry， I mean。

 basically what it's saying is this is the old。😡，Data structure starting point。

This is the old data structuress endpoint。 So there's our old data structure starting and end。

 I want you to copy all that into the new data structure。 So this is now using STL algorithms。

Is this something we'd like you to do in your assignment？Again， if you don't have to。

 if you don't want to， it's not going to like stop you getting like well above 90 but。Well， above 90。

 I guess I should say but。Yeah， it's preferred to do and again。

 we kind of get these people being like， oh， I don't really know what to do here and blah， blah。

 blah it。😊，You know， because they're like， isn't this technically a pointer and you know。

 Hayden said pointers are bad because like dad' is a pointer？

Does that make it bad And I talked to Nathaniel about this over the weekend and the kind of conclusion we came to was the best advice we can give about like what。

 what a good boundary is between。Cause you， you have to use pointers to some extent。

 just it's the very nature of it。 But like， generally speaking， if there's a D reference anywhere。

 that's when， you know， you've started to probably like。A。Screw up So like if you。

 if you' like doing original data， that's probably like not great。 but generally speaking。

 if you're like doing anything like this， that's where you you're definitely doing something wrong。嗯。

So some questions。Fson says is it possible to avoid the fall loops with the operator overloading。

 It's pretty much possible to avoid fall loops in general with STL algorithms。

 I would say Jinghang says， yeah， but if everyone uses standard copy。

 then the code in this part is not。All almost the same。 I don't know what you mean by that。

 I'm sorry。嗯。But。Point is we've now dealt with our copy semantic。Correctly。Now， you could。诶。

You could go and we could make this for the copy assignment too。

 but that's an exercise I'll leave with you because I've kind of you know given you a bunch well not a bunch of hintsca to be honest with you。

 some of this isn't super applicable for the assignment becauses actually even easier in the assignment in some cases。

🤢，But I hope this demonstrates the point that if there's heat memory。

 you have to manage it explicitly。Jinghang says， but if everyone uses standard copy。

 then this part of the code is almost the same， I think I understand because five sense as you mean for plagiarism checks。

Assignment 2。Is a somewhat hard assignment to。嗯。Plagiarism check because it's a breadth assignment。

Right。That being said， it's really obvious when people cheat。 And also。

 you still have to write a bunch of tests。 So if you have any ambition in getting a high mark。

 you're going to write a bunch of tests。 and it's very hard to make your tests identical to someone else。

So， yes。Cool， that's， I'm， I'm kind of really dragging today out， which I'm gonna regret soon。

 I already showed you copy assignment。 I've no why I said this。

 they'll leave this to you for the assignment。 I'm sorry。We added this in。

So copy assignment is very similar， we're using a couple of other STL algorithms here we're using swap。

😊，嗯。And swaps really interesting because。What does swap do？My brain is melting， standard swap。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_70.png)

I mean， I get generally what it is， it swaps the values A and B。So this one confused me。

 I think when I first kind of looked at this a long time ago， I was like swap。

 I thought we wanted to copy， not swap。 but what's actually happening here is that。嗯。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_72.png)

Yeah， so the interesting thing is to pay attention to like how this is written。

 so when you call the operator assignment。We are creating a new third。My Vic。Which is empty。

And then we are， essentially。Well wait sorry， we're creating a third new MyV which is a copy so were using we're using our copy constructor here and then we're swapping our new one with our current one so like just to really very quickly demonstrate this because again I'm cautious of time is that you have your' like your old thing over here and you have your new thing over here and when you want to copy assign you're new to your old what we do is we go and make a like a V3 up here。

😊，And we use our copy constructor。To create it。So now the old one has things that we don't want。

And our our new one has things that we do because well new and the one we made has things that we do。

 and then after we've done that， we simply call swap on this。So that's what we call swap。

So what happens then is that our good one on our temporary object is now down here and our bad ones up here and then we delete this because it gets deleted once the stack gets poppeded up the stack。

嗯。Chillo says， isn't it inefficient to create a third copy。It's a good question。So they're like。

 why are we creating copy when you could just like。Deep copy every member over。

I'm not an expert on everything， though a couple of things I would point to are that。Generally。

 this is kind of easier and clearer than writing out the same logic again， of course。

 because like in this case， we could reuse the logic but， but beyond that。

 I actually want to say that there's a lot of things in C++ even I'm not familiar with。

 So for instance， like standard swap sometimes。Like。

 and I've had some people explain this to me before。Where， in some cases。

I'm not saying this is for standard swap。 It's just something I'm not sure about off the top of my head is that there are some cases where like C plus plus is very well calibrated to deal with things really quickly。

 So I wouldn't be surprised as what I'd say， and I could be wrong。

 I wouldn't be surprised if standard swap。In some cases。

 is capable of like swapping without like doing。Like full copies in terms of like copying things over is probably the same complexity as Reek is constructing something。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_74.png)

And then swapping it， but again it totally depends on what we're dealing with like we know in this class that constructing it and swapping all the member objects are pretty much going to take the same amount of time So in this case I think it's totally fine。

😊。

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_76.png)

So I'm going to move off copy。 I think I really spend a lot of time there or you might save another couple of questions。

 We can send them to the forum， but the point is that you know。You。嗯。You want to copy stuff。 Now。

 one thing that's that made no sense。 One thing that's not maybe not evident here， too。

 is that this is one implementation。 and then this is another implementation。

 So these are not all tied together here。 It's like this is one way you could do it where you you simply create a new object and then swap it immediately and then return the new this or you could have like a swap implementation like this depends on what you're trying to do。

 There's no real rhyme or reason about that right here。 Now。

I want to get on to standard a move because we've only got half an hour left。

And to understand standard move requires us to understand L values and R values。

 which is not exactly my favorite part of C++ because I think it's a bit confusing。🤢，InC++。

This gets a bit more complicated This is a slightly oversimplification。

 but in C plus plus we have notions of what we call L values and R values。

Most things that you look at or you point to。Or most expressions you look at will produce。

Or are either an L value or an R value。And a very general。The very general rule。

Is that if you ever have an equal sign？Everything on the left。Is always an old value。

Everything on the right is either an L value or an odd value。

So right hand side could be either left hand side is definitely an L value。

 Now what are those two different things？Well， an L value is an expression that's an object reference。

 Now， what hell is an object reference essentially。That means that an L value。

Refers to something that actually has an address in memory。

 It actually occupies space in like real memory and like the stack or the heap or something。 It's。

 it's an actual thing。And you have to be a bit more conceptual about like what our code is doing here because like I。

 J。 K， these are all L values。 Yes， they're on the left。 So， you know， they're an L value。

 But like think about what they are。 They are addresses to actual memory。 They're referring。

 They're an object reference。 like short， it's not a reference in the sense that。You know。

 it doesn't have the ampersand or whatever， but the point is that I is a variable name that simply refers like forget what a C++ reference is it just refers to an object。

It's representing an object。 It's a name of some object in memory。

Whereas an R value is an expression that's not an L value。 Oh surprise。And generally。

 how I think about all values is if。If it's something that。

Doesn't have any storage associated with it。 Then we generally consider it an R value。

 And you kind of know if something's an R value because it doesn't really persist。

 It kind of exists temporarily。 You wouldn't really know where to put it in memory。

 And this little piece of code I have here as an example kind of shows us that。5 and4 are。

Like 5 is in our value and4 is in our value， and 4 plus I is also an our value。 And you just， again。

 you just have to think about what these things mean。 It's like， okay， what's 5。

 Does 5 have an address in memory。 Where is 5。Like。I know where I is。

 I is a variable that refers to something， and we're going to assign the value of 5 to I。So whatever。

 you know， I will now be five， you know， I refers to some object and that object will now be 5。

 but what is this five here， It's an R value。It doesn't have an address associated with it。

 This I here is an L value。 So in this case， we're saying that J is an L value and I' is an L value。

 So you can， you know， you can make an L value equal to an L value。嗯。

Int K equals 4 plus I in this case I is an L value， 4 is an R value。

 which we've established and then 4 plus I is an R value as well。

Because remember the definition of L value and R value is this keyword here expression now I know a bunch of you wouldn't have done like languages courses。

 but expressions you got to think of expressions as essentially a bunch of values joined by pluses and minuses and equals and stuff right so it's a bunch of values with operators between them that can get like collapsed into a single value。

4 plus I here is an R value because where is 4 plus I like I don't like is it in memory and I think so Kai said in the chat。

 can I say that R values are things that are still in the registers but haven't been stored to memory？

I think that's a reasonable way to think about it if you think in those low level terms， yeah。

 like there are things that the computer might work with that just aren't in RA。

 they just don't have an address， you couldn't tell me what the point like what's the pointer to five。

In the stack， it it doesn't exist that like  five is just a number。 By the way。

 this concept is really annoying and confusing。 And you can go Google it and you'll see like 10 different explanations on Google。

 For anyone that did 1，5，3，1 with me。 it's like it reminds me of like functional and non functional requirements。

 It's like。It's hard to get a clear answer sometimes but this is my best attempt at it。

 I he says soate our values are literally the objects that variable are equal to。Not really。

 our values are just part like an expression that。doesnn't have an address associated with it。

 So my point is it's like K is somewhere， like I could get appointed to K。 I know it's on the stack。

I don't know like full plus I as just a value。It doesn't have an address。

 It doesn't it's just a value that I'm giving。 I'm assigning to something with a sense of an address。

 So， so again， I L value， JL value， KL value， everything on the left hand side an L value always。

But on the right hand side， it's like5 is an R value。 I is an L value because it has an address。

 I know what the I has an address。4 is an R value。 I is an L value， which we've established。

 and then the sum of these two is an R value。嗯。Yeah， I mean。

 L value and R value could generally mean left and right。

 but like L values can be on the left and the right， so。It's like， you know。

 don't take that too literally。Oopsy， I wrote constant percentage。

 That should be constant and percent。This stuff gets really confusing until week 8， I think， but。

I've got a slide here on L value references。I might。Might skip over this for a sec。

And talk about standard move。 and then we'll come back to it。 Let me just check what we got left。

 We got moving objects easy， and then we got。RII yeah， should be fine。Sorry。

 where was I going with this， I was here。 So we wanted to talk about standard move now。

Stand a move is this really weird function in C+ plus。🤢。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_78.png)

And the idea is， with standard move， this gets into argument binding and stuff。

 which can get very confusing really quickly， but。The idea with standard move is that if I have an object here and I say auto MV2 equals my V M V。

MV。Is an L value。In， it's a reference to an L value because I mean， you know。

 it's not a little a reference， but M refers to some object that's stored in memory。Okay， we know it。

 we created it， it's an L value。When you pass an L value into a constructor。

It actually explicitly calls something that looks like this and it always looks the same。

 it's always like my V， my V con reference or like that。This is what we call a。As you know。

 a copy instructor， however。If you want to call a move constructor。

 which we'll talk about in a sec what that is and a move constructor， it's like a copy construct。

 instead of copying A to B， it just like moves the memory from A to B。

It's like an efficient way to transfer， it's like a transfer the memory thing。A move constructor。

Actually， looks like oops。Actually looks like。This one， as we will， oh， nearly。Sorry。

 I think it actually looks like this。If you're not sure。

 you can actually go back to our rule of five slides back here， you can actually see it here。😊。

Is that this is our move constructor。Kind of look similar to our copy constructor。

 except there's no const because it can't be const because if you're trying to transfer something from the the the。

The old thing to the new thing， then you， you have to。You have to modify it， right。

 Like to to cop to move it， you have to mutate it。 So， so yes， that's how the move constructor looks。

 But anyway， back here。If we。

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_80.png)

Want to create a move constructor that kind of looks like this。And I can show you， we can。

 We can do something。 Standard Z out， hello。This is a terrible move constructor。

 Your move constructor should not print hello and do nothing。

It's a move constructed because it has this double ammppersand here。

 We'll learn more in week 8 why and what that is， But generally it's like if there's a double ampersand。

 then it's kinda like saying this is movable， this is ready to be moved。

 The problem is that there's there's no like standard command and C plus plus to say like know。

 auto M like let me show you auto M3 equals move。Like move my Vc M V like that。

 There's no there's no way to say I want you to call the move constructor。

 but in C plus plus we do have a way to effectively do that。

 which is to wrap what we're trying to move into standard move。

And I've already forgotten what it looks like。I thought it was that， but I thought I was going crazy。

And what happens is if you take something that's like an L value， like just a normal object。

 standard object， standard variable， and you wrap it in standard move。Essentially。

 what happens is the compiler converts it from an L value to an R value。

hich is a little bit of a weird concept， but essentially it turns it from is a bit of a hack。

 I think， maybe not a hack， but I think it's a bit unintuitive。

It turns it from something that kind of has an address and has， like， real。Memory to。

 to appear like something that's an R value， because if we didn't have this standard move function。

 we wouldn't be able to call this because there's no way to kind of just convert an object to this type that easily。

 So really in its essence， without either overthinking it don't don't don't freak out， it's like。

This is just a way of saying， oh， can you make this movable？So now when I pass this in to the vector。

 it will look at this and say， oh， that's like a movable M。 that's not just a standard M。

 a standard M I'll copy， I know what to call with that if I get a standard M I'll just call my copy constructor。

 but if I get a movable MV which is you know like that's like a raper function。

 if I get a movable M then I'll call my move constructor So you'll see here when I try and when I run this here。

 it should work。嗯。🤢，嗯。What have I done wrong？Oh my god。 So many errors。呃。

Your move still has a constantant， doesn't it？2。Oh， oops， sorry， I removed the wrong thing。Os。

So now when I run this， you'll see that it actually prints out hello and its Seg faults quite quite rapidly。

 I don't know why it's seg faulting， probably the destruction or or something I'm not sure。😊。

So the standard move is actually what calls that。 And if I just， if I got rid of that standard move。

 it wouldn't know to call the move constructor。 It would just call the copy constructor again。

So standard move takes an object and it makes it movable， it makes it ready to be moved。

 which is kind of like making it an R value。So that's how we use standard move and。Why。

 why we have standard move。Is that。Sometimes in C++。

 we want to take an object from over here and put it into a new variable。Without the penalty。

We don't want to have to， we don't want to like copy it and then delete one because you understand that's costly。

 it's costly to like if you have an object， you have to totally copy it and then delete all the old stuff。

 wouldn't it be better just to grab the contents and just shift it across。You know。

 rather than deal with all of that so that's kind of the motivation here of what a move constructor and move assignments all about。

And standard move converts an L value to an R value。 Now， in reality， there's no。

 there's no casting that happens that you should not think about it as like literally converting it。

 It's more like it converts the type that's associated with it。 And it's a little bit like， you know。

 in in C， if you have something like a。

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_82.png)

Enta equals 5， and then you say like char j equals char5。You aren't actually modifying the value。

 you're not actually like converting it in the literal sense that you're taking it and you're shifting it and you're changing what it is or whatever。

 you're just changing what it appears to be。And I think that's a really good way to think about standard move because standard move is not actually like like when I say changing it from an L value to R value。

 that's not like ripping it apart and doing anything structural， that's like。

That's telling the compiler that I want you to treat this L value like an R value， like hey compiler。

 as far as you're concerned， this is now an R value， okay。

 and when the compiler gets an R value in it will try and itll try and move it in this case because the double ammppaand refers to an R value。

 which is what we talk about more in week 8。Dvanche says after using standard moved does the original objects still exist。

 Okay， so let's come back to that question after we actually implement a move constructor。

 because I just want to stress again。Standard move does not move anything。

Things are only moved by the move constructor or the move assignment。

 like there what actually moves it just like the copy constructor and assignment。

 there what actually copies it。All we're doing here is telling who's calling it that I want you to treat this like an R value。

 so actually just telling it that I want this to be moved at this point。

 we're saying please call the move constructor。We're not actually moving anything。

But let's get into moving stuff， I might come back to those slides I glossed over。

Let's get back to moving stuff。Moving stuffs a lot like copying except we're not copying。

 though one really important thing you can read through this if you want， one really important thing。

Is that when you move objects from。When you move stuff from one object to another。

They should be in what we call a valid but unspecified state。Now。In essence。

What that means is that after you've moved data from object 1 to object 2。

Anyone who uses object one is dealing with undefined behavior。 It's totally not usable anymore。

 It's unspecified。 There is no expectation that it's used it doesn't have to work。

 it doesn't have to make sense。But it needs to be valid in the sense that like， you know。

You shouldn't just replace pointers with like， what's an example。 Val is in like it。

 it still functions。 It doesn't like crash or anything like that。 It's， it's a， it's an object that。

It's technicalecly valid， but you would never use it again。 Now。

 I know that might not make a lot of sense yet， but hopefully we can talk about that in sec。

 So if we're going to move objects， let's actually have a look at the move constructor。

 So we should be familiar with this type of slide because we've seen it before where we have our。

 you know these are our default things， but we need to override our move constructor because we're dealing with explicit memory。

 like keep memory。

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_84.png)

And what does this move constructed look like， Okay， well。

 I have my little move thingy there and then I initialize things。 and I've got the standard exchange。

 standard exchange， standard exchange。And then I go， okay， well， what's standard exchange。

 I might just， you know quickly Google that standard exchange。

 I'm be scared to Google STD things now， standard exchange says replaces the value of Oge the left hand side with new value and returns the old value of ob。

So it's basically like take new value， put it into Oge， and then return OB。Okay。

 so new value into that and then return what was there。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_86.png)

And this actually makes sense when you go back and look at the code here。

 because what it's saying is that。

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_88.png)

嗯。I mean， I think it's a little bit tricky， which is that we're saying that what standard exchange will do。

Is it we replace our。Allld objects， data with an null pointer。But then it will return， by the way。

 null point is just null and C plus plus we don't talk about that much these days。

 but like null point is just null null pointer lowercase is the same as null pointer caps just let's move past that for the moment。

 so it takes null pointer or null and it replaces the old objects data member with null pointer but standard exchange returns what was replaced that means that the new objects data gets populated。

With the return of this。So I just really want to maybe like make this very visual for you。

Which is that what happens here is that。We take null pointer and we put it in here。

And then we take what was in here and we return it to whoever called us。

So our old thing goes into the new thing and old point it goes into the old thing。

So it's a nifty little function that essentially allows us to move something。😊。

And its standard exchange will be used a lot with like move things。

 but what you also notice here is that we don't have to deal with any new and deletes or anything because we're moving。

 we're not creating new memory。We we're simply moving the values of it。 so if you go back to paint。

Bless old paint。If you go back to our old things in paint that we had here。Effectively。

 this one is the equivalent of like。嗯。You create your new data structure。Except so this is like MB2。

 the one we're moving to and then the new data structure is what points to that because we simply move the value so and then this old one here points to simply like null。

So you're just playing around with pointers there because moving isn't creating any more memory。

Because you're just moving something， you're copying or deleting， you're just shifting。

 So that's why we don't have to deal with any user deletes， though。Now。

 what happens to the original object？ That's a good question。 It's left in a valid。

 but unspecified state。And that valid but unspecified state is that it has no size， no capacity and。

The data object points to a null pointer。AndThat's valid C+ plus， but it might not make sense。

 it might undermine some preconditions， it might whatever it doesn't matter it。

It's technically valid，cause it。The values that the variable names make sense。 But like they。

 they work。 but it makes the the object useless。 So the point is a moved object。

 something that has been moved from is basically garbage at that point。So you don't need to like。

 be really smart and like add any flags or anything。 It's just， it just needs to。You know。

 just plug the hole， put some stuff there that's valid enough like it's it's valid values。

 but it's don't use it again。That's kind of how we feel about it。 Jin says。

 so you can still call member functions from the moved object。 Yes， you can。

 but it's undefined behaviour。 What is undefined behaviour， undefined behaviour。

 as we've talked about， is like saying int a or like saying。Autto V equals standard vector。Int12。

 and then saying standard the R D5。That is an example of unspecified behavior。 You can do it。

 You just shouldn't do it。 The same thing is true for like objects that we move from。

 You still can use it。 You just shouldn't because bad things might happen。

 It's the same as the subscript thing here。Sam Yang says when we call the default constructor for Invec or whatever。

 does that initialize the value to be0 or null pointer， I don't know。

 I'm not sure it doesn't really matter。Damud says， what's the point of moving。

 why not just use the original object？嗯。That's a good question。

I probably will have a better answer for you down the line。But。Yeah， I I。

 I don't have a great answer for you right now， but rest assured for the moment。 P sense says。

 what happens to M V， It still exists。 You can still use it Like you， you could still like。

You could still say like M V， I don't think we either haven't have any functions on it， but。

 you know， you could still。Do stuff with it here。 You just shouldn't。

 It's just like you can subscript a vector。 You just shouldn't， in some cases， In this case。

 you just shouldn't。 It's still totally usable。 It's not gone。 It's just。

 it's just undefined behavior if you touch it anymore。嗯。Okay， yeah。 that's one。 That's right。

 I have some notes from another week about this stuff， and I just didn't have them in front of me。

 but。Sillo says standard swap can make use of move to make it faster。

 like swapping to vectors as a use case for move。 Yeah that's a good example so。Like standard swap。

 which we saw。 Oh God。 standard swap， which we saw before。

 Like if you would implement standard swap just as like just a person and you had like a thing A and a thing B。

 How would you do it， You would make C， You would copy， construct A into C。

And then you would copy assign B into A， and then you would copy assign sign C into B， right。

 That's three copies to do a swap。But C++ is able to make use of a move constructor if you have it because it can just move A to C and then move B to A and then move C to B。

 and you haven't actually had to do any creation of new memory。

 just some like moving So thank you for that I was mental blanking for a sec。

That's an example of why we might want to use move constructors。 So standard swap itself。

 that's right， does use that。 And I think standard exchange also。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_90.png)

Might do that？Can't remember。 Sam Youngang says what I mean is after you create a default object。

 is that behave the same as an object that got removed。 I don't know。 It does it， it's unspecified。

 That's the thing， like。That like， that's why we say it's in an unspecified state。

 If it had to be like a default constructed thinging， we'd say that after an object is moved。

 it must be the same as a default constructed object。 but it's like， no， it could be like， like。

 if you just replace the 0 with like a two here， that would still be a valid but unspecified state。

 No one should move。 No one should touch it again。So it doesn't have to mean anything。

 this object means nothing after you've moved from it。嗯。And Daonche。

" stand a move will get rid of whatever is stored at the address of MV。I mean。

 I want to be careful with answering that because when you say get rid of what it means is that。

It takes all the values out。The dot is still there， it's still a stack object。

It just has crap in it now。So it's unusable。But it's not like on this very line here。

 it's freed suddenly or anything like that。 That's not the true。

Pyn says wouldn't setting data underscore to null pointer。Like this。

Cause Seg faults for subscripting。I'm gonna say this one more time。 It's like。Don't ask the question。

After I've moved it。But if I use it， why't something bad happen。

Because like we're saying that after you move it。It's not usable anymore。 You don't use it。

 It's like subscripting an array for a value that doesn't exist。 You just don't do it。

 Like that's you're a bad programmer if that happens， right， So it's like。There is no what if。

 like the what if is like whatever， Like， what if I do subscript， like。

 what if I have an array that I subscript。What might happen， Like。

 I don't know anything could happen。 It could be valid。 It could Seg fault。 It could give me 0。

 It could give me a big number。 like anything can happen。

 That's why it's defined as undefined behavior。 So it's the same thing with like setting data to an null pointer。

 you're essentially saying like like this object is in a valid but unspecified state。Oki dokey。

 move assignments the same。 I don't want to talk about that，cause it's。

It's pretty much the same you can read through that in your own time， you're all not children。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_92.png)

嗯。Okay， new slides。 I'm sorry that that formatting screwed up there。嗯。What do even is that？Oh， sorry。

Oh， wait。 No， no， no。I think I actually， I think we had these， and I deleted them。And I I mean。

 I wanted to delete them。Yeah， let's not worry about that。 sorry about that。

No wonder the formatting screwed up。 I missed that。

 So that's essentially how you you do your move assignment。

 So we've we've kind of touched on the rule of  five now， which is like copy， construct， copy。

 assign， move， construct， move assign and destructor。

 And the point again is that whenever you're dealing with heat memory directly。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_94.png)

When if you are creating heat memory， you need to think about these things because typically。

You know， not always you might need to deal with it now in this case。

I think you wouldn't have to make your own move constructor。

Because I think the compilers synsized one would be。Fine。I think it'd be fine。

 I can't see why we would need a new constructor， in this case。Because。Yeah。

 like we're just copying the pointers across。 So I think the compiler synthesize one should be fine。

 I mean， we could try that out。 I mean， I think even in this case。

 we're just using the compiler synthesize one。 I mean， if we got rid of this。

 the compiler would synthesize one for us。So we can see if that would work。Seem， I mean， it compiles。

 I don't know what it does。 We could try it out。 I mean， we don't have a。

Let's make all the data members public。Let's。Let's try printing out standard out M3。

tI'm breaking encapsulation here just for quick。Let's try and do that。Save this will work。0。

 And if I try and say MV dot data， I'm very terribly breaking encapsulation here this。

Throwing up in my own mouth。 Yeah， Okay， so we， we successfully moved it here。

 and you'll see like M V， M B is now in a valid but unspecified state。 So if I try and print out。

 say M V's thing， it's like， I don't know。 anything could happen。Print out 5， in this case。

I have no idea why。Oh， we do need move we do need a move constructor。 That's right。I was like。

 why is it 5， I thought we moved it， right， Like I thought we moved it， but。はい。Oh。

 it is using the copy constructor。 Hi， Nathaniel。Why is it using the copy constructor。Oh， yes。

 that's right so。There's a really important note here， which I just forgot。嗯。

Which I'm trying to remember where we wrote it。呃。It's somewhere in the slides。

 but essentially when you like with this rule of five here。

Once you start overriding any of these behaviors like a copy construct。

 you basically have to override all of them or explicitly default them。In these cases here。

 if you were to say just to a copy construct， but you still wanted the compiler to。诶。Actually。

 have the synthesized move constructors， you would essentially need to put these lines in explicitly。

So。Back one slide at the bottom， is it？

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_96.png)

I don't know。 That's okay。 So you would need to put these in explicitly。 So here。

 So I've got my copy constructor that I made， but if I want to tell the compiler no no just give me what give me what you think is best here and then I try and run that one。

Yeah， so。And this， this is kind of， I'm surprised as this is why I didn't crash before， but。

This is why we kind of have to be careful here， because。

What's happening in this move case here is that after it's moved。

I believe that the old one is still pointing to the same piece of memory。

So I'm not too sure why the move constructor。Would be doing that。 My guess is the move construct。

 My guess is， I mean， Nathan might know because he's in the chat here， but it's like。The。

 the compiler will just try and move these three values from the old object to the new object。

 like we've seen， I'm guessing perhaps for small types that it's。It it will just actually copy it。

 I'm not really sure if there's any efficiency in a compiler moving an int。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_98.png)

Move constructed doesn't change the old values。 Yeah， so in this case， it's just not even。

 it's not changing the old values， so。That's why we need to be careful here because as you can see。

 like this is why it printed up five twice because the new object。

 MV3 and the old moved from object MV both have the same data pointer to the same heap item and the default move constructor in this case is not actually like cleaning anything up it's not deleting this for us so the most critical line here in our move constructor。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_100.png)

Was this line here？This like novel pointo。Like， you could kind of get away by like not even。

By like not zeroing out the old size。Because largely that's not going to have any impact at all。

 it's not going to cause。Cause if your old object is not being used any more。

 then that's not going to cause any impact， depending on， I guess。

 how the destruct or whatever is defined。 So in this case， here。

 what you have to think about is like， even though our old myvec， the one we're moving from。

Is not being used anymore。It's still going to be destructed at some point when it goes out of scope。

 even if it's not used， it still gets destructed because it's just another stack resource。

 So let's make sure that it doesn't do anything silly。

Like called delete on that pointer that it used to have so this is why this is kind of why we say that once you deal with like he resources or once you start overriding some of these you really need to think about all of them and you really need to stop and think about all of them So someone's pointed out。

Yeah， okay， so。We talked about move assignment。 All of that。 We're coming up right at the end。

 The last couple of slides here are。As was just pointing out the， like。

This is just a summary again of like， if you have a class T。

 this is just the copy constructors and the move constructors。 it's just like。

 remember that you can like it's not just that the compiler will synthesize them if you don't define them and it's not just that you have to。

Make them yourself， but it's like if you don't define any of these you can actually tell the compilers this is a bit Kent for assignment too you can actually tell the compiler to just not have them so in this case if I did not have a move constructor or a move assignment and I'd say didn't have a destructor too。

And I just had this。 the compiler will synthesize these for you。

Consynthesize the copy constructor and the copy assignment。So if you want to tell it，No no no。

 I don't want you to synthesize it， just like we learned back in week three with constructors。

 you can tell the compiler，No， I don't want you to copy construct this， please don't。

And then that's what will happen here。 So now when we go to compile this。

The compiler will see that there's no operator to construct。Use of deleted function。

 I mean here it's it's even clearer to you as a programmer tells you exactly what's wrong。

 It's like no no no you made clear this is not something that we want to be that has a semantic associated with it。

 So please don't do that。 Now a bunch of text here at the end。 this is all just the details of it。

This is kind of what you might find useful for the assignment。

I think one thing that's important here I was looking for this line。

 I think I thought it was earlier in the slides， but if you define one of the rule of five。

 you should explicitly delete default or define all five。

That' that's essentially why we call it the rule of five here。

 So if the default behavior isn't sufficient for one of them。

 it's unlikely to be sufficient for all of them。 And we saw that today with like we needed our own destructor we needed our own copy semantics。

 therefore we need our own move semantics as well And when I say like semantics is essentially like the study of meaning So when I say like move semantics that's like that's saying what does moving mean So when we say we need to define our own move semantics We're saying we need to define what moving means。

Because we can't rely on the default meaning of what moving means， we need to give it a new meaning。

嗯。It's also even if， even if it is。嗯。Even if the synthesized one is sufficient。

 sometimes there's still good practice to。Simp write it in for other programmers to read it and make sense of it。

嗯。And then， yeah， the， the very last thing is that。I mean， we have like two minutes left。

 And normally， this would be like a whole。5 or 10 minutes in itself。

 But we actually talked about this so extensively at the start of the lecture that。

And we've spent so much time on this that I actually think this might make sense。

 but there's this concept called RAII or Re acquisition is initialization。

And the short summary of this is that it's good practice in C++ or I mean any language for that matter。

 that if you're ever creating a heap object， you should wrap that up。Inside a stack object。

 like we do with vector。 So think about what a vector is。

 a vector is a or my V or a standard onloaded set。 These are all stack objects that。

Acquire resources。 They create heat memory in their constructors and they remove the heat memory in their destructors。

 So that means that you are able to use standard vector without having to worry about what memory freed。

Because the actual。The actual resources， the actual heap objects are encapsulated inside these like stack objects。

 so therefore we're making use of the stack behavior。

 the scope lifetime of like you know we define it and then it destruct is called at the end of its scope and that handles all the mallaching and freeing for us so that's what we would refer to this concept as a best practice。

嗯。Yeah， so seven， just clicked over to8。We're going to be talking about smart pointers tomorrow。

 I don't think smart pointers are going to take up two hours。

 So if you have questions about this today， you can absolutely。



![](img/3efd6503c9c433ea94f3548f5a7cd7bd_102.png)

Ask them tomorrow。 We can keep talking about this topic tomorrow。 In fact。

 if you're a little bit confused about this today， you'll actually probably find talking about smart pointers tomorrow will help understand like。

Why this is relevant and how we can make this even simpler。Which will be very good。U。

And just for the sake of time， I've just send any other questions to the farm， but。

Thanks for coming tonight。 Let's keep chatting about this tomorrow night。

Please leave some feedback if you got your phone with you or whatever。

 I will put the URL on these in the future， but just snap it with your phone。 It's such a short form。

 Just like， click， click， click。 And thank you for coming again。

 Good luck with assignment 2 and how it's going。 We can also chat about that more tomorrow night if people。

😊。

![](img/3efd6503c9c433ea94f3548f5a7cd7bd_104.png)

Want to talk more about it， but anyway， thanks， everyone。

