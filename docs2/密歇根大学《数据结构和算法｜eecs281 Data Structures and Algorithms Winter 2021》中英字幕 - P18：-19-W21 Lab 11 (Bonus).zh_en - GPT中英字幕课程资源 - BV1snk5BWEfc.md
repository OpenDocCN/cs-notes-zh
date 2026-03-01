# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P18：-19-W21 Lab 11 (Bonus).zh_en - GPT中英字幕课程资源 - BV1snk5BWEfc

![](img/b6f0a9a3f69d3fac7aabea69ad948eb8_0.png)

Cool， did that start the recording， somebody confirm that I've never actually done this before。Sweet。

Okay， so a few things before we start first， congratulations on making it through each 21。

 This is by no means an easy class。 And I think you guys have all。😊。

Showone some great skill by just making it this far。 and you shall be proud of yourselves。

And with that said， what we're going to be going over today are going to be some of the more advanced topics that you probably won't even see covered in other courses here at Uish。

Um， but they're just things that I think are。Very， very cool。 And at the very least。

 they are certainly helpful if you want to get into some advanced C+ plus programming in the future。

 So that said， I'm gonna try to go over this at a reasonable pace， reasonable being rather slow。

 And if you have any questions at any time， please feel free， put something in the chat。

 I have it open or just unmute your mic and you know shout it out， stop me at any time。So。

Without any further ado， here's what we're going to be going over today。

 I think we'll make it through all this I've allocated two hours for this and I'm pretty sure we'll be able to get through all of it in time。

 but if we don't I'll just go over and feel free to leave everything we will be in the recording。

So the first thing we're going to talk about is move semantics。And C++ move semantics。

They're kind of based around the idea of the rule of three。

 so if you were if you were at UMH when you took your course before E281， which at UE would be E280。

 you would learn about the rule of  three， which is if you're defining a custom class or struct。

And you need to define any one of the following those being a copy constructor。

 a copy assignment operator or a destructor that you probably need to define them all。

 and if I'm remembering correctly from E 280， this usually was referring to the managing of dynamically allocated memory so if we have some class that in a constructor calls new on some chunk of memory。

 then normally what we would want to do in the copy constructor and copy assignment operator is do a deep copy of the allocated data rather than just a shallow copy of just the pointer itself。

And this makes sense， because we don't want to。We don't want to just copy the pointer value。

 We want to actually copy the data that's being pointed to。

 so that would be what we would override the copy constructor and copy assignment operator to do and in the destruct。

 of course， if we call it new in the constructor， we're going to probably need to call it delete in the destruct。

So that's the idea of the rule of three， if anybody has any questions on that， go ahead。

 this is just a general idea from Es 280 that hopefully at least some of you remember。

And then building on that， though， is that we have kind of a tricky situation with the rule of three where we run into some。

Issues with efficiency where we could have a better situation。So like this says， if you guys want。

 you can type in this link into your browser， it might be a little bit of a pain。

 so I'll try to put it in chat actually。And then you can hit the fourth button and you can play around with this code yourself。

 or you can do you can just do what I expect most of you will do。

 which is just watch me play around with the code。So first question， can you guys see。The rep like。

 can you see this， this code here。Sweet， thanks everybody。So first。

 we're just gonna go over this brief class that I've written out here。

 just basically describing what I。What I just outlined with a class that manages dynamic memory。

 so we have a constructor， what we're going to do in the constructor， this is basically。

 we're just going to implement a vector， a vector class like we've seen in the STL。

So in a constructor we're gonna to have some size capacity and some data pointer and we're calling new in the constructor。

 this is the important part we're managing some dynamic memory and we just have some print statement here so we can see in the demo that's to come what exactly is going happen。

 Destructor we're going to delete the data This is all not very important the memory thing is just just so we know that we're managing something and you'll see you'll see later why that's important。

We have a copy constructor that's going to print out that basically we're copying the data and you can see that in the copy constructor。

 we're actually doing a deep copy over the data。And then in the copy consign the copy assignment operator。

 excuse me， we are just going to call the copy constructor here so we're redelegating that work to the function we already wrote and then we're doing swap so if you remember from lecture there's the copy swap idiom where we can essentially reuse the copy constructor to get around duplicating the work of writing both a copy constructor and a copy assignment operator。

But the main line here is that both of these things are both doing a deep copy。嗯。Yeah， so。

We've got that， we've got our swap function， which both of those rely on。

And then I've implemented a pushback function that if you really want to see it's。

Down here somewhere， it's basically just doing the。

Push and then grow if you need to kind of idea that we've seen in class， but。Nobiigil。So anyways。

 with all that said， the important things you need to know at this point is that we have a custom vector class and that I've overridden all of the constructors and destructor to print out when they're called。

And I have an ID class or an ID static class member that just tracks。You know what。

 what number vector we've created。 So the first vector we create will be vector 1。

 the second vector we create will be vector 2。 and I've labeled the names accordingly as well。So。

What does the static keyword do here So good question。

 I know we don't talk about static members usually like at all in any of the classes here。

 but static when referring to a class member， whether that be a function or a data member。

 just means that this variable is shared amongst all myint vector objects。

So what this allows us to do is so we have this next ID variable， what we're doing。

 you'll see down here， I initialize it to one and you have to do this outside of the class if you want I can talk about that more but I don't think it's that important you just have to know。

You have to initialize it outside of the class and then what I'm doing is in the constructor。

 I'm setting each individual object's next ID member to be the shared next ID variable plus one。

So what this is doing in practice， it means that the first time a constructor is called ever in this class。

 what we're going to do is we're going to set that object' ID variable to be， you know。

The class wide count for how many might in vectoror objects there are in existence。

Does that make sense， I don't know if that was a two roundabout way or not in depth enough， cool。

cool。Yeah， so we'll see that when we try to run this in a second。

But I guess the main point here is we're just going to try to figure out what the output should be。

 So thinking about the big three， what we're going to do is create of Gs。系。Losing some lines here。

Okay， cool。 Well that work。 So we're creating a vector。

 And what I would guess is that this is gonna to print。嗯。Constructing vector1。

We're going to push back some stuff。 I didn't have the pushback function print anything。

 and then we're going to print it， and I would assume if we implemented this correctly。

 we're going to get something that looks like 1，2，3，4，5。 So that looks good to me。

 Then we have vector 2， which is co be constructed from vector 1。And， of course。

 what this should do is do。ACo C tour probably from one to two。

 that we're going to push back a new item into vector 2 and the important thing to note here is that vector 2 should now have1。

2，3，4，5，6。Right， so we want to add that to that， but we want vector 1 to still contain the original data。

 This is just kind of checking that we're doing a deep copy on our data。 and we don't have any。

You know， if we did a shallow copy here， both of the pointers refer to the same array。

 and therefore we would have added six to both things so that's just making sure we're doing a deep copy。

And then if we do this， another default constructed my vectoror。

 we're going to do we're going to have a C tour3 printed from this line。

 and this will call the copy assignment operator。 So again， we're going to get another deep copy。

So we're going to get copy。A sign from one to three will be the output。

And then when we print this here， we should also get one， two， three， four， five。hoops。

So let's just double check that I'm correct here， I've written a little make file to let me actually just double check which one I want to use here。

嗯。YeahI've written a little make file to。Make the construction process a little easier because we've got a bunch of these that we're going to go through。

 So let's check if we were right。So I said we're going to print c to our  one。

 Y we constructed object one， we're printing the first vector， and you can see we have  one。

 two34 five。 looks good。Then we're copy constructing from one to two。Or from two to one or sorry。

 two from one。 So y what I wrote there is correct。 and we can see that this has the six at the end。

 my in vectoror number two has the six at the end。Whereas my in vectoror number one does not have the 60 end。

 so we did our deep copy correctly。Then we have our。Constructing three， like we said。

 we're copy assigning three from one。 And this right here is where it gets a little bit interesting。

 We see a copy constructing four from one and then a destructing4。And this might be a little bit。

Weird just eyeballing it， but if you can remember back to our implementations。

 we're actually calling the copy constructor in our copy assignment operator and we're constructing a temporary vector here。

So this this four that's created this this might vector number four that's created is actually this temp vector。

 And you can see at the end of this function， this temp vector is actually going to go out of scope and destruct。

So that's why we get this destructing four。And this usually isn't that important to worry about。

 it's just， you know， explaining why the things that were printed were printed。And then at the end。

 my inor 3 has12 through4 five， like we assumed it would。And we get destructing three。

 destructing two， destructive one， so all of our local all of our local mi vectors deed as we expected they would。

Um， so that's just the brief overview of the rule three， probably at this point。

 a lot of you are wondering。You know， I I already know all this。

 why is Michael going over this and move semantics are actually going to help us in a lot of cases。

 making these deep copies more efficient。So let's take a look at this second chunk of code here then。

So we have this function， create big vector， which just takes in a number and then。

It just creates a vector with the numbers from0 to n or 0 to n minus-1 rather。

 And then it just returns the vector。 So this is pretty straightforward stuff。

 If we do create big vector with 10， we should expect to see the numbers 0 through 9。

 And then if vector prints， we should see， you know，0，1，2，3，4，5，6，789。But the question here is。

What exactly is gonna happen。With the vector that is kind of temporarily constructed here and then copy assigned to this vector。

And a better way to ask this question would maybe be what happens to Big Vec。

 which is local to this function？Are we going to create an entire vector here。

 which has the items from zero to9 and then as soon as it's returned。Gets copied into this vector。

 And then this local variable is destroyed。 or we going to have a situation where。

Maybe this big vector is constructed and then all of its data is just。Now， assumed by the name Vec。

I think a better way to go about this would be， maybe to just。

See exactly what happens and then talk about it because it's pretty difficult to understand without looking at output in my opinion。

So what we see here is we're constructing one and if we follow the code here。

 actually what this is doing is we're going to go into this create big vector function first。

 so this is actually vector 1。嗯。So we've created this vector。

 and then before that vector is destroyed， actually， we copy construct 2 from one。

So it's kind of like the in between of this line here happens before we actually lose the local variable from this function。

So we are creating this， which is vector 2 from vector 1， and then vector 1。

 which was big vector this function， is destroyed because this function call officially ends。

And then。And then we see copy constructing three from two。Let me think about what this is doing。

Oh yeah， this is something I forgot， actually。But what's actually happening here？

So return doesn't finish until the copy construction happens。 Yeah。

 so you can kind of think of the process of a function as being。

Only finished when the return statement finishes and part of the return statement is kind of storing the return value where it belongs。

嗯。So part of what I misspoke about there is this is V1。

 it's going to be constructed and at the end of this function we're going to return it。

And we're actually returning it to this kind of temporary variable here。嗯。

So if we just ignore the left hand side of this assignment first。

 so let's say we just had this line of code here， this would still execute and this would still work。

This line of code itself， once it's executed， is actually a myin vector。 Once this code is evaluated。

 right， because the return value of this statement is a myan vector。

 the type of this object will be a myin vector。 It's just going to be a temporary and it's going to destruct as soon as this line finishes。

 but this in and of itself is a miin vector。So we have this temporary object here。

And that is going to be。That's going to be our Mayant vector， which is labeled too。

So we already have this kind of temporary thing here， but it has a name。

 then we have this temporary thing here， which doesn't have a name。

Then what we're doing with this second temporary vector is we're only then assigning it to our actual vector V。

 and that's why we have the third vector， which is actually vector V。

 which is copy constructed from vector 2。And then we destruct one and2。 And at the very end。

 we get to see 0 through 9 printed， which is the data we expect。

 And the whole point of this is to just kind of say。If you are。

Copying large data out of out of a function or out of a piece of code that doesn't need the data anymore。

 So， for example， this might vector big V variable does not need the data anymore after this function returns。

 There's no need for us to copy this data， right， We could just steal all the data from this big V variable and give it to Vec。

TheresThere's no need for us to make a deep copy here that's just kind of a waste。

So that's the idea behind this， and that's the justification for move semantics。

I can talk about specifically what's happening with the double copying in one second。

 But I'll answer this question first。 Why can't I just create the vector on line one and then pass it by reference to the function。

 No copying necessary。 Yep， that's a totally valid way to do this。

 And I've actually lied to you all a little bit because this isn't how C plus plus actually works。

 I've。If you take a look at this line right here where I'm actually doing an the compilation step。

 I have specified a special constructor flag or a special flag for G++。And。If I make copy allied。

 I've specified the same compilation process， but without that flag。

And this will make a little bit more sense after I run this。

 and I'm sure you guys just kind of think about this implicitly at this point， but。

If I run it without that flag， you'll see that I just have constructing one and destructing one。

Which is very different from this huge mess of three mayant vectors created and three mian vectors destroyed thing we have here。

And that's just because of this thing called return value optimization。

 which I will talk about later。 I know this is a lot of information at once。

 but basically default C plus plus implementations， compilers are allowed to。

Specifically for returned values from functions， compilers are allowed to construct the value。

In place as opposed to constructing it as a local variable。So。

The default options do this automatically already。 Yes。

 but you'll see there are many cases when the compiler is not smart enough to do this for you in order to keep this example。

I guess understandable in a short period of time， I did elect to go with something that was。

I don't know， a simpler example， but we'll see in a second。

So just a really quick wrap up that last thought though。

This big vector is actually never created if we use the default G plus plus compilation process。

 What happens is instead of creating this my vector big vector。What the compiler sees。

 the compiler sees that this function is just returning a my vector by value。

 And because that my in vector is created in the function and is returned after the function ends。

 the compiler knows。You know， there's no reason that this vector has to exist at all。

 Why can't we just create that vector where it's gonna to end up。

 Why don't we just create it where the return value is assigned？ So that's exactly what happens。

 Instead of creating a big vector here， you can essentially think of this as like Thomas said。

 the function is now essentially taking in this vector by reference。

 and we're populating the vector itself。Right， so V itself just gets the data。

 So that's called return value optimization。 And if this isn't making sense。

 I promise this is only like the first slide of this and it will it will sink in once we've gone over an example。

Okay， but the big idea is without this optimization that the compiler just happens to be smart enough to make。

 there are a lot of situations where we can get away with stealing the data for temporary objects when。

When they're about to be destructed， so we know a temporary object or an object like this。

 which is local to a function， it's about to be destructed and we know it's not going to need its data anymore so we can just steal its data and not feel bad about it as opposed to doing a full deep copy。

So。That's the one thing。 Okay， let me answer some questions now。

 So whoever wrote G plus plus really thought about every way to optimize code。 Yeah， I mean。

 I'm sure if you really dug deep into the G plus plus code base。

 you would find some absolutely nasty lines of code for just some insane optimizations。

Are there any encode flags that can explicitly request the compiler to use copy illusion？ Yes。

 that's just the， the default is that。Well， specifically for。

There are a few cases where compilers are allowed to use copy illusion。

 one of them is return value optimization， which is this example here where it will construct this Mayan vector in the returned location as opposed to on the local stack frame and then copy it out。

I think there are others， I'm not sure， but。One thing that's important to note here is that this。

 this copy all actually does change the outcome of our code。 In this case。

 the only change that we can see is that we're avoiding。

Avoiding calling the copy constructor and you can see， though。

 there is a difference in output just from our code itself， our code。

 the execution of our code changes because of this copy all。

And you can imagine that if our copy constructor did something other than just print something。

 this could have affected the run of our code。So a lot of cases where the compiler maybe could detect that it could align a copy constructor。

 I'm not sure if the standard allows it to in every case。

 because you know that changes the outcome of your code and a lot of programmers probably don't want that。

嗯。So if that doesn't answer your question。Feel free to follow up。 but at the same time， there's also。

A huge depth of knowledge， which I don't have about the specifics of compilation。Anyways。

 let's go back to the slides though real quick because。

I think the the big idea of this will be coming up soon。 The moral of the story。

 if you didn't get any of that because we did go a little bit off track is that if we know the other object won't be using its data anymore。

 we can just steal it to somebody， if somebody has a question， feel free to speak up。Yeah。Yeah。Yeah。

Otherwise， I think somebody accidentally unmuted so。Just make sure that before we continue。seeep。

 other objects not using its data anymore， we can steal it。

We don't have any way of doing this with the functions outlined by the rule of 3 though。

 So if we only have our copy constructor， a copy assignment operator。

 we can't exactly define like a steel operator。嗯。But the main idea here is that stealing the data is often much faster than copying it。

 so you can think of our deep copy for our May vector class as being O of N。

 right we need to copy each individual data element into our new vector。

But our our steel operation we could think of as just copying the pointer itself。

 so if we just take over the pointer itself and then we give the other object like a demmi pointer。

 then we know that we now control that other objects data vector。

 or data array and that other object now controls an empty data array。

So stealing is often much faster than copying， and this is exactly what moves semantics allow。

 They allow us to steal the internal data when we determine we don't need to make a copy。So。

This is the brief aside where we already kind of got into this。

 but good compilers avoid making the copies without us asking them in certain without us asking them to in certain cases。

 such as when we're returning a temporary object from a function。

 So in our create big vector function before we already discussed this。

 but that local variable big be is never actually created。

 we just create the vector in the return spot。And that allows us to avoid making that copy。

And it's usually clear that this data that's about to be returned doesn't need its internal data once the function returns。

 so they can just build it where the values returned to never creating the temporary object in the first place。

Yep， so。Maybe some of these slides are going to be me just reading these bullet points and then fielding questions。

 but I guess that's what you get when you try to make slides that are accessible for people that are just viewing the slides。

So I'll hop back over to。The repplet。Oops， I guess I can just go here。

To look at an example where we have a move constructor defined find。So let me clear out the terminal。

So we have our same mind vector class and。We have our constructor destructor， copy copy， blah，lah。

 blah， and now I've defined a move constructor and a move assignment operator for this class。

And the syntax is going to be a little bit wonky here， so I'll go as slow as I can。But if we have。

 let's just look at our copy constructor first and then compare it。We have。No return value。

 just like any other construct， and we're taking in exactly one parameter。

 which is the other my vector object that we're copying from。嗯。And in this case。

 we're taking it in by cont reference for the copy constructor。 And this is typical。

 You normally take it in by con reference。 You could take it in by just normal reference without the con。

 or I suppose you could just take it in by value。Actually， no， you couldn't because then that would。

Cause some infinite recursion either way， not really important。

 We're taking it in by reference for copy constructors and for the move constructor。

 it kind of looks like we're taking it in by noncon double reference here。嗯。In this， this。

Deeclaration here is actually denoting that this other value is an R value and this is a term that probably none of you have ever heard before。

 and I'm going to have to delay explaining it for a few slides because it would be a huge aside to explain it now。

 but think of this as the syntax for defining a move constructor just looks like that and then what we're doing in this constructor。

Is we're just shallow swapping with the other vector。

 So if we look at our if we look at our swap function here。We're just swapping。

The first size with the second size， the first capacity with the second capacity and the first data with the second data。

 and if we look at our data object or our data member， like I discussed before。

 it's just the pointer to the in array。So this， all this is doing is doing a shallow swap。

And the move constructor。What it does is just shallow swaps all the members and that's all it's doing。

嗯。Man， this is， there we go。It keeps showing like white boxes on my screen for some reason where it's obstructing a code。

 I don't know if you guys can see that。So just doing a shallow copy there。

 we're avoiding making a deep copy and the idea here is if we know that this other vector isn't going to use its data anymore。

 we just steal it and we can steal it by doing a shallow copy。

And one other thing to note if that's important， which I almost forgot is that we're actually。

Calling the default constructor first。So before we swap our data with the other vectors data。

 we are initializing our data with default stuff。mSo right here we're initializing it with default stuff and we're just calling that function to make sure that whatever data we give the other vector after we swap is safe data。

嗯。So one thing that you might consider is that if we steal another vector's data。

 what happens when the other vector destructs， well。

 we need to make sure that that other vector can destruct safely。

 and you can imagine that if the other vector was still pointing to the data that we just stole。

 then when the other vector destructs， it's going to delocate the data that we wanted to keep。

So we need to make sure that we initialize our data vector with something safe。

 that it's okay for the other vector to destroy when it destructs。But again。

 we'll see an example of this in a second。 I think it'll be important for everybody to take a look at that before we think too deeply about this。

 And then the move assignment operator。Very similar。

 we're just doing a shallow shallow swap with the other vector just stealing the data。And then。

 in typical。Assignment operator fashion， we're just returning the dereference this pointer。Okay， so。

What will the output be this time when we do our same line of code？And this time， we are going to do。

We're going to use that NOAAied constructors's flag again。

 so we're going to get every constructor call that you would expect to see here。First question。

 All right， we got if we define a normal non move C tour to do this with the compiler yell at us。嗯。

So this is kind of what we'll， we'll kind of get into this in a little bit with the R value talk。

 but。This will only be called when the function signature is matched。

 So if we're thinking just about traditional function overloads in C plus plus， right。

 we do have a constructor here where we have Mayan vector with one parameter。

 and we have a Mayan vector with another parameter or with one parameter here。 So these are kind of。

Conflicting definitions and the compiler needs to choose which one to call in each scenario。

 And this is only going to be called in very specific situations。 So I think yeah。

 Paul is right where the parameter is technically different than the parameter for this function here。

So they're just called in different scenarios。 And I think the bottom line is， you can't。Well。

 you could define a constructor。That steals the data from the underlying vector object。

You would need to know exactly when。You would just need to be sure whenever you called that function that the object could be stolen from。

And。The advantage of using the R value as the parameter here is that the compile will be able detect to detect for us exactly when the other object can be stolen from。

So maybe that's roundabout， I promise we'll get to that though in a second。

 I think kind of the nature with all this is that there's a lot of new topics being introduced at once and that we kind of just have to work through them。

But yeah， this， this will be useful， more useful than defining， say。

 a function that's called steel data。 and we' see we'll see some explanation for that in a second。

So what was the R value again？I'm going to defer that question for a little bit。

 I know that's annoying to hear， but we'll come back to this code after I explain it。

 this is just kind of the justification for move semantics so。

What's going to happen when we run this new code？Right so we create a big vector。

So we're constructing one， which is。Our big v here。Then we construct two。

 which is our temporary vector here， if we remember from last time。

 and then we move construct2 from one， so instead of doing that deep copy。

 the compiler recognizes that this is a temporary value and we're constructing this vector here by just stealing this vector's data。

And then in the same vein， we're constructing the third vector， which is this actual vector。

 and we're move constructing three from two because the compiler is able to recognize that this is a temporary vector and again we can just steal its data。

So， with our。With our nifty move constructor and move assignment operator。

 we're able to avoid making the unnecessary copies in this case。Okay， and one more thing to note。

I guess we'll uncom that really quick and give it another run。

But it's just going to be what you expect， we're going to get full control of the data from this big vector that we created in the function。

Why is ampersand ampersand used instead of single ampersand for move semantics？For that。

 I think it's just。They needed a way to differentiate the R value reference from an L value reference in the standards committee and again we're just going that'll be something I'll defer for another slide or two。

Okay， so this little note here， maybe this is getting in too deep。

 but I think it's important to note so if we steal the other data and remember when we steal the other guy's data。

 we're just giving them whatever our data was and if we don't say we don't say we don't default initialize ourselves when we run this code。

What's going to happen is。If I can get there。We're going have。We're going to have this weird。

 double free or this core dump here。And the basic explanation for that is that when we move constructed the data out of this function。

嗯。无异议。We moved it to this vector here。But this vector here still has to destruct。

So when this vector destructs and you can see it here from the destructing one call。嗯。We didn't。

 we didn't give it anything else to point at。All we did is we swapped。

 we swapped the values that this was initialized with with its other data and。This wasn't。

 We don't really have any data in this case。 We didn't initialize any of our member variables to anything。

 These are all uninitialized， and we gave the other vector totally uninitialized data， so。

It's not valid for the other vector to delete uninitialized data because probably this pointer is not null pointer。

 which means it's not a safe thing to delete and as a result we get some invalid free and we get a core dump。

So that's just why it's important to。嗯。Initialize your own data before you swap it with somebody else that you're。

That you're stealing from。Okay， so I'll hop back over to the slides and I'm sure I will answer a million of the other questions that have popped up in chat。

So return value optimization is one instance where the C++ standards allows compilers to all the constructors。

 so we had matching function calls in our my vector class in this case， or in the previous case。

 we had copy constructors that matched。But the compiler determined we didn't need to make a copy there。

 so it instead had built the object in place。So this is just a big aside about how。

 like I said earlier， if we actually were relying on the side effects of that copy construct being called。

 then maybe this would be a bad thing， but usually it's a good thing So I'm going skip over that because it's such an edge case Here we go。

 let's get to our all values and R values and then I'll answer the chat questions。So in C+ plus。

 there is a non in C plus in。Most programming languages。

 there is a distinction between R values and L values。嗯。

And I think let's just talk about this a little bit before we。I guess get too much into the theory。

 but definition of an L value you can think of as being something that could be on the left hand side of an assignment so。

If you want a little mnemonic， you can think of it as a location value。

 cute little L there at the front， is it only represents the location of some data variables。

 which are names that refer to data are L values， or is the definition of an R value。

 is that something that can be on the right hand side of an assignment。

 a good rule of thumb is that these are read only values。

 temporaryname unnamed variables are R values。 So whoops。

Let's just go through this code here and I can point out what are our values， what are L values。

 and hopefully that'll give you some idea of what these words mean。So。

First thing I'm noting here is right hand of this assignment is the string literal apple and the string literal apple is in R value。

 It doesn't have a name or variable associated with it。 It is just data。The good rule of thumb。

 I think， is important here， it's a read only value if we try to assign something to the string literal apple。

Nothing would happen， that's definitely not valid， you can't store something in a temporary object。嗯。

Right so this string literal apple， it's an R value， bananas is an R value， orange is an R value。

 the S1 name itself though is an L value right， so it's a variable。

 it's a location where we can store data and ultimately it's just a name that refers to some data。

 so whereas r values are usually just raw data， the L values are usually names that refer to raw data。

So S1 is an L value， S2 is an L value， S3 is an L value。whohoops， I keep scrolling on accident。

Back one， L value， just another variable like we talked about。嗯。Here more examples。

 X and Y are L values， but the three and the four are data themselves， there are values。

Here's another， I think， canonical expression here。

 we have an assignment where we're assigning to an L value， right？

But the right hand side is an expression。 So what's happening here is S1 plus S2 what that's going to evaluate to。

 it's going to evaluate to some new string object。 The new string object is going to contain the text Apple banana。

 but that's not going to be stored in any variable yet it's just a temporary variable or a temporary value that contains the string apple banana。

And then that temporary value is going to be stored in the string S3 variable。

 So the expression itself， S1 plus S2 is an R value。

 but S1 itself is an L value and S2 itself is an L value。

And then there are some other examples down here。 But at this point， if anybody wants to。Um。

 pipepe up and ask any questions about this or put anything in the chat。I recognize that this is a。

Pretty difficult concept to grasp on the first time around， so。If anybody wants to ask any questions。

 please go ahead。I guess from chat， if we weren't using copy swap。

 we would only construct two vectors here， correct？let me see。So if we go back to our example。

Alright， let's find out。 I think if we weren't using copy swap， we'd only construct two vectors here。

 I think you're referring to the temporary vector here or not temporary。

 the local vector here to this function。 and then the like true temporary vector here。嗯。No。

 we would definitely still have both of these vectors。Yeah。

 we would still have both of these vectors。 and if you see if you see the move con or sorry the if we go back to our our copy。

I think is the， the better。Example。If we go back to our。

Our copy constructor example you can see that it's actually calling the copy constructor not the copy assignment operator so even though it looks like we're doing an assignment here right。

 we're actually it's actually calling the copy constructor and that's just something that another G plus plus thing most compilers will make this optimization where if it detects that we're creating a new variable。

Usually it will call the copy constructor instead of copy assignment operator。

So if we had the copy assignment operator， I agree we would have a temp vector constructed and then。

We would swap with that temp vector。 But in this case， it's actually calling the copy constructor。

 which doesn't create another local variable。 So that's just another。

Iickkey compiler thing that it just does without your knowledge。And now I've lost the chat。 Okay。

 chat back here。Okay， informal answer just to help understand our values， value that member location。

 something that can only be used in the RHF an assignment。 Yep， very good from Paul。

 Great explanation。😊，Okay， Elen asks， how does plus plus x and plus plus x do to R or L value any specific use cases for either。

 Yeah， that's a great question， so。I'll hop back into this。So this was a specific。

 funny edge case that I remember looking at myself because I didn't remember when I was writing these slides。

So what x plus plus is actually doing is it is incrementing the value of x。

 but the expression itself evaluates to the old value of x。So。For example。

 I guess let me again hop back over to the， the code here。 So let's say we have int X equals 4。

 and then we see out。X plus plus， right。What we're going to get is。Make sure I'm actually。

Write about this。Right， we're going to get 4。 So x is actually incremented。

 but we're going to get the old value of x as the result of this expression。

 And then if we see how x itself。You'll see that we end up getting five because it is incrementalcremented。

 but we get the old value upon return。 So the consequence of this is that x plus plus。

It can't return the value itself because the value itself needs to be updated and we want to return the old value。

 it has to return a temporary copied value。So。If we think of。Man。

 this would be nice to have something I could draw on here。

 But if we think of like X as being stored up here， just like using my hands as a diagram。

If we want to assign a value to x， then we need to actually know this location here。 We need to give。

Whatever， I guess assignment that we want to use， we need to give it this location here and say， hey。

 put whatever value you want to assign in this box。

But because we want the old value of x to be returned from the expression x plus+。What happens is。

We need to increment whatever's in this box here。But we want to return the old value。

 So we can't return this box here。 We have to return a temporary object that has the old value。

 So as a result， say， we wanted to do something like this。

You'll see that this it's going to yell at us for this being not assignable and what that means is that x plus+ is evaluating to an R value or something that cannot appear on the left hand side of an assignment。

Conversely， though， or not conversely。Maybe somebody who just took 203 can help me out with what I mean by that。

If we do plus plus x here。I guess this is probably a better way to do it。 Plus plus x， because plus。

 plus x prefix actually increments the value before。The expression returns。

 and this evaluates to the incremented value。 We can actually just return from this expression。

 that box itself。So if we do plus plus x， we're going to have the old value， say the old value is 4。

 It's going to be incremented to 5。 and then that whole expression itself can actually evaluate to the object itself。

 It doesn't need to evaluate to a temporary object。 So as a result。

 we can do plus plus x and then assign that a new value。Because plus plus x is an L value。

 whereas x plus plus is an R value。So that is probably overkill for what you're asking。

 but hopefully that makes sense。 Let me know if that didn't make sense。

 and I can go in a little more depth about that。So but how many of these R values actually exist when the preprocesor gets around to optimization？

Good question， I think I'm going to defer that a little bit。

Because you don't need the processor to or you don't need the preprocessor or the compiler to determine what is an L value and what's an R value。

 you can actually specify it yourself and say， hey， I know better in this case。

 this is actually something that's going to be used。So is x equals 3。

 the same thing as plus plus x equals 3。 Yeah， I mean， in the case of just having integers。

 of course， incrementing the value of。X beforehand has no effect on it， but yeah。

 I think what you're getting at is that plus plus x equals 3 does change the value of x， yes。

It changes it to three specifically。By the end of the line， plus plus x equals 3。

 x will have the value 3， no matter what happens。Yeah， and that actually， if you want all that。

 if you want to see all that code golflfed， you know， pointer arithmetic stuff。

 then I agree this is pretty important stuff。 So that's kind of the distinction between L values and R values。

 feel free to keep asking questions if you want。 But now we have our full rule of 5， which is。

The updated version of the rule of three， where if you have a copy constructor。

 copy assignment operator， we probably also want to define a move constructor and a move assignment operator along with the deor and that's just because if we have some resource that's being managed by our class that you know it's it's a sufficient resource enough to where we need to。

Specify rules for how it is deep copied， then we probably also want to specify rules for how we can steal that data。

And that's just the basic idea there。So let's take a look at our previous example using that。

Interesting， well， I think。I think I already did that。

 so I'm not quite sure why I put this slide in there twice。Okay， so now we have now we have， I think。

 what Thomas was asking about earlier。But。Stid moveve is a function that allows you to tell the compiler that。

 hey， the object that I'm referring to is actually in R value。So from CBB reference。

 this is just exactly what CBB reference says Siid moveve is used to indicate that an object T may be moved from i。

e。 allowing the efficient transfer of resources from T to another object。

 it is exactly equivalent to a static cast to an R value reference type。So in other words。

 we're just telling the compiler to interpret this value。

 which likely has a name in this context and thus is an L value as an R value reference。Okay。

 so I think getting at Thomas's question earlier for why would this actually matter。

Why would you ever need to do this because the compiler is probably going to take care of all those cases for you and the answer is that you can tell the compiler。

 hey， in this case， we need to treat this value as a value that can be moved from or a temporary value that we can steal from。

So here's an example of using SidMove。Let's say we have two functions of F up here。

 We have one that takes in an R value reference mightant vector。

 and we have one that takes in a constant L value reference mightan vector。

So we we construct some vector here and we callF on St move of V。So which version is called？

If somebody wants to take a shot at answering。Go ahead。Top， I agree， perfect。

And this is just because even though V in the context of main， V is an L value。 V has a name。

 it can be assigned to it is an object that refers to the location of some data or it's a name that refers to the location of some data。

 it's an L value。 but what happens here is that we are。We're calling stood moveve。

 which is basically telling the compiler hey， treat this as an R value reference。 So as a result。

 we are getting version A of that function call。 But down here we're going to get version B because V is an L value So thus we're getting a con my vector reference V。

 which is just a con L value reference。嗯。Cool， and then。

This is the kind of the kicker here with using standard move。

 our stood move is that what if this version a of the function steals our data。

 and this is kind of the point of having functions that take in our value references is that we're telling the function that。

 hey， this vector doesn't actually need its data anymore。You know， you can steal from it。

 so it's totally valid for this function to just take the data or modify it in any way that you want。

 because we've told this function if if we're in this function at all。

 this function should expect that Vec is data that be can be stolen freely。

So if foodo steals our data。Then we don't know what's going to happen in this call down here。

 the second call of fo， you know， the state of V is completely undefined after this call unless we knew exactly what this first function call was doing in the definition。

m but yeah， you can't really rely on the state of an object effort it's been moved。

 so that's just saying that foo may or may not steal our data or change it or do anything to it because we've told it。

 go ahead and do it。So if we go back to our。Move assignment operator， remember。

All we did is we just swapped we swapped the data in the current vector with the other vectors data。

 And if we imagine the same thing happening here in the definition of fo。

 maybe we got some other vectors data just randomly maybe we got like 4，5，6。

7 is the new value of my vector V and that's just something where again。

 you don't know what to expect if you are using move on some value that you want to use later。

 So rule of thumb only use stood move when you don't actually need the value。

Of the variable after it's done returning。So just another thing to point that out there。

And then I guess let's go back to that really quick and I'll try to answer some of these questions If anybody has any questions about St move。

 feel free to put those in there。Now I understand 30 seconds of lecture where Dr。

 P said we need to rule five without explaining what the other two were， yep， yep， yep， yep。

Some more pointer stuff， some piazza stuff， cool。Okay， yeah。

 if anybody's got any questions about Si move。Feel free。To did move， just say make this an R value。

 Yep， that is all it does。 And in fact， if you go to the CPP reference page。

 it is exactly equivalent to a static cast to an R value reference type。 And that is just true。

 It's a a friendly way to just do an ugly static cast。Yeah， which is pretty funny。

 but a lot of the times it's very necessary。So it would be static cast。

 might inveor ampersand ampersand B， yes， yep。And in fact。

 if you want to avoid using Std move and you just want to do the static cast yourself。

 that's totally valid。You can cast all your L values you want to our values the long way。

 and that's totally valid。Okay， I'm going to try to pick this up because even though move semantics are probably the hardest。

 the hardest thing in this mini lab， then they're not the only thing， so let's keep going。Okay。

 so we've already got that。 We've got universal references。 I'm gonna to breeze over this very。

 very quickly。 feel free to ask questions， but this is kind of a dark corner of C+ plus thing which is not used。

 I have never used this personally， but I can imagine others using it。

So if we want a template to function to take in both L value and R value references。

 while still preserving what type of value they were。

 then we can do this with something called universal references。

So feel free to read the rest of the slide。 But let's say we have this function bar。 And based on。

You know， the type of the vector that's passed to it， we want to call the appropriate version of foo。

And the question is， do we have a way to do this or do we need to have a version of bar that takes in。

 you know。An R value reference in a version of bar that takes in a cons L value reference and duplicate that code。

An answer is yes， there's a way to do this with something called universal references。嗯。So， this is。

I would say some undeniably ugly code， but I'll explain what it does very briefly。

 We've got our two versions， our value reference， Con value reference。

 We have the function bar here that was previously mentioned。 It is templated。

And the type of the parameter is T ampersand ampersand。And this is。

Controversially or maybe not controversially called a universal reference as opposed to an R value reference in this context。

嗯。And。I guess without going too much into it， if we look at this code down here。

 if we call bar with an L value， what's going to happen is this V is going to be initialized with a constant L value reference and then when we call this stood forward。

 which also needs to be templated， it is going to forward the underlying value of V so。

You can think of Vec as。Knowing what the original type of the value was upon passing so。

In the context of this function， Vc has a name， so V is always going to be an L value。

But when Vc was passed to this function， it actually might have been an R value。

 So in this case here， my in vectoror is a temporary value。 So when we pass this to the function bar。

 Vec was originally initialized with an R value reference。But again， in the context of this function。

 V has a name， so thus it is an L value。So if we want to get back that R value reference that we had when we passed the value to this function。

 we need to call stood forward。Which。More or less， you can think of as achieving or accessing that previous true type of whatever V was。

 and it'll call the correct function as a result so。These both call bar first。

 but this one is going to call version B of fu， which is the constant L value reference。

 And then this one is going to call version A of fu， which is the R value reference again。

 not really that important。I'm going to skip over that。Quz time， I'm also gonna skip over this。

 feel free to go through and check out quiz。 cP。 It's just a lot of examples with。

A bunch of this stuff being exercised and just picking which function will be called in each of the given instances。

 This is tough stuff。 so do not worry if you're not getting edges from this and we clearly do not have enough time to even go in depth at a high level about this。

So I think we're going to skip ahead to smart pointers。 But first。

 I'm going to answer all the other questions in chat that I see。

So does a compiler optimized by automatically our value casting variables the very last time they can be used。

 So that's a good question and。My answer is， I don't know， but from my experience， the answer is no。

 because that's actually a very difficult。That's often a very difficult question to answer。

You can think of the easy example where if you have a local variable declared in some scope。

Say that's about to destruct， it's very easy to tell， hey。

 this value will not be used after the scope destructs。

 therefore you know you can steal its data right now。

But it's not very easy if the variable is outside of some scope that's about to destruct。

And I think oftentimes， you cannot tell that。 And if you want to。Mark that an object is stealable。

 then you need to do it explicitly in a lot of cases and also for code readability。

 you should use Stmove if you want to indicate that something should be stolen。

 even if you know the compiler is going to do it on its own。That said。

 you don't need to still move clear temporary variables， like in our last example， where we have。

 you know， my in vectoror passed as just a default constructed。Clearly there's no name。

 clearly this is temporary， you don't need to move that。Cool。Hopefully that answers your question。

With that said， I'm going to move on to smart pointers because。We don't have。

All night to do this stuff， but hopefully that's a good overview。So。Totally shifting gears here。

 you probably remember from E280 that managing dynamically allocated memory is hard。

 you saw a lot of that in what we just talked about here。Um，A lot of issues， you know。

 dangling pointers， double freeze， memory leaks， all that good stuff。

And there is a special class of objects that you can use in C++ and in a lot of other languages to completely avoid ever using the new or delete keywords。

And I think these are completely fascinating， and。I would expect。

 I haven't seen a lot of C++ production code， but I would expect these are all over any piece of complicated C++ code because they simplify things a lot and they have very low overhead in C++ fashion。

So the basic idea is we have a class that takes in an object。And it deletes the object。

When it detects， the object is no longer being used。

So it's a pretty simple idea on paper you can think of it as。Our constructor in our my vector class。

 which calls new in the constructor and it calls delete in the destructor。

 you can think of it as being very similar。Very similar to that。

 but maybe we don't call new in the constructor， somebody gives us something they want us to allocate and we manage and delete it when we detect it's no longer used。

So actually asks asks， does Java do this automatically， So Java。Java uses garbage collection。

 which is not exactly the same implementation wise as smart pointers and C++。

I believe believe Java uses the Shenandoah garbage collector。

 which I think is a lot more complicated than C++ smart pointers are。

 and that it's probably a lot more efficient at detecting things that aren't being used。

And it'll be able to detect usage cycles and stuff like that， I believe。

How does this differ from garbage collection， This differs from garbage collection。

Because garbage collection is often。That's a tough question to answer because garbage collection is kind of a a background process that runs underneath garbage collection。

 garbage collected languages， whereas。C++ smart pointers are kind of a programmer implemented thing where we are actively managing the memory and we're choosing to do it in a certain way as opposed to calling new and delete。

Yeah， I don't think I don't think I have the knowledge to give a much better answer than that。

 but they're definitely different， they're definitely different things， but very similar idea。Y。

So let's move on now。So the first class that we're going to look at is called St unique pointer。

The goal is we want an object to be managed by a single pointer and if we have a class that takes in a pointer and in that class's deor。

 we call delete on it， then we kind of。We kind of get that functionality so。

Let's just move ahead to an example， I think that'll be the best way to go about this。

 so let's say we have some item。This is just a general struct in our construct。

 we you know we have some in variable， we create some item and then we have a de that destroys it and we have a vector of unique pointer a a vector of unique pointer of items so you can essentially thinking you can essentially think of this as being equivalent to a vector of item star of items。

嗯。But we're using the smarter C++ version of memory management here。So。

Just as a justification for using dynamic memory at all。

 instead of adding some items to this container in our main function。

 we're going to add them in some other function。So we're going to add 10 items to our items container and in our add items container or add items function。

 You can see we're just。Going from zero to n。 and we're pushing back a unique pointer of item with the new item constructor I。

So we are giving this unique pointer object control of the pointer returned by the new operator here。

 we're giving we have the address of some item object and we are giving stood unique pointer control of that underlying pointer。

嗯。So that's that's kind of the justification for what's happening there and at the end of that line of code items is going to have an item with value0 through nine。

 so it's going to have 10 unique pointers in it。Pretty straightforward stuff there。

Then for each of these， for I guess， five of these items， we're gonna， we're gonna process them。

 So we are going to。Just pop the back of the container is all that's going to do。

And then at the end of that， we're going to say done processing。So， the idea。

I guess let's just look at the output。So 10 items are created at first in this add items function。

Pretty straightforward。 And then when we process each item。

 you can see that we're getting deors called here。 Remember， our deor prints item X destroyed。

So every time an item is processed， that item is actually destroyed。

And that's because when items do popback finishes。The unique pointer is going out of scope。So， items。

Yeah， the only， the only place that this item object is stored or more accurately， this。

 this unique pointer is stored is in this container。 So when。

The unique pointer itself is removed from the container， the unique pointer deor is called。

 and in the unique pointer destructor， it's going to call delete on the pointer it was given。

So when we pop back on the itemss container， the item object itself ends up getting deleted。

And that's the， I guess magic of unique pointers there。 So when we call process item  five times。

 we get 1，2，3，4，5 items destroyed。 And then it's done processing。 And after main ends up returning。

 you know， our file scope variables are going to get destructed。

 So the item vector is going to get destructed。 and we'll see that the rest of our。

The rest of our unique corners are going to get。Destructed and thus clean up their associated item objects。

Cool， so a few more questions， Andrew asks， did they use RAII stuff to do reference counting。

 like incrementing some counter on copies and decrementing them when the local references go out of scope。

 Yes， and we will see， I will go in depth on the implementation of these。

 because I think it helps a lot but if you're talking about。Garbage collection stuff。

 And the answer is， yeah， a lot of them do use reference counting， but they don't have to。嗯。Yeah。

 Gabe with the link to what Java uses for garbage collection that's fantastic。

 Why don't pointers automatically delete whatever they're pointing to when they go out a scope。

So the justification for why that's not the default behavior is that。It's just slower。The only。

That's another good point Ian is that weak pointer does that and I'll talk about that in a second too。

 but even if we have a one line destructor that calls delete on some some pointer or if we have something else in our destructor even though it's only one line or something。

Those， those lines of codes for performance applications may not be necessary。

 and they may just be wasting time。 So I think the justification when C plus plus was created was to maintain the efficiency of C。

 and they determined that。Although smart pointers were， I guess， a popular thing in the community。

It wasn't something that should be the default behavior。Yeah， and if you， of course， if you have。

If everything uses smart pointers as somebody。You may have double free if I think you delete every pointer yeah so you can't delete or you don't want to delete pointers that are referred to by smart pointers because they're already managing the object for you。

嗯。Cool， so I think， I think some other questions are going to be answered in a second here when I get into the implementation of shared pointers。

 So unique pointer。Was very simple in that it just takes control of one object and it deates it in the deor。

And this is useful， but sometimes we want to have more than one pointer that's referring to an object and unique pointer can you can think about if we have two pointers pointing to the same object and one of them goes out of scope。

 then the object is going to get cleaned up and our second pointer is going to be pointing to nothing。

 We're going have a dangling pointer。So the solution for this is that there's a second class of smart pointers called SharePoiner。

And they allow any number of objects to or any number of pointers to refer to the same object。

And instead of just having a simple constructor and destructor。

 we have a manager object that knows how many pointers are referring to the given object at any time。

And only when zero pointers are now referencing the manager object。

 it can free the memory for the underlying， I guess in our previous example， it was an item object。

Yeah， and in my opinion， these are much more useful than unique pointers and I had a project for E381。

 which is a class that is unfortunately not being offered anymore。

But you can just replace any instance of a。嗯。Of a raw pointer being used with a shared pointer with a few exceptions。

 and your program should behave exactly the same。Because they should have the same syntax and the same。

I guess implementation， not implementation， the same effects as using normal raw pointers if you replace them just word for word。

They're also copyable and moable， moable， copyable and moable， just some more helpful stuff to know。

 So let's look at an example。 let's say we have our shared corner shared。

Pointer container of items instead of our unique pointer container of items。

 So we've changed some definitions here a little bit。

Let's say we just add the container or add the items to the container in line here。

One thing to note is that we have this locally storage shared pointer to item number0。

 and we're putting that in the container so items just has zero right now。

 then we're adding item one through four。Then what we have is。Oh yeah。

 I remember this was kind of ugly。 But the， the idea is that we are， we're processing the back。

Four items of the container here。Yeah， and then we're done there and we can see the effects of that。

Counsil output。0 through three created， so that's0 created here。

 and then up through three created in this loop here。 Then we get a new line。

 We are processing item 3。So what we're going to do is we're going to process the item and we can see that。

Items do back， which is a shared pointer， is copied into this temporary shared pointer item object。

 Then we're popping the back of it， and we're returning the temp variable。

 which is still referring to the shared pointer that used to be at the back of the container。So。

If we were using unique pointers when we called popback here。

 this temp pointer would actually be pointing to nothing because it would have destructed that object。

 but because we're using shared pointers， the pointer that's returned from process item is still referring to the object Excel itself。

So item returned X is still live and we can see that item 3 is still alive。

 and then only once this returned object goes out of scope and thus there is no more reference in the container and theres no more reference in this local scope here。

 only then is the object destroyed。And we can see the same thing for item two and item one。Item0。

 however， is a special case because even though we had the copy of item 0 in the items container and we had the copy of item 0 in this local variable for loop here。

 we also have the。Unfortunately， I named it local， but we have this this variable here at the top of main that's also referring to that same item zero object so。

The item zero doesn't get destructed when we run through the scope here because there's still something referring to it。

Then after it's done processing， we can see that local item still has the value of zero。

 so we're still able to access it， it didn't get destroyed just like we talked about。

And then only after this， the main function exits， does that final reference go out of scope and we can determine that the object is no longer being used so it gets delocated。

So another question， if I declare two unique pointers to the same object， you get a double free。

 but using shared pointers， you would be fine yep， and that's kind of the whole point。And in fact。

 this is the whole reasoning behind this next slide here， which if you try to view it on your own。

 it will look terrible， but that's because it has a lot of animations which are going to help with this。

So。We have same class as our last example。 we have our item class so we're creating a new item and we have a shared pointer that refers to it。

 Here's what's going to happen。 First thing that's going to happen we're going to create a manager object。

 So the manager object is not the item object itself and it's not the shared pointer object itself。

 It is something else。 It is an object created by the shared pointer class to manage your item for you。

So。The the manager object is going to create the item itself。

 and it's going to keep a raw pointer to it。And then whenever we have a shared pointer that refers to the object。

 it's actually going to refer to the manager object。

 And the manager object is going to intelligently keep track of how many references there are to it。

And because we've defined the Sha pointer class ourselves or because the C++ standard library defined it themselves。

 that's something that can be easily done， you can easily keep track of how many times shared pointer copy constructors are called。

 how many times shared pointer constructors are called very simple stuff。

So right now we can see we have one reference to our manager object， so just pointer one。

 the only reference there。Pretty straightforward。Now let's say we have pointer two。

 which is copy constructor from pointer1， How does this change what we're looking at？Well。

 we just have another thing that's referring to the manager opt and we can see that we now have two references instead of one。

And。Oh yes， this is a big point here is that even though we're pointing to the manager object ourselves and we're not actually pointing to the item object。

The the dereference and the arrow operators are defined to give you the raw pointer versions of those operators。

 which is very convenient， it would be very annoying to do dereference pointer one。

 arrow raw instead of just dereference pointer one。So。Yeah， I think that's a huge。

 huge selling point of using shared pointers。So we do another thing。

 let's say we do copy assignment this time， we just have another pointer that refers to the manager object。

 now we have three references。So let's say a pointer two goes out of scope。

We have references are now just two because in our deor。

 we could tell that the managed or in the destructor of the shared pointer。

 the reference count was de。Dremented， my goodness。Then if pointer1 goes out of scope。

 you'll see it happens again。Then pointer3 is going to go out of scope。 And once this count hits 0。

We know that there's no way for anybody to access this object ever again。

 because if we have no reference to it now， we have no way to create a new reference to this。

 So we are free and clear to clean up the data。 So what's going to happen is the object itself is going to get cleaned up and then the manager object is going to get cleaned up。

So， that is a。Just drawing example of how shared pointers are implemented。Any questions for that。

Is there an in place equivalent for making let me get some pointers back up here。

 Is there an in place equivalent for making a shared pointer like how you can use in place back on a vector and pass in parameterss for the item C That is a fantastic question Yes。

 there is and it will get rid of this ugly new that we see here。

 It's called make shared and I will talk about it in like two slides。 It's fantastic。Okay。

 so any problems with Sha pointers， I guess before that，ll we'll talk about this。嗯。Another question。

 how much overhead actually is there with using shared pointers over manual management？So。

I guess the， my answer would be it's not that much you， you have。Just off the top of your head。

 And this is to be clear， this previous example that I showed。

It's not defined by the standard how smart pointers have to be implemented。

 This is just the way that I was taught that smart pointers are implemented。 but a compiler。

 any given compiler is free to implement it。 however they wish so long as it you know achieves the same functionality But in this example。

 if this was how smart pointers are implemented， we would just have one more new allocation for the first time an object is allocated。

 So so we have new item 5 here。 we would not only create the item object。

 but we would also have to create the manager object。 So thats that's something that's you know。

 it's one more new call that might be you know， something that you want to to make a note of And at the same time in every copy constructor move constructor。

Basically， in every one of the big five， you're going to have to do some kind of work on the reference count here。

 So for shared pointer。I mean， in the in the copy constructor。

 you're going to have to increment the rough count in the default not the default constructor in the。

Normal constructor， which takes on the raw point or you're going to have to increment the ref count in the destructor。

 you're going to need to decrement the ref count and potentially clean everything up。So。

 although it's。Basically， you're just going to need to do some pointer increments and decrements here and there。

 and you're going to do one extra allocation at the beginning。

 but I would say it is a cost that is not that much。It's not that high a cost to pay。 and most。

 I think production level。Programs would prefer to use smart pointers over raw pointers because。

Raw pointer bugs are nasty。Hopefully that answered the question。

Okay so another example where we have potential problems is that if we have。

 let's say this person class which has a shared pointer referring to let's say the best friend and then in Maine we say we have some some people objects here which oh yeah。

 this is make shared and we'll talk about this in a second but we have person object Albi。

 we have person object Jade， person object Nikkil， person object Mina。

 and let's say we set their smart pointers or we set their shared pointer for best friend to you know。

Some other， some other person in that group。The question is， is there a problem here。

 So this is probably。A tough question to answer， but does anybody see a problem with the setup we have outlined here。

Riv Nikkila。Okay nobody， nobody set。 Nobody set him as a best friend。Yes。

 I think Gabe hit the nail on the head in that we have what are called circular references here。

So if we remember our definition of Sha pointer that we。I guess created earlier。

 we only destruct objects when they have nothing， no Sha pointers referring to them。

So even when Al BJ， Nkil and Mina got out a scope。We're still going to have the internal。

Shared pointers， referring to。Referring to them。 So they may or may not have other people or other。

Other smart pointers still referring to their personal objects。 That is a terrible way of wording it。

 So I'm glad that I drew a picture to demonstrate exactly what I'm talking about。😊，So。

Here is the picture that we can。That we have from the given code from mainine。 So we have our。

We have our pointers， which are referring our local variable pointers in main。

 which refer to each of these objects。 And then we have the shared pointers themselves。

 which are referring to the objects， But from within other person objects。 So， of course。

 Nikkiil's shared pointer refers to Mea， Mina's refers to Ale， yada， yada， yada。

So when we leave Maine。We can think of these pointers as destructing。And again。

 because we don't allocate these person objects in main。

 these person objects themselves aren't going to destruct。

 we only have these shared pointers which are going to destruct。So the pointers go away。

 the reference counts all get decremented by one， but you can see that none of the reference counts well。

The kills reference count as zero， so he ends up getting destructed。

Which not a great thing to just say。 Minina ends up getting destructed because Nkil's pointer is no longer referring to Mina。

And then we have the problem here where Alb and Jade are referring to each other and。

There's nothing else we can do， they're never going to get destructed because they each still have one pointer refrained them。

So。This， as Gabe mentioned in chat， we have a cycle of Sha pointers。

 which means that the rough counts are never going to hit zero。

 the manager objects are never going to invoke their instructorors and these two person objects are going to be leaked and this is a memory leak and you can imagine how in a larger application if you were to maybe run something for a long amount of time。

This could be a problem where you'd end up using way， way， way more memory than you need to。So。

The problem with the previous example is that we don't really want the best friend pointers to have ownership over the person objects they point to so my rationale in English language for this is if you know if the person no longer exists the the idea of somebody being their best friend shouldn't really keep that object around anymore we should more more accurately say that like their best friend you know is no longer in scope。

嗯。Maybe that's a little bit morbid to use person example there。

 but let's ignore that for the time being。So standard weak pointer or stood weak pointer。

 as somebody mentioned in chat， solves this problem。Weak points don't contribute to the rough count。

 so they don't keep the object alive， but they can tell you when the object has been destructed。

Smartly leaving off the word destructed there from that sentence。

So whenever we don't want to assume ownership of an object。

 we use weak pointer instead of shared pointer。 And of course。

 this is usually only relevant in cyclical reference cases。

 but there are maybe other examples from when you want to use them。 So back to our diagram I've。

Ignoreed the first two animations because they were paying to do。

 But if we have shared pointers and weak pointers， we can see we no longer just have one ref count。

 We actually have a strong reference count and a weak reference count。

So two strong references or two shared references， one week reference。

And we'll see what happens when everything goes out of scope here。S pointer goes out of scope。

 we now only have one strong reference， S pointer 2 goes out of scope。

We have zero references and when we have zero references， same as before。

The item object itself or the raw pointed to object itself actually is still destroyed。

So what that means is if we try to access the object through the weak pointer。

We are not going to be able to。And this is good。 This is exactly what we wanted。

 because in our previous example， this would mean that Alb and Mina would destruct or Albian Jade。

So now if the weak point goes out of scope。The manager object is going to destruct。

 but it's important to note that it wasn't it did not destruct before the weak pointer went out of scope。

So when we still had a weak point of referring to the manager object， we could still tell that。

You know there wasn't there wasn't anything pointed to by the raw pointer so we could tell that the object has been destroyed and that's that's important you're going to find out when we use it later。

So that's the the gist there。 If we have no references at all， we clean up the manager object。

 but as soon as we only have or as soon as we have zero strong references。

 we clean up the manage object。Cool， so if we go back to our previous example。

 let's say our weak pointers are dotted lines and our strong pointers or shared pointers are the bolded lines。

So we leave Maine and another note from， I guess E280 here is that the destruction happens in the reverse order。

 the construction so。Mina was constructed last， so she will be destructed first so。Her pointer。

Oh yes， and you can just assign shared pointers to weak pointers。

 they are implicitly convertible like that。嗯。Doesn't that mean that the manager question。

 doesn't that mean that the manager objects would leak in the previous example， yes， yep。

So not only would the person objects in the previous example leak the manage objects would as well。

And that's something that I didn't draw on the diagram because that would require four more boxes。

 which would be a little bit annoying。Are we going through all the topics today。

 Are we stopping at smart pointers。I'm planning on going through all the topics， and。

I think after smart pointers， they get significantly easier。 so I will， I will pick it up。

 but I don't plan on taking up。You know， more than maybe。Three hours。 so if it goes beyond that。

 then I'll probably leave it。Anyways， continuing， Mina gets MEa pointer goes out of scope。

 so no more shared pointers referring to MEa， so Mina， the person object will go out of scope。

And thus， Nikkiel's weak pointer will be able to detect that there is nothing there anymore。

 and we'll see later how that's relevant。嗯。Then Nkel's shared pointer goes out of scope。

 so the Nkel Per person object is cleaned up， then you know Jade goes out of scope。

 we can see that even though there's a weak point referring to her。

 that does not affect that the person object is cleaned up and then similarly。

 Alby goes when there's nothing referring to him。Cool， so last few notes。

 you can use them pretty much like you can Sha pointers except for you can't actually access the referenced item with a weak pointer。

You must create a shared pointer from the weak pointer to access it and weak pointer lock is the function you want to use to do this if you have a weak pointer and you call lock on it。

 it will return a shared pointer to the manage object if the object still exists。

 but if the object doesn't exist anymore， then you'll get a null pointer。

 which is very useful if you want to determine。You know， if the object still exists or not。

 and if we were using raw pointers， obviously there's no data under the hood for a raw pointer。

 so it has no idea of knowing if the thing it's pointing to is has already been cleaned up or not。

Another question from chat， why doesn't delete automatically set pointer Sul would be super convenient？

I agree。 And the answer is just that， again， that's one more。One more slight。

Annoyance for maybe folks that want extremely performant code。

 because even though it's only one line， it is a。It is an assignment that is technically unnecessary。

 so I'm sure a lot of a lot of folks writing extremely performant code don't need that extra line of code in there yeah。

So real quick usage here， let's say we have a weak pointer， this is just directly from CPP reference。

 by the way， this example。So what we're doing is we have I skipped over the explanation here。

 but we're making a shared。We're making a shared pointer to an integer and we're referring to it through a shared pointer。

 then we're making a weak pointer。And we're calling observe。So in the observed function。

 we can see the use count， which is just getting that reference count that we looked at earlier in the。

In the manager object example， so we're going to see use count。

 I believe it's just going to say one because I don't think that takes into account weak references。

嗯。And again， we're going to use a shared pointer to refer to the actual object itself。

 So we're going to call the lock function to get a shared pointer。 and this is。

Another cute little thing that the left hand side of an assignment is actually what the assignment evaluates to so。

If Gw。lock is a null pointer。Then this whole assignment， which evaluates to SP。

 which is a Sha pointer。SPT will be a null pointer。

 which means that the entire expression will evaluate to null pointer。

 which in the context of a conditional evaluates to the boolean false。

 so this is actually the same thing as saying autoST equals Gw do lock and then if SPT is not a null pointer do the following pretty cute little thing and then my favorite thing in all Ss plus which is you can actually do。

You can kind of do two expressions in an if statement， I believe as of C++ 14。

 I could be wrong about that， but you can do an assignment or just pre some preexpress。

 some preassignment to the if， and then you can specify a second Boolean condition afterwards and that will determine the second condition will actually determine whether or not the if is taken or not。

And better yet， this is totally unnecessary to know。

 but this SPT object will be destructed after the if and any coming elses。So。

Totally relevant to know。Anyways， so console output。Use count is one， the first time we call observe。

 so that makes sense we have one shared pointer referring to it and we can dereence it once we get the shared pointer。

 we can see 42。Then after this inner scope in Maine， the shared pointer goes out of scope。

 So the object。The 42 object itself is destroyed。 and the second time we call observe。

 you can see that we have zero use count and。When we do this conditional。

 the manager object tells us， hey， that object doesn't exist anymore， so we say GW is expired。Cool。

 I am going to skip this， but the gist of it is don't mix regular pointers with smart pointers if you're using smart pointers。

 typically you just want to use smart pointers。As a fun exercise。

 try to think of some bugs for how you could come up with that。

And this is the brief explanation of make Sha and make unique is。Instead of using naked news for the。

For the argument to a shared pointer constructor， instead。

 what you can do is you can construct a pointer from this make shared function call。

 which is also annoyingly templated， but you just need to give it the arguments to the constructor and it will。

Create the shared pointer for you and。It will first。

 I guess the make Sha call will create the item objects itself。

 and then the Sha pointer constructor will create the manager object and you'll have all of your memory management set up for you without having to call new or delete explicitly anywhere in your code。

So this bottom line of code is typically how you would see shared pointers。Declared and used in code。

Al right， so skipping head a little further。 RII， I'm going to touch on this super briefly。

 but the idea is。For any resource in general。We can use C++ as guarantee and other languages have this guarantee too。

 but C++ has a guarantee that any time objects are constructed in a scope。

Just before they go out of scope， their destructors will be inserted in the reverse order in which they were initialized and the main part is that destructors will always be called when an object goes out of scope。

And they will always be called right at that exact point and we can use that to you to do some pretty nifty things and this idea is called RAII where in a constructor we acquire some resource and the destructor we free up that resource and it's a pretty nifty pattern you'll see it used in plenty of other things in particular if you take 482 you'll see it with lock acquisition and lock freeing。

Here's a really nifty example， I think。 So let's say we have some。

 some sea out flags that we wan to set， I think， in projects。I guess just project4 actually。

 we we have the precision for C out set to two so we don't print a bunch of decimals on the end of your tours。

So say we wanted to set that precision， but we only wanted to set it for one function。

What we could do is save the old precision， you know before we change it and then after we change it set it back。

 but a more fun way to do it is to write a class that does it for you and in the constructor we are going to store the old flags and the old precision and in the destructor we're going to restore the flags from what the old flags were and the precision from what the old precision was。

So in this function， clearly， we want to mess around with the precision and some flags。

 So we're going to first declare a see out format saver， which is going to store。

Whatever see out settings were at this line of code。

 then we're going to change them and then as soon as this function returns right at this curly brace down here。

 we're going to restore automatically via the deor of C out format saver。

 the old settings are going to be restored， which is pretty nifty。And additional。

 another justification for using RAII is that it's exception safe and that des are called even if the frame is left through an exception。

Even if we have some function that could throw here。

 we can rest assured that no matter how we leave this function。

 our old settings for our sea out formatting will be restored。So skipping ahead。

 this is not important at all。 Let's look at Lambdas in the functional library。

I'll pause for like a minute to see if anybody has any questions。 But other than that。

 we will be moving ahead。Gu。All right， so let's look at Lambdaos in the functional library。Oh。

 I thought exceptions caused des to not run， or is that exit one？Exit one， I think。

 is what you're thinking of。And I actually。I recently learned。Actually。

 I don't know enough about that to even say what I was thinking， but exceptions， exceptions always。

Triggered destructions of local variables to run。 That is a。Guaranteed thing that you can rely on。

Exit one， I believe does not， but I mean， if you're using exit， the exit function at all。

 you probably don't really care about the state of memory in your program because you are about to exit the program。

嗯。Yeah， but that's generally seen as bad style。 You generally want to。

Kind of end your program from the same spot。 And one way to do that is by throwing a throwing an exception all the way to the top level of your code where you can。

Handle it if you want to。Is exit one any different than return one from Ma？Yes， for the。

 for the reason， actually， I just mentioned and possibly for other reasons。

 But if you're returning one from Maine， that means that you are。

Destructing all of the local variables for。For the current frame， and at the very least。

 that's the the main frame or the frame for the function into main。

But if you were to exit one from main， then the local variables to main would not be destructed。

And if you were to call it from a different function， say those locals would not be deed either。

Why does it matter if we destruct variables if the program is ending。

 Does't a program ending mean all of its memory will be delocated。

 That is a question that I do not have the knowledge to answer。If somebody。In chat has an answer。

 then。That is probably more than I know。 my answer is。Good style， I don't know， maybe。

 maybe there's a reason but。I don't exactly know it。Yeah， no problem。Yeah， okay。

 so let's look at lambdas and a little bit of the functional library。

 But I expect I will skip the functional library stuff。So lambmbdas are just anonymous functions。

Sometimes we write functions that we only use in one place， and。We don't need to give them a name。

 We don't， we don't necessarily need to you know， put them at the file scope。 We。

 we usually just want to in these cases。We just want to have a function that we're going to use once so if we do。

 then why don't we have a way to define these functions in line？

And I think a great justification for this would be we've written a lot of comparators。

In the projects in this course and these comparators are usually only used in one place。

 so if we want to， why don't we define these comparators right in line So if we have a standard sort call。

 why don't we define the comparator right in the standard sort call and Lambdas allow us to do that basically just shorthand for writing a function and you can do them in line which is super。

 super convenient。Yeah， and S++ doesn't allow you to create functions within functions。

 other languages do allow you to do that。I would say like notably Python and JavaScript are very。

Geared towards that sort of thing。But S++ does not， so if we wanted to create a function。

 we would have to do it outside of the current function scope。

 which is going to potentially pollute the namespace。

So Lambdas are anonymous functions that can be defined and used similarly to function objects。

Anonymous because by default， they're nameless and they are usually not stored。

 but they can't be stored， I guess。Gabe says is。far as I know。

 it's not super significant for programs that terminate what this matters most is for programs that run for a long time like an operating system。

Yeah， that makes sense to me。嗯。I guess especially if you had。Sub processes。

 so if we have an OS that has a ton of other processes that are running off of it and the sub processes exit。

Maybe because the main process is still running。Those sub processes， memories， memories。

 the memory of those sub processes not getting cleaned up would maybe have some effect。

That makes sense。 I could accept that justification。Okay， so lambmbdas。

 here is the anatomy of a lambmbda， which I think is super， super cool。

We have first in square brackets， something called a capture list， then in parentheses。

 we have the parameters to the function， then in the curly races。

 we have the body to the function and everything except for this capture list out front probably looks more or less like a normal function。

And the capture list is you can kind of think of it as being member variables that the lambmbda has so。

If we're thinking about lambdas as function objects。

You can think of this captureist as kind of being a constructor that takes in and stores some data that the body of the function can use and modify as it wishes to。

And we'll see later that this is actually a lot more powerful than just。What it seems。But yeah。

 we'll look at that later。 So if we have this function here， like I said， we have a comparator。

 you know， we just。Have some items， some item， and we just want to return if the item's x value is less than the other item's x value。

Um， we would have some comparator function that's outside of the current frame， like I said。

 and we're just going to pass it to standard sort。But the way we could do this with Lambdas is。

We define a lambda right in line， right in that sort call。

 which takes in the two items and returns the proper。Proper thing as a result。

And you can see how this is much cleaner。 and specifically now this comp funk function is no longer。

In this file scope， when it definitely doesn't need to be because we only are using it in one place。

So a little bit more on capture list。Yeah， these are definitely one of the weirdest things in C++。嗯。

This is not， I would say not super important to know， but if we want to go deep into captureists。

 take a look at this slide， there's a stack overflow post that I've linked in the notes for these slides。

 but for now I'm going to skip this and I believe I'm going to skip the next few slides as well just because they're not super important。

And that might bring us to the end of Lambdas。 So if anybody has any lambmbda questions。

 feel free to ask them now。I guess first I'll talk about trailing return types。

But if we go back to our anatomy， remember we have our square brackets。

 then our parentheses for the parameters， then we have our curly braces for the body。

 and we never specify a return type there， but we do have to specify return types for normal functions。

What's the deal there how how come how come we can't get away with doing that for normal functions。

 Why do we need to specify return types。嗯。The answer is just that normally Lambdas are simple and normally they only have one return statement。

 and normally the compiler can very， very trivially determine what the return type of lambmbda is。

But unfortunately， as this bullet point says this is not always the case。

 So if we have a function even as simple as this where we have we're taking in a double and if d is less than0。

 we're returning0， otherwise we're returning D the compiler is going to analyze this and it's going to see this zero。

 it's going say h we're returning an in in this case。

 but in this case we're returning a double So it's going to throw its hands up and say I don't know we're supposed to return here。

This isn't going to compile。嗯。So yeah， Elen's pointing out in the chat that yeah。

 we could definitely just say return 0。0 and this might work。

 I'm not actually sure it might actually the compiler might take a look at this and still see two return statements and throw its hands up。

But either way， sometimes it's not as easy as just adding a 0。0。

So what we actually need to do is add a return type explicitly with the trailing return type。

 which is， in my opinion， ugly。So you can do this for any function， by the way。

 if you want to specify if you've ever seen an auto return type on a function and the return type specified after the parameters。

 but before the body that's the same thing here you can just do the little arrow after the parameters and specify the return type and from there the compiler will be able to tell okay。

 cool in both of these cases we're returning a double。

 I'm happy with that and then it can do the rest of its type checking like S++ normally does。

Workorse。Great。Oh yeahep， and here's the S Overflow post I was talking about。嗯。Yeah。

 one more weird thing about Lambda is you can。Capture。That's not right。

 It's just the auto type to store something， but you can actually capture a lambda in a variable。

 which is super， super interesting。 And usually， you don't really have an easy way in C plus plus of storing functions and variables。

 You normally have to do。Weird stuff with function pointers or with the functional library。

 which are going to be in the slides that I'm not going to go over， which are right after this。嗯。And。

Anyways， with a line of code like this， if you have some variable that has the auto type。

 you can actually assign a lambmbda to it。And from there。

 you can call that just like you would call a normal function。 and this is actually super。

 super interesting。 and you can you can get some really fun code out of this where say you only want to say you have a lambda that you want to call twice in the same function。

 but because it's just in the same function， you don't want to create a function out of line to do it。

 you can just create a lambda， store it and then use it twice within that function very nifty stuff in my opinion。

If you want to go more in depth about all that capture list stuff that I talked about。

 I would recommend reading the stack overflow post。

 It's honestly fantastic and it goes over probably everything you're gonna to need to know。

And here's a great line of C++ code。What's happening here is we have our capture list for a lambda。

 we have our parameters for a lambda。 we have the body for a lambda and then good question in chat。

 what's this last parentheses， This is just calling the lambda。 So like any other function。

If you go to call the function and you need to call it with the list of parameters that you want the function to receive。

 so if you look up here to where we're calling function。

 we have to call it with parameters and we have to give it five because it takes in an int。

But because we're defining and using it on the same line here。

 and because it actually takes in no parameters， we can just pass this temporary lambda object。

 no parameters， and it will call this lambmbda。So this is a line of code that effectively defines an anonymous function that does nothing and then calls it。

 which effectively also does nothing， but is pretty funny。Cool， so this is all I've got on Lambdas。

 and we have some more stuff on the functional library that I am going to regretfully skip to be clear。

 though， I think this stuff is not super important at all。 If you want to do functional programming。

Honestly， C+++ is probably not your language anyways， you probably coding and。I don't know。

 something Lisp eque or something Python Eque。So I'm going to skip over that Any questions？

And just to be clear， these first， I guess the first two topics were by far the longest。

 these last ones are not nearly as long so。I'm expecting we be pretty。Pretty fine。

Our lambda is pretty much the same as using block scoped， struct funcctors。I would say yes。

So you cannot define functions in line， but you can actually define classes andstructs in line。

So if you want to， instead of using lambmbda， you can definitely define a。

A function class which you know， has parentheses operator and has a constructor。

 which maybe takes in some data and modifies it。You can do all of that and put it in a block of code and then just use that functer and that will give you。

 you can always get the same effect from a functer as you can from a Lambda and I actually believe under the hood that Lambdas are just implemented using function objects so yes。

 you can you can pretty much do the exact same stuff。Cool， so verytic templates。

Basic idea of verytic templates are it's a template or it's a function that can take in any number of arguments and。

The idea is that in the body of a function， we're going to process some number of the arguments。

 and then we're going to recurse with the remainder of the arguments。So。Already。

 let's just take a look at some code because I think this is the easiest way to take a look at what's happening here。

 One， I guess， question really quick for you guys。 Can you guys see my mouse when I'm like mousing around on screen or not。

Yes， cool。Awesome， I was relying on that earlier for like pointing at stuff。

 I'm glad to glad to see you can。😊，Okay， so let's look at this bottom definition here。We have。

We have a template which is necessary for this， even if we know what the types of the function that we're going to receive are。

 we need to template this function。So we have specifically。

 we need to template the veryatic argument， which I'll talk about in a second。

But we have in this print function， we have the first object， which is。Some， some object of type T。

 and then we have this object as of type as dot dot dot。嗯。

And this is not really something that you're going to see anywhere else， this dot dot dot syntax。

 and it's just reserved for this specific case of what C++ refers to as a parameter pack so。

You you can think of this as storing the rest of the arguments to this function。

 but the first argument is kind of pulled out into this T first parameter。

So what we're going to do is we're going to print the first argument just normally。

 just print it with whatever the operator，arrow error or the operator less than less than a。

What's actually going to do and then we're going to print a space and then we're going to recurse with the rest of the items。

So important thing to note is that because this args item is of。A veryatic type。

 so it has a bunch of types stored in it， we need to unpack it before we recurse on the next one。So。

Thing to note， let's just look at the example here。

 if we print four different things with this example。

 what's going to happen is the first time we call this function。

 we're going to get this first item is going to be equal to the a string literal。

 then ArgG is going to have the int5， the int3 and the string literal apple in it。

Then the second time we recur with Args or we recur on print。

 the first item is going to be the in5 and then Args is going to have three and apple。

 and you can see how that would work。Till the end。 And one thing to note is that you do actually need this base case of。

Where there's only one item and no。No ags。Actually， now that I'm saying that。

 you might not need to so。One thing where I don't actually know。

Completely down to the last detail what's going on here。

 But you might be able to get away with not having this definition。

 but it is important sometimes because in this example here。

 we want to print the new line at the end。 So we actually do want a specific base case function。

But I don't know， play around with it for yourself if you want to see if you can get away with happening an our glist that actually has nothing in it。

嗯。Oh， and actually。Totally disregard that I think you do need it because if we were to call print on Args dot dot dot。

 but As had nothing in it， then this would surely cause a there would be no matching function call for this so。

Yeah， I think that would that would be how that works。Question from chat。

 just to solidify my understanding is one plus2 in the main function in R value。

 whereas the three that's being printed in as and L value。Yeah， okay。 so yes， this one plus2。

This one plus2 is an R value。 Yes， like you said， and the three， which this evaluates to。

 is also an R value。 But as soon as we enter the context of this function。

As soon as we give that value of three a name， yes， you're correct， it is an L value at that moment。

 so similarly this a here， just because it's the first one and it's easier to explain this。

 this a here is in our value， but as soon as you know it becomes this value first。

 it becomes bound to this variable first in this function than yes， it is an L value at this point。

Cool， yeah， good question。So this is how bartic functions work。I think I have another example here。

Oh， yeah， I。Past me is smarter than present me。Yeah。

 the code will not compile if we do not have this base case function because eventually we will recurse with zero unpacked args。

 which does not match any function signature。Gol。Glad that I put that on there。

And rather than just doing one function or one argument process in each call。

 there's no reason you can't do more than one。So if we have。

 say a similar function that instead of just printing something， we want to print pairs of things。

Then this was how you would， this would be how you'd set that up。 You。

 you unpack two of the parameters in the first。Not in the first， you unpack two of the parameters。

 and then you have the rest of the parameters stored in this as。

Args parameter pack and you know we print two of them and then we recurse， we have this base case。

 which takes in two objects and print of them and then prints done so if we call it on four items here we're going see the first two are printed together you know the last two are printed together and then we're going to get done because that's what happens the end of our base case。

嗯。Yeah， and the important thing to note here is that all of this like everything in C++ is check that compile time。

 So if there's no matching function call， we will know it pretty darn soon。 So for example。

 if we call this print Paris function with five items。What we're going to get is at the end here。

 this print pairars， wow I misspelled a lot of stuff on these slides。

 but this print pairars recursion at the end is going to recurse eventually with one item it's going to just recurse with sauce and there's no matching function call for just one item passed to print pairs so。

嗯。So yeah， the above code would call。 It doesn't actually call it。

 but it the compilers walking through this and checking what would be called。

 So it would call string int and then。The parameter pack of int string string。

 so that's legal that one checks out， then it would call int string parameter pack of string。

 that's also legal that checks out Those would both match with this bottom definition here。

Then we have the final one， which would be print pairs with just string。

 and that doesn't match with this one and it doesn't match with this one because there's only one argument。

 so no matching function call compiler would detect this and throw an error。Which is pretty nifty。

Cool， anything on veryatic templates？I think that's a pretty brief one。 And if you wanted to。

 I'm sure there is probably one stack overflow post that you could read that would。

Give you all the information you need to know on it。

If you want to hear an actual use case for when I've used Vatic templates。In 482。

 if any of you take 482， you're likely going to want to do a lot of debug printing。And。啊。Also in 42。

 if you want to。If you want to make sure that your printing is deterministic。

 you're going need to lock C out before you do any printing so you can use veryatic templates to。

Write your own Python ask print function that takes in any number of arguments and acquires and releases the lock。

The first time that you。The first time you need it and releases it after the last time that you need it。

That probably won't make sense unless you've taken 482。

Question from chat print F would have to use them， right？Yes， so。Yeah， so the only。

The only thing that's different there is that C per def is as a C function。

 So I don't actually know what the C equivalent of。Viatic templates are。

 but if you were to write print F in， you know， a C plus plus the modern C plus plus。

 you would use verytic templates， yeah。B， I don't actually know what the C version of veryic temples are。

 Maybe they use something like void pointers to get around it。Cool。

 I am stoked to talk about tries because I think tries are the coolest thing ever。

 and this is not a C+ plus specific thing。 This is just a data structure。

Let me get some water real quick。So， tries。They are a node based data structure specifically for storing strings。

And you can。You can extrapolate this idea to store things other than strings。

 but you'll see pretty quickly why they're useful for strings。 They're very simple design。

 They're extremely efficient in insertion and lookup better than hash tables。

 and I think they are just dope and pronounce a try。I don't make the rules I'm just reporting。嗯。

Just reporting what I've been told。So the design of a try， instead of storing words separately。

 we store just characters。 So the words that have overlap don't store duplicated data and an example here。

 if we want to have say we have a hash table and we have we push app into it and we push Apple into it。

 then this APP， this prefix APP is dupd across these two words， we'd be storing APP twice。

 we'd store it once an app and once an Apple and with a try。

 we can get away with not duplicating this data which I think is super clever super clever。so。Yeah。

 this is kind of the， the structure for what I try looks like visually。

 and all we're storing is we're storing the characters and we're storing。

Whether or not each node is the end of a word so in this example。

 we can see that APP is a word because the final P is denoted as a terminal。

 it's the end of a word and similarly APP L E Apple is a word because this E is a terminal node。嗯。

Question from chat， what would the root node in the example， Okay， yeah。

 the root node in this example here。You'll see， but it doesn't。

 it's just a special note that doesn't have a character associated with it。 That's the only。

The only difference here。 And you will see once I give a larger example as well that， you know。

 each of these nodes doesn't need to just have one children， one child。 it actually can have。

Up to 26 children， which is kind of how this whole thing works。Well。

 let's take a look at that in a second。Okay， my animation there was busted。

 but for each letter for each of those nodes in the previous example。

 we're going store whether or not it's the end of the word and we're going to store pointers to the n possible children nodes。

 So usually n is equal to 26 if we're destroying lowercase English letters。

 I would say that's by far the most common use of tries。嗯。

And if you don't have a limited set of characters in your input set， then tries are not。

Really gonna have the value that you would expect。 I think of this as being similar to accounting sort idea where you want the input set to be。

Small in order for this to be as efficient as it can be。Yeah。

 so that's what that bullet point there means。 And then if there isn't a child for any given。

There isn't a child for any of the given。I guess letters， then you don't need to store a node。

 you just store a null pointer， so we can get away with not unnecessarily allocating things。

So let's say we have a children array here。 let's say this is the root node of our tree we have you know。

Pointers for each of the lowercase English letters， and these would all point to child tri nodes。

Or they would be no pointer。And。To me， this makes a little more sense when we see it in action so。

Let's say we insert app into our try and this is the root node。

 so it doesn't have a letter associated with it， it's just the root。

So first thing we're going to do is we're going to allocate the child array to have all 26 slots that we discussed earlier。

 these are all going to be initialized to null pointer so they start off as having nothing。嗯。

But soon you're going to see we're going to add stuff。 So because we insert it app first。

 we're going to insert a into the root。So now we have an a node。And。I guess from there。

 we still have the P and the P to allocate， so we need to allocate this children array。

 and I've nicely carved out a little slot for the P to exist here。

And we're going to allocate a new try node for the P。And similarly， we're going to。

Alloccate another allocate the children ready for the P because it still has another child to go。

 we have another P。And I believe I shrunk everything here， good， good， good。

 And then we allocate this array。 And of course， we need to allocate。The second P node。

 so that's what's going to happen here and we don't need to allocate the children array for this one yet and of course。

 this is the end of a word， so we're going to market as such。And that will。That will。

Finish up this insertion。So what happens when you insert bat。

 you're going to see a very similar thing， we're going to go to the root。

We're going to see B currently has no。No word starting with B from the root。

 so what we're going to do from there is we're going to allocate a new node and we're going to point to it from the root the root children B slot。

Then allocate the children array for the B node。 We have nothing in the A slot。

 which is the next character we're looking at。 So allocate the a node。Then of course。

 similar thing to allocate the final one。Then if we insert Apple。

 we're going to look at the root node。 we're going to see we actually already have something in the a slot。

 So we look at the a node。 We see we already have something in the P slot after that。

 So we look at the next node。We already have another P in the slot after that。

 so we look at the next node and we'll see that there are no children here。

 so we have nowhere to put the L， so let's allocate the children node for this P node here and from there we can create the L node。

 allocate children for that。And then we can create the E node and specify that that's the end of the word。

哦。Hopefully I muted in time for that cough， but you can see how。

The example I've chosen here is kind of like two sticks going down。

 But you can imagine how this would be。You know， there's potentially 26 children going off of each of these nodes。

 right， So if I had。I don't know A word that start what a the word ape right。

 so we would go A P and then there would be an E node here that maybe points to or sorry。

 there'd be a pointer here that points to an E node that would， you know。

 store the E and we would have her word ape as well。So any questions on the idea of a try。

 This is pretty much all there is to it。You can talk about time complexity and stuff on the next slide。

 but implementation wise， any questions。Guo。Let's move on。So complexities。

 and I'm sure a lot of you are seeing this and you're saying， wait a minute， I thought these were。

 I thought these were fantastic， I't a hash table just better than this。😊，嗯。So first。

 let's think about why is this the way that it is insert。

 look up and remove are all O of k where k is the length of the string。So。

This makes sense to me intuitively， if we want to insert or look up a word。

 we need to you know check each node according to the character that we're looking for。

 and then at the very end， the last step would be you know。

 do we is the ending character that we're on the end of a word？Right。

 so if we're looking for the word， I guess let's assume A is a word。

 If we're looking for the word A in this tree， what we would do is we check for A。

 then we check for P。 and we would say， yep， we have a P， but。This isn't the end of a word。

 So the word A P is actually not stored in the try。 But either way。

 the big idea is that we need to check the number of characters equal to the length of the string。

 So O of K， time for that insert certain look up。 that makes sense in removal。

 you could think of this。 Let's see if I drew。 I did。 Yes， So removal。

 you can say find the word and just set the end bit to false。 So if we wanted to remove Apple。

 we could just find the word apple and then set this E to。False。And this， I would say。

 would be a very common way of implementing removal， but。One could argue。

 and I would say positive rightfully so that this is wasteful of memory because if we delete Apple。

 we could actually delete this L E chain on the end of this leftmost chain here。

 So the other way you could do it if you actually want to remove letters is you could recurse back up to try after you found the word and if there's no other children。

 it's not the end of the word for each given node。 So starting with the E。嗯。We would delete the E。

 then we'd go back up to the L and we'd say if there are no other children and it's not the end of the word。

 we can delete the node and recurse up， so L has no other children besides E and L is not the end of the word so we can delete it。

And we can move back up。 Then we check P。 Does P have any other children。 No， it does not。

 It only had L is P the end of the word。 Yes， P is the end of the word。

 so we cannot delete P and thus our。Recursion has done。 and We've removed it。Either way， though。

 at worst， this is going to take O of k to go down the tree and then at worst it'll take O of k to go back up the tree to do this recursion。

 so this is still O of K。And I think， okay， yeah， this is just pseudocode。

 obviously there's edge cases， blah， blah， blah， and no accountability if you implement this and have bunch bugs。

Yeah， this is what I was wanting to talk about， though。

 These are the theoretical lower bounds for a string data structure for these three operations。

 You cannot actually get better than this in terms of big O complexity。

So what I was talking about earlier is that hash tables， we say， are O of one insert， look up remove。

 but。Really， those are。Constant time not counting the amount of time it takes to hash the object。So。

In order to hash strings， you do need to actually access each character in the string。

 which makes them O of K to hash。So really hash tables are O of K for all these operations as well。

 and in practice they're going to be a lot slower than using a try because of the overhead of doing things like you know。

 actually hashing， calling a hash function。So。Things to consider heavy heavy。

 heavy memory overhead because we have an array of 26 pointers per node。

 even though we don't allocate it every time we need to， I mean。

 in this case here for this tree specifically， we have a lot of wasted space our a node。

 actually each of these nodes except for the T and the E have 26 children and they're only using one of them。

So you can think of that as being， you know，8 bys per pointer times 25 times 1，2，3，4，5，6。

 I guess 7 because the root nodes。 so quite a lot of wasted space here， but。Wops。

 I guess that was the last light， but very， very fast。

And if you're into the whole interview questions or maybe leak code or whatever like that。

 which you certainly don't need to be， but I have seen these come up。A few times。

 And I think it's just， it's an interesting thing to know。

Even if they're not easy to code up on the spot， it's something where you can explain maybe to an interviewer that you know a way to achieve X complexity。

See you any questions on tries？Cool， I am going to move on polymorphism under the hood。

 I'm gonna breeze through this。I guess I don't I don't even know， yeah。

 I'm going to breeze through this because I think this is not a super important topic to to discuss unless people are super into object oriented programming。

 so I'll go super quick here。嗯。We， we say that。In hierarchies for any object oriented programming language that the child class object or child class objects are parent class objects。

 So wherever a parent pointer is expected， we can use a child pointer instead。

And this is something that I believe was explained in E 280 as well。

But the main question of this that I want to answer here is， why is this the case。

 What's kind of the under the hood of how does C plus plus implement。Object oriented stuff。

 How do they implement objects in a hierarchy， how are virtual functions working under the hood？

So what what objects look like in general is they are as efficient as they can be。

 they just are the data members stacked up。As tightly packed as they can be。And then any pointer。

That's referring to an object that exists in this fact just points to the beginning of the object。

 and the data members are accessed via just byte offsets。 So ins or 4 bytes。 So we know that。

 you know the first field of any A object is just in the bytes 0 to 4。

The second field will be stored in the bys 4 to8， and then the third field because it's the double will be stored in the bytes 8 to 16。

I chose a nice example here， but if you if you've taken 370。

 you'll know that there are some asterisks with padding and things like that。

 especially if you're not using things that are even fours and8s。So they are continuous in memory。

 sometimes padding， data members are stored in the order specified in the class definition and we access them via light offsets and the pointers point at the beginning already said all that。

So yeah， getting the A2 field will grab by its fourth or rate， great。

So if we have an object and a hierarchy。 So let's say we have a B object that is。

Inheriting or a B class that inherits from the A class。

So a B object really has all of the data from the A object。

 and it has all the data from the B object。So in memory。

 this looks exactly how you would expect it to。 It's just the data members for an A object and then the data members for the B objects right at the end of it。

And still getting the A2 field will just get bytes 4 through 8 from the underlying representation。So。

 this isn't。There's no like there's no difference between an A pointer and a B pointer in this way。

 and this is why we can say that you know， our child class pointers are just parent class pointers because quite literally they both point to the same spot。

So there's no， there's no reason that if you wanted to do anything on a B object that or sorry。

 anything on an A object that you couldn't also do it on a B object。

 And I think the easiest way is to just know they literally。

 the pointers literally point the same spot in the object。Great， so that's， that's that。

 I think that's very simple。Virtual functions。I'm not going to get super in depth of this basics of virtual functions。

 you're going to， if you call a function。Through a pointer and the function is marked virtual。

 you are going to get the most derived version of that function。

So this is maybe something you remember from 280， but if not。

 you can take a look at that slide after and get a feel for it。 I'm not gonna go over this example。

 I do have the output there if you want to take a look at it。

 And I believe in the rept that I that I linked earlier。

 I have a similar a similar thing there where the the example is listed out and you can play around with it。

So how do virtual functions work， what's the overhead？

The virtual function table is how C++ implements。Virtual functions and the big idea is that each class has a table of the virtual functions that it defines and for each object in the class hierarchy。

 we keep a pointer to that table。Yeah， and the pointer initialized behind the scenes during construction。

 and it points to the V table for the most derived class so。Let's look at an example for this。

 because I think this is， this is how I work best。 And I think this is how this stuff is best explained。

 So let's say we have our A struck and our B struck again。 But this time we have functions。

So let's say we have in the parent class， the base class here。

 we have a virtual function foo in a virtual function bar， and then in the child class we have Fo。

 which is， even though it's not marked virtual， it is overriding the parent class version of Fo。

 and we have a new function BS， which is marked as virtual and B。

So here's what the V tables would look like for these two classes， so the V table for class A。

 it's going to have an entry for P and an entry for bar because those are the two virtual functions that it knows and for B。

 it's going to have one for F， one for bar because that's what it inherited from class A and it's also going to have one for badS because that's the one that it declared in its definition。

So this is what the V tables look like for these two classes。And if we look at。

You know what an object looks like。What a C++ object in a hierarchy looks like if any of those objects in the hierarchy have virtual functions。

This is what they're going to look like now is that we have this V pointer。

 this hidden V pointer field， which is actually the first data member of the object itself。

And it points to the correct V table。Given the object， so let's say we have an A object here。

We're going to have just the data members for the A class and we're going to have a V pointer that's pointing to the V table for class A。

So because we have an actual base class object here。

 this isn't really that fancy because if we want to call fo。

 what's going to happen is we're going to look through the v pointer we're going to see which version of F should we call and of course it's going to be A's version of F because we're in the base class there's no derived class version to use and similarly if we want to call bar we're going to look through the V pointer and see which version of bar should we call and we're going to call A's version of bar。

Where it becomes interesting is when we actually do this with a child class object so during construction the v pointer is going to be initialized to point to B's V table so we still have all the data members stored just how we expected for the previous example。

 but now if we want to we' want to call a virtual function of the hierarchy what we do is we go through the V pointer and we can call the most derived versions of the functions so。

嗯。You say if we want to call fo on a B object through a pointer。

 so it has to be a virtual function call， go back a few slides if you want to see exactly what a virtual function call means。

 but if we're callingF virtually， then we're going to see that B's version of F will be called and if we look at this。

 this is actually correct because it's a virtual function to the base class and we overwrote it in the derived class。

And then for bar， we're going to get A's version of bar because it was marked virtual in the base class and we didn't overrideite it in the drive class。

 so that looks good too， and then BS， which is the new entry which we didn't have in A's V table。

Which is， of course， going to get our be defined version of BS。

So this is how that is all implemented under the hood。

 The important thing to know is that these compile or these V tables are generated at compile time。

 so just by looking at the code。Without creating any objects or generating anything。

 just by looking at the code， the compiler can tell exactly what versions of each function should be called for a given class。

And that makes sense because you always want to pick the most derived version you have access to and you know。

 if we have a B object， we can tell right away we want to use the versions。

 we want to use the B versions for everything it can。

 otherwise we're going to use the A versions for everything we can。

 otherwise you know if there was another base class， we'd use those versions for everything we can。

So that's how this all looks under the hood。This is the engine for super plus polylymorphic function calls and the run time overhead is just a pointer de reference and an array access。

 The memory overhead is that we do need to store an additional pointer per object， importantly。

 though。If you have if you have some kind of class hierarchy that doesn't use virtual functions at all。

 then there's no V pointer stored， so you're not losing anything by。

Just having normal class objects in a hierarchy。Cool， this is also in very two plus plus fashion。

 this is very efficient。I think other。For example， Python， virtual lookup， not virtual lookup。

 but Python like。Polymorphic function calls， it works more or less through a runtime maintained dictionary。

 which is just a hash table。 So in Python， what would happen is let's go back to our previous example。

 I guess in Python， what would happen is。Instead of a V pointer。

This object would have a dictionary of names to functions。 And if we wanted to call foo， it would do。

 you know。Functions dot find or whatever the hash table lookup would be functions， square brackets。

 foo， and that would return the fo function that should be called and then it would call that fo function。

 which is notably slower than just doing know a point of de reference in an array access。Anyhow。

 not knocking Python because there's。Plenty of practical reasons why you'd want the run time function dictionary that they they use。

That is certainly not a topic for today。And then super， super briefly。

 anybody anybody has any questions， Feel free to drop in the chat。

 And I'm trying to speed through this Liy split。 Super， super briefly。

 structured bindings and C+ plus。 This is just a quality of life thing。

 This is not gonna change your code significantly。 It's just。

It's just a fun little thing that you can use to。You know。

 make your code a little more readable and a little less nasty。

So if we want to return multiple values in C++， like in Python。

 what you can do is you can return not just Python in a lot of other languages， but as an example。

 in Python， if you want to return multiple values， you can do something of the form return you know one comma2。

 and it's going to return two values， the value one in the value2 and you can do this for any number of values。

 they don't even have to be the same type， it's great， it's fantastic。

And C++ this is not possible if we want to do something like this。

 we would have to do something ugly like declare a st tuple of int comma int and then return the tuple with like return。

 make tuple of one comma 2。Pretty ugly， I don't think it's that gray。

 but it's as close as we can get in C++ without using structured bindings so we can come pretty close to approximating multiple return values if we use structured bindings instead tuple。

嗯，是样。If you wanted to do multiple return values before structure bindings。

 you could do any of these things which are all sufficiently ugly in their own right。

But if we have structured bindings， then what we can do is we can return a tuple like object and we can unpack it on the fly into a bunch of different variables and with this we can have a budget version of multiple return values。

Here's the anatomy type， then we have square brackets and we have name of the variable。

 name of the variable， dot dot dot as many variables as you need。

And you are going to assign a tubple like object into it。So。

Normally this is going to look like auto and then a list of variable names that you want to create for these tuple objects。

 so this is a I think a great example here。I think these are actually all from CPP reference。

 if I'm remembering correctly。Yeah。So the insert function for hash tables returns an iterator to the inserted object and a boolean determining whether or not the insert was successful。

So what you do。What you could do is because that is a tuple。

 you can assign it to this structured binding， which has the type auto and it's going to initialize this it thing。

 which is not yet a variable， but after this line it will be a variable。

 it's going to initialize the iter with the iterator pointing to the newly inserted object and it's going to initialize success with the Boolean denoting whether or not the insertion was successful。

So these don't have to be the same type or anything。 We're using the auto keyword here。

 Iter is now a stood iterator。I mean， specifically， it's going to be as stoodud。嗯。

Whatever unordered map of string to， I don't know， enter something call and call iterator。

 but it's just an iterator and success is going to be a boolean。

So we can do that with anything that looks like a tuple。We can also do it with astruct， which is。

 I didn't know you could do this。But this is pretty cool。

 you can declare somestruct object and then by reference you can capture new or by reference。

 you can unpack sort of T's fields into these new variables HM and S and then you can set if you set H in this current frame。

 it's the same thing as setting T dot hours， which I think is pretty cool。And then similarly。嗯。

Kind of the， the idea I just talked about if we we have a function that returns a tuple， we can。

We can make variables which correspond to the return value of the function using structured binding。

Alright， this can also be used to unpack array values， just other stuff。 All in all。

 though this is just a nice quality of life feature。 There are not many of these in C+ plus。

 in my opinion， so we take what we can get。Cool， so that is finally。Let's see what we clocked in at。

Just over two and a half hours。 I guess that's not too bad， but。Still。

 an excruciatingly long lecture of。Extra stuff in C++ that you may or may not use。

 but I think is at the very least very interesting。So any questions at all。

 feel free to fire them off， but totally understand that this is a long one and。If that's it， then。

 I mean， I hope you all had a great experience in each 21 and I wish you all the best of luck in your future classes if you're graduating。

 congratulations， I wish you the best of luck in whatever your future holds。And yeah。

 for the rest of you， maybe I'll see you on campus in fall of 21。Yeah， thanks。 Thanks， everybody。

 Thanks Ewe， Andrew。William Merrt， yeah， one question， where did I learn all of this so。

I would say that I learned。Man， let me let me look at the agenda really quick， actually。

I can give you， I can give you an exact breakdown。So。Move semantics， smart pointers， RAIi。

Lambda is in the functional library。 I learned all of this in。I learned these。And these in Es 381。

Which is not offered anymore because the professor， Dr。 Curs， actually retired。Fantastic class。

 a ton of work， though， and。Yeah， nobody else wanted to teach class because it was so much work for the professor that I don't I don't think it will be picked up again in the near future。

Yeah， so another question billing on that you mentioned 31 before。

 do you recommend going through the previous course content as the class got removed？So。I mean。

 yes and no， it's I think the content is fantastic， I think frankly。

 a lot of the benefit from the class you could pick up from these slides alone。

 but and even bigger part of the class was that Professor Curs hand graded your code for all seven of the projects and。

He would go extremely hard on design decisions and style。

 which is not something that is really graded in at least any other class that I have taken there's a little bit of style grading in classes like 482 or programming languages。

 but it's not that much。Very， very， very good for things like code maintainability and， you know。

 not duplicating code。Things that are just， in general， good for。

Code that other people can read and understand and update。

 which I think is probably very important for industry That said you're not going get any of that from the course content on the website。

 That's kind of just something you would get from him hand grading your projects。

 So that's something you'll miss out on if you do the online stuff。嗯。The second thing I would say。

 would be the design， the design aspect of the course。

 and there are a ton of different design idioms that he goes over。

 which are on the course website you can go through。I think there's like three different PDFs。

 which are like 30 pages each， which go through a bunch of different design idioms。

 which are all fantastic to look at。Where's the course website， Let's see if I can find it。Es 381。

 There we go。Look at that。 No H TPS needed。Love that little red squibbly。 You know。

 put that right there。 if you wanna try to。Figure your stuff out。

 let's see if I can find some stuff handouts。Where are the。What your notes， maybe here we go。 Yeah。

 these are the three。These are the three like design patterns。

 PDFs you can look at super interesting stuff that you will see you will certainly see if you're taking a look at any industry code。

Stuff like model view controller， Singleton idioms， you know， mixing idioms。I don't know。

 there's a lot to look at there so。Take it or leave it。

 I would say you can definitely learn a lot of this stuff if youre going into industry， just by。

Being on the job and absorbing information， so definitely not necessary。

 but if you want to maybe impress some people， you can do that。Anyways。

 those are the kind of benefits of 381 totally up to you。

 There's a ton of reading that you just need to absorb。 And a lot of the learning， at least for me。

 was gathered through the next day in class after you did the readings， there would be。

A professor orchestrated discussion of the content。

 So that's not something you're gonna to get either。 But the readings are all fantastic。

 He writes up things better than you're going to find on CPP reference better than you're going to find in stack overflow post。

 He has written them concisely。 He's been doing it for so many years， so。All of his readings。

 I think， are great。To finish up the first question， though， verytic templates。

I don't remember where I learned them， maybe。I don't know。

 That's maybe something I just looked up on my own tries。

I don't remember either maybe somebody told me about them。 I think they're pretty nifty。

 This is probably somebody mentioned it on staff once and I Googleod them and I thought it was fascinating structured bindings I didn't know until the semester。

 Joe Richards on staff made a note to them and I said。

 oh the what's interesting And then I looked into them and I said， oh， that's really cool。

So that's where I gathered all this stuff， really， though， this isn't like。

I'm not some like super genius or anything。 I just picked up this as I programmed。

 and as you program more in C plus plus， you'll see some of these things organically and you'll just pick them up。

 So even without each 381， you're not gonna。I mean。

 you will eventually run into all of these topics and learn about them。Cool， one more question。

 what would be some good things to do like resume projects over the summer。

 like some things that could help build a personal portfolio。Yeah， so I think。I mean。

 I'm not like the best to。I'm probably not like the best person to just ask about this， but。嗯。

One thing that I can definitely say is the university itself is good at helping with things like resume building。

I know the career center。I'm sure there's one for LSA but I know the College of Engineering has a great career center if you want to reach out and talk to people about that。

 they do resume reviews which are free， I know they do workshops and stuff like that and also I think Mark Bhab。

 which is one of the 370 professors and a 470 professors as well sent out an email recently with a bunch of professors that are looking for students to help with summer projects。

And some of them are paid and a lot of them you can do for student credit actually so if you're interested in joining some sort of project over the summer。

Getting to know a professor and doing something with a professor。

 I would say is a huge thing that you can do。So yeah， if you want。Yeah， if you want。

 I would either take a look in your email if that yeah， perfect。Awesome。

 William just put the link in the chat for that。Yeah， so， so take a look at that。 I would definitely。

Definitely do that。Cool， I think that is all the questions。Yeah， so barring， barring any last minute。

Squeakers， we are going to call this。The official end of Es 281。Yep。

 great more resources in the chat from Ethan。Yeah， yeah， no problem。 everybody。

 thank you guys for coming。 I'm surprised everybody showed up。 I would have expected this to be。

Very small， if， if not zero group。 but this was， this was a lot of people。Yeah， no problem。

 So I'm going to end the recording here。

![](img/b6f0a9a3f69d3fac7aabea69ad948eb8_2.png)

If I can figure out how to do that。