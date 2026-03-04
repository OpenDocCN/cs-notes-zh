# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p36 35_08_another-expression-example -BV1bw4m1D7MM_p36-

The purpose of this segment is to just give you an example of me writing a function like you might do on your homework。

 What I want to do is continue using this important data type binding we've introduced for arithmetic expressions where constructors are for constants。

 negations， additions and multiplications and the function I want to write is max constant It's going to have type X arrow int and what it's supposed to do is find the largest constant contained anywhere in the expression So on the homework I would typically just ask a question like that。

 write max constant and it's up to you to figure out what concepts from the course are relevant。

 how to use them the difference between a solution that seems to work and is correct versus an elegant one that uses the concepts in the best possible way So this example is going to show a number of concepts we've studied nothing new so in that sense its review or it's optional and the entire rest of the segment will just be spent over in the emax buffer as I try to write this with you So I've got things started here in a short example file I have the data type binding that we need and I went ahead and wrote a test case here。



![](img/e4c6049fa8b3891fa75471bd64cff795_1.png)

I have a test expression and then I call max constant on it。

 that's just to emphasize that it's often good software engineering practice to write tests even before you've written your functions in order to understand what answer you expect and how the function should behave and then I obviously still need to write the body of max constant So let's just get started the first thing that seems obvious is that we're going to need some sort of recursive function that uses a case expression so I'm going have to case on this and I'm going to have to think that if I have a constant then the maximum constant in it is just I that's a nice base case for my recursion otherwise if I have a negate of some smaller expression then I should just compute recursively the max constant in E2 so far so good two cases down to to go if I have an add I'm going to bind to two smaller variables E1 and E2 and now I have to figure out the max of each of them and take the bigger one so what I might do is I might say if max constant of E1 is greater than。

Max constant of E2， then return max constant of E1。

 This should probably be setting off some alarm bells， but that's okay。 It's a fine first attempt。

 And if that looks okay， that's fine。 And if anything seemed sort of fishy about the style of that part。

 notice that now what I'm going to do is say that in multiply。

 it's really the exact same thing I need。 So how about I just copy and paste the code down there。

Allright， so copy in paste is often a bad idea。 We'll get back to that in just a second。

 But let's see if we have a working solution。 So let's just go over here。

 try use do xml and sure enough， my test case passed， I vow 19 equals 19。 And in fact。

 I'm not kidding you。 This is actually a correct solution。

 I believe it will technically produce the correct answer for any X that you would pass to it unless I've made a mistake。

 I don't realize here， but it fell into this trap of recomputing recursive results。

 which we know could lead to a very inefficient solution。

 we won't see that if we tested only with small expressions。

 But if you tested it with a very deep expression with a somewhat large expression。

 you could see this problem come up pretty quickly。 So we know how to fix that。

And that's with let binding。 So what if we said let Val M1 equals max constant。

Of E1 and Val M2 equal max constant of E2。 And then just said。

 if M1 is greater than M2 than M1 else M2。 All right， and that。

Would be fine and never cause anything recursively more than once。

 And now I could just paste that down for multiply because I still want to do the same thing there。

 And I want to fix the same problem。Allright， so let's try that out。 All right， let's restart here。

And it works again。 So this seems better。 Allright， And that's a perfectly good second solution。

 But now this cut and paste is really bothering me。

 And it's not particularly good style to duplicate code like that。

 And we know how to avoid duplicating code。 We could have a little helper function。

We could have a little function up here that' say took two expressions and returned the maximum constant in either of them。

And it turns out E1 and E2。 Now it makes perfect sense to go ahead and cut this and paste it up here because it's exactly what we want for the body of this function。

 All， And then we can use that here in add。 We can say max of 2 E1， E2。And now， yes。

 this is a little bit of cut and paste。 But just to call a helper function， that is just fine。

 And we can delete this。 And now we need an end to end the let that created our local function binding。

 And that is a solution I'm pretty proud of。 Allright。

 so let's go back over here and try that one out。😊，It's still working。

 So let's hope it's still all correct。 And now we're probably pretty good。

 Let me show you a couple more versions， though， that I like。

 It turns out that this if M1 greater and M2 than M1 else M2。

 It turns out if you knew a little bit more about the standard library in SmL。

 there's a built in function that computes the max of two integers。

 And whenever there's a builtin function， it's usually easier to read reader of your code who knew there is an int dot max would probably be much happier to just see that and then try to read your if then else and figure out what's going on。

 So that would be a perfectly good solution。😊，And now， once we have that， believe it or not。

 I'm going to start undoing some of the things I did before。

Because now these local variable bindings， there's nothing wrong with them if you find this easier to read。

 but I'm no longer risking with that。 if than else， of computing the maximum of anything twice。

 I could go ahead and just write in here。 max constant of E1 and max constant of E2。

 And now I don't need this let。And I don't need this in。 And I better get rid of the end。

 And that is because when you call a function like in dot max， In do max is just a function。

 We evaluate the arguments to values before we call the function。

 So we're gonna call max constant of E1 once。 We're gonna call max constant of E2 once。

 Then we're gonna to pass those resulting numbers to int max。

 which is going be implemented with an if then else and do the right thing。

 So this will be efficient。 There's no concern about a very slow function。

 And let's make sure that this one's still working。

 I don't like to do too much work without checking my work。 Okay， we're still good。

 And now there's local helper function that we wrote。 is so short。

That you could argue you don't need the style of a local helper function just to save this actually pretty small computation here。

 So now let's undo that local helper function as well。 Take this。Paste it in here。

And paste it in here。 It's a little long for using twice， but not too long。

 It actually looks a little worse with the font blown up here so you can read it easily。

 It really does fit on one line。 How about I move things over just a little bit here So you can see that all together。

 You would have more columns on your screen than I would。 Alright。

 And now we can get rid of this let in。In this case。And make sure it also works。And it does。

 And this is actually pretty pleasant to read to compute the max constant of an E。

 Let's pattern match on E。 if it's a constant， then just return it， if it's a negation。

 recursively compute the constant of E2。 If it's an addd。

 compute the max of the maximum constant in E1 and the maximum constant in E2 and the same for multiply。



![](img/e4c6049fa8b3891fa75471bd64cff795_3.png)