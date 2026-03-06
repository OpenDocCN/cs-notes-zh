# 【基于LLVM和MLIR构建编译器】 p05 How to build a compiler with LLVM and MLIR - 05 The Abstract Syntax Tree -BV1vi421Y7P1_p5-

Hello and welcome to another episode of How to build a Comp with LLVM and MLIR。

 I'm Samir and in today's episode。We're going to talk about the abstract syntax tree。

Before we start a quick shout out to the folks who reach out to me and shared their feedback on the video series。

 thank you folks， much appreciated。And it means a lot to me， thank you。Okay， let's get started by。

Taking a look at what is an ASD tree， what is an ASD， sorry。So in the previous episode。

 we talked about the reader and how Parers actually read promo string of seemed like a Gison a string that contains the source code and convert it into a data structure。

And that data structure is an abstract syn text tree， which is。

An abstract syntactic structure of the source code。So。Like any other tree。

 an abstract syntax tree is made out of nodes and each node represents a syntactic piece of the source code basically。

 or different syntax in the source code。So as you can see， I already。Wrote a studio list code here。

 like two lines of code in the first line we have a。

Were defining a symbol called main and bindinging。The name main to an unanimous function that returns for all the time。

 it's a constant function。And in the second line， we're calling a function called PRN that basically typically prints out whatever you give give it to it。

 So in this case it calls the function main and prints the return value of that function。

It's a pseudo code， like it doesn't have anything to do with serene at this stage。But。

If we pass this source code to the reader， it's going to create an ASD out of it。And in the diagram。

 below the source code， as you can see， I tried to map out the。A SD into an diagram。

So we have two lines of code。Each line basically gets translated into a tree on its own。

So the the three on the left， we have a list on top which represents the entire list here。

It has three elements， the first element is the symbol de， so de by itself would be a node in a tree。

 right so that node contains a symbol and the symbol name is de。The second one。

 the second element of the list is main， is that another symbol sorry。It's another symbol。

That the name is main， just like the first one， but the name is different。And finally。

 the last element in the list is another list。So。The last element is a list。

And it has its own elements， the first element， again， another symbol。But the name is FN。

 an empty list， as you can see， with no children and a number four。

So all of these white boxes are representing a node in our abstract syntax tree。Also。

 the entire tree here。So the left three。By itself is another node in a bigger tree， you know。

 so we have two lines here， I could have actually kind of sort these two trees as a children of another list here like here。

I could have put them as a child of a parent least。

Since that technically that's not a character representation， I decided not to do that。So。

Here's the first line on the left and on the second line， we have two lists， like a nested list。

The first one has the first list and the other list has a。Element， which is a symbol。callled PRN。

 So the first node under the list is a symbol that the name is PRN and the second one。

 which is the one in here。Is a list that has just one element， a symbol main。As you can see here。

 we don't have any。Semantic structure， so we don't know like where is the function。

 where is the function called or what are the types of different pieces in this tree well like we don't know any of that the only thing that we know is like how the source code。

Like it。Basically， we know the structure of the source， but that is it。

We have some notes and we don't know whether they work alongside each other or they semantically correct or do we have a syntax error here we don't know any of that Of course the reader would sanitize the source code to some degree for example。

 if I like。Remove a parentheses from here actually I should have removed that parenthesesis that was like extra one and that's another like that can be a good example if I put a reverted bag I put like a parentheses here so。

😊，This syntax here is not correct， we have an extra closing parenthesesis at the end and the reader would actually catch that。

But for example， if I， I don't know， put four here a lot。Put a number here， number two here， right？

Semantically speaking， this is not right， who is not a function we can't call number two。

As far as reader is concerned， as far as the father is concerned， this is right。

 so the synctic syntactic structure of the source code is correct。

We can have a list have number that has number two as the first element。

 nothing is stopping us from doing that， but later on when we get to the semantic analyzer and other pieces of the compiler。

 we'll see that actually we have to catch these type of semantic errors。

For now let's stick to what we add in here， okay。Soまあ。

We ended up with a tree of nodes that each node represent a。Syntactic structure in our source code。

No semantic analysis yet。Basically， the diagram we have here actually represent the data settings ASD。

 so the node names are correct。But to get us started with the actual implementation of theC。

 we have to talk about the abstraction sorry the expression abstract class。

 we have a class in terms of like object oriented。Programming。

 we have a base class or an abstract class called expression， which I'm going to show you in a bit。

This class is the parent class to all the nodes that we might have in Ser ASD。For example。

 in this diagram， the symbol list， the number， all the symbols， all the。

Notes here are a child class of the expression。But while I chose the expression as a name。

 it has nothing to do with the ASDS stuff， but I guess it's a good time to talk about expressions。

What is an expression and how it differs from a statement so depends on the language you are familiar with。

 you might know about expressions and you might not know about expressions。

 many languages have statements like I don't know a equals to4 for example。So in a language。

 you might see something like this， right a equals to three。Here is state in an imperative language。

 a equals to3 is an statement。You're stating that there's a variable called a and its value must be3。

 So you're kind of assigning the the variable a with the value。To the value， number3。And that's it。

 that's just a statement。If we want to look at it like mathematically， this is just like a。

Logic logical statement， you're stating that a equals to3 is true， right？

But unlike statements in an expression evaluates to a value so for example。A。The oops。

A plus3 is an expression， so if we evaluate a plus3。

 we end up with a value depending on the value of a。The final result might be different。

 but there is a final result。Expressions always evaluate to a value by the statements。

They don't evaluate into a value， they're just statements， they're a stating effect。So。We can。

 like expressions are actually if you took a algebra course in high school or whatever。

 youre already familiar with like。Experions， all the algebra basically is about expressions。And。

Lisppe itself。Like。L is not a language， it's like a framework for languages。

 it's hard to describe it， it's like a way of thinking。

 it's like a mathematical model for a programming language and sharing being a list means。

It has to follow certain rules， so one of the main rules in Lisp is that everything is an expression there's an like a asterisk there。

Some of the list implementation doesn't follow that rule and this rule is not actually really obvious when you read the paper。

That being said。This is a rule like this is an implicit rule in the listsp world。

 everything must be an expression， so everything has to evaluate into a value and after all。

 a Li is all about reading and evaluating some S expressions or like symbolic expressions。

I'm not going to get into the。kindind of the theory here。

 but we might have an episode about what is a list and why it is different than other programming languages and what is the idea the main idea behind symbolic expressions。

 but for now everything is everything in Lsp must be an expression and expressions evaluate to a value while statements stating a fact and they don't evaluate。

 they don't evaluate into a value。Okay， let me read one of these。Okay。Now。嗯。

It's time for me to show you some code。Let's start from expression。That H。Okay。So we have a fine， oh。

 I don't know Doctor wrong file， sorry。Expressation okay。So。We have a file called expressionion。

 H in the include Ser and Exp directory， you can see the full path on the bottom on the center。

 basically let me actually here's the full path to this file from the root of the project。

This header file is actually the main entry for you if you want to read the source code for Ser ZestD。

Let's have a look and see what's going on here。Obviously， we have a name of space called Exp。

What I'm trying to do in the Syrian source code is to。

Basically kind of map directories to name asspaces。Inside the serene directory。

Each subdirecty would have a name and space for itself。So。We have some type tys here。

That are kind of really important you would see them all over the place in the source code we talked about node the other day on the previous episode it's just a shared shared pointer to an expression since explorationir is。

Parent class do all the expressions， all the nodes in the ASD。

 basically a node is a shared pointer to a type of expression， it can be a symbol。

 it can be a number， it can be whatever。Eror pointer， it's the same。

 it's a shape pointer to an error。We're going to talk about errors maybe in the future。

 but for now you can think of them as another type of expression。

 but I'm kind of avoiding I'm trying to avoiding them because it's in my plan。

 it's in my radar to actually refactor the whole error system and error handling system in the future in the near future。

 so it's not kind of wise to talk about them right now since they're going to be major differences。

 major。Refactoring there。So。Another thing is error tree。

 which is just a vector or error pointers and since pointer  errors are stackable so  error can contain other types of error and they can stack on top of each other。

 error tree is actually a tree rather than only a vector。

Another important type for us that we use quite a lot in Ser is maybe node we already talked about their result type。

 which takes two types one as a success case and one as a failure case and maybe an maybe node is a result that the success case is a node and the failure case is actually an error three so maybe node can be translated to。

And there might be so let me rephrase if we have a node that its type is maybe node。

Then in place of that note， in case of a successor story， there would be a note。Otherwise。

 if there's something wrong in that note， there would be a error tree there。

It might sound a little bit complicated， but when you see how we use it， you're going to get it。

And finally， the ASD itself is just a type there for a vector of nodes。As you saw in here。

I didn't put these two lists as children of another list here because we modeled them like this。

 So AC is just a vector of nodes， right。And similarly。

 maybe ASD is just the result that the success case is an ASD and otherwise it's an error tree。

 we use maybe node and maybe ASD quite a lot。Also here's the like app。shorthortcut for us that。

Is an empty node whenever we want to have a note that the success case。Holding an null pointer。Sorry。

Since node is actually a shared pointer， it can be an null pointer。

And then we represent an empty node with a null pointer。

 so whenever in the AST3 that we have a null pointer。

 that node is empty it might sound a little bit strange and to be honest like I don't like to use null pointers anywhere。

 they're just recipe for disaster。But we have a mechanism to use them in the semantic analyzer which we're going to talk about in future episodes and I'm going to show you how we're using them。

Obviously。This is just the minimal working version of the compiler and most of these kind of tricks are going to go away in the future when we want to like have a solid foundation。

 but for now it's fine we want to finish up our wiring first。Okay， let's move on。

And here is the most important piece of code that we're going to go through today。

 the expression class。As you can see it's an abstract class， it has some virtual function members。

 by the way as I mentioned in the first episode I'm not a C++ expert so I'm not used to like terms in C++ word so sometimes I might say something that might sound stupid in C++ and I borrowed them from other languages so please bear with me I'm not used to calling method。

Function memories， so I might make mistakes at times to times。😊，Okay。

 so the expression class contains several virtual function members that each member。

 each node and each expression type has to。Override them， basically。

The only thing that the expression class itself handles is the location。

So in the previous episode we talked about the location range。

 a location range basically is a data structure。That。Like you。

Contains the starting point and ending point of an expression in the source code right so any expression in the ASD。

Has to be able like we should be able to find that expression。In the source code， So， for example。

Let's go back to here yeah。The symbol main here， the symbol would be an object inheriting from the expression。

 so it would have that location range， the location range of main would be on line zero from columns1。

2，3，45 to like I don't know8， right？Or not。Later on， whenever we want to point to the source code。

 whether there's an exception there or something is wrong。

 we want to print out like a stack trace or whatever。

We can look into the location to find out where exactly that thing happened in the source code and print it out in the CD out we get to that later again。

 but just to have an idea of what that location range is for。And obviously。

AConstructor to initialize the location。So。😊，We have four virtual function members。

 the first one is the get type。The get type， it doesn't have anything to do with the type system because we don't have a type system yet then I'm kind of。

Hesitant to change the name because there might be conflicts in the future。

 but I'm going to leave that decision to the future me right now， let's stick to whatever we have。

The get type basically returns an expert type enum。Each children， a child of。Experion， basically。

 each top class has to have its unique get expert type。So。What is an expert type。

 as you can see here， we have different like。Expertite by itself is just an enum or inum how it depends on how you pronounce it。

That contains several different values， it can be either a symbol list， number， D， error。

 fn and call this list definitely will grow in the future， but for now we have only these types。

And again， each subclass has to return a unique value here。Another member function is to a string。

 which is kind of really obvious， but the only。Important thing about the two string function member is that。

This function is just for debugging。 It doesn't have anything to do with the actual type casting in the language。

 it's not any of that。 So whenever we want to print out an AD in the。In the CD out。

 we call the twist string function of the nodes。If you remember from the previous episode that we actually tested the output of the reader by printing out the ADSD。

That's how it works。 It calls the to a string function member of each node and ask it to return it string representation and print it out in the。

It city out。We have two more function that are really important。

 but we're not going to talk about them today because they're kind of not related to ASDs。

 really the analyze function and generate IR。The analyze function is actually used for semantic analyzer in the semantic analyzer。

 which we're going to talk about next， hopefully in the next episode， I don't know yet。

And the generate IR is the function that we use for code generation。Converting the ASD to the CIR。

 which is our first layer of intermediate representation。呃。

The only thing I can say right now is that any subclass has to overide these two functions and provide the logic for semantic analyzer and codegen for their own type。

That was the expression interface quite simple， it might grow in the future。

 but for now since we're looking for a minimal set of features for a compiler that's all we need。

We have several functions here that we talked about earlier in the previous episode。

 but these functions are the main in like the official API to interact with the。With the AS C。

 So whenever we want to create a node， we have to call one of these functions and nothing else。

 like we can't go around and create。like use the constructor of different expression types。Directly。

 we have to we should make sure that we're using one of these functions。

The first one that we saw in the previous episode as well is make it。Like if you。

 if you're new to C++， this is kind of really weird。 but if you're a C+ plus guru。

 you know what it does， it it takes like。Number of arguments and basically create a Sha pointer based on the first type and pass those arguments to the constructor of that type。

It might sound weird， but an example would like make it easy to understand let's say we want to create a symbol right all we need to do is to do something like this sorry。

Oops。你到。😔，And pass it and name because the constructor of the symbol just accepts one， accepts one。

Input。So all it does。Is the symbol here would map to the type T here。

 right so the first type of the template would be symbol and the rest。Like it is not important here。

And we use the basic like it would be like， okay， whatever you pass here。

 I don't care about the type， pass it to the constructor and deal with it there， that's basically it。

Nothing special and we're calling the constructor of type T here because like make shared calls the constructor of whatever type you gives it to and forward is basically what I told you it's just like I don't care about this kind of stuff。

 forwarded to the down the line， like whatever is there let it deal with it， I don't care。

And since the。Anything that we pass here should be a node。So make function actually returns a node。

There's a， like a。Really important issue here since we didn't constrain the type T to any interface or any trade。

We can pass actually any type here and expect to get a note back。So if I pass like an in here。

 it should break but。That's like， I can't fix that but。

It's going to be kind of one of those things that we don't care right now since it。

It's like a minimal version we expected to just work to be quick。Just for that。

 I created a to do for it to fix it later， free if you're interested， feel free to send me a patch。

Okay moving on the make function returns a node and if you remember a node was a shared pointer to any type of expression。

 so what you get here is an expression right we have another function called make and cast which basically casts the created node into the concrete type so the type T here is a concrete type concrete type meaning that it is its a。

Type that you can actually use， it's not a like abstract class。

So the difference is make and cast returns the concrete class concrete node while the make function returns the abstract node。

So if you want to use like。For example， if you create a symbol here with make and you want to use something specific to symbols。

 then you have to cast that abstract expression to a node。

which basically is the same thing that make and Ca is doing。

 it creates the node and casts it in place and returns the symbol for you。

 so what you get from make and cast when you're creating a symbol is a shared pointer to a symbol。

 not a shared pointer to an expression and since symbol is a child class of an expression both of them are actually nodes and they can be used in the ASD。

We have two other functions， helper functions， one is make successful node and make it or full oh。

 it should have it should have a node here， but I forgot about that， I have to fix it。So remember。

 we had a type called the maybe node。In the future episode when I'm going to talk about semantic Anar。

There might be a situation that our syntax is correct syntactically， but is not correct semantically。

If it was correct semantically， we want to return。A success type basically maybe node was a type of as you can see here。

 a type of node an error tree and the success case of that saying would be a node and that's what we're doing here so basically make successful node is returns the maybe node with a success case that the success case guaranteed。

That contains the success kit， that's the better analogy and the make error full。

 I should have used note here， I'm going to fix it again。Is the same。

 but returns the maybe node that contains an error rather than。

A success case that's all it is they're just helper functions that we're going to use later in semantic analyzer。

And finally， some really simple functions， AST2 S string， again， like2 S string for。Experions。

 it works on ASD level， you pass it a pointer to an ASD。

 it prints it out to the it returns a string representation of that ASD just for debugging purposes。

And。The string I expert type since expert type itself is a enome and enomes are integer based。

We want to have a string representation of them again for debugging purposes。And finally。

 the do function， but you give it a reference to an ASD。

 it prints out the string representation in the studiodia。呃。

If you want to see the implementation of all these functions that we talked about。

 just look at the expression， that CPP file， it's not much most of them like we already had to define。

The other important functions here， like the make family here since they contain template types templates basically。

 we had to kind of implement them in the header files。

The CPP file only contains like the debug related functions and those are not important。Moving on。

 I'm going to show you some。Some of the actual node implementations。

 the first one and the simplest one is a symbol。So as you can see。

 a symbol is a node and is an expression， right？It inherits from expression。

 it has just one property， which is a name publicly available。In the constructor， as you can see。

 we need to get the location range and then en name。So here is like until now。

 whatever we talked about our kind of。C+ plus only。

 but from now on we're entering the LLVM territory。

We might see some types from the LLVM right now here and there。

 but in the near future we would be all about LLVM and MLLIR。

 but for now what you see here is LLVM a stringing ReF， which is a reference type made in LLVM。

 it's supposed to be really fast。And it's a reference type。

 it doesn't own the value if you're interested about。This kind of stuff。

 make sure to look at the I'm going to include the link in the description。

 but there's a programming manual in LLVM documentation。



![](img/f796fd9bddbbd1ef077afe0a51b14f04_1.png)

It's really complete it's really complete， it describes everything from different types they provide for different purposes like different string types。

 different。

![](img/f796fd9bddbbd1ef077afe0a51b14f04_3.png)

I don't know collection types， array types and many other stuff， it's really good to know them。

 but little by little when we get to use any of those，Types and functionalities。

 I'm going to talk about them a little bit as well。

 so a string we is just a reference type on a string， it doesn't own the actual value。Okay。

So that's the constructor， pretty simple， caused the parent constructor to set up the location and finally sets the name。

Oh okay， and here is how we can create a this is like a copy copy constructor for the symbol to create a symbol out of another one。

The get type， the two strings and the other two are from the expression interface。

 but here's an here's an。Here's important aesthetic method here， aesthetic function here， sorry。

The class of， it wasn't part of the interface， but all of our node have to have the class of implemented in for their own type。

 what is class of and what does it do， it's pretty simple if you see the implementation。

 it's actually quite simple。But。Basically， we need to include class of with the same name into our。

Classes that we want to cast。Either statically or dynamically using the casting functionality of LLVM。



![](img/f796fd9bddbbd1ef077afe0a51b14f04_5.png)

In the programmer manual， there's。Good chunk good chunk of information about。Basically， the。

Statatic and dynamicing cast of LLVM give me the read it's really nice basically they try to avoid expensive use of RTTIs in LLVM so they came up with their own casting functionality and it's supposed to be pretty fast I never actually ran any benchmark or something to see whether it's fast or not I trust the LLVM community。

Basically how it works is in order to be able to convert and cast a type to another compatible type。

 you your class need to implement a static method called classO。

Which returns like a I'm going to show you the actual implementation。

 but what happens is LLVM will call that function to determine whether it can cast this function this class to another compatible class or not。

 if it can it will do the job for us， if it can based on the casting you need for example。

 case of a dynamic cast， it either returns Neil or in case of an aesthetic cast。

 it raises an exception in compile time。

![](img/f796fd9bddbbd1ef077afe0a51b14f04_7.png)

Though。Let's have a look at how it works。😔，吔屎冇。Okay， here's the implementation of the symbol。No。

 actually this should be like this I am kind of。😔，Accist with using the right。

Ising the right syntax here。So。You see。😊，The get type supposed to return an expert type that。

Demonstrate that type or。A better term would be。git type would return expert type that basically returns the type of the current node and the current node is symbol。

 so we just return the symbol value for the expert type you know。To a string again。

 as I mentioned earlier is just for debugging， we want like the a string representation of the symbol should be something like this。

 also talking since we entered the。LLVM territory， LLVM provides many like utility functions to avoid using any kind of a third party library in the project in the compiler and their implementations are。

Faster than like normal libraries。One of them one of the utility functions is format V。

 which is exactly like a format function， you pass it a string and provide the placeholders for that string and it formats the string for you also it is compatible with the obviously compatible with the rest of the LLVM ecosystem so if you need a string graph here。

 it can cast the return type of format V to a string graph or other types of a strings that LLVM has。

I'm not going to talk about the analyze here， but the class up， as you can see。

It should return the billion。It gets an expression， a pointer to an expression。

And we want to know whether。The expression that we got。

Is a symbol or not right so what happens here when we want to cast an expression to a symbol right？

I have to show you an example， so。Let's say we have something like this。And we am。Oops。

I have autoshift enabled on my keyboard， that's why I。诶。Mess up sometimes。So。Once。

So if we do something like this and even one supposed to be a note， right？

When we do something like this， what happened is。LLVM is going to call the class of method of symbol。

Since the symbol is the type that we want to cast to， it's going to call this method here。

 this function here， sorry again， I'm using wrong terminology here。It calls a class of function。

 the aesthetic function on the symbol class and passes the expression to it， so expression。

 the E variable here， the E argument here would be the E1 here， right。

What we do here is to call the get type of E if it returns symbol， then they are a compatible type。

 we can actually dynamically cast the E input the variable E to a symbol。

 and if it wasn't the symbol， then dynamic cast。Will return now。 And in in case of a static cast。

 it's going to。Praise an exception in comp。So。Also， there's more functions that we can use。

In this case， like there's another function called is， oh， it's better too。

Show you in the documentation， by the way， since I increase the font size in my editor。

 the jump you see is because it tries to show some hints and some error messages on the screen。

 but I already zoomed out it breaks basically。

![](img/f796fd9bddbbd1ef077afe0a51b14f04_9.png)

Okay， so as you can see， there's a function called is。You can use it like this， right。

 so is really a constant？Or is it an argument or is a global value。

 so global value argument and constant here are types that already have like implemented the class of function。

呃。These are like， quite。Useful functions to have， especially since they don't use RTTI。

 they're supposed to be really good。And the cost for us is only to implement that function in our。



![](img/f796fd9bddbbd1ef077afe0a51b14f04_11.png)

Note classes。Okay， moving on， let's let me show you。The number。Note or number expression type again。

 it's quite simple。It's like super， it's like a stupid， it's not even simple。Since at this stage。

 we only care about integers， I64。I keep it as a。A string， so when we read it from the source code。

We keep it into like we store it into a string and then we cast it to an I64 later。

 like is negative is obvious， its float is obvious since even we don't even support float here。

 but my plan was to support only integers and floats to begin with but I was like yeah that's too much。

 let's just stick with the bare minimum and the bare minimum is integers。

So in the future we have to change this to a proper implementation。

 but for now it's not our goal to have a proper number implementation， numerical implementation。

 we just stick with the bare minimum。It's really simple。

 just it has a function that cast the number to I64， that's it like two integers， basically。

Nothing special and the rest is kind of the same as symbol if we take a look at the。Sorry。😔，Yes。

 if we take a look at the implementation， it's not a big deal。

 it's kind of similar to what we had oh oh it has a generator IR unlike symbol。

 I'm not going to talk about it today， it needs its own time and episode。And finally。

 the kind of more complicated。Note we have one of the most complicated one， the list。

The heart of any lisp。So again， it's an expression， but it stores the elements as an ASD。List is。

 basically。An ASD on its own， right， so any element in the least。Or is an expression in fact。

 and list itself is an expression， so it can be a nested least un nested。

AST is basically that is what makes an ASD a tree， right， its elements can on its own be a tree。

Here is like the copy and move constructor not important， so we have two three main constructor。

 the first one that creates an empty list just gets a location。

 put it put the location like initialize the location and that's it no element。

 the second one gets one a reference of a node just a single node and use that node as the like put that node in the。

Elements here， basically， right， since the type is ASC。

 I'm trying to avoid any language that might be confusing。And finally。

 it takes an ASD and a vector of elements and create a list out of it easy， right？

I'm going to show you the implementation in a bit， but it has an append function that gets a node and obviously append that node into the elements in place。

I really don't like to mutate objects in place。We're looking like our goal is to have a bare minimum compiler。

 we don't care like we take care of these in the future。

Ac count that counts the number of elements that we have， a from function。

 you give it an index of the elements you want and it returns a new like it returns an ASD from that node to the end like if you know Python and let's say we have a list called X。

We can the from would be exactly something like this here。

 right it would be like give me a sublist from element number one till the end from is doing the exact same thing。

Okay， we have a new type here， LLVM optional。Optional type is like there might or might not be a value of type expression。

 a pointer to a expression。We have a function called at， right， we give it an index。

 the index might be out of range， like our least might contain like six elements and the index might be 10 for example。

At that case， since we return an optional type。The optional type is like our result type as well。

 it might have two values， the first one， the success case should be an expir。

 a pointer to an expir and the failure case would be nu no actually it would beium。No。

Did I write it right？No it would be LLVM non the failure case。

 so going I'm going to show how it works in the source code later on。

 but basically when you call the add function， you have to check the result to see whether it holds a value or it is none and you can do it by a I guess simple if。

So we have four functions here that are obviously quite familiar if you know C++。

 we can use them to create iterators out of a list and use a list as an iterator whatever we want。

 like in a for loop， for example。The other function members from our expression interface and finally the class the class of a static functions。

Let's have a quick look at the least implementation as well。😔，Le C。Okay。So。As you can see， the。

Constructor for copy and like this is the copy。A constructor， we just create a new list。

 gets the element from the other list， and put them in our own element。An immense storageage。

If what if we gets a node， this is the constructor to create a least with just one node and finally at least with an。

ASD of elements。Obviously gett typey has to return a list type。改钱包。For two a string。呃。

It's quite like， simpler。We'll look into our element storage if we don't have any element。

We return a dash。Otherwise， we set the value of S to an MTS string。Then。

We like loop in our elemented storage and call the two e string function， as you remember。

 the two e string member function is part of our expression interface so N supposed to be a node。

But right， elements isn't ASD， ASD is just a vector of nodes and。And should be a node。

 a reference to a node。 So and each node has to be an expression and expression has this。

Mem function。 So what happens is we just concatenate the。

Two a strings our elements together and finally we wrap them in a new a string to represent a list。

Quite simple。 I'm not going to talk about analyze again。 same goes for。嗯。

Cogen but here's our add function so if you as you can see we check whether the index is bigger than the size of the element or not and since we are using an on side integer we don't have to check the negative case so if it was bigger if the index was larger than our number of elements we just return LLVM none otherwise we return an optional value with the success case which is a pointer to the element in。

The right index。Same goes for from we we check the index to be in range and then create a new ASD。

Since ASC is a vector we're calling。Constructor from a constructor of the vector type and we pass it the starting point and the ending point of our own elements。

 elements is vector itself， so it creates a new ASD out of our elements from the provided locations and return it otherwise we return an empty ASD。

Append is quite easy just push back the given node。

 but we move the node here if you're not familiar with C++。Unfortunately。

 I can't talk about the move semantic S+ plus here it needs a。Complete。Episode on its own。

Basically to put it simply what what we're doing here is to move the ownership of type n into elements into our own node so the current list would be the new owner of。

Then node end here， but since。Th node is a shared pointer， it's kind of be like， okay。

 I own this as well， so whenever。We want to free。Notode in and read the memory associated with it we look into how many owners it has and if the owner counter was zero then we're freed we can free the node otherwise there's an owner pending so we can free it if you don't know about move and move semantics in C+ plus please read about it a little bit we're going to use it。

A lot in the future。But for now， you can think of it as we're removing the ownership of N。

Like giving the ownership of end to the current list。So I guess that's it for today。

 we like we have more notes to look into， but since they're kind of tight with other parts of the compiler like the semantic analyzer and。

C generator， I'm not going to talk about them today。 they need their own。Time is slot。

So that's it for today folks， please share your feedback with me also if you're interested in contributing to setting please let me know I would be it would make me really happy thanks for watching please subscribe to my channel if you liked my work and hope to see you in the next episode thank you。

handandb， sheep boy。

![](img/f796fd9bddbbd1ef077afe0a51b14f04_13.png)