# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p14 13_03_the-repl-and-errors -BV1bw4m1D7MM_p14-

All right， in this segment， I want to take a brief break from building up our conceptual framework for understanding ML to go through a couple more pragmatic topics。

 namely how to use the Reple that readtaval print loop effectively。

 as well as how to deal with error messages and show you a bunch of examples of errors that are fairly common when starting to learn ML。

Okay so we want to ask a couple questions， first of all is how do we run programs using the Reple and what does it mean to have a Reple and then what happens when we make mistakes and how can we go about debugging those mistakes and fundamentally debugging is a skill you develop over time and I just want to give you some practice with it by watching me do some。

So the way we've been using our repple was primarily with this use expression and really the way I want you to think about it is that it takes the contents of a file and it's like you typed in those bindings。

 those variable bindings one at a time into the repple and that really is what happens So if I take this file which we've seen before it has a bunch of bindings when I come over here with control C control S return to bring this up I could manually type these in one at a time。

 Val x equals 34 L y equals 17 and so on but instead when I say use first SmL， it does that。

 but all at once in a batch showing me the result of doing all of those bindings what are their types and what's the result of evaluating them and that's all that it's doing and it's convenient that way and so when you look at it this way what it's actually going on is the meaning of our programs is that all we have as a repple and use is just a。



![](img/c4d3140de295ad40c73897f2943ec466_1.png)

![](img/c4d3140de295ad40c73897f2943ec466_2.png)

Convenient way to use that rebel。So Repel stands for Read Aval print Lo。

 and it's actually pretty well named that what happens at that prompt when you type in a binding is it reads it。

It evaluates it， although if it doesn't type check。

 it just gives you an error message to that extent， it prints the result。

And then the loop part is about how it gives you another prompt back so that you can continue。

So we can just think of this as a strange way to run programs where we open up the Reple and then we typeU。

 but it's often quite convenient for after you typeU to then go ahead and try a few things out。Now。

 after you type use， you find yourself typing the same thing over and over again like you're building up a collection of test cases for。

 say your homework problems， you're probably not making an efficient use of your time。

 and it's better to go ahead and move those tests into a second file and then go ahead and use one file then use a second file that's going to include all your tests and then maybe do a little extra playing around。

 But what I don't ever recommend for reasons we'll discuss in the next segment is typing use playing around and then using the same file again。

 instead， what you'll always see me do is come over here to the repple type control D to end my session。

 Control C control S return to restart it and then it's okay to type uses again with a file。

 The repple won't stop you from doing it another way。

 but I don't recommend it because it's often very confusing what's going on。



![](img/c4d3140de295ad40c73897f2943ec466_4.png)

![](img/c4d3140de295ad40c73897f2943ec466_5.png)

Okay， so now let's turn to errors。 Usually when I show you programs here in the video。

 they just work。 I'm trying to demonstrate something， but we all make mistakes。

 You could make a syntactic mistake。 You don't write something down the way you expected。

 You can make a type checking mistake。 What you wrote down is the correct syntax。

 but it doesn't follow the type checking rules for the language concept you're using。

Or it might type check and then run and either it produces an exception or it goes into an infinite loop。

 or it produces an answer， a value， but not the value you wanted。

 So debugging has to attack all of these problems。 And one of the hard things is you often don't know which mistake you made。

 And the error message you get from M may not help either。 and there's a few reasons for that。

 Well the good reason is， well， you wrote something that isn't what you intended。

 So whatever error message you get is just M's best guess as to what might be the problem。

 but it's up to you to figure out what actually the problem is。

 And the other thing is that as much as I love M is a language and love having a read ofvalprint loop。

 the error messages you get， particularly when you have a type checking error are usually actually quite bad。

 And it's really a bit of an acquired skill to to look behind them and figure out what you did wrong。

So the best way to learn something is by trying it and I want you to just try writing ML programs。

 don't be afraid of errors， slow down， find what line number the error is coming from and so forth and I thought I would help point you in the right direction by just doing a little bit of that myself so I have a second file here that iss called errors。

sml and it looks like a pretty good program here， it turns out it has a bunch of errors and this is the entire thing but suppose I wrote all this down。



![](img/c4d3140de295ad40c73897f2943ec466_7.png)

And now I go over here and I say use errorsors。sml。So it turns out it gives me a couple errors here。

 the first one you can see is at line 14， and it says syntax error inserting else ID。Okay。

 so if I go over to line 14， which you can see here in emmax out at the bottom。

 it prints out the line number。 That line is just v a equals -5。 So it's not。

 you can't look at that line and figure out why it's inserting an else。

 It turns out is often the case。 the error is actually a little bit before the line number that's being reported as the problem。

 And indeed， if you look up here， I have this if then expression。 Well Ml。

 there's no such thing as an if then expression， you need an else afterwards。

 which it thought you might want to put on line 14。 I actually want to put it up here。

 And I have to have else something how about else 42。 And that's because as we know。

 when you have a conditional expression， either branch。

 the then or the else might need to be evaluated。 So you can't leave the else off。

 Like you can in some programming languages。 So okay， we fix that error。 Let's go back here。

 come down to the end， restart things。 Try again。And by the way。

 if you don't want to keep typing this， you can type metaP to get your previous commands back and now we see an error on line 18。

 it says replacing fun with wild Now if you look at line 18 here， it might look just fine to you。

 why can't I have a variable called fun Well this often happens when you're learning a programming language we stumbled across a keyword。

 it turns out fun means something else in the language and we're not allowed to use it for a variable So we're gonna to have to change this and how about funny that should do the trick。

Quit， restart。Type that back in。 And now we get a whole bunch of error messages。

 They don't even fit on the screen because we're now don't have any syntax errors that Ml found。

 So it's giving a bunch of different type errors。 And I like to fix the first one and then come back。

 So up here at line 8， it says unbound variable or constructor X。 So if I look at line 8。Sure enough。

 I am using x right here， y equals x plus1， but it sure looks like it should be bound。

 it should be in my dynamic environment from the previous line。

But it turns out that the error here actually is syntax。

 even though it looks like type checking because I'm not actually finished with the previous expression。

 if you want to start another expression， you have to type v again since I left that off the type checker thought this entire thing was one expression and for this expression there is no X in the dynamic environment yet because I haven't finished defining it so I have to put v here by the way。

 I used to put semicolonons at the end here and you still can you have to in the repel but in a file it's not actually necessary。

 so it turns out that was not the error， but leaving off the vowel was so all right。

 so we'll try this again。And we still have a bunch more errors， but at least now we're up to line 10。

 where it says test expression in if is not of type bo。 If we go over here to line 10。 aha。

 I actually got one right。 This is actually a very accurate error message right here。

 This expression Y has type int， because that's the type of the variable Y。

 and you're not allowed to have something of type in there。 You have to have something of type bo。

 So this is just nonsense code， but maybe the programmer meant to write if y is greater than0。 Okay。

 So we fix that one。 come back here， restart， right again。Still a bunch of errors。

 still on line 10 types of if branches do not agree。

 We remember that the then branch and the else branch both have to have the same type so that that can be the type of the entire if then else expression。

 And indeed，34 is type in。 and X less than 4 has type bo。 So I don't know which of these is wrong。

 But I have to fix one of them。 How about fixing that one。Alright， back we go。

 Hopefully you don't usually make this many errors in this few lines of code。

 but we're up to line 14 expression or pattern begins with infi identifier minus this one might not make you very happy at all。

 It's actually complaining about that-5。 And maybe that seems crazy to you。 but an M。

 the only thing you can use-4 is as a binary operation like x-5 or 0-5 or 13-5 or so on。

 If you want to write a negative number， you might say oh， well 0-5 would work。

 you don't have to do it that way。 there's just different syntax in M。

 when you learn a programming language you have to learn that languages syntax rules。

 And it turns out that negation of one argument is the tilde character with or without a space here。

 not the minus character。 you can't use， you have to use tilde and that will fix this problem。😊，And。

We're up to line 20。Operator and operaan don't agree real star real in star n。

 The expression it's complaining about is this X slash W。

 where presumably I was trying to do a division。 Well。

 that is how you do division on floating point numbers in M， which it calls realels。

 but it doesn't apply to integers。 You're not allowed to use slash on integers and M。

 That's just the type checking rule。 but there is a different operator for division。

 and it's spelled DV for div。All right， so we maybe looked that up somewhere。We've got that fixed。

 and now we can run this， and。That looks like a very different kind of message。

 So it turns out we're not getting a type checking error here at all。

 We're now actually everything type checkedck and we're running the program。 But when we ran it。

 we got an uncalaught exception for divide by0。 like in many languages， you get an error。

 if you divide by0。 When you run the program， it's not a typing error。 And sure enough。

 if you look at this x div W。 when we go to evaluate W。

 we look it up in the dynamic environment and we get 0。 So if we don't want that error。

 we're gonna have to do some different division。 How about dividing by W plus1。

So let's go back here one more time。And look at that。 We actually ran。 We have a bunch of types now。

 We have a bunch of values。 but if you look at the end， not this Val it。

 that's the result of the use itself。 but the last variable binding we did。

 I created a variable 14 and it is bound to the value 0 of type end。

 Now that's not necessarily a problem。 but maybe it's not what I meant。 and I brought this up。

 I included this just to remind you that sometimes you get this great sense of satisfaction when it all type checks it all runs。

 but you still have to make sure you have the right answer。 And if I wanted this to be 14。

 I brought it in one7-7， I wanted 7 plus 7。 Of course there's no way a type checker or an automatic tool can know what I meant14 is just an English word。

 but you still have to test your program and look at the answers and make sure it all works。

 and in this case， after fixing that I'm finally happy with what I've got。 And so let's stop there。😊。



![](img/c4d3140de295ad40c73897f2943ec466_9.png)