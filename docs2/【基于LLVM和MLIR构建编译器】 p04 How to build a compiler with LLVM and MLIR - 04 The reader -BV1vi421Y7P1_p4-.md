# 【基于LLVM和MLIR构建编译器】 p04 How to build a compiler with LLVM and MLIR - 04 The reader -BV1vi421Y7P1_p4-

Hello and welcome to another episode of How to be the compiler with LLBM and MLR。 This is Samir。

 and let's get started。In today's episode， we're going to talk about the reader。

 the par of the Syrian language。As I mentioned in the earlier episodes。

I assume that you are familiar with some of the basic concepts in the compiler board， so。

I'm not going to describe and explain some of the things about parsers today。

 but just in case let's go over a really brief overview of what is a parser。

To put it simply a parer is a piece of code which reads the source code in textual format and creates the data structured out of it。

We call that data structure an abstract syn texttry。呃。

Theres so many different algorithms to create to build a parer or different use cases I'm not going to talk about them today。

 but I included a couple of links for you as a self study it would be really good to know about like at least the famous ones。

But it's not mandatory。Because most of the time you're going to use a library to create a parer。

 which we call a parer generator parer generators are quite common， most of the languages use them。

And basically what you need to do to use a Part generator is to describe your language。

Different aspects of your aspects of your language in。Type of a grammar。

 different libraries expect you to write the grammar in different formats like BNF and things like that。

But you create the grammar， you express your language in that grammar。

 and you pass the grammar to the parer generator， and finally it generates a parer for you which pars a language in that grammar。

So they're really good， usually since they are battle tested and used in many different places。

 the part that they generate are really good。And most of the generators can generate par using different algorithms。

But in rare cases， you don't need to use the pars generator and ser is one of those cases。

Since is the least。And it's a leastful language。The source code is already in like。

When you write a list language， you are actually filling out a data structure。

So your source code is already well extract， right， so you don't need to go some of the like。

Sts before you need to parse the language like you don't need a lecture really。

 you can just since there's a structure already in place， you can start parsing it into a。A。

To an ASD so that's what we're doing insert learning as well， we don't have a Leer。

 we loop over the input just once。The algorithm that we're using is quite simple， it's just the LL 1。

5， the 1。5 is kind of a joke。But basically how it works is that we starts from there。

Outer left character， which is。The first one， right， we read one character at a time。

And the 05 like 1。5 is because sometimes you have to read two characters ahead。

 so in average it would be 1。5。And。We just loop over the entire source code and decide how to parse it。

That's it， right？The time complexity of our partner is at best ON and at worst02N。And at the moment。

 at this stage， it's not fully completed yet。It parses all the things that we need for the wiring of the compiler。

 so if you remember from the previous episode our aim is to wire up a compiler with them。

A set of minimal features。That just。Compose a source code to a target code， right so。

We are missing many， many useful features for a language。

 but that's okay we're going to add them little by little in the future。

So let's see the source code and talk over the implementation。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_1.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_2.png)

If you remember from their earlier episode， we talked about the straw tree structure of serene。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_4.png)

We have a directory called Read in Serene inside the I directory。

That contains the header files for the reader name and space。The parer。Contains two major pieces。

 one is the location related stuff and the second one， which is the most important one。

 is the parsel itself。So let's go over the location really quick， we have two data structures here。

 one is location and the other one is location range。Basically。

 what location does is to point to a specific point in the source code， for example。

 when we passse the source code we。Specify the location of each expression in the source code using the location structure and the location range is。

Just。A Ra4 location， so it contains two locations， one is the start and the other is the end。

The location range， we mostly use the location range over direct location because。

An expression in list starts from a specific location and in in a specific location as well。

 so it makes sense to know their range instead of just a starting point we don't want to。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_6.png)

fall back to parsing the source code again when we want to raise an error or something like that。

There's like couple several useful， sorry。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_8.png)

There are several useful functions。Actually， a couple of them。Which are quite simple。

Increase the location and decrease the location， ink location， the location。

Increased location moves the location， the given location， which we pass it by reference here。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_10.png)

By one and decreased location does the same thing。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_12.png)

But obviously， decreases the location by one。 We use these two functions in in the parer。

To keep track of where we are in the source code。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_14.png)

I don't。 let's have a look。Look at the implementation as well， I don't think's necessary。

 but just in case。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_16.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_17.png)

So as you can see， the most important pieces are those two functions and they're quite simple。

 they just keep track of the new line and increase the line counter and column counter。

 same goes for the decreased location as well。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_19.png)

Okay， now let's go to the important part。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_21.png)

Important hiter， sorry。The reader dot H the。Main in entry point of the reader。

 So basically we have a reader name and space inside the certain name of space。We here。

That contains a reader class。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_23.png)

Breer class is it's not a bass class。But we have two parsel at the moment， two readers at the moment。

 one reads from a string， the other one reads from a file。The reader reads from the string。

 from a stream of a string。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_25.png)

The current character obviously stores the current。

Character that were reporting at the moment I just use the initial value which is kind of useless。

As a comma， sorry， as a comment。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_27.png)

Inputted stream， obviously the。Input source code that we need to parse by the way I just realized that I'm using aN cases for a variables name here。

 but since we wrote the parer long ago， we didn't go by the style guide。

 we changed our style guide to use the LLVM like coding a style。

 we have to use something like a CAl case which it starts with a lawyercase。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_29.png)

Vor for the variables names， but it's okay for now I'd probably change it in the future。

We have a function called get Care， which as you can guess。

 it just reads the next character and returns it。The most important thing about the red getcar is that if we pass white space as true。

 it's going to escape all the white spaces till it gets to the next character。

On get care basically unreads the。Current character， why。

 Because sometimes we need to go back and provide this。

Kind of let reader function to read that character， we will get to that in a bit。

Another function here is valid for identifier， that is quite simple， it just gets a character。

 check whether it is a valid character to be used in a symbol if it is returned true otherwise false。

AsSD， again， simple enough， this is the actual output of our reader。

 which we are going to return eventually。So here's the important part we have。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_31.png)

4our different functions， we call them read their functions， each of them。

Reads an specific type of expression。From the source code and creates a node。 What is a node。

 I'm going to show you in a bit， but it's。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_33.png)

An abstract node in our AST tree。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_35.png)

The public interface of this class is quite simple， create a reader and set the input。

 sometimes we don't have the input when we want to create the reader。

 but that's not important for now。Oh by the way， if you don't know what a string graph is。

 you need to take a look at LLVM documentation， there's a long section on I can't remember the name but basically they describe different utilities and different types that LLVM provides for like ES sub programming。

 a string graph is one of them quite useful just like referenced on a string。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_37.png)

But make sure to check out that documentation page。

 I'm going to put a link somewhere on the screen for you later。We have a read function。

 which is the main。Public function on the reader， it parsees the source code and returns a result of an ASD。

What is the result and what is a ASD type I'm going to talk about that。Briefly。

In a couple of minutes。And finally， to a string that is quite obvious。

 I need to change the name here actually to dump。Instead of twist a string because twist a string kind of。

Imply that it has to return a string， but it in fact writes into the studio。

 so it's not a good name I have to change it to them。去你。😔，do。Yes。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_39.png)

してです。Just for future reference。And another class， which works on the same。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_41.png)

看到。works in the same way as the。A reader is file reader。That uses the reader class internally。

 but just reads from a file rather than an input string。Same interface doesn't matter。

 We didn't use any abstract class or anything we just because just there's just one public function we don't want to。

 I didn't want to bother with abstract classes and stuff like that。Also。

 one other important function。Is the read function， it's not a member function。

 just a function on its own。I consider the this function as the public and this sole entry point to the reader at this stage later on I'm going to write more read functions that get different types as the input。

 but for now since we just want to stick with the minimal set of features。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_43.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_44.png)

This is enough， right？So let's take a look at the implementation。没理解。Okay， move to the top。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_46.png)

Okay。So。I'm going to skip over some of the obvious implementations and just talk over some of the less obvious ones。

Such input is quite simple。Give it a string， give it like a inputter string。

 it's going to do some initialization and set that string as the input string。

Set the current location to unit， unit is just like。The initial location， which is zero， zero， zero。

Remove the previous ASD if there is any。And finally， create input stream out of the input stream。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_48.png)

Decar again in a loop， we read a character from the input stream， sorry， inputest stream。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_50.png)

Set it as the current character。Increase the location by one with respect to the end of the line since I'm on a Linux environment。

 I hardcoded the end of the line here， but we have a to do to respect the OS end of line。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_52.png)

And if a skip white space what's true is true。And the character is a space， ignore it。

 move to the next character。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_54.png)

Otherwise， return the character。Unget care is quite obvious as well。

 decrease the location again with respect to the end of line。

Just put the character back into the stream。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_56.png)

Is valid for identify is like really simple and it doesn't。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_58.png)

Need to talk over it。😔，Talk about it。 So before we talk about the reader functions。

 we have to start from。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_60.png)

Read Exp。Right didn in here。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_62.png)

So the member function read experter， basically。Is a dispatcher function。

 it reads one character from the input， it doesn't escape over the whitet spaces。

And it put it back immediately because in some cases we need the reader function to read the first character。

 like for example， a symbol。If I put a comment here， let's say。啦。Blah is a symbol， right。

 If we read the first character and pass the rest to the。Reader function。

 then it's going to end up with La。But we need to put it back so it can read the actual b。

 that's why we aren't get it immediately， but it doesn't happen。All the time， for example。

 in case of at least we don't have to read the first character。Okay。

 so we'll look at the character that we just read if it was an open parenthesesis。

Call the read list to read the list。If it was the end of while。Return null null pointer。

 the node is like a shared pointer I'm going to show it to you later on。Otherwise， rate symbol。

Quite easy really simple in the future when we want to add。

 I don't know vector maps and different pieces of the language we're going to expand this switch case into more cases。

 check for different characters here and call the appropriate reader function。

 but for now it's quite simple。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_64.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_65.png)

Let's start with the red symbol because it's the easiest one， in my opinion。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_67.png)

Basically。We cant think of numbers as symbols as well， but they have a different semantics， right？

That's why we need to。Be careful here。We read the first character， if it was a valid idifier。

 a character for identifier， we continue otherwise， we show an error an just exit。By the way。

 I know this is nasty， we don't have a。I don't know what to call it like an error system at the moment。

 but that's next in line to be implemented。When we implement that piece。

 I'm going to change all the simple errors that we use here， it should be like more elegant。

It should have like a nice representation， at least。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_69.png)

So if the first character was a dash， so it might be a number， it might be like a negative number。

We check for like the next character in line so we read two ahead of time and if it was a number indeed we will call the read number function。

 I'll get to that later。Again， if the first character was a number， go read the number。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_71.png)

Otherwise， create a location range and。Sorry， set the starting point at the current location。

Read the entire sequence in a loop and if it wasn't empty。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_73.png)

Create a symbol out of it。So this line is kind of important here， right？

I zoomed out a lot so it breaks when I when some hints has to be shown on the screen， but anyway。

 this is how we create nodes in our ASD the symbol class from Exp is a class representing symbols in our ASD it gets a location almost。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_75.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_76.png)

Yeah， all of not almost like all of the sorry， all of the expression classes gets a location as this first argument and the rest is different based on the。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_78.png)

Class based on the type basically。So。What happens here they make？

Function acts as the main entry point to the ASD。 It creates a node for you。

 but it gets the type of node that you want to create。 for example， like at this in this case。

 we want to create a symbol node。 and then we pass a symbol name。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_80.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_81.png)

From the like we reads it from the source code and pass it to the constructor of。Symbol class。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_83.png)

And since reader functions has to return a node and make create a node if you see the。

If you look at the。Description on top。Right off the screen， you can see that it returns。

 make returns and node Excel。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_85.png)

Otherwise， we need to return an null point there and as I mentioned in the todo it should never happen。

 but we have to take care of that later， it's not important at this stage。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_87.png)

Now let's have a look at read number。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_89.png)

Okay， just like any other reader function， it returns a node。

Gets just one parameter which indicates whether we're reading a negative number or a positive number。

I don't think yeah， yeah， we take care of float here as well。We read the string。

 we read the number as a string with some location attached to it。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_91.png)

And then。We do some checks whether to find out whether it's a float or not things like that and finally。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_93.png)

Here， we create a。We create a number。A node out of the string that we just read。Alright。And again。

 noll pointer if it wasn't the case which it shouldn't happen， we take care of that in the future。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_95.png)

And finally， read list function。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_97.png)

This one is a little bit different because we create the node first with the current location attached to it as an empty list。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_99.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_100.png)

So make and cast， while the make function， the experiment main function returns a node。

 make and cast creates a node buts casts that node into the given type。

 so list here would be an actual list in a seven node。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_102.png)

List it still is a node， but since we cast it to a list。

 we can use different member functions of the list here。Okay， I have to make another todo here。

We shouldn't use A to be honest。Oops。你可识你。😔，嗯。Because Az is just debug only and it won't make it to the release。

Build， so it would be pointless to check。To have this check here in an A form。

 we have to have an actual check and fail if it was the first character is not an open panhesesis。

So what happens here is we read a character if it was the end of line。

 it means that we reach the end of line while we were parsing an open list so it never the user never closed the list。

 so it's my problem， it's an error。We have to rise。 And and if the。Co there was a close parenthees。

 it means that， okay， we just finished with reading the list， let's create a list and return it。

And if the character wasn't any of those two， let's read another expression。

And append it to a list so a list is basically a sequence of expression expressions。

 different expressions right a list itself is an expression， so nested lists are steel expressions。

We read the next expression by calling the read Exp reader function and upend the node to the list itself。

So basically we keep doing it until we reach the point that we see and see close parentheses and at that point we just return the node。

 right？Easy， busy， it might seem a little bit complicated， but it's not really。So。

That was kind of the entire reader。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_104.png)

Beside the read functions， the read function is the most important one。

And yet it's like quite simple what we do here is。To get a character， escape the。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_106.png)

Escape the whitet spaces， check for the end of the line， if it wasn't the end of the line。

 just read the first expression and push it to the ASD。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_108.png)

This ASD here， if you remember， is a member。Member attribute in the reader class so what we we're doing here is until we get the end of the line。

 we get to the end of the line， we read an expressionion。

 push it back to the ASD and at the end create a result out of it。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_110.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_111.png)

What is the result？Result were actually I'm going to show show it to you。

 it's quite nice to know about the result at this stage， but for now before I show it to you。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_113.png)

Just。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_115.png)

Think of it as a successful result， which contains the actual result。Okay。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_117.png)

To a string is quite easy as well。Each of the nodes in our ASD。

I have a function to represent themselves as a stream， we loop over theT。

And basically call that to a string function on each node and print it out。Somer。

To to actually hang on a second。Are we using the twist string at all。Oh yeah。

 this function is redundant。 We need to remove it。 Now I remember that I added another function to do this。

 It's not important at all。 We can。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_119.png)

Get rid of this function entirely。What I'm going to do after I stopped recording。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_121.png)

嗯。The reach function on the file reader is kind of similar as well。

 the difference is it reads the implementation from reads the input from a file and create a reader out of it。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_123.png)

And call the read function on the Read class， itself's easy。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_125.png)

Again， we don't need this one as well。 We can remove it that。😔。

Detro is not important and finally the main entrance， which is the read。Bangsheng。Creates a reader。

ReSet the input， read it， and return the ESD。Sorry。😔，Easy。Now let's have a look at the result first。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_127.png)

It might be a little bit overwhelming， but basically what it is。

 it's if youre familiar with functional programming， it's like a MonA， like a。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_129.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_130.png)

What does it call like in maybe Monad， but it's a little bit different in implementation。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_132.png)

There's， you can read the。Comments here later on， but simply。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_134.png)

Result is an object that gets two types， the first type is the type of the value that is it wants to hold when it's successful result。

 otherwise the second type is the type of the value that result needs to hold when it is not a successful result。

The implementation here is not that important， but basically we use a variant which is like a union here。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_136.png)

We have implementation of a different function that puts the different value in that union like the success function gets a value of type T and put it in the variant as the successful type like the variant one sorry zero。

 not one and error is basically gets the second gets input of type E and put it as the as the second type in the variant so the implementation is kind of it looks as scary but。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_138.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_139.png)

The fact is it's a value of two types， it's either the type T or type E and you can check whether it holds type like which type it holds by calling the OK function or a basic pullolean use it in a like a if as an if conditional。

 it will tell you which one it holds and you can get the actual value by calling get value or get error like it can return a reference or a move reference or whatever。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_141.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_142.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_143.png)

That's the result part and just to show you quickly what ASD is and what nodeD is。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_145.png)

Oops， oops， oops， oops。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_147.png)

So ASD and node are defined in the expert name and space。

 actually my editor points to the wrong location so let me。T it to you，哪。😔。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_149.png)

那你嘞。😔，Okay。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_151.png)

So in the expert name and space we have an expression class which is an abstract class for all the nodes in the ESD node itself is a shared pointer to an expression expression is an abstract class so it can be a number can be a symbol at least or whatever thing that we have we have several more types in ourD that the reader doesn't know about them but the semantic analyzer node about them like we get to them later in the future and some other types。

For example， maybe node is just a result type of node and a rot tree。

I I just show you the results so the successful case would hold a note otherwise an error tree and ASD is a vector of notes simple as simple as that right although maybe ASD is again a result of。

ASD as a success case and error tree as the failure case。It's quite simple。

 but how our ASD works that for another episode and not today so let's go back to the。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_153.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_154.png)

I there here。As you can see， our reader is at this stage quite。Dely simple。

 we have some test cases for it。In S C， sorry， S C。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_156.png)

Ts。Reader reader test cases。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_158.png)

You can see how we might use the read function pass string containing some expression sorry it returnss the maybe ASD if it wasn't。

A failure case， we have to fail the test。Otherwise。

 we get the value by moving out the actual value from the maybe ASD to ASD and then do our testing。

By the way， this two a string here refers to the two a string method of the node and not the reader。

 just to make it clear。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_160.png)

Have a look at the test cases， they're quite simple， there's not much because they。

Reader is quite simple at this stage it will show you how to use the reader on your own I wanted to show you one more thing okay so if we。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_162.png)

Go to the terminal。So I didn't talk about the serC file itself yet just yet because it contains some detail that you shouldn't know at this stage it's going to make you。

 it's going to confuse you， but just to show you how to use the reader。

So you already know about the builder script if I run the builder。And passive。Run up command。

With a meat。I basically want to emit the ASD， so it would be like parse this input file。

As the ASD and show me the ASD。One more thing to know。

 since it's like a we try to be as minimalistic as possible。

 we only support the full path at the moment， so that PW here basically。

Gets the current working directory and attach the rest to it。So if I just call this one。

 as you can see， it prints out the ASD for us， why it looks like this。

 each of the nodes has a to a string function that converts the node。

 the AST node into like a string representation， so for example this one is a symbol node that contains the name de。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_164.png)

This one is a symbol node that contains the name main。It goes on， I guess。

This is how you can debug your ASD if you decided to play around with the reader。

 this is how you can actually see the ASD on for your changes or for your input。

 also there's one more thing to show you here。If you provide a flag called Dbug。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_166.png)

Os。对吧。It will spit out all the logs。Yeah， basically all the logs that we have in Serin itself to help you debug your issue。

 we might have different pieces， different types of loggers in the source code。

 that's why you can restrict it to just one type of logger for example debug only reader it show you the reader log entries so as you can see it says like what character it's reading in what function。

 it reads a symbol， Read symbol， reading a list， things like that it can help you debug the changes you might to make to the reader file。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_168.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_169.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_170.png)

Also， the last thing I want to talk show you is。

![](img/542a53fb59a278f6d2d7115f5c07e7b9_172.png)

Yeah， the reader log， so we define a macro called reader log that calls the debug with type of LLVM and sets the type to reader this reader here is the one that we pass into the pass of the CLI。

 right？

![](img/542a53fb59a278f6d2d7115f5c07e7b9_174.png)

As simple as that， use this logger whatever you want later on we're going to it out from the。

Release build， and it's not that important at the moment。

So here you go that's the reader for you quite simple let me know if you have any question in the comments or reach out to me directly finally if you find my work interesting or you're interested in this content please subscribe and please share your feedback I really like to have your feedback on this video series thanks for sticking around and have a great day。



![](img/542a53fb59a278f6d2d7115f5c07e7b9_176.png)

![](img/542a53fb59a278f6d2d7115f5c07e7b9_177.png)