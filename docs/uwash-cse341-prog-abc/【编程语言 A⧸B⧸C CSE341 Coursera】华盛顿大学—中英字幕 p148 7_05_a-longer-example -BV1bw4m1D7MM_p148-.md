# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p148 7_05_a-longer-example -BV1bw4m1D7MM_p148-

In this segment， I want to show you a larger example。

 both to put together a lot of what we've already seen in Ruby。

 as well as to show a few additional features just as we go along。

So what I've chosen to do is define a small class called Myrational that is actually a lot like the rational modules for fractions that we saw back when we studied the module system in ML I'm calling the class myrational because it turns out that the current version of Ruby has wonderful built-in support for fractions that actually already uses a class called rational but we're going to build our own for purpose of an example and as I mentioned we're going to see a number of new features as we go along just to show you that Ruby is a large language and that I can't show you all the different kinds of useful expressions there are and to encourage you to learn more on your own if you're interested before I just get into the code and show you what I have let me remind you a little bit about how the rationals we studied in ML work because this is a very similar piece of code that lets you see the same thing in a different programming style so we will have numerators and denominators our little library our class is always going to keep things in reduced form。

3 over2， not9 over 6， and it will always make sure the denominator is positive。

 The numerator may be positive or negative， and then we'll have methods what we used to have functions for to add together to rationals and for converting a rational to a string。

 So without further ado， let's just go over to the code and look at what I have。



![](img/593ab1cab571251d1edc1d2f13ece772_1.png)

So I have a class my rational。 So instances of this class will represent fractions。

 I have an initialization method here。 It takes an enummerator， and then this is kind of cute。

 I'll let the denominator be optional so that you can have a default of one so that if you just pass one argument to my rational dot new then presumably you want a whole number。

 Now I do need some logic in here。 the denominator is0， that's an error。

 I don't allow zero denominators in my fractions。 So Ruby has a raised primitive that takes a string and that does something like exceptions and errors that we've seen in other languages。

 Here's an Els if， so nested if then El's notice the somewhat unusual and certainly non-english spelling of else here。

 and then if the denominator is less than0 then I'm going to have two。

Statements here to expressions where I initialize two instance variables。

 num and den to be negative numerator and negative denominator right here。

 these are you know the local variables that were the parameters to initialize Lsi initialize them this way。

 you can put semicolonons in， but they are optional when they're on separate lines。

 And then the last thing I need to do to start the invariants that I have for how I represent fractions is call self dot reduce。

 it's a zero argument method so I can put the parentheses And if I want， but they are optional。

 And because it turns out it's a private method， I'll show it to you down below。

 you can't write self dot， you have to just write reduce。So that's initialized。Now。

 once I have a fraction， we need to be able to convert it to a string。

 and in typical objectoriented style， it has a method to string， if you will。

 that we call on a fraction and we get back a string。

 So fractions know how to convert themselves to strings in sort of OOP terminology。 And in Ruby。

 it's conventional to have such methods we called two underscore S。 Many。

 many classes have this method defined。 and it's the standard way so that anything that knows how to convert itself to a string should implement this method。

 Now there are many ways we could implement this。 I'm actually going to show you few of them。

 but here's a good first way。 So to S here。 starts by taking whatever is in the numerator instance variable andm calling its2 S。

 It turns out that numbers have a two S method and this will get us the string representation of the numerator。

Then if the denominator is not one， then let's concatenate so we can use plus on strings to concatenate to the right。

 a slash character and then continue to concatenate the denominator converted to a string。

 If the denominator is one， then we'll just not do any of this。

 and when we're all done with that we'll return ants， which will be a string， which is what we want。

So this works fine。 Let me show you two other ways just to show you some other ruby features that are perhaps a little bit of overkill here。

 Here's a second version to way of converting it to a string。

 Let's just create a little local variable。 I， the empty string。😊。

Then let's add to that string via concatenation。 Let's change it to slash concatenated with2 S of the denominator。

 But only if the denominator is -1。 Now， this is somewhat strange。

 If you haven't seen this in scripting languages， it's fairly popular in these languages。

 It's just a different kind of conditional that's written E1， if E2。And it reads somewhat backwards。

 This says if E2 is true， then do E1。 So some people find this easier to read when it's sort of a one liner。

 It's a convenient way to just write something on one line that says， well， do this action。

But only if the denominator is not one。 So there you go。 In any case。

 whatever dens is after this line， we need to concatenate on the front。

 converting the numerator to a string。 And then since this is the last expression in our method。

 that's what will be returned。 And that's exactly what we want。One more version of two string。

 this uses things like rackcs quasi quote and unquote。

 which I explained in an optional segment at the end of that unit。

 basically I'm just going to return a string， but inside of double quotes。

Whenever you have hash and then brace up to the matching brace， what that does is evaluate。

This expression in here and then convert it to a string。

And so it turns out that another way to do this is to convert the numerator to a string。

 this will implicitly call its2 S method， I believe， followed by this conditional。

 which is if the denominator equals one， then nothing else slash concatenated on if you're interested in this。

 it's generally called interpolation expression interpolation in Ruby and you can learn more of it on your own we won't have much need for it。

 So that's converting to strings， now let's do something more interesting。

 let's write a version of add。 I'm calling it add bang because it's actually going to mutate the object itself。

 this is somewhat common convention in Ruby。 So what I'm going to do is take in another rational and update myself。

 whatever object I call add bang on， will have its numerator and denominator replaced by adding to it the numerator and the denominator in R。

So what I need to do is get R's numerator and denominator。 Now。

 this is perhaps the most interesting part， because I cannot say something like R dot atum。

 because instance variables of R are private to R。 That is a different object。 I can't do that。

 So R is going to have to provide some methods for me to get to numerator and denominator。

 So those R defined below on my rational。 And I've made them protected。

Because they're protected this code， which is part of the same class。

 even though they're not the same object， will be able to access them。

 even though they are not fully public methods so fine a equals r dot num B equals R dot1。

 I could then let C and D be my numerator and denominator。

 then a little bit of arithmetic to update V mutation nuome to be a times d plus B times C den to be B times D call reduced because that fraction might not be reduced。

 and then I find it convenient to return the object itself。

 I showed you an earlier example where that turns out to be convenient and I'll show you a use of this sort of method where that's convenient in just a minute。

So that's an imperative addition。 If we wanted a functional addition。

 we could do that using our imperative edition。 So here's how that might work。

 How about I define a method called plus this will actually be quite nice。

 So I'll be able to do calls like R1 dot plus R2。 but it turns out that in Ruby plus the regular plus is just syntactic sugar for calling the plus method on the left argument with the right argument。

 So by calling this method plus I will actually be able to just use the addition operator on my rationals。

 and that's kind of syntactically cute as well， So here's how I will do this。

What I will do is I will make a local variable ants that's a new rational that holds this object same values as numerator and denominator。

 So this is just making a copy， if you will， where I'm just passing to the new thing。

 the my numerator and my denominator and the initialized method above will do the correct thing for that new rational Now given that new rational。

 let's go ahead and imperatively add to it R and then just return that new rational。

 So plus always returns a new fraction， it never updates this object' numerator and denominator field。

Okay， so we've seen most of it here。 Here is our protected getter methods for numerator and denominator。

 The comment here points out that we could have used the shorter syntax of doing something like adder reader。

 but I find these a little easier to read。 So fine。 And then I just haven't shown you reduce yet。

 So here is reduce。 It's just the same logic we had before。

 It causes helper function GCD for greatest common divisor。

 It passes the absolute value of the numerator and numbers all have this method a defined on them。

 so that works fine。 And then GCD， which is right here。 we've seen a few times in the course。

 Recursion works just fine in Ruby。 So this GCD method is just calling itself。

 This is a self dot GCD， but you can't write the self because it's private on itself to do the right calculation to compute the greatest common divisor of an X and a Y。

So that is our class Now let me just show you a little top level method here when you define a method outside of an explicit class it just gets put in the object class and this method just creates and uses some rationals so what does it do。

 it creates a rational3 over4 puts it in the R1 local variable then notice the use of plus here this is actually going to call the plus method that we defined so another way to write this would have been R1 dot plus with R1 and then on the result of that。

😡，Dot plus， and then my rational of -5 over 2， as you see there。 And then I just have some printing。

 So put S R to to S。 So put S just print out its argument。 So when I convert this to a string。

 hopefully I will get， I think，-1， because I'll have three fourths plus three fourth，-5 hs。

Then I do some imperative update on R2 where I add to it imperatively R1 and then take that result so it turns out this returns the same object that R2 refers to。

 adds to it imperatively again minus one fourth and then I try out all my different printing methods on that result and so sure enough if I just come over here quickly。

 if I load example do RB I just get true back just says I successfully loaded because use rationals is a method and I haven't called that method yet。

 and if I call it， I will see the appropriately print printed out thing。

 this is the first print where I was just printing。

 I think it was R yes R2 here which is minus1 but then after I imperatively update it once with R1 which is three fourth and then again with a minus one fourth that's going to have the overall effect of adding a half to it so all my other printing shows three different ways of printing out minus。

1 over two， and that's our larger example showing a number of new features of Ruby and also an object oriented programming style where my rational objects were things with methods that knew how to perform the appropriate computation on the fraction。



![](img/593ab1cab571251d1edc1d2f13ece772_3.png)