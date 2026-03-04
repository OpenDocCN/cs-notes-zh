# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p112 4_JavaScript变量与表达式.zh_en -BV1Lr421A75d_p112-

![](img/766b8216287fa00ba65b491195ac2d72_0.png)

![](img/766b8216287fa00ba65b491195ac2d72_1.png)

So one of the important parts of any programming language is the operators and the expressions。

 and so these of course are very much like all sea based languages。

 we have our plus minus multiplication is asterisk diionist slash division unlike Python 2 is creates floating point based on just like you might expect from a calculator so if you take 9 divided by 2 you get 4。

5 modulo， which is an integer division that gives you back the remainder。

And then there are these side effect operators like K plus plus。

 which is the same as K equals k plus 1 so there's a minus minus and you can have these plus pluses or minus minuses either in the back or in the front。

You can also have side effect operators like J plus equals 5， which is the same as J equals J plus 5。

Again， these are contractions that we tend to avoid unless we have a reason to kind of make our syntax really dense。

The comparison operators are very much like PhP and the C language。

 So we have the big thing to remember is that there's assignment statement that's the equal sign and double equals is the question mark。

 So asking the question is J equal to 10 is double equal sign and then。

From that not equals flows less than less than greater than less than or equals all are kind of straightforward。

 And there's two kinds of equality operators。 One is the double equals。

 which is effectively numeric equivalence or equivalence after type conversion。

 and then the triple equals is comparison without type conversion。 So if I put false into J。

And we had the same thing in PhP false into J。 And I'd say is false， numerically equal to 0。

 And the answer is yes， is false， identical to 0。 And the answer is no， it is not。Okay and is false。

 identical to false。 Yes， it is。 And there is also a not triple equals。 And again。

 these are very PhP like。 and I like， it's funny。 I like these。

Hows probably going to do some programming in Java， the big language。

 Java and I didn't have these and I'm like， oh if it's false。

 but in Java the equality is different because you don't do auto type conversion and so in languages like PhP and JavaScript that do automatic type conversion。

 you have to have an equality test that stops the automatic type conversion because this implies an automatic type conversion in the language like Java that's a type strict type language。

 you can't have two types， you can't check the equality of two different types because it's just a syntax error。

In JavaScript， we have numerical quality and absolute quality， which is type and value。

The logical operators are again straight from the C language。

 double and is logical and so both sides must be true， true and true becomes true。

 or meaning either side， you know， true or false becomes true because only either side has to be true。

 greater than greater than not in logical expressions are exclamation point。

 like in all C languages in this， if we're looking at that， that would be exactly as it is in C。

And if we're looking at all of these things， they would be exactly the same as in the C language and the Java language except these things are they're used in C like languages that don't have strict typing。



![](img/766b8216287fa00ba65b491195ac2d72_3.png)

A concatetnation。I have PhP。 I love the doc concatenation operator。

 but I accept the fact that it will never be in any other language except PhP。

 We use plus to do concatenation and of course it does string conversions automatically。

 it's not like Python where you've got to get the types exactly right。 The plus simply says， oh。

 I got a string in a number， let's turn that number into a string so I concatennate it together。

 And so X becomes the string 12。 and so we concatenate hello space 12 space people。

 And like all languages， this doesn't add a space and so these two spaces are I've explicitly put into the string so that they actually work。

Javascript is a loosely typed language there's a video that perhaps I'll put a reference elsewhere to that's kind of funny about how adding things together。

 different types it's all very consistent but it's not something that a beginner would predict and so in this case let's just take a look at some silly things 123 plus 10。

Well， is is that a numeric。 Well， in P P， that would be deterministic because it plus is a numeric operator。

 but plus is not a numeric operator。 It might be concatenation， and it might be numeric。

 In this case， it sees it as concatenation。 And so we get a string 1，2，3，1，0。But multiplication。

Is a numeric operator， So string 123 times 1。Is the number 1，23， and then you add 10 to it。

 and that's 133。And this is different than PP。 The string Fred multiplied by one。 that's in numeric。

 no numeric operation。 And instead of pretending that Fred is 0 like PhP would do because PP is very loosely typed。

 JavaScriptscript has this notion of not a number。 And so when it looks at Fred and tries to convert Fred into a number。

 it goes， that's not a number。 And then not a number times one is not a number。And if you take X。

 which then ends up being not a number and then add one to it。

 not a number plus one is still not a number。 So not naan is kind of a sticky thing。

 And it's just kind of fun to look in some U I。😊，And blah， blah， blah blah， blah Nan。

 And it's always， you know， uppercase N， lowercase N。 And you're like， oh， they did some conversion。

 They did some calculation in jascript and it didn't work out so well。

 And so you see Nan in all kinds of user interfaces。

 And you know that they're doing math in jascript。 And they got some kind of a bad value divided by zero or took an undefined thing and multiplied it by something else。

 And then they printed it out in the document object model。 And it came out as a naan。

 that's kind of a running joke of ja。 I that Nans。So Nan， like I said， is sticky。

 you can check to see if a variable is a NN like is Nan is a function that returns to or false。

 dividing by zero gives you infinity。And these are actually so JavaScript seems weird in this case。

 but in a way JavaScript is sort of more right， so dividing by zero shouldn't be you know an error just infinity。

 so that's what it is mathematically and there's situations that are mathematically not a number and so there is kind of an underlying official standard for how numbers are supposed to function and JavaScript is probably closer to those than other languages like PhP。

 so even though we make fun of Nan all the time， it's probably a more responsible numeric implementation than some other systems might have。

There is a type of operator that can tell you whether something is a string or an integer or whatever。

 and it returns itself a string， which means that you can put that in if statement。

 you can say if type of variable is equal equal quote string quote and it will tell you something and that's a common thing that we do functions are an important part of any programming language。

 there's lots about JavaScriptscript functions that are exactly as you might expect there's a function。

 this again very C like function， name of function， arguments to the function。

 the arguments by default are passed by value， not pass by reference。

 and then you can have a return value， and that all sort of works the exact way that you would expect in any other programming language。

So that part's pretty straightforward。But the weird part。Someday I would like to know why。

 But the weird part is one of the things that I always talk about when I talk about functions is how they are like isolated by default from the outside world。

 The only thing that we touch are the parameters that go in and the return value that comes out。

And the stuff that goes on in the function generally does not sort of bleed out into the outside world。

By default。Not true in JavaScript， super not true in JavaScriptscript， Fishly not true in JavaScript。

So in jascript， if there is a variable， you're coming down and this is done in sequence so that the fact that this G L is before the function actually matters because it's sort of evaluating this in order。

 and it looks at this thing and it says， oh。You didn't tell me that this was local。

 and there is a variable that's global。 so I'll just make these two things the same。So at this point。

 we have GL out here。It ends up with 123， and then this code runs， and it's the same GL。

 And so that changes this to 456。 And so when we run the check function， it changes to 456。

 and then we print it out and out comes 456。 I think that's like a。

Not a very good feature by default， but。It is， and we can't change it。B。

So one of the things you see in JavaScript， all responsible JavaScript programmers is use Var V var var var。

Like， don't forget to use the var。 So what vr says is。

effectivelyff draws what I wish was default to say this is a local variable。

 even though there is a variable globally of the same name。

 this G L does not sort of smear out or percolate out beyond its boundaries somehow。

 And so in this case， there are two G Ls。 There is a。A GL in here。And a G all out here。

This one gets 123 in it。The code runs。 This one gets 456 in it， Then the code comes back。

 and then the global one is unchanged。 And so that's really the way you want it。

 So you think to yourself， why do I have to keep doing this。 You've got to put varr in。



![](img/766b8216287fa00ba65b491195ac2d72_5.png)

I have written a lot of jascript where the mistake was， I'm like， why isn't this working， Well。

 that's because I did didn't have the var。 I'm like put the var in。 So just get used to it。

 It's a little weird。 You have to explicitly mark function variables within functions as if they are local。

 you have to you have to explicitly say it。 It's not like any other， well。

 at least most other commonly used programming languages don't do that。

So up next we'll talk about arrays， arrays and objects are always sort of the fun part of any programming language。

