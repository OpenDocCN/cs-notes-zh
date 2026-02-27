# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P6：-06-COMP6771 21T2 - 2.1 - STL Containers.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

🎼あの？🎼，🎼Oh。🎼，🎼Yeah。🎼The。Hi everyone， I didn't get a chance to。Fix up me webcam。Hello对。Okay， good。

 good evening。I see lots of people chatting in the chat about。

6 to 8 lectures and the lateness of lectures。 I mean， just as a fun fact for everyone。

So level six courses。A basically level 3，4 courses that allow postgrads to do it because one third of you are postgraduate students。

 and the university tries to。To schedule post grad lectures later， I think in general， I don't know。

 I have this in my hand， but。Yeah， so that's why it's kind of 6 to8。

 and that's why courses like security and staff are also 6 to8Beyond that lectures can generally preference times。

 I never feel like I have enough time for anything So Id never really preference itcause， you know。

 it's kind of just like， yeah。I'm sorry。Im just there on my desk。

 I was trying to pull out my my my USB was broken earlier and it got stuck in the port。

 so I had to like yank it out and here we are。😊，Okay， so hope everyone had a great week1。

 As I said in the notice， it was really good seeing everyone get stuck into it。

 I think one of the unique challenges of。😊，Here's the thing without getting off tangent。

I think one thing that separates a lot of computer scientists， in my opinion。

 from other people in other professions， is their level of patience relative。To other people。

 So I think， you know， first years are super impatient and like final years are super patient people。

 And I think computer scientists in general are like super more patient than others because the nature of what we do is like kind of miserable sometimes。

 you know， like it's not all just oh yeah， let's like， you know。

 let's just like be all happy and stuff。 It's like， oh。

 let's go look at something that doesn't work and we don't know why it doesn't work right and it can be really challenging sometimes。

 So。The blessing that we have is that we can most of the time fix things， you know。

 like nothing is worse than people who have to work with software。

 they can't even modify a lot of the time or have solutions to solve or have any way to solve it。

 But what's really cool is just seeing everyone kind of jump in and like figure out see make list and figure out what's happening with the assignment and try and try and。

Try and get everything working。 you all think you aren't patient， but you know。I think you are。

 I think you're probably more patient than you realize software has to instill in people a certain sense of patience。



![](img/290c3a372105c2e0532361e8593f92eb_1.png)

I'm sure some of you are just raving lunatics maybe， but you know， probably not。



![](img/290c3a372105c2e0532361e8593f92eb_3.png)

嗯。Week two， we are here to talk about containers。Or even broader than that。

 we're here to talk about S T L。 Now， S TL' is a really exciting topic because it's a pretty fundamental thing to C plus plus。

 It's also a it's also a part of。Like your assignment， which is really cool。

much too much light in my room。The reason that we're talking about this is because most C plus plus programs you write will consist of data structures and algorithms。

 right， Like that's what a lot of computing is。 It's， it's binary search， it's sorting algorithms。

 it's。Looping algorithms， trees and sets and hash maps and stuff。

 And some of you already dealt with those in the assignment， but。Unlike a language like C。

 there's a whole bunch of these software components that have been built for you and are actually baked into C plus plus。

 And as I said here， it's like，If you've done other courses beyond 1511。

 you've probably used libraries before， but libraries are a pretty critical part of most programming languages。

 most times you import something you are using a library in some way。

It's just that with a lot of other C courses you've done， you've actually been the library writer。

 you know。1，511，2521 if you've done those courses， you've actually had to write the graph。

 you've had to write the set or you've had to write the tree like you've had to do all of these things。

 but we're going to be using libraries that have already been written for us in C++ as part of the standard template library so in C++ we have this library called STL which stands for standard Tate library。

And it's basically an architecture and design philosophy for managing。

This is a very formal definition。For managing abstract collections of data with sorry for managing generic and abstract collections of data with algorithms。

 So what it is essentially in this diagram below kind of ticks at it is it's a collection of data structures。

 it's a collection of algorithms right so data structures being like trees and graphs and sets and lists and arrays。

Algorithms being， you know， searching and sorting and and and like looping and lambs and。

Removing and inserting like the whole shebang of actually manipulating the data structures。

 And then those two concepts are glued together with this notion of an iterator。 and iterators are。

Essentially。A way that containers like graphs and trees and lists and arrays provide like an API for algorithms to interact with them。

 And this is super exciting。 This is actually something I don't think you see much in other languages。

 So it's one thing I think C plus plus does really well because it actually allows you to plug and play with different types of algorithms and containers as as we will see。

U。And。As you can see written in the slides here， I think the two kind of summaries of that are that containers from a design perspective。

 the design philosophy of STL is such that containers should store data。

 but they shouldn't have to understand how algorithms will operate on them and algorithms should be able to manipulate data。

 but not have to know how containers are implemented。

 So it's very abstract type like abstract data type API style thing where you're trying to develop algorithms that just focus on the input like an interface and data structures that provide an interface。

 but that interface is broad enough and general enough that you can mix and match them。

 you know so like how can you use a search algorithm to look through a list or to look through an array or to look through a doubly linked list like all these different structures without having to manipulate your code。

 So a lot of nice general behavior。And we're going to kind of step through a whole bunch of code examples on this。



![](img/290c3a372105c2e0532361e8593f92eb_5.png)

The first thing we're doing。Is going to pull up。Let me just rearrange my windows really quick。Great。

I'm going to I've got the lecture slides three here。

 you can find it on Gitlab 677121 T2 lectures Every time a student tells me they don't know where the lecture code is。

 it's written up the top of the lecture page row here just in case you missed it so。



![](img/290c3a372105c2e0532361e8593f92eb_7.png)

嗯。I did a I'm going to do a get pull on that。

![](img/290c3a372105c2e0532361e8593f92eb_9.png)

Make sure that I have the latest code changes。And then I'm going to open it up in VS code。

Then we'll go through some examples， let me just close up all I was working on lectures for week three。

So we're going to go to the week two lectures。 Now， the first example we're dealing with here is。

AVk dash iter。File。Now。We've talked about iteration previously。 We kind of touch on it in week 2。

 We don't go into a lot of depth with it， but we do touch on it。

And what we touched on last week though， was that for a vector， this could be a vector。

 but I'm using an array here just just for a fun。We can loop through things in the C style with the counter and doing it less than the size。

 or we can use a full range loop。Whi we did here when we talked about references and stuff。

 there's a third option which I've slapped in the middle here， which we haven't talked about。

 but before we get there， let's actually talk about this data structure。

 So you know from last week that we could create an array in C plus plus of ints called ages and we could maybe populate it with some data。

Now， a vector， sorry。 Now， what actually is a vector。嗯。mean we'll talk about this in a sec。

 but a vector is a bit different from an array it's a dynamically sized array and what that means is that a vector underneath the hood is an array。

 but it does that whole kind of self resizing thing where if the vector gets too big it will resize itself and get bigger and bigger and bigger like that。

A STD array， which is a different data structure。 And you can see that instead of hash including vector。

 we actually hash include array， that is actually a C style array with a very lightweight abstraction in terms of it is a fixed amount of memory that you cannot exceed。

 And that's actually why when you're creating the array as part of the type parameters you're giving it you actually have to give it a size because a vector is dynamically size。

 So it doesn't care about like， it'll just make a decision as to how big it should be because underneath the hood。

Underneath the abstraction， it'll be， you know， it'll just set 10 elements。

 And then once you exceed that， it'll resize them and resize them and resize them。

 And you can actually see this， if you。

![](img/290c3a372105c2e0532361e8593f92eb_11.png)

Search up standard vector at CPP reference， and you go look at the pushback operator。

And you look at the time complexities of it。 you can actually see this here is it says aortized constant。

 So aortized constant essentially just means that if it's set up the data structure correctly。

 it doesn't。's， it's like immediately。How would you put it？It doesn't need to do any reallocation。

 so it's constant time because adding to a data to an array is like that， right。

 it's direct index lookup。And Jason says， so why do we need an array？ That's a great question， Jason。

I don't know off the top of my head。 my， my guess is that。So。

These are one of those million questions I don't know the answer to someone in the chat mind or Nathaniel probably does on the forum。

 Two things that would come to mind。 I mean， the reason you would choose an array。

 the reason it exists is because it would have some kind of performance benefit over a vector。

 right Like it just wouldn't exist otherwise the only things I can think about are that。

I just don't know what the performance benefit is， right， So with an array。

There might not be runtime checks like we could actually look this up like， I mean。

 we could Google it 2， I0' not going to spend the time Googling that now。It encapss fixed size。

It might use less memory， perhaps， because it's not。

Sttoring account or probably is storing account because it's got the app。 I'm not sure。

 Let's leap back to that one because it definitely would be storing something。

 but it would be something。 Some of you can Google it， and we can talk about it。



![](img/290c3a372105c2e0532361e8593f92eb_13.png)

I haven't personally used it。You know， a third of the things in this course I've never personally used for like a project outside of the course。

 I guess that's true for any course but。If we go back to VS code。🤢。



![](img/290c3a372105c2e0532361e8593f92eb_15.png)

An array is just a fixed size。 You can't。 You can't reallocate it， right。

 Like if you want a bigger array just like in C， you actually have to make it a new data type。

 Nn says a vector is primitive or reference type。So the way to think about variables in C++ is that everything is an object。

Just the best way to think about it， an in is an object， or this is an object。And yeah。

 when you create a type， it's an object。 And a reference is a separate thing。 though。

 like using other language， like vector is not in any way of primitive type。

 primitive types are typically types that the。Processor， I guess。

 I'm not really sure how you define it， but a primitive type is something that's not like an abstraction within the language itself。

 Like your CPU understands a double and it understands an end。 Your CPU doesn't get given a vector。

 a vector is an abstraction that helps you manage how to interact with the CPU。

 But without getting too lost on that， we have this array here with three elements in it。

 And if we want to print them out。 I've got three methods here， we can run， we can run this。嗯。

And we'll just do the same thing we've been doing previously。 build， Oh God it's so small。

 Someone told me how to update the confid that it appears to be。Does anyone remember the？Font size。

 not the editor， or is it d want the editor be smaller and then zoom everything in。 I don't know。

 Let's try that out。Maybe make that 16， and then we'll just make everything really big。Yeah。Great。

 all right， well that's a starting point。So I go to see a 67，7，1 slash lectures。

 I'm just making the terminal smaller， and then we'll go build slash lectures， slash lectures 2。

 slash demo 201。 There's our binary。 and we run it。 Now， you can see this prints out stuff on。

Multiple lines， I think we could probably get rid of these backslash ends。

Just so you can see things a little easier。We can run and build that one again。Thank you。

 I'll update that later。So we run that。And I forgot to put the space between them。

 But you get the point right。 I' say we've got 1819 and 20。

 and each of these three loops will print out those three things。 Now。

 we said we prefer the four range loop。 in generally。

 you should know that unless you're dealing with iterating that requires the index。

 But you'll actually see this other type here， which is super interesting， which is。呃。

Looping with this dot begin and dot end stuff now。What is actually happening here。 And again。

 you might know this from Java stuff， but。When you're iterating。

Like in Java there's a concept of an iterator， and we're going to talk about iterators more in the next lecture。

 but essentially an iterator is an abstract pointer to somewhere in the array。

 So if you have some kind of data structure。

![](img/290c3a372105c2e0532361e8593f92eb_17.png)

Where you have all these like squares， like a vector or something。Then。

What is happening when you say Im going to get the beginning of that vector。

Is its returning an iterator， and that iterator is basically a pointer effectively。

To the first element。And then just like an iterator in other languages。

 when you plus plus that iterator。It like a counter， then just magically moves on to the next one。

And then it moves on to the next one， and then it moves on to the next one。Like that。



![](img/290c3a372105c2e0532361e8593f92eb_19.png)

嗯。So that's actually what's happening here。 And with iterators， there are two concepts。 Again。

 we're going to loop back to this。 It's just really simple to start。 I you have the beginning of a。

Data structure。 and you have the end of a data structure。 And essentially。

 this loop is saying I'm going to create an iterator that points to the beginning。

 We're going to go while it's not at the end。And then we're going to increment it each time。

So it'll keep moving across it。 And this is actually getting into that S TL topic where we're talking about iterators and we're trying to understand。

What iterators like we're trying to understand how algorithms use them。

 So we're not actually using an algorithm here for the data structure， right。

 an array is a container， and we're using the iterator on that container。

 where we're not actually passing it through an algorithm。 So the benefit of this is quite low here。

 We're mainly just。Demonstrating now， Pin when asked， what does the type of dot begin， Again。

 the great thing about CPP reference honestly is that。



![](img/290c3a372105c2e0532361e8593f92eb_21.png)

It's really well documented。I can go to standard array。

 pretty much anything you can do in C++ is written here， I'll find my begin。

And then it'll tell me it。诶。Returns an iterator type。

 And you could go down this rabbit hole if you want。

 because I know iterator would be defined here somewhere。 and like an iterator is a。



![](img/290c3a372105c2e0532361e8593f92eb_23.png)

Legacy Random access Acerator， which is like a you know， you can get lost in here。

 I'm not saying there' straightforward answers， but there are answers。嗯。呃。

Girt says why don't we have autoconst it， That's a good question so why don't we have autocont it Well。

 because an iterator is an actual object that you do modify。 It's like a pointer。

 it's like a counter。 It's the same reason you don't have an unsigned int const because you want to actually modify that thing。

So we will again come back to iters a bit more。Oover over order to see the type。Hello。

It's not working。Again， we're going to talk about iterated， Sir。

I'm not going to answer every question yet， I'm simply trying to show you that there is this concept of an iterator that we can use to loop through something which will'll keep coming back to so you can loop through things without index access and without four range loops。

You can actually do it quite directly。

![](img/290c3a372105c2e0532361e8593f92eb_25.png)

But don't worry， your questions will be answered， I promise。



![](img/290c3a372105c2e0532361e8593f92eb_27.png)

There are5。 I mean， there's more than this， but there are many different types of containers。

That we have in the course。 So we're going， we're going to look through the different types of containers。

 and then we'll come back to the usages of those containers， so。In the set of containers。

 there are sequential containers， ordered containers and other things like that， but。

There's kind of five key sequential containers that are built into STL。

 So STL is again a set of library it's a library or yes。

 a set of libraries and containers are a big part of that library and these are the sequential containers。

 So sequential containers are essentially data structures。

That organize a finite set of objects into a strict linear arrangement。

 So they're ordered and they're linearized in some way。 So well sorry， they're not ordered。

 That's the wrong word。 They are linear。 So if you think about structures that you've dealt with like。

Ss and hash maps and stuff。 they're not ordered。 In fact， if you've been working on the assignment。

 you know that there is a thing called an unordered set。 And you know。

 from other programming languages， if you've done like a Python course or something that if you try and print out a dictionary。

Then it doesn't always print it in the same order because the dictionary itself does not order anything。

 So sequential containers have a sense of ordering。 Now。

 there are five key ones we're looking at here。 We have a standarded vector。

 which is a dynamically sized array。 So it is literally an array data structure。

 It's just itss resized。 ands we can look at this on TPP reference。

 It'll give us a tell tell what it is。 the elements are stored contiguously。

 That means like as an array。

![](img/290c3a372105c2e0532361e8593f92eb_29.png)

Which means that elements can be accessed not only through iterators。

 but using offsets to regular pointers， basically it's saying it's like it's a sea style array underneath。

 which means really， really quick lookup。The storage of a vector is handle automatically。

 it expands and it contracts as needed。 And you can actually see this here because it says that。

It has this notion of a capacity。 So capacity and a vector。

 it returns the number of elements that the container currently has allocated for。

 So we could actually play with this if we want to here。



![](img/290c3a372105c2e0532361e8593f92eb_31.png)

I'm I comment out this code quickly and we can just look at it together。

 I could say auto vehicle standard vector of ins。And it will have a one， two， and a three unit it。

And then I could stand at the B dot size like this。Now I have to hash include vector to here。

I should include these alphabetically just for。嗯。OCD reasons， I guess。

 now I'm going to build that and I'm going to run it。

So my code builds and I run it and it says the size is three because there are three elements in it。

 but if I then take this and I print out the capacity，We're going to get a different number。

I think it's 10， I don't know。It3， okayright。 Maybe it's not3。 Maybe it's。Maybe。

 maybe the first one is like spot on。 I'm not too sure I'm not familiar with the internal workings of it。

 But what the capacity is is it's the total。Well， maybe it's after we remove something。

 I think that might be it。 We could go and read about this。

 but capacity is essentially the amount of allocated memory that we can be queried with it， right。

 so。Vectctors usually occupy more space than static arrays because more memory is allocated in future to handle growth。

 So rather than like have four。And then， you know， it has five and then six and then seven and then eight and then nine。

 and like every time we do that， having to reallocate， it'll actually do it。Like in chunks。

 like it'll maybe create space for 10 and it'll wait till that 10s filled up and then it'll double in 20 and similarly。

 So I really like Fison's suggestion about we should really push back to the array to the vector。

 which I agree with。 Let's try that。So we can understand how it works。

 So I'm just going to copy this line here。 and then I'm going to do V dot pushback。

 Let's add something to it。 Let's just add 5 to it and see what happens。

 So what this means is that because the vector capacity is4 to start。

 it's going to have to resize the array because it needs more space。

And you can see what it's actually done here is when it's resized that it's just doubled it because rather than resize it to five and then again and again and again。

 it's just set up， we'll just double it。

![](img/290c3a372105c2e0532361e8593f92eb_33.png)

And then done。 And then you can see here。 Let's see what happens when I。Delete from vector。

 So how do I delete from a vector， Will we go， we go and look at the。what are we got。

 What things do we have， erase， erases elements。So this is using iterators。

 which I don't want to get into yet。So you probably won't be able to。Do much with that yet。

 which is fine。 We can come back to that example becauseuse we can tie that into iterators。



![](img/290c3a372105c2e0532361e8593f92eb_35.png)

So vector is an array that's dynamically sized。 I that popback。 Did I just miss that。



![](img/290c3a372105c2e0532361e8593f92eb_37.png)

Oh， I did。 Thank you。 Sorry。 Thank you， everyone。 I was like， I was swear there was something。

 I thought I was going crazy。 thought I was going crazy。 Thank you so much。

 So let's pop back two elements。😊，Say what happens。I was like。

 I'm pretty sure you could change this anything't think you needederators。So you go。

 it's still eight。So you can see that in this case， like I mean。This is one。There go。

 So it it's not it's not making it any smaller。 I don't know what the particular algorithm is。

 but it would， in that case， it would probably be like what's the point of downsizing that。

 It's 8 bytes。 I just don't know what it is off the top of my head。 I didn't write the library。

 So but the point is you can see we have this notion of a capacity。

 And then we also have this thing reserve here and you can go look through the library increase the capacity。

 So， for instance， you've seen that it actually doubles right So if I push back like5 and then I do this like a bunch of times。

 and then I build it and then run it。You'll see that the capacity has jumped from 8 to its now 16。

 So it's actually had to do two reallocs at this point。 It's had to go from 4 to 8 to 16 like this。

 Whereas if I was to instead say V dot reserve， which I think you give it a what type does it take。



![](img/290c3a372105c2e0532361e8593f92eb_39.png)

A size type。 Yeah， I thought it'd take a size type。

 So it's essentially saying like how many units of the type。Do I want， And I could just say 16。

So now immediately， it could get constructed with four elements。 I could resize at once to 16。

 which is only one allocation of memory reallocation。 And now when I build it。

It will be finitely faster because it's done one reallocation instead of two。

 So these data structures have very powerful APIs that you can use to modify them。嗯。Yeah。

 and Ryan says， does the compiler look ahead to see that no more is added so it doesn't bother decreasing the size？

No， it， it doesn't。 It could， though， I guess。But okay， so firstly， it probably could theoretically。

 I don't think it does。 That's what a stand like， that's what a compiler time optimization is it。

 it looks at。Patterns of behavior and tries to make optimizations。

 The reason though I doubt that it would ever be implemented is because most of the variability in。

vectorctor additions would probably come from user input。Like。Most programs。

 if they're not relying on some kind of unknown input， could just be compiled to the result。

Immediately， right， Like， if you write a program that just。

Calculates an nine factorial it doesn't need to compile into a program。

 it could just compile into a number。嗯。So it's probably why it doesn't look ahead because it's not really able to。

Pson， will throw an error if you reserve to something smaller， Probably， I mean， again。

 you could just look at the docks for a lot of this stuff， right， like reserve。



![](img/290c3a372105c2e0532361e8593f92eb_41.png)

嗯。New capacity of the V honor would let you do a smaller one。嗯。

But it says if new cap is greater than capacity。Otherwise， the method does nothing。

 so I don't even think it would let you minimize it。I don't know。

 but I'm not going to get lost in too many rabbit holes。Yeah， Charlie says。

 why does the capacity jump to8 when you add something into the vector because it needs more space and if it went to5。

 it thinks you might add 6 soon， so why not just jump to 8， save on a whole bunch of reallocations。



![](img/290c3a372105c2e0532361e8593f92eb_43.png)

![](img/290c3a372105c2e0532361e8593f92eb_44.png)

So that was a fun little deep dive because I hope that demonstrated to you how these things are abstractions。

 right， So a vector is a， is it an actual， you know， it has an array underneath。

 but they're also lightweight abstractions。

![](img/290c3a372105c2e0532361e8593f92eb_46.png)

For instance， I'll show you another thing in C plus plus is that。

Which we will talk about later in the course again， but if I try and stand at CR V0。

This will give me a number， as you'd expected to， because I printed out the0 with index。

 which gives me a one。 That's my one here。 But if I print out。 and if I do V dot at 0。

 this does the same thing。So the V dot Act gives me the value of a particular index。

So it's like what's the difference between these two Well I'll show you the difference watch what happens when I try and do v of4。

 which I need to remind you is the0，1，23，4 fifth element， right？Which doesn't exist when I do this。

 the program will throw an error and crash， its says aborted because it's thrown at uncot exception。

So the actual library itself， checked。How many elements were in the array in the underlying array。

 It found out there is no fifth element， and it threw an exception。 And again。

 the assumed knowledge in this course is that you are familiar with exceptions。

 But if I do something like this。The index for。I'll show you what happens。We get a massive。

Think it's a heap buffer overflow。 And hell， if I make this some crazy number like 400。

 the point is this， this does not， this does not fail gracefully in this case。

 These are heap overflows is basically the equivalent of a seg fault。 I think。

 I think because we're in debug mode， it's probably。嗯。Putting debug symbols in。

 Let me go to release mode and try building this again。 So release mode。

 like think of debug mode like it builds with GDP every time。 And therefore it's really slow。

 whereas like if I go to release mode， it does something even worse。 it succeeds right。

 and this is like a common trope of programming。 If your program is F， you want it to break。

 This is the worst thing that can happen。 your program has this is what when we get into logic errors right。

 So this program has succeeded because we've tried to look this up and we've somehow hit valid memory。

 So again， C plus plus what do we say at the start。

 it aims to provide lightweight abstractions and lightweight abstraction。😊。

Ligh weight abstractions mean getting out of your way if you don't need it。

 So like sometimes you might not need to check the index is right。Right， you might not need to。

Do bounce checking because， you know， for some reason that it's valid。

 So C plus plus allows you to not do bounce checking， right， So there's the power of it。

 But if you want to do bounce checking， the vector also has an app inside of it that you can use to check stuff。

And again， this is all written in the documentation。



![](img/290c3a372105c2e0532361e8593f92eb_48.png)

Because you'll see it here， we have our app。We have our operator brackets。

 no bounce checkings performed with bounces checking， like it's all in the docks， really good docks。



![](img/290c3a372105c2e0532361e8593f92eb_50.png)

And yes， that's undefined behavior。So。Surus says， so in C++ we don't have to write structures to define known data structures that correct。

 Yes， and also these are going to be written better than anything you can write， frankly。

 or I can write definitely。So that's why we use them。 We have a standard array。

 which is a fixed size array。 Someone answered before about that arrays are useful to really communicate to someone that it's a fixed size。

 I think that's a good point too because it's like if you have a if you want to use a vector with 10 elements exactly no more no less。

 you could put comments there， but using a standard array can even communicate that clearer to someone the other thing is that vector sizes aren't known。

😊，Compile time because they can be theoretically bigger and arrays are known at compile time。

 so the compiler will actually know how big your array is going to be。 so forever。

 so there's probably some optimizations there that could be made I'm again not sure。We have a DQ。

 which is a double ended queue。 I'm not sure how these are implemented。呃。

If they're not stored contiguously， which I think means it's not using an array， it's probably using。

Some kind of。Pointer some sort like linkless saw thing。I don't know。

 Probably not because random access is01 so。That wouldn't make sense。

 I don't know how something could be a linkuist with that。 It just says it's not still contiguously。

 So potentially， it's。I just don't know honestly I don't look at this one much so I don't have a lot of good answers for you and you could read up on it again my job here is not to read documentation for you for a couple hours and then we have our standard forward list and our standard list so a standard list is a wubly link list I think the reason that standard list is a w link list is because w link lists are really powerful and they don't use that much more storage so。

嗯。Yeah， so you have a forward list， which is a singlely linked list and you have a standard list。

Yeah， I'm not sure you guys should Google it like every。

 every year I learn a lot more about this language。 and then I there's just more and more questions。

 and there's just never， never ends。

![](img/290c3a372105c2e0532361e8593f92eb_52.png)

Just the next section in the stock。What do you mean in the next section。

 Someone says it's really close。 Did I just skip over it。ち。Hash。I don't know。Table dinner， anyway。



![](img/290c3a372105c2e0532361e8593f92eb_54.png)

Something。嗯。Oh， typical。Okay， sorry， there we go。 Tiff implementation uses a sequence of individually allocated fixed size arrays。

 Yeah， okay， that makes sense， Like I was wonderingcause like if it's not contiguous。

 but it has random access， then it has to be a collection of arrays。 So that's good to know。

 It was written right there。 I just can't read。 There you go。 So in terms of sequential containers。

 these are all the ones where things are stored linearly。

 I should have also like probably realize that given that title。😊，嗯。

And we have actually kind of looked through vector a bit。 I kind of jumped ahead on this stuff。

 so I don't think we really need to talk about this code example because we've talked about at in capacity and we've already done four loops and stuff。

 but this is just essentially demonstrating what we've just been talking about with vector。



![](img/290c3a372105c2e0532361e8593f92eb_56.png)

![](img/290c3a372105c2e0532361e8593f92eb_57.png)

嗯。We have another two types of containers， which are。 so this is three types。 This is a second type。

 and it's an ordered associative container so。When something is an associative container。Typically。

It's some kind of。Hash structure。Because。Like not always。

 but like you want to think about it like it' like a dictionary or an object or something where you have a key value。

Structure， essentially， so most sequential containers are a collection of objects。

 Maybe those objects are pairs and tus or strs or something， but。

As far as the container is concerned， it's a collection of single atomic objects。

For audit associative containers though it's a。Typically a key pair style structure。

 but often it's only like the keys are the only necessary part of it。

 So the ones you might be familiar with are sets and maps now。Really here， even though there's four。

 there's actually only two because we have a set， which is a collection of keys。

 which is basically keys without values。 So sets are how you typically just keep track of values in an Associative fashion。

 so they're not stored in arrays it essentially like a big pool of stuff。😊，嗯。

Often they'll be implemented as hashes of some sort。And then you have maps。

 which are key value pairs which you probably already figured out from the assignment。

 is that collection of like， you know， okay， have this key maps to that， you know you know。

 collecting names and ages or names and driver's license numbers， it's how you associate。

1 value to another。 And then you have multi sets and multi mapps。

 which themselves are just where you can have duplicates， because sets and maps by default。

 which honestly， I use 99% of the time。 I've never had a reason to use a multiet multimap sets and maps by default。

 You can't have duplicate keys， which is one thing that makes them really useful。

 So this is the multi set docs and。I was hoping there might be like a handy little example here。But。

That doesn't really matter。Nope。But again we've kind of look at these。

 I've already got an example here anyway， so it doesn't really matter but。



![](img/290c3a372105c2e0532361e8593f92eb_59.png)

Let's have a look at this one in VS code。

![](img/290c3a372105c2e0532361e8593f92eb_61.png)

啊。So let's see this here。What I'm doing here is I'm working with a map and。

Because a map's an associative container， that has。Keys linking to values， right， So A links to B。

 It means that the generic types that it needs are two。 So we need to give it a key and a value。

 And in this case。The the key is a string， and the value is a。A number。 And here we're saying that。

 you know， we're storing looks like names to numbers， not really sure what these are for。

 Let's just pretend it's the weight of。Things， the weight of a bat or something。

 And you can see that we're making a map， which is just。嗯。Clled M。 Now， remember that the。

 the modern C plus plus style that we're asking you all to use is instead of doing a definition like this。

 we actually want you to use a definition like this。

 And I think Nathan's touched on this on the forum。 And our code examples just。

So our lecture code examples show different ways of doing this because we want to demonstrate to you that there are different ways of doing it because lots of C++ you see around the internet will have this kind of style of things though we encourage you to use this approach because this essentially it makes your code a lot more consistent because it basically means that every time you declare and define a variable that auto is always on the left so it like follows a very similar pattern which is you know auto variable name equals type and then the constructor here。

We'll come back to that even more next week， but in the meantime。

 just remember anytime you see something like this where it's type variable name。

 we often want it to be auto variable name equals type。嗯。So you're creating a map called M。

 demo creating a pair。Now， a pair， if we look that up。I don't want to Google Pecause， you know。

 what am I going to get， probably some fruit。Oh， that's cute。Little birdies。Okay。Well。

 that was weird。Standard pair。嗯。A standard pair is essentially think of it like a map except。 Well。

 it's not really like a map。 My point is that it's just a collection of two types。

Now you can see that pair is defined in the utility library， but because maps are made up of pairs。

 like that's all a map really is right， it's a collection of like key value pairs。

 the actual map library itself will have included pair as well so that's why we don't need to include it here to make it to make it work。

😊，呃。So we have a standard pair of this and then we want to insert it into our map。

 so at this point we create a map of M， we create a pair which is like a little coupling of things ready to be slapped into a map。

 and then we insert it into the map。You can also insert things directly into the map like this。 Now。

 this， this doesn't really fit into a language convention because it doesn't really make sense。

 Like what the hell is that， like。It's braces and a comma， okay， but the compiler is actually。

Will actually automatically take that， and it will turn it into a standard pair。

 and then it will insert it for you。 So this is kind of like a shortcut way to do the above。

But the preferred way of doing it because it's a lot clearer， in my opinion。

 is to actually use the in place。In place function。 So here you go to the standard maps。API。

 you'll see that they have a whole bunch of modifiers， which will include insert。

Which you'll see here we' say inserts elements since the++ 17， and then you have in place。

Which constructs elements in place。So I'll also tell you why this one's better。



![](img/290c3a372105c2e0532361e8593f92eb_63.png)

嗯。The reason I like this one is because I think it's。I think it's a bit clearer。2。

My microphone just came out。嗯。One sec。ok给。被告人人。Jesus。There we go。

 I like this one because it's kind of clear that it's like just， it's。

 it's a function call that takes into arguments as opposed to a function call that takes in its squiggly little collection of things。

 But I think the other reason this is preferred is because what this one actually does is that it。



![](img/290c3a372105c2e0532361e8593f92eb_65.png)

And bear with me here， because I。

![](img/290c3a372105c2e0532361e8593f92eb_67.png)

I haven't double checked this， triple checked it， sorry。What insert does。

Is I think insert takes the value， and then。Coopies it sometimes。 And if， if， if this is not true。

 I mean， this is not a big detail， but this is an example of something that actually happens a lot in C plus plus。

Is that I think it might copy it， whereas in place， we'll actually construct it inside。

 So it's constructed in place。 And I think what that means is that。Insert will。

Like doing this via insert， you have to take the two variables。

 construct it into a pair and then copy that pair in and have it recreated in the structure right so there's that extra step of like taking values。

 constructing a pair， copying that pair in whereas in place willll actually just take the two values and construct it straight into the data structure and in that way I think it has a finite。

Improvement on time。Like as in it's a little bit faster。So。You can see here that。

Someone is also trying to print out the value at a given key right because maps are just key value pairs we have written here this is very dangerous and one of the most common causes of mistakes in C+ yeah so generally I've got all these tabs open here I'm sorry probably all over the place but generally speaking if you are trying to look up the value of something in a map you want to use the lookup to find it now in next lecture I think is when we talk about how to look things up in these structures using iterators。

 but generally speaking you would rather use the find method rather than trying to look things up directly or you use dot in this case as well just like just like a vector has So just answer a couple of questions that have come up on this example Matthew says when declaring container without contents is there a difference between braces and brackets So short answer is no longer answer a little bit but we're talking about that in week3 but for now the answer is just。



![](img/290c3a372105c2e0532361e8593f92eb_69.png)

I can easy know。Easy， easy， now。嗯。AndYep， Charlie says。

 is it accurate to say that a map is an array of pes and someone's already answered that because it's not really an array？

It's these things are often stored as。Hashs or something like that。Which means that they're。

They're not contiguous in memory， like that's the thing about an array。

 it's all a block of memory together。嗯。So。

![](img/290c3a372105c2e0532361e8593f92eb_71.png)

That's audit Associ arrays。 Now the keys are actually sorted here。

 I don't quite know off the top of my head。How they're sorted。But they are certainly sorted。嗯。Yeah。

 so。They're sorted in the sense that。When you print these out， like in this code example here。

They will print out in in an actual order that is predictable。 And like we can try this here。

 for instance， like if I， maybe if I try and insert like bat and cat dot， I think let me try this。

Sorry， my throat's just gone。That's the wrong code example。Yeah so。

You can see here that the actual keys themselves are ordered， so when I try and print it out。

He printed out bat cat dot even though I added bat dot cat。And。

That's why you use a map if you care about the keys being ordered。

 So if you don't care about the keys being ordered， use the next type of data structures。

 but if you do care about them being ordered， then the map structure will be very efficient。But yes。

 this is dangerous just for the same reason it is with a vector。

No bounce check look up you're basically。You're basically just saying like， you know。

 I am so certain it's there that I'm going to ask no one to check it and if I get it wrong。

 we get into the undefined behavior territory and undefined behavior is really dangerous because anything can happen。

 undefined behavior can make your program work 100 times and then fail 100 and first time which makes it super dangerous。

Okay。They have a good time。 they' run， they' run good， they run good， happy， chilling。

1undred and19 people watching。It's good。 It's about a quarter of you。Oki。

 the last type is unordered associative containers。😊。

There's not a lot of explanation that's needed here because。Unordered sets。

 unordered maps are like sets and maps that just don't have a sense of order。

 that means you can't just say to it like if you say to it give me all the keys。

 it might be able to give you a list of keys， you might be able to iterate over it in certain libraries but it's not ordered。

And if you do get an order， it's just because that's how it happened to。be printed out to you， right。

 So there's no real order。 it might just appear to be in order。Now there might be the question。

 why do we want to use these if there's no order and the answer is because they are very very fast and I know this because these libraries were introduced in C++ 11 and the two years I spent writing code for Robo Cup。

 one of those years was a lot of C++。😊，There sure was no。

 We were using C plus plus 98 on the robots at the time。 So we couldn't even use these。

 So we actually had to use C style。We had to like write sea styleyle hash maps， essentially。

 because if you go and look at our maps， right， here's the thing about map。 when you want to get a。



![](img/290c3a372105c2e0532361e8593f92eb_73.png)

A value。So for instance， find or you want to find something。嗯。

It's logarithmic now I don't have the head space right now to remember why that's logarithmmic。

 it probably implies that it's stored as a tree。It probably is a tree。

That would make sense if it's an ordered set。So I'm going to just guess it's a tree。It's logarithmic。

 which means that it has to go through the entire structure right and like go down through the tree to be like。

 oh， there it is So it's actually probably not using hashes to store this here。

 right It's just going to be using it as a tree。And。

That means that look up is log n Now login is still very quick。

 right log n is like for a balanced tree， a million items is only 2020 levels to go down。

 so you know massive massive improvements at scale。

 but it's not instant So if you're dealing with huge huge quantities or unbalanced trees and everything like this then it's not that slow。

Not that quick， sorry。Now。Where an unordered set differs。

 is that an unordered set or an unordered map， an unordered map is super powerful。

 is that I'm pretty sure it's definitely a hash structure where essentially you take like what happens is you hash the key。

And then that hash tells you where to find the value。 And there's sometimes collisions in that。

 but generally not， which means that when someone gives you a key。

 you can tell if it's in the map immediately by hashing it。

 which is generally considered a constant time operation。 and then it tells you immediately。

 So there's no traversing。 There's no traversing arrays。 There's no traversing trees。

 It's just traversing。 It's just looking up the hash directly because we're using hashes。

 there's no sense of order。 you can't you can't really store a hash style structure with a sense of order without adding more overhead。

And again， the point is C+ pluses to provide lightweight abstraction， so unaudered maps。

 unordered sets， perfect things if you're trying to look up really quick because it's Contantine lookup。

嗯。Yeah。Someone has said。Isn't it crazy that it took C++ 20 to include a dot contains method？

That's true。 Let's see what these differences， because I look at this。 I haven't used dot contains。

 but it's like at will actually get you the value。 returnsturns a reference to the mapped value。

 So you give it a key。 And if the value is there it。Returns you a reference to that value。

 And you can see if it's not there。 it actually throws a standard out of range exception。

 We talk about exceptions in week。four。But since C plus plus 20， they've added a new method。

 which is contains which returns a bull。 So basically someone like you can imagine how annoying it would be to use an unordered map。

 And like if you want to figure out if something's in there， you have to do like a try catch。

 see if an exceptions thrown， which is just like a pain right， It's just more code。

 potentially more confusion as opposed to a nice little like dot contains method。

You'd want find not at。呃。I actually don't know what the difference between can Oh， okay so。

I don't know the difference between contains and。Find is。Because find， I guess。

 would give you the element。Oh， yes， if find would give you the element。

 I guess containss would just tell you if it's there。 That's an easy answer。

 So if you actually need the value of it， then you would probably use at。

 I think returns the element。 It'll tell us at returns T ampersso。 So to read these docs as well。

 standard it unordered map。It actually has all this other crap here， but you can ignore that。

 It's basically like you create an unored map。 It has a key and it has a value。 That's what T is。

 So this is saying that the at function in the map returns you a reference to T a value。

 So at and find are kind of the same thing one's an iterator one's just the reference， but。😊，嗯。Yeah。

 it generally contains iss just different to that。Okay。



![](img/290c3a372105c2e0532361e8593f92eb_75.png)

Spending a lot of time on the docks today， which I think is kind of fun。Because you know。

 we get to learn a little bit about how to interpret things， which I think is super useful。 So y。

 these these unordered structures are a ridiculously fast for lookup。Foster Tra， that's all they for。

Okay， and last thing before we take a break and then we start talking about iterators is container performance。

 So now we've been talking about these as we go through them。 But the point is that。嗯。

just like you would have learned in data structures and algorithms。

Every container has compromises on performance and choosing the right container all depends on what you're doing。

 generally speaking。You can get very， very， very far with vectors and unordered maps like you could do。

 I'd say 90% of things you want to with just that because one of them is a contiguous starter structure with instant like look up an addition and it's audit and then maps are like real like。

You know， past retrieval and stuff like that。 But it's important that you remember that all of them do have different。

Structures， so for instance， if you look at a list here， which you know is a Doubly linked list。

Look at all of its erase， insert， popback， pushback， pop front， all of these things。

 which are the modifications。 They're all hugely fast， whereas you know， getting the size of it。

Equality here。Probably even some lookups as well， which isn't referenced here。 They're quite slow。

 right， That's the nature link list。Yeahep， so。啊。Yeah， that's that's kind of the big difference。

And the other thing just lost reminder， I guess， is that。

A lot of data structures are do amortization stuff， too。 Like。

 that's why you'll see things like amortized， like what， what did the。



![](img/290c3a372105c2e0532361e8593f92eb_77.png)

Like anytime you see a data structure， say， where's me vector？

Are we got to go up on containers library vector。Yeah。

 I'm surprised the list doesn't store the size as well。 Let's actually look at the list。

Did the list have a Did the list have a。Plus， no， it didn't。 That's okay。 Yeah， So like list。

 if you wantan to get the size of the list， it'll tell you the complexity is。Now constant。

 So I think this table is probably outdated now， even a constant all linear。 So， yeah。

 since C plus plus 11， it's constant。 to be honest with you， this is actually one of the oldest。



![](img/290c3a372105c2e0532361e8593f92eb_79.png)

Screenshot of the this is。 So this course was originally created on another slide deck that I copied from the version of a course that I did as an undergrad a long。

 long time ago。 And we threw out most of it。 But this is one thing we kept because I thought it was a cool table。

 But as you can see， this is actually， this table was actually。When C plus plus 11 was released。

 So it's probably referring to like just before then。

 So that's another example of why US C plus plus features are better。

 I was a bit dubious at that because I had the same question you did fire in when I was like， oh。

 it seems a bit weird that it wouldn't be constant time。 But yeah， again。

 if you look at things like pushback， you'll see this phrase， aortized constant， which again。

 just kind of means that so amortization， amortized analysis or amortization analysis I can't remember is basically just trying to look at the complexity of something over a broad thing which which。



![](img/290c3a372105c2e0532361e8593f92eb_81.png)

Ignores like these little one off。 So it's like if you try and add a million numbers right to a vector。

 it's going to resize it 20 times。So when you look at that， you want to take you know。

 instead of like when you have eight items and you insert one。

 you wouldn't want to look at the complexity of that because that would be a reallocation plus an insertion。

You'd want to look at like， okay， well a million items。

 20 reallocations in the context of a million items is kind of we like aortize that out so it's like you know。

These， these like preemptive and structural changes are just like we just kind of ignore them。

 but we note that it's like it's constant time if you'reortized out there。

The bigger things that happen。 Anyway， let's take a five or so minute break。 We get started around。7。

10。But before we do， because we've just finished this one。

 I would also like to take the opportunity to ask you all to fill out the survey for this lecture。

 So this is ST TL containers。 I'll probably start putting these in the slides instead。

 because otherwise I'm gonna forget， so。Grab your phone， recording， live stream， snapap it quick。

Be like， yep， give it a number。 I don't care about the feedback。 I mean， the feedback matters to me。

 I guess if you have something to say。 but like the biggest one is just the numberca what what I typically will do is like at the end of the course。

 I'll。Go through all like I'll find like the top 15， top 10， whatever worst lectures。

 and then I'll figure out what was wrong with them so anyway。Cool， well， yeah。

 thanks for filling that out。 And let's take a break and I'll get back to it after the break。



![](img/290c3a372105c2e0532361e8593f92eb_83.png)