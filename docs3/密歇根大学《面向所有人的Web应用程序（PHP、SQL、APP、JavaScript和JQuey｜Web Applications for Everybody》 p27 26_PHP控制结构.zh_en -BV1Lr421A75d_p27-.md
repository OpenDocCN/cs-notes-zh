# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p27 26_PHP控制结构.zh_en -BV1Lr421A75d_p27-

![](img/cf6099e91be86794ef655c798c3e51ae_0.png)

![](img/cf6099e91be86794ef655c798c3e51ae_1.png)

So now we're going to talk a little bit about control structures。

 the if or if then else is kind of the first one we take a look at。

 There's a whole series of logical operators。 We talked a little bit about the equals。

 the no equals less than greater than greater than or equal。

 less than or equal greater than or equal these are pretty obvious and if you know other programming languages。

 they make sense。 The ones that are kind of new unless you've known C based programming languages before double ampersand is and。



![](img/cf6099e91be86794ef655c798c3e51ae_3.png)

ADouble vertical bars or an exclamation point is not。Exlamation is like not so that。

 but it comes in the beginning。 So be like not something， something， something。

 And then so we put that at beginning。 So exclamation point is not。

We use curly braces to set out the beginning and end of things， so here's a simple if then else。

 we have some variable we have as most ifs， we have parentheses that are required here。

 this evaluates eventually to a true or a false。If this is not a boolean operator and the double equals is a boolean operator。

 this could evaluate to non zero。And 0 and non0 becomes true and 0 becomes false。

 So this could be a mathematical calculation。 So if I just like put if。Dollar ants。

Which is 42 that would then become true right because this is non zero。

 if this somehow evaluated to zero， then it would become false。

So then this evaluates a true or false in this case， it's true。

 and then there's a curly brace and a curly brace。 and that's the block of text。

 Then there could be many lines in here。 there's only one line。

 and this is the true block and this is the false block like most if then else's。

 the first if part is the true part and the second part is the false part and then you have at the end you have else。

 which starts a new block， and then you have an open curly brace and a closed curly brace。

So this prints out， this comes and runs， runs， this becomes true。

 so it runs this block of code and then skips to the end and then never runs this block of code。

 so it comes hellello world。

![](img/cf6099e91be86794ef655c798c3e51ae_5.png)

White space doesn't matter。 That's， that's the nature of a sea based programming language。

 We put whitespace in。 We are very good at putting whitespace in because we just don't want to be crazy。

 So this is all pretty。 It's got indenting。 You can argue all day long about what the best indenting is。

 This has like all a big mess。 It's all concatenated together could be one long line。

 P P loves this stuff。 But humans。

![](img/cf6099e91be86794ef655c798c3e51ae_7.png)

Humans hate this stuff right， so we're very careful to be stylistically pretty。

 some languages like Python demandman indentation， PhP does not， but we do anyways。Just so you know。

 it's not essential。If you want to start a fight among C style programming programmers。

 ask them if you like the old or the new style of indentation， the old original style from 1970s。

Which I still use because I was around back then as the curly brace comes up and then the closed brace lines up with the if that you pull all the elses up onto the same line。

 And then the second closed brace lines up。 This is my favorite。But others say， you know。

 you should have this open brace and close brace on their own lines and they should line up the else should be its own thing and so I don't like this。

But I understand that this is an artistic choice when you're looking at code。

 What you should probably do is just follow the pattern。

 you should learn to read both of the sort of variance and then follow the pattern of the code that you're in。

 It's not worth arguing the other great argument is whether or not this is a tab or four spaces。

 That's another great argument to have that can def an anger programmers quite badly。

A multi branch if。This is an if， else， else else else， and like in most languages， a multi branch。

 if is the way it works is it's evaluating until it finds it true， and then when it finds it true。

 it's done so it checks them in order。If this is true， then it runs the first one。

 And if this is false， then it skips and checks。 So it doesn't even do the second check。

 It's not like it Does all the checks first。All it checks first。 it checks the first one。

 If it's true， it's completely done。Then it， if that one is false。

 then it even checks the second one， and if that one's true， then it does that one and it's done。

 And if this is false and this is false， then it'll run that。

 And you can have as many as you want in there。Curly braces are not required if it's a single line right。

 if it's just going to be a single line， some people will sort of pull this up on the end of the if because white space doesn't matter and so this is a completely legit thing。

 it's equivalent to this。I would never write this code。

 I sometimes will do it with one if and a real tiny bit of code up here。

 I'll put it up there and add a semicollon because then it's really obvious。

 But as soon as it gets this complex， I'm gonna to be put in curly braces。

 and I'm actually not even going do actually that's a sad face。

 I'm not even going to like this because if it's this complex。

 I'm going to put these on separate lines and indent them， etc ce。

 because part of the job is to write code that other people can see。

 but are not required and you can do it。 for looping strategies。 There's a while loop。

 which is a zerotri loop， meaning that it functions。 The first time in is like an if statement。

 So it's an if statement， but the difference with it is it just keeps going and checks at the top。

 So it's a top tested loop or a zerotri loop。 So in this case， fuel is 10。 This starts here。

 ask acting kind of like an if if fuel is greater than one。 true。 So then run this code。

 So then it prints room。 But the difference is it goes back up and fuel is still greater than one。

 So says broom b room。Ro， this is an infinite loop。

And it's not a good thing to do because we did not create an iteration variable。

 We have this iteration variable。 We didn't change it inside the loop。

 That's the way you get an infinite loop， so。Here is a better version of that loop。

 so fuel starts as 10。 If fuel is greater than one， do it。 the answer is yes。

 so it runs the room room， then it subtracts one and goes up and fuel is 9，8，7，6，5，4，3。

 and it's only it'll run than two， then it'll subtract it， it'll be1。

 and at that point fuel is when fuel is1， it's no longer greater than one。

So then it's going to go up。 So this is going to run 10 times， and we have a real iteration variable。

 and we are also responsible。 We， the programmer， are responsible for managing the iteration variable when we're using a while loop。

There's a one trip loop called a do。 It starts with a do statement。

 I rarely write these very rarely w tend to be how we think about code， It's a one trip。

 which means it's going to run this code before it asks the question whether it's a good idea to keep running it。

But sometimes you want a one trip loop。And so it's going to run once。

 and that's going to do whatever it does and then plus plus count。

 That's going to add one to count automatically。 So there's one of those plus plus operators that adds one to count。

 and then the it adds one to count。 And then after the addition is done。

 that's what participates in the less than or equal to5。 So this is going to run a few times。

 and then it's going to finally because we are adding one to count right here。

 that's adding one to count。 So we do have a well managed iteration variable。

 And then we end up running this thing five times1，2，3，4，5。Again， I tend to not write these。

 but back in the day， I mean， a long time ago。1970s， this was just there for completeness。

Now we use this a lot， and you might as well go ahead and learn this because every C based language has this counted for Java C+ plus JavaScript objective C。

 they all have it。So this is a counted for loop which is not like a go all through all all things in array。

 which we'll talk about that in a second， what this is is counted loop。

 so this has a bit of code that runs before the loop starts。

That initializes the iteration variable generally。 We have a test to decide whether or not we're done with the loop。

 And so the loop continues as long as this remains true。 It is a top tested。

 which means if it's initially， it's immediately false。 This loop will it'll skip right past it。

 So it's sort of functions like an if statement in that result。

 meaning if this becomes false before the loop is run even once。 the loop will not run once。

 So it's a zero trip， top tested loop。 And then we have a count plus plus。

 and this is really common to increment， that's count equals count plus 1 at the end of the loop。

 So it's kind of like down here before the loop comes up。 this code here runs at the bottom loop。

 So this just now a counted loop for equals1 to 6，1，2，3，4 or 5，6， right， So that's a counted loop。

 So this becomes kind of like an idiom。And count how you do counted loops in all C based。

 all languages that are C based， that's a counted loop。Like all C- based languages。

 the notion of break and the notion of continue are in the language。

 so the break is the simplest one， if while this loop is running， if this code executes。

 it basically takes this entire loop and gets rid of it and it just gets out of the loop it escapes the loop so you can have this this could be hundreds of lines of code。

 as soon as you hit a break， it knows which loop it's in and it starts executing at the line after the end of the loop and so that's what the break is。

The continue。Is another executable line of statement？Instead of going to the line after the loop。

 it goes to the top of the loop。 So continue says， oh， we're done。 Don't run these lines down here。

 We're going to go back to the top of the loop。 And we're going to run。 The key thing is。

 is it sort of runs through this bit right here。 So it does do the increment this third thing。

 And then it starts the thing up。 So you don't。 you need to increment your iteration variable。

 Otherwise your loop could get could become an infinite loop。



![](img/cf6099e91be86794ef655c798c3e51ae_9.png)

So that's how continue works and again， all C based languages C invented this idea of break and continue。

 not everyone loves them as much as I do， but it's something that I use and something you will probably use and then you'll meet someone who's a purist and they'll say you should never have to write a continu and I'm like yeah then you have too many of statements。

Okay， so that was roaring through some of the unique language features of PhP I didn't just try to teach a PhP because I assume at this point that you already know a programming language because if you don't know a programming language。

 you should go learn something like Python because it's way easier to learn programming in Python than it is to start with PhP as your very first language so hope this has been helpful up next we're going to do talk about arrays。



![](img/cf6099e91be86794ef655c798c3e51ae_11.png)