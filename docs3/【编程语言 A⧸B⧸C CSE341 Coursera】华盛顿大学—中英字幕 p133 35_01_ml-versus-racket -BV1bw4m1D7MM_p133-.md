# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p133 35_01_ml-versus-racket -BV1bw4m1D7MM_p133-

Now that we've actually learned a fair amount of both racket programming and ML programming。

 I feel we're in a good place to finally compare and contrast the two languages and their relative strengths and weaknesses So there are a lot of ways to do this and we should first point out that rackcet and ML have a lot in common they both have higher order functions。

 they both discourage mutation， they both have eager evaluation of function arguments。

 there's a lot that really are the same， Of course it's more interesting to focus on the differences and the first one you might think of is the syntax。

 the regular syntax and parenthesisbased syntax of rackcet versus the more sophisticated and subtle syntax of M。

 the fact that M's pattern matching versus the kind ofstructs that we saw in racket。

 that different semantics for the various kinds of lead expressions is something that racket has and ML doesn't and so on but I think it's fair to say the biggest difference in approach of the two languages is that M has a sophisticated type system that rejects a lot of programs before they ever start to run。



![](img/6abd9379455588f906c03a04c0b66128_1.png)

And Racet chooses not to to be more permissive in its set of programs and instead have a wider class of errors that happen while a program is evaluating。

 and it's that distinction that we're going to really focus on for pretty much the rest of this section。



![](img/6abd9379455588f906c03a04c0b66128_3.png)

So we have a lot of questions coming up， we're going to ask questions like what exactly is type checking。

 what does it mean to check for something statically before a program runs。

 why a type checker has to be approximate in terms of what it's trying to accomplish and then we'll build to the real question that people love to argue about which is whether your language should do static checking。

 static type checking or not， but before we get to that I think it'll be helpful。

To better appreciate ML and rackcet as languages themselves in terms of how a racket programmer might think about ML's type system and then how an ML programmer might think about rack's lack of static type checking and how you might code up the racket style in ML。

 so that's what we're going to do here I'll give a nice context before we get into these more precise questions in the upcoming segments。



![](img/6abd9379455588f906c03a04c0b66128_5.png)

So first， let's imagine you're a rackcet programmer。 That's the language you know and love。

 and then you learn ML， and let's ignore the syntax and the different kind of lead expressions in the module system and all that。

 and just focus on this issue of the type system。Probably the most natural thing for a rackcet programmer to think is that oh M is just racket。

 but it's a subset of racket。 It takes all the racket programs。

 the type system gets rid of a lot of them， and then you have M。

 and that's the perspective I want to share here on this slide。

 And you might be very happy because a lot of the programs that M gets rid of have bugs in them。

 You wouldn't want to write them。 And so it's nice that it catches those errors and throw them away from you。

😊，So you have， say， a function like this function G that takes an x and adds x to X。

 There's no bug there。 It type checks the fact that it's you know int arrow int is nice and all。

 but the point is it is in the language。 whereas these functions F and H。

 if you translate them to the corresponding syntax and M would not type check。

 And I would argue that's a good thing。 This function F。

 even though we don't see any call to it in the part of the program we're looking at here。

 you can tell it's buggy。Any call to F is going to raise an error because we pass Y the argument。

 both to plus and to car。 and there's simply no value in racket that that's going to work for。

 We're always going to get an error。 So it's nice to know that without having to test F。

And then here in H， it actually looks perfectly reasonable。

 taking an argument Z con Z and 2 called G with the result。

 But if you actually look at what G is bound to in our environment up here in this first line。

 we can see that will raise an error as well。 We know this it's nice to catch these bugs。 In fact。

 the subset is well enough to find that we do know the type of everything everywhere。 So。

 for example， in the programs that are left in our subset view of the world。

You never have to use built in primitives like is something a number。

 you always know statically and there'd be no reason to at runtime have to evaluate a question like is this value a number and that's pretty neat。

On the other hand， you might not be so happy with this subset because the subset also gets rid of programs that you're used to writing in rackcet and that don't have bugs。

 so this function F here happens to have an if expression that sometimes returns a Boolean and sometimes returns a list。

 there's nothing wrong with that in a racket， It cannot type check in ML Similarlyly this X is builds a list holding different kinds of data。

 can't do that directly an ML either and then on this last line it's just a call to F using X's that all type checks all works fine and a racket programmer would look at this and say。

 okay I'm going to get a true back and there's nothing wrong with this， but ML doesn't allow it。Okay。

 so that's ML from a racket perspective。 You might think that racket from an ML perspective would just be the opposite that it's just a superet。

 and that is one perspective， but I want to show you a more interesting one。



![](img/6abd9379455588f906c03a04c0b66128_7.png)

There are ML programmers out there who like to think of racket very differently。

 They like to think of racket as just a particular style of Ml programming， a very strange style。

 but it turns out every racket program can be thought of an LML program or almost show you on the next slide why this doesn't quite work。

 And the way to think about this is that everything in racket is really just part of one big data type。

It's not that rackcet doesn't have types。 It's that everything has the same type and let's call it this data type the type。

 the one type right So every value is either the constructor int applied to some int or the constructor string applied to some string or the constructor pair for cons applied to two values of the type。

 It's a recursive data type binding functions just take in something of the type and return the type。

 I guess since we have multiargument functions， we could say it takes a list of the types and you would have one of these constructors for every built-in kind of thing in the language。

And then from this very ML view of the world， what racket expressions evaluate to are values of the type because the racket interpreter。

 the racket implementation adds the constructors for you automatically So you just write 42。

 but it's like you wrote the constructor int applied to 42 and racket does this for you。

 so every value passed along has value of the type。

 so there's always a tag that tells you what type everything is and we use that tag so that functions like car can raise errors and functions like pair question mark can see whether they should return true or false so in this world where everything is tagged we can think of functions like car and pair question mark and doing the M pattern matching under the implementation where you can't see it。

So car just takes in some value cases on it if it's made from the pair constructor return the first thing。

 otherwise raise an exception， cause some error， Similarlyly pair question marked as the same sort of pattern matching and uses it to return true or false so everything works this way plus just takes into arguments pattern matches to get out the underlying number raise as an exception if it's not given a number。

 adds those two things together and then tags the result with int so that everyone else in our program can continue to have those tags so really everything in racket is just using the type which you see to find here。



![](img/6abd9379455588f906c03a04c0b66128_9.png)

So all you need to do this is to have a built in constructor for every primitive kind of data in your program。

 You need numbers and strings and booles and pairs and symbols and procedures and so on。

 The only thing this does not cover isstructs。So when an M programmer looks at thestruct and racket。

 they see something that is actually new and different。

 because if you have this one type for everything view of the world。

 what astruct definition is doing is dynamically while the program is executing adding a new kind of constructor to the type。

 And you can do that。 It's well defined， you wouldn't want to do it in M because it would mess up things like checking exhaustiveness and pattern matching。

 but it does make sense that you could have a data type binding that you can add new constructors to M does not allow it。

 but we can think of it as a sensible thing。 In fact， in M， this is how the exception type EXN works。

 but that's kind of an obscure feature that is only sometimes used in that way。More generally。

 I just like this perspective， it's kind of a mind bendending way to think of racket as a programming language that doesn't have no types。

 it has one type， and that's a very ML centric way of looking at rackcet。



![](img/6abd9379455588f906c03a04c0b66128_11.png)