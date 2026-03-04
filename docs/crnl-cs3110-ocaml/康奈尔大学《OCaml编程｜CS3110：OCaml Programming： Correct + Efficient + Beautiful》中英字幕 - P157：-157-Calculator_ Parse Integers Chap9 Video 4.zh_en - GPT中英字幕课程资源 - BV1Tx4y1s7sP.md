# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P157：-157-Calculator_ Parse Integers Chap9 Video 4.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

The very first test case I have here is just trying to interpret the integer 22。

Let's work on that next。 going back to our AsT。We're going to design a tree type here for representing the expressions in our source language。

One of those kinds of expressions is just integers like the integer 22。

So I'm going to build this out as a variant type。And have a constructor named int that carries along with it。

 an Oaml integer。So this will represent an integer from our source language we don't have plus or multiplication of parentheses yet。

 and we'll get to those later Next， let's take a look at the parser and extend it to handle integers。

Now remember what the interface between the Lexer and the parser is， its tokens。

 the Lexer needs to produce a token stream which the parser then consumes。So in my parser。

 I actually need to define what the tokens are。😡，I've got one definition here so far。

 which is just the end of file or EOF token。 That's a special token that the Leer is going to return when it reaches the end of a string that it's trying to parse so we're kind of puning strings with files here。

😡，Now I need to have tokens that are integers as well。

So I'm going to go ahead and define a new token here。With percent token。

 and I'm going to call this token INT capital INT for integer。

And this token needs to carry some information along with it。

 It needs to actually carry an integer with it to say which integer we parsed。

So I'm going to put that in here as an Ocal type int。Now this is funny syntax。

 let's not get too far into it here， but basically what we're saying is behind the scenes there's going to be a variant type for tokens and this is telling the OKl parser to add a new constructor for that named int capital INT that carries along with it some information of type int small case IN。

Okay， so now that we have that token， we need to go ahead and parse it。

So I have what's called a rule here for parsing a program。

 and so far all I can parse is an end of file。😡，But I want to be able to parse more than that。

 In particular， I want to be able to parse expressions out of these strings。

 So what I'm going to do is extend this to say， actually。

 I want to be able to parse an expression here。And in fact。

 that expression should then be followed by in the file， so it's like an entire expression。

 an entire program， there's nothing left else left to do。And I want to call that expression E。😡。

And as a result of parsing that program， now I want to return E rather than just unit。And in fact。

 now that I'm going to do that， I want to return as the result of parsingololius and expression node from the AST。

So all of those changes were driven by the fact that I had created this expert type and added a constructor to it。

Now， as far as parsing that expression， let me introduce a new rule and there are going to be many kinds of expressions we could parse by the time we're done。

 but this ones just going to be an integer， so I want to be able to parse an integer。

Now I'm using INT there in capitals because that's the name of the token。

So when I see an integer token， what do I want to do with it？Well。

 I want to return a value of the AST node to represent that。😡。

So that means I need to return an int constructor， but of course， I need to return which int it is。

And so to do that， I will say that I want little I to be the actual int value that was parsed there。

 like 22。So this will then return int 22。That builds out our parser。

 Now I need to take care of the Lexer so that it can transform a sequence of characters into an integer token。

So in my Leer I already have a rule that says that it can parse end of file。

 it can just recognize the end of a character string。

 but I want to extend this to be able to parse integers or really lex integers。

So when I see an int there， and I'm going to need to define what int is。

 the Leer already knew what EOF meant， that was a special thing that I needed to define int。

I want it to return an integer token， and I'm going to need to fill that in of what particular integer I want to return as well。

😡，Okay， so there's two pieces to this， one is to actually define what an int is。

 I'll do that up here。So what is an integer， Well， an integer is composed of digits。

 So let me define a digit first。Digit is going to be any character in the range zero through nine。

OkaySo a digit is0，1，2，3，4，5，6，7，8 or9 as a character。And now an int is going to be a digit。In fact。

 it's going to be one or more digits， so you've got to have at least one and you can have as many of them as you like that's what the plus means there。

And optionally let's allow negative integers as well here。

 so I could have the hyphen or dash or negative sign there and I'm going to make it optional。

 That's what that question mark means。 and in can either start with that and be followed by some digits or not start with it and just contain digits。

Okay， so now that I have defined what an integer actually is in terms of a character sequence。

 what am I going to return along with this int token？Inside the Ocaml Leer。

 there is a module called Lexing， and it has a function Lex E in it。

 And if you apply that to the special variable named Lexbuff， which already exists。

 we didn't have to do anything to create it。 What that does is it takes whatever was matched over here。

 In this case， a sequence of digits。 maybe with a minus sign in front of it。

And returns that as a string。Soine Leum Lexbuff gets me back that string。

 of course I need to convert that to an Ocal int because that's what my AST carries along with it and that's what this token carries along with it。

 so I will apply the standard library function int of string to that to actually turn it into an。😡。

Now let's go back to mainine and look at the parse function inside of it。

So the parse function there in which I've annotated the types of the input and the output just to make it completely clear what they are。

 is going to take in a string and return an expert， that type that represents an AST。

Inside the Leing module from the OM Leer， there's a function called from string and you pass in a string to that and it gives you back a Lexuff a Leer buffer。

 this is something that characters can be read from。

I then pass that Lex Buff to the parser module in which there's a function called Prag standing for program。

😡，And that function also takes in another argument， which is a read function from the Lexer。

Now the names of those are no accident， you might already recognize them in fact。

 so in my parser file here， I actually had a rule named Prague and I had to said that's where I start parsing that causes the OcaMl parser generator to create a function called Prague that I can call and get back an AST。

😡，Likewise， in my Leer file here， this read that was a choice of my own that's causing the Leer generator inside of Ocal to create a function called Re。

 and that is what is transforming a sequence of characters into a token。😡。



![](img/8bcea1262f58eea52477574d3807e459_1.png)

So you can see it all laid out here， Leexer dot Re is going to take in that Lexbuff。

 which is representing a character stream and give back a token。

 parser dot Progue is going to take a function that can transform a Lex buffer to a token。

Take in the Leing buffer and give us back an AST。And so that's what my parse function is doing。

And now already， right away， I can go ahead and parse integers。So if I rebuild my code here。

 I can now parse the integer 22， which I couldn't do before and get back a value of the AST。

 which is an int node containing 22。Of course， if I try to interpret it at this point。

 I'm still not there， I haven't implemented that interpreter yet。😡。



![](img/8bcea1262f58eea52477574d3807e459_3.png)