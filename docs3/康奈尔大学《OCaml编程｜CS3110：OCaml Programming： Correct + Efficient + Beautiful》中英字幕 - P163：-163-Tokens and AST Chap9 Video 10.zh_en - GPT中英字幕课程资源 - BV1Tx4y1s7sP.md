# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P163：-163-Tokens and AST Chap9 Video 10.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/f8e4ddf052c78187c6a162e3725f1940_0.png)

Now that we've seen a kind of whirlwind tour of implementing an interpreter。

 let's go back and look at some of the pieces of it in more detail。😡。



![](img/f8e4ddf052c78187c6a162e3725f1940_2.png)

The thing that was in common throughout all of it， the Lexer， the parser。

 the evaluation of it was that there was a data structure called the abstract syntax tree。



![](img/f8e4ddf052c78187c6a162e3725f1940_4.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_5.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_6.png)

That core piece， that definition of the types for representing syntax the language was really shared amongst all those modules。

 so that's why I had it factored out into its own separate file。😡。



![](img/f8e4ddf052c78187c6a162e3725f1940_8.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_9.png)

And for our tiny little calculator language， we had binary operators which were at or molt and expressions which were either just integer constants or binary operators。



![](img/f8e4ddf052c78187c6a162e3725f1940_11.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_12.png)

Of course， to represent a bigger language， you're going to need more kinds of expressions。

 maybe more kinds of binary operators， and so forth。



![](img/f8e4ddf052c78187c6a162e3725f1940_14.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_15.png)

The Leer， the parser and the abstract syntaxt tree are all highly coupled together and I hope you can appreciate how that makes any kind of linear presentation of them pretty challenging that's why I've done this kind of high level overview of all of them and now we're going to dive back into them in detail。



![](img/f8e4ddf052c78187c6a162e3725f1940_17.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_18.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_19.png)

There's really two ways to look at compilation here， one is a database view。

 so in the database view we have tokens。😡，Those are declared in the parser。

 We said percent token in it。And they are produced by the Lexer。



![](img/f8e4ddf052c78187c6a162e3725f1940_21.png)

The other kind of data is AST notess。 Those were defined in our AST module and they were produced by the parser。

😡。

![](img/f8e4ddf052c78187c6a162e3725f1940_23.png)

So the tokens become the interface between the Lexer and parser。

The AST nodes become the interface between the parser and everything else that follows in compilation。

 especially evaluation。

![](img/f8e4ddf052c78187c6a162e3725f1940_25.png)

Another way of factoring our view of this is based on the tools。

 so it's the Lexer's job to produce the tokens。

![](img/f8e4ddf052c78187c6a162e3725f1940_27.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_28.png)

It's the parser's job to produce the AST nodes， but it actually has the responsibility for declaring the tokens。



![](img/f8e4ddf052c78187c6a162e3725f1940_30.png)

And the evaluator computes on the AST nodes。

![](img/f8e4ddf052c78187c6a162e3725f1940_32.png)

Now， the way this is factored between the Leer and the parser is really just a consequence of the way that these tools are designed to work in OcaMl and really OamMl inherits the way it works from previous generations of tools from the C。



![](img/f8e4ddf052c78187c6a162e3725f1940_34.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_35.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_36.png)

![](img/f8e4ddf052c78187c6a162e3725f1940_37.png)