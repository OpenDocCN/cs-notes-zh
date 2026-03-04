# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P14：-014-Lambdas Chap2 Video 9.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's take a closer look now at the syntax and semantics of anonymous functions and application。

An anonymous function expression has a keyword fun at the beginning of it， so yes。

 fun is a keyword in Ocael， I love that。After that， there are some arguments to that function。

These are the names of the parameters， as they will be known in the body of the function。

 x1 through xn。Of course， you can name these as you could name any other identifier in OMl。

Then there's a little piece of punctuation， which is the dash greater than that's meant to look like an arrow。

 the idea is that it's a transformation of the input into the output。And finally。

 the body of the anonymous function E， which itself can be any expression。

How do we evaluate functions？Nothing to do。Think of an anonymous function。

 just like an integer or a string or a Boolean。 All of those are already values。

 There's no computation to be done with them。It's the same thing for an anonymous function。

 There's no computation to do at that point。A common mistake people make is they think， well。

 maybe the body of the function would be evaluated then turns out it's not the Ocal rules of evaluation say that the body of the function is not evaluated until the time that the function is applied。

So we're done， there's no further computation to be done。 Anonymous function is already a value。

Anonymous functions go by another name out in the programming language universe。

 They're known as Lambda expressions。 The origin of the name comes from mathematics。

It actually comes from the notation Lambda x。 E This means the same thing as the anonymous function syntax that we've already seen in Ocal。

Just written a little differently， think of the lambmbda here as meaning what follows is an anonymous function。

 just like the fun keyword does in Ocael。You'll find lambmbdas all over the place。

 Here are four different examples。Python has Lambda expressions。

 you create them with the syntax Lambda， which is itself a keyword in Python。

Java has lambmbda expressions， you would have seen those last semester in 20110。

There's a very popular programming languages blog called Lambda the Ultimate。

 if you really get into programming language theory， you'll enjoy reading this。



![](img/328449b4690cc167a4bf848aa59a9fc5_1.png)

And finally， one of my favorite YouTube videos。Lambda style， performed by a professor at UCSD。



![](img/328449b4690cc167a4bf848aa59a9fc5_3.png)

![](img/328449b4690cc167a4bf848aa59a9fc5_4.png)

おぱいなナしたい。なんだスさ。🎼つい。🎼好。さきだて。はcus。いっぱい出す。🎼must the pleasure。🎼一下我们。🎼第一狗。🎼かし。どしゃた。

I mean the faithful bad book bad。が十。🎼My I not be that。🎼そう、すね。Okay。有。🎼もた全て。🎼快对对嘿。我。🎼你说的晒。

What aboutラ time。

![](img/328449b4690cc167a4bf848aa59a9fc5_6.png)

Lambda style。In summary， functions are values。Now that was a design decision that might not have been apparent at first。

 but is going to have far reaching consequences in OCll。Since functions are values。

 we can use them anywhere we would use other values。

 that means functions can take functions as arguments。And functions can return functions as results。

This is an incredibly powerful language feature， and it is one of the distinguishing features of functional programming。



![](img/328449b4690cc167a4bf848aa59a9fc5_8.png)