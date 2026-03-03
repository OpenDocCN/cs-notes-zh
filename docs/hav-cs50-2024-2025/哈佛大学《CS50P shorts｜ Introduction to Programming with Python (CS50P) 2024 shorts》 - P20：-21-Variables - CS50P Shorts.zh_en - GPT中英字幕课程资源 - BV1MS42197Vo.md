# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P20：-21-Variables - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

![](img/7d1ff47c2114261aea5462b9a184798e_0.png)

Okay， now in this short we're going to take a look at one other building block of our programs in this case variables and variables should be containers for some value that can change over time so let's say I want to make a guessing game where the user can guess some number and I'll tell them if they guess correctly or incorrectly Now it would be probably worthwhile to have some way referring to the user's guess in my program What number did they guess and that is a great use case for a variable。



![](img/7d1ff47c2114261aea5462b9a184798e_2.png)

So I want to make a variable in Python， I can do it by typing the variables name first。

 so what's a good name for this variable， I might say something like just guess。

 so guess is name of our variable our container for the value that you're going to give us that we can store over time。

😊，So I'll call this guess here。And now I want to assign this container called guess some value。

 some number to hold as the user's guess， so let's say the first guess by the user is 10。

 I could store that value 10 by saying guess equals 10 and this equal sign doesn't necessarily say that guess is equal to 10 now。

 but more so that we're going to assign this value 10 to be inside the container that we're going to call guess。

And now that I've done that， if I want to print out the guess， see what is inside this container。

 I can do that online too， I could say print guess， now I'll say Python of guess。

 pi and I should see 10 printed back out to me on the screen。

Now variables become really powerful and we combine them with things like functions。

 so let's try to make our own function that can get a user's guess。

 Now one way to do this is to define some new function and I might call it maybe like get guess。

 so I'll say de， define me a function called get guess。😊，And I'll take no input。

But I'll then inside this function， define myself a variable called guess。

 and I'll set it equal to 10 here， just like I did before。

 and now I'll have that function returned to me as we saw in the return value short， this guess here。

 return guess itself。Now down below， I could say print get guess， just like this。

 which will run the get guess function and then print the return value。

 which in this case is this variable called guess， so I'll say Python of guess dot pi and I should see 10 again。

Now， it would be not a great program if the user had to open up guest dot Pi and change their guest every time。

 So ideally， we would actually let them type in their guests in the terminal and there is a function for this called input in Python so I could set this variable instead of being equal to the number 10 equal to whatever the user types in a terminal and I could say input just like this enter。

Enter a guess。 So now before we assign this variable called guess of value。

 we'll run the input function。 We'll print this text， enter a guess。

 and whatever the user types in will be now stored in this variable called guess。 So let's try it。

 I'll say Python of guest dot pi。 And now I'll type in 20。And I should see I printed out 20。

 so that means that the return value of get guess is 20。

 What if I did Python of guess dot pi again and I entered5。Well in that case。

 it seems like the return value of get guest changes as I type in numbers here。

 so that's pretty handy for me。Now what if I also had a way to compare the guess against some actual number here。

 well I could go ahead and define the main part of my program and get working on the functionality to check the number that the user actually gave us so I'll say define the main function now and inside of here I'll maybe make a new variable called guess guess equals and then say get guess so now what's going to happen is get guess will run and its value will be assigned to the guess variable here。

Now one question you might have is that it seems like I'm using these variables guess multiple times and isn't that something I shouldn't be doing Well。

 it turns out that because these variables are inside of different functions。

 they can be used in different contexts， in which case they will never refer to that same value。

 they can be separated， let's say by these two functions。

So now I'll go ahead and I will run Python of guest。 Pi actually before I do that。

 let me go ahead and actually。Run the main function down below。And let me try to run Python of guest。

 Pi and also enter a guess， I'll type 10。Nothing yet。

 but I haven't really printed anything over here， so I want to go ahead and now print the guess I got from the user and now I see 10 overall。

And again， this worked because these two variables are inside of what we call different scopes。

 this variables inside the scope of this function， get guess。

 whereas this guess variables inside the scope of this function called main。

So let's go ahead and actually compare the number here and the number I'm thinking of is number called 50。

 so I'll say if guess is equal to 50， why don't I go ahead and print correct， just like this？

Or let's say maybe the guess isn't 50 in this case I'll print， I'll print incorrect， just like that。

 so now this is our program in its entirety。And this here simply is a question we're asking if guess is equal to number 50 we'll print out correct。

 if it's not， we'll print out incorrect。So now I'll go ahead and I will run。Python。Of guess， dot pi。

Hit enter， and I'll say， maybe I'm going to guess 50。But I get incorrect。

HSo it seems like I typed in the number 50， but we went to check if guess equals this number 50。

didnn't seem to see that it is that same number。Now this is a bit of a tricky scenario if you're new to programming。

 but it's also one that kind of shows different kinds of variables we can have。

 Now it turns out that in Python there are many types of variables you can have one of them being like an integer as in like this number 50 here and one of them being a string where a string is some collection of characters and in this case when I use the input function I'm actually getting not the integer 50 but the string of numbers like 50 so to illustrate this real quick here I'll say this is the number 50 but this is the string 50 and if I were to say does 50 equal the string 50 I would get back that they actually don't equal each other So this is an example of different variable types and it's often useful to compare variables of the same type because if you were comparing like let's say the。

The word cat， it's number 50。doesn't quite make sense。

 so let's try to actually convert the result of the input function to a whole number。

 and I can do that by using this function called int。

 which takes some text and converts it to or at least tries to convert it to a whole number like 50 or 25。

 for instance。So now I will store inside of this guess variable， inside the guess function。

 the number 50， and then later on I'll compare that number 50 against the number 50 down below。

 so I'll say Python of guess dot pi hit enter， and I'll say 50 and now I see it's correct。

 I'll say Python of guess dot pi and let me try now 25 and I guess incorrect。

Let's say I want the user though to actually type in the let's say type in like 50， for instance。

 or 10， just like this。 that would be an example of a string。

 not some whole number like an integer so I could change my program。

 I could simply revert the int from this and now it'll give me just plain text and I could compare I could say is guess equal to this string called 50。

 I could check that I'll say Python guest dot pi and now I'll say 50 and that seems to be correct。

 I could say Python guest dot pi and guess 10， and that seems to be incorrect So the type of variable you use often depends on the context。

And as you go off and write more programs， hopefully you have to see how powerful variables can be and what type might best suit you for each scenario。



![](img/7d1ff47c2114261aea5462b9a184798e_4.png)

![](img/7d1ff47c2114261aea5462b9a184798e_5.png)