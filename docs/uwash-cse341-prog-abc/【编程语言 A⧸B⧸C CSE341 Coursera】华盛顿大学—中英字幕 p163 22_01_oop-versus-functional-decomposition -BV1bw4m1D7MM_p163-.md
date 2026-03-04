# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p163 22_01_oop-versus-functional-decomposition -BV1bw4m1D7MM_p163-

As we approach the end of the course， we still have plenty of new things to learn。

 but we'll find ourselves more and more learning them in the context of comparing and contrasting what we already know and the beginning of this section of the course is no exception。

 in fact， it's one of the great punchline of the course and we're going to start by considering how object oriented programming and functional programming。

 decompose programs into more manageable pieces。So when we were programming in functional languages。

 what we generally did was we took a program and we broke into smaller functions。

 each function performed some operation over its arguments。In object oriented programming。

 we find ourselves breaking a program down into classes and all the methods of a particular class perform operations over one kind of data。

 the kind of data that that class represents and so what we're going to do over the next few segments is understand that these two approaches are so exactly opposite that they're actually just complementary perspectives。

 ways of viewing the same matrix of operations and I'll show you that matrix in just a second so which perspective which view is better is largely frankly a matter of personal taste but as we'll see in the next segment it does it is more than taste。

 if you think that your software might be extended in particular ways。

 and then after that will' get into the issue that object oriented programming struggles quite a bit more on certain operations that take multiple arguments of different varieties and we'll get there when we get there so that's our roadmap and let's just jump in。

And to this matrix， by understanding the canonical example people use when explaining this issue。

So suppose we have expressions for a small programming language。

 exactly the kind of language we considered when we learned how to write interpreters earlier in the course。

 Well， it turns out that you really have two things， you have different variants of expressions。

 different constructors， so maybe you have integer constants， you have addition expressions。

 you have negation expressions and so on。 Those are different kinds of data。

You also have different operations， the operation we've focused on is Eval， evaluate an expression。

 but you could have other operations， you could have two string that converts an expression to a string。

 you could have has zero that just runs over an arithmetic expression and returns true if there's a constant zero somewhere in that expression。

 syntactically not evaluating it， just looking for a zero。

 you could have any number of other operations。So if you think of this in terms of variances in operations。

 you essentially have a matrix which is just a twodimenional grid where as I've shown it here。

 you have one row for each kind of data and one column for each operation and I would argue that no matter what programming language you are using to implement this software。

 you have to decide the correct behavior for every square in the grid。

 how do you convert an integer to a string， how do you evaluate an addition expression。

 how do you evaluate a has zero and so on。So you have to fill out the grid and different programming styles just encourage you to fill out that grid in different ways。

So let's do the functional or procedural decomposition first when we're writing in a language like ML or racket。

 well， let's think about ML， we can define a data type with one constructor for each variant。

 Our data type is saying what the rows of the grid are。

Then in our functional decomposition we have one function for each column of the grid。

 We have an eval function， a two stringing function， and it has zero function。

 and then in those functions we use case expressions to have one branch for each row for each square in this column that's how we decompose our program if multiple of your squares can be implemented the same way。

 then you can use wild card patterns or something like that。

 but fundamentally you're decomposing it in terms of for each operation which is a function what are the various branches。

 So let me make this very concrete because we're going to build on this an upcoming segments here is the ML code that does exactly that。

 Heres our data type expression that says what the rows of our table are and then we have one function for each operation So here's the eval function takes it an expression E it's an integer just returns the expression if it's a negate it recursively evaluates make sure it gets an int out and it negates it otherwise it raises an exception and。



![](img/0280919010287aa253d9be2bd6a04b6f_1.png)

I have one more case for that last row of the Eval column， which is to in addition。

 recursively evaluate E1 E2， and because of where this is going in future segments。

 I'm using a helper function here， add values， which is right up here， helper functions are fine。

 and all this does is make sure that both values are integers。

 in which case it returns a new integer that adds them together， otherwise it raises an exception。

That is only one column of my grid。The next column two string is right here。

 and I have one case for each branch， so an int I just call the int dot2 string function in ML for negate。

 I have some recursion here for add， I have two recursive calls and so on。

 and then a column for the has zero function that again has one branch for each row of the table。



![](img/0280919010287aa253d9be2bd6a04b6f_3.png)

So those are my three columns， that is functional programming。Now let's look at OOP。In OOP。

 the way we would approach this in OOP style is we would define a class。

That describes the idea of expression。 Now you don't actually have to do this in rubby because it's a dynamically typed language。

 but I'm going to present it that way and think of int add and negate as all subclass of that superclass。

 you could just define int add and negate as classes that weren't subclasses of anything other than object。

 But let's think of it as having a class X within subclasses int add and a gate。

 So then what we do is to fill out our table we have one class for each row。 we have the int class。

 the add class and then thegate class。 and then we fill in the entries of that row by int having an eval method。

 a two stringing method that has zero method， add having the same three methods。

 negate having the same three methods and those methods say this is how a negation converts itself to a string。

 So we are essentially filling out the exact same table organizing our code into rows instead of into columns。

😊。

![](img/0280919010287aa253d9be2bd6a04b6f_5.png)

As you might imagine， I've done exactly that over here in the Ruby file。So again。

 I have this class X which I don't really need in Ruby， in fact。

 I'm even going to have a separate superclass for values in my language which currently are only int expressions。

 this is similar to the sort of thing you'll do on your homework which is why I have it。

 but it is overkill in this example。So now I have one class for each row。 So here's my int class。

 And if I look further down， here's my negate class。 If I look further down， here is my add class。

Now inside of each of these classes， I fill out the row right so I have a little bit of stuff for how to initialize an integer which has you know one instance variable for the underlying in itself。

 but then I do have a method for eval， a method for two stringing and a method for has zero。

 so evaling an integer。Just returns the object itself。

 This is the same thing as in functional programming in the branch of eval where an ant evaluates to the entire int。

 This object， when you call eval on it， returns self， returns the entire object for two string。

 Let's just call the two S method on the underlying instance variable that holds the number And for has0。

 let's see if I equals 0。 These three。Entries in our table are exactly。The int case of Eval。

The int case of two string and the in case of has 0。

 We've just put them next to each other so we can see all the operations on int in one place。

Niggate is similar。For Eval， we have recursively call Eval on this。

E this I'm actually calling the getter method here。

 I could have just as well just directly done the instance variable。

 That's a matter of dynamic dispatch as we've seen。 So take the subexpression， call its eval method。

 then assume it is an int， which you can kind of see because I'm saying dot I here this is the sort of thing that an ML being statically typed。

 I had to have a branch here with an exception， but that's an orthogonal issue。

 that's really static versus dynamic typing。And then that will give me some number and create a new integer。

 and that is how you eval in a gate， which is exactly this case of EVval in the functional code and similar I have a method for converting a negate to a string and deciding if a ne gate has a zero in it。

 which is just recursively seeing if the underlying expression has a zero in it。And finally。

 add works exactly the same way。 I have a constructor here that initializes two instance variables to hold the subexpressions。

 I do a PRC， I have getters for both of those。 so now I have an eval method that recursively evals E1 by sending it the eval message recursively evaluates E2 by sending it the eval message and putting it together。

Same thing here where I'm just assuming the result is an int， so I'm calling the dot I method。

 you can't do that aesthetically typed language works fine here and return a new integer。

 and this is exactly the addition case of evalal from our ML code Similarlyly I have a two string method and it has zero method So that's the ruby code。

 I want you to understand you'll do something similar on your homework optionally I do also have the Java version and here because we're an aesthetic statically typed language your super class X does need to indicate what methods every X has but then it's really the same thing。

 I have an int class with three methods eval 2 stringing and has zero and a gate class with those methods and an add class with those methods and you can look at this code if you're interested in the Java。



![](img/0280919010287aa253d9be2bd6a04b6f_7.png)

So to me this is a huge punchline of the course and something you can only appreciate after you've studied functional programming and object oriented programming in a precise and conceptual programming languages way。

 which is that FP and OOP are often doing the same thing in the exact opposite way it's a question of whether you want to organize your program by rows or by columns and if I put it that way。

 I think it's reasonable to say that it can be a matter of personal taste and that it's a matter of perspective which is most natural to me if you're writing an interpreter for a programming language。

 the functional programming decomposition is just more natural。

 it's the way I think about it I'm evaluating an expression and I have separate cases for the different kinds of expressions if I'm writing a graphical user interface。

 I generally find the object oriented programming approach different。

 I have lots of different things on my screen for each kind of graphical element。

 how does it respond to。Mouse clicks， What color does it have。

 What happens if I drag it with the mouse。 These are questions I'd like to keep everything about that graphical object together。

 And I find the OOP decomposition more natural。And finally I would say that from this perspective。

 we're really talking about a matter of code layout and there's no perfect way to lay out your code in a large program because software has so much structure。

 there's so many connections between different parts of your program。

 but the way we write software in these programming languages is that we have rows and columns and files and there's just only so many ways we can lay out the code and that's why modern development environments provide lots of features for viewing the code in different ways。

 and in fact one way you can look at modern IDEs is maybe you're writing in an OOP language but if you say why I know my code is laid out in terms of rows but please find me all that has zero methods for all the subclasses of X。

 you're essentially asking the IDE to find for you the column even though your code is laid out in terms of rows。

 you could imagine an IDE for a functional programming language doing the exact opposite thing。

Programming these sort of things like our expression language。

 is fundamentally about filling out a two dimensional grid。

 and we have two programming styles that do it in the exact opposite way。



![](img/0280919010287aa253d9be2bd6a04b6f_9.png)