# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p13 5_02_01_第3章控制流的历史背景.zh_en -BV1v2421P7pt_p13-

![](img/dc6a305efd12f6f7ff25dd384229cd3a_0.png)

Hello， welcome Chapter 3， I'm Charles Severance and I'm your instructor。 So here in chapter 3 again。

 I'm just， I want you to read the book， I'm just going to call your attention to a few of the unique things that might help you make more sense of the book。

So we're going to talk about semicolon use， how it' started in C and is used across multiple languages。

 how else ifF is a little different across languages。The switch statement， a bit of motivation。

 when the switch statement is even in C， the comm comma， I don't know， operator separator。

 and then sort of this tendency towards excessive succinctness or brevity that is pretty common in C programming right it just it's like there's such a value in making things really。

 really short and that makes it kind of different。

![](img/dc6a305efd12f6f7ff25dd384229cd3a_2.png)

So I love semicolon based languages and we have a whole bunch of semicolon based languages that we've learned and are going to learn certainly 1978。

 the C programming language with its non non-stactically important spacing， the key to C is that C。

 the semicolon is a terminator and every statement must be terminated by a semicolon。

 so we see x equals x plus1 semicolon and x equals x divided by two semicolon right and that's the idea the print f ends in a semicolon。

So you may or may not know in Python， you're allowed to have semicolonons。

 They're pretty much optional， like on the print open print X closed print。

 that semicolon does not need to be there， but it is a separator， not a terminator。

 So you can see the print open print X close print semicolon as。

One statement followed by a separator， followed by an empty statement， which does nothing。

 But the interesting thing is you can put more than one line on one line。

 you can put more than one line of code by put using a separator。

 So there I say x equals x plus1 semico and x equals x over two semicon。 I don't have to indent that。

 I just it's， two lines in the same block of code。 And that's legal。

 Most of the time people choose not to use semico。 the other thing about that is that。

Shell scripting， which is sort of the Linux automation treats it as a separator。

 and so that sort of looks a bit like shell scripting to have multiple statements on the same line separated by semies。

In Java， it tends to follow the C pattern where it's a terminator， I tend to like it as a terminator。

 I don't like the idea that you can leave it off the way JavaScript does。

 and so you see it's on two assignment statements and the system out printlin in Java。In PhP。

 PhP follows C very closely and so it is。It is a terminator there as well and so I think that's natural and the good news if it's a separator like in JavaScript in the next example where it's separating it。

 and so in this case the x equals X divided by2 does not need to be terminated because the closed curly brace is going terminate that and and like even the console。

 log openPend closeP semicolon that semicolon is optional when I tend to write JavaScriptscript。

 I tend to put semicolonons everywhere when I tend to write Python I put semicolonons nowhere and then in PhPC and Java I tend to you know put semicolonons everywhere。



![](img/dc6a305efd12f6f7ff25dd384229cd3a_4.png)

Even though sometimes there are things you can leave out。Another thing that is very。

 very subtle is the notion of else if。So C predates Python and C in this book shows else if as two separate words and there's an else keyword and an if keyword。

 and so you say else space if， and then you have the expression and another statement， else space。

 if expression and another statement and then else for the one when none of those expressions are true。



![](img/dc6a305efd12f6f7ff25dd384229cd3a_6.png)

And if you look at Python， it looks almost identical， it says if expression， then L if。Expression。

 LF expression and L。

![](img/dc6a305efd12f6f7ff25dd384229cd3a_8.png)

The key is that LF is a separate language construct in Python。

 and I think it's actually really beautiful and elegant。And the key is。

 is that this else if while it is， I can think of it in C as like indented incorrectly。



![](img/dc6a305efd12f6f7ff25dd384229cd3a_10.png)

So you can look at it as the very first if has an if and an else。

And everything from the second if on down is really part of that else so if you look。To the right。

 you see the curly braces with the indentation that's explicit。 It's exactly the same thing。

 But what you're going to see is you can see that its if you are going to truly correctly indent an if Elsif。

 Els if else in C， you would indent it the way it's shown on the right side。

 and it's neither here and nor there very， very， it is very rare that you would see any C programmer。

 you know， do all the indentation， the technically right way。

 But I just want to call your attention to it that it's different than LF。

 LF is its own language element that is not a deeper nesting， deeper and deeper nesting。

 If you were to nest it， you see on the right hand side。 you see。

 I've got three curle closed curly braces， curly brace curly brace curly brace and it's just so the LF。

 I think is a really elegant addition that Python has added。



![](img/dc6a305efd12f6f7ff25dd384229cd3a_12.png)

Thus， which statement？唉。I think that the reason that the authors put the switch statement in C is there was a time where we would write code in assembly language using what we call a jump table where we take sort of the take a number。

 maybe take it。

![](img/dc6a305efd12f6f7ff25dd384229cd3a_14.png)

askkets， so it's only from zero through 16 and then look up a series of addresses and jump through a jump table and the compute go to was the way in Fortrann of expressing a jump table but in Fortran it was just a mess you you got these labels and columns on through six and the con statement doesn't work like the continu and and C like languages and you had to have these go tos to get out of the switch statement。

If you think about it from an assembly language perspective。

 it's not that hard to build the compute go to with a little tiny jump table and so I think to some degree whether or not we have to use a jump table in modern C is really it's really。

 really rare where you have to use a jump table， we just would do a few repeating Elsifs and it's just fine back then a few extra statements might bothered something if you' were going to do it a times a million times a minute or something。

The switch statement is much prettier You do have to put the brake statements in there。

 You can kind of nest you have the stack cases。 and then there's a default case。

 So if at least I compare the C switch statement with the forran computed go too。

 I want to say that the C switch statement was pretty much a lot more elegant。

 a lot easier to use a lot easier to understand。 And because of language programmers of the time did think in terms of jump tables。

 If a high level language didn't have a way to express a jump table in that language。

 then we would kind of think of it as missing。

![](img/dc6a305efd12f6f7ff25dd384229cd3a_16.png)

But frankly， in your programming， I'm not sure I've written a switch statement in because Java has a switch statement to who I probably haven't written a switch statement。

Over 20 years and maybe more。I like the fact that it improved on Forran。

 but that doesn't mean that you should use it。

![](img/dc6a305efd12f6f7ff25dd384229cd3a_18.png)

The comma operator or comma separator，s I like to think of it as like a light version of the semicolon。

And most people almost never use it and the only place we use it is when it is sort of idiomatic where in a force statement。

 because we're already using semicolon to separate the start before the。

 the loop test and then the loop。

![](img/dc6a305efd12f6f7ff25dd384229cd3a_20.png)

Increment per iteration。 We're using semilon for that。 So if we want to do like two statements。

We are going to like， oh I equals0 J equals Stlin S minus1 with a comma in between to say do these two things before the loop starts。

 And then at the end， you say I plus plus comma j minus minus that is do these two things at the end of each loop。

 So I only see it in idiomatic situations。 Just think of it as like we couldn't use a semicle in here。

 it functions exactly like a semicle and although the syntax already has a semi in it。

 So I think it's actually a pretty clever way to say I want to put two statements in here and you maybe you could put curly braces in there or something。

 but I thought the comma was a pretty cool thing。

![](img/dc6a305efd12f6f7ff25dd384229cd3a_22.png)

![](img/dc6a305efd12f6f7ff25dd384229cd3a_23.png)

Another problem is that there was just this notion that we as assembly language programmers。

We could do things like be smart and leave some value in a register and then check the register a couple of different ways。

 and that would lead to really succinct fast code， hand to code where you might have to look at it to figure out what it's doing。

 but then you realize， well I did that in six statements rather than 12 statements。

12 statements might have made more sense， but the six statements were really fast。

And in the early days in the early 70s， they were changing their compilers so fast and changing their hardware so fast that they really didn't build super great optimizing compilers so they would look at the source code well that came out of the compiler and like I could do better than that so there was a lot of a kind of comparison of the source code。

Between the what the C compiler would generate and whatever。

 And so they found over time that if they would kind of use these tricks that like。



![](img/dc6a305efd12f6f7ff25dd384229cd3a_25.png)

Told the compiler to like take this C equals get cha and leave the C in a register and compare it。

To double to a space and then compare it again to a new line and compare it again to a tab。

 we would think， oh， I can see how that would run in assembly language and I can hope that the compiler would generate the assembly language that。

Compilr would generate a similar language that would make me happy。

 And then another pattern you see in this is the number four thing where all the work's been done in the loop test。

 Thiss a why loop that whole big expression is just the test to know when it's done。

 but it's actually reading the data， comparing it three times， storing it in a variable。



![](img/dc6a305efd12f6f7ff25dd384229cd3a_27.png)

And when that's all done， there's nothing to do in the loop。

 And so that's why you say close paren semicolon。 And you'll see a lot of those things。

 especially when doing string stuff where you're sort of zooming through an array and you did it all in the forlo and you don't really have anything to do in the forlo。

 And again。

![](img/dc6a305efd12f6f7ff25dd384229cd3a_29.png)

We're thinking in early days of how this is going to translate into assembly language and so you're trying to make that loop really。

 really small and again。It's amazing how often they looked at the resulting assembly language in a non optimizing compiler situation and then wondered if the compiler could have done better。

So that gets us going in this chapter， we talked about the semicolon we talked about the switch statement。

 the else if subtle syntax difference between Python and C。

 the comma and just get used to the notion that it's obtuse code please don't write obtuse code these days the optimizers are so great and so don't write Optuse code but don't be too upset as you read the textbook and see Optuse code。



![](img/dc6a305efd12f6f7ff25dd384229cd3a_31.png)