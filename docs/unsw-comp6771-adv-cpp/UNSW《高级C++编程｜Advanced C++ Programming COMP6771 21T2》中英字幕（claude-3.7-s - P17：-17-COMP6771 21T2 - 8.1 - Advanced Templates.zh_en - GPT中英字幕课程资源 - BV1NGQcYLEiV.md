# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P17：-17-COMP6771 21T2 - 8.1 - Advanced Templates.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Good evening， everyone。 Wel to。Week 8， it's so nice to see you again。

 I guess since we've last talked the exciting things that have happened are that you have submitted assignment。

😊，2。Which， as I said on my notice， is super cool， because。嗯。You know， you。

Basically I've done 40% of the course already。呃。Whereas like， you know， in a lot of other courses。

 students who are still working on or like you know。

 have just submitted things that are like worth smaller percentages。嗯。And， basically。

The good thing about where C+ passes is at is that we're at the tail end of a course that is quite front heavy。

In the sense that。The rest of what we talk about in this course is like not really to do with assignments so much as it's just a mix of general knowledge in the exam so week eight and9 we talk about kind of relevant topics for the exam and then in week 10 it's just a bit of revision and other stuff so we're really getting to the easier end of this course。

Which is super helpful。嗯。But what we're going to be focusing on today is probably this topic here。

 which is advanced templates now。

![](img/015aec1d2084e65be62a50b75655afbc_1.png)

These aren't the most critical topics in the course to get。

If you don't make sense of them that's manageable in terms like it's not going to destroy your life so the pressure is kind of a little bit off a little bit in this area then tomorrow we talk about some more advanced type stuff and we will probably talk about assignment 3 tomorrow night as well because the next lecture is pretty light Fireyn says how long does auto marketinging take。



![](img/015aec1d2084e65be62a50b75655afbc_3.png)

![](img/015aec1d2084e65be62a50b75655afbc_4.png)

Auto marking， I'm not sure what you mean like we spend two weeks marking your assignments。

 I'm not too short what your question is， but feel free to elaborate if you want soup。



![](img/015aec1d2084e65be62a50b75655afbc_6.png)

8。1。Advanced templates， this topic is all about taking what we learned at the start of week 7 with templates。

And。Basically expanding on it。So that。We， how would you put it。

The week 7 was really just about the basics of like， how you use it。

 Now we're really gonna push it to the edges of what you can do with templates。 Oh。

 I don't have a y screen on this one。 That's okay。 Let's get straight into the action。 I guess。

 I mean， the reason we're learning about this is because。



![](img/015aec1d2084e65be62a50b75655afbc_8.png)

There's lots of actual use cases of dealing with templates where you want to do something quite obscure。

 whether it's like templates of templates or default members or specialization。

 and if you know those you can really really make the most of templates So one of the first things that we're starting with。

 for instance， is default members and this is essentially default types for templates and this one's relatively straightforward in the sense that like if we if we pull up this code。



![](img/015aec1d2084e65be62a50b75655afbc_10.png)

I would hope that by now， all of you will be familiar with them。Sorry。

All of you will be familiar with。How when it comes to like functions， you can have。

 you have parameters for functions， right， And in most languages， those parameters can have。Default。

嗯。How would you put it， Those parameters can have default。Arguments， you know。

 like you write a function in in C+ or in any language and you can say， you know。

 in function in a in B equals 5， you can do something like that。 You know。

 that's pretty manageable with C++ we can do the exact same thing for template types。

 So for instance， inside of demo 801 here。You can see that I've got this class stack。

hich is just a stack class。 and you can see that it takes in two different。Types。

 so remember that any time we're templating either a class or a function。

 the line above is always template and then something inside the brackets。 In this case。

 we've got two template arguments。 We talked about this briefly last week。

 where we said like you can have a class that's template on two different types。

 So this class stack is templated on a type name T and it's also templated on a type name cont。

 So cont and T refer to types at compile time。 But in this case here。

 conant is actually going to be by default equal to a standard vector of T。

 So I' saying is if someone does not supply。A type of con forest。

 Then we'll just assume that it's a standard vector。 So essentially。

 this is saying that we're building a stack。Where the container is a template is is like tempable in terms of this container here could be not just a standard vector。

 but potentially a standard。List or which whichever are applicable containers that would compile。

 So in this case， if I tried to build and run this one。And we run it。yeah， it works， right。

 Like it prints out one and three because。In this case， here， we created。With stack of floats。

 And we created a stack of ints。 And these both worked。 And it set the default。

Set the default stack type to be a standard vector because that's what we did。

 So that cont type here was populated as a standard vector of type T。 Now。

 if we wanted it to be a different type， we could of course simply say that by saying actually our stack is going to be the elements themselves will be floats and the container might be a standard list。

Of floats， and then I'd have to include lists here as well。Cool， so then when we run that。没业。

The exact same thing now。Here's a question。That I want to ask you all。

 And I want to say what your answer is， is what。Like what containers would and wouldn't work？

When it comes to， like， this code。So we just saw that a standard vector worked with a standard。

and standard list work， what other types would and wouldn't work here？



![](img/015aec1d2084e65be62a50b75655afbc_12.png)

I'll just wait for the lag to catch up。

![](img/015aec1d2084e65be62a50b75655afbc_14.png)

So Pyn says， would it depend on what functions are run in the dot H。

 Aen says maps wouldn't unordered S says maps and sets wouldn't work。 Now， the simple answer here。

 I mean， we can try this out， right， Like what is a what is an unordered set。

 Was it just unordered set， I think we just include unordered set。 Let's try this one。

So what would happen if we had an unordered set of floats？An ordered set of float。801。

Not the stick compile， this compile and ran。So I had a few people saying， you know。

 these things wouldn't work。 Now， the simple， you know， the simple realistic thing here is that。

Kant can initially be anything you wanted to。 We could make it a， you know a。A Euclidean vector。

So at compile time。So Pyn says， would it crash if you ran a specific function。 So in this case。

 have a look at what the dot H file is。 This dot H file is just a series of a constructor destructor。

And a default definition of a static variable。 And then a whole bunch of。

Member functions for this class that are not defined。

 but it doesn't matter that they're not defined because they're not even used。

By the caller in our mean function。 and therefore， they're lazy instant instantiiateated。

 which means they're never actually。Created， yeah， the result did change。 though。 You guys are right。

And。Well， okay， so just to be clear， the result here had changed because。Okay， so。😊。

Let me talk about why the result change in a sec and it's back to what we learned in week seven about static。

 so basically here。😊，Because these were lazy instantiiateated， they were never created。

 There was actually no function in the definition of this stack that used the container。

 And since there was nothing that used the container， there was nothing to fail at。 But for instance。

 if I define this type here where I say， okay， we've got this container。 And when someone calls push。

I then say do， you know， stack。Don't push back。嗯。Item。Right， so someone， someone。

 someone calls push with a reference to an item。 So， for instance， here， I do。Whereas this one's in。

 I say int j equals 5， and then I say I1 dot push J。

 So I want to push5 to this stack Now what's going to happen here。

Is that I have what I gotta clearly a compile error somewhere， sorry。

So what's going to happen in this case here。Right。Oops。

What's going to happen in this case here is that this will also work because in this case。

 we are creating a stack of ints and standard vector ints。Okay。U。

This is working because when this particular data type goes to get instantiateated。

 it's getting created with a standard vector of T's， of which pushback is a valid function call。

 whereas watch what happens now if I try and do something such as FS or you know I could make a float。

 I'd say float K equals 5 and then I'll say FS dot push K。

So now we get an error here because what's happened is that our unordered set。Has been successfully。

We've created this stack， say， think of this like compile time in slow motion。

 We've created a stack with an unordered set of floats as a container。

 The compile is happy with that。 It doesn't mind that。 But then the second。

That it actually starts to try and instantiate this this class and it instantiates all the functions that it uses of that type。

 which in this case is push。 it now fails because it was like you told me the type of stack was a standard unordered set of T but then you called pushback on it。

 And I simply can't find this right No member name pushback in the unaudered set。

 So there is no like kind of hard rules of what you can and can't do。

 It's like a lot of other things。 It's a lot like the operator less than where。嗯。You know。啊。

How would you put it？With the operator less than what happens is that， you know。You don't。

 Your type doesn't need to define operator less than unless it actually like。Uses it。

 So it's the same thing here。 It's like it what's a valid container。 Well， it depends what you use。

 And back to the question about， would it crash if you ran a specific。

Function would would it crash if you were run a specific function。 It doesn't crash。

 It fails to compile， right， And I know that might have been what you meant。But yeah。

 that's kind of the gist of where that went so。That's what this case is here。

 And to point out that Jinghang says the result changed and the result did change。

 And the reason for that's really interesting， because。Previously， when I had just had float of。嗯。

When I had float of standard vectority。Like this。Right， when I had this and we printed out here。

The stack float numb stackacks。Stack floatat nus stackacks is in this case， one。

 because when I ask the compiler， when I tell the compiler， I want the stack float type。Right。

What that actually is。Is a stack float of standard vector of floats。

 Because that's what I specified here as the default。 So when I say like when I sorry。

 when I just say stack float， this is implicitly standard vector of float as well。

 That's actually what that is in reality。 So therefore， it printed one before。

 when I did a stack float or a stack float， standard vector float。

 But the second I changed it to this， It was a whole different type。

 And what did we learned last week in week 7 about this is that。

Every single separate instantiation in terms of types has its own set of static members。

So in this case here， what that means is that if I was to say， maybe let's make another one。

 I'll make a couple of these， I'll make FS2 and I'll make FS3 and FS3 can just be a stack of float。

Is that if I try and say print out the what is this unordered set。

 the number of the stacks the reference count basically， or I print out this one。

We will get two different values and we'll get one and then two and then three we should get。

 let me get rid of that。

![](img/015aec1d2084e65be62a50b75655afbc_16.png)

We get one and two and three because there's one。The number of stacks for a floats with an unauordered set container is one。

 the number of stacks for a float which is the exact same as a float and the standard vector of floats because of the default template argument is two because we created two of them。

 one here and one here and then the number of stacks instance three because we created three there So that's that's pretty much it on default members a lot of it's maybe a little bit weird。

 but you know。Certainly not the least unintuitive thing you ever heard。嗯。But this leads us on to。嗯。

Specialization。Okay， so。This is one of the biggest topics with temples we deal with。

Specialization is。Where we try and take the very broad definitions of templates we've had so far。

 which are basically saying I'm going to create a type and it's templated on these these types like T and U and V。

 and they can be anything we want。 And we say let's make it more specific。 And in particular。

 the two types of ways we make it more specific are partial specialization， which is where。

 you know you might have a generic type like a standard vector。

 and then you go away and you create another similar type for just say a standard vector or pointers of T's instead of just t's。

 That one's a bit confusing。 And then you have explicit specialization， which is like， okay。

 I created this very。Kind of complex function for。This complex generic type for a standard of vector。

 But now I'd actually like to define a separate behaviour for a specific type。

 And if that sounds a bit conceptual to you， think of it like， you know。

 you might have a function like in min。

![](img/015aec1d2084e65be62a50b75655afbc_18.png)

Auto A， auto B， right？Or say auto something like this。 Now， you wouldn't really do this but。

 you know， you could say return， you know， A less than B。A L B， Okay。

 now if you want to like this is， you can think of this like a generic function。Again。

 you wouldn't really want to use autos for stuff like this。 But， you know， it's like， okay。

 this is me trying to generically describe a behaviour。 but if the behaviour you want。

Needs a different implementation for a specific type。

 You would do what you call specializing something， which in this case could be say， for instance。

Auto min standard string， A standard string B。 For the references and cons， Except in this case。

 imagine that strings， they should be sorted by size for some reason。 So you say， you know。

 return if a dot size is less than B dot size。Cha it A， otherwise B。So。In this case， here。

You have kind of specialized or given like a specialized case of how to deal with the min function。

Uh， whichch is， you know。That's all it really is is you've got your generic case and you've got your special case。

 your specific case， so that's what explicit specialization is。

 and we're going to go through examples of both of those together。😊。



![](img/015aec1d2084e65be62a50b75655afbc_20.png)

So the first thing is， when should you specialise， and I know this is a bit early because you probably don't even know what I'm talking about。

 when should you take something generic like this and create special cases for it like this。😊。



![](img/015aec1d2084e65be62a50b75655afbc_22.png)

![](img/015aec1d2084e65be62a50b75655afbc_23.png)

The times that you want to do that are pretty much。

Only when you need to preserve the existing meaning of what something does， except。A。

If you don't implement something else， it would not work otherwise。

 So the point of specialization is not to create different meaning。 It's to preserve meaning。

 It's like if you've created know a stack that works on any type， in float。

 standard strings or whatever， and has the exact same meaning on all these types。

 you can totally generalize it。 But then you need a specific implementation for a specific type。

 That's when you do that to maintain that semantic。And we'll come back to the slide in a bit。

 But maybe let's just talk about。Yeah， let's just talk about the examples and then we'll kind of come back to the why because I think that'll make some more sense。

Okay， so。

![](img/015aec1d2084e65be62a50b75655afbc_25.png)

Firstly， here's a stack template very similar to what we looked at before。

 This one has its member functions defined， it has a push， top pop size and sum。

 some is just defined using an STL algorithm standard it accumulate or accumulates from the beginning to the end with0。

Across the SL container。This one has a concrete type of standard vector for the container。

This particular type is just a stack of some elements， just like a standard SL container has。

 And then on the right， we've got our main function where we created two ints。

 we create a stack of ints。 We add both of those ints to the stack and then we print out the stack size top and some。

 I feel like I might have had these examples somewhere anyway。

 This is like a standard stack template class。 You should be familiar with this from We 7， right。



![](img/015aec1d2084e65be62a50b75655afbc_27.png)

![](img/015aec1d2084e65be62a50b75655afbc_28.png)

嗯。Partial specialization。Is where we take a class， like our stack。

And we make another template for it。 That's essentially saying。

 I want to deal with a special case of this， which is typically pointers。

 There are more cases in this， but we don't really go into the much in the course。

 But essentially what we're saying here is that maybe I want my stack。To behave。

The same for pointers。As it does for， say， it。 and let me。

 let me like really spell this example out because it's probably a little bit confusing。Right so。嗯。

This is the full code example， which will make a bit more sense so firstly。😊。

Pay attention to how I've got my stack up the top。Push top top implementations。

 definitions or overs in sum。嗯。😊，Then underneath， I have another reefinition of that stack。

Except this one。I've actually had to specify here that it's a specific specialization of that stack。

 Basically what this is saying here is that this is a templated type on type name T called stack and this one here is saying this is a templated type on type name T。

😊，Where it's like stack。But it's only fatigue tea pointers。

So now we're expecting only t pointers to be passed in。 so when we call it partial specialization。

 the reason it's called partial is because。If it was like if it was no specialisation。

 if it was just a broad example， that's what we have up here。

 where it's just a stack that can take in anything。

 whereas this one is specialising in the sense that it's doing something more specific。

 which is that it's only working on pointers。But the reason we call it partial specialization is because it's not a concrete type like T star is still a could be anything like you know it could be any kind of pointer So that's why it's called partial specialization and you can see here that the implementation actually looks really similar One of the only differences is how we do the accumulate。

 but in terms of like top pop size， these things are all just like taking off the stack pushing onto the stack。

They're either taking a pointer off the top or they're pushing a pointer to the stack。

 So this stack is taking a pointers， right， So you have a stack of ins you have a stack of pointers to ins or whatever。

 But you see the one thing that we've done differently here is that we want to preserve the sum semantic。

Right， and what what I mean by that is that if you have a stackum。Pointers， pointers ends。

 pointers to anything。 When someone says sum on that stack。

 you still want to sum up the actual elements it points to。 So in this case， here。

 your stacks actually full of like。It's a vector of pointas。

There's no real like summing up pointers doesn't make any sense。

 Like you can sum up all of the values that those pointers point to。

 but you can't actually sum up pointers。 So in this case here， the actual implementations for the。

Most of these methods are the same， but the implementation for some is a bit different because now when we accumulate from the start of the stack to the end and we start from 0。

 we have to give it a lambda to essentially tell it how to sum things up because otherwise the default behaviour of the compiler will be to try in some pointers and you'll see this right if I。

If I get rid of that for a sec。And I， and I try and run my code。

 It will try and use the one template I've defined。

 So it when it tries to create a stack of ins or a stack of instar。

 it will try and just use the same template because normal templates can be any type， right。

 They can be。In in stars， in factorsors whatever。 And you can see that I've got a compile area here because it's saying incompatible pointeder to integer conversion。

 This is all because of this sum line。 So you'll see if I get rid of this line。

This all works fine now。嗯。This all works fine now， but once I sum it。

 because my container is a bunch of ints。When it tries to do this it like it's like okay I'm going to start it in zero and then I'm going to start trying to accumulate and reduce or sum up the elements。

 but each elements a pointer so it fails so that's why we need this partial specialization。

And this partial specialization gives a more clear behaviour of what to do with pointers。

 which is that add the running total to the dereence of the item I have in this in the stack because。

 you know my stack is。呃。Yeah。Cool。So。Now。嗯。That's really it。 That's like the whole thing。

 It's like you're pretty much just defining a special case。

 Sometimes like when we say partial specialization， you might think， okay， is that just pointers。

 right。Which is like， you know， it's like standard T star could be standard vector or T， whatever。

 like it's any time you're saying that there's a specific constraint that I'm adding to this。

Except that that specific constraint is not a fully realized type。 It still itself is。

 is somewhat generic。嗯。Yeah。Soir。That's what that T star is there。

Are there any questions about partial specialisation。

 I think there was a question before that's like， do we need to write two separate classes？ Yes。

 I do think you need to rewrite things from memory Like you have to copy and paste。

 It's not really a very elegant thing。 Let me let me， let's try it。

 Let's get rid of the top function and see if it see if it still complains'ca we use that in the。

The special case。Yeah， so it's basically like it doesn't exist。

 So it is it is a little bit of ugly boiler platelate。 This is one of those things that I imagine in。

 in future versions of C plus plus， they will streamline substantially to avoid this kind of repetition。



![](img/015aec1d2084e65be62a50b75655afbc_30.png)

yeah， any questions about this before we move on and。Maybe talk about explicit specialization。



![](img/015aec1d2084e65be62a50b75655afbc_32.png)

Oh， so I missed your question。 Did I miss your question， Ellen。Oh， no。

 I think I answer that anywhere， y。Cool， so。Basically。

Explicit specialization is the exact same thing， except you're actually making it a concrete type。

Right， so with explicit specialisation， we can try and do this ourselves here。 I don't。

I don't know if you say template type name T。 I think you get rid of the template type name T from memory。

Oh， you just sorry， template。 you get rid of the type name T， my bad so。

The idea here is that if you are defining this for a concrete type。

 then you have this template type named T。Except the。There is no T anymore， right， Like it's still。

 it's still an explicit specialisation of a template， but there is no type named T anymore。 So now。

 instead of this， we actually give it a concrete type， which here might。

 let's say we have a stack of standard strings for some reason。嗯。And now we， you know。

 instead of push here， it's just， you know， standard string t and then the T here， similarile。

 like we just go and actually， you know， make them make the more concrete。

 we get rid of the T's at's the standard vector of T's and then let's just start off with like this。

 So this is an explicit specialization because all the T's are gone essentially there is no template or there is no type variable here。

 And what that means is that we can then come along and say， okay， well。

 actually I'm going to make a new stack of standard string。And I will。You know， say auto。S equals。

Standard string。Hello， like that， and then I'll say S3 dot push S， and we'll see if this compiles。

Now。Oops。What did I do wrong here。M。Yes， Sir。One of the weird things about。Templates。Is that。

I'm pretty sure that when it comes to。嗯。Partial specialization。Like so this will compile， right。

 let's just get a base case here。Oh， no， it doesn't。 What have I done wrong then。OhOkay。Yes。

 so do you know how back in week 7， we talked about lazy instantsiation。

 which was that for templateative types， the functions themselves。

 the compiler ignores the member functions unless they're actually used right Like if they used the compiler looks at them and Nathaniel was in the chat and Nathaniel pointed out that this can actually lead to some really weird behavior whereby。

 I mean comment out my string class as well can really make this point clear。

Nathaniel pointed out there's some really weird behavior here how like you know this program works。

 and if I get rid of the sum here。Right。This， this function could fail。Right。

 so this function may just say not work oops。This function technically right now wouldn't work if we tried to use it。

 but it doesn't matter because we didn't try and use it。 And whilst we didn't try and use it。

 the compiler doesn't even bother trying to compile it， because if it's not used。

 how does the compiler even know whether it's valid or not。

 And we saw this before when someone asked， we were talking about， Is this valid。

 And the answer is it depends what type you have。 So if you have a valid type here it works。

 it instantiates it correctly， if you have an invalid validid type it doesn't work。

 And even if you have an invalid type It doesn't even bother to check if the function works unless you call the function。

 That's all like just the template behavior。 So templates behave a little bit differently than。

To our explicit specialization， because even if I don't create an instance of the class。Sorry。

 even if I don't use a function in this class。And then even if I don't even create an instance of it。

 this is basically treated like a non templated function at compile time。 And this makes sense。

 right， Because the mean reason。The compilers don't instantiate something as because it doesn't exist。

 They don't know what type it is。 Therefore， they can't do their normal checks。

 Like you can't create a class of a type。 you don't know what it is。

 whereas with an explicit specialisation， you know exactly what it is。

 It It's a stack of standard string。So in this case here， it's like， okay， well， I know what it is。

 cool。 I can check， and it did check for us。 It checked and it ran this function and knows what these types are。

 And it said， this does not。Pass our type checking。Right。嗯。So。0， so not0。 So it's so compile error。

 And the compile error here is exactly the like a similar thing we had with the pointers where it's like。

 I don't know how you want me to add a string to 0 because accumulator is adding a。

All the values in the vector and it's like I can't add a string to0 and in this case it's saying there is an invalid opera to a binary expression which is adding int and basic string。

 which is know the standard string。So again， for explicit specialization， we could， you know。

 we could define a separate lambda that says， say I'm going to sum up all the string length。

 so I might copy this lambda here just for simplicity。And this lambda what what this lamb does。

 it has no capture。 It takes in the int， which is the sum。 And then it takes in the standard string。

 which is the element， because all an accumulate does， is has like a running total。

 which it's like always just adding on。 So this standard string is what we add to it。

 And in this case， I'm just going add B dot size。 I just want to add the size of the string to the running total。

 Now， this should compile。Or get close to compiling。But B dot size isn' an unsaiign long。

 This is a bad example， by the way。 So I'm gonna do some really ugly things。

 And I don't even know if it's gonna let me。 It's probably gonna complain。

 It's gonna be like use of old style cast。This example is meant to show you what not to do。

 So I was like， I'm not gonna like over invest in getting it right。 Let me just word wrap it。

What's red wrap on this thing。OhWro， tole warro， yeah。Maybe this funny will work。Okay。

 so this one still works and then if I tried to print out。

 notice how it didn't compile even though like we didn't even use it。

 and now if I try and print out say S3。 sum。We should get the sum of the string， which is hello。

 so we should get five， right。It's the wrong one。 Is it， No， it's the right file， okay。

So we get five。So again， because it's a string， we went to the explicit specialization。

 the way the compiler works is that。ItIt looks for like explicit ones。 Well， I mean。

 the compiler just looking for an exact match， right， it always wants to do that。

 then it'll look for a partial one， then it'll look for the most general one。

 so it moves in that order。😊，Now， what I want to point out here is that this has mainly been me just trying to show you the behaviour of this language feature in reality。

 what I've done is kind of terrible for partial it's probably not great。

 but for strings it's even worse because what I've done here is I have changed like the semantic of what all of this means now。

🤢，It's maybe not the end of the world， but it's like。The point of specialization。

Is not to make your template work for every single type in existence。

 There are lots of types There are templates that just might not work for certain types。

And there are conditions on some types you have to pass into templates like。

Sometimes they have to be ordered types， like if you pass if you pass a type into an ordered set and it doesn't implement an operator less than it's just not going to work。

嗯。You know， if I tried to create a。If I came into my code here and I was like。

 I'd like to create a standard set which is ordered of a stack of ints。



![](img/015aec1d2084e65be62a50b75655afbc_34.png)

The compiler here is going to say， sorry， but stack of in is not ordered。

And I expect an ordered type with these kind of， you know。Abilities。

 so I'm just not going to compile it。 So， and that's totally fine because like the aim of specialization again is not to make sure things compile all the time。

 It's not to just keep adding in all these random use cases so that things work。

 It's that if you know， you can make something work the exact same way。Without changing any meaning。

 I the person using it thinks it works identical。Then do it， You know， otherwise don't。

 So in this case here， I've kind of changed the meaning in the sense that。

This sum function should just not really work with string。 Perhaps you could implement this。

 this explicit specialization to just remove the sum。 Sure。

 that's okay because you haven't really redefined the meaning of it here。

 taking something away is probably better。 but the main point is that。

You should just use this with caution。Okay， because。Again， back to the slides。Whatever I set up here。

You special to preserve existing semantics that would would not compile if you hadn't made the specialization。

 The times you don't specialise is pretty much。When you think it would be cool to change some feature for a class for a specific type。

 that's just a different class。 If it has a different behaviour， it's a different type。

 otherwise you're just an nahole really annoying people So everyone will always assume that any templated type has the exact same behavior in semantics generally speaking for all these different types that's like a good rule to follow。

And。The only other note on this slide is not to use。Template specialization for functions。

 as weve already talked about this before， like we don't really want to using specialization for functions anyway。

 We'd rather you just use function overload。 So， yeah， just do function overloads。

 You don't need templates for anything like that。Now， Pin says， so if the template works for type A。

 you don't need to make a partial specialization for type A。 Yeah， exactly。 so like。If your class。

 like when you make a class like a vector， it has a meaning。 that meaning is you can push。

 you can pull， it， does this， it does that。If it works for all types。

 then you don't need to specialize anything。But let's say your for some reason。

 your template doesn't work with pointers。 something breaks。 I'm not too sure what。

 I don't use a to of partial specialization， but it just doesn't work。 And you think， well。

 if I just implement this differently， I can bring it to the exact same meaning as something else so that other people using my thing won't even know to look the exact same。

 but in reality， I've had to you know pull some levers and make some things a little bit different。



![](img/015aec1d2084e65be62a50b75655afbc_36.png)

An example that I don't know too much about， though I thought it was really interesting to read about。

 I linked something here。

![](img/015aec1d2084e65be62a50b75655afbc_38.png)

About standard vector bulls。 And I actually think that's the did I miss a point。One that。Oh， yes。

 The only thing I've missed here。Is that another reason for specialization。Is if you have。

 if you have like a templated type like a vector that does compile with say string。It is fine。

 but you think you have a way to make things go faster。 and an example of that is with standard ball。

Standard vectorables。And。I don't know。 Like， I'm not 100 acenture on all the details here。 I I。

 I read this and kind of mate mainly went through this a year ago。

 But even if I'm missing something or even if。

![](img/015aec1d2084e65be62a50b75655afbc_40.png)

Even if I got pranked to something I'm just kidding， but like the point is still the same。Is that。

I mean here we're looking at it now for space optimization reasons。

 the C++ standard calls out vector Bull as a special standard container where each bowl only uses one bit of space rather than one by。

Now， what do we know about memory with computers， We know that a byte is defined as the smallest amount of addressable memory on a computer。

 you know， so like， yeah， you deal with bits， but you can't update a bit on a computer。

 you can update bits that are part of a byte like you say this memory address points to this byte of memory and you can update that byte。

 which consists of those 8 bits， right but。嗯。As you know， like a bull。

 a true or false is just a bit of data。 So like there's no point like when you store you know。

 when you store a vector of bulls。Say， and youve got your， you know， you got your bite over here。

 which is， you know， like 1，0，1，0，1，0，1，1。 This is 8 B and a byte and you're。

 you're trying to contain a huge amount of data， you know。

 like potentially 2 billion or whatever integers。But。Is it 2 billion。I can't remember， you know。

 but if you think about it， like if you have a standard vector bulls。Oh， that's a four bite in。

 I'm sorry。 It's like a char， right，'s 256。 I'm really， I'm a moron。 So let me take a step back。

1 by on a computer is like 2，56 pieces。 right， A char is one by。

 say a simple char that can do the ASI characters as one byte at memory can do 256 values。

 So when you have a standard vector of chas， it's going to be smaller than a standard vector of ins。

 right， because a standard vector of chas is going to be you know1 by for each character in the array。

 A standard vector of ins is going to be4 Bs。For each item in the array of vector， right。

 So a standard vector of ins with 10 elements will be four times bigger than a standard vector of chas because of the type。

The problem with bulls is that bulls use less than one by。

RightBecause even though chacars use one by， that's because they need to represent 256 characters which means they need eight bits。

 so they need eight little pieces of binary。 a bull just needs one true or false。

 So when you have a standard vector of bulls， if you just store it as a standard one byte data type。

 then you're essentially wasting you know eight times the memory because in a single by you could represent8 bits。

You could represent eight bulls。

![](img/015aec1d2084e65be62a50b75655afbc_42.png)

So an example。I've never had to interact with this。

 I just think it's an interesting academic example。

 an interesting example of this point at the top here about there are like one of the other reasons to specialize is when there's an optimization you can make for a specific type without changing the semantic is standard bull the idea that you could implement standard bull as a bit math or a bit set or whatever so that each kind of buy it。



![](img/015aec1d2084e65be62a50b75655afbc_44.png)

嗯。You know， holds 8 bulls or something like that。 So you， you could do this for， say。

 space performance reasons。 So storing a vector of a billion bulls。Uses eight times less memory。

And you know， this a lot of this stuff starts to make sense。

 which is one of my more my one the thing I like about C plus plus is like， you know。

 here we're saying， you know。With this specialization。Since you can't get an address a bit。

 which makes sense because， you know， like on a computer， let's say that you're storing 16 balls。嗯。

Those 16 balls might be like across two bys， so you've got like one ball two ball and you got。

8 balls here and another eight balls here。You can't actually access a particular ball。

 you can't say go get me like the third ball or the fifth ball because a computer can only interact with the start of each bitete。



![](img/015aec1d2084e65be62a50b75655afbc_46.png)

So the article the article the stack Overflow page here is describing like since you can't take the address of a bit within a byte。

 things such as operator Subscript， which you're familiar with because of assignment too can't just return a ball reference because typically what you do is you return a byte like like a reference to a particular piece of memory so instead like standard vector actually returns a proxy object so you know maybe like an intermediary class or something I know very little about this in the details。

Because I don't really care that much personally。 But I think like， I think it's an interesting。

 again， academic example about how you can use。Explicit specialization to actually give an optimization。

 So so standard bull would work fine， like it still compiles without an explicit specialization。

 but if you do this， then you can maybe get a type that looks and feels and behaves exactly the same。

 but。😊，嗯。You know， can have some。Potential space performance increases。Improvements。Cool。

 that's pretty much it on specialization。 Just having a quick look。Few things。

Let's quickly talk about type traits before the break。



![](img/015aec1d2084e65be62a50b75655afbc_48.png)

Type traits are a really interesting example。嗯。Of explicit specialization or even partial specialization。

 And there're probably a way we can help。Really solidify like what the purpose and usefulness of some of the stuff is。

 You might have seen these things before。These things around where you can。

Get some information or you know。I don't know how you describe it。

 whenever you see something like this in your code， It's what we call a type trait。

 and a type trait is essentially a type in C plus plus that characterises a type as and gives you some information about a type。

 And the really interesting thing about type traits is that they're actually just implementations。

 They're actually just explicit specializations。😊，Of a particular。Tempature type。 So， for instance。

 have a look at the bottom code here。 The struck numeric limits。 This is a。

True generic template or type in C plus+ it's a class structure all the same thing。

 it's a class type called numeric limits， which has one public static member function， which is min。

 and it returns a type T。That's what Min returns。And。Yep， and it's not implemented。 It's not defined。

 right。 And what that means is that if you try to go and instantiate a version of this。

Just generally， if this was all that was declared， you would not be out the compiler wouldn't do it。

 It'd be like， sorry， there's no definition there。 But what we're doing instead underneath is we're actually creating explicit two explicit specializations of that numeric limits type。

 one for ins and one for floats。 And what we're saying is that for the int explicit specialization。

My static function min is actually going to return me this particular value。

 which is kind of defined at the。Like in maxax is like。

 think of it like a global variable that's tied into the specific compiler you're using that knows what type of operating system you're on because on different operating systems。

 your integers might be different， right？ And you know， same with like float max。

 So it's like you can actually get the limits of the biggest in and double you can get this way。

 And again， one really powerful thing about this is these aren't runtime checks。

 these are actually compile time checks。 where the compiler can actually bake this in to your your code。

 Like when this all gets compiled up， this entire line here just simply gets replaced with。

Itt max -1 or a function that just returns that， for instance， if it's not constant expression。

 So really powerful because it means that you know you can kind of custom。

 you can define the limits of all these primitive types just by simply doing explicit specializations and it's a nice little abstraction you again。

 you can constant expression this and reduce it all to just a constant compile time without having to memorize anything。

 This is tied this is part of the limits library here， but yeah， that's super cool。

 that's an example of a type trait because this is characteristicizing a type in this case here。

 the characteristic is the numerical limits of a particular type。Now。

 other reasons type traits can be useful right， Well not other reasons reasons type traits can be useful is if you remember back to our nontype parameter examples from week 7。

 the start of week 7， we talked about how you can nontype parameter a fine max function for say a standard array or something which you'll have some compile time benefits and all this other stuff。

 but one of the problems with any kind of。Standard function that finds the min or the max of。

 of a list of values or array of values is that whenever you're finding the min or a max。

 you generally either need to。Set them in as the first element， or you need to set them in as like。

Some massive number。 So that pretty much anything except like anything。

 any next value is gonna be smaller than it。 You've probably done something like this before， right。

 where you've said the largest number。 well， so I've got that the wrong way around where you've said the largest number is negative 99999999-99999999 in the keyboard right You're like。

 let's just make of the smallest number possible so that literally any number in L list is gonna be bigger than that's a good default value because you know。

 it's just easier is you can see here， now instead of doing that negative smashing 9 on the keyboard。

 we can actually just say that the largest number so far is the literal minimum that this type T can be。

And the benefit of using type traits instead of just saying int min or importing some random C plus plus library that has that constant。

To find in it is that because we have these type traits， which are templates。

 we can actually generalize what the minimum is now。

 So we don't even have to like whether that's in or float or whatever it doesn't matter。

 Our fine max class or function， sorry is able to。嗯。Put in that type。 like， for instance。

 if you do a fine max of an array of ints， then it will just call the numerical limit on ints。

 So the cool thing about all these things is that it really allows you to build these really consistent layers of abstraction where your function and other type traits that users can all be templated on the same types because all these systems are using the same kind of template structures。

 Pi omega says don't we need to make it a constant expression to make a compile time， Yeah。

 so I think there's some examples we have somewhere。

 but these would need to return constant expression values to compile time be be like injected directly in though the main benefit of this is not like I kind of alluded to that at the start。

 So that's probably my fault。 But the main benefit of this as you see it is not necessarily performance it's actually just a really nice abstraction。

 It means that like because of type traits， you can simply say that。

I want to find the maximum of this type T， whatever that is。 And to start off。

 I need to find the minimum value of this type T， whatever that is。

 So when someone comes along and they add a new type， say if they wanted to to a C plus plus library。

 they could just add not only that type， but they could add what they could add an explicit specialization for the numerical limits of that type and define the in。

 and therefore it all keeps working with the same same infrastructure and processes and stuff。



![](img/015aec1d2084e65be62a50b75655afbc_50.png)

There's a couple more examples of type traits here， which use both special。

Partial I'm really off off it today。 partial specialization and explicit specialization。

 and this is a really good example of partial specialization and one I said earlier。

 like I don't use partial specialization。 much what I mean is that I've never come across a situation myself where I've needed a partially partially specialize a class that I've written but I understand like how it's used in the library。

 So a good example of other type traits say is void which is another templated class which simply has this like so is void is quite these are really sneaky ways of doing things which I really like is you create a templated class called is void All it has is a static cons ball that's false。

 So there's a static member data member that's just false。😊，But you explicitly specialize it。

For the case of bull。To have that data member be true。

So now when you have a program like this and you saySt up is void Valel。

Is void of an intve or is void of a void vow， this one's going to print false and this one's going to print true。

😊，And you might ask。What the hell is the point of that， Cool。

 We just printed out whether void is a void。 That was helpful。

 And a lot of the reason I'm not sure if I have an example that we do。

 We have an example on the next slide， is like。This I like to think of this is it allows you to。

 to capture。Type traits as values。And I know it might sound weird to you。

 but it's like you don't write programming with types。You don't put types in your if conditions。

Or your or your wall loops。 like all of those things are all values。

 So if you can convert a type characteristic to a value。

 it means you can do logic programming with it。 It means you can save for a template at a type when someone instantiates your。

 I mean， what hit like。Like here's an example。 I'm pretty sure there's another。

 There's probably another type called like I bull right。 So it's like you could， you could。

 for instance， in your code say something like I've got my。I've got my template type up here。

My stack。 And I could say here， if。It is。Yeah， is void， let's start with that。 is void T。Val。

 then I'm going to like deal with the void case。Else， I'll deal with like the non void case。

 So it actually allows you to add some conditionality to your code based on the particular type that's been passed in so that you don't have to like necessarily even explicitly。



![](img/015aec1d2084e65be62a50b75655afbc_52.png)

Specialized things。 But， you know， you have a little bit of conditionality there， which is nice。 Now。

 the con the more clear examples of that are。

![](img/015aec1d2084e65be62a50b75655afbc_54.png)

And I like this example， demo 807， which is like we have a main function that creates know an inter long and a double。

 and then we have this test if number type function here where we basically just want to see if it's a number。

😊，So we just have a function we take in a value and we want to see if that value is a number type and what we're doing is we're actually using type traits here to say。

 okay， well， my test if a number type isn anaught is a templated function。

 sorry this is actually one area where like。This is probably like one of the few examples I can think about where a templated function is better than a template than an auto function。

Because with an auto function， you couldn't really do what we're doing on line 6。

 But the point here is that I've got this templated function that takes in a generic type T could be any type。

 And then we simply say if。It's an integer type or it's a floating point type。

 then we're going to stand at C out that it's a number else we're going to stand at C out that it's not a number。

 So we're using these type traits to capture the generic type that ends up getting constructed and extract traits of that type。

 We don't know whether the tea is an integral or not。 We don't know whether it's a floating point。

 It depends on the type that the person using your library actually ends up calling。

 but this allows us to you know build this conditionality into it。

Are there any questions about any of this， I'll wait a minute for any questions。

 and then we can take a break。Phi sensors， will it mostly be for static functions。

 Probably the most common case of。Of partial specialization I've seen is for。Static well。

 like not static functions。 just， you know， like these library types that are mainly like statics just a way it it。

 it manages this because you're not instantiating anything。 you're。

 you're just dealing with astruct It could technically be a function as well。



![](img/015aec1d2084e65be62a50b75655afbc_56.png)

I guess。Also， I glossed over this example before， and I'm sorry about that。

 but this is the example of partial specialisation。

Where here I'm actually like I actually use a partial specialization to determine whether or not a particular type is a pointer。

So， again， this is a value。 This is a value you could put in if statement。 You could say if value。

 you， you could actually in your template， like you can do this with your graph in assignment 3。

 right， you actually put something in that's like， yep。

 if the type being passed in is a point to type。 and I'm going to use that type trait。

 I think this is missing。These might be missing some ST TDs。Oh no that sorry。 we。

 we custom made these my bad。 Yeah， So like， you know。

 this would help you figure out whether it's a point or not in in a nice， generic， abstract way。

So let's take a five minute break and then we'll keep going through and we'll talk about varied templates and member templates and some other things。

Yeah， so I'll chat you in5 or 10 minutes， cool。We're going keep moving on the next real topic to chat about is veryic templates。

 This is a bit of a random topic I'm not going to lie。 We don't really know where to put it。

 could probably put it in tomorrow's stuff to be perfectly honest now that they think about it。

 but this whole week's kind of where some topics ended up just generally。



![](img/015aec1d2084e65be62a50b75655afbc_58.png)

There's more of that tomorrow， butvariic templates are a really interesting example of something you can do with C+ plus。

 particularly around templated types。And even more importantly。

 it plays into some stuff we'll probably talk about with Standard For tomorrow。

 which I find very confusing as you'll you'll soon find out。

 but the idea with veryatic templates is it's basically you got to think of it like I think of it like type recursion in the sense that have any of you ever wondered how say a。

I mean， this isn't the best example。 But like， have you ever wondered how a printf can just take any number of arguments。

 Like you can give a printf like the format string。 and then however many variables exist。

 you give it like 100 variables or two。 How does it deal with all of that。

 Has someone manually gone and written in like v 1， var 2， var 3， var 4 and then defaulted them。

 Like how does that all work， So there's some kind of variability there in terms of how。嗯。

Those functions take in arguments， right， And a simple way that we can do that with C plus plus。

 In fact， we could implement our own print function is to。Template to print function。

Just type name T。 I think of this like the base case in a recursive sense。

 It takes in a reference to a conee message， and then it standard see outs that message。

 And then we make another templated function， which is still called print， which takes in two things。

 a type name a。And a type name B， but these kinds of dot dot dots refer to like a list it's like a spread operator。

 It's just a way of saying many type names， like many type names B。

 And then when when we look at the actual function parameters itself。

 it's saying that we're going to take in one argument which is our head。

 and then we're going to take in the rest of our arguments which are tail。

 So tail here refers to a type。That is a collection of bees， basically。

 And this is referring to here as a type。 that's like a collection of bees。

And then we print the head and then we call print on tail dot dot dot。

 which is like the collection of bees， which may recursively instantiate another version of print because again。

 like think about how you know， if this is kind of confusing， think about。

 you know how printing a linked list works。 you know， you give it like the head and then the rest。

 and you print the head and then you recursively call print on the rest。

 which prints the head and the rest and you kind of go for like you go down that path until you eventually run out of things to print。

 So therefore， if I try and print one and2。To as a float。 It'll work。

 If I try and print  one to and hello， that'll also work because it can like recursively deal with it。

 What's really interesting， though， that I help， I think。

 helps make sense of what's happening here is that let's have a look at the instantiations that are generated。

 You prologue I'm getting prologue flashbacks。 I haven' looked at prologue since 2013 when it hurt me。

Do you know， Do you know， Do you know Claude， you know Claude USW。You know。

 Cloyd was like one of the I I don't。 I'm probably wrong about this。

 but Clayde was one of the people that helped write prologue or part of it。 He was。

 he was a big part of prologue。 I， I don't know much。 You should go email him and ask him。

 It's probably written here。Or is it prologue or is it somewhere else。Plogue。I don't know。

 Maybe I made that up， maybe I dreamt it。But。Yeah。The no。I should ask you and remember。 so I don't。

Either。But butcher is， butcher' is working either way。 But anyway。

 we have cool people at USW is the point。 I don't he was， he was， he was。

 He was very relevant part of the community in its early days。

 That's about as broad a statement as I'm confident on。😊，Yeah， he， he， he's he's a smart guy。

 leads up leads up the AI group， I believe， or robotics or intelligence。

 I'm not sure what they call it the intelligence group。 anyway， smart very smart guy。So。

I just lost my train。 Yeah， so what's interesting here is that。

When we actually do something like these two print statements。

 there's a whole bunch of instantiations that are generated。 And again。

 this is actually one of those random things that also makes C plus plus quite a fast language because a lot of its kind of compile time in the sense that like if you had a language like I don't know Python maybe and you say you print many things like think about how Python works。

 It does like all these like run time checks like it's like I have a list of things to do like my Kw args And I'm just going to go through them all and figure out what there's a lot of run time checks that happen whereas what actually happens with C plus plus is that when you say I want to print。

嗯。I'mJust double checking。 I think this on the right here。Is。Just the bottom one。

So like these are the instant instantiate instant instantations，iations。m saying it weird。

 but these are the ones that are created when I call print with one as an in two is a float。

3 is as a chart constant。A pointer to a con cha， which is a string literal in C， right。

 is that firstly， when I call this。It。Tryries to generate this function here。

 So what I want you to visualize is that when you call this when the compiler sees this function call。

It looks for a print that types match this。 It finds this one， the veryatic template。

 and it generates this piece of code in the binary in the executable。 So。

 and this makes sense because basically what it's like is I'm going to take a type A。

 call it my head。 and I'm going print the the name associated with that type。

 And then I'm going go take take all the other things。And print those next。

 which is why we get kind of print B。 I I might have explained that poorly early on， but it's like。

 that's the gist of it as it's like， it just groups them together in other languages。

 the spread operator is a way to kind of capture a。呃。

So in other language is a spread operators a way to take a list of things and essentially break them up as if they were like normal parameters。

 So instead of print， the second print getting a single argument， which was a list of stuff。

 It's actually getting all of those things you had as separate arguments so。

We end up having print A and then print B， but then the compiler says okay， print A。

 well I don't know how to print A A is an int， so the compiler then looks at this and it says that's not a template I want and it looks at this one it says oh。

 that's a good template， It takes in one argument。 we can match it so then it instantiates this one here。

Right， it instantiates that， and then it looks at this print and says， how do I print B and C。

 I don't have something for it， It goes back to here which works。

 and then it instantiates this one which is the head and then the tail。

Right the head of type A and the tail of like the list type H B， and then it does that。

 but then both print B and C， printing a float and printing pointed to a cont。

They both need their own functions。 So again， we get two instantiations of this。Richard says。

 are you saying that the print functions on the right are created at the compile time exactly that's exactly what I'm saying。

 So what actually happens here is that all of these different function calls are statically resolved now。

Is this a good thing， Maybe probably， but， you know， sure it's gonna to add some code bloat。

 But again， the reason we like some of these languages like C plus plus is because they're very fast because now at runtime。

 there are no checks。 It's literally a series of function calls。

 It's as if you just define these all yourself。's no not dealing with polymorphism。

 You're not dealing with anything strange。 It's just here's the list printed out the exact functions。

 Make the calls。 Do the stuff。 go go， go So that has some benefits to it。 Of course。

 But it's just kind of relevant to understand how it works。

 there are any kind of questions about that。 Otherwise we' keep going。I'm gonna go。 Keep movinging。嗯。

One of the last few topics to talk about is member templates。嗯。So。Clearly， this could work。

 but doesn't by default。Yes， so let's look at this code here。

 What we're trying to do is we're trying to create a stack of ints。 And then we are trying to。呃。

Push to that stack， and then we're trying to create a second stack of。

 and then we're trying to create a stack of doubles that takes in a stack of。Okay。

 so what are member templates， Member templates are essentially functions。

Or member functions of a class that deal with other kind of templates。So。嗯。And this again。

 this isn't something that's like you're going to use every day。

 It's just an understanding of how the language works。 So firstly， when we tried to copy。

 construct it， this works because we know that if you don't define。Those rule of five things。

 the compiler would generate them for you， it would generate the copy constructor and the move constructor and the copy assignment。

 and the move assignment。And it'll just do a member wise copy for you。So if you do this。

 the compiler will automatically generate a copy constructor that will simply copy all the members across and standard vectors copy Conor will copy all of its members across and you get that big beautiful recursive。

Copying， but this one here won't work when I try and construct a stack of doubles with a construct in。

 And that makes sense because it's not a copy construction， right， That's。

 that's actually kind of like a boutique function， or it's a copy constructor with a specific。

Kind of argument。 So member templates are a bit weird。

 But the idea with member templates is that if you have a class like this， a stack。

 you've got a constructor， you've got to push a poppa empty， all those things you'd expect。

's it's full of vectors。 You've got your pop implementation of it。 This is from week 7。

And then you use it like this。 if you want to be able to do this and construct a stack of doubles given a struct of integers。

 then you have to start doing some funny syntax things like this。

 And what this is is you saying that actually inside my templated type。

 which is templated upon type name T， I want to create a copy constructor。

Or I guess this is specifically a constructor that takes in a stack of another type or a reference to it。



![](img/015aec1d2084e65be62a50b75655afbc_60.png)

So obviously if I was let me look at the code， let's look at the code together。

 obviously if I was just saying like I want to create a copy construct。

 then you could probably do something like this right。

 I have a you know and maybe maybe make it constant as well。

I want to create a constructor for my stack it takes in a constant reference to another stack of the exact same type。

 but if we want this to be a different type， then we need to put template。



![](img/015aec1d2084e65be62a50b75655afbc_62.png)

Type name T 2 above it to kind of specify that， no， no no。

 while this is a generic class and this is a constructor for a generic class。

It's actually taking in a separate， different type。Different generic type。As part of the peri list。

And then from there， the only other weird thing you need to keep in mind is that when you go and implement that outside of the class。

 let's say you want to define it underneath to keep your code a bit cleaner in a normal case when you're doing that。

 just like pop， you just write template type name T up the top， just like your class。

 and then you just scope it just like a normal class thing we've learned in week 3。

 this is what we learned in week 7， but if you're ever doing member templates。

Where you're not only defining a constructor for a template type。

But that constructor is using another template type， such as say， taking in a stack of another type。

 Then you actually need to put both template type name T and template type name T to it above it。

 Now， you， you can't do template type name T。

![](img/015aec1d2084e65be62a50b75655afbc_64.png)

Type name T2。Because that would imply that this particular function is templated onto like static types。

 that would actually be a whole different type。That's a different thing。

 What we're saying here is that we're dealing with two templates。

 Both of them have one generic type in them。One of them is our stack。

 and the other ones the other kind of stack。 And you can see that the way this function actually works is that。

And by the way， this one is， this one is something you probably wouldn't want to doca there's some problem like there's some best practice problems with like having a stack randomly unload its values and。



![](img/015aec1d2084e65be62a50b75655afbc_66.png)

Cost。I guess it's an up cost， at least， which is good。BA。

 you can go through the old stack of ints and then you could push it to the new stack and statically cast them to T。

 which is the type of the new stack。So that's essentially how you could do some generic template programming between your template type and another template type。

Yeah， so that one's kind of interesting。That's pretty much in on that。

 Are there any questions about that？I'll give you guys 30 seconds， again。For that one。

Bd says so a copy and swap idiom there would be better if that's even possible。 Yeah， it would。

 but the two problems with this example， in my opinion are that one。Well。

 I mean this example's main problem that it's operating on a stack。And。

I don't know how much you'd want to allow moving between different types for a copy construct。

 This is just an easy example to kind of explain some intricacies of of the language's behaviour in quite a small amount of space。

 But but yeah， normally you probably wouldn't use a separate type。 I think it'd be pretty normal to。

You know， define a copy constructed just with one type。嗯。Jin says。

 can you explain the template T E T2 thing again， Are you referring to like when I。

 when I brought this up and said it could be this。

![](img/015aec1d2084e65be62a50b75655afbc_68.png)

If， if you are referring to that， my point is that that's just like a different。Thing。

 it's like giving it a different function name。 like the second stacks templated on two types。

 It's a different。 it's saying that it's saying that my stack is templated on two different generics。

 like my object。 whereas something here is more saying that my stack is templated on one object。

 one type T， but it' it's going to be using you know， another objective of another templated type T2。

 So it's just a difference between saying I am two things versus like there are two things。

 like instead of saying there's one thing with two types。

 or're just kind of saying there's two things with one type。Kai says。

 " iss there a way to specify a constraint of what template type it can take in？U。

What kind of constraints do you mean。That'd probably be the question I have most on my mind。

Cacause like， you can obviously， like if you only want it to be one type or two types。

 you could constrain that with。Some specialization。

A lot of that's kind of handled for you implicitly， I guess，ca I guess as a library writer。

 you don't really care what type it is that sell point of generic programming。

 You just need to make sure that that type has the fundamental capabilities that you expect of it。

 So， for example， in。嗯。You know， in your graph assignment。You assume that the types are ordered。

 I believe， because you need to be able to sort the edge edges so。嗯。So yeah， that in a way。

 like that's constraining it implicitly it's maybe not that well documented。 And you know。

 you kind of find out about it through your compiler。

 but generally speaking it's like if a compiles it the type's good enough。

 I can't imagine situations where you would want your templated class to not work on a type that is valid。

That makes sense， but I'm not sure there might be something I'm forgetttting around the constraints。

This one is probably one of the more。

![](img/015aec1d2084e65be62a50b75655afbc_70.png)

Interesting and confusing things。 And there's a few different ways to do this。

 as we've learnt in previous times as well。 And thiss the idea of template template parameters and template template parameters are simply saying that。

Like。With a template。嗯。You're saying that this class has a template type and it has two tight parameters。

One is a type T and the other one might be another type T。

 or maybe there's only one templated type parameter。What a template。Template parameter is。

 is saying that I've got a template with type name T。

 But then the other type is actually another template with type name， something。

 And I'm not going to lie。 This syntax wes me out。 And I never remember it。

 And if you asked me before this week to。To to do it。

 I'd just be randomly trying different ways that the templates and type names work because it's just like an overload of like template type name template type name。

 which is a little bit weird and I can try and explain to you how I think about it。

 but basically what this is trying to do。

![](img/015aec1d2084e65be62a50b75655afbc_72.png)

Is if you think back to our earliest example today around default， you probably noticed。

 and you might have been thinking about this。That when you create a stack。

Of floats with an unordered set of floats or even a vector of floats we having to define float twice。

 Now， if you're a good little programmer。That hurts you， right， You're like， oh。

 why are we saying that twice like。Bad things can happen。 And， in fact。

 I'll show you how bad things can happen。 Watch this。I can make this an int。 And in some cases。

 I mean， I I， an int might fail， but。Anyway， it's like。Maybe not that one。s all that is void stuff。

 I'm pretty there's some circumstances where you might be able to do that validly。Where you have a。

A container that's taking in a type T but the actual you have your class we're just taking in a type T and storing it in a container of not type T like so do you like how do you constrain that now I know you asked beforefoca how do you constrain the types。

 this is a very specific example of that and I'm sure you're asking broader but this is a specific way of how you can how you can basically instead of saying float and a standard vector of floats。

 just say float and standard vector。Just give， like give me the generic type and like。

 give the class the generic type， and it'll figure out that it's a standard vector it floats。

 You know， like it's， it's cleaner， It's simpler， lesser room for error。

 So it's good that that's possible。 The downsiders that syntactically， it's kind of a nightmare and。



![](img/015aec1d2084e65be62a50b75655afbc_74.png)

嗯。I kind of have this on the left here， right， I don't know why I went back to that example。

 but it's like instead of saying a stack of instant standard vector events。

 you just want to be able to say stack of instant standard a vector。

 stack of floats and standard a vector。So how to do that is that we create template template parameters。

 Now， the top example here， the， the top two are the example。

The normal example without the template template parameters， where we just simply say， okay。

 our class is has a type name T and a container， and then we specify int and a standard vector events。

The second example is when we use a template parameter and we say。

 actually we've got a template here。Which takes in a type named T， which is like our inter float。

 and then it takes in a type name cont。Which itself is primed。By something。

And it's the same function。 It does the same stuff。

 And the only other difference in the library that you'll see is that instead of just saying conier。

 which used to be a whole type like a standard vector of n or a standard vector of float。

 now we actually say con of T。 Now， intuitively this makes sense because before we were like。

Stand a vector of int。So you didn't need the tea。 And now we're saying standard vector。

 So if you just think about copying and pasting it， it's like， well。

 we need the tea now because we haven't specified what the type of the vector is And this feels nice right because this tea relates to this tea up here。

 So you've kind of got those two things those two things joined。嗯。In that way。

 and it does allow you to write simple code like we've got down here。 So if I go to， you know。

 demo 810。Template template， I've already compiled this it looks like。Sometime a couple weeks ago。

 it works。 I don't think it does anything。Just push this stuff， right， but it works。 it compiles。

 compiling off the battle with this stuff。So that's really cool。

 Now let's take a look at what in God's name is happening here。 So here，'s。

 here's the way I think about it。 It's like your template takes in。 okay。

 you have a class called Sta。😊，When you put template at the top of it。

 you're saying that this stack is a template type， takes in generics， it's a generic type。

Then you give it the templates。When you say type name T here。And this。

 you are now telling it how many templates it has， Basically， how many arguments inside the the。

 the side brackets do you give it，1，2。 So you're gonna need two lines there。

 You're gonna need two things between those， those， those。So I。Side areas。

 Ive suddenly forgot with the cold。嗯。Yeah， so。Now。The first one is easy。It's like， okay。

 there's two things I'm templated on。 The first one is just a T。 It's it's a random type called T。

 The second one is a random type called cont。 So if you actually forget about this for a sec it looks the same as what we had before。

 We're giving it two types。 The only difference is by adding this at the start you're actually telling it a bit more about what con is。

Here， Con is a concrete type。 It's a fully resolved type。

 It's something like int or float or standard string or standard vector of T。 It's a nontempd type。

 right， Like， sure， like standard vector is a templateative， but this is a concrete type。

 It's not begging for more information to tell you what it is。

 It's like it' you've been clear about it。 If you do， you know。

 if you do a standard unordered map of ins and ints。 It's like that's a fully concrete type。

But like a standard unordered map is just still a generic waiting to be made concrete。

 and a standard vector without an inn is just waiting to be made concrete。

 So if we want to use standard vector here， then we need to put out the front of this。

Template type name。Putting template type name out the front。

 what it says is that Conant has a templated type。That has one type name。 Now。

 this will work for standard vector right， which I think is what we have here。Stand a vectorto。



![](img/015aec1d2084e65be62a50b75655afbc_76.png)

Oh， not， Why not。Yes， okay， sorry。 I， I got my data structures mixed up。

 But let me show you the problem here。 So here's the problem。

 You think standard vector just has one templated。Argument， right。

 It just takes in that that what storing。 But if you actually go to the CPP reference。

 you'll see that templates actually are templated on two different types。Both the class T。

 which is the type you're dealing with and a class allocator。

 which is kind of above my head to be perfectly honest。 But it's basically a way that it， it like。

What is it。I remember how to explain this once， but it， it's to do with。嗯。Yeah， I mean。

 the language I can't summarizeise is better than the languageca it's very clear。

 but's it's how it essentially allocates resources and there's a default one that you've probably never really worried about and I've never worried about before。

 but the point is the vector takes in two templateative types。Two of them。So therefore。

 to make this work， I have to say type name， type name。And that still doesn't work。

 What have I screwed up here。 too few template。Oh， no， I've made a mistake。 That's okay。

 The point is that this here， actually， like the point is that what this needs to do is this needs to reflect。

What the type name count you give it。 So if you give the type name count to standard vector。

The template of things on the left here need to reflect what a vector expects or something along those lines。

 So typically， we get around that just by going。Template type name dot dot dot。

 because just like veryatic templates we saw before， this is a way of saying some list of type names。



![](img/015aec1d2084e65be62a50b75655afbc_78.png)

So now when I compile this， there could be one type name or two or three or four。

 and it will still work。

![](img/015aec1d2084e65be62a50b75655afbc_80.png)

Anyway， that's the whole background and rationale behind that。Super， I think it's interesting。

Think I use that once in my life。For something pretty random， but certainly interesting。嗯。Yeah。

So that's， that's pretty much it on。Templar template parameters to loop back to Kai's question。

 how can I constrain my types， So it only takes types you want to upcast or something。

 I I still think probably the only advice I would be able to give。 I mean。

 maybe there'd be more interesting people that could give you advice is like。

 if you write your code such that。Only types that are safely upcasted are valid。

 then the compiler will handle those constraints for you by basically。Being a compile error。

Is the idea， Sir。Yeah， and then last thing in this course， o， sorry。

Richard says so since a vector expects two type names。

 you do this so you can use a container which may require multiple types to construct Yeah exactly。

 so the the type name dot dot dot thing essentially says like whatever container we give it if the container expects。

One argument or two or three。 Like if the container is templated across one type name or two or three or4 or5 or many。

 still make it valid， of course。This， though， will only work。For types。

 templated types that only require one。They only require one type to be made concrete because like an unordered map。

 for instance。

![](img/015aec1d2084e65be62a50b75655afbc_82.png)

An unordered map in C+ plus。You can see here that an unordered map requires you to specify the two template types。

 but the way this code is written。

![](img/015aec1d2084e65be62a50b75655afbc_84.png)

You only have one to specify here。 So you probably have to do like a。I mean。

 maybe that's another case of a partial specialization。Baby， I don't know。

 but like the point is that this can work on any container type regardless of how many type parameters it has。

 it's just that only one of them can't be defaulted because like it's just not how you've written。



![](img/015aec1d2084e65be62a50b75655afbc_86.png)

The the the library here， I guess。嗯。Yeah， and then lastly。



![](img/015aec1d2084e65be62a50b75655afbc_88.png)

Just quickly on this topic because some people have asked it before。

 there's this notion of template argument deduction， which is quite relevant。

 which is that what the compiler actually does is that the compiler。

Determines the type of the type parameters and the non type parameters basically everything in the template line。

We determine those by looking at the coal parameters。Now。

 the core parameters are sometimes what we call arguments。

 which is that when someone calls Find Min the compiler， if you don't tell it what。You know。

 generic types to use。 it will actually figure that out from the arguments。

 And what we mean by that is that。If you have a， if you have a templated function here called F。

 which takes an a T star that you call a arrays appointed to a type T， when you call。

When you created a C style array of ints and you say F of a。The compiler is like， hm， what's a。

 A is a pointer to ins。 Great， So then it looks at this and it says， all right， well。

This can take an appointed to something， and I have appointed to int。 So therefore t must be an int。

 So I'm going to instantiate the end version of that。 And the same kind of thing you know。

 works throughout here。It will do。It trip。That's okay， so the the three。

 so that was just the example， but generally it wants to match the type exactly。

 the three times it will implicitly match it， though are an array to a pointer。

 which is the example I just talked through a non cons to a cons。 So as you can see here。

 A's cons A's non cons， but this actual templated type。😊，Argument is constant。

 but it'll do that conversion。 And then the other one is derived base type， super type subtypes。

 just all the O O stuff that we're going to be talking about next week。Alternatively。

 you can always explicitly deduct things if you want to。This is kind of a。Actually， so Pyn just said。

 wouldnn't it be better style to use implicit since it's simpler or worse since you might lose some info while reading Yeah。

 so in general implicit deduction is okay unless you think you need to communicate that to someone one thing you've got to be careful of though is like if we have a templated function like min here and we have a main function that creates an end a double。

If I call men with I and end and then I static at cost。D， the double to an inch。It all。

 because I I gave it to in's template argument deduction will think T's and int in this case here。🤧U。

But if I wna， if I want to actually tell it what I wanted to do with it， then I， then sometimes the。

The explicit deduction can be useful by saying min double here。 I'm actually telling the compiler。

 can you go and instantiate a version of the min function where t is a double。

 And then I'll give you two parameters。 One of them is an ensure but we know you can upcast an it to a double without a loss in precision。

Yeah。Yeah。So that's one instance where you might want to do like an explicit deduction， for instance。

 So these are just different ways of essentially like these two ways you're getting the compiler to deduce it for you and the commented outline here and then this line here are ways of you telling the compiler no no no don't deducted I'm telling you exactly what it is in this case here。

 this one's commented out because even though the compiler will try and instantiate a int version of this min function。

 the problem is that Ds a double So I think you get a compile error or a warning is an error that's like there's a lost in precision here because the double might be bigger than the int。



![](img/015aec1d2084e65be62a50b75655afbc_90.png)

But that's that's that's template argument deduction。 and that is why you've been able to do things。

 and you I think I've done this by accident where you can say auto S equals standard vector1，2。

3 because the compiler is able to look at those ins and be like looks looks like looks like I know what the T is there It's pretty unambiguous what the type is So it'll just go and figure it out for you Anyway。

 any last questions otherwise we're gonna pretty much wrap up now because that's the end of it。



![](img/015aec1d2084e65be62a50b75655afbc_92.png)

Should put up the feedduct screen。I hope did I add the feedback in？I think I did。Yeah， I did。 Okay。

 Le feedback。 Thank you， everyone， for filling it in。

I I don't know how many people have been filling it in recently。 I haven't really looked much。

I mainly collect this at the end of time。Oh， feedback is sparse。Feedback is sparse。

m getting like2 or3 a lecture。Thank you whoever just filled that in。Average。

 how is the lecture average， excellent。That's good。K。Thank you for that。Kai says in Java。

 you can do generics like T extends and to say that you can only specialize templates that a subclass of N。

 can you do add and see plus plus。I don't know。Not that I know of， but I don't。

 I don't do a ton with。Templates regularly。So I'm not sure。Post that on the farm。

 I'll check with someone for you， too。M。Cool。Yeah， I'm not too sure。I mean。

 the the compile will do it for you with some kind of specialization。But yeah。

 the compiler will catch it。 I'm not sure if there's a more clear way to kind of signal that to someone though。

But anyway， I'm going to wrap up there and if you have any other questions post on the forum。

 otherwise I'll see you tomorrow night。

![](img/015aec1d2084e65be62a50b75655afbc_94.png)

Everything else， nice to see you all and have a great evening。

