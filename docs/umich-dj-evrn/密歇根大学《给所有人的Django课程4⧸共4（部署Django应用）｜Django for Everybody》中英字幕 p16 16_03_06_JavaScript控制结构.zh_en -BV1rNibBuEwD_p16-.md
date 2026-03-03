# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p16 16_03_06_JavaScript控制结构.zh_en -BV1rNibBuEwD_p16-

Now let's talk about control structures， logic loops and all that kind of stuff so the first kind of control structure we're going to deal with is an ifF statement and every language has an if statement。

 we have a whole bunch of logical operators that we just got done talking about equals the double equals as the question mark triple equals is the same S and same type as not equals the not and then the and and the or double ampers sand is and and a double vertical bars is or and so triple equals and exclamation double equals。



![](img/9f21c9c4c7f9069274a2ebaa4e7407f3_1.png)

And curly braces are the way that we talk about the begin and end of the blocks that are affected by the if statement。

So other than that， we say if printency answer equals 42。

 this is kind of the question that we're going to ask and that's going to lead to a true or a false。

 if it's true， of course the first block is going to execute。

 and then there's an else and then if it's if that result is false the question is false then the else section is going to execute。

 and there it can be more than one line in here， I'm just showing one line to keep it small on the screen。

 So in this code all runs it basically。Comes in， answers 42， then this is true。

 answer equal 42 is true， it runs consoles log Hello world then skips the else clause and is all done。

 so the output of this is indeed hellello world。There's multiwayFs and you can hang them together with LCFs。

 just like in Python。And it does it in order。 if this is false， if the first if is false。

 it checks the else if， and as soon as that's true。

 it runs that block of code and then hops out to the end。

 it doesn't check all of the if questions simultaneously。



![](img/9f21c9c4c7f9069274a2ebaa4e7407f3_3.png)

And you can optional have an else clause so that if none of the if else if clauses are true。

Then it just falls through and runs the code in the else block。



![](img/9f21c9c4c7f9069274a2ebaa4e7407f3_5.png)

You can have an indeterminate loop， a while loop that runs until something becomes true。

 it's a zero trip loop， which means that it runs a minimum of zero times。

 which means it effectively functions the first time through like an if statement。

 so while fuel greater than one， do this thing in the block。

Is really like an if fuel greater than run。 If fuel is greater than one， do this block。

 Although in this case， I've built myself an infinite loop because fuel starts out at 10。 And I say。

 while fuel is is greater than one， Cons our log room。

 which means it's just going to do that forever。 And that's because I didn't change the iteration variable in this case。

 fuel。 And usually we construct these in a way that they terminate eventually。

And so I've done a much better job in the second one where I set fuel to 10 and I say well fuel is greater than one。

 and inside loop， I console log room and then I subtract one and I go up and up and up and up and then it's going to go and then it fuel will eventually get to zero and then it will exit out the loop and finish and so this here is an infinite loop and this is a finite loop。

W loops are always a little tricky because you've got to construct the iteration variable or make sure you know how to get out of the loop。



![](img/9f21c9c4c7f9069274a2ebaa4e7407f3_7.png)

The for loop is a counted loop。And it's going to run。 And so there's three parts to it。

 and they're separated by semicollonons。 Its it looks really complex， but it's not。

 So you make an iteration variable。 The first part up to the semicolon is the code that before loop runs before the loop starts。

 So I'm going to set this variable count equals one。The second part is like a while。

 and it's a top test a zerotri loop， and as long as count remains less than equal to6。

 then the body of loop is going to execute。 and then each time at the bottom of the loop。

 we're going to add one So this is going to go you know1，2，3，4，5，6 when it's equal to6。

 it's going to run the six time， but then it's going to come up and be 7 but then the loop is not going to run。

 And so that's what's called a counted loop where we have some variable that's just running through on a set of numbers in Python we would use range to do this kind of a thing。



![](img/9f21c9c4c7f9069274a2ebaa4e7407f3_9.png)

Now， like in Python， we've got the brake statement and the brake statement just says I'm going to get out of this loop。

 so if this line executes， it looks at the if there's more than one loop。

 it's the innermost loop and it just basically escapes the loop and moves on to the line of code that follows the loop immediately。



![](img/9f21c9c4c7f9069274a2ebaa4e7407f3_11.png)

Just it if it's done， get out， don't execute another line， it doesn't run that next。

 the rest of the iteration， it just skips out of the loop completely。



![](img/9f21c9c4c7f9069274a2ebaa4e7407f3_13.png)

Continue。Is another very useful thing you can basically say discard I want to give up on this iteration and go back up and do the next iteration。

 but the thing is this increment usually is this third part of the for loop。If you say continue。

 that actually runs， so it actually continue goes and does the plus plus。

 and then it does the check and then either continues to run back here or it jumps out if count is now greater than 10。



![](img/9f21c9c4c7f9069274a2ebaa4e7407f3_15.png)

And so continue works pretty much the same in loops， in JavaScript as it does in。In Python。



![](img/9f21c9c4c7f9069274a2ebaa4e7407f3_17.png)

So you can also loop through objects， and so here's an object that has three attributes， golf。

 tennis， and ping。And I can say four ball in balls。

 And then that means that this iteration variable is going to walk through the keys or the attributes。

 So it's going to be golf， p and tennis。 And then I can use the look up syntax to look up。

🎼Balls sub golf， balls， sub tennis and balls of p。 And then print all those things out。

 So that's what's called a definite loop that's looping through an object that that we're going to see。

 Now， when you're looping through an array， which is a linear list， you actually use a counted loop。

 not a definite loop， but objects。

![](img/9f21c9c4c7f9069274a2ebaa4e7407f3_19.png)

whichch are like dictionaries， which are like associative arrays。

 will use definite loops to loop through them。So that is a quick ro through JavaScript。

 not so much to get to the point where you can write a bunch of JavaScript。

 but so you can read it and then when you get a syn text there， hopefully you can fix it。

