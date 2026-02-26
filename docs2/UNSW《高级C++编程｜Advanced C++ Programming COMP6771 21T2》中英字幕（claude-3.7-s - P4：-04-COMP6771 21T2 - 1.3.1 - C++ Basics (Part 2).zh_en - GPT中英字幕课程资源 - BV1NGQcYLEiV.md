# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P4：-04-COMP6771 21T2 - 1.3.1 - C++ Basics (Part 2).zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Hi everyone。Nice to see you all again。It's been a long time 24 hours since we've last spoke and today we're pretty much just finishing off the second half of our C++ basics lecture so we started our C++ basics lecture yesterday but there's more to go through today and we'll see how we go honestly like the first few weeks of content aren't super hard so if we finish early then we will finish early otherwise we'll see how we go but let's get stuck into it so。



![](img/19b429d67b955be61d2c4d78f317efc9_1.png)

Essentially， these slides， where we got to yesterday was we got to。嗯。

We got to the end of expressions， and then we kind of got on to value semantics。 But I feel like we。

My。We didn't get to that specifically， but let's talk about it now。嗯。So a shortcut the full screen。



![](img/19b429d67b955be61d2c4d78f317efc9_3.png)

So。With。嗯。With C+， we really kind of talked about this a couple of times。It copies things， right。

 and。This is， again， very different from Java。In the sense that it both。



![](img/19b429d67b955be61d2c4d78f317efc9_5.png)

Just trying to think about a comparison to Java。 So I know， I know not all of you know Java。

 So I think there was a few people posting in the on the forum or in the feedback yesterday that was like。

嗯。What。Like what if I don't know Java and it's like just it's just'cause comp 2511 is a prereq so I'm not 100% sure maybe for postgrads it's different。

 but if you're an undergrad， it is an assumption that you're familiar with Java so we kind of have to operate that way too。

 but essentially if you were writing in something like Java and you said for instance。

 something like string S equals new string hello。

![](img/19b429d67b955be61d2c4d78f317efc9_7.png)

And then you said string S2 equals S。They would be the same string with the same reference right。

 and then if you did something like you know an equivalent of assertt S equals S2。

Then that would also be true because you'd be checking if two references point to the same heap object right And if you want to check you know if there's two separate things you do the whole you know dot equals in Java now like where C plus plus differs on this front is that it does do a copy here instead of a reference but also when you do comparisons it's actually like the equals by default won't necessarily compare the point0 it will do the Java dot equals equivalent。

 it will actually compare the value So for instance， strings， two whole separate different strings。

 which is what hello and hello2 are two separate pieces of memory。



![](img/19b429d67b955be61d2c4d78f317efc9_9.png)

嗯。They。Completely like when you compare them， it actually goes through the character array Like it doesn't say。

 are you the same piece of memory。 It says， do you have the same values。

 And that's what we mean by value semantic。 So semantics， I think is， is what， would you describe it。

 It's what describes meaning。The branch of linguistics concerned with meaning， so。

That means that a lot of things in C++ have a lot of meaning focused on their value。

 not so much their reference and stuff and the rest of the example here。

 I think you can kind of understand intuitively。If we get onto a more interesting topic like type conversion。

 then we can talk a little bit about how C plus plus differs from C。 So with C， you're probably。



![](img/19b429d67b955be61d2c4d78f317efc9_11.png)

Some of you would be aware that you could do something， for instance。

 like say n a equals5 and then double B equals double A or in some cases you can actually just say double C equals A。

Now， there's a couple of things like happening here， which I think you need to be familiar with。

 The first one is that。In this case here， everyone understands， you know， equals equals 5。

 In this case here， what we're doing is we're casting。A copy of a2 B。

And whereas kind of setting it as a double。 So this is kind of that you'll see explicit cast thing。

 Now you don't have to do this in this case because a double is a more precise version of an integer in general and therefore the compiler is comfortable knowing that you can convert from an integer to a double without a loss in precision and without that loss in precision。

 this is what we would call an implicit cast or an implicit type conversion。 Something like this。

 though gets a bit trickier because a char is one by it， but an in4 byte。

 So there's particularly a lossy conversion here。 and a standard compiler won't actually let you do something like this because it's aware that there's a loss in that conversion。

 but in some languages like， you can often cast anything well not anything to anything。

 but you can sometimes cast thing。 So you can sometimes force that a to be a char。

 the kind of casting rules that you might have been exposed to for C or a little bit fast and loose sometimes So while we're kind of focusing。



![](img/19b429d67b955be61d2c4d78f317efc9_13.png)

here is。The implicit type conversion in C plus plus which is very familiar。

 And then we're going to look at the explicit type conversion。

 which is a little bit a little bit different。 So first one is implicit promoting conversion。

 So if I have an auto I equals 0， and then I have an auto D equals 0。We can。Set D to B equal to I。

 just like I've said that， we can implicitly cast。 we can implicitly convert， or in this case。

 we call it implicitly promote because it's going from an int to a double an in to a double。

 And we can see that in action here。 So we've got our entire equals 42。 We try and cast it。

 And this should all behave totally fine。 And you know， I'll just run this again。



![](img/19b429d67b955be61d2c4d78f317efc9_15.png)

Sweet， and then we'll do build source， stemmer。sorry right， like。Build lectures。Lecture 1， demo 106。

All test passed。 Okay， cool。 So that that silent conversion does work。Alvin asks a great question。

 which is why are there curly braces here。 Well， in this case。

 the curly braces are actually there just to help make it look like the catch too。



![](img/19b429d67b955be61d2c4d78f317efc9_17.png)

![](img/19b429d67b955be61d2c4d78f317efc9_18.png)

Here like because you know， we define this and then inside the catch to block， we do that。

 but in reality。What actually happens is that。You can get away with writing code that just looks like this。

 Like you could just say auto K equals 5。 and then you could say auto。L equals3。You could do that。

 but we're not going to get to that till week three。

 it's not really something you need to be concerned with， but it's definitely possible。

 Jin says so is it typo and lecture code that I equal zero。No， it's， it's not a typo。 Oh， I mean。

 it's just different。 It's like all the same stuff。 like the， the lecture。The lecture code doesn't。



![](img/19b429d67b955be61d2c4d78f317efc9_20.png)

Oh， I see what you're saying。 Yeah， I guess that's a typo。

 I'm not sure really how that happened since they're copied and pasted。 B yeah the。

 the lecture code is often like not the true source， Like it's not the source of truth。 In general。

 the lecture code is like we write it。 And then we copied into the lecture slides。

 And sometimes we have to cut things out。 So to do take the lecture stuff with a grain of salt'ca you know。



![](img/19b429d67b955be61d2c4d78f317efc9_22.png)

嗯。

![](img/19b429d67b955be61d2c4d78f317efc9_24.png)

Yep， okay， so the other part of type conversions， though， which is equally as important is。



![](img/19b429d67b955be61d2c4d78f317efc9_26.png)

嗯。Explicit promoting conversions。So in this case， is' where you explicitly tell the compiler that you'd like to convert something。

And what this means is the only difference in the previous example though is that instead of just saying D equals I we've actually said here D equals static cast double of I so static cast is a function that is built in to the C+ plus core library so you don't actually have to import anything and it has a couple of purposes so one of the first purposes is that it tells what has the main purpose honestly which is that it tells the programmer exactly what you're doing it gives a lot of intent because casting or type conversions are a common source of errors in code because you know there's like maybe a loss in precision or some kind of other strange conversion and therefore we like to try and be explicit about things。



![](img/19b429d67b955be61d2c4d78f317efc9_28.png)

![](img/19b429d67b955be61d2c4d78f317efc9_29.png)

So in this case， we're going to try and statically cast an into a double and we put this here now。

What actually happens here compared to the previous example， I think， is in this example。

The right hand side of the assignment is an int， and then we assign it to the double and during that assignment process is where the promotion happens。

 it's where the type conversion happens。In the second case here。

 this static cast will actually take the endt， and it will promote it to a double。

 So the right hand side of this is now a double。 And therefore。

 the assignment from the right hand side to the left hand side is actually just。An assignment。

 you know， just set the double to be the double I one better or quicker functionally performance wise。

 not really。 Again， this one's just a lot clearer to people what's happening because you you always want to kind of yell and scream when something's being casted。

What happens though if we try and swap that around？

 So what happens if instead here I may be try and then say autocon E equals static cast。Chaia。嗯。Of。

I the other cool thing about staticcast is it means you don't actually have to write the type over here because in this case here。

 we kind of said auto d equals 0。0， but in actual fact we kind of would have written that normally or you'd have to say double D equals I because't you can't really say auto d equals I because that would just make it an int right because it will infer the type of D based on the right-hand side so that's kind of why we have to fudge it by setting it to be 0。

0 but let's try and run this one。Okay， we get an error in the areas and this variable okay。

So I'm going to deal with my unused variable just by avoiding it that's a common technique you can use。

Okay， it worked， now let's try and run it。All tests passed。 Well， I guess that makes sense。

Let's try printing it out， Let's see what it does， standard CR E。Oops， sorry I have to import。

Like these in some of these examples I like to just print things because I know I could write a test for it。

 but I'm also familiar from my experience teaching these courses that students often need something tactile like they need to actually see something printing and running so I'm going to run it again and it did not print anything。

It's not very nice of it。W why that is。That's very oh， there it is sorry。 Now it's a stop。So it's。

 oh， okay， yeah， okay， I understand so。

![](img/19b429d67b955be61d2c4d78f317efc9_31.png)

Yeah， it's casted the eye， which is 42。To cha。 And then we've tried to print that。

 And we look up our good old friend， Mr Draki table， Mr or Mrs or Daaski table。 And we got 42。

 which is a star。I can't read askI tables。 stuff。 There we go。 So that works。

 But here's the question。 What happens if we actually try and type convert something huge， Like。

 let's say something will beyond the size of one bite， because remember， what's one by。

 which is the size of a chart。 What's the maximum size it can be。



![](img/19b429d67b955be61d2c4d78f317efc9_33.png)

I just try to click on the first thing on Google。 I mean， the answer is 8 B， right。

 So it's 2 to the power of 8， which will be 2，56。 So 2，55 is the biggest it can be。

 So let's try and make something bigger than that。

![](img/19b429d67b955be61d2c4d78f317efc9_35.png)

![](img/19b429d67b955be61d2c4d78f317efc9_36.png)

Let's do something like 500 here。And I'll just adjust some of these tests。Let's try this build 106。

Okay， run。Ooh， we got a funny little symbol here。So that's a bit strange。

We'm not really sure what that is， let's try and print it out as an endt。So Sureish has asked。

 what is void E for again， void E is。Essentially。Just a way of using E。

 it's basically a statement that we do nothing with its return value。

 it's an easy way to force the compiler to think that you're actually using something and is great during debugging。

Okay， so。So here's the strange things about what's happened and why you have to like be careful with this stuff because。

嗯。We started with 500 as an int。 We statically casted it to a char。

 which wasn't a promotion because we've lost precision。 We've gone from a 4 B integer to a 1 B char。

 and then we've casted it back to an int and tried to print it out。 And what we get is negative 12。

 And that doesn't make any sense。 I don't think， right。 Does anyone know why it's negative 12。

I can't。Oh， I guess that makes sense 256 times too。So basically， it's like overflowed here。

 So I mean， the simple math of it's like we had 500， which is 256， It overflows 256。

 which basically gets you up to。

![](img/19b429d67b955be61d2c4d78f317efc9_38.png)

Anyway， I won't go through that， but。It's it's a。It's like if you think about it， 2，56 times 2 is 5。

12， and we got negative 12， which essentially means that we've gone kind of 12 too far in a way。

 I mean， you can go away and think about that。 This course isn't really on like overflows specifically。

 we can maybe come back to that if we have extra time。Soir。Next。Any questions about costing？

Just before we move on。Why did my cast of int in the print fail。

 I think it failed because the compiler was like， please don't do that。

 It was like that's an old style of casting。

![](img/19b429d67b955be61d2c4d78f317efc9_40.png)

So this compiler that we have in the course， I didn't set it up originally。

 but I'm pretty sure it has some extra warnings turned on I just I don't know off the top of my head。

Itll be in some config file that I haven't looked at， but。Yeah。

 there's some things you can't do that like normal G plus plus would let you do。

 So like just just going G plus plus without any like any flags of any type is like it'll just do whatever it humanly can。

So this one is just a little bit more strict。

![](img/19b429d67b955be61d2c4d78f317efc9_42.png)

Okay， so let's move on to functions。Functions in C plus plus this one shouldn't be too bad because it's a lot like other languages。

 First thing is， we have a whole bunch of functions。 Now， there are。

 there are actual names for these things like functions with no parameters are called nullary functions。

 functionss with one parameter called unary functions。 Uniary means like one。

Functions with two or called binary functions。And they're all exactly what you'd expect。

 I don't want to talk about this because I hope you all understand it。One subtle thing。Oh god。

 sorry about that。I tried to breathe and swallow at the same time。

One subtle thing though is since the introduction of C++ 20 there is another type of function syntax that you can do。

 which is the top one here， So the bottom one is what we've kind of written so far in the course which is just like your standard C style int main standards the out and stuff whereas the one up the top here's what it's done is it's taken the return type of the function it's put it on the other side of the function with a little dash arrow and then it's put auto out the front。

Now。This is something that one of the people who helps with the course Krista Bella is really passionate about and essentially I think my understanding of it is that it aligns better with Lambda syntax。

 which is what we're going to be talking about next week。

 so it's trying to add more consistency to the overall way that you define functions in the course。

 I think some students last time found it a bit awkward， so we won't enforce the specific use of。

The new style of function syntax。 But what we will do is we will ask you to be consistent。

 So if you want to use the bottom one， use it， if you want to use the top one， use it。

 just be consistent。 And remember， the top one will not work with older compilers。

 So I'll give you an example of this。 like actually this is actually a great example to show you different C plus plus versions。

 which I talked about in my tu today。 by the way， speaking of that， I accidentally hit pause on my。

 So I kind of botch the recording。 I'm really sorry。 So Simon recorded his tutorial。

 So if you want a full tutorial here， you can go watch it。 if you want my crappy 12 minute1。

 you can watch。

![](img/19b429d67b955be61d2c4d78f317efc9_44.png)

![](img/19b429d67b955be61d2c4d78f317efc9_45.png)

![](img/19b429d67b955be61d2c4d78f317efc9_46.png)

嗯。But yeah， let's get onto this。 So this is our function。



![](img/19b429d67b955be61d2c4d78f317efc9_48.png)

I'm just going to open up a standard sorry I'm trying to get back here。

 I'm going to open up a standard terminal and I'm going to make a file and we'll call it like old dot CPP and I'm just going to paste this in here。

 So this is just our old kind of function thing。 If I try and G plus plus this。

Let me just get rid of that。If I try G plus plus old。It seems to work。 Why does it work？

I didn't think it would work。 Maybe it's， maybe it's defaulting to。

See plus plus 20 now maybe it does that Let me try this。好，O。

Maybe that's a bad example of a C++ Pny feature。Just walked into a trap there。



![](img/19b429d67b955be61d2c4d78f317efc9_50.png)

I'm actually surprised。 that compiled。

![](img/19b429d67b955be61d2c4d78f317efc9_52.png)

That's good。 That means you're less likely to run into problems。

 So what we'll see later in the course is that。There are different versions of C++ and again I talked to 15 people about this in my tutorial today。

 but there's essentially version 98， 11， 1417 and 20 98 to 11 had the biggest jump most of you after this course like all of the code you write in this course could easily be modified slightly to work with。

呃。C plus plus 11 so in a lot of ways you kind of got to think about you're really learning like C plus plus 11 with bonus things because that's the mid big。

Shift change， but there's a lot of stuff you'd write in this course that you would never get compiling with C++ 98 because it's just so kind of different and basic but we kind of cover features in all these different areas and we'll talk about them Honestly I could be wrong about the function thing that's not really my forte。



![](img/19b429d67b955be61d2c4d78f317efc9_54.png)

I'll go and have a look at that for you。Essentially oh sorry I jumped the gun essentially there's just those two different styles and you can kind of pick the one that works for you。

😊，OkayIn terms of functions， one thing that C+ plus has that C doesn't that many other programming languages do is the addition of default arguments。

 So when you define a function like in this case a function called RGB that returns a standard string you can give it RG and B as shorts which would like two bytes I think and you can give them default arguments so that if people don't enter them。

 it'll actually call it with default arguments， again。

 this is pretty common practice in most programming languages so if you've done any other language beside C you might have been exposed to this in some way。

 B you can see if you just call RGB even though there are three parameters it will still take it and it will just prepopulate them as zero。

The only actual thing that you can。Not do is， is once you define the first parameter in the list。

 you can't。Default the rest。 So like in this case here， if you want to。

 if you want to explicitly state R， then you have to， you have to sorry。

If you want to explicitly state something， you have to make sure everything before it's defined。

 I got that around the wrong way。 So in this case， if you want to explicitly define G。

 you're also going to have to define R。 that's just how it works so。Once you want to define one。

 everything before it has to be defined， some languages like Python will not necessarily want that。

 but in C++ it's kind of in between being crappy and very flexible。

The only other thing I want to note in this course is a really good piece of。

Syntax lingo to get your head around is the， the difference between parameters and arguments。

 So parameters。Are up here， parameters are really what's in our function declarations and definitions。

 whereas arguments are what we call particular values that we give to our function calls。

 So formally speaking， it's like you would call R parameter G parameter B a parameter in this context。

 but 100100，200200， they are arguments。 So， I mean， you could also call this default parameters。

 but that's just a useful piece of knowledge， I think to help separate out some ideas in your head。

One thing that C plus+ also has is function overloading。

 We're playing around with the new syntax here。 So what function overloading is in a language like C++ is that you can redefine。

The same named function multiple times if the input parameters differ。

So in this case I've got a function or a name called square。

 I have a name called Square which is a function。And it takes in an int constant X。

And I can define that function。 I can also define another function with the exact same name square。

With a double conts。嗯。And the compiler will be totally fine with it。

 And the reason is because it doesn't affect how the compiler does look up。 So for instance。

 if you call square with a2， it's going to go look up the first function。

 If you call square with a 2。0， which is a double it's going to go look up the second function。

 Now a big thing that kind of comes up in this course a lot is how compilers think and it's very relevant to this course。

 So for example， you can ask yourself the question， what happens if I just define this bottom one。

 what happens if I didn't have this one up the top here。 So if we just had say that。



![](img/19b429d67b955be61d2c4d78f317efc9_56.png)

Would this still work， yes， it would still work， and that's because when the compiler is doing its compilation。

It would take this to and it would say it's an int。 and then it will go Okay。

 I can't see any square functions that take in an int。

 but what I can find is a double and I can convert an int to a double without any loss in precision so it considers this one maybe not the ideal fit but one that is still appropriate and it will compile fine with that whereas if you kind of had you know a square where you used a string。

 the compiler would simply say I'm sorry this doesn't exist because it can't find it at all。

 Edward says does the parameter usually need to be set as const。 Well， again。

 what were the rules we talked about in the first part of this was that everything should be cont by default unless you need it to be mutable。

 So in this case， we don't need to mutate the X inside the function because we're just squaring it and returning and therefore we make it be const because there's no need to change it。



![](img/19b429d67b955be61d2c4d78f317efc9_58.png)

![](img/19b429d67b955be61d2c4d78f317efc9_59.png)

So if we have a look here， we've got these functions。

 this is all written out here if you want to go play around with the code。

We have our two square definitions in and double a common mistake people make when it comes to these functions is that they will think that this one is also an override。

 like if they say something like this， they'll be like， oh yes， this one is different， sorry。

 that's not what I meant。They'll say， oh now I'd actually like a function that will take in a double and return an int。

 So when it comes to the function overloading rules in C plus plus you can't count different return values。

 So essentially it's all the parameters so as far as the compilers concerned these two are identical because they have the same name and they have the same parameters。

 it doesn't care about the return value。Is he so a stupid question。

 but is the check function similar to the assert function and C， Yes。

 so in catch2 check and require a very similar to the assert function， it's just that check won't。

Crash the test。 So I think require is most similar to the。嗯。Most similar to the assert function。

 This one here。 So I think if this isn't true， it will crash。 And I think you usually。

 I don't know if it will crash。 Sorry， I think it might end the test or end the section or something like that。

 I don't know off the top of my head。 But the idea with check is that。



![](img/19b429d67b955be61d2c4d78f317efc9_61.png)

So conceptually speaking， you would check something。

If it can be not true and the rest of the test still make sense。Whereas。If you require something。

 you're basically saying， if this isn't true， we should really stop testing this bit。So in this case。

 it's saying。Let's make sure these two strings are equal and if they're not let's stop。

 we want to you abt the test case as's written in my notes， thank you。

You bought the test case if this expression is false， but a check will keep going if it's false。

 and that makes sense here because if the strings aren't the same something's deeply wrong。

 but if the back of the strings not right， then you could probably still run a number of other tests。

So that's a little bit of a tip for the assignment， speaking of the assignment。

 I have to release that we'll talk about that at the end， that's right。😊，Okay。So the overload rules。

 I've kind of talked about this just briefly then， but essentially the compiler will look for all the functions with the same name。

And then Ill look for the ones that have the same arguments。嗯。

Or at least has the ability to convert some arguments。 And then it will find the best match。

 So in this case， if you call F with 5。6， the compiler will look at all four functions。

 It will rule out G because the names different。It will then rule out。The second one。

Because it has a different number of arguments。Because sorry when I say the second one。

 I mean the third one and what it will leave is these two here。

 so it'll leave the autoF inch and the autoF double double because both of them can have one argument。

 right？And then it will look for the one。That it can type with better。

 essentially like type matching better。 So in this case， it'll choose the。第。Yeah。

 it'll choose this one here because a double is a better match than an int because it's a double right。

 So it doesn't want to lose precision。 It doesn't want to go down to the end。 So in this case。

 it would match with the F down there。

![](img/19b429d67b955be61d2c4d78f317efc9_63.png)

A really important note when it comes to overloads， which is a common mistake some students can make。

 is you should always write overloads that are trivial and what that means is that if you have three different functions。

Like that are all called F or you have two different functions that are both called square。

 They should have the exact same behavior。 So if you ever overload functions。

 it should have no different behavior。 It should have the same semantic。

 It should have the same expectations。 And if it doesn't， you give it another function name。

 don't try and be all cute and pretty just because you think you can function overload。

 It's like if they are different if they are not literally the same function in terms of its behavior and expectations。

 then you just give it a different name。

![](img/19b429d67b955be61d2c4d78f317efc9_65.png)

Okay， if statements。

![](img/19b429d67b955be61d2c4d78f317efc9_67.png)

I'm not going to run a ton of code with this unless I get asked to。

 but if statements in C++ are really similar， this is just a function that has an if statement in it。

What you'd expect。嗯。Jan， I don't actually know， I don't think it will because it'll consider a downcast。

嗯。The other thing you can do in C plus plus is conditionals， shorthand conditionals。

 So instead of using F L statements， you can use。The ternary if statements。

 which are the question mark and the colon， this is essentially you might have seen this in languages like Python。

 where instead of saying if then else， then this is now saying like if，Then。Else then like that。

 If you're not really familiar with this， then you can Google Ternary。 if statements， that's T E， R。

 N R A Y， like it's really quick to Google。

![](img/19b429d67b955be61d2c4d78f317efc9_69.png)

Tannerary if statements。And you'll see like they're all the same in every different language right。

 this is just from JavaScript， the first one I found。



![](img/19b429d67b955be61d2c4d78f317efc9_71.png)

We're not here to teach that because it's not required in the course。

 it's more just like for people who are familiar with it， the point is you can do it。And C++。

Probably the only thing to be cautious of is that。It can make code shorter。

 but that doesn't make it easier to read and your objective is to make code easier to read。

 not to make it shorter。 So in this case here this can kind of nearly be harder to read so you just have to use it with caution so that you don't make your code unreadable。

C++ also has switch statements， these are exactly what you'd expect these are pretty much identical to see。

 so nothing much to say here。The the brackets fold through is。I don't think that's actual syntax。

I don't think it is， I mean， we can try it out。

![](img/19b429d67b955be61d2c4d78f317efc9_73.png)

Let's， let's， let's do it really simply。 Let's do our basic。Let's do switch dot CPP。

 We'll just do this one on terminal。I had pretty sure， I can't remember。Yeah。

 want to find reference to main sure。嗯。Okay， maybe it is a thing。

I've a feeling I got asked this last year。 I don't really use it， Sir。There you go。 Well。

 here's a cool example。 So this is a feature that was added in C plus plus 17。

 So now let's try and actually compile this with C plus plus 14。😊。

I don't think I understand G++ very well because that shouldn't work。嗯。I don't know why it works。

 I would expect that it wouldn't because it's a， it's a different feature here。

 So what this is saying is that in C plus plus 17， they created。They're meant to be double dash or。

NoI don't know。 I'll look， I'll figure that out later。 Sorry guys， they added a new piece of syntax。

 which was square bracket， square bracket fall through。 And it's。

 I think it's a way it's only be used in the switch statement where the next statement is to be executed as a statement with a case or default label for that switch statement。

嗯。Optimize out， yeah， quite possibly。嗯。So this is quite interesting。I mean， again， this is my point。

 I don't keep a catalog of everything about C++。On the top of my head。

 But let's let's delete one and see what happens。See。

 what I'm wondering here is like why not just have K0， like surely that still works。You know。

 like nothing's particularly wrong with that。嗯。I could probably read this more。

 it's just I don't want you guys to sit here watching me try。Understand something。

Indates that a fourthroom in the previous case is it should not be diagnosed by a compiler that wars on forth through Oh okay。

 sure so essentially what this was was that。

![](img/19b429d67b955be61d2c4d78f317efc9_75.png)

嗯。Compilrs would sometimes have warnings in them if cases fell through right， because， you know。

 in a standard switch state when you're meant to include breaks everywhere。 So it's like case0。

 something break， case1， something break。But if you didn't have that break。

 sometimes compiles would be like， hey， friend， I think you might have forgotten the break there and people would be like I know what I'm doing。

 Don't tell me what I forget。So this for through here is actually just a message to both the programmers and the compiler that they know what they're doing right so I'm like I know know what I'm doing pretty simple。

第二。I've never used that personally because I don't use switch statements much at all in my life。

 but that's good to know。 I think it's cool how it's a C plus plus 17 feature as well。

It just kind of starts to give you a sense of these like little things that have come up in different versions General you'll find that C++ 17 would be the standard and pretty much everywhere and C++ 20 is probably like becoming a lot more mainstream。

嗯。Next is sequenced collections。 So a kind of， I think， past。嗯。The basics of the language。

 And we're starting to actually look at different data structures now。

 So the basics are done and now we're going to have a look at the beginning of sequence collections。

 We're going to talk more about sequence collections in week 2。

 where we go into a lot more detail of it。 But at the moment， we're just going to focus on。

We're just going to focus on。How to actually interact with it。

 So we talked yesterday about a standard vector and a standard vector， Oops strong one。



![](img/19b429d67b955be61d2c4d78f317efc9_77.png)

A standard vector is basically an array list is what I said。 So it's a it's a。

 you can think of it like a C array or a C lingist or an array list or whatever。 In reality。

 it's a dynamically sized array。 So it's actually an array。Underneath the hood。

 but it kind of feels like a Python list or a Java array a list or something like this。

So we create ourselves a vector， which is like a list or an array of ints。

 and we can immediately populate it like this。 We'll get into the y of this later as well。😊。

So it is0，1，2，3， four，5， six，7，8， nine like that。D。Next thing we can do is we can make a copy of it。

 so I'm going to copy my vector to a second vector and then I'm going to check if they're equal and they should be equal because of how things work and we've talked about that。

Then we can access elements of that vector。Like this by saying I'd like the second index2 item of that。

 and we assume。And we set it to be zero。So just like seeing in other languages。

 the second index is number two here。And then we check if they' are not equal to each other anymore。

Which is what we expect。 And we can try that out。 We can， we can print out。More single digits， too。

And have a look at it together。Oops。I have to include ios stream。Cool， so I got 0。 Now。

 what happens if we try and print out the vector。 Let's actually try and print out the vector。

 See what it does。 See what the compiler says。😊，Okay， so we've got an error here。

 and that error is that。No known conversion from standard vector to standard old point。 blah bla。

 blah。 Now we're going to get more into this into week  four。

 But what is happening here is that it's basically saying the compiler。

Has no idea how to stream a vector to an output stream， right， like standard it out。

 So the compiler like， I don't know how to do that。 And we could help it。 but like for now。

 we could just do something simpler。 This will come up in like one of the next lecture slides so we can skip over when we get there。

 But like in the meantime， we could just do like a simple four loop right， we could say n equals 0。

 We could say 4 n equals 0 I is less than more single digits dot size。Les plus I。

And then we could just add this here and say more single digits， I， there are better ways to loop。

 but I'm just keeping it simple for now。Build 1，0，9。Oh， this happens。

So here's one of the downsides of a language like C+ plus as it gets a bit more involved because when you have a vector。

 the actual size here。😊。

![](img/19b429d67b955be61d2c4d78f317efc9_79.png)

Right， it actually returns something that is' in an in and we can look that up in the library。

 so if I go to standard vector here。嗯。And we have a look at size。

What size will return us It actually says it's a size type。 It's a bit of a rabbit hole here。

 But then if we like， you know， C plus plus size type。kind of gets a bit complicated。

 but the point is that the actual type is like not an int。 It's not straightforwardly an int。

 and therefore sometimes you might have to do something like this or even better or maybe better。

 Let's try auto， see what happens here。

![](img/19b429d67b955be61d2c4d78f317efc9_81.png)

So auto doesn't really like this either because。Yeah。

 so what's happened here with auto is that it has implicit conversion change signness inch to blah。

 blah，lah， bh， blah。 So I think one aspect of auto like。There are some rules around auto2。

 like for instance， auto doesn't carry across the con。

 so if you say something like auto con A equals5 and then you say auto B equals6。Auto vehicless A。

 it copies it， but it doesn't like auto doesn't pick up the con as well， you know。

 And I think with auto， it might not do some things to do with the sinness as well。

 But the main point is that auto doesn't carry all the information。 So in this case。

 I think what's happening is even though it's like a size T or an unsigned int。 it's just like， well。

 I'll just leave it as an int。 So it is capturing it as an int the same。 But then it's。Yeah。

 then it's losing it after basically。 Matthew says。

 would autoic equals digits dot size and count down to0 work。 Probably。

 So that's an interesting thing that Matthew has said here， which is basically that。

If I was to instead say， let's start with auto I equals the size。

 and then we loop while I is greater than 0。 and then we decrement this。 This might work now because。

You know， does the size return the right thing？So that works， right。

 because I is actually being set correctly here because previously， it was just a 0 being， you know。

 derived from the0， whereas now it's actually like the size type。

 We could also probably play around with things here if we wanted to。

Instead of using auto we might be able to see like standard size T I think that's what type it might be or maybe we have to use a different size type。

 So standard size T is the actual like underlying type here as well。

 so that would probably be the most endorsed approach We like things like size T because it's a nice abstraction like unsigned int。

There's。Theres， there's no way for an unsside int to like。Be taken over later。

 Like if someone changes the， the sorry， or something funny。

 If someone like the C plus plus compiler decides that we want to do a different way of doing vectors。

 It's kind of locked into like an unsigned in or a size tea is a nice little abstraction of things。

So that's how we do that and we could loop through it and we could print it all out now。Yep，0，1，0，3。

4，5，6，7，89。 And you can see that that's mutated there。

 And if we tried to print out the single digits one， it would not have the two。

 it would not have the two to become0 because that's a whole。Separate thing。 That's why we copied it。

Okay。Right。So。

![](img/19b429d67b955be61d2c4d78f317efc9_83.png)

They do the wrong one。 Yeah， so you'll see it's 0，1，2 there。 So that's the basics of a vector。

 It behaves a lot like other array type structures that you might have seen in other courses。



![](img/19b429d67b955be61d2c4d78f317efc9_85.png)

嗯。I would like to skip this slide。 I wasn't sure if I wanted to teach it。

 but we can come back to it next week， but it kind of， now， I wantanna skip this slide。

 I'm probably just delete it。 I was a bit unsure about it。 but I decided now I don't wantan to do it。

 So that's the basics of vector。 Pretty simple。 We're gonna get into one of the most important parts of C plus plus basics here。

 which is reference。Whi it references， which is kind of like C pointers。 So in C。

 you have this kind of ability to pass things by value or pass things by reference at will and it's actually something that you don't have a lot of control over in other languages。

 So， for instance， if you if you use Java again， all the primitive types in doubles bulls， chas。

 they're all values and you can't pass them by reference。

 you can only ever copy them and then but all the heap items like the actual objects are pass by reference and you can't like you have to be explicit to pass them by value。

In C plus+， because everything' is by value， we need a mechanism to make things by reference。 Now。

 if we were thinking along our C logic， we could solve this just by using pointers， right。

 And I'm not sure if I have the example I was hoping for here。I might have gotten rid of it。



![](img/19b429d67b955be61d2c4d78f317efc9_87.png)

Yeah， so I really want to demonstrate this to you maybe in a little bit more detail than。Kind of。

 you know， we might have planned。 So I， I'm just gonna， I'm just gonna。

Coming out some of this stuff here。So。In C plus plus， if you want to create a swap function。Right。

 and you do something like in A and B like this， and it's going to swap some things。Now。

 if I have a main function here where I say n equals 5 and n J equals 6， and then I print out。

I equals。five。J equals 6 like this。 This program will compile， right。

 Like we're not actually using the swap function yet， but let's just start simple。

And I'm getting complaints because I didn't write code correctly。Classic。

So this compiles it runs when I try and run it。I get I equals 5 j equal 6。 Now。

 if I call swap and I pass an I and J。 we all know this。

 this won't work because I'm passing this in by values。

 is something we would have learned the beginning of first year。

 even if I wrote this function correctly。 And I said。

 you know int temp equals A and then A equals B and then B equals temp。

 even if I did something like that， it's still not going to work because by passing in them by value those values here and put on the stack locally and then deleted and it does not affect the like the stuff outside。

 If we wanted to do the C style we would do this， we would say we would pass these in as pointers。

 And then we would do some funky， ugly， confusing pointer crap， which no one likes doing。

Because it's confusing and it's seg fault sometimes。 So we do something like this。

 we pass in the addresses of these pieces of memory， and then we like dereference them and。

This is fine， but it's a bit confusing to make sense of。 And then even more than that， it。

 it's really going to lead you to making seg faults because you're dealing with memory directly now。

 So that works。 We've swapped them now， but I don't like it。 You shouldn't like it。So。In C++。

 we actually have this notion of a reference and references are really great because syntactically it looks very similar to passing by value。

😊，But what we're doing here instead is when we define variables。

 if we put an ampersand after the type， we are telling the compiler that we would like these to be passed in by reference。

 So it effectively acts like a pointer， but it's not dealing with pointers。

 what it's saying to the compilers when someone passes I into the swap function。

Please give me a reference to that。 So if I modify it within my function。

 it actually modifies what it's referencing。 So now with as little as just these two ampersans here。

 when I go and build this。It says I equals J。 I equals 6 J equals 5。 So that's references。 right。

 We'll talk about the details of it。 But that's like the tactile。

Physical interaction you'd use with it。 is like， I'm passing something by a reference now without having to F around with pointers in terms of getting into the details a bit more。



![](img/19b429d67b955be61d2c4d78f317efc9_89.png)

嗯。A reference is an alias for another object。 It's not a pointer。 It's not a pointer。

 It's just similar to a pointer in behavior。You don't need to use the dash arrowed access elements。

 It's treated just like a normal object。 It can't be null。

 Both of those things are the case because it's not a pointer。

 But I think one of the most important things the deficit is。



![](img/19b429d67b955be61d2c4d78f317efc9_91.png)

Is that if we go back to our？Kind of provided examples before I jumped into my little tangent there。

One thing about references is that once they're set， you can't change them。

And this kind of gets a little bit confusing。 So if I say auto I equals 5。

 I now have an integer called I， which is 1。 I print it out。 And then when I say auto reference。

 J equals I， what this becomes is this becomes a int reference because I is a reference。

 So auto like auto。嗯。Deriveves that it's an int， and then the ampersand means it's a reference。

And then when I say J equals 3， what is happening here is that I'm not changing what j points to or anything pointy。

 I'm actually saying that I equals 3 effectively because J and I are now just names。

 they are just like variable names that point to the same piece of stack memory。

 which is this I here。 So now when I print them out。

 I would get the same value because they both are the same thing。 J and I are the same thing。

 j Js a reference。Just to the same object。And we can have a look at that。

 let's just run that really quick。Great133， that's what we expect one is I and then we update J and I's update too because they're both the same thing。

嗯。Great， so now we say auto k equal one。 So k is now an in。

 And what we're doing here instead is we're using a constant reference。

 So now this type is going to be into constant reference。So it's an int。

 because that's what auto did for us。 It's const because we've said its's const。

 And and then it's a reference because we've said it's a reference。

 So ref is now a const reference to K。 What const references are are things that。

Can it's like a read only reference。 So if you have a con reference to something， you can print it。

But you can't modify it。 So you'll see here I have my K。 I'm allowed to increment my K。

 which will work， and reference will update， but I can't plus plus reference。

 So if we just look at these lines of code between 18 and 22 here and I go to run them。

This will work。We'll print out reference， it'll be one。

 we increment k and then we print reference again and because it's pointing to K。

 we're not pointing because it's referencecing K， it will give me the same value， so I'll get。

Just look at the bottom three lines here。Oh， just these two lines， sorry。

 I get one and then I get two because we inmenate if I tried to do ref plus plus the compiler is going to stop me because the compiler has enough information。

To tell me that it's all not good。Cannot assigned a variable ref with consqu type constant in M percent。

So it's basically like， hey， I just saw you try and increment or modify something that's can't。

 don't do that， please。嗯。Yep， and then I'm just looking here。

And then the only other thing to keep in mind is that if you make something cons。

 any reference to it also has to be const， so here I've got myself an interconst。

Because it's a constant integer， m equals 1。I can make a cons reference to it。

 so I can make an M ref， which just is a reference to M。

 That's totally fine because the reference is cont。

 but I can't do this one here because I can't have a like amable reference to something that's immutable。

 They would like that would make no sense。 So the compiler also similarimilely says here。

Or maybe you can。 Maybe it complains if you try and do something with it。

 I'm not sure let's try and actually like print it out。Sorry， ref 2。 That should be ref 2。Ooh。

 the compiler isn't mind。Prints out11 or 111。Oh。Printnce out 11， I like， why is it 11？Great。

So we get one one here， which makes sense。 So we we can actually do that。

 I'm sorry that's just the problem in my notes， but it's implicitly consed。

 So if I try and Ref2 plus plus that's where the compiler actually complains。



![](img/19b429d67b955be61d2c4d78f317efc9_93.png)

Because。Yes， I'm guessing what's happening here。Y， so what's actually happening here is that even though I haven't written Con。

 the compiler is adding it for me， it's kind of forcing this to be constant and that you can actually see this in the compilation message here because it says you cannot do anything to refF2。

Because it has a type constant into ampersand。嗯。So， yes， you just have to be careful around that。

 So I should just modify that to kind of say like that's okay。 Well， that's just， I mean。

 you wouldn't say that's not allowed。 This is just， this is just stupid。

But like saying ref2 plus plus is not allowed。Psin is a better practice to have constantt。

 I'll answer this for the third time and the third time only。

 which is that you always want to put cons everywhere humanly possible until for some reason you need to modify it in which case it doesn't become constant。

😊，And then George says， so you can't point ref2 to something else， correct。

 Once you define a reference， that name is permanently referencing that。

 You can't change where it references。 It's not like a pointer where you just make a pointer that points there。

 and then it points here and then it points there， it actually is always pointing to that。

 So ref 2 for as long as it's life now will reference M。That's it。

So just a question of whether it's read only or not read only。嗯。No。

 you can make references like that the people in the chat， that's fine Ram and then this other one。

 if A equals food and B equals food， then does AM percent equal BM percent。

I don't understand your question。 I'm not sure if that actually makes sense。

 You might have to give me a bit of code， but you can always run it yourself too。

 like like it's really easy。 Like we all have computers and you can just put it in。

 Like that's what that's what I just did a few times here。 We just figured that out。

 then there was something I didn't fully understand。 Anyway， We're at 7 o'clock。

 So let's take a five minute break。 and then keep going。 And then next after the break。

 we'll move into。Poss by value。Oh， I already did this。I think I jumped the gun here。

 I think I forgot that I had this example。 I've been changing these lecture slides around。

 So I probably made a mistake。 but that's good。 Save a small time。 Allright。

 let's take a short break， and then we'll get stuck back into it。He。

We're getting stuck back into it now。 So what I'm gonna do is this whole functions pass by value。

 pass by referencing。 I kind of accidentally did this before while I wanted to explain references。

 I think I might even swap these。

![](img/19b429d67b955be61d2c4d78f317efc9_95.png)

Slides around a bit because。In the future， because I think it's kind of easier to understand references as like a comparison to what you might do and see because references make sense。

 but like why do they exist， They want to solve a problem which is to like pass by reference So that's all fine。

 There's all the code you can play around with there。

One of the next short pieces is and this is in the Cute one。

 so anyone who had aute today all four classes probably came across this。

 but with our programming with our programs， there are two important concepts which are declarations and definitions。

And a declaration's job is to make known the type and the name of a particular variable or function。

And a definition， which is also a declaration。Tries to it allocates typically the storage of this type。

And。It can only exist once。 So every definition can only kind of happen once。

 So declaration is really just you saying this thing， like has some certain。Like properties。

 And we can kind of see these here right where in this top one here， this is a declaration。

 So anytime you do a function prototype without an actual body， you might call it the function body。

 that's what we call a declaration。 The second you give it a body， it becomes a definition。

 And you can see that here on line 11。 when we give this one a body。 So we give this one。Return one。

 which you know now it's a definition。 we can only do this once。

 if you do this many times the compiler will be okay with it。 if you do that。

 this many times the compiler will complain that there's been a redefinition。

 if we make a class here， which we're going talk more about in week three when you actually define like when you add a body to a class like with the braces then that's a definition and within this class。

 there is a member function which is just a declaration because we haven't given it a body and then we have a definition because it's a function that we have given a body。

 And then at the bottom here， this gets a little bit more confusing but all three of these are actually definitions because the short answer is that we couldn't do it multiple times。

 you can't say into I twice So therefore it's a definition So the obvious giveaway whether something's a definition is if you can't do it more than once in the same scope。

The second thing that helps for variables give it away is that for variables it's typically you asked yourself the question。

 have I allocated memory here and if you've allocated memory。

 then it's probably a definition so into I in cons J。AutoVD， they all allocate memory。嗯。

In C plus plus， we also have four range statements。 I don't need to take you through。4 loops。

 because we already know four loops。 But if you're familiar with other languages。

 then we have four range statements。 So we have this example here。

 which I butchered where we kind of loop through this vector。

 I want to come back here to demonstrate this because we've already looked at it rather than doing this。

 I can actually do things even simpler with four range loop。 I can say autocont。



![](img/19b429d67b955be61d2c4d78f317efc9_97.png)

A。In single digits。Or digit。It should work。I think。Great。109， let's go back。109，109， there we go。

So this one also works。 So you can see we printed out the list twice here。

 So a four range loop is just like Java4 range loops is just like Python's4 range loops。

 What you're saying now is you're saying I want to go and get every element It's like a four each loop。

 so I want to go and get every element of single digits and each time I loop I want to store it in a variable called digit。

Generally speaking， most four range loops， the element that you're looping with will have the type autocon reference because you don't want it to be a you generally don't want to mutate things in a four range loop。

But it's going to be reference because that's quicker。

 It's going to be con because that's quicker and you don't want to modify it。 and auto is great。

 The only other thing I haven't commented on about references。Is that。嗯。

References are also a little bit quicker， and that's why we try to use references where we can。

 You do have to be careful， though， because references aren't like you got to think about it if you have like have 300 kiloby struct。

 it's a lot easier to just use a reference to a struct than copy it。

 Even if you're not gonna modify it。 So for non-priitive types like vectors and other things。

 if you want to use that vector you want to use that thing than references are better because they're quicker because you don't have to copy memory It's just like a pointer。

 it's just really quick。

![](img/19b429d67b955be61d2c4d78f317efc9_99.png)

So that's loops， I mean loops are pretty straightforward at the basic level。

They're just normal four loops， four range loops， these are four loops that we've seen before。

 not a lot to talk about there。 You can also go play around with the examples。

 C plus plus does have enum types enum types are just enumerated types which are basically like a collection of names。

 Think of it like like a di set of strings， if you will and you can use these if you kind of want to not use numbers So you know how in like some of your C programs you might do something like you do like hash define Monday is one hash define Tuesday is two hash define Wednesday is3 you can get around that in C plus plus by using this thing here enum class so you could say create something that's like just to give you an example really quick。



![](img/19b429d67b955be61d2c4d78f317efc9_101.png)

Um，You could say， okay， I'm going to call this like days of week。And then you could put here。

 you know， like Monday。Tuesday。Wednesday， et cetera。 And then when you want to do stuff。

 you could just say， you know， this is like just the days of week。Monday。

There's nothing special about this， it's just a much nicer way to program because you can just use enUs instead of having to use like integers or some other horrible placeholder。

Yeah。

![](img/19b429d67b955be61d2c4d78f317efc9_103.png)

So you can look at that if you want， there's very few places in the course you need to use that。

 but I know some people have been interested in it。Yep。

 I'm going come back to some questions as as we go through these。

 a really important data type that'll come up in your first assignment are both hashets and。Sorry。

 hashets and hash maps。These are just sets and maps。

 So sets you should be familiar with because it's like sets are just like a pool of unique things and maps are basically just dictionaries。

 So if you've worked with， you know。Java， Python， again。

 you would have been familiar with some kind of hash map， hash or map or dictionary。

But hashets are hashetss are pretty straightforward。 The library we use is a standard unaudered set。

 which I think is a C plus plus 11。

![](img/19b429d67b955be61d2c4d78f317efc9_105.png)

Feature。Yep， it's a C plus plus 11 thing。 So this didn't exist until C plus plus 11。

 And this is a very， very critical。

![](img/19b429d67b955be61d2c4d78f317efc9_107.png)

Data type。So you can see here we can create an unordered set of strings and we can add to it a series of strings like Lovelace Babbage during Hamilton Church Borg。

U。And once we add them， we can check if inside of that lovelace is contained within it。

 right So an unordered set is an object itself。 and you can check if things exist in it。

 It has a whole bunch of methods。 You can insert into it。

 So this is just what you would add when you construct it contains the race。

 you can get rid of things in it， you can check if things are in it。

 We're going talk more about this next week when we do the algorithms and iterators part。

 So don't worry about the finding and element part yet because we'll come back to that。

 You can clear it， and then you can check if it's empty。

 So this is a nice little testing file to show you like the expectations you could have on a set。

And remember， like a set functionally is just like a dictionary， just like a vector。

 Like if I told you really simple to。You know， read in a list of numbers and。You know。

 show me at the end。 Which numbers appeared。 Not how many times just which ones appeared。

 You might store it in a vector and you might do a thing where every time you get a number。

 you check if it's in the vector。 And if it's not， you add it， right。

 you're effectively building a set。 It's just a language like C plus plus has a set built into it。

 So you can just use this。 So if you， for instance， try and add Lovelace multiple times。

 it will just stay there once。 So if I was to say do this line many times。

 It will not change the data structure after the first one because sets can only contain one of a particular data type。

 It can be a set of strings。 It can be a set of ints。 It can be a set of whatever。

Why we care about using these data structures is because and again。

 we will talk about this next week， but different data structures have different properties。 So。

 for instance， an unaudered set here。

![](img/19b429d67b955be61d2c4d78f317efc9_109.png)

嗯。We'll have like， it's certain member functions like。Look up， find， for instance。

You can see here that if you have a set。The time complexity of looking up a member of a set。

 seeing if something's in the set is average。Average constant。

I'm not sure how the sets implemented underneath the hood。

 but basically sets are used because of their performance， so their constant time look up on average。

 which is exceptionally good， right， like if you're dealing with huge amounts of data。

 that's so much quicker than anything like a vector or a linked list。

So performance is a big thing and inserts probably constant time or more， I don't know。Yeah。

 so inserting is average case constantantine worst case o size。Wonderful， I mean。

 you can read about this all you want。 but it this essentially a set is like a it's essentially like a hash or a dictionary where you don't care about the value right。

 you're just stor keys。 So it's not ordered， which is a problem， right。

 Like the biggest reason you use an array or a link listers because there's a sense of order to it。

 but with sets you don't really care as much。 So' that's a hash set a hash map is pretty similar except there's a value。

 So you'll actually notice here with a vector and with unordered set。

 We gave it a type that we want it to be for in tors string or something。 But for a map。

 we actually give it two types。

![](img/19b429d67b955be61d2c4d78f317efc9_111.png)

So in this case， what we're saying is that we want to create a dictionary where these are the keys and these are the values。

 Now， again， if you've used other kinds of like Python as a great example because with Python。

 all of your keys， I think mostly have to be strings whereas in C+ plus you could make an unordered map of anything you could make it be insta doubles or strings to ins or insta strings but the main point is an unordered map is a collection of keys mapping to values So it it's a dictionary。

 it's a map it's a hash， there's tons of different some of you would have seen this data structure in some fashion。



![](img/19b429d67b955be61d2c4d78f317efc9_113.png)

And it's usage just pretty intuitive too this is another C plus plus 11 feature so you can see here that a test case at hashmat we're creating country codes。

 so we're mapping country codes to country names so we're mapping strings to strings we're going to populate it with a bunch of them here We can check if the country codes contain this key。

 We can check if country codes does not contain this key and then there's some other functions here but。

😊，In place， which is add。 So this is kind of like push or add。 And again， similarly。

 you can go straight to the。

![](img/19b429d67b955be61d2c4d78f317efc9_115.png)

![](img/19b429d67b955be61d2c4d78f317efc9_116.png)

Say， plus， plus。Reference and go have a look at an unored map and an unordered map it'll show you。

 It's like you can insert into it， you can em place into it。

And these will all have time complexities as well， and like looking up where was the lookout one at Find。

So a similar thing here， find is constant time on average and。Inset is。More complicated。

 but generally it's very quick， right， So these are not these these are designed for add in look up。

 They're not designed for printing。 They're not designed for listing， ordering or anything like that。

 So super， super helpful in a lot of context。 But yeah， sets and maps。

 That's what we're dealing with here。 These are just more of the examples。



![](img/19b429d67b955be61d2c4d78f317efc9_118.png)

You can do more with it， I don't need to take you through every single thing about C++ otherwise we'd be here for four years。

 but it's mainly just trying to give you an overview。So some of the questions。

 map is just like the dictionary of Python。 yep， mapping is just like dictionaries and unordered map is just like a dictionary in Python。

Is auto S equals unordered map preferred over？From scratch， I don't。Think we have a。Preference。

For that。I'll have to get back to you on that， but we do talk about it in week three。

 so if you can wait till week three， you'll get a better answer， I believe。

And is a set a hash mount without a value， yes， it is， that's correct。

I'm not too sure I'm men in Devvancher's questions。

 so you might have to explain those too again to me。Cool。

 so last couple of things before we get onto the assignment。So。

This is just thrown at the end of this because I think it's really important。

 which is understanding the different types of errors you get in your code because。

Your programs will have different errors。 Sometimes they'll go wrong for different reasons。

 and it's important that you're able to appropriately communicate。With people。You know。

Like what's actually going wrong。 So， for instance， the four types errors here。

 first ones a compile error。 compile errors are pretty straightforward。

 It's when a compiler knows something's wrong right， you go to compile， it's like na。

 that doesn't make sense。 So if you just say a equals 5， it's gonna be like what's a。

 you haven't defined or declared what A is， I have no idea what that is。 please don't do that。



![](img/19b429d67b955be61d2c4d78f317efc9_120.png)

So that's a compile time error。 We all get that because we know the compiler fails。

 One thing that we， you probably aren't familiar with though as much is link time errors。

 And these are really important to distinguish between， because。



![](img/19b429d67b955be61d2c4d78f317efc9_122.png)

A link time error。 We can try this out。 Let's just override。Let's override 1，10。

So we've got this really simple program here。And it's a main function that tries to print out the return type of is 67。

71。 Now， in another world， we would have implemented this。 we would have said is 6771。

 and we would say ball， and we would maybe return true。Like this。Why does that look so funny？Oh。

Every year， sure， that's probably fine。 And when I try and run this， it probably works。Right。

 and then we can probably。Run it and it says one， right。

 because ball is when you try and print out a ball。But is the thing if we don't。Do this。

 It will still compile。 It just won't link properly， because。Remember。

 your C++ programs are a series of files that are all compiled separately and then linked at the end。

 so if I build this。

![](img/19b429d67b955be61d2c4d78f317efc9_124.png)

You actually get a different type of error and it's really important to understand that this is not a compile error。

 This is a linking error。 your code has successfully compiled。

 You could compile this to a dot O file but what you can't do here is actually turn those compiled files。

 link them together into an executable something that you can run and that's because it compile this but when it went to link them together。

 it was like I cannot find this function you did not link me with another compiled thing。

That I can actually finish this with。So they're linking errors。 So it looks like a compile error。

 but it's actually a step beyond that。 We have run time errors。

 which are things that we can't detect a compile time that go wrong。 So， for instance， you know。

 if someone。The file can't be found or anything like that。嗯。Pretty simple， like divide by zero。

 10 of 90， things like that， runtime crashes。And then we have logical programming errors。

 so these are things that don't always crash。Necessarily， but。Sometimes they're undefined behavior。

 So these are sometimes the worst things。 So these are when like。The compiler doesn't care。

In runtime， it doesn't crash the program， but it doesn't do the right thing。

 And these are the most dangerous types of errors that exists。 So， for instance。

 this is valid code here to say autocon empty equal standard string and then to try and index the zero with element。

 because in C plus plus for performance reasons。It does not do bounce checking on indexes。

 So just like C， if you try and say empty of 0， empty of  one or empty of 10。

 see the C plus plus like will not。DC plus plus the you know。At runtime。

 it will not check it for you so this code。Will actually run。 and it might seg fault。 It might not。

 It's what we call undefined behavior。 The compiler says。You know。嗯。I will do my best， but like。

Anything's kind of possible And a similar kind of thing here。 This could also be bad。 So this is。

 these are like logical programming errors。 They have undefined behavior in general， as a principle。

 everyone in the world wants。To move these errors up。 So， for instance， like。

Compile errors are great， Theyre the best kinds of errors compiler picks up on it notices it we all want compile errors in a perfect world。

 everything would be done at compile time right so that like and that's what Te are like tests aren't for compile errors Tea for runtime errors and program logic errors so that's why we like type languages that's why all of this because we can move it further up towards compilation and that's why these ones are so dangerous because there's less and less eyes on them to make sure they're working。

So the very last thing before we get into the assignment is just a tiny little demo on file inputs and outputs。

This is not that important， this wasn't actually normally included， I only included it。



![](img/19b429d67b955be61d2c4d78f317efc9_126.png)

Today or like like this week because I thought that people are curious about it and I'm not going to go through it in excessive depth that's actually just here as like a code sample for you to play around with。

 but essentially in C+ plus when you open files in you when you open files you generally open files as a stream so in C++ there's this notion of a stream which is kind of like a buffer。



![](img/19b429d67b955be61d2c4d78f317efc9_128.png)

![](img/19b429d67b955be61d2c4d78f317efc9_129.png)

Or whatever， where if I want to open a file to write out to。

Then I will create an output file stream or OF stream。

 and I'll call it F out and I'll give it the name of the file。

So this is me saying I'd like to open this file to write to it。嗯。

And then if I want to start writing to it， I might open another file called data dot in。

Which is me opening an input file stream。And you've probably seen in your tu。

 And if you haven't already， you will see that you can actually like read from。Standard C N。

 So like in the tu， we do something where we're like C N and read into a variable。

 C N is just a stream。 you're taking that stream and you're reading into a variable。

 It doesn't have to be standard inputted。 It can actually be a file， which is what's happening here。

 So you're saying that we want to open this file data dot in as an input file stream。

 And then we want to stream out of that file into a variable Some data。嗯。

And then on that input file stream， there's some things you can check like， is it a bad file。

 Is it the end of the file as you're like looping through that， et cetera。

 you can also close the file at the end。 now again， there's a lot to this。

 We could talk about this for 20 minutes if we want to。

 And we don't actually get you a don't think to explicitly do any opening or closing of files anytime and soon。

 So it's more again， just like a， you know， this is doable go play around with this example if you'd like to。

And you can ask questions about it in your tutor in the forum and stuff like that。

So I'm just going to answer a couple of questions。Just to jump back to demo 112， Devonche says。

If you go to line 21， yep。You see this four autocon if name is just an address。

Why can you print the value that name is pointing to。Well， it's not an address。

 that's what I mean like references aren't addresses。

 they're aliases and name is like just because it's a reference to it it doesn't mean that name stores a pointo it's saying name if you use name。

 it's like you're using the real thing so。Printing name is like printing what it references。

 they're identical。Peng says， how can we distinguish these two from the output？

I'm sure that was from a previous question， I'm sorry I must have missed that。嗯。

And then an IO here what does in mean yeah it means read into it what I'd say is go to your shoot this week if you haven't been already or go watch the recording because we do talk about streaming from standard input a bit and if you can understand streaming from standard input then it'll make a lot more sense what streaming from an input file stream actually does as well so you can check that out。

Min said。Okay， so I understand Min's question。 So what Min's asking here is I basically。

 I thought references could only reference one thing， and we can't redefine them。

 Then how his name here。Referencing all the different elements in it， right。

 Like if it can only reference one thing， why doesn't it kind of like fail after the first time And the reason for this is kind of a little bit。

Complicated， but basically every time a fall loop runs， it's like it's in its own scope again。

And we're going to talk again more about scope in week3。

 But essentially each time this for loop runs its its own scope， that's why in for loops。

 you can do something like nj equals 3 and you don't get like a compile error saying it's redefined because every time you for loop。

 it's like it's a new thing。 So everything that's defined and declared in that for loop gets like kind of removed at the end of the loop like if if you defined it in there。

Right so if I do this。This is what we call a redefinition error。

 The compiler will complain it will say you cannot do this on line 23 because you've already done it on line 21。

But if I just do it on line 23， it will。Be okay， because every time it loops， it's a new scope。

 It's kind of like refreshed in a way。 And it's the same thing with the40 cons reference name。

 It's like a new thing， every loop， so。That's why it's not a problem because it's kind of removed and then recreated every time。

嗯。Liinnk list would still be implemented with pointers。

 There's there's lots of things you still use pointers for。 Link list would be one of them。

 you can't Refences are not replacements of pointers totally they are。They are much safer， easier。

 clearer way to achieve what you want to achieve with pointers most of the time。

 pointers still have their place。 Absolutely， Otherwise。

 you wouldn't be able to use pointers in Z++ anymore。嗯。

Are there ways to differentiate two variables with the same values？I don't understand what you mean。

 sorry。Oh， great， answers is yours too。Excellent， okay。

 let's move on to assignment one because we've got 23 minutes left。



![](img/19b429d67b955be61d2c4d78f317efc9_131.png)

I will literally push this out after the lecture。It's coming straight out after the lecture。



![](img/19b429d67b955be61d2c4d78f317efc9_133.png)

打。Okay。Let's do it。 Oh， let me， let me stop the recording。 Start another one。



![](img/19b429d67b955be61d2c4d78f317efc9_135.png)