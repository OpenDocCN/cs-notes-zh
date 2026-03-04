# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p34 33_06_useful-datatypes -BV1bw4m1D7MM_p34-

Allright， in this section， I just want to show some more examples of data type bindings in particular because the only example I've shown you so far was just a silly example that didn't actually do anything useful。

 So I want to explore the idea of one of types and some of the common idioms that we see them used for right so these examples will be small but they'll nonetheless be indicative of the sort of things you use data types for So the simplest example is probably just for whats enums or enumerations are used for in other languages if you haven't heard of those no problem so suppose I just want to represent what suit a playing card is so in English every playing card is either a club a diamond a heart or a spade So it would be a great example to just have a data type binding I have a new type suit and then if I want to do something for each possible suit I can just have a case expression that has one branch for each pattern if you don't do this with an enumeration you end up just encoding something like oh one is for club two is for diamond。

3 is for heart。 And that sort of thing is hard to keep track of。

 You don't get as much error checking。 It's harder to read。 Data types are perfect for this。 Now。

 what's interesting is this is a very simple use of data types。

 because none of the constructors Club diamondmon Heart spade carried any data。

 There were no underlying values。 That's fine。 data types just can do more than that。

 So another example is if I wanted the rank of a playing card。

 So this is the thing that in America is called a jack， a queen。

 a king or an ace or as a number between two and 10。

 So the second data type I have here can represent that fairly well。

 you could argue that by doing none of int。 I'm not restricting that int to be between2 and 10。

 It could be negative7， it could be 142。 But this is still a pretty good concise way。

 very readable way to read the rank part of a playing card。

 You would then and we'll see how to do this in a future segment create an each of type that had a suit。

Under rank， and that would represent a card。Allright， so another common pattern。

 another common idiom that we use data types for is when we just have alternate ways of identifying some objects。

 some thing that we're representing in our program。

 so suppose I had a bunch of students in my class and mostly I wanted to represent them by some sort of student number but some of the students were say just taking a pass fail or just sitting in they were turning in the homework but they didn't have a student number。

So then what I might want is some type like called ID for student ID that was either an int。

 which I'll mark with the constructor's student nu or a name which could have a first name。

 a last name and maybe an optional middle name。 and since for each student。

 I only want one of these possibilities。 I don't want any confusion， I don't want all of this stuff。

 this is a perfectly reasonable way to represent that。So compare it， if you will。

 to trying to do that same idea with each of types。 and unfortunately。

 students often do this and we often even see code and programming languages that encourage using each of types when what you have is conceptually a one of types。

 So here's something that's really bad style。 let's do the same idea where we have a record with a student numb field。

 a first field， a middle field and a last field， but we'll say even though students ideas have all these。

 you should never use them all。 and what we'll do is we'll say the student numb is what you should use。

 but if it's minus one or some other special value， then ignore it。

And use the first middle and last field。 All right， So what don't I like about this approach。

 You're basically giving up all the benefits of using a language concept that enforces that you have a one of type。

 You're getting no help that people should only use a number or a name， not both。

 you have to read this comment to understand that you have to expect a minus- one value and react accordingly。

 it just makes it a lot less clear what it is that you're actually doing。

 And that's why in any programming language it's worth learning how one of types should be represented and then using that pattern when it's the right thing to do。

Now that said， this is a bit of a strange example because there are situations where it makes sense to use each of type to represent students。

 Suppose we just had a slightly different thing we were modeling where every person does have a name and optionally has a student number and I want to have both of those。

 Well， if you want both things， then each of is exactly the right thing。

 and you should use a record type like you see here。 the student nu should just be an int option。

 Don't use minus1。 It's too hard to remember to check for it。

 use an options with's either sum of a number or none。 That's the one of。

 And then the first middle and last name should always be present since the middle name might not be present。

 will make that an option as well。 So this is a big thing you have to do when you're designing your software is understand what kind of data you want。

 how you're gonna model those things in your program and then use the right kind of compound types to directly capture the idea of what you're doing。

Alright， so that's all good。 Now， in the rest of this segment。

 let me focus on an example of another kind of data type binding that's going to be recursive and is going to be near and dear to our hearts because it's how you represent things like programming languages themselves。

 Allright。 So here is the last data type binding。 I'm going to show you in this segment。

 It's called X for expression。 and it defines a little language， if you will。

 of arithmetic expressions。 So it says an expression is one of the following things。

 It's either a constant， which holds an int or a negation of a smaller expression， not just an int。

 but any smaller expression， an add an addition of two smaller expressions or a multiply of two smaller expressions。

 So notice how we're using selfreference here。 Many of the constructors themselves hold other xs the same way a list in its tail holds another list。

 And what we're actually doing is defining a set of trees。😊。

The set of trees that this data type binding represents are trees where at the leaves are constants with a number attached and at the internal nodes are either negate。

 which has one child， one smaller expression or add and multiply that have two smaller expressions So in ML once we have this data type binding。

 we could write an expression like you see here in the middle we could just call the ad constructor with two arguments that each themselves have type X。

 the first one could be constant， which we just need to call with anything of type int。

 like the result of the expression 10 plus 9 and then negate。

 which has to be called with one expression and another expression could be the constant four。

So that's how we would write these in ML， but what I want you to have in your head is this tree version of it to think of this expression as evaluating evaluating to this value。

 it's a tree that has add here at the root， two children。

 constant which holds a 19 and negate which itself has a child which is a constant that holds four and so every value of type X is going to look like some sort of tree that has this kind of shape。

So now we very concisely in just the four line data type binding described a set of trees that represent an interesting collection of arithmetic expressions。

 and now what we could do is we could write functions that operate over things of type X and probably the most obvious type of function to write is something that takes an X and returns the integer you get if you evaluate it right so we have a little language here let's write a function eval of type X arrow int So we're going to take any X and we're going to return the int that that arithmetic expression should evaluate to if you actually ran it。

So here's what we would do。 We would have a case expression。 We would say， well。

 any X is built with constant negate add or multiply。 What should we do in each case。Well。

 if it's built with constant， let's get the underlying int out and that's our answer Cons are that's the result。

 that's the number。But what if we have a negate， Well， then we have some smaller expression here。

 We'll bind it to E2。 So now over here in this right branch。

 we have an expression that is in the variable E2 and what we could do is recursively call eval on it。

 and that will tell us the result of evaluating E2 in this little language and then we could use M's negation operator to negate the result。

For add， let's bind to two local variables， the two subtrees， E1 and E2。

 we recursively call Eval on both of them， take those two numbers we get back and use MLs plus ML's addition to come up with a result。

And if you like that， multiply is very similar， create two variables。

 you want to E2 for the two parts， recurs we call eval and then multiply them together。

So it's perhaps not very surprising that functions over recursive data types。

 data type bindings that have selfreference like this end up being recursive。

 You want to do something useful within an X you have。

 usually you need to consider the smaller expressions that are in the subtes of that tree and the way you're going to recursively find those and figure out how they're made is with a recursive function call that then has its own case expression。



![](img/e50f09c447319a67b8cf55012022120a_1.png)

Alright， so that's most of the code I wanted to show you。

 Everything I've shown you on the slides is over here in the file。

 You'll also notice I have a second function here， number of ads。 and then I have some example code。

 So for example， here's what I had on the slide。 So example X is just a little variable binding of type X。

 and then example ants， when I call eval on example X will just be something of type in。😊。

I have one other this function number of ads is also happens to have the same type as eval x barrel int。

 but what it does is it doesn't run the expression， doesn't compute its answer。

 instead it just counts how many additions are anywhere in the expression and it's the same kind of recursive processing let'll just do a case on E if it's a constant there are no ads in it。

 if it's a negate， it has the same number of ads that are in E2 so just recursively called number of ads with E2 and that's our answer。

If it is an ad， well then there's one ad， but we need to also include any ads that are in the subexpressions。

 So let's recursively call number of ads Z1， number of adss Z2， add those together， Add one to that。

 that will be our answer。 and multiply is similar， except we don't have the one plus because the multiply itself is not an ad。

 And there's an example here of trying that out as well。

So what I want to leave you with is data types are useful for representing lots of different kinds of data。

 particularly these interesting tree like structures that we can then write recursive functions over to produce answers in terms of the answers for the subtrees。



![](img/e50f09c447319a67b8cf55012022120a_3.png)