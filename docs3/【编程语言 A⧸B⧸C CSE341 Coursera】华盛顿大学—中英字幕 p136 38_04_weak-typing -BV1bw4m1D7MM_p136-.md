# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p136 38_04_weak-typing -BV1bw4m1D7MM_p136-

In this segment I want to briefly talk about weak typing。

 which is actually a separate topic from static versus dynamic typing。

 but because it's often confused with that issue， I thought it would be good to put it here in the course and sort of set the record straight。



![](img/d895ffea4bc5645bddc632b62f63bf4d_1.png)

So weak typing， which is probably best known as the sort of type system that CNC++ have。

 is what I'll describe as follows。There exist programs that， according to the language definition。

 must pass static checking。But then when the program is run。

 they are allowed to do absolutely anything。 I like to say that they're allowed to set the computer on fire。

 by which I mean they're allowed to crash。 They're allowed to corrupt your data。

 They're allowed to be a virus。 They're allowed to delete all your files and so on。

So the idea is there are programs that perform operations that don't make any sense。

 but the dynamic checking that would catch those errors before they do anything disastrous is optional and in practice in implementations of CNC++ is not done。

Now， if you've only ever programmed in rackcet or Python or ML or Java， this would seem crazy。

 Why would you allow a language implementation not to do these checks and the answers are numerous。

 So it turns out there are good reasons to use CRC++ in some settings。

 One is that it makes the language easier to implement for all sorts of different computing platforms The checks are left to the programmer Now I would prefer to have a harder language implementation and make programming easier。

 but that's not always the tradeoff that people make。



![](img/d895ffea4bc5645bddc632b62f63bf4d_3.png)

Probably the biggest one that people emphasize is performance that if you don't have to perform dynamic checks。

 then not only do you save the time of not doing them。

 but you don't have to use space in your program to store the various tags and sizes and other things that you need in order to do the dynamic checks and that's actually related to this third reason which is just lower level that if you want a language where programmers can control things like the representation of data。

 then you can't have dynamic checks that require extra fields that the programmer doesn't have control over but that's really about CNC plus plus which is course is really not about。

 I just want to emphasize the idea of week typing and to tell you that it's not a very good name it doesn't really have to do with type systems it has to do with there being things that you're trying to prevent some bad property X and not checking for it you're not checking for it statically and you're not checking for it dynamically and。

Saying if it happens， the computer is allowed to catch fire。

So you can see it's not really about typing when you realize that one of the biggest reasons that CNC++ programs do unexplained things up to and perhaps not including setting the computer on fire is when you have a ray bounds violations。

 which are not checked， but most people don't think of a ray bounds as related to the type system in these languages。

So it turns out that decades ago people used to be fans of weak typing， some people were。

 many people were not and the people in favor of weak typing had this saying strong types for weak minds so the idea is that you would only want to have strong typing which is the opposite of weak typing if you thought the computers were smarter than humans and we know they're not。

 we know that static checking would never be perfect。

 so you always need the smart humans to have some work around who turn off the checking that they may know is unnecessary and the computer is not smart enough to realize is unnecessary that in the end languages should not get in the way of humans and humans should be able to say trust me I say this is right and if I'm wrong。

 you can do anything。And I think the conventional wisdom has really changed on this quite a bit that in reality。

 we've learned that humans are really bad at avoiding bugs and we need all the help we can get。

 and if we can write a computer program that does some of the checking for us。

 it's a nice division of responsibility， the person writing the static checker or dynamic checker can focus on getting just the checking right。

 people writing applications can focus on the logic of their applications and rely on the automatic checking that we get in strongly typed programming languages。

It's also fair to point out that conventional wisdom has changed because our type systems have just gotten a lot better。

 they're more flexible， we have things like polymorphism。

 we have things like subtyping that have made it a lot easier to program in a language with a strong type system and not feel like it's getting in your way。

The weak typing argument in my mind， really breaks down when you look at the modern size and complexity of software。

 there are operating systems today that literally contain 30 or 40 or 50 million lines of C code。

 If you're writing 200 or 1000 lines of C code。 I'm sympathetic to the argument that humans can look at that code and through hard work and staring carefully get most of or even all of the bugs out of it and maybe a type system shouldn't tell them that it knows better。

 but when you get to 30 million lines and any one line in that program could cause the entire application to perform arbitrary behavior。

 I just think it's ridiculous to expect that we don't want some assurance that certain kinds of errors and preventable properties are not possible in the software。

 I like to joke when I'm teaching this stuff that there was an important bug related to the weak typing of C announce just this week。

 and I actually don't have to look。up because there are plenty of websites to catalog these things。

 And I'm sure there's something posted on them every week。 So， you know。

 we just have too much software， too complex a software in the world today to sort of rely on humans to get their software right。



![](img/d895ffea4bc5645bddc632b62f63bf4d_5.png)

The thing I want to emphasize though is that racket is not weeklyly typed。

 This is just a matter of definitions。 Raet is dynamically typed。

 it checks a lot of things like not using a number as a procedure at runtime。

 but that is very different than not checking them。

 but we have is a language definition that says those errors will be detected at particular points in an error will be raised。

 then in the language implementation。The checks can be removed if the implementation can perform some analysis to show that they would never fail。

 So the language definition says these checks have to be in there。 If the check would ever fail。

 that has to be indicated by an exception or an error in the program。

 But you can remove checks in the implementation。 if you're sure they would never fail。

 And this is all very different than the sort of catch fire semantics we've been talking about with C and C plus plus。



![](img/d895ffea4bc5645bddc632b62f63bf4d_7.png)

And just to finish up this segment， let me talk about another topic that is not weak typing and is not dynamic typing。

 but is often confused with these things。 And that's this issue of what primitives can sorry what operations can primitives do So in some languages if you try to call plus with strings。

 you get an error that's a type error and ML it's a runtime error in racket。

 but in other languages plus just means string incatenation。

 but maybe in those languages trying to add a string and a number is an error。

 and then there are languages where it's not an error where it will convert the number two string and you'll end up with a four character string like F003。

There are other things that I'm used to being errors and some languages say are not。

 If I access the10th element of an array and that array only has five elements， I that an error。

 Well， in some languages， it says no， you'll just get something like null back。

 you'll get an empty list back or something like that， even if you assign to an array。

 What if we just made an array bigger。Suppose you had a function like in racket and you called it with the wrong number of arguments。

 that's an error in racket， but a different language can make a different choice。

 it could say if you pass too many arguments we'll just ignore the extra ones。

 maybe if you pass too few arguments we'll pass in 79 for all the arguments you were missing。

You can define your language in these ways to be more flexible and decide that fewer things are errors。

 but this is not actually static versus dynamic checking。

We sometimes think of languages that are more permissive on these things as being more dynamic。

 but technically that's not what they are。 All that's going on is that we've changed the evaluation rules for a primitive in our language。

 whether it's accessing an array， calling a function or performing an edition。

And if you change the evaluation rules for your language to allow more arguments。

 more types of things， you are being more flexible。

 you are increasing the set of legal programs at the expense oftentimes of detecting bugs in a timely fashion。

 then instead you just silently continue even if it's unlikely that that's what the programmer meant。

So some of the tradeoffs between static checking which catches bugs earlier and dynamic checking which catches them later apply here here we're being even more dynamic and being even more delayed in announcing that something seems to have gone wrong。

But it's not really static checking at all， it's not really dynamic checking。

 it's just saying that I've changed the evaluation rules of my language。



![](img/d895ffea4bc5645bddc632b62f63bf4d_9.png)