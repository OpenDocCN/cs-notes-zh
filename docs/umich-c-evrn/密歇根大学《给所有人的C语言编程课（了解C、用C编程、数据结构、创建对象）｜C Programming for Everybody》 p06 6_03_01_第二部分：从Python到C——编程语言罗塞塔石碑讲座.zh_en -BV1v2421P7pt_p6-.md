# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p06 6_03_01_第二部分：从Python到C——编程语言罗塞塔石碑讲座.zh_en -BV1v2421P7pt_p6-

![](img/de08f7b781a5b29c46451061737ced75_0.png)

There's another way。That's a little safer to do this。

 And these are the exact same thing where this command F get S。 So F get S says。

 put it into the up to 1 thousand0 characters looking for a new line。

And reading from what's called standard input。 So in C， there are three basic files。

 one is the standard input， which usually is read through to up to EOF standard output。

 which is where printf is going， and then there's a thing called standard error。

 which is where you send error messages that you don't just go want to go to the output。

 So the input and the output， like if you're going to make a program to do uppercase you would read your input。

 you would uppercase it， and then send it out， but if， for example。

 you encountered a character that you didn't want to copy and you wanted to send an error says I'm not going to copy。

 you wouldn't just send it to standard output， you actually send it to standard error when you're running。

Just on a terminal， like in your command line， standard input is their keyboard。

 standard output is your screen and standard error is your screen。

 so you can see both the error messages and the output of the program。

But if you're running sort of with redirecting input and output。

 you do tend to still see the error message on your screen。

 and it doesn't end up hidden in some standard output。喂。In this case， we're using FKS。

 which is part of the standard library and we are saying read this from standard input Now you'll see in a second when we read a file。

 FKS can read a file and that third parameter is the file handle。

 but there are three predefined file handles in C programs， standard in standard out。



![](img/de08f7b781a5b29c46451061737ced75_2.png)

And standard error， they're all named SDD IN。 that's their name， their're predefined constantss。

In the C standard SIio。h library。 Okay， so now we're going to read a file。

 we do this a lot in Python。

![](img/de08f7b781a5b29c46451061737ced75_4.png)

We go get a file handle。 It reads it。 This might fail。 Of course， if the file doesn't exist。

 then we go out a nice determminant loop。 Remember we talking about an enddeper loosen。 this forin。

 It's so Pythonny， and it's so awesome， and it's like， so expressive。 I love it。 I miss it。😊，Okay。

And then line dot strip， which takes the new line off， and so that's going to read， you know。

 just read reads little file， writes it out。

![](img/de08f7b781a5b29c46451061737ced75_6.png)

So we have to create a variable， we'll call it  a thousand0 characters。

 we now we are in Python we could have any length of characters in our file and it would work but in C。

 now we're going to have to actually say we can only handle up to 100 characters because we've declared the line that we're going to use the line variable we're going to read this in has  a thousand00。



![](img/de08f7b781a5b29c46451061737ced75_8.png)

There is a equivalent to the handle， file is a type it's defined in STD outth， star hand。

 which means it's a pointer to a file object。And hand equals F open Romeo。ttt R。

 so that's two character arrays， Romeo do Txt and R and actually。

The open in Python is inspired by the F open in。嗯。And see， and that's because again。

 when they were writing Python， they were writing in at C。

 why don't we take an open and all they did was made the open in Python be a little easier。

So we don't have any kind of a。IO4 in， so we have to write our own while loop here。

So we're going to call F giS line。Give me up to 1000 characters from the file handle， named hand。

And FKS returns null， which is a constant that's defined in STD doh。 If it is reaches end of file。

 So this basically is a loop that says read everything up till end of file。

 very similar to this four line in hand。 and then we're printing it Now I don't have to strip it because FGS actually takes the new line that is the end of each line。

 So in Python you would get double spacing if you didn't strip a new line at the end of each one of these little things。

 right， each line， whereas the fGS is's nice enough not to give us the new line。So there we go。

So counted loop。Now this honestly is not one of my favorite things in Python。

 but this range is a generator that's going to generate the number 0 through44 I in range。

 this is effectively kind of a dynamically generated set and then we're going to print it so we're going 0。

1，2，3，4 and C we of course have to declare the I is going to be an int and the for loop has three。



![](img/de08f7b781a5b29c46451061737ced75_10.png)

Pieces separated by semicols， there's the initialization piece。

 Now PhP and JavaScript are the exact same thing so that this looks familiar to you。

 that's because you took those classes， congratulations。

So for equals 0 is the initialization that says before the loop starts set I to 0。

 Then there is the middle part is the test。 whether or not the loop should run or continue to run。

 It's a top tested loop。 And so I less than5 must be true or the loop won't run at all。

 But given that I is0 at the beginning， it's less than5。 So it's going to run at least once。

 And then each time through the loop at the bottom after the loop is run。

 We're going to add one to I with a I plus plus a post increment operator。 And again。

 that line of code。 P P Javascript Java all look the same。

 except P P has dollar signs for variable prefixes， which yeah bothers me， but it is what it is。

And of course， we have a block。Curly brace， open curly brace and close curly brace denote the block。

 And then we simply print the variable out， and both。

 both bits of code produce the exact same output。 So if we get a little bit trickier。



![](img/de08f7b781a5b29c46451061737ced75_12.png)

We're going to do a take an example from a Python for everybody class and look at the max and min and because we need to prime the loop。

 we're going to set our max Val to nonen and the min Val to none。

 and we're going to do a middle tested infinite loop。



![](img/de08f7b781a5b29c46451061737ced75_14.png)

While true。

![](img/de08f7b781a5b29c46451061737ced75_16.png)

We're going to read the input line each line like 5，29。

 we're going to strip it just because we're going to check to see if it's the string done if it is。

 we're going to break out of the loop， right？And then we're going to convert it to an integer。

And we're going to check to see if max v is none or the value we read is greater than max Val。

 we're going remember it。 And if min Valal is none or the value we just read is less than minve。

 we're going to remember it and when the loop finally reads all the way through。

 we're going to print out the maximum and the minimum So this is pretty much the same code except we're using scanf with a percent D format input format and scanning into the v integer variable and using Ampersand to indicate that it's called by reference and to replace the current vow and then the rest of it's the same if it's the first one or we've got a larger one we keep it if it's the first one or we got a smaller one。

 we keep that one as well， we loop through and it all goes。

 Now one thing that if we're using scanf and as I mentioned before scanf doesn't sort of stop and the end of lines。

 it keeps on going and so if if have5 to and9 and again we have to use control D or EofF here to finish this。



![](img/de08f7b781a5b29c46451061737ced75_18.png)

OrF25 space2，5 space 9， and then EOF， it does the same because scanf is just looking for an integer it's really its algorithm。

 we'll see this in chapter 8， but the thing that it does it's like get me an integer。

 which means throw away stuff that's not an integer So away you go。

 So that's a slightly more scphonic version of this min Max using scanf and it doesn't suffer from the problem of using get us and having to worry about the size of the arrays。



![](img/de08f7b781a5b29c46451061737ced75_20.png)

B character race。Here's a guessing game。 That's one of my favorite applications。

 so we have an infinite loop， the ultimate nondeterminant loop。

 a loop that you got to examine to know that it's going to finish。

 and in this particular one we're just looping to EOF you're using try and accept why because line doesn't give you any return indication that it's hit into file so we just have to like have it blow up and then do an accept and then jump out。



![](img/de08f7b781a5b29c46451061737ced75_22.png)

Oh， well。So we throw away the new line。And then we convert the line to an integer， and we say。

 if guess is 42， nice work， and then brake， which gets out of the loop。 the brake affects the loop。

 not the if。And then LF guess less than 42 to low else print too high。

 So this is a classic multiway if we're going to have an if you can have it kind of as many LFs as you want dot dot dot and then an L。

When you do the same thing in C。We're going to use the scanF pattern waiting till we see EOF if the guess is 42。

We print nice work and then break now we have to have curly braces here because that is a two statement block and so if you have more than one statement。

 you've got to do curly braces。And then else， this else matches up with that if else。

 if guess less than 42， print F now。Modern programmers would tend to put curly braces。

 even though this is only one line， but this print F is the statement connected to the F。

 and it does not need curly braces because what comes after an if is a statement。

Or block of statements with curly braces。And the same is true of this else。

 the print F is the single statement， so you'd not seen curly braces here。



![](img/de08f7b781a5b29c46451061737ced75_24.png)

And I would write this with curly braces， but because the authors of the book are really very succinct。

 they tend to not put curly braces and some calling your attention to that。Now。

 a really important thing to call your attention to is the difference between else， space。

 if and L if。

![](img/de08f7b781a5b29c46451061737ced75_26.png)

Now， the high level is。What we're doing in C is not really a multiway， if。

What we're doing in Python is truly a multiway if， this if and LF and else are really part of the same block of code。

But。This else if is two keywords。 And so if you look at the first if。

The first if has one block of code。Which is the printf nice work in the break。

And then the else clause of the first if is this entire block of code here。

 which is if guess less than 42， print F yada yada， and then another else。 and so this is a block。

 so this is a block if and in the else clause， there is another block if。And so if you look at this。

 really the indentation of this stuff ought to be in in this like the elsesif part and the else。

 that indentation should be further in。

![](img/de08f7b781a5b29c46451061737ced75_28.png)

Now by convention， we don't add that indentation even though it's technically correct because this is an else。

 and then there's one statement and that statement is the if okay。And so。It's。

We use this idiomaticically all the time， it looks like a multiway。If elsesif else， but it's not。

 It's actually a further and further deeply nested elsesif。An else with an if inside the else。

 and then another else with an if inside the else， we just don't indent it。

 We indent it by convention as if it were a multi way if。

You don't need to know this precisely when you are writing code。

 but I just want to point that out in case like in the back of your mind you're like。

 why is Poson called LF which is one reserved word and why does C not have an LF but instead has an Elsive？

I think when the Gio invented Python， he said， look， that's a cool convention。

 let's make it actually part of the language rather than a idiomatic use of the language。Okay。

 enough of that， enough of that。Okay， calling by value functions。 This is pretty easy， right？

 There's no def key word。 You have the return value， the name of the function and the parameters。

 and then， of course， before the curly braces， you have to have the type of the parameters。

 Those are not the type of the variables in the function。 Those are the type of the parameters。

 in Python， you don't need to tell it what type they are。

 Python is kind of a flexible typeless language， the type of a variable goes right along with it。

 any you could be inside my molten say what kind of a thing is a And then a could be an integer。

 It could be a float。 It could be whatever could be a string， right。

 because that's an object and an object can have a type， whereas a is just a number。

 and you have to tell it in C， that number that's coming in， it is an integer。

 And if someone miscas it in C。Like put 6。0 here， it just blows up， doesn't work right。I mean。

 it might do something It's just unexpected， right， So there's no cleverness。

 Now there might be some checking。 You might get a compiler warning that says。

 how come it's an integer here and it's a floating point here。 that will be dangerous。

 but it won't fix it for you， and it doesn't automatically convert it。

 whereas if you did this in Python， It would automatically convert。

 So you have a far greater responsibility to。Match your types up and see。Things like。

Return statement pretty much functions the same。 That was。

 you know the Python return statement is an im of the C return statement。

 You do have to declare your variable types that are going to be used temporary inside the function。

 Scope wise， right， this C is not outside that we will see later when we get to the functions chapter about external values and static values。

 et cetera。 But the default scoping is that any variable that you declare inside of a function only lives inside the function。

 and there is no A B or C in the main code， and that's the same as how Python works。Oh。

 that's a lot of Rosetta stone。We talked about input output， we talked about looping。

 we talked about reading a file， we've talked about strings which are really character arrays。

We've talked about float and later， later， later， later， later， we're going to learn a lot。

Chapters  five and six are the crazy chapters， but we're going to play with how would we implement some of the things？

That Python strings， lists and dictionaries handle。And before this course is over。

We're going to come back。

![](img/de08f7b781a5b29c46451061737ced75_30.png)

🎼And get inside the mind of what it would take to build Python using the C language。

 so we'll see how ac structures， pointers， etc， character race can't be used to build string object list object and di object and that to me is the learning objective of this course is not so much。

How to code C because it's your job， but what in C is necessary to make a higher level language like Python or JavaScript or Java or C sharpharp work。

And we'll get to that before the end of the course， it is a long course and again。

This was a long lecture。This takes some time to absorb。And just zooming through this。

You achieve nothing。If you just do the homework without understanding it， so take your time。

🎼I put the lines in this lecture， the lines of code are there very much on purpose。

 Every single one is trying to teach something， so hope you'll take the time to learn all this material。

Cheers。🎼。

![](img/de08f7b781a5b29c46451061737ced75_32.png)

![](img/de08f7b781a5b29c46451061737ced75_33.png)