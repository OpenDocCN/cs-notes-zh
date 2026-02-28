# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P25：25_02_10_条件执行.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

Welcome back Now that you know how to repeat steps with a for loop。

 the only piece remaining to implement the green screen algorithm is to be able to make decisions based on a condition。

In this algorithm， we wanted to look at a pixel， see if it's green。

 and then do different steps based on whether it was or was not green。

Now let's learn how to implement decision making。Decision making is done with if else statements here you see an if else statement。

 which looks at the condition is x less than y， and then decides which set of statement to do based on whether that is true or false。

This example assumes that the variables are declared and initialized previously。

 Let's break down the syntax。 First， you have the keyword if。

 which tells jascript that you are writing an if else statement。Next。

 you have the condition to make a decision based on here it is x less than y。

This condition is an expression written inside apprenheses。After the conditional expression。

 you have the then clause。The then cause is a set of statements to execute if the condition is true。

These are written inside of curly braces。After the then clause is the key word else。

Then the else clause， the else clauses a set of statements to execute if the condition is false。

Again， these are written in curly braces。Sometimes you may see an if statement with no elseLs clause。

 in which case both the keyword Als and the elsets clause are omitted。

This is shorthand for an empty else clause。 whenever the programmer does not want to do anything in the case of a false condition。

Okay， now that you have the basic syntax， let's look at the semantics here we have just reached this if statement with our variables having the values shown on the right。

The first thing that happens is we evaluate the conditional expression is x less than y。

To evaluate this， we look at the values of these variables。

 the values they have in their boxes and see that we are checking if two is less than 7。

Two is less than7， so this expression evaluates the true。Since the condition is true。

 we go inside the then clause and begin executing statements there。

 we execute the statements here according to their normal rules。

This next statement is an assignment statement， Z equals2， so we update Z's box to have two。

Now we are the closed curly brace of the then claws。

We are done with the statements here and need to skip over the else clause。

 since those statements are only for when the condition is false。

 So we jump down past the end of the else clause。We would then keep executing whatever code comes next。

Now let's look at the example again， but with different values for our variables。

 we again begin by evaluating the condition expression is x less than y。However， this time。

 x is 42 and y is 7， so we're evaluating is 42 less than 7。

This expression evaluates the fault since 42 is not less than 7。

Since a conditional expression evaluated defaults， we jump into the elseLtz clause and begin executing statements there。

Again， we execute statements according to their normal rules， First， a equals y plus 1。

 which updates a to be 8， then y equals x minus 3， which updates y to be 39。

Now we are at the end of the elseLts clause， so you can just go past the closed curly brace of the ElLts clause and begin executing whatever code comes next。

You have seen several important concepts separately。

 but it is instructive to see them all put together， as in this example。

One important thing to remember when putting pieces together is that they generally follow the same rules。

 no matter how they are combined。A concept called compositionality。

Let's see what this code does First， we declare a variable called IMG and initialize it to a new simple image。

Which is the two by two image you saw in previous examples。 Next， there is a for loop。

 which iterates over each pixel and IM G dot values。 You've already seen how this works。

And we will again follow the same rules。We create a box for the pixel variable。

 initialize it to the first pixel in our image and go into the body of the loop。

Now we have an if statement。It does not matter what this this statement is inside a forlope。

 It still follows the same rules。Is0 greater than or equal to 2 divided by 2？No， that is false。

 So we go into the elses clause and execute statements there。

 This will set the pixels blue to the pixel's red value， which is 255。

Changing it from red to magenta。Now we're at the end of the else clause。 So we go outside of it。

 which brings us to the closed curly brace of the for loop。

 So we go to the next pixel and back to the top of the loop。We again， go into the loop body。

 but now the pixel's X is one。 So we're asking， is one greater than or equal to 2 divided by two。

 That's true。 So we go into the then clause and execute the statements there。

Pixel dot get red divided by2 is0， divided by2， which is0。 So we set the pixels red to 0。

 which does not change anything since it was already0。 We are now at the end of the then clause。

 So we jump just past the closed curly brace of the al clauses。

 We have again reached the end of the for loop。 So we go to the next pixel and jump back to the top。

This pixel's x is 0， so we are again evaluating is 0 greater than or equal to2 divided by 2。

 which is false。 So we go into the elsets clause。 We execute that statement and leave the elset clause and go to the next pixel as we jump back to the top of the loop。

Going back into the loop for the last pixel， we evaluate the condition， which is true。

 So we enter the then clause。We are going to set the red to 127。5。

But pixel set red will round that to 127， since the pixel only works with integer RGB values。Now。

 the pixel is light cion instead of white。 We have reached the end of the then clauses。

 so we jump past the end of the altz clauses， which brings us to the end of the forelet。

We go back to the top and there's no more pixels， so we jump past the end of the loop and begin executing whatever code might be there。

Thank you。