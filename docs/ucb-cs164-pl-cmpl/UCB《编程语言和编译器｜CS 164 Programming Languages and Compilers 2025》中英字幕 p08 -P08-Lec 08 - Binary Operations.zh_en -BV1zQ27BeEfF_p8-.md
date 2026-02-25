# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p08 -P08-Lec 08 - Binary Operations.zh_en -BV1zQ27BeEfF_p8-

![](img/5198d3115891bf506642adc26b8aea03_0.png)

Alright， hello， everybody。 Happy heat wave。 I am so sorry that it is so warm in here。

 I believe it is maybe slim。Move down in the room， but I wouldn't swear to it。

 So feel free to shuffle around if you find more comfortable spots。 I am really sorry。

 and I wish it were better。 But thank you for coming and joining。 It's so exciting to see you all。

 As always， I'm going to start by thanking you for filling out the drills。

 I cannot tell you how much we appreciate it。 Really helps for figuring out what people are still stumbling on。

😊，This LED me to a couple things that I want to mention。 One is I。Folks mostly know about this。

 but for those who are like， oh my gosh， there are so many assembly instructions。

 I'm googling I'm finding a bunch of them and I don't know what to use。😊，Don't worry about all that。

 You don't need to like go through all of the various like like the X 86，64 instructions。

 There's a ton of them。 There are many very complex ones。

 All the ones you need to know about are gonna be in the resource that we have on the website for you。

 So you can just go ahead to the website and see the resource that talks about the assembly instructions that we are gonna need for the course of this class。

 and also sort of the little M okay library that we have that actually generates stuff in assembly。

 So all the details you need should be there。 No need to like go around po around seeing other things。

 Let's see what else about。😊，Drill responses， oh。Okay， yeah。

 so one was we are still gonna be dealing with  tagging to a certain extent。

 So those of you who have started homework are probably familiar with the fact that we are still dealing with type tagging。

 But in terms of sort of the lower level operations that we use for type typing。 So like。

Bitwise or bit wise andt， we are not going to be going over those either in class sessions or in section。

 So for that， spend a little time on the Wikipedia if you're not yet comfortable with bitwise and bitwise or that kind of deal。

And one final thing that I wanted to mention one final thing that I wanted to mention was about a word that has been cropping up in some of our responses。

 I keep seeing the word convention oh， I'm trying to work on this。

 but I'm distracted because I don't know the convention for X。

 or I have been doing this and this and this。 And then I realize I don't know the convention for Y。

 And that's what's really tripping me up。 I would love for us to just erase that word from our vocabulary for the purposes of this course right in general。

 there isn't any part of our compiler where you need to have memorized the convention because it's all right there in the source code。

 And you've seen all of that source code being built up So you can just go look through compile Ml。

 look through interpret Ml， look through whatever the equivalents are。

 right like you can go through and see， oh yeah， we went ahead and we put that value inside re。

 We went ahead and put that value in this other place。 That's all you're gonna need to know。

 It's always gonna be right there in the source code。 None of this is magic。

 There's no magic behind the scenes that's sort of making things happen that you' all are not seeing。

 You can always just look。source code。There are going to be a couple of times where we need to know a little bit about the C conventions。

 but that's really just so that we can then communicate back to our C runtime if you remember the thing that's actually calling entry。

 we had to know that okay， it was going to expect to find its answer inside RAX， but other than that。

No conventions， none of the time。So hopefully that's feeling okay to folks。Okay， cool。

Our main topic for today is going to be binary operations。 I know I shouldn't play the favorites。

 but I do think that what we're about to do is just so pretty。

 And I think we're gonna to have a very good time。 But first。

 I want to make sure that we actually wrap up what we didn't quite finish on last week。

 So let's return to where we were last week。 And what we had basically figured out was the new。😊。



![](img/5198d3115891bf506642adc26b8aea03_2.png)

Things we're going to use on the assembly side in order to implement。



![](img/5198d3115891bf506642adc26b8aea03_4.png)

Are if。 so we can see that right。 Yeah， great， Okay。

 So these were the new instructions that we got right at the end。

 which was basically the idea of jumps。 So in particular， we met two new jumps。 We met J Z。

 which is going to jump if Z F， the flag Z F has been set to one。

 That's the situation where that one is actually going to cause a jump。

 So that will be a conditional jump。 And then we have jump L， which is just going to jump to label L。

 regardless of whatever else is happening in the state of the computer。So， far， Ser。Amazing， okay。

 so now I want to talk about how we're actually going to use those。

So this is how we are going to take advantage of JZ and Ju in order to actually implement our。

So here we go。 We've got our sort of if expressions that we met last time。

 we had already decided how they're going to behave。 if you remember we had decided that okay。

 we're going to go ahead and compare this to false。

 right so we're going to go ahead and evaluate whatever is associated with our test condition。

 we'll compare that to false。 If it is indeed false。

 then we want to go ahead and do whatever is in this else case。

 Otherwise we want to do what's in this then branch。

 And that's all that we're really thinking about here。

 And so I want to talk about sort of how we are laying out the code in order to actually achieve that。

 So okay， we can enter entry。 That's all normal。 We go ahead and put in the assembly associated with our test condition。

RightSo the sequence of assembly instructions that it's going to get the value associated with actually executing o sorry actually executing test。

 we're going to make sure that the sequence of instructions associated with that is going to put the value associated with test inside RAX。

 then we can go ahead and compare whatever is an RAX with our value that represents false right So if we recall this is false。

And that's what we mean when we do that comparison。And then we're going to go ahead and say， okay。

 well， if we find that this is in fact， exactly equal to false。

 the very next thing that we want to do is jump to else。

So we have down here an else label followed by the assembly instructions associated with actually evaluating。

Else。On the other hand， if we reach that point of doing the comparison with false and we find that the value we have inside Rx is not the value false。

 then we want to go ahead and not do this jump， right？

 So that's why we have J Z here instead of jump。 It is going to go ahead and do that jump only if what we have in Zf is one。

 In the case where we actually do this comparison and it is not false。

 What we'll have inside Zf is 0。 And so then we'll just go ahead and pass through to this code。

 The code associated with。And then at the end of actually executing that。

 we want to go ahead and jump down to continue because remember。

 we do not want to actually evaluate both the then and the else。

 we should only ever evaluate one of them。 So if we're in this then case。

 we want to make sure that we jump over what's inside else and we go straight to continue。

 which is just the we're going to use for whatever it is that we're doing after this if expression。

Are there questions about this overall structure that we are going to use for laying out？

The assembly associated with if expressions。So far， so good oh yeah。再要さ。Oh， interesting。

 can you run me through that question one more time。Like it jumped right。Haan。

I'm not totally sure I understand the question， but let me try sort of rephrasing it and seeing if this is answering what you're asking。

 So I think this question is， what is it that is going to appear after continue。

 Are we just going to sort of start again with entry。

 Are we going go ahead and evaluate this entire thing all over again， And the answer is no。

 But in fact， in this case， we won't actually have anything coming after the continue。

 Because as soon as we finish executing this， we're done with this program， But say that instead。

 we had something like add one。And then applied to this if。 Well。

 then we would need to actually go through the process of having some kind of an addition that happens here afterwards that is going to operate on whatever came back from evaluating this。

 And so all of the code leading up to here would make sure that the value associated with evaluating the if is now inside R X。

 And then our add one would just go ahead and do the addition based on needing to now add one。

To whatever is inside REX， Does that answer the original question？Other questions about this？

In that case， let's go ahead and do it。So last we saw we had done this process inside the interpreter of making ifs available。

 and the only thing we had to do there was take advantage of the fact that OKm already has if expressions。

 and so we said okay， let's go ahead and interpret the test expression， let's compare it to false。

 if it is false， then okay， we're going to go ahead and do the else expression。

 otherwise we're going to go ahead and do the then expression。

So let's go ahead and see what we've got over here in I've actually typed this in in the interim and so I'm just going to talk through what's happening here。

 it is literally just exactly what you saw on the whiteboard， and so we say okay。

 the first thing we need to do is generate the assembly associated with getting the value of test expression into RAX then I'm going to compare that to the value that we use to represent the Woan false。

And then I'm going to go ahead and jump to the else case only in the situation where this comparison was actually true。

 right， where we did find that what was an R X was the value false。

So that's what JZ is actually doing for us After that we'll go ahead and have the assembly associated with evaluating the then expression。

 we have our jump to continue， we have the label else。

 and then we go ahead and have what we have associated with the else expression。

 all of the assembly that we would use to get that value into RAX。😊，Great question。Oh， interesting。

 Okay， I think I understand the question。 So this question was， what if we took。This， and put it。

Here。And then we could just evaluate both of them。This is saying。

 what if we could we avoid the case where we have to jump for both and in one of the cases just fall through And in fact。

 that is exactly what we're doing right， So in this case， right， where we see that， oh， okay。

 the jump does happen， that's only happening。 if we found that the value inside RX was the value false。

 Otherwise， we just go straight through to this condition。Right。

 so we just go ahead and fall through if we're in the situation where we had true。

 where we had three， where we had anything other than false。

 we go ahead and just carry on to this thing that is associated with the then expression。 However。

 we still have to do the jump at the end of that because we don't then want to do all of the assembly associated。

With the other condition， right， So one way or another。

 we have to make sure that both of these end up at continue after doing only one of the branches。

 Does that make sense。But yeah absolutely， what's happening here is that we're falling through in one of the cases。

Other questions。Okay， cool。 So we're getting pretty close to what we're looking for here。

 but I'll give you a little bit of a spoiler。 We're not quite there yet。

 So let's see a bit about why。And let's do compile and run。And what shall we run， let's do if one。

 two， three。Okay， so far， so good。What about。哇哦。So what has gone wrong？Well。

 we can take a look at program。s to see exactly what is gone wrong， right else？Else， ha。

That's not good， right， When I see something that says I should jump to else。

Which of these do I jump to， Oh oh， go ahead and brainstorm for 30 seconds。 What should we do。

 Just turn to someone nearby。All right， what do we think？What shall we do？Ids。大変なも。I love it。

 Let's do that。 Absolly。 That is exactly what we're gonna do。

 So let's make ourselves a little helper function that says， basically， okay。

 we're in the situation where we need sort of a unique version of else for the specific else that we are in。

 We can use a counter to do that。 So let's go ahead and maybe do something like this。😊，Now。

 this looks a little bit different from the Ocama we have been writing before。

 So let me go ahead and first show some examples of running this little helper。

 and then we'll figure out what's going on and why this is sort of wacky for us。

 So let's do gens else。Okay， else， underscore underscore zero。Genss Els， who。

 else underscore underscore1。お。Under underscore 2。It's okay。If you're sort of comfy and Python land。

 maybe this isn't sort of a shocking thing to have happen where we're applyinging the same。

 know we're giving the same argument as an input， but then we're getting back a different output。

 but we've all spend a lot of time in okay Molan now。

 and probably we're feeling like this is a little bit wacky。 This is something that's kind of weird。

 We haven't seen before where we're actually going ahead and getting back something different even though we've provided the same argument。

 This is no longer a mathematical function。 because one of the expectations of a mathematical function is if that we provide the same input。

 we're going go ahead and get back the same output。 And that's not happening anymore。 And that is。

 of course， by design， the reason we are doing this is trying to make sure that we never have these overlapping labels that we're going to be able to generate a unique label that we haven't actually used in the past。

 And so we are going to want to be doing something like that countert suggested by the audience。

 And so what's going on here is we're introducing the idea of a reference。

RightAnd so in contrast to when we have used let bindingding in the past where we have used it just to give a nickname to a particular value。

 what we have here is basically a cell that we get to pop values into over and over again。

 something more like what you might see in the imperative languages that you're comfortable with and so what's happening down here is we're saying okay we have this little bank syntax that's saying go ahead and find whatever is inside that reference cell give me a sort of a read from that and then we do our little add one and then this colon equals is basically assignment saying I want to go ahead and overwrite what whatever was in that cell before with what I now have on the right-hand side of this assignment。

I also want to note real quick that this is the idiomatic way to use sort of mutable state in okcal。

 and in particular， the thing I want to draw your attention to is that there is no way to mess with counter except by calling gensim So if you look at what gensim actually is right it's just a name for something that we are going to be able to call and how do we get the thing that we are going be able to call while we execute the expression that we see right here on the right-hand side of this equals and what is that expression Well。

 it's a lead expression where it's saying okay， I want to have this ref cell available under the name counter inside the body of my lead expression and the body of my lead expression evaluates to a function and that function is then the thing that gets named gensim。

And so now the only way to ever access counter is by calling the thing that ends up being called gensim。

 which is to say this function。Are we feeling more or less okay with this idea。 In fact。

 we could put a whole bunch of other things in here。 And all of these would only be executed once。

 right， We can't access those ever again。Feeling pretty okay with this idea。

 Do we have questions about this， yes。What if you give it a different name than else。

 is it going restart the counter。 Great question。 So this connects to the answer I just gave。

 which is saying we actually only ever run sort of this program that decides what gensen is exactly once。

 right， And so we are just going to have like， if we give else。 But then later we did。

 then it's all going to use the same counter。😊，What is a cell under the hood。

 We are going to talk about that later on in the semester For now。

 we're not really going to think about it all that differently from the way we think about names。

 except that it is mutable。 So you can think of it as a name where we have now instead of saying this is fixed forever。

 we are instead going to go ahead and give you access to this new syntax that you couldn't even use if we hadn't had this ref right here。

 We're going give you access to this new syntax that lets you right back into the place where you had saved that original value。

Yeah。So I will say something about sort of how labels get generated in。Well。Honestly。

 this is kind of a discussion for later in the semester。 So there are other ways to do this， right。

 This is a simple way that lets us really quickly， right， Like we run out of。

Slots to put assembly code in the program before we run out of numbers that we can have in this label。

 right， Like we're simply not going to be dealing with that overflow case。

 and therefore we take the simple approach to implementing。But yeah。

 there are other ways that we could right what we need is to be able to have a unique label for each of the places that we are trying to make a unique label。

Great question。 So this question is， hey， we suddenly we have mutable state。

 Can't we just basically write imperative programs instead of functional programs now inside Ocal。

 And the answer is absolutely yes。 like you could just use this to recreate everything you love and hate from imperative languages right Like we are not actually locked in to doing things in the way that we've been doing them where we are using these immutable let bound names。

 So absolutely， in fact， what we are doing right now is kind of sidesteping that constraint。

 like we do now suddenly have mutable state。 This is the only place we' use it right everywhere else。

 everything we've done in the last month or so， we haven't used that。

 All of the rest of the compiler has just been built up on our sort of standard let bindinging。

 And now for the first time， we're choosing to sort diverge from that。

 but we are doing it in sort the idiomatic okcal way where we say， okay。

 this is the only way you're gonna to be able to access counter。

 we've sort wrapped it up in a way that's not accessible outside。

 we're sort trying to prevent people from running into the bad things about state where you know somewhere down the line。

 we accidentally reset counter now suddenly we're getting collisions。 is。😊，the as yells at us。

 We're sad。 So we are trying to avoid the bad things about state to the extent that we can。Okay。

 cool。 let's try using this。 So here we go back into compile。 What are we going to do here Well。

 we're probably going to start using。Genssim， so let's see。If I do。This。

I'm going to ask you to reflect with folks nearby。Is this going to work？

Go ahead and chat for 30 seconds。All right， hum for this solves our else problem。

Hum for this does not solve our else problem。Yeah， I totally agree， right。 So like previously， again。

 up until this point， because we have never used a function where we would expect to get something different back based on having the same expression as input。

 we would have always been able to do this， right， all of our previous functions that we've made。

 if we go ahead and provide the same input。 we would go ahead and get the same output。

 And so this would have been totally fine。 Now， all of a sudden， that is not the case for us anymore。

 So we have to be a little bit careful about using this compared to the things that we have done previously in the past。

 So let's go ahead and say， let's。😊，Else label。And we'll go ahead and seal that out。

And we'll make our continue label。And let's use these。 So down here， we want to jump。To else。

Here we want to do continue。Okay， and now these should agree because we've gone ahead and just actually made the call once。

 given it a name that we can then reuse。So discuss with folks nearby another 30 seconds。

 have we now solved it， Is it now going to work？All right， hum for， we fixed it。Hummre。

 we haven't fixed it。See， you have such good baseline assumptions about the fact that I'm going trick you。

 But no， actually， we have。 Oh， no， what did I do wrong。Wow， yeah， that was supposed to work， oh。

 I did I'd not recompile。Oh， no， what is going on？I'm still calling it in there。 Oh。

 thank you so much。 Oh my gosh。Yeah， see， staal getcha， watch out。Okay。Allright， now， now I last。

 We have fixed it。 So okay， now it is no longer complaining。 We don't have these overlapping labels。

 Everything has nice names that we are， are comfy passing off to the asmbler。

So now we have it expressions， we have conditionals。 We have a language， It's doing stuff。



![](img/5198d3115891bf506642adc26b8aea03_6.png)

DoWe have questions about this？We feel maybe like tackling some binary operations next。Cool。

 all right， let's do it。So here we are。 We're over in binary operations land。



![](img/5198d3115891bf506642adc26b8aea03_8.png)

What are we going to do over here？ Well， I think honestly。

 these are going to be pretty familiar operations to everyone。

 I don't think we should be feeling a lot of surprise about what we're actually going to be implementing。

 but I'll just real quick jot us some notes about the types we're expecting。

 So we're expecting that to be a number， expecting that to be a number。

And we want to get a number back out。Same deal for our subtraction。For our equals。

 we'll be a little bit more flexible about what we're getting in here， so they like whatever。

Right who cares， But we do want to get out a Boolean。And over here， we do want this to be a number。

This to be a number。And what we get out will be a booleion。Hopefully that feels relatively natural。

So far， so good。All right， cool。 So let's go ahead and try this out in our interpreter。

And from there， we can move towards our compiler。So back to Inter。ml。What have we got in there， Well。

 we're going to want to make a case for。Plus。And we're going to go ahead and have。E1， E2。

 And here you might already start to notice something that's a little bit weird。

 a little bit different。 Like up until this point， we've really been mostly。

 except for our if expressions， dealing with just one thing coming in。

 So this is starting to be a little bit wacky。 So what is something that we probably want to do here。

What might we like to do with E1 and E2。 Go ahead and discuss with the folks nearby for 30 seconds。

Alright， what I'm hearing in the crowd is that we probably want to run these two expressions somewhere。

 right， Like we're gonna want to go ahead and get whatever value is associated with E1。

 and we're gonna want to go ahead and get whatever value is associated with E2。

 And then we've got to do something with it where we probably check the types。 And I totally agree。

 So let's go ahead and do our match。 Let's do it on the pair that includes。The results from those。

 And then what we actually want to match with， well。

 we know what to do in the case where we have a number。And another number。So that's the case where。

 okay， let's go ahead and make ourselves another number。

Based on adding those two numbers and what do we want to do in any other situation， Well。

 we want to go ahead and raise。Bad expression。 that feels good to me。

I'm going to go ahead and just quickly rename this away from program to X。

 I think that's actually closer to how we are treating it。

 like we're treating it as an expression rather than as the full program we are doing these recursive calls and so just to emphasize that I'm going to go ahead and call that X now。

So， okay。This seems like it is doing what we want for addition， do we have questions about this？

Maybe we can just try it out real quick。Ku，5。So far， so good。Amazing， let's do something honestly。

 relatively similar for our others that we are trying to add right now。 So let's copy this。

And let's go ahead and handle the case where we're doing subtraction。

We want to change to be subtraction shockingly enough。

Now what's going to be different with our equals well？

We no longer need to really do any of this type checking because actually。

 we're fine with comparing whatever。 We're just trying to see if they're the same。

 So let's go ahead and get rid of all this stuff。 And let's just make Boolean based on whether Interp X applied to E1 is the same as inter X applied to E2。

And that's enough for checking equality。let's go ahead and do our last one。

 which is to say our less than this one is maybe a little bit wackier， right。

 we are still going to need to do our matching。And we are， in fact。

 going to need to check for numbers， but what we want to get back isn't going to be a number itself。

 instead we will be giving back a boolean based on whether N1 is less than N2。

So let's go ahead and real quick。Check those out。Be thinking of any questions？okK。😔，Less than two。

 three。Good。Les than three， two。Also good。So far， so good on our interpreter implementation of our binary operations。

Okay， cool。Well， in that case， I think it's time for us to look at how to do it with our compiler。

Let's take。This pop it right into compiledMl。And start thinking about what to do next。

 So here's sort of the first thing that I would think of。

 If I was thinking of what we just did in interpreter land， I would think， okay。

 we're going to want to call compile X on E1。And then you know we're maybe going to want to do something where we call compile X on E2。

 and then we're going to want to combine those values in some way。However。

 we are not going to be able to have the snippet of code that I just wrote inside this section。

 Why not discuss with folks nearby for 20 seconds？All right， did you want to throw out an answer。

 There was an answer back there。 Yeah， go for it。Yeah， we are just going to overwrite R X。

 If we think about the role of compile X， the whole thing that it's supposed to be doing is giving us a sequence of instructions that when we run them on our processor is going to put the value associated with the expression being compiled inside R X。

 So this is saying， okay， go ahead and figure out the value associated with E1 and put it in R X。

 Now， go ahead and figure out the value associated with E2 and put in R X， right。

 Clabbering what we had in there before。 Not so help before us。 So okay。

 let me propose an alternative。 And we can see if we like that。 So let's go ahead and between those。

 I'll add this instruction。😊，O， a new register， we are now seeing an additional register cool。Okay。

 now we can go ahead and keep doing our compile X。 and then let's do。O。

So let's see a little bit about what happens when we try this。 right， We're。

 we're clearly avoiding the situation where we are just overriding what's inside RA X。

With the the sort of one after the other calls， right we're going to go ahead and we're going to store off whatever we got from evaluating E1。

 We're going to put that inside R8 for a moment， and then we'll go ahead and do our compile X per to all the assembly instructions associated with that。

 that will put somebody inside R E X that we want。 And then maybe we can go ahead and do this edition。

 So let's try this。So plus one，2。I like that。 That is three。 That feels good。Okay， now how about。

Plus。Okay， I also like that， right， that's six， that is six， great， so far so good。Now。

How about we change the grouping somewhat。 So let's do。哦哦。That is not seven。

 I do not like that answer。What has gone wrong， go ahead and discuss with folksols nearby for one minute。

 what's happening？All right， so what has gone wrong？At a high level， we're saying， okay。

 let's take our runtime representation of one。 We'll put it inside R X。 Okay。

 that's one of our intermediate values。 Let's go ahead。 Let's store that over inside R8 for a second。

 Let's hide that away。 Let's stash it。And then we're saying， okay。

 let's move our runtime representation of two inside R X。 But okay。

 we're about to do an addition that involves that。 Let's go ahead and hide that away。

 Let's stash that。 Let's put it inside R8， right， So then we have overwritten with the。

 the spot that we are placing our intermediate values。

 So let's actually walk through this real slow on our whiteboard because I want us to actually see this happening。

 right， So here is。😊，A one， it's showing up right there。 Great。

 let's go ahead and move that value inside R X。 So far so good。

 And now we want to go ahead and save it。 This is one of our intermediate values。

 Let's put that inside here。 We're saving that runtime representation of one。 Co。

 Let's switch colors。 because now we're gonna go ahead and start messing around with our runtime representation of two。

 So let's go ahead and cross out what we previously had in R X。 No problem， right， Okay。

 it's totally fine that we are now putting something else in Rx because we have saved off that other intermediate value。

 So we're still good to go all good， right， So let's go ahead and put 8 in here。😊，Yup， looks good。

 And now we start getting ourselves into trouble。 right， because now we say， okay， well。

 this is one of my intermediate values。 And I want to go ahead and store that over inside R8。

 and now we have overwritten that 4 that we thought we were going to keep in there because we are actually going need that later。

 And so we're gonna see how that runs us into trouble down the line。

 So now we go ahead and we over write， Okay， sorry， actually， let me switch colors。

 again to represent that we're now messing around with our representation of 3。

 So let's go ahead and put 12 inside there， great， we've got 12 inside there。

 We are now ready to do our addition of these two numbers。

 We go ahead and get 20 fantastic so far so good。 And now the part where we thought that we were gonna be adding this value and this value。

 instead we have ended up in the situation。 we're adding this value and that value。

 We didn't intend to be reusing that。 but we overwrote。 And so now we get 28。

 which is to say our runtime representation of 7。 And that's how we got our wrong answer there。😊，收。

What else can we do？How do we deal with this？Go ahead and brainstorm with folks nearby for about a minute。

Alright， so this is kind of weird right Like you can imagine okay well。

 let's start keeping track of which registers we've already used and we can keep sort of going to the next currently unused register and we can keep putting intermediate values there maybe we can come up with some kind of scheme Now the problem with that is we've only got 16 of those we're probably going to want to have programs that have more than 16 intermediate values。

 What do we do if we just run out。Anyone want to take a guess？All right。

 so we've got our surprise topic making an appearance today we get to learn about the stack so that is what we are going to do in order to handle this situation of we might have whole bunch of intermediate values that we're going to need to keep track of for some amount of time。

😊，So now let's go ahead and meet our representation of the stack for the purposes of this class。

Here we are。 We have the stack。So what's going on here？Well。

 we're actually going to learn a little bit about what's been happening this whole time。

 And then we're going to learn how we can use this more going forward。

 So the first thing that's going to be happening here that we haven't actually noticed up until this point is that we have the callers。

Frame address。Right here at a particular spot in memory。

 which we are going to call RSP or RSP minus0 now what is RP RSP is just the name of a register。

 and it happens to be the register where we are storing basically the base of our stack。

RightSo we're going go ahead and have some insight now into how we have actually been communicating with the runtime。

 So if you recall， we have， where did I put the runtime， we have this runtime， which says， okay。

 you've got to give me entry， right？ I'm not going actually define entry here。

 and then we've been actually creating the assembly associated with entry。

 And then at the end of this， we have this RE instruction， which returns。Control to somewhere。

How do we know where， Where is it returning control to？ Well。

 that is actually answered finally now that we know about what's sitting in the stack。

 because this is the thing that is telling us where we are going to return。

So let's learn a little bit more about what's happening here。

 so the way that memory is laid out on the computer。

 we can think of it as we'll have low number memory addresses here。

And then we go down to high number。Memory address is here。

 but the the lowest in the stack that we will ever go will be right here， right。

 we can never overwrite the frame address associated with the thing that called us。

 It's really important that we not overwrite that or when we try to return control。

 Nothing good is going to happen。 Who knows where we will go。

 And so we'll never touch anything below here， even though there could be all kinds of things down there。

So we won't mess around with that for our purposes。

 We'll just have the stack growing up in this direction。

 where are we going to put things on the stack， Well。

 we don't want to be writing into what we see there at RP minus0。

 or we might also just call it RP because that has to be saved so that we can go ahead and return control when the time comes。

 but we absolutely can write to RSP minus8 to RSP minus-16。And on and on and on。

You might notice now a weird thing where I am subtracting multiples of eight。

 That's because actually we've got 8 bytes available in here。 And so this would be RSP-1。

 But for the purposes of this class， we're actually only ever going be writing these 64 bit things。

 We're going to sort of treat it as though it is a whole you know stack of 64 bit slots And so we're actually only going deal with these 8 by segments one at a time。

 we're never going break into those little segments between。 So let's cross that out and ignore that。

And we are going to grow。Upwards。Okay。What questions do we have about the model of the stack？

Or we feel friendly with the stack。Cool， all right， in that case。

 let's go ahead and take our five minute break。 we'll come back together at 431 after you've had a stretch in water。

好了 not是 what is the dumb question like。Because in computer security，1，6，1， right。

 we learn about like RP and SFP。 So like， where would this be， like。

 would this be like a different part of the stack or like。好好的这个。嗯。

I think I understand the question you're asking， but I think your question is about the names of registers。

 I that right No of this RP in the stack So RP is just the name of a register。

 It so happens that what we have based on the fact that we're interacting with C in our runtime when control gets passed to us what we will have inside RP is this specific address。

 the address associated with that address lie on the stack it。Like。

 let's say if it's like in C right， we call like the main function。

 then we have put like the like the safe frame pointer and then like the return instruction pointer like somewhere on on the stack。

 right When control comes to us， RP is pointing to the memory address where the caller's frame address lives。

哦。😮，That's what is an RP when we get control。Okay， so it's like a pointer to like。

It's a pointer to the specific spot where the caller frame address was put。

And everything above it is empty， blank， unused， or it might have been used。

 but it's allowed to be overwritten。But what is actually pointed to by， like。

 if we look inside the register RP and we see what value is in there， It is the address of。

The spot where we have stored the college frame address so right like RSP is actually pointing to like this spot in memory is just this address of memory and what happens to be in that part of memory。

 what will always be the college address。Ya， great question。 So， so for the caller's address。

 do you mean like the instruction of the collar， or is it like the position on the stack that contains like the。

 the collar。We will be getting into that， but we'll be getting into it basically a little bit later in the right。

 So like we're going to complicate this model， the stack a little bit more when we get to implementing functions。

 So we are going to be thinking a little more deeply about what's there For now。

 it's sufficient to just think of this as， okay， this is what is going to allow us to return control to whatever it is that called entry。

Becauseuse remember， right now， we only have this one function that we're implementing。

 It is all just entry。 as soon as we are making our own functions within the language。

 And I guess So I treat as a black box。 It just allows us to return to like wherever they call。

Alright， I'm gonna bring us back together。 So what we have seen in here is everything that we're gonna need to know about the stack until the point where we start implementing functions for our language up until that point。

 this model of the stack is going to do everything we needed to do？

 But I got an awesome question during the break about well。

 how did we get this specific value inside RP， right， RP is just， again， the name of a register。

 Why does that happen to have the address that is pointing to wherever the caller' frame address is stored。

 And that's because of， okay， if you recall， what we were doing with。Entry。Inside our runtime。

 we went ahead and we actually called entry the place where we called it was right here and what happens in C when we actually call a function is this behavior of putting the address associated with the college frame address putting that address inside the register RP so that's why we know that we are going to have the address associated with sort of returning control to right here。

 why we're going to have that inside RSP minus0， but the only implication that really has for us right now is that we have to avoid overwriting it so as long as we're writing to parts of the stack that appear above the address shown in RSP which should be good to go。

Okay， cool。So。That's where we've been left right now。 We've got this sort of model of the stack now。

 when we know a bit about sort of what parts of it we're allowed to write into。

 specifically anything that's sort of above RSP-0， right， we can't overwrite what's in there。

 but we can go ahead and write sort for our purposes indefinitely up to to the top。 Now， obviously。

 we all know about stack overflow errors We can't actually write infinitely if only But that again。

 it something for us to wrestle with on another day。

 So how is that going to help us actually solve the problem that we were dealing with。

 Let's start messing around with our compiler and see how we might use access to memory to fix the issue we were having。

 So I'm going first do something that is not going fix it。

 but starts to get at how we will actually use memory accesses。 So let's do mem offset。



![](img/5198d3115891bf506642adc26b8aea03_10.png)

![](img/5198d3115891bf506642adc26b8aea03_11.png)

Again， this is just a register like any other。And remember。

 we only want to go ahead and write to spots that are negative 8 or above offset from RP。

 So if we went ahead and did。This， instead of R8。What is going to happen？Oops， what did I do wrong。

 I left a comma in。 great。 So let's go ahead and。Try this version of our compiler and see what has changed。

So。This still looks good。This still gives us 7， right， So basically。

 this is exactly the same as what we had before， except that instead of saving things inside register R 8。

 we are now saving things in a particular slot of memory。

Specifically whatever slot of memory sits at the address seated in RP minus8。

 that's where we are putting it。 so if we can actually take a look at our program。

 we can see these square brackets indicating yep， we are going ahead and writing to memory now。

Are there questions about the change we just made？Were so far so good。

You feel comfy with writing a memory。Great， okay， so now let's start to move closer to actually fixing our problem。

 right， The reason the stack is interesting to us is because we can keep using slots and slots and slots。

 And so we're going to be able to store lots of intermediate values。

 So probably we don't just want to always use this negative 8 slot， right。

 We're obviously having the exact same problem that we have before。😊。

So let's go ahead and see what we can do。 So we are going to want to change something。

To avoid overwriting。And I want you to spend about a minute brainstorming with folks nearby about what we should do。

To avoid overriding。And then if you get to it， think for a moment about。

 should the thing that we do happen at runtime or compile time。So go ahead and discuss。Bless you。

All right， what do we think， what can we do？I love it。 Yeah。

 so let's start keeping track of some offset that we can use in order to actually figure out。Where。

In the stack we have available to us。 And from your answer。

 it sounds like you're suggesting that we should do that at compile time。 Is that right。Oh， okay。

 all right。 So yeah， let's now take about。Half a minute， say we've decided to start tracking。

Which part of the stack is actually available to us。

 can we get away with doing that in the compileilr or are we going to have to do it with the assembly tracking it at runtime。

 discuss for half a minute。All right， go ahead and hum if you think we can get away with doing this at compile time。

Go ahead and hum if you think we're going to have to do this at runtime。Oh， cool。

 There's controversy。 I love it。We are gonna be able to get away with doing this at compile time。

 which I know is so wacky。 But since we can get away with it， we want to， right in general。

 to the extent that we can get away with doing things at compile time。

 we do want to be able to do that if possible。 And I know it it's super weird to wrap our heads around。

 So we're gonna spend the rest of class really thinking about that。

 So the way that I am gonna choose to have us start keeping track of what's available to us。

 It actually pretty simple。 I'm just gonna give us another argument here to our compile X。

 It is going to be called stack index。 that is not a special string in any way。

 it's just the name I have chosen to give to this argument。 right。

 There's nothing special about the name Str index。 I could have called it unicorn。

 but that wouldn't be very informative。 So instead I'm calling it stack index。

 And that's gonna be an in。Okay， now Oam's mad at me。

 It says you're doing all these places where you're calling compile X and you're not providing the stack index。

 So let's first do the simple thing where we make sure that when we call compile X。

We are passing an a stack index。 And as a starting point。

 let's just have it be the same stack index that we got as our input， even though， in fact。

 we will have to change it a number of places。 Whoops， I didn't want that。 But that's okay。

 We can go back and fix that。 So all those places， it's good。Now。

 here's a place where it's not actually going to be good， right。

 So here's where we're actually calling it from compile。 We're calling it on that original program。

 We're gonna have to figure out in a moment what to actually provide as that first stack index。

 But first， let's actually figure out how we're using this thing。

 And let's get rid of where we added that extra thing。 Okay， great。

 So now for most of the places where we are actually calling compile X。

 We're going ahead and adding stack index is our first argument。Now。

 where that doesn't necessarily make sense is right here， right。

 So let's adjust our program to actually take advantage of the stack index。

 instead of just providing negative 8， let's have the stack index itself B。The offset。

 why is this not going to fix it for us。 Go ahead and discuss for a minute。All right。

 what do we think， H4， we fixed it。Homefor we have not fixed it。Yeah。

 I totally agree right So we're still just using the same thing throughout。

 we never actually change it。 So we're just gonna to keep using the same thing throughout。

 unless we change it somewhere。 and what's gonna to be the place for us to change it， well。

 we are going to go ahead and make sure that once we have used one slot that any next situation where we need to use the stack is going to use the slot above right so here we have just gone ahead and use whatever stack index was available to us sort of for the first usage and now we want to go ahead and say。

 okay， we really don't want to overwrite what's in that。

 we're really trying to preserve what's in that And so for the next piece of assembly that we are going to put together let's make sure that it is not using that particular stack index we've already used instead it should use the next slot that's available And so that's how we're going to go ahead and do that now that we've seen that I think we can probably guess that what we're going want to produce as the first input is negative8 so that that very first time that we use the stack index it's not going。

Overwrite what we had at RSP minus0。So do we have questions？About the changes we have made so far。

Okay， cool， let's see what happens。Hey， we got sick， we did it。

 We have managed to use multiple slots in the stack。

 we can see it right here right if we look between those square braces， we're seeing okay。

 negative 8， negative 16， we're just crawling up the stack using the next available slot。

So I want to walk us through this on the， the sort of whiteboard model of our。

Computer because I know this is a little bit wacky。

And we are also going to use this as an opportunity to see the stack in this diagram that we keep drawing。

 So let's go ahead and see what happens。 I have gone ahead and done a little bit of highlighting。

 so you can see that we have this plus 2，3 in blue。

 And that' sort of matched up with the blue text that we see in the assembly to show which part corresponds to which。

😊，Okay， now let's go ahead and go through it。 So the first thing we're going to do is going to put our runtime representation of one into RA X。

 so far so good， so far so easy。 Now let's go ahead and save off this intermediate value。

 Let's put it at the appropriate spot， the appropriate next available slot inside the stack。

 So that's RP-8。 Fastic。 We've put it at RP-8。 And remember these I'm putting them next to them。

 but you should think of them as pointing to that spot there when we are actually going ahead and writing a full 64 bits。

😊，Okay， great。 now let's go ahead and put the representation of two inside RX that's okay because we have gone ahead and we've actually saved off that value 4 that represents our other intermediate value。

 so that's totally fine。 And now when we go ahead and decide to save off 8。

 our second intermediate value， it's totally okay because we go ahead and put it here， not cloboing4。

 but instead using that next available slot on the stack。Awesome。😊。

Now we're ready to go ahead and put in our runtime representation of three， we put that inside REX。

 we are now ready to move off the last saved intermediate value into R8。

So we've gone ahead and done that and we're ready to do our addition。

 So let's go ahead and replace that with 20。 and now we're ready to go ahead and take that next saved value right so the one in RSP-8。

 let's put that inside R8。 So we put4 in great。 and now we're ready to do our addition again。

 let's get 24， which is to say our runtime representation of 6。😊。

DoWe have questions about how that played out。cool。Yes。😊，I like this question。

 So this is basically about like， which direction does it make sense to show the stack when we are drawing it in pictures for communicating to other humans？

 And so even though we are subtracting from RP， remember that that's because the lower memory addresses are here。

And the higher are here。Right， so we' are actually seeing this laid out as though we are just seeing the computer's memory all sort of laid out in front of us from top to bottom。

 right， we're seeing those lower addresses at the top and then the higher addresses at the bottom where higher means like a bigger number right so you can imagine that we're sort of starting at zero and going all the way down to。

 I don't know， some large number。Does that make sense。

 It's also convenient because this way we can draw it less though we're drawing a stack of pancakes。

 right， So when we're adding to the stack， we are adding to the top of the stack。 right。

 It's weird to put the pancake at the bottom of the stack of pancakes。But yeah。

 it's a convention like this is sort of the normal way that people in most parts of the world draw it。

 You can absolutely draw the other direction if you want。Okay， cool。We're in a pretty good spot。

 I do want to quickly issue a warning。 You are now in the position where you will be writing into memory in your own assembly real soon。

And it is really easy to end up trying to access parts of memory that you do not actually control。

 And then we get Sevas。 So watch out， try to only read from the parts of the sec that you actually control。

 Be thinking about this diagram that we've drawn and making sure that you're only in the parts of it that we are actually in charge of。

But now that we've had that little warning， let's go ahead and use the memory a little bit more。

 Let's go ahead and add those other things that we're interested in adding。

 and they're going to look honestly relatively similar in a lot of ways。

 So subtraction is going to look super similar。Let's go ahead and copy that over。

And let's turn this instead of an ad， let's make it a sub。What did I mess up there， O。

 I put it at the end after the bad expression， how'd that happen。Get rid of that， undo， undo， undo。

Great。Now when we do our change to subtraction。It looks good。 Okay。

 Any questions about subtraction or that feels familiar having now seen。Addition。Cool， okay。

 so let's keep going。 Let's go ahead and do our equality check。

 which is actually going to be a little bit different， right， So obviously。

 there is going to be some work in common here。 So we do， in fact。

 want to get the value associated with E1 into R X。

 We do also want to get the value associated with E2 into some register， right？

 And then what do we do with it after that we're not going to do addition。 Instead。

 we're going to go ahead and actually do。A comparison， right， We want to see。Are those two the same？

And in fact， we can't actually do this with the mem offset directly。

 and so instead we're going to have to go ahead and move what we have in that mem offset into R8。

 and then once we have that move done， we can go ahead and do our comparison。

Where we compare what's in our8。With what's in RAX。Feeling okay so far， so far， so good。Now。

 is it enough to leave it there？20 seconds to chat， are we good with equality now？

I've been doing this thing with directly trying to use the memo offset stuff throughout。

 I'm gonna fix that。 I'm so sorry。 I''re gonna have to do some more moves。All right。

 hum for we are now done with equality。Hm for， we are not yet done for equality。Yeah， I agree。

 In addition to the baseline assumption that I'm probably asking because we're not done。

 which is a good baseline assumption。 The other reason is even though this has now set the Zf flag the way we want it to be set。

 remember that we don't really care if the Zf flag is set to something。

 we're trying to get the value into RAX and right now。

 whatever is an RAX is just whatever was previously in RAX。

 which is to say the value is associated with E2。 That's not actually what we want in there。

 Instead we want a boolean representing what we have in the Zf flag。 and in fact。

 we already have a nice helper that lets us do that。 It is just this sequence of instructions。

 which we have used a number of times in order to figure out whatever we've got in the Zf flag and just tag that to turn it into a boolean。

 So let's go ahead and just do that same thing at the end of our equality check。Great。

 we've got that。 Now we want to do something very， very similar。

 but still a little bit different for our less than。 So， okay。

 we are gonna to want to go ahead and again get the value associated with E1。

 Get the value associated with E2。 We are going want to do the comparison。

 but it turns out that the comparison actually sets a bunch of flags。

 So the Zf flag is the one that it sets in order to actually indicate whether these were exactly the same number。

 There is another flag。 I don't remember what it's called。 It's called set。😊，Z， no。

 set Z is the one we already use。 set L is the one that we are actually interested in right now。

 So let's go ahead and make something comparable to Z F for Bo。

That is going to actually access not the set Z flag， but the set L flag。 We will call this L F to bo。

 And this is just doing the same thing except that it's checking for less than instead of checking for exact equality。

 So let's go ahead and do instead of Z F to boole， let's do LF to bo。

And assuming I have put these in the right order， did I， Yeah。

 R 8 is first before R E X because it's very easy to swap your orders。

 And if you have R X on the side and R 8 on the other side。

 then you're gonna get the greater than instead of the less than don't do that。

 But this is actually going to go ahead and behave well for us。It's okay。

We have landed on something that is tackling our new operators。

But there is something that's a little bit different from how we handle things in our interpreter。

I want us to reflect on that for- I'm sorry， Are there questions about this before we go into our reflection question。

Okay cool， take us right to our reflection question。 So let's go ahead and look at how we handled。

 say less than。Inside the interpreter。What is different about what we implemented inside the interpreter compared to what we implemented inside the compiler。

 discuss for a about minute。I'm going to ask a follow up question。

What should this program evaluate to？So let's real quick see what happens if we actually run this。

Okay。That feels okay。 I mean， look， I don't love it， right， If we go ahead and look at。Runtime。 C。

 right， this is the thing。That we really don't want to have happening。 Oh。

 I seem to have misspelled that at some point。 If I recompile the runtime。

 we'll see it with the misspelling。 that could be good， I guess。 Okay， well。

 we don't really care about that。 whatever。 It's got the misspelling。So it's bad to see this， right。

 We talked about the fact that only us making a mistake would lead to the situation where we see this。

 So that's a little bit bad。 But I actually think there's something even worse。

 So let's go ahead and see。好。Well， well， well。So what has gone wrong here， right？ So if I do。

No problem。We're not supposed to do that。Yep， great。But then when we swapped a compiler land。True。

So what's happening is because we know what's happening inside the compiler。

 we are able to actually come up with this program that lands us in a really confusing spot right。

 this really should not happen and this is because we are not checking our type tags right we have that information represented at runtime It's all right there in how we have used those 64 bits of information。

 but we haven't actually checked it。So don't worry， we are gonna be getting to that。

 But before we wrap up for the day， let's take our last few minutes。

 I want us to really think about how we are using this stack。

 And so I'm going to write out a particular program that we could write in our language。

 And the question that I'm going ask you is to figure out what is the highest point in the stack。

 So the lowest address of memory that we would end up accessing in order to actually run this program。

 and we'll just sort of make that answer relative to RP sort of the number of slots that we will use。

 So let's try。嗯。It's going to be a lot。All right。Go ahead and chat with folks nearby for these last few minutes。

What is the highest memory address， so the highest position on the stack that we're going to reach to execute this？

How if you think slot RSP minus8？How if you think R is P minus 16？How if you think RS P minus24？

How if you think RSP minus-32？Okay， we've got some various ideas。

 Let's go ahead and find out we've got our answer key， which can just tell us。Oh， my goodness。

So don't worry we won't leave this topic， we're going to keep coming back to this if you're feeling confused about this answer。

 I highly encourage you to sort of draw out the tree representation of the program， think about okay。

 when we're going down the left sibling， what's happening when we're going down the right sibling。

 what's happening and think it through。And likewise， we will not be leaving the topic of。

Our plus one。32， whatever all of those topics， we'll be back。All right， see you soon。

 have a good rest of your Tuesday。Hello there， how goes？Already agree。



![](img/5198d3115891bf506642adc26b8aea03_13.png)

Change or can we do some？Because I have a course， which。

